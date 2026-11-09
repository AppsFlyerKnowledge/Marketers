---
title: 오디언스(Audiences) 가이드
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-10-14T10:32:34Z'
  id: 115002689186
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 앱스플라이어 오디언스를 사용하여 오디언스가 세그먼트를 구축하고 파트너 네트워크에 연결함으로써 사용자 인입 및 리마케팅 캠페인의 효율성을 높입니다.

<Image align="center" alt="Intro_image.png" src="https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png" />

<div id="audiences-basics" />

## 오디언스 기반

앱스플라이어 오디언스를 사용하면 오디언스 세그먼트를 쉽게 구축하고 이를 소유 채널과 유료 채널에 연결할 수 있으므로, 더 나은 인게이지먼트와 성과를 위한 맞춤형 캠페인을 제공할 수 있습니다. 캠페인이 전송되면 오디언스에서도 성과 지표를 볼 수 있습니다.

오디언스는 사용자가 정의하는 특정 기준을 충족하는 앱의 현재 또는 과거 사용자의 세그먼트입니다. 오디언스는 개인적 특성, 행동, 인앱 액티비티, 어트리뷰션 소스, 생성된 수익, 지리적 위치, 기기 유형 등을 기반으로 할 수 있습니다.

**1단계 - 앱스플라이어에서 오디언스 구축:** 맞춤 오디언스를 처음부터 구성하거나, 하나를 가져오거나, 또는 사용자 정의가 가능한 기존의 "추천 오디언스 목록에서 선택할 수 있습니다. 이 목록은 시간을 절약하고 업계 모범 사례를 기반으로 합니다.

**2단계 - 오디언스 연결:** 오디언스를 구축했다면, 다음 단계는 오디언스를 앱스플랄이어 내에서 미디어 파트너에 연결하는 것입니다. 그러면 해당 오디언스 구성원에 대한 식별자가 파트너에게 전송되고 파트너 시스템에 오디언스가 생성됩니다. 이를 통해 이러한 사용자에게만 특정 광고를 제공할 수 있습니다. 오디언스는 매일 한 번 자동으로 새로고침되어 파트너에게 푸시됩니다. 또한 오디언스를 Amazon S3 버킷과 같은 타사 서비스에 업로드하거나 대시보드에서 바로 CSV 파일로 다운로드할 수 있습니다.

오디언스가 데이터를 미디어 파트너에게 업로드하는 데 필요한 모든 정보는 파트너 연결에 지정되어 있습니다. 단일 미디어 파트너에 대해 다중 연결을 사용할 수 있습니다(다른 계정, 로그인 정보 등의 사용). iOS 14.5의 프라이버시 요구 사항 및 기타 사용자의 프라이버시 고려사항을 준수할 수 있도록 하기 위해, **오디언스를 통해 계정 수준 및 각 파트너 연결에서 파트너와 공유하는 식별자 결정에 대해 완전히 제어할 수 있습니다**.

<div id="audience-split-and-incrementality-testing" />

### 오디언스 분할 및 성과 증분 테스트

<Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview">성과 증분</Anchor> 테스트에서는 "성과 증가분"(마케팅 캠페인의 결과로 발생한 전환과 어쨌든 발생했을 전환 사이의 차이)을 정확하게 측정하는 A/B 테스트를 통해 캠페인의 실제 영향을 측정합니다. 앱스플라이어 잠재 고객은 선택한 미디어 파트너와 대조군 간에 잠재 고객을 분할하는 옵션 기능으로 테스트의 단계를 설정하므로, 성과 증분 대시보드를 사용하여 캠페인의 진정한 가치를 이해할 수 있습니다.

<div id="get-started" />

## 시작하기

다음 단계를 따라 오디언스 관련 작업을 시작하세요.

