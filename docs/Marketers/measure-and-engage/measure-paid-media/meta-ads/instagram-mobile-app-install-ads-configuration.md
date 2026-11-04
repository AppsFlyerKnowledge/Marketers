---
title: Configuración de anuncios de instalación de la app móvil de Instagram
metadata:
  keywords:
    - Facebook
    - Instagram
    - install ads
    - integrated partner
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-09T01:10:44Z'
  edited_at: '2026-08-12T12:20:02Z'
  id: 207034066
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/207034066
---
> **Resumen:** Añade instalaciones de la aplicación móvil de Instagram a tu cuenta de anuncios de Meta.

<Image alt="instagram_logo.jpg" src="https://files.readme.io/55ab80e2b1ba9d164d978116f3aaaacb9fe7e4571f71e0130a40e1ded16679db-360000492725.jpg" width="101px" />

<div id="setting-up-instagram" />

## Configuración de Instagram

La configuración de Instagram aparece en Anuncios de Meta, en la sección de Integraciones activas de AppsFlyer.

Puedes encontrar la documentación de Meta <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/guides/instagramads/">aquí</Anchor> y <Anchor target="_blank" href="https://www.facebook.com/business/help/1634705703469129">aquí</Anchor>.

1. Vincula tu cuenta de Instagram a Meta Business Manager  

   ![link-inst-with_fb-account.png](https://files.readme.io/c6c7fe17274f0b9af008c4452b4b7ea2233cc5bca8773307fef6afaeb7d06015-11212956311441.png)
2. Una vez añadida en Business Manager, asigna una cuenta de anuncios a tu cuenta de Instagram  

   <Image alt="assign-inst-ad-to-fb.png" src="https://files.readme.io/658dc57d0056a2217a9f0f5c785b87e24c297158b75c5815eddb64930d00ea17-11213052873745.png" width="550px" />
3. Configura los anuncios de Meta en la configuración de Integraciones activas añadiendo el ID de tu aplicación de Facebook.
4. Si no tienes un ID de aplicación de Facebook, crea uno <Anchor target="_blank" href="https://developers.facebook.com/apps">aquí</Anchor>.  
   [![facebook_app_id.png](https://files.readme.io/2e497e1e00c22d0006aebd540b24c47ba4f2907ee9de061dc04ab50bbbe2cc67-14069602144273.png)](https://support.appsflyer.com/hc/article_attachments/49754369845265)

<div id="instagram-landing-page-for-deep-linking" />

## Página de destino de Instagram para deep linking

Actualmente, <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Instagram admite deep linking a aplicaciones iOS mediante Universal Links</Anchor> para Static ads (sin catálogo). iOS Universal Links y Android App Links solo se admiten en campañas en las que se selecciona **App** como destino.

Si necesitas usar enlaces personalizados con Deep Linking en Instagram en campañas en las que no se puede seleccionar **App**, for ejemplo, si configuras una campaña de reconocimiento en Meta - como esta campaña no permite **App** que se seleccione como destino, no se admiten los Universal Links de iOS ni los App Links de Android. Puedes <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">configurar la página de destino de Instagram</Anchor>. Esto te permite usar OneLink con Universal Links en Instagram para dirigir a los usuarios mediante deep linking y ofrecer una mejor experiencia de usuario.

Para los anuncios dinámicos, los Universal Links de iOS, los App Links de Android y los esquemas URI se pueden usar como se indica <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads">aquí</Anchor>.

<div data-zendesk-anchors="setting-up-instagram=configuraci%C3%B3n-de-instagram instagram-landing-page-for-deep-linking=p%C3%A1gina-de-destino-de-instagram-para-deep-linking" />
