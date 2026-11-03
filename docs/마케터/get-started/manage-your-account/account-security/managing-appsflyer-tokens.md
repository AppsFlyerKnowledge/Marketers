---
title: 앱스플라이어 토큰 관리
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-10-14T10:37:06Z'
  id: 360004562377
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/360004562377
---
> **한눈에 보기:** 토큰은 데이터 보안을 강화합니다. 이를 통해 사용자는 앱스플라이어 API를 통해 데이터에 액세스하거나 서버 간 호출을 사용하여 이벤트 데이터를 수신할 수 있습니다. 관리자는 데이터 연속성을 유지하면서 여러 토큰을 관리할 수 있습니다. 여기에는 필요에 따라 API와 서버 간 토큰을 만들고, 이름을 바꾸고, 제거하는 작업이 포함됩니다.

> 🚧 **중요!**
>
> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)
>
> * 관리자만이 토큰을 보고 관리할 수 있습니다. 계정 사용자는 토큰 페이지에 접근할 수 없습니다.
> * 토큰이 귀하의 데이터에 액세스할 수 있도록 안전하게 보관합니다. 공개 코드 리포지토리에 토큰을 게시하지 마십시오.
> * 180일마다 토큰을 교체하는 것이 좋습니다.

## 앱스플라이어 토큰 정보

사용자가 앱스플라이어 API 및 S2S 호출을 통해 유저가 데이터에 액세스할 수 있도록 하는 데 사용됩니다. 관리자는 다양한 목적으로 토큰을 사용합니다.

* 보안 수단:
  * 토큰 손상 또는 의심되는 무단 액세스와 같은 특정 보안 문제 해결
  * 정기적인 보안 정책 업데이트의 일환으로 주기적 토큰 교체
* 다양한 API 호출 관리
* 테스트 목적
* 원링크 API와 같은 특정 기능과 함께 사용

## 토큰 페이지로 이동하기

1. 상단 표시줄에서 계정 메뉴(이메일 주소 드롭다운) > **보안 센터**를 엽니다.
2. **앱스플라이어 API 토큰** 섹션에서 **앱스플라이어 API 토큰 관리**를 클릭합니다.  현재 토큰이 표시됩니다.

## 토큰 유형

여러 목적을 위한 다양한 유형의 토큰이 있습니다. 기본적으로 API 토큰은 각 새 계정(API 토큰 V2)에 대해 생성됩니다. 관리자는 아래 표에 자세히 설명된 대로 각 유형에 대해 최대 2개의 토큰을 만들 수 있습니다.

| 토큰 유형 | 사용 목적 |
| --- | --- |
| <span id="api-token"></span>API 토큰 | Pull API, Cohort API, ROI API 등과 같은 API 호출을 승인하는 데 사용되는 JWT 토큰(JSON Web Token)입니다. |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크 API</Anchor> (프리미엄) | 대규모 캠페인에서 최적의 사용자 인게이지먼트를 위해 개인화된 링크를 생성하는 원링크 API에 사용되는 고유 토큰입니다. |
| <span id="s2s-token"></span>S2S 토큰 | 서버 간 호출을 사용하여 데이터를 보내는 데 사용됩니다. |
| <span id="mcp-token"></span>MCP 토큰 | 타사 또는 자체 호스팅 시스템을 AppsFlyer MCP로 인증하는 데 사용됩니다. |

## 토큰 관리

관리자는 토큰 생성, 이름 바꾸기 및 제거와 같은 작업을 수행하며 여러 토큰들을 관리할 수 있습니다. 주요 목표는 현재 토큰을 새 토큰으로 교체하는 것입니다. 먼저 새 토큰을 [만들고](#토큰-만들기), 시스템에서 구현하여 사용할 수 있게 만든 후 이전 토큰을 [삭제](#토큰-삭제)하는 작업이 필요합니다.

### 토큰 검색

1. 상단 메뉴에서 계정 메뉴(이메일 주소 드롭다운)를 열고 > **보안 센터**로 이동합니다.
2. **앱스플라이어 API 토큰**  섹션에서 앱스플라이어 API 토큰 관리를 클릭합니다 .
3. 사용 가능한 토큰이 표시됩니다.
4. 필요한 토큰을 복사합니다.

### 토큰 만들기

1. [**토큰** 페이지](#토큰-페이지로-이동하기)에서 **+ 새 토큰**을 클릭합니다.
2. 토큰 이름을 입력합니다.
3. 토큰 유형을 선택합니다.
4. **토큰 만들기**를 클릭합니다.

> 📘 **참고**
>
> * 새로운 토큰은 즉시 사용 가능해집니다.
> * 시스템에 새 토큰을 구현해야 합니다.

### 토큰 이름 바꾸기

1. [**토큰** 페이지](#토큰-페이지로-이동하기)에서 이름을 바꾸려는 토큰의 편집 아이콘을 클릭합니다.
2. 토큰의 이름을 바꿉니다.
3. **저장**을 클릭합니다.

### 토큰 삭제

> ❗️ **주의**
>
> * 토큰을 삭제하면 토큰에 의존하는 시스템에 오류가 발생할 수 있습니다.
> * 토큰을 삭제하면 토큰 페이지에서 제거되며, 이전 토큰의 모든 호출이 거부됩니다.
> * 토큰을 바꾸려면 먼저 새 토큰을 만들고 구현한 다음 사용할 수 있게 된 후에("보류 중" 상태가 아닌 경우), 이전 토큰을 삭제할 수 있습니다.

1. [**토큰** 페이지](#토큰-페이지로-이동하기)에서 삭제할 토큰의 삭제 아이콘을 클릭합니다.
2. "토큰 삭제"를 입력하여 토큰 삭제를 확인해야 합니다.
3. **토큰 삭제**을 클릭합니다.

## API V2 토큰의 응용 프로그램

API V2 토큰을 사용하는 광고주 및 광고 네트워크의 사용 사례:

### 광고주

| API V2 토큰 |
| --- |
| <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">Pull API 로데이터</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">Pull API 집약형 데이터</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/app-list-api-for-app-owners">앱 목록 가져오기</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-api">코호트</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAdNetwork 집약형 리포트</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">파트너 연동 설정 복사</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">인스톨 레퍼러 암호 해독 키 설정</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">넷 수익 API</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |
| 오디언스 API 가져오기 |

### 애드 네트워크

| API V2 토큰 |
| --- |
| <Anchor target="_blank" href="/partners/ko/docs/app-list-api-for-ad-networks">애드 네트워크용 앱 목록</Anchor> |
| <Anchor target="_blank" href="/partners/ko/docs/access-to-aggregated-analytics-tools-for-api-partners">캠페인 관리 플랫폼과의 연동</Anchor> |
| <Anchor target="_blank" href="/partners/ko/docs/protect360-for-integrated-partners#protect360-애드-네트워크-리포팅-api">연동 파트너를 위한 Protect360 리포트</Anchor> |
| <Anchor target="_blank" href="/partners/ko/docs/incost-api-for-ad-networks">InCost</Anchor> |

## S2S 토큰의 응용

광고주 및 S2S 토큰을 사용하는 광고주를 위한 사용 사례:

### 광고주

| S2S 토큰 |
| --- |
| <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">모바일 인앱 이벤트 S2S API</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-s2s-api-for-web-performance-measurement">웹 이벤트 S2S API</Anchor> |

### 애드 네트워크

| S2S 토큰 |
| --- |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-appsflyer-preload-referrer-attribution">앱스플라이어 프리로드 리퍼러 어트리뷰션</Anchor> |

> 📘 **참고**
>
> 대부분의 광고 네트워크에서 S2S 토큰 생성은 더 이상 셀프 서비스가 아닙니다. 그 결과, 관리자는 UI에서 S2S 토큰을 생성하는 옵션을 볼 수 없습니다. 셀프 서비스 토큰 생성은 특정 관리 파트너에게만 제공됩니다.

## 원링크 토큰 신청

원링크 API 토큰을 사용하는 광고주의 사용 사례:

맞춤형 파라미터가 포함된 원링크 짧은 URL을 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">생성</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">가져오기</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">업데이트</Anchor>, 그리고 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">삭제</Anchor>할 수 있습니다.

## MCP 토큰 신청

사용 가능한 MCP 토큰의 사용 사례를 보려면 <Anchor target="_blank" href="/marketers/ko/docs/beta-appsflyer-mcp">AppsFlyer MCP 기사</Anchor>를 참조하십시오.

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=%EC%A4%91%EC%9A%94 overview=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%86%A0%ED%81%B0-%EC%A0%95%EB%B3%B4 h_01HFY5D0E1H66CEB3KMJQEXV4K=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%86%A0%ED%81%B0-%EC%A0%95%EB%B3%B4 reaching-the-tokens-page=%ED%86%A0%ED%81%B0-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A1%9C-%EC%9D%B4%EB%8F%99%ED%95%98%EA%B8%B0 h_01HFTT570KF3XM9MBSFYRDYN9S=%ED%86%A0%ED%81%B0-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A1%9C-%EC%9D%B4%EB%8F%99%ED%95%98%EA%B8%B0 token-types=%ED%86%A0%ED%81%B0-%EC%9C%A0%ED%98%95 h_01HFBR7KP8BZN7KH0BNJ982WK8=%ED%86%A0%ED%81%B0-%EC%9C%A0%ED%98%95 manage-your-tokens=%ED%86%A0%ED%81%B0-%EA%B4%80%EB%A6%AC h_01HFY5D0E1AF4NYPX31W3VJYQC=%ED%86%A0%ED%81%B0-%EA%B4%80%EB%A6%AC retrieving-api-tokens=%ED%86%A0%ED%81%B0-%EA%B2%80%EC%83%89 h_01HBQN3T2HKEMNC8MSR0THYW2S=%ED%86%A0%ED%81%B0-%EA%B2%80%EC%83%89 create-a-token=%ED%86%A0%ED%81%B0-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HFY5D0E1FECQC1HN0EXWMXAV=%ED%86%A0%ED%81%B0-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HFY5D0E1HJFKFPRT8WVNPHDG=%EC%B0%B8%EA%B3%A0 rename-a-token=%ED%86%A0%ED%81%B0-%EC%9D%B4%EB%A6%84-%EB%B0%94%EA%BE%B8%EA%B8%B0 h_01HFY5D0E2Z8ZH0PAX148C4F38=%ED%86%A0%ED%81%B0-%EC%9D%B4%EB%A6%84-%EB%B0%94%EA%BE%B8%EA%B8%B0 delete-a-token=%ED%86%A0%ED%81%B0-%EC%82%AD%EC%A0%9C h_01HFY5D0E2B1KXGSFZR0AYAER5=%ED%86%A0%ED%81%B0-%EC%82%AD%EC%A0%9C h_01HFY5D0E2KZYG0J2R7GR1R7W5=%EC%A3%BC%EC%9D%98 applications-of-the-api-v2-token=api-v2-%ED%86%A0%ED%81%B0%EC%9D%98-%EC%9D%91%EC%9A%A9-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8 h_01HG64DMW7PYRXBMZN00EQN991=api-v2-%ED%86%A0%ED%81%B0%EC%9D%98-%EC%9D%91%EC%9A%A9-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8 v20-token%E2%80%94advertiser-apis=%EA%B4%91%EA%B3%A0%EC%A3%BC h_01HBQN7TBASK192P8D7AEWM9P6=%EA%B4%91%EA%B3%A0%EC%A3%BC v20-token%E2%80%94ad-network-apis=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC h_01HBQN7TBAWAHEQXMYK9V14G0M=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC applications-of-the-s2s-token=s2s-%ED%86%A0%ED%81%B0%EC%9D%98-%EC%9D%91%EC%9A%A9 h_01HG64M8K1PPY2Z2406MC78EEN=s2s-%ED%86%A0%ED%81%B0%EC%9D%98-%EC%9D%91%EC%9A%A9 advertiser=%EA%B4%91%EA%B3%A0%EC%A3%BC-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=%EA%B4%91%EA%B3%A0%EC%A3%BC-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-1 ad-network=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=%EC%B0%B8%EA%B3%A0-1 applications-for-the-onelink-token=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%86%A0%ED%81%B0-%EC%8B%A0%EC%B2%AD h_01JSKCWS5406YQJP3RR9KAXJC9=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%86%A0%ED%81%B0-%EC%8B%A0%EC%B2%AD applications-for-the-mcp-token=mcp-%ED%86%A0%ED%81%B0-%EC%8B%A0%EC%B2%AD h_01K9YD2Y9M1C8QDBS5H048XYYD=mcp-%ED%86%A0%ED%81%B0-%EC%8B%A0%EC%B2%AD" />
