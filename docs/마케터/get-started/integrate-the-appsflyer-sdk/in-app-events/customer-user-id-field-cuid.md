---
title: 고객 유저 ID 필드(CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-10-14T10:32:29Z'
  id: 207032016
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/207032016
---
> **한눈에 보기:** CUID를 통해 동일한 유저의 이벤트를 다양한 디바이스, 매체소스 또는 채널에서 그룹화할 수 있습니다.

## **CUID란 무엇인가요?**

고객 유저 ID (CUID)는 고유한 유저 식별자입니다. 일반적으로 앱 소유자가 유저를 등록할 때 발생한 설정합니다. CUID를 통해 앱 소유자는 다양한 디바이스에서 유저의 여정을 추적할 수 있습니다.

> 📄 **예시**
>
> 두 개 이상의 디바이스를 사용하는 유저는 앱 내에서 동일한 CUID를 가집니다. 유저가 모바일이나 데스크톱 디바이스에서 이벤트를 수행할 때마다 해당 이벤트는 CUID와 함께 캡처됩니다. 이를 통해 광고주는 디바이스의 데이터를 통합하여 전체적인 유저 뷰를 얻을 수 있습니다.
>
> 몇 가지 사용 사례:
>
> * 같은 앱에서 동일한 유저가 여러 디바이스(휴대폰, 태블릿, TV, 데스크톱)에서 인앱 구매를 수행할 경우 단일 뷰로 결합할 수 있습니다.
> * 다양한 플랫폼(데스크톱, 모바일, TV)에 설치된 게임에 대한 유저 성과가 이러한 플랫폼 간에 공유되어 전체적인 유저 경험을 달성할 수 있습니다.

## **CUID 설정방법**

SDK 초기화 흐름에서 가능한 한 일찍 CUID를 설정하여 가능한 많은 이벤트가 CUID와 연관될 수 있도록 권장합니다.

<Tabs>
<Tab title="안드로이드 네이티브">

CUID를 사용할 준비가 되면 `setCustomerUserID`를 호출하여 설정할 수 있습니다. CUID는 설정된 후 발생한 인앱 이벤트만 연관될 수 있습니다. 따라서 `setCustomerUserID`이 `setCustomerUserID` 전에 호출되면 인스톨 이벤트는 CUID와 연관되지 않습니다.

### **CUID를 인스톨 이벤트와 연결하기**

인스톨 이벤트를 CUID와 연결하는 것이 중요하다면, `start`을 호출하기 전에 설정해야 합니다.

**중요:**  `start` 앞에서 CUID를 설정하면 SDK가 인스톨 이벤트를 발송하지 않아 어트리뷰션이 발생하지 않을 수 있습니다. 예를 들어, 유저가 앱을 처음 실행한 후 SDK가 CUID를 설정하기 전에 종료하는 경우 이러한 상황이 발생할 수 있습니다.

안드로이드에서는 `start` 메서드와 CUID 설정을 앱 구현에 따라 글로벌 `Application` 클래스 또는 `Activity` 클래스에서 실행할 수 있습니다. 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#sdk를-어느-클래스에서-시작할지-선택하세요">SDK를 시작할 클래스를 선택</Anchor>를 참조하세요.

#### SDK가 Application 클래스에서 시작되는 경우

글로벌 `Application` 클래스에서 인스톨 이벤트와 CUID를 연관시키려면 `waitForCustomerUserId` 메서드를 사용하여 인스톨 이벤트 발송을 지연시켜야 합니다. 이 메서드는 CUID가 설정될 때까지 SDK를 대기 모드로 전환합니다.

참고: CUID 설정이 실패하면 SDK는 대기 모드 상태로 남아 이벤트를 발송하지 않습니다.

#### SDK가 액티비티 클래스에서 시작되는 경우

`Activity` 클래스에서 시작할 때 CUID를 인스톨 이벤트와 연관시키려면 인스톨 이벤트 발송을 지연할 필요가 없습니다. `start`를 호출하기 전에 `start`을 호출하세요.

#### 개발자 지침

개발자에게 다음 사항을 알려주세요:

* SDK가 글로벌 `Application` 클래스에서 시작되는 경우 `waitForCustomerUserId`을 사용합니다.
* 개발자 링크:
  * CUID를 인스톨 이벤트와 연결하려면 [여기](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event)를 참조하세요.

</Tab>

<Tab title="iOS 네이티브">

`customerUserId` 메서드를 사용하여 CUID를 설정합니다. `start` 메서드와 관련된 `start`의 위치는 CUID와 연관될 수 있는 이벤트를 결정합니다.

* `start`를 호출하기 전에 `customerUserId`이 호출되면 CUID는 인스톨 및 그 후의 인앱 이벤트와 연결됩니다.
* `start` 이후 호출되면, CUID는 CUID 설정 후 기록된 이벤트에만 연결됩니다.

#### 개발자 지침

귀사의 개발자에게 Dev Hub에서 [고객 유저 ID 설정](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id)을 확인하도록 하세요.

</Tab>

<Tab title="유니티">

#### 개발자 지침

귀사의 개발자에게 Dev Hub에서 [고객 유저 ID 설정](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id)을 확인하도록 하세요.

</Tab>

<Tab title="리액트 네이티브">

#### 개발자 지침

귀사의 개발자에게 Dev Hub의 [setCustomerUserId](https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid) API 참조를 확인하도록 하세요.

</Tab>
</Tabs>

## **CUID 및 프라이버시**

앱스플라이어는 귀사의 사용자의 프라이버시를 중시하고 존중하며, [앱스플라이어 플랫폼으로의 민감한 개인 데이터의 수집 또는 전송을 허용하지 않습니다.](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

귀사의 사용자 프라이버시 보호를 위해, CUID에 사용자를 직접 식별하는 정보를 포함해서는 안 됩니다. 여기에는 소셜 보안 번호나 국민식별번호가 포함됩니다.

또한, 설정된 CUID에 사용자의 이메일 주소나 전화번호가 포함된 경우, 이러한 정보는 앱스플라이어에 발송할 때 반드시 해시되어야 합니다. 개인 정보가 포함된 해시되지 않은 CUID를 앱스플라이어로 발송하는 것은 금지되어 있습니다.

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#유저-여정-리포트">유저 여정 보고서</Anchor> (로데이터 리포트에서 CUID에 대한 자세한 내용)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">PII 전송 방지를 위한 Google 모범 사례</Anchor>

<div data-zendesk-anchors="what-is-cuid=cuid%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HAJ00DVHRSDBS4FFKM16JFER=cuid%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HAJ00DVHZ8V8MRAXN2W3T8DS=%EC%98%88%EC%8B%9C setting-the-cuid=cuid-%EC%84%A4%EC%A0%95%EB%B0%A9%EB%B2%95 h_01HAJ00DVHDGM133A72HD5JXER=cuid-%EC%84%A4%EC%A0%95%EB%B0%A9%EB%B2%95 associate-the-cuid-with-the-install-event=cuid%EB%A5%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%97%B0%EA%B2%B0%ED%95%98%EA%B8%B0 h_01HAJ00DVHDE9V2MT6JQF8SAH3=cuid%EB%A5%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%97%B0%EA%B2%B0%ED%95%98%EA%B8%B0 if-the-sdk-starts-in-the-application-class=sdk%EA%B0%80-application-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%EB%90%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 h_01HAJ00DVH746B6YJVF70PMZJ8=sdk%EA%B0%80-application-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%EB%90%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 if-the-sdk-starts-in-an-activity-class=sdk%EA%B0%80-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%EB%90%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 h_01HAJ00DVHYZBER40RJH0GM8KF=sdk%EA%B0%80-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%ED%81%B4%EB%9E%98%EC%8A%A4%EC%97%90%EC%84%9C-%EC%8B%9C%EC%9E%91%EB%90%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 developer-instructions-android=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 h_01HAJ00DVHZBZCRA1VGYJY44VY=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 developer-instructions::31dbab4b=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 h_01HAJ00DVH2RV902D6G224A4QY=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 developer-instructions-unity=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 developer-instructions-react=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%A7%80%EC%B9%A8 cuid-and-privacy=cuid-%EB%B0%8F-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C h_01HAJ00DVH4987JGZZVDA1NB29=cuid-%EB%B0%8F-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C h_01HE7RXTEPQAWV03276TDEPG0V=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
