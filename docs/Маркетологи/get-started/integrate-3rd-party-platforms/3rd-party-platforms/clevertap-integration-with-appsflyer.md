---
title: Интеграция CleverTap с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
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
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-10-19T14:08:08Z'
  id: 360001299165
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360001299165
---
> **Кратко:** CleverTap — это современное интегрированное облачное решение для удержания, которое помогает цифровым потребительским брендам повышать удержание клиентов и их пожизненную ценность.

<Image align="center" alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-clevertap" />

## Настройка CleverTap

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе:

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

Этот переключатель должен быть включен все время, пока вы работаете с этим партнером.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации партнёров</Anchor>.

<div id="general-settings" />

### Общие настройки

**Токен аккаунта**

CleverTap подключается к AppsFlyer с помощью уникальных токена аккаунта, региона, кода-пароля аккаунта и идентификатора аккаунта. Если у вас их еще нет, для продолжения интеграции вы должны получить их в CleverTap или выполнить следующие шаги.

<div id="important-1" />

> 🚧 **Важно!**
>
> Чтобы разрешить отправку постбэков в CleverTap, обязательно выполните **оба** следующих шага:
>
> * Заполните как минимум **одно** из следующих полей: account\_token, account\_passcode или account\_id
> * В SDK AppsFlyer задайте значение Customer User ID (<Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#установка-cuid">iOS, Android</Anchor>). Рекомендации о том, какой параметр лучше использовать в качестве Customer User ID, см. в [документации CleverTap](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration). Обратите внимание: если Customer User ID пуст, постбэки не будут отправляться в CleverTap.

<Image align="center" alt="CleverTap_msc_new_2.png" src="https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png" />

<div id="obtain-clevertap-account-token" />

### Получение токена аккаунта CleverTap

**Чтобы получить токены аккаунта в CleverTap:**

1. В дэшборде CleverTap перейдите в **Settings** в правом верхнем углу.

   <Image align="center" alt="CleverTap_msc_new_4.png" src="https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png" />
   В самом верху страницы “Settings” вы увидите идентификатор аккаунта CleverTap, токен аккаунта и код-пароль рядом с полями "Account ID", “Account token” и “Passcode” соответственно:

   <Image align="center" alt="CleverTap_msc_new_5.png" src="https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png" />
2. Чтобы отобразить значения, нажмите на значки «глаза» рядом с каждым полем.
3. Скопируйте значения и вставьте их на страницу CleverTap в AppsFlyer.

   <div id="note" />

   > 📘 **Примечание:**
   >
   > * Регион зависит от URL-адреса дэшборда CleverTap для вашего аккаунта:
   > * Если URL-адрес вашего аккаунта — <Anchor target="_blank" href="https://eu1.dashboard.clevertap.com/">https://eu1.dashboard.clevertap.com</Anchor>, регион — EU1, то есть данные аккаунта размещены в дата-центре в ЕС.
   > * Если URL-адрес вашего аккаунта — <Anchor target="_blank" href="https://in1.dashboard.clevertap.com">https://in1.dashboard.clevertap.com</Anchor>, регион — IN1, то есть данные аккаунта размещены в дата-центре в Индии.
   > * Если URL-адрес вашего аккаунта — [https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com), регион — ID, то есть данные аккаунта размещены в дата-центре в Индонезии.* Настройка региона чувствительна к регистру, поэтому нужно использовать только заглавные буквы. Если используются строчные буквы, постбэк будет отправлен на сервер по умолчанию (EU1).

4. Завершите интеграцию в соответствии с <Anchor target="_blank" href="https://developer.clevertap.com/docs/appsflyer#section-step-2-integration">документацией CleverTap</Anchor>.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в CleverTap после установок пользователей. В этом разделе можно определить источник пользователей, которому нужно отправлять постбэки. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

<Image align="center" alt="clevertap-default-postbacks_en-us.png" src="https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png" />

**Чтобы отправлять постбэки в CleverTap для любого пользователя, который загружает приложение:** выберите **Все медиаисточники, включая органические**.

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

<Image align="center" alt="clevertap-in-app-events_en-us.png" src="https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png" />

В этом разделе вы сопоставляете события AppsFlyer с партнером через постбэки.  
Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">постбэках по событиям в приложении.</Anchor>

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Введите все обязательные токены.
2. Активируйте **постбэки по внутренним событиям**.
3. Чтобы добавить в список событие SDK, нажмите **Add Event** .
4. Выберите **название события SDK** из выпадающего меню.
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

Данные о стоимости неприменимы для этого партнера.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Данные о доходах от рекламы неприменимы для этого партнера.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения для CleverTap недоступны.

</Accordion>

<div id="measure-clevertap-owned-media" />

## Измерение собственных медиа CleverTap

Поскольку CleverTap — это платформа, которая использует электронную почту, СМС, push-уведомления и т. д. для автоматизации маркетинга, вы можете использовать <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">AppsFlyer OneLink</Anchor> как решение для измерения собственных медиа, исходящих из CleverTap.

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-clevertap=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-clevertap h_01H9FK5JT1ATCHY6WAVB6E2YEW=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-clevertap h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FK5JT12Z1M6WW3GQQF5QVN=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK5JT1FMC6JANBP9KBB0V2=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK5JT1MQKT7KWJ3EVNEA1E=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 obtain-clevertap-account-token=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-clevertap h_01H9FK5JT1RVJ1V0CGXSH1XZPM=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-clevertap h_01H9FK5JT2QV9CKSZ1N3S4WTGE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK5JT2CE0WQ9HAGVGAQA5B=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK5JT2YS7G5WDD4F5MPYVZ=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab measure-clevertap-owned-media=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-clevertap h_01H9FK5JT2AZTT5936DD88ZZV3=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-clevertap" />
