---
title: Configura el SSO de AppsFlyer en Okta
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
  created_at: '2023-02-12T13:10:51Z'
  edited_at: '2026-08-12T12:03:56Z'
  id: 12934808889745
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/12934808889745
---
> **De un vistazo:** Configura el proceso de SSO usando Okta como proveedor de identidad (IdP).

El primer paso para configurar el proceso de SSO de AppsFlyer se realiza en la plataforma de Okta. Sigue los pasos que se indican a continuación:

<div id="create-the-appsflyer-app-in-okta" />

<Accordion title="Crea la app de AppsFlyer en Okta">

**Requisito previo:** Una cuenta de Okta con privilegios de administrador.

1. En la consola de administración, ve a **Applications** > **Applications**.  
   <Image alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="241px" />
2. Haz clic en **Create App Integration**.
3. En el cuadro de diálogo **Create a new app integration**, selecciona **SAML 2.0** y haz clic en **Next**.
4. En **(1) General Settings**, en el campo **App name**, introduce el nombre que quieres que se muestre en la lista de apps del complemento de Okta.  
   <Image alt="Okta_app_name_and_icon__1_.png" src="https://files.readme.io/6998e7737b0aa5c4d70ad97ab41e17e471ddaf060e78c44fa2de41be1df17574-13572380565521.png" width="639px" />
5. [Opcional] **App logo**: añade un logotipo para que aparezca junto al nombre de la aplicación.
6. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.
7. En **(2) Configure SAML Integration**, define la integración según los siguientes campos: ![okta-create-saml-integration.png](https://files.readme.io/6c276dd54afd30e828b989fc6796de5eca46282ade015e7a34e0bd1cc95d7fb8-16870970396177.png)
   * **Single sign-on URL:** Introduce el endpoint al que Okta envía la verificación del usuario. Usa el enlace según la <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">configuración de la URL de devolución de llamada descrita aquí</Anchor>
   * **Audience URI (SP Entity ID):** Introduce este enlace: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **Name ID format:** Selecciona **EmailAddress** como formato para identificar al usuario
   * **Application username:** Selecciona **Okta username**  
     **Nota:** El correo electrónico del usuario de Okta debe ser el mismo que el correo electrónico de la cuenta de AppsFlyer del usuario
8. Haz clic en **Show Advanced Settings** y define la integración según cada uno de los campos que se muestran en la imagen siguiente:

   <Image alt="Okta_advanecd_settings__1_.png" src="https://files.readme.io/9a3461f700cc50a54237578a304206ed7693e30cdd516398089954321cd44af4-13572576788241.png" width="640px" />

   * **Assertion Encryption:** Selecciona **Encrypted** o **Unencrypted**.   
     **Nota:** Como las aserciones las controla tu IdP, se recomienda seleccionar **Encrypted**.
   * **Encryption certificate:** Carga el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">certificado de cifrado de AppsFlyer</Anchor>. AppsFlyer firma este certificado y se usa tanto para cifrar como para firmar la solicitud.
   * [Opcional] **Signature certificate:** Carga el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate">certificado de firma de AppsFlyer</Anchor>.
9. Desplázate hasta el final de la página y haz clic en **Siguiente**.
10. Selecciona **I’m an Okta customer adding an internal app** y haz clic en **Finalizar**.

</Accordion>

<div id="create-okta-users" />

<Accordion title="Crear usuarios de Okta">

Ahora que se ha creado la aplicación SAML de Okta, vamos a añadir usuarios.

1. En la consola de administración, selecciona **Directory** > **People**.

   <Image alt="Okta___directory___people.png" src="https://files.readme.io/d9c5da8787fdb81bf97bc0753b2f7794cdc59060e5026348428545064d138d18-13572579297169.png" width="226px" />
2. Haz clic en **Agregar persona**.

   <Image alt="Okta___People___Add_person.png" src="https://files.readme.io/6bb8b854cf000259970d63b9eacb28bf6d4079d648939814aaa0e456a96c9bbe-13572600647697.png" width="524px" />
3. En el cuadro de diálogo **Agregar persona**:

   <Image alt="Okta_Add_person__1_.png" src="https://files.readme.io/d6d7e198fab965872b5a01302a00bdbd0bfb5d561af372fc4390c9882a22a42c-13572617052689.png" width="620px" />

   * En **Tipo de usuario**, selecciona **Usuario**.
   * Introduce todos los campos obligatorios: **Nombre**, **Apellidos**, **Nombre de usuario** (debe ser un correo electrónico) y **Correo electrónico principal**.
   * En **Password**, puedes elegir si la establece el usuario o el administrador.
4. Para seguir añadiendo usuarios, haz clic en **Save and Add Another** y, a continuación, repite los pasos 1-4. Cuando termines de añadir todos los usuarios, haz clic en **Save**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Asignar usuarios a tu aplicación">

1. En la consola de administración, vuelve a **Applications** > **Applications**.
2. En **Browse App Catalog**, selecciona la aplicación que acabas de crear.  
   <Image alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="233px" />
3. En la aplicación que has seleccionado, en la pestaña **Assignments**, haz clic en **Assign** > **Assign to People**.  
   ![Okta_sso_assign_to_people.png](https://files.readme.io/50930693a4a58ad8162b2ac81e476081c9b0288da4dab5b92bb41fece4aff586-14942267242769.png)
4. Busca el usuario que quieras asignar a tu aplicación y haz clic en **Assign**.
5. Repite este paso con todos los usuarios.
6. Haz clic en **Done** cuando termines de añadir todos los usuarios. Los nuevos usuarios ahora aparecen en **People**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obtener metadatos de SSO del IdP">

1. En la consola de administración, vuelve a **Applications** > **Applications**.
2. En **Browse App Catalog**, selecciona tu aplicación.
3. Haz clic en la pestaña **Sign On**.
4. En la sección **SAML Signing Certificates** , haz clic en **Actions** > **View IdP metadata** del certificado activo. <Image alt="okta_sso_view_idp_metadata.png" src="https://files.readme.io/a6d9f6753ead962713851bcc367abba6fad226d6e0a5f908055e44b1d3e1b2be-14942369009809.png" width="601px" />
5. Copia la URL de la pestaña que se abrió. Usarás esta URL en el siguiente paso en la plataforma AppsFlyer.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Completa el proceso en AppsFlyer">

Ahora que ya has configurado la parte del IdP, vuelve a AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">completar la configuración</Anchor>. A continuación, puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">probarlo</Anchor> para comprobar que funciona.

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="https://developer.okta.com/docs/guides/build-sso-integration/openidconnect/main/">Documentación de SSO de Okta</Anchor>

<div data-zendesk-anchors="h_01HDNZYDQGGBMB9MJ97RF4BADM=create-the-appsflyer-app-in-okta h_01HDNZYDQGGFCA2KB9PDQY1ZTG=create-okta-users h_01HDNZYDQGC9MRQH92MM8W4FVE=assign-users-to-your-app h_01HDNZYDQGWRE9K6XG5EPYTYYX=get-idp-sso-metadata h_01HDNZYDQG6GNEP3TQMXVT5FTG=complete-the-process-in-appsflyer h_01HDP00WTAVP0X8FT51JC1JKKC=v%C3%A9ase-tambi%C3%A9n" />
