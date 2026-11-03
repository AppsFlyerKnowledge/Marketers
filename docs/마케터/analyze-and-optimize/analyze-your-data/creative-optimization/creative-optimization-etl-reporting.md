---
title: 광고 소재 최적화 - ETL 보고
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-10-14T10:33:03Z'
  id: 19253873174801
  locale: ko
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ko/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **요약: 요약:** 데이터 락커를 사용하여 광고 소재 최적화 보고를 클라우드 스토리지에 자동으로 지속적으로 스트리밍하여 BI 시스템에 프로그래밍 방식으로 효율적으로 로드할 수 있습니다./strong>

## 광고 소재 최적화 ETL 정보

광고 소재 최적화 추출 변환 로드(ETL)는 데이터 분석가가 광고 소재 성과 분석에 필요한 모든 정보를 얻을 수 있도록 합니다. 이를 위해 광고 소재 최적화 보고를 클라우드 스토리지로 자동 스트리밍하여 BI 시스템에 프로그래밍 방식으로 로드합니다.

모든 핵심성과지표(KPI), 상위 및 하위 퍼널 KPI, 기여 분석 데이터, 광고 소재 자산 데이터를 포함한 전체 자산 수준 성과 보고가 제공됩니다.

광고 소재 최적화 ETL은 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">데이터 락커</Anchor>를 활용하여 광고 소재 최적화 보고 데이터를 클라우드 스토리지로 보냅니다. Amazon Web Services(AWS)의 앱스플라이어 소유 버킷 또는 AWS, GCS, Yandex, BigQuery, Snowflake 등의 자체 스토리지와 같은 다양한 스토리지 대상 중에서 선택할 수 있습니다. 데이터 락커는 여러 목적지를 지원하므로, 모든 데이터를 하나 이상의 목적지로 전송하고, 특정 데이터를 특정 목적지로 전송하고, 필요에 따라 데이터 전달을 사용자 지정할 수 있습니다. Creative Optimization ETL은 **Creative Optimization Premium 구독 플랜에서 사용할 수 있습니다.**

## 시작하기

이 섹션에서는 크리에이티브 최적화 보고를 위해 데이터 락커를 설정하는 방법에 대해 설명합니다.

<div id="set-up-data-locker" />

<Accordion title="데이터 락커 설정">

**선행 조건**:

앱스플라이어 CSM을 통해 크리에이티브 최적화 프리미엄 플랜을 구독합니다. 구독하면 데이터 락커를 설정할 수 있습니다.

**데이터 락커 설정 방법:**

1. 다음 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">지침</Anchor>을 따릅니다.
2. 2. 데이터 락커를 설정할 때 데이터 락커 구성 페이지에서 **광고 소재** ( 보고서 선택 아래)를 선택합니다.

![데이터 락커 - 크리에이티브 최적화(Creative Optimization).jpg 선택](https://support.appsflyer.com/hc/article_attachments/51912733317905)

</Accordion>

<div id="edit-data-locker-configuration" />

<Accordion title="데이터 락커 구성 편집">

이 섹션에서는 기존 데이터 락커 구성을 편집하여 광고 소재 최적화  보고를 추가하는 방법을 설명합니다.

**데이터 락커에 광고 소재 최적화 보고를 추가하는 방법은 다음과 같습니다.**

1. 앱스플라이어의 사이드 메뉴에서 **내보내기 > 데이터 락커**를 선택합니다.
2. 데이터 락커 구성 페이지에서 **보고서 선택** 아래에서 **크리에이티브 최적화**를 선택합니다.

![데이터 락커 - 크리에이티브 최적화(Creative Optimization).jpg 선택](https://support.appsflyer.com/hc/article_attachments/51912733317905)

</Accordion>

## 추가 정보

<div id="data-freshness" />

<Accordion title="데이터 최신성">

광고 소재 최적화  보고서가 구성되면 매일 데이터 락커로 스트리밍되어 지난 30일 동안의 데이터를 제공합니다. 매일 UTC + 12에 스트리밍됩니다. 즉, 일별 시간은 지리적 위치에 따라 달라질 수 있습니다. 해당 시간을 결정하려면 **0 UTC + 12 + 현지 시간대** 계산을 사용하십시오.

**어떤 예시들:**  
뉴욕 0 UTC + 12 - 5 = 7:00  
베를린 0 UTC + 12 + 1 = 13:00  
샹하이 0 UTC + 12 + 8 = 20:00

</Accordion>

<div id="available-data" />

<Accordion title="활용 가능 데이터">

데이터 락커에서 사용할 수 있는 광고 소재 데이터는 다음과 같습니다.

| 필드 | 유형 |
| --- | --- |
| date | 문자열 |
| asset\_link | 문자열 |
| 광고 소재 | 문자열 |
| media\_source | 문자열 |
| campaign | 문자열 |
| campaign\_id | 문자열 |
| 광고 | 문자열 |
| ad\_id | 문자열 |
| 광고 세트 | 문자열 |
| adset\_id | 문자열 |
| app\_name | 문자열 |
| app\_id | 문자열 |
| creative\_first\_seen | 문자열 |
| creative\_age | 문자열 |
| creative\_type | 문자열 |
| 기간 | 문자열 |
| end\_card\_type | 문자열 |
| geo | 문자열 |
| 플랫폼 | 문자열 |
| 오리엔테이션 | 문자열 |
| 시간 단위 | 문자열 |
| 노출 | 문자열 |
| 클릭 | 문자열 |
| 설치 | 문자열 |
| CTR | 문자열 |
| CVR | 문자열 |
| IPM | 문자열 |
| 비용 | 문자열 |
| eCPI | 문자열 |
| 리어트리뷰션 | 문자열 |
| 리인게이지먼트 | 문자열 |
| CPM | 문자열 |
| roas\_d1 | 문자열 |
| roas\_d7 | 문자열 |
| roas\_d14 | 문자열 |
| roas\_d30 | 문자열 |
| roas\_d60 | 문자열 |
| roas\_d90 | 문자열 |
| retention\_d1 | 문자열 |
| retention\_d7 | 문자열 |
| retention\_d14 | 문자열 |
| retention\_d30 | 문자열 |
| retention\_d60 | 문자열 |
| retention\_d90 | 문자열 |
| revenue\_d1 | 문자열 |
| revenue\_d14 | 문자열 |
| revenue\_d30 | 문자열 |
| revenue\_d60 | 문자열 |
| revenue\_d7 | 문자열 |
| Revenue\_d90 | 문자열 |
| partner\_cpm | 문자열 |
| partner\_ctr | 문자열 |
| partner\_cvr | 문자열 |
| partner\_clicks | 문자열 |
| partner\_cost | 문자열 |
| partner\_ipm | 문자열 |
| partner\_impressions | 문자열 |
| partner\_installs | 문자열 |
| partner\_ecpi | 문자열 |

<Anchor target="_blank" href="/marketers/ko/docs/creative-optimization-guide#standard-metrics-and-dimensions">표준 지표</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/creative-optimization-guide#unique-metrics-and-dimensions">크리에이티브 최적화에 고유한 지표</Anchor> 모두에 대한 정의 목록을 참조하십시오.

> 📘 **참고**
>
> * 광고에 미리 보기가 없는 경우 **asset\_link** 및 **creative** 열이 채워지지 않습니다.
> * 다음 데이터는 사용할 수 없습니다.
>   * 커스텀 데이터 기준
>   * 사용자 지정 지표
>   * 인앱 이벤트
>   * AI 데이터(요소 및 장면)
>   * 리타게팅 데이터

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 설명 |
| --- | --- |
| 비용 데이터 | 광고 소재 최적화 ETL 리포트에 비용 데이터를 포함하려면 ROI360 구독이 필요합니다. |

</Accordion>

<div data-zendesk-anchors="about-creative-etl=%EA%B4%91%EA%B3%A0-%EC%86%8C%EC%9E%AC-%EC%B5%9C%EC%A0%81%ED%99%94-etl-%EC%A0%95%EB%B3%B4 h_01HCF5ZDDGTN52MZ9DX2MDKJV7=%EA%B4%91%EA%B3%A0-%EC%86%8C%EC%9E%AC-%EC%B5%9C%EC%A0%81%ED%99%94-etl-%EC%A0%95%EB%B3%B4 get-started=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 h_01HCF65RS2NKHEDHFE9TN78ES8=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 h_01HCFF8BWHGFX5KEZWKVDYXKKA=set-up-data-locker h_01HCFF8BWJCQHNN17N8G555FP9=edit-data-locker-configuration data=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCF8C8S392WJMYYHV6ECMNCW=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCFC87EDDD3X0ZXNCAQAHTZB=data-freshness h_01HCFBYBBMNZ52TH4M3G3YB3YM=available-data h_01HF44ZFSHJ8MX9ZNBF7SWB5JN=%EC%B0%B8%EA%B3%A0 01JH2M65K4MC96MZE4CVRPMS8B=traits-and-limitations" />
