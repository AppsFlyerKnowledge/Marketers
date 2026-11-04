---
title: Retención de datos a nivel de usuario
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-11-03T01:57:47Z'
  id: 360006091197
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/360006091197
---
> **En resumen:** Las políticas de retención y uso a nivel de usuario (raw data) están determinadas por AppsFlyer, las leyes pertinentes y las condiciones de uno de SRN ("**Partners**").

<div id="caution" />

> ❗️ **Importante**
>
> AppsFlyer proporciona las explicaciones de restricción de datos, en este artículo, solo con fines informativos.  *Nada de lo que se indica aquí es asesoramiento legal. Se proporciona para tu información y comodidad.*

<div id="data-retention-and-deletion-obligations" />

## Obligaciones de conservación y eliminación de datos

AppsFlyer recibe datos a nivel de usuario de aplicaciones, partners y otras fuentes.

<div id="availability-of-user-level-data-to-advertisers" />

### Disponibilidad de datos a nivel de usuario para los anunciantes

Por lo general, los datos a nivel de usuario se ponen a disposición de los anunciantes a través de herramientas de generación de reportes de raw data si su paquete de suscripción incluye datos de raw data durante un período de acceso de 90 días (consultar <Anchor target="_blank" href="/marketers/es/docs/data-availability-windows">ventanas de disponibilidad de datos</Anchor>). En algunos casos, hay <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">Restricciones de raw data</Anchor>.

<div id="data-retention" />

### Retención de datos

AppsFlyer conserva los datos a nivel de usuario durante un período de retención limitado. Los períodos de retención de raw data varían según el método de entrega y los requisitos del partner. En general:

* El período de retención de **raw data a nivel usuario** se basa en el tipo de integración y los requisitos del partner.
* Los **datos agregados** se conservan durante un máximo de 25 meses.

Antes de que finalice el período de retención, los eventos de usuario se atribuyen a la fuente de medios que trae al usuario. Una vez finalizado el período de retención, los eventos del usuario se atribuyen a orgánico.

El período de retención se determina de acuerdo con lo siguiente:

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">Política de privacidad de los servicios de AppsFlyer</Anchor>
* Según lo indique, exija o permita la ley
* Términos de uso y período de retención de los partners, como se indica en la tabla siguiente.

Ten en cuenta lo siguiente:

* La ventana de acceso y el período de retención pueden diferir.
* AppsFlyer, en algunos casos, puede ampliar la ventana de acceso.
* El período de retención puede variar según el partner que trae el usuario
* Algunos datos a nivel de usuario se atribuyen a la función <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">fuente de medios restringida</Anchor>, lo que significa que los raw data no contienen los datos de atribución. Esto puede ocurrir en los siguientes casos:
  * Política de uso compartido de datos de partner
  * La <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">privacidad avanzada agregada</Anchor> está activada.

<div id="partner-data-retention-periods" />

#### Periodos de conservación de los datos de partners

| SRN/partner | ID de partner (PID) | Después de la instalación, elimina los datos después de [x] meses |
| --- | --- | --- |
| Anuncios de Amazon | amazondsp\_int | 12 |
| Anuncios en la búsqueda de Apple | Anuncios en la búsqueda de Apple | Sin límite |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int, doubleclick\_int | 6 |
| Anuncios de Google* | googleadwords\_int (todos los canales) | 6 |
| Hotstar | hotstar\_int | 6 |
| Anuncios de Meta* | facebook\_int (todos los canales) | 6 |
| Microsoft | microsoftdisplay\_int y bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat* (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>) | "snapchat\_int" | 6 |
| TikTok para empresas* | tiktokglobal\_int | 13 |
| X Ads (anteriormente Twitter) | twitter\_int | 3 |
| Walmart | walmart\_int | 6 |

<div id="note" />

> 📘 **Nota***
>
> En el caso de los SRN, los períodos de retención de esta tabla solo se aplican a los datos proporcionados directamente por el SRN. No se aplican a la atribución realizada mediante los enlaces de atribución W2A de AppsFlyer (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=importante data-retention-and-deletion-obligations=obligaciones-de-conservaci%C3%B3n-y-eliminaci%C3%B3n-de-datos h_01H95FY07TABPC769R7TYGY5DD=obligaciones-de-conservaci%C3%B3n-y-eliminaci%C3%B3n-de-datos availability-of-userlevel-data-to-advertisers=disponibilidad-de-datos-a-nivel-de-usuario-para-los-anunciantes h_01H95FY07T2Q9QAGW5A5S6KP6J=disponibilidad-de-datos-a-nivel-de-usuario-para-los-anunciantes data-retention=retenci%C3%B3n-de-datos h_01H95FY07TXS63FVDJC2NEFXYC=retenci%C3%B3n-de-datos partner-data-retention-periods=periodos-de-conservaci%C3%B3n-de-los-datos-de-partners h_01H95FY07TZ4N0RRJRGJ6FN2EK=periodos-de-conservaci%C3%B3n-de-los-datos-de-partners h_01KRKAWSHH2WFZT9Q5M0FSBBAB=nota" />
