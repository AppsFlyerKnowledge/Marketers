---
title: Añadir una aplicación a AppsFlyer
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-08-12T12:04:49Z'
  id: 207377436
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/207377436
---
> **Resumen breve:** Descubre cómo añadir tu aplicación a AppsFlyer para obtener datos de atribución sobre instalaciones y eventos dentro de la aplicación, y analiza los datos con las diversas herramientas de AppsFlyer.

## Visión general

Si todavía no has agregado una aplicación a tu panel, la página de incorporación de aplicaciones aparecerá al iniciar sesión en AppsFlyer. El onboarding de aplicaciones te guía a través de todos los pasos necesarios para añadir tu aplicación y prepararla para la atribución.

### Acceder al asistente para añadir una aplicación

Puedes acceder al asistente para añadir aplicaciones desde la plataforma o mediante la página de incorporación de aplicaciones (solo para aplicaciones Android e iOS).

**Para acceder al asistente desde la página de incorporación de la aplicación:**

* En el paso **Agregar tu aplicación**, haz clic en **Añadir aplicación** y sigue las instrucciones para hacerlo.

> 📘 **Nota:**
>
> Si la página de incorporación no está abierta, desde la barra de menú superior > menú desplegable con la dirección de correo electrónico, haz clic en **Incorporación de aplicaciones**.

![página de incorporación.png](https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png)

**Para acceder al asistente Añadir una aplicación desde la plataforma:**

* Desde la barra de menú superior > **Mis Apps,** haz clic en **+ Añadir aplicación**
* Desde la página de inicio de AppsFlyer, haz clic en **+ Añadir aplicación**
* Desde la barra superior, abre el menú de cuenta (desplegable de dirección de correo electrónico) > **Incorporación de aplicaciones**, haz clic en **+ Incorporar otra aplicación**

<Image alt="agregar una aplicación (1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

## Agregar una aplicación

Después de [acceder al asistente para añadir una aplicación](#acceder-al-asistente-para-añadir-una-aplicación), sigue estos pasos:

1. [Introducir los detalles de la aplicación](#introduce-los-detalles-de-la-aplicación).
2. [Proporcionar información adicional](#introduzca-información-adicional-no-aplicable-a-aplicaciones-web).
3. Haz clic en **Añadir mi aplicación**.
4. Copia la clave de desarrollo, que se utilizará en la <Anchor target="_blank" href="/marketers/es/docs/getting-started-onboarding-for-marketers#paso-2-integración-de-sdk--api">integración del SDK</Anchor> (puedes recuperarla más tarde desde la página <Anchor target="_blank" href="/marketers/es/docs/app-settings#configuración-general-de-la-aplicación">Configuración de la aplicación</Anchor>).
5. Haz clic en **Finalizar** o **+ Añadir otra aplicación** para incluir más aplicaciones. Repite el proceso para añadir más aplicaciones.

> 📘 **Nota**
>
> * Solo los administradores y los <Anchor target="_blank" href="/marketers/es/docs/user-management">usuarios de cuenta con los permisos necesarios</Anchor> pueden añadir aplicaciones.
> * A medida que sigues los pasos para añadir una aplicación (a continuación), las opciones disponibles variarán en función de las elecciones previas que hayas realizado.

Después de registrar la aplicación, esta aparecerá en el panel de control. Para que las instalaciones y los eventos dentro de la aplicación se registren y se atribuyan correctamente a las fuentes de medios, necesitas:

* Integrar el SDK
* Conectar la aplicación con socios en el Marketplace de Socios

Consulta <Anchor target="_blank" href="/marketers/es/docs/getting-started-onboarding-for-marketers">todos los pasos</Anchor> para completar el proceso de incorporación.

### Introduce los detalles de la aplicación

Selecciona la plataforma de la aplicación y proporciona los detalles requeridos, tal como se indica a continuación:

<div id="android-androidtv-fire" />

<Accordion title="Android, Android TV, Amazon Fire">

Utiliza esta opción para las siguientes plataformas:

* Android (móvil)
* Android TV
* Amazon Fire
* Amazon Fire TV
* Kindle

<Table>
  <thead>
    <tr>
      <th>
        Estado de Google Play
      </th>
      <th>
        Cuándo utilizarlo
      </th>
      <th>
        Detalles requeridos
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="in-store"></span>
        En tienda
      </td>
      <td>
        Tu aplicación está actualmente disponible en la tienda Google Play
      </td>
      <td>
        **URL de Google Play** (copiada de Google Play)

        * **Ejemplo:** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest&hl=es&gl=ES
        * **¡Importante!**
          * Si tu aplicación **no** está listada en la tienda Google Play de EE.UU., :
            * La URL debe incluir el código de país de cualquier tienda donde esté listado, como mostrado en el ejemplo arriba: **&gl=`{código_de_país}`.** Si no incluyes el código del país, lo harás recibir un error al intentar agregar la aplicación.
            * El código de idioma es opcional: **&hl=`{language_code}`**
          * Si tu tienda **está** listada en la tienda Google Play de EE.UU., tanto el código de país como el código de idioma son opcionales.
      </td>
    </tr>
    <tr>
      <td><span id="pending-approval-not-published"></span>
        Pendiente de aprobación/no publicada
      </td>
      <td>
        Tu aplicación aún no está publicada o está pendiente de aprobación de Google Play
      </td>
      <td>
        **Nombre del paquete de Android**

        * **Ejemplo:** com.appsflyer.adNetworkTest
        * **Nota:** Nombre del paquete es sensible
        * **Formato:**
          * Debe tener al menos dos segmentos (con uno o más puntos)
          * Cada segmento debe iniciar con una letra
          * Todos los caracteres deben ser alfanuméricos o guion bajo (a-z, A-Z, 0-9, o, \_)
          * Longitud máxima de 100 caracteres

        Para más información, consulta la <Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">documentación para desarrolladores de Android</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="third-party-store-out-of-store"></span>
        Tienda de terceros/fuera de la tienda
      </td>
      <td>
        Tu aplicación está en una tienda de aplicaciones Android distinta a Google Play y/o se puede descargar desde un lugar distinto a una tienda de aplicaciones
      </td>
      <td>
        * Para conocer los requisitos detallados, consulta la fila anterior (pendiente de aprobación/no publicado)
        * URL de la aplicación (copiado del third-party o e de la ubicación fuera de la tienda)
        * **Nombre del canal:** un nombre único que estableces en el AndroidManifest.xml de APK individual preparado para esa tienda/ubicación. El nombre debe ser:
          * distingue entre mayúsculas y minúsculas
          * El nombre debe distinguir entre mayúsculas y minúsculas y ser idéntico al nombre que ingresaste en <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">el campo **Nombre del canal** cuando añadiste la app</Anchor>.

        ```xml
        <application>
             ...
             <meta-data android:name="CHANNEL" android:value="Amazon"/>
             ...
        </application>Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
        ```

        > 📘 **Nota:**
        >
        > No se recomienda usar el parámetro channel para la atribución multitienda. Para una implementación más sencilla y estandarizada, usa el parámetro af\_store en su lugar.

        > 🚧 **¡Importante!**
        >
        > Si tu aplicación está disponible en más de una fuente (es decir, cualquier combinación de Google Play, tiendas de third-party o ubicaciones fuera de la tienda), es vital considerar las opciones para la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">configuración de la atribución de Android en múltiples tiendas</Anchor>.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="iOS, tvOS, macOS">

Utiliza esta opción para las siguientes plataformas:

* apps de iOS,
* tvOS
* macOS

| Estado de la App Store | Cuándo utilizarlo | Detalles requeridos |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>En tienda | Tu aplicación está actualmente disponible en la App Store | **URL de la App Store** (copiado de la App Store)<ul><li>**Ejemplo:** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**Notas:**<ul><li>Asegúrate de que la URL incluya el código de país de dos letras de la tienda (por ejemplo, **us** en la URL anterior)</li><li>Una aplicación añadida a la App Store antes del 14 de junio de 2019, puede contener itunes.apple.com en su URL (en lugar de apps.apple.com).</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>Pendiente de aprobación/no publicada | Tu aplicación aún no está publicada o está pendiente de aprobación desde la App Store | **País** de la App Store a la que se ha enviado la aplicación<br /><br />**ID de aplicación** asignado por la App Store, sin el prefijo id<ul><li>**Ejemplo:** 1543229303</li><li>**Formato:** 9 o 10 caracteres numéricos , 0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

Utiliza esta opción para las siguientes plataformas:

* Windows Phone
* Windows (escritorio)

| Estado de la Microsoft Store | Cuándo utilizarlo | Detalles requeridos |
| --- | --- | --- |
| En tienda | Tu aplicación está actualmente disponible en la Microsoft Store | **URL de la Microsoft Store** (copiada de la Microsoft Store)<ul><li>**Ejemplo:** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**Nota:** La URL anterior es un ejemplo para una aplicación de Windows Phone. El formato URL varía para las aplicaciones de ordenador de Windows.</li></ul>**ID de la aplicación:** Longitud máxima de 50 caracteres. |
| Pendiente de aprobación/no publicada | Tu aplicación aún no está publicada o está pendiente de aprobación desde la tienda | **ID de aplicación** asignado por Microsoft Store<ul><li>**Longitud máxima:** 150 caracteres</li><li>**Ejemplo:** 9wzdncrfhwfg</li><li>Nota: El ID de la aplicación es sensible</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="Web (PBA)">

> 📘 **Nota**
>
> Una aplicación web es aquella en la que defines un sitio web para incluirlo en un paquete de marca para nuestra función de Atribución Basada en Personas (PBA).
>
> * Esta opción solo está disponible para clientes suscritos a PBA.
> * <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">Más información</Anchor> sobre PBA y la atribución de visitas web, eventos web e instalaciones asistidas por el sitio web para obtener una vista unificada de los recorridos del cliente en todos los canales, plataformas y dispositivos.

**URL completa:** La URL completa del sitio web para el cuál quieres medir el tráfico. Este es el sitio web en el que has implementado (o implementarás) el <Anchor target="_blank" href="/marketers/es/docs/onboarding-guide-to-people-based-attribution#2">SDK Web de PBA</Anchor>.

[<Image alt="Diagrama_URL" src="https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png" width="377px" />](https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png)

Incluir –

* esquema
* subdominio [opcional]
* nombre de dominio
* dominio de nivel superior
* ruta [opcional] – la dirección de un directorio o página específica de tu sitio web

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación

* Longitud máxima: 100 caracteres
* No se permiten etiquetas XSS

> 🚧 **¡Importante!**
>
> Una vez que creas una aplicación web, no puedes editar sus propiedades (URL y nombre de la aplicación) sin eliminarla y volver a crearla, **lo que significa que también debes <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">eliminar el paquete de marca</Anchor> del que forma parte.**

**Próximos pasos:**

* Añade tu aplicación web recién creada a un <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings">paquete de marca PBA</Anchor> para verla en el panel de control de PBA.
  * Asegúrate de que todas las aplicaciones móviles que deseas incluir en el paquete de marca estén añadidas a tu cuenta antes de crear el paquete.
* <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide">Integra el SDK Web de PBA</Anchor> en el sitio web especificado en la aplicación web para que comience el flujo de datos de medición.

</Accordion>

<div id="web" />

<Accordion title="Web">

Usa la plataforma web para crear una nueva aplicación web y medir las visitas al sitio web y las conversiones mediante Web Performance Measurement.

#### **Antes de comenzar:**

* Visión general
* Si migras desde una aplicación web PBA heredada, puedes usar tu PBA Web Dev Key actual.

#### **Nota**

1. Ve a **My Apps** > **Add app**.
2. Selecciona **Website**.
3. Introduce lo siguiente:

**Nombre de la aplicación**: El nombre que has elegido para tu aplicación web.

* **Longitud:** 1-100 caracteres
* **Caracteres permitidos:** Letras (de cualquier idioma), números, espacios (no al principio ni al final) y caracteres especiales: . - \_ :
* **Caracteres bloqueados:** ; \`{ }\` $ < > \` \

**Ejemplo:** My Online Store, Corporate Website 2024, E-Commerce\_Production

**Dominio principal (URL completa)**: El dominio principal de tu sitio web. Esto se configura durante la creación de la aplicación web y no se puede cambiar después.

* **Formato:** Solo nombre de dominio válido (sin protocolo, ruta ni puerto)
* **Longitud:** Máximo 500 caracteres
* **Procesamiento:** AppsFlyer automáticamente
  * Elimina http:// o https://
  * Elimina las barras diagonales finales
  * convierte el dominio a minúsculas
* **Inmutabilidad:** No se puede editar después de crear la aplicación

**Importante:** Para cambiar el dominio principal, debes eliminar y volver a crear la aplicación web, lo que da como resultado la pérdida de continuidad de los datos históricos.

**Ejemplos:**

* https://shop.example.com/checkout → Se almacena como shop.example.com → ID de la aplicación: website-shop.example.com
* example.com/ → Se almacena como example.com → ID de la aplicación: [website-example.com](http://website-example.com)

**ID de la aplicación**: El ID único que AppsFlyer crea para la aplicación web en función del dominio principal.

* Se genera automáticamente con el formato: website-`<primary_domain>`
* Ejemplo: website-shop.example.com.

**ID del SDK web**: El identificador que utiliza el SDK web para la atribución (anteriormente denominado web\_dev\_key).

Dos opciones durante la creación de la aplicación:

**Opción 1: Generar uno nuevo (predeterminado)**

* Crea automáticamente un nuevo ID del SDK web
* Formato: website-`{yourdomain.com}`
* Ejemplo: website-shop.example.com.
* **Caso de uso:** Nuevas implementaciones de atribución web

**Opción 2: Reutilizar una clave de desarrollo de PBA existente**

* Selecciona en el desplegable una de las claves de desarrollo de aplicaciones web de PBA (People-Based Attribution) existentes
* Permite una migración fluida sin cambiar el código del sitio web
* **Caso de uso:** Migración de PBA a la nueva solución de atribución web

**Nota:** Reutilizar la clave de desarrollo de PBA te permite migrar de PBA a la nueva aplicación web **sin hacer ningún cambio en la implementación de tu sitio web.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

Cada clave de desarrollo de PBA solo se puede asignar a **UNA** aplicación web. Una vez que se usa una clave de desarrollo de PBA para una aplicación web, deja de estar disponible para otras aplicaciones web.

* **Longitud:** 1-550 caracteres
* **Inmutabilidad:** No se puede cambiar después de crear la aplicación
* **Migración de PBA:** En el desplegable solo aparecen las claves de desarrollo de las aplicaciones web de PBA de tu cuenta

**Moneda**: La moneda utilizada para los informes de la aplicación.

* Código de moneda estándar ISO 4217 (p. ej., USD, EUR, GBP, ILS)
* Se selecciona en el desplegable
* Campo requerido

**Zona horaria**: La zona horaria utilizada para los informes de la aplicación.

* Formato de zona horaria IANA (p. ej., America/New\_York, Europe/London, Asia/Tokyo)
* Seleccionado en el menú desplegable
* Campo requerido

4. Haz clic en **Crear aplicación**.

**Limitaciones**

* El **dominio principal no se puede cambiar** después de crear la aplicación.
* El dominio principal se añade automáticamente a **Dominios excluidos** como tipo **PRIMARY**.

Cada **Web Dev Key heredada solo se puede reutilizar para una** nueva aplicación web.

> 📘 **Nota**
>
> Para obtener toda la información sobre la configuración de atribución web, <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings">consulta aquí</Anchor>.

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**Nombre de la aplicación:** Nombre del canal copiado desde el <Anchor target="_blank" href="https://developer.roku.com/developer">Panel de Desarrollador de Roku</Anchor>.

* **Ejemplo:** Mi canal de Roku
* **Formato:**
  * Longitud máxima de 100 caracteres
  * No se permiten etiquetas XSS

**ID del canal:** ID numérico asignado al canal por Roku.

* **Formato:**
  * Caracteres numéricos (0-9)
  * Nota
* **¿Cómo lo encuentro?**
  * Desde el <Anchor target="_blank" href="https://developer.roku.com/developer">panel de desarrollador de Roku</Anchor>, haz clic en el nombre del canal que estás agregando a AppsFlyer. Esto abrirá la página de Vista Previa y Publicación de Roku para el canal.
  * El número al final de la URL de la página es el ID del canal: ID del canal:

    ![](https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png)

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la app:** El ID de la app. Se encuentra con la notación DNS inversa:  `<tld>`.`<company_name>`.`<app_name>`  
Debe contener un mínimo de 2 segmentos. Cada segmento debe empezar con una letra seguida de caracteres de: `A-Z` `a-z` `0-9.``_` `-`.

Para más información, consulta el campo «id» en la <Anchor target="_blank" href="https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields">documentación de Amazon Vega OS</Anchor>.

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación, tal como lo reconoce Vizio. Comienza con las letras `vz`, seguidas de 2 a 10 caracteres de: `.``-` `0-9``.` `-`. Si necesitas confirmar la ID de la aplicación, consulta con tu representante de Vizio.

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID del paquete asignado a tu aplicación por Samsung. Comienza con la letra `G`, seguida de 8-15 dígitos. Puedes encontrarlo al final de la URL de la tienda de aplicaciones de tu aplicación:

1. Inicia sesión en Samsung TV Seller Office usando [este enlace](https://developer.samsung.com/tv-seller-office/guides/overview.html).

   1. Introduce la URL de desarrollador
2. Tu Bundle ID se genera y se muestra automáticamente. Se puede usar para acceder a la URL de la tienda de aplicaciones.
3. Si tienes algún problema, abre un ticket del panel de incidencias en el Seller Office.

Nota: Para acceder a tu página web única de la tienda de aplicaciones, añade el bundle ID a la URL "[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)".

Por ejemplo, si tu bundle ID es "G15147002586", la URL de tu página será "[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/) ". La URL del desarrollador, el bundle ID y el ID de la tienda de aplicaciones se muestran entonces en los metadatos de esa página.

![](https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png)

</Accordion>

<div id="lg-webos" />

<Accordion title="LG WebOS">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación LG WebOS.

* **Formato:**
  * Longitud máxima de 50 caracteres
  * Caracteres de `A-Z` `a-z``.` `_` tipo de paquete formato. Debe comenzar con letras.
* **Ejemplo:** com.mi-empresa.app

Si necesitas confirmar el ID de la aplicación, consulta con tu representante de LB WebOS.

</Accordion>

<div id="playstation" />

<Accordion title="PlayStation">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de concepto de PlayStation, un identificador único asignado a un juego u otros conceptos de contenido. Aparece como un número de 5 a 9 dígitos en la URL de la tienda PlayStation. Puedes encontrarlo al final de la URL de la tienda de aplicaciones de tu aplicación:

![playstation_app_id_url.png](https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png)

</Accordion>

<div id="vidaa" />

<Accordion title="Finalidad">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación Vidaa. Longitud máxima de 50 caracteres.

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación Steam. Este es el número de 5 a 8 dígitos que aparece en la URL de la tienda Steam:

![steam_store_app_url.png](https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png)

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación de Xbox, tal como aparece en la URL de la tienda de Xbox desde donde se descarga la aplicación. Incluye solo 12 letras y dígitos (`0-9` `0-9``0-9`).

<Image alt="" src="https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png" width="397px" />

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación de Nintendo Switch, como aparece al final de la URL de la tienda desde la que se descarga la aplicación. Incluye 14 dígitos.

* **Ejemplo:** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación Meta Quest, tal como aparece al final de la URL de la tienda de Meta desde donde se descarga la aplicación. Incluye solo 12 letras y dígitos (`A-Z` `a-z0-9`).

![](https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png)

**Nota:** El ID de la aplicación distingue entre mayúsculas y minúsculas.

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación de Epic Games, tal como aparece en la tienda desde la que se descarga la aplicación. Incluye entre 3 y 50 caracteres de: `A-Z` `a-z``0-9``.`

![](https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png)

</Accordion>

<div id="native-pc" />

<Accordion title="PC Nativo">

**Nombre de la aplicación:** El nombre que has elegido para tu aplicación.

**ID de la aplicación:** El ID de la aplicación nativa de PC. Incluye entre 3 y 50 caracteres de: `A-Z` `a-z``0-9``.`

</Accordion>

### Introduzca información adicional (no aplicable a aplicaciones web):

<Image alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

#### **Seleccionar moneda**

Seleccione la moneda en la que se mostrarán los datos de esta aplicación en el panel de control. Los eventos de ingresos y gastos se convertirán a esta moneda utilizando el tipo de cambio vigente en el momento del evento. <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-currency">Obtenga más información</Anchor> sobre la configuración de la moneda de la aplicación y su impacto.

> 🚧 **¡Importante!**
>
> Tenga cuidado al seleccionar la moneda que desea usar para la aplicación. No podrá cambiarla una vez que se hayan registrado los costos y los ingresos.

#### **Seleccionar zona horaria**

Alinee la zona horaria seleccionada aquí con la zona horaria que configure con otros socios de atribución (como anuncios de Meta y Google Ads). Esto garantiza la mayor coincidencia posible entre los datos informados en el panel de AppsFlyer y los que recibe de estos socios.

> 📘 **Nota:**
>
> * Una vez establecida, la zona horaria permanecerá bloqueada y no podrá cambiarse hasta el día siguiente.
> * <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">Conozca más</Anchor> sobre la configuración de la zona horaria de la aplicación y su impacto.

#### **Definir el público objetivo de la aplicación**

Escoja **Sí** o **No** para indicar si su aplicación está dirigida a niños o a un público mixto (niños y adultos).  
Si ha elegido **Sí:**

1. Acceda y lea la <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">guía</Anchor> sobre cómo cumplir con los requisitos para aplicaciones dirigidas a niños.
2. Marque la casilla para confirmar que ha leído la guía y aplicará los controles que indica.

> 📘 **Nota:**
>
> * Dos semanas después de añadir la aplicación, recibirás una notificación solicitando que confirmes la implementación de controles de privacidad para las aplicaciones dirigidas a niños. Tras confirmar, recibirás un mensaje de confirmación. Puedes acceder al mensaje de confirmación desde el Centro de notificaciones o ver los detalles de confirmación en el <Anchor target="_blank" href="/marketers/es/docs/audit-log">Registro de auditoría</Anchor>.
> * Consulta las <Anchor target="_blank" href="/marketers/es/docs/child-directed-apps-faq">preguntas frecuentes sobre aplicaciones dirigidas a niños</Anchor>.

#### Gestiona tus aplicaciones en bloque a través de la API

Los administradores de cuentas pueden <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/app-management-v2-overview">gestionar múltiples aplicaciones en bloque</Anchor> empleando una API dedicada que admite las funciones principales de la interfaz. Esto incluye añadir y eliminar aplicaciones, así como actualizar su configuración. La API también incluye los mismos mecanismos de verificación de errores.

> 📘 **Nota:**
>
> En esta fase, añadir aplicaciones y actualizar su configuración a través de API solo es posible para aplicaciones móviles. Eliminar aplicaciones es posible en todas las plataformas.

### Añadir una aplicación de depuración o de prueba

Si tu desarrollador crea una **aplicación de depuración**, de **sandbox** o de **prueba**, debes añadir la aplicación al dashboard. Una vez que tu desarrollador empiece a hacer pruebas con la aplicación, los datos se mostrarán en el dashboard de la aplicación.

> 📘 **Nota**
>
> Para las aplicaciones de iOS que aún no se han publicado en la App Store y todavía no tienen un ID de App Store válido, puedes continuar con la prueba del SDK añadiendo la aplicación con un **ID ficticio de la App Store de iOS**. Esto permite la integración y la prueba del SDK sin necesidad de contar con una ficha real en la tienda de aplicaciones.

Para obtener instrucciones para desarrolladores sobre cómo crear una aplicación de depuración y añadirla al dashboard, consulta:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app">Nombre del paquete de Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app">Instrucciones para iOS</Anchor>

## Acerca de las aplicaciones en estado pendiente

Trabajar con una aplicación en estado pendiente puede ser útil cuando la estás probando para el SDK de AppsFlyer.

El estado pendiente de la aplicación en el panel no afecta la recopilación y medición de datos. Tanto si una aplicación está en estado pendiente como activa en una tienda, si los usuarios la instalan e interactúan con ella, esos datos se registran en el tablero.

Una vez que tu aplicación pendiente se active, AppsFlyer detectará automáticamente el cambio de estado, sin necesidad de volver a agregarla. <Anchor target="_blank" href="/marketers/es/docs/why-is-my-app-still-pending">Aprenda más</Anchor> sobre las aplicaciones pendientes y el procedimiento opcional para actualizar manualmente el estado.

## Resolución de problemas

Encuentra soluciones para problemas comunes:

<div id="app-wasnt-added" />

<Accordion title="La aplicación no se añadió">

Si este error ocurre, contacta con tu CSM o envía un correo a [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="La aplicación no está en la tienda">

Confirme que ha copiado correctamente la URL de la tienda, asegurándose de usar el nombre o ID apropiado de la aplicación.

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="No se puede acceder al marketplace.">

Este error puede ocurrir al añadir una aplicación de Android desde una tienda que no sea la de EE. UU. Siga estos pasos para solucionarlo:

1. Añada la aplicación con estado de **Pendiente de aprobación/no publicada**, como se indica anteriormente.
2. Acceda a la página de **Configuración de la aplicación** de AppsFlyer.
3. Cambie el **país de la tienda de aplicaciones** al correcto (por ejemplo, Japón).

</Accordion>

<div id="something-went-wrong" />

<Accordion title="Ha ocurrido un error. Inténtelo de nuevo, por favor.">

Una posible causa de este error es intentar añadir una aplicación de Android sin un código de país (para aplicaciones **no** listadas en Google Play Store de EE. UU.). Consulte [más arriba](/docs/adding-an-app-to-appsflyer#in-store) para ver los detalles completos sobre cómo resolver este problema.

</Accordion>

<div id="my-ios-app" />

<Accordion title="Mi aplicación de iOS fue eliminada de la App Store. ¿Por qué sigo viendo instalaciones?">

Esto sucede porque los usuarios pueden reinstalar una aplicación a través del sistema operativo si anteriormente existía en su dispositivo. Incluso si la aplicación ya no está disponible en la App Store, los usuarios aún pueden instalarla, y estas instalaciones se contarán en AppsFlyer.

</Accordion>

## Otra información

<div id="product-line" />

<Accordion title="Evento ambiguo">

Puedes añadir o eliminar aplicaciones de una línea de productos. Para obtener más información sobre las líneas de productos y lo que ofrecen, <Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution">consulta aquí</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H8Y09SSKZS2RHM35JT16ESKM=visi%C3%B3n-general entering-the-wizard-for-adding-an-app=acceder-al-asistente-para-a%C3%B1adir-una-aplicaci%C3%B3n 01H8Y0K9EHWH05DB5K02ASJG11=acceder-al-asistente-para-a%C3%B1adir-una-aplicaci%C3%B3n 01H8F2TENNWXADKVZFHY9SE8JC=nota adding-an-app=agregar-una-aplicaci%C3%B3n 01H8ECFB7V0DCNE0ZKPZ2GCVMP=agregar-una-aplicaci%C3%B3n 01H81661SR41SQFZZ0AW6K2EDM=nota-1 enter-app-details=introduce-los-detalles-de-la-aplicaci%C3%B3n 01H815FE64VZZS9WGJSC8VY74D=introduce-los-detalles-de-la-aplicaci%C3%B3n 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire h_01KRB930DZ2NRYBZSERSG7WB3A=nota-2 01H815FE641Q6N5JY5846QE59Y=importante 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=nota-3 01H815FE65R1Z06TJR0DNC8PFY=importante-1 h_01KGEPG8V7ZZ6V2EYYPES0QM77=web before-you-begin=antes-de-comenzar h_01KGPM33BA6AJSX32CTN808AXM=antes-de-comenzar to-add-a-web-app=nota-4 h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=nota-4 h_01KGPM5TTNSECSWEAQY5VH7DTY=nota-5 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc enter-additional-information-not-applicable-to-web-apps=introduzca-informaci%C3%B3n-adicional-no-aplicable-a-aplicaciones-web 01H815FE65AWE8VKV9FYJ7N8MV=introduzca-informaci%C3%B3n-adicional-no-aplicable-a-aplicaciones-web select-currency=seleccionar-moneda h_01HHCFD94K6PGQRED6Z6KXKRQF=seleccionar-moneda 01H815FE65X7BCFKH1EEFA91GQ=importante-2 select-timezone=seleccionar-zona-horaria h_01HHCFDE25S92GZ9TPGQW4PXHV=seleccionar-zona-horaria h_01HMNSSBP2EFXCVW290MKW1EFV=nota-6 define-app-audience=definir-el-p%C3%BAblico-objetivo-de-la-aplicaci%C3%B3n h_01HHCFDRNFDERZZV3TT8BVXMB4=definir-el-p%C3%BAblico-objetivo-de-la-aplicaci%C3%B3n h_01H9MYF17VNBETQ0HS745EJ85H=nota-7 manage-your-apps-in-bulk-via-api=gestiona-tus-aplicaciones-en-bloque-a-trav%C3%A9s-de-la-api h_01HR3Z81NXCAZKK26HWCN5VD9D=gestiona-tus-aplicaciones-en-bloque-a-trav%C3%A9s-de-la-api h_01HR3ZJW7YD4B8WV0NW9MX6EVP=nota-8 add-debug-or-testing-app=a%C3%B1adir-una-aplicaci%C3%B3n-de-depuraci%C3%B3n-o-de-prueba h_01K2F8JX66F614HF8D5MWQ26P7=a%C3%B1adir-una-aplicaci%C3%B3n-de-depuraci%C3%B3n-o-de-prueba ios-dummy-app-id-note=nota-9 h_01K2F8JX662XEY0A47DZG6DHWQ=nota-9 about-pending-apps=acerca-de-las-aplicaciones-en-estado-pendiente 01H815FE65MYPABC3DTVEMA8E9=acerca-de-las-aplicaciones-en-estado-pendiente troubleshooting=resoluci%C3%B3n-de-problemas 01H815FE655HS8EA4R00D0VCYD=resoluci%C3%B3n-de-problemas 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app other-information=otra-informaci%C3%B3n h_01K7KSRWCB1Y89T21JFJR42VAJ=otra-informaci%C3%B3n h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />
