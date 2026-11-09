---
title: Интеграция Liquid с AppsFlyer
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-08-19T00:11:19Z'
  id: 207040626
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/207040626
---
> **Кратко:** Liquid, интегрированный партнер AppsFlyer, автоматизирует ваши кампании и процессы — без необходимости привлекать IT-команду. Их интеллектуальный механизм правил работает на основе поведения пользователей и расширенной аналитики.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-liquid" />

## Настройка Liquid

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** вам нужно будет переключить тумблер ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**API-токен**

Liquid подключается к AppsFlyer через уникальный API-токен. Если у вас его ещё нет, для продолжения интеграции вы должны получить его у Liquid или следовать приведённым ниже инструкциям.

<Image align="center" alt="" src="https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png" />

<div id="obtaining-the-api-token" />

### Получение API-токена

API-токен можно найти, войдя в дэшборд Liquid.

* Нажмите значок **«Настройки»**
* Скопируйте production API-токен
* Вставьте APP\_TOKEN, полученный от Liquid

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки об установках пользователей Liquid. В этом разделе можно определить отправку этих постбэков.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Выберите **События, атрибутированные любому партнеру или органически**, чтобы отправлять постбэки в Liquid для любого пользователя, который загружает приложение, или выберите **Выкл.**

Нажмите кнопку **Сохранить.**

После сохранения этой конфигурации AppsFlyer начинает отправлять в Liquid следующие данные для каждой органической и неорганической установки:

* Токен приложения
* customer\_user\_id, заданный в SDK
* Медиа-источник
* Название кампании

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Liquid.

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

Разрешения для Liquid недоступны.

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-liquid=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-liquid h_01H9FKBW5QMJTARZ6KZ41QT1BN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-liquid h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKBW5RRYW1JTK2S9V4V6SA=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKBW5RB52QQKVF5TMFVKKT=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 obtaining-the-api-token=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-api-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0 h_01H9FKBW5RCGHVJRJEBQW4KNGD=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-api-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKBW5RVYXPEEFDG948P1XV=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
