---
title: Discrepancias de atribución entre Amazon Ads y AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-08-29T00:26:55Z'
  id: 28461159218449
  locale: es
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/es/articles/28461159218449
---
> **At a glance:** Infórmate sobre las diferencias en los modelos de atribución entre Amazon Ads y AppsFlyer.

## Visión general

Como líderes en el ecosistema de adquisición de usuarios móviles, Amazon Ads y AppsFlyer utilizan modelos de atribución distintos. Esto puede causar discrepancias entre los paneles de Amazon Ads y AppsFlyer. Aunque trabajamos estrechamente con Amazon Ads para minimizar estas discrepancias, los anunciantes deben conocer las posibles causas.

## Diferencias en los Modelos de Atribución

La siguiente tabla describe las posibles razones de las discrepancias entre los paneles de Amazon Ads y AppsFlyer:

| Causa | Gestor de Anuncios de Amazon | fuentes de medios |
| --- | --- | --- |
| <span id="multichannel-source-attribution"></span>Atribución de Fuentes Multicanal | Amazon Ads se atribuye las instalaciones sin considerar otras fuentes de medios. | AppsFlyer utiliza atribución de último clic.  <br />Saber más sobre el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución de AppsFlyer</Anchor>. |
| <span id="different-timezones"></span>Diferentes Zonas Horarias | La zona horaria de Amazon Ads (mostrada junto al rango de fechas) no se puede modificar. Se configuró al crear la cuenta publicitaria. | La zona horaria predeterminada de la app de AppsFlyer es UTC+0. Para coincidir con la zona horaria de Amazon Ads, ajústala en la <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-time-zone">página de configuración de la app</Anchor>. |

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01J81NN4J4A1KWBXJQD9SM2AWH=visi%C3%B3n-general differences-in-attribution-models=diferencias-en-los-modelos-de-atribuci%C3%B3n h_01J81NN4J4WSJBFHBARKTQ9JG5=diferencias-en-los-modelos-de-atribuci%C3%B3n reducing-discrepancies=diferencias-en-los-modelos-de-atribuci%C3%B3n h_01J81NN4J4EJQH47YJF0H5M97G=diferencias-en-los-modelos-de-atribuci%C3%B3n" />
