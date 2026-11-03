---
title: Gestión de creatividades
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2025-09-17T12:01:55Z'
  edited_at: '2026-10-09T00:01:54Z'
  id: 39137008313105
  locale: es
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/es/articles/39137008313105
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** La gestión de creatividades te ayuda a centralizar, revisar y lanzar las creatividades con mayor rapidez. Úsala para sincronizar creatividades desde tu almacenamiento de creatividades, consultar el estado de actividad en distintas fuentes de medios, encontrar fácilmente las creatividades relevantes y subirlas directamente a campañas de fuentes de medios compatibles.

## Sobre la gestión de creatividades

La gestión de creatividades es un centro para gestionar los activos creativos durante todo su ciclo de vida, desde sincronizar el almacenamiento hasta cargar la fuente de medios.

Utiliza la gestión de creatividades para:

* Sincronizar las creatividades desde el almacenamiento de creatividades.
* Buscar y revisar fácilmente las creatividades en una galería centralizada.
* Conocer el estado de la actividad creativa en todas las fuentes de medios.
* Priorizar a los creativos con una puntuación previa al lanzamiento basada en IA.
* Subir las creatividades directamente a las campañas de todas las fuentes de medios.
* Revisar los resultados de las subidas y comprobar qué creatividades se han subido correctamente o no.

Creada para la escala, la gestión de creatividades ayuda a los equipos creativos y de marketing a reducir el trabajo manual, optimizar el tiempo de lanzamiento y aumentar el performance de la campaña.

## Comienza

**Requisitos previos**

Una cuenta de AppsFlyer con una suscripción de <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide">Optimización Creativa</Anchor>. Para registrarte en la gestión de creatividades, contacta a tu CSM o escribe a [hello@appsflyer.com](mailto:hello@appsflyer.com). También puede estar disponible una prueba gratuita.

**Para empezar a usar la gestión creativa, sigue los pasos que se indican a continuación:**

<div id="sync-creatives-from-the-creative-storage" />

<Accordion title="Sincroniza las creatividades desde el almacenamiento de creatividades">

La gestión de creatividades puede sincronizar las creatividades desde el almacenamiento conectado. Una vez guardada la conexión, extrae las creatividades del almacenamiento conectado y mantiene la biblioteca actualizada a medida que se añaden nuevas creatividades.

Actualmente, la gestión de creatividades es compatible con Google Drive y Dropbox. Cada fuente tiene un flujo de conexión diferente.

**Las conexiones de almacenamiento compatibles incluyen:**

* [Google Drive](#conectar-google-drive)
* [Dropbox](#conectar-dropbox)

#### Conectar Google Drive

**Para conectar una carpeta de Google Drive:**

1. En AppsFlyer, ve a **Optimizar > Gestión de creatividades.**

**<Image alt="Clic Creative Management New.png" src="https://files.readme.io/c4ae98a4409b0766c9bd41e2f153d67c3d6168d31af82dadd1f43f345678878e-40988213459217.png" width="35.83%" />**

2. Haz clic en **Conexiones de creatividades**.

<Image alt="clic Creative connection.png" src="https://files.readme.io/a1ba600e90389351dc119bb00a358d14909eb92a3fc0b8391e3efa7650992ae2-small-48939135740689.png" width="150%" />

3. Haz clic en **Agregar conexión**.
4. Selecciona **Google Drive**.
5. En Google Drive, concede a AppsFlyer acceso a la carpeta que contiene tus creatividades. Para ello, comparte la carpeta con permisos de lector para la cuenta de servicio de AppsFlyer: `creative-google-account-drive@creative-prod.iam.gserviceaccount.com`.
   * La gestión de creatividades sincroniza las creatividades de las carpetas seleccionadas y sus subcarpetas.
6. Vuelva a “Gestión de creatividades” e introduce la URL de la carpeta.
7. Selecciona la aplicación correspondiente. Este paso es opcional, pero lo recomendamos porque ayuda a organizar y combinar las creatividades correctamente.
8. Haz clic en **Añadir URL**.
9. Repite los dos pasos anteriores para conectar varias carpetas a la vez.

<Image alt="image (49).png" src="https://files.readme.io/c29dab5dc76470b5e99e8efd8accaec7bfd1c6878f3bcfe8d58d7b650063065b-48939152741393.png" width="92.07%" />

10. Haz clic en **Conectar**.

#### Conectar Dropbox

Antes de conectar Dropbox, asegúrate de haber iniciado sesión en Dropbox con la cuenta que tiene acceso a las carpetas creativas correspondientes.

**Para conectar carpetas de Dropbox:**

1. En AppsFlyer, ve a **Optimizar > Gestión de creatividades.**
2. Haz clic en **Conexiones de creatividades**.
3. Haz clic en **Agregar conexión**.
4. Selecciona **Dropbox**.
5. En la ventana emergente de inicio de sesión de Dropbox, conéctate a la cuenta de Dropbox correspondiente.
6. En el modal de conexión, haz clic en **Elegir carpetas** y, a continuación, selecciona las carpetas que deseas conectar.
   * La gestión de creatividades sincroniza las creatividades de las carpetas seleccionadas y sus subcarpetas.

<Image alt="clic Choose folders.png" src="https://files.readme.io/13d62001deedecfb95a202aa54d36a1d7948d36aa76ac2a93b056be54d2ffe01-48939135745937.png" width="84.64%" />

7. Selecciona la aplicación correspondiente para cada carpeta. Este paso es opcional, pero lo recomendamos porque ayuda a organizar y combinar las creatividades correctamente.
8. Haz clic en **Conectar**.

Una vez creada la conexión, la gestión de creatividades comienza a extraer y procesar las creatividades. Una vez finalizado el procesamiento, las creatividades aparecen en la galería con metadatos como el tipo de creatividad, la fecha de sincronización, la fecha de lanzamiento, el estado y las versiones disponibles.

</Accordion>

<div id="browse-and-select-creatives" />

<Accordion title="Busca y selecciona creatividades">

La galería de gestión creativa es el lugar donde se revisan, buscan, filtran y seleccionan las creatividades.

Cada tarjeta creativa representa una creatividad. Una creatividad puede incluir varias versiones, como diferentes resoluciones o formatos. Desde la tarjeta, puedes comprender rápidamente si la creatividad es nueva, está activa o inactiva en todas las fuentes de medios y ver metadatos de alto nivel, como cuándo se lanzó por primera vez y cuándo se sincronizó con la gestión de creatividades. Cada creatividad nueva se analiza y califica automáticamente para ayudarte a elegir las mejores antes de su lanzamiento. Las puntuaciones van de C (menos probable que tenga éxito) a A (listo para escalar), ayudándote a priorizar creativos de alto rendimiento con confianza.

<Image alt="image (52).png" src="https://files.readme.io/a295ed00e01564b04bd32a7ce515cf41012a62324a8fcd350d1b4b9113e0cacb-small-48939135746577.png" width="150%" />

#### Filtrar creatividades

Utiliza la barra de búsqueda y los filtros para encontrar los creativos relevantes por:

* **Barra de búsqueda**: Busca creatividades por ID o nombre.
* **Aplicación**: Se centra en las creatividades relacionadas con una aplicación específica.
* **Fuente de medios**: Busca creativos que estén activos o estuvieron activos en una red específica.
* **Tipo de creatividad**: Filtra por imagen, vídeo o HTML.
* **Estado de la creatividad**: Filtra por creatividades nuevas, activas o inactivas.
* **Puntuación creativa**: Se centra en los nuevos creativos con una puntuación de IA específica.
* **Sincronizar fecha**: Busca creatividades añadidas a la gestión de creatividades durante un período específico.
* **Fecha de lanzamiento**: Encuentra las creatividades lanzadas por primera vez durante un período específico.
* **Resolución**: Busca creatividades con una versión específica disponible.

De forma predeterminada, las creatividades se ordenan por fecha de sincronización, por lo que las creatividades añadidas recientemente aparecen primero. También puedes ordenar por fecha de lanzamiento o nombre de la creatividad.

</Accordion>

<div id="upload-creatives-to-media-sources" />

<Accordion title="Sube creatividades a fuentes de medios">

Cuando estés listo para lanzar creatividades, selecciona una o más creatividades de la galería y haz clic en **Cargar a fuente de medios**.

Actualmente, la gestión de creatividades solo permite subir contenido para campañas de promoción de aplicaciones. La configuración de carga cambia en función de la fuente de medios seleccionado porque cada red tiene requisitos y estructuras de destino diferentes.

Para todas las fuentes de medios compatibles, puedes cargar creatividades en varios destinos a la vez.

**Fuentes de medios compatibles incluyen:**

* [Anuncios de Google](#anuncios-de-google)
* [Anuncios de Meta](#anuncios-de-meta)
* [Anuncios Tik Tok](#anuncios-tik-tok)
* [Mintegral](#mintegral)
* [Unity Ads](#unity-ads)
* [AppLovin](#applovin)

#### Anuncios de Google

En el caso de Google Ads, puedes subir creatividades a los grupos de anuncios de promoción de aplicaciones existentes.

1. Selecciona creatividades de la galería.
2. Haz clic en **Cargar a fuente de medios**.
3. Elige Google Ads.
4. Selecciona los detalles de destino requeridos: Cuenta de Google y grupos de anuncios.
   * Puedes usar el filtro de campaña para restringir la búsqueda a grupos de anuncios específicos.
   * No necesitas añadir el canal de YouTube.
5. Si la acción de carga incluye vídeos, selecciona si los vídeos subidos son para niños.
6. Selecciona las creatividades en la sección **Todas las creatividades** y asígnalas a los grupos de anuncios.
7. Si una creatividad tiene varias versiones, selecciona las correspondientes que quieras subir.
8. Revisa la configuración y los mensajes de validación.
9. Haz clic en **Subir a Google Ads**.

<Image alt="clic Upload to Google Ads.png" src="https://files.readme.io/5280a1a396584e6874d8a2c24882fb9be4b25747d322fab607944da57a8fcdc9-48939152742545.png" width="100%" />

> 📘 **Nota**
>
> Antes de subir un lote grande por primera vez, te recomendamos que pruebes con una sola creatividad para confirmar que aparece correctamente en la fuente de medios seleccionada.

#### Anuncios de Meta

En el caso de Meta, puedes crear anuncios dentro de los conjuntos de anuncios existentes.

1. Selecciona creatividades de la galería.
2. Haz clic en **Cargar a fuente de medios**.
3. Elige Meta Ads.
4. Selecciona los detalles de destino requeridos: Cuenta y conjuntos de anuncios de Meta Ad.
   * Puedes usar el filtro de campaña para restringir la búsqueda por grupos de anuncios.
5. Crea tantos anuncios nuevos como necesites.
   * Si has seleccionado varios conjuntos de anuncios, cada anuncio se crea en cada conjunto de anuncios.
6. Selecciona las creatividades en la sección **Todas las creatividades** y asígnalas a los anuncios.
7. Si una creatividad tiene varias versiones, selecciona las correspondientes que quieras subir.

<Image alt="Anuncios de Meta.png" src="https://files.readme.io/56c387af74f4904921770abdee23e0d27a92e8f26c40d2d4fa46a4c42a4e2bb0-48939152743441.png" width="1838px" />

8. Revisa la configuración y los mensajes de validación.
9. Haz clic en **Siguiente**.
10. Configura campos a nivel de anuncio: Página de Facebook, perfil de Instagram, texto principal, título, CTA, estado de lanzamiento y si se permiten las mejoras de Meta para tus creatividades.
    * De forma predeterminada, esta configuración se aplica a todos los anuncios nuevos que se creen. Puedes editar anuncios específicos seleccionándolos en el menú desplegable **Personalizar un anuncio específico**.
11. Haz clic en **Crear anuncios en Meta**.

<Image alt="image (55).png" src="https://files.readme.io/95125f551e731428a8d18a7ba1162246a867cdff4e0d34aee3950e08446c5eeb-48939152744209.png" width="1840px" />

#### Anuncios Tik Tok

En el caso de los anuncios de TikTok, puedes subir creatividades a los anuncios de promoción de aplicaciones existentes.

1. Selecciona creatividades de la galería.
2. Haz clic en **Cargar a fuente de medios**.
3. Elige TikTok.
4. Selecciona los detalles de destino requeridos: Cuenta publicitaria y anuncios de TikTok.
   * Puedes usar los filtros de campaña y de grupo de anuncios para restringir la búsqueda de anuncios específicos.
   * No necesitas añadir el canal de YouTube.
5. Selecciona las creatividades en la sección **Todas las creatividades** y asígnalas a los anuncios.
6. Si una creatividad tiene varias versiones, selecciona las correspondientes que quieras subir.
7. Revisa la configuración y los mensajes de validación.
8. Haz clic en **Subir a TikTok**.

#### Unity Ads

> 📘 **Nota**
>
> En el caso de Unity Ads, actualmente solo puedes subir creatividades a la biblioteca creativa de Unity. La subida directa a las campañas se añadirá pronto.

1. Selecciona creatividades de la galería.
2. Haz clic en **Cargar a fuente de medios**.
3. Elige **Unity Ads**.
4. Selecciona la aplicación a la que deseas asociar las creatividades y el idioma de las creatividades (opcional).
5. Si una creatividad tiene varias versiones, selecciona las correspondientes que quieras subir.
6. Haz clic en **Subir a Unity Ads**.

#### Mintegral

> 📘 **Nota**
>
> En el caso de Mintegral, actualmente solo puedes subir creatividades a la biblioteca creativa de Mintegral. La subida directa a las campañas se añadirá pronto.

1. Selecciona creatividades de la galería.
2. Haz clic en **Cargar a fuente de medios**.
3. Elige **Mintegral**.
4. Selecciona la cuenta de Mintegral a la que quieres que se asocien las creatividades.
5. Si una creatividad tiene varias versiones, selecciona las correspondientes que quieras subir.
6. Haz clic en **Cargar a Mintegral**.

#### AppLovin

> 📘 **Nota:**
>
> El acceso a la API de gestión de campañas de AppLovin está disponible para anunciantes seleccionados. Para solicitar acceso u obtener más información sobre la elegibilidad, ponte en contacto con tu representante de AppLovin.

En AppLovin, puedes subir creativos a conjuntos de creativos existentes o crear nuevos conjuntos de creativos.

1. Selecciona los creativos de la galería.
2. Haz clic en **Subir a la fuente de medios**.
3. Elige AppLovin.
4. Elige si quieres crear nuevos conjuntos de creativos o subirlos a los existentes.

**Para crear un nuevo conjunto de creativos:**

1. Selecciona la cuenta de AppLovin.
2. Selecciona las campañas en las que quieres que se cree el conjunto de creativos.
3. Introduce un nombre para el conjunto de creativos.
4. Selecciona el estado de lanzamiento.
5. Haz clic en **Añadir**. Puedes crear tantos conjuntos de creativos como necesites.
6. Selecciona los creativos en la sección **Todos los creativos** y asígnalos a los conjuntos de creativos.
7. Si un creativo tiene varias versiones, selecciona las que quieras subir.
8. Revisa la configuración y los mensajes de validación.
9. Haz clic en **Subir a AppLovin**.

**Para subir a un conjunto de creativos existente:**

1. Selecciona la cuenta de AppLovin.
2. Selecciona los conjuntos de creativos a los que quieres subirlos.
   * Puedes usar el filtro de campaña para acotar la búsqueda de conjuntos de creativos específicos.
3. Selecciona los creativos en la sección **Todos los creativos** y asígnalos a los conjuntos de creativos.
4. Si un creativo tiene varias versiones, selecciona las que quieras subir.
5. Revisa la configuración y los mensajes de validación.
6. Haz clic en **Cargar en AppLovin**.

</Accordion>

<div id="review-upload-results" />

<Accordion title="Revisa los resultados de las subidas">

Tras iniciar una carga, la ventana de carga se cierra automáticamente y la gestión de creatividades continúa con el proceso de carga en segundo plano mientras sigues trabajando.

Para revisar los resultados de las subidas, haz clic en **Historial de subidas** en la galería de gestión de creatividades.

El historial de subidas muestra los trabajos de subida anteriores y sus resultados, incluidos:

* Fuente de medios y destino.
* Estado de carga: Éxito, éxito parcial o error.
* Número de creatividades subidas del total seleccionado.
* Hora de finalización de la carga.
* Detalles de las creatividades que fallaron.

Si la carga finaliza con éxito o error parcial, la gestión de creatividades muestra una indicación en el historial de subidas para que puedas revisar el problema más adelante. En la vista de detalles, las creatividades fallidas aparecen con un motivo de error.

</Accordion>

<div id="creative-activity-status" />

<Accordion title="Estado de la actividad creativa">

El estado de la creatividad te ayuda a comprender dónde se usa una creatividad en las fuentes de medios conectadas.

En la galería, cada creatividad puede mostrar:

* **Nueva**: La creatividad aún no se ha lanzado.
* **Activa**: La creatividad está actualmente en funcionamiento.
* **Inactiva**: La creatividad estaba activa anteriormente, pero no está en funcionamiento actualmente.

La gestión creativa también te ayuda a comprender dónde están en funcionamiento actualmente tus creatividades activas. Haz clic en una tarjeta creativa para abrir el dashboard, donde puedes ver exactamente en qué campañas y grupos de anuncios está activa la creatividad.

Utiliza la información de estado para responder a preguntas como:

* ¿Qué nuevas creatividades debo subir a continuación?
* ¿Qué creatividades están activas en una fuente de medios y se pueden probar en otra?
* ¿Qué creatividades se probaron antes y podría valer la pena relanzarlas?
* ¿Qué creatividades están activas en una campaña de prueba y deberían subirse a más campañas?

</Accordion>

## Características y limitaciones

| Caducado | Descripción |
| --- | --- |
| Alcance de la campaña | Actualmente, la gestión de creatividades solo admite campañas de promoción de aplicaciones. |
| Fuentes de almacenamiento compatibles | La sincronización de repositorios es compatible actualmente con Google Drive y Dropbox. |
| Los destinos de carga varían según la red | Los destinos de carga admitidos y los campos obligatorios varían según la fuente de medios. |
| El método de carga varía según la red | El método de carga varía según la red.  <br />Google Ads, Meta Ads y TikTok admiten la carga directa a las campañas (como anuncios o conjuntos creativos); actualmente, Unity Ads y Mintegral solo admiten la carga a la biblioteca creativa de la red. |
| Requisitos de los recursos | Los formatos, las dimensiones, la duración y el tamaño de los archivos creativos deben cumplir los requisitos de cada red. |
| Alcance del historial de subidas | El historial de subidas refleja el resultado de la subida, no el estado de publicación o moderación en curso de la creatividad. |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide">Guía de optimización creativa</Anchor>

<div data-zendesk-anchors="about-creative-management=sobre-la-gesti%C3%B3n-de-creatividades get-started=comienza h_01KXDN2V1R9SRPFSRGZZ4ZA62S=sync-creatives-from-the-creative-storage connect-google-drive=conectar-google-drive h_01KXDN2V1RGCDYJ074FV4KJY8T=conectar-google-drive connect-dropbox=conectar-dropbox h_01KXDN2V1R75971RE5ECTDM8TM=conectar-dropbox h_01KXDN2V1RAA882M55HK9152D6=browse-and-select-creatives filter-creatives=filtrar-creatividades h_01KXDN2V1RHJJZC67ZM84TNT0Y=filtrar-creatividades h_01KXDN2V1R8CXZ4XGTX656XRWF=upload-creatives-to-media-sources google-ads=anuncios-de-google h_01KXDN2V1RE8748NWSCJP824PD=anuncios-de-google h_01KXDN2V1R31MABH1A3G0T9B84=nota meta-ads=anuncios-de-meta h_01KXDN2V1RG25RR7BXYAFVEAT7=anuncios-de-meta tiktok-ads=anuncios-tik-tok h_01KXDN2V1RBANB482286YP1QSY=anuncios-tik-tok h_01KXDN2V1R52Y91AZNVGPPWW44=unity-ads h_01KXDN2V1RF9TZ25DFYQ91RVRC=nota-1 h_01KXDN2V1REED32CRW83W7MMC9=mintegral h_01KXDN2V1SVWASV4KGJJ2VC162=nota-2 h_01KXDN2V1RSFB2GHDPN95S90EJ=applovin h_01M1H2RMVW2CYMV7KBBSHJ9686=nota-3 h_01KXDN2V1S8NZP8F4QN51NS3XP=review-upload-results h_01KXDN2V1SC0PHRY810NJG6QY3=creative-activity-status traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KXDN2V1SDNR1Z5FTKEJNDZF3=consulta-tambi%C3%A9n" />
