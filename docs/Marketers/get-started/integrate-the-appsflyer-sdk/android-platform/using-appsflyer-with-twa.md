---
title: Uso de AppsFlyer con TWA
metadata:
  keywords:
    - Web View
    - Developers
    - TWA
    - PWA
    - Trusted web activities
    - Progressive web apps
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-26T05:08:01Z'
  edited_at: '2026-08-12T12:00:34Z'
  id: 360002330178
  locale: es
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/es/articles/360002330178
---
> **De un vistazo:** Utiliza AppsFlyer con actividades web de confianza (TWA) para medir las instalaciones y registrar eventos in-app.

## Introducción

### ¿Qué son las actividades web de confianza?

Las actividades web de confianza (TWA, por sus siglas en inglés) son una nueva forma de integrar contenido web con tu aplicación de Android. El desafío con las TWA es poder registrar los eventos in-app. Hablamos sobre este desafío en este artículo. Para obtener más información sobre las TWA, consulta <Anchor target="_blank" href="https://developers.google.com/web/updates/2019/02/using-twa">aquí</Anchor>.

Las TWA también se pueden utilizar con aplicaciones web progresivas.

### ¿Qué son las aplicaciones web progresivas?

Las aplicaciones web progresivas (PWA) son aplicaciones que ofrecen una experiencia similar a una aplicación, pero que en realidad están completamente basadas en la web. Una forma de PWA es una aplicación de Android cuyas actividades se basan en TWA. Esta es la forma de PWA que se analiza en este artículo. Las TWA te permiten integrar tu PWA dentro de una aplicación de Android independiente, lo que te permite presentar tu aplicación PWA existente en Play Store.

La otra forma, que se basa exclusivamente en la web, no se analiza en este artículo. Para obtener más información sobre las PWA, consulta <Anchor target="_blank" href="https://developers.google.com/web/progressive-web-apps/">aquí</Anchor>.

Esta pestaña analiza la PWA que está integrada en una actividad web de confianza, un navegador web de pantalla completa in-app. Estas aplicaciones tienen la <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">clase de aplicación global de Android</Anchor> pero cuyas actividades se basan únicamente en la web.

Esta forma de PWA te permite medir las instalaciones. La otra forma de PWA, aquellas que están puramente basadas en web, no te dan la opción de medir las instalaciones.

## TWA

<div id="sending-inapp-events-from-twa" />

<Accordion title="Envío de eventos in-app desde TWA">

Los eventos in-app se envían mediante el SDK de AppsFlyer desde actividades de la aplicación nativa. Dado que la TWA está basada en la web y no es una actividad nativa, no puedes enviar eventos in-app utilizando el SDK de AppsFlyer. Puedes utilizar <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">eventos in-app de servidor a servidor</Anchor> como alternativa. Sigue las instrucciones a continuación para enviar eventos de servidor a servidor con TWA.

### Requisitos previos

Antes de que puedas comenzar a enviar eventos desde TWA a AppsFlyer, haz lo siguiente:

1. Agrega el siguiente repositorio al archivo gradle a nivel de proyecto:  

   ```java
   maven { url "https://jitpack.io"}
   ```
2. Agrega las siguientes bibliotecas:
   * Para bibliotecas de android.support:
     * Agrega lo siguiente en tu build.gradle:  
       implementation 'com.github.GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     * Importa las siguientes bibliotecas:

       ```java
       import android.support.customtabs.CustomTabsClient;
       import android.support.customtabs.CustomTabsIntent;
       import android.support.customtabs.CustomTabsServiceConnection;
       import android.support.customtabs.CustomTabsSession;
       import android.support.customtabs.trusted.TrustedWebActivityIntentBuilder;
       import static android.support.customtabs.TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   * Para bibliotecas de androidX:
     * Agrega lo siguiente en tu build.gradle:  

       ```java
       implementation 'com.github.GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```
     * Importa las siguientes bibliotecas:

       ```java
       import androidx.browser.customtabs.CustomTabsClient;
       import androidx.browser.customtabs.CustomTabsIntent;
       import androidx.browser.customtabs.CustomTabsServiceConnection;
       import androidx.browser.customtabs.CustomTabsSession;
       import androidx.browser.trusted.TrustedWebActivityIntentBuilder;
       ```

### Obtención del ID de AppsFlyer

Para enviar eventos de servidor a servidor, necesitas el ID de AppsFlyer. Puedes obtener el ID de AppsFlyer desde el SDK de AppsFlyer para Android.

Primero, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">integrar el SDK de AppsFlyer para Android</Anchor>. Luego puedes obtener el ID de AppsFlyer usando la siguiente API del SDK:

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

