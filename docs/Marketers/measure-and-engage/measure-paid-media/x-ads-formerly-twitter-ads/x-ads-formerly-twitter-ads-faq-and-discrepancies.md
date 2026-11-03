---
title: 'Guía de configuración de Twitter Ads: preguntas frecuentes y discrepancias'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2026-11-03T01:58:52Z'
  id: 4410464352017
  locale: es
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/es/articles/4410464352017
---
> **De un vistazo:** Resuelve las preguntas frecuentes sobre los Twitter Ads y comprende las discrepancias.

## Preguntas frecuentes y discrepancias sobre Twitter Ads

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="¿Quién puede realizar la configuración de Twitter en AppsFlyer?">

El usuario que autoriza la integración entre AppsFlyer y Twitter deberá tener acceso de Administrador a la Cuenta de Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="¿Qué ocurre si no hay ninguna cuenta de X Ads seleccionada para la atribución en AppsFlyer?">

Todas las atribuciones son para campañas de la cuenta seleccionada. Si no hay ninguna cuenta seleccionada, no se enviará ningún evento in-app ni atribución a Twitter, incluso si la asignación de eventos in-app aún está visible en la ventana de Configuración de Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="¿El propietario de la cuenta y los integrantes del equipo ven los mismos datos de Twitter?">

N.º El propietario de la cuenta ve todas las cuentas de Twitter conectadas. Los miembros del equipo solo ven sus cuentas de Twitter conectadas.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="¿Cómo desconecto AppsFlyer de X Ads?">

Puedes desconectar AppsFlyer de tu cuenta de Twitter. Las siguientes instrucciones suponen que has iniciado sesión en tu cuenta de Twitter utilizando un navegador de computadora de escritorio o portátil:

1. Inicia sesión en X Ads.
2. En el menú de la izquierda, haz clic en **Más** > **Configuración y privacidad**.
3. Ve a **Seguridad y acceso a la cuenta** > **Aplicaciones y sesiones** > **Aplicaciones conectadas**.
4. Haz clic en AppsFlyer.
5. Haz clic en **Revocar acceso**.

Ahora puedes volver a tu cuenta de AppsFlyer y <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-integration-setup">conectar una cuenta de Twitter diferente</Anchor> si lo deseas.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="¿Es posible atribuir instalaciones a varias cuentas de X Ads?">

Sí, pero requiere algunas acciones en anuncios de X. Primero, es necesario tener algunos antecedentes:

Puede conectar **solamente un nombre de usuario** (también llamado usuario de Twitter) a su cuenta de AppsFlyer. Cuando conectes este identificador, tu cuenta de anuncios de X aparecerá en la configuración de anuncios de X en el dashboard de AppsFlyer.

Si uno de los miembros de tu equipo también tiene una cuenta de anuncios de X, significa que tiene un identificador distinto al tuyo y no puede conectar su identificador a AppsFlyer. Esto se debe a que **su nombre de usuario es el que ya está conectado a su cuenta de AppsFlyer**. Para que su cuenta de anuncios de X también aparezca en AppsFlyer, tiene que **dar acceso a tu identificador como administrador de la cuenta en su cuenta de anuncios de X**.

Digamos que la integrante de tu equipo es Jenny y que su identificador es @jenny. Tu identificador es @nivi y es el que está conectado a AppsFlyer. Para que su cuenta de anuncios de X aparezca en la cuenta de AppsFlyer, **tiene que dar acceso a tu identificador como administrador de la cuenta en su cuenta de anuncios de X**. Jenny tiene que dar acceso a Nivi a su cuenta de anuncios de X, y no al revés. Cuando lo hace, AppsFlyer observa el identificador de Nivi y ve todas las cuentas de anuncios con las que está asociado, incluida la de Jenny.

**Para conectar la cuenta de anuncios de X de Jenny a AppsFlyer:**

1. Jenny inicia sesión en <Anchor target="_blank" href="https://ads.x.com/">X Ads</Anchor> con el identificador @jenny.
2. En su cuenta de anuncios de X, Jenny abre la configuración de acceso a la cuenta y da acceso a @nivi como **administrador de la cuenta**. Consulta las <Anchor target="_blank" href="https://help.x.com/en/business-and-advertising/multi-user-login-faq">Preguntas frecuentes sobre el login multiusuario</Anchor> en el Centro de ayuda de X.
3. Jenny inicia sesión en AppsFlyer, va a **Colaborar** > **Integraciones de partners** > **Integraciones activas**, busca **X Ads** y lo selecciona.
4. Su cuenta de anuncios de X ahora aparece en la configuración de la integración, y ella puede configurar la integración. Jenny solo ve su cuenta de anuncios de X. El administrador de la cuenta ve todas las cuentas de anuncios de X conectadas, incluida la suya.

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="¿Hay alguna instrucción especial para las agencias?">

Sí.  
Cuando una agencia crea una nueva campaña de Twitter, el nombre de la campaña debe comenzar con el nombre de la agencia seguido de un guion bajo (Ejemplo: "NombredeAgencia\_Campaña1").

> 📘 **Nota**
>
> Para establecer la conexión entre AppsFlyer y Twitter, el anunciante DEBE configurar Twitter de modo que permita a las agencias procesar tráfico de Twitter.

Para conocer más detalles, ingrese <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#configuraciones-de-srn">aquí</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="¿El raw data de X Ads está disponible para las agencias?">

No proporcionamos raw data de X Ads a las agencias porque las condiciones del servicio de X Ads consideran a las agencias como terceros.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Hago clic en Guardar y Cerrar, pero no se guarda la configuración de Twitter. ¡Ayuda!">

Si tu aplicación estuvo suscrita a otro proveedor de atribución anteriormente, que se utilizó para atribuir instalaciones de Twitter, pueden aparecer los siguientes errores cuando configuras Twitter en el panel de control de AppsFlyer:

**Error:  La aplicación está asociada con otro proveedor de atribución. Asóciala con AppsFlyer.**

También puede aparecer el siguiente error:  

[![](https://files.readme.io/cdad9e9adb2eb7408af3a4ba53ff0dfdf2bbb666f460741996a9d1cda79e399d-21402353721361.png)](https://files.readme.io/cdad9e9adb2eb7408af3a4ba53ff0dfdf2bbb666f460741996a9d1cda79e399d-21402353721361.png)

**Error:  Ocurrió un error al guardar la configuración de Twitter. No fue posible actualizar algunas cuentas:  XX Varios ID de proveedores para el mismo (appid, conversionType) del evento appid2872.**

Si la selección de cuenta no se guarda, esto puede deberse a que la cuenta de Twitter en cuestión estuvo anteriormente asociada con otro proveedor del lado de Twitter. Para resolver esto:

* Comunícate con X Ads para eliminar el otro proveedor de tu lado.
* Selecciona el nombre de la Cuenta Activa.
* Haz clic en **Guardar y Cerrar**.
* Si esto sigue sin resolver el problema, tendrás que ponerte en contacto con tu anterior proveedor de medición y pedirle que elimine las etiquetas anteriores de X Ads asociadas a tu cuenta.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="¿Cómo puedo configurar campañas de retargeting con Twitter?">

Para conocer detalles sobre cómo configurar una Campaña de Retargeting de Twitter, haz clic aquí.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="¿La función de retargeting afecta los eventos in-app que se envían a Twitter?">

Sí. Si está activada la función de retargeting, AppsFlyer no enviará lo postbacks del evento af\_app\_opened a Twitter, a pedido de Twitter.  
Ten en cuenta que si la ventana de configuración de Twitter permite esta selección, los postbacks de af\_app\_opened no se enviarán con la función de retargeting.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="¿Cómo puedo dejar de medir las atribuciones de X Ads?">

Para desactivar la integración con Twitter, desmarca todas las cuentas y haz clic en **Guardar y Cerrar**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="¿Una agencia puede medir las atribuciones de Twitter para anunciantes?">

Sí.  
Para establecer la conexión entre AppsFlyer y Twitter, el anunciante DEBE seleccionar una cuenta activa en la página de partners de Twitter en el panel de control del AppsFlyer, para que por lo menos haya una cuenta de Twitter marcada.  
Más adelante, la agencia necesitará conectar su cuenta de Twitter directamente desde su propio panel de control de agencia.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="¿Una Agencia Puede Configurar Eventos In-App para Twitter?">

Las agencias no pueden configurar eventos in-app para Twitter. Como ocurre con Anuncios de Meta, el anunciante debe configurar estos eventos.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="¿Cuánto tiempo conservan los datos de X Ads de nivel de usuario?">

Twitter exige que los proveedores de atribución eliminen sus datos a nivel de usuario 3 meses después de la instalación. Esto significa que los eventos efectuados por estos usuarios 3 meses después de que hayan instalado la aplicación se cuentan como orgánicos.

Los datos agregados anteriores permanecen iguales.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="¿Por qué veo datos de costos duplicados?">

Cuando se configura una campaña en Twitter, se pueden agregar varias aplicaciones a la campaña. Cuando Twitter reporta el costo, los datos del costo total de la campaña se muestran debajo de cada aplicación en AppsFlyer, y no se dividen por aplicación.

Por ejemplo, si realizas una campaña que cuesta USD 1000 para una aplicación de Android e iOS, entonces se muestra un costo de USD 1000 en el panel de control de AppsFlyer debajo las aplicaciones de Android e iOS. El costo no se divide, por ejemplo, en USD 500 cada uno.

Para evitar la duplicación de costos, se recomienda definir solo una aplicación por partida/campaña.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="Estoy intentando vincular mi cuenta de Twitter con AppsFlyer, pero recibo un mensaje de error">

Tu cuenta de Twitter tiene que ser una cuenta de anuncios activa para recibir los datos de atribución de AppsFlyer.

**Para resolver este problema:**

1. Cierra sesión en X Ads.
2. En AppsFlyer, desde el menú lateral, selecciona **Collaborate > Partner Integrations >** **Active Integrations.**
3. Busca X Ads y selecciónalo. Se abre la ventana de configuración del partner.
4. En la pestaña **Integración**, haz clic en **Activar partner**.
5. Haz clic en **Iniciar sesión con X Ads**,  
   se abre una ventana de inicio de sesión de X Ads.
6. Inicia sesión con tu cuenta de X Ads.

</Accordion>

## Discrepancias entre X Ads y AppsFlyer

Aunque trabajamos en estrecha colaboración con X Ads, podrían aparecer discrepancias entre el panel de control de X Ads y el panel de control y los reportes de AppsFlyer.

A continuación enumeraremos los motivos frecuentes de tales discrepancias que deben tener en cuenta los anunciantes:

| Causa | Anuncios X | fuentes de medios |
| --- | --- | --- |
| **Ventana de atribuciones** | X Ads permite que sus usuarios configuren la ventana de atribución y admite atribuciones por clics y por impresiones. De manera predeterminada, 14 días para las atribuciones por clics y 1 día para las atribuciones por impresiones. | Si no configuraste la ventana retrospectiva de atribución de AppsFlyer para X Ads con los mismos valores que figuran en X Ads, pueden surgir discrepancias. |
| **Atribución de fuentes multicanal** | La atribución en X Ads funciona tal como se especificó antes, independientemente de otras fuentes. | AppsFlyer usa la atribución de último clic (puedes encontrar más información sobre la atribución de AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">aquí</Anchor>). |
| **Diferencias en la zona horaria** | La zona horaria de X Ads está definida por la zona horaria configurada de la aplicación del anunciante. | La zona horaria predeterminada de AppsFlyer es UTC±00:00, pero el anunciante puede configurar cualquier zona horaria. |
| **Diferencias en la hora de instalación** | X Ads muestra las instalaciones en función de la hora del clic (lo que se conoce como "hora de engagement"). | AppsFlyer muestra la hora en que se abrió la aplicación por primera vez. |
| **Tipo de interacción de atribución** | La atribución de X Ads se basa en sus propios clics e impresiones. | AppsFlyer prioriza la atribución por clics por sobre la atribución por impresiones. Si X Ads cuenta una impresión y AppsFlyer detecta un clic adicional dentro de la ventana de atribución por clics, el clic de otra fuente se atribuye en el panel de control de AppsFlyer. En X Ads, se atribuye la impresión y se presenta en su panel de control. |
| **Configuración de X Ads para compartir datos** | X Ads permite que sus usuarios NO <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">compartan sus datos personales con terceros</Anchor>. Estos datos incluyen los anuncios con los que interactúan.<br /><br />Las estadísticas del panel de control de X Ads reflejan todos los engagements, incluidos los usuarios que han optado por no compartir los datos. | AppsFlyer muestra los datos agregados de estos usuarios de X Ads, pero no reporta su raw data a nivel de usuario (más <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-setup-guide-overview#privacidad-del-usuario-de-x-ads">detalles</Anchor>). |
| **Lógica de re-engagement de X Ads** | X Ads cuenta usuarios únicos. Si un usuario se vuelve a comprometer más de una vez como resultado de la misma campaña, X Ads muestra estos engagements como una conversión. | AppsFlyer cuenta cada instancia de re-engagement y, por lo tanto, en un caso similar, muestra estos engagements como varias conversiones. |

> 📘 **Nota**
>
> Como consecuencia de las <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">reglas de validación de AppsFlyer</Anchor>, los resultados pueden diferir en los paneles de control ya que algunas instalaciones se muestran en Twitter, pero no se muestran en el panel de control de AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=preguntas-frecuentes-y-discrepancias-sobre-twitter-ads h_01HE7S15F9YR28FBA1TYCE3N0X=preguntas-frecuentes-y-discrepancias-sobre-twitter-ads h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=nota h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=discrepancias-entre-x-ads-y-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=discrepancias-entre-x-ads-y-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=nota-1" />
