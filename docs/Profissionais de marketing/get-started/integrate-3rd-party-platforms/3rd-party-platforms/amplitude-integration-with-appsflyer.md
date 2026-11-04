---
title: Integração do Amplitude com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-09-10T12:10:15Z'
  id: 211200306
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/211200306
---
> **At a glance:** Integre o AppsFlyer com o Amplitude para compartilhar dados de atribuição de usuários e análises de eventos e obter melhores insights sobre engajamento, retenção e receita. Escolha entre **duas versões de integração, V1 ou V2**, dependendo do seu caso de uso e das suas necessidades de análise.

<div id="about-the-integration" />

## Aba de integração

**Visão geral:** Visão geral: o Amplitude, um parceiro integrado da AppsFlyer, fornece análises de produtos para ajudar empresas mobile e web a entender o comportamento do usuário. As equipes de produto, marketing e growth usam o Amplitude para descobrir e compartilhar insights de engajamento, retenção e receita. A integração permite que a AppsFlyer envie dados de eventos-chave para a Amplitude após a instalação, possibilitando uma análise abrangente em nível de usuário.

Há duas versões da integração com a Amplitude:

* **Amplitude V1:**  
  Esta versão usa a API de atribuição da Amplitude. A AppsFlyer envia os dados de instalação coletados após a conclusão da integração. A Amplitude usa o ID do anúncio como identificador e descarta os dados se nenhum evento de usuário correspondente for registrado em 72 horas. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">Saiba mais</Anchor>
* **Amplitude V2 :**  
  Esta versão usa a API HTTP V2 da Amplitude. A AppsFlyer envia dados de instalações e de eventos in-app após a conclusão da integração. Os identificadores são priorizados (user\_id e device\_id) e, se a correspondência falhar, um novo usuário é registrado. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">Saiba mais</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>Para ativar ou editar a integração:**

| Versão | API usada | Identificadores usados | Cobertura de eventos |
| --- | --- | --- | --- |
| **V1** | Permissões | ID de publicidade (AdID) | Somente instalações |
| **V2** | API HTTP V2 | `user_id`, `device_id` (lógica de fallback) | Instalações e eventos in-app |

> 🚧 **Important**
>
> **Importante!**
>
> * Escolha a integração Amplitude V1 ou V2. **Não use as duas** simultaneamente. Usar as duas versões ao mesmo tempo pode resultar no envio de eventos duplicados para o Amplitude.
> * <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="prerequisites" />

## Pré-requisitos

**Antes de começar:**

* Entre em contato com a Amplitude para criar uma conta, caso ainda não tenha uma.
* Decida se você configurará a integração com a Amplitude **V1** ou **V2**.
* Evite enviar os mesmos eventos pelo SDK da Amplitude e pela AppsFlyer para impedir a duplicação.
* Consulte o pré-requisito adicional para a integração com a Amplitude V2.

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Pré-requisitos adicionais para a integração com a Amplitude V2

A integração V2 exige a configuração de:

* [ID do dispositivo da Amplitude](/docs/amplitude-integration-with-appsflyer#id-do-dispositivo-da-amplitude)
* [ID de usuário cliente](/docs/amplitude-integration-with-appsflyer#id-de-usuário-cliente)
* [ID da sessão da Amplitude](/docs/amplitude-integration-with-appsflyer#id-da-sessão-do-amplitude)

<div id="amplitude-device-id" />

#### ID do dispositivo da Amplitude

Para ativar a atribuição em nível de usuário, você deve passar o Device ID da Amplitude para a SDK da AppsFlyer. Esse valor é enviado com cada postback.

<Tabs>
<Tab title="com o Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**Linguagem:** Java/Kotlin

**Documentação:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">referência do SDK para Android</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**Linguagem:** Objective-C

**Documentação:** [referência da SDK para iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**Linguagem:** Swift

**Documentação:** [referência da SDK para iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData. Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId()); AppsFlyer.setAdditionalData(customData);
```

**Linguagem:** C#

**Documentação:** [referência da SDK do Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="CONTEXTO">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},
(res) => {
//...
}
);
```

**Idioma:** JavaScript

**Documentação:** [referência do SDK do React Native](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**Idioma:** JavaScript

**Documentação:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};
appsFlyerSdk.setAdditionalData(data);
```

**Idioma:** Dart

**Documentação:** [referência do SDK do Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### ID de usuário cliente

Defina o ID de usuário do cliente (CUID). Este é um identificador exclusivo, normalmente gerado e definido  
pelo proprietário do aplicativo durante o registro do usuário. <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">Saiba mais</Anchor>

<div id="amplitude-session-id" />

#### ID da sessão do Amplitude

Defina o ID da sessão do Amplitude e transmita-o para a AppsFlyer. <Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">Saiba mais</Anchor>

<Tabs>
<Tab title="com o Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**Idioma:** Java/Kotlin

**Documentação:** [referência do SDK do Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**Idioma:** Objective-C

**Documentação:** [referência do SDK do iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**Idioma:** Swift

**Documentação:** [referência do SDK do iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData. Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId()); AppsFlyer.setAdditionalData(customData);
```

**Idioma:** C#

**Documentação:** [referência do SDK do Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="CONTEXTO">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},
(res) => {
//...
}
);
```

**Idioma:** JavaScript

**Documentação:** [referência do SDK do React Native](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**Idioma:** JavaScript

**Documentação:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeSessionId": amplitude.getSessionId()};
appsFlyerSdk.setAdditionalData(data);
```

**Idioma:** Dart

**Documentação:** [Referência do SDK do Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## Configurando o Amplitude

**Para ativar ou editar a integração:**

1. No AppsFlyer, acesse a guia **Collaborate** > **Partner Integrations > Marketplace** .
2. Para configurar a integração do Amplitude V1, selecione **Amplitude V1** (parceiro de tecnologia).

   <Image alt="Select Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />

   Para configurar a integração do Amplitude V2, selecione **Amplitude V2** (parceiro de tecnologia).

   <Image alt="Selecionar Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. Depois de selecionar sua versão do Amplitude, clique em **Configurar a integração**.

   ![Clique em configurar a integração.png](https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png)
4. Clique em **Configurar a integração**.
   * Selecione seu aplicativo.
   * Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.

     <Image alt="Ativar integração de parceiros blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. Complete a configuração nas abas restantes:

<Accordion title="Aba Integração">

A guia Integração é dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **primeiro acesso**, você precisará habilitar **ativar Parceiro** para permitir a configuração dos parâmetros da aba de integração. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

<div id="advanced-data-sharing" />

#### Compartilhamento avançado de dados

Para compartilhar informações adicionais com o Amplitude, ative o **compartilhamento avançado de dados**. Quando ativado, o Amplitude recebe os seguintes dados para instalação (e não eventos in-app) mapeados conforme listamos abaixo:

| Propriedade do Amplitude | Ponto de dados da AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| Disponível apenas em <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">relatórios avançados</Anchor>. | Nome da entidade da linha de produto que agrupa aplicativos parecidos entre plataformas. |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| app\_version | app\_version |

<div id="amplitude-eu-data-center" />

#### Centro de dados da UE

Quando o **centro de dados do Amplitude na UE** está desativado, os postbacks de instalação são enviados para o centro de dados dos EUA.  
Para enviar os postbacks ao banco de dados do Amplitude da UE, ative o banco de dados do Amplitude da UE.

<div id="api-key" />

#### Chave da API

O Amplitude se conecta com a AppsFlyer através de uma chave de API exclusiva. Se você ainda não tem essa chave, peça-a ao Amplitude para continuar com a integração ou siga as etapas abaixo.

<span id="obtaining-the-api-key-from-amplitude"></span>**Obtenção da chave de API do Amplitude**

**Observação:** somente usuários que têm a função de administrador ou gerente no Amplitude podem acessar a chave de API.

1. Faça login na sua conta do Amplitude.
2. No canto superior direito da página, clique no ícone de configurações > **configurações da organização**.

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Clique em **projetos** e selecione o projeto desejado.

   ![amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. Na aba **projeto**, copie sua chave de API.

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Configure o Amplitude no dashboard da AppsFlyer.

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Amplitude após uma instalação. Use essa seção para definir a fonte de usuários para a qual os postbacks são enviados. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

<Image alt="Captura de tela 2025-12-03 às 1.57.03 PM.png" src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" width="703px" />

<div id="in-app-event-settings" />

### Configurações de eventos in-app

* Insira a chave da API.
* Quando o **centro de dados do Amplitude** está desativado, os postbacks de eventos in-app são enviadas para o centro de dados dos EUA.  
  **Para enviar postbacks de eventos in-app para o centro de dados da UE, basta ativá-lo no Amplitude.**

Depois de salvar a configuração, a AppsFlyer envia os seguintes dados para o Amplitude:

* Device ID (IDFV/Google Advertising ID)
* Media Source
* Campaign name

O envio do IDFA para dispositivos iOS depende do <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">status do consentimento do usuário na ATT e às configurações de Privacidade Avançada</Anchor>.

<div id="in-app-event-postbacks" />

### Postbacks de eventos in-app

<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Configure o envio de postbacks de eventos in-app</Anchor> para o Amplitude.

</Accordion>

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<Accordion title="Aba de custo">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<Accordion title="Aba de receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<Accordion title="Aba permissões">

As permissões não estão disponíveis para o Amplitude.

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Visualização dos dados de atribuição no console do Amplitude

Os dados de atribuição enviados para o Amplitude são exibidos em seus dashboards como eventos e propriedades prefixados com **[AppsFlyer]**:

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **Important**
>
> **Importante!**
>
> Em alguns casos, o Amplitude mostra dados da AppsFlyer como "bloqueados". Se você não consegue ver os dados da AppsFlyer no Amplitude, verifique se eles estão definidos como eventos bloqueados.

<div id="sending-amplitude-events-to-appsflyer" />

## Enviando eventos de Amplitude para o AppsFlyer

A integração também permite enviar seus eventos do Amplitude para o AppsFlyer via uma API de servidor para servidor. Veja a documentação da Amplitude sobre como fazer isso.

<div data-zendesk-anchors="about-the-integration=aba-de-integra%C3%A7%C3%A3o h_01JSE81SX1B1RH978Y08W1XXX8=aba-de-integra%C3%A7%C3%A3o set-up-the-integration=pr%C3%A9-requisitos h_01JSE958V510B9P6VEQTXC55S7=pr%C3%A9-requisitos additional-prerequisites-for-the-v2-integration=pr%C3%A9-requisitos-adicionais-para-a-integra%C3%A7%C3%A3o-com-a-amplitude-v2 h_01JSKEMMEB00PERVQWPYNF5V2E=pr%C3%A9-requisitos-adicionais-para-a-integra%C3%A7%C3%A3o-com-a-amplitude-v2 amplitude-device-id=id-do-dispositivo-da-amplitude h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=id-do-dispositivo-da-amplitude customer-user-id=id-de-usu%C3%A1rio-cliente h_01JSKFK4BFH3PP98XAZ0W8GG11=id-de-usu%C3%A1rio-cliente amplitude-session-id=id-da-sess%C3%A3o-do-amplitude h_01JSKFQXPPJVCW68C4H9B4EJ76=id-da-sess%C3%A3o-do-amplitude set-up-the-integration::45aa5acf=configurando-o-amplitude h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=configurando-o-amplitude activate-partner=ativar-parceiro 01H8KPA9JKDRA680Y0WPZ172EM=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais 01H8KPA9JKF4VCA4S22SYT40WT=configura%C3%A7%C3%B5es-gerais advanced-data-sharing=compartilhamento-avan%C3%A7ado-de-dados 01H8KPA9JKJ2XN1AEPV74QVJYZ=compartilhamento-avan%C3%A7ado-de-dados amplitude-data-center=centro-de-dados-da-ue 01H8KPA9JKP0T0FDND97VA23EY=centro-de-dados-da-ue api-key=chave-da-api 01H8KPA9JKDYDPDGRXZSH2BAV8=chave-da-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=postbacks-padr%C3%A3o 01H8KRBGYQ973CT3H8GHZ8R0BH=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app 01H8KPA9JKM4S79160BEYN3B6V=configura%C3%A7%C3%B5es-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app 01H8KSQ76XE9Z191P1RMANF6EQ=postbacks-de-eventos-in-app viewing-attribution-data-in-the-amplitude-console=visualiza%C3%A7%C3%A3o-dos-dados-de-atribui%C3%A7%C3%A3o-no-console-do-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=visualiza%C3%A7%C3%A3o-dos-dados-de-atribui%C3%A7%C3%A3o-no-console-do-amplitude sending-amplitude-events-to-appsflyer=enviando-eventos-de-amplitude-para-o-appsflyer h_01HPYFZDX1WWDWJEBZ4DK706B4=enviando-eventos-de-amplitude-para-o-appsflyer" />
