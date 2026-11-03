---
title: Obter dados de conversão usando o SDK da AppsFlyer - Visão geral
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-08-18T00:13:34Z'
  id: 4410481069969
  locale: pt
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/pt/articles/4410481069969
---
> **Visão geral:** Use os dados de conversão para identificar vários cenários de conversão, personalizar a experiência do usuário e muito mais.

Usar os dados de conversão para:

* Enviar usuários para atividades específicas
* Fornecer conteúdo personalizado

> 🚧 **Importante!**
>
> **Limitações dos dados de conversão do SDK**
>
> Ao usar o callback `onConversionDataSuccess` do SDK da AppsFlyer, observe que ele pode ser acionado antes da conclusão do processo de atribuição. Como resultado, os dados retornados pelo SDK podem não corresponder aos dados nos relatórios ou nas APIs da AppsFlyer.
>
> **Recomendação:**
> Não use o método Get Conversion Data (GCD) para coletar ou validar dados de atribuição.
> Para obter resultados de atribuição precisos e completos, use os dashboards, relatórios ou APIs da AppsFlyer.

## Get conversion data

O SDK da AppsFlyer retorna dados de conversão usando o seguinte:

* * `onConversionDataSuccess`: Aquisição de usuário (UA) e conversões de reatribuição
    * Android: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * iOS: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity: loadConversionData
  * `onAppOpenAttribution`: Para conversões de reengajamento

<div data-zendesk-anchors="h_01K9KSQQDVDEACFRXS0M4JNW9M=importante h_01HTZ6M409RPZAQM66R0H5HA16=get-conversion-data" />
