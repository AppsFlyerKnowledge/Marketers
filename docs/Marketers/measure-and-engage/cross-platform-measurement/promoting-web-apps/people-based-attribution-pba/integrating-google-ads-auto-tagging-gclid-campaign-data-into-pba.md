---
title: >-
  Integración de los datos de campaña del etiquetado automático (gclid) de
  Google Ads en PBA
metadata:
  keywords:
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-08-02T05:47:05Z'
  edited_at: '2026-08-12T12:11:11Z'
  id: 360011487937
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360011487937
---
> **At a glance:** Enriquece los datos de PBA con información de campañas de gclid del etiquetado automático al conectarte a Google Ads.

![](https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png)

## Integración de los datos de campaña de Google Ads en PBA

Conecta tu cuenta de Google Ads (1 o más) a tu paquete de marca. Los datos de campaña de Google Ads mejoran las capacidades analíticas del Dashboard y enriquecen aún más los Reportes de raw data.

* Si el **gclid** está presente en la URL de una visita web, PBA obtiene los siguientes datos de Google mediante GCLID. ¡Nota! La solución GCLID no cuenta con soporte oficial de Google Ads, que puede dejar obsoleto el parámetro en el futuro.
* La integración enriquece los siguientes campos. La disponibilidad de los campos depende del Dashboard de PBA y de los Reportes de raw data.
  * Nombre de la campaña e ID de campaña
  * Nombre del conjunto de anuncios e ID del conjunto de anuncios
  * Nombre del grupo de anuncios e ID del grupo de anuncios
* Los datos proporcionados por la integración tienen prioridad y sobrescriben los datos del nombre de la campaña extraídos de los campos UTM. La campaña y el ID de campaña están disponibles en los reportes de raw data.
* Si tienes varias cuentas de Google Ads, asegúrate de conectar las cuentas que ejecutan campañas que llevan tráfico a tu sitio web.

**Dashboard de atribución del sitio web con la jerarquía de campaña completada**

![PBAWebSite.png](https://files.readme.io/46004298b827d3f4eaa4adae9fb2a8676867e6b5dde44a7ff087fe1bda07f054-4403138621713.png)

Los datos de la jerarquía de campañas y anuncios están disponibles en los Dashboard y en raw data de la siguiente manera:

* **Paneles de control**
  * **Atribución del sitio web:** soporte para los niveles campaña > conjunto de anuncios > anuncio.
  * **Instalaciones asistidas en la web:** nivel de campaña
* **Raw data:**
  * **Web-to-App:** web\_googleads\_campaign\_id, web\_googleads\_campaign\_name

**Para conectarte a Google Ads:**

1. En AppsFlyer, en el menú lateral, selecciona **Configuración**> **Brand Bundles**
2. Ve a la pestaña **integración de Google Ads**.
3. Haz clic en **Conectar cuenta.** Se abre la página de inicio de sesión de Google Anuncios.
4. Inicia sesión en la cuenta de Google Anuncios. Completa el proceso para dar acceso a AppsFlyer.

**Gestionar conexiones de Google Anuncios**

En la página de integración de Google Anuncios, están disponibles las siguientes acciones:

* Eliminar conexión
* Activar/desactivar la conexión

### Mensajes de estado de PBA—Google Anuncios

| Estado | Significado | Observaciones/acción requerida |
| --- | --- | --- |
| Activo | La conexión está activa y extrayendo datos | N/D |
| Inactivo | La conexión se deshabilitó manualmente | Activa la conexión para volver a extraer datos |
| Nunca se sincronizó | La configuración está completa | La configuración está completa. AppsFlyer puede tardar hasta 24 horas en obtener datos de Google Anuncios por primera vez. Si este mensaje persiste durante más de 24 horas, comunícate con el soporte técnico de AppsFlyer. |
| No hay datos | La conexión fue exitosa | Google Ads no devolvió ningún dato a nuestra consulta. Asegúrate de conectar todas las cuentas relevantes de Google Anuncios a PBA. |
| No responde | No podemos contactar con los servidores de Google Anuncios | En este momento, no podemos conectarnos a los servidores de Google Anuncios. Si este estado persiste durante más de 24 horas, comunícate con el soporte técnico de AppsFlyer. |
| Credenciales inválidas | AppsFlyer no puede obtener los datos porque las credenciales no son válidas. | Asegúrate de que las credenciales correctas estén configuradas en la página de integración de Google Anuncios. Intenta conectarte de nuevo con las credenciales más recientes. Si el problema persiste, contacta con el soporte de AppsFlyer: support@AppsFlyer.com |
| Error general |  | Si este estado persiste durante más de 24 horas, comunícate con el soporte técnico de AppsFlyer |

<div data-zendesk-anchors="integrating-google-ads-campaign-data-in-pba=integraci%C3%B3n-de-los-datos-de-campa%C3%B1a-de-google-ads-en-pba h_01HKW2V24JE5V959999TJDR2RX=integraci%C3%B3n-de-los-datos-de-campa%C3%B1a-de-google-ads-en-pba pba%E2%80%94google-ads-status-messages=mensajes-de-estado-de-pbagoogle-anuncios h_01HKW2V24KM85CCC2F0CZHY359=mensajes-de-estado-de-pbagoogle-anuncios" />
