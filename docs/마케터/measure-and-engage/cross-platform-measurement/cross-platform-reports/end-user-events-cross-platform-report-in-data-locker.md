---
title: '[베타] 데이터 락커에서 크로스 플랫폼 엔드 유저 이벤트 리포트'
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
  edited_at: '2026-10-14T10:28:23Z'
  id: 39748676204817
  locale: ko
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/ko/articles/39748676204817
---
> **한눈에 보기:** 크로스 플랫폼 엔드 유저 이벤트 리포트는 플랫폼 및 디바이스 전반에 걸친 전체 유저 여정, 전환 및 LTV를 측정합니다.

크로스 플랫폼 엔드 유저 이벤트 리포트는 고객 사용자 ID(CUID)를 사용하여 각 유저에 대한 이벤트 레벨의 세션 및 인앱 이벤트 로그를 제공하는 로데이터 리포트입니다. 각 이벤트는 크로스 플랫폼 어트리뷰션 결과를 포함하여 완전한 사용자 여정을 분석할 수 있습니다.

사용자 기반 어트리뷰션 흐름 및 설정에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-attribution">사용자 기반 크로스 플랫폼 어트리뷰션</Anchor>을 참조하십시오.

## 리포트 필드

리포트에 포함된 필드를 확인하려면 [리포트 샘플을 다운로드하십시오](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv).

리포트 샘플은 모든 리포트 필드와 해당 값을 포함합니다. 필드의 정의는 필드 사전 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">을 참조하십시오</Anchor>.

## 리포트 데이터 최신성

* 리포트는 4시간마다 일괄 처리됩니다.
* 각 배치 실행은 이전 4시간 동안 데이터베이스에 입력한 이벤트를 처리합니다.
  * 예시: 8:00 AM 배치 실행은 3:00 AM에서 7:00 AM 사이에 데이터베이스에 입력된 이벤트를 처리합니다.

* 이벤트는 해당 시간 별 버킷에 할당됩니다.
  * 예시: 오전 3시에서 4시 사이에 데이터베이스에 입력한 이벤트는 오전 3시 버킷에 표시됩니다.

> 🚧 **중요!**
>
> 일반적으로 이벤트의 실제 발생과 데이터베이스에 입력 사이에 짧은 지연이 있습니다. 리포트는 데이터베이스 입력 시간을 사용하여 정확하고 일관된 시간 별 그룹화를 보장합니다.

### 8:00 AM 배치 실행 예시

| 날짜 | 리포트 버전. | 리포트 위치 | 리포트는 다음 사이에 발생한 이벤트를 포함합니다. | 리포트는 다음을 기준으로 데이터베이스에 입력한 이벤트를 포함합니다. |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | $150 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | $150 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | $150 |
| 2025-10-01 | 6:00 | 9:00 | $150 | $150 |

위 예시 참고:

* 실행 전 마지막 시간의 이벤트는 관련 CUID로 이벤트를 보강할 충분한 시간이 필요하도록 처리되지 않습니다. 위의 예시에서는 8:00 AM 배치 프로세스 이벤트가 3:00&#126;7:00 사이에 데이터베이스에 입력되었습니다. 7:00시에서 8:00시 사이에 데이터베이스에 입력한 이벤트는 처리되지 않습니다.
* 내부 프로세스가 해당 시간 동안 배치를 업데이트하기 때문에 이 리포트는 배치 실행 후 한 시간 후에만 사용할 수 있습니다. 위의 예시에서는 8:00 AM 배치가 9:00 AM에 제공됩니다.

## 보고서를 구독하려면 어떻게 해야 하나요?

1. 앱스플라이어의 사이드 메뉴에서 **내보내기 > 데이터 락커**를 선택합니다.
2. **데이터 락커 콘텐츠 창**에서 스크롤을 내려서 **고급 리포트** 섹션으로 이동합니다.
3. 최종 사용자 이벤트 크로스 플랫폼

## 클라우드 버킷의 리포트 데이터에 어떻게 액세스하나요?

리포트 경로는 다음과 같은 폴더 계층으로 구성됩니다.

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

### 리포트 폴더 계층 구조

[![](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)

## BI 개발사 고려사항

* 각 리포트 시간 별 버킷은 고유한 엔드유저 이벤트를 포함하고 있습니다. 모든 리포트를 매시간 또는 매일 가져오십시오.
* 광고 수익 이벤트는 아직 포함되지 않았습니다.
* 모든 앱 데이터는 단일 파일로 제공됩니다. 앱 ID 필드를 사용하여 앱별로 데이터를 분리하거나 데이터 락커를 앱별로 분리하도록 설정합니다. 통합 분류 유형을 사용하는 것이 좋습니다.
* 비용, 클릭 및 노출과 같은 사전 어트리뷰션 데이터는 비용 ETL 리포트에서 추출해야 합니다.

### 쿼리 예시

다음은 BI 개발자가 데이터 락커를 통해 추출할 수 있는 코호트 데이터의 인기 있고 실용적인 애플리케이션의 예입니다. 각 예시는 SQL 문구로 설명됩니다.

<div id="calculating-total-user-acquisitions" />

<Accordion title="총 사용자 획득 계산하기">

미디어소스 및 캠페인별 고유 신규 유저 수를 계산합니다.

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
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="총 플랫폼 활성화 계산">

사용자 별로 가져온 총 새 플랫폼, 그룹, 미디어 소스 및 캠페인 수를 합산합니다.

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
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="총 수익 계산">

미디어 소스 및 캠페인당 총 수익을 합산합니다.

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
WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C h_01K6Z40KG9H1AC81H77XXEGK1B=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C report-data-freshness=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B5%9C%EC%8B%A0%EC%84%B1 h_01K6Z40KG9PTRAFGXB3XJH5TJ7=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B5%9C%EC%8B%A0%EC%84%B1 h_01K6Z40KG9QPSMXT13N50TE7KE=%EC%A4%91%EC%9A%94 example-of-the-800-am-batch-run=800-am-%EB%B0%B0%EC%B9%98-%EC%8B%A4%ED%96%89-%EC%98%88%EC%8B%9C h_01K6Z40KG9JTHGJG7YJNH9TTDT=800-am-%EB%B0%B0%EC%B9%98-%EC%8B%A4%ED%96%89-%EC%98%88%EC%8B%9C how-to-subscribe-to-the-report=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 h_01K6Z40KG9J1XWV99Z9M7AG0BY=%EB%B3%B4%EA%B3%A0%EC%84%9C%EB%A5%BC-%EA%B5%AC%EB%8F%85%ED%95%98%EB%A0%A4%EB%A9%B4-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 how-to-access-the-report-in-your-bucket=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%82%98%EC%9A%94 h_01K6Z40KG9CDQ43ASM5T80AK65=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%B2%84%ED%82%B7%EC%9D%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%82%98%EC%9A%94 dl-report-folder-hierarchy=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01K6Z40KG9NSVWTRSHR71Q7PM6=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 bi-developer-considerations=bi-%EA%B0%9C%EB%B0%9C%EC%82%AC-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD h_01K6Z7QHDT4Q2D4JFGC28W8MND=bi-%EA%B0%9C%EB%B0%9C%EC%82%AC-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD query-examples=%EC%BF%BC%EB%A6%AC-%EC%98%88%EC%8B%9C h_01K6Z40KG9E2F30Q9P5GFA9TWT=%EC%BF%BC%EB%A6%AC-%EC%98%88%EC%8B%9C h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />
