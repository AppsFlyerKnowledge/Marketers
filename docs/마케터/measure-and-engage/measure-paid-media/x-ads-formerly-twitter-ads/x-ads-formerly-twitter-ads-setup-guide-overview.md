---
title: X Ads(이전의 Twitter Ads) 설정 가이드—개요
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-10-14T10:30:19Z'
  id: 4410464316049
  locale: ko
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ko/articles/4410464316049
---
> **한눈에 보기:** **요약:** X Ads 계정을 앱스플라이어와 연동하는 방법을 알아봅니다.

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## X Ads 모바일 앱 프로모션

X Ads 모바일 앱 프로모션은 트위터에 앱을 프로모션하는 방식입니다. 광고주가 효과적 앱 카드 디자인으로 모바일 앱을 홍보하여 인스톨, 앱 참여도 및 딥 링크를 유도할 수 있도록 지원합니다. 앱 유저는 X Ads 타임라인에서 바로 앱을 설치하고 쉽게 사용할 수 있습니다.

## X Ads 사용자 개인정보 보호

X Ads 사용자는 광고주와 정보를 공유하는 방법을 제어할 수 있습니다.

* 유저 설정이 광고주와 인게이지먼트 정보를 공유하지 못하도록 설정된 경우, X Ads 기반 인스톨 및 인앱이벤트는 로데이터에서 제외되지만 여전히 X Ads에 어트리뷰션됩니다.
* 집계된 어트리뷰션 데이터는 앱스플라이어에 정확히 반영되며 X Ads 정책의 영향을 받지 않습니다.
* 결과적으로 X Ads 집계 데이터와 로데이터 리포트는 서로 연관성이 없습니다.

2021년 7월 31일부터 X Ads 고급 모바일 측정(AMM) 프로그램에 참여하지 않는 광고주는 X Ads MACT 사용자 수준 데이터를 더 이상 수신하지 못하게 됩니다.

광고주는 AMM 프로그램을 통해 X Ads가 오로지 측정 목적으로만 데이터를 사용함을 확인하기 위한 감사 권한을 부여한 후에, 보다 완전한 사용자 수준 데이터를 수신할 수 있습니다. 이는 적용 가능한 데이터 보호 법률 및 업계 전반의 일반적인 관행과 일치합니다.  
**AMM 프로그램에 가입하려면:** ads.twitter.com/help > **모바일 앱, 전환 추적 & 오디언스 관리자,** 그리고 **고급 모바일 측정 프로그램 계약 양식**을 클릭하세요.

AMM 프로그램에 가입하기 전에 수신된 사용자 수준 데이터는 내보낼 수 없습니다.

자세한 정보는 X Ads 계정 관리자에게 문의하십시오.

## X Ads 및 앱스플라이어 SKAN 상호 운용성

X Ads는 전용 API를 통해 SKAdNetwork 포스트백 데이터를 전송합니다. X Ads의 SKAN 데이터가 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN 대시보드</Anchor>에 표시됩니다.

X Ads는 다음과 같은 데이터 필드를 사용하여 SKAN 포스트백을 풍부하게 합니다.

* 캠페인 이름
* 캠페인 ID
* Adset 이름
* Adset ID

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=x-ads-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98 h_01H9QR6TH7M0H5YMXRWVVAYRK9=x-ads-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98 twitter-user-privacy=x-ads-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01H9QR6TH74R50K00H7FYN61KC=x-ads-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 twitter-ads-and-appsflyer-skan-interoperation=x-ads-%EB%B0%8F-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1 h_01H9QR6TH74PKBGM5RC4M118GE=x-ads-%EB%B0%8F-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1" />
