---
title: Utiliza la API de OneLink para crear enlaces en campañas a gran escala
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-10-29T01:24:08Z'
  id: 360001250345
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** La API de OneLink te ayuda a captar la atención de los usuarios finales y a aprovechar los medios propios mediante la generación de enlaces personalizados en campañas a gran escala, a través de SMS y mucho más. Úsalo para crear viajes fluidos entre canales, profundizar el engagement y mejorar la conversión.

<div id="about-onelink-api" />

## API de OneLink

La API de OneLink es una función premium que te permite convertir cualquier canal propio en una ruta directa a tu aplicación móvil. Al generar enlaces cortos personalizados de forma programática, puedes ofrecer viajes de usuario personalizados a escala, profundizar el engagement e impulsar más conversiones en SMS, correo electrónico, sitios web, publicaciones en redes sociales y mucho más. Con la API de OneLink, puedes:

* https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link
* Los parámetros relacionados con la atribución, usados para medir y monitorear esfuerzos de marketing, como fuentes de medios, campañas y activos.**Nota**: El parámetro de la fuente de medios (pid) es obligatorio.
* Estos parámetros te permiten enviar a los usuarios a contenido personalizado in-app, por ejemplo, una página de producto específica, un código de cupón o una promoción.
* Genera automáticamente grandes volúmenes de enlaces cortos y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-qr">QR code</Anchor>.
* Personaliza el TTL (Time To Live) y el comportamiento de renovación por caso de uso. <Anchor target="_blank" href="/marketers/es/docs/bulletin-onelink-short-url-ttls-automatically-extend">Más información</Anchor>
* Aplica una validación estricta de parámetros para garantizar un comportamiento de redirección predecible y una medición fiable.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">Consulta el uso de la cuota</Anchor> para gestionar el consumo.

<div id="example" />

> 📄 **Ejemplo**
>
> Una aplicación global de viaje genera millones de enlaces cortos contextuales al día en experiencias de CRM, correo electrónico y QR. Con la API de OneLink v2.0, su plataforma de automatización crea enlaces profundos por usuario que respetan la configuración regional, el nivel de fidelización y los destinos específicos in-app, al tiempo que mantiene la gobernanza y una medición coherente en todos los mercados. Prácticas recomendadas:

<div id="get-started" />

## Comienza

**La API de OneLink es una función premium que se utiliza para:**

**Requisito previo:** Una cuenta de AppsFlyer. Para acceder a la API de OneLink, contacta con tu CSM o escríbenos a hello@appsflyer.com.

**Para configurar la API de OneLink:**

1. Copia el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#tipos-de-token">token de la API de OneLink</Anchor>.
2. <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Crea una plantilla de OneLink</Anchor>.
3. Copia el ID de la plantilla de OneLink.   
   <Image align="center" alt="" src="https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg" />
4. Comparte el ID de la plantilla y el token de API con el desarrollador y pídele que siga estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">instrucciones</Anchor>.

<div id="dashboard" />

## **Panel de Control**

El dashboard de la API de OneLink muestra nuestro uso diario, mensual y trimestral de la API. Esto te ayuda a llevar el monitoreo de tu consumo frente al límite de cuota mensual. 

**Para ver el dashboard de la API de OneLink**: 

En AppsFlyer, en el menú lateral, selecciona **Engage** > **API de OneLink**.

<div id="use-cases" />

## CASOS DE USO

Los siguientes casos de uso destacan formas habituales de usar la API de OneLink para crear viajes fluidos y contextuales hacia tu aplicación.

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<Accordion title="Viajes multiplataforma (CTV, desktop, Web-to-app)">

Genera enlaces de corta duración o por sesión que ayuden a los usuarios a moverse sin fricciones entre dispositivos. Algunos ejemplos habituales incluyen QR code en anuncios de TV o flujos de «escanea para continuar» en desktop que llevan a los usuarios directamente al paso in-app correcto.

**Valor:** Continuidad sin fricciones y mejora de la conversión entre dispositivos.

</Accordion>

<div id="crmpowered-channels-sms-email-whatsapp" />

<Accordion title="Canales impulsados por CRM (SMS, correo electrónico, WhatsApp)">

Crea enlaces cortos personalizados por usuario en el momento del envío para mensajes de alta intención, como alertas de bajada de precio, listas de espera, campañas de recuperación, recordatorios de facturas o flujos de inicio de sesión mágico.

**Valor:** Personalización a escala con una atribución coherente.

</Accordion>

<div id="offline-and-qrbased-engagement" />

<Accordion title="Engagement offline y basado en QR">

Genera enlaces escaneables para materiales en tienda, recibos, embalajes o señalización de eventos. Puedes actualizar la configuración de destino sin tener que volver a imprimir los materiales físicos.

**Valor:** Enrutamiento dinámico y atribución offline sin tener que reimprimir activos físicos.

</Accordion>

<div id="referral-and-advocate-sharing" />

<Accordion title="Compartición de referidos y defensores de la marca">

Habilita enlaces cortos compartibles para programas de referencias de influencers, creadores o clientes, con parámetros personalizables y enrutamiento preparado para la atribución.

**Valor:** Medición escalable y atribución precisa para las referencias.

</Accordion>

<div id="traits-and-limitations" />

## **Características y limitaciones**

En esta sección se enumeran algunos de los principales atributos y limitaciones de la API de OneLink. Dile al desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">instrucciones del centro de desarrollo</Anchor>.

| Caducado | Observaciones |
| --- | --- |
| Límite de cuota de la API | <ul><li>El límite para usar la API de OneLink para crear, editar o eliminar enlaces de OneLink es de 7,5 millones al mes (zona horaria UTC), por cuenta.</li><li>Las solicitudes POST, PUT y DELETE cuentan para este límite. Las solicitudes GET y las solicitudes GET de QR no cuentan para la cuota.</li><li>No se atienden todas las solicitudes que se realizan después de superar esta cuota y no se crean los enlaces; la llamada a la API recibe el código de estado de error 429 con el mensaje «Se ha superado la cuota mensual».</li><li>Puedes comprobar cuánto de la cuota se ha usado o queda disponible de una de estas formas:<br />• Visita la página de la API de OneLink en la plataforma de AppsFlyer para ver el historial de uso de los últimos 4 meses, o<br />• Usa la API GET de cuota para recuperar el estado actual de tu cuota.<br />También puedes usar la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">API GET de cuota</Anchor> para activar alertas internas cuando tu uso se acerque al umbral definido.</li></ul> |
| Visibilidad de los enlaces | <ul><li>Los enlaces creados mediante la API no aparecen en la lista de enlaces personalizados de OneLink en el dashboard de AppsFlyer.</li></ul>af\_dp |

<div data-zendesk-anchors="onelink-api=api-de-onelink h_01HJR5MAKKNH236MVDZ03X1B1P=api-de-onelink h_01HJR5MAKKTDRPS0WQ44VN594X=ejemplo get-started=comienza h_01KATK4KWTGSHTW5BEY8TEE5JD=comienza dashboard=panel-de-control h_01KATKWCPHZB1MKCJ8DVDYZ1B3=panel-de-control use-cases=casos-de-uso h_01KAGQNZZA0NM19KV29QZ9ZDKP=casos-de-uso h_01KBJ92FSTKCH9KXGWKJAF1DFH=crossplatform-journeys-ctv-desktop-webtoapp h_01KBJ92FST51NKDB465N76EX3M=crmpowered-channels-sms-email-whatsapp h_01KBJ92FST5H7V5S13TZ502VJV=offline-and-qrbased-engagement h_01KBJ92FST4FP4ZES5T643DD3R=referral-and-advocate-sharing traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KAGQP00QZ2VBE9EY3SNPHGBP=caracter%C3%ADsticas-y-limitaciones" />
