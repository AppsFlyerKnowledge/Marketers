---
title: агрегированные данные Pull API
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-08-27T00:03:57Z'
  id: 207034346
  locale: ru
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ru/articles/207034346
---
> **Краткий обзор.** Использование Pull API для получения агрегированных отчетов AppsFlyer в виде файлов CSV.

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

<div id="looking-for-pull-api-raw-data" />

> 👍 **Вам нужны сырые данные Pull API?**
>
> Узнайте все о них <Anchor target="_blank" href="/marketers/ru/docs/pull-api-raw-data">здесь</Anchor>.

<div id="pull-api-aggregate-data" />

## агрегированные данные Pull API

* Pull API позволяет получать агрегированные отчеты по привлечению пользователей (UA) и ретаргетингу в виде файлов CSV.
* <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">Показатели актуальности данных</Anchor> такие же, как в аналогичном отчете на странице «Экспорт данных» и на обзорном дэшборде. Обратите внимание, что затраты могут обновляться с задержкой в несколько часов, в зависимости от партнера, предоставляющего данные о затратах.
* Доступна фильтрация по медиа-источнику и диапазону дат.
* Дополнительные возможности в Pull API:
  * Добавление типа взаимодействия для атрибуции
  * Выбор часового пояса

<div id="aggregate-performance-reports-available-via-pull-api" />

#### Сводный отчет об эффективности доступен через Pull API

<table><thead><tr><th>Категория</th><th> UA</th><th>Ретаргетинг\*</th></tr></thead><tbody><tr><td>Партнеры (медиаисточник)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Партнеры — по датам</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Ежедневно</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Геоданные</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Отчеты по геоданным — по датам</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3">\* Для отчетов по ретаргетингу добавьте в URI атрибут <code><span>&amp;reattr=true</span></code>. </td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Использование Pull API для агрегированных данных">

**Чтобы использовать Pull API для агрегированных данных**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Получите токен API. Получить токен должен админ.
2. Дайте разработчику токен API, который будет использоваться в заголовке аутентификации.
3. Предоставьте разработчикам [параметры](/docs/pull-api-aggregate-data#parameters), которые они должны ввести при вызове API, как описано в следующем разделе. Параметры определяют, что содержится в отчете, как он организован, а также устанавливают временные рамки отчетности.
4. Скажите разработчику, чтобы он следовал инструкциям по <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API для агрегированных данных</Anchor> в хабе для разработчиков.

</Accordion>

<div id="parameters" />

<Accordion title="Параметры">

| Параметр | Описание |
| --- | --- |
| app\_id (идентификатор приложения) | Идентификатор приложения |
| from (от) | <ul><li>Диапазон дат задается параметрами `from`и `to` . Под диапазоном понимается диапазон дат LTV (установки).</li><li>Формат: `yyyy-mm-dd`,</li><li>Пример: 2010-01-01</li></ul> |
| to (по) | Дата окончания. Так же, как и параметр `from` |
| медиа-источник | Используйте для ограничения (фильтрации) по определенному медиа-источнику.<ul><li>Например:`media_source=facebook`</li></ul> |
| attribution\_touch\_type | Установите этот параметр, как показано в примере, чтобы получить ключевые показатели [эффективности атрибуции](/docs/pull-api-aggregate-data) (VTA).<br /><br />Пример: `attribution_touch_type=impression`<br /><br />Некоторые ключевые показатели эффективности VTA, такие как клики, показы и API затрат, не имеют связанных значений и отображают значение N/A. |
| currency (валюта) | Валюта дохода и затрат.<br /><br />Агрегированные отчеты Pull API всегда используют валюту приложения. |
| reattr | Получить данные по конверсии ретаргетинга.<ul><li>[По умолчанию] Если установлено значение false, возвращаются кампании с данными о пользователях (UA).</li><li>Если установлено значение true, возвращаются данные по конверсии ретаргетинга.</li><li>**Пример**:`reattr=true`</li></ul> |
| Time Zone (Часовой пояс) | [По умолчанию] Данные предоставляются по часовому поясу UTC.<ul><li>Шаблоны URI заполняются с помощью параметра часового пояса, установленного для часового пояса приложения.</li><li>[По умолчанию] Если параметр не передан, данные предоставляются по часовому поясу UTC.</li><li>Если вы отправляете `timezone=[Joda-Time]`, данные предоставляются с использованием часового пояса приложения.</li></ul>Примечания о выборе часового пояса<ul><li>Формат часового пояса Joda-Time учитывает переход на летнее время.</li><li>Значение Joda-Time должно совпадать со значением в настройках приложения. Например, если установлен часовой пояс Парижа, значение часового пояса в Pull API URL должно быть таким:  `timezone=Europe%2fParis`.</li><li>Данные в выбранном часовом поясе доступны для извлечения только с даты установки этого часового пояса. Данные, предшествующие дате изменения, отображаются в часовом поясе UTC.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Ограничения и особенности">

| Специфика | Комментарии |
| --- | --- |
| Необходимый тип токена API | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">Токен V2.0</Anchor> |
| Доступ рекламной сети | Н |
| Доступ агентств | Д |
| Прозрачность агентства | Д |
| Валюта приложения | Д |
| Часовой пояс приложения | Д |
| затраты | Данные о затратах доступны только по кампаниям UA и не доступны по ретаргетинговым и неактивным кампаниям (кампаниям без установок). |
| Актуальность данных | <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Непрерывно</Anchor> |
| Исторические данные | Агрегированные данные LTV доступны за период до 25 месяцев (2 года + 1 месяц) |
| Неорганические данные | Д |
| органические данные | Д |
| Ограничение предоставления данных | <Anchor target="_blank" href="/marketers/ru/docs/report-generation-quotas-rate-limitations">Ограничения</Anchor> |
| Ограничения на размер | <ul><li>Pull API поддерживает до 1 млн строк сырых данных. Pull API для **агрегированных данных** может агрегировать до 1 млн строк сырых данных.</li><li>Вызов API возвращает максимум 200 тысяч строк.<ul><li>Если в отчете ровно 200 тысяч строк, стоит предположить, что какие-то строки отсутствуют.</li><li>Сделайте несколько API-вызовов, используя параметры from/to с указанием времени.</li></ul></li></ul> |
| Изменения названия кампании | Отчеты через Pull API не поддерживают изменения названия кампании |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/aggregated-and-analytics-reporting-overview">Описания и примеры агрегированных отчетов</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/aggregated-and-analytics-reporting-overview">Выбор подходящего инструмента доставки данных для агрегированных данных</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=%D0%B2%D0%B0%D0%BC-%D0%BD%D1%83%D0%B6%D0%BD%D1%8B-%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-pull-api pull-api-aggregate-data=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-pull-api h_01HE0YP829WD5TDFHTPYAV30QN=%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-pull-api aggregate-performance-reports-available-via-pull-api=%D1%81%D0%B2%D0%BE%D0%B4%D0%BD%D1%8B%D0%B9-%D0%BE%D1%82%D1%87%D0%B5%D1%82-%D0%BE%D0%B1-%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%B5%D0%BD-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01HE0YP829EQ7N6CST352X917H=%D1%81%D0%B2%D0%BE%D0%B4%D0%BD%D1%8B%D0%B9-%D0%BE%D1%82%D1%87%D0%B5%D1%82-%D0%BE%D0%B1-%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%B5%D0%BD-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
