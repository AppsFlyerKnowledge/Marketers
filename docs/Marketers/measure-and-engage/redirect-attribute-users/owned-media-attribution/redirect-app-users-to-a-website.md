---
title: Redirigir a los usuarios de la app a un sitio web
metadata:
  keywords:
    - OneLink
    - Marketers
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2022-02-22T11:45:43Z'
  edited_at: '2026-08-12T12:25:04Z'
  id: 4460838224273
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/4460838224273
---
> **De un vistazo:** Redirige a los usuarios de la app a una URL web o a una página de redes sociales mediante una URL generada con OneLink.

<div id="redirect-app-users-to-a-web-url" />

## Redirigir a los usuarios de la app a una URL web

Los anunciantes pueden publicar URL de OneLink que dirijan a páginas web externas o a sitios de redes sociales. AppsFlyer mide los clics en el enlace dentro de la app, lo que te permite determinar la eficacia del anuncio.

**Requisitos previos**: Una cuenta de AppsFlyer con al menos una aplicación.

**Para configurar la redirección de app a web**:

1. Configura una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>.
   * En la sección **When app is installed**, asegúrate de no configurar ningún método para abrir la app (Universal Links, App Links o esquema URI).
2. Crea un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">enlace personalizado de OneLink</Anchor>.
   * En la sección **When app isn’t installed**, asegúrate de que la configuración de redirección apunte a la URL web deseada.
   * No añadas el parámetro `af_dp` con un esquema URI.
3. Asegúrate de que el dominio al que rediriges a los usuarios aparezca en tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de permitidos de redirección de dominios</Anchor>.   
   **Nota:** Configurar una lista de permitidos de redirección de dominios es obligatorio para garantizar que los usuarios sean redirigidos a dominios verificados y fiables.

**Para probar tu enlace**:

**Requisitos previos**: Un dispositivo móvil con la aplicación instalada.

1. Envía la URL corta o larga a tu teléfono y haz clic en ella.  
   **Nota**: Envíate el enlace por correo electrónico o WhatsApp y ábrelo en tu teléfono. No lo pegues en notas de iOS ni directamente en un navegador móvil.
2. Deberías ser redirigido a la URL web.

<div data-zendesk-anchors="redirect-app-users-to-a-web-url=redirigir-a-los-usuarios-de-la-app-a-una-url-web 01JENAXDEE8C81DN0JGPWPZQSY=redirigir-a-los-usuarios-de-la-app-a-una-url-web" />
