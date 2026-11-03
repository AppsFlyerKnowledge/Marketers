---
title: Conexiones de Partners de medios de la Data Collaboration Platform (DCP)
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-04-12T14:19:36Z'
  edited_at: '2026-08-12T11:54:05Z'
  id: 45669216166417
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/45669216166417
---
## Resumen general

Conecta tus audiencias con partners de medios para activar tus campañas personalizadas y obtener los máximos resultados.

## Acerca de las conexiones de partners

Las conexiones de Partners de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP)</Anchor> te permiten conectar de forma segura tus audiencias de DCP con Partners de medios compatibles, para que puedas activar campañas personalizadas en sus plataformas. Una vez que un Partner está conectado a una audiencia, DCP entrega la audiencia según el flujo de actualización y activación configurado, utilizando los datos de fuente disponibles más recientes y los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#permisos-de-uso-compartido">permisos</Anchor>.

> 📘 **Advertencia**
>
> * La audiencia se envía para su activación como una lista de identificadores de usuario. Cada envío representa una instantánea completa de la audiencia en el momento de la exportación.
> * Las actualizaciones de audiencia no son continuas ni en tiempo real. En su lugar, se activan según la política definida, basada en una cadencia, que comprueba si los datos de la fuente se han actualizado. Cada actualización genera y envía la lista de audiencias a los destinos seleccionados.

## Conexiones de Partners compatibles

En esta sección se enumeran las conexiones con Partners de medios compatibles con DCP, junto con los requisitos de configuración de cada Partner, los permisos, los tipos de campaña compatibles y cualquier requisito o limitación adicional.

<div id="google-ads" />

<Accordion title="Anuncios de Google">

**Plataforma del Partner de medios:**  
Google Ads

**Nombre del Partner de medios en DCP:**  
Google Ads

**Requisitos de configuración de la conexión y de permisos de cuenta del Partner de medios:**

* Cuenta de Google activa.
* Acceso de usuario: acceso estándar o de administrador a la cuenta de Google Ads
* Customer Match: debe estar habilitado y aprobado
* Autorización del Partner: cuenta aprobada para trabajar con el Partner (a través de un representante de Google)
* Enlace del Partner: conexión de backend creada por Google

**Cómo funciona:**

Un usuario estándar/administrador debe habilitar la integración durante la configuración.   
Después, DCP carga las audiencias automáticamente a través del enlace del Partner.

**Recursos oficiales:**  
<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10589050">Ayuda de Customer Match de Google Ads</Anchor>

**Tipos de campaña compatibles:**

* **Búsqueda**  
  Usa listas de Customer Match en modo Observación o Targeting para ajustar las pujas o afinar el targeting de las consultas de búsqueda.
* **Display**  
  Segmenta o excluye audiencias directamente en la Red de Display de Google mediante listas de Customer Match.
* **Vídeo (YouTube)**  
  Usa audiencias para el targeting de anuncios en YouTube (in-stream, in-feed, Shorts).
* **Shopping**  
  Aplica audiencias en modo Observación para optimizar las pujas para los usuarios en campañas de Shopping.
* **Performance Max (PMax)**  
  Usa listas de Customer Match como señales de audiencia para guiar la automatización de Google (no targeting estricto).
* **Demand Gen**  
  Usa listas de Customer Match para el targeting directo de audiencias en YouTube, Discover y Gmail.
* **App Campaigns**   
  App Campaigns para instalaciones (ACi) usan las audiencias subidas solo como señales de optimización, mientras que las campañas de re-engagement (ACe) admiten targeting determinista y son el método principal de activación de audiencias.

#### Directrices de campañas de aplicaciones (ACi & ACe)

Las campaigns de apps de Google (antes conocidas como Universal App Campaign - UAC) se comportan de forma distinta a otros tipos de campaña cuando usan audiencias de Customer Match:

**App Campaigns for Installs (ACi)**

Diseñadas para adquirir nuevos usuarios a escala.  
Las audiencias de Customer Match **no se pueden usar para targeting directo.**  
Las audiencias subidas se usan **solo como señales** para mejorar el aprendizaje automático y la optimización de Google.  
La activación está **totalmente automatizada por la IA de Google**, sin control sobre la inclusión o exclusión de audiencias.  
Requiere suficiente historial de la cuenta (por ejemplo, datos de conversión y gasto) para poder optar a esta función.

**App Campaigns para engagement (ACe)**

Diseñadas para **re-engagement de usuarios existentes.**  
Las audiencias de Customer Match ofrecen **targeting determinista.**  
Los anunciantes pueden:

* Hacer targeting de segmentos de usuarios específicos (p. ej., usuarios que han abandonado, compradores)
* Ejecutar campañas del ciclo de vida (upsell, cross-sell, retención)

Las listas de audiencias de DCP se usan como criterio principal de targeting, igual que en otras plataformas.

> 📘 **Notas**
>
> * Usa ACi cuando tu objetivo sea la escala y la adquisición de usuarios (audiencias = solo señales).
> * Usa ACe cuando tu objetivo sea el re-engagement y el targeting preciso de audiencias (audiencias = targeting directo).

**Caducidad de la conexión:**

* Las conexiones suelen ser persistentes y no caducan automáticamente
* Puede ser necesaria una nueva autenticación si se revocan los tokens de OAuth, cambian los permisos de la cuenta, se actualizan la contraseña o la configuración de seguridad, o cambia la autorización de Partners de Google

**Actualización de las audiencias:**

* Las pertenencias de Customer Match caducan después de 540 días, a menos que se actualicen
* Validación operativa recomendada: cada 60–90 días
* Actualización de audiencias recomendada: diaria para campañas de rendimiento/ciclo de vida; como mínimo, cada 7 días
* Las audiencias críticas no deben permanecer desactualizadas durante más de 7 días

**Requisitos/limitaciones adicionales:**

* Las listas de Customer Match requieren un mínimo de 1.000 usuarios activos con coincidencia antes de poder usarse para publicar anuncios.
* Consentimiento de la UE (DMA): Debes añadir que, para los usuarios del Espacio Económico Europeo (EEE), es estrictamente obligatorio enviar señales de consentimiento explícito concedido (ad\_user\_data y ad\_personalization) para usar Customer Match. Si se deniega el consentimiento o no está disponible, el usuario no se procesará.

</Accordion>

<div id="dv360" />

<Accordion title="DV360">

**Plataforma del partner de medios:**  
Google DV360 (Display & Video 360)

**Nombre del partner de medios en DCP:**  
DV360

**Requisitos de configuración de la conexión y de permisos de la cuenta del partner de medios:**

* Cuenta de DV360 activa
* Acceso de usuario: acceso de nivel partner o de nivel anunciante con permisos suficientes
* Ingesta de audiencias habilitada: la cuenta debe permitir cargas de audiencias de origen 1st-party
* Autorización del partner: cuenta aprobada para trabajar con el partner (a través de un representante de Google)
* Enlace del partner: conexión de backend creada por Google

**Cómo funciona:**

Se necesitan los permisos de acceso adecuados de DV360 para habilitar la integración durante la configuración.  
Después de eso, DCP carga las audiencias automáticamente a través del enlace del partner.

**Recursos oficiales:**  
<Anchor target="_blank" href="https://support.google.com/displayvideo/answer/9134175?hl=en">Ayuda sobre audiencias de Display & Video 360</Anchor>

**Tipos de campaña compatibles:**

* **Display** – Se usa para el targeting directo de audiencias y las exclusiones
* **Vídeo (YouTube & vídeo programático)** – Se usa para el targeting directo de audiencias en YouTube y en el inventario de vídeo
* **Audio** – Se usa para el targeting en el inventario de audio digital
* **Native** – Se usa para el targeting de audiencias en ubicaciones nativas
* **Connected TV (CTV)** – Se usa para el targeting en inventario de streaming y TV
* **Campañas de app:** DV360 ofrece soporte para estrategias de instalación de la app y re-engagement, pero en un modelo programático basado en partidas. No replica las campañas de app de Google Ads, y las audiencias de Customer Match se usan directamente para targeting/exclusión en lugar de como señales principales de optimización o para el targeting determinista de usuarios de la app.

