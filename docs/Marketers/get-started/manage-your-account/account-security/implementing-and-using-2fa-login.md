---
title: Implementando y usando el inicio de sesión 2FA
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-08-12T12:04:26Z'
  id: 360010178037
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/360010178037
---
> **En resumen:** Utiliza la autenticación de dos factores (2FA) para agregar una capa adicional de seguridad al proceso de inicio de sesión. Las credenciales de inicio de sesión para los usuarios de la cuenta se complementan con Google Authenticator o verificación por SMS.

## Aspectos destacados

* 2FA es una función opcional activada por un usuario administrador.
* Las opciones son **Google Authenticator** y **verificación por SMS**.
* La activación/desactivación se aplica a todos los usuarios de la cuenta.
* Los usuarios de la cuenta en el momento de la activación podrán iniciar sesión y se les pedirá que configuren el 2FA en su próximo inicio de sesión.

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) Administrador: Gestionando 2FA

Solo un usuario administrador puede activar, restablecer o desactivar la configuración de 2FA de un usuario.

<div id="activate" />

<Accordion title="Activar">

Si un administrador activa **Google Authenticator** y **verificación por SMS**, los usuarios de la cuenta pueden elegir qué método prefieren usar.

> 📘 **Nota:**
>
> La verificación por SMS depende de las tasas de éxito de SMS, que varían según el operador móvil y el país. Por lo tanto, recomendamos encarecidamente habilitar tanto la verificación por SMS como Google Authenticator para evitar quedar bloqueado debido a la entrega fallida de SMS.

**Para activar 2FA:**

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección **Seguridad de inicio de sesión mejorada**, haz clic en **Configurar método de inicio de sesión** para acceder a la página **Seguridad de inicio de sesión**.
3. En la sección **Autenticación de dos factores (2FA)**, activa el interruptor para **Google Authenticator** y/o **verificación por SMS.**

</Accordion>

<div id="reset" />

<Accordion title="Restablecer">

En el caso de las cuentas que utilizan 2FA, puede haber ocasiones en las que necesites restablecer la autenticación de dos factores de un usuario. Ten en cuenta que después del restablecimiento, **Google Authenticator** es la pantalla de inicio de sesión 2FA predeterminada.

**Para restablecer el 2FA de un usuario:**

1. En la barra de menú, haz clic en el menú desplegable de direcciones de correo electrónico.
2. Selecciona **Administración de usuarios**.
3. En la pestaña **Usuarios**, haz clic en el botón Acciones <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> en el extremo derecho de la fila del usuario.
4. Selecciona **Restablecer 2FA** en el menú.

**Nota:** Un administrador puede restablecer el 2FA de cualquier otro administrador que no sea la suya o la del <Anchor target="_blank" href="/marketers/es/docs/user-management#administrador">propietario de la cuenta</Anchor>. Para restablecer la autenticación de dos factores del propietario de la cuenta, contacta con el equipo de soporte de AppsFlyer.

</Accordion>

<div id="deactivate" />

<Accordion title="Desactivar">

Si 2FA está desactivado, los usuarios de la cuenta iniciarán sesión utilizando solo su nombre de usuario y contraseña.

**Para desactivar 2FA:**

1. Desde la barra superior, abra el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección **Seguridad de inicio de sesión mejorada**, haz clic en **Configurar método de inicio de sesión** para acceder a la página **Seguridad de inicio de sesión**.
3. En la sección **Autenticación de dos factores (2FA)**, desactiva el interruptor para **Google Authenticator** y/o **verificación por SMS.**
4. Confirma la desactivación.

</Accordion>

## Usuarios de la cuenta: Usando Google Authenticator

**Google Authenticator** es la pantalla inicial predeterminada; sin embargo, el último método 2FA utilizado aparece en el siguiente inicio de sesión.

Si decides no usar **Google Authenticator**, entonces las pantallas de configuración e inicio de sesión tienen un enlace a la pantalla de 2FA de **verificación por SMS**.

<div id="firsttime-setup" />

<Accordion title="Configuración inicial">

Antes de usar 2FA por primera vez, cada usuario de la cuenta debe descargar **Google Authenticator** y una aplicación de **QR code**. Estas aplicaciones están disponibles a través de **Google Play** (Android) o la **App Store** (iOS).

**Nuevo usuario de cuenta**

1. Sigue las instrucciones del correo electrónico y crea una contraseña.
2. Inicia sesión en **AppsFlyer,** y serás redireccionado a la página de configuración de 2FA.
3. Configura 2FA.
   * Descarga **Google Authenticator** y una aplicación de **QR code**.
   * Escanea el QR code.
   * Ingresa el código de verificación emitido por **Google Authenticator**.
   * Haz clic en **Verificar**, y serás redireccionado a la página de **Mis aplicaciones**.

**Usuarios de cuentas existentes**

1. Inicia sesión en **AppsFlyer** (nombre de usuario y contraseña), y serás redireccionado a la página de configuración de 2FA.
2. Configura 2FA.
   * Descarga **Google Authenticator** y una aplicación de **QR code**.
   * Escanea el QR code.
   * Ingresa el código de verificación emitido por **Google Authenticator**.
   * Haz clic en **Verificar**, y serás redireccionado a la página de **Mis aplicaciones**.

</Accordion>

<div id="ongoing-use" />

<Accordion title="Uso continuo">

**Sigue estos pasos para el uso continuo.**

1. Inicia sesión en **AppsFlyer** (nombre de usuario y contraseña), y serás redireccionado a la página de inicio de sesión de 2FA.
2. Abre **Google Authenticator** en tu móvil para obtener el código de verificación.
3. Ingresa el código en la página de 2FA.
4. Haz clic en **Verificar**, y serás redireccionado a la página de **Mis aplicaciones**.

</Accordion>

## Usuarios de la cuenta: Usando la verificación por SMS

Si eliges no usar la **verificación por SMS**, entonces las pantallas de configuración e inicio de sesión tienen un enlace a la pantalla de 2FA de **Google Authenticator**.

<div id="firsttime-sms-setup" />

<Accordion title="Configuración de SMS por primera vez">

**Google Authenticator** es el método de 2FA predeterminado. Para acceder al método de **verificación por SMS**, haz clic en el enlace de **verificación por SMS**.

**Nuevo usuario de cuenta**

1. Sigue las instrucciones del correo electrónico y crea una contraseña.
2. Inicia sesión en **AppsFlyer,** y serás redireccionado a la página de configuración de 2FA.
3. Configurar 2FA:
   * Ingresa tu número de teléfono (solo números, sin caracteres especiales) y haz clic en **Enviar código**.
   * Ingresa el código de verificación por SMS > haz clic en **Verificar**. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

**Usuarios de cuentas existentes**

1. Inicia sesión en **AppsFlyer** (nombre de usuario y contraseña), y serás redireccionado a la página de configuración de 2FA.
2. Configurar 2FA:
   * Ingresa tu número de teléfono (solo números, sin caracteres especiales) y haz clic en **Enviar código**.
   * Ingresa el código de verificación por SMS > haz clic en **Verificar**.

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="Uso continuo de SMS">

**Sigue estos pasos para el uso continuo:**

1. Inicia sesión en **AppsFlyer** (nombre de usuario y contraseña), y serás redireccionado a la página de inicio de sesión de 2FA.
2. La página de **verificación por SMS** aparecerá si se utilizó en su último inicio de sesión. Si no, haz clic en el enlace en la parte inferior de la página de 2FA de **Google Authenticator**.
3. Tu número de teléfono se mostrará automáticamente. Haz clic en **Enviar código**.
4. Ingresa el código de verificación enviado por SMS.
5. Haz clic en **Verificar**.

</Accordion>

<div data-zendesk-anchors="highlights=aspectos-destacados h_01HEHRKE8PY64KWVSSFR6T4F1Z=aspectos-destacados admin-managing-2fa=-administrador-gestionando-2fa h_01HEHRKE8PZA3H9SXPRD1FZ50S=-administrador-gestionando-2fa h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=nota h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=usuarios-de-la-cuenta-usando-google-authenticator h_01HEHRKE8P1A2BARBDVMJPH1WY=usuarios-de-la-cuenta-usando-google-authenticator h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use account-users-using-sms-verification=usuarios-de-la-cuenta-usando-la-verificaci%C3%B3n-por-sms h_01HEHRKE8QZ245ZYBZ4FF814KN=usuarios-de-la-cuenta-usando-la-verificaci%C3%B3n-por-sms h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />
