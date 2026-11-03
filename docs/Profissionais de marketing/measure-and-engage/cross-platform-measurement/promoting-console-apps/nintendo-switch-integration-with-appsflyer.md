---
title: Integração do Nintendo Switch com AppsFlyer
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
  created_at: '2023-05-02T10:50:43Z'
  edited_at: '2026-08-18T00:22:33Z'
  id: 14988397864593
  locale: pt
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/pt/articles/14988397864593
---
> **Visão geral:** Integre seu jogo ou aplicativo do Nintendo Switch com a AppsFlyer para receber dados de atribuição e de eventos para suas campanhas no Nintendo Switch.

## Sobre a atribuição no Nintendo Switch

Os aplicativos em execução no Nintendo Switch podem se integrar à AppsFlyer por meio da API S2S para receber dados de atribuição e mensuração de performance sobre quais fontes e campanhas impulsionam a abertura do aplicativo e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

### Exemplo de fluxo de atribuição

A seguir está um exemplo de fluxo que destaca as etapas mais importantes na jornada do usuário, do engajamento do anúncio à atribuição. Inclui a página de destino multiplataforma recomendada pela AppsFlyer. **Observação:** Embora recomendemos usar a página de destino multiplataforma, você também pode usar links de atribuição direta

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Ponto de contato de marketing: Os clientes interagem com sua marca por meio de pontos de contato de marketing online ou offline. Eles podem incluir email e newsletters, redes sociais, web mobile e muito mais.
2. Página inicial do jogo: Uma página inicial de um jogo direciona os clientes para a página de download do aplicativo. Esta etapa é importante para coletar UTM e outros parâmetros de URL para atribuir clientes do clique/instalação às fontes de mídia originais ou às suas próprias fontes de mídia.  
   A página inicial também é útil porque fornece links para as várias plataformas compatíveis com o jogo. Por exemplo, você pode ter links para sua página do Xbox, da Microsoft Store e do Steam na sua página inicial.
3. Página do aplicativo: Esta é a URL da página do seu aplicativo no Nintendo Switch, que hospeda seu aplicativo para os clientes fazerem o download.
4. Instalação do jogo: O usuário instala o jogo, acionando a atribuição e a gravação de eventos e sessões no aplicativo.

## Etapas de integração

A tabela abaixo lista as tarefas necessárias para integrar seu aplicativo do Nintendo Switch com a AppsFlyer.

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
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor>
        * <Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor>
        * <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu aplicativo do Nintendo Switch na AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        Integração da API com o seu app (via S2S)
      </td>
      <td>
        <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integre a API da AppsFlyer</Anchor> em seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.

        * Primeiras aberturas do app
        * https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg
        * Sessões

        **Observação**:

        * A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.
        * Para o parâmetro `device_ids`, selecionar o tipo `custom`.
          * O ID `custom` gerado para as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder aos seus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e ao ID <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">das sessões</Anchor>.
          * Envie eventos usando a API. Compartilhe com seu desenvolvedor quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.

        Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>
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
        **Recomendado**: Uma landing page multiplataforma que utiliza o Smart Script da AppsFlyer e permite que você faça a atribuição web-to-app. Recomendado em casos em que a sua campanha promove um app disponível em diversas plataformas, como na Epic e Native PC.

        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor>

        <Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor>

        **Observação**:

        Para o Nintendo Switch, os seguintes parâmetros são necessários:

        * **plataforma**  
          switch
        * **nintendo\_app\_id**  
          O ID da página do aplicativo.  

          Você pode encontrar seu ID exclusivo do aplicativo copiando-o da barra de URL ou acessando <Anchor target="_blank" href="https://www.nintendo.com/store/products/octopath-traveler-ii-switch/">https://www.nintendo.com/store/products/</Anchor> e pesquisando seu jogo. Exemplo:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```

          onde **app-id** é o ID exclusivo do seu aplicativo.
        * **fonte\_de\_mídia**

        Os seguintes parâmetros não são obrigatórios, mas são recomendados:

        * **campanha**
        * **anúncio**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          A URL completa da loja do Nintendo Switch para seu aplicativo, incluindo seu **nintendo\_app\_id**.  
          Exemplo:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```
      </td>
      <td>
        Profissional de marketing (a assistência de um desenvolvedor pode ser necessária)
      </td>
    </tr>
    <tr>
      <td>
        Configuração do link
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
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor>
      </td>
      <td>
        Profissional de marketing/engenheiro de dados
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| Caraterística | Considerações |
| --- | --- |
| Redirecionamento | Atualmente sem suporte |
| Dados de custo | Os dados de custo devem ser enviados por meio do <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Ad Spend Ingestion</Anchor> usando o método de upload de arquivo por e-mail. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-nintendo-switch-attribution=sobre-a-atribui%C3%A7%C3%A3o-no-nintendo-switch 01H7Z1HPD0AB0VP6REMBF2HCR8=sobre-a-atribui%C3%A7%C3%A3o-no-nintendo-switch example-attribution-flow=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=etapas-de-integra%C3%A7%C3%A3o 01H7Z1HPD0VAMPEHBPN8MAT3ST=etapas-de-integra%C3%A7%C3%A3o 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
