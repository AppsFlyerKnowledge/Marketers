---
title: 리타겟팅 어트리뷰션 가이드
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-10-14T10:36:58Z'
  id: 207033786
  locale: ko
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ko/articles/207033786
---
> **요약:** 리타겟팅(리마케팅) 캠페인은 사용자가 앱에 다시 참여하거나, 앱을 삭제한 사용자가 앱을 재설치하도록 유도합니다.

<div id="retargeting-fundamentals" />

## 리타겟팅 기본 사항

리타겟팅 어트리뷰션은 사용자가 [리타겟팅 어트리뷰션 링크](/docs/retargeting-attribution-guide#retargeting-attribution-links) 또는 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">딥 링크</Anchor>를 클릭하여 리타겟팅 캠페인에 참여할 때 발생합니다. 이로 인해 다음 중 하나의 어트리뷰션 이벤트가 발생할 수 있습니다.

* **리인게이지먼트:** 디바이스에 앱이 있는 경우, 유저가 앱을 열도록 동기를 부여한 미디어 소스가 리인게이지먼트로 인정받습니다.
* **리어트리뷰션(일명 리타겟팅 재설치)**: 앱이 유저 디바이스에 없는 경우(즉, 유저가 앱을 삭제한 경우), 리타겟팅 캠페인에 참여하면 유저가 앱을 다시 설치하고 열게 됩니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우 동안 이 경우가 발생하면:</Anchor> 리타겟팅 미디어 소스에 리어트리뷰션이 적용됩니다. 관련 자료: <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#reinstalls">재설치.</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

리타겟팅 캠페인을 운영하기 전에, 다음 섹션에서 리인게이지먼트 규칙과 사례를 확인한 후, 리타겟팅 절차 섹션에 설명된 대로 리타겟팅을 설정하세요. 이해를 돕기 위해, 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">어트리뷰션 모델</Anchor>과 관련된 어트리뷰션 기간에 대한 이해가 필요합니다.

<div id="tip" />

> 👍 **팁**
>
> 리타겟팅에 대해 더 알고 싶으신가요? 앱스플라이어 학습 포털에서 짧고 유익한 <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">강좌</Anchor>를 확인하세요.

<div id="reengagement-rules-and-windows" />

<Accordion title="리인게이지먼트 규칙 및 기간">

* 리타겟팅 어트리뷰션 규칙은 이벤트가 리타겟팅 이벤트이고 리타겟팅 미디어 소스에 귀속되는지를 판단합니다.
* 유저 유입 어트리뷰션 캠페인과 유사하게 SRN 리타겟팅 리인게이지먼트는 API로 보고되며, 비-SRN의 경우 어트리뷰션 링크로 보고됩니다.
* 유저 여정에 따라 규칙이 구성됩니다:
  * [포함 기간](/docs/retargeting-attribution-guide#포함-기간)은 리인게이지먼트가 발생할 수 있는 기간입니다.
  * [제외 기간](/docs/retargeting-attribution-guide#제외-기간)은 리인게이지먼트가 발생할 수 없는 기간입니다.
* 리인게이지먼트가 귀속되면, 리인게이지먼트 기간 동안 인앱 이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">두 번 어트리뷰션됩니다.</Anchor> 즉, 리타겟팅 미디어 소스와 원래 UA 미디어 소스 (알려진 경우) 둘 다에 어트리뷰션이 됩니다.

다음 도표는 리인게이지먼트 규칙 세트를 포함합니다. 이를 가이드로 사용하여 리타겟팅 캠페인과의 상호작용이 리인게이지먼트로 어트리뷰션되는지 판단하세요.

**리인게이지먼트 규칙**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **참조-포함 및 제외 기간**

다음 표는 리타겟팅 어트리뷰션 관련 기간에 대한 참조 정보를 포함합니다.

<div id="inclusion-windows" />

#### 포함 기간

| 기간 유형 | 설명 |
| --- | --- |
| 뷰-쓰루(view-through) | 사용자가 광고를 본 이후 앱을 열 때까지의 최대 기간입니다.<br /><br />**구성 위치:** 어트리뷰션 링크<br /><br />**기간**:<ul><li>기본값: 1일</li><li>범위: 1-23시간\/1-7일</li></ul> |
| 클릭 룩백 | 사용자가 광고를 클릭한 후 앱을 열 때까지의 최대 기간입니다.<br /><br />**구성 위치**: 어트리뷰션 링크<br /><br />**기간** :<ul><li>기본값: 7일</li><li>범위: 1-23시간\/1-30일</li></ul>**SRN 비고:** SRN의 특정 룩백 윈도우 정책을 확인하세요. |
| 리인게이지먼트 | 리인게이지먼트 기간에 대해 다음 사항을 고려하세요.<ul><li>이 기간은 사용자가 리타겟팅 미디어 소스와 상호작용한 후 처음 앱을 열 때 시작됩니다.</li><li>인앱 이벤트는 기간 동안 리타겟팅과 유저 유입 미디어 소스에 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor>됩니다.</li><li>기간은 앱 설정이나 SRN에 의해 결정됩니다.</li><li>리인게이지먼트 기간 중 사용자가 다른 리타겟팅 캠페인과 상호작용하며 제외 기간에 의해 차단되지 않는 경우, 현재 리인게이지먼트 기간이 즉시 종료되고 새 리인게이지먼트 기간이 시작됩니다.</li><li>리어트리뷰션의 맥락에서:  **어트리뷰션 윈도우** 기간은 시간 제한이 없습니다 (인스톨과 유사). 그러나 새로 인스톨하거나 재설치하는 경우 또는 데이터 리텐션 제한으로 인해 이 기간이 종료됩니다.</li></ul>**설정 위치:** 어트리뷰션 링크<ul><li>기본값: 30일</li><li>범위: 1-23시간\/1-90일\/수명</li></ul>**SRN 비고**: SRN에 대해 설정할 수 있습니다.<br /><br />기간 설정을 변경하면 앞으로의 리인게이지먼트에 영향을 미칩니다. 기존 리인게이지먼트에는 영향을 미치지 않습니다. |

<div id="exclusion-windows" />

#### 제외 기간

| 기간 유형 | 설명 |
| --- | --- |
| 리인게이지먼트 전환 사이의 최소 시간 | 제외 기간 동안 리인게이지먼트를 기록하지 마세요.<br /><br />**리인게이지먼트 전환 사이의 최소 시간**<ul><li>리인게이지먼트 시, 인앱 이벤트가 리타겟팅 및 UA 캠페인 양측에 어트리뷰션되는 기간이 열립니다.</li><li>이로 인해 리타겟팅 캠페인의 성과를 측정할 수 있습니다.</li><li>이 기간 중 다른 네트워크나 캠페인이 리인게이지먼트를 가져오면:<ul><li>[기본값] 기존 리인게이지먼트 기간이 닫히고, 새로운 리인게이지먼트가 기록되며 이후의 인앱 이벤트는 최근의 리인게이지먼트에 어트리뷰션됩니다.</li><li>이를 방지하려면, 리인게이지먼트 전환 사이의 최소 시간을 설정하세요. 이 경우, 최소 경과 시간이 지난 후에만 추가적인 리인게이지먼트를 기록할 수 있습니다.</li></ul></li><li>이 설정은 리인게이지먼트 기간이 이 설정의 기간보다 짧은 경우에는 영향을 미치지 않습니다. 예: 리인게이지먼트 기간이 1일이고, 이 설정이 4일인 경우, 이 설정은 아무런 영향을 미치지 않습니다.</li><li>이러한 설정은 인스톨과 리인게이지먼트 사이의 기간에는 영향을 미치지 않습니다.</li></ul>**설정 위치**: 앱 설정 페이지<br /><br />**기간**:<ul><li>기본값: 없음</li><li>범위: 1-23시간\/1-30일</li></ul> |
| <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window">최소 비활성 기간</Anchor> | 제외 기간 동안 리인게이지먼트 또는 리어트리뷰션을 기록하지 마세요.<br /><br />**설정 위치:** 연동 탭의 통합 파트너 설정 페이지.<br /><br />**기간**:<ul><li>기본값: 없음</li><li>0-30일</li></ul>**SRN 비고**: SRN은 일반적으로 고유의 비활성 기간 규칙을 가지고 있다는 점을 고려하세요. 귀사의 설정이 SRN의 설정과 다르면 불일치가 발생할 수 있습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션</Anchor> | 리어트리뷰션 윈도우는 리어트리뷰션에 영향을 미치지만 리인게이지먼트에는 영향을 미치지 않습니다.<br /><br />리타겟팅 캠페인에 참여한 후 리어트리뷰션 윈도우 동안 재설치를 한 사용자는 리타겟팅 매체 소스에 어트리뷰션됩니다. 관련 자료: <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#reinstalls">재설치</Anchor><br /><br />**설정 위치:** 앱 설정 |

<div id="example-flow-implementing-the-rules" />

#### **규칙 구현 예시 흐름**

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

클릭-쓰루 및 뷰-쓰루 어트리뷰션을 위한 리인게이지먼트 규칙 체크리스트:

| 규칙 | 규칙 |
| --- | --- |
| A | 사용자가 리타겟팅 캠페인에 참여했습니다. 즉, 리타겟팅 광고로 정의된 광고를 보거나 클릭한 것입니다. |
| B | 해당 인게이지먼트는 클릭 룩백 또는 뷰-쓰루 기간**에** 발생했습니다. |
| C | 사용자는 최소 비활성 기간보다 오랜 시간 동안 비활성 상태였습니다. |
| D | 인앱 이벤트는 리인게이지먼트 기간 동안 발생합니다. |
| E | 이전 리인게이지먼트 간의 기간이 리인게이지먼트 간의 최소 기간보다 깁니다. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="리타겟팅 예시 시나리오">

| **시나리오 1: 리인게이지먼트 기간 전, 중, 후의 구매**<br /><br />유저 여정:<ul><li>네트워크 Z의 광고를 보고 앱을 인스톨한 후 구매합니다(A).</li><li>네트워크 Y에서 리타겟팅 광고를 보고 앱을 열어 구매합니다(B).</li><li>추가 구매(C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />P\/S 열: <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">리타겟팅 이벤트의 이중 어트리뷰션</Anchor>에 설명된 기본 또는 보조 |
| --- |
| **시나리오 2: 리인게이지먼트 어트리뷰션 기간 동안의 다중 전환**<br /><br />유저 여정:<ul><li>네트워크 Z의 광고를 보고 앱을 인스톨한 후 구매합니다(A).</li><li>네트워크 Y에서 리타겟팅 광고를 보고 앱을 열어 구매합니다(B).</li><li>추가 구매(C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />P\/S 열: <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">리타겟팅 이벤트의 이중 어트리뷰션</Anchor>에 설명된 기본 또는 보조 |

</Accordion>

<div id="retargeting-operations" />

## 리타겟팅 작업

<div id="retargeting-settings" />

<Accordion title="리타겟팅 설정">

시나리오에 따라 필요한 설정:

| 전환 유형 | SRN | 비 SRN |
| --- | --- | --- |
| 리인게이지먼트 | <ol><li>앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.</li><li>**리인게이지먼트** **어트리뷰션** 이 켜져 있는지 확인하세요.</li><li>SRN별:</li><li>사이드 메뉴에서 **협업** > **활성 연동**을 선택하고 SRN을 선택합니다.</li><li>**리인게이지먼트 어트리뷰션**을 켭니다.</li></ol> | <ol><li>앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.</li><li>**리인게이지먼트 어트리뷰션** 이 켜져 있는지 확인하세요.</li><li>비 SRN별: 이 섹션에 자세히 설명된 대로 어트리뷰션 링크에 리타겟팅 매개변수를 추가합니다.</li></ol> |
| 리어트리뷰션 | <ol><li>사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.</li><li>**재설치 어트리뷰션**을 켭니다.</li></ol> | <ol><li>명시적인 설정이 필요하지 않습니다.</li><li>이 섹션에 자세히 설명된 대로 어트리뷰션 링크에 리타겟팅 매개변수를 추가합니다.</li></ol> |

<div id="non-srn-settings" />

#### **비 SRN 설정**

**비 SRN 애드 네트워크 리타겟팅 파트너 설정 방법**:

1. 사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.
2. 애드 네트워크를 선택하세요.
3. 리타겟팅 설정을 켜세요. 이는 `is_retargeting=true`을 링크에 추가하여 어트리뷰션 링크를 리타겟팅 URL로 수정합니다.
4. 다음 중 하나를 선택하세요.
   * **단일 플랫폼(앱별) 링크에는 표준 어트리뷰션 링크를 사용하세요**.
   * **원링크를 사용하세요**.
     * 필요한 경우 **딥 링크 URL**을 입력하세요. (<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">딥링킹</Anchor> 가이드 참조)
5. 발생한 URL을 복사하여 애드 네트워크와 공유하여 리타겟팅 캠페인에 사용하세요.  
   **참고**: URL은 지속되지 않으며 저장할 수 없습니다.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="리타겟팅 대시보드">

개요 대시보드에는 리타겟팅 및 유저 유입 측정항목이 포함되어 있습니다. 이 측정 항목은 LTV(유저생애가치)를 기반으로 하며 리타겟팅 캠페인에 참여하는 사용자를 대상으로 합니다.

**리타겟팅 데이터를 보려면**:

1. 사이드 메뉴에서 **분석** > **개요**를 선택합니다.
2. ‘**보기 유형**’을 클릭하고 ‘**리타겟팅**’을 선택하세요.  
   리타겟팅 데이터가 표시됩니다.  
   **참고**: 통합 뷰에서도 리타겟팅 데이터를 확인할 수 있습니다. 대시보드 보기 유형을 참조하세요.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="리타겟팅 어트리뷰션 링크">

* 리타겟팅 링크는 일반 유저 유입 링크와 비슷합니다.
* 다음 용도로 생성하세요:
  * 리타겟팅을 지원하는 비 SRN.
  * 링크 관리 페이지를 사용하여 온드 미디어를 관리하세요.

리타겟팅 어트리뷰션 링크의 파라미터

| 파라미터 | 설명 | 필수 |
| --- | --- | --- |
| `is_retargeting` | 설정: `is_retargeting=true` | 예 |
| 광고 ID | 가능하면 IDFA, OAID, IDFV 등의 광고 ID를 발송하세요. <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">iOS 앱의 확률적 모델링 제한 사항.</Anchor> | 아니요 |
| 리타겟팅 클릭 룩백 윈도우 | <ul><li>리타겟팅 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우</Anchor>는 유저 유입 캠페인과 비슷하게 작동합니다.</li><li>사용자가 광고를 클릭한 후 귀속되기까지의 최대 기간을 정의합니다.</li><li>룩백 윈도우는 `&af_click_lookback` 매개변수를 사용하여 설정됩니다.</li><li>기본 설정은 7일입니다.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>예**<br />14일 클릭-쓰루 룩백 윈도우를 설정하려면, 리타겟팅 캠페인의 어트리뷰션 링크에 다음을 추가하세요: `&af_click_lookback=14d` | 아니요 |
| 리타겟팅 뷰-쓰루 룩백 타이머 | <ul><li>리타겟팅 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">뷰-쓰루 룩백 윈도우</Anchor>는 유저 유입 캠페인과 유사하게 작동합니다.</li><li>사용자가 광고를 본 후 귀속되기까지의 최대 기간을 정의합니다.</li><li>기본값은 1일입니다.</li><li>룩백 윈도우는 다음을 사용하여 설정합니다.</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>예**<br />5시간의 뷰-쓰루 룩백 윈도우를 설정하려면 리타겟팅 캠페인의 어트리뷰션 링크에 다음을 추가하세요: `&af_viewthrough_lookback=5h` | 아니요 |
| 리인게이지먼트 윈도우 | <ul><li>**리인게이지먼트 윈도우**는 어트리뷰션 링크 사용자 인터페이스에서 설정할 수 있습니다. 이 설정은 어트리뷰션 링크에 **af\_reengagement\_window** 매개변수를 추가합니다. 매개변수는 수동으로 추가할 수 있습니다.</li><li>기본값은 30일입니다.</li><li>사용 가능한 리인게이지먼트 윈도우 값은 다음과 같습니다.</li><li>시간: 1-23시간</li><li>일: 1-90일</li><li>평생: 사용자가 앱 삭제하거나 다른 리인게이지먼트를 수행할 때까지 지속됩니다. 예: af\_reengagement\_window=lifetime</li></ul>예를 들어, **af\_reengagement\_window=60d**는 리인게이지먼트 후 60일 이내에 보고된 이벤트가 리타겟팅 미디어 소스에 어트리뷰션된다는 뜻입니다. | 아니요 |

<div id="retargeting-view-through-lookback-period" />

#### 리타겟팅 뷰-쓰루 룩백 윈도우

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="리타겟팅 리포트 및 로데이터">

* UA의 <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">집계</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터</Anchor> 리포트와 유사한 리타겟팅 리포트는 리포팅 도구를 통해 제공됩니다.
* 리타겟팅 인앱 이벤트 및 세션은 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션됩니다.</Anchor>

**리타겟팅 전환 리포트**

* 리타겟팅 전환 리포트에는 리인게이지먼트 및 리어트리뷰션의 로데이터가 포함됩니다.
* 일부 필드는 리타겟팅의 맥락에서 유저 유입 리포트에 사용된 필드와 다른 의미를 가집니다.

리타겟팅 맥락에서의 로데이터 리포트 해석

| 열 | **설명** |
| --- | --- |
| 이벤트 이름 | <ul><li>필드의 인구 구성은 리포트 유형에 따라 다릅니다.</li><li>인앱 이벤트 리포트: 인앱 이벤트 이름.</li><li>리타겟팅 전환 리포트: 리인게이지먼트 또는 리어트리뷰션. **참고**! 데이터 락커의 경우 값은 다음과 같습니다:<ul><li>인스톨은 리어트리뷰션을 의미합니다</li><li>리타겟팅은 리인게이지먼트를 의미합니다</li></ul></li></ul> |
| 속성 터치 유형 | 인게이지먼트 유형:<ul><li>클릭</li><li>노출</li></ul> |
| 어트리뷰션된 터치 시간 | 리타겟팅 인게이지먼트 시간 |
| 인스톨 시간 | 리인게이지먼트 또는 리어트리뷰션 후 첫 앱 실행 시간입니다. |
| 이벤트 시간 | 이벤트가 발생한 시간 |
| 앱스플라이어 ID | <ul><li>리어트리뷰션: 새로운 앱스플라이어 ID</li><li>리인게이지먼트: 변경되지 않음</li></ul> |
| 리타겟팅임 | 리타겟팅 전환과 이벤트에 TRUE |
| 기본 어트리뷰션 | 리타겟팅 전환과 이벤트에 TRUE |
| 리타겟팅 전환 유형 | 이 필드는 향후에 더 이상 사용되지 않을 예정입니다 (날짜는 추후 공지 예정). 전환의 맥락을 파악하려면 conversion\_type과 campaign\_type을 사용하세요.<ul><li>리인게이지먼트</li><li>리어트리뷰션</li></ul> |
| 전환 유형 | 전환 유형:<ul><li>인스톨</li><li>재설치(1)</li><li>리인게이지먼트</li><li>알 수 없음(2)</li></ul>(1) conversion\_type이 재설치이고, campaign\_type이 리타겟팅인 경우, 리타겟팅 전환 유형은 리어트리뷰션과 동일합니다<br /><br />(2) 어떤 미디어 소스에도 어트리뷰션되지 않은 인앱 이벤트\세션. |
| 캠페인 유형 | 유저를 유입시키는 소스:<ul><li>UA</li><li>오가닉</li><li>리타겟팅</li><li>알 수 없음</li></ul> |
| 어트리뷰션 룩백 | 리타겟팅 클릭-쓰루 룩백 윈도우 |
| 원본 URL | 다음 중 하나를 포함:<ul><li>리타겟팅 링크</li><li>딥링킹 데이터</li><li>SRN에 비어 있음</li></ul> |
| 기여자 필드 | 리인게이지먼트에 대해 사용 불가 |

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="probabilistic-modeling" />

<Accordion title="확률적 모델링">

2021년 2월 17일부터 리타겟팅에서 확률적 모델링이 지원됩니다. <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#note-for-ios-apps">iOS 14.5+의 제한 사항이 적용됩니다</Anchor>. 리타겟팅 확률적 모델링에 사용되는 룩백 윈도우는 앱스플라이어에서 운영 체제에 따라 동적으로 설정됩니다.

전송된 클릭에 필요한 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#애드-네트워크에-대한-확률적-모델링-파라미터">확률적 모델링 파라미터</Anchor>가 포함되어 있는지 확인하십시오.

</Accordion>

<div id="app-requirements" />

<Accordion title="앱 요구 사항">

리타겟팅 캠페인을 실행하려면 앱이 다음 최소 요구 사항을 충족해야 합니다.

* iOS
  * 표준 앱스플라이어 SDK 연동 외에도 앱 대리자에 추가 코드를 추가해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#원링크를-사용한-딥링킹">SDK 연동</Anchor> 문서(어트리뷰션 링크 섹션)를 참조하십시오.
  * iOS 9의 경우 유니버설 링크 앱 오픈 코드를 구현해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">iOS 9의 유니버설 링크</Anchor>
* 안드로이드:

  * 딥 링크가 기본 액티비티 외의 액티비티를 여는 경우 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#deep-linking">SDK 연동</Anchor> 문서(어트리뷰션 링크 섹션)를 참조하십시오.

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="리타겟팅 제한 사항">

* 2021년 2월 17일부터 리타겟팅에서 확률적 모델링을 지원합니다.
* 리타겟팅에 대한 캠페인 비용 데이터는 통합 보기의 개요 및 코호트 대시보드와 보고서에서 확인할 수 있습니다.

</Accordion>

<div id="faq" />

<Accordion title="자주 묻는 질문">

| **리타겟팅 클릭:**<ul><li>리타겟팅 클릭에는 앱스플라이어 어트리뷰션 링크에 참여한 리타겟된 사용자가 포함됩니다.</li><li>SRN이나 <Anchor target="_blank" href="/marketers/ko/docs/measuring-push-notification-re-engagement-campaigns">푸시 알림</Anchor>에서 발생한 클릭은 계산에 포함되지 않습니다.</li><li>일부 클릭은 유저 유입으로 간주되는 새로운 인스톨로 이어집니다. 이는 비사용자 또는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor> 만료 후 이전 사용자가 리타겟팅 링크에 참여하고 인스톨할 때 발생합니다.</li></ul> |
| --- |
| **어트리뷰션 된 터치와 인스톨 시간이 언제 동일한가요?**<ul><li>유니버설 링크나 안드로이드 앱 링크를 사용하는 사용자가 딥 링크를 수행하면 앱스플라이어를 거치지 않고 앱으로 직접 이동합니다.</li><li>앱이 실행되고 SDK가 새로운 리인게이지먼트를 보고하면, 앱스플라이어는 실행과 동일한 타임스탬프를 사용하여 클릭 데이터를 복원합니다. 이로 인해 참여 시점과 실행 시간이 동일해집니다.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">앱스플라이어 어트리뷰션 모델</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">오디언스 가이드</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EA%B8%B0%EB%B3%B8-%EC%82%AC%ED%95%AD h_01HCFJHC85VK0A05X5F69E2WKT=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EA%B8%B0%EB%B3%B8-%EC%82%AC%ED%95%AD h_01HCFJHC851PV0VR42H07VQAXF=%ED%8C%81 h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=%ED%8F%AC%ED%95%A8-%EA%B8%B0%EA%B0%84 h_01HCFJHC85FRFJ531Y08DW03Y2=%ED%8F%AC%ED%95%A8-%EA%B8%B0%EA%B0%84 exclusion-windows=%EC%A0%9C%EC%99%B8-%EA%B8%B0%EA%B0%84 h_01HCFJHC85ECS3PJV80D943TVY=%EC%A0%9C%EC%99%B8-%EA%B8%B0%EA%B0%84 example-flow-implementing-the-rules=%EA%B7%9C%EC%B9%99-%EA%B5%AC%ED%98%84-%EC%98%88%EC%8B%9C-%ED%9D%90%EB%A6%84 h_01HCFJHC8529NW0ABMQ0RB3E8R=%EA%B7%9C%EC%B9%99-%EA%B5%AC%ED%98%84-%EC%98%88%EC%8B%9C-%ED%9D%90%EB%A6%84 h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%9E%91%EC%97%85 h_01HCFJHC863XPHNWRHJ60JPSRF=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%9E%91%EC%97%85 h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=%EB%B9%84-srn-%EC%84%A4%EC%A0%95 h_01HCFJHC865V36R3H58D5PWXYY=%EB%B9%84-srn-%EC%84%A4%EC%A0%95 h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HCFJHC863CSP03AYBXFSNC37=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCFJHC86RKKPPMBYEZV4Q3X9=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
