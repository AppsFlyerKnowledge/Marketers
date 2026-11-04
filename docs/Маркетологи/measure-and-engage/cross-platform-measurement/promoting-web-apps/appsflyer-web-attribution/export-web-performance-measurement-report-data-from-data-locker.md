---
title: Экспорт данных отчетов Web Performance Measurement из Data Locker
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-08-26T00:22:27Z'
  id: 43510758321809
  locale: ru
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ru/articles/43510758321809
---
> **Кратко:** Экспортируйте данные Web Performance Measurement из Data Locker в двух типах отчетов, чтобы анализировать эффективность сайта на нужном уровне. Используйте End User Events для анализа всех посещений и событий, а Conversions — для подсчета и атрибуции уникальных конверсионных якорей (первых посещений, повторных посещений и событий привлечения пользователей).

> ❗️ **Warning**
>
> **Важно!** Чтобы использовать отчеты Web Performance Measurement в Data Locker, у вас должна быть подписка на Data Locker.

<div id="about-the-web-performance-measurement-reports" />

## Об отчетах Web Performance Measurement

Data Locker предоставляет два отчета для Web Performance Measurement: **End User Events** и **Conversions**, каждый из которых предназначен для разных задач анализа.

* Отчет **End User Events** — основной источник для анализа активности на сайте:
  * Включает **все веб-события и посещения**
  * Регистрирует каждое посещение как атрибутированную сессию `SESSION`
  * Идеально подходит для отчетности на **уровне посещений** и **уровне событий**
* Отчет **Conversions** лучше всего подходит для анализа на уровне конверсий. Конверсия — это якорь атрибуции, точка взаимодействия, которая определяет, когда и как распределять маркетинговую ценность. Сюда входят:
  * *первые посещения* (когда пользователь впервые заходит на ваш сайт),
  * *повторные посещения* (когда пользователь возвращается после взаимодействия с неорганической рекламой), и
  * *события привлечения пользователей* (пользовательские события, например регистрация или первый депозит), которые указывают на то, что пользователь был привлечен.
* Все пользовательские события позже связываются с этими конверсиями и наследуют данные об их кампаниях

В интерфейсе Data Locker Advanced Reports также указаны **Engagements** и **End User Events Cross-Platform** как отдельные варианты отчетов Web Performance Measurement. В этой статье рассматриваются **End User Events** и **Conversions** — два отчета, которые используются для большинства видов анализа Web Performance Measurement.

<div id="select-a-web-performance-measurement-report" />

## Выберите отчет Web Performance Measurement

Перед экспортом данных Web Performance Measurement выберите соответствующий отчет в Data Locker.

1. В AppsFlyer в боковом меню выберите **Экспорт > Data Locker**.
2. Кликните вкладку **Advanced Reports**.
3. Выберите **End User Events** или **Conversions** из списка отчетов Web Performance Measurement.
4. Нажмите **Сохранить конфигурацию**.

<div id="report-fields" />

## Поля отчета

Чтобы узнать, какие поля содержатся в отчетах, скачайте образец для каждого отчета:

* [Образец отчета End User Events](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [Образец отчета о событиях конверсии](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

Образец отчета включает все поля отчета и их значения. Определения полей см. в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">словаре полей</Anchor>.

<div id="report-timing-and-data-freshness" />

## Сроки формирования отчетов и актуальность данных

Используйте эти сведения, чтобы понять, когда добавляются новые данные и когда недавние события становятся доступны в отчете.

* **Частота формирования отчета**: новые данные добавляются каждый час.
* **Актуальность данных**: события обычно появляются в отчете в течение 2–3 часов после их возникновения.

<div id="heres-how-each-batch-works" />

### Вот как работает каждый пакетный запуск:

* Каждый пакет **обрабатывает** события в рамках 1,5-часового окна.
* В пределах этого окна **атрибутируется** только первый час событий.
* Оставшиеся 30 минут используются **только для обогащения** атрибутированных событий идентификаторами пользователей клиентов (CUIDs).
* События за последние 30 минут **пока не атрибутированы** — они будут включены в следующий пакет.

[![](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)

<div id="when-will-these-events-appear-in-the-report" />

### Когда эти события появятся в отчете?

События записываются в отчеты **после завершения обработки**. Например, события за период **08:00–09:00**, атрибутированные в пакете 10:00, появятся в **версии отчета 11:00**.

<div id="example-what-the-1000-am-batch-does" />

### Пример: что делает пакет 10:00 AM

| **дата;** | **Отчет доступен в** | **Атрибутированные веб-события (время события)** | **Веб-события, обработанные для обогащения более ранних событий CUIDs** |
| --- | --- | --- | --- |
| 01.28.2026 | 11:00 | 08:00 – 09:00 | 09:00 – 09:30 |
| 01.28.2026 | 12:00 | 09:00 – 10:00 | 10:00 – 10:30 |
| 01.28.2026 | 13:00 | 10:00 – 11:00 | 12:00 – 13:30 |

<div id="download-report-data-from-your-cloud-bucket" />

## Загрузите данные отчета из своего облачного бакета

Подробнее о том, как загрузить данные отчета из своего облачного бакета, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#folder-structure">структура папок Data Locker</Anchor>.

<div id="bi-developer-considerations" />

## Информация для разработчиков систем бизнес-аналитики

<Accordion title="Ключевые различия: веб и мобильные">

Веб-атрибуция отличается от мобильной атрибуции как идентификаторами, так и логикой данных. Чтобы повысить точность данных, применяйте в запросах следующие фильтры и практические рекомендации.

| Аспект | Мобильная платформа | Веб |
| --- | --- | --- |
| Фильтр по платформе | `платформа = 'IOS'` или `платформа = 'ANDROID'` | `платформа = 'WEBSITE'` |
| Идентификатор пользователя (значение) | `appsflyer_id` (на основе устройства) | `appsflyer_id_value` (на основе файлов cookie) |
| Тип идентификатора | Зависит от устройства | `appsflyer_id_type` всегда имеет значение `web_id` |
| Событие привлечения | установка | По умолчанию используется First Visit, но событие привлечения пользователей можно настроить |
| False означает, что налог включен в общую выручку. | `ПОВТОРНОЕ ВОВЛЕЧЕНИЕ` | `REVISIT` |
| Ретаргетинг | Поддерживается | Не поддерживается — для веба доступны только привлечение пользователей и повторные визиты |
| Время события | Идентификатор приложения (например, `id123456789`) | Домен с префиксом (например, `website-www.example.com`) |

</Accordion>

<Accordion title="Какую таблицу запрашивать?">

Отчет **End User Events** подходит для большинства видов анализа. Он включает все события и визиты на сайте. В этом отчете каждый веб-визит также записывается как атрибутированная `SESSION`, поэтому он служит основным источником для отчетности на уровне визитов и событий.

Таблица **Conversions** подходит в основном для подсчета первых визитов, повторных визитов и привлечений пользователей, когда нужны уникальные конверсии без дублирующихся записей событий.

| Пример использования | Таблица | Почему |
| --- | --- | --- |
| Подсчет визитов/сессий | `end_user_events` | Каждая строка — это сессия или событие |
| Подсчет уникальных конверсий | `конверсий` | Помогает избежать дубликатов |
| Анализ внутренних событий приложения | `end_user_events` с `end_user_event_type = 'IN_APP'` | Только у событий в приложении есть названия событий |

</Accordion>

<Accordion title="Реализуйте фильтры запросов">

Примените следующие фильтры, чтобы обеспечить точность запросов к сырым данным. Если не реализовать их, это приведет к дублированию записей и смешению метрик разных платформ.

* **Фильтр по платформе (обязательно):** Добавьте `WHERE platform = 'WEBSITE'`, чтобы отделить данные из веб-источников и исключить записи из мобильной среды, среды ПК или CTV.
* **Фильтр по атрибуционному credit (обязательно):** Одно и то же действие пользователя может отображаться дважды в `end_user_events`, потому что AppsFlyer может присвоить ему два разных атрибуционных credit в зависимости от представления отчетности.

  Это может произойти, если у пользователя есть:

  * исходный источник **User Acquisition (UA)**, а позже —
  * источник **повторного вовлечения**.

  В таком случае AppsFlyer может записать две записи для одного и того же события:

  * **Primary credit:** Атрибутирует событие к самому недавнему релевантному маркетинговому взаимодействию. Используется в Unified и представлении ретаргетинга.

    Чтобы избежать двойного подсчета, по умолчанию запрашивайте `end_user_events`, используя только запись primary credit:

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **Secondary credit:** Атрибутирует событие обратно к исходному источнику UA. Используется в представлении «Привлечение пользователей» для измерения пожизненной ценности (LTV).

    Поскольку одно и то же действие пользователя может храниться как две записи (одна с primary credit, другая с secondary credit), подсчет событий без фильтра может привести к двойному учету этого действия.

    Используйте эти запросы как шаблоны для анализа данных атрибуции веб-трафика в BigQuery или других инструментах бизнес-аналитики.

* **Фильтр по типу конверсии (необязательно):** Добавьте `WHERE conversion_type = 'USER_ACQUISITION'` или `WHERE conversion_type = 'RETARGETING'`, чтобы выделить данные атрибуции по типу кампании.

<div id="filter-summary-table" />

#### Таблица сводки по фильтрам

| Требование к фильтру | Логика SQL | Контекст реализации |
| --- | --- | --- |
| Спецификация платформы | `WHERE platform = 'WEBSITE'` | Изолирует данные, полученные из веб-источников, от других записей платформы. |
| Единое представление (избегайте дублирования) | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | Отдавайте приоритет атрибуции ретаргетинга перед исходной UA-кампанией. Используйте для общей отчетности, чтобы избежать двойного учета. |
| Только представление «Ретаргетинг» | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | Используйте только при анализе эффективности ретаргетинговых кампаний. |
| Только представление «Привлечение пользователей» | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | Используйте специально для представлений, ориентированных на привлечение, где события должны быть привязаны к первому визиту. |

</Accordion>

<Accordion title="Идентификация и подсчет конечных пользователей">

В сырых данных Web Performance Measurement один конечный пользователь может отображаться под двумя разными идентификаторами:

* `customer_user_id`: стабильный идентификатор, который вы задаете (обычно для авторизованных пользователей).
* `appsflyer_id_value`: идентификатор на основе cookie, срок действия которого со временем может истечь.

Чтобы правильно определять **уникальных пользователей** и рассчитывать **метрики на уровне пользователя**, всегда используйте:

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

Вот, как это работает:

* Если `customer_user_id` существует, AppsFlyer использует его (предпочтительный, стабильный вариант).
* Если его нет, AppsFlyer использует `appsflyer_id_value`.

Используйте `COALESCE(customer_user_id, appsflyer_id_value)`, когда нужно:

* Подсчитывать уникальных пользователей
* Группировать по пользователю
* Фильтровать по конкретным пользователям
* Объединять таблицы по пользователю
* Рассчитывать любые метрики на уровне пользователя

<div id="example-count-distinct-users" />

#### Пример: подсчёт уникальных пользователей

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<Accordion title="Органический vs. неорганический трафик">

Используйте поле `is_organic`:

| Тип трафика | Фильтр |
| --- | --- |
| Органика | `is_organic = true` |
| Неорганический | `is_organic = false` |

</Accordion>

<Accordion title="Обработка пустых значений">

| Тип данных | Пустое значение |
| --- | --- |
| строка | `''` (пустая строка) |
| Доход от рекламы | `NULL` |

</Accordion>

<Accordion title="Примеры запросов">

<Accordion title="1. Общее количество посещений по медиаисточникам (7 дней)">

Подсчитывает количество веб-сессий, атрибутированных каждому медиаисточнику.

```sql
SELECT media_source, COUNT(*) AS total_visits
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION'
GROUP BY media_source
ORDER BY total_visits DESC
```

</Accordion>

<Accordion title="2. Первые посещения и повторные посещения по кампаниям">

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name
ORDER BY conversion_count DESC
```

</Accordion>

<Accordion title="3. Подсчет уникальных названий событий (только события в приложении)">

```sql
SELECT
  event_name,
  COUNT(*) AS event_count
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP'
GROUP BY event_name
ORDER BY event_count DESC
```

</Accordion>

<Accordion title="4. Подсчет уникальных пользователей по медиаисточникам">

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY media_source
ORDER BY unique_users DESC
```

</Accordion>

<Accordion title="5. Коэффициент конверсии — от первого визита до покупки (межтабличное соединение)">

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate
FROM first_visits fv
LEFT JOIN purchases p ON fv.user_id = p.user_id
GROUP BY fv.media_source
ORDER BY conversion_rate DESC
```

</Accordion>

<Accordion title="6. Доход по кампаниям (последние 7 дней)">

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0
GROUP BY campaign_name, media_source
ORDER BY total_revenue_usd DESC
```

</Accordion>

<Accordion title="7. Органические и неорганические первые посещения по дням">

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'органический' ELSE 'неорганический' END AS traffic_type,
  COUNT(*) AS first_visits
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT'
GROUP BY visit_date, traffic_type
ORDER BY visit_date, traffic_type
```

</Accordion>

<Accordion title="8. Разбивка по привлечению пользователей и ретаргетингу">

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
GROUP BY conversion_type, conversion_name
ORDER BY conversions DESC
```

</Accordion>

<Accordion title="9. Распределение идентификаторов кликов (Google, Meta, TikTok и т. д.)">

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != ''
GROUP BY click_id_type
ORDER BY events_with_click_id DESC
```

</Accordion>

<Accordion title="10. Сгруппируйте пользователей в когорты по дате конверсии (эквивалентно дате установки в мобильном приложении)">

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY cohort_date, media_source
ORDER BY cohort_date, cohort_users DESC
```

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## Спецификации и ограничения

Следующие поля **не поддерживаются для веб-данных** и всегда будут пустыми:

| Специфика | Описание |
| --- | --- |
| `advertising_id_type`, `hardware_id_type` и т. д. | Оба типа |
| `agency`, `site_id`, `ad_type` | Оба типа |
| `platform_group` | конверсий |
| `app_version__conversion` | end\_user\_events |
| Все поля `__assist_*` | конверсий |

<div id="see-also" />

## Смотрите также

* <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">О расширенных отчётах Data Locker</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Data Locker для маркетологов</Anchor>

<div data-zendesk-anchors="about-the-data-locker-web-attribution-reports=%D0%BE%D0%B1-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-web-performance-measurement h_01KGM4FT90X1K2V8M8GJV6EW5K=%D0%BE%D0%B1-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-web-performance-measurement h_01_select-web-performance-measurement-report=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82-web-performance-measurement select-a-web-performance-measurement-report=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82-web-performance-measurement report-fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 h_01KGM4FT90WP73N1D75WWNT2TE=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 report-timing-and-data-freshness=%D1%81%D1%80%D0%BE%D0%BA%D0%B8-%D1%84%D0%BE%D1%80%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-%D0%B8-%D0%B0%D0%BA%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01KGM4FT90B6W7KBS9K1FSSETD=%D1%81%D1%80%D0%BE%D0%BA%D0%B8-%D1%84%D0%BE%D1%80%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-%D0%B8-%D0%B0%D0%BA%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 here%E2%80%99s-how-each-batch-works=%D0%B2%D0%BE%D1%82-%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%BA%D0%B0%D0%B6%D0%B4%D1%8B%D0%B9-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA h_01KGM4FT91MCGCBYSHE18JHQ96=%D0%B2%D0%BE%D1%82-%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%BA%D0%B0%D0%B6%D0%B4%D1%8B%D0%B9-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA when-will-these-events-appear-in-the-report=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D1%8D%D1%82%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D0%BE%D1%8F%D0%B2%D1%8F%D1%82%D1%81%D1%8F-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B5 h_01KGM4FT91XF7HCM8E8TQ56D0D=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D1%8D%D1%82%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D0%BE%D1%8F%D0%B2%D1%8F%D1%82%D1%81%D1%8F-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B5 example-what-the-1000-am-batch-does=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-1000-am h_01KGM4FT91D90DWYGSE3SES2ZY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-1000-am download-report-data-from-your-cloud-bucket=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%B8%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%B8%D0%B7-%D1%81%D0%B2%D0%BE%D0%B5%D0%B3%D0%BE-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B1%D0%B0%D0%BA%D0%B5%D1%82%D0%B0 h_01KGM4FT91NECKXMDW60A4B9X5=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%B8%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%B8%D0%B7-%D1%81%D0%B2%D0%BE%D0%B5%D0%B3%D0%BE-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B1%D0%B0%D0%BA%D0%B5%D1%82%D0%B0 bi-developer-considerations=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC-%D0%B1%D0%B8%D0%B7%D0%BD%D0%B5%D1%81-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8 h_01KGM4FT91C2KP050ZAYW6K8FD=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC-%D0%B1%D0%B8%D0%B7%D0%BD%D0%B5%D1%81-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8 filter-summary-table=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D1%81%D0%B2%D0%BE%D0%B4%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%B0%D0%BC h_01KGM4FT91MSN2SN7TKNJZ54V4=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D1%81%D0%B2%D0%BE%D0%B4%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%B0%D0%BC example-count-distinct-users=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D0%BE%D0%B4%D1%81%D1%87%D1%91%D1%82-%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01KGM4FT91VDR0FWTMAPW6GM83=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D0%BE%D0%B4%D1%81%D1%87%D1%91%D1%82-%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KGM4FT91QZR30KJAQ87AG691=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01_web-perf-see-also=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5 see-also=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
