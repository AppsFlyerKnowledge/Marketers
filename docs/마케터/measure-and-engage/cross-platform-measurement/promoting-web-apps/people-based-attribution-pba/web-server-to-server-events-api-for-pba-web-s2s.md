---
title: PBA를 위한 웹 서버 대 서버 이벤트 API(Web-S2S)
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2026-10-14T10:34:08Z'
  id: 360006997298
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360006997298
---
> **한눈에 보기:** 웹 서버 대 서버(Web-S2S) 이벤트 API를 이용하여 웹 SDK로 리포트되지 않는 이벤트와 전환을 PBA에 리포트하세요.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

<div id="web-server-to-server-events-api-for-pba" />

## PBA용 웹 서버 대 서버 이벤트 API

웹-S2S API는 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide">웹 SDK</Anchor>를 보완하여 마케터가 웹사이트에서 발생하지만 웹 SDK 범위 바깥에서 일어나는 이벤트를 리포트할 수 있게 해줍니다. 예를 들어 웹사이트 방문자(웹 유저)가 온라인 결제 이벤트를 유발하고 이벤트는 백엔드 시스템에 의해 처리됩니다. 처리를 마친 후 백엔드는 S2S API를 활용해 앱스플라이어에 이벤트를 리포트합니다.

S2S API를 통해 전송된 이벤트는:

* 웹 SDK로 리포트된 이벤트와 마찬가지로 기록됩니다.
* 전환 이벤트로 설정될 경우 PBA 대시보드에 포함됩니다.
* *event\_source 필드*를 *웹 S2S*로 설정하여 PBA 로데이터를 채웁니다.

<div id="api-use-instructions" />

## API 사용법

다음 섹션을 활용해 API 호출을 만드십시오.

| 아니오. | 아이템 | 설명 |
| --- | --- | --- |
| 1 | 고유 사용자 ID | <ul><li>가능한 최고의 고유 사용자 ID를 제공하려고 노력해 주세요. 이것은 데이터 분석에 큰 영향을 미칩니다.</li><li>최상의 방법론은 customerUserId 전송입니다. 가능하지 않다면, 웹 SDK에 의해 설정된 웹사이트 쿠키 ID인 afUserId를 전송하세요.</li><li>고객의 고유 사용자 ID(<Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">CUID</Anchor>)와 [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)를 연결할 때는 두 ID 모두를 포함하는 setCuID() 메시지를 전송하세요.</li></ul> |
| 2 | Timestamp | <ul><li>AppsFlyer는 유입되는 이벤트 타임스탬프에 엄격한 유효성 검증을 적용합니다.</li></ul><ul><li>**늦은 도착 이벤트:** 이벤트는 그들이 속한 날짜로부터 24시간 이내에 도착하면 원래의 타임스탬프와 함께 받아들입니다. **예를 들어, 월요일 타임스탬프(2025-08-18 23:59 UTC)가** 있는 이벤트는 **화요일** 23:59:59 UTC까지 전송될 때까지 해당 타임스탬프를 유지합니다. 동일한 이벤트가 화요일 23:59:59 UTC 이후에 전송되면 타임스탬프는 서버의 수신 시간으로 덮어씁니다.</li><li>**향후 타임스탬프: 실제 도착 시간보다 나중에 타임스탬프가 있는** 이벤트는 허용되지 않습니다. 이러한 타임스탬프는 서버의 수신 시간으로 덮어씁니다.</li></ul><ul><li>타임스탬프는 UTC 기준입니다. 필요한 경우 파라미터를 완성하기 전에 현지 시간을 UTC 시간으로 변환하세요</li></ul> |
| 3 | 수익 및 화폐 단위 | 이벤트 값에 포함될지라도 반드시 *eventRevenueCurrency*와 *eventRevenue*를 기입해야 합니다. 대시보드에서 이 정보들을 활용하기 때문에 필수적입니다. |

<div id="api-basics" />

<Accordion title="API 기초">

API 구현 시 대시보드에서 제공되는 다음 인증 정보들이 필요합니다:

* 번들 ID(브랜드 번들 ID로도 알려져 있음)
* 웹 개발자 키

**인증 정보를 얻으려면:**

1. 앱스플라이어의 상단 메뉴에서 <strong>내 앱</strong> > 브랜드 번들 보기를 선택하세요.  
   번들 목록이 나타납니다.
2. 다음 항목들을 복사해서 기록하세요:
   * ***브랜드 번들 ID***
   * ***웹 개발자 키***

<div id="web-s2s-api-basics" />

#### 웹 S2S API의 기본 사항

| 경로 | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`: 대시보드에서 앱 번들 ID가 제공됩니다.</li><li>다음 중 하나가 될 수 있습니다:<ul><li>[이벤트](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): 보고할 백엔드 이벤트 전송 시</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) afUserId를 귀사 CUID와 연결할 때</li></ul></li></ul> |
| --- | --- |
| HTTP 메서드 | `POST` |
| 허용된 콘텐츠 타입 | `application/json` |
| JSON 페이로드 제한 | JSON 페이로드 크기: 최대 1KB |
| 콜 수 제한 | POST 제한: 분당 60,000건의 POST. 한도 증가를 원하면 CSM에 연락하세요. |
| TLS | <ul><li>TLS 1.2 버전 또는 그 이상</li><li><Anchor target="_blank" href="/marketers/ko/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">암호(cipher)가 지원됩니다.</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="setCuId 메소드">

| 메소드 명 | setCuId |
| --- | --- |
| 적용 케이스 | 방문자의 CUID와 연결할 때. 예를 들어, 언제든지 귀사의 고객 사용자 ID와 웹 `afUserId`을 매칭시킬 때. 이를 통해 PBA가 다양한 소스로부터의 데이터와 매칭할 수 있게 합니다. 이는 웹사이트에서 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> 설정과 유사합니다. |
| 메소드 경로 | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| 페이로드 | JSON 페이로드는 여기에 나열된 파라미터들로 구성됩니다. 모든 파라미터는 필수항목입니다.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

<div id="curl-example-setcuid" />

#### Curl 예제 setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="이벤트 메서드">

| 메소드 명 | 이벤트 |
| --- | --- |
| 적용 케이스 | 보내기 |
| 메소드 경로 | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| 상세한 정보 | 이 문서의 [이벤트 메소드 세부 정보](/docs/web-server-to-server-events-api-for-pba-web-s2s#이벤트-메소드-상세-정보) 섹션에는 페이로드 상세 정보, Curl 예제, Python 예제 및 테스팅 제안이 포함되어 있습니다. |

</Accordion>

<div id="event-method-details" />

## 이벤트 메소드 상세 정보

<div id="payload-parameters" />

<Accordion title="페이로드(payload) 파라미터">

페이로드 파라미터는 사용자 식별자 및 이벤트 파라미터로 구분됩니다.

* 유저 ID: <mark>최소한 하나 이상의 사용자 ID 파라미터를 전송해야 합니다.</mark>
* 이벤트: 필수 파라미터와 필요에 따라 선택적 파라미터를 전송하세요.

<div id="user-identifier-parameters-send-at-least-one-parameter" />

#### 사용자 식별자 파라미터(최소 한 개 이상 전송해야 함)

| 사용자 ID 파라미터 | 설명 |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 사용자 ID(CUID)</Anchor>는 귀하가 지정한 고유 식별자입니다.<ul><li>앱스플라이어에 보고된 모든 방법의 이벤트에 같은 식별자를 사용하세요. 즉, 웹 SDK, 모바일 SDK, S2S API에서 모두 동일한 식별자를 사용합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">웹 SDK용 고객 사용자 ID</Anchor></li><li>형식: 문자열</li><li>예: `"customerUserId" : "663274"`</li><li>로 데이터 필드 채우기: `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | 웹 SDK를 통해 방문하는 모든 사용자에게 할당된 고유 사용자 ID입니다. 쿠키 값을 귀사의 백엔드 서버로 전달해야 합니다.<ul><li>쿠키 세부 정보:<ul><li>이름: afUserId</li><li>값: *afUserId*를 이 값으로 설정하세요</li><li>도메인: 웹사이트 도메인</li></ul></li><li>예: `"afUserId" : "unique_cookie_uuid"`</li><li>로 데이터 필드 채우기: `af_web_id`</li></ul> |

<div id="event-parameters" />

#### 이벤트 파라미터

| 파라미터 이름 | 필수적 | 설명 |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | 예 | 대시보드에서 제공되는 [웹 개발자 키](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key)를 사용하여 채웁니다.<ul><li>예:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>이벤트 유형 | 예 | 앱스플라이어 내부용 이벤트 속성 식별자. 항상 *EVENT.*로 설정해야 합니다.<ul><li>예: `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | 예 | <ul><li>마케터가 PBA 설정에서 저정한 <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings#web-event-settings">이벤트 전환 목록</Anchor>을 통해 전환 이벤트와 비전환 이벤트를 구분하기 위해 이 파라미터를 사용합니다.</li><li>마케터의 전환 논리와 일치하는 값을 채워 넣어야 합니다.</li><li>형식: 문자열</li><li>예: `"eventName" : "web_purchase"`</li><li>로 데이터 필드 채우기: `event_name`</li></ul> |
| <span id="timestamp"></span>타임 스탬프 | 아니오 | 이벤트 발생 시간(밀리초 단위). 13자리 <Anchor target="_blank" href="https://www.unixtimestamp.com/">Unix 타임스탬프</Anchor> 형식으로 보내세요.<ul><li>타임스탬프를 보내지 않을 경우 서버의 시간을 이용해 시간이 설정됩니다.</li><li>**지연 도착 이벤트는 현재 서버 시간으로 타임스탬프가 설정됩니다.** 지연된 도착이란 이벤트 발생 다음 날 UTC 자정 이후에 도착한 경우를 의미합니다. 예를 들어, 월요일에 발생한 이벤트는 화요일 UTC 자정 전에 처리되어야 **합니다**.</li><li>현재 서버 시간에 비해 미래의 타임스탬프가 있는 이벤트는 서버 시간으로 타임스탬프가 설정됩니다.</li><li>형식: Int</li><li>예: `"timestamp" : 1584835200123`</li><li>로 데이터 필드 채우기: `event_time`</li></ul> |
| <span id="eventvalue"></span>eventValue | 아니오 | 이벤트를 설명하는 이벤트 파라미터의 집합입니다. 제품 SKU, 개별 항목 가격과 같은 리치 인앱 이벤트 전송에 이 파라미터를 사용하세요.<ul><li>**수익 관련 중요 안내!** 이 파라미터를 수익 정보로 채우세요. 그리고 *eventRevenue*와 *eventRevenueCurrency*도 함께 입력해야 합니다.</li></ul><ul><li>형식: JSON</li><li>예시: 예: 블루 색상의 SKU ABC123, 단위 가격 $3.99일 때, eventValue를 다음과 같이 설정하세요:<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>제한사항: 1000자입니다. 이 값을 초과하지 마세요. 초과하는 경우 내용이 잘릴 수 있습니다.</li><li>로데이터 필드에 적용됩니다: `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | 아니오 | 수익 이벤트의 통화 코드는 3자리 <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> 통화 코드를 사용합니다.<ul><li>기본 설정: USD</li><li>형식: 문자열</li><li>예:  `"eventRevenueCurrency" : "EUR"`</li><li>로 데이터 필드 채우기: `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>이벤트 수익 | 아니오 | 이벤트에 할당된 수익(금액).<br /><br />일러두기! 수익을 *eventValue*에 보고할 때는 *eventRevenue*에도 보고하고, eventRevenueCurrency도 함께 기입해야 합니다.<ul><li>음수 값도 입력 가능합니다. 예를 들어 환불 시와 같은 경우를 의미합니다.</li><li>형식: Float</li><li>예시 값들: `1` `1.2` `1234.20` `-1234.20`</li><li>로 데이터 필드 채우기: `event_revenue`</li></ul> |
| <span id="eventcategory"></span>eventCategory | 아니오 | 이 파라미터는 더 이상 사용되지 않으며, 앞으로 시스템에서 제거될 예정입니다. 대신에 eventValue를 사용해주세요. |
| <span id="eventlabel"></span>eventLabel | 아니오 | 이 파라미터는 더 이상 사용되지 않으며, 앞으로 시스템에서 제거될 예정입니다. 대신에 eventValue를 사용해주세요. |
| <span id="referrer"></span>리퍼러 | 아니오 | HTTP 리퍼러<ul><li>형식: 문자열</li><li>예시: `"referrer" : "https://www.google.com/"`</li><li>로데이터 필드에 적용됩니다: `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | 아니오 | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">유저 에이전트 요청은 브라우저가 서버로 보낸 요청입니다.</Anchor><ul><li>가능하다면 이 값을 전송하세요. 디바이스 유형을 판별하는 데 도움이 됩니다.</li><li>형식: 문자열</li><li>예시: `"userAgent" : "Chrome/80.0.3987"`</li><li>로데이터 필드에 적용됩니다: `user_agent`</li></ul> |
| <span id="ip"></span>ip | 아니오 | 사용자 IP 주소<ul><li>가능한 경우 해당 필드의 값을 전송하는 것이 좋습니다. 이는 유저의 <Anchor target="_blank" href="/marketers/ko/docs/determine-user-location">지리적 위치</Anchor>를 파악하는 데 유용합니다.</li></ul><ul><li>형식: 문자열</li><li>예시: `"ip": "192.0.2.1"`</li><li>로데이터 필드에 적용됩니다: `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="curl 예시">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,

		"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}

}'
```

</Accordion>

<div id="python-example" />

<Accordion title="Python 예제">

```python
''' using the requests python package, install using pip install requests  '''
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Accordion>

<div id="testing" />

<Accordion title="테스트">

테스트를 위해 다음과 같이 여러 이벤트를 전송하세요:

1. 이벤트를 전송합니다.
2. 200 OK 응답 코드를 받았는지 확인하세요. 만약 그렇지 않다면, 복구 조치를 위해 반환 코드와 오류 메시지를 사용하세요.
3. UTC 자정이 지난 후 몇 시간을 기다렸다가 PBA 로데이터에서 보고된 이벤트를 확인하시기 바랍니다. PBA 데이터는 일일 기준으로 처리되므로, 기다려야 합니다.

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="getting-the-web-dev-key" />

<Accordion title="웹 개발 키를 가져오는 방법">

**웹 개발 키를 가져오는 방법:**

1. AppsFlyer에서***내 앱***탭으로 이동하세요.
2. '브랜드 번들 보기'를 클릭하세요.

   [![GetWebDevKeyPba_us-en.pn](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)
3. 필요한 **웹 개발 키를 복사하세요.**

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="웹 SDK에서 afUserID 추출">

* afUserID는 귀하의 웹사이트를 사용자가 첫 방문했을 때 웹 SDK에 의해 부여되는 고유 식별자입니다.
* 필요한 경우 아래 방법 중 하나를 사용하세요.

<div id="get-afuserid-from-the-http-cookie-header" />

#### **HTTP 쿠키 헤더에서 afUserId 획득**

* 방문자의 브라우저가 귀하의 사이트로 요청을 보낼 때 `afUserId`이(가) 전송됩니다.
* 필요하다면 HTTP 쿠키 헤더에서 추출하십시오.

<div id="viewing-afuserid-in-the-visitors-browser" />

#### **방문자 브라우저에서 afUserId 확인**

* 방문자의 브라우저에서 afUserID를 확인하여 문제를 해결하거나 디버깅할 수 있습니다.
* 이를 확인하기 위해 방문자는 최소 한 번 웹 SDK가 있는 페이지를 방문해야 합니다.
* `afUserId`을(를) 포함하는 쿠키는 귀사의 도메인과 관련된 자사 쿠키입니다.
* 이 절차는 크롬 버전 81을 기반으로 준비되었습니다. 브라우저 및 운영 체제에 따라 차이가 있을 수 있습니다.

**방문자 브라우저에서 afUserId 가져오는 방법:**

1. 브라우저에서 귀하의 웹사이트로 이동하십시오.
2. '검사'를 선택하기 위해 마우스 오른쪽 버튼을 클릭하세요  
   브라우저의 요소 검사 창이 나타납니다.

   [![S2S_inspect.jpg](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)
3. '애플리케이션(Application)' 탭으로 이동하세요.
4. 측면 메뉴에서 '쿠키(Cookies)'를 확장하세요.
5. 귀하의 웹사이트를 선택하세요. 보이지 않는다면 브라우저를 새로고침하세요.
6. (C) ***필터*** 필드에 `afUserId`을(를)}입력하세요.  
   afUserID의 값이 나타납니다.

</Accordion>

<div id="response-codes" />

<Accordion title="응답 코드">

| 응답 코드 | 메시지 | 처리 방법 |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Not found | <ul><li>엔드포인트를 확인하세요</li><li>번들 ID가 정확한지 확인하시기 바랍니다.</li></ul> |
| 400 | Bad request | <ul><li>JSON에 오류가 존재합니다. 자세한 사항은 오류 메시지를 참고하세요.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="문제 해결">

* 증상: HTTP 반환 코드가 반환되지 않습니다.  
  해결 방안: 앱스플라이어 서버를 허용 목록에 추가하십시오.

</Accordion>

<div id="release-notes" />

<Accordion title="릴리즈 노트">

<table><caption>웹 SDK 릴리스 노트</caption><thead><tr><th>Date (날짜) </th><th>엔드포인트 버전</th><th>참고</th></tr></thead><tbody><tr><td>2020-05-12</td><td>1</td><td> 초판</td></tr><tr><td>2020-05-24</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* 버전 번호는 엔드포인트의 버전 번호를 나타냅니다. </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=pba%EC%9A%A9-%EC%9B%B9-%EC%84%9C%EB%B2%84-%EB%8C%80-%EC%84%9C%EB%B2%84-%EC%9D%B4%EB%B2%A4%ED%8A%B8-api h_01HKW2YAW4HHYK27F41HC3B24Y=pba%EC%9A%A9-%EC%9B%B9-%EC%84%9C%EB%B2%84-%EB%8C%80-%EC%84%9C%EB%B2%84-%EC%9D%B4%EB%B2%A4%ED%8A%B8-api api-use-instructions=api-%EC%82%AC%EC%9A%A9%EB%B2%95 h_01HKW2YAW4DCESP3MNY9D4GTFK=api-%EC%82%AC%EC%9A%A9%EB%B2%95 h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=%EC%9B%B9-s2s-api%EC%9D%98-%EA%B8%B0%EB%B3%B8-%EC%82%AC%ED%95%AD h_01HKW2YAW4XDKZ3YGAHAP3AG2T=%EC%9B%B9-s2s-api%EC%9D%98-%EA%B8%B0%EB%B3%B8-%EC%82%AC%ED%95%AD h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=curl-%EC%98%88%EC%A0%9C-setcuid h_01HKW2YAW5SJFKGTNRGRKN6NCJ=curl-%EC%98%88%EC%A0%9C-setcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A9%94%EC%86%8C%EB%93%9C-%EC%83%81%EC%84%B8-%EC%A0%95%EB%B3%B4 h_01HKW2YAW53H43SCYTDXAYBDHX=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A9%94%EC%86%8C%EB%93%9C-%EC%83%81%EC%84%B8-%EC%A0%95%EB%B3%B4 h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EC%B5%9C%EC%86%8C-%ED%95%9C-%EA%B0%9C-%EC%9D%B4%EC%83%81-%EC%A0%84%EC%86%A1%ED%95%B4%EC%95%BC-%ED%95%A8 h_01HKW2YAW5RR4Q2PCWC9717ACG=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EC%B5%9C%EC%86%8C-%ED%95%9C-%EA%B0%9C-%EC%9D%B4%EC%83%81-%EC%A0%84%EC%86%A1%ED%95%B4%EC%95%BC-%ED%95%A8 event-parameters=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKW2YAW5G46ZV4Z0CYEWB011=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HKW2YAW5D4N3SYA625F10YFW=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=http-%EC%BF%A0%ED%82%A4-%ED%97%A4%EB%8D%94%EC%97%90%EC%84%9C-afuserid-%ED%9A%8D%EB%93%9D h_01HKW2YAW5FK04C3AWCXGP1XAW=http-%EC%BF%A0%ED%82%A4-%ED%97%A4%EB%8D%94%EC%97%90%EC%84%9C-afuserid-%ED%9A%8D%EB%93%9D viewing-afuserid-in-the-visitors-browser=%EB%B0%A9%EB%AC%B8%EC%9E%90-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%97%90%EC%84%9C-afuserid-%ED%99%95%EC%9D%B8 h_01HKW2YAW5CT2WZ229KJD2FWYK=%EB%B0%A9%EB%AC%B8%EC%9E%90-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%97%90%EC%84%9C-afuserid-%ED%99%95%EC%9D%B8 h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
