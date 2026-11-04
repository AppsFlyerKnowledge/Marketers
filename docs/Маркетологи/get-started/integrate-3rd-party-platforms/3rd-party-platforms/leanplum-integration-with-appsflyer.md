---
title: Интеграция Leanplum с AppsFlyer
metadata:
  keywords:
    - Leanplum
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
  created_at: '2016-08-08T13:41:18Z'
  edited_at: '2026-08-28T00:10:47Z'
  id: 211487846
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/211487846
---
> **Кратко:** Leanplum — интегрированный партнер AppsFlyer — это платформа мобильного маркетинга, предназначенная для интеллектуального взаимодействия. Ее интегрированное решение обеспечивает вовлеченность через рассылку и in-app опыт. Leanplum предлагает рассылку, автоматизацию, редактирование приложения, персонализацию, A/B-тестирование и аналитику.

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-leanplum" />

## Настройка Leanplum

Клиенты Leanplum могут интегрироваться с AppsFlyer, отправляя в Leanplum постбэк, содержащий информацию о паблишере. Это позволяет просматривать эти данные в аналитике Leanplum, а также использовать их для таргетинга в A/B-тестах или маркетинговых кампаниях с помощью меню таргетинга и сегментации Leanplum.

Перед активацией интеграции с AppsFlyer необходимо сначала убедиться, что в вашей интеграции Leanplum используется тот же идентификатор устройства, что и в AppsFlyer. Это важно, поскольку Leanplum сопоставляет установку пользователя с постбэком по идентификатору устройства, поэтому, если они не совпадают, Leanplum не сможет передавать данные.

По умолчанию Leanplum собирает IDFV для iOS и MD5-хеш MAC-адреса для Android, но это можно легко изменить на IDFA для iOS и GAID для Android одной строкой кода. Чтобы узнать, как изменить формат идентификатора устройства для Android и iOS, нажмите <Anchor target="_blank" href="https://docs.leanplum.com/docs/which-device-id-format-should-i-use">здесь</Anchor>.

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом посещении** здесь вам нужно перевести кнопку ***Активация партнера*** в положение «Включено», чтобы включить настройку параметров вкладки интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
    Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне конфигурации Leanplum используется только вкладка **Интеграция**.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** этого раздела необходимо включить переключатель ***Активировать партнера***, чтобы настроить параметры на вкладке «Интеграция». Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="general-settings" />

### Общие настройки

**ID приложения и ключ клиента**

Leanplum подключается к AppsFlyer с помощью уникального ID приложения и ключа клиента. Если у вас их еще нет, для продолжения интеграции вы должны получить их от Leanplum или выполнить следующие шаги.

![Leanplum_msc_new_3.png](https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png)

**Отправка IDFA или IDFV**

Если эта опция активна, в постбэке отправляется IDFV. Если IDFV не найден, в качестве резервного варианта отправляется IDFA.

Если эта опция неактивна, в постбэке отправляется IDFA. Если IDFA не найден, в качестве резервного варианта отправляется IDFV.

Если ни один из них недоступен, постбэк не отправляется.

<div id="obtaining-the-app-id-and-client-key" />

### Получение ID приложения и ключа клиента

Нажмите на свое имя в правом верхнем углу экрана и выберите **Настройки приложения**

![](https://files.readme.io/fcb9bb4fab1eec1db130904c2c4856529f58582bd8c9c04f08200ed82c0fcb80-206117303.png)

Выберите приложение и нажмите **Ключи & настройки**

[![](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)

![](https://files.readme.io/cd638732b197f03c6194b8bae7b8f726a6e4c16661702fdad48054a35ce333e5-206117343.png)

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки об установках пользователей Leanplum. В этом разделе можно определить отправку этих постбэков.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Выберите **События, атрибутированные любому партнеру или органически**, чтобы отправлять постбэки в Leanplum для любого пользователя, который загрузил приложение.

Нажмите кнопку **Сохранить.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Leanplum.

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

Разрешения для Leanplum недоступны.

</Accordion>

<div id="viewing-user-attribution-data-in-leanplum" />

## Просмотр данных атрибуции пользователя в Leanplum

После настройки интеграции между Leanplum и AppsFlyer вы сможете получить доступ к этой информации с помощью меню таргетинга и сегментации Leanplum:

[![](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)

Это меню доступно в разделах «Аналитика», «Сообщения», «A/B-тесты» и «Пользователи» платформы Leanplum. В разделе Аналитика вы можете фильтровать, группировать и формировать когорты по этим данным, в разделе Пользователи — фильтровать по этим данным, а в Аналитике и A/B-тестах — использовать эти данные для таргетинга.

<div data-zendesk-anchors="h_01H9FKB51R253NAXWEKSYVRZ3P=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- setting-up-leanplum=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-leanplum h_01H9FKB51RA35X0G19ZPN2KAQ7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-leanplum h_01H9FKB51VVVS5C4WEQ4FKHH4H=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKB51VY7QASRV8XW8KRZK1=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKB51VA8A6XZYM3W6AVNMH=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 obtaining-the-app-id-and-client-key=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-id-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 h_01H9FKB51VFGCW21AG0BYWGFXZ=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-id-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKB51V63GPAS3R1GBWNTWR=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKB51VR8160P1RQK994DGZ=attribution-link-tab h_01H9FKB51VEJWHZXKENFASR9NG=cost-tab h_01H9FKB51V7C44MGTWR3RNX4D8=ad-revenue-tab h_01H9FKB51VY9V478W297NB58EM=permissions-tab viewing-user-attribution-data-in-leanplum=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-leanplum h_01H9FKB51VHAYS1STK6GQE4515=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-leanplum" />
