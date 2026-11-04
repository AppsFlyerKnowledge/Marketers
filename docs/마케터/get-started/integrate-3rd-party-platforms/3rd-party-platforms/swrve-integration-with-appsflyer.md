---
title: Steam과 앱스플라이어 연동
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-10-14T10:39:46Z'
  id: 207040656
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/207040656
---
> **한눈에 보기:**

* 이메일

<div id="integrating-swrve-and-appsflyer" />

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.


3단계:

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

3단계:


**<span id="setting-up-swrve"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.   
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

설정 창에서는 연동 탭만 활용합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래 설명과 같이 여러 섹션으로 나누어져 있습니다.

<div id="activate-partner" />

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 ***파트너 활성화*** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="general-settings" />

### 일반 설정

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

* API 키를 입력합니다.

<div id="swrve-reporting-with-appsflyer-data" />

<div id="default-postbacks" />

### 기본 포스트백

앱스플라이어는 유저 인스톨 후 자동 포스트백을 믹스패널로 전송할 수 있습니다. 이 섹션을 사용하여 이러한 포스트백 전송을 정의합니다.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

앱을 다운로드한 모든 사용자에 대해 Braze로 포스트백을 발송하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**를 선택하십시오.

**저장**을 클릭합니다.

* api\_key
* 미디어 소스
* 캠페인 이름

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Braze에서는 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Braze에서는 권한 설정을 사용할 수 없습니다.

</Accordion>


[![](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="h_01H9HWK5DM87JTDVFND0KB965G=%EC%A4%91%EC%9A%94 integrating-swrve-and-appsflyer=%EC%A4%91%EC%9A%94 h_01H9HWK5DM1K9P5XXC6S7ENAGV=%EC%A4%91%EC%9A%94 h_01H9HWK5DMS8HAK25BF5EXZT51=setting-up-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9HWK5DN375XJVHQCZ8Y3K13=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9HWK5DN0XK2E0HXS61GRECE=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9HWK5DNH6SYY8T9NX09MRYS=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9HWK5DN3QB9V593EV566GAQ=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1" />
