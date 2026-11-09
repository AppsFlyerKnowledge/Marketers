---
title: OpenDSR API
metadata:
  keywords:
    - Advertisers
    - GDPR
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2026-10-14T10:35:10Z'
  id: 11332840660625
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/11332840660625
---
> **한눈에 보기:** 이 기사는 플랫폼을 사용하여 앱 사용 및 귀속을 기록하는 AppsFlyer 클라이언트, 종종 광고주 또는 앱 소유자라고 불리는 사용자를 위한 것입니다. 앱 소유자는 GDPR(유럽), CCPA(캘리포니아), LGPD(브라질), PDPA(태국) 및 PIPA(한국)와 같은 적용 가능한 데이터 보호 법률을 준수하기 위해 OpenDSR(데이터 주체 요청) API를 구현합니다.

변호사로부터의 한마디: 여기에 명시된 내용은 법적 조언이 아닙니다. 정보와 편의를 위해 제공됩니다. 귀하는 GDPR, CCPA 또는 기타 법률이 귀하에게 어떻게 적용될 수 있는지 또는 적용되지 않을 수 있는지를 정확히 판단하기 위해 법률 및 기타 전문 자문가와 긴밀히 협력해야 합니다. 사용자와 앱스플라이어간의 프라이버시 관계는 <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">앱스플라이어 서비스 개인정보 보호 정책</Anchor>에 의해 관리됩니다. 본 서비스 개인 정보 보호 정책과 관련하여 질문이 있거나 데이터 보호 책임자에게 문의하려면 privacy@appsflyer.com. 일반 데이터 보호 규정(General Data Protection Regulation) 제27조에 의거하여, 앱스플라이어의 EU 내 대리인은 AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Germany (연락처 privacy@appsflyer.com; +49-30-166373500)입니다.

<div id="privacy-regulations" />

## 개인정보 보호 규정

본 기사에서 개인정보 보호정책에 대한 참조에는 다음 테이블에 기재한 규정이 포함됩니다.

| 규정 | 로고 | 설명 |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | 개인정보보호 규정(GDPR)은 유럽 연합(EU) 시민의 데이터 보호 및 개인정보보호에 관한 EU 규정입니다. |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | 캘리포니아 소비자 프라이버시 보호법 |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | 브라질 일반 개인정보 보호법 |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | 개인 데이터 보호법 |

용어 프라이버시 규정, GDPR, CCPA, LGPD 및 PDPA는 본 기술자료에서 상호 교환 가능하게 사용됩니다.

<div id="the-opendsr-initiative" />

### OpenDSR 이니셔티브

개인 정보 보호 규정에 따라 제출된 데이터 주체의 요청을 처리하고 관리하기 위해 앱스플라이어는 mParticle, Amplitude 및 Braze와 함께 OpenDSR 프로토콜(이전의 OpenGDPR)을 시작했습니다.

OpenDSR은 소비자 데이터의 공정하고 투명한 사용을 위해 기술 회사들 간의 협력을 지원하는 오픈 소스 프레임워크입니다. 이 프로토콜을 사용하면 공급업체가 고객 데이터를 처리하고 저장하는 여러 시스템에서 데이터 정보 보호 작업을 수행할 수 있습니다.

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">OpenDSR 이니셔티브에 대해 자세히 알아보세요</Anchor>.

<div id="definitions" />

### 정의

| DSR 용어 | 앱스플라이어 용어 | 설명 |
| --- | --- | --- |
| 데이터 주체 | 앱 사용자 또는 최종 사용자 | 데이터가 수집되는 앱 사용자 |
| 데이터 처리자 | 앱 소유자 또는 광고주 | 앱 소유자는 개인 데이터가 처리되는 목적 및 수단을 판별합니다. |
| 데이터 처리 수탁자 | 앱스플라이어 및 파트너 | AppsFlyer 및 관련 파트너가 데이터 처리자를 대신해 개인 데이터를 처리합니다. |

<div id="dsr-requirements" />

### DSR 요구 사항

DSR은 데이터 처리자가 준수해야 하는 데이터 주체의 필수 권리를 자세히 규정합니다. API 목적상 이러한 권리는 요청 유형으로 변환됩니다. 아래에서 앱스플라이어가 다른 요청 유형을 처리하는 방법을 자세히 설명합니다.

| **요청 유형**<br /><br />**(권리)** | **GDPR 정의** | 앱스플라이어에서 요청 처리 |
| --- | --- | --- |
| **액세스** | <ul><li>요청되면, 앱 사용자는 앱 소유자가 자신의 데이터를 처리하는 시간, 이유 및 시간을 알 권리가 있습니다.</li><li>앱스플라이어와 같은 제3자와 데이터를 공유하는 경우 앱 사용자는 이러한 제3자가 누구인지 알 권리가 있습니다.</li><li>처리되는 데이터의 범주를 데이터 주체가 알 권리를 포함합니다.</li><li>데이터 주체에게 유의미한 영향을 미치는 자동화 처리가 있는지 여부를 포함합니다.</li></ul> | 앱 소유자는 앱 사용자의 처리된 개인 데이터의 사본을 수신합니다. |
| **이동성** | 앱 사용자에게 제공되는 모든 개인 데이터는 CSV 파일처럼 흔히 사용되는, 기계로 판독 가능한 구조화된 형식이어야 합니다. | 앱 소유자는 앱 사용자의 처리된 개인 데이터의 사본을 수신합니다. |
| **정정** | 데이터가 정확하지 않거나 사실이 아닌 경우 앱 사용자에게 이를 정정할 수 있도록 허용합니다. 앱 소유자는 부정확하거나 불완전한 데이터를 지우거나 정정해야 합니다. | <ul><li>앱스플라이어는 정정 요청 이전에 기록된 앱 사용자의 데이터를 삭제합니다.</li><li>이후에 수신된 데이터는 앱스플라이어에서 기록합니다.</li></ul> |
| **삭제** | 삭제 권리에 따라 앱 소유자가 요청을 받은 날로부터 14일 이내에 개인 데이터를 제거해야 합니다. | 데이터를 삭제합니다. |

<div id="appsflyer-gdpr-requests-api" />

## AppsFlyer의 GDPR 요청 API

본 절에 설명된 대로 GDPR 요청 API를 사용하여 DSR 준수를 구현합니다.

* GDPR 요청 GDPR 요청: 열람, 이동, 삭제 또는 정정 중 하나의 요청을 수행합니다.
* 2. 상태 요청 GDPR 요청의 현재 상태를 조회하십시오.
* 4. 검색 요청 지원되는 API 버전 및 데이터 형식에 대해 문의하십시오.
* 취소 진행 중인 단계에서 GDPR 요청을 취소합니다.

앱 소유자는 앱에 UI 변경을 구현하여 앱 사용자가 요청을 제출할 수 있도록 해야 합니다. GDPR 요청은 한 번에 한 사용자만 제출할 수 있습니다.

<div id="1-gdpr-request" />

<Accordion title="1. GDPR 요청">

<div id="gdpr-request-flow" />

### GDPR 요청 과정

GDPR 요청 유형인 열람, 이동, 삭제 및 정정 과정은 모두 동일합니다.

1. **앱 사용자**는 요청을 제출합니다.
2. **앱 소유자**는 GDPR 요청을 구성하고 (아래 참조) 앱스플라이어로 전송합니다.
3. **앱스플라이어**는 요청을 수신하고 유효한 요청에 대해 "201 OK"로 응답합니다.
4. 접근성과 휴대성을 위해: 요청이 즉시 이행됩니다.  
   삭제 및 수정의 경우:
   * 다음 48시간 동안 요청이 큐에 대기되고 ***보류 중*** 상태가 됩니다. 앱 사용자는 요청을 취소할 수 있습니다.
   * 48시간 후 요청 상태가 ***in\_progress***로 변경됩니다. 앱스플라이어가 상태 변경 포스트백을 보냅니다. 이 시점에서는 요청을 취소할 수 없습니다.
   * 앱스플라이어는 14일 이내에(아래 참고 사항 참조) 요청을 이행하고 요청 상태가 ***완료됨***으로 업데이트됩니다. 앱스플라이어가 상태 변경 포스트백을 보냅니다.

     * *삭제* 또는 *정정*의 경우, 앱 사용자의 데이터가 삭제됩니다.
     * *이식성* 또는 *액세스*의 경우, 앱 사용자의 데이터는 **GDPR** 에 따라 앱스플라이어 대시보드 또는 요청 API(아래 참조)를 통해 액세스할 수 있습니다.

     **참고: 이 10일 기간은 앱 소유자가 요청을 제출할 때 시작됩니다. 48시간 후, 요청 상태가 진행 중으로 변경되며 추가 8일 이내에 완료되어 총 10일이 소요됩니다.**

<div id="gdpr-request-format" />

### GDPR 요청 형식

HTTP POST를 통해 GDPR 요청 API를 다음 엔드포인트로 제출할 수 있습니다.

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

API 권한 부여의 경우 Pull API와 동일한 V2 API 토큰을 사용합니다. 관리자는 대시보드의 API 토큰 페이지에서 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens#토큰-검색">토큰을 검색할</Anchor> 수 있습니다. 요청 헤더에 토큰을 다음과 같이 추가하세요:

<div id="parameters" />

#### 파라미터

<table><thead><tr><th><strong>속성 이름</strong></th><th><strong>필수</strong></th><th><strong>설명</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>예</td><td>UUID v4 문자열입니다. 데이터 처리 수탁자에게 요청을 제출할 때 데이터 처리자가 생성합니다. 요청의 상태를 체크하고 요청을 업데이트 또는 취소하기 위해 사용할 수 있습니다.</td></tr><tr><td><strong>subject_request_type</strong></td><td>예</td><td>GDPR 요청 유형을 나타내는 문자열 값입니다. 지원 값:<ul><li>erasure</li><li>portability</li><li>액세스</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>예</td><td><ul><li>요청자의 신원을 정의하는 ID 오브젝트의 배열(아래 참조).</li><li>각 요청은 하나의 주체만 포함할 수 있습니다.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>예</td><td><ul><li>데이터 주체가 최초로 요청한 시간에 대한 RFC 3339 날짜 문자열</li><li>UTC의 타임 스탬프</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>예</td><td><p>이 요청을 시도한 모바일 앱을 나타내는 문자열입니다.</p><p><strong>예</strong>:</p><ul><li> <strong>iOS</strong>: id123456789 </li><li> <strong>안드로이드</strong>: com.example, com.publishers.name  </li><li> <strong>스토어 외 안드로이드</strong>: com.publisher.name-channel<br/><strong>일러두기</strong> 일부 경우에는 앱 소유자가 Android Google Play 이름을 사용하여 스토어 외 어트리뷰션을 기록하는 경우도 있습니다. 이러한 경우 대시보드에 표시되는 대로 일반 앱 이름을 사용하십시오.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>아니요</td><td>GDPR 요청 API의 알맞은 버전을 나타내는 버전 문자열</td></tr><tr><td><strong>status_callback_urls</strong></td><td>아니요, 하지만 추천합니다</td><td><ul><li>다음 요청 상태 변경으로 보낼 상태 콜백에 대한 최대 3개의 엔드포인트 배열입니다.</li><li>HTTPS 엔드포인트만 지원됩니다.</li><li>잘못된 URL은 거부됩니다.</li></ul></td></tr><tr><td rowspan="2"> <strong>플랫폼</strong><br/><br/> </td><td>아니요</td><td>가치는 지원되는 DSR 플랫폼 중 하나입니다:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code> </td></tr><tr><td>예</td><td><p>CTV, PC 또는 콘솔 플랫폼 요청의 경우 다음 플랫폼 중 하나를 포함합니다.  </p><p> <code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Subject\_identities 오브젝트

| 오브젝트 유형 | **필수** | **설명** |
| --- | --- | --- |
| identity\_type | 예 | <ul><li>다음 플랫폼의 문자열 형식의 ID 유형은 다음 중 하나입니다:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>customer\_user\_id(CUID)</li></ul></li></ul><ul><li>다음과 같은 플랫폼에 대해서만:<ul><li>appsflyer\_id</li><li>customer\_user\_id(CUID)</li></ul></li></ul><ul><li>예: `android_advertising_id`</li></ul>**<span id="01JFVT3ATDGJXBX4VN7BHX6JB8"></span>중요!**<br />OpenDSR API를 통해 CUID를 사용하려면, 인앱 이벤트에서 CUID를 /와 함께 전송해야 합니다 : 또는 |
| identity\_value | 예 | <ul><li>형식: 문자열</li><li>예시: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | 예 | <ul><li>identity\_value를 인코딩하는 데 사용되는 방법: `raw`rawraw만 지원됩니다.</li><li>예시: "raw"</li></ul> |

<div id="zd-gdpr-erasure-request-code-example" />

<div id="example-gdpr-erasure-request" />

### 예시: GDPR 삭제 요청

다음은 , , , 플랫폼에 대한 삭제 요청의 예입니다:

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '{ 
 "subject_request_id":"f4e5a271-f25e-4107-b681-************",
 "subject_request_type":"erasure",
 "submitted_time":"2020-07-05T10:00:00Z",
 "platform": "android",
 "subject_identities":[ 
  { 
   "identity_type":"android_advertising_id",
   "identity_value":"55*****-****-****-************",
   "identity_format":"raw"
  }
 ],
 "api_version":"0.1",
 "property_id":"com.*********.*******.********",
 "status_callback_urls":[ 
  "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

플랫폼에 대한 삭제 요청의 예:

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
"subject_request_type":"erasure",
"submitted_time":"2020-07-05T10:00:00Z",
"subject_identities":[ 
 { 
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
"api_version":"0.1",
"property_id":"app-id",
"platform": "roku",
"status_callback_urls":[ 
 "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

<div id="gdpr-erasure-request-code-example" />

### GDPR 삭제 요청 코드 예시

<Tabs>
<Tab title="Java">

```java
/* 
using the okhttp package install from maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */

import okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null, "" +
  "{\r\n\"subject_request_id\": \"\"," +
  "\r\n\"subject_request_type\": \"erasure\"," +
  "\r\n\"platform\": \"android\"," +
  "\r\n\"submitted_time\": \"2018-11-02T15:00:00Z\"," +
  "\r\n\"subject_identities\": [\r\n" +
  "{\r\n\"identity_type\": \"android_advertising_id\"," +
  "\r\n\"identity_value\": \"\"," +
  "\r\n\"identity_format\": \"raw\"\r\n}" +
   "\r\n]," +
   "\r\n\"property_id\": \"com.example.application\"}");

  Request request = new Request.Builder()
  .url("https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/opendsr_requests")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Accept", "application/json")
  .addHeader("Authorization: Bearer", "")
  .build();

  try {
   Response response = client.newCall(request).execute();
   System.out.println(response.code());
   System.out.println(response.body().string());
   System.exit(0);
  } catch (IOException e) {
   e.printStackTrace();
   System.exit(1);
  }
 }
}
```

</Tab>

<Tab title="PythonNode.jsC#">

```python
""" using the requests python package, 
install using pip install requests """

import requests
import json
headers = {
 "Content-Type": "application/json",
 "Accept": "application/json",
 "Authorization: Bearer": ""
}

body = {
 "subject_request_id": "", 
 "subject_request_type": "erasure", 
 "submitted_time": "2018-10-02T15:00:00Z",
 "platform": "android", 
 "subject_identities": [
  { "identity_type": "android_advertising_id", 
   "identity_value": "", 
   "identity_format": "raw" }
  ], 
 "property_id": "com.example.application" 
} 
body = json.dumps(body) 
res = requests.request("POST", 
"https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests", 
headers=headers, data=body, params=params) 
print(res.text)
```

</Tab>
</Tabs>

</Accordion>

<div id="2-status-request" />

<Accordion title="2. 2. 상태 요청">

모든 제출된 GDPR 요청에 대해서 나중에 `subject_request_id`subject\_request\_idsubject\_request\_id를 지정하여 상태를 확인할 수 있습니다. 다음의 4가지 상태 유형이 있습니다.

1. ***pending*** - 요청이 올바르게 수신되었고 현재 대기열에 있습니다.
2. ***in\_progress*** - 요청이 현재 처리 중입니다.
3. ***completed*** - 요청이 처리되었습니다.
4. ***canceled*** - 요청이 취소되었습니다.

<div id="status-request-format" />

### 상태 요청 형식

HTTP GET을 통해 상태 요청을 다음 엔드포인트로 제출할 수 있습니다.

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

### 상태 응답 예시

```http
HTTP/1.1 200 OK
Content-Type: application/json
X-OpenGDPR-Processor Domain: example processor.com
X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

<div id="status-postbacks" />

### 상태 포스트백

위의 GDPR 요청 흐름에서 설명한 바와 같이, GDPR 요청의 상태가 ***pending***에서 ***in\_progress***로, 그리고 ***completed***로 변경되는 경우, 앱스플라이어는 **status\_callback\_urls** 속성으로 지정된 요청 엔드포인트로 GDPR 포스트백을 전송합니다.

상태 포스트백 예시:

```http
POST /opengdpr_callbacks HTTP/1.1
Host: examplecontroller.com
Content-Type: application/json
X-OpenGDPR-Processor Domain: gdpr.appsflyer.com
X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

<div id="validate-postback" />

### 포스트백 유효성 검사

**수신 포스트백의 유효성 검사 방법**:

1. 콜백을 수행할 수 있는 모든 프로세서 도메인의 허용 목록을 만듭니다.
2. 헤더 값이 허용 목록에 있으면 인증서를 가져옵니다.
   * 인증서 URL은 응답 본문의 값입니다.
   * 앱스플라이어 엔드포인트에서 V2 API 토큰을 권한 부여 헤더의 베어러 토큰으로 사용하여 인증서를 직접 가져올 수도 있습니다.
3. 라이브러리를 사용하여 인증서의 유효성을 검사하여 인증서가 다음과 같은지 확인합니다.
   1. 신뢰할 수 있는 기관에서 발급되었습니다.
   2. 헤더 값에 제공된 동일한 문자열에 발급됩니다.
   3. 만료되지 않았습니다.
4. 인증서가 유효하다고 확인되면, 이를 사용하여 원시 요청 본문에 대한 헤더를 검증하십시오. 앱스플라이어는 SHA256 RSA를 서명 알고리즘으로 사용합니다.
5. 상태 헤더에서 응답을 가져옵니다.
   1. 유효성이 성공하면.
   2. `401 Unauthorized`401 Unauthorized 서명의 유효성을 검사하지 못하거나 프로세서 도메인이 허용 목록에 없는 경우.

</Accordion>

<div id="3-report-request" />

<Accordion title="3. 3. 보고서 요청">

**열람 요청** 또는 **이동 요청**이 완료되고 나면 보고서를 다음 엔드포인트로 HTTP GET을 활용하여 다운로드할 수 있습니다.

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

생성된 보고서는 완료 시점부터 14일간 다운로드할 수 있습니다.

</Accordion>

<div id="4-discovery-requestin-process" />

<Accordion title="4. 4. 검색 요청 프로세스">

AppsFlyer가 지원하는 형식을 알아보기 위해 HTTP GET을 통한 검색 요청을 다음 엔드포인트로 제출할 수 있습니다.

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

### 검색 응답 예시

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
 "api_version": "0.1",
 "supported_identities": [
 {
  "identity_type": "android_advertising_id",
  "identity_format": "raw"
 },
 ],
 "supported_subject_request_types": [
 "erasure", "access", "portability", "rectification"
 ],
 "processor_certificate": "https://exampleprocessor.com/cert.pem"
}
```

</Accordion>

<div id="5-cancellation-request" />

<Accordion title="5. 5. 취소 요청">

GDPR 요청은 그에 따라 취소할 수 있지만, 대기 중인 단계에서만 가능합니다.

HTTP DELETE를 제출하려면 :

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

### 취소 응답

GDPR 취소 요청을 받으면 AppsFlyer는 상태 코드 202 및 기타 여러 파라미터와 함께 HTTP 응답을 반환합니다.

요청 취소가 이루어지면 AppsFlyer는 ***cancelled*** 상태의 포스트백을 전송합니다.

</Accordion>

<div id="6-gdpr-requests-test-api" />

<Accordion title="6. 6. GDPR 요청 테스트 API">

이 AppsFlyer API는 AppsFlyer의 GDPR 요청 API용 테스트 API입니다.

<div id="how-does-it-work" />

### 어떻게 작동하나요?

이 테스트 API가 동작하는 방식은 다음과 같습니다.

1. 1. GDPR 요청이 생성되고 나면 요청이 즉시 승인 대기 상태로 변경됩니다. 테스트 목적으로 30초마다 상태가 변경됩니다.

2. 2. 상태 포스트백의 엔드포인트가 GDPR 요청에 삽입된 경우 첫 번째 포스트백이 요청 직후에 전송되고 이후 상태 포스트백 두 개가 30초 간격으로 추가 전송됩니다.

**GDPR 요청 테스트 엔드포인트** POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**상태 요청 테스트 엔드포인트** GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**검색 요청 테스트 엔드포인트** GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**취소 요청 테스트 엔드포인트** DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**인증서 테스트 엔드포인트**: GET GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**열람/이식성 리포트 테스트 엔드포인트**: GET GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

<div id="note" />

> 📘 **참고**
>
> * 유효한 V2 API 토큰은 다음과 같이 요청 헤더에 삽입되어야 합니다:
> * 'property\_id' 속성에서 App ID는 계정 소유자(API 토큰에 따름)에 속해야 합니다.

</Accordion>

<div id="7-request-logs" />

<Accordion title="7. 요청 로그">

관리자는 로그 대시보드에 제출된 GDPR 요청에 액세스할 수 있습니다.

완료된 열람 및 이동 요청의 경우 이 대시보드에서 보고서를 다운로드할 수도 있습니다.

로그 대시보드 액세스 방법

1. 화면 상단 표시줄에서 계정(이메일 주소) 아래 드롭다운 메뉴를 펼치고 로그아웃을 클릭합니다.
2. 다음 창이 열립니다:

<Image align="center" alt="GDPR_Table.png" src="https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png" />

</Accordion>

<div id="8-gdpr-api-return-codes-and-error-messages" />

<Accordion title="8. 8. GDPR API 리턴 코드 및 오류 메시지">

이 절에서는 GDPR API HTTP 리턴 코드 및 오류 메시지를 자세히 설명합니다.

<div id="gdpr-api-return-codes" />

#### GDPR API 리턴 코드

| 리턴 코드 | 설명 |
| --- | --- |
| 201 | 생성됨 |
| 202 | 취소 요청 수신함 |
| 400 | 잘못된 요청. 본문에는 다음 표에 나열된 오류 코드 및 메시지가 포함되어 있습니다. |

<div id="http-return-code-400---bad-request" />

### HTTP 리턴 코드 400-잘못된 요청

리턴 코드 400을 가진 메시지에는 오류 코드 및 메시지와 함께 JSON이 포함되어 있습니다.

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

<div id="return-code-400-bad-request-messages" />

#### 리턴 코드 400 잘못된 요청 메시지

| 오류 코드 | 오류 설명(메시지) |
| --- | --- |
| e111 | 속도 제한 초과 |
| e211 | 잘못된 상태의 요청 취소 불가 |
| e212 | 요청이 허용되지 않음. 식별자에 대한 삭제가 진행 중입니다. |
| e213 | 요청이 이미 존재함 |
| e214 | 요청을 찾을 수 없음 |
| e311 | 잘못된 요청 콘텐츠-유형 |
| e312 | 잘못된 API 버전 |
| e313 | 잘못된 subject\_request\_id |
| e314 | 잘못된 submitted\_time 형식 |
| e315 | 잘못된 status\_callback\_url 길이 |
| e316 | 잘못된 status\_callback\_url 형식 |
| e317 | 잘못된 app\_id 형식 |
| e318 | 잘못된 identity\_type |
| e319 | 애플리케이션 플랫폼이 식별 유형과 일치하지 않음 |
| e320 | 잘못된 identity\_type |
| e321 | LAT 사용자가 API를 통해 지원되지 않음 |
| e322 | 잘못된 subject\_request\_type |
| e323 | 잘못된 subject\_identities 형식 |
| e324 | 잘못된 subject\_identities 길이 |
| e325 | 잘못된 subject\_identities 값 |
| e411 | AppID가 올바르지 않거나 사용자 계정에 속하지 않음 |
| e412 | 삭제 요청을 취소할 수 있는 권한이 없음 |
| e413 | 요청을 볼 수 있는 권한이 없음 |
| e511 | 내부 문제, 60분 기다렸다가 다시 시도하십시오. 문제가 지속되면 AppsFlyer 지원팀에 문의하십시오. support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

* OpenDSR API 속도 제한: 분당 350건의 요청 이 한도를 초과하면 오류가 발생하여 요청을 다시 보내야 합니다. 이 비율 제한 내에서 유지하면 하루에 최대 504,000개의 요청이 가능합니다.
* 60일 이상 전의 요청 상태를 확인하면 "요청을 찾을 수 없음"이 반환됩니다.

<div data-zendesk-anchors="privacy-regulations=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 h_01HB866TQ0AWHQ9659Q8Q4XMQM=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 the-opendsr-initiative=opendsr-%EC%9D%B4%EB%8B%88%EC%85%94%ED%8B%B0%EB%B8%8C h_01HB866TQ0R18S4GCH3KPGNJHD=opendsr-%EC%9D%B4%EB%8B%88%EC%85%94%ED%8B%B0%EB%B8%8C definitions=%EC%A0%95%EC%9D%98 h_01HB866TQ06XV2AJDMA3M5Q5KK=%EC%A0%95%EC%9D%98 dsr-requirements=dsr-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01HB866TQ0JNEZTHQ7BR1TMD5M=dsr-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD appsflyer-gdpr-requests-api=appsflyer%EC%9D%98-gdpr-%EC%9A%94%EC%B2%AD-api h_01HB866TQ0HNFGF9QTJNT792N7=appsflyer%EC%9D%98-gdpr-%EC%9A%94%EC%B2%AD-api h_01HB866TQ0ATDT8B000Z70MBTH=1-gdpr-request gdpr-request-flow=gdpr-%EC%9A%94%EC%B2%AD-%EA%B3%BC%EC%A0%95 h_01HB866TQ0FCZGQ1DWENVSWHSG=gdpr-%EC%9A%94%EC%B2%AD-%EA%B3%BC%EC%A0%95 gdpr-request-format=gdpr-%EC%9A%94%EC%B2%AD-%ED%98%95%EC%8B%9D h_01HB866TQ0GC7V1081GT53TWEZ=gdpr-%EC%9A%94%EC%B2%AD-%ED%98%95%EC%8B%9D parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HB866TQ0CFAC0X2Y98B4EE5Q=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 subject_identities-objects=subject_identities-%EC%98%A4%EB%B8%8C%EC%A0%9D%ED%8A%B8 h_01HB866TQ02HMKJMKKPHHR4CMN=subject_identities-%EC%98%A4%EB%B8%8C%EC%A0%9D%ED%8A%B8 example-gdpr-erasure-request=%EC%98%88%EC%8B%9C-gdpr-%EC%82%AD%EC%A0%9C-%EC%9A%94%EC%B2%AD h_01HB866TQ1CT316PTFBJC59C79=%EC%98%88%EC%8B%9C-gdpr-%EC%82%AD%EC%A0%9C-%EC%9A%94%EC%B2%AD gdpr-erasure-request-code-example=%EC%98%88%EC%8B%9C-gdpr-%EC%82%AD%EC%A0%9C-%EC%9A%94%EC%B2%AD h_01HB866TQ1D7290A6G29Q4HDE7=gdpr-%EC%82%AD%EC%A0%9C-%EC%9A%94%EC%B2%AD-%EC%BD%94%EB%93%9C-%EC%98%88%EC%8B%9C h_01HB866TQ15M1897AV5W099SFV=2-status-request status-request-format=%EC%83%81%ED%83%9C-%EC%9A%94%EC%B2%AD-%ED%98%95%EC%8B%9D h_01HB866TQ1YEZZ4M6QMHTKCEGX=%EC%83%81%ED%83%9C-%EC%9A%94%EC%B2%AD-%ED%98%95%EC%8B%9D status-response-example=%EC%83%81%ED%83%9C-%EC%9D%91%EB%8B%B5-%EC%98%88%EC%8B%9C h_01HB866TQ1M7G7JNH0V7TEVFYY=%EC%83%81%ED%83%9C-%EC%9D%91%EB%8B%B5-%EC%98%88%EC%8B%9C status-postbacks=%EC%83%81%ED%83%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HB866TQ1109WJ2J13D8FM8KX=%EC%83%81%ED%83%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 validate-postback=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%82%AC h_01HB866TQ1YG0B6JDEQ2KMFEN0=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%9C%A0%ED%9A%A8%EC%84%B1-%EA%B2%80%EC%82%AC h_01HB866TQ1TYQWZ7492H0DKWB7=3-report-request h_01HB866TQ1CH06PRJ78MHE7ZG0=4-discovery-requestin-process discovery-response-example=%EA%B2%80%EC%83%89-%EC%9D%91%EB%8B%B5-%EC%98%88%EC%8B%9C h_01HB866TQ1AJCSS2442EEWA19X=%EA%B2%80%EC%83%89-%EC%9D%91%EB%8B%B5-%EC%98%88%EC%8B%9C h_01HB866TQ1R8C9G4VH085897ZQ=5-cancellation-request cancellation-response=%EC%B7%A8%EC%86%8C-%EC%9D%91%EB%8B%B5 h_01HB866TQ1F72KP3S55ZJYC8Y7=%EC%B7%A8%EC%86%8C-%EC%9D%91%EB%8B%B5 h_01HB866TQ1Y35SZVFSTPG3ZJDH=6-gdpr-requests-test-api how-does-it-work=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01HB866TQ1KFRGX7NZCSJWVW0T=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01HB866TQ1W6X6NSEA6ZXAE6AG=%EC%B0%B8%EA%B3%A0 h_01HB866TQ1H8BKVGP5PFQYVBAA=7-request-logs h_01HB866TQ139BREE45W1FGTT3K=8-gdpr-api-return-codes-and-error-messages gdpr-api-return-codes=gdpr-api-%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C h_01HB866TQ128R2TSHS4JTCQK70=gdpr-api-%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C http-return-code-400-bad-request=http-%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C-400-%EC%9E%98%EB%AA%BB%EB%90%9C-%EC%9A%94%EC%B2%AD h_01HB866TQ1A51STZQCJC5TV65X=http-%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C-400-%EC%9E%98%EB%AA%BB%EB%90%9C-%EC%9A%94%EC%B2%AD return-code-400-bad-request-messages=%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C-400-%EC%9E%98%EB%AA%BB%EB%90%9C-%EC%9A%94%EC%B2%AD-%EB%A9%94%EC%8B%9C%EC%A7%80 h_01HB866TQ10MAMTS9WB0CKN55V=%EB%A6%AC%ED%84%B4-%EC%BD%94%EB%93%9C-400-%EC%9E%98%EB%AA%BB%EB%90%9C-%EC%9A%94%EC%B2%AD-%EB%A9%94%EC%8B%9C%EC%A7%80 limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HB866TQ1PXGRX5JRHRSCT0EN=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
