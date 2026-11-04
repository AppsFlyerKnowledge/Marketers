---
title: >-
  Boletín: obtén la atribución de Meta Ads en los Reportes de raw data con la
  Referencia de instalación de Meta
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-02-12T10:47:33Z'
  edited_at: '2026-10-20T03:55:41Z'
  id: 22461635687185
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/22461635687185
---
| **¿Qué hay de nuevo?** | La Referencia de instalación de Meta ayuda con la medición de la Atribución de tus campañas de anuncios de Android en Facebook, Instagram y Audience Network, cuando el objetivo es la instalación de la app. Esto se suma a Google Play Install Referrer. |
| --- | --- |
| **Fecha de entrada en vigor** | Feb 28, 2024 |
| **Prerrequisitos** | Asegúrate de lo siguiente:<ul><li>Tienes la versión **V6.12.6** o posterior del SDK de AppsFlyer para garantizar que los datos del referente se transmitan correctamente</li><li>Has introducido la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#encrypted-data-from-the-referrer">clave de descifrado de la Referencia de instalación</Anchor> en la página de integración</li><li>Las versiones <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites">descritas aquí</Anchor> están instaladas en los dispositivos de tus usuarios</li></ul> |
| **Acciones requeridas** | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support">Configura el soporte de la Referencia de instalación de Meta</Anchor> |
| **¿Qué debo saber?** | Los datos del referente tienen prioridad sobre los datos proporcionados por la integración de anuncios de Meta y están disponibles en los Reportes de raw data. Esta solución se aplica tanto a la atribución por clics como a la atribución por impresiones. |
| **¿Cuál es el impacto?** | <ul><li>Es posible que veas un aumento de las instalaciones atribuidas a Meta en los reportes de raw data</li><li>Ahora se incluyen dos nuevos campos de tipo de coincidencia en los reportes de raw data: `fb_referrer` y `ig_referrer`:<ul><li>`fb_referrer` para la atribución desde la aplicación de Facebook</li><li>`ig_referrer` para la atribución desde la aplicación de Instagram</li><li>`fb_referrer` o `ig_referrer` para la atribución desde Audience Network.</li></ul></li></ul> |

<div id="see-also" />

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#userlevel-data">Meta install referrer</Anchor>

<div data-zendesk-anchors="h_01H9FHRVKE88CXGH8G7E26ZXT2=consulte-tambi%C3%A9n" />
