---
title: Atribución de invitaciones de usuarios
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2026-08-12T12:25:12Z'
  id: 115004480866
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/115004480866
---
> **En resumen:** Atribuye y registra nuevas instalaciones cuando los usuarios existentes recomiendan a otros que usen tus aplicaciones.

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

<div id="about-user-invite-attribution" />

## Sobre la atribución de invitaciones de usuarios

Las invitaciones de usuario significan que los usuarios de tu aplicación actual comparten enlaces que redireccionan a otros (por ejemplo, sus amigos) para descargar/abrir tu aplicación.

La atribución de invitaciones de usuario significa que atribuyes cualquier nueva instalación de aplicaciones o a los usuarios que enviaron las recomendaciones.

La atribución de invitaciones de usuario te permite:

* Analizar el costo y el ROI de las invitaciones de usuarios. Las invitaciones de usuarios consumen el espacio publicitario de tu aplicación, que de otro modo podría utilizarse para generar ingresos publicitarios. Es posible que desees ver si las invitaciones de usuarios proporcionan un mejor ROI que las alternativas.
* Registrar información sobre tus usuarios que más recomiendan a otros. Los usuarios que invitan a otros a tu aplicación son usuarios de alto valor y comprometidos, a los que tal vez quieras reorientar o incentivar.

También puedes utilizar los datos de los enlaces para:

* Personalizar la experiencia del nuevo usuario. Por ejemplo, que abra la aplicación a un contenido específico o, en lugar de un mensaje general, aparezca un mensaje personalizado de bienvenida, como "¡Hola, Juan!” Tu amiga María quiere desafiarte a un juego. “¡Juega ahora!"
* Recompensar a los usuarios que recomiendan a otros. [Saber más](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

Los enlaces de invitaciones que los usuarios comparten con otros son en realidad enlaces personalizados (URL cortas) de OneLink generados por el SDK de AppsFlyer integrado en tu aplicación. La configuración de tu OneLink garantiza que los usuarios que reciben una invitación sean redireccionado al lugar correcto: a la tienda de aplicaciones correcta, a tu aplicación o a un deep link/deferred deep link a una página específica de tu aplicación. <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">Saber más sobre OneLink</Anchor>

<div id="flow" />

### Flujo

El flujo es el siguiente:

1. El usuario A hace clic dentro de la aplicación para compartirla con un amigo. (El usuario A tiene la aplicación instalada y ha iniciado sesión).
2. El clic genera un enlace con un parámetro que identifica al Usuario A en él.
3. El usuario A envía el enlace al usuario B por correo electrónico/WhatsApp/SMS, etc.
4. Si el usuario B:
   * Tiene instalada la aplicación, se abre. El usuario B se puede enlazar mediante un deep link a una página específica de la aplicación y/o recompensar.
   * Si no tiene instalada la aplicación, se envía a la tienda de aplicaciones correcta. Se puede enviar al usuario B a una página específica en la aplicación mediante deferred deep linking después del primer inicio de la aplicación y/o se puede recompensar al usuario A.
   * Realiza un evento in-app, el Usuario A puede ser recompensado.

<div id="viewing-data" />

## Visualización de datos

Los datos de invitación de usuario están disponibles a través de los dashboards y reportes de AppsFlyer. En los dashboards de AppsFlyer, puedes filtrar la atribución de invitaciones de usuario por:

* **Fuente de medios**: Invitaciones de usuarios.
* **Canal**: Según lo decida el marketer.
* **Campaña**: Según lo decida el marketer.

En los reportes, la fuente de medios (parámetro `pid`) es enviada por el SDK con el valor predeterminado `af_app_invites`.

<div id="procedures" />

## Procedimientos

**Para crear enlaces de invitación de usuario**:

1. Crea una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>.
2. Decide los valores de los parámetros de canal y campaña. Ver [parámetros](/docs/user-invite-attribution#parameters).
3. Decide qué casos de uso deseas para los enlaces. Los casos de uso comunes incluyen:
   * Deep links de nuevos usuarios a una página específica en la aplicación.
   * Registro de qué usuarios hicieron la invitación.
   * Recompensa a los nuevos usuarios.
4. Ponte en contacto con tus desarrolladores de Android e iOS para planificar qué parámetros serán responsables de los casos de uso que deseas para los enlaces. Consulta los [parámetros](/docs/user-invite-attribution#parameters) disponibles.
5. Dile al desarrollador que <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">implemente deep linking</Anchor> (utilizando el comportamiento deseado de los parámetros en el código).
6. Dile al desarrollador que implemente invitaciones de usuario en las siguientes plataformas:

   <Tabs>
   <Tab title="Android">

   Consulta la [invitación de usuario de Android](https://dev.appsflyer.com/hc/docs/dl_android_user_invite) en el Dev Hub.

   </Tab>

   <Tab title="iOS">

   Consulta la [invitación de usuario de iOS](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite) en el Dev Hub.

   </Tab>

   <Tab title="Unity">

   Consulta la [invitación de usuario](https://dev.appsflyer.com/hc/docs/userinvite) en el Dev Hub.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="Parámetros">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### Parámetros/valores proporcionados al desarrollador para implementar en el SDK

<table><thead><tr><th>Parámetro/valor</th><th>Observaciones</th><th>Registra el valor/caso de uso que el desarrollador debe implementar</th></tr></thead><tbody><tr><td>ID de plantilla de OneLink</td><td>El ID de la plantilla de OneLink con la configuración básica en la que se basarán todos los enlaces de invitación de usuario. Por ejemplo: H5hv</td><td> </td></tr><tr><td>Canal</td><td>El nombre del canal. Esto te ayuda a ordenar y ver las atribuciones por canal en la interfaz de usuario de AppsFlyer.</td><td> </td></tr><tr><td>Campaña</td><td>El nombre de la campaña. Esto te ayuda a ordenar y ver las atribuciones por campaña en la interfaz de usuario de AppsFlyer.</td><td> </td></tr><tr><td> <span>is_retargeting=true</span><br/> </td><td>Se agrega si tu campaña es para reorientar a los usuarios existentes.</td><td> </td></tr><tr><td>deep_link_value</td><td>Un parámetro que se usará en el dispositivo del usuario referido para brindarle una experiencia específica. Por lo general, se utiliza para nombrar la página específica a la que se dirigirá a los usuarios. Por ejemplo, si tu aplicación vende frutas, puedes establecer deep links entre los usuarios y la página de manzanas.</td><td> </td></tr><tr><td>deep_link_sub1</td><td rowspan="10">Un parámetro que se usará en el dispositivo del usuario referido para brindarle una experiencia específica. Como el deep_link_value se utiliza normalmente para enviar usuarios a una página específica, este parámetro se puede usar para cualquier otra funcionalidad deseada. Por ejemplo, para agregar una recompensa o un descuento, o para registrar al usuario que hizo la recomendación. </td><td> </td></tr><tr><td>deep_link_sub2</td><td> </td></tr><tr><td>deep_link_sub3</td><td> </td></tr><tr><td>deep_link_sub4</td><td> </td></tr><tr><td>deep_link_sub5</td><td> </td></tr><tr><td>deep_link_sub6</td><td> </td></tr><tr><td>deep_link_sub7</td><td> </td></tr><tr><td>deep_link_sub8</td><td> </td></tr><tr><td>deep_link_sub9</td><td> </td></tr><tr><td>deep_link_sub10</td><td> </td></tr><tr><td>[Opcional] pid</td><td><p>De forma predeterminada, los enlaces que generes incluyen la fuente de medios (parámetro <code>pid</code>) con el valor <code>af_app_invites</code>. </p><p>Para cambiar el valor, tu desarrollador debe agregar un parámetro personalizado llamado <code>pid</code> con el valor que deseas. <strong>Nota</strong>: Para Android, esto solo funciona para el SDK V6.4.2+.</p></td><td> </td></tr><tr><td>Nombre de marca</td><td>El nombre de dominio de marca. Esto te ayuda a ordenar y ver las atribuciones por dominio de marca en la interfaz de usuario de AppsFlyer.</td><td> </td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="Ejemplo">

Mark, el marketer, tiene una aplicación que vende frutas. Quiere crear un deep link a los usuarios a la página de una fruta específica, con la opción de comprar una cantidad específica de fruta.

Quiere que este enlace pueda enviarse a través de una invitación de usuario y recompensar a los referentes cada vez que su recomendación lleve a una nueva instalación de la aplicación y a la compra de frutas.

Para que todo esto funcione, Mark envía a su desarrollador la siguiente lista de parámetros y valores que se utilizarán al implementar los enlaces de invitación de usuario:

| Parámetro | Valor | Observaciones |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | Para deep linking utilizando el método UDL de AppsFlyer. |
| deep\_link\_sub1 | promo\_code | Para deep linking utilizando el método UDL de AppsFlyer. |
| deep\_link\_sub2 | referrer\_id | Para la creación de enlaces a través del SDK. |
| param\_1 | referrer\_id | Para el evento in-app que registra cada compra. |
| Canal | mobile\_share | Para la atribución y para ver datos en AppsFlyer. |
| Campaña | summer\_sale | Para la atribución y para ver datos en AppsFlyer. |

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="record-user-invites-as-inapp-events" />

<Accordion title="Registrar invitaciones de usuarios como eventos in-app">

Registrar un evento in-app después de que un usuario envía una invitación de usuario te ayuda a identificar a los usuarios que recomiendan a otros, así como a las fuentes de medios que te dan estos referentes.

**Para registrar un evento in-app de invitación de usuario**:

* Envía un <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#invite-af_invite">evento af\_invite</Anchor>. El desarrollador debe implementar esto siguiendo las instrucciones de nuestro centro de desarrollo.

**Nota**: Puedes agregar más parámetros que desees asociar con el evento. Elige parámetros que proporcionen contexto adicional al evento y enriquezcan los datos. <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">Saber más</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="Recompensa a los referentes por las instalaciones de invitaciones de usuario">

**Para recompensar a los referentes por una invitación de usuario que resulte en una instalación**:

1. Asegúrate de que el ID del referente sea el valor de uno de los [parámetros deep\_link\_sub1-10](/docs/user-invite-attribution#parameters).
2. Dile a los desarrolladores de tu aplicación que <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">implementen deep linking</Anchor> (usando el comportamiento deseado del parámetro elegido en el código).
3. Dile a tus desarrolladores de backend que trabajen con tus desarrolladores de aplicaciones para recuperar los IDs de referencias (de los reportes de AppsFlyer) y recompensar a los referentes.

Ejemplo:

1. El usuario A invita al usuario B a instalar tu aplicación.
2. Cuando el usuario B inicia la aplicación, la aplicación obtiene el ID de referencia del usuario A.
3. Tu backend recupera el ID de referencia de los reportes de AppsFlyer.
4. En tu backend, agrega el ID de referencia del usuario A a una lista de usuarios que serán recompensados.
5. Cuando el usuario A inicie la aplicación, verifica si su ID de referencia está en la lista de usuarios para ser recompensados y, si lo está, recompensarlo.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="Recompensar a los referentes por las acciones de los usuarios referidos">

**Para recompensar a los referentes por una invitación de usuario que resulta en un evento in-app específico**:

1. <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#configuración-de-eventos-in-app">Crea el evento in-app</Anchor> que deseas recompensar.
2. Dile al desarrollador que agregue un parámetro (por ejemplo, param\_1) al evento con el valor de ID de referencia. **Nota**: El ID de referencia se registra originalmente en la instalación de la aplicación utilizando el [parámetro](/docs/user-invite-attribution#parameters) seleccionado (deep\_link\_sub1-10).
3. Dile a tus desarrolladores de backend que trabajen con tus desarrolladores de aplicaciones para recuperar los IDs de referencias (de los reportes de AppsFlyer) y recompensar a los referentes.

Ejemplo:

1. El usuario A invita al usuario B a realizar una acción en tu aplicación.
2. Cuando el usuario B realiza la acción, se atribuye un evento in-app que contiene el ID de referente del usuario A.
3. Tu backend recupera el ID de referencia de los reportes de AppsFlyer.
4. En tu backend, agrega el ID de referencia del usuario A a una lista de usuarios que serán recompensados.
5. Cuando el usuario A inicie la aplicación, verifica si su ID de referencia está en la lista de usuarios para ser recompensados y, si lo está, recompensarlo.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Versión del SDK | Debes tener la versión 4.8.0 o superior del SDK de AppsFlyer y la versión 4.17.0 o superior del SDK de Unity. |
| <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Landing page de aplicaciones de redes sociales</Anchor> | Los enlaces generados a partir de las invitaciones de usuarios no pueden implementar landing pages de aplicaciones de redes sociales. |
| Tiempo de vida (TTL) | El tiempo de vida predeterminado (TTL) para las URLs cortas de OneLink creadas a través de una invitación de usuario de SDK es de 60 días. Se extiende 60 días cada vez que se hace clic en el enlace. |
| Límite de carga útil | El valor de carga útil de los parámetros del enlace no debe superar los 3.000 caracteres. |
| Precios | Incluido en los planes de suscripción OneLink Standalone y Attribution.<br /><br />**Nota:** Si tu paquete finaliza o se cancela, el SDK de invitación de usuario dejará de generar nuevos enlaces de invitación y cualquier flujo de invitación relacionado se verá afectado. Los enlaces de invitación existentes seguirán funcionando. |
| iOS 14+: | La atribución de invitación de usuarios no utiliza el IDFA, por lo que iOS 14 no lo afecta de ninguna manera. |
| ID de URL | El ID de URL (o ID de enlace corto) se puede editar para resaltar la oferta de tu campaña. Por ejemplo: https://myapp.onelink.me/abc123/apples. El ID de URL no debe superar los 50 caracteres y puede ser una combinación de letras y números. Por defecto, tiene 8 caracteres.<br /><br />**Nota**: Solo puedes editar el ID de URL si el ID actual aún no está en uso. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=sobre-la-atribuci%C3%B3n-de-invitaciones-de-usuarios h_01H98E1CZ2AG8AW2H77SPPHFGR=sobre-la-atribuci%C3%B3n-de-invitaciones-de-usuarios flow=flujo h_01H98E1CZ234MRBWDEYGZFCDRE=flujo viewing-data=visualizaci%C3%B3n-de-datos h_01H98E1CZ23FEAS8JJC7FFTFXD=visualizaci%C3%B3n-de-datos procedures=procedimientos h_01H98E1CZ2VBCG0RREERW8FNJE=procedimientos h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=par%C3%A1metrosvalores-proporcionados-al-desarrollador-para-implementar-en-el-sdk h_01H98E1CZ2CANBK1T55DD103JB=par%C3%A1metrosvalores-proporcionados-al-desarrollador-para-implementar-en-el-sdk h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=informaci%C3%B3n-adicional h_01H98E1CZ28T2SJ3YNY8TNCAZY=informaci%C3%B3n-adicional h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
