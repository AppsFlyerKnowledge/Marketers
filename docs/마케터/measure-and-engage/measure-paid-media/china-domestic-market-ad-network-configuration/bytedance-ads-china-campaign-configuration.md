---
title: ByteDance Ads China—캠페인 구성
metadata:
  keywords:
    - bytedance
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
  created_at: '2017-06-18T07:05:42Z'
  edited_at: '2026-10-14T10:27:12Z'
  id: 115003019403
  locale: ko
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ko/articles/115003019403
---
> **한눈에 보기:** 앱스플라이어 통합 파트너인 ByteDance Ads China(Ocean Engine)는 여러 머신러닝 지원 콘텐츠 플랫폼을 운영하는 인터넷 기술 회사입니다.

> 📘 **참고**
>
> ByteDance Ads China를 통해 안드로이드 앱을 홍보하려면 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">앱스플라이어 SDK 연동 - 안드로이드</Anchor>의 지침에 따라 OAID를 앱스플라이어 SDK로 보내야 합니다. Google Play 서비스는 중국에서 차단되었으며 OAID는 광고 어트리뷰션에 가장 많이 사용되는 안드로이드 디바이스 ID입니다.

클릭 기반 모바일 어트리뷰션 외에도 ByteDance Ads China는 귀사가 앱스플라이어로 기록할 수 있는 뷰-쓰루 어트리뷰션도 제공합니다.

ByteDance Ads China로 캠페인을 구성하려면 아래 단계를 따르세요.

## ByteDance Ads China 설정

**전제 조건:**  연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.**
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다.  
   **참고:** 파트너와 함께 작업하는 동안에는 토글이 켜져 있어야(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화</Anchor>) 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

팁

> 👍 **Tip**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수**입니다.
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 ***파트너 활성화*** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

일반 설정

**뷰-쓰루 어트리뷰션 활성화**

[![](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)

ByteDance Ads China로 뷰-쓰루 인스톨을 어트리뷰션하려면 이 옵션을 **설정하세요**. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

### 기본 포스트백

앱스플라이어는 사용자 설치 및 리인게이지먼트 후 ByteDance Ads China에 자동 포스트백을 보낼 수 있습니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

![bytedance-default-postbacks.png](https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png)

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 ByteDance Ads China와 매핑할 수 있습니다.

1. 인앱 이벤트 포스트백을 켭니다.
2. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**.
3. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
4. 다음 파라미터를 완성합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이벤트 이름을 매핑하지 않고 이벤트를 그대로 보냅니다.</li></ul> |
| **유저에 대한** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다. 즉, 유저가 이 파트너에서 온 경우입니다.</li><li>**오가닉 포함 모든 매체 소스**: 파트너에게 어트리뷰트된 이벤트와 오가닉 이벤트에 대한 포스트백을 보냅니다. 즉, 해당 이벤트를 수행한 사용자는 모든 미디어 소스에서 왔습니다.</li></ul> |
| **포함** | 포스트백에서 파트너와 공유할 이벤트 데이터를 선택합니다.<ul><li>**값 없음 & 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).</li><li>**값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값(이벤트에 존재하는 경우)을 **포함한** 모든 이벤트 파라미터를 전송합니다.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기</Anchor>.  

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

### 클릭 어트리뷰션 링크

어트리뷰션 링크를 생성했으면 ByteDance Ads China 사이트에서 캠페인 설정 프로세스를 완료합니다.

**1. Ocean Engine에서 전환 추적을 만듭니다.**

Ocean Engine에 로그인([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **라이브러리** > **전환 추적**.

![OE_dashboard_1.png](https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png)

**추적 애플리케이션**을 클릭하고 **새 애플리케이션 변환**을 만듭니다.

![OE_dashboard_2.png](https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png)

**API** 메서드를 클릭합니다.

![OE_dashboard3.png](https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png)

모니터링 링크 부분에 앱스플라이어 클릭 어트리뷰션 링크 및/또는 노출 수 어트리뷰션 링크를 입력합니다.

![dashboard4.png](https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png)

**2. 웹사이트의 지침에 따라 어트리뷰션 테스트를 완료합니다**.

**3. 새로 생성된 전환으로 광고 캠페인을 만듭니다**.

**새 광고** >> **예산 및 입찰가 설정**으로 이동하고 이 앱에 대해 만든 전환을 선택합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 앱스플라이어는 v1.0 ByteDance 시스템에서 실행되는 캠페인을 제외하고는 ByteDance에 대한 광고 수준 비용 데이터를 지원하지 않습니다.

### API로 지원되는 데이터

| 지역 | 미디어 소스 | 캠페인 | 광고 세트 | 광고 | 기타 |
| --- | --- | --- | --- | --- | --- |
| Yes | - | Yes | 예 | 아니요<br /><br />(광고는 v1.0 ByteDance 캠페인에서만 지원됨) | - |

**ByteDance Ads China 비용 API 활성화 방법**:

1. 연동 파트너 비용 탭에서, ***비용 데이터 가져오기***를 활성화합니다.
2. ByteDance Ads China에 로그인합니다.
3. ***비용 저장***을 클릭합니다.
   * 절차를 성공적으로 완료했습니다. API가 활성화됩니다. 앱스플라이어는 하루 6번, 평균 4시간마다 한 번씩 파트너로부터 데이터를 수집합니다.
   * 비용 연동 탭에는 비용 연동 상태와 앱스플라이어가 해당하는 비용 데이터를 가져온 마지막 시간이 표시됩니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 섹션은 사용자에게 파트너의 광고를 표시하는 퍼블리셔에게만 해당됩니다. 퍼블리셔에 해당되는 경우는 다른 소스에서 획득한 사용자의 인게이지먼트를 측정하여 가장 수익성이 높은 소스를 찾을 수 있습니다.

**광고 수익 API 설정 방법**:

* 다음 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">연동 지침을 따르십시오</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 ByteDance Ads China에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. ByteDance Ads China에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 ByteDance Ads China에 제어 권한을 부여할 수 있습니다.

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

### 애드 네트워크 권한

* ***파트너 연동 설정 허용*** - 파트너가 연동 탭을 설정할 수 있도록 허용 (인앱 이벤트 포스트백 제외)
* ***인앱 이벤트 포스트백 설정 허용*** - 파트너가 연동 탭에서 자사와 인앱 이벤트 포스트백을 매핑할 수 있도록 허용
* ***리텐션 리포트 액세스 허용*** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* ***종합 로열 유저 데이터 접근 허용*** - 파트너 자사만의 로열 유저에만 해당
* ***통합 인앱 이벤트 데이터 액세스 허용** -* 파트너가 유입시킨 유저의 인앱 이벤트 데이터만 해당
* ***종합 수익 테이터 접근 허용*** - 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* ***Protect360 대시보드 접근 허용*** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

<div data-zendesk-anchors="h_01HJR1HREQDCQDN6JZRPD356VS=%EC%B0%B8%EA%B3%A0 setting-up-bytedance-ads-china=bytedance-ads-china-%EC%84%A4%EC%A0%95 h_01HJR1HREQ6YAW1WPX2BTZS2R7=bytedance-ads-china-%EC%84%A4%EC%A0%95 h_01HJR1HRERBBZFKBHH78BK6QW2=integration-tab activate-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HJR1HRER22XX94R1WEQK60GJ=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HJR1HRERMXHAAGXEFJS4ZS8C=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HJR1HRERF2Y205KP0J8HZFR3=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HJR1HRER391J6PD9Q0M1MW3F=attribution-link-tab click-attribution-link=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HJR1HRERCHNHQGX3X1E1ARDK=%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01HJR1HRER1G4K3PQG1Z7M6CCX=cost-tab api-dimensions-supported=api%EB%A1%9C-%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HJR1HRES86BJM4ABQ0B414F1=api%EB%A1%9C-%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HJR1HRES470MKXS1S08X202D=ad-revenue-tab h_01HJR1HRESJ7KNFZ9TDHZKESJ7=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HJR1HRESZCC6YV9D40YYSYX0=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C" />
