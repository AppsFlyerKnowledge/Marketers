---
title: 'Aviso: alteração no parâmetro de atribuição do preload referrer'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2023-12-12T19:07:05Z'
  id: 20161765461009
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/20161765461009
---
| **Novidades** | O parâmetro de atribuição do preload referrer de novas instalações, eventos in-app e sessões atribuídas a instalações registradas após a data de vigência será relatado de forma diferente.<br /><br />Listamos abaixo as alterações feitas:<ul><li>**attributed\_touch\_type** será **download** (no lugar de preload ou click\_to\_download)<ul><li>e**ngagement\_type** será **preload** (para preload\_rfr match type) ou **click\_to\_download** (para af\_referrer match type)</li></ul></li></ul>Eventos in-app e sessões atribuídas a instalações antes da data de vigência manterão o comportamento existente:<ul><li>**attributed\_touch\_type** será **preload** ou **click\_to\_download**<ul><li>**engagement\_type** será **empty**</li></ul></li></ul> |
| --- | --- |
| **Data de início** | 17 de janeiro de 2024 |
| **O que isso afeta** | <ul><li>Anunciantes e agências que usam a <Anchor target="_blank" href="/marketers/pt/docs/set-up-appsflyer-preload-referrer-attribution">atribuição de preload referrer da AppsFlyer</Anchor></li><li>Onde essa alteração será feita: dashboards e relatórios de dados brutos</li></ul> |