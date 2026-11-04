---
title: TikTok 비즈니스용 - 웹사이트 앱용 웹 캠페인 생성
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-10-14T10:27:41Z'
  id: 46191822292113
  locale: ko
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ko/articles/46191822292113
---
> **한눈에 보기:** 웹사이트 앱에 TikTok 웹 광고 연동 설정하여 이벤트 API 통해 웹 전환 신호를 TikTok으로 전송하세요.

<div id="overview" />

## 개요

앱스플라이어 TikTok 웹 광고와의 연동 지원합니다.`tiktokweb_int` 웹사이트 및 앱 캠페인의 경우, TikTok 이벤트 API 통해 직접 기여도 및 전환 데이터를 리포트 할 수 있습니다. 그런 다음 Meta는 해당 데이터를 활용하여 광고 타겟팅을 최적화하고, 성과를 측정하며, 오디언스를 커스텀하여 구축할 수 있습니다.

작동 방식은 다음과 같습니다. 사용자가 TikTok 광고를 클릭하여 웹사이트에 방문한 후 웹사이트 이벤트 (예: 구매 또는 가입)를 완료하면 앱스플라이어 이벤트 API 통해 TikTok에 전환 신호를 보냅니다. 틱톡은 이 데이터를 활용하여 광고 타겟팅 최적화하다 하고 캠페인 성과 측정합니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/web-performance-measurement-overview">앱스플라이어 웹 어트리뷰션 - 개요</Anchor>

<div id="important" />

> 🚧 **중요!**
>
> 현재로서는 이벤트 API 통한 리인게이지먼트 포스트백 전송은 연동 지원 되지 않습니다.

<div id="prerequisites" />

### 필수 조건

웹사이트 앱에 TikTok 웹 광고 연동 활성화하기 전에 다음 사항을 확인하세요.

* 앱스플라이어 에서 설정된 웹사이트 앱
* <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">틱톡 광고 관리자</Anchor> 의 비즈니스 계정

<div id="how-to-set-up-tiktok-web-ads-for-your-website-app" />

### 웹사이트 앱에 틱톡 웹 광고를 설정하는 방법

설정 과정에는 TikTok 웹 광고와 앱스플라이어 간의 연동 정의하고 TikTok 광고 관리자에서 캠페인 구성하는 작업이 포함됩니다. 다음 부분들을 포함합니다:

* 2부: 앱스플라이어에서 Meta 웹 광고 연동 설정 (필수)
* 2부: TikTok 웹 광고에 앱스플라이어 연동 설정하기 (필수의)

<div id="part-1-set-up-tiktok-web-ads-integration-in-appsflyer" />

## 1부: 앱스플라이어 에 TikTok 웹 광고 연동 설정하기

먼저 TikTok 웹 광고 연동 활성화하고 앱스플라이어 이벤트 API 로 전송하는 포스트백을 설정하세요.

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1. TikTok 웹 광고 연동 활성화하세요">

TikTok 웹 광고 연동 활성화하려면 다음 단계를 따르세요.

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. **TikTok 비즈니스용 검색 - 고급 SRN** (또는)`tiktokweb_int` )를 선택하세요.
3. **연동 설정**을 클릭하세요. 활성 **연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다. 파트너와 함께 작업하는 동안 토글은 계속 켜져 있어야 합니다.
5. **픽셀 ID: 픽셀 ID를 입력합니다. <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">틱톡 문서</Anchor> 에 나와 있는 지침에 따라 틱톡 광고 관리자에서 생성하거나 가져올 수 있습니다.**
6. **액세스 토큰: 액세스 토큰을 입력합니다. 이를 생성하거나 검색하려면 <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTok 문서에</Anchor> 나와 있는 절차를 따르세요.**
7. **틱톡 웹 광고의 사용자 개인 정보 사용을 제한하십시오(CCPA):** <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">데이터 보호법</Anchor> 준수를 활성화하려면 이 토글을 켭니다.

<div id="note" />

> 📘 **참고**
>
> CCPA 정보보호법 준수 활성화하면 캘리포니아 또는 미국 내 기타 민감한 주에 거주하는 TikTok 웹 광고 사용자로부터 수집되는 데이터가 제한됩니다.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. 인앱 이벤트 포스트백 설정">

앱스플라이어 이벤트를 TikTok 웹 광고 이벤트에 매핑하여 앱스플라이어 가 TikTok 광고로 전송할 웹 전환 이벤트를 정의할 수 있습니다. 이러한 포스트백은 TikTok 광고 관리자에서 확인할 수 있으며, TikTok은 매핑된 이벤트를 캠페인 최적화 및 리포팅 사용합니다.

인앱 이벤트 포스트백 설정

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. 필요한 경우 인앱 이벤트 포스트백 1. 기간 2. 창 설정하세요. 인앱 이벤트 포스트백 1. 기간 2. 창 구성에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 구성 섹션을</Anchor> 참조하세요.
3. **이벤트 추가**을 클릭하여 목록에 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱스플라이어 웹사이트에 통합된 웹 SDK 또는 앱스플라이어 로 전송하는 서버 간(S2S) 이벤트로부터 이벤트 이름을 수신합니다.
5. **'매핑된 파트너 이벤트'** 열에서 가장 적합한 사전 정의된 파트너 이벤트 선택합니다.
6. **'사용자 대상** ' 열에서 적절한 옵션을 선택하세요.
   * **이 파트너는** TikTok 웹 광고와 관련된 이벤트만 전송합니다.
   * 소스 와 관계없이 모든 이벤트를 **모든 미디어 소스( 오가닉 포함** )에 전송합니다.
7. **포함** 열에서 이벤트가 수익 값과 함께 전송될지 여부를 선택합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">포스트백에 포함할 데이터</Anchor> 참조
8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭하세요.

<div id="note-1" />

> 📘 **참고**
>
> * 구매 이벤트를 설정하는 경우, **포함** 열을 **값 및 수익**으로 설정합니다. 다른 옵션을 선택하면 포스트백이 실패하게 됩니다.
> * 현재, 오직 구매 이벤트만 수익(revenue)을 포함하도록 설정할 수 있습니다.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-tiktok-web-ads" />

## 2부: TikTok 웹 광고에 앱스플라이어 연동 설정하기

틱톡 광고 관리자에서 다음 단계를 완료하세요.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 캠페인 유형, 목적, 목표 설정">

앱스플라이어 에서 전송되는 미리 정의된 인앱 이벤트 캠페인 목표 로 선택할 수 있습니다. 웹사이트 전환 목표와 일치하는 캠페인 목표를 선택하세요. 예를 들어 웹사이트 트래픽 증가 또는 웹사이트 내 전환 최적화 등이 있습니다.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. 도착 URL 설정">

1. **'목적지' 항목** 의 **'웹사이트 URL'** 필드에 사용자가 광고를 클릭한 후 이동하는 페이지인 웹사이트 URL 을 입력하세요.

   **웹사이트 URL** 이 주요 목적지 옵션입니다. 사용자가 광고를 클릭 전환 이벤트를 완료하기 위해 웹사이트로 바로 이동합니다.
2. **[대체] AF 어트리뷰션 링크 (원링크):** 사용자를 모바일 앱 으로 리디렉션하고 웹사이트로 다시 연결되도록 하려면 대상 URL 로 AF 어트리뷰션 링크 (원링크 )를 사용할 수 있습니다.
3. URL 파라미터 대상 URL 에 추가하려면 **'URL 매개변수 생성'을** 클릭하세요.
4. 아래의 **사용자 지정 매개 변수**에서 **매개 변수 추가**를 클릭합니다.
5. 앱스플라이어 파라미터 TikTok 값에 매핑합니다.

| AF 매개변수 | 매핑된 틱톡 가치 |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `c` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   <div id="note-3" />

   > 📘 **참고**
   >
   > 캠페인 분석을 간소화하려면 캠페인 이름에 캠페인 유형(웹 또는 모바일)을 접두사 또는 접미사로 포함하세요. 예를 들어,`campaign-name_web` .


   URL 파라미터 구성 및 트래픽 소스 확인에 대한 모범 사례는 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">트래픽 소스 확인 정보 를</Anchor> 참조하세요.

   결과 URL 의 예:

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   <div id="note-4" />

   > 📘 **참고**
   >
   > 틱톡은 자동으로 추가합니다`ttclid={{ttclid}}` 광고를 클릭된 때 목적지 URL 로 이동합니다.


</Accordion>

<div id="view-web-attribution-data" />

## 웹 어트리뷰션 데이터 보기

웹 전환 이벤트는 다음 항목에 보고됩니다.`tiktokweb_int` PID에서`media_source` 필드. 웹 어트리뷰션 데이터 보려면 로데이터 보고서를 사용하고 필터링하세요.`media_source = tiktokweb_int` 틱톡 웹사이트 앱 전환율을 분리하기 위해.

웹사이트 앱 캠페인에 대한 대시보드 리포팅 아직 제공되지 않습니다. 웹 캠페인 성과 다른 채널과 함께 분석할 수 있는 통합 리포팅 기능이 향후 출시 에 포함될 예정입니다.

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 비용 데이터 | 틱톡 광고 비용 데이터 (`tiktokglobal_int` 웹사이트 앱 캠페인은 대시보드 에 보고되지 않으며, **전체 비용** 리포트 를 제외한 비용 ETL 보고서에도 보고되지 않습니다.   <br />웹사이트 앱 캠페인에 대한 TikTok 비용 데이터를 **전체 비용** 리포트 에서 확인하려면 TikTok 광고 계정을 TikTok 비용 연동 에 연결하세요.`tiktokglobal_int` **비용 설정** 페이지 또는 **비용** 탭을 통해 변경할 수 있습니다. |
| 클릭과 노출 | 현재 틱톡에서는 웹사이트/앱 캠페인의 클릭 수와 노출 수를 확인할 수 없습니다. |
| 리인게이지먼트 | 이벤트 API 를 통한 재참여 포스트백은 현재 지원되지 않습니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KQC152Q49R7P96BPMMZGVZWS=%EA%B0%9C%EC%9A%94 h_01KQC25PY3PPRTQBJ7K8NV3JWQ=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9 h_01KQC152Q42VT7XKTGCEJV7V7S=%EC%A4%91%EC%9A%94 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01KQC152Q4A31VJ1JTXWJG6CN0=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 how-to-set-up-tiktok-ads-for-your-website-app=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%95%B1%EC%97%90-%ED%8B%B1%ED%86%A1-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01KQC152Q4S1VTK7BGWPHHD27W=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%95%B1%EC%97%90-%ED%8B%B1%ED%86%A1-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 part-1-set-up-tiktok-ads-integration-in-appsflyer=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90-tiktok-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90-tiktok-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=%EC%B0%B8%EA%B3%A0 h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=%EC%B0%B8%EA%B3%A0-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=2%EB%B6%80-tiktok-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EC%97%90-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC152Q4NKQHF75Y14XCCFNH=2%EB%B6%80-tiktok-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EC%97%90-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=%EC%B0%B8%EA%B3%A0-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=%EC%B0%B8%EA%B3%A0-3 view-web-attribution-data=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KQC152Q45QE5M5BGD4RJNFR9=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KQC152Q45WC7HNZ64T98JJ6Y=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
