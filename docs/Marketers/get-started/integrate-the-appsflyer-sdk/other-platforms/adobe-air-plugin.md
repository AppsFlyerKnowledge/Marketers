---
title: Plugin de Adobe AIR
metadata:
  keywords:
    - github
    - Adobe
    - Air
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-12-09T11:32:45Z'
  edited_at: '2026-08-12T12:02:19Z'
  id: 207032226
  locale: es
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/es/articles/207032226
---
> **En resumen:** Integra el SDK de AppsFlyer en aplicaciones iOS/Android desarrolladas con la plataforma de desarrollo Adobe AIR para medir las instalaciones, los eventos in-app, las fuentes de medios y más.

<div id="plugin-information" />

## Información del plugin

Plataformas compatibles:

* Android
* iOS 6+

Basado en:

* iOS AppsFlyer SDK V6.0.3
* SDK para Android de AppsFlyer V5.4.1

<div id="installation-and-implementation" />

## Instalación e implementación

<div id="installation" />

<Accordion title="Instalación">

Descarga el archivo <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/AppsFlyerAIRExtension.ane">AppsFlyerAIRExtension.ane</Anchor> de la carpeta bin. Añade el ANE a tu proyecto y asegúrate de que el IDE esté marcado para empaquetarlo.

Si lo siguiente no se ha añadido automáticamente, añádelo a APP\_NAME-app.xml:

```html Markup
<extensions>
  <extensionID>com.appsflyer.adobeair</extensionID>
</extensions>
```

<div id="notes-for-android-apps" />

> 📘 **Notas para aplicaciones Android**
>
> * En el Dashboard de AppsFlyer, tendrás que añadir el prefijo "air." al nombre del paquete, ya que Air lo añade automáticamente. For example - una aplicación con el nombre de paquete "**com.test.android**", debe configurar el ID de la aplicación en el Dashboard de AppsFlyer como "**air.com.test.android**".
> * Añade los siguientes permisos al Android Manifest (en la descripción de la aplicación `APP_NAME-app.xml`):
>
>   ```html Markup
>   <uses-permission android:name="android.permission.INTERNET"/>
>   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
>   <uses-permission android:name="com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE" />
>   ```
> * Añade la siguiente etiqueta meta al Android Manifest dentro de la etiqueta de la aplicación (en la descripción de la aplicación `APP_NAME-app.xml`):
>
>
>   ```html Markup
>   meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
>   ```
>
> Como resultado, tu Manifest debería verse así:
>
> <Image align="center" alt="" src="https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png" />
>
> **Importante:** Debido a algunas limitaciones de <Anchor target="_blank" href="https://help.adobe.com/en_US/air/build/WS5b3ccc516d4fbf351e63e3d118666ade46-7fd9.html">ADT</Anchor>, después de compilar el APK faltan algunos archivos importantes.
>
> Para añadir esos archivos (con la ayuda de **un script automatizado** ):
>
> 1. Coloca en un único directorio de tu elección:
>    * Archivo APK
>    * Keystore que se usó para firmar el APK
>    * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/af_apk_fix.sh">script af\_apk\_fix.sh</Anchor>
> 2. Ejecuta `./af_apk_fix.sh` e introduce la información solicitada cuando se te pida.
>
> Esto es lo que hace el script. En caso de que haya algún problema, puedes realizar estos pasos manualmente:
>
> 1. Decodifica el APK con <Anchor target="_blank" href="https://ibotpeaches.github.io/Apktool/">apktool</Anchor>. Esto creará la carpeta app\_name.
>    `apktool d app_name.apk`
> 2. Descarga el [jar/aar del SDK de AppsFlyer](https://repo.maven.apache.org/maven2/com/appsflyer/af-android-sdk/5.4.1/af-android-sdk-5.4.1.aar) de la misma versión que se usó en el APK.
> 3. Extrae los archivos `a-` y `b-` del jar (renombrando el jar como un zip) y colócalos en la carpeta del apk descompilado, en `app_name/unknown/com/appsflyer/internal`
> 4. Edita `apktool.yml` añadiendo estas líneas debajo de `unknownFiles:`
>
>    ```
>    com/appsflyer/internal/b-: '0'
>    com/appsflyer/internal/a-: '0'
>    ```
>
>    Mira la captura de pantalla de ejemplo que aparece a continuación.
>
>    [![](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)
> 5. Compila de nuevo el APK (aparecerá en la carpeta `app_name/dist` ).
>    `apktool b app`
> 6. Firma el APK.
>
>    ```html Markup
>    jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore myKeystore.keystore app_name/dist/app_name.apk myKey
>    ```
> 7. Zipalign el apk (para poder subirlo a Google Play)
>
>    ```html Markup
>    zipalign -f -v 4 app_name/dist/app_name.apk app_name/dist/zipalign_app_name.apk
>    ```
> 8. Verifica la alineación con zipalign
>
>    ```html Markup
>    zipalign -c -v 4 app_name/dist/zipalign_app_name.apk
>    ```
> 9. ¡Tu apk `zipalign_app_name.apk` está lista para usar!

</Accordion>

<div id="implementation" />

<Accordion title="Implementación">

Importa la extensión de AppsFlyer a tu proyecto:

```html Markup
import AppsFlyerInterface;
```

Crea la interfaz de AppsFlyer:

```html Markup
private static var appsFlyer:AppsFlyerInterface; 
appsFlyer = new AppsFlyerInterface();
```

[Opcional] Si quieres realizar Deep Linking o acceder a los datos de conversión de AppsFlyer desde la aplicación, registra el detector de conversiones:

```html Markup
appsFlyer.registerConversionListener();
```

Configura la clave de desarrollador y el ID de la app de iOS (opcional) e inicializa el SDK:

```html Markup
appsFlyer.appsFlyer.init("DevKey", "iOSAppID");
```

Inicializa el registro de sesiones (registra automáticamente los inicios de la aplicación y las transiciones de segundo plano a primer plano) con la DevKey y el ID de la aplicación iOS (opcional):

```html Markup
appsFlyer.start("DevKey", "iOSAppID");
```

</Accordion>

<div id="deep-linking" />

<Accordion title="Enlaces profundos">

Para recibir la información relevante de AppsFlyer del enlace profundo utilizado:

1. Registra los siguientes слушadores de eventos:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.APP_OPEN_ATTRIBUTION, eventHandler); // success \nappsFlyer.addEventListener(AppsFlyerEvent.ATTRIBUTION_FAILURE, eventHandler); // error
   ```
2. Gestiona la respuesta en un controlador de eventos correspondiente:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("Evento de AppsFlyer: " + event.type + "; \nDatos: " + event.data);
   }
   ```

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Enlaces profundos diferidos">

Para recibir los datos de conversión de la instalación actual:

1. Registra los siguientes слушadores de eventos:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_DATA_LOADED, eventHandler); // success\nappsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_FAILED, eventHandler); // error
   ```
2. Gestiona la respuesta en un controlador de eventos correspondiente:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("Evento de AppsFlyer: " + event.type + "; \nDatos: " + event.data);
   }
   ```

