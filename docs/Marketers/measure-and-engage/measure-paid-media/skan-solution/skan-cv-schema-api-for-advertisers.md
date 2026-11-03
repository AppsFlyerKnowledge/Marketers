---
title: API de esquema de CV de SKAN para anunciantes
metadata:
  keywords:
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2026-08-12T12:21:39Z'
  id: 8610329713553
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/8610329713553
---
> **De un vistazo:** Consulta tu esquema actual del valor de conversión (CV) de SKAdNetwork (SKAN), tal como está configurado en AppsFlyer Conversion Studio.

## API del esquema de valor de conversión de SKAN

<div id="api-basics" />

<Accordion title="Conceptos básicos de la API">

| Visión general | Consulta tu esquema actual de valor de conversión (CV) de SKAdNetwork (SKAN) tal como está configurado en AppsFlyer Conversion Studio.<br /><br />**Nota**:<ul><li>El esquema histórico de CV de SKAN no está disponible.</li><li>También puedes ver tu esquema de SKAN descargando el archivo CSV de asignación disponible en Conversion Studio.</li></ul> |
| --- | --- |
| Ruta | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| Parámetros de ruta (obligatorios) | `<app_id>`: es el identificador de la app tal como aparece en el dashboard de AppsFlyer. Insértalo exactamente como aparece en el dashboard. Ejemplo: id123456789 |
| Método HTTP | `GET` |
| Tipo de contenido de la respuesta | `text/plain` |
| Autorización | Se requiere la cabecera HTTP `Authorization`, que contiene el token de API V2.0 (token Bearer).<br /><br />![AppsFlyerAdmin_us-en.png](https://files.readme.io/466e632ed4068c94ee10e1f72e3451e6133f7029554358d60b7433c267538bba-21590572168721.png)Un usuario administrador <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">obtiene el token V2 en el dashboard,</Anchor> from la barra superior, abre el menú de la cuenta (lista desplegable de la dirección de correo electrónico) > **Security Center** > **AppsFlyer API and S2S tokens**. |
| Limitación de velocidad | <ul><li>Las consultas devuelven hasta 50K filas</li><li>10 llamadas por minuto</li></ul> |
| Fecha del último cambio de configuración | <ul><li>En el modo de decodificación, la fecha aparece en el nombre del archivo.</li><li>En todos los demás modos, la fecha aparece en la columna last\_config\_change.</li></ul> |

### Ejemplo de solicitud (cURL)

```shell
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (cadena de más de 700 caracteres)>'
```

</Accordion>

<div id="report-name" />

<Accordion title="Nombre del informe">

La API devuelve un archivo CSV con el siguiente esquema de nomenclatura:

Para el modo de decodificación: `conversion_value_mapping_<fecha del último cambio de configuración del esquema>`

Para todos los demás modos: `conversion_schema_report_custom_encode`

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la red publicitaria | Si es un partner de análisis, solicita permiso al anunciante. |
| Acceso a la agencia | No disponible |
| Acceso del usuario a la cuenta | El token de autorización está disponible para un usuario administrador en el panel de control. |

</Accordion>

<div id="http-response-codes-and-troubleshooting" />

<Accordion title="Códigos de respuesta HTTP y resolución de problemas">

| HTTP | Respuesta | Nota |
| --- | --- | --- |
| 200 | Correcto | Datos válidos devueltos (CSV) |
| 400 | Solicitud incorrecta | Solicitud no válida |
| 401 | No autorizado | Falta el token de autorización o no es válido<br /><br />Asegúrate de usar el token correctamente |
| 401 | Demasiadas solicitudes | Se ha excedido el límite de frecuencia |
| 403 | No hay permiso | No tienes permisos para acceder a este reporte. Si eres un partner de análisis, pide al anunciante que te dé permiso. |
| 404 | No encontrado | <ul><li>Resuelve cualquier problema relacionado con la red o el cortafuegos.</li><li>Asegúrate de que las <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">direcciones IP de AppsFlyer estén en la lista de permitidas</Anchor></li></ul> |

</Accordion>

<div data-zendesk-anchors="skan-conversion-value-schema-api=api-del-esquema-de-valor-de-conversi%C3%B3n-de-skan h_01HKW1B4XQH2JCJ3T0M1D6W7EM=api-del-esquema-de-valor-de-conversi%C3%B3n-de-skan h_01HKW1B4XQCZPQBQFADGNTZDC3=api-basics request-example-curl=ejemplo-de-solicitud-curl h_01HKW1B4XQXQW0Z0G8ZF9EE8AZ=ejemplo-de-solicitud-curl h_01HKW1B4XQ6ZD45YPHKHDHAZX0=report-name h_01HKW1B4XQVFNM33WV73BA5QXG=traits-and-limitations h_01HKW1B4XQY0V30B4BYCRF9HP5=http-response-codes-and-troubleshooting" />
