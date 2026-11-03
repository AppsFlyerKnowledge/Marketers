---
title: 푸쉬 알림 리인게이지먼트 캠페인 측정
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-10-14T10:37:44Z'
  id: 207364076
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/207364076
---
> **한눈에 보기:** 요약: iOS 및 안드로이드 모두에서 푸시 알림 캠페인을 측정합니다.

## 개요

앱스플라이어는 Firebase 클라우드 메시징 또는 APNS(Apple 푸시 알림 서비스) 상단에 직접 구현된 캠페인뿐만 아니라 모든 푸시 제공업체의 푸시 알림 캠페인 측정을 지원합니다.

연동을 구현하는 가능한 방법에는 다음의 두 가지가이 있습니다.

* 푸시 알림의 페이로드에 `af`afaf 키가 있는 JSON 오브젝트 전송(레거시).

전환 결과는 개요 대시보드, 리타겟팅 또는 통합 보기에 표시됩니다.

## 어떻게 작동하나요?

본 기사에서 설명한 단계를 완료하면 앱이 다음과 같이 작동합니다.

2. 앱 사용자는 푸시 알림을 수신하고 클릭합니다.
3. 앱이 로드되고 앱스플라이어 SDK가 시작됩니다.
4. SDK는 앱을 연 푸시 알림의 페이로드를 처리합니다.
5. SDK는 어트리뷰션 데이터를 추출하여 앱스플라이어로 보냅니다.

원링크 시나리오에서 원링크가 사용자를 앱의 특정 위치로 라우팅하도록 설정된 경우 딥링크 흐름이 트리거됩니다.

## 필수 조건

계속하기 전에 앱에 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide">앱스플라이어 SDK가 연동</Anchor>되어 있는지 **그리고** 푸시 알림을 수신할 수 있는 지 확인하십시오.

## 단계

푸시 알림 측정을 설정하려면 다음 단계를 완료해야 합니다.

1. 원링크 템플릿이 포함된 커스텀 데이터 키 [또는](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) JSON 오브젝트가 값으로 포함된 **af** 키가 포함된 `af`푸시 알림af을 생성합니다.
2. [커스텀 키를 확인하도록 SDK를 설정합니다](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (앱 개발자가 수행).
3. 푸시 알림을 트리거하여 [연동을 테스트합니다](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration).
4. 대시보드에서 [푸시 알림 캠페인 성과를 표시합니다](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard).

<div id="1-creating-the-push-notification" />

<Accordion title="1. 1. 푸시 알림 생성">

먼저 다음 방법 중 하나를 사용하여 어트리뷰션 데이터가 포함된 푸시 알림을 만듭니다.

> 📘 **참고사항**
>
> 다음 데모에서는 Firebase를 푸시 제공업체로 사용합니다. 지침은 약간의 차이(있는 경우)가 있더라도 모든 푸시 제공업체에 적용되어야 합니다. 해당 푸시 제공업체의 설명서를 참조하십시오.

<Tabs>
<Tab title="원링크 사용(권장)">

#### **원링크 사용(권장)**

푸시 알림과 앱스플라이어를 통합하는 권장 방법입니다.

1. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">원링크 템플릿을 만들어 리타겟팅용으로 설정합니다.</Anchor>  
   **참고**: 참고: 원링크의 단축 URL과 긴 URL이 모두 지원됩니다.
2. 푸시 알림 커스텀 데이터에서 앱스플라이어로 보내려는 어트리뷰션 데이터가 포함된 원링크를 추가합니다.

> 📄 **Firebase 예시**
>
> Firebase에서:
>
> [![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="JSON 사용(레거시)">

<div id="using-json-legacy" />

#### **JSON 사용(레거시)**

> 📘 **참고사항**
>
> 다음은 푸시 알림과 앱스플라이어를 연동하는 레거시 방법을 문서화하며 이전 버전과의 호환성을 위해 사용할 수 있습니다. 새 앱을 설정하는 경우 [권장되는 원링크 기반 솔루션](/docs/measuring-push-notification-re-engagement-campaigns#원링크-사용권장)을 사용하십시오.

푸시 알림의 커스텀 데이터에서 JSON 형식으로 앱스플라이어에 보내려는 어트리뷰션 데이터가 포함된 `af`afaf라는 커스텀 키를 추가합니다. 다음 어트리뷰션 파라미터는 필수입니다.

* `pid`
* `is_retargeting`
* `c`

> 📄 **Firebase 예시**
>
> Firebase에서:
>
> [![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. 2. SDK 설정">

이 작업을 수행하려면 앱 코드를 변경해야 합니다. SDK 설정 방법에 대한 지침을 따르십시오.

* 권장되는 원링크 기반 솔루션을 구현하는 경우:
  1. 알림에 추가한 커스텀 키의 이름이 무엇인지 앱 개발자에게 알려주십시오.
  2. 그들에게 이 지침을 보내십시오.
* 레거시 JSON 기반 솔루션을 구현하는 경우 개발자에게 이 지침을 보내십시오.

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. 3. 연동 테스트">

푸시 알림 측정이 올바르게 연동되었는지 테스트하려면 1단계에서 설정한 캠페인에서 푸시 알림을 트리거하기만 하면 됩니다.

모든 것이 올바르게 구성된 경우 SDK는 다음을 수행합니다.

1. 푸시 알림을 받습니다.
2. 푸시 알림에 포함된 어트리뷰션 데이터를 처리하여 앱스플라이어로 보냅니다.
3. 원링크를 사용하여 푸시 알림 측정을 구현하는 경우 일반 딥링킹 흐름을 진행합니다.

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. 4. 대시보드에서 푸시 알림 캠페인 보기">

<Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#retargeting-dashboard">리타게팅 대시보드</Anchor>에서 푸시 알림에서 발생한 데이터를 볼 수 있습니다.

**참고**: 참고: 앱스플라이어는 푸시 알림 데이터를 중복 제거합니다. 즉, 동일한 페이로드가 두 번 이상 수신되면 하나만 계산됩니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01J5XFSEG9DR31DP73KTAGQPFW=%EA%B0%9C%EC%9A%94 how-does-it-work=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01J5XFSEG967HXNT3GFSC2AQYE=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01J5XFSEG91SER3JKB3RKK6B6G=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 steps=%EB%8B%A8%EA%B3%84 h_01J5XFSEG9W3RTP62NW7SV4D0F=%EB%8B%A8%EA%B3%84 h_01J5XFSEG9PXHTD4C9XCDC01DH=1-creating-the-push-notification h_01J5XFSEG9C2C1Z8HK4R1V03H1=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD using-onelink-recommended=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%82%AC%EC%9A%A9%EA%B6%8C%EC%9E%A5 h_01J5XFSEG9W73JYPHH9VRZSTZ8=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%82%AC%EC%9A%A9%EA%B6%8C%EC%9E%A5 h_01J5XFSEG97PMRHV20V1VG0SP4=firebase-%EC%98%88%EC%8B%9C h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy h_01J5XFSEG9G7QV4N4JATS8W3MX=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01J5XFSEG9XAQ1KMB088GFK4YS=firebase-%EC%98%88%EC%8B%9C h_01J5XFSEG9GYMKAT27AWTN1WZZ=2-configuring-the-sdk h_01J5XFSEG91NH41QMV9K3S4F18=3-testing-the-integration h_01J5XFSEG904NC72K8MWX9YM06=4-viewing-push-notification-campaigns-in-the-dashboard" />
