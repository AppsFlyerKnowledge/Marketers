---
title: '[베타] 내 대시보드에서 커스텀 메트릭 설정'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2025-01-01T09:21:05Z'
  edited_at: '2026-10-14T10:30:11Z'
  id: 31400289569169
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/31400289569169
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

<Image alt="beta_feature.png" src="https://files.readme.io/d57432ddeb4d168760f9acd97f4287473658a8528edc1114ecee8ee2f8e9c9b2-16484830033425.png" width="805px" />

> **한눈에 보기:** 자체 지표를 정의하고 이를 사용하여 내 대시보드에서 데이터를 볼 수 있습니다.

<div id="about-custom-metrics" />

## 커스텀 메트릭 정보

커스텀 지표를 사용하면 기존 데이터를 기반으로 계산을 정의하여 고유한 비즈니스 요구에 맞게 데이터 분석을 조정할 수 있습니다. 커스텀 지표를 사용하면 데이터를 세밀하게 조정하고 원하는 방식으로 구성할 수 있으며, 여러 지표를 결합하거나 캠페인 결과를 예측하고, KPI를 자유롭게 정의할 수 있습니다.

예를 들어, "수익" 또는 "클릭 수"와 같은 일반적인 지표 대신, 다음과 같은 고유한 사용 사례에 맞는 수식을 만들 수 있습니다.

* Revenue D60 Prediction = Revenue D1 * 3
* 클릭 대비 구매율 = 클릭 수 / af\_purchase [고유 사용자]

커스텀 지표는 테이블, 차트 및 KPI를 포함하여 My Dashboards의 모든 위젯 유형과 호환됩니다. 마케터가 캠페인 ROI를 추적하든, 제품 관리자가 인게이지먼트를 모니터링하든, 분석가가 성과를 예측하든, 커스텀 메트릭은 트렌드를 분석하고 기회를 파악하며, 특정 비즈니스 요구 사항에 맞는 데이터 기반 의사 결정을 내릴 수 있는 능력을 대시보드에서 직접 강화합니다.

**참고**: 생성한 사용자 지정 기준은 계정 레벨에 있으며, 이는 동일한 앱스플라이어 계정의 다른 앱이 동일한 사용자 지정 기준을 사용할 수 있음을 의미합니다.

<div id="procedures" />

## 절차

<div id="create-a-custom-metric" />

<Accordion title="커스텀 메트릭 생성">

**사용자 지정 지표 만들기**:

1. 대시보드에서 다음 중 하나를 수행합니다.
   * 클릭 **+ 새로 만들기** > **사용자 지정 지표**.
   * 어떤 차트나 표에서든, **Metrics** 드롭다운 메뉴에서 **+ Custom Metric 생성** 을 클릭합니다.
2. * 메트릭의 이름을 지정하세요. 커스텀 메트릭 편집기 상단에 메트릭에 대한 설명 이름을 입력합니다(예: "IPM").
3. **Metric 유형을** 선택합니다. 지표가 숫자인지, 백분율인지, 화폐인지(통화인지) 선택합니다.
4. 메트릭 공식을 정의하세요. 다음 중 하나:
   * 빠르게 시작하세요! 제안된 공식을 사용합니다(사용자 지정 지표 편집기 왼쪽 메뉴에 표시). 그런 다음, 편집기를 사용하여 다양한 인앱이벤트를 선택하거나 배수 또는 기타 파라미터를 수정하여 특정 요구 사항에 맞게 템플릿을 편집합니다. 예를 들어, 템플릿 `Retention rate D2 / Retention rate D7`의 경우 D2와 D7을 다른 이벤트나 기간으로 교체할 수 있습니다.
   * 인터랙티브 편집기를 사용합니다. 메트릭과 연산자(버튼 사용)와 숫자(키보드를 사용하여)를 추가하여 공식을 정의합니다.
5. fx 공식 필드의 수식을 미리 볼 수 있습니다.
6. [선택 사항] 일반 대시보드에서 커스텀 메트릭을 만든 경우, **저장하고 차트에 추가하기**를 클릭합니다.  
   커스텀 메트릭을 포함한 새 차트가 생성되었습니다.
7. **저장**을 클릭하세요.
   * 위젯 내에서 커스텀 메트릭을 만든 경우, 자동으로 차트 또는 테이블에 추가됩니다.
   * 일반적인 대시보드에서 커스텀 메트릭을 만든 경우, 이제 원하는 위젯에 추가할 수 있습니다.

</Accordion>

<div id="edit-a-custom-metric" />

<Accordion title="커스텀 메트릭 편집">

대시보드 또는 특정 위젯 내에서 커스텀 메트릭을 편집할 수 있습니다. **참고**! 커스텀 메트릭을 변경할 때는 계정별로 변경할 수 있습니다. 즉, 변경 사항은 모든 사용자와 대시보드의 메트릭에 영향을 미칩니다.

**대시보드에서 커스텀 메트릭을 편집하는 방법**:

1. 대시보드에서 **+ 새로 만들기** > **사용자 지정 지표**를 클릭합니다.
2. 사용자 지정 지표 편집기 왼쪽 메뉴에서 내 사용자 지정 지표 아래에서 편집을 원하는 지표를 찾고 **편집** 아이콘을 클릭합니다.
3. 사용자 지정 지표 공식에 원하는대로 변경하세요.
4. **저장**을 클릭하세요.

**위젯에서 사용자 지정 지표 편집하기**:

1. 어떤 차트나 표에서든, **Metrics** 드롭다운 메뉴에서 편집하려는 메트릭을 찾아 **편집** 아이콘을 클릭합니다.
2. 사용자 지정 지표 편집기 왼쪽 메뉴에서 내 사용자 지정 지표 아래에서 편집을 원하는 지표를 찾고 **편집** 아이콘을 클릭합니다.
3. 사용자 지정 지표 공식에 원하는대로 변경하세요.
4. **저장**을 클릭하세요.

</Accordion>

<div id="delete-a-custom-metric" />

<Accordion title="커스텀 메트릭 삭제">

대시보드 또는 특정 위젯 내에서 커스텀 메트릭을 삭제할 수 있습니다. **참고**! 사용자 지정 지표에 대한 모든 삭제는 계정 수준이며, 모든 사용자 및 대시보드에서 지표가 삭제됩니다.

**대시보드에서 사용자 지정 지표를 삭제하려면**

1. 대시보드에서 **+ 새로 만들기** > **사용자 지정 지표**를 클릭합니다.
2. 사용자 지정 지표 편집기 왼쪽 메뉴에서 내 사용자 지정 지표 아래에서 삭제하려는 지표를 찾아 **삭제** 아이콘을 클릭합니다.

위젯에서 사용자 지정 지표 삭제 **방법**:

* 어떤 차트나 표에서든, **Metrics** 드롭다운 메뉴에서 삭제하려는 메트릭을 찾아 **삭제** 아이콘을 클릭합니다.

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="best-practices" />

<Accordion title="모범 활용 사례">

* **단순 시작**: 기본 측정 지표부터 시작하여 필요에 따라 점진적으로 복잡성을 추가하고 공식 개발에 익숙해지세요.
* **목적 준수**: 각 지표가 특정 비즈니스 목표 또는 질문과 연관되어 있는지 확인하십시오.
* **수식 문서**: 간단한 업데이트 또는 디버깅을 위해 사용자 정의 수식을 참조하세요.
* **주기적으로 검토**: 지표를 정기적으로 평가하여 관련성을 높이세요.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 계정 수준 접근성 | 모든 계정 구성원은 커스텀 메트릭을 만들고 보고 편집하며 삭제할 수 있습니다. 여기에는 다른 사용자가 생성한 지표도 포함됩니다. |
| 커스텀 지표 | <ul><li>커스텀 메트릭은 계정당 1,000개의 커스텀 메트릭을 제한합니다.</li><li>커스텀 메트릭은 현재 일 별 쪼개보기만 지원됩니다. 주간 및 월간 분석은 지원되지 않습니다.</li></ul> |
| 공식 복잡성 | 커스텀 메트릭 공식당 최대 5개 지표. |
| Nesting 제한 | 커스텀 메트릭은 다른 커스텀 메트릭 수식의 구성 요소로 사용할 수 없습니다. |

</Accordion>

<div data-zendesk-anchors="about-custom-metrics=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%A9%94%ED%8A%B8%EB%A6%AD-%EC%A0%95%EB%B3%B4 h_01H8XWQHPERAEDQVD275TFVC5B=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%A9%94%ED%8A%B8%EB%A6%AD-%EC%A0%95%EB%B3%B4 procedures=%EC%A0%88%EC%B0%A8 h_01H8XWQHPESY4DDDJSTR0JDHNB=%EC%A0%88%EC%B0%A8 h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-metric h_01H8XWQHPE22WZ46RTNCYKX96F=edit-a-custom-metric h_01H8XWQHPED4PFPJP2044FT1H8=delete-a-custom-metric additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01JGGT56V05BJRCV9Q572JJR3W=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01JGK1XAVB3M5KDA59A9ZASM2K=best-practices h_01H8XWQHPF7WZ7B5Q7T9CHADRK=traits-and-limitations" />
