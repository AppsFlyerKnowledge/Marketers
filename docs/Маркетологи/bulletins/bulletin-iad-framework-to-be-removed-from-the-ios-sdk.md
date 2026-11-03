---
title: 'Бюллетень: фреймворк iAd будет удален из iOS SDK'
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
  edited_at: '2026-10-19T14:39:35Z'
  id: 19329934807569
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/19329934807569
---
| **Что нового?** | Apple объявила, что через два года любое Приложение, содержащее код фреймворка iAd, перестанет запускаться на iPhone и iPad. В прошлом фреймворк iAd был обязательным для приложений iOS, работающих с Apple Search Ads (ASA), прежде чем его заменил Apple Ads Attribution API.<br /><br />Начиная с версии 6.10.1 AppsFlyer iOS SDK не использует фреймворк iAd и полагается исключительно на Apple Ads Attribution API. Однако код фреймворка все еще входил в SDK.<br /><br />Однако следующая версия <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes">AppsFlyer iOS SDK</Anchor> (6.12.3) будет соответствовать требованиям Apple и не будет содержать код фреймворка iAd. Версия 6.12.3 ожидается в середине ноября, и мы настоятельно рекомендуем перейти на нее.<br /><br />**Обратите внимание: даже если вы не обновите SDK до версии 6.12.3, Apple предоставляет льготный период на 2 года, прежде чем заблокировать запуск приложения.** |
| --- | --- |
| **Дата вступления в силу** | Запланированная дата релиза iOS SDK 6.12.3 (November, 2023) |
| **На что это влияет** | Атрибуция не затронута. Фактически начиная с версии 6.10.1 AppsFlyer SDK использует новейший фреймворк ASA AdServices и не полагается на устаревший фреймворк iAd. |