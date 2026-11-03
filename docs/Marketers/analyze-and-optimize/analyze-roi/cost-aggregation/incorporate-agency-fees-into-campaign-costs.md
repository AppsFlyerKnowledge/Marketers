---
title: Incorpora las tarifas de agencia a los costos de campaña
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2021-06-03T13:53:23Z'
  edited_at: '2026-08-12T11:48:07Z'
  id: 4402103019665
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/4402103019665
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen:** Las reglas de tarifas de agencia forman parte de la función premium ROI360 de AppsFlyer, que permite a los anunciantes añadir los porcentajes de tarifas que las agencias cobran por el tráfico para poder ver el costo total de la campaña.

## Visión general

El anunciante (con privilegios de administrador de la cuenta de AppsFlyer) define las reglas de tarifas de agencia en el creador de reglas mediante condiciones personalizadas que añaden porcentajes de tarifa al costo de las campañas de agencia para aplicaciones y/o fuentes de medios específicas.

ROI360 utiliza la regla de tarifa de agencia para calcular el costo total del anuncio con la tarifa, en función de la API de la ad network y del costo del enlace de atribución. El cálculo se aplica en todos los niveles de granularidad (campaña, conjunto de anuncios, etc.). Los resultados se muestran en tus dashboards, reportes y Cost ETL; no en los dashboards ni en los reportes de la agencia o de la ad network. **Nota**: Los reportes de Cost ETL tienen campos adicionales para las tarifas de agencia<Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#file-fields">fields for agency fees</Anchor>.

Las reglas de agencia ayudan a los anunciantes a:

* Comprender el costo real de sus campañas publicitarias
* Ahorrar tiempo y esfuerzo manual al reportar datos de costo
* Gestionar el rendimiento de la agencia
* Analizar con precisión los datos históricos de costo

## Procedimientos

Consulta las secciones siguientes para ver las instrucciones sobre cómo ver, añadir, editar y eliminar reglas. Todos los procedimientos requieren privilegios de administrador de AppsFlyer.

<div id="view-rule-list" />

<Accordion title="Ver la lista de reglas">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para ver todas las reglas de tarifas de agencia creadas en tu cuenta**:

1. En AppsFlyer, en el menú lateral, selecciona **Settings** > **Cost Control.**  
   La pantalla Cost Control muestra la lista de reglas de agencia. Las reglas se clasifican en los siguientes estados posibles:
   * **Activo:** La fecha de inicio de la regla es hoy o anterior, y la regla ha calculado datos de tarifas al menos una vez.
   * **Inactivo:** La fecha de finalización de la regla está en el pasado (es decir, antes de hoy).
   * **Programado:** Hay datos pendientes de procesarse. Después de crear una regla o editar la fecha o el precio, la regla queda programada hasta que se procesa y luego pasa a Activo o Inactivo.
   * **Fallido:** La regla no puede calcularse por motivos técnicos.
2. Filtra las reglas de la lista con las opciones de filtro: Partner, App y fuente de medios.

</Accordion>

<div id="add-rule" />

<Accordion title="Agregar regla">

La interfaz de usuario del creador de reglas está diseñada para la creación de reglas interactivas. **Consejo!** Familiarízate y experimenta con el creador de reglas antes de revisar este artículo en detalle.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para añadir una regla nueva**:

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Control de costos.**
2. Haz clic en + **Añadir regla de tarifas de agencia**.  
   Se muestra la pantalla de la regla de tarifas de agencia.
3. Selecciona un partner (agencia).
4. Elige una o varias aplicaciones o selecciona **Todas las aplicaciones**. Si seleccionas **Todas las aplicaciones**, la regla se aplica a todas tus aplicaciones, incluidas las aplicaciones que se añadan a tu cuenta en el futuro.
5. Selecciona una o varias fuentes de medios o marca Todas las fuentes de medios. Si marcas Todas las fuentes de medios, la regla se aplica a todas las fuentes de medios, incluidas las que se añadan en el futuro.
   * Si la agencia con la que trabajas no es transparente, la opción **Todas las fuentes de medios** se selecciona de forma predeterminada y no puedes seleccionar una fuente de medios específica.
   * Si la aplicación que has seleccionado no es transparente, el menú desplegable de la fuente de medios permanece deshabilitado, a menos que la aplicación seleccionada en el menú desplegable contenga anuncios de Meta o anuncios de X, ya que estos siempre son transparentes.
6. Introduce una fecha de inicio.
7. [Opcional] Introduce una fecha de finalización.
8. Introduce el porcentaje de la tarifa de agencia. Puede ser un número entre 100 y -100 (para reflejar descuentos o reembolsos de la agencia).
9. Haz clic en **Crear regla**.

> 📘 **Nota**
>
> Los siguientes errores pueden impedir que se cree la regla:
>
> * Un campo obligatorio no está rellenado. Para resolverlo, asegúrate de que todos los campos obligatorios estén rellenados.
> * La lógica de la regla entra en conflicto con una regla existente. Para resolverlo, cambia la aplicación o la fuente de medios.

</Accordion>

<div id="edit-duplicate-or-delete-a-rule" />

<Accordion title="Editar, duplicar o eliminar una regla">

**Consideraciones:**

Cuando editas o eliminas una regla, se sobrescriben los datos calculados previamente (hasta 90 días atrás):

* En una regla editada, el costo total refleja el porcentaje actualizado de la tarifa de agencia.
* En una regla eliminada, la tarifa de agencia se elimina del costo total.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para editar, duplicar o eliminar una regla**:

1. En la [lista de reglas](/docs/incorporate-agency-fees-into-campaign-costs#view-rule-list), coloca el cursor sobre la regla que quieres editar, duplicar o eliminar.
2. Haz clic en **Menu** ⋮ en el lado derecho.
3. Selecciona la acción que quieres realizar.

> 📘 **Nota**
>
> La agencia y la fecha de inicio de una regla no se pueden editar después de crear la regla. Si necesitas cambiarlas, elimina la configuración anterior y crea una regla nueva.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Agencias y ad networks | Las Agencias y las ad networks no pueden ver las reglas ni los datos de costo total de anuncios que son resultado de las reglas de tarifas de agencia en sus dashboards y reportes. |
| Actualización de datos | <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">A lo largo del día</Anchor>. Los cálculos iniciales pueden tardar hasta 5 horas en mostrarse. |
| Datos históricos | Las reglas se pueden crear y afectar a los datos hasta 90 días en el pasado. |
| Frecuencia de procesamiento de las reglas | Las nuevas reglas de tarifas de agencia se procesan cada **4 horas**. Esto significa que una regla puede tardar hasta **4 horas** en aplicarse. |

Especificaciones y limitaciones

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HFV23CD24HQVC82NNNBDKFRH=visi%C3%B3n-general procedures=procedimientos h_01HFV23CD38RXRT59DNGZAADV1=procedimientos h_01HFV23CD3F5ZPT4D3X8PHJS4T=view-rule-list h_01HFV23CD3MZSZDKTH8CZAY954=add-rule h_01HFV23CD3W6J9QSPHBV9NE19S=nota h_01HFV23CD3SHHR1HRK6DX4QCET=edit-duplicate-or-delete-a-rule h_01HFV23CD3QH6X0WJEAFTMXNMD=nota-1 h_01HFV23CD3E486GBA5XBSN41RA=traits-and-limitations" />
