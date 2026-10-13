---
title: "AppsFlyer HTTPS/SSL encryption policy support"
excerpt: "Learn about the outgoing SSL cipher suites and TLS protocols supported by AppsFlyer for secure API communications."
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
At a glance: Learn about outgoing SSL cipher suites supported by AppsFlyer.

## Introduction

AppsFlyer APIs use secured protocols.

These protocols support:

- Outgoing messages, where AppsFlyer acts as a client

The AppsFlyer SSL Security profile supports the following SSL protocols:

- TLS V1.2+

AppsFlyer supports different ciphers for outgoing messages, as detailed below.

## Outgoing messages: AppsFlyer as client

For app owners, AppsFlyer acts as a client when sending out push messages.

Supported SSL ciphers for Push API:

| Supported SSL Ciphers |
| --- |
| TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA |
| TLS_RSA_WITH_AES_128_CBC_SHA |
| TLS_ECDH_ECDSA_WITH_AES_128_CBC_SHA |
| TLS_ECDH_RSA_WITH_AES_128_CBC_SHA |
| TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256 |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 |
| TLS_RSA_WITH_AES_128_GCM_SHA256 |
| TLS_ECDH_ECDSA_WITH_AES_128_GCM_SHA256 |
| TLS_ECDH_RSA_WITH_AES_128_GCM_SHA256 |
| TLS_ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA |
| TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA |
| SSL_RSA_WITH_3DES_EDE_CBC_SHA |
| TLS_ECDH_ECDSA_WITH_3DES_EDE_CBC_SHA |
| TLS_ECDH_RSA_WITH_3DES_EDE_CBC_SHA |
| TLS_EMPTY_RENEGOTIATION_INFO_SCSV |