---
title: Integração do Segment
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
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
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-08-18T00:12:20Z'
  id: 210041606
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/210041606
---
> **Visão geral:** Envie seus dados de analytics do Segment para a AppsFlyer.

<div id="introduction" />

## Introdução

O Segment facilita o envio dos seus dados para a AppsFlyer. Depois de registrar seus dados por meio das bibliotecas de código aberto do Segment, os dados são traduzidos e encaminhados para a AppsFlyer no formato apropriado. A AppsFlyer ajuda os profissionais de marketing a identificar a segmentação, otimizar os gastos com anúncios e aumentar o ROI.

<div id="integrating-segment-with-appsflyer" />

## Integração do Segment com a AppsFlyer

Siga <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">este guia do Segment</Anchor> para saber como integrar o Segment à AppsFlyer.

<div id="faqs" />

## Perguntas frequentes

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="Como posso integrar o Segment à AppsFlyer?">

Para integrar o Segment à AppsFlyer, siga estas etapas:

* <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Configure o painel do Segment</Anchor> para se conectar à AppsFlyer
* Implemente [o Segment Wrapper SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work) em seu aplicativo:
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">iOS nativo</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">Android nativo</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="Quais SDKs preciso adicionar ao meu aplicativo?">

Você só precisa adicionar o Segment SDK wrapper. Quando você adiciona a dependência Segment SDK wrapper, o processo de criação do aplicativo adiciona automaticamente o Segment SDK e o AppsFlyer SDK ao seu aplicativo.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="Como funciona o wrapper do SDK?">

O Segment SDK wrapper conecta o Segment SDK e o AppsFlyer SDK.

Quando você usa o Segment SDK wrapper para chamar os métodos do Segment para registrar instalações e eventos no aplicativo, o wrapper do SDK chama os métodos do Segment e da AppsFlyer.

Isso economiza tempo e esforço e requer menos codificação.

<div id="warning" />

> ❗️ **Aviso**
>
> Aviso- **NÃO USE** métodos de ambos: Segment SDK wrapper e AppsFlyer SDK. Isso pode levar a erros e discrepâncias de dados.
>
> **Use apenas métodos do Segment SDK wrapper.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Há alguma diferença de funcionalidade entre o Segment SDK wrapper e o AppsFlyer SDK?">

Não, não há diferença na funcionalidade. Todas as funções do AppsFlyer SDK estão disponíveis no Segment SDK wrapper.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="Não vejo dados de eventos in-app no painel da AppsFlyer">

* Siga as instruções para implementar o método de rastreamento no Segment SDK wrapper:
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">com o Android</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">/docs/ctv-pc-and-console-platform-attribution-concepts</Anchor>
* Certifique-se de <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">especificar sua chave de desenvolvimento</Anchor> ao integrar a AppsFlyer no painel do Segment.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Os dados de instalação e eventos in-app no Segment e na AppsFlyer não correspondem">

Certifique-se de que usar apenas o Segment SDK wrapper. NĀO combine o Segment SDK com o AppsFlyer SDK. Veja [aqui](/docs/segment-integration#how-does-the-sdk-wrapper-work) mais informações.

[O FAQ acima](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) também especifica os motivos pelos quais os dados podem não estar alinhados entre o Segment e a AppsFlyer.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="Estou recebendo um erro de validação ao testar eventos no Segment">

Quando você testa eventos usando o comando ***Event Tester*** na página ***Destino***, você pode receber um erro: ***Erro de validação ID do dispositivo da AppsFlyer ('integrações. AppsFlyer.appsFlyerId') é necessário para enviar eventos server to server***.

Esse erro não significa que há um problema com a integração entre o Segment e a AppsFlyer. O Event Tester permite que você teste o server-to-server do Segment para a AppsFlyer. Qualquer evento enviado usando server-to-server requer o AppsFlyerID, e é por isso que o event tester gera o erro.

No entanto, isso só é relevante para server-to-server. Quando você usa o Segment SDK API para registrar eventos, os eventos são enviados do SDK para o Segment e a AppsFlyer. Para a chamada de API da AppsFlyer, o ID de dispositivo da AppsFlyer está incluído.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="Estou usando uma ferramenta de analytics de terceiros. Devo integrá-lo à AppsFlyer e ao Segment?">

Não, você só deve usar o painel do Segment para habilitar as ferramentas de analytics de terceiros.

</Accordion>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01JZMD855TA62KQ4AWJ5F6WSDP=introdu%C3%A7%C3%A3o integrating-segment-with-appsflyer=integra%C3%A7%C3%A3o-do-segment-com-a-appsflyer h_01JZMD855TNEYZG1MDZY7FWV8S=integra%C3%A7%C3%A3o-do-segment-com-a-appsflyer faqs=perguntas-frequentes h_01JZMD855TAEBDPAMEAEH66F27=perguntas-frequentes h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=aviso h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />
