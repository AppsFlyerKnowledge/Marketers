---
title: 앱 소유자에 대한 유효성 검증 규칙
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-10-14T10:40:17Z'
  id: 115004703926
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/115004703926
---
> **한눈에 보기:** 검증 규칙은 잘못된 타겟 캠페인과 사기에 대한 맞춤형 보호 계층을 추가합니다. 이 규칙은 앱 소유자가 어떤 설치 및 인앱 이벤트 귀속이 차단되거나 마지막 유효 소스에 귀속되는지를 제어할 수 있게 합니다.

![5906_animation-750x330__1_.gif](https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif)

<div id="overview" />

## 개요

* 유지 또는 차단할 앱 인스톨 또는 인앱 이벤트를 필터링하고 선택하는 사용자 지정 조건 및 논리를 사용하여 규칙 작성기에서 유효성 검사 규칙이 정의됩니다.
* 규칙은 다음과 같은 여러 사용 사례에 대한 다양한 파라미터를 기반으로 합니다.
  * 캠페인에 대한 타겟 없는 인스톨(잘못된 지역, OS 버전 등)
  * 광고 네트워크로 서명한 삽입 순서를 충족하지 않는 인스톨
  * 사기성 네트워크에 의해 하이재킹된 인스톨
  * 봇, 에뮬레이터 또는 디바이스 팜에서 전송된 사기성 인스톨 또는 인앱 이벤트
* 인앱 이벤트에 대해 정의된 규칙은 이전에 차단되지 않은 인스톨과 관련된 IAE에만 적용됩니다.
* 광고 네트워크가 포함된 규칙은 해당 광고 네트워크의 직원이 볼 수 있습니다(그러나 직원들은 규칙에 포함된 다른 광고 네트워크는 볼 수 없음). 이것은 투명성을 위한 것이고 광고 네트워크가 제공하는 트래픽의 성능을 더 잘 이해하도록 돕기 위한 것입니다.
* 규칙은 실시간으로 실행되면서 즉각적인 조치를 취합니다. 결과 섹션에서 자세히 알아보세요.
* <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360</Anchor> 고객은 자동 Protect360 사기 차단 및 탐지 기능 외에도 추가 유효성 검사 규칙 옵션을 사용할 수 있습니다. 이 조건들은 다양한 설치 탈취, 가짜 설치 및 가짜 인앱 이벤트 사기 유형을 탐지하는 데 도움이 되는 것으로 알려져 있습니다.  
  **참고**: 검증 규칙은 Protect360에 의해 사기로 식별되지 않은 설치/인앱 이벤트만 검증합니다.

<div id="outcomes" />

<Accordion title="결과">

* 설치의 경우: 검증 규칙은 선택된 작업에 따라 귀속을 차단하고 마지막 유효 미디어 소스로 수정하거나 귀속을 완전히 차단합니다.
* 인앱이벤트인 경우: 검증 규칙은 인앱 이벤트의 귀속을 차단합니다.
* 유효성 검사 규칙 블록 유형 결과를 보여 주는 다음 표를 참조하십시오.  

<table><thead><tr><th> </th><th>차단 유형</th><th>설명</th><th>인스톨 데이터를 볼 수 있는 위치</th><th>그에 따른 인앱 이벤트</th></tr></thead><tbody><tr><td rowspan="2"><strong>인스톨</strong></td><td>차단 어트리뷰션 및 마지막 유효한 미디어소스로 정정.</td><td><ul><li><span>인스톨은 실제이지만 조건에 따라 인스톨이 어트리뷰트되거나 되지 않아야 한다는 조건을 결정해야 한다고 가정할 때 선택합니다. </span></li><li><span>어트리뷰션이 수정되고 인스톨은 유효한 마지막 미디어소스에 어트리뷰트됩니다.</span></li><li><span>식별된 올바른 미디어소스가 없으면 인스톨은 오가닉으로 표시됩니다.</span></li></ul></td><td><ul><li>앱스플라이어 대시보드 및 로데이터를 정기 인스톨로 보고합니다(유효한 마지막 미디어소스에 추가됨).</li><li>Protect360 프리미엄 플랜으로:<ul><li><a href="./protect360-dashboard#대시보드-인스톨" target="_blank">Protect 360은 대시보드를 인스톨합니다.</a></li><li>Protect360은 로데이터 리포트를 인스톨합니다(<span>차단된 미디어소스를 통해)</span>. </li></ul></li><li>Protect360 프리미엄 플랜 미포함:<ul><li>Protect360은 로데이터 리포트를 인스톨합니다(<span>차단된 미디어소스를 통해)</span>. </li></ul></li></ul></td><td><ul><li>인스톨과 동일한 수정된 어트리뷰션을 가집니다.</li><li>Protect360 프리미엄 플랜을 통해 사용 가능한 데이터:<ul><li>앱스플라이어 대시보드 및 리포트에서 수정된 어트리뷰션을 일반 IAE로 지정</li><li>Protect360 IAE 대시보드 및 Protect360 차단된 IAE 로데이터 리포트에 차단된 미디어소스 포함</li></ul></li></ul></td></tr><tr><td>설치를 유효하지 않은 것으로 표시하고 귀속하지 않습니다.</td><td><ul><li><span>규칙 조건에 따라 유효하지 않은 인스톨이 사기로 간주될 때 선택합니다.</span></li><li><span>인스톨은 전혀 어트리뷰트되지 않습니다(논오가닉도 오가닉도 아님)</span></li></ul></td><td><ul><li>Protect360 프리미엄 플랜으로:<ul><li><a href="./protect360-dashboard#대시보드-인스톨" target="_blank">Protect 360은 대시보드를 인스톨합니다.</a></li><li>Protect360은 로데이터 리포트를 인스톨합니다(<span>차단된 미디어소스를 통해)</span>. </li></ul></li><li>Protect360 프리미엄 플랜 미포함:<ul><li>Protect360은 로데이터 리포트를 인스톨합니다(<span>차단된 미디어소스를 통해)</span>. </li></ul></li></ul></td><td><ul><li><span>차단 수</span></li><li><span>Protect360 IAE 대시보드의 Protect360 프리미엄 플랜 및 차단된 IAE 로데이터 보고서로 데이터 사용 가능</span></li></ul></td></tr><tr><td rowspan="2"><strong>인앱 이벤트</strong></td><td>어트리뷰션 차단 </td><td><ul><li><span>규칙 조건에 따라 유효하지 않은 인앱 이벤트가 사기로 간주될 때 선택합니다.</span></li></ul></td><td><ul><li> Protect360 프리미엄 플랜으로:<ul><li><a href="./protect360-dashboard#인앱-이벤트-대시보드" target="_blank">Protect360 IAE 대시보드</a></li><li>Protect360 인앱 이벤트 로데이터 리포트</li></ul></li><li>Protect360 프리미엄 플랜 미포함: 해당 없음</li></ul></td><td><ul><li> Protect360 <span>IAE 대시보드</span>의 Protect360 프리미엄 플랜 및 차단된 인앱 이벤트 로데이터 보고서로 데이터 사용 가능 </li></ul></td></tr><tr><td>앱스플라이어에서 완전히 제거하기</td><td><ul><li><span>데이터가 필요하지 않은 인앱 이벤트가 있을 때 사용하는 것이 좋습니다.</span></li><li><span>앱스플라이어는 이런 이벤트를 전혀 기록하지 않습니다. </span></li></ul></td><td><span></span></td><td><span></span></td></tr></tbody></table>

