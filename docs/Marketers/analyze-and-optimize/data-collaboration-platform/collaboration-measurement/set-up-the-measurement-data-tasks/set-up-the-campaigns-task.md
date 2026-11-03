---
title: Configurar la tarea de campañas
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T11:31:27Z'
  edited_at: '2026-08-12T11:53:00Z'
  id: 38190881693969
  locale: es
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/es/articles/38190881693969
---
> **De un vistazo:** descubre cómo configurar la fuente de la campaña para campañas on-site, off-site y combinadas (campañas on-site y off-site).

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#campaign-mapping">La fuente de la campaña</Anchor> conecta los eventos de conversión on-site con sus respectivas campañas off-site, on-site y combinadas, lo que permite una atribución precisa y la elaboración de informes de rendimiento. A diferencia de otras tareas en DCP (como conversiones o engagement), la **tarea de campañas es idéntica tanto para las campañas on-site como para las campañas off-site**. Esto significa que sigues el mismo proceso de configuración independientemente del tipo de campaña.

## Prerrequisitos

Antes de poder configurar la tarea de campañas, el propietario de la colaboración debe asignársela al colaborador que sea propietario de la plataforma donde se generan los eventos de conversión. Para obtener más información, consulta Asignar tareas de configuración

## Configurar la tarea de campañas

La fuente de campañas enlaza los eventos de conversión internos con identificadores a nivel de campaña (por ejemplo, ID de campaña) en el contexto de campañas on-site, off-site o combinadas. La información de campaña que configures en esta tarea se envía a DCP a través de una fuente de datos personalizada.

<div id="1-prepare-campaign-data" />

<Accordion title="1. Preparar los datos de campaña">

Antes de configurar la fuente de campaña en DCP, prepara la fuente personalizada de la campaña y súbela a tu servicio en la nube. Para obtener más información sobre el esquema de mapeo y cómo cargar la fuente de campaña en tu entorno en la nube, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Preparar la fuente de campaña</Anchor>.

Para configurar la fuente de campaña en DCP:

1. Ve a la página de **medición de la colaboración**.
2. Haz clic en **Campañas**.
3. En el cuadro de diálogo **Campañas**, haz clic en **+ Nueva fuente de campaña**.
4. En el cuadro de diálogo **Nueva fuente de campaña**, introduce un nombre en el campo **Nombre de la fuente** de acuerdo con los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-y-directrices">requisitos y directrices</Anchor>.
5. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

</Accordion>

<div id="2-open-campaigns-settings" />

<Accordion title="2. Abrir la configuración de campañas">

En la página **Configuración de la medición** configuras cómo se recopilan y atribuyen las campañas, y cómo se conectan con los datos de partners de medios como parte de la configuración de tu colaboración.

Para abrir la página **Configuración de la medición**, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la página **Data Collaboration Platform**, selecciona la colaboración que deseas configurar.
3. En la parte inferior de la página de colaboración, haz clic en **Configurar medición.**
   * Si el enlace está desactivado, configura las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">fuentes de datos</Anchor> y las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiencias</Anchor> de la colaboración.
4. En la página **Configuración de la medición**, haz clic en el panel **Campañas** para abrir el cuadro de diálogo **Campañas**.

   > 📘 **Nota:**
   >
   > * Si el cuadro de diálogo **Campañas** está bloqueado, significa que la tarea de **Campañas** está asignada a tu colaborador y no puedes ver su contenido. Si eres el propietario de la colaboración, puedes desbloquearlo reasignándote la tarea. Sin embargo, se eliminará cualquier configuración anterior y la tarea se restablecerá.
   > * Si el panel **Campañas** aparece atenuado, pide al propietario de la colaboración que te asigne la tarea de Campañas.


</Accordion>

<div id="3-set-campaign-data-provision-method" />

<Accordion title="3. Configurar el método de suministro de datos de campaña">

Los datos de campaña se proporcionan a DCP en un archivo de origen personalizado almacenado en tu nube.

Para configurar el método de suministro de conversiones en DCP, sigue estos pasos:

1. En el cuadro de diálogo **Campañas** , haz clic en + **Nueva fuente de campaña**.
2. En el cuadro de diálogo **Nueva fuente de conversión** , en el paso **Nombre de la fuente**, establece el nombre de la fuente de campaña en el **Nombre de la fuente** según los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-y-directrices">requisitos y directrices</Anchor>.
3. Haz clic **Siguiente**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Establecer ubicación de la fuente">

Define la ubicación de la fuente de la campaña en tu servicio en la nube.

1. En el paso **Establecer ubicación de la fuente**, selecciona la conexión desde la que se accede a la fuente.
   * Si tu cuenta no tiene conexiones definidas, se abrirá el cuadro de diálogo **Nueva conexión** para que crees una.
   * Si ya tienes conexiones existentes pero quieres usar una nueva, abre la lista **Seleccionar conexión** y selecciona **+ Nueva conexión**.
2. Configura los datos de acceso según tu servicio en la nube:
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube">Amazon S3 y GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#ubicación-de-la-fuente-como-archivos-locales">Sistema de archivos local</Anchor>
3. Selecciona cómo deben gestionarse los datos nuevos. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Configurar el método de sincronización de la fuente</Anchor>.
4. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

</Accordion>

<div id="5-map-campaign-fields" />

<Accordion title="5. Asignar campos de campaña">

Si se utiliza una fuente personalizada para proporcionar eventos de conversión a DCP, asigna los campos de tu fuente de conversión personalizada en el sitio a los campos correspondientes de DCP.

**Cargar campos de la fuente de campaña**

Si los campos de la fuente de campaña todavía no están cargados, puede que tengas que cargarlos manualmente para asignarlos a los campos de DCP.

Para cargar los campos de la fuente de conversión, sigue estos pasos:

1. En el paso **Asignar campos de la fuente**, haz clic **Cargar campos desde la fuente**.
2. Para obtener información sobre cómo cargar campos manualmente, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carga-tus-campos-de-la-fuente">Cargar los campos de tu fuente</Anchor>.

**Asignar automáticamente campos de campaña**

Cuando se cargan los campos de fuente de campaña, DCP los asigna automáticamente a sus campos de DCP correspondientes. La asignación automática puede tardar hasta 10 segundos. Se muestra un banner con el resultado de la asignación, que indica cuántos campos se han asignado y enumera las columnas de fuente para las que no se ha encontrado ninguna coincidencia.

Para volver a activar la asignación automática, haz clic en **Actualizar asignación**.

**Asignar campos de campaña**

Si se cargan los campos de fuente de conversión, puedes asignarlos a los campos de DCP.

Para asignar los campos de fuente personalizados de las campañas, sigue estos pasos:

1. Asigna los campos de **Campos de fuente** a sus campos correspondientes de **Campos de DCP**.
   * Para ver una lista de campos y descripciones, consulta El esquema de campañas.
2. Haga clic en **Guardar**. Se muestra el mensaje **campaign\_mapping source created**.

</Accordion>

<div id="5-align-collaborator-name" />

<Accordion title="6. Alinear nombre del colaborador">

El paso final después de completar la tarea de Campañas es alinear el nombre del colaborador. Esto es necesario porque cada cuenta de DCP solo tiene una fuente de campaña. Como el propietario de la cuenta puede mantener varias colaboraciones con distintos colaboradores, DCP necesita saber qué colaborador está activo en la colaboración actual.

Para alinear el nombre del colaborador:

* En el cuadro de diálogo **Campañas**, en **Alinear nombres de colaboradores**, selecciona el colaborador de la colaboración actual.

</Accordion>

<div data-zendesk-anchors="prerequisites=prerrequisitos h_01K3BEVMGMPENVYY18EB0ANQCP=prerrequisitos set-up-the-campaigns-task=configurar-la-tarea-de-campa%C3%B1as h_01K3BEVMGM6EEP6DY54HDDVKTR=configurar-la-tarea-de-campa%C3%B1as h_01K3BEVMGMC9C09FJTRVMS2J32=1-prepare-campaign-data h_01K3BEVMGMT28RXKBN31EBAFYJ=2-open-campaigns-settings h_01K3BEVMGMGV8GVGKZFDCSC0DF=nota h_01K3BEVMGM2D9TA52F9F36Z31W=3-set-campaign-data-provision-method h_01K3BEVMGM67JV6VT6TBXTYACC=4-set-source-location h_01K3BEVMGNNFYFF939RHB8Z8E1=5-map-campaign-fields h_01K3BEVMGN4MAV9B0HP2TK5XCC=5-align-collaborator-name" />
