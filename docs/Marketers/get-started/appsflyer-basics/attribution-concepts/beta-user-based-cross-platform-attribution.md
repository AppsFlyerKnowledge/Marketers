---
title: '[Beta] Atribución multiplataforma basada en usuarios'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Cross-Platform Measurement
    - pm-gil-bouchnik
  created_at: '2025-09-16T13:58:09Z'
  edited_at: '2026-08-17T11:49:09Z'
  id: 39104189339793
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/39104189339793
---
> **At a glance:** Descubre qué es la atribución multiplataforma basada en usuarios, cómo funciona y cómo configurarla en AppsFlyer.

<div id="what-is-user-based-attribution" />

## ¿Qué es la atribución basada en usuarios?

Es un modelo multiplataforma que se basa en un <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario cliente (CUID)</Anchor> persistente para vincular eventos de conversión entre plataformas. Mediante el uso del CUID, el modelo atribuye toda la actividad a la fuente de medios original que impulsó el primer evento de conversión del usuario.

> 📘 **Note**
>
> Si quieres usar re-engagement entre plataformas, asegúrate de seguir leyendo este artículo, ya que aborda el modelo de atribución fundamental. Después, puedes consultar las directrices específicas en "Re-engagement" entre plataformas para atribución basada en usuarios.

<div id="a-cross-platform-user-journey-example" />

### Un ejemplo de viaje de usuario multiplataforma

Por ejemplo, un usuario hace clic en un anuncio web de Google, se registra y completa una compra en un navegador de desktop. Más tarde, el mismo usuario hace clic en un anuncio móvil de Instagram, instala la aplicación móvil y realiza otra compra in-app. Una semana después, el usuario instala la aplicación CTV de la marca, inicia sesión con el mismo CUID y también inicia una suscripción de pago allí.

Debido a que el CUID identifica constantemente al usuario en todas las plataformas y a que la campaña web de Google fue el primer evento de lanzamiento no orgánico asociado a ese CUID, toda la actividad posterior, incluida la compra de aplicaciones móviles y la suscripción a CTV, se atribuye a la campaña de Google.

<div id="user-based-vs-device-based-attribution" />

### Atribución basada en usuarios vs basada en dispositivos

Este modelo aborda una limitación clave de la **atribución basada en dispositivos**, que trata cada dispositivo como un usuario separado y fragmenta la trayectoria del usuario entre plataformas. Por el contrario, la **atribución centrada en el usuario** vincula los eventos entre dispositivos mediante un CUID persistente, lo que permite una medición coherente, un acreditamiento preciso de la campaña y una comprensión real del LTV en toda la línea de productos.

El siguiente ejemplo de viaje del usuario ilustra la diferencia entre la atribución centrada en el dispositivo y la centrada en el usuario:

[<Image alt="user-journey.png" src="https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png" width="2048px" />](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)

Un usuario hace clic en un anuncio de Meta en la web, es redirigido al sitio web del anunciante, se registra y crea una cuenta. Más tarde, el mismo usuario instala la aplicación de iOS del anunciante, inicia sesión y realiza una compra de $50. Unos días después, el usuario ve un anuncio de YouTube, instala la aplicación de PC del anunciante, inicia sesión de nuevo y realiza una compra de $100.

La atribución basada en dispositivos acredita $0 a Meta Ads, mientras que la atribución basada en usuarios acredita $150. La tabla a continuación muestra cómo se atribuiría este viaje en cada modelo:

| Compra de evento in-app | **Atribución centrada en el dispositivo** | **Atribución centrada en el usuario (CUID)** |
| --- | --- | --- |
| **Compra en la app para iOS** ($50) | Atribuido a **Orgánico** (no se realizó ningún clic en el anuncio antes en el dispositivo) | Atribuido a **Meta** (desde el anuncio web inicial) |
| **Compra en la app para PC** ($100) | Atribuido a **YouTube** (según la interacción reciente a nivel de dispositivo) | Atribuido a **Meta** (el mismo usuario identificado a través del CUID) |
| **Total de compras** ($150) | **$50 para Orgánico**, **$100 para YouTube** (dividido en campañas) | **$150 total** atribuidos a Meta (fuente única unificada) |

<div id="what-makes-an-event-a-candidate-for-cross-platform-attribution" />

### ¿Por qué un evento es candidato para la atribución multiplataforma?

Un evento se considera **candidato a atribución multiplataforma** si cumple **todas** las condiciones a seguir:

* **El CUID está presente:** El evento debe incluir un <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario</Anchor> válido (CUID), es decir, un identificador persistente proporcionado por el anunciante (por ejemplo, ID de acceso o correo electrónico con hash) que identifique de manera única a un usuario en todos los dispositivos y plataformas.
  * Si a un evento le falta un CUID pero comparte el mismo `appsflyer_id`, AppsFlyer puede rellenar el CUID en un breve periodo de procesamiento, hasta 4 horas antes de que llegue el primer evento con un CUID. Para más información, consulta [la ventana de procesamiento de enriquecimiento de CUID](#la-ventana-de-procesamiento-de-enriquecimiento-de-cuid) a continuación.
  * Los eventos que llegan sin un CUID y no se pueden enriquecer a través del proceso de enriquecimiento de CUID todavía se incluyen en la atribución multiplataforma. En estos casos, la atribución se determina utilizando su método de atribución a nivel de dispositivo (clásico).
* **Pertenece a una línea de productos:** La aplicación que genera el evento debe formar parte de una **línea de productos**, es decir, una agrupación de aplicaciones relacionadas (por ejemplo, iOS, Android, CTV) bajo la misma marca, para las que la atribución se amplía y configura colectivamente. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution#acerca-de-product-line">Agrupar aplicaciones para la atribución multiplataforma</Anchor>.
* **Dentro de la ventana de restauración de inactividad:** El evento debe estar dentro de la **ventana de inactividad**, es decir, un período configurable (por ejemplo, de 7 a 390 días) durante el cual un CUID se considera activo y elegible para la atribución dentro de una línea de productos determinada. Si el CUID no se ha visto dentro de esta ventana, se descarta su asignación de atribución anterior.
* **Los campos de atribución a nivel de dispositivo están presentes:** El evento ya debe contener **parámetros de atribución válidos** a nivel de dispositivo (por ejemplo, fuente de medios, ID de campaña) derivados del modelo clásico de atribución basada en dispositivos de AppsFlyer.

<div id="how-is-the-attribution-source-determined" />

### ¿Cómo se determina la fuente de atribución?

Este modelo atribuye todos los eventos de un usuario determinado (CUID) a la **fuente de medios original** que impulsó la primera conversión del usuario.

La fuente de medios original atribuida se determina siguiendo la siguiente lógica:

* Para cada evento in-app con un CUID en una línea de productos, AppsFlyer identifica el evento de inicio **más temprano** para ese CUID (es decir, un evento de inicio con una fuente de medios válida).
* La fuente de medios atribuida a ese evento de inicio por atribución clásica centrada en el dispositivo se considera la fuente de atribución para el evento in-app.
* Esta fuente de medios se utiliza como **fuente de atribución multiplataforma de adquisición de usuarios** para todos los eventos posteriores asociados con ese CUID y esa línea de productos.
* Si falta el CUID en un evento in-app, AppsFlyer intenta rellenarlo durante la [ventana de procesamiento de enriquecimiento](#la-ventana-de-procesamiento-de-enriquecimiento-de-cuid) de 1-4 horas.
* Si un evento sin CUID llega fuera de la [ventana de enriquecimiento](#la-ventana-de-procesamiento-de-enriquecimiento-de-cuid) de CUID definida, seguirá incluido en la atribución multiplataforma. Estos eventos se atribuyen utilizando su método de atribución a nivel de dispositivo (clásico).

> 📘 **Note**
>
> AppsFlyer solo coincide con CUID idénticos **dentro de la misma línea**. No intentamos emparejar, inferir o compartir CUID entre diferentes líneas de productos o clientes. Esto garantiza un enfoque estricto que prioriza la privacidad, manteniendo los datos de cada cliente aislados e independientes.

<div id="the-cuid-enrichment-processing-window" />

#### La ventana de procesamiento de enriquecimiento de CUID

Es el período (de 1-4 horas) durante el cual AppsFlyer procesa los eventos in-app recién llegados para rellenar los ID de usuario (CUID) de los clientes que faltan. Esto permite la atribución multiplataforma incluso si algunos eventos in-app llegan sin un CUID.

**¿Cómo funciona el enriquecimiento CUID?**

* Cada 1-4 horas, AppsFlyer ejecuta un trabajo de procesamiento.
* Si un evento llega sin un CUID pero comparte el mismo `appsflyer_id` que otro evento con un CUID, AppsFlyer rellena el CUID que falta.
* Esta vinculación solo se aplica a los eventos recibidos durante la ventana de procesamiento.

**Ejemplo de enriquecimiento de CUID**

* **8:01**: Un *evento de primera apertura de la aplicación* se registra con `appsflyer_id = XYZ`.
* **9:00**: Se registra un evento de *registro* con `cuid = 123` y `appsflyer_id = XYZ`.
* **12:00**: Finaliza la ventana de procesamiento de 4 horas. AppsFlyer une `cuid = 123` retroactivamente al evento de *primera apertura de la aplicación*.
* **12:30**: Se registra un evento de *compra* con `appsflyer_id = XYZ`  pero no tiene
* **12:30**: Un evento de *compra* se registra con `appsflyer_id = XYZ` pero sin CUID. Como el evento llega después de que se cierra la ventana, AppsFlyer no le da `cuid = 123`.

**Limitaciones de enriquecimiento de CUID**

* Los eventos sin CUID que llegan **fuera de la ventana** se atribuyen mediante la atribución clásica de AppsFlyer y se agregan a los resultados del método de atribución multiplataforma.
* La vinculación del CUID **no se aplica de forma retroactiva** fuera de la ventana de procesamiento.

> 👍 **Tip**
>
> Para maximizar la coincidencia entre plataformas, siempre incluye un CUID en cada evento in-app enviado.

<div id="set-up-cross-platform-attribution" />

## Configuración de la atribución multiplataforma

Para configurar la atribución multiplataforma, debes aplicar algunas configuraciones en AppsFlyer e implementar funciones específicas del SDK en el código de tu aplicación.

* **En AppsFlyer**, asigna tus aplicaciones a una línea de producto, opta por la atribución multiplataforma y especifica la ventana de restauración de inactividad. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution#cómo-configurar-una-product-line">Configurar una línea de productos</Anchor>.
* **En tu aplicación**, configura el SDK de AppsFlyer para enviar eventos con CUID. Para obtener instrucciones para desarrolladores, consulta [Configurar ID de usuario de cliente](https://dev.appsflyer.com/hc/docs/set-customer-user-id).

<div id="view-cross-platform-attribution-results" />

## Ver resultados de atribución multiplataforma

* Para ver los resultados de la atribución multiplataforma, consulta el <Anchor target="_blank" href="/marketers/es/docs/end-user-events-cross-platform-report-in-data-locker">reporte multiplataforma de eventos de usuario final de Data Locker</Anchor>.
* **My Dashboards:** Disponible mediante la plantilla «Cross Platform». Para obtener más información sobre cómo seleccionar una plantilla de dashboard, consulta <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#create-dashboard">Crear un dashboard personalizado</Anchor>.

<div id="frequently-asked-questions-faqs" />

## Preguntas frecuentes (FAQs)

<Accordion title="¿Por qué los resultados de la atribución entre plataformas son diferentes de los resultados de la atribución clásica de AppsFlyer?">

Hay varias razones que pueden explicar las diferencias.

<div id="different-attribution-logic" />

#### Lógica de atribución diferente

* **La atribución entre plataformas se basa en el usuario.** Vincula la actividad mediante el CUID y atribuye toda la actividad posterior del Usuario a la cohorte de Campaña del usuario dentro de la línea de Producto.
* **La atribución clásica de AppsFlyer se centra en el dispositivo** (un ID de AppsFlyer por dispositivo). Esto significa que el mismo usuario real en varios dispositivos o plataformas puede contabilizarse como usuarios distintos y atribuirse a diferentes puntos de contacto.

**Impacto:** Aunque los ingresos totales sean similares, los ingresos por fuente de medios o campaña pueden variar significativamente.

<div id="different-attribution-date" />

#### Fecha de atribución diferente

* En los resultados de cohortes clásicos y de LTV, la fecha de atribución refleja la fecha de la primera apertura de la App por parte del Usuario o, en web, la fecha inicial de Adquisición de usuarios.
* En la vista de UA entre plataformas, la fecha de atribución representa la primera fecha de adquisición del usuario en todas las plataformas. Cuando el re-engagement entre plataformas está habilitado, la fecha de atribución refleja la apertura no orgánica más reciente de la App.

Como resultado, algunas métricas de la atribución entre plataformas pueden atribuirse a fechas anteriores en comparación con la atribución clásica.

</Accordion>

<div data-zendesk-anchors="what-is-userbased-attribution=qu%C3%A9-es-la-atribuci%C3%B3n-basada-en-usuarios h_01K59D3JXN9P5ZN40WX957CHKC=qu%C3%A9-es-la-atribuci%C3%B3n-basada-en-usuarios a-crossplatform-user-journey-example=un-ejemplo-de-viaje-de-usuario-multiplataforma h_01K59D3JXN4WJ3HN0AXN58N877=un-ejemplo-de-viaje-de-usuario-multiplataforma userbased-vs-devicebased-attribution=atribuci%C3%B3n-basada-en-usuarios-vs-basada-en-dispositivos h_01K59D3JXN3EXS90N2AX7DXV3B=atribuci%C3%B3n-basada-en-usuarios-vs-basada-en-dispositivos what-makes-an-event-a-candidate-for-crossplatform-attribution=por-qu%C3%A9-un-evento-es-candidato-para-la-atribuci%C3%B3n-multiplataforma h_01K59D3JXNNYZHYFAPRH50E4Z4=por-qu%C3%A9-un-evento-es-candidato-para-la-atribuci%C3%B3n-multiplataforma how-is-the-attribution-source-determined=c%C3%B3mo-se-determina-la-fuente-de-atribuci%C3%B3n h_01K59D3JXNGNZYAYPG13SZ98V1=c%C3%B3mo-se-determina-la-fuente-de-atribuci%C3%B3n the-cuid-enrichment-processing-window=la-ventana-de-procesamiento-de-enriquecimiento-de-cuid h_01K59D3JXN5CYVB6F84DTRBZS9=la-ventana-de-procesamiento-de-enriquecimiento-de-cuid set-up-crossplatform-attribution=configuraci%C3%B3n-de-la-atribuci%C3%B3n-multiplataforma h_01K59D3JXNH84WMZ6PQ4BVF44B=configuraci%C3%B3n-de-la-atribuci%C3%B3n-multiplataforma view-crossplatform-attribution-results=ver-resultados-de-atribuci%C3%B3n-multiplataforma h_01K59D3JXNGGG4AKEXM9Q9KA6A=ver-resultados-de-atribuci%C3%B3n-multiplataforma frequently-asked-questions-faqs=preguntas-frecuentes-faqs h_01KNSGZXB1EFD78QSA8B28XCN9=preguntas-frecuentes-faqs different-attribution-logic=l%C3%B3gica-de-atribuci%C3%B3n-diferente h_01KNSG79PE8RFRSHYWGTGWN4VV=l%C3%B3gica-de-atribuci%C3%B3n-diferente different-attribution-date=fecha-de-atribuci%C3%B3n-diferente h_01KNSG79PEBXX0H14B9SQZ0W83=fecha-de-atribuci%C3%B3n-diferente" />
