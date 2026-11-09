---
title: 데이터 협업 플랫폼(DCP) - 오디언스 구축 및 활성화
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-10-14T10:29:52Z'
  id: 24522739719057
  locale: ko
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ko/articles/24522739719057
---
> **한눈에 보기:** 오디언스 빌더 도구를 사용하여 오디언스를 생성하고 활성화합니다. 필요한 권한에 따라, 오디언스는 양 당사자 모두의 결합된 데이터셋 또는 한 당사자만의 결합된 데이터셋을 기반으로 할 수 있습니다.

> 👍 **DCP 소개**
>
> 데이터 협업 플랫폼(DCP)은 오디언스 생성 및 활성화를 포함하여 데이터 협업의 중앙 지점 역할을 합니다. DCP는 협업 및 오디언스 관리 프로세스를 위한 데이터 프라이버시와 보안을 보장하기 위해 데이터 클린룸(DCR)의 고급 기술을 사용합니다.

<div id="about-dcp-audiences" />

## 개요

광범위한 데이터셋에서 오디언스를 구축하는 과정에는 데이터 세트를 결합하여 풍부한 데이터를 생성하는 것을 포함합니다. 이러한 데이터를 활용하여 고객에게 정확하게 도달할 수 있습니다. 오디언스는 양 당사자 모두의 결합된 데이터셋을 사용하거나 한 당사자가 제공하는 데이터셋을 사용하여 생성될 수 있습니다. 두 가지 경우 모두, 데이터를 제공하는 공동 작업자가 동의한 조건에 따라 권한과 액세스 권한을 부여합니다. 오디언스를 생성한 후, 미디어 파트너로 보내서 활성화하거나 클라우드 서비스로 보낼 수 있습니다.

## 잠재 고객 빌더 도구

잠재 고객을 구축하기 위해 다음 도구를 사용할 수 있습니다.

* **시각적 오디언스 빌더:** 시각적 오디언스 빌더는 비 기술 사용자가 SQL 기술을 필요로 하지 않고도 오디언스 세그먼트를 생성할 수 있는 사용자 친화적인 도구입니다. 그래픽 인터페이스를 사용하여 고급 오디언스 세분화를 할 수 있습니다.
* **SQL 오디언스 빌더:** 제한 없이 데이터를 쿼리할 수 있는 SQL 쿼리입니다. SQL 전문 지식 필요.

<div id="key-features" />

<div id="build-an-audience" />

#### 주요 기능

| 시각적 오디언스 빌더 | SQL 오디언스 빌더 |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>각 공동 작업자의 하나의 소스 또는 하나의 공동 작업자의 여러 소스를 사용하는 것을 지원합니다. | 양쪽 업체 모두의 여러 소스 지원 |
| <span id="supports-using-overlapping-data-only"></span>각 공동 작업자에 대한 하나의 소스에 대해서, 중복 데이터만 사용하도록 지원합니다. | 모든 데이터 쿼리 지원 |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>선택한 속성 범위 내의 값을 검색하도록 지원합니다. | 어트리뷰트 범위를 넘어 쿼리 값 지원 |

## 잠재 고객 구축

