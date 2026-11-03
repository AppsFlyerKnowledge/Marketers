---
title: Настройка кампании MoPub Acquire
metadata:
  keywords:
    - CrossInstall
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-20T11:27:42Z'
  edited_at: '2026-09-12T00:24:21Z'
  id: 211187263
  locale: ru
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ru/articles/211187263
---
> **Кратко:** MoPub Acquire (ранее Crossinstall, компания X Ads) — интегрированный партнер AppsFlyer. MoPub Acquire — это платформа DSP для мобильных устройств, специализирующаяся на playable ads в большом масштабе. Помимо мобильной атрибуции по кликам, MoPub Acquire также предлагает атрибуцию по стоимости и просмотрам, которую можно регистрировать с помощью AppsFlyer.

<Image alt="MoPub Acquire, компания Twitter" src="https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png" width="104px" />

## Настройка MoPub Acquire

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

### Активация партнера

**Чтобы включить интеграцию этого партнера**, включите опцию **Активировать партнера**.  
Этот переключатель должен быть активирован все время, пока вы работаете с этим партнёром. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации партнёров</Anchor>.

**Активация атрибуции по просмотрам**

Включите эту опцию, если хотите атрибутировать установки после просмотра из MoPub Acquire. На вкладке «Ссылка атрибуции» (описана ниже) имеется шкала для окна атрибуции по просмотрам.

### Постбэки по умолчанию

Отправляйте автоматические постбэки в MoPub Acquire после установок и повторных вовлечений пользователей. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

Выберите **Только события, атрибутируемые этому партнеру** для событий, которые приходят исключительно от пользователей, атрибутированных MoPub Acquire.

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе можно сопоставить события AppsFlyer с MoPub Acquire с помощью постбэков.

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Включите **In-app event postback**.
2. Установите **In-app event postback window** (read more about<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям"> in-app event postback window configuration</Anchor>).
3. Click **Add event** , чтобы добавить событие SDK в список.
4. Заполните необходимые параметры:

| Имя параметра | Description(Описание) |
| --- | --- |
| Имя события в SDK | Название события, полученное AppsFlyer либо из SDK, интегрированного с вашим приложением, либо из межсерверных событий.  <br />**Совет**: Не нашли нужное событие? Введите его SDK Event Name, нажмите **Create custom** и сопоставьте как обычно. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий</Anchor> читайте здесь. |
| Sending option (Вариант отправки) | Выберите вариант отправки для события:<ul><li>**Только события, атрибутируемые этому партнеру** для событий, поступающих **только** от пользователей, атрибутированных этому партнеру.</li><li>**События, атрибутируемые любому партнеру или органические**: партнер будет получать сведения о событиях всех пользователей, которые есть в вашей базе.</li></ul> |
| Отправить доход | <ul><li>**Нет значений и нет дохода:** отправляет только само событие без значения.</li><li>**Значения, нет дохода:** отправляет все параметры, кроме значения дохода.</li><li>**Значения и доход**: отправляет все параметры события, включая значение дохода (если оно есть в событии).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

На этой вкладке можно создавать ссылки атрибуции, которые нужно отправить в MoPub Acquire для атрибуции кампаний, групп объявлений и даже отдельных рекламных объявлений MoPub Acquire.

На этой вкладке есть несколько разделов:

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Campaign** - добавьте, чтобы сравнивать разные кампании, запущенные в MoPub Acquire.  
  **Параметр ссылки атрибуции:** c
* **Adset** - задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний MoPub Acquire.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия групп объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках отдельных кампаний MoPub Acquire.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки определенным паблишерам. При наличии большого количества паблишеров рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить допустимое количество идентификаторов сайтов</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** — используйте любой из 5 параметров подписчика для подстановки полезных значений. Обратите внимание, что эти параметры обрабатываются и отображаются в отчете о сырых данных, что очень удобно для агрегации или фильтрации данных  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

### Атрибуция по кликам

На этой шкале можно задать **максимальное время от клика до установки**. Для MoPub Acquire атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об окне атрибуции по кликам <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">см. здесь</Anchor>.

### Ссылка атрибуции для клика

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в MoPub Acquire, чтобы она активировалась, когда лиды кликают по соответствующему рекламному объявлению.

### Окно лукбэк на основе просмотров

На этой шкале можно задать **максимальное время от показа до установки**. Для MoPub Acquire атрибутируются только те установки (первые запуски), которые произошли в рамках этого окна атрибуции после показа рекламы, при условии отсутствия других кликов по объявлению, относящихся к этой установке.

Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 7).

**Параметр ссылки атрибуции:** af\_viewthrough\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">атрибуции по просмотрам см. здесь</Anchor>.

### Ссылка на атрибуцию показов

Ссылка атрибуции показа содержит такие же данные атрибуции, как и ссылка регистрации кликов (за исключением другого окна атрибуции). Отправьте ее в MoPub Acquire для активации при просмотре соответствующей рекламы.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

AppsFlyer получает информацию о затратах через API. Подробную информацию о поддерживаемых параметрах, метриках и функциях см. в <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">таблице интеграции затрат рекламной сети</Anchor>. **Примечание**: Для получения данных о затратах требуется подписка ROI360.

**Чтобы включить API данных о затратах**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">этим инструкциям по интеграции</Anchor>.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотрите статус вашего API данных о затратах</Anchor> и время, когда AppsFlyer получил соответствующие данные о затратах в последний раз, либо на дэшборде статуса интеграции затрат (и доходов от рекламы), либо на дэшборде отдельной рекламной сети. .

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения, которые будут предоставлены MoPub Acquire. Обратите внимание, что, даже когда атрибуция для MoPub Acquire отключена, вкладка разрешений остается активной и можно предоставить MoPub Acquire разрешение на управление. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">Узнайте, какие разрешения можно предоставить MoPub Acquire</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mopub-acquire=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-mopub-acquire h_01HFP4C4JDPYDGM3RBSQCNHC3T=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-mopub-acquire h_01HFP4C4JDRMK87B48F4MV5B91=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HFP4C4JD5A9RZP6HBBM2WFHZ=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HFP4C4JDAK0N210GAH978CM0=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HFP4C4JDEW2YBFCFR0MN6G91=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HFP4C4JDWBC03HBEZ13HP3NS=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HFP4C4JDWAWKMT1CSPQSCNMZ=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HFP4C4JDW2DRVVHXJ8ZAT9W5=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HFP4C4JDTXJYH4S1EZ4HYJWG=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 viewthrough-attribution-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 h_01HFP4C4JDDWH23CVQMJNH2V70=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 impressions-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HFP4C4JDYXBYAP5AYBN54A4B=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HFP4C4JDP8NDDRHGXM0Y7XM7=cost-tab h_01HFP4C4JDBWCER854NDKTYRW8=ad-revenue-tab h_01HFP4C4JDRYYPW6W2PNA8J8P3=permissions-tab" />
