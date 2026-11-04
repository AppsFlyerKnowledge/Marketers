---
title: 'Boletín: Apple Ads añade timestamps a todas las reclamaciones de atribución'
metadata:
  keywords:
    - apple ads
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-26T09:02:50Z'
  edited_at: '2026-10-20T03:54:02Z'
  id: 50216486847249
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/50216486847249
---
| Sección. | Detalles |
| --- | --- |
| ¿Qué hay de nuevo? | A partir del 1 de septiembre de 2026:<ul><li>La API AdServices de Apple añade un timestamp de engagement a todas las reclamaciones de atribución de iOS, incluidas las que antes no lo tenían. AppsFlyer usa este timestamp para aplicar a estas reclamaciones tu ventana de lookback configurada y las reglas de atribución de último toque.</li><li>En los grupos de anuncios con targeting por edad o sexo, Apple devolverá un payload de atribución false, y estos engagements no podrán atribuirse a Apple Ads en AppsFlyer.</li></ul> |
| Fecha de entrada en vigor | 1 de septiembre de 2026 |
| Lo que debes saber | <ul><li>En la mayoría de las campañas de Apple Ads, la precisión de la atribución mejora porque ahora los engagements se evalúan según la ventana de lookback definida por el anunciante, en lugar de las ventanas predeterminadas anteriores, incluidos los engagements de usuarios que no dieron su consentimiento y que antes se reclamaban sin timestamps.</li><li>Por separado, los grupos de anuncios con targeting por edad o sexo devolverán un payload de atribución false. Apple Ads no reclama los engagements de esos grupos de anuncios y, por tanto, no pueden atribuirse a ellos.</li></ul> |
| Lo que debes hacer | No se requiere ninguna acción. Tu integración de Apple Ads refleja este cambio automáticamente. Si ejecutas grupos de anuncios segmentados por edad o sexo, revisa los reportes de Apple Ads después del 1 de septiembre para entender cualquier cambio en las conversiones atribuidas. |

<div id="see-also" />

#### Consulte también

* <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup">Configuración de la integración de Apple Ads</Anchor>

<div data-zendesk-anchors="h_01M0YZSHS593T92XC58PR1FXYY=consulte-tambi%C3%A9n" />
