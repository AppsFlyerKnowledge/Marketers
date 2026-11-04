---
title: Настройка кампании WiFi Master Key Ads
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
  created_at: '2019-07-05T09:27:19Z'
  edited_at: '2026-09-17T00:26:45Z'
  id: 360001954137
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/360001954137
---
> **Кратко:** WiFi Master Key Ads — интегрированный партнер рекламной сети AppsFlyer.

<div id="setting-up-wifi-master-key-ads" />

## Настройка WiFi Master Key Ads

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   **Важно:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настроек WiFi Master Key Ads есть 3 активные вкладки: Integration, Attribution link и Permissions. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка Integration (Интеграция)">

<div id="activate-partner" />

### Activate Partner (Активировать партнера)

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**clientid и secretkey**

WiFi Master Key Ads подключается к AppsFlyer с помощью уникальных clientid и secretkey. Если у вас еще нет clientid и secretkey, необходимо получить их в WiFi Master Key Ads, чтобы продолжить интеграцию.

<Image alt="mceclip2.png" src="https://files.readme.io/8b486a98e25837a0d64e0a27e9b3aa7b66b426e8bad3fbae07b7436b91351db5-50900288875153.png" width="406px" />

<div id="default-postbacks" />

### Постбэки по умолчанию

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="509px" />

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе можно сопоставить события AppsFlyer с WiFi Master Key Ads с помощью постбэков.

**clientid и secretkey**

WiFi Master Key Ads подключается к AppsFlyer с помощью уникальных clientid и secretkey. Если у вас еще нет clientid и secretkey, необходимо получить их в WiFi Master Key Ads, чтобы продолжить интеграцию.

![mceclip3.png](https://files.readme.io/035ce248d6876cf31870abc49e949fc887f6bef08efd6e132e43b8c74e3aaf45-50900269524881.png)

1. Укажите здесь clientid и secretkey для WiFi Master Key Ads.
2. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
3. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
4. Введите следующие параметры:

| Имя параметра | Описание |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор ID каждого события, определенные на стороне WiFi Master Key Ads.  <br />Получите соответствующий идентификатор ID события в WiFi Master Key Ads и укажите его в текстовом поле. |
| **Отправка данных о доходе** | **Если флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного in-app события, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Если флажок установлен** — AppsFlyer отправляет все параметры, в том числе значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

На этой вкладке можно создать ссылки атрибуции, которые нужно отправить в WiFi Master Key Ads для атрибуции кампаний, групп объявлений и даже отдельных объявлений в WiFi Master Key Ads. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Campaign** — добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в WiFi Master Key Ads.  
  **Параметр ссылки атрибуции:** c
* **Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний WiFi Master Key Ads.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия рекламных групп, чтобы сравнивать разные креативы в конкретных рекламных группах в рамках конкретных кампаний WiFi Master Key Ads.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки конкретным паблишерам. Если паблишеров много, рекомендуем ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы избежать <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превышения лимита идентификаторов сайтов</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** — используйте любой из 5 параметров подписчика, чтобы подставить полезные значения. Обратите внимание, что эти параметры парсятся и отображаются в Отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

Этот ползунок позволяет задать **максимальное время от клика до установки**. К WiFi Master Key Ads могут быть атрибутированы только установки (первые запуски), которые происходят в течение окна атрибуции.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об окне атрибуции по кликам <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">см. здесь</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="click-attribution-link" />

### Ссылка атрибуции по нажатиям

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в WiFi Master Key Ads, чтобы она активировалась, когда потенциальные клиенты нажимают на соответствующее объявление.

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

На этой вкладке можно выбрать разрешения для WiFi Master Key Ads в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и другое. Обратите внимание, что даже если атрибуция для WiFi Master Key Ads отключена, вкладка разрешений остается активной и вы можете предоставить WiFi Master Key Ads разрешение на управление.

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

<div data-zendesk-anchors="setting-up-wifi-master-key-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-wifi-master-key-ads h_01HKW6Z9DPAYATXWJR4GZMD0KM=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-wifi-master-key-ads h_01HKW6Z9DPYGREGB9VHJJQP6FS=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6Z9DP6WQD968EQS8G0SZY=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HKW6Z9DQ3K3RTCT7CMT67WCX=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6Z9DQ26D258602BC43T9B=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6Z9DQ1XMVERFP97HQ7HM7=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6Z9DQ0GEE118QKXRA335C=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6Z9DQ8YMNT6W2B8NEV520=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6Z9DQ9D2F75XWZRM0JAQM=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BD%D0%B0%D0%B6%D0%B0%D1%82%D0%B8%D1%8F%D0%BC h_01HKW6Z9DQQE4QP37994K8HMCQ=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BD%D0%B0%D0%B6%D0%B0%D1%82%D0%B8%D1%8F%D0%BC h_01HKW6Z9DQJ6F8Z074H9JG97EC=cost-tab h_01HKW6Z9DQ6GW0S9KDG0RFK1BX=ad-revenue-tab h_01HKW6Z9DQ3Y12DV461NHST3FT=permissions-tab ad-network-permissions=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01HKW6Z9DQZ8TBA8DK6NJNQT4F=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8" />
