---
title: 'Audiencias: usa tus cohortes de Amplitude como audiencias'
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2026-08-12T12:26:04Z'
  id: 4470658876817
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/4470658876817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **A simple vista:** Saca partido a tus datos propios sincronizando tus cohortes de Amplitude con AppsFlyer como audiencias importadas.

<div id="about-the-amplitude-integration" />

## Acerca de la integración con Amplitude

La **integración de Audiencias de AppsFlyer-Amplitude** te permite sincronizar las cohortes definidas en tu cuenta de Amplitude directamente con AppsFlyer como <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems">audiencias importadas</Anchor>. AppsFlyer puede entonces servir como tu plataforma central para conectar y mantener estos segmentos de audiencia con socios, revisar las métricas de campañas y vincular tus datos propios de Amplitude y AppsFlyer para aprovechar al máximo el potencial de ambos.

Las cohortes de Amplitude se pueden sincronizar con AppsFlyer de forma puntual o mediante una sincronización programada con actualizaciones diarias o por horas.

<div id="setting-up-the-integration" />

## Configuración de la integración

Configura la integración de Audiencias-Amplitude desde la plataforma Amplitude.

<div id="define-appsflyer-data-destinations" />

### Definir destinos de datos en AppsFlyer

**Sigue estos pasos en Amplitude para definir los destinos de datos de AppsFlyer.** **Ten en cuenta que debes definir un destino de datos independiente para cada aplicación en la que estés importando audiencias de AppsFlyer.**

1. Desde la sección **Destinos de datos** en Amplitude, selecciona la opción **AppsFlyer**.
2. En **Destinos de cohortes**, selecciona **AppsFlyer.**
3. Introduce la siguiente información en el cuadro de diálogo **Conectar con AppsFlyer**.

   **¡Importante!** Si ya tienes destinos de datos de AppsFlyer creados en tu cuenta de Amplitude, el cuadro de diálogo mostrará una lista desplazable con todos los destinos existentes. Para crear un nuevo destino, desplázate hasta el final de la lista y haz clic en **Agregar otro destino.**

   <Image align="center" alt="" src="https://files.readme.io/ba47fc9a411bd55d84ad34ccd5c1d74fecb1648f8f7aed3ae713965bef616ae8-33375708375441.png" />

   

| Campo | Descripción |
| --- | --- |
| Nombre | Introduce un nombre para el destino.<br /><br />Si vas a crear más de un destino de AppsFlyer en un solo proyecto de Amplitude (por ejemplo, si tienes más de una aplicación en el proyecto), asegúrate de crear un nombre que puedas identificar fácilmente más adelante. |
| Token API de AppsFlyer V2.0 | **Para obtener el token de API de AppsFlyer, sigue estos pasos en AppsFlyer:**<ol><li>Desde la barra de menú superior, accede al menú de usuario (desplegable de dirección de correo electrónico en la esquina superior derecha).</li><li>Selecciona **Centro de seguridad.**</li><li>En la sección **Tokens de API de AppsFlyer**, haga clic en **Administrar sus tokens de API de AppsFlyer.**</li><li>Copie el token **V2.0**.</li></ol> |
| ID de la aplicación de AppsFlyer | Introduzca el ID de la aplicación para este destino tal como aparece en el panel de AppsFlyer:<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| Plataforma | Seleccione la plataforma de la aplicación (iOS o Android). |
| Identificador | Indique a AppsFlyer cómo conectar sus datos de Amplitude con sus datos de AppsFlyer seleccionando una propiedad de usuario de Amplitude a la izquierda y la clave de AppsFlyer para asignarla a la derecha. La clave de AppsFlyer que seleccione debe ser una de las siguientes:<ul><li>**Para audiencias de iOS:** ID de anunciante de iOS, ID de usuario de Amplitude o ID de usuario de cliente de AppsFlyer</li><li>**Para audiencias de Android:** ID de anunciante de Google, ID de usuario de Amplitude o ID de usuario de cliente de AppsFlyer</li></ul> |

4. Haga clic en **Guardar** para guardar el nuevo destino de AppsFlyer.

<div id="sync-amplitude-cohorts-to-appsflyer-destinations" />

### Sincronizar cohortes de Amplitude con destinos de AppsFlyer

**A continuación, siga estos pasos para sincronizar cualquiera de sus cohortes de Amplitude con sus destinos de AppsFlyer:**

1. Desde la sección **Cohortes** de la plataforma Amplitude, seleccione la cohorte para la que desea crear una audiencia de AppsFlyer. (Alternativamente, puede crear una nueva cohorte).
2. Siga el enlace: **Haga clic para ver los detalles de la cohorte.**
3. Desde la página **Definición de cohorte**, haga clic en el botón **Sincronizar con…** .
4. Seleccione el icono de AppsFlyer y luego haga clic en **Siguiente**.

   Se abrirá el cuadro de diálogo **Definir destino y cadencia**.

   <Image align="center" alt="amplitude_define_destination_and_cadence_dialog.png" src="https://files.readme.io/e9f726c731e865e6313bf430b1e5506db5a820fc7d3d544747a873cf08139b26-33375708382097.png" />
5. En la lista **Seleccione un destino de API para sincronizar**, elija el nombre del destino de AppsFlyer relevante.
6. Decida si desea sincronizar esta cohorte con AppsFlyer una sola vez o de manera programada. (Para sincronizaciones programadas, elija si desea actualizar diariamente o cada hora).
7. Haga clic en el botón **Sincronizar** para comenzar a sincronizar.

Después de completar con éxito la primera sincronización, una nueva audiencia para esta cohorte será visible en la pestaña Audiencias del panel de Audiencias.

Por defecto, el nombre de la nueva audiencia es el nombre de la cohorte de Amplitude sincronizada, seguido de un identificador alfanumérico. Puede editar el nombre de la audiencia desde el panel de Audiencias si lo desea.

<Image align="center" alt="audiencia_importada_de_amplitud.png" src="https://files.readme.io/a4f8efc6818d94a68b28ca62ae26215f17bfc7edcfb990855a042a2dee71f8b6-33375708383249.png" />

<div data-zendesk-anchors="overview=acerca-de-la-integraci%C3%B3n-con-amplitude h_01HNZP6HDVC5RBMKTCZY81HG4M=acerca-de-la-integraci%C3%B3n-con-amplitude setting-up-the-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n h_01HNZP6HDVZH6Q1KGJE7FXSPMT=configuraci%C3%B3n-de-la-integraci%C3%B3n define-appsflyer-data-destinations=definir-destinos-de-datos-en-appsflyer h_01HNZP6HDVV3GSEPARCY1VABX8=definir-destinos-de-datos-en-appsflyer sync-amplitude-cohorts-to-appsflyer-destinations=sincronizar-cohortes-de-amplitude-con-destinos-de-appsflyer h_01HNZP6HDV6EFPCM5FE5XBAS78=sincronizar-cohortes-de-amplitude-con-destinos-de-appsflyer" />
