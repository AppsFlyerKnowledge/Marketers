---
title: Настройка SearchAds.com (MobileAction)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-06-20T13:34:38Z'
  edited_at: '2026-09-17T00:26:01Z'
  id: 4402846897041
  locale: ru
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ru/articles/4402846897041
---
> **Кратко:** Оптимизируйте кампании Apple Ads с помощью SearchAds.com by MobileAction. После настройки AppsFlyer отправляет постбэки в SearchAds.com.

## Включение атрибуции Apple Ads

Чтобы отправлять постбэки в SearchAds.com, сначала включите атрибуцию для Apple Ads. Это может сделать рекламодатель или агентство.

> 📘 **Примечание:**
>
> Если рекламодатель или агентство отключит атрибуцию для Apple Ads, отправка постбэков в SearchAds.com и другим маркетинговым партнерам Apple Ads прекратится.

* **Рекламодатели**: следуйте приведенным ниже инструкциям, чтобы включить атрибуцию для Apple Ads.
* **Агентства**: <Anchor target="_blank" href="/marketers/ru/docs/apple-ads-integration-setup#agency-setup">следуйте этим инструкциям</Anchor>, чтобы включить атрибуцию для Apple Ads.

## Настройка SearchAds.com в AppsFlyer

### Получение необходимой информации из SearchAds.com

Перед началом настройки SearchAds.com в AppsFlyer получите **api\_key** и **идентификатор группы кампаний Apple Ads**.

* Чтобы получить api\_key, перейдите в дэшборд SearchAds.com и выберите **Integrations** > **AppsFlyer**. В открывшемся всплывающем окне скопируйте идентификатор ID. [![API-ключ SearchAds.com](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)
* Для идентификатора группы кампаний Apple Ads: в **дэшборде Apple Ads** получите идентификатор группы кампаний Apple Ads для нужной группы кампаний:

  ![apple-search-ads-campaign-group-id.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

### Настройка кампаний в AppsFlyer

**Чтобы настроить SearchAds.com:**

1. При необходимости активируйте **интеграцию с Apple Search Ads:**
   1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Маркетплейс партнеров**.
   2. Найдите и выберите партнера. Вы перенаправлены на страницу конфигурации партнера.
   3. На вкладке **Интеграция** включите **Активировать партнёра**.
   4. Нажмите кнопку **Save Integration** (Сохранить интеграцию).
2. **В AppsFlyer настройте SearchAds.com:**
   1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции**.
   2. Найдите SearchAds.com (by MobileAction).  
      На экране появится список маркетинговых партнеров.
   3. Выберите SearchAds.com (by MobileAction).
   4. Установите переключатель **Активировать партнера** в положение «Включено».
   5. Введите API-ключ в поле **api\_key**.
   6. Введите **идентификатор кампании Apple Ads** SearchAds.com. Введите только цифры.
   7. Нажмите **Save** (Сохранить).

#### Настройка постбэков по событиям в приложении

**Чтобы настроить постбэк, который должен отправляться в SearchAds.com при событиях в приложении:**

1. Введите **api\_key**.
2. Включите **постбэк событий в приложении**.
3. Выберите **Отправлять все события**.
4. В разделе **Send revenue** выберите **Values&Revenue**.
5. Нажмите **Сохранить интеграцию**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-apple-ads h_01HKW0B2AZ40F0N9A7YYGTHCE0=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-apple-ads h_01HKW0B2AZ411647BAS75M5BG6=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 setting-up-searchadscom-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-searchadscom-%D0%B2-appsflyer h_01HKW0B2AZWC9AQBAYDWFPAKQN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-searchadscom-%D0%B2-appsflyer getting-required-information-from-searchadscom=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B9-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8%D0%B7-searchadscom h_01HKW0B2AZ49R66CMJ747M485M=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B9-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8%D0%B7-searchadscom setting-up-campaigns-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-appsflyer h_01HKW0B2AZ419YS071HNXHPZXY=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-appsflyer configuring-inapp-event-postbacks=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKW0B2AZ4GHJE5SQHB3ZSZ8D=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8" />
