---
title: 'Boletim: atualização do detalhamento de Meta Ads por canal'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-08-04T08:33:09Z'
  edited_at: '2026-10-20T03:54:07Z'
  id: 49465306965393
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/49465306965393
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | A Meta agora exige adesão por conta de anúncios para o detalhamento `impression_device`, com vigência a partir de 6 de agosto de 2026. Como a API de relatórios da Meta não consegue retornar dados de custo detalhados por geolocalização e canal na mesma consulta, as contas sem essa adesão verão dados incompletos:<ul><li>Os dados de custo no nível de canal podem não aparecer na visualização padrão do My Dashboards</li><li>Os dados da Meta podem não aparecer no Cost ETL</li></ul>A mesma limitação também afeta os dados de performance de criativos segmentados por canal. |
| **Data de início** | 6 de agosto de 2026 |
| **O que você precisa saber** | A Meta aplica essa adesão automaticamente nas contas de clientes da AppsFlyer. Você não precisa fazer nada antes de 6 de agosto.<ul><li>Se os seus dados de custo detalhados por canal ou os seus dados de performance de criativos detalhados por canal não aparecerem após 6 de agosto, a adesão automática ainda não foi aplicada à sua conta.</li></ul> |
| **O que você precisa fazer** | Execute as seguintes etapas:<ol><li>Depois de 6 de agosto, verifique seus dados de custo segmentados por canal (My Dashboards) e seus dados de performance de criativos segmentados por canal.</li><li>Se você notar uma lacuna, entre em contato diretamente com a Meta para receber orientações sobre como ativar a adesão ou fale com seu representante da AppsFlyer para receber ajuda.</li><li>Assim que a adesão for aplicada à sua conta, seus dados serão preenchidos automaticamente por backfill pouco tempo depois.</li><li>Você também pode verificar diretamente no Ads Manager se Impression Device já está ativado para a conta. Veja abaixo [Como verificar Impression Device no Ads Manager](#como-verificar-impression-device-no-ads-manager) para conferir as etapas.</li></ol> |

<div id="check-impression-device-in-ads-manager" />

## Como verificar Impression Device no Ads Manager

Para verificar se Impression Device já está ativado para uma conta de anúncio:

1. Acesse o <Anchor target="_blank" href="https://adsmanager.facebook.com/">Ads Manager</Anchor> e selecione **Settings**.

[![Barra de ferramentas do Ads Manager mostrando o botão Settings](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)

2. No painel Create, selecione **Delivery**.
3. Em Delivery, localize **Additional Breakdowns**.
4. Em Additional Breakdowns, verifique se o símbolo de mais ao lado de **Impression Device** (`impression_device`) já está selecionado. Se estiver, a adesão estará ativa para esta conta.

[![Painel Additional Breakdowns no Ads Manager com ícones de mais para Time of Day, Impression Device e Frequency Value](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)

<div data-zendesk-anchors="check-impression-device-in-ads-manager=como-verificar-impression-device-no-ads-manager h_01KZ63J08GPADE2AH0KV9NNESC=como-verificar-impression-device-no-ads-manager" />
