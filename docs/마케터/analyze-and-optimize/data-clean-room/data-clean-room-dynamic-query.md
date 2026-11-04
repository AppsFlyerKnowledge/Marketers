---
title: Data Clean Room - 동적 쿼리
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
  edited_at: '2026-10-14T10:39:08Z'
  id: 18704719821329
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/18704719821329
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **요약:**

<div id="overview" />

## 개요





3. * * <span id="preserving-privacy"></span>appsflyer\_id
     * idfa
     * idfv
     * advertising\_id
     * android\_id
     * 고객\_유저\_ID
     * ip
4. * collect\_list
   * collect\_set
   * last\_value
   * first\_value
   * 최대
   * 최소


<div id="restricted-function" />

<div id="grouped-by-nonpermitted-custom-data-field" />

<div id="grouped-by-nonpermitted-attribution-data-field" />

<div id="no-group-by-statement" />

<div id="invalid-queries" />

<div id="complex-attribution-and-firstparty-data-join" />

<div id="enrich-your-custom-data-with-attribution-insights" />

<div id="calculate-custom-attribution-metrics" />

<div id="explore-data-integrity" />

<div id="obtain-crossapp-insights" />

<div id="sample-queries" />

<div id="reference" />

<div id="accessing-dynamic-query" />

<div id="note" />

<div id="available-sources" />

<div id="query-language-and-dialect" />

<div id="why-use-dynamic-query" />

## 참고


**<span id="querying-attribution-data"></span><span id="combining-sources"></span><span id="query-reference"></span>Group 42053**

|  | 설명 |  |
| --- | --- | --- |
| 설치 |  |  |
| re\_installs |  |  |
| re\_engagements |  |  |
| re\_attribution |  |  |
| organic\_installs |  |  |

**Group 42053 인앱 이벤트:**

|  | 설명 |  |
| --- | --- | --- |
| in\_app\_events |  |  |
| in\_app\_organic\_installs |  |  |

**Group 42053 노출**

|  | 설명 |  |
| --- | --- | --- |
| 노출 |  |  |



```sql
SELECT app_id, COUNT(*) AS reinstall_count
FROM re_installs
WHERE media_source = 'snapchat_int' AND dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY app_id
ORDER BY reinstall_count DESC
LIMIT 3;
```


```sql
SELECT media_source, COUNT(*) AS total_installs, ROUND((SUM(CASE WHEN idfa IS NULL THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2) AS null_idfa_rate
FROM installs
WHERE dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY media_source
ORDER BY total_installs DESC
LIMIT 10;
```


```sql
SELECT media_source,campaign,geo_mean(GREATEST(1, unix_timestamp(install_time, "yyyy-MM-dd HH:mm:ss") - unix_timestamp(attributed_touch_time, "yyyy-MM-dd HH:mm:ss.SSS")))
FROM installs
GROUP BY 1,2
```


```sql
SELECT media_source, sum(c.score)
FROM client_input c JOIN install i on i.appsflyer_id = c.appsflyer_id
GROUP BY media_source;
```


```sql
SELECT conversion_type, SUM(sum_score), MAX(max_age)
FROM (SELECT media_source, conversion_type, SUM(score) as sum_score, MAX(age) as max_age
FROM (SELECT * from install union all select * FROM installRetarget) af
JOIN client_input c on c.appsflyer_id = af.appsflyer_id
JOIN client_age ca on ca.appsflyer_id = c.appsflyer_id
GROUP BY media_source, conversion_type)
GROUP BY conversion_type
```



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


```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY appsflyer_id
```

-----------------------------------------------------

```sql
SELECT substr(appsflyer_id, 0, 5), count(*)
FROM install
GROUP BY substr(appsflyer_id, 0, 5)
```

-----------------------------------------------------

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY 1
```


```sql
SELECT my_id, count(*)
FROM installs
JOIN my_source on my_source.my_id = installs.appsflyer_id
GROUP BY my_id
```


```sql
SELECT App_id, collect_list(appsflyer_id)
FROM install
GROUP BY app_id
```

-----------------------------------------------------

```sql
SELECT app_id, collect_list(campaign)
FROM (select app_id, campaign
  FROM Install
  GROUP BY 1, 2)
GROUP BY app_id
```

-----------------------------------------------------

```sql
SELECT app_id, collect_list(c.score)
FROM client_input c
GROUP BY app_id
```

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HAS0VY179VDWWV6N5YY2578E=%EA%B0%9C%EC%9A%94 why-use-dynamic-query=%EC%B0%B8%EA%B3%A0 query-language-and-syntax=%EC%B0%B8%EA%B3%A0 h_01HF9G8TXGTAJDFZFVT8WS3QJE=%EC%B0%B8%EA%B3%A0 h_01HF3KZXC2VHNG92YX25K9HX7Q=%EC%B0%B8%EA%B3%A0 h_01HASGQZ5ATBPQ0HF28ETAGPMJ=%EC%B0%B8%EA%B3%A0 h_01HF45KMZNF95SC0K6DE7P4K1R=%EC%B0%B8%EA%B3%A0 01HF3EJEN2KSRR56F9XF0VSPQF=preserving-privacy accessing-the-dynamic-query=%EC%B0%B8%EA%B3%A0 reference=%EC%B0%B8%EA%B3%A0 h_01J3FBVTVW2NCNESK3SYR0G9Q8=%EC%B0%B8%EA%B3%A0 h_01HAS0X3NDFM136YMYSAG88JD7=%EC%B0%B8%EA%B3%A0 h_01HFKFTBD7BCVP8PT0FDNGVHXS=query-reference sample-queries=%EC%B0%B8%EA%B3%A0 h_01HF3TDC0A8N9ZXGJHY4MZE3Y6=%EC%B0%B8%EA%B3%A0 invalid-queries=%EC%B0%B8%EA%B3%A0 h_01HF3V03EFAVYR6M4WX0BHSVDK=%EC%B0%B8%EA%B3%A0" />
