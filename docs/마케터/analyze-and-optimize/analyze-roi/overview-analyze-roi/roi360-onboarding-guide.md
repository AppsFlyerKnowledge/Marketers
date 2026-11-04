---
title: ROI360- 온보딩 가이드
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-10-14T10:40:03Z'
  id: 25301111725329
  locale: ko
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/ko/articles/25301111725329
---
> **한눈에 보기**: 이 글의 온보딩 지침에 따라 ROI360의 비용 및 수익 데이터를 설정하여 운영하세요.

![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

<div id="about-roi360" />

## ROI360 소개

ROI360은 가장 정확한 최신 데이터를 제공하는 고유한 비용 및 수익 리포트 도구 모음입니다. 비용과 수익 인사이트를 결합하면 광고비 지출 수익(ROAS)과 투자 수익(ROI)을 완벽하게 파악할 수 있으며, 그에 따라 최적화 및 개선이 가능합니다.

아래의 온보딩 지침에 따라 비용, 광고 수익, 수익(인앱 구매 및 구독 수익) 보고를 위한 ROI360 도구를 설정하고 실행하세요. 온보딩은 마케터, 앱 개발자, BI 개발자가 완료해야 합니다.

**팁**! 빠르게 온보딩하려면 하나의 앱을 우선으로 설정하고, ROI360이 작동되도록 모든 단계를 완료하세요. 비용, 광고 수익, 인앱 구매 및 구독 수익에 집중할 수 있으나, 먼저 하나의 앱에 대한 온보딩을 완료하세요.

<div id="cost-onboarding" />

<Accordion title="비용 온보딩">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

ROI360 비용 솔루션으로 매일 여러 번 업데이트되는 상세한 비용 및 ROI 인사이트를 얻을 수 있습니다. 이를 통해 애드 네트워크, 온드 미디어, 에이전시 등 무엇을 사용하든 다양한 미디어소스(애드 네트워크), 캠페인, 지역에 걸쳐 캠페인 비용을 효과적으로 관리하고 예산 할당을 확인할 수 있습니다.

비용 온보딩을 완료하면 다음과 같이 할 수 있습니다.

* 모든 미디어소스에서 자동으로 통합되어 캠페인 비용에 대한 포괄적이고 업데이트된 개요를 확인할 수 있습니다.
* 설치 후 업데이트된 가장 정확한 비용 데이터를 기반으로 데이터를 분석하세요.
* ROI360 Advanced 사용자의 경우, 하루에 최대 4번까지 자세한 비용 데이터를 BI 시스템으로 스트리밍할 수 있습니다.
* 에이전시 수수료를 관리하고 전체 캠페인 비용을 정확하게 측정하여 재무 감독과 투명성을 확보할 수 있습니다.

| 작업 | 목적 | 필요한 조치 | 담당자 |
| --- | --- | --- | --- |
| 협력하는 모든 광고 네트워크의 비용 API 연동을 설정하세요. | 가장 세밀한 수준에서 어트리뷰션과 연결된 모든 소스의 비용 데이터를 얻을 수 있습니다. | 앱스플라이어 UI에서 각 광고 네트워크에 대해 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">비용 API 활성화</Anchor>를 실행하세요. **참고**: 연동하기 전에 각 광고 네트워크의 인증 정보 및 로그인 정보를 준비해야 합니다. | 마케터 |
| 비용 ETL 리포트를 설정합니다. (ROI360 Advanced 구독자만 사용 가능) | 미디어 소스별로 최상의 세부 정보로 캠페인 비용 데이터를 확인하세요. 하루 최대 4번 업데이트됩니다. | <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>에 대한 비용 ETL 보고서를 설정하세요. | 마케터/BI 개발자 |
| 비용 가져오기를 통해 비용 데이터를 업로드합니다. | 비용 데이터 가져오기:<ul><li>API 또는 클릭을 통해 비용을 보고하지 않는 애드 네트워크의 경우.</li><li>인플루언서 등을 이용한 광고에 원링크 링크를 사용하는 경우</li><li>비용 데이터를 수정해야 하는 경우</li></ul> | <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 가져오기</Anchor>를 활용해 비용 데이터 파일을 업로드하거나 이메일로 전송하세요. | 마케터 |
| 에이전시 수수료를 구성합니다. | 대행사를 이용하는 경우, 트래픽에 대한 대행사의 수수료 비율을 포함한 총 캠페인 비용을 확인하세요. | 협력하는 각 에이전시에 대한 <Anchor target="_blank" href="/marketers/ko/docs/incorporate-agency-fees-into-campaign-costs">에이전시 수수료 규칙</Anchor>을 만드세요. | 마케터 |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="광고 수익 온보딩">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

ROI360 광고 수익 솔루션으로 매일 여러 번 업데이트되는 귀중하고 세밀한 광고 수익 데이터를 받아볼 수 있습니다.

미디에이션 플랫폼 또는 협력하는 수익화 네트워크에 연결하고, 광고 수익 노출 수준 SDK API를 구현하며, UA 파트너와 데이터를 공유하는 일련의 광고 수익 온보딩을 완료하면 다음과 같은 작업을 수행할 수 있습니다.

* 모든 앱스플라이어 대시보드와 리포트에서 정확하고 새로운 광고 수익 데이터를 확인할 수 있습니다.
* 필요에 따라 세밀한 최신 데이터를 BI 시스템으로 스트리밍할 수 있습니다.
* UA 네트워크가 광고 수익 지표를 기반으로 최적화하여 캠페인 성과를 향상시킬 수 있습니다.

| 작업 | 목적 | 필요한 조치 | 담당자 |
| --- | --- | --- | --- |
| 광고 수익 어트리뷰션 연동 유형을 결정합니다. | 각 연동 유형의 이점을 이해하고 비즈니스 요구 사항에 가장 적합한 연동 유형을 결정합니다. | 다양한 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">광고 수익 연동 유형</Anchor>에 대해 알아보고 1가지를 선택하세요. | 마케터 |
| 함께 협력하는 모든 광고 수익 미디에이션 및 수익화 네트워크에 연결합니다. | 미디에이션 또는 수익화 네트워크에서 광고 수익 데이터를 가져옵니다. | 앱스플라이어 UI에서 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">광고 수익 통합을 연결</Anchor>하세요. | 마케터 |
| 노출 수준 광고 수익 SDK API를 구현하세요. | <ul><li>SDK 수준 연동 유형과 관련이 있습니다.</li><li>거의 실시간의 데이터 신선도로 광고 수익 데이터를 활용하세요.</li></ul> | <ol><li><Anchor target="_blank" href="/marketers/ko/docs/integrate-the-roi360-ad-revenue-sdk-api">ROI360 앱스플라이어 광고 수익 SDK API</Anchor>를 통합하세요.</li><li>SKAN 대시보드에서 광고 수익 데이터를 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetwork 서버 간 지원</Anchor>을 켜세요.</li></ol> | 개발자/마케터 |
| UA 파트너와 광고 수익 데이터를 공유하세요. | UA 광고 네트워크는 광고 수익 데이터를 활용하여 UA 캠페인을 최적화할 수 있습니다. | <ol><li><Anchor target="_blank" href="/marketers/ko/docs/share-ad-revenue-data-with-partners#ua-파트너와-광고-수익-데이터-공유하기">UA 파트너와 광고 수익 데이터를 공유하는 2가지 방법</Anchor>에 대해 알아보세요.</li><li><Anchor target="_blank" href="/marketers/ko/docs/share-ad-revenue-data-with-partners#절차">선택한 방법</Anchor>을 구현하세요.</li></ol> | 마케터 |
| 수익 ETL 리포트를 설정합니다. (ROI360 Advanced 구독자만 사용 가능) | 매일 여러 번 업데이트되는 최상의 세부 정보로 BI에서 광고 수익 데이터를 스트리밍하고 확인할 수 있습니다. | <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports">광고 수익 ETL 보고서</Anchor>를 설정하세요. | 마케터/BI 개발자 |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="인앱 구매 및 구독 수익 온보딩">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

ROI360 수익 솔루션을 사용하면 수익원을 선제적으로 제어할 수 있습니다.

수익 온보딩을 완료하고, 스토어 알림 설정 및 Android와 iOS용 구매 SDK API 구현을 포함한 작업을 마치면 다음의 작업을 수행할 수 있습니다.

* 앱 스토어 및 구글 플레이 거래에 대한 자동 유효성 검증 및 측정을 설정합니다.
* 추가적인 개발자 노력이 필요 없는 원활하고 정확한 수익 보고를 즐기세요. ROI360에서 모든 인앱 수익 이벤트를 처리해 드립니다.
* 정확한 수익 측정을 통해 포트폴리오 전반의 전략적 성장 이니셔티브를 효과적으로 관리하세요.

| 작업 | 목적 | 필요한 조치 | 담당자 |
| --- | --- | --- | --- |
| ROI360 인앱 구매 및 구독 수익 솔루션을 구현합니다. | 앱 스토어(iOS) 또는 구글 플레이(안드로이드)를 통해 유입되는 인앱 구매, 자동 갱신 구독, 관련 이벤트의 수익을 자동으로 검증하고 측정합니다. | 다음 지침에 따라 작업을 수행하세요.<ol><li>인앱 구매(IAP) 및 구독 수익 측정</li><li>SDK 커넥터를 사용한 앱 버전 출시</li></ol> | 개발자/마케터 |
| 수익 ETL 리포트를 설정합니다. (ROI360 Advanced 구독자만 사용 가능) | 하루에 여러 번 업데이트되는 최상의 세부 수준으로 BI에서 수익 데이터를 스트리밍하고 확인하세요. | <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports">수익 ETL 보고서</Anchor>를 설정하세요. | 마케터/BI 개발자 |

</Accordion>

<div data-zendesk-anchors="overview=roi360-%EC%86%8C%EA%B0%9C h_01HKHGX9JJQQCKF9SDZRSCM1XJ=roi360-%EC%86%8C%EA%B0%9C h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
