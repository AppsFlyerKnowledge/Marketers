---
title: Configura la autenticación SSO con tu proveedor de identidad (IdP)
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
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
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-08-12T12:04:06Z'
  id: 360015017198
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/360015017198
---
> **De un vistazo:** Al integrar AppsFlyer con tu proveedor de identidad (IdP), los usuarios de cuentas de AppsFlyer pueden iniciar sesión en AppsFlyer mediante el inicio de sesión único (SSO). Obtén información sobre la autenticación SSO, cómo configurar SSO con tu IdP y encuentra respuestas a las preguntas frecuentes.

<div id="considerations" />

## Consideraciones

* Al asignar usuarios al IdP, asegúrate de utilizar el mismo correo electrónico de usuario que en AppsFlyer para que cada usuario en ambas plataformas tenga el mismo correo electrónico.
* Los ajustes de configuración de SSO solo pueden ser gestionados y eliminados por un administrador con el permiso de **seguridad de login** configurado en **Gestionar**.
* SSO se aplica a la cuenta de forma predeterminada.
* Los administradores pueden añadir usuarios de excepción que pueden iniciar sesión con SSO o con un método de login alternativo asignado.
* Los métodos de login alternativos compatibles para los usuarios de excepción son:
  * Nombre de usuario & contraseña
  * Aplicación de autenticación (2FA)
* SMS no es compatible como método de login alternativo para los usuarios de excepción.
* Cuando no se añaden usuarios de excepción, SSO se aplica de forma predeterminada a todos los usuarios tras la activación.

<div id="note" />

> 📘 **Advertencia**
>
> Te recomendamos añadir al menos un administrador de confianza como usuario de excepción antes de activar SSO. Esto ayuda a evitar el bloqueo de la cuenta si la configuración de SSO es incorrecta

<div id="access-the-sso-configuration-page" />

## Accede a la página de configuración de SSO

1. Desde la barra superior, abre el menú de la cuenta (menú desplegable de dirección de correo electrónico del administrador)> **Centro de seguridad**.
2. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
3. Desde la barra superior, abre el menú de la cuenta (menú desplegable de dirección de correo electrónico del administrador)> **Centro de seguridad**.

<div id="set-up-sso" />

## Configura SSO con tu IdP

