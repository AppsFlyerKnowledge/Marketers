---
title: 스냅챗— 웹사이트 앱용 웹 캠페인 생성
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-14T10:27:39Z'
  id: 46196482479249
  locale: ko
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ko/articles/46196482479249
---
> **한눈에 보기:** 웹사이트 앱에 스냅챗 웹 광고 연동 설정하여 전환 API 통해 웹 전환 신호를 스냅챗 으로 전송하세요.

<div id="overview" />

## 개요

앱스플라이어 스냅챗 웹 광고와의 연동 지원합니다.`snapweb_int` 웹사이트 앱 캠페인의 경우 Snapchat의 전환 API 통해 직접 기여도 및 전환 데이터를 리포트 할 수 있습니다. 그런 다음 Meta는 해당 데이터를 활용하여 광고 타겟팅을 최적화하고, 성과를 측정하며, 오디언스를 커스텀하여 구축할 수 있습니다.

작동 방식은 다음과 같습니다. 사용자가 스냅챗 광고를 클릭하여 웹사이트에 방문한 후 웹사이트에서 특정 이벤트 (예: 구매 또는 가입)를 완료하면 앱스플라이어 전환 API 통해 스냅챗 에 전환 신호를 전송합니다. 스냅챗 이 데이터를 활용하여 광고 타겟팅 최적화하다 하고 캠페인 성과 측정합니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/web-performance-measurement-overview">앱스플라이어 웹 어트리뷰션 - 개요</Anchor>

<div id="important" />

> 🚧 **중요!**
>
> 현재로서는 전환 API 통한 리인게이지먼트 포스트백 전송은 연동 지원 하지 않습니다.

<div id="prerequisites" />

### 필수 조건

웹사이트 앱에 스냅챗 웹 광고 연동 활성화하기 전에 다음 사항을 확인하세요.

* 앱스플라이어 에서 설정된 웹사이트 앱
* <Anchor target="_blank" href="https://ads.snapchat.com/">스냅챗 광고 관리자</Anchor> 의 비즈니스 계정

<div id="how-to-set-up-snapchat-ads-for-your-website-app" />

### 웹사이트 앱에 스냅챗 웹 광고를 설정하는 방법

설정 과정에는 스냅챗 웹 광고와 앱스플라이어 간의 연동 정의하고 스냅챗 광고 관리자에서 캠페인 구성하는 작업이 포함됩니다. 다음 단계를 포함합니다.

* 2부: 앱스플라이어 에 스냅챗 웹 광고 연동 설정하세요(필수).
* 2부: 스냅챗 웹 광고에 앱스플라이어 연동 설정하세요(필수).

<div id="part-1-set-up-snapchat-ads-integration-in-appsflyer" />

## 1부: 앱스플라이어 에서 스냅챗 웹 광고 연동 설정하세요

먼저 스냅챗 웹 광고 연동 활성화하세요. 다음으로 앱스플라이어 전환 API 로 보내는 포스트백을 구성합니다.

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1. 스냅챗 웹 광고 연동 활성화하세요">

스냅챗 웹 광고 연동 활성화하려면 다음 단계를 따르세요.

1. 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.
2. **스냅챗** 검색해서 선택하세요.
3. **연동 설정**을 클릭하세요. 활성 **연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다. 파트너와 함께 작업하는 동안 토글은 계속 켜져 있어야 합니다.
5. **픽셀 ID: 픽셀 ID를 입력합니다. <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">스냅챗 웹 광고 문서</Anchor> 의 지침에 따라 스냅챗 광고 관리자에서 생성하거나 가져올 수 있습니다.**
6. **액세스 토큰: 액세스 토큰을 입력합니다. 웹 광고를 생성하거나 검색하려면 <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">스냅챗 웹 광고 공식 문서의 지침을</Anchor> 따르세요.**

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. 인앱 이벤트 포스트백 설정">

앱스플라이어 이벤트를 스냅챗 웹 광고 이벤트에 매핑하여 앱스플라이어 가 스냅챗 광고로 전송할 웹 전환 이벤트를 정의할 수 있습니다. 이러한 포스트백은 스냅챗 광고 관리자에서 확인할 수 있습니다. 스냅챗 매핑된 이벤트를 캠페인 최적화 및 리포팅 활용합니다.

인앱 이벤트 포스트백 설정

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. 필요한 경우 인앱 이벤트 포스트백 1. 기간 2. 창 설정하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">앱 내 이벤트 포스트백 구성</Anchor> 에서 자세한 내용을 확인하세요.
3. **이벤트 추가**을 클릭하여 목록에 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱스플라이어 웹사이트에 통합된 웹 SDK 또는 앱스플라이어 로 전송하는 서버 간(S2S) 이벤트로부터 이벤트 이름을 수신합니다.
5. **'매핑된 파트너 이벤트'** 열에서 목록에서 가장 적합한 사전 정의된 파트너 이벤트 선택합니다.
6. **'사용자 대상** ' 열에서 적절한 옵션을 선택하세요.
   * **이 파트너는** 스냅챗 웹 광고와 관련된 이벤트만 전송합니다.
   * **모든 미디어 소스( 오가닉 포함** )는 소스 와 관계없이 모든 이벤트를 전송해야 합니다.
7. **'포함** ' 열에서 수익 값을 포함한 이벤트를 전송할지 여부를 선택하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">포스트백에 포함할 데이터</Anchor> 참조
8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭하세요.

<div id="note" />

> 📘 **참고**
>
> * 구매 이벤트를 설정하는 경우, **포함** 열을 **값 및 수익**으로 설정합니다. 다른 옵션을 선택하면 포스트백이 실패합니다.
> * 현재로서는 구매 이벤트 에만 수익 포함하도록 설정할 수 있습니다.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-snapchat-ads" />

## 2부: 스냅챗 웹 광고에 앱스플라이어 연동 설정하기

스냅챗 광고 관리자에서 다음 단계를 수행하십시오.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 캠페인 유형, 목적, 목표 설정">

앱스플라이어 에서 전송되는 미리 정의된 인앱 이벤트 캠페인 목표 로 선택할 수 있습니다. 웹사이트 전환 목표와 일치하는 캠페인 목표를 선택하세요. 예를 들어 웹사이트 트래픽 증가 또는 웹사이트 내 전환 최적화 등이 있습니다.

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. 대상 URL 설정하세요">

1. **'목적지' 항목** 의 **'웹사이트 URL'** 필드에 사용자가 광고를 클릭한 후 이동하는 페이지인 웹사이트 URL 을 입력하세요. **웹사이트 URL** 이 주요 목적지 옵션입니다. 사용자가 광고를 클릭 전환 이벤트를 완료하기 위해 웹사이트로 바로 이동합니다.
2. **[대안] AF 어트리뷰션 링크 (원링크):** 사용자를 모바일 앱 으로 리디렉션하고 웹사이트로 다시 연결되도록 하려면 대상 URL 로 AF 어트리뷰션 링크 (원링크 )를 사용할 수 있습니다.
3. URL 파라미터 대상 URL 에 추가하려면 **'URL 매개변수 생성'을** 클릭하세요.
4. 아래의 **사용자 지정 매개 변수**에서 **매개 변수 추가**를 클릭합니다.
5. 앱스플라이어 파라미터 스냅챗 값에 매핑합니다.

| AF 매개변수 | 매핑된 스냅챗 값 |
| --- | --- |
| `pid` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_channel` | `{{site_source_name}}` |

   * 캠페인 분석을 간소화하려면 캠페인 이름에 캠페인 유형(웹 또는 모바일)을 접두사 또는 접미사로 포함하세요. 예를 들어,`campaign-name_web` .

   URL 파라미터 구성 및 트래픽 소스 확인에 대한 모범 사례는 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">트래픽 소스 확인 정보 를</Anchor> 참조하세요.

   결과 URL 의 예:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

<div id="note-3" />

> 📘 **참고**
>
> Meta는 광고가 클릭될 때, `ScCid={{ScCid}}`을 도착 URL로 자동으로 추가합니다.

</Accordion>

<div id="view-web-attribution-data" />

## 웹 어트리뷰션 데이터 보기

설정 후 어트 어트리뷰션 데이터 검토할 때 다음과 같은 내용을 확인할 수 있습니다.

* **원시 데이터 내보내기 및 API 응답** 에는 Snap Web이 포함됩니다.`media_source` Snap 웹 활동 위한 필드입니다.
* 웹 캠페인 설정 세부 정보를 확인하려면 다음을 확인하세요.`original_url` 필드가 표시됩니다`snapchat_int` 웹 캠페인 생성 시 사용되는 PID입니다.

> 📘 **참고**
>
> 웹사이트 앱 캠페인에 대한 대시보드 리포팅 아직 제공되지 않습니다. 웹 캠페인 성과 다른 채널과 함께 분석할 수 있는 통합 리포팅 기능이 향후 출시 에 포함될 예정입니다.

<div id="measure-web-attribution-data-with-web-cost" />

## 웹 비용으로 웹 어트리뷰션 데이터 측정하세요

스냅챗 광고의 웹 어트리뷰션 데이터 와 웹 비용 데이터를 대시보드 와 <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">비용 ETL 보고서</Anchor> 에서 완벽 성과 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide#roi360-소개">ROI360 패키지를</Anchor> 보유하고 다음 설정을 완료해야 합니다.

1. 웹사이트 앱에 비용을 연결하려면 다음을 이용하세요.`snapchat_int` (통하지 않음)`snapweb_int` **비용** 탭 또는 **비용 설정** 페이지에서 확인할 수 있습니다. 비용 데이터 연결 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">ROI360 비용 API 설정하여 비용 데이터 측정하기를</Anchor> 참조하세요.
2. 캠페인 ID 포함하세요(`af_c_id` ) 랜딩 페이지 URL 에 있습니다. 비용, 클릭 수, 노출 수를 웹 기여도와 연결하여 가장 세밀한 수준 까지 확인할 수 있도록 URL 에 전체 캠페인 계층 구조가 포함되어 있는지 확인하세요.

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 클릭과 노출 | 웹 캠페인의 클릭 및 노출 수를 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide">ROI360 구독이</Anchor> 필요합니다. |
| 리인게이지먼트 | 전환 API 통한 재참여 포스트백은 현재 지원되지 않습니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KQC7RA5R1PS69N3015WY4QRY=%EA%B0%9C%EC%9A%94 h_01KQC80MBB1KCVVNDSFSJHG5ZT=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9 h_01KQC7RA5RAY6R70GNHCYWAMRC=%EC%A4%91%EC%9A%94 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01KQC7RA5R02QV60T81NX055DM=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 how-to-set-up-snapchat-ads-for-your-website-app=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%95%B1%EC%97%90-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01KQC7RA5RPWP0X927ENN6KJ9V=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%95%B1%EC%97%90-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 part-1-set-up-snapchat-ads-integration-in-appsflyer=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90%EC%84%9C-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 h_01KQC7RA5RY1HF9VHC332FVBFR=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90%EC%84%9C-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=%EC%B0%B8%EA%B3%A0 part-2-set-up-appsflyer-integration-in-snapchat-ads=2%EB%B6%80-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EC%97%90-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC7RA5REPX0WDDHT7YWDHMC=2%EB%B6%80-%EC%8A%A4%EB%83%85%EC%B1%97-%EC%9B%B9-%EA%B4%91%EA%B3%A0%EC%97%90-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=%EC%B0%B8%EA%B3%A0-1 view-web-attribution-data=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KQC7RA5SKRWGGCKV71MV8J56=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KQC7RA5S5VWHT4DW2MPSMNY0=%EC%B0%B8%EA%B3%A0-2 measure-web-attribution-data-with-web-cost=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EC%9C%BC%EB%A1%9C-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B8%A1%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 h_01KQC7XYSWPTHVDY5R3EG8H4K2=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EC%9C%BC%EB%A1%9C-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B8%A1%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KQC7RA5SSZB8M8G00NTXG71K=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
