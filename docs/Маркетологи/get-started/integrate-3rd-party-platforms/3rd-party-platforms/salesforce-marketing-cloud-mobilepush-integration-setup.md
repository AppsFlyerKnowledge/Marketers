---
title: Настройка интеграции Salesforce Marketing Cloud MobilePush
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2026-08-18T00:12:34Z'
  id: 10590769196817
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/10590769196817
---
> **Краткий обзор.** Salesforce Marketing Cloud MobilePush, интегрированный партнер AppsFlyer, — это платформа привлечения пользователей для специалистов по маркетингу, росту и вовлечению.

<div id="overview" />

## Обзор

Salesforce Marketing Cloud MobilePush позволяет создавать и отправлять целевые push-сообщения на основе кросс-канальных данных о потребителях. Это стимулирует использование приложений и повышает рентабельность инвестиций. С помощью MobilePush вы можете просматривать, как пользователи перемещаются по вашему приложению, от продуктов, которые они просматривают, и до времени, проведенного на каждой странице. Интеграция MobilePush позволит вам:

* Повысить активность и эл. коммерцию
* Получать ценную информацию о пользователях
* Легко создавать кросс-канальные кампании
* Сегментировать и планировать сообщения

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам.  Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Настройка Salesforce Marketing Cloud MobilePush

Большая часть настройки выполняется в Salesforce (шаги 1-4). Шаг 5 выполняется в AppsFlyer.

<div id="step-1-set-up-mobilepush-sdk" />

### Шаг 1: Настройте SDK MobilePush

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Выполните настройку SDK MobilePush</Anchor>

<div id="step-2-provision-for-push-notifications" />

### Шаг 2: Условия для работы push-уведомлений

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Создайте сертификат `.p12`</Anchor>

<div id="step-3-enable-app-push-notifications" />

### Шаг 3: Включите push-уведомления приложения

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Внедрите push-уведомления</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### Шаг 4: Настройте push-уведомлений приложения

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Создавайте и отправляйте push-сообщения на мобильные устройства</Anchor>

<div id="note" />

> 📘 **Примечание**
>
> При создании push-уведомления в Salesforce Marketing Cloud необходимо добавить <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">пользовательский ключ</Anchor>, чтобы AppsFlyer мог правильно атрибутировать PID и атрибуты кампании. В качестве пользовательского ключа используйте `AF_xxxxxxxxx`.

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### Шаг 5: Настройте push-уведомления в AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Настройте SDK iOS с помощью OneLink (шаг 3 по этой ссылке)</Anchor>

<div id="note-1" />

> 📘 **Примечание**
>
> Убедитесь, что пользовательский ключ `AF_xxxxxxxxx`, который вы ввели в [шаг 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#шаг-4-настройте-push-уведомлений-приложения) , имеет то же значение, что и в функции `addPushNotificationDeepLinkPath`.

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9HWK3F5TQZ8YQZBHGBZACPG=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9HWK5DM87JTDVFND0KB965G=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-salesforce-marketing-cloud-mobilepush=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-sdkmobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-sdkmobilepush step-2-provision-for-push-notifications=%D1%88%D0%B0%D0%B3-2-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9 h_01H9HWK3F5RNCZG340E0CT5XJC=%D1%88%D0%B0%D0%B3-2-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9 step-3-enable-app-push-notifications=%D1%88%D0%B0%D0%B3-3-%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B8%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK3F5E4W8FG35V4JTFN7F=%D1%88%D0%B0%D0%B3-3-%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B8%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F step-4-set-up-app-push-notifications=%D1%88%D0%B0%D0%B3-4-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK3F5K8V8AVADXNNG25GY=%D1%88%D0%B0%D0%B3-4-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK3F5VG2GBCE93B69AADH=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 step-5-set-up-push-notifications-in-appsflyer=%D1%88%D0%B0%D0%B3-5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=%D1%88%D0%B0%D0%B3-5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-push-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />
