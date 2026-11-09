---
title: API de eventos Servidor para servidor para PBA (Web-S2S)
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
  edited_at: '2026-08-19T00:23:20Z'
  id: 360006997298
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360006997298
---
> **Resumo:** Use a API de eventos de servidor para servidor Web (Web-S2S) para relatar eventos e conversões para PBA que não são relatados pelo Web SDK.

<Image align="center" alt="5107_Infographic_Web_S2S_759x270_option1.jpg" src="https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg" />

<div id="web-server-to-server-events-api-for-pba" />

## API web de eventos de servidor para servidor para PBA

A API Web-S2S para atribuição baseada em pessoas complementa o <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide">Web SDK</Anchor> permitindo que os profissionais de marketing relatem eventos que ocorrem em seus sites, mas fora do escopo do Web SDK. Por exemplo, um visitante do site (um usuário da web), aciona um evento de pagamento online, processado por sistemas de backend. Após o processamento, o backend, usando a API S2S, relata o evento à AppsFlyer.

Eventos enviados pela API do S2S:

* são registrados de forma semelhante aos eventos relatados pelo Web SDK
* são incluídos nos painéis do PBA se definidos como eventos de conversão
* preenchem dados brutos de PBA com o campo *event\_source* definido como *]web S2S*

<div id="api-use-instructions" />

## Instruções de uso da API

Crie sua chamada de API usando as seções a seguir.

| Não. | Item | Observações |
| --- | --- | --- |
| 1 | Usuário único (EN: Unique user) | <ul><li>Forneça-nos a melhor ID de usuário único possível. Isso tem um impacto significativo na análise dos dados.</li><li>A prática recomendada é enviar a customerUserId. Se não estiver disponível, envie a afUserId sendo a ID do cookie do site definida pelo WebSdk.</li><li>A qualquer momento você associa sua ID de usuário do cliente (<Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">CUID</Anchor>) com o [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid) enviar uma mensagem setCuID() com ambas as IDs.</li></ul> |
| 2 | Carimbo de data/hora | <ul><li>A AppsFlyer aplica uma validação rigorosa aos timestamps de eventos recebidos:</li></ul><ul><li>**Eventos que chegam atrasados:** Eventos são aceitos com seu timestamp original se chegarem dentro do período de 24 horas do dia ao qual pertencem. **Por exemplo**, um evento com um timestamp de segunda-feira (2025-08-18 23:59 UTC) manterá esse timestamp se for enviado **a qualquer momento até terça-feira** 23:59:59 UTC. Se o mesmo evento for enviado após terça-feira 23:59:59 UTC, o timestamp será substituído pelo horário de recepção do servidor.</li><li>**Timestamps futuros:** Eventos com um timestamp posterior ao horário de chegada real não são permitidos. Esses timestamps também são substituídos pelo horário de recepção do servidor.</li></ul><ul><li>Os timestamps são baseados em UTC. Se necessário, converta da hora local para a hora UTC antes de preencher o parâmetro</li></ul> |
| 3 | Receita e moeda | Você deve preencher *eventRevenueCurrency* e *eventRevenue* mesmo que eles estejam contidos no eventValue. Faça isso porque os usamos em nossos painéis. |

<div id="api-basics" />

<Accordion title="Noções básicas da API">

A implementação da API requer as seguintes credenciais disponíveis no painel:

* ID do agrupamento (também conhecida como ID do agrupamento da marca)
* Chave do desenvolvedor web

**Para obter as credenciais:**

1. Na AppsFlyer, no menu superior, selecione **Meus aplicativos** > **Exibir agrupamentos de marca.**  
   A lista de agrupamentos é exibida.
2. Copie e registre:
   * ***ID do agrupamento de marca***
   * ***Chave do desenvolvedor web***

<div id="web-s2s-api-basics" />

#### Noções básicas da API Web S2S

| Caminho | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`: A ID do agrupamento de aplicativos está disponível no painel.</li><li>`method` sendo um dos seguintes:<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): enviar para eventos de backend relatáveis</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) enviar ao associar afUserId com seu CUID</li></ul></li></ul> |
| --- | --- |
| Método HTTP | `POST` |
| Tipo de conteúdo aceito | `application/json` |
| Limitação de carga útil JSON | Tamanho da carga útil JSON: máximo de 1KB |
| Limitação de taxa | Volume de limitação do POST: 60.000 POSTs por minuto. Para aumentar o limite, entre em contato com seu CSM. |
| TLS | <ul><li>TLS 1.2 ou posterior</li><li><Anchor target="_blank" href="/marketers/pt/docs/appsflyer-https-ssl-encryption-policy-support#mensagens-de-saída-appsflyer-como-cliente">Cifras suportadas</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="método setCuId">

| Nome do método | setCuId |
| --- | --- |
| Caso de uso | Ao associar um CUID a um visitante do seu site. Por exemplo, sempre que você fizer a correspondência da web `afUserId` com a ID de usuário do cliente. Isso permite que o PBA corresponda dados de várias fontes. Isso é semelhante a <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> no site. |
| Caminho do método | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Carga útil | A carga JSON consiste nos parâmetros listados aqui. Todos os parâmetros são obrigatórios.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

<div id="curl-example-setcuid" />

#### Exemplo de Curl setCuId

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

<Accordion title="Método do evento">

| Nome do método | event |
| --- | --- |
| Caso de uso | Enviar |
| Caminho do método | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Informações detalhadas | [Detalhes do método do evento](/docs/web-server-to-server-events-api-for-pba-web-s2s#detalhes-do-método-do-evento) deste artigo contém detalhes de carga útil, exemplo de Curl, exemplo de Python e sugestões de teste. |

</Accordion>

<div id="event-method-details" />

## Detalhes do método do evento

<div id="payload-parameters" />

<Accordion title="Parâmetros do payload">

Os parâmetros de carga útil são divididos em identificadores de usuário e parâmetros de evento.

* ID do usuário: <mark>você deve enviar pelo menos um parâmetro de ID de usuário.</mark>
* Evento: envie os parâmetros obrigatórios e opcionais conforme necessário.

<div id="user-identifier-parameters-send-at-least-one-parameter" />

#### Parâmetros do identificador do usuário (enviar pelo menos um parâmetro)

| Parâmetro de ID do usuário | Descrição |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">O ID de usuário do cliente (CUID)</Anchor> é um identificador exclusivo definido por você.<ul><li>Use o identificador idêntico para eventos relatados por qualquer meio à AppsFlyer. Ou seja, o mesmo identificador é usado no web SDK, no mobile SDK e nas APIs S2S.</li><li><Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">ID do usuário cliente do web SDK</Anchor></li><li>Formato: Sequência de caracteres</li><li>Exemplo: `"customerUserId" : "663274"`</li><li>Preenche o campo de dados brutos: `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | O ID de usuário exclusivo atribuído pelo web SDK a cada usuário que visita seu site. Você precisará passar o valor do cookie para seus servidores de backend.<ul><li>Detalhes do cookie:<ul><li>Nome: afUserId</li><li>Valor: defina *afUserId* para este valor</li><li>Domínio: website-domain</li></ul></li><li>Exemplo: `"afUserId" : "unique_cookie_uuid"`</li><li>Preenche o campo de dados brutos: `af_web_id`</li></ul> |

<div id="event-parameters" />

#### Parâmetros do evento

| Nome do parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | Sim | Preencha usando a [chave do desenvolvedor web](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) disponível no painel.<ul><li>Exemplo:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | Sim | Identificador de atributo de evento para uso interno pela AppsFlyer. Sempre definido como *EVENTO.*<ul><li>Exemplo: `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | Sim | <ul><li>Usamos esse parâmetro para diferenciar eventos de conversão e não conversão usando a <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#web-event-settings">lista de conversão de eventos</Anchor> definida pelo profissional de marketing nas configurações do PBA.</li><li>Certifique-se de preenchê-lo com valores consistentes com a lógica de conversão do profissional de marketing.</li><li>Formato: Sequência de caracteres</li><li>Exemplo: `"eventName" : "web_purchase"`</li><li>Preenche o campo de dados brutos: `event_name`</li></ul> |
| <span id="timestamp"></span>timestamp | Não | Tempo em que o evento ocorreu em milissegundos. Enviar como um <Anchor target="_blank" href="https://www.unixtimestamp.com/">carimbo de data/hora Unix</Anchor> com 13 dígitos.<ul><li>Se nenhum carimbo de data/hora for enviado, a hora será definida usando a hora do servidor.</li><li>**Os eventos que chegam atrasados são marcados com data e hora usando a hora atual do servidor.** Tarde significa chegada após a meia-noite UTC do dia seguinte ao evento. Por exemplo, um evento que ocorre na segunda-feira **deve** ser processado antes da meia-noite UTC de terça-feira.</li><li>Os eventos com carimbo de data/hora no futuro (em relação à hora atual do servidor) são marcados com carimbo de data/hora com a hora do servidor.</li><li>Formato: Int</li><li>Exemplo: `"timestamp" : 1584835200123`</li><li>Preenche o campo de dados brutos: `event_time`</li></ul> |
| <span id="eventvalue"></span>Valor do evento | Não | Mapa de parâmetros de eventos que descrevem o evento. Use este parâmetro para enviar eventos avançados in-app como SKU do produto, preço do item de linha.<ul><li>**Observação sobre a receita!** você pode preencher esse parâmetro com detalhes de receita. Além disso, você deve preencher *eventRevenue* e *eventRevenueCurrency.*</li></ul><ul><li>Formato: JSON</li><li>Exemplo: Para enviar SKU ABC123, com uma cor azul e um preço unitário de $3.99 defina eventValue para:<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>Limitação: 1000 caracteres. Não exceda o limite permitido.</li><li>Preenche o campo de dados brutos: `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | Não | Código de moeda de um evento de receita, sendo um código de moeda <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> de três caracteres.<ul><li>Predefinição: USD</li><li>Formato: Sequência de caracteres</li><li>Exemplo:  `"eventRevenueCurrency" : "EUR"`</li><li>Preenche o campo de dados brutos: `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | Não | Receita (valor monetário) atribuída a um evento.<br /><br />**Atenção!** Se a receita for relatada em *eventValue,* relate-a também em *eventRevenue* e preencha eventRevenueCurrency.<ul><li>Valores negativos permitidos. Por exemplo, um reembolso.</li><li>Formato: Float</li><li>Valores de exemplo: `1` `1.2` `1234.20` `-1234.20`</li><li>Preenche o campo de dados brutos: `event_revenue`</li></ul> |
| <span id="eventcategory"></span>~~eventCategory~~ | Não | Esse parâmetro foi preterido e será removido do sistema em uma data futura. Em vez disso, use eventValue. |
| <span id="eventlabel"></span>~~eventLabel~~ | Não | Esse parâmetro foi preterido e será removido do sistema em uma data futura. Em vez disso, use eventValue. |
| <span id="referrer"></span>referrer | Não | Referência HTTP<ul><li>Formato: Sequência de caracteres</li><li>Exemplo:`"referrer" : "https://www.google.com/"`</li><li>Preenche o campo de dados brutos: `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | Não | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">Solicitação de agente do usuário</Anchor> enviada pelo navegador ao servidor.<ul><li>Sempre que possível, envie esse valor, pois ele auxilia na determinação do tipo de dispositivo.</li><li>Formato: Sequência de caracteres</li><li>Exemplo: `"userAgent" : "Chrome/80.0.3987"`</li><li>Preenche o campo de dados brutos: `user_agent`</li></ul> |
| <span id="ip"></span>ip | Não | Endereço IP do usuário<ul><li>Sempre que possível envie o valor deste campo. Auxilia na determinação da <Anchor target="_blank" href="/marketers/pt/docs/determine-user-location">geolocalização</Anchor> do usuário.</li></ul><ul><li>Formato: Sequência de caracteres</li><li>Exemplo:`"ip": "192.0.2.1"`</li><li>Preenche o campo de dados brutos: `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Exemplo de Curl">

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

<Accordion title="Exemplo de Python">

```python
''' usando o pacote requests python, instale usando pip install requests  '''
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

<Accordion title="Testes">

Para fins de teste, envie vários eventos da seguinte maneira:

1. Envie um evento.
2. Certifique-se de obter um código de retorno 200 OK. Caso contrário, execute uma ação corretiva usando os códigos de retorno e as mensagens de erro.
3. Aguarde várias horas após a meia-noite UTC para ver o evento relatado nos dados brutos do PBA. Você deve aguardar porque os dados do PBA são processados uma vez por dia.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="getting-the-web-dev-key" />

<Accordion title="Obtendo a chave do desenvolvedor web">

**Para obter a chave do desenvolvedor web:**

1. Na AppsFlyer, vá para a aba ***Meus Aplicativos***.
2. No campo (C) ***filtro*** field, enter `afUserId`  
   O valor de afUserID é exibido.

   <Image align="center" alt="GetWebDevKeyPba_us-en.pn" src="https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png" />
3. Copie a chave do desenvolvedor web necessária.

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Extraindo o afUserID do Web SDK">

* O `afUserId` é um identificador exclusivo definido pelo Web SDK quando um usuário visita seu site pela primeira vez.
* Se você precisar `afUserId`use um dos métodos a seguir.

<div id="get-afuserid-from-the-http-cookie-header" />

#### **Obtenha afUserId do cabeçalho do cookie HTTP**

* O `afUserId` é enviado pelo navegador de visitantes em chamadas para o seu site.
* Extraia-o do cabeçalho do cookie HTTP, se necessário.

<div id="viewing-afuserid-in-the-visitors-browser" />

#### **Visualizando afUserId no navegador do visitante**

* Visualize o`afUserId` no navegador do visitante, para fins de solução de problemas e depuração.
* Para que ele esteja disponível, o visitante precisa ter visitado primeiro uma página com o Web SDK pelo menos uma vez.
* O cookie que contém `afUserId` é um cookie primário em relação ao seu domínio.
* O procedimento a seguir foi preparado usando o Chrome 81. Pode haver algumas diferenças entre vários navegadores e sistemas operacionais.

**Para obter o afUserId do navegador do visitante:**

1. No seu navegador, acesse seu site.
2. Clique com o botão direito do mouse, selecione ***Inspecionar***  
   A janela do elemento de inspeção do navegador é aberta.

   <Image align="center" alt="S2S_inspect.jpg" src="https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg" />
3. Vá para a aba (A) ***Aplicativo***.
4. No menu lateral (B), expanda Cookies.
5. Selecione seu site. Se ele não for exibido, atualize o navegador.
6. No campo de ***filtro*** (C), insira `afUserId`  
   O valor de afUserID é exibido.

</Accordion>

<div id="response-codes" />

<Accordion title="Códigos de resposta">

| Código de resposta | Mensagem | O que fazer |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Não encontrado | <ul><li>Verifique o endpoint</li><li>Verifique se a ID do agrupamento está correta</li></ul> |
| 400 | Erro na solicitação | <ul><li>Há um erro no JSON. Consulte a mensagem de erro para mais detalhes.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolução de problemas">

* Sintoma: Os códigos de retorno HTTP não retornam  
  Solução: Incluir servidores da AppsFlyer na lista de permissões

</Accordion>

<div id="release-notes" />

<Accordion title="Notas de versão">

<table><caption>Notas de versão do Web SDK</caption><thead><tr><th>Data </th><th>Versão do endpoint\*</th><th>Observações</th></tr></thead><tbody><tr><td>12/05/2020</td><td>1</td><td> Lançamento inicial</td></tr><tr><td>24/05/2020</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* O número da versão refere-se ao número da versão do endpoint. <code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=api-web-de-eventos-de-servidor-para-servidor-para-pba h_01HKW2YAW4HHYK27F41HC3B24Y=api-web-de-eventos-de-servidor-para-servidor-para-pba api-use-instructions=instru%C3%A7%C3%B5es-de-uso-da-api h_01HKW2YAW4DCESP3MNY9D4GTFK=instru%C3%A7%C3%B5es-de-uso-da-api h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=no%C3%A7%C3%B5es-b%C3%A1sicas-da-api-web-s2s h_01HKW2YAW4XDKZ3YGAHAP3AG2T=no%C3%A7%C3%B5es-b%C3%A1sicas-da-api-web-s2s h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=exemplo-de-curl-setcuid h_01HKW2YAW5SJFKGTNRGRKN6NCJ=exemplo-de-curl-setcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=detalhes-do-m%C3%A9todo-do-evento h_01HKW2YAW53H43SCYTDXAYBDHX=detalhes-do-m%C3%A9todo-do-evento h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=par%C3%A2metros-do-identificador-do-usu%C3%A1rio-enviar-pelo-menos-um-par%C3%A2metro h_01HKW2YAW5RR4Q2PCWC9717ACG=par%C3%A2metros-do-identificador-do-usu%C3%A1rio-enviar-pelo-menos-um-par%C3%A2metro event-parameters=par%C3%A2metros-do-evento h_01HKW2YAW5G46ZV4Z0CYEWB011=par%C3%A2metros-do-evento h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=informa%C3%A7%C3%B5es-adicionais h_01HKW2YAW5D4N3SYA625F10YFW=informa%C3%A7%C3%B5es-adicionais h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=obtenha-afuserid-do-cabe%C3%A7alho-do-cookie-http h_01HKW2YAW5FK04C3AWCXGP1XAW=obtenha-afuserid-do-cabe%C3%A7alho-do-cookie-http viewing-afuserid-in-the-visitors-browser=visualizando-afuserid-no-navegador-do-visitante h_01HKW2YAW5CT2WZ229KJD2FWYK=visualizando-afuserid-no-navegador-do-visitante h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
