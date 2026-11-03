---
title: Páginas de destino multiplataforma con Smart Script
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2026-08-12T12:09:50Z'
  id: 18440789126289
  locale: es
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/es/articles/18440789126289
---
> **Resumen:** Utilice una página de destino multiplataforma que ejecute el Smart Script de AppsFlyer para realizar la atribución de web a app. Es decir, transforme a los usuarios que ven un anuncio web desde cualquier fuente de medios en usuarios de la aplicación en plataformas como CTV, PC, consola o móviles.

## Descripción general

Con una página de destino multiplataforma que ejecuta el Smart Script de AppsFlyer, puede realizar atribuciones de web a aplicación. Esto significa que puede atribuir instalaciones en cualquier plataforma a anuncios mostrados en la web.

El Smart Script en una página de destino multiplataforma utiliza el enlace entrante (el enlace en el anuncio web) para realizar dos acciones que aseguran que la fuente de medios original y el anuncio web se atribuyan correctamente con la instalación:

* Crear un enlace OneLink multiplataforma que envía una impresión a AppsFlyer.
* Crear enlaces de atribución directa para cada aplicación o plataforma.

## Configuración

#### ALCANCE DEL TRABAJO

| **¿Quién está involucrado?**<ul><li>**Anunciante**:<ul><li>Define qué deben contener los [enlaces de impresión multiplataforma](#create-crossplatform-impression-link) y [de atribución directa](#create-direct-attribution-links) salientes, basándose en los <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> del Smart Script. Esto determina los datos de atribución que se adjuntan a la URL saliente, manipulando la URL entrante o forzando ciertos valores.</li><li>Se asegura de que todas las campañas que llevan al sitio web tengan URLs entrantes con parámetros que el script pueda procesar.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Prueba el Smart Script</Anchor>.</li></ul></li><li>**Desarrollador web**:<ul><li>Añade los argumentos al script e implementa el Smart Script en la página de destino.</li><li>Prueba el Smart Script.</li></ul></li></ul> |
| --- |
| **Requisitos previos**<ul><li>Una cuenta de AppsFlyer con al menos una aplicación.</li><li>Para la URL de impresión: Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla OneLink</Anchor> con la atribución multiplataforma habilitada.</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="Crear un enlace de impresión multiplataforma">

**Para crear un enlace OneLink multiplataforma que envía una impresión a AppsFlyer**:

1. Asigne los parámetros del enlace entrante a los parámetros que el enlace de impresión debe contener (fuente de medios, campaña, nombre del anuncio, etc.).
   * Infórmese más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> en el script que procesa la URL entrante.
   * El valor del argumento <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL</Anchor> es el dominio+ID de la plantilla OneLink con la atribución multiplataforma habilitada.
2. Indique a su desarrollador que inicialice los argumentos del Smart Script y ejecute el método Smart Script `generateOneLinkURL`. <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Vea la demostración e instrucciones para desarrolladores</Anchor>.  
   **Nota:** El `af_xplatform=true` parámetro es fundamental para permitir la atribución multiplataforma.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="Crear enlaces de atribución directa">

1. Mapea los parámetros de los enlaces entrantes a los que deben tener los enlaces de atribución directa que salen (fuente de medios, campaña, nombre del anuncio, etc.). Obtenga más información sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> en el script que gestiona la URL entrante.
2. Indique a su desarrollador que inicialice los argumentos del Smart Script y ejecute el método Smart Script para crear un enlace para cada plataforma o aplicación. Consulte la <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">demostración</Anchor> y las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">instrucciones</Anchor> para desarrolladores.  
   **Nota:** El desarrollador debe agregar los siguientes parámetros:  

| Parámetro/Argumento | Nota | Registra tus respuestas (para que las utilices tú o tu desarrollador) |
| --- | --- | --- |
| Identificador de origen | Una cadena describe la plataforma y debe ser de esta lista:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>Android</li><li>ios</li><li>steam</li><li>quest</li><li>battlenet</li><li>nativepc</li></ul> |  |
| id\_aplicación | <ul><li>Identificación de la aplicación</li><li>Ejemplo: 123456</li></ul> |  |
| redirectURL | <ul><li>La URL a la que debe ser redirigido el usuario de la plataforma o aplicación.</li><li>Ejemplo: `https://store.steampowered.com/app/123456/Team_Fortress_2/`</li></ul> |  |

</Accordion>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general 01H8V0RV7X8JEVEJ36TJB1X43D=descripci%C3%B3n-general setup=configuraci%C3%B3n 01H8V0RV7X0K157JTDQMJSQYKF=configuraci%C3%B3n scope-of-work=alcance-del-trabajo h_01H95PGMNWPBRHSZBPMKNJ2PS6=alcance-del-trabajo 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />
