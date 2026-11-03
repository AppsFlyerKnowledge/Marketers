---
title: 로데이터 콘텐츠 제한 – 미디어 소스 또는 유저 식별자
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-10-14T10:35:46Z'
  id: 360006868017
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/360006868017
---
> **요약:** 일부 파트너는 특정 로데이터 리포트의 특정 필드를 제한하도록 앱스플라이어에 요구합니다. 다른 경우, 파트너는 써드 파티 플랫폼에 포스트백을 공유할 때 미디어 소스를 삭제해달라고 요청할 수 있습니다. 이 문서에서는 이러한 제한사항과 그에 따른 의미를 설명합니다.

## 로데이터 제한

앱스플라이어는 광고주의 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> 설정이나 데이터를 제공하는 광고 네트워크의 데이터 공유 정책에 따라 특정 로데이터 리포트 필드에 대한 액세스가 제한됩니다. 이러한 제한은 리포트의 유형과 제한 이유에 따라 달라집니다.

### 미디어 소스 제한

다음 표는 전환, 클릭, 노출에 대한 미디어 소스별 제한 사항을 나열합니다.

> 📘 **참고사항**
>
> * 데이터 집약형 어트리뷰션 및 분석 데이터는 제한 없이 제공됩니다. 그러나 모든 포스트백과 디바이스 단위 리포트에는 아래에 설명된 제한이 적용됩니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/discrepancies-between-appsflyer-and-third-party-platforms#타사-플랫폼에-대한-포스트백-제한">써드 파티 플랫폼에 대한 포스트백 제한:</Anchor>
>   * 아래 표에 설명된 제한 사항은 써드 파티 플랫폼으로 전송되는 포스트백에 포함된 이벤트에 적용됩니다.
>   * 다른 이벤트에는 추가적인 포스트백 제한이 적용될 수 있습니다.

| 미디어 소스 | 어트리뷰션 유형 제한 |
| --- | --- |
| <span id="amazon-ads"></span>아마존 광고 | Amazon Ads의 로데이터는 앱스플라이어 플랫폼에서 제한됩니다. 결과적으로 미디어 소스는 "제한됨"으로 보고되며 캠페인 세부 정보는 null로 처리됩니다.<br /><br />모든 SRN과 마찬가지로 Amazon의 클릭과 노출은 로데이터 리포트에 포함되지 않습니다. |
| <span id="meta-ads"></span>Meta Ads | <ul><li>클릭-쓰루 및 뷰-쓰루 어트리뷰션 데이터가 제한됩니다.</li><li>AEM 딥 링크 솔루션(iOS)의 데이터와 구글 플레이 인스톨 리퍼러 및 Meta 인스톨 리퍼러(안드로이드)의 데이터는 디바이스 단위 리포트에서 제한 없이 제공됩니다.</li></ul><ul><li>Meta Ads의 클릭과 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="pinterest"></span>핀터레스트 | <ul><li>클릭-쓰루 및 뷰-쓰루 어트리뷰션 데이터가 제한됩니다.</li><li>핀터레스트의 클릭과 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="reddit"></span>레딧 | <ul><li>2024년 10월 22일부터 Reddit의 로데이터가 앱스플라이어 플랫폼에서 제한됩니다. 이로 인해 미디어 소스는 '제한됨'으로 보고됩니다. Reddit의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="roku-oneview"></span>로쿠 원뷰 | <ul><li>2024년 4월 18일 이전의 Roku OneView 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="samsung-dsp"></span>삼성 DSP | <ul><li>2023년 10월 17일부터 Samsung DSP의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="snapchat"></span>스냅챗 | <ul><li>2023년 3월 1일부터 스냅챗 언인스톨은 로데이터 리포트에 포함되지 않습니다.</li><li>뷰-쓰루 어트리뷰션은 제한적입니다. 다음은 로데이터 전달 도구에 포함되지 않습니다.<ul><li>미디어 소스 (snapchat\_int)</li><li>채널</li><li>어트리뷰트 터치 유형(노출)</li><li>귀속된 터치 시간(날짜로만 보고됨 - "dd\/mm\/yyyy")</li><li>캠페인은 *"제한됨"*으로 보고됩니다.</li></ul></li><li>스냅챗의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |
| <span id="tiktok-for-business"></span>TikTok for Business | <ul><li>미디어 소스 (bytedanceglobal\_int 및 tiktokglobal\_int)<ul><li>채널</li><li>어트리뷰트 터치 유형(노출)</li><li>귀속된 터치 시간(날짜로만 보고됨 - "dd\/mm\/yyyy")</li><li>캠페인은 *"제한됨"*으로 보고됩니다.</li></ul></li><li>bytedanceglobal\_int의 노출은 로데이터 리포트에서 제한됩니다.</li><li>tiktokglobal\_int의 클릭 및 노출 로데이터 리포트는 데이터 락커를 통해 제한됩니다.</li></ul> |
| <span id="x-ads-formerly-twitter"></span>X Ads(이전의 트위터) | <ul><li>일부 경우, X Ads는 로데이터를 앱스플라이어 플랫폼에서 사용할 수 없도록 합니다. 이런 경우에는 이벤트가 로데이터 리포트에 나타나지 않습니다.</li><li>X Ads의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.</li></ul> |

