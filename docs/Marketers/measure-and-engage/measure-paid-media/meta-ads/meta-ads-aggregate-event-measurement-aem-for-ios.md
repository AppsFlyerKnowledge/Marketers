---
title: Medición de eventos agregados (AEM) de Meta ads para iOS
metadata:
  keywords:
    - Agencies
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
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-27T03:47:29Z'
  id: 19228737402129
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/19228737402129
---
> **Resumen:** Obtén más información sobre la solución de medición de eventos agregados (AEM) para optimizar las conversiones de iOS y los eventos in-app, y para atribuir los re-engagements de iOS en Meta Ads.

## Descripción general

AppsFlyer es compatible con la solución de <Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Medición de eventos agregados de Anuncios de Meta (AEM)</Anchor>. Esta solución permite medir los eventos web y de aplicaciones en dispositivos iOS 14 o posteriores mediante los siguientes métodos de atribución:

* [AEM de aplicaciones para re-engagement](#aem-de-aplicaciones-para-re-engagement)
* [AEM de aplicaciones para promoción de aplicaciones](#aem-de-aplicaciones-para-promoción-de-aplicaciones)

Como parte de la solución AEM, Meta acepta postbacks de conversión y eventos in-app provenientes de AppsFlyer, siempre que los eventos sean aptos para AEM. Para verificar la elegibilidad de tus eventos para AEM, consulta lo siguiente:

* [Verifica si los eventos de tu app son elegibles para AEM](#comprobar-elegibilidad)

## AEM de aplicaciones para re-engagement

Con AEM, Meta Ads proporciona atribución de re-engagement mediante enlace profundo para usuarios de iOS cuando el ID del anunciante no está disponible.

### Flujo de atribución

Meta Ads añade los datos de atribución al deep link junto con el identificador de `campaign_ids` AEM. AppsFlyer recibe y procesa los parámetros de campaña que se muestran en la URL del enlace profundo y, a continuación:

* Envía datos de reportes agregados a Anuncios de Meta
* Realiza atribución basada en la información de enlace profundo anexada por Anuncios de Meta
* Incluye los datos de atribución del enlace profundo en los reportes de raw data y datos agregados.

### Parámetros de datos de atribución

Los siguientes parámetros de datos de atribución, compartidos por Anuncios de Meta, se incluyen en los reportes:

* `id_adset`
* `adgroup_id`
* `id_campaña`
* `campaign_group_id`
* `account_id`

> 📘 **Advertencia**
>
> Para aprovechar AEM para remarketing, el SDK de AppsFlyer recupera la string `campaign_ids` al abrir el enlace profundo. De forma predeterminada, el SDK comparte enlaces profundos de todos los dominios. Si has personalizado tu integración, asegúrate de que esté configurada para compartir enlaces profundos de todos los dominios, incluido el dominio de Meta, y no solo del dominio de AppsFlyer.

### Preguntas frecuentes sobre la atribución de re-engagement de enlaces profundos

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="¿Qué debe hacer el anunciante para habilitar esta atribución?">

**No se requiere ninguna acción** por parte del anunciante para recibir estos parámetros para la atribución.

Sin embargo, para medir la atribución de re-engagement de enlace profundo, el **selector de atribución de re-engagement** **debe estar activado**.

**Nota:** Según los términos y condiciones de Meta Ads sobre AEM, habilitar la medición de la atribución de re-engagement significa que los postbacks a Meta Ads podrían incluir direcciones IP parciales como parte de los datos de atribución.

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="¿Qué pasa con las agencias y los partners de gestión de campañas de Meta?">

En esta etapa, no se admite la atribución para agencias y partners de gestión de campañas de Meta. Esto significa que todo el tráfico se atribuye a Anuncios de Meta. Esto es temporal y va a cambiar pronto.

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="¿Hay alguna restricción en los datos de esta atribución?">

Los datos provenientes de atribuciones de enlaces profundos no están sujetos a restricciones de reportes. Esto significa que todos los datos aparecen tanto en los reportes agregados como en los reportes sin procesar a nivel de usuario.

</Accordion>

## AEM de aplicaciones para promoción de aplicaciones

### Elegibilidad de AEM

Cuando una aplicación es apta para AEM en Meta Ads, **Aggregated Event Measurement** se selecciona de forma predeterminada durante la creación del conjunto de anuncios. Esto significa que tanto AEM como SKAdNetwork (SKAN) se pueden usar simultáneamente para la campaña. Si en su lugar se selecciona **Apple SKAdNetwork**, solo SKAN se aplicará a la campaña. Esto significa que AppsFlyer tiene una capacidad limitada para medir la actividad de la aplicación en Meta Ads.

<Image alt="aem_meta_ads_platform.png" src="https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png" width="563px" />

> 📘 **Nota**
>
> Si tienes problemas con la elegibilidad para AEM, consulta [Comprueba si los eventos de tu app son aptos para AEM](#verifica-si-los-eventos-de-tu-app-son-elegibles-para-aem).

### Compartición de datos de AEM

**La compartición de datos avanzada** te permite compartir todos los eventos de conversión con Meta ads y atribuir todas las instalaciones y eventos in-app posteriores, independientemente del estado de consentimiento ATT.

* Cuando está desactivada, la compartición avanzada de datos se limita a los eventos de conversión de usuarios con un ID del anunciante disponible. Los eventos de usuarios sin un ID de anunciante no se comparten ni se atribuyen.
* Cuando está habilitada, la compartición avanzada de datos pone los eventos de conversión a disposición de Meta Ads para todos los usuarios, incluidos los que no tienen un ID del anunciante. AppsFlyer atribuye estos eventos. Los datos puestos a disposición podrían incluir información adicional relacionada con el dispositivo que no implique el ID del dispositivo. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#advanced_data_sharing">Compartición de datos avanzada</Anchor>.

![aem](https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png)

> 📘 **Nota**
>
> * Todos los eventos incluyen las instalaciones, aperturas de la aplicación y eventos in-app.
> * Antes de habilitar **Advanced data sharing**, asegúrate de que poner estos datos a disposición de Meta Ads, incluido cualquier uso de tus datos por parte de terceros, cumpla con las políticas o normativas de la plataforma a las que estés sujeto. Los datos puestos a disposición podrían incluir direcciones IP, anon\_ids (si están disponibles), vendor\_id y user agents.
> * Para eventos in-app enviados mediante server-to-server (S2S), Meta requiere que tanto la **dirección IP** como el **Identifier for Vendors (IDFV)** se incluyan en la carga útil del evento. Sin estos identificadores, el evento no será elegible para la atribución AEM de Meta.
> * Meta AEM para promoción de apps también puede incluir atribuciones view-through no determinísticas. Para admitir la atribución view-through no determinística mediante Meta AEM, asegúrate de que el selector a nivel de app Enable view-through attribution via campaign measurement modeling esté activado. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">Atribución view-through mediante modelado probabilístico</Anchor>.

## Verifica si los eventos de tu app son elegibles para AEM

Puedes visitar Meta Events Manager para verificar si los eventos de tu app son elegibles para AEM. Una vez que el evento de tu app sea elegible, podrás ver los resultados de las campañas AEM seleccionadas en Ads Manager. Para aprender a verificar si los eventos de tu app son elegibles para AEM, consulta la <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">documentación de Meta</Anchor>.

## Habilitar AEM: resumen

Utiliza la siguiente tabla como una lista de verificación rápida para habilitar Meta ads AEM en AppsFlyer.

| **Solución** | **Selector** | **Ubicación del selector** | **Impacto** |
| --- | --- | --- | --- |
| **Remarketing AEM (re-engagements)** | Atribución de re-engagement | Integración de partner (Meta ads) | Habilita AEM para remarketing (atribución de re-engagement). |
| **Promoción de apps AEM (instalaciones)** | Intercambio avanzado de datos | Integración de partner (Meta ads) | Habilita AEM para la promoción de apps, incluido poner a disposición eventos de usuarios cuando no hay un ID del anunciante disponible, hacer que se puedan medir mediante Meta y aceptar atribuciones no determinísticas (cuando corresponda). |
| **Promoción de apps AEM (instalaciones)** | Habilitar la atribución view-through mediante modelado probabilístico | Configuración de la aplicación | Habilitar la atribución view-through mediante modelado probabilístico |

## Resolución de problemas

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Resolución de problemas de eventos no elegibles en Meta AEM">

Si Meta Ads marca los eventos de tu app como no aptos y muestra errores como **«Missing opt-out events»** u otros mensajes relacionados con AEM, normalmente se debe a datos que faltan o están mal configurados. Utiliza la siguiente lista de verificación para diagnosticar y corregir problemas comunes.

> 🚧 **¡Importante!**
>
> Después de completar los pasos a continuación, espera un tiempo para que los cambios surtan efecto. Meta Ads puede tardar hasta **2–3 días** en reflejar la elegibilidad para AEM.

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="Paso 1: la compartición avanzada de datos está habilitada">

1. Ve a **Colaborar**> **Integraciones activas** > **Meta Ads**.
2. Asegúrate de que **Advanced data sharing** esté activado.

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="Paso 2: El enmascaramiento de IP está deshabilitado">

Los eventos con IPs enmascaradas no son elegibles para AEM.

* Ve a **Configuración de la app**.
* Asegúrate de que el **enmascaramiento de IP** esté desactivado.

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="Paso 3: Los eventos de servidor a servidor (S2S) incluyen los parámetros requeridos">

Cada evento S2S debe incluir:

* **Dirección IP**
* **IDFV** (identificador para proveedores)

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="Paso 4: Revisa la tasa de consentimiento de App Tracking Transparency (ATT)">

Meta acepta un volumen limitado de eventos con valores del Identifier for Advertisers (IDFA) ausentes o establecidos en cero. Si tu aplicación supera este umbral, puede que veas el siguiente error: «**Advertiser Tracking Enabled parameter volume out of range.»**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="Paso 5: Configuración del mapeo de postbacks">

Asegúrate de que los postbacks de eventos estén configurados como **Enviar todos (incluyendo orgánicos)**.

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="Step 6: Verificar la configuración de re-engagement (si corresponde)">

Para campañas de re-engagement:

* Habilita **atribución de re-engagement** tanto en **Configuración de la aplicación** como en la **página de integración activa de Meta**.

</Accordion>

#### ¿Aún no funciona?

Si algunos eventos específicos siguen siendo no elegibles:

1. Ve al Administrador de Eventos de Meta y sigue las instrucciones en pantalla.
2. Selecciona el evento de la app afectado.
3. Configura **tráfico de MMP** como el método de conexión preferido.

#### ¿Necesitas ayuda?

Si el problema persiste:

* Enviar una solicitud de asistencia
* Incluye una captura de pantalla de Meta Ads que muestre los eventos no elegibles

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="No recibo datos AEM en dashboards ni reportes, aunque mis campañas son elegibles para AEM">

Esta es la respuesta de Meta: «Estamos implementando esta actualización en colaboración con tu MMP durante los próximos meses y es posible que algunos anunciantes no tengan acceso hasta que el despliegue se complete.»

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="¿Por qué no puedo ver instalaciones atribuidas por AEM en los reportes de raw data incluso después de firmar el acuerdo AMM?">

Cuando AAP está habilitado, las instalaciones atribuidas mediante la Medición de eventos agregados (AEM) de Meta se excluyen de los reportes de raw data. Esto aplica incluso si el acuerdo AMM está firmado.

</Accordion>

> 📘 **Nota:**
>
> Cuando **Uso compartido avanzado de datos** está activado, Meta puede reclamar y atribuir instalaciones mediante la Medición de eventos agregados (AEM) incluso cuando no hay datos de consentimiento disponibles, también en los casos en los que no se recopila nunca ningún IDFA. Sin embargo, los resultados de AEM pueden mejorar a medida que haya más señales de IDFA disponibles, por lo que te recomendamos enviar tantos eventos con consentimiento como sea posible.

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01HCAM4CEVRCG13CA32B0GM9QS=descripci%C3%B3n-general app-aem-for-reengagement=aem-de-aplicaciones-para-re-engagement 01H88ZM20H99W37M0H6XXQVMQA=aem-de-aplicaciones-para-re-engagement attribution-flow=flujo-de-atribuci%C3%B3n 01H7YJVNMV7QSZJWKZZA9042K6=flujo-de-atribuci%C3%B3n attribution-data-parameters=par%C3%A1metros-de-datos-de-atribuci%C3%B3n 01H7YJVNMVPPCD08Z2R0V5GCMY=par%C3%A1metros-de-datos-de-atribuci%C3%B3n h_attribution_deeplink_note=advertencia faqs-on-deep-link-reengagement-attribution=preguntas-frecuentes-sobre-la-atribuci%C3%B3n-de-re-engagement-de-enlaces-profundos 01H7YJVNMV4ZKMWKD06RC6GKFW=preguntas-frecuentes-sobre-la-atribuci%C3%B3n-de-re-engagement-de-enlaces-profundos 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%20attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=aem-de-aplicaciones-para-promoci%C3%B3n-de-aplicaciones 01H88ZM20HQFMG962AZGYA98FR=aem-de-aplicaciones-para-promoci%C3%B3n-de-aplicaciones aem-eligibility=elegibilidad-de-aem 01H7YJVNMVPB054VFS60KH9N7W=elegibilidad-de-aem h_01HR886Q0KPM99FCQXD6RDPSBK=nota aem-data-sharing=compartici%C3%B3n-de-datos-de-aem 01H88ZM20HK2HY32M4BKZ4N0B9=compartici%C3%B3n-de-datos-de-aem 01H7YK9CHHNARCD7M2VZRMEW6S=nota-1 check-eligibility=verifica-si-los-eventos-de-tu-app-son-elegibles-para-aem 01JBHQSHF8NA4SGVJ3WYPRN9B3=verifica-si-los-eventos-de-tu-app-son-elegibles-para-aem enable-aem-toggles-summary=habilitar-aem-resumen h_01KJ28ETP9GK6TBTJK8SBZ5PFW=habilitar-aem-resumen faqs-and-troubleshooting=resoluci%C3%B3n-de-problemas 01H7YK9CHHZN78CBHFTQ7E9RKQ=resoluci%C3%B3n-de-problemas h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=importante h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=a%C3%BAn-no-funciona h_01K722GQSB8CXSSCVZPA3R3CJX=a%C3%BAn-no-funciona need-help=necesitas-ayuda h_01K722GQSBBB8KS8JNRBJZ4WWT=necesitas-ayuda 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%27t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01M5VSB77G1VDKA6SJC81XNNFX=nota-2" />
