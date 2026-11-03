---
title: >-
  Применить решение для соблюдения Закона Китая о защите персональной информации
  (PIPL)
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-05-10T08:59:00Z'
  edited_at: '2026-10-19T14:25:24Z'
  id: 6031419375377
  locale: ru
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/ru/articles/6031419375377
---
> **Кратко:** повысьте гибкость, сохраняя возможность измерений с AppsFlyer и соблюдая требования PIPL.

## Фон

В конце 2021 года в Китае был принят Закон о защите персональной информации (PIPL), регулирующий сбор, использование и передачу персональных данных пользователей. Чтобы обеспечить клиентам дополнительную гибкость при использовании AppsFlyer и поддержать соблюдение правовых норм PIPL, следуйте пошаговым инструкциям, приведенным в этой статье.  
Решение AppsFlyer для PIPL основано на 3 принципах:

* Запретите SDK собирать идентификаторы устройств.
* Маскируйте и хешируйте IP-адреса событий SDK, событий S2S, а также кликов и показов.
* Включите аудит всех событий приложения на промежуточном сервере в Китае.

## Применение решения PIPL в AppsFlyer

В следующем разделе описаны действия, которые необходимо выполнить, чтобы применить решение AppsFlyer для PIPL.

**Чтобы применить решение PIPL:**

1. Запретите SDK собирать идентификаторы устройств. Убедитесь, что вы не отправляете AppsFlyer идентификаторы устройств ни для взаимодействий, ни для событий.
   * Для Android:
     * Установите для `setDisableAdvertisingIdentifiers` значение true
     * Установите для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor> значение false
     * Установите для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor> значение false
   * Для iOS:
     * Установите для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier">`disableAdvertisingIdentifier`</Anchor> значение true
     * Установите для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection">`disableIDFVCollection`</Anchor> значение true

   Обратите внимание, что настройка этих методов влияет на сбор идентификаторов не только в Китае. Чтобы отключить идентификаторы только для китайского рынка, необходимо реализовать пользовательскую логику.
2. Маскируйте и хешируйте клики и показы, используя специальные китайские домены для передачи этих событий в AppsFlyer.
   * Используйте следующие китайские домены для OneLink и ссылок атрибуции:
     * Для кликов на одной платформе — **hclicks.aflink.com** — не используйте подпись кликов. Убедитесь, что <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add">исключили приложение из подписи кликов</Anchor>.
     * Для показов на одной платформе — **himpressions.aflink.com**
     * Для кликов OneLink — **`{subdomain}`.onelnk.com**
   * Отправьте своему CSM список релевантных ID приложений и субдоменов OneLink.
   * Если вы используете смарт-баннеры:
     * <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">Отправьте AppsFlyer ключ сайта.</Anchor>
     * Используйте только `{subdomain}`.onelnk.com.
     * Внимание! Поскольку PIPL требует маскирования и хеширования IP-адресов, смарт-баннеры на основе правил геолокации не будут работать должным образом.
3. Маскируйте и хешируйте события SDK и S2S и передавайте их через релейный сервер в Китае
   * **События SDK:**  
     Укажите для событий SDK домен **hevents.appsflyer-cn.com**. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Инструкции для Android</Anchor>. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost">iOS instructions</Anchor>.  
     Использование этого домена гарантирует, что IP-адреса всех событий SDK будут маскироваться и хешироваться.
   * **События S2S:**  
     Для событий S2S используйте домен `api2.hevents.appsflyer-cn.com`, чтобы маскировать и хешировать IP-адреса, как указано ниже:
     * IP-адрес нужно преобразовать в двоичный формат, а затем замаскировать последние 2 цифры.
     * Замаскированный двоичный IP-адрес нужно преобразовать в текст, а затем хешировать по алгоритму sha256.

## Ограничения решения

В этом разделе описаны некоторые ограничения, которые накладывает решение PIPL.

* Решение S2S для API OneLink для создания коротких ссылок не поддерживается.
* Все идентификаторы устройств для всех взаимодействий должны быть хешированы.

<div data-zendesk-anchors="background=%D1%84%D0%BE%D0%BD h_01HQ5Y1W7M46BBJGEZZ5VEYW3K=%D1%84%D0%BE%D0%BD apply-pipl-solution-in-appsflyer=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-pipl-%D0%B2-appsflyer h_01HQ5Y1W7MRYYGJWJNWY7ZSY9S=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-pipl-%D0%B2-appsflyer solution-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F h_01HQ5Y1W7M39XRY607H4G7X0X4=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F" />
