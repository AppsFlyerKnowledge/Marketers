---
title: 메타 광고 불일치
metadata:
  keywords:
    - Facebook
    - Advertisers
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
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2026-10-14T10:33:44Z'
  id: 4410481130641
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/4410481130641
---
> **한눈에 보기:** 요약: 페이스북 광고와 앱스플라이어 사이의 어트리뷰션 모델의 차이점에 대해 자세히 알아봅니다.

## 앱스플라이어와의 메타 광고 불일치

모바일 유저 유입 생태계에서 중요한 선도 기업인 앱스플라이어와 페이스북은 어트리뷰션 모델에 차이가 있습니다. 이로 인해 메타 광고와 앱스플라이어 대시보드 간에 불일치가 발생할 수 있습니다.

이 차이를 줄이기 위해서 앱스플라이어는 페이스북과 긴밀히 협조하고 있지만, 광고주는 다음의 원인에 대해서 알고 있어야 합니다.

### 앱스플라이어 광고와 메타 광고의 불일치 감지

메타 광고 이벤트 매니저에 나열된 **이벤트** 와 앱스플라이어 보고서에 나열된 이벤트를 비교합니다. 이벤트 개수가 현저히 차이나는 경우 불일치가 발생할 수 있습니다.

## 어트리뷰션 모델의 차이점

<table><thead><tr><th>1. 일으키다. 2. 발생시키다. </th><th>Meta Ads</th><th>앱스플라이어</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>클릭 어트리뷰션 룩백 기간</strong></td><td>7일(<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">기본값이 차이 나게 되는 특수한 경우가 있다는 점</a>을 알아두십시오).</td><td>1-30일. 메타 광고의 경우 7일로 설정해야 합니다.</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>뷰-쓰루 어트리뷰션 룩백 윈도우</strong></td><td>1일(<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">기본값이 차이 나게 되는 특수한 경우가 있다는 점</a>을 알아두십시오).</td><td>기본 1일, 그러나 1시간 - 48시간 사이에서 설정 가능(기본값 유지 권장)</td></tr><tr><td><span id="multichannel-sourceattribution"></span> <br/><strong>어트리뷰션</strong> </td><td>Meta 광고는 다른 미디어 소스에 관계없이 자체 속성 설치를 합니다.</td><td></td></tr><tr><td><span id="crossdevice-attribution"></span><strong>크로스 디바이스 어트리뷰션</strong></td><td>페이스북은 다양한 기기, 예를 들면, iOS/안드로이드/데스크톱에서의 클릭 및 인스톨까지 해당 사용자로 어트리뷰션합니다.</td><td>앱스플라이어는 인게이지먼트와 인스톨이 모두 이루어진 단일 기기에 대해서만 어트리뷰션합니다.</td></tr><tr><td><span id="different-time-zones"></span><strong>다른 표준 시간대</strong></td><td>메타 광고의 기본 보고 시간대는 PST입니다.  <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">메타 광고 관리자에서</a> 앱스플라이어의 앱 설정에 정의된 앱 시간대와 일치하도록 변경해야 합니다.</td><td>앱스플라이어의 기본 앱 시간대는 UTC+0입니다. <a href="./app-settings#localization-time-zone" target="_blank">앱 설정 페이지</a>에서 앱에 설정된 시간대를 페이스북 광고 관리자에 정의된 시간대와 일치하도록 변경할 수도 있습니다.</td></tr><tr><td><span id="google-install-referrer"></span><strong>인스톨 리퍼러:</strong></td><td colspan="2"> </td></tr></tbody></table>

## 클릭-쓰루 및 뷰-쓰루 어트리뷰션

앱스플라이어는 클릭-쓰루 및 뷰-쓰루 어트리뷰션을 모두 지원합니다. 메타 광고와 앱스플라이어 간의 불일치를 최소화하려면 클릭연결 및 조회 완료 확인 창이 모두 메타 광고에 정의된 기본 기간과 일치하는지 확인하세요.

Meta 광고의 기본 클릭연결 전환 확인 기간은 7일로 정의됩니다. [기본값이 다른 경우도](https://www.facebook.com/business/help/395050428485124?id=428636648170202)있지만, 앱스플라이어의 클릭연결 전환 확인 기간을 7일로 설정하여 모든 메타 광고의 기본 옵션을 포함하는 것이 좋습니다.

![image (13).png](https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png)

> 📄 **예시**
>
> 앱스플라이어에서는 메타 광고 클릭 전환 확인 기간이 앱 com.greatapp에 대해 1일로 구성되어 있고 메타 광고에서는 기본값이 7일이라고 가정합니다. 페이스북에서 greateapp의 광고를 클릭했지만 앱 최초 실행은 클릭 이후 2&#126;7일째에 시행한 사용자의 경우, 앱스플라이어는 오가닉 사용자로 어트리뷰트하지만 페이스북은 해당 사용자를 자체적으로 보고합니다.

### 제한된 미디어 차이

2021년 10월 28일까지 뷰-쓰루 어트리뷰션(VTA)에서 가져온 사용자의 어트리뷰션 데이터는 제한되었으며 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">광고주가 사용할 수 없습니다</Anchor>.  
2021년 10월 29일부터 시작하여 상기 제한은 뷰-쓰루 어트리뷰션 및 클릭-쓰루 어트리뷰션 모두에서 가져온 사용자에게 적용됩니다. 집약형 리포트는 이로부터 영향을 받지 않습니다.

메타 광고는 사용자 수준 데이터를 전송하지 않으므로 앱스플라이어는 전환 지원 노출 및 클릭을 메타 광고로 어트리뷰션하지 않을 수 있습니다.

> 📄 **예시**
>
> 1. 사용자는 AwesomeApp에 대한 페이스북에서의 광고를 보거나 클릭하게 됩니다. 그런 다음 AwesomeApp에 대한 GreatAdNetwork 광고를 보고 클릭하여 설치합니다.
> 2. Meta 광고는 전환 확인 기간 내에 발생한 전환이라고 주장합니다.
> 3. 앱스플라이어는 인스톨 전 마지막 인게이지먼트를 맺었기 때문에 GreatAdNetwork로의 전환을 어트리뷰트합니다.
> 4. 앱스플라이어는 메타 광고의 원시 데이터가 제한되어 있으므로 메타 광고를 전환 지원 네트워크로 간주하지 않습니다.
>    * 제한되지 않습니다.
>    * 로데이터 리포트에서 확인할 수 있습니다.

하지만 클릭-쓰루 어트리뷰션의 경우 광고에서 사용자들을 구글 플레이 스토어로 리디렉트하면, 어트리뷰션 필드들은 Google 인스톨 리퍼러의 광고주들이 이용할 수 있습니다. 레퍼러를 통해 제공되는 필드는 사용자가 사용할 수 있는 앱스플라이어 로데이터 리포트에 입력되며 앱스플라이어에서 광고 ID(LAT-사용 가능)가 없는 사용자를 어트리뷰트할 수 있게 합니다.

## 인앱 이벤트 차이

플랫폼 간의 차이는 페이스북 및 앱스플라이어에 표시되는 설치 후 이벤트(예: 인앱 구매)에서도 나타날 수 있습니다. 다음 표에서는 이런 차이가 나타나는 일반적인 원인과 이를 최소화하는 방법에 대해 설명합니다.

| 1. 일으키다. 2. 발생시키다. | 설명 | 앱스플라이어 팁 |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**서로 다른 사용자 라이프 타임 정의** | 메타 광고를 사용하는 사용자의 전체 기간은 최대 7일로 정의되며, 이는 메타 광고가 광고 클릭 후 7일 이상 발생한 경우 이벤트가 표시되지 않음을 의미합니다.  <br />앱스플라이어에서 메타 광고 사용자의 수명은 최대 180일로 정의됩니다. | 7일 후에 발생한 페이스북 캠페인의 사용자 가치를 평가할 때 앱스플라이어의 데이터를 사용하여 더 넓게 이해하십시오. |
| <span id="unmapped-events"></span>**매핑되지 않은 이벤트** | 앱스플라이어는 SDK가 생성한 이벤트를 수신하지만, 페이스북으로 매핑하지 않았다면 전송되지 않습니다. | 사용자의 품질을 나타내는 모든 인앱 이벤트를 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping">Meta 광고로 매핑</Anchor> 해야 합니다. |
| <span id="unsent-revenue"></span>**전송되지 않은 수익** | 앱스플라이어는 SDK가 생성한 이벤트로부터 수익을 받지만, 이 수익은 페이스북으로 전송되지 않습니다. | 인앱 이벤트의 **수익 전송** 상자가 항상 체크되어 있는지 확인합니다. 예를 들어, 아래 캡처 화면의 구매 이벤트를 들 수 있습니다. |
| <span id="missing-event-values-on-facebook"></span>**메타 광고에서 누락된 이벤트 값** | 올바른 구조를 가지고 있으면, 앱스플라이어는 이벤트 매핑의 일부로 파라미터와 값(event value)을 페이스북에 전송합니다. | 페이스북과 이벤트 값을 완전 매핑하려면 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure">앱스플라이어 권장 구조</Anchor>에 따라 SDK 인앱 이벤트를 구축해야 합니다. |
|  <span id="different-event-count"></span>|  | 더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#데이터-차이-및-불일치에-대한-정보">여기</Anchor>를 참고하십시오. 액티비티(Activity) |

## 나의 UA 대시보드에서 리인게이지먼트 캠페인으로부터의 설치란?

리인게이지먼트 캠페인을 통해 사용자가 이미 설치된 앱을 열 수 있습니다(**리인게이지먼트**). 또는, 앱스플라이어가 같은 기기에서 있었던 앱의 이전 설치를 인식했을 때, 앱스플라이어는 그 전환을 **리어트리뷰션**으로 간주할 수 있습니다.

리인게이지먼트 캠페인에서 Meta 광고가 **신규 사용자** 또는 최초 설치 후 설정된 리어 **<Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">트리뷰션 기간을</Anchor>초과** **한 후** 앱을 처음 설치한 사용자를 타게팅하는 경우, 이러한 사용자는 **앱스플라이어에 신규 사용자 획득 설치**로 기록되며, 이는 메타 광고의 리인게이지먼트 캠페인에 속합니다.

반면에, 기존 설치 후 **설정된 리어트리뷰션 기간 내**에 앱 설치가 이루어지면, 페이스북에서는 신규 설치로 표시될 수 있지만, 앱스플라이어에서는 리어트리뷰션으로 간주하고 앱스플라이어 리타겟팅 페이지에 표시됩니다.

> 📘 **참고**
>
> 트위터는 리타겟팅 캠페인의 모든 앱 설치를 한 곳에서 보여주지만, 앱스플라이어 대시보드에서는 앱 설치를 개요 페이지(신규 설치)와 리타겟팅 페이지(리어트리뷰션 및 리인게이지먼트)에 나눠서 표시합니다.

## 크로스 디바이스 어트리뷰션

Meta 광고는 교차 기기 기여에 대해 보고합니다. 때로는 어떤 플랫폼(iOS/안드로이드)의 캠페인이 다른 플랫폼의 인스톨로 표시되는 문제를 발생시킬 수 있습니다.

> 📄 **예시**
>
> 린다는 안드로이드 휴대전화를 사용하여 페이스북에서 GreatApp의 모바일 광고를 클릭합니다. 메타 광고는 원래 안드로이드 타겟팅 캠페인 '안드로이드 Females'에서 린다가 수행한 클릭을 기록합니다. Linda는 집에 있는 iPad에 GreatApp을 설치하기로 마음먹습니다. 앱스플라이어는 처음 출시되자마자 메타 광고에 iOS 설치의 출처를 묻고, 페이스북은 "안드로이드 여성" 캠페인으로 답변합니다.

## 유효성 검증 규칙 및 Protect360

<Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">앱스플라이어의 검증 규칙을</Anchor>사용하는 경우, 원래 메타 광고에서 발생한 설치가 거부된 경우 앱스플라이어와 메타 광고 간에 결과가 다를 수 있습니다. 이 경우에 페이스북은 인스톨을 자체 보고하지만, 앱스플라이어는 인스톨로 기록하지 않습니다.

마찬가지로, 앱스플라이어의 사기 방지 솔루션, Protect360을 사용하고 있을 때, 페이스북은 자체 보고하지만 앱스플라이어는 인스톨로 기록하지 않는 경우가 있습니다.

> 📄 **예시**
>
> GreatApp의 UA 매니저 제프는 북미의 스페인어 사용자만을 타겟으로 하는 SPNA 캠페인을 만듭니다. 이를 검증하기 위해 제프는 캐나다와 미국 사용자만 수용하는 검증 규칙을 정의합니다.
> 스페인의 Meta 광고 사용자가 앱을 클릭하여 설치하면 Meta 광고는 설치를 자체 보고하지만 앱스플라이어는 유효성 검사 규칙을 통과하지 못한 설치를 거부합니다.

## SDK 관련 불일치

<Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#who-needs-facebooks-sdk">광고주가 앱스플라이어와 Facebook Ads SDK를 모두 구현하는 경우가 여러 번</Anchor> 있을 수 있습니다. 이로 인해 인앱이벤트 모두에 대해 불일치가 발생할 수 있습니다. 즉, Meta 광고는 수익 및 기타 이벤트를 허위로 보고할 수 있습니다.

* 다음 방법 중 하나를 사용하여 Meta 광고에서 중복 인앱 이벤트 보고를 방지하세요.
  * 페이스북 SDK에서 이벤트를 설정하지 마십시오.
  * 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping">메타 광고 인앱 이벤트 매핑</Anchor> 을 비활성화합니다.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80%EC%9D%98-%EB%A9%94%ED%83%80-%EA%B4%91%EA%B3%A0-%EB%B6%88%EC%9D%BC%EC%B9%98 01H890CZSXPMK0BDMC4202HNYM=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80%EC%9D%98-%EB%A9%94%ED%83%80-%EA%B4%91%EA%B3%A0-%EB%B6%88%EC%9D%BC%EC%B9%98 detect-a-discrepancy-between-appsflyer-and-facebook=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B4%91%EA%B3%A0%EC%99%80-%EB%A9%94%ED%83%80-%EA%B4%91%EA%B3%A0%EC%9D%98-%EB%B6%88%EC%9D%BC%EC%B9%98-%EA%B0%90%EC%A7%80 01H890CZSXGHVBH21SQA0671JQ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B4%91%EA%B3%A0%EC%99%80-%EB%A9%94%ED%83%80-%EA%B4%91%EA%B3%A0%EC%9D%98-%EB%B6%88%EC%9D%BC%EC%B9%98-%EA%B0%90%EC%A7%80 differences-in-attribution-models=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%AA%A8%EB%8D%B8%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90 01H890CZSX8M6VGGREYX4W2X37=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%AA%A8%EB%8D%B8%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90 clickthrough-and-viewthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%B0%8F-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H890CZSX40JDGY8P8AQ4CYGS=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%B0%8F-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H890CZSXRD7PCZBK52GW7QE9=%EC%98%88%EC%8B%9C restricted-media-discrepancies=%EC%A0%9C%ED%95%9C%EB%90%9C-%EB%AF%B8%EB%94%94%EC%96%B4-%EC%B0%A8%EC%9D%B4 01H890CZSX5WFX5Q0RNSG01GFH=%EC%A0%9C%ED%95%9C%EB%90%9C-%EB%AF%B8%EB%94%94%EC%96%B4-%EC%B0%A8%EC%9D%B4 01H890CZSX567CQ3ZWZS5F05XW=%EC%98%88%EC%8B%9C-1 inapp-events-differences=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B0%A8%EC%9D%B4 01H890CZSXKC5JKK9051MC0VY6=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B0%A8%EC%9D%B4 installs-from-reengagement-campaigns-in-my-ua-dashboard=%EB%82%98%EC%9D%98-ua-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9C%BC%EB%A1%9C%EB%B6%80%ED%84%B0%EC%9D%98-%EC%84%A4%EC%B9%98%EB%9E%80 01H890CZSYE21K7PBQK4PNMGJR=%EB%82%98%EC%9D%98-ua-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9C%BC%EB%A1%9C%EB%B6%80%ED%84%B0%EC%9D%98-%EC%84%A4%EC%B9%98%EB%9E%80 01H890CZSY7TRCA4NVKSVPY7DB=%EC%B0%B8%EA%B3%A0 crossdevice-attribution::77a37a1f=%ED%81%AC%EB%A1%9C%EC%8A%A4-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H890CZSYS8QKEAF6799SBS8J=%ED%81%AC%EB%A1%9C%EC%8A%A4-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H890CZSY2Z3S6E9R5MYC1CHX=%EC%98%88%EC%8B%9C-2 validation-rules-and-protect360=%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D-%EA%B7%9C%EC%B9%99-%EB%B0%8F-protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%A6%9D-%EA%B7%9C%EC%B9%99-%EB%B0%8F-protect360 01H890CZSYCTQZCAYAZP9TCBBF=%EC%98%88%EC%8B%9C-3 sdk-related-discrepancies=sdk-%EA%B4%80%EB%A0%A8-%EB%B6%88%EC%9D%BC%EC%B9%98 01H890CZSYVFPQP0SKNPWMPB1R=sdk-%EA%B4%80%EB%A0%A8-%EB%B6%88%EC%9D%BC%EC%B9%98" />
