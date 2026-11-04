---
title: Интеграция Convertro с AppsFlyer
metadata:
  keywords:
    - Attribution
    - Convertro
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
  created_at: '2015-12-24T11:37:56Z'
  edited_at: '2026-08-28T00:10:27Z'
  id: 207040636
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/207040636
---
> **Кратко:** Convertro, интегрированный партнер AppsFlyer, стремится стать ведущим автоматизированным инструментом для маркетологов, чтобы они могли по-настоящему понимать эффективность своих рекламных решений и как можно быстрее действовать на основе этих инсайтов. Компания разработала технологию, которая не только собирает гранулярную информацию о пути клиента к конверсии, но и позволяет научно оптимизировать маркетинговый микс и автоматически определять, как перераспределять бюджет, чтобы максимизировать ROI.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-convertro" />

## Настройка Convertro

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настройки Convertro используется только вкладка **Integration**.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** включите переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**URL-адрес страницы, идентификатор сайта и имя клиента**

Convertro подключается к AppsFlyer с помощью уникальных URL-адреса страницы, идентификатора ID сайта и имени клиента. Если у вас их еще нет, для продолжения интеграции вы должны получить их в Convertro или выполнить инструкции ниже.

[![](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)

<div id="obtaining-the-client-name-page-url--site-id-from-the-convertro-platform" />

### Получение "Client Name, Page URL & Site ID" на платформе Convertro

Чтобы получить Client Name, Page URL-адрес и идентификатор сайта, войдите в дэшборд Convertro:

**URL-адрес страницы:**

[![](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)

**Тип устройства: xiaomi-Redmi Note 8:**

[![](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)

**Имя клиента:**

![](https://files.readme.io/2e5342006bdfff9e3b3c1dffdaed3e9d83ec2fe4c465b7918023a359776cee91-204595606.png)

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять в Convertro автоматические постбэки об установках пользователей. В этом разделе можно определить отправку этих постбэков.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Выберите **События, атрибутированные любому партнеру или органически**, чтобы отправлять постбэки в Convertro для любого пользователя, который загружает приложение, или выберите **Выкл.**

Нажмите кнопку **Сохранить.**

<div id="in-app-event-settings" />

### Настройки внутренних событий приложения

[![](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)

В этом разделе можно сопоставить события AppsFlyer с Convertro посредством постбэков.

1. Снова введите имя клиента, идентификатор сайта и URL страницы.
2. Включите переключатель «Постбэки по внутренним событиям приложения».
3. В поле «Вариант отправки» выберите значение, которое будет использоваться для всех событий, определенных в SDK.  
   **- Только события, атрибутированные этому партнеру**: партнер будет получать сведения о событиях **только** тех пользователей, которые ему атрибутированы.  
    **- События, атрибутированные любому партнеру или органические**: партнер будет получать сведения о событиях всех пользователей, которые есть в вашей базе.
4. Чтобы добавить в список событие, определенное в SDK, нажмите **Add Event** (Добавить событие).
5. Введите следующие параметры:

| Имя параметра | Description(Описание) |
| --- | --- |
| **Имя события в SDK** | Название события, полученное AppsFlyer либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор ID каждого события, заданные со стороны Convertro.  <br />Получите соответствующий идентификатор ID события в Convertro и укажите его в текстовом поле. |
| **Отправка данных о доходе** | **Если флажок снят** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Если флажок установлен** — AppsFlyer отправляет все параметры, включая значение дохода (если оно присутствует в событии). |

Нажмите **Save** (Сохранить).

После сохранения этой конфигурации AppsFlyer начинает отправлять в Convertro следующие данные для каждой органической и неорганической установки:

* Параметры Converto
* Идентификатор устройства Device ID для Android и iOS
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.
* Время клика
* IP-адрес пользователя
* User Agent.
* Идентификатор пользователя клиента (необязательно, если настроено)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Convertro.

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

Разрешения недоступны для Convertro.

</Accordion>

<div data-zendesk-anchors="h_01H9FK64HSFKW54BBRVB3W9ZR0=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-convertro=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-convertro h_01H9FK64HS75VDP07DGETASAH7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-convertro h_01H9FK64HSK1B1Y9BRWP7AN96R=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FK64HS7VJWHF1QCWNYVBX8=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK64HSCAYHB82DZX0JA2ZX=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 obtaining-the-client-name-page-url-site-id-from-the-convertro-platform=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-client-name-page-url--site-id-%D0%BD%D0%B0-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-convertro h_01H9FK64HSKR8N45RXQQC3VEW1=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-client-name-page-url--site-id-%D0%BD%D0%B0-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-convertro default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK64HTPK69QQ92DJ55RNVM=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK64HTGKXWW0FMN0T445FG=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK64HTCM3H0243FVFDY0ET=attribution-link-tab h_01H9FK64HT9JHKBN5W8H16E6CK=cost-tab h_01H9FK64HTSP070RX7ZCYM7KE3=ad-revenue-tab h_01H9FK64HTCXAMY6TR186EE0M9=permissions-tab" />
