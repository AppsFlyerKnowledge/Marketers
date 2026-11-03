---
title: 'Boletim: novos campos e valores do Data Locker e da Push API'
metadata:
  keywords:
    - Data Locker
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2022-12-04T20:34:01Z'
  edited_at: '2026-10-20T03:56:22Z'
  id: 11135475316113
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/11135475316113
---
| **Novidades** | <ul><li>Os relatórios do SKAdNetwork via Data Locker e Push API incluem novos campos para dar suporte ao SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: o valor é um integer que representa a janela SKAN, `0`, `1` ou `2`. Para SKAN 3, o valor é `0`.</li><li>**skad\_coarse\_conversion\_value**: Valor pode ser `low`, `medium` ou `high`. Para SKAN 3, o valor é `null`.</li><li>**skad\_source\_identifier**: o valor é uma string de até 4 dígitos. Para SKAN 3, o valor é `null`.</li><li>**skad\_source\_domain**: o valor é uma string que representa a origem dos anúncios da web atribuíveis. Para SKAN 3, o valor é `null`.</li><li>**ad\_network\_creative**: o valor é uma string baseada no enriquecimento de dados recebido da ad network. Para SKAN 3, o valor é `null`.</li></ul></li><li>Quando o canal de mídia é Meta ads, todos os relatórios exibem o valor `Facebook Ads` (não Facebook).</li></ul> |
| --- | --- |
| **Data de início** | Alterações no esquema dos relatórios em 9 de janeiro de 2023. O preenchimento de dados desses campos começa como parte do lançamento do SKAN 4 da AppsFlyer (em breve). |
| **Onde:** | Os seguintes relatórios são afetados:<ul><li>Novos campos do SKAN 4:<ul><li>**skad\_installs** (via Data Locker e Push API)</li><li>**skad\_redownloads** (via Data Locker e Push API)</li><li>**skad\_inapps** (via Data Locker e Push API)</li><li>**skad\_postbacks** (via Data Locker)</li><li>**skad\_postbacks\_copy** (não inclui o campo ad\_network\_creative) (via Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Veja exemplos de esquemas de relatório</Anchor></li></ul></li><li>Canal de mídia Meta ads: Todos os relatórios</li></ul> |