---
title: Настройка кампании Ligatus
metadata:
  keywords:
    - Ligatus
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
  created_at: '2016-06-20T12:47:01Z'
  edited_at: '2026-08-31T00:25:27Z'
  id: 211189743
  locale: ru
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ru/articles/211189743
---
> **Кратко:** Ligatus — интегрированный партнер AppsFlyer, рекламная сеть, которая лидирует в области решений для нативной рекламы для паблишеров, рекламодателей и programmatic-покупателей, обеспечивая высокое качество и высокую эффективность. Помимо мобильной атрибуции по кликам, Ligatus также предлагает атрибуцию затрат, дохода от рекламы, ретаргетинга и атрибуцию по просмотрам, данные которых можно регистрировать с помощью AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ligatus.png" width="209px" />

<div id="setting-up-ligatus" />

## Настройка Ligatus

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом посещении** этого раздела вам нужно перевести кнопку ***Activate Partner*** в положение «Вкл.», чтобы стала доступна настройка параметров вкладки интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
    Дополнительная информация об активации партнера доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

Окно конфигурации Ligatus включает 2 активные вкладки: «Интеграция» и «Ссылка атрибуции». Чтобы ознакомиться с настройками вкладок, нажмите на пункты ниже.

<div id="tip" />

> 👍 **Совет.**
>
> * Этап <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#d">Общие настройки</Anchor> на вкладке интеграции необходимо **обязательно** выполнять для всех партнеров.
> * Все остальные этапы описаны только для сведения или же являются **необязательными**.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации/деактивации партнеров</Anchor>.

<div id="default-postbacks" />

### Постбэки по умолчанию

автоматически отправляйте постбэки в Ligatus после установок и повторных вовлечений пользователей. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

Выберите **Только события атрибутируемые этому партнеру** для событий, которые приходят только от пользователей, атрибутированных Ligatus.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

На этой вкладке можно создавать ссылки атрибуции, которые нужно отправить в Ligatus для атрибуции кампаний, групп объявлений и даже отдельных объявлений Ligatus. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

<div id="attribution-link-parameters" />

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Добавление параметров в ссылку атрибуции позволяет впоследствии получать более детальную информацию при анализе. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Кампания** — добавьте этот параметр, чтобы сравнивать разные кампании в Ligatus.  
  **Параметр ссылки атрибуции:** c
* **Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний Ligatus.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** — задайте названия объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний Ligatus.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки определенным паблишерам. Если паблишеров много, рекомендуем ограничить количество используемых идентификаторов site ID и использовать параметр Sub Site ID, чтобы избежать <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превышения ограничений site ID</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Параметры подписчика** — используйте любой из 5 параметров подписчика, чтобы добавить полезные значения. Обратите внимание, что эти параметры обрабатываются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Атрибуция по кликам

На этой шкале можно задать **максимальное время от клика до установки**. Для Ligatus могут быть атрибутированы только те установки (первые запуски), которые произошли в пределах окна атрибуции.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по кликам см. здесь</Anchor>.

<div id="click-attribution-link" />

### Ссылка атрибуции для клика

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в Ligatus, чтобы она активировалась, когда лиды кликают по соответствующей рекламе.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнером.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнером.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Для Ligatus настройка разрешений недоступна.

</Accordion>

<div data-zendesk-anchors="setting-up-ligatus=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ligatus h_01HKW2DXQHTK9HVAWK0ECR46AZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ligatus h_01HKW2DXQJ4DBPP38P4RRZGX10=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 h_01HKW2DXQJYQ7PJVN6HAM0AHXB=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW2DXQJEF1KX2C489M18EB7=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW2DXQJPJKBMA7ZN75JSSNR=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW2DXQJNFZJT6NVC2R3GDSB=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW2DXQJC123Y5DPX0V86M4K=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW2DXQK53YBMRBF2RC26SG8=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW2DXQKFGXMBB31N3EJAA55=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW2DXQKPZBFVKQ71G6076VN=cost-tab h_01HKW2DXQKQ0YDVHMGJ0WMP1CB=ad-revenue-tab h_01HKW2DXQKBC42EMXQRVZSK7N4=permissions-tab" />
