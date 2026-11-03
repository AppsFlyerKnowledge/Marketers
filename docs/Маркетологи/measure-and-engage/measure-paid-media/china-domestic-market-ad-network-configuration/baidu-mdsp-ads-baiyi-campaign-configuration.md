---
title: Конфигурация кампании Baidu mDSP Ads (Baiyi)
metadata:
  keywords:
    - Advertisers
    - Baidu mDSP
    - Baiyi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-24T07:22:04Z'
  edited_at: '2026-09-17T00:26:10Z'
  id: 115004330446
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/115004330446
---
> **Кратко:** Baidu mDSP Ads (Baiyi) — партнер AppsFlyer, интегрированный как рекламная сеть, поставщик рекламных решений и часть Baidu, доминирующей поисковой системы в Китае с долей рынка более 70%.

## Настройка Baidu mDSP Ads (Baiyi)

1. В AppsFlyer в боковом меню выберите **Collaborate** **> Partner Integrations** > **Partner Marketplace**.
2. Найдите партнера и выберите его. Вы будете перенаправлены на страницу настройки интеграции.

Окно конфигурации Baidu mDSP Ads (Baiyi) включает 2 активные вкладки: Интеграция и ссылка атрибуции. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

### Активация партнера

При **первом посещении** необходимо включить кнопку ***Активировать партнера***, чтобы включить настройку параметров вкладки интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Baidu mDSP Ads (Baiyi) после установок и повторных вовлечений пользователей. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

![baidu-mdsp-default-postbacks.png](https://files.readme.io/fdde731527468b9837efa2230c5416f3393024b8c4eec8b44339086a2f31b984-360002069005.png)

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе вы можете сопоставить события AppsFlyer с Baidu mDSP Ads (Baiyi) через постбэки.

![baidu-mdsp-in-app-events.png](https://files.readme.io/fa515fac11e82be11bb55bb9b198ac63681ecdb713f0f6537f4ca7bf0c60e5b1-360002069085.png)

1. Включите переключатель «Постбэки по внутренним событиям приложения».
2. Чтобы добавить в список событие, определенное в SDK, нажмите **Add Event** (Добавить событие).
3. Введите следующие параметры:

| Имя параметра | Description(Описание) |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или ID каждого события, определенные на стороне Baidu mDSP Ads (Baiyi).  <br />Получите соответствующий идентификатор ID события в Baidu mDSP Ads (Baiyi) и введите его в текстовое поле. |
| **Отправка данных о доходе** | **Флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, кроме параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, в том числе значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

На этой вкладке вы можете создавать ссылки атрибуции, которые хотите отправлять в Baidu mDSP Ads (Baiyi) для атрибуции кампаний, групп объявлений и даже отдельных объявлений Baidu mDSP Ads (Baiyi). Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Кампания** — добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в Baidu mDSP Ads (Baiyi).  
  **Параметр ссылки атрибуции:** c
* **Adset** - задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний Baidu mDSP Ads (Baiyi).  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** - задайте названия объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний Baidu mDSP Ads (Baiyi).  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки конкретным паблишерам. Если у вас много паблишеров, рекомендуем ограничить количество используемых идентификаторов ID сайтов и использовать параметр идентификатора ID подсайта, чтобы избежать <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превышения лимита идентификатора ID сайта</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** - используйте любой из 5 параметров подписчика, чтобы вставить полезные значения. Обратите внимание, что эти параметры анализируются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

### Атрибуция по кликам

Этот ползунок позволяет задать **максимальное время от клика до установки**. К Baidu mDSP Ads (Baiyi) могут быть атрибутированы только те установки (первые запуски), которые произошли в пределах окна атрибуции/лукбэка.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции кликов см. здесь</Anchor>.

![baidu-mdsp-click-through.png](https://files.readme.io/19f6616cc1e62ec8888a72625ce936acdb6e8e63e4a4cd4273cdc99fd2297a93-360002075089.png)

### Ссылка атрибуции для клика

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в Baidu mDSP Ads (Baiyi), чтобы она активировалась, когда потенциальные клиенты нажимают на соответствующее объявление.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Интеграция затрат недоступна для Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

В Baidu mDSP Ads (Baiyi) интеграция доходов от рекламы недоступна.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Настройка разрешений недоступна для Baidu mDSP Ads (Baiyi).

</Accordion>

## Создайте правило конверсии в Baidu mDSP Ads

Войдите в Baidu mDSP Ads по адресу http://baiyi.baidu.com/ и перейдите в **Tool** >> **Apps**:

![mDSP_4.png](https://files.readme.io/90f99229f6bffe9b9edbf0469f9b4e66ca9c5c55184eb542e250ef6a9bd76aee-115014006086.png)

Нажмите **Create New App**.

![mDSP_5.png](https://files.readme.io/c034e3238fbd6021fefc44ff8b1cf8b4d39c3f9043b02074c3bdccce2747ac48-115014006106.png)

Введите в поля всю необходимую информацию.

Добавьте **ссылку атрибуции AppsFlyer в поле Feedback URL**:

![mDSP_6.png](https://files.readme.io/6692275131ee49b62febcb558457f7f1a1fbd167f3d3f61d976e1cb248a61388-115014006906.png)

***ПРИМЕЧАНИЕ***: Для приложений iOS добавьте приложение, введя **Appid**. Для приложений Android приложение можно добавить двумя способами:  
1. Подключение к приложению, которое вы загрузили на платформу Baidu для разработчиков ([http://app.baidu.com/](http://app.baidu.com/)), или  
2. Перейдите на страницу загрузки APK или загрузите APK там.

Затем нажмите кнопку отправки в нижней части страницы.

**3. Создайте рекламу для продвижения приложения в Baidu mDSP Ads**.

Нажмите **Campaign Management** >> **Create New Campaign**:

![mDSP_7.png](https://files.readme.io/aab8866a1969e403247c97018aae1d65d456ce4e261412035ef91a1862f509b9-115014006926.png)

В разделе **2. &lt;0>Настройте рекламный блок** >> перейдите к разделу **Цели**, выберите «Установка приложения»>> укажите остальные необходимые данные и отправьте рекламную кампанию на проверку:

![mDSP_8.png](https://files.readme.io/da064e6811b4c749a20757d711186dc705070629887cdf2e7b514cc17274af75-115014006946.png)

<div data-zendesk-anchors="setting-up-baidu-mdso-ads-baiyi=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-baidu-mdsp-ads-baiyi h_01HKW6TN4YBTMR1ZDH77D7SK7N=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-baidu-mdsp-ads-baiyi h_01HKW6TN4YM927W1VAKNWFQ0SJ=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6TN4Y4EXABZTJ2VE4QRTK=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6TN4YYDKNGCSJB4MARK52=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6TN4Y2D2K419172AZJXR6=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6TN4YQTMGSMPGR01FR658=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6TN4Y9ZP7SXMTD0XGNPGV=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6TN4Y5A1PT6RCVCFYRG9Q=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6TN4Z02V726B7379TMBC0=cost-tab h_01HKW6TN4Z01YZWHMGF5N1KC50=ad-revenue-tab h_01HKW6TN4Z3KCEFDW9YA2A2BZV=permissions-tab create-conversion-rule-at-baidu-mdsp-ads=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2-baidu-mdsp-ads h_01HKW6TN4ZWEA7683C8MFAT4AY=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2-baidu-mdsp-ads" />
