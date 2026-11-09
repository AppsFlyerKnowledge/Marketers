---
title: Integración de Kahuna con AppsFlyer
metadata:
  keywords:
    - kahuna
    - Advertisers
    - Ad Networks
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
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-08-12T11:59:02Z'
  id: 212561966
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/212561966
---
> **Descripción general:** Kahuna, partner integrado de AppsFlyer, se dedica a ayudar a las empresas a crecer y prosperar en la era móvil. Permitimos un nuevo nivel de engagement auténtico entre las marcas y sus clientes, estén donde estén —la web, el correo electrónico, el móvil y los canales sociales—, mediante una comunicación personalizada a escala. Con el respaldo de big data y aprendizaje automático, ayudamos a crear experiencias excelentes para cada cliente con el mensaje perfecto, entregado en el canal adecuado y en el momento preciso.

<div id="important" />

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

Siga las instrucciones a continuación para configurar la integración con Kahuna:

1. Requisitos mínimos - SDK de AppsFlyer:

* Android – versión 2.3.1.18 y posteriores
* iOS – versión 3.3.3 y posteriores

2. La integración con Kahuna requiere que el <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/deviceid/">ID de dispositivo</Anchor> de Kahuna (identificador de usuario único de Kahuna) se complete en el SDK de AppsFlyer. Este parámetro se envía con cada postback y permite la identificación de cada usuario. Para realizar esto debes insertar las siguientes cadenas en el código de tu aplicación:

<div id="important-note" />

> 📘 **Nota Importante**
>
> Asegúrate de que las líneas de código se inserten en el lugar correcto: después de que se inicie el SDK de Kahuna y antes de que se llamen a los métodos appsflyer.sendtracking (Android) / trackAppLaunch (iOS).

<Tabs>
<Tab title="Para Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="Para iOS">

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```

</Tab>
</Tabs>

<div id="setting-up-kahuna" />

## Configuración de Kahuna

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Configurar la integración de ASA**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Kahuna solo utiliza la pestaña ***Integration***.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Clave secreta de Kahuna, staging y production**

Kahuna se conecta con AppsFlyer mediante una clave secreta única. Si aún no la tienes, debes obtenerla de Kahuna para continuar con la integración o seguir los pasos que se indican a continuación. [![](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)

<div id="obtaining-the-kahuna-secret-key" />

### Obtener la clave secreta de Kahuna

1. Accede a tu cuenta de Kahuna

2. Haz clic en el icono de usuario y selecciona **Settings** en la esquina superior derecha del menú del Dashboard

<Image align="center" alt="" src="https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png" />

3. Copia la clave secreta de Kahuna:

<Image align="center" alt="" src="https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png" />

4. Selecciona **APIs & Integrations**– en esta página puedes encontrar los parámetros:

* Introduce la clave maestra de Kahuna obtenida de la consola de Kahuna (consulta la sección 3)
* Si quieres enviar los eventos al entorno Sandbox de Kahuna, introduce la letra S en el campo Staging (consulta «Pruebas con el Sandbox de Kahuna»)
* Para el entorno de producción, introduce la letra P en el campo Production
* Si insertas ambos, los eventos se envían a producción
* Haz clic en **Save**

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Kahuna. Usa esta sección para definir el envío de estos postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks a Kahuna de cualquier usuario que descargue la aplicación.

Haga clic en **Guardar**.

Una vez que hayas guardado la configuración, AppsFlyer envía los siguientes datos a Kahuna para cada instalación orgánica y no orgánica:

* Kahuna Dev\_ID
* Fuente de medios
* Código de país
* Versión del sistema operativo

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Kahuna.

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

Los permisos no están disponibles para Kahuna.

</Accordion>

<div id="view-user-attribution-data-in-kahuna" />

## Ver los datos de atribución de usuarios en Kahuna

Los eventos de instalación se pueden ver como Newbies en el Dashboard principal de Kahuna.

<Image align="center" alt="" src="https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png" />

Puedes buscar un usuario concreto o ir a «Top People» en la navegación lateral izquierda.

<Image align="center" alt="" src="https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png" />

Al seleccionar uno de los usuarios, se abre el Mini Profile, donde puedes ver el evento de instalación «af\_install» en la sección «Top Events»:

<Image align="center" alt="" src="https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png" />

<div id="testing-with-sandbox" />

## Pruebas en sandbox

Si todavía no has lanzado tu aplicación a la tienda de aplicaciones y quieres probar la integración desde el entorno Sandbox de Kahuna, sigue estos pasos:

1. Asegúrate de introducir «s» en el cuadro de texto Staging al configurar Kahuna en AppsFlyer

<Image align="center" alt="" src="https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png" />

2. Asegúrate de haber añadido el código a tu aplicación para integrar los SDK de AppsFlyer y Kahuna, tal como se describe en las secciones anteriores

3. Debes obtener el Advertising ID de tu dispositivo de prueba (puedes encontrar el Advertising ID instalando la aplicación en tu dispositivo y consultando los registros)

4. Pide a AppsFlyer que ponga tu Advertising ID en la allowlist

5. Desinstala la App de tu dispositivo

6. Configura esta URL con tus datos (nombre del paquete de la aplicación, Advertising ID y nombre de la campaña... no incluyas los corchetes) - [https://app.appsflyer.com/[APP PACKAGE NAME]?pid=[SOMETHING]&advertising\_id=](https://app.appsflyer.com/com.dailylabs.kahunatest?pid=Testing_Installs&advertising_id=0eea1488-3037-44b2-a944-11f8bfc3e479)[DEVICE’S ADVERTISING ID]

7. Ve a esa URL; puede que veas esto:

<Image align="center" alt="" src="https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png" width="486px" />

8. Instala la aplicación en tu dispositivo

9. Ve al Dashboard de Kahuna y busca al usuario (puedes activar la depuración de Kahuna y consultar los registros para obtener el ID de dispositivo único de Kahuna de ese usuario.. «dev\_id»... o, si tu aplicación requiere iniciar sesión y pasas las credenciales a Kahuna, también puedes buscar por esas credenciales). Una vez que encuentres al usuario, deberías ver un evento «af\_install» para ese usuario.

<Image align="center" alt="" src="https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png" width="629px" />

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=importante h_01H9FKAF22W59PMYJRFW8HKBQ7=nota-importante setting-up-kahuna=configuraci%C3%B3n-de-kahuna h_01H9FKAF222ES9240V0THQQ5X0=configuraci%C3%B3n-de-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=activar-socio h_01H9FKAF22EFF1F8D2QR1F38PV=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FKAF221EXQYBJGS8GFRF4S=configuraci%C3%B3n-general obtaining-the-kahuna-secret-key=obtener-la-clave-secreta-de-kahuna h_01H9FKAF22XMJW7A89MBD0J276=obtener-la-clave-secreta-de-kahuna default-postbacks=postbacks-predeterminados h_01H9FKAF2258JVR3XS6P7TT8H3=postbacks-predeterminados h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab view-user-attribution-data-in-kahuna=ver-los-datos-de-atribuci%C3%B3n-de-usuarios-en-kahuna h_01H9FKAF22A5910NXRFDGC1JTG=ver-los-datos-de-atribuci%C3%B3n-de-usuarios-en-kahuna testing-with-sandbox=pruebas-en-sandbox h_01H9FKAF22KW2J6H2B6F9AMDP9=pruebas-en-sandbox" />