El proceso de configuración, utilizando el protocolo SAML2.0, se realiza en tres etapas. [El paso 1](#step-1-configure-the-idp-platform) incluye procedimientos detallados para los siguientes IdP: Una vez que se selecciona la opción **Forzar inicio de sesión SSO** y se guarda la configuración, esta opción se desactiva.

<div id="note-1" />

> 📘 **Desde el Inicio de sesión único (SSO) , cerca Copia el último certificado , haz clic en Vista .**
>
> * Esta guía incluye procedimientos detallados para los IdP que se indican a continuación. Para todos los demás IdP, se describe una visión general de la configuración.
>   * JumpCloud
>   * Okta
>   * OneLogin
>   * Identidad de ping

<div id="step-1-set-up-the-idp-platform" />

<Accordion title="Paso 1: Configurar la plataforma IdP">

Consulta los procedimientos detallados para configurar la autenticación SSO en cualquiera de los siguientes IdP:

* <Anchor target="_blank" href="/marketers/es/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/configure-appsflyer-sso-in-ping-identity">Identidad de ping</Anchor>

<div id="setup-overview-for-other-idp-platforms" />

#### Descripción general de la configuración para otras plataformas IdP

Descripción general del proceso de configuración en otras plataformas IdP:

* Se crea una aplicación AppsFlyer en la plataforma IdP, basada en el protocolo SAML 2.0, y el [certificado de autenticación de AppsFlyer](#the-authentication-certificate) se implementa en la plataforma IdP.
* Los usuarios son asignados a la nueva aplicación AppsFlyer
* El certificado de IdP o los metadatos se recuperan para su uso en AppsFlyer (en el [Paso 2](#step-2-complete-the-configuration-at-appsflyer)) Proporciona los metadatos del IdP).

<div id="note-2" />

> 📘 **Nota**
>
> * **Nota:** Asegúrate de que todos los correos electrónicos de los usuarios estén configurados en ambos sistemas: en tu IdP y en la plataforma AppsFlyer.
> * Los <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">metadatos de AppsFlyer</Anchor> contienen:
>   * Certificados de cifrado y firma
>   * ID de entidad
>   * URL de devolución de llamada

<div id="step-2-set-up-appsflyer" />

<Accordion title="Paso 2: Completa la configuración en AppsFlyer">

Después de configurar la plataforma IdP, regresa a AppsFlyer para completar la configuración.

Consulta cómo [acceder a la página de configuración de SSO](#accede-a-la-página-de-configuración-de-sso).

<div id="step-1-select-authentication-starting-point" />

<Accordion title="1. Obtener datos">

1. Selecciona desde dónde acceden los usuarios a AppsFlyer. Esto también define el proceso de autenticación.
   * [Conoce el proceso de inicio de sesión en AppsFlyer mediante inicio de sesión único (SSO) con tu proveedor de identidad (IdP).](idp)
   * [Proveedor de servicios (AppsFlyer)](#proveedor-de-servicios-appsflyer)
2. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

<div id="identity-provider-idp" />

#### Procedimientos de configuración para los principales IdP

Ve a tu IdP e implemente el nuevo certificado de AppsFlyer.

<div id="note-3" />

> 📘 **Nota**
>
> Al seleccionar esta opción, los usuarios pueden iniciar sesión tanto a través del IdP como del proveedor de servicios (AppsFlyer).

<div id="service-provider-appsflyer" />

#### Proveedor de servicios (AppsFlyer)

Los usuarios también pueden ingresar a AppsFlyer a través de la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">página de inicio de sesión de SSO de AppsFlyer</Anchor> haciendo clic en **Iniciar sesión con SSO** e ingresando su dirección de correo electrónico. Serán dirigidos al IdP para su autenticación y luego redirigidos a la página de inicio de AppsFlyer.

[<Image alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="257px" />](https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png)

<div id="note-4" />

> 📘 **Nota**
>
> Agregar AppsFlyer a tu IdP permite a tus usuarios iniciar sesión en AppsFlyer directamente desde tu IdP mediante un proceso de inicio de sesión único (SSO).

<div id="step-3-select-certificate-type" />

<Accordion title="2. Crear el archivo de texto del certificado:">

AppsFlyer proporciona un certificado de cifrado para cifrar datos y firmar la solicitud de SSO.

* Abre la URL <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">de metadatos de AppsFlyer</Anchor> y busca `use="encryption"`.
* **Certificado firmado por CA:** Un certificado de AppsFlyer **firmado por Amazon**.

**Para realizar este paso:**

* Selecciona el tipo de certificado y haz clic en **Siguiente**.

<div id="note-5" />

> 📘 **Nota**
>
> El certificado solo se activa después de que ambas partes completen el proceso de implementación mutua del certificado: AppsFlyer incorpora la configuración SAML del IdP y el IdP integra los metadatos de SSO más recientes de AppsFlyer. Esto se hace en dos pasos:

</Accordion>

<div id="step-4-obtain-service-provider-appsflyer-metadata" />

<Accordion title="3. Obtener metadatos del proveedor de servicios (AppsFlyer)">

1. Copia los últimos metadatos de SSO de AppsFlyer e impleméntalos en la configuración SAML de tu IdP.
   * Si has seleccionado el **certificado firmado por AppsFlyer:** copia cualquiera de los campos que aparecen a continuación.
     * **URL de metadatos:** Para los IdP compatibles con URL de metadatos completas, copia la URL e impleméntala en tu IdP.
     * **Componentes de metadatos:** Para los IdP que no admiten URL de metadatos completas, copia cada uno de los componentes e impleméntalos en la sección correspondiente de tu IdP: **ID de entidad**, **clave de cifrado** (descargable) y **URL de ubicación**.
     * **Archivo XML:** Tienes la opción de descargar los metadatos de SSO de AppsFlyer como archivo XML.
   * Si has seleccionado el **certificado firmado por una CA:** copia los **componentes de metadatos**.
2. **Requisito previo:** Los usuarios deben estar configurados en ambos sistemas (AppsFlyer y el IdP) usando el mismo correo electrónico

</Accordion>

<div id="step-5-provide-idp-metadata" />

<Accordion title="4. Proporcionar metadatos de IdP">

Proporciona los metadatos de SSO del IdP con las opciones que aparecen a continuación y, después, valida el formato de los metadatos. **Nota**: Los datos del certificado del IdP deben estar en un formato de una sola línea y sin metacaracteres.

1. Selecciona el método preferido para proporcionar los metadatos de tu IdP:
   * **Utiliza el siguiente enlace para autenticar usuarios desde el IdP:**
   * **Archivo XML:** Sube el archivo XML de metadatos del IdP.
2. Haz clic en **Validar**. En la parte superior de la página aparece un mensaje de confirmación que indica el estado de la validación.
3. Haz clic en **Activar**. En la parte superior de la página aparece un mensaje de confirmación que indica el estado de activación de la autenticación SSO.

</Accordion>

<div id="5-add-exception-users" />

<Accordion title="5. Añadir usuarios con excepciones">

Los usuarios con excepción son usuarios que no están obligados a iniciar sesión mediante SSO. SSO sigue siendo obligatorio para la cuenta y solo los usuarios añadidos explícitamente como usuarios con excepción pueden iniciar sesión con un método de login alternativo asignado.

Añadir usuarios con excepción es opcional. Si la función está configurada en modo solo SSO, todos los usuarios deben iniciar sesión usando solo SSO y no se pueden excluir usuarios específicos.

<div id="note-6" />

> 📘 **Advertencia**
>
> Añade al menos un administrador de confianza como usuario con excepción antes de activar SSO. Si la configuración de SSO es incorrecta, este usuario puede iniciar sesión con su método de login alternativo asignado y actualizar la configuración.

Para añadir usuarios con excepción:

1. Haz clic en **Añadir usuarios con excepción**.
2. En el cuadro de diálogo **Añadir usuarios con excepción**, busca un usuario por nombre o correo electrónico.
3. Selecciona el usuario que quieres añadir.
4. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
   * **Nombre de usuario & contraseña**
   * **appsflyer firma-de-certificado.jpg**
5. Repite los pasos 2 a 4 para cada usuario que quieras añadir.
6. Haz clic en **Agregar usuarios de excepción**.

<div id="add-login-methods-for-multiple-users" />

### **Agregar métodos de inicio de sesión para varios usuarios**

Para agregar el mismo método de inicio de sesión alternativo para varios usuarios de excepción:

1. Selecciona las casillas de verificación de los usuarios que quieres actualizar.
2. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
3. Selecciona una de las siguientes opciones:
   * **Aplicar el nombre de usuario y la contraseña a todos los usuarios seleccionados**
   * **Aplicar la app de autenticación a todos los usuarios seleccionados**

<div id="delete-an-exception-user" />

### **Eliminar un usuario de excepción**

Para eliminar un usuario de la lista de usuarios de excepción:

* Haz clic en el icono **Eliminar** en la fila del usuario.

El usuario se elimina de la lista inmediatamente.

</Accordion>

<div id="6-activate-sso" />

<Accordion title="6. Activar SSO">

<div id="note-7" />

> 📘 **Advertencia**
>
> Antes de activar SSO, te recomendamos que añadas al menos un administrador de confianza como usuario de excepción. Esto ayuda a evitar el bloqueo de la cuenta si la configuración de SSO es incorrecta.

Sólo un administrador puede activar o desactivar SSO

1. **Para activar el método SSO cuando 2FA está activo:** Primero desactiva 2FA, luego activa SSO
2. En el cuadro de diálogo **¿Activar SSO?** revisa la configuración de SSO.
3. **Para activar el método 2FA cuando SSO está activo:** Primero desactiva SSO, luego activa 2FA

Una configuración incorrecta podría impedir que los usuarios accedan a AppsFlyer. Revisa tu configuración antes de activar SSO.

Si no se añadieron usuarios de excepción, el cuadro de diálogo de confirmación muestra un mensaje indicando que, después de la activación, todos deberán iniciar sesión mediante SSO.

<div id="activation-results" />

### **Resultados de la activación**

| **Resultado** | **Nota** |
| --- | --- |
| La activación de SSO se completa correctamente y se añaden usuarios de excepción | SSO está activo y los usuarios de excepción están configurados. |
| La activación de SSO se completa correctamente, pero no se añaden algunos usuarios de excepción | SSO sigue activo. Agrega o actualiza usuarios de excepción desde **Editar SSO**. |
| Autenticación SSO | SSO no se activa y el estado de la configuración vuelve a **No configurado**. |

## **Editar SSO**

Después de que SSO esté activo, puedes editar la configuración de SSO y gestionar los usuarios de excepción.

Para editar la configuración de SSO:

1. En la sección**Inicio de sesión único (SSO)**, desactiva la opción **Inicio de sesión único** .
2. Abre la sección que quieres actualizar.
3. Haz los cambios requeridos.
4. Haz clic en **Importar**y luego en **Guardar**.
5. En el cuadro de diálogo **Save changes?** cuadro de diálogo, revisa los cambios.
6. Desde la barra superior, abre el menú de cuenta (menú desplegable de dirección de correo electrónico) > **Centro de seguridad**.

Cuando actualizas el tipo de certificado o el punto de inicio de la autenticación, los metadatos de AppsFlyer cambian. Copia los metadatos SSO más recientes del proveedor de servicios (AppsFlyer) y añádelos a la configuración SAML de tu IdP inmediatamente después de guardar los cambios.

<div id="edit-exception-users" />

### **Editar usuarios con excepciones**

Para editar usuarios con excepciones:

1. En la página de edición de SSO, abre la sección **Usuarios con excepciones**.
2. Haz clic en **Editar usuarios con excepciones**.
3. En el cuadro de diálogo **Editar usuarios con excepciones**, añade usuarios, elimínalos o actualiza métodos de login alternativos.
4. Activa **Inicio de sesión único**y haz clic en **Guardar**.
5. En el cuadro de diálogo **Save changes?** cuadro de diálogo, haz clic en **Save changes**.

Los usuarios con excepciones que hayas añadido anteriormente aparecen con su método de login alternativo actual.

</Accordion>

</Accordion>

<div id="step-3-test-the-sso-configuration" />

<Accordion title="Paso 3: Prueba del proceso SSO">

Después de completar la configuración de SSO en ambas plataformas: el IdP y AppsFlyer, verifica que los usuarios puedan iniciar sesión en AppsFlyer en **cualquiera** de los [métodos de devolución de llamada de URL](#single-signon-url-configuration): tu IdP o el proveedor de servicios (AppsFlyer), pero no ambos.

<div id="test-authentication-via-your-idp" />

#### Prueba la autenticación a través de tu IdP

Si has configurado la autenticación para iniciar sesión a través de tu IdP, verifica que los usuarios puedan ingresar a AppsFlyer desde el complemento o la página web del IdP:

1. Si has iniciado sesión en AppsFlyer y en el IdP, cierra sesión en ambos.
2. Abra una página web en modo incógnito.
3. Ve a la página web de tu IdP. Como no has iniciado sesión en el IdP, pasarás por un proceso de autenticación. Inicia sesión con el usuario correspondiente.
4. Busca y selecciona AppsFlyer. Se te dirigirá a la página de inicio de AppsFlyer. Esto indica que el proceso fue exitoso.

<div id="test-authentication-via-your-service-provider-appsflyer" />

#### Pruebe la autenticación a través de tu proveedor de servicios (AppsFlyer)

Si has configurado el flujo de autenticación para iniciar sesión a través de tu proveedor de servicios (AppsFlyer), verifica que los usuarios puedan ingresar a AppsFlyer usando su correo electrónico:

<Image alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. Si has iniciado sesión en AppsFlyer y en el IdP, cierra sesión en ambos.
2. Abra una página web en modo incógnito.
3. Ve a la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">página de inicio de sesión de AppsFlyer</Anchor> y haz clic en **Iniciar sesión con SSO**.
4. Ingresa el correo electrónico correspondiente y haz clic en **Continuar**. Ahora serás dirigido al IdP para su autenticación.
5. Después de la autenticación de IdP, se te dirigirá nuevamente a AppsFlyer como usuario conectado. Esto indica que el proceso fue exitoso.

</Accordion>

</Accordion>

</Accordion>

<div id="manage-sso-configuration" />

## Gestionar la configuración de SSO

Una vez que hayas configurado SSO, puedes editar la configuración o eliminarla.

Consulta cómo [acceder a la página de configuración de SSO](#accede-a-la-página-de-configuración-de-sso).

<div id="zd-edit-sso" />

<div id="edit-sso" />

<Accordion title="Editar SSO">

Desde esta página, puedes editar cualquiera de las siguientes opciones:

* Punto de partida de la autenticación
* El certificado de autenticación.
* Metadatos del proveedor de servicios
* IdP\_SSO\_certificate\_\_1\_.png
* Usuarios con excepciones

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> Cuando actualizas el tipo de certificado o el punto de inicio de la autenticación, los metadatos de AppsFlyer cambian. Copia los metadatos más recientes del proveedor de servicios de AppsFlyer y añádelos a la configuración SAML de tu proveedor de identidad (IdP) inmediatamente después de guardar los cambios

<div id="note-8" />

> 📘 **Advertencia**
>
> Añade al menos un administrador de confianza como usuario con excepciones. Si la configuración de SSO es incorrecta, este usuario puede iniciar sesión con el método de login alternativo que tenga asignado y actualizar la configuración.

Para editar la configuración de SSO:

1. En la sección**Inicio de sesión único (SSO)**, desactiva la opción **Inicio de sesión único** .
2. Abre la sección que quieras actualizar.
3. Haz los cambios requeridos.
4. Haga clic en **Guardar**.
5. En el cuadro de diálogo **Save changes?** Dialog, revisa los cambios.
6. Desde la barra superior, abre el menú de cuenta (menú desplegable de dirección de correo electrónico) > **Centro de seguridad**.

<div id="edit-exception-users-1" />

### Editar usuarios con excepciones

Para editar usuarios con excepciones:

1. Abre la sección **Usuarios con excepciones**.
2. Haz clic en **Editar usuarios con excepciones**.
3. En la lista de usuarios de **Editar usuarios con excepciones**, añade usuarios, elimina usuarios o actualiza los métodos de login alternativos.
4. Haga clic en **Guardar**.
5. En el cuadro de diálogo **¿Guardar cambios?**, haz clic en **Guardar cambios**.

Los usuarios con excepciones que se añadieron anteriormente aparecen con su método de login alternativo actual.

</Accordion>

<div id="remove-sso-configuration" />

<Accordion title="Desactivar la autenticación SSO">

Para eliminar la configuración de SSO:

1. En la sección **SAML Single sign-on (SSO)**, haz clic en el icono **Delete**.
2. En el cuadro de diálogo de confirmación, revisa el impacto de eliminar la configuración.
3. Haz clic en **Eliminar**.

Cuando eliminas la configuración de SSO, AppsFlyer elimina los metadatos y la configuración de SSO guardados para la cuenta.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Nombre | Descripción |
| --- | --- |
| Símbolos en la dirección de correo electrónico | SSO no admite direcciones de correo electrónico con el signo + en la dirección de correo electrónico.<br /><br />Por ejemplo: my+customer@demo.com<br /><br />Esto provocará un fallo de login. |
| Usuarios con excepciones | Un administrador debe añadir explícitamente a los usuarios con excepciones. |
| Métodos de login alternativos | Los métodos de login alternativos compatibles son **Nombre de usuario & contraseña** y **App de autenticación**. |
| Autenticación por SMS | SMS no es compatible como método de login alternativo para usuarios con excepciones. |
| No hay usuarios con excepciones | Si no se añaden usuarios con excepciones, todos los usuarios deben iniciar sesión mediante SSO después de la activación. |
| Permisos | Para configurar el SSO y gestionar usuarios con excepciones, los administradores deben tener el permiso **Seguridad de login** configurado en **Gestionar**. |
| Permisos de solo visualización | Los administradores con acceso de solo visualización a **Seguridad de login** pueden ver la página de SSO, pero no pueden editar la configuración de SSO ni los usuarios con excepciones. |
| Migración heredada de anulación de aplicación de SSO | En las cuentas migradas desde la anulación de aplicación de SSO heredada a nivel de cuenta, los usuarios existentes con nombre de usuario y contraseña se añaden como usuarios con excepciones. Los usuarios nuevos deben iniciar sesión mediante SSO, a menos que un administrador los añada explícitamente como usuarios con excepciones. |
| Usuario con excepciones recomendado | Te recomendamos añadir al menos un administrador de confianza como usuario con excepciones antes de activar SSO. Esto ayuda a evitar el bloqueo de la cuenta si la configuración de SSO es incorrecta. |

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> <Anchor target="_blank" href="/marketers/es/docs/sso-authentication-overview-and-faq">Encuentra respuestas a preguntas frecuentes sobre el inicio de sesión SSO.</Anchor>
>
> <Anchor target="_blank" href="/marketers/es/docs/manage-exception-users-for-sso">Más información sobre cómo gestionar usuarios con excepciones para SSO</Anchor>

<div data-zendesk-anchors="considerations=consideraciones h_01J7KK52TX8WGA3EK110R9M0GY=consideraciones h_01KSM8FMC9SCPBY2P56QPD6WJ2=advertencia access-the-sso-configuration-page=accede-a-la-p%C3%A1gina-de-configuraci%C3%B3n-de-sso h_01J7X4Y5Y50EFAPVP6JY8WAMKN=accede-a-la-p%C3%A1gina-de-configuraci%C3%B3n-de-sso setting-up-sso-authentication=configura-sso-con-tu-idp h_01HCHG901V25TSRGRT9244384D=configura-sso-con-tu-idp h_01J530X1930CMCF7XJM1XKPC74=desde-el-inicio-de-sesi%C3%B3n-%C3%BAnico-sso--cerca-copia-el-%C3%BAltimo-certificado--haz-clic-en-vista- 01J530ZP34SQKHM5324DNFA25Y=step-1-set-up-the-idp-platform configuration-overview-for-other-idp-platforms=descripci%C3%B3n-general-de-la-configuraci%C3%B3n-para-otras-plataformas-idp h_01HCHG901VPG0ZJ20XJBFPY7CD=descripci%C3%B3n-general-de-la-configuraci%C3%B3n-para-otras-plataformas-idp h_01HCHG901VH2XZS9Q0KM9D26WX=nota h_01J5303SNTEVQNA4KZEMS2VG04=step-2-set-up-appsflyer h_01J4PGJ2T73313B1X6ECQ17S7Q=step-1-select-authentication-starting-point identity-provider-idp=procedimientos-de-configuraci%C3%B3n-para-los-principales-idp h_01J4PHJ8FECGSAGQJGWREX3PKK=procedimientos-de-configuraci%C3%B3n-para-los-principales-idp h_01J4PHSVS55G2M00S00KG06BB7=nota-1 service-provider-appsflyer=proveedor-de-servicios-appsflyer h_01J4PHTR1E9JV3SM0A7N4X3WJY=proveedor-de-servicios-appsflyer h_01J4PJEQTBJ9P2SZBKGPF2696S=nota-2 h_01J4PGJ2T76F7YTK42VBW8J1P6=step-3-select-certificate-type h_01J8CEE2BZN0THJ7DNSGRCGJNQ=nota-3 h_01J4PGJ2T76PKE0V7NS7YXC4T5=step-4-obtain-service-provider-appsflyer-metadata h_01J4PGJ2T7SM8EGYZCW6D7AQN8=step-5-provide-idp-metadata h_01KSM7TN32SDETTPJRX5WPR707=5-add-exception-users h_01KSM8FMC91SDE8JQS12J7WXAG=advertencia-1 add-login-methods-for-multiple-users=agregar-m%C3%A9todos-de-inicio-de-sesi%C3%B3n-para-varios-usuarios h_01KSM7WDKE0PGCMFC6JCKTC107=agregar-m%C3%A9todos-de-inicio-de-sesi%C3%B3n-para-varios-usuarios delete-an-exception-user=eliminar-un-usuario-de-excepci%C3%B3n h_01KSM7WDKFBFDN7TQVK4YWH3FR=eliminar-un-usuario-de-excepci%C3%B3n h_01KSM7TN324FN2QS5W6XBY91ES=6-activate-sso h_01KSM8H456C2SFE9E21HNAWFQM=advertencia-2 activation-results=resultados-de-la-activaci%C3%B3n h_01KSM7YKYJ22W6TM1Q2EQGAAZ9=resultados-de-la-activaci%C3%B3n edit-sso::496a151=editar-sso h_01KSM7YKYPNA5MZKMZH7K5R09S=editar-sso edit-exception-users=editar-usuarios-con-excepciones h_01KSM7YKYSVF5ZSMSYK5HPQJQ0=editar-usuarios-con-excepciones h_01J5303SNTYMDMP2DW4GQCGEHK=step-3-test-the-sso-configuration testing-authentication-via-the-idp=prueba-la-autenticaci%C3%B3n-a-trav%C3%A9s-de-tu-idp h_01HCHG901WXSQ2VPCH2NKE63SE=prueba-la-autenticaci%C3%B3n-a-trav%C3%A9s-de-tu-idp testing-authentication-via-appsflyer=pruebe-la-autenticaci%C3%B3n-a-trav%C3%A9s-de-tu-proveedor-de-servicios-appsflyer h_01HCHG901W6DJ3GN6E7WFR6RNK=pruebe-la-autenticaci%C3%B3n-a-trav%C3%A9s-de-tu-proveedor-de-servicios-appsflyer manage-sso-configuration=gestionar-la-configuraci%C3%B3n-de-sso h_01J7WKPGTNPF10N4XMJG9ZDN87=gestionar-la-configuraci%C3%B3n-de-sso h_01J7X4P6B18HXJB99JYTVSC75N=edit-sso h_01KSMFXHV6501KFVD9SCCMJCF9=dos-puntos- h_01KSMFXHV6NJ4PKQ5117HB5B4H=advertencia-3 edit-exception-users::6da5a820=editar-usuarios-con-excepciones-1 h_01KSMFSP2QXYEQWB2CM4YHTTS0=editar-usuarios-con-excepciones-1 h_01J7X4P6B1THTVR1M966JS4P99=remove-sso-configuration h_01K44S4WP3N8HG872PQX1CCES8=traits-and-limitations h_01HDPF69BTMRYR6E6VNMFR4JY4=v%C3%A9ase-tambi%C3%A9n" />
