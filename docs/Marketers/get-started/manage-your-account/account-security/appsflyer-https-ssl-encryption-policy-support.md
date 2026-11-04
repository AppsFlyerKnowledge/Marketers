---
title: Soporte de la política de cifrado HTTPS/SSL de AppsFlyer
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
  edited_at: '2026-08-12T12:04:11Z'
  id: 360001288945
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/360001288945
---
> **Resumen:** Descubre qué suites de cifrado SSL salientes admite AppsFlyer.

<div id="introduction" />

## Introducción

Las API de AppsFlyer usan protocolos seguros.

Estos protocolos ofrecen soporte para:

* Mensajes salientes, en los que AppsFlyer actúa como cliente

El perfil de seguridad SSL de AppsFlyer admite los siguientes protocolos SSL:

* TLS v1.2+

AppsFlyer admite distintos cifrados para los mensajes salientes, como se detalla a continuación.

<div id="outgoing-messages-appsflyer-as-client" />

## Mensajes salientes: AppsFlyer como cliente

Para los propietarios de aplicaciones, AppsFlyer actúa como cliente al enviar mensajes push.

Cifrados SSL admitidos para la API Push:

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

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HM679ZCX155SEV7GP0XEWR5B=introducci%C3%B3n outgoing-messages-appsflyer-as-client=mensajes-salientes-appsflyer-como-cliente h_01HM679ZCXBFAAJ8BTQBF1D810=mensajes-salientes-appsflyer-como-cliente" />
