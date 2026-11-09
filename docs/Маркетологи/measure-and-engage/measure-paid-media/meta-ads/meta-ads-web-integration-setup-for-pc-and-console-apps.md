---
title: Настройка интеграции Meta Web для приложений ПК и консоли
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-09-17T00:28:37Z'
  id: 18704273772689
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/18704273772689
---
> **Краткий обзор.** Узнайте, как интегрировать Meta Web для приложений для ПК и консоли с AppsFlyer и настраивать кампании в Meta Web.

<div id="important" />

> 🚧 **Важно!**
>
> Эта интеграция доступна только для приложений для ПК и консолей, таких как Steam, Epic или нативный ПК. Для мобильных приложений см. страницу <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup">Настройка интеграции Meta ads</Anchor>.

<div id="overview" />

## Обзор

Эта статья содержит информацию и шаги по настройке и использованию Meta Web для приложений для ПК и консолей с AppsFlyer. Сюда входят:

* [Активация партнерской интеграции в AppsFlyer](#активация-партнера-в-appsflyer).
* [Настройка Meta Web в AppsFlyer](#настройка-meta-web-в-appsflyer).
* [Настройка кампаний в Meta для приложений для ПК и консолей](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#настройка-кампаний-в-meta-для-приложений-для-пк-и-консолей).

<div id="prerequisite" />

### Необходимое условие

Прежде чем активировать интеграцию Meta Web, убедитесь, что у вас есть [бизнес-аккаунт в Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

<div id="activating-partner-in-appsflyer" />

## Активация партнера в AppsFlyer

**Чтобы активировать партнерскую интеграцию:**

1. В AppsFlyer в боковом меню выберите **Collaborate** > **Partner Integrations > Marketplace** вкладку.
2. Найдите **Meta Web**.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настройки.
4. На вкладке **Интеграция** включите **Активировать партнёра**.  
   **Примечание: <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Переключатель должен оставаться включённым (</Anchor><Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активированным</Anchor>) всё время, пока вы работаете с партнёром.**
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе.

<div id="setting-up-meta-web-in-appsflyer" />

## Настройка Meta Web в AppsFlyer

В этой части настройки вы также можете настроить постбэки в Meta Web. Интеграция Meta Web (metaweb\_int) использует инструмент Conversions API, предоставляемый Meta ads для рекламодателей, чтобы отправлять данные из своих **приложений для ПК и консолей** непосредственно на серверы Meta. Эти данные могут включать в себя действия пользователей, например покупки, регистрации и другие виды конверсий, выполненные на немобильных платформах (веб-сайты или приложения). Полученные данные используются Meta ads для оптимизации таргетинга, оценки эффективности рекламы и создания пользовательских аудиторий для ретаргетинга.

Интеграция с Meta Web поддерживает только отправку постбэков для установок и внутренних событий приложения.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть ряд разделов, описанных ниже.

<div id="activate-partner" />

#### Активация партнера

Чтобы настроить интеграцию, необходимо сначала включить переключатель **Активировать партнёра**.

<div id="general-settings" />

#### Общие настройки

* **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете получить его в менеджере Meta ads:
  1. В боковом меню <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads Manager</Anchor> перейдите в раздел **Все инструменты** > **Events Manager**.   
     **Примечание:** Убедитесь, что в выпадающем списке справа вверху выбран нужный бизнес.
  2. В боковом меню **Events Manager** выберите **Источники данных**. Вы увидите список пикселей. Если у вас нет пикселя для выбранного бизнеса, вы можете создать его в том же окне.
  3. Скопируйте идентификатор пикселя по именем пикселя и вставьте его в поле Pixel ID интеграции AppsFlyer.  
     <Image align="center" alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **Токен доступа:** Введите токен доступа. Для этого следуйте [этим инструкциям](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
* **Ограничение использования персональных данных пользователей в рекламе на платформах Meta (CCPA):** Включите этот переключатель, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законов о защите данных</Anchor>.  
  **Примечание.** Закон CCPA ограничивает использование данных, которые поступают от пользователей Meta Ads, находящихся в штате Калифорния (США).

<div id="enable-view-through-attribution" />

#### Активация атрибуции по просмотрам

AppsFlyer поддерживает атрибуцию по просмотрам для веб-кампаний в Meta с использованием вероятностного моделирования (PMOD) и посадочной страницы с активированными <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">смарт-скриптами</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">смарт-баннерами</Anchor>. Это позволяет AppsFlyer атрибутировать установки приложений, которые происходят после того, как пользователи посмотрели рекламу, а затем установили приложение, даже на разных платформах, без необходимости прямого клика.

Когда пользователь нажимает на рекламу Meta Web и попадает на посадочную страницу с активированным <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>, AppsFlyer может атрибутировать вторичную установку приложения. Если доступно, в постбэк к Meta будет включён параметр `fbclid` для повышения точности атрибуции.

**Активация атрибуции по просмотрам:**

1. В AppsFlyer, в боковой панели, откройте **Активные интеграции** > **Meta Ads Web**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кросс-платформенной атрибуции** и установите для него окно атрибуции. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

<div id="default-postbacks" />

#### Постбэки по умолчанию

Постбэки по установкам автоматически отправляются в Meta Web. В поле **Для пользователей из** выберите один из следующих вариантов:

* **Только этот партнер**, чтобы гарантировать, что постбэки событий в приложении отправляются исключительно для событий, выполненных пользователями, пришедшими от этого партнера.
* **Все медиаисточники, включая органические,** должны гарантировать, что постбэки событий в приложении отправляются для событий, выполненных пользователями, пришедшими от этого партнера, других партнеров или из органических источников.

<div id="in-app-event-postbacks" />

#### Постбэки событий в приложении

Настройте сопоставление постбэков по внутренним событиям приложения, отправляемых в Meta Web. Эти события можно просматривать в менеджере событий <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Meta Events Manager</Anchor>:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| Имя параметра | Описание |
| --- | --- |
| **Событие AppsFlyer** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<ul><li>Нажмите кнопку **Добавить элемент**, введите название события и нажмите ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png).</li></ul> |
| **сопоставлено с событием партнера** | Уникальное имя или идентификатор каждого события, определенные партнером.<ul><li>Выберите в раскрывающемся списке наиболее подходящее предопределенное событие партнера или опцию CUSTOM (Пользовательское).</li></ul> |
| **для пользователей от** | <ul><li>**Только этот партнер**, чтобы гарантировать, что постбэки событий в приложении отправляются исключительно для событий, выполненных пользователями, пришедшими от этого партнера.</li><li>**Все медиаисточники, включая органические,** должны гарантировать, что постбэки событий в приложении отправляются для событий, выполненных пользователями, пришедшими от этого партнера, других партнеров или из органических источников.</li></ul> |
| **включая** | **Значения и доход:** в постбэке отправляются все параметры события, включая значение дохода (если оно есть в событии). |

3. [Необязательно] Нажмите значок **Добавить условие**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">установить условия</Anchor> для события.
4. Если требуется, установите **окно постбэков по внутренним событиям** (подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">настройке окна постбэков по внутренним событиям</Anchor>).
5. Нажмите **Сохранить интеграцию**.
6. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
   1. В левом верхнем углу под именем партнера нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из раскрывающегося списка.
   3. Повторите шаги по интеграции для выбранного приложения.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Генерация ссылки атрибуции в пользовательском интерфейсе AppsFlyer в настоящее время недоступна. Однако вы можете либо использовать кроссплатформенную целевую страницу с SmartScript, либо создать прямую ссылку атрибуции для своего приложения (см. таблицу ниже).

| Вариант | Действия | Кто задействован |
| --- | --- | --- |
| Кроссплатформенная целевая страница | **Рекомендация:** для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Steam.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кроссплатформенных целевых страницах</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кроссплатформенную целевую страницу</Anchor><ul><li>Убедитесь, что все соответствующие параметры URL (которые впоследствии будут считаны Smart Script) добавлены к URL объявления.</li><li>Убедитесь, что скрипт берет FBCLID из входящего URL и добавляет его в сгенерированную ссылку. То есть, сопоставьте исходящий параметр `fbclid` URL-адреса FBCLID с входящим параметром URL-адреса `fbclid`. **Важно!** Для отображения в отчетах по сырым данным AppsFlyer входящий параметр `fbclid` также должен быть сопоставлен с одним из исходящих параметров `af_sub[1-5]`.</li><li>Необязательно: используйте макросы Meta для динамических URL вместо того, чтобы вводить значения вручную. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Узнать больше</Anchor></li></ul> | Маркетолог (может потребоваться помощь разработчика) |
| Прямая ссылка атрибуции | Если вы не используете кроссплатформенную целевую страницу, потому что у вас есть только одно приложение на одной платформе, вы можете создать прямые ссылки атрибуции для размещения в объявлениях.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor><ul><li>Убедитесь, что в ссылке указаны обязательные параметры:<ul><li>media\_source (медиа-источник)</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>Шаблон для ссылки на ссылку объявления в Meta Web:<br /><br />`https://engagements.appsflyer.com/v1/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />Пример ссылки на рекламу Meta Web, ведущую в Steam: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**Внимание**: шаблон включает некоторые динамические параметры URL, поддерживаемые Meta. При желании вы можете заменить их реальными значениями вручную. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Подробнее о динамических параметрах URL в Meta</Anchor> | Маркетолог |

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Затраты недоступны для Meta Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы недоступен для Meta Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

В настоящее время Meta Web не предоставляются разрешения.

</Accordion>

<div id="setting-up-campaigns-in-meta-web-for-pc-and-console-apps" />

## Настройка кампаний в Meta для приложений для ПК и консолей

**Когда вы создаете новую кампанию**:

* Выберите цель кампании. Мы рекомендуем выбрать один из следующих вариантов:
  * **Продажи**: цель позволяет Meta оптимизировать конкретное событие (ваш основной KPI).
  * **Traffic** (Трафик): цель позволяет Meta оптимизировать клики по рекламе. Эту цель следует использовать только в том случае, если у вас нет других KPI или если объем других KPI слишком мал.
  * **Своя**: Если вы хотите установить пользовательское событие (в качестве цели кампании). **Примечание:** Чтобы указать пользовательское событие в качестве цели кампании на дэшборде Meta, сначала настройте пользовательское событие в AppsFlyer.
* Выберите **Веб-сайт** в качестве места конверсии.
* Когда вы будете называть свой пиксель конверсии Facebook, введите тот же идентификатор пикселя, который вы ввели для metaweb\_int в маркетплейсе партнеров AppsFlyer.
* Когда вы вводите URL-адрес сайта в качестве пункта назначения объявления, он должен быть одним из следующих:
  * Целевая страница на сайте (рекомендуется, если приложение работает на нескольких платформах)
  * URL-адрес магазина (рекомендуется, если ваше приложение находится в одном магазине приложений на одной платформе)

<div id="view-web-to-app-attribution-data" />

## Просмотреть данные атрибуции web-to-app

Хотя события конверсии, происходящие в вебе, отправляются в Meta с исходным PID `metaweb_int`, на дэшборде и в отчётах о сырых данных AppsFlyer они отображаются под PID `Facebook Ads`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Объединённый формат отчётности позволяет анализировать эффективность как кампаний для веба и приложений в одном месте, включая полные отчёты по затратам в вебе и мобильных каналах.

<div id="view-in-the-dashboard" />

### Посмотреть на дэшборде

Вся атрибуция Meta web-to-app отображается как `Facebook Ads` в дэшбордах «Обзор» и «Активность». Это обеспечивает единое, консолидированное представление результатов кампаний на разных платформах. Используйте стандартные фильтры и разбивки, чтобы сравнивать трафик в приложении и на вебе внутри ваших данных Meta Ads.

<div id="view-in-raw-data-and-api-reports" />

### Просмотр в отчётах о сырых данных и через API

* В **экспортах сырых данных и ответах API** используется PID `Facebook Ads` в поле `media_source` для веб-активности Meta. Чтобы верифицировать детали настройки веб-кампании, обратитесь к полю `original_url`, которое показывает `metaweb_int` как PID, использованный при создании веб-кампаний.
* **Отчеты о постбэках** показывают `metaweb_int` как оригинальный медиаисточник, к которому был отправлен постбэк.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Описание |
| --- | --- |
| Клики и показы (Временное ограничение) | Данные о кликах и показах для кампаний, нацеленных на приложения для ПК и консолей, временно недоступны из Meta SRN (`Facebook Ads`). |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer setting-up-metaweb-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-meta-web-%D0%B2-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-meta-web-%D0%B2-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HFXV8HPH6X92YETNAGZ910AV=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 transaction-id=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HARQDVEDA206D0BBXBC6WEHH=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 enable-viewthrough-attribution=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01ZXVWB1ZYKK4DP38QY1RMEY6M=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01H88VAJH3WE9Z0971WMBRBJRS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 01H88VAJH3AS37MVF75GANWX4B=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-meta-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 h_01HK4S03KVAN99YKXTHAKCT420=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-meta-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 meta%20view=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-webtoapp-attribution-data-from-november-2-2025=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01K88J8JFNMHCVZ0C34E3D7AST=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01K88J8JFN8W2572N92466YFZQ=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KB503RDVWPSFBAPAPW4CNZXM=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />
