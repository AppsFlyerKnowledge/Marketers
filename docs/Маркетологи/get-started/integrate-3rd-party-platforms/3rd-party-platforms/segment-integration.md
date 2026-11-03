---
title: Интеграция Segment
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
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
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-08-18T00:12:37Z'
  id: 210041606
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/210041606
---
> **Краткий обзор.** Отправляйте данные аналитики Segment в AppsFlyer.

## Введение

Segment позволяет легко отправлять данные в AppsFlyer. После записи данных в библиотеках Segment с открытым исходным кодом эти данные переводятся и направляются в AppsFlyer в соответствующем формате. AppsFlyer помогает маркетологам точно определить таргетинг, оптимизировать расходы на рекламу и повысить ROI.

## Интеграция Segment с AppsFlyer

Следуйте <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">этому руководству от Segment</Anchor>, чтобы узнать, как интегрировать Segment с AppsFlyer.

## Вопросы и ответы

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="Как интегрировать Segment с AppsFlyer?">

Чтобы интегрировать Segment с AppsFlyer, выполните следующие действия:

* <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Настройте дэшборд Segment</Anchor> для подключения к AppsFlyer
* Внедрите [обертку Segment SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work) в свое приложение:
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">Нативный iOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">Нативный Android</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="Какие SDK необходимо добавить в приложение?">

Вам нужно только добавить обертку Segment SDK. Когда вы добавляете зависимость для обертки Segment SDK, процесс сборки приложения автоматически добавляет Segment SDK и AppsFlyer SDK в ваше приложение.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="Как работает обертка SDK?">

Обертка Segment SDK соединяет Segment SDK и AppsFlyer SDK.

Когда вы используете обертку Segment SDK для вызова методов Segment для записи установок и событий в приложении, обертка SDK вызывает методы как Segment, так и AppsFlyer.

Это сэкономит ваше время и усилия и потребует меньше написания кода.

> ❗️ **Предупреждение**
>
> методы как из обертки Segment SDK, так и из AppsFlyer SDK. Это может привести к ошибкам и расхождениям в данных.
>
> **Используйте только методы из обертки Segment SDK.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Есть ли разница в функциональности между оберткой Segment SDK и AppsFlyer SDK?">

Нет, функциональность не изменится. Все функции AppsFlyer SDK доступны в обертке Segment SDK.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="Я не вижу данных о событиях в приложении на дэшборде AppsFlyer">

* Обязательно следуйте инструкциям по реализации метода отслеживания в обертке Segment SDK:
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">Android;</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">https://support.appsflyer.com/hc/article_attachments/360016192917</Anchor>
* Убедитесь, что <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">вы указали свой ключ разработчика</Anchor> при интеграции AppsFlyer на дэшборде Segment.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Данные об установках и событиях в приложении в Segment и AppsFlyer не совпадают">

Убедитесь, что вы используете только обертку Segment SDK. Не комбинируйте обертку Segment SDK с AppsFlyer SDK. Более подробную информацию смотрите [здесь](/docs/segment-integration#how-does-the-sdk-wrapper-work).

[В вопросах выше](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) также указаны причины, по которым данные между Segment и AppsFlyer могут не совпадать.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="Я получаю ошибку проверки при тестировании событий в Segment">

Когда вы тестируете события с помощью ***тестера событий*** на странице ***Пункт назначения***, вы можете получить ошибку: ***Ошибка проверки: для отправки событий с сервера на сервер необходим идентификатор устройства AppsFlyer ('integrations.AppsFlyer.appsFlyerId')***.

Эта ошибка не означает, что есть проблема с интеграцией между Segment и AppsFlyer. Тестер событий (Event Tester) позволяет протестировать отправку с сервера на сервер из Segment в AppsFlyer. Любое событие, отправляемое с сервера на сервер, требует AppsFlyerID, поэтому тестер событий выдает ошибку.

Однако это актуально только для межсерверных событий. Когда вы используете API в Segment SDK для записи событий, события отправляются из SDK как в Segment, так и в AppsFlyer. В вызов API AppsFlyer включается идентификатор устройства AppsFlyer.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="Я использую сторонний инструмент аналитики. Нужно ли интегрировать его с AppsFlyer и Segment?">

Нет, вы должны использовать только дэшборд Segment для включения сторонних инструментов аналитики.

</Accordion>

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01JZMD855TA62KQ4AWJ5F6WSDP=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 integrating-segment-with-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-segment-%D1%81-appsflyer h_01JZMD855TNEYZG1MDZY7FWV8S=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-segment-%D1%81-appsflyer faqs=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B h_01JZMD855TAEBDPAMEAEH66F27=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />
