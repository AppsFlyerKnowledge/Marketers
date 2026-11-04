---
title: Públicos-alvo — API de Identificadores Adicionais
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-06T00:18:14Z'
  id: 4411552670993
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/4411552670993
---
> **Num relance:** Utilize a API de Identificadores Adicionais para carregar em massa identificadores de utilizadores dos seus sistemas internos (como BI e CRM) para o AppsFlyer Audiences, permitindo uma comunicação de público mais abrangente com parceiros relevantes, baseada nestes identificadores.

<div id="about-the-api" />

## Sobre a API

A API de Identificadores Adicionais pode ser utilizada para adicionar os seguintes identificadores de utilizador dos seus sistemas internos ao AppsFlyer Audiences:

* Até 2 endereços de e-mail encriptados
* Número de telefone encriptado
* Número de telefone E164 encriptado

Pode optar por enviar estes identificadores aos seus parceiros do Audiences (sujeito à sua <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política de identificadores de utilizador a nível de conta</Anchor>), permitindo-lhes identificar de forma mais precisa os seus públicos-alvo. Note que nem todos os parceiros de publicidade suportam todos os identificadores.

<div id="when-should-i-use-this-api" />

### Quando devo utilizar esta API?

Esta API foi desenhada para ser utilizada quando pretende fazer o upload de um grande volume de dados de identificadores. Normalmente, isto significa dados recolhidos ao longo do tempo (por exemplo, e-mails encriptados recolhidos de todos os utilizadores de uma app nos últimos 12 meses). Para atualizações individuais e em tempo real de identificadores de dispositivos específicos, <Anchor target="_blank" href="/marketers/pt/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">configure identificadores adicionais</Anchor> no SDK da AppsFlyer ou API S2S-mobile.

<div id="important" />

> 🚧 **Importante!**
>
> **Encriptação:** Todos os valores de identificadores adicionais **devem** ser encriptados com o algoritmo de hash SHA256. Os identificadores que não estiverem encriptados não serão processados.
>
> **Tempo:** Para garantir uma correspondência precisa dos identificadores, a API de Identificadores Adicionais pode ser utilizada logo **no dia seguinte** ao relatório dos principais identificadores através do SDK da AppsFlyer (UTC). Por exemplo, os principais identificadores reportados a 3 de janeiro de 2022 (UTC) podem ser atualizados através desta API a partir de 4 de janeiro de 2022 (UTC).

<div id="actions" />

## Ações

* [Adicionar/modificar identificadores](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [Remover identificadores](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

<div id="authentication" />

## Autenticação

O pedido deve incluir um cabeçalho HTTP contendo o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token da API AppsFlyer V2.0</Anchor> da sua conta. Solicite ao seu administrador de conta para obter este token no painel de controlo da AppsFlyer.

<div id="api-specifications-and-sample-code" />

## Especificações da API e código de exemplo

<div id="addmodify-identifiers-put" />

<Accordion title="Adicionar/modificar identificadores (PUT)">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**URL do pedido de API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parâmetro | Descrição | Obrigatório |
| --- | --- | --- |
| `{id da aplicação}` | ID da aplicação de onde os identificadores foram recolhidos (como aparece no painel da AppsFlyer) | Sim |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**Corpo do pedido API**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },  
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| Parâmetro | Descrição | Obrigatório |
| --- | --- | --- |
| `{key_type}` | O identificador usado como valor único para representar o utilizador em cada linha de dados do pedido.<br /><br />O valor especificado aqui aplica-se a todas as linhas do pedido.<br /><br />Valores possíveis:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_<br />id</li><li>imei</li><li>OAID</li></ul> | Sim |
| `{ação}` | adicionar | Não<br /><br />Valor padrão: adicionar |
| `{valor_chave}` | Valor válido do identificador para o key\_type especificado | Sim |
| \{identificadores\} | Objeto que contém os nomes e valores dos identificadores a adicionar:<ul><li>\{hashed\_emails\}</li><li>\{número\_telefone\_sha256\}</li><li>\{número\_telefone\_e164\_sha256\}</li></ul> | Sim<ul><li>Deve incluir um valor para pelo menos 1 destes 3 identificadores</li></ul> |
| `{hashed_emails}` | Uma matriz com até 2 endereços de e-mail com hash<br /><br />Formato:<ul><li>Minúscula</li><li>Sem espaços em branco</li><li>Hash SHA256</li></ul>Exemplo de valor antes do hash: nome@dominio.com | Não |
| `{número_telefone_sha256}` | Número de telefone (ver nota abaixo)<br /><br />Formato:<ul><li>Sem símbolos, letras ou zeros à esquerda</li><li>Incluir o código do país</li><li>Hash SHA256</li></ul>Exemplo de valor antes do hash:<br /><br />442070313000 | Não |
| `{número_telefone_e164_sha256}` | Número de telefone no formato E164 (ver nota abaixo)<br /><br />Formato<ul><li>Número de telefone E164</li><li>Hash SHA256</li></ul>Exemplo de valor antes do hash:<br /><br />+442070313000 | Não |

<div id="notes" />

> 📘 **Observações**
>
> * Diferentes parceiros de publicidade aceitam diferentes formatos de número de telefone. Portanto, se optar por adicionar um número de telefone, é recomendável enviar ambos os identificadores: *phone\_number\_sha256* e *phone\_number\_e164\_sha256*.
> * `customer_user_id` é o mesmo identificador mencionado em outras partes desta seção como CUID (ID de usuário do cliente). Quando `key_type` for `customer_user_id`, usar o valor de CUID da conta como `key_value`. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política de identificador de usuário do Audiences</Anchor> para saber mais sobre este e outros identificadores compatíveis.

**Restrições**

As seguintes restrições aplicam-se ao pedido **Adicionar/modificar identificadores**:

* Os valores anteriormente existentes (se houver) serão substituídos pelos valores enviados no pedido.
* O objeto `{data}` pode incluir no máximo 4.000 linhas (key\_values) por pedido.

**Exemplo de pedido para adicionar identificadores**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="Remover identificadores (PUT)">

**URL do pedido de API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parâmetro | Descrição | Obrigatório |
| --- | --- | --- |
| `{id da aplicação}` | ID da aplicação de onde os identificadores foram recolhidos (como aparece no painel da AppsFlyer) | Sim |

**Corpo do pedido API**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| Parâmetro | Descrição | Obrigatório |
| --- | --- | --- |
| `{key_type}` | O identificador usado como valor único para representar o utilizador em cada linha de dados do pedido.<br /><br />O valor especificado aqui aplica-se a todas as linhas do pedido.<br /><br />Valores possíveis:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_<br />id</li><li>imei</li><li>OAID</li></ul> | Sim |
| `{valor_chave}` | Valor válido do identificador para o key\_type especificado | Yes |
| `{ação}` | remover | Não<br /><br />Valor padrão: adicionar |
| \{identificadores\} | Uma matriz que contém os nomes dos identificadores cujos valores devem ser removidos:<ul><li>\{hashed\_emails\}</li><li>\{número\_telefone\_sha256\}</li><li>\{número\_telefone\_e164\_sha256\}</li></ul> | Sim<ul><li>Deve incluir pelo menos 1 destes 3 identificadores</li></ul> |

**Restrições**

O objeto `{data}` pode incluir no máximo 4.000 linhas (key\_values) por pedido.

**Exemplo de pedido para remover identificadores**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="Respostas">

| Código | Mensagem | Descrição |
| --- | --- | --- |
| 202 | Aceite para processamento | O pedido será processado na próxima janela disponível. |
| 400 | O corpo do pedido deve conter um key\_type válido | Os seguintes key\_types são suportados:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_<br />id</li><li>imei</li><li>OAID</li></ul> |
| 400 | O pedido deve incluir 'dados' com pelo menos um elemento | A lista de dados não pode estar vazia. |
| 400 | Os 'dados' do pedido não devem ultrapassar o tamanho de 4.000 por pedido único | A lista de dados pode incluir no máximo 4.000 linhas. |
| 400 | Dados do pedido contêm demasiados elementos inválidos | Mais de 10% dos dados a serem modificados não são válidos conforme a especificação. |
| 404 | AppsFlyer - Página não encontrada | Verifique o seguinte:<ul><li>O `{app-id}` especificado no URL do pedido API está correto.</li><li>O cabeçalho HTTP contém o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token correto da API AppsFlyer V2.0</Anchor>. O administrador da sua conta pode obter este token no painel de controlo da AppsFlyer.</li></ul> |

**Exemplos de resposta**

```json
{
"message": "Aceito para processamento",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
Importante!
```

```json
{
"error": "A solicitação deve ter 'data' com pelo menos 1 elemento",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Os 'data' da solicitação não devem exceder o tamanho de 4000 em uma única solicitação",
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Os dados da solicitação têm muitos elementos 'data' inválidos",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="Limites de taxa">

* 5 pedidos por segundo
* 350 pedidos por minuto

</Accordion>

<div data-zendesk-anchors="api-overview=sobre-a-api h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=sobre-a-api when-should-i-use-this-api=quando-devo-utilizar-esta-api h_01HNZP1Y2MJY56TMN6QH4BVRPA=quando-devo-utilizar-esta-api h_01HNZP1Y2MX414NJ49BCVW7KZC=importante methods=a%C3%A7%C3%B5es h_01HNZP1Y2MS5V43XS008GG4S32=a%C3%A7%C3%B5es authentication=autentica%C3%A7%C3%A3o h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=autentica%C3%A7%C3%A3o api-specifications-and-sample-code=especifica%C3%A7%C3%B5es-da-api-e-c%C3%B3digo-de-exemplo h_01HNZP1Y2MR0GCCA1916RMB6GJ=especifica%C3%A7%C3%B5es-da-api-e-c%C3%B3digo-de-exemplo h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=observa%C3%A7%C3%B5es h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
