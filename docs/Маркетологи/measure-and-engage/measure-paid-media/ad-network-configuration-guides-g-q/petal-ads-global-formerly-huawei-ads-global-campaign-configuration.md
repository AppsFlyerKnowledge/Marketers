---
title: Настройка кампании Petal Ads Global (ранее HUAWEI Ads Global)
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - huawei
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
  created_at: '2020-06-28T08:40:00Z'
  edited_at: '2026-09-12T00:24:33Z'
  id: 360010605858
  locale: ru
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ru/articles/360010605858
---
> **Кратко:** Petal Ads Global, интегрированный партнер AppsFlyer, — это платный сервис размещения рекламы, предоставляемый Huawei панэкосистемным партнерам. Он помогает партнерам наладить взаимодействие с пользователями устройств Huawei, чтобы предоставлять им ценную информацию и качественные услуги. Petal Ads Global предоставляет места для показа основных форматов рекламы, таких как нативная реклама, реклама с вознаграждением за просмотр видео, баннерная реклама и межстраничная реклама, более чем 570 миллионам пользователей устройств Huawei по всему миру.

<Image align="center" alt="huaweiadsglobal.png" src="https://files.readme.io/12f1351923768c1afc1ba0f16b267388a8c9b1ae7fc2d6d36b5d1d01381f1bbc-14151449726353.png" width="18.53%" />

<div id="petal-ads-global-introduction" />

## Обзор Petal Ads Global

Petal Ads Global интегрирован в несколько сторонних приложений и приложений Huawei, таких как HUAWEI Browser, HUAWEI Video, HUAWEI Assistant, HUAWEI Reader и HUAWEI Music, которые являются субпаблишерами медийной сети Petal Ads Global. Кроме того, стандартные рекламные места AppGallery и App Gallery Search Ads также поддерживают атрибуцию AppsFlyer.

<div id="setting-up-petal-ads-global" />

## Настройка Petal Ads Global

Для атрибуции в Petal Ads Global требуется использовать **OAID** . Инструкции по получению OAID на устройствах HUAWEI см. в <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">**нашем руководстве по реализации OAID в Android SDK**</Anchor>. Кроме того, для приложений в HUAWEI AppGallery Petal Ads Global настоятельно рекомендуется использовать **атрибуцию по рефереру HUAWEI AppGallery**. Чтобы включить атрибуцию по рефереру HUAWEI, обновите Android SDK до версии 6.14.0 или более поздней.

| Источник трафика | Значение канала | Методы атрибуции | Примечание |
| --- | --- | --- | --- |
| Медийная реклама | huaweiadsglobal | Сопоставление по идентификатору (OAID или GAID), вероятностное моделирование, реферер Huawei | Нажмите <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">здесь</Anchor>, чтобы ознакомиться с руководством по внедрению OAID в Android SDK. Для атрибуции по рефереру Huawei требуется Android SDK 6.14.0 |
| App Gallery | huaweiappgalleryglobal | Сопоставление по идентификатору (OAID или GAID), реферер Huawei | Для атрибуции по рефереру Huawei требуется Android SDK 6.14.0 |
| Petal Search | пустое значение | Сопоставление идентификаторов (OAID или GAID), вероятностное моделирование | Нажмите <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">здесь</Anchor>, чтобы ознакомиться с руководством по внедрению OAID в Android SDK |

<div id="setting-up-the-petal-ads-global-integration" />

### Настройка интеграции с Petal Ads Global

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.  
   Чтобы отредактировать: Выберите **Совместная работа** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    **Обратите внимание:** Переключатель должен оставаться включённым (активированным) всё время, пока вы работаете с партнёром. Этот переключатель должен быть <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">включен</Anchor> все время, пока вы работаете с этим партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе. Для подробного описания заголовка окна для конфигурации партнера, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть несколько разделов:

<div id="activate-partner" />

#### Активация партнера

Чтобы включить конфигурацию, <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активируйте партнера</Anchor>.

Этот переключатель должен быть активирован все время, пока вы работаете с этим партнёром.

<div id="general-settings" />

#### Общие настройки

**Активация атрибуции по просмотрам**

Чтобы атрибутировать установки по просмотрам из Petal Ads Global, включите этот переключатель. Слайдер окна атрибуции по просмотрам доступен на вкладке **Ссылка атрибуции**.

<div id="default-postbacks" />

#### Постбэки по умолчанию

Отправляйте автоматические постбэки в Petal Ads Global только после установок пользователей, атрибутированных к Petal Ads Global. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

<div id="in-app-events-settings" />

#### In-App Events Settings (Настройки внутренних событий приложения)

Настройте постбэки событий в приложении, которые отправляются в Petal Ads Global.

**Чтобы настроить постбэки для внутренних событий приложения:**

1. Включите **постбэки событий в приложении**.
2. Установите <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">**окно постбэка для событий в приложении**</Anchor>.
3. Чтобы добавить событие SDK в список, нажмите **Добавить событие**.
4. Для каждого события выберите следующие параметры:

| Название параметра | Description(Описание) |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, активируйте его на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Введите уникальное имя или идентификатор каждого события, как определено в Petal Ads Global. Выберите наиболее подходящее предопределенное событие из 68 вариантов для вашего события SDK, например:<ul><li>`browse` (просмотр)</li><li>`collection` (добавление в избранное)</li><li>`addToCart` (добавление в корзину)</li><li>`preOrder` (оформление заказа)</li><li>`register` (регистрация)</li><li>`retain` (удержание на следующий день)</li><li>`paid` (совершена оплата)</li><li>`custom` (событие пользовательского типа)</li></ul> |
| **Sending option (Вариант отправки)** | Постбэки можно отправлять только для событий, выполненных пользователями, атрибутированными к Petal Ads Global. |
| **Отправить данные о событии** | <ul><li>**Нет значений & нет дохода:** Отправляется только само событие без значения события.</li><li>**Значения & без дохода:** Отправьте все параметры, кроме значения дохода.</li><li>**Значения & доход**: Отправьте все параметры события, включая значение дохода (если оно есть в событии).</li></ul> |

5. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Формируйте и сохраняйте ссылки атрибуции и отправляйте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>.

**Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этим инструкциям</Anchor>.  
При создании ссылки атрибуции выберите параметры из списка ниже и сопоставьте их с названиями параметров Petal Ads Global, приведенными в таблице.

**Параметры ссылки атрибуции**

| Параметр | Название параметра | Глобальный макрос рекламы Petal Ads | Description(Описание) |
| --- | --- | --- | --- |
| кампания; | c  <br />af\_c\_id | \_\_CID\_\_ | Добавьте, чтобы сравнивать различные кампании, запущенные в Petal Ads Global. |
| Блок рекламы | af\_adset  <br />af\_adset\_id | \_\_ADSETID\_\_ | Используется для различения наборов объявлений. |
| Рекламное объявление | af\_ad  <br />af\_ad\_id | \_\_ADID\_\_ | Используется для различения креативов в наборе объявлений. |
| Идентификатор сайта и идентификатор подсайта | af\_siteid  <br />af\_subsiteid | \_\_SITEID\_\_ | Используется для атрибуции установок конкретным паблишерам.<br /><br />**Полезный совет!** Если паблишеров несколько,<ul><li>Ограничьте количество используемых идентификаторов сайта.</li><li>Используйте параметр subsite ID, чтобы избежать <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превышения лимита идентификатора ID сайта</Anchor>.</li></ul> |
| Канал | af\_channel | \_\_CHANNEL\_\_ | Используется для различения мест размещения рекламы.<br /><br />huaweiadsglobal<br /><br />huaweiappgalleryglobal<br /><br />Если значение пустое, используется реклама в Huawei Search Ads. |
| Параметры подписчика | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 |  | Используется для вставки дополнительных полезных значений.<ul><li>Параметры анализируются и включаются в отчет о сырых данных.</li><li>Используйте их для агрегации данных или фильтрации.</li></ul> |
| Тип объявления | af\_ad\_type | \_\_APP\_STATUS\_\_ | используется для определения того, было ли приложение активировано ранее.<ul><li>если кампания используется для таргетинга на пользователей, которые установили приложение, но ни разу его не открывали, параметр будет иметь значение</li></ul>af\_ad\_type=installed<ul><li>если кампания используется для таргетинга на пользователей, которые никогда не устанавливали приложение, параметр будет иметь значение</li></ul>af\_ad\_type=notinstalled |

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о затратах не поддерживаются этим партнером.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Этот партнер не поддерживает данные о доходах от рекламы.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке вы можете выбрать разрешения для предоставления Petal Ads Global. Обратите внимание: даже если атрибуция для Petal Ads Global отключена, вкладка разрешений активна, и вы можете предоставить управление Petal Ads Global.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">Узнайте больше о том, как предоставить разрешения Petal Ads Global.</Anchor>

</Accordion>

<div id="configuring-campaigns-on-petal-ads-global" />

## Настройка кампаний в Petal Ads Global

**Чтобы настроить атрибуцию AppsFlyer в Petal Ads Global,** [**нажмите здесь**](https://developer.huawei.com/consumer/en/doc/distribution/promotion/appsflyer-0000001122291488)**, чтобы узнать больше в Центре поддержки Huawei.**

1. <span id="EN-US_TOPIC_0000001122291488__li7712141055015"></span><span id="EN-US_TOPIC_0000001122291488__en-us_topic_0000001122291488_ol75772831710"></span>Получите URL-адреса отслеживания показов и кликов в AppsFlyer.
2. Свяжите AppsFlyer с Petal Ads Global.
3. Настройте постбэк данных в AppsFlyer.
4. Создайте конверсию в Petal Ads Global.
5. Протестируйте конверсию в Petal Ads Global.
6. Создайте рекламную задачу в Petal Ads Global.
7. [Просмотрите данные конверсии](https://developer.huawei.com/consumer/en/doc/distribution/promotion/tracking-shu-0000001139892541) в Petal Ads Global.

<div id="data-discrepancies" />

## Расхождения в данных

**Примечание：** На дэшборде Petal Ads Global данные конверсии (например, установки/активации) поступают из 2 источников: AppsFlyer и HMS. Если вы хотите сравнить данные, например по установкам, между AppsFlyer и дэшбордом Petal Ads Global, выберите на дэшборде Huawei пункт 'Activations', а не 'Activations(HMS)'.

<Image align="center" alt="" src="https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png" />

<div id="data-reporting-on-petal-ads-global-and-faqs-of-data-discrepancy" />

#### Отчетность в Petal Ads Global и часто задаваемые вопросы о расхождениях в данных

| метрику | Источник данных | Часто задаваемые вопросы | Description(Описание) |
| --- | --- | --- | --- |
| Версия SDK от AppsFlyer | Huawei | Показы Huawei &lt; показы AF | AppsFlyer фиксирует все показы, которые Huawei отправляет в AF, а Petal Ads Global перед отображением показов на дэшборде Petal Ads Global выполняет дополнительную обработку данных. |
| клики; | Huawei | Клики Huawei &lt; клики AF | AppsFlyer фиксирует все клики, которые Huawei отправляет в AF, а Petal Ads Global перед отображением кликов на дэшборде Petal Ads Global выполняет дополнительную обработку данных. |
| Загрузки | Huawei | н/д | В AF этой метрики нет. |
| Активации | Activations поступают из AppsFlyer; Activations HMS — из Huawei | Активации Huawei > установки AF | Активации в Huawei соответствуют установкам в AF. Расхождение в данных связано с разной логикой отчетности. <br /><br />Например, пользователь загрузил приложение из AppGallery 24 декабря и впервые открыл его 25 декабря. В этом случае AF зафиксирует установку 25 декабря, а Petal Ads Global зафиксирует эту активацию 24 декабря. |
| Удержание Day2 и другие события в приложении | Для вариантов, отличных от HMS, источником данных является AppsFlyer. | Huawei > AF | Расхождение в данных связано с разной логикой отчетности. <br /><br />Продолжая пример выше: пользователь зарегистрировался в приложении 26 декабря. Обзорный дэшборд AF покажет данные о регистрации за 25 декабря — так же, как и дату установки. В то время как промодэшборд Petal Ads Global покажет регистрацию за 24 декабря — дату загрузки. |

<div data-zendesk-anchors="huawei-ads-introduction=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-petal-ads-global h_01HJQZWW4SH5E9C3VXYM6NNPBA=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-petal-ads-global setting-up-huawei-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-petal-ads-global h_01HJQZWW4SQ3CDC1TP9NZGQHH5=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-petal-ads-global setting-up-the-petal-ads-global-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-petal-ads-global h_01HJRA1NPKF36ZV8AB3PKGWMXS=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-petal-ads-global h_01HJQZWW4SPFQAKKPJCZ38YNV4=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HJQZWW4TR0XVYFYWPGAQ2FMX=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HJQZWW4T9QYECWJKFN8SV5D5=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HJQZWW4T62ZJSH1RBGJSC8MY=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HJQZWW4T44X5H42KAR432VN7=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HJQZWW4T7TEZ27VRFPFY7DKA=attribution-link-tab h_01HJQZWW4TGDKCV8Q7B80Y5ZWG=cost-tab h_01HJQZWW4T384J7GVEEJ2EQZ0N=ad-revenue-tab h_01HJQZWW4T2P0NZ51TSF8VDEBP=permissions-tab configuring-campaigns-on-huawei-ads-global=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-petal-ads-global h_01HJQZWW4TEX7SDZSG03AK51H9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-petal-ads-global data-discrepancies=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HJQZWW4VNTKP5R4KYWX80P5P=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 data-reporting-on-huawei-ads-and-faqs-of-data-discrepancy=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B2-petal-ads-global-%D0%B8-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%BE-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HJQZWW4VZV1R32TMGGEVNCVA=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B2-petal-ads-global-%D0%B8-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%BE-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85" />
