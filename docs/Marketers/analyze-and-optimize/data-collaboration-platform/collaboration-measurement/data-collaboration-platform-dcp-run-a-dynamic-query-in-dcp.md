---
title: >-
  Plataforma de colaboración de datos (DCP) - Ejecuta una consulta dinámica en
  DCP
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-10-15T11:14:42Z'
  edited_at: '2026-10-20T03:54:59Z'
  id: 51953788887569
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/51953788887569
---
> **Resumen:** Dynamic Query te permite ejecutar tus propias consultas SQL directamente sobre los datos de tu Plataforma de colaboración de datos (DCP). Consulta tus propios datos, tus propios datos de atribución de AF o los datos compartidos dentro de una colaboración para responder preguntas concretas sin tener que configurar un reporte.

<div id="about-dynamic-query" />

## Acerca de Dynamic Query

Dynamic Query te permite ejecutar consultas ad hoc y personalizadas sobre tus datos de DCP en tiempo real para responder a tus preguntas específicas de colaboración de forma rápida y eficiente.

* Permite que un colaborador segmente mejor tus datos antes de crear una audiencia.
* Crea tu propia lógica de medición de campaña con Dynamic Query.

Dynamic Query funciona de forma diferente según consultes tus propios datos o datos compartidos en una colaboración.

<div id="before-you-start" />

## Antes de empezar

Antes de poder ejecutar cualquier consulta, <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configura el destino de tu cloud bucket</Anchor>. Este paso es obligatorio, porque cada consulta se ejecuta en tu propio cloud bucket y escribe los resultados directamente en tu almacenamiento. AppsFlyer no almacena los resultados de tu consulta, por lo que tus datos permanecen dentro de tu propio entorno en la nube.

<div id="run-a-query-on-your-own-data" />

## Ejecuta una consulta sobre tus propios datos

En las siguientes secciones se explica cómo acceder a los datos que te pertenecen y consultarlos. El panel Fuentes aquí solo muestra las fuentes que te pertenecen; no puedes añadir la fuente de un colaborador en esta vista. Si quieres consultar los datos compartidos contigo en una colaboración, consulta [Ejecuta una consulta con datos de colaboración](#).

<div id="access-dynamic-query" />

### Accede a Dynamic Query

1. En AppsFlyer, ve al menú lateral > **Colaborar** > **Data Clean Room**.
2. Selecciona la pestaña **Dynamic Query**.

<div id="write-your-query-on-your-own-data" />

### Escribe tu consulta sobre tus propios datos

1. Explora los campos de la fuente en el panel Fuentes. Haz clic en un campo para previsualizar sus valores únicos.

   <div id="note" />

   > 📘 **Nota:**
   >
   > Esto ayuda a que tus filtros coincidan con datos reales antes de escribir la consulta. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboración de datos (DCP): crea y gestiona fuentes</Anchor>.

2. Escribe tu consulta libremente, a nivel raw o agregado; tú eliges. Todas las fuentes de aquí te pertenecen, así que no hay comprobación de permisos ni requisito de GROUP BY.

   <div id="note-1" />

   > 📘 **Nota:**
   >
   > Si también eres cliente de AppsFlyer, puedes consultar así tus datos de atribución de AF, pero los resultados solo se muestran agregados, aunque sean tus propios datos.


<div id="run-a-query-with-collaboration-data" />

## Ejecuta una consulta con datos de colaboración

En las siguientes secciones se explica cómo acceder a los datos compartidos contigo en una colaboración y cómo consultarlos. Si, en cambio, quieres consultar solo los datos que te pertenecen, consulta [Ejecuta una consulta sobre tus propios datos](#).

<div id="access-dynamic-query-in-a-collaboration" />

### Accede a Dynamic Query en una colaboración

1. En AppsFlyer, ve al menú lateral > **Colaborar** > **Data Clean Room**.
2. Selecciona la pestaña **Colaboraciones** y, después, la colaboración correspondiente.
3. Selecciona la pestaña **Dynamic Query**.

Cuando consultas datos compartidos en una colaboración, Dynamic Query puede acceder a cualquier fuente <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">añadida a esa colaboración</Anchor>.

<div id="write-your-query-with-collaboration-data" />

### Escribe tu consulta con datos de colaboración

1. Explora los campos de la fuente en el panel de fuentes. Haz clic en un campo para previsualizar sus valores distintos.

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Esto ayuda a que tus filtros coincidan con datos reales antes de escribir la consulta. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboración de datos (DCP): crea y gestiona fuentes</Anchor>.

2. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-sharing-permissions">Consulta el tipo de permiso de la fuente</Anchor> para determinar si tu consulta necesita una unión. Hay dos tipos de permisos:

   

| Tipo de permiso | ¿Se requiere una unión? | Nivel de resultado |
| --- | --- | --- |
| Intersectados | Sí, debes unirla con tu propia fuente | Solo agregados |
| Todos los datos | No, puedes consultarla libremente | Solo agregados |

3. Escribe tu consulta con una cláusula GROUP BY o una función de agregación, como `COUNT(*)`.

   <div id="important" />

   > 🚧 **Importante**
   >
   > Una fuente que no te pertenece siempre devuelve resultados agregados, independientemente del tipo de permiso con el que se comparta. Los resultados a nivel sin procesar solo están disponibles para las fuentes que te pertenecen.


<div id="explore-sample-queries" />

## Explora consultas de ejemplo

Los siguientes ejemplos muestran cómo funciona cada tipo de permiso en la práctica.

<div id="h_01M56WAZ8WGKHMG3BJYXNYHJT4" />

<Accordion title="Encuentra candidatos para colaboraciones con marcas">

Esta consulta usa el permiso All Data para encontrar las principales marcas en una colaboración por número de clientes e ingresos durante los últimos 60 días.

```sql
SELECT
    t.brand_name,
    COUNT(DISTINCT t.hashed_email) AS total_clients,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 60) AND current_date()
GROUP BY t.brand_name
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8WWJ78CQCK17FXWCWF" />

<Accordion title="Crea un segmento de retargeting para un club de fidelización">

Esta consulta usa el permiso Intersected. Combina los datos de tu club de fidelización con los datos de compras de un colaborador por país durante los últimos 30 días.

```sql
SELECT
    t.country,
    COUNT(DISTINCT l.hashed_email) AS loyalty_members,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
JOIN <my_loyalty_club_table> l ON l.hashed_email = t.hashed_email  -- required join satisfies intersection permission
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
    AND t.brand_name = '<collaborator_brand_name>'
GROUP BY t.country
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8W6KN04JZN06T75A9A" />

<Accordion title="Descubre audiencias antes de una campaña de adquisición de usuarios (UA)">

Esta consulta usa el permiso All Data para segmentar las transacciones de un colaborador por país y categoría, de modo que puedas descubrir audiencias de alto valor antes de crear una para adquisición de usuarios.

```sql
SELECT
    t.country,
    t.category,
    COUNT(DISTINCT t.hashed_email) AS total_buyers,
    COUNT(*)                       AS total_purchases,
    SUM(t.revenue)                 AS total_revenue,
    AVG(t.revenue)                 AS avg_order_value
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
GROUP BY t.country, t.category
ORDER BY total_buyers DESC
LIMIT 20;
```

</Accordion>

<div id="view-and-download-query-results" />

## Ver y descargar resultados de consultas

En las siguientes secciones se explica cómo ejecutar tu consulta y gestionar sus resultados.

<div id="h_01M56WAZ8WXC0X46H2P3AY3GFX" />

<Accordion title="Modos de ejecución de consultas dinámicas">

Todas las consultas se ejecutan en uno de estos dos modos:

* **Datos de muestra** (predeterminado): se ejecuta sobre un pequeño subconjunto de tus datos para que puedas perfeccionar la consulta antes de ejecutarla en el conjunto de datos completo.
* **Todos los datos**: se ejecuta sobre la fuente completa. Solo este modo tiene un botón de **descarga**.

<div id="note-3" />

> 📘 **Nota:**
>
> No confundas el modo de ejecución **Todos los datos** con el tipo de permiso **All Data**. Los tipos de permiso controlan a qué puede acceder un colaborador. Los modos de ejecución controlan cuánto de tu propia consulta se ejecuta.

</Accordion>

<div id="h_01M56WAZ8W2E7P4S60T0WJ4NNF" />

<Accordion title="Historial de consultas">

Tu consulta y sus resultados se mantienen al cambiar entre pestañas y hojas de trabajo. Puedes abrir varias hojas de trabajo para trabajar en distintas consultas a la vez.

Selecciona **Todas las ejecuciones** para ver tu historial de consultas, incluido el estado y la duración de cada ejecución, en el modo Datos de muestra o en el modo Todos los datos.

</Accordion>

<div id="h_01M56WAZ8WCVEVWRQK68736H02" />

<Accordion title="Límites y descargas de resultados">

Los resultados se muestran en páginas de 100 filas, hasta un máximo de 10 páginas (1.000 filas en total). Para verlo todo, descarga los resultados. El recuento total de resultados siempre se muestra, aunque sea mayor que lo que aparece en pantalla. Este recuento tiene un límite de 10 millones, así que, si tu recuento real de resultados es de 20 millones, el recuento mostrado seguirá indicando 10 millones.

Puedes descargar hasta 1 millón de filas directamente. Si tus resultados son mayores, Dynamic Query te redirige a tu <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">cloud bucket</Anchor> en su lugar. Tu cloud bucket admite hasta 10 millones de filas. Si necesitas más, contacta con tu Customer Success Manager (CSM) para ampliar este límite.

</Accordion>

<div id="privacy-and-query-restrictions" />

## Privacidad y restricciones de las consultas

Dynamic Query aplica protecciones de privacidad en varios niveles:

* Las fuentes no propias siempre devuelven resultados agregados; consulta [Ejecutar una consulta con datos de colaboración](#).
* Los campos de identificadores de tipo clave, como AppsFlyer ID, Android ID e IDFA (Identifier for Advertisers), siempre se devuelven como valores hashed en los resultados de la consulta.
* Los valores distintos no están disponibles para los campos clasificados como Keys, como AppsFlyer ID o Android ID, al explorar el panel de Fuentes.

<div id="traits-and-limitations" />

## Características y limitaciones

| Rasgo | Description |
| --- | --- |
| Límite de visualización de resultados | 1.000 filas (100 filas por página, hasta 10 páginas) |
| Límite de descarga | 1 millón de filas directamente, 10 millones de filas a través de tu cloud bucket; contacta con tu CSM para ampliarlo |
| Configuración del cloud bucket | Obligatorio antes de poder ejecutar cualquier consulta, no solo antes de descargar |
| Modos de ejecución | Datos de muestra (predeterminados, sin descarga) y todos los datos (fuente completa, descarga disponible) |

<div id="see-also" />

## Consulte también

* <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-dynamic-query">Consulta dinámica de Data Clean Room</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-guide">Guía de la Plataforma de colaboración de datos (DCP)</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-sharing-permissions">Permisos para compartir de la Plataforma de colaboración de datos (DCP)</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">Plataforma de colaboración de datos (DCP): crear una colaboración</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">Diccionario de campos de raw data</Anchor>

<div data-zendesk-anchors="h_01M56WAZ8VZKYM6TP7AYGKQA52=acerca-de-dynamic-query h_01M56WAZ8VQ4D6NHCNJ463ZJE4=antes-de-empezar h_01M56WAZ8VPZPM8P1H0DNVTTA6=ejecuta-una-consulta-sobre-tus-propios-datos h_01M56WAZ8VQ4NNZEYAX4ZAZCFZ=accede-a-dynamic-query h_01M56WAZ8VPG7QEAPSSBG11N11=escribe-tu-consulta-sobre-tus-propios-datos h_01M56WAZ8VDWA030BB53YP1TR2=nota h_01M56WAZ8VBVRQV8B7J0TA21ZM=nota-1 h_01M56WAZ8V82DRQ92ZPC3KFZYJ=ejecuta-una-consulta-con-datos-de-colaboraci%C3%B3n h_01M56WAZ8VK33RR50SWQYV7KE0=accede-a-dynamic-query-en-una-colaboraci%C3%B3n h_01M56WAZ8WXRM23PDCTA11APA2=escribe-tu-consulta-con-datos-de-colaboraci%C3%B3n h_01M56WAZ8WM0ZHFDKTT7AZ1CG8=nota-2 h_01M56WAZ8W01XKEQDYVZCQ23ZZ=importante h_01M56WAZ8W348ZTS79F23MAP3C=explora-consultas-de-ejemplo h_01M56WAZ8WZ23RCK7TYQC2FPZD=ver-y-descargar-resultados-de-consultas h_01M56WAZ8WK936BRP4F7VHG954=nota-3 h_01M56WAZ8W471Z9B14ZJ3V41VC=privacidad-y-restricciones-de-las-consultas h_01M56WAZ8WCVFPD8JMHQ39HMEJ=caracter%C3%ADsticas-y-limitaciones h_01M56WAZ8WBY66ZBNHSNGFAJKD=consulte-tambi%C3%A9n" />
