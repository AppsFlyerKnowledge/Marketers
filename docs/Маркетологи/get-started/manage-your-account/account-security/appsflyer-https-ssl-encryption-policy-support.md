---
title: Поддержка политики шифрования HTTPS/SSL в AppsFlyer
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
  edited_at: '2026-10-19T14:13:05Z'
  id: 360001288945
  locale: ru
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ru/articles/360001288945
---
> **Краткий обзор:** Узнайте о наборах шифров SSL для исходящих соединений, поддерживаемых AppsFlyer.

## Введение

API AppsFlyer используют защищенные протоколы.

Эти протоколы обеспечивают:

* Исходящие сообщения, в которых AppsFlyer выступает в роли клиента

Профиль SSL Security AppsFlyer поддерживает следующие протоколы SSL:

* TLS V1.2+

AppsFlyer поддерживает различные шифры для исходящих сообщений, как указано ниже.

## Исходящие сообщения: AppsFlyer в роли клиента

Для владельцев приложений AppsFlyer выступает в роли клиента при отправке push-сообщений.

Поддерживаемые шифры SSL для Push API:

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

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01HM679ZCX155SEV7GP0XEWR5B=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 outgoing-messages-appsflyer-as-client=%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D0%B5-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-appsflyer-%D0%B2-%D1%80%D0%BE%D0%BB%D0%B8-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 h_01HM679ZCXBFAAJ8BTQBF1D810=%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D0%B5-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-appsflyer-%D0%B2-%D1%80%D0%BE%D0%BB%D0%B8-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0" />
