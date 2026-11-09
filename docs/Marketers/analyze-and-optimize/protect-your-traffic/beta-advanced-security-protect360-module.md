---
title: Beta - Módulo Protect360 de seguridad avanzada
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-11-02T01:04:12Z'
  id: 39145848948625
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/39145848948625
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **De un vistazo:** Refuerza la protección contra el fraude de tu aplicación Android con el módulo de seguridad avanzada. Esta solución en tiempo real detecta y bloquea la suplantación de atribución y el tráfico manipulado antes de que se atribuyan las instalaciones. Diseñado para aplicaciones con mucho tráfico y clientes de Protect360, especialmente para quienes trabajan con afiliados. Puedes configurar el módulo por completo, lo que te permite realizar la configuración inicial y el mantenimiento continuo para adaptarte a los patrones de fraude en evolución y proteger la integridad de los datos.

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> La beta del módulo Advanced Security Protect360 está disponible para todos los clientes de Protect360. Para unirte, contacta a tu CSM.

<div id="what-is-sdk-spoofing" />

## ¿Qué es la falsificación del SDK?

La falsificación del SDK es una táctica avanzada de fraude en la que los atacantes envían solicitudes falsas de instalación y de eventos in-app directamente a los servidores de AppsFlyer, sin instalar ni ejecutar la aplicación en un dispositivo real. El SDK de la aplicación no se hackea ni se modifica. En su lugar, los defraudadores imitan las solicitudes de red que enviaría una aplicación real, haciendo que la actividad parezca legítima.

Para los anunciantes, la falsificación del SDK puede generar instalaciones y engagement que nunca se produjeron, volúmenes de instalación inflados, discrepancias entre AppsFlyer y las cifras de la tienda de aplicaciones, y gasto publicitario desperdiciado.

<div id="about-the-advanced-security-module" />

## Acerca del módulo de seguridad avanzada

El **módulo Advanced Security** es un complemento del paquete Protect360 de AppsFlyer, diseñado para detectar y detener técnicas avanzadas de suplantación de atribución en Android. Al evaluar la actividad de instalación después del primer inicio de la aplicación, pero antes de que se produzca la atribución, el módulo identifica el tráfico sospechoso y evita que las instalaciones fraudulentas afecten a tus métricas de rendimiento.

Esta solución es especialmente valiosa para las aplicaciones que presentan discrepancias entre los datos de la tienda de aplicaciones y la atribución de AppsFlyer, o que gestionan tráfico de afiliados, dos indicadores habituales de fraude de instalación.

**Cómo funciona**

El módulo se activa después del primer inicio de la aplicación (registrado por el SDK), pero antes de que se atribuya la instalación. Para usar el módulo Advanced Security, debes utilizar Android SDK v6.15.2 o una versión posterior.

<div id="prerequisites" />

## Prerrequisitos

Antes de empezar, asegúrate de que tienes lo siguiente:

* **Android SDK v6.15.2 o posterior** integrado en tu app.
* **Un token de API V2** — necesario para la autenticación del repositorio de Maven cuando tu desarrollador integra la dependencia del módulo de seguridad. Consulta <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#aplicaciones-del-token-api-v2">Gestión de tokens de AppsFlyer</Anchor> para saber cómo recuperar o generar uno.
* **Todos los hashes de certificados (SHA-256)** de cada certificado utilizado para firmar tu app (debug y release). Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint">Generar una huella digital SHA256</Anchor>.

<div id="important-1" />

> 🚧 **Importante:**
>
> Si tu cuenta ya ha alcanzado el límite de dos tokens de API V2, no necesitas solicitar uno nuevo: puedes reutilizar un token de API V2 existente para esta integración. Ponte en contacto con tu CSM si tienes preguntas sobre la asignación de tokens.
>
> Para ver todos los pasos de la integración técnica, consulta la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin">guía para desarrolladores del plugin de seguridad de Android</Anchor>.

<div id="set-the-advanced-security-module" />

