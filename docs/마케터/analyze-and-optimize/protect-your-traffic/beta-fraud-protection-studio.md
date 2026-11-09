---
title: '[Beta] 프로드 방지 스튜디오'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-10-14T10:33:24Z'
  id: 30754984040977
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/30754984040977
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

<Image align="center" alt="beta_feature.png" src="https://files.readme.io/d57432ddeb4d168760f9acd97f4287473658a8528edc1114ecee8ee2f8e9c9b2-16484830033425.png" width="805px" />

> **한눈에 보기:** 프로드 방지 스튜디오(FPS)는 일반적인 방법보다 프로드 탐지 방법을 더 세밀하게 조정할 수 있습니다. 사용자가 프로드 감지 데이터를 차단하고 프로드로 보고할지, 또는 태그만 지정할지를 선택할 수 있어 맞춤형 프로드 관리가 가능합니다.

<div id="about-fraud-protection-studio" />

## 프로드 방지 스튜디오 소개

프로드 방지 스튜디오에서는 태그된 탐지 상태를 새롭게 도입했습니다.

태그된 감지 상태를 통해 광고주는 자동으로 조치를 취하지 않고도 프로드를 감지할 수 있으며, 다음과 같은 장점이 있습니다.

* 평가: 탐지 업데이트를 적용하기 전에, 적용 후의 영향을 미리 평가합니다.
* 대조군: 비즈니스 모델과 요구 사항에 맞게 프로드 탐지를 조정합니다.
* 투명성: 태그된 데이터를 통해 추가적인 프로드 방지 단계에 대한 인사이트를 얻을 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> 오직 관리자, 마케팅 리드, 팀 관리자 및 보안 <Anchor target="_blank" href="/marketers/ko/docs/user-management#역할-관리">권한 역할</Anchor>만이 프로드 방지 스튜디오에 접근할 수 있습니다.

<div id="how-the-fraud-protection-studio-works" />

## 프로드 방지 스튜디오의 작동 원리

<div id="key-concepts" />

<Accordion title="핵심 개념">

<div id="fps-modes" />

#### FPS 모드

FPS에는 **구현됨** 및 **태그됨**이라는 두 가지 모드가 있습니다. 광고주는 자신의 목표에 따라 이러한 모드를 전환할 수 있어, 프로드 감지 방식이 필요에 맞게 조정되도록 할 수 있습니다.

**현재 탐지 메커니즘:** 설치는 다음 중 하나로 간주됩니다.

* **유효한** 어트리뷰션
* **탐지됨**
  * 실시간으로 **차단됨**
  * 포스트 어트리뷰션 프로드로 **리포트됨**

<Image align="center" alt="Image description" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />
**FPS 메커니즘:** 설치는 다음 중 하나로 간주됩니다.

* **유효한** 어트리뷰션
* **탐지됨** 및
  * **태그됨** 그러나 **유효한** 어트리뷰션으로 기록됨
  * **구현됨**
    * 실시간으로 **차단됨**
    * 포스트 어트리뷰션 프로드로 **리포트됨**

<Image align="center" alt="Image description" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />

<div id="note" />

> 📘 **참고**
>
> 태그 모드에서는 태그되었지만 여전히 유효한 모든 프로드 감지 항목이 고객의 설정에 따라 유효한 것으로 간주되며, 따라서 소비 플랜에 크레딧이 반환되지 않습니다.

<div id="where-is-tagged-detection-reflected" />

#### 태그된 탐지는 어디에 반영되나요?

태그된 탐지는 프로드 리포트에 반영되지 않습니다. 태그가 지정된 감지는 일반 어트리뷰션 리포트와 Protect360 대시보드에서 다음과 같이 제공됩니다.

**리포트**:

* 실시간 태그된 설치
* 포스트 어트리뷰션 태그 설치
* 실시간 태그된 인앱 이벤트
* 포스트 어트리뷰션 태그가 있는 인앱 이벤트

**Protect360 대시보드**:

<Image align="center" alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />

* 상단 페이지 구성 요소의 총 태그 수 (1)
* “감지 상태”의 시간 경과에 따른 추세 (2)
* “태그 유형”, “태그 사유”, “세부 사유”별로 식별된 프로드 (3)

</Accordion>

<div id="how-to-use-fraud-protection-studio" />

## 프로드 방지 스튜디오 사용 방법

<div id="general" />

<Accordion title="일반">

프로드 방지 스튜디오는 감지 항목을 언제 구현(implemented)할지 또는 태그(tagged)로 표시할지를 지정할 수 있는 페이지입니다. 이 플랫폼에서는 다음과 같은 사항을 제공하여 태깅 요건을 정의하는 데 도움을 줍니다.

* 감지 상태 데이터.
* 구현 모드와 태그 모드 간 전환 옵션.

시작하려면:

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 카드를 선택하세요. 현재 옵션은 다음과 같습니다:
   * [클릭 플러드](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [신규 릴리스](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="클릭 플러드 감지">

프로드 방지 스튜디오를 통해 클릭 플러드 감지를 간편하고 관리하고, 관리 방식을 사용자 맞춤화할 수 있습니다. 앱 수준(모든 파트너 대상)에서 클릭 플러드 감지에 태그를 지정할 수 있도록 하며, 태그된 클릭 플러드 감지 데이터를 전용 리포트에서 제공합니다.

클릭 플러드 카드 페이지에서는 구현된 상태와 태그된 상태 간의 [감지 상태를 확인하고 조정](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법)할 수 있으며, [현재 감지 상태](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source) 데이터를 볼 수 있습니다.

클릭 플러드 리포트 데이터 샘플 다운로드

<div id="important-2" />

<div id="important-1" />

> 🚧 **중요!**
>
> * 태그된 탐지를 선택하면 로데이터 리포트에 보고되며, 프로드 리포트에는 보고되지 않습니다.
> * 클릭 플러드에 대한 태깅은 앱 수준에서 이루어지며, 차단이나 어트리뷰션 이후 적용이 발생하지 않도록 방지합니다. 따라서 이를 태그 모드로 설정하면 논오가닉 설치뿐만 아니라 오가닉 설치에도 악용 위험에 노출될 수 있습니다.

<div id="how-to-access-click-flood" />

#### 클릭 플러드에 액세스하는 방법

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 **클릭 플러드** 카드를 선택합니다.

<div id="click-flood-page" />

### 클릭 플러드 페이지

클릭 플러드 페이지는 두 섹션으로 구분되어 있습니다.

[탐지 상태](/docs/beta-fraud-protection-studio#탐지-상태)

[현재 탐지 상태](/docs/beta-fraud-protection-studio#현재-탐지-상태)

<div id="detection-status" />

#### 탐지 상태

* [감지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법) - [감지](/docs/beta-fraud-protection-studio#fps-모드) 모드를 선택할 수 있습니다. **구현된** 감지와 **태그된** 감지 중에서 선택할 수 있습니다.
* [현재 감지 상태](/docs/beta-fraud-protection-studio#현재-탐지-상태) - 클릭 플러드 활성화가 지난 주 이전 7일 동안의 설치 및 관련 이벤트에 어떤 영향을 미쳤는지를 보여줍니다. 이 섹션은 다음과 같이 구분되어 있습니다.
  * 현재 감지 위젯
  * 클릭 플러드 탐지 분석 위젯
  * 미디어소스별 클릭 플러드 위젯

<div id="how-to-adjust-the-detection-status" />

#### **감지 상태를 조정하는 방법**

감지 상태에서는 [감지](/docs/beta-fraud-protection-studio#fps-모드)모드를 선택할 수 있습니다. **구현된** 감지와 **태그된** 감지 중에서 선택할 수 있습니다.

1. 클릭 플러드 창에서 [탐지 모드](/docs/beta-fraud-protection-studio#fps-모드)를 선택합니다.
2. 페이지 하단의 **저장** 버튼을 클릭합니다.

   <Image align="center" alt="Expandable Image" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />

<div id="current-detection-status" />

#### **현재 탐지 상태**

현재 감지 상태 섹션은 지난 주 이전 7일 동안의 추정치를 보여줍니다.

현재 탐지 상태 섹션에는 다음과 같은 내용이 표시됩니다.

* 현재 감지 위젯
* 클릭 플러드 탐지 분석 위젯
* 미디어소스별 클릭 플러드 위젯

**현재 감지 위젯**

* **전체 설치 수** - 전체 앱 설치 수
* **클릭 플러드 탐지** - 탐지된 전체 클릭 플러드 수
* **총 감지**(클릭 플러드 제외) - 클릭 플러드를 제외한 총 프로드 감지 수
* **총 감지**(클릭 플러드 포함) - 클릭 플러드를 포함한 총 프로드 수. 계산 방식: (클릭 플러드 탐지 + 총 탐지(클릭 플러드 제외) )

**클릭 플러드 탐지 분석 위젯**

오가닉 및 논오가닉설치별 클릭 플러드 탐지 데이터를 보여줍니다.

**미디어소스별 클릭 플러드 위젯**

탐지된 클릭 플러드 설치를 미디어소스별로 분석하여 표시합니다.

참고: 더 자세한 리포트를 원하시면 **내보내기** 버튼을 클릭하여, 감지 지표를 CSV 파일로 다운로드하고 오프라인에서 분석하세요.

</Accordion>

<div id="new-releases" />

<Accordion title="신규 릴리스">

신규 릴리스(New Releases) 기능을 통해 새로운 프로드 감지 업데이트를 적용하기 전에 그 영향을 평가할 수 있습니다. 기본적으로 각 새로운 프로드 감지 패키지는 태그 모드로 시작되며, 이를 통해 영향도를 평가할 수 있는 시간과 제어 권한이 제공됩니다.

신규 릴리스 리포트 데이터 샘플을 다운로드하세요.

<div id="note-1" />

> 📘 **참고**
>
> 감지 패키지는 하나 이상의 감지 업데이트를 그룹화하여 함께 배포한 것입니다.

<div id="how-this-works" />

#### 작동 방식

* 프로드 탐지 업데이트는 패키지로 그룹화됩니다.
* 프로드 탐지 패키지는 [태그 모드](/docs/beta-fraud-protection-studio#fps-모드)로 시작합니다.
* 새 패키지는 최대 14일 동안 태그 모드로 설정할 수 있습니다.
* 현재 활성 패키지를 평가하고 구현할 수 있습니다.
* 새 패키지 릴리스에 대한 알림은 알림을 통해 알려드립니다.

<div id="how-to-access-new-releases" />

#### 신규 릴리스에 액세스하는 방법

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭 다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 **신규 릴리스** 카드를 선택합니다.

<div id="new-releases-page" />

### 신규 릴리스 페이지

신규 릴리스 페이지는 두 개의 섹션으로 나뉩니다.

* [향후 릴리스](/docs/beta-fraud-protection-studio#신규-릴리스에-액세스하는-방법) - 새로운 프로드 감지 패키지가 적용되기 전에 최대 14일 동안 감지를 태그된 상태로 표시하여 그 영향을 평가할 수 있도록 합니다.
* [신규 릴리스](/docs/beta-fraud-protection-studio#현재-활성-패키지-평가-및-구현-방법) - 현재 활성 패키지를 평가할 수 있도록 감지 성능을 모니터링하고 바로 구현할 수 있습니다.

<div id="how-to-set-the-tagged-mode-time-period-for-future-packages" />

#### 향후 패키지에 대한 태그 모드 기간을 설정하는 방법

향후 릴리스 기능을 사용하면 향후 감지 패키지가 실제로 적용되기 전에 [태그된](/docs/beta-fraud-protection-studio#fps-모드) 상태로 유지할 기간(일 수)을 설정할 수 있습니다. 이를 설정하려면 다음을 수행합니다.

1. 드롭다운 박스의 신규 릴리스(New Release) 창에서 새 패키지가 시스템에 적용되기 전에 태그된 상태로 유지할 기간(일 수)을 선택합니다.(기본값 14일, 최대 14일까지 조정 가능)
2. **저장**을 클릭합니다.

<Image align="center" alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

<div id="note-2" />

> 📘 **참고**
>
> * 이것은 향후 패키지에만 영향을 미칩니다. 현재 실행 중인 감지 패키지는 지연되거나 변경되지 않습니다.
> * 드롭다운 박스에서 0일을 선택하는 것은 “[지금 적용(Implement now)](/docs/beta-fraud-protection-studio#태그된-상태에서-현재-패키지-구현하기)” 을 선택하는 것과 동일하며, 해당 패키지에 대한 [향후 릴리스](/docs/beta-fraud-protection-studio#신규-릴리스에-액세스하는-방법) 설정을 무시합니다.

<div id="how-to-evaluate-and-implement-current-active-packages" />

#### 현재 활성 패키지 평가 및 구현 방법

신규 현재 릴리스(New Current Release) 섹션에서는 다음을 확인할 수 있습니다.

* 마지막으로 릴리스된 패키지
* 릴리스 날짜
* 상태 - 해당 패키지가 언제 적용될지 표시 (패키지가 태그 모드인 경우)
* 해당 감지 패키지가 데이터에 미치는 영향에 대한 지표
* 세부 정보 리포트 내보내기
* 향후 릴리스 설정을 우회하고 해당 탐지 패키지를 즉시 적용

<div id="to-implement-the-current-package-if-in-tagged-status" />

#### 태그된 상태에서 현재 패키지 구현하기

1. FPS 탭에서 **신규 릴리스 카드**를 엽니다.
2. 테이블과 내보내기 가능한 리포트를 통해 감지 성능을 모니터링할 수 있습니다.
3. 준비가 되면 **지금 구현하기**를 클릭하여 변경 사항을 적용하십시오.  
   <Image align="center" alt="" src="https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png" />

<div id="note-3" />

> 📘 **참고**
>
> 이것은 이 패키지의 [향후 릴리스](/docs/beta-fraud-protection-studio#신규-릴리스에-액세스하는-방법) 설정을 무시합니다.

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="앱 감지 평가">

앱 감지 평가 카드를 이용하면 비즈니스 목표에 따라 탐지 상태를 변경할 수 있습니다. 여기서 내려진 결정은 앱 수준 에 적용되며 광고주의 모든 파트너에게 영향을 미칩니다.

앱 탐지 평가 카드에서 탐지 항목을 태그하면 Protect360의 모든 로직에 영향을 미칩니다. 하지만 사용자가 정의한 유효성 검사 규칙에 따라 발생하는 탐지는 영향을 받지 않습니다. 해당 유효성 검사 규칙을 수동으로 비활성화하지 않는 한 이러한 감지 사항은 '적용' 상태로 유지됩니다.

앱 탐지 평가 페이지를 통해 [탐지 모드](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법) (적용 또는 태그 지정)를 확인 및 변경할 수 있으며, 실시간 [탐지 현황](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source) 데이터를 모니터링할 수 있습니다.

> 🚧 **중요!**
>
> * 태그 모드의 탐지 항목을 선택할 경우, 프로드 리포트가 아닌 로데이터 리포트에 산출 및 집계됩니다.
> * 앱 탐지 평가에 대한 태그 설정은 앱 레벨로 작동하여 Protect360 로직에 의한 데이터 차단 및 기여 후속 조치 실행을 막아줍니다. 따라서 태그 모드를 설정할 경우, 오가닉 설치 및 논오가닉 설치 전반에 걸쳐 부정 모니터링 위험 요소에 노출될 우려가 있습니다.
> * 정의되고 활성화된 모든 검증 규칙은 항상 적용 모드로 유지됩니다. 검증 규칙의 적용을 일시 중지하려면 검증 규칙 페이지로 이동하여 해당 위치에서 비활성화하세요.

<div id="how-to-access-app-detection-evaluation" />

#### **앱 감지 평가에 액세스 방법**

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 >** **프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 **앱 감지 평가** 카드를 선택하세요.

<div id="app-detection-evaluation-page" />

#### **앱 감지 평가 페이지**

앱 감지 평가 페이지는 두 부분으로 나뉘어 있습니다.

* [감지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법) - [감지](/docs/beta-fraud-protection-studio#fps-모드) 모드를 선택할 수 있습니다. 적용 상태와 태그 지정 상태 중에 선택할 수 있습니다.
* [현재 감지 상태](/docs/beta-fraud-protection-studio#현재-탐지-상태) - 지난주 이전의 최근 7일을 기준으로 현재 앱 설치 및 관련 이벤트에 영향을 미치는 탐지 현황을 보여줍니다. 이 섹션은 다음과 같이 구분되어 있습니다.
  * **Protect360 로직**   
    적용 탐지 모드:
    * **적용률** - 이 비율은 (*Protect360 로직에 의해 적용된 로직의 양*)을 (*앱의 총 기여 수*)로 나눈 값을 나타냅니다.
  * **앱 수준**  
    태그 감지 모드:
    * **태그 지정률** - 이 비율은 (*앱 탐지 평가 태그 지정으로 태그가 지정된 로직의 양*)을 (*앱의 총 기여 수*)로 나눈 값을 나타냅니다.
  * **총 설치**
  * **총 감지**
  * **적용된 탐지** - [탐지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법)를 적용에서 태그 지정으로 변경하기 전 결정을 내릴 수 있도록 지원하는 데 사용됩니다.
    * Protect360 로직 - 이는 Protect360 로직을 통한 탐지 비율을 보여줍니다. 태그 지정으로 변경 시 태그 지정 탐지로 전환될 것으로 예상되는 탐지량입니다.
    * 검증 규칙 - 직접 정의하고 활성화한 검증 규칙을 기반으로 하는 탐지의 비중을 보여줍니다. 탐지 모드를 태그 지정으로 변경하더라도, 검증 규칙 기반 탐지는 적용 모드로 유지됩니다.
  * **태그 지정된 탐지** - [탐지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법)를 태그 지정에서 적용으로 변경하기 전 결정을 내릴 수 있도록 지원하는 데 사용됩니다. 탐지 상태를 태그 지정에서 적용으로 변경하기 전에, 예상되는 결과를 반영할 수 있도록 모든 태그 지정 사유에 대한 분석 결과를 확인할 수 있습니다.
    * 앱 수준 - 이 KPI는 태그 지정된 항목 중 앱 탐지 평가 카드를 통해 태그가 지정된 비중이 얼마나 되는지 이해할 수 있게 해줍니다. 이 KPI 에 반영된 수치는 탐지 상태를 적용할 경우 예상되는 증가량입니다.
    * 기타 태그 지정 - 프로드 방지 스튜디오의 여러 기능(카드)에서 탐지에 태그를 지정할 수 있습니다.

<div id="how-to-adjust-the-detection-status-1" />

#### 감지 상태를 조정하는 방법

탐지 상태를 통해 [탐지](/docs/beta-fraud-protection-studio#fps-모드) 모드를 선택할 수 있습니다. 적용됨과 태그 지정됨 중에서 선택할 수 있습니다 (기본값은 적용됨입니다).

1. 앱 탐지 평가 페이지에서 [탐지 모드](/docs/beta-fraud-protection-studio#fps-모드)를 선택하세요.
2. 페이지 하단의 저장 버튼을 클릭합니다.

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="리인게이지먼트 하이재킹 탐지">

Protect360의 리인게이지먼트 하이재킹 탐지 기능은 특히 리인게이지먼트 활동에 맞춰 기존의 부정 탐지 범위를 확장합니다. 이 탐지 기능은 부정 예방 관리에 대한 통제력을 더욱 강화해 줍니다.

기본적으로 이 탐지 기능은 [태그 지정 모드](/docs/beta-fraud-protection-studio#fps-모드)로 출시되므로, 적용하기 전에 그 효과와 잠재적 영향을 평가해 볼 수 있습니다.

<div id="how-this-works-1" />

#### 작동 방식

* 리인게이지먼트 하이재킹 탐지는 기본적으로 태그 지정 모드로 설정되어 있습니다. 실시간 어트리뷰션 데이터에 영향을 주지 않고 탐지 성능을 평가할 수 있습니다.
* 적용 시 탐지는 어트리뷰션 이후에 발생하며, 이는 부정 리인게이지먼트를 식별하여 어트리뷰션 기록에서 제거함을 의미합니다.
* 적용 시 탐지 후 제거된 모든 앱 내 이벤트는 기존 유저 획득(UA) 제공업체로 다시 어트리뷰션되거나, 유효한 UA 제공업체가 없는 경우 오가닉으로 표시됩니다.

<div id="how-to-access" />

#### 액세스 방법

1. **앱스플라이어**에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 상단의 앱 드롭다운을 사용하여 설정하려는 앱을 선택하세요.
4. 왼쪽 메뉴에서 **리인게이지먼트 하이재킹** 카드를 선택하세요.

<div id="re-engagement-hijacking-page" />

#### 리인게이지먼트 하이재킹 페이지

리인게이지먼트 하이재킹 페이지는 두 부분으로 나뉩니다.

* [감지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법) - [감지](/docs/beta-fraud-protection-studio#fps-모드) 모드를 선택할 수 있습니다. 적용 상태와 태그 상태 중에서 선택할 수 있습니다.
* [현재 탐지 상태](/docs/beta-fraud-protection-studio#현재-탐지-상태) - 오늘을 제외한 최근 14일을 기준으로, 리인게이지먼트 하이재킹을 활성화했을 때 설치 및 관련 이벤트에 미쳤을 영향을 보여줍니다.  
  **참고:** 리인게이지먼트 하이재킹 탐지는 어트리뷰션 이후에 작동하므로, 최근 7일간의 데이터는 불완전할 수 있으며 소급하여 계속 업데이트됩니다.  

  이 섹션은 다음과 같이 구분되어 있습니다.
  * 리인게이지먼트 하이재킹 탐지 위젯
    * 탐지 건수 - 리인게이지먼트 하이재킹 로직 단독으로 탐지된 수
    * 탐지율 - 전체 리인게이지먼트 탐지 중 리인게이지먼트 하이재킹 탐지가 차지하는 백분율
  * 전체 리인게이지먼트 탐지 위젯 - 모든 로직에서 탐지된 전체 리인게이지먼트 탐지량
  * 리인게이지먼트 어트리뷰션 볼륨 위젯
    * 어트리뷰션 - 해당 기간 동안의 리인게이지먼트 어트리뷰션량
    * 전체 어트리뷰션 대비 비율 - 전체 앱 어트리뷰션 중 리인게이지먼트 어트리뷰션이 차지하는 비중
  * 미디어 소스별 리인게이지먼트 탐지 - 탐지 건수가 가장 높은 주요 미디어 소스의 리인게이지먼트 하이재킹 탐지 수

<Image align="center" alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="인앱 기반 탐지">

앱 내 기반 탐지는 앱 내 행동 이상 징후를 분석하여 어트리뷰션 이후 시점에 설치 건을 확정적으로 부정으로 표시합니다. 설치 후 실제 참여를 시늉하지만 비정상적인 이벤트 흐름과 타이밍 패턴을 보이는 봇 등 고도화된 부정 행위 수법을 식별합니다.

#### 액세스 방법

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭 다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 **인앱 기반 감지** 카드를 선택하세요.

<div id="the-in-app-based-detection-page" />

#### 인앱 기반 감지 페이지

인앱 기반 감지 페이지는 두 부분으로 나뉩니다.

* [감지 상태](/docs/beta-fraud-protection-studio#클릭-플러드에-액세스하는-방법) - [감지](/docs/beta-fraud-protection-studio#fps-모드) 모드를 선택할 수 있습니다. 적용됨과 태그 지정됨 중에서 선택할 수 있습니다.
* [현재 감지 상태](/docs/beta-fraud-protection-studio#현재-탐지-상태) - 오늘을 제외한 최근 14일을 기준으로, 앱 내 기반 탐지를 활성화했을 때 설치 건에 미쳤을 영향을 보여줍니다.   

  참고: 앱 내 기반 탐지는 어트리뷰션 이후에 작동하므로, 최근 7일간의 데이터는 불완전할 수 있으며 소급하여 계속 업데이트됩니다.

이 섹션은 다음과 같이 구분되어 있습니다.

* **앱 내 기반 로직에 의한 신규 탐지**
  * 탐지 건수 - 앱 내 로직에 의해 탐지된 설치 건수
  * 추가 가치 비율 - 앱의 전체 설치 수 대비 앱 내 기반 탐지 건수의 비율
* **가짜 설치 감지**
  * 탐지 횟수 - 총 오탐지 횟수
  * 탐지율 - 앱의 전체 설치 수 대비 가짜 탐지 수의 비율
* **총 설치**

* **미디어 소스별 앱 내 기반 탐지** - 주요 미디어 소스별 설치 수

<Image align="center" alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="고급 보안 모듈 데이터">

Android 앱을 대상으로 고급 보안 모듈이 실시간으로 탐지한 설치 후보 사이버 공격 건을 확인하세요. 이를 통해 검증된 트래픽만 앱에 도달하도록 보호할 수 있습니다.

<div id="how-to-access-2" />

<div id="how-to-access-1" />

#### 액세스 방법

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 **설정 > Protect360 > 프로드 방지 스튜디오**로 이동합니다.
3. 페이지 상단의 앱 드롭 다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 **고급 보안 모듈** 카드를 선택하십시오.

<div id="the-advanced-security-module-page" />

#### 고급 보안 모듈 페이지

고급 보안 모듈 페이지에는 다음 내용이 표시됩니다.

* **상위 앱 버전** — 설치량이 가장 많은 상위 5개 앱 버전으로, 스푸핑된 트래픽이 어디에 집중되어 있는지 파악할 수 있습니다.

감지 결과는 다음 중 하나로 표시됩니다.

* **차단됨** — 어트리뷰션 전 단계에서 실시간으로 차단된 트래픽입니다.
* **태그됨** — 의심스러운 트래픽으로 표시되었으나 어트리뷰션은 유지되므로, 적용하기 전에 미리 검토할 수 있습니다. 기본 감지 모드입니다.
* **태그되지 않음** 모듈에서 이상으로 표시하지 않은 설치 후보 건입니다.

<div id="note-4" />

> 📘 **참고**
>
> 전체 설정, 요구사항 및 상세 리포트는 <Anchor target="_blank" href="/marketers/ko/docs/beta-advanced-security-protect360-module">[Beta] 고급 보안 Protect360 모듈</Anchor> 문서를 참조하세요.

</Accordion>

<div id="faqs" />

## 자주 묻는 질문

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="파트너 또는 미디어 소스를 위한 태그된 감지를 구성할 수 있나요?">

이것은 감지 유형에 따라 다릅니다. 예를 들어, 편향된 감지를 방지하기 위해 하이재킹 감지에는 파트너 태깅이 제공되지 않습니다.

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="태그 지정 기간이 끝나면 어떻게 되나요?">

평가 기간이 끝나면 태그된 감지가 구현 모드로 자동 전환됩니다.

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="태그된 설치는 어디에서 볼 수 있나요?">

태그 지정된 데이터는 **원시 데이터 리포트**의 다음 리포트에서 확인할 수 있습니다.

* 태그된 설치
  * 실시간
* 태그된 설치
  * 포스트 어트리뷰션
* 태그된 인앱 이벤트
  * 실시간
* 태그된 인앱 이벤트
* 포스트 어트리뷰션

다음 태그가 지정된 리포트도 **데이터 락커** 에서 이용할 수 있습니다.

* 태그된 설치
  * 실시간
* 태그된 인앱 이벤트
  * 실시간

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="앱별 설정에 맞게 태그된 감지를 조정할 수 있나요?">

네, 클릭 클릭플러드 태그 지정은 앱 수준에서 구성할 수 있습니다.

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="태그된 인앱 이벤트를 볼 수 있나요?">

네. 같은 앱스플라이어 ID로 태그된 설치와 연결된 인앱 이벤트도 태그됩니다.

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="누가 FPS를 변경, 설정 또는 볼 수 있나요?">

오직 관리자 계정만 FPS 설정을 변경할 수 있습니다. 프로드 방지 스튜디오는 <Anchor target="_blank" href="/marketers/ko/docs/manage-data-access-permissions">권한 페이지</Anchor>에 따라 표시됩니다.

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="태그된 설치 건에 대해 소비 플랜에 크레딧이 반환되나요?">

아니요. 태그된 탐지 항목은 소비 플랜에 크레딧으로 반환되지 않습니다.

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="태그된 설치는 프로드로 간주되나요?">

Protect360에서 태그된 인스톨을 탐지합니다. 그러나 고객의 설정에 따라 태그됩니다. 따라서 개요 대시보드 및 Protect360 대시보드 모두에서 해당 항목은 어트리뷰션된 지표에 반영됩니다.

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="클릭 플러드 태깅으로만 태그된 인스톨 수를 볼 수 있을까요?">

네. 이 데이터는 내보내기 페이지와 Protect360 대시보드의 새로운 전용 리포트에서 사용할 수 있습니다.

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%86%8C%EA%B0%9C 01JEQR86DC1CK03DKCZH760N4M=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%86%8C%EA%B0%9C h_01JK3BGVNMYFQYQGRPJBVN2A7Z=%EC%A4%91%EC%9A%94 how-flexible-protection-works=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC 01JEQR86DEG7RTRNYFP02WHJGQ=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4%EC%9D%98-%EC%9E%91%EB%8F%99-%EC%9B%90%EB%A6%AC 01JETRN5S347ZXV8CGZJDHQH56=key-concepts fps-modes=fps-%EB%AA%A8%EB%93%9C h_01JEWZEBBA9VAPCKR87NJ5AK3C=fps-%EB%AA%A8%EB%93%9C 01JEWZQ7PBD6W4J15W0HE2Q4MJ=%EC%B0%B8%EA%B3%A0 where-is-tagged-detection-reflected=%ED%83%9C%EA%B7%B8%EB%90%9C-%ED%83%90%EC%A7%80%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EB%B0%98%EC%98%81%EB%90%98%EB%82%98%EC%9A%94 01JEWZT9N34FZ9SE8H7EGCMPBZ=%ED%83%9C%EA%B7%B8%EB%90%9C-%ED%83%90%EC%A7%80%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EB%B0%98%EC%98%81%EB%90%98%EB%82%98%EC%9A%94 how-to-use-flexible-protection=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95 01JEQR86ECSYTM7RN3YPYRSAGE=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=%EC%A4%91%EC%9A%94-1 adjust-detection-status=%ED%81%B4%EB%A6%AD-%ED%94%8C%EB%9F%AC%EB%93%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01JEQVJS6YTQD299X39Q8E3506=%ED%81%B4%EB%A6%AD-%ED%94%8C%EB%9F%AC%EB%93%9C%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 click-flood-page=%ED%81%B4%EB%A6%AD-%ED%94%8C%EB%9F%AC%EB%93%9C-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JJKE1ZKE5WDRSPKS8JE9MRRG=%ED%81%B4%EB%A6%AD-%ED%94%8C%EB%9F%AC%EB%93%9C-%ED%8E%98%EC%9D%B4%EC%A7%80 detection-status=%ED%83%90%EC%A7%80-%EC%83%81%ED%83%9C h_01JZQ81MW4HMY9B782Y7PWVE8Y=%ED%83%90%EC%A7%80-%EC%83%81%ED%83%9C h_01JJKE1ZKEJ4QM2HTT37FERA92=%EA%B0%90%EC%A7%80-%EC%83%81%ED%83%9C%EB%A5%BC-%EC%A1%B0%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 current-detection-status=%ED%98%84%EC%9E%AC-%ED%83%90%EC%A7%80-%EC%83%81%ED%83%9C 01JEQVZCNSTXY4V8H2Y1QP224C=%ED%98%84%EC%9E%AC-%ED%83%90%EC%A7%80-%EC%83%81%ED%83%9C 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=%EC%B0%B8%EA%B3%A0-1 how-this-works=%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D h_01JEXC0ABSTCEA939DGQ5SDJBJ=%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D how-to-set-the-tagged-mode-time-period-for-future-packages=%EC%8B%A0%EA%B7%9C-%EB%A6%B4%EB%A6%AC%EC%8A%A4%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JEXC2HAR2S6BWK28N8W3HHSZ=%EC%8B%A0%EA%B7%9C-%EB%A6%B4%EB%A6%AC%EC%8A%A4%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 new-releases-page=%EC%8B%A0%EA%B7%9C-%EB%A6%B4%EB%A6%AC%EC%8A%A4-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JJKE1ZKE0K1W2VE3KHQ639B1=%EC%8B%A0%EA%B7%9C-%EB%A6%B4%EB%A6%AC%EC%8A%A4-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JJKE1ZKE13D7EC6BMN3JJNGW=%ED%96%A5%ED%9B%84-%ED%8C%A8%ED%82%A4%EC%A7%80%EC%97%90-%EB%8C%80%ED%95%9C-%ED%83%9C%EA%B7%B8-%EB%AA%A8%EB%93%9C-%EA%B8%B0%EA%B0%84%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01JF50BVZ75ZSXTJEKAV4HVSTZ=%EC%B0%B8%EA%B3%A0-2 how-to-evaluate-and-implement-current-active-packages=%ED%98%84%EC%9E%AC-%ED%99%9C%EC%84%B1-%ED%8C%A8%ED%82%A4%EC%A7%80-%ED%8F%89%EA%B0%80-%EB%B0%8F-%EA%B5%AC%ED%98%84-%EB%B0%A9%EB%B2%95 h_01JEXC3DESR10WVV34ED30B7BH=%ED%98%84%EC%9E%AC-%ED%99%9C%EC%84%B1-%ED%8C%A8%ED%82%A4%EC%A7%80-%ED%8F%89%EA%B0%80-%EB%B0%8F-%EA%B5%AC%ED%98%84-%EB%B0%A9%EB%B2%95 to-implement-the-current-package-if-in-tagged-status=%ED%83%9C%EA%B7%B8%EB%90%9C-%EC%83%81%ED%83%9C%EC%97%90%EC%84%9C-%ED%98%84%EC%9E%AC-%ED%8C%A8%ED%82%A4%EC%A7%80-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 h_01JF505FK4NP88WYXP8PVQRYDS=%ED%83%9C%EA%B7%B8%EB%90%9C-%EC%83%81%ED%83%9C%EC%97%90%EC%84%9C-%ED%98%84%EC%9E%AC-%ED%8C%A8%ED%82%A4%EC%A7%80-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 01JF50BVZ9QPT5W41P8KQAREKV=%EC%B0%B8%EA%B3%A0-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=%EC%A4%91%EC%9A%94-2 how-to-access-app-detection-evaluation=%EC%95%B1-%EA%B0%90%EC%A7%80-%ED%8F%89%EA%B0%80%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 h_01JQXG4GJ2DB8HM26K3E1WA3A1=%EC%95%B1-%EA%B0%90%EC%A7%80-%ED%8F%89%EA%B0%80%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 app-detection-evaluation-page=%EC%95%B1-%EA%B0%90%EC%A7%80-%ED%8F%89%EA%B0%80-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JQXG6QDSTAPCJDMQVQMXS86W=%EC%95%B1-%EA%B0%90%EC%A7%80-%ED%8F%89%EA%B0%80-%ED%8E%98%EC%9D%B4%EC%A7%80 how-to-adjust-the-detection-status=%EA%B0%90%EC%A7%80-%EC%83%81%ED%83%9C%EB%A5%BC-%EC%A1%B0%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95-1 h_01JQXG6QEAM0Y67G504JV2SA5R=%EA%B0%90%EC%A7%80-%EC%83%81%ED%83%9C%EB%A5%BC-%EC%A1%B0%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=%EC%9E%91%EB%8F%99-%EB%B0%A9%EC%8B%9D-1 how-to-access=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 h_01JWAVPAVK7ZT471AQAFKAS64K=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 reengagement-hijacking-page=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JWAVPAVKKB4JSP41P967EESS=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95-2 h_01JZMAZET0JXYEDGKE0B797TQ7=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95-2 the-inapp-based-detection-page=%EC%9D%B8%EC%95%B1-%EA%B8%B0%EB%B0%98-%EA%B0%90%EC%A7%80-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=%EC%9D%B8%EC%95%B1-%EA%B8%B0%EB%B0%98-%EA%B0%90%EC%A7%80-%ED%8E%98%EC%9D%B4%EC%A7%80 advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95-2 h_01K0ASM07ADVSECMOD07=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%ED%8E%98%EC%9D%B4%EC%A7%80 the-advanced-security-module-page=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01K0ASM13ADVSECMOD13=%EC%B0%B8%EA%B3%A0-4 faqs=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01JEQR86EMZQFNSZ5NWZ08F5YQ=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />
