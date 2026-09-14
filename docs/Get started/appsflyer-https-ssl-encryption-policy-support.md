---
title: "AppsFlyer HTTPS/SSL encryption policy support"
excerpt: "Learn about the outgoing SSL cipher suites and TLS protocols supported by AppsFlyer for secure API communications."
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