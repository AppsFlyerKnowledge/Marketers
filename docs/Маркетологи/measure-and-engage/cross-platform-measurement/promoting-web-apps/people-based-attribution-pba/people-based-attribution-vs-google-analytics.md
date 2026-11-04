---
title: Атрибуция People-Based (PBA) vs. Google Аналитика
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T15:03:02Z'
  id: 360001305617
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360001305617
---
> **Краткий обзор**. Различия между атрибуцией People-based (PBA) и Google Аналитикой.

<div id="pba-compared-to-google-analytics" />

## Сравнение PBA и Google Аналитики

И атрибуция People-Based (PBA), и Google Аналитика — это решения для веб-аналитики и измерения конверсии. Каждое из них фокусируется на своих аспектах измерений. PBA также предлагает дополнительные преимущества.

* PBA — независимый, беспристрастный инструмент атрибуции, который фокусируется на измерении атрибуции. PBA связывает конверсии и доходы с медиа-источниками и кампаниями, которые привлекают пользователей на ваш сайт.
* Google Аналитика больше фокусируется на веб-аналитике. Решение собирает, анализирует и агрегирует данные, связанные с поведением пользователей. Так, с помощью Google Аналитики вы можете анализировать поведение пользователей, воронки и веб-события.

<div id="benefits-of-pba-over-google-analytics" />

### Преимущества PBA перед Google Analytics

PBA имеет следующие преимущества перед Google Analytics:

* PBA включает в себя:
  * Измерение web-to-app. Эта метрика говорит вам, сколько пользователей переходят с вашего веб-сайта на ваше приложение. Кроме того, она сообщает, с каких медиа-источников и кампаний на ваш веб-сайт приходят пользователи, которые затем устанавливают ваше приложение.
  * <Anchor target="_blank" href="/marketers/ru/docs/pba-raw-data-reports">Сырые данные для конверсий и событий</Anchor>, которые вы можете использовать в своих собственных системах бизнес-аналитики. Это дает вам возможности и ресурсы для собственного анализа.

<div id="reasons-for-differences" />

### Откуда берутся различия

Если вы сравниваете данные из PBA и Google Analytics, различия в данных имеют следующие причины.

<div id="sdk-implementation" />

#### Использование в SDK

То, как вы используете PBA и Google Analytics, может повлиять на сбор данных.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics показывает больше сеансов и посетителей.">

<div id="cause" />

#### Причина

Если Google Analytics загружается раньше, чем веб-SDK, пользователи, которые сразу уходят с сайта, или пользователи, которые проводят короткие периоды времени на вашем сайте, не учитываются в PBA. Это вызывает расхождения в данных по сеансам и посетителям.

<div id="solution" />

#### Решение

Мы настоятельно рекомендуем размещать веб-SDK так, чтобы он загружался как можно раньше.

Независимо от того, <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#integrating-the-web-sdk-into-the-website">загружаете ли вы SDK непосредственно или через Google Tag Manager,</Anchor> поздняя загрузка SDK может вызвать значительные расхождения.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics показывает больше данных по сессиям, кампаниям и конверсиям.">

<div id="cause-1" />

#### Причина

Веб-SDK присутствует только на определенных страницах. Google Analytics присутствует на всех страницах. В результате Google Analytics собирает данные со всего вашего веб-сайта, тогда как веб-SDK собирает данные только с определенных страниц. Это приводит к расхождениям в данных по сеансам, посетителям, кампаниям и конверсиям.

<div id="solution-1" />

#### Решение

Внедрите веб-SDK на всех страницах вашего сайта.

</Accordion>

<div id="dashboard-settings" />

### Настройки панели управления

Настройки панели управления, такие, как часовой пояс или фильтр по дате, могут оказывать влияние на то, какие данные вам предоставляются.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Настройки часового пояса — расхождения в данных.">

<div id="cause-2" />

#### Причина

Если настройки часового пояса в Google Analytics отличаются от настроек в панели управления PBA, вы можете столкнуться с расхождениями.

<div id="example" />

> 📄 **Пример**
>
> Ваша панель управления AppsFlyer сконфигурирована на UTC, а ваша панель управления GA сконфигурирована на UTC +13. Это значит, что ваша панель управления GA опережает вашу панель управления AppsFlyer на день.
>
> Поэтому данные, которые выводятся на дэшборд AppsFlyer за 2 марта, появятся на вашем дэшборде GA, только если вы выберете в фильтре по датам 3 марта.

<div id="solution-2" />

#### Решение

Убедитесь, что настройки часового пояса в AppsFlyer и Google Analytics одинаковы.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Фильтры по данным— расхождения в данных.">

<div id="issue" />

#### Проблема

Как AppsFlyer, так и Google Analytics позволяют вам фильтровать данные по дате, атрибутированным медиа-источникам, кампаниям и событиям. Различные фильтры в AppsFlyer и Google Analytics могут создавать разные представления для одних и тех же данных.

<div id="solution-3" />

#### Решение

При сравнении данных с панелей управления убедитесь, что к данным не применяются фильтры.

</Accordion>

<div id="conversions-and-events" />

### Конверсии и события

Различные модели атрибуции, окна атрибуции, способ отправки событий, настройки файлов cookie — все это может влиять на сбор и обработку данных.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Окно атрибуции — расхождения при измерении конверсии.">

<div id="cause-3" />

#### Причина

Если у вас настроены разные окна атрибуции в Google Analytics и PBA, могут возникнуть расхождения в данных по атрибуции.

<div id="solution-4" />

#### Решение

В PBA окно атрибуции всегда 30 дней. При <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">выборе модели атрибуции</Anchor> убедитесь в том, чтобы в Google Analytics установлено окно атрибуции также в 30 дней.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Модель атрибуции — расхождения при измерении конверсии.">

<div id="cause-4" />

#### Причина

Различные модели атрибуции в PBA и Google Analytics могут приводить к расхождениях в данных об атрибуции.

<div id="solution-5" />

#### Решение

Google Analytics предлагает <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">модели атрибуции по умолчанию</Anchor>, из которых вы можете выбирать. Однако PBA работает по модели атрибуции последнего непрямого взаимодействия с окном атрибуции в 30 дней. Выберите в Google Analytics модель атрибуции последнего непрямого взаимодействия.

</Accordion>

<div id="sending-events" />

<Accordion title="Отправка событий">

<div id="issue-1" />

#### Проблема

И Google Analytics SDK, и веб-SDK позволяют отправлять события. Если вы реализуете одну логику для отправки событий в Google Analytics, а другую — для отправки событий в PBA, могут возникнуть расхождения.

<div id="solution-6" />

#### Решение

Когда вы отправляете события, проверьте следующее:

* Убедитесь, что один и тот же триггер применяется к обоим инструментам
* Убедитесь, что вы отправили событие и в Google Analytics, и в PBA

Нажмите <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#principles-of-event-recording">здесь</Anchor>, чтобы узнать, как отправлять события через веб-SDK.

</Accordion>

<div id="cookies" />

<Accordion title="Файлы сookie">

И PBA, и Google Analytics используют файлы cookie для распознавания пользователей.

<div id="cookie-settings-in-google-analytics" />

#### Настройки файлов cookie в Google Analytics

Хотя рекомендуется, чтобы Google Analytics SDK автоматически обрабатывал настройки файлов cookie, вы все равно можете <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">настраивать и изменять параметры файлов cookie</Anchor>. Любое изменение настроек файлов cookie может привести к расхождению.

<div id="setting-cookie-expiration" />

#### Установка срока действия файла cookie

Google Analytics позволяет настраивать срок действия файлов cookie. Если вы установите срок действия файла cookie в Google Analytics так, что он будет истекать до истечения срока действия файла cookie в веб-SDK, это может привести к расхождениям.

<div id="example-1" />

> 📄 **Пример**
>
> Марк является постоянным посетителем вашего сайта уже более года и рассматривает возможность подписки на премиум-контент.
>
> Ваш разработчик установил срок действия файла cookie Google Analytics в один год. Однако веб-SDK устанавливает срок действия файла cookie в два года.
>
> Когда Марк наконец подписывается и конверсия регистрируется, cookie-файл Google Analytics больше не действует, и вместо него создается другой файл cookie.
>
> Конечным результатом является то, что Google Analytics показывает двух пользователей, каждый из которых Марк, и только у одного из них есть конверсия. PBA, однако, показывает одного пользователя и для Марка, и того пользователя, с которым связана конверсия.
>
> Это означает, что ваш коэффициент конверсии в Google Analytics ниже, чем в PBA.

<div id="setting-cookie-subdomain" />

#### Настройка cookie для поддомена

Google Analytics позволяет устанавливать файлы cookie для поддоменов, тогда как PBA устанавливает файлы cookie только для домена верхнего уровня.

<div id="example-2" />

> 📄 **Пример**
>
> Вы устанавливаете cookie на поддомен **store.mywebsite.com**. Света заходит на ваш сайт, а затем заходит в ваш интернет-магазин по адресу **store.mywebsite.com**. Google Analytics считает ее **двумя разными пользователями** .
>
> Так как PBA устанавливает cookie на домене верхнего уровня **mywebsite.com**, он считает Свету в **mywebsite.com** и **store.mywebsite.com** одним и тем же пользователем.
>
> Конечный результат — два пользователя в Google Analytics и один пользователь в PBA.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-pba-%D0%B8-google-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8 benefits-of-pba-over-google-analytics=%D0%BF%D1%80%D0%B5%D0%B8%D0%BC%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D0%B0-pba-%D0%BF%D0%B5%D1%80%D0%B5%D0%B4-google-analytics reasons-for-differences=%D0%BE%D1%82%D0%BA%D1%83%D0%B4%D0%B0-%D0%B1%D0%B5%D1%80%D1%83%D1%82%D1%81%D1%8F-%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F sdk-implementation=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2-sdk cause=%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D0%B0 solution=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5 cause::49d3e519=%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D0%B0-1 solution::447e7ac9=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-1 dashboard-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F cause::30244d2c=%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D0%B0-2 solution::f1a0e066=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D0%B0 solution::df8f3921=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-3 conversions-and-events=%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F cause::b346571c=%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D0%B0-3 solution::4bb14ac9=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D0%B0-4 solution::b2be4a33=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-5 issue::b412f5ba=%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D0%B0-1 solution::39b4d7d6=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-6 cookie-settings-in-google-analytics=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%84%D0%B0%D0%B9%D0%BB%D0%BE%D0%B2-cookie-%D0%B2-google-analytics setting-cookie-expiration=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D1%81%D1%80%D0%BE%D0%BA%D0%B0-%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-cookie setting-cookie-subdomain=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-cookie-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0" />
