---
title: Интеграция Localytics с AppsFlyer
metadata:
  keywords:
    - Localytics
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
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-08-28T00:10:52Z'
  id: 210748626
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/210748626
---
> **Краткий обзор:** Localytics — интегрированный партнер AppsFlyer и маркетинговая и аналитическая платформа для мобильных и веб-приложений. Аналитика приложений Localytics предоставляет когортный анализ удержания, воронки, сегментацию клиентов и анализ в реальном времени, помогая выявлять группы пользователей с самым высоким уровнем лояльности и наибольшей пожизненной ценностью. Маркетинг приложений Localytics предоставляет приложениям сервисы автоматизации маркетинга за счет измерения долгосрочной эффективности кампаний по привлечению клиентов и отправки насыщенных и полезных in-app- и push-сообщений релевантным клиентам в момент, когда они могут оказать наибольшее воздействие.

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

## Настройка Localytics

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Окно конфигурации Localytics содержит 4 вкладки: **Интеграция, Ссылка атрибуции, Обогащение данных** и **Разрешения**. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

### Активация партнера

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

[![](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)

### Общие настройки

**Идентификатор ID атрибуции**

Localytics подключается к AppsFlyer через уникальный идентификатор атрибуции. Если у вас его еще нет, для продолжения интеграции вы должны получить его в Localytics или выполнить следующие шаги.

![Localytics_msc_new_3.png](https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png)

Получение ключа приложения Localytics в Localytics

* Войдите в дэшборд Localytics
* Нажмите **Атрибуция** на панели слева
* Выберите **Сторонняя атрибуция**
* Скопируйте ключ атрибуции

[![](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)

Настройте Localytics в дэшборде AppsFlyer.

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Localytics после установки пользователем. В этом разделе можно определить отправку этих постбэков.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Выберите **События, атрибутированные любому партнеру или органически**, чтобы отправлять постбэки в Localytics для любого пользователя, который загрузил приложение.

После завершения настройки AppsFlyer отправляет в Localytics следующие данные для каждой органической и неорганической установки:

* Идентификатор устройства (IDFA / Google Advertising ID)
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.

Нажмите кнопку **Сохранить.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Localytics.

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

Разрешения недоступны для Localytics.

</Accordion>

## Просмотр данных атрибуции в консоли Localytics

Перейдите на экран настроек атрибуции Localytics и включите атрибуцию третьих сторон в Localytics, чтобы видеть данные AppsFlyer.

[![](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)

[![](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)

<div data-zendesk-anchors="h_01H9FKCBM5W16BYJQ6TH9SSBVC=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-localytics=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-localytics h_01H9FKCBM5Z39GPE5772799DB1=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-localytics h_01H9FKCBM5JZ5V4YMB6S24JA6V=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKCBM5PSZZ5FP1G12M9F63=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKCBM5N4RB5ZSB61W02368=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKCBM5STZ79NBP3EFYGMB9=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKCBM54S067F1Z51E4FXQD=attribution-link-tab h_01H9FKCBM591RG57Q80JZ7FJWY=cost-tab h_01H9FKCBM5Q8P53V34QRQMS0BS=ad-revenue-tab h_01H9FKCBM5GGXX04JEH3DHNV78=permissions-tab viewing-the-attribution-data-in-the-localytics-console=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-localytics h_01H9FKCBM5VBM87C2PHNZVZ4RJ=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-localytics" />
