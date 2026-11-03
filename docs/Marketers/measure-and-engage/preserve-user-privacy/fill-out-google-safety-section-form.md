---
title: Formulario de la sección de seguridad de Google
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2026-08-12T12:23:40Z'
  id: 4417197430289
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/4417197430289
---
> **De un vistazo**: A partir de abril de 2022, los desarrolladores de aplicaciones deben completar el formulario de la sección de seguridad de datos de Google Play y publicar un enlace a una política de privacidad, incluso si no recopilan ninguno de los tipos de datos especificados por Google. Esta página tiene como objetivo proporcionar información para ayudarte a responder el cuestionario de la sección de seguridad de Google, solo en relación con lo que AppsFlyer procesa en nombre de los clientes.

Los clientes deben trabajar estrechamente con asesores legales y otros asesores profesionales para determinar exactamente cómo se aplican las políticas de Google y deben adaptar sus respuestas de acuerdo con sus configuraciones y usos específicos.

#### **Advertencia**

La información contenida en este artículo está destinada a ayudar a responder el cuestionario de la sección de seguridad de Google en relación **únicamente** con lo que AppsFlyer procesa en nombre de los clientes.

Se proporciona únicamente con fines informativos y de conveniencia. Los clientes deben trabajar estrechamente con asesores legales y otros asesores profesionales para determinar exactamente cómo se aplican las políticas de Google y deben adaptar sus respuestas de acuerdo con sus configuraciones y usos específicos.

## Introducción

A partir de abril de 2022, los desarrolladores de aplicaciones deberán proporcionar información relacionada con sus prácticas de privacidad a través de la sección de seguridad dedicada de Google. Específicamente, los desarrolladores de aplicaciones deberán proporcionar detalles sobre los datos que recopilan, cómo se manejan y comparten, incluso mediante el uso de SDK de terceros.

La información proporcionada por cada aplicación se mostrará en la ficha de la tienda de Google para ayudar a los usuarios finales a comprender mejor las prácticas de privacidad de una aplicación.

## audiencia

Todos los desarrolladores de aplicaciones deberán completar el cuestionario de la sección de seguridad y publicar un enlace a una política de privacidad, incluso si no recopilan ninguno de los tipos de datos especificados por Google.

## Formulario de seguridad de Google (cuestionario)

Google ha publicado un formulario (cuestionario) que los desarrolladores de aplicaciones deberán completar. El cuestionario incluye las siguientes secciones:

* Recopilación y seguridad de datos
* Tipos de datos
* Uso y manejo de datos

Los desarrolladores de aplicaciones deberán evaluar primero sus prácticas de recopilación y manejo de datos antes de responder el cuestionario.

Con respecto al uso de AppsFlyer, se recuerda a los desarrolladores de aplicaciones que tienen control total sobre cómo implementan y configuran AppsFlyer, incluidos los datos recopilados y cómo se utilizan. Por lo tanto, cada desarrollador de aplicaciones puede tener diferentes respuestas al cuestionario según sus prácticas de datos y el uso de AppsFlyer.

Los desarrolladores de aplicaciones deben responder al cuestionario de acuerdo con sus casos de uso, configuraciones e integraciones de partners específicos.

### Recopilación y seguridad de datos

En esta sección, se te harán algunas preguntas generales de tipo sí/no:

1. ¿Tu aplicación recopila o comparte alguno de los tipos de datos requeridos?
2. ¿Todos los datos de usuario recopilados por tu aplicación están cifrados en tránsito?
3. ¿Proporcionas una forma para que los usuarios puedan solicitar que se eliminen sus datos?

Con respecto a tu uso de AppsFlyer, AppsFlyer cifra todos los datos en tránsito que se transmiten a través del SDK. AppsFlyer también brinda a los clientes la capacidad de eliminar datos específicos del usuario final a través de su marco OpenGDPR. Para los tipos de datos recopilados, consulta la tabla en la sección [Tipos de datos](/docs/fill-out-google-safety-section-form#tipos-de-datos).

### Tipos de datos

En esta sección, se te pedirá que selecciones los tipos de datos recopilados y respondas a lo siguiente:

1. Si se comparten los datos
2. Si los datos se procesan de forma efímera
3. Si se requieren los datos o los usuarios finales pueden optar por la exclusión opcional
4. El propósito

La siguiente tabla asume las configuraciones predeterminadas del software AppsFlyer. Los desarrolladores de aplicaciones son responsables de asegurarse de que se adapten en consonancia con sus configuraciones y usos específicos.

"Recopilados" significa datos transmitidos fuera del dispositivo por cualquier medio (por ejemplo, vista web o SDK).  Una excepción es si se utiliza un cifrado de extremo a extremo que hace que los datos sean ilegibles para cualquiera.

| Tipo de datos | Recopilación de datos predeterminada de AppsFlyer | Notas |
| --- | --- | --- |
| Información sobre la ubicación<ul><li>Ubicación aproximada</li><li>Ubicación precisa</li></ul> | Ver notas -> | Ubicación precisa: No<br /><br />Ubicación aproximada: Sí, la dirección IP se recibe y se asigna a un nivel de región/ciudad. |
| Información personal<ul><li>Nombre</li><li>Correo electrónico</li><li>Identificadores personales (ID de cuenta, número o nombre)</li><li>Dirección</li><li>Número de teléfono</li><li>Raza y etnia</li><li>Creencias políticas o religiosas</li><li>Orientación sexual o identidad de género</li><li>Otra información personal</li></ul> | Ver notas -> | No se debe recopilar información personal y AppsFlyer restringe la recopilación de datos personales como el nombre y la dirección. Sin embargo, si los desarrolladores de aplicaciones configuraron la transmisión de correos electrónicos cifrados o números de teléfono cifrados o configuraron un ID de cuenta de usuario del cliente (CUID), deberán responder como corresponda. |
| Información financiera<ul><li>Número de tarjeta de crédito, tarjeta de débito o cuenta bancaria</li><li>Historial de compras</li><li>Información de crédito</li><li>Otra información financiera</li></ul> | No  <br />  <br />Opcional<br /><br />No  <br />No | No se debe recopilar información financiera, como tarjetas de crédito e información crediticia.<br /><br />Si estás midiendo las compras in-app (historial de compras), debes responder **Sí** |
| Salud y actividad física<ul><li>Información de salud</li><li>Información de actividad física</li></ul> | No | No se debe recopilar |
| Mensajes<ul><li>Correos electrónicos</li><li>Mensajes SMS o MMS</li><li>Otros mensajes in-app</li></ul> | No | No se debe recopilar |
| Fotos o videos<ul><li>Fotos</li><li>Videos</li></ul> | No | No se debe recopilar |
| Archivos de audio<ul><li>Grabaciones de voz o sonido</li><li>Archivos de música</li><li>Otros archivos de audio</li></ul> | No | No se debe recopilar |
| Calendario<ul><li>Eventos del calendario</li></ul> | No | No se debe recopilar |
| Actividad en la aplicación<ul><li>Vistas de página y toques in-app</li><li>Historial de búsqueda in-app</li><li>Aplicaciones instaladas</li><li>Otro contenido generado por el usuario</li><li>Otras acciones</li></ul> | Ver notas -> | AppsFlyer mide de forma predeterminada los inicios de las aplicaciones que pueden considerarse vistas de página u otras acciones.<br /><br />Además, si configuras tu aplicación para medir eventos in-app específicos, debes responder Sí de acuerdo con tus configuraciones. |
| Navegación web | No | No se debe recopilar |
| Información y rendimiento de la aplicación<ul><li>Registros de fallas</li><li>Diagnósticos</li><li>Otros datos de rendimiento de la aplicación</li></ul> | No<br /><br />Sí<br /><br />Sí | La hora de inicio o los niveles de batería se pueden recibir con fines de detección de fraude. |
| Dispositivo u otros identificadores<ul><li>Dispositivo u otros identificadores (por ejemplo, IMEI, MAC e ID de anuncio)</li></ul> | Ver notas -> | El SDK de Android de AppsFlyer, de forma predeterminada, recoge el Identificador de Anunciante de Google (GAID).   <br />Puedes deshabilitar la recopilación del ID de publicidad en el SDK [revocando el permiso AD\_ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission) y llamando a [setDisableAdvertisingIdentifiers](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib). |

"Compartido" significa la transferencia de datos a un tercero (ya sea fuero o dentro del dispositivo)."

Las excepciones incluyen lo siguiente:

* Transferencias a proveedores de servicios que procesan los datos en tu nombre y según tus instrucciones
* Transferencias necesarias para fines legales (por ejemplo, en respuesta a una solicitud del gobierno)
* Acción del usuario final o basada en una divulgación y consentimiento destacados in-app
* Datos anónimos

Es importante tener en cuenta que si bien AppsFlyer actúa únicamente como un proveedor de servicios en tu nombre y según tus instrucciones, si estás compartiendo datos con redes de terceros (por ejemplo, a través de postbacks, SRN y audiencias), esto se considerará compartido.  Por lo tanto, cada desarrollador de aplicaciones deberá evaluar sus configuraciones e integraciones de partners y responder en consecuencia.

## Procesamiento efímero

El procesamiento efímero se refiere a los datos procesados en la memoria, solo durante el período de tiempo necesario para procesar una acción específica en tiempo real y sin otro propósito. Dada la naturaleza de los servicios de AppsFlyer, los datos procesados por AppsFlyer en tu nombre no se procesan efímeramente.

## Elección del usuario

Con carácter general, los datos recopilados son necesarios para la realización de los servicios. Dicho esto, los desarrolladores de aplicaciones tienen la capacidad de someter cualquier recopilación de datos a controles de aceptación o exclusión opcional.

## Finalidad

Google ha proporcionado una lista de propósitos de los cuales los desarrolladores de aplicaciones deben elegir como se detalla en la tabla siguiente. Debes identificar el propósito relevante.

| Finalidad | Notas |
| --- | --- |
| Funcionalidad de la aplicación | Selecciona esta opción si usas los datos para habilitar cualquier función en la aplicación. |
| Analíticas | Sí |
| Comunicaciones para desarrolladores | Selecciona este opción si utilizas los datos para enviar notificaciones a los usuarios. |
| Publicidad y marketing | Selecciona esta opción si compartes el tipo de datos con un tercero con el fin de mostrar anuncios de terceros o si se usa para promocionar productos o enviar notificaciones push. |
| Fraude, prevención, seguridad y cumplimiento | Sí |
| Personalización | Selecciona esta opción si utilizas los datos para cualquier tipo de personalización de productos. |
| Gestión de cuentas | Selecciona esta opción si utilizas los datos para la configuración y gestión de cuentas de usuario. |

> 📄 **Consulta también**
>
> Para aprender más sobre cómo prepararse para la sección de seguridad de Google Play y cómo completar el formulario requerido, lee estos artículos:
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Preparación para la nueva sección de seguridad de Google Play</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Proporcionar información para la sección de seguridad de datos de Google Play</Anchor>

<div data-zendesk-anchors="disclaimer=advertencia h_01HDP3NTTKH3X3585J3DM6MCDC=advertencia introduction=introducci%C3%B3n h_01HDP3NTTK1BDTZTHNWRM3411D=introducci%C3%B3n audience=audiencia h_01HDP3NTTKQE2N0HZDNGK2ZQPC=audiencia google-safety-form-questionnaire=formulario-de-seguridad-de-google-cuestionario h_01HDP3NTTKK6DJSF49326V3BEG=formulario-de-seguridad-de-google-cuestionario data-collection-and-security=recopilaci%C3%B3n-y-seguridad-de-datos h_01HDP3NTTK89K8YPT6C7S9QM3W=recopilaci%C3%B3n-y-seguridad-de-datos data-types=tipos-de-datos h_01HDP3NTTK9DYZTQ2B64QMKGX8=tipos-de-datos ephemeral-processing=procesamiento-ef%C3%ADmero h_01HDP3NTTKT7C0TGVCZJ4GR9BF=procesamiento-ef%C3%ADmero user-choice=elecci%C3%B3n-del-usuario h_01HDP3NTTK4CT8MJ1S84MAG8VD=elecci%C3%B3n-del-usuario purpose=finalidad h_01HDP3NTTKD3MND388MWCC6PAT=finalidad h_01HDP3RBENN69F150ESQMSVP3Q=consulta-tambi%C3%A9n" />
