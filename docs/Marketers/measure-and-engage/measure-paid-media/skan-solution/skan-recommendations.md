---
title: Recomendaciones de SKAN
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2026-08-12T12:21:47Z'
  id: 7078169815057
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/7078169815057
---
> **De un vistazo**: Utiliza las recomendaciones de SKAN para optimizar la configuración de los valores de conversión y recibir mediciones de la actividad post-instalación más precisas.

## Visión general

SKAdNetwork (SKAN), parte de Apple iOS, permite a los anunciantes medir el rendimiento de la campaña y al mismo tiempo preservar la privacidad del usuario. Con SKAdNetwork, la actividad post-instalación se mide utilizando solo los números (valores de conversión) entre 0 y 63.

AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Conversion Studio</Anchor> te ofrece la máxima flexibilidad para que cada valor de conversión (CV) cuente. Tú determinas con precisión qué datos de medición deben codificarse en el CV, incluidas las actividades que deben medirse durante el periodo post-instalación y durante cuánto tiempo.

Sin embargo, dada la limitada capacidad de medición de SKAN, puede ser difícil decidir qué se debe medir (por ejemplo, ingresos, eventos in-app o retención) y cómo utilizar mejor los CV entre 0 y 63. Las decisiones pueden basarse en estimaciones, ensayo y error, o en herramientas de aprendizaje de máquina que utilizan datos internos de la aplicación. Y las mediciones no siempre son todo lo precisas que podrían ser.

Recomendaciones de AppsFlyer SKAN:

* Ofrecen sugerencias para mejorar la configuración actual de tu CV y optimizar la eficacia de tu CV y la precisión de las mediciones.
* Resuelven las dificultades que puedas tener para tomar decisiones sobre la configuración del CV.
* Se basan en tu vertical y geolocalización específicas, los datos de la aplicación SKAN y no SKAN, y el comportamiento de los usuarios.

## Recomendaciones

<div id="revenue" />

<Accordion title="Ingresos">

#### **Comprender las recomendaciones sobre ingresos**

Contar con el esquema de configuración de ingresos adecuado es crucial para obtener reportes de ingresos precisos.

La configuración del valor de conversión (CV) que tienes para reportar los ingresos no es necesariamente 100 % exacta, y los ingresos reportados por SKAN pueden diferir de los ingresos reales. Por ejemplo, el ARPPU real (reportado por AF) puede ser de 10 USD, pero tu configuración actual de CV reporta un SKAN ARPPU de 7 USD, lo que significa que SKAN, por cada usuario de pago, reporta 3 USD menos en ingresos.

AppsFlyer comprueba diariamente tus datos de ingresos no SKAN (que son 100 % precisos), para hacer recomendaciones personalizadas que puedes implementar para mejorar la precisión de tus reportes de ingresos SKAN. Las recomendaciones también se basan en la configuración de la ventana de actividad guardada en Conversion Studio, así como en tu vertical y geolocalización específicas, y el comportamiento de los usuarios de la aplicación.

Las recomendaciones:

* Te proporcionan una imagen clara del rendimiento de la campaña con reportes de ingresos precisos.
* Te ahorran valores de conversión utilizando menos rangos para medir con precisión los ingresos.
* Ten en cuenta tanto las compras in-app como los ingresos por publicidad.

#### **Disposición de las recomendaciones de ingresos**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>Ventana de actividad guardada en tu configuración de Conversion Studio, durante la cual se miden los ingresos de SKAN.</span></td></tr><tr><td><p><span>B</span></p></td><td><span>Ingresos medios reales de la aplicación por usuario de pago (ARPPU), basados en datos precisos de usuarios orgánicos y no orgánicos atribuidos a través de los métodos de AppsFlyer (AF).</span></td></tr><tr><td><p><span>C</span></p></td><td><p><span>ARPPU con la configuración actual (SKAN ARPPU), es decir el ARPPU medido <span>según tu configuración actual en Conversion Studio para la ventana de actividad y la configuración de CV para los reportes de ingresos.</span></span></p></td></tr><tr><td><span>D</span></td><td><p>ARPPU estimado: el ARPPU previsto para el número de rangos seleccionado. Se calcula tomando todos los datos de ingresos de los últimos 14 días de la aplicación, independientemente del método de atribución (como SKAN o el método clásico), y dividiéndolos entre el número de usuarios de pago. <span>Consulta F y G</span></p><p><span><strong>Nota:</strong> </span><span>Es importante destacar que este número no está disponible en otros dashboards de AF.</span> Aquí mostramos el ARPPU (ingresos medios por usuario de pago), mientras que en otros dashboards presentamos el ARPU (Ingreso promedio por usuario).</p></td></tr><tr><td><p><span>E</span></p></td><td><p>Error aproximado: la d<span>iferencia entre B y C. Puede ser un error positivo o negativo, dependiendo de si tu SKAN ARPPU está reportado de más o de menos.</span></p><p><span>Ejemplo: si el ARPPU real es de 10 USD y el SKAN ARPPU es de 7 USD, el error aproximado es un reporte del 30 % menos (-3 USD por usuario).</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>Recomendaciones para la configuración de tus ingresos en SKAN. Selecciona el número de rangos que deseas incluir en tu configuración.</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>Tu configuración actual de ingresos tal y como está establecida en Conversion Studio.</span><span></span></p></td></tr></tbody></table>

#### **Utilizar las recomendaciones de ingresos**

**Requisito previo:** las recomendaciones de ingresos requieren al menos 14 días de datos de ingresos.

> 📘 **Advertencia**
>
> Esto se actualiza todos los días. Esto significa que el periodo de recomendación de los 14 días anteriores se cuenta desde ayer. Por ejemplo, si hoy es 28 de agosto. Los datos de entrada de la recomendación van del 13 al 27 de agosto.

**Para usar las recomendaciones de ingresos:**

1. En AppsFlyer, dependiendo de si usas SKAN 4, el modo personalizado o el fijo, ve a:
   * **Configuración** > **SKAN Conversion Studio** > **SKAN 4** > **Ingresos generales/Evento in-app**.
   * **Configuración** > **SKAN Conversion Studio** > **Personalizado** > **Ingresos generales/Evento in-app**.
   * **Configuración** > **SKAN Conversion Studio** > **Ingresos**.
2. Si ya tienes configurado un rango de ingresos, omite este paso. Si no tienes configurado un rango de ingresos, configúralo ahora.  
   Cuando se configura el rango de ingresos, se muestra información sobre la precisión de tu configuración y el error aproximado.
3. Haz clic en **Comprobar recomendaciones**.  
   Se muestra información sobre tu configuración actual, junto con las recomendaciones de rango de ingresos y la precisión estimada (error aproximado) que proporcionarán si se implementan. Se proporcionan recomendaciones tanto para mantener como para cambiar el número de rangos.
4. Selecciona una recomendación de rango.
5. Haz clic en **Aplicar recomendación**.
   * Si tienes la configuración de ingresos en modo personalizado, se aplica la recomendación.
   * Si tienes la configuración de ingresos en modo fijo (ingresos), debes registrar la recomendación de rango. Para ello, ve a **SKAN Conversion Studio** > **Personalizado** > **Ingresos generales**, y configura el rango recomendado.
6. Haz clic en **Guardar**.
   * Si luego cambia algo en la configuración de tus ingresos, puedes volver a comprobar tu configuración y ver las nuevas recomendaciones.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HGSZ05CH4P8BQT23VYH6DKVP=visi%C3%B3n-general recommendations=recomendaciones h_01HGSZ05CHPZKWKY7MR6MA68YZ=recomendaciones h_01HGSZ05CH2RG3514N576ZGDFM=revenue understanding-revenue-recommendations=comprender-las-recomendaciones-sobre-ingresos h_01HGSZ05CHC93SHP28DN9EK27N=comprender-las-recomendaciones-sobre-ingresos revenue-recommendations-layout=disposici%C3%B3n-de-las-recomendaciones-de-ingresos h_01HGSZ05CH5DVKAQ24EED16JRN=disposici%C3%B3n-de-las-recomendaciones-de-ingresos using-revenue-recommendations=utilizar-las-recomendaciones-de-ingresos h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=utilizar-las-recomendaciones-de-ingresos h_01HGSZCYCWRYEJPWZKDBC9SX8H=advertencia" />
