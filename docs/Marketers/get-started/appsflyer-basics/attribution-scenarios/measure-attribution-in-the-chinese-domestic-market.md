---
title: Mide la atribución en el mercado nacional de China
metadata:
  keywords:
    - Advertisers
    - China
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-17T12:33:29Z'
  edited_at: '2026-08-12T11:57:32Z'
  id: 360002049858
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/360002049858
---
> **De un vistazo:** Atribución de dispositivos Android sin GAID mediante OAID o IMEI. Mejores prácticas para ver datos de atribución en AppsFlyer.

<div id="attribution-android-apps-in-the-chinese-domestic-market" />

## Atribución de aplicaciones Android en el mercado nacional chino

En China, los propietarios de aplicaciones se enfrentan a varios retos:

* Google Play Services (GPS) no está activo en la mayoría de los dispositivos Android, lo que significa que no tienen GAID.
* El uso de tiendas de aplicaciones Android de terceros crea oportunidades para el secuestro de tiendas por parte de los fabricantes de dispositivos.
* No se puede acceder a los servidores de atribución o responden con lentitud.
* Gestionar y ver datos de atribución de Google Play y de tiendas de aplicaciones Android de terceros.

Con AppsFlyer, estos retos pueden superarse de las siguientes formas:

* Implementar atribución basada en <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor>
* Usar el IMEI del dispositivo como alternativa al GAID en dispositivos con Android 28 o una versión anterior
* Preparar APKs con identificadores únicos para detectar el Hijacking de tiendas Android
* Configurar enlaces de atribución que se reconozcan en China

<div id="preparing-the-app" />

## Preparar la aplicación

Integra el SDK en la aplicación y prepara el APK con uno de los métodos según la versión de Android de los dispositivos de destino.

<div id="integrate-the-sdk-in-the-app" />

<Accordion title="Integra el SDK en la aplicación">

**Usa IMEI y/o OAID en lugar de GAID**

Por lo general, Google Play Services no está instalado en los dispositivos Android suministrados en China. Esto significa que no hay ningún GAID que puedas usar como identificador único de atribución.

Una alternativa al uso de GAID es IMEI y/o OAID, cuando esté disponible, para habilitar el registro de la atribución.

**OAID:**

* Es un ID de publicidad reiniciable por el usuario, similar a GAID e IDFA.
* Requiere el SDK de Android de AppsFlyer V5.1.0 o posterior.
* A partir del SDK de AppsFlyer V5.4.0, el SDK intentará recopilar OAID automáticamente de forma predeterminada.
* Varios fabricantes han completado pruebas de interoperabilidad de atribución de OAID con AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">Incluye Huawei, Lenovo, OPRO, Vivo, Samsung y Xiaomi,</Anchor>

**IMEI**:

* El SDK de AppsFlyer impide el acceso al IMEI, salvo que se configure de otro modo. En general, se da por hecho que Google Play Services está activo en el dispositivo y que no se necesita el IMEI. En China, no ocurre así.
* Al integrar el SDK de AppsFlyer en tu app, debes habilitar el acceso al IMEI.
* Cuando sea necesario, OAID e IMEI deben implementarse simultáneamente para garantizar la atribución independientemente de la versión de Android.
* Esto se debe a que el acceso al IMEI está restringido a partir de <Anchor target="_blank" href="https://developer.android.com/training/articles/user-data-ids">Android 10 (nivel de API 29)</Anchor>, lanzado a finales de 2019. Ni tu app ni el SDK de AppsFlyer pueden recopilar estos identificadores. Cuando no hay ningún identificador disponible, AppsFlyer recurre a la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">atribución mediante modelado probabilístico.</Anchor>

**Antes de empezar**:

* Se requiere AppsFlyer Android SDK V5.1.0 o una versión posterior.

Usa uno de los siguientes procedimientos:

<div id="oaid-starting-from-android-api-level-29" />

<Accordion title="OAID a partir del nivel de API 29 de Android">

Hay dos métodos para recopilar el OAID:

* setCollectOaid
* setOaidData

<Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk#msa-sdk">Instrucciones para habilitar los métodos de la API</Anchor>

</Accordion>

<div id="imei-android-api-level-2328" />

<Accordion title="IMEI en el nivel de API 23-28 de Android">

Hay dos métodos para recopilar el IMEI:

* setImeiData
* setCollectIMEI(true)

Usa el siguiente ejemplo de código para integrar el SDK. Este ejemplo de código usa el método `onConversionDataSuccess`. Este es el nombre del método para obtener datos de conversión a partir de la versión 5.0 del SDK. Si estás utilizando una versión del SDK anterior a la V5.0, el nombre del método es `onInstallConversionDataLoaded`. Te recomendamos actualizar a la <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">versión actual del SDK.</Anchor>

**Nota:** Android API nivel 23 o posterior requiere el permiso del usuario, mediante un aviso, para acceder al IMEI. Esto puede dar como resultado que el IMEI se recupere después de la activación de la API StartTracking. A partir del nivel 29 de la API, el acceso al IMEI está restringido.

```java
Public class AFApplication extends Application {
   private static final String AF_DEV_KEY = "";
   private static AFApplication instance;
   @Override
   public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true); //El desarrollador recopila el IMEI y el ID de Android, y luego los envía al SDK de AppsFlyer.
	  AppsFlyerLib.getInstance().setImeiData("customer imei"); 
	  AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //O usa las dos API siguientes para que el SDK de AppsFlyer recopile el IMEI & android id
      //independientemente de si Google Play Services existe o no.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);
      //Configura el tiempo mínimo entre dos sesiones; la recomendación es 2 segundos.
      AppsFlyerLib.getInstance().setMinTimeBetweenSessions(2);
      final AppsFlyerConversionListener conversionDataListener = new 
AppsFlyerConversionListener() {
       @Override
       public void onConversionDataSuccess(Map<String, Object=""> map) {}
       @Override
       public void onConversionDataFail(String error) {}
       @Override
       public void onAppOpenAttribution(Map<string, string=""> map) {}
       @Override
       public void onAttributionFailure(String s) {}
     }
     AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
     AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
   }  
   @Override
     protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
  public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```

En el primer inicio de la aplicación, se envía al usuario una solicitud de permiso READ\_PHONE\_STATE en la devolución de llamada onResume() de MainActivity.

build.gradle en el módulo de la aplicación

```java
allprojects {
    repositories {
       ....
       maven { url 'https://jitpack.io'}
    }
}
dependencies {
    implementation 'com.github.tbruyelle:rxpermissions:0.10.2'
}
```

<Tabs>
<Tab title="MainActivity">

```java
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       startIMEILogic();
   }
   private void startIMEILogic() {
       SharedPreferences permissions_flags = getSharedPreferences("appsflyer-data", MODE_PRIVATE);
       if (!permissions_flags.contains(Manifest.permission.READ_PHONE_STATE)) {
           requestIMEIPermissions();
       }
   }
   private void requestIMEIPermissions() {
       if (ContextCompat.checkSelfPermission(this,
               Manifest.permission.READ_PHONE_STATE)
               != PackageManager.PERMISSION_GRANTED) {
           ActivityCompat.requestPermissions(this,
                   new String[]{Manifest.permission.READ_PHONE_STATE},
                   MY_PERMISSIONS_REQUEST_READ_PHONE_STATE);
       } else {
           //El permiso ya se había concedido
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, true);
           permissionsFlagsEditor.apply();
       }
   }
   @Override
   public void onRequestPermissionsResult(int requestCode,
                                          String[] permissions, int[] grantResults) {
       if (requestCode == MY_PERMISSIONS_REQUEST_READ_PHONE_STATE) {
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           boolean granted;
           // Si la solicitud se cancela, las matrices de resultado están vacías.
           if (grantResults.length > 0
                   && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
               // permission was granted!
               granted = true;
               AppsFlyerLib.getInstance().setCollectIMEI(true);
           } else {
               // permission denied!
               granted = false;
           }
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(0);
           AppsFlyerLib.getInstance().reportTrackSession(this);
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(5);
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, granted);
           permissionsFlagsEditor.apply();
       }
   }
}
```

</Tab>

<Tab title="MainActivity (heredado)">

```java
public class MainActivity extends AppCompactActivity {
    @Override
    protected void onResume() {
        super.onResume();
        final RxPermissions rxPermissions = new RxPermissions(this);
         if(RxPreference.Instance().getBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, false){
          return;
         }
         if(rxPermissions.isGranted(Manifest.permission.READ_PHONE_STATE)) {
            return;
         }
          RxPreference.Instance().putBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, true);
        rxPermissions.request(Manifest.permission.READ_PHONE_STATE)
                .subscribe(granted -> {
                    if (granted) {  
AppsFlyerLib.getInstance().setImeiData("customer imei");  
AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");  
//or  
AppsFlyerLib.getInstance().setCollectIMEI(true);  
AppsFlyerLib.getInstance().setCollectAndroidID(true);  
//NOTE: Here the report session API is reportTrackSession() not the startTracking()
                        AppsFlyerLib.getInstance().reportTrackSession(AFApplication.getAppInstance());
                    } else {
                    }
                });
    }
}
```

</Tab>
</Tabs>

</Accordion>

Hay dos métodos para recopilar el IMEI:

* setImeiData
* setCollectIMEI(true)

Usa el siguiente ejemplo de código para integrar el SDK. **Nota:** El ejemplo de código usa el método `onConversionDataSuccess` para obtener datos de conversión. Este es el nombre del método a partir del SDK V5. Si estás utilizando una versión del SDK inferior a 5.0.0, el nombre del método es `onInstallConversionDataLoaded`. Recomendamos que actualices al SDK 5.0.0. Para aprender más, haz clic <Anchor target="_blank" href="/marketers/es/docs/links-to-appsflyer-sdk-release-notes">aquí</Anchor>.

```java
 public class AFApplication extends Application {
    private static final String AF_DEV_KEY = "";
    private static AFApplication instance;
    @Override
    public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true);  
 //El desarrollador recopila el IMEI y el ID de Android, y luego los envía al SDK de AppsFlyer.  
 AppsFlyerLib.getInstance().setImeiData("imei del cliente");  
 AppsFlyerLib.getInstance().setAndroidIdData("android_id del cliente");\n      //O usa las dos API siguientes para que el SDK de AppsFlyer recopile el IMEI & android id, independientemente de si \n      //Google Play Service existe o no.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);  
      final AppsFlyerConversionListener conversionDataListener = new AppsFlyerConversionListener() {
          @Override
          public void onConversionDataSuccess(Map<String, Object=""> map) {} 
    	  @Override
          public void onConversionDataFail(String error) {}    
    	  @Override
          public void onAppOpenAttribution(Map<string, string=""> map) {}
          @Override
          public void onAttributionFailure(String s) {}
  	};
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
      AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
  }
    @Override
    protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
    public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```


</Accordion>

<div id="preparing-the-apk" />

<Accordion title="Preparación del APK">

Selecciona cómo se muestran los datos de atribución en AppsFlyer entre estas opciones:

* (mejores prácticas) **Aplicación única:** Los datos de todas las tiendas de aplicaciones de Android de terceros (mercado interno chino) se muestran en una sola aplicación, independiente y separada. Esto significa que ves los datos de atribución de todas las tiendas chinas nacionales en una sola aplicación en AppsFlyer. Para usar este método, ve a la sección [agregar la aplicación en AppsFlyer](/docs/measure-attribution-in-the-chinese-domestic-market#agregar-la-aplicación-en-appsflyer) que aparece a continuación.
* **Aplicación única consolidada con Google Play Store:** La atribución tanto de las tiendas de aplicaciones de terceros como de Google Play Store se muestra como una sola entidad. Esta opción requiere que el nombre del paquete de la tienda Google Play y de las tiendas de terceros sea idéntico. El uso de esta opción supone que la aplicación ya está definida en AppsFlyer. Para usar este método, continúa con [la preparación del APK/manifest](/docs/measure-attribution-in-the-chinese-domestic-market#preparación-del-apkmanifiesto) en la sección siguiente.
* **Varias aplicaciones** significa que los datos de atribución de cada tienda se muestran en una aplicación independiente. Por ejemplo, cada una de las siguientes se muestra por separado: Google Play Store, tienda de terceros A, tienda de terceros B, etc. Para usar este método, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">varias aplicaciones</Anchor>.

<div id="adding-the-app-in-appsflyer" />

### Agregar la aplicación en AppsFlyer

**Para agregar la aplicación en AppsFlyer**:

1. En AppsFlyer, haz clic en **My Apps**.
2. Haz clic en **Add App**.  
   Se abre la ventana Add Your App.
3. Selecciona **Android out of store APK**.
4. Configura los siguientes campos:  
   * **Nombre del paquete de Android**: texto libre
   * **Nombre del canal**: debe ser idéntico al nombre del canal en el manifest, como se explica en la sección siguiente. La mejor práctica es establecer este campo en **cn\_market**.
   * **App URL**

**Nota**: puedes crear la app con la opción **Pendiente de aprobación o sin publicar**, pero no se recomienda. Consulta con tu CSM antes de usar este método.

<div id="preparing-the-apkmanifest" />

### Preparación del APK/manifiesto

**Para preparar un APK/manifiesto separado para cada tienda de aplicaciones de terceros, haz lo siguiente:**

1. Añade lo siguiente al manifiesto para identificar el tráfico de China:

   ```java
   < meta-data android:name="CHANNEL" android:value="cn_market">
   ```

   **Nota:** Los parámetros distinguen entre mayúsculas y minúsculas. Te recomendamos que configures el canal como **cn\_market**.
2. Elige uno de los siguientes métodos para identificar la tienda:
   * **Método de manifiesto:** añade la siguiente línea al archivo AndroidManifest.xml. El valor de AF\_STORE debe ser único para cada tienda.

     ```xml
     <meta-data android:name="AF_STORE" android:value="example_store"/>
     ```

     **--O bien--**
   * **Método API:** prepara un APK independiente para cada tienda de aplicaciones de terceros. Llama a la API setOutOfStore para establecer el valor AF\_STORE. Configura un valor exclusivo para cada tienda.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("example_store")
     ```

Los métodos descritos establecen el parámetro AF\_STORE, que a su vez establece el campo install\_app\_store en los datos de atribución. Este campo está disponible en:

* análisis de cohortes
* <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Reportes de raw data</Anchor>

</Accordion>

<div id="additional-attribution-considerations" />

## Consideraciones adicionales sobre la atribución

<div id="workaround-for-stores-without-attribution-link-support" />

<Accordion title="Solución alternativa para tiendas sin soporte para enlaces de atribución">

Muchas tiendas de aplicaciones Android de terceros en China también venden tráfico, lo que significa que también son una plataforma de anuncios. En algunos casos, estas tiendas no admiten el uso de enlaces de atribución. Las siguientes soluciones alternativas se pueden usar como alternativa:

* install\_app\_store field: (recomendado) cuando la instalación se realiza sin un enlace de atribución, AppsFlyer atribuye la instalación a instalaciones orgánicas. Si usas el campo install\_app\_store, puedes identificar la fuente real de la instalación. Nota: el campo install\_app\_store se establece mediante el parámetro AF\_STORE descrito en la sección anterior.
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-factory-preinstall-using-manifest-android">Nombre de preinstalación</Anchor> en el archivo de manifiesto. Uso del nombre de preinstalación incluido en el manifiesto. La desventaja de este método es que, si el APK de preinstalación se filtra al mercado, la información de atribución será incorrecta. Al usar este método, asegúrate de contar con los términos comerciales adecuados para proteger tu APK.

</Accordion>

<div id="china-domestic-attribution-links" />

<Accordion title="Enlaces de atribución nacionales de China">

Al preparar enlaces de atribución, ten en cuenta lo siguiente:

**Enlaces basados en China**

Para las fuentes de medios que solo tienen tráfico nacional (chino), usa los enlaces de dominio que se detallan aquí. Estos enlaces se reconocen dentro de China y ofrecen una experiencia de usuario superior.

Para los enlaces de atribución normales, usa: https://app.aflink.com - (aflink.com)

Para los enlaces de atribución de OneLink, usa: https://go.onelnk.com (onelnk.com) Nota: Antes de usar el dominio onelnk.com, ponte en contacto con tu CSM de AppsFlyer.

Ten en cuenta que en weChat solo **onelnk.com** está en la lista de permitidos, mientras que **onelink.me** está bloqueado

**Usa af\_r**

Usa af\_r para asegurarte de que los usuarios se redirijan a una URL de descarga de APK o a una tienda de APK, y no a Google Play.

Nota: Con frecuencia, las fuentes de medios integradas nacionales de China tienen este parámetro configurado como &redirect=false en la plantilla de URL de atribución predeterminada. Esto significa que la redirección la realizarán las plataformas publicitarias y no AppsFlyer.

Para obtener más información sobre las fuentes de medios integradas:  
<Anchor target="_blank" href="/marketers/es/docs/android-app-promotion-in-china">Promoción de apps Android en China</Anchor>

</Accordion>

<div id="detecting-store-hijacking" />

<Accordion title="Detección de hijacking de tiendas">

En escenarios de tiendas de aplicaciones de terceros, los usuarios primero instalan la app desde la tienda de terceros de la fuente de medios (ad networks). En caso de secuestro de la instalación, una ventana emergente de advertencia sugiere al usuario que instale o actualice la app directamente desde la tienda de aplicaciones del fabricante del dispositivo (teléfono). Si el usuario acepta, se le redirige para descargar desde la tienda de aplicaciones del fabricante y se descarga el APK. Esto significa que el fabricante del dispositivo ha secuestrado la instalación.

El siguiente ejemplo ilustra tanto un flujo legítimo como un flujo secuestrado:

**Flujo legítimo**

Un usuario de la app hace clic en un anuncio mostrado por media-example y descarga la app de inmediato o bien se le redirige a legitimate-app-store para descargar la APP. En AppsFlyer se registra la siguiente información de atribución:

* **Fuente de medios**: media-example
* **Tienda de aplicaciones de instalación**: legitimate-app-store

**Flujo secuestrado**

Un usuario de la app hace clic en un anuncio mostrado por medio-ejemplo. Cuando se inicia la descarga, aparece una ventana emergente de advertencia que sugiere que el usuario descargue la app desde la tienda de aplicaciones del fabricante del dispositivo. Si el usuario acepta, se le redirige a la tienda del fabricante y descarga la aplicación. En AppsFlyer se registra la siguiente información de atribución:

* **Fuente de medios:** media-example
* **Install-app-store**: manufacturer-store

**Identificación del evento de secuestro en AppsFlyer**

Para identificar la instalación secuestrada, compara los campos fuente de medios e Install-app-store. Si no coinciden el valor esperado de Install-app-store y el valor real de Install-app-store, se indica un secuestro de la instalación.

</Accordion>

<div data-zendesk-anchors="attribution-android-apps-in-the-chinese-domestic-market=atribuci%C3%B3n-de-aplicaciones-android-en-el-mercado-nacional-chino preparing-the-app=preparar-la-aplicaci%C3%B3n adding-the-app-in-appsflyer=agregar-la-aplicaci%C3%B3n-en-appsflyer preparing-the-apkmanifest=preparaci%C3%B3n-del-apkmanifiesto additional-attribution-considerations=consideraciones-adicionales-sobre-la-atribuci%C3%B3n" />
