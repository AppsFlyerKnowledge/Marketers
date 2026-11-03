---
title: Resolución de problemas del SDK web
metadata:
  keywords:
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2019-07-22T13:55:15Z'
  edited_at: '2026-08-12T12:11:51Z'
  id: 360002075858
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360002075858
---
> **Resumen:** Guía de resolución de problemas del SDK web de AppsFlyer, añadido directamente a tu sitio web o implementado mediante Google Tag Manager.

## SDK añadido directamente

Puedes añadir el SDK directamente a tu sitio web.

### No hay datos o hay datos parciales en el dashboard de PBA

| Causa | SOLUCIÓN |
| --- | --- |
| Los datos pueden tardar hasta 24 horas en mostrarse en los <Anchor target="_blank" href="/marketers/es/docs/pba-website-attribution-dashboard">dashboards de People-Based Analysis</Anchor> después de implementar el SDK. | Espera 24 horas. Si los datos siguen sin estar disponibles, consulta causas adicionales en este documento. |
| Clave de desarrollador web incorrecta | <ul><li>El SDK web utiliza la clave de desarrollador web para identificar los eventos web enviados y así saber a qué paquete atribuir los datos.</li><li>Verifica que estás utilizando la <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">clave de desarrollador web correcta.</Anchor></li></ul><Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#add-brand-bundle">Página del paquete de marca</Anchor> |
| Has colocado el SDK web en el cuerpo de la página | <ul><li>Puedes colocar el SDK web en el body de la página, pero esto puede afectar a los datos que se envían a AppsFlyer.</li><li>Te recomendamos que lo pongas en la sección head de la página.</li></ul> |
| El SDK web no está colocado en todas las páginas de tu sitio web | Te recomendamos colocar el SDK web en todas las páginas de tu sitio web. |

### No se envían eventos

| Causa | SOLUCIÓN |
| --- | --- |
| Los eventos se envían antes de que se cargue el SDK web. En estos casos, la consola para desarrolladores del navegador muestra el error: `Uncaught ReferenceError: AF is not defined` | Verifica que el SDK web se cargue antes que el código que envía eventos. |
| Clave de desarrollador web incorrecta | <ul><li>PBA requiere una clave de desarrollador web para saber a qué paquete atribuir los datos. Asegúrate de que se utiliza la clave de desarrollador web correcta.</li><li>Verifica que estás utilizando la <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">clave de desarrollador web correcta.</Anchor></li></ul> |
| Eventos malformados | Asegúrate de que el evento esté bien formado.<br /><br />Consulta los <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">parámetros de evento disponibles</Anchor> para saber más sobre los eventos con el formato correcto. |
| SDK llamado dos veces |  |

### SDK y bibliotecas en conflicto

Muchos SDK web hacen uso de bibliotecas JavaScript populares. Estos SDK también ocupan nombres en el ámbito global. Por ejemplo, nuestro SDK web ocupa **AF** como el objeto principal que habilita el SDK web.

* Si algún SDK hace uso de la versión 1.2 de la biblioteca X y el SDK de AppsFlyer hace uso de la versión 2.1 de la biblioteca X, las dos bibliotecas podrían entrar en conflicto.
* Si otro SDK o biblioteca hace uso de **AF** (en el ámbito global) como nombre de objeto, los dos SDK entran en conflicto y uno podría sobrescribir al otro.

## SDK añadido mediante Google Tag Manager

* Implementar el SDK web con la ayuda de Google Tag Manager (GTM) puede ahorrarte tiempo.
* Puedes implementarlo de forma independiente y no tienes que depender de tu desarrollador web para añadirlo a tu sitio web.

Si encuentras problemas. Además de los problemas descritos en la [implementación nativa del SDK](/docs/troubleshooting-the-web-sdk#sdk-añadido-directamente), hay algunos posibles problemas específicos de GTM.

### Llamada al SDK

| Causa | SOLUCIÓN |
| --- | --- |
| <ul><li>Nuestra guía del SDK web muestra cómo añadir el SDK web usando una etiqueta.</li></ul><ul><li>Algunos usuarios, al crear etiquetas para llamar a eventos, configuran la etiqueta para que también vuelva a llamar a la etiqueta del SDK. Pero esto puede causar problemas.</li></ul>![mceclip0.png](https://files.readme.io/77be12759c5ec5a04a517ee1b99109e8952b97d1d4280b71c51fa36304f5adbf-360003756558.png) | La mejor opción es configurar una etiqueta para cargar el SDK y hacer que se active en todas las páginas. Las etiquetas que envían eventos no deben volver a llamar a la etiqueta del SDK. |

### Prioridad de la etiqueta

GTM te permite <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">establecer la prioridad de las etiquetas</Anchor>. Esto significa que puedes controlar qué etiquetas se activan primero.

| Causa | SOLUCIÓN |
| --- | --- |
| Una etiqueta que carga el SDK tiene una prioridad inferior a la de una etiqueta que envía un evento al cargar la página. Como resultado, el SDK no se inicializa a tiempo para enviar el evento. | En la etiqueta que carga el SDK, establece siempre una prioridad superior a la de las etiquetas que envían eventos o identifican usuarios. |

### Activación de etiquetas

En GTM, cada etiqueta tiene un activador que determina cuándo debe activarse esa etiqueta.

| Causa | SOLUCIÓN |
| --- | --- |
| El activador encargado de activar la etiqueta que carga el SDK no está configurado para todas las páginas. Como resultado, no se registran todas las visitas a la página y algunos eventos no se envían. | Lo mejor es configurar un activador de <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en">vistas de todas las páginas</Anchor> para la etiqueta que carga el SDK. |
| El activador encargado de activar las etiquetas que envían eventos no está configurado correctamente. Como resultado, algunos eventos no se envían. | Determina las condiciones del activador. Por ejemplo:<ul><li>una interacción con elementos del DOM, como hacer clic en un botón</li><li>una visita a una página con una ruta concreta, como **/thank-you-page** o **/confirmation-page**</li></ul> |

### Publicación de contenedores de GTM

Todos los cambios en GTM, como añadir o editar etiquetas y activadores, requieren que publiques el contenedor de GTM para que los cambios surtan efecto. Si usas el SDK web con GTM, pero el SDK no se carga o no se envían eventos, asegúrate de [publicar el contenedor de GTM](https://support.google.com/tagmanager/answer/6107163?hl=en).

<div data-zendesk-anchors="sdk-added-directly=sdk-a%C3%B1adido-directamente no-data-or-partial-data-in-the-pba-dashboard=no-hay-datos-o-hay-datos-parciales-en-el-dashboard-de-pba events-are-not-sent=no-se-env%C3%ADan-eventos conflicting-sdks-and-libraries=sdk-y-bibliotecas-en-conflicto sdk-added-using-google-tag-manager=sdk-a%C3%B1adido-mediante-google-tag-manager calling-the-sdk=llamada-al-sdk tag-priority=prioridad-de-la-etiqueta triggering-tags=activaci%C3%B3n-de-etiquetas publishing-gtm-containers=publicaci%C3%B3n-de-contenedores-de-gtm" />
