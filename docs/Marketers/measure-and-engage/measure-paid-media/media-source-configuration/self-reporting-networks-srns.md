---
title: Redes de autorreporte (SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-08-12T12:19:50Z'
  id: 360001546905
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/360001546905
---
> **En resumen:** Descubre más sobre las redes de autorreporte (SRN): atribución, deep linking, implicaciones para iOS y preguntas frecuentes.

<div id="srns-integrated-with-appsflyer" />

## SRNs integradas con AppsFlyer

| **nombres de SRN reservados** | **Logotipo** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration">Anuncios de Amazon</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">Anuncios de Google</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/google-marketing-platform-display-video-360-dv360-integration">Plataforma de Marketing de Google</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup">Meta Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/snapchat-advanced-srn-integration-setup">Snapchat—SRN Avanzado</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencent Social Ads | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—SRN Avanzado</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Anuncios X</Anchor> | <Image alt="Logotipo_X_Ads.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/yahoo-integration-setup">Yahoo (Oath: Plataformas de Anuncios / Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Japan Yahoo! Anuncios de búsqueda</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Nota:** Las SRNs tienen <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">restricciones para el uso y retención de datos a nivel de usuario.</Anchor>

<div id="attribution" />

## Atribución

A diferencia de las redes no SRN (ad networks), que utilizan enlaces de atribución para reportar eventos a AppsFlyer, las SRNs se autoatribuyen utilizando el ID del dispositivo cuando AppsFlyer notifica sobre una instalación. Para las aplicaciones de iOS, se emplean <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> y el <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">framework de privacidad avanzada agregada</Anchor> para la atribución.

La atribución de AppsFlyer tanto para SRN como para no SRN se fundamenta en dos metodologías:

* Metodologías de último toque y multitoque.
* Logica estándar de atribución de AppsFlyer para secuenciar los datos relevantes de impresiones y clics.

<div id="how-does-attribution-work-with-srns" />

### ¿Cómo funciona la atribución con las SRNs?

Las SRN reportan eventos, como nuevas instalaciones y eventos en la aplicación, a AppsFlyer de la siguiente manera:

* Empleando APIs para comunicarse con proveedores de atribución y medición.
* Cuando los proveedores de atribución de terceros detectan una instalación, consultan la red a través del ID de publicidad.
* Reporte de detalles sobre cualquier clic o impresión de anuncios relevante.

Después de que AppsFlyer realice la atribución, se envían postbacks in-app a la SRN durante el <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention#periodos-de-conservación-de-los-datos-de-partners">período de retención de datos del partner</Anchor>.

<div id="how-does-attribution-work-with-advanced-srns" />

### ¿Cómo funciona la atribución con las SRNs Avanzadas?

Las SRN avanzadas efectúan la atribución de la misma manera que las SRNs. Sin embargo, las SRNs avanzadas también pueden atribuir interacciones cuando no hay un ID de dispositivo (IDFA), utilizando el framework de <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#privacidad-avanzada-agregada">Privacidad Avanzada Agregada</Anchor>. En ocasiones, la atribución se realiza mediante <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#device-id-matching">coincidencia de ID</Anchor> con doble consentimiento y, para algunas SRNs avanzadas, mediante <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">modelado probabilístico</Anchor> a través de la comunicación por API sobre clics e impresiones.

<div id="install-attribution" />

### Atribución de instalación.

Antes de instalar una aplicación, los usuarios potenciales ven e interactúan con varios anuncios. En general, los proveedores de atribución ofrecen a los anunciantes una atribución de último toque, lo que significa que se atribuye una instalación al último clic realizado antes de la instalación efectiva.

Cuando se lanza una aplicación por primera vez:

* AppsFlyer verifica que:
  * La aplicación esté configurada para recibir tráfico de SRNs.
  * El usuario tenga un ID de publicidad.
* Si ambas condiciones se cumplen, AppsFlyer consulta a las SRNs usando el ID de publicidad.
* AppsFlyer realiza la atribución tras considerar las afirmaciones de la SRN.

<div id="install-attribution-examples" />

#### Ejemplos de atribución de instalaciones

<div id="example-a-assisted-attribution" />

<Accordion title="Ejemplo A: Atribución asistida">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Lunes:** La red A informa un clic de usuario.

**Martes:** La red B informa una interacción con video.

**Miércoles:** La red C informa un clic en un anuncio interactivo y, 30 minutos después, se produce una instalación.

**AppsFlyer** atribuye la instalación a la red C y reconoce a las redes A y B por su contribución en la instalación.

AppsFlyer proporciona a los anunciantes datos de asistencia (interacciones sin atribuir que ocurren antes de una instalación). Esto permite a los anunciantes personalizar sus modelos de atribución multitáctil o fraccionada. Para más detalles, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-assisted-installs">Explicación de las instalaciones asistidas</Anchor>.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Ejemplo B: Atribución del último clic">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**La red D** (SRN) informa un clic unos minutos antes de la red C.

**La red C** utiliza la integración de atribución estándar.

**AppsFlyer** atribuye la instalación a la red C, ya que fue donde se realizó el último clic.

</Accordion>

<div id="attribution-windows" />

### Ventanas de atribución

Las ventanas de atribución incluyen la retrospectiva y la view-through. Algunas SRNs cobran a los anunciantes por una instalación basada en el costo por mil impresiones (CPM) y el costo por acción (CPA); estos se basan en clics o impresiones que ocurren durante un período de 1 a 28 días.

**AppsFlyer** asigna la instalación, la actividad, el costo efectivo por instalación (eCPI) y el costo efectivo por acción (eCPA) basándose en la metodología de atribución preferida por el anunciante y las ventanas retrospectivas.

**Los anunciantes** pueden tener que pagar por las instalaciones basadas en ventanas retrospectivas de atribución de SRN y modelos view-through.

* Los anunciantes esperan que la metodología de atribución universal de terceros de AppsFlyer optimice y distribuya su gasto publicitaria.
* ¿Por qué? Porque AppsFlyer informa el eCPI y eCPA reales según los términos definidos por el anunciante.
* Las SRNs pueden beneficiarse a corto plazo, dado que generalmente definen sus propias condiciones de pago. No obstante, los anunciantes corrigen esto usando proveedores de atribución de terceros.

<div id="deep-linking-with-srns" />

## Deep linking con SRNs

Para que los usuarios abran tu aplicación al hacer clic en el enlace, solo necesitas configurar App Links/Universal Links/Esquemas URI. Sin embargo, para realizar deep linking o deferred deep linking a una página o actividad específica de tu app, las SRNs utilizan sus propios métodos, sin involucrar el método de deep linking de AppsFlyer.

Entonces, ¿cómo puedes integrar a tus usuarios y obtener los datos relevantes de las SRNs?

<div id="direct-deep-linking" />

<Accordion title="Direct deep linking">

Cuando un dispositivo de usuario realiza un deep linking, el direct deep linking con SRNs se efectúa sin llamar al método de deep linking de AppsFlyer. En el ejemplo a continuación, los usuarios existentes que hacen clic en un anuncio son redireccionados a la actividad directamente mediante los métodos de Facebook, mientras que los usuarios nuevos obtienen la misma experiencia a través de los datos de conversión de AppsFlyer. Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta Ads utilizan OneLink para crear deep linking</Anchor>

<div id="example" />

> 📄 **Ejemplo**
>
> Jill, el mobile marketer de "greatapp", decide llevar a cabo una campaña de deep linking en Meta Ads, dirigida a un público general. La campaña envía a los usuarios que hacen clic a una actividad "bonus".
> Jack, el desarrollador móvil, incorpora esta lógica tras obtener los datos de conversión:
>
> 1. ¿Tiene su origen en Facebook ("is\_fb=true")?
> 2. Si es así, obtén el valor del parámetro del grupo de anuncios.
> 3. Si el valor contiene la palabra "bonus", dirige al usuario a la actividad "bonus".

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Enlaces profundos diferidos">

A diferencia de los deep linking, los deferred deep linking con SRNs son posibles mediante la API GCD de AppsFlyer.  AppsFlyer recibe los datos de conversión y los pone a disposición de la aplicación en la primera apertura. A los usuarios nuevos que instalan la aplicación después de hacer clic en una campaña de deep linking o retargeting en una SRN se los puede redireccionar dentro de la aplicación al momento del inicio, utilizando los datos de conversión.

Los deferred deep linking son compatibles con Google Ads, Snapchat y TikTok for Business mediante el uso del valor real del deep linking, que se puede consultar a través de GCD usando el campo `af_dp`. En el caso de TikTok for Business, este valor también es accesible desde el campo `deep_link_value`.

Sin embargo, con otras SRNs, los parámetros de deep linking normales de AppsFlyer no forman parte de los datos del deep link. Para utilizar esta información dentro de la aplicación, el desarrollador debe usar lógica adicional basada en los parámetros disponibles, como el nombre de la campaña, del conjunto de anuncios o de anuncios individuales.

</Accordion>

<div id="ios-implications" />

## Implicaciones para iOS

La mayoría de las SRNs son compatibles con SKAdNetwork y tienen la integración necesaria con AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Atribución de SRN en iOS 14.5">

A partir de iOS 14.5, cuando los usuarios dan su consentimiento de la ATT en ambas aplicaciones, tanto del anunciante como del publisher (<Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#doble-consentimiento">consentimiento dual</Anchor>), las instalaciones de SRN, que se registran en el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard de SKAdNetwork</Anchor>, también se muestran en los dashboards tradicionales.

<div id="note" />

> 📘 **Nota:**
>
> * El dashboard tradicional muestra una reducción en las instalaciones atribuidas a SRNs. Al considerar el rendimiento de SRN, utiliza el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard de SKAdNetwork</Anchor>. En general, se anticipa una disminución en las atribuciones de instalaciones de SRN, junto con un aumento correspondiente en instalaciones orgánicas. Sin embargo, para las SRNs avanzadas, el impacto es menor ya que también acreditan interacciones cuando no hay un ID de dispositivo.
> * El dashboard de <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork</Anchor> se actualiza con un retraso de 48 a 72 horas después de las instalaciones.
> * Las instalaciones generadas por los Apple Search Ads (ASA) no se atribuyen en el dashboard de SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Envío de postbacks de eventos a SRNs">

Las SRNs que reciben postbacks de eventos dependen de la inclusión del ID del dispositivo en el postback. Esto permite a las SRNs autoatribuir las acciones de usuarios reportados. Muchos usuarios de iOS 14 no dan su consentimiento, lo que significa que no permiten el acceso a su ID de dispositivo (IDFA). En este caso, deberías esperar lo siguiente:

* Una disminución en el número de postbacks de eventos enviados a SRNs
* Discrepancias en el número de postbacks de eventos entre las SRNs y AppsFlyer, que registra todos los eventos.

<div id="note-1" />

> 📘 **Nota:**
>
> * Si no hay IDFA, los postbacks de instalaciones, aperturas de aplicaciones o eventos internos no se envían a las SRNs. [No obstante, en algunos casos, AppsFlyer envía postbacks a SRNs incluso cuando no hay un ID de publicidad](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid).
> * Las ad networks de clics no se ven afectadas, ya que utilizan sus propios identificadores de transacción, en lugar de identificadores de dispositivos, para autoatribuirse la información de los postbacks de eventos.

</Accordion>

<div id="faq" />

## Preguntas frecuentes

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="¿Cómo funciona el retargeting con SRNs?">

Los clics de retargeting desde redes no SRNs se identifican fácilmente por la existencia del parámetro `is_retargeting=true` en el enlace de atribución de retargeting.  
Para las SRNs, no hay una indicación similar. En su lugar, para permitir la atribución de re-engagements desde SRNs, AppsFlyer utiliza otra lógica:

* Prerrequisitos:
  * En la página de **Configuración de la Aplicación**, activa **Habilitar retargeting**.
  * En la página de **Integraciones Activas**, selecciona la SRN y activa **Retargeting**.
* Con cada apertura de la aplicación, AppsFlyer consulta a la SRN sobre interacciones recientes del ID de dispositivo con anuncios de campañas de la app.
  * Si la SRN responde con detalles de la interacción, AppsFlyer verifica que esta interacción esté dentro del periodo de lookback y supere el tiempo mínimo entre re-engagements.
  * Las interacciones validadas se registran como re-engagements y se atribuyen a la SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="¿Qué es la mala segmentación de SRN?">

Las campañas de SRN deberían dirigirse a una audiencia específica, pero esto no siempre ocurre: No usuarios en campañas de adquisición de usuarios y usuarios existentes en campañas de retargeting.

Si se utiliza una SRN para ejecutar campañas de adquisición de usuarios y retargeting, esto puede llevar a una segmentación incorrecta de los usuarios. Como consecuencia, se paga por tráfico no deseado.

**Escenario:** Una SRN en la plataforma de AppsFlyer está habilitada para una campaña de adquisición de usuarios.

* Tras cada lanzamiento de la aplicación, AppsFlyer consulta a la SRN para verificar si el ID de publicidad (usuario) tuvo una interacción reciente.
* Si la respuesta es sí,
  * SRN responde con el nombre de la campaña.
  * AppsFlyer determina si fue la primera apertura (o no) y atribuye en consecuencia:  
    **Primera apertura**: Se atribuye una nueva instalación a la campaña.  
    **Segunda apertura o posterior**: Un evento de retargeting se atribuye a la campaña.

**Conclusión:** Es un desperdicio obtener eventos de retargeting a partir de una campaña destinada a adquisición de usuarios.

<div id="is-mistargeting-a-problem" />

#### ¿La orientación incorrecta es un problema?

Analistas de AppsFlyer revisaron campañas de **adquisición de usuarios** de Meta Ads durante un mes específico.

* El retargeting estaba habilitado.
* En un 30% de las campañas, al menos un 15% de los usuarios objetivo eran ya usuarios de la aplicación.
* En un 5% de las campañas, al menos un 40% ya eran usuarios de la aplicación.
* **Conclusión: En campañas de adquisición de usuarios SRN, 1 de cada 10 usuarios dirigidos ya es un usuario existente.**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

<div id="solving-the-mistargeting-problem" />

#### Solucionar el problema de orientación incorrecta

**Solución básica:** No incluir usuarios existentes en una campaña de adquisición de usuarios.

* SRN solo se enfocará en nuevos usuarios potenciales.
* **Maximiza los resultados de adquirir nuevos usuarios con el mismo presupuesto**.
* Actualiza la campaña de forma periódica (y manual), por ejemplo, una vez al mes.
* Sin embargo, las brechas de tiempo pueden provocar que los usuarios existentes sean el objetivo de campañas de adquisición durante el primer mes después de instalar una app.

<Anchor target="_blank" href="/marketers/es/docs/audiences-guide">**Audiences**</Anchor>, una característica premium de AppsFlyer, te permite enviar automáticamente, a diario, cualquier segmento de tu base de usuarios a docenas de ad networks.

Investigaciones de AppsFlyer muestran que solucionar problemas de orientación errónea puede tener un impacto significativo en tus esfuerzos de marketing y adquisición de usuarios.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="¿Por qué está vacío el campo de URL original en los reportes de raw data?">

El clic se realiza en el entorno SRN pero sin un enlace de atribución de AppsFlyer. Por lo tanto, los datos de la URL original asociados al clic no están disponibles para AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="El dashboard no muestra los clics e impresiones de la SRN">

El clic se realiza en el entorno SRN pero sin un enlace de atribución de AppsFlyer. Por ende, algunas SRNs no proporcionan datos de clics e impresiones a AppsFlyer.

<Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> proporcionan algunos datos agregados a AppsFlyer.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="¿Pueden las agencias configurar campañas SRN?">

Sí, <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#redes-publicitarias-de-autoinforme">consulta aquí sobre la configuración de SRN por agencias</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="¿AppsFlyer envía postbacks por IDs de publicidad faltantes (IDFA/GAID)?">

Cuando los IDs de publicidad contienen una cadena vacía (“”) o muestran el valor '00000000-0000-0000-0000-000000000000' (IDFAs vacíos), AppsFlyer no envía postbacks para instalaciones, aperturas de aplicaciones o eventos in-app, excepto en los siguientes escenarios:

* Google Ads: Como parte de la integración para la medición de remarketing con Google Ads, cuando un usuario de iOS que no ha dado consentimiento abre la aplicación o realiza un evento dentro de ella, AppsFlyer envía la información del `gbraid` y del evento a Google Ads (para el evento `additional_data_json`).
* Google Ads: En Android, cuando no hay un ID de dispositivo pero el valor de referencia contiene un `gclid` (para instalaciones) o un evento de reactivación incluye un deep link con el parámetro `gclid`, AppsFlyer envía el `gclid` y la información del evento a Google Ads.
* Meta: ID de cookies o de campañas de Facebook (en deep linking o en re-engagements previos) o si está habilitada la opción AEM.
* Snapchat y TikTok (SRN avanzado): Si atribuimos a Snapchat o TikTok a través de PMOD y luego llega un evento in-app vinculado a esa instalación, enviaremos el postback.

Parámetro **Google Ads** `gbraid`: Un identificador agregado generado por Google que identifica un grupo de dispositivos y al que se hace referencia a través del deep link.

**ID de clic de Google (parámetro** `gclid` ): Un parámetro incluido en la URL con los clics en el anuncio, que identifica la campaña y otros atributos relacionados con el clic asociados con el anuncio. Esto se utiliza para el seguimiento de anuncios y la atribución de campañas.

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="¿Los clics e impresiones de las SRNs están disponibles en los reportes de raw data?">

No, los clics e impresiones de las SRNs no se comparten en los reportes de raw data. Si bien los datos de SRNs se utilizan para la atribución, los raw data de clics e impresiones no se incluyen en los reportes. Esto se aplica a todas las SRNs, incluidas TikTok, Snap, Meta y Google.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srns-integradas-con-appsflyer h_01HFM2MET40AFB84AW5N8GKWF3=srns-integradas-con-appsflyer attribution=atribuci%C3%B3n h_01HFM2MET4ZNKEZBT3S74N8CMC=atribuci%C3%B3n how-does-attribution-work-with-srns=c%C3%B3mo-funciona-la-atribuci%C3%B3n-con-las-srns h_01HFM2MET42R6C87XB5RWX9ABJ=c%C3%B3mo-funciona-la-atribuci%C3%B3n-con-las-srns how-does-attribution-work-with-advanced%E2%80%94srns=c%C3%B3mo-funciona-la-atribuci%C3%B3n-con-las-srns-avanzadas h_01HFM2MET4Q6WCSANH18VTGBQX=c%C3%B3mo-funciona-la-atribuci%C3%B3n-con-las-srns-avanzadas install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n h_01HFM2MET4YQGN3GZKTTBRQ4HK=atribuci%C3%B3n-de-instalaci%C3%B3n install-attribution-examples=ejemplos-de-atribuci%C3%B3n-de-instalaciones h_01HFM2MET40Y9V8YGA20CCGVNN=ejemplos-de-atribuci%C3%B3n-de-instalaciones h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=ventanas-de-atribuci%C3%B3n h_01HFM2MET4ZJF290QNE3TPXQMA=ventanas-de-atribuci%C3%B3n deep-linking-with-srns=deep-linking-con-srns h_01HFM2MET4ZA6WD6HX92JNFW7X=deep-linking-con-srns h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=ejemplo h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=implicaciones-para-ios h_01HFM2MET4DGERZJ18A7CEFDS9=implicaciones-para-ios h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=nota h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=nota-1 faq=preguntas-frecuentes h_01HFM2MET49FZ8QHDMA7H92BTE=preguntas-frecuentes h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=la-orientaci%C3%B3n-incorrecta-es-un-problema h_01HFM2MET4C1HMWH715XP42ZAQ=la-orientaci%C3%B3n-incorrecta-es-un-problema solving-the-mistargeting-problem=solucionar-el-problema-de-orientaci%C3%B3n-incorrecta h_01HFM2MET41CDCP8VNGR39YMCK=solucionar-el-problema-de-orientaci%C3%B3n-incorrecta h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />
