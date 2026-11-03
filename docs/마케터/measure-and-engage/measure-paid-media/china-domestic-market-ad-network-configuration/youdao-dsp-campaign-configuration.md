---
title: Amazon DSP 캠페인 설정
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - youdao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-30T09:13:02Z'
  edited_at: '2026-10-14T10:38:07Z'
  id: 360002133558
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/360002133558
---
> **한눈에 보기:**


<span id="setting-up-youdao-dsp"></span>설정은 **활성 연동** 페이지에서 수행되지만 신규 파트너를 찾으려면 먼저 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations">마켓플레이스</Anchor>로 이동해야 합니다.

> 📘 **참고사항**
>
> 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설해야 합니다.

**연동 활성화 방법:**

1. 앱스플라이어의 측면 메뉴에서 협업> **파트너 마켓플레이스**를 선택하세요.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하세요.
4. 연동 설정 페이지로 이동합니다.
5. **연동** 탭에서 **파트터 활성화**를 켭니다.

RTB House의 구성 창에는 연동, 어트리뷰션 링크, 권한이라는 3개의 활성 탭이 있습니다. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

### 파트너 활성화

이곳을 **처음 방문**하면 아래를 토글해야 합니다. ***파트너 활성화*** 버튼을 **켜서** 연동 탭의 파라미터 설정을 활성화합니다. 파트너와 함께 작업하는 동안에는 토글이 **켜져 있어야** 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

### 기본 포스트백

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="583px" />

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

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="511px" />

다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 **앱스플라이어 어트리뷰션 링크 구조와 파라미터**에서 참조하십시오.

### 클릭 조회(click-through) 어트리뷰션

**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 트위터로 어트리뷰션됩니다.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### 어트리뷰션 링크

이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 연동 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 RTB House에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. RTB House에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 RTB House에 제어 권한을 부여할 수 있습니다.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### 광고 네트워크 권한

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

* ***연동 탭 설정 허용*** - 파트너가 연동 탭을 설정할 수 있도록 허용(인앱 이벤트 포스트백 제외)
* ***인앱 이벤트 포스트백 설정 허용*** - 파트너가 연동 탭에서 자사와 인앱 이벤트 포스트백을 매핑할 수 있도록 허용
* ***리텐션 리포트 액세스 허용*** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* ***Protect360 대시보드 접근 허용*** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

<div data-zendesk-anchors="h_01HKW6ZN60XK9DSCEVQ216P1G9=setting-up-youdao-dsp h_01HKW6ZN60DM5PFX946S76DVGW=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKW6ZN60J946AYXMKJPSW91T=%ED%8C%81 h_01HKW6ZN60TAMV09SSD8JM29GS=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW6ZN60PGGR7RDWKP5S2HJ9=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW6ZN61B4KY1BEA76MYX4BC=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW6ZN61WPTBRKNTG3BXHYRP=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKW6ZN6172ASA82J51CM13NW=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%A1%B0%ED%9A%8Cclick-through-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HKW6ZN614J1A71A9B38QRN7E=%ED%81%B4%EB%A6%AD-%EC%A1%B0%ED%9A%8Cclick-through-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 attribution-link=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6ZN61EZP9ES6GK09C68DH=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6ZN61AWQFR8VD489ZEC6J=cost-tab h_01HKW6ZN68J89ZY3QCJZARYSTP=ad-revenue-tab h_01HKW6ZN68EQS2MB9MK7TV7TB1=permissions-tab ad-network-permissions=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HKW6ZN68HZECRSMR3GPTAG4R=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C" />
