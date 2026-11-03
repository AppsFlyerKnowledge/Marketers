---
title: Data Clean Room — Динамический запрос
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-09-20T10:05:34Z'
  edited_at: '2026-08-27T00:05:17Z'
  id: 18704719821329
  locale: ru
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ru/articles/18704719821329
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** Запускайте пользовательские DCR-запросы в режиме реального времени к данным атрибуции в системе AppsFlyer, к вашим пользовательским источникам или к их комбинации. Просмотрите результаты ваших запросов в режиме предпросмотра или загрузите полные результаты.

## Информация о компании

### Зачем использовать Dynamic Query?

Dynamic Query позволяет выполнять специальные пользовательские запросы к вашим данным DCR в режиме реального времени, чтобы быстро и эффективно получать ответы на конкретные маркетинговые вопросы.

* Используя возможности и гибкость SQL, он позволяет проводить углубленные исследования и выполнять сложные вычисления, которые невозможно выполнить иначе. С Dynamic Query вы можете применять свою бизнес-логику к данным, которые иначе были бы недоступны.
* Кроме того, Dynamic Query позволяет эффективно получать ответы на разовые или нерегулярные вопросы без необходимости настраивать отчеты. (Разумеется, <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-reports">традиционные отчеты DCR</Anchor> по-прежнему являются правильным решением для регулярного извлечения и загрузки данных.)

Dynamic Query доступен **всем клиентам DCR** и позволяет выполнять запросы и предварительно просматривать результаты без использования кредитов из вашего пакета DCR. Кредиты списываются только в том случае, если вы решите загрузить полные результаты. Так вы сможете убедиться, что правильно настроили запросы, и получите нужные ответы до того, как с вас спишут кредиты.

### Язык и диалект запросов

Dynamic Query использует SQL **(диалект Spark SQL)** и поддерживает:

* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/sql-ref-syntax-qry-select.html">Запросы SELECT</Anchor>
* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/api/sql/">Стандартные функции SQL</Anchor>
* Пользовательские функции (UDF) по запросу клиента
  * Если вам нужна нестандартная функция SQL, обратитесь к своему CSM или напишите на [hello@appsflyer.com](mailto:hello@appsflyer.com,), и мы сделаем все возможное, чтобы добавить ее.

### Доступные источники

Dynamic Query позволяет выполнять пользовательские запросы к следующим источникам данных:

* Ваши данные атрибуции в системе AppsFlyer
  * [Узнать больше](#querying-attribution-data) о таблицах данных атрибуции и о том, как выполнять запросы к ним
* <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources">Пользовательские источники</Anchor>, которые вы настроили в DCR

Вы можете запрашивать эти источники по отдельности или [объединять 2 и более](#combining-sources) с помощью операторов **JOIN** или **UNION**. Благодаря такой гибкости Dynamic Query полезен в различных сценариях, например:

* Запросы только к данным атрибуции, чтобы [получать инсайты по всем приложениям](#obtain-crossapp-insights), [анализировать целостность данных](#explore-data-integrity) или [рассчитывать пользовательские метрики атрибуции](#calculate-custom-attribution-metrics)
* Запрос данных из ваших пользовательских источников в сочетании с данными атрибуции, чтобы [обогатить ваши данные](#enrich-your-custom-data-with-attribution-insights) инсайтами атрибуции

В зависимости от типов источников, используемых в запросе, [применяются правила](#сохранение-конфиденциальности), обеспечивающие строгое соблюдение конфиденциальности пользователей.

> 📘 **Примечание**
>
> В настоящее время Dynamic Query не запрашивает данные атрибуции и не возвращает результаты из Meta (Facebook, Instagram и т. д.) Чтобы запрашивать эти данные, настройте <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-reports">отчеты DCR</Anchor>. Чтобы запрашивать эти данные, настройте <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-reports">отчеты DCR</Anchor>.

### Сохранение конфиденциальности

Чтобы обеспечить строгое соблюдение стандартов конфиденциальности DCR в Dynamic Query, ко всем запросам применяются следующие требования:

1. Любой запрос, использующий **данные атрибуции**, должен включать оператор **GROUP BY**, чтобы результаты были агрегированы.
2. Операторы **UNION** **нельзя** использовать для объединения пользовательских источников с данными атрибуции.
3. Группировка по следующим полям **не разрешена:**
   * **Поля данных атрибуции:**
     * appsflyer\_id
     * IDFA
     * IDFV
     * рекламный\_идентификатор
     * android\_id
     * идентификатор\_пользователя\_клиента
     * ip
   * **Поля пользовательских источников**, которые соединены с любым из указанных выше полей данных атрибуции.
4. Следующие функции **не разрешены** при запуске для **неагрегированных данных атрибуции.** Они **разрешены** при запуске для **агрегированных данных атрибуции** или **данных пользовательских источников:**
   * collect\_list
   * collect\_set
   * последняя
   * last\_value
   * первая
   * first\_value
   * max
   * min (Минимальный)

Чтобы узнать больше о том, что можно и чего нельзя *делать* при создании запросов, см. примеры и пояснения для [корректных](#выборочные-запросы) и [некорректных](#недопустимые-запросы) запросов.

### Доступ к Dynamic Query

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Data Clean Room**.
2. В верхнем меню выберите вкладку **Dynamic Query**.

## Reference(?)

### Справочник по запросам

Следующие вкладки содержат дополнительную информацию о создании запросов в среде Dynamic Query.

<div id="combining-sources" />

<Accordion title="Объединение источников: JOIN и UNION">

Операторы **JOIN** объединяют источники, сопоставляя общее поле:

* Можно использовать для объединения любых источников: таблиц данных атрибуции и/или пользовательских источников
* Можно использовать для объединения неограниченного числа источников
* **Обычно используется для обогащения данных пользовательских источников данными атрибуции**

Операторы **UNION** объединяют таблицы с совпадающей схемой (с одинаковыми столбцами и типами данных):

* **Можно** использовать для объединения таблиц данных атрибуции ***или*** пользовательских источников; **нельзя** использовать для объединения таблиц данных атрибуции ***с*** пользовательскими источниками
* Можно использовать для объединения неограниченного числа источников
* **Обычно используется для выполнения запросов к** [**нескольким таблицам данных атрибуции**](#querying-attribution-data)

</Accordion>

<div id="querying-attribution-data" />

<Accordion title="Запросы к таблицам данных атрибуции">

Данные атрибуции в системе AppsFlyer представлены в 8 разных таблицах:

* Каждая таблица содержит разные типы событий атрибуции.
* Период доступности данных для запросов зависит от таблицы.
  * При создании запроса в консоли Dynamic Query наведите указатель мыши на название таблицы на панели выбора, чтобы увидеть точные даты доступности данных для этой таблицы.
* Таблицы в каждой из перечисленных ниже групп имеют совпадающую схему, поэтому вы можете использовать операторы **UNION**, чтобы легко выполнять запросы к нескольким таблицам одновременно.

**Группа 1: установки приложения и события ретаргетинга**

| Название таблицы | Description(Описание) | Даты доступности данных |
| --- | --- | --- |
| installs | Пользователь загружает, устанавливает и запускает мобильное приложение | Предыдущие 180 дней  <br />(не включая текущий день) |
| re\_installs | Пользователь устанавливает приложение, затем удаляет и повторно устанавливает его в течение окна реатрибуции | Предыдущие 180 дней  <br />(не включая текущий день) |
| re\_engagements | Неактивный пользователь определенного приложения взаимодействует с кампанией ретаргетинга для этого приложения, а затем запускает его | Предыдущие 180 дней  <br />(не включая текущий день) |
| re\_attribution | Бывший пользователь определенного приложения (который удалил его) взаимодействует с кампанией ретаргетинга для этого приложения, а затем повторно устанавливает его | Предыдущие 180 дней  <br />(без учета текущего дня) |
| organic\_installs | Установка, не атрибутированная к конкретному медиаисточнику | Предыдущие 180 дней  <br />(без учета текущего дня) |

**Группа 2: События в приложении**

| Название таблицы | Description(Описание) | Даты доступности данных |
| --- | --- | --- |
| in\_app\_events | События после установки, настроенные для измерения в SDK приложения | Предыдущий день + текущий день |
| in\_app\_organic\_installs | События в приложении после органической установки | Предыдущий день + текущий день |

**Группа 3: Показы**

| Название таблицы | Description(Описание) | Даты доступности данных |
| --- | --- | --- |
| impressions (показы) | Рекламное объявление просматривается пользователем приложения или посетителем веб-сайта<ul><li>Данные доступны только для рекламных сетей, не относящихся к SRN</li></ul> | Предыдущие 5 дней + текущий день |

</Accordion>

### Выборочные запросы

Эти запросы демонстрируют лишь несколько возможностей Dynamic Query. Их можно использовать просто для поиска идей или как отправную точку для собственных запросов.

**Чтобы использовать примеры запросов как основу для своих запросов:**

1. Скопируйте и вставьте: скопируйте нужные примеры SQL и вставьте их в рабочий лист на вкладке **Динамический запрос**.
2. Замените параметры: измените код SQL, заменив параметры на конкретные источники и поля, которые вы хотите запросить.
3. Выполните: нажмите кнопку **Запустить**, чтобы запустить запрос и просмотреть результаты.  
   * Запуск запроса и предварительный просмотр результатов не расходуют кредиты.
   * Кредиты из вашего пакета DCR расходуются, только если вы загружаете полные результаты.

<div id="obtain-crossapp-insights" />

<Accordion title="Получайте инсайты по всем приложениям">

Этот запрос извлекает информацию о 3 приложениях с наибольшим количеством повторных установок из Snapchat за последние 3 дня.

```sql
SELECT app_id, COUNT(*) AS reinstall_count
FROM re_installs
WHERE media_source = 'snapchat_int' AND dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY app_id
ORDER BY reinstall_count DESC
LIMIT 3;
```

</Accordion>

<div id="explore-data-integrity" />

<Accordion title="Подробнее о целостности данных">

Чтобы помочь вам оценить целостность данных, этот запрос рассчитывает долю нулевых значений IDFA для 10 медиаисточников с наибольшим количеством установок за последние 7 дней.

```sql
SELECT media_source, COUNT(*) AS total_installs, ROUND((SUM(CASE WHEN idfa IS NULL THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2) AS null_idfa_rate
FROM installs
WHERE dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY media_source
ORDER BY total_installs DESC
LIMIT 10;
```

</Accordion>

<div id="calculate-custom-attribution-metrics" />

<Accordion title="Рассчитывайте кастомные метрики атрибуции">

Рассчитывая геометрическое среднее разницы во времени (в секундах) между временем установки и временем атрибутированного касания для каждого медиаисточника и кампании, результирующие данные дают представление об эффективности различных медиаисточников с точки зрения конверсий пользователей и сроков атрибуции.

```sql
SELECT media_source,campaign,geo_mean(GREATEST(1, unix_timestamp(install_time, "yyyy-MM-dd HH:mm:ss") - unix_timestamp(attributed_touch_time, "yyyy-MM-dd HH:mm:ss.SSS")))
FROM installs
GROUP BY 1,2
```

</Accordion>

<div id="enrich-your-custom-data-with-attribution-insights" />

<Accordion title="Обогащайте свои пользовательские данные инсайтами атрибуции">

Этот запрос использует данные атрибуции для группировки оценки из Custom Source C (c.score) по медиаисточнику, что позволяет использовать вашу пользовательскую метрику для оценки относительной эффективности различных медиаисточников.

```sql
SELECT media_source, sum(c.score)
FROM client_input c JOIN install i on i.appsflyer_id = c.appsflyer_id
GROUP BY media_source;
```

</Accordion>

<div id="complex-attribution-and-firstparty-data-join" />

<Accordion title="Сложная атрибуция и объединение собственных данных">

Этот запрос использует более сложный процесс объединения данных, что позволяет получать расширенные инсайты. Сначала он извлекает и объединяет данные из 2 отдельных таблиц атрибуции ("install" и "installRetarget"). Затем он объединяет эти данные с 2 пользовательскими источниками first-party, чтобы предоставить инсайты о различных типах конверсий, включая агрегированную пользовательскую метрику эффективности (score) и максимальный возраст для каждого типа.

```sql
SELECT conversion_type, SUM(sum_score), MAX(max_age)
FROM (SELECT media_source, conversion_type, SUM(score) as sum_score, MAX(age) as max_age
FROM (SELECT * from install union all select * FROM installRetarget) af
JOIN client_input c on c.appsflyer_id = af.appsflyer_id
JOIN client_age ca on ca.appsflyer_id = c.appsflyer_id
GROUP BY media_source, conversion_type)
GROUP BY conversion_type
```

</Accordion>

### Недопустимые запросы

Эти запросы иллюстрируют некоторые правила, которые Dynamic Query использует для обеспечения соблюдения правовых норм в части требований к конфиденциальности пользователей. Используйте их, чтобы лучше понять, что *можно* и *нельзя* делать при построении запросов для DCR.

<div id="no-group-by-statement" />

<Accordion title="Отсутствует оператор GROUP BY">

Каждый из следующих запросов недопустим, поскольку использует данные атрибуции, но не включает оператор **GROUP BY**:

```sql
SELECT *
FROM install;
```

-----------------------------------------------------

```sql
SELECT media_source, appId
FROM client_input c
JOIN install af on af.appsflyer_id = c.appsflyer_id;
```

</Accordion>

<div id="grouped-by-nonpermitted-attribution-data-field" />

<Accordion title="Группировка по недопустимому полю данных атрибуции">

Следующий запрос недопустим, поскольку он группирует по недопустимому полю данных атрибуции (appsflyer\_id):

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY appsflyer_id
```

-----------------------------------------------------

Следующий запрос недопустим, поскольку он группирует по недопустимому полю данных атрибуции (appsflyer\_id). Это недопустимо, даже если поле находится внутри функции:

```sql
SELECT substr(appsflyer_id, 0, 5), count(*)
FROM install
GROUP BY substr(appsflyer_id, 0, 5)
```

-----------------------------------------------------

Следующий запрос недопустим, поскольку он группирует по недопустимому полю данных атрибуции (appsflyer\_id). Это недопустимо, даже если поле находится внутри индекса:

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY 1
```

</Accordion>

<div id="grouped-by-nonpermitted-custom-data-field" />

<Accordion title="Группировка по полю пользовательского источника, связанному с недопустимым полем данных атрибуции">

Следующий запрос недопустим, поскольку он группирует по полю пользовательского источника (my\_id), которое связано с недопустимым полем данных атрибуции (appsflyer\_id); поэтому к my\_id применяется то же ограничение на группировку.

```sql
SELECT my_id, count(*)
FROM installs
JOIN my_source on my_source.my_id = installs.appsflyer_id
GROUP BY my_id
```

</Accordion>

<div id="restricted-function" />

<Accordion title="Ограниченная функция">

Следующий запрос **недопустим**, поскольку в нём предпринимается попытка запустить функцию collect\_list для **неагрегированных** данных атрибуции:

```sql
SELECT App_id, collect_list(appsflyer_id)
FROM install
GROUP BY app_id
```

-----------------------------------------------------

Сравните его со следующим **допустимым** запросом, который запускает функцию collect\_list для **агрегированных** данных атрибуции:

```sql
SELECT app_id, collect_list(campaign)
FROM (select app_id, campaign
  FROM Install
  GROUP BY 1, 2)
GROUP BY app_id
```

-----------------------------------------------------

Сравните его со следующим **допустимым** запросом, который запускает функцию collect\_list для **пользовательских данных источника:**

```sql
SELECT app_id, collect_list(c.score)
FROM client_input c
GROUP BY app_id
```

</Accordion>

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HAS0VY179VDWWV6N5YY2578E=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 why-use-dynamic-query=%D0%B7%D0%B0%D1%87%D0%B5%D0%BC-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-dynamic-query h_01HF9G8TXGTAJDFZFVT8WS3QJE=%D0%B7%D0%B0%D1%87%D0%B5%D0%BC-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-dynamic-query query-language-and-syntax=%D1%8F%D0%B7%D1%8B%D0%BA-%D0%B8-%D0%B4%D0%B8%D0%B0%D0%BB%D0%B5%D0%BA%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2 h_01HF3KZXC2VHNG92YX25K9HX7Q=%D1%8F%D0%B7%D1%8B%D0%BA-%D0%B8-%D0%B4%D0%B8%D0%B0%D0%BB%D0%B5%D0%BA%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2 h_01HASGQZ5ATBPQ0HF28ETAGPMJ=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8 h_01HF45KMZNF95SC0K6DE7P4K1R=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 preserving-privacy=%D1%81%D0%BE%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 01HF3EJEN2KSRR56F9XF0VSPQF=%D1%81%D0%BE%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 accessing-the-dynamic-query=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-dynamic-query h_01J3FBVTVW2NCNESK3SYR0G9Q8=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-dynamic-query h_01HAS0X3NDFM136YMYSAG88JD7=reference query-reference=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-%D0%BF%D0%BE-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0%D0%BC h_01HFKFTBD7BCVP8PT0FDNGVHXS=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-%D0%BF%D0%BE-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0%D0%BC h_01HFM169F3W9FDZZ3A4SG7WW58=combining-sources h_01HFM169F3WECT4M32H1CVCMKS=querying-attribution-data sample-queries=%D0%B2%D1%8B%D0%B1%D0%BE%D1%80%D0%BE%D1%87%D0%BD%D1%8B%D0%B5-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HF3TDC0A8N9ZXGJHY4MZE3Y6=%D0%B2%D1%8B%D0%B1%D0%BE%D1%80%D0%BE%D1%87%D0%BD%D1%8B%D0%B5-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HF40PRZV7DBMYQRS6YJK2RM4=obtain-crossapp-insights h_01HF40PRZVFHY7B0R1G5S5PRTG=explore-data-integrity h_01HF40PRZVB5N2B14VEYW2CB3N=calculate-custom-attribution-metrics h_01HF40PRZVDXPZBDT25B9JK2EE=enrich-your-custom-data-with-attribution-insights h_01HF40PRZVM2HGQMX9TCK8WF7Y=complex-attribution-and-firstparty-data-join invalid-queries=%D0%BD%D0%B5%D0%B4%D0%BE%D0%BF%D1%83%D1%81%D1%82%D0%B8%D0%BC%D1%8B%D0%B5-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HF3V03EFAVYR6M4WX0BHSVDK=%D0%BD%D0%B5%D0%B4%D0%BE%D0%BF%D1%83%D1%81%D1%82%D0%B8%D0%BC%D1%8B%D0%B5-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HF40PRZVZWTSK4BJ6BQ1D7S0=no-group-by-statement h_01HF40PRZVY13XM4RVETNK7E6K=grouped-by-nonpermitted-attribution-data-field h_01HF40PRZVJ9G4BAXKGW5VZMJX=grouped-by-nonpermitted-custom-data-field h_01HF42A4B20727TQGPPMP20629=restricted-function" />
