---
title: Configuración de la Google License Verification Library (LVL)
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2026-08-12T11:54:56Z'
  id: 17329535522961
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Protege tus aplicaciones contra el uso no autorizado agregando la Google License Verification Library (LVL) para manejar todas las comunicaciones relacionadas con licencias con Google Play.

<div id="overview" />

## Visión general

LVL es una biblioteca que puedes agregar a tus aplicaciones (descargable desde el SDK de Android) que maneja toda la comunicación relacionada con las licencias con el servicio de licencias de Google Play.

Esto agrega otra capa de protección, además de los algoritmos de Protect360, al permitir la verificación de que las instalaciones provienen de usuarios reales de Google Play. Esto ayuda a reducir las discrepancias entre la cantidad de instalaciones visibles en Google Play y el dashboard de AppsFlyer.

* LVL está disponible solo para clientes de Protect360. Sin el paquete P360, el módulo no valida licencias.
* LVL evita la pérdida de ingresos derivada del uso no autorizado de la app, garantizando el cumplimiento y protegiendo tu inversión.

El servicio Google Play Licensing determina si el usuario tiene licencia para utilizar una aplicación o no. Google Play considera que los usuarios tienen licencia si son compradores registrados de la aplicación. La licencia es única por aplicación y se puede utilizar para una protección mejorada. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Saber más</Anchor>

El SDK de AppsFlyer recopila los datos del lado del cliente y Protect360 realiza la verificación de la licencia del lado del servidor, bloqueando instalaciones fraudulentas que no pasan la verificación tanto para instalaciones orgánicas como no orgánicas. El "Motivo del bloqueo" que verás en el dashboard y los reportes de Protect360 serán "Bots".

<div id="set-up-lvl" />

## Configuración de LVL

<div id="add-lvl" />

<Accordion title="Proceso de configuración">

Actualmente, este es un proceso manual en el que deberás pasar la siguiente información a tu CSM de AppsFlyer para que puedan agregarla manualmente.

**Para agregar el LVL:**

1. Define una propiedad en el archivo gradle.properties llamada:

   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // p. ej., 6.15.2
   ```
2. Haz referencia a la propiedad de forma dinámica en tu archivo build.gradle:

   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3. Para usuarios de Kotlin DSL:

   ```http
   dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // p. ej., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```

   <div id="note" />

   > 📘 **Advertencia**
   >
   > Puedes definir una variable local en la sección dependencies. Esto hará que las versiones de LVL y del SDK de AppsFlyer coincidan, lo que garantiza que ambos módulos tengan la misma versión.

4. Obtén la licencia de la aplicación y la facturación dentro de la aplicación:  
   Desde la Google Play Developer Console (selecciona la aplicación -> Herramientas de desarrollo -> Servicios y APIs).

   ```http
   Clave pública RSA codificada en Base64
   ```
5. Proporciona a tu CSM la siguiente información:

* Llave pública
* app-id
* versión mínima de la aplicación en la que LVL está integrado
* Una captura de pantalla de su implementación de LVL (Liveness Verification Library)

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Siguientes pasos">

Una vez que recibamos tu solicitud, el equipo de Protect360 configurará la verificación LVL en modo STAGING. En esta etapa, el sistema solo informará los resultados de la verificación LVL internamente para AppsFlyer. Un par de días después comprobaremos nuestros datos.

**Si todo se ve bien:**

* Configuraremos la verificación LVL en modo PRODUCTION y comenzará a bloquear el tráfico.
* El equipo de Protect360 notificará al CSM.

**Si algo no está bien** (como si no vemos información LVL en los eventos de instalación):

* Dejaremos la verificación LVL en modo STAGING.
* Tu CSM recibirá una notificación y te ayudará a solucionar problemas de implementación en la aplicación.

</Accordion>

<div id="setup-process" />

<Accordion title="Probar y solucionar problemas">

Al depurar la aplicación, deberías poder ver información LVL en la carga útil que se envía a AppsFlyer, como en el siguiente ejemplo:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Trabaja con tu equipo de soporte/SDK en caso de que no haya información LVL en el mensaje de instalación.

</Accordion>

<div id="faq" />

## Preguntas frecuentes

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="¿Qué pasa si una aplicación se instala desde una tienda que no sea Google Play?">

La validación LVL no verificará ni bloqueará las instalaciones provenientes de tiendas distintas a Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="¿Cuánto tiempo lleva configurar LVL?">

Una vez que obtenemos la información, se necesitan algunos días hábiles para configurar LVL y verificar los datos. Ver detalles sobre el [proceso de configuración](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="¿LVL afecta la funcionalidad de la aplicación?">

No, la funcionalidad de la aplicación no se ve afectada.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="¿Cuál es la diferencia entre LVL y GP-referrer?">

La verificación de licencia usando LVL difiere de los algoritmos de verificación de referencia de GP ya que LVL maneja la verificación de licencia para la aplicación en sí (licencia por aplicación), mientras que la referencia de GP se usa para obtener la fuente de redirección de la instalación a la tienda Google Play con el instalado URL de referencia del paquete (las marcas de tiempo de cuando ocurrió un clic en la referencia, cuando comenzó la instalación, la versión de la aplicación, etc.). En resumen, mientras que LVL se usa para verificar que el usuario tiene licencia para usar la aplicación, el GP-referrer se usa para verificar que los detalles de la instalación no fueron falsificados.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H7YJ35YKDHJ2MDZSSYKMDCJ4=visi%C3%B3n-general set-up-lvl=configuraci%C3%B3n-de-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=configuraci%C3%B3n-de-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01JGK7NK10ZDD6CM6Y4631FB4Q=advertencia 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=preguntas-frecuentes 01H7YJ35YMR8PBTTSHD77WZ4AE=preguntas-frecuentes 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