## Configura el módulo de seguridad avanzada

Configura el módulo de seguridad avanzada para validar que el tráfico in-app procede de las compilaciones firmadas de tu aplicación y para detectar (y, opcionalmente, bloquear) el tráfico falsificado.

<Accordion title="Configura el módulo de seguridad avanzada">

<div id="step-1-open-and-select-an-app" />

#### **Paso 1: abre y selecciona una aplicación**

1. En AppsFlyer, ve a **Settings > Protect360 > Advanced security module**.
2. Haz clic en **Get Started** o en **Add build**.
3. Selecciona la aplicación en la que quieres implementar la solución del módulo Advanced Security.
4. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer

<div id="step-2-add-certificate" />

#### **Paso 2: Añadir certificado**

1. Agrega:
   1. <span class="af-ol-a"></span>Nombre del certificado
   2. Valor del certificado
2. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer

Nota: pide a tu desarrollador todos los [hashes de certificados](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint) utilizados para firmar la aplicación. El módulo de seguridad usa estos certificados para validar que el tráfico procede de tu aplicación, por lo que debes incluir todos los hashes relevantes.

<div id="step-3-excluded-app-versions-from-detection" />

#### **Paso 3: Versiones de la aplicación excluidas de la detección**

* Añade las versiones de la aplicación que deban excluirse de la detección de Advanced Security. Normalmente, serían estas:
  * Versiones lanzadas antes de que se integrara el módulo de Advanced Security.
  * Builds de prueba o heredadas que no incluyen el módulo.

<div id="step-4-build-activation" />

#### **Paso 4: Activación del build**

1. Haz clic en **Activar build**.
2. Tu build pasará a **En curso** hasta que se complete el build. Esto puede llevar 10-15 minutos.
3. Cuando se complete, copia el código haciendo clic en el botón **Copiar código** del build y envíaselo a tu desarrollador para integrarlo en el SDK de la aplicación.

<div id="note" />

> 📘 **Advertencia**
>
> Después de realizar el build, el modo de detección se configura como **Tagged** de forma predeterminada. En este modo, AppsFlyer marca el tráfico sospechoso, pero no lo bloquea. Cuando la versión protegida esté activa, cambia al modo **Implemented** para bloquear el tráfico suplantado. Para obtener más información sobre los modos Tagged e Implemented, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-fraud-protection-studio#modos-de-fps">Modos de FPS</Anchor>.

</Accordion>

<Accordion title="Mantenimiento y actualización de la configuración">

Las técnicas de fraude cambian con el tiempo, y los actores maliciosos pueden intentar aplicar ingeniería inversa a la lógica de detección. Un mantenimiento regular garantiza su eficacia continua.

<div id="when-to-update-the-configuration" />

#### **Cuándo actualizar la configuración**

Actualiza la configuración si detectas lo siguiente:

* Instalaciones o eventos sospechosos que pasan por la detección
* Cambios en los patrones de tráfico
* Nuevas versiones de la app o cambios en los certificados
* Menor eficacia de las protecciones existentes

<div id="what-you-can-update" />

#### **Qué puedes actualizar**

Podrás hacer lo siguiente:

* Añadir o actualizar certificados de la app
* Modificar las versiones excluidas de la aplicación
* Reconstruir y volver a implementar el módulo de seguridad
* Ajustar el modo de detección en función del estado del despliegue

<div id="best-practices" />

#### **Mejores prácticas**

* Revisar periódicamente los insights de seguridad avanzada
* Coordinarse con los desarrolladores antes de lanzar la app
* Actualizar los certificados inmediatamente después de los cambios en la firma
* Reevaluar la configuración periódicamente para adelantarte a los nuevos métodos de fraude

</Accordion>

<div id="data-visibility" />

## **Visibilidad de los datos**

La detección del módulo de seguridad avanzado se refleja en dos lugares:

* Panel de control de Protect360
* Fraud Protection Studio

<Accordion title="Panel de control de Protect360">

La detección del módulo de seguridad avanzado se encuentra en la sección **Atribución falsificada**.

Los datos se dividen en dos KPI y un gráfico.

**KPIs**

* **Atribución falsificada etiquetada**: número de candidatos a instalación detectados por el módulo de seguridad avanzado en modo etiquetado.
* **Atribución falsificada implementada**: número de candidatos a instalación detectados por el módulo de seguridad avanzado en modo implementado y bloqueados.

**Gráfico**

* **Tendencia de atribución falsificada**: reflejo de la detección del módulo de seguridad avanzado a lo largo del tiempo. Este gráfico refleja el estado general de la detección de suplantación a nivel de app/s.

<Image align="center" alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<Accordion title="Fraud Protection Studio (FPS)">

El Advanced Security Module se encuentra en la página de Fraud Protection Studio.

<div id="how-to-access" />

#### Cómo acceder

Para acceder al Advanced Security Module:

1. Envíanos tus comentarios con el mensaje "Envía comentarios a AppsFlyer" y contacta con el equipo de soporte de AppsFlyer.
2. En el menú de la izquierda, ve a Configuración > Protect360 > Fraud Protection Studio.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. Selecciona la tarjeta Advanced Security Module en el menú de la izquierda.

<div id="the-advanced-security-module-page" />

#### La página del Advanced Security Module

<Image align="center" alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

La página del Advanced Security Module se divide en tres secciones.

<div id="detection-status" />

##### Estado de detección

* Muestra el modo de detección. Las dos opciones son implemented y tagged. De forma predeterminada, está configurado como **Tagged**.

Nota: Para cambiar el estado de detección, ponte en contacto con tu CSM.

<div id="top-app-versions-by-detection-status" />

##### Versiones principales de la aplicación por estado de detección

* El gráfico muestra las 5 versiones principales de la aplicación en términos de volumen de instalaciones
  * Cada versión de la aplicación se desglosa por:
    * **Untagged** - Candidatos de instalación que no detectó el módulo de seguridad avanzada.
    * **Tagged** - Candidatos de instalación que detecta el módulo de seguridad avanzada en modo etiquetado.
    * **Blocked** - Candidatos de instalación que detecta el módulo de seguridad avanzada en modo implementado. Todos los candidatos de instalación que se bloqueen no continuarán.

##### Insights

Los insights te ayudan a comprender el desglose del gráfico. Los tres tipos de insights son:

* **Todo el tráfico está bloqueado** - Las versiones de la aplicación que están bloqueadas al 100% pueden indicar que no se han añadido a la lista de exclusión. Por favor, verifica la lista de exclusión de versiones de la aplicación con tu CSM y considera añadir las versiones de la aplicación relevantes.
* **Todo el tráfico está etiquetado** - Es posible que las versiones de la aplicación etiquetadas al 100% no se hayan añadido a la lista de exclusión. Por favor, verifica la lista de exclusión de versiones de la aplicación con tu CSM y considera añadir las versiones de la aplicación relevantes.
* **Tasa alta de detecciones etiquetadas** - Una o más versiones de la aplicación muestran más del 20% de detecciones del módulo de seguridad avanzada en modo etiquetado. Se recomienda encarecidamente que te pongas en contacto con tu CSM para cambiar al modo de detección implementado y obtener los mejores resultados.

</Accordion>

<Accordion title="Preguntas frecuentes">

<div id="what-is-advanced-security" />

#### ¿Qué es la seguridad avanzada?

Advanced Security es una capa de protección adicional para el SDK de AppsFlyer para Android que ayuda a evitar la suplantación de la atribución, un tipo de fraude en el que se reportan instalaciones o eventos falsos aunque ningún usuario real haya instalado ni usado la aplicación.

<div id="what-problem-does-advanced-security-solve" />

#### ¿Qué problema resuelve Advanced Security?

Advanced Security ayuda a evitar instalaciones falsas y actividad in-app causadas por el spoofing que aparecen en AppsFlyer, pero no existen en la tienda de aplicaciones ni en los sistemas de backend. Esto reduce el número inflado de instalaciones, las discrepancias en los datos y el gasto publicitario desperdiciado.

