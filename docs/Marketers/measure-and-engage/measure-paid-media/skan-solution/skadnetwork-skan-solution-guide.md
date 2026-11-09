---
title: Guía de la solución SKAdNetwork (SKAN)
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-08-12T12:21:20Z'
  id: 360011420698
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360011420698
---
> **Resumen**: Atribuir instalaciones de aplicaciones usando SKAN.

<Image align="center" alt="5754" src="https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png" />

<div id="skan" />

## SKÁN

SKAdNetwork (SKAN), parte de Apple iOS, permite a los anunciantes medir el rendimiento de las campañas mientras se preserva la privacidad del usuario. SKAN opera sin IDFA ni otro identificador publicitario. SKAN funciona sin necesidad del consentimiento de ATT.

<div id="tip" />

> 👍 **Consejo**
>
> * A partir de iOS 15, recomendamos enviar <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">copias de postback de SKAN</Anchor> a AppsFlyer. Esto permite a AppsFlyer verificar que los valores de conversión en los postbacks no han sido alterados.
> * ¿Te gustaría entender mejor la solución SKAN de AppsFlyer? Consulta este breve y educativo <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">curso en el Portal de Aprendizaje de AppsFlyer</Anchor>.

**Definiciones**

* <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">SDK</Anchor><Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">: Versión actual del SDK de iOS de AppsFlyer integrado en una aplicación.</Anchor>
* **Ventana de medición de SKAN**: Aplicable para SKAN 4+. Existen 3 períodos de tiempo (ventanas) en los que se mide la actividad del usuario posterior a la instalación:
  * Ventana 1: 1-2 días
  * Ventana 2: 3-7 días
  * Ventana 3: 8-35 días
* **Valor de conversión (CV)**: La calidad del usuario reportada en los postbacks enviados por iOS al final de las ventanas de medición de SKAN 4 o, para SKAN 3 y anteriores, al final de la Ventana de Actividad. El SDK de AppsFlyer configura los CV automáticamente. Sin embargo, si quieres configurar el CV, utiliza <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">Decodificar</Anchor> para cargar tu archivo de mapeo de CV.
  * Para SKAN 4+, existen valores de conversión tanto detallados como generales.
* **Estudio de Conversión**: Solución de AppsFlyer para mapear valores de conversión (CV) de infraestructura a eventos.
* **Solución:** SDK, Infraestructura, Estudio de Conversión y la plataforma AppsFlyer trabajando en conjunto. La solución SKAN de AppsFlyer ofrece a los anunciantes y redes publicitarias datos de LTV a través de análisis de dashboards, reportes y postbacks.
* **Ventana de Actividad:** Aplicable para SKAN 3 y anteriores. Tiene una duración establecida, con un predeterminado de 24 horas, comenzando desde la primera vez que se abre la aplicación. Si estás usando SKAN 4+, pero los dispositivos de los usuarios o las redes publicitarias aún no son compatibles con SKAN 4, la ventana de actividad es de 48 horas.

Este artículo describe las características relevantes de la infraestructura y la solución. Para configurar la medición, revisa <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

<div id="about-apple-skan" />

<Accordion title="Acerca de Apple SKAN">

