---
title: 메타 광고 인앱 이벤트 매핑
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-10-14T10:37:45Z'
  id: 4410480904081
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/4410480904081
---
> **한눈에 보기:** 한눈에 보기: 앱의 풍부한 인앱이벤트를 앱스플라이어에서 메타 광고로 전송하세요.

## 메타 인앱이벤트 매핑

광고주는 인앱이벤트(SDK 또는 서버 간)를 메타 사전 정의 이벤트에 매핑합니다. 광고주는 또한 각 <Anchor target="_blank" href="/marketers/ko/docs/measure-sessions">앱 실행</Anchor> 또는 확인된 모든 <Anchor target="_blank" href="/marketers/ko/docs/measure-uninstalls#앱-삭제-이벤트-매핑">앱 삭제</Anchor>에 대해 페이스북에 포스트백을 보낼 수 있습니다.

이를 통해 광고주는 메타의 고급 최적화 기능을 활용하고 맞춤 및 유사 타겟 세그먼트를 구축할 수 있습니다.

### 사전 정의된 이벤트 매핑

메타 광고는 <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">넓은 범위의 이벤트</Anchor>를 미리 정의해 놓고 매핑할 수 있도록 제공합니다.

<Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure">여기</Anchor>에서 메타로 전송할 수 있는 **리치 인앱** 이벤트 목록과 이벤트 **품질에 대한 추가 정보**를 제공하는 추가 파라미터를 확인하세요.

<Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#inapp-event-mapping">메타에서 이벤트를 매핑하는</Anchor> 방법에 대해 자세히 알아보세요.

[alt앱\_내\_이벤트\_포스트백\_en-us.pngalt](https://support.appsflyer.com/hc/article_attachments/51858084853137)

메타 광고에 삭제 효과를 전송하기 위해 미리 정의된 이벤트는 없습니다. 앱 제거를 보내려면 [사용자 정의 이벤트](/docs/meta-ads-in-app-event-mapping#커스텀-인앱-이벤트-매핑)를 사용하십시오.

다음은 추가 파라미터가 없는 다른 사전 정의 메타 이벤트 목록입니다.

| 메타 이벤트 식별자 | 설명 | 앱스플라이어 SDK 용 추천 이름 |
| --- | --- | --- |
| Donate | 조직이나 목적에 자금을 기부. | af\_donate |
| Schedule | 지점 중 한 곳을 방문 예약. | af\_schedule |
| SubmitApplication | 상품, 서비스 또는 프로그램 (신용카드, 교육 프로그램, 구인 공고) 등에 신청서 제출. | af\_submit\_application |
| FindLocation | 방문할 목적으로, 지점 위치를 웹이나 앱으로 검색. 예를 들어, 제품을 검색하고 이를 광고주의 지점 중 하나에서 찾음. | af\_find\_location |
| Contact | 고객과 광고주 사업 사이에 전화나 문자 메시지, 이메일, 채팅 또는 다른 유형으로 연락. | af\_contact |
| CustomizeProduct | 광고주의 응용 프로그램이나 설정 도구를 이용해 제품을 맞춤 설정. | af\_customize\_product |
| `Adimpression`안드로이드의 경우Adimpression:  <br />`Fb_mobile_purchase`iOS의 경우:Fb\_mobile\_purchase |  | af\_ad\_revenue |


<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th></th><th><span id="mapping-ad-revenue-data-for-campaign-optimization"></span>플랫폼</th><th><strong>매핑된 파트너 이벤트 이름</strong></th><th></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>안드로이드</td><td>AdImpression</td><td></td></tr><tr><td>iOS</td><td>fb_mobile_purchase</td><td>인앱 구매</td></tr></tbody></table>


* <span id="availability-limitations"></span>현재 **Adimpression** 이벤트를 통한 최적화는 다음 사항에만 사용할 수 있습니다.
  * 안드로이드 앱. iOS 앱은 *fb\_mobile\_purchase* 이벤트를 사용하여 광고 수익 데이터를 계속 전송할 수 있습니다.
  * Meta의 기준에 부합하는 선택된 Meta ads 계정. 계정이 회색으로 표시되면 [자격 요건이 충족되지 않았을 수 있습니다](https://www.facebook.com/business/help/571188993373447?id=561906377587030).
* 이 *af\_ad\_revenue* 이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-cost-and-revenue-data">ROI360 고급 패키지</Anchor>가 포함된 플랜에서만 사용할 수 있습니다.
  * ROI360이 아닌 플랜은 다른 이벤트 이름을 사용하여 광고 수익 데이터를 보낼 수 있습니다.

### 커스텀 인앱 이벤트 매핑

앱스플라이어를 사용하면 커스텀 메타 이벤트 식별자 옵션을 사용하여 메타로 전송할 커스텀 인앱이벤트를 매핑할 수 있습니다.

SDK에 설정된 이벤트 이름 및 이벤트 값(이벤트 파라미터 포함)은 페이스북에 전달되고 "사용자정의"가 아닌 기존 앱스플라이어 SDK 이벤트 이름으로 표시됩니다.

<Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">이러한 이벤트를 사용하여 캠페인을 최적화</Anchor>할 수 있다는 것을 알아두십시오.

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### 사용자정의 이벤트와 자동 파라미터 매핑

페이스북과 앱스플라이어의 밀접한 연동을 통해서, 앱스플라이어의 많은 표준 SDK 이벤트 파라미터는 페이스북 사전 정의 파라미터로 자동 매핑됩니다. 예를 들면, **af\_revenue** 파라미터는 페이스북의 **valueToSum** 파라미터로 변환됩니다. 따라서 페이스북에서 측정하고 최적화할 수 있는 이벤트당 수익을 전송할 수 있습니다.

> 📘 **참고**
>
> 파라미터 자동 매핑은 커스텀과 사전 정의된 이벤트 간에 다를 수 있습니다.
>
> 커스텀으로 매핑된 이벤트의 경우, **af\_price**는 항상 **fb\_price**에 매핑되며, **af\_revenue**는 **\_valueToSum**에 매핑됩니다.

다음 표는 커스텀 이벤트를 통해서 페이스북에 매핑될 때, 페이스북 파라미터로 자동 매핑되는 모든 앱스플라이어 이벤트 파라미터를 나타냅니다.

| 앱스플라이어 파라미터 | 메타 파라미터 |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_콘텐츠\_유형 | fb\_content\_type |
| af\_country | fb\_국가 |
| af\_통화 | fb\_통화 |
| af\_date\_a | fb\_체크인\_날짜 |
| af\_date\_b | fb\_체크아웃\_날짜 |
| af\_departing\_arrival\_date | fb\_출발\_도착\_날짜 |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_설명 | fb\_설명 |
| af\_목적지\_a | fb\_출발지\_공항 |
| af\_목적지\_b | fb\_destination\_airport |
| af\_목적지\_목록 | fb\_목적지\_ID |
| af\_호텔\_점수 | fb\_호텔\_점수 |
| af\_수준 | fb\_수준 |
| af\_max\_rating\_value | fb\_최대\_평가\_값 |
| af\_성인\_수 | fb\_성인\_수 |
| af\_어린이\_수 | fb\_어린이\_수 |
| af\_유아\_수 | fb\_유아\_수 |
| af\_주문\_id | fb\_주문\_ID |
| af\_결제\_정보\_사용 가능 | fb\_payment\_info\_available |
| af\_선호하는\_지역 | fb\_선호\_지역 |
| af\_선호하는\_경유지 | fb\_선호\_정류장\_수 |
| af\_선호\_가격대 | fb\_선호\_가격대 |
| af\_선호\_별점\_평가 | fb\_선호\_별점\_평가 |
| af\_가격 | fb\_가격 |
| af\_수량 | fb\_항목\_수 |
| af\_지역 | fb\_지역 |
| af\_registration\_method | fb\_registration\_method |
| af\_귀국 도착 날짜 | fb\_returning\_arrival\_date |
| af\_귀국 출발 날짜 | fb\_귀국 출발 날짜 |
| af\_수익 | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |


| **<span id="value-to-sum"></span>Meta event** |  |
| --- | --- |
| fb\_모바일\_수준\_달성 | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_가격 |
| fb\_mobile\_add\_to\_wishlist | af\_가격 |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_모바일\_결제\_시작 | af\_가격 |
| fb\_mobile\_purchase | af\_수익 |
| fb\_모바일\_평가 | af\_등급\_값 |
| fb\_mobile\_search | af\_수익 |
| fb\_mobile\_spent\_credits | af\_가격 |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_가격 |
| StartTrial | af\_가격 |
| Subscribe | af\_수익 |

## 이벤트 및 파라미터 제한

다음 제한은 [사용자가 페이스북 광고에 보낸 이벤트](https://developers.facebook.com/docs/app-events/faq#limits)에 적용됩니다.

* 다음 문자는 사용할 수 없습니다.
  * 콜론(:)
  * 마침표(.)
  * 비라틴어(영어) 문자 집합: 2020년 1월 12일부터 Meta 광고에서는 중국어 문자를 거부합니다. AppsFlyer는 다른 문자 세트를 테스트하지 않았으며 포스트백에서 이러한 문자 세트를 지원하는지 메타로 확인한 후에만 사용해야 합니다.
* 이벤트 이름은 대소문자를 구분합니다. 수치 차이를 피하려면, 모든 미디어소스 및 앱 버전의 이벤트 이름에 정확한 대소문자를 사용하세요.
* 최대 파라미터 개수: 25. 24,033.07
* 이벤트 이름 및 파라미터 길이: 2–40. 0 - 5달러
* 2-40자
* 1000자입니다.
* 비 라틴(영어) 문자를 사용하지 마십시오. 비 라틴 문자를 사용하면 결과가 일치하지 않을 수 있습니다.

인앱 이벤트 명명과 관련된 고려 사항:

* 앱스플라이어의 이벤트 이름은 메타 이벤트 이름과 동일하게 지정할 수 있지만(예: fb\_price), 메타에 커스텀 이벤트로 전송해서는 안 됩니다.  
  **안전을 위해 메타 이벤트 이름과 동일한 이벤트 이름을 지정하지 마세요.**
* 메타에서 인앱이벤트 포스트백 매핑을 수행하려면 오가닉을 포함한 모든 소스에서 이벤트 데이터를 가져오세요.

> 🚧 **중요!**
>
> 위의 파라미터를 제외하고, 앱스플라이어는 커스텀 이벤트 데이터를 **있는 그대로** 메타로 전송합니다. 이벤트 데이터가 유효한 메타 파라미터를 사용하여 메타 요구 사항을 준수하는지 확인하는 것은 앱 소유자의 책임입니다(위 표 참조). 그렇지 않으면 이러한 파라미터가 메타로 전송되지 않습니다.

<div data-zendesk-anchors="facebook-iae-mapping=%EB%A9%94%ED%83%80-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01J1WCP44CHN0Q73P6DN7H8FKG=%EB%A9%94%ED%83%80-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 predefined-event-mapping=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01J1WCP44D18WMXCMHJ0FNF6Y0=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 01JAPZ6M11HSCE9QNN5NSD61FK=mapping-ad-revenue-data-for-campaign-optimization 01JAQ1ECZVR8SZ81KE6CDD08A2=availability-limitations custom-inapp-events-mapping=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01J1WCP44DK14AC5ZG4KTFFFSC=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 automatic-parameter-mapping-with-the-custom-event=%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%9E%90%EB%8F%99-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 h_01J1WCP44D645TS6JFGM2BDGM9=%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%9E%90%EB%8F%99-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 h_01J1WCP44DSZ7G3603W5EBWZEW=%EC%B0%B8%EA%B3%A0 01JATBG1SZRRZ0PCANKQ6S8CX4=value-to-sum event-and-parameter-limitations=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%8F-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%A0%9C%ED%95%9C h_01J1WCP44DF2QMV10VXF8NQZ7W=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%8F-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%A0%9C%ED%95%9C h_01J1WCP44D9SNEYZG59KNM822K=%EC%A4%91%EC%9A%94" />