<div id="what-is-attribution-spoofing" />

#### ¿Qué es la suplantación de atribución?

La suplantación de atribución es una técnica de fraude en la que los atacantes generan datos falsos de instalación o de eventos in-app y los envían a AppsFlyer mientras fingen que proceden de tu app. En realidad, no se produce ninguna instalación real de la aplicación ni ninguna actividad del usuario.

<div id="how-does-advanced-security-prevent-attribution-spoofing" />

#### ¿Cómo evita Advanced Security la suplantación de atribución?

Advanced Security verifica que los datos de instalación y de eventos in-app proceden realmente del SDK de tu aplicación añadiendo una firma de verificación única a cada solicitud. AppsFlyer comprueba esta firma para confirmar que los datos son auténticos y no han sido suplantados ni manipulados.

<div id="does-advanced-security-affect-the-app-or-user-experience" />

#### ¿Advanced Security afecta a la aplicación o a la experiencia del usuario?

N.º Advanced Security se ejecuta en segundo plano y no cambia la forma en que los usuarios instalan o usan la aplicación. Todo el procesamiento adicional se realiza entre bastidores y los usuarios no lo perciben.

<div id="who-should-use-advanced-security" />

#### ¿Quién debería usar Advanced Security?

Advanced Security es especialmente relevante para las apps que trabajan en gran medida con redes no SRN o de afiliados, observan discrepancias sin explicación entre las instalaciones de la tienda de aplicaciones y los datos de AppsFlyer, o sospechan de un fraude sofisticado que resulta difícil de detectar con métodos estándar.

<div id="is-advanced-security-available-for-all-platforms" />

#### ¿Advanced Security está disponible para todas las plataformas?

N.º Actualmente, Advanced Security solo está disponible para aplicaciones Android y se ofrece a los clientes premium de Protect360. También es compatible con todos los plugins de AppsFlyer.

<div id="how-do-i-know-advanced-security-is-working" />

#### ¿Cómo sé si Advanced Security está funcionando?

