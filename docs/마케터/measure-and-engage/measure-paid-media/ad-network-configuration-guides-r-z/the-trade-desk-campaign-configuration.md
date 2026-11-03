---
title: 트레이드 데스크 캠페인 구성
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2026-10-14T10:38:08Z'
  id: 360000894849
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/360000894849
---
> **한눈에 보기:** 요약: 앱스플라이어 애드 네트워크 연동 파트너인 트레이드 데스크(The Trade Desk)는 향상된 모바일 광고 솔루션을 사용하여 크로스 디바이스 사용자의 요구를 충족하기 위해 전략적이고 확장 가능하며 스마트한 캠페인을 개발합니다. 트레이드 데스크는 클릭 기반 모바일 어트리뷰션, 뷰-쓰루 모바일 어트리뷰션 및 클릭 기반 리타게팅을 제공하며, 이 모든 것은 앱스플라이어를 통해 기록할 수 있습니다.

## 트레이드 데스크(TTD) 설정

다음 단계에 따라 앱스플라이어 캠페인 측정을 활성화하십시오.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="1단계: 1단계: TTD에서 전환 이벤트 정의">

1. TTD 광고주 페이지의 왼쪽 메뉴에서 **데이터**를 클릭합니다.
2. 상단 메뉴에서 **앱 데이터 추가**를 클릭합니다.
3. **앱 데이터 만들기** 페이지에서 다음 필드를 입력합니다.
   * 앱 이름
   * 운영 체제    
     **참고:** 참고: TTD는 Android 및 iOS 옵션에서 모두 CTV를 지원합니다.
   * **앱스플라이어**를 선택합니다.
   * 이벤트 이벤트: **이벤트 추가**를 클릭하여 전환 이벤트를 추가하고 필드를 작성합니다.
     * 이벤트 이름   
       **참고:** 참고: 이름은 앱스플라이어에서와 같이 대문자, 공백 및 기호를 포함하여 정확하게 작성되어야 합니다.
     * 이 옵션에는 어트리뷰션과 리타게팅이 모두 포함됩니다.
     * 이벤트를 더 추가하려면 **이벤트 추가**를 클릭하고 프로세스를 반복합니다.
   * **참고:**

     * 캠페인 중에는 이 선택을 변경하지 마십시오.
4. **앱 데이터 만들기**를 클릭합니다.

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="2단계: 2단계: 앱스플라이어에서 전환 이벤트 정의">

앱스플라이어가 전환 이벤트를 정의하고이벤트 포스트백을 TTD로 보낼 수 있도록 하려면 먼저 [TTD를 앱스플라이어와 연동](/docs/the-trade-desk-campaign-configuration#ttd와-앱스플라이어-연동하기)하고 다음 구성을 설정해야 합니다.

* 연동 설정(이벤트 포스트백 구성 포함)
* 어트리뷰션 링크
* 권한

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="3단계: 3단계: 앱스플라이어에서 정의된 전환 이벤트 매핑">

1. TTD 왼쪽 메뉴에서 **캠페인**을 클릭합니다.
2. **캠페인**까지 아래로 스크롤하고 목록에서 캠페인을 선택합니다.
3. **리포팅 및 어트리뷰션 편집**을 클릭합니다.
4. **전환 데이터 소스 추가**를 클릭합니다.
5. **전환 데이터 소스** 아래에서 **앱스플라이어**를 선택합니다. 앱스플라이어 이벤트는 이제 TTD 이벤트에 매핑됩니다.
6. **크로스 디바이스 개념**:
   * [1단계](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (전환 크레딧 소스)에서 TTD에 의한 변환을 선택한 경우 여기서 **Household**를 선택하여 사용 가능한 모든 채널(모바일 인앱 및 CTV 등)의 변환을 확인합니다.
   * [1단계에서](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) 앱스플라이어를 선택한 경우 여기에서 **없음**을 선택합니다.
7. **저장**을 클릭합니다.

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="4단계: 4단계: 캠페인 광고소재에 클릭 및 노출 트래커 추가">

이 단계에서는 앱스플라이어에서 생성된 클릭 및 노출 트래커를 TTD의 각 광고소재에 추가합니다.

1. TTD 왼쪽 메뉴의 **캠페인** 에서 상단 탭의 **광고소재**를 클릭합니다.
2. 현재 캠페인과 연결된 광고소재 목록에서 광고소재를 선택합니다.
3. **추적**까지 아래로 스크롤합니다.
4. 앱스플라이어에서 [어트리뷰션 링크](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) (클릭 처리량 및 뷰-쓰루)를 복사하여 각 **1x1 픽셀 노출 추적 URL** 필드에 붙여넣습니다.
5. **변경 사항 저장**을 클릭합니다.
6. 캠페인과 연결된 각 광고소재에 대해 이 단계를 반복합니다.

</Accordion>

> 📘 **참고사항**
>
> [1단계에서](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) TTD에 의해 전환이 어트리뷰션되도록 선택한 경우 어트리뷰션 기간을 수정할 수 있습니다.
>
> 1. TTD 페이지 오른쪽의 아이콘 메뉴에서 톱니바퀴를 클릭하여 **광고주 기본 설정**을 엽니다.
> 2. **어트리뷰션 기간**까지 아래로 스크롤하고 오른쪽에 있는 편집 버튼을 클릭합니다.
> 3. **어트리뷰션 기간 관리** 페이지에서 어트리뷰션 기간을 편집합니다.
> 4. **저장**을 클릭합니다.

## TTD와 앱스플라이어 연동하기

**전제 조건:** **연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.**

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업**>**파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업** > 활성 연동을 선택합니다.**
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. 연동 탭에서 **파트너 활성화**를 켭니다.  
   **참고: 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(활성화됨).**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

연동, 어트리뷰션 링크, 권한이라는 3개의 활성 탭이 있습니다. 탭 설정에 대한 자세한 설명은 아래 항목을 참조하십시오.

파트너 구성 창 헤더에 대한 자세한 설명을 보려면 여기를 클릭하세요.

<div id="integration-tab" />

<Accordion title="연동 탭">

#### 파트너 활성화

처음 방문 시에 **파트너 활성화** 토글을 켜서 연동을 설정해야 합니다. 토글은 TTD에서 작동하는 동안 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

#### 프라이버시 강화 모드

iOS 앱의 경우 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">고급 개인 정보 보호 활성화</Anchor> 토글이 나타납니다. 이 기능을 켜면 파트너와의 사용자 식별자 공유가 제한됩니다.

#### 일반 설정

**트래커 및 광고주 ID**

트레이드 데스크는 고유한 네트워크 ID를 통해 앱스플라이어와 연결됩니다. Tracker\_ID와 광고주가 아직 없는 경우 연동을 계속하려면 트레이드 데스크에서 가져와야 합니다.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**뷰-쓰루 어트리뷰션 활성화**

**뷰-쓰루 어트리뷰션 활성화**를 켜서 트레이드 데스크에서 뷰-쓰루 인스톨을 어트리뷰트합니다. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

#### 기본 포스트백

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

사용자 설치 및 리인게이지먼트 이후 트레이드 데스크에 자동 포스트백을 보냅니다. 이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 사용자의 출처를 정의할 수 있습니다.

* **이 파트너만 해당**: 트레이드 데스크로 어트리뷰트된 사용자로부터 발생한 이벤트에만 적용됩니다.
* **오가닉을 포함한 모든 미디어소스**: 트레이드 데스크에 리포트할 수 있는 전체 사용자 기반을 가지는 미디어소스를 의미합니다.

> 📘 **참고사항**
>
> 모든 인스톨 네트워크인 트레이드 데스크는 모든 소스에서 앱의 모든 신규 설치에 대한 포스트백을 수신하는 것을 선호하며, 모든 인스톨 포스트백을 트레이드 데스크로 전송하려면 **오가닉을 포함한 모든 미디어소스**를 선택할 것을 권장했습니다.

#### 인앱 이벤트 설정

포스트백을 통해 앱스플라이어 이벤트를 TTD로 매핑합니다. 포스트백 발송이 활성화된 경우, 이는 거부된 인앱 이벤트(Protect360에 의해 차단된 이벤트나 유효성 검증 규칙을 준수하지 않는 것으로 판단된 이벤트)를 포함합니다.

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**인앱 이벤트 포스트백을 구성하려면:**

1. advertiserid 및 **Tracker\_ID**를 입력합니다.
2. **인앱 이벤트 포스트백**을 활성화합니다.
3. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성에 대해</Anchor>자세히 알아보십시오 ).
4. 가능한 경우 자동 또는 수동으로 이벤트를 전송할지 여부를 선택하십시오. 모든 이벤트를 있는 그대로 전송하기에 대해 자세히 알아보십시오.
5. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버 간 이벤트를 추가합니다.
6. 필수 파라미터를 입력합니다.
7. [선택 사항] <Image alt="" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />conditional-iae-postbacks-icon.png를 클릭하여 파트너에게 특정 인앱 이벤트를 전송하기 위한 alt조건을 설정alt합니다.  
   조건적인 인앱 이벤트 포스트백에 대해 알아보세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**! 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>앱스플라이어 이벤트에 입력한 다음 **사용자 지정 생성**을 클릭합니다. 커스텀 이벤트 매핑에 대해 더 알아보세요.</li></ul> |
| **사용자용** | 이벤트 발송 옵션을 선택합니다:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에게 귀속된 경우에만 포스트백을 발송합니다.</li><li>**오가닉을 포함한 모든 미디어소스**: 오가닉 이벤트를 포함하여 모든 파트너로 어트리뷰션된 이벤트의 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 보냅니다.</li><li>**값 및 수익**: 매출 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익이 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타게팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 제공하기 위해 어트리뷰션 링크를 생성하고 저장한 후 TTD에 보냅니다. 단일 플랫폼 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용할 수 있습니다.

#### 어트리뷰션 링크 파라미터

어트리뷰션 링크에 파라미터를 추가하면 철저한 드릴다운 분석이 가능합니다. 이미 정의된 어트리뷰션 링크 파라미터를 여기에서 새 값을 추가하여 편집할 수 있습니다. 어트리뷰션 링크를 저장할 때 이 탭에서 구성된 모든 파라미터가 저장됩니다.

어트리뷰션 링크에 추가할 파라미터를 선택하세요.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

#### 기본 파라미터

| 이름 | 설명 | 파라미터 |
| --- | --- | --- |
| 사이트 ID | 사이트 ID 매개변수를 설정하여 특정 퍼블리셔에게 설치를 어트리뷰션하도록 합니다. 여러 퍼블리셔가 존재하는 경우 사이트 ID 제한을 초과하지 않도록 사용된 <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">사이트 ID 수를 제한</Anchor>하고 하위 사이트 ID 파라미터를 사용하는 것이 좋습니다. | af\_siteid |
| 캠페인 이름 | 캠페인 이름을 추가하여 TTD로 실행 중인 여러 캠페인을 비교합니다. | c |
| 캠페인 ID | 캠페인 ID를 추가합니다. | af\_c\_id |
| 광고세트 ID | 광고 세트 ID를 추가하여 광고 세트 당 모든 광고의 성과를 비교하세요. | af\_adset |
| 광고 ID | 광고 ID를 추가합니다. | af\_ad\_id |

어트리뷰션 링크에 더 많은 파라미터를 추가할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">어트리뷰션</Anchor> 링크 설정과 어트리뷰션 링크 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">구조 및 파라미터</Anchor>에 대해 자세히 알아보십시오.

#### CTV 측정을 위한 파라미터

앱스플라이어로 CTV 트래픽을 측정하려면 다음 파라미터와 값을 추가할 수 있습니다.

| 파라미터 | 값 | 설명 |
| --- | --- | --- |
| 리디렉트 | false |  |
| af\_xplatform\_vt\_lookback | 1&#126;72시간 | 1&#126;72시간 사이의 값을 입력할 수 있습니다. |

#### 클릭-쓰루 어트리뷰션

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

슬라이더를 사용하여 클릭에서 인스톨까지 최대 시간을 설정하십시오. 룩백 윈도우 내에 발생한 인스톨(첫 실행)만 어트리뷰션 됩니다.

1&#126;23시간 또는 1&#126;30일.

어트리뷰션 링크 파라미터: af\_click\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">클릭 전환 확인 기간에</Anchor>대해 자세히 알아보세요.

클릭-쓰루 어트리뷰션 링크를 복사하여 파트너에게 보내 잠재 고객이 해당 광고를 클릭할 때 활성화되도록 할 수 있습니다.

#### 뷰-쓰루 어트리뷰션

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

슬라이더를 사용하여 노출에서 설치까지의 최대 시간을 설정합니다. 광고 노출 후 다른 관련 광고 클릭이 없는 경우에 한해 이 룩백 윈도우 내에 발생하는 인스톨(첫 실행)만 파트너에게 어트리뷰션됩니다.

0-24시간

어트리뷰션 링크 파라미터: af\_viewthrough\_lookback

<Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">뷰-쓰루 어트리뷰션에</Anchor> 대해 자세히 알아보세요.

뷰쓰루 어트리뷰션 흐름 링크를 복사하여 파트너에게 보내 잠재 고객이 해당 광고를 클릭할 때 활성화되도록 할 수 있습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

트레이드 데스크에는 비용 연동을 사용할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

트레이드 데스크의 광고 수익은 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서 애드 네트워크, 에이전시 또는 둘 다의 역할을 하는 트레이드 데스크에 부여할 권한을 선택할 수 있습니다. 트레이드 데스크에 대한 저작자 표시가 비활성화된 경우에도 권한 탭이 활성화될 수 있으며 트레이드 데스크에 제어 권한을 부여할 수 있습니다.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

#### **애드 네트워크 권한**

* 파트너 연동 설정 허용 파트너가 연동 탭을 설정하도록 허용하세요(인앱 이벤트 포스트백 제외).
* 인앱 이벤트 포스트백 구성 허용
* 리텐션 리포트 접근 허용
* 집약형 로열 유저 데이터 접근 허용
* 집약형 인앱 이벤트 데이터 접근 허용
* 집약형 수익 데이터 접근 허용
* 프로텍트360 대시보드에 액세스 허용

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=%ED%8A%B8%EB%A0%88%EC%9D%B4%EB%93%9C-%EB%8D%B0%EC%8A%A4%ED%81%ACttd-%EC%84%A4%EC%A0%95 h_01HH2DHQWXTB9K2R07SJP1AXER=%ED%8A%B8%EB%A0%88%EC%9D%B4%EB%93%9C-%EB%8D%B0%EC%8A%A4%ED%81%ACttd-%EC%84%A4%EC%A0%95 h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD integrating-ttd-with-appsflyer=ttd%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01GFNDH51M6KYE39C7DJW3BJ8W=ttd%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HH2DHQWYME21J7JV176N71P2=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C h_01HH2DHQWYFJB3ZCWVZZ048AQP=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HH2DHQWYN3CZZCFT9X2R2N9J=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HH2DHQWY1GPVP5W5R4XV2H9C=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HH2DHQWY284121FR8HSFGH45=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HH2DHQWY0XM70BPE7222XE78=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HH2DHQWY4GXPMCV5JEBFERG6=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 default-parameters=%EA%B8%B0%EB%B3%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HH2DHQWYZSECQWRQEKDB9KZH=%EA%B8%B0%EB%B3%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 parameters-for-measuring-ctv=ctv-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HH2DHQWYZPKCY947MWK7GEAP=ctv-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HH2DHQWYCFGJK4ZT9CXFX3X3=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 viewthrough-attribution=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HH2DHQWYP6S95MRAS39Q4RTT=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HH2DHQWYCWYQFBDA19Z9BA8W=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C" />
