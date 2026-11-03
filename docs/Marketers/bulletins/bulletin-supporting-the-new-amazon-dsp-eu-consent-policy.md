---
title: >-
  Boletín: Soporte para la nueva política de consentimiento de Amazon DSP en la
  UE
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-20T03:54:19Z'
  id: 45664244736529
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/45664244736529
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | Como parte de la aplicación por parte de Amazon del Digital Markets Act (DMA), Amazon Ads está actualizando su política de consentimiento en la UE. AppsFlyer está implementando los cambios necesarios para cumplir con los requisitos de la política de Amazon, asegurando al mismo tiempo que los anunciantes maximicen el valor de sus canales de marketing en Amazon Ads. |
| **Fecha de entrada en vigor** | <ul><li>Fecha de entrada en vigor en Amazon - 30 de junio de 2026</li><li>Fecha de inicio de soporte en AppsFlyer - 18 de mayo de 2026</li></ul> |
| **Lo que debes saber:** | **Integraciones y audiencia relevantes:** Todos los anunciantes con aplicaciones integradas con Amazon Ads mediante la integración SRN `amazondsp_int` y que tengan actividad publicitaria en la UE (incluidos Reino Unido y Suiza).<br /><br />**Acciones requeridas:** Asegúrate de enviar señales de consentimiento DMA válidas a AppsFlyer para cualquier evento (apertura de la aplicación o evento in-app) de usuarios en la UE, Reino Unido o Suiza.<br /><br />Las señales de consentimiento pueden ser una de las siguientes:<ol><li>**Consentimiento manual:** El único campo obligatorio es `ad_user_data_enabled` como parte del array de consentimiento manual. Los otros campos requeridos para el consentimiento DMA de Google no son relevantes para Amazon.</li><li>**Consentimiento TCF:** Envía la información completa de consentimiento TCF generada por tu CMP y asegúrate de incluir el ID de proveedor de Amazon Ads (`793`) en la lista de proveedores con consentimiento.</li><li>**Cadenas de consentimiento GPP:** Amazon admite cadenas de consentimiento GPP, pero actualmente AppsFlyer no es compatible con ellas.</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>Consulte también**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">Cómo enviar el consentimiento DMA a través del SDK de AppsFlyer</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">Cómo enviar el consentimiento DMA a través de S2S de AppsFlyer</Anchor> (busca `consent_data`)</li></ul> |