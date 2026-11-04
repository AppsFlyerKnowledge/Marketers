---
title: iOS Meta Ads 데이터 집약형 이벤트 측정(AEM)
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
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-14T10:33:14Z'
  id: 19228737402129
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/19228737402129
---
> **한눈에 보기:** iOS 전환 및 인앱 이벤트를 최적화하고, Meta Ads 에서 iOS 리인게이지먼트 성과를 측정하기 위한 AEM 솔루션에 대해 알아보세요.

<div id="overview" />

## 개요

앱스플라이어는 <Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Meta Ads 데이터 집약형 이벤트 측정(AEM)</Anchor> 솔루션을 지원합니다. 이 솔루션을 통해 다음 어트리뷰션 방법을 사용하여 iOS 14+ 디바이스의 웹 및 앱 이벤트를 측정할 수 있습니다:

* [리인게이지먼트를 위한 앱 AEM](#리인게이지먼트를-위한-앱-aem)
* [앱 프로모션을 위한 앱 AEM](#앱-프로모션을-위한-앱-aem)

AEM 솔루션의 일환으로, Meta는 이벤트가 AEM에 적합한 경우 앱스플라이어로부터 전환 및 인앱 포스트백을 수락합니다. 이벤트의 AEM 적합성을 확인하려면 다음을 참조하세요:

* [앱 이벤트가 AEM에 적합한지 확인하기](#앱-이벤트가-aem에-적합한지-확인하기)

<div id="app-aem-for-re-engagement" />

## 리인게이지먼트를 위한 앱 AEM

AEM을 통해 Meta Ads는 디바이스 ID 없이 iOS 사용자의 딥 링크 리인게이지먼트 어트리뷰션을 얻습니다.

<div id="attribution-flow" />

### 어트리뷰션 플로우

Meta Ads는 AEM `campaign_ids`식별자와 함께 딥 링크에 어트리뷰션 데이터를 추가합니다. 앱스플라이어는 딥 링크에 표시된 데이터와 함께 식별자를 수신하면:

* 데이터 집약형 리포팅 데이터를 Meta Ads로 다시 보냅니다.
* Meta Ads에서 추가한 딥 링크 정보를 기반으로 어트리뷰션을 수행합니다.
* 딥 링크 어트리뷰션 데이터를 로데이터와 데이터 집약형 리포트에 포함합니다.

<div id="attribution-data-parameters" />

### 어트리뷰션 데이터 파라미터

Meta Ads에서 제공하는 다음 어트리뷰션 데이터 파라미터가 보고서에 포함됩니다:

* `ad_id`
* `adgroup_id`
* `campaign_id`
* `campaign_group_id`
* `account_id`

<div id="faqs-on-deep-link-re-engagement-attribution" />

### 딥 링크 리인게이지먼트 어트리뷰션 FAQ

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="광고주는 이러한 어트리뷰션을 활성화하려면 무엇을 해야 합니까?">

이러한 파라미터를 수신하기 위해 광고주가 **별도로 조치를 취할 필요는 없습니다**.

그러나 딥 링크 리인게이지먼트 어트리뷰션을 측정하려면 **리인게이지먼트 어트리뷰션 토글**을 **사용 설정**해야 합니다.

**참고:** Meta Ads의 AEM 관련 이용 약관에 따르면, Meta Ads에서 리인게이지먼트 어트리뷰션 측정을 활성화하면 모든 포스트백에 부분 IP 주소가 포함됩니다.

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="에이전시 및 Meta 캠페인 관리 파트너는 어떻게 되나요?">

현재로서는 에이전시 및 Meta 캠페인 관리 파트너에 대한 어트리뷰션이 지원되지 않습니다. 즉, 모든 트래픽이 Meta Ads에 어트리뷰션됩니다. 이는 일시적이며 곧 변경될 예정입니다.

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="이 어트리뷰션의 데이터에 대해 제한 사항이 있습니까?">

딥 링크 어트리뷰션에서 오는 데이터는 리포팅 제한이 없습니다. 즉, 모든 데이터가 데이터 집약형 로데이터 리포트와 사용자 수준 로데이터 리포트에 모두 표시됩니다.

</Accordion>

<div id="app-aem-for-app-promotion" />

## 앱 프로모션을 위한 앱 AEM

<div id="aem-eligibility" />

### AEM 자격

앱이 Meta Ads에서 AEM을 사용할 수 있는 경우, 광고 세트 생성 프로세스 중 기본적으로 **집약된 이벤트 측정**이 선택됩니다. 즉, AEM과 SKAN을 모두 캠페인에서 동시에 사용할 수 있습니다. 대신 **Apple의 SKAdNetwork**를 선택하면 SKAN만 캠페인에 적용됩니다. 이는 앱스플라이어가 Meta Ads에서 앱 액티비티를 측정할 수 있는 능력이 제한적이라는 것을 의미합니다.

<Image alt="aem_meta_ads_platform.png" src="https://support.appsflyer.com/hc/article_attachments/19228698538769" width="563px" />

<div id="note-1" />

> 📘 **참고**
>
> AEM 적합성에 문제가 있는 경우, [앱 이벤트가 AEM에 적합한지 확인하기](#앱-이벤트가-aem에-적합한지-확인하기)를 참조하세요.

<div id="aem-data-sharing" />

### AEM 데이터 공유

**고급 데이터 공유** 기능을 통해 모든 전환 이벤트를 Meta Ads와 공유할 수 있으며, ATT 동의 상태와 관계없이 모든 설치 및 후속 인앱 이벤트에 대한 어트리뷰션 데이터를 확보할 수 있습니다.

* 기능을 비활성화할 경우, ATT 프롬프트에 동의한 유저의 전환 이벤트만 공유됩니다. 즉, 미동의 유저의 이벤트는 Meta Ads로 공유되지 않으며 어트리뷰션 데이터에서도 제외됩니다.
* 기능을 활성화하면, ATT 동의 상태와 관계없이 모든 유저의 전환 이벤트를 전송할 수 있습니다. 앱스플라이어는 이러한 이벤트에 대한 어트리뷰션을 수행합니다. 공유되는 데이터에는 디바이스 ID를 포함하지 않는 추가적인 기기 관련 정보가 포함될 수 있습니다. 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#advanced_data_sharing">고급 데이터 공유</Anchor>를 참조하세요.

![aem](https://support.appsflyer.com/hc/article_attachments/19228710265361)

<div id="note-2" />

> 📘 **Note**
>
> * 모든 이벤트에는 인스톨, 앱 열기 및 인앱 이벤트가 포함됩니다.
> * **고급 데이터 공유**를 활성화하기 전에 제3자에 의한 데이터 사용을 포함하여 이러한 공유가 귀하에게 적용되는 모든 플랫폼 정책 및/또는 규정을 준수하는지 확인하세요. 공유되는 데이터에는 IP 주소, anon\_ids(사용 가능한 경우), vendor\_id 및 user agents가 포함될 수 있습니다.
> * Server-to-Server (S2S)을 통해 전송된 인앱 이벤트의 경우, Meta는 이벤트 페이로드에 **IP 주소**와 **벤더 식별자 (IDFV)** 가 포함되어야 합니다. 해당 식별자가 없으면, 해당 이벤트는 Meta의 AEM 어트리뷰션 대상에서 제외됩니다.
> * 앱 프로모션을 위한 Meta AEM은 비확정적 뷰 쓰루 클레임을 포함할 수 있습니다. Meta AEM을 통한 비확정적 뷰 쓰루 어트리뷰션 (View-through Attribution)을 지원하려면, 앱 레벨의 **확률적 모델링을 통한 뷰 쓰루 어트리뷰션 활성화** 토글이 켜져 있는지 확인하십시오. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">확률적 모델링을 통한 뷰 쓰루 어트리뷰션</Anchor>을 참조하세요.

<div id="check-if-your-app-events-are-eligible-for-aem" />

## 앱 이벤트가 AEM에 적합한지 확인하기

Meta 이벤트 관리자에 방문하여 앱 이벤트가 AEM에 적합한지 확인할 수 있습니다. 앱 이벤트가 적합해지면, 광고 관리자 (Ads Manager) 에서 선택한 AEM 캠페인의 결과를 볼 수 있습니다. 앱 이벤트가 AEM에 적합한지 파악하는 구체적인 방법은 <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">Meta 문서</Anchor>를 참조하세요.

<div id="enable-aem-summary" />

## AEM 활성화 방법 - 요약

아래 표를 사용하여 앱스플라이어에서 Meta 광고 AEM을 활성화하기 위한 빠른 체크리스트로 사용하세요.

| **솔루션** | **토글** | **토글 위치** | **영향** |
| --- | --- | --- | --- |
| **AEM 리마케팅 (리인게이지먼트)** | 리인게이지먼트 어트리뷰션 | 파트너 연동 (Meta Ads) | 리마케팅을 위해 AEM을 활성화합니다 (리인게이지먼트 어트리뷰션). |
| **AEM 앱 프로모션 (설치)** | 고급 데이터 공유 | 파트너 연동 (Meta Ads) | 앱 프로모션을 위해 AEM을 활성화하며, ATT 옵트아웃 사용자로부터의 공유 이벤트와 비결정론적 어트리뷰션을 수락합니다 (해당되는 경우). |
| **AEM 앱 프로모션 (설치)** | 확률적 모델링을 통해 광고 조회 어트리뷰션 활성화 | 앱 설정 (App Settings) | 비확정적 성과 측정에 대한 뷰 쓰루 어트리뷰션을 활성화합니다. |

<div id="troubleshooting" />

## 문제 해결

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Meta AEM 측정 부적합 이벤트 해결 방법">

Meta 광고가 앱 이벤트를 자격이 없다고 표시하는 경우—**“누락된 옵트아웃 이벤트”** 와 같은 오류 또는 기타 AEM 관련 메시지를 표시하는 경우—일반적으로 누락되었거나 잘못 설정된 데이터 때문입니다. 아래 체크리스트를 사용하여 일반적인 문제를 진단하고 수정하세요.

<div id="important" />

> 🚧 **중요!**
>
> 아래 단계를 완료한 후 변경 사항이 적용될 시간을 허용하세요. 변경 사항이 적용된 후, Meta Ads는 AEM 자격을 반영하는 데 최대 **2–3일**이 걸릴 수 있습니다.

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="1단계: 고급 데이터 공유 기능 활성화 확인">

1. **Collaborate**> **Active Integrations(활성 연동) >** Meta Ads.
2. **고급 데이터 공유**가 켜져 있는지 확인하세요.

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="2단계: IP 마스킹이 비활성화 확인">

마스킹된 IP가 있는 이벤트는 AEM에 자격이 없습니다.

* **앱 설정 (App Settings)** 으로 이동.
* **IP 마스킹**이 꺼져 있는지 확인세요.

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="3단계: Server-to-Server (S2S) 이벤트 필수 파라미터 포함 확인">

모든 S2S 이벤트는 다음을 포함해야 합니다:

* **(IP 주소)**
* **IDFV** (벤더 식별자)

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="4단계: ATT 동의율 검토">

Meta는 IDF가 누락되었거나 0으로 설정된 이벤트에 대해 제한된 수량만을 수용합니다. 해당 임계치를 초과할 경우, 다음과 같은 오류 메시지가 표시될 수 있습니다: **광고주 추적 허용 파라미터 수치가 허용 범위를 벗어났습니다.**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="5단계: 포스트백 매핑 설정 확인">

이벤트 포스트백이 **모든 전송(오가닉 포함)** 에 매핑되었는지 확인하세요.

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="5단계: 리인게이지먼트 설정 확인(해당되는 경우)">

리인게이지먼트 캠페인

* **리인게이지먼트 어트리뷰션**을 **앱 설정** 및 **메타 활성 연동 페이지** 모두에서 활성화하세요.

</Accordion>

<div id="still-not-working" />

#### 아직도 작동하지 않나요?

특정 이벤트가 여전히 적합하지 않은 경우:

1. Meta의 이벤트 관리자에 가서 화면의 안내를 따르세요.
2. 영향을 받는 앱 이벤트를 선택하세요.
3. **MMP 트래픽**을 선호하는 연결 방법으로 설정하십시오.

<div id="need-help" />

#### 도움이 필요하신가요?

문제가 지속되면:

* 기술 지원 요청 티켓 제출하기
* 자격이 없는 이벤트를 보여주는 Meta Ads의 스크린샷을 포함해주세요.

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="캠페인이 AEM 자격이 있음에도 불구하고 대시보드와 보고서에서 AEM 데이터를 받지 못합니다.">

여기 Meta의 답변이 있습니다: “현재 MMP와 협력하여 향후 몇 달에 걸쳐 이 업데이트를 순차적으로 적용하고 있습니다. 이에 따라 업데이트가 완전히 완료될 때까지 일부 광고주는 해당 기능을 사용하지 못할 수 있습니다.”

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="AMM에 동의했는데도 왜 로데이터 리포트에서 AEM 어트리뷰션 설치 성과를 확인할 수 없나요?">

AAP가 활성화된 경우, Meta의 AEM을 통해 어트리뷰션된 설치 데이터는 로데이터 리포트에서 제외됩니다. 이것은 AMM에 동의한 경우에도 동일하게 적용됩니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HCAM4CEVRCG13CA32B0GM9QS=%EA%B0%9C%EC%9A%94 app-aem-for-reengagement=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%95%B1-aem 01H88ZM20H99W37M0H6XXQVMQA=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%95%B1-aem attribution-flow=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 01H7YJVNMV7QSZJWKZZA9042K6=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 attribution-data-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H7YJVNMVPPCD08Z2R0V5GCMY=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 faqs-on-deep-link-reengagement-attribution=%EB%94%A5-%EB%A7%81%ED%81%AC-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-faq 01H7YJVNMV4ZKMWKD06RC6GKFW=%EB%94%A5-%EB%A7%81%ED%81%AC-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-faq 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%C2%A0attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=%EC%95%B1-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%95%B1-aem 01H88ZM20HQFMG962AZGYA98FR=%EC%95%B1-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%95%B1-aem aem-eligibility=aem-%EC%9E%90%EA%B2%A9 01H7YJVNMVPB054VFS60KH9N7W=aem-%EC%9E%90%EA%B2%A9 h_01HR886Q0KPM99FCQXD6RDPSBK=%EC%B0%B8%EA%B3%A0 aem-data-sharing=aem-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 01H88ZM20HK2HY32M4BKZ4N0B9=aem-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 01H7YK9CHHNARCD7M2VZRMEW6S=note check-eligibility=%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EA%B0%80-aem%EC%97%90-%EC%A0%81%ED%95%A9%ED%95%9C%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0 01JBHQSHF8NA4SGVJ3WYPRN9B3=%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EA%B0%80-aem%EC%97%90-%EC%A0%81%ED%95%A9%ED%95%9C%EC%A7%80-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0 enable-aem-toggles-summary=aem-%ED%99%9C%EC%84%B1%ED%99%94-%EB%B0%A9%EB%B2%95---%EC%9A%94%EC%95%BD h_01KJ28ETP9GK6TBTJK8SBZ5PFW=aem-%ED%99%9C%EC%84%B1%ED%99%94-%EB%B0%A9%EB%B2%95---%EC%9A%94%EC%95%BD faqs-and-troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01H7YK9CHHZN78CBHFTQ7E9RKQ=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=%EC%A4%91%EC%9A%94 h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94 h_01K722GQSB8CXSSCVZPA3R3CJX=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94 need-help=%EB%8F%84%EC%9B%80%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%98%EC%8B%A0%EA%B0%80%EC%9A%94 h_01K722GQSBBB8KS8JNRBJZ4WWT=%EB%8F%84%EC%9B%80%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%98%EC%8B%A0%EA%B0%80%EC%9A%94 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%E2%80%99t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />
