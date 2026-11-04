---
title: Medir las instalaciones asistidas
metadata:
  keywords:
    - Attribution
    - installs
    - Assisted
    - multi-touch
    - reporting
    - assisted intalls
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:21:25Z'
  edited_at: '2026-08-12T11:57:05Z'
  id: 207040506
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/207040506
---
> **De un vistazo:** Mide el impacto más amplio de las fuentes de medios que involucraron a tus usuarios y ayudaron antes del último toque.

<div id="assisted-installs" />

## Instalaciones asistidas

Las <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/assisted-installs-mobile-advertising-assists/">instalaciones asistidas</Anchor> (también conocida como atribución multi-touch) son instalaciones en las que la fuente de medios/campaña no tuvo el último toque, pero sí llegó al usuario antes de la instalación y durante la ventana de atribución. Una instalación puede tener hasta 3 instalaciones asistidas.

Los datos analíticos de las instalaciones asistidas están disponibles tanto a nivel de fuente de medios como de campaña para medir el impacto más amplio de cada fuente de medios y campaña.

<div id="view-assisted-installs-metrics-in-the-overview-dashboard" />

### Ver métricas de instalaciones asistidas en el panel de control general

**Para ver las instalaciones asistidas en el panel de control general**:

1. En AppsFlyer, en el menú lateral, selecciona **Análisis** > **General**.
2. Selecciona el reporte de Vista General Ampliada.
3. Desplázate hacia abajo hasta los gráficos de tendencias en el tiempo.
4. Selecciona la dimensión **Fuente de medios** o **Campaña**.
5. Selecciona la métrica **Instalaciones asistidas**.  
   Se muestra el gráfico de instalaciones asistidas. El azul indica las instalaciones no orgánicas y el naranja indica las instalaciones asistidas. ![AssitedInstallWidget.png](https://files.readme.io/a2fb5fb1f7414ede9a96858e325688d0c60b2ff910e24bc86e5597160c7548ca-33302646504977.png)

<div id="why-are-assists-important" />

### ¿Por qué son importantes las asistencias?

En muchos casos, los usuarios potenciales se familiarizan con una aplicación a través de la fuente de asistencia, pero no la instalan por algún motivo. Por lo tanto, medir y reconocer las asistencias es importante en la optimización y medición de las campañas.

<div id="assisted-installs-reporting" />

### Reportes de instalaciones asistidas

AppsFlyer atribuye hasta 3 redes contribuyentes además del origen de instalación atribuido.

En los dashboards agregados y reportes, las (hasta 3) redes de colaboradores se consolidan en una métrica llamada "Assisted Installs (Instalaciones Asistidas)". Es decir, 1 instalación puede tener hasta 3 instalaciones asistidas contadas.

En los reporte de raw data, los datos de las redes contribuyentes se desglosan en campos separados para los Colaboradores 1-3.

[![](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)

Para cada una de las redes contribuyentes, el reporte de raw data incluye lo siguiente:

* Nombre de la red (fuente de medios)
* Nombre de la campaña
* Tiempo de engagement (tiempo de toque)
* Tipo de engagement (clic o impresión)
* Nombre de la agencia involucrada (partner), si hubiera una
* Tipo de coincidencia (<Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::cecc12c5">Igual que los tipos de coincidencia de instalación.</Anchor>)

Consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reportes-del-viaje-del-usuario">raw data de la trayectoria del usuario.</Anchor>

<div id="note" />

> 📘 **Advertencia**
>
> **Fuentes de medios con restricciones de datos a nivel de usuario**
>  Si una <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">fuente de medios restringe los datos a nivel de usuario</Anchor>, no se le puede atribuir como colaboradora ni como asistencia en una atribución ganadora. Esto significa que determinadas fuentes no aparecen como colaboradoras aunque hayan interactuado con el usuario antes de la instalación.

<div id="note-1" />

> 📘 **Advertencia**
>
> Varias de las principales redes de publicidad <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">restringen el intercambio de datos con plataformas de terceros</Anchor>, incluidas las agencias. Por lo tanto, las instalaciones asistidas no aparecen en el panel de control de la agencia para estas redes.

En los reportes de raw data, los datos de las redes contribuyentes se desglosan en campos separados para **Colaboradores 1–3**.

<div id="total-candidates-field" />

### Campo de candidatos totales

Además de los campos **Colaboradores 1–3**, el campo `total_candidates` muestra el número de engagement (como clics o impresiones) asociados al mismo dispositivo en el momento de la instalación o del re-engagement.

Sin embargo, no todos los engagement contabilizados en `total_candidates` pueden optar a la atribución. Por ejemplo, algunos engagement pueden haber sido:

* Fuera de la ventana de lookback
* Bloqueados por la protección contra el fraude
* Afectados por la configuración de integración de la app o de partners
* No cumplir de otro modo las condiciones de atribución de AppsFlyer

En la práctica, esto significa:

* Si la instalación se atribuyó a orgánico, es porque ninguno de los engagements de `total_candidates` cumplía todas las condiciones necesarias para la atribución.
* Si no hay colaboradores, es por la misma razón: los engagement registrados en `total_candidates` no podían servir como colaboradores.

En resumen, `total_candidates` indica los engagement recibidos, que no son necesariamente candidatos válidos para la atribución. Es posible ver un valor en este campo y que la instalación siga atribuida a orgánico o sin colaboradores.

<div id="note-2" />

> 📘 **Consideraciones para agencias**
>
> El soporte de AppsFlyer no proporcionará explicaciones ni desgloses a nivel de engagement de `total_candidates` debido a la complejidad de la lógica de atribución.

<div data-zendesk-anchors="assisted-installs=instalaciones-asistidas h_01HCBC922K9PCDXGDCCVEARADH=instalaciones-asistidas view-assisted-installs-metrics-in-the-overview-dashboard=ver-m%C3%A9tricas-de-instalaciones-asistidas-en-el-panel-de-control-general h_01HCBC922KRHB043FK1CQRKXDA=ver-m%C3%A9tricas-de-instalaciones-asistidas-en-el-panel-de-control-general why-are-assists-important=por-qu%C3%A9-son-importantes-las-asistencias h_01HCBC922KDAG8T27KK2JGRE7C=por-qu%C3%A9-son-importantes-las-asistencias assisted-installs-reporting=reportes-de-instalaciones-asistidas h_01HCBC922KJV54QW6G85SN2JM7=reportes-de-instalaciones-asistidas h_01KSFPXWNAX8FZ6H2ZKN1Z2TJQ=advertencia h_01HCBC922K5HKF94JCY7C88R88=advertencia-1 total-candidates-field=campo-de-candidatos-totales h_01K453B1K1X7QVJHPQ505P745N=consideraciones-para-agencias" />
