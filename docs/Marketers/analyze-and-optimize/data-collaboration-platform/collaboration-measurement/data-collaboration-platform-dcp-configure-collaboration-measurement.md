---
title: 'Data Collaboration Platform (DCP): configurar la medición de la colaboración'
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
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-08-12T11:53:16Z'
  id: 32147174933905
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/32147174933905
---
**En resumen:** Aprende a configurar DCP para realizar la atribución a nivel de SKU en función de los datos de conversión, engagement y asignación de campañas.

<div id="overview" />

## Descripción general

Después de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">preparar los datos de conversión, engagement y asignación de campañas</Anchor>, puedes configurar DCP para utilizarlos en la medición y la atribución:

1. [**Definir el tipo de campaña**](#selecciona-el-tipo-de-campaña-on-site-off-site-o-ambas) – Elige entre on-site, off-site o combinado. Esto determina cómo DCP procesa tus datos y define las tareas de configuración necesarias.
2. [**Asignar tareas**](#asignar-una-tarea-de-configuración) – El propietario asigna cada tarea de configuración al colaborador que tiene acceso a los datos correspondientes.
3. [**Configurar tareas**](#configurar-la-medición-de-campañas-on-site-y-off-site) – Los colaboradores configuran las conversiones, los engagements y la asignación de campañas. Esto incluye configurar campañas on-site y off-site para que todos los datos estén conectados, asignados y listos para la atribución.
4. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**Ejecutar y gestionar mediciones**</Anchor> - Ejecuta mediciones en tiempo real o históricas, duplícalas, vuelve a ejecutarlas o cambia su alcance.

<div id="start-the-measurement-setup" />

## Iniciar la configuración de la medición

Para iniciar la configuración de la medición, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la página **Data Collaboration Platform**, selecciona la colaboración que deseas configurar.
3. En la página de colaboración, realiza **uno** de los siguientes pasos:
   * Si esta es la primera medición que configuras en tu colaboración, haz clic en **Configurar medición.** Se muestra la página **Crear medición**.
   * Si ya tienes una medición configurada en tu colaboración, haz clic en el signo más del panel de selección de mediciones. Se muestra la página **Crear medición**.

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## Selecciona el tipo de campaña: on-site, off-site o ambas.

Como los tipos de campaña on-site y off-site se diferencian por el lugar donde se produce la conversión y por la forma en que se gestiona la atribución, el propietario de la colaboración debe especificar el tipo de campaña antes de configurar la medición de la colaboración. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">On-site vs medición de campañas off-site</Anchor>.

Para seleccionar el tipo de campaña, sigue estos pasos:

1. [Iniciar la configuración de la medición](#iniciar-la-configuración-de-la-medición).
2. En la página **Crear medición**, elige  <Image alt="icono on-site.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **En el sitio, <Image alt="off-site icon.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> Off-site** o ambas. Continúa con **uno** de los siguientes:
   * [Configurar la campaña on-site](#configurar-la-medición-de-campañas-on-site-y-off-site),
   * [Configurar la campaña off-site](#configure-offsite-campaign-measurement),
   * [Configurar una campaña combinada on-site y off-site](#configure-combined-onsite-and-offsite-campaign-measurement).

<div id="assign-configuration-task" />

## Asignar una tarea de configuración

La página “Configuración de la medición” incluye cinco tareas clave: conversión, engagement, asignación de campañas, partners de medios y configuración de la ventana de lookback.

El propietario de la cuenta de DCP puede asignar tareas a los colaboradores para garantizar la privacidad de los datos y reflejar la distribución de responsabilidades. Por ejemplo, un colaborador puede encargarse de los datos de engagement mientras que el otro se encarga de las conversiones. Los colaboradores solo tienen acceso a las tareas que se les asignan.

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="Asignar una tarea de configuración a un colaborador">

Para asignar cualquiera de las tareas anteriores, sigue los pasos que se indican a continuación:

1. [Abrir la configuración de la medición](#iniciar-la-configuración-de-la-medición).
2. En cada una de las cuatro tareas anteriores, en la lista **Asignado a**, selecciona el colaborador que se encargará de la tarea.
   * **Tarea de conversiones:** Asígnala al colaborador cuya plataforma aloja las conversiones.
   * **Tarea de campañas:** Asígnala al colaborador cuya plataforma aloja las conversiones.
   * **Tarea de engagements:** Asígnala al colaborador en cuya plataforma se produce el engagement de los usuarios.
   * **Tarea de partners de medios:** Asígnala al colaborador cuya cuenta de partner de medio se utiliza para las campañas off-site.
   * **Tarea de ventanas de lookback** – Se asigna automáticamente al propietario de la colaboración. De forma opcional, puedes asignarla al otro colaborador.

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="Eliminar la asignación de una tarea de configuración a un colaborador">

En algunos casos, puede ser necesario revocar la asignación de una tarea de configuración a un colaborador. Cuando el propietario de la colaboración elimina una asignación, ocurre lo siguiente:

* El colaborador pierde inmediatamente el acceso a la tarea cuya asignación se ha eliminado.
* Se descarta cualquier configuración que el colaborador hubiera proporcionado previamente para esa tarea.
* Se detiene la medición de la colaboración.

Para eliminar la asignación de una tarea de configuración, sigue los pasos que se indican a continuación:

1. Ve a la medición de la colaboración; consulta abrir la configuración de la medición.
2. En el paso de configuración correspondiente, en la lista **Asignado a**, elimina el colaborador asignado.

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## Configurar la medición de campañas on-site y off-site

Configura la medición de campañas en “Configuración de la medición”. Sigue los pasos que se indican a continuación según si tu medición es on-site, off-site o una configuración combinada de on-site y off-site.

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="Configurar la medición de campañas on-site">

Para configurar una <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">campaña on-site</Anchor>, sigue estos pasos:

1. [Iniciar la configuración de la medición](#iniciar-la-configuración-de-la-medición).
2. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configurar la tarea de campañas</Anchor>
3. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task">Configurar la tarea de conversiones</Anchor>
4. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configurar la tarea de engagements</Anchor>
5. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configurar la tarea de ventanas de lookback</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="Configurar la medición de campañas off-site">

Para configurar una <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campaña off-site</Anchor>, sigue estos pasos:

1. [Iniciar la configuración de la medición](#iniciar-la-configuración-de-la-medición).
2. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configurar la tarea de campañas</Anchor>
3. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task">Configurar la tarea de conversiones</Anchor>
4. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configurar la tarea de partners de medios</Anchor>
5. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configurar la tarea de ventanas de lookback</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="Configurar la medición de campañas combinadas on-site y off-site">

Para configurar una <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">campaña combinada on-site y off-site</Anchor>, sigue estos pasos:

1. [Iniciar la configuración de la medición](#iniciar-la-configuración-de-la-medición).
2. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configurar la tarea de campañas</Anchor>
3. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task">Configurar la tarea de conversiones</Anchor>
4. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configurar la tarea de engagements</Anchor>
5. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configurar la tarea de partners de medios</Anchor>
6. <Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configurar la tarea de ventanas de lookback</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01K3EHANCCZ703MMMM5PTEF68B=descripci%C3%B3n-general open-measurement-settings=iniciar-la-configuraci%C3%B3n-de-la-medici%C3%B3n h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=iniciar-la-configuraci%C3%B3n-de-la-medici%C3%B3n select-campaign-type-onsite-offsite-or-both=selecciona-el-tipo-de-campa%C3%B1a-on-site-off-site-o-ambas h_01K3EHANCCW8PQ8NWC6ZHWCMGT=selecciona-el-tipo-de-campa%C3%B1a-on-site-off-site-o-ambas assign-configuration-task=asignar-una-tarea-de-configuraci%C3%B3n h_01K3EHANCCW97TV88ECVMQKF2N=asignar-una-tarea-de-configuraci%C3%B3n h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=configurar-la-medici%C3%B3n-de-campa%C3%B1as-on-site-y-off-site h_01K3EHANCD936QN2MKFY5QSDBZ=configurar-la-medici%C3%B3n-de-campa%C3%B1as-on-site-y-off-site h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
