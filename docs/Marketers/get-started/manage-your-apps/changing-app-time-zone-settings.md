---
title: Cambiar la configuración de zona horaria de la aplicación
metadata:
  keywords:
    - Time Zone
    - Existing Apps
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2026-08-12T12:05:00Z'
  id: 115000306786
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/115000306786
---
> **De un vistazo:** Establece o cambia una zona horaria específica de la aplicación para ver los datos de la aplicación más alineados con tu zona horaria o con la de tus partners publicitarios. Comprende el efecto de los cambios de zona horaria en los reportes de datos dentro de la plataforma AppsFlyer.

## ¿Por qué cambiar la zona horaria?

La zona horaria predeterminada para las nuevas aplicaciones es UTC (UTC +0). Si se cambia la zona horaria de la aplicación, esto afecta la forma en que aparecen los datos en la plataforma.

* **Situación:** Trabajas en una zona horaria que no es UTC. However, you want app data aligned to your time zone or to the time zone you selected with other partners like Facebook and Google.
* **Objetivo:** Simplificar las comparaciones de datos entre AppsFlyer y otras redes.
* **Solución:** Alinea la zona horaria en la plataforma de AppsFlyer con los otros proveedores de servicios que usas. De forma predeterminada, se admite un horario de verano preciso (no configurable).

**Agencias y ad networks**:

* Agencias: visualizan los datos usando la zona horaria establecida por el propietario de la aplicación. Las agencias no pueden establecer la zona horaria.
* Redes de publicidad: visualizan los datos utilizando UTC en todo momento, independientemente de la zona horaria establecida por el anunciante.

## Cambiar la zona horaria

The account admin can make time-zone changes. Los cambios se pueden realizar una vez cada 48 horas. La configuración para cambiar la zona horaria no está disponible durante las 48 horas posteriores a un cambio anterior.

**Para cambiar la zona horaria de la aplicación:**

1. In AppsFlyer, go to **Configuration** > **App settings**.
2. In **Localization** > **Time Zone**, select **UTC**.
3. Haz clic en **Guardar configuración** y luego espera 48 horas.
4. Go to **Configuration** > **App settings**.
5. En **Localización** > **Zona horaria** > selecciona una zona horaria (por ciudad o país).
6. Haz clic en **Guardar configuración**.  
   El cambio entra en efecto al comienzo del día siguiente a las 00:00 UTC.

> 📄 **Ejemplo**
>
> * October 24 at 22:00, the time zone is changed.
> * El 25 de octubre a las 00:00 UTC el cambio entra en vigor.

Después de cambiar la zona horaria:

* La zona horaria utilizada en la presentación de datos depende del período y el método de reporte, como se detalla en las tablas siguientes.
* Los reportes agregados tendrán algunas anomalías el día y el día siguiente al cambio de zona horaria.
  * Cost data is duplicated on the day of the change.

#### Datos agregados

<table><thead><tr><th rowspan="2">Método de reporte </th><th colspan="3">Intervalo de fechas del reporte</th></tr><tr><th>Comienza y termina <span>antes</span> del cambio </th><th>Comienza y termina <span>después</span> del cambio </th><th>Comienza antes y termina después del cambio</th></tr></thead><tbody><tr><td>[Beta] My Dashboards</td><td><p>No está soportado. Los datos solo están disponibles en UTC cuando se cambia la zona horaria del dashboard.</p></td><td>Zona horaria actual</td><td>Los datos solo se muestran para las fechas posteriores al cambio.</td></tr><tr><td>Panel de vista general</td><td>Zona horaria anterior</td><td>Zona horaria actual</td><td><p>Divide:</p><ul><li>Antes del cambio: UTC</li><li>Después del cambio: zona horaria actual</li></ul></td></tr><tr><td>Paneles de control de eventos y personalizados</td><td>UTC</td><td>Zona horaria actual</td><td><p>Divide:</p><ul><li>Antes del cambio: UTC</li><li>Después del cambio: zona horaria actual</li></ul></td></tr><tr><td>Panel de control de actividades</td><td>Zona horaria anterior</td><td>Zona horaria actual</td><td>UTC</td></tr><tr><td>Cohorte, Retención, Pivote</td><td>UTC</td><td>Zona horaria actual (1)</td><td>UTC</td></tr><tr><td>API maestra</td><td colspan="3"><ul><li>Predeterminado: UTC</li><li>Option: <a href="./pull-api-aggregate-data#aggregate-report-uri-and-parameters" target="_blank">Select the time zone when you pull data</a> </li></ul></td></tr><tr><td colspan="4">Notas:<br/>(1) Todas las aplicaciones deben usar la misma zona horaria específica de la aplicación durante un período de reporte determinado. De lo contrario, la zona horaria vuelve a UTC.</td></tr></tbody></table>

#### Reportes de raw data

<table><thead><tr><th rowspan="2">Método de reporte </th><th colspan="3">Intervalo de fechas del reporte</th></tr><tr><th>Comienza y termina <span>antes</span> del cambio </th><th>Comienza y termina <span>después</span> del cambio </th><th>Comienza antes y termina después del cambio</th></tr></thead><tbody><tr><td>Exportar raw data de la página</td><td>Zona horaria actual</td><td>Zona horaria actual</td><td>Zona horaria actual</td></tr><tr><td>API Push</td><td colspan="3">Separa los campos para UTC y la zona horaria específica de la aplicación calculada utilizando la zona horaria seleccionada en el momento del evento.</td></tr><tr><td>API pull</td><td colspan="3"><ul><li>Predeterminado: UTC</li><li>Option: <a href="./pull-api-aggregate-data#aggregate-report-uri-and-parameters" target="_blank">Select the time zone when you pull the data</a> </li></ul></td></tr><tr><td>Casillero de datos</td><td colspan="3">Not impacted - date fields are in UTC</td></tr></tbody></table>

<div data-zendesk-anchors="why-change-the-time-zone=por-qu%C3%A9-cambiar-la-zona-horaria h_01HJR69P6Z44SZA5A684H82PNV=por-qu%C3%A9-cambiar-la-zona-horaria changing-the-time-zone=cambiar-la-zona-horaria h_01HJR69P6ZWJQ47FQY2HATAAE3=cambiar-la-zona-horaria h_01HJR69P6Z6B0Q6E6996WXVZ0N=ejemplo aggregate-data=datos-agregados h_01HJR69P6ZY8JJBCBSDZKN75N6=datos-agregados raw-data-reports=reportes-de-raw-data h_01HJR69P6ZDXXK8ZTKK3E774VJ=reportes-de-raw-data" />
