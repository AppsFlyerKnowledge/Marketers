---
title: Beta - Módulo Protect360 de segurança avançada
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-11-02T01:04:13Z'
  id: 39145848948625
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/39145848948625
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Resumo:** Fortaleça a proteção contra fraudes do seu aplicativo Android com o módulo avançado de segurança. Essa solução detecta e bloqueia o spoofing de atribuição e o tráfego manipulado em tempo real, antes que as instalações sejam atribuídas. Ela foi projetada para aplicativos que possuem um tráfego elevado e para clientes do Protect360, especialmente aqueles que trabalham com afiliados. O módulo pode ser totalmente configurável, permitindo que a configuração inicial e a manutenção contínua se adaptem aos padrões de fraude em evolução, protegendo a integridade dos seus dados.

<div id="important" />

> 🚧 **Importante!**
>
> O beta do módulo avançado de segurança do Protect360 está disponível para todos os clientes do Protect360. Para participar, entre em contato com seu CSM.

<div id="what-is-sdk-spoofing" />

## O que é spoofing de SDK?

Uma tática avançada de fraude em que os ataques enviam solicitações falsas de instalação e eventos in-app diretamente para os servidores da AppsFlyer, sem instalar ou executar o aplicativo em um dispositivo real. O SDK do aplicativo não é hackeado ou modificado: os fraudadores imitam as solicitações de rede que um aplicativo real enviaria, fazendo com que a atividade pareça legítima. O SDK do aplicativo não é hackeado ou modificado: os fraudadores imitam as solicitações de rede que um aplicativo real enviaria, fazendo com que a atividade pareça legítima.

Para os anunciantes, o spoofing de SDK pode levar a instalações e engajamentos que nunca ocorreram, volumes de instalação inflacionados, discrepâncias entre os números da AppsFlyer e da loja de aplicativos e desperdício no investimento em anúncios.

<div id="about-the-advanced-security-module" />

## Sobre o módulo avançado de segurança

O **modulo de segurança avançado** é um complemento do conjunto de ferramentas do Protect360 da AppsFlyer, projetado para detectar e bloquear técnicas avançadas de spoofing de atribuição no Android. Ao avaliar a atividade de instalação após a primeira abertura do aplicativo, antes da ocorrência da atribuição, o módulo identifica tráfego suspeito e evita que instalações fraudulentas afetem suas métricas de performance.

Essa solução é especialmente útil para aplicativos que enfrentam discrepâncias entre os dados da loja de aplicativos e a atribuição da AppsFlyer, ou aqueles que gerenciam o tráfego de afiliados, dois indicadores comuns de fraude de instalação.

**Como funciona**

O módulo é acionado após a primeira abertura do aplicativo (registrada pelo SDK), antes que a instalação seja atribuída. Para usar o módulo avançado de segurança, você deve usar o Android SDK v6.15.2 ou versões mais recentes.

<div id="prerequisites" />

## Pré-requisitos

Antes de começar, certifique-se de que você tem o seguinte:

* **SDK do Android v6.15.2 ou posterior** integrado ao seu aplicativo.
* **Um token da API V2** — necessário para a autenticação no repositório Maven quando seu desenvolvedor integrar a dependência do Módulo de Segurança. Consulte <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#aplicações-o-token-api-v2">Gerenciamento de tokens da AppsFlyer</Anchor> para saber como recuperar ou gerar um.
* **Todos os hashes de certificado (SHA-256)** de cada certificado usado para assinar seu aplicativo (debug e release). Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint">Como gerar uma impressão digital SHA256</Anchor>.

<div id="important-1" />

> 🚧 **Importante!**
>
> Se a sua conta já atingiu o limite de dois tokens da API V2, você não precisa solicitar um novo; um token da API V2 existente pode ser reutilizado para esta integração. Entre em contato com seu CSM se tiver dúvidas sobre a alocação de tokens.
>
> Para ver as etapas completas da integração técnica, consulte o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin">guia do desenvolvedor do plugin de segurança do Android</Anchor>.

<div id="set-the-advanced-security-module" />

## Configure o módulo avançado de segurança

Configure o módulo avançado de segurança para validar se o tráfego in-app está vindo de versões oficiais assinadas do seu aplicativo e para detectar (e opcionalmente bloquear) tráfego falsificado.

<Accordion title="Configure o módulo avançado de segurança">

<div id="step-1-open-and-select-an-app" />

#### 1º passo: Abra e selecione um aplicativo

1. Na AppsFlyer, vá para **Configurações > Protect360 > Módulo avançado de segurança**.
2. Clique em **Começar** ou **Adicionar build**.
3. Selecione o aplicativo no qual você deseja implementar a solução de módulo avançado de segurança.
4. Clique em **Próximo**.

<div id="step-2-add-certificate" />

#### **2º passo: Adicionar certificado**

1. Adicione:
   1. <span class="af-ol-a"></span>Nome do certificado
   2. Valor do certificado
2. Clique em **Próximo**.

Atenção: Peça ao seu desenvolvedor todos os [hashes de certificado](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint) usados para assinar o aplicativo. O módulo de segurança usa esses certificados para validar se o tráfego vem do seu aplicativo. Portanto, todos os hashes relevantes devem ser incluídos.

<div id="step-3-excluded-app-versions-from-detection" />

#### **3º passo: Versões de aplicativos excluídas da detecção**

* Adicione as versões do aplicativo que devem ser excluídas da detecção de segurança avançada. Normalmente, elas incluem:
  * Versões lançadas antes da integração do módulo avançado de segurança.
  * Builds de teste ou builds legados que não incluem o módulo.

<div id="step-4-build-activation" />

#### **4º passo: Ativar build**

1. Clique em **Ativar build**.
2. Seu build terá o status **em andamento** até que o build seja concluído. Isso pode levar de 10 a 15 minutos.
3. Uma vez concluído, copie o código clicando no botão **copiar código** no build e envie-o ao seu desenvolvedor para integrar ao SDK do aplicativo.

<div id="note" />

> 📘 **Atenção**
>
> Feito o build, o modo de detecção fica definido como **tagged** por padrão. Nesse modo, a AppsFlyer sinaliza qualquer tráfego suspeito, mas não o bloqueia. Depois que a versão segura estiver ativa, mude para o modo **implemented** para bloquear o tráfego falsificado. Para obter mais informações sobre os modos Tagged e Implemented, consulte <Anchor target="_blank" href="/marketers/pt/docs/beta-fraud-protection-studio#modos-fps">FPS Modes</Anchor>.

</Accordion>

<Accordion title="Manter e atualizar a configuração">

As técnicas de fraude evoluem ao longo do tempo, e os fraudadores podem tentar reverter a lógica de detecção. A manutenção regular garante uma eficácia contínua.

<div id="when-to-update-the-configuration" />

#### **Quando atualizar a configuração**

Atualize suas configurações se você perceber:

* Instalações ou eventos suspeitos que não estão sendo detectados
* Alterações nos padrões de tráfego
* Novas versões do aplicativo ou alterações no certificado
* Menor eficácia das proteções existentes

<div id="what-you-can-update" />

#### **O que você pode atualizar**

Você pode:

* Adicionar ou atualizar certificados do aplicativo
* Modificar versões de aplicativos excluídas
* Refazer e redefinir o módulo de segurança
* Ajustar o modo de detecção com base no status de implementação

<div id="best-practices" />

#### **Práticas recomendadas**

* Revise os insights de segurança avançada regularmente
* Coordene com os desenvolvedores antes de lançar o aplicativo
* Atualize certificados imediatamente após assinar as alterações
* Revise a configuração periodicamente para se manter atualizado sobre os métodos de fraude emergentes

</Accordion>

<div id="data-visibility" />

## **Visibilidade de dados**

A detecção do módulo avançado de segurança pode ser visualizada em dois dashboads:

* Dashboard do Protect360
* Fraud Protection Studio

<Accordion title="Dashboard do Protect360">

A detecção do módulo avançado pode ser visualizada na seção **Spoofing de atribuição**.

Os dados são separados em dois KPIs e um gráfico.

**KPIs**

* **Spoofing de atribuições no modo tagged**: número de candidatos à instalação detectados pelo módulo avançado de segurança no modo tagged.
* **Spoofing de atribuição no modo implemented**: número de candidatos à instalação detectados e bloqueados pelo módulo avançado de segurança no modo implemented.

**Gráfico**

* **Tendência de spoofing de atribuição**: mostra a detecção feita pelo módulo avançado de segurança ao longo do tempo. Esse gráfico reflete o status de alto nível da detecção de spoofing no nível do(s) app(s).

<Image align="center" alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<Accordion title="Fraud Protection Studio (FPS)">

O módulo avançado de segurança pode ser encontrado na página do Fraud Protection Studio.

<div id="how-to-access" />

#### Como acessar

Para acessar o módulo avançado de segurança:

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse Configurações > Protect360 > Fraud Protection Studio.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. Selecione o card Módulo avançado de segurança no menu à esquerda.

<div id="the-advanced-security-module-page" />

#### Página do Módulo de segurança avançado

<Image align="center" alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

A página do Módulo avançado de segurança é dividida em três seções.

<div id="detection-status" />

##### Status de detecção

* Mostra o modo de detecção. As duas opções disponíveis são: implemented ou tagged. Por padrão, o modo é definido como **Tagged**.

Atenção: Para alterar o status de detecção, entre em contato com seu CSM.

<div id="top-app-versions-by-detection-status" />

##### Principais versões do app por status de detecção

* O gráfico mostra as 5 principais versões do aplicativo em termos de volume de instalações
  * Cada versão do aplicativo é dividida em:
    * **Untagged** - candidatos à instalação que não foram detectados pelo módulo avançado de segurança.
    * **Tagged** - candidatos à instalação detectados pelo módulo avançado de segurança no modo tagged.
    * **Bloqueado** - candidatos à instalação detectados pelo módulo avançado de segurança no modo implemented. Candidatos bloqueados não seguem para a próxima etapa do fluxo de atribuição.

##### Insights

Insights ajudam você a entender a análise do gráfico. Esses são os três tipos de insights exibidos:

* **Todo o tráfego foi bloqueado** - versões do aplicativo que tiveram o tráfego 100% bloqueado podem indicar que elas não foram adicionadas à lista de exclusão. Por favor, verifique a lista de exclusão com o seu CSM e considere adicionar a versão do aplicativo relevante.
* **Todo o tráfego foi marcado como tagged** - as versões do aplicativo que tiveram 100% do tráfego marcado como tagged podem não ter sido adicionadas à lista de exclusão. Por favor, verifique a lista de exclusão com o seu CSM e considere adicionar a versão do aplicativo relevante.
* **Uma ou mais** versões do aplicativo mostram mais de 20% de detecções do módulo avançado de segurança no modo tagged. Entre em contato com seu CSM para mudar para o modo implemented e obter resultados melhores.

</Accordion>

<Accordion title="Perguntas frequentes">

<div id="what-is-advanced-security" />

#### O que é a segurança avançada?

A segurança avançada é uma camada de proteção adicional para o SDK Android da AppsFlyer que ajuda a evitar o spoofing de atribuição, um tipo de fraude no qual instalações ou eventos falsos são relatados mesmo quando nenhum usuário real instalou ou usou o aplicativo.

<div id="what-problem-does-advanced-security-solve" />

#### Quais problemas a segurança avançada resolve?

A segurança avançada ajuda a evitar instalações falsas e atividades in-app geradas por falsificações que aparecem na AppsFlyer, mas que não foram registradas na loja de aplicativos ou nos sistemas de backend. Isso reduz o número de instalações inflacionadas, discrepâncias de dados e desperdício do investimento em anúncios.

<div id="what-is-attribution-spoofing" />

#### O que é spoofing de atribuição?

