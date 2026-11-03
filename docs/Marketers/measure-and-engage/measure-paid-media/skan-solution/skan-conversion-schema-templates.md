---
title: Plantillas de esquemas de conversión de SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-10-06T09:58:43Z'
  edited_at: '2026-08-12T12:21:28Z'
  id: 28968432692241
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/28968432692241
---
> **En resumen:** las plantillas de esquemas de conversión de SKAN son plantillas listas para usar. Simplifican la configuración de SKAN al ofrecer plantillas basadas en una combinación de datos de la industria y datos específicos de la aplicación, y proporcionan insights del sector y mejores prácticas. Las plantillas de esquemas de conversión de SKAN se encuentran en Conversion Studio.

## Beneficios clave

* Estas plantillas agilizan la configuración de SKAN al permitir crear un esquema de conversión en solo unos clics.
* Al aprovechar las mejores prácticas de la industria y los insights, los profesionales del marketing pueden perfeccionar su esquema y aumentar la confianza en su eficacia utilizando plantillas basadas en datos del sector combinados con datos específicos de la aplicación.

## Cómo empezar

1. En el menú de la izquierda, ve a **Configuración > SKAN Conversion Studio**
2. Haz clic en el botón **Plantillas de la industria**
3. Se abrirá la ventana de plantillas
4. Selecciona de la lista de industrias y verticales del lado izquierdo
5. En el lado derecho de la pantalla se muestra el aspecto del esquema de conversión sugerido
   1. Usa el interruptor **Modo SKAN 4** para activar o desactivar el soporte de SKAN 4  
      **Nota:** con SKAN 4, se sugieren tres ventanas de actividad, junto con valores de conversión aproximados para la primera ventana. Si está desactivado, solo se sugieren valores de conversión detallados para la primera ventana.
   2. Utiliza el ? haz clic en los iconos junto a cada medición para ver una explicación de por qué se sugirió ese evento o esa medición, junto con información de referencia
6. Haz clic en **Select & customize**  
   **Nota:** Esto todavía no guardará tu configuración
7. Se te redirigirá a la página de edición de **Conversion Studio**
   1. Usa las <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#componentes-de-medición">funciones y herramientas estándar</Anchor> de Conversion Studio para personalizar la plantilla según las necesidades de tu aplicación

## ¿Qué son las plantillas de esquemas de conversión de SKAN?

Las plantillas de conversión de SKAN sugieren asignaciones de valores de conversión para actividades significativas del usuario posteriores a la instalación, adaptadas por industria y vertical. Las sugerencias se pueden personalizar para adaptarse a las necesidades específicas de la aplicación, combinando insights basados en datos y experiencia del sector.

### Estructura de la plantilla

* **Estrategia**: define si el enfoque debe ponerse en eventos in-app, en la medición de ingresos o en una combinación de ambos. La estrategia está predefinida, pero se puede personalizar en la página de edición de Conversion Studio.
* **Versión de SKAN**: indica qué versión de SKAN tiene soporte, ya sea SKAN4 o versiones anteriores. De forma predeterminada, SKAN 4 es compatible. Si SKAN 4 está desactivado, se desactivan las mediciones del valor de conversión aproximado y Conversion Studio cambia al modo «personalizado».
* **Mediciones**: La plantilla sugiere actividades específicas posteriores a la instalación para medir. Esto incluye eventos específicos o rangos de ingresos, así como el uso de funciones como Funnel y Single Source of Truth (SSOT), que se sugiere de forma predeterminada.
  * Las mediciones sugeridas se pueden personalizar en la página de edición de Conversion Studio.
  * Los eventos preseleccionados se adaptan a cada plantilla.
  * Los rangos de ingresos se personalizan en función de los datos específicos de la aplicación mediante modelos avanzados de recomendación de ingresos  Cuando no hay suficientes datos históricos, se usan datos de la industria para hacer sugerencias.

## ¿Qué es el esquema de conversión de SKAN?

El esquema de conversión de SKAN define la configuración de medición del framework SKAdNetwork (SKAN). Especifica qué métricas de engagement del usuario (por ejemplo, eventos in-app o ingresos) se medirán y se reportarán. SKAdNetwork no reporta directamente el engagement posterior a la instalación con la app. En su lugar, reporta «Valores de conversión», que el Desarrollador de apps asigna a actividades significativas posteriores a la instalación. Esta asignación se conoce como el esquema de conversión de SKAN.

## ¿En qué se basan estas plantillas?

Las plantillas se basan en un análisis basado en datos de los esquemas de conversión por vertical, junto con investigación cualitativa e insights de expertos de la industria. Algunas de las sugerencias se basan en datos específicos de la aplicación, como se indica a continuación.  
Los pasos clave del proceso de creación de plantillas:

1. **Aplicaciones líderes muestreadas**: Identificamos aplicaciones de muestra para el análisis cuantitativo. Con conjuntos de datos internos y externos, clasificamos las aplicaciones en jerarquías verticales. Para cada subvertical, analizamos decenas de aplicaciones líderes y las clasificamos según el volumen de tráfico de SKAN que generaban.
2. **Definimos la estrategia**: A partir de datos de benchmark de la industria, establecimos una estrategia estandarizada adaptada a cada vertical. Después de analizar el porcentaje de aplicaciones de cada vertical que miden eventos, ingresos o ambos, seleccionamos una estrategia para cada vertical. También tuvimos en cuenta el recuento medio de eventos y el volumen de aplicaciones que utilizan la función funnel para determinar el número de eventos por plantilla y si un funnel es adecuado.
3. **Creamos grupos de eventos colectivos**: Asignamos los distintos nombres de eventos, según los definen las aplicaciones, a grupos predefinidos, y cada grupo reflejaba una colección de eventos de negocio similares.
4. **Eventos sugeridos**: Identificamos los eventos de negocio más recomendados para medir dentro de cada vertical. Utilizando los grupos de eventos creados en el paso anterior, analizamos el porcentaje de aplicaciones que medían cada evento. Tras la revisión por parte de expertos de la industria y la validación con decenas de esquemas de conversión de las aplicaciones líderes, seleccionamos la mejor combinación de eventos para cada subvertical.
5. **Rangos de ingresos definidos**: Sugerimos los mejores rangos de ingresos para maximizar la precisión de los ingresos reportados. Cuando un usuario abre el cuadro de diálogo de la plantilla, comprobamos en tiempo real si la aplicación es apta para recibir recomendaciones de ingresos en función de nuestros modelos avanzados. Si es así, el modelo crea rangos de ingresos personalizados con los datos de la aplicación. Si no, sugerimos rangos de ingresos basados en datos de la industria obtenidos al aplicar nuestros modelos de recomendación de ingresos a los datos de las aplicaciones líderes del vertical.
6. **Eventos específicos de la aplicación mapeados**: Después de que la aplicación aplique una plantilla específica, asignamos los eventos in-app relevantes a los nombres de eventos empresariales predeterminados en la plantilla del vertical. La aplicación debe verificar entonces que se han seleccionado los eventos correctos.

<div data-zendesk-anchors="intro=beneficios-clave h_01J9GM9NV7HDA1N9WZH4Y6K1VH=beneficios-clave how-to-get-started=c%C3%B3mo-empezar h_01J9GME5K3C0BMPVK6K1D46HT0=c%C3%B3mo-empezar what-are-skan-conversion-schema-templates=qu%C3%A9-son-las-plantillas-de-esquemas-de-conversi%C3%B3n-de-skan h_01J9GMP733JQSY60AJH22FGPRS=qu%C3%A9-son-las-plantillas-de-esquemas-de-conversi%C3%B3n-de-skan template-structure=estructura-de-la-plantilla h_01J9GMPACY2TY0MYNEEJNW39Z5=estructura-de-la-plantilla what-is-skan-conversion-schema=qu%C3%A9-es-el-esquema-de-conversi%C3%B3n-de-skan h_01J9GMQX4R8BMSQQ3XW4C97VEJ=qu%C3%A9-es-el-esquema-de-conversi%C3%B3n-de-skan what-are-these-templates-based-on=en-qu%C3%A9-se-basan-estas-plantillas h_01J9GMR0FTV2Q75N9N5FQZW98F=en-qu%C3%A9-se-basan-estas-plantillas" />
