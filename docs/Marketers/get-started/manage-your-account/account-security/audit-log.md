---
title: Registro de auditoría
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2026-08-12T12:04:17Z'
  id: 360007971697
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/360007971697
---
> **En resumen:** Identifica y protégete contra el acceso no autorizado a tu cuenta de AppsFlyer utilizando Audit log. Visualiza y descarga un resumen de la actividad relacionada con la seguridad en tu cuenta.

<div id="overview" />

## Visión general

El **registro de auditoría** proporciona una ubicación central para revisar diversas actividades en tu cuenta, como login, acceso a datos, llamadas a la API, modificaciones de configuración y permisos en Partners integrados, reglas de validación, audiencias y otros eventos significativos. Esto desempeña un papel clave para garantizar la transparencia, la seguridad y el cumplimiento de los estándares de cumplimiento. Para proteger la seguridad de tu cuenta de AppsFlyer, es recomendable revisar periódicamente **quién** accede a tu cuenta y **cómo** se accede a ella. Los datos de Audit log están disponibles durante los últimos 90 días.

**Para acceder al Audit log:**

1. En la barra superior, abre el menú de la cuenta (menú desplegable de la dirección de correo electrónico): **Centro de seguridad.**
2. En la sección **Audit log**, haz clic en **Ver audit log.**

<div id="using-the-audit-log" />

## Usando Audit log

En la siguiente tabla se proporciona una descripción de los datos proporcionados por el registro de auditoría y un resumen de sus capacidades.

[![audit_log.png](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)

|  | Elemento | Descripción |
| --- | --- | --- |
| ![A.png](https://files.readme.io/d515ad5eb908256574b52dee5d598a785020c3392b410b9fa4574eeb8c4ae594-6867187386897.png) | Cuadro de búsqueda y filtros | Filtra los datos mostrados para centrarte solo en lo que quieres ver:<ul><li>Utiliza el cuadro de búsqueda para filtrar los datos por un término específico (como un ID de aplicación relevante, una dirección de correo electrónico, etc.)</li><li>Utiliza el selector de fecha para seleccionar el período de tiempo para el cual se muestran los datos</li><li>Utiliza el filtro de servicios para filtrar los datos según los servicios específicos a los que accedas:<ul><li>Acceso al sistema</li><li>Permisos de partners integrados</li><li>Gestión de usuarios</li><li>Reglas de validación</li><li>Llamadas a la API</li></ul></li></ul>Ten en cuenta que el servicio de **llamadas a la API** no está seleccionado de forma predeterminada para optimizar la legibilidad del reporte. Asegúrate de seleccionar este servicio si deseas incluirlo en el reporte. |
| ![B.png](https://files.readme.io/ee0be2e394ad7bf76766a84c3bcad882a55dd0522e0aa41ed8ef11432c0df592-6867187537809.png) | Datos del Audit log | Cada entrada en el audit log incluye los siguientes datos:<ul><li>**Fecha y hora:** la fecha y hora en que se accedió al servicio (en UTC)</li><li>**Aplicación/cuenta accedida:**<ul><li>Para inicios de sesión de usuarios (acceso al sistema) y administración de usuarios, esta columna muestra **Cuenta** (que indica acceso a nivel de cuenta).</li><li>Para llamadas a la API, esta columna muestra el acceso a la **cuenta** o el **ID de la app** para la que se accedió a los datos.</li></ul></li><li>**Credenciales**<ul><li>Para acceso al sistema o gestión de usuarios, esta columna muestra la dirección de correo electrónico del usuario que accede al servicio.</li><li>Para llamadas a la API, esta columna muestra el token API de AppsFlyer utilizado (V2)</li></ul></li><li>**Servicio:** el servicio al que se accedió (Acceso al sistema, Gestión de usuarios o llamadas a la API)</li><li>**Acción:** la acción registrada (ejemplos: iniciar sesión, cerrar sesión, los datos a los que accede una API)</li><li>**Detalles:** Detalles adicionales sobre la acción registrada</li></ul> |
| ![C.png](https://files.readme.io/078ad9663eed2141f7047e0869fe02f4d1a0f8545176bce4d1c6027bfaa439b3-6867187658385.png) | ![audit_log_download_button.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | Haz clic en el botón de descarga para descargar el audit log como un archivo CSV.<ul><li>Todas las selecciones aplicadas al reporte tal como se muestran en la pantalla (usando el cuadro de búsqueda y filtros) también se aplican al archivo descargado.</li></ul> |

<div id="troubleshooting" />

## Resolución de problemas

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="¿Por qué el audit log de un anunciante muestra solicitudes de llamadas a la API del partner?">

Cuando un partner realiza una solicitud de la API en una aplicación propia de un anunciante, tanto el partner como el anunciante ven la solicitud en su audit log.

Cuando un anunciante realiza una solicitud de la API utilizando su propio token, solo se mostrará en el audit log del anunciante.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01H9Q3XYYBKYSRP3T0R2MP712C=visi%C3%B3n-general using-the-audit-log=usando-audit-log h_01H9Q3XYYBBCB6PXBZBF97QE11=usando-audit-log troubleshooting=resoluci%C3%B3n-de-problemas h_01H9Q3XYYB24R3EATM7R32V0G7=resoluci%C3%B3n-de-problemas h_01H9Q3XYYCHWJ1NQS389MR311X=why-does-an-advertiser-audit-log-show-partner-api-call-requests" />
