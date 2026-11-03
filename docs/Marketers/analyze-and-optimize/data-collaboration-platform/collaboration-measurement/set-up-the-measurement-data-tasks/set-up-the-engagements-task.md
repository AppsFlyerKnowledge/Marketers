---
title: Configurar la tarea de Engagements
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
  created_at: '2025-08-18T10:19:20Z'
  edited_at: '2026-08-12T11:53:06Z'
  id: 38188042548113
  locale: es
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/es/articles/38188042548113
---
> **De un vistazo:** Aprende a configurar eventos de engagement para campañas on-site y combinadas (campañas on-site y off-site).

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#engagements">Los eventos de engagement</Anchor> capturan interacciones de los usuarios, como visualizaciones de anuncios o clics, que se producen antes de una conversión. Se configuran solo para campañas on-site, ya sea por sí solas o combinadas con campañas off-site. (En el caso de las campañas off-site, los datos de engagement los proporcionan directamente partners externos, como Meta o Google. En este artículo se explica cómo configurar engagements por tipo de campaña.

## Prerrequisitos

Antes de poder configurar la tarea de Engagements, el propietario de la colaboración debe asignársela al colaborador propietario de la plataforma donde se generan los eventos de engagement. Para obtener más información, consulta Asignar tareas de configuración

## Configurar engagements para campañas on-site o combinadas

En el contexto de las campañas on-site y combinadas, todos los eventos de engagement se originan en las propiedades del colaborador, como su aplicación, sitio web o sistemas en tienda. Estos eventos de engagement suelen recopilarse mediante el SDK de AppsFlyer o enviarse a través de fuentes de datos personalizadas, y se atribuyen exclusivamente a la actividad de los usuarios on-site.

<div id="1-prepare-engagement-data" />

<Accordion title="1. Preparar datos de engagement">

Antes de configurar la fuente de engagement personalizada en DCP, puedes proporcionar datos de engagement de una de estas dos formas:

* **Archivo de fuente personalizada:** Crea un archivo de fuente de engagement y cárgalo en tu servicio en la nube. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Preparar archivos de fuente personalizados para engagements</Anchor>.
* **SDK de AppsFlyer:** Integra el SDK de AppsFlyer en tu aplicación para enviar automáticamente eventos de engagement in-app a DCP. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Preparar eventos in-app para engagements</Anchor>.

</Accordion>

<div id="2-open-engagement-settings" />

<Accordion title="2. Abrir la configuración de engagement">

En la página **Configuración de la medición** configuras, como parte de la configuración de la medición de la colaboración, cómo se recopilan y atribuyen los engagements.

Para abrir la página **Configuración de la medición**, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la página **Data Collaboration Platform**, selecciona la colaboración que deseas configurar.
3. En la parte inferior de la página de colaboración, haz clic en **Configurar medición.**
   * Si el enlace aparece atenuado, configura las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">fuentes de datos</Anchor> y las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiencias</Anchor> de la colaboración.
4. En la página **Configuración de la medición**, haz clic en el panel **Engagements** para abrir el cuadro de diálogo **Engagements**.

   > 📘 **Nota:**
   >
   > * Si el cuadro de diálogo **Engagements** está bloqueado, significa que la tarea de Engagements se ha asignado a tu colaborador y que no puedes ver su contenido. Si eres el propietario de la colaboración, puedes desbloquearla reasignándote la tarea. Sin embargo, se eliminará cualquier configuración anterior y la tarea se restablecerá.
   > * Si el panel **Engagements** aparece en gris, pide al propietario de la colaboración que te asigne la tarea de Engagements.


</Accordion>

<div id="3-set-data-provision-method" />

<Accordion title="3. Establecer el método de suministro de datos">

Los datos de engagement se proporcionan a DCP mediante eventos in-app, una fuente personalizada o ambas opciones:

* **Eventos in-app** — El origen de los datos de los eventos de engagement es el SDK de AppsFlyer integrado en tu aplicación móvil. El SDK envía eventos de engagement en tiempo real desde tu aplicación cada vez que el usuario realiza una acción definida.
* **Fuente personalizada** — El origen de los eventos de engagement es un archivo de fuente personalizado almacenado en tu servicio en la nube.

Para configurar el método de suministro de datos de engagement en DCP, sigue estos pasos:

1. En el cuadro de diálogo **Engagements**, selecciona el tipo de suministro de engagement: eventos in-app, archivo de fuente personalizado o ambos.
2. Según el método de suministro, introduce los siguientes datos:
   * **Eventos in-app:**
     1. Selecciona la aplicación que envía los eventos in-app que contienen los datos de engagement.
     2. En la lista **Select ad engagement event**, selecciona cuál de los Eventos in-app enviados por el SDK de AppsFlyer es el evento de engagement.
     3. En la lista **Select advertised item (SKU)**, selecciona el parámetro del evento in-app que contiene el valor del SKU.
   * **Fuentes personalizadas:**
     1. Haz clic en + **Nueva fuente de engagement**.
     2. En el cuadro de diálogo **Nueva fuente de engagement**, introduce el nombre de la fuente de engagement en el campo **Nombre de la fuente** de acuerdo con los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-y-directrices">requisitos y directrices</Anchor>.
3. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Establecer ubicación de la fuente">

Si se usa una fuente personalizada para proporcionar eventos de engagement a DCP, configura los datos que permiten a DCP acceder a ella en tu servicio en la nube.

1. En el paso **Establecer ubicación de la fuente** , selecciona la conexión desde la que se accede a la fuente.
   * Si tu cuenta no tiene conexiones definidas, se abrirá el cuadro de diálogo **Nueva conexión** para que crees una.
   * Si ya tienes conexiones, pero quieres usar una nueva, abre la lista **Seleccionar conexión** y selecciona **+ Nueva conexión.**
2. Configura los detalles de acceso a la fuente según tu servicio en la nube:
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube">Amazon S3 y GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#ubicación-de-la-fuente-como-archivos-locales">Sistema de archivos local</Anchor>
3. Selecciona cómo deben gestionarse los datos nuevos. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Establecer el método de sincronización de la fuente</Anchor>.
4. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

</Accordion>

<div id="5-map-engagement-source-fields" />

<Accordion title="5. Asignar campos de la fuente de engagement">

Si se usa una fuente personalizada para proporcionar eventos de engagement a DCP, asigna los campos de tu fuente de engagement personalizada a sus campos correspondientes en DCP.

> 📘 **Nota:**
>
> La **base de datos de eventos de conversión de DCP** almacena todos los eventos de conversión de la colaboración actual en un esquema unificado, incluidos los eventos de conversión procedentes de **Eventos in-app** o de **campañas off-site** (si estás ejecutando una campaña combinada on-site y off-site).

**Cargar campos de la fuente de engagement**

Si los campos de la fuente de engagement aún no se han cargado, puede que tengas que cargarlos manualmente para asignarlos a los campos de DCP.

Para cargar los campos de la fuente de engagement, sigue estos pasos:

1. En el paso **Map source fields**, haz clic en **Load fields from source**.
2. Para obtener información sobre cómo cargar campos manualmente, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carga-tus-campos-de-la-fuente">Cargar tus campos de fuente</Anchor>.

**Asignación automática de campos de engagement**

Cuando se cargan los campos de la fuente de engagement, DCP los asigna automáticamente a sus campos de DCP correspondientes. La asignación automática puede tardar hasta 10 segundos. Se muestra un banner con el resultado de la asignación, que indica cuántos campos se han asignado y enumera las columnas de la fuente que no se han podido hacer coincidir.

Para volver a activar la asignación automática, haz clic en **Actualizar asignación**.

**Asignar campos de engagement**

Si los campos de la fuente de engagement están cargados, puedes asignarlos a los campos de DCP.

Para asignar los campos de fuente personalizados de engagement, sigue estos pasos

1. Si estás configurando una campaña combinada **On-site and Off-site campaign**, en el paso **Map source fields**, expande **Data for on-site attribution;** de lo contrario, pasa al paso siguiente.
2. Asigna todos los campos obligatorios en **Required**.
3. (Opcional) Expande **Datos de enriquecimiento opcionales** para asignar campos adicionales.
4. Haz clic en **Guardar**. Aparece el mensaje **fuente `{source name}` creada** .[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.62%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div data-zendesk-anchors="prerequisites=prerrequisitos h_01K3EFVGA56P7FB605JY1BQ34M=prerrequisitos set-up-engagements-for-onsite-or-combined-campaigns=configurar-engagements-para-campa%C3%B1as-on-site-o-combinadas h_01K3EFVGA6GT10BXJYE9SFM9TE=configurar-engagements-para-campa%C3%B1as-on-site-o-combinadas h_01K3EFVGA6NM4YKZ8MEEYXX58B=1-prepare-engagement-data h_01K3EFVGA65CFME4H3ZC89X471=2-open-engagement-settings h_01K3EFVGA618KT7PGSVQXF6JSV=nota h_01K3EFVGA6BKGAS5GZR3GW2N2M=3-set-data-provision-method h_01K3EFVGA64CQTKZ8C227042PY=4-set-source-location h_01K3EFVGA6J7PX1QE8TRA42QEY=5-map-engagement-source-fields h_01K3EFVGA6E3WH7FEYCW09P74V=nota-1" />
