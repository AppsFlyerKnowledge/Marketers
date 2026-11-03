---
title: Integración de Google Analytics—dimensiones personalizadas
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
  edited_at: '2026-08-22T00:12:24Z'
  id: 4413033740817
  locale: es
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/es/articles/4413033740817
---
> **At a glance:** Configura la integración con Google Analytics mediante dimensiones personalizadas.

## Dimensiones personalizadas en Google Analytics

Hay otro método para enviar los datos de atribución de AppsFlyer a Google Analytics, que se configura en GA y no en el dashboard de AppsFlyer.

> 🚧 **Important**
>
> **Importante:**
>
> El método de dimensiones personalizadas **NO SE RECOMIENDA** por lo siguiente:
>
> * Integrar Google Analytics a través del Dashboard de AppsFlyer es simple, rápido y fácil
> * Integrar Google Analytics mediante dimensiones personalizadas es complicado y propenso a errores
> * Usar dimensiones personalizadas requiere que uses tanto el SDK de AppsFlyer como el SDK de Google Analytics
> * Usar dimensiones personalizadas tiene más posibilidades de causar discrepancias

Los anunciantes que usan la nueva <Anchor target="_blank" href="/marketers/es/docs/google-analytics-ga4-integration">integración con Google Analytics</Anchor> no necesitan usar el método de dimensiones personalizadas.

> 📘 **Note**
>
> **Nota:**
>
> Este método requiere que integres el SDK de GA en tu App.
>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/android/v4/">SDK de GA para Android</Anchor>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/ios/v3/">SDK de GA para iOS</Anchor>

### Configurar la fuente de medios como una dimensión personalizada en Google Analytics

Google Analytics tiene una herramienta potente para crear segmentación a nivel de usuario llamada dimensiones personalizadas. Los valores de las dimensiones personalizadas se envían desde dispositivos móviles y los reportes se generan en función de estas dimensiones, desde tu dashboard de Google Analytics.

### Paso 1: Defínelo en Google Analytics

1. Selecciona tu aplicación en el menú de GA
2. Selecciona ***Admin*** en la barra superior del dashboard de GA
3. En la columna ***PROPERTY***, selecciona ***Custom Definition***
4. Selecciona ***Dimensiones personalizadas***
   ![Opción de dimensiones personalizadas en el panel de administración de Google Analytics](https://files.readme.io/e475ad1eda5b6338825b712e6c8254f245d5339f50ae40e723f465207e124262-4413121542033.png)
5. Crea una nueva dimensión. Llámala **AppsFlyer Media Source** y asegúrate de seleccionar el alcance ***Usuario***. Esto garantiza que los datos se guarden durante varias sesiones. ![ga2.png](https://files.readme.io/b2d85fd068e5523265a2b49b4218234fc77d5896ad41801cbe0e017752763cf2-4413121449873.png)

   Cada dimensión se crea con un índice que debes recordar para poder usarlo más adelante en la API de GA desde tu aplicación. En este ejemplo, el índice de la nueva dimensión es 10.

   ![ga3](https://files.readme.io/6efc2249ede92291a2aadd16eccbc5b38b580723c6277e3746bdd467de29764a-11179413394193.png)

   Repite este paso y crea otra dimensión y llámala **Campaña de AppsFlyer**

### Paso 2: Configurar y enviar los datos desde la aplicación

Primero, debes obtener el valor de la fuente de medios desde el SDK de AppsFlyer. Puedes hacerlo con el método `onConversionDataSuccess`.

**Nota:** A partir del SDK V5, `onConversionDataSuccess` es el nombre del método para obtener datos de conversión. Si estás utilizando una versión del SDK inferior a 5.0.0, el nombre del método es `onInstallConversionDataLoaded` en Android y `onConversionDataReceived` en iOS. Recomendamos que actualices al SDK 5.0.0. Para aprender más, haz clic <Anchor target="_blank" href="/marketers/es/docs/links-to-appsflyer-sdk-release-notes">aquí</Anchor>.

A continuación, puedes establecer la fuente de medios como dimensión personalizada mediante el SDK de Google Analytics. Consulta los siguientes ejemplos de código para ver cómo hacerlo:

<Tabs>
<Tab title="Android">

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

<Tab title="apps de iOS,">

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

### Paso 3: Ver los resultados en Google Analytics

La mayoría de los reportes de GA tienen una opción para profundizar llamada ***Dimensiones personalizadas***. Puedes seleccionar las dimensiones ***Fuente de medios de AppsFlyer*** o ***Campaña de AppsFlyer*** ([configuradas en el paso 1](/docs/google-analytics-integration-custom-dimensions#paso-1-defínelo-en-google-analytics)) para ver qué fuentes de medios y campañas atraen a los usuarios que instalan tu app.

![G_analytics1.png](https://files.readme.io/dde9219a7a8eec5c861b5031ad741ff7377d85ba9c3693bcbc455fd735f8af2d-4413121449617.png)

<div data-zendesk-anchors="custom-dimensions-on-google-analytics=dimensiones-personalizadas-en-google-analytics h_01HDP3FHGNR06EV1KS8F1PFQ09=dimensiones-personalizadas-en-google-analytics setting-media-source-as-a-custom-dimension-on-google-analytics=configurar-la-fuente-de-medios-como-una-dimensi%C3%B3n-personalizada-en-google-analytics h_01HDP3FHGP9H18VJKNSR27HXEZ=configurar-la-fuente-de-medios-como-una-dimensi%C3%B3n-personalizada-en-google-analytics step-1-define-it-on-google-analytics=paso-1-def%C3%ADnelo-en-google-analytics h_01HDP3FHGPTJ4EVYPDA7RWPJF9=paso-1-def%C3%ADnelo-en-google-analytics step-2-setting-and-sending-the-data-from-the-app=paso-2-configurar-y-enviar-los-datos-desde-la-aplicaci%C3%B3n h_01HDP3FHGPF3BJZSG6G0QP5T1R=paso-2-configurar-y-enviar-los-datos-desde-la-aplicaci%C3%B3n step-3-see-the-results-in-google-analytics=paso-3-ver-los-resultados-en-google-analytics h_01HDP3FHGP9G9BP956KM4ACDRC=paso-3-ver-los-resultados-en-google-analytics" />
