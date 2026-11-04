---
title: 'vivo Ads: настройка кампании'
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
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-09-17T00:26:40Z'
  id: 360002358897
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/360002358897
---
> **Кратко:** vivo Ads — интегрированный партнер AppsFlyer из числа рекламных сетей.

<div id="setting-up-vivo-ads" />

## Настройка vivo Ads

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   **Важно:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Окно конфигурации vivo Ads включает 2 активные вкладки: интеграция и ссылка атрибуции. Чтобы ознакомиться с настройками этих вкладок, нажимайте на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка Integration (Интеграция)">

Интеграция с vivo Ads поддерживает в постбэке по умолчанию только событие установки.

<div id="activate-partner" />

### Activate Partner (Активировать партнера)

При **первом посещении** здесь вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="enable-view-through-attribution" />

### Активация атрибуции по просмотрам

Переведите этот переключатель в положение «Включено», если хотите атрибутировать установки после просмотра из vivo Ads. На вкладке «Ссылка атрибуции» (описана ниже) имеется шкала для окна атрибуции по просмотрам.

<div id="default-postbacks" />

### Постбэки по умолчанию

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="456px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

На этой вкладке можно создавать ссылки атрибуции, которые нужно передать в vivo Ads для атрибуции кампаний vivo Ads, групп объявлений и даже отдельных рекламных объявлений. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Кампания** — добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в vivo Ads.  
  **Параметр ссылки атрибуции:** c
* **Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний vivo Ads.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний vivo Ads.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — используйте параметр Site ID, чтобы атрибутировать установки конкретным паблишерам. При наличии большого количества паблишеров рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить ограничения по Site ID</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** — используйте любой из 5 параметров подписчика для вставки полезных значений. Обратите внимание, что эти параметры анализируются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="479px" />

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

На этой шкале можно задать **максимальное время от клика до установки**. К vivo Ads атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции/ретроспективы.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по кликам см. здесь</Anchor>.

![viewthrough_en-us.png](https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png)

<div id="attribution-link" />

### Ссылка атрибуции

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в vivo Ads, чтобы активировать, когда потенциальные клиенты кликают по соответствующему рекламному объявлению.

<div id="view-through-attribution-lookback-window" />

### Окно лукбэк на основе просмотров

На этой шкале можно задать **максимальное время от показа до установки**. К vivo Ads атрибутируются только те установки (первые запуски), которые произошли в рамках этого окна атрибуции после показа рекламы, при условии отсутствия других релевантных кликов по объявлению.

Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 7).

**Параметр ссылки атрибуции:** af\_viewthrough\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">атрибуции по просмотрам см. здесь</Anchor>.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### Ссылка на атрибуцию показов

Ссылка атрибуции показа содержит такие же данные атрибуции, как и ссылка регистрации кликов (за исключением другого окна атрибуции). Отправьте ее в vivo Ads для активации при просмотре соответствующей рекламы, обычно в течение 1 секунды или более.

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

<div data-zendesk-anchors="setting-up-vivo-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-vivo-ads h_01HKW6Y9CJED5RV97WWSYQNBDG=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-vivo-ads h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6Y9CJC0EWH84B7GW29VJM=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 enable-viewthrough-attribution=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6Y9CJDY5XHWXN3CK0YGK8=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6Y9CKSHBWNBH0RY3X3RR3=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6Y9CKE86Z1Z4QZH0M665T=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6Y9CKNB685ZYXB8RM1P41=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 viewthrough-attribution-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 h_01HKW6Y9CKV48NRWSXD0ZKY3M0=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 impressions-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HKW6Y9CKV6XY1BCD9XX42XZ7=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