</Accordion>

<div id="imei-and-android-id-collection-android-only" />

<Accordion title="Recopilación de IMEI e ID de Android (solo Android)">

**Importante**! Las aplicaciones con servicios de Google Play deberían evitar la recopilación del IMEI, ya que esto viola la política de Google Play.

De manera predeterminada, el SDK no recopila el IMEI ni el ID de Android si la versión del sistema operativo es superior a KitKat (4.4) y el dispositivo contiene servicios de Google Play.

Para enviar explícitamente estos ID a AppsFlyer, los desarrolladores pueden usar las siguientes API y colocarlas antes de inicializar el SDK.

Si la aplicación NO contiene Google Play Services, el SDK recopila el IMEI y el ID de Android.

**Activar/desactivar la recopilación de IMEI (desactivada de forma predeterminada)**

```html Markup
appsFlyer.setCollectIMEI(bool);
```

**Configurar manualmente los datos de IMEI**

```html Markup
appsFlyer.setImeiData("imeiString");
```

**Activar/desactivar la recopilación del ID de Android (desactivada de forma predeterminada)**

```html Markup
appsFlyer.setCollectAndroidID(bool);
```

**Configurar manualmente los datos del ID de Android**

```html Markup
appsFlyer.setAndroidIdData("AndroidIDString");
```

</Accordion>

<div id="api-reference" />

## Referencia de API

<div id="api-methods" />

<Accordion title="Métodos API">

<Table>
  <thead>
    <tr>
      <th>
        Nombre
      </th>
      <th>
        Nota
      </th>
      <th>
        Firma/ejemplo
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        logEvent
      </td>
      <td>
        Registra eventos in-app.
      </td>
      <td>
        ```html Markup
        var param:String = "Deposit";
        var value:String = '{"amount":10, "FTDLevel":"-"}';
        appsFlyer.logEvent(param, value);
        ```
      </td>
    </tr>
    <tr>
      <td>
        comenzar
      </td>
      <td>
        Envía un evento de registro de sesión, independientemente del estado de la app.
      </td>
      <td>
        ```html Markup
        appsFlyer.start();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setAppUserId
      </td>
      <td>
        Obtiene el ID del usuario tal como se usa en la aplicación.
      </td>
      <td>
        ```html Markup
        appsFlyer.setAppUserId("user_id_as_used_in_the_app");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setUserEmails
      </td>
      <td>
        Obtiene el correo electrónico del usuario.
      </td>
      <td>
        ```html Markup
        appsFlyer.setUserEmails("example@example.com");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setCurrency
      </td>
      <td>
        Establece la moneda para registrar eventos de ingresos, por ejemplo, USD.
      </td>
      <td>
        ```html Markup
        appsFlyer.setCurrency("USD");
        ```
      </td>
    </tr>
    <tr>
      <td>
        detener
      </td>
      <td>
        Se usa cuando quieres desactivar todo el registro del SDK por motivos de cumplimiento legal y de privacidad. Una vez que se invoca esta API, nuestro SDK deja de comunicarse con nuestros servidores.
      </td>
      <td>
        ```html Markup
        appsFlyer.stop();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setDebug
      </td>
      <td>
        Activa o desactiva los registros de depuración de AppsFlyer.

        **Importante:** Do not publiques la app en tiendas de aplicaciones con los registros de depuración habilitados.
      </td>
      <td>
        ```html Markup
        appsFlyer.setDebug(bool);
        ```
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="plugin-information=informaci%C3%B3n-del-plugin installation-and-implementation=instalaci%C3%B3n-e-implementaci%C3%B3n api-reference=referencia-de-api" />
