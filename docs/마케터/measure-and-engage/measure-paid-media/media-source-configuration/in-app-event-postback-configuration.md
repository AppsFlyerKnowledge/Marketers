---
title: 인앱 이벤트 포스트백 구성
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-10-14T10:35:55Z'
  id: 208439256
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/208439256
---
> **한눈에 보기:** 인앱 이벤트 데이터를 활용하여 앱 인게이지먼트와 귀사의 유저의 가치를 측정하고 캠페인을 최적화합니다.

<div id="overview" />

## 개요

인앱 이벤트는 마케터가 다양한 소스에서 앱 인게이지먼트와 유저의 가치를 측정하고 적절한 유저 유입 전략을 수립할 수 있게 합니다. 광고 네트워크는 인앱 이벤트 정보를 사용하여 캠페인을 최적화하고 비용당 액션\/이벤트 캠페인을 실행합니다. 광고 네트워크는 실시간으로 전송되는 포스트백을 통해 인앱 이벤트 데이터를 수신합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">리치 인앱 이벤트에 대해 더 보기</Anchor>.

<div id="postback-in-app-event-selection" />

## 인앱 이벤트 포스트백 선택

마케터는 이 문서에 설명된 설정을 사용하여 광고 네트워크에 포스트백으로 발송할 인앱 이벤트를 선택할 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> * 인앱 이벤트에는 **거부된 이벤트**가 포함됩니다. 이는 Protect360에 의해 차단되었거나 대상 유효성 검증 규칙에 부합하지 않는 이벤트를 의미합니다.
> * **연동** 탭에 **인앱 이벤트 포스트백** 섹션이 없는 경우, 이는 파트너가 앱스플라이어와의 예비 구성에서 인앱 이벤트 기록을 설정하지 않았음을 의미합니다. 파트너는 <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">파트너 어시스턴트 위젯</Anchor>을 사용하여 앱스플라이어에 연락하여 연동을 완료할 수 있습니다.

<div id="in-app-event-postback-window" />

## 인앱 이벤트 포스트백 기간

인앱 이벤트 포스트백 기간을 설정하면, 네트워크와 CPA (행동당 비용) 기반으로 협력하는 마케터가 전환 후 이벤트 포스트백이 더 이상 전송되지 않는 기간을 구성할 수 있습니다.

예를 들어, 사용자가 인스톨 후 15일 이내에 발생하는 이벤트에 대한 요금이 청구되는 경우, 다음과 같이 기간을 설정하세요.

<Image alt="15일_인앱_이벤트_포스트백_설정.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

이 기간 이후에 포스트백은 전송되지 않고, 네트워크에 알림이 전달되지 않지만, 이벤트는 여전히 앱스플라이어에 기록되고 네트워크에 기인한 것으로 간주됩니다.

포스트백은 항상 **현재** 기간 설정에 따라 전송됩니다. 다음 예를 참조하십시오:

| 1월 1일 | 기간은 15일입니다.<br /><br />사용자가 앱을 인스톨합니다. |
| --- | --- |
| 1월 2일 | 기간이 10일로 변경되었습니다. |
| 1월 14일 | 사용자가 구매를 진행합니다.<br /><br />이벤트가 현재 기간 (10일)에 포함되지 않기 때문에 포스트백이 애드 네트워크로 전송되지 않았습니다. |
| 1월 15일 | 기간이 20일로 변경되었습니다. |
| 1월 18일 | 사용자가 다시 구매를 진행합니다.<br /><br />이번에는 이벤트가 현재 기간(20일)에 포함되므로 포스트백이 발송됩니다. |

<div id="note-1" />

> 📘 **참고**
>
> 이 [모든 미디어 소스, 유기적 설정 포함](#포스트백-발송-옵션)이 선택되면, 이 규칙은 적용되지 않습니다. 이 경우, 이 설정을 구성한 파트너는 광고주가 수신하는 모든 전환 이벤트에 대해 포스트백을 받습니다. **다른 파트너가 이벤트에 귀속되었더라도**, 이벤트가 포스트백 윈도우 내에서 발생한 한, 가능합니다. **이 설정을 구성한 파트너를 위해 정의된.**

<div id="default-postback-window" />

### 기본 포스트백 기간

인앱 이벤트 포스트백을 설정할 때 기본 기간은 자동으로 6개월로 설정됩니다.

<div id="note-2" />

> 📘 **참고**
>
> 2019년 7월 30일 이전에 특정 파트너와 인앱 이벤트 포스트백을 사용하기 시작한 경우 기간의 기본 설정은 평생입니다. 즉, 인앱 이벤트 포스트백은 항상 발송됩니다.

<div id="who-can-configure-postback-windows" />

### 포스트백 기간을 설정할 수 있는 사람

* 마케터
* 대행사는 **인앱 이벤트 포스트백 구성 허용** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">권한</Anchor>이 부여된 경우 설정 가능합니다.  
  **참고:** 동일한 애드 네트워크와 협력하는 마케터와 대행사는 네트워크와의 계약에 따라 각각 별도로 포스트백 기간을 설정할 수 있습니다.
* 파트너는 **인앱 이벤트 포스트백 구성 허용** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한</Anchor>이 부여된 경우 가능합니다.

<div id="event-mapping" />

## 이벤트 매핑

각 마케터는 같은 유형의 이벤트에도 다른 이름을 사용할 수 있습니다. 이런 이벤트 이름은 파트너 이름과 다를 수도 있습니다.

예를 들어, 사용자가 앱을 통해 무언가를 구입할 때 한 마케터는 이를 `purchase` 또는 덜 명확한 ID인 `event5`로 명명할 수 있고, 파트너는 이를 `purchase_event`로 명명할 수 있습니다.

마케터의 이벤트가 파트너의 동일한 이벤트와 일치하도록 하려면 이벤트 이름을 매핑해야 합니다.

<div id="note-3" />

> 📘 **참고**
>
> 특정 파트너 연동 탭에서 매핑된 이벤트는 표준과 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN 포스트백</Anchor> 모두에 적용됩니다.

<div id="mapping-methods" />

### 매핑 방법

각 파트너는 인앱 이벤트 매핑을 위한 다음 방법 중 어느 것을 사용할지 결정합니다:

* [파트너 이벤트 ID 입력](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [목록에서 이벤트 ID 선택](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [이벤트를 있는 그대로 발송(매핑 없음)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

<div id="note-4" />

> 📘 **참고**
>
> * 모든 매핑 방법이 모든 파트너에게 제공되지는 않습니다.
> * [파트너에게 자체 매핑을 수행할 수 있는 권한을 부여](/docs/in-app-event-postback-configuration#애드-네트워크에-의한-이벤트-매핑)할 수 있습니다.

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="파트너 이벤트 ID 입력">

* **앱스플라이어 이벤트**: 귀사의 앱 이벤트 목록에서 이벤트 선택.
* **파트너 이벤트**에 매핑됨: 텍스트 필드에 귀사의 앱 이벤트에 해당하는 파트너로부터 받은 이벤트 ID를 입력합니다.

<div id="note-5" />

> 📘 **참고**
>
> * 이벤트 이름은 대소문자를 구분합니다. 불일치를 피하려면 모든 매체 소스와 앱 버전에서 올바른 이벤트 이름을 사용하세요.
> * 이벤트 이름을 입력할 때 이벤트 이름 앞이나 뒤에 밑줄이 그어진 공백(언더바)을 사용할 수 있습니다. 앱스플라이어에서 보낸 이벤트 이름에 밑줄이 그어진 공백이 정확히 동일할 때만 사용해야 합니다.

[alt이벤트\_이름\_입력.pngalt](https://support.appsflyer.com/hc/article_attachments/30448114068753)

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="목록에서 이벤트 ID를 선택하세요.">

* **앱스플라이어 이벤트**: 귀사의 앱 이벤트 목록에서 이벤트를 선택하세요.
* **파트너 이벤트**에 매핑됨: 사전 정의된 파트너 이벤트 목록에서 귀사의 앱 이벤트에 해당하는 이벤트를 선택하세요.

[alt앱\_내\_이벤트\_포스트백\_en-us.pngalt](https://support.appsflyer.com/hc/article_attachments/30448114070033)

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="이벤트를 있는 그대로 매핑 없이 발송합니다.">

일부 파트너는 매핑되지 않은 인앱 이벤트 포스트백을 받는 것을 선호합니다. 즉, 이벤트 이름이 귀사의 앱에서 지정된 대로 발송되는 것을 의미합니다. 이벤트 이름이 `구매`, `유입`, 또는 `이벤트5`로 지정되었는지는 중요하지 않습니다.

파트너에게 발송할 매핑되지 않은 이벤트를 선택할 수 있습니다.

* **수동으로 추가:** 특정 이벤트를 선택하세요.
* **모든 이벤트 발송 (앱 삭제 및 세션 제외)**: 모든 귀사의 이벤트를 발송하세요. 여기에는 앱 삭제, 세션(앱 실행), 그리고 `af_app_opened` 이벤트는 포함되지 않습니다.

<div id="note-6" />

> 📘 **참고**
>
> 광고주가 의도치 않게 써드 파티 분석 플랫폼에 너무 많은 정보를 공유하는 것을 방지하기 위해, 2019년 3월부터 해당 플랫폼에서 **모든 이벤트 발송 (앱 삭제 및 세션 제외)** 옵션을 제거했습니다. 이 날짜 이전에 구성된 분석 플랫폼은 여전히 이 설정 옵션을 유지합니다.

**이벤트를 수동으로 추가하려면:**

1. **이벤트 추가**를 클릭하세요.
2. 포스트백 옵션을 선택하세요:
   * **앱스플라이어 이벤트**: 귀사의 앱 이벤트 목록에서 이벤트를 선택하세요.
   * **사용자에게서**: 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#for-users-from">발송 옵션</Anchor>을 선택하세요.
   * **포함하여**: 포스트백에 포함할 [데이터를 선택하세요](/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터).
3. 더 많은 이벤트에 대해서 이 과정을 반복하세요.

![포스트백을_그대로_보내세요_en-us.png](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**모든 이벤트 발송을 위해:**

1. **모든 이벤트 발송(제거 및 세션 제외)** 을 선택합니다.
2. 포스트백 옵션을 선택하세요:  
   * **사용자에게서**: 모든 이벤트에 대해 [발송 옵션](/docs/in-app-event-postback-configuration#포스트백-발송-옵션)을 선택하세요.
   * **포함하여**: 포스트백에서 모든 이벤트에 대해 [포함할 데이터를 선택합니다.](/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터)

![포스트백_맵핑_없음.png](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

이벤트 매핑에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">인앱 이벤트 포스트백</Anchor>을 참조하세요.

<div id="options-for-sending-postbacks" />

### 포스트백 발송 옵션

각 이벤트에 대해 어느 경우에 포스트백을 발송할지 선택할 수 있습니다 (포스트백 기간 내에서):

* **해당 파트너만:** 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다. 즉, 이벤트를 실행한 사용자가 이 파트너에서 온 경우입니다.
* **오가닉 포함 모든 매체 소스**: 모든 파트너에 어트리뷰션된 이벤트와 오가닉 이벤트에 대해 모든 매체 소스로 포스트백을 발송합니다. 즉, 이를 실행한 사용자가 어떤 매체 소스에서 온 경우입니다. **참고**: 오가닉 포함 모든 매체 소스가 선택되면 다른 파트너의 포스트백에는 어트리뷰션 데이터가 포함되지 않습니다.

<div id="data-to-include-in-the-postbacks" />

### 포스트백에 포함할 데이터

어떤 종류의 이벤트 데이터를 네트워크에 포스트백으로 공유할지 선택할 수 있습니다. 다음 옵션 중 하나를 선택하세요.

* **값 없음 및 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).
* **값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.
* **값 있음 & 수익 있음**: 수익 값(이벤트에 존재할 경우)을 포함한 모든 이벤트 파라미터를 전송합니다.
* 가치, 수익 및 순이익 이벤트의 모든 매개변수를 전송하십시오. 수익 값과 순수익 값(존재하는 경우)을 포함하여.

<div id="note-7" />

> 📘 **참고**
>
> 옵션은 **ROI360 고급** 구독이 필요하며 `af_purchase*` 및 `af_ars_*` 이벤트에 대해서만 사용할 수 있습니다.

광고 네트워크에서 귀사의 캠페인을 최적화하고 캠페인 결과를 개선하려면 수익 공유를 권장합니다. 그러나, 수익 공유는 필수 사항이 아닙니다. 이벤트 값에 `af_revenue` 또는 `af_projected_revenue`가 정의된 이벤트에 대해서만 수익 공유를 활성화해야 합니다. 그렇지 않으면 광고 네트워크에서 수익 값이 비어 있는 이벤트를 받습니다.

<div id="share-revenue" />

#### 수익 공유

포스트백에서 `af_revenue`과 `af_currency`는 event\_value JSON 외부에 `event_value`monetaryevent\_value와 **currency**로 작성되며 별도로 발송할 수 있습니다. 포스트백 구조 예시:

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

**값, 수익 및 순수익** 옵션이 선택되면, `af_net_revenue`는 `event_value` JSON 외부에 **순수 금전적**으로 작성되어 별도로 전송될 수 있습니다. 포스트백 구조 예시:

```http
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

<div id="note-8" />

> 📘 **참고**
>
> 또는 **값 및 수익 없음**을 선택할 때, 해당 매개변수는 N/A로 마스킹됩니다.

<div id="tip" />

> 📘 **팁**
>
> 앱 내 이벤트 포스트백을 구성하여 표준 수익(금전적) 매개변수에서 총 수익 대신 순수익을 전송할 수도 있습니다. 이 구성을 이용하려면 고객 성공 관리자(CSM)에게 문의하십시오.

<div id="h_01HBZCRNKGBEDSBZEY87KYQ60G" />

> 📄 **예시**
>
> 어떤 마케터가 다음 event\_value를 포함하여 구매 이벤트를 전송합니다: `event_value`event\_value
>
> ```json
> {"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}
> ```
>
> 아래 표는 파라미터가 발송되는 방식을 보여줍니다.
>
>
>
> | 필드 이름 | event\_value | 금전적 | 통화 | net-monetary |
> | --- | --- | --- | --- | --- |
> | **값 없음 & 수익 없음** | 해당 없음 | 해당 없음 | 해당 없음 | 해당 없음 |
> | **값 있음 & 수익 없음** | `{"af_currency":"N/A","af_content_id":"1234567","af_revenue":"N/A","af_content_type":"category_a"}&monetary=N/A&content_id=1234567` | 해당 없음 | 해당 없음 | 해당 없음 |
> | **값 있음 & 수익** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}&monetary=50.87&content_id=1234567` | 50.87 | USD | 해당 없음 |
> | **가치, 수익 및 순이익** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_net_revenue":35.61,"af_content_type":"category_a"}&monetary=50.87&net-monetary=35.61&content_id=1234567` | 50.87 | USD | 35.61 |

<div id="conditional-in-app-event-postbacks" />

### 조건부 인앱 이벤트 포스트백

다양한 이벤트에 매핑할 수 있는 여러 조건을 사용하여 인앱 이벤트 포스트백을 필터링합니다. 필터 조건을 충족하는 이벤트만 SRN 및 분석 파트너를 포함한 파트너에게 발송됩니다. 이 기능은 다음과 같은 경우에 유용합니다:

* 사용자 세분화, 개인화 및 리텐션 최적화
* 데이터 최소화
* 사용자 개인 정보 보호

<div id="h_01HBZCRNKHRTMHP3JPFVCS8D6N" />

> 📄 **예시**
>
> 게임 앱을 운영하는 마케터는 수준 10이나 수준 50을 달성한 사용자, 또는 앱 구매에 3달러를 지출한 사용자만을 대상으로 애드 네트워크를 통해 운영되는 캠페인을 최적화하려고 합니다.
>
> [altin_app_event_condition__1_.pngalt](https://support.appsflyer.com/hc/article_attachments/30448097840657)
>
> **이 이벤트에 대한 조건은 다음과 같이 설정됩니다.**
>
> * <strong><em>수준</em></strong> 이 <strong><em>10</em></strong>과 같으면 <em>`fb_mobile_level_acheived`</em>에 매핑합니다.
>   그렇지 않으면 (**또는**),
> * <strong><em>수준</em></strong> 이 <strong><em>50</em></strong>과 같으면 <em>`fb_mobile_level_acheived`</em>에 매핑합니다.
>   그렇지 않으면 (**또는**),
> * <strong><em>비용</em></strong> 이 <strong><em>3</em></strong>과 같으면 <em>`fb_mobile_purchase`</em>에 매핑합니다.

**이벤트에 대한 조건을 설정하려면:**

1. 파트너 연동 페이지에서 필수 인앱 이벤트를 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">정의하고 매핑합니다</Anchor>.
2. 조건 추가 ![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) 아이콘을 클릭하여 필요한 이벤트를 설정하세요.
3. <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#event-values">이벤트 값</Anchor>에 나타나는 대로 조건 필드를 입력하세요.
   * 속성 이름
   * 값
   * 조건을 매핑할 파트너 이벤트 (다음 [매핑 옵션](/docs/in-app-event-postback-configuration#매핑-방법) 중 하나 사용)
4. 더 많은 조건을 추가할 수 있지만, 먼저 기존 조건의 모든 필드를 입력해야 합니다.
5. **연동 저장**을 클릭합니다.

<div id="considerations" />

#### 고려 사항

조건을 구성할 때 이벤트가 파트너에게 전송되도록 하기 위해 다음 사항을 충족해야 합니다.

<div id="condition-structure" />

<Accordion title="조건 구조">

* 조건의 속성과 값은 모두 이벤트의 데이터와 일치해야 합니다.
* 현재 조건은 "동일"로만 설정할 수 있습니다.
* 배열과 같은 복잡한 구조는 지원되지 않습니다.

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="이벤트에 대한 여러 조건">

* 이벤트당 조건의 최대 개수는 5개입니다.
* 포스트백을 보내려면 최소한 하나의 조건이 충족되어야 하지만 실행되는 조건은 단 하나입니다.
* 각 조건은 나타나는 순서대로 확인됩니다. 즉, 가장 먼저 충족되는 조건이 실행됩니다.
* 각 조건은 별도로 매핑됩니다. 파트너 이벤트 이름이 **조건 기반**으로 변경되었습니다.
* 여러 조건이 동일한 속성이나 값을 가질 수 있지만, 두 개의 조건이 동일한 속성과 값을 모두 가질 수는 없습니다.
* 여러 조건을 동일한 이벤트에 매핑할 수 있습니다.

</Accordion>

<div id="note-9" />

> 📘 **참고**
>
> * 캠페인 최적화에 대한 영향을 이해하려면 시험 앱이나 사소한 이벤트에서 이 기능을 시험해 보는 것이 좋습니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">포스트백 콘텐츠</Anchor>를 보려면 로데이터 포스트백 리포트를 다운로드하세요.

<div id="editing-multiple-events" />

### 여러 이벤트 편집

이벤트를 매핑하는 동안  **사용자용**  및  **포함** 필드 값을 한 번의 작업으로 여러 이벤트에 대해 편집할 수 있습니다.

**여러 이벤트를 편집하려면:**

1. 업데이트할 이벤트를 선택하세요.
2. **대량 작업**을 클릭합니다.
3. 선택한 모든 이벤트에 적용할 새 설정을 선택하세요.
   * **사용자를 위한** (옵션 하나만 선택)
     * 해당 파트너
     * 오가닉을 포함한 모든 매체 소스
   * **포함** (옵션 하나만 선택)
     * 데이터 없음(기본값)
     * 수익 없는 값
     * 값과 수익

[alt앱\_내\_이벤트\_포스트백\_en-us.pngalt](https://support.appsflyer.com/hc/article_attachments/30448114091153)

<div id="custom-events" />

### 커스텀 이벤트

매핑에 사용할 수 있는 이벤트 목록에는 SDK에서 이미 보고된 이벤트 또는 앱스플라이어로 전송된 서버-투-서버 이벤트만 표시됩니다. 매핑하려는 이벤트가 드롭다운 목록에 나타나지 않는 경우에는 다음과 같은 이유가 있을 수 있습니다.

* 아직 사용자가 해당 이벤트를 수행하지 않았습니다.
* 마지막으로 해당 이벤트가 발생한 지 2주가 지났습니다.
* 활성화된 이벤트 목록이 너무 많습니다.

**이 경우, 이벤트를 파트너 ID에 매핑하려면:**

1. 드롭다운 목록에서 **+ 항목 추가**를 클릭합니다.
2. 텍스트 상자에 추가하려는 이벤트의 이름을 입력합니다.
3. 확인하려면 V 표시를 클릭하세요. 이제 추가한 이벤트가 목록에 나타나고 선택할 수 있습니다. ![add-custom-event-name.jpg](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. 이벤트를 파트너 식별자에 매핑하세요.
5. 매핑이 기록되었는지 확인하려면 **연동 저장**을 클릭하세요.

<div id="note-10" />

> 📘 **참고**
>
> * 포스트백 페이지에 커스텀 이벤트를 추가해도 귀사의 앱에서 해당 이벤트가 자동으로 가져오지 않습니다. 적절한 기능을 위해 SDK나 S2S에서 이벤트를 구성해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#이벤트-발송">앱스플라이어에 이벤트를 발송하는 방법</Anchor>을 참조하세요.
> * 특정 파트너에 커스텀 이벤트를 추가하면 해당 이벤트가 모든 파트너의 이벤트 목록에 추가됩니다. 즉, 모든 파트너의 이벤트 드롭다운 목록에 이 이벤트가 표시됩니다.
> * 이벤트 이름과 파라미터 정의에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#tips">팁</Anchor>과 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#limitations">제한 사항</Anchor>을 확인하세요.

**대행사 및 애드 네트워크:**

* 커스텀 이벤트를 추가할 수 없습니다.
* 마케터가 이벤트를 추가하고 필요한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한</Anchor>을 부여한 후에만 이벤트를 보거나 매핑할 수 있습니다.

<div id="event-mapping-by-ad-networks" />

## 애드 네트워크에 의한 이벤트 매핑

마케터는 광고 네트워크가 이벤트를 스스로 매핑하도록 허용할 수 있습니다. 이를 위해 마케터는 애드 네트워크에 관련 권한을 부여해야 합니다.

1. **활성화된 연동** 페이지에서 권한 부여 대상 파트너를 찾으세요.
2. 권한 탭에서 **인앱 이벤트 포스트백 구성 허용** 토글을 **켜기**로 전환하세요.

![adnetwork-permissions-postbacks.png](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

애드 네트워크가 권한을 받으면 [텍스트 필드에 이벤트 ID 입력](/docs/in-app-event-postback-configuration#매핑-방법)의 지침에 따라 이벤트를 매핑할 수 있습니다.

<div id="event-mapping-by-agencies" />

## 대행사에 의한 이벤트 매핑

마케터는 에이전트가 인앱이벤트 포스트백을 설정하도록 허용할 수 있습니다.

<div id="note-11" />

> 📘 **참고**
>
> 광고주와 대행사가 동일한 인앱 이벤트 포스트백을 동일한 애드 네트워크에 대해 활성화하면, AppsFlyer는 포스트백을 한 번만 전송합니다. 이것은 이벤트의 중복 리포팅을 방지합니다.

**에이전시에게 인앱 이벤트 포스트백을 설정할 수 있는 권한을 부여하려면:**

1. **활성화된 연동** 페이지에서 대행사를 찾으세요.
2. 대행사가 모든 이벤트를 공유할지, 아니면 특정 애드 네트워크에 귀속된 이벤트만 공유할지 선택하세요.
3. 대행사가 이벤트 수익을 발송할 수 있는지 여부를 선택하세요.
4. 대행사가 공유할 수 있는 특정 이벤트를 선택하세요.

![대행사-이벤트.png](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

<div id="h_01HDP3XHBPA5GZEVERMBN43JH0" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">리치 인앱 이벤트—개요</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure">리치 인앱 이벤트—이벤트 구조</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HE0FQ1AB6NQCTKFTDW22SRYC=%EA%B0%9C%EC%9A%94 postback-inapp-event-selection=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A0%ED%83%9D h_01HBZCRNKGH1PAK8RC846PPRTS=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A0%ED%83%9D h_01HBZCRNKGQTJ4VJ00TVTS14N2=%EC%B0%B8%EA%B3%A0 inapp-event-postback-window=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84 h_01HBZCRNKGS71QGK5506N07K84=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84 h_01K9MBNYC6PPHXSZ3KNVNSDASJ=%EC%B0%B8%EA%B3%A0-1 default-postback-window=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84 h_01HBZCRNKGV5CREN5K0RBDMBH6=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84 h_01HBZCRNKGVXN233AFFHG42NW9=%EC%B0%B8%EA%B3%A0-2 who-can-configure-postback-windows=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%82%AC%EB%9E%8C h_01HBZCRNKG7AECFSBXV2WDD9AR=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EA%B8%B0%EA%B0%84%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%82%AC%EB%9E%8C event-mapping=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HBZCRNKG7SZ4T41BY60BAJZN=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HBZCRNKGT64TE2XYK9VS4ATD=%EC%B0%B8%EA%B3%A0-3 mapping-methods=%EB%A7%A4%ED%95%91-%EB%B0%A9%EB%B2%95 h_01HBZCRNKG4EF9MSY696SD5VQ9=%EB%A7%A4%ED%95%91-%EB%B0%A9%EB%B2%95 h_01HBZCVAGPSNDJMWRWENEP45N7=%EC%B0%B8%EA%B3%A0-4 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=%EC%B0%B8%EA%B3%A0-5 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=%EC%B0%B8%EA%B3%A0-6 options-for-sending-postbacks=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%B0%9C%EC%86%A1-%EC%98%B5%EC%85%98 h_01HBZCRNKG1VN7E6TVCPDW7M73=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%B0%9C%EC%86%A1-%EC%98%B5%EC%85%98 data-to-include-in-the-postbacks=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1%EC%97%90-%ED%8F%AC%ED%95%A8%ED%95%A0-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HBZCRNKGESY50NSZGTVPT25M=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1%EC%97%90-%ED%8F%AC%ED%95%A8%ED%95%A0-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01KRKDVVV246YZYGM5G2ZJR63W=%EC%B0%B8%EA%B3%A0-7 sharing-revenue=%EC%88%98%EC%9D%B5-%EA%B3%B5%EC%9C%A0 01J9Y0T400M5Z62Q9CKF8M75WR=%EC%88%98%EC%9D%B5-%EA%B3%B5%EC%9C%A0 h_01KRKDVVV2YF4XMKNCVEG1FFSG=%EC%B0%B8%EA%B3%A0-8 h_01KRKDVVV242YPHP2W8EWTBSMD=%ED%8C%81 h_01HBZCRNKGBEDSBZEY87KYQ60G=%EC%98%88%EC%8B%9C conditional-inapp-event-postbacks=%EC%A1%B0%EA%B1%B4%EB%B6%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HBZCRNKG5X3B2NJZZP6ER2CX=%EC%A1%B0%EA%B1%B4%EB%B6%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HBZCRNKHRTMHP3JPFVCS8D6N=%EC%98%88%EC%8B%9C-1 considerations=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HBZCRNKHBR57YVHZQP7NJBAP=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=%EC%B0%B8%EA%B3%A0-9 editing-multiple-events=%EC%97%AC%EB%9F%AC-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8E%B8%EC%A7%91 h_01HBZCRNKHHD3WC4GTJT9NSJ4C=%EC%97%AC%EB%9F%AC-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8E%B8%EC%A7%91 custom-events=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HBZCRNKH754PANWSZ4FMXJVQ=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HBZCRNKH4PVR3FEMTMERW3M1=%EC%B0%B8%EA%B3%A0-10 event-mapping-by-ad-networks=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HBZCRNKH1GCZY17R04WTZ0MQ=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 event-mapping-by-agencies=%EB%8C%80%ED%96%89%EC%82%AC%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HBZCRNKHHF3E6CZNQQG0Q4VS=%EB%8C%80%ED%96%89%EC%82%AC%EC%97%90-%EC%9D%98%ED%95%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01K5B6QS6YXKMJSEWE2WFT5AQC=%EC%B0%B8%EA%B3%A0-11 h_01HDP3XHBPA5GZEVERMBN43JH0=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
