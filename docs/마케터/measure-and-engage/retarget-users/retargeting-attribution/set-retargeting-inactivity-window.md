---
title: 리타게팅 비활성 기간
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-10-14T10:39:29Z'
  id: 360009305817
  locale: ko
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ko/articles/360009305817
---
> **한눈에 보기:** 비활성 사용자를 대상으로 한 리타겟팅을 통해 성과 증가분을 높일 수 있습니다. 미디어 소스별 비활성 기간 설정하기.
>
> ![](https://files.readme.io/d18c3ba0a4693866646e3dec57ea2c56ac4df1468bf92f5b38f0a864e3ead50c-51912966877329.png)

<div id="inactivity-period" />

## 비활성 기간

광고주는 리타겟팅을 통해 활동이 멈춘 유저를 다시 끌어들입니다. 이런 캠페인들은 흔히 높은 전환율을 보이며 상당한 ROAS를 창출합니다. 하지만, 활성 유저를 선별하지 않아 성과가 낮아지는 리타겟팅 캠페인들도 많습니다. 리타겟팅 캠페인의 추가적인 성과 향상을 위해서는, 활성 유저를 거르기 위해 **최소 비활성 기간**을 적용하십시오.

최소 비활성 기간을 설정함으로써 광고주는 활성 유저에게 어트리뷰션을 하지 않게 됩니다. 예시로, 최소 비활성 기간이 3일인 경우, 지난 0-3일 동안 활동한 유저들은 어트리뷰션 대상에서 제외됩니다. 4일 이상 비활성 상태였던 유저들은 어트리뷰션 대상이 됩니다. 비활성 기간은 재어트리뷰션과 재인게이지먼트 상황 모두에 적용됩니다. 재어트리뷰션의 상황에서는 마지막 활동이 앱을 삭제하기 전 마지막 세션을 의미합니다.

**비활성 규칙**

* **어트리뷰션됨:** 설정된 비활성 기간 이상 앱을 사용하지 않은 이용자. 리타겟팅으로 재참여하거나 앱을 재설치하는 경우 어트리뷰션됩니다.
* **어트리뷰션되지 않음**: 최소 비활성 기간을 초과하지 않고 앱을 실행하는 활성 유저들은 리타겟팅 캠페인에 어트리뷰션되지 않습니다.

<div id="retargeting-inactivity-terminology" />

### 리타겟팅 비활성 용어 설명

| 용어 | 정의 |
| --- | --- |
| 최대값 | 30일 |
| 기본값 | 0 (해당 없음)  <br />미디어 소스별 **비활성 기간** 기능은 기본 설정에서 활성화되어 있지 않습니다. |
| 사용자 활동 | SDK나 서버 대 서버를 통해 보고된 설치 또는 세션. |
| 이전된 디바이스 | 이전 시간은 마지막 활동 시간으로 간주됩니다. |

<div id="scenarios" />

## 시나리오

리타겟팅 시나리오에서는 미디어 소스별로 비활성 기간이 명시됩니다.

<div id="reattribution" />

<Accordion title="리어트리뷰션">

다음 그림에서는 사용자 시나리오를 설명합니다. 사용자:

* 앱을 삭제하고 활동이 없음
* 미디어 소스가 진행하는 리타겟팅 캠페인에 참여함
* 앱을 다시 설치함

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| 시나리오 | 비활성 기간 임계값 | 사용자 비활성 기간 | 완료 후 |
| --- | --- | --- | --- |
| A | 7일 | 8일.<br /><br />**사용자가 비활성** 상태였던 기간이 비활성 임계값을 초과했습니다 | <ul><li>**재어트리뷰션** (리타겟팅을 통한 재설치)</li><li>리타겟팅 미디어 소스 A로 인정됨</li></ul> |
| B | 14일 | 5일<br /><br />사용자가 활동하고 있었습니다. | <ul><li>**오가닉 재설치**</li><li>**논오가닉 재설치:** 유저가 UA 미디어 소스와 상호작용했을 경우.</li><li>리타겟팅 미디어 소스 A는 사용자의 비활성 기간 임계값으로 인해 어트리뷰션할 수 없습니다.</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="리인게이지먼트">

다음 그림에서는 사용자 시나리오를 설명합니다. 사용자:

* 앱을 설치함
* 여러 날 동안 활동 없음
* 그 후 미디어 소스가 주관하는 리타겟팅 캠페인에 참여해 앱을 실행함

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| 시나리오 | 미디어 소스 A의 비활성 기간 임계값 | 사용자 비활성 기간 | 완료 후 |
| --- | --- | --- | --- |
| A | 7일 | 8일<br /><br />**사용자가 비활성** 상태였던 기간이 비활성 임계값을 초과했습니다 | <ul><li>**리인게이지먼트**가 미디어 소스 A로 어트리뷰션됨</li></ul> |
| B | 7일 | 4일<br /><br />설정된 비활성 기간 내에 **사용자가 앱을 사용함**. | <ul><li>**정규 세션**</li><li>리타겟팅을 위한 미디어 소스 A 어트리뷰션되지 않음</li></ul> |

</Accordion>

<div id="partner-setup" />

## 파트너 설정

<div id="zd-srn" />

<Accordion title="SRN">

비활성 기간을 지원하는 SRN은 해당 기능을 그들의 연동 탭에서 설정할 수 있습니다.

**리타겟팅을 지원하는 자체 보고 네트워크(SRN)에 비활성 기간을 설정하려면:**

1. 앱스플라이어의 왼쪽 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. SRN을 선택하세요.
3. **연동** 탭까지 내려가세요. **리타겟팅 시 활성 유저 무시**를 활성화합니다
4. **비활성 윈도우 설정.** (1-30일 사이.)
5. **연동 저장**을 클릭하세요.

[![Inactivity_window_SRN.png](https://files.readme.io/a25c3ef3bf92179354072914552f234426981ac47e06a11b02a267593c1da4c8-51912966881937.png)](https://files.readme.io/a25c3ef3bf92179354072914552f234426981ac47e06a11b02a267593c1da4c8-51912966881937.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="비-SRN(클릭 기반 애드 네트워크)">

**리타겟팅을 지원하는 비-SRN에 대한 비활성 기간을 설정하려면:**

1. 앱스플라이어의 왼쪽 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 애드 네트워크를 선택하세요.
3. **어트리뷰션 링크** 탭까지 이동한 후, 아래로 스크롤하고 **리타겟팅 시 활성 유저 무시**를 활성화합니다.
4. **비활성 윈도우 설정.** (1-30일 사이.)  
   **비활성 기간** 파라미터를 어트리뷰션 링크에 추가합니다. 예: "&af\_inactivity\_window=7d". 기능이 비활성화되어 있다면, 어트리뷰션 링크에 포함되지 않습니다.

[![Inactivity_window_non-SRN.png](https://files.readme.io/d57b6537f1d9953a5a89e95deef1083a3b9c3e4fcc92f91a161770fdbcd233ae-51912966884881.png)](https://files.readme.io/d57b6537f1d9953a5a89e95deef1083a3b9c3e4fcc92f91a161770fdbcd233ae-51912966884881.png)

</Accordion>

<div id="agencies" />

<Accordion title="에이전시">

#### SRN

광고주가 권한을 준 에이전시

**비활성 기간 설정 접근 방법:**

1. 앱스플라이어의 왼쪽 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. SRN을 선택하세요.
3. **연동** 탭에서, 이어지는 표에 따라 설정을 진행하세요.

| SRN | 에이전시 |
| --- | --- |
| 더블클릭 | <ul><li>리타겟팅 활성화/비활성화 가능</li><li>비활성 기간 구성 가능</li></ul> |
| Google Ads | <ul><li>리타겟팅 활성화/비활성화 불가능</li><li>에이전시에게 권한이 있다면, 비활성 기간을 구성할 수 있음</li></ul> |
| Meta 광고/X 광고/Snapchat | 리타겟팅 및 비활성 기간 설정 접근 불가능 |

#### Non-SRN

리타겟팅을 지원하는 파트너

**리타겟팅을 지원하는 비-SRN에 대한 비활성 기간을 설정하려면:**

1. 앱스플라이어의 왼쪽 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 비-SRN 광고 네트워크를 선택 > **어트리뷰션 링크** 탭으로 이동하세요.

</Accordion>

<div data-zendesk-anchors="inactivity-period=%EB%B9%84%ED%99%9C%EC%84%B1-%EA%B8%B0%EA%B0%84 h_01H9JS3QKW5S7VP9YW05CB6STR=%EB%B9%84%ED%99%9C%EC%84%B1-%EA%B8%B0%EA%B0%84 retargeting-inactivity-terminology=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%B9%84%ED%99%9C%EC%84%B1-%EC%9A%A9%EC%96%B4-%EC%84%A4%EB%AA%85 h_01H9JS3QKXMBS95RG06A9JXGT0=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%B9%84%ED%99%9C%EC%84%B1-%EC%9A%A9%EC%96%B4-%EC%84%A4%EB%AA%85 scenarios=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4 h_01H9JS3QKXWDX8Y58GX1G5HNYY=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4 h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%84%A4%EC%A0%95 h_01H9JS3QKXGNFM8499G52458B2=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%84%A4%EC%A0%95 srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=non-srn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=non-srn" />
