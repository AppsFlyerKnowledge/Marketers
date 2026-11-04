---
title: 'Boletim: Apple Ads adiciona timestamps a todas as reivindicações de atribuição'
metadata:
  keywords:
    - apple ads
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-26T09:02:50Z'
  edited_at: '2026-10-20T03:54:02Z'
  id: 50216486847249
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/50216486847249
---
| Seção | Detalhes |
| --- | --- |
| Novidades | Em 1 de setembro de 2026:<ul><li>A API AdServices da Apple adiciona um timestamp de engajamento a todas as reivindicações de atribuição do iOS, incluindo aquelas que antes não tinham um. A AppsFlyer usa esse timestamp para aplicar a janela de lookback configurada e as regras de atribuição de último toque a essas reivindicações.</li><li>Para grupos de anúncios com segmentação por idade ou gênero, a Apple retornará um payload de atribuição como false, e esses engajamentos não poderão ser atribuídos ao Apple Ads no AppsFlyer.</li></ul> |
| Data de entrada em vigor | 1 de setembro de 2026 |
| O que você deve saber | <ul><li>Para a maioria das campanhas do Apple Ads, a precisão da atribuição melhora porque os engajamentos agora são avaliados com base na sua janela de lookback definida pelo anunciante, em vez das janelas padrão anteriores, incluindo engajamentos de usuários sem consentimento que antes eram reivindicados sem timestamp.</li><li>Além disso, grupos de anúncios com segmentação por idade ou gênero retornarão um payload de atribuição false. Os engajamentos desses grupos de anúncios não são reivindicados pelo Apple Ads e, portanto, não podem ser atribuídos a ele.</li></ul> |
| O que você precisa fazer | Nenhuma ação é necessária. Sua integração com o Apple Ads reflete essa mudança automaticamente. Se você veicula grupos de anúncios com segmentação por idade ou gênero, revise seus relatórios do Apple Ads após 1º de setembro para entender qualquer mudança nas conversões atribuídas. |

<div id="see-also" />

#### Consulte também

* <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup">Configuração da integração do Apple Ads (Search Ads)</Anchor>

<div data-zendesk-anchors="h_01M0YZSHS593T92XC58PR1FXYY=consulte-tamb%C3%A9m" />
