---
title: Información sobre el modelo de atribución mejorada
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2025-11-30T11:53:35Z'
  edited_at: '2026-08-12T11:56:44Z'
  id: 41442782045073
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/41442782045073
---
> **En resumen:** El modelo de atribución mejorada mejora la precisión de la atribución al atribuir únicamente los clics y las impresiones aptos cuando se detecta flooding de clics y de impresiones en el dispositivo.

<div id="what-is-the-enhanced-attribution-model" />

## ¿Qué es el modelo de atribución mejorada?

El modelo de atribución mejorada combate el flooding de engagement al considerar para la atribución únicamente las señales que reflejan el engagement real del usuario. Cuando AppsFlyer detecta patrones de engagement que indican flooding, AppsFlyer solo tiene en cuenta los clics y las impresiones aptos. Como resultado, la atribución se basa en el último clic apto, que no es necesariamente el clic más reciente.

El modelo funciona continuamente en segundo plano y se aplica a todo el tráfico relevante sin requerir ninguna acción por parte de los anunciantes o Partners.

<div id="how-the-enhanced-attribution-model-helps" />

## Cómo ayuda el modelo de atribución mejorada

El modelo de atribución mejorada ayuda a Anunciantes, Ad network y Partners de las siguientes maneras:

* Anunciantes
  * Aumenta la precisión de la atribución tanto en los flujos de adquisición como de retargeting.
  * Permite escalar con confianza en canales de alto crecimiento sin comprometer la calidad de la atribución.
  * Mejora la protección del gasto al basar las decisiones en datos de atribución más fiables.
  * Ayuda a identificar y priorizar canales y partners de alto valor.

* Ad networks y partners
  * Garantizan que la atribución se base en la actividad real del usuario.
  * Mejoran la precisión de los reportes y las decisiones de Optimización.
  * Mantienen una competencia de atribución coherente y justa.
  * Reducen el efecto de volúmenes de engagement inflados artificialmente.

<div id="how-the-enhanced-attribution-model-works" />

## Cómo funciona el modelo de atribución mejorada

Así es como funciona:

1. AppsFlyer recibe registros de engagement de múltiples fuentes de medios, como clics o impresiones.
2. Cuando AppsFlyer detecta un patrón de flooding durante el proceso de atribución, un modelo adicional ayuda a seleccionar los engagements aptos.

<div id="where-enhanced-attribution-data-appears-in-appsflyer-reports" />

## Dónde aparecen los Datos de atribución de atribución mejorada en los reportes de AppsFlyer

Puedes ver los datos de atribución mejorada en los siguientes canales:

<div id="raw-data-reports" />

### Reportes de raw data

**Total candidates for attribution** es una métrica que se muestra en los Reportes de raw data. Indica el número de engagements que habrían entrado en la competencia de atribución antes de que se apliquen la lógica de atribución mejorada y la lógica de detección de fraude de Protect360. Dado que la elaboración de informes de contribuyentes refleja los resultados posteriores al filtrado, el número total de candidatos puede ser significativamente mayor que el número de contribuyentes.

Esta métrica puede indicar un posible "engagement flooding" y ayuda a los anunciantes a entender el volumen de engagement y los patrones de las fuentes. No representa el número de dispositivos ni de usuarios.

<div id="note" />

> 📘 **Nota:**
>
> La métrica también puede ser mayor que cero en las instalaciones orgánicas, ya que los engagements orgánicos aún pueden entrar en la competencia de atribución antes de la validación.

<div id="protect360-dashboards-and-reports" />

### Dashboards y reportes de Protect360

* Media de engagements por instalaciones comprometidas y no comprometidas
* Tendencias de atribución segmentadas por instalaciones comprometidas y no comprometidas

**Nota:** Los datos comprometidos empiezan a aparecer en el dashboard de Protect360 solo después de que se añada una aplicación a la atribución mejorada. Sin embargo, los datos comprometidos y no comprometidos pueden seguir mostrándose para periodos históricos anteriores a que la aplicación se añadiera a la función.

<div data-zendesk-anchors="what-is-the-enhanced-attribution-model=qu%C3%A9-es-el-modelo-de-atribuci%C3%B3n-mejorada h_01KEC2P5M5EPDA22XZ6XSQRZFQ=qu%C3%A9-es-el-modelo-de-atribuci%C3%B3n-mejorada how-the-enhanced-attribution-model-helps=c%C3%B3mo-ayuda-el-modelo-de-atribuci%C3%B3n-mejorada h_01KEC2P5M5NZ5F134TPRPN8K15=c%C3%B3mo-ayuda-el-modelo-de-atribuci%C3%B3n-mejorada how-the-enhanced-attribution-model-works=c%C3%B3mo-funciona-el-modelo-de-atribuci%C3%B3n-mejorada h_01KEC2P5M59QCG1E5C74ERASYE=c%C3%B3mo-funciona-el-modelo-de-atribuci%C3%B3n-mejorada where-enhanced-attribution-data-appears-in-appsflyer-reports=d%C3%B3nde-aparecen-los-datos-de-atribuci%C3%B3n-de-atribuci%C3%B3n-mejorada-en-los-reportes-de-appsflyer h_01KEC2P5M52MG4EWD63PE761G9=d%C3%B3nde-aparecen-los-datos-de-atribuci%C3%B3n-de-atribuci%C3%B3n-mejorada-en-los-reportes-de-appsflyer raw-data-reports=reportes-de-raw-data h_01KEC2P5M5VTJ5YF4NJ13ZY0NF=reportes-de-raw-data h_01KEC2P5M5T43VGNWF9HW9K76Z=nota protect360-dashboards-and-reports=dashboards-y-reportes-de-protect360 h_01KEC2P5M5TAHRRC3YCSB5EQE5=dashboards-y-reportes-de-protect360" />
