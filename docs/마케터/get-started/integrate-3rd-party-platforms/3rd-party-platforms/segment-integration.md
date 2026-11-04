---
title: 세그먼트 연동
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-10-14T10:26:04Z'
  id: 210041606
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/210041606
---
> **한눈에 보기:** Segment 분석 데이터를 앱스플라이어에 전송합니다.

<div id="introduction" />

## 소개

Segment를 사용하면 데이터를 앱스플라이어로 쉽게 전송할 수 있습니다. Segment의 오픈 소스 라이브러리를 통해 데이터를 기록한 경우 데이터가 적절한 형식으로 변환되어 앱스플라이어로 라우팅됩니다. 마케터는 앱스플라이어를 사용해 타겟팅을 정확히 찾아내고, 광고 지출을 최적화하며, ROI를 높일 수 있습니다.

<div id="integrating-segment-with-appsflyer" />

## Segment와 앱스플라이어 연동하기

<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">Segment의 이 가이드</Anchor>를 따라 Segment를 앱스플라이어와 연동하는 방법을 알아보세요.

<div id="faqs" />

## 자주 묻는 질문

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="Segment를 앱스플라이어와 연동하려면 어떻게 해야 하나요?">

Segment를 앱스플라이어와 연동하려면 다음 단계를 따르세요.

* 앱스플라이어에 연결하도록 <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Segment 대시보드를 구성합니다</Anchor>.
* 앱에서 [Segment Wrapper SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work)를 실행합니다.
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">네이티브 iOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">네이티브 안드로이드</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="내 앱에 어떤 SDK를 추가해야 하나요?">

Segment SDK 래퍼만 추가하면 됩니다. Segment SDK 래퍼 종속성을 추가하면 앱 빌드 프로세스가 Segment SDK와 앱스플라이어 SDK를 앱에 자동으로 추가합니다.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="SDK 래퍼는 어떻게 작동하나요?">

Segment SDK 래퍼는 Segment SDK와 앱스플라이어 SDK를 연결합니다.

Segment SDK 래퍼를 사용하여 설치 및 인앱 이벤트를 기록하기 위해 Segment의 메서드를 호출하는 경우, SDK 랩퍼는 Segment 메서드와 앱스플라이어 메서드를 모두 호출합니다.

따라서 시간과 노력이 절약되고 코딩이 덜 필요합니다.

<div id="warning" />

> ❗️ **경고**
>
> 경고 - Segment SDK 래퍼와 앱스플라이어 SDK의 메서드는 모두 **사용하지 마세요**. 사용할 경우 오류 및 데이터 불일치가 발생할 수 있습니다.
>
> **Segment SDK 래퍼의 메서드만 사용하세요.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Segment SDK 래퍼와 앱스플라이어 SDK 간에 기능의 차이가 있습니까?">

아니요, 기능에는 변화가 없습니다. 앱스플라이어 SDK의 모든 기능은 Segment SDK 래퍼에서 사용할 수 있습니다.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="앱스플라이어 대시보드에서 인앱 이벤트 데이터를 볼 수 없습니다.">

* Segment SDK 래퍼에서 track 메서드 구현 지침을 따라야 합니다.
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">안드로이드</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">iOS</Anchor>
* Segment의 대시보드에서 앱스플라이어를 연동할 때 <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">dev 키를 지정하세요</Anchor>.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Segment와 앱스플라이어의 설치 및 인앱 이벤트 데이터가 일치하지 않습니다.">

Segment SDK Wrapper만 사용하려면 Segment SDK Wrapper를 앱스플라이어 SDK와 결합하면 안 됩니다. 자세한 내용은 [여기](/docs/segment-integration#how-does-the-sdk-wrapper-work)를 참조하세요.

또한 [위의 FAQ](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard)에서는 Segment와 앱스플라이어 간에 데이터가 정렬되지 않을 수 있는 이유를 상술합니다.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="Segment에서 이벤트를 테스트할 때 유효성 검증 오류가 발생합니다.">

***대상*** 페이지에서 ***Event Tester***를 사용하여 이벤트를 테스트할 때 오류가 발생할 수 있습니다. ***유효성 검증 오류 앱스플라이어 디바이스 ID('integrations.AppsFlyer.appsFlyerId')는 서버 간 이벤트 전송에 필수적입니다***.

이 오류가 발생한다고 해서 Segment와 앱스플라이어 간 연동에 문제가 있다는 의미는 아닙니다. Event Tester를 사용하면 Segment에서 앱스플라이어로 서버 간 전송을 테스트할 수 있습니다. 서버 간 연결을 사용하여 전송되는 모든 이벤트에는 AppsFlyerID가 필요하며, 그게 바로 이벤트 테스터가 오류를 발생시키는 이유입니다.

그러나 이는 서버 간 이벤트에만 관련이 있습니다. Segment SDK API를 사용하여 이벤트를 기록하면 SDK에서 Segment와 앱스플라이어로 모두 이벤트가 전송됩니다. 앱스플라이어 API 호출의 경우 앱스플라이어 디바이스 ID가 포함됩니다.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="나는 타사 분석 도구를 사용하고 있습니다. 앱스플라이어 및 Segment 모두와 연동해야 합니까?">

아니요, Segment 대시보드만 사용하여 타사 분석 도구를 활성화해야 합니다.

</Accordion>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01JZMD855TA62KQ4AWJ5F6WSDP=%EC%86%8C%EA%B0%9C integrating-segment-with-appsflyer=segment%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01JZMD855TNEYZG1MDZY7FWV8S=segment%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 faqs=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01JZMD855TAEBDPAMEAEH66F27=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=%EA%B2%BD%EA%B3%A0 h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />
