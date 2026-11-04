---
title: Интеграция Luna Labs с AppsFlyer
metadata:
  keywords:
    - postbacks
    - integrated partner
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-08-28T00:10:54Z'
  id: 360019465017
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360019465017
---
> **Кратко:** Luna Labs — это комплексная платформа, которая позволяет своим клиентам создавать, управлять и оптимизировать плейблы и видеорекламу.

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-luna-labs" />

## Настройка Luna Labs

**Предварительные условия:** Перед настройкой интеграции обязательно свяжитесь с партнером и откройте у него аккаунт.

**Новая интеграция:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.
2. Выберите соответствующее приложение.
3. Найдите Luna Labs и выберите **Integrate**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    Оставьте его включенным на все время работы с Luna Labs.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

**Изменение существующей интеграции:**

В AppsFlyer перейдите на вкладку **Collaborate > Partner Integrations > Active integrations** , найдите партнера и внесите изменения.

<div id="integration" />

## Интеграция

Для настройки используйте вкладку «Интеграция». Остальные вкладки неактивны.

<div id="note" />

> 📘 **Примечание:**
>
> Luna Labs не использует собственные ссылки атрибуции. Они получают постбэки от рекламных сетей, которые проводят кампании для рекламодателей. Luna Labs получает постбэки только для собственных креативов и только те постбэки, которые включают параметр и значение `af_addpb=1`. См. дальнейшее объяснение ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** необходимо включить **Активировать партнера**, чтобы настроить параметры вкладки интеграции. **Этот переключатель должен быть активирован все время, пока вы работаете с партнером**.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Luna Labs после установок пользователей.

**Примечание:** Luna Labs может получать постбэки только для собственных креативов.

**Чтобы отправлять постбэки в Luna Labs:**

1. Убедитесь, что рекламная сеть, с которой вы работаете вместе с Luna Labs, активирована и интегрирована с AppsFlyer.
2. Убедитесь, что рекламная сеть добавляет параметр `af_addpb=1` в ссылку атрибуции, которую рекламная сеть отправляет в AppsFlyer и в Luna Labs.  
   Этот параметр включает отправку постбэка в Luna Labs и сообщает им, что клик был по их креативу.
3. Выберите **События, атрибутируемые любому партнеру или органические**.

Например, если рекламная сеть X работает с определенным приложением (id1234567890) и хочет отправлять постбэки в Luna Labs, URL-адрес должен выглядеть так:

```http
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```

<div data-zendesk-anchors="h_01H9FKCW1FJ2QCVVE6HEE640H9=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- setting-up-luna-labs=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-luna-labs h_01HJR5M5C0P759S4X5SSJCY501=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-luna-labs integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01H9FKCW1FE6JCY5FAFF3Y4TGH=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01H9FKCW1FNPCF1M7SRWTMNDCW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKCW1FV00605GYK498JZN9=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKCW1FGMA3FKAY5B9YCJVH=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E" />
