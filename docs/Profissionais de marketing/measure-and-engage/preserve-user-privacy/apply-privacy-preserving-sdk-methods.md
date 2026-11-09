---
title: Métodos de proteção da privacidade no SDK
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
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
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-08-19T00:32:59Z'
  id: 360001422989
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/360001422989
---
> **At a glance:** **Visão geral:** proteja a privacidade dos seus usuários usando um mais métodos disponíveis com o SDK da AppsFlyer.

> 📘 **Note**
>
> **Importante!**
>
> As informações apresentadas neste artigo destinam-se exclusivamente a fornecer informações sobre os métodos disponíveis aos desenvolvedores de aplicativos para controlar o compartilhamento de dados do usuário com proprietários de aplicativos, ad networks e redes sociais. **Este artigo não inclui nem constitui orientação sobre conformidade com regulamentações de privacidade, como COPPA ou GDPR, ou quaisquer regulamentações específicas de proteção de privacidade.**

O SDK da AppsFlyer oferece diversos métodos para proteger a privacidade e o controle de dados do usuário. Nesse artigo, vamos falar sobre cada um deles e avaliar como eles afetam os dados do usuário, além de explicar como esses métodos podem ser usados para proteger a privacidade dos clientes sem impedir a atribuição.

Depois de definir as opções que você deseja usar, compartilhe as informações de implementação necessárias em nosso Dev Hub com seus desenvolvedores.

Vamos falar sobre cada método.

<div id="use-start-and-stop-methods" />

## Use os métodos start e stop

O SDK envia instalações e eventos in-app para a AppsFlyer somente depois que o método `start` é chamado. Qualquer evento que ocorra antes do chamado `start` não será relatado pelo SDK. Da mesma forma, se o chamado `start` for revertido usando o método `stop`, nenhum evento será enviado.

<div id="impact-on-attribution" />

### Como isso afeta a atribuição

A atribuição **não** ocorre quando:

* o método `start` não é chamado.
* o método `stop` é chamado para reverter o start anterior.

<div id="common-use-cases" />

### Casos comuns

| Caso de uso | Descrição |
| --- | --- |
| Opt-in ou opt-out na hora da abertura do app | Chame `start` depois que o usuário permitir o compartilhamento de dados na primeira abertura do app.  <br />Caso contrário, você não deve chamar   <br />`start`. |
| Sessão com opt-out | Em cada sessão do aplicativo, peça o consentimento do usuário e depois faça a chamada `start` quando adequado. |
| Opt-out único (quando o usuário dá opt-in e depois decide pelo opt-out). | Faça a chamada `stop` para impedir que o SDK continue enviando eventos. |

<div id="developer-reference" />

### Documentação para desenvolvedores

Para consultar referências e documentação sobre como usar os métodos start e stop, acesse:

<Tabs>
<Tab title="Android iOS">

[Use o método start para compartilhar apenas o evento de instalação](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="Exemplo">

[Use o método start para compartilhar apenas o evento de instalação](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

<div id="prevent-sharing-data-with-networks" />

## Como impedir o compartilhamento de dados com ad networks

No momento da integração com uma ad network ou com uma rede de autorrelato (SRN), você pode optar por compartilhar informações no nível do usuário com o parceiro em questão. No SDK, você pode fazer uma filtragem ainda mais personalizada, optando pelo compartilhamento com todos ou com alguns parceiros, **de acordo com as preferências do usuário final**, usando o método `setSharingFilterForPartners`.

Ao usar esse método, a AppsFlyer desativará completamente o compartilhamento de dados com um parceiro, seja através de postbacks, APIs, relatórios de dados brutos, etc.

<div id="impact-on-attribution-1" />

### Como isso afeta a atribuição

* Instalações de **ad networks removidas do compartilhamento** **(não SRNs)** são atribuídas na AppsFlyer. As ad networks não serão notificadas.
* Instalações de **SRNs** **removidas do compartilhamento** não são atribuídas, e os dados não são compartilhados com seus parceiros integrados. Isso não se aplica a **SRNs avançadas**, em que a Atribuição ainda é possível; no entanto, instalações, reengajamentos e eventos in-app não serão compartilhados de volta devido ao filtro de compartilhamento.

  > 📘 **Note**
  >
  > **Importante!**
  >
  > A AppsFlyer não atribui dados de engajamento para nenhuma SRN que não recebe seus dados.


<div id="developer-reference-1" />

### Documentação para desenvolvedores

Para consultar referências e documentação sobre como impedir o compartilhamento de dados com terceiros, acesse:

<Tabs>
<Tab title="Android / iOS">

[Impedir o compartilhamento de dados com terceiros](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

[Impedir o compartilhamento de dados com terceiros](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

<div id="anonymize-user-information" />

## Como anonimizar informações do usuário

Você pode configurar o SDK para solicitar a remoção de todas as informações pessoais dos usuários usando o método `anonymizeUser`. Nesse caso, o SDK envia eventos in-app e de instalação para a AppsFlyer, nos quais todas as informações pessoais são deletadas ou anonimizadas:

* **Deletado:** identificadores pessoais (GAID, IDFA, IDFV e CUID).
* **Anonimizado:** AppsFlyer ID e endereço IP

A imagem abaixo mostra um exemplo de dados brutos que foram deletados e/ou anonimizados:

<Image align="center" alt="Exemplo de linha de dados brutos mostrando campos excluídos e com hashing após a anonimização" src="https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png" />

<div id="impact-on-attribution-2" />

### Como isso afeta a atribuição

Se você chamar `anonymizeUser` antes de chamar `start`, a atribuição não poderá usar identificadores do dispositivo nem o endereço IP do dispositivo. Como resultado, os métodos padrão de atribuição baseados nesses identificadores não ocorrem.

No entanto, a atribuição ainda pode ocorrer usando os métodos a seguir, que não dependem de identificadores do dispositivo:

* <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#atribuição">Atribuição de rede de autorrelato (SRN)</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">Modelo probabilístico (PMOD)</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#install-referrer-android-only">Atribuição baseada no referenciador</Anchor>

Para atribuir o evento de instalação, chame a função `anonymizeUser` somente depois de confirmar que o SDK enviou o evento de instalação para a AppsFlyer.

Esse fluxo garante que:

* O evento de instalação pode ser atribuído normalmente.
* Quaisquer eventos in-app que ocorram depois que `anonymizeUser` for chamado serão enviados **sem identificadores**.

Como resultado, esses eventos in-app são considerados **orgânicos** ou **desconsiderados**, dependendo do método de relatório.

> 📘 **Note**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#atribuição">SRN</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">PMOD (probabilístico)</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#install-referrer-android-only">Atribuição baseada no referenciador</Anchor> são compatíveis no modo anônimo. Isso inclui <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#google-play-install-referrer">Install Referrer do Google Play</Anchor> , outros referenciadores de loja (como <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Xiaomi, Huawei,</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/set-up-appsflyer-preload-referrer-attribution#preload-referrer-da-samsung">e Samsung</Anchor>) e <Anchor target="_blank" href="/marketers/pt/docs/set-up-appsflyer-preload-referrer-attribution?utm_source=chatgpt.com">AppsFlyer preload referrer</Anchor>

<div id="developer-reference-2" />

### Documentação para desenvolvedores

Para consultar referências e documentação sobre como anonimizar informações do usuário, acesse:

<Tabs>
<Tab title="Importante!">

[Como anonimizar informações do usuário](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png">

[Como anonimizar informações do usuário](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

<div id="remove-specific-device-identifiers" />

## Como remover identificadores de dispositivo específicos

Você pode impedir que o SDK colete e envie identificadores específicos para a AppsFlyer. Ao contrário do método `anonymizeUser`, a desativação de identificadores específicos permite que você decida quais IDs deseja manter.

A SDK API inclui os seguintes métodos:

<div id="android-identifiers" />

### Identificadores Android

| Método | Identificadores desativados |
| --- | --- |
| [`Documentação para desenvolvedores`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) | <ul><li>Google Advertising ID (GAID)</li><li>Open Anonymous Device Identifier (OAID)</li><li>Amazon Advertising ID (AAID)</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Open Anonymous Device Identifier (OAID) |

<div id="ios-identifiers" />

### Identificadores iOS

| Método | Identificadores desativados |
| --- | --- |
| [`Se você chamar anonymizeUser antes de chamar start, nenhuma atribuição ocorrerá.`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) | IDFA (iOS 13 e versões anteriores) |
| [`Observação`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection) | IDFV |

<div id="developer-reference-3" />

### Documentação para desenvolvedores

Para consultar referências e documentação sobre como remover identificadores de dispositivo específicos, acesse:

<Tabs>
<Tab title="Android iOS">

[Desativar IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="Android iOS">

[Desativar IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

> 📘 **Note**
>
> **Dúvidas sobre a política de privacidade da AppsFlyer?**
>
> Nossa política de privacidade é definida pelo [AppsFlyer Statement on Data Processing](https://www.appsflyer.com/legal/processing-customer-data/). Para dúvidas com relação a esse documento ou para entrar em contato com nosso responsável pela proteção de dados, envie uma mensagem para [dpo@appsflyer.com](mailto:dpo@appsflyer.com).

<div data-zendesk-anchors="use-start-and-stop-methods=use-os-m%C3%A9todos-start-e-stop h_01HKD1N2C8V0SP1NG8W2EJPRQZ=use-os-m%C3%A9todos-start-e-stop impact-on-attribution=como-isso-afeta-a-atribui%C3%A7%C3%A3o h_01HKD1N2C80QAJSNE83SD45DJA=como-isso-afeta-a-atribui%C3%A7%C3%A3o common-use-cases=casos-comuns h_01HKD1N2C8YHWYARRAGX1TD6DM=casos-comuns developer-reference=documenta%C3%A7%C3%A3o-para-desenvolvedores h_01HKM6VNJFCW77F2268XXDF65Q=documenta%C3%A7%C3%A3o-para-desenvolvedores prevent-sharing-data-with-networks=como-impedir-o-compartilhamento-de-dados-com-ad-networks h_01HKD1N2C8ASV10XWY33R972MC=como-impedir-o-compartilhamento-de-dados-com-ad-networks impact-on-attribution::aa0a9f9e=como-isso-afeta-a-atribui%C3%A7%C3%A3o-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=como-isso-afeta-a-atribui%C3%A7%C3%A3o-1 developer-reference::f2007ab7=documenta%C3%A7%C3%A3o-para-desenvolvedores-1 h_01HKM6VNJFP8C7KCFSV1046H0B=documenta%C3%A7%C3%A3o-para-desenvolvedores-1 anonymize-user-information=como-anonimizar-informa%C3%A7%C3%B5es-do-usu%C3%A1rio h_01HKD1N2C8CWSWK0VSXZ39MQ3D=como-anonimizar-informa%C3%A7%C3%B5es-do-usu%C3%A1rio anonymize-impact=como-isso-afeta-a-atribui%C3%A7%C3%A3o-2 h_01KK93D18X4QYG87CFMZWNHSBA=como-isso-afeta-a-atribui%C3%A7%C3%A3o-2 developer-reference::e4cacf1f=documenta%C3%A7%C3%A3o-para-desenvolvedores-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=documenta%C3%A7%C3%A3o-para-desenvolvedores-2 remove-specific-device-identifiers=como-remover-identificadores-de-dispositivo-espec%C3%ADficos h_01HKD1N2C8S3Y73AZ9J7JFDKQE=como-remover-identificadores-de-dispositivo-espec%C3%ADficos android-identifiers=identificadores-android h_01HKD1N2C8HZ61XHMBC0JNTK7S=identificadores-android ios-identifiers=identificadores-ios h_01HKD1N2C8AHK4EYANG6N6ST06=identificadores-ios developer-reference::4e0971d1=documenta%C3%A7%C3%A3o-para-desenvolvedores-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=documenta%C3%A7%C3%A3o-para-desenvolvedores-3" />
