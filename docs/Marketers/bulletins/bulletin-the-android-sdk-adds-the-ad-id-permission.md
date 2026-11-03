---
title: 'Boletín: El SDK de Android añade el permiso AD_ID'
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
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2026-10-20T03:56:32Z'
  id: 7569900844689
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/7569900844689
---
> **Resumen:** A partir de AppsFlyer Android SDK V6.8.0, el permiso AD\_ID se declara en el AndroidManifest.xml del SDK.

| **Background** | A principios de 2022, Google anunció un cambio en el comportamiento de Google Play Services y la obtención del ID de publicidad de Android.<br /><br />Según el <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">anuncio</Anchor>, las aplicaciones orientadas a Android 13 (API 33) y versiones posteriores tendrán que declarar un permiso normal de los servicios de Google Play en su archivo de manifiesto para poder acceder al ID de publicidad del dispositivo.<br /><br />El permiso se concede a la aplicación en el momento de la instalación y no requiere ninguna interacción por parte del usuario. |
| --- | --- |
| **Qué ha cambiado** | A partir de AppsFlyer Android SDK V6.8.0, el permiso AD\_ID se declara en el AndroidManifest.xml del SDK. Cuando se compila la aplicación, el manifiesto del SDK se fusiona por defecto con el manifiesto de tu aplicación, y el permiso se añade incluso si la aplicación no declara explícitamente el permiso. Si el permiso existe tanto en la aplicación como en el SDK, quiere decir que funciona perfectamente y no habrá colisión. |
| **Lo que debes saber** | <ul><li>Si estás utilizando el SDK V6.8.0 y tienes el permiso AD\_ID en el manifiesto de tu aplicación, puedes eliminarlo opcionalmente del manifiesto y dejar que el SDK lo añada por ti.</li><li>Si utilizas una versión del SDK **anterior** a la V6.8.0 y tu aplicación está orientada a Android 13 (API 33) y versiones superiores, deberás añadir el permiso AD\_ID a tu aplicación para que el SDK pueda acceder al ID de publicidad.</li><li>**Aplicaciones dirigidas a niños:** Según <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">la Política de Google</Anchor>, las aplicaciones dirigidas a niños no deben transmitir el ID de publicidad. Si estás creando una aplicación para niños y utilizas SDK V6.8.0 o superior, debes revocar el permiso AD\_ID. Consulta las instrucciones para desarrolladores <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">aquí</Anchor>.</li></ul> |