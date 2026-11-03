---
title: Gestión de tokens de AppsFlyer
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
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-09-28T00:07:42Z'
  id: 360004562377
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/360004562377
---
> **En resumen:** Los tokens mejoran la seguridad de los datos. Permiten a los usuarios acceder a los datos a través de las APIs de AppsFlyer o recibir datos de eventos mediante llamadas server-to-server. Los administradores pueden gestionar varios tokens manteniendo la continuidad de los datos. Esto incluye crear, renombrar y eliminar tokens de APIs y de server-to-server según sea necesario.

> 🚧 **Importante:**
>
> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)
>
> * Sólo los administradores pueden ver y gestionar los tokens. Los usuarios de la cuenta no tienen acceso a la página de tokens.
> * Mantén tus tokens seguros, ya que permiten acceder a tus datos. No publiques tokens en repositorios de código públicos.
> * Se recomienda sustituir los cada 180 días.

## Sobre los tokens de AppsFlyer

Se utilizan para permitir a los usuarios acceder a los datos a través de la API de AppsFlyer y las llamadas S2S. Los administradores utilizan los tokens para diversos fines:

* Medidas de seguridad:
  * Sustitución de tokens para abordar problemas de seguridad específicos, como el compromiso de un token o la sospecha de un acceso no autorizado.
  * Sustitución periódica de tokens como parte de las actualizaciones rutinarias de la política de seguridad.
* Gestión de diferentes llamadas a la API
* Pruebas
* Para su uso con determinadas funciones, como la API OneLink

## Cómo llegar a la página de tokens

1. Desde la barra superior, abre el menú de la cuenta (dropdown del correo electrónico) > **Centro de seguridad**.
2. En la sección **Tokens de la API de AppsFlyer**, haz clic en **Administrar tus tokens API de AppsFlyer.** Se muestran los tokens actuales.

## Tipos de token

Existen varios tipos para diferentes fines. Por defecto, se genera un token API para cada cuenta nueva (token API V2). Los administradores pueden crear un máximo de dos tokens para cada tipo, como se detalla en la tabla siguiente.

| Tipo de token | Uso previsto |
| --- | --- |
| <span id="api-token"></span>Token API | Un token JWT (JSON Web Token) utilizado para autorizar llamadas a la API, como Pull API, Cohort API, ROI API y otras. |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> (premium) | Un token único utilizado para la API OneLink, que genera enlaces personalizados para un engagement de usuario óptimo en campañas a gran escala. |
| <span id="s2s-token"></span>Token S2S | Se utiliza para enviar datos mediante llamadas server-to-server. |
| <span id="mcp-token"></span>Token MCP | Se utiliza para autenticar sistemas de terceros o alojados por el usuario con AppsFlyer MCP. |

> 📘 **Nota**
>
> Si vas a integrar una función que requiere un token de API V2 específico (por ejemplo, el <Anchor target="_blank" href="/marketers/es/docs/beta-advanced-security-protect360-module">Advanced Security Module</Anchor>) y ya has alcanzado el límite de dos tokens, puedes reasignar un token de API V2 existente en lugar de solicitar uno nuevo: el mismo token puede servir para varios casos de uso.

## Gestiona tus tokens

Como administrador, puedes gestionar varios tokens: crear, renombrar y eliminar tokens. El uso principal sería sustituir los tokens actuales por otros nuevas. Para ello, primero hay que [crear](#crear-un-token) uno nuevo, implementarlo en los sistemas y, una vez que esté disponible, [eliminar](#borrar-un-token) el antiguo.

### Recuperar tokens

1. En la barra superior, abre el menú de la cuenta (dropdown del correo electrónico) > **Centro de seguridad**.
2. En la sección **Tokens de API de AppsFlyer**, haz clic en **Administrar tus tokens API de AppsFlyer.**
3. Se muestran los tokens disponibles.
4. Copia el token requerido.

### Crear un token

1. En la página [**Tokens**](#cómo-llegar-a-la-página-de-tokens), haz clic en **+ Nuevo token**.
2. Introduce el nombre del token.
3. Selecciona el tipo de token.
4. Haz clic en **Crear token**.

> 📘 **Nota:**
>
> * Los tokens de API V2 están activos inmediatamente después de crearlos.
> * Los tokens de tipo S2S, OneLink y otros pueden tardar hasta 30 minutos en activarse.
>   * Hasta que se complete la activación, el estado del token es **Pendiente**.
>   * Usa el token solo después de que su estado cambie a **Activo**.
> * Asegúrate de implementar el nuevo token en tus sistemas

### Borrar un token

> ❗️ **Advertencia**
>
> * Borrar un token puede provocar fallos en los sistemas que dependen de él.
> * Al eliminar un token, este se elimina de la página de tokens y se rechazan todas las llamadas realizadas con el token anterior.
> * Si deseas reemplazar un token, asegúrate de crear primero un nuevo token, implementarlo, y sólo después de que esté disponible, es decir, que no esté en estado "Pendiente", podrás eliminar el token antiguo.

1. En la página [**Tokens**](#cómo-llegar-a-la-página-de-tokens), haz clic en el icono de edición de tokens del que quieres cambiar el nombre.
2. Debes confirmar la eliminación del token escribiendo "Eliminar token".
3. Haz clic en **Guardar**.

## Aplicaciones del token API V2

Casos prácticos para anunciantes y ad networks que utilizan el token API V2:

### AppsFlyer

| Token API V2 |
| --- |
| <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">Obtener raw data desde la Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Datos agregados de Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/app-list-api-for-app-owners">Obtener lista de aplicaciones</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-api">Cohorte</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">Reportes agregados de SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Copiar la configuración de integración de partners</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Establecer la clave de descifrado del referente de instalación</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">API de ingresos netos</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-management-api">Importar API de audiencia</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/beta-advanced-security-protect360-module">Integración de Advanced Security Module (Android)</Anchor> |

### Red publicitaria

| Token API V2 |
| --- |
| <Anchor target="_blank" href="/partners/es/docs/app-list-api-for-ad-networks">Lista de aplicaciones para ad networks</Anchor> |
| <Anchor target="_blank" href="/partners/es/docs/access-to-aggregated-analytics-tools-for-api-partners">Integración con plataformas de gestión de campañas</Anchor> |
| <Anchor target="_blank" href="/partners/es/docs/protect360-for-integrated-partners#api-de-informes-de-redes-publicitarias-de-protect360">Reportes de Protect360 para partners integrados</Anchor> |
| <Anchor target="_blank" href="/partners/es/docs/incost-api-for-ad-networks">InCost</Anchor> |

## Aplicaciones del token S2S

Casos de uso para anunciantes y anunciantes que utilizan el token S2S:

### AppsFlyer

| Token S2S |
| --- |
| <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">Eventos móviles in-app de la API S2S</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement">API de eventos web S2S</Anchor> |

### Red publicitaria

| Token S2S |
| --- |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-appsflyer-preload-referrer-attribution">Atribución de referencias de precarga de AppsFlyer</Anchor> |

> 📘 **Nota:**
>
> Para la mayoría de los ad networks, la generación de tokens S2S ya no está disponible mediante autoservicio. Como resultado, los administradores no verán la opción para generar un token S2S en la interfaz de usuario. La generación de tokens mediante autoservicio solo está disponible para determinados partners gestionados.

## Aplicaciones para el token de OneLink

Casos de uso para anunciantes que utilizan el token API de OneLink:

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Crea</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">obtén</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">actualiza</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">elimina</Anchor> URLs cortas de OneLink con parámetros personalizados.

## Aplicaciones del token MCP

Consulta el <Anchor target="_blank" href="/marketers/es/docs/beta-appsflyer-mcp">artículo AppsFlyer MCP</Anchor> para ver los casos de uso disponibles para los tokens MCP.

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=importante overview=sobre-los-tokens-de-appsflyer h_01HFY5D0E1H66CEB3KMJQEXV4K=sobre-los-tokens-de-appsflyer reaching-the-tokens-page=c%C3%B3mo-llegar-a-la-p%C3%A1gina-de-tokens h_01HFTT570KF3XM9MBSFYRDYN9S=c%C3%B3mo-llegar-a-la-p%C3%A1gina-de-tokens token-types=tipos-de-token h_01HFBR7KP8BZN7KH0BNJ982WK8=tipos-de-token h_01M36NWJZ03NKZVAC2SCTAWBFX=nota manage-your-tokens=gestiona-tus-tokens h_01HFY5D0E1AF4NYPX31W3VJYQC=gestiona-tus-tokens retrieving-api-tokens=recuperar-tokens h_01HBQN3T2HKEMNC8MSR0THYW2S=recuperar-tokens create-a-token=crear-un-token h_01HFY5D0E1FECQC1HN0EXWMXAV=crear-un-token h_01HFY5D0E1HJFKFPRT8WVNPHDG=nota-1 delete-a-token=borrar-un-token h_01HFY5D0E2B1KXGSFZR0AYAER5=borrar-un-token h_01HFY5D0E2KZYG0J2R7GR1R7W5=advertencia applications-of-the-api-v2-token=aplicaciones-del-token-api-v2 h_01HG64DMW7PYRXBMZN00EQN991=aplicaciones-del-token-api-v2 v20-token%E2%80%94advertiser-apis=appsflyer h_01HBQN7TBASK192P8D7AEWM9P6=appsflyer v20-token%E2%80%94ad-network-apis=red-publicitaria h_01HBQN7TBAWAHEQXMYK9V14G0M=red-publicitaria applications-of-the-s2s-token=aplicaciones-del-token-s2s h_01HG64M8K1PPY2Z2406MC78EEN=aplicaciones-del-token-s2s advertiser=appsflyer-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=appsflyer-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=red-publicitaria-1 ad-network=red-publicitaria-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=nota-2 applications-for-the-onelink-token=aplicaciones-para-el-token-de-onelink h_01JSKCWS5406YQJP3RR9KAXJC9=aplicaciones-para-el-token-de-onelink applications-for-the-mcp-token=aplicaciones-del-token-mcp h_01K9YD2Y9M1C8QDBS5H048XYYD=aplicaciones-del-token-mcp" />
