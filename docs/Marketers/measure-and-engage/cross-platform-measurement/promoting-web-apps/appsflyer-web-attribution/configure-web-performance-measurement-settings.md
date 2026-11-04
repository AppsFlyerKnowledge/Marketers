---
title: Configurar los ajustes de atribución web de AppsFlyer
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-08-12T12:10:54Z'
  id: 43541863890961
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43541863890961
---
> **De un vistazo:** Configura los ajustes de atribución web para controlar cómo AppsFlyer atribuye las visitas al sitio web, las conversiones y la actividad de los usuarios a las campañas de marketing. Los ajustes incluyen ventanas de atribución, eventos de adquisición de usuarios, reglas de re-engagement y exclusiones de dominio.

<div id="overview" />

## Visión general

Los ajustes de atribución web definen cómo AppsFlyer mide y atribuye la actividad de los usuarios en tu sitio web. Estos ajustes determinan:

* Qué eventos califican como adquisición de usuarios.
* Durante cuánto tiempo se atribuyen los eventos posteriores a las fuentes de marketing.
* Cuándo considerar que los usuarios vuelven (re-engagement) o se reacquieren.
* Qué dominios excluir de la atribución.

<div id="who-should-configure-these-settings" />

### Quién debe configurar estos ajustes

Normalmente, los equipos de marketing y los responsables de crecimiento configuran estos ajustes en función de los objetivos de negocio. Los equipos técnicos pueden participar en la integración del SDK y en la configuración del dominio.

<div id="accessing-web-attribution-settings" />

### Acceder a los ajustes de atribución web

Para acceder a los ajustes de atribución de tu aplicación web:

1. En AppsFlyer, ve a **My Apps**
2. Selecciona tu aplicación web de la lista
3. Ve a **App Settings** > **Attribution**

<div id="quick-reference" />

## Referencia rápida

| Ajustes | Predeterminado | Opciones | Editable | Qué controla |
| --- | --- | --- | --- | --- |
| Nombre de aplicación | Entrada del usuario | 1–100 caracteres | Sí | Nombre visible en AppsFlyer |
| URL completa (dominio principal) | Entrada del usuario | 1–500 caracteres | No | Identificador de la App y dominio principal excluido |
| ID de SDK web | Generado automáticamente | 1–550 caracteres | No | Identificador del SDK para la recopilación de eventos |
| Truemoney | Seleccionado por el usuario | Códigos ISO | Sí | Reportes de ingresos y ROI |
| Zona horaria | Seleccionado por el usuario | Zonas IANA | Limitado | Marcas temporales de los informes |
| Evento de adquisición de usuarios | Primera visita | Tasa del impuesto sobre los ingresos netos | Sí | Cuándo se considera que se ha adquirido un usuario |
| Ventana de lookback (UA) | 30 días. | 1 hora–90 días | Sí | Hasta dónde retroceder para encontrar un punto de contacto de UA |
| Ventana de reengagement | 30 días. | 1 hora–90 días | Sí | Durante cuánto tiempo el retargeting recibe la atribución |
| Ventana de inactividad (re-engagement) | Desactivado | 0–30 días | Sí | Inactividad mínima para retargeting |
| Ventana de atribuciones | Duración | Opciones predefinidas | Sí | Durante cuánto tiempo los eventos se atribuyen a UA |
| Ventana de inactividad (re-acquisition) | 90 días | 1–180 días | Sí | Cuándo se considera que los usuarios han hecho churn |
| Evento de readquisición | Visita | Tasa del impuesto sobre los ingresos netos | Sí | Qué hace que los usuarios que se han dado de baja vuelvan |
| Dominios excluidos | Solo primario | Hasta 100 | Sí | Dominios ignorados para la atribución |

**Restricción:**  
La ventana de inactividad de re-engagement debe ser **menor o igual que** la ventana de inactividad de readquisición. De lo contrario, los usuarios podrían volver a adquirirse antes de cumplir los requisitos para el retargeting.

<div id="basic-settings" />

## **Configuración básica**

La configuración básica de la aplicación web es la siguiente:

* Nombre de aplicación
* URL completa
* ID de SDK web
* Truemoney
* Zona horaria

Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Añadir una aplicación a AppsFlyer</Anchor>.

<div id="user-acquisition-settings" />

## Configuración de adquisición de usuarios

La configuración de adquisición de usuarios (UA) determina cómo AppsFlyer identifica cuándo se adquiere por primera vez un usuario y cómo atribuir esa adquisición a las fuentes de marketing.

<div id="user-acquisition-event" />

<Accordion title="Evento de adquisición de usuario">

El evento que desencadena la adquisición de usuarios. Esta es una acción empresarial importante que define cuándo consideras que un usuario está realmente "adquirido".

<div id="why-customize" />

#### Por qué personalizarlo

De forma predeterminada, la **primera visita** suele representar una señal débil del valor del usuario. Un usuario puede hacer clic en un anuncio por accidente o abandonar de inmediato. Al personalizar esta configuración, te aseguras de que el valor a largo plazo (LTV) se atribuya a la fuente de marketing que impulsó una acción significativa, y no solo un clic por curiosidad.

**Predeterminado:** primera visita (el usuario se adquiere en su primera visita al sitio web)

<div id="common-alternatives-by-industry" />

#### Alternativas habituales por industria

| **industria** | **Evento de UA recomendado** |
| --- | --- |
| Banca/Finanzas | registration o first\_time\_deposit |
| Comercio electrónico | sign\_up o first\_purchase |
| Delivery | first\_order |
| SaaS/Suscripción | inicio\_de\_la\_suscripción |
| Gaming | sign\_up o tutorial\_complete o first\_purchase |

<div id="how-it-works" />

#### Cómo funciona

Si se establece en **primera visita**:

* Los usuarios se adquieren inmediatamente en su primera visita al sitio web.
* La atribución comienza desde la primera visita.

Si se establece en **un evento personalizado** (p. ej., sign\_up):

* Los usuarios entran en un **«período previo a la adquisición»** desde la primera visita hasta que realizan el evento.
* Durante el período previo a la adquisición, los eventos se atribuyen al último punto de contacto no orgánico dentro de la ventana de lookback (atribución de último toque).
* Una vez que se produce el evento de UA personalizado, se crea una **conversión de Adquisición de usuarios** y comienza la atribución a largo plazo.

<div id="example-scenario-ua-event--sign_up" />

#### Ejemplo de escenario (evento de UA = sign\_up):

* **Día 0:** El usuario llega desde un anuncio de Facebook → comienza el periodo previo a la adquisición
* **Día 2:** El usuario llega desde un anuncio de Google → el crédito pasa a Google (último toque)
* **Día 3:** El usuario se registra → la adquisición de usuarios se atribuye al anuncio de Google

**Día 10:** El usuario realiza una compra → la compra se atribuye a Google para la medición del LTV

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="Ventana de lookback (adquisición de usuarios)">

Hasta cuánto tiempo atrás busca AppsFlyer para encontrar el punto de contacto de marketing que impulsó la adquisición de usuarios.

Esta ventana controla durante cuánto tiempo AppsFlyer «recuerda» un punto de contacto de marketing. Si un usuario llega desde un anuncio pero no completa el evento de UA hasta más tarde, esta configuración determina si el anuncio sigue recibiendo el crédito.

**Por defecto:** 30 días

**Rango:** de 1 hora a 90 días

<div id="how-it-works-1" />

#### Cómo funciona

Cuando un usuario realiza el evento de UA (p. ej., sign\_up), AppsFlyer busca dentro de esta ventana el punto de contacto no orgánico más reciente y atribuye la adquisición a esa fuente de marketing.

<div id="example-1-30-day-lookback" />

#### Ejemplo 1 (lookback de 30 días):

* **Día 0:** El usuario hace clic en un anuncio de Facebook y visita el sitio web
* **Día 25:** El usuario vuelve directamente y completa el evento sign\_up
* **Resultado:** La adquisición de usuarios se atribuye a Facebook (dentro de la ventana de lookback de 30 días)

