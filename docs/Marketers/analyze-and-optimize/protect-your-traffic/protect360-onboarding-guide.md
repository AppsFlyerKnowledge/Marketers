---
title: Guía de onboarding de Protect360
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-08-12T11:55:25Z'
  id: 34554022072209
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/34554022072209
---
> **En resumen:** Protege rápida y eficazmente tus inversiones de marketing siguiendo esta guía de onboarding paso a paso para maximizar tu valor de Protect360 en solo 6 semanas.

<div id="onboarding-timeline-and-what-to-expect" />

## **¿Cronología de onboarding y qué esperar?**

Esta guía describe un enfoque de onboarding gradual de 6 semanas:

* **Configuración (semanas 1–3)**: Integra y valida Protect360.
* **Optimización (semanas 3–5)**: Optimiza en función de los insights iniciales.
* **Reconciliación (semanas 5 a 6)**: Concilia los datos de fraude con los partners publicitarios.
* **Protección avanzada (semana 6+) [Opcional]**: Habilita capas avanzadas de protección contra el fraude.

<div id="about-protect360" />

## **Sobre Protect360**

Protect360 es una solución avanzada de protección contra el fraude diseñada para detectar, prevenir y responder al fraude publicitario. Impulsado por IA y con detección en tiempo real, ayuda a bloquear el fraude, reducir el gasto desperdiciado y proteger tu marketing de amenazas como la inyección de clics, las instalaciones falsas y los bots. Permite un control preciso y una transparencia total a través de funciones como las reglas de validación y Fraud Protection Studio.

<div id="setup-weeks-1-3" />

<Accordion title="Configuración (semanas 1-3)">

En este paso, la atención se centra en enviar datos in-app a AppsFlyer, configurar la configuración básica para la protección contra el fraude y alinear tus términos de Business Intelligence con los de AppsFlyer.

**Datos de eventos in-app**

Existen dos formas de enviar datos de eventos in-app a AppsFlyer: SDK y servidor a servidor (S2S). Dependiendo del método utilizado, puede ser necesario realizar alguna acción:

* **SDK**: No se requiere ninguna acción.
* **Servidor a servidor (S2S)** Asegúrate de que los eventos se envíen a través de la API3. <Anchor target="_blank" href="/marketers/es/docs/bulletin-upgrading-the-appsflyer-s2s-api">Saber más sobre cómo hacerlo aquí.</Anchor>

<div id="note" />

> 📘 **Nota**
>
> Si no estás seguro de cuál utilizas, confirma con tus equipos de desarrollo o de operaciones de marketing

<div id="fraud-protection-studio-settings" />

#### **Configuración de Fraud Protection Studio**

Fraud Protection Studio ofrece una forma de evaluar el impacto y el valor de las diferentes capas de la solución de protección contra el fraude de AppsFlyer. Te permite distinguir claramente entre la detección y la aplicación del fraude.

Comprender estas diferencias y las opciones disponibles es clave para tomar decisiones informadas:

* **Implemented** (predeterminado): Bloquea automáticamente la actividad fraudulenta en tiempo real o la marca como fraude posterior a la atribución si se detecta después de la instalación. Esto es ideal si la prevención inmediata del fraude se alinea con tus objetivos.
* **Tagged**: El fraude se detecta y etiqueta, pero sigue siendo válido para la atribución, lo que te permite analizar y revisar sin bloquear automáticamente. Elige esto si prefieres flexibilidad y un análisis inicial más profundo antes de aplicar.

<div id="note-1" />

> 📘 **Nota**
>
> Puedes cambiar (<Anchor target="_blank" href="/marketers/es/docs/user-management">solo administrador</Anchor>) entre los modos **Implemented** y **Tagged** en cualquier momento para que coincidan con los objetivos empresariales en evolución. <Anchor target="_blank" href="/marketers/es/docs/beta-fraud-protection-studio#key-concepts">Saber más aquí.</Anchor>

<Image alt="" src="https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png" width="624px" />

Consejo: En esta etapa, cuando tu equipo se familiarice con Protect360, te recomendamos encarecidamente que visites la tarjeta de <Anchor target="_blank" href="/marketers/es/docs/beta-fraud-protection-studio#app-detection-evaluation">**evaluación de detección de aplicaciones**</Anchor> en Fraud Protection Studio para probar y comprender esta configuración a nivel de aplicación.

<div id="data-connection-setup" />

#### **Configuración de conexión de datos**

Puedes exportar los datos de Protect360 de tres maneras: <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#sobre-los-informes-de-datos-sin-procesar-de-protect360">Reporte de raw data</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#pull-api">Pull API</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#data-locker">Data Locker</Anchor>. Sea cual sea la forma que elijas, es importante configurar tus conexiones de datos correctamente para garantizar la exactitud de los reportes de datos sobre fraude y un análisis eficaz.

<Image alt="" src="https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png" width="624px" />

<div id="important" />

> 🚧 **¡Importante!**
>
> Para obtener el valor completo de Protect360, exporta el <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#postattribution-reports">reporte posterior a la atribución</Anchor> cada 8 de cada mes, para que puedas reconsolidarte con los partners.

<div id="how-to-display-hijacked-installs-correctly-in-your-bi" />

#### **Cómo mostrar correctamente las instalaciones secuestradas en tu BI**

Para una mayor alineación y granularidad de los datos de protección contra el fraude dentro de tus sistemas, puedes **utilizar reportes de raw data, Pull API o Data Locker para ver correctamente las instalaciones secuestradas dentro de tu BI.**

<div id="raw-data-report" />

#### **Reporte de raw data**

Para mostrar las instalaciones secuestradas correctamente en tu BI:

1. Busca el campo **Valor del motivo del rechazo**.
2. Este campo se completará con uno de los siguientes:
   1. Blanco, orgánico, colaborador1, colaborador2, etc.
3. Informa a tu equipo de BI sobre el significado de cada uno, para que puedan alinear los términos y sus implicaciones.

* En blanco - No secuestrado
* Orgánico - cambia la atribución a orgánico
* Colaborador1, colaborador2, colaborador3, etc. - Atribución correcta a la fuente de medios especificada.

<div id="note-2" />

> 📘 **Nota**
>
> Para más información sobre tus datos **Tagged**, puedes ver los 4 reportes de raw data:
>
> * Instalaciones Tagged
> * Instalaciones Tagged posteriores a la atribución
> * Eventos in-app Tagged
> * Eventos in-app posteriores a la atribución

![](https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png)

<div id="pull-api" />

#### **API Pull**

Para mostrar las instalaciones secuestradas correctamente en tu BI:

4. Busca el campo **Valor del motivo del rechazo**.
5. Este campo se completará con uno de los siguientes:
   1. Blanco, orgánico, colaborador1, colaborador2, etc.
6. Informa a tu equipo de BI sobre el significado de cada uno de ellos para que puedan alinear los términos y sus implicaciones.

* En blanco - No secuestrado
* Orgánico - ajusta la atribución a orgánico
* Colaborador1, colaborador2, colaborador3, etc. - Atribución correcta a la fuente de medios especificada.

<div id="data-locker" />

#### **Casillero de datos**

Para mostrar las instalaciones secuestradas correctamente en tu BI:

7. Busca el campo **validation\_reason\_value**.
8. Este campo se completará con uno de los siguientes:
   1. Blanco, orgánico, colaborador1, colaborador2, etc.
9. Informa a tu equipo de BI sobre el significado de cada uno de ellos para que puedan alinear los términos y sus implicaciones.

* En blanco - No secuestrado
* Orgánico - ajusta la atribución a orgánico
* Colaborador1, colaborador2, colaborador3, etc. - Atribución correcta a la fuente de medios especificada.

<div id="validation-rules" />

#### **Reglas de validación**

Las reglas de validación te permiten agregar una capa de lógica empresarial a tu protección contra el fraude, adaptada a tu estrategia de marketing. Con las reglas de validación, puedes definir qué instalaciones se consideran válidas o inválidas en función de una variedad de parámetros en múltiples casos de uso.

Contacta con tu Customer Success Manager o Account Manager para obtener más información sobre las mejores prácticas recomendadas para tu vertical.

<div id="note-3" />

> 📘 **Nota**
>
> Para que las reglas sean lo más efectivas posible, se recomienda revisar tu estrategia de UA/marketing/compra de medios y evaluar qué tipos de instalaciones o eventos in-app coinciden con tus esfuerzos, para permitir o bloquear según tus necesidades. Por ejemplo, si no promocionas tu aplicación en el país (GEO) X, puedes crear una regla para bloquear automáticamente cualquier actividad de este tipo que llegue desde GEO X. Puedes crear varias reglas para alinear la protección con tu estrategia de marketing.

<div id="working-with-dashboards" />

#### **Trabajar con dashboards**

El <Anchor target="_blank" href="/marketers/es/docs/protect360-dashboard">dashboard</Anchor> de Protect360 proporciona una descripción general visual de tus datos de fraude, lo que te permite investigar más a fondo y comprender mejor la detección del fraude y su impacto en tus actividades.

<Image alt="" src="https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png" width="624px" />

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="Optimización (semanas 3–5)">

<div id="campaign-optimization" />

#### **Optimización de campañas**

En este paso, es hora de optimizar tu campaña para asegurarte de que estás aprovechando al máximo Protect360. Para hacer esto, debes:

* Consultar las [mejores prácticas](/docs/protect360-onboarding-guide#mejores-prácticas).
* [Revisar tu configuración de protección contra el fraude](/docs/protect360-onboarding-guide#revisar-tu-configuración-de-protección-contra-el-fraude)

<div id="best-practices" />

#### Mejores prácticas

* Combina datos en tiempo real y posteriores a la atribución para evaluar el rendimiento de la campaña en función de la calidad (retención, eventos in-app, etc.) y el fraude.
* Optimiza las campañas en función de site\_id o subsite\_id.
* Analiza las tasas y los tipos de fraude específicos de los partners.

<div id="review-your-fraud-protection-settings" />

#### Revisar tu configuración de protección contra el fraude

Revisa la [configuración de Fraud Protection Studio](/docs/protect360-onboarding-guide#configuración-de-fraud-protection-studio) para asegurarte de que aún se ajusten a tus objetivos.

<div id="note-4" />

> 📘 **Nota**
>
> Las instalaciones **Tagged** son un subconjunto de las válidas. Cambia al modo **Implemented** para bloquear en tiempo real según la detección de Protect360

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="Reconciliación (semanas 5 a 6)">

<div id="fraud-data-reconciliation" />

#### **Reconciliación de datos de fraude**

Después de implementar Protect360 y acumular varias semanas de datos de detección de fraude, es hora de conciliar tus insights sobre fraude con tus partners publicitarios.

Este paso crítico ayuda a garantizar que tú y tus partners estén alineados con el rendimiento de la campaña, los métodos de detección del fraude y la precisión.

Descarga tus <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide#postattribution-detection">datos posteriores a la atribución</Anchor> y colabora estrechamente con tus partners publicitarios para establecer referencias cruzadas entre las métricas de fraude. Esta reconciliación ayuda a identificar discrepancias, resolver conflictos de forma proactiva y fomentar la transparencia. Descubre <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks">aquí</Anchor> cómo conciliar los datos de fraude con los partners publicitarios.

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="Configuración avanzada de protección (semana 6+) [opcional]">

#### **Advanced Security Module**

Disponible exclusivamente para clientes Protect360, el Advanced Security Module está diseñado para aplicaciones de alto tráfico. Añade una capa de seguridad vital a tu SDK de Android, validando las solicitudes de red en tiempo real para bloquear las instalaciones falsas y el tráfico manipulado.

Al filtrar las señales no autorizadas en la fuente, ayuda a reducir las discrepancias de la tienda de aplicaciones, refuerza la precisión de la atribución y protege tus datos contra el sofisticado fraude cibernético.

Conacta con tu CSM o envía un correo electrónico a `<hello@appsflyer.com>`

</Accordion>

<div data-zendesk-anchors="what-to-expect=cronolog%C3%ADa-de-onboarding-y-qu%C3%A9-esperar h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=cronolog%C3%ADa-de-onboarding-y-qu%C3%A9-esperar about-protect360=sobre-protect360 h_01JSBWNSHDZ8J3B70KYEG2T03X=sobre-protect360 setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=nota fraud-protection-studio-settings=configuraci%C3%B3n-de-fraud-protection-studio h_01JSY4SNK5X23DBVD374FV12FG=configuraci%C3%B3n-de-fraud-protection-studio h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=nota-1 data-connection-setup=configuraci%C3%B3n-de-conexi%C3%B3n-de-datos h_01JSY4SNK57K77TBXZB92QPBKA=configuraci%C3%B3n-de-conexi%C3%B3n-de-datos h_01JVVK5Z1H0TZH02S76M7JRKWQ=importante how-to-display-hijacked-installs-correctly-in-your-bi=c%C3%B3mo-mostrar-correctamente-las-instalaciones-secuestradas-en-tu-bi h_01JVVJBVB4FRATEHVZ2Q7EWC54=c%C3%B3mo-mostrar-correctamente-las-instalaciones-secuestradas-en-tu-bi raw-data-report=reporte-de-raw-data h_01JWDAV3K7JF8ATZP88D4NQRW4=reporte-de-raw-data h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=nota-2 pull-api=api-pull h_01JWDAV8GC5N1859AD1PMEQXH9=api-pull data-locker=casillero-de-datos h_01JWDAVEVDAJD47WQYY0FNSPE9=casillero-de-datos validation-rules=reglas-de-validaci%C3%B3n h_01JSY4SNK5HAG08PAJQEPB7MQ4=reglas-de-validaci%C3%B3n h_01JVVK5Z1H05XX8BXECMXAJ4J7=nota-3 working-with-dashboards=trabajar-con-dashboards h_01JSY4SNK50RHSQ95E1E2ZK068=trabajar-con-dashboards optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 campaign-optimization=optimizaci%C3%B3n-de-campa%C3%B1as h_01JV255GGVBY8XGQS28F0QZRVH=optimizaci%C3%B3n-de-campa%C3%B1as best-practices=mejores-pr%C3%A1cticas h_01JV6WFR7MN2X8KTN7RMTXQ5KX=mejores-pr%C3%A1cticas review-your-fraud-protection-settings=revisar-tu-configuraci%C3%B3n-de-protecci%C3%B3n-contra-el-fraude h_01JV6WGDRP200GHN6MJNZJ5MQE=revisar-tu-configuraci%C3%B3n-de-protecci%C3%B3n-contra-el-fraude h_01JVVK5Z1HXPM2G6HAMTYV7MY5=nota-4 reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 fraud-data-reconciliation=reconciliaci%C3%B3n-de-datos-de-fraude h_01JV25RP3VAJBCEWWK2TEZFKB2=reconciliaci%C3%B3n-de-datos-de-fraude advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional h_01JV260Y9M3M6CC48854YHQ01S=advanced-security-module" />
