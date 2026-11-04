---
title: Integração com o Google Analytics — Dimensões personalizadas
metadata:
  keywords:
    - Analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-07T13:34:54Z'
  edited_at: '2026-08-19T00:12:24Z'
  id: 4413033740817
  locale: pt
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/pt/articles/4413033740817
---
> **At a glance:** **Visão geral:** Configure a integração com o Google Analytics usando dimensões personalizadas.

<div id="custom-dimensions-on-google-analytics" />

## Dimensões personalizadas no Google Analytics

Há outro método para enviar os dados de atribuição do AppsFlyer ao Google Analytics, que é configurado no GA e não no dashboard do AppsFlyer.

> 🚧 **Important**
>
> **Importante!**
>
> O método de dimensões personalizadas **NÃO É RECOMENDADO** pelos seguintes motivos:
>
> * Integrar o Google Analytics pelo dashboard do AppsFlyer é simples, rápido e fácil
> * Integrar o Google Analytics usando dimensões personalizadas é complicado e sujeito a erros
> * Usar dimensões personalizadas exige que você use o SDK do AppsFlyer e o SDK do Google Analytics
> * Usar dimensões personalizadas tem maior potencial de causar discrepâncias

Os anunciantes que usam a nova <Anchor target="_blank" href="/marketers/pt/docs/google-analytics-ga4-integration">integração com o Google Analytics</Anchor> não precisam usar o método de dimensões personalizadas.

> 📘 **Note**
>
> **Atenção**
>
> Este método exige que você integre o SDK do GA ao seu aplicativo.
>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/android/v4/">SDK do GA para Android</Anchor>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/ios/v3/">SDK do GA para iOS</Anchor>

<div id="setting-media-source-as-a-custom-dimension-on-google-analytics" />

### Definir o canal de mídia como uma dimensão personalizada no Google Analytics

O Google Analytics tem uma ferramenta poderosa para criar segmentação no nível do usuário chamada dimensões personalizadas. Os valores das dimensões personalizadas são enviados de dispositivos mobile, e seus relatórios são gerados com base nessas dimensões no dashboard do Google Analytics.

<div id="step-1-define-it-on-google-analytics" />

### Etapa 1: Defina no Google Analytics

1. Selecione seu aplicativo no menu do GA menu
2. Selecione ***Admin*** na barra superior do GA dashboard
3. Na coluna ***PROPERTY***, selecione ***Custom Definition***
4. Selecione ***Custom Dimensions***
   ![Opção Dimensões personalizadas no painel de administração do Google Analytics](https://files.readme.io/e475ad1eda5b6338825b712e6c8254f245d5339f50ae40e723f465207e124262-4413121542033.png)
5. Crie uma nova dimensão. Chame-a de **AppsFlyer Media Source** e certifique-se de selecionar o escopo ***usuário***. Isso garante que os dados sejam salvos em várias sessões. ![ga2.png](https://files.readme.io/b2d85fd068e5523265a2b49b4218234fc77d5896ad41801cbe0e017752763cf2-4413121449873.png)

   Cada dimensão é criada com um índice que você deve lembrar para poder usá-lo depois na API do GA a partir do seu aplicativo. Neste exemplo, o índice da nova dimensão é 10.

   ![ga3](https://files.readme.io/6efc2249ede92291a2aadd16eccbc5b38b580723c6277e3746bdd467de29764a-11179413394193.png)

   Repita esta etapa e crie outra dimensão e chame-a de **Campanha da AppsFlyer**

<div id="step-2-setting-and-sending-the-data-from-the-app" />

### Etapa 2: Configurando e enviando os dados do aplicativo

Primeiro, você precisa obter o valor do canal de mídia no SDK da AppsFlyer. Você pode fazer isso usando o método `onConversionDataSuccess`.

**Nota:** A partir do SDK V5, `onConversionDataSuccess` é o nome do método para obter dados de conversão. Se você estiver usando uma versão do SDK inferior à 5.0.0, o nome do método é `onInstallConversionDataLoaded` no Android e `onConversionDataReceived` no iOS. Recomendamos que você atualize para o SDK 5.0.0. Clique <Anchor target="_blank" href="/marketers/pt/docs/links-to-appsflyer-sdk-release-notes">aqui</Anchor> para saber mais.

Em seguida, você pode definir o canal de mídia como dimensão personalizada usando o SDK do Google Analytics. Veja os exemplos de código a seguir para saber como fazer isso:

<Tabs>
<Tab title="Android iOS">

```objectivec
private static Tracker sTracker;
@Override
public void onConversionDataSuccess(Map<String, String> conversionData)
{
  if (conversionData.get("af_status") == "Non-organic")
  {
    String mediaSource = conversionData.get("media_source");
    String campaign = conversionData.get("campaign");
    sTracker.set(Fields.customDimension(10), mediaSource);
    sTracker.set(Fields.customDimension(1), campaign);
  }
  else if (conversionData.get("af_status") == "Organic")
  {
    sTracker.set(Fields.customDimension(10), "Organic");
  }
}
```

</Tab>

<Tab title="Exemplo">

```objectivec
-(void)onConversionDataSuccess:(NSDictionary*) installData {
  id status = [installData objectForKey:@"af_status"];
  if([status isEqualToString:@"Non-organic"]) {
		id mediaSource = [installData objectForKey:@"media_source"];
		id campaign = [installData objectForKey:@"campaign"];
		[[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			] value: mediaSource];
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:1
			]
			value: campaign];
   } 
	 else if([status isEqualToString:@"Organic"]) {
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			]
			value: "Organic"];
   } 
}
```

</Tab>
</Tabs>

<div id="step-3-see-the-results-in-google-analytics" />

### Etapa 3: Veja os resultados no Google Analytics

A maioria dos relatórios do GA tem uma opção de análise detalhada chamada ***Dimensões personalizadas***. Você pode selecionar as dimensões ***Canal de mídia da AppsFlyer*** ou ***Campanha da AppsFlyer*** ([definidas na etapa 1](/docs/google-analytics-integration-custom-dimensions#etapa-1-defina-no-google-analytics)) para ver quais canais de mídia e campanhas trazem usuários que instalam seu aplicativo.

![G_analytics1.png](https://files.readme.io/dde9219a7a8eec5c861b5031ad741ff7377d85ba9c3693bcbc455fd735f8af2d-4413121449617.png)

<div data-zendesk-anchors="custom-dimensions-on-google-analytics=dimens%C3%B5es-personalizadas-no-google-analytics h_01HDP3FHGNR06EV1KS8F1PFQ09=dimens%C3%B5es-personalizadas-no-google-analytics setting-media-source-as-a-custom-dimension-on-google-analytics=definir-o-canal-de-m%C3%ADdia-como-uma-dimens%C3%A3o-personalizada-no-google-analytics h_01HDP3FHGP9H18VJKNSR27HXEZ=definir-o-canal-de-m%C3%ADdia-como-uma-dimens%C3%A3o-personalizada-no-google-analytics step-1-define-it-on-google-analytics=etapa-1-defina-no-google-analytics h_01HDP3FHGPTJ4EVYPDA7RWPJF9=etapa-1-defina-no-google-analytics step-2-setting-and-sending-the-data-from-the-app=etapa-2-configurando-e-enviando-os-dados-do-aplicativo h_01HDP3FHGPF3BJZSG6G0QP5T1R=etapa-2-configurando-e-enviando-os-dados-do-aplicativo step-3-see-the-results-in-google-analytics=etapa-3-veja-os-resultados-no-google-analytics h_01HDP3FHGP9G9BP956KM4ACDRC=etapa-3-veja-os-resultados-no-google-analytics" />
