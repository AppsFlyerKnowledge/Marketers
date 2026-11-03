---
title: >-
  Измерение эффективности кампаний по повторному вовлечению пользователей при
  помощи push-уведомлений
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-08-18T00:36:05Z'
  id: 207364076
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/207364076
---
> **At a glance:** Измеряйте кампании push-уведомлений на устройствах iOS и Android.

## Обзор

AppsFlyer поддерживает измерение кампаний push-уведомлений от всех push-провайдеров, а также кампаний, реализованных непосредственно на базе Firebase Cloud Messaging или Apple Push Notification Services (APNS).

Есть два возможных способа реализовать интеграцию:

* С помощью шаблонов OneLink (рекомендуется).
* Отправив объект JSON с ключом `af` в полезной нагрузке push-уведомления (устарело).

Конверсии отображаются на обзорном дэшборде, в ретаргетинге или объединенных представлениях.

## Как это работает?

После того как вы выполните все шаги, описанные в этой статье, ваше приложение будет работать следующим образом:

1. Вы запускаете push-уведомление, содержащее шаблон OneLink **или** ключ `af` в его полезной нагрузке.
2. Пользователь приложения получает push-уведомление и нажимает на него.
3. Приложение загружается, и запускается SDK AppsFlyer.
4. SDK обрабатывает полезную нагрузку push-уведомления, которое открыло приложение.
5. SDK извлекает и отправляет данные атрибуции в AppsFlyer.

В сценарии OneLink, если OneLink настроен на направление пользователя на определенный экран в приложении, запускается диплинкинг.

## Необходимые условия

Прежде чем продолжить, убедитесь, что ваше приложение имеет <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide">интегрированный SDK AppsFlyer</Anchor>  **и** может получать push-уведомления.

## Шаги

Чтобы настроить измерение push-уведомлений, необходимо выполнить следующие шаги:

1. [Создайте push-уведомление](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification), содержащее пользовательский ключ данных с шаблоном OneLink **или** ключ `af` с объектом JSON в качестве значения.
2. [Настройте SDK для получения пользовательского ключа](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (выполняется разработчиком приложения).
3. [Протестируйте интеграцию](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration), запустив push-уведомление.
4. [Просматривайте эффективность кампаний push-уведомлений](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) на дэшборде.

<div id="1-creating-the-push-notification" />

<Accordion title="1. Создание push-уведомления">

Сначала создайте push-уведомление, содержащее данные атрибуции, используя один из следующих методов.

> 📘 **Note**
>
> **Примечание**
>
> В следующем примере мы используем Firebase в качестве push-провайдера. Инструкции должны быть применимы к любому push-провайдеру, с небольшими отличиями (если таковые имеются). Обратитесь к документации соответствующего push-провайдера.

<Tabs>
<Tab title="Использование OneLink (рекомендуется) Использование JSON (устарело)">

#### **Использование OneLink (рекомендуется)**

Это рекомендуемый метод для интеграции AppsFlyer с push-уведомлениями.

1. Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">ссылку OneLink и настройте ее на ретаргетинг.</Anchor>  
   **Примечание**: поддерживаются как короткие, так и длинные URL-адреса OneLink.
2. В пользовательских данных push-уведомления добавьте ссылку OneLink, содержащую данные атрибуции, которые вы хотите отправлять в AppsFlyer.

> 📘 **Note**
>
> **Пример Firebase**
>
> В Firebase:
>
> ![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png">

<div id="using-json-legacy" />

#### **Использование JSON (устарело)**

> 📘 **Note**
>
> **Примечание**
>
> Ниже приводится документация по устаревшему методу интеграции AppsFlyer с push-уведомлениями, которая доступна для целей обратной совместимости. Если вы настраиваете новое приложение, используйте [рекомендованное решение на базе OneLink](/docs/measuring-push-notification-re-engagement-campaigns#использование-onelink-рекомендуется).

В пользовательских данных push-уведомления добавьте пользовательский ключ `af`, который содержит данные атрибуции, которые вы хотите отправлять в AppsFlyer в формате JSON. Требуются следующие параметры атрибуции:

* `pid`
* `is_retargeting`
* `c`

> 📘 **Note**
>
> **Пример Firebase**
>
> В Firebase:
>
> ![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. Настройка SDK">

Эта задача требует изменения кода приложения. Следуйте инструкциям по настройке SDK:

* При внедрении рекомендованного решения на базе OneLink:
  1. сообщите разработчику приложения, как называется пользовательский ключ, который вы добавили к уведомлению. В нашем примере это `af_push_link`.
  2. Отправьте ему <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">эти инструкции</Anchor>.
* При реализации устаревшего решения на базе JSON отправьте своим разработчикам <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">эти инструкции</Anchor>.

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. Тестирование интеграции">

Чтобы проверить, что измерения push-уведомлений интегрированы корректно, просто запустите push-уведомление в кампании, которую вы настроили в Шаге 1.

Если все настроено правильно, SDK будет делать следующее:

1. Прослушивать push-уведомления.
2. Обрабатывать данные атрибуции, встроенные в push-уведомление, и отправлять их в AppsFlyer.
3. Выполнять стандартный диплинкинг, если измерение push-уведомлений реализовано с помощью OneLink.

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. Просмотр кампаний push-уведомлений на дэшборде">

Данные, полученные из push-уведомлений, можно увидеть на <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide#retargeting-dashboard">дэшборде Ретаргетинг</Anchor>.

**Примечание**: AppsFlyer устраняет дублирование данных push-уведомлений. То есть если AppsFlyer несколько раз получает идентичные полезные нагрузки, учитывается только одна.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J5XFSEG9DR31DP73KTAGQPFW=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 how-does-it-work=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01J5XFSEG967HXNT3GFSC2AQYE=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01J5XFSEG91SER3JKB3RKK6B6G=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F steps=%D1%88%D0%B0%D0%B3%D0%B8 h_01J5XFSEG9W3RTP62NW7SV4D0F=%D1%88%D0%B0%D0%B3%D0%B8 h_01J5XFSEG9PXHTD4C9XCDC01DH=1-creating-the-push-notification using-onelink-recommended=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-onelink-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F h_01J5XFSEG9W73JYPHH9VRZSTZ8=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-onelink-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy h_01J5XFSEG9GYMKAT27AWTN1WZZ=2-configuring-the-sdk h_01J5XFSEG91NH41QMV9K3S4F18=3-testing-the-integration h_01J5XFSEG904NC72K8MWX9YM06=4-viewing-push-notification-campaigns-in-the-dashboard" />
