---
title: CTV, PC 및 콘솔 플랫폼 다이렉트 어트리뷰션 링크
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-14T10:37:53Z'
  id: 15199908310801
  locale: ko
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ko/articles/15199908310801
---
> **요약:**  CTV, PC, 콘솔 플랫폼에 대한 앱스플라이어 어트리뷰션 링크와 파라미터를 자세히 알아보십시오. **참고**: 안드로이드 PC 게임을 포함한 안드로이드 및 iOS 앱에는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">모바일 어트리뷰션 링크 지침</Anchor>을 사용하십시오.

## 개요

CTV, PC 및 콘솔 플랫폼 다이렉트 어트리뷰션 링크를 사용하면 광고주가 클릭 후 사용자를 리디렉션하고 데이터를 수집할 수 있습니다. 이러한 직접 어트리뷰션 링크는 **한 번에 한 플랫폼에서 실행되는 하나의 목적 앱에 대한** 리디렉션 및 어트리뷰션을 지원하는 앱스플라이어 링크입니다. 리디렉션 대상은 링크에 포함된 af\_r 파라미터의 값입니다.

**참고**: 안드로이드 PC 게임을 포함한 안드로이드 및 iOS 앱에는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">모바일 어트리뷰션 링크 지침</Anchor>을 사용하십시오.

어트리뷰션 링크는 사용자가 직접 만들어 광고 뒤에 배치할 수 있습니다. 이러한 링크를 만들려면 이 문서의 지침을 따르십시오.

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">또는 EngagementsAPI를 사용하여 S2S를 통해 링크를 만들 수 있습니다. 이는 약간의 개발 작업을 요구합니다. **참고**: S2S를 통해 생성된 링크도 노출 데이터를 수집할 수 있습니다.</Anchor>

### 어트리뷰션 링크

<table><thead><tr><th colspan="2">어트리뷰션 링크 구조</th></tr></thead><tbody><tr><td>기본 URL</td><td>engagement.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>필수 경로 파라미터</td><td><ul><li>플랫폼<br/>예: steam</li><li>app_id<br/>예: 123456</li></ul></td></tr><tr><td>필수 쿼리 파라미터</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>기타 파라미터</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#파라미터">전체 보기</a></td></tr><tr><td>URL 구조</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr><tr><td>샘플 URL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&amp;af_campaign_id=1234&amp;af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello</code></td></tr></tbody></table>

### 파라미터

