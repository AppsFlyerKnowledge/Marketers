---
title: 트래픽 리졸루션 정보
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-14T10:27:50Z'
  id: 43518064765201
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43518064765201
---
> **At a glance:** 랜딩 페이지 로드 시 확인 가능한 URL 파라미터와 리퍼러 데이터를 활용하여, 각 웹 방문의 최초 미디어 소스, 캠페인 및 채널을 식별하려면 트래픽 소스 리졸루션을 사용하세요. 이를 통해 어트리뷰션에 필요한 트래픽 소스 컨텍스트를 제공하여 신규 사용자 유입 이벤트를 포함한 하위 웹 이벤트를 정확하게 어트리뷰션할 수 있습니다.

<div id="what-is-traffic-source-resolution" />

## 트래픽 소스 리졸루션이란 무엇인가요?

웹 어트리뷰션의 경우, 랜딩 페이지 로드(**웹 방문**)는 사용자가 웹사이트와 갖는 첫 번째 참여입니다. 앱스플라이어는 URL 파라미터 및 리퍼러 데이터와 같이 당시에 확인 가능한 정보를 기반으로 사용자의 미디어 소스, 캠페인, 채널을 식별합니다.

**트래픽 소스 리졸루션**으로 알려진 이 프로세스는 URL 파라미터에서 미디어 소스 및 캠페인 정보를 식별하고 리졸루션합니다. 앱스플라이어는 이러한 파라미터를 수집하고 우선순위를 지정하여 방문에 대한 초기 트래픽 소스 컨텍스트를 결정합니다.

트래픽 소스 리졸루션은 **프리 어트리뷰션 프로세스**입니다. 리졸루션된 파라미터는 이후 <Anchor target="_blank" href="/marketers/ko/docs/web-performance-measurement-overview#웹-성과-측정-플로우">어트리뷰션 프로세스</Anchor> 동안 재정의될 수 있습니다.

트래픽 소스 리졸루션의 역할은 방문에서 끝나지 않습니다. 이 결과는 어트리뷰션 프로세스가 향후 신규 사용자 획득 이벤트를 포함한 후속 웹 이벤트를 어트리뷰션할 때 사용하는 트래픽 소스 컨텍스트를 제공합니다.

트래픽 소스 리졸루션의 메커니즘을 이해하는 것은 정확한 URL을 생성하기 위해 필수적입니다. 올바른 구조의 URL을 생성하는 방법을 알아보려면, <Anchor target="_blank" href="/marketers/ko/docs/choose-attribution-parameters-for-landing-page-urls">랜딩 페이지 URL용 어트리뷰션 파라미터 선택하기</Anchor>를 참조하세요.

<div id="the-traffic-source-resolution-flow" />

## 트래픽 소스 리졸루션 흐름

트래픽 소스 리졸루션은 각 웹 방문에 대한 어트리뷰션 컨텍스트를 단계적으로 구축하는 체계적인 다단계 플로우를 따릅니다. 웹 방문 자체를 캡처하는 것부터 리포팅을 위한 트래픽 분류에 이르기까지, 각 단계는 특정 정보 레이어를 제공합니다. 트래픽 소스 리졸루션 플로우에서 사용되는 데이터는 웹 SDK 또는 Web S2S에 의해 수집됩니다.

흐름은 다음 단계로 구성됩니다.

1. [방문 기록](#1단계-방문-기록): 트래픽 소스가 아직 파악되지 않은 경우에도 사용자의 웹사이트 도달을 캡처하고 방문 이벤트를 기록합니다. 이는 어트리뷰션 로직이 적용되기 전에 모든 대상 사용자 유입이 측정되도록 합니다.
2. [미디어 소스 리졸루션](#2단계-미디어-소스-리졸루션): URL 파라미터와 리퍼러 데이터를 분석하여 방문을 유발한 플랫폼이나 파트너를 식별하거나, 해당 방문이 오가닉인지 여부를 결정합니다.
3. [캠페인 리졸루션](#3단계-캠페인-리졸루션): 식별된 미디어 소스에 연결된 세부 캠페인 정보를 리졸루션하여 심도 있는 성과 분석을 가능하게 합니다.
4. [채널 분류](#4단계-채널-분류): 리졸루션된 미디어 소스를 기반으로 각 방문을 상위 수준의 트래픽 채널에 할당하여 리포팅 및 분석을 위한 표준화된 뷰를 제공합니다.

<div id="step-1-visit-recording" />

## 1단계: 방문 기록

방문 기록은 웹 성능 측정 흐름의 첫 번째 단계입니다. 이는 미디어 소스 리졸루션 및 어트리뷰션 이전에 수행되며, 정제되지 않은 사용자 활동을 캡처하는 전처리 레이어 역할을 합니다.

로직은 두 단계로 작동합니다. 첫째, **리퍼러**(사용자가 사이트에 도달하기 전에 거쳐 온 도메인)를 분류합니다. 그런 다음 리퍼러 유형에 따라 사용자의 세션 상태와 미디어 소스 정보의 존재 여부를 평가하여 방문을 기록할지 결정합니다.

<div id="stage-1-referrer-classification" />

#### 단계 1: 리퍼러 분류

앱스플라이어는 리퍼러를 세 가지 유형 중 하나로 분류합니다:

* **외부 제외 항목** (예: 결제 처리 업체 또는 제외 대상으로 지정한 도메인)
* **내부 제외** (예: 귀하의 하위 도메인 또는 로그인 흐름)
* **기타** (모든 다른 리퍼러)

<div id="stage-2-session-evaluation-and-visit-recording" />

#### 2 단계: 세션 평가 및 방문 기록

리퍼러 유형을 기반으로 앱스플라이어는 세션 상태를 평가하고 방문 기록 여부를 결정합니다.

* **외부 제외:** 방문은 절대 기록되지 않습니다.
* **내부 제외:** 리퍼러 기반 어트리뷰션은 차단됩니다. 해당 리퍼러가 실제 사용자 획득 소스가 아니기 때문입니다.
  * 활성 세션이 있는 경우(30분 동안 활동이 없으면 세션이 비활성으로 간주되며, 그렇지 않은 경우 활성 상태임), 방문은 기록되지 않습니다.
  * 활성 세션이 없는 경우 방문은 기록되지만, 리퍼러는 자체 참조(Self-referral)로 처리되어 무시됩니다. URL에 어트리뷰션 파라미터(UTM, PID, 클릭 ID 등)가 포함되어 있지 않은 한 해당 방문은 오가닉으로 기록됩니다.
* **기타:**
  * 활성 세션이 없는 경우, 방문을 기록할 수 있습니까? 다른 조건에 상관없이, 새로운 세션은 신규 방문으로 카운트됩니다.
  * 활성 세션이 존재하고 비직접 미디어 소스(UTM, PID, 클릭 ID 등)가 포함되어 있는 경우, 방문을 기록합니다. 이 재방문은 리타겟팅 전환(재참여)을 유발할 수 있으며, 이는 이후 이벤트의 어트리뷰션에 활용됩니다.
  * 활성 세션이 존재하고 미디어 소스 정보가 없는 경우, 해당 세션 내에서 새로운 방문을 기록하지 않습니다.

<Image alt="트래픽 흐름 해결" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

<div id="step-2-media-source-resolution" />

## 2단계: 미디어 소스 리졸루션

디어 소스 리졸루션 프로세스는 방문이 다음과 같은지를 결정합니다.

* **논오가닉:** 특정 어트리뷰션 소스가 확인되었습니다.
* **오가닉** 어트리뷰션 소스가 식별되지 않습니다 (예: 사용자가 URL을 직접 입력하거나 북마크를 사용한 경우).

미디어 소스 리졸루션 프로세스 동안 앱스플라이어는 랜딩 페이지 URL 경로 및 쿼리 문자열에서 추출한 파라미터를 평가하여 웹 방문의 출처를 결정합니다.

최상의 결과를 얻으려면 가장 높은 수준의 세밀도와 제어 기능을 제공하는 `pid` 및 `af_campaign`와 같은 앱스플라이어 전용 파라미터를 사용하세요. 앱스플라이어는 UTM 태그 및 클릭 ID와 같은 업계 표준 파라미터도 인식하므로 기존 광고 측정 설정을 변경하지 않고 즉시 시작할 수 있습니다.

앱스플라이어는 미디어 소스를 리졸루션하기 위해 우선순위에 따라 처리합니다. 소스가 성공적으로 식별되는 즉시 해당 프로세스가 중단됩니다. 미디어 소스 리졸루션 프로세스는 다음 단계로 구성됩니다:

<Accordion title="1. 제외 도메인">

첫째, 앱스플라이어는 방문이 **제외 목록**에 등록된 도메인에서 발생했는지 확인합니다. 도메인이 제외 대상인 경우(예: 내부 도메인 또는 페이팔과 같은 결제 대행사), 해당 방문은 자동으로 무시되거나 **오가닉**으로 분류됩니다.

웹 앱을 앱스플라이어에 추가할 때 제외 도메인을 지정하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#제외-도메인">제외된 도메인</Anchor> 문서를 참조하세요.

</Accordion>

<Accordion title="2. 앱스플라이어 PID(파트너 ID)">

도메인이 제외되지 않은 경우, 앱스플라이어는 URL에서 `pid=` 매개변수를 찾습니다.

* 발견되면, 미디어 소스는 이 값에서 직접 가져옵니다.
* <span id="social-media-partners"></span>다음 소셜 미디어 파트너는 원본 URL 파라미터 값 대신 특정 디스플레이 레이블을 사용합니다.

| URL 매개변수(PID) | 미디어 소스 표시 이름 |
| --- | --- |
| `pid=iossearchads_int` | Apple Search Ads |
| `pid=facebook_int` | Facebook Ads |
| `pid=metaweb_int` | Facebook Ads |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | snapchat\_int |

</Accordion>

<Accordion title="3. UTM 매개변수">

URL에서 PID가 확인되지 않은 경우, 앱스플라이어는 `utm_source` 및 `utm_medium` 파라미터를 평가하여 미디어 소스를 식별합니다. 이 두 필드의 조합에 의해 최종 리졸루션 결과가 결정됩니다.

<div id="how-utm-logic-works" />

#### **UTM 논리가 작동하는 방식**

* 대부분의 경우, 앱스플라이어는 `utm_source`의 원본 값을 추출하여 이를 미디어 소스로 지정함으로써 미디어 소스를 결정합니다.
* `utm_medium`이(가) `email`, `mail` 또는 `e-mail`인 경우, 미디어 소스는 자동으로 `e-mail`(으)로 리졸루션됩니다.
* `utm_medium`이(가) 존재하고 이메일 값이 아닌 경우, 앱스플라이어는 특정 커스텀 매핑 규칙에 따라 해당 값을 확인합니다(아래 매핑 표 참조).
* `utm_medium`이(가) 누락되었거나 커스텀 규칙과 일치하지 않는 경우, 앱스플라이어는 대체 수단으로 `utm_source`을(를) 미디어 소스로 사용합니다.

<div id="utm-mapping-rules" />

#### **UTM 매핑 규칙**

| utm\_source | utm\_medium | 미디어 소스 |
| --- | --- | --- |
| Google | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | CPM | dv360\_int |
| Facebook / FB / Meta | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Facebook Ads |
| Bing / microsoft / ms | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / gemini | cpm / display / listing | yahoogemini\_int |
| twitter | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | snapchat\_int |
| pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |

</Accordion>

<Accordion title="4. 클릭 ID">

URL에 PID와 UTM 파라미터가 모두 없는 경우, 앱스플라이어는 **Click ID**를 사용하여 미디어 소스 식별을 시도합니다. 이 값은 특정 광고 네트워크가 URL에 자동으로 추가하는 고유 식별자입니다.

앱스플라이어는 방문을 어트리뷰션하기 위해 다음과 같은 Click ID 매핑을 사용합니다:

| 클릭 ID 파라미터 | 리졸루션된 미디어 소스 |
| --- | --- |
| `gclid`, `wbraid` 혹은 `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | snapchat\_int |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * 앱스플라이어는 Meta가 유료 및 오가닉 Facebook 클릭 모두에 fbclid를 추가하기 때문에 트래픽 소스 판별에 fbclid를 사용하지 않습니다. Meta로 트래픽 기여를 집계하려면 pid=facebook\_int를 포함하거나 utm\_source를 관련 Meta 소스 값으로 설정하세요.
> * dclid 파라미터는 미디어 소스 판별에 사용되지 않습니다. dclid는 CM360을 사용할 때 fbclid(Facebook)나 ttclid(TikTok) 같은 다른 클릭 ID와 함께 표시될 수 있는 Campaign Manager 360(CM360) 식별자입니다. dclid만 단독으로 사용할 경우 잘못된 매칭이나 결과 판별로 이어질 수 있습니다.

</Accordion>

<Accordion title="5. HTTP 리퍼러">

URL에서 쿼리 파라미터(PID, UTM, 클릭 ID)가 발견되지 않으면 앱스플라이어는 `http_referrer`을(를) 사용하여 트래픽 소스를 식별합니다. 이는 도메인 호스트를 추출하여 미디어 소스 매핑을 수행하는 내부 파싱 메커니즘을 기반으로 합니다.

<div id="the-parsing-mechanism" />

#### **파싱 메커니즘**

유입 소스를 식별하기 위해 앱스플라이어는 다음과 같이 리퍼러 문자열을 정제합니다.

1. URL을 **호스트**로 단순화하는 작업
2. **도메인 접미사**(최상위 도메인인 `.com`, `.org` 또는 `.co.uk`와 같은 확장자) 제거
3. **도메인 접두사** (예: `www.`, `m.`, `l.` 또는 `lm.`) 제거

*예:* `www.mywebsite.com?param=example`*의 리퍼러는* `mywebsite`*의 미디어 소스로 리졸루션됩니다.*

<div id="referrer-mapping-rules" />

#### **리퍼러 매핑 규칙**

| 도메인 호스트에 다음이 포함되어 있는 경우 | 리졸루션된 미디어 소스 |
| --- | --- |
| `mail.` 혹은 `outlook.` | Email |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

<div id="search-engine-mapping" />

#### **검색 엔진 매핑**

| 도메인 호스트에 다음이 포함되어 있는 경우 | 리졸루션된 미디어 소스 |
| --- | --- |
| `google.` | Google Search |
| `search.yahoo` | Yahoo Search |
| `bing.com` | Bing Search |

<div id="android-app-referrers" />

#### **Android 앱 리퍼러**

방문이 Android 앱에서 발생한 경우, 리퍼러 호스트는 다음과 같이 매핑됩니다.

| 앱 리퍼러 문자열 | 리졸루션된 미디어 소스 |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google Search |
| `com.google.android.gm` | Email |
| `com.linkedin.android` | LinkedIn |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | Telegram |

</Accordion>

<div id="step-3-campaign-resolution" />

## 3단계: 캠페인 리졸루션

2단계에서 미디어 소스가 확인되면 앱스플라이어는 세부 캠페인 정보를 식별하기 위한 작업을 진행합니다.

앱스플라이어는 우선순위에 따라 다음 URL 파라미터에서 캠페인 정보를 수집합니다.

| URL 파라미터 | 매핑됨 | 우선 순위 |
| --- | --- | --- |
| `c`, `af_campaign`, `utm_campaign` | 캠페인 이름 | <ol><li>`c`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`, `af_campaign_id` | 캠페인 ID | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_adset` | 광고 세트 이름 | — |
| `af_adset_id` | 광고세트 ID | — |
| `af_ad` | 광고 이름 | — |
| `af_ad_id` | Ad ID | — |
| `af_keywords` | 키워드 | — |

<div id="step-4-channel-classification" />

## 4단계: 채널 분류

미디어 소스를 식별하는 것 외에도 앱스플라이어는 각 방문을 특정 채널로 분류합니다. 이러한 분류를 통해 로우 데이터 리포트 및 대시보드에서 트래픽 유형에 대한 고차원적인 인사이트를 확인할 수 있습니다.

<div id="overriding-the-channel-with-af_channel" />

### af\_channel을 사용한 채널 값 덮어쓰기

커스텀 채널 값을 할당하려면 랜딩 페이지 URL에 `af_channel` 파라미터를 추가하세요. 예를 들어 `af_channel=ig` 설정은 채널을 `ig`(으)로 지정하여 광고 지면 노출 위치처럼 표준 카테고리에서는 파악하기 어려운 수준까지 트래픽을 세분화하여 분석할 수 있게 해줍니다.

`af_channel` 방문에 대한 미디어 소스도 식별된 경우에만 리졸루션됩니다. 유입 방문이 오가닉(미디어 소스가 식별되지 않은 경우)인 경우, `af_channel` 여부와 관계없이 항상 `Direct`(으)로 리졸루션됩니다.

<div id="default-channel-classification" />

### 기본 채널 분류

`af_channel`(이)가 존재하지 않거나 방문이 위 조건에 부합하지 않는 경우, 앱스플라이어는 식별된 미디어 소스를 기반으로 자동 분류를 수행합니다.

* **Direct:** 사용자가 URL을 직접 입력했거나 북마크를 통해 방문했습니다. 어떠한 기여 소스도 식별되지 않은 상태입니다.
* **오가닉 검색:** Google, Yahoo, Bing과 같은 검색 엔진에서 유입된 무상 트래픽입니다.
* **소셜 미디어 :** 소셜 플랫폼에서 발생하는 트래픽입니다.
* **이메일 :** 이메일 캠페인 또는 이메일 서비스 제공업체를 통한 트래픽입니다.
* **Ad:** 유료 광고를 통해 발생한 트래픽입니다.
* **리퍼럴:** 리퍼러를 통해 식별된 다른 웹사이트로부터의 트래픽입니다.
* **기타:** 위의 어떤 카테고리에도 해당하지 않는 트래픽입니다.

**참고:** 모든 방문은 채널에 할당됩니다. 분류는 식별된 미디어 소스 와 출처 표기 방법을 기반으로 자동적이고 확정적으로 이루어지며, `af_channel`에 의해 재정의되지 않는 한 그대로 유지됩니다.

<div data-zendesk-anchors="what-is-traffic-source-resolution=%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01KGMEER6DX8W3ECBEBYP4DQV1=%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 the-traffic-source-resolution-flow=%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98-%ED%9D%90%EB%A6%84 h_01KGMEER6DA4HMSZ3TVEAG84WZ=%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98-%ED%9D%90%EB%A6%84 step-1-visit-recording=1%EB%8B%A8%EA%B3%84-%EB%B0%A9%EB%AC%B8-%EA%B8%B0%EB%A1%9D h_01KGMEER6DV02F44C5ZPSBEQEX=1%EB%8B%A8%EA%B3%84-%EB%B0%A9%EB%AC%B8-%EA%B8%B0%EB%A1%9D stage-1-referrer-classification=%EB%8B%A8%EA%B3%84-1-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EB%B6%84%EB%A5%98 h_01KSSEM5P8RX29CD6C6ZD2DVAT=%EB%8B%A8%EA%B3%84-1-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EB%B6%84%EB%A5%98 stage-2-session-evaluation-and-visit-recording=2-%EB%8B%A8%EA%B3%84-%EC%84%B8%EC%85%98-%ED%8F%89%EA%B0%80-%EB%B0%8F-%EB%B0%A9%EB%AC%B8-%EA%B8%B0%EB%A1%9D h_01KSSEM5P8KBYDBCB7PAPGPX5M=2-%EB%8B%A8%EA%B3%84-%EC%84%B8%EC%85%98-%ED%8F%89%EA%B0%80-%EB%B0%8F-%EB%B0%A9%EB%AC%B8-%EA%B8%B0%EB%A1%9D step-2-media-source-resolution=2%EB%8B%A8%EA%B3%84-%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98 h_01KGMEER6D082QTZGZYEXT6726=2%EB%8B%A8%EA%B3%84-%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98 how-utm-logic-works=utm-%EB%85%BC%EB%A6%AC%EA%B0%80-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94-%EB%B0%A9%EC%8B%9D h_01KGMF0E1XBSJCVDWGC4R8XMPX=utm-%EB%85%BC%EB%A6%AC%EA%B0%80-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94-%EB%B0%A9%EC%8B%9D utm-mapping-rules=utm-%EB%A7%A4%ED%95%91-%EA%B7%9C%EC%B9%99 h_01KGMF0JSBZ3WYM65R55BCDAMN=utm-%EB%A7%A4%ED%95%91-%EA%B7%9C%EC%B9%99 the-parsing-mechanism=%ED%8C%8C%EC%8B%B1-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98 h_01KGMEZA9ETGK6Z89GM111E64Z=%ED%8C%8C%EC%8B%B1-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98 referrer-mapping-rules=%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EB%A7%A4%ED%95%91-%EA%B7%9C%EC%B9%99 h_01KGMEZESC451HVJT139BSXEA5=%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EB%A7%A4%ED%95%91-%EA%B7%9C%EC%B9%99 search-engine-mapping=%EA%B2%80%EC%83%89-%EC%97%94%EC%A7%84-%EB%A7%A4%ED%95%91 h_01KGMEZKCTASMNXZG13VTVECVH=%EA%B2%80%EC%83%89-%EC%97%94%EC%A7%84-%EB%A7%A4%ED%95%91 android-app-referrers=android-%EC%95%B1-%EB%A6%AC%ED%8D%BC%EB%9F%AC h_01KGMEZQYCDS23MVW3MQH9Q5JQ=android-%EC%95%B1-%EB%A6%AC%ED%8D%BC%EB%9F%AC step-3-campaign-resolution=3%EB%8B%A8%EA%B3%84-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98 h_01KGMEER6ES1AYT24MC4HZCX9X=3%EB%8B%A8%EA%B3%84-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A6%AC%EC%A1%B8%EB%A3%A8%EC%85%98 step-4-channel-classification=4%EB%8B%A8%EA%B3%84-%EC%B1%84%EB%84%90-%EB%B6%84%EB%A5%98 h_01KGMEER6ETWGFFM3E17KHMDAF=4%EB%8B%A8%EA%B3%84-%EC%B1%84%EB%84%90-%EB%B6%84%EB%A5%98 h_01_overriding-the-channel-with-af-channel=af_channel%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EC%B1%84%EB%84%90-%EA%B0%92-%EB%8D%AE%EC%96%B4%EC%93%B0%EA%B8%B0 overriding-the-channel-with-af_channel=af_channel%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EC%B1%84%EB%84%90-%EA%B0%92-%EB%8D%AE%EC%96%B4%EC%93%B0%EA%B8%B0 h_01_default-channel-classification=%EA%B8%B0%EB%B3%B8-%EC%B1%84%EB%84%90-%EB%B6%84%EB%A5%98 default-channel-classification=%EA%B8%B0%EB%B3%B8-%EC%B1%84%EB%84%90-%EB%B6%84%EB%A5%98" />
