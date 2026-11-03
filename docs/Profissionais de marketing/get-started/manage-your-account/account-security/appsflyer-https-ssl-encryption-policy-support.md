---
title: Suporte à política de criptografia HTTPS/SSL da AppsFlyer
metadata:
  keywords:
    - Advertisers
    - https
    - tls
    - ssl
    - security
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
  created_at: '2018-07-10T09:34:40Z'
  edited_at: '2026-08-18T00:17:06Z'
  id: 360001288945
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/360001288945
---
> **Resumo:** Saiba mais sobre as cifras SSL de saída compatíveis com a AppsFlyer.

## Introdução

As APIs da AppsFlyer usam protocolos seguros.

Estes protocolos oferecem suporte a:

* Mensagens de saída, em que a AppsFlyer atua como cliente

O perfil de segurança SSL da AppsFlyer oferece suporte aos seguintes protocolos SSL:

* TLS V1.2+

A AppsFlyer oferece suporte a diferentes cifras para mensagens de saída, conforme detalhado abaixo.

## Mensagens de saída: AppsFlyer como cliente

Para os proprietários de aplicativos, a AppsFlyer atua como cliente ao enviar mensagens push.

Cifras SSL compatíveis com a Push API:

| TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_CBC\_SHA |
| --- |
| TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA |
| TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA |
| TLS\_ECDH\_ECDSA\_WITH\_AES\_128\_CBC\_SHA |
| TLS\_ECDH\_RSA\_WITH\_AES\_128\_CBC\_SHA |
| TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256 |
| TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256 |
| TLS\_RSA\_WITH\_AES\_128\_GCM\_SHA256 |
| TLS\_ECDH\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256 |
| TLS\_ECDH\_RSA\_WITH\_AES\_128\_GCM\_SHA256 |
| TLS\_ECDHE\_ECDSA\_WITH\_3DES\_EDE\_CBC\_SHA |
| TLS\_ECDHE\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA |
| SSL\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA |
| TLS\_ECDH\_ECDSA\_WITH\_3DES\_EDE\_CBC\_SHA |
| TLS\_ECDH\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA |
| TLS\_EMPTY\_RENEGOTIATION\_INFO\_SCSV |

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HM679ZCX155SEV7GP0XEWR5B=introdu%C3%A7%C3%A3o outgoing-messages-appsflyer-as-client=mensagens-de-sa%C3%ADda-appsflyer-como-cliente h_01HM679ZCXBFAAJ8BTQBF1D810=mensagens-de-sa%C3%ADda-appsflyer-como-cliente" />
