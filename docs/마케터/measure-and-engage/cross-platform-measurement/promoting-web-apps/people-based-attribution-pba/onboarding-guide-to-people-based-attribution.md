---
title: 사람 기반 어트리뷰션(PBA) 온보딩 가이드
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-10-14T10:38:40Z'
  id: 360013821097
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360013821097
---
> **요약:** PBA 설정 체크리스트

## PBA 설정하기

다음 작업 항목과 표에 정리된 설정 작업 목록에 따라 PBA를 설정하세요.

* 앱스플라이어 고객 성공 매니저(CSM) 또는 영업 담당자에게 연락하여 PBA를 활성화하세요.
* 브랜드의 디지털 자산을 브랜드 번들로 그룹화하세요.
* 웹 SDK를 웹사이트에 연동하고, 모바일 SDK를 앱에 연동하세요.
* 앱스플라이어가 데이터를 수집하고 어트리뷰션합니다.
  * 데이터는 여러 소스에서 수집됩니다.
  * 수집된 데이터는 터치포인트와 이벤트로 나뉩니다.
  * 이벤트는 최근 30일 이내의 마지막 비직접 웹 방문에 어트리뷰션 됩니다.
  * 광고주는 특정 이벤트를 전환 이벤트로 지정할 수 있습니다. 예를 들어 구매와 같은 이벤트입니다. 전환 이벤트는 대시보드에서 분석됩니다.
  * 로데이터는 커스텀 데이터 분석에 사용됩니다.
* 고객 여정을 분석하여 캠페인을 최적화하세요.

### PBA 설정 단계

시작하기 전에 앱스플라이어 CSM 또는 영업 담당자에게 연락하여 PBA를 활성화하세요. 그런 다음 설정을 시작하세요. 표에 설정 작업이 자세히 설명되어 있습니다. 진행 상황을 기록하려면이<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">스프레드시트</Anchor>를 다운로드하세요.

**모범 사례: <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">앱과 웹사이트에</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">CUID</Anchor><Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">를 구현하세요. 사용자가 등록하거나 로그인할 때 앱스플라이어는 CUID를 수신합니다.</Anchor>**

<table><thead><tr><th> </th><th>담당자</th><th>작업</th><th>비고</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>광고주 </p></td><td><ul><li> <span><a href="./adding-an-app-to-appsflyer" target="_blank">웹 앱을 앱스플라이어</a>계정에 추가하세요. 웹 앱은 트래픽을 측정할 웹사이트의 URL을 지정하며 이는 <a href="./pba-media-source-attribution-rules" target="_blank">자체 어트리뷰션</a>을 방지하는 데 사용됩니다.</span> </li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">브랜드 번들을 설정하세요.</a> 이를 통해 브랜드의 디지털 자산(모바일 앱과 웹 앱)이 결합됩니다.</span> </li><li>추가로 <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">제외 도메인</a>을 지정하세요.</li></ul></td><td><ul><li><span>분석 및 리포트는 브랜드 내에서 집계됩니다.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> 웹마스터 </td><td><ul><li>웹 앱으로 정의한 웹사이트에 <a href="./pba-web-sdk-integration-guide" target="_blank">웹 SDK</a>를 설치하세요. </li><li>웹 SDK를 다음과 같이 구성하세요:  <ul><li>방문 기록</li><li>이벤트 기록</li><li><mark><a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a>를 설정하세요.</mark></li><li> <a href="./test-pba-web-sdk-integration" target="_blank">SDK 테스트 도구</a>로 구현을 테스트하세요. </li></ul></li></ul></td><td><ul><li><span>SDK는 방문 횟수와 이벤트를 기록합니다.</span></li><li><span>연동은GoogleTag Manager(GTM), Adobe 또는 Tealium을 통해 완벽하게 지원됩니다.</span></li><li> <strong>필수:</strong> 사용자가 회원가입 또는 로그인 직후 SetCustomerUserID()를 호출하세요. CUID가 없으면 CSM과 대안을 논의하세요. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>광고주</p></td><td><p>웹마스터는 SDK가 다음과 같이 구성되었는지 <a href="./test-pba-web-sdk-integration" target="_blank">SDK 시험 도구</a>로 확인해야 합니다.</p><ul><li>방문 기록</li><li>이벤트 기록</li><li>고객 사용자 ID 설정</li></ul></td><td><p><mark>광고주! 이 단계가 완료될 때까지 진행하지 마세요. </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>개발자 &amp; 광고주</p></td><td><p>[선택사항] <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">웹 서버-투-서버</a> API</p></td><td>자동 구독 갱신과 같은 웹 관련 이벤트를 보고합니다.</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>광고주</p></td><td><ul><li> 전환 이벤트를 <span>표시합니다</span>. <ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">웹 이벤트</a></span></li><li> </li></ul></li></ul></td><td><ul><li><span>매일 처리가 완료될 때까지 기다렸다가 이 작업을 수행하세요. </span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>광고주</p></td><td><p>대시보드 사용 시작</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">웹사이트 어트리뷰션</a></li><li><a href="./pba-web-assisted-installs" target="_blank">웹 인스톨 어시스트</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>광고주</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">데이터 락커 설정</a></td><td><p>PBA 로데이터 리포트에 대한 액세스를 제공합니다. 여기에는 터치포인트, 표준 이벤트와 전환 이벤트, 웹 보조 인스톨 및 전환 경로에 대한 특화된 리포트가 포함됩니다.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>광고주</p></td><td><p>[선택사항]<br/><a href="./pba-raw-data-reports" target="_blank">로데이터</a> 사용 시작</p></td><td><p>데이터는 매일 정기적으로 처리된 후 조회할 수 있습니다.</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* 데이터 처리로 인해 데이터는 이벤트 발생 당일 UTC 자정 이후 10시간 후에 사용할 수 있습니다. 즉, 월요일의 이벤트 데이터는 화요일 10:00 UTC부터 조회할 수 있습니다. </td></tr></tbody></table>

## SDK/API를 통한 PBA 데이터 수집

|  | 웹 플랫폼 | 모바일 (앱) 플랫폼 |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide">웹</Anchor><ul><li>웹사이트에 설치된 JavaScript 태그 SDK</li><li>웹사이트 방문 및 웹 이벤트를 보고합니다.</li></ul> | <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">모바일</Anchor><ul><li>앱 SDK가 iOS, 안드로이드, Unity 등에 통합됩니다.</li><li>앱 인스톨 및 인앱 유저 활동을 보고합니다.</li></ul> |
| 서버-투-서버 API | <Anchor target="_blank" href="/marketers/ko/docs/web-server-to-server-events-api-for-pba-web-s2s">웹 서버-투-서버</Anchor><ul><li>백엔드 서버(웹 아님)에서 발생하는 이벤트를 보고합니다.</li><li>예: 구독 갱신</li></ul> | <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">모바일 서버-투-서버</Anchor><ul><li>백엔드 서버(앱 아님)에서 발생하는 이벤트를 보고합니다.</li><li>예: 구독 갱신</li></ul> |

<div data-zendesk-anchors="setting-up-pba=pba-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H8V1XPAHGFVJRKM56S2ZQTBD=pba-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 pba-setup-steps=pba-%EC%84%A4%EC%A0%95-%EB%8B%A8%EA%B3%84 01ECF26CMN668ZZV6XNZA3W692=pba-%EC%84%A4%EC%A0%95-%EB%8B%A8%EA%B3%84 pba-dataacquisition-via-sdkapi=sdkapi%EB%A5%BC-%ED%86%B5%ED%95%9C-pba-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%88%98%EC%A7%91 01H8V1XPAH23BV25ZCMFR7MM9Q=sdkapi%EB%A5%BC-%ED%86%B5%ED%95%9C-pba-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%88%98%EC%A7%91" />
