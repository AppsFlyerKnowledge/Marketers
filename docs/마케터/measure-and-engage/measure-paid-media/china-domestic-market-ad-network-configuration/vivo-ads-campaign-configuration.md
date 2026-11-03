---
title: Unity Ads 캠페인 구성
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-10-14T10:38:35Z'
  id: 360002358897
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/360002358897
---
>


<span id="setting-up-vivo-ads"></span>설정은 **활성 연동** 페이지에서 수행되지만 신규 파트너를 찾으려면 먼저 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations">마켓플레이스</Anchor>로 이동해야 합니다.

> 📘 **참고사항**
>
> 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설해야 합니다.

**연동 활성화 방법:**

1. 앱스플라이어의 측면 메뉴에서 협업> **파트너 마켓플레이스**를 선택하세요.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하세요.
4. 연동 설정 페이지로 이동합니다.
5. **연동** 탭에서 **파트터 활성화**를 켭니다.

Pinterest의 구성 창에는 연동 및 어트리뷰션 링크. 탭 설정에 대한 자세한 설명은 아래 항목을 참조하십시오.

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

### 뷰-쓰루 어트리뷰션 활성화

뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

### 기본 포스트백

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="456px" />

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

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="479px" />

다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 **앱스플라이어 어트리뷰션 링크 구조와 파라미터**에서 참조하십시오.

### 클릭-쓰루 어트리뷰션

**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 X Ads로 어트리뷰션됩니다.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

![viewthrough_en-us.png](https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png)

### 어트리뷰션 링크

이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

### 뷰-쓰루 어트리뷰션 룩백 윈도우

이 슬라이더는 **노출에서 인스톨까지의 최대 시간**을 설정합니다. 해당 인스톨에 연관된 다른 광고 클릭이 없다면, 광고 노출 이후에 이 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 X Ads로 어트리뷰션됩니다.

이 값을 1-23시간 또는 1-7일로 사용자 정의할 수 있습니다.

**어트리뷰션 링크 변수:** af\_viewthrough\_lookback

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">여기에서 뷰-쓰루 어트리뷰션</Anchor> 항목을 참조하십시오.

### 노출 어트리뷰션 링크

노출 어트리뷰션 링크는 다른 룩백 윈도우를 제외하고 클릭 기록 링크와 유사한 어트리뷰션 데이터를 포함합니다. 일반적으로 1초 이상 광고가 노출되면 활성화되도록 파트너에게 발송합니다.

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

</Accordion>

<div data-zendesk-anchors="h_01HKW6Y9CJED5RV97WWSYQNBDG=setting-up-vivo-ads h_01HKW6Y9CJ747R6F84H6XEVHRC=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKW6Y9CJXAR3YQ1RM3VTE0CF=%ED%8C%81 h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW6Y9CJC0EWH84B7GW29VJM=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 enable-viewthrough-attribution=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW6Y9CJDY5XHWXN3CK0YGK8=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKW6Y9CKSHBWNBH0RY3X3RR3=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HKW6Y9CKE86Z1Z4QZH0M665T=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 attribution-link=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6Y9CKNB685ZYXB8RM1P41=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HKW6Y9CKV48NRWSXD0ZKY3M0=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 impressions-attribution-link=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6Y9CKV6XY1BCD9XX42XZ7=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