Los resultados de detección se muestran en el dashboard de Protect360 y en Fraud Protection Studio, donde puedes hacer track del tráfico suplantado que se etiqueta o bloquea y revisar las tendencias a lo largo del tiempo.

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=dos-puntos- what-is-sdk-spoofing=qu%C3%A9-es-la-falsificaci%C3%B3n-del-sdk h_01KH8MPFJBSN67PSQXX25NG6ZZ=qu%C3%A9-es-la-falsificaci%C3%B3n-del-sdk about-the-advanced-security-module=acerca-del-m%C3%B3dulo-de-seguridad-avanzada h_01K5C4BCNRE8JWQ9DA20DJ3A07=acerca-del-m%C3%B3dulo-de-seguridad-avanzada h_01K9PRQNEWSECTION0001AB=prerrequisitos prerequisites=prerrequisitos h_01K9PRQNEWSECTION0002AB=importante set-the-advanced-security-module=configura-el-m%C3%B3dulo-de-seguridad-avanzada h_01KHK6M3CTY4YSCRTSMS707S5Z=configura-el-m%C3%B3dulo-de-seguridad-avanzada step-1-open-and-select-an-app=paso-1-abre-y-selecciona-una-aplicaci%C3%B3n h_01KH8XDACWA2C46MEEGFMM6J8M=paso-1-abre-y-selecciona-una-aplicaci%C3%B3n step-2-add-certificate=paso-2-a%C3%B1adir-certificado h_01KH8XDACYBFZJWHZZCD0JSNGJ=paso-2-a%C3%B1adir-certificado step-3-excluded-app-versions-from-detection=paso-3-versiones-de-la-aplicaci%C3%B3n-excluidas-de-la-detecci%C3%B3n h_01KH8XDAD08E1JJVVSV9GY4RAB=paso-3-versiones-de-la-aplicaci%C3%B3n-excluidas-de-la-detecci%C3%B3n step-4-build-activation=paso-4-activaci%C3%B3n-del-build h_01KH8XDAD122D7PWP2367YVNP2=paso-4-activaci%C3%B3n-del-build h_01KH8XJXN717M3GDJNPPMWDBHY=advertencia when-to-update-the-configuration=cu%C3%A1ndo-actualizar-la-configuraci%C3%B3n h_01KH8XDAD3M4RARMK7DS7RA08X=cu%C3%A1ndo-actualizar-la-configuraci%C3%B3n what-you-can-update=qu%C3%A9-puedes-actualizar h_01KH8XDAD46P524Z2H8BBZRAR1=qu%C3%A9-puedes-actualizar best-practices=mejores-pr%C3%A1cticas h_01KH8XDAD5PVKNPW37PMG3NKHH=mejores-pr%C3%A1cticas data-visibility=visibilidad-de-los-datos h_01K5C4BCNTBVDQX8DGTGEAN01T=visibilidad-de-los-datos how-to-access=c%C3%B3mo-acceder h_01K5C4BCNZBS424A4PMS7AR8XG=c%C3%B3mo-acceder the-advanced-security-module-page=la-p%C3%A1gina-del-advanced-security-module h_01K5C4BCP14ARR3JMDPMRWZPTT=la-p%C3%A1gina-del-advanced-security-module h_01K5C4BVN5CQVP8HJG1MBV72AW=estado-de-detecci%C3%B3n h_01K5C4BVN69SK4TBNWPFPWYXPN=versiones-principales-de-la-aplicaci%C3%B3n-por-estado-de-detecci%C3%B3n h_01K5C4BVN6XA4SNP4TK9SSRHS9=insights what-is-advanced-security=qu%C3%A9-es-la-seguridad-avanzada h_01KH9HERVW7QE2JXCGBBC206VW=qu%C3%A9-es-la-seguridad-avanzada what-problem-does-advanced-security-solve=qu%C3%A9-problema-resuelve-advanced-security h_01KH9HERVX8V537KQBSMAR31T8=qu%C3%A9-problema-resuelve-advanced-security what-is-attribution-spoofing=qu%C3%A9-es-la-suplantaci%C3%B3n-de-atribuci%C3%B3n h_01KH9HERVY5G1J5KQV9ZKTHGXX=qu%C3%A9-es-la-suplantaci%C3%B3n-de-atribuci%C3%B3n how-does-advanced-security-prevent-attribution-spoofing=c%C3%B3mo-evita-advanced-security-la-suplantaci%C3%B3n-de-atribuci%C3%B3n h_01KH9HERVZAT11WNX99R2EQCPB=c%C3%B3mo-evita-advanced-security-la-suplantaci%C3%B3n-de-atribuci%C3%B3n does-advanced-security-affect-the-app-or-user-experience=advanced-security-afecta-a-la-aplicaci%C3%B3n-o-a-la-experiencia-del-usuario h_01KH9HERW0XFEGCKGJZA6C44HY=advanced-security-afecta-a-la-aplicaci%C3%B3n-o-a-la-experiencia-del-usuario who-should-use-advanced-security=qui%C3%A9n-deber%C3%ADa-usar-advanced-security h_01KH9HERW00N9M05DSF8998JE0=qui%C3%A9n-deber%C3%ADa-usar-advanced-security is-advanced-security-available-for-all-platforms=advanced-security-est%C3%A1-disponible-para-todas-las-plataformas h_01KH9HERW13WYZYBAGA9XXKW1B=advanced-security-est%C3%A1-disponible-para-todas-las-plataformas how-do-i-know-advanced-security-is-working=c%C3%B3mo-s%C3%A9-si-advanced-security-est%C3%A1-funcionando h_01KH9HERW2CQ76W33ERFTP0FS9=c%C3%B3mo-s%C3%A9-si-advanced-security-est%C3%A1-funcionando" />
