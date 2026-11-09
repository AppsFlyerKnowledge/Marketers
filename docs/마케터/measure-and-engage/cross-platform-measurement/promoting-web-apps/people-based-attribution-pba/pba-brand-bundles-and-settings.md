---
title: PBA 브랜드 번들 및 설정
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2026-10-14T10:36:17Z'
  id: 360000646498
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360000646498
---
> **한눈에 보기:** 브랜드 번들은 브랜드 관련 앱 및 웹 사이트의 어트리뷰션, 이벤트, 방문 및 수익을 통합합니다. 브랜드 번들 설정 페이지를 사용하여 전환 이벤트를 표시하고 Google 광고 등과 통합할 수 있습니다.

<Image align="center" alt="BrandBundles.png" src="https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png" />

<div id="about-brand-bundles" />

## 브랜드 번들 정보

브랜드는 웹과 모바일 자산을 모두 아우르는 생태계에서 운영됩니다. 광고주로서 플랫폼 전반–웹과 모바일–에 걸친 브랜드 성과에 대한 전체적인 이해가 필요합니다. PBA에서 브랜드 번들은 분석 및 로데이터를 위해 모바일 및 웹 속성의 데이터를 단일 엔티티에 통합합니다.

<div id="what-is-a-web-app" />

> 📘 **웹 앱이란 무엇입니까?**
>
> 웹 앱은 성과를 측정하려는 웹 사이트를 지정하는 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에서 생성된 엔티티</Anchor>입니다.
>
> * 웹 앱 엔티티는 2022년 2월 9일 앱스플라이어에 추가되었습니다. 이전에는 브랜드 번들을 생성할 때 별도의 설정으로 브랜드 번들 도메인을 입력했습니다. 이제는 도메인을 정의하는 웹 앱을 먼저 만든 다음 번들을 만들 때 해당 웹 앱을 포함합니다.
> * 2022년 2월 9일에 기존 브랜드 번들이 있었다면, 이제 각 번들에 해당하는 웹 앱이 **내 앱** 페이지에 있다는 것을 알게 될 것입니다. **안심하십시오!** 웹 트래픽은 이전과 동일하게 어트리뷰트되며 PBA 대시보드 또는 로데이터 리포트에 다른 변경 사항은 없습니다.

**브랜드 번들 기본:**

* 브랜드 번들에는 정확히 하나의 웹 앱*(필수)*과 하나 이상의 모바일 앱*(선택 사항)*이 포함됩니다.
* 앱(웹 또는 모바일)은 1개의 번들에만 속할 수 있습니다.
* [원래 번들을 삭제하지 않고](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) 번들에서 앱을 삭제하거나 번들에서 다른 번들로 이동할 수 없습니다.
  * 번들 삭제 시 앱스플라이어는 번들에 대한 PBA 데이터 어트리뷰트를 중지하고 더 이상 해당 기록 데이터에 액세스할 수 없습니다.

<div id="accessing-brand-bundles" />

## 브랜드 번들 액세스

**브랜드 번들** 페이지에 액세스하여 브랜드 번들과 해당 설정을 관리합니다.

* 앱스플라이어에서 상단 메뉴를 선택하고 **내 앱** > **브랜드** 번들 보기를 선택합니다.  
                           또는
* 앱스플라이어의 사이드 메뉴에서 **설정** > **브랜드 번들을 선택합니다.**

<div id="managing-brand-bundles" />

## 브랜드 번들 관리

브랜드 번들을 추가, 삭제 또는 관리하려면 **브랜드 번들** 페이지에서 다음 옵션 중 하나를 선택합니다.

| 옵션 | 세부 정보 |
| --- | --- |
| 브랜드 번들 추가 |  |
| PBA 대시보드 | 브랜드 대시보드를 엽니다. |
| 브랜드 번들 ID | 브랜드 번들 ID를 클립보드에 복사합니다. |
| 웹 개발자 키 | 웹 dev 키를 클립보드에 복사합니다. |
| 브랜드 번들 설정 및 옵션을 업데이트할 기존 번들을 선택하십시오. | 사용 가능 옵션:<ul><li>이벤트를 전환 이벤트로 표시:<ul><li>[웹 이벤트 설정](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[인앱 이벤트 설정](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[도메인 제외](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/ko/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">구글 애즈 연동</Anchor></li></ul> |
| 아이콘 삭제 | [선택한 브랜드 번들을 삭제합니다](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)(귀하가 그렇게 하기로 결정한 후). |

<div id="add-brand-bundle" />

<Accordion title="브랜드 번들 추가">

계속하기 전에 번들에 포함할 모든 앱이 계정에 추가되었는지 확인하십시오. 브랜드 번들을 만든 후에는 [번들을 삭제](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)하고 다시 만들지 않으면 포함된 앱을 변경할 수 없습니다.

브랜드 번들을 추가하는 방법:

1. [브랜드 번들](/docs/pba-brand-bundles-and-settings#브랜드-번들-액세스) 페이지에서 **브랜드 번들 추가**를 클릭합니다.
2. **브랜드 번들 이름**(번들을 식별하는 데 사용할 이름)을 입력합니다.
3. 번들에 포함할 앱을 선택합니다.

   **참고:** 일러두기: 다른 번들에 포함된 앱은 선택할 수 없습니다.

   * 필수 웹 앱
   * * 번들을 만드는 데 모바일 앱이 필요하지 않습니다.
     * 번들에 포함할 수 있는 모바일 앱의 개수에는 제한이 없습니다.
4. 번들 생성을 클릭합니다.

<div id="important" />

> 🚧 **중요!**
>
> 다음 환경에서는 브랜드 번들을 생성할 수 없습니다.
>
> * 유효한 URL을 가리키지 않는 번들에 포함하도록 선택된 웹 앱.
> * 번들에 포함되도록 선택한 웹 앱과 안드로이드 모바일 앱의 앱 ID가 동일합니다.

</Accordion>

<div id="web-event-settings" />

<Accordion title="웹 이벤트 설정">

웹 이벤트에는 **표준** 및 **전환**의 두 가지 유형이 있습니다. 최적화에 집중하고 우선순위를 지정하려면 일부 이벤트를 전환 이벤트로 설정합니다.

* PBA는 표준 이벤트와 전환 이벤트를 동일한 방식으로 어트리뷰트합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터</Anchor> 리포트에는 표준 이벤트와 전환 이벤트가 모두 포함됩니다.
* PBA 대시보드는 전환 이벤트만 포함합니다.
* 이벤트 유형은 언제든지 변경할 수 있지만 변경 사항이 소급되지는 않습니다.

**전환 이벤트를 설정하는 방법:**

1. [브랜드 번들](/docs/pba-brand-bundles-and-settings#브랜드-번들-액세스) 페이지에서 브랜드 번들을 선택합니다.  
   **브랜드 번들 업데이트** 페이지가 열립니다.
2. **웹 이벤트 설정** 탭으로 이동합니다.
3. 필요에 따라 **전환 이벤트로 표시**를 켭니다.
4. **번들 업데이트**를 클릭합니다.

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="인앱 이벤트 설정">

[기본값] 수익을 가진 인앱이벤트는 전환 이벤트로 표시됩니다. **참고!** 기본 이벤트를 변경하는 경우 인앱 수익 이벤트를 직접 명시적으로 표시해야 합니다.

**인앱이벤트를 전환 이벤트로 표시하는 방법:**

1. [브랜드 번들](/docs/pba-brand-bundles-and-settings#브랜드-번들-액세스) 페이지에서 브랜드 번들을 선택합니다.  
   **브랜드 번들 업데이트** 페이지가 열립니다.
2. **인앱이벤트 설정** 탭으로 이동합니다.
3. 필요에 따라 **전환 이벤트로 표시**를 켭니다.
4. **번들 업데이트**를 클릭합니다.

</Accordion>

<div id="domain-exclusion" />

<Accordion title="도메인 제외">

다음을 방지하기 위해 <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules">PBA 미디어소스 규칙</Anchor>의 일부인 도메인 배제 메커니즘이 구현됩니다.

* 자기 어트리뷰션 셀프 어트리뷰션: 즉, 앱스플라이어는 웹 앱 자체에 정의된 웹 사이트와 해당 웹 사이트와 해당 웹사이트에 연결된 사용자가 지정한 도메인에 이벤트를 어트리뷰트하지 않습니다.
* 브랜드에는 속하지 않지만 사용자 흐름에 참여하는 도메인과 관련된 이벤트(예: 결제 게이트웨이)를 어트리뷰트하거나 기록합니다.

| 도메인 유형 | 설명 | 배제의 영향 |
| --- | --- | --- |
| 기본 | 브랜드 번들에 포함된 웹 앱의 도메인. 여기에는 하위 도메인이 포함됩니다.<br /><br />예를 들어, 도메인이 mydomain.co.za이면 a.mydomain.co.za, b.mydomain.co.za와 같은 하위 도메인이 자동으로 포함됩니다.<br /><br />웹 앱의 도메인은 웹 앱을 삭제 및 재생성하지 않으면 변경할 수 없습니다. (이는 웹 앱이 포함되는 번들을 삭제한다는 의미도 내포합니다). | 논셀프 어트리뷰션 |
| 내부 | 브랜드의 일부를 구성하는 다른 도메인 나열, 예를 들어 mydomain.com, mydomain.in, mydomain.co.ng, abc.com | 논셀프 어트리뷰션 |
| 외부(사용자가 기재) | 웹사이트에서 직접 사용되지만 브랜드의 일부가 아닌 도메인. 여기에는 전자결제 대행사, 결제 처리 사이트 등이 포함됩니다. | <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules#visit-recognition-rules">방문은 무시됨</Anchor> |
| 외부(앱스플라이어가 기재) | 앱스플라이어가 기재하고 항상 배제되는 도메인.<ul><li>PayPal(페이팔)</li><li>Stripe</li><li>Adyen</li></ul>자동화된 도메인 목록은 수정할 수 없습니다. | <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules#visit-recognition-rules">방문은 무시됨</Anchor> |

**내부 또는 외부 도메인을 배제하는 방법:**

1. [브랜드 번들](/docs/pba-brand-bundles-and-settings#브랜드-번들-액세스) 페이지에서 브랜드 번들을 선택합니다.  
   **브랜드 번들 업데이트** 페이지가 열립니다.
2. **도메인 배제** 탭으로 이동합니다.
3. **도메인 추가**를 클릭합니다.
4. 도메인 이름을 입력합니다.
6. **도메인 추가**를 클릭합니다.  
   실행 사항이 적용되는 데 한 시간이 걸립니다.

</Accordion>

<div id="faq" />

## 자주 묻는 질문

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="동일한 앱을 두 개 이상의 번들에 포함할 수 있습니까?">

**아니오.** 아닙니다. 앱이 번들에 추가되면 다른 번들에 추가할 수 없습니다.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="번들을 생성한 후 앱을 추가하거나 삭제할 수 있습니까?">

**아니오.** 아닙니다. 번들이 생성되면 그에 포함된 앱은 변경할 수 없습니다.

이유는? 각 앱에는 자체 데이터가 있으며 앱스플라이어는 이 데이터를 사용하여 플랫폼(웹 및 앱) 간의 사용자 여정을 분석합니다. 앱이 변경되면 이전 데이터와 호환되지 않는 다른 데이터 집합이 포함되게 됩니다.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="번들에서 앱을 추가 또는 삭제(제거)하려면 어떻게 해야 합니까?">

앱이 포함된 번들을 변경하려면 원래 번들을 삭제하고 앱을 포함하는 번들을 새로 만듭니다.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="번들을 삭제하면 어떻게 됩니까?">

<div id="page-404" />

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### 번들을 삭제한 경우 발생하는 일에 대한 자주 묻는 질문

번들을 삭제한 경우:

* 앱스플라이어가 번들 어트리뷰트를 중지합니다.
* 번들 데이터는 유지되지만(즉, 영구적으로 삭제되지는 않음) 데이터를 보기 위해 번들 자체를 복원할 수는 없습니다.

  **이유는?** 이유는? 새 번들은 다른 웹 dev 키를 사용하기 때문에 동일한 앱을 포함하더라도 원래 번들은 복원되지 않습니다.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="번들에 추가할 때 특정 앱을 사용할 수 없는 이유는 무엇입니까?">

* 관리자 관리자: 번들을 생성할 때 앱을 선택할 수 없는 경우 앱이 앱스플라이어 계정에 추가되었고 다른 번들에 포함되어 있지 않은지 확인하십시오.
* 기타 계정 사용자: 추가하려는 앱에 액세스하는 데 필요한 역할과 권한이 있는지 계정 관리자에게 확인하십시오.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/onboarding-guide-to-people-based-attribution">PBA 온보딩 가이드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/people-based-attribution-pba-overview">PBA 시작하기</Anchor>

<div data-zendesk-anchors="about-brand-bundles=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EC%A0%95%EB%B3%B4 h_01HE0Y2A3A5W86YY44RWCTKM1Y=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EC%A0%95%EB%B3%B4 h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=%EC%9B%B9-%EC%95%B1%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C accessing-brand-bundles=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HE0Y2A3A7265NYM7GVBZVXEN=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EC%95%A1%EC%84%B8%EC%8A%A4 managing-brand-bundles=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EA%B4%80%EB%A6%AC h_01HE0Y2A3A272QJ4ZQH7VXJWCC=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%B2%88%EB%93%A4-%EA%B4%80%EB%A6%AC h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=%EC%A4%91%EC%9A%94 h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HE0Y2A3AB24NCNPAYFC0J4YH=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=%EB%B2%88%EB%93%A4%EC%9D%84-%EC%82%AD%EC%A0%9C%ED%95%9C-%EA%B2%BD%EC%9A%B0-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HE0Y2A3B276FV92EYBCZRA6C=%EB%B2%88%EB%93%A4%EC%9D%84-%EC%82%AD%EC%A0%9C%ED%95%9C-%EA%B2%BD%EC%9A%B0-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01HE0Y2KTXS06WHN57MQ91AD09=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
