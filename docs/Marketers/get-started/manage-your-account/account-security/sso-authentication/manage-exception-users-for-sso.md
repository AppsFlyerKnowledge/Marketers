---
title: Gestionar usuarios con excepciones para SSO
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
  created_at: '2026-05-27T08:43:46Z'
  edited_at: '2026-08-12T12:04:04Z'
  id: 47096696016529
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/47096696016529
---
> **En resumen:** Los usuarios con excepciones son usuarios que no tienen que iniciar sesión mediante SSO. SSO sigue estando habilitado para la cuenta, y los administradores pueden dar a usuarios concretos acceso a un método de login alternativo asignado.

## **Información sobre los usuarios con excepciones**

Los usuarios con excepciones proporcionan acceso controlado a los usuarios que necesitan un método de login que no sea SSO. Por ejemplo, los administradores pueden usar usuarios con excepciones para acceso de emergencia o para usuarios que no pueden usar el proveedor de identidad de la cuenta.

Los usuarios con excepciones pueden iniciar sesión con SSO o con el método de login alternativo que tengan asignado. Los usuarios que no se añadan como usuarios con excepciones deben iniciar sesión mediante SSO.

Recomendamos añadir al menos un administrador de confianza como usuario con excepciones durante la configuración inicial de SSO. Si la configuración de SSO es incorrecta, el administrador puede iniciar sesión con el método de login alternativo que tenga asignado y actualizar la configuración.

## **Prerrequisitos**

* SSO debe estar configurado para la cuenta.
* Para gestionar SSO y los usuarios con excepciones, debes tener el permiso **Seguridad de login** establecido en **Gestionar**.

<div id="add-exception-users-during-sso-setup" />

<Accordion title="Añadir usuarios con excepciones durante la configuración de SSO">

**Recomendado:** Añade al menos un administrador de confianza como usuario con excepciones antes de activar SSO. Esto ayuda a evitar que se bloquee la cuenta si la configuración de SSO es incorrecta.

Añadir usuarios con excepciones:

1. En el paso **Añadir usuarios con excepciones**, haz clic en **Añadir usuarios con excepciones**.
2. Busca un usuario por nombre o correo electrónico.
3. Selecciona al usuario que quieres añadir.
4. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
   * **Nombre de usuario & contraseña**
   * **appsflyer firma-de-certificado.jpg**
5. Repite los pasos del 2 al 4 para cada usuario que quieras añadir.
6. Haz clic en **Añadir usuarios con excepciones**.
7. **Para activar el método SSO cuando 2FA está activo:** Primero desactiva 2FA, luego activa SSO

Si no añades usuarios con excepciones, todos los usuarios de la cuenta deberán iniciar sesión mediante SSO después de la activación.

</Accordion>

<div id="add-login-methods-for-multiple-users" />

<Accordion title="Añadir métodos de login para varios usuarios">

Para añadir el mismo método de login alternativo a varios usuarios:

1. Selecciona las casillas de verificación de los usuarios que quieres actualizar.
2. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
3. Selecciona una de las siguientes opciones:
   * **Aplicar el nombre de usuario y la contraseña a todos los usuarios seleccionados**
   * **Aplicar la app de autenticación a todos los usuarios seleccionados**

</Accordion>

<div id="edit-exception-users-after-sso-activation" />

<Accordion title="Editar usuarios con excepciones después de activar el SSO">

Después de que el SSO esté activo, puedes añadir usuarios con excepciones, eliminar usuarios con excepciones o actualizar sus métodos de login alternativos.

Para editar usuarios con excepciones:

1. Ve a **Centro de seguridad** > **Seguridad de login**.
2. En la sección**Inicio de sesión único (SSO)**, desactiva la opción **Inicio de sesión único** .
3. Abre la sección **Usuarios con excepciones**.
4. Haz clic en **Editar usuarios con excepciones**.
5. Añade usuarios, elimina usuarios o actualiza métodos de login alternativos.
6. Haga clic en **Guardar**.
7. En el cuadro de diálogo **¿Guardar cambios?** dialog, haz clic en **Guardar cambios**.

Los usuarios con excepciones añadidos anteriormente aparecen con su método de login alternativo actual.

</Accordion>

<div id="delete-exception-users" />

<Accordion title="Eliminar usuarios con excepciones">

Para eliminar un usuario con excepciones:

En el cuadro de diálogo Editar usuarios con excepciones, busca el usuario que quieres eliminar.

Haz clic en el icono de borrar.

El usuario se elimina de la lista inmediatamente.

</Accordion>

<div id="alternative-login-methods" />

<Accordion title="Métodos alternativos de login">

| **Método de inicio de sesión** | **Nota** |
| --- | --- |
| Nombre de usuario & contraseña | Permite que el usuario con excepciones inicie sesión con su nombre de usuario y contraseña de AppsFlyer. |
| appsflyer firma-de-certificado.jpg | Permite que el usuario con excepciones inicie sesión con una aplicación de autenticación. SMS no es compatible. |

</Accordion>

<div id="handle-partial-activation-failures" />

<Accordion title="Gestionar errores de activación parcial">

En algunos casos, la activación del SSO se realiza correctamente, pero no se añaden uno o varios usuarios con excepciones.

Cuando esto sucede:

* El SSO permanece activo.
* Los usuarios que no se hayan añadido como usuarios de excepción deben iniciar sesión a través de SSO.
* Los administradores pueden añadir o actualizar usuarios de excepción en **Editar SSO**.

</Accordion>

<div id="reset-passwords-for-sso-accounts" />

<Accordion title="Restablecer contraseñas de cuentas SSO">

Todos los usuarios pueden iniciar el flujo de recuperación de contraseña. Sin embargo, solo los usuarios de excepción a los que se les haya asignado el método alternativo de inicio de sesión **Nombre de usuario & contraseña** pueden iniciar sesión con la nueva contraseña.

Los usuarios que no sean usuarios de excepción deben seguir iniciando sesión mediante SSO.

</Accordion>

<div id="migrate-from-legacy-unforce-sso" />

<Accordion title="Migrar desde el Unforce SSO heredado">

En las cuentas migradas desde la versión heredada de Unforce SSO a nivel de cuenta, los usuarios existentes que iniciaban sesión con nombre de usuario y contraseña se añaden como usuarios de excepción con **Nombre de usuario & contraseña** como método alternativo de inicio de sesión.

Los usuarios nuevos que se creen después de la migración deben iniciar sesión mediante SSO, a menos que un administrador los añada explícitamente como usuarios de excepción.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| **Caducado** | **Nota** |
| --- | --- |
| Aplicación de SSO | El SSO sigue aplicándose en la cuenta. Los usuarios de excepción son excepciones controladas a nivel de usuario. |
| Métodos alternativos de inicio de sesión compatibles | Los usuarios de excepción pueden usar **Nombre de usuario & contraseña** o la **aplicación Authenticator**. |
| Autenticación por SMS | El SMS no es compatible como método alternativo de login. |
| Permiso obligatorio | Para gestionar usuarios de excepción, los administradores deben tener el permiso **Seguridad de inicio de sesión** configurado como **Gestionar**. |
| Permiso de solo visualización | Los administradores con acceso de solo visualización pueden ver los usuarios de excepción existentes, pero no pueden editarlos. |
| Usuarios nuevos después de la migración | Los usuarios nuevos deben iniciar sesión mediante SSO, a menos que un administrador los añada como usuarios de excepción. |

</Accordion>

<div data-zendesk-anchors="about-exception-users=informaci%C3%B3n-sobre-los-usuarios-con-excepciones h_01KSM9MR6FEJH62VN5BPG7C8C8=informaci%C3%B3n-sobre-los-usuarios-con-excepciones prerequisites=prerrequisitos h_01KSM9MR6GG6K3JVYEDKKSARH5=prerrequisitos h_01KSM9RZPTBKSBH788FNP1PMDH=add-exception-users-during-sso-setup h_01KSM9RZPT9WGSMX5K10BA9WSY=add-login-methods-for-multiple-users h_01KSM9RZPTXDTM7Y0RV2PVRAX7=edit-exception-users-after-sso-activation h_01KSM9RZPT1G9MJ4BQYTSKPZ0F=delete-exception-users h_01KSM9RZPT3CZR4QGMWAH534H5=alternative-login-methods h_01KSM9RZPTJ988PFQA68DVE73G=handle-partial-activation-failures h_01KSM9RZPVS8AVWAD7EPGCG6F9=reset-passwords-for-sso-accounts h_01KSM9RZPV36BQWH360QSP98SY=migrate-from-legacy-unforce-sso h_01KSMA3KYT6F2FSB2QGDPV4CAM=traits-and-limitations" />
