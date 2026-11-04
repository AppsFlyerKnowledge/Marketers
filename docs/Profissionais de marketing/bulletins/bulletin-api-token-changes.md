---
title: 'Boletim: alterações de token de API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2026-08-18T00:18:56Z'
  id: 12399683708305
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/12399683708305
---
| **Novidades** | Para fornecer uma experiência mais segura e confiável para o uso da API, o token da API V1, incluído nas URLs da API, será substituído pelo token da API V2, que é um token baseado em JWT transmitido no cabeçalho para autorização do portador.<br /><br />O token da API V1 e as APIs que o utilizam não estão mais disponíveis desde 18 de setembro de 2023. |
| --- | --- |
| **Data de início** | 18 de setembro de 2023 |
| **Pré-requisitos** | Somente um administrador pode <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#recuperar-tokens">recuperar o token da API V2</Anchor> do painel da AppsFlyer. |
| **Quem precisa atualizar o token da API?** | Tanto os anunciantes quanto as agências que ainda usam o token da API V1 precisam atualizar seus tokens. |
| **Como encontrar tokens da API V1** | Use o <Anchor target="_blank" href="/marketers/pt/docs/audit-log">Registro de auditoria</Anchor> para filtrar quaisquer tokens da API V1 ainda em uso. Você pode fazer download dos dados para um arquivo CSV:<ol><li>Acesse o [Painel de registro de auditoria](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Digite "Token da API V1" na barra de pesquisa.</li><li>No filtro de **Serviço** , selecionar apenas **chamadas de API** e filtre os resultados.</li><li>Clique no ícone Download no canto superior direito da página.<br />Seu arquivo CSV é baixado e inclui o ID do aplicativo, o serviço usado e o URL da chamada de API.</li></ol> |
| **Ação necessária** | **Atualize as seguintes APIs para o token da API V2:**<ol><li>Acesse a <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">página do token da API</Anchor>.</li><li>No token de API V2.0, clique no ícone **Copiar para a área de transferência**.</li><li>Para cada uma das seguintes APIs:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">API mestre V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">API de extração agregada V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">API de extração de dados brutos V2</Anchor></li></ul><ol><li>Substitua o URL da API V1 pelo URL na documentação acima.</li><li>Cole o token que você copiou no cabeçalho de autenticação do portador.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Para a **API OpenDSR**, cole o token no cabeçalho do portador da solicitação:<br />`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **Sobre os tokens de API** | **Saiba mais sobre os tokens de API:**<ul><li><Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Gerenciando tokens da API</Anchor><ul><li><Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Pull API agregada</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">Dados brutos</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests#formato-da-solicitação-do-gdpr">API OpenDSR</Anchor></li></ul></li></ul> |