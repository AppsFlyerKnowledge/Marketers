---
title: Medir sesiones
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2026-08-12T11:57:11Z'
  id: 360000520785
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/360000520785
---
> **En resumen**: Los anunciantes utilizan la métrica de sesiones para medir el engagement de los usuarios de la aplicación durante un período determinado.

<Image alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

## Principios del recuento de sesiones

El número de sesiones, es decir de inicios, realizadas por los usuarios es una métrica importante y se utiliza para medir el engagement del usuario con la aplicación. Está disponible a través de varios reportes y paneles de control. Las sesiones se utilizan para derivar las siguientes métricas:

* Usuarios activos diarios (DAU)
* Usuarios activos mensuales (MAU)
* Retención
* Usuarios fieles que usan la configuración predeterminada de 3 aperturas de la aplicación

**¡Atención!** **Nota:** En el caso de las sesiones orgánicas, la métrica está disponible en los paneles de control Actividad y Cohorte, pero no está disponible en el panel de control General.

### Cálculo de sesiones

La métrica de sesiones se calcula mediante el evento *af\_app\_opened* reportado por el SDK. En el lado del servidor, las 5 primeras sesiones se contabilizan sin tener en cuenta el intervalo de tiempo entre ellas. Un mecanismo de tiempo mínimo entre sesiones regula qué sesiones se cuentan en el lado del servidor.

El *evento af\_app\_opened* se muestra como *launch* en el raw data de las sesiones disponible a través de Data Locker. Las sesiones no están disponibles a través de otras herramientas de reportes. Para facilitar la comprensión, en este artículo usaremos el término *af\_app\_opened*.

**Reporte de sesiones**

El SDK reporta una sesión cuando se produce alguna de las siguientes situaciones:

* Un usuario inicia la aplicación.
* Cuando la aplicación pasa de segundo a primer plano. El desarrollador puede modificar el comportamiento de los reportes llamando a [setMinTimeBetweenSessions.](/docs/measure-sessions#session-reporting-by-the-app-sdk)
* Un reporte de sesiones explícito del desarrollador en aplicaciones de Android. Por ejemplo, esto lo implementan las aplicaciones de utilidades que siempre están en segundo plano.

**Métrica de sesiones**

La métrica de sesiones se cuenta desde la primera sesión. La métrica de sesiones se cuenta después de considerar un mecanismo de tiempo mínimo entre sesiones con una duración predeterminada de 10 minutos, como se describe en el ejemplo siguiente.

## Mecanismo de tiempo mínimo entre sesiones

El mecanismo afecta al recuento de sesiones. **¡Atención!** **Nota:** Ten en cuenta que si el tiempo mínimo entre sesiones es largo, más de una hora, y los usuarios no abren la aplicación muchas veces al día, algunas métricas relacionadas con la sesión, como DAU y retención, pueden verse afectadas. Esto es especialmente cierto en el caso de las aplicaciones en las que los usuarios suelen abrir la aplicación una vez al día. 

<div id="description-and-example" />

<Accordion title="Descripción y ejemplo">

El mecanismo regula qué sesiones se cuentan. Una sesión se cuenta si ha pasado el tiempo mínimo permitido entre sesiones.

El flujo es el siguiente: Se cuenta una sesión → Se inicia un temporizador de cuenta regresiva → No se tienen en cuenta las sesiones reportadas mientras el temporizador está en cuenta regresiva.

**Ejemplo**

Supuesto: El tiempo mínimo permitido entre sesiones es de 10 minutos.

| Caso de ejemplo | Tiempos de reporte de sesiones (número de minutos desde las 00:00) | Número de sesiones contabilizadas | Sesiones ignoradas |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | Ninguno |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="Ajuste del temporizador">

* Valor predeterminado: 10 minutos
* Los valores posibles son:

  * 1-60 minutos
  * 1-24 horas

**Para establecer el temporizador de tiempo mínimo permitido entre sesiones:**

1. En AppsFlyer, en el menú lateral, selecciona **Configuración**> **Configuración de la aplicación**.
2. Configura el **Tiempo mínimo entre sesiones.**
3. Haz clic en **Guardar configuración.**   
   El cambio entra en vigor en el transcurso de una hora.

</Accordion>

## Temas relacionados con las sesiones

<div id="retargeting-sessions" />

<Accordion title="Sesiones de retargeting">

* Las sesiones de retargeting están disponibles a partir del 12 de julio de 2020.
* Las sesiones de retargeting están disponibles en:
  * Retargeting y tipo de vista unificada en el panel de control general.
  * Las vistas de cohorte relevantes, es decir, retargeting y unificadas. 
    * En el caso de la vista unificada, si las sesiones se atribuyen a una fuente de medios de retargeting y de la UA, prevalece la fuente de medios de retargeting y no se muestra la fuente de medios de la UA.
    * Actualización de los datos: Diariamente a las 13:00 UTC.
  * Data Locker: Se pueden habilitar los reportes de sesiones de retargeting; incluyen sesiones de reengagement y de reatribución. 
    * Actualización de los datos: Demora de 6 horas.
* Durante las ventanas de reengagement, las sesiones se atribuyen tanto a la UA como a la fuente de medios de retargeting. Del mismo modo, otros eventos de reengagement en la aplicación tienen <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución</Anchor>.
* En el caso de Google Ads y X Ads, para evitar postbacks duplicados, el evento *af\_app\_opened* se envía una vez.

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="Postbacks de sesiones a partners">

Puedes enviar postbacks de sesiones a partners para que se envíe un <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">postback</Anchor> por cada sesión contada.

* Para enviar el postback: Asigna explícitamente *af\_app\_opened* a un evento de partner. ¡Atención! Nota: En el reporte de raw data de AppsFlyer disponible a través de Data Locker, este evento se refleja como un *inicio.*
* Ten en cuenta que se trata de un evento de gran volumen y que muchos partners no quieren recibirlo.

> 📘 **Nota**
>
> La asignación de `af_app_opened` solo es compatible con los partners que tengan **Enviar sesiones** habilitado.

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="Reportes de sesiones por parte de la aplicación (SDK)">

**Lado de la aplicación:** El SDK envía *af\_app\_opened* cada vez que la aplicación se abre o se pone en primer plano después de considerar la configuración *setMinTimeBetweenSessions* del SDK.

**Lado del servidor:** Las sesiones reportadas por la aplicación se cuentan y registran después de considerar el mecanismo de tiempo mínimo entre sesiones. Las sesiones contadas se atribuyen con las mismas <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">reglas de atribución</Anchor> que otros eventos in-app.

#### **Reportes de sesiones explícitos por parte del desarrollador (solo aplicaciones Android)**

Usa <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession">logSession</Anchor> en Android para reportar explícitamente una sesión. Una llamada equivalente no está disponible en iOS.

* Las aplicaciones que funcionan en segundo plano de forma continua pueden requerir cierta lógica implementada por el desarrollador para reportar las sesiones. Por ejemplo, aplicaciones de utilidad como ahorradores de batería, iniciadores, bloqueos de pantalla y aplicaciones antivirus. Para estos tipos de aplicaciones, considera la posibilidad de reportar una sesión diariamente a medianoche o en algún otro intervalo adecuado para la aplicación.
* En otros casos, es posible que desees contar las sesiones cuando los usuarios realizan alguna acción in-app, como presionar el botón de *borrar memoria*, etc.

#### **Establecer el tiempo mínimo entre inicios de aplicaciones**

En el SDK, establece el tiempo mínimo que puede transcurrir entre dos sesiones para que se reporten por separado.

Usa ***setMinTimeBetweenSessions,*** es decir el evento af\_app\_opened, para controlar la cantidad mínima de tiempo que debe transcurrir entre sesiones para que se reporte cada una de ellas.

* [Predeterminado] cinco segundos. Lo que significa que deben transcurrir al menos 5 segundos antes de que se reporte otra sesión.
* La API permite establecer el tiempo mínimo requerido entre sesiones.

**La referencia del SDK `setMinTimeBetweenSessions`:**

<Tabs>
<Tab title="Android">

Consulta [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions) en la referencia del SDK de Android

</Tab>

<Tab title="iOS">

Consulta [`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions) en la referencia del SDK de iOS

</Tab>

<Tab title="Unity">

Consulta [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions) en la referencia del SDK de Unity

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=principios-del-recuento-de-sesiones h_01HB8NDPNKERK1RR1Y09V2R2CC=principios-del-recuento-de-sesiones sessions-calculation=c%C3%A1lculo-de-sesiones h_01HB8NDPNKFW6S28A3TC7W5J3C=c%C3%A1lculo-de-sesiones minimum-time-between-sessions-mechanism=mecanismo-de-tiempo-m%C3%ADnimo-entre-sesiones h_01HB8NDPNKF32E34M3CBJ6GMP8=mecanismo-de-tiempo-m%C3%ADnimo-entre-sesiones h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=temas-relacionados-con-las-sesiones h_01HB8NDPNKPTJX56Q2SVAB6V6T=temas-relacionados-con-las-sesiones h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=nota h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=reportes-de-sesiones-expl%C3%ADcitos-por-parte-del-desarrollador-solo-aplicaciones-android h_01HB8NTFMR3Y9GHFP3EWMAATHY=reportes-de-sesiones-expl%C3%ADcitos-por-parte-del-desarrollador-solo-aplicaciones-android setting-minimum-time-between-app-launches=establecer-el-tiempo-m%C3%ADnimo-entre-inicios-de-aplicaciones h_01HB8NTMC1JYPDWYG9YC8RNSEQ=establecer-el-tiempo-m%C3%ADnimo-entre-inicios-de-aplicaciones" />
