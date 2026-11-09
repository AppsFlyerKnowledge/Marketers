---
title: 데이터 클린룸 - 인앱 이벤트 리포트 생성
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
  created_at: '2022-09-22T12:03:40Z'
  edited_at: '2026-10-14T10:29:25Z'
  id: 9312610473233
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/9312610473233
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 앱이 설치된 후 발생하는 사용자 활동에 초점을 맞춘 인앱 이벤트 리포트를 만듭니다. 인앱 이벤트 로데이터에서 특정 이벤트 파라미터를 추출하고, 선택적으로 데이터를 사용자 지정 소스와 일치시킨 다음, 이를 처리하여 집계된 형태로 표시합니다.

<div id="creating-an-in-app-event-report" />

## 인앱 이벤트 리포트 만들기

**인앱 이벤트 리포트를 만들려면 아래 탭에 자세히 설명된 단계를 따르세요.**

**참고:** 이들 단계는 쉽게 읽을 수 있도록 탭으로 나뉩니다. 리포트를 만들려면 모든 단계를 완료해야 합니다. *(표시된 대로 특정 단계는 사용자 지정 소스를 사용하지 않는 리포트와 관련이 없습니다.)*

<div id="perform-preliminary-steps" />

<Accordion title="예비 단계 수행">

1. **DCR**의 **리포트** 탭으로 이동합니다.
2. **+ 새 리포트** 버튼을 클릭합니다.
3. **인앱 이벤트**를 소스 데이터 유형으로 선택한 다음, 화면 오른쪽 하단에서 **다음**을 클릭합니다.
4. 리포트의 이름을 입력합니다.
   * DCR 플랫폼에서 리포트를 식별하는 데 도움이 될 이름일 수 있습니다.
   * **중요!** 리포트 이름이 계정의 다른 모든 리포트와 달라야 하며, 그렇지 않으면 [리포트를 저장](/docs/data-clean-room-creating-in-app-event-reports#configure-report-settings-and-save-the-report)할 수 없습니다.
   * 리포트 이름 요구 사항:
     * 길이: 2&#126;80자
     * 유효한 문자:
       * 문자 **(A-Z, a-z)**
       * 숫자 **(0-9)**, *이름의 첫 문자가 될 수 없습니다.*
       * 하이픈 (-), *이름의 첫 문자가 될 수 없습니다.*
     * 유효하지 않은 문자:
       * 공백
       * 기타 모든 기호 또는 특수 문자

</Accordion>

<div id="select-sources" />

<Accordion title="소스 선택">

리포트에 사용할 소스 데이터를 지정합니다.

<div id="in-app-event-sources" />

#### **인앱 이벤트 소스**

* **앱:** 앱스플라이어 계정에서 하나 이상의 앱을 선택합니다.
* **시간표:** DCR이 인앱 이벤트를 검색하도록 할 기록 데이터의 일수(1&#126;30일)를 선택합니다.
* **이벤트:** 리포트에 포함할 인앱 이벤트를 하나 이상 선택합니다.
  * 사용 가능한 이벤트에는 SDK 또는 서버 간 API(S2S)를 통해 앱스플라이어에 데이터를 리포트하도록 구성된 **선택한 앱**의 모든 인앱 이벤트가 포함됩니다.
* **소스 유형:** 하나 이상의 인앱 이벤트 데이터 유형을 선택합니다. 

| 인스톨 | 설치 어트리뷰션과 관련된 인앱 이벤트<ul><li>사용자가 모바일 앱을 다운로드하고 설치하고 실행하면 설치가 기록됩니다.</li></ul> |
| --- | --- |
| 재참여 | 리인게이지먼트와 관련된 인앱 이벤트<ul><li>리인게이지먼트는 특정 앱의 비활성 사용자가 앱에 대한 리타겟팅 캠페인에 참여한 후 앱을 실행할 때 기록됩니다.</li></ul> |
| 리어트리뷰션 | 리어트리뷰션과 관련된 인앱 이벤트<ul><li>리어트리뷰션은 특정 앱의 이전 사용자(앱을 제거한 사용자)가 앱에 대한 리타겟팅 캠페인에 참여한 후 앱을 다시 설치할 때 기록됩니다.</li></ul> |

<div id="data-sources" />

#### **데이터 소스**

1. [선택 사항] 리포트에서 사용할 소스를 더 추가합니다. 소스를 더 추가할지 여부를 선택할 때 사용자 지정 소스를 **사용하는** 리포트와 **사용하지 않는** 리포트 간의 상당한 차이에 유의하세요.
   * 사용자 지정 소스를 사용하지 **않는** 리포트는 인앱 이벤트 로데이터에서 특정 이벤트 파라미터와 값을 추출합니다.
   * 사용자 지정 소스를 **사용하는** 리포트는 인앱 이벤트 로데이터에서 특정 이벤트 파라미터와 값을 추출한 다음, 이 데이터를 사용자 지정 소스(예: BI 또는 CRM 시스템의 데이터)의 사용자 수준 데이터와 일치시킵니다.
2. 리포트에서 사용자 지정 소스를 사용하는지 여부를 기준으로 다음 단계를 완료합니다.
   * 리포트에서 사용자 지정 소스를 사용하지 **않는** 경우 **[측정기준 선택](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions)** 으로 건너뛴 다음 나머지 모든 탭의 단계를 계속 진행합니다.
   * 리포트에서 사용자 지정 소스를 **사용하는** 경우 바로 다음에 나오는 [**소스 조인**](#join-sources-only-for-reports-containing-custom-sources) 탭과 나머지 모든 탭의 단계를 계속 진행합니다.

</Accordion>

다음 단계는 **사용자 지정 소스를 사용하는 리포트에만** 해당됩니다.

<div id="join-sources-only-for-reports-containing-custom-sources" />

<Accordion title="소스 조인(사용자 지정 소스가 포함된 리포트에만 해당)">

소스 사이에서 데이터를 일치시키려면 리포트에 사용된 각 **사용자 지정** 소스에 인앱 이벤트 데이터의 **키 식별자**에 매핑된 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services">식별자</Anchor>가 포함되어야 합니다.

* 인앱 이벤트 리포트에는 선택한 기간 동안 키 식별자와 일치하는 선택된 이벤트가 **모두** 포함됩니다.

<div id="what-is-a-key-identifier" />

#### **키 식별자란 무엇입니까?**

이러한 인앱 이벤트 데이터 식별자 중 하나에 다음과 같이 **키 식별자**로 매핑할 수 있습니다.

* **앱스플라이어 ID(af\_id):** 앱스플라이어 설치 시, 앱스플라이어가 생성하는 고유한 앱 식별자–
  * 이 ID는 앱스플라이어가 기록한 모든 이벤트에 나타납니다.
  * 앱을 삭제한 다음 다시 설치하면 새 앱스플라이어 ID가 생성됩니다.
* **고객 사용자 ID(CUID):** 일반적으로 사용자 등록 시 앱 소유자가 생성하고 설정하는 고유한 사용자 식별자입니다.
  * CUID를 사용하여 데이터를 매핑하려면 앱이 SDK 또는 서버 간 API(S2S)를 통해 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">앱스플라이어로 CUID를 전송</Anchor>하도록 구성되어 있어야 합니다.

<div id="important" />

> 🚧 **중요!**
>
> 모든 미디어소스가 CUID를 사용한 일치를 허용하는 것은 아닙니다. 반드시 앱스플라이어 ID를 사용하는 것이 좋습니다.

<div id="mapping-schemes-directindirect" />

#### **매핑 스키마(직접/간접)**

리포트에 두 개 이상의 사용자 지정 소스가 포함된 경우, 그중 하나만 인앱 이벤트 키 식별자에 **직접** 매핑하면 됩니다. 다음 예에서 설명한 대로 다른 사용자 지정 소스는 **직접 또는 간접적으로** 매핑할 수 있습니다.

<div id="example" />

> 📄 **예시**
>
> <Image align="center" alt="dcr_mapping_identifiers_in-app events.png" src="https://files.readme.io/73d0e929663bda4e6f142c64d0228fdf1eeec3b02ef1560f6f03f2a089d00664-9969546429713.png" />
>
> 위에 표시된 시나리오에서:
>
> * 사용자 지정 소스 #1 식별자 **AF**는 인앱 이벤트 키 식별자 **af\_id**에 직접 매핑됩니다.
> * 사용자 지정 소스 #2는 간접적으로 매핑됩니다. **user\_code** --> **AF** --> **af\_id.**
> * 사용자 지정 소스 #3은 더 긴 체인을 통해 간접적으로 매핑됩니다.
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * 사용자 지정 소스 #4 식별자 **ID**는 인앱 이벤트 키 식별자 **af\_id**에 직접 매핑됩니다.
>   * (사용자 지정 소스 #3 식별자 **user\_id**를 통해) 대신 간접적으로 매핑되었을 수도 있지만, 어느 옵션이든 다 잘 작동합니다.
>
> ✓ 이 매핑 스키마는 각 사용자 지정 소스가 인앱 이벤트 키 식별자 **af\_id**에 직접 또는 간접적으로 매핑되므로 모든 소스 사이에서 데이터를 일치시키는 역할을 합니다.

</Accordion>

나머지 탭은 사용자 지정 소스 포함 여부와 관계없이 **모든 인앱 이벤트 리포트**와 관련됩니다.

<div id="select-dimensions" />

<Accordion title="측정기준 선택">

사용자 수준 데이터는 DCR에서 리포트할 수 없습니다. 대신, 선택한 측정기준별로 데이터를 집계(또는 그룹화)하여 필요한 의사 결정 인사이트를 제공합니다.

측정기준은 일반적으로 앱 사용자를 분류하는 기준이 되는 특성입니다(예: 지역, 설치 날짜, 캠페인 등).

<div id="extracting-dimensions-from-event_value" />

#### **event\_value에서 측정기준 추출**

인앱 이벤트가 SDK나 S2S API를 통해 앱스플라이어에 리포트되는 경우, 로데이터 대부분은 **event\_value라는 단일 필드에 포함됩니다.** 이 구조화된 데이터 필드에는 앱이 앱스플라이어에 전송하는 이벤트에 대해 구성된 모든 특정 인앱 이벤트 파라미터가 포함됩니다.

인앱 이벤트 리포트의 주요 장점 중 하나는 선택한 이벤트에 대한 **event\_value** 필드에서 특정 파라미터와 해당 값을 추출할 수 있다는 점입니다.

**DCR 리포트에서 사용하도록 event\_value 필드에서 측정기준을 추출하려면 다음을 수행하세요.**

1. **소스의 측정기준** 목록에서 <Image alt="extract_dimension_button.png" src="https://files.readme.io/c238da4a1d2a15fe2249070747fa6247db63ab4129b1c72804b84550675214f3-10754426767761.png" width="123px" /> 버튼을 클릭합니다.

   **event\_value에서 필드 추출** 창이 열립니다.
2. **리포트 필드** 상자에 리포트에 표시할 추출된 측정기준의 이름을 입력합니다.
3. **Event\_value 파라미터** 목록에서 2단계에서 정의한 리포트 필드(측정기준)에 기본적으로 매핑해야 하는 인앱 이벤트 파라미터를 선택합니다.
   * 사용 가능한 파라미터에는 **선택한 앱**의 **선택한 인앱 이벤트**에서 구성된 파라미터가 포함됩니다.
4. 기본 매핑은 앱 및/또는 이벤트에 따라 다를 수 있습니다. 이 경우에는 다음을 수행하세요.
   1. **예외 추가** 버튼을 클릭합니다.
   2. 리포트 필드를 다르게 매핑해야 하는 앱과 이벤트를 선택합니다.
   3. 이 앱/이벤트 조합에 대한 리포트 필드에 매핑해야 하는 인앱 이벤트 파라미터를 선택합니다.
   4. 설정하려는 예외 횟수에 대해 다음 단계를 수행합니다.
5. 추출된 측정기준에 대한 매핑 설정을 마치면 **저장 및 다른 측정기준 추가**를 클릭하여 event\_value 필드에서 다른 측정기준을 추출하거나 **저장**을 클릭하여 기본 화면으로 돌아갑니다.

**추출된 측정기준을 편집하는 방법은 다음과 같습니다.**

1. **소스의 측정기준**이나 **리포트 측정기준** 목록에서 편집하려는 측정기준의 이름을 마우스로 가리킵니다.
2. 측정기준 오른쪽에 표시되는 <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> 버튼을 클릭합니다.
3. **추출된 필드 편집**을 선택합니다.
4. 필요에 따라 **리포트 필드** 이름 및/또는 파라미터 매핑을 변경합니다.
5. 변경 사항을 저장하려면 **저장**을 클릭합니다.

**추출된 측정기준을 삭제하는 방법은 다음과 같습니다.**

1. **소스의 측정기준** 또는 **리포트 측정기준** 목록에서 삭제하려는 측정기준의 이름을 마우스로 가리킵니다.
2. 측정기준 오른쪽에 표시되는 <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> 버튼을 클릭합니다.
3. **필드 삭제**를 선택합니다.
   * **주의!** **리포트 측정기준** 목록에서 추출된 필드를 삭제하면 추출된 필드의 정의도 삭제됩니다. 정의를 보존하면서 리포트에서 필드를 제거하려면 필드를 선택하고 대신 **제거** 버튼을 사용하세요.

<div id="selecting-report-dimensions" />

#### **리포트 측정기준 선택**

인앱 이벤트 리포트 측정기준에는 다음이 포함될 수 있습니다.

* event\_value에서 추출한 측정기준
* [기본 인앱 이벤트 측정기준](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)
* (해당되는 경우) <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#3-define-the-source-structure">측정기준으로 분류된</Anchor> 리포트의 사용자 지정 소스에 있는 모든 필드

**리포트에 포함할 측정기준을 선택하는 방법은 다음과 같습니다.**

1. 왼쪽에 있는 **소스의 측정기준** 목록에서 하나 이상의 측정기준을 선택하고 화면 중앙에 있는 **추가** 버튼을 사용하여 이들 측정기준을 **리포트 측정기준** 목록에 추가합니다.
   * 검색 창을 사용하여 목록에서 측정기준을 검색할 수 있습니다.
2. 측정기준을 제거하려면 **리포트 측정기준** 목록에서 제거할 측정기준을 선택하고 **제거** 버튼을 사용하여 **소스의 측정기준** 목록으로 되돌립니다.
3. 리포트에 포함하려는 각 측정기준을 추가할 때까지 이 과정을 반복합니다.

**참고:** 기본적으로 모든 리포트는 인앱 이벤트 측정기준 **media\_source**를 기준으로 그룹화됩니다. 리포트에서 이 측정기준을 사용하지 않으려면 **리포트 측정기준** 목록에서 제거할 수 있습니다.

<div id="optional-customizing-dimension-display-names" />

#### **[선택 사항] 측정기준 표시 이름 사용자 지정**

기본적으로, 측정기준 이름은 인앱 이벤트 데이터 또는 사용자 지정 소스에 이름이 지정된 그대로 정확히 리포트에 표시됩니다. 원한다면 리포트의 측정기준 이름을 사용자 지정할 수 있습니다.

**측정기준 표시 이름을 사용자 지정하는 방법은 다음과 같습니다.**

1. **리포트 측정기준** 목록에서 표시 이름을 편집하려는 측정기준의 이름을 마우스로 가리킵니다.
2. 측정기준 오른쪽에 표시되는 편집 버튼 ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png)을 클릭합니다.
3. 이름을 리포트에 사용할 측정기준 표시 이름(최대 50자)으로 변경합니다.
4. 표시 이름을 저장하려면 **확인**을 클릭하고 취소하려면 **X**를 클릭합니다.

**참고:** **추출된 측정기준**의 이름을 변경하려면 위에서 추출한 측정기준을 편집하는 단계를 따르세요.

<div id="preserving-privacy-while-grouping-by-dimension-regrouping" />

#### **측정기준별로 그룹화하는 동안(재그룹화) 개인정보 보호**

데이터 세트의 크기, 선택한 측정기준 수, 기타 요인에 따라 리포트에 사용자 수가 너무 적어 리포팅을 허용할 수 없는 그룹이 하나 이상 포함될 수 있습니다. 데이터가 이러한 방식으로 리포트되면 사용자 수준 데이터 제공에 대한 제한을 위반하게 됩니다.

그러나 리포트에서 데이터를 완전히 제거하거나 숨기는 대신 DCR은 **재그룹화 메커니즘**을 사용하여 사용자 개인정보 보호를 유지하면서 가능한 한 많은 세부 정보를 제공합니다.

<div id="regrouping-example" />

> 📄 **재그룹화 예**
>
> (순서대로) 다음 측정기준에 따라 리포트를 설정했다고 가정하겠습니다.
>
> * **인앱 이벤트 측정기준:**
>   * 미디어소스별
>   * campaign
>   * adset\_name
>   * ad\_id
> * **사용자 지정 소스 측정기준:**
>   * user\_type
>
> **재그룹화하기 전에**
>
> 데이터의 초기 분석 후, DCR이 데이터가 다음과 같이 분류된다고 결정합니다.
>
>
>
> | media  <br />source | campaign | adset  <br />name | ad  <br />id | user  <br />type | rev  <br />D0 | rev  <br />D7 | count | reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | lkh123 | beg | 6 | 7 | x | **X** |
> | media\_source | UA\_200 | green | ilk945 | beg | 3 | 21 | x | **X** |
> | media\_source | UA\_200 | green | plm654 | beg | 8 | 17 | x | **X** |
>
>
>
> 현재 상태 그대로, 마지막 3개 행은 각각 사용자 수가 너무 적어 리포트할 수 없습니다. (이 미디어소스는 최소 **y**명 이상의 사용자가 있어야 리포트 가능합니다. 그런데 **x**명밖에 없습니다.)
>
> 재그룹화 논리에 따라 DCR은 먼저 마지막으로 나열된 인앱 이벤트 측정기준을 ‘제거’합니다(이 경우 **ad\_id**). 그런 다음 데이터를 다시 분석하여 리포트 가능한 행을 확인합니다.
>
> **재그룹화 후**
>
> 재그룹화 논리를 적용한 후 리포트는 다음과 같이 나타납니다.
>
>
>
> | media  <br />source | campaign | adset  <br />name | ad  <br />id | user  <br />type | rev  <br />D0 | rev  <br />D7 | count | reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | RESTRICTED | beg | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **결과:**
>
> * 이제 마지막 행은 이전에 3개 행에 있었던 데이터를 결합합니다. 그러면 결합된 행의 사용자 수가 **y**와 같아져 리포트할 수 있습니다.
> * 제거된 측정기준은 이제 RESTRICTED로 리포트됩니다.
> * 리포트할 수 없는 행(**y**명 미만의 사용자)이 여전히 있는 경우 DCR은 반복적으로 데이터를 분석하여 다음 중 하나가 충족될 때까지 측정기준을 하나씩 제거합니다.
>   * 모든 행을 리포트할 수 있을 때까지, 또는
>   * 제거할 인앱 이벤트 측정기준이 부족해질 때까지
>
> **참고:** 기본적으로, DCR은 (추출된 인앱 이벤트 측정기준이나 사용자 지정 소스 측정기준이 아니라) **[기본 인앱 이벤트 측정기준](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)** 에만 재그룹화를 적용합니다. 기본 인앱 이벤트 측정기준에 따라 그룹화된 데이터가 **y**명 미만의 사용자를 포함하는 행으로 생성되는 경우, 해당 행의 데이터는 RESTRICTED로 리포트됩니다.
>
> * *사용자 지정 소스 측정기준에도 재그룹화를 적용하는 데 사용할 수 있는 고급 옵션에 대해서는 아래를 참조하세요.*

<div id="optional-managing-dimension-priority" />

#### **[선택 사항] 측정기준 우선순위 관리**

기본적으로, 인앱 이벤트 측정기준은 **리포트 측정기준** 목록에 나타나는 순서의 역순으로 제거됩니다. 그러나 기본 시퀀스를 수정하거나 선택한 사용자 지정 소스 측정기준(해당되는 경우)에 재그룹화를 적용하여 자신에게 가장 중요한 측정기준을 유지할 수 있습니다.

**측정기준이 제거되는 순서를 변경하는 방법은 다음과 같습니다.**

1. **측정기준 우선순위 관리** 버튼을 클릭합니다.
2. 측정기준을 선택하고 목록에서 원하는 위치로 드래그하거나 오른쪽의 화살표 버튼을 사용하여 이동합니다.
   * (목록 맨 위) **가장 높은 우선순위**로 레이블이 지정된 측정기준은 재그룹화가 필요한 경우 가장 마지막으로 제거된다는 의미입니다.
3. [선택 사항] 사용자 지정 소스 측정기준에 재그룹화를 적용하는 방법은 다음과 같습니다(사용자 지정 소스를 사용하는 리포트의 경우).
   1. **고급 옵션을 사용하여 재그룹화 구체화**를 클릭합니다.
   2. 재그룹화를 적용하려는 사용자 지정 소스 측정기준을 선택합니다.
   3. 선택한 측정기준이 **측정기준 우선순위 관리** 목록에 추가됩니다.
      * 기본적으로, 이러한 측정기준은 재그룹화를 위해 **가장 낮은 우선순위**로 목록 맨 아래에 추가됩니다. 그러나 위에서 설명한 대로 인앱 이벤트 측정기준과 마찬가지로 순서를 변경할 수 있습니다.
4. **확인**을 클릭하여 변경 사항을 저장합니다.
   * 기본 화면의 **리포트 측정기준** 목록은 원래 순서대로 유지되지만, 수정된 순서는 저장되었습니다. (선택 사항을 검토하거나 편집하려면 **측정기준 우선순위 관리** 버튼을 다시 클릭하세요.)

</Accordion>

<div id="select-metrics" />

<Accordion title="지표 선택">

지표는 앱 사용자와 관련하여 수집한 숫자 데이터(예: 수익, 앱 실행 횟수, LTV 등)로, 지표로 분류한 소스의 모든 숫자 데이터 필드가 될 수 있습니다.

<div id="extracting-metrics-from-event_value" />

#### **event\_value에서 지표 추출**

[리포트 측정기준](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions)과 마찬가지로, **event\_value** 필드에서 인앱 이벤트 파라미터를 추출하여 리포트의 지표로 사용할 수 있습니다.

**DCR 리포트에서 사용하도록 event\_value 필드에서 측정기준을 추출하려면 다음을 수행하세요.**

1. **소스의 지표** 목록에서 <Image alt="extract_metric_button.png" src="https://files.readme.io/93ca5970968816d452331df4ce5ff4cfb678cbb24f65eb99fe01bd3bb3016959-10755235273233.png" width="102px" /> 버튼을 클릭합니다.

   **event\_value에서 필드 추출** 창이 열립니다.
2. **리포트 필드** 상자에 리포트에 표시하려는 추출된 메트릭의 이름을 입력합니다.
3. **Event\_value 파라미터** 목록에서 2단계에서 정의한 리포트 필드(지표)에 기본적으로 매핑해야 하는 인앱 이벤트 파라미터를 선택합니다.
   * 사용 가능한 파라미터에는 **선택한 앱**의 **선택한 인앱 이벤트**에서 구성된 파라미터가 포함됩니다.
4. 기본 매핑은 앱 및/또는 이벤트에 따라 다를 수 있습니다. 이 경우에는 다음을 수행하세요.
   1. **예외 추가** 버튼을 클릭합니다.
   2. 리포트 필드를 다르게 매핑해야 하는 앱과 이벤트를 선택합니다.
   3. 이 앱/이벤트 조합에 대한 리포트 필드에 매핑해야 하는 인앱 이벤트 파라미터를 선택합니다.
   4. 설정하려는 예외 횟수에 대해 다음 단계를 수행합니다.
5. 추출된 지표에 대한 매핑 설정을 마치면 **저장 및 다른 지표 추가**를 클릭하여 event\_value 필드에서 다른 지표를 추출하거나 **저장**을 클릭하여 기본 화면으로 돌아갑니다.

**추출된 지표를 편집하는 방법은 다음과 같습니다.**

1. **소스의 지표** 또는 **리포트 지표** 목록에서 편집하려는 지표 이름을 마우스로 가리킵니다.
2. 지표 오른쪽에 표시되는 <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> 버튼을 클릭합니다.
3. **추출된 필드 편집**을 선택합니다.
4. 필요에 따라 **리포트 필드** 이름 및/또는 파라미터 매핑을 변경합니다.
5. 변경 사항을 저장하려면 **저장**을 클릭합니다.

**추출된 지표를 삭제하는 방법은 다음과 같습니다.**

1. **소스의 지표** 또는 **리포트 지표** 목록에서 삭제하려는 지표 이름을 마우스로 가리킵니다.
2. 지표 오른쪽에 표시되는 <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> 버튼을 클릭합니다.
3. **필드 삭제**를 선택합니다.
   * **주의!** **리포트 지표** 목록에서 추출된 필드를 삭제하면 추출된 필드의 정의도 삭제됩니다. 정의를 보존하면서 리포트에서 필드를 제거하려면 필드를 선택하고 대신 **제거** 버튼을 사용하세요.

<div id="select-report-metrics" />

#### **리포트 지표 선택**

**리포트에 포함할 지표를 선택하는 방법은 다음과 같습니다.**

1. 왼쪽에 있는 **소스의 지표** 목록에서 하나 이상의 지표를 선택하고 화면 중앙에 있는 **추가** 버튼을 사용하여 이들 지표를 **리포트 지표** 목록에 추가합니다.
   * 검색 창을 사용하여 목록에서 지표를 검색할 수 있습니다.
2. **리포트 지표** 목록의 각 지표에 대해 데이터를 다음 중 하나로 리포트할지 선택합니다.
   * 숫자 값의 합계, 또는
   * 고유 값의 개수
3. 지표를 제거하려면 **리포트 지표** 목록에서 해당 지표를 선택한 다음 **제거** 버튼을 사용하여 **소스의 지표** 목록으로 되돌립니다.
4. 리포트에 포함하려는 각 지표를 추가할 때까지 이 과정을 반복합니다.

<div id="optional-customizing-metric-display-names" />

#### **[선택 사항] 지표 표시 이름 사용자 지정**

기본적으로, 지표 이름은 인앱 이벤트 데이터 또는 사용자 지정 소스에 이름이 지정된 그대로 정확히 리포트에 표시됩니다. 원한다면 리포트의 지표 이름을 사용자 지정할 수 있습니다.

**지표 표시 이름을 사용자 지정하는 방법은 다음과 같습니다.**

1. **리포트 지표** 목록에서 표시 이름을 편집하려는 지표의 이름을 마우스로 가리킵니다.
2. 지표 오른쪽에 표시되는 편집 버튼 ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png)을 클릭합니다.
3. 이름을 리포트에 사용할 지표 표시 이름(최대 50자)으로 변경합니다.
4. 표시 이름을 저장하려면 **확인**을 클릭하고 취소하려면 **X**를 클릭합니다.

**참고:** **추출된 지표**의 이름을 변경하려면 위에서 추출한 지표를 편집하는 단계를 따르세요.

<div id="optional-select-identifiers-to-count" />

#### **[선택 사항] 계산할 식별자 선택**

기본적으로, 리포트의 각 행은 해당 행의 데이터에서 그룹화된 고유한 앱스플라이어 ID의 수를 포함하는 열로 끝납니다.

**소스에서 다른 식별자의 고유 개수에 대한 열을 추가하려면 다음과 같이 추가하세요.**

1. 왼쪽에 있는 **소스의 식별자** 목록에서 하나 이상의 식별자를 선택하고 화면 중앙에 있는 **추가** 버튼을 사용하여 이들 지표를 **고유 카운트 식별자** 목록에 추가합니다.
   * 검색 창을 사용하여 목록에서 식별자를 검색할 수 있습니다.
2. 식별자를 제거하려면 **고유 카운트 식별자** 목록에서 해당 식별자를 선택하고 **제거** 버튼을 사용하여 **소스의 식별자** 목록으로 되돌립니다.
3. 리포트에 계산하려는 각 식별자를 추가할 때까지 이 과정을 반복합니다.

</Accordion>

<div id="configure-report-settings-and-save-the-report" />

<Accordion title="리포트 설정 구성 및 리포트 저장">

<div id="schedule-only-for-reports-without-custom-sources" />

#### **일정(사용자 지정 소스가 없는 리포트에만 해당)**

사용자 지정 소스가 없는 리포트는 사용자가 정의한 일정에 따라 실행됩니다.

**리포트 일정을 정의하는 방법은 다음과 같습니다.**

1. 리포트를 매일 실행할지 아니면 일주일에 하루 이상 실행할지를 선택합니다.
2. 리포트를 실행할 시간을 선택합니다(시간대는 UTC임).

<div id="important-1" />

> 🚧 **중요!**
>
> 예약 옵션은 사용자 지정 소스를 사용하는 리포트에 대해 사용할 수 없습니다. 이 유형의 리포트는 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-creating-attribution-data-reports#사용자-지정-소스">사용하는 모든 사용자 지정 소스</Anchor>의 새 버전이 감지될 때마다 실행됩니다.
>
> * **데이터 웨어하우스**(BigQuery 및 Snowflake)에 있는 소스의 경우 DCR은 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#table-columns">`v`소스 테이블의 열</Anchor>에서 새 값을 감지하면 소스의 새 버전이 생성되었음을 인식합니다.
>   * **중요!** 리포트의 완전성을 보장하려면 열 값이 변경될 때마다 원본 테이블을 전체 데이터 집합으로 채워야 합니다.
> * **클라우드 스토리지 버킷**(Amazon S3 및 GCS)에 위치한 소스의 경우, DCR은 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#리포트-처리를-트리거하기-위한-소스-업데이트">소스 파일의 새 버전</Anchor>이 수반되는 \_SUCCESS 파일과 함께 업로드된 것을 감지하면 소스의 새 버전이 생성되었음을 인식합니다.
>
> 앱스플라이어는 **현재 날짜와 2일 전**에 대한 새 버전의 소스를 지속적으로 검색합니다.

<div id="report-destination" />

#### **리포트 대상**

DCR은 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">앱스플라이어 데이터 락커</Anchor>를 사용하여 선택한 클라우드 서비스에 리포트를 제공합니다. 따라서 리포트 대상을 지정하려면 데이터 락커 연결을 선택하거나 만들어야 합니다.

* **참고:** DCR 리포트를 수신하는 데 데이터 락커에 대한 프리미엄 구독이 필요하지 않습니다. 데이터 락커를 통해 다른 앱스플라이어 리포트를 수신하려면 CSM에 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)으로 이메일을 보내주십시오.

**리포트 대상을 설정하고 리포트를 저장하는 방법은 다음과 같습니다.**

1. 앱스플라이어 계정에서 사용할 수 있는 데이터 락커 연결 목록에서 선택합니다.
   * 계정에 정의된 연결이 없는 경우:
     * 브라우저에서 새 탭이 열립니다(앱스플라이어 데이터 락커 페이지 표시).
     * **새로운 연결** 대화 상자가 열립니다. <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections#참고사항">다음 지침</Anchor>에 따라 연결을 생성합니다.
   * 기존 연결이 있지만 새로운 연결을 사용하려면 ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) 버튼을 클릭하세요.
     * 브라우저에서 새 탭이 열립니다(앱스플라이어 데이터 락커 페이지 표시).
     * **새로운 연결** 대화 상자가 열립니다. <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections#참고사항">다음 지침</Anchor>에 따라 연결을 생성합니다.
   * 연결을 만든 후 브라우저의 DCR 탭으로 돌아가서 데이터 락커 연결 목록에서 새로 만든 연결을 선택합니다.
2. **저장**을 클릭하여 리포트를 저장합니다.
3. 이제 새로운 리포트가 **데이터 클린룸**의 **리포트** 탭에 표시됩니다.

</Accordion>

<div id="reference" />

## 참고

<div id="default-inapp-event-dimensions" />

<Accordion title="기본 인앱 이벤트 측정기준">

**event\_value**에서 추출한 측정기준과 사용자 지정 소스의 측정기준(해당되는 경우) 외에도, 다음 인앱 이벤트 측정기준을 사용하여 리포트를 그룹화할 수 있습니다.

* media\_source*([기본적으로 리포트 측정기준으로 포함됨](#리포트-측정기준-선택))*
* ad
* ad\_id
* ad\_type
* adset\_id
* adset\_name
* app\_id
* app\_version
* attributed\_touch\_type
* brand
* campaign
* campaign\_id
* channe
* 도시
* conversion\_type
* country
* device\_type
* dma
* engagement\_type
* event\_name
* 이벤트 수익 통화
* geo\_region
* is\_attributed
* 키워드
* match\_type
* model
* partner
* platform
* site\_id

</Accordion>

<div id="default-inapp-event-metrics" />

<Accordion title="기본 인앱 이벤트 지표">

**event\_value**에서 추출한 지표와 사용자 지정 소스의 지표(해당되는 경우) 외에도, 다음과 같은 인앱 이벤트 지표를 리포트에 포함할 수 있습니다.

* event\_revenue
* event\_revenue\_u\_s\_d

</Accordion>

<div data-zendesk-anchors="creating-an-inapp-event-report=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HA9W7NP4CR9CVXY9CXENYSPF=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HA9W7NP4B55Y2SB6ADKE06JV=perform-preliminary-steps h_01HA9W7NP4A7YK5JFYNFXFY6ZJ=select-sources inapp-event-sources=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%86%8C%EC%8A%A4 h_01HA9W7NP4G0S2TQT9W2RK1QBA=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%86%8C%EC%8A%A4 custom-sources=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 h_01HA9W7NP46D57Q7H8611K4KBB=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 h_01HA9W7NP4K2055TXTE98HWTAW=join-sources-only-for-reports-containing-custom-sources what-is-a-key-identifier=%ED%82%A4-%EC%8B%9D%EB%B3%84%EC%9E%90%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HA9W7NP4WTBJ83MY73JQ2ESH=%ED%82%A4-%EC%8B%9D%EB%B3%84%EC%9E%90%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HA9W7NP5N8W4X8H1WRN1183Z=%EC%A4%91%EC%9A%94 mapping-schemes-directindirect=%EB%A7%A4%ED%95%91-%EC%8A%A4%ED%82%A4%EB%A7%88%EC%A7%81%EC%A0%91%EA%B0%84%EC%A0%91 h_01HA9W7NP51HWA36BBP1JC3HMW=%EB%A7%A4%ED%95%91-%EC%8A%A4%ED%82%A4%EB%A7%88%EC%A7%81%EC%A0%91%EA%B0%84%EC%A0%91 h_01HA9W7NP5V1SV5PGF277G5P6T=%EC%98%88%EC%8B%9C h_01HA9W7NP56M09TF9CB7FCBPBR=select-dimensions extracting-dimensions-from-event_value=event_value%EC%97%90%EC%84%9C-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%B6%94%EC%B6%9C h_01HA9W7NP5BV7GJXMEMS57HNJ9=event_value%EC%97%90%EC%84%9C-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%B6%94%EC%B6%9C selecting-report-dimensions=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%84%A0%ED%83%9D h_01HA9W7NP5S6EWDE38Q6T42QEB=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%84%A0%ED%83%9D %5Boptional%5D-customizing-dimension-display-names=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%ED%91%9C%EC%8B%9C-%EC%9D%B4%EB%A6%84-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95 h_01HA9W7NP5YC8E3B05GV7J1Z5V=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%ED%91%9C%EC%8B%9C-%EC%9D%B4%EB%A6%84-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95 preserving-privacy-while-grouping-by-dimension-regrouping=%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80%EB%B3%84%EB%A1%9C-%EA%B7%B8%EB%A3%B9%ED%99%94%ED%95%98%EB%8A%94-%EB%8F%99%EC%95%88%EC%9E%AC%EA%B7%B8%EB%A3%B9%ED%99%94-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01HA9W7NP5XJGK4CXNHK02NYT4=%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80%EB%B3%84%EB%A1%9C-%EA%B7%B8%EB%A3%B9%ED%99%94%ED%95%98%EB%8A%94-%EB%8F%99%EC%95%88%EC%9E%AC%EA%B7%B8%EB%A3%B9%ED%99%94-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01HA9W7NP596RGHA1BES64GSK1=%EC%9E%AC%EA%B7%B8%EB%A3%B9%ED%99%94-%EC%98%88 %5Boptional%5D-managing-dimension-priority=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84-%EA%B4%80%EB%A6%AC h_01HA9W7NP5781HV31T5DAYSMMT=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%B8%A1%EC%A0%95%EA%B8%B0%EC%A4%80-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84-%EA%B4%80%EB%A6%AC h_01HA9W7NP6WCSRSH157P78QEQF=select-metrics extracting-metrics-from-event_value=event_value%EC%97%90%EC%84%9C-%EC%A7%80%ED%91%9C-%EC%B6%94%EC%B6%9C h_01HA9W7NP6JEXE67A935BJ93AQ=event_value%EC%97%90%EC%84%9C-%EC%A7%80%ED%91%9C-%EC%B6%94%EC%B6%9C select-report-metrics=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%A7%80%ED%91%9C-%EC%84%A0%ED%83%9D h_01HA9W7NP6EF23ZDGZHDKVTS7V=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%A7%80%ED%91%9C-%EC%84%A0%ED%83%9D %5Boptional%5D-customizing-metric-display-names=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%A7%80%ED%91%9C-%ED%91%9C%EC%8B%9C-%EC%9D%B4%EB%A6%84-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95 h_01HA9W7NP6X584YAXT030A6BEY=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EC%A7%80%ED%91%9C-%ED%91%9C%EC%8B%9C-%EC%9D%B4%EB%A6%84-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95 %5Boptional%5D-select-identifiers-to-count=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EA%B3%84%EC%82%B0%ED%95%A0-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%84%A0%ED%83%9D h_01HA9W7NP6YETQ1ND0K8XZTZZ0=%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EA%B3%84%EC%82%B0%ED%95%A0-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%84%A0%ED%83%9D h_01HA9W7NP6ZH3KRN7YNWCPFZC9=configure-report-settings-and-save-the-report schedule-only-for-reports-without-custom-sources=%EC%9D%BC%EC%A0%95%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%86%8C%EC%8A%A4%EA%B0%80-%EC%97%86%EB%8A%94-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HA9W7NP62DCR2SWD8X4M61R7=%EC%9D%BC%EC%A0%95%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%86%8C%EC%8A%A4%EA%B0%80-%EC%97%86%EB%8A%94-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HA9W7NP6XQE1MN0J08FE89V4=%EC%A4%91%EC%9A%94-1 report-destination=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8C%80%EC%83%81 h_01HA9W7NP6BQYAF3RMZSW747HH=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%8C%80%EC%83%81 reference=%EC%B0%B8%EA%B3%A0 h_01HA9W7NP6BS0TE332GNPTW9M1=%EC%B0%B8%EA%B3%A0 h_01HA9W7NP606HF0MSPQ4S09YRS=default-inapp-event-dimensions h_01HA9W7NP6A1N25KQ947J3EJW3=default-inapp-event-metrics" />
