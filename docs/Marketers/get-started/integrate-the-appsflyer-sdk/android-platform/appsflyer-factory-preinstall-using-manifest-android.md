---
title: Preinstalación de fábrica de AppsFlyer mediante manifiesto (Android)
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
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
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2026-08-12T12:00:31Z'
  id: 207032166
  locale: es
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/es/articles/207032166
---
> **En resumen:** Atribuye las instalaciones de aplicaciones a los fabricantes de los dispositivos para las aplicaciones agregadas a los dispositivos antes de salir de fábrica. **Nota**: Consulta <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#preload-campaigns">todos los demás métodos de atribución de precarga</Anchor>.

![pre-install-intro-breakdown.png](https://files.readme.io/28b0a0dc5bde0b600011b16de97501fa358e4b710c532118ba6bc09c2c5dc1ce-49753458858385.png)

## Introducción

### ¿Qué es una campaña de preinstalación?

Las campañas de preinstalación permiten a los propietarios de aplicaciones llegar a una audiencia muy amplia sin necesidad de ejecutar campañas en línea.

En las campañas de preinstalación, los propietarios de aplicaciones pueden solicitar a los fabricantes de dispositivos que **preinstalen sus aplicaciones en los dispositivos antes de salir de fábrica**.

Las campañas de preinstalación también pueden ser una colaboración con fuentes de medios de terceros, que trabajan con diversos fabricantes en nombre de los propietarios de aplicaciones.

> 🚧 **¡Importante!**
>
> AppsFlyer cuenta una instalación una vez que una aplicación se inicia por primera vez. Por lo tanto, el número de preinstalaciones mostradas es el número de usuarios que inician tu aplicación, y no el número de dispositivos en los que está preinstalada.

### Ventajas de registrar las instalaciones de las campañas de preinstalación

La atribución de campañas de preinstalación permite medir el:

* número de usuarios que inician tu aplicación preinstalada
* número de usuarios de aplicaciones que aporta cada fabricante
* LTV de cada usuario y determinar qué fabricante aporta usuarios de alto valor

### ¿Cómo puedo medir las campañas de preinstalación?

Hay cuatro formas de medir las campañas de preinstalación. Para más información, consulta la [sección Configuración](/docs/appsflyer-factory-preinstall-using-manifest-android#configuración) de este artículo.

### Visualización de los datos de preinstalación

Las preinstalaciones aparecen en el panel de control de AppsFlyer bajo la fuente de medios atribuida, como cualquier otro evento de instalación. Sin embargo, el nombre de su campaña es siempre **Preinstalación**.

> 📘 **Nota**
>
> Puedes especificar diferentes nombres de campaña para las preinstalaciones con el [método API del SDK](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method).

> 📘 **Nota**
>
> A partir del 24 de mayo de 2022:
>
> * Match\_type para las campañas de preinstalación de fábrica se muestra como `preload_conf` en los reportes de raw data.
> * AppsFlyer muestra en los paneles de control la red de publicidad que impulsó la precarga y las redes de publicidad que contribuyeron al primer inicio de la aplicación. Más información sobre las <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#preload-campaigns">campañas de precarga</Anchor>.

## Configuración

Selecciona uno de los siguientes métodos para medir las campañas de preinstalación.

| Nombre del método | ¿Requiere múltiples APK? | ¿Garantiza la atribución de preinstalación? | ¿Requiere acción de la fuente de medios o el fabricante? |
| --- | --- | --- | --- |
| Propiedades del sistema | No | Sí | Sí |
| API de SDK | Sí | No | No |
| Nombre en el archivo de manifiesto | Sí | No | No |
| Ruta | No | No | Sí |

<div id="system-properties-method-recommended" />

<Accordion title="Método de propiedades del sistema (recomendado)">

Usa la versión del SDK `V4.0+`.

Se recomienda este método porque es el más sólido de todos; sin embargo, ten en cuenta que para todas las instalaciones posteriores de aplicaciones, siempre se atribuye a la fuente de medios de preinstalación. Esto es independiente de si la instalación es nueva o una reinstalación. 

El método de propiedades del sistema requiere acciones tanto por parte del desarrollador como del fabricante.

#### desarrollador

Debe proporcionar el APK al fabricante o a la fuente de medios. Se proporciona el APK por defecto. Este método no requiere un APK separado.

Crea un archivo llamado `pre_install.appsflyer`. En el archivo, agrega un par clave-valor:

`<package_name>=<media_source>`

Por ejemplo:

`com.appsflyer.sampleapp=huawei`

**Para especificar parámetros adicionales de preinstalación:**

En el archivo **pre\_install.appsflyer**, transmite los parámetros adicionales en formato JSON. Por ejemplo:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

> 🚧 **¡Importante!**
>
> Es importante tener en cuenta el siguiente comportamiento al utilizar esta opción:
>
> * En el raw data, ajusta el Canal en "Pre-install".
> * Si el parámetro `pid` no está presente en el JSON, la fuente de medios aparece como "None" en el raw data.
> * En la configuración JSON, si el parámetro `c` no está presente, el nombre de la campaña se establece como "Pre-install".
> * Si el JSON está mal formado, la cadena transmitida se trata como el nombre de la fuente de medios

Una vez que tengas el archivo pre\_install.appsflyer, entrégalo a la fuente de medios o al fabricante junto con el APK.

#### Fabricante

El fabricante coloca el archivo ***pre\_install.appsflyer*** en una ruta de archivo de su elección. Los permisos del archivo **pre\_install.appsflyer** deben establecerse en 744.

A continuación, el fabricante edita el archivo de propiedades del sistema para que apunte al archivo ***pre\_install.appsflyer***. Para ello, el fabricante debe agregar un par clave-valor a las propiedades del sistema.

> 📘 **Nota**
>
> Para este paso se necesitan permisos root. También se necesitan permisos root para probar la configuración de preinstalación. Consulta la [sección Pruebas](/docs/appsflyer-factory-preinstall-using-manifest-android#probar-la-configuración-de-preinstalación) para obtener más información.

**Agregar un par clave-valor a las propiedades del sistema Android:**

```bash
adb shell su\nsetprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

Un método alternativo es recuperar el archivo system-properties del sistema de archivos android, editarlo y hacer push de vuelta:

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 644 /system/build.prop
adb reboot
```

#### Ventajas

No hay necesidad de mantener diferentes APK para cada fuente de medios o fabricante. No es necesario hacer cambios y agregar rutas a la aplicación en Google Play. Los fabricantes pueden utilizar rutas personalizadas y no hay dependencias entre varias aplicaciones preinstaladas que se ejecuten en distintos dispositivos.

Este método garantiza la atribución a campañas de preinstalación y fuentes de medios. Incluso si un usuario actualiza la aplicación antes de iniciarla o la instala después de hacer clic en un anuncio, la preinstalación se sigue atribuyendo a la fuente de medios de preinstalación o al fabricante.

#### Desventajas

Parte de la responsabilidad se transfiere a la fuente de medios o al fabricante. Los desarrolladores tienen que asegurarse de que el fabricante o la fuente de medios adopta las medidas necesarias. Además, este método puede ser un poco más difícil de probar para el desarrollador de la aplicación.

</Accordion>

<div id="sdk-api-method" />

<Accordion title="Método de API de SDK">

El método de la API de SDK proporciona una forma nativa de especificar el nombre del fabricante o de la fuente de medios a la que se atribuye la preinstalación.

Para utilizar este método, agrega la siguiente llamada al método en la clase AFApplication antes de inicializar el SDK:

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

#### Al trabajar con una fuente de medios

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");\nAppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

#### Al trabajar con un fabricante

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");\nAppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

> 📘 **Nota**
>
> * El parámetro de fuente de medios es obligatorio.
> * La propiedad `android.os.Build.MANUFACTURER` contiene el nombre del fabricante configurado por el sistema operativo. El uso de esta propiedad no garantiza que se obtenga el nombre del fabricante en el mismo formato en todos los dispositivos de ese fabricante. Asegúrate de que esta propiedad contiene el nombre del fabricante tal y como se espera.
> * Los parámetros `campaign` y `siteId` son opcionales, pero son necesarios para el método `setPreinstallAttribution`. Si no deseas especificar `campaign` y `siteId`, indica null en ambos.

#### Ventajas

El método de la API del SDK te permite recuperar el nombre del fabricante mediante programación. Independientemente del fabricante, el método del SDK recupera el nombre directamente del dispositivo. Esto significa que puedes mantener un APK para todos los fabricantes con los que colabores.

El método `setPreinstallAttribution` permite especificar el nombre de la campaña. Puedes separar cada fabricante o fuente de medios en diferentes campañas, en lugar de tenerlos todos bajo la campaña "Pre-install".

#### Desventajas

Si trabajas directamente con fabricantes, tienes que mantener dos versiones de tu APK, una para los fabricantes y otra para Google Play. En cualquier caso, se necesita más de un APK.

Si trabajas con varias fuentes de medios que se comunican con el fabricante en tu nombre, debes mantener un APK independiente para cada fuente de medios.

En algunos casos, es posible que la instalación no se atribuya a la fuente de medios de preinstalación:

* Si un usuario con un dispositivo nuevo actualiza la aplicación preinstalada directamente desde Google Play sin iniciarla antes, la instalación se considera orgánica.
* Si un usuario con un dispositivo nuevo actualiza la aplicación desde Google Play tras hacer clic en un anuncio, la instalación se atribuye a la fuente de medios que sirve el anuncio.

> 👍 **Consejo**
>
> Puedes implementar la lógica en la aplicación para asegurarte de que la instalación se cuenta como preinstalación, incluso si se producen los escenarios anteriores. Tanto el APK de Play Store como el APK destinado a la preinstalación deberían contener esa lógica.
>
> **Ejemplo:**
>
> * Ya sabes que las aplicaciones vienen preinstaladas en los dispositivos de un determinado fabricante y modelo. Estos dispositivos también funcionan con un operador determinado.
> * Cuando se inicie la aplicación, puedes comprobar si se dan estas condiciones. Si se cumplen estas condiciones, la instalación se registra como preinstalación. Dado que la lógica también existe en el APK de Play Store, la instalación se registra como Preinstalación aunque el usuario actualice la aplicación antes de iniciarla.

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="Método de nombre en el archivo de manifiesto">

El nombre en el método de manifiesto requiere que agregues una etiqueta de metadatos al archivo de manifiesto de la aplicación. Debes repetir este paso para cada fuente de medios o fabricante con el que colabores.

Agrega una etiqueta de metadatos antes de la etiqueta de cierre de la aplicación:

```html Markup
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>\n  </application>\n</manifest>
```

Cuando la aplicación se inicia por primera vez, el SDK de AppsFlyer detecta esta etiqueta de metadatos en el archivo de manifiesto y atribuye la instalación en consecuencia.

#### Ventajas

El método del nombre en el manifiesto se considera un método sencillo para atribuir campañas de preinstalación. Sólo hay que agregar una etiqueta al manifiesto. Además, la fuente de medios o el fabricante no tienen que hacer nada por su parte para permitir la medición de campañas.

#### Desventajas

Dado que la etiqueta de metadatos especifica la fuente de medios o el nombre del fabricante, es necesario mantener diferentes conjuntos de APK, uno para cada fuente de medios o fabricante.

En algunos casos, es posible que la instalación no se atribuya a la fuente de medios de preinstalación:

* Si un usuario con un dispositivo nuevo actualiza la aplicación preinstalada directamente desde Google Play sin iniciarla antes, la instalación se considera orgánica.
* Un usuario con un dispositivo nuevo instala la aplicación desde Google Play tras hacer clic en un anuncio, la instalación se atribuye a la fuente de medios que sirve el anuncio.

</Accordion>

<div id="pathway-method" />

<Accordion title="Método de ruta">

> 📘 **Nota**
>
> Compatible con SDK versión 4.5.0 o posterior.

Este método requiere que tanto el desarrollador como el fabricante realicen algunas acciones por su parte.

#### desarrollador

El método de ruta te permite especificar una ruta a un archivo que contiene el nombre de la fuente de medios o del fabricante. Debes seguir tres pasos:

1. Crear un archivo que contenga un par clave-valor. El archivo debe llamarse ***pre\_install.appsflyer***. En el archivo, especifica el par clave-valor con el formato `<NOMBRE_DE_PAQUETE>`=`<FUENTE_DE_MEDIOS>`. Por ejemplo, `com.appsflyer.sampleapp=my_media_source`.  

   #### Transmitir parámetros adicionales de preinstalación

   Puedes especificar parámetros adicionales de preinstalación en el archivo utilizando JSON. Por ejemplo, puedes agregar el siguiente par clave-valor en el archivo **pre\_install.appsflyer**:

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   > 🚧 **¡Importante!**
   >
   > Es importante tener en cuenta los siguientes comportamientos al utilizar esta opción:
   >
   > 1. Establece "Pre-install" como af\_channel.
   > 2. Si el pid no está presente en el JSON, la fuente de medios aparece como "None".
   > 3. En la configuración JSON, si c no está presente, el nombre de la campaña se establece en "Pre-install".
   > 4. Si el JSON está mal formado, la cadena transmitida se trata como el nombre de la fuente de medios


   Una vez que tengas el archivo pre\_install.appsflyer, entrégalo a la fuente de medios o al fabricante junto con el APK.
2. Habla con la fuente de medios o el fabricante y acuerda con ellos la ruta donde colocar el archivo. La ruta recomendada es "/data/local/tmp/pre\_install.appsflyer".
3. Una vez acordada la ruta, especifícala en el archivo de manifiesto. Coloca el siguiente fragmento antes de la etiqueta de cierre de la aplicación:  

   ```html Markup
   <meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
   ```

#### Fabricante

El fabricante debe colocar el archivo en la ruta acordada. Los permisos del archivo pre\_install.appsflyer deben establecerse en 744.

Una vez que la aplicación se inicia, el SDK mira dentro del archivo de manifiesto, ve la ruta especificada y busca el archivo allí. Cuando la encuentra, atribuye la instalación según la fuente de medios que se especifique en ella.

#### Ventajas

AppsFlyer busca el archivo **pre\_install.appsflyer** en dos rutas por defecto:

```bash
/data/local/tmp/pre_install.appsflyer\nOR \n/etc/pre_install.appsflyer
```

Algunos fabricantes prefieren colocar el archivo en una ruta no predeterminada. En tal caso, puedes especificar esta ruta no predeterminada en el archivo de manifiesto.

> 🚧 **¡Importante!**
>
> La ruta no predeterminada requiere SDK versión 4.8 o posterior
>
> Aunque se permiten rutas no predeterminadas, recomendamos implementar el [método Propiedades del sistema](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended) en su lugar.

#### Desventajas

Es necesario mantener por separado ***pre\_install.appsflyer*** para diferentes fuentes de medios o fabricantes.

Es posible que el fabricante quiera poner el archivo ***pre\_install.appsflyer*** en una ruta no predeterminada. En este caso, deberás mantener APKS independientes para cada ruta no predeterminada.

Si se utiliza una **ruta no predeterminada**, es posible que la instalación no se atribuya a la fuente de medios de preinstalación:

* Si un usuario con un dispositivo nuevo actualiza la aplicación preinstalada directamente desde Google Play sin iniciarla antes, la instalación se considera orgánica.
* Un usuario con un dispositivo nuevo instala la aplicación desde Google Play tras hacer clic en un anuncio, la instalación se atribuye a la fuente de medios que sirve el anuncio.

</Accordion>

## Probar la configuración de preinstalación

Esta sección muestra cómo probar y verificar la configuración de preinstalación.

> 🚧 **¡Importante!**
>
> Antes de empezar las pruebas, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">poner en la lista de permitidos los dispositivos</Anchor> que vas a utilizar para las pruebas.
> Además, asegúrate de establecer el registro de depuración en true en la clase AFApplication.
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="Verificación de la configuración en la aplicación">

> 👍 **Consejo**
>
> Para evitar problemas de caché y obtener mejores resultados, se recomienda limpiar el proyecto antes de compilarlo. En Android Studio, haz clic en ***Build*** (Compilar) en el menú contextual y selecciona ***Clean Project*** (Limpiar proyecto).

Crea tu aplicación en Android Studio e instálala en el dispositivo de prueba. Una vez iniciada la aplicación, abre el Logcat en Android Studio y filtra por "AppsFlyer". Deberías ver la instalación atribuida con todos los detalles. Véanse las capturas de pantalla siguientes a modo de ilustración:

![pre_install_logcat.png](https://files.readme.io/ad4055ead94d755f9db9d72ed458a305660548b871ca53f63297f81c11b56bad-49753458859281.png)

![pre_install_logcat_2.png](https://files.readme.io/92fc8a4e500975cb353c87b1533e15257abe8422bf07a035b4c3056e51d220e6-49753442960145.png)

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="Verificación de la configuración en el panel de control de AppsFlyer">

Si la configuración se realiza correctamente, aparece en el panel de control una instalación no orgánica atribuida a un fabricante o a una fuente de medios. El evento de instalación también aparece en la campaña "Pre-install".

Accede a tu cuenta de AppsFlyer y abre el panel de control de la aplicación que estás probando. Sigue los pasos que se indican a continuación:

1. En la página de resumen, filtra por fuentes de medios y elige la fuente de medios:  

   ![choose_media_source.png](https://files.readme.io/7aa7e0e4a5d1c4b8428ec4fe934f673ec8304da97ae9d2cc41c2b6f4eac3147b-49753458860689.png)
2. En el ***Desglose por campaña*** puedes ver que la instalación atribuida a "my media source" procede de una campaña de preinstalación:  

    [![](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)  
   También puedes verificar que la instalación se atribuye correctamente consultando el ***Reporte agregado de desempeño***. En él, puedes ver la fuente de medios y la campaña. Véase la siguiente captura de pantalla donde "My Media Source" es la fuente de medios y la campaña es Pre-install:  

    [![](https://files.readme.io/9238b9b19220a40bef2b33dc21277da27e58792af2e6a123fadb640e77e0bf57-49753442961809.png)](https://files.readme.io/9238b9b19220a40bef2b33dc21277da27e58792af2e6a123fadb640e77e0bf57-49753442961809.png)
3. Repite el proceso para todos los fabricantes o fuentes de medios con los que colabores para las campañas de preinstalación.

</Accordion>

## Casos especiales

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="Múltiples aplicaciones preinstaladas en el mismo dispositivo">

Si tienes campañas para varias aplicaciones instaladas en el mismo dispositivo, puedes medir la atribución utilizando cada uno de los cuatro métodos:

* Método de nombre en el manifiesto: para cada aplicación, especifica la fuente de medios o el fabricante en el archivo Manifest.xml de cada aplicación.
* Método de API de SDK: para cada aplicación, especifica la fuente de medios o el fabricante en el método de API de SDK para la preinstalación.
* Para los métodos de propiedades del sistema o de ruta, puedes especificar las aplicaciones y su correspondiente fuente de medios en el archivo ***pre\_install.appsflyer***. Cada información de la aplicación debe agregarse en una nueva línea del archivo. Por ejemplo:

  ```bash
  com.appsflyer.tester=market_name\ncom.newapp.newapp=market_name\ncom.game.king=market_name
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="Envío de postbacks de instalación">

Si la fuente de medios o el fabricante con el que colaboras es un <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#your-integrated-partners">partner de AppsFlyer</Anchor>, puedes habilitar los postbacks para las instalaciones.

Para ello, asegúrate de que el nombre de la fuente de medios es equivalente al pid de la fuente de medios tal y como está configurado por AppsFlyer.

Por ejemplo, si estás colaborando con nombre\_mercado, su pid es nombre\_mercado\_int. Puedes ver el pid examinando el <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#atribución-por-clic">enlace de atribución de un partner integrado</Anchor>.

</Accordion>

<div id="agencies" />

<Accordion title="Agencias">

Actualmente, las agencias no pueden atribuirse preinstalaciones.

Si el af\_prt (parámetro para el nombre de la agencia) forma parte de los datos de preinstalación y el usuario inicia la aplicación preinstalada:

* El usuario se atribuye a la fuente de medios utilizada por la agencia (pid=).
* El cliente puede acceder a todos los datos a nivel de usuario.
* El usuario NO se atribuye a la agencia.
* La agencia no puede acceder a los datos a nivel de usuario.

</Accordion>

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01J421581P06FTM7B3XG2GYB2P=introducci%C3%B3n what-is-a-preinstall-campaign=qu%C3%A9-es-una-campa%C3%B1a-de-preinstalaci%C3%B3n h_01J421581P6GYK60D5JQ9PK93N=qu%C3%A9-es-una-campa%C3%B1a-de-preinstalaci%C3%B3n h_01J421581PBQQ5AS3S4JPX52CF=importante benefits-of-recording-installs-from-preinstall-campaigns=ventajas-de-registrar-las-instalaciones-de-las-campa%C3%B1as-de-preinstalaci%C3%B3n h_01J421581P5MS4X9BHSJ3TTWBF=ventajas-de-registrar-las-instalaciones-de-las-campa%C3%B1as-de-preinstalaci%C3%B3n how-can-i-measure-preinstall-campaigns=c%C3%B3mo-puedo-medir-las-campa%C3%B1as-de-preinstalaci%C3%B3n h_01J421581PEZZW2R244ZX9HX0R=c%C3%B3mo-puedo-medir-las-campa%C3%B1as-de-preinstalaci%C3%B3n viewing-preinstall-data=visualizaci%C3%B3n-de-los-datos-de-preinstalaci%C3%B3n h_01J421581PS1CEPK3NN7AZ0ZDE=visualizaci%C3%B3n-de-los-datos-de-preinstalaci%C3%B3n h_01J421581PDE1CEXRS6BYTDV35=nota h_01J421581PKQTX47GC62K4AB9A=nota-1 setup=configuraci%C3%B3n h_01J421581P28NEVB44R3XTPY75=configuraci%C3%B3n h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended developer=desarrollador h_01J421581Q8ZAPZS12PEG4VW3N=desarrollador h_01J421581QYRNXCP16GY8CJTKT=importante-1 manufacturer=fabricante h_01J421581QF6Y6MY28N5MR5BTM=fabricante h_01J421581QBFMVT3KPCPPFRX42=nota-2 advantages=ventajas h_01J421581QEPAC0WZK93HH3QYP=ventajas disadvantages=desventajas h_01J421581QCG3HARVZVECMHQ1K=desventajas h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method when-working-with-a-media-source=al-trabajar-con-una-fuente-de-medios h_01J421581Q6F1AD0SYXEEJB8FB=al-trabajar-con-una-fuente-de-medios when-working-with-a-manufacturer=al-trabajar-con-un-fabricante h_01J421581Q3YSNH7KXQXET7FD4=al-trabajar-con-un-fabricante h_01J421581QRYRWY2WJKCBHQBFG=nota-3 advantages::d999b734=ventajas-1 h_01J421581QWHP73CA7P13WAQ7Q=ventajas-1 disadvantages::92772f7d=desventajas-1 h_01J421581QRRFBJWZB5Z6M08BE=desventajas-1 h_01J421581QF11R7ZXAXRP2YQYR=consejo h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=ventajas-2 h_01J421581Q8WFYYFQJ45KPWZWP=ventajas-2 disadvantages::919cb3e3=desventajas-2 h_01J421581QYC02EKB5P0FN5G3F=desventajas-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=nota-4 developer::7c51f631=desarrollador-1 h_01J421581QB4TH9DMA2ANHG7RD=desarrollador-1 passing-additional-preinstall-parameters=transmitir-par%C3%A1metros-adicionales-de-preinstalaci%C3%B3n h_01J421581Q45AEN4GEM5ZKPYRN=transmitir-par%C3%A1metros-adicionales-de-preinstalaci%C3%B3n h_01J421581Q3MMTKPP3E8SZD13F=importante-2 manufacturer::56d9649d=fabricante-1 h_01J421581Q16AVHRCTHME67VHQ=fabricante-1 advantages::1fb76031=ventajas-3 h_01J421581QTRY13FVNQRMG0H2B=ventajas-3 h_01J421581Q0P5VQJHQ9X3VRW8N=importante-3 disadvantages::c9cae863=desventajas-3 h_01J421581QSNNCHPC2VSF48FT3=desventajas-3 testing-preinstall-configuration=probar-la-configuraci%C3%B3n-de-preinstalaci%C3%B3n h_01J421581QYHRHF119J4YBZD23=probar-la-configuraci%C3%B3n-de-preinstalaci%C3%B3n h_01J421581QW0XKZ635A194W80J=importante-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=consejo-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard special-cases=casos-especiales h_01J421581Q624TH08PX24B1P3X=casos-especiales h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />
