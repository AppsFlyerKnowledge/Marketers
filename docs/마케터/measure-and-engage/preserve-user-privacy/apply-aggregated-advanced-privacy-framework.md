---
title: 집약형 프라이버시 강화(Aggregated Advanced Privacy, AAP) 프레임워크
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-10-14T10:33:56Z'
  id: 360018515798
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/360018515798
---
> **한눈에 보기:** 요약: 광고주는 iOS 14.5 이상의 일반 출시와 Apple의 ATT 시행으로 시작하여 집약형 프라이버시 강화 dva프레임워크(Aggregated Advanced Privacy, AAP) 프레임워크를 사용하여 플랫폼에서 사용자 수준 어트리뷰션 데이터의 가용성을 제어합니다.

## 집약형 프라이버시 강화(Aggregated Advanced Privacy, AAP) 프레임워크

앱스플라이어 AAP(집약형 프라이버시 강화) 프레임워크는 다른 회사가 소유한 앱과 웹사이트 전반에 걸친 추적을 방지하고 사용자 또는 장치를 고유하게 식별하는 기능을 제공합니다. AAP는 개인 정보 보호 임계값에 대한 최소 벤치마크로 Apple 앱 추적 투명성 개인 정보 수준을 활용합니다.

프레임워크는 광고주에게 앱스플라이어 플랫폼을 통해 사용자 수준 어트리뷰션 데이터의 가용성을 제어할 수 있는 기능을 제공합니다.

iOS 14.5 일반 가용성 및 Apple의 ATT 시행 이후 AAP가 켜져 있으면 광고주 또는 파트너는 iOS 14.5이상을 실행하는 비동의 사용자에 대한 사용자 수준 어트리뷰션 데이터를 사용할 수 없습니다.

AAP는 광고주 및 파트너에 대한 집계된 어트리뷰션 데이터 및 분석 리포트의 가용성에 영향을 미치지 않습니다.

### AAP 영향을 받는 기능

AAP가 켜져 있으면 로데이터에서 제공하는 데이터가 영향을 받으며 일부 필드가 제한되거나 사용할 수 없습니다. 이는 다음 도구에서 제공하는 데이터에 영향을 줍니다:

* 데이터 락커
* 로데이터 Pull API
* 푸시 API
* 대시보드 내보내기 페이지
* 네트워크에 포스트백
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">고객 측 사용자 수준 데이터 API의 상황에 맞춰</Anchor> 전환 데이터 가져오기(GCD) API

AAP가 다음과 같이 설정되어 있으면 데이터 가용성이 영향을 받습니다.

* **귀속 데이터 및 사기(Protect360):** <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">일부 속성 필드는 제한되거나 사용할 수 없습니다.</Anchor>
* **클릭, 노출 및 차단된 클릭(사기) 데이터:** <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#identifier-restriction">사용자 및 장치 관련 식별자</Anchor>는 사용할 수 없습니다.
* **디퍼드 딥링킹(Deferred Deep Linking)**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">디퍼드 딥링킹</Anchor>: 유료 미디어에서 디퍼드 딥링킹을 구현하는 경우 통합 딥링킹 API(UDL)를 사용합니다. GCD를 사용하는 레거시 API는 비동의 사용자의 맥락에서 사용할 수 없습니다. 소유 미디어의 경우, 소유 미디어에 대한 지연 심층 링크는 GCD 및 최신 지연 심층 링크 API를 통해 지원됩니다.

## 집약형 프라이버시 강화 프레임워크의 데이터 가용성 원칙

AAP가 특정 사용자의 데이터에 적용될 때 데이터 가용성은 해당 사용자의 ATT 상태와 사용자를 인입하는 미디어소스에 따라 달라집니다.

**정의:**

* 사용자 수준 어트리뷰션 데이터 사용자 수준의 귀속에 연결된 장치 수준 식별자를 포함하는 데이터 기록
* 광고주에 대해 제한된 어트리뷰션 데이터
  * 사용 가능 장치 수준 식별자. (IDFA는 이용자의 동의가 있어야 이용할 수 있습니다.)
  * 사용 불가 퍼블리셔 속성 링크를 통해 수신된 속성 매개변수(예: `pid` 및 `c`). <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">광고주에게 제한되고 사용할 수 없는 필드 목록</Anchor> 즉, 제한된 미디어 소스입니다.
* **파트너에 대해 제한된 어트리뷰션 데이터:**
  * 사용 가능 집계된 캠페인 세부정보입니다.
  * 사용 불가 사용할 수 없음: 앱스플라이어 ID, 커스텀 데이터, 고객 사용자 ID(CUID), 클릭 ID, IDFA, IDFV, IMEI, 사용자 에이전트 및 IP 주소와 같이 사용자를 식별하는 데 도움이 되는 사용자 수준 데이터.

광고주와 파트너가 사용할 수 있는 데이터를 설명하기 위해 정의된 용어가 다음 그림과 섹션에서 사용됩니다.

Advanced Privacy Framework - Advertisers (4).png

사전 개인 정보 보호는 웹에서 게재될 때 다르게 작동하며 af\_media\_type=web 또는 af\_media\_type=app 매개변수를 사용해야 합니다. <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#웹-캠페인">자세한 내용은 여기를 참조하세요</Anchor> .

### 유료 및 온드 미디어 데이터 가용성

<div id="paid-media" />

<Accordion title="페이드(paid) 미디어">

유료 미디어에는 광고주가 캠페인을 실행하는 앱스플라이어 플랫폼에 연동된 모바일 광고 네트워크가 포함됩니다.

#### ATT 상태에 의한 유료 미디어 데이터 가용성

<table><thead><tr><th rowspan="2">매체 유형</th><th colspan="2">ATT 상태</th><th colspan="2">다음에 사용 가능한 데이터:</th></tr><tr><th>퍼블리셔 앱</th><th>광고주 앱</th><th>광고주</th><th>애드 네트워크</th></tr></thead><tbody><tr><td rowspan="4">앱</td><td>승인됨</td><td>승인됨</td><td>사용자 수준 어트리뷰션 데이터</td><td>사용자 수준 어트리뷰션 데이터</td></tr><tr><td>승인되지 않음</td><td>승인됨</td><td>광고주에 대해 제한된 어트리뷰션 데이터  </td><td>파트너에 대해 제한된 어트리뷰션 데이터</td></tr><tr><td>승인됨</td><td>승인되지 않음</td><td>광고주에 대해 제한된 어트리뷰션 데이터  </td><td>파트너에 대해 제한된 어트리뷰션 데이터</td></tr><tr><td>승인되지 않음</td><td>승인되지 않음</td><td>광고주에 대해 제한된 어트리뷰션 데이터  </td><td>파트너에 대해 제한된 어트리뷰션 데이터</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>웹</p></td><td>해당 없음</td><td>승인됨</td><td>사용자 수준 어트리뷰션 데이터</td><td>사용자 수준 어트리뷰션 데이터</td></tr><tr><td>해당 없음</td><td>승인되지 않음</td><td>광고주에 대해 제한된 어트리뷰션 데이터  </td><td>파트너에 대해 제한된 어트리뷰션 데이터</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="온드 미디어">

Apple의 AppTrackingTransparency 프레임워크는 다른 회사에서 수집한 데이터에만 적용됩니다. 따라서 사용자의 ATT 동의 여부와 관계없이 광고주가 소유한 미디어 사용자 수준 어트리뷰션 데이터를 사용할 수 있습니다.

온드 미디어에는 광고주가 고객에게 다가가기 위해 사용하는 디지털 마케팅 캠페인이 포함됩니다. 여기에는 이메일 캠페인, 크로스 프로모션, 푸시 알림 등이 포함됩니다. 앱스플라이어에서 광고 네트워크를 사용하는 캠페인은 온드 미디어로 간주되지 않습니다.

</Accordion>

## Advanced Aggregated Privacy 제어

<div id="aap-central-switch" />

<Accordion title="집계된 개인 정보 보호 강화(AAP) - 앱 수준 전환">

AAP는 선택한 앱의 모든 파트너에 대한 프라이버시 강화 프레임워크 설정을 제어하는 앱 수준 전환입니다. AAP 전환은 **앱 설정** 페이지에 있습니다. AAP 전환이 켜져 있으면 선택한 앱의 모든 파트너에 대한 **프라이버시 강화 프레임워크** 전환이 자동으로 켜지며 수정할 수 없습니다. 이를 해제하면 광고주가 각 파트너 연동으로 개별적으로 이동하여 **프라이버시 강화 프레임워크**를 설정할 수 있습니다.

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

