---
title: Configurar la API de costos de ROI360 para medir los datos de costos
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-23T01:09:23Z'
  id: 360008850257
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360008850257
---
> **At a glance:** Obtén datos de costo de marketing agregados, incluidos datos de rendimiento de LTV (Lifetime value) relacionados con el costo, mediante la API de Costo a nivel de cuenta de fuente de medios.

<div id="overview" />

## Resumen

ROI360 proporciona datos de costo de marketing agregados, incluidas las métricas de rendimiento de LTV relacionadas con el costo, a nivel de cuenta publicitaria.

Las integraciones de costos se configuran en **Configuración de costos**, donde cada integración se conecta a una cuenta de fuente de medios y mide el costo de todas las aplicaciones que selecciones. Según la ad network, esto puede incluir apps móviles, de CTV, para PC y consola, y web. Conecta cada cuenta de fuente de medios una vez para habilitar el costo en varias aplicaciones.

También puedes crear y editar integraciones de costos desde la pestaña **Costo** de Partner Marketplace. Ambos puntos de entrada generan la misma integración a nivel de cuenta.

<div id="note" />

> 📘 **Nota:**
>
> El acceso a **Configuración de costos** está controlado por permisos de rol. Si no puedes abrir **Configuración de costos**, pídele a tu administrador que actualice los permisos de tu rol en la página **Gestión de usuarios**. La capacidad relevante es **Conexiones de costos**.

<div id="create-a-new-api-cost-integration" />

## Crear una nueva integración de costos mediante API

Todas las integraciones de costos siguen los mismos dos pasos: autenticarte con la fuente de medios y, después, asignar un nombre a la integración y seleccionar las aplicaciones que cubre. Algunas fuentes de medios requieren un paso adicional para que AppsFlyer pueda asociar tus aplicaciones con los identificadores que se usan en su sistema.

Después de la configuración inicial, los datos de costo aparecen en el Dashboard con la siguiente extracción de datos, programada cada cuatro horas, seis veces al día.

<div id="h_01M43Y9WQ8WCXWQ0S9ZAT59CWW" />

<Accordion title="Paso 1: Proporciona las credenciales">

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **ROI360** > **Configuración de costos**.
2. Haz clic en **+ Nueva integración**, selecciona la fuente de medios y, después, haz clic en **Siguiente**.
3. Según la fuente de medios, verás una de las siguientes opciones:
   * **Inicio de sesión:** inicia sesión con tu cuenta de ad network y completa el flujo de autenticación. AppsFlyer valida la conexión y asigna a la integración el nombre de la cuenta que has conectado.
   * **Credenciales:** proporciona credenciales estáticas y completa los campos que se muestran para esa fuente de medios, por ejemplo, un nombre de usuario y una contraseña, o una clave de la API. Los nombres de los campos varían según la fuente de medios. Las credenciales estáticas no se validan durante la configuración.
4. Cambia el nombre de la integración si quieres otro distinto o conserva el nombre predeterminado. El nombre tiene un máximo de 50 caracteres y es una etiqueta que te ayuda a identificar la integración más adelante, lo cual es importante si creas más de una para la misma fuente de medios.

</Accordion>

<div id="h_01M43Y9WQ8HK1N0GJNW5BH4MPZ" />

<Accordion title="Paso 2: Selecciona apps">

Haz clic en **Seleccionar aplicaciones** y elige las aplicaciones que cubre esta integración. Puedes seleccionar cualquier app a la que tengas permiso de acceso, ya sea móvil, web, CTV o cualquier otra plataforma que uses para ejecutar tus campañas. Haz clic en **Aplicar** y, luego, en **Siguiente**.

Si la fuente de medios requiere un paso adicional, continúa con el [paso 3](#additional-steps-specific-media-sources-only) a continuación. De lo contrario, haz clic en **Guardar integración**.

</Accordion>

<div id="additional-steps-specific-media-sources-only" />

<Accordion title="Paso 3: Pasos adicionales (solo para fuentes de medios específicas)">

Algunas fuentes de medios requieren un paso adicional después de seleccionar las aplicaciones. Añade la asignación a nombres de paquete e ID de bundle, o a ID de sitio.

<div id="map-apps-to-package-names-or-bundle-ids" />

#### Asigna aplicaciones a nombres de paquete o ID de paquete

Hay fuentes de medios que identifican las aplicaciones por el nombre de paquete de Android o el ID de paquete de iOS, por ejemplo, AppLovin.

Como parte de la configuración de costos, después de seleccionar las aplicaciones, introduce el nombre de paquete o el ID de paquete exactos de cada aplicación, tal como aparecen en el sistema de la fuente de medios. Cada aplicación requiere un valor de asignación. Haz clic en **Guardar integración**.

<div id="map-apps-to-site-ids" />

#### Asigna aplicaciones a ID de sitio

Para las fuentes de medios que identifican las aplicaciones por ID de sitio, por ejemplo, Liftoff.

Después de seleccionar las aplicaciones, elige un parámetro predeterminado de ID de sitio. Se aplica a cada aplicación de la integración. Patrones disponibles:

* `${APP_ID}`
* `${APP_NAME}`
* `${APP_ID}_${APP_NAME}`
* `${APP_NAME}_${APP_ID}`

Para anular el valor predeterminado de una aplicación concreta, selecciona un parámetro distinto en el menú desplegable de **ID de sitio** de esa aplicación. Úsalo cuando el ID de sitio de una aplicación tenga un formato diferente en el sistema de la fuente de medios. Haz clic en **Guardar integración**.

<div id="note-1" />

> 📘 **Nota:**
>
> La asignación del ID de sitio garantiza que las macros de ID de sitio del enlace de atribución de AppsFlyer coincidan con el valor que espera la fuente de medios. Si tu enlace de atribución usa macros distintas de la asignación que seleccionaste, los datos del ID de sitio no se completarán correctamente.

<div id="select-which-ad-account-to-pull-cost-from" />

#### Selecciona de qué cuenta publicitaria extraer el costo

En algunas fuentes de medios, como TikTok, un mismo login puede tener acceso a varias cuentas publicitarias. Después de iniciar sesión en la fuente de medios, tienes que seleccionar tú mismo la cuenta publicitaria concreta.

</Accordion>

<div id="edit-and-delete-an-integration" />

## Editar y eliminar una integración

Esto funciona igual en todas las integraciones, independientemente del punto de entrada que usaras para crearla: **Configuración de costos** o la pestaña **Costo**.

<div id="h_01M43Y9WQ804YMN8TZ7HGYSQH7" />

<Accordion title="Editar una integración de costos">

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **ROI360** > **Configuración de costos**.
2. Haz clic en la fuente de medios que quieres editar.
3. En la página de la fuente de medios, haz clic en la cuenta concreta que quieres editar.
4. En la pestaña **Apps**, haz clic en **Editar** para añadir o eliminar aplicaciones y, a continuación, guarda los cambios.

Las aplicaciones añadidas a una integración que usa un paso adicional deben asignarse antes de que puedas guardar los cambios. La pestaña **Detalles de la integración** muestra la configuración de la conexión.

</Accordion>

<div id="h_01M43Y9WQ89XKB2CN2EY4TG2AD" />

<Accordion title="Eliminar una integración de costos">

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **ROI360** > **Configuración de costos**.
2. Haz clic en la fuente de medios de la que quieres eliminar.
3. En la página de la fuente de medios, en la columna **Acción**, haz clic en el icono de eliminar de la cuenta concreta que quieres eliminar.
4. En el cuadro de diálogo de confirmación, haz clic en **Sí, eliminar**.

La recopilación de datos de costo se detiene de inmediato. Los datos históricos de costo no se ven afectados.

</Accordion>

<div id="h_01M43Y9WQ8ANZY2KNHKMV67YNY" />

<Accordion title="Transferir una aplicación a otra cuenta">

Las integraciones de costos se desconectan automáticamente cuando una aplicación se transfiere a otra cuenta.

</Accordion>

<div id="view-cost-api-status" />

## Ver el estado de la API de costos

El estado de la integración de costos se informa en dos niveles.

* **Nivel de aplicación:** cada aplicación incluida en una integración tiene su propio estado. Aquí es donde se informa del estado real de la recopilación de datos.
* **Nivel de conexión:** cada integración muestra un único estado, derivado de los estados de las aplicaciones que incluye. Cuando todas las aplicaciones comparten el mismo estado, la conexión muestra ese estado. Cuando las aplicaciones tienen estados distintos, la conexión muestra **Mixto**. Mixto no indica un problema con la conexión en sí, sino que las aplicaciones no están en un estado uniforme. Abre la integración para ver qué aplicaciones están afectadas.

El estado está disponible en los siguientes lugares:

| Donde | Nivel mostrado |
| --- | --- |
| Configuraciones de costo | Tanto a nivel de conexión como a nivel de aplicación |
| Dashboard de estado de integración de costo (e ingresos por publicidad) | A nivel de aplicación, en todas las fuentes de medios con la integración de costos habilitada en tu cuenta y en la cuenta de la agencia con la que trabajas. No se muestra el estado mixto. |
| Pestaña de costo | A nivel de aplicación, para una aplicación y una fuente de medios cada vez |

<div id="view-status-in-cost-settings" />

<Accordion title="Ver el estado en la configuración de costos">

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **ROI360** > **Configuración de costos**.
2. Selecciona la fuente de medios relevante. La columna **Estado** muestra el estado a nivel de conexión de cada integración.
3. Para ver el estado a nivel de aplicación, haz clic en la fila de la integración para abrir la página **Integración de costos** y, a continuación, consulta el estado de cada aplicación en la lista.

</Accordion>

<div id="view-status-in-cost-tab" />

<Accordion title="Ver el estado en la pestaña Costo">

Relevante para las fuentes de medios compatibles con la obtención de datos de costo a través de la API. Esta vista muestra el estado de la aplicación seleccionada, junto con la última vez que AppsFlyer extrajo correctamente los datos de costo correspondientes.

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Integraciones activas**.
2. Selecciona la fuente de medios.
3. En la lista de aplicaciones situada encima de la barra de pestañas, selecciona la aplicación cuyo estado de costo quieras ver.
4. Haz clic en la pestaña **Costo** para ver el estado y la hora de la última sincronización.

</Accordion>

<div id="h_01M43Y9WQ8H8ANPDEGYCH0T0MF" />

<Accordion title="Tabla de estados">

La siguiente tabla enumera todos los estados de integración de costos y lo que significa cada uno.

| Estado | Observaciones/acción requerida |
| --- | --- |
| Activo | La integración está habilitada y conectada correctamente a la fuente de medios. AppsFlyer está extrayendo datos de costo. |
| Cuenta de anunciante no habilitada | La cuenta de anuncios conectada no está habilitada para la recopilación de datos de costo del lado de la fuente de medios. Ponte en contacto con la fuente de medios para habilitar el acceso a la API para la cuenta y, después, vuelve a conectar la integración. |
| Error general | Se produjo un error inesperado durante la extracción. AppsFlyer lo vuelve a intentar en la siguiente extracción programada. Si el estado persiste, comunícate con el soporte técnico de AppsFlyer. |
| Credenciales no válidas | AppsFlyer no puede obtener datos a través de la API porque las credenciales no son válidas. Vuelve a conectarte utilizando las credenciales correctas. |
| Faltan credenciales | No has configurado credenciales para esta integración. Añade las credenciales necesarias en la configuración de costos o en la pestaña Costo del partner. |
| No hay campañas activas | Normalmente, la integración extrae el costo solo de las campañas que tienen conversiones en AppsFlyer. En esta extracción, no se encontró ninguna campaña de este tipo durante el periodo seleccionado. No se requiere ninguna acción. AppsFlyer lo reporta como una extracción correcta. |
| No hay datos | La API del partner respondió, pero no devolvió ningún dato. Esto suele ocurrir porque tus campañas están en pausa y no hay datos para extraer. No hace falta hacer nada, a menos que esperes que las campañas estén en funcionamiento. Si lo están, revisa la integración. |
| La API del socio no responde | El servidor del partner integrado no responde a AppsFlyer o la API del partner limitó la tasa de solicitudes. AppsFlyer lo vuelve a intentar en la siguiente extracción programada. Espera seis horas. Si el estado persiste, comunícate con el soporte técnico de AppsFlyer. |
| La API del partner no devuelve datos para la información proporcionada. Verifica la configuración | La fuente de medios no devolvió datos a pesar de tener campañas activas (campañas con conversiones en AppsFlyer), lo que apunta a una mala configuración a nivel de la fuente de medios. Vuelve a conectar la cuenta mediante OAuth y verifica que se haya seleccionado la cuenta de Anuncio correcta. |
| Esperando sincronización | La cuenta o la aplicación aún se está sincronizando con la ad network. Espera a que se complete la sincronización. |
| Mixto | Se muestra solo en Configuración de costos > página Fuente de medios, cuando las aplicaciones de una integración tienen estados diferentes. Abre la página de integración para ver el estado de cada aplicación. No se muestra en el dashboard de estado. |

</Accordion>

<div id="cost-integration-and-agencies" />

## Integración de costos y agencias

Si un anunciante utiliza una agencia para ejecutar sus campañas, recomendamos que sea la agencia, y no el anunciante, quien se integre con los partners relevantes. De lo contrario, si tanto el anunciante como la agencia se integran con un partner utilizando las mismas credenciales para la misma aplicación, los datos de costos se duplican.

Si un anunciante deja de trabajar con una agencia, los datos de costo se siguen extrayendo si la agencia sigue teniendo configurado el costo para la aplicación. El anunciante debe pedir a la agencia que elimine su integración de costos para dejar de extraer estos datos.

<div id="traits-and-limitations" />

## Rasgos y limitaciones

| Caducado | Comentarios |
| --- | --- |
| Agencias | Las agencias no pueden usar Configuración de costos para realizar integraciones de costos en varias aplicaciones a la vez, pero sí pueden usar la pestaña Costo en Partner Marketplace para hacerlo. |
| Las aplicaciones futuras heredan automáticamente la función de configuración de costos en la configuración de costos a nivel de cuenta | Actualmente no soportado. |
| Comportamiento de los datos de costos cuando el anunciante y la agencia se conectan a la misma ad network | Si tanto un anunciante como una agencia se conectan a la integración de costos para la misma cuenta de ad network (por ejemplo, Google Ads), los datos de costos se obtienen de la cuenta que recibe la atribución. Ejemplo: el anunciante se conecta con credenciales de anunciante, la agencia se conecta con credenciales de agencia y la atribución se asigna a la cuenta de la agencia. Resultado: ROI360 extrae los datos de costo de la conexión de la agencia y la conexión del anunciante aparece como Sin datos. |
| Desconexión automática de la integración de costos de Google | Las integraciones de costos que muestren el estado Sin datos o Credenciales no válidas durante más de 365 días consecutivos se desconectan automáticamente. Actualmente, esto solo se aplica a las integraciones de costos de Google. |
| Configuración de la lista de ID de anunciante de TikTok | Configura la lista de ID de anunciante a nivel de cuenta usando solo los ID de anunciante conectados al usuario de TikTok en la ad network. Los ID de anunciante que se añaden a la lista y no están alineados con el usuario en la ad network no devuelven datos de costo. |

<div data-zendesk-anchors="overview=resumen h_01K9S0A1PRMX3VBGHTNQ8C5FJW=resumen h_01M43Y9WQ83AK0KTKB9XM8FGM6=nota create-a-new-api-cost-integration=crear-una-nueva-integraci%C3%B3n-de-costos-mediante-api h_01K9S0A1PTQW9YJM3C4LKZRHFB=crear-una-nueva-integraci%C3%B3n-de-costos-mediante-api h_01K9S0A1PVCXZ3NQ7MWFKTJRH8=additional-steps-specific-media-sources-only h_01M43Y9WQ8HNRN4ZKWRBT9QY9G=asigna-aplicaciones-a-nombres-de-paquete-o-id-de-paquete site-id-mapping=asigna-aplicaciones-a-id-de-sitio h_01K3DGA6SKDTTPY8Q1JBTCTY7H=asigna-aplicaciones-a-id-de-sitio h_01M43Y9WQ8V94HB74M6CAKC9PB=nota-1 h_01M43Y9WQ8P3XATJS0TBB27ZPQ=selecciona-de-qu%C3%A9-cuenta-publicitaria-extraer-el-costo deleting-cost-integrations=editar-y-eliminar-una-integraci%C3%B3n h_01K3DGA6SKF8ZA5M9AW6DA0V3J=editar-y-eliminar-una-integraci%C3%B3n view-cost-api-status=ver-el-estado-de-la-api-de-costos h_01K9S0A1PWRNK08ZQXCF5V3YTM=ver-el-estado-de-la-api-de-costos h_01K9S0A1PXJQF2NVC9ZRMLK6HT=view-status-in-cost-settings h_01K9S0A1PYMBX4RQJZC8TNVK3F=view-status-in-cost-tab cost-integration-and-agencies=integraci%C3%B3n-de-costos-y-agencias h_01K9S0A1PZQXN4RTC7VWBLKM9H=integraci%C3%B3n-de-costos-y-agencias specification-and-limitation=rasgos-y-limitaciones h_01K3DGA6SKVZ347ZDY599S0Y7Y=rasgos-y-limitaciones" />
