---
title: AppsFlyerのHTTPS／SSL暗号化ポリシーと対応範囲
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
  edited_at: '2026-10-28T09:13:54Z'
  id: 360001288945
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/360001288945
---
> **概要：** AppsFlyerからの送信通信でサポートするSSL暗号スイートについて説明します。

## はじめに

AppsFlyerのAPIは、安全な通信プロトコルを使用しています。

これらのプロトコルは、次の通信に対応しています。

* AppsFlyerがクライアントとして行う、外部へのメッセージ送信

AppsFlyerのSSLセキュリティプロファイルは、次のSSLプロトコルに対応しています。

* TLS V1.2以降

AppsFlyerからの送信通信では、以下の暗号方式に対応しています。

## 送信メッセージ｜AppsFlyerがクライアントとなる場合

アプリ所有者にPushメッセージを送信する際、AppsFlyerはクライアントとして動作します。

Push APIでサポートするSSL暗号方式：

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

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HM679ZCX155SEV7GP0XEWR5B=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB outgoing-messages-appsflyer-as-client=%E9%80%81%E4%BF%A1%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8appsflyer%E3%81%8C%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E3%81%A8%E3%81%AA%E3%82%8B%E5%A0%B4%E5%90%88 h_01HM679ZCXBFAAJ8BTQBF1D810=%E9%80%81%E4%BF%A1%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8appsflyer%E3%81%8C%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E3%81%A8%E3%81%AA%E3%82%8B%E5%A0%B4%E5%90%88" />
