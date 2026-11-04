---
title: 'Настройка кампании UC Toutiao Ads: конфигурация'
metadata:
  keywords:
    - Advertisers
    - UC Toutiao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-25T05:41:49Z'
  edited_at: '2026-09-17T00:26:38Z'
  id: 115004843026
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/115004843026
---
> **Краткий обзор:** UC Toutiao Ads, интегрированный партнер рекламной сети AppsFlyer, — одно из ведущих новостных приложений-агрегаторов в Китае.

<div id="setting-up-uc-toutiao" />

## Настройка UC Toutiao

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

Окно конфигурации UC Toutiao включает 2 активные вкладки: интеграция и ссылка атрибуции.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

<div id="activate-partners" />

### Активация партнеров

При **первом посещении** вам нужно перевести переключатель ***Активировать партнера*** в положение «Включено», чтобы можно было настроить параметры вкладки интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="default-postbacks" />

### Постбэки по умолчанию

По умолчанию UC Toutiao получает постбэки только по событиям новых установок, атрибутированным ему.

![uc-toutiao-integration.png](https://files.readme.io/1ed78bd49d9a49d134f5c48655765ad205515752d88528a0a453bd3a091492c0-360002074869.png)

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе можно сопоставить события AppsFlyer с UC Toutiao с помощью постбэков.

[![](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)](https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png)

1. Повторно укажите здесь идентификатор сети UC Toutiao
2. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
3. В поле «Вариант отправки» выберите значение, которое будет использоваться для всех событий, определенных в SDK.  
   **- Только события, атрибутированные этому партнеру**: партнер будет получать сведения о событиях **только** тех пользователей, которые ему атрибутированы.  
    **- События, атрибутированные любому партнеру или органические**: партнер будет получать сведения о событиях всех пользователей, которые есть в вашей базе.
4. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
5. Введите следующие параметры:

| Имя параметра | Description(Описание) |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор ID каждого события, определенные на стороне UC Toutiao.  <br />Получите соответствующий идентификатор ID события в UC Toutiao и введите его в текстовое поле. |
| **Отправка данных о доходе** | **Флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, включая значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

На этой вкладке можно создавать ссылки атрибуции, которые нужно передать UC Toutiao для атрибуции кампаний, групп объявлений и даже отдельных объявлений UC Toutiao. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

[![UC_Toutiao_attribution_link_tab.png](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)](https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png)

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Кампания** — добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в UC Toutiao.  
  **Параметр ссылки атрибуции:** c
* **Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний UC Toutiao.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний UC Toutiao.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки конкретным паблишерам. Если паблишеров много, рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">не превысить допустимое количество идентификаторов сайтов</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** — используйте любой из 5 параметров подписчика, чтобы вставить полезные значения. Обратите внимание, что эти параметры анализируются и отображаются в Отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-params.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

Этот ползунок позволяет задать **максимальное время от клика до установки**. Для UC Toutiao атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции/лукбэка.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по клику см. здесь</Anchor>.

![uc-toutiao-click-through.png](https://files.readme.io/8128e80c365aa223105260a25aa99a61bd9eeccdf19d311804ed3e66b744ef39-360002074929.png)

<div id="click-attribution-link" />

### Ссылка атрибуции для клика

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в UC Toutiao, чтобы она активировалась, когда потенциальные клиенты нажимают на соответствующее объявление.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Интеграция стоимости не предоставляется для данного партнёра

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Интеграция доходов от рекламы для этого партнера недоступна.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Для этого партнера настройка разрешений недоступна.

</Accordion>

<div id="create-conversion-at-uc-toutiao-ads" />

## Создайте конверсию в рекламе uc toutiao ads

Войдите в UC Toutiao Ads (<Anchor target="_blank" href="https://e.uc.cn/">[https://e.uc.cn/](https://e.uc.cn/)</Anchor>) и выберите **Инструменты продвижения** >> **Инструменты конверсии** >> **Создать конверсию**.

![Toutiao_4.png](https://files.readme.io/40e4c3f26faf2cf928fe874398a7e505d100e717669867fc8a55b8b9fec1f021-115016024743.png)

Введите информацию о приложении >> **нажмите «Подтвердить»** >> **сгенерируйте QR-код**.

Приложение для Android:

![Toutiao_5.png](https://files.readme.io/8db1f985882f847aad08e4e46710bd9af8a95b62e0a0b488d5242879cd11b7bd-115015832006.png)

Приложение iOS:

![Toutiao_6.png](https://files.readme.io/18b8ba97b8792db66ec4874269bf1b6ccb21ad68016a57e52534f4e97835cc92-115016025123.png)

Используйте приложение Alipay или приложение Dingding, чтобы отсканировать 2-мерный код и установить ваше приложение. Завершите тест конверсии, после чего статус этой конверсии станет активным.

6. Создайте рекламные объявления

Создайте объявление: перейдите в раздел **Уровень рекламного блока** >> **Настройки ставок** >> **Включить конверсию**.

![Toutiao_7.png](https://files.readme.io/f2c49499432c3c358d737544ea02cb5b1e634244313606a62102707dd8a3c31e-115015832146.png)

<div data-zendesk-anchors="setting-up-uc-toutiao=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-uc-toutiao h_01HKW6Y1PVGS22BXK54VW8C488=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-uc-toutiao h_01HKW6Y1PWJEJHCCY5WM8AYNGE=integration-tab activate-partners=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HKW6Y1PWX3TMM41S78MJ21C1=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6Y1PWRZNRX6061KFECTDN=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6Y1PWRMK1H7QCW1GQWAA7=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6Y1PW95EWPGP09CCJF97M=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6Y1PWVTGGNX96AWVZJ9PP=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6Y1PWEW2FWN8K5S8DKQJJ=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6Y1PWKPJ09G70XMQG8H1S=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6Y1PWFS5X835MYJG0CVJ0=cost-tab h_01HKW6Y1PWJW4EW33MYRDN2FJB=ad-revenue-tab h_01HKW6Y1PWDWN4KWMA1KX5FYDT=permissions-tab create-conversion-at-uc-toutiao-ads=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8E-%D0%B2-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%B5-uc-toutiao-ads h_01HKW6Y1PWVMM70F6MJVCJYKT3=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8E-%D0%B2-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%B5-uc-toutiao-ads" />
