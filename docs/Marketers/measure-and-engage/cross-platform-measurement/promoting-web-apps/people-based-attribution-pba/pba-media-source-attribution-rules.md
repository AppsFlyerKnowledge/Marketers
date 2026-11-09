---
title: Reglas de atribución de fuentes de medios de PBA
metadata:
  keywords:
    - media source
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-09-03T07:30:08Z'
  edited_at: '2026-08-12T12:11:19Z'
  id: 360002386997
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360002386997
---
> **De un vistazo:** Mide el impacto de los esfuerzos de marketing para impulsar el tráfico efectivo del sitio web. Qué fuentes de medios, tipos y canales son responsables de las visitas y los eventos de conversión. Métricas disponibles a nivel anuncio.

<Image align="center" alt="Touchpoints_us-en.png" src="https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png" />

<div id="website-visits-and-web-events" />

## Visitas al sitio web y eventos web

* **Reconocimiento de una visita:** PBA registra una visita según las [reglas de reconocimiento de visitas.](/docs/pba-media-source-attribution-rules#visit-recognition-rules)
* **Atribución de visitas**
  * Para determinar la fuente de medios responsable de atraer a un usuario al sitio web, PBA analiza los parámetros de consulta de la URL y los referentes de documentos HTTP recopilados por el SDK web.
  * La determinación de la fuente de medios basada en reglas utiliza los datos recopilados, tal como se detalla en este artículo. De forma similar, también se determinan el tipo de medio y el canal de medios.
  * La visita se registra en <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">PBA raw data</Anchor>.
* **Campaña** la información se extrae de:
  * Parámetros de consulta que utilizan la fuente de medios
  * Gclid (si está disponible) mediante la <Anchor target="_blank" href="/marketers/es/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">integración de anuncios de Google</Anchor>
* **Evento web**
  * Se produce un evento web cuando un visitante realiza una acción en el sitio web, por ejemplo, búsqueda de producto, selección de producto o compra.
  * Los eventos se atribuyen a la visita web no directa más reciente, dentro de una ventana retrospectiva de 30 días.
  * Los eventos se subdividen en:   
    * **Eventos de conversión**: eventos significativos designados por el profesional del marketing. Por ejemplo, compra o registro.
    * **Eventos estándar**: otros eventos.
  * Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/pba-website-attribution-url-best-practices">Mejores prácticas de URL de atribución del sitio web de PBA</Anchor>.

Los Dashboard de PBA y los Reportes de raw data usan las fuentes de medios, los tipos, los canales y las campañas atribuidos.

<Image align="center" alt="MediaSource_us-en.png" src="https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png" />

Para facilitar la comprensión, la tabla siguiente contiene ejemplos de la fuente de medios determinada con su tipo y su canal.

| Nombre de la app | Media Type | Valor de ejemplo: store\_commission |
| --- | --- | --- |
| Directo | Obtenido | Directo |
| <ul><li>Social Facebook</li><li>Social X (anteriormente Twitter)</li></ul> | Propios | Redes sociales |
| <ul><li>Meta Ads</li><li>Anuncios X</li></ul> | Paga | Redes sociales |
| Búsqueda de Google | Obtenido | Búsqueda orgánica |
| Correo electrónico | Propios | Correo electrónico |
| googleadwords\_int | Paga | El valor puede tener hasta 4 dígitos. |
| usatoday.com | Obtenido | Referencia |

<div id="determining-the-media-source" />

## Determinación de la fuente de medios

PBA determina la fuente de medios, el tipo de medio y el canal de medios de forma jerárquica. Esto significa determinar la regla de fuente de medios pertinente y la fuente de medios. Después, se determinan el tipo de medio y el canal.

<div id="media-source-rules" />

<Accordion title="Reglas de fuente de medios">

Las reglas de fuente de medios que se muestran en la siguiente tabla se clasifican de mayor a menor prioridad:

<Table>
  <thead>
    <tr>
      <th>
        Regla de fuente de medios
      </th>
      <th>
        Resolución de la fuente de medios
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Evitar la autoatribución
      </td>
      <td>
        Para evitar atribuir eventos al propio sitio web (autoatribución) y a otros dominios relacionados, se utiliza una lista de <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#domain-exclusion">exclusión de dominios</Anchor>. La lista consta de:

        * Dominio principal: lo determina la URL de la aplicación web incluida en el paquete de marca
        * Dominios internos: dominios que forman parte de la marca
        * Dominios externos: se excluyen automáticamente las pasarelas de pago y los sitios de procesamiento de pagos que configures, así como algunos dominios, como PayPal y Stripe, configurados por AppsFlyer
      </td>
    </tr>
    <tr>
      <td>
        PID
      </td>
      <td>
        Se resuelve con el valor pid de la URL. En el caso de algunas SRN, el pid se resuelve con el nombre comercial de las SRN para mantener la coherencia y la claridad. Por ejemplo, pid=facebook\_int se resuelve como Facebook Ads y twitter\_int se resuelve como Twitter.
      </td>
    </tr>
    <tr>
      <td>
        ID de clics
      </td>
      <td>
        Las principales ad networks, como Google, usan ID de clic para etiquetar automáticamente las campañas. Los ID de clic se resuelven de la siguiente manera:

        * **gclid:** <Anchor target="_blank" href="https://support.google.com/searchads/answer/7342044?hl=en">ID de clic de Google</Anchor> se resuelve como *googleadwords\_int*. ¡Atención! *La solución GCLID no cuenta con soporte oficial de Google, que podría dejar de ofrecerla en el futuro.*
        * **dclid**: el ID de clic de DoubleClick se resuelve como *doubleclick\_int.*
        * **msclkid:** <Anchor target="_blank" href="http://help.ads.microsoft.com/apex/index/3/en/60000">ID de clic de Bing</Anchor> se resuelve como *bingsearch\_int*.
      </td>
    </tr>
    <tr>
      <td>
        Parámetros UTM
      </td>
      <td>
        **Reglas personalizadas de UTM**

        | utm\_source | utm\_medium | Nombre de la app |
        | --- | --- | --- |
        | * | * correo electrónico, mail, e-mail<br />* ¡Atención! Si utm\_medium contiene uno de estos valores, se ignora la utm\_source. | Correo electrónico |
        | Google | cpc/ppc/paidsearch/search | googleadwords\_int |
        | Google | cpm/display/banner/video/listing | doubleclick\_int |
        | dfa / dbm | Cadena | doubleclick\_int |
        | facebook | cpc/ppc/cpm/cpa/paidsocial/paid-social | Facebook Ads |
        | bing | cpc | bingsearch\_int |
        | yahoo / gemini | cpc/display/listing | yahoogemini\_int |
        | twitter | cpc | Anuncios X |
        | snapchat | swipe | "snapchat\_int" |
        | pinterest | cpc | pinterest\_int |

        Si no hay ninguna coincidencia de regla personalizada, la fuente de medios se resuelve en el valor del parámetro utm\_source.

        <Anchor target="_blank" href="https://en.wikipedia.org/wiki/UTM_parameters">Información sobre los parámetros UTM</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Referente
      </td>
      <td>
        El referente es la fuente HTTP que envió al usuario al sitio web. La fuente de medios es el nombre de dominio de la fuente de referencia.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="media-source-type" />

<Accordion title="Tipo de fuente de medios">

Los especialistas en marketing suelen segmentar las fuentes de medios web en tres tipos:

* **Pagado:** campañas publicitarias, como banners de display, vídeos y anuncios de búsqueda.
* **Medios propios:** campañas de marketing procedentes de medios propios, es decir, campañas de correo electrónico, publicaciones en redes sociales y blogs.
* **Ganado:** tráfico directo u orgánico procedente de motores de búsqueda, referencias y tráfico directo real.

El tipo de medio se determina consultando la regla de fuente de medios utilizada en combinación con la fuente de medios u otros parámetros.

<table><thead><tr><th>Regla de fuente de medios aplicable</th><th>Nombre de la app</th><th>Media Type</th></tr></thead><tbody><tr><td colspan="1" rowspan="2"><div>PID</div></td><td><p>La regla pid determina si la fuente de medios es: </p><ul><li>Facebook social</li><li>X social (antiguo Twitter)</li><li>SMS</li><li>Blog</li><li>Correo electrónico</li></ul></td><td>Propios</td></tr><tr><td>Cualquier otra fuente de medios</td><td>Paga</td></tr><tr><td>ID de clic</td><td><p><span>Se determina mediante un ID de clic:</span></p><ul><li>gclid</li><li>dclid</li><li>msclkid</li></ul></td><td>Paga</td></tr><tr><td colspan="1" rowspan="2"><div>UTM</div></td><td>Las reglas UTM personalizadas determinan la fuente de medios</td><td>Paga</td></tr><tr><td>Cualquier otra fuente de medios</td><td>Propios</td></tr><tr><td rowspan="2">Referente</td><td><p><span>El valor del dominio de referencia es uno de los siguientes:</span></p><ul><li>googleads.g.doubleclick.net </li><li>tpc.googlesyndication.com</li></ul></td><td><p>Paga</p></td></tr><tr><td><span>Cualquier otra fuente de medios </span></td><td><p>Obtenido</p></td></tr></tbody></table>

</Accordion>

<div id="media-source-channel" />

<Accordion title="Canal de fuente de medios">

El canal de medios se determina según las reglas que se indican aquí.

<table><thead><tr><th>Prioridad</th><th>Regla del canal de medios</th><th>Valores</th><th>Valor de ejemplo: store_commission</th></tr></thead><tbody><tr><td rowspan="4">Prioridad más alta</td><td rowspan="4">La fuente de medios es uno de los valores indicados</td><td>Directo</td><td>Directo</td></tr><tr><td><ul><li>Google Search</li><li>Yahoo Search</li><li>Bing Search</li></ul></td><td>Búsqueda orgánica</td></tr><tr><td><ul><li>facebook</li><li>twitter</li><li>snapchat</li><li>pinterest</li><li>linkedin</li><li>whatsapp</li></ul></td><td>Redes sociales</td></tr><tr><td>Correo electrónico</td><td>Correo electrónico</td></tr><tr><td> </td><td>El tipo de medio es pagado</td><td> </td><td><div>El valor puede tener hasta 4 dígitos.</div></td></tr><tr><td> </td><td>Fuente de medios determinada por el referente</td><td> </td><td>Referencia</td></tr><tr><td>Prioridad más baja</td><td>No coincidió ninguna otra condición anterior</td><td> </td><td>Otro</td></tr></tbody></table>

</Accordion>

<div id="determine-the-campaign" />

<Accordion title="Determinar la campaña">

* Las campañas se determinan mediante: 
  * Parámetros de URL de la campaña, según los parámetros de URL de la fuente de medios.
  * ID de clic de Gclid y uso de <Anchor target="_blank" href="/marketers/es/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Anuncios de Google</Anchor> integración
* Si no se encuentra en la URL el parámetro de campaña correspondiente, no se deriva la campaña.

| Parámetro de fuente de medios utilizado | Parámetro de campaña utilizado |
| --- | --- |
| PID | Los parámetros de fuente de medios de AppsFlyer disponibles en la URL se utilizan para completar los raw data y el dashboard de Atribución web. Parámetros disponibles: af\_c\_id, af\_adset, af\_adset\_id, af\_ad\_id |
| ID de clic: gclid | Obtener mediante la API de Google Ads |
| utm\_source | utm\_campaign |

</Accordion>

<div id="additional-attribution-rules" />

## Reglas de atribución adicionales

<div id="visit-recognition-rules" />

<Accordion title="Reglas de reconocimiento de visitas">

Una visita al sitio web se registra siguiendo las reglas que se indican a continuación y teniendo en cuenta el estado actual de la sesión. Una sesión activa es una sesión con menos de 30 minutos de inactividad.

* No registres una visita si el usuario procede de un dominio <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#domain-exclusion">externo excluido</Anchor>.
* Durante una sesión activa: registra una visita si la carga de la página incluye una fuente de medios.
* Si no hay ninguna sesión activa: registra una visita.
* No hay un tiempo mínimo de visita.

**Reglas de registro de visitas de PBA**

<Image align="center" alt="PBA_-_PBA-vist.png" src="https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png" />

</Accordion>

<div id="data-finalization" />

<Accordion title="Finalización de datos">

* Finalización de datos:
  * Para las instalaciones asistidas por web y la atribución del sitio web, PBA identifica eventos relacionados adicionales durante los primeros 7 días posteriores a la conversión. Esto puede cambiar la fuente de medios identificada como la responsable final de impulsar la conversión.
  * En los reportes de datos sin procesar relacionados, el campo *final\_data* es "false" durante el periodo inicial de 7 días.

</Accordion>

<div data-zendesk-anchors="website-visits-and-web-events=visitas-al-sitio-web-y-eventos-web h_01H936NV7VP8CTE9BZP6D5E7NK=visitas-al-sitio-web-y-eventos-web determining-the-media-source=determinaci%C3%B3n-de-la-fuente-de-medios h_01H936NV7VZHWBDPHFJRFFCPSW=determinaci%C3%B3n-de-la-fuente-de-medios h_01H936NV7V6GMWSCHNDMJ205JS=media-source-rules h_01H936NV7W9ZFMET29GY6JTBGN=media-source-type h_01H936NV7W61DB43D3E1MNEJHN=media-source-channel h_01H936NV7WZYE3EKYZ9PX9ZJXW=determine-the-campaign additional-attribution-rules=reglas-de-atribuci%C3%B3n-adicionales h_01H936NV7WA9WZM4RTQZHD22VV=reglas-de-atribuci%C3%B3n-adicionales h_01H936NV7W323HQMG5E6SQFQEN=visit-recognition-rules h_01H936NV7WSB2FMRBPDN936TWM=data-finalization" />
