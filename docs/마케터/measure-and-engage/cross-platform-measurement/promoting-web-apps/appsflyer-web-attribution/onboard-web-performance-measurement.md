---
title: '[베타] 앱스플라이어 웹 어트리뷰션 온보딩'
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-10-14T10:27:46Z'
  id: 43529798016401
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43529798016401
---
> **한눈에 보기:** 이 가이드의 온보딩 지침에 따라 앱스플라이어 웹 어트리뷰션을 설정하세요. 설정이 완료되면 웹사이트 방문 및 웹 이벤트를 측정하고 이를 마케팅 소스별로 분류할 수 있으며, 웹사이트의 실질적인 성과에 기여하는 요인을 파악하고, 크로스 플랫폼 측정을 지원할 수 있습니다.

## 앱스플라이어 웹 어트리뷰션에 대하여

<Embed title="[베타] 앱스플라이어 웹 어트리뷰션 온보딩" typeOfEmbed="youtube" url="https://www.youtube.com/embed/tJ_LoaQinzY" providerUrl="https://www.youtube.com" />

앱스플라이어 웹 어트리뷰션은 웹사이트에서 발생하는 방문 및 웹 이벤트와 이를 유도한 마케팅 소스를 연결해 줍니다. 즉, 어떤 미디어 소스와 캠페인이 사용자를 사이트로 유입시키고 그들의 다음 행동에 영향을 미치는지 보여주므로, 이를 통해 성과를 측정하고 ROI를 최적화할 수 있습니다.

앱스플라이어에서 웹사이트 방문 및 웹 이벤트 측정을 시작하려면, 아래의 앱스플라이어 웹 어트리뷰션 설정 체크리스트에 있는 온보딩 단계를 따르세요.

## 앱스플라이어 웹 어트리뷰션 설정 체크리스트

아래 표를 사용하여 앱스플라이어에서 웹 방문 및 웹 이벤트 수집을 시작하기 위해 필요한 주요 설정 작업, 담당자, 수행 순서를 확인하십시오.

| 작업 | 필요한 조치 | 어디서 학습할 수 있나요? | 담당자 |
| --- | --- | --- | --- |
| 1. 웹 앱 만들기 | <ol><li>**앱 설정 페이지**로 이동합니다.</li></ol><ul><li>**웹 SDK ID**를 복사하여 개발사에 전달해 주세요.</li><li>리포팅 **시간대와** **통화를** 설정하십시오.</li><li>**제외된** 도메인을 선택하십시오.</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#web">웹 앱 설정 구성</Anchor></li></ul> | 마케터 |
| 2. (선택 사항) 크로스 플랫폼 LTV를 위한 제품 라인 생성 | 크로스 플랫폼 어트리뷰션 및 LTV 사용자 여정 측정을 활성화하려면 제품 라인 엔터티를 생성하고 관련 앱/웹 자산을 연결하거나, 기존 제품 라인에 웹 앱을 추가하십시오. | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/product-line-group-apps-for-cross-platform-attribution">제품 라인 구성</Anchor></li></ul> | 마케터 |
| 3. Web SDK 인스톨 및 구성 | 웹사이트에 앱스플라이어 웹 SDK를 연동하세요. | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/integrate-appsflyer-web-sdk">웹 SDK를 웹사이트에 연동하세요</Anchor></li></ul> | 개발자 |
| 4. 웹 앱 어트리뷰션 설정을 구성합니다. | **앱 설정** 페이지에서 룩백 윈도우 및 유저 유입 이벤트와 같은 웹 앱 어트리뷰션 설정을 구성하세요.   <br />**참고:** 웹 SDK를 웹사이트에 연동한 후에만 커스텀 유저 유입 이벤트를 선택할 수 있습니다. | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings">웹 앱 어트리뷰션 설정 구성</Anchor></li></ul> | 마케터 |
| 5. 앱스플라이어 웹 어트리뷰션용 URL 생성 | 가장 정확하고 세밀한 어트리뷰션 결과를 얻으려면 올바른 어트리뷰션 파라미터를 사용하여 URL을 생성하세요. | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/choose-attribution-parameters-for-landing-page-urls">랜딩 페이지 URL에 대한 어트리뷰션 파라미터 선택</Anchor></li></ul> | 마케터 |
| 6. 지원되는 파트너와의 연동 설정 | 파트너를 활성화하고 해당 파트너에게 전송될 포스트백을 설정하십시오.<br />지원되는 파트너:<ul><li>Google Ads</li><li>Meta ads</li><li>TikTok Ads</li><li>스냅챗 광고</li></ul> | 다음 기능을 사용하여 웹사이트 앱용 웹 캠페인을 생성하세요:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-campaigns-for-website-apps">Meta ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/snapchat-create-web-campaigns-for-website-apps">스냅챗 광고</Anchor></li></ul> | 마케터 |
| 7. 데이터 락커에서 앱스플라이어 웹 어트리뷰션 데이터 내보내기 | 앱스플라이어 웹 어트리뷰션 로데이터 리포트를 위해 **데이터 락커를** 구성하여 BI 및 분석 팀이 웹 여정을 분석할 수 있도록 하십시오. | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/export-web-performance-measurement-report-data-from-data-locker">데이터 락커에서 앱스플라이어 웹 어트리뷰션 데이터 내보내기</Anchor></li></ul> | 마케팅 담당자 / BI 엔지니어 |
| 2. 웹사이트 캠페인 비용 측정<br /><br />**(ROI360 전용)** | 지원되는 자체 보고 네트워크(SRN)에 대해 **‘비용 설정**’에서 웹 앱을 비용 연동 기능에 연결하세요: 구글, Meta(Facebook), 스냅챗, 트위터.  <br />  <br />연결이 완료되면 웹 캠페인의 비용, 클릭 수 및 임프레션 수는 Cost ETL 리포트와 내 대시보드에서 거의 실시간으로 확인하실 수 있습니다.  <br />  <br />**ROI360 고급** 패키지의 경우, Cost ETL 구성 페이지의 포함된 앱 목록에 웹 앱을 추가하십시오.  <br />  <br />**참고:** 어트리뷰션 링크에는 랜딩 페이지 URL에 캠페인 ID가 포함되어야 합니다 | 웹 앱을 비용 연동에 연결하세요:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-campaigns-for-website-apps#웹-비용으로-웹-귀속-데이터-측정하기">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-campaigns-for-website-apps#웹-비용과-연계하여-웹-어트리뷰션-데이터를-측정하세요">Meta ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/snapchat-create-web-campaigns-for-website-apps#웹-비용으로-웹-어트리뷰션-데이터-측정하세요">스냅챗 광고</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">ETL 구축 비용</Anchor></li></ul> | 마케팅 담당자 / BI 엔지니어 |

<div data-zendesk-anchors="about-appsflyer-web-attribution=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KGN43TYPKCQ7H3SRRHHPT387=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC appsflyer-web-attribution-setup-checklist=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01KGN43TYP1EV5KFQ37FC4SM0C=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8" />
