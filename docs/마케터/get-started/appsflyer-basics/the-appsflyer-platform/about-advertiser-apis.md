---
title: 광고주 API 소개
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-10-14T10:39:39Z'
  id: 360009122638
  locale: ko
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ko/articles/360009122638
---
> **한눈에 보기:** 광고주가 데이터에 액세스하거나 업데이트하는 데 사용할 수 있는 API입니다.

<div id="advertiser-api-list-and-interfaces" />

## 광고주 API 목록 및 인터페이스

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>리포트, 리포트 도구 및 리포트 API에 대한 특정 정보:

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>로데이터 리포트 도구/API</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">종합 및 애널리틱스 리포트 도구/API</Anchor>

<div id="interfaces-for-advertisers" />

#### 광고주를 위한 인터페이스

| 아레나 | API 이름 | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />프리미엄 기능 | 설명 | 인증  <br />토큰/키 | 인터페이스 유형 |
| --- | --- | --- | --- | --- | --- |
| 모바일 어트리뷰션 | <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">서버 간 이벤트</Anchor> | 아니요 | 모바일 앱 외부에서 발생하는 인앱 이벤트를 기록합니다. | <Anchor target="_blank" href="/marketers/ko/docs/app-settings#sdk-authentication-dev-key">SDK 개발 키</Anchor> | REST API |
| 사람 기반 어트리뷰션(PBA) | <Anchor target="_blank" href="/marketers/ko/docs/web-server-to-server-events-api-for-pba-web-s2s">서버 간 웹</Anchor> | 아니요 | 백엔드에서 발생하는 PBA 이벤트 보고 | <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings#브랜드-번들-관리">PBA 키</Anchor> | REST API |
| 인게이지먼트 | <Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크</Anchor> | 예 | 원링크 관리: 생성, 업데이트, 검색, 삭제 | <Anchor target="_blank" href="/marketers/ko/docs/app-settings#sdk-authentication-dev-key">SDK 개발 키</Anchor> | REST API |
| 리마케팅 | <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#import-an-audience">오디언스</Anchor> | 예 | 오디언스에 사용자 목록 업로드 | <Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems">키 가져오기</Anchor> | REST API |
| 프라이버시 | <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">openDSR 요청</Anchor> | 아니요 | 데이터 삭제 요청 및 상태 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 성과 KPI</Anchor> | 예 | CSV 파일의 다중 앱 캠페인 성과 지표 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">집계 리포트 가져오기</Anchor> | 아니요 | CSV 파일로 리포트 집계 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">로데이터 가져오기</Anchor> | 예 | CSV 파일의 로데이터 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/cohort-api">코호트 분석</Anchor> | 예 | JSON 또는 CSV 파일의 코호트 지표 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">데이터 락커</Anchor> | 예 | 로데이터 및 집계 데이터 리포트 | 해당 없음 | 클라우드 스토리지 |
| 모바일 어트리뷰션 | <Anchor target="_blank" href="/marketers/ko/docs/push-api-streaming-raw-data">푸시</Anchor> | 예 | 광고주 서버로 전송되는 실시간 인스톨 및 인앱 이벤트 | 해당 없음 | REST API |
| 캠페인 비용 | <Anchor target="_blank" href="/partners/ko/docs/cost-import-for-ad-networks">비용 가져오기</Anchor> | 아니요 | 캠페인 비용 리포트 | 해당 없음 | (파일 업로드) |
| 계정 | <Anchor target="_blank" href="/marketers/ko/docs/app-list-api-for-app-owners">앱 목록 가져오기</Anchor> | 아니요 | 계정에 있는 앱 목록 가져오기 | <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">ETL 비용</Anchor> | 예 | 비용 ETL 세분화된 캠페인 비용 | 해당 없음 | 클라우드 스토리지 |
| 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#reporting-options">SKAN 리포팅</Anchor> | 아니요 | SKAN 집계 리포팅 | V2.0 | REST API |
| 연동된 파트너 | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">파트너 연동 설정 복사</Anchor> | 아니요 | 한 앱에서 다른 앱으로 연동 구성 파라미터 복사 | V2.0 | REST API |
| 연동된 파트너 | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">인스톨 레퍼러 암호 해독 키 설정</Anchor> | 아니요 | 메타 광고로부터 받은 인스톨 리퍼러 복호화 키 설정 | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=%EA%B4%91%EA%B3%A0%EC%A3%BC-api-%EB%AA%A9%EB%A1%9D-%EB%B0%8F-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 h_01HX9638DX6EHR4ETMSH10K68F=%EA%B4%91%EA%B3%A0%EC%A3%BC-api-%EB%AA%A9%EB%A1%9D-%EB%B0%8F-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 interfaces-for-advertisers=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 h_01HX9638DXNJM3A968A2PSRRKS=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4" />
