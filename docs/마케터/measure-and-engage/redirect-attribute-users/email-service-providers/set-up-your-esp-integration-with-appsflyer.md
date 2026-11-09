---
title: '[클로즈 베타 - 특별 접근] AppsFlyer와의 ESP 통합 설정'
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-10-14T10:36:35Z'
  id: 26967438815377
  locale: ko
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ko/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** AppsFlyer와의 ESP 통합을 설정하여 이메일 캠페인에서 원활하고 안전한 딥 링크를 활성화하여 사용자 참여 및 전환율을 향상시킵니다.

<Image align="center" alt="ESP final main KB image.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

<div id="about-the-appsflyer-esp-integration" />

## AppsFlyer ESP 통합에 대하여

마케터들은 종종 대규모 이메일 캠페인을 보내기 위해 이메일 서비스 제공업체(ESP)를 사용합니다. 이 과정은 간단해야 하지만, 예측 가능한 사용자 여정을 제공하는 것은 종종 그렇지 않습니다. 그 이유는 일반적인 ESP가 분석을 처리하는 방식에 있으며, 이는 딥 링크를 깨뜨리고 모바일 사용자 경험에 부정적인 영향을 미치는 경향이 있습니다. 결과적으로 사용자는 때때로 앱 대신 모바일 웹사이트로 라우팅되어 전환 가능성이 낮아집니다.

AppsFlyer는 ESP 통합 솔루션으로 이 문제를 해결하며, 이를 통해 AppsFlyer가 ESP 서버와 귀하의 도메인 이름 사이의 중개 역할을 할 수 있습니다. 프록시로 작동하여 딥링킹을 가능하게 하는 연결 파일(AASA/애셋 링크)을 제공합니다. 또한, AppsFlyer 솔루션은 측정 데이터를 귀하의 ESP로 다시 전송하여 이메일 분석을 효과적으로 모니터링할 수 있도록 합니다.

AppsFlyer와의 ESP 통합을 설정하여 이메일 캠페인에서 원활하고 안전한 딥 링크 경험을 제공하고, 최적의 모바일 사용자 참여 및 전환율을 달성하세요.

<div id="set-up-the-integration" />

## 연동을 설정하려면:

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>이 섹션에서는 AppsFlyer와의 ESP 통합을 설정하는 방법을 설명합니다.

<div id="prerequisites" />

### 선행 조건

AppsFlyer와의 ESP 통합을 설정하기 전에 지원되는 ESP*에 계정이 있어야 합니다. 다음 항목이 필요합니다:

* 새로운 **클릭 추적 도메인** (에서 [1단계.](#step-1-create-a-onelink-template-for-your-email-campaign))
* **ESP 엔드포인트**: 엔드포인트는 클릭을 해당 서버로 라우팅할 수 있도록 ESP에서 제공됩니다. ESP 엔드포인트 구조의 예: esp.endpoint.com.
* **특정 ESP 통합 요구 사항:**
  * **Emarsys** - Emarsys 고객 성공 관리자에게 HTTP 리디렉션을 활성화해 달라고 요청하세요.
  * **Blueshift** - Blueshift 고객 성공 관리자에게 요청하세요.  
    클릭에 대한 HTTP 응답 코드를 기본값 307에서 302로 변경합니다.

**통합을 설정하려면 다음 단계를 따르십시오:**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="1단계: ESP 플랫폼에서 클릭 추적 도메인을 생성합니다 (IT / 시스템 관리자 작업)">

클릭 추적 도메인(CTD)은 이메일 메시지에 나타나는 URL의 도메인 구성 요소입니다.   
서브도메인과 기본 도메인으로 구성되며, 예: mail.yourbrand.com입니다. 다른 ESP는 이를 링크 브랜딩, 추적기 도메인, 클릭 도메인, 링크 재작성, 클릭 추적 또는 화이트 라벨링이라고 부를 수 있습니다.

**새 CTD를 만드는 것은 필수입니다**, 기존의 것을 이미 사용하고 있더라도. 이것은 현재 진행 중인 이메일 캠페인의 트래픽에 영향을 미치지 않도록 보장합니다.

<div id="notes" />

> 📘 **참고**
>
> * SSL 인증서는 AppsFlyer에 의해 처리됩니다 (3단계에서).
> * 이 단계에서는 이메일 링크가 보안되지 않을 가능성이 높으며, URL 접두사는 HTTPS 대신 HTTP가 됩니다. 이는 [5단계에서 해결됩니다.](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).

</Accordion>

<div id="h_01JMYD02VRGT8353RDBARRPJ2M" />

<div id="step-2-use-a-oneLink-template-for--your-email-campaign" />

<Accordion title="2단계: 이메일 캠페인에 OneLink 템플릿을 사용하십시오.">

<Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">OneLink 템플릿</Anchor>을 생성하고 "**앱이 설치되었을 때**" 아래에서 유니버설 링크/앱 링크를 구성합니다. 이 템플릿은 나중에 이메일 캠페인을 위한 OneLink 링크를 생성하는 데 사용됩니다.

*이미 유니버설 링크/앱 링크를 활성화하는 기존 OneLink 템플릿이 구성되어 있다면, 이를 사용할 수 있습니다.

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="3단계: AppsFlyer에서 ESP 통합을 설정하십시오.">

이제 AppsFlyer에서 ESP 통합을 설정할 시간입니다. 이 단계와 다음 단계("[4단계. 앱을 구성하십시오](#step-2-configure-your-app-developer-task)")는 동시에 설정할 수 있습니다.

**AppsFlyer에서 ESP 통합을 설정하려면:**

1. **AppsFlyer**의 사이드 메뉴에서 **Engage** > **ESP 통합**을 선택합니다.

<Image align="center" alt="Engage 클릭 ESP 통합.png" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. 당신의 ESP를 선택하세요.

<Image align="center" alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3. 이메일 캠페인에 사용할 OneLink 템플릿을 선택한 후 **다음**을 클릭하세요.

<Image align="center" alt="select OneLink template.png" src="https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png" />

4. 선택한 ESP에 활성 계정이 있는지 확인하세요.

ESP에서 다음을 준비해야 합니다:

* 1단계에서 생성한 클릭 추적 도메인입니다.
* ESP 엔드포인트

**다음**을 클릭합니다.

5. 클릭 추적 도메인과 ESP 엔드포인트를 입력한 후 **연결 확인**을 클릭하세요. 이것은 클릭 추적 도메인이 입력한 엔드포인트를 가리키는지 확인합니다.

<Image align="center" alt="ctd 및 esp 엔드포인트 입력.png" src="https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png" />

완료되면 **다음**을 클릭합니다.

6. 링크 트래픽을 앱스플라이어로 라우팅

a. **AppsFlyer에서 사용자 정의된 미리 작성된 지침을 복사하여 IT 또는 도메인 관리자에게 보내세요.** 그들은 ESP 서버에서 AppsFlyer 서버로 이메일 캠페인 트래픽을 리라우트해야 하며, AppsFlyer에서 제공한 새 도메인으로 DNS CNAME 레코드를 업데이트해야 합니다.

결과적으로, 링크가 클릭될 때마다 클릭은 AppsFlyer로 리디렉션되고, 다시 ESP 엔드포인트로 리디렉션됩니다.

<Image align="center" alt="Af에서 ESP로 클릭 이미지.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

b. 지침을 복사하고 보낸 후 **완료**를 클릭하세요.

당신의 ESP 통합이 생성되었습니다.

다음을 참조하십시오.

* - ESP 연동 상태는 보류 중이며 CNAME 레코드가 매핑된 후에야 작업이 시작됩니다.
* - 새 연동이 작동을 시작하고 활성화되려면 매핑 후 최대 24시간이 소요될 수 있습니다.

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="4단계: 앱을 구성하세요 (개발자 작업)">

개발자에게 앱에 다음 구성을 하도록 하세요:

* [앱이 연관된 도메인을 지원하도록 구성하세요](#앱이-연관된-도메인을-지원하도록-구성하세요)
* [앱이 딥 링크를 지원하도록 구성하세요](#앱이-딥-링크를-지원하도록-구성하세요)
* [앱이 웹 링크 및 애플리케이션 링크를 처리하도록 구성하세요](#웹-링크-및-애플리케이션-링크를-처리하도록-앱을-구성하세요)

<div id="configure-your-app-to-support-associated-domains" />

#### **앱이 연관된 도메인을 지원하도록 구성하세요**

AppsFlyer는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#유니버설-링크">유니버설 링크(iOS)</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#안드로이드-앱-링크">앱 링크(Android)</Anchor>를 활성화하기 위해 귀하의 앱에 대한 앱 연관 파일을 호스팅합니다.

**앱이 파일에 접근하도록 구성하려면:**

**iOS**  
**전제 조건:** SDK 버전 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
앱으로의 이메일 메시지에서 유니버설 링크를 활성화하도록 앱을 구성하세요.  
<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">유니버설 링크</Anchor> 구성에 대해 자세히 알아보세요.  
**참고:** 클릭 도메인은 이미 연관된 도메인에 정의된 현재 도메인에 추가되어야 합니다.

**안드로이드**  
**전제 조건:** SDK 버전 <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
앱으로의 이메일 메시지에서 Android 앱 링크를 활성화하도록 앱을 구성하세요. Android <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#유니버설-링크">앱 링크</Anchor> 구성에 대해 자세히 알아보세요.  
**참고:** 클릭 도메인은 Android 매니페스트에 이미 정의된 현재 도메인에 추가되어야 합니다.


<div id="configure-your-app-to-support-deep-linking" />

#### **앱이 딥 링크를 지원하도록 구성하세요**

앱 링크 또는 유니버설 링크를 클릭하면 앱이 열려야 합니다.

**앱이 클릭 기록 도메인 뒤에 있는 OneLink를 추출하고 딥 링크를 해결하도록 활성화하려면:**

1. 클릭 기록 도메인을 SDK API resolveDeepLinkURLs에 제공하세요. 이 API는 SDK 초기화 전에 호출되어야 합니다.

* iOS의 경우 다음 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">지침</Anchor>을 따르세요.
* Android의 경우 다음 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">지침</Anchor>을 따르세요.

2. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">통합 딥링크 API</Anchor>를 사용하여 딥 링크 매개변수를 가져오고 딥 링크 데이터를 처리합니다.


<div id="if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />

<div id="do-i-need-to-create-an-ssl-certificate-at-any-point" />

<div id="faq" />

<div id="configure-your-app-to-handle-weblinks-and-application-links" />

#### **웹 링크 및 애플리케이션 링크를 처리하도록 앱을 구성하세요**

제공된 코드는 이메일 캠페인 내에서 래핑된 링크의 기능을 규제하는 것을 목표로 하며, 특히 두 가지 유형을 다룹니다: 웹사이트를 열기 위한 웹 링크와, 유니버설 링크 또는 앱 링크를 통해 앱을 열기 위해 설계된 링크입니다.  
개발자 정보에 대한 자세한 내용은 다음 가이드를 참조하세요:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">iOS Deep Linking ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Android Deep Linking ESP 2.0</Anchor>

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="5단계: ESP 플랫폼에서 SSL 클릭 추적이 활성화되어 있는지 확인하세요.">

링크 상태를 확인하기 위해 이메일 테스트를 수행하세요.   
CTD 링크가 HTTP로 식별되면, SSL 클릭 추적을 활성화하기 위해 ESP 팀에 문의하세요.   
이렇게 하면 모든 HTTP 링크가 자동으로 HTTPS로 변환됩니다.

ESP에 연락할 때 다음 샘플 메시지 텍스트를 사용할 수 있습니다:

안녕하세요 팀,  
CTD XXX에 대해 SSL 클릭 추적을 활성화해 주실 수 있나요? 현재 HTTPS 대신 HTTP로 설정되어 있습니다.   
이 업데이트에 대한 귀하의 도움에 감사드립니다.

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="6단계: AppsFlyer에서 이메일 캠페인을 위한 OneLink 링크를 사용자 정의하세요.">

**캠페인을 위한 OneLink 링크를 생성하고 사용자 정의하려면:**

1. AppsFlyer에서 이전에 생성한 OneLink 템플릿 내에서 OneLink 관리 페이지(또는 수동으로)에서 "이메일-앱" OneLink 링크를 생성하세요. 이 링크는 귀하의 사양에 따라 사용자를 귀하의 이메일 캠페인에서 귀하의 사양에 따라 귀속시키고 리디렉션하는 데 사용됩니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">OneLink 링크</Anchor>를 생성하는 방법을 알아보세요.

<Image align="center" alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**모범 사례:** ESP 이메일 캠페인과 해당 캠페인에서 사용되는 AppsFlyer OneLink 링크 모두에서 동일한 캠페인 이름을 사용하세요.

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="2단계: ESP 플랫폼에서 통합을 테스트하세요">

**당신이 만든 OneLink 링크와 통합을 테스트하기 위해:**

당신이 만든 테스트 이메일에 OneLink URL을 삽입하고 자신에게 보내세요.

* 모바일 기기에서 이메일을 열고 링크를 클릭하세요. 앱이 설치되어 있다면, 앱이 열리고 관련 콘텐츠로 깊이 연결됩니다. 또한, 모바일 클릭이 제공된 미디어 소스와 캠페인에 귀속되어 AppsFlyer 대시보드에 나타나야 하며, ESP 분석 대시보드에서도 나타납니다.
* 웹 링크를 클릭하고 올바른 목적지로 리디렉션되는지 확인하세요.

테스트가 성공하면, 모든 준비가 완료된 것입니다.

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="2단계: 이메일 캠페인에서 링크를 자신 있게 사용하세요">

잘 하셨습니다! 이제 이메일 캠페인에서 링크를 사용할 준비가 되었습니다. 그 후, ESP 또는 AppsFlyer 대시보드에서 캠페인 결과를 확인할 수 있습니다.

</Accordion>

*이 통합에서 지원하는 ESP는 다음과 같습니다: Blueshift, Braze, CleverTap, Customer.io, Emarsys, Expert Sender, Klaviyo, MailExpress, MailGun, Moengage, RDStation, Reteno, Sailthru, Sendgrid, Sparkpost 등입니다. 전체 <Anchor target="_blank" href="/marketers/ko/docs/email-service-provider-esp-integration-guide">목록</Anchor>을 확인하세요.

<div data-zendesk-anchors="overview=appsflyer-esp-%ED%86%B5%ED%95%A9%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01J6RXTXCS7WC0P5X4J96T8JAP=appsflyer-esp-%ED%86%B5%ED%95%A9%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01J3JHJCCASM6E5QYJB5VHQ8HK=appsflyer-esp-%ED%86%B5%ED%95%A9%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC set-up-your-esp-integration-with-appsflyer=%EC%97%B0%EB%8F%99%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%A0%A4%EB%A9%B4 h_01J3JHFRGA6BTMWSK7EEEVGS6T=%EC%97%B0%EB%8F%99%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%A0%A4%EB%A9%B4 prerequisites=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01J3JJ74GYF5AJT9R2P2CXDXE1=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=%EC%B0%B8%EA%B3%A0 step-2-use-a-oneLink-template-for-%20your-email-campaign=step-2-use-a-oneLink-template-for--your-email-campaign h_01JMYD02VRGT8353RDBARRPJ2M=step-2-use-a-oneLink-template-for--your-email-campaign h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=%EC%95%B1%EC%9D%B4-%EC%97%B0%EA%B4%80%EB%90%9C-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8F%84%EB%A1%9D-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3W8XR5QS227XNCD453RWYZ9=%EC%95%B1%EC%9D%B4-%EC%97%B0%EA%B4%80%EB%90%9C-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8F%84%EB%A1%9D-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 configure-your-app-to-support-deep-linking=%EC%95%B1%EC%9D%B4-%EB%94%A5-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%A7%80%EC%9B%90%ED%95%98%EB%8F%84%EB%A1%9D-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3WS4QWMRT8KSW6J3QHXM9TQ=%EC%95%B1%EC%9D%B4-%EB%94%A5-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%A7%80%EC%9B%90%ED%95%98%EB%8F%84%EB%A1%9D-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3W8Y7FMSWPG7MFF6FMSXFM3=%EC%95%B1%EC%9D%B4-%EB%94%A5-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%A7%80%EC%9B%90%ED%95%98%EB%8F%84%EB%A1%9D-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 ::250c928e=%EC%9B%B9-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%B2%98%EB%A6%AC%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 configure-your-app-to-handle-weblinks-and-application-links=%EC%9B%B9-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%B2%98%EB%A6%AC%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3WS4QWMSKZ33APWFR8CG5TZ=%EC%9B%B9-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%B2%98%EB%A6%AC%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3W8ZMHSXQGJPQEVR62Q28X9=%EC%9B%B9-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%B2%98%EB%A6%AC%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />
