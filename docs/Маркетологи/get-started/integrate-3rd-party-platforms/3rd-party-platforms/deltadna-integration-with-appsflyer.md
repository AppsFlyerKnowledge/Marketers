---
title: deltaDNA integration with AppsFlyer
metadata:
  keywords:
    - deltaDNA
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
  created_at: '2016-09-04T06:41:51Z'
  edited_at: '2026-09-12T00:10:36Z'
  id: 212247706
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/212247706
---
> **At a glance:** deltaDNA — интегрированный партнер AppsFlyer и ведущая платформа аналитики в реальном времени и маркетинга для мобильного гейминга. Сочетание ведущих на рынке функций работы с глубокими данными, сверхвысокой производительности и гибкой открытой среды позволяет пользователям максимизировать вовлеченность и пожизненную ценность за счет сегментации игроков, прогнозного моделирования и таргетированных вмешательств в реальном времени.

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="integrating-with-deltadna" />

## Интеграция с deltaDNA

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> Идентификатор userID в deltaDNA SDK, созданный автоматически или переданный игрой, должен быть задан в AppsFlyer SDK как идентификатор пользователя клиента, чтобы данные атрибуции, полученные от AppsFlyer, применялись к нужному пользователю. Это необходимо делать только в сборках игры, интегрированных со средой LIVE на стороне deltaDNA.

1. Если вы используете собственный идентификатор пользователя и передаете его как в параметре AppsFlyer custom\_user\_id, так и в параметре пользователя deltaDNA, дополнительная реализация в коде не требуется.
2. Если вы не используете собственный идентификатор пользователя, необходимо взять свойство userID из deltaDNA и использовать его в SDK AppsFlyer в параметре **customer\_user\_id**. Следующий код следует реализовать после инициализации обоих SDK.

<Tabs>
<Tab title="Android;">

```java
AppsflyerLib.getInstance().setCustomerUserId(DDNA.instance().getUserId())
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = [DDNASDK sharedInstance].userID;
```

</Tab>

<Tab title="Unity">

```swift
AppsFlyer.setCustomerUserID (DDNA.Instance.UserID)
```

</Tab>
</Tabs>

Чтобы настроить интеграцию с deltaDNA, следуйте инструкциям ниже

**В deltaDNA:**

1. Создайте в deltaDNA событие AppsFlyerAttribution с помощью инструмента Event Management

![Delta DNA 1](https://files.readme.io/e5224bbaa730d997699e1a930425946f69a2b86ef94e241b4ba6fdb9ad978c66-206781083.png)

2. Получите ключ Live environment на странице Game Details в дэшборде deltaDNA:

![Delta DNA 2](https://files.readme.io/6b28184264dfd695000e8bfae9538862a3e17ea6f9d355af0996ccf107b4e6c2-206768886.png)

**В AppsFlyer активируйте или отредактируйте интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите вкладку **Collaborate** > **Partner Integrations > Marketplace**.  
   **Чтобы отредактировать**: В AppsFlyer в боковом меню выберите вкладку **Collaborate** > **Partner Integrations > Active Integrations**.
2. Найдите и выберите **deltaDNA**.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настройки интеграции.
4. На вкладке **Интеграция** выберите приложение для интеграции и включите **Активировать партнера**.  
   **Примечание:** Переключатель должен быть включен <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(активирован)</Anchor> в течение всего времени работы с партнером.
5. Введите Environment\_key, полученный в консоли deltaDNA (см. раздел 2).
6. Установите для параметра **Sending option** значение **All media sources, including organic**.
7. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

После сохранения конфигурации AppsFlyer отправляет в deltaDNA следующие данные для каждой органической и неорганической установки:

* Ключ среды
* Идентификатор пользователя
* Время установки
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.

> 📘 **Note**
>
> **Примечание:**
>
> deltaDNA отклоняет постбэки об установках из AppsFlyer, если не задан Customer User ID или UserID.

<div id="viewing-the-attribution-data-in-the-deltadna-console" />

## Просмотр данных атрибуции в консоли deltaDNA

Данные атрибуции, полученные от AppsFlyer, можно использовать для:

* Фильтрации графиков Measure
* Создания пользовательских дэшбордов и отчетов
* Проведения детального анализа
* Создавайте пользовательские сегменты игроков, чтобы настраивать таргетинг с помощью персонализированных кампаний и предложений.

Фильтр Acquisition Channel в верхней части всех графиков Measure, матриц удержания, а также предикторов LTV и Retention использует медиаисточник AppsFlyer и основан на нем.

![Delta DNA 3](https://files.readme.io/21cf4f1c8641351a1ecc200d8b95d7558b92f4daf38f49975601d996a0fcfb86-206781123.png)

AppsFlyer может отправлять в deltaDNA 8 параметров атрибуции для использования в анализе, отчетах и запросах. Все они имеют префикс **afAttr.**   
*Например. afAttrCampaign, afAttrAgency, afAttrMediaSource — соответственно для кампании, агентства и медиаисточника.*

Все параметры атрибуции перечислены в **appsFlyerAttribution**, добавленном на ваш экран управления событиями.

![Delta DNA 4](https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png)

Используйте их для создания пользовательских запросов и отчетов для анализа в любом из инструментов deltaDNA Analyze.

![Delta DNA 5](https://files.readme.io/f4b9d0320feb3990182a0c9a835a18565ba959fabf7269c45a4651506666f941-206768946.png)

<div data-zendesk-anchors="integrating-with-deltadna=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-deltadna h_01H9FK6N8V597T8AY0RF0H6CZW=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-deltadna viewing-the-attribution-data-in-the-deltadna-console=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-deltadna h_01H9FK6N8W8011X3JVG2EZ66H4=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-deltadna" />
