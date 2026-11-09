---
title: Configurar SSO de AppsFlyer en OneLogin
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-05-04T07:41:06Z'
  edited_at: '2026-08-12T12:03:58Z'
  id: 15044997313041
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/15044997313041
---
> **De un vistazo:** configura el proceso de SSO con OneLogin como proveedor de identidad (IdP).

La primera fase de la configuración del proceso de SSO de AppsFlyer se realiza en la plataforma OneLogin. Sigue los pasos que se indican a continuación:

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="Crear la aplicación de AppsFlyer en OneLogin">

**Requisito previo:** una cuenta de OneLogin con privilegios administrativos.

1. En la consola de administración de OneLogin, ve a **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
2. En la parte superior derecha, haz clic en **Add App**.
3. Busca y selecciona **SAML Custom Connector (Advanced)**.  

   <Image align="center" alt="onelogin_saml_app.png" src="https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png" width="601px" />
4. En el campo **Display Name**, introduce el nombre que se mostrará en la lista de aplicaciones del plugin de OneLogin.
5. [Opcional] **App logo**: añade un logotipo para que aparezca junto al nombre de la aplicación.
6. [Opcional] Añade una descripción.
7. Haga clic en **Guardar**. Aparece un mensaje de confirmación en la parte superior.
8. Ve a la pestaña **Configuration** del menú lateral.
9. Define la integración según los siguientes campos:
   * **Audience (EntityID):** introduce este enlace: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **ACS (Consumer) URL Validation**, **ACS (Consumer) URL:** introduce el endpoint al que OneLogin envía la verificación del usuario. Usa el enlace según la <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">configuración de la URL de callback descrita aquí</Anchor>
   * **Recipient:** introduce la misma URL que has introducido en el campo **ACS (Consumer) URL** .
   * **Login URL:** introduce la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">URL de login</Anchor> de AppsFlyer.
   * **SAML not valid before**, **SAML not valid on or after:** especifica el periodo de tiempo (en minutos) durante el que la aserción es válida.
   * **SAML initiator:** <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">Selecciona desde dónde empieza la autenticación</Anchor>:
     * Si la autenticación empieza desde el IdP, selecciona **OneLogin**
     * Si la autenticación empieza desde AppsFlyer, selecciona **Service Provider**
   * **SAML nameID format:** selecciona Correo electrónico.
   * **Tipo de emisor SAML:** Selecciona Específico.
   * **Elemento de firma SAML:** Selecciona **Ambos**.
   * **Cifrar aserción**: marca esta casilla.
   * **Método de cifrado SAML:** Selecciona **AES-256-CBC**.
10. Haga clic en **Guardar**.
11. **Cifrado de aserción:** 
    1. Abre <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">la URL de metadatos de SSO</Anchor> y copia el valor del certificado de cifrado.
    2. Vuelve a la pestaña **Configuration** y pégalo en el cuadro de texto **SAML encryption**.
    3. Haga clic en **Guardar**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obtener metadatos SSO del IdP">

1. En la aplicación seleccionada (**Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**), selecciona **SSO** en el menú lateral.
2. Copia la **URL del emisor** y pégala en una pestaña nueva para descargar los metadatos de SSO.

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="Crear usuarios de OneLogin">

1. En el menú superior, ve a **Users** > <Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/users">**Users**</Anchor>.
2. Haz clic en **New User** en la parte superior derecha.
3. Introduce el **First name**, el **Last name** y el **Email** del usuario.
4. En la parte superior derecha, haz clic en **Save User**, luego en **More Actions**, y selecciona **Change Password** para establecer una contraseña para el usuario.
5. Establece una contraseña para el usuario y haz clic en **Update**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Asignar usuarios a tu aplicación">

1. Ve a la pestaña **Application** en el menú lateral del usuario seleccionado.
2. Haz clic en el signo + junto a **Applications**.
3. Selecciona la aplicación de AppsFlyer que has creado y haz clic en **Continue**.  

   <Image align="center" alt="onelogin_assign_app.png" src="https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png" width="326px" />
4. En el menú superior, ve a **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
5. Selecciona la aplicación que acabas de crear.
6. Haga clic en **Guardar**.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Completa el proceso en AppsFlyer">

Ahora que ya has configurado la parte del IdP, vuelve a AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">completar la configuración</Anchor>. Después, puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">probar</Anchor> para comprobar que funciona.

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />
