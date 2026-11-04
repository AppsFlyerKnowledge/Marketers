---
title: Steam과 앱스플라이어 연동
metadata:
  keywords:
    - Advertisers
    - Batch
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
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-10-14T10:31:30Z'
  id: 360000833437
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/360000833437
---
> **한눈에 보기:**

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 따라서 포스트백 전송 설정에 관계없이 제한된 이벤트 포스트백은 이 파트너에게 전송되지 않습니다.


<div id="setting-customer-user-id" />

<div id="integrating-batch-and-appsflyer" />

### 고객 사용자 ID 가져오기

<Tabs>
<Tab title="안드로이드">

#### Batch

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

<div id="appsflyer" />

#### 앱스플라이어

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective-C">

<div id="appsflyer-1" />

#### Batch

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### 앱스플라이어

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

<div id="appsflyer-2" />

#### Batch

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### 앱스플라이어

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>


**<span id="setting-up-batch"></span><span id="setting-up-batch-in-appsflyer-dashboard"></span>전제 조건:** **연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.**

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서 측면 메뉴의 **협업** > **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법**: 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:  파트너와 협력하는 동안 토글은 반드시 켜져 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor> .**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partner" />

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="general-settings" />

### 일반 설정

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

<div id="viewing-appsflyer-data-in-the-batch-dashboard" />

<div id="default-postbacks" />

### 기본 포스트백

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

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


[![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="h_01H9FK389FZGSK6XPYE73MYEDH=%EC%A4%91%EC%9A%94 integrating-batch-and-appsflyer=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 setting-customer-user-id=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01H9FK389GXG3CDFPNM5ASKJ3N=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01H9FK389MPKFN8J74BX1E3MGG=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01H9FK389MK1HM1460VAT6X82Y=batch appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01H9FK389MPGNEX8B3923KYDB3=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01H9FK389M7V83A66M6T9EV8QT=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01H9FK389MT6PD8FW21SYHBPCV=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01H9FK389MCSR5YDSF4RKFDSDZ=setting-up-batch-in-appsflyer-dashboard h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FK389M19AVM63DEX5JTTQK=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FK389MN82EKHVGMM9Z6H58=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK389MXA3DS403VXRRK5NX=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK389M8BNRFECN0WG23BCD=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1" />
