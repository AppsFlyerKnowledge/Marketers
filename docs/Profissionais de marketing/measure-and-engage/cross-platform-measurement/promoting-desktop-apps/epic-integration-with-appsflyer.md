---
title: Integração da Epic com a AppsFlyer
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
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-08-18T00:23:01Z'
  id: 14241298075921
  locale: pt
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/pt/articles/14241298075921
---
> **Visão geral:** Integre seu jogo da Epic com a AppsFlyer para receber dados de atribuição e de eventos para suas campanhas da Epic. A integração com a Epic oferece suporte à atribuição e ao registro de eventos in-app para jogos da Epic (em outras palavras, atribuição e registro no dispositivo do usuário).

## Sobre a atribuição de jogos da Epic

Os jogos em execução na Epic podem se integrar à AppsFlyer via API (tanto S2S quanto client-side) para receber dados de atribuição e mensuração de performance sobre quais fontes e campanhas impulsionam a abertura do aplicativo e eventos in-app. Os profissionais de marketing baseiam-se nestas informações para medir e otimizar as atividades de marketing.

### Exemplo de fluxo de atribuição

A seguir está um exemplo de fluxo que destaca as etapas mais importantes na jornada do usuário, do engajamento do anúncio à atribuição. Inclui a página de destino multiplataforma recomendada pela AppsFlyer. **Observação**: Embora recomendemos usar a página de destino multiplataforma, você também pode usar links de atribuição direta.

![Epic_journey.jpg](https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg)

1. Ponto de contato de marketing: Os clientes interagem com sua marca por meio de pontos de contato de marketing online ou offline. Isso pode incluir e-mails e boletins informativos, mídias sociais, web móvel e muito mais.
2. Página inicial do jogo:  Uma página inicial de jogo direciona os clientes para a página do seu jogo na Epic. Esta etapa é importante para coletar UTM e outros parâmetros de URL para atribuir clientes do clique/instalação às fontes de mídia originais ou às suas próprias fontes de mídia.  
   A página de destino também é útil porque fornece links para as diversas plataformas compatíveis com seu jogo. Por exemplo, você pode ter links para sua página do Xbox, da Microsoft Store e do Steam na sua página inicial.
3. Página do aplicativo da Epic: Esta é a página da vitrine da Epic que hospeda seu jogo da Epic para os clientes fazerem download.
4. Instalação do jogo: O usuário instala o jogo, acionando a atribuição e o registro de eventos in-app e sessões.

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar seu jogo da Epic à AppsFlyer.∑

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
        * <Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor>
        * <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu jogo da Epic na AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        Integração da API com o seu aplicativo (via S2S ou client-side)
      </td>
      <td>
        Há dois métodos de integração que você pode usar: S2S e client-side.

        Para o método S2S:

        <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">Integre a API Epic da AppsFlyer</Anchor> ao seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.

        * Primeira abertura do app
        * https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg
        * Sessions

        **Observação**:

        * A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.
        * Para o parâmetro `device_ids`, selecione o tipo `personalizado` ou `epicid`.
          * O `custom` ou `epicid` para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder aos seus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e ao ID das <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessões</Anchor> .
        * Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados.
        * Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>

        Para o método client-side, há três versões: <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">C++</Anchor> nativo, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app">Unreal</Anchor> e <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app">Unity</Anchor>.

        **Observação**:

        Se você tiver uma base de usuários existente e quiser que a primeira sessão seja considerada uma sessão e não uma instalação, o desenvolvedor pode usar o método `skipFirst=true`.
      </td>
      <td>
        Desenvolvedor do aplicativo
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

        Para a Epic, os seguintes parâmetros são necessários:

        * **plataforma**  
          epic
        * **app\_id**  
          O ID do aplicativo da página do jogo na loja da Epic.

          Você pode encontrar o ID exclusivo do seu jogo no console de desenvolvedores da Epic. Exemplo:

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **fonte\_de\_mídia**

        Os seguintes parâmetros não são obrigatórios, mas são recomendados:

        * **Twitter**
        * **Anúncio**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          A URL completa da vitrine da Epic para seu aplicativo, incluindo seu **app\_id**.  
          Por exemplo, `https://store.epicgames.com/en-us/p/12345678/`.
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
        Profissional de marketing/Engenheiro de dados
      </td>
    </tr>
  </tbody>
</Table>

### Removendo dados do AppsFlyer ao desinstalar o aplicativo

Para remover todos os dados do AppsFlyer SDK ao desinstalar o aplicativo, peça ao seu desenvolvedor para executar as etapas especificadas [aqui](https://dev.appsflyer.com/hc/docs/epic-vanilla#deleting-appsflyer-data-on-uninstall).

## Especificações e limitações

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente não compatível |
| Dados de custos | Os dados de custo devem ser enviados por meio do <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Ad Spend Ingestion</Anchor> usando o método de upload de arquivo por e-mail. |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral das plataformas CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-steam-attribution=sobre-a-atribui%C3%A7%C3%A3o-de-jogos-da-epic 01H7Z1F3SE03BXJD0WAJV8RE7Q=sobre-a-atribui%C3%A7%C3%A3o-de-jogos-da-epic flow=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o 01H7Z1F3SETVXQKRQ71YAJACY3=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=procedimentos-de-integra%C3%A7%C3%A3o removing-appsflyer-data-when-uninstalling-the-app=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo h_01J3349MAA4J231B6FJ74V3PTB=removendo-dados-do-appsflyer-ao-desinstalar-o-aplicativo traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HF9WA5FJ6P4C357ZE231GMR0=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HE7T4JX3RX3SZW2VPW5ZZY7E=consulte-tamb%C3%A9m" />
