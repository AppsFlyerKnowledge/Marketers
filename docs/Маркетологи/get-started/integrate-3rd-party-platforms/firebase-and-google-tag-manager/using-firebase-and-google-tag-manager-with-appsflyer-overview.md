---
title: Использование Firebase и Google Tag Manager с AppsFlyer — Обзор
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2026-08-18T00:13:12Z'
  id: 210353513
  locale: ru
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ru/articles/210353513
---
> **Краткий обзор**. Отправка событий, о которых сообщается через SDK Firebase, в AppsFlyer с помощью Google Tag Manager.

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

Интеграция AppsFlyer с Google Tag Manager (GTM) и Firebase позволяет разработчику отправлять внутренние события приложения в Firebase с помощью SDK Firebase, и затем эти события будут отправлены в AppsFlyer через SDK с помощью Google Tag Manager. Это позволяет не отправлять одно и то же событие дважды.

События, отправленные с помощью GTM, моделируются на основе внутренних событий AppsFlyer. Имя события, параметры и структура одинаковы. Если у вас уже есть GTM в вашем приложении, использовать его для отправки событий в AppsFlyer очень просто.

Используйте шаги и инструкции в этом руководстве для отправки событий. 

<div id="considerations" />

### Соображения

* **Источник события в сырых данных**: в отчетах по сырым данным для событий, генерируемых GTM, источник установлен на S2S. Это может привести к некоторой путанице, поскольку события сообщаются через SDK.
* **Обновление значения конверсии SKAdNetwork**: события, генерируемые GTM и сообщаемые в SDK, как описано в данном руководстве, заставляют SDK обновлять значение конверсии способом, аналогичным обычным событиям SDK. Нужно просто включить и задать <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">настройки измерения SKAdNetwork</Anchor>.

<div id="note" />

> 📘 **Примечание**
>
> * В настоящее время интеграция Google Tag Manager не поддерживает отправку в AppsFlyer следующих параметров:
>   * <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">Идентификатор клиента</Anchor>
>   * `att`
>   * `os`Обратите внимание:
>   * При отправке постбэков о внутренних событиях приложения в SRN требуется параметр `att`.
>   * При отправке постбэков о внутренних событиях приложения в Meta Ads требуются параметры `att` и `os`.

<div id="prerequisites" />

### Необходимые условия

Прежде чем вы сможете начать отправлять события в AppsFlyer с помощью GTM, вам необходимо внедрить SDK GTM в свое приложение. Вам нужны:

1. Вам нужен [аккаунт GTM](https://www.google.com/analytics/tag-manager/).
2. Вам необходимо настроить интеграцию GTM + Firebase для вашего приложения (см. инструкции для [Android](https://developers.google.com/tag-manager/android) и [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/ru/docs/integrate-the-appsflyer-sdk">Интегрируйте SDK AppsFlyer</Anchor>, если вы еще не сделали этого.

Как только все будет готово, приступайте к <Anchor target="_blank" href="/marketers/ru/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">Настройке GTM</Anchor>.

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Переход с Firebase Dynamic Links на AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7SKSCBH47YYFTKBWY3JVSV=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7SKSCBBTTWATRZ87BYRW6G=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HE7SKSCB9QHA4WEERVSWMF0P=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HE7SQQG2VJW9179Q77PTZFPH=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
