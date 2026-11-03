---
title: Adquant by Kenshoo — конфигурация кампании Google Ads
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Kenshoo
    - Adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-12-09T07:43:55Z'
  edited_at: '2026-10-19T14:25:29Z'
  id: 360000654357
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/360000654357
---
> **Кратко:** Оптимизируйте кампании Google AdWords с помощью Adquant by Kenshoo. После настройки AppsFlyer отправляет постбэки в Adquant.

## Настройка Adquant by Kenshoo

**Необходимые условия:** Перед настройкой интеграции обязательно свяжитесь с партнёром и откройте у него аккаунт.

**Новая интеграция:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.
2. Выберите соответствующее приложение.
3. Найдите Adquant by Kenshoo и выберите **Integrate**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Не выключайте этот параметр, пока работаете с Adquant by Kenshoo.
5. При необходимости настройте остальные вкладки, как описано ниже.

**Изменение существующей интеграции:**

В AppsFlyer перейдите на вкладку **Collaborate > Partner Integrations > Active integrations**, найдите партнера и внесите изменения.

> 📘 **Примечание:**
>
> Идентификатор клиента Google Ads необходимо вводить **без** дефисов.

6. В аккаунте **Google Ads** скопируйте идентификатор клиента (без дефисов) в левом верхнем углу и вставьте его в параметр AppsFlyer **Ads Customer ID**, как показано на снимках экрана ниже.

[![](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)

7. Введите **Action Identifier**, **Disable\_Country\_Sending** (предоставляется Adquant) и номер **Google Ads Customer ID** в соответствующие поля.

### События в приложении

1. Чтобы отправлять постбэки событий в приложении в Adquant by Kenshoo, переключите In-App Events Postback в положение **ON**.

2. По отдельности добавьте события в приложении, которые нужно отправлять в Adquant by Kenshoo, и сопоставьте их с полем **Partner Event Identifier**.

3. Выберите **Send Revenue**, чтобы отправлять все параметры, включая значение дохода (если оно есть в событии).

4. Нажмите **Сохранить**.

> 📘 **Важное примечание**
>
> * Отключение атрибуции для Google Ads предотвращает отправку постбэков партнерам Google Ads.
> * Вы можете настроить несколько аккаунтов Google Ads (CID) для отправки постбэков (шаг 5), разделив каждый CID запятой.

<div data-zendesk-anchors="setting-up-adquant-by-kenshoo=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-adquant-by-kenshoo h_01HKA1JQRK5BVGW13P72YEXZT7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-adquant-by-kenshoo h_01HKA1JQRKGDMZHTVSPVDSV463=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 inapp-events=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKA1JQRK4YNEXKAHVBYP3EC1=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKA1JQRKZJJ4RXCCVSS1BG7Z=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE%D0%B5-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />
