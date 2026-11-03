---
title: 'Boletín: La privacidad del tracking de enlaces (LTP) llegará con iOS17'
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2023-09-21T08:37:39Z'
  edited_at: '2026-10-20T03:56:03Z'
  id: 18730398273553
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/18730398273553
---
| **¿Qué hay de nuevo?** | iOS17 detectará y eliminará los parámetros identificados como parámetros de tracking de los enlaces que los usuarios compartan en las aplicaciones integradas: Mail, Mensajes y el modo de navegación privada de Safari.<br /><br />Hicimos pruebas internas para ver cómo afecta LTP a OneLink. Nuestros hallazgos indican que no se eliminó ninguno de los parámetros de AppsFlyer. Estos son los resultados de nuestras pruebas:<br /><br />**<span id="h_01HAVEDAEFTDVGS1SXBD7NEJFE"></span>Los siguientes parámetros se eliminan por LTP**<ul><li>`gclid` - ID de Google Ads / Analytics</li></ul><ul><li>`fbclid` - ID de publicidad de Facebook</li></ul>**<span id="h_01HAVEDAEFN7XEPK3TNCSZRAMW"></span>LTP no modifica los siguientes parámetros**<ul><li>Parámetros UTM</li></ul>**<span id="h_01HAVEDAEFMGD1SFYRJNXE9JBE"></span>Parámetros de atribución de AppsFlyer:**<ul><li>`pid`</li></ul><ul><li>`c`</li></ul><ul><li>`Is_regtargeting`</li></ul><ul><li>`af_channel`</li></ul><ul><li>`af_adset`</li></ul><ul><li>`af_ad`</li></ul><ul><li>`af_sub1-10`</li></ul><ul><li>`af_inactivity_window`</li></ul><ul><li>`af_click_lookback`</li></ul><ul><li>`af_cost_value`</li></ul><ul><li>`af_cost_currency`</li></ul>**<span id="h_01HAVEDAEFEFZ1ZCPAZ05C3AWW"></span>Parámetros de redireccionamiento de AppsFlyer**<ul><li>`af_dp`</li></ul><ul><li>`deep_link_value`</li></ul><ul><li>`af_deep_link_sub1-10`</li></ul><ul><li>`af_web_dp`</li></ul><ul><li>`af_ios_url`</li></ul><ul><li>`af_android_url`</li></ul><ul><li>`af_xp`</li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | La fecha de lanzamiento público de iOS17 (18 de septiembre de 2023) |
| **Esto afecta a** | **<span id="h_01HAVEDAEFE7K3FT7RNA0FANHV"></span>Redireccionamiento y Deep Linking**<br /><br />Es poco probable que el redireccionamiento y el Deep Linking se vean afectados por este cambio. El único caso en el que el Deep Linking puede verse afectado es cuando la Atribución depende de GCLID o FBCLID.<br /><br />**<span id="h_01HAVEDAEFAB2AGW54XW52YAXJ"></span>Web-2-app**<br /><br />Como LTP solo se aplica al modo de navegación privada de Safari, esperamos un impacto mínimo en la Atribución de los flujos Web-to-app. Sin embargo, cuando el usuario está en el modo de navegación privada de Safari, los parámetros GCLID y FBCLID, que LTP elimina, no se asignarán mediante los Smart Scripts.<br /><br />**<span id="h_01HAVEDAEFTC8QRKTZCQZSC8G6"></span>Correo electrónico, SMS y notificaciones**<br /><br />Las aplicaciones integradas de Apple, como Mail y Messages, bloquearán los parámetros de tracking pertinentes mencionados anteriormente. Por lo tanto, el uso de enlaces en este tipo de campañas puede provocar la pérdida de datos a nivel de usuario. Además, algunos identificadores de estadísticas de los proveedores de servicios de correo electrónico (ESP) podrían bloquearse como parte de este cambio, lo que podría afectar a las estadísticas de las campañas de correo electrónico. Te recomendamos que contactes con tu ESP para entender plenamente el impacto. |