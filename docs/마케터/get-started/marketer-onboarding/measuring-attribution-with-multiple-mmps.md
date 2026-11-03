---
title: 여러 MMP를 사용한 어트리뷰션 측정
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-07-27T08:29:19Z'
  edited_at: '2026-10-14T10:32:55Z'
  id: 17316973509393
  locale: ko
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ko/articles/17316973509393
---
> **한눈에 보기:** 한눈에 보기: 여러 MMP를 동시에 사용할 때 어트리뷰션을 측정할 수 있는 미디어소스를 확인하여 앱스플라이어와 다른 MMP 간의 어트리뷰션 결과를 비교할 수 있습니다.

## 개요

다른 MMP에서 앱스플라이어로 마이그레이션하려는 광고주는 동일한 미디어소스와 캠페인에 대한 두 MMP 측정값을 동시에 비교할 수 있습니다. 이렇게 하려면 다음 요구 사항을 충족해야 합니다.

* 테스트된 앱에는 **두 MMP SDK가 모두 통합**되어 있어야 함
* 미디어소스는 **두 개의 MMP로 어트리뷰션을 지원하도록 구성**되어야 함

그러나 모든 미디어소스가 두 개 이상의 MMP를 사용한 측정을 지원하는 것은 아닙니다.  

## 미디어소스 측정의 세부 사항 및 제한 사항

다음은 여러 MMP를 동시에 사용할 때 미디어소스 측정에 대한 세부 정보와 제한 사항입니다.

### 자체 리포트 네트워크

| SRN | 세부 정보 및 제한 사항 | 측정 지원 |
| --- | --- | --- |
| Apple Search Ads | ASA는 제한 없이 여러 MMP 측정을 지원합니다. 여러 MMP에서 API 호출 요청이 있을 경우 해당 MMP로 데이터가 전송됩니다. | ✓ |
| DV360 (GMP) | 여러 MMP를 사용할 수 있지만, 캠페인 설정에는 각 플러드라이트 추적(링크 ID)에 대해 별도의 광고 항목이 있어야 합니다. | ✓ |
| Google Ads | Google Ads는 다음과 같은 여러 MMP 측정을 지원합니다.<ul><li>광고주는 여러 MMP 링크 ID를 하나의 Google Ads 계정에 연결하고 각 MMP에서 포스트백을 받을 수 있음</li><li>Google Ads는 여러 MMP로부터 포스트백을 수신할 수 있음</li><li>여러 MMP 성능을 측정할 수 있음</li></ul>**참고:** 참고: 데이터가 새 MMP로 유입되면 기존 통합을 중지할 것을 권장합니다. | ✓ |
| Meta Ads | Meta 광고는 여러 MMP로부터 데이터 요청을 받습니다. 그러나 다음과 같은 이유로 MMP를 두 개 이상 사용하지 **않는** 것이 좋습니다.<ul><li>Meta 광고는 이벤트가 아닌 설치에 대해서만 중복 제거를 처리할 수 있습니다. 따라서 이벤트는 하나의 MMP에서만 전송되어야 함</li><li>MMP에서 여러 SDK를 삽입하는 경우 중복 제거 과정에서 문제 및 2차 오류가 발생할 가능성이 매우 높음</li><li>Meta 광고로 전송되는 데이터의 양이 두 배로 늘어나면 최적화 및 측정 시스템에 두 배의 데이터가 입력될 수 있습니다.</li></ul>따라서 여러 MMP 어트리뷰션은 단기적으로만 지원될 수 있습니다. | 제한 있음 |
| 스냅챗 | 스냅챗과 여러 MMP 간에 데이터를 전송할 수 있습니다. 그러나 겹치는 마이그레이션 기간을 최소화하는 것이 좋습니다. 여러 MMP 데이터를 수신할 때 특정 MMP를 선택하여 최적화할 수 있는 옵션은 없습니다. 즉, MMP 모두에 대해 최적화가 수행되며 데이터가 중복될 가능성이 높습니다. | 제한 있음 |
| TikTok for Business | TikTok for Business로 포스트백을 전송하는 것은 하나의 MMP에 대해서만 지원됩니다. 다른 MMP에서 마이그레이션할 때 앱스플라이어가 전환을 TikTok for Business에 어트리뷰션할 수 있도록 하려면 먼저 다른 MMP의 포스트백을 끈 다음 앱스플라이어를 구성해야 합니다. | x |
| X Ads | X Ads는 다중 MMP 연동을 지원하지 않습니다. | x |

### SKAN

### 비-SRN 애드 네트워크

MMP 어트리뷰션 링크는 SRN이 아닌 애드 네트워크에서 사용자의 인게이지먼트를 기록한 후 실제 설치가 되는 인게이지먼트를 어트리뷰션하는 데 사용됩니다. 여러 MMP에 대한 어트리뷰션을 동시에 활성화하려면 애드 네트워크에서 다음 요구 사항을 충족해야 합니다.

| 애드 네트워크 요구사항 | 세부 정보 |
| --- | --- |
| 단일 인게이지먼트에 대한 데이터는 두 MMP에 모두 전송되어야 합니다. | <ul><li>**클릭 수:** 클릭 횟수: 어트리뷰션 링크는 사용자를 앱 스토어로 리디렉션하므로 하나의 어트리뷰션 링크만 사용할 수 있습니다. <Anchor target="_blank" href="/partners/ko/docs/redirecting-users-to-the-app-store#개요">클릭 어트리뷰션 데이터를 앱스플라이어로 전송하는</Anchor> 동안 기존 MMP의 어트리뷰션 링크를 계속 사용하는 것이 좋습니다.</li><li>노출 노출: 노출은 사용자를 앱 스토어로 리디렉션하지 않으므로 애드 네트워크는 두 MMP 모두에 노출 데이터를 전송해야 합니다.</li></ul> |
| 수신된 설치 포스트백은 중복 제거되어야 합니다. | 애드 네트워크는 두 MMP 모두에서 설치 포스트백을 수신합니다. 이중 청구를 방지하려면 애드 네트워크는 이러한 포스트백 중 하나를 중복 제거해야 합니다. |
| 수신된 인앱이벤트 포스트백은 중복 제거되어야 합니다. | 각 MMP가 인앱이벤트 포스트백을 전송하도록 구성된 경우, 애드 네트워크는 두 MMP 모두로부터 인앱이벤트 포스트백을 수신합니다. 이중 어트리뷰션으로 인해 이중 요금이 부과되는 것을 방지하려면 애드 네트워크는 이러한 포스트백 중 하나를 중복 제거해야 합니다. 애드 네트워크가 이중 인앱이벤트 포스트백을 중복 제거할 수 없는 경우, 인앱이벤트 포스트백이 하나의 MMP에만 설정되어 있는지 확인하세요. |

### 소유 매체

비 SRN 애드 네트워크와 마찬가지로 온드 미디어에서 설치를 어트리뷰션하려면 MMP 어트리뷰션 링크를 사용해야 합니다. 그러나 이메일 목록, SMS 또는 QR 코드와 같은 일부 온드 미디어 유형의 경우 MMP는 단일 참여에 대한 데이터를 한 번만 전송할 수 있습니다. 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/convert-your-mobile-web-visitors-to-app-users">모바일 웹-투-앱 어트리뷰션</Anchor> 솔루션을 사용하면 **웹사이트 또는 랜딩 페이지에서 발생하는 설치를 측정할 수 있습니다**. MMP 어트리뷰션을 비교하기 위해 온드 미디어를 사용하는 것의 장점은 인스톨이나 이벤트 중복 제거가 필요하지 않다는 것입니다.

## 어트리뷰션 불일치 방지

* 두 MMP가 동일한 시간대를 사용해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">앱스플라이어에서 앱 시간대를 설정하는</Anchor> 방법은 다음과 같습니다.
* 예를 들어, 두 MMP에서 동일한 룩백 윈도우를 설정할 수 있습니다.
* MMP 대시보드 또는 리포트의 데이터를 비교할 때는 동일한 날짜 범위 및 지역의 트래픽과 같은 동일한 기준을 비교해야 합니다.

<div data-zendesk-anchors="ability-to-measure-with-multiple-mmps=%EA%B0%9C%EC%9A%94 01H7TP9P86DE0J04VHXJYKE3PA=%EA%B0%9C%EC%9A%94 details-and-limitations-of-media-source-measurement=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4-%EC%B8%A1%EC%A0%95%EC%9D%98-%EC%84%B8%EB%B6%80-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01H81ANMGMEKCZCS2FNBY67321=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4-%EC%B8%A1%EC%A0%95%EC%9D%98-%EC%84%B8%EB%B6%80-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD selfreporting-networks=%EC%9E%90%EC%B2%B4-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC 01H81APGNBGCMREZVFXJW9KN6H=%EC%9E%90%EC%B2%B4-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC 01H7TP9P86YQ75N0XFY7EW2JHQ=skan nonsrn-ad-networks=%EB%B9%84-srn-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC 01H7TP9P86TEWC47MZZVQ1965K=%EB%B9%84-srn-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC owned-media=%EC%86%8C%EC%9C%A0-%EB%A7%A4%EC%B2%B4 01H7W2YTXYMAEN403WCHYH8G7W=%EC%86%8C%EC%9C%A0-%EB%A7%A4%EC%B2%B4 avoiding-attribution-discrepancies=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B6%88%EC%9D%BC%EC%B9%98-%EB%B0%A9%EC%A7%80 01H7YVHVW3YY8XY8GHQX1B0WZN=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B6%88%EC%9D%BC%EC%B9%98-%EB%B0%A9%EC%A7%80" />
