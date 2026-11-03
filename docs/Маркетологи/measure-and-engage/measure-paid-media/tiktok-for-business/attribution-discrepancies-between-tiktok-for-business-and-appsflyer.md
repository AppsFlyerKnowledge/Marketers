---
title: Несоответствия в атрибуции между TikTok for Business и AppsFlyer
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-08-18T00:33:19Z'
  id: 19733501619473
  locale: ru
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ru/articles/19733501619473
---
> **Краткий обзор:** Узнайте о различиях в атрибуционных моделях между TikTok for Business и AppsFlyer.

## Обзор

Как две крупные платформы в экосистеме привлечения мобильных пользователей, TikTok for Business и AppsFlyer используют разные модели атрибуции. Это может привести к расхождениям в данных на панелях управления TikTok for Business и AppsFlyer. Мы тесно сотрудничаем с TikTok for Business, чтобы минимизировать эти расхождения, но рекламодателям следует знать о возможных причинах.

## Различия в атрибуционных моделях

В таблице ниже описаны возможные причины расхождений между TikTok Ads Manager и панелями управления AppsFlyer:

<table><thead><tr><th>Причина</th><th>Менеджер рекламы TikTok</th><th>AppsFlyer:</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Окно лукбэк на основе кликов</strong></p></td><td><p>Окно по умолчанию составляет 7 дней. Однако его можно настроить по-разному для приложений Android и для приложений, переведенных на самоатрибуцию TikTok (TikTok—SRN).</p></td><td><p>Окно по умолчанию составляет 7 дней. Окно может быть настроено в диапазоне от 1 до 30 дней. Обязательно согласуйте окно атрибуции с параметрами TikTok.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Окно лукбэк на основе просмотров</strong></p></td><td><p>Окно по умолчанию — 1 день. Однако его можно настроить по-разному для приложений Android и для приложений, переведенных на самоатрибуцию TikTok (TikTok—SRN).</p></td><td><p>Окно по умолчанию — 1 день. Окно может быть настроено в диапазоне от 1 до 48 часов. Обязательно согласуйте окно атрибуции с параметрами TikTok.</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Многоканальная атрибуция источников</strong></p></td><td><p>TikTok самостоятельно атрибутирует установки, независимо от других медиа источников.</p></td><td><p>AppsFlyer использует атрибуцию по последнему клику (Узнать больше о <a href="./appsflyer-attribution-model" target="_blank">модели атрибуции AppsFlyer</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Атрибуция на различных устройствах</strong></p></td><td><p>TikTok атрибутирует пользователей, которые используют разные устройства, такие как iOS, Android и компьютер, для вовлечения и установки.</p></td><td><p>AppsFlyer атрибутирует пользователей, выполняющих вовлечение и установку на одном устройстве.</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Различные часовые пояса</strong></p></td><td><p><a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">Часовой пояс TikTok</a> (отображается рядом с диапазоном дат) изменить нельзя. Он был настроен при создании рекламного аккаунта.</p></td><td><p>Часовой пояс приложения AppsFlyer по умолчанию — UTC+0. Чтобы соответствовать часовому поясу, указанному в TikTok Events Manager, измените часовой пояс, установленный для приложения, на <a href="./app-settings#localization-time-zone" target="_blank">странице настроек приложения</a>.</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>Атрибуция iOS</strong></p></td><td><p>Для iOS-приложений менеджер рекламы TikTok отображает только результаты атрибуции SKAN.</p></td><td><p>Для приложений iOS платформа AppsFlyer отображает результаты атрибуции SKAN, вместе с атрибуцией AppsFlyer для SRN и расширенных SRN, а также дедуплицированные данные SSOT. Только данные SKAN предполагается совпадать на обеих платформах. </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>Периоды атрибуции внутренних событий приложения</strong></p></td><td colspan="2"><p>Атрибуция на каждой платформе может отличаться в зависимости от окон периода с момента первоначальной установки:</p></td></tr><tr><td><span id="day-1-90"></span><p>День 1-90</p></td><td colspan="2"><p>Нет расхождений в атрибуции. Обе платформы связывают события в приложении с временем установки.</p></td></tr><tr><td><span id="day-91-180"></span><p>День 91-180</p></td><td rowspan="2"><p>После 90 дней внутренняя активность не учитывается в TikTok.</p></td><td><div><div><div>AppsFlyer привязывает события в приложении к времени установки.</div></div></div></td></tr><tr><td><span id="day-180"></span><p>День 180+</p></td><td><div><div><div>Из-за <a href="./user-level-data-retention#установленные-партнерами-сроки-хранения-данных" target="_blank">политики удержания данных TikTok</a> внутренние события атрибутируются как органические.</div></div></div></td></tr></tbody></table>

## Различия в установках

В некоторых случаях TikTok для бизнеса учитывает установки, которые AppsFlyer отклоняет или не признает как новые установки.

### Кампании по повторному вовлечению

Кампания по повторному вовлечению может побудить пользователей открыть уже установленное приложение (**re-engagement**). Когда AppsFlyer обнаруживает предыдущую установку приложения на том же устройстве, он рассматривает это как **реатрибуцию**.

Пользователи фиксируются в AppsFlyer как **установки для нового привлечения пользователей**, если они впервые установили приложение через кампанию по повторному вовлечению на TikTok for Business. Кроме того, если пользователи установят приложение после завершения специального <Anchor target="_blank" href="/marketers/ru/docs/set-up-re-attribution-window">Окно re-attribution</Anchor> **после первоначальной установки, они также считаются новыми приобретениями.**

С другой стороны, установки, выполненные **в пределах установленного окна реатрибуции** после первоначальной установки, классифицируются как реатрибуции. Эти установки отображаются на странице ретаргетинга AppsFlyer. Тем не менее, TikTok для бизнеса может считать их новыми установками.

### Отклоненные установки при использовании правил проверки и Protect360

<Anchor target="_blank" href="/marketers/ru/docs/implement-validation-rules-to-prevent-fraud">Правила проверки</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/protect360-anti-fraud-guide">Protect360</Anchor> — это функции AppsFlyer, которые обеспечивают защиту, отклоняя (блокируя) определенные установки. При использовании этих функций отклоненные установки из TikTok for Business блокируются AppsFlyer, хотя TikTok для бизнеса самостоятельно сообщает об этих установках.

> 📄 **Пример**
>
> Джефф, менеджер по UA компании GreatApp, создает кампанию под названием SPNA, нацеленную только на испаноязычных жителей Северной Америки. Чтобы проверить это, Джефф устанавливает правило проверки, принимающее только пользователей из Канады и США.
> Когда пользователь TikTok for Business из Испании кликает и устанавливает Приложение, TikTok for Business самостоятельно сообщает об установке, в то время как AppsFlyer отклоняет установку, которая не проходит по правилам проверки.

## Уменьшение расхождений

Хотя существуют различия в моделях атрибуции, в некоторых случаях расхождения можно сократить.

### Атрибуция по кликам и просмотрам

AppsFlyer поддерживает атрибуцию как по кликам, так и по просмотрам. Чтобы уменьшить расхождения между TikTok for Business и AppsFlyer, убедитесь, что окна лукбэк по кликам и по просмотрам согласованы с теми, которые определены в TikTok for Business.

> 📄 **Пример**
>
> Предположим, что окно лукбэк по кликам в TikTok for Business настроено в AppsFlyer на 1 день для вашего приложения `com.greatapp`, в то время как в TikTok for Business оно настроено на значение по умолчанию 7 дней. Пользователи, которые кликают на рекламу Greatapp в TikTok, но впервые запускают Приложение спустя 2–7 дней, атрибутируются как органические пользователи в AppsFlyer, в то время как TikTok for Business самостоятельно регистрирует таких пользователей.

### Атрибуция внутренних событий приложения

Различия между платформами могут также проявляться в событиях после установки (например, в покупках внутри приложения), которые отображаются как в TikTok for Business, так и в AppsFlyer. Следующая таблица описывает наиболее распространенные причины этих различий и содержит рекомендации по их уменьшению:

| Причина | Описание | Совет от AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Самоатрибуция** | TikTok всегда относит установки и события к своим собственным кампаниям, тогда как AppsFlyer относит их к источнику привлечения. Такие события обозначены как участие TikTok в AppsFlyer. | Объедините необработанные данные об атрибутированных конверсиях TikTok с необработанными данными, где TikTok является источником. |
| <span id="unmapped-events"></span>**Неотображенные события** | AppsFlyer получает события, созданные SDK (пакет средств разработки ПО), но они не сопоставляются с TikTok for Business и, следовательно, не отправляются. | Обязательно <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#постбэки-по-внутренним-событиям-приложения">сопоставляйте с TikTok for Business</Anchor> события внутри приложения, которые отображают качество пользователя. |
| <span id="unsent-revenue"></span>**Неотправленная выручка** | AppsFlyer получает выручку от событий, созданных SDK (пакет средств разработки ПО), но она не отправляется в TikTok for Business. | Не забудьте включить выручку при <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#постбэки-по-внутренним-событиям-приложения">сопоставлении внутренних событий TikTok для бизнеса</Anchor>. |
| <span id="missing-event-values-on-tiktok"></span>**Отсутствие ценностей, значения событий в TikTok для бизнеса** | AppsFlyer отправляет параметры и ценности, значения в TikTok для бизнеса в рамках сопоставления событий, если они имеют правильную структуру. | Разрабатывайте внутренние события SDK (пакет средств разработки ПО) в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure">рекомендуемыми структурами AppsFlyer</Anchor>, чтобы правильно сопоставить ценности, значения событий с TikTok для бизнеса. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HFXTVVZNJQJFAAR1F3HW1D5M=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 differences-in-attribution-models=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85 h_01HFXTVVZN79JX9E5PTXMPB8BS=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85 differences-in-installs=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0%D1%85 h_01HFXTVVZNDQKNW85BBWR0PE2Z=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0%D1%85 reengagement-campaigns=%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%BC%D1%83-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8E h_01HFXTVVZNA1R59KCA41H2YSBJ=%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%BC%D1%83-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8E rejected-installs-when-using-validation-rules-and-protect360=%D0%BE%D1%82%D0%BA%D0%BB%D0%BE%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B8-%D0%B8-protect360 h_01HFXTVVZNJVFHE0W5DTP5PDCG=%D0%BE%D1%82%D0%BA%D0%BB%D0%BE%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B8-%D0%B8-protect360 01H890CZSYCTQZCAYAZP9TCBBF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 minimizing-discrepancies=%D1%83%D0%BC%D0%B5%D0%BD%D1%8C%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9 h_01HFXTVVZNW9GZB8QYMR1KTNMN=%D1%83%D0%BC%D0%B5%D0%BD%D1%8C%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9 clickthrough-and-viewthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC-%D0%B8-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HFXTVVZNN45WY997DK9K8WA4=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC-%D0%B8-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HFRQMF6HTT84J4EDFXZMK7CP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 inapp-event-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HFXTVVZNG7TKQVY1229X594G=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F" />
