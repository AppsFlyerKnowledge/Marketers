---
title: Integración de Adobe Analytics con AppsFlyer
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
  edited_at: '2026-09-24T00:11:03Z'
  id: 115003326706
  locale: es
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/es/articles/115003326706
---
> **De un vistazo:** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (anteriormente Omniture) es un conjunto de herramientas para el análisis predictivo y en tiempo real que se puede integrar en fuentes de terceros. Incluye las aplicaciones de reportes y análisis de marketing (SiteCatalyst), análisis ad hoc (Adobe Discover) e Insight para ayudar a crear una visión holística de las actividades empresariales al transformar las interacciones con los clientes en información.

## Descripción general

Esta integración consiste en un flujo de datos bidireccional entre Adobe y AppsFlyer. Para que la integración sea exitosa, esta integración requiere la implementación de código en la aplicación. Se deben cumplir los requisitos de AppsFlyer y Adobe para que la integración sea completamente exitosa.

## Configuración de la integración de Adobe Analytics

Si utilizas Adobe Analytics Report Suite para el análisis general del rendimiento de la campaña y la creación de segmentos, la integración de AppsFlyer con Adobe Analytics permite la transferencia automática de datos de atribución de AppsFlyer a Adobe para ayudarte a alcanzar tus objetivos.

### Requisitos previos:

* Configuración <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">de los documentos del SDK móvil de Adobe Experience Platform</Anchor>
* <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/home">ID de visitante de Marketing Cloud</Anchor> o servicio de ID de Experience Cloud
* Tres eVars en cada grupo de reportes que se pueden usar con el único propósito de esta integración

### Paso 1: Comparte el ID de Adobe Experience Cloud (ECID, ID de Marketing Cloud o ID de visitante) con AppsFlyer.

Para extraer y compartir el ID de Adobe Experience Cloud:

1. <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid">Actualiza la aplicación y extrae el ID de visitante de Marketing Cloud</Anchor> con el método del SDK de Adobe justo después de inicializar el SDK de Adobe.
2. Usa uno de los siguientes métodos del SDK de AppsFlyer para configurar el ID de visitante de Adobe Marketing Cloud:

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="Android">

Aprender más sobre [el método setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

Aprender más sobre [el método setAdditionalData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata).

Objective C

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

Aprender más sobre [el método setAdditionalData](https://dev.appsflyer.com/hc/docs/api#setadditionaldata).

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap. Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="setCustomerUserId">

<Tabs>
<Tab title="Android">

Aprender más sobre <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">el</Anchor> método <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor>.

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

Aprender más sobre <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">el método setCustomerUserId</Anchor>.

Objective C

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

### Paso 2: Configurar Adobe analytic en AppsFlyer

**Requisito previo:** Antes de configurar la integración, asegúrate de [pasar el ID de visitante de Adobe Marketing Cloud al SDK de AppsFlyer](/docs/adobe-analytics-integration-with-appsflyer#paso-1-comparte-el-id-de-adobe-experience-cloud-ecid-id-de-marketing-cloud-o-id-de-visitante-con-appsflyer).

**Para activar o editar la integración:**

1. En la pestaña  **Integración** , selecciona la aplicación para la integración y activa  **Activar socio** .  
   **Nota:** El selector debe estar activado  <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activated)</Anchor> mientras trabajes con el partner.
2. Busca **Adobe Analytics** y selecciónelo.
3. Haz clic en  **Configurar integración**. Serás redirigido a la página de configuración de integración.
4. **Para editar**: en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas.Nota:** El selector debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.
5. Configura los postbacks predeterminados enviados a Adobe Analytics. AppsFlyer puede enviar postbacks automáticos tanto para instalaciones como para re-engagements (incluidas las reatribuciones). Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">los postbacks predeterminados</Anchor>.
6. Desde el <strong>SDK de Adobe Analytics</strong>, como parte del archivo <strong>ADBMobileConfig.XML</strong>, copia el <strong>Report\_Suite\_ID (resaltado en azul) y el</strong> Adobe\_Analytic\_Server\_URL (resaltado en verde) y pégalos en los campos correspondientes de la página de integración de Adobe Analytics en AppsFlyer.

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
7. Haz clic en **Guardar integración**.

Una vez guardados, AppsFlyer envía los siguientes datos a Adobe Analytics para cada instalación orgánica y no orgánica:

* ID de Adobe (MCVID)
* ID del grupo de reportes y URL del servidor
* ID del dispositivo del cliente
* Fuente de medios
* Nombre de la campaña

> 📘 **Nota:**
>
> De acuerdo con los términos de servicio de Anuncios de Meta y X Ads, AppsFlyer tiene prohibido compartir datos a nivel de usuario con terceros. Esto significa que las instalaciones de Anuncios de Meta y X Ads se envían como orgánicas.

### Paso 3: Asigna datos a eVars en Adobe Analytics

Debido a la obsolescencia de los conectores de datos de Adobe Analytics, tendrás que aprovechar las reglas de procesamiento para asignar variables de contexto a las eVars.

Aprender más sobre [cómo usar las reglas de procesamiento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en).

Por lo tanto, las variables de datos de contexto de AppsFlyer se asignaron:

* MobileAdCampaign (datos de contexto)
* MobileAdNetwork (datos de contexto)
* MobileAdProvider (datos de contexto)

Si tienes problemas para asignar variables de datos de contexto de AppsFlyer mediante reglas de procesamiento, ponte en contacto con tu equipo de cuentas de Adobe para obtener más ayuda.

### Paso 4 [opcional]: Configura tu canal de marketing

Consulta la <Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">documentación de Adobe Analytics</Anchor> sobre cómo configurar tu canal de marketing en su plataforma. Asegúrate de seleccionar los siguientes campos en las reglas de identificación:

1. «El valor de la variable de conversión establecido por la baliza web de Adobe»: Selecciona **AppsFlyer** y **Exists**.
2. «Identificar el canal como»: Selecciona **Atribución de aplicaciones móviles**.
3. «Establece el valor del canal en:» Selecciona Campaña de **AppsFlyer**.

## Detalles de dominio y seguridad

A continuación se detallan los problemas de dominio y seguridad:

1. ANALYTIC\_SERVER\_DOMAIN se encuentra como la variable de servidor en el archivo de configuración de la aplicación. Puedes seleccionar cualquier dominio para el análisis de atribución. En general, se utilizan dominios estándar para el servicio de colecciones de Adobe Analytics, como sc.omtrdc.net. Puedes encontrarlo en la configuración de análisis (servidor) de su archivo **ADBMobobile.config**.
2. El protocolo (HTTP/HTTPS) de la URL depende de si el dominio del servidor ANALYTIC es seguro o no. Es importante que utilices el protocolo correcto. Para saber si la configuración es segura, comprueba si la configuración de Analytics (SSL) está establecida en **true** en el archivo **ADBMobobile.config**. Si tu conexión es segura, utiliza HTTPS, si no es segura, utiliza HTTP.
3. El ID de REPORT SUITE se encuentra como la variable **rsids** en el archivo de configuración de las aplicaciones. Puedes asignar cualquier nombre a tu grupo de reportes.
4. El ts= `{timestamp}` solo se usa si la configuración **OfflineEnabled** es verdadera en el archivo de configuración. Elimina este parámetro de la URL si **OfflineEnabled** está establecido en False o si tu grupo de reportes no tiene habilitada la **marca de tiempo**.

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=descripci%C3%B3n-general setting-up-adobe-analytics-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-adobe-analytics h_01HA4ZWDM11RJ6GRJ7W8QMFACT=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-adobe-analytics prerequisite=requisitos-previos h_01HA4ZWDM1YK58Q56Y0S8PC1E2=requisitos-previos step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=paso-1-comparte-el-id-de-adobe-experience-cloud-ecid-id-de-marketing-cloud-o-id-de-visitante-con-appsflyer h_01HA4ZWDM1J65D32PVXY0ZD9YV=paso-1-comparte-el-id-de-adobe-experience-cloud-ecid-id-de-marketing-cloud-o-id-de-visitante-con-appsflyer h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=paso-2-configurar-adobe-analytic-en-appsflyer h_01HA4ZWDM26AVEQKC4CXF18D22=paso-2-configurar-adobe-analytic-en-appsflyer h_01HA4ZWDM23A6BFXDV2JH4NR2J=nota step-3-map-data-to-evars-in-adobe-analytics=paso-3-asigna-datos-a-evars-en-adobe-analytics h_01HA4ZWDM27S52KY36GS1QPKJ5=paso-3-asigna-datos-a-evars-en-adobe-analytics step-4-%5Boptional%5D-set-up-your-marketing-channel=paso-4-opcional-configura-tu-canal-de-marketing h_01HA4ZX6FG6RM5JNDKQP6GVAD1=paso-4-opcional-configura-tu-canal-de-marketing domain-and-security-details=detalles-de-dominio-y-seguridad h_01HA4ZWDM2NNFVPP1XYWKPS89A=detalles-de-dominio-y-seguridad" />
