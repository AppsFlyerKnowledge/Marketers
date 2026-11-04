---
title: Когортный API
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-08-18T00:03:01Z'
  id: 360004799057
  locale: ru
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ru/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Когортный API (Cohort API) предоставляет рекламодателям программный способ получения данных когорт. Используйте API для интеграции данных по когортам в системы бизнес-аналитики и автоматизации маркетинга.

<div id="cohort-api" />

## Когортный API

Когортный API используется для получения когортных данных об эффективности кампаний с платформы AppsFlyer. Функционально он эквивалентен <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">когортному дэшборду</Anchor>.

Чтобы использовать когорты и удержание, вы определяете данные, которые хотите просмотреть. Необходимо выбрать пользователей из приложения и сегментировать их по времени конверсии. Доступны такие метрики когортного анализа, как доход, ROI и коэффициент конверсии событий. Для сравнения когорта может быть разбита по таким показателям, как кампания и медиа-источник. Результат возвращается в виде файла CSV или JSON. Вы можете использовать эти результаты, чтобы обнаруживать закономерности или изменения эффективности в течение жизненного цикла пользователя или кампании.

См. <Anchor target="_blank" href="https://www.appsflyer.com/ru/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Сценарии когортного анализа</Anchor>.

**Как использовать Когортный API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Получите <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">токен API</Anchor>. Получить токен должен администратор.
2. Передайте своему разработчику токен API, который будет использоваться в заголовке аутентификации.
3. Предоставьте разработчикам [параметры](#filtering-and-grouping-parameters), которые они должны ввести при вызове API, как описано в следующих разделах. Параметры определяют, что содержится в отчёте, как он организован, а также устанавливают временные рамки отчётности.
4. Попросите своего разработчика следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">инструкциям для Когортного API</Anchor> в разделе для разработчиков.

<div id="filtering-and-grouping-parameters" />

<Accordion title="Параметры когортного API">

Для получения необходимых данных используйте следующие параметры.

| Название параметра | Описание | Необязательно |
| --- | --- | --- |
| <span id="bearer"></span>bearer | Токен API, используемый в заголовке аутентификации API. | Да |
| <span id="cohort-_type"></span>cohort \_type | Тип атрибуции когорты (конверсии) один из следующих:`user_acquisition`, `retargeting`, `unified`<ul><li>Объединённая: объединённая эффективность кампаний по привлечению пользователей и ретаргетингу.</li><li>Если событие атрибутировано и к ретаргетингу, и к кампаниям по привлечению пользователей, то в возвращаемые KPI включается только событие ретаргетинга, что означает is\_primary=true.</li><li>форматирования ячеек с затратами;</li><li>Например: `"cohort_type": "user_acquisition"`</li></ul> | Да |
| <span id="min_cohort_size"></span>min\_cohort\_size | Минимальный размер когорты используется для уменьшения количества возвращаемых записей за счёт исключения когорт с небольшим количеством пользователей. Это означает, что значение KPI «пользователи» должно быть равно или больше указанного.<ul><li>Формат: Целое число</li><li>Минимально допустимое значение: 1. Не отправлять 0 (ноль)</li><li>По умолчанию: 1</li><li>Например: `"min_cohort_size": 50`</li></ul> | Нет |
| <span id="from"></span>from (от) | Нижняя граница диапазона дат атрибуции LTV. Самая ранняя дата: 720 дней до текущей даты.<ul><li>Формат: строка гггг-мм-дд</li><li>Пример: `"from": "2020-01-02"`</li></ul> | Да |
| <span id="to"></span>to (по) | Верхняя граница диапазона дат атрибуции LTV<ul><li>Количество дней в диапазоне: 1-31 дней</li><li>За один день: значения `from` и `to` идентичны.</li><li>Формат: гггг-мм-дд</li><li>Пример: `"from": "2020-01-01", "to": 2020-01-31` составляет 31 день.</li></ul> | Да |
| <span id="granularity"></span>granularity | Почасовая детализация для предыдущих 72 часов, если задать `"granularity": "hour"` и установить диапазон `from` и `to` по времени суток.<ul><li>Формат: гггг-мм-дд чч:мм:сс</li><li>Пример:</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | Нет |
| <span id="partial_data"></span>partial\_data | Во избежание искажения и неверной интерпретации данных, в когорту возвращаются данные за полные дни. Однако данные о неполных днях могут быть также полезны.<br /><br />Количество полных дней когорты для запроса рассчитывается как разница между сегодняшней датой и датой *to* (до).<ul><li>[По умолчанию] Если выбрано «false», то возвращаются полные дни.</li><li>Если «true», то возвращается до 180 дней когорты, включая дни с неполными данными.</li><li>Формат: логический</li><li>Версия пользовательского интерфейса платформы: false</li></ul>**Пример**: 10 мая количество полных дней когорты для пользователей, совершивших конверсию в период с 1 по 30 апреля, равно 10.<ul><li>Если выбрано «false» [по умолчанию], то возвращаются дни когорты 0-9. Это количество дней (10) между последней датой конверсии и сегодняшним днем.</li><li>Если выбрано «true», то возвращаются дни когорты 1-40. Дни 11-40 содержат неполные данные и не возвращаются. Например, с 20 апреля прошло всего 20 дней и т.д.</li></ul>**Примечание**: Частичные данные допускаются только в том случае, если выбран кумулятивный тип агрегирования данных. | Нет |
| <span id="filters"></span>filters | Фильтрация возвращаемых данных и дней выбранного периода. Выберите фильтры из [списка фильтров для показателей](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Формат: Строки в вложенном JSON. Значения должны быть в массиве.</li><li>**Пример ограничения по определённым регионам:** `"filters": {"geo": ["US"]}` включает только пользователей, атрибутированных в США.</li><li>**Пример периода (когорты) в днях**: Фильтр `period` устанавливает дни, по которым возвращаются меры. Возможные значения: 0-180</li><li>По умолчанию: Если фильтр периодов не установлен, то возвращаются дни 0-30, 60, 90 и 180. [Пример фильтра с периодом](/docs/cohort-api#using-period-filters)</li></ul> | Нет |
| <span id="groupings"></span>groupings | <ul><li>Чтобы включить дополнительные столбцы и сделать отчеты менее детализированными, используйте параметры группировки.</li><li>Выберите 1-7 группировок из [списка группировки показателей](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Формат: Строки в массиве</li><li>Пример: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Да |
| <span id="kpis"></span>KPI's | KPI – это метрики, используемые для получения информации о работе вашего приложения. [Узнайте, как выбирать и форматировать KPI](/docs/cohort-api#selecting-and-formatting-kpis) | Да |
| <span id="preferred_currency"></span>preferred\_currency | Параметр, который устанавливает формат возвращаемых KPI. [Подробнее о форматировании KPI](/docs/cohort-api#форматирование-функций-kpi) | Нет |
| <span id="preferred_timezone"></span>preferred\_timezone | Параметр, который устанавливает формат возвращаемых KPI. [Подробнее о форматировании KPI](/docs/cohort-api#форматирование-функций-kpi) | Нет |
| <span id="aggregation_type"></span>aggregation\_type | Параметр, который устанавливает формат возвращаемых KPI. [Подробнее о форматировании KPI](/docs/cohort-api#форматирование-функций-kpi) | Да |
| <span id="per_user"></span>per\_user | Параметр, который устанавливает формат возвращаемых KPI. [Подробнее о форматировании KPI](/docs/cohort-api#форматирование-функций-kpi) | Нет |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Выбор и форматирование KPI">

* В таблице перечислены доступные KPI и связанные с ними функции. При вызове KPI возвращаются все его функции.
* Всегда возвращаются следующие KPI: users (пользователи), ecpi, и cost (затраты)
* Выберите один дополнительный KPI для каждого вызова.
* Для каждого запрашиваемого KPI возвращаются все функции.
* Формат: Строки в массиве
  * Пример A: `"kpis": ["sessions"]`
  * Пример B: `"kpis": ["event_name"]`

<table><thead><tr><th> </th><th> </th><th colspan="5">Функции</th></tr><tr><th rowspan="2">По умолчанию/ Необязательно </th><th rowspan="2">KPI (название параметра) </th><th>Количество</th><th>cvr (коэффициент конверсии)</th><th>Коэффициент</th><th>Сумма</th><th>Уникальные пользователи</th></tr><tr><th>Число</th><th>Процент</th><th>Процент</th><th>Число</th><th>Число</th></tr></thead><tbody><tr><td>Всегда</td><td>польз.</td><td><span>Д</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Всегда</td><td>ecpi</td><td>-</td><td>-</td><td>-</td><td><span>Д</span></td><td>-</td></tr><tr><td>Всегда</td><td>Данные о затратах</td><td>-</td><td>-</td><td>-</td><td><span>Д</span></td><td>-</td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td> <code>"event_name"</code>(4) </td><td><span>Д</span></td><td><span>Д</span></td><td>-</td><td><span>Да (3)</span></td><td><span>Д</span></td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td>выручка</td><td><span>Д</span></td><td>-</td><td>-</td><td><span>Д</span></td><td>-</td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td>roas</td><td>-</td><td>-</td><td><span>Д</span></td><td>-</td><td>-</td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td>roi</td><td>-</td><td>-</td><td><span>Д</span></td><td>-</td><td>-</td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td>sessions (сеансы)</td><td><span>Д</span></td><td>-</td><td><span>Д</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>НЕОБЯЗАТЕЛЬНОЕ</td><td>uninstalls (2)</td><td><span>Д</span></td><td>-</td><td><span>Д</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) Уникальные сессии возвращаются при <em>aggregation_type = on_day</em></p><p>(2) Недоступно, если cohort_type=unified </p><p>(3) Сумма означает общий доход, принесённый событием. В отчете это обозначается как <code>sum_event_name"</code></p><p>(4) Важно! Названия событий чувствительны к регистру.</p></td></tr></tbody></table>

<div id="formatting-kpi-functions" />

#### Форматирование функций KPI

Следующие параметры задают формат возвращаемых KPI.

| Параметр | Значения | Необязательно |
| --- | --- | --- |
| preferred\_currency | Валюта дохода KPI<ul><li>Если true, то доход возвращается с использованием <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-currency">валюты приложения</Anchor>, заданной на платформе.</li><li>[По умолчанию] Если false, то результаты возвращаются в долларах США.</li><li>Формат: логический</li><li>Версия пользовательского интерфейса платформы: true</li></ul> | Нет |
| preferred\_timezone | **Часовой пояс диапазонов дат**<ul><li>Если true, то время будет выражаться с использованием <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">часового пояса приложения</Anchor>, заданного на платформе.</li><li>[По умолчанию] Если false, то время выражается с использованием часового пояса UTC.</li><li>Формат: логический</li><li>Версия пользовательского интерфейса платформы: true</li></ul> | Нет |
| aggregation\_type | <ul><li>`Кумулятивный`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`форматирования ячеек с затратами;` | Да |
| per\_user | Функция KPI делится на количество пользователей приложения. Применяется только к соответствующим KPI.<ul><li>Если true, то значения KPI делятся на количество пользователей в когорте.</li><li>Если значение false, то значения KPI не делятся на количество пользователей.</li><li>Формат: логический</li><li>Пример, если true: общий доход составляет $1000, количество пользователей приложения – 500, возвращаемое значение – $2.</li></ul> | Нет |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Группировка по и фильтрация">

<table><thead><tr><th>Название параметра </th><th>Значение API параметра</th><th>Группировки</th><th>Фильтры</th></tr></thead><tbody><tr><td>Реклама</td><td>af_ad</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Идентификатор рекламы</td><td>af_ad_id</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Кампания</td><td>c</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Идентификатор кампании</td><td>af_c_id</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Канал</td><td>af_channel</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Медиа-источник</td><td>pid</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Cубпараметр 1</td><td>af_sub1</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Ключевые слова</td><td>af_keywords</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Агентство</td><td>af_prt</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Тип конверсий (1) </td><td>cohort _type</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Идентификатор сайта</td><td>site_id (идентификатор сайта)</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Тип дохода (2)</td><td>тип_выручки</td><td><span>X </span></td><td><span>Д</span></td></tr><tr><td>Атрибутированный тип взаимодействия (3)</td><td>attributed_touch_type (атрибутированный тип взаимодействия)</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Группа объявлений</td><td>af_adset</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Идентификатор группы объявлений</td><td>af_adset_id</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Страна</td><td>геолокация</td><td><span>Д</span></td><td><span>Д</span></td></tr><tr><td>Дата (дата установки / повторной атрибуции / повторного вовлечения в контексте выбранного типа когорты (cohort_type)) </td><td>дата</td><td><span>Д</span></td><td><span>X </span></td></tr><tr><td>Период</td><td><p>Период</p><p><a href="./cohort-api#using-period-filters">Подробное объяснение</a></p></td><td><span>X</span></td><td><span>Д</span></td></tr><tr><td colspan="4"><p>Примечания: </p><p>Опции параметров:</p><p>(1) Тип конверсии:  <code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> и <code>re-attribution</code>), <code>unified</code></p><ul><li>При экспорте:<ul><li> <code>re-engagement</code> будет отображаться как <code>retargeting</code> </li><li> <code>re-attribution</code> будет отображаться как <code>reattr</code> </li></ul></li></ul><p>(2) Тип дохода: <code>regular</code>, <code>ad_monetization</code><span></span></p><p>(3) Атрибутированный тип взаимодействия: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## Дополнительные сведения

<div id="using-period-filters" />

<Accordion title="Использование фильтров периодов">

Период относится к дню после атрибуции, где период 0 – это день атрибуции. Например, пользователь устанавливает приложение 1 января. Это день атрибуции. Покупка, совершенная в период 0, означает, что она была совершена 1 января. Покупка, совершенная в период 3, означает, что она была совершена 4 января. Аналогично, если пользователь устанавливает приложение 11 января, эта дата становится периодом 0. Покупка, сделанная 14 января, будет периодом 3.

Если диапазон дат отчёта с 1 по 11 января, то в отчёт попадают пользователи, атрибутированные (установившие приложение) в этот период. Другие данные не включаются.

* Значение периода может быть одним или несколькими из следующих 0-180. Например, 0, 1, 2, 30, 180.
* Если период не указан, то по умолчанию возвращаются значения 0, 1, 2 и так далее до 30, 60, 90 и 180.

<div id="example-period-filter" />

> 📄 **Пример фильтра периодов**
>
> * Этот пример содержит параметры запроса JSON, сырые данные и итоговый CSV-файл.
> * В запросе *отфильтрованы периоды* 0, 1 и 2, а в качестве KPI выбирается *доход*.
> * В запросе указывается тип агрегации как «кумулятивный». Измените на «on\_day», если вы хотите получать данные день в день.
> * В результате возвращаемые данные содержат:
>   * показатели пользователей, затрат и ecpi, которые всегда возвращаются;
>   * показатели дохода, состоящие из суммы и количества для каждого периода, под которыми понимаются периоды 0, 1 и 2.
>
> **Запрос**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **Сырые данные**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Результаты**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика | Замечания |
| --- | --- |
| Доступ к рекламной сети | Нет |
| Доступ агентств | Нет |
| Часовой пояс конкретного приложения | Да |
| Валюта приложения | Да |
| Ограничения по размеру | Ничего |
| Ограничение предоставления данных | <ul><li>Лимит частоты вызовов API: 60 вызовов в минуту и 50 000 вызовов в день на один аккаунт.</li><li>Запросы возвращают до 30 000 строк.</li></ul> |
| Органические данные | Доступно |
| Неорганические данные | Доступно |
| Ограничение по данным о затратах | <ul><li>Данные о затратах приводятся только для кампаний, в которых зарегистрирована хотя бы одна установка.</li><li>AppsFlyer не предоставляет данные о затратах для ключевых слов, содержащих заглавные буквы, в когортном отчёте или когортном API</li><li>Нельзя объединить некоторые комбинации группировок с затратами. Например, Meta Ads может предоставить группировку либо по региону, либо по каналу, но не по обоим параметрам сразу. Точная комбинация группировок зависит от рекламной сети.</li></ul> |
| Обновление данных | Обновление данных зависит от [partial\_data](/docs/cohort-api#partial_data) следующим образом:<ul><li>[По умолчанию] Если false, то <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#daily">ежедневно</Anchor>.</li><li>Если true, то <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">непрерывно (в реальном времени)</Anchor>.</li><li>Метрики затрат и удалений обновляются ежедневно во всех случаях.</li></ul> |
| Исторические данные | Ежедневные когорты: 2 года |
| Доступ для пользователей аккаунта | Токен авторизации доступен пользователям-администраторам на дэшборде |
| Доход от рекламы | Для событий af\_ad\_revenue метрика уникальных пользователей недоступна при указанном ниже типе агрегации данных:<ul><li>«Кумулятивный» (Cumulative).</li><li>«В день» (On day) для дат между 5 октября 2022 года и 16 февраля 2023 года.</li></ul> |
| Группировки по неделям и месяцам | Группировка по параметрам недели и месяца недоступна в когортном API. Используйте дэшборд когорт. |
| Период когортного API | <ul><li>Период конверсии обозначается как 0 (час 0 или день 0). Следующий период после конверсии обозначается как 1 (час 1 или день 1) и т.д.</li><li>В AppsFlyer период когорты не учитывает конкретную временную метку установки. Часы работы когорты округляются до ближайшего часа, а дни работы когорты определяются на основе календарного дня. Это может привести к расхождениям при сравнении данных когорты AppsFlyer с данными других сетей, где все периоды когорты определяются по конкретной временной метке установки (то есть час – это 60 минут после установки, а день – это 24 часа после установки и т.д.).</li></ul> |
| Даты | <ul><li>Даты или диапазоны дат относятся к датам жизненного цикла клиента <Anchor target="_blank" href="/marketers/ru/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">(LTV)</Anchor>, то есть к дате атрибуции (конверсии) пользователя, а не к дате самой активности.</li><li>Самая ранняя поддерживаемая дата: За 730 дней до текущей даты. То есть 2 года.</li><li>Максимальный диапазон запроса: 60 дней.</li></ul> |
| Повторные установки | <ul><li>Если события после переустановки считаются неатрибутированными органическими:<ul><li>Они включены только с 26 мая 2024 года. <Anchor target="_blank" href="/marketers/ru/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Узнать больше</Anchor></li><li>Время установки определяется на основе поля <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Они не учитываются в подсчётах уникальных пользователей и показателях удержания.</li></ul></li><li>Если события после переустановки отнесены к первой установке, они всегда учитываются. <Anchor target="_blank" href="/marketers/ru/docs/unique-users">Узнать больше</Anchor></li></ul> |
| Когортный API для партнёров | Доступ к когортному API для маркетинговых партнёров прекращён с 15 сентября 2024 года. Маркетинговым партнёрам рекомендуется <Anchor target="_blank" href="/partners/ru/docs/data-locker-reports-for-api-partners">активировать Data Locker</Anchor>, чтобы обеспечить постоянный доступ к данным клиентов. |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D0%B9-api 01H7WFZR41YAQX4MFPBMJD1MBP=%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D0%B9-api 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9-kpi 01H7WFZR43HFF65TSWG1AN0JTB=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9-kpi 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HMY09W324E54VPZWPJVS2KB8=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%B0-%D0%BF%D0%B5%D1%80%D0%B8%D0%BE%D0%B4%D0%BE%D0%B2 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
