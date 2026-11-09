---
title: Интеграция Insider с AppsFlyer
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
  created_at: '2021-01-03T11:23:45Z'
  edited_at: '2026-10-19T14:08:23Z'
  id: 360016827838
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360016827838
---
> **Краткий обзор:** Insider, интегрированный партнер AppsFlyer, — это маркетинговая и аналитическая платформа для мобильных и веб-приложений. Insider обеспечивает прогнозную сегментацию и персонализацию в реальном времени в вебе, мобильном вебе, мобильном приложении и рекламных каналах.

<Image align="center" alt="rockerbox-logo_en-us.png" src="https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png?v=1" />

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-insider" />

## Настройка Insider

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

Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации партнёров</Anchor>.

<div id="general-settings" />

### Общие настройки

Insider подключается к AppsFlyer с помощью уникального идентификатора партнера.

**Чтобы получить идентификатор,** войдите на платформу **Insider** и скопируйте свой идентификатор в правом верхнем углу дэшборда.

<Image align="center" alt="insider-partner-ID_en-us.png" src="https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png" />

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Insider после установки приложения пользователем. В этом разделе можно определить источник пользователей, которому нужно отправлять постбэки. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

**Чтобы отправлять в Insider постбэки для любого пользователя, загрузившего приложение,** выберите **Все медиаисточники, включая органические**.

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

<Image align="center" alt="insider-partner-field.png" src="https://files.readme.io/ad4b4a5e9d688be93b20ccf645c779c361390cc95e2a2acbab7299408b7478bf-4403354160785.png" />

В этом разделе вы настроите отправку партнеру постбэков о своих событиях в AppsFlyer. Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">постбэках по событиям в приложении.</Anchor>

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Введите **идентификатор партнера Insider**, который находится в правом верхнем углу дэшборда **Insider**.

   <Image align="center" alt="insider-partner-ID_en-us.png" src="https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png" />
2. В AppsFlyer активируйте **постбэк по событию в приложении.**
3. Нажмите **Add Event** , чтобы добавить SDK-событие в список.
4. Выберите **имя SDK-события** из выпадающего меню.
5. Введите **идентификатор события партнера**.
6. Выберите **вариант отправки**.
7. Выберите нужный вариант в раскрывающемся меню «Отправить доход»:
   * **Нет значений и нет дохода:** отправляет только само событие без значения.
   * **Значения, нет дохода:** отправляет все параметры, кроме значения дохода.
   * **Значения и доход**: отправляет все параметры события, включая значение дохода (если оно есть в событии).
8. Чтобы завершить настройку интеграции, нажмите кнопку **Сохранить интеграцию**.

<div id="note" />

> 📘 **Примечание**
>
> Чтобы включить постбэки, установите InsiderID как CUID.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для этого партнера.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах неприменимы при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы неприменим при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для этого партнера.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8YZMFS4XHX69CG90A18K=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-insider=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-insider h_01H9FK8YZM63N7HF514RVFPMJY=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-insider h_01H9FK8YZN7D4R6TBABMDB3K3K=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FK8YZNMN9QBRS33WPZQWPB=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK8YZNAFP5G2B277YPNY68=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK8YZNZWSD64K3R2TVHCE2=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK8YZN15KPHHA58XRABRD4=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01K88DMNP3SKDE93SXGXJXTE0C=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01H9FK8YZNJ86KQT59H9RD5CJA=attribution-link-tab h_01H9FK8YZN99ZBQQFBZF26HJZJ=cost-tab h_01H9FK8YZNAJ1XW7TSQWT7PYPW=ad-revenue-tab h_01H9FK8YZQTKN1SFMN9M0CKVYM=permissions-tab" />
