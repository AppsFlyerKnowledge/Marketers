---
title: Integración de OneSignal con AppsFlyer
metadata:
  keywords:
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
  created_at: '2020-11-29T08:11:41Z'
  edited_at: '2026-08-22T00:11:46Z'
  id: 360015926437
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360015926437
---
> **At a glance:** OneSignal es el proveedor líder del mercado de notificaciones push y mensajes in-app, y presta soporte a más de 1 millón de desarrolladores y profesionales del marketing con una plataforma de engagement de primer nivel.

![onesignal-logo-stack__3_.png](https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png)

OneSignal envía 8 billion mensajes cada día en todo el mundo. Impulsado por una arquitectura superior y una plataforma fácil de usar, OneSignal envía mensajes más rápido, de forma más eficiente y a mayor escala que cualquier otra solución del mundo. Más información en [onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)

> 🚧 **Important**
>
> **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-onesignal" />

## Configuración de OneSignal

La integración con OneSignal incluye insertar unas pocas líneas de código en el SDK de AppsFlyer de tu app y, después, activar la integración en AppsFlyer.

<div id="set-up-the-appsflyer-sdk" />

### Configurar el SDK de AppsFlyer

Al usar Android, la integración con OneSignal requiere que el OneSignal Player ID (identificador de usuario único de OneSignal) se complete en el SDK de Android de AppsFlyer. Este parámetro se envía con cada postback y permite la identificación de cada usuario.

**Para configurar el SDK de AppsFlyer para Android:**

1. Asegúrate de que la versión del SDK que usas sea la 2.3.1.18 o posterior.
2. Inserta las siguientes líneas de código en el código de tu app, [después de iniciar el SDK de OneSignal](https://documentation.onesignal.com/docs/android-sdk-setup) y antes del código de inicialización del SDK de AppsFlyer.
   * Para dispositivos Android que usan la versión 3.x.x del SDK de OneSignal:

     ```http
     OSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

               String deviceId = status.getSubscriptionStatus().getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Para el SDK de Unity:

     ```http
     var status = OneSignal.GetPermissionSubscriptionState();

               String deviceId = status.subscriptionStatus.userId;

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Para dispositivos Android que usan la versión 4+ del SDK nativo de OneSignal:

     ```http
     OSDeviceState device = OneSignal.getDeviceState();

               String deviceId = device.getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```

**Para configurar el SDK de AppsFlyer para iOS:**

1. Asegúrate de que la versión del SDK que usas sea la 2.3.1.18 o posterior.
2. Inserta las siguientes líneas de código en el código de tu app, [después de iniciar el SDK de OneSignal](https://documentation.onesignal.com/docs/android-sdk-setup) y antes del código de inicialización del SDK de AppsFlyer.
   * Para dispositivos iOS que usan la versión 2.x.x del SDK de OneSignal:

     <Tabs>
     <Tab title="Swift">

     ```http
     let status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
     if let deviceId = status.subscriptionStatus.userId{
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```http
     OSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState];
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

   * Para dispositivos iOS que usan OneSignal Native SDK versión 3+:

     <Tabs>
     <Tab title="Swift">

     ```http
     if let deviceState = OneSignal.getDeviceState() {
         let deviceId = deviceState.userId
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective-C">

     ```http
     OSDeviceState *deviceState = [OneSignal getDeviceState];
     NSString *deviceId = deviceState.userId;
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Configurar la integración de ASA**

1. **Para activar:** En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editar:** En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Selecciona la aplicación correspondiente.
3. Busca al partner (`rokuads_int`) y selecciónalo.
4. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner. **Nota:** El selector debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajes con el partner. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación:

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

![onesignal-integration-tab.png](https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png)

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

Debe estar activado mientras trabajes con el partner.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación del partner</Anchor>.

<div id="general-settings" />

### Configuración general

#### OneSignal AppID

Para conectar tu cuenta de OneSignal con AppsFlyer, introduce el ID de tu app en el campo **OneSignal AppID**.  
El ID de la aplicación de OneSignal está disponible en la plataforma de OneSignal, en **Settings** > **Keys & IDs**.

![onesignal-app-id-es_es.png](https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png)

<div id="default-postbacks" />

### Postbacks predeterminados

![onesignal-default-postbacks_es-es.png](https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png)

AppsFlyer puede enviar postbacks automáticos a OneSignal tras las instalaciones de los usuarios. Utiliza esta sección para definir la fuente de los usuarios a los cuales se envían los postbacks de cada evento.  
Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks por defecto</Anchor>.

**Para enviar postbacks de cualquier usuario que descargue la aplicación a OneSignal**, selecciona **Todas las fuentes de medios, incluidas las orgánicas**.

**Para completar la configuración de la integración,** haz clic en **Guardar integración**.

Aunque AppsFlyer envía todos los eventos, OneSignal no cuenta las instalaciones orgánicas y, por lo tanto, OneSignal API las ignora.

Una vez que hayas guardado la configuración, AppsFlyer envía los siguientes datos a OneSignal para cada instalación orgánica y no orgánica:

* Nombre de la app
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
* ID de dispositivos
* Retargeting: Primer inicio después del re-engagement o la reatribución.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costo no son aplicables en la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no son aplicables en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para este partner.

</Accordion>

<div id="view-user-attribution-data-in-onesignal" />

## Ver datos de atribución de usuarios en OneSignal

Puedes ver la atribución en el Editor de segmentos, en las etiquetas de OneSignal, ya sea a nivel de dispositivo individual o al crear un segmento para usarlo en una campaña.

![onesignal-view-attribution_es-es.png](https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png)

<div data-zendesk-anchors="setting-up-onesignal=configuraci%C3%B3n-de-onesignal h_01H9HWJTEYDEZ8AGVQBHZZTP7K=configuraci%C3%B3n-de-onesignal set-up-the-appsflyer-sdk=configurar-el-sdk-de-appsflyer h_01H9HWJTEY71PTXR1YSAK709QT=configurar-el-sdk-de-appsflyer h_01H9HWJTEZC62F9JW1KD4Y1CYS=integration-tab activate-partner=activar-socio h_01H9HWJTEZH60AEPE7AB43X4YG=activar-socio general-settings=configuraci%C3%B3n-general h_01H9HWJTEZJAK2PTF4HQP3DQ1X=configuraci%C3%B3n-general h_01H9HWJTEZCNZX17K86H9KCRFN=onesignal-appid default-postbacks=postbacks-predeterminados h_01H9HWJTEZ91KR3ZA8NX5BVZCF=postbacks-predeterminados h_01H9HWJTEZZYRBS6PPRBBQAXZ5=attribution-link-tab h_01H9HWJTEZNT0EHJ7G4SFRD8K5=cost-tab h_01H9HWJTEZS7TN4FCAN40QB1NT=ad-revenue-tab h_01H9HWJTEZEY5VKCKDZ1Q7APRG=permissions-tab view-user-attribution-data-in-onesignal=ver-datos-de-atribuci%C3%B3n-de-usuarios-en-onesignal h_01H9HWJTEZZTJFTZC1Z2A6F5QM=ver-datos-de-atribuci%C3%B3n-de-usuarios-en-onesignal" />