| Características | Descripción |
| --- | --- |
| Requisitos previos | Para habilitar el uso de SKAN en la aplicación:<ul><li>La aplicación anunciada (tu aplicación), es decir, la app que se publicita, implementa el SDK de AppsFlyer* para configurar el CV. Alternativamente, puedes configurar el CV usando el <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">Modo de decodificación</Anchor>.</li><li>Las aplicaciones del editor (app que muestra un anuncio) deben <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">configurar una aplicación fuente</Anchor>.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">Las redes publicitarias deben registrarse con Apple</Anchor></li></ul>**\*Nota:** Asegúrate de que no tengas otro SDK que configure valores de conversión integrado en tu app. |
| Compatible | <ul><li>La versión de SKAdNetwork compatible depende de la versión de iOS:<ul><li>iOS 11-13: V1 (sólo instalaciones sin CV)</li><li>iOS 14-14.5: V2+ (con CV)</li><li>iOS 14.6-16: V3 (con CV)</li><li>iOS 16.1+: V4+ (con CVs para 3 ventanas y valores tanto finos como gruesos)</li></ul></li><li>Atribución de app a app</li></ul> |
| Limitaciones | <ul><li>Los anuncios de Apple (Search Ads) son compatibles con las versiones 1–3 de SKAN. El soporte para view-through y SKAN 4 está pendiente</li><li>La web móvil no es compatible</li><li>Hasta SKAN 4, la numeración de ID de campaña está <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">restringida al rango 1-100</Anchor>; significando 100 valores únicos por red publicitaria por aplicación. Las redes publicitarias proporcionan a AppsFlyer su ID y nombre de campaña. Esto se refleja en los dashboards y reportes de AppsFlyer.</li><li>A partir de SKAN 4, el identificador de fuente va del 1 al 10.000.</li><li>Instalaciones orgánicas: SKAN no admite instalaciones orgánicas.</li><li>Reenganche.</li></ul> |
| Principios de atribución de SKAN | <ul><li>SKAN realiza atribuciones usando el siguiente <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">modelo de atribución</Anchor>:<ul><li>Un usuario hace clic en un anuncio, dentro de los 30 días instala (descarga) la app, y luego, dentro de los 60 días, abre la app por primera vez.</li><li>Un usuario ve un anuncio, instala (descarga) la app en las siguientes 24 horas, y luego, en un plazo de 60 días, abre la app por primera vez.</li><li>A partir de SKAdNetwork V2.2, la atribución por clic tiene prioridad sobre la atribución por visualización. La versión de SKAN depende de la versión de iOS.</li><li>iOS envía postbacks a la red publicitaria atribuida. A partir de iOS 15, los anunciantes pueden enviar una copia del postback directamente a AppsFlyer.</li></ul></li></ul> |
| Anonimato de multitudes | Apple envía algunos postbacks con datos limitados para proteger la privacidad del usuario. Según Apple, el postback no incluirá los CV finos o gruesos, ni el ID de la aplicación fuente o el identificador de fuente completo si esto contraviene los límites de privacidad de Apple. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Más información</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## Solución SKAN de AppsFlyer

AppsFlyer proporciona resultados de atribución agregados de iOS mediante los postbacks SKAN de iOS. Estos postbacks son enviados por iOS a las redes publicitarias, que luego los reenvían a AppsFlyer. Los postbacks incluyen registros de atribución anónimos enriquecidos con un valor de conversión (CV) establecido por el anunciante. El CV es una medida de la calidad del usuario durante una ventana inicial tras la instalación.

La solución SKAN de AppsFlyer ofrece a los anunciantes:

* Datos de SKAN en dashboards y reportes derivados de la agregación de postbacks de todas las redes publicitarias, enriquecidos con otros datos como el costo.
* La capacidad de controlar, a través de AppsFlyer Conversion Studio, lo que mide el CV, sin necesidad de realizar cambios en el código de la aplicación. El CV se puede utilizar para medir ingresos, interacciones o eventos de conversión.  
  **Nota:** Solo el SDK de AppsFlyer debería tener la capacidad de establecer valores de conversión. Asegúrate de que no tengas otro SDK que configure valores de conversión integrado en tu app.

<div id="principles-and-flow" />

<Accordion title="Principios y flujo">

<div id="skan-attribution-flow" />

#### **Flujo de atribución de SKAN**

<Image align="center" alt="SKAN_flow_-_Diagrama_de_afinidad_2.png" src="https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png" />

