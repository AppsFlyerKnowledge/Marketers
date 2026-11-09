---
title: Mide los engagement view-through
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-08-12T11:57:43Z'
  id: 210084473
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/210084473
---
> **De un vistazo:** Un usuario que ve un anuncio (impresión) y posteriormente instala la aplicación, se atribuye mediante atribución por impresiones.

<div id="overview" />

## Visión general

La atribución por impresiones mide las instalaciones, las reatribuciones y los re-engagements de los usuarios que vieron un anuncio pero no hicieron clic en él.

<div id="view-through-attribution-flow" />

### Flujo de atribución por impresiones

<Image align="center" alt="Retargeting_-_View-through__1_.png" src="https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png" />

<div id="terminology" />

### Terminología

* **Impresión:** la visualización de un anuncio a un usuario, independientemente de cualquier clic u otro engagement de usuario.
* **Instalación**: en este artículo, significa instalaciones, reatribuciones y re-engagements.
* **Atribución por impresiones:** la atribución de instalaciones a una fuente de medios después de que el usuario vea una impresión.

<div id="view-through-attribution-principles" />

### Principios de la atribución por impresiones

* Se admiten tanto la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#device-id-matching">coincidencia de ID de dispositivo</Anchor> como el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">modelado probabilístico</Anchor> (<Anchor target="_blank" href="/marketers/es/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">que debes activar</Anchor>).
* Con el respaldo de los partners que figuran en la [lista de partners de atribución por impresiones](/docs/measure-view-through-engagements#view-vta-partner-list).

Las impresiones son candidatas a la atribución por impresiones mediante los siguientes principios:

* La impresión ocurrió dentro de la ventana retrospectiva por impresiones (predeterminada en 24 horas).
* Si se encuentran varias impresiones, se considera la impresión más reciente.
* Los clics tienen prioridad sobre las impresiones. Esto significa que si hay clics en la ventana retrospectiva por clics, gana el clic más reciente. La impresión más reciente se atribuye como colaborador (asistencia).

<div id="view-through-lookback-window" />

### Ventana retrospectiva por impresiones

* Para no SRN, la duración de la ventana de atribución retrospectiva por impresiones es de 1 a 24 horas. Para SRN, la ventana retrospectiva puede ser más larga.
* Para establecer la ventana:
  * **Redes de publicidad:** establece la duración mediante enlaces de atribución para impresiones configurando el parámetro `af_viewthrough_lookback`. Si el parámetro no está configurado, se utiliza una ventana predeterminada de 24 horas.
  * **SRN**: la ventana es determinada por la SRN. Recomendamos establecer el mismo valor que la SRN en AppsFlyer.

<div id="view-through-attribution-reporting-and-metrics" />

### Métricas y reportes de atribución por impresiones

* **Datos agregados:** las redes de publicidad informan datos agregados de impresiones a AppsFlyer a través de la API o por impresión. Ten en cuenta que cada partner define individualmente el recuento de impresiones y los reportes. Las métricas relacionadas están disponibles en el panel de información general y a través de otras herramientas de reportes. Las métricas disponibles son:
  * Impresiones: Número de impresiones mostradas durante un período determinado.
  * Por impresiones: la cantidad de instalaciones atribuidas mediante la atribución por impresiones.
* **Raw data**:
  * Los datos de nivel de usuario (raw data) de los usuarios atribuidos a través de la atribución por impresiones están disponibles y son similares a los de los usuarios atribuidos por clics. Sin embargo, algunos partners restringen la disponibilidad de estos datos.
  * Los datos de impresiones (similares a los datos de clics) están disponibles.
  * El campo attributed\_touch\_type contiene el valor *impression.*

<div id="view-through-operations" />

## Operaciones por impresiones

<div id="set-impression-links" />

<Accordion title="Establecer enlaces de impresiones">

Las redes de publicidad envían enlaces de impresiones a AppsFlyer rellenados con la campaña y otros detalles similares a los incluidos en los <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">enlaces de atribución</Anchor> por clics.

Los enlaces se envían en tiempo real para que, si una instalación sigue a una impresión, se atribuya correctamente.

Ten en cuenta lo siguiente al preparar los enlaces:

* La URL base debe ser `http://impression.appsflyer.com`.
* Usa una solicitud GET.
* Incluye los ID de los dispositivos donde estén disponibles: IDFA, GAID, IDFV, etc.
* Incluye parámetros del <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks">modelado probabilístico</Anchor>.
* Se puede aplicar hashing a los valores de ID de dispositivo para mayor seguridad con SHA1. El nombre del parámetro debe comenzar con "sha1\_", seguido del nombre del parámetro y el valor hash, por ejemplo sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id y sha1\_imei.

> 📄
>
>  Ejemplo
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Establecer enlaces de impresiones personalizados">

Los anunciantes utilizan enlaces de impresiones de atribución con sus propias fuentes de medios personalizadas, por ejemplo, banners de sitios web.

Cuando los anunciantes <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">crean enlaces de atribución personalizados</Anchor>, obtienen enlaces de impresiones completos, que pueden activarse cada vez que los usuarios interactúan con sus anuncios.

Los enlaces de impresiones personalizados (creados a través de OneLink) también se pueden usar para realizar una atribución por impresiones de los visitantes del sitio web móvil. Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">crear URL de impresiones personalizadas</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Desactivar la atribución por impresiones">

De forma predeterminada, la atribución por impresiones está activada. Si AppsFlyer recibe un enlace de atribución de impresión válido, la impresión participa en el flujo de atribución.

Como la atribución por impresiones está activada de forma predeterminada, es importante que los anunciantes acuerden con la red, de antemano y por contrato, si la atribución por impresiones debería estar activa o no.

La atribución por impresiones puede activarse por fuente de medios. Sin embargo, si se reciben impresiones, y la atribución por impresiones se desactiva:

* Las métricas de impresiones están disponibles en el panel de control.
* El proceso de atribución ignora estas impresiones.

**Para desactivar la atribución por impresiones:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona un partner integrado.
3. En la pestaña Integración, desactiva **Atribución de instalaciones por impresiones**.
4. Haz clic en **Guardar integración**.

En el caso de las SRN, desactivar la atribución por impresiones en AppsFlyer no implica desactivarla del lado de las redes. Asegúrate de alinear la configuración de las impresiones en AppsFlyer y en las redes para evitar discrepancias.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HEMT7T1TB9W7ZBRPQW29SRPF=visi%C3%B3n-general viewthrough-attribution-flow=flujo-de-atribuci%C3%B3n-por-impresiones h_01HEMT7T1T6ZK4ZH7DKV3162J1=flujo-de-atribuci%C3%B3n-por-impresiones terminology=terminolog%C3%ADa h_01HEMT7T1TY46QXBDS6MBF1DZ5=terminolog%C3%ADa viewthrough-attribution-principles=principios-de-la-atribuci%C3%B3n-por-impresiones h_01HEMT7T1THD8TVKRRJ168HKY2=principios-de-la-atribuci%C3%B3n-por-impresiones viewthrough-lookback-window=ventana-retrospectiva-por-impresiones h_01HEMT7T1TWHN2AB3Q5X36TKKB=ventana-retrospectiva-por-impresiones viewthrough-attribution-reporting-and-metrics=m%C3%A9tricas-y-reportes-de-atribuci%C3%B3n-por-impresiones h_01HEMT7T1TQNKM5GABA7VY6KR1=m%C3%A9tricas-y-reportes-de-atribuci%C3%B3n-por-impresiones viewthrough-operations=operaciones-por-impresiones h_01HEMT7T1T13JC75ZYY01N8PS6=operaciones-por-impresiones h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution" />
