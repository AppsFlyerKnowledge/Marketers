---
title: '[Beta] Configurar métricas personalizadas en My Dashboards'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2025-01-01T09:21:05Z'
  edited_at: '2026-08-22T00:03:32Z'
  id: 31400289569169
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/31400289569169
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **En resumen:** Define tus propias métricas y úsalas para ver datos en My Dashboards.

<div id="about-custom-metrics" />

## Acerca de métricas personalizadas

Las métricas personalizadas te permiten adaptar el análisis de datos a las necesidades únicas de tu negocio al definir cálculos basados en datos existentes. Proporcionan más control y flexibilidad que las métricas estándar, lo que te permite combinar múltiples métricas, crear proyecciones y personalizar KPIs.

Por ejemplo, en lugar de métricas genéricas como "Ingresos" o "Clics", puedes crear fórmulas para tus casos de uso únicos, como:

* Predicción de ingresos D60 = Ingresos D1 * 3
* Tasa de clics para comprar = Clics / af\_purchase [usuarios únicos]

Las métricas personalizadas son compatibles con todos los tipos de widgets en My Dashboards, incluidos tablas, gráficos y KPIs. Ya sea que seas un marketer que rastrea el ROI de la campaña, un gerente de producto que monitorea el compromiso o un analista que pronostica el rendimiento, las métricas personalizadas mejoran tu capacidad para analizar tendencias, identificar oportunidades y tomar decisiones basadas en datos para las necesidades únicas de tu negocio, todo directamente desde tu dashboard.

**Nota**: Las dimensiones personalizadas que creas están a nivel de cuenta, lo que significa que diferentes aplicaciones en la misma cuenta de AppsFlyer pueden usar las mismas dimensiones personalizadas.

<div id="procedures" />

## Procedimientos

<div id="create-a-custom-metric" />

<Accordion title="Crear una métrica personalizada">

**Para crear una métrica personalizada**:

1. En tu dashboard:
   * Haz clic en **+ Crear nuevo** > **Métricas personalizadas**.
   * En cualquier gráfico o tabla, en el menú desplegable **Métricas**, haz clic en **+ Crear métrica personalizada**.
2. Nombra tu métrica. En la parte superior del editor de métricas personalizadas, ingresa un nombre descriptivo para tu métrica (por ejemplo, "IPM").
3. Elige un **Tipo de métrica**. Selecciona si la métrica es numérica, un porcentaje o monetaria (moneda).
4. Define tu fórmula de métrica. Elige entre:
   * Comenzar rápidamente: Utiliza las fórmulas sugeridas (mostradas en el menú de la izquierda del editor de métricas personalizadas). Luego, utiliza el editor para modificar la plantilla según tus necesidades específicas, como seleccionar diferentes eventos in-app o modificar multiplicadores u otros parámetros. Por ejemplo, para la plantilla `Retention rate D2 / Retention rate D7`, puedes reemplazar D2 y D7 con diferentes eventos o períodos de tiempo.
   * Usa el editor interactivo: Agrega métricas y operadores (usando los botones), y números (usando tu teclado) para definir tu fórmula.
5. Previsualiza la fórmula en el campo de fórmula fx.
6. [Opcional] Si creaste la métrica personalizada desde el dashboard general, haz clic en **Guardar y agregar al gráfico**.  
   Se crea un nuevo gráfico que incluye tu métrica personalizada.
7. Haz clic en **Guardar**.
   * Si creaste la métrica personalizada desde un widget, se agrega automáticamente al gráfico o tabla.
   * Si creaste la métrica personalizada en el dashboard general, ahora puedes agregarla a cualquier widget que desees.

</Accordion>

<div id="edit-a-custom-metric" />

<Accordion title="Editar una métrica personalizada">

Puedes editar una métrica personalizada ya sea desde el dashboard o desde dentro de un widget específico.   
[Práctica recomendada]: ¡**Importante**! Cualquier cambio que realices en una métrica personalizada es a nivel de cuenta, lo que significa que los cambios afectan la métrica para todos los usuarios y dashboards.

**Para editar una dimensión personalizada desde el dashboard**:

1. En tu dashboard, haz clic en **+ Crear nuevo** > **Métricas personalizadas**.
2. En el menú del lado izquierdo del editor de métricas personalizadas, bajo Mis métricas personalizadas, encuentra la métrica que deseas editar y haz clic en el icono **Editar**.
3. Haz los cambios que desees en la fórmula de la métrica personalizada.
4. Haz clic en **Guardar**.

**Para editar una dimensión personalizada de un widget**:

1. En cualquier gráfico o tabla, en el menú desplegable **Métricas**, encuentra la métrica que deseas editar y haz clic en el ícono **Editar**.
2. En el menú del lado izquierdo del editor de métricas personalizadas, bajo Mis métricas personalizadas, encuentra la métrica que deseas editar y haz clic en el icono **Editar**.
3. Haz los cambios que desees en la fórmula de la métrica personalizada.
4. Haz clic en **Guardar**.

</Accordion>

<div id="delete-a-custom-metric" />

<Accordion title="Eliminar una métrica personalizada">

Puedes eliminar una métrica personalizada ya sea desde el dashboard o desde dentro de un widget específico.   
[Práctica recomendada]: ¡**Importante**! Cualquier eliminación de una métrica personalizada es a nivel de cuenta, lo que significa que la métrica se elimina para todos los usuarios y dashboards.

**Para eliminar una dimensión personalizada desde el dashboard**:

1. En tu dashboard, haz clic en **+ Crear nuevo** > **Métricas personalizadas**.
2. En el menú del lado izquierdo del editor de métricas personalizadas, bajo Mis métricas personalizadas, encuentra la métrica que deseas eliminar y haz clic en el icono **Eliminar**.

**Para eliminar una dimensión personalizada de un widget**:

* En cualquier gráfico o tabla, en el menú desplegable **Métricas**, encuentra la métrica que deseas eliminar y haz clic en el ícono **Eliminar**.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="best-practices" />

<Accordion title="Mejores prácticas">

* **Comienza simple**: Comienza con métricas básicas y agrega complejidad progresivamente según sea necesario y a medida que te familiarices más con el desarrollo de fórmulas.
* **Alinéalo con los objetivos**: Asegúrate de que cada métrica esté relacionada con un objetivo o pregunta empresarial específica.
* **Documenta tus fórmulas**: Mantén una referencia de tus fórmulas personalizadas para facilitar las actualizaciones o la depuración.
* **Revisar periódicamente**: Evalúa regularmente tus métricas para asegurarte de que sigan siendo relevantes.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Accesibilidad a nivel de cuenta | Todos los miembros de la cuenta pueden crear, ver, editar y eliminar cualquier métrica personalizada. Esto incluye métricas creadas por otros usuarios. |
| Límite de métricas personalizadas | <ul><li>Las métricas personalizadas tienen un límite de 100 métricas personalizadas por cuenta.</li><li>Actualmente, las métricas personalizadas solo se admiten con el desglose diario. No se admiten los desgloses semanales y mensuales.</li></ul> |
| Complejidad de la fórmula | Máximo 5 métricas por fórmula de métrica personalizada. |
| Restricción de anidamiento | Las métricas personalizadas no se pueden usar como componentes en otras fórmulas de métricas personalizadas. |

</Accordion>

<div data-zendesk-anchors="about-custom-metrics=acerca-de-m%C3%A9tricas-personalizadas h_01H8XWQHPERAEDQVD275TFVC5B=acerca-de-m%C3%A9tricas-personalizadas procedures=procedimientos h_01H8XWQHPESY4DDDJSTR0JDHNB=procedimientos h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-metric h_01H8XWQHPE22WZ46RTNCYKX96F=edit-a-custom-metric h_01H8XWQHPED4PFPJP2044FT1H8=delete-a-custom-metric additional-information=informaci%C3%B3n-adicional 01JGGT56V05BJRCV9Q572JJR3W=informaci%C3%B3n-adicional 01JGK1XAVB3M5KDA59A9ZASM2K=best-practices h_01H8XWQHPF7WZ7B5Q7T9CHADRK=traits-and-limitations" />
