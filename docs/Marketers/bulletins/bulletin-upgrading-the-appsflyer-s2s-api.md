---
title: 'Boletín: Actualización de la API S2S de AppsFlyer'
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
  created_at: '2023-11-28T16:26:35Z'
  edited_at: '2026-10-20T03:55:51Z'
  id: 20509378973457
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/20509378973457
---
| **¿Qué hay de nuevo?** | Para ofrecer una experiencia más segura en el uso de la API y reducir el fraude, AppsFlyer ha actualizado su API Server-to-Server (S2S) para eventos in-app. El endpoint actual quedará obsoleto en el futuro y recomendamos empezar a planificar el cambio.<br /><br />AppsFlyer está trabajando en una solución para partners tecnológicos externos que envían datos en tu nombre. |
| --- | --- |
| **Fecha de entrada en vigor** | 12 de diciembre de 2023 |
| **Prerrequisitos** | Solo un administrador puede actualizar la nueva API S2S. |
| **Acción requerida** | Actualiza los siguientes campos para enviar eventos in-app por S2S a AppsFlyer:<ol><li>Ve a la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_s2s_inappevent">API POST S2S de evento in-app</Anchor>.</li><li>Sustituye la URL:<br />De <Anchor target="_blank" href="https://api2.appsflyer.com/inappevent">https://api2.appsflyer.com/inappevent</Anchor><br />Por <Anchor target="_blank" href="https://api3.appsflyer.com/inappevent">https://api3.appsflyer.com/inappevent</Anchor></li><li>Actualiza el encabezado Authorization: sustituye la Dev key por la <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">**nueva clave S2S**</Anchor>.</li><li>Si envías eventos S2S a AppsFlyer a través de un partner integrado (como Segment, Tealium, Amplitude, mParticle, RevenueCat u otros), ponte en contacto con él para saber cómo actualizar la integración.</li></ol> |
| **Medidas recomendadas:** | **Antes de actualizar la nueva API en todas tus llamadas de producción:**<br /><br />Recomendamos encarecidamente enviar varios eventos in-app de prueba al nuevo endpoint y **asegurarte de que no se devuelve ningún error**. |
| **Lo que debes saber** | Si te preocupa que se estén enviando eventos de fraude al endpoint antiguo después de haber actualizado la nueva API, ponte en contacto con tu CSM o con el soporte de AppsFlyer. Asegúrate de incluir los App ID correspondientes.<br /><br />Cuando completes la migración a producción, AppsFlyer bloqueará el endpoint de la API antigua para estas aplicaciones, por lo que también se bloquearán todas las llamadas de fraude. |
| **¿Quién debe actualizar la nueva API?** | Solo los anunciantes deben actualizar la nueva API S2S para eventos in-app. |
| **Acerca de la API S2S** | Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">S2S y tokens de API</Anchor>. |