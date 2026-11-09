---
title: Integração do Adobe Analytics com a AppsFlyer
metadata:
  keywords:
    - Adobe Analytics
    - Integration
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
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-09-23T00:11:08Z'
  id: 115003326706
  locale: pt
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/pt/articles/115003326706
---
> **Resumo:** [O Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (antigo Omniture) é um conjunto de ferramentas para análises preditivas e em tempo real que podem ser integradas a fontes de terceiros. Ele inclui os aplicativos de relatórios e análises de marketing (SiteCatalyst), análise ad hoc (Adobe Discover) e Insight para ajudar a criar uma visão holística das atividades comerciais, transformando as interações com os clientes em insights.

<div id="overview" />

## Visão geral

Essa integração consiste em um fluxo de dados bidirecional entre a Adobe e a AppsFlyer. Para que a integração seja bem-sucedida, essa integração requer a implementação de código em seu aplicativo. Os requisitos da AppsFlyer e da Adobe devem ser atendidos para que a integração seja totalmente bem-sucedida.

<div id="setting-up-adobe-analytics-integration" />

## Configurando a integração com o Adobe Analytics

Se você estiver usando o Adobe Analytics Report Suite para análise geral do desempenho da campanha e criação de segmentos, a integração da AppsFlyer com o Adobe Analytics permite a transferência automática de dados de atribuição da AppsFlyer para a Adobe para ajudar você a atingir suas metas.

<div id="prerequisites" />

### Pré-requisitos:

* Configuração de documentos <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">do SDK móvel da Adobe Experience Platform</Anchor>
* <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/home">ID de visitante do Marketing Cloud</Anchor> ou serviço de ID da Experience Cloud
* Três eVars em cada conjunto de relatórios que podem ser usadas com o único propósito dessa integração

<div id="step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer" />

### Etapa 1: Compartilhe o Adobe Experience Cloud ID (ECID, Marketing Cloud ID ou ID de visitante) com a AppsFlyer.

Para extrair e compartilhar a Adobe Experience Cloud ID:

1. <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid">Atualize o aplicativo e extraia o ID de visitante da Marketing Cloud</Anchor> usando o método Adobe SDK logo após a inicialização do SDK da Adobe.
2. Use um dos seguintes métodos do SDK da AppsFlyer para definir a ID de visitante da Adobe Marketing Cloud:

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="Android">

Saiba mais sobre [o método setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID"); AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

Saiba mais sobre [o método setAdditionalData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata).

Objetivo c

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

Saiba mais sobre [o método setAdditionalData](https://dev.appsflyer.com/hc/docs/api#setadditionaldata).

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>(); CustomDataMap. Add("marketingCloudID", "ADOBE_VISITOR_ID"); AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="Definir ID de usuário cliente">

<Tabs>
<Tab title="Android">

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">o método</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserID</Anchor><Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">.</Anchor>

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">o método setCustomerUserID</Anchor>.

Objetivo c

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserID
```

</Tab>
</Tabs>

</Accordion>

<div id="step-2-configure-adobe-analytics-in-appsflyer" />

### Passo 2: Configurar o Adobe Analytics na AppsFlyer

**Pré-requisito:** Antes de configurar a integração, certifique-se de [passar a ID de visitante da Adobe Marketing Cloud para o SDK da AppsFlyer](/docs/adobe-analytics-integration-with-appsflyer#etapa-1-compartilhe-o-adobe-experience-cloud-id-ecid-marketing-cloud-id-ou-id-de-visitante-com-a-appsflyer).

**Para ativar ou editar a integração:**

1. No separador **Integração**, selecione a aplicação para integração e ative **Ativar Parceiro**.  
   **Nota:** Essa opção deve permanecer habilitada <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativada)</Anchor> enquanto você trabalhar com o parceiro.
2. Pesquise o **Adobe Analytics** e selecione-o.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração da integração.
4. **Para editar**: Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.Para ativar:** Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Marketplace de Parceiros.
5. Configure os postbacks padrão enviados para o Adobe Analytics. A AppsFlyer pode enviar postbacks automáticos tanto para instalações quanto para reengajamentos (incluindo reatribuições). Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.
6. No **SDK do Adobe Analytics**, como parte do arquivo **ADBMobileConfig.XML**, copie o **Report\_Suite\_ID (destacado em azul) e o Adobe\_Analytic\_Server\_URL** **(destacado em verde) e cole-os nos respectivos campos na página de integração do Adobe Analytics** na AppsFlyer.

   <Image align="center" alt="" src="https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png" />
7. Clique em  **Salvar integração**.

Depois de salvar, a AppsFlyer envia os seguintes dados para o Adobe Analytics para cada instalação orgânica e não orgânica:

* ID da Adobe (MCVID)
* ID do conjunto de relatórios e URL do servidor
* ID do dispositivo do cliente
* Canal de mídia
* Nome da campanha

<div id="note" />

> 📘 **Nota**
>
> De acordo com os termos de serviço dos Meta ads e dos X Ads, a AppsFlyer está proibida de compartilhar dados em nível de usuário com terceiros. Isso significa que as instalações do Meta Ads e do X Ads são enviadas como orgânicas.

<div id="step-3-map-data-to-evars-in-adobe-analytics" />

### Passo 3: Mapeie dados para eVars no Adobe Analytics

Devido à descontinuação dos conectores de dados do Adobe Analytics, você precisará aproveitar as regras de processamento para mapear variáveis de contexto para as eVars.

Saiba mais sobre [como usar as regras de processamento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en).

Variáveis de dados de contexto da AppsFlyer mapeadas adequadamente:

* MobileAdCampaign(Dados de contexto)
* MobileAdNetwork(Dados de contexto)
* MobileAdProvider(Dados de contexto)

Se você tiver problemas com o mapeamento de variáveis de dados de contexto da AppsFlyer por meio de regras de processamento, entre em contato com sua equipe de contas da Adobe para obter mais suporte

<div id="step-4-optional-set-up-your-marketing-channel" />

### Etapa 4 [opcional]: Configure seu canal de marketing

Consulte a <Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">documentação do Adobe Analytics</Anchor> sobre como configurar seu canal de marketing na plataforma deles. Certifique-se de selecionar os seguintes campos nas regras de identificação:

1. “O valor da variável de conversão definido pelo web beacon da Adobe”: **Selecione** AppsFlyer e Exists.
2. “Identificar o canal como”: Selecione **Atribuição de aplicativo móvel**.
3. “Defina o valor do canal como:” Selecione **Campanha da AppsFlyer**.

<div id="domain-and-security-details" />

## Detalhes de domínio e segurança

Abaixo estão os detalhes dos problemas de domínio e segurança:

1. ANALYTIC\_SERVER\_DOMAIN pode ser encontrado como a variável do servidor no arquivo de configuração do seu aplicativo. Você pode selecionar qualquer domínio para análise de atribuição. Em geral, domínios padrão para o serviço de coleções do Adobe Analytics, como sc.omtrdc.net, são usados. Isso pode ser encontrado nas configurações de análise (servidor) no arquivo **ADBMobile.config**.
2. O protocolo (HTTP/HTTPS) do URL depende se o domínio do servidor ANALYTIC é seguro ou não. É importante que você use o protocolo correto. Para descobrir se a configuração é segura, verifique se a configuração de análise (SSL) está definida como **verdadeira** no arquivo **ADBMobile.config**. Se sua conexão for segura, use HTTPS; se não for segura, use HTTP.
3. O ID do conjunto de relatórios pode ser encontrado como a variável **rsids** no arquivo de configuração do seu aplicativo. Você pode dar qualquer nome ao seu conjunto de relatórios.
4. O ts= `{timestamp}` só é usado se sua configuração **offlineEnabled** for verdadeira em seu arquivo de configuração. Remova esse parâmetro da URL se **OfflineEnabled** estiver definido como False ou se seu conjunto de relatórios não estiver habilitado para **Timestamp**.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=vis%C3%A3o-geral setting-up-adobe-analytics-integration=configurando-a-integra%C3%A7%C3%A3o-com-o-adobe-analytics h_01HA4ZWDM11RJ6GRJ7W8QMFACT=configurando-a-integra%C3%A7%C3%A3o-com-o-adobe-analytics prerequisite=pr%C3%A9-requisitos h_01HA4ZWDM1YK58Q56Y0S8PC1E2=pr%C3%A9-requisitos step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=etapa-1-compartilhe-o-adobe-experience-cloud-id-ecid-marketing-cloud-id-ou-id-de-visitante-com-a-appsflyer h_01HA4ZWDM1J65D32PVXY0ZD9YV=etapa-1-compartilhe-o-adobe-experience-cloud-id-ecid-marketing-cloud-id-ou-id-de-visitante-com-a-appsflyer h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=passo-2-configurar-o-adobe-analytics-na-appsflyer h_01HA4ZWDM26AVEQKC4CXF18D22=passo-2-configurar-o-adobe-analytics-na-appsflyer h_01HA4ZWDM23A6BFXDV2JH4NR2J=nota step-3-map-data-to-evars-in-adobe-analytics=passo-3-mapeie-dados-para-evars-no-adobe-analytics h_01HA4ZWDM27S52KY36GS1QPKJ5=passo-3-mapeie-dados-para-evars-no-adobe-analytics step-4-%5Boptional%5D-set-up-your-marketing-channel=etapa-4-opcional-configure-seu-canal-de-marketing h_01HA4ZX6FG6RM5JNDKQP6GVAD1=etapa-4-opcional-configure-seu-canal-de-marketing domain-and-security-details=detalhes-de-dom%C3%ADnio-e-seguran%C3%A7a h_01HA4ZWDM2NNFVPP1XYWKPS89A=detalhes-de-dom%C3%ADnio-e-seguran%C3%A7a" />
