---
title: Настройка кампании Baidu Native Ads 2.0
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
  created_at: '2019-08-02T04:18:11Z'
  edited_at: '2026-09-17T00:26:13Z'
  id: 360002158958
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/360002158958
---
> **Кратко:** Baidu Native Ads 2.0 — рекламная сеть, интегрированный партнер AppsFlyer.

<div id="setting-up-baidu-native-ads-20" />

## Настройка Baidu Native Ads 2.0

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   **Важно:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Окно настроек Baidu Native Ads 2.0 включает 3 активные вкладки: Integration, Attribution link и Permissions. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка Integration (Интеграция)">

<div id="activate-partner" />

### Activate Partner (Активировать партнера)

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

Baidu Native Ads 2.0 подключается к AppsFlyer с помощью уникального **akey**. Если у вас еще нет ключа, вам необходимо получить его в Baidu Native Ads 2.0, чтобы продолжить интеграцию.

<Image alt="mceclip2.png" src="https://files.readme.io/fe8f44ee7d58fda9ee6289872903f96c716ab6d1191dd831745445cbced8b316-50899807435409.png" width="417px" />

<div id="default-postbacks" />

### Постбэки по умолчанию

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="552px" />

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе вы можете сопоставить события AppsFlyer с Baidu Native Ads 2.0 через постбэки. 

<Image alt="mceclip1.png" src="https://files.readme.io/1d929a3ba75da04165e416843f5037b8e299b12ae190aa9068cc3b317348087c-50899846627601.png" width="598px" />

1. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
2. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
3. Введите следующие параметры:

| Имя параметра | Описание |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор каждого события, определенные на стороне Baidu Native Ads 2.0.  <br />Получите соответствующий Event ID в Baidu Native Ads 2.0 и задайте его в текстовом поле. |
| **Отправка данных о доходе** | **Если флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, в том числе значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

На этой вкладке вы можете создать ссылки атрибуции, которые хотите отправить в Baidu Native Ads 2.0 для атрибуции кампаний, групп объявлений и даже отдельных объявлений Baidu Native Ads 2.0. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Campaign** - добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в Baidu Native Ads 2.  
  **Параметр ссылки атрибуции:** c
* **Adset** - задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний Baidu Native Ads 2.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** - задайте названия групп объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний Baidu Native Ads 2.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — используйте параметр Site ID, чтобы атрибутировать установки определенным паблишерам. При наличии большого количества паблишеров рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить допустимое количество идентификаторов сайтов</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Параметры подписчика** — используйте любой из 5 параметров подписчика, чтобы подставить полезные значения. Обратите внимание, что эти параметры парсятся и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**структуре и параметрах ссылки атрибуции AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

Этот ползунок позволяет задать **максимальное время от клика до установки**. К Baidu Native Ads 2.0 могут быть атрибутированы только установки (первые запуски), которые происходят в течение окна ретроспективы.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по кликам см. здесь</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="attribution-link" />

### Ссылка атрибуции

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в Baidu Native Ads 2.0, чтобы она активировалась, когда потенциальные клиенты нажимают на соответствующее объявление.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка 'Cost' (Затраты)">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка 'Ad Revenue' (Доходы от рекламы)">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка 'Разрешения'">

Разрешения не поддерживаются при интеграции с этим партнёром.


</Accordion>

<div data-zendesk-anchors="setting-up-baidu-native-ads-20=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-baidu-native-ads-20 h_01HKW6TZKDHY5D1VZ5PB7VM2MC=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-baidu-native-ads-20 h_01HKW6TZKDRECSQTP2VSAZZ5V6=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6TZKDY6EEHMK5SJWBW0EH=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HKW6TZKDGFFMPSZGN8AZWA80=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6TZKDBAQRP63ST32NN4DN=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6TZKDYHPZXN0TC219XPA1=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6TZKEFVXGP11N8G4C6JTP=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6TZKE5GJV1ZSJTVPG668Q=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6TZKEWA482TABZ8651NPP=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6TZKEWJTMCK86JZN27R1F=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6TZKEX2JQQNA5JMQ40848=cost-tab h_01HKW6TZKE4N38GCTBK4VDNNF8=ad-revenue-tab h_01HKW6TZKEY7RSV934KZ6XRXM2=permissions-tab" />
