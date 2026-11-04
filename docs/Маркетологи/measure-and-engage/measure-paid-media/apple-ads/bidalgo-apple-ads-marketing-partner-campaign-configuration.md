---
title: Маркетинговый партнер Apple Ads Bidalgo — настройка кампании
metadata:
  keywords:
    - Apple Search Ads
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-26T10:33:54Z'
  edited_at: '2026-09-17T00:25:58Z'
  id: 360001340429
  locale: ru
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ru/articles/360001340429
---
> **Кратко:** Оптимизируйте кампании Apple Ads с помощью Bidalgo. После настройки AppsFlyer отправляет постбэки в Bidalgo.

<div id="enabling-sending-postbacks-to-bidalgo-apple-ads-marketing-partner" />

## Включение отправки постбэков в Bidalgo (маркетинговому партнеру Apple Ads)

<div id="note" />

> 📘 **Примечание:**
>
> Если рекламодатель или агентство отключает атрибуцию для Apple Ads, атрибуция для этого приложения, включая отправку постбэков маркетинговым партнерам Apple Ads, прекращается.

И рекламодатели, и агентства могут включить атрибуцию для Apple Ads.

* **Рекламодатели:** следуйте инструкциям ниже, чтобы включить атрибуцию для Apple Ads.
* **Агентства:** <Anchor target="_blank" href="/marketers/ru/docs/apple-ads-integration-setup#agency-setup">следуйте этим инструкциям</Anchor>, чтобы включить атрибуцию для Apple Ads.

<div id="configuring-bidalgo" />

### Настройка Bidalgo

**Чтобы настроить Bidalgo:**

1. При необходимости активируйте **интеграцию с Apple Search Ads:**
   1. В AppsFlyer в боковом меню выберите вкладку **Collaboration** > **Partner Integrations > Partner Marketplace** .
   2. Найдите и выберите партнера. Вы перенаправлены на страницу конфигурации партнера.
   3. На вкладке **Интеграция** включите **Активировать партнёра**.
   4. Нажмите кнопку **Save Integration** (Сохранить интеграцию).
2. **На дэшборде Apple Ads**: получите параметр идентификатор ID группы кампаний Apple Ads, связанный с Bidalgo. Чтобы найти идентификатор, следуйте указаниям на скриншоте ниже.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **В AppsFlyer настройте Bidalgo:**
   1. В AppsFlyer в боковом меню выберите **Сотрудничество**> **Активные интеграции**.
   2. Найдите Bidalgo — маркетингового партнера Apple Ads.  
      На экране появится список маркетинговых партнеров.
   3. Выберите Bidalgo — маркетингового партнера Apple Ads.
   4. Установите переключатель **Активировать партнера** в положение «Включено».
   5. Введите **идентификатор кампании Apple Ads** в Bidalgo, полученный на предыдущем шаге. Введите только цифры.
   6. Нажмите **Save** (Сохранить).

<div id="default-postbacks" />

### Постбэки по умолчанию

Установки и повторные вовлечения отправляются автоматически после активации партнера.

<div id="configuring-in-app-events-postbacks" />

### Настройка постбэков по событиям в приложении

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Включите **постбэк событий в приложении**.
2. Чтобы добавить в список событие, определенное в SDK, нажмите **Add Event** (Добавить событие).
3. Введите следующие параметры:

   

| Имя параметра | Description(Описание) |
| --- | --- |
| Имя события в SDK | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события. **Совет:** если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| Отправка данных о доходе | Выберите один из следующих вариантов: без значений и без дохода, значения без дохода или значения и доход. |

4. Нажмите **Сохранить интеграцию**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-bidalgo-apple-search-ads-marketing-partner=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%B2-bidalgo-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%BC%D1%83-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D1%83-apple-ads h_01HKW0AZ05126SWNF374821AAH=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%B2-bidalgo-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%BC%D1%83-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D1%83-apple-ads h_01HKW0AZ05SXCVY0M3M7R07KG6=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 configuring-bidalgo=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-bidalgo h_01HKW0AZ06QFMYPJF95XQRAK99=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-bidalgo default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW0AZ06SPXE8K9JQN60B8T2=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E configuring-inapp-events-postbacks=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKW0AZ06F0169D59AWKQJN87=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8" />