### 로데이터 컨텍스트

로데이터의 필드 수준 제한은 다음 표에 나열된 데이터의 컨텍스트에 따라 달라집니다.

| 제한 유형 | 영향을 받는 보고서 |
| --- | --- |
| [제한된 미디어 소스](/docs/about-raw-data-identifier-restrictions#미디어-소스-제한): 사용자가 어느 소스에서 왔는지 | <ul><li>어트리뷰션: 인스톨, 리타겟팅 전환, 언인스톨</li><li>인앱 이벤트, 세션</li><li>Protect360 보고서</li></ul> |
| 완전히 제한됨 | <ul><li>클릭</li><li>노출</li><li>차단된 클릭 (Protect360)</li></ul> |

**로데이터 전달**

앱스플라이어의 유저 수준 어트리뷰션 데이터는 다음 로데이터 전달 도구를 사용하여 제공됩니다:

* 데이터 락커
* 로데이터 Pull API
* 푸시 API
* 대시보드 내보내기 페이지
* 네트워크에 포스트백
* 클라이언트 측 유저 수준 데이터 API의 컨텍스트에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">전환 데이터(GCD) API 가져오기</Anchor>

<div id="unavailable-attribution-fields" />

<Accordion title="사용할 수 없는 어트리뷰션 필드">

미디어 소스가 제한된 경우 다음 필드를 사용할 수 없습니다:

| 표시 이름 | API 이름 |
| --- | --- |
| 광고 | af\_ad |
| 광고 ID | af\_ad\_id |
| 광고 유형 | af\_ad\_type |
| 광고 세트 | af\_adset |
| 광고 세트 ID | af\_adset\_id |
| 어트리뷰션 룩백 윈도우 | af\_attribution\_lookback |
| 캠페인 ID | af\_c\_id |
| 채널 | af\_channel |
| 비용 통화 | af\_cost\_currency |
| 비용 모델 | af\_cost\_model |
| 비용 값 | af\_cost\_value |
| 키워드 | af\_keywords |
| 파트너 | af\_prt |
| 사이트 ID | af\_siteid |
| 하위 사이트 ID | af\_sub\_siteid |
| 하위 매개변수 [n] (n=1-5) | af\_sub[n] (n=1-5) |
| 귀속된 터치 시간 | attributed\_touch\_time |
| 귀속된 터치 유형 | attributed\_touch\_type |
| 캠페인 | campaign |
| 기여자[n] 미디어 소스 (n=1-3) | contributor[n]\_media\_source (n=1-3) |
| 기여자[n] 파트너 (n=1-3) | contributor[n]\_af\_prt (n=1-3) |
| 기여자[n] 캠페인 (n=1-3) | contributor[n]\_campaign (n=1-3) |
| 기여자[n] 측정 유형 (n=1-3) | contributor[n]\_match\_type (n=1-3) |
| 기여자[n] 터치 시간 (n=1-3) | contributor[n]\_touch\_time (n=1-3) |
| 기여자[n] 터치 유형 (n=1-3) | contributor[n]\_touch\_type (n=1-3) |
| 딥링크 URL | deeplink\_url |
| HTTP 레퍼러 | http\_referrer |
| 애플 앱 스토어 설치 | install\_app\_store |
| 키워드 ID | keyword\_id |
| 키워드 측정 유형 | keyword\_match\_type |
| 측정 유형 | match\_type |
| 네트워크 계정 ID | network\_account\_id |
| 원본 URL | original\_url |
| 리인게이지먼트 기간 | af\_reengagement\_window |
| 스토어 제품 페이지 | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="식별자 제한">

식별자 제한이 적용될 때, 다음 표에 나열된 필드만 로데이터 리포트에서 사용할 수 있습니다.

| API 이름 |
| --- |
| <span id="event_time"></span>이벤트 시간 |
| <span id="event_name"></span>이벤트 이름 |
| <span id="event_revenue"></span>이벤트 수익 |
| <span id="event_revenue_currency"></span>이벤트 수익 통화 |
| <span id="event_revenue_usd"></span>이벤트 수익 USD |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>이벤트 소스 |
| <span id="media_source"></span>미디어 소스 |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>리타겟팅 여부 |
| <span id="retargeting_conversion_type"></span>리타겟팅\_전환\_유형 |
| <span id="is_primary_attribution"></span>1차\_어트리뷰션 |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>국가 코드 |
| <span id="blocked_reason"></span>차단 이유 |
| <span id="blocked_reason_value"></span>차단 이유 값 |
| <span id="blocked_reason_rule"></span>차단 이유 규칙 |
| <span id="blocked_sub_reason"></span>차단된 하위 이유 |
| <span id="platform"></span>플랫폼 |
| <span id="is_paid_media"></span>유료 매체인가 |

</Accordion>

## 자주 묻는 질문

<div id="what-events-are-restricted" />

<Accordion title="어떤 이벤트가 제한되나요?">

[위 표](/docs/about-raw-data-identifier-restrictions#미디어-소스-제한)에 자세히 설명된 제한된 이벤트에는 전환(인스톨 및 재참여) 및 제한 애드 네트워크에 기인한 인앱 이벤트가 포함될 수 있습니다.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="제한된 미디어 소스는 로데이터 리포트에 어떤 영향을 미칠까요?">

* *미디어 소스* 필드는 *제한됨*으로 표시됩니다.
* 이 문서에 나열된 어트리뷰션 필드는 비어 있거나 *null*로 표시됩니다.

**리포트 예시:** CSV 파일에 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">제한된 로데이터</Anchor>로 인스톨합니다. 다른 로데이터 리포트도 비슷한 방식으로 처리됩니다.

</Accordion>

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="제한된 미디어 소스가 파트너에게 전송되는 포스트백에 어떤 영향을 미칠까요?">

파트너에게 전송된 포스트백에는 어트리뷰션 필드가 포함되지 않습니다.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="제한된 이벤트가 써드 파티 플랫폼으로의 포스트백에 어떤 영향을 미칠까요?">

[위 표](#미디어-소스-제한)에 나열된 어트리뷰션된 애드 네트워크의 포스트백은 써드 파티 플랫폼으로 전송되지 않습니다.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="제한되지 않은 이벤트가 써드 파티 플랫폼으로의 포스트백에 영향을 미칠까요?">

<Anchor target="_blank" href="/marketers/ko/docs/discrepancies-between-appsflyer-and-third-party-platforms#타사-플랫폼에-대한-포스트백-제한">어떤 경우에는</Anchor> 제한이 없는 이벤트의 포스트백에 미디어 소스가 포함되지 않을 수 있습니다. 이는 어트리뷰션이 오가닉으로 간주된다는 의미입니다.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="어트리뷰션의 일부로 사용되는 지원 데이터는 어떻게 처리되나요?">

지원과 관련된 데이터는 어트리뷰션 데이터로 간주되어 제공되지 않습니다.

</Accordion>

> 📄 **참고 자료**
>
> <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">유저 수준 데이터 리텐션</Anchor>

<div data-zendesk-anchors="raw-data-restriction=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C 01H7WQHTV9RM2JF2BV45XF626H=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C media-source-restrictions=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EC%A0%9C%ED%95%9C 01H7WQHTV9HJEHHH1N8VN6APX6=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EC%A0%9C%ED%95%9C 01H7WQHTV90YFRP3Z9AEP7ACRD=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD raw-data-context=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8 01H7WQHTVA8H9FTBJ1FB6BJQ2A=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%BB%A8%ED%85%8D%EC%8A%A4%ED%8A%B8 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H7WQHTVA5439QPE6GNXNKJ63=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=%EC%B0%B8%EA%B3%A0-%EC%9E%90%EB%A3%8C" />
