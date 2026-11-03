---
title: '[베타] 사용자 기반 크로스 플랫폼 재참여 귀속'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2026-04-05T12:40:10Z'
  edited_at: '2026-10-14T10:27:42Z'
  id: 45444294953361
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/45444294953361
---
> **한눈에 보기:** 크로스 플랫폼 재참여 귀속이 기존 사용자를 귀하의 제품으로 다시 데려오는 미디어 소스에 어떻게 크레딧을 부여하는지 알아보세요.

## 크로스 플랫폼 재참여 귀속에 대하여

크로스 플랫폼 재참여 귀속은 최신 광고 참여를 기반으로 사용자 집단을 측정하는 것을 포함하여 <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-attribution">사용자 기반 크로스 플랫폼 귀속</Anchor> 모델을 확장합니다.

크로스 플랫폼 사용자 획득 귀속에서는 주어진 사용자에 대한 모든 활동이 첫 번째 전환을 유도한 원래 미디어 소스에 크레딧이 부여되며, 지속적인 고객 사용자 ID(CUID)를 사용하여 장치와 플랫폼 간의 이벤트를 연결합니다. 이것은 각 사용자의 여정에 대한 통합된 뷰를 제공합니다. 여정이 어디에서 발생하든 상관없이 말입니다.

크로스 플랫폼 재참여 귀속은 이 모델에 레이어를 추가합니다. 항상 원래 획득 소스에 크레딧을 부여하는 대신, 비활동 기간 후 기존 사용자를 귀하의 제품으로 다시 데려오는 미디어 소스에도 크레딧을 부여합니다. 이것은 귀하의 캠페인이 실행된 장치나 플랫폼뿐만 아니라 전체 제품 라인에 걸쳐 진정한 영향을 측정할 수 있게 해줍니다.

다음은 두 모델 간의 관계입니다:

|  | 크로스 플랫폼 사용자 획득 귀속 | 크로스 플랫폼 재참여 귀속 |
| --- | --- | --- |
| **측정하는 것** | 첫 번째 전환 및 이후 모든 활동 | 비활동 후 기존 사용자의 재활성화 |
| **크레딧이 부여되는 곳** | 원래 획득 소스 | 재참여 미디어 소스(예: 메타) |
| **Scope** | 비활동 복원 창 내의 모든 이벤트 | 재참여 창 내의 이벤트만 |
| **설정** | 제품 라인 수준에서 구성됨 | 사용자 획득 설정 위에 구성된 옵트인 |

재참여 귀속은 사용자 획득과 함께 작동하므로, 사용자를 처음 획득한 소스와 그들을 다시 데려온 소스를 동일한 보고 뷰에서 모두 볼 수 있습니다.

## 재참여 귀속은 어떻게 작동합니까?

인앱 이벤트가 재참여 미디어 소스에 귀속되기 위해서는 다음 모든 조건이 충족되어야 합니다:

* **크로스 플랫폼 재참여가 활성화되었습니다:** 재참여 귀속은 귀하의 AppsFlyer 설정에서 제품 라인에 대해 활성화되어야 합니다.
* **CUID가 존재합니다:** 이벤트에는 동일한 제품 라인에서 이전에 본 CUID와 일치하는 유효한 고객 사용자 ID(CUID)가 포함되어야 합니다. 이것이 AppsFlyer가 사용자를 새로운 사용자 대신 돌아온 사용자로 식별하는 방법입니다.
* **리타게팅 비활성화 창이 경과했습니다:** CUID는 마지막 출현 이후 재참여를 위한 비활성화 창의 기간 동안 최소한 한 번도 보이지 않아야 합니다. 이 창 내에서 이벤트가 발생하면 재참여로 간주되지 않으며, 원래 획득 소스에 귀속됩니다.
* **이벤트가 재참여 창 내에서 발생합니다:** 자격을 갖춘 재참여 귀속이 감지되면 재참여 창이 열립니다. 이 창 내에서 발생하는 인앱 이벤트만 재참여 미디어 소스에 귀속됩니다. 창이 닫힌 후 발생하는 이벤트는 원래 획득 소스에 귀속됩니다.

## 크로스 플랫폼 재참여 사용자 여정 예시

다음 예시는 동일한 사용자 여정을 두 번 보여줍니다: 첫 번째는 크로스 플랫폼 재참여 없이, 두 번째는 재참여가 옵트인된 상태입니다. 두 가지를 비교하면 재참여가 귀속을 어떻게 변화시키는지 정확히 보여줍니다.

<div id="user-journey-without-re-engagement" />

<Accordion title="재참여 없는 사용자 여정">

