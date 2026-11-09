---
title: Bidalgo — конфигурация кампании Google Ads
metadata:
  keywords:
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
  created_at: '2018-07-19T11:46:44Z'
  edited_at: '2026-10-19T14:25:32Z'
  id: 360001325405
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/360001325405
---
> **Кратко:** Bidalgo, интегрированный партнер AppsFlyer, — ведущий поставщик решений на базе искусственного интеллекта, помогающих мобильным маркетологам масштабировать рост.

<div id="set-up-bidalgo-integration" />

## Настройка интеграции Bidalgo

**Необходимые условия:** Перед настройкой интеграции обязательно свяжитесь с партнёром и откройте у него аккаунт.

**Новая интеграция:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.
2. Выберите соответствующее приложение.
3. Найдите Bidalgo и выберите **Integrate**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Не выключайте его, пока работаете с Bidalgo.
5. При необходимости настройте остальные вкладки, как описано ниже.

**Изменение существующей интеграции:**

В AppsFlyer перейдите на вкладку **Collaborate > Partner Integrations > Active integrations** , найдите партнера и внесите изменения.

<div id="note" />

> 📘 **Примечание:**
>
> Идентификатор клиента Google Ads необходимо вводить **без** дефисов.

6. В вашем аккаунте **Google Ads** скопируйте идентификатор клиента (без дефисов) из левого верхнего угла и вставьте его в параметр AppsFlyer **Ads Customer ID**, как показано на следующих снимках экрана.

<Image align="center" alt="" src="https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png" />

7. Введите номер в поле **Google Ads Customer ID**.

<div id="in-app-events" />

### События в приложении

1. Чтобы отправлять постбэки событий в приложении в Bidalgo, переведите переключатель In-App Events Postback в положение **ON**.

2. Добавьте по отдельности события в приложении, которые вы хотите отправлять в Bidalgo, и сопоставьте их с полем **Partner Event Identifier**.

3. Выберите **Send Revenue**, чтобы отправлять все параметры, включая значение дохода (если оно есть в событии).

4. Нажмите **Save** (Сохранить).

<div id="important-note" />

> 📘 **Важное примечание**
>
> * Отключение атрибуции для Google Ads предотвращает отправку постбэков партнерам Google Ads.
> * Можно настроить несколько аккаунтов Google Ads (CID) для отправки постбэков (шаг 5), разделив каждый CID запятой.

<div data-zendesk-anchors="set-up-bidalgo-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-bidalgo h_01HKA1JNXMRJ8059FAJAEQ6RK5=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-bidalgo h_01HKA1JNXM5R15CBVQ2WHT99Z9=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 inapp-events=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKA1JNXM59W74725961FZA27=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HKA1JNXMASTQ9X2144JCKKNQ=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE%D0%B5-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />
