---
title: '[Beta] Fraud protection studio'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-08-22T00:07:07Z'
  id: 30754984040977
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/30754984040977
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Resumo:** O FPS (Fraud Protection Studio) oferecem um maior controle sobre como a detecção de fraudes é aplicada. Com o FPS, você pode escolher se os dados de detecção de fraudes serão bloqueados e relatados como fraude ou tagged, permitindo o gerenciamento personalizado de fraudes.

## Sobre o Fraud Protection Studio

O Fraud Protection Studio introduz um status de detecção tagged.

Esse status permite que os anunciantes detectem fraudes sem implementar ações automaticamente.

* Avaliação: avalie o impacto das atualizações de detecção antes que elas sejam aplicadas.
* Controle: adapte a detecção de fraudes de acordo com seu modelo de negócios e suas necessidades.
* Transparência: os dados com tags fornecem insights sobre camadas adicionais de proteção contra fraudes.

> 🚧 **Importante!**
>
> Apenas as <Anchor target="_blank" href="/marketers/pt/docs/user-management#gerenciar-funções">funções</Anchor> de Administrador, Líder de marketing, Gerente de equipe e Segurança podem ter acesso ao Fraud Protection Studio.

## Como o Fraud Protection Studio funciona

<div id="key-concepts" />

<Accordion title="Principais conceitos">

#### Modos FPS

O FPS tem dois modos, **implementado** e **tagged**. Os anunciantes podem alternar entre esses modos com base em suas metas, garantindo que a detecção esteja alinhada às suas necessidades específicas.

**Mecanismo de detecção atual:** As instalações são consideradas:

* Atribuição **válida**
* **Detectadas**
  * **Bloqueadas** em tempo real
  * **Relatadas** como fraude pós-atribuição

[<Image alt="Image description" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />](https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png)   
**Mecanismo com FPS:** As instalações são consideradas:

* Atribuição **válida**
* **Detectadas** e
  * **Tagged**, mas permanecem **válidas** para atribuição
  * **Implementadas**
    * **Bloqueadas** em tempo real
    * **Relatadas** como fraude pós-atribuição

[<Image alt="Image description" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />](https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png)

> 📘 **Atenção**
>
> No modo tagged, todas as detecções de fraude tagged são consideradas válidas de acordo com a configuração do cliente e, como tal, não são creditadas no plano de consumo

#### Onde a detecção tagged é refletida?

Detecções tagged não são refletidas nos relatórios de fraude. Elas estão disponíveis nos relatórios de atribuição e no dashboard do Protect360 da seguinte forma:

**Relatórios**:

* Instalações tagged em tempo real
* Instalações tagged após a atribuição
* Eventos in-app tagged em tempo real
* Eventos in-app tagged após a atribuição

Dashboard do Protect360

[<Image alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />](https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png)

* Contagem total de tags nos componentes superiores da página (1)
* Tendência de overtime de "Status de detecção" (2)
* Fraude identificada por "Tipo de tag", "Motivo da tag", "Motivo da sub tag" (3)

</Accordion>

## Como usar o Fraud Protection Studio

<div id="general" />

<Accordion title="Geral">

O FPS é uma página de configuração que permite especificar quando você deseja que as detecções sejam [implementadas ou](/docs/beta-fraud-protection-studio#modos-fps) tagged. A plataforma ajuda a definir os requisitos de identificação, fornecendo:

* Dados de status de detecção.
* Opção de alternar entre os modos implementado e tagged.

Para começar:

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. Selecione o card no menu à esquerda. As opções atuais são:
   * [Click flood](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [Novos lançamentos](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="Detecção de click flood">

O FPS torna a gestão da detecção de click flood mais simples e personalizável. Ele permite o tagging de detecções de click flood no nível do aplicativo (todos os parceiros) e mostra dados de detecção de click flood identificados como tagged nos relatórios dedicados.

Na página do card de click flood, você pode [ver e ajustar o status de detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood) entre implementado e tagged, e visualizar os dados [atuais do status de detecção](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source).

Baixe a amostra de dados do relatório de click flood

> 🚧 **Importante!**
>
> * Quando a detecção de tags é selecionada, elas são relatadas em relatórios de dados brutos, não em relatórios de fraude.
> * O tagging de click flood é feito a nível de aplicativo e impedirá o bloqueio ou a implementação após a atribuição. Portanto, ao adicionar uma tag, você se expõe a riscos em suas instalações não orgânicas e orgânicas.

#### Como acessar click flood

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. No menu à esquerda, selecione o card **Click Flood**

### Clicar na página de click flood

A página de click flood é dividida em duas seções.

[Status de detecção](/docs/beta-fraud-protection-studio#status-de-detecção)

[Status de detecção atual](/docs/beta-fraud-protection-studio#status-de-detecção-atual)

#### Status de detecção

* [Status de detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood): Permite que você escolha o modo de [detecção](/docs/beta-fraud-protection-studio#modos-fps). Você pode escolher entre **implemented** e **tagged**.
* [Status atual da detecção](/docs/beta-fraud-protection-studio#status-de-detecção-atual) - Mostra como a ativação de Click Flood afetaria suas instalações e eventos relativos com base nos 7 dias antes da semana anterior. Essa seção se divide ainda mais em:
  * Widget de detecção atual
  * Widget de análise de detecção de click flood
  * Widget de click flood por fonte de mídia

#### **Como ajustar o status de detecção**

O status de detecção permite que você escolha o modo de [detecção](/docs/beta-fraud-protection-studio#modos-fps). Você pode escolher entre **tagged** e **identificado.**

1. Na janela Click Flood, escolha o [modo de detecção.](/docs/beta-fraud-protection-studio#modos-fps)
2. Clique no botão **Salvar** na parte inferior da página.

   [<Image alt="Expandable Image" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />](https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png)

#### **Status de detecção atual**

A seção de status de detecção atual mostra uma estimativa com base nos últimos 7 dias antes da semana anterior.

Nela, você encontra o seguinte:

* Widget de detecção atual
* Widget de análise de detecção de click flood
* Widget de click flood por fonte de mídia

**Widget de detecção atual**

* **Total de instalações** - a quantidade total de instalações do aplicativo
* **Detecção de click flood** - o total de click floods detectados
* **Detecção total** (sem click flood) - a quantidade total de detecções de fraude, sem incluir click flood
* **Detecção total** (com click flood) - a quantidade total de fraudes, incluindo click flood Calculado da seguinte maneira: [detecção de click flood + detecção total (sem click flood)] Calculado por: (deteção de click flood + deteção total (sem click flood)) Calculado por: (deteção de click flood + deteção total (sem click flood))

**Widget de análise de detecção de click flood**

Mostra uma análise detalhada da detecção de click flood por instalações orgânicas e não orgânicas.

**Widget de click flood por fonte de mídia**

Mostra uma análise das instalações que ocorreram por click flood, separadas por fonte de mídia.

Atenção: para obter um relatório mais detalhado, clique no botão **Exportar** para baixar as métricas de detecção como um arquivo CSV e fazer uma análise offline.

</Accordion>

<div id="new-releases" />

<Accordion title="Novos lançamentos">

Com os novos lançamentos, você pode avaliar o impacto das novas atualizações de detecção de fraudes antes da implementação. Por padrão, cada novo pacote de detecção de fraudes começa no modo tagged, permitindo que você tenha um maior controle para avaliar seu impacto.

Baixe a amostra de dados do relatório de novos lançamentos

> 📘 **Atenção**
>
> Um pacote de detecção é composto por uma ou várias atualizações de detecção que são agrupadas e lançadas juntas.

#### Como funciona

* As atualizações de detecção de fraudes são agrupadas em pacotes.
* Os pacotes de detecção de fraudes começam no [modo tagged](/docs/beta-fraud-protection-studio#modos-fps).
* Novos pacotes podem ser configurados para o modo tagged por até 14 dias.
* O pacote ativo atual pode ser avaliado e implementado.
* Você será notificado sobre novos lançamentos de pacotes por meio do sino de notificação.

#### Como acessar os novos lançamentos

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. No menu à esquerda, selecione o card **Novo lançamento**.

### Página de novos lançamentos

A página de novos lançamentos se divide em duas seções.

* [Lançamentos futuros](/docs/beta-fraud-protection-studio#como-acessar-os-novos-lançamentos) - permitem que você avalie o impacto de novos pacotes de detecção de fraudes, marcando as detecções como tagged por até 14 dias antes de entrarem em vigor.
* [Novas versões](/docs/beta-fraud-protection-studio#como-avaliar-e-implementar-os-pacotes-ativos-atuais) - permitem que você avalie o pacote ativo atual, monitorando a performance da sua detecção e implementando-o imediatamente.

#### Como definir o período de tempo do modo tagged para pacotes futuros

Os lançamentos futuros permitem que você configure o número de dias durante os quais você deseja que os pacotes sejam marcados como [tagged](/docs/beta-fraud-protection-studio#modos-fps) antes de entrarem em vigor. Para isso:

1. Na janela Novo lançamento, na caixa suspensa, selecione o número de dias durante os quais você deseja marcar novos pacotes como tagged antes de serem implementados (padrão: 14 dias, ajustável para até 14 dias)
2. Clique em **Salvar**.

<Image alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

> 📘 **Atenção**
>
> * Isso afeta somente pacotes futuros. Os pacotes de detecção que estão ativos não serão adiados nem alterados.
> * Selecionar 0 dias na caixa suspensa é o mesmo que selecionar [Implementar agora](/docs/beta-fraud-protection-studio#para-implementar-o-pacote-atual-com-o-status-tagged) e substitui as configurações de [lançamento futuro](/docs/beta-fraud-protection-studio#como-acessar-os-novos-lançamentos) desse pacote.

#### Como avaliar e implementar os pacotes ativos atuais

A seção Novo lançamento atual permite que você veja:

* O último pacote lançado
* Data de lançamento
* Status - quando esse pacote entrará em vigor (se estiver no modo tagged).
* Métricas que mostram como esse pacote de detecção afetará seus dados
* Exportação de relatórios detalhados
* Ignore as configurações de lançamentos futuros e implemente esse pacote de detecção agora

#### Para implementar o pacote atual com o status tagged

1. Abra o card **Novo lançamento** na aba FPS.
2. Monitore a performance da detecção usando a tabela e os relatórios exportáveis.
3. Quando estiver tudo pronto, clique em **Implementar agora** para aplicar as alterações.  
   [![](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)

> 📘 **Atenção**
>
> Isso substitui as configurações de [lançamento futuro](/docs/beta-fraud-protection-studio#como-acessar-os-novos-lançamentos) desse pacote.

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="Avaliação da detecção de aplicativos">

O card de avaliação da detecção de aplicativos permite que você altere o status de uma detecção com base nos seus objetivos de negócio. As decisões que você toma são aplicadas no nível do aplicativo e afetam todos os parceiros do anunciante.

Adicionar uma tag a uma detecção no card de avaliação da detecção de aplicativos influencia toda a lógica do Protect360. No entanto, as detecções acionadas pelas regras de validação definidas não são impactadas. Elas permanecem com o status "implemented", a menos que desative manualmente a regra de validação correspondente.

Na página de avaliação da detecção de aplicativos, você pode [ver e mudar o status de detecção para](/docs/beta-fraud-protection-studio#como-acessar-click-flood) "implemented" ou "tagged" e visualizar os  [dados atuais do status de detecção](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source).

> 🚧 **Importante!**
>
> * Quando a detecção de tags é selecionada, essas tags são informadas em relatórios de dados brutos, não em relatórios de fraude.
> * Adicionar uma tag a avaliação da detecção de aplicativos está no nível do aplicativo e impedirá o bloqueio ou a implementação de lógicas do Protect360 após a atribuição. Portanto, ao adicionar uma tag, suas instalações orgânicas e não orgânicas ficam expostas a fraudes.
> * Qualquer regra de validação definida e ativada permanecerá sempre no modo "implemented". Para pausar a implementação de quaisquer regras de validação, acesse a página das regras de validação e desative a regra.

#### **Como acessar a avaliação da detecção de aplicativos**

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 >** **Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. No menu à esquerda, selecione o card **Avaliação da detecção de aplicativos**.

#### **Página de avaliação da detecção de aplicativos**

A página de avaliação da detecção de aplicativos é dividida em duas seções.

* [Status de detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood): Permite que você escolha o [modo de detecção](/docs/beta-fraud-protection-studio#modos-fps). Você pode escolher entre "implemented" e "tagged".
* [Status de detecção atual](/docs/beta-fraud-protection-studio#status-de-detecção-atual): Mostra a detecção atual nas suas instalações e nos eventos relativos com base nos 7 dias anteriores à semana passada. Essa seção ainda se divide em:
  * **Lógicas do Protect360**   
    Modo de detecção "implemented":
    * **Taxa de implementação**: representa *a quantidade de lógica implementada pelas lógicas do Protect360* dividida pelo *total de atribuições do aplicativo*.
  * **Nível do aplicativo**  
    Modo de detecção "tagged":
    * **Taxa de tags**: representa *a quantidade de lógica com tags da avaliação da detecção de aplicativos* dividida pelo *total de atribuições do aplicativo*.
  * **Total de instalações**
  * **Total de detecções**
  * /docs/beta-fraud-protection-studio#adjust-detection-status
    * Lógicas do Protect360: Mostram a parcela da detecção feita pelas lógicas do Protect360. Ao mudar para "tagged", é a quantidade esperada de detecção que será convertida em detecção com tags.
    * Regras de validação: Mostra a parcela da detecção baseada nas regras de validação definidas e ativadas. Se você alterar o modo de detecção para "tagged", a detecção baseada nas regras de validação permanecerá no modo "implemented".
  * **Detecções com tags:** Usadas para ajudar você a decidir se deve mudar o [status de detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood) das tags para a implementação. Você poderá visualizar todos os motivos das tags conforme o resultado esperado antes de mudar o status de detecção de "tagged" para "implemented". 
    * Nível do aplicativo: Esse KPI permite que você descubra a parcela de tags adicionadas pelo card de avaliação da detecção de aplicativos. O número reflete o aumento previsto se você implementar o status de detecção.
    * Outras tags: Você pode adicionar tags à detecção em várias funcionalidades (cards) no Fraud Protection Studio.

#### **Como ajustar o status de detecção**

O status de detecção permite que você escolha o [modo de detecção](/docs/beta-fraud-protection-studio#modos-fps). Você pode escolher entre "implemented" e "tagged" (o padrão é "implemented").

1. Na página de avaliação da detecção de aplicativos, escolha o [modo de detecção](/docs/beta-fraud-protection-studio#modos-fps).
2. Clique no botão "Salvar" na parte inferior da página.

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="Detecção de hijacking de reengajamento">

No Protect360, a detecção de hijacking de reengajamento expande a cobertura padrão da detecção de fraudes especificamente para atividades de reengajamento. Esse tipo de detecção aumenta seu controle sobre o gerenciamento de fraudes.

Por padrão, esse tipo de detecção está disponível no [modo "tagged"](/docs/beta-fraud-protection-studio#modos-fps), permitindo que você avalie a eficácia e o possível impacto antes da implementação.

#### Como funciona

* Por padrão, a detecção de hijacking de reengajamento está configurada para o modo "tagged". Você pode avaliar sua performance de detecção sem que isso afete seus dados de atribuição em tempo real.
* Quando implementadas, as detecções ocorrem após a atribuição, o que significa que reengajamentos fraudulentos são identificados e removidos dos registros de atribuição.
* Quando implementados, todos eventos in-app após uma remoção de detecção serão reatribuídos ao provedor de aquisição de usuários (UA) original ou marcados como orgânico se não existir um provedor de UA válido.

#### Como acessar

1. Faça login na **AppsFlyer**.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Selecione o aplicativo que você pretende configurar utilizando a lista suspensa na parte superior.
4. No menu à esquerda, selecione o card **Hijacking de reengajamento**.

#### Página de hijacking de reengajamento

A página de hijacking de reengajamento é dividida em duas seções.

* [Status da detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood): Permite que você escolha o [modo de detecção](/docs/beta-fraud-protection-studio#modos-fps). Você pode escolher entre "implemented" e "tagged".
* [Status de detecção atual](/docs/beta-fraud-protection-studio#status-de-detecção-atual): Mostra como a ativação do hijacking de reengajamento teria afetado suas instalações e eventos relativos com base nos últimos 14 dias (excluindo o dia atual).  
  **Observação:** uma vez que a detecção do hijacking de reengajamento funciona após a atribuição, os dados dos últimos 7 dias podem ser parciais e continuar se atualizando de maneira retroativa.  

  Essa seção se divide ainda mais em:
  * Widget de detecção de hijacking de reengajamento
    * Detecções: número de detecções somente pela lógica de hijacking de reengajamento
    * Taxa de detecção: porcentagem de detecções de hijacking de reengajamento fora da detecção de reengajamento
  * Widget de detecção de reengajamentos totais: quantidade de detecção de reengajamento geral de todas as lógicas
  * Widget de volume de atribuição de reengajamento
    * Atribuições: quantidade de atribuição de reengajamento no período
    * Taxa fora do total de atribuições: parcela das atribuições de reengajamento de todas as atribuições do aplicativo
  * Detecção de reengajamento por fonte de mídia: número de detecções de hijacking de reengajamento para as principais fontes de mídia detectadas

<Image alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="Detecção baseada no aplicativo">

De maneira determinística, a detecção baseada no aplicativo marca as instalações como fraude na pós-atribuição através da análise de anomalias do comportamento no aplicativo. Ela identifica esquemas de fraude sofisticados, como bots que imitam o engajamento real, mas exibem fluxos de evento incomuns e padrões de tempo desde a instalação.

#### Como acessar

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. No menu à esquerda, selecione o **card de detecção baseada no aplicativo**.

#### Página de detecção baseada no aplicativo

A página de detecção baseada no aplicativo é dividida em duas seções.

* [Status de detecção](/docs/beta-fraud-protection-studio#como-acessar-click-flood): Permite que você escolha o  modo de detecção. Você pode escolher entre "implemented" e "tagged".
* [Status de detecção atual](/docs/beta-fraud-protection-studio#status-de-detecção-atual): Mostra como a ativação da detecção baseada no aplicativo teria afetado suas instalações com base nos últimos 14 dias (excluindo o dia atual).   

  Observação: uma vez que a detecção baseada no aplicativo funciona após a atribuição, os dados dos últimos 7 dias podem ser parciais e continuar se atualizando de maneira retroativa.

Essa seção ainda se divide em:

* **Novas detecções por lógica baseada no aplicativo**
  * Detecções: número de instalações detectadas pela lógica no aplicativo
  * Taxa de valor agregado: detecção baseada no aplicativo dividida pelo total de instalações do seu aplicativo
* **Instalações falsas detectadas**
  * Detecções: número total de detecções falsas
  * Taxa de detecção: detecções falsas divididas pelo total de instalações do aplicativo
* **Total de instalações**

* **Detecção baseada no aplicativo por fonte de mídia**: número de instalações pelas principais fontes de mídia

<Image alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="Página do módulo avançado de segurança">

Revise as detecções do módulo avançado de segurança para ataques cibernéticos em tempo real relacionados a possíveis instalações em aplicativos Android. Isso ajuda a garantir que somente o tráfego verificado chegue ao seu aplicativo.

#### Como acessar

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse **Configurações > Protect360 > Fraud Protection Studio**.
3. Use o menu suspenso na parte superior da página para selecionar o aplicativo que você deseja configurar.
4. Selecione o card **Módulo avançado de segurança** no menu à esquerda.

#### Página do módulo avançado de segurança

A página do módulo avançado de segurança mostra:

* **Principais versões do aplicativo**: as 5 principais versões do aplicativo por volume de instalação, para que você possa identificar onde o tráfego fraudulento se concentra.

As deteções são apresentadas como uma das seguintes:

* **Blocked**: Tráfego parado em tempo real, antes da atribuição.
* **Tagged**: Tráfego sinalizado como suspeito, mas atribuído, para que você possa analisar antes de tomar uma decisão. Esse é o modo de detecção padrão.
* **Untagged**: Possíveis instalações que o módulo não sinalizou.

> 📘 **Atenção**
>
> Para a configuração completa, requisitos e relatórios detalhados, consulte <Anchor target="_blank" href="/marketers/pt/docs/beta-advanced-security-protect360-module">[Beta] Módulo avançado de segurança do Protect360</Anchor>.

</Accordion>

## Perguntas frequentes

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="Posso configurar a detecção tagged para parceiros ou canais de mídia?">

Depende do tipo de detecção. Por exemplo, o tagging de parceiros não está disponível para detecção de hijacking, para evitar uma detecção tendenciosa.

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="O que acontece quando o período de tagging termina?">

No final desse período, a detecção tagged é convertida automaticamente para o modo implementado.

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="Onde posso ver as instalações tagged?">

Os dados com tags estão disponíveis nos seguintes **relatórios de dados brutos**:

* Instalações com tags
  * Em tempo real
* Instalações com tags
  * Pós-atribuição
* Eventos in-app com tags
  * Em tempo real
* Eventos in-app com tags
* Pós-atribuição

O relatório com tags abaixo também está disponível no **Data Locker**:

* Instalações com tags
  * Em tempo real
* Eventos in-app com tags
  * Em tempo real

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="A detecção tagged pode ser ajustada para configurações específicas do aplicativo?">

Sim, o tagging de click flood pode ser configurado no nível do aplicativo.

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="Posso ver eventos in-app tagged?">

Sim. Eventos in-app conectados a uma instalação tagged pelo mesmo AppsFlyer ID também serão identificados como tagged.

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="Quem pode alterar, configurar ou visualizar o FPS?">

Somente o administrador pode alterar a configuração do FPS. O FPS pode ser acessado de acordo com a configuração da <Anchor target="_blank" href="/marketers/pt/docs/manage-data-access-permissions">página de permissões</Anchor>.

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="As instalações tagged são creditadas no plano de consumo?">

Não. A detecção marcada não será creditada de volta ao plano de consumo.

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="As instalações tagged são consideradas fraudes?">

As instalações tagged são detectadas pelo Protect360. No entanto, eles são marcados de acordo com a configuração do cliente. Assim, tanto no dashboard de visão geral quanto nos dashboards do Protect360, elas serão refletidas nas métricas atribuídas.

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="Posso ver quantas instalações são identificadas como tagged apenas pelo tagging de click flood?">

Sim. Esses dados estão disponíveis nos novos relatórios na página de exportação e no dashboard do Protect360.

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=sobre-o-fraud-protection-studio 01JEQR86DC1CK03DKCZH760N4M=sobre-o-fraud-protection-studio h_01JK3BGVNMYFQYQGRPJBVN2A7Z=importante how-flexible-protection-works=como-o-fraud-protection-studio-funciona 01JEQR86DEG7RTRNYFP02WHJGQ=como-o-fraud-protection-studio-funciona 01JETRN5S347ZXV8CGZJDHQH56=key-concepts fps-modes=modos-fps h_01JEWZEBBA9VAPCKR87NJ5AK3C=modos-fps 01JEWZQ7PBD6W4J15W0HE2Q4MJ=aten%C3%A7%C3%A3o where-is-tagged-detection-reflected=onde-a-detec%C3%A7%C3%A3o-tagged-%C3%A9-refletida 01JEWZT9N34FZ9SE8H7EGCMPBZ=onde-a-detec%C3%A7%C3%A3o-tagged-%C3%A9-refletida how-to-use-flexible-protection=como-usar-o-fraud-protection-studio 01JEQR86ECSYTM7RN3YPYRSAGE=como-usar-o-fraud-protection-studio 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=importante-1 adjust-detection-status=como-acessar-click-flood 01JEQVJS6YTQD299X39Q8E3506=como-acessar-click-flood click-flood-page=clicar-na-p%C3%A1gina-de-click-flood h_01JJKE1ZKE5WDRSPKS8JE9MRRG=clicar-na-p%C3%A1gina-de-click-flood detection-status=status-de-detec%C3%A7%C3%A3o h_01JZQ81MW4HMY9B782Y7PWVE8Y=status-de-detec%C3%A7%C3%A3o h_01JJKE1ZKEJ4QM2HTT37FERA92=como-ajustar-o-status-de-detec%C3%A7%C3%A3o current-detection-status=status-de-detec%C3%A7%C3%A3o-atual 01JEQVZCNSTXY4V8H2Y1QP224C=status-de-detec%C3%A7%C3%A3o-atual 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=aten%C3%A7%C3%A3o-1 how-this-works=como-funciona h_01JEXC0ABSTCEA939DGQ5SDJBJ=como-funciona how-to-set-the-tagged-mode-time-period-for-future-packages=como-acessar-os-novos-lan%C3%A7amentos h_01JEXC2HAR2S6BWK28N8W3HHSZ=como-acessar-os-novos-lan%C3%A7amentos new-releases-page=p%C3%A1gina-de-novos-lan%C3%A7amentos h_01JJKE1ZKE0K1W2VE3KHQ639B1=p%C3%A1gina-de-novos-lan%C3%A7amentos h_01JJKE1ZKE13D7EC6BMN3JJNGW=como-definir-o-per%C3%ADodo-de-tempo-do-modo-tagged-para-pacotes-futuros 01JF50BVZ75ZSXTJEKAV4HVSTZ=aten%C3%A7%C3%A3o-2 how-to-evaluate-and-implement-current-active-packages=como-avaliar-e-implementar-os-pacotes-ativos-atuais h_01JEXC3DESR10WVV34ED30B7BH=como-avaliar-e-implementar-os-pacotes-ativos-atuais to-implement-the-current-package-if-in-tagged-status=para-implementar-o-pacote-atual-com-o-status-tagged h_01JF505FK4NP88WYXP8PVQRYDS=para-implementar-o-pacote-atual-com-o-status-tagged 01JF50BVZ9QPT5W41P8KQAREKV=aten%C3%A7%C3%A3o-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=importante-2 how-to-access-app-detection-evaluation=como-acessar-a-avalia%C3%A7%C3%A3o-da-detec%C3%A7%C3%A3o-de-aplicativos h_01JQXG4GJ2DB8HM26K3E1WA3A1=como-acessar-a-avalia%C3%A7%C3%A3o-da-detec%C3%A7%C3%A3o-de-aplicativos app-detection-evaluation-page=p%C3%A1gina-de-avalia%C3%A7%C3%A3o-da-detec%C3%A7%C3%A3o-de-aplicativos h_01JQXG6QDSTAPCJDMQVQMXS86W=p%C3%A1gina-de-avalia%C3%A7%C3%A3o-da-detec%C3%A7%C3%A3o-de-aplicativos how-to-adjust-the-detection-status=como-ajustar-o-status-de-detec%C3%A7%C3%A3o-1 h_01JQXG6QEAM0Y67G504JV2SA5R=como-ajustar-o-status-de-detec%C3%A7%C3%A3o-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=como-funciona-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=como-funciona-1 how-to-access=como-acessar h_01JWAVPAVK7ZT471AQAFKAS64K=como-acessar reengagement-hijacking-page=p%C3%A1gina-de-hijacking-de-reengajamento h_01JWAVPAVKKB4JSP41P967EESS=p%C3%A1gina-de-hijacking-de-reengajamento h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=como-acessar-1 h_01JZMAZET0JXYEDGKE0B797TQ7=como-acessar-1 the-inapp-based-detection-page=p%C3%A1gina-de-detec%C3%A7%C3%A3o-baseada-no-aplicativo h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=p%C3%A1gina-de-detec%C3%A7%C3%A3o-baseada-no-aplicativo advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=como-acessar-2 h_01K0ASM07ADVSECMOD07=p%C3%A1gina-do-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a the-advanced-security-module-page=p%C3%A1gina-do-m%C3%B3dulo-avan%C3%A7ado-de-seguran%C3%A7a h_01K0ASM13ADVSECMOD13=aten%C3%A7%C3%A3o-4 faqs=perguntas-frequentes 01JEQR86EMZQFNSZ5NWZ08F5YQ=perguntas-frequentes 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />
