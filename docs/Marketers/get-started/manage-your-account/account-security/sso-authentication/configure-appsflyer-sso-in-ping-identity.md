---
title: Configura el SSO de AppsFlyer en Ping Identity
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - security
    - Marketers
    - authentication
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
  created_at: '2023-06-11T09:28:10Z'
  edited_at: '2026-08-12T12:04:01Z'
  id: 16062655361937
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/16062655361937
---
> **Resumen:** Configura el proceso de SSO usando Ping Identity como proveedor de identidad (IdP).

El primer paso para configurar el proceso de SSO de AppsFlyer se realiza en la plataforma Ping Identity. Sigue los pasos que se indican a continuación:

<div id="create-the-appsflyer-app-in-ping" />

<Accordion title="Crea la aplicación de AppsFlyer en Ping Identity">

**Requisito previo:** Una cuenta de Ping Identity con privilegios administrativos.

1. En el menú de administración de Ping Identity, ve a **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Aplicaciones</Anchor>** y haz clic en +.
2. En la sección que se abre a la derecha:
   * Introduce el nombre que quieres mostrar en la lista de aplicaciones del plugin de Ping Identity.
   * Selecciona Aplicación SAML como tipo de aplicación.
3. Haz clic en **Configure**. Aparece la configuración de SAML.
   * Para la autenticación iniciada desde el proveedor de servicios (AppsFlyer), selecciona **Import From URL**:
     * **Import URL:** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">https://hq1.appsflyer.com/auth/sso-metadata</Anchor>
     * **ACS URLs:** Introduce el siguiente enlace usando el ID de tu cuenta de AppsFlyer:  
       <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">https://hq1.appsflyer.com/auth/sso-callback</Anchor>
     * **Entity ID:** Introduce el siguiente enlace: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>  

       <Image alt="ping" src="https://files.readme.io/8b265666f05bc4f6ab984151d7d73653b9ea5dcb837898d17e96bf9c392fe638-16063467179921.png" width="419px" />
   * Para la autenticación iniciada desde el IdP (Ping Identity), selecciona **Manually Enter**:
     * **ACS URLs:** Introduce el siguiente enlace usando el ID de tu cuenta de AppsFlyer:   
       `https://hq1.appsflyer.com/auth/sso-callback/<Introduce aquí el ID de tu cuenta de AppsFlyer>`
     * **Entity ID:** Introduce el siguiente enlace: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>
4. Haga clic en **Guardar**.
5. En la pestaña **Configuration**:
   1. Haz clic en **Download Metadata**.
   2. En la esquina superior derecha, haz clic en el icono de edición e introduce los campos siguientes:  

      <Image alt="ping" src="https://files.readme.io/386fab01b9389d88ea0c4870ba2ea8e33d9ab6e27322059be5e46efbf248714b-16063435689233.png" width="487px" />

      * **CLAVE DE FIRMA:**
        * Selecciona **Sign Assertion & Response**.
        * **Algoritmo de firma:** Selecciona **RSA\_SHA256**.
      * **CIFRADO:**
        * Selecciona **Enable Encryption**.
        * ALGORITMO: Selecciona **AES\_256**.
      * **CERTIFICADO:**
        * Selecciona **Importar** y sube el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">certificado de cifrado de AppsFlyer</Anchor>. Este certificado está firmado por AppsFlyer y se utiliza tanto para cifrar como para firmar la solicitud.  
          **Nota:** Puedes subir el certificado de AppsFlyer firmado por Amazon. Contacta a tu CSM para obtener este certificado.
        * Selecciona **Enforced Signed Authn Request**.
6. Haga clic en **Guardar**.
7. En la pestaña **Attribute Mappings**, haz clic en el icono de edición y selecciona **Email Address** en **PingOne Mappings**.  

   <Image alt="ping-identity" src="https://files.readme.io/b93ac5463868c8f5f7760b60492a30f7ae59c52b766e76ef57fbe42e00f4bf2b-16292200523025.png" width="620px" />
8. Haga clic en **Guardar**.

</Accordion>

<div id="create-ping-groups" />

<Accordion title="Crear grupos de Ping Identity">

Ahora que ya has creado la aplicación SAML de Ping Identity, crea grupos de usuarios y, después, añade usuarios a los grupos.

1. En el menú de administración de Ping Identity, ve a **Identity** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/group">Groups</Anchor>** y haz clic en +.  

   <Image alt="ping" src="https://files.readme.io/fcc2a3f035a285d96d7b7c3e83cfeed64e86cb0f0807e6acced75df89bd8dfc4-16292210866705.png" width="216px" />
2. En la sección que se abre a la derecha, introduce el nombre del grupo y haz clic en **Save**.
3. Repite los pasos 1-2 para todos los grupos de usuarios.

</Accordion>

<div id="create-ping-identity-users-and-assign-them-to-groups-and-roles" />

<Accordion title="Crear usuarios de Ping Identity y asignarlos a grupos y roles">

1. En el menú de administración de Ping Identity, ve a **Identity** > <Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/user">**Users**</Anchor> y haz clic en +.  

   ![ping](https://files.readme.io/802946a62c1df918b82cccc1cf0855ffea8167ed91aa6b0d6bce8973c37b4e75-16292200536081.png)
2. En la sección que se abre a la derecha:
   1. Introduce el nombre y la dirección de correo electrónico del usuario.
   2. Selecciona **Administrator Population**.
   3. Crea una contraseña de un solo uso para el usuario o haz clic en **Generate Password** para generar una para el usuario. Cuando el usuario acceda a Ping Identity, tendrá que crear
   4. Haga clic en **Guardar**.
3. Haz clic en el botón Editar de **Groups**, marca el grupo para añadir el usuario y haz clic en **Save**.
4. Haz clic en la pestaña **Roles** > **Grant roles**, selecciona los roles para el usuario y haz clic en **Save**.

</Accordion>

<div id="provide-access-to-your-groups-and-activate-the-app" />

<Accordion title="Concede acceso a tus grupos y activa la aplicación">

### Concede acceso a tus grupos

1. En el menú de administración de Ping Identity, ve a **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** y selecciona la aplicación que has creado.  

   ![pi-applications.png](https://files.readme.io/6c8545bc5334747d7da6a090ca745c1b00cfedc3f48e59ccc304c814885cd183-16522614384785.png)
2. En la sección que se abre a la derecha, selecciona la pestaña **Access** y haz clic en el botón Editar.
3. Selecciona el grupo o los grupos que has creado y haz clic en **Save**.

### Activa la aplicación

1. En el menú de administración de Ping Identity, ve a **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** y selecciona la aplicación que has creado.
2. Activa la aplicación.  

   ![pi-appsflyer](https://files.readme.io/24c34f3426ae7b46301316937ae8485464e0b3810808e3bbcc1be843ba34a616-16523020816657.png)

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Completa el proceso en AppsFlyer">

Ahora que has configurado la parte del IdP, vuelve a AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">completar la configuración</Anchor>. Después, puedes hacer una <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">prueba</Anchor> para comprobar que funciona.

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="https://docs.pingidentity.com/r/en-us/pingfederate-112/pf_ident_provid_sso_config">Documentación de configuración de SSO de Ping Identity</Anchor>

<div data-zendesk-anchors="h_01HDP087XSDCY9W577GARNQ5GS=create-the-appsflyer-app-in-ping h_01HDP087XSRYXKE5TW7HYR3NYZ=create-ping-groups h_01HDP087XSKBVDREY0YZ27CG8T=create-ping-identity-users-and-assign-them-to-groups-and-roles h_01HDP087XSQPN3DAH8HAKMH3GS=provide-access-to-your-groups-and-activate-the-app provide-access-to-your-groups=concede-acceso-a-tus-grupos h_01HDP087XST1C28TEJXF3X8XK4=concede-acceso-a-tus-grupos activate-the-app=activa-la-aplicaci%C3%B3n h_01HDP087XSMBE3G6A4DSQ1WHBT=activa-la-aplicaci%C3%B3n h_01HDP087XS1S0XC5W74MK2AYY3=complete-the-process-in-appsflyer h_01HDP0ARX3NJZWBK0KC9Q64MG8=v%C3%A9ase-tambi%C3%A9n" />
