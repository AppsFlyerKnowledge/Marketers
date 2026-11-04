---
title: Настройка кампании The Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2026-09-16T00:25:19Z'
  id: 360000894849
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/360000894849
---
> **Краткий обзор.** The Trade Desk, рекламная сеть – интегрированный партнер AppsFlyer, предлагает усовершенствованное решение для мобильной рекламы для создания стратегических, масштабируемых и интеллектуальных кампаний, отвечающих потребностям пользователей различных устройств. The Trade Desk предлагает мобильную атрибуцию по кликам, мобильную атрибуцию по просмотрам и ретаргетинг по кликам с возможностью записи в AppsFlyer.

<div id="setting-up-the-trade-desk-ttd" />

## Настройка The Trade Desk (TTD)

Выполните следующие шаги, чтобы включить измерение кампаний в AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Шаг 1: Определите события конверсии в TTD">

1. В левом меню вашей страницы рекламодателя TTD нажмите **DATA** (ДАННЫЕ).
2. В верхнем меню нажмите **Add App Data** (Добавить данные приложения).
3. На странице **Create App Data** (Создать данные приложения) заполните следующие поля:
   * **App Name** (Имя приложения): введите имя приложения.
   * **Operating System** (Операционная система): выберите либо **Android**, либо **iOS**.   
     **Примечание:** TTD поддерживает CTV как в версии для Android, так и для iOS.
   * **Tracking Vendor** (Поставщик отслеживания): выберите **AppsFlyer**.
   * **Events** (События): нажмите **ADD EVENT** (ДОБАВИТЬ СОБЫТИЕ), чтобы добавить события конверсии, и заполните поля:
     * **EVENT NAME** (ИМЯ СОБЫТИЯ): введите название события.  
       **Примечание.** Убедитесь, что имя написано точно так же, как в AppsFlyer, включая заглавные буквы, пробелы и символы.
     * [Необязательно] **DESCRIPTION** (ОПИСАНИЕ): Добавьте описание.
     * [Необязательно] **USAGE OF COLLECTED DATA** (ИСПОЛЬЗОВАНИЕ СОБРАННЫХ ДАННЫХ): выберите **Attribution** (Атрибуция). Этот вариант включает в себя как атрибуцию, так и ретаргетинг.
     * Чтобы добавить больше событий, нажмите **ADD EVENT** (ДОБАВИТЬ СОБЫТИЕ) и повторите процесс.
   * **Conversion Credit Source** (Источник приписывания конверсий): выберите, какому источнику атрибутировать конверсии: AppsFlyer или The Trade Desk.   
     **Внимание**:
     * Для измерения покупок на различных устройствах и в TTD выберите **The Trade Desk**.   
       Для получения целостного представления об измерениях не только в TTD выберите **AppsFlyer**.
     * Никогда не изменяйте этот выбор в ходе кампании.
     * Проверьте, что выбрали правильный источник, прежде чем нажать **CREATE APP DATA** (СОЗДАТЬ ДАННЫЕ ПРИЛОЖЕНИЯ). Вы не сможете изменить источник атрибуции конверсии во время кампании.
4. Нажмите **CREATE APP DATA** (СОЗДАТЬ ДАННЫЕ ПРИЛОЖЕНИЯ).

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Шаг 2: Определите события конверсии в AppsFlyer">

Чтобы AppsFlyer мог определять события конверсии и позволить вам отправлять постбэки о событиях в TTD, необходимо сначала [интегрировать TTD с AppsFlyer](/docs/the-trade-desk-campaign-configuration#интеграция-ttd-с-appsflyer) и настроить следующие параметры:

* Настройки интеграции (включая настройку постбэков о событиях)
* Ссылка атрибуции
* Разрешения

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Шаг 3: Сопоставьте определенные события конверсии из AppsFlyer">

1. В левом меню TTD нажмите **CAMPAIGNS** (КАМПАНИИ).
2. Прокрутите вниз до раздела **Campaigns** (Кампании) и выберите кампанию из списка.
3. Нажмите **Edit Reporting & Attribution** (Изменить отчетность и атрибуцию).
4. Нажмите **ADD CONVERSION DATA SOURCE** (ДОБАВИТЬ ИСТОЧНИК ДАННЫХ О КОНВЕРСИИ).
5. В разделе **CONVERSION DATA SOURCE** (ИСТОЧНИК ДАННЫХ О КОНВЕРСИИ) выберите или введите **AppsFlyer**. События AppsFlyer теперь сопоставлены с событиями TTD.
6. **КОНЦЕПЦИЯ КРОСС-ДЕВАЙС**:
   * Если в [Шаге 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Источник атрибуции конверсий) вы выбрали, чтобы конверсии атрибутировались TTD, выберите здесь **Household** , чтобы видеть конверсии во всех доступных каналах (например, в мобильных приложениях и CTV).
   * Если в [Шаге 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) вы выбрали AppsFlyer, выберите здесь **None** (Нет).
7. Нажмите **SAVE** (СОХРАНИТЬ).

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Шаг 4: Добавьте трекеры кликов и показов к креативам кампании">

На этом шаге вы добавите трекеры кликов и показов, созданные в AppsFlyer, к каждому креативу в TTD.

1. В разделе **CAMPAIGNS** (КАМПАНИИ) в левом меню TTD нажмите на **CREATIVES** (КРЕАТИВЫ) на верхней вкладке.
2. Выберите креатив из списка креативов, связанных с текущей кампанией.
3. Прокрутите вниз до раздела **Tracking** (Отслеживание).
4. Скопируйте из AppsFlyer [ссылку атрибуции по просмотрам](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) и вставьте её в поле 1x1 Pixel Impression Tracking URL-адрес.
5. Скопируйте ссылку атрибуции по кликам из AppsFlyer и вставьте её в поле click-Through URL-адрес.
6. Нажмите **SAVE CHANGES** (СОХРАНИТЬ ИЗМЕНЕНИЯ).
7. Повторите этот шаг для всех креативов, связанных с кампанией.

</Accordion>

<div id="note" />

> 📘 **Примечание**
>
> Если вы выбрали, чтобы конверсии атрибутировались TTD (в [Шаге 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), вы можете редактировать окна атрибуции:
>
> 1. В меню иконок справа на любой странице TTD нажмите на шестеренку, чтобы открыть **Advertiser Preferences** (Параметры рекламодателя).
> 2. Прокрутите вниз до раздела **Attribution Windows** (Окна атрибуции) и нажмите кнопку редактирования справа.
> 3. На странице **Manage Attribution Windows** (Управление окнами атрибуции) отредактируйте окна атрибуции:
>    * **De-duplication Windows** (Окна дедупликации): количество конверсий за определенный период времени.
>    * **Campaign Attribution Windows** (Окна атрибуции кампании): период времени от показа рекламы до конверсии.
> 4. Нажмите **SAVE** (СОХРАНИТЬ).

<div id="integrating-ttd-with-appsflyer" />

## Интеграция TTD с AppsFlyer

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

В окне настроек TTD есть три вкладки: Integration (Интеграция), Attribution link (Ссылка атрибуции) и Permissions (разрешения). Чтобы ознакомиться с настройками этих вкладок, нажимайте на названия пунктов ниже.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка 'Интеграция'">

<div id="activate-partner" />

#### Активация партнера

При первом входе вам нужно включить переключатель **Активация партнера**, чтобы настроить интеграцию. Переключатель должен оставаться во включенном положении все время, которое вы работаете с TTD.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации/деактивации партнеров</Anchor>.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Для приложений iOS появляется переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Включить режим расширенной конфиденциальности</Anchor>. Когда он включен, он ограничивает предоставление партнеру идентификаторов пользователей. Обратите внимание, что когда в настройках приложения включен переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Агрегированная расширенная конфиденциальность</Anchor>, то переключатель **Включить режим расширенной конфиденциальности** включен и заблокирован по умолчанию.

<div id="general-settings" />

#### Общие настройки

**Идентификатор трекера и рекламодателя**

The Trade Desk подключается к AppsFlyer посредством уникального сетевого идентификатора. Если у вас еще нет идентификаторов Tracker\_ID и advertiserid, необходимо получить их от The Trade Desk, чтобы продолжить интеграцию.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Активировать атрибуцию по просмотрам**

Включите переключатель **Активировать атрибуцию по просмотрам**, чтобы атрибутировать установки по просмотру от The Trade Desk. На вкладке «Ссылка атрибуции» (описана ниже) имеется слайдер окна атрибуции по просмотрам.

<div id="default-postbacks" />

#### Постбэки по умолчанию

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Автоматически отправляйте в The Trade Desk постбэки после осуществления пользователем установки и повторного вовлечения. В этом разделе можно определить источник пользователей, который позволяет отправлять постбэки.

* **Только этот партнер**: для событий, поступающих только от пользователей, атрибутированных к The Trade Desk.
* **Все источники, включая органические,** чтобы предоставлять в The Trade Desks отчеты о событиях всех пользователей, которые есть в вашей базе.

<div id="note-1" />

> 📘 **Примечание**
>
> Поскольку The Trade Desk — сеть, ориентированная на все установки, она предпочитает получать постбэки обо всех новых установках вашего приложения из любого источника и рекомендует выбрать **Все медиаисточники, включая органические** для отправки всех постбэков по установкам в The Trade Desk.

<div id="in-app-events-settings" />

#### In-App Events Settings (Настройки внутренних событий приложения)

Сопоставьте события AppsFlyer с TTD с помощью постбэков. Если отправка постбэков активирована, они будут включать отклоненные внутренние события (события, признанные несоответствующими по правилам таргетинга или заблокированные Protect360).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**Для настройки постбэков по внутренним событиям приложения:**

1. Введите **advertiserid** и **Tracker\_ID**.
2. Активируйте **постбэки по внутренним событиям**.
3. Если требуется, установите **окно постбэков по внутренним событиям** (подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">настройке окна постбэков по внутренним событиям</Anchor>).
4. Если доступно, выберите, как отправлять события: автоматически или вручную. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">отправке всех событий «как есть»</Anchor>.
5. Нажмите **Добавить событие**.
6. Заполните необходимые параметры.
7. [Необязательно] Нажмите<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы задать условия отправки определенных событий в приложении в TTD.  
   Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">условных постбэках по событиям в приложении</Anchor>.

| Имя параметра | Description(Описание) |
| --- | --- |
| **AppsFlyer event (Событие AppsFlyer)** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer**, затем нажмите **Добавить другое**. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий.</Anchor></li></ul> |
| **for users from (для пользователей от)** | Выберите вариант отправки для события.<ul><li>**Только этот партнер**: постбэки отправляются только в том случае, когда событие атрибутируется этому партнеру.</li><li>**Все медиа-источники, включая органические**: отправляйте постбэки для событий, атрибутированных любому партнеру, а также для органических событий.</li></ul> |
| **Включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Значения и доход**: отправлять все параметры события, **включая** значение дохода (если оно есть в событии).</li><li>**Значения без дохода**: передача всех параметров события, **кроме** значения дохода.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

Сгенерируйте и сохраните ссылки атрибуции и отправьте их в TTD, чтобы атрибутировать определенные кампании, блоки рекламы и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.

<div id="attribution-link-parameters" />

#### Параметры ссылки атрибуции

Добавление параметров в ссылку атрибуции позволяет проводить тщательный анализ. Кроме того, можно изменять уже заданные параметры ссылки атрибуции — добавлять их и вводить новые значения. При сохранении ссылки атрибуции сохраняются все параметры, настроенные на этой вкладке.

Выберите параметры, которые требуется добавить в ссылку атрибуции.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

<div id="default-parameters" />

#### Параметры по умолчанию

| Имя | Описание | Параметр |
| --- | --- | --- |
| ID сайта | Задайте параметр идентификатора сайта, чтобы атрибутировать установки конкретным издателям. При наличии большого количества издателей рекомендуется ограничить количество используемых идентификаторов сайтов и использовать идентификаторы подсайтов, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить допустимое количество идентификаторов сайтов</Anchor>. | af\_siteid |
| Название кампании | Добавьте название своей кампании, чтобы сравнить различные кампании, запущенные в TTD. | c |
| ID кампании | Добавьте идентификатор кампании. | af\_c\_id |
| ID блока рекламы | Добавьте идентификатор блока рекламы, чтобы сравнить эффективность всех ваших объявлений по блокам. | af\_adset |
| ID рекламы. | Добавьте идентификатор рекламного объявления. | af\_ad\_id |

Вы можете добавить дополнительные параметры в ссылку атрибуции. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">настройке ссылки атрибуции</Anchor> и о <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">структуре и параметрах</Anchor> ссылки атрибуции.

<div id="parameters-for-measuring-ctv" />

#### Параметры для измерения CTV

Для измерения трафика CTV в AppsFlyer можно добавить следующие параметры и значения:

| Параметр | Значение | Комментарии |
| --- | --- | --- |
| перенаправление | = false\` |  |
| af\_xplatform\_vt\_lookback | 1h-72h | Можно ввести любое значение в диапазоне 1-72 часа |

<div id="click-through-attribution" />

#### Атрибуция по кликам

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

На этой шкале можно задать максимальное время от клика до установки. Атрибуция производится только для установок (первых запусков), которые произошли в течение окна атрибуции.

Диапазон окна атрибуции: 1–23 часов или 1–30 дней.

Параметр ссылки атрибуции: af\_click\_lookback

Узнать больше об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции для кликов</Anchor>.

**Ссылка атрибуции по кликам:** содержит все параметры, которые вы включили при настройке ссылки атрибуции. Вы можете скопировать ссылку и отправить ее партнеру, чтобы она активировалась, когда ваши лиды кликнут по соответствующему объявлению.

<div id="view-through-attribution" />

#### Атрибуция по просмотрам

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Используйте ползунок, чтобы установить максимальное время от показа до установки. Только установки (первые запуски), которые происходят в это окно атрибуции после показа рекламы, приписываются партнеру, если не было других соответствующих кликов по рекламе.

Диапазон окна атрибуции: 1–24 часа.

Параметр ссылки атрибуции: af\_viewthrough\_lookback

Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">атрибуции по просмотрам</Anchor>.

**Ссылка атрибуции по просмотрам:** содержит все параметры, которые вы включили при настройке ссылки атрибуции. Вы можете скопировать ссылку и отправить ее партнеру, чтобы она активировалась, когда ваши лиды кликнут по соответствующему объявлению.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Интеграция затрат недоступна для The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка 'Ad Revenue' (Доходы от рекламы)">

Доходы от рекламы недоступны для The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения для The Trade Desk в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и другое. Обратите внимание, что, даже если атрибуция для The Trade Desk отключена, вкладка разрешений остается активной, и вы можете предоставить The Trade Desk разрешение на управление.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Эти переключатели позволяют предоставить рекламной сети право самостоятельно выполнять настройки для вашего приложения:

<div id="ad-network-permissions" />

#### **Ad Network Permissions (Разрешения для рекламной сети)**

* **Разрешить настраивать интеграцию:** разрешите TTD настраивать вкладку интеграции, за исключением постбэков по внутренним событиям.
* **Разрешить настройку постбэков по внутренним событиям:** разрешите TTD настраивать сопоставление постбэков по внутренним событиям на вкладке интеграции.
* **Разрешить доступ к отчету об удержании:** только для собственных данных TTD об удержании.
* **Разрешить доступ к агрегированным данным по вашим лояльным пользователям:** только для данных по лояльным пользователям TTD.
* **Разрешить доступ к агрегированным данным о внутренних событиях приложения**: TTD получает доступ только к собственным данным о внутренних событиях.
* **Разрешить доступ к агрегированным данным о доходах**: TTD получает доступ к данным только по атрибутированным ему доходам.
* **Разрешить доступ к дэшборду Protect360**: TTD получает доступ только к собственным данным Protect360, при условии что вы активировали эту функцию.

См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешений рекламной сети</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-the-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-the-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 integrating-ttd-with-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-ttd-%D1%81-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-ttd-%D1%81-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HH2DHQWYME21J7JV176N71P2=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HH2DHQWYFJB3ZCWVZZ048AQP=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HH2DHQWYN3CZZCFT9X2R2N9J=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HH2DHQWY1GPVP5W5R4XV2H9C=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HH2DHQWY284121FR8HSFGH45=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HH2DHQWY0XM70BPE7222XE78=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HH2DHQWY4GXPMCV5JEBFERG6=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 default-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HH2DHQWYZSECQWRQEKDB9KZH=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E parameters-for-measuring-ctv=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-ctv clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HH2DHQWYCFGJK4ZT9CXFX3X3=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC viewthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HH2DHQWYP6S95MRAS39Q4RTT=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=ad-network-permissions-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01HH2DHQWYCWYQFBDA19Z9BA8W=ad-network-permissions-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8" />
