---
title: Руководство по интеграции атрибуции People-Based
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-08-18T00:23:58Z'
  id: 360013821097
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360013821097
---
> **Краткий обзор.** Контрольный список для настройки PBA

## Настройка PBA

Настройка PBA состоит из нескольких действий, описанных здесь и перечисленных в следующей таблице.

* Обратитесь к своему менеджеру по работе с клиентами или торговому представителю AppsFlyer, чтобы включить PBA.
* Сгруппируйте цифровые свойства бренда в группу брендов.
* Интегрируйте веб-SDK на свой веб-сайт и мобильный SDK в свое приложение.
* AppsFlyer собирает и атрибутирует данные.
  * Данные собираются из нескольких разных источников.
  * Зарегистрированные данные делятся на точки взаимодействия и события.
  * События связаны с последним непрямым посещением веб-сайта за последние 30 дней.
  * Рекламодатели могут обозначать некоторые события как события конверсии. Например, покупки. События конверсии анализируются на дэшбордах.
  * Сырые данные используются для выполнения пользовательского анализа данных.
* Анализируйте путь клиента для оптимизации кампаний.

### Этапы настройки PBA

Прежде чем начать, свяжитесь с вашим менеджером по работе с клиентами или торговым представителем AppsFlyer, чтобы включить PBA. Затем начните настройку. Задачи по настройке подробно описаны в таблице. Загрузите эту <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">электронную таблицу</Anchor>, чтобы фиксировать в ней прогресс.

**Практические рекомендации:** Внедрите <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">CUID</Anchor> в приложении и на вашем сайте. AppsFlyer получит CUID, когда пользователь зарегистрируется или войдет в систему.

<table><thead><tr><th> </th><th>Ответственность</th><th>Действия</th><th>Примечания</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>Рекламодатель </p></td><td><ul><li> <span><a href="./adding-an-app-to-appsflyer" target="_blank">Добавьте веб-приложение</a> в свой аккаунт AppsFlyer. Веб-приложение указывает URL-адрес веб-сайта, для которого вы хотите измерить трафик, и </span>применяется для предотвращения <a href="./pba-media-source-attribution-rules" target="_blank">самостоятельной атрибуции</a>.</li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">Настройте пакеты бренда</a>; они объединяют в себе цифровые активы бренда (мобильные приложения и веб-приложение).</span> </li><li>Укажите дополнительные <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">исключенные домены</a>.</li></ul></td><td><ul><li><span>Аналитические отчеты и отчеты объединяются внутри бренда.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> Вебмастер </td><td><ul><li>Установите <a href="./pba-web-sdk-integration-guide" target="_blank">веб-SDK</a> на веб-сайт, определенный веб-приложением. </li><li>Настройте веб-SDK следующим образом:  <ul><li>Запись посещений</li><li>Запись событий</li><li><mark> Установка <a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a> </mark></li><li>Тестовое внедрение с помощью <a href="./test-pba-web-sdk-integration" target="_blank">инструмента для тестирования SDK</a> </li></ul></li></ul></td><td><ul><li><span>SDK записывает посещения и события.</span></li><li><span>Интеграция полностью поддерживается через Google Tag Manager (GTM), Adobe или Tealium.</span></li><li> <strong>Обязательно:</strong>  Вызовите SetCustomerUserID() сразу после того, как пользователь зарегистрируется или войдет в систему. Если у вас нет CUID, обсудите альтернативные варианты со своим менеджером по работе с клиентами. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>Рекламодатель</p></td><td><p>Убедитесь, что веб-мастер использовал <a href="./test-pba-web-sdk-integration" target="_blank">инструмент для тестирования SDK</a> для проверки того, что веб-сайт, для которого настроен SDK, выполняет следующее:</p><ul><li>Запись посещений</li><li>Запись событий</li><li>Установка CUID</li></ul></td><td><p><mark> Рекламодатель! Не продолжайте, пока этот шаг не будет завершен.  </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>Разработчик и рекламодатель</p></td><td><p>[Необязательно] <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">API межсерверных событий</a></p></td><td>Для отражения таких событиях, как автоматическое продление подписки</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>Рекламодатель</p></td><td><ul><li> <span>Отметьте </span>события конверсии: <ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">Веб-события</a></span></li><li><span>[Необязательно] <a href="./pba-brand-bundles-and-settings#inapp-event-settings" target="_blank">Внутренние события мобильного приложения</a>.</span></li></ul></li></ul></td><td><ul><li><span>Прежде чем делать это, дождитесь завершения ежедневной \* обработки.</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>Рекламодатель</p></td><td><p>Использование дэшбордов</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Атрибуция веб-сайтов</a></li><li><a href="./pba-web-assisted-installs" target="_blank">Web-Assisted Installs</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>Рекламодатель</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Настройте Data Locker</a></td><td><p>Предоставляет доступ к отчетам PBA по необработанным данным, включая точки взаимодействия, стандартные события и события конверсии, а также специализированные отчеты для установок, на которые повлияло посещение веб-сайта.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>Рекламодатель</p></td><td><p>[Необязательно]<br/>Использование <a href="./pba-raw-data-reports" target="_blank">необработанных данных</a></p></td><td><p>Данные доступны после ежедневной \* обработки.</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* В связи с обработкой данные доступны через 10 часов после полуночи по всемирному координированному времени в день события . Это означает, что события понедельника доступны во вторник в 10:00 UTC. </td></tr></tbody></table>

## Сбор данных PBA через SDK / API

|  | Веб-платформа | Мобильная платформа: |
| --- | --- | --- |
| SDK (пакет средств разработки ПО) | <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide">Веб</Anchor><ul><li>SDK тегов JavaScript установлен на сайте</li><li>Отчеты о посещениях веб-сайтов и веб-событиях</li></ul> | <Anchor target="_blank" href="/marketers/ru/docs/integrate-the-appsflyer-sdk">Мобильная платформа</Anchor><ul><li>App SDK интегрирован в iOS, Android, Unity и т. д.</li><li>Сообщает об установках приложения и действиях пользователя в приложении</li></ul> |
| API межсерверных событий | <Anchor target="_blank" href="/marketers/ru/docs/web-server-to-server-events-api-for-pba-web-s2s">Межсерверные события</Anchor><ul><li>Сообщает о событиях, происходящих в бэкенд-серверах (не на Web)</li><li>Например: обновление подписки</li></ul> | <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">Мобильные межсерверные события</Anchor><ul><li>Сообщает о событиях, происходящих в бэкенд-серверах (не на Web)</li><li>Например: обновление подписки</li></ul> |

<div data-zendesk-anchors="setting-up-pba=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-pba 01H8V1XPAHGFVJRKM56S2ZQTBD=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-pba pba-setup-steps=%D1%8D%D1%82%D0%B0%D0%BF%D1%8B-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-pba 01ECF26CMN668ZZV6XNZA3W692=%D1%8D%D1%82%D0%B0%D0%BF%D1%8B-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-pba pba-dataacquisition-via-sdkapi=%D1%81%D0%B1%D0%BE%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-pba-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sdk--api 01H8V1XPAH23BV25ZCMFR7MM9Q=%D1%81%D0%B1%D0%BE%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-pba-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sdk--api" />
