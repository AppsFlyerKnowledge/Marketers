---
title: >-
  Boletín: parámetros adicionales disponibles para el deep linking de usuarios
  existentes
metadata:
  keywords:
    - SDK
    - deep link
    - deep linking
    - Developers
    - Marketers
    - OneLink
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-04-27T09:49:22Z'
  edited_at: '2026-10-20T03:56:39Z'
  id: 5733303620113
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/5733303620113
---
> **Resumen:** El método UDL devuelve parámetros adicionales para el deep linking de usuarios existentes.

| **¿Qué hay de nuevo?** | AppsFlyer SDK V6.6+ permite que el método UDL devuelva parámetros adicionales para el deep linking de usuarios existentes (con la app instalada). |
| --- | --- |
| **Fecha de entrada en vigor** | 27 de abril de 2022 |
| **Donde** | Método UDL para el deep linking de usuarios existentes con la app instalada |
| **Qué** | **Antes del cambio:** el método UDL solo devolvía los parámetros `deep_link_value` y `deep_link_sub1-10` para el deep linking de usuarios existentes.<br /><br />**Después del cambio:** el método UDL devuelve todos los parámetros que figuran en el parámetro de enlace, incluidos:<ul><li>`c`</li><li>`pid`</li><li>`path`</li><li>`esquema`</li><li>`host`</li><li>`af_c_id`</li><li>`af_adset`</li><li>`af_adset_id`</li><li>`af_ad`</li><li>`af_ad_id`</li><li>`af_ad_type`</li><li>`af_canal`</li><li>`af_dp`</li><li>`esp_name`</li><li>`enlace`</li></ul> |
| **Lo que debes saber** | **Mejores prácticas**: Aunque estos parámetros están disponibles para el deep linking de usuarios existentes, te recomendamos crear enlaces nuevos usando solo los parámetros `deep_link_value` y `deep_link_sub1-10`, como se documenta en nuestra <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">guía de deep linking</Anchor>.<ul><li>Este cambio solo está pensado para clientes con enlaces existentes que usan métodos heredados de deep linking. Ahora, estos clientes pueden implementar el método UDL para deep linking y usar estos parámetros adicionales para hacer deep linking de usuarios existentes, mientras siguen usando los mismos enlaces. No es necesario crear enlaces nuevos.</li><li>Se requiere el SDK de AppsFlyer v6.6 o superior</li></ul> |