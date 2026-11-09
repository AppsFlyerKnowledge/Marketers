---
title: Eventos recomendados para apuestas deportivas
metadata:
  keywords:
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
  created_at: '2021-11-11T13:24:45Z'
  edited_at: '2026-08-12T12:01:46Z'
  id: 4410672219025
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/4410672219025
---
> **De un vistazo:** Mide la calidad de tus usuarios a lo largo de su viaje como usuarios registrando estos eventos in-app sugeridos para tu aplicación de apuestas deportivas.

<div id="-sports-betting" />

## <Image alt="balón_de_fútbol.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="71px" /> Apuestas deportivas

Las aplicaciones de apuestas deportivas permiten a los apostantes realizar apuestas en una variedad de mercados deportivos. Los eventos típicos que sugerimos registrar son los depósitos, realizar apuestas y las retiradas.

Registrar estos eventos puede ayudarte a determinar:

* Calidad de los usuarios de tu aplicación
* Cuán involucrados están los usuarios.
* Ingresos generados a través de las apuestas
* Qué tipos de apuestas generan los ingresos más bajos o más altos

<div id="important" />

> 🚧 **Importante:**
>
> * Asegúrate de leer las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">instrucciones</Anchor> para marketers sobre la implementación de eventos in-app.
> * (Próximamente) Para agilizar el proceso de implementación, usa nuestro <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">generador de eventos in-app</Anchor>. Esta herramienta incluye todos los eventos in-app típicos que se describen en este artículo y te permite modificar los eventos de acuerdo con tus necesidades comerciales. Una vez completado, comparte el archivo con tu desarrollador.
> * Para cada evento recomendado incluido en este artículo, hay <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">ejemplos de código</Anchor> para desarrolladores de iOS, Android y Unity.
> * Puedes encontrar instrucciones detalladas para tu desarrollador en el **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">centro para desarrolladores de AppsFlyer</Anchor>.**
>
> Para obtener más información sobre la grabación de eventos in-app, consulta la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía de eventos in-app</Anchor>.

<Image align="center" alt="In_appEvents_UserJourneys_-_Sports_betting__5_.png" src="https://files.readme.io/7a47ba917ebc5a6e661efb23b078675c16ce43c59c41f9c6fd6fd89d37c242bf-4424606611473.png" />

<div id="recommended-structures-for-predefined-events" />

## Estructuras recomendadas para eventos predefinidos

La siguiente sección proporciona una lista de estructuras de eventos típicas del vertical de apuestas deportivas. Cada estructura incluye un nombre de evento predefinido y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="login-af_login" />

<Accordion title="Iniciar sesión (af_login)">

**Finalidad**

Comprender la retención de tus usuarios registrados.

**Disparador**

Cuando el usuario accede correctamente.

**Parámetros del evento**

Se puede enviar sin ningún parámetro adicional.

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Completar registro (af_complete_registration)">

**Finalidad**

Descubrir cuántos usuarios instalaron la aplicación y completaron el proceso de registro, y qué métodos de registro prefieren tus usuarios.

**Disparador**

Cuando el usuario completa el proceso de registro y la aplicación confirma el registro (sin errores).

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_registration\_method | El tipo de método de registro | correo electrónico, facebook |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estructuras recomendadas para eventos personalizados

La siguiente sección proporciona una estructura de evento que incluye un nombre de evento personalizado y los parámetros del evento sugeridos para usar. Ten en cuenta que los eventos in-app pueden incluir cualquier parámetro de evento que cumpla con las necesidades de tu negocio.

<div id="first-time-deposit-first_time_deposit" />

<Accordion title="Primer depósito (first_time_deposit)">

**Finalidad**

Registrar este evento puede ayudarte a determinar:

* Cuando los usuarios realizan un primer depósito
* Ingresos generados por los primeros depósitos

Además, los Partners de ad network pueden optimizar tus campañas publicitarias mediante targeting a usuarios que han realizado un primer depósito.

**Disparador**

La primera vez que el usuario realiza un depósito en su cuenta de apuestas

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetario del depósito realizado | 200 |
| af\_currency | Moneda en la que se realizó el depósito | AUD |

</Accordion>

<div id="deposit-deposit" />

<Accordion title="Depósito (deposit)">

**Finalidad**

Determina el valor de los depósitos que realizan tus usuarios.

**Disparador**

Depósito posterior que el usuario realiza después del primer depósito

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetario del depósito realizado | 200 |
| af\_currency | Moneda en la que se realizó el depósito | AUD |

</Accordion>

<div id="placed-bet-placed_bet" />

<Accordion title="Apuesta realizada (placed_bet)">

**Finalidad**

Descubre qué eventos generan la menor cantidad de ingresos y cuáles generan la mayor.

**Disparador**

Cuando se realiza una apuesta correctamente

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Valor monetario de la apuesta realizada | 100 |
| af\_currency | Moneda en la que se realizó la apuesta | AUD |
| event\_number | Identificador único del evento en el que se realizó la apuesta | 123789 |
| Cadena | Fecha del evento en el que se apostó | 13122021 |
| event\_time | Hora del evento en el que se apostó | 17:30 |
| transaction\_id | ID de la apuesta realizada | 221 |

</Accordion>

<div id="withdrawal-withdrawal" />

<Accordion title="Retirada (retirada)">

**Finalidad**

Descubre cuándo los usuarios retiran dinero que habían depositado previamente en su cuenta de apuestas.

**Disparador**

Cuando un usuario retira dinero de su cuenta de apuestas

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Valor monetario de la retirada. Regístralo como un valor de ingresos negativo. | -100 |
| af\_currency | Moneda que se retiró | AUD |

</Accordion>

<div id="bonus-bet-bonus_bet" />

<Accordion title="Apuesta de bonificación (bonus_bet)">

**Finalidad**

Las apuestas de bonificación son apuestas opcionales que los propietarios de apps pueden usar para recompensar a los apostantes como incentivo de registro o depósito, o como promoción para realizar un determinado tipo de apuesta.

Registrar este evento te ayuda a determinar el valor total de las apuestas de bonificación otorgadas a los usuarios y el número de usuarios que realizaron una apuesta de bonificación.

**Disparador**

Cuando se realiza una apuesta correctamente

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Valor monetario de la apuesta realizada | 100 |
| af\_currency | Moneda en la que se realizó la apuesta | AUD |
| event\_number | Identificador único del evento en el que se realizó la apuesta | 123789 |
| Cadena | Fecha del evento en el que se apostó | 13122021 |
| event\_time | Hora del evento en el que se apostó | 17:30 |
| bonus\_id | ID de la apuesta de bonificación | 221 |

</Accordion>

<div id="cancels-bet-canceled_bet" />

<Accordion title="Cancela la apuesta (canceled_bet)">

**Finalidad**

Este evento puede ayudarte a:

* Registrar a los usuarios que cancelan apuestas constantemente
* Saber cuántas apuestas se cancelan
* Conocer los motivos por los cuales se cancela una apuesta

**Disparador**

Cuando el usuario cancela una apuesta

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Valor monetario de la apuesta realizada | 100 |
| af\_currency | Moneda en la que se realizó la apuesta | AUD |
| event\_number | Identificador único del evento en el que se realizó la apuesta | 123789 |
| Cadena | Fecha del evento en el que se realizó la apuesta | 13122021 |
| event\_time | Hora del evento en el que se realizó la apuesta | 17:30 |

</Accordion>

<div id="account-deducted-account_deducted" />

<Accordion title="Cuenta debitada (account_deducted)">

**Finalidad**

Registrar y guardar los débitos en las cuentas de usuario

**Disparador**

Cuando se pierde una apuesta

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Valor monetario de la apuesta realizada | 100 |
| af\_currency | Moneda en la que se realizó la apuesta | AUD |
| account\_number | Identificador único de la cuenta del usuario | 15780 |
| event\_number | Identificador único del evento en el que se realizó la apuesta | 123789 |
| Cadena | Fecha del evento en el que se realizó la apuesta | 13122021 |
| event\_time | Hora del evento en el que se realizó la apuesta | 17:30 |

</Accordion>

<div id="account-credited-account_credited" />

<Accordion title="Cuenta acreditada (account_credited)">

**Propósito**

Registrar y guardar los créditos en las cuentas de usuario

**Disparador**

Cuando se gana una apuesta

**Parámetros del evento**

| Nombre | Nota | Valor de ejemplo |
| --- | --- | --- |
| af\_price | Valor monetario de la apuesta realizada | 100 |
| af\_currency | Divisa en la que se realizó la apuesta | AUD |
| account\_number | Identificador único de la cuenta del usuario | 15780 |
| event\_number | Identificador único del evento en el que se realizó la apuesta | 123789 |
| Cadena | Fecha del evento en el que se apostó | 13122021 |
| event\_time | Hora del evento en el que se apostó | 17:30 |

</Accordion>

<div data-zendesk-anchors="sports-betting=-apuestas-deportivas h_01HGTAE0AT9KD9RKX7XPR7A4AT=-apuestas-deportivas h_01HGTAE0ATTMEART2R1BD1ZDSB=importante recommended-structures-for-predefined-events=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAE0ATYW0RDDZZD5EAR7BZ=estructuras-recomendadas-para-eventos-predefinidos h_01HGTAE0ATMBJVKS14SGWGK0DG=login-af_login h_01HGTAE0ATHZWSM0R9A6R9BV96=complete-registration-af_complete_registration recommended-structures-for-custom-events=estructuras-recomendadas-para-eventos-personalizados h_01HGTAE0ATJQDWWBB8D836QRJ5=estructuras-recomendadas-para-eventos-personalizados h_01HGTAE0AT3ZBH5G16QJW4MGQ1=first-time-deposit-first_time_deposit h_01HGTAE0ATTRCNX1Y4AFJ8VGWC=deposit-deposit h_01HGTAE0ATNW97Y8WJWWXTXX7V=placed-bet-placed_bet h_01HGTAE0ATPB6KHMHHBW7T9B0Q=withdrawal-withdrawal h_01HGTAE0ATGS9VS7QY1974XAPY=bonus-bet-bonus_bet h_01HGTAE0AVKKGGJCB9WWXMWT0D=cancels-bet-canceled_bet h_01HGTAE0AVMB59TDT6AM65DE94=account-deducted-account_deducted h_01HGTAE0AVXMY0J983V9NTYQ2J=account-credited-account_credited" />
