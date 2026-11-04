---
title: Cambiar la configuración de moneda de la aplicación
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-12-24T08:22:42Z'
  edited_at: '2026-08-12T12:04:57Z'
  id: 42223406543249
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/42223406543249
---
> **Resumen:** Gestiona fácilmente la configuración de moneda de tu aplicación para alinear tus reportes de ingresos con las necesidades de tu negocio. En este artículo se aclara cómo afectan los cambios de moneda a tus datos históricos y futuros, quién puede hacer estos cambios y cuáles son los pasos de aprobación necesarios.

<div id="about-changing-app-currency-settings" />

## **Información sobre cómo cambiar la configuración de moneda de la aplicación**

De forma predeterminada, tus dashboards de AppsFlyer muestran los datos con la moneda local seleccionada. Puedes cambiar a la vista en USD en cualquier momento sin modificar la configuración de moneda real de tu aplicación.

Si estás viendo datos de varias aplicaciones con distintas monedas locales, el dashboard se establece automáticamente en USD de forma predeterminada.

<div id="who-can-change-the-app-currency" />

## **¿Quién puede cambiar la moneda de la aplicación?**

Los cambios de moneda dependen de los datos existentes de tu aplicación:

* **Aplicaciones sin ingresos ni costos:** Puedes cambiar la moneda directamente.
* **Aplicaciones con ingresos o costos:** Solo un **administrador de AppsFlyer** puede realizar el cambio.  
  Para solicitar un cambio de moneda:

1. Ponte en contacto con tu representante de AppsFlyer o envía un ticket de soporte.
2. Proporciona los datos de tu aplicación.
3. Adjunta una aprobación por escrito en la que se reconozca el impacto en los reportes.

<div id="how-currency-changes-impact-your-data" />

## **Cómo afectan los cambios de moneda a tus datos**

Cambiar la moneda de tu aplicación afecta a la visualización y a la precisión de los datos de ingresos:

<div id="future-data" />

<Accordion title="Datos futuros">

Una vez que cambie la moneda, todos los eventos futuros con el parámetro af\_revenue usarán la nueva moneda. Los reportes posteriores al cambio lo reflejarán, pero los reportes que abarquen la fecha del cambio pueden mostrar una mezcla de monedas.

</Accordion>

<div id="historical-data-accuracy" />

<Accordion title="Precisión de los datos históricos">

Los datos históricos se conservan, pero dejan de ser precisos:

* Los eventos de ingresos anteriores al cambio permanecen en la moneda anterior.
* Los eventos de ingresos posteriores al cambio usan la nueva moneda.
* Esta mezcla provoca imprecisiones en métricas como LTV y ROAS.

El impacto varía:

* **Historial amplio de ingresos:** Discrepancias significativas.
* **Historial mínimo de ingresos:** Menor impacto.

</Accordion>

<div id="example" />

### **Ejemplo**

<div id="reporting-impacts" />

<Accordion title="Impactos en los reportes">

Si cambias la moneda de tu aplicación el **1 de octubre**, así es como se ven afectados los métodos de reporte de ingresos:

| **Método de reporte** | **Antes del 1 de oct** | **Abarca el 1 de oct** | **Después del 1 de oct** |
| --- | --- | --- | --- |
| **LTV & cohorte (D0–180)** | Monedas mixtas (inexactas) | Monedas mixtas (inexactas) | Preciso |
| **ACTIVIDAD** | Muestra la moneda anterior | Monedas mixtas (inexactas) | Preciso |
| **Métricas orgánicas del día 7** | Preciso hasta 7 días antes del cambio | Monedas mixtas (inexactas) | Preciso |

</Accordion>

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> * Los cambios de moneda son **permanentes**.
> * Los datos históricos **no se pueden convertir ni restaurar**.
> * Confirma todas las implicaciones con tu gerente de cuenta de AppsFlyer antes de hacer cambios.

<div data-zendesk-anchors="about-changing-app-currency-settings=informaci%C3%B3n-sobre-c%C3%B3mo-cambiar-la-configuraci%C3%B3n-de-moneda-de-la-aplicaci%C3%B3n h_01KD7Q6FR8VKG3HGXDJC6YB5J3=informaci%C3%B3n-sobre-c%C3%B3mo-cambiar-la-configuraci%C3%B3n-de-moneda-de-la-aplicaci%C3%B3n who-can-change-the-app-currency=qui%C3%A9n-puede-cambiar-la-moneda-de-la-aplicaci%C3%B3n h_01KD7Q6FR96NRV4SBRQ8YEW12X=qui%C3%A9n-puede-cambiar-la-moneda-de-la-aplicaci%C3%B3n how-currency-changes-impact-your-data=c%C3%B3mo-afectan-los-cambios-de-moneda-a-tus-datos h_01KD7Q6FRB9TCV2N0KT2N4599A=c%C3%B3mo-afectan-los-cambios-de-moneda-a-tus-datos h_01KD7QJQ4FF197R69RAD5Q6KKT=future-data h_01KD7QM57R8TJY5T10R36EB1P9=historical-data-accuracy example=ejemplo h_01KD7QW856FFEQ779153KNCYW6=ejemplo h_01KD7QG6CB2KFGXE6D4M46B65H=reporting-impacts h_01KD7QS7EYS21KX0Q9WB7ETV99=dos-puntos-" />
