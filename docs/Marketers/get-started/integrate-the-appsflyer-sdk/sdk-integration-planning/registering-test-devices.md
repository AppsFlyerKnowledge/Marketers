---
title: Registro de dispositivos de prueba
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
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
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-08-30T00:14:36Z'
  id: 207031996
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/207031996
---
> **At a glance:** Cuando realices pruebas de atribución, registra tu dispositivo de prueba para asegurarte de que cada instalación se anote como nueva. Un dispositivo de prueba registrado impide que las instalaciones se atribuyan como reinstalaciones.

## ¿Por qué registrar un dispositivo de prueba?

Al realizar pruebas de atribución, la ventana de reatribución limita las atribuciones de instalación a una por cada 90 días. Por lo tanto, si usas el mismo dispositivo repetidamente para probar las atribuciones de instalación, no se registrará nada. Registrar un dispositivo como dispositivo de prueba evita que las instalaciones repetidas en el dispositivo registrado se consideren reinstalaciones.

## Métodos para registrar un dispositivo de prueba

Registrar un dispositivo de prueba implica seleccionar el sistema operativo del dispositivo (Android, iOS o Windows) y añadir el identificador del dispositivo.

Puedes utilizar uno de los siguientes métodos para registrarte:

* [Descarga e instala la aplicación My Device ID by AppsFlyer:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) Una vez que instales la app en el dispositivo de prueba, podrás registrar el dispositivo automáticamente y compartir los detalles del ID de dispositivo con tu cuenta de AppsFlyer. El dispositivo aparecerá automáticamente en la página de **Dispositivos de prueba**.

> 📘 **Note**
>
> * En dispositivos de prueba con iOS 14+, puedes usar este método de registro solo si se implementó AppTransparencyTracking (ATT) en tu aplicación y deseas realizar pruebas como usuario que da su consentimiento. Si este no es el caso, utiliza el método manual.
> * Si tu cuenta de AppsFlyer tiene activada la autenticación de dos factores (2FA), no puedes registrar dispositivos de prueba mediante la aplicación porque la aplicación no admite la autenticación 2FA. En este caso, usa el método manual para registrar dispositivos de prueba.

* [Agregar manualmente el dispositivo de prueba:](#register-a-device-manually) Cualquier usuario de la cuenta puede registrar directamente un dispositivo de prueba añadiendo el identificador del dispositivo a la página de **Dispositivos de prueba**.

Ten en cuenta lo siguiente:

* Los dispositivos de prueba registrados están disponibles para todas las aplicaciones que pertenecen a la cuenta.
* Las ad networks deben pedir al anunciante que añada dispositivos; las agencias pueden añadir sus propios dispositivos.

<Accordion title="Identificadores de dispositivos compatibles">

Los identificadores de dispositivos incluyen lo siguiente:

* **Android:** AID (GAID u OAID), IMEI, ID de Android

> 📘 **Note**
>
> Al registrar un dispositivo de prueba, debes agregar identificadores de dispositivo IMEI o Android ID solo si tu aplicación recopila y utiliza estos identificadores.

* **iOS:** IDFA, IDFV
* **Windows Phone:** ID de publicidad de Windows

</Accordion>

## Gestión del registro de dispositivos de prueba

<Accordion title="Registrar un dispositivo usando la aplicación de ID de dispositivo de AppsFlyer">

**Para descargar la aplicación de ID de dispositivo de AppsFlyer:**

1. Descarga e instala la aplicación utilizando el QR code (tienda Google Play) o uno de los enlaces proporcionados.

   <div id="android" />

   <Accordion title="Android">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   **Enlaces:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) y [Tienda out-of-market](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <div id="ios" />

   <Accordion title="iOS">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   </Accordion>

   <div id="windows" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="50.91%" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. En un dispositivo iOS 14.5+, si deseas permitir la recopilación de IDFA, selecciona **Permitir** cuando aparezca la solicitud de la ATT. [<Image alt="" src="https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png" width="50%" />](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. En la pantalla de Android/iOS/Windows, selecciona **Registrar** para registrar el dispositivo.

   <div id="android::db8cc168" />

   <Accordion title="Android">

   [<Image alt="" src="https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png" width="50%" />](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <div id="ios::80f176b3" />

   <Accordion title="iOS">

   [<Image alt="" src="https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png" width="50%" />](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <div id="windows::6c6af14b" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg" width="50%" />](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. Introduce tus credenciales de inicio de sesión de AppsFlyer. El dispositivo ya está registrado.
5. Toca **Compartir** detalles para compartir la información de ID del dispositivo.

</Accordion>

<Accordion title="Registrar un dispositivo manualmente">

Los usuarios de la cuenta pueden registrar un dispositivo manualmente:

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** -> **Dispositivos de prueba**.
2. Selecciona **Dispositivos de prueba**.
3. Haz clic en **+ Agregar dispositivo**.

   [<Image alt="" src="https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png" width="50%" />](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. Completa lo siguiente:
   * **Nombre (solo utiliza letras en inglés):** Introduce un nombre de identificación único para el dispositivo.
   * **Sistema operativo:** Selecciona un sistema operativo.
   * **Tipo de ID de dispositivo:** Selecciona un identificador de dispositivo.
   * **Identificador del dispositivo:** Proporciona el ID del dispositivo según el sistema operativo:

     <div id="ios::41efa11e" />

     <Accordion title="apps de iOS,">

     Cómo obtener los identificadores IDFA o IDFV:

     * **IDFA:** Para obtener el IDFA, instala la aplicación de ID de dispositivo AppsFlyer en tu dispositivo de prueba. Para saber cómo, consulta: [Agrega un dispositivo](#register-a-device-manually) usando la aplicación de ID de dispositivo de AppsFlyer (solo admin) más arriba.
     * **IDFV:** Para obtener el IDFV, pide a tu desarrollador que instale la herramienta de prueba de IDFV en tu dispositivo de prueba. Una vez instalada y ejecutada, la herramienta mostrará el IDFV. **Nota:** La herramienta de prueba se puede instalar solo después de que el desarrollador haya realizado los pasos preliminares en X-Code.

     Para saber cuándo usar IDFA o IDFV, consulta [Registro de un dispositivo de prueba iOS](#registro-de-un-dispositivo-de-prueba-ios).

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="Android">

     Obtén los identificadores utilizando la aplicación AppsFlyer Device ID o marcando los códigos en el dispositivo:

     | Identificador | Método de recuperación | Google Play | Otro |
     | --- | --- | --- | --- |
     | AID (GAID o OAID) | Usa la aplicación [AppsFlyer Device ID](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Obligatorio |  |
     | IMEI | *#06#* | No aplicable | Asegúrate de que el desarrollador haya utilizado <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor> para recopilar el ID. |
     | ID de Android | *#*#8255#*#* (puede que no funcione en dispositivos más recientes) | No aplicable | Asegúrate de que el desarrollador haya utilizado <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectAndroidID</Anchor> para recopilar el ID. |

     </Accordion>

5. Haz clic en **Guardar**. El dispositivo aparece en la lista de dispositivos registrados. **Nota**: Aunque el dispositivo aparece inmediatamente en la lista de dispositivos registrados, puede tardar unos minutos en registrarse en el sistema y funcionar como se espera.

> 📘 **Note**
>
> **Agregar más de un identificador**
>
> Puede haber ocasiones en las que quieras agregar más de un identificador a tu dispositivo de prueba; por ejemplo, querrás tanto IDFA como IDFV en el mismo dispositivo.
>
> **Para agregar un identificador adicional:**
>
> 1. Haz clic en **Agregar dispositivo**.
> 2. Usa el mismo nombre para el dispositivo de prueba y añade el segundo identificador.
> 3. Haz clic en **Guardar**.

</Accordion>

<Accordion title="Anular el registro de un dispositivo">

Se pueden registrar hasta un máximo de 200 dispositivos por cuenta.

**Para eliminar un dispositivo de la lista:**

1. En AppsFlyer, en la parte superior derecha, haz clic en tu dirección de correo electrónico.
2. Selecciona **Dispositivos de prueba**.
3. Haz clic en el icono de eliminar para quitar dispositivos.

</Accordion>

## Registro de un dispositivo de prueba iOS

El diagrama de flujo a continuación ilustra los posibles cursos de acción al registrar tus dispositivos de prueba iOS.

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

Selecciona entre las siguientes opciones al registrar tu dispositivo de prueba iOS:

<Accordion title="Registra tu dispositivo de prueba con IDFA">

#### **¿Cuándo utilizar IDFA para el registro del dispositivo de prueba?**

Puedes registrarte con IDFA si tu aplicación ha implementado AppTransparencyTracking (ATT) y quieres realizar pruebas como un usuario que da su consentimiento. Al iniciar la aplicación probada por primera vez, asegúrate de hacer clic en **Permitir** en el aviso de ATT.

#### **¿Cómo registrar tu dispositivo de prueba con un IDFA?**

Para registrarte con IDFA, utiliza la aplicación de ID del dispositivo AppsFlyer para registrar un dispositivo.

</Accordion>

<Accordion title="Registra tu dispositivo de prueba con IDFV">

#### **¿Cuándo usar IDFV para el registro de un dispositivo de prueba?**

Cuando IDFA no está disponible, IDFV es tu única opción. En los siguientes escenarios **debes usar IDFV:**

* **Se implementó ATT,** pero quieres realizar pruebas como un usuario sin consentimiento. Al iniciar la aplicación por primera vez, asegúrate de hacer clic en **No permitir** en el aviso de la ATT.
* **La ATT no fue implementada** en absoluto.

#### **Cómo registrar tu dispositivo con IDFV**

1. Antes de que puedas registrar el dispositivo de prueba con un IDFV, tu desarrollador debe instalar la aplicación de herramienta de prueba IDFV en tu dispositivo de prueba. Para instrucciones del desarrollador, puedes remitir a tu desarrollador a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">este artículo</Anchor>.
2. Después de que tu desarrollador instale la aplicación de herramienta de prueba IDFV, ábrela y copia el IDFV que se muestra.
3. [Registra el dispositivo de prueba manualmente](#register-a-device-manually) usando el IDFV.

> 📘 **Note**
>
> **¿Cuáles son las razones para instalar la aplicación de herramienta de prueba IDFV?**
>
> * La aplicación de herramienta de prueba IDFV se utiliza para obtener el IDFV que necesitas para registrar el dispositivo de prueba.
> * Cuando no tienes ninguna otra aplicación de tu cuenta de desarrollador instalada en tu dispositivo de prueba. En este caso, iOS asigna un nuevo ID de proveedor cada vez que reinstalas la app. Dado que muchas pruebas implican reinstalar la app, cada reinstalación provoca que iOS restablezca el IDFV. **La aplicación de utilidad, al hacerse pasar por el proveedor, evita que iOS cree un nuevo IDFV cada vez que se reinstala la app en el dispositivo de prueba.**

</Accordion>

<Accordion title="Prueba con un dispositivo no registrado">

Utiliza esta opción solo si no puedes registrar un dispositivo de prueba con IDFA o IDFV. En este caso se utiliza el modelado probabilístico para la atribución. Cada instalación se registra como una nueva instalación en el dispositivo de prueba. Este método puede ser útil para registrar instalaciones de prueba repetidas en el mismo dispositivo si se cumple al menos una de las siguientes condiciones:

* El SDK de iOS de AppsFlyer es la versión 6.8.0 o inferior.
* La detección de reinstalación está desactivada para la aplicación (no se recomienda para aplicaciones en producción).
* El enlace de atribución de prueba contiene `is_retargeting="true"`. En este caso, las instalaciones se consideran como reatribuciones y están disponibles en el dashboard y los reportes de raw data de retargeting.
* Solo para iOS: Para evitar que Protect360 marque los clics como fraudulentos, añada el parámetro de consulta `pid="ios_testing"` a tu enlace de atribución de prueba.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=por-qu%C3%A9-registrar-un-dispositivo-de-prueba 01H7W9EA7RQDB69QS339XFHAFZ=por-qu%C3%A9-registrar-un-dispositivo-de-prueba methods-for-registering-a-testing-device=m%C3%A9todos-para-registrar-un-dispositivo-de-prueba 01H7W9EA7RRRJBFSXW3KY53R9K=m%C3%A9todos-para-registrar-un-dispositivo-de-prueba managing-testingdevice-registration=gesti%C3%B3n-del-registro-de-dispositivos-de-prueba 01H7W9EA7R7SJVVQCST3WA6YBM=gesti%C3%B3n-del-registro-de-dispositivos-de-prueba 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKN5Z54T180C7G462C26Z4=ios 01JHJKN5Z51FABEGCFVTK0MPYR=windows 01JHJKTNRHHSZSC44WDWA9J2PD=android::db8cc168 01JHJKTNRJJBBA6WAC44PD33V7=ios::80f176b3 01JHJKTNRK9DY99SZ759ZGRP23=windows::6c6af14b 01JHJKDZK8084GMZ9QAZPHVBHQ=ios::41efa11e 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 registering-an-ios-testing-device=registro-de-un-dispositivo-de-prueba-ios h_01H6S2AKDH181MBDFGPBP1BQPV=registro-de-un-dispositivo-de-prueba-ios when-to-use-idfa-for-testing-device-registration=cu%C3%A1ndo-utilizar-idfa-para-el-registro-del-dispositivo-de-prueba 01H7W9EA7SRD5V5134H2BRZ2AF=cu%C3%A1ndo-utilizar-idfa-para-el-registro-del-dispositivo-de-prueba how-to-register-your-testing-device-with-an-idfa=c%C3%B3mo-registrar-tu-dispositivo-de-prueba-con-un-idfa 01H7W9EA7SBBCAP3Y24FFCCGJW=c%C3%B3mo-registrar-tu-dispositivo-de-prueba-con-un-idfa when-to-use-idfv-for-testing-device-registration=cu%C3%A1ndo-usar-idfv-para-el-registro-de-un-dispositivo-de-prueba 01H7W9EA7S3103TSHSH4XHTP1R=cu%C3%A1ndo-usar-idfv-para-el-registro-de-un-dispositivo-de-prueba how-to-register-your-device-with-idfv=c%C3%B3mo-registrar-tu-dispositivo-con-idfv 01H7W9EA7SGTDQCRVJKKRH0EVT=c%C3%B3mo-registrar-tu-dispositivo-con-idfv" />
