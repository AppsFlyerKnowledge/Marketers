---
title: Integração de PC nativo com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2026-10-06T00:11:48Z'
  id: 16308237781649
  locale: pt
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/pt/articles/16308237781649
---
> **Visão geral:** Integre seu jogo ou aplicativo para PC com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas para PC. A integração de PC nativo é compatível com a atribuiçãoe a gravação de eventos in-app para aplicativos de PC (ou seja, atribuição e gravação no PC de um usuário).

## Sobre a atribuição de PC nativo

O PC nativo é executado em dispositivos Windows, através da instalação de uma extensão de arquivo .EXE ou .MSI.

Isso é diferente do <Anchor target="_blank" href="/marketers/pt/docs/windows-sdk-integration-for-developers">SDK 2.4.1 para Windows da AppsFlyer</Anchor>, que funciona com instalações da Microsoft App Store, telefones Windows e UWP.

Os aplicativos executados no PC podem se integrar à AppsFlyer por meio da S2S API ou SDK para receber dados de atribuição e mensuração de performance, que oferecem um insight sobre quais fontes e campanhas impulsionam aberturas do app e eventos in-app. Os profissionais de marketing baseiam-se nestas informações para medir e otimizar as atividades de marketing.

### Exemplo de link de atribuição

A seguir está um exemplo de fluxo que destaca as etapas mais importantes na jornada do usuário, do engajamento do anúncio à atribuição. Ele Inclui a página de destino multiplataforma recomendada pela AppsFlyer. **Observação**: Embora recomendemos usar a página de destino multiplataforma, você também pode usar links de atribuição direta

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Ponto de contato de marketing: Os clientes interagem com sua marca por meio de pontos de contato de marketing online ou offline. Eles podem incluir email e newsletters, redes sociais, web mobile e muito mais.
2. Página inicial do jogo: Uma página inicial de um jogo direciona os clientes para a página de download do aplicativo. Esta etapa é importante para coletar UTM e outros parâmetros de URL para atribuir clientes do clique/instalação às fontes de mídia originais ou às suas próprias fontes de mídia.  
   A página de destino também é útil porque fornece links para as diversas plataformas compatíveis com seu jogo. Por exemplo, você pode ter links para sua página do Xbox, da Microsoft Store e do Steam na sua página inicial.
3. Página do aplicativo: Este é o URL da página do aplicativo do PC nativo que hospeda seu aplicativo para os clientes fazer download.
4. Instalação do jogo: O usuário instala o jogo, acionando a atribuição e a gravação de eventos e sessões no aplicativo.

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar seu aplicativo do PC na AppsFlyer.

**Observação**: A adição de membros da equipe e a criação de relatórios no Data Locker não são obrigatórias.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários de conta com as permissões adequadas</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app do PC na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S ou SDK) | Existem dois métodos de integração que podem ser utilizados: S2S e SDK.<br /><br />Para o método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integre a API da AppsFlyer</Anchor> ao seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.<ul><li>Primeira abertura do app</li><li>https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg</li><li>Sessions</li></ul>Observação:<ul><li>A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.</li><li>Para o parâmetro `device_ids`, selecione o tipo `custom`.<ul><li>O ID `custom` gerado para as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder aos seus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e ao ID <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">das sessões</Anchor>.</li></ul></li><li>Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li><li>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor></li></ul>Para o método SDK, há três versões: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor> nativo, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreale</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**Observação**:<br /><br />Se você tiver uma base de usuários existente e quiser que a primeira sessão seja considerada uma sessão e não uma instalação, o desenvolvedor pode usar o método `skipFirst=true`. | Desenvolvedor de aplicativos |
| Configurar uma landing page multiplataforma | **Recomendado**: Uma página inicial multiplataforma que executa o Smart Script da AppsFlyer permite que você faça a atribuição web-to-app. Recomendado em casos em que a sua campanha promove um app disponível em diversas plataformas, como na Epic e Native PC.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor><br /><br /><Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor><br /><br />Para o PC nativo, os seguintes parâmetros são necessários:<ul><li>**Nome da aplicação**</li><li>**app\_id**<br />É necessário um App ID para a AppsFlyer usar. Os aplicativos nativos para PC não têm regras específicas de ID do aplicativo, portanto seu desenvolvedor pode escolher e criar qualquer ID do aplicativo que quiser para o seu aplicativo. **Recomendado:** Escolha um ID que seja significativo para você, mas que seja pouco provável que seja usado por aplicativos. Por exemplo: `app-name-is-the-best`.</li><li>**media\_source**</li><li>**af\_campaign\_id**</li><li>**plataforma**<br />Exemplo: steam</li></ul>Os parâmetros seguintes não são obrigatórios mas são recomendados:<ul><li>**campanha**</li><li>**anúncio**</li><li>**ad\_set**</li></ul> | Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) |
| Configuração do link de atribuição direta | <ul><li>Se você não usa uma página inicial multiplataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.</li><li>Se você usar uma landing page multiplataforma, recomendamos também usar links de atribuição direta e colocá-los atrás dos botões dedicados à plataforma na landing page.</li><li><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor></li></ul> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Técnico de marketing/engenheiro de dados |

### Removendo dados do AppsFlyer ao desinstalar o aplicativo

Para remover todos os dados do AppsFlyer SDK ao desinstalar o aplicativo, peça ao seu desenvolvedor para executar as etapas especificadas [aqui](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall).

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente não compatível |
| Dados de custo | Importe dados de custo via <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> usando o método de upload de arquivos **por e-mail**. Você também pode extrair dados **via API** do Google, Meta ou TikTok. |

> 📄 **Veja também**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-steam-attribution=sobre-a-atribui%C3%A7%C3%A3o-de-pc-nativo 01H7Z19FJ5J1CB4ESE55Z32C1C=sobre-a-atribui%C3%A7%C3%A3o-de-pc-nativo flow=exemplo-de-link-de-atribui%C3%A7%C3%A3o 01H7Z19FJ5R869054GDRKHTBJ8=exemplo-de-link-de-atribui%C3%A7%C3%A3o 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z19FJ5KKPJ88KAQM49FNVA=procedimentos-de-integra%C3%A7%C3%A3o removing-appsflyer-data-when-uninstalling-the-app=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo h_01J3349MAA4J231B6FJ74V3PTB=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HF9W8YG149TMQE1F57BG0ZS7=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
