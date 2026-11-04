---
title: >-
  Boletim: obtenha atribuição de anúncios da Meta em relatórios de dados brutos
  com o install referrer da Meta
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-02-12T10:47:33Z'
  edited_at: '2026-10-20T03:55:45Z'
  id: 22461635687185
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/22461635687185
---
| **Novidades** | O install referrer da Meta ajuda na mensuração de atribuição das suas campanhas de anúncios para Android no Facebook, Instagram e Audience Network, quando o objetivo é instalações do aplicativo. Isso é adicional ao install referrer do Google Play. |
| --- | --- |
| **Data de início** | 28 de fev. de 2024 |
| **Pré-requisitos** | Confira o seguinte:<ul><li>Você tem a versão **V6.12.6** ou posterior do SDK da AppsFlyer para garantir que os dados de referrer sejam transmitidos corretamente</li><li>A <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#encrypted-data-from-the-referrer">chave de descriptografia do Install referrer</Anchor> na página de integração foi inserida</li><li>As versões <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites">descritas aqui</Anchor> estão instaladas nos dispositivos dos seus usuários</li></ul> |
| **Ações necessárias** | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support">Configure o suporte ao install referrer da Meta</Anchor> |
| **O que devo saber?** | Os dados de referrer têm prioridade sobre os dados fornecidos pela integração do Meta Ads e estão disponíveis em relatórios de dados brutos. Essa solução se aplica à atribuição de cliques e não à atribuição de exibição. |
| **Qual o impacto?** | <ul><li>Você pode ver um aumento nas instalações atribuídas à Meta em relatórios de dados brutos</li><li>Dois novos campos de tipo de correspondência agora estão incluídos em relatórios de dados brutos, `fb_referrer` e `ig_referrer`:<ul><li>`fb_referrer` para atribuição do aplicativo do Facebook</li><li>`ig_referrer` para atribuição do aplicativo do Instagram</li><li>`fb_referrer` ou `ig_referrer` para atribuição da Audience Network.</li></ul></li></ul> |

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#userlevel-data">Install referrer do Meta</Anchor>

<div data-zendesk-anchors="h_01H9FHRVKE88CXGH8G7E26ZXT2=consulte-tamb%C3%A9m" />
