---
title: Unity Ads 캠페인 구성
metadata:
  keywords:
    - Wechat Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-10-14T10:36:09Z'
  id: 115003044106
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/115003044106
---
> **한눈에 보기:**

## 소개


2. * 인스톨
   * 회원가입
   * Purchase
   * 장바구니 추가

![wechat-configuration.png](https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png)

![wechat-keys.png](https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png)



<span id="setting-up-wechat-campaign-as-an-agency"></span>설정은 **활성 연동** 페이지에서 수행되지만 신규 파트너를 찾으려면 먼저 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations">마켓플레이스</Anchor>로 이동해야 합니다.

> 📘 **참고사항**
>
> 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설해야 합니다.

**연동 활성화 방법:**

1. 앱스플라이어의 측면 메뉴에서 협업> **파트너 마켓플레이스**를 선택하세요.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다.  
   **참고:** 파트너와 함께 작업하는 동안에는 토글이 켜져 있어야(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화</Anchor>) 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

이곳을 **처음 방문**하면 아래를 토글해야 합니다. ***파트너 활성화*** 버튼을 **켜서** 연동 탭의 파라미터 설정을 활성화합니다. 파트너와 함께 작업하는 동안에는 토글이 **켜져 있어야** 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

> 📘 **참고사항**
>
> LINE은 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다.

### 일반 설정

**파트너 ID**

<Image alt="wechat-integration-general-settings.png" src="https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png" width="390px" />

### 기본 포스트백

이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

![wechat-default-postbacks.png](https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png)

아이언소스에 어트리뷰트된 사용자에게만 발생하는 이벤트에 대해 **이 파트너에 기여한 이벤트만** 선택합니다. **전체 사용자 기반을 아이언소스에 리포트할 수 있도록 하려면 파트너 또는 오가닉에 어트리뷰트되는 이벤트를 선택합니다.**

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 트위터와 매핑합니다.

![wechat_in_app_event_postbacks.png](https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png)

4. 인앱 이벤트 포스트백을 ON으로 토글합니다.
5. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**
6. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
7. 다음 파라미터를 완성합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트로부터 앱스플라이어가 수신한 이벤트 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** | Reddit 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다.  <br />해당하는 이벤트 ID를 트위터에서 가져와서 텍스트 필드에 설정합니다. |
| **수익 전송** | **체크하지 않은 경우** - 앱스플라이어는 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다. 단, **af\_revenue** 파라미터에 포함된 수익 값은 제외합니다.  <br />**선택한 경우** - 앱스플라이어가 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

앱스플라이어는 생성된 파트너 어트리뷰션 링크를 저장하지 않음을 주의하십시오.

이 탭은 여러 섹션으로 나눠집니다.

### 어트리뷰션 링크 파라미터

이 섹션에서는 어트리뷰션 링크에 추가하고 싶은 파라미터를 선택합니다.

여기서 파라미터를 어트리뷰션 링크에 추가하면, 나중에 심층 분석을 수행할 수 있습니다. 이미 정의된 어트리뷰션 링크 파라미터를 여기에서 새 값을 추가하여 편집할 수 있습니다.

* **어트리뷰션 링크 파라미터:** c
* **어트리뷰션 링크 파라미터:** af\_adset
* **광고 이름** - 온드 미디어소스의 특정 캠페인에서 특정 광고 세트의 다양한 창작물을 비교하기 위해 광고 세트 이름을 설정합니다.  
  **어트리뷰션 링크 파라미터:** ad\_ad
* **사이트 ID** 및 **하위 사이트 ID** - 설치를 특정 퍼블리셔로 어트리뷰션 설정하려면 사이트 ID 파라미터를 설정합니다. 여러 퍼블리셔가 존재하는 경우 사이트 ID 제한을 초과하지 않도록 사용된 사이트 ID 수를 제한하고 하위 사이트 ID 파라미터를 사용하는 것이 좋습니다.  
  **어트리뷰션 링크 파라미터:** af\_siteid 및 af\_sub\_siteid
* **보조 파라미터** - 유용한 값을 삽입하기 위해 5개의 보조 파라미터 중 하나를 사용합니다. 이러한 파라미터는 분석되어 로데이터 리포트에 표시됩니다. 그래서 데이터 집계나 필터링에 매우 편리합니다.  
  **어트리뷰션 링크 파라미터:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 **앱스플라이어 어트리뷰션 링크 구조와 파라미터**에서 참조하십시오.

### 클릭-쓰루 어트리뷰션

**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 트위터로 어트리뷰션됩니다.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

### 클릭 어트리뷰션 링크

이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

트위터에 대해서는 광고 수익 연동을 할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

</Accordion>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HKW6Z36NGCWC0R6EQX49S34J=%EC%86%8C%EA%B0%9C setting-up-your-campaign-on-wechat=%EC%86%8C%EA%B0%9C h_01HKW6Z36NTSGCDQM553YMHHDH=%EC%86%8C%EA%B0%9C setting-up-wechat-on-appsflyer=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N8S8KSBNMR8A54RRN=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36N3JSYEWJZH74M5WWJ=setting-up-wechat-campaign-as-an-agency h_01HKW6Z36NPKQGH2E3ZZJFVTHH=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKW6Z36NHHDW13B7K24D18H6=%ED%8C%81 h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW6Z36P0EQF829NW3GDXKEN=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW6Z36P806MHV6N3D1N9HW3=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HKW6Z36P51EG4BW7WA3JGSKN=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW6Z36P3D4EPKC6ZZK94YVF=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HKW6Z36PA90WEJMFH7BZMD72=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKW6Z36P73H79MVFXQ29K2M6=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HKW6Z36P95C7CT1J6YS5CQN8=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 click-attribution-link=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6Z36PEAPM8RAKB0RM9RES=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
