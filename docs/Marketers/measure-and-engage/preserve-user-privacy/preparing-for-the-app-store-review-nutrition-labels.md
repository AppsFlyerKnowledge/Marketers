---
title: 'Preparación para la revisión del App Store: etiquetas nutricionales'
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2026-08-12T12:23:45Z'
  id: 207032086
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/207032086
---
> **De un vistazo**: A partir de iOS 14, los desarrolladores de aplicaciones deben proporcionar la información de la App Store relacionada con sus prácticas de privacidad cuando envíen una aplicación. La App Store publica las prácticas en el formato de una *etiqueta de nutrición.*

**Notas de nuestros abogados:** *Nada de lo que se indica aquí es asesoramiento legal. Se proporciona para tu información y comodidad. Debes trabajar estrechamente con asesores legales y otros asesores profesionales para exactamente determinar cómo se te aplican las políticas de Apple a ti.* Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

## Etiquetas de nutrición y revisión de la App Store

* Para generar las etiquetas de privacidad, los desarrolladores de aplicaciones deben responder a un cuestionario al enviar su aplicación a App Store Connect que incluya las siguientes secciones:
  * Tipos de datos recopilados
  * [Fines de la recopilación de datos](/docs/preparing-for-the-app-store-review-nutrition-labels#fines-del-uso-de-datos)
  * [Si el tipo de datos está vinculado a una identidad](/docs/preparing-for-the-app-store-review-nutrition-labels#datos-vinculados-a-una-identidad)
  * Si se utilizan datos para el tracking (incluido en relación con cualquier servicio de terceros o SDK que se incluya en una aplicación).
* Desarrolladores de aplicaciones:
  * Tienen un control total sobre cómo implementar y configurar el software de AppsFlyer, qué datos recoger y cómo se utilizan los datos.
  * Puede haber respuestas al cuestionario muy diferentes en función de cómo configuran el software de AppsFlyer y los puntos de datos que eligen recopilar.
* Según la comprensión de la política de Apple por parte de AppsFlyer, AppsFlyer no realiza ningún *seguimiento.* Dicho esto, los desarrolladores de aplicaciones deben responder al cuestionario de acuerdo con sus usos específicos e integraciones de partners.
* Si utilizas los datos recopilados con fines de seguimiento, debes implementar el aviso de ATT.
* A continuación se asumen las configuraciones predeterminadas del software de AppsFlyer. Los desarrolladores de aplicaciones son responsables de asegurarse de que se adapten en consonancia con sus configuraciones y usos específicos.

#### Tipos de datos recopilados

| **Tipo de datos** | **Recopilación de datos de AppsFlyer** | **Observaciones** |
| --- | --- | --- |
| **Información de contacto**<ul><li>Nombre</li><li>Dirección de correo electrónico (incluidas con hash)</li><li>Número de teléfono (incluidos con hash)</li><li>Dirección física</li><li>Otra información de contacto del usuario</li></ul> | No | No se debe recopilar la información de contacto. Sin embargo, si has configurado tu aplicación para transmitir correos electrónicos con hash o números de teléfono con hash, responde en consecuencia en el cuestionario de la App Store. |
| **Fitness** | No | No recopilar |
| **Información financiera**<ul><li>Información de pago</li><li>Información de crédito</li><li>Otra información financiera</li></ul> | No | No recopilar |
| **Información sobre la ubicación**<ul><li>Ubicación precisa</li><li>Ubicación gruesa</li></ul> | Ver las observaciones | <ul><li>Ubicación precisa: No</li><li>Ubicación aproximada: Sí. La dirección IP se recopila y se asigna a una ubicación geográfica aproximada.</li></ul> |
| **Información confidencial** | No | No recopilar |
| **Contactos** | No | No recopilar |
| **Contenido del usuario**<ul><li>Correos electrónicos o mensajes de texto</li><li>Fotos o videos</li><li>Datos de audio</li></ul> | No | No recopilar |
| **Historial de navegación** | No | No recopilar |
| **Historial de búsqueda** | No | No recopilar |
| **Identificadores**<ul><li>ID de usuario</li><li>ID de dispositivo (Identificador de anunciante [IDFA])</li></ul> | Opcional | <ul><li>ID de usuario: Los desarrolladores de aplicaciones pueden configurar y transmitir el ID de usuario (CUID)</li><li>ID de dispositivo: el identificador de anunciante (IDFA) se recopila solo cuando se puede acceder a él.</li></ul> |
| **Compras**<ul><li>Historial de compras</li></ul> | Opcional | Los desarrolladores de aplicaciones pueden elegir configurar ciertos eventos de compra in-app para medir. |
| **Datos de uso**<ul><li>Interacción con el producto</li><li>Datos de publicidad</li><li>Otros datos de uso</li></ul> | <ul><li>Sí</li><li>Opcional</li><li>No</li></ul> | <ul><li>Interacciones con el producto: se miden los inicios de la aplicación, así como cualquier otra interacción con el usuario configurada por el desarrollador de la aplicación.</li><li>Datos de publicidad: se reciben si el desarrollador de la aplicación utiliza el módulo de ingresos por publicidad de AppsFlyer.</li></ul> |
| **Datos de diagnóstico**<ul><li>Datos de bloqueo</li><li>Datos de rendimiento</li><li>Otros datos de diagnóstico</li></ul> | <ul><li>No</li><li>Sí</li><li>No</li></ul> | Se puede recibir la hora de inicio y/o los niveles de batería para detectar el fraude. |
| **Otros datos**<ul><li>Otros tipos de datos</li><li>IDFV</li></ul> | Sí | <ul><li>AppsFlyer recibe información técnica del dispositivo (p. ej., SO, tipo de dispositivo, idioma, tamaño de pantalla, etc.) o la información de la red (p. ej., la dirección IP, el agente de usuario HTTP).</li><li>AppsFlyer aplica un ID de instalación a cada instalación de aplicación llamada ID de AF.</li><li>Se recopila el identificador de proveedor (IDFV).</li></ul> |

### Fines del uso de datos

Los desarrolladores de aplicaciones deben elegir de una lista de fines que tiene Apple, tal como se detalla en la siguiente tabla. Debes identificar los fines relevantes para cada tipo de datos relacionados con tu uso específico.

| Fin de los datos | Selección en función de cómo se utilizarán los datos de AppsFlyer |
| --- | --- |
| Publicidad de terceros | Selecciona esta opción si compartes el tipo de datos con un tercero con el fin de mostrar anuncios de terceros en tu aplicación. |
| Publicidad o marketing del desarrollador | Selecciona si deseas mostrar anuncios propios en tu aplicación, incluso si compartes con un tercero para mostrar tus anuncios, o para otros fines de marketing. |
| Analíticas | Sí |
| Personalización del producto | Selecciona si utilizas datos para cualquier personalización de producto. |
| Funcionalidad de la aplicación | Sí |
| Otros fines | Selecciona si utilizas los datos para cualquier fin que no esté indicado. |

### Datos vinculados a una identidad

Los tipos de datos recopilados a través de AppsFlyer generalmente están conectados a un identificador como el ID de dispositivo (cuando está disponible) u otros identificadores, como los ID emitidos por el cliente, cuando se configuran.

Por lo tanto, los desarrolladores de aplicaciones deben seleccionar **Sí** cuando se les pregunte si los datos están vinculados a una identidad.

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">Política de privacidad del servicio AppsFlyer</Anchor>: Cómo AppsFlyer maneja y utiliza los datos.
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Datos de privacidad de la app en la App Store de Apple</Anchor>.

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=etiquetas-de-nutrici%C3%B3n-y-revisi%C3%B3n-de-la-app-store h_01HE7T7J409620K5KX5XKPEQVZ=etiquetas-de-nutrici%C3%B3n-y-revisi%C3%B3n-de-la-app-store data-types-collected=tipos-de-datos-recopilados h_01HE7T7J4004XVJTMF6S964DVB=tipos-de-datos-recopilados data-use-purposes=fines-del-uso-de-datos h_01HE7T7J4098NNW8D0BCD3EFBJ=fines-del-uso-de-datos data-linked-to-an-identity=datos-vinculados-a-una-identidad h_01HE7T7J41BJG9GTBWMVKG7031=datos-vinculados-a-una-identidad h_01HE7TES34MEF1XR4B6BDEMJW4=consulta-tambi%C3%A9n" />
