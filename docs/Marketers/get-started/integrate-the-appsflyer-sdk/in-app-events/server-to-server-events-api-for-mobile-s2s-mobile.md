---
title: API de eventos de servidor a servidor para móviles (S2S-mobile)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2026-08-22T00:14:04Z'
  id: 207034486
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/207034486
---
> **At a glance:** Envía eventos desde tus servidores a AppsFlyer para medir los eventos móviles que ocurren fuera de la aplicación.

![S2S_us-en.png](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)

<div id="server-to-server-events-api-for-mobile" />

## API de eventos de servidor a servidor para móviles

Para apps de iOS, a partir de iOS 14, debes enviar el parámetro os (sistema operativo).

La plataforma AppsFlyer atribuye y registra los eventos de las apps móviles enviados por el SDK de AppsFlyer y por las API. Utiliza la API S2S para reportar eventos que ocurren fuera de la aplicación; por ejemplo, cuando un usuario renueva su suscripción mediante la interfaz web. Los eventos S2S, una vez registrados, están disponibles en toda la plataforma, incluyendo paneles, raw data y análisis. Para eventos web de PBA, consulta <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s">Web S2S para PBA.</Anchor>

AppsFlyer completa los eventos S2S con:

* Valores enviados en el mensaje S2S.
* Algunos valores de atribución de instalación de AppsFlyer, como la hora de instalación y la fuente de medios.

Para enviar eventos a través de API, indica a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">instrucciones de API de eventos de servidor a servidor</Anchor>.

<div id="populating-parameters" />

## Completando parámetros

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="Diferencias entre orgánico y no orgánico">

Cuando AppsFlyer procesa eventos S2S dentro de la app, los campos de atribución se rellenan usando el ID de AppsFlyer para identificar el evento de instalación asociado que precedió a los eventos dentro de la app.

Esto significa que algunos datos que AppsFlyer asocia con eventos S2S no orgánicos dentro de la app, no se asocian con eventos S2S orgánicos dentro de la misma.

> 📘 **Note**
>
> **Ejemplo**
>
> Por ejemplo, si comparas reportes de raw data de eventos S2S dentro de la app, observarás que los eventos no orgánicos contienen datos que los orgánicos no tienen.
>
> Los eventos no orgánicos dentro de la app incluyen datos sobre la fuente del medio, la campaña, el tipo de interacción atribuida y el tiempo de dicha interacción.
>
> Mientras que los eventos orgánicos dentro de la app ocurren tras una instalación orgánica. Las instalaciones orgánicas no tienen datos relacionados con la campaña, la fuente de medios, el tipo de contacto atribuido y el tiempo de instalación.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="Asignación del ID de AppsFlyer al ID de usuario del cliente (CUID)">

Es necesario desarrollar lógica de backend para obtener los valores y completar los parámetros. A continuación se muestra cómo obtener el ID de AppsFlyer:

* El ID de AppsFlyer es esencial y se utiliza para atribuir eventos.
* Se genera cuando un usuario instala la aplicación móvil por primera vez.
* Para poder relacionar tu CUID con el ID de AppsFlyer, debes configurar el CUID en la aplicación.

Para facilitar la identificación del usuario que realizó cada evento, implementa el siguiente proceso:

* <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">Configura el ID de usuario del cliente</Anchor> cuando el usuario instale la aplicación.
* Los reportes de raw data de AppsFlyer incluyen el CUID y el ID de AppsFlyer. Utiliza una de las herramientas de entrega de datos o la API Push de AppsFlyer para obtener esto.
* Utiliza los reporte de raw data para hacer coincidir el CUID con el ID de AppsFlyer.
* El ID de AppsFlyer está disponible en el SDK integrado en tu aplicación (Android/iOS).
* Relaciona el ID de AppsFlyer con el ID de usuario del cliente en tus sistemas internos (importante para uso futuro).

Una vez que asignes el ID de AppsFlyer a tu CUID, podrás relacionar al usuario con los eventos realizados. Después, puedes obtener otros valores (valor del evento, moneda del evento, hora del evento, etc.) y enviarlos de servidor a servidor en la aplicación.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="Cómo obtener el ID de AppsFlyer">

`appsflyer_id` es un parámetro obligatorio en los mensajes de eventos de servidor a servidor. AppsFlyer utiliza este parámetro para atribuir el evento al dispositivo original y a la fuente de medios atribuida. Puedes obtener el ID usando uno de los siguientes métodos:

* Desde el dispositivo móvil llamando a la API del SDK de AppsFlyer:

  <Tabs>
  <Tab title="Android nativo">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="iOS nativo">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="React Native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* Desde la plataforma de AppsFlyer, usando uno de los siguientes: <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data?query=pull">Pull API,</Anchor> <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">API Push,</Anchor> exportar <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">raw data de instalación.</Anchor>

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="Marca de tiempo de eventos S2S">

![Diagrama lógico de marca de tiempo](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)

Cuando los eventos S2S llegan en gran cantidad a AppsFlyer, se les asigna una marca de tiempo según los valores de su propiedad `eventTime` y la hora de llegada. La propiedad `eventTime` indica el momento en el que ocurre el evento in-app.

Al llegar, los eventos se marcan con el siguiente criterio de tiempo:

* Si el parámetro `eventTime` no está incluido en el registro del evento, la hora del evento se establece a la hora de llegada del mensaje HTTP.
* Los eventos que llegan antes de las 02:00 UTC se marcan con el valor de `eventTime`. Es decir, para que los eventos se marquen con `eventTime`, deben reportarse el mismo día del evento o al día siguiente antes de las 02:00 UTC.
* Los eventos que ocurrieron el día anterior o antes, y llegan después de las 02:00 UTC, se registran con la hora de llegada (la hora de la llamada a la API).
* Eventos que llegan con un valor `eventTime` futuro (eventTime > hora de llegada):
  * Si el `eventTime` reportado y la hora de llegada están en el mismo día del calendario, el evento se marca con el valor `eventTime`.
  * Si el `eventTime` reportado es para el día siguiente en el calendario, el evento se marca con la hora de llegada.
* Los eventos con un valor `eventTime` no válido se registran con la hora de llegada del mensaje HTTP.

**Ejemplo**

* Se envía un evento con `eventTime` = lunes 21:00.

| Llegada a AppsFlyer | Marca de tiempo de AppsFlyer | Nota |
| --- | --- | --- |
| Martes 01:00 | Lunes 21:00 | Llegó antes del cierre de operaciones. El tiempo se ajusta al valor `eventTime`. |
| Miércoles 09:00 | Miércoles 09:00 | Llegó después del cierre de operaciones. La hora se ajusta a la hora de llegada. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="Envío de ingresos negativos">

Se pueden enviar eventos con un valor de ingresos negativo. Por ejemplo, si se cancela una compra. El parámetro `af_revenue` puede adoptar valores negativos para registrar este tipo de situaciones.

Si rellenas `af_quantity`, es posible que quieras rellenarlo con un valor negativo en función de la lógica de tu sistema. AppsFlyer no hace uso de `af_quantity`.

</Accordion>

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<Accordion title="Inclusión del agente de usuario y la dirección IP en eventos S2S">

Al enviar eventos S2S al endpoint `metaweb_int`, la carga útil debe incluir los parámetros `ua` (agente de usuario) y `ip` (dirección IP). Meta requiere estos valores para optimizar el rendimiento de la campaña mediante la Conversions API (CAPI).

AppsFlyer incluye `ua` y `ip` automáticamente para los eventos notificados a través del SDK. Para los eventos S2S, los anunciantes deben enviar estos parámetros explícitamente en la carga útil de la solicitud.

</Accordion>

> 📘 **Note**
>
> **Nota**
>
> Para ser medido en <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">Incrementality</Anchor>, los eventos S2S deben incluir el ID de publicidad en su payload (IDFA para iOS, GAID para Android).

<div id="increasing-the-volume-of-data-transactions" />

## Aumentar el volumen de transacciones de datos

Con el uso de un escalado gradual, AppsFlyer puede gestionar un alto volumen de transacciones por segundo (TPS) utilizando soluciones de auto-escalado. Por ejemplo:

* Comienza con 10.000 transacciones por segundo (TPS) y escala de forma gradual, en intervalos mínimos de 1 minuto.
  * 00:00:00 - enviar 10K TPS (línea base)
  * 00:01:00 - aumentar a 12K TPS
  * 00:02:00 - aumentar a 14K TPS
  * 00:03:00 - aumentar a 16K TPS
  * 00:04:00 - aumentar a 18K TPS
  * …
