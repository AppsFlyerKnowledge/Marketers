---
title: 성과 증분 측정 실험 알림
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2023-03-05T12:31:35Z'
  edited_at: '2026-10-14T10:29:39Z'
  id: 13479545385489
  locale: ko
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/ko/articles/13479545385489
---
> **한눈에 보기:** 정확한 실험 결과를 위해 알림을 이해하고 해결하세요.

![경험치_경고_조작됨.jpg](https://files.readme.io/3981e4a4bd66206d9b5986cc1b573f67e1ab836042a1f73518f48a1ea17b6568-35266706078481.jpg)

<div id="about-experiment-alerts" />

## 실험 알림에 대하여

<Anchor target="_blank" href="/marketers/ko/docs/run-an-incrementality-for-remarketing-experiment">성과 증분 측정 솔루션 실험을 설정</Anchor>하면 성과 증분 측정 대시보드에서 알림을 확인할 수 있습니다. 이러한 알림은 귀사의 실험 결과의 무결성과 정확성을 손상시킬 수 있는 문제를 식별하는 데 도움이 됩니다. 문제에 대한 구체적인 정보를 제공하고 해결할 수 있는 조치를 제안하여 정확한 실험 결과를 보장합니다. 이 문서 는 다양한 알림 유형과 문제 해결을 위한 권장 조치에 대한 포괄적인 개요를 제공합니다.

<div id="alert-types" />

## 알림 유형

실험 알림은 다음 범주로 나뉩니다.

<div id="experiment-setup" />

<Accordion title="실험 설정">

<div id="audience-deletion-or-control-group-removal" />

#### 오디언스 삭제 또는 통제군 제거

연결된 오디언스가 삭제되었거나 분할된 오디언스 통제군이 제거된 실험입니다. 이 두 시나리오 모두 실험 페이지를 방문하면 404 오류가 발생합니다.

**이 문제를 해결하고 실험 결과를 복원하려면:**  
**오디언스가 삭제된 경우** - 귀사의 CSM에게 문의하여 수동으로 복원하세요.  
**통제군이 제거된 경우** - 오디언스를 다시 분할하고 통제군을 이전과 동일한 비율로 설정하세요.

<div id="more-suitable-campaign-srns-only" />

#### 더 적합한 캠페인? (SRN만 해당)

이 알림은 SRN(자체 보고 네트워크)에만 해당됩니다. 이 알림은 캠페인이 실험에 연결되어 있지만, 데이터에 따르면 오디언스 타겟팅에 더 적합한 캠페인이 있는 것으로 나타날 때 표시됩니다.  
"더 적합한 캠페인"은 실험 기간 동안 활성화된 캠페인 중에서 구성된 캠페인보다 실험군을 더 잘 타겟팅하는 캠페인을 의미합니다(통제군은 타겟팅하지 않음).

**취해야 할 조치:** 올바른 캠페인이 연결되었는지 확인하세요.

**참고:** 해당 오디언스가 다른 캠페인의 타겟팅 구성에 포함되지 않았는지 확인하세요.

<div id="no-impressions-non-srns-only" />

#### 노출 없음(비 SRN에만 해당)

비(非) SRN 광고 네트워크에서 캠페인을 실행할 때 성과 증분 측정 솔루션, Incrementality 실험을 실시하면, 앱스플라이어가 해당 캠페인의 증분 영향을 가장 정확하게 계산하려면 유저 노출이 필요합니다. 노출이 없으면 실험 페이지에 결과가 표시되지 않습니다.

이 경고는 연결된 캠페인에 대한 노출 데이터를 받지 못하는 상황을 설명합니다.

**취해야 할 조치:** 매체사 파트너로부터 노출이 발생하고 있는지, 테스트된 캠페인이 제대로 작동하며 광고를 내보내고 있는지 확인하세요.

</Accordion>

<div id="experiment-background-environment" />

<Accordion title="실험 배경 환경">

<div id="background-campaign-one-or-multiple" />

#### 백그라운드 캠페인 (하나 또는 여러 개)

이 경고는 실험에 설정된 캠페인보다 오디언스에 더 크고 관련 없는 캠페인이 있을 때 나타납니다.

어떻게 이런 일이 발생할 수 있을까요?  
관련 없는 캠페인이 배경에 존재하는 것은 일반적입니다. 그러나 해당 캠페인이 더 큰 예산이나 집중적으로 운영될 경우, 설정된 캠페인의 효과가 가려지고 실험 결과에 영향을 미칠 수 있습니다.

**취해야 할 조치:**

* 예산을 늘려 귀사의 캠페인 영향을 증대시켜 보세요.
* 테스트된 오디언스가 배경 캠페인의 타겟팅 오디언스와 겹치는지 확인하세요 (오디언스 파트너 중복 기능으로 확인 가능).
* 테스트된 오디언스가 관련 없는 배경 캠페인과 겹치는지 확인하세요.
* 테스트된 오디언스 세분화를 강화하세요.
* 백그라운드 캠페인의 영향을 최소화하는 조치를 취했다면, 변경 후 실험 시작 날짜를 설정하세요.

**참고:** **다른 캠페인으로 테스트된 오디언스를 타겟팅하는 것을 최소화하세요.**

</Accordion>

<div id="linked-campaign-performance" />

<Accordion title="연결된 캠페인 성과">

<div id="audience-overlap" />

#### 오디언스 중복

연결된 캠페인이 중복되는 오디언스를 타겟팅하고 있습니다. 이는 연결된 캠페인의 타겟팅 설정에 두 개 이상의 오디언스가 포함되어 있음을 의미합니다.  
또한, 테스트된 캠페인 설정에서 여러 오디언스가 겹칩니다. 이로 인해 시험 대상 오디언스 외부에 타겟팅 하게 되며, 여기에는 시험된 오디언스의 통제군도 포함됩니다.

**취해야 할 조치:**  
캠페인 타겟팅을 업데이트하여 시험된 오디언스만 포함하고, 추가된 모든 오디언스를 제거하세요.

<div id="control-group-is-targeted" />

#### 통제군이 타겟팅됨

이 경고는 구성된 캠페인이 실험군이 아니라 통제군을 타겟으로 하고 있음을 나타냅니다.

**어떻게 이런 일이 발생할 수 있습니까?**

* 실험이 잘못된 캠페인과 연결되었습니다.
* 매체사 파트너 측의 캠페인이 오디언스 외부의 사용자를 대상으로 구성되었습니다(페이스북 및 Google의 <Anchor target="_blank" href="/marketers/ko/docs/run-an-incrementality-for-remarketing-experiment#오디언스-확장-기능을-확인하세요">오디언스 확장 기능</Anchor>을 확인하세요).
* 네트워크가 타겟팅 구성을 적용하지 않고 있습니다.

**취해야 할 조치:**  
위에 나열된 일반적인 시나리오를 확인하시고, 불확실한 경우 귀사의 CSM에 문의하세요. 특정 경우, 통제군 사용자의 캠페인 노출이 중요한 경우 이를 해결할 방법이 없으며 새 성과 증분 측정 솔루션, Incrementality 실험을 만들어야 합니다.

침해가 비교적 작다면 통제군 타겟팅을 중단하는 것으로 충분합니다. 실험 UI에서 경고를 측정하고 며칠 후에도 경고가 계속 나타나는지 확인하세요.

<div id="detailed-targeting-toggle-is-enabled" />

#### 세부 타겟팅 토글이 활성화되었습니다.

세부 타겟팅은 특정 광고 네트워크에서 제공하는 기능으로, 광고를 누가 보는지 세부적으로 조정할 수 있습니다. 캠페인의 세부 타겟팅 토글이 활성화된 경우 이 알림이 나타날 것입니다. 이 기능을 활성화하면 설정된 오디언스 외부를 캠페인이 타겟팅할 수 있습니다.

**취해야 할 조치:** 파트너 측 캠페인 구성에서 세부 타겟팅 토글이 꺼져 있는지 확인하세요.

<div id="low-activity" />

#### 액티비티 적음

캠페인 광고가 게재되지 않거나 타겟 오디언스에게 매우 적은 수의 광고가 게재됩니다.

**취해야 할 조치:** 캠페인 광고가 왜 게재되지 않는지 확인하려면 매체사 파트너 측의 문제를 조사하세요.

<div id="multiple-audiences-connected" />

#### 여러 오디언스 연결됨

캠페인의 타겟팅 구성에 여러 오디언스가 포함되어 있습니다. 이로 인해 시험된 오디언스나 통제군 외부를 타겟팅하게 되어, 궁극적으로 시험 결과에 영향을 줄 수 있습니다.

**취해야 할 조치:**  
성과 증분 측정 시험의 모범 사례는 시험된 캠페인이 하나의 오디언스만을 타겟으로 설정해야 한다는 것입니다.

<div id="out-of-audience-targeting" />

#### 오디언스 외부 타겟팅

시험된 캠페인이 타겟 오디언스 실험군 외의 사용자도 타겟팅하고 있습니다. 캠페인 비용의 일부는 시험된 오디언스 사용자와 관련이 없는 사람들에게 광고를 전달하는 데 사용되고 성과 증분 측정 시험에서는 고려되지 않습니다.

따라서 관련 없는 사용자에게 비용을 지출할 경우, iROAS와 CPiA 등 캠페인 비용 관련 지표가 편향될 수 있습니다. 이들은 오디언스 외부의 사용자에게 광고를 게재하는 데 드는 비용을 포함한 전체 캠페인 비용을 고려하지만, 그들의 전환은 포함하지 않습니다.

**어떻게 이런 일이 발생할 수 있습니까?**

* 실험이 잘못된 캠페인과 연결되었습니다.
* 매체사 파트너 측의 캠페인이 오디언스 외부의 사용자를 대상으로 구성되었습니다(페이스북 및 Google의 <Anchor target="_blank" href="/marketers/ko/docs/run-an-incrementality-for-remarketing-experiment#오디언스-확장-기능을-확인하세요">오디언스 확장 기능</Anchor>을 확인하세요).
* 네트워크가 타겟팅 구성을 적용하지 않고 있습니다.

**취해야 할 조치:**  
캠페인의 타겟팅 설정에 시험된 오디언스만 포함되어 있는지 확인하고, 캠페인 설정에서 오디언스 외부를 타겟팅하지 않도록 하세요.

</Accordion>

<div data-zendesk-anchors="about-experiment-alerts=%EC%8B%A4%ED%97%98-%EC%95%8C%EB%A6%BC%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HNZPQJDA5D7Q04CDKMYCW763=%EC%8B%A4%ED%97%98-%EC%95%8C%EB%A6%BC%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC types-of-alerts=%EC%95%8C%EB%A6%BC-%EC%9C%A0%ED%98%95 h_01HE7R6CQ5R9HAYG83B3903AY8=%EC%95%8C%EB%A6%BC-%EC%9C%A0%ED%98%95 h_01HE7R6CQ5SNX6VYFD18501JYT=experiment-setup audience-deletion-or-control-group-removal=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%82%AD%EC%A0%9C-%EB%98%90%EB%8A%94-%ED%86%B5%EC%A0%9C%EA%B5%B0-%EC%A0%9C%EA%B1%B0 h_01HE7R6CQ5DM1QNN1E55TGDKKH=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%82%AD%EC%A0%9C-%EB%98%90%EB%8A%94-%ED%86%B5%EC%A0%9C%EA%B5%B0-%EC%A0%9C%EA%B1%B0 more-suitable-campaigns-srns-only=%EB%8D%94-%EC%A0%81%ED%95%A9%ED%95%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-srn%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HE7R6CQ518RS50X87243M7BV=%EB%8D%94-%EC%A0%81%ED%95%A9%ED%95%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-srn%EB%A7%8C-%ED%95%B4%EB%8B%B9 no-impressions-received-nonsrns-only=%EB%85%B8%EC%B6%9C-%EC%97%86%EC%9D%8C%EB%B9%84-srn%EC%97%90%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HE7R6CQ57DV8D642APE01JV0=%EB%85%B8%EC%B6%9C-%EC%97%86%EC%9D%8C%EB%B9%84-srn%EC%97%90%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HE7R6CQ5XFAE56PTX6RRZD5J=experiment-background-environment background-campaign-one-or-multiple=%EB%B0%B1%EA%B7%B8%EB%9D%BC%EC%9A%B4%EB%93%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%ED%95%98%EB%82%98-%EB%98%90%EB%8A%94-%EC%97%AC%EB%9F%AC-%EA%B0%9C h_01HE7R6CQ5AZW1RB7XJH4GEEBT=%EB%B0%B1%EA%B7%B8%EB%9D%BC%EC%9A%B4%EB%93%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%ED%95%98%EB%82%98-%EB%98%90%EB%8A%94-%EC%97%AC%EB%9F%AC-%EA%B0%9C h_01HE7R6CQ5C6009QZK6TQS6QGC=linked-campaign-performance audience-overlap=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A4%91%EB%B3%B5 h_01HE7R6CQ6X5C0D4E519W535PH=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A4%91%EB%B3%B5 control-group-is-targeted=%ED%86%B5%EC%A0%9C%EA%B5%B0%EC%9D%B4-%ED%83%80%EA%B2%9F%ED%8C%85%EB%90%A8 h_01HE7R6CQ5NFH58H8ZNRG6E4MG=%ED%86%B5%EC%A0%9C%EA%B5%B0%EC%9D%B4-%ED%83%80%EA%B2%9F%ED%8C%85%EB%90%A8 detailed-targeting-toggle-is-enabled=%EC%84%B8%EB%B6%80-%ED%83%80%EA%B2%9F%ED%8C%85-%ED%86%A0%EA%B8%80%EC%9D%B4-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%98%EC%97%88%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01HKSTD08WK37RHM5DM922GGWF=%EC%84%B8%EB%B6%80-%ED%83%80%EA%B2%9F%ED%8C%85-%ED%86%A0%EA%B8%80%EC%9D%B4-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%98%EC%97%88%EC%8A%B5%EB%8B%88%EB%8B%A4 low-activity=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%A0%81%EC%9D%8C h_01HE7R6CQ6C76SZEAN0R93H9QN=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EC%A0%81%EC%9D%8C multiple-audiences-connected=%EC%97%AC%EB%9F%AC-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%97%B0%EA%B2%B0%EB%90%A8 h_01HKSTFSKDTD2Z8HKCCX2MWBJQ=%EC%97%AC%EB%9F%AC-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%97%B0%EA%B2%B0%EB%90%A8 outofaudience-targeting=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%99%B8%EB%B6%80-%ED%83%80%EA%B2%9F%ED%8C%85 h_01HE7R6CQ6TVCGW5X8GBX0AJKS=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%99%B8%EB%B6%80-%ED%83%80%EA%B2%9F%ED%8C%85" />
