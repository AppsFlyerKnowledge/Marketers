---
title: '업데이트 알림: 앱스플라이어의 SKAN 4 지원'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2026-10-14T10:29:36Z'
  id: 11938810583825
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/11938810583825
---
| **헤드라인** |  |
| --- | --- |
| **발효일** | <ul><li>2025년 2월 1일</li><li>2월부터 V6.10을 사용하더라도 최신 버전 V6.12 이상으로 업데이트하는 것이 좋습니다.<ul><li>변경 사항 목록은 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-ios-sdk-release-notes">여기</Anchor>서 볼 수 있습니다.</li></ul></li><li>곧 적용 예정:</li></ul> |
| **필수 조건** | SKAN 4 iOS 데이터를 올바르게 기록하려면 다음이 필요합니다.<ul><li>앱스플라이어 SDK 버전 V6.12.1 이상</li><li>광고 네트워크는 SKAdNetwork V4에 대한 광고 서명을 생성해야 합니다.</li><li>앱에 표시되는 광고의 경우 iOS 16.1 SDK 이상으로 앱을 빌드해야 합니다.</li><li>웹 광고의 경우 Safari 16.1 이상이 필요합니다.</li><li>보급된 앱은 App Store에서 서명해야 하며 iOS 16.1 이상이 설치된 기기에서 실행해야 합니다.</li></ul> |
| **필요한 작업** | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/appsflyer-ios-sdk-release-notes">앱스플라이어 SDK를 V6.12.1 이상</Anchor>으로 업그레이드</li><li>앱스플라이어 SKAN Conversion Studio에서 SKAN <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#skan-4">4 측정 모드로</Anchor> 업그레이드하고 3개의 SKAN 창에 대한 CV를 구성합니다(또는 기본 설정 유지).</li></ul>**참고: 참고: SKAN 4로 업그레이드한 경우:**<ul><li>SKAN 4 설치 이전의 활동 타이머는 48시간입니다.</li><li>이전 SKAN 버전으로 되돌릴 수 없습니다.</li></ul> |
| **SKAN Conversion Studio**의 변경 사항 | 3개의 SKAN 기간을 구성하는 새로운 SKAN 4 측정 모드 |
| **대시보드**의 변경 사항 | <ul><li>SKAN 개요 대시보드에는 3개의 SKAN 기간 동안 이벤트 수 및 수익에 대한 새로운 필드(테이블 설정에서 사용 가능)가 포함되어 있습니다.<ul><li>이벤트 수 D0-D2</li><li>이벤트 카운트 D0-D2(모델링됨)</li><li>이벤트 수 D3-D7</li><li>이벤트 수 D8-D35</li><li>수익 D0-D2($)</li><li>수익 D0-D2($)(모델링)</li><li>수익 D3-D7($)</li><li>수익 D8-D35($)</li></ul></li><li>SSOT 대시보드 보기에는 활동 기간 대신 D2 데이터 필드가 표시됩니다. SKAN 3 데이터의 경우, 이 필드에는 기간이 2일보다 길거나 짧더라도 모든 활동 기간 데이터가 표시됩니다.</li></ul> |
| **보고서**의 변경 내용 | <ul><li>SKAdNetwork 리포트에는 SKAN 4를 지원하기 위해 다음과 같은 새로운 필드가 포함됩니다.<ul><li>**skad\_postback\_sequence\_index**: SKAN 3의 경우 값은 0</li><li>**skad\_coarse\_conversion\_value**: SKAN 3의 경우 값은 0</li><li>**skad\_source\_identifier**: SKAN 3의 경우 값은 0</li><li>**skad\_source\_domain**: SKAN 3의 경우 값은 0</li><li>**ad\_network\_creative**: 값은 애드 네트워크에서 수신한 데이터 보강에 기반합니다. SKAN 3의 경우 값은 비어 있습니다.</li></ul></li><li>다음 데이터 락커 및 푸시 API 리포트가 영향을 받습니다.</li></ul><ul><li>**skad\_installs**(데이터 락커 및 푸시 API를 통해)</li><li>skad\_redownloads(데이터 락커 및 푸시 API를 통해)</li><li>skad\_inapps(데이터 락커 및 푸시 API를 통해)</li><li>**skad\_postbacks**(데이터 락커를 통해)</li><li>skad\_postbacks\_copy (ad\_network\_creative 필드를 포함하지 않음)(데이터 락커를 통해)</li><li>샘플 보고서 스키마를 참조하세요.</li></ul><ul><li>SKAN 집계 포스트백 도착 날짜 API 및 SKAN 집약형 성과 리포트 API에는 SKAN 4 필드가 포함되어 있습니다. **참고**: 참고: SKAN 4의 V2 API 토큰 경로를 사용해야 합니다.</li></ul> |