O spoofing de atribuição é uma técnica de fraude em que os ataques geram dados de instalação ou eventos in-app falsos, que são enviados para a AppsFlyer como se tivessem vindo do seu aplicativo. Nenhuma instalação ou atividade feita por um usuário real ocorre.

<div id="how-does-advanced-security-prevent-attribution-spoofing" />

#### Como a segurança avançada previne o spoofing de atribuição?

A segurança avançada verifica se os dados de instalação e eventos in-app realmente vieram do SDK do seu aplicativo, adicionando uma assinatura de verificação exclusiva a cada solicitação. A AppsFlyer verifica essa assinatura para confirmar que os dados são genuínos e não foram falsificados ou manipulados.

<div id="does-advanced-security-affect-the-app-or-user-experience" />

#### A segurança avançada afeta o aplicativo ou a experiência do usuário?

Não. A segurança avançada é executada em segundo plano e não altera a forma como os usuários instalam ou usam o aplicativo. Qualquer processamento adicional acontece nos bastidores e não é perceptível para os usuários.

<div id="who-should-use-advanced-security" />

#### Quem deve usar a segurança avançada?

A segurança avançada é mais relevante para aplicativos que trabalham majoritariamente com redes não-SRN ou redes afiliadas, que observam lacunas inexplicáveis entre as instalações da loja de aplicativos e dados registrados pela AppsFlyer ou suspeitam de fraudes sofisticadas que são difíceis de detectar usando métodos padrão.

<div id="is-advanced-security-available-for-all-platforms" />

#### A segurança avançada está disponível para todas as plataformas?

Não. No momento, a segurança avançada está disponível apenas para aplicativos Android e é oferecida a clientes premium do Protect360. Também é compatível com todos os plugins da AppsFlyer.

<div id="how-do-i-know-advanced-security-is-working" />

#### Como sei que a segurança avançada está funcionando?

Os resultados da detecção ficam disponíveis no dashboard do Protect360 e no Fraud Protection Studio, onde você pode acompanhar o tráfego falsificado marcado como tagged ou que foi bloqueado, acompanhando tendências ao longo do tempo.

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=importante what-is-sdk-spoofing=o-que-%C3%A9-spoofing-de-sdk h_01KH8MPFJBSN67PSQXX25NG6ZZ=o-que-%C3%A9-spoofing-de-sdk about-the-advanced-security-module=sobre-o-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a h_01K5C4BCNRE8JWQ9DA20DJ3A07=sobre-o-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a h_01K9PRQNEWSECTION0001AB=pr%C3%A9-requisitos prerequisites=pr%C3%A9-requisitos h_01K9PRQNEWSECTION0002AB=importante-1 set-the-advanced-security-module=configure-o-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a h_01KHK6M3CTY4YSCRTSMS707S5Z=configure-o-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a step-1-open-and-select-an-app=1%C2%BA-passo-abra-e-selecione-um-aplicativo h_01KH8XDACWA2C46MEEGFMM6J8M=1%C2%BA-passo-abra-e-selecione-um-aplicativo step-2-add-certificate=2%C2%BA-passo-adicionar-certificado h_01KH8XDACYBFZJWHZZCD0JSNGJ=2%C2%BA-passo-adicionar-certificado step-3-excluded-app-versions-from-detection=3%C2%BA-passo-vers%C3%B5es-de-aplicativos-exclu%C3%ADdas-da-detec%C3%A7%C3%A3o h_01KH8XDAD08E1JJVVSV9GY4RAB=3%C2%BA-passo-vers%C3%B5es-de-aplicativos-exclu%C3%ADdas-da-detec%C3%A7%C3%A3o step-4-build-activation=4%C2%BA-passo-ativar-build h_01KH8XDAD122D7PWP2367YVNP2=4%C2%BA-passo-ativar-build h_01KH8XJXN717M3GDJNPPMWDBHY=aten%C3%A7%C3%A3o when-to-update-the-configuration=quando-atualizar-a-configura%C3%A7%C3%A3o h_01KH8XDAD3M4RARMK7DS7RA08X=quando-atualizar-a-configura%C3%A7%C3%A3o what-you-can-update=o-que-voc%C3%AA-pode-atualizar h_01KH8XDAD46P524Z2H8BBZRAR1=o-que-voc%C3%AA-pode-atualizar best-practices=pr%C3%A1ticas-recomendadas h_01KH8XDAD5PVKNPW37PMG3NKHH=pr%C3%A1ticas-recomendadas data-visibility=visibilidade-de-dados h_01K5C4BCNTBVDQX8DGTGEAN01T=visibilidade-de-dados how-to-access=como-acessar h_01K5C4BCNZBS424A4PMS7AR8XG=como-acessar the-advanced-security-module-page=p%C3%A1gina-do-m%C3%B3dulo-de-seguran%C3%A7a-avan%C3%A7ado h_01K5C4BCP14ARR3JMDPMRWZPTT=p%C3%A1gina-do-m%C3%B3dulo-de-seguran%C3%A7a-avan%C3%A7ado h_01K5C4BVN5CQVP8HJG1MBV72AW=status-de-detec%C3%A7%C3%A3o h_01K5C4BVN69SK4TBNWPFPWYXPN=principais-vers%C3%B5es-do-app-por-status-de-detec%C3%A7%C3%A3o h_01K5C4BVN6XA4SNP4TK9SSRHS9=insights what-is-advanced-security=o-que-%C3%A9-a-seguran%C3%A7a-avan%C3%A7ada h_01KH9HERVW7QE2JXCGBBC206VW=o-que-%C3%A9-a-seguran%C3%A7a-avan%C3%A7ada what-problem-does-advanced-security-solve=quais-problemas-a-seguran%C3%A7a-avan%C3%A7ada-resolve h_01KH9HERVX8V537KQBSMAR31T8=quais-problemas-a-seguran%C3%A7a-avan%C3%A7ada-resolve what-is-attribution-spoofing=o-que-%C3%A9-spoofing-de-atribui%C3%A7%C3%A3o h_01KH9HERVY5G1J5KQV9ZKTHGXX=o-que-%C3%A9-spoofing-de-atribui%C3%A7%C3%A3o how-does-advanced-security-prevent-attribution-spoofing=como-a-seguran%C3%A7a-avan%C3%A7ada-previne-o-spoofing-de-atribui%C3%A7%C3%A3o h_01KH9HERVZAT11WNX99R2EQCPB=como-a-seguran%C3%A7a-avan%C3%A7ada-previne-o-spoofing-de-atribui%C3%A7%C3%A3o does-advanced-security-affect-the-app-or-user-experience=a-seguran%C3%A7a-avan%C3%A7ada-afeta-o-aplicativo-ou-a-experi%C3%AAncia-do-usu%C3%A1rio h_01KH9HERW0XFEGCKGJZA6C44HY=a-seguran%C3%A7a-avan%C3%A7ada-afeta-o-aplicativo-ou-a-experi%C3%AAncia-do-usu%C3%A1rio who-should-use-advanced-security=quem-deve-usar-a-seguran%C3%A7a-avan%C3%A7ada h_01KH9HERW00N9M05DSF8998JE0=quem-deve-usar-a-seguran%C3%A7a-avan%C3%A7ada is-advanced-security-available-for-all-platforms=a-seguran%C3%A7a-avan%C3%A7ada-est%C3%A1-dispon%C3%ADvel-para-todas-as-plataformas h_01KH9HERW13WYZYBAGA9XXKW1B=a-seguran%C3%A7a-avan%C3%A7ada-est%C3%A1-dispon%C3%ADvel-para-todas-as-plataformas how-do-i-know-advanced-security-is-working=como-sei-que-a-seguran%C3%A7a-avan%C3%A7ada-est%C3%A1-funcionando h_01KH9HERW2CQ76W33ERFTP0FS9=como-sei-que-a-seguran%C3%A7a-avan%C3%A7ada-est%C3%A1-funcionando" />
