---
title: "AppsFlyer HTTPS/SSL encryption policy support"
excerpt: "Learn about outgoing SSL cipher suites supported by AppsFlyer."
x-zendesk:
  id: 360001288945
  url: https://support.appsflyer.com/hc/en-us/articles/360001288945-AppsFlyer-HTTPS-SSL-encryption-policy-support
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account security
  section_id: 6551173202065
  position: 7
  owner: Tal Inbar
  owner_email: tal.inbar@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, https, tls, ssl, security, Developers, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2018-07-10T09:34:40Z'
  edited_at: '2024-12-31T09:53:54Z'
---
## Introduction

AppsFlyer APIs use secured protocols.

These protocols support:

* Outgoing messages, where AppsFlyer acts as a client

The AppsFlyer SSL Security profile supports the following SSL protocols:

* TLS V1.2+

AppsFlyer supports different ciphers for outgoing messages, as detailed below.

## Outgoing messages: AppsFlyer as client

For app owners, AppsFlyer acts as a client when sending out push messages.

Supported SSL ciphers for Push API:

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