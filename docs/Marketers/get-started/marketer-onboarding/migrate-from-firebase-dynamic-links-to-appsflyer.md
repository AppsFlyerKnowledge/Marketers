---
title: Migrar de Firebase Dynamic Links a AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-08-22T00:17:31Z'
  id: 16282289097105
  locale: es
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/es/articles/16282289097105
---
> **De un vistazo:** Realiza la transición de Firebase Dynamic Links a AppsFlyer fácilmente con nuestra guía de migración paso a paso.

<Image align="center" alt="53375 imagen de la migración de Firebase KB.png" src="https://files.readme.io/b5340a5b30c160bca2b420052fd60b23f4bfe0de6d2868f91ad4342bee36c7df-30063560499345.png" />

<div id="about-the-migration" />

## Migración

Los <Anchor target="_blank" href="https://firebase.google.com/docs/dynamic-links">Firebase Dynamic Links</Anchor> de Google quedarán obsoletos el 25 de agosto de 2025. A partir de esa fecha, todos los enlaces proporcionados por Firebase Dynamic Links (tanto los alojados en dominios personalizados como en subdominios page.link) dejarán de funcionar y se deshabilitará la creación de nuevos enlaces. Si usas Firebase Dynamic Links, es fundamental que tomes medidas proactivas lo antes posible para migrar tus enlaces a otro lugar y evitar interrupciones en los recorridos de los usuarios desde tus campañas.

AppsFlyer OneLink te permite crear fácilmente enlaces con capacidades de atribución, redirección y deep linking en medios propios o pagados, independientemente del dispositivo, sistema operativo, canal o plataforma. Colabora con AppsFlyer para crear recorridos de usuario personalizados y contextuales que lleven a los usuarios a tu aplicación para maximizar la conversión y los ingresos. Sigue las instrucciones de abajo para empezar a migrar tus Firebase Dynamic Links a AppsFlyer.

<div id="migrate-from-firebase-to-appsflyer" />

## Cómo migrar de Firebase a AppsFlyer

Con el <Anchor target="_blank" href="https://firebase.google.com/support/dynamic-links-faq">anuncio de Google</Anchor> de que cerrarán Firebase Dynamic Links, ahora es el momento de migrar fácilmente a AppsFlyer.

**Para migrar a AppsFlyer:**

**Requisitos previos**

Antes de empezar, necesitarás lo siguiente:

* Tus enlaces dinámicos de Firebase
* Tu desarrollador de aplicaciones

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="1. Creación de la cuenta">

* Crea una cuenta de AppsFlyer
* Agrega usuarios a la cuenta con los permisos adecuados

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="2. Agregación de la aplicación">

* <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega la aplicación</Anchor> en AppsFlyer.
* [Opcional] Cambia la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> predeterminada de 90 días para alinearla con tu definición de usuarios activos.

<Image align="center" alt="agregar" src="https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png" />

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="3. Configuración de la plantilla de OneLink">

**Para este paso, se os necesita tanto a ti como a tu desarrollador de apps**.

Se necesita una plantilla para crear enlaces y experiencias de usuario final. Forma la base de la lógica de redireccionamiento de todos los enlaces de OneLink que crees para tus distintas campañas de marketing.

* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Crea una plantilla de OneLink</Anchor>
  * El marketer debe ser un usuario administrador de AppsFlyer o tener <Anchor target="_blank" href="/marketers/es/docs/user-management">permiso para agregar/editar plantillas de OneLink</Anchor>.

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="4. Configuración del SDK">

**Para este paso, se necesita a tu desarrollador de apps**.Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

El SDK de AppsFlyer integrado en la aplicación es el enlace entre la aplicación y la plataforma de AppsFlyer. Proporciona:

* Enlaces profundos: el SDK permite la implementación de enlaces profundos unificados (UDL)
* Atribución: el SDK reporta las instalaciones de la aplicación, las aperturas de la aplicación, los eventos in-app, etc.

Integra el SDK de AppsFlyer en tu aplicación siguiendo los pasos a continuación.

<div id="appsflyer-sdk-integration-steps" />

#### Pasos para la integración del SDK de AppsFlyer

1. Integra el SDK de AppsFlyer en la aplicación.  
   Consulta las guías para la integración del SDK para <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Android</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">iOS</Anchor>.
2. Asigna los eventos in-app que deseas registrar, utilizando los esquemas de AppsFlyer.  
   Esto se puede hacer a través de <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">SDK</Anchor> o de <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Gestiona el SDK de Firebase.  
   Puedes cambiarte exclusivamente a AppsFlyer, o ejecutar ambos SDK simultáneamente durante unas semanas. Observa un desglose de estas opciones en la tabla que figura a continuación.

| Opción | Qué pasa después del  <br />lanzamiento de la versión actualizada de la aplicación | Impacto |
| --- | --- | --- |
| Eliminar el SDK de Firebase (recomendado) | Solo AppsFlyer registra las nuevas instalaciones y actualizaciones de los usuarios.  <br />Firebase aún muestra los eventos realizados por los usuarios, hasta que los usuarios también actualicen su aplicación. | <ul><li>Transición rápida.</li><li>No hay atribución doble.</li><li>Te permite ver si tienes alguna versión persistente de la aplicación con el SDK de Firebase aún en ella.</li></ul> |
| Mantener el SDK de Firebase durante un período de transición | AppsFlyer y Firebase atribuyen las instalaciones nuevas y reportan eventos. En una fecha posterior, elimina el SDK de Firebase. | <ul><li>La validación de datos es posible. Es decir, puedes comparar los datos de AppsFlyer y de Firebase.</li><li>Doble atribución, lo cual puede provocar cargos duplicados con las redes de publicidad.</li><li>Mayor carga de trabajo.</li></ul> |

4. Una vez completadas todas las demás tareas del alcance del trabajo, actualiza la versión de la aplicación con el SDK de AppsFlyer para el mercado. AppsFlyer atribuye a los usuarios nuevos.   
   **Nota**:
   * Asegúrate de actualizar la aplicación para iOS, Google Play y cualquier mercado fuera de la tienda de Android relevante.
   * Es posible que tu aplicación de Android exista en sitios APK no oficiales, aunque no lo sepas (busca el nombre del paquete de tu aplicación en la web para averiguarlo). Los sitios APK tardan un tiempo en actualizarse a la última versión, por lo que pueden traer usuarios orgánicos, que instalan versiones anteriores sin el SDK de AppsFlyer.
   * Las implementaciones de actualizaciones de la aplicación en las tiendas de aplicaciones pueden tardar hasta un par de días en completarse. Es posible que los usuarios que realizaron la instalación durante esta fase obtengan la versión anterior.

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="5. Comprensión de la asignación de parámetros">

**Para este paso, se necesita a tu desarrollador de apps**.Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

Comprende cómo se asignan los parámetros de Firebase Dynamic Links a los parámetros correspondientes de AppsFlyer.

La correcta asignación y comprensión de los parámetros correspondientes garantizarán que tus enlaces obtengan los mismos resultados.

En la siguiente tabla, se enumeran todos los parámetros de Firebase y los parámetros de AppsFlyer correspondientes.

Usa esta tabla como referencia para todos los parámetros que usas actualmente cuando migras a AppsFlyer.

<div id="note" />

> 📘 **Nota**
>
> Si un parámetro de Firebase no aparece en la lista, es porque AppsFlyer lo cubre en la configuración de la plantilla de OneLink sin necesidad de poner un parámetro en tus enlaces.

<table><thead><tr><th>Agrupación</th><th>Firebase</th><th>AppsFlyer</th><th>Descripción</th></tr></thead><tbody><tr><td>Parámetros móviles</td><td>enlace CM360</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li> <strong>af_dp</strong>: esquema URI utilizado como método alternativo para iniciar aplicaciones iOS y Android.</li><li> <strong>deep_link_value</strong>: nombre del valor del contenido in-app específico al que se dirigirá a los usuarios.</li></ul></td></tr><tr><td> <br/><span>Parámetros de Android</span> </td><td>afl</td><td>af_android_url</td><td>Permite redirigir a los usuarios de Android a una página web personalizada (el dominio debe estar en la <a href="./set-up-your-domain-redirect-allowlist" target="_blank">lista de permitidos de redirección</a>)</td></tr><tr><td rowspan="2"> <span>Parámetros de iOS</span><br/><br/><br/> </td><td>ifl</td><td>af_ios_url</td><td>Permite redirigir a los usuarios de iOS a una página web personalizada.</td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>Se utiliza para forzar que una aplicación iOS se abra utilizando el esquema URI af_dp. Sin esto, la aplicación no se abrirá utilizando el esquema URI.</td></tr><tr><td>URL de otra plataforma</td><td>ofl</td><td>af_web_dp</td><td>Permite redirigir a los usuarios de equipos de escritorio a una página web personalizada.</td></tr><tr><td rowspan="3"> <br/><span>Etiquetas sociales</span><br/><br/><br/> </td><td>st</td><td>af_og_title</td><td>Se utiliza para personalizar el título de los contenidos compartidos en las redes sociales.</td></tr><tr><td>sd</td><td>af_og_description</td><td>Se utiliza para personalizar la descripción de los contenidos compartidos en las redes sociales.</td></tr><tr><td>si</td><td>af_og_image</td><td>Se utiliza para personalizar la imagen de los contenidos compartidos en las redes sociales.</td></tr><tr><td rowspan="5"><p>Parámetros analíticos <br/><br/><br/><br/> </p></td><td>utm_source</td><td>PID</td><td>Fuente de medios</td></tr><tr><td>utm_medium</td><td>af_canal</td><td>Identifica los canales de fuentes de medios en los que se distribuyen tus anuncios.</td></tr><tr><td>utm_campaign</td><td>C</td><td>Nombre de la campaña</td></tr><tr><td>utm_term</td><td>af_palabras_clave</td><td>Lista de palabras clave para campañas orientadas a texto</td></tr><tr><td>utm_content</td><td>af_conjunto de anuncios</td><td>Colección de anuncios asociados a una campaña</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="Paso 6. Crea enlaces de OneLink con parámetros asignados">