#### AAP가 활성화됨

* 집계된 어트리뷰션을 사용할 수 있습니다. 여기에는 예를 들어 개요 대시보드 및 코호트 및 Master API와 같은 리포트 도구가 포함됩니다.
* [고급 개인정보 보호 파트너 전환](#partner-advanced-privacy-switch)이 켜져 있으며 수정할 수 없습니다. 참고! 그들은 고정된 상태입니다.
* 광고주 및 파트너에 대한 사용자 수준 데이터의 가용성은 [이전 섹션](/docs/apply-aggregated-advanced-privacy-framework#집약형-프라이버시-강화-프레임워크의-데이터-가용성-원칙)에 정의된 대로 제한됩니다.

#### AAP가 비활성화됨

* 광고주는 사용자 수준 어트리뷰션 데이터를 사용할 수 있습니다.
* 파트너별 프라이버시 강화 설정은 개별적으로 설정할 수 있습니다.

AAP를 끄기 전에 사용자 수준의 어트리뷰션 데이터를 제3자에게 제공할 수 있는지 여부와 제3자가 데이터를 사용하는 방법을 고려하십시오. Apple이 추적을 정의하는 방법과 관련하여 법률 및 기타 전문 고문과 긴밀히 협력해야 합니다.  여기에 명시된 내용은 법적 조언이 아닙니다. 정보와 편의를 위해 제공됩니다.

**집약형 프라이버시 강화 설정을 지정하는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.
2. **필요에 따라** 집약형 프라이버시 강화 프레임워크를 켜거나 끕니다.
3. **저장**을 클릭하세요.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="AP(Advanced Privacy) - 파트너 수준 전환">

AAP가 비활성화된 경우 광고주는 각 광고 네트워크에 대해 프라이버시 강화 설정을 개별적으로 설정할 수 있습니다.

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**파트너의 프라이버시 강화를 끄려면:**

1. **앱 설정** 페이지에서 AAP의 중앙 스위치가 꺼져 있는지 확인합니다.
2. 사이드 메뉴에서 협업 > 활성 연동을 선택합니다.
3. 애드 네트워크를 선택하세요.
4. **연동** 탭에서 프라이버시 강화를 끕니다.

**AAP 설정 변경 및 파트너의 프라이버시 강화 설정에 미치는 영향**

앞에서 설명한 것처럼 AAP 설정은 파트너 수준의 프라이버시 강화(AP) 설정보다 우선합니다. 그러나 나중에 AAP(중앙 스위치)를 끄면 개별 파트너 수준 프라이버시 강화 설정이 이전 상태로 되돌아갑니다. 의미는 다음과 같습니다.

* 이전에 사용자는 AAP를 끄고 일부 파트너 AP 설정을 끄기로 설정했습니다.
* 나중에 사용자는 AAP를 켰습니다. AAP가 켜져 있으면 파트너 설정을 무시하고 모든 파트너가 켜져 있는 것으로 간주됩니다.
* 이제 사용자는 AAP를 다시 끕니다. 개별 파트너 설정이 적용됨을 의미합니다. 따라서 일부 파트너의 경우 설정이 이미 꺼져 있습니다.

</Accordion>

## Advanced Aggregated Privacy implications for your partners(파트너에 대한 고급 집계 개인 정보 보호 영향)

<div id="ad-networks" />

<Accordion title="애드 네트워크">

#### **광고 네트워크 파트너에 대한 포스트백**

AAP는 공유된 데이터와 관련하여 광고 네트워크에 영향을 미치며 광고 네트워크의 맥락에서 광고주에게 적용되는 AAP 원칙과 일치합니다. 광고 네트워크와 공유되는 데이터는 어트리뷰트된 광고 네트워크와 어트리뷰트되지 않은 광고 네트워크 간에 다른 포스트백을 통해 이루어집니다.

설명된 데이터 공유 규칙은 다음 스위치 중 하나가 켜져 있는 경우 지정된 광고 네트워크에 적용됩니다.

* AAP: AAP: 앱 수준 전환
* AP: AP: 파트너 수준 전환

#### **어트리뷰트된 광고 네트워크에 대한 포스트백**

어트리뷰션 네트워크의 경우 데이터 공유에 사용되는 포스트백 유형은 다음과 같이 사용자 동의 상태에 따라 다릅니다.

* 동의 사용자 동의 사용자: 식별자를 포함한 사용자 수준 어트리뷰션 데이터를 포함하는 정기적인 포스트백.
* iOS 미동의 유저 제한된 귀속 데이터를 포함하는 고급 개인 정보 보호(AP) 포스트백. 여기에는 캠페인 세부정보가 포함되며 식별자는 없습니다.
  * **전제 조건:** 전제 조건: 광고 네트워크가 AP 포스트백을 받으려면 앱스플라이어와 AP 연동이 있어야 합니다. 연동하지 않으면 비동의 사용자에 대해 포스트백이 전송되지 않습니다.
  * **예외: 예외: Apple Search Ads(ASA)에 어트리뷰션된 인스톨의 경우, Advanced Privacy를 지원하지 않는 광고 네트워크에서 설치 포스트백을** 오가닉을 포함한 모든 미디어 소스/strong>로 설정해도 Apple Search Ads(ASA)는 광고주 측의 Advanced Privacy 상태와 관계없이 광고 네트워크에 인스톨 포스트백을 전송합니다.

사용된 다양한 사용자 동의 시나리오 및 포스트백 유형은 다음 그림에 나와 있습니다.

AAP - Attributed ad networks.png

사전 개인 정보 보호는 웹에서 게재될 때 다르게 작동하며 af\_media\_type=web 또는 af\_media\_type=app 매개변수를 사용해야 합니다. <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#웹-캠페인">자세한 내용은 여기를 참조하세요</Anchor> .

#### **어트리뷰트되지 않은 파트너를 위한 포스트백**

연동 파트너의 연동 탭에서 전송 옵션이 *오가닉을 포함한 모든 미디어 소스* 로 설정되고 해당 파트너가 다음 그림과 같이 이벤트에 기여하지 않은 경우 어트리뷰트되지 않은 포스트백이 네트워크로 전송됩니다.

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

사용된 다양한 사용자 동의 시나리오 및 포스트백 유형은 다음 흐름도에 나와 있습니다.

AAP - Unattributed ad networks.png

사전 개인 정보 보호는 웹에서 게재될 때 다르게 작동하며 af\_media\_type=web 또는 af\_media\_type=app 매개변수를 사용해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#웹-캠페인">여기</Anchor>를 참조하세요.

</Accordion>

<div id="analytics-partners" />

<Accordion title="분석 파트너">

AAP는 분석 파트너와 공유되는 데이터와 관련하여 분석 파트너에게 영향을 미치며 분석 파트너의 맥락에서 광고주에게 적용되는 AAP 원칙과 일치합니다.   파트너와 공유되는 데이터는 포스트백을 통해 이루어집니다.

설명된 데이터 공유 규칙은 다음 스위치 중 하나가 켜져 있는 경우 지정된 파트너에 적용됩니다.

* AAP: AAP: 앱 수준 전환
* AP: AP: 파트너 수준 전환

사용자 식별자를 포함한 사용자 수준 어트리뷰션 데이터가 포함된 포스트백은 동의 사용자에게 전송됩니다. 비동의 사용자의 경우 포스트백이 전송되지 않습니다.

사용된 다양한 사용자 동의 시나리오 및 포스트백 유형은 다음 그림에 나와 있습니다.

AAP - Analytics partner.png

사전 개인 정보 보호는 웹에서 게재될 때 다르게 작동하며 af\_media\_type=web 또는 af\_media\_type=app 매개변수를 사용해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#웹-캠페인">여기</Anchor>를 참조하세요.

</Accordion>

<div id="agencies" />

<Accordion title="에이전시">

**데이터 가용성** AAP가 기관에 미치는 영향은 광고주와 유사합니다. 특정 앱에 대해 에이전시가 로데이터를 사용할 수 있고 특정 사용자의 데이터에 AAP가 적용되는 경우, 데이터는 광고주에 대한 제한된 어트리뷰션 데이터의 규칙에 따라 사용할 수 있습니다.

**광고 네트워크의 프라이버시 강화 설정을 변경하는 에이전시:**

* AAP가 꺼져 있으면 각 연동 파트너의 프라이버시 강화를 설정할 수 있습니다.
* 기본적으로 광고주만 프라이버시 강화 설정을 변경할 수 있습니다. 그러나 광고주는 에이전시에서 활성화한 광고 네트워크의 프라이버시 강화 설정을 지정할 수 있는 권한을 에이전트에 명시적으로 부여할 수 있습니다.

**에이전시에 프라이버시 강화를 설정할 수 있는 권한 부여**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

**에이전시가 프라이버시 강화를 설정하도록 허용하려면**:

1. 사이드 메뉴에서 협업 > 활성 연동을 선택합니다.
2. 에이전시를 선택합니다.
3. **권한** **탭에서 프라이버시 강화 설정 변경을 켭니다.**
4. **저장**을 클릭하세요.

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">광고 네트워크에 대한 Advanced Privacy 안내서 및 포스트백 매크로</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=%EC%A7%91%EC%95%BD%ED%98%95-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94aggregated-advanced-privacy-aap-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC h_01HDPDE0H3SYFWBHK59HBV2P6N=%EC%A7%91%EC%95%BD%ED%98%95-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94aggregated-advanced-privacy-aap-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC aapimpacted-features=aap-%EC%98%81%ED%96%A5%EC%9D%84-%EB%B0%9B%EB%8A%94-%EA%B8%B0%EB%8A%A5 h_01HDPDE0H339BPACN235V70MWW=aap-%EC%98%81%ED%96%A5%EC%9D%84-%EB%B0%9B%EB%8A%94-%EA%B8%B0%EB%8A%A5 data-availability-principles-in-aggregated-advanced-privacy=%EC%A7%91%EC%95%BD%ED%98%95-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC%EC%9D%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1-%EC%9B%90%EC%B9%99 h_01HDPDE0H3QBE60DVBZ1MWNB9N=%EC%A7%91%EC%95%BD%ED%98%95-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC%EC%9D%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1-%EC%9B%90%EC%B9%99 paid-and-owned-media-data-availability=%EC%9C%A0%EB%A3%8C-%EB%B0%8F-%EC%98%A8%EB%93%9C-%EB%AF%B8%EB%94%94%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HDPDE0H326EXNCQHPVJWXK3H=%EC%9C%A0%EB%A3%8C-%EB%B0%8F-%EC%98%A8%EB%93%9C-%EB%AF%B8%EB%94%94%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=att-%EC%83%81%ED%83%9C%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9C%A0%EB%A3%8C-%EB%AF%B8%EB%94%94%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HDPDE0H3SACYAV19WQD9TCQ3=att-%EC%83%81%ED%83%9C%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9C%A0%EB%A3%8C-%EB%AF%B8%EB%94%94%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=advanced-aggregated-privacy-%EC%A0%9C%EC%96%B4 h_01HDPDE0H4VQC2DWAV68Q9VDVQ=advanced-aggregated-privacy-%EC%A0%9C%EC%96%B4 h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap%EA%B0%80-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%A8 h_01HDPDE0H4SC810EBK7ZGQ02K0=aap%EA%B0%80-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%A8 aap-disabled=aap%EA%B0%80-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%EB%90%A8 h_01HKHPGQ1R6HZEXSRTX7ATVWE9=aap%EA%B0%80-%EB%B9%84%ED%99%9C%EC%84%B1%ED%99%94%EB%90%A8 h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=advanced-aggregated-privacy-implications-for-your-partners%ED%8C%8C%ED%8A%B8%EB%84%88%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EA%B8%89-%EC%A7%91%EA%B3%84-%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EC%98%81%ED%96%A5 h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HDPDE0H47ENYTWRVFPX0VTZC=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 postbacks-for-attributed-ad-networks=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%9C-%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HDPDE0H4B01YG577QZCG7TA7=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%9C-%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 postbacks-for-unattributed-partners=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%ED%8C%8C%ED%8A%B8%EB%84%88%EB%A5%BC-%EC%9C%84%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HDPDE0H63ZMV255SN7EKDRMV=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%ED%8C%8C%ED%8A%B8%EB%84%88%EB%A5%BC-%EC%9C%84%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