* 광고 네트워크와 에이전시는 광고주가 그들에게 필요한 권한을 할당하는 경우에만 데이터를 볼 수 있습니다.
* 설치 귀속이 차단되거나 실시간으로 유효 미디어 소스에 귀속될 때, 차단된 광고 네트워크에 즉시 거부된 포스트백이 전송되어 조정 흐름을 간소화합니다. 귀속이 차단되고 마지막 유효 미디어 소스로 수정될 때, 마지막 유효 광고 네트워크에도 포스트백이 전송됩니다.
* 인앱 이벤트가 차단되면 거부 포스트백이 차단된 광고 네트워크로 즉시 전송됩니다.  
  참고:
  * 포스트백은 그것을 받기 위해 설정된 광고 네트워크가 앱스플라이어와 통합되어 있는 경우에만 전송됩니다.
  * 포스트백 및 거부된 포스트백 리포트는 내보내기 페이지에서 사용할 수 있습니다.
  * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">포스트백</Anchor> 및 <Anchor target="_blank" href="/partners/ko/docs/rejected-attribution-postbacks-to-integrated-partners">거부된 포스트백</Anchor>에 대해 자세히 알아보세요.
* 설치 및 IAE 귀속 차단은 AppsFlyer에서 데이터가 보고되는 방식과 위치에만 영향을 미칩니다. 최종 사용자의 앱 사용은 금지하지 않습니다.
  * 필요한 경우 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">차단된 인스톨 및 차단된 IAE 로데이터 리포트</Anchor> (내보내기, pull API 및 데이터 락커를 통해 사용할 수 있는)를 사용하여 비활성화할 앱 사용자 목록을 가져올 수 있습니다.
* 차단된 설치/IAE 보고서 및 거부된 포스트백에는 차단된 설치/IAE의 차단 사유 아래에 차단한 규칙의 이름이 포함됩니다. 하나 이상의 규칙이 있는 경우 [여러 규칙](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules) 섹션을 참조하십시오.
  * 인스톨/IAE가 Protect360 사기 방지 엔진에 의해 차단되면 유효성 검사 규칙이 있더라도 Protect360 이유가 표시됩니다.
* 규칙에 따라 앱스플라이어와 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-discrepancies">메타 광고</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-faq-and-discrepancies">구글 애드워즈</Anchor>와 같은 SRN이 설치를 검증하기 위해 자체 로직을 배포할 때 불일치가 보고될 수 있습니다.

</Accordion>

<div id="multiple-rules" />

<Accordion title="다중 규칙">

* 동일한 인스톨/IAE에서 다중 유효성 검증 규칙을 실행할 수 있습니다. 이 상황은 인스톨이 다중 규칙 조건을 충족할 때 발생합니다.
* 인스톨/IAE는 별도로 규칙의 조건을 준수하지 않는 경우 유효하지 않은 것으로 분류됩니다.
* 로데이터 리포트 및 거부된 포스트백에서 **차단 이유 값** 필드에는 설치 또는 인앱 벤트를 유효하지 않은 것으로 분류하는 모든 규칙의 이름이 포함됩니다.
* 동일한 인스톨에 대한 다중 규칙은 규칙의 차단 유형에 따라 다음 순서로 실행되도록 순서가 지정됩니다.

| 규칙/차단 유형 | 순서 |
| --- | --- |
| 인스톨 차단 | 무작위 |
| 어트리뷰션 차단 | 무작위 |
| 인앱 이벤트 차단 | 무작위 |
| 앱스플라이어에서 완전히 제거 및 그 밖의 다른 것 | 앱스플라이어에서 제거됩니다. 다른 규칙들은 무시됩니다. |
| 인스톨 차단 및 어트리뷰션 차단 | <ol><li>인스톨 차단 규칙(무작위 순서로)</li><li>어트리뷰션 차단 규칙(무작위 순서로)</li></ol> |
| Protect360 엔진 및 유효성 검사 규칙을 통한 인스톨 차단 및 어트리뷰션 차단 | <ol><li>Protect360 엔진으로부터 인스톨 차단</li><li>유효성 검사 규칙으로부터 인스톨 차단</li><li>Protect360 엔진으로부터 어트리뷰션 차단</li><li>유효성 검사 규칙으로부터 어트리뷰션 차단</li></ol> |
| Protect360 엔진 및 유효성 검사 규칙을 통한 인앱 이벤트 차단 | <ol><li>Protect360 엔진으로부터 IAE 차단</li><li>유효성 검사 규칙으로부터 IAE 차단</li></ol> |

</Accordion>

<div id="rule-builder" />

## 규칙 빌더

규칙 빌더 UI는 대화식으로 규칙을 작성하도록 고안되었습니다. **팁!** 팁! 이 항목을 자세히 살펴보기 전에, 규칙 빌더를 잘 알고 실험해보십시오.

![새 검증 규칙 페이지.jpg](https://files.readme.io/23875c647c24226c09f5aa2f4dbb85264f95b09e867a053ee55bc2d3ebbc9895-21855980276753.png)

규칙 빌더는 다음 섹션을 포함합니다.

| 섹션 | 비고 |
| --- | --- |
| 일반 세부 정보 | <ul><li>**규칙 이름 -** 새 규칙의 이름을 입력하십시오.</li><li>**규칙 유형 -** 규칙 유형을 선택하십시오, **실시간** 또는 **귀속 후**.</li><li>**이벤트** - 규칙이 적용되는 이벤트 유형을 선택하십시오, **설치** 또는 **인앱 이벤트**.</li><li>**앱 선택 -** **선택된 앱** 또는 **모든 앱**을 선택하십시오.<ul><li>**선택된 앱**이 선택된 경우:<br />**앱 선택 -** 규칙이 적용되는 앱을 선택하십시오 : 단일 앱, 여러 앱 또는 계정의 모든 앱.</li><li>**모든 앱**이 선택된 경우:<br />옵션 **미래 앱 포함 -** 이 규칙에 미래 앱을 포함할 수 있도록 허용합니다.</li></ul></li></ul>선택은 다음 섹션(에이전시, 미디어소스, 캠페인 등)에서 사용할 수 있는 옵션에 영향을 미칩니다.<br /><br /><br /><br />**참고**<br />앱 버전은 숫자만 포함해야 합니다. 예를 들어, 5.12345<br /><br />참고:<br /><br />숫자 앱 버전(예: 2.2.1)은 모든 연산자(같음, 큼, 작음 등)를 지원합니다.<br /><br />앱 버전이 사용자 정의 텍스트(예: version123 또는 our\_latest\_version)인 경우, "같음" 또는 "같지 않음" 연산자만 작동하며; "큼" 또는 "작음"은 적용되지 않습니다. |
| 트래픽 소스 | 규칙이 적용되는 트래픽 소스. [Protect360 소스를 참조하십시오](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| 조건 | 설치/앱 내 이벤트가 정의된 조건과 "일치"하거나 "일치하지 않도록" 차단할지 선택하세요.<ul><li>**조건 일치 -** 정의된 조건과 일치하는 설치/앱 내 이벤트에 대한 귀속이 차단되며, 아래에서 선택한 작업이 모두 적용됩니다.</li><li>**조건 불일치 -** 다음 조건과 일치하지 않는 설치/앱 내 이벤트에 대한 귀속이 차단되며, 아래에서 선택한 작업이 나머지 모두에 적용됩니다.</li></ul>인스톨 및 [인앱이벤트](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions)에 대해서는 또한 Protect360 조건을 참조하십시오. |
| 작업 | 인스톨의 경우: 지정된 조건을 충족하는 인스톨로 수행할 작업을 선택합니다.<ul><li>**설치를 유효하지 않은 것으로 표시하고 귀속하지 않음**. 설치는 Protect360 및 보고서를 제외한 AppsFlyer 대시보드에 나타나지 않습니다.</li><li>차단 어트리뷰션 및 마지막 유효한 미디어소스로 정정. 유효한 미디어 소스가 식별되지 않으면 설치는 유기적으로 간주됩니다.</li></ul>인앱 이벤트의 경우: 지정된 조건을 충족하는 인스톨로 수행할 작업을 선택합니다.<ul><li>**귀속 차단, 그러나 Protect360 데이터에 표시**. 이벤트는 귀속되지 않지만 Protect360 대시보드 및 원시 데이터에 표시됩니다.</li><li>**AppsFlyer에서 제거**. 이벤트는 AppsFlyer 플랫폼에 전혀 표시되지 않습니다.</li></ul>자세한 정보는 [결과](/docs/implement-validation-rules-to-prevent-fraud#outcomes)를 참조하십시오. |

<div id="install-sources" />

<Accordion title="인스톨 소스">

**소스** 섹션은 규칙이 적용되는 인스톨의 트래픽 소스를 정의하는 장소입니다.

다음 두 가지 초기 옵션이 있습니다.

* 전체 트래픽 모든 트래픽: 이 규칙은 소스(에이전시, 미디어소스, 캠페인, 오가닉 등)에 관계없이 모든 인스톨에 적용됩니다.    
  **참고**: 이 옵션은 유기적 설치를 포함하므로 추가 소스 정보를 선택할 수 없으며, 설치 차단 옵션만 사용할 수 있습니다. 이는 유기적 설치에 대한 귀속을 차단/수정할 수 없기 때문입니다.
* 논-오가닉만 논오가닉만 해당: 규칙은 다음 표에 설명된 필드, 연산자 및 값과 함께 사용자가 선택한 소스에 적용됩니다.

[인스톨](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) 및 [인앱 이벤트](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)에 대해 Protect360 고객은 추가적인 소스 옵션을 사용할 수 있습니다.

<table><thead><tr><th>필드</th><th>운영자</th><th>값</th><th>비고</th></tr></thead><tbody><tr><td>에이전시</td><td><ul><li>이 경우,</li></ul></td><td><ul><li>에이전시 및 에이전시 외 트래픽</li><li>에이전시 외 트래픽</li><li>투명 에이전시(메뉴)</li><li>비투명 에이전시(메뉴)</li></ul></td><td><ul><li> <span>비투명 에이전시:</span><ul><li>트래픽 소스를 공유하지 않는 에이전시입니다.</li><li>"비투명 에이전시" 또는 "에이전시 및 비에이전시 트래픽"을 선택하면 특정 미디어소스를 선택할 수 없습니다.</li><li>메타 광고와 X 광고는 투명하지 않은 에이전시를 선택한 경우에도 항상 에이전시가 소스로 공유해야 하기 때문에 계속 선택할 수 있습니다.</li></ul></li><li> <span>투명 에이전시:</span><ul><li>미디어소스를 지정하는 에이전시입니다.</li><li>선택한 앱 중 일부에 대해서만 투명한 에이전시는 비투명 에이전시 메뉴에 표시됩니다.</li></ul></li></ul></td></tr><tr><td>미디어 소스</td><td><ul><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>포함</span></li><li><span>포함하지 않음</span></li><li><span>시작 소스</span></li><li><span>다음으로 종료</span></li><li> <span>정규식 일치</span><span></span> </li></ul></td><td><ul><li><span>원하는 값 검색.</span></li><li><span>메뉴에서 선택. </span></li><li><span>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</span></li></ul></td><td rowspan="6"><ul><li> <span>메뉴는 다음에 기반합니다.</span><ul><li>선택한 앱 및 에이전시.</li><li>트래픽 양에 따라 정렬된 지난 30일간의 트래픽.</li></ul></li><li><span>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</span></li></ul></td></tr><tr><td>캠페인</td><td rowspan="5"><ul><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>포함</span></li><li><span>포함하지 않음</span></li><li><span>시작 소스</span></li><li><span>다음으로 종료</span></li><li><span>비어 있음</span></li><li><span>비어 있지 않음</span></li><li><span>정규식 일치</span></li></ul></td><td><ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택.</li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul></td></tr><tr><td>캠페인 ID</td><td rowspan="4"><ul><li><span>무료 텍스트만 해당.</span></li><li><span>여러 값을 공백으로 구분하여 추가 가능.</span></li></ul></td></tr><tr><td>광고 ID</td></tr><tr><td>광고세트 ID</td></tr><tr><td>광고 세트 이름</td></tr></tbody></table>

</Accordion>

<div id="install-conditions" />

<Accordion title="인스톨 조건">

**조건** 섹션은 인스톨이 차단되거나 마지막으로 유효한 소스로 인한 경우를 결정하는 조건을 정의하는 장소입니다.

모든 규칙에 다중 조건 및 조건 그룹을 추가할 수 있습니다.

조건은 다음 표에 요약된 조건, 연산자 및 값에 따라 정의됩니다.

<div id="bulk-upload" />

#### 대량 업로드

조건이 지원하는 경우 **목록에 있음** 또는 **목록에 없음** 연산자를 선택할 때, 새 항목을 추가할 때 CSV 파일을 대량 업로드할 수 있는 옵션이 있습니다.

설정 방법:

1. **목록에 포함** 또는 **목록에 포함되지 않음** 연산자를 선택하십시오.
2. 연산자 드롭다운 목록에서 **목록에 포함** 또는 **목록에 포함되지 않음**을 선택하십시오.
3. **새 항목 추가** 상자에서 **CSV 파일 업로드**를 선택하십시오.

참고: CSV 파일은 최대 17K 값을 포함할 수 있습니다.

[인스톨](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) 및 [인앱이벤트](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)에 대해 Protect360 고객은 추가 조건 옵션을 사용할 수 있습니다.

<table><thead><tr><th><span>조건</span></th><th><span>운영자</span></th><th><span>값</span></th><th><span>비고</span></th></tr></thead><tbody><tr><td><span>캠페인</span></td><td rowspan="6"><ul><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>포함하지 않음</span></li><li><span>포함</span></li><li><span>시작 소스</span></li><li><span>다음으로 종료</span></li><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>정규식 일치</span></li><li><span>비어 있음</span></li><li><span>비어 있지 않음</span></li></ul></td><td><ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택.</li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul></td><td rowspan="11"><ul><li> <span>메뉴는 다음에 기반합니다.</span><ul><li>선택한 앱 및 에이전시.</li><li>트래픽 빈도에 따라 정렬된 지난 30일간의 트래픽.</li></ul></li><li><span>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</span></li></ul></td></tr><tr><td><span>캠페인 ID</span></td><td rowspan="5"><ul><li><span>무료 텍스트만 해당.</span></li><li><span>여러 값을 공백으로 구분하여 추가 가능.</span></li></ul></td></tr><tr><td><span>광고 ID</span></td></tr><tr><td><span>광고세트 ID</span></td></tr><tr><td><span>광고 세트 이름</span></td></tr><tr><td><span>기기 유형</span></td></tr><tr><td><span>지역</span></td><td rowspan="3"><ul><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li></ul><br/> </td><td><ul><li><span>필요한 값 선택(국가명, 국가 코드, 주 또는 시에 기반).</span></li><li><span>메뉴에서 값 선택.</span></li></ul></td></tr><tr><td><span>플랫폼</span></td><td><span>메뉴에서 값 선택.</span></td></tr><tr><td><span>통화</span></td><td><p>통화만 가능합니다. 가능한 값:</p><p>USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF</p></td></tr><tr><td><span>수익</span></td><td><ul><li><span>하한</span></li><li><span>보다 작거나 동일</span></li><li><span>보다 큰</span></li><li><span>보다 크거나 동일</span></li><li><span>사이 값</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li></ul></td><td><ul><li><span>무료 텍스트만 해당.</span></li></ul></td></tr><tr><td><span>OS 버전</span></td><td><ul><li><span>보다 작은</span></li><li><span>보다 작거나 동일</span></li><li><span>보다 큰</span></li><li><span>보다 크거나 동일</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>사이 값</span></li><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li></ul></td><td><ul><li><span>원하는 값 검색.</span></li><li><span>메뉴에서 선택. </span></li><li><span>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</span></li></ul></td></tr><tr><td><span>룩백 일수</span></td><td><ul><li><span>보다 작은</span></li><li><span>보다 크거나 동일</span></li><li><span>사이 값</span></li></ul></td><td><ul><li>자유 텍스트 단일 숫자 값.</li></ul></td><td><ul><li><span>일 단위의 노출/클릭 기여 기간을 말합니다.</span></li><li><span>더 긴 어트리뷰션 기간을 허용하도록 수정된 어트리뷰션 링크를 통한 인스톨 비용을 지불하지 않습니다.</span></li><li><span>어트리뷰션 링크에서 기여 기간의 설정을 바꾸지 않습니다.</span></li><li> [권장] 어트리뷰션 터치 유형 조건과 함께 사용합니다(<span>Protect360과 함께 사용 가능</span>). </li></ul></td></tr><tr><td><span>사전 설치됨</span></td><td rowspan="2"><ul><li><span>예</span></li><li><span>아니요</span></li></ul></td><td rowspan="2"><ul><li>값 없음(연산자가 값입니다)</li></ul></td><td><ul><li> <span>모든 사전 설치 유형을 검증합니다.</span><ul><li><span>공장 사전 설치, OS의 일부로 기기에 제공되는 앱을 의미합니다.</span></li><li>제공된 사전 설치, 기기가 초기화되는 즉시 홍보 및 사용자에게 제공되는 앱을 의미합니다. 이 작업은 사전 설치용으로 지정된 미디어소스에 의해 수행됩니다.</li></ul></li><li>다중 클릭/소스를 통한 인스톨의 경우 이 조건은 소스 중 하나가 사전 설치인지 여부를 검증합니다.</li></ul></td></tr><tr><td><span>딥링크</span></td><td> <span>로데이터의 비어 있는 딥링크 필드는 </span>딥링크 = 아니요로 간주됩니다.</td></tr></tbody></table>

</Accordion>

<div id="inapp-event-sources" />

<Accordion title="인앱 이벤트 소스">

이벤트 섹션에서 **인앱이벤트**를 선택하면 **일반 소스 옵션** 외에도 고객이 규칙을 적용할 인앱이벤트를 정의하는 다른 소스 옵션이 제공됩니다.

소스는 필드, 연산자 및 다음 표에 요약된 값에 따라 정의됩니다.

**참고**: 일러두기: 다른 모든 인앱이벤트 소스는 IAE가 연결된 설치 소스(예: 에이전시, 미디어 소스, 캠페인, 캠페인 ID, 사이트 ID 등)를 기반으로 합니다.

| 필드 | 운영자 | 값 | 비고 |
| --- | --- | --- | --- |
| 이벤트 이름 | <ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li><li>포함</li><li>포함하지 않음</li><li>시작 소스</li><li>다음으로 종료</li><li>비어 있음</li><li>비어 있지 않음</li><li>정규식 일치</li></ul> | <ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택.</li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul> | <ul><li>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</li></ul> |

</Accordion>

<div id="inapp-event-conditions" />

<Accordion title="인앱이벤트 조건">

**앱 내 이벤트**가 **이벤트** 섹션에서 선택되면 고객은 규칙이 적용되는 앱 내 이벤트를 정의하기 위한 추가 조건 옵션을 갖습니다. 이 조건은 비-Protect360 조건과 혼합하여 사용할 수 있습니다 [이전에 나열된](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Protect360 조건은 다음 표에 요약된 조건, 연산자 및 값에 따라 정의됩니다.

| 조건 | 운영자 | 값 | 비고 |
| --- | --- | --- | --- |
| 이벤트 이름 | <ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li><li>포함</li><li>포함하지 않음</li><li>시작 소스</li><li>다음으로 종료</li><li>비어 있음</li><li>비어 있지 않음</li><li>정규식 일치</li></ul> | <ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택.</li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul> | <ul><li>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</li></ul> |

</Accordion>

<div id="protect360-install-and-inapp-event-sources" />

<Accordion title="Protect360 인스톨 및 인앱이벤트 소스">

일반 소스 옵션 외에도 Protect360 고객에게는 규칙이 적용되는 인스톨을 정의할 수 있는 다른 소스 옵션이 있습니다. 소스는 필드, 연산자 및 다음 표에 요약된 값에 따라 정의됩니다.

| 필드 | 운영자 | 값 | 비고 |
| --- | --- | --- | --- |
| 사이트 ID | <ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li><li>포함</li><li>포함하지 않음</li><li>시작 소스</li><li>다음으로 종료</li><li>비어 있음</li><li>비어 있지 않음</li><li>정규식 일치</li></ul> | <ul><li>무료 텍스트만 해당.</li><li>여러 값을 공백으로 구분하여 추가 가능.</li></ul> | <ul><li>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</li></ul> |

</Accordion>

<div id="protect360-install-conditions" />

<Accordion title="Protect360 설치 조건">

Protect360 고객은 설치를 검증하기 위한 추가 조건 세트를 갖습니다. 이 조건은 비-Protect360 조건과 혼합하여 사용할 수 있습니다 [이전에 나열된](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Protect360 조건은 다음 표에 요약된 조건, 연산자 및 값에 따라 정의됩니다.

<table><thead><tr><th><span>조건</span></th><th><span>운영자</span></th><th><span>값</span></th><th><span>비고</span></th></tr></thead><tbody><tr><td><span>CTIT(Click Time to Install Time)</span></td><td><ul><li><span>보다 작은</span></li><li><span>보다 크거나 동일</span></li><li><span>사이 값</span></li></ul></td><td><ul><li>자유 텍스트 단일 숫자 값.</li></ul></td><td><ul><li> 특정 CTIT(일반적으로 특정 지역)가 확실한 경우에만 이 필드를 사용합니다. 그렇지 않으면 인스톨이 거짓 양성으로 차단될 수 있습니다.<br/><span><strong>참고</strong>: 일러두기: Protect360 사기 방지 엔진에는 속성 하이재킹, 클릭 플러딩, 봇에 의한 가짜 설치 등으로 인한 복잡한 CTIT 이상을 식별하는 정교한 방법이 내장되어 있습니다. </span> </li><li> <span>이 필드를 다음 필드와 함께 사용해 보십시오.</span><ul><li>사전 설치</li><li>딥링크</li><li>지역</li></ul></li></ul></td></tr><tr><td><span>고객 사용자 ID(Customer User ID, CUID)</span></td><td><ul><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>포함하지 않음</span></li><li><span>포함</span></li><li><span>시작 소스</span></li><li><span>다음으로 종료</span></li><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>정규식 일치</span></li><li><span>비어 있음</span></li><li><span>비어 있지 않음</span></li></ul></td><td><ul><li><span>무료 텍스트만 해당.</span></li><li><span>여러 값을 공백으로 구분하여 추가 가능.</span></li></ul></td><td><ul><li> <span>메뉴는 지</span>난 30일 동안의 트래픽을 기준으로 트래픽 빈도에 따라 정렬됩니다.</li><li><span>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</span></li></ul><br/><br/> </td></tr><tr><td><span>앱 버전</span></td><td><ul><li><span>보다 작은</span></li><li><span>보다 작거나 동일</span></li><li><span>보다 큰</span></li><li><span>보다 크거나 동일</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>사이 값</span></li><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li><li><span>마지막이 아님</span></li><li><span>마지막이 아님(주요)</span></li></ul></td><td><ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택. </li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul></td><td><ul><li> <span>메뉴는 지</span>난 30일 동안의 트래픽을 기준으로 트래픽 빈도에 따라 정렬됩니다.</li><li><span>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</span></li><li> "마지막이 아님"에 대해 버전이 두 개 이상인 경우 "마지막이 아님(주요)"을 선택합니다. <a href="./implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work"><span>더 알아보기</span></a> </li></ul></td></tr><tr><td><span>SDK 버전</span></td><td><ul><li><span>보다 작은</span></li><li><span>보다 작거나 동일</span></li><li><span>보다 큰</span></li><li><span>보다 크거나 동일</span></li><li><span>동일함</span></li><li><span>동일하지 않음</span></li><li><span>사이 값</span></li><li><span>목록에 있음</span></li><li><span>목록에 없음</span></li></ul></td><td><ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택. </li><li>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</li></ul></td><td><ul><li> <span>메뉴는 지</span>난 30일 동안의 트래픽을 기준으로 트래픽 빈도에 따라 정렬됩니다.</li><li><span>무료 텍스트는 로데이터에 표시되는 대로 정확하게 입력해야 합니다.</span></li></ul></td></tr><tr><td><span>인스톨러/스토어</span></td><td rowspan="3"><ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li></ul></td><td> <span>메뉴에서 값 선택.</span><ul><li>구글 플레이</li><li>기타 스토어</li><li>스토어 외부</li></ul></td><td><ul><li>구글 플레이 AppsFlyer는 설치 패키지가 <code>com.android.vending</code>임을 식별합니다.</li><li>기타 스토어 기타 스토어: 앱스플라이어는 인스톨이 써드파티 안드로이드 스토어의 것임을 식별합니다.</li><li>스토어 외부 스토어 외부: 앱스플라이어는 안드로이드 스토어에 없는 APK를 식별합니다.</li></ul><span>사용자의 장치에서 앱스플라이어에 인스톨러/스토어 파라미터를 제공하지 않는 경우 규칙이 적용되지 않습니다.</span> </td></tr><tr><td>사용자 정의 설치 프로그램/스토어</td><td>무료 텍스트(검색 결과에 나타나지 않는 값에 대해).</td><td><ul><li>클라이언트가 "기타" 조건과 사용자 정의 설치 프로그램=X 조건을 선택한 경우 - 차단은 설치 프로그램 X에 대해서만 적용됩니다.</li><li>클라이언트가 "기타" 조건 또는 사용자 정의 설치 프로그램=X 조건을 선택한 경우 - 차단은 모든 "기타" 설치 프로그램/스토어에 적용되며 - X는 해당 그룹의 일부입니다.</li></ul></td></tr><tr><td><span>어트리뷰션 터치 유형</span></td><td><ul><li><span>클릭</span></li><li><span>노출</span></li></ul></td><td><ul><li>[권장 사항] 룩백 날짜 조건과 함께 사용합니다.</li><li>단순히 노출에 대해 어트리뷰트하지 않으려면 <a href="./measure-view-through-engagements#turn-off-viewthroughattribution" target="_blank">뷰-스루 어트리뷰션을 끌 수 있습니다</a>.</li></ul></td></tr><tr><td><span>통신사</span></td><td><ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li></ul></td><td><ul><li>무료 텍스트만 해당.</li></ul></td><td> </td></tr><tr><td><span>유저 에이전트</span></td><td><ul><li>포함</li><li>포함하지 않음</li></ul></td><td><ul><li>무료 텍스트만 해당.</li></ul></td><td> </td></tr><tr><td>IP 주소</td><td><ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li></ul></td><td><ul><li>무료 텍스트만 해당.</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="protect360-inapp-event-conditions" />

<Accordion title="Protect360 인앱이벤트 조건">

선택한 **앱 내 이벤트**가 **이벤트** 섹션에 있으면, Protect360 고객은 규칙이 적용될 앱 내 이벤트를 정의하기 위한 추가 조건 옵션을 가집니다. 이 조건은 비-Protect360 조건 [이전에 나열된](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)와 함께 혼합 및 조합할 수 있습니다.

Protect360 조건은 다음 표에 요약된 조건, 연산자 및 값에 따라 정의됩니다.

| 조건 | 운영자 | 값 | 비고 |
| --- | --- | --- | --- |
| 이벤트 소스 | <ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li></ul> | <ul><li>원하는 값 검색.</li><li>메뉴에서 값 선택.</li></ul> | SDK 또는 서버 간 선택하세요. |
| 이벤트 값 | <ul><li>목록에 있음</li><li>목록에 없음</li><li>동일함</li><li>동일하지 않음</li><li>포함</li><li>포함하지 않음</li><li>시작 소스</li><li>다음으로 종료</li><li>비어 있음</li><li>비어 있지 않음</li><li>정규식 일치</li></ul> | <ul><li>무료 텍스트만 해당.</li><li>여러 값을 공백으로 구분하여 추가 가능.</li></ul> | <ul><li>선호하는 값을 선택하세요.</li></ul> |
| 인스톨 투 이벤트 시간(초 단위) | <ul><li>보다 작은</li><li>보다 크거나 동일</li><li>사이 값</li></ul> | 자유 텍스트 단일 숫자 값. | <ul><li>앱의 흐름에 따라 앱 인스톨과 IAE 사이 통과하는 올바른 시간을 결정합니다.<ul><li>예시: 예: 레벨 5 도달 시간, 최초 입금 시간(FTD), 체크아웃 시간 등.</li></ul></li><li>시간은 초 단위이지만 초 등가물을 사용하여 분, 시간 또는 일의 유효성을 검사할 수 있습니다.</li></ul> |

</Accordion>

<div id="logic-between-conditions-and-condition-groups" />

<Accordion title="조건과 조건 그룹 간의 논리">

규칙에 다중 조건 또는 조건 그룹을 추가하는 경우 다음 중 하나를 사용하여 조건 또는 조건 그룹 간의 논리적 관계를 선택합니다. 

* 별개로 AND: 인스톨이 정의된 모든 조건을 준수한다는 의미합니다.
* 또는 OR: 인스톨이 정의된 조건 중 하나 이상을 준수함을 의미합니다.

예를 들어 플랫폼과 OS 모두에 기반한 인스톨을 검증하려면 AND를 선택해야 합니다. 이렇게 하면 정의된 플랫폼은 항상 정의된 OS에 있어야 합니다. 플랫폼 또는 OS에 기반한 인스톨을 검증하려면 OR을 선택해야 합니다.

</Accordion>

<div id="additional-features" />

## 절차

<div id="view-rule-list" />

<Accordion title="규칙 목록 보기">

**계정에 생성된 모든 규칙을 보는 방법**:

1. AppsFlyer에서 **설정** > **검증 규칙.**  
   검증 규칙 창이 열리며, 검증 규칙 목록이 표시됩니다.
2. **목록 보기/상세 보기** 토글을 사용하여 원하는 표 보기를 선택합니다.
3. 검색 및 필터 옵션을 사용하여 목록의 규칙을 필터링합니다.
   * 규칙 이름, 소스, 조건 이름 및 값을 기준으로 검색할 수 있습니다.
   * 예를 들어 7이 포함된 OS 버전에 대해 정의된 모든 규칙을 찾으려면 **7**을 입력합니다(예: “2.7.4”, “7.1”, 등). “2.7.4”, “7.1”, etc.). 또는 지역 조건에서 캐나다로 정의된 규칙을 찾으려면 캐나다를 입력합니다.

</Accordion>

<div id="add-rule" />

<Accordion title="룰 추가">

**새 규칙을 설정하는 방법**:

1. AppsFlyer에서 **설정** > **검증 규칙.**  
   검증 규칙 창이 열립니다.
2. 클릭 **규칙 추가.**  
   새 규칙 추가 창이 열립니다.
3. **규칙 이름**을 입력합니다.  다음과 같은 고유 이름을 사용하십시오.
   * 규칙을 정확하게 설명하는 이름.
   * 광고 네트워크에 대한 거부된 포스트백뿐만 아니라 차단된 인스톨 리포트에 표시되므로 광고 네트워크에 해를 끼치지 않는 이름.
4. [규칙 빌더 섹션](/docs/implement-validation-rules-to-prevent-fraud#규칙-빌더)을 완료합니다.
5. [선택 사항] 필요에 따라 조건 및/또는 조건 그룹을 추가합니다. [조건/조건 그룹 간에 관련 논리](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups)를 선택해야 합니다.
6. [선택사항] **트래픽 영향 평가**[를 클릭하여](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact) 규칙이 트래픽에 영향을 주는지를 보십시오.
7. **저장**을 클릭하세요.

<div id="note-2" />

> 📘 **참고**
>
> 앱 버전은 숫자만 포함해야 합니다. 예를 들어, 5.12345
>
> 참고:
>
> 숫자 앱 버전(예: 2.2.1)은 모든 연산자(같음, 큼, 작음 등)를 지원합니다.
>
> 앱 버전이 사용자 정의 텍스트(예: version123 또는 our\_latest\_version)인 경우, "같음" 또는 "같지 않음" 연산자만 작동하며; "큼" 또는 "작음"은 적용되지 않습니다.

<div id="view-validation-rule-impact" />

<Accordion title="유효성 검증 규칙 영향 보기">

유효성 검증 규칙이 트래픽에 미치는 예상 영향, 예를 들어 차단된 인스톨 및 차단된 어트리뷰션 수를 참조하십시오. 

![vr_estimate.png](https://support.appsflyer.com/hc/article_attachments/360019928077)

> 📘 **참고**
>
> * 유효성 검증 규칙 추정기는 광고주만 액세스할 수 있습니다. 파트너는 액세스할 수 없습니다.
> * 평가는 인앱이벤트 관련 규칙이 아닌 인스톨 관련 규칙에 대해 사용할 수 있습니다.
> * 또한 예측에는 규칙에 적용되는 항목이 표시되지만 이미 Protect360 사기 방지, 다른 유효성 검증 규칙에 의해 차단되어 있거나 예상 규칙이 새로운 규칙이 아닌 경우 이전 설정에 의해 차단된 트래픽도 표시됩니다.

**유효성 검증 규칙의 예상 영향을 보는 방법**:

1. 앱스플라이어에서 **유효성 검증 규칙**으로 이동합니다.
2. 현재 규칙을 선택하거나 **+ 규칙 추가**를 [클릭하여 규칙 소스와 조건으로](/docs/implement-validation-rules-to-prevent-fraud#add-rule) 새 규칙을 생성하십시오.
3. 규칙의 맨 아래로 스크롤하고 클릭 **트래픽 영향 추정**.  
   규칙의 추정 영향 창이 열립니다.
4. 마지막 날짜의 데이터에 대한 예상 영향을 기준으로 할지 아니면 지난 7일의 데이터를 기준으로 할지 선택합니다.
   * 예상된 새 차단과 유효성 검증 규칙으로 인해 새로 차단된 트래픽 비율이 표시됩니다.
   * 규칙이 비유기적 소스에만 정의된 경우, 추정치는 규칙의 영향이 모든 트래픽에 대해 표시됩니다. 특정 미디어 소스나 캠페인과 같은 소스에 대한 영향을 보려면, 차트 범례에서 **기타 소스**의 선택을 해제하세요.  
     [![](https://support.appsflyer.com/hc/article_attachments/360020016218)](https://support.appsflyer.com/hc/article_attachments/360020016218)

</Accordion>

<div id="edit-or-delete-a-rule" />

<Accordion title="규칙 수정 또는 삭제">

**규칙을 편집, 삭제, 활성화 또는 비활성화하는 방법**:

* [규칙 목록](/docs/implement-validation-rules-to-prevent-fraud)에서 특정 규칙에 대해 수행할 작업을 선택합니다.
  * **활성화**에서 규칙을 활성화 또는 비활성화합니다.
  * **액션**에서 규칙을 편집 또는 삭제합니다.

</Accordion>

</Accordion>

<div id="faq" />

## 자주 묻는 질문

<div id="what-is-a-regular-expression" />

<Accordion title="'정규식'이란 무엇입니까?">

정규식 패턴은 일치를 찾으려는 문자로 구성됩니다. 단순 패턴은 직접 일치시킬 문자를 사용하여 구성됩니다. 일치 항목 검색에 직접 일치 항목 이상이 필요한 경우 패턴에 특수 문자를 포함할 수 있습니다.

**예**:

| **정규식** | **설명** |
| --- | --- |
| ^abc | abc로 시작함 |
| xyz$ | xyz로 끝남 |
| ^abc.*xyz$ | abc로 시작하고 xyz로 끝남 |
| ^abc.*(?&lt;xyz)$ | abc로 시작하고 xyz로 끝나지 않음 |
| ^([0-9]`{2}`) | 2자리로 시작함 |
| \"example\_param\":\"[5\|6] | 5 또는 6으로 시작하는 지정된 파라미터 값. |
|  | 비어 있거나 `{}`만 포함합니다. |

</Accordion>

<div id="why-doesnt-the-source-or-condition-display-as-a-suggested-value-when-i-search-for-it" />

<Accordion title="소스 또는 조건을 검색할 때 제안 값으로 표시되지 않는 이유는 무엇입니까?">

두 가지 가능한 이유 때문입니다.

* 관련 앱이 선택되었는지 확인하십시오. 앱을 선택하지 않으면 검색 결과에 값이 표시되지 않습니다.
* 검색 중인 값이 지난 30일 동안 트래픽에 나타난 경우에만 결과가 표시됩니다. 또한 변환이 발생한 시점과 소스 또는 조건이 메뉴 옵션으로 표시되는 시점 사이에 최대 1일의 지연이 있습니다.

값이 검색 결과로 나타나지 않으면 값을 자유 텍스트로 입력하고 키보드에서 Enter 키를 누를 수 있습니다.

</Accordion>

<div id="why-do-my-media-source-options-only-include-facebook-ads-and-twitter" />

<Accordion title="미디어소스 옵션에 메타 광고와 X 광고만 포함되는 이유는?">

미디어소스(Media Sources) 필드 옵션은 에이전시(Agency) 선택에 영향을 받습니다. 트래픽 소스 중 하나로 '불투명 에이전시'를 선택하면 메타 광고와 트위터를 제외한 미디어소스가 표시되지 않으며, 이는 불투명한 에이전시도 투명해야 합니다.

**참고**: 참고: 규칙이 여러 앱에 적용되는 경우, 선택한 앱 중 일부에서는 투명하지만 다른 앱에서는 투명하지 않은 에이전시는 투명하지 않은 것으로 간주됩니다. 즉, 메타 광고 또는 트위터 이외의 특정 미디어소스를 선택할 수 없습니다.

</Accordion>

<div id="is-it-necessary-to-have-andor-both-within-specific-conditions-and-between-condition-groups" />

<Accordion title="특정 조건 내 또는 조건 그룹 간에 모두 '및/또는'가 필요합니까?">

그것은 사용 사례에 따라 다릅니다. 경우에 따라 두 옵션 모두 동일한 결과를 얻을 수 있습니다. 두 가지 옵션이 모두 필요한 경우도 있습니다.

예를 들어 미국에서는 OS V10 이상에서만 인스톨을 지원하지만 브라질에서는 V7 이상에서 지원하는 경우 다음과 같은 규칙이 필요합니다.

`{[Geo = US] 및 [OS 버전 = 10]} 또는 {[Geo = Brazil] 및 [OS 버전 = 7]}`

</Accordion>

<div id="do-validation-rules-block-clicks" />

<Accordion title="유효성 검증 규칙이 클릭을 차단합니까?">

아닙니다. 유효성 검증 규칙은 인스톨을 차단하거나 인스톨 소스에 대한 어트리뷰션을 차단하거나(클릭/노출의 미디어소스가 어트리뷰션을 수신하지 못하도록 함) 인앱이벤트를 차단할 수 있습니다. 그러나 이러한 옵션 중 어느 것도 실제 클릭을 차단하지 않으며 클릭 KPI는 유효성 검증 규칙 실행의 영향을 받지 않습니다.

</Accordion>

<div id="looking-at-the-raw-data-i-see-that-installs-i-expected-to-be-blocked-by-validation-rules-have-a-different-block-reason-than-my-rule-name-why-is-that" />

<Accordion title="로데이터를 보면 유효성 검증 규칙에 의해 차단될 것으로 예상되는 인스톨의 차단 이유가 내 규칙 이름과 다른 것을 알 수 있습니다. 왜 그렇게 됩니까?">

이는 차단이 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#차단된-이유">Protect360 엔진</Anchor> 때문이며 유효성 검사 규칙 때문이 아님을 의미합니다. 또한 [다중 규칙](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules)을 참조하십시오.

</Accordion>

<div id="do-existing-rules-automatically-apply-for-newlyintegrated-agency-traffic" />

<Accordion title="새로 연동된 에이전시 트래픽에 기존 규칙이 자동으로 적용됩니까?">

이것은 아래 표에 설명된 대로 **소스** 설정에 따라 다릅니다.

규칙이 자동으로 적용되지 않으면 다음과 같이 규칙을 편집해야 합니다.

* 에이전시 필드를 **에이전시 및 비 에이전시 트래픽**으로 변경하거나 특정 에이전시를 선택합니다.

<table><thead><tr><th>소스 설정</th><th>에이전시 필드 선택</th><th>모든 에이전시가 앱 중 하나와 연동되기 전에 규칙이 만들어진 경우 규칙이 적용됩니까?</th><th>하나 이상의 에이전시가 앱 중 하나와 연동되기 전에 규칙이 만들어진 경우 규칙이 적용됩니까?</th></tr></thead><tbody><tr><td><span>전체 트래픽</span></td><td><span>N/R</span></td><td><span>예</span></td><td><span>예</span></td></tr><tr><td rowspan="3"> <br/><span>논-오가닉만</span> </td><td><span>N/R</span></td><td><span>아니요</span></td><td><span>N/R</span></td></tr><tr><td><span>에이전시 및 에이전시 외 트래픽</span></td><td><span>N/R</span></td><td><span>예</span></td></tr><tr><td><p><span>비 에이전시 트래픽 및/또는</span></p><p><span>특정 에이전시</span></p></td><td><span>N/R</span></td><td><span>아니요</span></td></tr></tbody></table>

</Accordion>

<div id="how-do-the-not-in-last-conditions-work" />

<Accordion title="'마지막이 아님' 조건은 어떻게 작동합니까?">

마지막이 아님은 유효성 검사 규칙에 포함하려는 일련의 앱 버전이 있을 때 사용되는 조건입니다. 마지막이 아님(주요)은 유효성 검사 규칙에 포함하려는 앱 버전 시리즈가 *두 개* 이상 있을 때 사용되는 조건입니다.

예시:

* 앱 버전 1.0 및 2.0 시리즈가 있습니다.
* 모든 기존 앱 버전:
  * 1.0.01
  * 1.0.02
  * 1.0.03
  * 2.0.01
  * 2.0.02
  * 2.0.03
* "최근 2개 버전이 아님"으로 정의된 규칙은 다음을 차단합니다.
  * 2.0.02
  * 2.0.03
* "최근 2개 버전(주요)이 아님"으로 정의된 규칙은 다음을 차단합니다.
  * 1.0.02
  * 1.0.03
  * 2.0.02
  * 2.0.03

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 설명 |
| --- | --- |
| 계정 유저 액세스 | 적절한 권한을 가진 계정 사용자만 유효성 검증 규칙을 보고 추가하고 편집할 수 있습니다. |
| 유저 유입 | 유효성 검증 규칙은 인스톨, 리인스톨 및 리어트리뷰션(앱이 장치에서 제거되었을 때)에 적용됩니다. 앱이 장치에 아직 있는 경우인 리인게이지먼트의 경우에는 적용되지 않습니다. |
| 자동 규칙 비활성화 | 규칙을 생성한 경우:<ul><li>Protect360 소스 또는 조건을 사용하고 Protect360 라이선스 또는 평가판이 만료되면 규칙이 자동으로 비활성화됩니다.</li><li>투명 에이전시 트래픽의 경우 하나 이상의 에이전시가 투명하지 않게 되면 규칙이 자동으로 비활성화됩니다.</li></ul> |
| 애드 네트워크 | 규칙 세부 정보를 보려면 **유효성 검증 규칙 보기**에 대한 광고주 권한이 필요합니다. **참고**: 일러두기: 규칙 이름은 항상 표시됩니다(로데이터 포함).<br /><br /><Anchor target="_blank" href="/partners/ko/docs/validation-rules-for-ad-networks-and-agencies">광고 네트워크의 유효성 검증 규칙에 대해 자세히 알아보기</Anchor> |
| 대행사 | 다음에 대한 광고주 권한 필수:<ul><li>규칙 세부 정보를 보려면 **유효성 검증 규칙**을 보십시오. **참고**: 일러두기: 규칙 이름은 항상 표시됩니다(로데이터 포함).</li><li>규칙을 추가 및 편집하려면 **유효성 검사 규칙**을 추가합니다. **참고**: 에이전시는 광고주가 만든 규칙을 편집할 수 없습니다.</li><li>Protect360 대시보드 및 로데이터에 액세스하여 Protect360 조건으로 규칙을 보고 추가합니다.</li></ul>에이전시의 유효성 검증 규칙에 대해 자세히 알아보기 |
| 고유 유저 | 100개 이상의 인앱이벤트가 구성된 경우 유효성 검증 규칙을 사용하여 특정 인앱이벤트를 무효화하더라도 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#limitations">고유 유저 수에 대한 제한</Anchor>은 계속 적용됩니다. 즉, 100개 이상의 이벤트는 유효성 검증 규칙에 의해 무효화되더라도 고유 유저 수가 계산되지 않습니다. |
| SKAN | 지원되지 않음 |

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H8VFA2ADGT4AMC0NGDFXRB6Z=%EA%B0%9C%EC%9A%94 01H8VFA2AD99JSA6F6A3GKEXWV=outcomes 01H8VFA2AD9XSKKWHGM8KMN94Y=multiple-rules rule-builder=%EA%B7%9C%EC%B9%99-%EB%B9%8C%EB%8D%94 01H8VFA2ADQVCR8RYV9SBG52R7=%EA%B7%9C%EC%B9%99-%EB%B9%8C%EB%8D%94 h_01JK5G66CM9TCDK6GATNZC4QMW=%EC%B0%B8%EA%B3%A0 01H8VFA2AD5Q2ZAB8BWEC7G1CF=install-sources 01H8VFA2AE4SEX1XRNVNHZ42TH=install-conditions bulk-upload=%EB%8C%80%EB%9F%89-%EC%97%85%EB%A1%9C%EB%93%9C h_01J4HRXAH6DEXXQZZ3YAWHY4TP=%EB%8C%80%EB%9F%89-%EC%97%85%EB%A1%9C%EB%93%9C 01H8VFA2AE3SQ2X25JSXMS1SEY=inapp-event-sources 01H8VFA2AEDNXY70WZFBHFMB0S=inapp-event-conditions 01H8VFA2AFYDB1RADDJFP34Q4M=protect360-install-and-inapp-event-sources 01H8VFA2AFHYK26P44VE16F4E4=protect360-install-conditions 01H8VFA2AFJGSFFM9QASF0H0Z4=protect360-inapp-event-conditions 01H8VFA2AFWE5FVC87XHWHVBBK=logic-between-conditions-and-condition-groups procedures=%EC%A0%88%EC%B0%A8 01H8VFA2AF6M84FKKVDTCXJEFR=%EC%A0%88%EC%B0%A8 01H8VFA2AFJFYFBA5HY2DH55VM=view-rule-list 01H8VFA2AF6CSC9W0949RFJ7C6=add-rule h_01JK5GDDGAZRKBVXZCCZ0RRB56=%EC%B0%B8%EA%B3%A0 01H8VFA2AG2SWC9DVYWJXYNGXX=view-validation-rule-impact 01H8VFA2AGZD0GS67SDW6BM4NC=%EC%B0%B8%EA%B3%A0-1 01H8VFA2AGAS3HH45Y5RJY1AA0=edit-or-delete-a-rule faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H8VFA2AG5DW5Z9G9FPSWM464=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H8VFA2AG49TT9HJZV03DV9FZ=what-is-a-regular-expression 01H8VFA2AGRG6D4MN0512E3T5C=why-doesnt-the-source-or-condition-display-as-a-suggested-value-when-i-search-for-it 01H8VFA2AGRQ5QTP081D9ED2VY=why-do-my-media-source-options-only-include-facebook-ads-and-twitter 01H8VFA2AGNTQZJEYTMM1FE5QM=is-it-necessary-to-have-andor-both-within-specific-conditions-and-between-condition-groups 01H8VFA2AGVJVBKG6SGZQJQD79=do-validation-rules-block-clicks 01H8VFA2AG4GNGMBW31HT4JF1W=looking-at-the-raw-data-i-see-that-installs-i-expected-to-be-blocked-by-validation-rules-have-a-different-block-reason-than-my-rule-name-why-is-that 01H8VFA2AGAK9BMAHTHQ3DFW2N=do-existing-rules-automatically-apply-for-newlyintegrated-agency-traffic 01H8VFA2AGACRX511105Z06XKK=how-do-the-not-in-last-conditions-work 01H8VFA2AHHEYDV763QQ6KPMWK=traits-and-limitations" />
