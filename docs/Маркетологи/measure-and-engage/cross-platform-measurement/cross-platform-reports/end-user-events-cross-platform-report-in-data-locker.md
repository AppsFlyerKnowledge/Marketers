---
title: Отчет о кроссплатформенных событиях конечных пользователей в Data Locker
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-09-05T00:04:05Z'
  id: 39748676204817
  locale: ru
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/ru/articles/39748676204817
---
> **Краткий обзор:** Кроссплатформенный отчёт о событиях конечных пользователей позволяет измерять полный путь пользователя, конверсии и LTV на разных платформах и устройствах.

Кроссплатформенный отчёт о событиях конечных пользователей содержит сырые данные: журналы сеансов на уровне событий и событий внутри приложения для каждого пользователя, сопоставленные между платформами по вашему идентификатору пользователя клиента (CUID)  Каждое событие содержит результат кроссплатформенной атрибуции, что позволяет анализировать полный путь пользователя Каждое событие содержит результат кроссплатформенной атрибуции, что позволяет анализировать полный путь пользователя Каждое событие содержит результат кроссплатформенной атрибуции, что позволяет анализировать полный путь пользователя

Для получения дополнительной информации о процессе атрибуции на уровне пользователя и конфигурации смотрите <Anchor target="_blank" href="/marketers/ru/docs/beta-user-based-cross-platform-attribution">кроссплатформенная атрибуция на уровне пользователя</Anchor>.

<div id="report-fields" />

## Поля отчета

Чтобы узнать, какие поля содержатся в отчете, [скачайте образец отчета](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv).

Образец отчета включает все поля отчета и их значения. Чтобы узнать названия полей, смотрите <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">словарь полей</Anchor>.

<div id="report-data-freshness" />

## Актуальность данных отчета

* Отчёт выполняет пакетную обработку каждые 4 часа.
* Каждый запуск пакетной обработки обрабатывает события, поступившие в базу данных за предыдущий четырехчасовой интервал.
  * Пример: Запуск пакетной обработки в 08:00 обрабатывает события, поступившие в базу данных между 03:00 и 07:00.

* События распределяются по соответствующим часовым интервалам.
  * Пример: События, поступившие в базу данных между 03:00 и 04:00, будут отображены в часовом интервале 03:00.

<div id="important" />

> 🚧 **Важно!**
>
> Обычно существует небольшая задержка между фактическим событием и его внесением в базу данных. Отчёт опирается на время добавления записи в базу данных, чтобы обеспечить точную и стабильную почасовую группировку.

<div id="example-of-the-800-am-batch-run" />

### Пример выполнения пакетной обработки в 8:00 утра

| Дата | Версия отчета | Отчет доступен в | Отчет включает события, происходящие между | Отчет включает события, которые поступили в базу данных между |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Примечания к приведенному выше примеру:

* События последнего часа перед запуском не обрабатываются, чтобы было достаточно времени для их обогащения соответствующим CUID. В приведённом выше примере пакетная обработка в 08:00 обрабатывает события, поступившие в базу данных между 03:00 и 07:00. События, которые попали в базу данных между 7:00 и 8:00, не обрабатываются.
* Отчет доступен только через час после пакетного запуска, потому что внутренний процесс обновляет пакет в течение этого часа. В приведенном выше примере пакет в 8:00 AM доступен в 9:00 AM.

<div id="how-to-subscribe-to-the-report" />

## Как подписаться на отчёт?

1. В AppsFlyer в боковом меню выберите **Экспорт** > **Data Locker**.
2. В панели **Содержимое Data Locker** прокрутите вниз до раздела **Расширенные отчеты**.
3. Выберите **Кроссплатформенные события конечного пользователя.**

<div id="how-to-access-the-report-data-in-your-cloud-bucket" />

## Как получить доступ к данным отчета в вашем облачном хранилище?

Путь к отчёту состоит из следующей иерархии папок:

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

<div id="dl-report-folder-hierarchy" />

### Иерархия папок отчёта DL

<Image align="center" alt="" src="https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png" />

<div id="bi-developer-considerations" />

## Соображения для разработчика бизнес-аналитики

* Каждый часовой интервал отчёта содержит уникальные события конечных пользователей. Обязательно выгружайте все отчёты с периодичностью раз в час или раз в день.
* События дохода от рекламы еще не включены.
* Все данные приложения предоставляются в одном файле. Используйте поле «Идентификатор приложения», чтобы разделить данные по приложениям, или настройте Data Locker на разделение по каждому приложению. Рекомендуется использовать единый тип сегрегации.
* Предатрибуционные данные, такие как стоимость, клики и показы, следует извлекать из отчёта Стоимость ETL.

<div id="query-examples" />

### Примеры запросов

Ниже приведены примеры некоторых популярных практических применений данных, которые разработчики бизнес-аналитики могут извлекать с помощью Data Locker. Каждый пример иллюстрируется SQL-запросом

<div id="calculating-total-user-acquisitions" />

<Accordion title="Расчёт общего числа привлечений пользователей">

Подсчитайте количество новых уникальных пользователей по медиаисточнику и кампании.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	,
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'ВАШЕ_НАЗВАНИЕ_ЛИНЕЙКИ_ПРОДУКТОВ'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="Расчет общего количества активаций платформы">

Просуммируйте общее количество новых платформ, групп, источников трафика и кампаний, привлечённых каждым пользователем.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'ВАШЕ_НАЗВАНИЕ_ЛИНЕЙКИ_ПРОДУКТОВ'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="Расчет общего дохода">

Суммируйте общий доход по медиаисточнику и кампании.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'ВАШЕ_НАЗВАНИЕ_ЛИНЕЙКИ_ПРОДУКТОВ'
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 h_01K6Z40KG9H1AC81H77XXEGK1B=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 report-data-freshness=%D0%B0%D0%BA%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 h_01K6Z40KG9PTRAFGXB3XJH5TJ7=%D0%B0%D0%BA%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0 h_01K6Z40KG9QPSMXT13N50TE7KE=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE example-of-the-800-am-batch-run=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BD%D0%BE%D0%B9-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2-800-%D1%83%D1%82%D1%80%D0%B0 h_01K6Z40KG9JTHGJG7YJNH9TTDT=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BD%D0%BE%D0%B9-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2-800-%D1%83%D1%82%D1%80%D0%B0 how-to-subscribe-to-the-report=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%B4%D0%BF%D0%B8%D1%81%D0%B0%D1%82%D1%8C%D1%81%D1%8F-%D0%BD%D0%B0-%D0%BE%D1%82%D1%87%D1%91%D1%82 h_01K6Z40KG9J1XWV99Z9M7AG0BY=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%B4%D0%BF%D0%B8%D1%81%D0%B0%D1%82%D1%8C%D1%81%D1%8F-%D0%BD%D0%B0-%D0%BE%D1%82%D1%87%D1%91%D1%82 how-to-access-the-report-in-your-bucket=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B8%D1%82%D1%8C-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5%D0%BC-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%BC-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B5 h_01K6Z40KG9CDQ43ASM5T80AK65=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B8%D1%82%D1%8C-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5%D0%BC-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%BC-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B5 dl-report-folder-hierarchy=%D0%B8%D0%B5%D1%80%D0%B0%D1%80%D1%85%D0%B8%D1%8F-%D0%BF%D0%B0%D0%BF%D0%BE%D0%BA-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0-dl h_01K6Z40KG9NSVWTRSHR71Q7PM6=%D0%B8%D0%B5%D1%80%D0%B0%D1%80%D1%85%D0%B8%D1%8F-%D0%BF%D0%B0%D0%BF%D0%BE%D0%BA-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0-dl bi-developer-considerations=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B1%D0%B8%D0%B7%D0%BD%D0%B5%D1%81-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8 h_01K6Z7QHDT4Q2D4JFGC28W8MND=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B1%D0%B8%D0%B7%D0%BD%D0%B5%D1%81-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8 query-examples=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2 h_01K6Z40KG9E2F30Q9P5GFA9TWT=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2 h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />
