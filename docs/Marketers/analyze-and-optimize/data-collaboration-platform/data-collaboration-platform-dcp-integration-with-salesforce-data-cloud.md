---
title: >-
  Plataforma de colaboración de datos (DCP): integración con Salesforce Data
  Cloud
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-02-29T14:30:51Z'
  edited_at: '2026-08-12T11:53:54Z'
  id: 22977208909969
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/22977208909969
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** la integración con Salesforce Data Cloud te permite llevar tus datos propios a la Plataforma de Colaboración de Datos de AppsFlyer con solo hacer clic en un botón.

<div id="before-you-begin" />

> 🚧 **Antes de comenzar**
>
> Antes de integrar Salesforce Data Cloud, debes **instalar la extensión de la app de AppsFlyer** desde Salesforce AppExchange. Esto debe hacerlo un usuario administrador de Salesforce con permiso para descargar paquetes de AppExchange.
>
> 1. Ve a la <Anchor target="_blank" href="https://appexchange.salesforce.com/appxListingDetail?listingId=6c756ddf-777c-42fc-9eaf-d96ca36ed2e3">lista de AppsFlyer</Anchor> en Salesforce AppExchange.
> 2. Haz clic en **Get It Now**.
> 3. Sigue los pasos descritos en la <Anchor target="_blank" href="https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm">guía de instalación de la aplicación</Anchor>.
>
> Cuando la instalación finalice correctamente, el proceso habrá terminado y no será necesaria ninguna configuración adicional del paquete.

<div id="set-up-the-integration" />

## Configura la integración

La integración consiste en crear una conexión de Salesforce Data Cloud y después crear fuentes. Solo necesitas una conexión para autenticar tu cuenta de Salesforce. Con esta conexión, puedes crear varias fuentes basadas en tablas de Salesforce.

<div id="note" />

> 📘 **Nota:**
>
> Si ya has configurado una conexión con Salesforce Data Cloud, no podrás crear otra.

<div id="create-a-salesforce-data-cloud-connection" />

### Crear una conexión de Salesforce Data Cloud

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la parte superior derecha de la página, haz clic en **Manage connections** > **+ New connection**.
3. En el cuadro de diálogo **New connection**, selecciona **Data providers** > **Salesforce Data Cloud**.  

   <Image align="center" alt="salesforce-data-cloud-new-connection.jpg" src="https://files.readme.io/6b240e0cff3f0bc9e6b7f6eaf45520a78252e1619769a696855e8d68d322ce60-23301617982353.jpg" width="517px" />
4. Haz clic en **Log in to Salesforce**.
5. Continúa con el proceso de autenticación y permite que Salesforce acceda a AppsFlyer.   
   **Nota:** si la autenticación no se realiza correctamente, volverás al cuadro de diálogo **New connection** para intentarlo de nuevo.
6. Después de autenticarte correctamente, volverás al cuadro de diálogo **New connection** con una indicación de que tienes una conexión activa con Salesforce. Ahora ya puedes continuar y crear una fuente.
7. Haz clic en **Create source** y sigue las [instrucciones que se indican a continuación](#crear-una-fuente-de-salesforce-data-cloud) para crear una fuente de Salesforce Data Cloud.

<div id="create-a-salesforce-data-cloud-source" />

### Crear una fuente de Salesforce Data Cloud

Después de autenticar tu cuenta de Salesforce y configurar la conexión con Salesforce Data Cloud, el siguiente paso es crear fuentes. Estas fuentes proporcionan a AppsFlyer los datos necesarios cada vez que realizas actualizaciones.

Accede a la pestaña **Sources** con uno de estos métodos:

* Después de completar el paso anterior, haz clic en **Crear fuente**.
* En el menú lateral de AppsFlyer, ve a **Collaborate** > **Data Clean Room** > **+ New Source**, que aparece en la esquina superior derecha de la página.

<div id="note-1" />

> 📘 **Nota:**
>
> Al crear tu fuente, asegúrate de que no se envíen datos restringidos a AppsFlyer.

**Para crear una fuente:**

1. **Establecer el nombre de la fuente:** Introduce un <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#1-name-the-source">nombre para la fuente</Anchor> y haz clic en **Siguiente**.
2. **Establecer ubicación de la fuente:**
   * **Selecciona la conexión:** Salesforce Data Cloud se rellena automáticamente después de añadir la conexión. Si no es así, selecciónala en la lista de conexiones.
   * **Tabla o vista:** Después de seleccionar la conexión de Salesforce Data Cloud, los nombres de las tablas y las vistas de tu cuenta de Salesforce se rellenan automáticamente. Selecciona la tabla o vista y haz clic en **Siguiente**.  

     <Image align="center" alt="crear-fuente-sf-3-pasos.jpg" src="https://files.readme.io/44549ef1cd59b99610944c604c1cdfd4d598352cd106877fab3a301ce14650f8-23306070497169.jpg" />
3. **Configura el esquema de la fuente:** Después de seleccionar una tabla o vista, los nombres y tipos de campo se rellenan automáticamente. Puedes editar los tipos de campo o eliminar los campos no deseados seleccionando el icono de la papelera al final de la fila del campo.  
   **Nota:** Asegúrate de que al menos un tipo de campo sirva como identificador. Por ejemplo, CUID, ID de plataforma, ID de AppsFlyer e ID con hash SHA256.
4. Haga clic en **Guardar**. La nueva fuente se muestra en la lista de todas las fuentes existentes.

<div data-zendesk-anchors="h_01HPKB2ERPGD2PS4JBSDGYW3MC=antes-de-comenzar set-up-the-integration=configura-la-integraci%C3%B3n 01HRW9TK3YZV32CXRM6Q2HCHS4=configura-la-integraci%C3%B3n 01HRSFKVQNJ264M16A9X9AEP53=nota create-a-salesforce-data-cloud-connection=crear-una-conexi%C3%B3n-de-salesforce-data-cloud h_01HRSDCVMHQ6C5R6R4S5XRT5KQ=crear-una-conexi%C3%B3n-de-salesforce-data-cloud create-a-salesforce-data-cloud-source=crear-una-fuente-de-salesforce-data-cloud h_01HRSG0P4Q38WHGQWBY3S3D11W=crear-una-fuente-de-salesforce-data-cloud h_01HRVPJ801B0VC879APZCGKDNE=nota-1" />
