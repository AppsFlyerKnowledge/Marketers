---
title: 데이터 협업 플랫폼(DCP, data collaboration platform) - 협업 측정 - 개요
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-01-27T08:21:27Z'
  edited_at: '2026-10-14T10:26:39Z'
  id: 32143318560017
  locale: ko
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ko/articles/32143318560017
---
> **한눈에 보기:**  협업 측정을 시작하려면 기본 개념과 설정 절차를 배우십시오.

## 온사이트 및 오프사이트 캠페인 측정

DCP는 현장 캠페인을 비현장 캠페인과 다르게 측정합니다. 협력자의 플랫폼 중 하나에서 현장 캠페인이 진행되는 동안, 오프사이트 캠페인은 Facebook, Google Ads 및 기타 SRN과 같은 제3자 플랫폼에서 진행됩니다. DCP는 이러한 플랫폼에서 참여 데이터를 직접 액세스할 수 없기 때문에, 귀속 흐름과 참여 데이터는 현장 캠페인과 다르며 고유한 솔루션이 필요합니다. 특별히 언급되지 않는 한, 측정 기사에 있는 정보는 두 캠페인 유형 모두에 적용됩니다.

## 측정의 세 가지 데이터 소스

DCP 측정 모델은 협업 맥락에서 발생하는 참여 이벤트에 변환 이벤트를 귀속시킵니다. 이 프로세스는 세 가지 주요 데이터 소스인 전환, 참여 및 캠페인 매핑의 데이터를 필요로 합니다. 각 소스는 어트리뷰션 흐름에서 중요한 역할을 합니다.

<div id="conversions" />

<Accordion title="전환">

전환 데이터에는 구매와 관련된 사용자 행동 및 해당 재고 유지 단위(SKU) 또는 소비재(CPG)에 대한 세부 정보가 포함되어 있습니다. 각 변환 인스턴스는 SKU, 사용자 ID 및 이벤트 시간과 같은 세부 정보를 캡처하는 단일 변환 이벤트를 나타냅니다.

**전환 파라미터 예시**

| **필드** | **값** |
| --- | --- |
| `app_id` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `event_name` | purchase |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |

AppsFlyer는 AppsFlyer SDK를 사용하여 귀하의 앱과 통합하거나 협력자가 제공하는 맞춤형 데이터 소스를 통해 앱 전환에 대한 액세스를 제공합니다. 웹 및 매장 내 전환 이벤트는 사용자 정의 데이터 소스를 사용하여 제공될 수 있습니다.

</Accordion>

<div id="engagements" />

<Accordion title="인게이지먼트">

참여 출처에는 클릭이나 노출과 같은 광고와의 사용자 상호작용에 대한 세부 정보가 포함되어 있습니다. 각 인스턴스는 참여 이벤트를 나타내며 캠페인 ID, 미디어 소스 및 터치 유형(예: 클릭 또는 노출)과 같은 속성을 포함합니다.

**인게이지먼트 파라미터 예시**

| **필드** | **값** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `media_source` | google |
| `campaign` | grc\_web\_ftu\_seq |
| `attributed_touch_time` | 2024-09-28T17:05:34 |
| `attributed_touch_type` | impression |
| `event_name` | start\_game |

참여 데이터를 액세스하려면, 현장 캠페인에서 AppsFlyer SDK를 사용하여 매개변수에 속성 데이터가 포함된 새로운 인앱 이벤트를 설정하거나 사용자 정의 소스를 통해 데이터를 공유할 수 있습니다.

오프사이트 캠페인에서는 참여 데이터가 제3자로부터 수신되며, 인앱 이벤트나 사용자 정의 소스를 통해 수신되지 않습니다.

</Accordion>

<div id="campaign-mapping" />

<Accordion title="캠페인 매핑">

캠페인 매핑 소스는 각 전환을 유도한 참여를 결정할 수 있게 해줍니다. 캠페인 매핑 기록은 SKU 또는 CPG를 캠페인 ID와 쌍으로 연결하여 전환 이벤트를 참여 이벤트에 연결합니다. 이 매핑을 사용하여 DCP는 주어진 SKU를 포함하는 전환 이벤트를 해당 캠페인 ID를 포함하는 참여 이벤트에 연결합니다.

캠페인 매핑 매개변수 예시

| **필드** | **값** |
| --- | --- |
| `collaborator_name` | fashion\_site |
| `collaborator_id` | 10079 |
| `campaign_id` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |

위의 매핑 정보는 커스텀 데이터 소스로 앱스플라이어에 제공됩니다.

</Accordion>

## **DCP 측정 프로세스**

DCP 귀속 흐름은 전환 SKU를 광고하는 참여 이벤트와 일치시켜 전환 이벤트를 참여 이벤트에 할당합니다. 이 프로세스는 협업, 참여 및 캠페인 매핑 데이터 소스에 접근할 수 있습니다.

이 프로세스의 단계는 아래에 간략하게 설명되어 있습니다.

1. DCP는 캠페인에 의해 촉발된 전환을 식별하기 위해 캠페인 매핑 데이터 소스를 전환 데이터 소스의 SKU와 매핑합니다. 일치하지 않는 전환은 오가닉으로 표시됩니다.
2. DCP는 캠페인에 매핑된 각 전환 이벤트를 동일한 사용자 ID 및 캠페인 ID를 가진 참여 이벤트에 연결하여 캠페인 및 전환 세부정보를 포함하는 귀속 전환 기록을 생성합니다.
3. DCP는 여러 SKU가 있는 속성 변환 기록을 개별 기록으로 분할하여 각 기록이 단일 SKU를 나타내도록 합니다.
4. DCP는 캠페인의 전환 대상이 아닌 SKU에 대한 기록을 필터링합니다.
5. 어트리뷰션 과정에서는 다음과 같은 로직을 적용합니다.
   * 여러 참여 이벤트가 전환에 연결될 때, DCP는 AppsFlyer 우선 순위 기준에 따라 마지막 터치 귀속을 적용합니다. 자세한 내용은 귀속 방법 우선순위(귀속 폭포)를 참조하십시오.
   * 단일 참여 이벤트가 여러 전환 이벤트에 책임이 있을 때, 첫 번째 전환만이 참여에 귀속되고 나머지는 귀속되지 않습니다.
6. DCP는 총 전환을 포함하여 통찰력을 생성하기 위해 귀속된 전환을 집계합니다.

### 측정 설정 프로세스 4단계

측정 설정 프로세스는 각각 전용 기사가 있는 네 단계로 설명할 수 있습니다:

1. 귀하의 조직에 적합한 협업 사용 사례를 고려하십시오.

4. 대시보드 및 리포트에서 어트리뷰션된 측정 데이터를 사용합니다.

<div data-zendesk-anchors="onsite-and-offsite-campaign-measurement=%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B8%A1%EC%A0%95 h_01JJKDD2YB8PPQ5EG7SSEQNV58=%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B8%A1%EC%A0%95 the-three-data-sources-of-measurement=%EC%B8%A1%EC%A0%95%EC%9D%98-%EC%84%B8-%EA%B0%80%EC%A7%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 h_01JJKDD2YBAGN14GY06HNBES4X=%EC%B8%A1%EC%A0%95%EC%9D%98-%EC%84%B8-%EA%B0%80%EC%A7%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 h_01JJKDD2YB757FKYAAMDSKREWT=conversions h_01JJKDD2YBGP02RRRFX2Q0XAK7=engagements h_01JJKDD2YBXHY4XA5TPN4T9CH4=campaign-mapping the-dcp-measurement-process=dcp-%EC%B8%A1%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4 h_01JJKDD2YBGEGZBF7K6F0TXJW7=dcp-%EC%B8%A1%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4 set-up-measurement-in-four-steps=%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-4%EB%8B%A8%EA%B3%84 h_01JJKDD2YBZ0F489P50SGE6TQF=%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-4%EB%8B%A8%EA%B3%84" />
