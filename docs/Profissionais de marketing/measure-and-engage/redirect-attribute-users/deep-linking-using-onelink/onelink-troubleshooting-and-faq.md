---
title: Solução de problemas e perguntas frequentes do OneLink
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-09-15T00:32:10Z'
  id: 360014821438
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/360014821438
---
> **At a glance:** encontre rapidamente soluções para testar e depurar problemas de redirecionamento/comportamento de links personalizados do OneLink.

<div id="onelink-troubleshooting-guide" />

## Guia de solução de problemas do OneLink

<div id="onelink-frequently-asked-questions" />

## Perguntas frequentes sobre o OneLink

<div id="onelink-template-faq" />

### Perguntas frequentes sobre o template do OneLink

<Accordion title="Qual método devo usar para iniciar aplicativos—Universal Links, App Links ou esquemas URI?">

**Universal Links:** Necessários para mais de 98% dos usuários do iOS

**App Links:** Para usuários do Android com a versão 6.0+. **Observação:** O Samsung OS não consegue abrir aplicativos usando Android App Links.

> 📘 **Note**
>
> Tanto os Universal Links quanto os App Links requerem uma prova de que o domínio na URL clicada (ou seja, o domínio do link personalizado do OneLink ou domínio de marca) pertence e está associado ao aplicativo específico que está tentando abrir. Essa associação de domínio é feita através do **arquivo Apple App Site Association (AASA)** para iOS e do arquivo **Assetlinks** para Android.
>
> Esses arquivos são hospedados pela AppsFlyer ou pelo anunciante em seu site. Por padrão, quando você cria templates do OneLink e configura Universal Links e App Links, esses arquivos são gerados e hospedados pela AppsFlyer.

**Esquemas URI:** Método principal para abrir aplicativos em dispositivos Samsung. Caso contrário, é usado um método herdado e de fallback para abrir aplicativos. Esse método pode ser usado:

* Para usuários do Android com versões anteriores a 6.0 (menos de 15% dos usuários do Android)
* Como um fallback para quando os Universal Links e App Links não abrem o aplicativo, ou porque não funcionam, ou porque não estão configurados. **Observação:** O uso de esquemas URI como fallback para Universal Links está sujeito a limitações do iOS. <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">Saiba mais</Anchor>.

#### Deep linking

Universal Links, App Links e esquemas URI são métodos seguros para **abrir** um aplicativo. Para fazer o deep linking e redirecionar usuários para atividades ou páginas específicas no aplicativo, siga as <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instruções de deep linking do OneLink</Anchor>.

</Accordion>

<Accordion title="Quais sistemas operacionais permitem que esquemas URI abram o aplicativo?">

| Sistema Operativo | Os esquemas URI funcionam para abrir o aplicativo? |
| --- | --- |
| https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png | **Sim.** Use como fallback em caso de falha dos Universal Links.<br /><br />**Notas Importantes:**<ul><li>O uso de esquemas URI como fallback está sujeito a limitações baseadas do iOS.</li><li>Para muitos navegadores, incluindo o Safari, você deve adicionar o parâmetro `af_force_deeplink=true` à URL para usar esquemas URI como fallback. <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">Saiba mais</Anchor>.</li><li>Se aparecer uma mensagem de erro dizendo: "Algo deu errado. O aplicativo não pôde ser aberto.” Isso geralmente significa que o aplicativo não está instalado ou que foi usado um esquema de URI incorreto.</li></ul> |
| Android / iOS | **Sim.** Use para dispositivos Samsung, versões do Android anteriores a 6.0 e como um fallback para quando os App Links falharem em versões posteriores do Android. |
| Amazon | **Sem** |
| Windows Mobile | **Sem** |

</Accordion>

<Accordion title="Preciso atualizar o aplicativo após a configuração de Universal Links do iOS e App Links do Android?">

**Sim.** Sempre que os Universal Links ou App Links são implementados para abrir o aplicativo para usuários existentes, iOS Associated Domains ou AndroidManifest.xml são atualizados. Isso significa que você deve enviar uma nova versão do aplicativo para a app store relevante. **Dica:** Para minimizar a necessidade de atualizações do aplicativo, faça todas as mudanças de dev necessárias para abrir o aplicativo e fazer o <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">deep linking</Anchor> de uma só vez.

</Accordion>

<Accordion title="Posso redirecionar os usuários existentes para uma página da web em vez do aplicativo?">

**Sim.** No entanto, se você configurar seu template com esse objetivo, todos os usuários (novos e existentes) serão afetados e enviados para a landing page/URL da web. Ou seja, novos usuários não são enviados para a app store.

Para enviar usuários para uma página da web:

1. No seu template, não configure Universal Links, App Links ou um esquema URI.
2. Quando o aplicativo não estiver instalado, configure os redirecionamentos para a landing page/URL da web.
   * A landing page/URLS da web são adicionadas como valores para os parâmetros af\_android\_url e af\_ios\_url.
   * Verifique se todas as URLs para as quais você está redirecionando usuários foram adicionadas à sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">domain redirect allowlist</Anchor>.
   * Os redirecionamentos também são aplicados automaticamente quando o aplicativo está instalado (para usuários existentes).

**Observação:** Se você quiser redirecionar usuários existentes para uma página na web mobile, somente após a abertura do aplicativo, o desenvolvedor do aplicativo deverá configurar esse comportamento.

</Accordion>

<Accordion title="Posso redirecionar usuários de tablet para um aplicativo ou URL diferente dos usuários de aplicativos mobile?">

Você pode definir redirecionamentos específicos para:

* Windows Phone
* iPad
* Amazon Kindle Fire

No momento, outros tablets não são compatíveis para redirecionamento separado.

</Accordion>

<Accordion title="Posso atribuir um aplicativo a vários templates do OneLink?">

**Sim.** Embora você possa usar um único template do OneLink para criar um número ilimitado de URLs do OneLink, em alguns casos talvez seja necessário atribuir um aplicativo a mais de um template do OneLink. Exemplo: se você tiver várias versões de um aplicativo Android para mercados fora da store, talvez seja necessário utilizar um template do OneLink separado para cada versão do Android, com o mesmo aplicativo do iOS atribuído a todas elas.

**Importante**:

Para templates que usam Universal Links do iOS e Android App Links para abrir o aplicativo, **caso os seus templates tenham subdomínios diferentes**, você precisará configurar e atualizar seus aplicativos do iOS e do Android para cada um:

* **Universal Links do iOS:** Após criar o novo template do OneLink e atualizar o domínio associado no aplicativo, envie uma nova versão para a App Store. Somente usuários do iOS que atualizaram para a nova versão podem ativar uma URL do OneLink criada no novo template.
* **Android App Links:**
  1. Após criar o novo template do OneLink, copie o trecho XML na parte inferior da seção de App Link e adicione-o ao arquivo **AndroidManifest.xml** dentro do intent no qual você deseja fazer deep linking, além de quaisquer intents anteriores.
  2. Envie a nova versão para a store. Somente usuários do Android que atualizaram para a nova versão podem ativar uma URL do OneLink criada no novo template

</Accordion>

<Accordion title="Posso excluir um template do OneLink?">

Atualizações do SO: **Novas atualizações do sistema operacional (iOS e Android) podem introduzir bugs inesperados que dificultam o deep linking.** Etapa 1:

**Para excluir um template:**

1. Na AppsFlyer, vá para a página de gerenciamento do OneLink.
2. Selecione o template do OneLink.
3. Clique na opção 'editar template' no menu de trê pontinhos.

   <Image alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />
4. Clique no ícone da lixeira.

**Atenção:** Se você tiver URLs do OneLink existentes com base no template excluído, **elas não funcionarão nem para levar usuários à loja de aplicativos.** Por isso, é particularmente importante que você não exclua um template sem antes se certificar de que não haja URLs do OneLink ligadas a ele. Como alternativa, considere se é possível obter os resultados necessários alterando a configuração do template existente em vez de excluí-lo.

</Accordion>

<Accordion title="Posso alterar o subdomínio em um template do OneLink?">

**Sim, desde que não haja links personalizados existentes na AppsFlyer com base no template.**

Se já houver links personalizados na AppsFlyer com base no template do OneLink, o subdomínio não poderá ser alterado. Essa limitação foi projetada para evitar quebrar o comportamento de redirecionamento/deep linking de links online.

Se você precisar alterar o subdomínio em um template em links personalizados existentes, você pode:

* Criar um novo template do OneLink com o novo subdomínio e criar links com base nele.
* Excluir todos os links personalizados existentes com base no template para o qual o subdomínio precisa ser alterado. Depois que todos os links baseados no template forem excluídos, o subdomínio torna-se editável.

</Accordion>

<Accordion title="O domínio/subdomínio de um template do OneLink pode ser aplicado ao ID do template de outro template?">

**Não.** Levar o subdomínio/domínio configurado a um template e ID de template específicos e concatená-lo manualmente a um ID de template diferente quebra a funcionalidade dos Universal Links e App Links, e representa uma ameaça à segurança.

**Nome do imposto sobre a receita líquida**

* O template 1ABC está configurado com o subdomínio **bank.onelink.me**.
* O template D123 está configurado com o subdomínio **game.onelink.me**.
* O link **bank.onelink.me/1ABC/shorturl** é criado com base no template 1ABC e funciona.
* O link **game.onelink.me/D123/exampleurl** é criado com base no template D123 e funciona.
* O link **game.onelink.me/1ABC/shorturl** não funciona
* O link **bank.onelink.me/D123/exampleurl** não funciona

</Accordion>

<Accordion title="Posso usar o mesmo subdomínio para mais de um template?">

**Sim. Entretanto, certifique-se de criar templates separados com o subdomínio; não apenas adicione manualmente o subdomínio a um ID de template.**

</Accordion>

<Accordion title="Como posso redirecionar usuários de desktop?">

Usuários de desktop podem se engajar com seus links personalizados do OneLink, por exemplo, por meio de uma campanha de e-mail. No entanto, quando usuários de desktop clicam nesses links, eles não podem ser redirecionados para um site mobile, app store ou aplicativo. Por padrão, os usuários de desktop são redirecionados para uma versão web da App Store ou da Google Play Store.

**Então, como posso oferecer aos usuários de desktop uma boa experiência e convertê-los em usuários mobile?**

Na URL ou template do OneLink, você pode redirecionar usuários de desktop (Windows ou Mac) para uma URL diferente. Essa URL da web é adicionada ao link no parâmetro `af_web_dp`. Verifique se todas as URLs para as quais você está redirecionando usuários foram adicionadas à sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">domain redirect allowlist</Anchor>. Caso contrário, o redirecionamento não funcionará.

**Atenção:** Se o link contiver `af_web_dp`, a AppsFlyer não registrará um clique quando vem de um desktop.

> 👍 **Tip**
>
> Tente redirecionar os usuários de desktop para uma URL da web que contém um formulário da web dedicado que envia uma URL do OneLink para o dispositivo mobile do usuário de desktop através de SMS ou e-mail. Saiba mais sobre essa opção como parte da solução de OneLink Smart Script.

</Accordion>

<Accordion title="Como posso redirecionar usuários do sistema operacional do Chrome?">

Os aplicativos no Chromebooks são considerados aplicativos para Android.

No Chromebook, para redirecionar novos usuários sem o aplicativo instalado para uma URL da web diferente:

1. Nas configurações do template do OneLink, em **Definir comportamento do link** > **Quando o aplicativo não está instalado** > **Android**, clique em **Alterar para uma URL diferente**.  
   OU  
   Nas configurações de link do OneLink, em **Deep linking e redirecionamento** > **Redirecionar** > **Quando o aplicativo não está instalado** > **Android**, selecione **URL Web**.
2. Insira a URL.  
   Quando adicionado através das configurações do link, a URL é adicionada ao seu link no parâmetro `af_android_url`.

</Accordion>

<Accordion title="Para qual aplicativo é registrado um clique no OneLink em desktop?">

O modelo do OneLink pode ser associado a dois aplicativos: um iOS e um Android. Quando um link do OneLink é clicado em um dispositivo mobile, o clique é registrado para o aplicativo correspondente à plataforma do dispositivo. Um clique em um dispositivo iOS é registrado para o aplicativo iOS, e um clique em um dispositivo Android é registrado para o aplicativo Android.

Quando um link do OneLink é clicado em um desktop, não há plataforma de dispositivo para corresponder. Nesse caso, o clique é registrado da seguinte forma:

* Se um aplicativo iOS e um aplicativo Android estiverem associados ao modelo, o clique será registrado para o aplicativo iOS.
* Se apenas um aplicativo estiver associado ao modelo, o clique será registrado para esse aplicativo.

</Accordion>

<div id="onelink-link-faq" />

### Perguntas frequentes do link OneLink

<Accordion title="O OneLink funciona sem o SDK da AppsFlyer?">

**Sim, mas apenas em parte.**

Se você precisa converter rapidamente visitantes de web mobile em usuários mobile e não consegue integrar o SDK da AppsFlyer, é possível fazê-lo.

O redirecionamento básico de usuários e o lançamento de aplicativos funcionam mesmo se o SDK da AppsFlyer ainda não estiver integrado ao aplicativo. Smart Banners também não exigem o SDK e também funcionam bem sem ele.

No entanto, a ausência do SDK significa que:

* Usuários que clicam não podem passar por deep linking além da inicialização do aplicativo.
* Os dados de atribuição não são registrados.
* Eventos in-app não são registrados.

</Accordion>

<Accordion title="Quais métodos estão disponíveis para criar links personalizados do OneLink?">

A tabela a seguir compara os diferentes métodos disponíveis para criar links personalizados do OneLink.

| Método de criação de link | Usos | URL curta/longa | Recurso premium | Visível na interface do usuário? | Atribuição TTL (Time to Live) máx e padrão |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Interface do usuário da AppsFlyer</Anchor> | Criar template do OneLink e links personalizados | Ambos | -- | ✓ | Sem TTL |
| <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> | Crie milhares de OneLinks rapidamente | Curto | ✓ | -- | 31 dias |
| <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">Criação de links em massa do OneLink</Anchor> | Crie milhares de URLs curtas do OneLink rapidamente usando os parâmetros definidos em um CSV | Curto | -- | -- | 365 dias |
| <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">SDK</Anchor> | Campanhas de convites de usuários (indicação) | Curto | -- | -- | 60 dias |
| <Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor> | Campanhas web-to-app mobile | Longo | -- | -- | Sem TTL |
| <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">Planilha</Anchor> | Crie milhares de links personalizados do OneLink aplicando suas próprias fórmulas | Longo | -- | -- | Sem TTL |

</Accordion>

<Accordion title="O que acontece quando eu excluo uma URL do OneLink da página de gerenciamento do OneLink?">

A partir de novembro de 2025,

* Depois que um link é excluído da seção de gerenciamento do OneLink, ele é removido da tabela e do banco de dados. Isso significa que, se um usuário final encontrar e clicar no link, ele será redirecionado com base nas configurações do modelo do OneLink. Os parâmetros de atribuição, os parâmetros de deep linking e as configurações de redirecionamento no nível do link não serão aplicados.
* O link deixará de funcionar em até 2 minutos após a exclusão.
* Os links excluídos pela interface após 5 de novembro de 2025 podem ser restaurados pela tabela **Links excluídos**, acessível no gerenciamento do OneLink.

  <Image alt="links excluídos.png" src="https://files.readme.io/d5a2cc7047fda06ba8249cc00b2830c309ec6137f10306cdabca61bcfe3d4d15-small-41829768141713.png" width="2768px" />
* Os links podem ser restaurados em até 90 dias a partir da data de exclusão. Se tiverem se passado mais de 90 dias desde a data de exclusão do link, ele não poderá ser restaurado.

</Accordion>

<Accordion title="Os links personalizados do OneLink podem abrir o aplicativo a partir de um navegador?">

**Sim,** mas observe que Universal Links e App Links só funcionam quando clicados (por exemplo, ao clicar em um link em uma página da web ou e-mail). **Colar o link na barra de endereços do navegador não iniciará o aplicativo.** Teste seus links clicando nas URLs, e não cole-as na barra de endereços do navegador.

</Accordion>

<Accordion title="Por que a URL do OneLink não abre o aplicativo ou faz um deep link de usuários existentes?">

Apesar das melhores intenções, em alguns casos, suas URLs do OneLink podem não executar o deep link pretendido. Quando isso acontece, no lugar de abrir o aplicativo ou fazer um deep link para uma atividade específica dentro do aplicativo, os usuários são redirecionados para a app store ou para uma página de erro.

Existem vários motivos possíveis para isso:

* Aplicativos host: **Aplicativos nos quais seus links de atribuição são compartilhados (por exemplo, WhatsApp, Gmail, WeChat) usam métodos diferentes para ativar links clicados, como navegadores internos proprietários. Alguns deles são conhecidos por bloquear todos os links de atribuição.**
* Navegadores: **Certos navegadores e plataformas de SO se comportam de maneira diferente com links. Em determinados navegadores, por exemplo, colar um link não funciona. Na verdade, o link deve ser clicado.**
* Atualizações do SO: **Novas atualizações do sistema operacional (iOS e Android) podem introduzir bugs inesperados que dificultam o deep linking.**
* **Dispositivos:** Diferentes smartphones, tablets, laptops e outros dispositivos que executam versões diferentes do iOS, Android, Windows Mobile e outros sistemas operacionais podem variar muito na forma como lidam com links de atribuição.
* Configuração incorreta: **O uso de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">caracteres especiais</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">no valor do deep linking quebra o link.</Anchor>**

Duas soluções para melhorar a experiência do usuário são URLs de fallback e deep linking forçado.

<div id="fallback-urls" />

#### URLs de fallback

URLs de fallback enviam usuários para páginas da web especificadas se a abertura do aplicativo ou o deep linking falhar por qualquer motivo. **Atenção!** Elas também enviam usuários sem o aplicativo instalado para a URL de fallback em vez de para a app store correta. Portanto, não se esqueça de usar essa opção somente se você estiver fazendo o retargeting de usuários com seu aplicativo já instalado.

Para implementar uma URL de fallback, no template do OneLink ou nas definições de links personalizado, defina o comportamento do link para quando o aplicativo não estiver instalado para redirecionar para uma URL diferente.

![different_url.png](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)

Essa configuração adiciona `af_ios_url` e `af_android_url` como parâmetros de destino para o fallback, o que fará com que os usuários do iOS sejam redirecionados para a página especificada por `af_ios_url` e os usuários do Android sejam redirecionados para a página especificada por `af_android_url`.

> 👍 **Tip**
>
> Considere, por exemplo, a seguinte URL do OneLink:
>
> Os usuários do iOS e do Android que clicarem neste link devem estar vinculados por deep linking ao aplicativo. No entanto, quando o deep linking falha, os usuários são redirecionados da seguinte forma:
>
> * iOS: www.seusite.com/ios-bonus
> * Android: www.seusite.com/android-bonus

> 📘 **Note**
>
> Quando o redirecionamento ocorre, os parâmetros da URL do OneLink passam para a página de destino especificada por af\_ios\_urlou af\_android\_url. Para evitar esse comportamento, adicione o parâmetro af\_param\_forwarding=false ao OneLink.

<div id="forced-deep-linking" />

#### Deep linking forçado

Forçar o deep linking permite que você use um esquema URI como um fallback para abrir o aplicativo e fazer um deep link dos usuários.

Essa solução funciona bem para usuários que têm o aplicativo instalado. No entanto, para iOS, usar um esquema de URI para abrir o aplicativo tem suas limitações, e talvez seja necessário adicionar `af_force_deeplink=true` a URL do OneLink para forçar o deep linking, fazendo com que ocorra a atividade especificada no esquema de URI (o `af_dp`). Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">fallback do esquema URI para iOS.</Anchor>

</Accordion>

<Accordion title="O OneLink oferece suporte a eventos do App Store Connect?">

sim, sim, Você pode usar um OneLink em eventos do App Store Connect. O redirecionamento, as aberturas do Aplicativo, as instalações e a atribuição de reengajamento funcionarão como esperado.

</Accordion>

<Accordion title="Por que minha URL do OneLink abre uma página em branco no Chrome?">

Certifique-se de que você não está usando uma tag HTML  que inclua o atributo `target`. Se a URL do OneLink for colocado dentro de uma tag  com o atributo `target="_blank"`, ele abrirá uma página em branco no Chrome (tanto no iOS quanto no Android), e o usuário não é redirecionado para a App Store ou para o Google Play.

</Accordion>

<Accordion title="Posso usar o OneLink para redirecionamento no Brave?">

Sim. No entanto, no Android, quando um usuário clica em um link OneLink em um navegador Brave, o deferred deep linking não funciona. No iOS, depois que o usuário clica, ele vê uma tela em branco, e o deferred deep linking só funciona se o usuário fizer algo na tela em branco, por exemplo, rolar, ou tocar.

</Accordion>

<Accordion title="Os links personalizados do OneLink levam mais tempo para carregar do que outros links?">

**Não.** Os links personalizados do OneLink não adicionam nenhum tempo de processamento ou de carregamento extra para funcionar corretamente e redirecionam os usuários conforme necessário. Eles são tão rápidos quanto qualquer outro link da AppsFlyer.

</Accordion>

<Accordion title="Como posso registrar o custo por instalação ao usar o OneLink?">

Ativar o **custo por instalação** (em **Parâmetros avançados**) permite aplicar um valor de CPI específico a cada instalação proveniente do link.

Selecione a moeda de custo e, em seguida, um **valor SOMENTE numérico** (com até 4 dígitos após o ponto decimal) representando o CPI. Isso adiciona os parâmetros af\_cost\_currency e af\_cost\_value ao link.

> 👍 **Tip**
>
> Uma campanha de SMS custa US$ 20 por 1.000 mensagens (CPM). A experiência mostrou que suas campanhas atingem uma taxa de conversão de 5%, o que significa que o CPI derivado é de US$0,40. Definir o custo por instalação para US$0,40 permite que você mensure o eventual ROI da campanha SMS.

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">mensurar o custo e o ROI</Anchor>.

</Accordion>

<Accordion title="Como posso evitar o encaminhamento de parâmetros em redirecionamentos?">

e `af_web_dp` transportam os parâmetros da ligação de atribuição ou do OneLink para a página redirecionada. Para evitar esse comportamento, adicione `af_param_forwarding=false` ao link de atribuição.

</Accordion>

<Accordion title="Como posso remover os parâmetros PID e C da AppsFlyer ao encaminhar enquanto mantenho todos os outros parâmetros em URLs de redirecionamento?">

Em alguns casos, você pode ter URLs com vários PIDs. Isso acontece porque a AppsFlyer adiciona parâmetros PID e C a uma URL de redirecionamento e o cliente também pode adicionar seus próprios parâmetros PID. Por exemplo, o "ID do produto" pode ser "pid" na URL do site do cliente.

Normalmente, adicionar `af_param_forwarding=false` ao link de atribuição remove todos os parâmetros.

No entanto, se o link for clicado em um desktop, o cliente pode querer que os parâmetros essenciais do CRM permaneçam. Para remover apenas os parâmetros PID e C da AppsFlyer e manter todos os outros parâmetros, adicione `af_base_params_forward=false` ao link de atribuição.

</Accordion>

<Accordion title="Os links personalizados de plataforma única ainda estão disponíveis?">

Não, os links personalizados de plataforma única não estão mais disponíveis.

</Accordion>

<Accordion title="Posso alterar o ID de URL curta depois de salvar um link?">

**Não,** o ID de URL curta só pode ser definido no momento em que o link é criado.

</Accordion>

<Accordion title="Posso encapsular e encurtar links personalizados do OneLink?">

**Encurtadores de links externos ou encapsulamento de links personalizados do OneLink quebrarão a funcionalidade de abertura de aplicativos de Universal Links e App Links.**

Para ativar Universal Links ou App Links, o SO precisa reconhecer o domínio da URL associada ao aplicativo, e qualquer tipo de encapsulamento, encurtamento ou redirecionamento para o link voltado para o usuário torna isso impossível. Isso inclui o uso de bit.ly, links de marca (branded links) que não são da AppsFlyer ou Provedores de Serviço de E-mail (ESPs) com gravação de cliques ativada.

**Para encapsular ou encurtar um link de forma que permita que o redirecionamento funcione corretamente:**

* Use as URLs curtas geradas pela AppsFlyer ao criar links personalizados do OneLink (em vez de encurtadores externos, como o bit.ly).  
  **Dica**! Torne a URL ainda mais curta criando um domínio curto de marca no seu link. E se você estiver criando os links na interface do usuário da AppsFlyer, poderá editar a ID da URL para ser a mais curta possível. Exemplo: https://marca.com/a1b2/a (em que **marca.com** é o domínio da sua marca, **a1b2** é o ID do modelo, que tem sempre 4 caracteres, e **a** é o ID da URL, que pode ter até 1 caractere editado.   
   Benefícios:
  * Esse método funciona porque usa o subdomínio do OneLink configurado no template do OneLink.
  * Isso permite que você altere os parâmetros rapidamente, incluindo quaisquer configurações de deep linking, mesmo depois de distribuir os links de atribuição para seus leads.
  * Isso conta todos os cliques de dispositivos mobile no dashboard da AppsFlyer, para que você não precise verificar outro serviço.
  * A última parte da URL curta pode ser personalizada para torná-la um <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">branded domain</Anchor>.
* Use o <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">esquema URI</Anchor> como um fallback para abrir o aplicativo quando links universais e App Links falharem, e adicione o seguinte parâmetro ao link: `af_force_deeplink=true`
* Veja as opções para [trabalhar com ESPs](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<Accordion title="Posso usar links personalizados do OneLink em e-mails?">

**Sim,** mas isso exige uma consideração especial quando você trabalha com Provedores de Serviços de E-mail (ESPs). **Sim**, mas requer consideração especial quando: para contar cliques realizados, os ESPs envolvem todos os links colocados dentro de e-mails. Isso quebra o fluxo de abertura/deep linking do aplicativo para usuários que clicam na URL.

Para evitar isso, use uma das seguintes soluções opcionais:

* Desative o registro de cliques na configuração do ESP.  
  **Dica: essa geralmente é a solução mais fácil.)**
* Force o aplicativo a abrir usando o esquema de URI especificado no parâmetro `af_dp` ao adicionar a flag `af_esp=true` ao link de atribuição. Essa solução funciona bem para usuários que têm o aplicativo instalado.
* Use ESPs compatíveis com a solução da AppsFlyer para a abertura de aplicativos e deep linking com links universais. <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">Saiba mais</Anchor>.

</Accordion>

<Accordion title="Como os usuários são redirecionados para a app store regional?">

O OneLink redireciona os usuários para a app store regional correta com base em seu endereço de IP.

</Accordion>

<Accordion title="Por que minha URL do OneLink não está redirecionando usuários para o domínio especificado?">

Verifique se você ativou as listas de permissões de redirecionamento na AppsFlyer. Se tiver ativado, o domínio ou subdomínio do web URL desejado deve ser adicionado à lista. <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">Saiba mais sobre listas de permissões de redirecionamento</Anchor>

</Accordion>

<Accordion title="Porque recebo o erro 'o aplicativo que você está procurando não está disponível'?">

O erro "o aplicativo que você está procurando não está disponível" pode surgir em vez do redirecionamento para o Google Play devido a:

* Seu aplicativo está atualmente no estado "Pendente" no Google Play. Para evitar a mensagem de erro acima mencionada, defina o redirecionamento do link para apontar para uma URL da web em vez do Google Play. Assim que o aplicativo for aprovado, o redirecionamento pode ser alterado para o Google Play. Estas alterações de configuração são feitas na <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">página do template do link</Anchor>.
* Se seu aplicativo estiver disponível exclusivamente através de uma loja de terceiros, o problema pode resultar do fato de lhe ter sido atribuído o estado incorreto do Google Play na AppsFlyer. Para resolver este problema, <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">é necessário definir seu estado no Google Play para Publicado fora da loja</Anchor> na página Definições Meus Aplicativos.

</Accordion>

<Accordion title="Por que meu link curto m.onelink.me não está funcionando?">

Em junho de 2024, a versão antiga do link curto **m.onelink.me** foi desativada. Os links que ainda usam esse subdomínio não redirecionam mais para o destino pretendido, potencialmente interrompendo a experiência planejada para o usuário.

</Accordion>

<Accordion title="Posso alternar manualmente entre o branded domain e o subdomínio do OneLink em um link?">

Sim - se o branded domain e o subdomínio OneLink estiverem mapeados corretamente. Veja: <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Configurar um Domínio de Marca na AppsFlyer</Anchor>

