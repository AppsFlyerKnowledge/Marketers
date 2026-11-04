---
title: Aplicar a solução da Lei de Proteção de Informações Pessoais (PIPL) da China
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-05-10T08:59:00Z'
  edited_at: '2026-08-18T00:29:22Z'
  id: 6031419375377
  locale: pt
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/pt/articles/6031419375377
---
> **Em resumo:** Aumente a flexibilidade ao mensurar com a AppsFlyer e manter a conformidade com a PIPL.

<div id="background" />

## CONTEXTO

No fim de 2021, a China aprovou a Lei de Proteção de Informações Pessoais (PIPL), que regula a coleta, o uso e a transferência de dados pessoais de usuários. Para oferecer aos clientes mais flexibilidade ao usar a AppsFlyer e dar suporte à compliance com a PIPL, siga as instruções passo a passo descritas neste artigo.  
A solução PIPL da AppsFlyer se baseia em 3 princípios:

* Impeça que o SDK colete IDs do dispositivo.
* Mascarar e aplicar hashing a IPs de eventos do SDK e S2S, além de cliques e impressões.
* Habilite a auditoria de todos os eventos do aplicativo em um servidor de retransmissão na China.

<div id="apply-pipl-solution-in-appsflyer" />

## Aplicar a solução PIPL na AppsFlyer

A seção a seguir descreve as ações que você precisa realizar para aplicar a solução PIPL da AppsFlyer.

**Para aplicar a solução PIPL:**

1. Interrompa a coleta de IDs do dispositivo pelo SDK. Certifique-se de não enviar à AppsFlyer os IDs de dispositivo, tanto para engajamentos quanto para eventos.
   * Para Android:
     * Defina `setDisableAdvertisingIdentifiers` como true
     * Defina <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor> como false
     * Defina <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor> como false
   * Para iOS:
     * Defina <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier">`disableAdvertisingIdentifier`</Anchor> como true
     * Defina <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection">`disableIDFVCollection`</Anchor> como true

   Observe que configurar esses métodos afeta a coleta de identificadores não só na China. Para desativar os identificadores especificamente para o mercado chinês, você precisa implementar uma lógica personalizada.
2. Mascare e aplique hash a cliques e impressões usando domínios chineses dedicados para transmitir esses eventos à AppsFlyer.
   * Use os seguintes domínios chineses para links do OneLink e links de atribuição:
     * Para cliques em uma única plataforma - **hclicks.aflink.com**, não use assinatura de clique. Certifique-se de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add">excluir o aplicativo da assinatura de clique</Anchor>.
     * Para impressões em uma única plataforma - **himpressions.aflink.com**
     * Para cliques do OneLink - **`{subdomain}`.onelnk.com**
   * Envie ao seu CSM uma lista de IDs de aplicativo relevantes e subdomínios do OneLink.
   * Se você estiver usando banners inteligentes:
     * <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">Envie à AppsFlyer a chave do site.</Anchor>
     * Use apenas `{subdomain}`.onelnk.com.
     * Observação! Como a PIPL exige mascaramento e hashing de endereços IP, os banners inteligentes baseados em regras de geolocalização não funcionarão como esperado.
3. Mascare e aplique hashing a eventos de SDK e S2S e transfira-os por um servidor de retransmissão na China
   * **Eventos de SDK:**  
     Defina o domínio dos eventos de SDK como **hevents.appsflyer-cn.com**. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Instruções para Android</Anchor>. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost">Instruções iOS</Anchor>.  
     Usar esse domínio garante que o IP de todos os eventos de SDK seja mascarado e sofra Hashing.
   * **Eventos S2S:**  
     Para eventos S2S, use o domínio `api2.hevents.appsflyer-cn.com` para mascarar e aplicar hashing a eventos de IP da seguinte forma:
     * O IP deve ser convertido em binário e, em seguida, os últimos 2 dígitos devem ser mascarados.
     * O IP binário mascarado deve ser convertido em texto e, em seguida, sofrer Hashing pelo algoritmo sha256.

<div id="solution-limitations" />

## Limitações da solução

Esta seção descreve determinadas limitações impostas pela solução PIPL.

* A solução S2S da API do OneLink para criação de links curtos não é compatível.
* Todos os IDs do dispositivo, para todos os engajamentos, devem sofrer Hashing.

<div data-zendesk-anchors="background=contexto h_01HQ5Y1W7M46BBJGEZZ5VEYW3K=contexto apply-pipl-solution-in-appsflyer=aplicar-a-solu%C3%A7%C3%A3o-pipl-na-appsflyer h_01HQ5Y1W7MRYYGJWJNWY7ZSY9S=aplicar-a-solu%C3%A7%C3%A3o-pipl-na-appsflyer solution-limitations=limita%C3%A7%C3%B5es-da-solu%C3%A7%C3%A3o h_01HQ5Y1W7M39XRY607H4G7X0X4=limita%C3%A7%C3%B5es-da-solu%C3%A7%C3%A3o" />
