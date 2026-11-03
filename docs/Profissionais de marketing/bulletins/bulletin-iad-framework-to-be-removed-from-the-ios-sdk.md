---
title: 'Comunicado: framework iAd será removido do SDK do iOS'
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-13T10:20:29Z'
  edited_at: '2026-10-20T03:56:05Z'
  id: 19329934807569
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/19329934807569
---
| **Novidades** | A Apple anunciou que qualquer aplicativo que contenha código do framework iAd deixará de abrir no iPhone e no iPad daqui a dois anos. O framework iAd era obrigatório para aplicativos iOS que funcionavam com o Apple Search Ads (ASA) no passado, antes de ser substituído pela Apple Ads Attribution API.<br /><br />Desde a versão 6.10.1, o SDK do iOS da AppsFlyer não vem usando o framework iAd e passou a depender exclusivamente da Apple Ads Attribution API. No entanto, o código do framework ainda estava incluído no SDK.<br /><br />No entanto, a próxima versão do <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">SDK do iOS</Anchor> da AppsFlyer (6.12.3) atenderá aos requisitos da Apple e não conterá nenhum código do framework iAd. A versão 6.12.3 está prevista para meados de novembro, e recomendamos fortemente adotá-la.<br /><br />**Observe que, mesmo que você não atualize seu SDK para a versão 6.12.3, a Apple oferece um período de carência de 2 anos antes de impedir que seu aplicativo abra.** |
| --- | --- |
| **Data de início** | Data de lançamento futura do SDK do iOS 6.12.3 (novembro de 2023) |
| **O que isso afeta** | A atribuição não é afetada. Na verdade, desde a v6.10.1 o SDK da AppsFlyer usa o framework AdServices mais recente do ASA e não depende do framework iAd, que foi descontinuado. |