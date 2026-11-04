---
title: Интеграция Airship с AppsFlyer
metadata:
  keywords:
    - Attribution
    - SDK
    - Configure
    - urban airship
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-16T11:31:38Z'
  edited_at: '2026-08-28T00:10:08Z'
  id: 207033976
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/207033976
---
> **Кратко:** Airship — интегрированный партнер AppsFlyer — предоставляет ведущую в мире платформу мобильной вовлеченности, помогая тысячам компаний любого размера выстраивать прямую и долгосрочную связь со своими клиентами. С Airship компании получают полный контроль над своим мобильным присутствием — приложениями, кошельками и данными на уровне пользователя — чтобы предоставлять опыт, который привлекает внимание и стимулирует действия в мобильной среде и в любых других точках контакта с клиентами.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-airship" />

## Настройка Airship

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом посещении** этой страницы включите **Активировать партнера**, чтобы настроить параметры вкладки интеграции. **Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером**.  
    Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе:

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** этого раздела необходимо включить параметр **Активировать партнера**, чтобы настроить параметры на вкладке интеграции. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="general-settings" />

### Общие настройки

Airship подключается к AppsFlyer с помощью уникальных App Key и Token. Если у вас их еще нет, вы можете получить их в Airship, чтобы продолжить интеграцию, или ознакомьтесь с инструкциями ниже о том, как их получить.

![airship-integration-tab.png](https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png)

**Чтобы настроить интеграцию с Airship:**

Минимальные требования — AppsFlyer SDK:

* Android — версия 2.3.1.18 и выше
* iOS — версия 3.3.3 и выше

Минимальные требования — Airship SDK — версия 13.1.0 и выше.

1. Для интеграции с Airship необходимо, чтобы channelid (уникальный идентификатор пользователя Airship) был заполнен в SDK AppsFlyer.

   * [Подробнее об идентификаторе канала для iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   * [Подробнее об идентификаторе канала для Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

   Этот параметр отправляется с каждым постбэком и позволяет идентифицировать каждого пользователя. Для этого необходимо вставить в код приложения следующие строки:

   <div id="important-note" />

   > 📘 **Важное примечание**
   >
   > Убедитесь, что строки кода вставлены в правильное место: после запуска Airship SDK и до вызова метода start в iOS или Android.


   <Tabs>
   <Tab title="Android">

   Подробнее о методе  `setAdditionalData` — клик <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">здесь</Anchor>.

   ```java
   HashMap<String, Object> customData = new HashMap<String,Object>();
   String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId);
   AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   </Tab>

   <Tab title="iOS">

   Подробнее о методе  `setAdditionalData` — клик <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">здесь</Anchor>.

   ```objectivec
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```

   </Tab>
   </Tabs>

2. Получите App Key из Airship:
   1. Войдите в свой аккаунт Airship по адресу: [go.airship.com](http://go.urbanairship.com/)
   2. В меню слева перейдите в **Настройки>** **API &** **Интеграции**и нажмите **Airship API**.

      ![airship-appkey-en_us.png](https://files.readme.io/c33611035d8dcadb73e41a3787690726608bddde55edbc38f34990c03948985d-360017666917.png)
   3. Скопируйте ключ приложения.
   4. В AppsFlyer вставьте ключ приложения в поле «App Key».
3. Получите токен из Airship:
   1. Войдите в свою учетную запись Airship по адресу: [go.airship.com](http://go.urbanairship.com/)
   2. В меню слева перейдите в **Settings >** **APIs &** **Integrations** и нажмите **Tokens**.

      ![airship-token-creation-1.png](https://files.readme.io/b0c22d9844dbc93f7dd158a75916eca98404474a65be0c1528f83e6e4ac7b210-360017480697.png)
   3. Нажмите кнопку **Создать токен**.

      ![airship-token-creation-2.png](https://files.readme.io/656f6f5a6eebe3ccd1a786f6abec62739633e4150722fec41bc1fbdea78f8275-360017549138.png)
   4. Введите имя токена и выберите роль.
   5. Нажмите кнопку **Создать токен**.
   6. В AppsFlyer вставьте токен в поле **Token Authentication**.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может автоматически отправлять постбэки в Airship после установки пользователем и повторного вовлечения. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

![urban_airship_msc_new_3.png](https://files.readme.io/394dd47ff26742092f3012e333f137d706f41bc85cd6875013d792ce7f36b01d-360001900305.png)

Выберите **Events attributed to any partner or organic**, чтобы отправлять постбэки в Airship для любого пользователя, который загружает приложение.

После сохранения конфигурации AppsFlyer отправляет в Airship следующие данные для каждой органической и неорганической установки:

* Идентификатор устройства (IDFA / Рекламный идентификатор Google)
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки Атрибуции недоступны для Airship.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнером.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнером.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Airship.

</Accordion>

<div id="set-up-and-manage-the-attribution-data-in-airship-console" />

## Настройка и управление данными атрибуции в консоли Airship

В Airship атрибуты — это пары «ключ — значение», которые вы связываете со своими аудиториями, чтобы точнее нацеливать их сообщениями. Используйте атрибуты для более точного таргетинга аудиторий, чем с помощью тегов.

Настройте данные атрибуции AppsFlyer в Airship, [добавив отдельные атрибуты в свой проект](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration).

<div data-zendesk-anchors="h_01H9FJYKH3V1TZ4GYEKKG46F2S=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-airship=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-airship h_01H9FJYKH3SWMNC8CRPPDQMCGQ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-airship h_01H9FJYKH4KQMK2N5BTTFTY076=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FJYKH4NTCNVKBW9XSENFTP=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FJYKH4MMRE57BNEBD0P5NT=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FJYKH4H93Q5S41HK7S4RD6=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE%D0%B5-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FJYKH44F4YQSEPKTGN7EYK=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FJYKH44S8F34YJ97TE32PM=attribution-link-tab h_01H9FJYKH47DYTR8T197CEXH0Z=cost-tab h_01H9FJYKH46AC5X7F6GAD9MQJG=ad-revenue-tab h_01H9FJYKH4N4T5JTGWHQC0A18Z=permissions-tab set-up-and-manage-the-attribution-data-in-airship-console=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-airship h_01H9FJYKH4Q09JSBJ25RRE02Y3=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-airship" />