세 플랫폼에서의 사용자 여정을 고려하십시오. 구글 광고가 사용자를 모바일 앱 설치로 유도하며, 여기서 고객 사용자 ID를 사용하여 가입합니다. 이후 메타 광고가 동일한 사용자를 웹 플랫폼으로 유도하며, 여기서 동일한 고객 사용자 ID로 로그인합니다. 로그인 후, 사용자는 모바일에서 두 번의 구매를 합니다: $100과 $50입니다.

[![](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)

이 시나리오에서는 재참여가 활성화되지 않았기 때문에 모든 활동은 원래의 획득 출처인 구글 광고에 귀속됩니다. $100 및 $50 구매와 두 플랫폼 활성화(모바일 및 웹)는 모두 구글에 귀속됩니다. 메타는 웹 설치를 유도했음에도 불구하고 크로스 플랫폼 귀속 내에서 어떠한 크레딧도 받지 않습니다.

| 미디어 소스 | 총 어트리뷰션 | 사용자 획득 | 리인게이지먼트 | 플랫폼 활성화까지 | 모바일 | 웹 | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 2 | 1 | 1 | $150 |
| Meta | 0 | 0 | 0 | 0 | 0 | 0 | $0 |

</Accordion>

<div id="user-journey-with-re-engagement" />

<Accordion title="재참여가 있는 사용자 여정">

사용자 여정은 위와 동일합니다. 차이점은 제품 라인이 재참여에 동의했다는 것입니다.

[![](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)

이 경우, 리타겟팅 비활성화 창이 메타 주도의 웹 로그인 이벤트가 재참여 이벤트로 자격이 되는지를 결정합니다. 창은 고객의 사용자 ID가 마지막으로 보였던 시점, 즉 모바일 가입 시점부터 열립니다. 웹 로그인 전에 충분한 시간이 지나면, 즉 로그인 시점이 재참여를 위한 비활성화 창 외부에서 발생하면, 메타는 재참여 크레딧을 받습니다.

메타가 재참여로 크레딧을 받으면, 재참여 창이 열립니다. 이 창 내에서 발생하는 모든 인앱 이벤트는 메타에 귀속됩니다. 이 예에서 $100 구매는 재참여 창 내에 있으며 메타에 귀속됩니다. $50 구매는 재참여 창 외부에 있으며 구글로 다시 귀속됩니다.

| 미디어 소스 | 총 어트리뷰션 | 사용자 획득 | 리인게이지먼트 | 플랫폼 활성화까지 | 모바일 | 웹 | LTV |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 1 | 1 | 0 | $50 |
| Meta | 1 | 0 | 1 | 1 | 0 | 1 | $100 |

</Accordion>

## 크로스 플랫폼 재참여 귀속 설정하기

크로스 플랫폼 재참여 귀속을 설정하려면, 제품 라인 설정 위에 재참여에 특정한 몇 가지 설정을 AppsFlyer에 적용해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/product-line-group-apps-for-cross-platform-attribution#how-to-create-a-product-line">제품 라인 생성 방법</Anchor>을 참조하십시오.

## 크로스 플랫폼 어트리뷰션 결과 보기

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/end-user-events-cross-platform-report-in-data-locker">데이터 잠금 장치 최종 사용자 이벤트 크로스 플랫폼 보고서</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/my-dashboards#crossplatform-dashboard">크로스 플랫폼 대시보드</Anchor>

<div data-zendesk-anchors="about-cross-platform-re-engagement-attribution=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KNEVA6TAJZRZYS11Z0Q59AQJ=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC how-does-re-engagement-attribution-work=%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01KNEVA6TASWZ0S6HH5QT0ZZF0=%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C a-cross-platform-re-engagement-user-journey-example=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%97%AC%EC%A0%95-%EC%98%88%EC%8B%9C h_01KNEVA6TA5PVF5E8YWFE13QAQ=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%97%AC%EC%A0%95-%EC%98%88%EC%8B%9C h_01KNEVA6TAPFZ48SHNN1F8Y8P5=user-journey-without-re-engagement h_01KNEVA6TA0ZRG6Z6A38JGEFAQ=user-journey-with-re-engagement set-up-cross-platform-re-engagement-attribution=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KNEVH8QZ2K59BJX0HZ908FXR=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9E%AC%EC%B0%B8%EC%97%AC-%EA%B7%80%EC%86%8D-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 view-cross-platform-attribution-results=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B2%B0%EA%B3%BC-%EB%B3%B4%EA%B8%B0 h_01KNEVH8QZNV046JAF9PRADK4E=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B2%B0%EA%B3%BC-%EB%B3%B4%EA%B8%B0 h_01KNEVH8QZK4J276D8RPBH15JY=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
