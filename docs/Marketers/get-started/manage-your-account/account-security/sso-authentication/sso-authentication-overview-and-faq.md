---
title: 'Autenticación SSO: resumen y preguntas frecuentes'
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
  created_at: '2024-08-11T07:54:46Z'
  edited_at: '2026-08-12T12:04:09Z'
  id: 27434547337617
  locale: es
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/es/articles/27434547337617
---
> **De un vistazo:** Obtén información sobre la autenticación de inicio de sesión único (SSO) y el proceso para iniciar sesión en AppsFlyer mediante tu proveedor de identidad (IdP) con SSO. Encuentra respuestas a las preguntas frecuentes sobre el login con SSO.

## ¿Qué es la autenticación SSO?

SSO es un método de autenticación que permite a los usuarios acceder a múltiples aplicaciones, sistemas o plataformas independientes iniciando sesión una vez a través de tu proveedor de identidad (por ejemplo, Okta, Azure AD o OneLogin). Agregar AppsFlyer a tu IdP permite a tus usuarios iniciar sesión en AppsFlyer directamente desde tu IdP mediante un proceso de inicio de sesión único (SSO). Esto permite que tus usuarios inicien sesión automáticamente con una **autenticación más segura** utilizando solo un conjunto de credenciales.

## ¿Cómo funciona la autenticación SSO?

La plataforma AppsFlyer admite la verificación SSO mediante el protocolo SAML2.0. Al implementar el certificado de autenticación de AppsFlyer en tu IdP por medio del protocolo SAML 2.0, tu IdP genera un token con datos de usuario autenticado. El mismo proceso se realiza desde tu IdP a AppsFlyer: su token se implementa en AppsFlyer.

## El certificado de autenticación de AppsFlyer (proveedor de servicios)

AppsFlyer proporciona un certificado de cifrado para cifrar datos y firmar la solicitud de SSO. Puedes elegir qué certificado usar:

* **Certificado firmado por AppsFlyer:** Un certificado de AppsFlyer creado a partir de la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL de metadatos de AppsFlyer</Anchor>
* **Certificado firmado por una CA:** Un certificado de AppsFlyer **firmado por Amazon**.

> 📘 **Advertencia**
>
> AppsFlyer no admite números de serie negativos en el certificado.

## Resolución de problemas y preguntas frecuentes

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="¿Pueden los usuarios iniciar sesión utilizando los métodos SSO y 2FA?">

Solo se puede utilizar un método de inicio de sesión de seguridad a la vez, ya sea SSO o 2FA.

* **Para activar el método 2FA cuando SSO está activo:** primero desactiva SSO y, después, activa 2FA
* **Para activar el método SSO cuando 2FA está activo:** primero desactiva 2FA y, después, activa SSO

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="¿Por qué algunos usuarios no pueden conectarse mediante SSO?">

Asegúrate de que todos los correos electrónicos de los usuarios estén configurados en ambos sistemas: en tu IdP y en la plataforma AppsFlyer. Si ese no es el motivo, comunícate con tu CSM para averiguar por qué y cómo solucionarlo. Mientras tanto, tu CSM puede desactivar temporalmente la opción **Forzar login con SSO** para que los usuarios puedan iniciar sesión con su correo electrónico y contraseña.

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="¿Necesito un entorno de prueba para probar la configuración antes de establecer la configuración?">

No se requiere un entorno de prueba. Sigue los pasos del paso 3 para probar el login con SSO, ya sea desde el IdP o desde el lado del proveedor de servicios (AppsFlyer).

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="¿Qué debo hacer antes de que caduque el certificado de AppsFlyer?">

AppsFlyer te avisará a través de la plataforma cuando tu certificado SSO de AppsFlyer esté a punto de caducar. Siga estos pasos para implementar el nuevo certificado de AppsFlyer:

1. [Crea un nuevo archivo de certificado con la clave de cifrado actualizada](#how-to-create-the-appsflyer-certificate-file).
2. Ve a tu IdP e implemente el nuevo certificado de AppsFlyer.
3. Después de la implementación, vuelve a la sección **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado** y confirma que has actualizado el certificado más reciente de AppsFlyer.

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="El inicio de sesión forzado SSO está deshabilitado, ¿cómo puedo habilitarlo?">

Una vez que se selecciona la opción **Forzar login con SSO** y se guarda la configuración, esta opción se desactiva. Para revertir el cambio y volver a habilitar **Forzar login con SSO**, tendrás que volver a configurar el <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">paso 2</Anchor> del proceso de SSO desde el principio.

> 📘 **Nota**
>
> Mantener seleccionada la opción **Forzar login con SSO** es el método recomendado para exigir un login más seguro. Significa que los usuarios que intentan iniciar sesión son autenticados por el IdP y no pueden iniciar sesión con su nombre de usuario y clave.

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="¿Es necesario utilizar el certificado de AppsFlyer en mi IdP?">

Se **recomienda encarecidamente** implementar el certificado de AppsFlyer en tu IdP, pero no es obligatorio. Algunos IdP, como Google Workspace y Microsoft Entra ID, no requieren de forma predeterminada un certificado de proveedor de servicios.

</Accordion>

<div id="what-happens-when-i-deactivate-sso-and-how-do-i-do-it" />

<Accordion title="¿Qué ocurre cuando desactivo SSO y cómo lo hago?">

Al desactivar la autenticación SSO, los usuarios podrán iniciar sesión con otros métodos, como sus nombres de usuario y contraseñas de AppsFlyer y el método <Anchor target="_blank" href="/marketers/es/docs/implementing-and-using-2fa-login">2FA</Anchor>.

1. Desde la barra superior, abre el menú de la cuenta (menú desplegable de dirección de correo electrónico del administrador)> **Centro de seguridad**.
2. En **Seguridad de inicio de sesión mejorada**, selecciona **Configurar método de inicio de sesión**.
3. En la sección **Inicio de sesión único (SSO)**, desactiva el interruptor **Inicio de sesión único**.

</Accordion>

<div id="can-i-have-negative-serial-numbers-in-the-certificate" />

<Accordion title="¿Puedo tener números de serie negativos en el certificado?">

N.º AppsFlyer no admite números de serie negativos en el certificado.

</Accordion>

<div data-zendesk-anchors="what-is-sso=qu%C3%A9-es-la-autenticaci%C3%B3n-sso h_01J5QR4DE5EBSVWHXXENZTRPWQ=qu%C3%A9-es-la-autenticaci%C3%B3n-sso how-does-sso-authentication-work=c%C3%B3mo-funciona-la-autenticaci%C3%B3n-sso h_01HCHG901WVRX1MKNB0KF02PSJ=c%C3%B3mo-funciona-la-autenticaci%C3%B3n-sso the-authentication-certificate=el-certificado-de-autenticaci%C3%B3n-de-appsflyer-proveedor-de-servicios h_01HCHG901WG05TP2NJBJRDRWPN=el-certificado-de-autenticaci%C3%B3n-de-appsflyer-proveedor-de-servicios h_01JJH8DC3AHNC6GST0S41X8MFV=advertencia faq=resoluci%C3%B3n-de-problemas-y-preguntas-frecuentes h_01HCHG901XSAQ7HSGM0ZVT7B70=resoluci%C3%B3n-de-problemas-y-preguntas-frecuentes h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=nota h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp h_01J5QRR54JNC5YNZHQ463KS7BS=what-happens-when-i-deactivate-sso-and-how-do-i-do-it h_01JJH8F3VFTQA1AANNNS85YBF8=can-i-have-negative-serial-numbers-in-the-certificate" />
