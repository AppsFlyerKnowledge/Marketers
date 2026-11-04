---
title: Отправка запросов API OpenDSR
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
  edited_at: '2026-10-03T00:16:53Z'
  id: 11332840660625
  locale: ru
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ru/articles/11332840660625
---
> **At a glance:** **Краткий обзор:** Эта статья предназначена для клиентов AppsFlyer (рекламодателей или владельцев приложений), которые используют платформу AppsFlyer для регистрации данных об использовании приложения и атрибуции. Владельцы приложений реализуют API OpenDSR (Запрос субъектов данных), чтобы соответствовать соответствующим правовым нормам о защите данных, таким как GDPR (Европа), CCPA (Калифорния), LGPD (Бразилия), PDPA (Таиланд) и PIPA (Корея).

**Важное юридическое примечание:** *информация в данной статье не может считаться рекомендациями юриста. Информация предоставляется только для ознакомления. Чтобы точно определить, необходимо ли вам соблюдать требования GDPR, CCPA или иных правовых норм, вам необходимо проконсультироваться с юристом или иным специалистом. Уровень конфиденциальности ваших данных в AppsFlyer определяется <Anchor target="_blank" href="https://www.appsflyer.com/ru/services-privacy-policy">Политикой конфиденциальности AppsFlyer</Anchor>. По любым вопросам, касающимся данной Политики конфиденциальности, или для связи с нашим специалистом по защите данных отправьте нам письмо по адресу [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Представителем AppsFlyer в ЕС по вопросам соблюдения статьи 27 Общего регламента по защите данных является AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Germany (контактные данные [privacy@appsflyer.com](mailto:privacy@appsflyer.com); +49-30-166373500).*

<div id="privacy-regulations" />

## Правила конфиденциальности

В данной статье под законами о защите данных понимаются законы, перечисленные в таблице ниже.

| Закон | Логотип | Описание |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | General Data Protection Regulation (GDPR) – общий регламент ЕС по защите данных; это регламент Европейского союза по правилам обработки персональных данных граждан ЕС. |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | California Consumer Privacy Act – закон о защите персональных данных граждан штата Калифорния. |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados – закон о конфиденциальности в Бразилии. |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Personal Data Protection Act – закон о защите персональных данных в Таиланде. |

Термины «законы о защите данных», «GDPR», «CCPA», «LGPD» и «PDPA» в данной статье употребляются как взаимозаменяемые.

<div id="the-opendsr-initiative" />

### Инициатива OpenDSR

Для рассмотрения и обработки запросов субъектов персональных данных, поданных в соответствии с правилами конфиденциальности, компания AppsFlyer, совместно с mParticle, Amplitude и Braze, инициировала протокол OpenDSR (ранее известный как OpenGDPR).

OpenDSR – это платформа с открытым исходным кодом, обеспечивающая сотрудничество между компаниями-разработчиками для обеспечения справедливого и прозрачного использования данных клиентов. Эта инициатива позволяет разработчикам без труда реализовывать меры по защите данных клиентов в разных системах при их обработке и хранении.

<Anchor target="_blank" href="https://www.appsflyer.com/ru/company/newsroom/pr/opengdpr-initiative/">Подробнее об инициативе OpenDSR</Anchor>.

<div id="definitions" />

### Определения

| Термин DSR | Термин AppsFlyer | Описание |
| --- | --- | --- |
| Субъект данных | Пользователь приложения или конечный пользователь | Пользователь приложения, о ком собираются данные |
| Контролёр данных | Владелец приложения или рекламодатель | Владелец приложения определяет цели и способы обработки персональных данных. |
| Обработчик данных | Компания AppsFlyer и её партнёры | Компания AppsFlyer и её партнёры, которые обрабатывают персональные данные по поручению контролёра данных. |

<div id="dsr-requirements" />

### Требования DSR

В DSR изложены обязательные права субъекта данных, которые должен соблюдать контролёр данных. В целях использования АPI эти права превращаются в запросы различных типов. Ниже показано, как AppsFlyer обрабатывает различные типы запросов.

| **Тип запроса**<br /><br />**(право)** | **Определение в GDPR** | Обработка запроса в AppsFlyer |
| --- | --- | --- |
| **Доступ к данным** | <ul><li>Пользователи приложения имеют право знать, будет ли владелец приложения обрабатывать их данные, с какой целью и в течение какого срока.</li><li>Если данные предоставляются третьим лицам, например, AppsFlyer, пользователи приложения имеют право знать, кто эти третьи лица.</li><li>Право на получение сведений об обрабатываемых категориях данных.</li><li>Сведения об использовании автоматических средств обработки, которые могут оказать существенное воздействие на данные.</li></ul> | Владельцы приложения получают копию обработанных персональных данных пользователя приложения. |
| **Переносимость данных** | Все персональные данные должны предоставляться пользователю приложения в структурированном, общепринятом и машиночитаемом формате, например в виде СSV-файла. | Владельцы приложения получают копию обработанных персональных данных пользователя приложения. |
| **Исправление данных** | Позволяет пользователям приложения вносить исправления в свои данные в случае их неточности или недостоверности. Владельцы приложения обязаны удалить или исправить неточные или неполные данные. | <ul><li>AppsFlyer удаляет данные пользователя приложения, записанные до даты запроса на *исправление*.</li><li>Данные, полученные после запроса, регистрируются.</li></ul> |
| **Удаление данных** | Право на удаление данных обязывает владельцев приложения удалить персональные данные пользователя в течение 10 дней с момента получения запроса. | Данные удалены. |

<div id="appsflyer-gdpr-requests-api" />

## API AppsFlyer для запросов GDPR

Используйте API для запросов GDPR, как описано в этом разделе, чтобы соблюдать DSR.

* **Запрос GDPR** выполнение запроса одного из вышеперечисленных типов: «доступ к данным», «переносимость данных», «удаление данных» или «исправление данных».
* **Запрос о статусе**: запрос текущего статуса запроса по GDPR.
* **Запрос на обнаружение**: запрос о поддерживаемой версии API и формате данных.
* **Отмена**: отмена запроса GDPR на этапе ***ожидания***.

Владельцы приложений обязаны внести изменения в пользовательский интерфейс приложения, чтобы пользователи приложения имели возможность отправлять такие запросы. Обратите внимание, что запросы GDPR рассматриваются по отдельным пользователям.

<Accordion title="1. Запрос GDPR">

<div id="gdpr-request-flow" />

#### Процедура выполнения запросов GDPR

Процедура выполнения запросов GDPR всех типов (доступ к данным, переносимость данных, удаление или исправление данных) одинакова:

1. **Пользователь приложения** отправляет запрос.
2. **Владелец приложения** создаёт запрос GDPR (см. ниже) и отправляет его в AppsFlyer.
3. **AppsFlyer** получает запрос и, если запрос правильный, отправляет ответ «201 OK».
4. **По вопросам, связанным с доступом к данным и переносимостью данных:** Запросы выполняются в течение 8 дней.  
   **Примечание:** Этот 8-дневный период начинается, когда Владелец приложения подаёт свой запрос. Статус запроса изменяется с «Ожидание» на «В процессе» и будет выполнен в течение дополнительных 6 дней, всего 8 дней.  
   **По удалению и исправлению:**
   * Запрос помещается в очередь и в течение следующих 48 часов имеет статус ***«Ожидание»***. На этом этапе пользователь приложения может отменить запрос.
   * Через 48 часов статус запроса меняется на ***«В процессе» (in\_progress).*** AppsFlyer отправляет постбэк ***изменения статуса***. На этом этапе запрос уже нельзя отменить.
   * В течение 10 дней (см. примечание ниже) AppsFlyer выполняет запрос, и статус запроса меняется на ***«Выполнен»*** . AppsFlyer отправляет постбэк status change (изменение статуса).

     * Если пользователь приложения запросил *удаление* или *исправление* данных, его данные удаляются.
     * Если поступил запрос на *переносимость данных* или *доступ к данным*, данные пользователя доступны на дэшборде AppsFlyer в разделе **GDPR** или через API запросов (см. ниже).

     **Примечание.** Этот 10-дневный период начинается с момента, когда владелец приложения подаёт свой запрос. Через 48 часов статус запроса изменится на **«В процессе»**, и он будет выполнен в течение дополнительных 8 дней, в общей сложности 10 дней.

<div id="gdpr-request-format" />

#### Формат запроса GDPR

В API GDPR для отправки запросов используется HTTP-команда POST в следующую конечную точку:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Для авторизации API используйте тот же токен API V2, что и для Pull API. Пользователь-администратор может <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#получение-токенов">получить токен</Anchor> со страницы токена API на дэшборде Добавьте токен в заголовок запроса следующим образом: `'Authorization': 'Bearer %AuthTokenV2%'` Добавьте токен в заголовок запроса следующим образом: `'Authorization': 'Bearer %AuthTokenV2%'` Добавьте токен в заголовок запроса следующим образом: `'Authorization': 'Bearer %AuthTokenV2%'`

<div id="parameters" />

#### Параметры

<table><thead><tr><th><strong>Свойство</strong></th><th><strong>Обязательно</strong></th><th><strong>Описание</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Да</td><td>Строка UUID v4. Создаётся контролёром при отправке запроса обработчику. Затем её можно использовать для проверки состояния, обновления или отмены запроса.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Да</td><td><p>Строковое значение, определяющее тип запроса GDPR. Допустимые значения:</p><ul><li>удаление данных;</li><li>Переносимость данных</li><li>доступ к данным;</li><li>Исправление данных</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Да</td><td><ul><li>Массив объектов-идентификаторов, определяющих идентификатор инициатора запроса (см. ниже).</li><li>Каждый запрос может содержать только один идентификатор инициатора запроса.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Да</td><td><ul><li>Строка даты в формате RFC 3339, определяющая время создания исходного запроса субъектом данных</li><li>Метки времени по UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Да</td><td><p>Строка, определяющая мобильное приложение, к которому относится этот запрос</p><p><strong>Примеры</strong>:</p><ul><li> <strong>iOS</strong>: id123456789</li><li> <strong>Android</strong>: com.пример, com.название.издателя</li><li> <strong>Внемагазинные приложения на Android</strong>: com.название.издателя-канал<br/><strong>Примечание</strong> В некоторых случаях владельцы приложений регистрируют атрибуцию внемагазинных приложений, используя название Google Play для Android. В таких случаях используйте обычное название приложения, как оно указано на дэшборде.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>Ни один</td><td>Строка версии, определяющая нужную версию API запросов GDPR</td></tr><tr><td><strong>status_callback_urls</strong></td><td>Нет, но рекомендуется</td><td><ul><li>Массив конечных точек до 3 шт. для обратных вызовов со статусами, которые передаются для изменения статуса запроса.</li><li>Поддерживаются только конечные точки HTTPS.</li><li>Недействительные URL-адреса отклоняются.</li></ul></td></tr><tr><td rowspan="2"> <strong>платформа</strong><br/><br/> </td><td>Ни один</td><td>Значение является одной из поддерживаемых платформ DSR:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code> </td></tr><tr><td>Да</td><td><p>Для запроса платформы CTV, ПК или консоли включите любую из приведённых ниже платформ:</p><p><code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Объекты Subject\_identities

| Тип объекта | **Обязательно** | **Описание** |
| --- | --- | --- |
| identity\_type | Да | <ul><li>Тип идентификатора в строковом формате для платформ `android`, `ios`, `web`, `windowsphone`: любой из приведённых ниже.<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Для платформ `CTV`, `PC`, и `Console` только следующее:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Пример: `android_advertising_id`</li></ul>**Important**<br />**Двоеточие (:)**<br /><br />Чтобы использовать CUID через OpenDSR API, вы должны отправить CUID с `idfa` / `appsflyer_id` внутри событий приложения, используя `event_name`: `Login - Complete` или `Registration - Account created` |
| identity\_value | Да | <ul><li>форматирования ячеек с затратами;</li><li>Пример: «a7551968-d5d6-44b2-9831-815ac9017798»</li></ul> |
| identity\_format | Да | <ul><li>Метод кодирования identity\_value: допустим только `raw`:</li><li>Пример: «raw»</li></ul> |

<div id="example-gdpr-erasure-request" />

#### Пример: запрос GDPR типа «удаление»

**Пример запроса на удаление для платформ:** `android`, `ios`, `web`, `windowsphone`

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

**Пример запроса на удаление для платформ:** `CTV`, `PC`**, и** `Console`

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

<div id="zd-gdpr-erasure-request-code-example" />

<div id="gdpr-erasure-request-code-example" />

#### Пример кода запроса GDPR типа «удаление»

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

```javascript
/* using the request npm package, 
install using npm install request */

var request = require("request");
var options = { method: 'POST',
 url: 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests',
 headers: 
 { Accept: 'application/json',
  'Content-Type': 'application/json',
  'Authorization: Bearer': '' },
 body:
 { subject_request_id: '',
  subject_request_type: 'erasure',
  submitted_time: '2018-10-02T15:00:00Z',
  platform: 'android',
  subject_identities: 
  [ { identity_type: 'android_advertising_id',
   identity_value: '',
   identity_format: 'raw' } ],
 property_id: 'com.example.application'
 },
 json: true };
request(options, function (error, response, body) {
 if (error) throw new Error(error);

 console.log(body);
});
```

```csharp
using System;
 using RestSharp;
 namespace CS
 {
  class Gdpr
  {
   static void Main(string[] args)
   {
 		var url = "https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests";
   var client = new RestClient(url);
   var request = new RestRequest(Method.POST);
   request.AddHeader("Content-Type", "application/json");
   request.AddHeader("Accept", "application/json");
   request.AddHeader("Authorization: Bearer", "")
   var body = "{\r\n\"subject_request_id\": \"\"," + 
    "\r\n \"subject_request_type\": \"erasure\"," + 
    "\r\n \"submitted_time\": \"2018-11-02T15:00:00Z\"," +
    "\r\n \"platform\": \"android\"," +
    "\r\n \"subject_identities\": [\r\n" +
    "{ \r\n \"identity_type\": \"android_advertising_id\"," +
    "\r\n \"identity_value\": \"\"," + 
    "\r\n \"identity_format\": \"raw\"\r\n }" + 
    "\r\n ]," + 
    "\r\n \"property_id\": \"com.example.application\"}";

    request.AddParameter("undefined", body,ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
    // handle response by reading response.StatusCode
    Console.WriteLine(response.Content);
   }
  }
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Запрос статуса">

Для каждого отправленного запроса GDPR можно впоследствии отправить запрос о его статусе, указав параметр `subject_request_id`. Возможны четыре возможных статуса:

1. ***pending*** (Ожидание) – получен правильный запрос, который в данное время находится в очереди.
2. ***in\_progress*** (Выполняется) – запрос в данное время находится в обработке.
3. ***completed*** (Выполнен) – запрос выполнен.
4. ***cancelled*** (Отменен) – запрос отменен.

<div id="status-request-format" />

#### Формат запроса статуса

Для отправки запросов статуса используется HTTP-команда GET в следующую конечную точку:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

#### Пример ответа на запрос статуса

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

#### Постбэки статуса

Как описано выше в разделе Процедура выполнения запросов GDPR, при изменении состояния запроса GDPR с ***pending*** на ***in\_progress*** и ***completed*** AppsFlyer отправляет постбэк GDPR в запрашивающие конечные точки, которые указаны в свойстве **status\_callback\_urls**.

Пример постбэка о статусе:

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

#### Проверка постбэка

**Для валидации входящих постбэков**:

1. Создайте список всех доменов процессора, которым вы разрешаете выполнять обратные вызовы.
2. Если значение заголовка `X-OpenGDPR-Processor-Domain` находится в вашем разрешённом списке, получите сертификат.
   * URL сертификата – это значение `processor_certificate` в теле ответа `/discovery`.
   * Вы также можете получить сертификат непосредственно от конечной точки AppsFlyer, используя токен API V2 в качестве токена предъявителя в заголовке авторизации: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`.
3. Проверьте сертификат с помощью библиотеки, чтобы убедиться, что сертификат:
   1. Выдан уполномоченным органом.
   2. выдан той же строке, что и в значении заголовка `X-OpenGDPR-Processor-Domain`;
   3. срок сертификата не истёк.
4. Как только вы убедитесь, что сертификат действителен, используйте его для проверки заголовка `X-OpenGDPR-Signature` в необработанном теле запроса. AppsFlyer использует SHA256 RSA в качестве алгоритма подписания.
5. Получите ответ в заголовке статуса:
   1. `202 Accepted` при успешной валидации;
   2. `401 Unauthorized`, если подпись не прошла проверку или домен процессора отсутствует в вашем разрешённом списке.

</Accordion>

<Accordion title="3. Отчёт по запросу">

После выполнения запроса типа **доступ** или **переносимость** можно с помощью HTTP-команды GET загрузить отчёт в следующую конечную точку:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

Сформированный отчёт доступен в течение 14 дней .

</Accordion>

<Accordion title="4. Процесс подачи запроса на обнаружение">

Для получения сведений о форматах, которые поддерживает AppsFlyer, можно отправить запрос на обнаружение с помощью HTTP-команды GET в следующую конечную точку:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

#### Пример ответа на запрос на обнаружение

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

<Accordion title="5. Запрос на отмену">

Запрос GDPR можно отменить, указав его параметр `subject_request_id`, однако это возможно только на этапе ***pending*** (ожидание).

Чтобы отправить HTTP-команду DELETE с параметром `subject_request_id`:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

#### Ответ на запрос об отмене

При получении запроса на отмену AppsFlyer возвращает HTTP-ответ с кодом состояния 202 и ряд других параметров.

После отмены запроса AppsFlyer отправляет постбэк со статусом ***cancelled*** (отменен).

</Accordion>

<Accordion title="6. Тестовый API запросов GDPR">

Этот API AppsFlyer представляет собой тестовый API запросов GDPR.

<div id="how-does-it-work" />

#### Как это работает?

Тестовый API работает следующим образом:

1. Сразу после получения запроса GDPR он переводится в состояние «Pending» (ожидание). Для целей тестирования состояние меняется каждые 30 секунд.

2. Если запрос GDPR содержит конечную точку для постбэка состояния, первый постбэк отправляется сразу же после получения запроса, а затем отправляются ещё два постбэка состояния с интервалом 30 секунд.

**Конечная точка тестирования запросов GDPR**: POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Конечная точка тестирования запросов статуса**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Конечная точка тестирования запросов на обнаружение**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Конечная точка тестирования запроса на отмену**: DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Конечная точка тестирования сертификатов**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Конечная точка тестирования отчётов о доступе/переносимости данных**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **Note**
>
> **Примечание**
>
> * Действительный токен API V2 необходимо вставить в заголовок запроса следующим образом: `'Authorization': 'Bearer %AuthTokenV2%'`
> * Идентификатор приложения, указанный в свойстве «property\_id», должен принадлежать владельцу аккаунта (в соответствии с токеном API).

</Accordion>

<Accordion title="7. Журналы запросов">

Пользователь с правами администратора может получить доступ к запросам GDPR, отправленным из раздела журналов дэшборда.

На этой панели управления можно также загрузить отчет о выполненных запросах типа "доступ" и "перенос".

Доступ к разделу журналов на дэшборде:

1. На верхней панели откройте меню учётной записи (выпадающий список адресов электронной почты) > **журнал E-GDPR**.
2. Откроется следующее окно:

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<Accordion title="8. Коды возврата для API GDPR и сообщения об ошибках">

В этом разделе приведены HTTP-коды возврата для API GDPR и сообщения об ошибках.

<div id="gdpr-api-return-codes" />

#### Коды возврата для API GDPR

| Код возврата | Обзор |
| --- | --- |
| 201 | Создано |
| 202 | Получен запрос на отмену |
| 400 | Неверный запрос. В сообщении содержится код ошибки и текст сообщения, как указано в таблице ниже. |

<div id="http-return-code-400---bad-request" />

#### HTTP-код возврата 400 – неверный запрос

В сообщениях с кодом 400 содержится JSON с кодом ошибки и текстом сообщения об ошибке.

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

<div id="return-code-400-bad-request-messages" />

#### Возможные сообщения с кодом 400 – неверный запрос

| Код ошибки | Описание ошибки (текст сообщения) |
| --- | --- |
| e211 | Unable to cancel request with invalid status (Невозможно отменить запрос с недействительным статусом) |
| e212 | Request not permitted. (Запрос не разрешён.) (Запрос не разрешён.) (Запрос не разрешён.) Erasure is in progress for the identifier. |
| e213 | Request already exists (Запрос уже существует) |
| e214 | Request not found (Запрос не найден) |
| e215 | Одна или несколько идентичностей субъекта уже существуют в открытом запросе. если другой запрос для того же identity\_value уже находится в статусе «pending» или «in\_progress». |
| e311 | Invalid request content-type (Неверный тип контента запроса) |
| e312 | Неверная версия API |
| e313 | Invalid subject\_request\_id (Неверный параметр subject\_request\_id) |
| e314 | Invalid submitted\_time format (Неверный формат параметра submitted\_time) |
| e315 | Invalid status\_callback\_url length (Неверная длина параметра status\_callback\_url) |
| e316 | Invalid status\_callback\_url format (Неверный формат параметра status\_callback\_url) |
| e317 | Invalid app\_id format (Неверный формат параметра app\_id) |
| e318 | Invalid identity\_type (Неверный параметр identity\_type) |
| e319 | Application platform does not match identity types (Платформа приложения не соответствует типам идентификации) |
| e321 | LAT users are not supported via api (Пользователи LAT не поддерживаются по АPI) |
| e322 | Invalid subject\_request\_type (Неверный параметр subject\_request\_type) |
| e323 | Invalid subject\_identities format (Неверный формат параметра subject\_identities) |
| e324 | Invalid subject\_identities length (Неверная длина параметра subject\_identities) |
| e325 | Invalid subject\_identities value (Неверное значение параметра subject\_identities) |
| e326 | Неверный формат JSON в теле запроса |
| e411 | AppID is incorrect or does not belong to your account (AppID неверен или не принадлежит вашему аккаунту) |
| e412 | No permissions to cancel erasure request (Нет прав для отмены запроса на удаление данных) |
| e413 | No permissions to view request (Нет прав для просмотра запроса) |
| e511 | Internal problem, wait 60 minutes and try again. (Внутренняя проблема, подождите 60 минут и повторите попытку.) (Внутренняя проблема, подождите 60 минут и повторите попытку.) (Внутренняя проблема, подождите 60 минут и повторите попытку.) If the problem persists contact AppsFlyer support. support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## Характеристики и ограничения

* **Ограничение скорости API OpenDSR: 350 запросов в минуту**. Превышение этого лимита приведёт к ошибке, требующей повторной отправки запроса. При соблюдении этого лимита, можно отправлять до 504 000 запросов в день.
* Проверка статуса запроса, сделанного более 60 дней назад, возвращает «request not found» (запрос не найден).

<div data-zendesk-anchors="privacy-regulations=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HB866TQ0AWHQ9659Q8Q4XMQM=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 the-opendsr-initiative=%D0%B8%D0%BD%D0%B8%D1%86%D0%B8%D0%B0%D1%82%D0%B8%D0%B2%D0%B0-opendsr h_01HB866TQ0R18S4GCH3KPGNJHD=%D0%B8%D0%BD%D0%B8%D1%86%D0%B8%D0%B0%D1%82%D0%B8%D0%B2%D0%B0-opendsr definitions=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01HB866TQ06XV2AJDMA3M5Q5KK=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F dsr-requirements=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-dsr h_01HB866TQ0JNEZTHQ7BR1TMD5M=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-dsr appsflyer-gdpr-requests-api=api-appsflyer-%D0%B4%D0%BB%D1%8F-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2-gdpr h_01HB866TQ0HNFGF9QTJNT792N7=api-appsflyer-%D0%B4%D0%BB%D1%8F-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2-gdpr gdpr-request-flow=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2-gdpr h_01HB866TQ0FCZGQ1DWENVSWHSG=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2-gdpr gdpr-request-format=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-gdpr h_01HB866TQ0GC7V1081GT53TWEZ=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-gdpr parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01HB866TQ0CFAC0X2Y98B4EE5Q=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B subject_identities-objects=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D1%8B-subject_identities h_01HB866TQ02HMKJMKKPHHR4CMN=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D1%8B-subject_identities example-gdpr-erasure-request=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-gdpr-%D1%82%D0%B8%D0%BF%D0%B0-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5 h_01HB866TQ1CT316PTFBJC59C79=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-gdpr-%D1%82%D0%B8%D0%BF%D0%B0-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5 h_01HB866TQ1D7290A6G29Q4HDE7=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-gdpr-%D1%82%D0%B8%D0%BF%D0%B0-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5 status-request-format=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 h_01HB866TQ1YEZZ4M6QMHTKCEGX=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 status-response-example=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%B0-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 h_01HB866TQ1M7G7JNH0V7TEVFYY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%B0-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 status-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 h_01HB866TQ1109WJ2J13D8FM8KX=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81%D0%B0 validate-postback=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0 h_01HB866TQ1YG0B6JDEQ2KMFEN0=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0 discovery-response-example=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%B0-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%BD%D0%B0-%D0%BE%D0%B1%D0%BD%D0%B0%D1%80%D1%83%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01HB866TQ1AJCSS2442EEWA19X=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%B0-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%BD%D0%B0-%D0%BE%D0%B1%D0%BD%D0%B0%D1%80%D1%83%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 cancellation-response=%D0%BE%D1%82%D0%B2%D0%B5%D1%82-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%BE%D0%B1-%D0%BE%D1%82%D0%BC%D0%B5%D0%BD%D0%B5 h_01HB866TQ1F72KP3S55ZJYC8Y7=%D0%BE%D1%82%D0%B2%D0%B5%D1%82-%D0%BD%D0%B0-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%BE%D0%B1-%D0%BE%D1%82%D0%BC%D0%B5%D0%BD%D0%B5 how-does-it-work=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01HB866TQ1KFRGX7NZCSJWVW0T=%D0%BA%D0%B0%D0%BA-%D1%8D%D1%82%D0%BE-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 gdpr-api-return-codes=%D0%BA%D0%BE%D0%B4%D1%8B-%D0%B2%D0%BE%D0%B7%D0%B2%D1%80%D0%B0%D1%82%D0%B0-%D0%B4%D0%BB%D1%8F-api-gdpr h_01HB866TQ128R2TSHS4JTCQK70=%D0%BA%D0%BE%D0%B4%D1%8B-%D0%B2%D0%BE%D0%B7%D0%B2%D1%80%D0%B0%D1%82%D0%B0-%D0%B4%D0%BB%D1%8F-api-gdpr http-return-code-400-bad-request=http-%D0%BA%D0%BE%D0%B4-%D0%B2%D0%BE%D0%B7%D0%B2%D1%80%D0%B0%D1%82%D0%B0-400--%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 h_01HB866TQ1A51STZQCJC5TV65X=http-%D0%BA%D0%BE%D0%B4-%D0%B2%D0%BE%D0%B7%D0%B2%D1%80%D0%B0%D1%82%D0%B0-400--%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 return-code-400-bad-request-messages=%D0%B2%D0%BE%D0%B7%D0%BC%D0%BE%D0%B6%D0%BD%D1%8B%D0%B5-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-%D0%BA%D0%BE%D0%B4%D0%BE%D0%BC-400--%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 h_01HB866TQ10MAMTS9WB0CKN55V=%D0%B2%D0%BE%D0%B7%D0%BC%D0%BE%D0%B6%D0%BD%D1%8B%D0%B5-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-%D0%BA%D0%BE%D0%B4%D0%BE%D0%BC-400--%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D0%B9-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HB866TQ1PXGRX5JRHRSCT0EN=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />
