---
title: TikTok for Business와 앱스플라이어 간의 어트리뷰션 불일치
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-10-14T10:33:34Z'
  id: 19733501619473
  locale: ko
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ko/articles/19733501619473
---
> **한눈에 보기:** TikTok for Business와 앱스플라이어의 어트리뷰션 모델 차이점에 대해 알아보세요.

<div id="overview" />

## 개요

모바일 유저 유입 생태계의 두 주요 업체인 TikTok for Business와 앱스플라이어는 서로 다른 어트리뷰션 모델을 사용합니다. 이로 인해 TikTok for Business와 앱스플라이어 대시보드 간에 불일치가 발생할 수 있습니다. TikTok for Business와 긴밀히 협력하여 이러한 불일치를 최소화하고 있지만, 광고주는 잠재적인 1. 일으키다. 2. 발생시키다. 원인을 이해해야 합니다.

<div id="differences-in-attribution-models" />

## 어트리뷰션 모델의 차이점

아래 표에서는 TikTok 광고 관리자와 앱스플라이어 대시보드 간 불일치의 가능한 이유를 설명합니다.

<table><thead><tr><th>1. 일으키다. 2. 발생시키다.</th><th>TikTok 광고 관리자</th><th>앱스플라이어</th></tr></thead><tbody><tr><td><p><strong>클릭-쓰루 어트리뷰션 룩백 윈도우</strong></p></td><td><p>기본 기간은 7일입니다. 하지만 안드로이드 앱과 TikTok의 자체 어트리뷰션(TikTok—SRN)으로 전환된 앱의 경우 이를 다르게 구성할 수 있습니다.</p></td><td><p>기본 기간은 7일입니다. 기간은 1&#126;30일 사이에서 구성할 수 있습니다. TikTok 어트리뷰션 기간에 맞춰 설정하세요.</p></td></tr><tr><td><p><strong>뷰-쓰루 어트리뷰션 룩백 윈도우</strong></p></td><td><p>기본 기간은 1일입니다. 하지만 안드로이드 앱과 TikTok의 자체 어트리뷰션(TikTok—SRN)으로 전환된 앱의 경우 이를 다르게 구성할 수 있습니다.</p></td><td><p>기본 기간은 1일입니다. 기간은 1&#126;48시간 사이에서 구성할 수 있습니다. TikTok 어트리뷰션 기간에 맞춰 설정하세요.</p></td></tr><tr><td><p><strong>멀티 채널 소스 어트리뷰션</strong></p></td><td><p>TikTok은 다른 매체 소스와 관계없이 인스톨을 자체적으로 어트리뷰션합니다.</p></td><td><p>앱스플라이어는 라스트 클릭 어트리뷰션을 사용합니다(앱스플라이어의 어트리뷰션 모델<a href="./appsflyer-attribution-model" target="_blank">에 대해 자세히 알아보세요</a>).</p></td></tr><tr><td><p><strong>크로스 디바이스 어트리뷰션</strong></p></td><td><p>TikTok은 사용자들이 iOS, 안드로이드, 데스크톱 등 다양한 디바이스를 사용해 인게이지먼트와 인스톨을 모두 수행하는 것으로 어트리뷰션합니다.</p></td><td><p>앱스플라이어는 동일한 디바이스에서 인게이지먼트와 인스톨을 모두 수행한 사용자를 어트리뷰션합니다.</p></td></tr><tr><td><p><strong>다른 시간대</strong></p></td><td><p><a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">TikTok의 시간대</a>(날짜 범위 옆에 표시됨)는 조정할 수 없습니다. 광고 계정을 생성할 때 구성되었습니다.</p></td><td><p>앱스플라이어의 기본 앱 시간대는 UTC+0입니다. TikTok 이벤트 관리자에 정의된 시간대와 일치하려면 <a href="./app-settings#localization-time-zone" target="_blank">앱 설정 페이지</a>에서 앱의 시간대를 변경하세요.</p></td></tr><tr><td><p><strong>iOS 어트리뷰션</strong></p></td><td><p>iOS 앱의 경우 TikTok 광고 관리자는 SKAN 어트리뷰션 결과만 표시합니다.</p></td><td><p>iOS 앱의 경우, 앱스플라이어는 SRN 및 고급 SRN에 대한 앱스플라이어 어트리뷰션과 중복이 제거된 SSOT 데이터를 함께 SKAN 어트리뷰션 결과를 표시합니다. 양 플랫폼에서 SKAN 데이터만 일치할 것으로 예상됩니다. </p></td></tr><tr><td><p><strong>인앱 이벤트 어트리뷰션 기간</strong></p></td><td colspan="2"><p>각 플랫폼의 어트리뷰션은 초기 인스톨 이후의 기간에 따라 다를 수 있습니다.</p></td></tr><tr><td><p>1일 차-90일 차</p></td><td colspan="2"><p>어트리뷰션 데이터 격차가 없습니다. 양 플랫폼 모두 인앱 이벤트를 인스톨 시점에 어트리뷰션합니다.</p></td></tr><tr><td><p>91일 차-180일 차</p></td><td rowspan="2"><p>90일이 지나면, TikTok에서는 인앱 이벤트가 보고되지 않습니다.</p></td><td><div><div><div>앱스플라이어는 인앱 이벤트를 인스톨 시점에 어트리뷰션합니다.</div></div></div></td></tr><tr><td><p>180일차 이후</p></td><td><div><div><div> <a href="./user-level-data-retention#파트너-데이터-리텐션-기간" target="_blank">TikTok의 데이터 리텐션 정책</a>에 따라 인앱 이벤트는 오가닉으로 간주됩니다.</div></div></div></td></tr></tbody></table>

<div id="differences-in-installs" />

## 인스톨의 차이점

경우에 따라 TikTok for Business에서는 앱스플라이어가 거부하거나 새로운 인스톨로 간주하지 않는 인스톨을 포함할 수 있습니다.

<div id="re-engagement-campaigns" />

### 리인게이지먼트 캠페인

리인게이지먼트 캠페인은 사용자가 이미 설치된 앱을 열게 할 수 있습니다(**리인게이지먼트**). 앱스플라이어가 동일 디바이스에 이전에 설치된 앱을 인식할 경우, 이는 **리어트리뷰션**으로 간주됩니다.

사용자가 TikTok for Business 리인게이지먼트 캠페인을 통해 처음으로 앱을 설치하면, **새로운 유저 유입 인스톨**로 앱스플라이어에 기록됩니다. 또한, 사용자가 초기 인스톨 후 지정된 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor> 가 지난 후 앱을 설치하는 경우에도 새로운 유입으로 간주됩니다.

반면, 원래 설치 후 설정된 리어트리뷰션 윈도우 내 **발생하는 설치는 리어트리뷰션으로 분류됩니다.** 이러한 설치는 앱스플라이어 리타겟팅 페이지에서 확인할 수 있습니다. 하지만 TikTok for Business에서는 이를 새로운 설치로 간주할 수 있습니다.

<div id="rejected-installs-when-using-validation-rules-and-protect360" />

### 유효성 검증 규칙 및 Protect360 사용 시 거부된 설치

<Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">유효성 검증 규칙</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360</Anchor>은 특정 설치를 거부(차단)하여 보호 기능을 추가하는 앱스플라이어 기능입니다. 이 기능을 사용할 경우, TikTok for Business에서 발생한 거부된 설치는 앱스플라이어에 의해 차단되며, TikTok for Business는 이러한 설치를 자체 보고합니다.

<div id="example" />

> 📄 **예시**
>
> GreatApp의 UA 매니저 제프는 북미의 스페인어 사용자만을 타겟으로 하는 SPNA 캠페인을 만듭니다. 이를 검증하기 위해 제프는 캐나다와 미국 사용자만 수용하는 검증 규칙을 정의합니다.
> 스페인에 있는 TikTok for Business 유저가 앱을 클릭해 인스톨 하면, TikTok for Business에서는 인스톨 을 자체 보고하지만 앱스플라이어는 유효성 검증 규칙을 통과하지 못한 인스톨 을 거부합니다.

<div id="reducing-discrepancies" />

## 불일치 줄이기

어트리뷰션 모델에 차이가 있지만, 어떤 경우에는 불일치를 줄일 수 있습니다.

<div id="click-through-and-view-through-attribution" />

### 클릭-쓰루 및 뷰-쓰루 어트리뷰션

앱스플라이어는 클릭-쓰루와 뷰-쓰루(view-through) 어트리뷰션을 모두 지원합니다. TikTok for Business와 앱스플라이어 간 불일치를 줄이려면, 클릭-쓰루 및 뷰-쓰루(view-through) 룩백 윈도우가 TikTok for Business에서 정의된 것과 일치하는지 확인하세요.

<div id="example-1" />

> 📄 **예시**
>
> 예를 들어, 앱스플라이어에서 TikTok for Business의 클릭-쓰루 룩백 윈도우를 귀사의 앱 `com.greatapp`에 대해 1일로 설정했지만, TikTok for Business에서는 기본값인 7일로 설정되었다고 가정해 보세요. TikTok에서 Greatapp 광고를 클릭한 후 2&#126;7일 후에 처음 앱을 실행하는 유저는 앱스플라이어에서는 오가닉 사용자로, TikTok for Business에서는 자체 보고됩니다.

<div id="in-app-event-attribution" />

### 인앱 이벤트 어트리뷰션

플랫폼 간 차이는 앱 설치 후 이벤트(예: 인앱 구매)가 TikTok for Business와 앱스플라이어에 다르게 표시될 때도 있습니다. 다음 표에서 이러한 차이의 가장 일반적인 이유와 이를 줄이는 방법에 대한 조언을 제공합니다.

| 1. 일으키다. 2. 발생시키다. | 설명 | 앱스플라이어 팁 |
| --- | --- | --- |
| **자기 어트리뷰션** | TikTok은 인스톨과 이벤트를 항상 자사 캠페인에 어트리뷰션하는 반면, 앱스플라이어는 이를 유입 소스에 어트리뷰션합니다. 이러한 이벤트는 앱스플라이어에서 TikTok 보조로 표시됩니다. | TikTok의 어트리뷰션 전환 로데이터와 TikTok이 기여한 로데이터를 결합하세요. |
| **매핑되지 않은 이벤트** | 앱스플라이어는 SDK 발생 이벤트를 받지만, TikTok for Business에 매핑되지 않아 전송되지 않습니다. | 사용자 의 품질을 나타내는 인앱 이벤트 를 TikTok for Business와 <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#인앱-이벤트-포스트백">매핑</Anchor>하세요. |
| **전송되지 않은 수익** | 앱스플라이어는 SDK에서 발생한 이벤트의 수익을 얻지만, 그 수익은 TikTok for Business로 전송되지 않습니다. | TikTok for Business 인앱 이벤트를 <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#인앱-이벤트-포스트백">매핑할 때</Anchor> 수익을 반드시 포함하세요. |
| **TikTok for Business에서 누락된 이벤트 값** | 앱스플라이어는 올바른 구조를 갖춘 경우, 이벤트 매핑의 일환으로 TikTok for Business에 파라미터와 값을 전송합니다. | <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure">앱스플라이어가 권장하는 구조</Anchor>에 따라 귀사의 SDK 인앱 이벤트를 구축하여 TikTok for Business와 이벤트 값을 완벽하게 매핑하세요. |