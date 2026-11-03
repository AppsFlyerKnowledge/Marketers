---
title: Inicio de sesión en la cuenta y restablecimiento de contraseña
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-03-03T09:04:23Z'
  edited_at: '2026-08-12T12:03:36Z'
  id: 33114514624273
  locale: es
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/es/articles/33114514624273
---
> **Resumen:** Inicia sesión en AppsFlyer, añade varias cuentas y restablece las contraseñas de los usuarios.

## Instrucciones de inicio de sesión

Instrucciones de inicio de sesión para usuarios nuevos y existentes. Esto incluye la creación de una cuenta nueva, la invitación a un usuario nuevo o cómo iniciar sesión como usuario existente.

**Nota**: Para ver instrucciones sobre cómo crear un usuario, consulta <Anchor target="_blank" href="/marketers/es/docs/user-management#creating-users">aquí</Anchor>.


<div id="logging-in-for-the-first-time" />

<Accordion title="Iniciar sesión por primera vez">

Tanto si acabas de registrarte como si te acaban de invitar a AppsFlyer, recibirás un correo electrónico con un enlace de activación.

Para iniciar sesión en AppsFlyer:

1. Abre el correo electrónico de activación de AppsFlyer
2. **Para el primer usuario de una cuenta**:
   1. Haz clic en el enlace de activación del cuerpo del correo electrónico  
      **Nota**: El usuario que se crea al abrir la cuenta es el «propietario de la cuenta» y se le asigna de forma predeterminada el <Anchor target="_blank" href="/marketers/es/docs/user-management#propietario-de-la-cuenta">rol de administrador.</Anchor>
3. **Para los usuarios que usan una invitación**:
   1. Copia el código de verificación del cuerpo del correo electrónico
   2. Haz clic en el botón **página de login de AppsFlyer** del cuerpo del correo electrónico
   3. Introduce tu código  
      **Nota:**  Los códigos de verificación son válidos durante 15 minutos. Si el código de verificación caduca, haz clic en **Resend Code** para recibir uno nuevo
4. Crear contraseña

</Accordion>

<div id="existing-users" />

<Accordion title="Usuarios existentes">

Los usuarios existentes pueden iniciar sesión en AppsFlyer desde la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">página principal de login</Anchor>.

Puedes iniciar sesión en AppsFlyer con lo siguiente:

* Credenciales (nombre de usuario y contraseña)
* Login de Google
* <Anchor target="_blank" href="/marketers/es/docs/sso-authentication">Inicio de sesión único</Anchor>

**Nota**: Si tu administrador configuró una <Anchor target="_blank" href="/marketers/es/docs/implementing-and-using-2fa-login">autenticación de dos factores (2FA)</Anchor> para tu cuenta, se te pedirá que verifiques el login mediante otro método de autenticación.

</Accordion>

<div id="twofactor-authentication-2fa" />

<Accordion title="Autenticación de dos factores (2FA)">

Si la 2FA está habilitada en la configuración de gestión de seguridad, se activará después de tu login inicial.

[Para restablecer el 2FA de un usuario, consulta este enlace](/docs/account-login-and-password-reset#resetting-twofactor-authentication-2fa).

</Accordion>

## Restablecimiento de contraseña, login o 2FA

Restablecimiento de contraseña para usuarios existentes y usuarios que no completaron el proceso inicial de registro o invitación.

<div id="existing-users-and-invited-users-who-have-not-activated-yet" />

<Accordion title="Usuarios existentes y usuarios invitados que todavía no se han activado">

Para restablecer tu contraseña:

1. En la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">página principal de login</Anchor> de AppsFlyer, haz clic en **¿Has olvidado la contraseña?**
2. Se enviará un código de verificación de un solo uso a tu correo electrónico
3. Copia el código de verificación del cuerpo del correo electrónico
4. Haz clic en el botón **AppsFlyer login page** del cuerpo del correo electrónico
5. Introduce tu código  
   **Nota:**  Los códigos de verificación son válidos durante 15 minutos  
   Si el código de verificación caduca, haz clic en **Resend Code** para recibir uno nuevo
6. Crea una nueva contraseña

</Accordion>

<div id="users-who-have-not-completed-the-initial-registration" />

<Accordion title="Usuarios que no han completado el registro inicial">

Al registrarte en AppsFlyer, se te envió una invitación por correo electrónico. El enlace de activación del correo electrónico es válido durante 7 días. Para completar el registro, haz lo siguiente:

1. Abre el correo electrónico
2. Haz clic en el botón de activación **AppsFlyer sign up page** del cuerpo del correo electrónico  
   **Nota**: El usuario creado cuando se abrió la cuenta, el «propietario de la cuenta», tiene asignado de forma predeterminada el <Anchor target="_blank" href="/marketers/es/docs/user-management#propietario-de-la-cuenta">rol de administrador.</Anchor>
   1. Si el enlace ha caducado, completa el registro  desde el principio
3. Crea una contraseña

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Restablecer la autenticación de dos factores (2FA) de un usuario">

Si tu cuenta usa 2FA, puede haber ocasiones en las que necesites restablecer la configuración 2FA de un usuario. Hazlo de la siguiente manera:

1. En la pestaña **Usuarios**, haz clic en el botón **Acciones** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> en el extremo derecho de la fila del usuario.
2. Selecciona **Restablecer 2FA** en el menú.

**Nota:** Un administrador puede restablecer el 2FA de cualquier otro usuario, excepto el suyo propio. Para restablecer el 2FA del propietario de la cuenta, contacta con el equipo de soporte de AppsFlyer.

</Accordion>

<div data-zendesk-anchors="log-in-instructions=instrucciones-de-inicio-de-sesi%C3%B3n h_01JNDM4M03F0T16ZHY2V1BSRQH=instrucciones-de-inicio-de-sesi%C3%B3n h_01JNDJFMRHCS20TABKNSHQ2MMW=logging-in-for-the-first-time h_01JNDM9HN8K396432TQ5MEVYCZ=existing-users h_01JNDS7ZT2TMX5315587CHBDY5=twofactor-authentication-2fa password-login-or-2fa-reset=restablecimiento-de-contrase%C3%B1a-login-o-2fa h_01JNDSMFB1YAWA340BAEYFXRES=restablecimiento-de-contrase%C3%B1a-login-o-2fa h_01JNDSJPQ4GNV0PD16GE7G9FY6=existing-users-and-invited-users-who-have-not-activated-yet h_01JNDTHN2B6VCH38ER68D3RNFS=users-who-have-not-completed-the-initial-registration h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
