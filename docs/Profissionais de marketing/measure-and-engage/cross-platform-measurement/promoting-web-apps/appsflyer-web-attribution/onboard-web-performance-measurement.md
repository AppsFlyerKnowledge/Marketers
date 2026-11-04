---
title: Onboarding para a mensuração da performance web
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-08-25T00:22:15Z'
  id: 43529798016401
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43529798016401
---
> **Resumo:** Siga as instruções de onboarding deste guia para configurar a mensuração da performance web. Após a configuração, você poderá mensurar e atribuir visitas ao site e eventos web a canais de marketing, compreender o que impulsiona resultados significativos e auxiliar a mensuração cross-platform.

<div id="about-web-performance-measurement" />

## Sobre a mensuração da performance web

A mensuração da performance web ajuda você a conectar o que acontece no seu site, como visitas e eventos web, às fontes de marketing que os impulsionaram. Em resumo, ela mostra quais canais de mídia e campanhas atraem usuários para o seu site e influenciam suas próximas ações, permitindo que você realize a mensuração de performance e otimize o ROI.

<div id="create-a-web-app-in-appsflyer" />

### Criar um aplicativo web na AppsFlyer

<Embed title="Onboarding para a mensuração da performance web" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" providerUrl="https://www.youtube.com" />

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

### Configurar integrações de ad network, postbacks e mensuração de custo

<Embed title="Onboarding para a mensuração da performance web" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

Para dar início à mensuração de visitas ao site e eventos web na AppsFlyer, siga as etapas de onboarding na checklist de configuração da mensuração da performance web:

<div id="web-performance-measurement-setup-checklist" />

## Checklist de configuração da mensuração da performance web

Use a tabela abaixo para definir as principais tarefas de configuração, os responsáveis e a ordem para registrar visitas e eventos web na AppsFlyer.

| Função | Ações necessárias | Onde aprender a | Responsável |
| --- | --- | --- | --- |
| 1. Criar um aplicativo web | Na página de **configurações do aplicativo**:<ul><li>Copie o **ID do Web SDK** e compartilhe com seus desenvolvedores.</li><li>Defina o **fuso horário** e a **moeda** para os relatórios.</li><li>Selecione os **domínios excluídos**.</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Configurar as definições do aplicativo web</Anchor></li></ul> | Marketer |
| 2. (Opcional) Criar uma linha de produtos para o LTV cross-platform | Para permitir a atribuição cross-platform e a mensuração da jornada do usuário em termos de LTV, crie uma linha de produtos e inclua os aplicativos/propriedades web relevantes ou adicione seu aplicativo web a uma linha de produtos já existente. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution">Criar uma linha de produtos</Anchor></li></ul> | Marketer |
| 3. Instalar e configurar o Web SDK | Integre o Web SDK da AppsFlyer no seu site. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">Integrar o Web SDK no seu site</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/use-the-web-sdk-test-page">Teste a integração do SDK web</Anchor></li></ul> | Desenvolvedor |
| 4. Enviar dados da web usando a S2S API | Use a server-to-server (S2S) API para enviar visitas e eventos web diretamente do seu servidor para a AppsFlyer. Use-a junto com o Web SDK para ampliar a cobertura da mensuração e enriquecer dados de eventos. Outra opção é usá-la de forma isolada para uma integração server-side completa. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement">Configurar a S2S API para mensurar a performance web</Anchor></li></ul> | Engenheiro de business intelligence (BI) |
| 5. Configurar as definições de atribuição do aplicativo web | Na página **Configurações do aplicativo** , configure as definições de atribuição do aplicativo web, como as janelas de lookback e os eventos de aquisição de usuários.  <br />**Observação:** os eventos personalizados de aquisição de usuários só podem ser selecionados após a integração do Web SDK ao seu site. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings">Configurar as definições de atribuição do aplicativo web</Anchor></li></ul> | Marketer |
| 6. Criar URLs para mensurar a performance na web | Crie URLs usando os parâmetros de atribuição corretos para obter resultados de atribuição mais precisos e granulares. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/choose-attribution-parameters-for-landing-page-urls">Selecionar os parâmetros de atribuição para as URLs das landing pages</Anchor></li></ul> | Marketer |
| 7. Configurar a integração com os parceiros compatíveis | Ative os parceiros e defina os postbacks enviados a eles.<br />Parceiros compatíveis:<ul><li>Google Ads</li><li>Meta Ads</li><li>TikTok Ads</li><li>Snapchat Ads</li></ul> | Criar campanhas na web para aplicativos de sites com:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-campaigns-for-website-apps">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/snapchat-create-web-campaigns-for-website-apps">Snapchat Ads</Anchor></li></ul> | Marketer |
| 8. Exportar dados de mensuração web a partir do Data Locker | Configure o **Data Locker** para os relatórios de dados brutos da mensuração da performance web, para que as equipes de business intelligence e analytics possam analisar jornadas web. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/export-web-performance-measurement-report-data-from-data-locker">Exportar dados de mensuração web a partir do Data Locker</Anchor></li></ul> | Marketer / Engenheiro de BI |
| 9. Visualize seus dados web no dashboard cross-platform | Veja como sessões e eventos web são exibidos no dashboard cross-platform. | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#atribuição-web-no-dashboard-cross-platform">Atribuição web no dashboard cross-platform</Anchor></li></ul> | Marketer |
| 10. Calcular o custo das campanhas no site<br /><br /><strong>(Apenas para o ROI360)</strong> | Conecte seus aplicativos web às integrações de custos nas <strong>configurações de custo</strong> para as Self-reporting networks (SRNs) compatíveis: Google, Meta (Facebook), Snapchat e TikTok.  <br />  <br />Depois de conectados, os custos, cliques e impressões das campanhas na web são apresentados quase em tempo real nos relatórios do Cost ETL e no My Dashboards.  <br />  <br />No <strong>pacote avançado do ROI360</strong>, adicione seu aplicativo web à lista de aplicativos incluídos na página de configuração do Cost ETL.  <br />  <br /><strong>Atenção:</strong> os links de atribuição devem incluir um ID de campanha na URL da landing page | Conectar seu aplicativo web à integração de custos:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-campaigns-for-website-apps#mensurar-dados-de-performance-web-com-custo-web">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-campaigns-for-website-apps#mensurar-os-dados-de-atribuição-web-com-os-custos-da-web">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/snapchat-create-web-campaigns-for-website-apps#mensurar-os-dados-de-atribuição-web-com-os-custos-da-web">Snapchat Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Configurar Cost ETL</Anchor></li></ul> | Marketer / Engenheiro de BI |

<div data-zendesk-anchors="about-appsflyer-web-attribution=sobre-a-mensura%C3%A7%C3%A3o-da-performance-web h_01KGN43TYPKCQ7H3SRRHHPT387=sobre-a-mensura%C3%A7%C3%A3o-da-performance-web how-to-create-a-web-app-in-appsflyer=criar-um-aplicativo-web-na-appsflyer h_01KVSNN9H462X8DVYBS6TJ8JXQ=criar-um-aplicativo-web-na-appsflyer how-to-set-up-network-integrations-postbacks-and-cost-measurement=configurar-integra%C3%A7%C3%B5es-de-ad-network-postbacks-e-mensura%C3%A7%C3%A3o-de-custo h_01KVSNSSZ7QY090JVWVTRF88ND=configurar-integra%C3%A7%C3%B5es-de-ad-network-postbacks-e-mensura%C3%A7%C3%A3o-de-custo appsflyer-web-attribution-setup-checklist=checklist-de-configura%C3%A7%C3%A3o-da-mensura%C3%A7%C3%A3o-da-performance-web h_01KGN43TYP1EV5KFQ37FC4SM0C=checklist-de-configura%C3%A7%C3%A3o-da-mensura%C3%A7%C3%A3o-da-performance-web" />