오디언스를 구축하는 단계는 오디언스 빌더 도구에 따라 달라집니다. 따라서 먼저 사용할 [오디언스 빌더 도구](#잠재-고객-빌더-도구)를 결정합니다.

* [시각적 오디언스 빌더](/docs/data-collaboration-platform-dcp-build-and-activate-audiences#visual-audience-builder)
* [SQL 오디언스 빌더](#sql-audience-builder) (SQL 전문 지식 필요)

<div id="visual-audience-builder" />

<Accordion title="시각적 오디언스 빌더">

**아래 단계에 따라 시각적 오디언스 빌더를 사용하여 오디언스를 구축하십시오.**

<div id="note" />

> 📘 **참고**
>
> 오디언스를 생성할 수 있는 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">오디언스 구축</Anchor> 권한이 있는지 확인하십시오.

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.

   <Image align="center" alt="from Collaborate.png" src="https://support.appsflyer.com/hc/article_attachments/32455804422545" width="266px" />
2. **협업** 탭에서 해당 협업을 클릭합니다.

   <Image align="center" alt="연관된 collaboration.png 을 클릭합니다." src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. 공동 작업에서 **새로운 오디언스** > **시각적 오디언스 작성기**를 클릭합니다.  
   **참고: 오디언스를 작성하기 전에** 하나 이상의 소스가 연결되어 있어야 합니다.

   <Image align="center" alt="새로운 Aud 비주얼 오디언스 builder.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. 아래의 **잠재 고객 작성기** 과정을 진행하십시오.

<div id="note-1" />

<div id="step-1-details-and-sources" />

#### 1단계: 세부 정보 및 소스

오디언스는 단일 공동 작업자의 데이터를 사용하거나 각 공동 작업자의 하나의 소스를 병합하여 결합된 데이터 소스를 활성화하여 생성될 수 있습니다.

![New aud.png](https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png)   

1. 오디언스 이름 잠재 고객 공동 작업 이름을 지정합니다.
2. 소스 선택 드롭다운 목록에서 소스를 선택합니다.
   * 양면 공동 작업의 경우: 소스를 자체 또는 공동 작업자의 소스를 선택합니다.
   * 양면 협업의 경우 자신의 소스와 공동 작업자의 소스 중 하나를 선택합니다.  
     **참고:** 두 소스가 교차하는 사용자를 공유하는 경우 오른쪽 창에는 소스 교차 요약이 표시되어 두 소스 모두에게 공통된 예상 사용자 수를 제공합니다.
3. **데이터 결합 방법:** 다음에서 오디언스를 생성할 데이터를 선택하십시오.
   * **사용자 상호 연결** - 두 소스(사용자 및 공동 작업자)에 표시되는 사용자만 포함합니다.
   * **내 소스의 사용자만** - 소스에 고유한 사용자만 포함합니다. 공동 작업자의 소스에 표시되는 모든 사용자를 제외합니다.
   * **동료 소스의 사용자만** - 공동 작업자의 연결 소스에 고유한 사용자만 포함합니다. 소스에 표시되는 모든 사용자를 제외합니다.  

     **참고:** 소스 권한에 "**오디언스 구축**" > "**모든 데이터 사용 가능** - **유니버설 데이터셋**"이 활성화된 경우에만 이 세 가지 옵션을 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#공유-권한">소스 권한에 대해 더 알아보기</Anchor>  

     <Image alt="arrow.png 으로 활성화된 모든 데이터 허가를 사용할 수" src="https://support.appsflyer.com/hc/article_attachments/34588579107345" width="87.42%" /> 있습니다.
4. **다음**을 클릭합니다.

<div id="step-2-define-the-audience" />

#### 2단계: 오디언스 정의

데이터 소스가 선택된 후에는 오디언스에 포함할 속성 및 값을 선택하는 작업이 포함됩니다.

1. 소스의 속성 목록을 보려면 **열 선택** 을 클릭합니다.
2. 어트리뷰트, 연산자 및 어트리뷰트 값을 선택합니다.
   * 연산자로 **숫자 및 날짜 속성**을 필터링할 수 있습니다.  
     같음, 같지 않음, 더 크기, 더 낮음, 더 크기 또는 같음,  
     최근 "X" 일 사이의 값보다 작거나 같음(현재 일 포함 가능)
   * 연산자로 필터링할 수 있는 **텍스트 속성**:  
     같음 또는 비슷함

     <div id="working-with-transactional-data-sources" />

     <div id="note-3" />

     <div id="summary-right-side-preview-pane" />

     <div id="note-2" />

     > 📘 **참고**
     >
     > * 어트리뷰트를 선택하지 않으면 기본적으로 모든 어트리뷰트가 포함됩니다.
     > * 어트리뷰트 값을 선택하면 오디언스 크기가 조정됩니다.

3. [선택 사항] 다른 속성을 추가하고 값을 선택하려면 **+ 조건**을 클릭합니다.  
   필요에 따라 반복하십시오.
4. **다음**을 클릭합니다.
5. 다음 단계에서 계속하세요. 오디언스를 활성화하기 위해 [오디언스를 보내기](#오디언스-활성화를-위해-보내기) 합니다.

<Image align="center" alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="SQL 오디언스 빌더">

아래 단계에 따라 SQL 오디언스 빌더를 사용하여 오디언스를 구축하십시오.

<div id="note-4" />

> 📘 **참고**
>
> 오디언스를 생성할 수 있는 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">오디언스 구축</Anchor> 권한이 있는지 확인하십시오.

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.

   <Image align="center" alt="from Collaborate.png" src="https://support.appsflyer.com/hc/article_attachments/32455804422545" width="266px" />
2. **협업** 탭에서 해당 협업을 클릭합니다.

   <Image align="center" alt="연관된 collaboration.png 을 클릭합니다." src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. 공동 작업에서 **잠재 고객 새로 만들기** > **SQL 잠재 고객 작성기** 를 클릭합니다.

   <Image align="center" alt="새로운 Aud SQL 오디언스 builder.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. 다음과 같은 **오디언스 작성기** 과정을 진행하십시오.

<div id="set-details" />

#### 세부 정보 설정

오디언스 이름을 지정하고 **다음**을 클릭합니다.

<div id="note-5" />

<div id="build-query" />

#### 쿼리 생성

1. 편집기를 클릭하여 [SQL 빌더를](#sql-audience-builder) 엽니다.
2. SQL 쿼리를 작성하여 오디언스를 구축합니다. 조합 또는 양측 소스를 사용할 수 있습니다.
3. **테스트**를 클릭하고 쿼리 문서 아래에 표시된 쿼리 결과(잠재 고객 샘플)를 검토합니다.
4. 다음 단계의 **오디언스 작성기** 워크스루를 진행하려면 **계속**을 클릭한 다음 **다음**을 클릭하거나 나중에 다시 시작하고 **초안으로 저장**합니다.
5. 계속하여 [잠재 고객 전송](#오디언스-활성화를-위해-보내기).

<div id="nonaggregated-transactional-query" />

<div id="transactional-source-joined-directly-to-another-transactional-source" />

<div id="aggregated-transactional-output-in-downstream-joins" />

<div id="transactional-source-joined-to-a-profileuserlevel-source" />

<div id="single-transactional-source-with-aggregation" />

<div id="transactional-data-in-sql-queries" />

<div id="the-sql-audience-builder" />

#### SQL 오디언스 빌더

SQL 빌더를 사용하여 데이터를 쿼리하고 오디언스를 생성합니다. 다음 표는 빌더의 섹션을 간략하게 표시합니다.

| 섹션 | 설명 |
| --- | --- |
| <span id="left-pane"></span>왼쪽 창: | 오디언스를 생성하는 데 사용할 수 있는 모든 소스를 표시합니다. 여기에는 소스와 공유 소스가 포함될 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**잠재 고객 만들기**</Anchor> 권한이 있는 소스만 볼 수 있습니다.<br /><br />소스를 선택하면 해당 열을 표시하도록 확장합니다. |
| <span id="topmiddle-section-text-editor"></span>상위 중간 섹션 (쿼리 편집기) | SQL 문서를 작성하는 쿼리 편집기. |
| <span id="bottommiddle-section-context-panel"></span>하단 중간 섹션(상관 패널) | 이 섹션에서는 왼쪽 창에서 선택한 객체를 기반으로 세부 정보를 동적으로 보여줍니다.<ul><li>**소스를 선택할 때:** 열 이름("필드 이름")과 해당 유형("유형")을 표시합니다.</li><li>**열을 선택하는 경우:** 각 값에 대한 열 값("고유 값")과 행 수("계수")를 표시합니다.</li><li>**다음과 같은 쿼리 실행:** 쿼리 결과 샘플을 표시합니다.<br />**참고:** 개인 정보 보호를 위해 결과 표에는 이메일이나 ID와 같은 해시된 값이 표시되지 않습니다. 이러한 값은 "Restricted(제한)"로 표시됩니다.</li></ul> |
| <span id="right-pane"></span>오른쪽 창: | 이 섹션에서는 선택한 객체에 기반하여 세부 정보를 동적으로 보여줍니다.<ul><li>**소스를 선택할 때:** 해당 소스에 부여된 권한을 표시합니다.</li><li>**SQL 쿼리를 작성하는 동안:**<ul><li>페이지 우측 상단에 쿼리 유효성 상태를 표시합니다. 여기에는 다음 상태 중 하나가 포함될 수 있습니다.<ul><li>**실행 준비:** 문제를 찾을 수 없습니다. 쿼리를 테스트하고 다음 단계로 넘어가실 수 있습니다.</li><li>**연동 오류:** 구문 오류가 확인 안내와 함께 탐지되었습니다.</li><li>**권한 오류: 소스에 어떤 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">액세스 권한이 제공되는지</Anchor> 설명하는 도구 설명과 함께 필요한 권한이 부족한 것을** 표시합니다.</li></ul></li><li>페이지 오른쪽 위에 **테스트** 버튼이 표시됩니다. 쿼리를 작성한 후에는 테스트를 완료하여 의도한 오디언스의 정확성을 확인해야 합니다.<br />**테스트**를 클릭하여 쿼리를 테스트하고 결과를 검사합니다.</li></ul></li></ul> |

</Accordion>

<div id="send-an-audience-for-activation" />

## 오디언스 활성화를 위해 보내기

오디언스 정의를 완료하면 (필수한 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#공유-권한">권한을 고려하여</Anchor>) 전달할 오디언스 위치를 선택합니다. 즉, 오디언스를 구성하는 사용자 ID 목록이 끊임없이 새로고침되고 매일 선택한 목적지로 전송됩니다. 두가지 목적지를 사용할 수 있습니다. 다음을 할 수 있습니다.

* 오디언스를 미디어 파트너와 [**연결시키세요**](#잠재고객을-미디어-파트너에-연결) - 미디어 파트너 플랫폼에는 Meta Ads, Google Ads 등이 있습니다. 유료 캠페인, 리마케팅 또는 유사 확장을 실행할 때 잠재 고객과 미디어 파트너를 연결합니다.
* [**오디언스를 클라우드 서비스로 내보내기**](#오디언스를-클라우드-서비스로-내보내기) - 클라우드 스토리지는 앱스플라이어 데이터 락커를 통해 관리됩니다. BI 모델, CDP 또는 내부 강화 파이프라인에서 파일이 필요한 경우 잠재 고객을 클라우드 서비스에 연결합니다.

<div id="connect-an-audience-to-media-partners" />

<div id="note-6" />

> 📘 **참고**
>
> * 소스 데이터가 업데이트될 때마다 오디언스는 자동으로 선택한 대상으로 전달됩니다.
> * 활성화를 위해 전송되는 데이터는 사용자 ID 목록입니다.

#### 잠재고객을 미디어 파트너에 연결

Meta ads 및 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google Ads</Anchor>와 같은 선호하는 미디어 파트너 플랫폼에서 활성화를 위해 오디언스를 직접 전송합니다. 시스템은 사용자 ID의 CSV를 전달하며, 파트너가 필요한 경우 자동으로 해시합니다.

<div id="export-to-cloud-storage" />

<div id="note-8" />

<div id="note-7" />

> 📘 **참고**
>
> 오디언스를 활성화할 권한이 없는 경우, 오디언스는 공동 작업자에게 전송되어 활성화됩니다.

**잠재 고객을 미디어 파트너에 연결하는 방법:**

1. 오디언스 생성기에서 **오디언스와 미디어 파트너 연결**을 설정합니다.  
     
   <Image align="center" alt="잠재고객을 미디어 파트너에 연결" src="https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png" />
2. **+ 파트너 연결**을 클릭하십시오.
3. 파트너 연결이 설정되지 않은 경우 새 파트너 연결을 생성합니다.
   1. **Add Connection (연결 추가)** 를 클릭합니다.
   2. 해당 미디어 파트너(메타 광고, 구글 애즈, DV360 또는 틱톡)를 선택합니다.
   3. 연결에 대한 이름을 입력합니다.
   4. **[파트너 이름]로 로그인]** 를 클릭합니다. 파트너 로그인 페이지로 이동합니다. 잠재 고객을 수신할 계정을 선택합니다. 그런 다음 대화상자로 리디렉션됩니다.
   5. **계정 ID 선택**을 클릭하고 관련 계정 ID를 선택합니다.
   6. **저장**을 클릭하세요.
4. **저장 및 전송** 을 클릭합니다.

<Image align="center" alt="미디어 파트너 connection.png 을 선택합니다." src="https://support.appsflyer.com/hc/article_attachments/35682279443857" width="610px" />

#### 오디언스를 클라우드 서비스로 내보내기

잠재 고객을 클라우드 서비스로 보냅니다. 오디언스는 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">앱스플라이어 데이터 락커</Anchor> 연결을 사용하여 선택한 클라우드 서비스로 내보냅니다. 사용자 ID의 CSV가 선택한 버킷에 기록됩니다.

* **참고:** AppsFlyer 데이터 락커를 사용하여 DCR 오디언스를 수신하려면 데이터 락커의 프리미엄 구독이 필요하지 않습니다. 데이터 락커를 통해 다른 앱스플라이어 리포트를 수신하려면 CSM에 문의하거나 hello@appsflyer.com로 이메일을 보내주십시오.

**잠재 고객을 클라우드 서비스로 보내려면:**

1. 오디언스 생성기에서 **오디언스 클라우드 내보내기**를 설정합니다.  
     
   오디언스를 클라우드로 내보내기
2. 오디언스를 전송할 수 있는 목록에서 기존 클라우드 연결을 선택하려면 **연결 선택**을 클릭하거나 데이터 락커에서 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">새로운 연결 만들기</Anchor>를 위해 **+ 새 연결** 을 클릭합니다. 사용 방법은 여기를 참조하세요.
3. **저장하고 닫기를 클릭합니다**. 오디언스가 선택된 클라우드 서비스로 전송됩니다. 이 프로세스는 최대 15분 정도 소요될 수 있습니다.

<div id="view-audience-statuses" />

<div id="access-audience-management" />

<div id="manage-audiences" />

## 오디언스 관리

관련 공동 작업 대시보드의 **오디언스** 섹션에서 연관된 오디언스를 보고 관리할 수 있습니다.

<Image align="center" alt="Audiences section.png" src="https://support.appsflyer.com/hc/article_attachments/32456187667345" width="2836px" />

**이 페이지에서 할 수 있는 작업:**

* **잠재 고객 검색:** 소스 이름 또는 잠재 고객 이름으로 검색.
* **필터 오디언스:** 잠재 고객 또는 공유 고객을 기준으로 필터링하도록 선택합니다.
* **잠재 고객 세부 정보 보기:** 공동 작업자의 이름, 중복 사용자에 대한 통계, [오디언스 상태](#잠재-고객-상태) 및 활성화 위치와 같은 세부 사항을 참조하십시오.
* **더 많은 액션:** 오디언스 카드의 3도트 메뉴 아이콘을 클릭하면 사용 가능한 추가 작업이 열립니다.
  * [편집](#오디언스-활성화-목적지를-편집합니다): 오디언스 활성화 목적지를 수정합니다.
  * **잠재 고객 기록 보기:** 연결 및 활성화 상태와 같은 세부 사항이 포함된 오디언스 활성화의 모든 인스턴스를 확인합니다.
  * CSV 내려받기 오디언스를 CSV 파일로 다운로드합니다.
  * **일시 중지:** 데이터 소스가 수정되면 오디언스가 업데이트되고 다시 활성화되지 않도록 합니다.
  * [삭제](#잠재-고객-삭제): 잠재 고객을 삭제합니다.

<div id="edit-the-audience-activation-destination" />

### 오디언스 활성화 목적지를 편집합니다.

오디언스를 작성할 때 초안으로 저장한 다음 다시 오디언스로 돌아와 활성화 대상(권한에 따라 다름)을 편집할 수 있습니다.

**잠재 고객 활성화 목적지를 편집하려면:**

1. **협업** 탭에서 해당 협업을 클릭합니다.
2. **오디언스** 섹션을 클릭하고 관련 오디언스를 찾으십시오.
3. 오디언스 > **편집** 화면에 마우스 오버하면 나타나는 3포인트 메뉴 아이콘을 클릭합니다.
4. 연결 및 내보내기(오디언스 페이지의 하단)에서 해당 토글을 설정합니다.
   * [미디어 파트너에 연결하기](#잠재고객을-미디어-파트너에-연결)
   * [클라우드 서비스 내보내기](#오디언스를-클라우드-서비스로-내보내기)

<div id="delete-an-audience" />

### 잠재 고객 삭제

계정에서 생성된 오디언스를 삭제할 수 있습니다. 이렇게 하면 계정에서 영구적으로 삭제됩니다.

**잠재 고객 삭제 방법:**

1. **협업** 탭에서 해당 협업을 클릭합니다.
2. **오디언스** 섹션을 클릭하고 관련 오디언스를 찾으십시오.
3. 오디언스 > **삭제** 메뉴 화면에 마우스 오버하면 나타나는 3점 메뉴 아이콘을 클릭합니다.
4. 삭제를 확인합니다.

### 잠재 고객 상태

공동 작업과 연결된 오디언스의 상태를 볼 수 있습니다.

<Image align="center" alt="잠재 고객 상태 - doctored with arrow.png" src="https://support.appsflyer.com/hc/article_attachments/36573611849361" />

오디언스는 다양한 상태를 가질 수 있습니다.

* 활성화됨 오디언스가 대상 플랫폼으로 성공적으로 전송되었으며 캠페인에서 사용할 수 있습니다.
* 초안 오디언스는 초안(연결, 내보내기 또는 전달되지 않음)으로 저장되었습니다.
* **유효하지 않음**: 오디언스에 사용되는 소스 또는 데이터 뷰가 만료되었거나 삭제되었거나 공동 작업에서 제거되었음을 나타냅니다.
* **연결 안됨:** 오디언스는 공동 작업자가 활성화를 위해 수신했지만 아직 연결되지 않았습니다.
* **보류 중:** 오디언스는 활성화를 위해 공동 작업자에게 전송되었으며, 활성화 대기 중입니다.
* 일시 중지됨 오디언스는 수동으로 일시 중지되었으며 새 데이터가 가능해지면 전송되지 않습니다.
* 정지됨 공동 작업 및 관련 오디언스는 일시 중지되었습니다.

또한 오디언스의 **업로드 히스토리** 상태도 볼 수 있습니다.

업로드 기록을 **보려면:**

특정 오디언스 옆의 드롭다운을 클릭하고 **히스토리 보기**를 선택합니다.

<Image align="center" alt="History view doctored .png" src="https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png" />

**업로드 기록 상태에는 다음이 포함됩니다.**

* 성공! 오디언스가 모든 연결로 성공적으로 전송되었습니다.
* 부분적인 실패 오디언스를 하나 이상의 연결으로 전송할 수 없습니다.
* 실패 오디언스 처리에 문제가 발생했습니다(예: 데이터 불일치, 플랫폼 제한 또는 플랫폼 오류).

<div data-zendesk-anchors="h_01HZHB2GVA3W5EXG8MM6Y9QZR2=dcp-%EC%86%8C%EA%B0%9C overview=%EA%B0%9C%EC%9A%94 h_01HWG1P909NHBXC5VF23BDVVPH=%EA%B0%9C%EC%9A%94 audience-builder-tools=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EB%B9%8C%EB%8D%94-%EB%8F%84%EA%B5%AC 01HWG510K97GCB137ZJZQE21DH=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EB%B9%8C%EB%8D%94-%EB%8F%84%EA%B5%AC key-features=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 h_01HWG5B2MEJH7M8E9BWA3FQFQ2=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 build-and-activate-your-audiences=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EA%B5%AC%EC%B6%95 h_01HWETSZWYZ8SFV9BH2N7X5BAE=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EA%B5%AC%EC%B6%95 h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=%EC%B0%B8%EA%B3%A0 step-1-join-sources=1%EB%8B%A8%EA%B3%84-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4-%EB%B0%8F-%EC%86%8C%EC%8A%A4 h_01HWFRRGP99KKGBSQ6QB10RD26=1%EB%8B%A8%EA%B3%84-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4-%EB%B0%8F-%EC%86%8C%EC%8A%A4 step-2-build-audiences=2%EB%8B%A8%EA%B3%84-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A0%95%EC%9D%98 h_01HWFRRPFTCFGEHY1AW8G4VMY4=2%EB%8B%A8%EA%B3%84-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A0%95%EC%9D%98 h_01JSEPSRF3FFJJ4S20GJJPJVWF=%EC%B0%B8%EA%B3%A0-1 h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=%EC%B0%B8%EA%B3%A0-2 step-1-set-details=%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4-%EC%84%A4%EC%A0%95 h_01HWG9VX0QB3GFZDARAT5QKHV0=%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4-%EC%84%A4%EC%A0%95 step-2-build-query=%EC%BF%BC%EB%A6%AC-%EC%83%9D%EC%84%B1 h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=%EC%BF%BC%EB%A6%AC-%EC%83%9D%EC%84%B1 the-sql-audience-builder=sql-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B9%8C%EB%8D%94 h_01HZM9P2GNCPGJDEA51HCV1Y99=sql-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B9%8C%EB%8D%94 send-audience-for-activation=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%9C%EC%84%B1%ED%99%94%EB%A5%BC-%EC%9C%84%ED%95%B4-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HZMCHKMVXRWK7RXZ7NN65JQX=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%9C%EC%84%B1%ED%99%94%EB%A5%BC-%EC%9C%84%ED%95%B4-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HZMCRJBBXFEV6JXEHGFXZDZW=%EC%B0%B8%EA%B3%A0-3 connect-audience-to-media-partners=%EC%9E%A0%EC%9E%AC%EA%B3%A0%EA%B0%9D%EC%9D%84-%EB%AF%B8%EB%94%94%EC%96%B4-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%97%90-%EC%97%B0%EA%B2%B0 h_01J8HNKQ08EVKXA75C9MZB7AW9=%EC%9E%A0%EC%9E%AC%EA%B3%A0%EA%B0%9D%EC%9D%84-%EB%AF%B8%EB%94%94%EC%96%B4-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%97%90-%EC%97%B0%EA%B2%B0 h_01HZMDXEEABQRQE8XMZNE86SRF=%EC%B0%B8%EA%B3%A0-4 export-audience-to-cloud-services=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EB%A5%BC-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4%EB%A1%9C-%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HZPCCXTT91FQSTSEXN8GS2Y5=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EB%A5%BC-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4%EB%A1%9C-%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0 manage-audiences=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC h_01HZPWTG23YQ5Y1GAPXT65DK07=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC edit-the-audience-activation-destination=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%9C%EC%84%B1%ED%99%94-%EB%AA%A9%EC%A0%81%EC%A7%80%EB%A5%BC-%ED%8E%B8%EC%A7%91%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HZPXJEDPB6EB4HK2BW8RDDJM=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%ED%99%9C%EC%84%B1%ED%99%94-%EB%AA%A9%EC%A0%81%EC%A7%80%EB%A5%BC-%ED%8E%B8%EC%A7%91%ED%95%A9%EB%8B%88%EB%8B%A4 delete-an-audience=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EC%82%AD%EC%A0%9C h_01HZPXJMANK6PBQCHAQ4XQSTF4=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EC%82%AD%EC%A0%9C audience-statuses=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EC%83%81%ED%83%9C h_01HZPXAKV9YTAN2MNZCD22S5AX=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EC%83%81%ED%83%9C" />
