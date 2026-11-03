---
title: Usando Firebase e Google Tag Manager com a AppsFlyer—Visão geral
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
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
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2026-08-18T00:12:44Z'
  id: 210353513
  locale: pt
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/pt/articles/210353513
---
> **Visão geral:** como enviar eventos relatados pelo SDK do Firebase para a AppsFlyer usando o Google Tag Manager.

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

A integração da AppsFlyer com o Google Tag Manager (GTM) e o Firebase permite ao desenvolvedor enviar eventos in-app para o Firebase usando o Firebase SDK, e ter os eventos enviados para a AppsFlyer através do SDK usando o Google Tag Manager. Isto evita a necessidade de enviar o mesmo evento duas vezes.

Os eventos enviados usando GTM são modelados nos eventos in-app da AppsFlyer. O nome do evento, os parâmetros e a estrutura são os mesmos. Se você já tem GTM em seu aplicativo, usá-lo para enviar eventos para a AppsFlyer é simples.

Use as etapas e instruções deste guia para enviar eventos. 

### Considerações

* **Fonte de eventos em dados brutos:** os eventos gerados pela GTM têm a fonte definida para S2S em relatórios de dados brutos. Isto pode levar a alguma confusão, já que os eventos são relatados pelo SDK.
* **Atualização do valor de conversão do SKAdNetwork**: eventos gerados pelo GTM e reportados ao SDK conforme descrito neste guia fazem com que o SDK atualize o valor de conversão de forma similar aos eventos regulares do SDK. Você só precisa habilitar e configurar suas configurações de métrica do <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAdNetwork</Anchor>.

> 📘 **Observação**
>
> * Atualmente, a integração do Google Tag Manager não suporta o envio dos seguintes parâmetros para a AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">ID de usuário cliente</Anchor>
>   * `att`
>   * `os`Observe que:
>   * Ao enviar postbacks de eventos no sistema SRN, o parâmetro `att` é necessário.
>   * Ao enviar postbacks de eventos para o Meta ads, os parâmetros `att` e `os` são necessários.

### Pré-requisitos

Antes de começar a enviar eventos para a AppsFlyer usando GTM, você precisa implementar o GTM SDK em seu aplicativo. Você precisa:

1. Ter uma conta [GTM.](https://www.google.com/analytics/tag-manager/)
2. Ter a configuração de integração GTM + Firebase para seu aplicativo (instruções para [Android](https://developers.google.com/tag-manager/android) e [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">Integrar o SDK da AppsFlyer</Anchor> se ainda não fez isso.

Depois de tudo feito, prossiga para <Anchor target="_blank" href="/marketers/pt/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">a configuração do GTM</Anchor>.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Migrar do Firebase Dynamic Links para a AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=considera%C3%A7%C3%B5es h_01HE7SKSCBH47YYFTKBWY3JVSV=considera%C3%A7%C3%B5es h_01HE7SKSCBBTTWATRZ87BYRW6G=observa%C3%A7%C3%A3o prerequisites=pr%C3%A9-requisitos h_01HE7SKSCB9QHA4WEERVSWMF0P=pr%C3%A9-requisitos h_01HE7SQQG2VJW9179Q77PTZFPH=veja-tamb%C3%A9m" />
