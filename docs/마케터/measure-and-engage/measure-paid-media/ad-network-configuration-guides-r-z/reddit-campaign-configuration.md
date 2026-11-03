---
title: Reddit 캠페인 구성
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-10-14T10:40:02Z'
  id: 360011016138
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/360011016138
---
> **한눈에 보기:** 앱스플라이어 애드 네트워크에 연동된 파트너인 Reddit은 다른 곳에서는 찾아볼 수 없는 월간 기준 참여도가 높은 사용자 수가 4억 3천만 명이나 되는 회사입니다.

## Reddit 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법**: 앱스플라이어의 측면 메뉴에서 협업 > **활성화된 연동**을 선택하세요.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다.  
   **참고:** 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(활성화됨/strong>).
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

***연동 탭***은 여러 섹션으로 나뉘어져 있습니다.

#### 파트너 활성화

구성을 활성화하려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">파트너를 활성화하세요</Anchor>.

#### 프라이버시 강화 모드

iOS**앱의 경우에만 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#b-advanced-privacy">고급 개인 정보 보호(iOS 14.5+ 이상)</Anchor>** 가 켜져 있으면 포스트백 및 리포트를 통해 Reddit과 공유되는 데이터를 제어할 수 있습니다.

#### 트랜잭션 ID

**iOS 앱에 한해, <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN 트랜잭션 ID 공유</Anchor>** 가 켜져 있으면 앱스플라이어가 SKAdNetwork 포스트백의 트랜잭션 ID를 Reddit과 공유할 수 있습니다. 그러면 Reddit이 SKAdNetwork 전환 값을 디코딩할 수 있습니다.

#### 일반 설정

**뷰-쓰루 어트리뷰션 활성화**

Reddit의 뷰-쓰루 설치를 어트리뷰션하려면 활성화합니다. 뷰-쓰루 룩백 슬라이더는 [***어트리뷰션 링크***](/docs/reddit-campaign-configuration#attribution-link-tab) 탭에서 사용할 수 있습니다.

#### 기본 포스트백

사용자 설치 후 자동 포스트백을 Reddit으로 전송합니다. 어트리뷰션된 설치에 대해 포스트백을 보낼지 여부를 선택합니다.

* Reddit만 해당
* 오가닉을 포함한 모든 소스

#### 인앱 이벤트 설정

이 섹션에서는 Reddit으로 전송되는 인앱 이벤트 포스트백을 구성할 수 있습니다.

**인앱 이벤트 포스트백 설정 방법:**

1. ***인앱 이벤트 포스트백***을 활성화합니다.
2. SDK 이벤트를 목록에 추가하려면 ***이벤트 추가***를 클릭합니다.
3. 다음 데이터를 입력합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | SDK 또는 서버 간 이벤트로부터 앱스플라이어가 수신한 이벤트 이름입니다.  <br />**팁**: 목록에 원하는 이벤트가 표시되지 않으면 논오가닉 설치가 있는 기기에서 이 이벤트를 활성화하고 다시 확인하세요. |
| **파트너 이벤트 식별자** | Reddit 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다. SDK 이벤트에 가장 적합한 사전 정의된 이벤트를 선택합니다.<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **보내기 옵션** | 다음과 같은 방법으로 이벤트를 보낼지 여부를 선택합니다.<ul><li>Reddit만 해당</li><li>오가닉을 포함한 모든 소스</li></ul> |
| **이벤트 데이터 전송** | <ul><li>**No values & no revenue:** 이벤트 값(event value)를 제외하고 이벤트만 전송합니다.</li><li>**Values & no revenue:** 매출 값을 제외한 모든 파라미터를 전송합니다.</li><li>**Values & revenue**: 매출 값(이벤트에 존재하는 경우)을 포함하여 모든 이벤트 파라미터를 전송합니다.</li></ul> |

4. ***저장***을 클릭합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기</Anchor>.

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

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

광고 수익 데이터는 Reddit에서 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서 Reddit에 부여할 권한을 선택할 수 있습니다. Reddit에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 Reddit에 제어 권한을 부여할 수 있습니다.

#### 애드 네트워크 권한

이 탭에서 Reddit에 부여할 권한을 선택할 수 있습니다. Reddit에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 Reddit에 제어 권한을 부여할 수 있습니다.

이 토글을 사용하여, 앱에 대한 자체 설정 권한을 애드 네트워크에 부여할 수 있습니다.

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>파트너 연동 설정 허용:*** 파트너가 연동 탭을 설정할 수 있도록 허용 (인앱 이벤트 포스트백 제외)
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***인앱 이벤트 포스트백 구성 허용:*** 파트너가 연동 탭에서 자체적으로 매핑되는 인앱 이벤트 포스트백을 설정하도록 허용
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***리텐션 리포트 액세스 허용:*** 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***종합 로열 유저 데이터 접근 허용:*** 파트너 자사만의 로열 유저에만 해당
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***연동 인앱이벤트 데이터 액세스 허용:*** 파트너가 유입시킨 유저의 인앱이벤트 데이터만 해당
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***종합 수익 데이터 접근 허용***: 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***지출 수집 허용:*** 파트너가 이 앱의 파일에 있는 광고 지출 데이터만 보낼 수 있도록 허용합니다.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Protect360 대시보드 액세스 허용:*** 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

## 로데이터 제한

2024년 10월 22일부터 Reddit의 로데이터가 앱스플라이어 플랫폼에서 제한됩니다. 이로 인해 미디어 소스는 '제한됨'으로 보고됩니다. Reddit의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.

<div data-zendesk-anchors="setting-up-reddit=reddit-%EC%84%A4%EC%A0%95 01EDKYCH117BTY81G0Z2NF181F=reddit-%EC%84%A4%EC%A0%95 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab activate-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01EDKYCH11E2X1VSSG2HKKP6VS=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C h_01HJRZF42CYME3EZ37470339CF=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C transaction-id=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id h_01HJRZF42CN7VT8SKNX5E638R0=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01EDKYCH11WFJ09XBND6RQT0XA=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01EDKYCH11KZT2BN64AGETTMD6=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 01EDKYCH11QAYSV2GMYD4R6DJJ=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C 01EDKYCH12FXE1WASY5YQF80CV=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C raw-data-restrictions=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C 01JAQ0TCR54Q03RQWPNT5PJGPN=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C" />
