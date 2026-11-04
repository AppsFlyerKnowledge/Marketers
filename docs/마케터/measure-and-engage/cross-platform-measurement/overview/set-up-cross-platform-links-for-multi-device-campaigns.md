---
title: 다중 장치 캠페인을 위한 크로스 플랫폼 링크 설정
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2026-10-14T10:31:05Z'
  id: 6966260647185
  locale: ko
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ko/articles/6966260647185
---
> **요약: 요약: 플랫폼에서 앱 설치를 다른 플랫폼의 광고 조회수로 홍보, 어트리뷰션, 측정하는 방법. 예를 들어 모바일 앱 설치가 CTV 디바이스에서 본 광고에, 게임 콘솔 앱 설치가 모바일 또는 데스크톱(웹)에서 본 광고에, CTV 앱 설치가 모바일 또는 데스크톱(웹)에서 본 광고에 어트리뷰트됩니다.**

## 개요

앱스플라이어 크로스 플랫폼 OneLink 링크(노출 URL)를 사용하면 한 플랫폼의 인스톨을 다른 플랫폼에 표시된 광고 뷰로 어트리뷰션할 수 있습니다. 동일한 가구 내에서 이루어지는 여러 설치는 동일한 크로스 플랫폼 광고 노출에 어트리뷰트될 수 있습니다.

<div id="set-up-cross-platform-partner-integration" />

<div id="create-a-onelink-templatefor-cross-platform-attribution" />

## 크로스 플랫폼 어트리뷰션을 위한 원링크 템플릿을 생성하거나 편집합니다.

단일 템플릿이 여러 플랫폼에서 앱을 지원합니다(즉, 하나의 템플릿이 모든 플랫폼에서 작동합니다).

1. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">크로스 플랫폼 어트리뷰션을 위한</Anchor> 원링크 템플릿을 생성하거나 편집합니다.
2. **크로스 플랫폼 귀속** 섹션에서 **편집 버튼 ->** **크로스 플랫폼 귀속 활성화**를 클릭합니다.
3. 관련 플랫폼 드롭다운에서 관련 앱을 선택합니다. **참고**: 각 앱은 크로스 플랫폼 귀속이 활성화된 하나의 OneLink 템플릿에만 추가될 수 있습니다. [<Image alt="크로스 플랫폼 귀속.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

## 크로스 플랫폼 파트너 통합 설정

크로스 플랫폼 노출 URL을 사용하여 크로스 플랫폼 귀속을 설정하려면 각 대상 앱에 대해 파트너 통합을 구성합니다.

<div id="equal-priority-advanced-setting" />

<div id="step-2-enable-viewthrough-attribution" />

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<div id="note" />

<div id="important-1" />

<div id="important" />

> 🚧 **중요!**
>
> OneLink 템플릿에서 선택한 모든 대상 앱에 대해 아래 단계를 수행하여 파트너 통합을 활성화해야 합니다(위의 [섹션](#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution) 참조). 대상 앱 중 하나에 대해 통합이 비활성화된 경우, 크로스 플랫폼 귀속이 발생하지 않습니다.

<Accordion title="1단계: 파트너 통합의 대상 앱 선택">

1. 앱스플라이어의 측면 메뉴에서 협업 > **활성화된 연동**을 선택하세요.
2. 통합 파트너를 선택하세요.
3. **통합** 탭에서 **앱** 드롭다운 상자에서 대상 앱을 선택합니다.

</Accordion>

<Accordion title="2단계: 뷰-쓰루 어트리뷰션 활성화">

연동 파트너가 링크를 사용하려면 뷰-쓰루 어트리뷰션을 활성화합니다.

1. **연동** 탭에서 뷰-쓰루 어트리뷰션 인스톨을 켭니다.
2. **연동 저장**을 클릭합니다.

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="3단계: 어트리뷰션 링크(크로스 플랫폼 노출 URL)를 만듭니다.">

통합 네트워크를 위한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">귀속 링크</Anchor> (크로스 플랫폼 노출 URL) 생성

1. 앱스플라이어의 사이드 메뉴에서 **콜라보레이트** > 활성 연동을 선택하고 연동 파트너를 선택합니다.
2. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">어트리뷰션 링크</Anchor> 탭에서 OneLink 링크를 생성할 때 OneLink 사용을 선택합니다.
3. 크로스 플랫폼 어트리뷰션을 위해 생성한 OneLink 템플릿을 선택하십시오.
4. **뷰 스루 귀속**으로 스크롤합니다.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. **크로스 플랫폼 어트리뷰션**을 설정합니다. 이것은 노출 귀속 링크에 `af_xplatform=true` 매개변수를 추가하고 링크에 크로스 플랫폼 귀속 기능을 부여합니다. 이 파라미터가 없으면 URL은 동일한 노출에 여러 인스톨을 표시할 수 없는 일반 노출 URL로 작동합니다.
6. **크로스플랫폼 뷰쓰루 어트리뷰션 기여 기간을 설정합니다.** 이렇게 하면 `af_xplatform_vt_lookback`af\_xplatform=trueaf\_xplatform\_vt\_lookback 파라미터가 노출 어트리뷰션 링크에 추가되고 노출에 따른 시간(최대 24시간)이 노출에 어트리뷰트할 수 있는 노출 시간을 나타냅니다.
7. 필요에 따라 추가 귀속 매개변수를 추가합니다. 크로스 플랫폼 앱 캠페인을 식별하는 명명 규칙을 사용합니다. 추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요.추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요.추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요. 샘플 링크:

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. CTV, PC 또는 콘솔 플랫폼에 표시되는 광고 뒤에 배치할 광고 네트워크에 대한 링크를 제공합니다.

> 🚧 **중요!**
>
> 소유 미디어 및 비통합 파트너에 대해 필요에 따라 매개변수를 추가합니다.  추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요.추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요.추가 데이터 및 메트릭에 추가할 수 있는 매개 변수에 대해 자세히 알아보세요.

</Accordion>

<Accordion title="어드밴스드 동일 우선 순위 설정(선택 사항)">

크로스 플랫폼 귀속에서 클릭 및 노출에 **동일 우선 순위**를 선택적으로 할당할 수 있습니다. 이 고급 설정을 사용하면 AppsFlyer가 인상(예: CTV 또는 콘솔)을 클릭과 동일한 귀속 우선 순위를 가진 것으로 처리할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드-우선순위어트리뷰션-워터폴">귀속 방법 우선 순위</Anchor>를 참조하십시오.

**동일한 우선 순위 활성화:**

1. 크로스 플랫폼 설정 섹션에서 **동일한 우선 순위** 체크박스를 선택하십시오.
2. **저장**을 클릭하세요.

> 📘 **참고**
>
> 동일한 우선 순위를 활성화하면 AppsFlyer가 다른 소스보다 자신의 귀속을 우선시할 수 있습니다. 이 설정은 주의해서 사용해야 하며 전체 귀속 전략과 일치하는 경우에만 사용해야 합니다.

</Accordion>

## 애드 네트워크 목록

CTV, PC 및 콘솔 플랫폼에 광고를 표시하고 크로스 플랫폼 속성(예: CTV-투-모바일 앱)을 지원하는 광고 네트워크 목록은 <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">앱스플라이어 파트너 마켓플레이스</Anchor>에서 확인할 수 있습니다. 앱스플라이어 계정에 로그인해야 합니다.

<div id="agency-permissions" />

<div id="cross-platform-attribution-links-in-mobile-devices" />

<div id="ctvto-mobile" />

<div id="ip-masking" />

<div id="reporting" />

<div id="household-attribution" />

<div id="attribution-method" />

<div id="retargeting" />

<div id="attribution-window" />

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<div id="faq" />

<div id="discrepancies" />

<div id="traits-and-limitations" />

## 특징 및 제한 사항

| 특징 | 비고 |
| --- | --- |
| 어트리뷰션 기간 | 1-72시간 사이, 조회 기간 매개변수 `af_xplatform_vt_lookback`(기본값은 24시간)에 따라 다릅니다. |
| 리타겟팅 | <ul><li>리어트리뷰션: 크로스 플랫폼-모바일에서 지원됩니다. 다른 플랫폼에는 해당되지 않습니다.</li><li>리인게이지먼트: 지원되지 않음</li></ul> |
| 어트리뷰션 메서드 | 확률적 모델링을 사용한 뷰-쓰루 어트리뷰션 |
| 가구 어트리뷰션 | 지원됨. 동일한 가구 내에서 이루어지는 여러 설치는 동일한 크로스 플랫폼 광고 노출에 어트리뷰트될 수 있음을 의미합니다. |
| 보고서 | <ul><li>크로스 플랫폼 설치는 일반 앱스플라이어 대시보드와 리포트에서 사용할 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">집약형 데이터</Anchor>대시보드 및 리포트</li><li>로데이터(Raw data) 리포트</li></ul></li><li>크로스 플랫폼 노출 횟수는 앱 수준 대시보드에 표시되지 않습니다. 그러나 데이터 락커를 통해 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports#user-journey">크로스 플랫폼 인게이지먼트 리포트</Anchor>에서 사용할 수 있습니다.</li><li>크로스 플랫폼 캠페인을 쉽게 식별할 수 있는 파라미터 명명 규칙을 사용해야 합니다.</li></ul> |
| IP 차단 | 크로스 플랫폼 인게이지먼트에 대한 IP 마스킹은 앱 수준 특성이므로 지원되지 않습니다. `ip_masking`ip\_maskingip\_masking이 구성된 경우 설치는 크로스 플랫폼 인게이지먼트에 어트리뷰트되지 않습니다. |
| CTV-to-모바일 | CTV에서 모바일로의 귀속 흐름은 크로스 플랫폼 캠페인을 수행할 권한이 있는 [통합 파트너](/docs/set-up-cross-platform-links-for-multi-device-campaigns#list-of-ad-networks)에게만 제공됩니다. |
| 모바일 장치의 크로스 플랫폼 귀속 링크 | 모바일 장치에서 크로스 플랫폼 귀속 링크가 표시될 때, 귀속은 <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>, PC 및 콘솔을 위해 설계된 크로스 플랫폼 귀속 흐름이 아닌 표준 모바일 확률 모델링 논리에 의해 결정됩니다. 결과적으로, 모바일 인상은 진정한 크로스 플랫폼 인상에 대해 제공되는 [동일한 우선 순위](#step-3-enable-equal-priority-for-crossplatform-impressions), [확장된 조회 기간](#attribution-window), 또는 [가구 귀속](#household-attribution)의 자격이 없습니다. |
| 에이전시 권한 | 대행사는 자신의 측에서 "크로스 플랫폼 동일 귀속 우선 순위"를 전환할 수 없습니다. 이 구성은 특정 광고 네트워크에 대한 광고주의 설정에서 직접 복사됩니다. |

## 불일치

앱스플라이어와 tvScientific은 어트리뷰션 모델이 다릅니다. 이로 인해 tvScientific과 앱스플라이어 대시보드 간에 불일치가 발생할 수 있습니다. 아래 표에서 불일치가 발생하는 이유를 참조하십시오.

| 원인 | tvScientific | 앱스플라이어 |
| --- | --- | --- |
| 기준 모델 | 공유 크레딧 어트리뷰션 모델 | 라스트 터치 어트리뷰션 모델 |
| 룩백 윈도우 | 최대 30일 | 최대 72시간 |
| 리타겟팅 | 신규 사용자(설치)와 재사용자(재참여) 모두의 기여 | 신규 사용자(설치)의 어트리뷰션만 |
| 비용 할당 | 비용은 운영 체제에 관계없이 노출에 할당됩니다 | 비용은 iOS 및 안드롤이드용 별도의 시스템에 대한 노출에 할당됩니다 |

## 자주하는 질문

<Accordion title="질문: 확률적 모델링을 통한 뷰 쓰루 어트리뷰션 활성화를 켜야 합니까?">

답변 : 아니요. 앱 설정의 확률적 모델링을 통한 뷰 쓰루 어트리뷰션 활성화 토글은 크로스 플랫폼 뷰 쓰루 어트리뷰션이 작동하도록 켤 필요가 없습니다.

</Accordion>

<Accordion title="대시보드에서 내 크로스 플랫폼 캠페인에 대한 인상을 왜 볼 수 없습니까?">

크로스 플랫폼 노출 횟수는 앱 수준 대시보드에 표시되지 않습니다. 이는 하나의 CTV 인상이 여러 앱에서 여러 전환으로 이어질 수 있으며, 각 앱에 인상을 할당하는 정확한 방법이 없기 때문입니다. <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-data-via-data-locker#report-types-and-availability">데이터 잠금소의 크로스 플랫폼 참여 보고서</Anchor>에서 인상 데이터를 액세스할 수 있습니다.

</Accordion>
