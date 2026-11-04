---
title: Redirigir a páginas de productos personalizadas de la tienda
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - OneLink
  created_at: '2021-08-26T07:25:53Z'
  edited_at: '2026-08-12T12:25:07Z'
  id: 4406217556625
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/4406217556625
---
> **De un vistazo:** Redirige a los usuarios a las listas personalizadas de la tienda de tu aplicación en Google Play o a las páginas de productos personalizadas en la App Store. Usa los datos de AppsFlyer sobre las páginas personalizadas de la tienda para optimizar tus campañas.

<div id="overview" />

## Información general

Las listas personalizadas de la tienda de Google Play y las páginas de productos personalizadas de Apple App Store (denominadas colectivamente en este artículo como páginas de productos personalizadas de la tienda) permiten a los propietarios de aplicaciones crear versiones adicionales de sus páginas de Google Play y App Store que muestran diferentes características o contenido dentro de su aplicación. Las páginas de productos personalizadas de la tienda pueden tener texto promocional, capturas de pantalla y vistas previas que son diferentes a las de la página predeterminada de la tienda.

Para Google Play, puedes crear hasta 50 páginas personalizadas. Para el App Store, puedes crear hasta 35.

Puedes usar las URL de OneLink de AppsFlyer o enlaces de atribución de plataforma única para redirigir a los usuarios a estas páginas de productos personalizadas y crear trayectorias contextuales distintas para diferentes públicos objetivo.

Los datos relacionados con las páginas de productos personalizadas de la tienda están disponibles en el panel de control de AppsFlyer y en los reportes de raw data como se describe en la siguiente sección. Puedes utilizar los datos para realizar pruebas A/B y optimizar tus campañas y páginas de productos.

<div id="data-availability" />

## Disponibilidad de datos

<div id="dashboard" />

<Accordion title="Panel de Control">

Los datos agregados para las páginas de productos personalizadas del App Store están disponibles en el panel de control general. Para las listas personalizadas de la tienda de Google Play, estarán disponibles pronto.

**Para ver los datos**:

* En el panel de control general, agrega la dimensión de agrupación de **páginas de productos de la tienda.**  
  La página de productos personalizada de la tienda se muestra en los gráficos y tablas del panel de control.

</Accordion>

<div id="raw-data" />

<Accordion title="Raw Data">

El raw data está disponible a través de las <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">herramientas de reportes de AppsFlyer</Anchor>.

En los reportes, el campo `store_product_page` indica a qué página personalizada se redirigió un usuario determinado.

</Accordion>

<div id="setup" />

## instalación

<div id="google-play" />

<Accordion title="Google Play">

Para configurar redireccionamientos a una lista personalizada de la tienda en Google Play, puedes intentar una de estas opciones:

* Utiliza la interfaz de usuario de OneLink.
* Agrega el parámetro `af_android_store_csl` a tus URL de OneLink o enlaces de atribución de plataforma única con el valor de la lista personalizada de la tienda que elegiste en Google Console. Por ejemplo: `af_android_store_csl=abc123`

<span id="use-the-onelink-ui-google-play"></span>**Nota:** Debido a cambios del sistema en algunos navegadores, incluido Google Chrome, el uso de la redirección de fichas personalizadas de la tienda puede llevar a una versión web de Google Play con la vista de ficha personalizada de la tienda (en lugar de la versión de la aplicación).

<div id="use-the-onelink-uigoogle-play" />

#### Usar la interfaz de usuario de OneLink: Google Play

Requisitos previos:

* Lista personalizada de la tienda creada en Google Console.  
  **Nota**: En Google Console, la lista personalizada debe configurarse para que sea a través de un parámetro de URL único.
* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Plantilla de OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Enlaces personalizados de OneLink</Anchor>

**Para agregar un redireccionamiento a una lista personalizada de la tienda a un enlace personalizado de OneLink**:

1. En tu enlace personalizado de OneLink, ve a la sección **Enlaces profundos y redireccionamientos.**
2. Desplázate hacia abajo hasta la configuración de **Cuando la aplicación no está instalada**.  
   ![android_cpp.png](https://files.readme.io/d354feb4d47171b14f0612011b7a52b579bd9062a87544095df226ba58c57ec6-11591784334865.png)
3. Para Android, asegúrate de que **Redirigir a** esté configurado en Google Play.
4. En el cuadro de texto **Lista personalizada de la tienda**, introduce el valor que definiste para el parámetro de URL única de la lista en Google Console. Por ejemplo: abc123
5. Haz clic en **Actualizar enlace**.
6. [Recomendado] Prueba el enlace en diferentes navegadores Android para asegurarte de que funcione según lo previsto.

</Accordion>

<div id="app-store" />

<Accordion title="Tienda de aplicaciones">

Para configurar redireccionamientos a una página de producto personalizada en la App Store, puedes intentar una de estas dos opciones:

* Utiliza la interfaz de usuario de OneLink.
* Agrega el parámetro `af_ios_store_cpp` a tus URL de OneLink o enlaces de atribución de plataforma única con el valor del ID de página de producto personalizada. Por ejemplo: `af_ios_store_cpp=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

<div id="use-the-onelink-uiapp-store" />

#### Usar la interfaz de usuario de OneLink: App Store

Requisitos previos:

* Página de producto personalizada creada en App Store Connect
* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Plantilla de OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Enlaces personalizados de OneLink</Anchor>

**Para agregar un redireccionamiento a una página de producto personalizada a un enlace personalizado de OneLink**:

1. En tu enlace personalizado de OneLink, ve a la sección **Enlaces profundos y redireccionamientos.**
2. Desplázate hacia abajo hasta la configuración de **Cuando la aplicación no está instalada**.  
   ![ios_cpp.png](https://files.readme.io/76f6b46644efc478dc27cb373b3de4a4a80600936db5d7e6725fdb4b9182f6bb-11591824202641.png)
3. Para iOS, asegúrate de que **Redirigir a** esté configurado en App Store.
4. En el cuadro de texto **Página de producto personalizada**, introduce el ID de la página de producto personalizada (ppid), tal como se define en App Store Connect. Por ejemplo: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.
5. Haz clic en **Actualizar enlace**.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Navegadores | <ul><li>Las listas personalizadas de la tienda de Google Play no son compatibles con Naver Blog.</li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=informaci%C3%B3n-general h_01J851YT6WHWEA6RTBFP1S9FT8=informaci%C3%B3n-general data-availability=disponibilidad-de-datos h_01J851YT6XG2A6VETQ3XSNZWVX=disponibilidad-de-datos h_01J851YT6XXTZVMPQFK4YDMACC=dashboard h_01J851YT6XHR6Y3KB30AMMGZXS=raw-data setup=instalaci%C3%B3n h_01J851YT6XWVEMRG9R5DYKJ70N=instalaci%C3%B3n h_01J851YT6X21X787WNDFGAW5EZ=google-play use-the-onelink-ui%E2%80%94google-play=use-the-onelink-ui-google-play h_01J851YT6XSVG70DX841NKVGDY=usar-la-interfaz-de-usuario-de-onelink-google-play h_01J851YT6XYQG2FGWBEPAJ686X=app-store use-the-onelink-ui%E2%80%94app-store=usar-la-interfaz-de-usuario-de-onelink-app-store h_01J851YT6XJ9NBK5KKHV1Y07M4=usar-la-interfaz-de-usuario-de-onelink-app-store h_01J851YT6XE6P2FDE9KEMH9SYN=traits-and-limitations" />
