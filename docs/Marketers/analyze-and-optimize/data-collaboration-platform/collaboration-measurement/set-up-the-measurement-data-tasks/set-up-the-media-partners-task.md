---
title: Configurar la tarea de Partners de medios
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-08-18T11:36:01Z'
  edited_at: '2026-08-12T11:53:11Z'
  id: 38191067035153
  locale: es
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/es/articles/38191067035153
---
> **De un vistazo:** Aprende a configurar Partners de medios para campañas off-site.

Antes de poder compartir conversiones aptas con tus Partners de medios de la <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campaña off-site</Anchor> y recibir a cambio datos de rendimiento agregados, primero debes conectar DCP con la cuenta de medios que activa la campaña. Esta conexión indica a AppsFlyer cómo enviar los datos de conversión al partner de medios.

## Prerrequisitos

Antes de poder configurar la tarea de Partners de medios, el propietario de la colaboración debe asignársela al colaborador que sea propietario de la cuenta de terceros (p. ej., Facebook o Google). Para obtener más información, consulta Asignar tareas de configuración

<div id="create-a-media-partner-connection" />

<Accordion title="Crear una conexión con un partner de medios">

> 📘 **Nota**
>
> La tarea **Media Partners** aparece en la página **Configuración de la medición** solo cuando configuras una <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campaña off-site</Anchor> que utiliza una fuente personalizada como método de aprovisionamiento. Para obtener más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#set-conversion-data-provision-method">Establecer el método de aprovisionamiento de datos de conversión</Anchor>

Sigue estos pasos para seleccionar o crear una conexión con un partner de medios:

1. En la página **Configuración de la medición** , haz clic en la tarea **Media partners** .

   > 📘 **Nota**
   >
   > * Si el cuadro de diálogo **Media partners** está bloqueado, significa que la tarea **Media partners** se ha asignado a tu colaborador y que no puedes ver su contenido. Si eres el propietario de la colaboración, puedes desbloquearlo y reasignarte la tarea. Sin embargo, se eliminará cualquier configuración anterior y la tarea se restablecerá.
   > * Si el panel **Media partners** aparece atenuado, pide al propietario de la colaboración que te asigne la tarea de conversión.

2. En el cuadro de diálogo Media partners, haz clic **+ Connect media partner**.
3. En el **Connect media partner** cuadro de diálogo, crea o selecciona una conexión con un partner de medios para la cuenta de medios que activa la campaña:
   * **Si hay una conexión existente disponible, selecciónala:**
     * En la **Select connection** lista desplegable, elige una conexión existente.
   * **Si no existe ninguna conexión, crea una:**
     1. Haz clic **+ Nueva conexión**.
     2. En la ventana **New media partner connection** , selecciona un partner de medios, como **Meta Ads** o **Google Ads** .
     3. En el **Nombre de la conexión** campo, introduce un nombre para la nueva conexión.
     4. Haz clic **Login to [Media Partner]** y completa la autenticación en la ventana de inicio de sesión del partner de medios.
     5. Haz clic en **Guardar** cuando se complete la autenticación. Después de guardarla, la nueva conexión se selecciona automáticamente en la lista desplegable **Seleccionar conexión** del cuadro de diálogo **Conectar partner de medio**.

</Accordion>

<div id="set-the-google-ads-conversion-action-id-parameter" />

<Accordion title="Configura el parámetro de ID de la acción de conversión de Google Ads">

Si tu partner de medio es Google Ads, proporciona a DCP el parámetro de ID de la acción de conversión. El ID de la acción de conversión se obtiene de tu cuenta de Google Ads y se incluye en los datos de conversión enviados a Google Ads. La acción de conversió**n** m ust be del tipo `UPLOAD_CLICKS`.

Para saber más sobre la acción de conversión de Google Ads, consulta la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12216226?hl=en">documentación de Google Ads</Anchor>.

Para configurar el ID de la acción de conversión de Google Ads, sigue estos pasos:

1. En la lista desplegable **Seleccionar conexión**, selecciona una conexión de Google Ads.
2. En el cuadro de diálogo **Conectar partner de medio**, rellena **al menos uno** de los siguientes campos con el ID de la acción de conversión de Google Ads. **Nota:** Puedes usar el mismo ID en varios recursos web o móviles, y puedes dejar algunos recursos sin asignar. Sin embargo, los recursos sin ID de acción de conversión no se atribuirán.

   * **Acción de conversión web:** el ID de la acción de conversión que se usa para los eventos de conversión creados en el sitio web del colaborador. Debe ser una **acción de conversión** del tipo `UPLOAD_CLICKS`.
   * **Acción de conversión de aplicación (por aplicación):** el ID de la acción de conversión que se usa para los eventos de conversión creados en la aplicación del colaborador. Introduce el ID de la acción de conversión correspondiente, también del tipo `UPLOAD_CLICKS`.

   > 📘 **Nota**
   >
   > Estas acciones de conversión deben mantenerse **exclusivas para la medición de DCP** y no deben usarse para otro tráfico.

3. Haz clic **Hecho** para volver al cuadro de diálogo principal.
4. Confirma que la conexión aparece en la lista y, después, haz clic **Guardar**.
5. En la página **Configuración de medición** verifica que el partner de medio muestre una marca de verificación verde y el estado **Conectado**.

</Accordion>

<div id="set-the-meta-ads-meta-pixel-and-dataset-id-parameters" />

<Accordion title="Configura los parámetros de ID de Meta Pixel y del conjunto de datos de Meta Ads">

Si tu partner de medio es Meta Ads, proporciona a DCP los parámetros de Meta Pixel y del ID del conjunto de datos. El Meta Pixel y el ID del conjunto de datos se obtienen de tu cuenta de Meta Ads y se incluyen en los datos de conversión enviados a Meta Ads.

Consulta la documentación de Meta Ads sobre <Anchor target="_blank" href="https://www.facebook.com/business/help/952192354843755?id=1205376682832142">Meta Pixel</Anchor> y <Anchor target="_blank" href="https://www.facebook.com/business/help/5818684664831465?id=490360542427371">ID del conjunto de datos</Anchor>.

Para configurar el ID de la acción de conversión de Google Ads, sigue estos pasos:

1. En la lista desplegable **Seleccionar conexión**, selecciona una conexión de Meta Ads.
2. En el cuadro de diálogo **Conectar Partners de medios**, rellena **al menos uno** de los siguientes campos con los ID de Meta o Pixel. **Nota:** Puedes dejar algunos recursos sin asignar. Sin embargo, no se atribuirán los recursos sin un ID de acción de conversión.

   * **Meta Pixel:** El ID que se usa para los eventos de conversión creados en el sitio web del colaborador.
   * **ID del conjunto de datos (por aplicación):** El ID que se usa para los eventos de conversión creados en la aplicación del colaborador.

   > ❗️ **Advertencia**
   >
   > El conjunto de datos y el Meta Pixel deben cumplir las siguientes condiciones:
   >
   > * Debe haberse creado específicamente para DCP.
   > * No debe **recibir ninguna conversión directamente** del cliente.
   > * Meta Pixel y el ID del conjunto de datos son intercambiables.


   > 📘 **Nota**
   >
   > El **usuario del sistema** cuyas credenciales se comparten con DCP debe:
   >
   > * Tener **acceso** al conjunto de datos.
   > * Tener concedido **ads\_read** permiso.

3. Haz clic **Listo** para volver al cuadro de diálogo principal.
4. Confirma que la conexión aparezca en la lista y, a continuación, haz clic **Guardar**.
5. En la **Configuración de medición** página, verifica que el partner de medios muestre una marca de verificación verde y el estado como **Conectado**.

</Accordion>

<div data-zendesk-anchors="prerequisites=prerrequisitos h_01K3G4VZX9X67EG0AA7GASSR51=prerrequisitos h_01K3G4VZX9QBCX8NGQJ6GV02CS=create-a-media-partner-connection h_01K3G4VZX90X7GFX0S274EP5Y4=nota h_01K3G4VZX9GX7JRZ7ZJPSG50VS=nota-1 h_01K3G4VZX9S8V2DVCNGNBHEFAD=set-the-google-ads-conversion-action-id-parameter h_01K3G4VZX93P0K0B0R4DR1JMB3=nota-2 h_01K3G4VZX9WC21793Q33431PCB=set-the-meta-ads-meta-pixel-and-dataset-id-parameters h_01K3G4VZX9KADAF2XXFEWVXG81=advertencia h_01K3G4VZXAQBHPPE91WM7R2REH=nota-3" />
