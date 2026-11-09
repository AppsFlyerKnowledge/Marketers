---
title: Configura AppsFlyer SSO en JumpCloud
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
  created_at: '2023-03-08T07:39:41Z'
  edited_at: '2026-08-12T12:03:53Z'
  id: 13563131567249
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/13563131567249
---
> **Resumen:** Configura el proceso de SSO con JumpCloud como proveedor de identidad (IdP).

La primera fase de la configuración del proceso de SSO de AppsFlyer se realiza en la plataforma de JumpCloud. Sigue los pasos que se indican a continuación:

<div id="create-the-appsflyer-app-in-jumpcloud" />

<Accordion title="Crea la aplicación de AppsFlyer en JumpCloud">

**Requisito previo:** una cuenta de JumpCloud con privilegios administrativos.

1. En el menú de administración de JumpCloud, ve a <Anchor target="_blank" href="https://console.jumpcloud.com/#/sso">SSO</Anchor> y haz clic en **+ Add New Application**.
2. Busca AppsFlyer en la lista de aplicaciones y haz clic en **configure**.
3. En **New SSO**, en la pestaña **General Info** , asigna un nombre a tu aplicación en el **Display label** campo.
4. [Opcional] Añade una descripción.
5. En la pestaña **SSO**:
   1. **Upload Metadata:** descarga los <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">metadatos de SSO de AppsFlyer</Anchor> como un archivo XML y, a continuación, súbelos aquí.
   2. **ACS URLs:** introduce la URL de devolución de llamada según el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">método para autenticar a tus usuarios</Anchor>.
   3. **Login URL:** introduce la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">URL de login</Anchor> de AppsFlyer.  

      <Image align="center" alt="jumpcloud_sso_tab2__1_.png" src="https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png" width="477px" />
6. Haz clic en **activate**.
7. Se crea un certificado público. Aparece una indicación en la parte superior derecha de la página. Haz clic en **Download Certificate**. Este certificado es necesario en el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">paso 2, en la plataforma de AppsFlyer</Anchor>.

</Accordion>

<div id="create-jumpcloud-users" />

<Accordion title="Crea usuarios en JumpCloud">

1. Ve a <Anchor target="_blank" href="https://console.jumpcloud.com/#/users">Users</Anchor> desde el menú de administración de JumpCloud y haz clic en el icono +.
2. Selecciona **Manual user entry**.  
   <Image align="center" alt="cloud_jump_manual_user_entry.png" src="https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png" width="417px" />
3. Introduce todos los campos obligatorios: **Username**, **Company Email**, y haz clic en **save user**.
4. Configura las opciones de contraseña del usuario según el método aceptado en tu empresa.
5. Para seguir añadiendo usuarios, haz clic en **Guardar y crear otro** y, a continuación, repite el paso 3. Cuando termines de añadir todos los usuarios, haz clic en **Guardar**.

</Accordion>

<div id="create-jumpcloud-groups" />

<Accordion title="Crea grupos de JumpCloud y asígnalos a la app de AppsFlyer">

Crea un grupo y asígnale usuarios:

1. En el menú de administración de JumpCloud, ve a <Anchor target="_blank" href="https://console.jumpcloud.com/#/groups/user">Grupos de usuarios</Anchor> y haz clic en el icono + .
2. Introduce el nombre del grupo.
3. En la pestaña **Usuarios**, selecciona los usuarios que quieres añadir a este grupo.
4. En la pestaña **Aplicaciones**, selecciona la aplicación de AppsFlyer que acabas de crear.
5. Haz clic en **Guardar**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obtén los metadatos de SSO del IdP">

1. En el menú de administración de JumpCloud, ve a **SSO**.
2. Selecciona la app de AppsFlyer que acabas de configurar y haz clic en **Copy Metadata URL** en la esquina superior derecha. Pegarás este enlace en el siguiente paso.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Completa el proceso en AppsFlyer">

Ahora que ya has configurado la parte del IdP, vuelve a AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">completar la configuración</Anchor>. Después puedes hacer una <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">prueba</Anchor> para comprobar que funciona.

</Accordion>

<div data-zendesk-anchors="h_01HF99ZFBKPYCP8228VKWPCRHX=create-the-appsflyer-app-in-jumpcloud h_01HF99ZFBKXD6HQE44FDQVQZWK=create-jumpcloud-users h_01HF99ZFBK0T9JQVFNTX705V9M=create-jumpcloud-groups h_01HF99ZFBKDFKTFXEE8Q0MH6SY=get-idp-sso-metadata h_01HF99ZFBK40ZTFKKJNXP4N294=complete-the-process-in-appsflyer" />
