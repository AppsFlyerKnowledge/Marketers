---
title: Guía de onboarding a la atribución basada en personas
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-08-12T12:11:13Z'
  id: 360013821097
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360013821097
---
> **De un vistazo:** Lista de verificación para la configuración de PBA

## Configuración de la PBA

La configuración de la PBA consiste en varios elementos de acción que se describen aquí y se enumeran en la tabla a continuación.

* Comunícate con tu CSM o representante de ventas de AppsFlyer para habilitar PBA.
* Agrupar las propiedades digitales de la marca en un paquete de marca.
* Integrar el SDK web en tu sitio web y el SDK móvil en tu aplicación.
* AppsFlyer recoge y atribuye los datos.
  * Los datos se recogen de varias fuentes diferentes.
  * Los datos registrados se dividen en puntos de contacto y eventos.
  * Los eventos se atribuyen a la última visita web no directa en los 30 días anteriores.
  * Los anunciantes pueden designar algunos eventos como eventos de conversión. Por ejemplo, las compras. Los eventos de conversión se analizan en los paneles de control.
  * El raw data se utiliza para realizar análisis de datos personalizados.
* Analizar las trayectorias de los clientes para optimizar las campañas.

### Pasos para la configuración de PBA

Antes de comenzar, Comunícate con tu CSM o representante de ventas de AppsFlyer para habilitar PBA. Luego comienza la configuración. Las tareas de configuración se detallan en la tabla. Descarga esta  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">hoja de cálculo</Anchor> para registrar tu progreso.

**¡Práctica recomendada!** Implementar <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">CUID</Anchor> en la aplicación y en tu sitio web. AppsFlyer recibirá el CUID cuando un usuario se registre o inicie sesión.

<table><thead><tr><th> </th><th>Responsabilidad</th><th>Acciones</th><th>Observaciones</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>AppsFlyer </p></td><td><ul><li> <span><a href="./adding-an-app-to-appsflyer" target="_blank">Agrega una aplicación web</a> a tu cuenta de AppsFlyer. La aplicación web especifica la URL del sitio web para el que deseas medir el tráfico y</span>Se utiliza para evitar <a href="./pba-media-source-attribution-rules" target="_blank">la autoatribución</a>.</li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">Configurar paquetes de marca</a>; combinan las propiedades digitales de una marca (aplicaciones móviles y una aplicación web).</span> </li><li>Especifica <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">dominios excluidosadicionales</a>.</li></ul></td><td><ul><li><span>Los análisis y reportes se agregan dentro de la marca.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> Webmaster </td><td><ul><li>Instala el <a href="./pba-web-sdk-integration-guide" target="_blank">SDK web</a> en el sitio web definido por la aplicación web. </li><li>Configurar el SDK web para:  <ul><li>Récord de visitas</li><li>Registrar eventos</li><li><mark> Establecer <a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a> </mark></li><li>Implementación de pruebas con la <a href="./test-pba-web-sdk-integration" target="_blank">herramienta de pruebas SDK</a> </li></ul></li></ul></td><td><ul><li><span>El SDK registra las visitas y los eventos.</span></li><li><span>La integración se admite por completo a través de Google Tag Manager (GTM), Adobe o Tealium.</span></li><li> Obligatorio  Llama a SetCustomerUserID() inmediatamente después de que un usuario se registre o inicie sesión. Si no tienes un CUID, pide alternativas a tu CSM. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>AppsFlyer</p></td><td><p>Asegúrate de que el webmaster haya utilizado la <a href="./test-pba-web-sdk-integration" target="_blank">herramienta de prueba del SDK</a> para verificar que el sitio web para el cual está configurado el SDK:</p><ul><li>Récord de visitas</li><li>Registrar eventos</li><li>Establecer el CUID</li></ul></td><td><p><mark> AppsFlyer! ¡Anunciante! No continúes hasta completar este paso.  </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>Desarrollador y anunciante</p></td><td><p>[Opcional] API de <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">servidor a servidor web</a></p></td><td>Reporta eventos relacionados con la web, como la renovación automática de suscripciones.</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>AppsFlyer</p></td><td><ul><li> <span>Marcar </span>eventos de conversión: <ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">Eventos web</a></span></li><li><span>[Opcional] <a href="./pba-brand-bundles-and-settings#inapp-event-settings" target="_blank">Eventos in-app</a>.</span></li></ul></li></ul></td><td><ul><li><span>Espera a que el procesamiento diario\* se complete antes de hacerlo.</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>AppsFlyer</p></td><td><p>Empieza a usar los paneles de control.</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Atribución del sitio web</a></li><li><a href="./pba-web-assisted-installs" target="_blank">Instalaciones asistidas por web</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>AppsFlyer</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Configurar el Data Locker</a></td><td><p>Proporciona acceso a reportes de raw data de PBA, incluidos puntos de contacto, eventos estándar y de conversión, y reportes especializados para instalaciones asistidas por web.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>AppsFlyer</p></td><td><p>[Opcional]<br/>Comienza a utilizar <a href="./pba-raw-data-reports" target="_blank">raw data</a></p></td><td><p>Los datos están disponibles después del procesamiento diario.\*</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* Debido al procesamiento, los datos están disponibles 10 horas después de la medianoche (UTC) del día del evento. Lo que significa que los eventos del lunes están disponibles el martes a las 10:00 UTC. </td></tr></tbody></table>

## Adquisición de datos de la PBA a través de SDK/API

|  | Plataforma web | Plataforma móvil (aplicación) |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide">Web</Anchor><ul><li>La etiqueta JavaScript del SDK instalado en el sitio web.</li><li>Reporta las visitas al sitio web y los eventos web.</li></ul> | <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">Móvil</Anchor><ul><li>El SDK de la aplicación integrado en iOS, Android, Unity, etc.</li><li>Reporta las instalaciones de la aplicación y acciones del usuario que ocurren en la aplicación.</li></ul> |
| API de servidor a servidor | <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s">Servidor a servidor web</Anchor><ul><li>Reporta los eventos que ocurren en los servidores de backend (no en la web).</li><li>Ejemplo: Renovación de suscripciones.</li></ul> | <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">Servidor a servidor móvil</Anchor><ul><li>Reporta los eventos que ocurren en los servidores de backend (no en la aplicación).</li><li>Ejemplo: Renovación de suscripciones.</li></ul> |

<div data-zendesk-anchors="setting-up-pba=configuraci%C3%B3n-de-la-pba 01H8V1XPAHGFVJRKM56S2ZQTBD=configuraci%C3%B3n-de-la-pba pba-setup-steps=pasos-para-la-configuraci%C3%B3n-de-pba 01ECF26CMN668ZZV6XNZA3W692=pasos-para-la-configuraci%C3%B3n-de-pba pba-dataacquisition-via-sdkapi=adquisici%C3%B3n-de-datos-de-la-pba-a-trav%C3%A9s-de-sdkapi 01H8V1XPAH23BV25ZCMFR7MM9Q=adquisici%C3%B3n-de-datos-de-la-pba-a-trav%C3%A9s-de-sdkapi" />
