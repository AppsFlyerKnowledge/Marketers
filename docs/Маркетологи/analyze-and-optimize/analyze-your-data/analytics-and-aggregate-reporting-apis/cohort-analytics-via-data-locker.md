---
title: Когортная аналитика через Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-08-19T00:02:42Z'
  id: 4408945472529
  locale: ru
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ru/articles/4408945472529
---
> **Краткий обзор**: Когортная аналитика в Data Locker содержит агрегированные данные по всем элементам иерархии рекламы. Отчеты содержат данные по атрибуции пользователей за предыдущие 365 дней. Этот отчет доступен рекламодателям, у которых в рамках подписки есть необработанные данные или API когорты (или и то, и другое). Это означает, что для этого отчета не требуется подписка на Data Locker.

## Когортная аналитика в Data Locker

В некоторых случаях необработанные данные атрибуции в AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">ограничены</Anchor> из-за политик обмена данными медиа-источников или ваших <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">политик сохранения конфиденциальности.</Anchor> Ограничение затрагивает все поля, связанные с атрибуцией, такие как кампания и набор объявлений. Когортные отчеты предоставляют агрегированные данные, которые можно использовать в качестве альтернативы необработанным данным.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">Скачать пример отчёта</Anchor>

<div id="enable-data-locker" />

<Accordion title="Включение Data Locker">

Отчет доступен подписчикам Data Locker, API для создания когортных отчетов (Cohort API) и отчетов по необработанным данным. Чтобы включить отчет в <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Data Locker,</Anchor> выполните одно из следующих действий.

| Получаете ли вы в настоящее время данные через Data Locker? | Процедура |
| --- | --- |
| Да | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Чтобы добавить когортные отчёты в Data Locker:<ol><li>В AppsFlyer в боковом меню выберите **Отчёт > Data Locker**.</li><li>Выберите все отчеты в разделе **Когортная аналитика**.</li><li>Нажмите **Сохранить конфигурацию**.<br />Отчеты будут доступны на следующий день до 10:00 UTC.</li></ol> |
| Нет | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Чтобы настроить Data Locker**:<ol><li>Завершите первоначальную настройку Data Locker (<Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#set-up-data-locker">рекламодатель</Anchor> \| <Anchor target="_blank" href="/partners/ru/docs/data-locker-for-partners">партнер</Anchor>).</li><li>Добавьте когортные отчеты в Data Locker:<ol><li>В AppsFlyer в боковом меню выберите **Отчёт > Data Locker**.</li><li>Выберите все отчеты в разделе **Когортная аналитика**.</li><li>Нажмите **Сохранить конфигурацию**.<br />Отчеты будут доступны на следующий день до 10:00 UTC.</li></ol></li></ol> |

</Accordion>

Вы можете загрузить данные в свои системы бизнес-аналитики и использовать их в процессах оценки и оптимизации кампаний.

**Доступные метрики**

Доступные показатели включают выручку, уникальных пользователей, совершивших событие, и количество событий. Для расчета метрик, связанных с затратами, таких как ROI и ROAS, вам нужны метрики выручки и затрат. Показатели доходов находятся в Cohort, а показатели затрат предоставляются <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

<div id="facts" />

<Accordion title="Факты о когортной аналитике">

| Доступные отчеты | Для загрузки доступны следующие отчеты. Типы отчетов подробнее описаны в <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard#cohort-principles">когортном дэшборде</Anchor>.<ul><li>**Привлечение пользователей:** атрибуция медиа-источнику, включая LTV в период повторного вовлечения.</li><li>**Ретаргетинг:** приписывается медиа-источнику ретаргетинга для событий, происходящих:<ul><li>во время окна повторного вовлечения.</li><li>в результате реатрибуции,</li></ul></li><li>**Унифицировано:** отображает данные медиа-источника последнего взаимодействия, приводящего пользователя, согласно правилам <Anchor target="_blank" href="/marketers/ru/docs/resolve-retargeting-double-attribution">двойной атрибуции</Anchor> AppsFlyer. Это значит, что суммарная прибыль, полученная от пользователей в рамках повторных вовлечений, отображается под медиа-источником ретаргетинга, а не под медиа-источником привлечения пользователей (UA).</li></ul> |
| --- | --- |
| Отчетный период | Пользователи, совершившие конверсию в течение предыдущих 365 дней. Другими словами, каждый день отчеты включают в себя пользователя, совершившего конверсию за предыдущие 365 дней. |
| Структура отчета | Схема отчета (включенные в него показатели и метрики) фиксирована и не подлежит редактированию. См. [структуру отчета](/docs/cohort-analytics-via-data-locker#report-structure). |
| Доставка отчетов | См. [Включение когортных отчетов в Data Locker](/docs/cohort-analytics-via-data-locker#enable-data-locker). |
| Обновление данных | <ul><li>Ежедневно.</li><li>Метрики рассчитываются на основе данных, доступных в полночь по UTC. Другими словами, в конце дня.</li><li>Отчеты доступны в Data Locker в папке даты и времени (dt) до 10:00 UTC. Например, данные за понедельник доступны во вторник в 10:00 UTC в папке «Понедельник».</li></ul> |
| Влияние политики партнеров по хранению данных | Учтите, что некоторые партнеры проводят политику хранения данных. В этом случае события, произошедшие после окончания периода удержания, считаются органическими в когортных отчетах.<br /><br />Пример: SRN A придерживается политики хранения данных в течение 180 дней. События пользователя до 180-го дня приписываются к SRN A. События, происходящие после 180 дней, считаются органическими. |

</Accordion>

<div id="report-structure" />

<Accordion title="Структура отчета">

Отчет состоит из показателей и метрик.

Формат полей следующий:

* **Измерения**: Строка. Максимальная длина строки является динамической и в большинстве случаев зависит от того, как вы заполняете элементы рекламной иерархии.
* **Показатели**: Число. **Примечание:** Формат поля selected\_currency — это строка.

#### Аспекты

<Table>
  <thead>
    <tr>
      <th>
        Имя поля
      </th>
      <th>
        Описание
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id (идентификатор приложения)
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        медиа-источник
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type (тип конверсии)
      </td>
      <td>
        Возможные значения: install, install\_unified (представляются установки в объединённом отчёте), re-engagement, re-attribution.
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type (атрибутированный тип взаимодействия)
      </td>
      <td>
        Возможные значения: click (клик), impressions (показы), pre-install (предварительная установка), unknown (неизвестно), tv (ТВ), null (пустое)
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution (дни после атрибуции)
      </td>
      <td>
        * Количество дней, прошедших с даты конверсии (не конкретная временная метка конверсии).
        * Совет! Используйте для расчета дней удержания и KPI.
      </td>
    </tr>
    <tr>
      <td>
        event\_date (дата события)
      </td>
      <td>
        * Дата выполнения пользователем данного события.
        * Формат: гггг-мм-дд
        * Пример: Дата выполнения пользователем данного события в приложении. В случае конверсии.
        * Примечание! Если event\_name равно af\_conversion, то дата события и дата конверсии будут совпадать.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date (дата конверсии)
      </td>
      <td>
        * Дата, когда произошла конверсия
        * Формат: гггг-мм-дд
        * Пример: Дата установки
      </td>
    </tr>
    <tr>
      <td>
        event\_name (название события)
      </td>
      <td>
        Обозначает событие. Некоторые имена событий имеют определенное значение, другие относятся к внутренним событиям, заданным рекламодателем в приложении. 

        | event\_name (название события) | Что сделал пользователь |
        | --- | --- |
        | af\_conversion | Пользователь совершил конверсию. Используйте тип конверсии conversion\_type, чтобы указать ее тип: install (установка), re-engagement (повторное вовлечение) или re-attribution (реатрибуция). |
        | af\_session | Открыл приложение |
        | когорта\_удалений | Удалили приложение |
        | Рекламодатель определил внутреннее событие приложения | Выполнил внутреннее событие в приложении |
      </td>
    </tr>
    <tr>
      <td>
        campaign (кампания)
      </td>
      <td>
        Иерархия кампаний

        Рассмотрим: Изменение названия кампании не поддерживается. Следовательно, с одним идентификатором кампании может быть связано несколько названий.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id (идентификатор кампании)
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        рекламный набор
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        adset\_id (идентификатор группы объявлений)
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        ad (объявление)
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        ad\_id (идентификатор объявления)
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        канал
      </td>
      <td>
        Иерархия кампаний.

        [Обновлено 27 октября 2021 г.] В настоящее время Meta ads не отображает канал в данных, предоставляемых через механизм Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        site\_id (идентификатор сайта)
      </td>
      <td>
        Иерархия кампаний
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        Используется для обозначения и удаления дубликатов данных ретаргетинга
      </td>
    </tr>
    <tr>
      <td>
        геолокация
      </td>
      <td>
        Код страны по ISO, полученный из IP-адреса пользователя.
      </td>
    </tr>
    <tr>
      <td>
        агентство
      </td>
      <td>
        * Поддержка прозрачности агентств.
        * В случае непрозрачных агентств может возникать несколько строк с одинаковым названием кампании, если рекламодатель и агентство одновременно запускают кампании с таким же названием. Не беспокойтесь. Строки не дублируются.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store (магазин приложений)
      </td>
      <td>
        Только приложения для Android: Магазин Android, из которого было загружено приложение. Заполняется рекламодателями, внедряющими <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">атрибуцию Android для нескольких магазинов</Anchor>. Если пусто, это означает Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords (ключевые слова)
      </td>
      <td>
        Слова, появляющиеся в поисковых запросах пользователя. Их сообщает рекламная сеть.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [Поле доступно с 27 апреля 2022 г.] Идентификатор ключевого слова, предоставляемый рекламной сетью.
      </td>
    </tr>
  </tbody>
</Table>

#### Метрики

| Имя поля | Описание | Формат |
| --- | --- | --- |
| unique\_users | Количество уникальных пользователей, выполнивших событие | Число |
| revenue\_usd | <ul><li>Сумма выручки в долларах США. Например, если выбранная валюта — EUR, то 1234,56 евро отражается как 1234.56</li><li>Максимум 2 знака после запятой.</li></ul> | Число |
| event\_count | Сколько раз произошло событие. | Число |
| selected\_currency | 3-буквенный код валюты (USD, EUR), установленный вами в настройках приложения. Формат <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Это та же валюта, которая используется для отображения выручки в Cohort в пользовательском интерфейсе. | строка |
| revenue\_selected\_currency | <ul><li>Сумма дохода в выбранной валюте. Например, если выбранная валюта — EUR, то 1234,56 евро отражается как 1234.56</li><li>Максимум 2 знака после запятой</li></ul> | Число |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Информация для разработчиков систем бизнес-аналитики">

**Объём данных в отчёте**

В отчетах содержатся данные об установках в рамках привлечения пользователей, повторных вовлечений и реатрибуции в рамках ретаргетинга, а также о связанных с ними событиях в приложении.

Вы можете загружать в свои BI-системы объединенные отчеты, отчеты о привлечении пользователей и отчеты о ретаргетинге по отдельности или вместе. Если вы загрузите их вместе и захотите самостоятельно отфильтровать представления:

* Для объединенного используйте поле is\_primary\_attribution=true или null.
* Для привлечения пользователей используйте conversion\_type=Install.
* Для ретаргетинга используйте conversion\_type=re-engagement или re-attribution.

Если вы просто используете объединенное представление в процессе загрузки данных, вы можете использовать логику разделения данных по типам кампаний, то есть атрибуции пользователей (установки) и ретаргетинг (повторные вовлечения). Для этого используйте conversion\_type=install, install\_unified, re-engagement или re-attribution. См. <Anchor target="_blank" href="/marketers/ru/docs/resolve-retargeting-double-attribution">Двойная атрибуция событий ретаргетинга.</Anchor>

**Соображения на уровне поля**

* Чтобы упростить расчет метрик удержания пользователей, используйте дни после атрибуции.
* Расчет уникальных пользователей с помощью таких показателей, как название кампании и идентификатор кампании: Если вы можете не принимать в расчет детализацию по названию кампании, вы можете суммировать количество уникальных записей по ID кампании, и метрики будут корректными.
* Вы можете агрегировать данные по полям иерархии кампаний.
* Доход в долларах США рассчитывается по валютному курсу на день события.
* События дохода от рекламы включены в случае наличия, но с задержкой по времени до 3 дней.

**Общие соображения**

Данные всех приложений предоставляются в одном файле. Используйте поле «Идентификатор приложения» для разделения данных по приложениям или настройте разделение по приложениям в Data Locker.

</Accordion>

<div id="use-cases" />

<Accordion title="Использование когорты">

Ниже приведены примеры некоторых популярных практических вариантов применения когортных данных, которые разработчики BI могут извлекать с помощью Data Locker. Каждый пример иллюстрируется оператором SQL и примером визуального представления в Excel.

#### **1. Расчёт удержания**

В следующем примере мы:

* Подсчитали показатели удержания в день 1 и день 7, а также общее количество установок по каждой кампании и объявлению.
* Суммируйте количество событий на каждое событие конверсии, отфильтровав `event_name`, чтобы получить `af_conversion`.
* В частности, проанализируйте кампании по привлечению пользователей в объединённом отчёте, отфильтровав данные следующим образом: `conversion_type IN (install, install_unified)`.

**SQL-запрос**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and app_id = YOUR_APP
group by 1,2
```

**Пример в Excel**

| Идентификатор кампании | идентификатор рекламы | Установки | День удержания 1 | День удержания 7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | На 15% |
| 07315466 | 613770 | 300 | 20% | 12 % |

#### **2. Расчёт ARPU для нескольких событий внутри приложения**

В следующем примере мы:

* Рассчитали ARPU для нескольких событий в приложении для одной кампании.
* Специально проанализируйте ретаргетинговые кампании, отфильтровав данные так, чтобы `conversion_type=re-engagement` и `conversion_type=re-attribution`.
* Суммируйте количество событий на каждое событие конверсии, отфильтровав `event_name`, чтобы получить `af_conversion`.
* Суммируйте выручку от нескольких событий, в данном случае `af_purchase` и `af_coins`.
* Установите `days_post_attribution` на минимально необходимое значение (в данном случае 7), чтобы минимизировать нагрузку на обработку данных.

**SQL-запрос**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Пример в Excel**

| Идентификатор кампании | Тип конверсии | Рост ARPU<br /><br />День 1 | Рост ARPU<br /><br />День 3 | Рост ARPU<br /><br />День 7 |
| --- | --- | --- | --- | --- |
| 12345678 | повторное вовлечение | 6.23 | 5.11 | 2.34 |
| 98765432 | повторное вовлечение | 3.57 | 1.34 | 4.86 |
| 07315466 | повторная атрибуция | 7.41 | 6.79 | 5.29 |

#### **3. Расчёт коэффициента конверсии событий внутри приложения для конкретного дня когорты**

В следующем примере мы:

* Рассчитали коэффициент конверсии событий в приложении в день 0 для нескольких показателей (в данном случае дата конверсии, гео, кампания, объявление и идентификатор сайта).
* Анализируйте объединенные данные (как UA, так и ретаргетинговые кампании), фильтруя их так, чтобы `is_primary_attribution=true`.
* Суммируйте количество событий на каждое событие конверсии, отфильтровав `event_name`, чтобы получить `af_conversion`.
* Установите `days_post_attribution` на минимально необходимое значение (в данном случае 7), чтобы минимизировать нагрузку на обработку данных.

**SQL-запрос**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Пример в Excel**

| Дата конверсии | Геоданные | Идентификатор кампании | идентификатор рекламы | Идентификатор сайта | День 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | США | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | Великобритания | 98765432 | Null | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | Null | Null | 63% |

#### **4. Расчёт ежедневных установок**

В следующем примере мы:

* Подсчитали количество установок по идентификатору приложения, дате конверсии, медиа-источнику, названию события и типу конверсии.
* Отфильтруйте данные в объединённом отчёте так, чтобы отобразить установки UA (не ретаргетинг), установив для `conversion_type` значение `install` или `install_unified`.
* Суммируйте установки, установив `event_name` на `af_conversion`.

**SQL-запрос**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // Если вы запрашиваете данные из унифицированных отчетов, измените строку ниже на: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Пример в Excel**

| Идентификатор приложения | Дата конверсии | Медиа-источник | Имя события | Всего |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

#### **5. Расчет выручки от рекламы на Facebook**

В следующем примере мы:

* Рассчитали доход за третий день от Facebook по дате конверсии и идентификатору приложения.
* Анализируйте данные Facebook, отфильтровав их так, чтобы `media_source='Facebook Ads'`.
* Установите `days_post_attribution` на минимально необходимое значение (в данном случае 3), чтобы минимизировать нагрузку на обработку данных.

**SQL-запрос**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
group by 1,2,3
group by 1,2,3
```

**Пример в Excel**

| Дата конверсии | Идентификатор приложения | Медиа-источник | Доход<br /><br />День 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

#### **6. Расчет ARPU по идентификатору ключевого слова ASA для когортных дней до 365**

В следующем примере мы:

* Рассчитали ARPU от Apple Search Ads на один идентификатор ключевого слова до 365-го дня когорты.
* Проанализируйте данные Apple Search Ads, отфильтровав их так, чтобы `media_source='Apple Search Ads'`.
* Суммируйте количество событий на каждое событие конверсии, отфильтровав `event_name`, чтобы получить `af_conversion`.

**SQL-запрос**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Пример в Excel**

| Медиа-источник | ID ключевого слова | Рост ARPU<br /><br />День 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

#### **7. Расчет ARPU за 7 дней по времени атрибуции для каждого региона**

Следующий пример демонстрирует, как использовать <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPI по времени атрибуции</Anchor>. В примере мы:

* Рассчитали ARPU (средний доход на пользователя) за 7 дней по дате атрибуции для каждого региона.
* Результаты отсортированы по количеству конверсий, отображаются 20 лучших регионов.
* Данные отфильтрованы таким образом, чтобы `conversion_type='install'`.
* В первом столбце указан регион. Второй столбец показывает общее количество конверсий. В последующих столбцах отображается доход за 7 дней для каждого дня, указанного в качестве строки в запросе.

**SQL-запрос**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // Если вы запрашиваете данные из унифицированных отчетов, измените строку ниже на: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Пример в Excel**

| Геоданные | Всего конверсий | ARPU: День 7 для 11.07.2023 | ARPU: День 7 для 12.07.2023 | ARPU: День 7 для 13.07.2023 | ARPU: День 7 для 14.07.2023 | ARPU: День 7 для 15.07.2023 | ARPU: День 7 для 16.07.2023 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Южная Корея | 120660 | 7798,89$ | 6997,37$ | 8258,95$ | 9050,21$ | 10018,04$ | 13765,73$ |
| Канада | 35099 | 64867,84$ | 7050,19$ | 5656,33$ | 9553,75$ | 8632,41$ | 11308,06$ |
| Чили | 26750 | 48160,02$ | 21249,55$ | 22584,57$ | 24033,07$ | 31118,91$ | 41145,22$ |

</Accordion>

## Дополнительные сведения

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика |  |
| --- | --- |
| Данные о затратах | <ul><li>Не доступно. <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports">Используйте Cost ETL</Anchor>.</li><li>См. также <Anchor target="_blank" href="/marketers/ru/docs/combine-cost-etl-and-cohort-reports-via-data-locker">объединение Cost ETL с когортными отчетами</Anchor>.</li></ul> |
| Изменения в названиях кампаний | Не поддерживается. |
| Обновление данных | Ежедневно (UTC). Отчеты появляются в Data Locker в папке даты и времени (dt) за отчетный день к 10:00 UTC следующего дня. |
| Доход от рекламы | <ul><li>Доступно</li><li>Для af\_ad\_revenue событий метрика «Уникальные пользователи» недоступна для дат с 5 октября 2022 г. по 16 февраля 2023 г.</li></ul> |
| Валюта | Для каждой строки доступны доллары США и валюта конкретного приложения |
| Часовой пояс | <ul><li>UTC</li><li>Часовой пояс для конкретного приложения доступен в <Anchor target="_blank" href="/marketers/ru/docs/advanced-aggregated-reports-in-data-locker">расширенном агрегированном когортном отчете с версиями часового пояса</Anchor>.</li></ul> |
| Органические данные | Доступно |
| Дни после конверсии (установка, реатрибуция, повторное вовлечение) | <ul><li>Доступны данные за 365 дней после установки.</li><li>1095 дней доступны в <Anchor target="_blank" href="/marketers/ru/docs/advanced-aggregated-reports-in-data-locker">расширенных агрегированных отчетах</Anchor>.</li></ul> |
| Прозрачность агентства | <ul><li>Поддерживается</li><li>Данные X Ads и Meta ads всегда прозрачны</li></ul> |
| Разделение приложений | Поддерживается |
| Данные SKAN | Не включены. То есть данные предоставляются в постбэках iOS. |
| Повторные установки | <ul><li>Если события после переустановки считаются неатрибутированными органическими:<ul><li>Они включены только с 26 мая 2024 года. <Anchor target="_blank" href="/marketers/ru/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Узнать больше</Anchor></li><li>Время установки определяется на основе поля <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Они не учитываются в подсчетах уникальных пользователей и показателях удержания.</li></ul></li><li>Если события после переустановки отнесены к первой установке, они всегда учитываются. <Anchor target="_blank" href="/marketers/ru/docs/unique-users">Узнать больше</Anchor></li></ul> |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Объедините Cost ETL и когортные отчеты</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">Ретаргетинг</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D0%B0%D1%8F-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0-%D0%B2-data-locker 01H7WG3CA1DDAN79D1PBPE0RJ3=%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D0%B0%D1%8F-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B0-%D0%B2-data-locker 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=%D0%B0%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D1%8B 01H7WG3CA14PQ2PJ58FX8TE6ZH=%D0%B0%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D1%8B metrics=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8 01H7WG3CA24VQKFVP99S82GCXZ=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D1%83%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D1%8F h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D1%83%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D1%8F 2-calculating-arpu-of-multiple-inapp-events=2-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-arpu-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-arpu-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D0%BA%D0%BE%D1%8D%D1%84%D1%84%D0%B8%D1%86%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BA%D1%80%D0%B5%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%BD%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D0%BA%D0%BE%D1%8D%D1%84%D1%84%D0%B8%D1%86%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BA%D1%80%D0%B5%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%BD%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B 4-calculating-daily-installs=4-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D0%B5%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D1%8B%D1%85-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-%D1%80%D0%B0%D1%81%D1%87%D1%91%D1%82-%D0%B5%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D1%8B%D1%85-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA 5-calculating-revenue-from-facebook-ads=5-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D0%B8-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BD%D0%B0-facebook h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D0%B8-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BD%D0%B0-facebook 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-arpu-%D0%BF%D0%BE-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%83-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B2%D0%BE%D0%B3%D0%BE-%D1%81%D0%BB%D0%BE%D0%B2%D0%B0-asa-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D1%85-%D0%B4%D0%BD%D0%B5%D0%B9-%D0%B4%D0%BE-365 h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-arpu-%D0%BF%D0%BE-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%83-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B2%D0%BE%D0%B3%D0%BE-%D1%81%D0%BB%D0%BE%D0%B2%D0%B0-asa-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D1%85-%D0%B4%D0%BD%D0%B5%D0%B9-%D0%B4%D0%BE-365 calculating-arpu-days-0-7-by-attribution-time-per-geo=7-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-arpu-%D0%B7%D0%B0-7-%D0%B4%D0%BD%D0%B5%D0%B9-%D0%BF%D0%BE-%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%B6%D0%B4%D0%BE%D0%B3%D0%BE-%D1%80%D0%B5%D0%B3%D0%B8%D0%BE%D0%BD%D0%B0 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-%D1%80%D0%B0%D1%81%D1%87%D0%B5%D1%82-arpu-%D0%B7%D0%B0-7-%D0%B4%D0%BD%D0%B5%D0%B9-%D0%BF%D0%BE-%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%B6%D0%B4%D0%BE%D0%B3%D0%BE-%D1%80%D0%B5%D0%B3%D0%B8%D0%BE%D0%BD%D0%B0 additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F 01H7WG3CA255TG9HW150RW1QTX=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