|  | 단계 |
| --- | --- |
| 1 | 앱스플라이어의 측면 메뉴에서 **인게이지먼트** > **오디언스**를 선택합니다.<br /><br />**참고:** 오디언스는 프리미엄 기능입니다. 오디언스를 시작하는 데 도움이 필요하면, 고객 성공 담당자에게 문의하거나 **hello@appsflyer.com**으로 메일을 보내주세요. |
| 2 | 사용자 식별자를 파트너와 공유하기 위한 계정 수준 <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">정책</Anchor> 설정 |
| 3 | 새 오디언스 생성:<ul><li>[커스텀 오디언스](/docs/audiences-guide#create-a-custom-audience) - 오디언스를 처음부터 구축</li><li>[추천 오디언스](/docs/audiences-guide#create-a-suggested-audience)   - 업계 모범 사례를 기반으로 이미 등록한 맞춤형 오디언스</li><li><Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems">오디언스 가져오기</Anchor> - 내부 시스템(예: BI 또는 CRM)에서 오디언스 세그먼트를 가져오기</li></ul> |
| 4 | 오디언스를 하나 이상의 미디어 파트너에 연결 |
| 선택 가능 | [오디언스를 파트너와 대조군으로 분할](/docs/audiences-guide#audience-split-and-control-groups) |
| 선택 가능 | <Anchor target="_blank" href="/marketers/ko/docs/audiences-create-better-audiences-with-user-attribute-data">사용자 어트리뷰트를 가져옵니다.</Anchor> |

<div id="create-and-manage-audiences" />

## 오디언스 생성 및 관리

이 섹션에서는 오디언스를 생성 및 관리하고 증분 테스트를 설정하는 방법에 대해 설명합니다.

<div id="create-a-custom-audience" />

<Accordion title="커스텀 오디언스 생성">

커스텀 오디언스는 원하는 규칙 집합과 필터를 사용하여 처음부터 만들어집니다.

**커스텀 오디언스 생성 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지** > **오디언스**를 선택합니다.
2. **새 오디언스**를 클릭합니다.
3. **커스텀 오디언스**를 선택합니다.  
   **빌드** 탭이 표시됩니다.
4. 고유한 **오디언스 이름**을 입력합니다.  
   **참고:** 오디언스 이름에는 특수 문자(" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)를 포함할 수 없습니다.
5. 플랫폼을 선택합니다. **안드로이드** 또는 **iOS**.
6. [사용자 식별자](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) 선택:
7. [기본값] **디바이스 ID**: 디바이스 ID로만 규칙을 평가합니다.
8. **고객 ID**: CUID를 사용해 기기를 그룹화하여 규칙 평가를 적용합니다. (데이터가 유효한 CUID를 가지고 있는지 확인한 후에 이 방법을 사용합니다.)
9. **새 규칙 세트**를 선택하거나 기존 오디언스인 사용자를 추가하려면 **기존 오디언스**를 클릭한 다음 목록에서 특정 오디언스를 선택합니다.
10. 사용자 인터페이스의 안내에 따라 오디언스를 빌드합니다. 규칙 옵션에 대한 구체적인 정보는 [모든 규칙 집합](/docs/audiences-guide#규칙-집합에-대한-모든-것)을 참조하십시오.
11. 연산자(and, or, exclude)를 사용하여 규칙 집합을 결합합니다.
12. 오디언스를 구축하면 오른쪽에 있는 창에 예상 오디언스 및 파트너별 업로드 크기가 자동으로 업데이트됩니다.
13. 오디언스 정의를 완료하고 **다음**을 클릭합니다.  
    **오디언스 연결** 창이 나타납니다. 여기에서 [오디언스를 미디어 파트너와 연결합니다](/docs/audiences-guide#connect-an-audience-to-media-partners).

<div id="notes" />

> 📘 **참고**
>
> * 한 번에 최대 100개의 활성 맞춤/추천 오디언스를 보유할 수 있습니다.
> * 오디언스 이름은 연결된 미디어 파트너 사이트에서 볼 수 있습니다. 이름에 민감한 정보를 포함하지 마십시오.

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="추천 오디언스 생성">

추천 오디언스를 사용하면 **업계 모범 사례를 기반으로 하는 미리 구성된 오디언스 세그먼트를 탐색하고 발견할 수 있습니다.** 오디언스를 선택하고 사용자 지정하고 파트너 네트워크와 연결하여 최적의 타겟 마케팅 캠페인을 수행할 수 있습니다.

**인입, 활성화, 인게이지, 현금화 및 산업별 오디언스의 범주 내에서 30명 이상의 오디언스 중에서 선택하세요.** 오디언스는 100% 사용자 정의가 가능하므로 필요한 오디언스를 정확하게 만들 수 있습니다. 오디언스에는 다음이 포함됩니다.

* 광고 클릭 유저를 설치 사용자로 전환
* 닮은꼴 얻기
* 금지 목록
* 등록 장려
* 구매 유도
* 구매자 수익화
* 그 외 다수

<div id="example-use-case" />

> 📄 **사용 사례 예시**
>
> 이 예에서는 하나의 일반적인 사용 사례를 보여줍니다. 아직 구매하지 않은 활성 앱 사용자의 첫 구매를 유도하고 싶다고 가정해 보겠습니다. "구매 유도" 오디언스를 선택하고 인앱 구매를 정의하는 이벤트를 지정하도록 사용자 지정할 수 있습니다. 그런 다음 오디언스를 파트너와 연결하고 구매를 유도하고 앱의 구매 페이지로 안내하는 프로모션 캠페인을 실행할 수 있습니다.
>
> <Image align="center" alt="Encourage_purchase_image_this_one.jpeg" src="https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg" />

**추천 오디언스 생성 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지** > **오디언스**를 선택합니다.
2. **새 오디언스**를 클릭합니다.
3. **추천 오디언스**를 선택합니다.
4. 앱을 선택합니다.
5. 다양한 카테고리를 탐색하고 목표와 일치하는 오디언스를 선택합니다.    
   **참고:** 일부 오디언스의 경우 특정 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트</Anchor>를 추가하여 오디언스 기준을 정의해야 합니다. 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#사전-정의된-이벤트-이름">사전 정의한 이벤트</Anchor>가 앱에서 이미 구성된 경우에는 미리 선택됩니다. 그렇지 않으면 드롭다운 메뉴에서 적절한 사용자 정의 이벤트를 선택해야 합니다. <Image alt="Select_an_event__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />
6. **선택 및 맞춤설정**을 클릭합니다.
7. 고유한 **오디언스 이름**을 입력합니다.  
   **참고:** 오디언스 이름에는 특수 문자(" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)를 포함할 수 없습니다.
8. 플랫폼을 선택합니다. Android 또는 iOS.
9. [사용자 식별자](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) 선택:
   * [기본값] **디바이스 ID**: 디바이스 ID로만 규칙을 평가합니다.
   * **고객 ID**: CUID를 사용해 기기를 그룹화하여 규칙 평가를 적용합니다. (데이터가 유효한 CUID를 가지고 있는지 확인한 후에 이 방법을 사용합니다.)
10. 추가 [규칙 세트](/docs/audiences-guide#규칙-집합에-대한-모든-것)를 추가하여 오디언스를 추가로 사용자 정의하려면 **+ 필터**를 클릭하여 그렇게 할 수 있습니다. 완료되면 **다음**을 클릭합니다.   
    **오디언스 연결** 창이 나타납니다. 여기에서 [오디언스를 미디어 파트너와 연결합니다](/docs/audiences-guide#connect-an-audience-to-media-partners).

<div id="notes-1" />

> 📘 **참고**
>
> * 한 번에 최대 100개의 활성 맞춤/추천 오디언스를 보유할 수 있습니다.
> * 오디언스 이름은 연결된 미디어 파트너 사이트에서 볼 수 있습니다. 이름에 민감한 정보를 포함하지 마십시오.

</Accordion>

<div id="import-an-audience" />

<Accordion title="잠재 고객을 가져옵니다.">

내부 시스템(BI 및 CRM 등)에서 <Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems">미리 정의된 오디언스 세그먼트</Anchor> 를 앱스플라이어 오디언스로 가져올 수 있으며 광고 파트너와 모든 오디언스 세그먼트를 연결하고 유지하기 위한 중심점으로 사용할 수 있습니다. 또한 식별자 일치/데이터 보강 및 연결된 캠페인 지표와 같은 오디언스 기능을 사용할 수 있습니다.

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="오디언스를 미디어 파트너에 연결">

오디언스를 정의한 후 다음 단계는 오디언스를 미디어 파트너에 연결하는 것입니다.

**오디언스를 미디어 파트너에 연결하는 방법:**

1. 오디언스 **구성** 페이지에서 새 오디언스를 정의한 후 **다음**을 클릭합니다. **오디언스 연결** 창이 나타납니다.
2. **+ 파트너 연결**을 클릭하고 다음 중 하나를 수행합니다.
   * **새 연결을 추가하려면** **+ 파트너 연결 추가**를 클릭합니다(자세한 지침은 아래 [새 연결 생성](/docs/audiences-guide#create-a-new-connection) 참조).
   * **기존 연결에서 선택하는 방법:**
     1. 파트너 연결을 검색합니다.
     2. 하나 이상의 기존 연결을 선택합니다.
     3. **저장**을 클릭하세요.  
        오디언스 연결 창이 열립니다.
     4. [선택 사항] [오디언스를 파트너와 대조군으로 분할합니다.](/docs/audiences-guide#audience-split-and-control-groups)
     5. [선택 사항] [분할 그룹을 S3에 복사합니다](/docs/audiences-guide#audience-split-and-control-groups).
3. **저장**을 클릭하세요.  
   연결되면 오디언스가 업데이트되고 매일 파트너에게 푸시됩니다.

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="사용자 식별자 - 디바이스 ID vs. 고객 ID">

오디언스 룰 평가 적용은 앱 사용자 식별자를 사용하여 이루어집니다. 아래에서 선택하세요.

* [기본값] **디바이스 ID:** 규칙 세트 준수는 디바이스 ID(GAID 또는 IDFA/IDFV)를 사용하여 평가됩니다. 규칙 세트를 준수하는 경우, 해당 디바이스 ID는 오디언스 목록에 추가됩니다. **참고:** 디바이스 ID는 사용자 식별자 정책에서 허용하는 경우에만 파트너와 공유합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">**고객 ID(CUID)**</Anchor>:
  * 동일한 CUID에 연관된 모든 디바이스 ID를 그룹화하여, 이것이 규칙 세트에 준수하는지 평가 적용이 이루어집니다. 만약 이 그룹이 규칙 집합을 따르는 경우, 이 그룹을 구성하는 디바이스 ID들이 오디언스에 추가됩니다. **참고**: CUID 자체는 오디언스 목록의 일부가 아니며 미디어 파트너에게 전송되지 않습니다.
  * CUID 구현 고려 사항:
    * 데이터가 유효한 CUID를 가지고 있는지 확인합니다.
    * CUID가 없는 앱 사용자(디바이스)는 무시됩니다.
    * 디바이스 ID가 CUID에 매칭되면, 해당 사용자에 대한 과거 오디언스 데이터가 소급하여 업데이트되며, 앞으로 구성하는 오디언스에 포함됩니다. **참고**: 로우 데이터는 변경되지 않습니다.
    * 디바이스 ID가 두 개의 서로 다른 CUID와 연결된 경우 가장 최근에 연결된 CUID가 사용됩니다.
    * CUID를 식별자로 사용하여 오디언스를 구축할 때, 관련 디바이스와의 완전한 연결과 디바이스 식별자(즉 GAID, IDFA)를 통한 성공적인 보강을 위해 앱스플라이어가 설치 시(설치 후 이벤트 발생 시가 아니라) CUID 연결을 수신했음에 틀림없습니다. <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">더 알아보기</Anchor>

<Image align="center" alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

<div id="example-device-id-vs-cuid" />

> 📄 **예시 디바이스 ID vs. CUID**
>
> 5달러 이상을 지출한 유저로 구성된 오디언스
>
>
>
> | 광고  <br />ID | CUID | 구매 $ |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | 없음 | 50 |
>
>
>
> | 규칙 평가 | 오디언스에 포함된 디바이스 ID | 설명 |
> | --- | --- | --- |
> | 디바이스 ID | B, D | A와 C는 포함되지 않았습니다 - 지출이 $5 미만입니다. |
> | CUID | A, B, C | * A와 C는 동일한 CUID(99)를 가지고 있습니다 - 총합한 지출은 $6입니다.<br />* D는 무시되었습니다 - CUID가 없습니다. |
>
>
>
> **<span id="h_01K0PAQ4SFXBK0TZ3MH07PWN4A"></span>참고**
>
> 위의 예에서 보여준 CUID로 그룹화된 장치 ID에 걸쳐 지출을 합산하는 동일한 방법은 다른 수치 속성(예: 점수 매기기)에도 적용됩니다.



</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="오디언스 분할 및 대조군">

파트너와 대조군 간에 오디언스를 분할하는 토글을 사용하여 A/B 테스트 및 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview">증분율 측정</Anchor>을 위한 단계를 손쉽게 설정하여 캠페인 영향에 대해 필요한 중요한 통찰을 얻을 수 있습니다. 이 기능을 활성화하면 선택한 파트너와 대조군 간에 오디언스를 무작위로 분할할 수 있습니다. 대조군은 파트너로부터 보류되는 오디언스의 일부이며 증분율 측정에 필요한 요구 사항입니다. 원하는 분할 비율을 조정하고 오디언스별로 분할을 비활성화하거나 다시 활성화할 수 있습니다.

| 기능 | 설명 |
| --- | --- |
| 분할 오디언스 | <ul><li>이 기능으로 선택한 파트너와 대조군 간에 오디언스를 무작위로 분할할 수 있습니다. **이 기능은 증분율 구독자에 대해 기본적으로 활성화되며** 언제든지 쉽게 비활성화하거나 다시 활성화할 수 있습니다.</li><li>A/B 테스트 및 증분율 측정과 같은 다양한 이유로 오디언스를 분할합니다.</li><li>**참고:** 파트너 간의 기존 분할 할당을 수정하면 전체 오디언스가 다시 배포됩니다. 이로 인해 A/B 테스트의 유효성에 부정적인 영향을 미칠 수 있으며 활성 증분율 실험이 종료되고 새 실험으로 다시 시작됩니다.</li></ul> |
| 대조군 | 오디언스의 일부는 대조군으로 보내지며 파트너에게는 보내지 않습니다.<ul><li>대조군은 A/B 테스트에서 사용되며 마케팅 캠페인의 성과 증가분을 측정합니다.</li><li>효과적인 통제군을 위해 오디언스의 15% 이상이 권장됩니다.</li><li>증분율 실험을 실행하는 데 필요한 최소 대조군 %는 1%입니다.</li></ul> |
| 분할 목록의 복사본을 S3 버킷에 보냅니다. | 분할된 오디언스 목록과 대조군을 포함한 CSV 파일은 Amazon S3 버킷에 전송될 수 있습니다.<ul><li>**참고**: 이것은 Amazon S3를 연결된 파트너로 정의하는 것과 다릅니다.</li><li>오디언스 목록은 CSV 파일로 다운로드할 수 있습니다. 이 CSV 파일을 사용하여, 예컨대 앱스플라이어에 연동하지 않은 파트너에게 보낼 수 있습니다.</li></ul> |

**오디언스를 분할하고 다른 파트너 작업을 수행하는 방법:**

1. 앱스플라이어 왼쪽 패널에서 **참여** > **오디언스**로 이동합니다.
2. **오디언스** 탭에서 오디언스를 선택합니다.
3. **연결** 탭으로 이동합니다.  
   [![audience_split_1200px.png](https://support.appsflyer.com/hc/article_attachments/30258966527249)](https://support.appsflyer.com/hc/article_attachments/30258966527249) 현재 설정 표시:  
   * 맨 위 오른쪽 창에는 (모든 파트너의) 예상 총 오디언스 및 업로드 크기가 표시됩니다.
   * 오른쪽 하단에는 다음이 시각적으로 표시됩니다.
     * 각 파트너별 예상 업로드 크기
     * 파트너 겹침(분할되지 않은 오디언스의 경우)
4. 다음 작업 중 하나를 수행하십시오.

<Table>
  <thead>
    <tr>
      <th>
        작업
      </th>
      <th>
        절차
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        오디언스를 파트너와 대조군으로 분할합니다.
      </td>
      <td>
        1. **오디언스 분할/증분 영향 측정** 토글이 활성화되어 있는지 확인합니다.
           * 대조군과 결합된 파트너로 분할된 그룹 총계는 100%여야 합니다.
           * 분할에 대조군을 포함하지 않으려는 경우 0%를 할당하십시오.
           * 연결된 모든 파트너에 분할의 일부를 할당해야 합니다(파트너에 0%를 할당하면 안 됨).
           * 할당된 총계를 보려면 화면을 아래로 이동하면 총 분할 백분율이 표시됩니다.
        2. 다음의 대상들에 할달됭 백분율을 다음과 같이 입력합니다.
           * **대조군 -** 15% 이상이 권장됩니다.
           * 연결당 분할 백분율을 입력하십시오.
           * 아래로 스크롤하여 백분율로 표시된 총 할당량을 표시하고 총 할당량이 100%인지 확인합니다.
           * **분할 저장**을 클릭하십시오.
           * **저장**을 클릭합니다.
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        분할 그룹을 S3에 복사
      </td>
      <td>
        **오디언스 분할 목록의 사본을 S3 버킷으로 전송하려면 다음을 수행하세요.**

        1. **분할 그룹을 S3에 복사**를 클릭합니다.
        2. 연결을 선택합니다.
        3. **저장**을 클릭하세요.

        파일은 다음 디렉토리 및 파일 이름 구조로 전송됩니다.

        * **디렉토리**:

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp\
          ```
        * **파일 이름**: 파트너 또는 대조군의 이름  
          참고: 파트너에 대한 연결이 실패하고 파일이 업로드되지 않은 경우 **실패함**이라는 단어가 파트너 이름에 추가됩니다(예: *partner\_name\_failed.csv*).
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        새 연결을 생성하고 추가합니다.
      </td>
      <td>
        **새 연결을 생성하는 방법은 다음과 같습니다.**

        1. **파트너** **연결** **추가**를 클릭하십시오.
        2. 연결 이름을 입력합니다.
        3. 파트너를 선택합니다.
        4. 사용자 인터페이스의 지침에 따라 프로세스를 완료합니다.
        5. **파트너 연결 추가**를 클릭하십시오.
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        기존 연결을 추가 또는 삭제합니다.
      </td>
      <td>
        **기존 연결을 삭제 또는 추가하는 방법은 다음과 같습니다.**

        1. 파트너 연결을 마우스로 가리킵니다.
        2. "제거" 아이콘을 클릭합니다.
        3. **저장**을 클릭합니다.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="오디언스 관리">

**오디언스 대시보드에서 오디언스 관리:**

1. 앱스플라이어 왼쪽 패널에서 **참여** > **오디언스**로 이동합니다.
2. 다음 옵션이 가능합니다.

| 옵션 | 설명 |
| --- | --- |
| <span id="create-a-new-audience"></span>새 오디언스 생성 | 새 오디언스 생성 |
| <span id="change-audience-settings"></span>오디언스 설정 변경 | **오디언스 이름**을 클릭하고 다음 중 하나를 수행합니다.<ul><li>**빌드** 탭에서 다음을 수행합니다. 규칙 세트를 확인하고 변경합니다.</li><li>**연결** 탭에서 다음을 수행합니다. 오디언스 분할 및 대조군 옵션을 설정합니다.</li></ul> |
| <span id="actions"></span>작업 | 오디언스 메인 페이지에서 오디언스 위로 마우스를 가져갈 때 오른쪽에 표시되는 <Image alt="3_dots_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" /> 아이콘에서:<ul><li>**히스토리 보기**: 오디언스 크기 및 파트너 간 분할을 포함한 오디언스 업로드 기록을 표시합니다.</li><li>**지금 업로드**: 오디언스를 연결된 파트너에게 보냅니다.</li><li>**CSV로 다운로드**:<ul><li>선택한 식별자가 포함된 CSV 파일로 오디언스 목록을 생성하고 다운로드합니다. <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">사용자 식별자 정책</Anchor>을 준수하는 데이터만 다운로드됩니다.</li><li>각 파트너별로 한 개 파일이 생성됩니다.</li><li>오디언스를 계산한 후 파일(들)이 다운로드됩니다. 오디언스를 만들거나 수정한 후 일정한 시간이 걸릴 수 있습니다.</li><li>다운로드되는 파일은 5백만 개의 레코드로 제한됩니다. 더 큰 파일의 경우, 파일을 <Anchor target="_blank" href="/marketers/ko/docs/audiences-partner-connections#amazon-s3">S3 버킷</Anchor>으로 보내십시오.</li><li>파트너 네트워크에 연결된 오디언스만 매일 업데이트되고 최신 상태로 유지됩니다. 오디언스가 파트너 네트워크에 연결되어 있지 않으면 오디언스 생성 날짜 이후에도 최신 상태로 유지되지 않습니다. 최신 정보를 다운로드하려면 오디언스를 복제하여 재생성한 다음(아래 참조) 복제된 오디언스의 CSV를 다운로드할 수 있습니다.</li></ul></li><li>**복제**:<ul><li>오디언스 정의를 복사합니다.</li><li>오디언스를 복제할 때, 고유한 이름을 지정하십시오.</li><li>[선택 사항] 복제 중에 연결된 하나 이상의 파트너를 삭제합니다.</li></ul></li><li>**지금 계산하기**: [가져온 오디언스의 경우] 오디언스의 사용자 수를 다시 계산합니다. 계산 결과가 올바르지 않은 경우, 필요에 따라 새로 고침하십시오.</li><li>**<span id="pause"></span>일시 중지:**</li></ul><ul><li>오디언스를 일시 중지하면 해당 오디언스가 비활성화되어 더 이상 계산되거나 연결된 파트너에게 업로드되지 않습니다.(지난 3년간의 기존 오디언스 데이터는 유지됨)</li><li>사용하지 않는 오디언스를 일시 중지하여 허용된 최대 활성 오디언스 수 이내로 유지할 수 있습니다. 한 번에 최대 100개의 활성 맞춤/추천 오디언스와 최대 500개의 가져온 활성 오디언스를 보유할 수 있습니다.</li></ul>**오디언스를 일시 중지하는 방법:**<ol><li>주 오디언스 페이지의 오디언스 위로 마우스를 가져가면 <Image alt="3 dots icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" />(작업 메뉴) 아이콘이 오른쪽에 나타납니다.</li></ol>![Actions menu.jpg](https://support.appsflyer.com/hc/article_attachments/30258966545297)<ol><li>아이콘을 클릭하고 **일시 중지**를 선택합니다.</li></ol>이제 오디언스가 일시 중지되었습니다.<br /><br />오디언스 옆에 있는 확인란을 선택한 다음 오른쪽 상단에 나타나는 **일시 중지**를 클릭하여 한 번에 여러 오디언스를 일시 중지할 수도 있습니다.<ul><li>**삭제:** 오디언스를 영구적으로 삭제합니다.</li></ul> |
| <span id="bulk-actions"></span>벌크 액션 | 다중 오디언스에 대해 동일한 작업을 수행합니다. 대량 작업을 사용하려면, 둘 이상의 오디언스를 선택하고 다음 대량 작업 중 하나를 선택합니다.<ul><li>**지금 업로드**</li><li>**겹치는 오디언스 표시**: 선택한 오디언스 중에 겹치는 오디언스를 표시합니다.</li><li>**삭제**</li></ul> |

</Accordion>

<div id="all-about-rulesets" />

## 규칙 집합에 대한 모든 것

규칙 세트를 사용하여 오디언스를 정의하는 방법을 알아보세요.

<div id="audience-segmentation-rulesets" />

<Accordion title="오디언스 세그멘테이션 규칙 집합">

<Image align="center" alt="audience_segmentation_rulesets.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018214801" />

* 오디언스 세그먼트 규칙 세트는 정밀 필터링을 활성화하는 하나 이상의 규칙으로 구성됩니다.
* 연산자(and, or, exclude)를 사용하여 룰 세트를 결합합니다.
* 규칙이 정의되고 계층화되면 예상 오디언스 크기가 실시간으로 표시됩니다.
* <Image alt="duplicate_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30258966550033" width="17px" /> 아이콘을 클릭하여 규칙 세트를 복제할 수 있습니다.
* 오디언스가 여러 규칙 집합으로 구성된 경우 중첩 시각화 표시를 사용하면 오디언스 세그먼트를 더 잘 이해할 수 있습니다.
* 규칙 평가를 적용하는 데 사용되는 [사용자 식별자](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)는 디바이스 ID[기본값] 또는 고객 사용자 ID(customer user ID, CUID) 중 하나입니다.

다음 예시에서는 다양한 시나리오에서 규칙 집합 구현을 설명합니다.

</Accordion>

<div id="ruleset-examples" />

<Accordion title="룰 세트 예시">

<div id="example-location-based-rule" />

> 📄 **예: 위치 기반 규칙**
>
> 지난 달에 앱을 삭제한 뉴욕 사용자.
>
> <Image align="center" alt="example_location_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966552209" />

<div id="example-user-attributes-based-rule" />

> 📄 **예: 사용자 특성 기반 규칙**
>
> 최근 7일 동안 1회 이상 앱을 실행하고 가장 좋아하는 무기가 검인 사용자입니다.
>
> <Image align="center" alt="example_user_attributes_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966566801" />

<div id="example-revenue" />

> 📄 **예: 수익**
>
> 지난 7일 동안 앱을 설치하고 $1 을 지출한 사용자.
>
> <Image align="center" alt="example_revenue.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966567825" />

<div id="example-owned-media-filter" />

> 📄 **예: 온드 미디어 필터**
>
> 소셜 미디어(유료 광고 제외), SMS, 이메일, 추천, 웹 또는 QR 코드와 같은 특정 온드 미디어 소스에 어트리뷰트한 사용자로 구성된 타겟 오디언스를 구축합니다. 세분화 수준을 선택하고 특정 미디어 소스, 캠페인, 광고 세트 또는 개별 광고에서 온 사용자를 타겟팅할 수도 있습니다.
>
> 다음은 지난 7일 동안 한 번 이상 앱을 실행하고 특정 이메일 캠페인과 특정 광고 세트 및 광고로 인해 인스톨을 진행한 사용자의 예입니다.
>
> <Image align="center" alt="Owned_media_example.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966580753" />
>
> 오디언스는 온드 미디어 또는 유료 미디어에서 개인화된 메시지로 이러한 사용자를 리인게이지하는 데 사용하거나 캠페인을 실행할 때 관련성이 없거나 불필요한 광고가 표시되지 않도록 제외 목록으로 사용할 수 있습니다.

<div id="example-remarketing" />

> 📄 **예: 리마케팅**
>
> 클릭 및 광고 시청을 사용한 효과적인 리마케팅. 이런 사용자를 전환하려면, 약간의 설득력 또는 부드러운 리마인드가 필요합니다. 이런 사용자는 전환할 확률이 높으므로 이들을 리마케팅하는 것은 새로운 세그먼트에 광고하는 것보다 훨씬 더 좋은 결과를 얻을 수 있습니다. 수집한 클릭과 노출 데이터를 기반으로 리마케팅을 위한 정확한 오디언스를 생성합니다.
>
> 지난 2 일 동안, 광고를 클릭했지만 인스톨은 하지 않은 잠재 사용자에 대한 오디언스를 작성합니다.
>
> <Image align="center" alt="example_remarketing.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018231313" />
>
> 이들은 최근에는 광고를 클릭할 만큼 해당 모바일 앱에 관심이 있었지만, 어떤 이유로 앱을 설치하지 않았습니다. 또는 앱을 설치했으나 아직 실행하지 않았습니다. 일부 유저는 이 앱을 인스톨 하라는 리마인더(푸시)만 단지 필요할 뿐입니다. 다른 유저는 최종적으로 전환시키려는 앱에 대한 추가 화면이나 기능 설명이 필요할 수도 있습니다. 그러므로, 신규 오디언스에 대한 주요 광고 소재가 있다면, 광고를 클릭했으나 설치 하지 않은 오디언스에게는 다른 광고 소재를 사용하는 것이 좋을 수 있습니다.

</Accordion>

<div id="ruleset-filters" />

<Accordion title="규칙 세트 필터">

* 규칙 세트는 하나 이상의 규칙으로 구성됩니다.
* 규칙 세트는 이벤트, 수익, 지역, 어트리뷰션, 사용자 어트리뷰트, 디바이스 및 온드 미디어 등 다양합니다.
* 규칙은 아래 테이블에 표시된 것처럼 다양한 파라미터와 설정을 가집니다.

<table><tbody><tr><td colspan="3"><h4><span id="h_01K5EH9WVTEX56980MCR81ZAHH"></span><span id="contains-does-not-contain-logic"></span><span id="h_01K5EHGKDPWS16HP9Q7KX9JXFY"></span><span id="events"></span>이벤트</h4><p><img alt="engagement_filter_with_A___B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966588305"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>광고를 본</li><li>광고를 클릭한</li><li>앱 설치</li><li>앱을 설치하지 않은</li><li>앱을 실행한</li><li>앱을 실행하지 않은</li><li>앱을 삭제한 </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>기간 및 빈도 </p></td></tr><tr><td colspan="3"><h4><span id="inapp-events"></span>인앱 이벤트</h4><p><img alt="in-app_event_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018249873"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>수행한 이벤트[<em>이벤트 이름</em>]</li><li>수행하지 않은 이벤트: [<em>이벤트 이름</em>] </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>기간 및 빈도 </p></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>이벤트 어트리뷰트 + 값:</p><ul><li>은</li><li>보다 큰</li><li>보다 작은</li></ul></td></tr><tr><td colspan="3"><p><a href="./in-app-events-overview" target="_blank"><strong>인앱 이벤트</strong></a><strong>와 관련된 참고 사항:</strong></p><ul><li>인앱 이벤트 목록은 <a href="./about-data-freshness-and-timezone-support#daily-processing" target="_blank">매일</a> 업데이트됩니다. </li><li> <strong>이벤트 수행</strong>이 선택되고, 인앱이벤트에 이와 연관된 어트리뷰트가 있는 경우, 인앱이벤트 어트리뷰션 값을 사용해 필터링할 수 있습니다. </li><li><p>인앱이벤트는 기본적으로 어트리뷰트 당 100개의 고유 값으로 제한됩니다. 예를 들어 이벤트가 "구매"이고 어트리뷰트가 "콘텐츠 유형"인 경우 가능한 콘텐츠 유형은 100개(또는 그 미만)뿐입니다. 그러나 숫자 값은 제한이 없습니다.<br/>목록에 표시되지 않는 인앱이벤트 속성(파라미터) 및 값이 있는 경우 <strong>이벤트 어트리뷰트(Add event attribute)</strong> &gt; <strong>항목 추가(Add item)</strong>를 클릭하여 수동으로 추가할 수 있습니다.<br/> </p><p><strong><img alt="Add_item.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966609297"/></strong></p><p>다음 사항을 참고하십시오.</p><p>- 수동으로 추가한 이벤트 항목은 모두 문자열 형태(텍스트)로만 입력해야 합니다. 숫자 값을 추가하면 안 되며 추가하면 올바르게 작동하지 않을 것입니다.</p><p>- 수동으로 추가한 이벤트 항목이 추가된 경우 "예상 오디언스 규모"가 정확하게 반영되지 않을 수 있습니다. <br/>100개 이상의 어트리트/값을 목록에 표시해야 하는 경우 CSM에 문의하거나 hello@AppsFlyer.com으로 이메일을 보낼 수 있습니다.</p></li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>수익</h4><p><img alt="revenue_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966611089"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>총 인앱 구매 수익</li><li>총 광고 수익</li><li>총수익 </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>은</li><li>보다 큰</li><li>보다 작은 경우 </li></ul><p><strong>정의:</strong></p><ul><li> <strong>총 인앱 구매 수익:</strong> 특정 디바이스/CUID에 대한 <code>af_revenue</code> 파라미터를 사용하여 리포트된 모든 이벤트의 총 가치</li><li> <strong>총 광고 수익:</strong> 특정 디바이스/CUID에서 생성된 총 광고 수익</li><li> <strong>총수익</strong>: 총 인앱 구매 수익 + 총 광고 수익</li></ul><p><strong>참고:</strong></p><ul><li> <strong>총 광고 수익</strong> 및 <strong>총 수익</strong> 필터를 사용하려면 앱스플라이어 계정에서 <a href="./roi360-guide-ad-revenue-attribution" target="_blank">광고 수익 어트리뷰션</a> 을 구현해야 합니다.</li><li>모든 수익 필터 옵션은 USD로 측정됩니다.</li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>지역</h4><p><img alt="location_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018257041"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>위치 </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>은</li><li>같지 않은</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p><strong>위치 옵션</strong></p><ul><li>국가</li><li>주</li><li>도시</li></ul></td></tr><tr><td colspan="3"><p><strong>위치와 관련한 참고사항:</strong></p><ul><li>여러 국가를 선택하는 경우 주를 선택할 수 없습니다.</li><li>여러 개의 주를 선택하는 경우 도시를 선택할 수 있습니다.</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>온드 미디어</h4><p><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966614801"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>온드 미디어 소스</li><li>온드 미디어 캠페인</li><li>온드 미디어 광고 세트</li><li>온드 미디어 광고</li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>은</li><li>같지 않은</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>다음과 같은 값:</p><ul><li>이메일</li><li>SMS</li><li>웹</li><li>소셜 미디어(유료 광고 제외)</li><li>QR 코드</li><li>추천 측정</li><li>특정 미디어 캠페인, 광고 세트 및 광고</li></ul></td></tr><tr><td colspan="3"><p>특정 온드 미디어 소스에 어트리뷰트된 사용자로 구성된 타겟 오디언스를 구축할 수 있습니다. 또한 세분화 수준을 선택하고 특정 온드 미디어 소스, 캠페인, 광고 세트 및/또는 개별 광고에서 온 사용자를 타겟팅할 수 있습니다.</p><p>생성한 오디언스를 활용하여 온드 미디어나 유료 미디어에서 맞춤형 메시지로 사용자의 재참여를 유도하거나, 신규 유저 확보 및 리인게이지먼트 캠페인 진행 시 불필요하거나 관련 없는 광고가 노출되지 않도록 제외 리스트로 활용하세요.</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>디바이스</h4><p><img alt="device_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966618897"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>디바이스 브랜드</li><li>디바이스 모델</li><li>앱 버전</li><li>OS 버전</li><li>통신사</li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>은</li><li>같지 않은 </li></ul></td><td> <img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/> 선택한 값</td></tr><tr><td colspan="3"><h4><span id="attribution"></span>어트리뷰션</h4><p><img alt="Attribution_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966620049"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><ul><li>오가닉</li><li>리타겟팅</li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>False</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>사용자 기여</a></h4><p><img alt="user_attribute_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966622097"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><p>사용자 기여 이름</p></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>문자열 유형<ul><li>은</li><li>같지 않은</li></ul></li><li>숫자 유형<ul><li>은</li><li>보다 큼</li><li>보다 작음</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/><br/>문자열의 경우: 값 선택</p><p>숫자의 경우: 값 입력</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="규칙 집합 결합">

**규칙 집합을 기존 오디언스와 결합하는 방법:**

1. **Engage** > **Audiences**로 이동합니다.
2. **오디언스 추가**를 클릭합니다.  
   **구축** 탭이 표시됩니다.
3. 고유한 **오디언스 이름**을 입력합니다.
4. 플랫폼을 선택합니다. **안드로이드** 또는 **iOS**.
5. [선택 사항] **고급 설정**을 선택하여 [사용자 식별자](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)를 선택합니다.
   * [기본값] **디바이스 ID**: 오직 디바이스 ID로 규칙 평가를 적용합니다.
   * **고객 사용자 ID(CUID)**: CUID를 사용해 기기를 묶어 규칙 평가를 적용합니다. 데이터가 유효한 CUID를 가지고 있는지 확인한 후에 이 방법을 사용합니다.
6. **기존 오디언스**를 클릭한 다음 특정 오디언스를 선택합니다.
7. 연산자 and, or, exclude를 선택합니다.

**제한 사항:**

* 기존 오디언스는 새 오디언스와 동일한 플랫폼(예: iOS 또는 안드로이드)에 있어야 합니다.
* 기존 오디언스를 기반으로 하는 오디언스는 사용할 수 없습니다.
* 가져온 오디언스는 사용할 수 없습니다.

</Accordion>

<div id="create-and-manage-partner-connections" />

## 파트너 연결 생성 및 관리

이 섹션에서는 미디어 파트너 연결을 생성하고 관리하는 방법을 설명합니다.

<div id="create-a-new-connection" />

<Accordion title="새 연결 생성">

**연결** 탭은 모든 파트너 연결과 각 상태를 표시합니다. 오디언스 데이터를 미디어 파트너에게 업로드하는 데 필요한 모든 정보는 파트너 연결에 지정되어 있습니다. 단일 미디어 파트너에 대해 다중 연결을 사용할 수 있습니다(다른 계정, 로그인 정보 등의 사용).

**새 연결을 생성하는 방법은 다음과 같습니다.**

1. **Engage** > **Audiences > Connections**로 이동합니다.
2. **+ 새 연결**을 클릭합니다.  

   **참고:** 오디언스 빌더 내에서 새 파트너 연결을 만드는 경우 **오디언스 연결 관리** 창에서 **+ 파트너 연결 추가**를 클릭합니다.
3. **파트너 이름**을 선택합니다.
4. **연결 이름**을 입력하십시오.  

   **참고:** 다른 연결을 만들 때 사용한 적이 없는 새 이름이어야 합니다.
5. 파트너에 대한 필수 필드/로그인 정보를 작성합니다. 일부 파트너에는 연결 방법에 대한 <Anchor target="_blank" href="/marketers/ko/docs/audiences-partner-connections">자세한 지시사항이 있습니다.</Anchor>   

   **참고:** 자격 증명은 고유해야 합니다. 중복 연결이 생성되는 것을 방지하기 위해, 해당 자격 증명이 이미 다른 파트너 연결에 사용된 경우에는 새 연결을 생성할 수 없도록 차단됩니다.
6. 이 파트너와 공유할 수 있는 권한을 부여한 사용자 식별자를 선택하십시오.
   * 지원되는 식별자는 파트너에 따라 다릅니다. 선택한 파트너가 지원하는 해당 식별자만 목록에 표시됩니다.
   * <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">계정 수준 사용자 식별자 정책</Anchor>을 준수하는 식별자만 업로드됩니다. 계정 정책에서 허용되지 않는 식별자를 선택하면 주의 메시지가 표시됩니다.  
     <Image align="center" alt="doctored_connection_image.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966624017" />
7. **저장**을 클릭합니다.

</Accordion>

<div id="manage-connections" />

<Accordion title="연결 관리">

**기존 연결 관리 방법:**

1. 파트너를 선택합니다.
2. 연결을 선택하세요. ![Edit_connection_screen.jpg](https://support.appsflyer.com/hc/article_attachments/30259018273553)
3. 다음 작업 중 하나를 수행하십시오.

| 옵션 | 절차 |
| --- | --- |
| <span id="change-the-connection-name"></span>연결 이름을 변경합니다. | **연결 이름을 변경하려면** **연결 이름** 필드에서 직접 수정하십시오. |
| <span id="reconnect"></span>재연결 | **재연결 방법:**<ol><li>연결 상태가 활성이 아니면 **재연결**을 클릭합니다.</li><li>연결 자격 증명을 업데이트하거나 파트너에 로그인하여 사용자 인터페이스의 지침에 따라 다시 인증합니다.</li></ol> |
| <span id="modify-user-identifiers"></span>사용자 식별자 수정 | **사용자 식별자를 수정하려면** 이 파트너에 공유할 수 있는 권한을 부여한 사용자 식별자를 선택/선택 해제하십시오. <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">계정 수준 사용자 식별자 정책</Anchor>을 준수하는 식별자만 업로드됩니다. |
| <span id="delete-connection"></span>연결 삭제 | **연결 삭제:**<ol><li>연결된 오디언스가 있는 경우 다음과 같이 삭제합니다.<ol><li>오디언스를 선택합니다.</li><li>새 탭에 오디언스 연결 탭이 열립니다.</li><li>연결을 해제합니다.</li><li>탭을 닫습니다.</li></ol></li><li>연결된 모든 오디언스가 연결 해제될 때까지 이 절차를 반복하십시오.</li><li>**연결 삭제**를 클릭합니다.</li></ol> |

</Accordion>

<div id="dashboard-and-metrics" />

## 대시보드 및 지표

이 섹션에서는 대시보드에 표시되는 기능 및 캠페인 지표에 대해 설명합니다.

<div id="audiences-dashboard" />

<Accordion title="오디언스 대시보드">

<Image align="center" alt="new_dashboard_image_doctored.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966628625" />

| 열 | 설명 |
| --- | --- |
| <span id="audience-name"></span>오디언스 이름 | 오디언스 이름 |
| <span id="size"></span>사이즈 | 오디언스 기준과 일치하는 모든 사용자 |
| <span id="upload-size"></span>업로드 크기 | 계정 수준 <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">사용자 식별자 정책</Anchor>과 링크된 파트너 연결에 대해 선택한 식별자를 적용한 후 업로드할 수 있는 오디언스 크기입니다.<br /><br />**참고:** 파트너 측의 실제 크기는 다음과 같은 여러 가지 이유로 다를 수 있습니다.<ul><li>파트너 매칭 프로세스.</li><li>iOS의 업로드 크기는 IDFV를 기반으로 한 보강 세그먼트 수를 나타내며, 여기에는 중복된 IDFA가 포함될 수 있습니다. 파트너 측에 업로드할 때 중복 제거가 이루어져 크기 불일치가 발생할 수 있습니다.</li></ul> |
| <span id="app-name"></span>앱 이름 | 오디언스 정의에서 참조된 앱(들)입니다. 이것들은 반드시 오디언스를 활용하는 캠페인에 의해 타겟이 되는 앱은 아닙니다. |
| <span id="upload-to"></span>업로드 대상 | <ul><li>오디언스를 보낼 파트너의 아이콘</li><li><Image alt="SplitAudiences.png" src="https://support.appsflyer.com/hc/article_attachments/30259018280465" width="36px" />는 오디언스가 파트너 간에 분할되어 있음을 나타냅니다.</li></ul> |
| <span id="incrementality"></span>성과증분측정 | Incrementatlity를 <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview">구독하는 경우 이 열이 표시됩니다.</Anchor> 상태는 다음과 같습니다.<ul><li>**보류 중** - 캠페인 시작일로부터 시작되는 초기 데이터 수집 기간(48시간)</li><li>**캠페인 연결** - 실험에 연결할 관련 캠페인을 선택합니다. 캠페인 제안이 있는 경우 미리 선택됩니다(추가 제안은 드롭다운 목록에서 관련성을 기준으로 정렬됨).</li><li>**활성** - 실험이 진행 중입니다.</li><li>**완료됨** - 실험이 종료되었습니다.</li></ul>상태를 클릭하면 Incrementatlity 대시보드로 이동합니다. |
| <span id="upload-status"></span>상태 업로드 | <ul><li>현재 오디언스 업로드 상태</li><li>툴팁은 가장 최근에 업로드한 날짜와 시간을 표시합니다.</li><li>실패하는 경우, **세부사항 보기**를 클릭하고 표시되는 자세한 오류 메시지에 따라 정정 조치를 수행하십시오.</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="캠페인 지표">

<div id="metrics-hash" />

#### 지표 해시

<div id="campaign-metrics-basics" />

#### 캠페인 지표 기본

오디언스 대시보드의 **캠페인 지표** 섹션에는 타게팅(포함, 제외 또는 찾아보기 대상의 기초)을 위해 오디언스를 사용한 캠페인에 대한 데이터가 표시됩니다.

* 미디어 파트너와의 캠페인은 타게팅(및 사용 방법 결정)을 위해 오디언스를 사용하는 것이 핵심입니다. 미디어 파트너는 오디언스 이용 방법에 대한 지원이 다양합니다.

**지원되는 파트너:** 현재 메타 광고, Google Ads 및 Snapchat에서 데이터를 사용할 수 있습니다. 대시보드의 **캠페인 지표** 섹션은 지원 파트너에 연결된 오디언스가 있는 경우에만 표시됩니다.

**캠페인 지표를 보는 방법:**

1. 오디언스 대시보드의 오른쪽 끝으로 스크롤하여 **캠페인 지표** 섹션을 완전히 표시합니다.
2. 데이트 피커를 사용하여 데이터를 표시할 기간을 선택하십시오. (기본적으로 대시보드에 지난 7일 동안의 데이터가 표시됩니다.)

**선택된 기간에 대한** **캠페인 지표를 다운로드하는 방법**:

1. 오디언스 대시보드 맨 위에 있는 **내보내기** 버튼을 클릭합니다.
2. 파일은 생성되면 자동으로 다운로드됩니다.


<div id="summary-view" />

#### 개요 뷰

초기 **캠페인 지표** 뷰는 각 오디언스에 대한 다음과 같은 개요 캠페인 데이터를 표시합니다.

<Image align="center" alt="campaign_metrics_summary_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018286225" width="433px" />

| 열 | 설명 |
| --- | --- |
| <span id="campaigns"></span>캠페인 | 선택한 기간에 오디언스를 대상으로 사용한 총 캠페인 수(지원 파트너와 함께 진행되는 캠페인만 해당) |
| <span id="campaign-cost"></span>캠페인 비용 | 선택한 기간에 이러한 캠페인의 총비용 |
| <span id="campaign-revenue"></span>캠페인 수익 | 선택한 기간에 이러한 캠페인에 어트리뷰트된 총수익 |

<div id="detailed-view" />

#### 상세 보기

요약 보기에서 <Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" /> 아이콘을 클릭하여 선택한 오디언스에 대한 상세 보기로 들어갑니다. (마우스를 해당 행에 놓으면 <Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" /> 아이콘이 행의 맨 오른쪽에 나타납니다.)

상세 보기에는 지원되는 파트너 및 캠페인별로 분류된 데이터가 표시됩니다.

<Image align="center" alt="campaign_metrics_detailed_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018293649" />

선택한 오디언스가 하나 이상의 앱을 대상으로 사용된 경우 드롭다운 목록 ![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697)를 사용하여 앱별로 데이터를 필터링합니다.

**개요 대시보드** 링크 ![pin_B.png](https://support.appsflyer.com/hc/article_attachments/30258966657169)를 클릭하여 개요 대시보드에서 캠페인을 볼 수 있습니다.

* 대시보드가 관련 캠페인에 의해 자동으로 필터링된 새 브라우저 탭에서 열립니다.
* **개요 대시보드** 링크가 비활성화된 경우 드롭다운 목록 ![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697)에서 단일 앱을 선택하여 대시보드 링크를 활성화할 수 있습니다. 링크가 활성화된 후 해당 링크를 클릭하면 선택한 앱의 개요 대시보드가 나타납니다.

| 열 | 설명 |
| --- | --- |
| <span id="cost"></span>비용 | 선택한 기간의 캠페인 비용(총비용, 이것을 지원 파트너 및 캠페인별로 구분) |
| <span id="revenue"></span>수익 | 선택한 기간에 캠페인에 어트리뷰트되는 수익(총비용, 이것을 지원 파트너 및 캠페인별로 구분) |
| <span id="daily-reach"></span>일일 도달 범위 | 선택한 기간에 캠페인에서 광고를 본 하루 평균 고유 사용자 수(파트너 리포트에 따름) |

<div id="data-sources-and-availability" />

#### 데이터 소스 및 가용성

데이터 출처를 살펴보면 **캠페인 지표** 데이터의 가용성을 보다 쉽게 파악할 수 있습니다.

* **파트너 데이터:** 미디어 파트너를 통해 특정 캠페인의 대상이 될 오디언스를 선택했으므로 다음 파트너만 특정 정보를 제공할 수 있습니다.
  * 캠페인에 오디언스 연결(즉, 특정 대상 고객이 해당 캠페인에 의해 타게팅에 사용되었다는 사실)
  * 캠페인에서 광고를 본 일일 고유 사용자 수("데일리 리치")
* **앱스플라이어 데이터:** 비용 및 수익 데이터는 앱스플라이어에서 제공합니다.

<div id="partner-data-availability" />

<Accordion title="파트너 데이터 가용성">

데이터는 [지원 파트너](/docs/audiences-guide#캠페인-지표-기본)와 함께 실행되는 캠페인에 대해서만 리포트됩니다.

* **참고:** Google Ads는 데일리 리치의 리포트를 지원하지 않습니다.

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="앱스플라이어 데이터 가용성">

비용 및 수익 데이터는 앱스플라이어의 다른 영역(예: 개요 및 이벤트 대시보드)의 앱에 대해 리포트된 경우 **캠페인 지표**의 컨텍스트 내에서 사용할 수 있습니다.

* 비용 데이터를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">ROI360</Anchor>에 가입해야 합니다.
* 수익 데이터를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution">광고 수익 어트리뷰션</Anchor> 및/또는 <Anchor target="_blank" href="/marketers/ko/docs/roi360-revenue-attribution-overview">인앱 이벤트 수익 어트리뷰션</Anchor>을 구성해야 합니다.

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="지원 파트너와 함께 실행되는 캠페인에 대한 캠페인 지표 데이터가 표시되지 않는 이유는 무엇입니까?">

캠페인 지표 데이터는 다음에만 사용할 수 있습니다.

* 오디언스와 연결된 캠페인입니다.
* 지원되는 미디어 파트너 사이트에서 실행 중인 캠페인.
* 선택한 기본 날짜 범위 내의 활성 캠페인.
* 캠페인 지표 필터에서 선택한 날짜 범위 내에서 설치 트래픽을 수신하는 캠페인.
* 캠페인 수준 데이터를 수신할 수 있는 권한이 있는 파트너 연결을 위해 구성된 사용자. 이 데이터를 보려면 파트너에 대한 사용자의 사용 권한을 변경하거나 파트너 연결 설정에서 다른 자격 증명을 사용하십시오.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

다음 특성 및 제한 사항에 유의하십시오.

<div id="traits" />

<Accordion title="특성">

| 특성 | 지원됨. | 비고 |
| --- | --- | --- |
| 애드 네트워크 | **x** |  |
| 에이전시 | **x** |  |
| 에이전시 투명성 | **x** |  |
| 앱별 시간대 | 해당 없음 |  |
| 앱별 통화 | 해당 없음 |  |
| 사이즈 제한 | 해당 없음 |  |
| 오가닉 데이터 | ✓ | 포함 |
| 논오가닉 데이터 | ✓ | 포함 |
| 데이터 최신성 | 일일 UTC | <ul><li>업데이트는 일별로 파트너에게 전송됩니다.</li><li>규칙 빌더 내 이벤트 목록은 매일 업데이트됩니다.</li></ul> |
| 과거 데이터 | ✓ | 오디언스 기능은 구독 시작일 기준 최대 90일 전의 앱 이벤트 데이터에 접근할 수 있습니다 (클릭 및 노출 데이터의 경우 31일 전). 데이터는 백필(백업 및 소급 적용) 프로세스가 완료된 후에 완전히 사용할 수 있게 됩니다 (약 5일에서 14일 소요). |
| 계정 유저 액세스 | ✓ | <ul><li>CSV 다운로드, S3 설정, Slack 파트너 연결과 같은 일부 기능은 로우 데이터에 접근하기 위해 사용자 계정 권한이 필요합니다.</li><li>보안 조치의 일환으로, 오디언스를 생성한 사용자의 계정이 삭제되면 앱스플라이어는 해당 오디언스의 데이터를 미디어 파트너에 업로드하는 작업을 중단합니다. 오디언스의 업로드 상태를 확인하려면 **참여** > **오디언스**로 이동하세요. 오디언스를 다시 활성화하려면 해당 오디언스를 복제한 후 [분할 오디언스](/docs/audiences-guide#audience-split-and-control-groups) 설정을 구성하세요.</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="제한 사항">

| 제한 사항 | 비고 |
| --- | --- |
| 어트리뷰션 데이터 | 클릭 및 노출 데이터에는 최초 클릭 URL에 advertising\_id 또는 idfa가 포함된 기기의 데이터만 포함됩니다. 외부 어트리뷰션 링크를 사용하지 않는 SRN 유저의 기기는 오디언스 클릭 데이터에 포함되지 않습니다. |
| 오디언스 생성: 오디언스 이름은 연동된 파트너 매체 쪽에서 변경할 수 없습니다. | <ul><li>오디언스를 생성할 때 가장 상위의 100개 이벤트만 표시됩니다. 하지만 이벤트 이름을 입력하기 시작하면 모든 이벤트가 표시됩니다.</li><li>쿼리 빌더 내에서 '총 매출' 필터를 사용하는 경우, 예상 오디언스 모수 크기를 확인할 수 없습니다. 이것은 오디언스 생성 프로세스에는 영향을 미치지 않습니다.연결: 중복된 파트너 연결(동일한 계정/로그인 정보/속성 ID 등을 사용한 연결) 생성은 지원되지 않으며 오류가 발생합니다.</li></ul> |
|  |  |
| 오디언스 CSV 파일 다운로드: 다운로드 파일 크기는 최대 500만 건(레코드)으로 제한됩니다.가져온 오디언스: 가져온 오디언스는 다른 오디언스나 룰셋(규칙 세트)과 결합할 수 없습니다. |  |
|  |  |
| 비활성 오디언스: 비활성 상태인 오디언스는 일시 중지됩니다. | 이는 해당 오디언스가 더 이상 계산되지 않으며, 연동된 파트너 매체로 업로드되지 않음을 의미합니다. '지금 업로드'를 클릭하여 언제든지 오디언스의 일시 중지를 해제 할 수 있습니다. 이렇게 하면 오디언스 연산이 재개되며, 이전과 마찬가지로 파트너 매체로의 자동 업로드가 다시 시작됩니다. |
| 지원되지 않음 | 다음은 앱스플라이어 오디언스에서 지원되지 않는 항목입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/audiences-partner-connections#google-ads">Google Ads</Anchor>: UAC 캠페인은 지원되지 않습니다. 기타 캠페인 유형이 지원됩니다.</li><li>Windows Phone OS중첩된 이벤트 값 (Nested event values)오디언스 개수:하루에 최대 100개의 오디언스를 생성할 수 있습니다.</li></ul> |
|  | <ul><li>동시에 활성화할 수 있는 커스텀/추천 오디언스는 최대 100개입니다.</li><li>한 번에 최대 500개의 활성 오디언스를 가져올 수 있습니다.</li></ul> |
| 규칙 세트 | <ul><li>룰셋 내에서 인앱 이벤트는 속성당 최대 100개의 고유 값으로 제한됩니다. 예를 들어 이벤트가 'purchase(구매)'이고 속성이 'content-type'인 경우, 가능 한 content-type의 종류는 최대 100개(이하)까지만 지정할 수 있습니다. 그러나, 숫자 값은 무제한입니다. 속성당 더 많은 값이 필요한 경우, 담당 CSM에게 문의하시거나 hello@appsflyer.com으로 이메일을 보내주세요.</li><li>숫자형 룰셋 필터에는 정수(소수점이 없는 수)만 사용할 수 있습니다. 부동 소수점(소수) 형태의 숫자는 지원되지 않습니다. 예: 인앱 매출 조건 설정 시 1달러($1 USD)는 사용할 수 있지만, 1.5달러와 같은 소수점 금액은 사용할 수 없습니다.</li></ul> |
| S2S 리포팅: S2S(서버 간) 인앱 이벤트 페이로드에 사용자 식별자(IDFV 또는 IDFA)가 포함되어 전송되는지, 그리고 해당 IDFV 또는 IDFA가 AppsFlyer SDK에서 수집하는 정보와 일치하는지 확인하세요. | 이를 통해 데이터 누락을 방지하고 오디언스를 정확하게 연산할 수 있습니다.참고 항목 |

</Accordion>

> 📄
>
> * <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview"><span id="see-also"></span><span id="h_01HDNZ24ZDXSAPJ1F5QCB9X1EN"></span>Incrementality 가이드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/run-an-incrementality-for-remarketing-experiment">성과 증분 측정 실험 실행</Anchor>

<div data-zendesk-anchors="audiences-basics=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B8%B0%EB%B0%98 h_01HBQMA619CKEESZD3ADSP3PSB=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B8%B0%EB%B0%98 audience-split-and-incrementality-testing=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B6%84%ED%95%A0-%EB%B0%8F-%EC%84%B1%EA%B3%BC-%EC%A6%9D%EB%B6%84-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HBQMA619KMJFVX7Y8MXMMQ6N=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B6%84%ED%95%A0-%EB%B0%8F-%EC%84%B1%EA%B3%BC-%EC%A6%9D%EB%B6%84-%ED%85%8C%EC%8A%A4%ED%8A%B8 get-started=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 h_01HBQMA619118PWF4TA98C4X0B=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0 create-and-manage-audiences=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EA%B4%80%EB%A6%AC h_01HBQMA619DBX2C7DRY7MSV3P9=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EA%B4%80%EB%A6%AC h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01JXA0GDBMBX541W6P63XXDVKQ=%EC%B0%B8%EA%B3%A0 h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80-%EC%98%88%EC%8B%9C h_01JXA0WJFMSHA710CTNF84BPQ5=%EC%B0%B8%EA%B3%A0-1 h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=%EC%98%88%EC%8B%9C-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-id-vs-cuid 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences h_01HT04HW2VBB9ZY28V5KQ5K2AJ=pause all-about-rulesets=%EA%B7%9C%EC%B9%99-%EC%A7%91%ED%95%A9%EC%97%90-%EB%8C%80%ED%95%9C-%EB%AA%A8%EB%93%A0-%EA%B2%83 h_01HBQMA61ANB4K0TCJ4WBHMV8D=%EA%B7%9C%EC%B9%99-%EC%A7%91%ED%95%A9%EC%97%90-%EB%8C%80%ED%95%9C-%EB%AA%A8%EB%93%A0-%EA%B2%83 h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=%EC%98%88-%EC%9C%84%EC%B9%98-%EA%B8%B0%EB%B0%98-%EA%B7%9C%EC%B9%99 h_01HBQMA61ATB7NYKBP7CD6SZZH=%EC%98%88-%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%8A%B9%EC%84%B1-%EA%B8%B0%EB%B0%98-%EA%B7%9C%EC%B9%99 h_01HBQMA61APWHKS4EP2NKABSQD=%EC%98%88-%EC%88%98%EC%9D%B5 01ECF4ZD0MJ8HVQCC54YHFE6DX=%EC%98%88-%EC%98%A8%EB%93%9C-%EB%AF%B8%EB%94%94%EC%96%B4-%ED%95%84%ED%84%B0 h_01JRAGFYEQ28R6RQNPEK6WZV2F=%EC%98%88-%EB%A6%AC%EB%A7%88%EC%BC%80%ED%8C%85 h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EA%B2%B0-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EA%B4%80%EB%A6%AC h_01HBQMA61C6WS72DQ8FXVR0KVW=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EA%B2%B0-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EA%B4%80%EB%A6%AC h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EC%A7%80%ED%91%9C h_01HBQMA61C6WPFFR1F8P0HE4KA=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EC%A7%80%ED%91%9C h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics metrics-hash=%EC%A7%80%ED%91%9C-%ED%95%B4%EC%8B%9C h_01HBQMA61CMF3WZFPXKY89076K=%EC%A7%80%ED%91%9C-%ED%95%B4%EC%8B%9C campaign-metrics-basics=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%A7%80%ED%91%9C-%EA%B8%B0%EB%B3%B8 h_01HBQMA61C4D5HFCDY83HNF5K7=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%A7%80%ED%91%9C-%EA%B8%B0%EB%B3%B8 summary-view=%EA%B0%9C%EC%9A%94-%EB%B7%B0 h_01HBQMA61DW9Z84G8CH1RNY2RF=%EA%B0%9C%EC%9A%94-%EB%B7%B0 h_01K3R8C7GK77FNVZ3N0C3XZGYG=%EA%B0%9C%EC%9A%94-%EB%B7%B0 detailed-view=%EC%83%81%EC%84%B8-%EB%B3%B4%EA%B8%B0 h_01HBQMA61D3VHDKD103EMN61YH=%EC%83%81%EC%84%B8-%EB%B3%B4%EA%B8%B0 data-sources-and-availability=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-%EB%B0%8F-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HBQMA61DB595QKRTPE97F94E=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-%EB%B0%8F-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HBQMA61DT46P43FNSRC1KGAX=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations" />