### Envío del ID de AppsFlyer a TWA

Puedes enviar el ID de AppsFlyer de dos maneras:

<div id="append-appsflyer-id-and-customer-user-id-to-url" />

<Accordion title="Agregación del ID de AppsFlyer y el ID de usuario del cliente a la URL">

Cuando creas una intención de actividad web de confianza, puedes pasar parámetros a su URL:

```java
private void launchTwa(String cuid, String af_id) {

    CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Configurar la CustomTabsSession que se utiliza para crear un intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Crear el intent para iniciar TWA usando una URL con parámetros de consulta que la aplicación web pueda leer
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri + "?cuid=" + cuid + "&appsflyer_id=" + af_id));
            Intent twaIntent = twaIntentBuilder.build(session);

            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### Obtención del ID de AppsFlyer

Una vez que se inicia la actividad web, puedes recuperar el ID de AppsFlyer usando un simple fragmento de JavaScript:

```javascript
let url = new URL(document.location.href);
    let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

Una vez que tengas el ID de AppsFlyer, guárdalo en el almacenamiento local para usarlo más adelante.

</Accordion>

<div id="sending-appsflyer-id-through-custom-headers" />

<Accordion title="Envío de ID de AppsFlyer a través de encabezados personalizados">

Puedes pasar encabezados personalizados a las actividades web de confianza. El servidor obtiene estos encabezados, los configura en cookies y los envía al navegador. Luego puedes recuperar el ID de AppsFlyer usando javascript:

```java
private void launchTwa(String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Configurar la CustomTabsSession que se utiliza para crear un intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Crear el intent para iniciar TWA usando una URL con parámetros de consulta que la aplicación web pueda leer
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Pasar encabezados personalizados adicionales al intent para que la aplicación web pueda leerlos
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=appsflyer_id" + af_id");
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### Obtención del ID de AppsFlyer

JavaScript no proporciona una API que permita a los desarrolladores acceder a los encabezados. Por lo tanto, el servidor debe enviar los datos de conversión a la actividad web como una cookie. El servidor obtiene los encabezados personalizados que contienen el ID de AppsFlyer, analiza los datos y los envía a la página web como una cookie.

Cuando se carga la página, se debe configurar un fragmento de JavaScript para recuperar la cookie de ID de AppsFlyer.

```javascript
// get the conversion data cookie 
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id); + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// obtener la cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id);
```

</Accordion>

### Envío del evento in-app

Para enviar eventos in-app, debes enviar los datos del evento a tu servidor y hacer que tu servidor envíe el evento a AppsFlyer. Existen algunos otros requisitos previos para enviar eventos in-app:

* <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Clave de desarrollador del SDK</Anchor> - **¡Importante! <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Clave de desarrollador del SDK</Anchor>:** ¡Importante! La clave de desarrollador del SDK es un valor confidencial y no debería estar presente en la TWA. Si vas a utilizar TWA y a enviar eventos in-app de servidor a servidor, almacena siempre la clave de desarrollador del SDK de forma segura en el lado del servidor.
* ID de aplicación: el ID de la aplicación tal como aparece en Android Manifest.xml.

Una vez que tengas estos tres parámetros (ID de AppsFlyer, clave de desarrollador del SDK, ID de la aplicación), podrá enviar el evento in-app. Siempre que tenga lugar un evento en la actividad web, debes enviar una solicitud a tu servidor web para manejar este evento. El servidor web obtiene los datos relacionados con el evento, lo compone y lo envía a AppsFlyer.

Consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile#api-de-eventos-de-servidor-a-servidor-para-móviles">aquí</Anchor> para ver ejemplos de cómo enviar eventos in-app de servidor a servidor.

</Accordion>

<div id="customizing-web-content-with-conversion-data" />

<Accordion title="Personalización del contenido web con datos de conversión">

El SDK de AppsFlyer te proporciona datos de conversión a través de dos API:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Obtener datos de conversión</Anchor>: se llama cuando la aplicación se inicia por primera vez después de una instalación y para inicios posteriores de la aplicación.
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/api-reference#onappopenattribution">Atribución de apertura de la aplicación</Anchor>: se llama cuando la aplicación tiene un enlace profundo para usar OneLink.

Puedes utilizar datos de conversión para personalizar el contenido web.

### Envío de datos de conversión a TWA

Una vez que obtengas los datos de conversión de cualquiera de los métodos enumerados anteriormente, puedes enviarlos a tu servidor web. Para hacerlo, usa encabezados personalizados:

```java
private void launchTwa(Map<String, String> conversionData, String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Configurar la CustomTabsSession que se utiliza para crear un intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Crear el intent para iniciar TWA usando una URL con parámetros de consulta que la aplicación web pueda leer
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Pasar encabezados personalizados adicionales al intent para que la aplicación web pueda leerlos
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=" + af_id");
            customHeaders.putString("conversion_data", conversionData);
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

