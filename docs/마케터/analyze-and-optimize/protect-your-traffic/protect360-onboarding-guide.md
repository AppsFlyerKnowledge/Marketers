---
title: Protect360 온보딩 가이드
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-10-14T10:28:50Z'
  id: 34554022072209
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/34554022072209
---
> **한눈에 보기:** 단계별 온보딩 가이드에 따라 6주 만에 Protect360의 가치를 극대화하고 마케팅 투자 자산을 신속하고 효과적으로 보호하세요.

<div id="onboarding-timeline-and-what-to-expect" />

## **온보딩 일정 및 기대 사항**

이 가이드는 6주 동안의 단계적 온보딩 접근 방식을 설명합니다:

* **셋업 (1&#126;3주)**: Protect360을 통합하고 검증합니다.
* **최적화 (3&#126;5주)**: 초기 인사이트를 바탕으로 최적화합니다.
* **조정 (5&#126;6주)**: 광고 파트너와 함께 프로드 데이터를 조정합니다.
* **고급 보안 (6주 이상) [선택 사항]**: 고급 프로드 방지 레이어를 활성화합니다.

<div id="about-protect360" />

## **Protect360에 대하여**

Protect360은 광고 사기를 탐지, 방지 및 대응하기 위해 설계된 고급 프로드 방지 솔루션입니다. AI 실행과, 실시간 탐지 기능을 통해 프로드를 차단하고, 낭비되는 지출을 줄이며, 클릭 주입, 가짜 설치 및 봇과 같은 위협으로부터 마케팅을 보호합니다. 검증 규칙 및 프로드 방지 스튜디오와 같은 기능을 통해 정밀한 제어와 완전한 투명성을 제공합니다.

<div id="setup-weeks-1-3" />

<Accordion title="셋업 (1&#126;3주)">

이 단계에서는 인앱 데이터를 AppsFlyer에 전송하고, 프로드 방지를 위한 기본 설정을 구성하며, BI 용어를 앱스플라이어와 얼라인합니다.

**인앱 이벤트 데이터**

인앱 이벤트 데이터를 앱스플라이어에 전송하는 방법은 두 가지가 있습니다: SDK 및 서버-투-서버 (S2S). 차용된 방법에 따라, 추가적 조치가 요구될 수 있습니다.

* **SDK**: 조치가 필요하지 않습니다.
* **서버-투-서버 (S2S)** : 이벤트가 API3을 통해 전송되도록 하십시오. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-upgrading-the-appsflyer-s2s-api">이를 수행하는 방법에 대해 자세히 알아보세요.</Anchor>

<div id="note" />

> 📘 **참고**
>
> 무엇을 사용할지 확실하지 않은 경우에는 개발 또는 마케팅 운영팀에 확인하세요.

<div id="fraud-protection-studio-settings" />

#### **프로드 방지 스튜디오 설정**

프로드 방지 스튜디오는 앱스플라이어의 프로드 방지 솔루션의 다양한 레이어가 미치는 영향과 가치를 평가하는 방법을 제시합니다. 프로드 탐지와 집행 간 차이를 명확하게 구분할 수 있습니다.

이러한 차이와 선택 가능한 옵션을 알고 있다면 현명한 결정을 내릴 수 있습니다:

* **구현됨** (기본 설정): 실시간으로 프로드 활동을 자동으로 차단하거나 이미 설치된 프로드 탐지 시 어트리뷰션 후 프로드로 마킹합니다. 즉각적 프로드 방지가 목적인 경우 이상적인 시스템입니다.
* **태그됨**: 프로드가 탐지되고 태그되지만 어트리뷰션은 유효하기 때문에 자동으로 차단되지 않고 분석 및 검토가 가능합니다. 유연성을 선호하고 구현하기 전 더 깊은 초기 분석을 선호하는 경우 이 옵션을 선택하십시오.

<div id="note-1" />

> 📘 **참고**
>
> 진화하는 비즈니스 목표에 따라서 **구현됨** 모드와 **태그 됨** 모드 간 언제든 전환 (<Anchor target="_blank" href="/marketers/ko/docs/user-management">관리자 권한</Anchor>) 이 가능합니다. 여기서 더 자세히 알아보세요!

<Image align="center" alt="" src="https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png" width="624px" />

팁: 이 단계에서 팀이 Protect360에 익숙해질 때, 프로드 방지 스튜디오 내의 <Anchor target="_blank" href="/marketers/ko/docs/beta-fraud-protection-studio#app-detection-evaluation">**앱 탐지 평가**</Anchor> 카드를 방문하여 주어진 설정을 앱 레벨에서 테스트하고 파악하는 것을 권장합니다.

<div id="data-connection-setup" />

#### **데이터 연결 설정**

Protect360 데이터를 세 가지 방법으로 내보낼 수 있습니다: <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#protect360-로데이터-리포트에-대하여">로데이터 보고서</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#pull-api">Pull API</Anchor>, 또는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#data-locker">데이터 락커</Anchor>. 어떤 방법을 선택하든, 정확한 프로드 데이터 리포팅 및 효과적 분석을 위해서는 데이터 연결을 올바르게 구성하는 것이 중요합니다.

<Image align="center" alt="" src="https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png" width="624px" />

<div id="important" />

> 🚧 **중요!**
>
> Protect360의 가치를 최대로 활용하려면 매달 8일에 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#postattribution-reports">포스트 어트리뷰션 보고서</Anchor>를 추출할 수 있으며, 이를 활용해 파트너와의 조율이 가능합니다.

<div id="how-to-display-hijacked-installs-correctly-in-your-bi" />

#### **하이재킹된 설치를 BI에서 올바르게 표시하는 방법**

시스템 내에서 프로드 방지 데이터의 정밀한 정렬 및 세분화를 위해, **로데이터 보고서, Pull API 또는 데이터 락커를 사용하여 BI 내에서 하이재킹된 설치를 올바르게 볼 수 있습니다.**

<div id="raw-data-report" />

#### 로데이터 보고서

BI에서 하이재킹된 설치를 올바르게 표시하려면:

1. **거부 사유 값** 필드를 찾으십시오.
2. 이 필드는 다음 중 하나로 채워집니다:
   1. 빈 값, 오가닉, 기여자1, 기여자2 등.
3. 각 용어의 의미를 BI 팀에 알려 그들이 해당 용어와 의미를 정렬하도록 합니다.

* 빈 값 - 하이재킹되지 않음
* 오가닉 - 어트리뷰션을 오가닉으로 변경
* 기여자1, 기여자2, 기여자3 등 - 어트리뷰션을 지정된 미디어 소스에 올바르게 지정

<div id="note-2" />

> 📘 **참고**
>
> 데이터에 대해 더 많은 인사이트를 얻으려면 로데이터 보고서 4개를 참고하세요.
>
> * 태그된 설치
> * 태그된 포스트 어트리뷰션 설치
> * 태그된 인앱 이벤트
> * 태그된 포스트 어트리뷰션 인앱 이벤트

<Image align="center" alt="" src="https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png" width="624px" />

#### **Pull API**

BI에서 하이재킹된 설치를 올바르게 표시하려면:

4. **거부 사유 값** 필드를 찾으십시오.
5. 이 필드는 다음 중 하나로 채워집니다:
   1. 빈 값, 오가닉, 기여자1, 기여자2 등.
6. 각 용어의 의미를 BI 팀에 알려 그들이 해당 용어와 의미를 정렬하도록 합니다.

* 빈 값 - 하이재킹되지 않음
* 오가닉 - 어트리뷰션을 오가닉으로 조정
* 기여자1, 기여자2, 기여자3 등 - 어트리뷰션을 지정된 미디어 소스에 올바르게 지정

<div id="data-locker" />

#### **데이터 락커**

BI에서 하이재킹된 설치를 올바르게 표시하려면:

7. **검증\_이유\_값** 필드를 찾으십시오.
8. 이 필드는 다음 중 하나로 채워집니다:
   1. 빈 값, 오가닉, 기여자1, 기여자2 등.
9. 각 용어의 의미를 BI 팀에 알려 그들이 해당 용어와 의미를 정렬하도록 합니다.

* 빈 값 - 하이재킹되지 않음
* 오가닉 - 어트리뷰션을 오가닉으로 조정
* 기여자1, 기여자2, 기여자3 등 - 어트리뷰션을 지정된 미디어 소스에 올바르게 지정

<div id="validation-rules" />

#### **유효성 검증 규칙**

검증 규칙을 사용하여 마케팅 전략에 따라 기존 프로드 방지 시스템에 비즈니스 로직 레이어를 추가할 수 있습니다. 검증 규칙을 사용하면 여러 사용 케이스에 걸쳐진 매개변수를 기반으로 어떤 설치가 유효한지 혹은 유효하지 않은지 정의 내릴 수 있습니다.

고객 성공 관리자 또는 계정 관리자에 연락하여 당신의 분야에 권장되는 모범 사례에 대해 자세히 알아보십시오.

<div id="note-3" />

> 📘 **참고**
>
> 규칙이 최대한 효과적이도록 하려면 UA / 마케팅 / 미디어 구매 전략을 검토하고 어떤 종류의 설치 혹은 앱 이벤트가 전략에 어울리는지를 결정하여 필요에 따라 허용하거나 차단하기를 권장합니다. 예를 들어, 국가 (GEO) X에서 앱을 홍보하지 않는 경우 GEO X에서 출발하는 모든 활동을 자동으로 차단하는 규칙을 만들 수 있습니다. 마케팅 전략에 맞게 보안을 구성하는 여러 개의 규칙 생성이 가능합니다.

<div id="working-with-dashboards" />

#### **대시보드 작업하기**

<Anchor target="_blank" href="/marketers/ko/docs/protect360-dashboard">Protect360 대시보드</Anchor>는 귀하의 프로드 데이터의 시각적 개요를 재공하여 더 깊게 조사할 수 있도록 하고 프로드 탐지 및 귀하의 활동에 미치는 영향을 더 잘 이해할 수 있도록 합니다.

<Image align="center" alt="" src="https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png" width="624px" />

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="최적화 (3-5주)">

<div id="campaign-optimization" />

#### **캠페인 최적화**

이 단계에서는 Protect360에서 최대한의 효과를 얻기 위해 캠페인을 최적화합니다. 이를 위해 다음을 수행해야 합니다:

* [모범 사례를](/docs/protect360-onboarding-guide#모범-활용-사례) 참조하세요.
* [프로드 보호 설정 검토하기](/docs/protect360-onboarding-guide#프로드-방지-설정-검토하기)
* [LVL 설정](/docs/protect360-onboarding-guide#lvl-설정)

<div id="best-practices" />

#### 모범 활용 사례

* 실시간 및 포스트 어트리뷰션 데이터를 결합하여 품질 (유지, 인앱 이벤트 등) 및 프로드 기반으로 캠페인 성과를 평가합니다.
* site\_id 또는 subsite\_id를 기반으로 캠페인을 최적화합니다.
* 파트너 특정 사기 비율 및 유형을 분석합니다.

<div id="review-your-fraud-protection-settings" />

#### 프로드 방지 설정 검토하기

귀하의 [프로드 방지 스튜디오 설정](/docs/protect360-onboarding-guide#프로드-방지-스튜디오-설정)을 검토하여 설정된 목표와 일치하는지 확인하십시오.

<div id="note-4" />

> 📘 **참고**
>
> 설치는 유효한 설치의 하위 항목입니다. Protect360 탐지에 따라 실시간으로 차단하기 위해 **구현된** 모드로 전환하십시오.

#### LVL 설정

구글 스토어에서만 오는 트래픽에 대해 LVL (구글 라이센스 검증 라이브러리)을 설정하십시오. Protect360 클라이언트 전용으로 제공되는 라이선스 검증 라이브러리 (LVL)는 각 설치가 실제로 라이선스가 있는 구글플레이 사용자로부터 오는지 확인하여 보안을 한 층 더 강화합니다.

설치 수준에서 라이선스를 검증함으로써 LVL은 무단 사용을 방지하고, 앱 수익을 보호하며 구글플레이와 앱스플라이어 대시보드 간 더 정교한 정렬을 확보합니다. <Anchor target="_blank" href="/marketers/ko/docs/implement-google-license-verification-library-lvl">더 알아보기</Anchor>

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="조정 (5-6주)">

<div id="fraud-data-reconciliation" />

#### **프로드 데이터 조정**

Protect360 구현 뒤 몇 주간 프로드 탐지 데이터를 축적한 후에는 프로드에 대한 인사이트를 광고 파트너와 공유하고 조정합니다.

이 단계에서는 귀하와 귀하의 파트너가 캠페인 성과, 프로드 탐지 방법 및 정확성에 대해 합치된 의견을 갖는지 확인할 수 있습니다.

귀하의 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide#postattribution-detection">포스트 어트리뷰션 데이터</Anchor>를 다운로드하고 광고 파트너와 긴밀히 협력하여 프로드 메트릭을 교차 참조할 수 있습니다. 이 조정은 불일치를 식별하고, 분쟁을 사전에 해결하며, 투명성을 구축하는 데 도움이 됩니다. 광고 파트너와 함께 프로드 데이터를 조정하는 방법을 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks">여기</Anchor>에서 확인하십시오.

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="고급 보안 설정(6주 이상) [선택 사항]">

<div id="advanced-security-module" />

#### **고급 보안 모듈**

Protect360 클라이언트 전용으로 제공되는 고급 보안 모듈은 트래픽이 많은 앱을 위해 설계되었습니다. 이 모듈은 Android SDK에 중요한 보안 레이어을 추가하여 네트워크 요청을 실시간으로 검증하고 스푸핑 된 설치 및 조작된 트래픽을 차단합니다.

소스에서 무단 신호를 필터링함으로써 앱 스토어 불일치를 줄이고, 어트리뷰션 정확성을 강화하며, 정교한 사이버 프로드로부터 데이터를 보호합니다.

CSM에 문의하거나 `<hello@appsflyer.com>`으로 문의주세요.

</Accordion>

<div data-zendesk-anchors="what-to-expect=%EC%98%A8%EB%B3%B4%EB%94%A9-%EC%9D%BC%EC%A0%95-%EB%B0%8F-%EA%B8%B0%EB%8C%80-%EC%82%AC%ED%95%AD h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=%EC%98%A8%EB%B3%B4%EB%94%A9-%EC%9D%BC%EC%A0%95-%EB%B0%8F-%EA%B8%B0%EB%8C%80-%EC%82%AC%ED%95%AD about-protect360=protect360%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01JSBWNSHDZ8J3B70KYEG2T03X=protect360%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=%EC%B0%B8%EA%B3%A0 fraud-protection-studio-settings=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%84%A4%EC%A0%95 h_01JSY4SNK5X23DBVD374FV12FG=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%8A%A4%ED%8A%9C%EB%94%94%EC%98%A4-%EC%84%A4%EC%A0%95 h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=%EC%B0%B8%EA%B3%A0-1 data-connection-setup=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%97%B0%EA%B2%B0-%EC%84%A4%EC%A0%95 h_01JSY4SNK57K77TBXZB92QPBKA=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%97%B0%EA%B2%B0-%EC%84%A4%EC%A0%95 h_01JVVK5Z1H0TZH02S76M7JRKWQ=%EC%A4%91%EC%9A%94 how-to-display-hijacked-installs-correctly-in-your-bi=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9%EB%90%9C-%EC%84%A4%EC%B9%98%EB%A5%BC-bi%EC%97%90%EC%84%9C-%EC%98%AC%EB%B0%94%EB%A5%B4%EA%B2%8C-%ED%91%9C%EC%8B%9C%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JVVJBVB4FRATEHVZ2Q7EWC54=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9%EB%90%9C-%EC%84%A4%EC%B9%98%EB%A5%BC-bi%EC%97%90%EC%84%9C-%EC%98%AC%EB%B0%94%EB%A5%B4%EA%B2%8C-%ED%91%9C%EC%8B%9C%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 raw-data-report=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C h_01JWDAV3K7JF8ATZP88D4NQRW4=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=%EC%B0%B8%EA%B3%A0-2 h_01JWDAV8GC5N1859AD1PMEQXH9=pull-api data-locker=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4 h_01JWDAVEVDAJD47WQYY0FNSPE9=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4 validation-rules=%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D-%EA%B7%9C%EC%B9%99 h_01JSY4SNK5HAG08PAJQEPB7MQ4=%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D-%EA%B7%9C%EC%B9%99 h_01JVVK5Z1H05XX8BXECMXAJ4J7=%EC%B0%B8%EA%B3%A0-3 working-with-dashboards=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0 h_01JSY4SNK50RHSQ95E1E2ZK068=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0 optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 campaign-optimization=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B5%9C%EC%A0%81%ED%99%94 h_01JV255GGVBY8XGQS28F0QZRVH=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B5%9C%EC%A0%81%ED%99%94 best-practices=%EB%AA%A8%EB%B2%94-%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01JV6WFR7MN2X8KTN7RMTXQ5KX=%EB%AA%A8%EB%B2%94-%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 review-your-fraud-protection-settings=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%84%A4%EC%A0%95-%EA%B2%80%ED%86%A0%ED%95%98%EA%B8%B0 h_01JV6WGDRP200GHN6MJNZJ5MQE=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%B0%A9%EC%A7%80-%EC%84%A4%EC%A0%95-%EA%B2%80%ED%86%A0%ED%95%98%EA%B8%B0 h_01JVVK5Z1HXPM2G6HAMTYV7MY5=%EC%B0%B8%EA%B3%A0-4 set-up-lvl=lvl-%EC%84%A4%EC%A0%95 h_01JV6WGGKTV1GNN9K49YXEYY65=lvl-%EC%84%A4%EC%A0%95 reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 fraud-data-reconciliation=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%EC%A0%95 h_01JV25RP3VAJBCEWWK2TEZFKB2=%ED%94%84%EB%A1%9C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A1%B0%EC%A0%95 advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional advanced-security-module=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88 h_01JV260Y9M3M6CC48854YHQ01S=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88" />
