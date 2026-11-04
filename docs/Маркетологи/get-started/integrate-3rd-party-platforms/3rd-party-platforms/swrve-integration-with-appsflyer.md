---
title: Интеграция Swrve с AppsFlyer
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
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
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-08-28T00:11:31Z'
  id: 207040656
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/207040656
---
> **At a glance:** Swrve, интегрированный партнер AppsFlyer, — это кроссплатформенный инструмент взаимодействия с клиентами, который позволяет рекламодателям обеспечивать для конечных пользователей таргетированные, персонализированные и оптимизированные взаимодействия:

* Динамическая оптимизация и тестирование основного контента приложения
* Кампании в приложении и кампании push-уведомлений
* Электронная почта

Наряду с AppsFlyer Swrve предоставляет комплексное решение для управления жизненным циклом, которое помогает максимизировать ROI от затрат на разработку и привлечение, а также обеспечивает превосходный пользовательский опыт на всем пути взаимодействия с мобильным приложением. Это включает настройку пользовательского опыта на основе источника привлечения, которым две платформы обмениваются между собой, что позволяет показывать пользователям контент, соответствующий их пользовательскому пути, с момента, когда они впервые открывают приложение.

Интеграция работает следующим образом: Swrve уведомляется об установках через их API с использованием их REST API. Для этого вам потребуется настроить серверный постбэк в вашей учетной записи AppsFlyer для каждого из ваших мобильных приложений.

> 🚧 **Important**
>
> **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="integrating-swrve-and-appsflyer" />

## Интеграция Swrve и AppsFlyer

Настройка постбэка, который позволяет Swrve измерять LTV и поведение пользователей для разных источников привлечения:

**Шаг 1**: После инициализации Swrve задайте идентификатор пользователя (до любых вызовов SDK AppsFlyer) следующим образом:

<Tabs>
<Tab title="Для Android">

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

</Tab>

<Tab title="Для iOS">

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

</Tab>

<Tab title="Для Unity">

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

</Tab>
</Tabs>

**Шаг 2**: Настройте постбэк в дэшборде AppsFlyer, выполнив следующие действия:

<div id="setting-up-swrve" />

## Настройка Swrve

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Окно настройки Swrve использует только вкладку **интеграция** .

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** этого раздела необходимо включить переключатель ***Активировать партнера***, чтобы настроить параметры на вкладке «Интеграция». Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**Идентификатор ID приложения и ключ API**

Swrve подключается к AppsFlyer через уникальный идентификатор ID приложения и ключ API. Если у вас их еще нет, вы должны получить их от Swrve, чтобы продолжить интеграцию.

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

При необходимости выполните следующие действия:

* Введите **APP\_ID**
* Введите **api\_key**
* Выберите **ЕС** для клиентов из ЕС
* Выберите **Расширенная передача данных**, чтобы отправлять в Swrve следующую дополнительную информацию: cost\_value, channel, keywords, siteID и c (кампания)

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Swrve после установки приложения пользователем. В этом разделе можно определить отправку этих постбэков.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Выберите **События, атрибутированные любому партнёру или органически**, чтобы отправлять постбэки в Swrve для любого пользователя, который загружает приложение.

Нажмите **Сохранить**.

После сохранения AppsFlyer начинает отправлять в Swrve следующие данные для каждой органической и неорганической установки:

* api\_key
* Идентификатор пользователя Swrve, заданный в SDK
* Источник медиа
* Название кампании

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Swrve.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Swrve.

</Accordion>

<div id="swrve-reporting-with-appsflyer-data" />

## Отчётность Swrve с данными AppsFlyer

После настройки серверных постбэков для отправки информации об атрибуции из AppsFlyer в Swrve вы сможете просматривать данные о привлечении на платформе Swrve и использовать весь набор функций таргетинга и тестирования Swrve.

На главной странице дэшборда вашего приложения представлена вся важная информация о приложении с первого взгляда. На этой странице вы можете продолжить использовать функции тестирования, таргетинга и отчётности, выбрав соответствующие вкладки на главной панели навигации.

![График привлечения на дэшборде Swrve](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)
![Таблица данных по привлечению на дэшборде Swrve](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="integrating-swrve-and-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-swrve-%D0%B8-appsflyer h_01H9HWK5DM1K9P5XXC6S7ENAGV=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-swrve-%D0%B8-appsflyer setting-up-swrve=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-swrve h_01H9HWK5DMS8HAK25BF5EXZT51=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9HWK5DN375XJVHQCZ8Y3K13=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9HWK5DN0XK2E0HXS61GRECE=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWK5DNH6SYY8T9NX09MRYS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-swrve-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-appsflyer h_01H9HWK5DN3QB9V593EV566GAQ=%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-swrve-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-appsflyer" />
