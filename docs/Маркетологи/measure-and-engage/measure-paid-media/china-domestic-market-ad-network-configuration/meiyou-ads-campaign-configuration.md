---
title: Настройка кампании Meiyou Ads
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - meiyou
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-01T03:26:18Z'
  edited_at: '2026-09-17T00:26:20Z'
  id: 360002141597
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/360002141597
---
> **Кратко:** Meiyou Ads — интегрированный партнер AppsFlyer и рекламная сеть.

<div id="setting-up-meiyou-ads" />

## Настройка Meiyou Ads

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   **Важно:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настроек Meiyou Ads есть 3 вкладки: Интеграция, Ссылка атрибуции и Разрешения. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка Integration (Интеграция)">

<div id="activate-partner" />

### Activate Partner (Активировать партнера)

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

Meiyou Ads подключается к AppsFlyer через уникальный **ключ**. Если у вас еще нет этого ключа, получите его в Meiyou Ads, чтобы продолжить интеграцию.

![mceclip3.png](https://files.readme.io/451f74c0a6b45926f89a3f2a5d04b6ef240184c4862b576bee0d0a2b7a832f30-50900150950417.png)

**Активация атрибуции по просмотрам**

Переведите этот переключатель в положение "Включено", если хотите атрибутировать установки после просмотра из Meiyou Ads. На вкладке «Ссылка атрибуции» (описана ниже) имеется шкала для окна атрибуции по просмотрам.

<div id="default-postbacks" />

### Постбэки по умолчанию

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="548px" />

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе можно сопоставить события AppsFlyer с Meiyou Ads через постбэки.

**Ключ**

Meiyou Ads подключается к AppsFlyer с помощью уникального ключа. Если у вас еще нет этого ключа, получите его в Meiyou Ads, чтобы продолжить интеграцию.

<Image alt="mceclip1.png" src="https://files.readme.io/32b1c68531c7aa752514f9b1c13c4438cddef2e93d2ca04ab287d46acecda15e-50900150956305.png" width="661px" />

1. Укажите здесь ключ Meiyou Ads
2. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
3. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
4. Введите следующие параметры:

| Имя параметра | Описание |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор каждого события, определенные на стороне Meiyou Ads.  <br />Получите соответствующий идентификатор события в Meiyou Ads и введите его в текстовое поле. |
| **Отправка данных о доходе** | **Флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, в том числе значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

На этой вкладке можно создать ссылки атрибуции, которые нужно отправить в Meiyou Ads для атрибуции кампаний Meiyou Ads, групп объявлений или даже отдельных рекламных объявлений. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

![mceclip2.png](https://files.readme.io/3a9b086aa1a76dc64289a512eec56885d108dce5c2778580fc0b2962f00c8a95-50900150957201.png)

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Кампания** — добавьте этот параметр, чтобы сравнивать разные кампании в Meiyou Ads.  
  **Параметр ссылки атрибуции:** c
* **Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний Meiyou Ads.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия групп объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний Meiyou Ads.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — используйте параметр Site ID, чтобы атрибутировать установки определенным паблишерам. Если паблишеров много, рекомендуется ограничить количество используемых идентификаторов Site ID и использовать параметр Sub Site ID, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить ограничения Site ID</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** — используйте любой из 5 параметров подписчика, чтобы передавать полезные значения. Обратите внимание: эти параметры обрабатываются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

На этой шкале можно задать **максимальное время от клика до установки**. К Meiyou Ads атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по кликам см. здесь</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="click-attribution-link" />

### Ссылка атрибуции по нажатиям

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в Meiyou Ads, чтобы активировать, когда потенциальные клиенты нажимают на соответствующее объявление.

<div id="view-through-attribution-lookback-window" />

### Окно лукбэк на основе просмотров

На этой шкале можно задать **максимальное время от показа до установки**. К Meiyou Ads атрибутируются только те установки (первые запуски), которые произошли в рамках этого окна атрибуции после показа рекламы, при условии что не было другого релевантного клика по рекламе.

Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 7).

**Параметр ссылки атрибуции:** af\_viewthrough\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">атрибуции по просмотрам см. здесь</Anchor>.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### Ссылка на атрибуцию показов

Ссылка атрибуции показа содержит такие же данные атрибуции, как и ссылка регистрации кликов (за исключением другого окна атрибуции). Отправьте ее в Meiyou Ads для активации при просмотре соответствующей рекламы, обычно в течение 1 секунды или более.


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

На этой вкладке можно выбрать разрешения для Meiyou Ads в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и другое. Обратите внимание, что даже если атрибуция для Meiyou Ads отключена, вкладка разрешений остается активной, и вы можете предоставить Meiyou Ads контроль.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

<div id="ad-network-permissions" />

### Полномочия для рекламной сети

Эти переключатели позволяют предоставить рекламной сети право самостоятельно выполнять настройки для вашего приложения:

* ***Разрешить настройку интеграции*** — разрешить партнеру настраивать вкладку интеграции (за исключением постбэков по событиям в приложении)
* ***Разрешить настройку постбэков по внутренним событиям приложения*** — разрешить партнеру настраивать постбэки по внутренним событиям и отображать эти настройки на вкладке интеграции.
* ***Разрешить доступ к своему отчету об удержании*** — доступ предоставляется только к собственным данным партнера.
* ***Разрешить доступ к панели управления Protect360*** — доступ предоставляется только к собственным данным Protect360 этого партнера, при условии что эта функция активирована для рекламодателя.

См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешений рекламной сети</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-meiyou-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-meiyou-ads h_01HKW6VQGVGFA45SQK1KANQ10Q=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-meiyou-ads h_01HKW6VQGV71MM2T401TGHEMHA=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6VQGV3HG1ZTR41BD43ZTC=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HKW6VQGVNG13KARWZBSD59KX=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6VQGV32R49RCEKCYK1G18=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6VQGVHCVWR4KDHTH24D17=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6VQGVV9X64XHW48VGW6E6=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6VQGVZJ36JVCZ3SW7Z3YD=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6VQGWZQQZWT476QT496YF=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BD%D0%B0%D0%B6%D0%B0%D1%82%D0%B8%D1%8F%D0%BC h_01HKW6VQGWG7BH11EK5HQACKVY=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BD%D0%B0%D0%B6%D0%B0%D1%82%D0%B8%D1%8F%D0%BC viewthrough-attribution-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 h_01HKW6VQGWFJEJYD9KG8BH9EX0=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 impressions-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HKW6VQGWXCB2W13TM4WAGWE1=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01HKW6VQGWY3AFFTN0DP8BCV7S=cost-tab h_01HKW6VQGWARB4409DWKVDY45W=ad-revenue-tab h_01HKW6VQGW20F6TTCBPGDH57JW=permissions-tab ad-network-permissions=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01HKW6VQGWXBME473RXA5K1217=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8" />
