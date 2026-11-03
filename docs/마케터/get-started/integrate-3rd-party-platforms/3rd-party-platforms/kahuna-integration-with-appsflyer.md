---
title: 앱스플라이어와 Vidaa 연동
metadata:
  keywords:
    - kahuna
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
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-10-14T10:38:43Z'
  id: 212561966
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/212561966
---
> **한눈에 보기:**

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.

아래 지침에 따라 Braze와의 연동을 구성하십시오.

1. 최소 요구사항 - 앱스플라이어 SDK:

* SDK 버전 6.14.0 이상

2. 이 매개변수는 모든 포스트백과 함께 전송되며 각 유저를 식별할 수 있게 합니다. 이를 수행하려면 귀사의 앱 코드에 다음 문자열을 삽입해야 합니다.

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```


**<span id="setting-up-kahuna"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. 1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스**를 선택합니다.  
      **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.**
   2. 파트너를 검색하고 선택합니다.
   3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
   4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.   
      **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**

아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

설정 창에서는 연동 탭만 활용합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

이곳을 **처음 방문**하면 아래를 토글해야 합니다. ***파트너 활성화*** 버튼을 **켜서** 연동 탭의 파라미터 설정을 활성화합니다. 파트너와 함께 작업하는 동안에는 토글이 **켜져 있어야** 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

### 일반 설정

아직 이렇게 하지 않은 경우에는 연동을 계속하거나 아래 단계를 수행하여 Amplitude에서 키를 가져와야 합니다.


<span id="obtaining-the-kahuna-secret-key"></span>1.

2.

3.

4.

* **저장**을 클릭합니다.

### 기본 포스트백

앱스플라이어는 Braze 사용자 인스톨에 자동 포스트백을 발송할 수 있습니다. 이 섹션을 사용하여 이러한 포스트백 전송을 정의합니다.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

앱을 다운로드한 모든 사용자에 대해 Braze로 포스트백을 발송하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**를 선택하십시오.

**저장**을 클릭하세요.

설정을 저장하면, 앱스플라이어는 모든 오가닉 및 논오가닉 인스톨에 대해 다음 데이터를 Braze로 보냅니다:

* Kahuna Dev\_ID
* 미디어 소스
* 국가 코드
* OS 버전

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



<span id="view-user-attribution-data-in-kahuna"></span>1.

2.

3.

4.

5.

6.

7.

24,033.07 기기에 앱을 설치합니다.

9.

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=%EC%A4%91%EC%9A%94 h_01H9FKAF22W59PMYJRFW8HKBQ7=%EC%A4%91%EC%9A%94 h_01H9FKAF222ES9240V0THQQ5X0=setting-up-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FKAF22EFF1F8D2QR1F38PV=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FKAF221EXQYBJGS8GFRF4S=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FKAF22XMJW7A89MBD0J276=obtaining-the-kahuna-secret-key default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKAF2258JVR3XS6P7TT8H3=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab testing-with-sandbox=view-user-attribution-data-in-kahuna h_01H9FKAF22A5910NXRFDGC1JTG=view-user-attribution-data-in-kahuna h_01H9FKAF22KW2J6H2B6F9AMDP9=view-user-attribution-data-in-kahuna" />
