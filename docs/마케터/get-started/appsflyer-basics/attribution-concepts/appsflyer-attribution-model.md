---
title: 앱스플라이어 어트리뷰션 모델
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
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
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-10-14T10:31:27Z'
  id: 207447053
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/207447053
---
> **요약:** 앱스플라이어는 사용자가 앱을 인스톨하거나 다시 참여하도록 동기를 부여한 미디어 소스를 파악하고, 앱스플라이어 어트리뷰션 모델을 사용해 해당 소스에 사용자의 행동을 어트리뷰트합니다.

 [![](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)

## 어트리뷰션이란 무엇인가요?

**어트리뷰션**은 사용자가 앱을 인스톨하거나 리인게이지먼트, 리어트리뷰션과 같은 인앱 활동을 수행하도록 동기를 부여한 요인을 판단하는 행위입니다. 어트리뷰션 결과는 다음 중 하나입니다.

* **논오가닉 미디어 소스**: 사용자는 미디어 소스와 상호 작용(일반적으로 노출 또는 클릭을 통해)했습니다.
* **오가닉**: 사용자는 미디어 소스와 상호 작용하지 않았습니다. 주의! 이해의 편의를 위해, 종종 사용자가 *오가닉하게 어트리뷰션*되었다고 말합니다. 엄밀히 말하면 이는 사실이 아닙니다. 오가닉하게 앱을 설치하는 사용자는 전혀 기여하지 않기 때문입니다.

어트리뷰션은 유저 유입, 리인게이지먼트 노력 및 결과를 최적화하는 데 필수입니다.

> 👍 **팁**
>
> 어트리뷰션에 대해 더 알고 싶으신가요? <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7766/play/18609/attribution-101-part-1">앱스플라이어 학습 포털에서 짧지만 유익한 강의 코스</Anchor>를 확인해 보세요.

## 앱 인스톨이란 무엇인가요?

**어트리뷰션 모델**은 전환 경로의 터치포인트에 이벤트에 대한 기여도를 할당하는 방법을 결정하는 일련의 규칙입니다. 앱 마케팅 생태계의 각 플레이어(구글 플레이, 애플 앱 스토어, Apple, CTV, PC 및 콘솔 플랫폼, Meta Ads 및 X Ads와 같은 애드 네트워크, 모바일 측정 회사)는 자체적인 어트리뷰션 모델을 갖고 있습니다. 각각 인스톨과 이벤트를 다르게 계산합니다.

중요한 것은 모델 간의 차이가 아니라 규칙이 명확하고 편향 없이 구현되는 것입니다. 광고주가 캠페인을 최적화하고 유저 가치를 비교할 수 있도록 지원합니다.

함께 일하는 플레이어의 모델과 규칙을 이해하는 것이 중요합니다. 가장 중요한 것은 앱스플라이어가 지원하는 방법의 모델과 뉘앙스를 이해하는 것입니다.

앱스플라이어에서는 다음 중 하나가 발생하면 어트리뷰션이 가능한 이벤트가 발생합니다.

* 유저 유입의 맥락에서: **인스톨**은 사용자가 앱을 다운로드하고 실행한 후에 기록되고 어트리뷰트됩니다. 이는 앱스플라이어에서 앱 **인스톨 타임스탬프가 앱 최초 오픈** 타임스탬프임을 의미합니다. 이와 달리, 애드 네트워크는 인게이지먼트 시간을, 앱 스토어는 다운로드 시간을 사용합니다.
* [리타겟팅](/docs/appsflyer-attribution-model#retargeting-attribution)의 맥락에서:
  * **리인게이지먼트**
  * **리어트리뷰션**

## 어트리뷰션 메서드

앱스플라이어는 다음 표에 나열된 여러 가지 어트리뷰션 메서드를 사용합니다.

<table><thead><tr><th>메서드</th><th>디바이스 ID 사용</th><th>기술</th><th>어트리뷰션 주체</th><th><p>안드로이드 (구글 플레이 및 써드 파티 스토어)</p></th><th>iOS </th><th>유니버설 윈도우 플랫폼(UWP)</th><th>CTV, PC, 콘솔 플랫폼(3)</th></tr></thead><tbody><tr><td> <a href="#install-referrer-android-only">리퍼러</a> (1)</td><td>아니오</td><td>결정론적</td><td>앱스플라이어</td><td>예 (2)</td><td>아니오</td><td>예</td><td>아니오</td></tr><tr><td> <a href="#device-id-matching">디바이스 ID 매칭</a> (1)</td><td>예</td><td>결정론적</td><td>앱스플라이어</td><td>예 </td><td>예</td><td>예</td><td>예</td></tr><tr><td> <a href="#probabilistic-modeling">확률적 모델링</a> (1)</td><td>아니오</td><td>확률론적</td><td>앱스플라이어</td><td>예 </td><td>예 </td><td>아니오</td><td>예</td></tr><tr><td> <a href="#aggregated-advanced-privacy-aap">데이터 집약형 프라이버시 강화(AAP)</a> (1)</td><td>아니오</td><td>집합</td><td>앱스플라이어</td><td>아니오</td><td>예</td><td>아니오</td><td>아니오</td></tr><tr><td> <a href="#preload-campaigns">프리로드</a> (1)</td><td>아니오</td><td>결정론적</td><td>앱스플라이어</td><td>예</td><td>아니오</td><td>예</td><td>아니오</td></tr><tr><td> <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a>(SKAN)</td><td>아니오</td><td>결정론적</td><td>Apple</td><td>아니오</td><td>예</td><td>아니오</td><td>아니오</td></tr><tr><td> <a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a> (1)</td><td>아니오</td><td>결정론적</td><td>Apple</td><td>아니오</td><td>예</td><td>아니오</td><td>아니오</td></tr><tr><td> <a href="./appsflyer-attribution-model#deep-link">딥 링크</a> (1)</td><td>아니오</td><td>결정론적</td><td>앱스플라이어</td><td>예</td><td>예</td><td>예</td><td>아니오</td></tr><tr><td colspan="7"><p>(1) 앱스플라이어 대시보드 및 보고서에서 "클래식" 어트리뷰션 메서드로도 알려져 있음</p><p>(2) 일부 써드 파티 스토어에서 지원함</p><p>(3) <a href="./ctv-pc-and-console-platform-attribution-concepts#지원되는-플랫폼" target="_blank">CTV, PC 및 콘솔<span> 플랫폼</span>의 전체 목록</a>을 참조하세요</p></td><td> </td></tr></tbody></table>

### 어트리뷰션 메서드 우선순위(어트리뷰션 워터폴)

새로운 인스톨 시, 유효한 인게이지먼트가 둘 이상 있는 경우, **앱스플라이어는 노출보다 클릭을, 확률적 방법보다 결정론적 방법을 우선시합니다**. 어트리뷰션 방법은 차트에 표시된 우선순위에 따라 활용됩니다.

![어트리뷰션 메서드 우선순위 23.png](https://files.readme.io/127da735ccb28c14eb7779f6c03f75be343d8543404da47bed41e5f07b158830-51912651128849.png)

아래에서 앱스플라이어 어트리뷰션 모델에 대한 자세한 설명을 확인하세요.

<div id="install-referrer-android-only" />

<Accordion title="인스톨 리퍼러(안드로이드 전용)">

* 구글 플레이 및 일부 다른 앱 스토어에서 다운로드한 안드로이드 앱은 일반적으로 인스톨 리퍼러 메서드로 어트리뷰션됩니다. 리퍼러는 안드로이드 스토어로 리디렉션되기 전에 클릭된 원래 URL을 제공합니다. 이것은 안드로이드 어트리뷰션의 기본 메서드입니다. 현재, Google Play, Huawei 앱 스토어, 삼성 갤럭시 스토어, Xiaomi GetApps Store에서 인스톨 리퍼러 어트리뷰션을 지원합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">리퍼러를 사용한 대체 앱 스토어 어트리뷰션</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Meta 인스톨 리퍼러:</Anchor> 앱스플라이어는 기기의 로컬 저장소에서 광고 캠페인 메타데이터를 수신하여 안드로이드 앱에 대한 Meta 광고 어트리뷰션을 지원합니다. 이 데이터는 어트리뷰션 측정에 사용됩니다 (Meta 디바이스 어트리뷰션).

</Accordion>

<div id="device-id-matching" />

<Accordion title="디바이스 ID 매칭">

유저 디바이스에 액세스할 수 있는 애드 네트워크는 클릭 URL을 통해 디바이스 ID를 앱스플라이어에 발송하거나, 노출이 발생했을 때 앱스플라이어에 알리는 고전적인 어트리뷰션 메서드입니다. 이를 통해 앱스플라이어는 클릭된 디바이스 ID와 앱스플라이어 SDK가 가져온 디바이스 ID를 일치시킬 수 있습니다.

디바이스 ID 매칭은 iOS의 주요 어트리뷰션 메서드입니다.

사용 가능한 ID는 다음과 같습니다:

* **iOS 디바이스**: IDFA, IDFV
* **안드로이드 디바이스: 구글 플레이 서비스를 사용하는 경우:** GAID
* **구글 플레이 서비스가 없는 안드로이드 디바이스:** OAID, 안드로이드 ID, IMEI, Fire ID

디바이스 ID는 어트리뷰션 링크에서 SHA1 또는 MD5를 사용하여 해시할 수 있습니다.

</Accordion>

<div id="device-id-matching-using-idfv-ios" />

<Accordion title="IDFV를 사용한 디바이스 ID 매칭(iOS)">

* 공급업체 식별자(IDFV)를 활용한 고전적인 어트리뷰션 메서드는 iOS 6.0 이상에서 사용할 수 있습니다. Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>와 LAT 메커니즘의 적용을 받지 않습니다. 항상 이용 가능하며 동일한 공급업체의 앱에 대한 상호 프로모션 광고에 사용할 수 있습니다.
* 앱스플라이어 SDK는 기본적으로 IDFV를 수집합니다.
* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">Apple에 따르면,</Anchor> *이 속성의 값은 동일한 디바이스에서 운영되는 동일한 공급업체의 앱에 대해 동일합니다.*
* IDFV는 유저가 특정 공급업체의 첫 번째 앱을 인스톨할 때 Apple에서 발생한 것입니다. 즉, Apple은 해당 디바이스에 동일한 공급업체의 다른 앱이 없는지 확인합니다. 결과적으로 특정 공급업체의 모든 앱을 삭제하고 동일한 공급업체의 앱을 다시 설치하면 새로운 IDFV가 생성됩니다.
* 가능하다면 IDFV를 발송해야 합니다. 이는 어트리뷰션을 향상시킵니다. 우리는 다음과 같은 다양한 시나리오에서 IDFV를 활용합니다:
  * 상호 프로모션 어트리뷰션.
  * 동일한 디바이스에서 어트리뷰션 재인스톨.
  * 로데이터 리포팅.
  * 오디언스.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="자체 리포팅 네트워크를 위한 디바이스 ID 매칭">

앱스플라이어는 앱을 처음 실행할 때 앱 설정을 확인하여 Meta 광고, 스냅챗, Google Ads와 같은 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">자체 보고 네트워크</Anchor> (SRN)에서 트래픽이 예상되는지 점검하는 전통적인 어트리뷰션 메서드를 사용합니다.

앱스플라이어는 신규 인스톨의 고유 디바이스 ID를 사용하여 관련된 SRN에 쿼리를 보냅니다. 이 쿼리는 SRN이 정한 모바일 측정 파트너(MMP) API를 사용합니다. 응답에 따라, 앱스플라이어는 새로운 사용자들을 SRN에 어트리뷰션할 수 있습니다.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="확률적 모델링">

확률적 모델링은 머신러닝을 활용하여 캠페인 성과를 추정하는 통계적 기법입니다. 확률적 모델링 파라미터는 수집됩니다:

* 처음에는 클릭 또는 광고 조회 시(활성화된 경우)
* 다시 앱이 실행될 때

**구현 특성**

* 통계를 사용하며 고유 ID를 기반으로 하지 않습니다.
* 리퍼러나 광고 ID가 없는 경우에 사용되는 대체 메서드입니다. 결정론적 어트리뷰션 방법, 즉 리퍼러 또는 ID 매칭을 통한 클릭은 룩백 윈도우 내에서 발생하는 경우 우선 적용됩니다.
* 모바일 앱의 경우, 앱스플라이어가 사용자 네트워크에 따라 동적으로 어트리뷰션 윈도우를 결정합니다. 윈도우 지속 기간은 어트리뷰션에 따라 조정되지만, 다른 메서드보다 짧습니다.(최대 24시간)
* CTV, PC 및 콘솔 앱의 경우, 어트리뷰션 윈도우는은 링크 파라미터에 의해 결정되며, 7일을 초과할 수 없습니다.
* 클릭-쓰루 확률적 모델링은 항상 활성화되어 있습니다.
* 뷰-쓰루 확률적 모델링은 앱 설정 페이지와 비-SRN 연동 탭에서 활성화되어야 합니다. CTV, PC 및 콘솔 앱의 경우, 기본으로 활성화되어 있습니다.

#### 애드 네트워크에 대한 확률적 모델링 파라미터

확률적 모델링 어트리뷰션을 구현하는 애드 네트워크는 어트리뷰션 링크 또는 HTTP 요청 헤더를 통해 다음의 파라미터를 발송해야 합니다.

* <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_os_version">af\_os\_version</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_model">af\_model</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ip">af\_ip</Anchor>

</Accordion>

<div id="aggregated-advanced-privacy-aap" />

<Accordion title="데이터 집약형 고급 프라이버시 보호(AAP)">

데이터 집약형 고급 프라이버시 보호(AAP)는 데이터 집약형으로 캠페인 성과 결과를 노출하여 여러 회사가 소유한 앱 및 웹사이트 사이에서 사용자를 기록할 수 있는 옵션을 방지하고, 사용자나 디바이스를 고유하게 식별할 수 있는 가능성을 차단합니다.

AAP는 Apple의 SKAdNetwork 개인정보 보호 수준을 개인정보 보호 임계값에 대한 최소 기준으로 활용합니다. AAP는 iOS 14.5 이상에서 작동하는 Apple 디바이스의 기본 어트리뷰션 모델입니다. 단, Apple이 명시적으로 허용한 경우, 예를 들어 온드 매체 및 앱 추적 투명성(ATT) 동의 사용자는 예외입니다.

설명된 다른 어트리뷰션 메서드와 달리 AAP 머신러닝 알고리즘의 목표는 최종 유저 어트리뷰션 정확도가 아니라 캠페인의 데이터 집약형 성과 정확성을 극대화하는 것입니다.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="프리로드 캠페인">

전형적인 프리로드 캠페인의 어트리뷰션 메서드로, 앱이 공장이나 디바이스 활성화 시 사전 로드 파트너에 의해 유저 디바이스에 설치됩니다. 프리로드 파트너는 다음과 같습니다:

* OEM(주문자 상표 부착 생산자)
* 앱 발견 플랫폼
* 이동 통신사

프리로드 캠페인을 어트리뷰션하는 방법은 3가지가 있습니다. 세 가지 방법 모두 동시에 사용할 수 있으며, 서로의 메커니즘을 방해하지 않습니다.

다음 표에는 3가지 방법과 주요 사양이 요약되어 있습니다. 각 프리로드 메서드에 대해 자세히 알아보려면 링크를 클릭하세요.

<table><thead><tr><th>프리로드 어트리뷰션 메서드</th><th>적용 사례</th><th>디바이스 활성화-앱 실행 정보\*</th><th>룩백 윈도우\*\*</th><th>로데이터의 매칭 유형</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">앱스플라이어 리퍼러</a>\*</td><td><ul><li>공장에서 사전 로드됨</li><li>디바이스 활성화 시 사전 로드됨</li></ul></td><td>예</td><td><ul><li>최대 180일</li><li>기본값은 90일입니다</li></ul></td><td><ul><li>프리로드: preload_rfr</li><li>다운로드하려면 클릭하세요: af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">구글 플레이 자동 설치</a>\*\*</td><td>디바이스 활성화 시 미리 로드됨(구글 플레이 앱의 경우)</td><td>아니오</td><td><ul><li>최대 180일</li><li>기본값은 90일입니다</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">시스템 속성 또는 매니페스트를 통한 공장 사전 로드(안드로이드)</a>\*\*</td><td><ul><li>공장에서 사전 로드됨</li><li>디바이스 활성화 시 사전 로드됨</li></ul></td><td>아니오</td><td>제한 없음</td><td>preload_conf</td></tr><tr><td colspan="5"><p>\* 앱스플라이어 리퍼러 프리로드 솔루션은 첫 번째 디바이스 활성화와 첫 번째 앱 실행 사이에 가시성과 측정 기능을 제공합니다. 이를 통해 특정 파트너가 앱을 미리 로드하여 활성화된 디바이스가 몇 대인지 확인하고, 앱이 처음 실행된 시점을 확인할 수 있습니다.</p><p>다른 두 방법에서는 사용자가 앱을 처음 실행한 후에만 어트리뷰션이 결정되며, 앱 최초 오픈 전에 앱이 설치된 디바이스의 수는 알 수 없습니다.</p><p>\*\* 사용자가 디바이스를 처음 켜고 사전 로드된 앱을 처음 실행할 때까지 며칠 또는 몇 주가 걸릴 수 있습니다. 결과적으로, 앱스플라이어는 사전 로드 캠페인의 어트리뷰션을 판단할 때 더 긴 룩백 윈도우를 사용하여 최우선 순위를 부여합니다.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="딥 링크">

리인게이지먼트에서만 사용되는 전형적인 어트리뷰션 메서드로, 사용자가 앱을 다운로드하기 위해 앱 스토어로 리디렉션되지 않을 때 사용됩니다. 따라서 URL에 있는 정보는 클릭(및 그에 따른 앱 오픈)과 직접적으로 연결될 수 있습니다. 이 어트리뷰션 메서드는 딥 링크라고 불리며, 리인게이지먼트를 어트리뷰션하기 위해 필요한 정보를 전달하는 딥 링크 URL이기 때문입니다.

</Accordion>

### 미디어 소스 및 앱스플라이어 기능별 어트리뷰션 메서드

지원되는 특정 어트리뷰션 메서드에 대한 전체 설명은 다음 섹션을 참조하세요.

* 미디어 소스: 온드(owned) 또는 페이드(paid)
* 사용되는 앱스플라이어 기능
* 유저 디바이스: 안드로이드 또는 iOS

<div id="owned-media" />

<Accordion title="온드 미디어(owned media)">

<table><thead><tr><th rowspan="2">미디어 소스</th><th rowspan="2">기능</th><th colspan="2">어트리뷰션 메서드</th></tr><tr><th>안드로이드</th><th>iOS</th></tr></thead><tbody><tr><td>온드 미디어: 이메일(ESP 포함), SMS 문자메시지, 소셜미디어 게시물, 인플루언서/제휴사, 인쇄물 등</td><td><a href="./onelink-guide" target="_blank"><span>원링크</span></a></td><td><ul><li>인스톨 리퍼러</li><li>확률적 모델링</li></ul></td><td>확률적 모델링</td></tr><tr><td rowspan="2">페이드 또는 오가닉 유입 트래픽이 있는 온드 모바일 웹사이트/랜딩 페이지</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">스마트 배너</a></td><td><ul><li>인스톨 리퍼러</li><li>확률적 모델링</li></ul></td><td>확률적 모델링</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">원링크 스마트 스크립트</a></td><td><ul><li>인스톨 리퍼러</li><li>확률적 모델링</li></ul></td><td>확률적 모델링</td></tr><tr><td rowspan="2">온드 모바일 앱</td><td><a href="./user-invite-attribution" target="_blank">유저 초대\/추천</a></td><td><ul><li>인스톨 리퍼러</li><li>확률적 모델링</li></ul></td><td>확률적 모델링</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">크로스 프로모션</a></td><td><ul><li>인스톨 리퍼러</li><li>디바이스 ID 매칭</li></ul></td><td>디바이스 ID 매칭</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="페이드(paid) 미디어">

<table><thead><tr><th rowspan="2">미디어 소스</th><th colspan="3">어트리뷰션 메서드</th></tr><tr><th>안드로이드</th><th>iOS</th><th><strong>CTV, PC 및 콘솔 플랫폼</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRNs</a></td><td>디바이스 ID 매칭</td><td><ul><li>디바이스 ID 매칭</li><li>AAP(iOS 14.5+)</li><li>SKAdNetwork(iOS 14+)</li></ul></td><td>디바이스 ID 매칭</td></tr><tr><td><ul><li> <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">파트너용 어트리뷰션 링크</a>를 통한 애드 네트워크(비 SRN) </li><li><span>CTV, PC 및 콘솔 플랫폼</span></li></ul></td><td><ul><li>인스톨 리퍼러</li><li>디바이스 ID 매칭</li><li>확률적 모델링</li></ul></td><td><ul><li>디바이스 ID 매칭</li><li>확률적 모델링(iOS 14.5 이전)</li><li>AAP(iOS 14.5+)</li><li>SKAdNetwork(iOS 14+)</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">디바이스에 사전 설치됨</a></td><td>사전 인스톨</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

## 유저 인게이지먼트 어트리뷰션 유형

어트리뷰션은 클릭-쓰루 및 뷰-쓰루 인게이지먼트를 기반으로 수행됩니다. 미디어 소스 어트리뷰션은 디바이스 ID 매칭과 확률적 모델링 기법을 활용하여 이뤄집니다.

<div id="clickthrough-attribution" />

<Accordion title="클릭-쓰루 어트리뷰션">

대부분의 인스톨은 유저가 배너, 동영상, 전면 광고와 같은 광고를 클릭한 결과입니다.

광고를 클릭하면 기본 설정이 7일인 클릭 룩백 윈도우가 열립니다. 룩백 윈도우 기간 중 발생한 인스톨은 논오가닉이며 미디어 소스에 어트리뷰션됩니다. 룩백 윈도우 이후에 발생한 인스톨은 오가닉 인스톨로 간주됩니다. 흔히 오가닉으로 어트리뷰션되었다고 언급됩니다.

* 7일간의 클릭 룩백 윈도우는 업계 표준으로 간주됩니다. 미디어 소스와의 합의에 따라 이 기간을 설정하세요.
* SRN 룩백 윈도우는 SRN에서 정한 기간에 맞춥니다.

<table><thead><tr><th rowspan="2"><strong>어트리뷰션 유형</strong></th><th rowspan="2"><strong>어트리뷰션 메서드</strong></th><th rowspan="2">기간</th><th rowspan="2">기본</th></tr></thead><tbody><tr><td rowspan="2"><p>클릭-쓰루</p><p>(모든 연동된 파트너)</p></td><td>리퍼러, ID 매칭</td><td>1–30일</td><td>7일</td></tr><tr><td>확률적 모델링</td><td>0–24시간</td><td><ul><li>적응형</li><li>앱스플라이어에서 결정</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">룩백 윈도우에 대해 더 보기</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="뷰-쓰루 어트리뷰션">

광고를 보기만 하고 클릭하지 않은 사용자는 광고를 제공하는 애드 네트워크에 측정될 수 있습니다.

뷰-쓰루 어트리뷰션을 위한 룩백 윈도우:

* 클릭-쓰루 어트리뷰션보다 짧습니다.
* 설정 가능합니다.

이 기능은 전통적으로 비디오 광고의 CTR이 낮은 비디오 애드 네트워크에 특히 유용하며, 일반 광고를 제공하는 기존 애드 네트워크에도 유용합니다.

클릭과 노출이 모두 발생하는 경우, 이는 적극적인 참여로 **클릭이 항상 우선합니다**.

<table><thead><tr><th><strong>어트리뷰션 유형</strong></th><th><strong>어트리뷰션 메서드</strong></th><th><strong>기간</strong></th><th> <strong>기본</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>뷰-쓰루(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">선택된 연동 파트너</a>의 경우)</p></td><td>ID 매칭</td><td>0-24시간</td><td>1일</td></tr><tr><td>확률적 모델링</td><td>0-24시간</td><td><ul><li>적응형</li><li>앱스플라이어에서 결정</li></ul></td></tr></tbody></table>

**뷰-쓰루 어트리뷰션을 활성화하려면:**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#뷰-쓰루-어트리뷰션-룩백-윈도우">설정 창에서</Anchor> 룩백 윈도우를 설정합니다.

<Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements">뷰-쓰루 어트리뷰션에 대해 더 알아보기</Anchor>

</Accordion>

## 고급 어트리뷰션 주제

<div id="in-app-events" />

<Accordion title="인앱 이벤트">

앱스플라이어는 디바이스 ID 또는 고유한 앱스플라이어 ID를 사용하여 앱 설치, 재설치 또는 리어트리뷰션 시 **인앱 이벤트를 미디어 소스에 측정합니다**. 광고주는 이 정보를 사용하여 앱의 로데이터에서 사용자의 여정을 추적할 수 있습니다. 요약된 일별 데이터에서는 디바이스 ID 또는 앱스플라이어 ID를 사용하여 고유 사용자 수를 계산합니다. 예를 들어, 인앱 이벤트를 수행하는 고유 사용자 수를 계산하는 경우입니다.

이벤트 어트리뷰션에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="assisted-installs" />

<Accordion title="어시스트된 인스톨">

앱스플라이어는 인스톨당 하나의 미디어 소스에만 완전히 어트리뷰션하며, 일반적으로 마지막 광고 클릭이나 마지막 광고 노출(클릭이 없는 경우)을 사용합니다.

인스톨 어시스트(멀티 터치 어트리뷰션)는 미디어 소스\/캠페인이 마지막 터치포인트가 아니었지만, 인스톨 전에 유저와 접촉했으며, 어트리뷰션 룩백 윈도우 내에서 발생한 인스톨입니다.

어시스트 네트워크는 앱스플라이어에서 인스톨에 기여한 것으로 표시됩니다.

더 많은 정보를 원하신다면 <Anchor target="_blank" href="/marketers/ko/docs/measure-assisted-installs">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="reinstalls" />

<Accordion title="재설치">

재설치는 유저가 앱을 인스톨하고 삭제한 후, 다시 인스톨하는 경우에 발생합니다. 재설치 어트리뷰션은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>에 의해 다음과 같이 조정됩니다.

* 리어트리뷰션 윈도우가 만료된 후에 재설치가 발생하면, 새로운 인스톨로 기록됩니다.
* 리어트리뷰션 윈도우 내에 재설치가 발생하면, 다음 중 하나가 적용됩니다.
  * 유저가 재설치 전에 리타겟팅 캠페인에 참여한 경우: <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅 재설치</Anchor> (일명 리어트리뷰션)가 기록됩니다.
  * 유저가 캠페인에 참여하지 않았거나, UA 캠페인에 참여한 경우: 인스톨이 기록되지 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls#개요">**재설치 이후 인앱 이벤트 어트리뷰션**</Anchor> 상태에 따라, 이러한 재설치 유저의 인앱 이벤트는 오가닉 또는 원래 인스톨에 귀속됩니다.

디바이스 테스트 및 멀티 인스톨을 위해 앱스플라이어에 디바이스를 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록</Anchor>하세요. 디바이스를 등록하지 않으면, 첫 번째 인스톨만 기록됩니다.

앱스플라이어는 광고주 ID 없이도 iOS 재설치를 더 정확하게 어트리뷰션할 수 있도록 지원합니다. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">앱 설정 페이지</Anchor>에서 이 기능을 활성화할 수 있습니다.

#### iCloud에 백업된 iOS 앱 재설치

iCloud를 통해 애플리케이션을 백업하고 나중에 복원하는 경우(같은 디바이스나 다른 디바이스에서), 앱스플라이어는 이를 새 인스톨이나 재설치로 간주하지 않습니다. iCloud에서 앱을 복원한 유저는 앱스플라이어 ID와 어트리뷰션 데이터를 유지합니다.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="리타겟팅 어트리뷰션">

![리타겟팅_-_흐름__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

<Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor> (기본적으로 90일) 내에 앱을 재설치한 유저는 리어트리뷰션으로 간주됩니다. 이 인스톨이 리타겟팅 캠페인에 참여한 이후 발생한 경우, 리타겟팅 재설치(즉, 리어트리뷰션)로 기록되며 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅</Anchor>으로 보고됩니다.

</Accordion>

<div id="app-updates" />

<Accordion title="앱 업데이트">

* 기존 사용자가 앱을 후속 버전으로 업데이트할 때, 이전에 앱스플라이어에 의해 어트리뷰션된 적이 있는 경우 이 이벤트는 어트리뷰션 이벤트로 간주되지 않습니다. 주의! 다른 MMP에서 앱스플라이어로 마이그레이션한 후, 기존 사용자가 처음으로 앱을 오픈하는 경우는 오가닉으로 간주됩니다.
* 앱 버전별 사용자 수와 관련된 지표는 <Anchor target="_blank" href="/marketers/ko/docs/sdk-information-version-consent-dashboard">SDK 정보 대시보드</Anchor>에서 확인하실 수 있습니다.

</Accordion>

<div data-zendesk-anchors="what-is-attribution=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 01H8GG9XPSS8KA9CHPD6ECNR2J=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 01H8GG9XPSA15N5CSHGZNBWSAV=%ED%8C%81 what-is-an-app-install=%EC%95%B1-%EC%9D%B8%EC%8A%A4%ED%86%A8%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 01EDRHGMTXK94Y97DPKFAMCJ5B=%EC%95%B1-%EC%9D%B8%EC%8A%A4%ED%86%A8%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 attribution-methods=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C 01EDRHGMTXCRNVXS9JGHQ1JAQT=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C attribution-waterfall=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9B%8C%ED%84%B0%ED%8F%B4 h_01JBC8582ABTE00W29PM5Y5X0B=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9B%8C%ED%84%B0%ED%8F%B4 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSQZPWJZ0BC0EAMB97=device-id-matching-using-idfv-ios 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling probabilistic-modeling-parameters-for-ad-networks=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%99%95%EB%A5%A0%EC%A0%81-%EB%AA%A8%EB%8D%B8%EB%A7%81-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HEMSHXKGNW2DF41094BXY0FY=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%99%95%EB%A5%A0%EC%A0%81-%EB%AA%A8%EB%8D%B8%EB%A7%81-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns attribution-methods-per-media-source-and-appsflyer-feature=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EB%B0%8F-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B8%B0%EB%8A%A5%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C 01H8GG9XPTXDR41QANF4XVSZMM=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EB%B0%8F-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B8%B0%EB%8A%A5%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A9%94%EC%84%9C%EB%93%9C 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=%EC%9C%A0%EC%A0%80-%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95 01EDRHGMTX7851H14R20F9KNAN=%EC%9C%A0%EC%A0%80-%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution advanced-attribution-topics=%EA%B3%A0%EA%B8%89-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A3%BC%EC%A0%9C 01EDRHGMTYYXBSCDPKXCDK1641=%EA%B3%A0%EA%B8%89-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A3%BC%EC%A0%9C 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=icloud%EC%97%90-%EB%B0%B1%EC%97%85%EB%90%9C-ios-%EC%95%B1-%EC%9E%AC%EC%84%A4%EC%B9%98 01EDRHGMTYDSNJKQNPNYFXJPAZ=icloud%EC%97%90-%EB%B0%B1%EC%97%85%EB%90%9C-ios-%EC%95%B1-%EC%9E%AC%EC%84%A4%EC%B9%98 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
