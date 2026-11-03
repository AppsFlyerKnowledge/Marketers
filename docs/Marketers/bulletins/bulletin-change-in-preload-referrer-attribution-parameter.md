---
title: 'Boletín: Cambio en el parámetro de atribución de referencia de precarga'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2026-10-20T03:55:56Z'
  id: 20161765461009
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/20161765461009
---
| **¿Qué hay de nuevo?** | El parámetro de atribución de referencia de precarga de las nuevas instalaciones y los eventos y las sesiones in-app atribuidas a nuevas instalaciones registradas después de la fecha de entrada en vigor se notificarán de forma diferente.<br /><br />A continuación se muestran los cambios en el parámetro de atribución de referencia de precarga:<ul><li>**attributed\_touch\_type** será **download** (en lugar de preload o click\_to\_download)<ul><li>e**ngagement\_type** será **preload** (para el tipo de coincidencia preload\_rfr) o **click\_to\_download** (para el tipo de coincidencia af\_referrer)</li></ul></li></ul>Los eventos y las sesiones in-app atribuidas a instalaciones anteriores a la fecha de entrada en vigor mantendrán el comportamiento existente:<ul><li>**attributed\_touch\_type** será **preload** o **click\_to\_download**<ul><li>**engagement\_type** estará **vacío**</li></ul></li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | 17 de enero de 2024 |
| **Esto afecta a** | <ul><li>Anunciantes y agencias que utilizan <Anchor target="_blank" href="/marketers/es/docs/set-up-appsflyer-preload-referrer-attribution">la atribución de referrer de precarga de AppsFlyer</Anchor></li><li>Dónde está cambiando: reportes de raw data y dashboards</li></ul> |