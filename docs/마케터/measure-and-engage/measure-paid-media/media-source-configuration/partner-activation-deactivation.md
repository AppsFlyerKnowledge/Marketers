---
title: 파트너 활성화/비활성화
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2026-10-14T10:30:41Z'
  id: 360000844778
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/360000844778
---
> **한눈에 보기:** 파트너 연동을 활성화 또는 비활성화하여 파트너가 귀사의 데이터를 가져가고 작업을 수행하는 것을 허가 또는 거부할 수 있습니다.

<div id="important" />

<div id="activation-overview" />

## 활성화 개요

파트너 연동은 활성화되거나 비활성화될 수 있습니다. 연동은 메인 연동 페이지에서 **파트너 활성화** 토글을 켜서 먼저 활성화됩니다. 다양한 연동 유형이 있습니다. 다른 [연동 유형](#id) (아래 표 참조)이 켜져 있는 경우에도 연동이 활성화된 것으로 간주될 수 있으며, 이 경우 **파트너 활성화** 토글은 꺼져 있을 수 있습니다.

**현재 선택된 앱의 파트너 연동 페이지로 이동하려면:**

* 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하고 파트너를 선택합니다.

아래 섹션에서는 다양한 연동 유형, 액티비티 수준이 표기되는 방식, 그리고 파트너 활성화 설정이 연동에 미치는 영향에 대해 설명합니다.

<div id="id" />

<Accordion title="연동 유형">

기본 연동 (**파트너 활성화**)는 첫 번째 연동 탭에서 활성화됩니다. 추가 연동 유형(아래 표 참조)은 후속 탭에서 활성화됩니다. **각 연동은 개별적으로 실행됩니다**. 연동이 활성화된 것으로 간주되려면, 적어도 하나의 연동 유형이 켜져 있어야 하며, 파트너 활성화 토글의 상태와 관계없이.

| 연동 유형 | 설명 |
| --- | --- |
| **주요 연동 (**<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#a-activate-partner">**파트너 활성화**</Anchor>) | 전환이 측정되며 파트너에게 포스트백을 보낼 수 있습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">**비용**</Anchor> (해당되는 경우) | 귀사의 캠페인, 광고 세트, 광고 및 지역/국가에 대한 비용, 클릭 및 노출 데이터를 얻을 수 있습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution">**광고 수익**</Anchor> (해당되는 경우) | 귀사의 광고로부터 수익 데이터를 얻을 수 있습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-integrated-partners-list">**SKAN**</Anchor> (해당되는 경우) | 파트너로부터 SKAN 포스트백을 받을 수 있습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">**권한**</Anchor> | 광고 네트워크 및 에이전시에게 귀사의 데이터에 대한 액세스와 연동 내 작업을 수행할 수 있는 권한을 부여할 수 있습니다. |

</Accordion>

<div id="integration-activity-indication" />

<Accordion title="액티비티 수준">

파트너 연동의 액티비티 수준은 지난 30일 동안 활성 전환이 있었던 일수를 기준으로 합니다. 각 파트너 연동은 두 가지 수준의 액티비티를 가질 수 있으며, 이는 파트너 마켓플레이스 내 파트너 로고 옆에 있는 녹색 또는 주황색 점으로 표시됩니다.

<Image align="center" alt="활성-통합-페이지-오렌지2.png" src="https://files.readme.io/a347f652b2829372ad1e0fefdf4c7158afa735deca6d32b557f6617a47472e27-51912587900305.png" />

다음 표는 특정 앱이 선택되었는지 또는 모든 앱이 선택되었는지에 따라 30&#126;90일 사이의 액티비티 수준 표시(녹색 또는 주황색)에 대한 기준을 설명합니다.

| 액티비티 수준 표시 | 특정 앱 선택됨 | 모든 앱 선택됨 |
| --- | --- | --- |
| <span id="green-dot"></span>녹색 점 | 선택한 앱에 파트너의 전환이 기록되었습니다. | 최소 하나의 앱에서 파트너와 전환이 이루어졌습니다. |
| <span id="orange-dot"></span>주황색 점 | 선택한 앱에서 파트너의 전환이 기록되지 않았습니다. | 모든 앱에서 파트너와의 전환이 없었습니다. |

> 📘 **참고**
>
> 90일 이상 액티비티 없는 연동은 [자동으로 비활성화](#automatic-deactivation)됩니다.

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="파트너 활성화 설정의 영향">

다음 표는 다양한 시나리오에서 파트너 활성화 설정이 어트리뷰션 및 포스트백에 미치는 영향을 보여줍니다.

<table><thead><tr><th>시나리오</th><th>파트너 활성화:<br/>켜짐</th><th>파트너 활성화: 꺼짐</th></tr></thead><tbody><tr><td>새로운 인스톨, <span>리어트리뷰션 및 리인게이지먼트에 대한 어트리뷰션 및 포스트백</span> </td><td><p><strong>어트리뷰션:</strong> 예</p><p><strong>포스트백:</strong> 예</p></td><td><p><strong>어트리뷰션:</strong> 아니요</p><p><strong>포스트백:</strong> 아니요</p></td></tr><tr><td><span>인게이지먼트(클릭)는 비활성화 전에 발생하나, 인스톨\/리어트리뷰션\/리인게이지먼트는 비활성화 후에 발생합니다.</span></td><td><p><span>해당 없음</span></p></td><td><span>비활성화된 파트너는 어트리뷰션되지 않습니다.</span></td></tr><tr><td>클릭과 노출</td><td>인게이지먼트는 측정되어 대시보드에 표시될 수 있습니다.</td><td><ul><li>클릭 시 403 금지 페이지로 리디렉션됩니다. </li><li>인게이지먼트는 측정되지 않으며 대시보드에 표시되지 않습니다.</li></ul></td></tr><tr><td>SKAN 어트리뷰션</td><td colspan="2"><p>적용되지 않음.</p><p>SKAN 어트리뷰션이 설정되면, <strong>파트너 활성화</strong> 설정이 켜져 있든 꺼져 있든 SKAN 데이터가 기록됩니다. </p></td></tr></tbody></table>

</Accordion>

<div id="activate-a-partner-integration" />

## 파트너 연동 활성화

**현재 선택된 앱의 메인 연동(연동 탭)을 활성화하거나 편집하려면:**

1. **활성화하려면:** 앱스플라이어의 사이드 메뉴에서 **협업**> **파트너 마켓플레이스**를 선택합니다.  
   **편집하려면:** 앱스플라이어의 사이드 메뉴에서 **협업**> **활성화된 연동**을 선택합니다.
2. 파트너를 검색하여 선택합니다. 연동 설정 페이지로 이동합니다.
3. **연동** 탭에서 **파트너 활성화**를 켭니다.
4. **연동 저장**을 클릭합니다.

[다른 연동 유형](#id)을 참조하세요.

<div id="caution" />

> ❗️ **주의**
>
> 설정을 사용하여 캠페인을 일시 중지하거나 종료하지 않도록 주의하세요. 그렇게 하면 활성 캠페인 측정에 돌이킬 수 없는 손상이 발생할 수 있습니다.

<div id="who-can-activate-an-integration" />

#### 누가 연동을 활성화할 수 있나요?

마케터와 대행사는 아래의 표에 따라 파트너 연동을 활성화할 수 있습니다.

| 활성화자 | SRN | 비(非) SRN |
| --- | --- | --- |
| 마케터 | 자체 사용 및 대행사를 대신하여 활성화 | 자체 사용을 위해 활성화 |
| 대행사 | 활성화할 수 없음 | 대행사에서 지정한 비(非) SRN 활성화 |

<div id="deactivate-a-partner-integration" />

## 파트너 연동 비활성화

**파트너 활성화** 토글을 끄면 귀사의 앱의 파트너 연동을 비활성화할 수 있습니다. 이로 인해 파트너는 전환 어트리뷰션을 받지 못하고 포스트백이 전송되지 않습니다. 그러나 다른 [연동 유형](#id) 중 하나가 계속 활성화된 경우, **파트너 활성화** 토글이 비활성화되더라도 계속 작동합니다. 이로 인해 해당 **연동이 계속 활성화되어** 데이터가 수집될 수 있음을 의미합니다.

<span id="deactivating-a-partner"></span>**파트너 연동을 비활성화하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동** 을 선택합니다.
2. 파트너를 검색하여 선택합니다. 연동 설정 페이지로 이동합니다.
3. **연동** 탭에서 **파트너 활성화**를 끕니다.
4. **연동 저장**을 클릭합니다.
5. 모든 [다른 연동 유형](#id)에서 파트너를 완전히 비활성화하려면 각 탭을 확인하고 비활성화하세요.  
   **참고:** Google 및 Meta Ads의 경우, SKAN 데이터를 중지하려면 SKAN 탭에서 연결을 삭제합니다.
6. **연동 저장**을 클릭합니다.
7. [선택 사항] 연동을 저장한 후 구성 페이지에 있는 동안 다른 앱에서 파트너를 비활성화할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택하세요.
   3. 2&#126;4단계를 반복합니다.

### 사용하지 않는 연동 비활성화

캠페인을 중단한 후에도 **파트너 활성화** 설정이 계속 켜져 있는 파트너는 캠페인 데이터를 포함하는 포스트백을 계속 받습니다. 정보 보호 문제의 가능성을 고려하여 사용하지 않는 연동을 비활성화하는 것을 권장합니다. 지난 30일 이상 활성화되어 있으나 사용되지 않은 파트너 연동을 식별하고 비활성화하도록 상기시키기 위해 활성화된 연동 페이지 상단에 경고 메시지가 표시됩니다.

<Image align="center" alt="active-integrations-deactivate-message-mini2.png" src="https://files.readme.io/46aaa3d5f76eef73f4f09caec1d7ec47bbfb0f0f42597c508972c0e3c80f7362-51912587906577.png" />

메시지에는 최근 전환이 없는 현재 선택한 앱의 연동을 보여주는 **사용하지 않는 연동 비활성화** 대화 상자의 링크가 포함되어 있습니다. 이 페이지에서 비활성 연동을 검토하고 비활성화할 항목을 선택할 수 있습니다.

> 📘 **참고**
>
> 대화 상자를 통해 연동을 비활성화하면 주요 연동만 비활성화됩니다(**파트너 활성화** 토글이 꺼짐). [다른 연동 유형](#id)이 남아 있으면 연동은 여전히 활성 상태로 간주됩니다.

**사용하지 않는 파트너 연동을 보고 비활성화하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
2. 페이지 상단의 경고 메시지에서 **검토 및 비활성화**를 클릭합니다.
3. **사용하지 않는 연동 비활성화** 대화 상자에서 현재 선택된 앱의 사용하지 않는 모든 파트너 연동을 볼 수 있습니다.  
   **참고:** 목록은 가장 많이 포스트백이 전송된 사용되지 않은 파트너 연동을 기준으로 정렬됩니다.
4. 비활성화할 파트너 연동을 선택하세요.
5. **비활성화**를 클릭합니다. 확인 후 선택된 파트너 연동이 비활성화됩니다.
6. 모든 [다른 연동 유형](#id)에서 파트너를 완전히 비활성화하려면 각 탭을 확인하고 비활성화하세요.  
   **참고:** Google 및 Meta Ads의 경우, SKAN 데이터를 중지하려면 SKAN 탭에서 연결을 삭제합니다.

또한 특정 파트너 연동 페이지로 이동하여 관련 탭에서 [연동 유형](#id)을 해제하여 파트너를 비활성화할 수 있습니다.

> 📘 **참고**
>
> * 대화 상자에서 연동을 비활성화하면 **파트너 활성화** 토글만 꺼집니다. [다른 연동 유형](#id)이 여전히 활성화되어 있으면 파트너 연동은 활성 상태로 간주됩니다.
> * 마케터는 특정 상황에서 플랫폼이 파트너 비활성화를 어떻게 처리하는지 주의해야 합니다. 마찬가지로, 포스트백이 필요한 마케팅 및 분석 파트너는 활성화해야 합니다.

#### 누가 경고 메시지를 보고 사용하지 않는 연동을 비활성화할 수 있나요?

* 계정 사용자는 자신이 구성을 편집할 수 있는 파트너에 대해서만 이 메시지를 볼 수 있습니다.
* 에이전시는 메시지를 보지만, 자신들의 연동만 비활성화할 수 있습니다.
* 파트너**는 연동 구성을 할 수 있는 권한이 있어도** 비활성화 메시지를 볼 수 없습니다.

<div id="partner-and-agency-access-to-dashboards" />

## 대시보드에 대한 파트너 및 에이전시 액세스

파트너와 에이전시는 각자의 권한에 따라 대시보드 보기와 구성 옵션이 다릅니다.

<div id="partner-visibility" />

### 파트너 가시성

* 파트너는 **파트너 활성화** 설정을 읽기 전용 모드로 볼 수 있습니다. 파트너가 연동 구성을 할 수 있는 권한이 있는 경우에도 마찬가지입니다.
* 파트너 설정의 가시성은 연동을 누가 구성했는지, 즉 마케터인지 에이전시인지에 따라 달라지며, 이는 다음 표에 자세히 설명되어 있습니다.

| 연동 설정 자 | 파트너에게 표시되는 설정 |
| --- | --- |
| 마케터 | 예 |
| 대행사 | 아니요 |

<div id="agency-permissions" />

### 에이전시 권한

귀사의 앱과 대행사 간에 작업 권한을 부여하여 대신 트래픽을 실행하도록 할 수 있습니다.

**앱에 에이전시 권한을 부여하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
2. 대행사를 찾아 선택하세요.
3. **권한** 탭으로 이동하여 **에이전시 권한**을 켭니다.
4. [선택 사항] 대행사에 추가 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">권한</Anchor>을 부여합니다.

<div id="note" />

> 📘 **참고**
>
> * **대행사**는 **비(非) SRN 파트너**에 대해 **파트너 활성화** 설정을 켜거나 끌 수 있습니다.
> * **마케터**는 **SRN**에 대한 **파트너 활성화** 설정을 켜거나 끌 수 있습니다. 이 경우 해당 SRN의 인스톨은 **에이전시에 어트리뷰션되지 않습니다**.

<div id="disabled-agency-permissions" />

#### 비활성화된 에이전시 권한

에이전시 권한이 비활성화된 경우:

* 에이전시는 앱스플라이어 대시보드에서 앱에 액세스할 수 없습니다.
* New 인스톨 및 이벤트는 에이전시에 어트리뷰션되지 않습니다.
* 포스트백은 에이전시가 사용하는 매체사로 전송되지 않습니다.
* 비활성화 전의 전환에 의한 New 이벤트는 마케터의 대시보드에 어트리뷰션되고 표시되지만, 포스트백은 매체사로 전송되지 않습니다.

**참고:** 마케터가 에이전시 권한을 비활성화하면 에이전시의 과거 데이터(예: 인스톨 및 비용)는 비투명해집니다.

다음 예는 마케터가 에이전시 권한을 제거한 후에도 계속 전송되는 트래픽에 무슨 일이 일어나는지 설명합니다:

<div id="example-1" />

> 📄 **예제 1**
>
> **비(非) SRN(어트리뷰션 링크 파트너) 에이전시 캠페인**
>
> 트래픽은 오가닉으로 어트리뷰션되거나 룩백 윈도우 내에 있을 경우 이전 인게이지먼트에 어트리뷰션됩니다. 에이전시는 어트리뷰션되지 않습니다.
>
> 이 예는 앱스플라이어가 클릭-쓰루 어트리뷰션 링크를 수신하고 파트너의 API를 쿼리하는 시나리오에도 적용됩니다.

<div id="example-2" />

> 📄 **예제 2**
>
> **SRN(어트리뷰션 링크 파트너)과의 에이전시 캠페인**
>
> 트래픽은 마케터 대시보드의 SRN에 어트리뷰션되지만, 에이전시에는 어트리뷰션되지 않습니다.

<div data-zendesk-anchors="overview=%ED%99%9C%EC%84%B1%ED%99%94-%EA%B0%9C%EC%9A%94 h_01HRA982WC3519NMGXV5WEY1AZ=%ED%99%9C%EC%84%B1%ED%99%94-%EA%B0%9C%EC%9A%94 01JDM949M75Q3BAG6M65DYMHZT=%ED%99%9C%EC%84%B1%ED%99%94-%EA%B0%9C%EC%9A%94 %20id%3D=id integration-types=id h_01HRAERWRJPQTT9GZA5M10ARW2=integration-activity-indication h_01HRPMG9SJHE32VMWS89P2HFAQ=%EC%B0%B8%EA%B3%A0 h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6THJ9TNGZZV78SEVBZN=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6THSEA65CY71VWJYX1P=%EC%A3%BC%EC%9D%98 who-can-activate-partners=%EB%88%84%EA%B0%80-%EC%97%B0%EB%8F%99%EC%9D%84-%ED%99%9C%EC%84%B1%ED%99%94%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01HJR1D6THRMF854SCSFVZFWM9=%EB%88%84%EA%B0%80-%EC%97%B0%EB%8F%99%EC%9D%84-%ED%99%9C%EC%84%B1%ED%99%94%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 deactivated-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6THE2QWSF971VQFXCBX=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner deactivate-unused-integrations=%EC%82%AC%EC%9A%A9%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EC%97%B0%EB%8F%99-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6THFWAZX3NSWYSD9126=%EC%82%AC%EC%9A%A9%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EC%97%B0%EB%8F%99-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1D6TH329RWMW3F1E5YZCT=%EC%B0%B8%EA%B3%A0-1 h_01HJR1D6THC13ZPV7H3CK8HYSV=%EC%B0%B8%EA%B3%A0-2 who-can-see-the-warning-message-and-deactivate-unused-integrations=%EB%88%84%EA%B0%80-%EA%B2%BD%EA%B3%A0-%EB%A9%94%EC%8B%9C%EC%A7%80%EB%A5%BC-%EB%B3%B4%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EC%97%B0%EB%8F%99%EC%9D%84-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01HRAK82N9J99VCEVF9KSJQVQR=%EB%88%84%EA%B0%80-%EA%B2%BD%EA%B3%A0-%EB%A9%94%EC%8B%9C%EC%A7%80%EB%A5%BC-%EB%B3%B4%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EC%97%B0%EB%8F%99%EC%9D%84-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 partner-and-agency-dashboards=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%B0%8F-%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HJR1D6THB0N1C8XCC5YAMQQ3=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%B0%8F-%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%95%A1%EC%84%B8%EC%8A%A4 partner-visibility=%ED%8C%8C%ED%8A%B8%EB%84%88-%EA%B0%80%EC%8B%9C%EC%84%B1 h_01HJR1D6TJ6D3TV2PCFWP4SEAR=%ED%8C%8C%ED%8A%B8%EB%84%88-%EA%B0%80%EC%8B%9C%EC%84%B1 agency-permissions=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HJR1D6TJ9T55PSPBRNW1XXS7=%EC%B0%B8%EA%B3%A0-3 disabled-agency-permissions=%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%EB%90%9C-%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HJR1D6TJ1ABQM6HCPK277R0Z=%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%EB%90%9C-%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HJR1D6TJBT0D3G2KWKFKEW5S=%EC%98%88%EC%A0%9C-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=%EC%98%88%EC%A0%9C-2" />
