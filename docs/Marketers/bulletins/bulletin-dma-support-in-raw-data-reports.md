---
title: 'Boletín: soporte de DMA en los Reportes de raw data'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2026-10-20T03:55:34Z'
  id: 25485269115793
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/25485269115793
---
| **¿Qué hay de nuevo?** | Los siguientes campos de consentimiento de DMA se están añadiendo a las herramientas de raw data de AppsFlyer:<ul><li>**gdpr\_applies:** Indica si el usuario está bajo la jurisdicción de DMA (true) o no (false).</li><li>**ad\_user\_data\_enabled**: Indica si el usuario ha dado su consentimiento para permitir que Google utilice sus datos a nivel de usuario para medición y publicidad personalizada (true) o no (false).</li><li>**ad\_personalization\_enabled**: Indica si el usuario ha dado su consentimiento para permitir que Google utilice sus datos a nivel de usuario para anuncios personales (true), o no (false).</li><li>**raw\_consent\_data**: Devuelve un objeto JSON con todos los datos de consentimiento sin procesar, tal como los envió el anunciante a AppsFlyer. La información enviada en este objeto se utiliza después para completar los tres campos anteriores.<ul><li>Este campo no está disponible en la exportación de raw data ni en Pull API</li></ul></li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | <ul><li>Página de exportación de raw data y Pull API - 3 de junio de 2024</li><li>Push API y Data Locker - 14 de octubre de 2024</li></ul> |
| **Donde** | <ul><li>Página de exportación de raw data</li><li>API pull</li><li>API Push</li><li>Data Locker</li></ul> |
| **Quién debe saberlo** | <ul><li>Anunciantes y agencias que usan la página de exportación de raw data, Push API, Pull API y Data Locker para exportar raw data (a nivel de evento) desde AppsFlyer.</li></ul> |
| **Cómo te afecta** | <ul><li>Configura tu esquema y cualquier otro proceso relacionado con el consumo de los datos.</li><li>Asegúrate de que los campos nuevos no alteren tu esquema para Push API y Data Locker.</li></ul> |
| **Información adicional** | Consulta nuestro artículo <Anchor target="_blank" href="/marketers/es/docs/support-google-eu-consent-policy">Soporte de la política de consentimiento de Google para la UE</Anchor>. |