---
title: Configuración de la atribución de múltiples tiendas de Android
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
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
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-08-12T11:57:51Z'
  id: 207447023
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/207447023
---
> **De un vistazo:** Atribuye tus aplicaciones en varias tiendas de Android y visualiza los datos en un solo panel de control de aplicaciones o en un panel de control de aplicaciones por tienda.

## Atribución de múltiples tiendas de Android

AppsFlyer atribuye las aplicaciones independientemente de la tienda de aplicaciones. Es decir, la tienda de Google Play y las tiendas de terceros de Android como Amazon, Opera, GetJar, Baidu y Huawei. (También conocidas como tiendas fuera del mercado o tiendas de aplicaciones alternativas de Android). Los propietarios de aplicaciones que comercializan la aplicación a través de múltiples tiendas pueden elegir entre un **único** **panel de control** con los datos de todas las tiendas juntas o un **panel de control por tienda.**

> 📘 **Nota: Los parámetros distinguen entre mayúsculas y minúsculas.**
>
> * La atribución de Android de AppsFlyer es compatible con todos los tipos de identificadores de dispositivos, incluidos el ID de publicidad de Google (GAID) y el <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>.
> * Para las aplicaciones comercializadas en China, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-attribution-in-the-chinese-domestic-market">Atribución de aplicaciones Android en el mercado nacional chino</Anchor>.

![DashboardType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

### Un solo panel de control vs. un panel de control por tienda

* **Panel de control único:** un panel de control que combina los datos de todas las tiendas, incluida Google Play Store.
* **Panel de control por tienda:** varios paneles de control; cada tienda tiene el suyo propio. Eso significa que tienes tantos paneles de control como tiendas que proporcionen la aplicación.

<table><thead><tr><th> </th><th>Panel de control único<br/> [Práctica recomendada]</th><th> Panel de control por tienda</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Nombre del paquete de Android</td><td colspan="2">Usa el mismo nombre de paquete (idéntico) independientemente de la opción seleccionada. </td></tr><tr><td><span id="channel-name"></span>Nombre del canal</td><td>No hay que configurar nada</td><td><ul><li><span>Al agregar la aplicación en el panel de control de AppsFlyer mediante la opción de <strong>APK fuera de la tienda de Android</strong>, debes configurar el canal.</span></li><li><span>El canal identifica la tienda.</span></li><li>La combinación del nombre del paquete de Android y el canal identifica de manera exclusiva cada panel de control de AppsFlyer.</li><li>Ejemplo: El nombre del paquete de Android es com.abc.def y el canal es xyz_device_store. El identificador exclusivo del panel de control es com.abc.def-xyz_device_store.</li><li>Si el APK tiene una configuración de canal pero no hay ninguna aplicación con esta configuración, el tráfico se atribuye a la aplicación predeterminada, siendo esta la aplicación con una configuración de canal en blanco en Google Play Store. </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Rellenar el campo install_app_store</td><td><ul><li>Identifica de manera exclusiva la tienda que proporciona la aplicación por cada descarga.</li><li>En el caso de Google Play Store, esto está en blanco.</li><li>El nombre de la tienda se establece en el <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifiesto/APK.</a> </li></ul></td><td>N/D</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#crear-una-plantilla-de-onelink" target="_blank">Plantilla de OneLink</a></td><td>Cuando se trabaja con OneLink, se recomienda este método. </td><td>N/D </td></tr><tr><td><span id="measurementattribution-links"></span>Enlaces de medición/atribución </td><td><ul><li>Los enlaces son los mismos independientemente de la tienda.</li><li>Para redirigir a la tienda correcta, usa <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> para establecer la URL de redirección.</li></ul></td><td><ul><li>Se requiere un enlace exclusivo para cada tienda.</li><li>Créalos desde la página <strong>Integraciones activas</strong>.</li><li>El ID de aplicación es el nombre del canal agregado al nombre del paquete de Android. P. ej.: com.abc.def-def_store.<br/>Por lo tanto, los enlaces de atribución serán diferentes.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Opciones de reportes disponibles con el campo install_app_store</td><td>Los reportes de información general, cohortes y raw data incluyen el campo. Ponte en contacto con tu CSM pidiéndole que agregue la marca de función SFDC necesaria. </td><td>N/D </td></tr><tr><td><span id="considerations"></span>consideraciones</td><td><ul><li>Precisión de la atribución: las reinstalaciones desde diferentes tiendas no resultan en números de instalación inflados.</li><li><span>Las instalaciones orgánicas reflejarán las instalaciones orgánicas del APK de todas las tiendas bajo un solo panel de control.</span></li><li><span>Las opciones de reportes, desglosadas por tienda, se limitan actualmente a información general, cohortes y raw data.</span></li></ul></td><td><ul><li>Precisión de la atribución: se cuentan las reinstalaciones, lo que resulta en una atribución menos precisa.</li><li><span><span>Las instalaciones </span><span>orgánicas</span><span> y </span><span>no orgánicas</span><span> y los datos de eventos in-app se visualizan por tienda (canal) en paneles de control de aplicaciones separados en AppsFlyer.</span></span></li><li><span>Usa la Cohorte para mostrar reportes combinados de todas las tiendas juntas.</span></li><li><p>Asegúrate de que los partners con los que estás trabajando estén <strong>activos</strong> (<a href="./partner-activation-deactivation" target="_blank">Activar partner</a> está activado) en <strong>todos</strong> los paneles de control. Esto es <span>para evitar discrepancias (más comunes al comparar datos con SRN</span>).<br/> </p></li></ul></td></tr></tbody></table>

## Configuración de tareas

En el flujo de trabajo que sigue se enumeran las actividades necesarias para configurar la opción deseada. Las tareas se dividen entre el marketer y el desarrollador.

Para la opción de Panel de control por tienda, repite las tareas para cada tienda.

### **Antes de comenzar:**

* Decide la convención de nombres para los parámetros canal y install\_app\_store.
* Usa la tabla de convención de nombres a continuación para asignar los canales y las tiendas.
* El desarrollador utiliza la tabla para preparar los APK.

<table><thead><tr><th>Parámetro</th><th>Instrucción</th><th>Panel de control único<br/> [Práctica recomendada]</th><th>Panel de control por tienda</th></tr></thead><tbody><tr><td>Nombre del paquete de Android</td><td>Nombre de paquete idéntico para todas las opciones del panel de control.</td><td colspan="2">Si la aplicación ya está en Google Play Store, usa el nombre del paquete existente. Ejemplo: comb.abc.def.</td></tr><tr><td>Nombre del canal</td><td>Un valor exclusivo para cada tienda.</td><td>No se configura. Déjalo en blanco. </td><td><p>Exclusivo para cada tienda. Configura el valor en el APK individual preparado para la tienda y al agregar la aplicación en AppsFlyer. </p><p>No configures un canal para el APK de Google Play Store. </p></td></tr><tr><td>Instalar tienda de aplicaciones AF_STORE</td><td>Un valor exclusivo que identifica la tienda</td><td><span>Exclusivo para cada tienda. Configúralo en el APK a través del manifiesto. Cada tienda tiene su propio APK. </span></td><td> No se configura.</td></tr></tbody></table>

### Tareas

| Paso | Responsabilidad | Panel de control único | Panel de control por tienda |
| --- | --- | --- | --- |
| 1 | desarrollador | [Preparación del APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [Preparación del APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Comercializador | No se requiere ninguna acción. Se supone que la aplicación ya está activa en AppsFlyer. | [Agrega la aplicación](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) en AppsFlyer. |
| 3 | Comercializador | [Prepara los enlaces de atribución.](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Prepara los enlaces de atribución con el ID de aplicación combinado con el nombre del canal. |
| 4 | Desarrollador y marketer | [Pruebas](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Pruebas](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

## Procedimientos

<div id="single-dashboard-apk-preparation" />

<Accordion title="Panel de control único: preparación del APK">

El nombre del paquete de Android determina qué panel de control contendrá los datos de atribución. En el método de panel de control único, todas las tiendas tienen nombres de paquetes de Android idénticos. No hay ningún concepto de un parámetro de canal aquí.

La identificación de la tienda de descarga se realiza mediante el conjunto de parámetros AF\_STORE del SDK, como se describe en esta sección.  El parámetro AF\_STORE no distingue entre mayúsculas y minúsculas. Por ejemplo, ABC, abc, Abc.

**Para preparar el APK:**

1. Crea una copia de la compilación de la aplicación. **Nota**: No cambies el nombre del paquete de Android.
2. Para identificar la tienda individual, usa uno de los siguientes métodos:
   * **Método de manifiesto:** agrega lo siguiente dentro de la etiqueta `<application>` del AndroidManifest.xml para identificar la tienda. Configura el parámetro AF\_STORE con el nombre de la tienda de aplicaciones.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="enter_store_name_here"/>
        ...
     </application>Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
     ```

     **--O bien--**
   * **Método API:** Prepara un APK distinto para cada tienda de aplicaciones alternativa. Llama a la API setOutOfStore para establecer el valor AF\_STORE. Configura un valor exclusivo para cada tienda.

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("enter_store_name_here")
     ```

El valor establecido aquí aparece en el campo install\_app\_store del raw data de AppsFlyer. Este campo está disponible en:

* Panel de vista general
* Panel de control de la cohorte
* <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Reportes de raw data</Anchor> (los reportes de raw data son una característica premium de AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Panel de control único: enlaces de atribución">

Tanto si creas tu enlace de atribución <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">para que lo use una red publicitaria</Anchor> como <Anchor target="_blank" href="/marketers/es/docs/onelink-onboarding-guide#sobre-onelink">para tus medios propios</Anchor>, sigue estos pasos para asegurarte de que todos los engagement de tus enlaces de atribución aparezcan en un único dashboard.

1. En la pestaña **Enlace de atribución**, establece el parámetro de **URL de fuera de la tienda**. Esto completa la macro `af_r` en el enlace de atribución para redirigir a los usuarios a la página de aterrizaje correcta de la tienda de aplicaciones. Por ejemplo, `&af_r=https://www.destinationurl.com`

   > 📘 **Nota**
   >
   > Por ejemplo, `&af_r=http://www.destinationurl.com` La URL predeterminada se establece en la página <Anchor target="_blank" href="/marketers/es/docs/app-settings">Configuración de la aplicación</Anchor>. Si esto ya está configurado, no hace falta actualizar el enlace de atribución, porque los enlaces de atribución creados para la aplicación se rellenarán automáticamente con esta URL. <Anchor target="_blank" href="/marketers/es/docs/app-settings#outofstore-app-url">Más información</Anchor>

2. Añade la redirección `af_r` a la <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de permitidos de redirección</Anchor>.
3. Rellena la macro af\_r con la URL de la página de aterrizaje de la tienda.
4. Establece <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#parámetros-del-enlace-de-atribución">parámetros del enlace de atribución</Anchor> adicionales.
5. Las fuentes de medios fuera de la tienda **utilizan la coincidencia de ID para la atribución** y el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">modelo probabilístico</Anchor> de AppsFlyer sirve como un método alternativo.
6. Agrega uno o más marcadores de ID de usuario a la URL del enlace:
   * `android_id`
   * `advertising_id`
   * `oaid`
7. Copia el enlace de atribución y dáselo al partner de la red de publicidad.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Panel de control por tienda: preparación del APK">

El nombre del paquete Android combinado con el parámetro del canal establecido en el manifiesto determina qué panel de control de la tienda contendrá los datos de atribución.

**Para preparar un APK/manifiesto separado para cada tienda:**

* Agrega lo siguiente dentro de la etiqueta `<application>` del AndroidManifest.xml para identificar la tienda. Configura el parámetro CHANNEL con el nombre de la tienda de aplicaciones.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="enter_store_name_here"/>
       ...
  </application>Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
  ```

  **Nota:** Los parámetros distinguen entre mayúsculas y minúsculas. Para el nombre del canal debes usar solo letras en minúsculas o mayúsculas (a-z o A-Z). No se permiten otros caracteres, como guion (-) o guion bajo (\_).

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Panel de control por tienda: agregar la aplicación">

Agrega un panel de control (aplicación) identificado por la combinación del nombre del paquete Android y el canal establecido en el APK/manifiesto. Ejemplo: Si el nombre del paquete de Android es com.myapp y el nombre del canal es abcstore, el nombre exclusivo del tablero es com.myapp—abcstore.

**Para agregar un panel de control por tienda en AppsFlyer**:

1. Ve a **Mis aplicaciones** y haz clic en **Agregar aplicación**.
2. Selecciona **Android > En tiendas de terceros.**
3. Rellena lo siguiente:
   * **Nombre del paquete de Android:** el nombre del paquete es exactamente como se muestra en el paquete de la aplicación.
   * **Nombre del canal:** identificador único (nombre de la tienda) para diferenciar los paneles de control que tienen el mismo nombre de paquete. Verifica que usas el mismo valor en el APK preparado para la tienda. **Nota:** Para el nombre del canal debes usar letras en minúsculas o mayúsculas solamente (a-z o A-Z). No se permiten otros caracteres, como guion (-) o guion bajo (\_).
   * **URL de la aplicación:**
     * Contiene la dirección de descarga de URL predeterminada que rellena la macro af\_r en los enlaces de atribución. Introduce la URL donde se aloja el APK o la URL de su página de aterrizaje.
     * Puedes cambiar esto por cada enlace de atribución cuando los crees.
4. Haz clic en **Siguiente**.
5. Sigue las instrucciones de la interfaz para completar la adición de la aplicación.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Pruebas: ambas opciones de panel de control">

#### **instalaciones no orgánicas**

**Para probar instalaciones no orgánicas:**

1. Usa un dispositivo de Android que no tenga tu aplicación instalada o <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registra el dispositivo</Anchor>.
2. Genera un enlace de atribución de prueba utilizando un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">enlace de OneLink</Anchor>. Usa test como nombre de la fuente de medios ("&pid=test").
3. Agrega un ID de publicidad que sea el ID de publicidad de Google (GAID), OAID o ID de Android a la URL del clic.

   ```http
   http://app.appsflyer.com/com.greatapp?pid=test
   &af_r=http://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Envíate el enlace de atribución por correo electrónico y haz clic en él. **Una vez redirigido, no ejecutes la instalación desde la tienda**. En lugar de ello, instala la versión beta actualizada de la aplicación con el SDK de atribución de AppsFlyer insertado e iníciala.

| Panel de control único | Panel de control por tienda |
| --- | --- |
| <ol><li>Verifica el reporte de raw data de la instalación de tu aplicación en la página Datos exportados.</li><li>Deberías ver una conversión de instalación con la fuente de medio de prueba. En la columna **Tienda de aplicaciones de la instalación**, deberías ver el nombre de la tienda tal como aparece en el archivo manifest.xml.</li><li>También puedes ver el param "af\_installstore": "STORE\_NAME" en los registros de la instalación.</li></ol> | <ol><li>Ve a la aplicación necesaria del panel de control por tienda.</li><li>Verifica el reporte de raw data de las instalaciones de la aplicación en la página Datos exportados o consulta la página de información general de la aplicación.</li><li>Deberías ver una conversión de instalación con la fuente de medios de "prueba".</li></ol> |

#### **Instalaciones orgánicas**

**Para probar instalaciones orgánicas:**

1. Utiliza un dispositivo de Android que no tenga instalada tu aplicación o que esté <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registrado</Anchor>.
2. Instala la versión beta actualizada de la aplicación con el SDK de atribución de AppsFlyer insertado e iníciala.
3. Revisa los resultados:

#### Resultados esperados

| Panel de control único | Panel de control por tienda |
| --- | --- |
| Revisa la página de información general para observar si hay una instalación orgánica nueva (clasificada como "orgánica" con respecto a la fuente de medios). Actualmente, con el método de aplicación única, no existen indicaciones con respecto al origen de las instalaciones orgánicas. | <ol><li>Ve al panel de control y a la página de información general de la aplicación específicos de la tienda evaluada.</li><li>Deberías ver una conversión de instalación en fuente de medios "orgánica".</li></ol> |

</Accordion>

## Características adicionales

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Dirigir a los usuarios de Facebook a la tienda de aplicaciones de Amazon">

1. Configura un enlace de URL a la aplicación desde la configuración de tu aplicación de Meta, en la sección **Android**.
2. Inicia sesión en Meta como administrador de la aplicación, ve a <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor> y elige la aplicación.
3. Ve a la sección de configuración y busca las opciones de Android o, si aún no has configurado Android, agrega la plataforma.
4. Completa los detalles requeridos, incluida la URL de la tienda de aplicaciones de Amazon específica para tu aplicación.  

   [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)
5. En el panel de control de AppsFlyer, en Integraciones activas, selecciona Anuncios de Meta e introduce el mismo ID de aplicación de Facebook que usas al registrar anuncios de instalación de aplicaciones móviles de Meta en la tienda con AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Obtener datos: reportes adicionales de AppsFlyer">

Además del panel de control general, puedes utilizar los siguientes métodos de reporte en AppsFlyer.

* Cohorte:
  * Combina varios paneles de control (aplicaciones) en un solo reporte.
  * Visualiza el rendimiento de cada panel de control desglosándolo por install\_app\_store
* Pull API (para el método de aplicación única): el raw data de instalaciones de <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Pull API</Anchor> no contiene la **tienda de aplicaciones de la instalación** por defecto. Para incluir la columna, agrega lo siguiente a la llamada de la Pull API: `&additional_fields=install_app_store`
* Si usas el método del panel de control múltiple, usa el <Anchor target="_blank" href="/marketers/es/docs/custom-dashboards">panel de control personalizado</Anchor> para combinar los datos de rendimiento de varias aplicaciones en un solo lugar.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Implementación de referencias: tiendas de terceros de Android">

La atribución del referrer de tiendas de terceros es compatible con el SDK de la siguiente manera:

* **El referrer de la tienda Samsung**: soporte inmediato.
* **El referrer de la tienda Huawei**: tu desarrollador debe añadir una dependencia; para ver las instrucciones, consulta [el Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer).
* En el caso de Xiaomi, es necesario configurar una dependencia adicional. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer">Aprender más</Anchor>

Tiendas de terceros de Android que tienen integraciones de atribución de referentes con AppsFlyer

| Tienda de aplicaciones de terceros | Comenzando desde | Versión del SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Tienda de Aplicaciones de Huawei | Julio de 2020 | +5.4.6, +6.1.1 |
| <span id="samsung-galaxy-store"></span>Tienda de Samsung Galaxy | Diciembre de 2020 | +6.1.1 |
| <span id="xiaomi-getapps-store"></span>Tienda Xiaomi GetApps | Septiembre de 2022 | 6.9.0 + |

</Accordion>

<div id="3rd-party-raw-data" />

<Accordion title="Se admite la atribución de referencia en relación con Google Play y las tiendas de terceros que se indican aquí.">

La atribución de referencia por parte de una tienda de terceros se refleja en los reportes de raw data de la siguiente manera:

* Tipo de coincidencia: el nombre de la tienda de terceros atribuida. Por ejemplo, huawei\_referrer.
* Colaborador: si el usuario se involucró con varias tiendas de aplicaciones antes de instalar la aplicación, AppsFlyer considera estos engagements como colaboradores. La instalación se otorga al engagement con el último clic. Ejemplo:
  * Un usuario hace clic en un anuncio publicado por Google y es redirigido a la Play Store. El usuario no descarga la aplicación.
  * El usuario hace clic en otro anuncio y se le redirige a la tienda de Samsung Galaxy. El usuario descarga e instala la aplicación.
  * La atribución se otorga a la red de publicidad, lo que hace que el usuario sea redirigido a la tienda Samsung Galaxy; Google es reconocido como colaborador.

</Accordion>

## Resolución de Problemas

### Instalaciones atribuidas a la aplicación predeterminada

Si creas un APK de aplicación con una configuración de canal, pero no creas un panel de control para este en la cuenta de AppsFlyer: las instalaciones se atribuyen a la aplicación predeterminada, normalmente la aplicación Google Play Store de tu cuenta. Si no hay una aplicación predeterminada, no se registran datos para la aplicación.

## Rasgos y limitaciones

| Característica | Observaciones |
| --- | --- |
| Redirección de OneLink a varias tiendas de aplicaciones | Se pueden establecer varias tiendas de aplicaciones en la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> si el nombre del paquete de aplicaciones es el mismo para todas las tiendas de aplicaciones e implementas la opción de panel de control único. |
| Tienda de aplicaciones de la instalación | Este parámetro no está disponible para agencias o redes de publicidad. |
| Migración del panel de control por tienda a un panel de control único | Si tu aplicación Android está disponible exclusivamente a través de una tienda de terceros, [debes establecer su estado de Google Play como Published out of store al añadir la aplicación](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app). Si eliges cualquier otro estado, se impedirá la redirección a la tienda de terceros y se mostrará un mensaje de error. |
| Cadena | Los valores de `af_ad_revenue` no se pueden agrupar por los valores de `install_app_store` . |

<div data-zendesk-anchors="multistore-android-attribution=atribuci%C3%B3n-de-m%C3%BAltiples-tiendas-de-android h_01HJ369QB8PDKG7QQRV840KRAY=atribuci%C3%B3n-de-m%C3%BAltiples-tiendas-de-android h_01HJ369QB876GZKQCGJZQDXDRF=nota-los-par%C3%A1metros-distinguen-entre-may%C3%BAsculas-y-min%C3%BAsculas single-dashboard-vs-dashboard-per-store=un-solo-panel-de-control-vs-un-panel-de-control-por-tienda h_01HJ369QB8SRN61ABBZ51TKFX2=un-solo-panel-de-control-vs-un-panel-de-control-por-tienda reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=configuraci%C3%B3n-de-tareas h_01HJ369QB8NPE8FAHR42D2YN0K=configuraci%C3%B3n-de-tareas before-you-begin=antes-de-comenzar h_01JD2DEXW74MFE44FM3S0JCK5Q=antes-de-comenzar tasks=tareas h_01JD2DFF2K0APZ98JV1X09ZB33=tareas procedures=procedimientos h_01HJ369QB990HH38TRQESQVFWN=procedimientos single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links h_01K5EJP59771926PMZBRC0C2AB=nota dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=instalaciones-no-org%C3%A1nicas h_01HJ369QB93A3ZZFAF0JAEXFRR=instalaciones-no-org%C3%A1nicas organic-installs=instalaciones-org%C3%A1nicas h_01HJ369QB9SA05Y8VES8DD1FY4=instalaciones-org%C3%A1nicas expected-results=resultados-esperados h_01HJ369QBAJADS4SMSDPKK9RHW=resultados-esperados additional-features=caracter%C3%ADsticas-adicionales h_01HJ369QBAQ49ACSG3VEGSH7D4=caracter%C3%ADsticas-adicionales h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook h_01HJ369QBA2WDAZNNPRRWA3MRT=getting-the-data-appsflyer-reports referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores 01JBKT1E0YA06EKW27VR1DH861=3rd-party-raw-data troubleshooting=resoluci%C3%B3n-de-problemas 01JBKV47A5YJXKYHWA7H8NQAAF=resoluci%C3%B3n-de-problemas installs-attributed-to-the-default-app=instalaciones-atribuidas-a-la-aplicaci%C3%B3n-predeterminada h_01HJ369QBANRCTCFKTGK8BTQEC=instalaciones-atribuidas-a-la-aplicaci%C3%B3n-predeterminada traits-and-limitations=rasgos-y-limitaciones h_01HJ369QBAJA87QJNTYNWYX82N=rasgos-y-limitaciones" />
