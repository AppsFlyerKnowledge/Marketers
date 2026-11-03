---
title: 'Boletín: Los TTL de las URL cortas de OneLink se extienden automáticamente'
metadata:
  keywords:
    - OneLink
    - User invite
    - OneLink API
    - Developers
    - Marketers
    - bulk upload
    - Link Management
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-03-10T11:17:11Z'
  edited_at: '2026-10-20T03:56:37Z'
  id: 4667188714001
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/4667188714001
---
| **¿Qué hay de nuevo?** | El tiempo de vida predeterminado (TTL) de las URL cortas de OneLink creadas mediante carga masiva, SDK (invitación de usuario) y la API de OneLink se extiende cada vez que se hace clic en el enlace:<ul><li>Carga masiva: 365 días</li><li>Invitación de usuario de SDK: 60 días</li><li>API de OneLink: 31 días</li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | 14 de enero de 2024 |
| **Donde** | <ul><li>Carga masiva de OneLink</li><li>Enlaces de invitación de usuario (URL de OneLink creadas mediante SDK)</li><li>OneLink API</li></ul> |
| **Qué ha cambiado** | **Antes del cambio**: las URL cortas de OneLink creadas mediante carga masiva, SDK (invitación de usuario) y la API de OneLink tenían un tiempo de vida (TTL). Cuando el TTL caducaba, los enlaces dejaban de funcionar según lo previsto y no proporcionaban datos de atribución.<br /><br />**Después del cambio**: las URL cortas de OneLink creadas mediante carga masiva, SDK (invitación de usuario) y la API de OneLink siguen teniendo un TTL. Sin embargo, cada vez que se hace clic en el enlace, el TTL se amplía:<ul><li>Carga masiva: 365 días</li><li>Invitación de usuario de SDK: 60 días</li><li>API de OneLink: 31 días</li></ul> |
| **Lo que debes saber** | <ul><li>El cambio afecta a las URL cortas de OneLink nuevas y ya existentes con TTL.</li><li>Para la API de OneLink:<ul><li>Puedes cambiar el TTL predeterminado añadiendo el parámetro `ttl={value}` y especificando cuántos días, horas o minutos. Por ejemplo, `ttl=7d`, `ttl=12h` o `ttl=10m`.</li></ul></li><li>Para la API de OneLink y la carga masiva:<ul><li>Si no quieres que los TTL de los enlaces se amplíen automáticamente, añade el parámetro `renew_ttl=false` a tus enlaces.<br />**Nota**:<ul><li>El parámetro `renew_ttl` no se muestra en la URL real.</li><li>Para la API de OneLink, el valor es boolean: true (predeterminado) o false.</li></ul></li></ul></li></ul> |