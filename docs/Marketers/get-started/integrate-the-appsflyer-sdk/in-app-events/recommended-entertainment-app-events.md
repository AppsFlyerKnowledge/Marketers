---
title: Eventos de aplicación recomendados para entretenimiento
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-08-12T12:01:15Z'
  id: 360019699898
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360019699898
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de entretenimiento.

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Entretenimiento

Los usuarios cada vez quieren ver más contenido a demanda, por lo que el mercado de las aplicaciones de entretenimiento en línea se ha vuelto muy competitivo. Los eventos típicos que recomendamos atribuir son: las suscripciones de los usuarios, la transmisión de contenido y la descarga y el almacenamiento de contenido.

Registrar estos eventos puede ayudarte a determinar:

* Qué tipo de contenido consumen los usuarios.
* Rendimiento de la campaña según el contenido que demandan los usuarios
* Engagement y uso por parte de los usuarios.

Estos eventos también son relevantes para las aplicaciones de entretenimiento que se ejecutan en las siguientes TV inteligentes:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

[![Diagrama_de_flujo_para_eventos_recomendados entertainment_app_user_journey](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de entretenimiento. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | Método que elige el usuario para registrarse. | Facebook, Google, correo electrónico |

</Accordion>

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Comenzar prueba (af_start_trial)">

**Finalidad**

Muchos servicios de reproducción en línea les ofrecen a los usuarios un período de prueba para explorar las características premium. Este evento puede ayudarte a:

* Ver cuántos usuarios optaron por un período de prueba.
* Ya sea que la prueba sea parte de una promoción o una colaboración con un partner.
* Qué promoción llevó al usuario a activar el período de prueba.

Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Activador**

Cuando el usuario opta por activar el período de prueba.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| método\_de\_prueba | Método para activar la prueba. | Gratis con un teléfono nuevo, gratis con el proveedor, promoción, código de cupón. |
| identificador\_del\_método\_de\_prueba | Identificador del método de prueba | Nombre del proveedor, por ejemplo, **Vodafone**<br /><br />Nombre del partner, por ejemplo, **Anuncios de Meta**<br /><br />Código del cupón, por ejemplo, **TRA123** |

> 📘 **Nota**
>
> Si vas a asignar este evento al evento StartTrial de Anuncios de Meta y deseas asociar los ingresos, usa el parámetro af\_price en lugar del parámetro af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Suscripción (af_subscribe)">

**Finalidad**

La suscripción es uno de los aspectos fundamentales de los servicios de reproducción en línea (streaming). Este evento puede ayudarte a:

* Ver qué campañas atraen a usuarios que se suscriben.
* Comparar la cantidad de usuarios en período de prueba con los usuarios suscritos.
* Determinar el monto de los ingresos generados a partir de las suscripciones y atribuirlos a campañas y fuentes de medios.

**Activador**

* Cuando el usuario se suscribe correctamente.
* Cuando se renueva una suscripción.

Consulta nuestra Guía general de atribución de suscripciones para obtener más información.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| new\_subscription | Si la suscripción es nueva o se renueva | Verdadero/Falso |
| af\_coupon\_code | Código de cupón, si se usa uno durante la suscripción. | Suscripción por 3 meses |
| coupon\_code\_value | Cuánto deduce el cupón del precio inicial | 10% |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Ingresos asociados con la suscripción. | 5.95 |
| af\_currency | Moneda en que se paga la suscripción. | USD (Dólar estadounidense) |
| subscription\_method | Método de pago usado para la suscripción. | Tarjeta de crédito, billetera electrónica, PayPal |
| expiration\_date | Fecha de vencimiento de la suscripción. | 2018/07/18 |

</Accordion>

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una lista de estructuras de eventos que incluye nombres de eventos personalizados y los parámetros de eventos sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="media-play-media_play" />

<Accordion title="Reproducción de medios (media_play)">

**Finalidad**

Registra los eventos en los que los usuarios reproducen los medios que ofreces. Dichos medios pueden ser, por ejemplo, videos, música, programas de televisión o programas de radio.

Registrar este evento puede ayudarte a determinar:

* Consumo de medios por tipo y contenido.
* Los idiomas del contenido reproducido en línea más popular.
* Duración mínima, máxima y promedio del contenido reproducido en línea.

**Disparador**

Después de una cantidad predefinida, por ejemplo, 2 minutos, de contenido reproducido en línea.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de contenido que se reproduce en línea. | Programa de TV, música |
| af\_content\_id | ID del contenido que se reproduce en línea. | 092, E34 |
| af\_content | El título del contenido, por ejemplo, el nombre de una canción o el título y el episodio de un programa de TV. | Título del contenido |
| duración\_multimedia | Duración total del medio, por ejemplo, la longitud total de un video. | 5 |
| Indicador de atribución AF | Idioma del contenido. | en-us, fr, es |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="Minutos de medios (media_minutes)">

**Finalidad**

Los minutos de medios indican la cantidad de un elemento de contenido determinado que consume el usuario. Después de la métrica de ingresos, esta es la métrica más importante de la industria de la reproducción en línea porque te permite estimar el uso del servicio por parte de los usuarios. Además, te permite saber cuál es la tasa de uso general del servicio y cuál es el contenido más popular. Este evento puede ayudarte a:

* Ver qué usuarios hacen un uso extensivo de tu servicio.
* Saber qué tipos de medios y qué tipos de contenido son populares.

**Disparador**

Una de los siguientes:

* Cuándo el usuario termina de reproducir en línea un elemento de medios.
* Cuándo el usuario deja de reproducir en línea un elemento de medios.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| minutes\_consumed | Número de minutos que el usuario interactuó con el medio. Por ejemplo, la duración total de un video puede ser de 5 minutos, pero un usuario puede que solo vea 3 minutos. | 3 |
| af\_content\_type | Tipo de contenido que se reproduce en línea. | Programa de TV, música |
| af\_content\_id | ID del contenido que se reproduce en línea. | 092, E34 |
| af\_content | El título del contenido, por ejemplo, el nombre de una canción o el título y el episodio de un programa de TV. | Título del contenido |
| duración\_multimedia | Duración total del medio, por ejemplo, la longitud total de un video. | 5 |
| Indicador de atribución AF | Idioma del contenido. | en-us, fr, es |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="Medios descargados (media_downloaded)">

**Finalidad**

Destaca las preferencias del usuario registrando la reproducción de medios y la descarga de medios y comparando ambas. Puedes ver qué medios los usuarios prefieren reproducir y cuáles prefieren descargar.

**Activador**

Cuándo un usuario comienza a descargar medios.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de contenido. | Programa de TV, música |
| af\_content\_id | ID del contenido. | 092, E34 |
| af\_content | El título del contenido, por ejemplo, el nombre de una canción o el título y el episodio de un programa de TV. | Título del contenido |
| duración\_multimedia | Duración total del medio, por ejemplo, la longitud total de un video. | 5 |
| Indicador de atribución AF | Idioma del contenido. | en-us, fr, es |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="Medios guardados (media_saved)">

**Finalidad**

Te ayuda a destacar las preferencias de los usuarios.

**Disparador**

Cada vez que el usuario guarda medios en su dispositivo.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de contenido. | Programa de TV, música |
| af\_content\_id | ID del contenido. | 092, E34 |
| af\_content | El título del contenido, por ejemplo, el nombre de una canción o el título y el episodio de un programa de TV. | Título del contenido |
| duración\_multimedia | Duración total del medio, por ejemplo, la longitud total de un video. | 5 |
| Indicador de atribución AF | Idioma del contenido. | en-us, fr, es |

</Accordion>

<div data-zendesk-anchors="entertainment=-entretenimiento h_01HGTAX1B0KT8Q6PRE41JCPJ60=-entretenimiento h_01HGTAX1B0K2RKYGPFFARM0E1B=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAX1B05C7G67RJPSG3YF66=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=nota h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAX1B1ATFH70K2BJZ7XW13=estructuras-recomendadas-para-eventos-personalizados h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
