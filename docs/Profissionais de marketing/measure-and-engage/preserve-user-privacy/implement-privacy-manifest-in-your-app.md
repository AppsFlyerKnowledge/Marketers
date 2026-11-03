---
title: Implemente o Manifesto de Privacidade no seu aplicativo
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
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-08-19T00:33:04Z'
  id: 21677433322641
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/21677433322641
---
> **Visão geral:** No WWDC23, a Apple apresentou novos manifestos de privacidade. Com os Manifestos de privacidade, os desenvolvedores de aplicativos podem fornecer descrições mais precisas de suas práticas de privacidade de aplicativos. A AppsFlyer criou um Manifesto de privacidade para o SDK do AppsFlyer e os detalhes são explicados abaixo.

## CONTEXTO

Com os Manifestos de privacidade, um desenvolvedor de aplicativos pode criar um registro das categorias de dados que coleta por meio de seu aplicativo de forma independente e por meio do uso de dependências de terceiros, como SDKs de terceiros usados pelo aplicativo. Essas informações ajudam os desenvolvedores de aplicativos a representar com precisão as práticas de privacidade em seus aplicativos, inclusive por meio dos rótulos nutricionais que fornecem aos usuários.

Em muitos casos, os desenvolvedores de aplicativos não estão cientes de quais dados SDKs de terceiros estão coletando ou para que um SDK específico está usando os dados. O Manifesto de privacidade permite que SDKs de terceiros passem facilmente essas informações para os desenvolvedores de aplicativos, ajudando-os a criar rótulos nutricionais precisos.

### O que são rótulos nutricionais?

Os rótulos nutricionais fornecem informações sobre as práticas de privacidade de um aplicativo em um formato fácil de ler e compreensível. Os usuários finais têm mais transparência sobre quais dados o aplicativo está coletando e para qual finalidade. Para obter mais informações sobre rótulos nutricionais, clique <Anchor target="_blank" href="/marketers/pt/docs/preparing-for-the-app-store-review-nutrition-labels">aqui</Anchor>.

## O que está incluído no Manifesto de privacidade da AppsFlyer?

> 🚧 **Importante!**
>
> Além do SDK da AppsFlyer, você terá que determinar sua própria coleta de dados, API de motivo necessário e uso em seu aplicativo ou outros SDKs e relatar essas informações nos rótulos nutricionais

A AppsFlyer SDK 6.14.0 inclui o Manifesto de privacidade da AppsFlyer. Isso inclui:

* [Uso de dados](#uso-de-dados)
* [APIs de motivo obrigatório](#apis-de-motivo-obrigatório)
* [Domínios de rastreamento](#domínios-de-rastreamento)

### Uso de dados

A Apple exige que os desenvolvedores de aplicativos e SDK registrem a categoria de dados e os motivos pelos quais o aplicativo ou SDK de terceiros coleta esses dados.

Os desenvolvedores de aplicativos podem usar o Xcode para criar um relatório de privacidade, resumindo as informações sobre os dados coletados.

A seguir estão os tipos de dados coletados pelo SDK da AppsFlyer, que estão incluídos no manifesto de privacidade:

> 📘 **Observação**
>
> O seguinte pressupõe as configurações padrão do software da AppsFlyer. Os desenvolvedores de aplicativos são responsáveis por garantir que eles adaptem seu próprio manifesto de acordo com suas configurações e usos específicos do SDK da AppsFlyer.

| Nome | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| ID do dispositivo (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | Sim | Sim | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| Interação com produtos (Lançamentos) | NSPrivacyCollectedDataTypeProductInteraction | Não | Não | NSPrivacyCollectedDataTypePurposeAnalytics |

### APIs de motivo obrigatório

A Apple forneceu uma lista de APIs que exigem o motivo para seu uso. Os aplicativos e SDKs que usam essas APIs devem detalhá-las na seção API de motivo obrigatório do Manifesto de privacidade. Essas APIs são divididas em categorias com base em sua funcionalidade e nas informações que fornecem de acordo com a <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">lista de tópicos da Apple.</Anchor> Estas são as APIs incluídas no manifesto de privacidade do AppsFlyer SDK versão 6.14.0:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">APIs de carimbo de data/hora de arquivo</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">APIs padrão do usuário</Anchor>

Para justificar o uso das Required Reason APIs, os desenvolvedores de aplicativos terão que fornecer a categoria de API desejada e especificar os motivos para seu uso. Abaixo estão as APIs da AppsFlyer e seu uso.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK versão 6.14.0 e superior">

| Categoria da API | Tipo de categoria da API | Motivo | Comentários |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">APIs de carimbo de data/hora de arquivo</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | O SDK está usando as APIs <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> e <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> para determinar a data de instalação do aplicativo e a data de atualização do aplicativo. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">APIs padrão do usuário</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | O SDK armazena dados necessários para sua operação. Por exemplo - mantendo quantas vezes o aplicativo foi iniciado. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK versões 6.13.x e anteriores">

| Categoria da API | Tipo de categoria da API | Motivo | Comentários |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">APIs de carimbo de data/hora de arquivo</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | O SDK está usando as APIs <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> e <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> para determinar a data de instalação do aplicativo e a data de atualização do aplicativo. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">APIs de tempo de inicialização do sistema</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | Medir o desempenho do SDK (tempo necessário para executar uma solicitação, etc.) |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">APIs padrão do usuário</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | O SDK armazena dados necessários para sua operação. Por exemplo - mantendo quantas vezes o aplicativo foi iniciado. |

Para sua conveniência, você pode copiar o seguinte trecho de código, que inclui os Motivos obrigatórios acima, e colá-lo em seu arquivo PrivacyInfo.xcprivacy. **Etapa 1:**

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

### Domínios de rastreamento

Qualquer Domínio de Rastreamento usado em um aplicativo ou SDK de terceiros deve ser registrado no manifesto de privacidade. Se os usuários não concederem permissões (opt-out) por meio da estrutura ATT (APp Tracking Transparency), o sistema operacional iOS bloqueará todo o tráfego de saída para esse domínio. O SDK da AppsFlyer verifica o status ATT do usuário antes de qualquer solicitação do servidor e executa a solicitação com base no fato de o usuário ter optado por participar.

## Perguntas frequentes

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="A AppsFlyer tem um SDK compatível com o Manifesto de privacidade?">

Sim, a partir da versão 6.14.0, o SDK tem compatibilidade total com o Manifesto de privacidade.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="Tenho que relatar minha própria coleta de dados?">

Sim, além da AppsFlyer ou de outros SDKs, você terá que determinar sua própria coleta e uso de dados e relatar essas informações nos rótulos nutricionais, incluindo quaisquer alterações de configuração feitas nas configurações padrão do SDK do AppsFlyer (por exemplo, mensuração de eventos in-app).

</Accordion>

<div data-zendesk-anchors="background=contexto h_01HCY4D9EKHYB5B3YNWRCB53F4=contexto what-are-nutrition-labels=o-que-s%C3%A3o-r%C3%B3tulos-nutricionais h_01HCY4ZASEAR69RT3YMHMSE4NP=o-que-s%C3%A3o-r%C3%B3tulos-nutricionais what-to-consider-when-getting-your-app-ready-to-ios17=o-que-est%C3%A1-inclu%C3%ADdo-no-manifesto-de-privacidade-da-appsflyer h_01HCY4D9EKTKB50BSZD7RBMMYB=o-que-est%C3%A1-inclu%C3%ADdo-no-manifesto-de-privacidade-da-appsflyer h_01HQ5C9WGW669HBWSG4WQMJTGP=importante data-usage=uso-de-dados h_01HQ03P71BG159MCE3VQY4GTMH=uso-de-dados h_01HT9QHRQSKDQ8GR17N7X5QB8N=observa%C3%A7%C3%A3o required-reason-apis=apis-de-motivo-obrigat%C3%B3rio h_01HQ03NV880VHFTXQDE8R6ZRZH=apis-de-motivo-obrigat%C3%B3rio h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=dom%C3%ADnios-de-rastreamento h_01HQ03NV88SJPYKBM66S7X6GP8=dom%C3%ADnios-de-rastreamento faq=perguntas-frequentes 01HQQXSN96D4QTTYHG8CBE8695=perguntas-frequentes h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />
