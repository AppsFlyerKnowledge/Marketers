---
title: 'Comunicado: atualização do relatório pós-atribuição do Protect360'
metadata:
  keywords:
    - Pull API
    - Advertisers
    - Protect360
    - Raw Data
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-25T11:39:55Z'
  edited_at: '2026-10-20T03:57:08Z'
  id: 360015900018
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/360015900018
---
| **Novidades** | Os relatórios pós-atribuição do Protect360 exibem o contribuinte válido (canal de mídia) para instalações sequestradas e eventos in-app. Ou seja, o contribuinte que originalmente deveria ter recebido a atribuição. |
| --- | --- |
| **Data de início** | 23 de novembro de 2020 |
| **Onde:** | Relatórios de dados brutos pós-atribuição do Protect360 via:<ul><li>Exportar dados (download) de relatórios de dados brutos</li><li>Relatórios de dados brutos da Pull API</li></ul> |
| **O que** | <ul><li>Até agora, os relatórios pós-atribuição não exibiam o canal de mídia do contribuinte válido. Os campos **contributor[1-3]** e **organic** exibiam os canais de mídia contribuintes, mas não permitiam saber qual deles justificava a atribuição.</li><li>A partir de 23 de novembro de 2020, o valor do campo **rejected\_reason\_value** exibe **contributor[1-3]** ou **organic**.<ul><li>No Data Locker, isso aparece como **validation\_reason\_value**.</li></ul></li><li>Os anunciantes podem verificar os campos **contributor[1-3]** para ver qual deve ser o canal de mídia atribuído e usar essas informações para reconciliação.<ul><li>Se os campos de contribuinte não forem exibidos no seu relatório, eles podem ser adicionados na página **Export data**.</li></ul></li></ul> |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#postattribution-reports">Relatórios pós-atribuição:</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#pull-api">Relatórios da Pull API</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#protect360::440536f1">Rejected\_reason\_value</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::f1c497c7">Contributor[1-3]</Anchor>
> * Novidades na AppsFlyer

<div data-zendesk-anchors="h_01HDPEGXJSMW6Q9DXA89AZ20T6=consulte-tamb%C3%A9m" />
