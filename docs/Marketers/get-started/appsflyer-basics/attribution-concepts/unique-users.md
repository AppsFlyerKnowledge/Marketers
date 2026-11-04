---
title: Usuarios únicos
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
  created_at: '2024-08-11T09:52:33Z'
  edited_at: '2026-08-12T11:57:27Z'
  id: 27435981457553
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/27435981457553
---
> **En resumen:** Descubre cómo se cuentan los usuarios únicos y cómo se utilizan en las métricas de los paneles de control y reportes de AppsFlyer.

<div id="about-unique-users" />

## Acerca de los usuarios únicos

Un usuario único es un término que se refiere a un dispositivo atribuido cuya presencia se cuenta solo una vez, independientemente de cuántas acciones realice un usuario en el dispositivo.

Es un cálculo que se utiliza en una amplia variedad de métricas de marketing, entre las que se incluyen:

* Instalaciones: el número de usuarios únicos que descargaron e instalaron la aplicación.
* Tasa de retención: porcentaje diario de usuarios únicos con una sesión.
* Usuarios únicos del evento: número de usuarios únicos (atribuciones) que realizan el evento.
* Usuarios activos diarios (DAU): número de usuarios únicos (contados solo una vez) que abren la aplicación al menos una vez durante el día.
* Y muchos más.

El cálculo de usuarios únicos se basa en el ID del dispositivo (como el IDFA o GAID). Si no hay ningún ID de dispositivo disponible (como para iOS SKAN), se utiliza el ID de AppsFlyer en su lugar. Esto garantiza que un usuario se cuente una sola vez, ya que el ID del dispositivo o el ID de AppsFlyer es el mismo para todas las acciones, sin importar cuántas sesiones o acciones realice.

<div id="use-cases" />

## Casos de uso

Aunque el cálculo de usuarios únicos suele ser sencillo, a veces surgen preguntas en torno a determinados comportamientos o acciones de los usuarios. Los siguientes casos de uso explican cómo se cuentan los usuarios únicos en algunas de esas instancias más complicadas.

<div id="install-and-reinstall" />

<Accordion title="Instalación y reinstalación">

![](https://files.readme.io/8b9f3c442f98c056069b4449c7e5115cbea828a64ace3a98e0090fb0d8d1d8d6-27455116159889.png)

La instalación y la reinstalación tienen el mismo ID de dispositivo/ID de AppsFlyer. Por lo tanto, solo se contabiliza 1 usuario único. Ambos eventos in-app se atribuyen al mismo usuario único que la primera instalación.

**Nota**:

* Si una reinstalación no incluye un ID de dispositivo o ID de AppsFlyer, no se puede conectar a la primera instalación y se considera como "orgánica sin atribuir". Los eventos posteriores a la reinstalación después de reinstalaciones orgánicas no atribuidas no se incluyen en el recuento de usuarios únicos.
* Puede haber otras razones para que algunos eventos no se atribuyan como orgánicos. En estos casos, los eventos tampoco se incluyen en el recuento de usuarios únicos.

</Accordion>

<div id="install-and-reattribution" />

<Accordion title="Instalación y reatribución:">

![](https://files.readme.io/40420c5ea201ba7cf13d03e5968d20c2fffaa31b74c47ae36cd917cccbaae353-27453973190289.png)

La instalación y la reatribución tienen el mismo ID de dispositivo/ID de AppsFlyer. Sin embargo, en este caso, AppsFlyer también tiene en cuenta el parámetro `is_retargeting=true`, por lo que el evento posterior a la reatribución se cuenta como un usuario único adicional. Por lo tanto, se contabilizan 2 usuarios únicos.

* En el panel de control general, la vista de UA muestra 1 usuario único, ya que las reatribuciones de retargeting no se muestran en la vista de UA. Lo mismo ocurre con los reportes de UA.
* En el panel de control general, la vista de retargeting muestra 1 usuario único, ya que las instalaciones de UA no se muestran en la vista de retargeting. Lo mismo ocurre con los reportes de retargeting.
* En el panel de control general, la vista unificada muestra 2 usuarios únicos, 1 conectado a la primera instalación y el segundo conectado a la reatribución. Lo mismo ocurre con los reportes unificados.

</Accordion>

<div id="install-and-reengagement" />

<Accordion title="Instalación y reengagement">

![](https://files.readme.io/bd4ee5eb9eacc561ac43c4b93d3fab30ddba6824a22e0433e12684fb6b3cf09b-49753330239121.png)

La instalación y el reengagement tienen el mismo ID de dispositivo/ID de AppsFlyer. Sin embargo, en este caso (al igual que para las reatribuciones), AppsFlyer también tiene en cuenta el parámetro `is_retargeting=true`, por lo que el evento posterior al reengagement se cuenta como un usuario único adicional. Por lo tanto, se contabilizan 2 usuarios únicos.

* En el panel de control general, la vista de UA muestra 1 usuario único, ya que los nuevos reengagements de retargeting no se muestran en la vista de UA. Lo mismo ocurre con los reportes de UA.
* En el panel de control general, la vista de retargeting muestra 1 usuario único, ya que las instalaciones de UA no se muestran en la vista de retargeting. Lo mismo ocurre con los reportes de retargeting.
* En el panel de control general, la vista unificada muestra 2 usuarios únicos, 1 conectado a la primera instalación y el segundo conectado al reengagement. Lo mismo ocurre con los reportes unificados.

</Accordion>

<div id="unattributed-inapp-events" />

<Accordion title="Eventos in-app no atribuidos">

![](https://files.readme.io/94bf078bcf4ba26a1dc4ca323a1b4a7543cfb4e3fc8b780d0d29713c4266aa95-27455116170001.png)

Cuando un evento in-app no está atribuido, es decir que ocurre después de una reinstalación pero por alguna razón no está vinculado a la primera instalación, no se incluye en absoluto en el recuento de usuarios únicos. Esto puede ocurrir cuando no hay un ID de dispositivo disponible para la reinstalación, pero también podría haber otras razones. <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#unattributed-organic-inapps">Saber más</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Detalles |
| --- | --- |
| Eventos de ingresos por publicidad<br /><br />(af\_ad revenue) | <ul><li>Se admite el recuento de usuarios únicos para eventos de ingresos por publicidad para:<ul><li>Métricas diarias de la cohorte</li><li>Métricas de actividad</li><li>Métricas de SKAN</li></ul></li><li>El recuento de usuarios únicos no se admite para eventos de ingresos por publicidad de:<ul><li>Métricas acumulativas de cohorte</li><li>Métricas LTV a través del método de atribución clásico. **Nota**: Esto significa que al observar un panel de control con la vista SSOT, la métrica de usuario única para eventos de ingresos por publicidad está disponible para los datos de SKAN, pero no para los datos de atribución clásica.</li></ul></li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=acerca-de-los-usuarios-%C3%BAnicos 01H7Z1003GTTMRY072BXWDFNP0=acerca-de-los-usuarios-%C3%BAnicos use-cases=casos-de-uso h_01J52T4MT63JVJEQ050E2BXMVQ=casos-de-uso h_01J52T9B4ZZH1TBW98YM5MY675=install-and-reinstall h_01J52T9B4ZYWQAGS3QHG99G3AS=install-and-reattribution h_01J531V2AKW8QP33B6K8QFH72R=install-and-reengagement h_01J52WPCZEBFP4RR0Y4ZC5TABK=unattributed-inapp-events h_01J52ZHXKYDG77PE70QZV63KY3=traits-and-limitations" />
