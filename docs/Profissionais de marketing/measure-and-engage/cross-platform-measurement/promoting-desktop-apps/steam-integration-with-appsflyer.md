---
title: Integração do Steam com AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-06T00:11:51Z'
  id: 11241130508433
  locale: pt
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/pt/articles/11241130508433
---
> Visão geral: **Integre seu game/aplicativo Steam com a AppsFlyer para receber dados de atribuição e de eventos para suas campanhas no Steam. A integração com o Steam é compatível com a atribuição e à gravação de eventos in-app para aplicativos Steam no dispositivo Steam de um usuário.**

## Sobre a atribuição do Steam

O Steam é executado em dispositivos Windows e Mac, Steam Deck e outros dispositivos Steam OS.

Os aplicativos executados no Steam podem se integrar à AppsFlyer por meio da S2S API ou SDK para receber dados de atribuição e mensuração de performance, que oferecem um insight sobre quais fontes e campanhas impulsionam aberturas do app e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

### Exemplo de fluxo de atribuição

A seguir está um exemplo de fluxo que destaca as etapas mais importantes na jornada do usuário, do engajamento do anúncio à atribuição. Inclui a página de destino multiplataforma recomendada pela AppsFlyer. **Observação**: Embora recomendemos usar a página de destino multiplataforma, você também pode usar links de atribuição direta

![Steam_user_journey.jpg](https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg)

1. Ponto de contato de marketing: Os clientes interagem com sua marca por meio de pontos de contato de marketing online ou offline. Isso pode incluir e-mails e boletins informativos, mídias sociais, web móvel e muito mais.
2. Página inicial do jogo: Uma página inicial de jogo direciona os clientes para a página do seu jogo no Steam. Esta etapa é importante para coletar UTM e outros parâmetros de URL para atribuir clientes do clique/instalação às fontes de mídia originais ou às suas próprias fontes de mídia.  
   A página de destino também é útil porque fornece links para as diversas plataformas compatíveis com seu jogo. Por exemplo, você pode ter links para sua página do Xbox, da Microsoft Store e do Steam na sua página inicial.  
   ![awesome_game.png](https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png)
3. <span id="marketing-touchpoint"></span>Página do aplicativo Steam: Esta é a página da sua loja Steam que hospeda seu aplicativo Steam para os clientes baixarem.
4. Instalação do jogo: O usuário instala o jogo, acionando a atribuição e a gravação de eventos e sessões no aplicativo.

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar um aplicativo do Steam na AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Função
      </th>
      <th>
        Ações
      </th>
      <th>
        Quem está envolvido
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuração do aplicativo
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta</Anchor>
        * <Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários de conta com as permissões adequadas</Anchor>
        * <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu aplicativo Steam ao AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        Integração da API com o seu app (via S2S ou SDK)
      </td>
      <td>
        Existem dois métodos de integração que podem ser utilizados: S2S e SDK.

        Para o método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">integre a API da AppsFlyer</Anchor> ao seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.

        * Primeira abertura do app
        * https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg
        * Sessions

        Observação:

        * A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.
        * Para o parâmetro `platform`, selecione `steam`.
        * Para o parâmetro `device_ids`, selecionar o tipo `custom`.
          * O ID `custom` gerado para as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder aos seus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e ao ID <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">das sessões</Anchor>.
        * Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.
        * Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>

        Para o método SDK, há três versões: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor> nativo, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreale</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

        **Observação**:

        Se você tiver uma base de usuários existente e quiser que a primeira sessão seja considerada uma sessão e não uma instalação, o desenvolvedor pode usar o método `skipFirst=true`.
      </td>
      <td>
        Desenvolvedor de aplicativos
      </td>
    </tr>
    <tr>
      <td>
        Configurar uma landing page multiplataforma
      </td>
      <td>
        **Recomendado**: Uma página inicial multiplataforma que executa o Smart Script da AppsFlyer permite que você faça a atribuição web-to-app. Recomendado em casos em que a sua campanha promove um app disponível em diversas plataformas, como na Epic e Native PC.

        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor>

        <Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor>

        **Observação**:

        Para o Steam, os seguintes parâmetros são necessários:

        * **plataforma**: steam
        * **steam\_app\_id**: O ID da página do aplicativo.

          Você pode encontrar seu ID exclusivo do aplicativo copiando-o da barra de URL ou acessando <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor> e pesquisando seu jogo. Por exemplo:

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          onde **12345678** é o seu ID exclusivo do aplicativo.
        * **fonte\_de\_mídia**

        Os seguintes parâmetros não são obrigatórios, mas são recomendados:

        * **Carga útil**
        * **anúncio**
        * **ad\_set**
        * **storefront\_redirect\_url**: A URL completa da loja Steam para seu aplicativo, incluindo seu **steam\_app\_id**. Por exemplo, `https://store.steampowered.com/app/12345678/`.
      </td>
      <td>
        `{1>Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) <1}`
      </td>
    </tr>
    <tr>
      <td>
        Configuração do OneLink
      </td>
      <td>
        Se você não usa uma página inicial multiplataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.

        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        Configuração de relatórios/visualização de dados
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em painéis e relatórios</Anchor>
      </td>
      <td>
        Técnico de marketing/engenheiro de dados
      </td>
    </tr>
  </tbody>
</Table>

### Removendo dados do AppsFlyer ao desinstalar o aplicativo

Para remover todos os dados do AppsFlyer SDK ao desinstalar o aplicativo, peça ao seu desenvolvedor para executar as etapas especificadas [aqui](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall).

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Categoria do dispositivo (por exemplo, MOBILE\_PHONE, TV) | Atualmente não compatível |
| Dados de custos | Importe dados de custo via <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> usando o método de upload de arquivo **por e-mail**. Você também pode coletar dados **via API** para Google, Meta ou TikTok. |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Atribuição de plataformas de CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-steam-attribution=sobre-a-atribui%C3%A7%C3%A3o-do-steam 01H7Z1DJRW1KPJQ4CZ6T85ASRK=sobre-a-atribui%C3%A7%C3%A3o-do-steam flow=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o 01H7Z1DJRWHB8TQC15WW4FVSHG=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z1DJRWX54DN2SNS21GPGXB=procedimentos-de-integra%C3%A7%C3%A3o removing-appsflyer-data-when-uninstalling-the-app=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo h_01J3349MAA4J231B6FJ74V3PTB=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HDEHMH0HF201TH4XDW691STH=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HDP1K6FDDEED5P2WNESST7GE=veja-tamb%C3%A9m" />
