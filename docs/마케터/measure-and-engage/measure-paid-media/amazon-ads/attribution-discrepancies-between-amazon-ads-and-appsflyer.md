---
title: Amazon Ads와 앱스플라이어 간의 어트리뷰션 불일치
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-10-14T10:34:54Z'
  id: 28461159218449
  locale: ko
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/ko/articles/28461159218449
---
> **한눈에 보기:** Amazon Ads와 앱스플라이어의 어트리뷰션 모델 차이점에 대해 알아보세요.

<div id="overview" />

## 개요

모바일 유저 유입 생태계의 두 주요 업체인 Amazon Ads와 앱스플라이어는 서로 다른 어트리뷰션 모델을 사용합니다. 이로 인해 Amazon Ads와 앱스플라이어 대시보드 간에 불일치가 발생할 수 있습니다. Amazon Ads와 긴밀히 협력하여 이러한 불일치를 최소화하고 있지만, 광고주는 잠재적인 원인을 알고 있어야 합니다.

<div id="differences-in-attribution-models" />

## 어트리뷰션 모델의 차이점

아래 표에서는 Amazon Ads와 앱스플라이어 대시보드 간 불일치에 대한 가능한 이유를 설명합니다.

| 1. 일으키다. 2. 발생시키다. | Amazon Ads 관리자 | 앱스플라이어 |
| --- | --- | --- |
| <span id="clickthrough-attribution-lookback-window"></span>클릭-쓰루 어트리뷰션 룩백 윈도우 | 기본 기간은 14일입니다. 현재는 구성할 수 없습니다. | 기본 기간은 7일입니다. 기간은 1&#126;30일 사이에서 구성할 수 있습니다. Amazon Ads 어트리뷰션 기간에 맞춰 설정하세요. |
| <span id="viewthrough-attribution-lookback-window"></span>뷰-쓰루 어트리뷰션 룩백 윈도우 | 기본 기간은 14일입니다. 현재는 구성할 수 없습니다. | 기본 기간은 1일입니다. 기간은 1&#126;30일 사이에서 구성할 수 있습니다. Amazon Ads 어트리뷰션 기간에 맞춰 설정하세요. |
| <span id="multichannel-source-attribution"></span>멀티-채널 소스 어트리뷰션 | Amazon Ads는 다른 매체 소스와 관계없이 인스톨을 자체적으로 어트리뷰션합니다. | 앱스플라이어는 라스트 클릭 어트리뷰션을 사용합니다.  <br /><Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">앱스플라이어 어트리뷰션 모델</Anchor>에 대해 더 보기. |
| <span id="different-timezones"></span>다른 시간대 | Amazon Ads 시간대(날짜 범위 옆에 표시됨)는 조정할 수 없습니다. 광고 계정을 설정할 때 구성되었습니다. | 앱스플라이어의 기본 앱 시간대는 UTC+0입니다. Amazon Ads에 정의된 시간대와 맞추려면 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">앱 설정 페이지</Anchor>에서 앱에 설정된 시간대를 변경하세요. |

## 불일치 줄이기

어트리뷰션 모델에 차이가 있지만, 어떤 경우에는 불일치를 줄일 수 있습니다.

### 클릭-쓰루 및 뷰-쓰루 어트리뷰션

앱스플라이어는 클릭-쓰루 및 뷰-쓰루 어트리뷰션을 모두 지원합니다. Amazon Ads와 앱스플라이어 간의 불일치를 줄이려면 클릭-쓰루 및 뷰-쓰루 룩백 윈도우가 Amazon Ads에서 정의한 윈도우와 일관되게 설정되어 있는지 확인하세요.

> 📄 **예시**
>
> 예를 들어, 귀사의 앱 com.greatapp에 대해 앱스플라이어에서 Amazon Ads 클릭-쓰루 룩백 윈도우가 1일로 설정되어 있고, Amazon Ads에서는 기본값인 7일로 설정되어 있다고 가정해 보겠습니다. Amazon Ads에서 Greatapp의 광고를 클릭한 후 2&#126;7일 사이에 앱을 처음 실행한 사용자는 앱스플라이어에서는 오가닉 사용자로 분류되지만, Amazon Ads에서는 자체적으로 이러한 사용자를 보고합니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01J81NN4J4A1KWBXJQD9SM2AWH=%EA%B0%9C%EC%9A%94 differences-in-attribution-models=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%AA%A8%EB%8D%B8%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90 h_01J81NN4J4WSJBFHBARKTQ9JG5=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%AA%A8%EB%8D%B8%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90 reducing-discrepancies=%EB%B6%88%EC%9D%BC%EC%B9%98-%EC%A4%84%EC%9D%B4%EA%B8%B0 h_01J81NN4J4EJQH47YJF0H5M97G=%EB%B6%88%EC%9D%BC%EC%B9%98-%EC%A4%84%EC%9D%B4%EA%B8%B0 clickthrough-and-viewthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%B0%8F-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01J81NN4J4X6V3XWRZWNDJ14PV=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%B0%8F-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01J81NN4J4NC0SK4QRTQZRJS0F=%EC%98%88%EC%8B%9C" />
