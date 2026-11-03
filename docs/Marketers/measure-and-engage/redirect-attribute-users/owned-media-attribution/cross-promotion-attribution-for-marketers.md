---
title: Atribución de promociones cruzadas para marketers
metadata:
  keywords:
    - tracking
    - Advertisers
    - Cross Promotion
    - cross-promotion
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2026-08-12T12:24:56Z'
  id: 115004481946
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/115004481946
---
> **En resumen:** Atribuye las instalaciones de campañas de promoción cruzada que promocionan tus aplicaciones en otras aplicaciones de tu propiedad.

![CrossPromo_recorridoDelUsuario](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

## Sobre la promoción cruzada

Son una de las mejores maneras de promocionar tus aplicaciones existentes o de guiar a los usuarios hacia las nuevas aplicaciones lanzadas por tu empresa. Este tipo de campañas pueden generar tasas de conversión y retención más altas en comparación con la mayoría de las demás fuentes de tráfico. Dado que la promoción cruzada es publicidad en medios propios, puedes usar la [coincidencia de ID de dispositivo](/docs/cross-promotion-attribution-for-marketers#atribución-de-promociones-cruzadas) para atribuir de forma determinística las nuevas instalaciones. La atribución entre promociones está disponible para todas las cuentas, independientemente de tu plan de AppsFlyer.

La siguiente imagen muestra el dashboard de la aplicación promocionada con un desglose de las métricas de las campañas que se publican en medios propios (**af\_cross\_promotion**) y otras fuentes de medios. Puedes ver que el número de descargas y la tasa de conversión de la campaña de promoción cruzada son mucho más altos que los de otras fuentes de medios.

[![CrossPromo_origenDeMedios](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

### ¿Cómo funciona la promoción cruzada?

1. El usuario recibe un anuncio de promoción cruzada en una aplicación existente de la que es propietario tu empresa. El anuncio promociona otra aplicación que también es propiedad de tu empresa. La creatividad del anuncio puede ser un banner, un vídeo o cualquier objeto en el que se pueda hacer clic.
2. [opcional] El <Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-developers">SDK registra y envía</Anchor> una impresión de promoción cruzada a AppsFlyer.
3. El usuario hace clic en el anuncio.
4. El SDK registra el clic y redirecciona al usuario a la página de la aplicación promocionada en la tienda de aplicaciones. El clic registrado por el SDK ya incluye el ID de publicidad del dispositivo.
5. Una vez instalada y lanzada la aplicación promocionada, el [dashboard de AppsFlyer](/docs/cross-promotion-attribution-for-marketers#dashboard-de-aplicaciones-promocionadas) muestra al usuario recién adquirido en la fuente de medios **af\_cross\_promotion.**
   * Para cambiar el valor de la fuente multimedia, el desarrollador debe agregar un parámetro personalizado llamado `pid` con el valor que deseas. **Nota**: Para Android, esto solo funciona para el SDK V6.4.2+.
   * La aplicación que impulsa la instalación, la aplicación nativa, aparece como **ID de sitio** de esta fuente de medios.
6. El SDK genera automáticamente un evento in-app.  
   El nombre del evento para Android es `af_cross_promotion` y para iOS es `af_cross_promotion_clicked`.

## Atribución de promociones cruzadas

AppsFlyer te permite usar la coincidencia de ID de dispositivo como método de atribución para registrar y atribuir las instalaciones que se originan en tus campañas de promoción cruzada. Puedes atribuir tanto las impresiones como los clics, lo que te permite calcular la <Anchor target="_blank" href="/marketers/es/docs/about-conversion-rates#etapas-del-embudo-de-marketing-y-tasas-de-conversión-1">tasa de click-through</Anchor> o el ratio de instalaciones/impresiones.

El identificador de dispositivo utilizado para la coincidencia depende de lo siguiente:

* El dispositivo del usuario y la versión del sistema operativo
* La versión del SDK de AppsFlyer en la aplicación nativa

| La coincidencia de ID de dispositivo para promociones cruzadas | Versión del dispositivo/sistema operativo | Versión del SDK | Notas |
| --- | --- | --- | --- |
| Identificador de anunciante (IDFA) | iOS 9 – 14.4 | V5.0.0+ |  |
| IDFV | iOS 14.5+ | V6.0.2+ | El IDFV se recoge automáticamente; el desarrollador no requiere ninguna otra acción. |
| GNA Company | Dispositivos Android con servicios de Google Play |  |  |
| OAID, ID de Android, IMEI, ID de Fire | Dispositivos Android sin servicios de Google Play |  |  |

## Configuración de la promoción cruzada

El proceso de configurar la atribución de promociones cruzadas requiere que el marketer y el desarrollador trabajen juntos para implementar código adicional en el SDK de AppsFlyer.

El flujo para el marketer y el desarrollador es el siguiente:

| Paso | Rol | Tarea | Detalles |
| --- | --- | --- | --- |
| 1 | Comercializador | Decide las aplicaciones existentes en las que quieres ejecutar la campaña de promoción cruzada. | La aplicación nativa a la que se atribuye la instalación aparecerá como **ID del sitio** en el dashboard de la aplicación promocionada. |
| 2 | Comercializador | Determina si quieres añadir <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">parámetros adicionales</Anchor>, como la ventana de lookback, el nombre del conjunto de anuncios y los parámetros de suscriptor. Envía estos nombres y valores de parámetros adicionales al desarrollador. |  |
| 3 | desarrollador | Implementa el código en el SDK. | La documentación para desarrolladores se encuentra <Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-developers">aquí</Anchor>. |
| 4 | Comercializador | En el [dashboard de la aplicación promocionada](/docs/cross-promotion-attribution-for-marketers#dashboard-de-aplicaciones-promocionadas), consulta el tráfico que proviene de la campaña de promoción cruzada y optimiza tus campañas en consecuencia. |  |
| 5 [Opcional] | Comercializador | Crea un [dashboard personalizado](/docs/cross-promotion-attribution-for-marketers#dashboard-personalizado) para comparar el tráfico de promociones cruzadas y compartir datos con los usuarios de la cuenta. |  |

## Visualización de datos de promociones cruzadas

### Dashboard de aplicaciones promocionadas

Te permite determinar qué aplicaciones nativas envían el mejor tráfico a la aplicación promocionada.

**Para comparar el tráfico de las aplicaciones nativas:**

1. Ve a **General**.
2. Selecciona la fuente de medios **af\_cross\_promotion** (o tu fuente de medios personalizada).
3. Agrupa por **ID de sitio** para ver la lista de aplicaciones nativas.[![CrossPromo_IDDelSitio](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)

#### Análisis

Al ver los datos sobre las instalaciones, los clics, las impresiones y la tasa de conversión de varias aplicaciones existentes que publican anuncios para la misma aplicación promocionada, puedes realizar un análisis de afinidad. Las aplicaciones nativas (ID de sitio) con las mejores tasas de conversión son las que mejor se adaptan a la aplicación promocionada y es más probable que sus usuarios la instalen. Basándote en esta información, puedes optimizar tus campañas de promoción cruzada en consecuencia.

> 📄 **Ejemplo**
>
> Eres un marketer de aplicaciones de gaming para PlayIt Gaming International. Tienes varias aplicaciones exitosas, como Bowling (com.playit.bowling) y Golfing (com.playit.golfing). Acabas de lanzar una nueva aplicación llamada Billiards. Decides realizar pruebas de promoción cruzada para ver cuántos usuarios hacen clic realmente en el anuncio de Billiards en una de las aplicaciones existentes. La campaña funciona bien en Bowling, con una tasa de conversión del 7,92%, por lo que decides anunciarte también en Golfing.
>
> Cuando consultas el dashboard, ves que la tasa de conversión para Golfing, 18,22%, es mucho más alta que la tasa de Bowling, lo que te permite determinar que existe una mayor afinidad entre Golfing y la aplicación promocionada, Billiards.
>
> [![CrossPromo_tasaDeConversión](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> En función de estos insights, puedes optimizar tu campaña de la siguiente manera:
>
> * Lleva a cabo una campaña de promoción cruzada a gran escala en Golfing.
> * Empieza a <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements#flujo-de-atribución-por-impresiones">atribuir las impresiones</Anchor> además de los clics. Dado que inicialmente configuraste tu campaña para medir solo los clics, las instalaciones de los usuarios que ven el anuncio sin hacer clic y luego lo instalan más tarde se cuentan como instalaciones orgánicas y no como no orgánicas. Esto significa que aún no tienes una imagen completa del rendimiento de la campaña para cada aplicación nativa.

### Dashboard personalizado

El dashboard de la aplicación promocionada es ideal para hacerte una idea de qué aplicaciones nativas generan el mejor tráfico. Pero, ¿qué pasa si quieres evaluar el rendimiento de una sola aplicación existente que se utiliza para promocionar varias aplicaciones? Aquí es donde un dashboard personalizado puede hacer exactamente lo que necesita.

Un <Anchor target="_blank" href="/marketers/es/docs/custom-dashboards">dashboard personalizado</Anchor> te permite ver la información de varias aplicaciones promocionadas en un solo lugar, incluido el tráfico de promociones cruzadas. Además, es una forma rápida y sencilla de compartir datos con los usuarios de la cuenta.

> 📄 **Ejemplo**
>
> Eres un marketer de eCommerce Apps, Ltd., y tienes una aplicación de gran éxito llamada Shoes. Ahora estás lanzando 3 nuevas aplicaciones: Accessories, Jackets y Coats y Sport Shoes. Decides lanzar una campaña de promoción cruzada en la aplicación Shoes para ver cuáles de tus nuevas aplicaciones promocionan mejor.
>
> Divides tu base de usuarios en 3 segmentos. Cada vez que un usuario abre la aplicación Shoes, se muestra 1 de los 3 anuncios posibles: 1 para Accessories, 1 para Jackets y Coats y 1 para Sport Shoes.
>
> Para ver las métricas de las tres aplicaciones promocionadas en un solo lugar, debes crear un dashboard personalizado. En la siguiente imagen, puedes ver que Sport Shoes tiene una tasa de conversión del 20,23%, lo que significa que Shoes tiene una afinidad mucho mayor con Sport Shoes que con las otras 2 aplicaciones que promociona.
>
> ![CrossPromo_customWidget](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=sobre-la-promoci%C3%B3n-cruzada h_01HE7RXZ2CZCYENE4K40W5YSHF=sobre-la-promoci%C3%B3n-cruzada how-does-crosspromotion-work=c%C3%B3mo-funciona-la-promoci%C3%B3n-cruzada h_01HE7RXZ2CE5EQV42Y4B9SK4FN=c%C3%B3mo-funciona-la-promoci%C3%B3n-cruzada attributing-crosspromotion=atribuci%C3%B3n-de-promociones-cruzadas h_01HE7RXZ2CWB2GZ8HV6447RVV1=atribuci%C3%B3n-de-promociones-cruzadas setting-up-crosspromotion=configuraci%C3%B3n-de-la-promoci%C3%B3n-cruzada h_01HE7RXZ2C9JGFYV8K8FECFFJN=configuraci%C3%B3n-de-la-promoci%C3%B3n-cruzada viewing-crosspromotion-data=visualizaci%C3%B3n-de-datos-de-promociones-cruzadas h_01HE7RXZ2CE9NWMQ1PT3G98QVN=visualizaci%C3%B3n-de-datos-de-promociones-cruzadas promoted-app-dashboard=dashboard-de-aplicaciones-promocionadas h_01HE7RXZ2CQG9M35Y2FJNPZWDA=dashboard-de-aplicaciones-promocionadas analysis=an%C3%A1lisis h_01HE7RXZ2CVQD8H0J6EVRJM5T7=an%C3%A1lisis h_01HE7RXZ2CW1P0QNA8FFXP5KBS=ejemplo custom-dashboard=dashboard-personalizado h_01HE7RXZ2C7N3DKNPF898WM4AD=dashboard-personalizado h_01HE7RXZ2C51KJMP795QYS26YK=ejemplo-1" />
