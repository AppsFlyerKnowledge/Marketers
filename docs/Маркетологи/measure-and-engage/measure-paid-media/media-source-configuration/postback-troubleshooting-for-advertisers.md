---
title: Устранение неполадок с постбэками для рекламодателей
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-09-23T00:14:30Z'
  id: 14272573202833
  locale: ru
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ru/articles/14272573202833
---
> **Краткий обзор.** Найдите основные причины и решения того, почему ваш партнер не получает ожидаемых постбэков. Просмотрите каждую из приведенных ниже тем и выясните, могут ли они быть причиной.

<div id="check-the-integration-toggles" />

## Проверьте переключатели интеграции

Различные переключатели управляют различными частями интеграции. Состояние переключателя может быть причиной того, что постбэки не приходят.

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Активация партнера выключена">

Когда переключатель <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">**Активировать партнера**</Anchor> выключен, конверсии не атрибутируются, а постбэки не отправляются партнерам.

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**Чтобы активировать интеграцию:**

1. В AppsFlyer в боковом меню выберите **Сотрудничество**> **c**
2. Нажмите значок управления интеграцией партнера.
3. На вкладке **Интеграция** включите переключатель **Активировать партнера**.

Другой случай может быть, если переключатель <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">**Активировать партнера**</Anchor> в настоящее время включен, но во время события он был выключен. Используйте журнал аудита, чтобы проверить, была ли партнерская интеграция активна во время события:

* <span id="1703758710.321359"></span>Перейдите к электронной почте пользователя (вверху справа) > **Центр безопасности** > **Журнал аудита**.

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="Постбэки по внутренним событиям приложения выключены">

Переключатель **<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration">Постбэки по внутренним событиям приложения</Anchor>** выключен, или он мог быть выключен во время события. Это означает, что постбэки не отправляются.

**Чтобы включить постбэки по внутренним событиям приложения:**

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции с партнерами** > **Активные интеграции.**
2. Нажмите значок управления интеграцией партнера.
3. На вкладке **Интеграция** прокрутите вниз до переключателя **Постбэки по внутренним событиям приложения** и включите его.

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

<div id="check-the-event-configuration" />

## Проверьте настройку событий

Событие может быть настроено таким образом, что определенные постбэки не будут отправляться.

<div id="the-event-wasnt-configured" />

<Accordion title="Событие не настроено">

Проверьте, что событие включено в список настроенных внутренних событий приложения. Если оно не определено, постбэк не отправляется.

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции с партнерами** > **Активные интеграции.**
2. Нажмите значок управления интеграцией партнера.
3. На вкладке **Интеграция** прокрутите вниз до раздела **Постбэки по внутренним событиям приложения** и посмотрите, появляется ли название события.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="Событие настроено неправильно">

Проверьте правильность <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#сопоставление-событий">сопоставления событий</Anchor>. Постбэки для событий после этого периода не отправляются партнеру, хотя события по-прежнему регистрируются в AppsFlyer.

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="Событие настроено правильно, но с условием">

Если для события определено условие, то постбэк отправляется в соответствии с условием. Проверьте, есть ли условие, ограничивающее отправку постбэка.

[![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="Событие настроено на отправку постбэков только атрибутированному партнеру">

Проверьте, настроена ли конфигурация событий в приложении на отправку постбэков <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#опции-для-отправки-постбэков">**Только этому партнеру** или на **Все медиа-источники и органический трафик**</Anchor>. Если установлено **Только этому партнеру**, только атрибутированный партнер получает постбэк.

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="Событие произошло за пределами окна конфигурации">

Постбэки отправляются в соответствии с настройками <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">окна постбэка</Anchor>. Постбэки для событий после этого периода не отправляются партнеру, хотя события по-прежнему регистрируются в AppsFlyer.

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

Обратите внимание, что для <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">SRN</Anchor> постбэки по внутренним событиям приложения отправляются в течение всего периода <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention#установленные-партнерами-сроки-хранения-данных">хранения данных партнером</Anchor>.

</Accordion>

<div id="privacy-restrictions" />

## Ограничения конфиденциальности

В следующих случаях AppsFlyer не отправляет постбэки из-за ограничений конфиденциальности.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="Партнер не поддерживает режим расширенной конфиденциальности или не настроил его">

Если <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Расширенная конфиденциальность</Anchor> включена, но партнер не настроил расширенную конфиденциальность на своей стороне или не поддерживает ее, он не будет получать <Anchor target="_blank" href="/partners/ru/docs/advanced-privacy-guide-postback-macros-for-ad-networks#типы-шаблонов-для-отправки-постбэков">агрегированные постбэки по расширенной конфиденциальности</Anchor>.

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Ограничения медиа-источников на сторонних платформах">

<Anchor target="_blank" href="/marketers/ru/docs/discrepancies-between-appsflyer-and-third-party-platforms#ограничения-постбэков-на-сторонних-платформах">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. AppsFlyer не может включить передачу сторонним платформам и сервисам данных на уровне пользователя, полученных через эти медиа-источники. Поэтому все установки из таких медиа-источников отправляются как органические. Обратите внимание, что Meta Ads не передает никаких данных сторонним платформам.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="SDK был настроен не предоставлять информацию партнеру">

Для предотвращения получения информации партнером в SDK реализован фильтр совместного доступа. Этот фильтр можно активировать как по явному запросу пользователя на отказ на предоставление данных, так и в любой другой момент жизненного цикла приложения.

Подробнее см: <Anchor target="_blank" href="/marketers/ru/docs/apply-privacy-preserving-sdk-methods#prevent-data-sharing-with-third-parties">Предотвращение передачи данных третьим лицам</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Разное

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="Постбэк был отправлен, но не отображается на платформе партнера">

В некоторых случаях, хотя AppsFlyer отправляет постбэк партнеру, на стороне партнера он не виден. В таких случаях необходимо связаться с партнером.

**Чтобы узнать, был ли отправлен постбэк из AppsFlyer:**

1. В AppsFlyer в разделе **Отчеты** перейдите в **Экспорт сырых данных**.
2. Просмотрите соответствующий отчет в разделе **Постбэки** (Установки, Внутренние события приложения, Конверсии ретаргетинга, Ретаргетинг внутренних событий приложения).

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="Событие не произошло или не было отправлено в AppsFlyer">

Все произошедшие события можно найти на <Anchor target="_blank" href="/marketers/ru/docs/activity-dashboard">дэшборде **Активность**</Anchor> и в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview?query=raw%20data%20reports">отчетах по сырым данным</Anchor>. Отсутствие события означает, что оно не произошло или не было отправлено в AppsFlyer.

Возможно, событие не было определено в SDK. В этом случае вы не увидите его на платформе. Проверьте конфигурацию SDK.  <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#регистрация-внутренних-событий-приложения">Определено в SDK</Anchor>.

Если вы считаете, что событие произошло, проверьте ниже, как посмотреть, появляется ли оно на дэшборде активности, или создайте отчет по сырым данным и поищите его там.

**Чтобы просмотреть дэшборд активности:**

* В AppsFlyer в разделе **Дэшборды** перейдите к **Активности** и выберите партнера и диапазон дат.

**Чтобы создать отчет по сырым данным:**

1. В AppsFlyer в разделе **Отчеты** перейдите в **Экспорт сырых данных**.
2. Нажмите **Создать отчет**.
3. Выберите соответствующий отчет.
4. Выберите диапазон дат и любые необходимые поля и нажмите **Создать**.
5. Скачайте отчет и поищите событие там.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Различия в часовых поясах">

Возможны расхождения в получении постбэков из-за разницы в часовых поясах между платформой AppsFlyer и платформой партнера. Дэшборды и отчеты AppsFlyer отображаются в соответствии с выбранным часовым поясом.

**Чтобы увидеть часовой пояс приложения в AppsFlyer:**

1. В AppsFlyer в разделе **Настройки** перейдите в **Настройки приложения**.
2. Посмотреть часовой пояс приложения можно в разделе **Локализация**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="В SRN отсутствуют рекламные идентификаторы (IDFA/GAID)">

Есть ряд <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">специфических случаев для SRN</Anchor>, в которых AppsFlyer не отправляет постбэки для установок, открытий приложений или внутренних событий.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="Ограничения медиа-источников на сторонних платформах">

<Anchor target="_blank" href="/marketers/ru/docs/discrepancies-between-appsflyer-and-third-party-platforms#ограничения-постбэков-на-сторонних-платформах">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. AppsFlyer не может включить передачу сторонним платформам и сервисам данных на уровне пользователя, полученных через эти медиа-источники. Поэтому все установки из таких медиа-источников отправляются как органические. Обратите внимание, что Meta Ads не передает никаких данных сторонним платформам.

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="Постбэки расширенной конфиденциальности">

Если включена расширенная конфиденциальность (AP), данные на уровне пользователя для пользователей, не давших согласие, на устройствах с iOS 14.5+ недоступны через постбэки. Постбэки отправляются в соответствии с <Anchor target="_blank" href="/partners/ru/docs/advanced-privacy-guide-postback-macros-for-ad-networks#типы-шаблонов-для-отправки-постбэков">шаблоном «Расширенная конфиденциальность»</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> <Anchor target="_blank" href="/partners/ru/docs/postback-troubleshooting-for-ad-networks">Поиск и устранение неисправностей в постбэках для рекламных сетей</Anchor>

<div data-zendesk-anchors="activation-toggles=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D0%BB%D1%8E%D1%87%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01H9FT385FY1QJC6M2YVMZF2NC=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D0%BB%D1%8E%D1%87%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D1%83-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9FT385FW71JV2KKZ22TP6TN=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D1%83-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window privacy-restrictions=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01H9FT385G84E2A1J64VWG8H4Z=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=%D1%80%D0%B0%D0%B7%D0%BD%D0%BE%D0%B5 h_01H9FT385GSWRPKEHKJ4HXCX01=%D1%80%D0%B0%D0%B7%D0%BD%D0%BE%D0%B5 h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