**Caducidad de la conexión:**

* La conexión permanece activa a menos que se revoque o cambien los permisos (refleja el comportamiento de Google Ads)
* Las pertenencias a audiencias siguen las políticas de Google Customer Match, incluida la ventana de caducidad de 540 días

**Actualidad de las audiencias:**

* Validación operativa recomendada: cada 60–90 días
* Actualización recomendada de audiencias: preferiblemente diaria; máximo 7 días entre actualizaciones para las campañas activas

**Requisitos o limitaciones adicionales:**

* Las listas de Customer Match requieren un mínimo de 1.000 usuarios activos con coincidencia antes de poder usarse para publicar anuncios.
* Consentimiento de la UE (DMA): Debes añadir que, para los usuarios del Espacio Económico Europeo (EEE), es estrictamente obligatorio enviar señales de consentimiento explícito concedido (ad\_user\_data y ad\_personalization) para usar Customer Match. Si se deniega el consentimiento o falta, el usuario no se procesará.

</Accordion>

<div id="meta-ads" />

<Accordion title="Anuncios de Meta">

**Plataforma del partner de medios:**  
Meta Ads Manager (Facebook / Instagram)

**Nombre del partner de medios en DCP:**  
Meta Ads

**Requisitos de configuración de la conexión del partner de medios y de permisos de la cuenta:**

* Cuenta personal válida de Meta (Facebook)
* Business Manager creado y vinculado a tu cuenta personal
* Al menos una página de Facebook
* Cuenta publicitaria que pertenezca a Business Manager o se comparta con él
* **Acceso de usuario:**
  * Acceso de administrador a Business Manager
  * Acceso de administrador o anunciante a la cuenta publicitaria

Debes ser el propietario de la cuenta publicitaria o tener permisos de administrador/anunciante en una cuenta publicitaria conectada a Business Manager. Estos permisos son necesarios para gestionar anuncios y audiencias, y son esenciales para las integraciones de DCP.

**Requisitos importantes:**

* El usuario de Meta utilizado para conectar el DCP debe:
  * Aceptar los Términos y condiciones de los anuncios de Meta & Condiciones
  * Aceptar las Condiciones de servicio de las audiencias personalizadas

El mismo usuario que autentica la conexión del DCP debe haber aceptado estos términos; de lo contrario, la conexión fallará.

**Cómo funciona:**

Necesitas los permisos necesarios durante la configuración para conectar el DCP.  

Después de completar la configuración:

* El DCP puede cargar y actualizar audiencias automáticamente.

**Recursos oficiales:**  
<Anchor target="_blank" href="https://www.facebook.com/business/help/1143109949216644/">Ayuda de Meta Business</Anchor>

**Tipos de campaña admitidos:**

Las audiencias personalizadas creadas en el DCP se pueden activar en los siguientes tipos de campaña de Meta:

* **Reconocimiento (Reconocimiento de marca / Alcance)** – Se utiliza para el targeting de audiencias amplias
* **Tráfico** – Se utiliza para impulsar a los usuarios hacia un destino (p. ej., un sitio web o una app)
* **Engagement** – Se utiliza para optimizar las interacciones (p. ej., interacción con publicaciones, visualizaciones de vídeo)
* **Leads** – Se utiliza para campañas de generación de leads
* **Promoción de aplicaciones** – Se utiliza para la instalación de la app y el re-engagement
* **Ventas (Conversiones)** – Se utiliza para impulsar compras u otros eventos de conversión

Las audiencias del DCP (Custom Audiences) se pueden usar para el targeting directo en todos los tipos de campaña de Meta, con soporte para casos de uso de embudo completo, desde el reconocimiento hasta la conversión.

**Caducidad de la conexión:**

* Por lo general, las conexiones son de larga duración, pero pueden interrumpirse por restablecimientos de contraseña, cambios en la MFA o la seguridad, permisos revocados, cambios de propiedad en Business Manager o revisiones de políticas de Meta

**Recencia de las audiencias:**

* Validación operativa recomendada: cada 60–90 días
* Actualización de audiencias recomendada: diaria para campañas de conversión/ciclo de vida; cada 3–7 días es aceptable para campañas de reconocimiento

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**Plataforma del partner de medios:**  
TikTok Ads Manager

**Nombre del partner de medios en el DCP:**  
TikTok

**Requisitos de configuración de la conexión y permisos de la cuenta del partner de medios:**

Cuenta del Administrador de anuncios de TikTok.  
Cuenta de anunciante aprobada y activa.  
Acceso de administrador al anunciante.  

Cuenta de anuncios de TikTok activa (Administrador de anuncios)

* **Acceso a la cuenta de anuncios:**
  * Acceso de administrador u operador a la cuenta de anuncios de TikTok
* **Permisos de audiencia:**
  * Capacidad para crear y gestionar audiencias personalizadas
* **Autorización de Partners:**
* Se debe conceder acceso a Partners (DCP) a través de TikTok Business Center o Ads Manager

**Cómo funciona:**

Se requiere un usuario administrador o estándar durante la configuración para autorizar y conectar el DCP.  

Después de completar la configuración:

* El DCP puede cargar y actualizar audiencias automáticamente
* La activación de audiencias se realiza directamente en TikTok Ads usando esas audiencias cargadas

**Recursos oficiales:**  
<Anchor target="_blank" href="https://ads.tiktok.com/help/article/invite-partners-into-tiktok-business-center?lang=en">Ayuda sobre el acceso de partners en TikTok Business Center</Anchor>

**Tipos de campaña admitidos:**

Las audiencias personalizadas creadas en el DCP se pueden activar en los siguientes tipos de campaña de TikTok:

* **Alcance** – Se usa para maximizar la exposición de las audiencias
* **Tráfico** – Se usa para impulsar a los usuarios a un sitio web o una landing page
* **Visualizaciones de vídeo** – Se usa para maximizar el engagement con el vídeo
* **Generación de leads** – Se usa para recopilar leads directamente en TikTok
* **Promoción de apps** – Se usa para la instalación de la app y el re-engagement
* **Conversiones (conversiones en el sitio web)** – Se usa para impulsar acciones como compras o registros

Las audiencias del DCP (audiencias personalizadas) se pueden usar para el targeting directo en todos los tipos de campaña de TikTok, con soporte para casos de uso de embudo completo, desde el reconocimiento hasta la conversión.

**Caducidad de la conexión:**

* La autorización OAuth o empresarial puede caducar o revocarse debido a cambios en los permisos o en la administración

**Actualización de audiencias:**

* Validación recomendada del token y de los permisos: trimestral
* Actualización recomendada de audiencias: preferiblemente a diario; máximo 7 días para audiencias activas

**Requisitos adicionales / limitaciones:**

* Tamaño mínimo de la audiencia: una audiencia personalizada requiere un mínimo estricto de 1.000 usuarios totales coincidentes para poder aplicarse a un grupo de anuncios

</Accordion>

<div id="pinterest" />

<Accordion title="Pinterest">

**Plataforma del partner de medios:**  
Administrador de anuncios de Pinterest

**Nombre del partner de medios en DCP:**  
Pinterest

**Requisitos de configuración de la conexión del partner de medios y de permisos de la cuenta:**

* Cuenta activa de Pinterest Business  
  Cuenta del Administrador de anuncios vinculada a la empresa
* **Acceso de usuario:**
  * Acceso de administrador o analista (con permisos de audiencias) a la cuenta de anuncios
* **Permisos de audiencias:**
  * Capacidad para crear y gestionar listas de clientes (audiencias)
* **Acceso del partner:**
  * Se debe conceder al partner (DCP) acceso a la cuenta de anuncios a través de Business Manager

**Cómo funciona:**

Se requiere un administrador o un usuario (con permisos suficientes) durante la configuración para conectar el DCP y conceder permisos.  

Una vez completada la configuración:

* El DCP puede cargar y actualizar audiencias automáticamente

**Recursos oficiales:**  
<Anchor target="_blank" href="https://help.pinterest.com/en/business/article/audience-targeting">Ayuda de Pinterest sobre targeting de audiencias</Anchor>

**Tipos de campaña compatibles:**

Las audiencias de listas de clientes creadas en el DCP se pueden activar en los siguientes tipos de campaña de Pinterest:

* **Awareness** – Se utiliza para maximizar el alcance y la visibilidad de la marca
* **Consideration (Traffic / Engagement / Video Views)** – Se utiliza para impulsar clics, engagement o visualizaciones de vídeo
* **Conversions** – Se utiliza para impulsar acciones como compras, registros u otros eventos de conversión
* **Catalog Sales (Shopping ads)** – Se utiliza para promocionar productos de un catálogo e impulsar compras

Las audiencias de DCP (listas de clientes) se pueden usar para el targeting directo en todos los tipos de campaña de Pinterest, lo que permite casos de uso de embudo completo, desde el reconocimiento hasta la conversión, incluidas las campañas de shopping/catálogo.

**Caducidad de la conexión:**

* Los tokens de OAuth y los permisos de los Partners pueden caducar o revocarse en función de cambios en la empresa o la cuenta

**Actualización de las audiencias:**

* Validación operativa de la reconexión recomendada: cada 60–90 días
* Actualización de audiencias recomendada: cada 1–7 días, según el tipo de campaña

</Accordion>

<div id="the-trade-desk" />

<Accordion title="The Trade Desk">

**Plataforma del partner de medios:**  
The Trade Desk (TTD)

**Nombre del Partner de medios en DCP:**  
The Trade Desk

**Requisitos de configuración de la conexión y de permisos de la cuenta del Partner de medios:**

* Cuenta de The Trade Desk (TTD) activa
* **Acceso de usuario:**
  * Acceso de nivel Admin o Trader a la cuenta
* **Permisos de audiencias:**
  * Capacidad para crear y gestionar audiencias first-party (segmentos de datos)
* **Intercambio de datos habilitado:**
  * La cuenta debe permitir el Onboarding de datos o la ingestión de audiencias desde Partners externos (como los DCP)
* **Autorización del Partner:**
  * El Partner (DCP) debe estar aprobado y vinculado como proveedor de datos en TTD
* **Credenciales de API (obligatorias)** Necesarias para la carga y activación de audiencias mediante API:
  * Genéralas en la sección «First Party Data Credentials» de TTD (o pídeselas al administrador de tu cuenta de TTD):
    * ID de anunciante
    * Clave secreta del anunciante

**Cómo funciona:**

Se requiere un usuario Admin o Trader durante la configuración para:

* Habilitar la integración
* Generar credenciales de API
* Aprobar el intercambio de datos del partner

Cuando la configuración se haya completado:

* El DCP carga audiencias mediante credenciales de API + configuración del partner
* Las audiencias están disponibles como segmentos de datos de first-party en TTD

**Recursos oficiales:**  
<Anchor target="_blank" href="https://www.thetradedesk.com/">La plataforma The Trade Desk</Anchor>

**Tipos de campaña compatibles:**

Las audiencias first-party creadas en el DCP se pueden activar en los siguientes tipos de campaña de TTD:

* **Display** – Se usa para el targeting directo de audiencias en inventario web y in-app
* **Video (Online Video & CTV)** – Se usa para el targeting en inventario de vídeo programático y TV conectada
* **Audio** – Se usa para el targeting en plataformas de audio digital/streaming
* **Native** – Se usa para el targeting de audiencias en formatos de anuncios nativos

Las audiencias de DCP en The Trade Desk se usan para el targeting directo en todos los tipos de campaña, incluidos Display, Video (CTV & OLV), Audio y Native, lo que permite la activación determinista de audiencias en todos los canales.

**Caducidad de la conexión:**

* Las credenciales de API suelen tener una larga duración hasta que se rotan o revocan manualmente
* Rotación de credenciales recomendada: cada 6–12 meses, según la política de seguridad

**Actualidad de las audiencias:**

* Actualización de audiencias recomendada: diaria o semanal, según el caso de uso de activación y la volatilidad del segmento

</Accordion>

## Crear una conexión de partner

Puedes configurar conexiones con partners como parte del flujo del creador de audiencias o por separado.

<div id="setup-as-part-of-the-audiencebuilder-flow" />

<Accordion title="Configuración como parte del flujo del creador de audiencias">

<span id="h_01HZHF5BWHBE7W8VNM3QFB7K58"></span>**Para crear una conexión con un partner de medios como parte del flujo del creador de audiencias:**

Sigue las instrucciones detalladas <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences#step-3-connect-and-export">aquí</Anchor>.

</Accordion>

<div id="separate-setup" />

<Accordion title="Configuración por separado">

<span id="h_01HZHF5BWH7P8HCWS9SG1JQ2BT"></span>**Para crear una conexión fuera del flujo del creador de audiencias:**

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. Desde el menú de la parte superior derecha, haz clic en **Gestionar conexiones**.
3. Haz clic en **Nueva conexión**. Si ya tienes conexiones en la nube en tu cuenta, las verás todas en **Partner**.
4. En **Nueva conexión con un partner de medios**, selecciona el partner de medios correspondiente.

   <Image alt="Nueva conexión de partners de medios.png" src="https://files.readme.io/1c50a570d4eb495c3d77ee8e572b14a577e39adad65e41fe20eb3b014cce8989-46196842129425.png" width="91.09%" />
5. Ingresa un nombre de conexión.
6. Inicia sesión en la cuenta del partner de medios con tus credenciales y sigue sus instrucciones para habilitar el acceso a AppsFlyer.
7. Haz clic en **Seleccionar ID de cuenta** y selecciona la cuenta relevante para esta conexión.
8. Haga clic en **Guardar**. La nueva conexión se añade a la lista de partners.

</Accordion>

<div data-zendesk-anchors="at-a-glance=resumen-general h_01KNS1JFT1R7K6MCWJRGA2EAAY=resumen-general about-partner-connections=acerca-de-las-conexiones-de-partners h_01KNS1JFT1C788JKA9ZH657TE0=acerca-de-las-conexiones-de-partners h_01KP0WCJVS71MZ5XEXRHRWXX2Q=advertencia media-partner-connections=conexiones-de-partners-compatibles h_01KNS1JFT1CT1AC1C6PAZAM779=conexiones-de-partners-compatibles h_01KNS1JFT1RE8MA525AJ99D9DS=google-ads app-campaigns-aci-ace-guidelines=directrices-de-campa%C3%B1as-de-aplicaciones-aci--ace h_01KQC3Y84E1GT5VJB463N42SFT=directrices-de-campa%C3%B1as-de-aplicaciones-aci--ace h_01KQC759QZPWJ7MWGPK7TJ06HW=notas h_01KNS1JFT1VESJCKHV4S11EKST=dv360 h_01KNS1JFT1P3ZR6EG6YR0M1F98=meta-ads h_01KNS1JFT1GTXJ4PMV5QKSDEX9=tiktok h_01KNS1JFT18VRXFHBYPRTS2MS6=pinterest h_01KNS1JFT2GJMKYNGR6ZRMWN25=the-trade-desk create-a-partner-connection=crear-una-conexi%C3%B3n-de-partner h_01KP115WC2QNT7MAS73HZSHQJT=crear-una-conexi%C3%B3n-de-partner h_01KP11SX0VMYNRCY9C7GKQPYGB=setup-as-part-of-the-audiencebuilder-flow h_01KP11SX0VCAQM5MEGV3RKG086=separate-setup" />
