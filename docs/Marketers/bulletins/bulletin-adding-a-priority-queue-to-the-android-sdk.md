---
title: 'Boletín: incorporación de una cola de prioridad al SDK de Android'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-19T13:46:02Z'
  edited_at: '2026-10-20T03:56:35Z'
  id: 6971914107025
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/6971914107025
---
| **¿Qué hay de nuevo?** | En la versión 6.7.0, introdujimos algunos cambios en la forma en que el SDK gestiona las distintas solicitudes a los servidores de AppsFlyer.<br /><br />Hemos detectado que hay apps que intentan enviar eventos in-app antes de haber iniciado el SDK. Con este cambio, nos aseguramos de que todo se ejecute en el orden correcto. |
| --- | --- |
| **Qué ha cambiado** | **Antes del cambio**: en versiones anteriores del SDK, la aplicación podía enviar eventos in-app a AppsFlyer antes de llamar al método `start` del SDK (es decir, antes de que la conversión se enviara al servidor).<br /><br />**Después del cambio**: a partir de esta versión, la solicitud de conversión tiene prioridad y todos los eventos in-app que se producen antes de llamar a `start` se almacenan y esperan a que se envíe la solicitud de conversión. |