| 파라미터 | 로데이터 내보내기 및 Pull API의 표시 이름 | 설명 | 필드 유형 |
| --- | --- | --- | --- |
| 플랫폼 | 플랫폼 | <ul><li>애플리케이션 플랫폼을 지정하는 경로 파라미터.</li><li>가능한 값:<ul><li>smartcast</li><li>티젠</li><li>로쿠</li><li>웨보스</li><li>비다</li><li>Playstation</li><li>steam</li><li>퀘스트</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | 문자열 |
| app\_id | 앱 ID | <ul><li>게시하는 앱의 앱 ID를 지정하는 경로 파라미터.</li><li>예시: ap123456</li></ul> | 문자열 |
| af\_media\_source | 미디어 소스 | 앱스플라이어 플랫폼에 정의된 고유 파트너 식별자입니다.  <br />다음 특수 문자는 허용되지 않습니다: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, \/, \{, \}, %. | 문자열 |
| af\_campaign | 캠페인 | 캠페인 이름 | 문자열 |
| af\_campaign\_id | 캠페인 ID | 캠페인 ID | 문자열 |
| af\_request\_id | 해당 없음 | 파트너 요청을 고유하게 식별하는 ID입니다. | 문자열 |
| af\_adset | 광고 세트 | 광고 세트 이름 | 문자열 |
| af\_adset\_id | 광고 세트 ID | 광고 세트 ID | 문자열 |
| af\_ad | 광고 | 광고 이름 | 문자열 |
| af\_ad\_id | 광고 ID | 광고 ID | 문자열 |
| af\_campaign\_type | 캠페인 유형 | 다음 중 하나:<ul><li>user\_acquisition</li><li>리타겟팅</li></ul> | 문자열 |
| af\_prt | 파트너 | <ul><li>에이전시에 어트리뷰션할 수 있도록 하는 에이전시 계정 이름</li><li>**주의**: **에이전시 권한**이 활성화되어 있는지 확인하기 전에는 이 매개변수를 사용하지 마세요.</li></ul> | 문자열 |
| af\_siteid | 사이트 ID | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>광고를 표시하는 퍼블리셔의 고유 ID | 문자열 |
| af\_sub\_siteid | 하위 사이트 ID | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>광고 서브 네트워크/퍼블리셔 ID | 문자열 |
| af\_click\_id | 해당 없음 | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>애드 네트워크 고유 트랜잭션 ID | 문자열 |
| af\_lookback\_window | 해당 없음 | <ul><li>ID 매칭으로 어트리뷰션하는 룩백 윈도우</li><li>룩백 윈도우 기간을 구성할 수 있는 일/시간의 선택입니다. 사용 가능한 파라미터 값: 1일&#126;30일(일) 또는 1시간&#126;23시간(시간).</li><li>유효성 검증: 위의 스키마를 사용하여 최대 3자.</li><li>기본값은 노출에 대해 24시간, 클릭에 대해 7일입니다.</li></ul> | 문자열 |
| af\_ad\_placement | 해당 없음 | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>애드 네트워크 고유 트랜잭션 ID | 문자열 |
| af\_ad\_type | 광고 타입 | <ul><li>광고 유형. 다음 명명 규칙을 사용하세요:<ul><li>**text:** 문자만 포함하는 광고 단위, 예: 검색 결과</li><li>**배너:** 디바이스 화면 상단 또는 하단에 표시되는 기본 형식</li><li>**interstitial:** 현재 사용 중인 앱의 쉬는 시간에 표시되는 전면 광고</li><li>**video:** 표준 비디오, 비보상형</li><li>**rewarded\_video:** 동영상을 시청하면 인앱 보상을 제공하는 광고 단위</li><li>**playable:** 앱 체험을 미리보기로 제공하는 광고 단위</li><li>**audio:** 오디오 광고</li></ul></li><li>대소문자 구분 엄격 적용</li></ul> | 문자열 |
| af\_channel | 채널 | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>광고가 배포되는 미디어 소스 채널, 예: UAC\_Search, UAC\_Display, 인스타그램, Meta Audience Network 등 | 문자열 |
| af\_model | 디바이스 모델 | 디바이스 모델명 | String 64 |
| af\_os\_version | 해당 없음 | <ul><li>디바이스 OS 버전</li><li>숫자와 점만 입력 가능</li><li>예시: 8.1.0</li></ul> | 문자열 |
| af\_device\_id\_type | 해당 없음 | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>디바이스 식별자 유형 다음 중 하나:<ul><li>Vida</li><li>tifa</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>커스텀</li></ul> | 문자열 |
| af\_device\_id\_value | 해당 없음 | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>디바이스 식별자 값 | 문자열 |
| af\_r | 해당 없음 | <ul><li>필수</li><li>올바른 애플 앱 스토어나 랜딩 페이지로 연결되는 링크를 포함합니다.</li><li>af\_r 매개변수 내의 모든 것은 인코딩해야 합니다. 여기에는 UTM 매개변수 값이 포함됩니다(추가된 경우).</li></ul>**참고:** | 문자열 |

## 특징 및 제약 사항

| 룩백 윈도우 | 확률적 모델링에서는 클릭과 노출에 대해 24시간의 고정 룩백 윈도우가 사용됩니다. af\_lookback\_window 값은 무시됩니다. |
| --- | --- |
|  |  |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H7Z1003GTTMRY072BXWDFNP0=%EA%B0%9C%EC%9A%94 attribution-link=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC 01H7Z1003G0WYBCK3530064WM1=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC attribution-link-parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H7Z1003GNC551PDCKKFQMPVN=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HVED5DJPFR5XCWYDSYCHMCR6=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
