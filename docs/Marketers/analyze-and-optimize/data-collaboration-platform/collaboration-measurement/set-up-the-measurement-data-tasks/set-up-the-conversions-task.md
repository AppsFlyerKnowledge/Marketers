---
title: Configurar la tarea de conversiones
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-08-18T10:13:32Z'
  edited_at: '2026-08-12T11:53:03Z'
  id: 38187770114449
  locale: es
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/es/articles/38187770114449
---
> **De un vistazo:** :AAG: Aprende a configurar eventos de conversión para campañas on-site y off-site.

Los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#conversions">eventos de conversión</Anchor> registran acciones valiosas posteriores al engagement, como compras, en distintas configuraciones de campaña. Aunque la estructura y el contenido de cada evento de conversión se mantienen constantes, la forma en que se miden, atribuyen y comparten las conversiones varía en función de si se trata de una campaña <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">on-site</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">off-site</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">on-site y off-site</Anchor>. En este artículo se explica cómo configurar la tarea de Conversiones para cada tipo de campaña.

<div id="prerequisites" />

## Prerrequisitos

Antes de poder configurar la tarea de Conversiones, el propietario de la colaboración debe asignársela al colaborador propietario de la plataforma en la que se generan los eventos de conversión. Para obtener más información, consulta Asignar tareas de configuración

<div id="set-up-on-site-campaign-conversions" />

## Configurar las conversiones de campañas on-site

En el contexto de las campañas on-site, todos los eventos de conversión se originan en las propiedades del colaborador, como su aplicación, su sitio web o sus sistemas en tienda. Estos eventos de conversión suelen recopilarse mediante el SDK de AppsFlyer o enviarse a través de fuentes de datos personalizadas, y se atribuyen exclusivamente a engagements de usuarios on-site.

Para configurar las conversiones on-site, sigue estos pasos:

1. [Preparar datos de conversión](#preparar-datos-de-conversi%C3%B3n)
2. [Abrir la configuración de conversiones](#abrir-configuracion-de-conversiones)
3. [Establecer el método de suministro de datos](#establecer-m%C3%A9todo-de-suministro-de-datos-de-conversi%C3%B3n)
4. [Establecer ubicación de la fuente](#establecer-ubicaci%C3%B3n-de-la-fuente-de-conversi%C3%B3n)
5. [Asignar campos de la fuente de conversión on-site](#asignar-campos-de-la-fuente-de-conversi%C3%B3n-on-site)

<div id="set-up-off-site-campaign-conversions" />

## Configurar las conversiones de campañas off-site

En el contexto de las campañas off-site, los eventos de conversión se producen dentro de las propiedades del colaborador, como su aplicación, su sitio web o sus sistemas en tienda, pero la atribución se basa en engagements que tuvieron lugar en plataformas externas, como Meta o Google.

Para configurar las conversiones off-site, sigue estos pasos:

1. [Preparar datos de conversión](#preparar-datos-de-conversi%C3%B3n)
2. [Abrir la configuración de conversión](#abrir-configuracion-de-conversiones)
3. [Establecer el método de suministro de datos](#establecer-metodo-de-provision-de-datos-de-conversion)
4. [Establecer ubicación de la fuente](#establecer-ubicacion-de-la-fuente-de-conversiones)
5. [Asignar campos de la fuente de conversión off-site](#asignar-campos-de-la-fuente-de-conversiones-off-site)

<div id="set-up-on-site-and-off-site-conversions" />

## Configurar conversiones on-site y off-site

En las configuraciones combinadas de campañas on-site y off-site, las conversiones de las propiedades del colaborador pueden atribuirse a engagement de fuentes on-site u off-site.

Para configurar las conversiones on-site y off-site, sigue estos pasos:

1. [Preparar datos de conversión](#preparar-datos-de-conversiones)
2. [Abrir la configuración de conversión](#abrir-configuracion-de-conversiones)
3. [Establecer el método de suministro de datos](#establecer-metodo-de-provision-de-datos-de-conversion)
4. [Establecer ubicación de la fuente](#establecer-ubicacion-de-la-fuente-de-conversiones)
5. [Asignar campos de la fuente de conversión on-site](#asignar-campos-de-la-fuente-de-conversiones-on-site)
6. [Asignar campos de la fuente de conversión off-site](#asignar-campos-de-la-fuente-de-conversiones-off-site)

<div id="configuration-activities" />

## Actividades de configuración

<div id="prepare-conversion-data" />

<Accordion title="Preparar datos de conversión">

Antes de configurar la fuente de conversión personalizada en DCP, puedes proporcionar los datos de conversión de una de estas dos formas:

* **Archivo de fuente personalizada:** Crea un archivo de fuente de conversión y súbelo a tu servicio en la nube. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Preparar archivos de fuente personalizados para conversiones</Anchor>.
* **SDK de AppsFlyer:** Integra el SDK de AppsFlyer en tu aplicación para enviar automáticamente eventos de conversión in-app a DCP. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Preparar eventos in-app para conversiones.</Anchor>

</Accordion>

<div id="open-conversion-settings" />

<Accordion title="Abrir la configuración de conversiones">

En la página **Configuración de medición** puedes configurar cómo se recopilan, atribuyen y comparten las conversiones y los engagement con partners de medios como parte de la configuración de tu colaboración off-site.

Para abrir la página **configuración de la medición** , sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la página **Data Collaboration Platform** , selecciona la colaboración que deseas configurar.
3. En la parte inferior de la página de colaboración, haz clic **Set up measurement.** (Si el enlace está desactivado, configura las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">fuentes de datos</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiencias</Anchor>.)
4. En la página **Configuración de la medición** , haz clic en el panel **Conversiones** para abrir el cuadro de diálogo **Conversiones**.

   <div id="note" />

   > 📘 **Nota:**
   >
   > * Si el cuadro de diálogo **Conversión** está bloqueado, significa que la tarea de **Conversión** se ha asignado a tu colaborador y que no puedes ver su contenido. Si eres el propietario de la colaboración, puedes desbloquearlo reasignándote la tarea. Sin embargo, se eliminará cualquier configuración anterior y la tarea se restablecerá.
   > * Si el panel **Conversión** aparece atenuado, pide al propietario de la colaboración que te asigne la tarea de Conversión.


</Accordion>

<div id="set-conversion-data-provision-method" />

<Accordion title="Configurar el método de aprovisionamiento de datos de conversión">

Los datos de conversión se proporcionan a DCP a través de eventos in-app, una fuente personalizada o ambos:

* **Eventos in-app** — El origen de los datos del evento de conversión es el SDK de AppsFlyer integrado en tu aplicación móvil. El SDK envía eventos de conversión en tiempo real desde tu aplicación cada vez que el usuario realiza una actividad de conversión.
* **Fuente personalizada** — El origen de los eventos de conversión es un archivo de fuente personalizado almacenado en tu nube.

Para configurar el método de aprovisionamiento de datos de conversión en DCP, sigue estos pasos:

1. En el cuadro de diálogo **Conversiones** , selecciona el tipo de aprovisionamiento de conversiones: eventos in-app, archivo de fuente personalizado o ambos.
2. Según el método de aprovisionamiento, introduce los siguientes datos:
   * **Eventos in-app:**
     1. Selecciona la aplicación que envía los eventos in-app que contienen los datos de conversión.
     2. En la lista **Seleccionar evento de conversión** , selecciona cuál de los eventos in-app enviados por el SDK de AppsFlyer es el evento de conversión.
     3. En el campo **Artículo anunciado (SKU)** , selecciona el parámetro que contiene los SKU del evento de conversión.
   * **Fuentes personalizadas:**
     1. Haz clic en + **Nueva fuente de conversión**.
     2. En el cuadro de diálogo **Nueva fuente de conversión** , introduce el nombre de la fuente de conversión en el campo **Nombre de la fuente** de acuerdo con los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-y-directrices">requisitos y directrices</Anchor>.
3. Haz clic **Siguiente**.

</Accordion>

<div id="set-conversion-source-location" />

<Accordion title="Establecer la ubicación de la fuente de conversión">

Si se utiliza una fuente personalizada para proporcionar eventos de conversión, habilita el acceso de DCP a ellos siguiendo estos pasos:

1. En el paso **Establecer ubicación de la fuente** , selecciona la conexión desde la que se accede a la fuente.
   * Si tu cuenta no tiene conexiones definidas, se abrirá el cuadro de diálogo **Nueva conexión** para que crees una.
   * Si ya tienes conexiones pero quieres usar una nueva, abre la lista **Seleccionar conexión** y selecciona **+ Nueva conexión.**
2. Configura los detalles de acceso a la fuente según tu servicio en la nube:
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube">Amazon S3 y GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#ubicación-de-la-fuente-como-archivos-locales">Sistema de archivos local</Anchor>
3. Selecciona cómo se deben gestionar los datos nuevos. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Establecer el método de sincronización de la fuente</Anchor>.
4. Haz clic **Siguiente**.

</Accordion>

<div id="map-onsite-conversion-source-fields" />

<Accordion title="Asignar campos de la fuente de conversión on-site">

Si se utiliza una fuente personalizada para proporcionar eventos de conversión a DCP, asigna los campos de tu fuente de conversión personalizada on-site a los campos de DCP correspondientes.

<div id="note-1" />

> 📘 **Nota:**
>
> La **base de datos de eventos de conversión de DCP** almacena todos los eventos de conversión de la colaboración actual en un esquema unificado, incluidos los eventos de conversión procedentes de **eventos in-app** o de **campañas off-site** (si estás ejecutando una campaña combinada on-site y off-site).

**Cargar campos de la fuente de conversión**

Si los campos de la fuente de conversión todavía no se han cargado, puede que tengas que cargarlos manualmente para asignarlos a los campos de DCP.

Para cargar los campos de la fuente de conversión, sigue estos pasos:

1. En el paso **Asignar campos de la fuente** , haz clic **Cargar campos desde la fuente**.
2. Para obtener información sobre cómo cargar los campos manualmente, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carga-tus-campos-de-la-fuente">Cargar los campos de la fuente</Anchor>.

**Asignar automáticamente campos de conversión**

Cuando se cargan los campos de la fuente de conversión, DCP los asigna automáticamente a sus campos de DCP correspondientes. La asignación automática puede tardar hasta 10 segundos. Un banner muestra el resultado de la asignación, indicando cuántos campos se asignaron y enumerando las columnas de la fuente que no se pudieron hacer coincidir.

Para volver a activar la asignación automática, haz clic en **Actualizar asignación**.

**Asignar campos de conversión**

Si los campos de la fuente de conversión están cargados, puedes asignarlos a los campos de DCP.

Para mapear los campos de fuente personalizados de conversión, sigue estos pasos

1. Si estás configurando una **campaña** **combinada dentro y fuera del sitio**, despliega **Datos para la atribución dentro del sitio;** de lo contrario, sáltate este paso y pasa al siguiente.
2. Mapea todos los campos obligatorios bajo **Obligatorios**.
3. (Opcional) Despliega **Datos de enriquecimiento opcionales** para mapear campos adicionales.

   <div id="note-5" />

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Si la campaña está combinada con una campaña fuera del sitio, y mapeas un campo (por ejemplo, ID de evento) que ya está mapeado en un canal fuera del sitio, se te mostrará un **¿Sobrescribir campo?** mensaje. Haz clic **Sí, continuar** para confirmar y aplicar el mapeo en todos los canales.

4. Haz clic en **Guardar**. Se muestra el **`{source name}` source created** mensaje.[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.33%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div id="map-offsite-conversion-source-fields" />

<Accordion title="Mapear campos de la fuente de conversión fuera del sitio">

Si se usa una fuente personalizada para proporcionar eventos de conversión de campañas fuera del sitio, mapea los campos de tu fuente de conversión personalizada fuera del sitio con los campos de DCP correspondientes.

<div id="note-3" />

> 📘 **Nota:**
>
> La **base de datos de eventos de conversión de DCP** almacena todos los eventos de conversión de la colaboración actual en un esquema unificado, incluidos los eventos de conversión procedentes de **eventos in-app** o **campañas dentro del sitio** (si estás ejecutando una campaña combinada dentro y fuera del sitio).

**Cargar campos de la fuente de conversión**

Si los campos de la fuente de conversión aún no están cargados, puede que tengas que cargarlos manualmente para mapearlos con los campos de DCP.

Para cargar campos de la fuente de conversión, sigue estos pasos:

1. En el **paso Map source fields**, haz clic **Load fields from source**.
2. Para obtener información sobre cómo cargar campos manualmente, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carga-tus-campos-de-la-fuente">Cargar los campos de tu fuente</Anchor>.

**Mapear automáticamente campos de conversión**

Cuando se cargan los campos de la fuente de conversión, DCP los mapea automáticamente con los campos de DCP correspondientes. El mapeo automático puede tardar hasta 10 segundos. Un banner muestra el resultado del mapeo, indicando cuántos campos se han mapeado y enumerando las columnas de la fuente que no se han podido hacer coincidir.

Para volver a activar el mapeo automático, haz clic en **Actualizar mapeo**.

**Mapear campos de conversión**

Si los campos de la fuente de conversión están cargados, puedes mapearlos con los campos de DCP. Cuando compartes datos de conversión con plataformas externas como Meta o Google, AppsFlyer envía solo los campos que necesita cada partner para cotejar las conversiones con sus propios eventos de engagement de campaña.

Los campos que se muestran aquí dependen de los tipos de fuente de conversión que seleccionaste durante la configuración:

1. Si estás configurando una **campaña** **combinada dentro y fuera del sitio**, despliega **Datos para la atribución fuera del sitio;** de lo contrario, pasa al siguiente paso.
2. Activa **Meta Ads** o **Google Ads**, en función de tus fuentes de datos:

   <div id="note-4" />

   > 📘 **Nota:**
   >
   > Cuando compartes datos de conversión con plataformas externas como Meta o Google, AppsFlyer envía solo los campos necesarios para que cada partner haga coincidir las conversiones con sus propios eventos de engagement de la campaña.


   **Asignación de campos de Meta Ads**

   Asigna los campos en **Source fields** a los campos correspondientes en **DCP fields**. Los campos de DCP que aparecen aquí reflejan los parámetros necesarios para Meta Ads.

   * Asigna los seis campos obligatorios en **Obligatorio**.
   * Despliega **Datos de enriquecimiento opcionales** para asignar campos adicionales (por ejemplo, nombre, IDFA y correo electrónico).

   **Asignación de campos de Google Ads**

   Asigna los campos en **Source fields** a los campos correspondientes en **DCP fields**. Los campos de DCP que aparecen aquí reflejan los parámetros necesarios para Google Ads.

   * Asigna los cinco campos obligatorios en **Obligatorio**.
   * Asigna al menos un identificador en **Se requiere al menos uno**.
   * Despliega **Datos de enriquecimiento opcionales** para asignar campos recomendados, como ingresos, agente de usuario del cliente o identificadores con hash.

   > 📘 **Nota:**
   >
   > Si la campaña se combina con una campaña off-site, y asignas un campo (por ejemplo, ID de evento) que ya está asignado en un canal off-site, se te solicitará con el mensaje **¿Sobrescribir campo?** mensaje. Haz clic en **Sí, continuar** para confirmar y aplicar la asignación en todos los canales.

3. Haz clic en **Guardar** para completar la configuración de la fuente.

</Accordion>

<div data-zendesk-anchors="prerequisites=prerrequisitos h_01K38T7G97M4403CPYYVG4F0SG=prerrequisitos set-up-onsite-campaign-conversions=configurar-las-conversiones-de-campa%C3%B1as-on-site h_01K38T7G970AVGNTPN6JN7E5SC=configurar-las-conversiones-de-campa%C3%B1as-on-site set-up-offsite-campaign-conversions=configurar-las-conversiones-de-campa%C3%B1as-off-site h_01K38T7G97KP9NHFPPFG3F4992=configurar-las-conversiones-de-campa%C3%B1as-off-site set-up-onsite-and-offsite-conversions=configurar-conversiones-on-site-y-off-site h_01K38T7G97ZXZZQ48ZRY4A019F=configurar-conversiones-on-site-y-off-site configuration-activities=actividades-de-configuraci%C3%B3n h_01K38T7G975KF5036EZTNA4NYJ=actividades-de-configuraci%C3%B3n h_01K38T7G974NCK1XE35KG4CF79=prepare-conversion-data h_01K38T7G97156TM1AJD7HTNZ2K=open-conversion-settings h_01K38T7G97VGR60QBE1YP565XQ=nota h_01K38T7G975CFGND94MK9B4PZS=set-conversion-data-provision-method h_01K38T7G979CKD39QCFV7ZESY5=set-conversion-source-location h_01K38T7G97XNE4AS4YE64QWK80=map-onsite-conversion-source-fields h_01K38T7G9738EZBAM1XVMASGK0=nota-3 h_01K38T7G97HV111FQ6CQCQMXHH=nota-2 h_01K38T7G976GHY5W6YDHJD1DY7=map-offsite-conversion-source-fields h_01K38T7G97WFBS0HHX1ASR2F5W=nota-3 h_01K38T7G97MZF6RYY3YRG2EVPQ=nota-4 h_01K38T7G976MJZWGDYMK6EB76A=nota-5" />
