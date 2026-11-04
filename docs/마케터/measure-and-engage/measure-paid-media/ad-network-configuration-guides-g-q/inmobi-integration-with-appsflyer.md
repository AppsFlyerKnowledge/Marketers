---
title: Steam과 앱스플라이어 연동
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - InMobi
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
  created_at: '2014-11-20T10:29:22Z'
  edited_at: '2026-10-14T10:34:33Z'
  id: 207033896
  locale: ko
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ko/articles/207033896
---
> **한눈에 보기:** 아이언소스는 클릭 기반 모바일 어트리뷰션 외에도 비용, 광고 수익, 리타게팅 및 뷰-쓰루 어트리뷰션을 제공하며, 앱스플라이어로 기록할 수 있습니다.

<Image alt="inmobi_icon.png" src="https://files.readme.io/cbe0e88492041fc8e1781b397b67a3c8c3a09591974f2cf4fa145a18ca9e6a8d-10602685724817.png" width="128px" />


**<span id="setting-up-inmobi"></span><span id="setting-up-glispa"></span>전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집하려면:** 앱스플라이어의 사이드 메뉴에서 **협업**> **활성화된 연동**을 선택합니다.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 협력하는 동안 토글은 반드시 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

Pinterest의 구성 창에는 연동, 어트리뷰션 링크, 비용, 권한이라는 4개의 활성 탭이 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="tip" />

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partners" />

### 파트너 활성화

**첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="note" />

> 📘 **참고**
>
> LINE은 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 **모든 파트너에 어트리뷰션된 이벤트**를 선택하여 모든 인스톨 포스트백을 LINE으로 전송합니다.

<div id="general-settings" />

### 일반 설정

**gpm\_ID**

![Inmobi_msc_new_3.png](https://files.readme.io/9c2efaed833211582a33b3a2bbd7d07336bc78d6e2d4e3a7645b5ca14be2fd73-360001865845.png)

**뷰-쓰루 어트리뷰션 활성화**

뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

<div id="default-postbacks" />

### 기본 포스트백

사용자 설치 및 리인게이지먼트 이후 아이언소스에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

아이언소스에 어트리뷰트된 사용자에게만 발생하는 이벤트에 대해 **이 파트너에 기여한 이벤트만** 선택합니다.  
전체 사용자 기반을 아이언소스에 리포트할 수 있도록 하려면 **파트너 또는 오가닉에 어트리뷰트되는 이벤트**를 선택합니다.

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 트위터와 매핑합니다.

2. 인앱 이벤트 포스트백을 ON으로 토글합니다.
3. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**.
4. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
5. 다음 파라미터를 입력하세요:

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** | Reddit 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다.  <br />해당하는 이벤트 ID를 트위터에서 가져와서 텍스트 필드에 설정합니다. |
| **수익 전송** | **체크하지 않은 경우** - **af\_revenue** 파라미터에 포함된 수익 파라미터를 제외하고, 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다.  <br />**선택한 경우** - 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

앱스플라이어는 생성된 파트너 어트리뷰션 링크를 저장하지 않음을 주의하십시오.

[![](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)

이 탭은 여러 섹션으로 나눠집니다.

<div id="attribution-link-parameters" />

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

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 **앱스플라이어 어트리뷰션 링크 구조와 파라미터**에서 참조하십시오.

<div id="retargeting-settings" />

### 리타겟팅 설정

설정이 활성화되면, <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">&is\_retargeting=true</Anchor>가 클릭 기록 링크에 추가되며, 앱스플라이어는 링크를, 유저 유입이 아닌, `&is_retargeting=true`리타겟팅&is\_retargeting=true 어트리뷰션 링크로 인식합니다. 리타겟팅은 현재 클릭-쓰루에서만 지원되고, 뷰-쓰루 어트리뷰션에서는 지원되지 않습니다.  
**어트리뷰션 링크 파라미터:** is\_retargeting

다음 설정은 리타겟팅이 활성화 되었을 때 표시됩니다.

![msc_new_7.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

1. 원링크

다음의 경우에는 **일반 어트리뷰션 링크** 옵션을 선택합니다.

* URL을 통해 딥링킹할 필요가 없는 경우, 또는
* 딥링킹 시 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI 스킴</Anchor>만 사용하는 경우

다음의 경우에는 **원링크를 사용** 합니다.

* 안드로이드 및 iOS 앱 모두에 하나의 링크 사용
* 유니버설 또는 앱 링크를 사용한 딥링킹

원링크를 선택하면 앱에 특정한 클릭 기록 링크가 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크 URL</Anchor>로 변경됩니다.

2. 딥링크 URL

링크가 사용자를 앱 내부의 특정 액티비티로 딥링킹하려는 경우, 이 필드를 사용합니다.  
**어트리뷰션 링크 파라미터:** af\_dp

3. 리인게이지먼트 기간

리인게이지먼트 이후에 발생하는 인앱 이벤트들이 리타겟팅 미디어 소스로 어트리뷰션 되는 기간을 설정합니다. 값은 일(1&#126;90), 시간(최대 23시간) 또는 수명 단위로 설정할 수 있습니다.

**어트리뷰션 링크 파라미터:** af\_reengagement\_window

<div id="click-through-attribution" />

### 클릭-쓰루 어트리뷰션

**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 트위터로 어트리뷰션됩니다.

**어트리뷰션 링크 파라미터:** af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

[![](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)

<div id="click-attribution-link" />

### 클릭 어트리뷰션 링크

이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

<div id="view-through-attribution-lookback-window" />

### 뷰-쓰루 어트리뷰션 룩백 윈도우

이 슬라이더는 **노출에서 인스톨까지의 최대 시간**을 설정합니다. 해당 인스톨에 연관된 다른 광고 클릭이 없다면, 광고 노출 이후에 이 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 X Ads로 어트리뷰션됩니다.

이 값을 1-23시간 또는 1-7일로 사용자 정의할 수 있습니다.

**어트리뷰션 링크 변수:** af\_viewthrough\_lookback

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">여기에서 뷰-쓰루 어트리뷰션</Anchor> 항목을 참조하십시오.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### 노출 어트리뷰션 링크

노출 어트리뷰션 링크는 다른 룩백 윈도우를 제외하고 클릭 기록 링크와 유사한 어트리뷰션 데이터를 포함합니다. 일반적으로 1초 이상 광고가 노출되면 활성화되도록 파트너에게 발송합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요. 주의: 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.

**비용 API를 활성화하는 방법**:

* 다음 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">연동 지침을 따르십시오</Anchor>.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 애드 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너는 광고 수익 데이터를 지원하지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Awin이 데이터에 액세스하고 다양한 작업을 수행할 수 있도록 부여할 권한을 선택합니다.

<div id="note-1" />

> 📘 **참고**
>
> 권한 토글이 켜진 상태에서 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되면 권한이 계속 부여됩니다.

</Accordion>

<div data-zendesk-anchors="h_01HKA0TGE08PJDBQHFER5ZZ785=setting-up-glispa h_01HHVXZ7FSGDRCECE93ZF69VMS=%ED%8C%81 h_01HHVXZ7FSZ7W855TSN5TSPD0G=integration-tab activate-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HHVXZ7FSJ0PS5KQ0YZHVSFKF=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HHVXZ7FSM5PT4VJRGVWDBRDK=%EC%B0%B8%EA%B3%A0 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HHVXZ7FSDF06G1848W0YH8W6=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HHVXZ7FS0DEZPEEH7D68SH0B=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HHVXZ7FS47Y4T3KDR732WCE6=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HHVXZ7FSX2TJC13GT3TGR7ZK=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HHVXZ7FSCE4NP1XC0ZJ81858=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 retargeting-settings=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 h_01HHVXZ7FSAVKE25TSS98RMK8V=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HHVXZ7FTE8EZYBA4HS45MFAR=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 click-attribution-link=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HHVXZ7FTP962PWNMEEDB31H5=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HHVXZ7FT8HVSEXB5YWABPXNA=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 impressions-attribution-link=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HHVXZ7FT7V6M8VC69EYRK700=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HHVXZ7FT9W1RN6P06JE53S7X=cost-tab h_01HHVXZ7FTGSKZCB57RT9GPYC9=ad-revenue-tab h_01HHVY4WHSM3B33KYACR9DJ5ZW=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%EC%B0%B8%EA%B3%A0-1" />
