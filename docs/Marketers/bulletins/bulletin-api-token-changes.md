---
title: 'Boletín: Cambios en el token de API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2026-10-20T03:56:16Z'
  id: 12399683708305
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/12399683708305
---
| **¿Qué hay de nuevo?** | Para proporcionar una experiencia más segura y confiable para el uso de API, el token de API V1, que se incluyó en las URL de la API, quedó en desuso a favor del token de API V2, que es un token basado en JWT que se transmite en el encabezado para la autorización del portador.<br /><br />El token API V1 y las API que lo utilizan ya no están disponibles desde el 18 de septiembre de 2023. |
| --- | --- |
| **Fecha de entrada en vigor** | 18 de septiembre de 2023 |
| **Prerrequisitos** | Solo un administrador puede <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#recuperar-tokens">recuperar el token de API V2</Anchor> desde el dashboard de AppsFlyer. |
| **¿Quién debe actualizar el token de API?** | Tanto los anunciantes como las agencias que todavía están usando el token de API V1 necesitan actualizar sus tokens. |
| **Cómo encontrar tokens de API V1** | Usa el <Anchor target="_blank" href="/marketers/es/docs/audit-log">registro de auditoría</Anchor> para filtrar cualquier token de API V1 que aún esté en uso. A continuación, puedes descargar los datos a un archivo CSV:<ol><li>Ve al [dashboard del registro de auditoría](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Escribe "API Token V1" en la barra de búsqueda.</li><li>En el filtro **Servicio** , selecciona solo **llamadas de API** y filtra los resultados.</li><li>Haz clic en el icono Descargar en la parte superior derecha de la página.<br />Tu archivo CSV se descarga e incluye tu ID de aplicación, el servicio utilizado y la URL de llamada a la API.</li></ol> |
| **Acción requerida** | **Actualiza las siguientes API para el token de API V2:**<ol><li>Ve a la <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">página del token de API</Anchor>.</li><li>En Token de API V2.0, haz clic en el icono **Copiar al portapapeles**.</li><li>Para cada una de las siguientes API:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">API maestra V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API agregada V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull API de raw data V2</Anchor></li></ul><ol><li>Reemplaza la URL de la API V1 por la URL en la documentación anterior.</li><li>Pega el token que copiaste en el encabezado de autenticación del portador.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Para la **API OpenDSR**, pega el token en el encabezado Bearer de la solicitud:<br />`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **Acerca de los tokens de API** | **Aprender más sobre los tokens de API:**<ul><li><Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Administración de tokens de API</Anchor><ul><li><Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API Master</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Pull API agregada</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">Datos sin procesar</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests#formato-de-solicitudes-gdpr">OpenDSR API</Anchor></li></ul></li></ul> |