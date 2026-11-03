---
title: '[Boletim] Os dados de agência agora são transparentes'
metadata:
  keywords:
    - Marketers
    - Platform essentials
    - Agencies
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2025-01-23T11:20:37Z'
  edited_at: '2025-02-11T21:01:04Z'
  id: 32048747169553
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/32048747169553
---
| **Novidades** | A partir de agora, todas as agências são transparentes. Essa alteração aumenta a sua capacidade de analisar e otimizar os seus investimentos em marketing com um maior nível de granularidade. |
| --- | --- |
| **Data da atualização** | 12 de março de 2025 |
| **O que você precisa saber** | **Antes da alteração**: Para agências não transparentes, o campo de fonte de mídia mostrava o nome da agência, em vez da ad network específica.<br /><br />**Depois da alteração**<ul><li>Todos os dados de campanha gerenciados pela agência ficarão totalmente visíveis para até o nível de fonte de mídia, independentemente das configurações de transparência anteriores. Ou seja, o campo de fonte de mídia mostrará a ad network específica, em vez do nome da agência. Você ainda poderá agrupar os dados por agência.</li><li>Dashboards: os dados históricos da agência também serão considerados transparentes.</li><li>Relatórios: os dados dos relatórios recebidos antes da alteração não serão atualizados. Por exemplo, os relatórios exibidos no Data Locker antes dessa atualização incluirão dados não transparentes, mas os relatórios realizados após a atualização mostrarão dados transparentes.</li><li>As regras de validação do Protect360 definidas para "agências não transparentes" serão reclassificadas simplesmente para "agências". As regras continuarão a funcionar sem problemas no framework atualizado de transparência, com todas as outras configurações definidas.</li><li>Se você estiver trabalhando com dados de custos enviados antes da alteração, poderá ver o custo agregado separado em várias linhas: uma sob o nome da agência anterior (antes da alteração) e outra sob a fonte de mídia diretamente (após a alteração). Nesse caso, os dados de custo de antes da alteração devem ser substituídos pelos dados após a alteração.</li></ul> |
| **O que você precisa fazer** | Se você tiver workflows internos que dependem do "nome da agência" atual exibido como a fonte de mídia para agências não transparentes, faça uma revisão desses workflows e considere a possibilidade de atualizá-los para acomodar essa alteração.<br /><br />Por exemplo, nos dashboards, agrupe os dados por fonte de mídia ou agência. Nos relatórios, use os campos `media_source` ou `af_prt`, conforme necessário. |