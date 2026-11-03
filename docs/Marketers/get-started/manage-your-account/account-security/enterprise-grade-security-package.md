---
title: Paquete de seguridad de nivel empresarial
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
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-10-20T03:41:52Z'
  id: 34053592094737
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/34053592094737
---
> **De un vistazo:** Refuerza la protección de tu cuenta con el **Enterprise-Grade Security Package,** una oferta premium diseñada para la gestión de identidades de nivel empresarial, el control de acceso a tokens y una visibilidad ampliada de auditoría.

## Introducción

El Enterprise-Grade Security Package reúne tres funciones clave que refuerzan la seguridad de tu organización:

* **Gestión de múltiples tokens con restricciones de servicio**: Creación escalable de tokens y controles de acceso granulares en API, S2S y OneLink.
* **API de registro de auditoría con retención ampliada**: Obtén visibilidad a largo plazo de la actividad de la plataforma e integra eventos de auditoría en tu pila de monitoreo.
* **Aprovisionamiento SCIM**: Automatiza y centraliza el control de acceso de los usuarios a través de tu proveedor de identidad.
* **Lista de permitidos de IP para login:** Evita el acceso no autorizado y garantiza que solo se pueda iniciar sesión en el dashboard de AppsFlyer desde redes e IP de confianza

### Compara los paquetes estándar y Enterprise-Grade:

| Función | Paquete estándar | Paquete de seguridad de nivel empresarial |
| --- | --- | --- |
| [Inicio de sesión único (SSO)](/docs/enterprise-grade-security-package#accordion-item) | Login SSO (solo para clientes existentes) | SSO SAML 2.0 con aprovisionamiento SCIM para usuario automatizado y gestión de roles |
| [Gestión de tokens](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Administra hasta 2 tokens por tipo (API, S2S o OneLink) | Gestiona varios tokens por tipo (hasta 30) con permisos granulares |
| [Acceso al registro de auditoría](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | Acceso solo por UI, retención de datos de 90 días | Acceso por UI y API, retención de datos de 180 días |
| [Gestión de usuarios basada en roles (RBAC)](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Hasta 10 roles personalizados | Hasta 50 roles personalizados |
| [Lista de IPs permitidas](/docs/enterprise-grade-security-package#ip-allowlist) | Lista de permitidos de IP para APIs | Lista de permitidos de IP para login y API para mejorar la seguridad |
| monitoreo de seguridad 24/7 | Incluidos | Incluidos |
| Autenticación multifactor | Incluidos | Incluidos |

<div id="multitoken-management-with-restrictions" />

<Accordion title="Gestión de múltiples tokens con restricciones">

Crea y gestiona hasta **30 tokens** por tipo (API, S2S, OneLink) con **restricciones por servicio** para mejorar la escalabilidad, la seguridad y el control sobre los tokens.

#### Características principales

* Los administradores pueden crear hasta **30 tokens por tipo**, frente a los 2 tokens del paquete estándar, lo que da soporte a equipos más grandes y flujos de trabajo complejos.​
* Asigna permisos de acceso específicos por servicio a los tokens de API para restringir el acceso a operaciones sensibles.​
* Los tokens se pueden revocar o rotar sin interrumpir integraciones ni automatizaciones.
* Restringe un token a una aplicación concreta para que solo pueda acceder a datos o realizar acciones de esa aplicación.
* Simplifica la colaboración con equipos internos y Partners externos mediante permisos específicos por token.

> 📄 **Ejemplo**
>
> Crea dos tokens para ayudar a mantener el acceso con privilegios mínimos y evitar la exposición accidental de datos.
>
> **Token de acceso solo a datos agregados:** Crea un token que acceda únicamente a datos agregados. Este token no podrá acceder a raw data ni realizar acciones como cambios de configuración. Usa este token para equipos de analítica o usuarios de agencia con acceso de solo lectura.
>
> **Token de acceso solo a configuración:** Emite un token que permita a los equipos internos gestionar la configuración, pero que no les permita extraer datos. Esto aísla las capacidades de administración del acceso a los datos.
>
> **Token de acceso específico de la app:** Crea un token que funcione solo para una app. Usa este token cuando un equipo interno, un partner externo o una automatización deban acceder solo a una aplicación específica.

> 📘 **Advertencia**
>
> Para obtener información general sobre los tokens estándar, consulta <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">administrar los tokens de AppsFlyer</Anchor>.

#### Cómo acceder a los tokens y controlarlos

**Para crear un token restringido**

1. Desde la barra superior, abre el menú de la cuenta (desplegable de la dirección de correo electrónico) -> **Centro de seguridad.**
2. Ve a la página de **Administración de tokens**.
3. Haz clic en **Crear token**.
4. Selecciona el tipo de token:
   * API
   * S2S
   * OneLink
5. Para los **tokens de API**, selecciona uno o varios servicios en el desplegable **Restricción de acceso**.  
   El acceso es binario: acceso total o ninguno.
6. Selecciona el tipo de restricción:
   1. Restricción de servicio: selecciona uno o varios servicios en la lista desplegable **Restricción de acceso**.
   2. Restricción de aplicación: selecciona la aplicación a la que puede acceder el token.
7. Haz clic en **Save**

**Gestionar tokens**

Para gestionar tus tokens, desde la barra superior abre el menú de la cuenta (desplegable de la dirección de correo electrónico) -> **Centro de seguridad -> Administración de tokens**.

Desde aquí, podrás:

* Ver metadatos del token: nombre, tipo, restricciones, creación/caducidad
* Eliminar tokens individualmente
* Monitorizar la actividad de los tokens en los registros de auditoría

> 📘 **Advertencia**
>
> Los tokens no se pueden editar. Para cambiar el acceso, elimina el token y vuelve a crearlo.

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="API de registro de auditoría y retención ampliada">

Esta función mejora las capacidades actuales del registro de auditoría, ya que incorpora una API para consumir registros de auditoría y amplía la retención de datos de 90 a 180 días. Ideal para equipos que necesitan acceso a largo plazo a los registros de acciones de los usuarios o integrar eventos de auditoría en herramientas externas de monitoreo como SOC y SEIM.

#### Características principales

* Accede a los registros de auditoría mediante programación con una API específica
* Conserva los registros durante un máximo de **180 días**, frente a los 90 días de los registros de auditoría estándar
* Filtra y exporta datos para cumplimiento, seguridad o uso operativo
* Usa tokens específicos del servicio para aislar el acceso a los registros
* Exporta datos a herramientas SIEM, dashboards o almacenamiento en la nube

> 📘 **Advertencia**
>
> Para obtener información general sobre Audit log estándar, consulta <Anchor target="_blank" href="/marketers/es/docs/audit-log">Standard audit log</Anchor>.

### **Cómo acceder a Audit log a través de la API**

Para usar la API de Audit log:

1. Desde la barra superior, abre el menú de la cuenta (desplegable de la dirección de correo electrónico): **Centro de seguridad.**
2. En la **Audit log** sección, haz clic **Ver audit log.**
3. Ve a la página **Token Management**.
4. Usa uno existente o crea un **token de API** nuevo.
5. En **Access restriction**, selecciona el servicio **Audit log**.
6. Usa el token para autenticar solicitudes en el endpoint de la API de Audit log.

> 📘 **Advertencia**
>
> Asegúrate de guardar tu token de API de forma segura. No se puede recuperar después de crearlo.

</Accordion>

<div id="accordion-item" />

<Accordion title="SSO y aprovisionamiento SCIM">

El aprovisionamiento SCIM mejora las capacidades de SSO de AppsFlyer al automatizar la gestión del ciclo de vida de los usuarios directamente desde tu proveedor de identidad (IdP), como Okta, Entra ID (Azure), OneLogin, JumpCloud o IdP autogestionados compatibles con acceso basado en atributos. Esto permite a las organizaciones incorporar, actualizar o desactivar usuarios sin intervención manual.

Al sincronizar usuarios mediante SCIM, mantienes un control total sobre los permisos de acceso en tiempo real. Combinado con SAML 2.0 SSO, esto forma una solución completa de gestión de identidades y accesos para clientes enterprise.

#### **Características principales**

* Crea automáticamente usuarios en AppsFlyer en función de los registros del proveedor de identidades (IdP).
* Los cambios en los roles o el estado de los usuarios en el IdP se reflejan al instante en AppsFlyer.
* Utiliza **SAML 2.0** para un SSO seguro y **SCIM** para el aprovisionamiento; es compatible con IdP líderes como Okta y Azure AD.

#### **Cómo configurar el aprovisionamiento SCIM**

Para empezar a usar el aprovisionamiento SCIM en AppsFlyer, debes:

1. [Configura SSO con tu IdP](/docs/enterprise-grade-security-package#configurar-sso)
2. [Habilitar SCIM](/docs/enterprise-grade-security-package#habilitar-scim)

#### Configurar SSO

Para configurar SSO, debes:

* <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">Configurar la plataforma IdP</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">Configurar SSO en AppsFlyer</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">Probar la configuración de SSO</Anchor>

#### Habilitar SCIM

> 📘 **Advertencia**
>
> Para habilitar SCIM, primero debes configurar SSO.

Para habilitar SCIM, debes seguir estos pasos:

* Sigue las [instrucciones de configuración del IdP](/docs/enterprise-grade-security-package#enlaces-de-instrucciones-del-idp)
* Configura las [conexiones SCIM](/docs/enterprise-grade-security-package#conexiones-scim)
* Añade los [atributos SCIM](/docs/enterprise-grade-security-package#atributos-scim)
* Añade [roles](/docs/enterprise-grade-security-package#roles)
* Añade [el espacio de nombres externo](/docs/enterprise-grade-security-package#external-namespace)

#### Enlaces de instrucciones del IdP

##### A continuación encontrarás las instrucciones para los IdP. <Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">Okta</Anchor>, <Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>, <Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">OneLogin</Anchor> y <Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">JumpCloud</Anchor>

#### Conexiones SCIM

En las conexiones SCIM, debes completar los siguientes campos:

| **Nombre de campo** | **Valor** |
| --- | --- |
| URL base del conector SCIM (endpoint de SCIM) | https://hq1.appsflyer.com/api/scim/v2 |
| Campo de identificador único para los usuarios | userName |
| Método de autenticación: cabecera HTTP llamada "Authorization" | Bearer &lt;<Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Tu token de API de AppsFlyer</Anchor>> |

#### Atributos SCIM

| **Attribute** | **Tipo** | **Requerido** | **Nombre de campo** | **Espacio de nombres externo** | **Description** |
| --- | --- | --- | --- | --- | --- |
| Rol | cadena | ✅ | rol | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>Asigna al usuario un rol predefinido o personalizado.</li><li>Consulta a continuación la lista de roles de AppsFlyer que debes introducir</li></ul> |
| Permitir el acceso a todas las aplicaciones futuras | Booleano | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Si se habilita, al usuario se le concederá acceso automáticamente a las nuevas apps. |
| App ID permitidos | cadena | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Lista de App ID separados por comas. Déjalo vacío para todas las apps o establécelo en "None" para no permitir ninguna app. |

#### Roles

Los roles deben coincidir con los <Anchor target="_blank" href="/marketers/es/docs/user-management#roles-tab">roles de AppsFlyer</Anchor>. La tabla siguiente muestra los roles actuales de AppsFlyer y sus valores. Se pueden añadir roles personalizados. Si usas JumpCloud, consulta las [limitaciones](/docs/enterprise-grade-security-package#limitaciones) que aparecen a continuación.

| **Nombre para mostrar** | **Valor** |
| --- | --- |
| Administrador | administrador |
| Administrador de equipo | team\_manager |
| Responsable de marketing | marketing\_lead |
| marketing | marketing |
| Marketing limitado | marketing\_limited |
| Contribuyente | desarrollador |
| Contabilidad | contabilidad |
| de la nube | seguridad |
| Garantía de calidad | quality\_assurance |
| Rol personalizado | [introduce el valor del rol personalizado] |

#### Limitaciones

| **Limitación** | **Description** |
| --- | --- |
| **JumpCloud - atributos personalizados** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">Los atributos personalizados no son compatibles</Anchor>. Como alternativa, asigna el campo Rol al campo compatible Dirección laboral. Consulta <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">el soporte de SCIM de JumpCloud</Anchor>. |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="Lista de IP permitidas para el login">

La lista ampliada de IP permitidas mejora la seguridad al evitar accesos no autorizados y garantizar que solo las redes de confianza puedan interactuar con la plataforma. Esta función es especialmente valiosa para empresas que aplican políticas de seguridad estrictas o gestionan el acceso remoto.

#### Características principales

* Reduce los ataques al bloquear intentos de login desde IP desconocidas.
* Permite especificar direcciones IP o rangos para garantizar que solo los usuarios y las redes autorizados puedan acceder a la plataforma.
* Ideal para organizaciones que usan VPN o requieren controles de acceso más estrictos.

#### Agregar IP a la lista

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección **Lista de IP permitidas para el login**, haz clic **Administrar la lista de IP permitidas**.
3. Agrega IP manualmente o mediante la carga de un CSV.
   1. Si las agregas manualmente, introduce la dirección IP o el rango CIDR y haz clic en **Agregar IP a la lista**.
      1. Ejemplos: `192.168.1.1`, `185.114.120.140`
      2. Para introducir un rango de direcciones IP, usa este formato: `185.114.120.1/32`  
         (donde `185.114.120.1` es la primera dirección del rango y `185.114.120.32` es la última dirección del rango).
4. Las IP añadidas se mostrarán en el lado derecho, en **Ver tus IP en la lista de IP permitidas**.
5. Haz clic en **Guardar lista**.

> 🚧 **Dos puntos (:)**
>
> * Asegúrate de que las direcciones IP o los rangos que añadas sean correctos. Si introduces datos incorrectos, es posible que no puedas acceder a tu cuenta.
> * La lista de permitidos debe contener al menos una dirección IP o un rango antes de que puedas guardarla y activarla, y puedes añadir hasta 100 direcciones IP o rangos a la lista de permitidos.
> * Después de hacer clic en Guardar lista, las restricciones de IP se aplicarán a partir de tu próximo inicio de sesión.

#### Eliminar IP de la lista

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección **Lista de IP permitidas para el login**, haz clic **Gestionar la lista de IP permitidas**.
3. Las IP añadidas se mostrarán a la derecha, en **Ver tus IP en la lista de IP permitidas**.
4. Haz clic en el icono de la papelera junto a la dirección IP que deseas eliminar.
5. Asegúrate de guardar tus cambios haciendo clic en el **Guardar lista** botón.

</Accordion>

<div id="frequently-asked-questions-about-our-security-package" />

<Accordion title="Preguntas frecuentes sobre nuestro paquete seguridad">

#### ¿Qué es el paquete de seguridad de nivel empresarial de AppsFlyer?

Escala segura con capacidades de seguridad avanzadas que van más allá de las protecciones estándar. Obtén SSO con aprovisionamiento SCIM, controles de acceso granulares, registros de auditoría ampliados y herramientas de cumplimiento diseñadas para líderes de seguridad empresarial y TI.

#### ¿Para quién está diseñado el paquete de seguridad de nivel empresarial?

Responsables de seguridad empresarial y TI que se preparan para auditorías, equipos de compras y jurídicos de sectores regulados que evalúan proveedores de SaaS, y administradores de plataformas que gestionan requisitos de acceso complejos en múltiples equipos e integraciones.

#### ¿Cómo trabajo el aprovisionamiento SCIM?

Automatiza la gestión del ciclo de vida del usuario conectándote directamente con tu proveedor de identidad. SCIM sincroniza automáticamente el acceso y los roles de usuarios, gestiona el onboarding y offboarding instantáneo, y elimina la administración manual de cuentas y los riesgos de acceso.

#### ¿Qué estándares de cumplimiento tiene este soporte?

Soporte para requisitos de auditoría SOC2, ISO 27001 y GDPR con retención de registro de auditoría de 180 días, documentación de acceso integral e integración SIEM en tiempo real para monitoreo continuo y verificación de cumplimiento.

#### ¿Cuántos roles y tokens API puedo crear?

Crea hasta 50 roles personalizables adaptados a la estructura de tu organización y hasta 30 restricciones específicas del servicio o de la aplicación. Aislar acceso para diferentes integraciones y funciones laborales manteniendo los principios de menos privilegios.

#### ¿Puedo integrarme con mis herramientas de seguridad existentes?

Sí. Transmite datos de auditoría directamente a tus herramientas SIEM y seguridad mediante la transmisión de registros basada en APIs. Permite el monitoreo en tiempo real, detección de anomalías y respuestas de seguridad automatizadas dentro de tu infraestructura SOC existente.

#### ¿Qué restricciones de red puedo aplicar?

Control de acceso a la plataforma mediante listas de IP permitidas y restricciones geográficas. Define redes y ubicaciones de confianza para evitar accesos no autorizados y, al mismo tiempo, admite situaciones de trabajo remoto y asegura la colaboración de los partners.

#### ¿Cuánto tiempo se conservan los registros de auditoría?

Acceso a pistas de auditoría completas con retención de registros de 180 días que capturan la interacción de cada plataforma. Obtén una visibilidad completa de las acciones del usuario, llamadas a la API y patrones de acceso para investigaciones exhaustivas de cumplimiento e investigaciones de seguridad.

#### ¿Esto reemplaza las funciones de seguridad estándar?

N.º El paquete de seguridad de nivel empresarial agrega capacidades avanzadas además de las funciones de seguridad estándar. Obtén controles, automatización y visibilidad mejorados al tiempo que mantienes todas las protecciones de seguridad existentes.

#### ¿Con qué rapidez puedo implementar estos controles de seguridad?

Implementa controles de seguridad empresarial rápidamente mediante una perfecta integración SSO y un aprovisionamiento SCIM automatizado. La mayoría de las organizaciones pueden implementar funciones principales en cuestión de días, manteniendo la continuidad operativa y la productividad del usuario.

</Accordion>

<div data-zendesk-anchors="intro=introducci%C3%B3n h_01JRA2GVNZCDW8C9VW6GH3G4KE=introducci%C3%B3n compare-the-standard-and-advanced-packages=compara-los-paquetes-est%C3%A1ndar-y-enterprise-grade h_01JVS101KETCVDMT1B2WZM89NF=compara-los-paquetes-est%C3%A1ndar-y-enterprise-grade h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions key-features=caracter%C3%ADsticas-principales h_01JQXRDEMJF2NT73FP1TFJG63Z=caracter%C3%ADsticas-principales h_01JVRZRXPD4AC1GAMJ2HKC1R9E=ejemplo h_01JVRZ0ACA19TGC9WJCZ562B70=advertencia how-to-access-and-control-tokens=c%C3%B3mo-acceder-a-los-tokens-y-controlarlos h_01JQXSE4TTYXTWCKXDHB20KJ1Z=c%C3%B3mo-acceder-a-los-tokens-y-controlarlos h_01JVRZ9X0D5V765FTXHVHMR807=advertencia-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=caracter%C3%ADsticas-principales-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=caracter%C3%ADsticas-principales-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=advertencia-2 how-to-access-the-audit-log-via-api=c%C3%B3mo-acceder-a-audit-log-a-trav%C3%A9s-de-la-api h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=c%C3%B3mo-acceder-a-audit-log-a-trav%C3%A9s-de-la-api h_01JVRZ69C2JYY9SK12SEVG3KXF=advertencia-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=caracter%C3%ADsticas-principales-2 h_01JV9W8DTENC21GS0380Q9DP8T=caracter%C3%ADsticas-principales-2 how-to-set-up-scim-provisioning=c%C3%B3mo-configurar-el-aprovisionamiento-scim h_01JV9W8DTFCE7Z0MQP96MK7BQC=c%C3%B3mo-configurar-el-aprovisionamiento-scim sso-set-up=configurar-sso h_01JV9W8DTFHJME1J1JKKJ3NA6C=configurar-sso enable-scim=habilitar-scim h_01JV9W8DTG50YYPQ9RS91K2CJ4=habilitar-scim h_01JVRZ3MC8J0B1E66A47GM5WYZ=advertencia-4 idp-instruction-links=enlaces-de-instrucciones-del-idp h_01JV9WBJCPQ0X5SKVVNK4TBYRR=enlaces-de-instrucciones-del-idp h_01JV9WTJ33KMJGZGM9P5PRK917=a-continuaci%C3%B3n-encontrar%C3%A1s-las-instrucciones-para-los-idp-okta-entra-id-azure-onelogin-y-jumpcloud scim-connections=conexiones-scim h_01JV9WBNC51WYW03RKWHBTP0AG=conexiones-scim scim-attributes=atributos-scim h_01JV9WBS928Z7WKJ2A2CFSWNT4=atributos-scim h_01JV9WBX3JHEMAG62JCASYXB59=roles limitations=limitaciones h_01JV9DMY0Y3795TAT3Q1E3PZRM=limitaciones h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=caracter%C3%ADsticas-principales-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=caracter%C3%ADsticas-principales-3 adding-ips-to-the-list=agregar-ip-a-la-lista h_01K35NHF44511J17KCXTE073QB=agregar-ip-a-la-lista h_01K3DGBBVYY08KVYS60F2MYDCW=dos-puntos- removing-ips-from-the-list=eliminar-ip-de-la-lista h_01K35PGV6Y84JR4CZJ0KGQNWZS=eliminar-ip-de-la-lista h_01K85MXJJ7A9ZTS3PSY2Q0ZDGZ=frequently-asked-questions-about-our-security-package what-is-appsflyers-enterprisegrade-security-package=qu%C3%A9-es-el-paquete-de-seguridad-de-nivel-empresarial-de-appsflyer h_01K85MZT9TDAV684V6PBBFGPTX=qu%C3%A9-es-el-paquete-de-seguridad-de-nivel-empresarial-de-appsflyer who-is-the-enterprisegrade-security-package-designed-for=para-qui%C3%A9n-est%C3%A1-dise%C3%B1ado-el-paquete-de-seguridad-de-nivel-empresarial h_01K85N0D7WVGH94HT1B7NY4KTZ=para-qui%C3%A9n-est%C3%A1-dise%C3%B1ado-el-paquete-de-seguridad-de-nivel-empresarial how-does-scim-provisioning-work=c%C3%B3mo-trabajo-el-aprovisionamiento-scim h_01K85N0ZV1CMH5VANHQCEGENAW=c%C3%B3mo-trabajo-el-aprovisionamiento-scim what-compliance-standards-does-this-support=qu%C3%A9-est%C3%A1ndares-de-cumplimiento-tiene-este-soporte h_01K85N1KB8VSR1Y44YJ7CJD4C2=qu%C3%A9-est%C3%A1ndares-de-cumplimiento-tiene-este-soporte how-many-roles-and-api-tokens-can-i-create=cu%C3%A1ntos-roles-y-tokens-api-puedo-crear h_01K85N26X17PGVN4C6108A47TB=cu%C3%A1ntos-roles-y-tokens-api-puedo-crear can-i-integrate-with-my-existing-security-tools=puedo-integrarme-con-mis-herramientas-de-seguridad-existentes h_01K85N2QW51KDHKE4CQE7VJQHE=puedo-integrarme-con-mis-herramientas-de-seguridad-existentes what-network-restrictions-can-i-apply=qu%C3%A9-restricciones-de-red-puedo-aplicar h_01K85N37KPK5XTFRRGW62CCN4M=qu%C3%A9-restricciones-de-red-puedo-aplicar how-long-are-audit-logs-retained=cu%C3%A1nto-tiempo-se-conservan-los-registros-de-auditor%C3%ADa h_01K85N3SVXVC6TD85V1PQ4EF2D=cu%C3%A1nto-tiempo-se-conservan-los-registros-de-auditor%C3%ADa does-this-replace-standard-security-features=esto-reemplaza-las-funciones-de-seguridad-est%C3%A1ndar h_01K85N4BCQ3NCH1G2P0EFWE3TQ=esto-reemplaza-las-funciones-de-seguridad-est%C3%A1ndar how-quickly-can-i-implement-these-security-controls=con-qu%C3%A9-rapidez-puedo-implementar-estos-controles-de-seguridad h_01K85N4VR1FBESRN1QDRYF077A=con-qu%C3%A9-rapidez-puedo-implementar-estos-controles-de-seguridad" />
