---
title: Интеграция WebEngage с AppsFlyer
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
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-08-28T00:11:39Z'
  id: 7898288493841
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/7898288493841
---
> **Кратко:** WebEngage, интегрированный партнер AppsFlyer, — это Intelligent Marketing Cloud, созданный для мира, в котором мобильные устройства на первом месте.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-webengage" />

## Настройка WebEngage

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При первом посещении включите **Activate Partner**, чтобы настроить интеграцию. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнёром. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настройки WebEngage используется только вкладка **Интеграция**.

Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">настройке заголовка страницы партнера.</Anchor>

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** включите **Активацию партнера**, чтобы настроить интеграцию. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="general-settings" />

### Общие настройки

WebEngage подключается к AppsFlyer с помощью API-ключа и региона дата-центра WebEngage.

* **api\_key:** Введите ключ API. Чтобы получить его, войдите в учетную запись WebEngage и следуйте <Anchor target="_blank" href="https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region">инструкциям</Anchor>.
* **Регион:** введите регион, в котором будут размещаться ваши данные: **US** (для дата-центра в США) или **IN** (для дата-центра в Индии). По умолчанию все данные хранятся в дата-центре в США.

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png) 

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может автоматически отправлять постбэки в WebEngage после установок приложений и повторного вовлечения пользователей.

* **Выкл.** : не отправлять постбэки по установкам.
* **Все медиаисточники, включая органические**: отправляйте постбэки для событий, атрибутированных любому партнеру, а также для органических событий.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Примечание:**
>
> Как сеть, ориентированная на все установки, WebEngage предпочитает получать постбэки для всех новых установок вашего приложения из любого источника, включая органические. WebEngage рекомендует выбрать **Все медиаисточники, включая органические**.

<div id="in-app-event-settings" />

### Настройки внутренних событий приложения

Сопоставляйте события AppsFlyer с WebEngage с помощью постбэков. Если отправка постбэков активирована, они будут включать отклоненные внутренние события (события, признанные несоответствующими по правилам таргетинга или заблокированные Protect360).

<div id="to-configure-in-app-event-postbacks" />

#### Для настройки постбэков по внутренним событиям приложения:

1. Введите **api\_key** и **Регион**.
2. Активируйте **постбэки по внутренним событиям**.
3. Нажмите **Добавить событие**.
4. Заполните необходимые параметры.
5. [Необязательно] Нажмите <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы задать условия отправки определённых событий в приложении партнёру.  
   Узнать больше об <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">условных постбэках по событиям в приложении</Anchor>.

| Имя параметра | Description(Описание) |
| --- | --- |
| **Событие AppsFlyer** | Имя события, полученное AppsFlyer либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer**, затем нажмите **Добавить другое**. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий.</Anchor></li></ul> |
| **для пользователей от** | Выберите вариант отправки для события:<ul><li>**Только этот партнер**: постбэки отправляются только в том случае, когда событие атрибутируется этому партнеру.</li><li>**Все медиаисточники, включая органические**: отправляйте постбэки для событий, атрибутированных любому партнеру, включая органические события.</li></ul> |
| **Включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Значения и доход**: отправляет все параметры события, **включая** значение дохода (если оно есть в событии).</li><li>**Значения без дохода**: передача всех параметров события, **кроме** значения дохода.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

**Ссылка атрибуции** не поддерживается при интеграции с этим партнером.

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

**Разрешения** не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div data-zendesk-anchors="h_01H9HWK7APBFK7RWVFH79VW0ME=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-webengage=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-webengage h_01H9HWK7AP6Z398NP3G2BQQBTF=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-webengage h_01H9HWK7AP3ERT0TM39E6S5M79=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9HWK7AP3FMR5RMANZCMQ6M0=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9HWK7APG1STZ4Q19QVX4KRY=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWK7AP23GK6WWJTB543FEQ=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWK7APMBSZ1PG8MK88HZFS=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK7APFNAFE9YM2484DDHD=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F to-configure-inapp-event-postbacks=%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK7APZM8328V0EV4B5QDN=%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9HWK7AQTZXE7GPX5E9X2ZYN=attribution-link-tab h_01H9HWK7AQ8SXED5KHVD5T4DZZ=cost-tab h_01H9HWK7AQ2JG4BRS784M85Z6E=ad-revenue-tab h_01H9HWK7AQ5YJDY2M96CA05H6P=permissions-tab" />
