---
title: Интеграция Rockerbox с AppsFlyer
metadata:
  keywords:
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
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-10-19T14:08:55Z'
  id: 360015760757
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360015760757
---
> **Кратко:** Узнайте, как автоматически передавать данные из AppsFlyer в Rockerbox — маркетинговую и аналитическую платформу для мобильных и веб-приложений.

<Image align="center" alt="rockerbox-logo_en-us.png" src="https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png" />

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-rockerbox" />

## Настройка Rockerbox

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

Этот переключатель должен быть включен все время, пока вы работаете с этим партнером.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации партнёров</Anchor>.

<div id="general-settings" />

### Общие настройки

**ID аккаунта Rockerbox**

**Чтобы подключить аккаунт Rockerbox к AppsFlyer,** введите ID аккаунта в поле **Rockerbox account ID**.   
ID аккаунта Rockerbox доступен на платформе Rockerbox в разделе **Settings** > **Account** > **General**.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Rockerbox после установки приложения пользователем. В этом разделе можно определить источник пользователей, постбэки для которых отправляются по каждому событию. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

Выберите **All media sources, including organic**, чтобы отправлять постбэки в Rockerbox для любого пользователя, загрузившего приложение.

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

<Image align="center" alt="rockerbox-in-app-events_en-us.png" src="https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png" />

В этом разделе вы настроите отправку партнеру постбэков о своих событиях в AppsFlyer. Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">постбэках по событиям в приложении</Anchor>

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Введите **Rockerbox Account ID**.
2. Активируйте **постбэки по внутренним событиям**.
3. Нажмите **Add Event** , чтобы добавить событие SDK в список.
4. Выберите **SDK event name** из выпадающего меню.
5. Выберите нужный вариант в раскрывающемся меню «Отправить доход»:
   * **Нет значений и нет дохода:** отправляет только само событие без значения.
   * **Значения, нет дохода:** отправляет все параметры, кроме значения дохода.
   * **Значения и доход**: отправляет все параметры события, включая значение дохода (если оно есть в событии).
6. Чтобы завершить настройку интеграции, нажмите кнопку **Сохранить интеграцию**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для этого партнера.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о стоимости неприменимы при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы неприменим при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для этого партнера.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-rockerbox=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-rockerbox h_01H9HWJW83BKP8DSYTV6YGPHK7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-rockerbox h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9HWJW83Z4NGT000091AHX0Z=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9HWJW832NQBPK2VS6TS1QK7=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWJW83CGMBADDBP7EJTR9N=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWJW84H4SDVRNZAG1D6N0D=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
