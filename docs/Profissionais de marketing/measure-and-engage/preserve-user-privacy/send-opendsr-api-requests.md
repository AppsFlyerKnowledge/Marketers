---
title: Enviar solicitações da OpenDSR API
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
  edited_at: '2026-10-02T12:16:45Z'
  id: 11332840660625
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/11332840660625
---
> **At a glance:** **Resumo**: esse artigo foi feito para os clientes da AppsFlyer, muitas vezes referidos como anunciantes ou proprietários de aplicativos, que usam nossa plataforma para registrar o uso e a atribuição de aplicativos. Os proprietários de aplicativos implementam a OpenDSR API (solicitação do titular de dados) para cumprir as leis de proteção de dados aplicáveis, como o GDPR (Europa), CCPA (Califórnia), LGPD (Brasil), PDPA (Tailândia) e PIPA (Coreia).

**Aviso legal:** *Nada declarado aqui é aconselhamento jurídico. Os dados são fornecidos para sua informação e conveniência. Você deve trabalhar em estreita colaboração com consultores jurídicos e outros profissionais para determinar exatamente como o GDPR, LGPD, CCPA ou quaisquer outras leis podem ou não se aplicar a você. A relação de privacidade entre você e a AppsFlyer é definida pela <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">Política de Privacidade dos Serviços da AppsFlyer</Anchor>. Para perguntas relacionadas a essa política ou para entrar em contato com nosso responsável pela proteção de dados, envie um e-mail para: [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Para fins do Artigo 27 do Regulamento Geral de Proteção de Dados, o representante da AppsFlyer na UE é a AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlim, Alemanha (envie uma mensagem para [privacy@appsflyer.com/strong>](mailto:privacy@appsflyer.com); +49-30-166373500).*

<div id="privacy-regulations" />

## Regulamentos de privacidade

Neste artigo, as referências aos regulamentos de privacidade incluem os regulamentos mencionados na tabela a seguir.

| Regulamento | Logo | Descrição |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | O Regulamento Geral de Proteção de Dados é o regulamento da UE com relação à proteção e privacidade de dados para os cidadãos da União Europeia. |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | Lei de Privacidade do Consumidor da Califórnia |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados Pessoais |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Lei de Proteção de Dados Pessoais |

Os termos de regulamentos de privacidade, GDPR, CCPA e LGPD são usados de forma intercambiável neste artigo.

<div id="the-opendsr-initiative" />

### A iniciativa do OpenDSR

Para atender e gerenciar solicitações de titulares de dados enviadas de acordo com os regulamentos de privacidade, a AppsFlyer, junto com mParticle, Amplitude e Braze, iniciou o protocolo OpenDSR (anteriormente conhecido como OpenGDPR).

O OpenDSR é uma estrutura de código aberto que facilita a cooperação entre empresas de tecnologia para o uso justo e transparente dos dados do consumidor. Ela permite que os fornecedores tomem medidas de privacidade de dados em vários sistemas que processam e armazenam dados de clientes.

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">Saiba mais sobre a iniciativa OpenDSR</Anchor>.

<div id="definitions" />

### Definições

| Termo do DSR | Termo AppsFlyer | Descrição |
| --- | --- | --- |
| Titular dos dados | Usuário do aplicativo ou usuário final | O usuário do aplicativo sobre quem os dados são coletados |
| Controlador de dados | Proprietário do aplicativo ou anunciante | O proprietário do aplicativo determina o propósito e os meios pelos quais os dados pessoais são processados. |
| Processador de dados | AppsFlyer e seus parceiros | A AppsFlyer e seus parceiros processam dados pessoais em nome do controlador de dados |

<div id="dsr-requirements" />

### Requisitos do DSR

O DSR detalha os direitos obrigatórios do Titular dos Dados, com os quais o Controlador de Dados deve cumprir. Para fins de API, esses direitos são traduzidos em tipos de solicitação. Veja a seguir como a AppsFlyer processa os diferentes tipos de solicitação.

| **Tipo de solicitação**<br /><br />**(Direito)** | **Definição do GDPR** | Processamento da solicitação pela AppsFlyer |
| --- | --- | --- |
| **Acesso** | <ul><li>Se solicitado, os usuários do aplicativo têm o direito de saber se, por que e por quanto tempo o proprietário do aplicativo processará seus dados.</li><li>Se os dados forem compartilhados com terceiros, como a AppsFlyer, os usuários do aplicativo terão o direito de saber quem são esses terceiros.</li><li>O direito de saber quais categorias de dados estão sendo processadas.</li><li>Se houver processamento automatizado, isso tem um efeito significativo sobre eles.</li></ul> | Os proprietários do aplicativo recebem uma cópia dos dados pessoais processados dos usuários do aplicativo. |
| **Portabilidade** | O usuário do aplicativo precisa receber todos os seus dados pessoais em um formato estruturado, comumente usado e legível pela máquina, como um arquivo CSV. | O proprietário do aplicativo recebe umacópia dos dados pessoais processados pelo usuário do aplicativo. |
| **Retificação** | Permite que os usuários do aplicativo corrijam seus dados caso percebam que estão imprecisos ou inverídicos. Os proprietários devem apagar ou corrigir dados imprecisos ou incompletos. | <ul><li>A AppsFlyer exclui os dados do usuário do aplicativo gravados antes da data do pedido de retificação.</li><li>Os dados recebidos depois disso são gravados pela AppsFlyer.</li></ul> |
| **Exclusão** | O direito de exclusão requer que os proprietários do aplicativo removam dados pessoais até 10 dias após o recebimento da solicitação. | Os dados são excluídos |

<div id="appsflyer-gdpr-requests-api" />

## API de solicitações do GDPR da AppsFlyer

Use a API de solicitações do GDPR, conforme descrito nesta seção, para implementar a conformidade com o DSR.

* **Solicitação do GDPR:** executar um dos tipos de solicitação acima: "acesso", "portabilidade", "exclusão" ou "retificação".
* **Solicitação de status:** consultar o status atual de uma solicitação do GDPR
* **Solicitação de descoberta:** questionar a versão da API compatível e formato de dados
* **Cancelamento:** cancelar uma solicitação do GDPR durante sua fase pending/strong>

Os proprietários do aplicativo devem implementar alterações de UI em seus aplicativos, para que os usuários possam enviar solicitações. Observe que as solicitações de GDPR são para um usuário por vez.

<Accordion title="1. Solicitação do GDPR">

<div id="gdpr-request-flow" />

#### Fluxo da solicitação do GDPR

Todos os tipos de solicitação do GDPR, seja acesso, portabilidade, exclusão e retificação, possuem o mesmo fluxo:

1. **O usuário do aplicativo** envia uma solicitação.
2. **O proprietário do aplicativo** cria a solicitação GDPR (veja abaixo) e a envia para a AppsFlyer.
3. **A AppsFlyer** recebe a solicitação e responde com "201 OK" para solicitações válidas.
4. **Para acesso e portabilidade:** os pedidos são atendidos em até 8 dias.  
   **Atenção:** esse período de 8 dias começa quando o proprietário do aplicativo envia sua solicitação. O status da solicitação muda de pendente para "em andamento" e será concluído em mais 6 dias, totalizando 8 dias.  
   **Para exclusão e retificação:**
   * durante as 48 horas seguintes, a solicitação fica na fila com o status  ***pendente***. O usuário do aplicativo pode cancelar a solicitação.
   * Após 48 horas, o status da solicitação muda para ***in\_progress.*** A AppsFlyer envia um ***postback de alteração de status***. Nesse ponto, a solicitação não pode ser cancelada.
   * Em 10 dias (consulte a observação abaixo), a AppsFlyer atende à solicitação e o status da solicitação é atualizado para ***concluído***. A AppsFlyer envia um postback de alteração de status.

     * Em caso de *apagamento* ou *retificação*, os dados do Usuário do Aplicativo são excluídos.
     * No caso de *portabilidade* ou *acesso,* os dados do usuário do aplicativo podem ser acessados no painel da AppsFlyer abaixo de **GDPR** ou por meio da API de solicitação (veja abaixo).

     **Atenção:** esse período de 10 dias começa quando o proprietário do aplicativo envia sua solicitação. Após 48 horas, o status da solicitação muda para **em andamento** e será concluído dentro de mais 8 dias, totalizando 10 dias.

<div id="gdpr-request-format" />

#### Formato da solicitação do GDPR

Uma API de solicitação do GDPR pode ser enviada por meio de HTTP POST ao seguinte endpoint:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

Para a autorização da API, use o mesmo token da API V2 da Pull API. O usuário administrador <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#recuperar-tokens">recupera o token</Anchor> na página token da API no dashboard. Adicione o token ao cabeçalho da solicitação da seguinte forma: `'Authorization': 'Bearer %AuthTokenV2%'`

<div id="parameters" />

#### Parâmetros

<table><thead><tr><th><strong>Nome da propriedade</strong></th><th><strong>Obrigatoriedade</strong></th><th><strong>A descrição</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>Yes</td><td>String UUID v4. Gerado pelo controlador no momento do envio da solicitação a um Processador. Em seguida, pode ser usado para verificar o status da solicitação, atualizá-la ou cancelá-la.</td></tr><tr><td><strong>subject_request_type</strong></td><td>Yes</td><td><p>Valor de string que representa o tipo de solicitação do GDPR.  Valores suportados:</p><ul><li>apagamento</li><li>portabilidade</li><li>Acesso</li><li>retificação</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>Yes</td><td><ul><li>Uma matriz de objetos de identidade que define a identidade do solicitante (veja abaixo).</li><li>Cada solicitação pode conter apenas uma identidade de titular dos dados.</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>Yes</td><td><ul><li>String de data RFC 3339 da hora da solicitação original pelo titular dos dados.</li><li>Carimbos de data/hora em UTC</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>Yes</td><td><p>String que representa o aplicativo mobile para o qual essa solicitação está direcionada:</p><p><strong>Exemplos</strong>:</p><ul><li> <strong>iOS</strong>: id123456789</li><li> <strong>Android</strong>: com.exemplo, com.publishers.nome</li><li> <strong>Android fora da loja</strong>: com.pulbisher.nome-canal<br/><strong>Atenção:</strong> em alguns casos, os proprietários de aplicativos registram atribuição fora da loja usando o nome do Google Play para Android. Nesses casos, use o nome regular do aplicativo, conforme exibido no dashboard.</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>Sem</td><td>String de versão que representa a versão desejada da API de solicitação do GDPR</td></tr><tr><td><strong>status_callback_urls</strong></td><td>Não, mas recomendado</td><td><ul><li>Uma lista de até 3 endpoints para retornos de chamada de status a serem enviados para as seguintes alterações de status de solicitação.</li><li>Apenas endpoints https são compatíveis.</li><li>URLs inválidas são rejeitadas.</li></ul></td></tr><tr><td rowspan="2"> <strong>plataforma</strong><br/><br/> </td><td>Sem</td><td>O valor é uma das plataformas DSR suportadas:<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code> </td></tr><tr><td>Yes</td><td><p>Para uma solicitação de plataforma CTV, PC ou console, inclua qualquer uma das seguintes plataformas: </p><p><code>nativepc</code>, <code>playstation</code>, <code>roku</code>, <code>steam</code>, <code>webos</code>, <br/><code>vidaa</code>,<code>tizen</code>, <code>smartcast</code>, <code>chatgpt</code>, <code>battlenet</code>, <br/><code>quest</code>, <code>switch</code>, <code>xbox</code>, <code>epic</code></p></td></tr></tbody></table>

<div id="subject_identities-objects" />

#### Objetos subject\_identities

| Tipo de objeto | **Obrigatoriedade** | **A descrição** |
| --- | --- | --- |
| identity\_type | Yes | <ul><li>O tipo de identidade em formato de string para plataformas`android`, `ios`, `web` e `windowsphone` é qualquer um dos seguintes:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Para plataformas `CTV`, `PC` e `Console`, apenas:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID)</li></ul></li></ul><ul><li>Exemplo: `android_advertising_id`</li></ul>**Important**<br />**Importante!**<br /><br />Para usar o CUID através da API OpenDSR, você deve enviar o CUID com `idfa` / `appsflyer_id` dentro dos eventos do aplicativo usando: `event_name` ou `Login - Complete` |
| identity\_value | Yes | <ul><li>Formato: Sequência de caracteres</li><li>Exemplo: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | Yes | <ul><li>O método usado para codificar identity\_value: `raw` é o único compatível:</li><li>Exemplo: "raw"</li></ul> |

<div id="example-gdpr-erasure-request" />

#### Exemplo: Pedido de exclusão GDPR

**Exemplo de um pedido de exclusão para as plataformas** `android`, `ios`, `web`, `windowsphone`:

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

**Exemplo de um pedido de exclusão para as plataformas** `CTV`, `PC` **e** `Console`:

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

#### Exemplo de código da solicitação de apagamento do GDPR

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

  Request request = new Request. Builder()
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
""" usando o pacote requests do Python, 
instalação: pip install requests """

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
JavaPythonNode.jsC#
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
   request. AddHeader("Content-Type", "application/json");
   request. AddHeader("Accept", "application/json");
   request. AddHeader("Authorization: Bearer", "")
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

    request. AddParameter("undefined", body,ParameterType. RequestBody);
    IRestResponse response = client. Execute(request);
    // handle response by reading response. StatusCode
    Console. WriteLine(response.
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Status da solicitação">

Toda solicitação do GDPR enviada pode ter seu status consultado posteriormente, especificando o `subject_request_id`. Existem quatro tipos de status compatíveis:

1. ***pending*** - uma solicitação correta foi recebida e está atualmente na fila
2. ***in\_progress*** - uma solicitação está sendo executada no momento
3. ***completed*** - uma solicitação foi atendida
4. ***cancelled*** - uma solicitação foi cancelada

<div id="status-request-format" />

#### Formato da solicitação de status

Uma solicitação de status pode ser enviada por meio de HTTP GET ao seguinte endpoint:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="status-response-example" />

#### Exemplo da resposta de status

```http
HTTP/1.1 200 OK Content-Type: application/json X-OpenGDPR-Processor Domain: example processor.com X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

<div id="status-postbacks" />

#### Postbacks de status

Conforme descrito no Fluxo da solicitação do GDPR acima, quando o status de uma solicitação do GDPR é alterado, de ***pending*** para ***in\_progress*** para ***completed***, a AppsFlyer envia um postback do GDPR aos endpoints solicitantes, especificados com a propriedade **status\_callback\_urls**.

Exemplo de postback de status:

```http
POST /opengdpr_callbacks HTTP/1.1 Host: examplecontroller.com Content-Type: application/json X-OpenGDPR-Processor Domain: gdpr.appsflyer.com X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

<div id="validate-postback" />

#### Validar postback

**Para validar a autenticidade dos postbacks recebidos**:

1. Crie uma lista de permissões de todos os domínios do processador que você permite fazer callbacks.
2. Se o valor do header para `X-OpenGDPR-Processor-Domain` estiver na sua lista de permissões, busque o certificado.
   * A URL do certificado é o valor de `processor_certificate` no corpo da resposta `/discovery`.
   * Você também pode buscar o certificado diretamente do endpoint do AppsFlyer usando o token da API V2 como um token bearer no cabeçalho de autorização: `GET https://hq1.appsflyer.com/api/gdpr/v1/certificate`
3. Valide o certificado usando uma biblioteca para confirmar que o certificado:
   1. Foi emitido por uma autoridade confiável.
   2. Foi emitido para a mesma string fornecida no valor `X-OpenGDPR-Processor-Domain` do header.
   3. Não está expirado.
4. Depois de confirmar que o certificado é válido, use-o para validar o header `X-OpenGDPR-Signature` no corpo da solicitação bruta. A AppsFlyer usa SHA256 RSA como um algoritmo de assinatura.
5. Obtenha uma resposta no header de status:
   1. `202 Accepted` se a validação for bem-sucedida.
   2. `401 Unauthorized` `401 Unauthorized` se a assinatura não for validada ou o domínio do processador não estiver em sua lista de permissões.

</Accordion>

<Accordion title="3. Solicitação de relatório">

Depois que uma solicitação de **acesso ou solicitação** de **portabilidade** for concluída, você poderá baixar o relatório via HTTP GET para o seguinte endpoint:

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

O relatório gerado fica disponível durante catorze dias a partir do momento da conclusão.

</Accordion>

<Accordion title="4. Processo de solicitação de descoberta">

Para saber sobre os formatos compatíveis com a AppsFlyer, uma solicitação de descoberta pode ser enviada por meio de HTTP GET ao seguinte endpoint:

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

<div id="discovery-response-example" />

#### Exemplo da resposta de descoberta

```http
HTTP/1.1 200 OK Content-Type: application/json
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

<Accordion title="5. Solicitação de cancelamento">

É possível cancelar um pedido de GDPR, com base no seu `subject_request_id`, mas apenas durante a fase ***pendente***.

Para enviar um HTTP DELETE com `subject_request_id`:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

<div id="cancellation-response" />

#### Resposta de cancelamento

Quando uma solicitação de cancelamento do GDPR é recebida, a AppsFlyer retorna uma resposta HTTP com código de status 202 e diversos outros parâmetros.

Depois que o cancelamento da solicitação ocorre, a AppsFlyer envia um postback com o status ***cancelado***.

</Accordion>

<Accordion title="6. API de teste das solicitações do GDPR">

Essa API da AppsFlyer é uma API de teste para a API de solicitações do GDPR.

<div id="how-does-it-work" />

#### Como funciona?

A API funciona da seguinte forma:

1. Assim que uma solicitação do GDPR for feita, a solicitação é colocada imediatamente no status "Pending". Para fins de teste, o status é alterado a cada 30 segundos.

2. Se um endpoint para um postback de status foi inserido na solicitação do GDPR, um primeiro postback é enviado logo após a solicitação e dois outros postbacks de status são enviados em intervalos de 30 segundos.

**Endpoint de teste da solicitação do GDPR**: POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Endpoint de teste da solicitação de status**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Endpoint de teste da solicitação de descoberta**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Endpoint de teste da solicitação de cancelamento**: DELETE

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Endpoint de teste de certificado**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**Endpoint de teste de relatórios de acesso/portabilidade**: GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **Note**
>
> **Observações**
>
> * Um token de API V2 válido deve ser inserido no header da solicitação da seguinte forma: `'Authorization': 'Bearer %AuthTokenV2%'`
> * Em "property\_id", o ID do aplicativo deve pertencer ao proprietário da conta (de acordo com o token da API).

</Accordion>

<Accordion title="7. Registros de solicitações">

O usuário administrador da conta pode acessar as solicitações de GDPR enviadas no Logs Dashboard.

Para obter acesso completo e solicitações de portabilidade, também é possível fazer download do relatório a partir do painel.

Para acessar o Logs Dashboard:

1. Na barra superior, abra o menu da conta (menu suspenso do endereço de e-mail) > **E-GDPR log**.
2. A janela a seguir será aberta:

<Image align="center" alt="GDPR_Table.png" src="https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png" />

</Accordion>

<Accordion title="8. Códigos de retorno e mensagens de erro da GDPR API">

Os códigos de retorno e mensagens de erro da GDPR API HTTP estão detalhados nessa seção.

<div id="gdpr-api-return-codes" />

#### Códigos de retorno da GDPR API

| Código de retorno | Visão geral |
| --- | --- |
| 201 | Criado |
| 202 | Solicitação de cancelamento recebida |
| 400 | Erro na solicitação. O corpo contém o código de erro e a mensagem conforme listado na tabela a seguir. |

<div id="http-return-code-400---bad-request" />

#### Código de retorno HTTP 400 - solicitação incorreta

Mensagens com código de retorno 400 contêm um JSON com o código de erro e mensagem.

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

<div id="return-code-400-bad-request-messages" />

#### Código de retorno 400 mensagens de erro na solicitação

| Código do erro | Descrição do erro (mensagem) |
| --- | --- |
| e211 | Não é possível cancelar uma solicitação com status inválido |
| e212 | Solicitação não permitida. A eliminação está em andamento para o identificador. |
| e213 | A solicitação já existe |
| e214 | Solicitação não encontrada |
| e215 | Uma ou mais identidades do titular já existem em uma solicitação aberta. se outra solicitação para o mesmo identity\_value estiver aberta no momento, no estado ‘pending’ ou ‘in\_progress’. |
| e311 | Tipo de conteúdo de solicitação inválido |
| e312 | Versão da API inválida |
| e313 | subject\_request\_id inválido |
| e314 | Formato do submitted\_time inválido |
| e315 | Comprimento do status\_callback\_url inválido |
| e316 | Formato do status\_callback\_url inválido |
| e317 | Formato do app\_id inválido |
| e318 | Identity\_type inválido |
| e319 | A plataforma do aplicativo não corresponde aos tipos de identidade |
| e321 | Usuários LAT não são compatíveis com api |
| e322 | subject\_request\_type inválido |
| e323 | Formato de subjet\_identities inválido |
| e324 | Comprimento subject\_identities inválido |
| e325 | Valor de subjet\_identities inválido |
| e326 | Formato JSON inválido no corpo da solicitação |
| e411 | AppID está incorreto ou não pertence à sua conta |
| e412 | Sem permissão para eliminar a solicitação de apagamento |
| e413 | Sem permissão para visualizar a solicitação |
| e511 | Problema interno, aguarde 60 minutos e tente novamente. Se o problema persistir, entre em contato com o suporte da AppsFlyer: support@appsflyer.com support@AppsFlyer.com support@AppsFlyer.com |

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

* **Limite de taxa da OpenDSR API: 350 solicitações por minuto**. Ultrapassar esse limite resultará em um erro, exigindo que a solicitação seja reenviada. Manter-se dentro deste limite de taxa permite até 504.000 solicitações por dia.
* Verificar o status de uma solicitação de mais de 60 dias atrás retorna "solicitação não encontrada".

<div data-zendesk-anchors="privacy-regulations=regulamentos-de-privacidade h_01HB866TQ0AWHQ9659Q8Q4XMQM=regulamentos-de-privacidade the-opendsr-initiative=a-iniciativa-do-opendsr h_01HB866TQ0R18S4GCH3KPGNJHD=a-iniciativa-do-opendsr definitions=defini%C3%A7%C3%B5es h_01HB866TQ06XV2AJDMA3M5Q5KK=defini%C3%A7%C3%B5es dsr-requirements=requisitos-do-dsr h_01HB866TQ0JNEZTHQ7BR1TMD5M=requisitos-do-dsr appsflyer-gdpr-requests-api=api-de-solicita%C3%A7%C3%B5es-do-gdpr-da-appsflyer h_01HB866TQ0HNFGF9QTJNT792N7=api-de-solicita%C3%A7%C3%B5es-do-gdpr-da-appsflyer gdpr-request-flow=fluxo-da-solicita%C3%A7%C3%A3o-do-gdpr h_01HB866TQ0FCZGQ1DWENVSWHSG=fluxo-da-solicita%C3%A7%C3%A3o-do-gdpr gdpr-request-format=formato-da-solicita%C3%A7%C3%A3o-do-gdpr h_01HB866TQ0GC7V1081GT53TWEZ=formato-da-solicita%C3%A7%C3%A3o-do-gdpr parameters=par%C3%A2metros h_01HB866TQ0CFAC0X2Y98B4EE5Q=par%C3%A2metros subject_identities-objects=objetos-subject_identities h_01HB866TQ02HMKJMKKPHHR4CMN=objetos-subject_identities example-gdpr-erasure-request=exemplo-pedido-de-exclus%C3%A3o-gdpr h_01HB866TQ1CT316PTFBJC59C79=exemplo-pedido-de-exclus%C3%A3o-gdpr h_01HB866TQ1D7290A6G29Q4HDE7=exemplo-de-c%C3%B3digo-da-solicita%C3%A7%C3%A3o-de-apagamento-do-gdpr status-request-format=formato-da-solicita%C3%A7%C3%A3o-de-status h_01HB866TQ1YEZZ4M6QMHTKCEGX=formato-da-solicita%C3%A7%C3%A3o-de-status status-response-example=exemplo-da-resposta-de-status h_01HB866TQ1M7G7JNH0V7TEVFYY=exemplo-da-resposta-de-status status-postbacks=postbacks-de-status h_01HB866TQ1109WJ2J13D8FM8KX=postbacks-de-status validate-postback=validar-postback h_01HB866TQ1YG0B6JDEQ2KMFEN0=validar-postback discovery-response-example=exemplo-da-resposta-de-descoberta h_01HB866TQ1AJCSS2442EEWA19X=exemplo-da-resposta-de-descoberta cancellation-response=resposta-de-cancelamento h_01HB866TQ1F72KP3S55ZJYC8Y7=resposta-de-cancelamento how-does-it-work=como-funciona h_01HB866TQ1KFRGX7NZCSJWVW0T=como-funciona gdpr-api-return-codes=c%C3%B3digos-de-retorno-da-gdpr-api h_01HB866TQ128R2TSHS4JTCQK70=c%C3%B3digos-de-retorno-da-gdpr-api http-return-code-400-bad-request=c%C3%B3digo-de-retorno-http-400---solicita%C3%A7%C3%A3o-incorreta h_01HB866TQ1A51STZQCJC5TV65X=c%C3%B3digo-de-retorno-http-400---solicita%C3%A7%C3%A3o-incorreta return-code-400-bad-request-messages=c%C3%B3digo-de-retorno-400-mensagens-de-erro-na-solicita%C3%A7%C3%A3o h_01HB866TQ10MAMTS9WB0CKN55V=c%C3%B3digo-de-retorno-400-mensagens-de-erro-na-solicita%C3%A7%C3%A3o limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HB866TQ1PXGRX5JRHRSCT0EN=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
