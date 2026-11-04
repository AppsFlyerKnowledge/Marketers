---
title: Configurar la tarea de ventanas de lookback
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
  created_at: '2025-08-18T11:38:51Z'
  edited_at: '2026-08-12T11:53:08Z'
  id: 38191154658193
  locale: es
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/es/articles/38191154658193
---
<div id="set-lookback-windows" />

## Configurar ventanas de lookback

> **De un vistazo:** configura las ventanas de atribución para campañas on-site y off-site a fin de determinar hasta qué punto en el tiempo se pueden asociar los engagements de los usuarios con las conversiones.

Las ventanas de lookback definen el tiempo máximo entre un engagement del usuario (clic o visualización) y la conversión resultante con fines de atribución. Cada colaboración puede establecer una duración personalizada de la ventana de lookback. Los Partners de medios, como Google Ads o Meta Ads, suelen aplicar reglas distintas para configurar estas ventanas. Este artículo explica cómo configurar ventanas de lookback tanto para colaboradores como para Google y Meta.

<div id="prerequisites" />

## Prerrequisitos

Antes de que un colaborador que no sea el propietario de la colaboración pueda configurar la tarea de ventanas de lookback, el propietario primero debe asignársela. Para obtener más información, consulta Asignar tareas de configuración.

<div id="open-the-lookback-windows-task" />

## Abrir la tarea de ventanas de lookback

En la página **Configuración de medición**, la tarea Ventanas de lookback es donde configuras las ventanas de lookback de las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">campañas on-site y off-site</Anchor>.

Para abrir la tarea de ventanas de lookback, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la página **Data Collaboration Platform**, selecciona la colaboración que deseas configurar.
3. En la parte inferior de la página de colaboración, haz clic en **Configurar medición.**
   * Si el enlace aparece en gris, configura las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">fuentes de datos</Anchor> y las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiencias</Anchor> de la colaboración.
4. En la página **Measurement Setting**, haz clic en el panel de tareas **Lookback windows** para abrir el cuadro de diálogo **Lookback windows**.

   <div id="note" />

   > 📘 **Nota**
   >
   > Si el panel **Lookback windows** aparece en gris, pide al propietario de la colaboración que te asigne la tarea de ventanas de lookback.


<div id="set-the-collaboration-lookback-window" />

## Configurar la ventana de lookback de la colaboración

Para configurar la ventana de lookback de la colaboración, sigue estos pasos:

1. Si estás configurando una <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">campaña combinada on-site y off-site</Anchor> en el cuadro de diálogo **Lookback Windows**, expande el panel <Image alt="AppsFlyer.png" src="https://files.readme.io/2536fe45ebde303e110c7b90cb3b2a95fc28672a5fa095efff485cdebbd466df-38392816916369.png" width="2.61%" /> **CMN Attribution**. De lo contrario, pasa al siguiente paso.
2. En los controles deslizantes de **Click-through** o **View-through lookback window**, arrastra el puntero para elegir la duración de la ventana en días.
3. Haz clic en **Guardar**.

<div id="set-the-meta-ads-lookback-window" />

## Configurar la ventana de lookback de Meta Ads

Si estás ejecutando una campaña off-site con Meta Ads, la tarea de Ventanas de lookback incluirá ajustes específicos para Meta Ads. Puedes establecer por separado las ventanas de atribución de click-through y view-through, según las duraciones de ventana predefinidas de Meta Ads.

1. En el panel **Ventanas de lookback**, despliega el panel <Image alt="Meta.png" src="https://files.readme.io/4023aa4c9446f22aa46063ab349fc038d974638aeefcbb3288e04663896ec788-38392832989585.png" width="3.22%" /> **Meta Ads**.
2. Selecciona las ventanas de atribución de **clic** y **view-through** entre las siguientes opciones:
   * **1 día**
   * **7 días**
   * **28 días**

<div id="google-ads-lookback-window" />

## Ventana de lookback de Google Ads

Si tienes una campaña off-site en funcionamiento con Google Ads, la tarea Ventanas de lookback incluirá un enlace a la plataforma de Google Ads.

1. En el cuadro de diálogo **Ventanas de lookback**, desplázate hasta el panel <Image alt="Google-ads.png" src="https://files.readme.io/afa0e2cd15ea4214eba625da397dccd04118b564450c59993fd0e668c31f023b-38392832994321.png" width="2.86%" /> **Google Ads**.
2. Haz clic en el **icono de flecha** para abrir la página de configuración de la acción de conversión correspondiente en la plataforma de Google Ads.
3. Actualiza la configuración de la ventana de lookback según sea necesario en Google Ads.

<div data-zendesk-anchors="set-lookback-windows=configurar-ventanas-de-lookback h_01K3G9Q0G79BDATM6T80T6F6TX=configurar-ventanas-de-lookback prerequisites=prerrequisitos h_01K3G9Q0G7XSM1VS4VF9VCTWD0=prerrequisitos open-the-lookback-windows-task=abrir-la-tarea-de-ventanas-de-lookback h_01K3G9Q0G7FM4MMR6CVWM4ATRA=abrir-la-tarea-de-ventanas-de-lookback h_01K3G9Q0G7DQRCX9FH9Q3N17N3=nota set-the-collaboration-lookback-window=configurar-la-ventana-de-lookback-de-la-colaboraci%C3%B3n h_01K3G9Q0G7X7FY6C0H4DQYSP3F=configurar-la-ventana-de-lookback-de-la-colaboraci%C3%B3n set-the-meta-ads-lookback-window=configurar-la-ventana-de-lookback-de-meta-ads h_01K3G9Q0G71ADFQ9QHBXJBTEAA=configurar-la-ventana-de-lookback-de-meta-ads google-ads-lookback-window=ventana-de-lookback-de-google-ads h_01K3G9Q0G7HEFS65XA6YD0V6YD=ventana-de-lookback-de-google-ads" />