1. El anunciante configura los ajustes de medición de SKAN en AppsFlyer Conversion Studio.
2. El usuario abre la aplicación por primera vez.
3. Durante cada ventana, AppsFlyer establece el CV basándose en las acciones del usuario y en el esquema de CV definido.
4. Una vez cerrada la ventana, iOS envía el postback a la red publicitaria y una copia del mismo a AppsFlyer. El postback llega con un cierto retraso:
   * Para la ventana de medición 1 de SKAN 4: 24-48 horas
   * Para las ventanas de medición 2 y 3 de SKAN 4: 24-144 horas
   * Para SKAN 3: 24-48 horas después del último aumento en el valor del CV.
5. Las copias de postback enviadas desde el dispositivo iOS a AppsFlyer se redirigen al punto final definido por el anunciante. Consulte <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar copias de postback de SKAN a AppsFlyer.</Anchor>
6. La red publicitaria envía postbacks enriquecidos a AppsFlyer, o SRN comunica los datos de postback a través de API.
7. AppsFlyer valida y decodifica el CV. Los datos decodificados se registran y se asignan antes de estar disponibles en AppsFlyer mediante dashboards, reportes y API.

Para superar las limitaciones funcionales y estructurales de la infraestructura de SKAdNetwork, la solución SKAN de AppsFlyer considera las características en la siguiente tabla.

| Características | Descripción |
| --- | --- |
| <span id="data-collection"></span>Recopilación de datos | <ul><li>Para el anunciante, los postbacks de SKAdNetwork se recopilan de varias redes publicitarias.</li><li>Los anunciantes no necesitan integrarse individualmente con cada red publicitaria, lo cual es una tarea compleja y tediosa.</li></ul> |
| <span id="data-validation"></span>Validación de datos | <ul><li>Asegura que los postbacks estén firmados por Apple, lo cual reduce las posibilidades de manipulación.</li><li>Utiliza el campo de ID de transacción para validar que los postbacks sean únicos.</li></ul> |
| <span id="data-enrichment"></span>Enriquecimiento de datos | <ul><li>Enriquece los datos de postback de SKAdNetwork con otra información para proporcionar un análisis completo del ROI. Por ejemplo, el nombre de la campaña proporcionado por la red publicitaria, entre otros.</li><li>Incluyen impresiones, clics, costos y más.</li></ul> |
| <span id="data-delivery"></span>Entrega de datos | Los datos enriquecidos de SKAdNetwork están disponibles a través de lo siguiente:<ul><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dashboard de la solución SKAdNetwork</Anchor></li><li>[Reportes descargables](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Integración sin complicaciones | <ul><li>La encapsulación completa permite un esfuerzo casi nulo para el anunciante a través de la página de configuración de la aplicación.</li><li>No se requiere programación. La aplicación necesita la última versión del SDK.</li><li>Incluye soporte para los cambios anticipados por Apple en la infraestructura de SKAdNetwork.</li></ul> |
| <span id="agility"></span>Agilidad | Los anunciantes pueden cambiar las configuraciones de medición según sea necesario desde el dashboard. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Estudio de conversión">

El <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Conversion Studio</Anchor> de AppsFlyer es la parte central de la solución SKAN. Le ofrece la máxima flexibilidad para que cada valor de conversión cuente. Tú decides con precisión qué datos de medición se deben codificar dentro del CV, incluyendo qué actividad y durante cuánto tiempo medir después de la instalación. Existen varios modos de medición que puedes emplear para configurar los ajustes de tu CV.

| Tipo | Modo de medición | Descripción | Ventana de actividad |
| --- | --- | --- | --- |
| Flexible | SKAN 4.0<br /><br />[Mejores prácticas] | Configura una combinación de mediciones de ingresos, conversiones (eventos en la aplicación) y participación durante 3 ventanas de medición configurables. | <ul><li>Ventana 1: 1-2 días</li><li>Ventana 2: 3-7 días</li><li>Ventana 3: 8-35 días</li></ul> |
| Flexible | <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#custom">Personalizado</Anchor> | Configura una combinación de mediciones de ingresos, conversiones (eventos dentro de la app) y participación a lo largo de una ventana de actividad configurable. | 12h-63 días |
| Fijo | Ingresos<br /><br />[Por defecto]<br /><br />[Heredado] | Mide los ingresos utilizando uno de los siguientes intervalos:<ul><li>$1-$630 en incrementos de $10</li><li>$1-$63 en incrementos de $1</li><li>$0.01-$0.63 en incrementos de $0.01</li></ul> | 24 horas |
| Fijo | Conversión<br /><br />[Heredado] | Selecciona de 1 a 6 eventos en la aplicación. | 24 horas |
| Fijo | Participación<br /><br />[Heredado] | Número de veces que un usuario realiza un evento | 24 horas |
| Flexible | <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">Descodificar</Anchor> | <ul><li>Crea tu propio mapeo de evento a CV y configura el CV directamente en la aplicación. Usa esta opción si no puedes integrar el SDK de AppsFlyer en tu aplicación. Para utilizar Decode, ve a **SKAN Conversion Studio,** haz clic en opciones (⋮) y selecciona **Subir archivo de mapeo personalizado**.</li></ul> | 12-1512h (63 días) |

</Accordion>

<div id="additional-skadnetwork-information" />

## Información adicional de SKAdNetwork

<div id="reporting-options" />

<Accordion title="Opciones de reportes">

Los reportes de SKAdNetwork no contienen identificadores a nivel de usuario.

| Nombre del reporte | Tipo | Enriquecido por AppsFlyer | Método de entrega | Función Premium |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">Reporte de rendimiento agregado de SKAN.</Anchor><br /><br />Agregados de instalaciones, eventos en la app e ingresos. Los datos son similares a los que se encuentran en el dashboard de SKAN. | Agregado usando la fecha de instalación o de llegada del postback | Sí | API | No |
| <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-postback-arrival-date-api">Reporte de postback agregado de SKAN</Anchor>.<br /><br />Postbacks de SKAN agregados al nivel más detallado posible. | Agregación de postbacks según la fecha de llegada del postback | No | API | No |
| <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports#raw-data-report-types">Reportes de raw data (nivel de fila) de SKAN a través de Data Locker</Anchor> (con ejemplos).<br /><br />Reportes disponibles:<ul><li>Postbacks enviados por iOS con enriquecimiento de datos de socios de la red publicitaria</li><li>Instalaciones</li><li>Re-descargas</li><li>Eventos en la app</li><li>Dimensiones publicitarias de SRN</li></ul> |  | Sí | Casillero de datos | Sí. Se requiere raw data. No se necesita suscripción a Data Locker. |
| Datos SKAN a través de la API push |  | Sí | API push | Sí |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="Lista de verificación para la implementación de la solución SKAdNetwork">

| N.º | Acción | Descripción | Responsabilidad |
| --- | --- | --- | --- |
| 1 | Preparar | <ul><li>Lea la <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">guía de la solución SKAdNetwork</Anchor></li><li>Lectura adicional: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Prepárese para iOS 14</Anchor></li></ul> | Comercializador, Desarrollador |
| 2 | Configurar | En AppsFlyer, configure la solución SKAdNetwork en <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>. | Comercializador |
| 3 | Preparar la aplicación | Migre la aplicación a AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">V6 SDK</Anchor><ul><li>No es necesario cambiar la lógica ni el código de la aplicación.</li><li>La solución AppsFlyer SKAN se basa en eventos dentro de la aplicación para configurar los eventos de envío de CV de manera habitual. No se requiere prueba específica para la solución SKAN.</li><li>Envíe la aplicación a la App Store</li><li>No se requiere registrarse ni realizar ningún proceso de SKAdNetwork en la App Store.</li></ul> | desarrollador |
| 4 | Integraciones de socios | Los socios de la red publicitaria deben integrarse con AppsFlyer utilizando la integración SKAdNetwork. ¡Atención! Nota: La simulación de SKAdNetwork de AppsFlyer contiene los datos de todos sus socios independientemente de su estado de integración actual. Esto no se aplicará a los datos en vivo informados por los postbacks de SKAdNetwork.<br /><br />En relación con los socios que ejecuten sus campañas, complete lo siguiente según sea necesario:<br /><br />**No SRN**:<ol><li>Verifique que el socio tenga una insignia de capacidad <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#c-transaction-id">SKAdNetwork</Anchor> de AppsFlyer y que en la interfaz del socio, el reporte de campañas de SKAdNetwork esté habilitado.</li><li>Verifique que los [nombres de eventos en la aplicación estén vinculados](#sending-postbacks-to-integrated-partners) a los nombres de eventos en la aplicación del socio.</li></ol>**Anuncios Meta**:<ul><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads">Configure la interoperabilidad de AppsFlyer SKAdNetwork con los anuncios Meta</Anchor></li></ul> | Comercializador |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Guía de resolución de problemas">

| Síntoma | Descripción |
| --- | --- |
| El dashboard no muestra instalaciones no orgánicas. | <ol><li>Verifique que la medición **SKAdNetwork** esté activada.<ol><li>Vaya a **Configuración** > **SKAN Conversion Studio.**</li><li>Haga clic en las opciones (⋮), revise la configuración de medición de SKAN.</li></ol></li><li>Verifique que su versión de SDK sea 6.2.6 o superior.<ul><li>Para hacerlo, vaya a **Integración** > **Información del SDK > Usuarios por versión del SDK.**</li></ul></li><li>Si utiliza complementos SDK, verifique que implemente una versión que soporte AppsFlyer SKAdNetwork.</li><li>Verifique que sus socios de la red publicitaria estén integrados con AppsFlyer y que reenvíen los postbacks de iOS a AppsFlyer.</li></ol> |
| El dashboard muestra instalaciones no orgánicas, pero no registra ningún evento dentro de la aplicación. | <ol><li>Verifique que su versión de SDK sea 6.2.6 o superior.<ul><li>Para hacerlo, vaya a **Integración** > **Información del SDK > Usuarios por versión del SDK.**</li></ul></li><li>Si utiliza complementos SDK, verifique que implemente una versión que soporte AppsFlyer SKAdNetwork.</li><li>¿Estás enviando eventos a través de S2S? ¿Estás enviando eventos a través de S2S? Si es así, asegúrate de que la opción **Registrar eventos dentro de la aplicación enviados por la API de servidor a servidor** esté activada.<ol><li>Vaya a **Configuración** > **SKAN Conversion Studio.**</li><li>**Haz clic en opciones (⋮) y comprueba que la configuración de S2S esté activa.** Nota: En el modo de medición personalizado y de decodificación, esta configuración está siempre activa y no se puede modificar.</li></ol></li></ol> |
| El dashboard muestra instalaciones y algunos eventos dentro de la aplicación. Faltan ciertos eventos dentro de la aplicación. | <ol><li>¿Estás enviando eventos a través de S2S? ¿Estás enviando eventos a través de S2S? Si es así, asegúrate de que la opción **Registrar eventos dentro de la aplicación enviados por la API de servidor a servidor** esté activada.<ol><li>Dirígete a **Configuración** > **SKAN Conversion Studio.**</li><li>**Haz clic en opciones (⋮) y comprueba que la configuración de S2S esté activa.** Nota: En el modo de medición personalizado y de decodificación, esta configuración está siempre activa y no se puede modificar.</li></ol></li><li>Revisa tus <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports#raw-data-report-types">datos brutos de postback</Anchor> para verificar si se han reportado todos los eventos.</li></ol> |
| Las ubicaciones geográficas (países) son confusas. | Los datos geográficos se derivan de la siguiente manera:<ul><li>Según el país asociado a una campaña e informado a AppsFlyer por la red publicitaria.</li><li>Usando la dirección IP del dispositivo. A partir de iOS 14.6, esta dirección es una proxy y no representa realmente la geolocalización del usuario.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Tiempo desde la instalación de la app hasta la actualización del dashboard y los reportes">

| Clave | Nombre del elemento | Descripción | Ejemplo A | Ejemplo B | Ejemplo C | Ejemplo D | Ejemplo E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Ventana de medición 1 de SKAN 4 | <ul><li>Durante esta ventana, los CV son configurados por la aplicación.</li><li>0-2 días</li><li>La ventana se puede bloquear antes de los 2 días en Conversion Studio</li></ul> | - | - | 2 días | - | - |
| B | Ventana de medición 2 de SKAN 4 | <ul><li>Durante esta ventana, el CV lo define la aplicación.</li><li>3-7 días</li><li>La ventana se puede cerrar antes de los 7 días en Conversion Studio</li></ul> | - | - | - | 7 días | - |
| C | Ventana de medición 3 de SKAN 4 | <ul><li>Durante esta ventana, el CV lo define la aplicación.</li><li>8-35 días</li><li>La ventana se puede cerrar antes de los 35 días en Conversion Studio</li></ul> | - | - |  | - | 35 días |
| D | Retraso de postback en ventana de medición 1 de SKAN 4 | 24-48 horas | - | - | 24-48 h | - | - |
| E | Retraso en ventana de medición 2-3 de SKAN 4 | 24-144 horas | - | - | - | 24-144h | 24-144h |
| F | Ventana de actividad<br /><br />(No aplicable para SKAN 4) | <ul><li>Durante esta ventana, el CV lo establece la aplicación.</li><li>La ventana comienza al abrirse la aplicación por primera vez.</li><li>Duración de 12 horas a 63 días.</li></ul> | 24 horas | 72 horas | - | - | - |
| G | Temporizador de SKAdNetwork<br /><br />(No aplicable para SKAN 4) | <ul><li>Cuenta atrás: 24 horas</li><li>Cada vez que el CV aumenta, se reinicia el temporizador. Esto significa que la cuenta atrás empieza desde las 24 horas.</li></ul> | 0-24 horas | 0-24 horas | - | - | - |
| H | Retraso aleatorio de SKAdNetwork<br /><br />(No aplicable para SKAN 4) | Tiempo de retraso al azar en devolución. La cuenta atrás empieza al finalizar el periodo definido por F+G. | 0-24 horas | 0-24 horas | - | - | - |
| I | Procesamiento por AppsFlyer | Los postbacks recibidos en un día se procesan al término del día UTC comenzando a las 00:01 del día siguiente. Los datos están disponibles 8 horas después. Esto significa que el procesamiento tarda entre 8 y 32 horas. Retraso medio de 20 horas. Por ejemplo, un postback recibido el lunes se procesa el martes. El dashboard se actualiza a las 08:00 UTC. | 8-32 horas | 8-32 horas | 8-32 horas | 8-32 horas | 8-32 horas |
| J | Resumen | El tiempo total que puede transcurrir | 32-104 horas | 80-152 horas | 80-128 horas | 200-344 horas | 872-1016 horas |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Métricas orgánicas en el contexto de SKAdNetwork">

Las métricas orgánicas en el dashboard de SKAdNetwork se calculan utilizando el siguiente mecanismo:

* Los **ingresos orgánicos** solo están disponibles para los ingresos en modo <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#fixed-modes">fijo</Anchor> o heredado.
* Los eventos **orgánicos in-app** solo están disponibles para "Conversión" en modos <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#fixed-modes">fijos</Anchor> o heredados.
* Para los **modos no heredados** (<Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#skan-4">SKAN4</Anchor>, codificación personalizada y modos de decodificación), los datos orgánicos están disponibles solo para instalaciones.
* Apple SKAdNetwork envía postbacks relacionados con los usuarios que instalan después de interactuar con una fuente de medios. Esto proporciona las métricas no orgánicas.
* Los dashboards de atribución de AppsFlyer contienen métricas de todas las instalaciones, independientemente de la fuente.  Consulte <Anchor target="_blank" href="/marketers/es/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">ver la atribución de AppsFlyer en paralelo con la atribución de SKAN</Anchor>.
* Utilizando estos datos, las métricas orgánicas se calculan como A-B donde:
  * A = Total de todos los usuarios según el dashboard general tradicional
  * B = Usuarios no orgánicos según lo informado por los postbacks de SKAdNetwork

**Advertencia relacionada con los anuncios de búsqueda de Apple**: Las instalaciones generadas por Apple Search Ads en el dashboard tradicional no son orgánicas. Sin embargo, en el contexto de SKAdNetwork, forman parte de la métrica orgánica.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la red publicitaria | Las redes publicitarias reciben postbacks |
| Agencias | No está soportado. Esto significa que las agencias no deben habilitar redes publicitarias que ejecuten campañas de SKAdNetwork. ¡Agencia! Pida al anunciante que habilite la red publicitaria, no lo haga usted mismo. Las agencias pueden indicar que trajeron al usuario implementando <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding#campañas-de-agencias-de-skadnetwork">reconocimiento de agencia SKAN</Anchor>. |
| Transparencia de la agencia | N/D |
| Zona horaria | UTC |
| Truemoney | USD (Dólar estadounidense) |
| Datos orgánicos | Basado en datos de eventos del SDK. Por ejemplo, las métricas de instalación orgánica se calculan de la siguiente manera: Datos de todas las instalaciones reportadas por el SDK menos las instalaciones no orgánicas reportadas por SKAdNetworks. |
| Datos no orgánicos | Basado en los postbacks de SKAdNetwork |
| Actualización de datos | Diariamente |
| Datos históricos | Fecha más temprana de disponibilidad de iOS 14 (16 de septiembre de 2020) |
| Acceso de usuario | Los usuarios de la cuenta deben tener los <Anchor target="_blank" href="/marketers/es/docs/user-management">permisos necesarios</Anchor> |
| App clips | Los app clips se atribuyen a lo orgánico en el dashboard de SKAdNetwork. Utiliza el dashboard general para ver las fuentes de medios de invocación. |

</Accordion>

<div id="skan-integrated-partners" />

## Socios integrados de SKAN

<div id="recording-ad-revenue" />

<Accordion title="Registro de ingresos por publicidad">

Atribuye los ingresos publicitarios generados durante las ventanas de medición de SKAdNetwork a la campaña que atrae al usuario. Actualmente, esto está limitado a los anunciantes integrados con ingresos publicitarios a nivel genérico de impresión a través del SDK.

Para registrar los ingresos por publicidad en tu dashboard de SKAN:

* Integra el <Anchor target="_blank" href="/marketers/es/docs/integrate-the-roi360-ad-revenue-sdk-api">SDK de ingresos publicitarios a nivel de impresión genérico</Anchor> en tu aplicación.
* Si utilizas un modo fijo de SKAN Conversion Studio [heredado], <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#report-events-by-servertoserver-api">activa la compatibilidad de servidor a servidor de SKAdNetwork</Anchor>.

**Nota**: Consulta la documentación del <Anchor target="_blank" href="/marketers/es/docs/integrate-the-roi360-ad-revenue-sdk-api">conector SDK genérico</Anchor> para obtener información sobre las fuentes de anuncios disponibles para la mediación.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Envío de postbacks a socios integrados">

AppsFlyer envía postbacks a socios integrados relacionados con la atribución de SKAN (para SKAN 4, los postbacks se envían solo para la ventana 1).

Toma nota de las distintas opciones y requisitos en la tabla que sigue

| Asunto | Descripción |
| --- | --- |
| <span id="transaction-id-sharing"></span>Compartición de ID de transacción | **Acción requerida**: Consulta con el socio integrado si requieren el <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">ID de transacción</Anchor> y configura el ajuste según corresponda.<br /><br />AppsFlyer envía los postbacks del socio de red publicitaria atribuido. Esto significa que enviamos los postbacks decodificados, no una copia del postback de SKAdNetwork recibido desde iOS. Estos postbacks contienen datos de CV decodificados relacionados con la instalación y datos de eventos internos de la aplicación asociados a las acciones realizadas por el usuario durante la ventana de actividad.<br /><br />Como el ID de transacción se puede emplear para decodificar tu CV, no lo compartimos sin tu permiso.<br /><br />**Compartición de ID de transacción**<br /><br />Los anunciantes <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#b-advanced-privacy">habilitan el uso compartido de ID de transacción</Anchor> de la siguiente manera: En AppsFlyer, dirige a **Colaborar** > **Integraciones activas** > selecciona un socio > **pestaña Integración** > **Uso compartido de datos**. |
| <span id="inapp-event-mapping-verification"></span>Verificación de mapeo de eventos en la aplicación | **<span id="1611499069.009700"></span>Acción requerida**: Debes <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">mapear tus eventos dentro de la aplicación</Anchor> con los nombres de eventos del socio correspondientes para que el socio registre correctamente los postbacks.<br /><br />Para cada uno de los socios que llevan a cabo campañas en SKAdNetwork, asegúrese de que el evento dentro de la aplicación esté configurado según el tipo de medición de la aplicación seleccionado.<br /><br />**Para verificar y modificar las asignaciones de eventos dentro de la aplicación de los socios**:<ol><li>En AppsFlyer, dirígete a **Colaborar** > **Integraciones activas**.</li><li>Selecciona al socio.</li><li>Ve a la pestaña **Integración**.</li><li>Verifique y, si es necesario, realice cambios de configuración de la siguiente manera:<ol><li>Activa la **devolución de eventos dentro de la aplicación**.</li><li>Compruebe que los eventos dentro de la aplicación, los **nombres de eventos SDK** configurados en la medición de SKAdNetwork estén correctamente asignados a los **identificadores de eventos de los socios**.</li></ol></li><li>Haz clic en **Guardar integración**.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan">Guía rápida y preguntas frecuentes sobre iOS 14, ATT y SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Configurar la medición con SKAN Conversion Studio (ajustes de SKAdNetwork)</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dashboard de SKAN de AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/skan-integrated-partners-list">Lista de socios integrados con SKAN</Anchor>
> * Interoperabilidad de los socios SKAN que requiere configuración en AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads">Anuncios de Meta</Anchor>
>   * <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads">Anuncios de Google</Anchor>
>   * <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-tiktok-for-business">Tik Tok para empresas</Anchor>
>   * <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="skan=sk%C3%A1n 01H7Z06Z03AQY25A3E45Z47A9G=sk%C3%A1n 01H7Z06Z03CSKH1ZB9RQP6SHA8=consejo 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=soluci%C3%B3n-skan-de-appsflyer 01H7Z06Z04G479NAKBEA33SGSZ=soluci%C3%B3n-skan-de-appsflyer 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=flujo-de-atribuci%C3%B3n-de-skan 01H7Z06Z05EGK5QBDK6G7BJQJK=flujo-de-atribuci%C3%B3n-de-skan 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=informaci%C3%B3n-adicional-de-skadnetwork 01H7Z06Z05556NQ35HMR4E2TRY=informaci%C3%B3n-adicional-de-skadnetwork 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=socios-integrados-de-skan 01H7Z06Z06KGT6ESN42XTJSK2F=socios-integrados-de-skan 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=consulta-tambi%C3%A9n" />