<div id="example-2-window-expired" />

#### Ejemplo 2 (ventana expirada):

* **Día 0:** El usuario hace clic en un anuncio de Facebook y visita el sitio web
* **Día 40:** El usuario vuelve directamente y completa el evento sign\_up

**Resultado:** La adquisición de usuarios se marca como orgánica (fuera de la ventana de lookback de 30 días)

</Accordion>

<div id="re-engagement-settings" />

## Configuración de re-engagement

La configuración de re-engagement controla cómo AppsFlyer atribuye la actividad cuando los usuarios adquiridos regresan a tu sitio web a través de campañas de retargeting.

<div id="reengagement-window-item" />

<Accordion title="Ventana de reengagement">

Cuánto tiempo sigue AppsFlyer atribuyendo eventos a ese punto de contacto de marketing después de una conversión de re-engagement.

Esta configuración determina durante cuánto tiempo las campañas de retargeting reciben crédito por la actividad del usuario. Equilibra el crédito de las acciones de retargeting sin dejar de atribuir el LTV a largo plazo a la fuente de adquisición original.

**Por defecto:** 30 días

**Rango:** de 1 hora a 90 días

<div id="how-it-works-2" />

#### Cómo funciona

Cuando un usuario adquirido vuelve a través de una fuente no orgánica (por ejemplo, un anuncio de retargeting) y cumple los criterios de re-engagement, se crea una **conversión de retargeting**. Los eventos dentro de esta ventana reciben **atribución dual**:

1. **Atribución principal** → Campaña de retargeting
   * Objetivo: dar crédito a la campaña de retargeting
2. **Atribución secundaria** → Fuente de UA original
   * Objetivo: dar soporte a la vista de UA, que mide el valor del ciclo de vida completo del usuario (LTV) desde la adquisición original

<div id="example-within-window" />

#### Ejemplo (dentro de la ventana):

* **Día 0:** Usuario adquirido a través de un anuncio de Facebook
* **Día 50:** El usuario hace clic en una campaña de retargeting por correo electrónico y vuelve (se crea una conversión de retargeting)
* **Día 60:** El usuario realiza una compra de 100 $ (10 días después del retargeting)
* **Resultado - Atribución dual:**
  * **Principal (vista de retargeting):** La campaña de correo electrónico recibe crédito por la compra de 100 $
  * **Secundaria (vista de UA):** El anuncio de Facebook también se registra para 100 $ en el LTV del usuario
* **Reportes:**
  * Vista unificada: muestra la compra atribuida al correo electrónico
  * Vista de retargeting: muestra la compra atribuida al correo electrónico
  * Vista de UA: muestra la compra atribuida a Facebook

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="Ventana de inactividad para re-engagement">

El período mínimo de inactividad del Usuario requerido antes de que un punto de contacto no orgánico pueda generar una conversión de Re-engagement (retargeting).

Evita atribuir conversiones a campañas de retargeting cuando los usuarios ya están comprometidos activamente con tu sitio web. Esto optimiza el presupuesto de retargeting al garantizar que las campañas se dirijan a usuarios realmente inactivos.

**Predeterminado:** Desactivado

**Rango:** de 0 (desactivado) a 30 días

<div id="how-it-works-3" />

#### Cómo funciona

**Cuando está desactivado:**

* Cada punto de contacto no orgánico de un usuario adquirido genera una conversión de retargeting

**Cuando está activado (por ejemplo, 7 días):**

* Solo crea una conversión de retargeting si el usuario ha estado inactivo durante al menos 7 días
* Si el usuario ha estado activo recientemente, la visita se atribuye en su lugar a la fuente de UA original

**Restricción:**

* No puede superar la ventana de inactividad (readquisición)

<div id="example-7-day-inactivity-window" />

#### Ejemplo (ventana de inactividad de 7 días):

