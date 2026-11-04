---
title: Transferencia de aplicaciones entre cuentas
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-09-24T00:07:50Z'
  id: 360001336005
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/360001336005
---
> **At a glance:** Transfiere aplicaciones entre cuentas de AppsFlyer siguiendo los pasos descritos en este artículo (para administradores de las cuentas del remitente y del receptor).

![Animación del proceso de transferencia de apps que muestra los pasos del asistente de transferencia](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

<div id="app-transfer-between-accounts" />

## Transferencia de aplicaciones entre cuentas

Para transferir una aplicación entre cuentas de AppsFlyer, tanto los propietarios de aplicaciones que envían como los que reciben (representados por los administradores de sus cuentas de AppsFlyer) deben completar los requisitos previos de transferencia necesarios y aceptar la transferencia.

<div id="prerequisites" />

### Requisitos previos

* Asegúrate de tener los correos electrónicos tanto del remitente como de la cuenta del destinatario (admin).
* Ambas cuentas están activas. Las cuentas suspendidas no pueden enviar ni recibir aplicaciones.
* Ninguna cuenta tiene facturas sin pagar.
* La transferencia de aplicaciones entre cuentas solo puede realizarla el <Anchor target="_blank" href="/marketers/es/docs/user-management#propietario-de-la-cuenta">propietario de la cuenta</Anchor>. No puede realizarlo un rol de administrador.
* La transferencia de la app debe hacerse a una cuenta con un plan de Growth o Enterprise. <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">Más información</Anchor>

<div id="app-transfer-process" />

### Proceso de transferencia de aplicaciones

A continuación se muestra un resumen del proceso de transferencia de aplicaciones:

1. El remitente solicita que AppsFlyer transfiera las aplicaciones seleccionadas e introduce la dirección de correo electrónico del administrador destinatario.
2. El receptor es notificado y acepta recibir las aplicaciones.
3. Tanto los administradores del remitente como los del destinatario reciben un aviso de la transferencia pendiente (por correo electrónico y en la página **Mis aplicaciones** ).   
   **Nota:** Mientras la transferencia está pendiente, cualquiera de los administradores puede eliminar la solicitud de transferencia de la aplicación (cancelar la transferencia).
4. AppsFlyer transfiere las aplicaciones. Si un requisito previo está incompleto, AppsFlyer se comunica con la parte correspondiente para asegurarse de que se complete.

<Accordion title="Alcance de la transferencia de aplicaciones">

En la siguiente tabla se detalla qué funciones y configuración de la aplicación se transfieren. Ten en cuenta que el remitente puede, a su discreción, eliminar ciertas funciones e información de configuración antes de la transferencia.

<table><thead><tr><th>Elemento</th><th>Transferido/<br/>no transferido</th><th>Detalles/consideraciones discrecionales</th></tr></thead><tbody><tr><td>Configuración App </td><td>Transferido</td><td> <strong>Discreción:</strong> el remitente puede eliminar la clave de servidor de Firebase/GCM antes de la transferencia. </td></tr><tr><td rowspan="2">Socios integrados</td><td>Transferido</td><td><p>Configuraciones de integración, costos e ingresos (incluyendo datos de costos e ingresos)</p><p><strong>Discreción:</strong> si el destinatario no necesita que se transfieran los partners integrados, el remitente debe desactivarlos y eliminar sus configuraciones y credenciales (incluidas las configuraciones de costo e ingresos por anuncios).</p></td></tr><tr><td>No transferido</td><td><p>Permisos de red de publicidad y agencia</p><p>Configuraciones y credenciales de Twitter</p></td></tr><tr><td>Gestión de enlaces</td><td>No transferido</td><td><p>Las plantillas y los enlaces de OneLink no se transfieren automáticamente, pero pueden ser transferidos por tu CSM. </p><p><strong>Para transferir plantillas y enlaces:</strong> ponte en contacto con tu CSM o envía un mensaje a <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>. <br/><strong>Nota:</strong> Los enlaces masivos se transfieren automáticamente junto con la plantilla.</p><ul><li>El remitente puede eliminar enlaces obsoletos antes de la transferencia.</li><li>Los tokens de la API de OneLink no se pueden transferir entre cuentas. Tendrás que usar un <a href="./managing-appsflyer-tokens" target="_blank">token</a> de tu nueva cuenta.</li></ul><p>La lista de permitidos de redirección de dominios tampoco se transfiere automáticamente. Si la lista de permitidos de la cuenta de destino no incluye ya los dominios de la app transferida, los enlaces que usen esos dominios dejarán de funcionar después de la transferencia. Asegúrate de <a href="./set-up-your-domain-redirect-allowlist" target="_blank">configurar la lista de permitidos de redirección de dominios</a> en la cuenta de destino antes de la transferencia o inmediatamente después.</p></td></tr><tr><td>API push</td><td>Transferido</td><td><p><strong>Discreción:</strong></p><ul><li>Si el destinatario no necesita que se transfieran las configuraciones de Push API (puntos de conexión), el remitente debe eliminar la configuración. De lo contrario, los datos seguirán enviándose a los puntos de conexión definidos por el remitente.</li><li>Alternativamente, el receptor puede cambiar la configuración en la recepción para asegurarse de que el remitente no reciba datos a nivel de usuario. </li></ul></td></tr><tr><td>Banners inteligentes</td><td>No transferido</td><td>Los banners, los grupos de banners, las creatividades y los sitios web no se transfieren. </td></tr><tr><td>Script inteligente</td><td>No transferido</td><td>Los Smart Scripts creados dentro de la interfaz de usuario de AppsFlyer no estarán disponibles en la nueva cuenta. </td></tr><tr><td>Agencias</td><td>No transferido</td><td>Las agencias pierden el acceso a la aplicación.</td></tr><tr><td>Audiencias</td><td>No transferido</td><td>Las audiencias se eliminan.</td></tr><tr><td>Importación de costos</td><td>N/D</td><td>El receptor no puede acceder a los archivos de importación de costos históricos. Esto no afecta al historial de costos. </td></tr><tr><td>Casillero de datos</td><td>No transferido</td><td>La aplicación se quita de la configuración de Data Locker y la cuenta del remitente deja de recibir datos de la aplicación. </td></tr><tr><td>Historial de datos</td><td>Transferido</td><td> </td></tr><tr><td>Paquetes de marca de PBA</td><td>No transferido</td><td><p>El paquete deja de estar disponible para el remitente si se transfiere cualquiera de sus aplicaciones relacionadas. El destinatario no puede acceder a los datos de la PBA.</p><p>Esto significa que si el cliente necesita seguir usando PBA en su nueva cuenta, debe eliminar su paquete web antes de que se complete la transferencia de la aplicación, de lo contrario, no podrá crear el mismo paquete web en su nueva cuenta.</p></td></tr><tr><td>Datos de Protect 360</td><td>Transferido</td><td><p>Si una aplicación se transfiere de una cuenta sin un recurso de Protect360 a otra que sí lo tiene: </p><ul><li>La detección de fraude empieza solo cuando se completa la transferencia.</li><li>Si la cuenta de destino tiene el recurso solo durante una parte del tiempo, los datos de fraude solo estarán disponibles a partir de la fecha de inicio del recurso, y no de forma retroactiva.</li><li>No se realiza ninguna detección de fraude durante el proceso de transferencia.</li></ul></td></tr><tr><td>Raw data y datos agregados</td><td>Transferido</td><td> </td></tr><tr><td>Clave de desarrollador de SDK</td><td>Transferido</td><td> </td></tr><tr><td>Reglas de validación</td><td>Transferido</td><td> </td></tr></tbody></table>

</Accordion>

<div id="transfer-procedures" />

## Procedimientos de transferencia

Para solicitar la transferencia de una o más aplicaciones a otra cuenta de AppsFlyer, inicia el proceso y el asistente te guiará en la interfaz de usuario.

<Accordion title="Remitente">

**Para enviar una solicitud de transferencia**:

1. Ponte en contacto con el administrador remitente:
   1. Revisa y acuerda el [alcance de la transferencia de aplicaciones](/docs/transferring-apps-between-accounts#app-transfer-scope). Asegúrate de que ambos entiendan lo que se transfiere y lo que no se transfiere y que ambos estén debidamente preparados.
   2. Solicita que el destinatario te proporcione la dirección de correo electrónico de administrador que utiliza en AppsFlyer.
2. Realiza una de las siguientes acciones:
   * Para transferir una aplicación: En la barra de menú superior > **Mis aplicaciones** > Abre el menú de acciones de la aplicación (...) > Selecciona **Transferir aplicación**.
   * Para transferir 2 o más aplicaciones: En la barra de menú superior > **Mis aplicaciones** > Abre el menú de acciones de la aplicación (...) > Selecciona **Transferir aplicación**.
3. Elige la aplicación o aplicaciones que deseas transferir.
4. Haz clic en **Siguiente**.
5. Ingresa la dirección de correo electrónico del administrador destinatario.
6. Haz clic en **Siguiente**.
7. Lee y firma los términos y condiciones.
   * Tú y el destinatario reciben una notificación (por correo electrónico) de que la solicitud se ha enviado correctamente.
   * Se te notificará (mediante un pop-up) si la solicitud requiere ser manejada por AppsFlyer.
   * Las apps aparecen en tu página **Mis aplicaciones** como pendientes de transferencia a `<receiver email>`. En esta etapa, todavía es posible eliminar la solicitud.

     ![Página Mis aplicaciones del remitente que muestra una aplicación incluida como transferencia pendiente, con una opción para eliminar la solicitud](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<Accordion title="Destinatario">

1. Ponte en contacto con el administrador remitente para revisar y acordar el [alcance de la transferencia de aplicaciones](/docs/transferring-apps-between-accounts#app-transfer-scope). Asegúrate de que ambos entiendan lo que se transfiere y lo que no se transfiere y que ambos estén debidamente preparados.
2. Recibirás una notificación por correo electrónico de que el remitente ha iniciado la solicitud de transferencia.
3. En la página **Mis aplicaciones**, haz clic en **Revisar solicitud**. Una solicitud puede incluir una o varias aplicaciones.

   ![Página Mis aplicaciones del destinatario que muestra una solicitud de transferencia de aplicación pendiente con una opción para revisar la solicitud](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. Revisa y aprueba o rechaza cada solicitud.
5. Lee y, si son aceptables, firma los términos y condiciones.
6. Tú y el remitente reciben una notificación por correo electrónico de que se ha aceptado la solicitud.
7. Las aplicaciones transferidas aparecen en **Mis aplicaciones** .

</Accordion>

<Accordion title="Eliminar la solicitud de transferencia">

Antes de que finalice la transferencia, el administrador del remitente o del receptor puede eliminar (cancelar) un proceso de transferencia de aplicaciones.

**Para eliminar una solicitud de transferencia de aplicaciones:**

* **Administrador remitente**: en la barra de menú superior > **Mis aplicaciones** > sección **Transferencia pendiente a [correo electrónico]** > haz clic **Eliminar solicitud**.   
  Se notifica tanto al administrador remitente como al destinatario (correo electrónico).
* **Administrador del receptor**:
* En la barra de menú superior > **Mis aplicaciones** > **Aplicaciones pendientes de transferencia** sección > haz clic **Rechazar**.   
  Se notifica tanto al administrador remitente como al destinatario (correo electrónico).

</Accordion>

<div data-zendesk-anchors="app-transfer-between-accounts=transferencia-de-aplicaciones-entre-cuentas h_01HJR1G7Q71H5DAH1G9QFSYK35=transferencia-de-aplicaciones-entre-cuentas prerequisites=requisitos-previos h_01HJR1G7Q7T1Q768MTTR3Y542X=requisitos-previos app-transfer-process=proceso-de-transferencia-de-aplicaciones h_01HJR1G7Q7EDJZ4E1T17GWYGTP=proceso-de-transferencia-de-aplicaciones transfer-procedures=procedimientos-de-transferencia h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=procedimientos-de-transferencia" />
