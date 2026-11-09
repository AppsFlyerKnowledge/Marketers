---
title: Eventos de aplicación recomendados para gaming
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-08-12T12:01:26Z'
  id: 360018941117
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/360018941117
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su trayectoria de usuario registrando estos eventos in-app sugeridos para tu aplicación de gaming.

## <Image alt="Eventos_en_la_aplicación_juegos.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" /> Gaming

Las aplicaciones de gaming incluyen juegos de tipo arcade, estrategia, educativos y juegos de azar. Los eventos típicos que recomendamos registrar son las compras in-app, las instancias en que los usuarios comparten en redes sociales y las invitaciones a amigos. Además, puedes incluir eventos como subir de nivel y completar un tutorial en el juego.

Registrar estos eventos puede ayudarte a determinar:

* Qué ofertas los usuarios compran más.
* Cuán involucrados están los usuarios.
* Cuántos usuarios publican contenido compartido en las redes sociales.
* Cuántos usuarios invitan a amigos a instalar la aplicación.

Estos eventos también son relevantes para aplicaciones de gaming compatibles con las siguientes plataformas:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Dispositivos móviles con Windows

<div id="important" />

> 🚧 **¡Importante!**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para más información sobre cómo registrar eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía Eventos in-app enriquecidos</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events recorrido del usuario de la app de gaming" src="https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos que son típicas de la vertical de gaming. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="login-af_login" />

<Accordion title="Acceso (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Finalidad**

Muchas aplicaciones de gaming permiten a los usuarios comprar artículos, por ejemplo, monedas, gemas o armas. Registrar estas compras puede ayudarte a:

* Determinar el valor de vida útil (LTV) de tus usuarios y el ROI de tus campañas en todas las agencias y redes de publicidad.
* Determinar qué ofertas son las más populares entre tus usuarios.
* Establecer referencias cruzadas entre las campañas y los artículos comprados a fin de optimizar el targeting de las campañas.

Para reportar un evento que incluye varios elementos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aquí</Anchor>.

**Disparador**

Cuando el usuario llega a la página de agradecimiento después de una compra exitosa.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Los ingresos estimados de la compra | 199.99 |
| af\_currency | Código de moneda | THB, USD |
| af\_quantity | Cantidad de artículos comprados | 2 |
| af\_content\_id | ID del artículo | 001, 092 |
| af\_order\_id | ID del pedido | 9277 |
| af\_receipt\_id | ID del recibo | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Nivel alcanzado (af_level_achived)">

**Finalidad**

Una de las principales metas de los usuarios es subir de nivel en los juegos. Con frecuencia, cuando se sube de nivel, se obtiene acceso a características y fases nuevas del juego, y esto alienta a los usuarios a seguir jugando. Registrar el nivel de logro puede ayudarte a:

* Determinar qué campañas generan mayor actividad por parte de los usuarios.
* Ver qué tipos de usuarios son los más activos e involucrados.
* Asociar la actividad general de los usuarios con dimensiones como los ingresos.

**Disparador**

Cuando el usuario llega a la página de finalización de nivel.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_level | Nivel alcanzado por el usuario | 3 |
| af\_score | Puntuación asociada con el logro del usuario | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Finalización del tutorial (af_tutorial_completion)">

**Finalidad**

Los tutoriales brindan a tus usuarios orientación sobre cómo usar la aplicación. Registrar este evento puede ayudarte a determinar:

* Con qué temas pueden tener problemas los usuarios.
* Qué tutoriales no dan buenos resultados.

**Disparador**

* Cuando un usuario finaliza el tutorial
* Cuando un usuario comienza el tutorial, pero lo abandona sin finalizarlo

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_success | Si el usuario completó el tutorial. | Verdadero |
| af\_tutorial\_id | ID del tutorial. | 3 |
| af\_content | Nombre del tutorial. | Primeros pasos |

</Accordion>

<div id="share-af_share" />

<Accordion title="Compartir (af_share)">

**Finalidad**

A los usuarios les gusta compartir sus logros en juegos a través de los sitios de redes sociales. Compartir este contenido genera conocimiento de marca y puede impulsar a que más usuarios descarguen e instalen tu aplicación. Registrar este evento te ayuda a saber cuándo es más probable que los usuarios compartan la aplicación con sus amigos. Aprender más sobre <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">cómo registrar el contenido compartido y las invitaciones</Anchor>.

**Disparador**

Cuando un usuario publica satisfactoriamente contenido compartido en las redes sociales.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_description | Motivo para compartir en las redes sociales, p. ej., lograr nueva puntuación alta o subir de nivel. | Logar nueva puntuación alta, Subir de nivel, Juego ganado |
| Identificador de origen | Plataforma utilizada para publicar contenido compartido | Facebook, WhatsApp, correo electrónico |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Invitar (af_invite)">

**Finalidad**

Descubre en qué sitios de redes sociales envían invitaciones los usuarios y cuántos usuarios invitaron a sus amigos a descargar e instalar la aplicación.

**Disparador**

Cuando el usuario invitó con éxito a un amigo a descargar e instalar la aplicación.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| af\_description | Contexto de la invitación | Prueba esta aplicación |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una estructura de evento que incluye un nombre de evento personalizado y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="Bonificación reclamada (bonus_claimed)">

**Finalidad**

Mira cuántos usuarios reclamaron las bonificaciones que se les ofrecen y asocia las bonificaciones reclamadas con la actividad y el engagement del usuario.

**Disparador**

Cuando el usuario solicita una bonificación y se actualiza en su cuenta.

**Parámetros del evento**

| Nombre | Descripción | Valor de ejemplo |
| --- | --- | --- |
| bonus\_type | Tipo de bonificación que el usuario reclama | Monedas |

</Accordion>

<div data-zendesk-anchors="gaming=-gaming h_01HGTAVT1XSEY0TS9T2R1H1KXV=-gaming h_01HGTAVT1XTXYHV1MTFR20BR6J=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAVT1X4QQS6GREKC0N0VK6=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAVT1YXGTF0E5YQX1C3CJN=estructuras-recomendadas-para-eventos-personalizados h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
