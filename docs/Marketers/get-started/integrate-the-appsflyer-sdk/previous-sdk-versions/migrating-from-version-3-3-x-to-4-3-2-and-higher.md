---
title: Migración de la versión 3.3.X a la 4.3.2 y posteriores
metadata:
  keywords:
    - Advertisers
    - Developers
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
  created_at: '2016-02-03T10:37:42Z'
  edited_at: '2026-08-12T12:02:46Z'
  id: 207606796
  locale: es
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/es/articles/207606796
---
> **Resumen:** Consideraciones para migrar versiones del SDK de AppsFlyer para Android.

Se han realizado cambios importantes en la integración del SDK de Android.

Los cambios principales son:

* El SDK ahora es un singleton, lo que significa que todas las llamadas a las API deben hacerse de la siguiente manera:

```java
AppsFlyerLib.getInstance().setCustomerUserId("myId");
```

* **SetAppsFlyerKey()**– se eliminó este método; como resultado, esperamos recibir la clave de desarrollador mediante el nuevo método init: AppsFlyerLib.getInstance().startTracking (this,"YOUR\_APPSFLYER\_DEV\_KEY")
* Se eliminaron **sendTracking()**, **onActivityPause()** y **onActivityResume()** . El SDK detecta los lanzamientos automáticamente
* **Deep Link** - para las actividades compatibles con Deep Linking, el desarrollador debe llamar a:

```java
AppsFlyerLib.getInstance().sendDeepLinkData(this) desde onCreate()
```

de la actividad mostrada.

Esto solo es necesario si la aplicación no se está ejecutando en segundo plano.

* **Registro** - el valor predeterminado del indicador de registro se ha cambiado a false. Además, si la marca está desactivada, no se imprime ningún registro (corrección de errores). Para activar la marca de registro, el desarrollador debe llamar a:

AppsFlyerLib.getInstance().setDebugLog(true);

Para ver la guía de integración del SDK de AppsFlyer para Android, haz clic <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">aquí</Anchor>.

**Migración a la versión 4.4.0 y posteriores**

El SDK de AppsFlyer para Android v4.4.0 **ya no admite el siguiente receiver** en el manifiesto:

```html Markup
<receiver android:name="com.appsflyer.AppsFlyerLib">
  <intent-filter>
    <action android:name="android.intent.action.PACKAGE_REMOVED"/>
    <data android:scheme="package"/>
  </intent-filter> 
</receiver>
```

Si usas la versión 4.4.0+, **elimina este receptor del archivo de manifiesto**.

El único receptor **obligatorio** para el SDK es el siguiente:

```html Markup
<receiver
  android:name="com.appsflyer.MultipleInstallBroadcastReceiver"
  android:exported="true">
    <intent-filter>
      <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>
```