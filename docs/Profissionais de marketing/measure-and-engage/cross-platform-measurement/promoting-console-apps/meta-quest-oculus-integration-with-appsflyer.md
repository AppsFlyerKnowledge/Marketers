---
title: Integração do Meta Quest (Oculus) com a AppsFlyer
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
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-06T00:11:28Z'
  id: 11241398279569
  locale: pt
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/pt/articles/11241398279569
---
> **Visão geral:** Integre seu aplicativo do Meta Quest (Oculus) com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas no Meta Quest (Oculus).

## Sobre a atribuição do Meta Quest (Oculus)

O Meta Quest (Oculus) para gaming funciona em todos os dispositivos Meta Quest (Oculus).

Os aplicativos executados no Meta Quest podem se integrar à AppsFlyer por meio da S2S API ou SDK para receber dados de atribuição e mensuração de performance, que oferecem um insight sobre quais fontes e campanhas impulsionam aberturas do app e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar um app do Meta Quest (Oculus) na AppsFlyer.

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
        * <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu aplicativo Meta Quest (Oculus) na AppsFlyer</Anchor>
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
        Existem dois métodos de integração que podem ser utilizados: S2S e SDK.

        Para o método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integre a API da AppsFlyer</Anchor> no seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.

        * Primeira abertura do app
        * https://support.appsflyer.com/hc/article_attachments/19284078965009
        * Sessions

        Observação:

        * A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.
        * Para o parâmetro `device_ids`, selecione o tipo `custom`.
          * O ID `custom` gerado para as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder aos seus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e ao ID <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">das sessões</Anchor>.
          * Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.
          * Para reportar engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engajamento de impressões</Anchor>.

        Para o método SDK, há duas versões: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal.</Anchor>

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

        Para o Meta Quest, os seguintes parâmetros são necessários:

        * **plataforma**: quest
        * **QUEST\_APP\_ID**: Quest Store app ID.  
          Para o Quest 2, esse é o número na URL da loja, por exemplo:

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          onde **XXXXXXXXXXXXXXXX** é seu App ID exclusivo.
        * **fonte\_de\_mídia**

        Os seguintes parâmetros não são obrigatórios, mas são recomendados:

        * **Carga útil**
        * **anúncio**
        * **ad\_set**
        * **storefront\_redirect\_url**: A URL completa da loja do Oculus para o seu aplicativo, incluindo seu **QUEST\_APP\_ID**. Por exemplo, `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/`.
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

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Categoria do dispositivo (por exemplo, MOBILE\_PHONE, TV) | Atualmente não compatível |
| Dados de custos | Importe dados de custo via <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> usando o método de upload de arquivo **por e-mail** . Você também pode extrair dados **via API** do Google, Meta ou TikTok. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-meta-quest-attribution=sobre-a-atribui%C3%A7%C3%A3o-do-meta-quest-oculus 01H7Z1MK9JHA4C5CB7YME4AJMA=sobre-a-atribui%C3%A7%C3%A3o-do-meta-quest-oculus integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z1MK9JNRKAY9VNH5RTF03F=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
