---
title: Настройка кампании MoEngage
metadata:
  keywords:
    - MoEngage
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
  created_at: '2017-06-25T07:50:18Z'
  edited_at: '2026-08-19T00:11:32Z'
  id: 115003139643
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/115003139643
---
> **Кратко:** MoEngage — это сторонняя платформа вовлеченности клиентов, интегрированная с AppsFlyer. Это агентная платформа вовлеченности клиентов, созданная для мира, ориентированного на мобильные устройства.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-moengage" />

## Настройка MoEngage

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При первом посещении включите **Activate Partner**, чтобы настроить интеграцию. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнёром. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">настройке заголовка страницы партнера.</Anchor>

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="general-settings" />

### Общие настройки

MoEngage подключается к AppsFlyer с помощью уникальных идентификатора ID приложения, ключа приложения и центра обработки данных MoEngage. Если у вас еще нет идентификатора ID приложения и ключа приложения, сначала получите их, чтобы продолжить интеграцию:

* **APP\_ID:** Введите идентификатор ID приложения. Чтобы получить его, войдите в учетную запись MoEngage и в меню слева перейдите в **Settings** > **App Settings**.
* **Центр обработки данных MoEngage:** Укажите центр обработки данных MoEngage, в котором вы зарегистрировались. Узнать больше о <Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage">центрах обработки данных в MoEngage</Anchor>.
* **APP\_KEY:** Введите API-ключ приложения. Чтобы получить его, войдите в учетную запись MoEngage и перейдите в **Settings** > **Analytics**.

![moengage_general_settings_en-us.png](https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png)

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в MoEngage после установки пользователей. Выберите один из следующих вариантов:

* **Выкл.** : Не отправлять постбэки об установках.
* **Все медиаисточники, включая органические**: Отправляйте постбэки для событий, атрибутированных любому партнеру, а также для органических событий.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Примечание:**
>
> Как сеть, ориентированная на все установки, MoEngage предпочитает получать постбэки для всех новых установок вашего приложения из любого источника, включая органические. MoEngage рекомендует выбрать **Все медиаисточники, включая органические**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

**Ссылка атрибуции** не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

**Данные о расходах** не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

**Доход от рекламы** не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

**«Разрешения»** не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJPMX1TXBZY6C94HQ7J85=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-moengage=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-moengage h_01H9HWJPMXN58VV9SQQPY4T5HZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-moengage h_01H9HWJPMX946NS52DTPAZWVEK=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9HWJPMX46NV79HHGRRD6D56=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9HWJPMXPZ5QV9D08CJMHMHS=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWJPMX0TZ496PP8EY3H336=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWJPMX4CHJ9MADEQBSDMGY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01H9HWJPMXJVWPK67W5X88GYHZ=attribution-link-tab h_01H9HWJPMXQ07XNN8Y79P5DCAN=cost-tab h_01H9HWJPMX8MC1GSD2VD3QQ82Y=ad-revenue-tab h_01H9HWJPMXKYXVCH3HRA2FCPSQ=permissions-tab" />
