---
title: SKAN 권장 사항
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2026-10-14T10:39:57Z'
  id: 7078169815057
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/7078169815057
---
> **간단히 보기**: 요약: SKAN 권장 사항을 사용하여 전환 가치 설정을 최적화하고 보다 정확한 포스트 인스톨 활동 측정 값을 받으세요.

## 개요

Apple iOS의 일부인 SKAdNetwork(SKAN)는 사용자의 개인 정보를 보호하면서 캠페인 성과를 측정할 수 있게 합니다. SKAdNetwork를 사용하면 포스트 인스톨 활동이 0-63 사이의 숫자(전환 값)만 사용하여 측정됩니다.

앱스플라이어 Conversion Studio는 모든 전환 가치(CV)를 계산할 수 있는 최대한의 유연성을 제공합니다. 설치 후 기간 동안 측정해야 하는 활동 및 기간을 포함하여 CV 내에서 인코딩해야 하는 측정 데이터를 정확하게 결정합니다.

그러나 SKAN의 제한된 측정 기능을 고려할 때, 무엇을 측정할 것인지(예: 수익, 앱 내 이벤트 또는 보존)와 0-63 사이의 CV를 가장 잘 활용하는 방법을 결정하는 것은 어려울 수 있습니다.

앱스플라이어 SKAN 권장 사항:

* 현재 CV 설정을 개선하고 CV 효율성과 측정 정확도를 향상시키기 위한 제안을 제공합니다.
* CV 설정을 결정할 때 발생할 수 있는 어려움을 해결합니다.
* 특정 수직 관계, 지역, SKAN 및 비 SKAN 앱 데이터와 사용자 동작을 기반으로 합니다.

## 권장 사항

<div id="revenue" />

<Accordion title="수익">

#### **수익 권장 사항 이해**

정확한 수익 리포트를 얻으려면 올바른 수익 설정 스키마를 갖는 것이 중요합니다.

수익을 리포트해야 하는 전환 가치(CV) 설정이 반드시 100% 정확한 것은 아니며 SKAN에서 리포트한 수익은 실제 수익과 다를 수 있습니다. 예를 들어, 실제(AF 리포트함) ARPPU는 $10일 수 있지만 현재 CV 설정에서 SKAN ARPPU는 $7로 리포트됩니다. 즉, SKAN은 각 유료 사용자에 대해 $3의 수익을 리포트하지 않습니다.

앱스플라이어는 SKAN이 아닌 수익 데이터(100% 정확함)를 매일 확인하여 SKAN 수익 리포트의 정확성을 개선하기 위해 구현할 수 있는 맞춤형 권장 사항을 제공합니다. 권장 사항은 또한 Conversion Studio에 저장된 활동 기간 설정과 특정 카테고리, 지역 및 앱 사용자 행동을 기반으로 합니다.

권장 사항:

* 정확한 수익 리포트를 통해 캠페인 성과를 명확하게 파악할 수 있습니다.
* 수익을 정확하게 측정하기 위해 더 적은 범위를 사용하여 전환 가치를 저장합니다.
* 인앱 구매와 광고 수익을 모두 고려하십시오.

#### **수익 권장 레이아웃**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>SKAN 수익이 측정되는 동안 활동 기간이 Conversion Studio 구성에 저장됩니다.</span></td></tr><tr><td><p><span>B</span></p></td><td><span>앱스플라이어(AF) 방식을 통해 어트리뷰트된 오가닉 및 논오가닉 사용자의 정확한 데이터를 기반으로 한 유료 사용자당 실제 앱 평균 수익(ARPPU).</span></td></tr><tr><td><p><span>C</span></p></td><td><p>현재 설정 ARPPU(SKAN ARPPU)는 <span>활동 기간 및 수익 리포트를 위한 CV 설정을 위해 Conversion Studio에서 현재 설정을 기준으로</span> 측정한 ARPPU를 의미합니다.</p></td></tr><tr><td><span>D</span></td><td><p>   F 및 G를 참조하십시오.</p><p><span><strong>참고:</strong> </span></p></td></tr><tr><td><p><span>E</span></p></td><td><p> 대략적인 오류: <span>B와 C의 차이점입니다. 이는 SKAN ARPPU가 과대 보고되었는지 과소 보고되었는지 여부에 따라 긍정 오류 또는 부정 오류일 수 있습니다.</span></p><p><span>예: 예: 실제 ARPPU가 $10이고 SKAN ARPPU가 $7인 경우 대략적인 오류는 30%(사용자당 -$3 달러)의 과소 보고입니다.</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>SKAN 수익 구성에 대한 권장 사항. 설정에 포함할 범위 수를 선택합니다.</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>Conversion Studio에 설정된 현재 수익 구성입니다.</span><span></span></p></td></tr></tbody></table>

#### **수익 권장 사항 이용**

**전제 조건: 전제 조건: 수익 권장 사항에는 14일 이상의 수익 데이터가 필요합니다.**

> 📘 **참고**
>
> 이것은 매일 업데이트됩니다. 14일 전의 추천 기간이 어제부터라는 의미입니다. 예를 들어 오늘이 8월 28일인 경우. 권장 사항에 대한 입력 데이터는 8월 13일부터 8월 27일까지입니다.

**수익 권장 사항 사용 방법:**

1. 앱스플라이어에서 SKAN 4의 사용자 지정 모드를 사용하는지 고정 모드를 사용하는지에 따라 다음 중 하나로 이동합니다.
   * **SKAN Conversion Studio** > **SKAN 4**> **설정> 전체 매출/인앱 이벤트**.
   * **설정 > SKAN Conversion Studio** > **커스텀** > **전체 매출/인앱 이벤트**.
   * **SKAN Conversion Studio** > **Revenue** > **설정합니다**.
2. 이미 수익 범위를 구성한 경우 이 단계를 건너뜁니다. 수익 범위를 구성하지 않은 경우 지금 구성하십시오.  
   수익 범위가 구성되면 구성 정확도 및 대략적인 오류에 대한 정보가 표시됩니다.
3. **권장 사항 확인**을 클릭합니다.  
   현재 구성에 대한 정보가 수익 범위 권장 사항 및 구현되는 경우 제공할 예상 정확도(대략적인 오류)와 함께 표시됩니다. 범위 수를 유지하고 변경하는 방법에 대한 권장 사항이 제공됩니다.
4. 범위 권장 사항을 선택합니다.
5. **권장 사항 적용**을 클릭합니다.
   * 수익 구성이 사용자 지정 모드로 설정된 경우 권장 사항이 적용됩니다.
   * 고정 모드(수익)의 수익 구성이 있는 경우 범위 권장 사항을 기록하고 **SKAN Conversion Studio** > **사용자 정의** > **전체 수익**으로 이동하여 권장 범위를 구성해야 합니다.
6. **저장**을 클릭하세요.
   * 그런 다음 수익 설정에서 무엇이든 변경하면 설정을 다시 확인하고 새 권장 사항을 볼 수 있습니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HGSZ05CH4P8BQT23VYH6DKVP=%EA%B0%9C%EC%9A%94 recommendations=%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD h_01HGSZ05CHPZKWKY7MR6MA68YZ=%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD h_01HGSZ05CH2RG3514N576ZGDFM=revenue understanding-revenue-recommendations=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD-%EC%9D%B4%ED%95%B4 h_01HGSZ05CHC93SHP28DN9EK27N=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD-%EC%9D%B4%ED%95%B4 revenue-recommendations-layout=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83 h_01HGSZ05CH5DVKAQ24EED16JRN=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83 using-revenue-recommendations=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD-%EC%9D%B4%EC%9A%A9 h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=%EC%88%98%EC%9D%B5-%EA%B6%8C%EC%9E%A5-%EC%82%AC%ED%95%AD-%EC%9D%B4%EC%9A%A9 h_01HGSZCYCWRYEJPWZKDBC9SX8H=%EC%B0%B8%EA%B3%A0" />
