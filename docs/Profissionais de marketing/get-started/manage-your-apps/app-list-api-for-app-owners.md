---
title: API de lista de aplicativos para proprietários de aplicativos
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-08-19T00:17:01Z'
  id: 360011999877
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/360011999877
---
> **Resumo:** Recupere os aplicativos ativos e pendentes associados à sua conta da AppsFlyer.

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

Se você for uma ad network, use a <Anchor target="_blank" href="/partners/pt/docs/app-list-api-for-ad-networks">API de lista de aplicativos para ad networks</Anchor>.

**Leitura adicional**: <Anchor target="_blank" href="/marketers/pt/docs/about-advertiser-apis">Lista de APIs para anunciantes</Anchor>

<div id="get-app-list-api" />

## Obter a API de lista de aplicativos

As seções a seguir incluem as informações necessárias para usar a API.

**Noções básicas para obter a lista de aplicativos**

<div id="get-api-list-basics" />

<Accordion title="Noções básicas da lista de APIs">

<table><thead><tr><th>Categoria</th><th>Item</th><th><span>A descrição</span></th></tr></thead><tbody><tr><td rowspan="3">Solicitação</td><td>Método HTTP</td><td><code>BAIXAR</code></td></tr><tr><td>Caminho</td><td><span>https://hq1.appsflyer.com/api/mng/apps</span></td></tr><tr><td>Cabeçalho de autorização </td><td><ul><li>O cabeçalho de autorização obrigatório contém um token Bearer. </li><li>Um usuário administrador obtém o token no dashboard da seguinte forma: <a href="./managing-appsflyer-tokens" target="_blank">O administrador acessa a lista suspensa do e-mail &gt; tokens de API para obter o token V2.0</a> </li></ul></td></tr><tr><td rowspan="3"> Tempo de</td><td>Resultados</td><td>Retorna em um JSON</td></tr><tr><td>Limite de solicitação</td><td><ul><li>20 solicitações/minuto</li><li>100 solicitações/dia</li></ul></td></tr><tr><td>Limite de registros</td><td>1.000 registros/solicitação. Se houver mais de 1.000 registros a serem retornados, use solicitações de paginação subsequentes descritas neste artigo.</td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="Solicitação de API">

A solicitação da API consiste no método, caminho, parâmetro obrigatório de capabilities e parâmetros opcionais de paginação. O token está contido no cabeçalho de autorização.

**Mensuração**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

Parâmetros obrigatórios para obter a lista de aplicativos:

| Parâmetro de consulta | A descrição |
| --- | --- |
|  | Não há parâmetros de consulta obrigatórios para esta API |

<div id="pagination-mechanism" />

#### **Mecanismo de paginação**

Um mecanismo de paginação, sempre operacional, está implementado.

**Princípios da paginação:**

* Retorna até 1.000 registros por solicitação (página).
* Os JSONs de resposta contêm as seguintes chaves relacionadas à paginação:
  * **meta.total\_items**: o número de registros a serem retornados por todas as páginas combinadas. Isso representa o número de aplicativos para os quais você recebeu as *capabilities* sendo consultadas.
  * Os links de paginação (mostrados no JSON a seguir) têm as seguintes chaves:
    * **links.prev**: se houve uma solicitação anterior, a solicitação usada para gerar a página anterior.
    * **links.self**: a solicitação atual, usada para gerar o JSON (página) atual
    * **links.next**: a solicitação necessária para obter a próxima página. Se não houver uma chave *next* , esta é a última página.

**Use um dos seguintes métodos de controle de paginação:**

* [Melhores práticas] Use os *links* no JSON: se a chave *links.next* existir, use-a para criar uma solicitação para obter a próxima página. Continue fazendo isso até receber um JSON sem a chave *links.next* .
* Implemente programaticamente os parâmetros *limit* e *offset* em conjunto com a chave *total\_items*.

**Exemplo de JSON de links de paginação**

* O exemplo a seguir contém o resultado da segunda solicitação, composto por dois registros na seção de dados (não exibida).
* O número total de registros a retornar é 6.
* A chave **links.next** contém a solicitação que retorna a segunda página: registros 5 e 6.

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

Parâmetros do mecanismo de paginação (opcional):

| Parâmetro de consulta | A descrição |
| --- | --- |
| limite | Número de registros retornados por chamada<ul><li>Máximo: 1,000</li><li>Se você não enviar`limit`, ele será definido automaticamente como 1,000.</li><li>Exemplo: `limit=2`</li><li>Obrigatório: Não</li></ul> |
| offset | O primeiro registro a ser retornado na chamada. Os números dos registros começam em 0.<ul><li>Se você não enviar `offset`, ele será definido automaticamente como 0.</li><li>Exemplo: `offset=2`</li><li>Obrigatório: Não</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="Resposta JSON">

| **Chave** | **A descrição** |
| --- | --- |
| id | ID do aplicativo, por exemplo: `id123456789`, `com.myapp.com` |
| Tipo | Sempre retornar `app` |
| coluna | Nome da aplicação |
| platforma | as integrações de SDK do iOS e Android |
| símbolos monetários | Código de moeda específico do aplicativo |
| time\_zone | Fuso horário específico do app |
| total\_items | Número de aplicativos na conta |
| links | Mecanismo de paginação (explicado na seção de parâmetros)<ul><li>prev: a chamada usada para gerar a página anterior</li><li>self: a chamada usada para gerar a página atual</li><li>next: a chamada usada para gerar a próxima página</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="Exemplo de cURL e resposta da lista de aplicativos">

**Requisição cURL**

Este exemplo inclui uma chamada completa, incluindo parâmetros opcionais de paginação.

```bash
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}' \ \
```

**Resposta JSON**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="Códigos de resposta HTTP">

| Código | Mensagem | Observações/solução de problemas |
| --- | --- | --- |
| 200 | OK | Dados válidos retornados |
| 200 | OK | **Sintoma**: Nenhum dado é retornado<br /><br />**Ação**: Verifique se o token de autenticação está no cabeçalho Bearer. |
| 400 | Pedido incorreto | Consulte a mensagem contida no JSON |
| 401 | Não autorizado | **Mensagem**: O token de autorização está malformado<br /><br />Certifique-se de que você tenha o token correto; ele deve ter mais de 700 caracteres. |
| 404 | Não encontrado | <ul><li>Resolva quaisquer problemas relacionados à network ou ao firewall.</li><li>Certifique-se de que os <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-server-ip-address-ranges-allowlisting">endereços IP da AppsFlyer estejam na allowlist</Anchor></li><li>Certifique-se de usar o token emitido mais recentemente.</li><li>Nenhum dado encontrado: nenhum aplicativo encontrado.</li></ul> |
| 429 | Pedidos em excesso | Limite de requisições excedido |

</Accordion>

<div data-zendesk-anchors="get-app-list-api=obter-a-api-de-lista-de-aplicativos h_01KQS56KS2G7TD4VHZCHVP0W9S=obter-a-api-de-lista-de-aplicativos h_01KQS56KS26TY81ACBN2XBK3W2=get-api-list-basics h_01KQS56KS27NETZ4C5RY28V804=api-request pagination-mechanism=mecanismo-de-pagina%C3%A7%C3%A3o h_01KQS56KS33VFVX099T1S2928G=mecanismo-de-pagina%C3%A7%C3%A3o h_01KQS56KS3Q5EEVSSC7G1FEFXR=json-response h_01KQS56KS3EZCH1KBBQQKTXWYP=get-app-list-curl-example-and-response h_01KQS56KS3S04KDZ58J7XKQNCK=http-response-codes" />
