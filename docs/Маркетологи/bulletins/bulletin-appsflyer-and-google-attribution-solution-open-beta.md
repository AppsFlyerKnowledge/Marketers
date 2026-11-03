---
title: 'Бюллетень: решение AppsFlyer и Google для атрибуции [открытая бета]'
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
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-19T14:38:12Z'
  id: 37857301293457
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/37857301293457
---
<Embed title="Видеоплеер YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| Раздел | Подробности |
| --- | --- |
| **Что нового** | Решение Google Integrated Conversions Measurement (ICM) будет доступно всем клиентам, которые используют Google Ads для измерения установок и реатрибуции. |
| **Ориентировочная дата запуска открытой бета-версии:** | <ul><li>**iOS** – открытая бета-версия (с 12 ноября) — доступно для всех приложений.</li><li>**Android** – открытая бета-версия (с 5 декабря 2025 г.) — доступно для всех приложений.</li></ul> |
| **Что важно знать** | <ul><li>ICM позволяет AppsFlyer выполнять атрибуцию установок в Google Ads без идентификаторов устройств, используя методы, сохраняющие конфиденциальность.</li><li>Google отправляет в AppsFlyer недетерминированные заявления об установках.<br />Если данные AppsFlyer подтверждают эти заявления, они используются для атрибуции. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#процесс-атрибуции-google-ads-с-расширенным-обменом-данными">процесс атрибуции Google Ads с расширенным обменом данными</Anchor>.</li></ul> |
| **Что необходимо сделать:** | <ul><li>**Требования к SDK:**<ul><li>**iOS:** Требуется AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK версии 6.17.9</Anchor> или более поздней *и* либо Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK версии 11.14.0</Anchor> или более поздней, либо отдельный <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>.</li><li>**Android:** обновление SDK не требуется.</li></ul></li><li>**Переключатель расширенного обмена данными:** новая настройка в интеграциях `googleadwords_int` для iOS и Android:<ul><li>Если **включено**: AppsFlyer будет отправлять в Google все события установок, даже без идентификатора устройства.</li><li>Если **отключено**: будут передаваться только события установок с доступным идентификатором устройства или GCLID, что снижает эффективность ICM.</li></ul></li><li>**Важно (только iOS):** ICM недоступно для трафика от пользователей из Европейской экономической зоны (ЕЭЗ), Великобритании и Швейцарии.</li></ul> |