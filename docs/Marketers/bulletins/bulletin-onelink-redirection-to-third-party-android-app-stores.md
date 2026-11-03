---
title: >-
  Boletín: Redireccionamiento de OneLink a tiendas de aplicaciones de terceros
  de Android
metadata:
  keywords:
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
  created_at: '2021-04-08T08:39:22Z'
  edited_at: '2026-10-20T03:56:58Z'
  id: 360019130678
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360019130678
---
| ¿Qué hay de nuevo? | Las plantillas de OneLink ofrecen una opción para redirigir a los usuarios sin tu aplicación a tiendas de aplicaciones de terceros de Android. |
| --- | --- |
| Fecha de entrada en vigor | 19 de mayo de 2021 |
| Donde | <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">OneLink template setup</Anchor> |
| Qué | Antes del cambio: las plantillas de OneLink ofrecían opciones para que los usuarios que no tenían tu aplicación fueran redirigidos a la tienda de aplicaciones de Apple, Google Play o una URL web.<br /><br />Después del cambio: las plantillas de OneLink también brindan opciones para que los usuarios sin tu aplicación sean redirigidos a las siguientes tiendas de aplicaciones de terceros de Android:<ul><li>Huawei AppGallery</li><li>Xiaomi Market</li><li>Tienda de Samsung Galaxy</li><li>Oppo App Market</li><li>Vivo App Store</li></ul> |
| Lo que debes saber | <ul><li>Redirigir a tiendas de aplicaciones de terceros de Android requiere que tu aplicación en las otras tiendas tenga el mismo nombre de paquete que la aplicación de Android seleccionada en tu plantilla de OneLink.</li><li>El nombre del paquete APK (por ejemplo: com.shop.app) se utiliza para el redireccionamiento, así que asegúrate de que el nombre del paquete APK exista en la tienda de aplicaciones de terceros antes de seleccionarlo.</li><li>Solo el nombre del paquete se extrae de la aplicación de Android para redirigir a los usuarios. Por ejemplo, si el nombre de AppsFlyer también incluye un canal, como com.shop.app-store, solo se extrae com.shop.app. En tal caso, la redirección funciona, pero la atribución no.</li><li>Si seleccionas una aplicación de Android que no está en Google Play, debes ingresar una URL a la que se redirige a todos los usuarios de Android.</li></ul>[![](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)<ul><li>Si tu aplicación Android está disponible exclusivamente a través de una tienda de terceros, <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">debes establecer su estado de Google Play como Publicada fuera de la tienda al añadir la aplicación.</Anchor> Si eliges cualquier otro estado, se impedirá la redirección a la tienda de terceros y aparecerá un mensaje de error.</li></ul> |