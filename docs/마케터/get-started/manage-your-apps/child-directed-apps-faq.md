---
title: 어린이용 앱—FAQ
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-10-14T10:32:22Z'
  id: 18324823209745
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/18324823209745
---
**한눈에 보기:** 요약: 어린이용 앱에 대해 자주 묻는 질문(FAQ)에 대한 답변을 확인하세요.

## 개요

어린이의 개인 정보를 보호하기 위해 어린이용 앱에 대한 많은 정책, 법률 및 규정이 있습니다. 주요한 것들로는 [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa)와 [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1)이 있습니다. 최근 몇 년 동안 iOS 및 Android와 같은 플랫폼은 어린이의 개인 정보 보호를 개선하기 위한 정책을 구현했습니다. 앱을 만들 때 가장 먼저 해야 할 일 중 하나는 어린이만을 대상으로 하는지 아니면 다양한 대상(어린이와 성인 모두)을 대상으로 하는지 확인하는 것입니다. 이 가이드에서 아동을 대상으로 하는 앱을 위한 호환 어트리뷰션 솔루션을 구현하는 방법을 알아보세요.

## 어린이용 앱 추가하기

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="어린이용 앱을 추가할 때 어떤 단계를 거쳐야 하나요?">

1. <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱 추가 마법사를 따릅니다</Anchor>.
2. 마법사의 2단계는 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#앱-오디언스-정의">어린이용 앱에 대한 지침을 참조하세요</Anchor>.
3. 앱이 추가된 후:
   * SDK에서 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#애플리케이션-내-개발-키-구현">Dev 키</Anchor>를 구현
   * 적절한 <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">개인 정보 보호 기능</Anchor>을 포함합니다

[애드 네트워크에 규정 준수 도구를 구현하기](#앱스플라이어-규정-준수-도구-구현)에서 자세히 알아보세요.

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="새 앱을 추가할 때 어린이용으로 표시하면 어떻게 되나요?">

앱을 추가한 후 2주 후에, 아동 대상 앱의 개인정보 보호 설정을 완료했는지 확인하는 알림을 받게 됩니다. 확인 후 확인 메시지를 받게 됩니다. 알림 센터에서 언제든지 확인 메시지에 액세스할 수 있으며, 감사 로그에서 확인 세부 정보를 볼 수 있습니다.

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="어린이를 대상으로 하는 앱 선택을 변경할 수 있나요?">

이 단계에서 앱이 어린이를 대상으로 하는지 여부를 선택하면 선택을 되돌릴 수 없습니다. 이 옵션은 앱을 추가하는 동안에만 사용할 수 있습니다.

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="팀원 중 누군가가 앱을 어린이용으로 표시했는지 어떻게 알 수 있나요?">

앱이 어린이를 대상으로 하는 것으로 확인되면 다음 두 가지 방법으로 확인한 것을 볼 수 있습니다.

* 알림 센터
* **감사 로그:**
  1. 메뉴 모음에서 사용자 메뉴(이메일 주소 드롭다운)에 액세스하십시오.
  2. 보안 센터를 선택하세요.
  3. 감사 로그 섹션에서 **감사 로그 보기**를 클릭하십시오.  
     내 앱/strong> 서비스에서 확인 세부 정보를 볼 수 있습니다.

</Accordion>

## 앱스플라이어 규정 준수 도구 구현

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="어떤 도구를 사용해야 하는지 어떻게 알 수 있습니까?">

앱이 어린이 또는 다양한 대상(어린이 및 성인)을 대상으로 하는 경우 법적 요구 사항에 부합하는 이 가이드의 권장 도구를 사용할 수 있습니다. 이 페이지 하단에서 더 많은 SDK 리소스를 참조하세요.

#### 규정 준수 도구 및 사용의 예

<table><thead><tr><th>도구</th><th>iOS</th><th>안드로이드</th><th>로데이터 가용성</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">엄격한 SDK</a>:  </p><p>IDFA가 앱스플라이어로 전송되지 않도록 합니다. 일반적으로 어린이를 대상으로 하는 앱에 권장됩니다.</p></td><td><span><span>✓</span></span></td><td>- </td><td>광고주만 사용할 수 있습니다</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p><a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd> API</a>를 사용하는 표준 SDK:</p><p>AAID(Google의 Android 광고 ID)가 앱스플라이어로 전송되지 않도록 합니다. 일반적으로 어린이를 대상으로 하는 앱에 권장됩니다.</p></td><td>- </td><td><span><span>✓</span></span></td><td>광고주만 사용할 수 있습니다</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p><a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>특정</kbd> 애드 네트워크에 대한 <strong>setSharingFilterForPartners</strong> 기능</a>을 사용하는 연령 게이트가 있는 표준 SDK:  </p><p>사용자가 연령 제한\* 미만인 경우 이러한 애드 네트워크가 데이터에 액세스하지 못하도록 합니다.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>특정 애드 네트워크에 대해 제한됨</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p><a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">모든</a> 애드 네트워크에 대해 <kbd><strong>setSharingFilterForPartners</strong> 기능</kbd>을 사용하는 연령 제한이 있는 표준 SDK:</p><p>사용자가 연령 제한\* 미만인 경우 모든 애드 네트워크가 데이터에 액세스하지 못하도록 합니다.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>광고주만 사용할 수 있습니다</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAN 전용</a>:</p><p>광고 ID가 다른 애드 네트워크와 공유되지 않도록 합니다.</p></td><td><span><span>✓</span></span></td><td>- </td><td>광고주만 사용할 수 있습니다</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>SDK가 없는 솔루션(권장하지 않음):</p><p><span>SDK</span><span>를 통해 데이터를 전송하는 대신 앱스플라이어에 데이터를 전송하도록 자체 서버를 구성합니다.</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>구성에 따라</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p>집약형 프라이버시 강화(Aggregated Advanced Privacy, AAP) 프레임워크 </p><p>Apple ATT 개인 정보 보호 수준을 적용하여 <span>광고주 또는 애드 네트워크에서</span> 사용자 수준 데이터를 <span>사용할 수 </span>없도록 합니다.</p></td><td><span><span>✓</span></span></td><td>- </td><td>광고주 또는 애드 네트워크에서는 사용할 수 없습니다</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* 연령 제한 차단을 적용할 때 연령 제한에 속하지 않는 사용자 수준 데이터를 로데이터 리포트에서 사용할 수 있습니다.</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="가이드의 도구를 사용하면 어트리뷰션에 어떤 영향을 미치나요?">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">앱스플라이어 규정 준수 솔루션 가이드</Anchor>는 각각 [다른 수준의 제어 기능을](#how-do-i-know-which-tool-to-use) 갖춘 다양한 도구를 제공합니다. 어트리뷰션에 미치는 영향은 구현하기로 선택한 특정 도구에 따라 다릅니다.

기기 ID와 같은 사용자 데이터 전송을 제한하는 도구를 사용하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">확률적 모델링</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#install-referrer-android-only">인스톨 리퍼러(Android용)</Anchor>와 같은 다른 어트리뷰션 방법이 사용됩니다.

사용자 수준 데이터를 전송하지 않는 도구는 개인 정보를 보호하는 것으로 간주되며 집계된 캠페인 데이터를 수신할 수 있습니다.

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="협업 중인 애드 네트워크가 규정을 준수하는지 모르겠는데 어떻게 해야 하나요?">

협업하는 애드 네트워크가 관련 법을 준수하는지 여부가 불분명한 경우가 많습니다. 이 질문은 애드 네트워크에 문의할 수 있습니다. 만일 그 애드 네트워크가 규정을 준수하지 않거나 확실하지 않은 경우 데이터 공유를 피할 수 있습니다. 이 **<Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` 기능을</Anchor>** 사용하여 앱 데이터 수신을 차단할 애드 네트워크를 지정할 수 있습니다. 이 기능을 사용하여 모든 애드 네트워크를 차단할 수도 있습니다. 더 많은 규정 준수 도구의 예를 참조하세요.

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="애드 네트워크가 규정을 준수하는 경우 앱스플라이어 규정 준수 도구를 구현해야 하나요?">

앱스플라이어 규정 준수 도구는 항상 구현되어야 합니다. 어떤 것이 귀하의 요구에 적합한지는 앱의 오디언스에 따라 다릅니다. 회원님과 협력 중인 애드 네트워크가 COPPA, GDPR, 관련 법률 및 규칙 또는 이를 요구하고 적절한 동의를 받는 기타 플랫폼 규칙에 따라 허용되는 제한된 목적을 위한 데이터 처리자로서만 귀하가 공유한 데이터를 취급하기로 약속한 경우  **<Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` 기능</Anchor>**("MediaSourceName")을 사용할 수 있습니다

이는 협업 중인 각 애드 네트워크에 적용됩니다.

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="애드 네트워크와 어떤 데이터를 공유하나요? 그것을 어떻게 통제할 수 있나요?">

<Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">SRN</Anchor>이 아닌 애드 네트워크는 포스트백을 통해 데이터를 수신합니다. 애드 네트워크는 포스트백에 포함할 이벤트를 정의할 수 있습니다. 인스톨 포스트백은 기본적으로 어트리뷰션을 위해 전송되는 반면, 인앱이벤트 포스트백은 전송하도록 설정하신 특정 이벤트만 전송됩니다.  포스트백이 SDK에 의해 차단되거나 제한되지 않는 한, 앱 사용자 참여(설치, 인앱 이벤트 및 리인게이지먼트)와 관련된 사용자 수준 데이터가 포함될 수 있습니다.

포스트백을 제외하고, 애드 네트워크와 에이전시는 <Anchor target="_blank" href="/marketers/ko/docs/manage-data-access-permissions">플랫폼을 통한 데이터 접근이 제한되어 있습니다</Anchor>.

**포스트백을 통해 애드 네트워크로 전송된 데이터를 확인하는 방법은 다음과 같습니다.**

* 리포트 > <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#postbacks">로데이터 내보내기</Anchor> 메뉴에서 **포스트백 리포트**를 다운로드합니다.

**전송하는 데이터를 제어하려면 다음 단계를 따르세요.**

* 특정 데이터가 전송되지 않도록 차단하거나 제한하기 위하여 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">setSharingFilterForPartners</Anchor> 와 같은 SDK 규정 준수 도구를 사용합니다.
* 누구에게 기본 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">인앱이벤트 포스트백</Anchor>을 보낼지, 이벤트가 어트리뷰션된 애드 네트워크 또는 오가닉을 포함한 모든 미디어소스에서 선택합니다.

**iOS 사용자에 대한 사용자 수준 어트리뷰션 데이터의 가용성을 제어하는 방법은 다음과 같습니다.**

* <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화 프레임워크</Anchor>를 사용하여 Apple ATT 개인 정보 보호 수준을 적용할 수 있습니다.

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="내 앱이 어린이용이고 모든 애드 네트워크가 차단된 경우 SDK가 필요한가요?">

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">SDK 연동 개요</Anchor>
> * SDK SDK: 개인 정보 보호 방법
> * SDK SDK: 사용자 개인 정보 보호 설정
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">앱스플라이어의 개인정보 보호 조치</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HA20EGWDBSNAFZ7WNXJFFRRV=%EA%B0%9C%EC%9A%94 general-questions=%EC%96%B4%EB%A6%B0%EC%9D%B4%EC%9A%A9-%EC%95%B1-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 h_01H9ZK2THJVFYQ49HHRYKZZNEK=%EC%96%B4%EB%A6%B0%EC%9D%B4%EC%9A%A9-%EC%95%B1-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%8F%84%EA%B5%AC-%EA%B5%AC%ED%98%84 h_01HGZ5VAJHNJVM2ENFZ3DEAK42=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%8F%84%EA%B5%AC-%EA%B5%AC%ED%98%84 h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%8F%84%EA%B5%AC-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EC%9D%98-%EC%98%88 h_01HHEED2AQTW7G0MJJZDZV2B09=%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%8F%84%EA%B5%AC-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EC%9D%98-%EC%98%88 standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