Con los parámetros asignados, puedes crear enlaces de OneLink en tu plantilla de OneLink.

Los enlaces se pueden crear utilizando el <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">panel de control de AppsFlyer</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">de forma masiva</Anchor> a través de un CSV, programáticamente con nuestra <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API de OneLink</Anchor>, en el <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">SDK</Anchor> o a través de <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">enlaces largos</Anchor>.

Utiliza la siguiente tabla para determinar qué método funciona mejor para tu uso.

| Firebase | AppsFlyer | Úsalo si | Notas |
| --- | --- | --- | --- |
| Consola de Firebase | <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">Página de administración de OneLink</Anchor> | Deseas crear enlaces de OneLink uno por uno. De esta manera, puedes utilizar todas las funciones y posibilidades de OneLink. |  |
| API de Dynamic Link Builder | <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">SDK</Anchor> | Deseas crear enlaces in-app generados mediante programación para usos como invitaciones y referencias de usuarios. | <ul><li>Requiere un desarrollador iOS o Android</li></ul> |
| API de Firebase REST | <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API de OneLink</Anchor> | Deseas crear enlaces mediante programación fuera de la aplicación móvil | <ul><li>Requiere un desarrollador</li><li>No disponible en el plan gratuito</li></ul> |
| Creación manual de enlaces | <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">Enlaces largos</Anchor> | Deseas crear manualmente el enlace con sus parámetros de consulta. Úsalo si no necesitas enlaces cortos. Por ejemplo, si el enlace estará detrás de un botón o un banner. |  |
|  | <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">Enlaces masivos</Anchor> | Deseas migrar todos tus enlaces dinámicos de Firebase de forma masiva a AppsFlyer.<br /><br />Esto se recomienda para pasar rápidamente todos tus enlaces sin errores. | <ul><li>Requiere un paso previo para [asignar las claves y los valores de los parámetros de enlace de acuerdo con los parámetros de Firebase correspondientes.](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>No disponible en el plan gratuito.</li></ul> |
|  | <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Banner inteligente</Anchor> | Permite redirigir a los usuarios de Android a una página web personalizada. |  |
|  | <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">Script inteligente</Anchor> | Si deseas crear un enlace largo de forma dinámica en una página web para una experiencia de la web a la aplicación. |  |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">Dominios de marca</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">Uso de Firebase y Google Tag Manager con AppsFlyer:</Anchor>

<div data-zendesk-anchors="overview=migraci%C3%B3n h_01J7ZPPQ340PNQ70FZAQY4GBZ1=migraci%C3%B3n 01H8K961JHRXNQHBVN930XW70Q=migraci%C3%B3n how-to-migrate-from-firebase-to-appsflyer=c%C3%B3mo-migrar-de-firebase-a-appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=c%C3%B3mo-migrar-de-firebase-a-appsflyer h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=pasos-para-la-integraci%C3%B3n-del-sdk-de-appsflyer h_01J5QXST2K890DV7QS6S9K3A01=pasos-para-la-integraci%C3%B3n-del-sdk-de-appsflyer h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=nota h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=consulta-tambi%C3%A9n" />
