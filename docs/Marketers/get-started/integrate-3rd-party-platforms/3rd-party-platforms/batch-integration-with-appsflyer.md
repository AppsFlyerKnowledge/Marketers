---
title: Integración de Batch con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Batch
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
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-08-22T00:10:49Z'
  id: 360000833437
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360000833437
---
> **At a glance:** Batch, un partner integrado de AppsFlyer, es una plataforma de análisis de aplicaciones, automatización de marketing y CRM móvil.

Batch permite a los anunciantes maximizar el engagement de los usuarios y, al mismo tiempo, ofrecer una experiencia de usuario personalizada. La plataforma avanzada de engagement de usuarios de Batch te permite comunicarte de una forma más personalizada con los usuarios de tu smartphone, reducir la pérdida de usuarios y aumentar el ROI de tu aplicación. AppsFlyer y Batch juntos pueden ayudar al anunciante a personalizar aún más la experiencia y el engagement de los usuarios en función del viaje del usuario. Esto significa que el anunciante puede enviar mensajes in-app específicos y notificaciones push en función de datos de atribución, como la fuente de medios y la campaña. Integrar Batch y AppsFlyer es sencillo y fácil.

> 🚧 **Important**
>
> **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="integrating-batch-and-appsflyer" />

## Integración de Batch con AppsFlyer

<div id="setting-customer-user-id" />

### Configuración del ID de usuario de cliente

Para que Batch pueda hacer coincidir los datos de AppsFlyer con sus propios datos, el anunciante debe proporcionar el mismo <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario de cliente</Anchor> en ambos. El ID de usuario de cliente se configura en el SDK.

Es importante que introduzcas un ID de usuario de cliente real y no un valor de marcador de posición. Un ID de usuario de cliente real es un ID de usuario que utilizas para identificar a tus clientes en tus propios sistemas.

<Tabs>
<Tab title="Android">

#### Batch

Establece el ID de usuario del cliente en el SDK de Batch.

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer

Establece el ID de usuario del cliente en el SDK de AppsFlyer.

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="apps de iOS,">

<Tabs>
<Tab title="Objective C">

#### Batch

Configura el ID de usuario de cliente en el SDK de Batch.

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer

Configura el ID de usuario de cliente en el SDK de AppsFlyer.

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### Batch

Configura el ID de usuario de cliente en el SDK de Batch.

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer

Define el ID de usuario del cliente en el SDK de AppsFlyer.

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>

<div id="setting-up-batch" />

### Configuración de Batch

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Configurar la integración de ASA**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La configuración de Batch solo requiere la pestaña **Integración**. Las otras cuatro pestañas están inactivas, ya que no son necesarias en esta integración.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, tendrás que activar el botón **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

Antes de configurar la integración con Batch, asegúrate de obtener tu **Batch Rest API Key** y tu **Batch API Key**. Si no estás seguro, [ponte en contacto con Batch](mailto:hello@batch.com) para obtener más información.  

Una vez que obtengas las dos claves, introduce cada una en el campo correspondiente. En **General Settings**, introduce tu **Batch Rest API Key** en el campo **BATCH\_REST\_API\_KEY** y tu **Batch API Key** en el campo **BATCH\_API\_KEY**.

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

<div id="default-postbacks" />

### Postbacks predeterminados

En **Default Postbacks**, en la lista desplegable **Sending Option**, selecciona **Events attributed to any partner or organic**.

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

Haz clic en **Guardar** en la esquina inferior derecha de la pantalla.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Batch.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Batch.

</Accordion>

<div id="viewing-appsflyer-data-in-the-batch-dashboard" />

## Ver los datos de AppsFlyer en el dashboard de Batch

Una vez que AppsFlyer empiece a enviar postbacks de instalación a Batch, podrás ver los datos en el dashboard de Batch y empezar a personalizar el engagement de los usuarios según los datos de atribución.

Puedes ver los datos en la pestaña **Userbase** de tu dashboard de Batch.

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="integrating-batch-and-appsflyer=integraci%C3%B3n-de-batch-con-appsflyer h_01H9FK389GXG3CDFPNM5ASKJ3N=integraci%C3%B3n-de-batch-con-appsflyer setting-customer-user-id=configuraci%C3%B3n-del-id-de-usuario-de-cliente h_01H9FK389MPKFN8J74BX1E3MGG=configuraci%C3%B3n-del-id-de-usuario-de-cliente h_01H9FK389MK1HM1460VAT6X82Y=batch h_01H9FK389MPGNEX8B3923KYDB3=appsflyer batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=appsflyer h_01H9FK389M7V83A66M6T9EV8QT=appsflyer batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=appsflyer setting-up-batch-in-appsflyer-dashboard=configuraci%C3%B3n-de-batch h_01H9FK389MCSR5YDSF4RKFDSDZ=configuraci%C3%B3n-de-batch h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01H9FK389M19AVM63DEX5JTTQK=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01H9FK389MN82EKHVGMM9Z6H58=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FK389MXA3DS403VXRRK5NX=postbacks-predeterminados h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=ver-los-datos-de-appsflyer-en-el-dashboard-de-batch h_01H9FK389M8BNRFECN0WG23BCD=ver-los-datos-de-appsflyer-en-el-dashboard-de-batch" />
