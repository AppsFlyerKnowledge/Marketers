---
title: Integración de Salesforce Marketing Cloud (SFMC) con AppsFlyer
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T14:53:41Z'
  edited_at: '2026-10-23T01:27:37Z'
  id: 50431751712529
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/50431751712529
---
> **At a glance:** Integra AppsFlyer con Salesforce Marketing Cloud (SFMC) para usar Deep Linking y dirigir a los usuarios desde campañas de correo electrónico hasta contenido in-app. Sincroniza los datos de eventos in-app en SFMC para crear audiencias y activar viajes en función del comportamiento real de la aplicación.

<div id="about-the-integration" />

## Sobre la integración

SFMC te permite volver a interactuar con los usuarios existentes mediante campañas de correo electrónico, usando Deep Linking para dirigirlos a contenido in-app específico, como una promoción o una oferta personalizada.

Hay dos opciones de integración:

* **Deep Linking estándar de correo electrónico de SFMC**: crea los enlaces OneLink de tu campaña en AppsFlyer y luego añádelos a tus correos electrónicos.
* **Integración avanzada con AppExchange de SFMC**: crea enlaces OneLink de campaña directamente en Salesforce e importa automáticamente datos de eventos in-app para poder crear audiencias de re-engagement. Esta es una función premium.

<div id="comparison-standard-vs-advanced" />

## Comparación: Standard vs. Advanced

| Capacidad | Deep Linking estándar de correo electrónico de SFMC | Integración avanzada con AppExchange de SFMC |
| --- | --- | --- |
| Deferred deep links | Sí | Sí |
| Enlaces directos | Sí | Sí |
| Medición de Deep Linking | Sí | Sí |
| Creación de enlaces | En AppsFlyer | En la aplicación de Salesforce dedicada |
| Postbacks de SFMC (sincronización de eventos in-app) | No | Sí |

<div id="prerequisites" />

## Prerrequisitos

<Tabs>
<Tab title="apps de iOS,">

* SDK de AppsFlyer para iOS, versión 4.9.0+
* Para los enlaces universales de iOS, haz lo siguiente en tu entorno de SFMC: compra e implementa un <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_sender_authentication_package.htm&type=5">Sender Authentication Package</Anchor> (SAP) y compra un certificado SSL (configuración de SSL) y envía un formulario de solicitud de SSL. Ponte en contacto con tu representante de cuenta de Salesforce o envía un Caso de soporte de entregabilidad a través de Salesforce ayuda para obtener ambos.

</Tab>

<Tab title="Android">

* SDK de AppsFlyer para Android, versión 4.9.0+
* SFMC no admite Android App Links, así que en su lugar se usa Deep Linking con <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI Scheme</Anchor>. No se requiere ninguna acción especial para soporte de Deep Linking en apps Android desde SFMC.

</Tab>
</Tabs>

<div id="set-up-standard-sfmc-email-deep-linking" />

## Configura Deep Linking estándar de correo electrónico de SFMC

**Configura la integración:**

<Accordion title="Paso 1: Configura tu dominio de registro de clics en SFMC">

Para configurar un dominio de registro de clics, sigue las guías oficiales de SFMC para:

* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_implement_ios_universal_link.htm&type=5">Implementación de enlaces universales de iOS</Anchor>
* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_dns_record_maintenance.htm&type=5">Mantenimiento de registros DNS</Anchor>

</Accordion>

<Accordion title="Paso 2: Carga tu certificado SSL en SFMC">

Para que los enlaces universales de iOS funcionen correctamente, tu dominio de registro de clics debe incluir el certificado SSL de tu dominio, que debe estar instalado en tu cuenta de SFMC. Encontrarás instrucciones para configurar tus certificados SSL en la <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_ssl_certificates.htm&type=5">guía oficial de SFMC</Anchor>.

</Accordion>

<Accordion title="Paso 3: Configura el deep linking en SFMC">

Para habilitar el enlace profundo desde los correos electrónicos de SFMC:

1. Inicia sesión en tu cuenta de SFMC y ve a la vista **Email Studio**
2. Haz clic en la pestaña **Administrar**
3. En el menú lateral, haz clic en **Deep Linking**. En esta vista, puedes configurar nuevas integraciones de enlaces profundos con tu aplicación, o modificar las existentes.

   <Image align="center" alt="[SE NECESITA TEXTO ALT: describe la pantalla de configuración de Deep Linking de SFMC]" src="https://files.readme.io/4b7e68abb76163329ab5d487425c4dfe3ee903bb3360893c9b59f40f73486858-50431735587345.png" width="3348px" />
4. Para crear una nueva configuración, haz clic en el botón **Crear** e introduce tu AppID. El valor AppID es una combinación de tu ID de equipo de desarrollador de Apple y el ID de paquete. Ambos valores pueden recuperarse desde tu cuenta de desarrollador de Apple.

   <div id="example" />

   > 📄 **Ejemplo**
   >
   > Dado el prefijo de ID de equipo *5UABCDFGH* y el ID de paquete *com.your.app*, debe introducirse el siguiente valor:  
   > 5UABCDFGH.com.your.app
   >
   > <Image align="center" alt="[SE NECESITA TEXTO ALT: describe la pantalla de configuración de Deep Linking de SFMC que se muestra aquí]" src="https://files.readme.io/4f5500c6f538b2b8e00db0bae1bcac240fc49b30419f4f4a8b07fb0bd3cf8f4a-50431735587985.png" width="1234px" />

5. La configuración de enlaces universales y enlaces profundos se completa una vez que SFMC configura el archivo Apple App Site Association (AASA). Este proceso puede durar unas horas. Puedes ver el archivo generado utilizando la siguiente URL:

   ```
   https://<click_recording_link_domain>/apple-app-site-association
   ```

</Accordion>

<Accordion title="Paso 4: Configura tu SDK de AppsFlyer">

> 📘 **Nota:**
>
> Si aún no lo has hecho, asegúrate de configurar tu aplicación para que admita <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Linking con OneLink</Anchor>.

Después de configurar tu dominio de registro de clics para que admita enlaces universales como se ha descrito anteriormente, debes configurar su aplicación para que establezca enlaces profundos y resuelva el enlace universal.

1. Asociar el dominio de registro de clics en Xcode:

   <Image align="center" alt="[SE NECESITA TEXTO ALT: describe la pantalla de dominios asociados de Xcode]" src="https://files.readme.io/02bee3d75c32d494d80719b2718ddf4648440bcb3ebcb2132799e44e38852629-50431735589009.png" width="1135px" />
2. Proporciona el dominio de registro de clics a la API del SDK `setResolveDeepLinkURLs`. Esta API debe llamarse antes de la inicialización del SDK. Para obtener más información, consulta la documentación del SDK sobre <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">la resolución de URL de Deep Linking</Anchor>.

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   * **¡Importante!** Si utilizas Movable Ink (MI) junto con Salesforce, debes obtener el CNAME de MI y los dominios internos de tu gestor de cuentas de MI y añadirlos a `setResolveDeepLinkURLs`, además del enlace de clic para Salesforce. Por ejemplo,

     ```swift
     AppsFlyerLib.shared().resolveDeepLinkURLs = ["salesforce-click.example.com", "mi.example.com", "example.micpn.com"]
     ```
3. Cuando se invoca la aplicación debido a un clic en el enlace universal, el SDK de AppsFlyer resuelve el enlace profundo y extrae el OneLink subyacente. A continuación, todos los parámetros de deep link se propagan a la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onappopenattribution">API onAppOpenAttribution</Anchor> para ejecutar la lógica de deep link.

</Accordion>

<div id="send-emails-with-standard-sfmc-email-deep-linking" />

## Envía correos electrónicos con Deep Linking de correo electrónico estándar de SFMC

**Para enviar correos electrónicos con Deep Linking de correo electrónico estándar de SFMC:**

1. Crea un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">enlace de OneLink</Anchor>, ya sea manualmente o desde la página de enlaces de OneLink en el dashboard de AppsFlyer.
2. Codifica en URL todos los valores de los parámetros cuando crees el OneLink. Estos parámetros son muy recomendables:

| Parámetro | Descripción | Notas |
| --- | --- | --- |
| pid | Fuente de medios | Fuente mediática representativa |
| C | Nombre de la campaña | La campaña que se atribuirá |
| af\_dp | URL de enlace profundo | Redireccionamiento de enlaces profundos para los usuarios |
| af\_web\_dp | Redireccionamiento de escritorio | Redireccionamiento para usuarios de ordenadores de mesa |
| af\_ios\_url |  | Redireccionamiento para usuarios de iOS que no tengan instalada la aplicación |
| af\_android\_url |  | Redireccionamiento para usuarios de Android que no tengan instalada la aplicación |

3. Copia el enlace en el correo electrónico que crees en Salesforce Email Studio. Salesforce Marketing Cloud envuelve el enlace con tu dominio de registro de clics, por lo que cualquier clic en ese dominio redirige a tu enlace de atribución de OneLink.

**Ejemplo** (parámetros de URL mostrados sin codificar, para facilitar la lectura):

```
https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
```

<div id="set-up-the-advanced-sfmc-app-exchange-integration" />

## Configura la integración avanzada de intercambio de aplicaciones de SFMC

**Para configurar la integración avanzada de SFMC con AppExchange:**

<Accordion title="Paso 1: Instala la app OneLink desde el SFMC AppExchange">

1. Pide a tu CSM, o escribe a hello@appsflyer.com, que habilite la instalación de la app en SFMC AppExchange.
2. En Salesforce, ve al enlace de AppExchange que comparta tu CSM una vez que la app esté habilitada.
3. Haz clic en **Install**.
4. Concede permisos: pide al administrador de Salesforce Marketing Cloud que conceda acceso a la app a usuarios individuales o unidades de negocio. Puede que necesites hacer una recarga completa para ver los nuevos permisos.
5. Da a los usuarios acceso a la app OneLink de AppsFlyer: ve a **Apps > Installed Packages**, selecciona la pestaña **ACCESS**, selecciona los usuarios que deban poder usar OneLink y haz clic en **Save**. De nuevo, puede que necesites hacer una recarga completa.

</Accordion>

<Accordion title="Paso 2: Completa la configuración básica">

Completa los pasos de «[Configurar el Deep Linking estándar de correo electrónico de SFMC](#configura-deep-linking-estándar-de-correo-electrónico-de-sfmc)» que aparecen arriba.

</Accordion>

<Accordion title="Paso 3: Crea enlaces OneLink en Salesforce con la app OneLink de AppsFlyer">

Crea un enlace de atribución independiente para cada campaña.

<Image align="center" alt="[SE NECESITA TEXTO ALT: actualmente el nombre de archivo es SFMC-AF-app1-en_us.png; describe la pantalla de la app OneLink que se muestra]" src="https://files.readme.io/21d7961d03e822dd2a4ccb426dc7b5c85c3700f81a9530bc8950a67e3f1d6237-50431735591185.png" width="684px" />

**Para crear un enlace de OneLink:**

1. En **Salesforce**, abre la app OneLink de **AppsFlyer**.
2. Haz clic en **Añadir OneLink**.
3. Introduce un nombre en el campo **Nombre del enlace**. Considere:
   * Elige un nombre fácil de identificar.
   * El nombre del enlace se usará al aplicar OneLinks a las campañas de correo electrónico.
4. En el campo **URL base**, introduce la URL OneLink en versión larga que copiaste de la página **Enlaces personalizados de OneLink de AppsFlyer**.
   * Usa una URL en versión larga para asegurarte de que la app analice y establezca los parámetros del enlace.
   * Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">copiar la URL de un enlace existente</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">crear un enlace OneLink nuevo</Anchor>.
5. [Opcional] Para añadir más parámetros, haz clic en **Añadir parámetro**. Consulta la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-del-enlace-de-atribución">lista de parámetros recomendados</Anchor>.
6. [Opcional] Para configurar una macro interna de Salesforce Marketing Cloud, haz clic en el icono situado a la derecha de un parámetro.
   * Se recomienda configurar una **Subscriber key** para cada parámetro de **OneLink**.
   * Esto te permite vincular las conversiones de correo electrónico atribuidas a tus datos de Salesforce.
7. Haz clic en **Generar enlace**.

</Accordion>

<Accordion title="Paso 4: Envía correos electrónicos que contengan enlaces de atribución personalizados">

1. En **Salesforce Email Studio**, crea una nueva plantilla o un nuevo correo electrónico.
2. Haz clic en el icono **Edit**, en la pestaña **Content** y, a continuación, selecciona **Blocks**.
3. Desplázate hacia abajo hasta encontrar **AppsFlyer Button CB** o **AppsFlyer Image CB**.

   <Image align="center" alt="[SE NECESITA TEXTO ALT: describe el panel de bloques de contenido que se muestra actualmente en el archivo sf_email_edit_onelink_new.PNG]" src="https://files.readme.io/565a80933451dbdb1606b20f8d71964019a36f14ffd0b0ba295649a96b056cf0-50431751706641.png" width="396px" />
4. Arrastra la imagen o el botón al cuerpo del correo electrónico.
5. Haz clic en la imagen o el botón para editarlo/la.
6. En el campo **Título**, asigna un nombre a la imagen o al botón.
7. Selecciona un **enlace de OneLink**.

   <Image align="center" alt="[SE NECESITA TEXTO ALT: describe el selector de enlaces de OneLink que se muestra]" src="https://files.readme.io/1d22268b5ced4d753cb6812decdccd960e92d9d8156213f76fc67db98b52c9c7-50431751707665.png" width="415px" />
8. Guarda el correo electrónico y envíalo.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Para facilitar la lectura, los parámetros URL no están codificados:
>
> ```
> https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

</Accordion>

<Accordion title="Paso 5: Prueba tus enlaces">

**Para probar tus enlaces de atribución:**

1. Crea la URL OneLink adecuada.
2. Colócalo en un correo electrónico.
3. Envíate el correo electrónico a ti mismo.
4. Haz clic en el enlace.

* Si tienes la aplicación instalada en tu dispositivo, la aplicación debe ser invocada.
* Si se implementan las API de enlaces profundos relevantes del SDK de AppsFlyer, debes tener un enlace profundo al contenido relevante.
* Debería aparecer un clic tanto en el panel de control de AppsFlyer, atribuido a la fuente de medios proporcionada como a la campaña.
* Aparece un clic en los datos de Salesforce.

</Accordion>

<div id="dynamic-emails" />

## Correos electrónicos dinámicos

Si necesitas generar enlaces dinámicamente para representar contenido dinámico por usuario, usa la API de OneLink.

Para hacerlo, usa una actividad de script de Automation Studio en Journey Builder de SFMC que llame a la API de OneLink antes del envío, escriba el enlace profundo generado en un campo de la Data Extension de envío para cada contacto y, después, haz que el correo electrónico extraiga ese campo con una búsqueda sencilla de AMPscript.

<div id="advanced-sfmc-in-app-events-data-sync" />

## Sincronización avanzada de datos de eventos in-app de SFMC

Esta función permite que AppsFlyer envíe automáticamente datos de eventos in-app desde tu aplicación a Salesforce Marketing Cloud, donde se almacenan en una Data Extension específica. Usa estos datos para crear audiencias, activar viajes y personalizar campañas en función del comportamiento real de la aplicación, como compras, registros o niveles completados.

Esta es una función premium, disponible como parte de la integración avanzada de AppExchange de SFMC.

<div id="how-it-works" />

### Cómo funciona

Cuando un usuario realiza un evento in-app (por ejemplo, al completar una compra), AppsFlyer envía un postback al conector de SFMC. El conector escribe los datos del evento en una Data Extension de tu cuenta de SFMC, donde cada fila representa un evento para un contacto. A partir de ahí, usa Journey Builder o Automation Studio de SFMC para activar comunicaciones de seguimiento en función de ese evento.

**Para configurar la sincronización avanzada de datos:**

<Accordion title="Paso 1: Activa el envío de postback en AppsFlyer">

1. En AppsFlyer, ve a **Colaborar > Integraciones activas** y busca Salesforce Marketing Cloud.
2. Selecciona la aplicación que quieres configurar y haz clic en **Configurar integración**.
3. En la pestaña **Integración**, asegúrate de que el selector **Activar partner** esté activado.
4. Desplázate hasta **Postbacks de eventos in-app** y activa el selector.
5. Haz clic en **Añadir evento** y asigna los eventos de AppsFlyer que quieras enviar a SFMC. Para cada evento, selecciónalo en la lista de eventos de tu aplicación y establece la condición de envío: **Solo este partner** (envía solo los eventos atribuidos al tráfico de SFMC) o **Todas las fuentes de medios, incluido el orgánico** (recomendado para crear audiencias, ya que envía cada ocurrencia del evento independientemente de la atribución).
6. Haz clic en **Guardar integración**.

<div id="note-1" />

> 📘 **Note**
>
> En la lista de eventos solo aparecen los eventos que AppsFlyer ya ha recibido a través de tu SDK o de la integración S2S. Si falta algún evento, primero revisa la implementación del SDK.

</Accordion>

<Accordion title="Paso 2: Verifica la Data Extension en SFMC">

Después de que se envíe el primer postback, AppsFlyer crea automáticamente una Data Extension en tu cuenta de SFMC con el nombre Installs-`{mid} o Events-{mid}`. Para verificarlo:

1. En SFMC, ve a **Email Studio > Data Extensions**.
2. Busca la Data Extension de tu aplicación.
3. Confirma que las filas se estén rellenando con datos de eventos. Cada fila debe incluir el identificador del contacto, el nombre del evento, la marca de tiempo del evento y los parámetros del evento.

Si la Data Extension no se creó automáticamente, confirma que la aplicación del conector de SFMC esté instalada correctamente y que el administrador de SFMC le haya concedido los permisos necesarios para escribir datos.

</Accordion>

<Accordion title="Paso 3: Usa los datos de eventos en Journey Builder">

1. En SFMC, abre Journey Builder y crea o edita un journey.
2. Configura la fuente de entrada como **Data Extension** y selecciona la Data Extension de AppsFlyer de tu aplicación.
3. Configura los criterios de entrada, por ejemplo, contactos cuyo event\_name sea igual a af\_purchase.
4. Crea los pasos del viaje que necesites (enviar correo electrónico, esperar, ramificar por valor de evento, etc.).
5. Activa el viaje.

> 👍 **Tip**
>
> Usa el parámetro af\_sub1 en tus OneLinks para pasar la clave de suscriptor de SFMC como identificador de usuario. Esto permite que los postbacks coincidan con el registro de contacto correcto en Salesforce, lo que habilita la personalización a nivel de contacto en lugar de solo la atribución a nivel de campaña.

</Accordion>

<div id="postback-data-fields" />

### Campos de datos de postback

El conector de SFMC crea dos Data Extensions en tu cuenta: una para instalaciones y otra para eventos in-app. Todos los campos existen en el esquema, pero algunos no se rellenan actualmente. Los campos marcados como "not written" forman parte del esquema, pero siempre estarán vacíos.

<Accordion title="Campos de datos">

**Campos de la Data Extension de instalación (49 campos)**

| Campo | Escrito | Notas |
| --- | --- | --- |
| Tipo de Toque | Sí |  |
| Tiempo de toque | Sí |  |
| eventName | Sí |  |
| Fuente del evento | Sí |  |
| Media Source | Sí |  |
| Channel | Sí |  |
| Campaña | Sí |  |
| Campaign ID | Sí |  |
| Sub Param 1 a 5 | Sí | Se asigna a af\_sub1 hasta af\_sub5 en OneLink |
| Región | Sí |  |
| Código del país | Sí |  |
| State | Sí |  |
| CITY | Sí |  |
| Código postal | Sí |  |
| DMA | Sí |  |
| IP | Sí |  |
| ID de AF | Sí | El identificador único de dispositivo de AppsFlyer |
| IDFV | Sí |  |
| Tipo de dispositivo | Sí |  |
| Categoría del dispositivo | Sí |  |
| Platform | Sí |  |
| Versión OS de la instalación | Sí |  |
| Versión de la aplicación | Sí |  |
| Versión del SDK | Sí |  |
| Identificación de la aplicación | Sí |  |
| App Name | Sí |  |
| Es retargeting | Sí |  |
| Tipo de coincidencia | Sí |  |
| User Agent | Sí |  |
| Hora de la Instalación | Sí |  |
| Event Time | Sí |  |
| Valor de enlace profundo | Sí |  |
| deep\_link\_sub1 a sub10 | No | Existe en el esquema, no se escribe |
| Identificador de anunciante (IDFA) | No | Existe en el esquema, no se escribe (identificador de dispositivo de iOS) |
| ID de anunciante | No | Existe en el esquema, no se escribe (GAID de Android) |

**Campos de la Data Extension de eventos in-app**

Todos los campos de instalación anteriores, además de:

| Campo | Escrito | Notas |
| --- | --- | --- |
| Es atribución primaria | No | Existe en el esquema, no está escrito |
| Ventana de re-engagement | No | Existe en el esquema, no está escrito |
| Valor del evento | No | Existe en el esquema, no está escrito |
| Divisa de ingresos del evento | No | Existe en el esquema, no está escrito |
| Ingresos del evento en USD | No | Existe en el esquema, no está escrito |

</Accordion>

<div id="troubleshooting" />

### Resolución de problemas

* **No hay datos en la Data Extension**: comprueba que tanto el selector Activar partner como el selector de postbacks de eventos in-app estén activados y que los eventos que necesitas estén mapeados. Confirma también que la aplicación de SFMC tiene permisos de escritura de datos en tu cuenta de SFMC.
* **Aparecen eventos, pero no hay contactos coincidentes**: Asegúrate de pasar af\_sub1=%%\_subscriberkey%% en tus OneLinks para que los postbacks puedan coincidir con los contactos de SFMC.
* **La Data Extension no se ha creado**: ponte en contacto con tu CSM o con el soporte de AppsFlyer para confirmar que el conector se ha aprovisionado correctamente para tu cuenta.

<div data-zendesk-anchors="h_01M1EKQ4FWJDKEECDASNHC226Z=sobre-la-integraci%C3%B3n h_01M1EKQ4FWVTQ3R02AE6QREKKK=comparaci%C3%B3n-standard-vs-advanced h_01M1EKQ4FW9XVMFC7FXD8551C1=prerrequisitos h_01M1EKQ4FW115929RS4BR442QF=configura-deep-linking-est%C3%A1ndar-de-correo-electr%C3%B3nico-de-sfmc h_01HE7RCE5NE25563AAGBH0EPZC=ejemplo h_01HE7RCE5N1WQA3XEN9W1QY29K=nota h_01M1EKQ4FW5Q23VEPA4YJK9MQF=env%C3%ADa-correos-electr%C3%B3nicos-con-deep-linking-de-correo-electr%C3%B3nico-est%C3%A1ndar-de-sfmc h_01M1EKQ4FW91474YRH5GZ0K805=configura-la-integraci%C3%B3n-avanzada-de-intercambio-de-aplicaciones-de-sfmc h_01HA51F56HX6VQDYNAQAADKBHJ=ejemplo-1 h_01M1EKQ4FW48QWSZ9W5J80AZVZ=correos-electr%C3%B3nicos-din%C3%A1micos h_01M1EKQ4FW4N9ZGBDGYZ6VAKWN=sincronizaci%C3%B3n-avanzada-de-datos-de-eventos-in-app-de-sfmc h_01M1EKQ4FWVP1A3J89BGQBV8A8=c%C3%B3mo-funciona h_01M1EKQ4FWZZS3D4T5QW7HNQ9W=campos-de-datos-de-postback h_01M1EKQ4FW366GDCCXJS7TDEQS=resoluci%C3%B3n-de-problemas" />
