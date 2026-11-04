---
title: Настройка SplitMetrics Acquire (ранее — SearchAdsHQ)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-15T08:21:04Z'
  edited_at: '2026-09-17T00:26:03Z'
  id: 360002249257
  locale: ru
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ru/articles/360002249257
---
> **Кратко:** Оптимизируйте кампании Apple Ads с помощью SplitMetrics Acquire. После настройки AppsFlyer отправляет постбэки в SplitMetrics Acquire.

<div id="enabling-apple-ads-attribution" />

## Включение атрибуции Apple Ads

Рекламодатели и агентства могут включить атрибуцию для Apple Ads.

<div id="note" />

> 📘 **Примечание:**
>
> Если рекламодатель или агентство отключает атрибуцию для Apple Ads, атрибуция для этого приложения, включая отправку постбэков маркетинговым партнерам Apple Ads, прекращается.

* **Рекламодатели**: выполните приведенные ниже инструкции, чтобы включить атрибуцию для Apple Ads.
* **Агентства**: <Anchor target="_blank" href="/marketers/ru/docs/apple-ads-integration-setup#agency-setup">выполните эти инструкции</Anchor>, чтобы включить атрибуцию для Apple Ads.

<div id="setting-up-splitmetrics-acquire-on-appsflyer" />

## Настройка SplitMetrics Acquire в AppsFlyer

<div id="getting-required-information-from-splitmetrics-acquire" />

### Получение необходимых данных из SplitMetrics Acquire

Перед началом настройки SplitMetrics Acquire в AppsFlyer получите **client\_id** и **идентификатор группы кампаний Apple Ads**.

* Чтобы получить client\_id, перейдите на дэшборд SplitMetrics Acquire и кликните **Integrations** > **AppsFlyer**. В открывшемся всплывающем окне скопируйте ID.
* Для Apple  Ads Campaign Group ID: **на дэшборде Apple Ads** получите параметр Apple Ads Campaign Group ID, связанный со SplitMetrics Acquire. Чтобы найти идентификатор, следуйте указаниям на скриншоте ниже.  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

<div id="setting-up-campaigns-on-appsflyer" />

### Настройка кампаний в AppsFlyer

**Чтобы настроить SplitMetrics Acquire:**

1. **В AppsFlyer настройте SplitMetrics Acquire:**
   1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции**.
   2. Найдите SplitMetrics Acquire.  
      На экране появится список маркетинговых партнеров.
   3. Выберите SplitMetrics Acquire.
   4. Установите переключатель **Активировать партнера** в положение «Включено».
   5. Введите идентификатор клиента в поле **client\_id**.
   6. Введите **ID кампании Apple Ads** для SplitMetrics Acquire, полученный на предыдущем шаге. Введите только цифры.
   7. Нажмите **Save** (Сохранить).
2. Если вы хотите регистрировать атрибуцию для Apple Ads, также включите **интеграцию Apple Ads:**
   1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Партнерский маркетплейс**.
   2. Найдите и выберите партнера. Вы перенаправлены на страницу конфигурации партнера.
   3. На вкладке **Интеграция** включите **Активировать партнёра**.
   4. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

<div id="configuring-in-app-event-postbacks" />

#### Настройка постбэков по событиям в приложении

**Чтобы настроить постбэк, который должен отправляться в SplitMetrics Acquire при событиях в приложении:**

1. Введите client\_id.
2. Включите **постбэк событий в приложении**.
3. Чтобы добавить в список событие, определенное в SDK, нажмите **Add Event** (Добавить событие).
4. Введите следующие параметры:

   

| Имя параметра | Description(Описание) |
| --- | --- |
| Имя события в SDK | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события. **Совет:** если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| Отправка данных о доходе | Выберите один из следующих вариантов: без значений и без дохода, значения & без дохода или значения & доход. |

5. Нажмите **Сохранить интеграцию**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-apple-ads h_01HBB5JWBAZMD5BHPGQYHYQY0Q=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-apple-ads h_01HBB5JWBA612TQV90K56H319J=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 setting-up-searchadshq-on-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-splitmetrics-acquire-%D0%B2-appsflyer h_01HBB5JWBA6QPV3ZN0FCBK0BHR=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-splitmetrics-acquire-%D0%B2-appsflyer getting-required-information-from-searchadshq=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-splitmetrics-acquire h_01HBB5JWBA6CGAAQAA9DZ4XMNS=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-splitmetrics-acquire setting-up-campaigns-on-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-appsflyer h_01HBB5JWBAMHKBAMQD4TTQSZ0H=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-appsflyer configuring-inapp-event-postbacks=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HBB5JWBBHMKT3Z9JKEQJAZZ7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8" />