* Implementa un mecanismo de reintento cuando se reciban errores.

<div id="troubleshooting" />

## Solución de problemas

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="Los eventos no se muestran en el dashboard">

* Endpoint: Asegúrate de que el endpoint usado sea correcto.
* Verifica que la carga útil incluya los parámetros obligatorios. Consulta [aquí](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid).
* Asegúrate de que el ID de AppsFlyer que usas para disparar el evento sea un appsflyer\_id real y esté vinculado a una instalación de aplicación válida. Consulta [aquí](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id).
* Los eventos S2S no permiten múltiples eventos en una sola solicitud S2S. Cada evento debe enviarse por separado.
  * Los eventos pueden enviarse de manera asincrónica para facilitar el tiempo de respuesta.
* En el dashboard general, el rango de fechas se refiere a la fecha de instalación de la aplicación (LTV) y no a la fecha del evento.
  * Asegúrate de seleccionar el rango de fechas adecuado.
  * Asegúrate de que el rango de fechas del dashboard se corresponda con la fecha de instalación del dispositivo (appsflyer\_id) y no con la fecha del evento.
* En los reporte de raw data de eventos, el rango de fechas se refiere a la fecha del evento y no a la de instalación.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="Los eventos no incluyen ingresos">

Si envías eventos S2S y sus ingresos no se registran, asegúrate de que el JSON enviado esté convertido en cadena. La parte más importante es el parámetro de valor del evento en el JSON. Debe estar convertido en cadena como se muestra en el siguiente ejemplo.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

Si no está codificado como cadena, el valor del evento no se procesa correctamente y los ingresos no se registran.

Los valores de ingresos no deben tener ningún formato. Pueden incluir un punto decimal. No incluyas signos o códigos de moneda ni delimitadores `,`. Los ingresos pueden estar precedidos por un `-`. `-`

* Ejemplos de valores válidos: `123`, `-123.45`, `123.456`
* Ejemplos de valores ilegales: `1,234.56`, `1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="No todos los campos se completan en los eventos S2S.">

Los campos de raw data de los eventos de S2S se rellenan exclusivamente con los valores enviados en la llamada de S2S. Los siguientes campos no pueden informarse a través de la API S2S y, por lo tanto, no se completan para eventos S2S en los reporte de raw data:

* Wi-Fi
* Operador
* Idioma
* Modelo del dispositivo
* Categoría del dispositivo
* Versión de la aplicación: Puedes usar `app_version_name`
* Nombre de la aplicación

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<Accordion title="Los eventos S2S dentro de la aplicación están erróneamente atribuidos como orgánicos.">

Los eventos S2S, como los de inicio de sesión, pueden llegar a AppsFlyer en cuanto se instala la aplicación y se activa el SDK. Sin embargo, si los eventos S2S dentro de la aplicación llegan antes de que AppsFlyer termine de procesar el evento de instalación, lo cual generalmente tarda entre 20 y 30 segundos o más, pueden ser marcados como eventos orgánicos no atribuidos.

Recomendamos introducir un breve retraso antes de enviar los eventos S2S dentro de la aplicación que ocurren inmediatamente después de la instalación a nuestros servidores.

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=api-de-eventos-de-servidor-a-servidor-para-m%C3%B3viles h_01H9Q8KBYGXAA8H4AKKXP8T8DY=api-de-eventos-de-servidor-a-servidor-para-m%C3%B3viles populating-parameters=completando-par%C3%A1metros h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=completando-par%C3%A1metros h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue including-user-agent-and-ip-address-in-s2s-events=h_01_including-user-agent-and-ip-address-in-s2s-events increasing-the-volume-of-data-transactions=aumentar-el-volumen-de-transacciones-de-datos h_01HX77GDZ1CCWN48CN616P860D=aumentar-el-volumen-de-transacciones-de-datos troubleshooting=soluci%C3%B3n-de-problemas h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=soluci%C3%B3n-de-problemas h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events h_01JWV0CS5BFBXDT333794BHFER=S2S_in-app_events_are_wrongly_attributed_as_organic" />
