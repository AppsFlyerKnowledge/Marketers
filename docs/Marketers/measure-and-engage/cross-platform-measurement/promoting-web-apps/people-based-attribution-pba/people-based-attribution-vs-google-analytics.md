---
title: La atribución basada en las personas frente a Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T15:01:25Z'
  id: 360001305617
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360001305617
---
> **De un vistazo**: Diferencias entre la atribución basada en las personas (PBA) y Google Analytics.

<div id="pba-compared-to-google-analytics" />

## La PBA en comparación con Google Analytics

La PBA y Google Analytics son soluciones de análisis web y de medición de conversiones. Cada una se centra en diferentes aspectos de la medición. La PBA también ofrece beneficios adicionales.

* La PBA es una autoridad de atribución independiente e imparcial que se centra en la medición de la atribución. La PBA atribuye conversiones e ingresos a fuentes de medios y campañas que atraen a los usuarios a tu sitio web.
* Google Analytics se centra más en el análisis web. Reúne, analiza y agrega datos relacionados con el comportamiento del usuario. Con Google Analytics puedes analizar, por ejemplo, el comportamiento de los usuarios, los embudos y los eventos web.

<div id="benefits-of-pba-over-google-analytics" />

### Beneficios de la PBA por sobre Google Analytics

Los siguientes son los beneficios de la PBA por sobre Google Analytics:

* La PBA incluye:
  * Medición de la web a aplicación. Esta métrica te indica cuántos usuarios se mueven de tu sitio web a tu aplicación. También te indica qué fuentes de medios y campañas atraen a los usuarios a tu sitio web que luego terminan instalando tu aplicación.
  * <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">Raw data de conversiones y eventos</Anchor> que puedes incorporar a tus propios sistemas de Business Intelligence. Esto te brinda la capacidad y el poder de ejecutar tu análisis.

<div id="reasons-for-differences" />

### Los motivos de las diferencias

Si comparas datos de la PBA y de Google Analytics, consulta los siguientes motivos de las diferencias en los datos.

<div id="sdk-implementation" />

#### Implementación de SDK

La forma en que implementas la PBA y Google Analytics podría afectar la recopilación de datos.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics muestra más sesiones y visitantes">

<div id="cause" />

#### Causa

Si Google Analytics se carga cuando los usuarios del SDK web rebotan o cuando los usuarios pasan períodos de tiempo cortos en tu sitio web no se cuentan en la PBA. Esto origina discrepancias en los datos de sesiones y visitantes.

<div id="solution" />

#### SOLUCIÓN

Te recomendamos posicionar el SDK web de modo que se cargue lo antes posible.

Ya sea que cargues <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#integración-del-sdk-web-en-el-sitio-web">el SDK directamente o mediante Google Tag Manager</Anchor>, la carga tardía del SDK puede originar discrepancias significativas.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics muestra más datos para sesiones, campañas y conversiones">

<div id="cause-1" />

#### Causa

El SDK web solo está presente en ciertas páginas. Google Analytics está presente en todas las páginas. Como resultado, Google Analytics recopila datos de todo tu sitio web, mientras que el SDK web solo recopila datos de ciertas páginas. Esto origina discrepancias en los datos de sesiones, visitantes, campañas y conversiones.

<div id="solution-1" />

#### SOLUCIÓN

Implementa el SDK web en todas las páginas de tu sitio web.

</Accordion>

<div id="dashboard-settings" />

### Configuración del panel de control

La configuración del panel de control, como la zona horaria y el filtro de datos, podrían afectar la forma en que se te presentan los datos.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Configuración de zona horaria: discrepancias en los datos">

<div id="cause-2" />

#### Causa

Si la configuración de la zona horaria en Google Analytics es diferente de la de tu panel de control de la PBA, es posible que encuentres discrepancias.

<div id="example" />

> 📄 **Ejemplo**
>
> Tu panel de control de AppsFlyer está configurado para UTC y tu panel de control de GA está configurado para UTC +13. Esto significa que tu panel de control de GA está un día por delante de tu panel de AppsFlyer.
>
> Por lo tanto, los datos que aparecen en el panel de control de AppsFlyer para el 2 de marzo solo aparecen en tu panel de control de GA si eliges el 3 de marzo en el filtro de rango de fechas.

<div id="solution-2" />

#### SOLUCIÓN

Asegúrate de que la configuración de la zona horaria sea la misma tanto en AppsFlyer como en Google Analytics.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Filtros de datos: discrepancias en los datos">

<div id="issue" />

#### Problema

Tanto AppsFlyer como Google Analytics te permiten filtrar datos por fecha, fuentes de medios atribuidas, campañas y eventos. Los diferentes filtros en AppsFlyer y Google Analytics pueden generar diferentes vistas para los mismos datos.

<div id="solution-3" />

#### SOLUCIÓN

Cuando compares datos de los dos paneles de control, asegúrate de que no hayan filtros aplicados al conjunto de datos.

</Accordion>

<div id="conversions-and-events" />

### Conversiones y eventos

Los diferentes modelos de atribución, las ventanas retrospectivas, la forma en que envías los eventos y la configuración de las cookies pueden afectar la recopilación y el procesamiento de datos.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Ventana retrospectiva: discrepancias en la medición de la conversión">

<div id="cause-3" />

#### Causa

Si tienes diferentes ventanas retrospectivas en Google Analytics y la PBA, pueden producirse discrepancias en los datos de atribución.

<div id="solution-4" />

#### SOLUCIÓN

La ventana retrospectiva de la PBA es siempre de 30 días. Asegúrate de establecer una ventana retrospectiva de 30 días en Google Analytics cuando elijas <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">tu modelo de atribución</Anchor>.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Modelo de atribución: discrepancias en la medición de la conversión">

<div id="cause-4" />

#### Causa

Los diferentes modelos de atribución en la PBA y Google Analytics pueden originar discrepancias en los datos de atribución.

<div id="solution-5" />

#### SOLUCIÓN

Google Analytics ofrece <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">modelos de atribución predeterminados</Anchor> entre los cuales puedes elegir. Sin embargo, la PBA opera con un modelo de atribución de ventana retrospectiva de toque indirecto de 30 días. Asegúrate de elegir un último modelo de atribución de toque indirecto en Google Analytics.

</Accordion>

<div id="sending-events" />

<Accordion title="Envío de eventos">

<div id="issue-1" />

#### Problema

Tanto el SDK de Google Analytics como el SDK web te permiten enviar eventos. Si implementas una lógica para enviar eventos a Google Analytics y otra para enviar eventos a la PBA, pueden originarse discrepancias.

<div id="solution-6" />

#### SOLUCIÓN

Cuando envíes eventos, verifica lo siguiente:

* Asegúrate de que el mismo disparador se aplique a ambos.
* Asegúrate de enviar el evento a Google Analytics y a la PBA.

Haz clic <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#principios-de-registro-de-eventos">aquí</Anchor> para obtener información sobre cómo enviar eventos mediante el SDK web.

</Accordion>

<div id="cookies" />

<Accordion title="Cookies">

Tanto la PBA como Google Analytics usan cookies para reconocer a los usuarios.

<div id="cookie-settings-in-google-analytics" />

#### Configuración de cookies en Google Analytics

Aunque se recomienda permitir que el SDK de Google Analytics maneje automáticamente la configuración de cookies, puedes <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">configurar y cambiar la configuración de las cookies</Anchor>. Cualquier cambio en la configuración de las cookies puede originar discrepancias.

<div id="setting-cookie-expiration" />

#### Configuración de la caducidad de las cookies

Google Analytics te permite configurar la caducidad de las cookies. Si configuras la cookie de Google Analytics para que caduque antes que la cookie del SDK web, se pueden originar discrepancias.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Mark es un visitante constante de tu sitio web desde hace más de un año y considera suscribirse al contenido premium.
>
> Tu desarrollador configuró la cookie de Google Analytics para que caduque después de un año. Sin embargo, el SDK web establece que la cookie caduque después de dos años.
>
> Cuando Mark finalmente se suscribe y se registra la conversión, la cookie de Google Analytics ya no es válida y en su lugar se ha establecido otra.
>
> El resultado final es que Google Analytics muestra dos usuarios, ambos son Mark, y solo uno de ellos tiene una conversión asociada. Sin embargo, la PBA muestra un usuario para Mark y el mismo usuario que tiene una conversión asociada.
>
> Esto significa que tu tasa de conversión en Google Analytics es inferior a la de la PBA.

<div id="setting-cookie-subdomain" />

#### Configuración de cookies para subdominios

Google Analytics te permite configurar cookies para subdominios, mientras que la PBA solo establece cookies en el dominio de nivel superior.

<div id="example-2" />

> 📄 **Ejemplo**
>
> Estableces una cookie para el subdominio **store.mywebsite.com**. Sharon visita tu sitio web y luego accede a tu tienda en línea en **store.mywebsite.com**. Google Analytics considera a Sharon **como dos usuarios diferentes**.
>
> Como la PBA solo establece cookies en el dominio de nivel superior **mywebsite.com**, considera a Sharon en **mywebsite.com** y **store.mywebsite.com** como el mismo usuario.
>
> El resultado final es dos usuarios en Google Analytics y un usuario en PBA.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=la-pba-en-comparaci%C3%B3n-con-google-analytics benefits-of-pba-over-google-analytics=beneficios-de-la-pba-por-sobre-google-analytics reasons-for-differences=los-motivos-de-las-diferencias sdk-implementation=implementaci%C3%B3n-de-sdk cause=causa solution=soluci%C3%B3n cause::49d3e519=causa-1 solution::447e7ac9=soluci%C3%B3n-1 dashboard-settings=configuraci%C3%B3n-del-panel-de-control cause::30244d2c=causa-2 solution::f1a0e066=soluci%C3%B3n-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=problema solution::df8f3921=soluci%C3%B3n-3 conversions-and-events=conversiones-y-eventos cause::b346571c=causa-3 solution::4bb14ac9=soluci%C3%B3n-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=causa-4 solution::b2be4a33=soluci%C3%B3n-5 issue::b412f5ba=problema-1 solution::39b4d7d6=soluci%C3%B3n-6 cookie-settings-in-google-analytics=configuraci%C3%B3n-de-cookies-en-google-analytics setting-cookie-expiration=configuraci%C3%B3n-de-la-caducidad-de-las-cookies setting-cookie-subdomain=configuraci%C3%B3n-de-cookies-para-subdominios" />