**Exemplo**:  
 Subdomínio do OneLink: demo.onelink.me  
 ID do template **A1r4**  
 Os domínios de marca mapeados para o subdomínio [**demo.onelink.me**](http://demo.onelink.me) são:

* **app.simulatorapp.com**
* **click.simulatorapp.com**

Você criou o seguinte link de marca na interface do usuário do OneLink:  
 **app.simulatorapp.com/A1r4/simulationlink**  
 Você pode substituir o link de marca acima pelo link de outro domínio de marca ou pelo link de subdomínio OneLink.  
Os links a seguir são funcionalmente idênticos e funcionam da mesma forma em todos os lugares:

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### Perguntas frequentes sobre o parâmetro do OneLink

<Accordion title="Quais parâmetros são obrigatórios para links personalizados do OneLink?">

Somente o parâmetro canal de mídia (**pid**) é obrigatório.

</Accordion>

<Accordion title="Os parâmetros podem ser anexados à URL curta?">

**Sim,** qualquer parâmetro pode ser anexado à URL curta.

**Importante!** Os parâmetros anexados à URL curta não substituem os parâmetros dentro do link.

> 👍 **Tip**
>
> * Você cria um link personalizado do OneLink com o seguinte output:
>   * URL longa: https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **URL curta:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * Você anexa os seguintes parâmetros à URL curta: https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * O parâmetro **af\_adset=fruits** anexado à URL curta é útil para atribuição. No entanto, o parâmetro **c=bananas** **não é útil**, uma vez que já existe um parâmetro **c** na URL longa.

</Accordion>

<Accordion title="Quais nomes de canais de mídia personalizados posso usar?">

Para mídias próprias, o nome do canal de mídia personalizado (valor PID) pode ser qualquer coisa, desde que não esteja reservado por um parceiro integrado. Para evitar um conflitos, não use o sufixo \_int (por exemplo, googleadwords\_int) para canais de mídia personalizados. Também não recomendamos que você use o termo *organic* como um nome de canal de mídia personalizado, pois isso poderia afetar a integridade dos dados de atribuição.

Se você estiver usando o OneLink para mídia paga:

* Use os valores de **PID** reservados por parceiros integrados (aqueles que terminam com **\_int**), como valores de canal de mídia em links personalizados do OneLink. Não use canais de mídia SRN como googleadwords *ou* *facebook* como nomes de canais de mídia personalizadas. Isso pode afetar a integridade dos dados de atribuição.
* Certifique-se de que o parceiro esteja ativo e integrado à AppsFlyer (o botão **Ativar parceiro** deve estar ativado) para todos os aplicativos configurados no template do OneLink.

</Accordion>

<Accordion title="Quais parâmetros de atribuição podem ser adicionados a um OneLink?">

Você pode adicionar vários parâmetros de atribuição para executar uma análise detalhada completa.

| **Parâmetro de atribuição** | **Descrição** | **Nome do link do parâmetro** |
| --- | --- | --- |
| **Campanha** | Configure nomes de campanha para comparar diferentes campanhas dentro do canal de mídia próprio | C |
| **Conjunto de anúncios** | Configure nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do canal de mídia própria | af\_adset |
| **Nome do anúncio** | Configure nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios/campanhas específicos do canal de mídia própria | af\_ad |
| **Canal** | Configure nomes de canais se quiser comparar mais de um canal de distribuição para sua mídia própria.<br /><br />Exemplo: se você dividir mensagens SMS entre dois provedores de serviços SMS, especifique o provedor usando o parâmetro de canal. Mais tarde, você pode comparar as taxas de conversão dos dois provedores. | af\_canal |
| **Parâmetros do assinante** | Use qualquer um dos 5 parâmetros de assinante disponíveis para inserir valores úteis para sua análise.<br /><br />**Observação:** Esses parâmetros são analisados e exibidos em relatórios de dados brutos, o que os torna úteis para realizar agregação ou filtragem de dados. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Parâmetros personalizados** | Semelhante aos parâmetros do assinante, você pode especificar campos com quaisquer nomes e valores de parâmetros. e quaisquer nomes.<br /><br />Ao contrário dos parâmetros do assinante, os parâmetros personalizados não são analisados em dados brutos. Eles aparecem em relatórios de dados brutos somente na coluna **url original**. | Personalizado  <br />(conforme especificado) |

Veja mais informações sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">estrutura e os parâmetros do link de atribuição da AppsFlyer</Anchor>.

</Accordion>

<Accordion title="Os parâmetros personalizados são adicionados aos links personalizados do OneLink disponíveis nos dados brutos?">

**Sim.** Os parâmetros personalizados são passados para a coluna **url original** em dados brutos e podem ser vistos lá. Eles não têm suas próprias colunas em dados brutos.

Para dados analisados, use parâmetros de assinante `af_sub1-5`, cada um deles tem uma coluna separada em relatórios de dados brutos.

</Accordion>

<Accordion title="Os nomes de parâmetros diferenciam maiúsculas de minúsculas?">

**Sim.** Certifique-se de usar apenas letras minúsculas para seus parâmetros e valores. Letras maiúsculas ou maiúsculas inconsistentes em nomes e valores de parâmetros podem causar erros ou discrepâncias de dados, tanto no dashboard quanto em dados brutos.

</Accordion>

<div id="integrated-partner-faq" />

### Perguntas frequentes sobre parceiros integrados

<Accordion title="Posso usar o OneLink em aplicativos sociais (não pagos)?">

Talvez você queira usar o OneLink em publicações não pagas em aplicativos sociais, já que usuários em potencial que estão expostos a esses posts não podem ser direcionados antecipadamente de acordo com seus dispositivos.

Infelizmente, as limitações e restrições dos Universal Links do iOS configuradas por alguns aplicativos sociais complicam o uso do OneLink para o reconhecimento básico de dispositivos, redirecionamento e atribuição de dispositivos e deep linking. Em certos casos, pode ser necessário configurar uma social app landing page ou um esquema URI para redirecionar ou fazer o deep link de usuários.

A tabela a seguir resume quando o OneLink pode ser usado nos aplicativos sociais mais populares:

<table><tbody><tr><td>Aplicativo social</td><td>Usuários do Android sem o aplicativo instalado</td><td>Deep linking do Android</td><td>Usuários do iOS sem aplicativo instalado</td><td>Deep linking do iOS</td></tr><tr><td> <strong>Facebook</strong>(incluindo publicações impulsionadas)</td><td><span>✓\*\*†† </span></td><td><span>✓\*\*††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*†† </span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓†† </span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓†† </span></td><td><span>✓††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X (antigo Twitter)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓† </span></td><td><span>✓† </span></td><td><span>✓\*</span></td><td><span>✓\*† </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* Nos casos de <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">esquema URI</a> ou da configuração de uma <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">social app landing page</a>. <strong>Observação:</strong> Para o Facebook e o Facebook Messenger, se o esquema URI e a social app landing page estiverem configurados, a social app landing page não será exibida.</p><p>\*\* Deve ter um esquema URI.</p><p>^ Deve ter uma landing page do aplicativo social com Universal Links configurados.</p><p><span>†</span> O usuário pode ser incentivado a abrir o link em um navegador externo.</p><p><span>†† Limitação de redirecionamento de deep linking de WebView para apps de redes sociais no Android. Mais detalhes </span><a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>aqui</span></a><span>.</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="Posso usar o OneLink com ad networks (pagas)?">

**Sim,** mas lembre-se que o OneLink é usado principalmente com mídias próprias, não com ad networks. Isso se deve ao fato de que as ad networks geralmente anunciam em aplicativos (o que significa que eles conhecem a plataforma do usuário, o ID do dispositivo, etc.), links de atribuição específicos de aplicativos e plataformas bastam - por isso, usar o OneLink não é necessário. No entanto, para casos em que as ad networks não conhecem a plataforma do usuário com antecedência (por exemplo, quando executam campanhas de e-mail ou SMS), o OneLink pode ser a solução.

> 🚧 **Important**
>
> Ao usar o OneLink com ad networks, você deve usar a URL longa do OneLink.

**Para configurar o OneLink para ad networks parceiras:**

* Siga as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">instruções do link de atribuição ae ad network</Anchor> e selecione **Usar OneLink** quando solicitado.

Depois que todos os parâmetros para Android e iOS forem adicionados corretamente, quando o link personalizado do OneLink é clicado e o usuário é redirecionado para a plataforma correta, os parâmetros necessários são enviados para a ad network dentro de um postback após a instalação do usuário.

> 👍 **Tip**
>
> A ad network usa os parâmetros IDFA ou GAID de acordo com a plataforma do dispositivo do cliente e desconsidera o outro parâmetro.

</Accordion>

<Accordion title="Como posso resolver o problema de abertura do aplicativo iOS a partir de aplicativos de redes sociais?">

O Facebook e outros aplicativos de redes sociais às vezes impedem os Universal Links de abrir aplicativos. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">As social app landing pages</Anchor> são a solução recomendada para esse tipo de problema./span>

Se você não deseja usar social app landing pages, você pode usar esquemas URI como um método de fallback. Porém, atenção:

* O uso de esquemas URI como fallback está sujeito a limitações baseadas do iOS.
* Para muitos navegadores, incluindo o Safari, você deve adicionar o parâmetro `af_force_deeplink=true` à URL para usar esquemas URI como fallback. <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">Saiba mais</Anchor>.
* O X (antigo Twitter) não oferece suporte a esquemas de URI. Uma página de destino de Aplicativo social deve ser usada para evitar problemas ao abrir o Aplicativo.

</Accordion>

<Accordion title="Posso usar o OneLink no Instagram?">

**Sim,** mas esteja ciente das seguintes limitações:

* Devido à forma como o Instagram renderiza o texto de uma publicação de página, os links não podem ser clicados quando inseridos na legenda da publicação.
* A abertura de aplicativos e o deep linking em aplicativos Android são compatíveis sem quaisquer considerações especiais. No entanto, o Instagram não é compatível com a abertura de aplicativos e o deep linking para aplicativos iOS. Para resolver esse problema, você pode seguir uma das seguintes abordagens:
  * **Recomendado:** Configure uma <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">social app landing page</Anchor>. Os templates Clustered Poster e ShowAndTell funcionam melhor. Além da landing page social, recomendamos configurar um esquema URI no seu template do OneLink.
  * Use um esquema URI e o [deep linking forçado](/docs/onelink-troubleshooting-and-faq#deep-linking-forçado) ao usar o OneLink no Instagram. Certifique-se de seguir as seguintes considerações ao usar `af_force_deeplink=true` com o OneLink no Instagram:

| Aplicativo instalado? | O clique tem af\_force\_deeplink=true? | Resultado |
| --- | --- | --- |
| Não | Yes | O clique abre a app store |
| Não | Não | O clique abre a app store |
| Sim | Sim | O clique abre o aplicativo |
| Sim | Não | O clique abre a app store |

</Accordion>

<Accordion title="Posso usar o OneLink no X (antigo Twitter)?">

sim, sim, Você pode usar o OneLink no X, mas é altamente **recomendado configurá-lo com uma página de destino de Aplicativo social (SALP) e links Universal.**

O motivo é que o navegador in-app do X no iOS bloqueia o redirecionamento para a loja de aplicativos e a abertura do Aplicativo por esquema de URI; portanto, configurações do OneLink definidas apenas com esquema de URI não abrirão o Aplicativo para usuários existentes. Usar a SALP com links Universal garante que os usuários sejam direcionados corretamente — abrindo o Aplicativo quando ele estiver instalado ou enviando novos usuários para a loja de aplicativos quando necessário.

</Accordion>

<Accordion title="Posso usar o OneLink para redirecionamento no WeChat?">

O WeChat substitui deep links do Android e iOS e redireciona os usuários para uma página da web. Na página da web, o usuário deve clicar no botão **Opções** e escolher abrir a página em um navegador. Como consequência, os usuários têm uma experiência interrompida, aumentando a chance de evasão no funil de conversão.

Para superar isso, o OneLink reconhece cliques no WeChat e carrega uma landing page dedicada instruindo o usuário a clicar no botão de opções e clicar em **Abrir no navegador.** Isso, por sua vez, abre a URL de redirecionamento definida na configuração do template do OneLink.

![WeChat_a.jpg](https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg)

Se o idioma do WeChat do usuário estiver cadastrado como Chinês, o OneLink gera uma versão localizada da landing page:

![WeChat_b.jpg](https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg)

</Accordion>

<Accordion title="Por que os usuários do Android com o aplicativo instalado estão sendo redirecionados para uma web URL e não para o aplicativo quando clicam em um link na visualização da web do Facebook?">

Normalmente, é possível abrir o aplicativo e estabelecer deep linking a partir de um anúncio no Facebook. No entanto, se as seguintes condições se aplicarem, o Facebook não poderá abrir o aplicativo para usuários de aplicativos existentes a partir da URL do OneLink. Em vez disso, todos os usuários, incluindo os que têm o aplicativo, são enviados para a URL definida no template do OneLink ou no valor do parâmetro af\_android\_url/span>, af\_r,**ou** af\_custom\_android\_url:

* O usuário tem um dispositivo mobile Android.
* O link é clicado no aplicativo do Facebook.
* O link leva a uma página HTML que é aberta na visualização web do Facebook (uma página inicial de um site ou aplicativo social).
* A página HTML contém um link com um parâmetro **af\_dp** (com um esquema URI) e uma configuração de redirecionamento de URL no template do OneLink ou em um parâmetro (um entre os seguintes: **af\_android\_url**, **af\_r** ou **af\_custom\_android\_url**).

</Accordion>

<Accordion title="Por que clicar no vídeo em uma campanha paga de anúncios web da Meta resulta em uma página em branco no iOS?">

Quando um link personalizado do OneLink é incorporado por trás do vídeo em uma campanha paga de anúncios web da Meta, clicar no vídeo no iOS no aplicativo do Facebook exige uma página de destino de aplicativo social (SALP) para redirecionar o usuário para a App Store. Se nenhuma SALP estiver configurada, clicar no vídeo resultará em uma página em branco.

</Accordion>

<div id="testing-faq" />

### Perguntas frequentes sobre testes

<Accordion title="Como posso fazer um teste A/B na landing page do aplicativo social?">

A <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">social app página inicial</Anchor> oferece aos usuários uma experiência de inicialização sem interrupção ao usar o OneLink em apps de redes sociais. Você pode estar preocupado com o fato de que adicionar uma etapa ao funil diminui as taxas de conversão. Mas a verdade é que, sem a landing page, as jornadas dos usuários geralmente são interrompidas, resultando em taxas de conversão muito baixas.

Se você não está totalmente convencido, por que não testar?

<Anchor target="_blank" href="/marketers/pt/docs/create-a-b-tests">Faça um teste A/B</Anchor> no seu link personalizado em aplicativos de rede social, com e sem a social app landing page.

**Para fazer um teste A/B na social app landing page:**

1. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Crie um link do OneLink</Anchor> (chamado Link1) para usar com apps de redes sociais. Não configure a social app landing page para esse link.
2. Adicione o parâmetro de atribuição **af\_adset**.
3. Adicione o parâmetro de atribuição **af\_ad** com o valor "no lp".
4. Teste o Link1 fora dos aplicativos de redes sociais e verifique se o link funciona e inicia seu aplicativo corretamente.
5. Duplique o Link1 e chame-o de Link2.
6. Altere o valor do parâmetro de atribuição **af\_ad** para "using lp".
7. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Crie a social app landing page</Anchor> apenas para Link2.
8. Publique 2 posts diferentes no **mesmo** aplicativo de rede social, usando Link1 e Link2.  
   Não se preocupe com o número diferente de cliques que cada link gera. O KPI importante é a taxa de conversão final de cada link.
9. **Verifique os resultados do teste A/B após a criação de tráfego suficiente.**
   1. Acesse o dashboard de visão geral da AppsFlyer e role para baixo até a tabela **Relatório de performance agregada**.
   2. Link1 e Link2 têm o mesmo canal de mídia, campanha e nome do conjunto de anúncios. Detalhe o conjunto de anúncios específico.
   3. Compare as taxas de conversão (e outros KPIs) de usuários que clicaram no Link1 ou no Link2.

</Accordion>

<Accordion title="Como posso ignorar a caixa de diálogo de seleção de aplicativos?">

Se você vir uma caixa de diálogo de seleção de aplicativos ao testar seu OneLink, certifique-se de <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">assinar seu aplicativo</Anchor>, mesmo que seja um <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">aplicativo de depuração.</Anchor> O certificado que você usa para assinar o aplicativo é o mesmo certificado que você usa para <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">gerar a impressão digital SHA256</Anchor> ao configurar o OneLink para App Links.

</Accordion>

<div id="deep-linking-faq" />

### Perguntas frequentes sobre deep linking

<Accordion title="Quais métodos de deep linking devem ser implementados?">

Seus desenvolvedores devem implementar o método Unified Deep Linking (UDL) para deep linking. Veja nossas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instruções completas para deep linking</Anchor>.

Universal Links para iOS e Android App Links são **métodos de abertura de aplicativos, que na verdade não fazem o deep linking de usuários** (enviando-os para um conteúdo específico dentro do aplicativo). O método de esquema URI pode iniciar o aplicativo e fazer o deep linking de usuários (por meio do parâmetro de link personalizado **af\_dp**), mas ele só deve ser configurado para a abertura do aplicativo. Seu principal uso é como um método de fallback para Universal Links, App Links e para novos usuários com versões do sistema operacional Android anteriores a 6.0.

Depois que o aplicativo é iniciado usando qualquer um desses métodos, o SDK da AppsFlyer fornece o **deep\_link\_value** especificado no link de atribuição personalizado. Esse valor deve ser entregue por meio do método UDL implementado por seus desenvolvedores.

</Accordion>

<Accordion title="Um esquema URI (parâmetro af_dp) pode ser usado para deep linking?">

**Sim, mas não é recomendado.** Idealmente, você deve usar o **deep\_link\_value** para deep linking e o esquema URI como um método de fallback para iniciar o aplicativo sem deep linking (por meio do parâmetro **af\_dp**). No entanto, se você já tiver o esquema URI configurado para deep linking, com parâmetros adicionais concatenados como parte do caminho da URI (por exemplo, greatapp: //param1/param2), não há necessidade de alterar sua configuração ou código existente; o esquema URI continuará funcionando.

**A prática recomendada para adicionar parâmetros personalizados é por meio da página de configuração de links personalizados**.

</Accordion>

<div id="ios-14-faq" />

### Perguntas frequentes sobre o iOS 14

<Accordion title="O deep linking do OneLink funciona para iOS 14?">

Aa experiência do usuário não é afetada para os usuários do iOS 14 que são vinculados por deep link a partir de campanhas em ad networks e mídia própria usando o método UDL. O método legado pode impedir o deep linking.

Para fins de atribuição/emissão de relatórios, a AppsFlyer usa IDFA ou IDFV quando disponível. Se não houver IDFA ou IDFV, a modelagem probabilística pode ser usada. A partir do iOS 14.5+, a modelagem probabilística é limitada ao contexto de mídia própria, promoção cruzada e fluxos consentidos do usuário web-to-app.

</Accordion>

<Accordion title="O deferred deep linking do OneLink funciona para o iOS 14?">

A experiência do usuário não é afetada para os usuários do iOS 14 que são enviados através de deferred deep link de campanhas em ad networks e mídia própria usando o método UDL. O método legado pode impedir o deferred deep linking.

Para fins de atribuição/emissão de relatórios, a AppsFlyer usa IDFA ou IDFV quando disponível. Se não houver IDFA ou IDFV, a modelagem probabilística pode ser usada. A partir do iOS 14.5+, a modelagem probabilística é limitada ao contexto de mídia própria, promoção cruzada e fluxos consentidos do usuário web-to-app. Aconselhamos os clientes que desejam implementar deferred deep linking de ad networks e mídias próprias a usar o SDK para iOS V6.1.0+ da AppsFlyer para permitir o consentimento da ATT (se necessário), eliminar qualquer impacto na atribuição e se beneficiar de tempos de resposta mais rápidos.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=guia-de-solu%C3%A7%C3%A3o-de-problemas-do-onelink 01H7WPYJV9CQ1J6J3PFCEQFGB0=guia-de-solu%C3%A7%C3%A3o-de-problemas-do-onelink onelink-frequently-asked-questions=perguntas-frequentes-sobre-o-onelink 01H7WPYJV9H52P659N8JPRX2TY=perguntas-frequentes-sobre-o-onelink onelink-template-faq=perguntas-frequentes-sobre-o-template-do-onelink 01H7WPYJV9TJRKHFZ77DFMKDDG=perguntas-frequentes-sobre-o-template-do-onelink 01H7WPYJV9JSQ5FV73YCE3H5AF=deep-linking onelink-link-faq=perguntas-frequentes-do-link-onelink 01H7WPYJVAPNYAQ1SH4FBX4Z9F=perguntas-frequentes-do-link-onelink fallback-urls=urls-de-fallback 01H7WPYJVACCGVJD1Z7ZPVG2SQ=urls-de-fallback forced-deep-linking=deep-linking-for%C3%A7ado 01H7WPYJVA1W3HYYJJFQM01136=deep-linking-for%C3%A7ado onelink-parameter-faq=perguntas-frequentes-sobre-o-par%C3%A2metro-do-onelink 01H7WPYJVAGRVWHRVMZVQG1ZVE=perguntas-frequentes-sobre-o-par%C3%A2metro-do-onelink integrated-partner-faq=perguntas-frequentes-sobre-parceiros-integrados 01H7WPYJVB8ZZSKFT1V01EN6QF=perguntas-frequentes-sobre-parceiros-integrados testing-faq=perguntas-frequentes-sobre-testes 01H7WPYJVC1PJJDA0GGT1DVVCF=perguntas-frequentes-sobre-testes deep-linking-faq=perguntas-frequentes-sobre-deep-linking 01H7WPYJVCTM39HKCG9JN03BN6=perguntas-frequentes-sobre-deep-linking ios-14-faq=perguntas-frequentes-sobre-o-ios-14 01H7WPYJVCVCVWHJW4RH85KC40=perguntas-frequentes-sobre-o-ios-14" />