* **Día 0:** Usuario adquirido a través de un anuncio de Facebook
* **Día 3:** El usuario visita de forma orgánica
* **Día 5:** El usuario hace clic en un anuncio de retargeting → **no se crea ninguna conversión de retargeting** (solo 2 días de inactividad)
* **Día 15:** El usuario hace clic en un anuncio de retargeting → **se crea una conversión de retargeting** (12 días de inactividad)

</Accordion>

<div id="re-acquisition-settings" />

## Configuración de re-adquisición

La configuración de re-adquisición determina cuándo se considera que los usuarios inactivos han «abandonado» y cómo hacer que vuelvan como usuarios re-adquiridos.

<div id="inactivity-window-reacquisition" />

<Accordion title="Ventana de inactividad (re-adquisición)">

El período de inactividad total tras el cual un usuario se marca como «abandonado». Los usuarios que han abandonado pueden readquirirse, lo que genera una nueva conversión de adquisición de usuarios.

Este ajuste define el umbral de abandono de tu empresa. Determina cuándo se considera que un Usuario está «perdido» y puede ser readquirido, lo que permite que las campañas de recuperación reciban el mérito por recuperar a los usuarios que han abandonado.

**Predeterminado:** 90 días

**Rango:** de 1 a 180 días

<div id="how-it-works-4" />

#### Cómo funciona

**Cuando el usuario se marca como abandonado:**

* El usuario deja de atribuirse a la fuente de UA original para eventos nuevos
* El usuario entra en un estado de "pre-adquisición" (a la espera de ser readquirido)
* Las ventanas de atribución de la adquisición original dejan de aplicarse

**Cuando vuelve un usuario abandonado:**

* Si el usuario realiza el evento de readquisición → se crea una nueva conversión de UA
* La campaña de recuperación recibe el crédito como nueva fuente de adquisición
* Desde la perspectiva de los informes, el usuario se trata como una adquisición completamente nueva

<div id="example-90-day-window" />

#### Ejemplo (ventana de 90 días):

* **Día 0:** Usuario adquirido mediante un anuncio de Google
* **Día 50:** Última actividad
* **Día 140:** Usuario abandonado (90 días inactivo)
* **Día 145:** El usuario hace clic en una campaña de recuperación por correo electrónico

**Día 146:** El usuario realiza el evento de readquisición → **Nueva conversión de UA** atribuida a la campaña de correo electrónico

</Accordion>

<div id="reacquisition-event" />

<Accordion title="Evento de readquisición">

El evento que activa la readquisición de los usuarios perdidos. Solo se puede readquirir a los usuarios perdidos.

Muchos eventos de adquisición de usuarios son acciones que solo pueden realizarse una vez (por ejemplo, sign\_up, first\_purchase) y no pueden producirse dos veces. Esta configuración te permite definir un evento repetible que indica que un usuario perdido ha regresado.

**Predeterminado:** visit (los usuarios abandonados se **readquieren inmediatamente** en su primera visita de regreso)

**Alternativas habituales:** sign\_in o purchase

<div id="how-it-works-5" />

#### Cómo funciona

**Si se establece como un evento personalizado (por ejemplo,** **sign\_in**):

* Los usuarios perdidos deben realizar el evento específico para ser readquiridos
* El usuario puede visitar varias veces antes de que se produzca la readquisición
* Definición más estricta de la readquisición «verdadera».

<div id="example-re-acquisition-event--sign_in" />

#### Ejemplo (evento de readquisición = sign\_in):

* El usuario abandonó después de 90 días de inactividad
* El usuario hace clic en la campaña de recuperación por correo electrónico y visita → Aún no se ha readquirido
* Un día después, el usuario inicia sesión → Se crea una conversión de readquisición, atribuida a la campaña de correo electrónico

</Accordion>

<div id="attribution-window" />

## Ventana de atribuciones

<div id="time-period" />

<Accordion title="Período de tiempo">

El período máximo tras la adquisición de usuarios durante el que AppsFlyer atribuye eventos a esa conversión.

**Predeterminado:** Para siempre

**Opciones disponibles:** Ninguno, 1 día, 7 días, 30 días, 60 días, 90 días, 180 días, 365 días, Para siempre (limitado por la retención de datos)

</Accordion>

<div id="excluded-domains" />

## Dominios excluidos

Dominios que se excluirán de la atribución. Esto evita que AppsFlyer atribuya visitas o eventos cuando los usuarios navegan entre los dominios especificados y tu sitio web.

**Propósito:**

1. **Evita la autoatribución:** Excluye tus propios dominios
2. **Excluye flujos de terceros:** Excluye pasarelas de pago y proveedores de autenticación

<div id="domain-types" />

<Accordion title="Tipos de dominio">

<div id="primary-required-automatic" />

#### PRIMARIO (obligatorio, automático)

* El dominio principal de tu sitio web (configurado durante la creación de la aplicación)
* Se añade automáticamente y no se puede eliminar
* Exactamente un dominio principal por aplicación web
* **Exclusión automática de subdominios:** El dominio principal excluye automáticamente todos sus subdominios
  * Ejemplo: example.com excluye automáticamente shop.example.com, blog.example.com, etc.
* **Impacto de la exclusión:** Sin autoatribución

<div id="internal-optional" />

#### INTERNO (opcional)

* Los otros dominios de tu marca no cubiertos por el dominio principal
* Añade hasta 99 dominios adicionales
* Ejemplo: dominios de nivel superior diferentes, como example.co.uk, example.in
* **Impacto de la exclusión:** Sin autoatribución

<div id="external-optional" />

#### EXTERNA (opcional)

Hay dos tipos de exclusiones de dominios externos:

<div id="external-listed-by-you" />

#### Externo (listado por ti)

* Dominios utilizados directamente por tu sitio web, pero que no forman parte de tu marca
* Entre ellos se incluyen pasarelas de pago, sitios de procesamiento de pagos y proveedores de autenticación
* Añade hasta 99 dominios adicionales
* Ejemplos: auth0.com, okta.com, facebook.com, google.com
* **Impacto de la exclusión:** Se ignoran las visitas

<div id="external-listed-by-appsflyer" />

#### Externo (listado por AppsFlyer)

* Dominios excluidos automáticamente por AppsFlyer:

  **Proveedores de pago**

  * PayPal (checkout de pago)
  * Stripe (checkout de pago)
  * Adyen (checkout de pago)
  * Klarna (checkout de pago)
  * Braintree (pasarela de pago)
  * Square (checkout de pago)
  * Paddle (checkout de pago)
  * Mollie (checkout de pago)
  * Alipay (checkout de pago)
  * Razorpay (checkout de pago)
  * Paytm (checkout de pago)
  * PayU (checkout de pago)
  * Mercado Pago (checkout de pago)
  * Yandex Pay (checkout de pago)
  * Naver Pay (checkout de pago)

  **Inicio de sesión con OAuth y SSO**

  * Inicio de sesión con Google (login de la cuenta de Google)
  * Apple ID (login de la cuenta de Apple)
  * Microsoft (login de la cuenta de Microsoft 365 / Entra)
  * Microsoft Live (login de la cuenta de Outlook/Live)
  * Login de Facebook (solo el dominio de inicio de sesión de Facebook)
  * Login de Yandex (login de la cuenta de Yandex)
  * Login de Kakao (login de la cuenta de Kakao)
  * Login de Naver (login de la cuenta de Naver)
  * Login de LINE (login de la cuenta de LINE)
  * Login de Weixin (inicio de sesión OAuth de WeChat)
  * Login de VK (login de la cuenta de VK)
  * Login de Daum (login de la cuenta de Daum)
* La lista de dominios automáticos no se puede editar
* **Impacto de la exclusión:** Se ignoran las visitas

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="Añadir dominios excluidos">

**Para añadir dominios:**

1. Ve a la configuración de tu aplicación web → Atribución
2. Ve a la sección de Dominios excluidos
3. Haz clic en **Agregar dominio**
4. Introduce el nombre de dominio (por ejemplo, custom-gateway.com)
5. Selecciona el tipo de dominio: Interno o Externo
6. Haz clic en **Save**

**Notas importantes:**

* Las exclusiones entran en vigor en **1 hora**
* Los cambios se aplican **solo de forma prospectiva** (no afectan a los datos históricos)
* Los proveedores de pago habituales y los dominios de inicio de sesión OAuth/SSO se excluyen automáticamente. Consulta la lista completa en [Externo (listado por AppsFlyer)](#externo-listado-por-appsflyer) (no hace falta que los añadas manualmente)

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="Requisitos y validación">

<div id="domain-format" />

#### Formato del dominio:

* Solo nombre de dominio (sin protocolos, rutas ni puertos)
* Máximo 500 caracteres por dominio
* Los protocolos (https://) se eliminan automáticamente y se convierten a minúsculas

<div id="examples" />

#### Ejemplos:

* example.com ✅
* shop.example.com ✅ (pero no es necesario si example.com es el dominio principal)
* https://example.com → example.com ✅ (protocolo eliminado)
* example.com/path ❌ (no se permiten rutas)
* example.com:8080 ❌ (no se permiten puertos)

<div id="limits" />

#### Límites:

* Máximo 100 dominios en total (incluido 1 PRINCIPAL)

</Accordion>

<div id="migrating-from-people-based-attribution-pba" />

## Migración desde la atribución basada en personas (PBA)

<div id="key-differences" />

<Accordion title="Diferencias clave">

| **Aspecto** | **PBA (heredado)** | **Nueva medición del rendimiento web** |
| --- | --- | --- |
| **Nivel de configuración** | Nivel de paquete de marca | Nivel de aplicación web |
| **Evento de UA personalizado** | No disponible | Completamente personalizable |
| **Ventanas de tiempo** | Control limitado | Control total (1 h - de por vida) |

</Accordion>

<div id="migration-steps" />

<Accordion title="Pasos de migración">

1. Crear una aplicación web nueva
   1. Ve a Mis aplicaciones → Añadir aplicación → Selecciona Sitio web
2. Elige el ID del SDK web   
   Reutiliza la clave de desarrollo de PBA existente (recomendado) para evitar cambios de código en tu sitio web.
3. Configura los ajustes   
   Asigna los ajustes de PBA a los nuevos ajustes de atribución web
4. Añade dominios excluidos   
   Asigna los dominios excluidos de PBA (Brand Bundle) a los nuevos ajustes de atribución web

**Nota:** Cada clave de desarrollo de PBA solo se puede asignar a una nueva aplicación web.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01KGPFHN8MKTPX5VYDEV30M9A7=visi%C3%B3n-general who-should-configure-these-settings=qui%C3%A9n-debe-configurar-estos-ajustes h_01KGPFK1RNA7ZTJRACJ6M97EAB=qui%C3%A9n-debe-configurar-estos-ajustes accessing-web-attribution-settings=acceder-a-los-ajustes-de-atribuci%C3%B3n-web h_01KGPFM0DJDMVDXZC2B6G6DVX5=acceder-a-los-ajustes-de-atribuci%C3%B3n-web quick-reference=referencia-r%C3%A1pida h_01KGPFT1W65R724WCNDPBHY3F6=referencia-r%C3%A1pida basic-settings=configuraci%C3%B3n-b%C3%A1sica h_01KGPGJG092S1TEDB1T9JNBASE=configuraci%C3%B3n-b%C3%A1sica user-acquisition-settings=configuraci%C3%B3n-de-adquisici%C3%B3n-de-usuarios h_01KGPGE592EK59XXVKTTFDGX16=configuraci%C3%B3n-de-adquisici%C3%B3n-de-usuarios h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event why-customize=por-qu%C3%A9-personalizarlo h_01KGPHMJWF6Z1VV0KH301TYAS5=por-qu%C3%A9-personalizarlo common-alternatives-by-industry=alternativas-habituales-por-industria h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=alternativas-habituales-por-industria how-it-works=c%C3%B3mo-funciona h_01KGPHN5M5GBBMPBYRMYHB9F0E=c%C3%B3mo-funciona example-scenario-ua-event-sign_up=ejemplo-de-escenario-evento-de-ua--sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=ejemplo-de-escenario-evento-de-ua--sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=c%C3%B3mo-funciona-1 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=c%C3%B3mo-funciona-1 example-1-30day-lookback=ejemplo-1-lookback-de-30-d%C3%ADas h_01KGPHX8JMG7FMRS1MYFYS6JRV=ejemplo-1-lookback-de-30-d%C3%ADas example-2-window-expired=ejemplo-2-ventana-expirada h_01KGPHXT83JHJ6J0APVN7NRJ3E=ejemplo-2-ventana-expirada reengagement-settings=configuraci%C3%B3n-de-re-engagement h_01KGPJ1ZMXXJJNCBB52CHY95Z2=configuraci%C3%B3n-de-re-engagement reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=c%C3%B3mo-funciona-2 h_01KGPJFG3X578XCP5X353RRVR1=c%C3%B3mo-funciona-2 example-within-window=ejemplo-dentro-de-la-ventana h_01KGPJG6WSYX2R0VVQYXXWZSMA=ejemplo-dentro-de-la-ventana h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=c%C3%B3mo-funciona-3 h_01KGPJK3H2JF7PV1ATQB3TE9AX=c%C3%B3mo-funciona-3 example-7day-inactivity-window=ejemplo-ventana-de-inactividad-de-7-d%C3%ADas h_01KGPJKDMY4FRAJSMHE19GGJCA=ejemplo-ventana-de-inactividad-de-7-d%C3%ADas reacquisition-settings=configuraci%C3%B3n-de-re-adquisici%C3%B3n h_01KGPJMJDX83SBA77A7BSRZ87V=configuraci%C3%B3n-de-re-adquisici%C3%B3n h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=c%C3%B3mo-funciona-4 h_01KGPJV8EJR94H1P7GZXMP8HSR=c%C3%B3mo-funciona-4 example-90day-window=ejemplo-ventana-de-90-d%C3%ADas h_01KGPJVHCNBZHD9ZXW288CGG9H=ejemplo-ventana-de-90-d%C3%ADas h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=c%C3%B3mo-funciona-5 h_01KGPJY5PA9907PXBRC2QHNJ6T=c%C3%B3mo-funciona-5 example-reacquisition-event-sign_in=ejemplo-evento-de-readquisici%C3%B3n--sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=ejemplo-evento-de-readquisici%C3%B3n--sign_in attribution-window=ventana-de-atribuciones h_01KGPK8H7P5AT59S0GQ9ZK0F01=ventana-de-atribuciones h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period excluded-domains=dominios-excluidos h_01KGPKA56KQRJKRS54HBR50NJN=dominios-excluidos h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types primary-required-automatic=primario-obligatorio-autom%C3%A1tico h_01KGPKJQ7M82KW5VE9ESYNNFEQ=primario-obligatorio-autom%C3%A1tico internal-optional=interno-opcional h_01KGPKJV9B2BHDR64JD24VHH1X=interno-opcional external-optional=externa-opcional h_01KGPKJZQYZESHHH3D0NA2WC9F=externa-opcional external-listed-by-you=externo-listado-por-ti h_01KGPKK4THXQ88AXT58GZ2MHHE=externo-listado-por-ti external-listed-by-appsflyer=externo-listado-por-appsflyer h_01KGPKK96ZAZSKVPBX60FC888X=externo-listado-por-appsflyer h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation domain-format=formato-del-dominio h_01KGPKKXRA59A4RDY4QE1M0Q66=formato-del-dominio examples=ejemplos h_01KGPKM213203KA8CEBHZ9KJP3=ejemplos limits=l%C3%ADmites h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=l%C3%ADmites migrating-from-peoplebased-attribution-pba=migraci%C3%B3n-desde-la-atribuci%C3%B3n-basada-en-personas-pba h_01KGPKPGSF3VSBTQJR6JN80BF4=migraci%C3%B3n-desde-la-atribuci%C3%B3n-basada-en-personas-pba h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />
