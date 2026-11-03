---
title: Métricas de actividad en My Dashboards
metadata:
  keywords:
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
    - Ad Networks
  created_at: '2025-09-09T10:46:09Z'
  edited_at: '2026-08-12T11:50:24Z'
  id: 38874924986001
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/38874924986001
---
> **En resumen:** Utiliza las métricas de actividad en <Anchor target="_blank" href="/marketers/es/docs/my-dashboards">My Dashboards</Anchor> para evaluar rápidamente el rendimiento de la aplicación, detectar tendencias de engagement, analizar ingresos y detectar problemas con antelación, en cualquier rango de fechas, con mayor precisión y flexibilidad.

> 📘 **Advertencia**
>
> Las métricas de ingresos netos se implementarán gradualmente para los clientes durante julio-agosto de 2026. Si todavía no las ves, no hace falta hacer nada; estarán disponibles para tu cuenta durante este periodo. Consulta <Anchor target="_blank" href="/marketers/es/docs/bulletin-cohort-and-activity-metrics-update-in-my-dashboards">Boletín: Actualización de métricas de cohortes y actividad en My Dashboards</Anchor>.

## Acerca de las métricas de actividad

Las métricas de actividad en My Dashboards permiten a los usuarios analizar datos de Actividad, LTV y Cohorte en un solo lugar. Esto te permite monitorear el rendimiento del negocio y obtener información más profunda al:

* Analizar **la actividad del usuario y la retención** con relevancia en tiempo real.
* Medir **el rendimiento de eventos, ingresos y tendencias de sesiones.**  
  Obtener visibilidad unificada a través de **LTV, Actual y Cohorte** en un solo tablero.
* Personalizar informes utilizando **desglose diario o mensual** (Usuarios activos).

Nota: En Mis Tableros, el término A**ctividad** ha sido renombrado a **Actual**. Este cambio aclara que estas métricas reflejan acciones reales de los usuarios durante el rango de fechas seleccionado y no están vinculadas a la agregación de LTV. Actual también es el período predeterminado para Sesiones, Ganancia Bruta y Ingresos Totales.

## Información del dashboard

**Vista de la actividad.**

Diseñado para el monitoreo de alto nivel, la plantilla de **vista de la actividad** ayuda a los marketers a evaluar rápidamente el rendimiento de la aplicación, identificar tendencias de engagement, analizar ingresos y detectar problemas temprano, lo que permite decisiones más rápidas y basadas en datos en campañas y plataformas.

**Agregar widgets a tu dashborad**

Puedes agregar widgets a tu tablero haciendo clic en el botón **+ Crear nuevo** en la parte superior derecha del tablero, y seleccionar el tipo de widget que deseas crear: Tabla, KPI, Gráfico, tabla de eventos in-app, gráfico de eventos in-app, o métrica personalizada. Puedes encontrar instrucciones detalladas <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#add-widget">aquí</Anchor>

**Agrega métricas a tu gráfico o tabla**

En Configuración del gráfico o Configuración de la tabla, haz clic en el signo más +.

Luego puedes agregar una dimensión Agrupar por y seleccionar Filtros.

Puedes encontrar instrucciones detalladas <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#add-metric">aquí</Anchor>

## Métricas de actividad disponibles

* Todas las métricas además de Usuarios activos, Usuarios activos en los últimos 31 días y DAU/MAU también admiten períodos de cohorte y LTV.

| **Métrica** | **Descripción** |
| --- | --- |
| Usuarios activos | <ul><li>Número de usuarios únicos activos que abrieron la aplicación al menos una vez durante el período seleccionado, basado en sesiones, según la configuración de desglose de tiempo seleccionada.</li><li>Si se selecciona diario, se muestra como DAU.</li><li>Si se selecciona mensual, se muestra como MAU.</li><li>Cuando se ve en gráficos de líneas, gráficos de columnas o una tabla agrupada por fecha, se muestra como DAU.</li><li>Para obtener información sobre cómo consultar informes de datos en bruto para DAU y MAU, consulte: Calcular usuarios activos diarios y mensuales (DAU y MAU)</li></ul> |
| Usuarios activos en los últimos 31 días | Número de usuarios únicos (contados solo una vez) que abrieron la aplicación al menos una vez durante los últimos 31 días (no basado en el mes calendario). |
| DAU/MAU | La tasa de usuarios que regresan (fidelidad).<br /><br />Una tasa de DAU/MAU del 50% significa que el usuario promedio abrió la aplicación en 15 de los 31 días anteriores.<br /><br />La tasa DAU/MAU mide la fidelidad del usuario y ofrece una instantánea de su retención.<br /><br />Fórmula: Usuarios activos diarios / Usuarios activos en los últimos 31 días. |
| Sesiones | Sesiones durante el rango de fechas seleccionado. |
| Ingresos totales | Ingresos generados durante el periodo seleccionado. Los ingresos consisten en compras dentro de la aplicación y ingresos por publicidad. |
| Ejemplo | Ingresos netos del periodo seleccionado, agregados a partir del parámetro de evento af\_net\_revenue. Para las aplicaciones que usan los ingresos de tienda de ROI360, se trata de los ingresos brutos menos las comisiones de la tienda de aplicaciones y los impuestos (neto = bruto - comisiones de la tienda - impuestos); las aplicaciones que envían af\_net\_revenue por su cuenta definen el cálculo. |
| Primeras visitas | Número de primeras visitas a una aplicación web. Se contabiliza en las filas donde conversion\_name = first\_visit. Disponible solo para aplicaciones web. |
| Revisitas | Número de visitas recurrentes no orgánicas a una aplicación web. Se contabiliza en las filas donde conversion\_name = revisit. Disponible solo para aplicaciones web. |
| Adquisición de usuarios | Disponible para atribución multiplataforma o aplicaciones web. En las aplicaciones web, Adquisición de usuarios refleja Primeras visitas, a menos que se configure un evento de adquisición de usuarios. En las aplicaciones móviles, Adquisición de usuarios equivale a instalaciones. Al ver varias aplicaciones juntas, Adquisición de usuarios = instalaciones + primeras visitas (o el evento web personalizado configurado por el cliente). |

## Métricas disponibles en la aplicación

| **Métrica** | **Descripción** |
| --- | --- |
| Tasa de conversión | Porcentaje de usuarios únicos (atribuciones) que realizan el evento. Fórmula: Usuarios únicos del evento / Atribuciones x 100 |
| Usuarios Únicos | Número de usuarios únicos (atribuciones) que realizan el evento |
| Recuento promedio | Número promedio de veces que se realizó este evento por atribución.<br /><br />Fórmula: Recuento de eventos / atribuciones |
| Costo Efectivo por Adquisición (eCPA) | Costo efectivo por acción (evento).<br /><br />Fórmula: Costo / Usuarios únicos del evento |
| Recuento | Número de veces que se realizó este evento |
| Ingresos | Ingresos generados por este evento específico |
| OPCIONAL | Ingresos medios por usuario.<br /><br />Fórmula: Ingresos / Usuarios únicos (usuarios = atribuciones) |
| Ganancia bruta | Ingresos - Costos |
| ROAS (Retorno de la Inversión Publicitaria) | Retorno sobre el gasto publicitario<br /><br />Fórmula: Ingresos / Costo * 100 |
| ROI (Retorno de la Inversión) | Retorno de la inversión<br /><br />Fórmula: (Ingresos - Costo) / Costo * 100 |
| Ejemplo | Ingresos netos generados por este evento específico (después de las comisiones de la tienda de aplicaciones y los impuestos). |
| ARPU neto | Ingresos promedio de este evento por atribución.<br /><br />Fórmula: Ingresos netos / usuarios únicos (usuarios = atribuciones) |
| Beneficio neto | Ingresos netos - Costo |
| ROAS neto | Retorno del gasto publicitario, basado en ingresos netos.<br /><br />Fórmula: Ingresos netos / Costo * 100 |
| ROI neto | Retorno de la inversión basado en ingresos netos.<br /><br />Fórmula: (Ingresos netos - Costo) / Costo * 100 |

**Métricas de ingresos netos**

Las métricas netas (ingresos netos, ROI neto, ROAS neto, ARPU neto y beneficio neto) muestran los ingresos netos en lugar de los ingresos brutos. Los ingresos netos son el valor que se envía en af\_net\_revenue y el anunciante define el cálculo (por ejemplo, los ingresos después de las comisiones de la tienda o los impuestos, el margen bruto o los ingresos después de las comisiones del servicio). En las aplicaciones que usan los ingresos de tienda de ROI360, AppsFlyer los calcula como el bruto menos las comisiones y los impuestos de la tienda de aplicaciones (Neto = Bruto - comisiones de la tienda - impuestos).

El valor procede del parámetro af\_net\_revenue de tus eventos in-app, del mismo modo que las métricas de ingresos habituales usan af\_revenue. El valor está en la divisa de la transacción, indicada por af\_currency (USD de forma predeterminada).

Cómo se rellena el valor:

* Si **los ingresos de tienda de ROI360** están habilitados para la aplicación, AppsFlyer completa af\_net\_revenue automáticamente en los eventos de compra in-app y de suscripción que registra.
* De lo contrario, el valor procede del parámetro af\_net\_revenue que envías en el evento in-app.
* Si ninguna de las dos opciones proporciona ingresos netos, la métrica muestra N/A.

Consulta <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue">Acerca de los ingresos de tienda de ROI360</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">Eventos in-app: estructura del evento</Anchor>.

## Dimensiones de filtro y agrupación soportadas

Puede agrupar y filtrar métricas de actividad usando:

* Desglose diario del tiempo
  * Anuncio
  * ID del anuncio
  * Conjunto de anuncios
  * ID del conjunto de anuncios
  * Aplicación
  * Tipo de atribución
  * Tipo de interacción atribuida
  * Campaña
  * ID de campaña
  * Canal
  * Geografía
  * Fecha
  * Palabras clave
  * Fuente de medios
  * Agencia
  * ID de sitio
  * Destino de engagement
  * Subparámetro 1
  * Comentario
  * Tipo de interacción atribuida
  * Destino de engagement
  * Tienda de aplicaciones de la instalación
* Desglose mensual del tiempo
  * Aplicación
  * Campaña
  * ID de campaña
  * Geografía
  * Mes
  * Fuente de medios
  * Agencia

## Especificaciones y limitaciones

| **Especificaciones** | **Nota** |
| --- | --- |
| Actualización de los datos | El tiempo real no es compatible con las aplicaciones web, de CTV o de PC y consola para las métricas de cohorte y actividad.<br /><br />**Nota:** Las métricas de LTV para aplicaciones de CTV y de PC y consola están disponibles en tiempo real; esta limitación solo se aplica a los datos de actividad y cohorte. |
| Granularidad temporal | En las aplicaciones web, CTV y de PC y consola, los datos de cohorte y actividad solo están disponibles con granularidad diaria. Los desgloses semanales y mensuales no son compatibles con estas plataformas. |
| Ingresos de anuncios | Los datos en tiempo real no son compatibles. |
| Métricas de ingresos netos: periodos | Compatible con las métricas de actividad y cohorte. No es compatible con LTV. |
| Métricas de ingresos netos: actualización de los datos | El tiempo real no es compatible. Los datos están disponibles a partir del día siguiente. |
| Métricas de ingresos netos: ingresos por publicidad | Los eventos de ingresos por publicidad no se incluyen en las métricas de ingresos netos.<br /><br />**Consejo:** Para ver los ingresos netos que incluyen ingresos por anuncios, crea una métrica personalizada que añada los ingresos por anuncios a los ingresos netos, por ejemplo: Ingresos netos + Ingresos (evento: af\_ad\_revenue). Consulta <Anchor target="_blank" href="/marketers/es/docs/beta-set-up-custom-metrics-in-my-dashboards">Configurar métricas personalizadas en My Dashboards</Anchor>. |
| Métricas de ingresos netos - fuente de atribución | No es compatible con SKAN ni con SSOT. |
| Métricas de ingresos netos - plataformas | Solo Android e iOS (móvil). |
| Zonas horarias | Todas las métricas son compatibles en zonas horarias locales excepto las que son solo UTC:<ul><li>Usuarios activos en los últimos 31 días</li><li>DAU/MAU</li><li>Usuarios activos con agrupación mensual (MAU)</li></ul> |
| Gráficos | Actualmente soporta **DAU** en formato de línea o columna |
| Widgets | KPI y los widgets de tabla soportan todas las métricas de actividad. |
| Rango de datos diario | Limitado a 62 días por vista |
| Eventos de desinstalación | No incluido en los datos de actividad |
| Datos históricos | Hasta 3 años (diariamente) |
| Agrupación geográfica | Basado en la geolocalización en el momento de la instalación; limitado a las 62 principales geolocalizaciones |
| Métricas de sesión | <ul><li>Los datos de actividad están unificados para UA y retargeting a partir del 1 de febrero de 2025</li><li>Puedes ver una vista de Retargeting filtrando los valores de **Tipo de atribución** por **Re-engagements** y **Reatribuciones**.</li></ul> |
| Métricas de vista unificada | Todas las métricas son compatibles solo en vista unificada |
| Usuarios únicos de eventos en la aplicación y Usuarios activos | **Usuarios únicos de eventos en la aplicación** y **Usuarios activos** en Mis Tableros se basan en un algoritmo de estimación estadística que reduce el conteo duplicado y proporciona una vista consistente de la actividad del usuario. |
| El tiempo real no es compatible. | Si el intervalo de fechas seleccionado incluye hoy y días anteriores, y el widget no está agrupado por fecha, los datos de hoy no se muestran. |

<div data-zendesk-anchors="h_01KXNJ1RB3ZWVG9SASCRNSS9N1=advertencia about-activity-metrics=acerca-de-las-m%C3%A9tricas-de-actividad h_01K4Q11V7F3KCHT69SC90J54Q6=acerca-de-las-m%C3%A9tricas-de-actividad dashboard-information=informaci%C3%B3n-del-dashboard h_01K4Q11V7MV95K09VC3D0190V3=informaci%C3%B3n-del-dashboard available-activity-metrics=m%C3%A9tricas-de-actividad-disponibles h_01K4Q11V7QY8DB1FNRG3AJBDWR=m%C3%A9tricas-de-actividad-disponibles available-inapp-metrics=m%C3%A9tricas-disponibles-en-la-aplicaci%C3%B3n h_01K4Q11V7Z4Y4TWT5E2J0354JA=m%C3%A9tricas-disponibles-en-la-aplicaci%C3%B3n supported-filter-and-group-by-dimensions=dimensiones-de-filtro-y-agrupaci%C3%B3n-soportadas h_01K4Q11V86S336QH6ZG5XS5AWG=dimensiones-de-filtro-y-agrupaci%C3%B3n-soportadas specifications-and-limitations=especificaciones-y-limitaciones h_01K4Q11V8DCBT4CY5MJZ44X7SX=especificaciones-y-limitaciones" />
