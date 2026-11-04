---
title: Integração adicional com SDK
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-08-19T00:15:00Z'
  id: 4408735106193
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/4408735106193
---
> **At a glance:** **Resumo:** considere as funcionalidades adicionais do SDK que estão disponíveis e trabalhe com seu desenvolvedor para implementar APIs, como métrica de desinstalação, atribuição de convite do usuário, notificações por push e configurações de privacidade.

<div id="additional-attribution-methods" />

## Métodos de atribuição adicionais

Considere esses métodos de atribuição adicionais se você planeja mensurar TV, desinstalações ou aplicativos pré-instalados.

**Todas as plataformas**

<Accordion title="Atribuição CTV">

Atribua <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">usuários mobile a anúncios de CTV</Anchor> exibidos em locais e horários específicos.

</Accordion>

<Accordion title="Mensurar desinstalações">

Mensure as taxas de desinstalação de usuários provenientes de diferentes fontes. A métrica de desinstalação pode ajudá-lo a analisar e otimizar suas campanhas de acordo com essas taxas de KPI significativas.

<Anchor target="_blank" href="/marketers/pt/docs/measure-uninstalls">Saiba como configurar a métrica de desinstalação</Anchor>.

</Accordion>

**Exclusivo para Android**

<Accordion title="Aplicativos pré-instalados">

Em <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-factory-preinstall-using-manifest-android">campanhas de pré-instalação</Anchor>, os proprietários de aplicativos contratam fabricantes de dispositivos (OEMs) para pré-instalar seus aplicativos.

Com a AppsFlyer, você pode atribuir facilmente instalações de aplicativos pré-instalados. Quando os usuários iniciam seu aplicativo pela primeira vez, a AppsFlyer atribui a instalação ao parceiro de pré-carregamento como uma fonte de mídia.

</Accordion>

<div id="sessions" />

## Sessões

Avalie o engajamento do usuário com seu aplicativo contando o número de sessões do usuário durante um determinado período.

**Todas as plataformas**

<Accordion title="Personalizar tempo entre sessões">

Por padrão, devem passar pelo menos 5 segundos entre duas inicializações de aplicativos para contar como duas sessões separadas. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions#session-reporting-by-the-app-sdk">sessões de contagem</Anchor>.

Definir um **valor alto para o tempo personalizado entre as inicializações pode prejudicar as APIs** que dependem de dados da sessão, como deep links.

</Accordion>

**Exclusivo para Android**

<Accordion title="Sessões em background para aplicativos utilitários">

Você pode <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions#session-reporting-by-the-app-sdk">reportar manualmente as sessões do usuário</Anchor>. Isso pode ser útil para aplicativos utilitários executados em segundo plano.

</Accordion>

<div id="owned-media" />

## Mídias próprias

Use o OneLink para atribuir suas fontes de mídia próprias, como sites, mídias sociais e convites de usuários.

**Todas as plataformas**

<Accordion title="Corrija URLs encurtadas de links diretos.">

Alguns serviços de terceiros, como <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">provedores de serviços de e-mail</Anchor>, envolvem links em e-mails com seus próprios domínios de gravação de links. Alguns até permitem que você defina seus próprios domínios de gravação de links. Se o OneLink estiver agrupado nesses domínios, poderá limitar sua funcionalidade.

Para superar esse problema, o desenvolvedor precisa configurar o aplicativo usando essas APIs:

<Tabs>
<Tab title="Android nativo">

Consulte [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) na referência do Android SDK

</Tab>

<Tab title="iOS nativo">

Consulte [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) na referência do iOS SDK

</Tab>

<Tab title="Unity">

Consulte [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) na referência do Unity SDK

</Tab>
</Tabs>

</Accordion>

<Accordion title="Gravar notificação push">

A AppsFlyer é compatível com a métrica de campanhas de notificação push de todos os fornecedores, incluindo o Google Cloud Messaging e os serviços de notificação push da Apple.

<Anchor target="_blank" href="/marketers/pt/docs/measuring-push-notification-re-engagement-campaigns">Saiba mais sobre a métrica de notificações push</Anchor>.

</Accordion>

<Accordion title="Atribuição de convites de usuário">

Permitir que os usuários existentes convidem seus amigos e contatos como novos usuários para seu aplicativo pode ser um fator de crescimento importante para seu aplicativo. Com a AppsFlyer, você pode atribuir e registrar instalações originadas de convites do usuário em seu aplicativo.

<Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">Saiba mais sobre a atribuição de convite do usuário</Anchor>.

</Accordion>

<Accordion title="Atribuição de promoção cruzada">

Aplicativos de promoções cruzadas podem ser um importante fator de crescimento para impulsionar novas instalações para seus aplicativos. A AppsFlyer permite que você atribua e registre instalações originadas de uma promoção cruzada do aplicativo que o usuário possui atualmente para outro de seus aplicativos.

<Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-marketers">Saiba mais sobre a atribuição de promoção cruzada</Anchor>.

</Accordion>

<Accordion title="Atribuir sessões de aplicativo iniciadas a partir de sites próprios (domínios)">

Os proprietários de aplicativos que usam links de aplicativos ou links universais para deep links (sem o OneLink) podem configurar o SDK para atribuir sessões iniciadas por meio do domínio associado ao aplicativo (<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>).

Por exemplo:

* Um usuário pesquisa no Google e clica em seu domínio, **www.exemplo.com**.
* Se o usuário não tiver o aplicativo instalado, ele será direcionado para o site (www.example.com).
* Se o usuário tiver o aplicativo instalado no seu dispositivo, haverá um link direto para o aplicativo associado com www.exemplo.com. A sessão é atribuída à fonte de mídia (parâmetro `pid`) configurada no SDK.

A documentação do desenvolvedor está disponível da seguinte forma:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referência do SDK do Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referência do SDK para iOS</Anchor>

**Dica!** <Anchor target="_blank" href="/marketers/pt/docs/convert-your-mobile-web-visitors-to-app-users#soluções-de-atribuição">O OneLink Smart Script</Anchor> pode ajudar os proprietários de aplicativos a converter visitantes do site em usuários do aplicativo.

</Accordion>

<div id="user-privacy" />

## Privacidade do usuário

Analise as regulamentações como GDPR e CCPA e seus requisitos de negócios e considere quais políticas de aceitação e exclusão implementar.

**Todas as plataformas**

<Accordion title="Política de optar por não participar">

Em alguns casos, talvez seja necessário instruir seu desenvolvedor a definir o SDK da AppsFlyer para interromper ou limitar a coleta de dados (por exemplo, para cumprir os regulamentos do GDPR e do CCPA). Há diferentes métodos para proteger a privacidade dos usuários no SDK. Para mais informações sobre esses métodos, consulte os <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">métodos de proteção à privacidade no artigo do SDK</Anchor>.

</Accordion>

<Accordion title="Excluir parceiros da obtenção de dados">

Em alguns casos, os anunciantes desejam parar de compartilhar dados no nível do usuário com ad networks/parceiros para determinados usuários. Os motivos variam:

* Políticas de privacidade como CCPA ou GDPR
* Mecanismos para o usuário optar por não participar
* Competição com alguns parceiros (ad networks, terceiros)

O compartilhamento de dados com parceiros é controlado através do método `setSharingFilterForPartners`:

<Tabs>
<Tab title="Iniciando o SDK no Android native">

Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> na referência do Android SDK

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`resolveDeepLinkURLs`</Anchor> na referência do iOS SDK

</Tab>

<Tab title="Unity/React Native">

Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> na referência do Unity SDK

Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> na referência do React Native SDK

</Tab>
</Tabs>

</Accordion>

<Accordion title="Enviar consentimento para compliance com o DMA">

Como parte da legislação do [Digital Marketer Act](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en) (DMA) da UE, grandes empresas de tecnologia devem obter o consentimento dos usuários europeus antes de usar dados pessoais de serviços de terceiros para fins de publicidade.

Para cumprir com a legislação, o Google exige que os clientes da AppsFlyer incluam campos de consentimento específicos ao enviar eventos originados de usuários da UE para o Google. O SDK da AppsFlyer (Android - v6.13.0+, iOS - v6.13.1+) envia os dados de consentimento necessários a cada evento, seguindo as diretrizes do Google.

O SDK oferece dois métodos alternativos para coletar dados de consentimento:

* **Através de uma plataforma de gestão de consentimento (CMP):** se o aplicativo usar uma CMP que esteja em compliance com o protocolo [Transparency and Consent Framework (TCF) v2.2](https://iabeurope.eu/tcf-supporting-resources/), o SDK poderá recuperar automaticamente os dados de consentimento.

  OU
* **Através de uma SDK API dedicada**: os desenvolvedores podem enviar os dados de consentimento necessários diretamente para o SDK usando uma API específica, projetada para esse fim.

Para implementar a coleta de dados de consentimento do usuário para compliance com o DMA, consulte nossos guias no Dev Hub:

<Tabs>
<Tab title="Android nativo">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance">Enviar consentimento para compliance com o DMA</Anchor>

</Tab>

<Tab title="iOS nativo">

[Enviar consentimento para compliance com o DMA](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

</Accordion>

**Exclusivo para iOS**

<Accordion title="SDK de modo estrito">

Use o SDK no modo estrito para remover completamente a funcionalidade de coleta IDFA e as dependências do framework do AdSupport (por exemplo, ao desenvolver <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">aplicativos para crianças</Anchor>).

Se você comercializa aplicativos para crianças, seu desenvolvedor precisa instalar o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK de modo estrito</Anchor> em vez do SDK normal. **Atenção:** o IDFV permanece disponível.

</Accordion>

<Accordion title="Desativar estruturas de anúncios">

Para desativar AdSupport e iAd frameworks, o SDK fornece os seguintes configuradores:

<Tabs>
<Tab title="Android nativo iOS nativo Unity React nativo">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) para opt-out de atribuições do Apple Search Ads.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) para não coletar o `advertisingIdentifier` da Apple

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) para opt-out de atribuições do Apple Search Ads.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) para não coletar o `advertisingIdentifier` da Apple

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-adicionais 01H8W01DRHQHJKNMJA24PR5S2T=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-adicionais sessions=sess%C3%B5es 01H8W01DRHD3EZBQT0ZKDMM1QB=sess%C3%B5es owned-media=m%C3%ADdias-pr%C3%B3prias 01H8W01DRHV8H3QFJX5QKABK5E=m%C3%ADdias-pr%C3%B3prias user-privacy=privacidade-do-usu%C3%A1rio 01H8W01DRHJFB71DVJ64QWJME4=privacidade-do-usu%C3%A1rio" />
