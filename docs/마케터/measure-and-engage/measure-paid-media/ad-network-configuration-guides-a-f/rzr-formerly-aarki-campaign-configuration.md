---
title: Awin 캠페인 구성
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-10-14T10:31:19Z'
  id: 360000423105
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/360000423105
---
> 한눈에 보기:  Pinterest는 클릭 기반 및 뷰-쓰루 모바일 어트리뷰션을 모두 제공합니다. 또한 Pinterest는 앱스플라이어로 기록할 수 있는 클릭 기반 리타겟팅도 제공합니다.

<Image alt="Aarki-logo.png" src="https://files.readme.io/7771a303a92fa22e0fc216038a7a367b3e249daa354593a81f4776f97b59afc6-51912636702865.png" width="207px" />


**<span id="setting-up-rzr"></span><span id="setting-up-aarki"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고: 파트너와 협력하는 동안 토글은 반드시 켜져**(활성화)/strong> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

연동, 어트리뷰션 링크, 비용, 권한이라는 4개의 활성 탭이 있습니다. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

파트너 설정 창 헤더에 대한 자세한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수** 항목입니다
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partner" />

### 파트너 활성화

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>**첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다. 파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">여기</Anchor>를 클릭하십시오.

<div id="note" />

> 📘 **참고사항**
>
> LINE은 모든 인스톨 네트워크로서 오가닉을 포함한 모든 소스에서 앱의 모든 신규 인스톨에 대한 포스트백을 수신하는 것을 선호합니다.

<div id="general-settings" />

### 일반 설정

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**파트너 ID**

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>뷰-쓰루 어트리뷰션 활성화**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

<div id="default-postbacks" />

### 기본 포스트백

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>사용자 설치 및 리인게이지먼트 이후 RTB House에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>아이언소스에 어트리뷰트된 사용자에게만 발생하는 이벤트에 대해 **이 파트너에 기여한 이벤트만** 선택합니다. 전체 사용자 기반을 아이언소스에 리포트할 수 있도록 하려면 파트너 또는 오가닉에 어트리뷰트되는 이벤트를 선택합니다.

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 트위터와 매핑합니다.

**인앱 이벤트 포스트백을 구성하려면:**

1. **인앱 이벤트 포스트백**을 켭니다.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.  

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션되었을 때만 포스트백을 전송합니다.</li><li>**오가닉 미디어 소스를 포함한 모든 미디어 소스**: 모든 파트너와 오가닉 이벤트에 어트리뷰션된 이벤트에 대해 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값이 없는 상태에서 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값이 있는 경우 이를 **포함한** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] **조건 추가**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
4. **연동 저장**을 클릭하세요.
5. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#integration-tab">연동 단계</Anchor>를 반복합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>앱스플라이어는 생성된 파트너 어트리뷰션 링크를 저장하지 않음을 주의하십시오.

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>이 탭은 여러 섹션으로 나눠집니다.

<div id="01ECJ9TJKGEPHEXZ60NAN9JPWG" />

<div id="attribution-link-parameters" />

### 어트리뷰션 링크 파라미터

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>이 섹션에서는 어트리뷰션 링크에 추가하고 싶은 파라미터를 선택합니다.

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>여기서 파라미터를 어트리뷰션 링크에 추가하면, 나중에 심층 분석을 수행할 수 있습니다. 이미 정의된 어트리뷰션 링크 파라미터를 여기에서 새 값을 추가하여 편집할 수 있습니다.

* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**<span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span><span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span><span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>광고 이름** - 미디어소스의 특정 캠페인에서 특정 광고 세트의 다양한 광고 소재를 비교하기 위해 광고의 이름을 설정합니다. **어트리뷰션 링크 파라미터: af\_ad**
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**사이트 ID** 및 **하위 사이트 ID** - 설치를 특정 퍼블리셔로 어트리뷰션 설정하려면 사이트 ID 파라미터를 설정합니다.
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**보조 파라미터** - 유용한 값을 삽입하기 위해 5개의 보조 파라미터 중 하나를 사용합니다.

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>다른 파라미터를 새 파라미터 상자에 입력하기만 하면, 어트리뷰션 링크에 추가할 수 있습니다. 더 많은 정보는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters"><span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>앱스플라이어 어트리뷰션 링크 구조와 파라미터</Anchor>에서 참조하십시오.

<div id="retargeting-settings" />

### 리타겟팅 설정

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>설정이 활성화되면, <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">&<span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>is\_retargeting=true</Anchor>가 클릭 기록 링크에 추가되며, 앱스플라이어는 링크를, 유저 유입이 아닌, 리타겟팅 어트리뷰션 링크로 인식합니다.

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>다음 설정은 리타겟팅이 활성화 되었을 때 표시됩니다.

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1. 원링크

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>다음의 경우에는 ***일반 어트리뷰션 링크*** 옵션을 선택합니다.

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>URL을 통해 딥링킹할 필요가 없는 경우, 또는
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>딥링킹 시 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>URI 스킴</Anchor>만 사용하는 경우

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>다음의 경우에는 ***원링크를 사용*** 합니다.

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>안드로이드 및 iOS 앱 모두에 하나의 링크 사용
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>유니버설 또는 앱 링크를 사용한 딥링킹

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>원링크를 선택하면 앱에 특정한 클릭 기록 링크가 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>원링크 URL</Anchor>로 변경됩니다.

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. 딥링크 URL

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>링크가 사용자를 앱 내부의 특정 액티비티로 딥링킹하려는 경우, 이 필드를 사용합니다. **<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">어트리뷰션 링크 파라미터:</Anchor> af\_dp더 자세한 정보는 앱스플라이어의 딥링킹 솔루션 가이드에서 확인할 수 있습니다.**

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3. 리인게이지먼트 기간

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>리인게이지먼트 이후에 발생하는 인앱 이벤트들이 리타겟팅 미디어 소스로 어트리뷰션 되는 기간을 설정합니다. 값은 일(1&#126;90), 시간(최대 23시간) 또는 수명 단위로 설정할 수 있습니다.

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>**어트리뷰션 링크 파라미터:** af\_reengagement\_window

<div id="click-through-attribution" />

### 클릭-쓰루 어트리뷰션

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>**클릭에서 인스톨까지의 최대 시간**을 이 슬라이더에서 설정할 수 있습니다. 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 트위터로 어트리뷰션됩니다.

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span>**어트리뷰션 링크 파라미터:** af\_click\_lookback

<span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span><Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows"><span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>클릭 룩백 윈도우 관련 상세 내용은 여기</Anchor>를 참조하십시오.

<div id="click-attribution-link" />

### 클릭 어트리뷰션 링크

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>이것은 설정해둔 모든 설정 정보를 포함하는 어트리뷰션 링크입니다.

<div id="view-through-attribution-lookback-window" />

### 뷰-쓰루 어트리뷰션 룩백 윈도우

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>이 슬라이더는 **노출에서 인스톨까지의 최대 시간**을 설정합니다. 해당 인스톨에 연관된 다른 광고 클릭이 없다면, 광고 노출 이후에 이 기여 기간 내에 일어난 인스톨(앱 최초 실행)만 X Ads로 어트리뷰션됩니다.

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>이 값을 1-23시간 또는 1-7일로 사용자 정의할 수 있습니다.

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**어트리뷰션 링크 변수:** af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>여기에서 뷰-쓰루 어트리뷰션</Anchor> 항목을 참조하십시오.

<div id="impressions-attribution-link" />

### 노출 어트리뷰션 링크

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>노출 어트리뷰션 링크는 다른 룩백 윈도우를 제외하고 클릭 기록 링크와 유사한 어트리뷰션 데이터를 포함합니다. 일반적으로 1초 이상 광고가 노출되면 활성화되도록 파트너에게 발송합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요. 주의: 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.

**비용 API를 활성화하는 방법**:

* 다음 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">연동 지침을 따르십시오</Anchor>.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 애드 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

<div id="warning" />

#### 경고

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>일단 Snap 비용을 설정했으면, 실행 중인 캠페인, 광고셋, 단일 광고의 이름을 변경하면 안됩니다. 변경 시에는 비용 데이터에 심각한 불일치나 누락이 발생할 수 있습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

<span id="01ECJ9TJKQNQBY77FTTFRZ0PGS"></span>광고 수익 데이터는 Reddit에서 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>이 탭에서는 X Ads에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. X Ads에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 X Ads에 제어 권한을 부여할 수 있습니다.

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

<div id="ad-network-permissions" />

### 애드 네트워크 권한

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>연동 탭 설정 허용*** - 파트너가 연동 탭을 설정할 수 있도록 허용(인앱 이벤트 포스트백 제외)
* <span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***인앱 이벤트 포스트백 설정 허용*** - 파트너가 연동 탭에서 자사와 인앱 이벤트 포스트백을 매핑할 수 있도록 허용
* <span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***리텐션 리포트 액세스 허용*** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***종합 로열 유저 데이터 접근 허용*** - 파트너 자사만의 로열 유저에만 해당
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>***연동 인앱이벤트 데이터 액세스 허용:*** 파트너가 유입시킨 유저의 인앱이벤트 데이터만 해당
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>***종합 수익 데이터 접근 허용*:** 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Protect360 대시보드 접근 허용*** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

<div id="01ECJ9TJKRMD549KXA59E682CH" />

<div id="agency-permissions" />

### 에이전시 권한

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>이러한 토글을 사용하여 앱에 대한 설정 권한을 에이전시에 부여합니다.

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>기본 토글*** - 에이전시 권한 옵션을 표시하려면 ON으로 설정
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span>**인앱이벤트 포스트백 설정 허용** - 에이전시가 연동 탭에서 자사와 인앱이벤트 포스트백을 매핑할 수 있도록 허용
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>통합 오가닉 데이터에 액세스 허용
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span>**리텐션 리포트에 액세스 허용** - 해당 에이전시의 고유 리텐션 데이터에만 해당

<span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">에이전시 권한 부여</Anchor>에서 확인하세요.

</Accordion>

<div data-zendesk-anchors="h_01HJR5M5C0P759S4X5SSJCY501=setting-up-aarki 01ECJ9SX6M89JYPTV72JMWYVFP=%ED%8C%81 h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01ECJ9TJKE15MJE7WS26VP52A0=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01J4KWRE6ECKEWEG4WP10N3BF7=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01ECJ9TJKFGQQVWA7SA3PRS690=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01ECJ9TJKF7G9KMGMGMAD414ZF=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 01ECJ9TJKFWH38NKYPDEZR4FRV=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01ECJ9TJKFD91X9DQXB8PV3840=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01ECJ9TJKGTPN4NF8CC66XBRRS=01ECJ9TJKGZP0D1TYCB5R8XJ80 01ECJ9TJKGSVH0XGW2R8HRDA4T=01ECJ9TJKGZP0D1TYCB5R8XJ80 retargeting-settings=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 01ECJ9TJKGJF1FS642MEM6WX4A=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%84%A4%EC%A0%95 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01ECJ9TJKHWMXAZYWNMVPDS8NY=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 click-attribution-link=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC 01ECJ9TJKJ0EQE45TB9S0WS2ZB=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 01ECJ9TJKJ72AN26F2FQ8VVKQ4=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 impressions-attribution-link=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC 01ECJ9TJKJZV9PADNEETA6GFRZ=%EB%85%B8%EC%B6%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab warning=%EA%B2%BD%EA%B3%A0 01ECJ9TJKQ8A7BFZR3MJ5H35CA=%EA%B2%BD%EA%B3%A0 h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C 01ECJ9TJKQ9E3A5863Z3TRVAWZ=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C agency-permissions=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C 01ECJ9TJKRMD549KXA59E682CH=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C" />
