---
title: 데이터 협업 플랫폼(DCP) - 측정 실행 및 관리
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-10-14T10:28:03Z'
  id: 44427723216017
  locale: ko
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ko/articles/44427723216017
---
> **한눈에 보기:** 현장 또는 비현장 측정을 구성한 후, 이를 실시간 측정 또는 역사적 측정으로 실행합니다. 목표에 가장 적합한 모드를 선택하십시오: 성능을 지속적으로 측정하거나 정의된 기간 동안 결과를 검증합니다.

<div id="about-the-measurement-run-modes" />

## 측정 실행 모드에 대하여

현장 또는 비현장 측정을 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#온사이트-및-오프사이트-캠페인-측정">구성한 후</Anchor>, 측정을 실행하는 방법을 선택할 준비가 되었습니다.

사용 가능한 실행 모드는 두 가지입니다:

* **실시간 측정**: 정기적으로 업데이트되는 지속적인 측정으로, 실시간 대시보드에 새로운 데이터가 추가됨에 따라 성능을 지속적으로 모니터링할 수 있습니다.
* **역사적 측정**: 특정 날짜 범위에 대한 일회성 측정으로, 역사적 대시보드에서 보고 분석할 수 있습니다.

<div id="live-vs-historical-measurements" />

### 실시간 측정 대 역사적 측정

| 주제 | 역사적 측정 | 실시간 측정 |
| --- | --- | --- |
| 실행 시 | **온디맨드** (수동) 실행 | **자동화된** 일일 실행 |
| 데이터 소스 | **역사적 데이터 업로드** 사용 | **SDK/ETL 설정** 필요 및 미리 정의된 시간 간격으로 실행 |
| 지원되는 소스 유형 | <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">추가</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">덮어쓰기(스냅샷)</Anchor> | <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">사용자 정의 소스 추가</Anchor> |
| 시간 프레임 선택 | 사용 가능한 데이터에서 **시작 및 종료 날짜**를 선택하세요 | **시작 날짜만 선택하세요** (플랫폼이 활성화 시 역사적 시간 프레임을 계산하고 데이터를 계속 축적합니다) |
| 측정당 몇 개 | 다수 | 하나의 |

<div id="choose-the-measurement-you-need" />

### 필요한 측정을 선택하세요

아래의 안내를 사용하여 목표에 맞는 측정을 결정하세요.

**원하는 경우 실시간 측정을 선택하세요**

* 새 데이터가 도착할 때마다 업데이트되는 지속적인 측정
* 성능을 지속적으로 모니터링할 수 있는 대시보드
* 장기적으로 항상 켜져 있는 측정을 위한 설정 (일회성 분석이 아님)

**원하는 경우 역사적 측정을 선택하세요**

* 특정 날짜 범위에 대한 일회성 측정을 실행하세요.
* 캠페인이 종료된 후 성능을 분석하세요.
* 어떤 경우 분석을 실행하여 회고 기간을 변경하고 그것이 귀속에 미치는 영향을 확인하세요.

**팁:** 설정을 테스트하거나 특정 기간을 먼저 검증하는 경우 **역사적 측정**부터 시작하세요. 지속적인 모니터링을 준비할 때, **실시간 측정**으로 전환하여 지속적인 업데이트를 받으세요.

<div id="run-a-live-measurement" />

## 실시간 측정을 실행하세요

**시작하기 전에**  <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#온사이트-및-오프사이트-캠페인-측정">측정 설정 페이지에서 현장 또는 비현장 측정 캠페인을 구성하세요</Anchor>.

1. **측정 설정** 페이지에서 **지금 실행**를 클릭하세요.

   **실행하기**가 비활성화되어 있으면, 측정 작업이 완료되지 않습니다. 측정을 실행하기 위해 필요한 모든 설정 작업을 완료하십시오.
2. **실행 준비** 대화 상자에서 **실시간 대시보드**를 선택하십시오.

   <div id="note" />

   > 📘 **참고**
   >
   > * 측정이 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">덮어쓰기</Anchor> 소스를 사용하는 경우, **히스토리 대시보드**만 사용할 수 있습니다. **실시간 대시보드**는 자동으로 새로 고침하기 위해 **추가형** 소스(또는 AppsFlyer SDK 내 이벤트)가 필요합니다.
   > * 협업에서는 **하나의 실시간 측정**만 동시에 실행할 수 있습니다. 다른 실시간 측정이 이미 실행 중일 때 새 실시간 측정을 시작하면 기존 측정을 일시 중지하라는 메시지가 표시됩니다.

3. 대시보드의 이름을 바꾸거나 기본 이름을 유지하십시오.
4. **측정 시작 날짜**를 선택하십시오. 기본값은 오늘 날짜이며, 날짜 선택기에서 과거 날짜를 선택할 수 있습니다. (데이터 소스에 존재하는 날짜만 선택할 수 있습니다.)
5. **시작**을 클릭하여 실시간 측정을 시작하십시오. 협업 측정 페이지로 리디렉션됩니다.
6. 협업 측정 페이지에서 자동 검증 검사가 성공적으로 완료된 후 **실행하기**를 클릭하십시오.

<div id="run-a-historical-measurement" />

## 히스토리 측정을 실행하십시오.

**시작하기 전에**  <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#온사이트-및-오프사이트-캠페인-측정">측정 설정 페이지에서 현장 또는 비현장 측정 캠페인을 구성하세요</Anchor>.

1. **측정 설정**에서 **실행하기**를 클릭하십시오.  
   **실행하기**가 비활성화되어 있으면, 측정 작업이 완료되지 않습니다. 측정을 실행하기 위해 필요한 모든 설정 작업을 완료하십시오.
2. **실행 준비** 대화 상자에서 **히스토리 대시보드**를 선택하십시오.
3. 대시보드의 이름을 바꾸거나 기본 이름을 유지하십시오.
4. **측정 날짜 범위**을 선택하십시오(데이터 소스에 존재하는 날짜만 선택할 수 있습니다):
   * **시작 날짜**을 설정하십시오.
   * **종료 날짜**을 설정하십시오.
5. **시작**을 클릭하여 역사적 측정을 시작하십시오. 협업 측정 페이지로 리디렉션됩니다.
6. 협업 측정 페이지에서 자동 검증 검사가 성공적으로 완료된 후 **실행하기**를 클릭하십시오.

<div id="manage-measurements" />

## 측정 관리

측정을 설정하고 실행한 후, 협업 측정 페이지의 측정 패널에서 이를 관리하십시오. 실시간 측정을 일시 중지하거나 재시작하고, 날짜를 조정하며, 역사적 측정을 다시 실행하거나, 측정을 복제하여 새로운 실행을 생성할 수 있습니다.

<div id="the-collaboration-measurement-page" />

### 협업 측정 페이지

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

<div id="pause-or-restart-live-measurement" />

<Accordion title="실시간 측정을 일시 중지하거나 재시작하십시오.">

<div id="legend" />

#### 범례

* **A** - 측정 패널
* **B** - 선택된 측정
* **C** - 공유 전환
* **D** - 옵션 메뉴.

1. 협업 측정 페이지를 엽니다.
2. 측정 패널([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지))에서 **실시간 대시보드**을 선택하십시오.
3. 옵션 메뉴([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지))를 열고 **측정 설정**을 클릭하십시오.
4. **측정 설정** 페이지에서 다음 중 하나를 수행하십시오:
   * 실시간 귀속을 **일시 중지**하려면 **측정 활성화**를 끄고, **측정 일시 중지?** 대화 상자에서 확인하십시오.
   * 실시간 귀속을 **재시작**하려면 **측정 활성화**를 켭니다.

</Accordion>

<div id="change-measurement-start-and-end-dates" />

<Accordion title="측정 시작 및 종료 날짜 변경">

다음 항목을 변경할 수 있습니다:

* 실시간 측정의 **시작 날짜**, 또는
* 역사적 측정의 **시작 및 종료 날짜**.

측정 시작 및 종료 날짜를 변경하려면 다음 단계를 따르십시오:

1. 협업 측정 페이지를 엽니다.
2. 측정 패널에서 측정을 선택하십시오 ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지)).
3. 옵션 메뉴([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지))를 열고 **측정 설정**을 클릭하십시오.
4. **측정 설정** 페이지에서 펜 아이콘을 클릭하십시오.
5. 시작일 또는 종료일을 클릭하십시오.
6. 날짜 선택기에서 새 날짜를 선택하십시오.

</Accordion>

<div id="rerun-a-historical-measurement" />

<Accordion title="과거 측정을 다시 실행하십시오.">

과거 측정을 다시 실행하면 최신 데이터를 사용하여 귀속이 재계산됩니다. 현재 결과는 새 결과로 대체됩니다.

1. 협업 측정 페이지를 엽니다.
2. 측정 패널에서 측정을 선택하십시오 ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지)).
3. 옵션 메뉴를 열고 ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지)) **다시 실행**를 클릭하십시오.
4. 프롬프트 메시지에서 **다시 실행**을 클릭하십시오.
5. 협업 측정 페이지에서 자동 검증 검사가 성공적으로 완료된 후 **실행하기**를 클릭하십시오.

</Accordion>

<div id="duplicate-a-live-or-historical-measurement" />

<Accordion title="실시간 또는 과거 측정을 복제하십시오.">

복제하면 기존 설정을 기반으로 새 측정이 생성됩니다. 설정을 업데이트하고 새 측정으로 실행할 수 있습니다.

1. 협업 측정 페이지를 엽니다.
2. 측정 패널에서 측정을 선택하십시오 ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지)).
3. 옵션 메뉴를 열고 ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지)) **복제**를 클릭하십시오.
4. 복제된 **측정 설정** 페이지에서 측정을 필요에 맞게 사용자 정의하십시오.

</Accordion>

<div id="share-a-dashboard" />

<Accordion title="대시보드를 공유하십시오.">

**공유** 토글을 켜서 협업자와 대시보드를 공유할 수 있습니다. **공유**가 켜져 있을 때, 대시보드(및 그 측정 결과)는 협업의 다른 사용자에게 제공됩니다.

**공유**가 켜져 있을 때 협업자가 할 수 있는 일은 그들이 대시보드에 **배정된** 여부에 따라 다릅니다.

* **배정된 사용자:**
  * 대시보드를 열고 **대시보드 보기**.
  * **측정 설정**을 열고 **그들에게 할당된 작업만 편집하세요.**

* **할당된 사용자들은 할 수 없습니다:**
  * **공유**를 켜거나 끄세요 (공유 또는 비공유)
  * **측정을 다시 실행**하세요

* **할당되지 않은 사용자들**은 더 제한된 접근 권한을 가지며, 대시보드가 공유되더라도 (예를 들어, 결과 요약을 보지 못하고 다시 실행하거나 공유할 수 없습니다).

대시보드를 공유하려면:

1. 협업 측정 페이지를 열고 측정 패널([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지))에서 공유하고 싶은 **대시보드**을 선택하세요.
2. **공유**([C](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#협업-측정-페이지))를 켭니다. 대시보드는 귀하의 협업 측정 페이지에서 이용할 수 있습니다.
3. **공유**를 끄면 공유가 중지됩니다. 공유가 꺼지면, 오직 귀하(및 적절한 권한을 가진 사용자)만 대시보드에 접근할 수 있습니다.

</Accordion>

<div data-zendesk-anchors="about-the-measurement-run-modes=%EC%B8%A1%EC%A0%95-%EC%8B%A4%ED%96%89-%EB%AA%A8%EB%93%9C%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KJW81RSZPK2Y1PSAF9FSMXB6=%EC%B8%A1%EC%A0%95-%EC%8B%A4%ED%96%89-%EB%AA%A8%EB%93%9C%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC live-vs-historical-measurements=%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%B8%A1%EC%A0%95-%EB%8C%80-%EC%97%AD%EC%82%AC%EC%A0%81-%EC%B8%A1%EC%A0%95 h_01KJW81RSZBG5ZC8HE9WFXE34D=%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%B8%A1%EC%A0%95-%EB%8C%80-%EC%97%AD%EC%82%AC%EC%A0%81-%EC%B8%A1%EC%A0%95 choose-the-measurement-you-need=%ED%95%84%EC%9A%94%ED%95%9C-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 h_01KJW81RSZQG21Z0MRHWPMD69F=%ED%95%84%EC%9A%94%ED%95%9C-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 run-a-live-measurement=%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%8B%A4%ED%96%89%ED%95%98%EC%84%B8%EC%9A%94 h_01KJW81RT0Q1RWEHZP66B5141M=%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%8B%A4%ED%96%89%ED%95%98%EC%84%B8%EC%9A%94 h_01KJW81RT0N37ARE5570X7MYJF=%EC%B0%B8%EA%B3%A0 run-a-historical-measurement=%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%8B%A4%ED%96%89%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01KJW81RT0QECMGBTRFSETA5A8=%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%8B%A4%ED%96%89%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 manage-measurements=%EC%B8%A1%EC%A0%95-%EA%B4%80%EB%A6%AC h_01KJW81RT046RE5FVHPGEDMCC5=%EC%B8%A1%EC%A0%95-%EA%B4%80%EB%A6%AC the-collaboration-measurement-page=%ED%98%91%EC%97%85-%EC%B8%A1%EC%A0%95-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01KJWNTR04PRG54W0GZVGQY72X=%ED%98%91%EC%97%85-%EC%B8%A1%EC%A0%95-%ED%8E%98%EC%9D%B4%EC%A7%80 legend=%EB%B2%94%EB%A1%80 h_01KJWNF8NAJ9NT5T8NAVTCMZVA=%EB%B2%94%EB%A1%80 h_01KJW81RT0A148W49X0BR0V9YM=pause-or-restart-live-measurement h_01KJW81RT0GYDCZCXXV2G5EJD7=change-measurement-start-and-end-dates h_01KJW81RT054CCYMTKFN7TS1XV=rerun-a-historical-measurement h_01KJW81RT0RKQJRCTRVP36YBKV=duplicate-a-live-or-historical-measurement h_01KJW81RT0C3R95JQVPGSZ043B=share-a-dashboard" />