### Obtención de datos de conversión del lado del cliente

JavaScript no proporciona una API que permita a los desarrolladores acceder a los encabezados. Por lo tanto, el servidor debe enviar los datos de conversión a la actividad web como una cookie. El servidor obtiene los encabezados personalizados que contienen los datos de conversión, analiza los datos y los envía a la página web como una cookie.

Cuando se carga la página, se debe configurar un fragmento de JavaScript para recuperar la cookie de datos de conversión y personalizar el contenido en consecuencia. Por ejemplo, si un usuario instala la aplicación desde una campaña de ofertas de vuelos, puedes completar la actividad web con contenido relevante para las ofertas que promociona la campaña.

```javascript
// get the conversion data cookie 
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id); + name + '=([^;]*)(;|$)');
    return v ? // get the conversion data cookie 
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('conversion_data'));
console.log(conversionData);
/*
conversion data example:
{ 
        campaign: "CAMPAIGN_NAME", // "None" if not specified on the link
        media_source: "MEDIA_SOURCE", //"None" if not specified on the link     
        cost_cents_USD : "0",
        is_first_launch: true,
        install_time: "2018-12-30 23:59:39.330",
        orig_cost: "0.0",
        af_click_lookback: "7d",
        click_time: "2018-12-30 23:59:09",
        cost_cents_USD: "0",
        af_status: "Non-organic"
}
*/
```

Para obtener más información sobre los casos de uso de datos de conversión, consulta <Anchor target="_blank" href="/marketers/es/docs/conversion-data-payloads-and-scenarios">aquí</Anchor>.

</Accordion>

## PWA

<div id="measuring-installs-for-pwa" />

<Accordion title="Medición de instalaciones de PWA">

Al igual que con cualquier otra aplicación de Android, puedes integrar el SDK de AppsFlyer con la aplicación para medir las instalaciones y obtener datos de conversión.

Para medir las instalaciones, todo lo que necesitas hacer es integrar el SDK siguiendo las instrucciones <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">aquí</Anchor>.

</Accordion>

<div id="customizing-content-using-conversion-data" />

<Accordion title="Personalización del contenido utilizando datos de conversión">

Puedes personalizar el contenido web según la campaña que solicita al usuario que instale tu aplicación. Por ejemplo, si un usuario instala una aplicación de una campaña que le ofrece un 20 % de descuento en productos de tu tienda web. Puedes obtener los datos de conversión y aplicar el descuento tan pronto como la aplicación abra la actividad web.

Para obtener información sobre el uso de datos de conversión para personalizar el contenido web, sigue las instrucciones [aquí](/docs/using-appsflyer-with-twa#envío-de-datos-de-conversión-a-twa).

</Accordion>

<div id="recording-events-in-pwa" />

<Accordion title="Registro de eventos en PWA">

La PWA hace uso de las TWA, que son esencialmente actividades web. Dado que la TWA está basada en la web y no es una actividad nativa, no puedes enviar eventos in-app utilizando el SDK de AppsFlyer. Como alternativa, puedes utilizar eventos in-app de servidor a servidor.

Sigue las instrucciones [aquí](/docs/using-appsflyer-with-twa#sending-inapp-events-from-twa) para aprender cómo enviar eventos in-app para PWA.

</Accordion>

<div data-zendesk-anchors="introduction=introducci%C3%B3n what-are-trusted-web-activities=qu%C3%A9-son-las-actividades-web-de-confianza what-are-progressive-web-apps=qu%C3%A9-son-las-aplicaciones-web-progresivas prerequisites=requisitos-previos getting-the-appsflyer-id=obtenci%C3%B3n-del-id-de-appsflyer sending-the-appsflyer-id-to-twa=env%C3%ADo-del-id-de-appsflyer-a-twa retrieving-the-appsflyer-id=obtenci%C3%B3n-del-id-de-appsflyer-1 retrieving-the-appsflyer-id::a3f31d46=obtenci%C3%B3n-del-id-de-appsflyer-2 sending-the-inapp-event=env%C3%ADo-del-evento-in-app sending-conversion-data-to-twa=env%C3%ADo-de-datos-de-conversi%C3%B3n-a-twa fetching-the-conversion-data-from-the-clientside=obtenci%C3%B3n-de-datos-de-conversi%C3%B3n-del-lado-del-cliente" />
