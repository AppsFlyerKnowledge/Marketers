---
title: Información sobre ATT y SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-08-12T11:57:30Z'
  id: 360011890298
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/360011890298
---
> **En resumen**: A partir de iOS 14.5, Apple requiere que implementes y cumplas con los términos de <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor> (ATT). La ATT significa que *si tu aplicación recopila datos sobre los usuarios finales y los comparte con otras empresas con el fin de realizar un seguimiento a través de aplicaciones y sitios web,* debes usar el aviso de consentimiento de la ATT y obtener el consentimiento del usuario tanto en la aplicación del editor como en la del anunciante. Si no realizas un seguimiento, no es necesario mostrar el aviso.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## Medición de la atribución en un entorno ATT

AppsFlyer te proporciona múltiples métodos de atribución que te brindan una gama completa de soluciones de atribución. El requisito de consentimiento de [ATT](/docs/about-att-and-skan#att-principles) afecta la atribución en el contexto de las campañas pagadas de aplicación a aplicación. Como tal, los anunciantes necesitan usar una combinación de soluciones de atribución y reportes. 

En el caso de las campañas pagadas de aplicación a aplicación, [SKAN](/docs/about-att-and-skan#skan-solution-principles) proporciona resultados de atribución deterministas. Otros tipos de campañas como medios propios, web a aplicación y Apple Search Ads utilizan las herramientas de atribución tradicionales de AppsFlyer. Las herramientas tradicionales proporcionan medición del valor de vida útil (LTV) a largo plazo, mientras que SKAN mide el rendimiento del usuario durante un breve período posterior a la instalación.

En resumen, para obtener una imagen completa, utiliza las soluciones tradicionales tanto de SKAN como de AppsFlyer, porque se complementan entre sí.

Este artículo proporciona a los anunciantes una introducción a SKAN y ATT. Está dirigido a anunciantes que estén familiarizados con la plataforma AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Principios de la solución SKAN">

AppsFlyer proporciona resultados de atribución de iOS agregados usando postbacks SKAN de iOS. Estos postbacks son enviados por iOS a redes de publicidad que luego los reenvían a AppsFlyer. Los postbacks contienen registros de atribución anonimizados enriquecidos con un valor de conversión (CV) establecido por el anunciante. El CV es una medida de la calidad del usuario durante una ventana inicial post-instalación.

La <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">solución SKAN</Anchor> de AppsFlyer proporciona a los anunciantes:

* Datos de SKAN en paneles de control y reportes derivados de la agregación de postbacks de todas las redes de publicidad enriquecidas con otros puntos de datos como el costo.
* La capacidad de controlar, a través de AppsFlyer Conversion Studio, lo que mide el CV sin necesidad de realizar cambios en el código de la aplicación. El CV se puede utilizar para medir los ingresos, engagements o eventos de conversión.

**Limitaciones de SKAN**

* **Campañas:** no es compatible con Apple Search Ads, campañas de promoción cruzada ni instalaciones móviles asistidas por web.
* **Periodo de medición:** el periodo de medición efectivo está limitado a unos pocos días.

**Flujo de SKAN**

![SKAN_flow_-_Diagrama_de_afinidad_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. El anunciante establece los ajustes de medición de SKAN en AppsFlyer Conversion Studio.
2. El usuario abre la aplicación por primera vez.
3. Durante cada ventana, AppsFlyer establece el CV en función de las acciones del usuario y el esquema de CV definido.
4. Después de que se cierra la ventana, iOS envía el postback a la red de publicidad y una copia del postback a AppsFlyer. El postback llega con cierto retraso:
   * Para la ventana de medición 1 de SKAN 4: 24-48 horas
   * Para las ventanas de medición 2-3 de SKAN 4: 24-144 horas
   * Para SKAN 3: 24-48 horas después del incremento más reciente en el valor CV.
5. Las copias de postbacks enviadas directamente desde el dispositivo iOS a AppsFlyer se reenvían al punto de conexión definido por el anunciante. Consulta <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Enviar copias de postbacks de SKAN a AppsFlyer.</Anchor>
6. La red de publicidad reenvía el postback enriquecido a AppsFlyer o la SRN comunica los datos del postback por API.
7. AppsFlyer valida y decodifica el CV. Los datos decodificados se registran y atribuyen antes de que estén disponibles en AppsFlyer a través de los paneles de control, reportes y API.

</Accordion>

<div id="att-principles" />

<Accordion title="Principios de la ATT">

El aviso de ATT proporciona a los anunciantes una forma de obtener el consentimiento explícito del usuario, que permite a los anunciantes recopilar y compartir sus datos. A partir de iOS 14.5, el identificador de anunciante (IDFA) solo está disponible si el usuario da su consentimiento a través de este aviso.

Tanto las aplicaciones del publisher como del anunciante muestran el aviso. Si el usuario brinda su consentimiento en ambas aplicaciones, significa que el usuario acepta ser *rastreado,* y Apple permite a los anunciantes rastrear al usuario entre las aplicaciones propiedad de diferentes empresas.

**Configuración de la ATT**

La ATT se establece en uno de los valores enumerados en la tabla que sigue. Inicialmente, iOS establece la ATT como no determinada o restringida.

Ten en cuenta que el uso del aviso de consentimiento para convertir a un usuario de *no determinado* a *autorizado* es opcional. Pero, si no muestras el aviso, no puedes obtener la *autorización.* Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

| Valor ATT | Consentimiento  <br />(IDFA disponible) | Observaciones |
| --- | --- | --- |
| Restringido | No | <ul><li>Determinado por Apple en función de la edad del usuario y otros criterios. El usuario del dispositivo no puede cambiarlo.</li><li>El aviso no se puede mostrar a estos usuarios.</li></ul> |
| No determinado (hasta iOS 14.4) | Sí | Valor predeterminado |
| No determinado<br /><br />(a partir de iOS 14.5) | No | Valor por defecto |
| Denegado | No | Ocurre si se cumple alguna de las siguientes situaciones:<ul><li>Se estableció después de mostrar el aviso.</li><li>El usuario desactivó *Permitir que las aplicaciones soliciten el seguimiento* (interruptor maestro a nivel de dispositivo).</li><li>Antes de instalar iOS 14 en el dispositivo, LAT estaba activado.</li></ul> |
| Autorizado | Sí | Se estableció después de mostrar el aviso. |

**Implicaciones de la ATT**

Debido a la ATT, muchos usuarios no darán su consentimiento, el IDFA no estará disponible y no se permitirá el seguimiento. Como resultado, los anunciantes que hasta iOS 14.5 dependían de los reportes de atribución a nivel de usuario deben cambiar algunos análisis a métodos de atribución agregados y reportes. <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">Modelos de atribución de AppsFlyer</Anchor>.

Los datos relacionados con la atribución para una aplicación provienen de varias fuentes. Los identificadores disponibles y utilizados por cada uno difieren. La mayoría de datos se muestran mediante las herramientas de atribución tradicionales. Sin embargo, para las instalaciones atribuidas mediante SKAN, el reporte se realiza a través del panel de control de SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="¿Qué panel de control tiene la instalación?">

En iOS 14 se puede atribuir una instalación tanto a los paneles de control tradicionales como a los de SKAN. Además, dependiendo del contexto de la fuente de medios, puede atribuirse como orgánica en un panel de control y como no orgánica en el otro.

</Accordion>

## Conocimientos importantes de iOS 14

#### Artículos y enlaces de iOS 14 y SKAN

| Área | Artículo | Interés especial: preguntas frecuentes, discrepancias, comparaciones |
| --- | --- | --- |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">Campos de raw data de SKAN</Anchor> | Campos de raw data de SKAN adicionales que admiten did\_win y SKAN 3.0 |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Tiempo desde la instalación de la aplicación hasta la actualización del panel de control</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Métricas orgánicas en el contexto de SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Atribución de AppsFlyer frente a atribución de SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">Preguntas frecuentes sobre las discrepancias de SKAN</Anchor></li></ul> |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation">Interoperabilidad de partners de SKAN</Anchor> (sección del artículo) | <Anchor target="_blank" href="/marketers/es/docs/skan-integrated-partners-list">Lista de partners integrados de SKAN</Anchor> |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads">Integración de Anuncios de Meta y AppsFlyer SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Resolución de problemas y discrepancias</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Diferencias de medición y sincronización</Anchor></li></ul> |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-snapchat">Interoperabilidad de Snapchat y AppsFlyer SKAN</Anchor> | <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-snapchat#discrepancies-guide">Guía de discrepancias</Anchor> |
| Privacidad | <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada agregada (AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework#funciones-afectadas-por-la-aap">Funciones afectadas por la AAP</Anchor></li></ul> |
| Privacidad | <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">Fuentes de medios restringidas</Anchor> | <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Campos de raw data restringidos</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/es/docs/preparing-for-the-app-store-review-nutrition-labels">Etiquetas nutricionales: preparación para la revisión del App Store</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Configuración de la ATT en la aplicación</Anchor> (Guía del SDK para desarrolladores) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">Acerca de las redes de autorreporte (SRN) como Google, Anuncios de Meta, etc.</Anchor> | <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#ios-145-srn-attribution">¿Dónde se reportan las instalaciones de SRN?</Anchor> |
| Facturación | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Facturación para aplicaciones iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Impacto de la disponibilidad del IDFA en la atribución y la medición">

#### **Métricas**

Ten en cuenta que, cuando un IDFA no está disponible, las siguientes métricas pueden verse afectadas:

| Métricas | Aumenta | Disminuye | Observaciones |
| --- | --- | --- | --- |
| /docs/apply-aggregated-advanced-privacy-framework#aap-central-switch | Orgánico | No orgánico |  |
| Cómo activar y desactivar la AAP | Instalaciones | Reinstalaciones |  |
| Reorientación | Instalaciones orgánicas y eventos in-app | Re-engagements, reatribuciones |  |
| Apple Search Ads | -- | -- | Sin cambios. Tanto los usuarios que dan su consentimiento, como los que no, se atribuyen correctamente. |

#### **Enlaces profundos**

Los enlaces profundos diferidos que utilizan el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">método heredado de onConversionDataSuccess</Anchor> pueden no funcionar para iOS 14.5+, ya que requieren datos de atribución que pueden no estar disponibles debido a la protección de la privacidad.

Recomendamos el uso de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">enlaces profundos unificados (UDL)</Anchor>. Los UDL cumplen con los estándares de privacidad de iOS 14.5+ y solo devuelven los parámetros relevantes para los enlaces profundos y enlaces profundos diferidos: `deep_link_value` y `deep_link_sub1.` Los parámetros de atribución como `media_source`, `campaign` y `af_sub1-5` devuelven null y no se pueden usar para propósitos de enlaces profundos.

</Accordion>

## Preguntas frecuentes: iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="¿Qué sucede con una aplicación que usa una versión del SDK anterior a V6+?">

Para las aplicaciones que utilizan una versión del SDK anterior a V6.0:

* SKAdNetwork y Apple Search Ads no funcionarán.
* Si envías la aplicación al App Store, probablemente será rechazada.

Para aplicaciones que usan un SDK anterior a V6.10: SKAN 4 no funcionará.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="¿Es obligatorio mostrar el aviso de ATT?">

N.º Solo necesitas pedir el consentimiento de ATT si quieres hacer un *seguimiento* de un usuario, recopilar el IDFA, o ambos.

</Accordion>

## Preguntas frecuentes:

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="¿Cómo sé cuándo recibiré los postbacks y si serán de SKAN 3 o SKAN 4?">

El tipo de postback de SKAN que recibes está determinado por una variedad de factores, incluyendo qué modo usas en Conversion Studio, qué red de publicidad usas y qué versión de iOS tienen tus usuarios.

Estos factores afectan a lo siguiente:

* Versión del postback: SKAN 3 o SKAN 4. <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#principles-and-flow">Aprender más</Anchor>
* Ventana 1 (AW): para SKAN 4, es de 48 horas. Para SKAN 3, se basa en la ventana de actividad. Nota: Si Conversion Studio no es SKAN 4, pero la firma de la red de publicidad sí lo es, la ventana se basa en la ventana de actividad o 48 horas, lo que sea menor.
* Retraso del postback: horas después de la instalación cuando llega el postback de SKAN. Esto depende de cuándo se cierra la ventana. <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">Aprender más</Anchor>
* Temporizador continuo: para SKAN 3, la ventana de actividad se puede extender hasta 63 días; el postback solo llega después de que se cierre la ventana.

El siguiente diagrama de flujo explica esto con mayor detalle.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="En SKAN, ¿estoy limitado a un cierto número de identificadores de fuentes/ID de campaña por red de publicidad?">

Sí. Anteriormente el límite era de 100 ID de campaña. Sin embargo, desde SKAN 4, los ID de campaña se denominan identificadores de fuente jerárquicos, y el límite es de 10 000. El identificador de fuente es un número entero de 4 dígitos.

Las redes de publicidad asignan el identificador de fuente SKAN a su ID de campaña.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="¿Cuál es el caso de uso del raw data de SKAN?">

* Usa el raw data para agregar dimensiones que no están disponibles a través de las API agregadas.
* Ajusta fácilmente los procesos de importación de raw data existentes para consumir raw data de SKAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="¿Por qué los valores de conversión que recibo no coinciden con mi configuración en AppsFlyer Conversion Studio?">

Normalmente, esto sucede por que hay otro SDK en tu aplicación con la capacidad de establecer valores de conversión, el cual entra en conflicto con tu SDK de AppsFlyer y los valores de conversión que has configurado en AppsFlyer. Asegúrate de no tener otro SDK que establezca valores de conversión integrado en tu aplicación.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="¿Por qué los datos agregados en mi panel de control de SKAN no coinciden con las cifras del raw data en mis reportes de SKAN Data Locker?">

A menudo, esta discrepancia se debe a que se miran los reportes de Data Locker en el lugar equivocado. Los datos de Google pueden tardar hasta 13 días en recibirse. Y en los reportes de raw data, los datos se escriben el día en que se reciben, no acumulativamente. Por lo tanto, para obtener unas métricas correctas para las instalaciones relacionadas con una fecha específica, también es necesario mirar todos los reportes 13 días después de esa fecha.

Ejemplo: En el reporte del 12 de junio, se muestran 100 instalaciones de Google ocurridas el 11 de junio. En el reporte del 24 de junio, se indica que ocurrieron 100 instalaciones MÁS el pasado 11 de junio. Deberás consultar todos los reportes de los últimos 13 días (del 12 al 24 de junio) y agregarlos en función del momento de la instalación o de la marca de tiempo de la red de publicidad, para obtener una lectura precisa de las 200 instalaciones totales ocurridas el 11 de junio.

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/getting-started-onboarding-for-marketers#paso-3-configuración-de-atribución">Introducción a AppsFlyer paso a paso</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=medici%C3%B3n-de-la-atribuci%C3%B3n-en-un-entorno-att h_01HE0C8YXSXSX003X0671Z97KZ=medici%C3%B3n-de-la-atribuci%C3%B3n-en-un-entorno-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=conocimientos-importantes-de-ios-14 h_01HE0C8YXS3BH109DF1Y1KNK5P=conocimientos-importantes-de-ios-14 ios-14-and-skan-articles-and-links=art%C3%ADculos-y-enlaces-de-ios-14-y-skan h_01HE0C8YXSPZKBWXC51Z2636R0=art%C3%ADculos-y-enlaces-de-ios-14-y-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=m%C3%A9tricas h_01HE0C8YXSJMYN81FKPCA8ATK7=m%C3%A9tricas deep-linking=enlaces-profundos h_01HE0C8YXS6ADG1SQCMVP0W69B=enlaces-profundos faq%E2%80%94ios-14=preguntas-frecuentes-ios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=preguntas-frecuentes-ios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=preguntas-frecuentes h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=preguntas-frecuentes how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=consulta-tambi%C3%A9n" />
