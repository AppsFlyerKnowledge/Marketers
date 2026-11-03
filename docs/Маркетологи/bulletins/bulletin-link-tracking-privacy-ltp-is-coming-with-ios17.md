---
title: >-
  Бюллетень: в iOS17 появится защита конфиденциальности при отслеживании ссылок
  (LTP)
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2023-09-21T08:37:39Z'
  edited_at: '2026-10-19T14:39:37Z'
  id: 18730398273553
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/18730398273553
---
| **Что нового?** | iOS17 будет обнаруживать и удалять параметры, определенные как параметры отслеживания, из ссылок, которыми пользователи делятся во встроенных приложениях: Mail, Messages и в режиме частного просмотра Safari.<br /><br />Мы провели внутреннее тестирование, чтобы проверить, как LTP влияет на OneLink. Наши результаты показывают, что ни один из параметров AppsFlyer не был удален. Вот результаты наших тестов:<br /><br />**<span id="h_01HAVEDAEFTDVGS1SXBD7NEJFE"></span>Следующие параметры удаляются с помощью LTP**<ul><li>`gclid` — идентификатор ID Google ads / Analytics</li></ul><ul><li>`fbclid` — рекламный идентификатор Facebook</li></ul>**<span id="h_01HAVEDAEFN7XEPK3TNCSZRAMW"></span>Следующие параметры не затрагиваются LTP**<ul><li>Параметры UTM</li></ul>**<span id="h_01HAVEDAEFMGD1SFYRJNXE9JBE"></span>Параметры атрибуции AppsFlyer:**<ul><li>`pid`</li></ul><ul><li>`c`</li></ul><ul><li>`Is_regtargeting`</li></ul><ul><li>`af_channel`</li></ul><ul><li>`af_adset`</li></ul><ul><li>`af_ad`</li></ul><ul><li>`af_sub1-10`</li></ul><ul><li>`af_inactivity_window`</li></ul><ul><li>`af_click_lookback`</li></ul><ul><li>`af_cost_value`</li></ul><ul><li>`af_cost_currency`</li></ul>**<span id="h_01HAVEDAEFEFZ1ZCPAZ05C3AWW"></span>Параметры перенаправления AppsFlyer**<ul><li>`af_dp`</li></ul><ul><li>`deep_link_value`</li></ul><ul><li>`af_deep_link_sub1-10`</li></ul><ul><li>`af_web_dp`</li></ul><ul><li>`af_ios_url`</li></ul><ul><li>`af_android_url`</li></ul><ul><li>`af_xp`</li></ul> |
| --- | --- |
| **Дата вступления в силу** | Дата публичного релиза iOS17 (18 сентября 2023) |
| **На что это влияет** | **<span id="h_01HAVEDAEFE7K3FT7RNA0FANHV"></span>Перенаправление и диплинкинг**<br /><br />Вероятность того, что это изменение повлияет на перенаправление и диплинкинг, невелика. Единственный случай, когда диплинкинг может быть затронут, — когда атрибуция зависит от GCLID или FBCLID.<br /><br />**<span id="h_01HAVEDAEFAB2AGW54XW52YAXJ"></span>Web-2-app**<br /><br />Поскольку LTP применяется только к режиму частного просмотра Safari, мы ожидаем минимального влияния на атрибуцию для сценариев Web-to-app. Однако, когда пользователь находится в режиме частного просмотра Safari, параметры GCLID и FBCLID, которые удаляет LTP, не будут сопоставляться с помощью Smart script.<br /><br />**<span id="h_01HAVEDAEFTC8QRKTZCQZSC8G6"></span>Email, SMS и уведомления**<br /><br />Встроенные приложения Apple, такие как Mail и Messages, будут блокировать соответствующие параметры отслеживания, упомянутые выше. Поэтому использование ссылок в таких кампаниях может привести к потере данных на уровне пользователя. Кроме того, в рамках этого изменения некоторые идентификаторы статистики поставщика услуг электронной почты (ESP) могут быть заблокированы, что потенциально повлияет на статистику email-кампаний. Рекомендуем обратиться к своему поставщику услуг электронной почты (ESP), чтобы полностью оценить последствия. |