---
title: Configuración de Store Revenue de ROI360
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-08-12T11:48:41Z'
  id: 42158608158353
  locale: es
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/es/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Configura la solución de ingresos de tienda ROI360 de AppsFlyer.

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> Los ingresos de la tienda ROI360 solo están disponibles para los clientes del plan premium de ROI360. Para verificar tu plan o realizar una actualización, ponte en contacto con tu Customer Success Manager (CSM).

<div id="overview" />

## Visión general

<div id="note" />

> 📘 **Nota:**
>
> Para obtener más información sobre ROI360, incluido cómo funciona y cómo habilitarlo en AppsFlyer, consulta <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue">Sobre los ingresos de tienda de ROI360</Anchor>.

Para configurar los ingresos de tienda de ROI360, completa los siguientes pasos en este orden:

1. Configura las credenciales de la tienda (iOS y Android):
   * [iOS:](#paso-1-ios-configura-las-claves-de-app-store-connect) Configura las claves de App Store Connect (clave de compra in-app, ID de clave e ID del emisor) en AppsFlyer.
   * [Android](#paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos): Configura una cuenta de servicio de Google Cloud, establece los permisos necesarios en Google Play Console y sube a AppsFlyer la clave JSON de la cuenta de servicio.
2. Configura las notificaciones de servidor (iOS y Android):
   * [iOS](#paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store): Configura las notificaciones del servidor de App Store, ya sea enviándolas directamente a AppsFlyer (recomendado) o reenviándolas desde tu propio endpoint, y valida la integración.
   * [Android](#paso-2-android-configura-las-notificaciones-del-servidor-de-google-play): Configura las notificaciones para desarrolladores en tiempo real de Google Play (RTDN), ya sea permitiendo que Google Play envíe las notificaciones directamente a AppsFlyer (recomendado) o reenviándolas a través de Pub/Sub.
3. [Implementa el SDK Connector](#paso-3-implementa-el-conector-sdk): Prepara a los desarrolladores para integrar el Purchase SDK Connector de AppsFlyer.
4. [Verifica la implementación del SDK](#paso-4-verifica-la-implementación-del-sdk): Prueba las compras in-app y las suscripciones de sandbox en ambas plataformas para confirmar que AppsFlyer recibe y procesa correctamente los eventos del SDK y las notificaciones de servidor.
5. [Verifica y actualiza la configuración](#paso-5-verifica-y-actualiza-la-configuración): Revisa y confirma los estados de la validación de compras, la gestión de reembolsos, la medición de suscripciones y la integración con la tienda para garantizar una atribución de ingresos precisa y continua en todas las plataformas.
6. [Publica las versiones de la app](#paso-6-lanza-las-versiones-de-la-aplicación-con-el-conector-del-sdk): Publica versiones actualizadas de la app con el SDK Connector integrado, asegurándote de que los indicadores de sandbox estén desactivados y de que las reglas de validación permitan los eventos de ingresos necesarios.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## Paso 1 (iOS): Configura las claves de App Store Connect

En el paso 1, obtén las siguientes credenciales de App Store Connect e introdúcelas en la página de configuración de ingresos dentro de la plataforma de AppsFlyer

* Clave de compra in-app
* ID de clave
* ID del emisor

**Antes de empezar**:

La configuración de las credenciales implica pasos realizados tanto en App Store Connect como en AppsFlyer. Durante la configuración, mantén abiertas las pestañas App Store Connect y AppsFlyer.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Crear las claves de App Store Connect">

Para configurar las credenciales de iOS, sigue estos pasos:

1. En App Store Connect, ve a **Usuarios y acceso**

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Ve a **Usuarios y acceso** > **Integraciones** y, en la lista de **Claves** , selecciona **Compra in-app**.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Haz clic en + para generar una clave de compra in-app nueva.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Ingresa un nombre para tu clave de API.
5. Haz clic en **Generar**.
6. Haz clic en **Descargar clave de compra in-app** junto a la clave que acabas de generar para descargarla. **Nota**: Solo puedes descargar la clave una vez.
7. Copia el **ID de clave** de la clave que acabas de generar y pégalo en la configuración de compras & suscripciones de AppsFlyer para **ID de clave**.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. Copia el **ID del emisor**. **Nota**: Si el **ID del emisor** no se muestra en la parte superior de la página, crea una clave de API de App Store Connect (con cualquier nivel de acceso). Después de eso, el ID del emisor aparecerá en la parte superior de la página para la clave de compra in-app.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 Configura la clave de App Store Connect en AppsFlyer">

1. <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#activa-los-ingresos-de-tienda-de-roi360">Activa los ingresos de tienda de ROI360</Anchor>.
2. En el paso **Claves de App Store Connect** , haz clic en [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Cargar** en el campo **Clave de compra in-app** para cargar el archivo p8.
3. En la sección titulada **Claves de App Store Connect**, pega los valores que copiaste de App Store Connect.

   * **ID de clave**

   * **ID del emisor**
4. Haz clic en **Validar claves** para asegurarte de que las claves que has introducido sean correctas. **Nota: Es posible que Validar clave** no funcione si tu aplicación aún no se ha publicado en la App Store.
5. haz clic en **Guardar y siguiente**

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## Paso 1 (Android): Configurar la clave de cuenta de servicio y los permisos

En el paso 1, puedes obtener las siguientes credenciales de App Store Connect e ingresarlas en la página de Configuración de ingresos dentro de la plataforma de AppsFlyer.

**Antes de empezar**:

* La configuración de la medición de las compras in-app y de los ingresos por suscripción implica pasos que se realizan en <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>, y la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">interfaz de usuario de AppsFlyer</Anchor>. Te recomendamos que mantengas un control de los tres lugares abiertos durante toda la configuración.
* La configuración en la interfaz de usuario de AppsFlyer requiere permisos de administrador.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1. Vincula tu cuenta de desarrollador de Google Play a tu proyecto de Google Cloud">

**Requisitos previos**: Acceso a Google Play Console y Google Cloud Project.

**Para vincular tu cuenta de desarrollador de Google Play a tu Google Cloud Project, sigue estos pasos**:

1. En Google Play Console, ve a tu cuenta de desarrollador de Google Play.
2. Vincula la cuenta a tu proyecto de Google Cloud. Para obtener instrucciones, consulta este <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">tema de ayuda de Google</Anchor>.
3. Habilita la API para desarrolladores de Google Play. Para obtener instrucciones, consulta <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">este tema de ayuda de Google</Anchor>.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2. Configuración de la cuenta de servicio en Google Cloud Platform">

**Requisitos previos**: Acceso a Google Cloud Platform.

**Para configurar tu cuenta de servicio, sigue estos pasos**:

1. Crea o localiza la **Cuenta de Servicio**:
   1. Ve a la **Service accounts** sección en Google Cloud Platform y haz clic en **Crear cuenta de servicio**.

      [![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Rellena los datos de la cuenta de servicio.

      [![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Copia la dirección de correo electrónico.

      [![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Haz clic en **Crear y continuar**.

      [![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. En el paso **Otorgar a esta cuenta de servicio acceso al proyecto** , selecciona el **Pub/sub** rol de suscriptor.

      [![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Haz clic en **Continuar** > **Hecho**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Descarga la **Clave privada de la cuenta de servicio**:
   1. En Google Cloud Platform, ve a la sección **Service accounts** , busca la cuenta que deseas (la que acabas de crear) en la lista y haz clic en el icono **More actions** .
   2. Haz clic en **Gestionar claves**.

      [![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Haz clic en **Agregar clave** > **Crear nueva clave**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. En la ventana emergente **Create private key** , en **Key type** , selecciona **JSON** y haz clic **Create** .

      [![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Haz clic en **Crear**. Se descarga el archivo JSON de la clave privada.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Guarda el archivo de clave JSON, que se cargará en AppsFlyer más tarde.   
      [Práctica recomendada]: Debes guardar la clave; no podrás recuperarla más tarde. Si no la guardas, tendrás que crear una clave completamente nueva

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3. Establecer permisos de acceso a la API en Google Play Console">

**Requisitos previos**: acceso a la Google Play Console.

**Nota**: Puede llevar un tiempo (a veces incluso 24 horas) después de configurar las credenciales y los permisos de la cuenta de servicio hasta poder utilizarlos. Esto puede provocar errores en pasos posteriores.

**Para establecer permisos de acceso a la API en Google Play Console**:

1. En Google Play Console, ve a **Usuarios y permisos**, busca la cuenta de servicio que has creado y haz clic en **Invitar a nuevos usuarios**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Introduce la **dirección de correo electrónico** que copiaste cuando configuraste tu cuenta de servicio en el paso 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. En la sección **Permisos** , ve a la pestaña **Permisos de cuenta** y selecciona ambas opciones:

   * Ver los datos financieros, los pedidos y las respuestas a la encuesta de cancelación.
   * Gestionar los pedidos y las suscripciones.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. En la pestaña **Permisos de la aplicación** , haz clic **Agregar aplicación,** y, a continuación, selecciona tu aplicación. Agrega varias aplicaciones si es necesario.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Haz clic en **Invitar usuario.**

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. En la ventana emergente de confirmación, haz clic en **Enviar invitación**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4. Cargar la clave privada de la cuenta de servicio en AppsFlyer">

Carga y valida la clave JSON de Google que descargaste en el [paso 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Requisitos previos**: acceso de administrador a AppsFlyer.

**Para cargar la clave privada de la cuenta de servicio en AppsFlyer, sigue estos pasos**:

1. <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#activa-los-ingresos-de-tienda-de-roi360">Activa Store Revenue de ROI360</Anchor>.
2. En el paso **Clave de cuenta de servicio y permisos** , en el campo **Cargar clave JSON de Google** , haz clic [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)  **(icono de carga).**
3. Carga el archivo JSON que descargaste en el [paso 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Haz clic en **Validar clave.** **Nota:**
   * Después de configurar las credenciales y los permisos de la cuenta de servicio, puede pasar algún tiempo (a veces incluso 24 horas) hasta que se puedan utilizar. Esto puede hacer que recibas errores al intentar validar la clave o realizar una prueba de validación.
   * Para evitar el tiempo de espera de 24 horas, en la Google Play Console, ve a cualquier aplicación; luego, ve a **Monetize** > **Products** > **Subscriptions/In-app products**, y realiza un cambio. Por ejemplo, edita la descripción de tu producto y guárdalo. Esto debería actualizar instantáneamente las credenciales y permisos de la cuenta. Luego puedes deshacer los cambios.
5. Haz clic en **Guardar y siguiente**.

</Accordion>

<div id="step-2-ios-set-up-app-store-server-notifications" />

## Paso 2 (iOS): Configura las notificaciones del servidor de App Store

Configura cómo se reciben las notificaciones de la App Store en AppsFlyer.

* Si ya tienes configurado un endpoint de notificaciones del servidor de la App Store en App Store Connect (por ejemplo, tu propio backend u otro servicio), elige entre la **Opción 1 (recomendada)** o la **Opción 2**.
* Si todavía no has configurado un endpoint en App Store Connect, elige la **Opción 1**.

<div id="option-1-recommended---appsflyer-as-the-primary-endpoint" />

#### Opción 1 (recomendada): AppsFlyer como endpoint principal

Sustituye la URL de notificaciones actual de App Store Connect por el endpoint de AppsFlyer y añade tu endpoint anterior en AppsFlyer como destino de reenvío. La lógica y los flujos de trabajo actuales de tu suscripción no cambian y siguen funcionando como se espera.

El flujo de notificaciones de esta opción es el siguiente:

1. App Store Connect envía notificaciones a AppsFlyer
2. AppsFlyer las procesa para ROI360
3. AppsFlyer reenvía todas las notificaciones a tu endpoint existente **en tiempo real**

Para usar esta opción, completa los pasos [2.1](#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](#22-send-notifications-directly-to-appsflyer) y [2.4](#24-test-the-server-notifications-integration).

<div id="option-2---your-endpoint-as-the-primary-endpoint" />

#### Opción 2: tu endpoint como endpoint principal

Si prefieres mantener tu endpoint existente como destino principal, configura tu servidor para reenviar las notificaciones del servidor de App Store a AppsFlyer.

Para usar esta opción, omite los pasos 2.1 y 2.2 y completa los pasos [2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer) y [2.4](#24-test-the-server-notifications-integration)

<div id="note-1" />

> 📘 **Advertencia**
>
> Apple solo admite un endpoint de notificaciones del servidor de App Store por aplicación y envía a él todos los tipos de notificación, no solo las notificaciones de compra y suscripción. AppsFlyer usa las notificaciones de compra y suscripción para medir los ingresos. Confirma la recepción de cualquier otro tipo a Apple para que Apple deje de reintentarlo, pero no lo procesa ni actúa en consecuencia.
>
> Si tu aplicación depende de tipos de notificación distintos de las compras y las suscripciones (por ejemplo, notificaciones de consentimiento), asegúrate de que esas notificaciones lleguen a tu propio servidor:
>
> * **Opción 1:** Mantén AppsFlyer como endpoint principal y habilita el reenvío (paso 2.1). AppsFlyer reenvía una copia de todas las notificaciones a tu endpoint en tiempo real, sin cambios respecto a cómo las envió Apple, incluidos los tipos que AppsFlyer no procesa.
> * **Opción 2:** Mantén tu propio endpoint como destino principal para que tu servidor reciba y gestione directamente todos los tipos de notificación, y reenvía a AppsFlyer las notificaciones de compra y suscripción.

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="2.1 Copiar el endpoint para notificaciones del servidor de AppsFlyer">

Para copiar el endpoint de notificaciones del servidor de AppsFlyer, sigue los pasos a continuación:

1. **En AppsFlyer,** en el paso **App Store server notifications** copia el endpoint de notificaciones del servidor de AppsFlyer.
2. Si antes tenías otro endpoint de notificaciones del servidor de App Store y quieres que AppsFlyer le reenvíe las notificaciones, selecciona **Reenviar una copia de las notificaciones a tu servidor (solo relevante para la opción 1).**
3. Ingresa tu endpoint de reenvío de notificaciones en el cuadro de texto que se muestra.

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="2.2 Enviar notificaciones directamente a AppsFlyer">

Para enviar notificaciones directamente a AppsFlyer, configura AppsFlyer como endpoint principal de notificaciones del servidor de App Store.

1. En **App Store Connect**, en la **App Information** sección, desplázate hasta **App Store Server Notifications**, y junto a **Production Server URL**, haz clic en **Edit**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Pega [el endpoint de notificaciones del servidor de AppsFlyer copiado de AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), selecciona **Version 2 Notifications**, y haz clic en **Save**. **Nota:** Ya no se admiten las notificaciones de la versión 1. Si el selector de versión de notificaciones no aparece en App Store Connect, significa que ya estás usando la versión 2.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. En la **App Information** sección, desplázate hasta **App Store Server Notifications**, y junto a **Sandbox Server URL**, haz clic en **Edit**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
4. Pega [el endpoint de notificaciones del servidor de AppsFlyer copiado de AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), selecciona **Version 2 Notifications**, y haz clic en **Save**. **Nota:** Las notificaciones de la versión 1 ya no reciben soporte. Si el selector de versión de notificaciones no aparece en Apple Store Connect, significa que ya estás usando la versión 2.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 [Opcional] Reenviar las notificaciones de tu endpoint a AppsFlyer">

Usa este paso solo si quieres mantener tu endpoint como destino principal de las notificaciones del servidor de la tienda de aplicaciones, en lugar de enviar las notificaciones directamente a AppsFlyer.

Esta opción no es la configuración recomendada y requiere una implementación de backend. Si ya has configurado AppsFlyer como endpoint principal en el paso **2.2** anterior, omite este paso.

Para reenviar notificaciones del servidor desde tu endpoint a AppsFlyer, sigue estos pasos:

1. En **App Store Connect**, en la **Información de la aplicación** sección, desplázate hasta **App Store Server Notifications**, y junto a **Production Server URL**, haz clic en **Editar**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Pega **la URL de tu endpoint del servidor**.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. Selecciona **Version 2 Notifications. Nota:** Las notificaciones de la versión 1 ya **no reciben soporte**. Si el selector de versión de notificaciones no aparece en Apple Store Connect, significa que ya estás usando la versión 2.
4. Haz clic en **Guardar**.
5. En **App Store Connect**, en la **Información de la aplicación** sección, desplázate hasta **App Store Server Notifications**, y junto a **Sandbox Server URL**, haz clic en **Editar**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
6. Pega **la URL de tu endpoint del servidor**.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. Selecciona **Version 2 Notifications. Nota:** Las notificaciones de la versión 1 ya **no reciben soporte**.
8. Haz clic en **Guardar**.
9. Configura tu backend para reenviar las notificaciones del servidor de Apple a la URL del endpoint de notificaciones de AppsFlyer. Las solicitudes deben coincidir exactamente con la carga útil de la tienda de aplicaciones tal como se recibe de Apple; consulta <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">los requisitos de formato de Apple</Anchor>.

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 Probar la integración de las notificaciones del servidor">

Para confirmar que AppsFlyer está recibiendo correctamente las notificaciones del servidor de App Store, o si has configurado el endpoint hace poco y aún no ha llegado ninguna notificación del servidor:

1. En AppsFlyer, ve al paso **Notificaciones del servidor de App Store**.
2. Haz clic en **Prueba de integración**. AppsFlyer envía una solicitud de notificación de prueba a Apple, comprueba si se ha recibido alguna notificación válida de Apple en los últimos 7 días y muestra una de las siguientes opciones:

   * Una confirmación de si se recibieron notificaciones válidas.
   * Un mensaje de estado que indica que no se encontró ninguna notificación.

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Apple puede tardar unos segundos en enviar el mensaje de prueba.


   * Si el estado sigue siendo no válido, espera unos momentos y vuelve a intentarlo.
   * Cuando la prueba se complete correctamente o cuando estés listo para continuar, haz clic en **Guardar y siguiente**.

</Accordion>

<div id="step-2-android-set-up-google-play-server-notifications" />

## Paso 2 (Android): Configura las notificaciones del servidor de Google Play

Para recibir datos de ingresos por compras in-app y suscripciones de Google Play, selecciona entre las siguientes opciones:

* (Recomendado) Google Play envía las notificaciones directamente Con esta opción, no se pueden enviar copias de las notificaciones a tu endpoint. Si deseas seleccionar esta opción, puedes ver [Enviar notificaciones de Google Play directamente a AppsFlyer](#21-send-google-play-notifications-directly-to-appsflyer).
* Google Play te envía primero las notificaciones, que luego se envían a AppsFlyer. Si eliges esta opción, consulta [Reenviar notificaciones de Google Play a AppsFlyer.](#22--optional--forward-google-play-notifications-to-appsflyer)

**Requisitos previos**: Acceso a Google Play Console y AppsFlyer UI.

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="2.1 Enviar notificaciones de Google Play directamente a AppsFlyer">

1. En AppsFlyer, en el paso 2,**Configura las notificaciones del servidor de Google Play**, selecciona **Permitir que el tema de AppsFlyer reciba mensajes RTDN directamente de Google**.
2. Copia el tema de AppsFlyer en el portapapeles.
3. En **Google Play Console** > **Inicio**, selecciona tu aplicación para verla. Se abre el dashboard.

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. Ve a **Monetizar con Play** > **Configuración de la monetización**, y en la **Facturación de Google Play** sección, asegúrate **Activar notificaciones en tiempo real** está marcada.

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. En el **Nombre del tema** campo, pega la dirección del tema de AppsFlyer que has copiado.

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. Para **Contenido de la notificación**, selecciona **Suscripciones, compras anuladas y todos los productos de un solo uso**.

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. Haz clic **Guardar cambios**. Puede tardar un tiempo (a veces incluso 24 horas) en hacer efecto. Por lo tanto, espera antes de realizar la prueba.

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="2.2. [Opcional] Reenviar las notificaciones de Google Play a AppsFlyer.">

**Nota**: Este paso es solo para cuando no has elegido el método recomendado para recibir los datos de compras in-app y los ingresos por suscripciones de Google Play mediante el envío de notificaciones directamente a AppsFlyer. Si has completado los pasos del método recomendado, para crear un tema en el que AppsFlyer reciba directamente las notificaciones RTDN de Google Play, salta este paso.

Si quieres establecer AppsFlyer como suscriptor de tu tema PUB/SUB existente, continúa con las instrucciones que aparecen a continuación.

**Requisitos previos**: Acceso a Google Cloud Platform y AppsFlyer UI.

**Para reenviar las notificaciones de Google Play a AppsFlyer**:

1. En AppsFlyer, desde el menú lateral, ve a **Configuración** > **Configuración de ingresos**,
2. Selecciona tu aplicación,
3. En la pestaña **Compras & suscripciones** , selecciona **Reenviar tus mensajes del tema RTDN a AppsFlyer**.
4. Copia la URL del endpoint en el portapapeles.
5. En Google Cloud Platform, en tu proyecto, busca **Pub/Sub**.

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. En **Pub/Sub** ve a la **Temas** sección, y verifica que tienes un tema pub/sub específico para las suscripciones.

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. En **Pub/Sub,** ve a la **Suscripciones** sección, y haz clic **Crear suscripciones**.

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. Introduce el **ID de suscripción**.

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. Selecciona el tema pub/sub de suscripción correspondiente en el menú desplegable.

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. Para **Tipo de entrega**, selecciona **Push**.

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. Pega la **URL del endpoint** que has copiado de AppsFlyer.

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. En **Período de vencimiento**, selecciona **Nunca vence**.

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. Haz clic en **Crear**.

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. Ve a la sección **Suscripciones** y haz clic en el nombre del tema que quieras.

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. Copia el nombre del tema en el portapapeles.

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. En **Google Play Console**, ve a **Monetizar con Play** > **Configuración de la monetización.** y en la **Google Play Billing** section, pega el nombre del tema que copiaste en el paso anterior en el campo Nombre del tema.

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. Para **Contenido de la notificación**, selecciona **Suscripciones, compras anuladas y todos los productos de un solo uso**.

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. Haz clic **Guardar cambios**. Puede tardar un tiempo (a veces incluso 24 horas) en hacer efecto. Por lo tanto, espera antes de realizar la prueba.

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 Envía una notificación de prueba desde Google Play Console">

Para verificar que AppsFlyer recibe correctamente las notificaciones para desarrolladores en tiempo real (RTDN) de Google Play, envía una notificación de prueba desde Google Play Console:

1. Haz clic en **Enviar notificación de prueba**. Esto envía un mensaje RTDN de prueba al tema de Pub/Sub configurado para AppsFlyer.

   <Image alt="image (33).png" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />
2. En **Google Play Billing**, localiza la sección Nombre del tema.
3. En el menú izquierdo, ve a **Monetizar con Play** → **Configuración de la monetización**.
4. Ve a Google Play Console.

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 Confirma la entrega de notificaciones en AppsFlyer">

1. Cuando la prueba se complete correctamente, o cuando estés listo para continuar, haz clic en **Guardar y siguiente**.
2. Resultado: AppsFlyer muestra si se ha recibido alguna notificación en los últimos 7 días.
   * Si se realiza correctamente, la interfaz muestra la fecha y la hora de la notificación más reciente.
   * Si no se recibió ninguna, la interfaz indica que no se encontraron notificaciones en los últimos 7 días.
   * Si no aparece ningún estado, revisa la configuración de Pub/Sub y vuelve a enviar la notificación de prueba.
3. En el paso **Notificaciones del servidor de Google Play**, haz clic en **Probar integración**.

</Accordion>

</Accordion>

<div id="step-3-implement-sdk-connector" />

## Paso 3: Implementa el conector SDK

En este paso, prepararás a tus desarrolladores para integrar el conector del SDK de compras de AppsFlyer y configurar el entorno de pruebas.

Para implementar el conector del SDK, sigue estos pasos:

1. En el paso **Implement SDK Connector**, copia el **mensaje predefinido** que aparece en el dashboard.
2. Envíalo a tus desarrolladores. Incluye:
   * El nombre y el ID de aplicación
   * Un enlace a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">la guía de integración del SDK</Anchor>.
   * Instrucciones para configurar el entorno de sandbox (`sandbox = true`)
   * Pasos de prueba (utilizando **TestFlight**)

Este mensaje proporciona toda la información que tus desarrolladores necesitan para completar la integración y comenzar las pruebas.

<div id="note-3" />

> 📘 **Nota:**
>
> El conector utiliza la detección automática de transacciones. Como alternativa, puedes implementar el método del SDK `validateAndLog` para registrar manualmente cada transacción. Este método no ofrece soporte para todas las funciones disponibles con el conector. Para obtener más información sobre ambas opciones de integración del SDK, consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">la documentación de DevHub</Anchor>.

<div id="step-4-verify-sdk-implementation" />

## Paso 4: Verifica la implementación del SDK

Prueba la integración de ingresos de compras in-app y suscripciones en un entorno sandbox para confirmar que el conector SDK esté correctamente integrado y que las notificaciones del servidor estén bien configuradas y AppsFlyer las reciba correctamente.

<div id="test-sdk-implementation" />

<Accordion title="Prueba de implementación de SDK">

Para comprobar si AppsFlyer ha recibido cargas útiles válidas de eventos de compra y suscripción de tu aplicación en los últimos 7 días, sigue estos pasos:

1. En el paso **Verifica la implementación del SDK**, haz clic en **Probar la implementación del SDK**.
2. Revisa los resultados, incluida la marca de tiempo de la carga útil más reciente recibida por AppsFlyer.

   <div id="note-4" />

   > 📘 **Nota:**
   >
   > Esta prueba solo confirma que las solicitudes llegan a AppsFlyer y no verifica que los datos estén completos ni que sean correctos.

3. Para validar completamente la implementación, continúa con los pasos de prueba que aparecen a continuación.

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="Eventos y parámetros de sandbox">

* El conector SDK genera eventos solo para la transacción inicial de sandbox:
  * Compra in-app: `af_purchase_sandbox_sdk`
  * Suscripción: `af_ars_sandbox_sdk`
* AppsFlyer procesa las notificaciones del servidor solo si se registró el evento del SDK de la transacción original.
  * Compra in-app S2S: `af_purchase_sandbox_s2s`
  * Suscripción S2S: `af_ars_sandbox_s2s`
* Si el SDK nunca registra la transacción original. no se crea ningún evento S2S.

**Consideraciones de iOS**

* Si `af_purchase_sandbox_sdk` incluye `af_sandbox_revenue`, se asigna a un `af_purchase` de producción.
* Si no hay ingresos, se asigna a un `af_purchase_free` de producción.

**Consideraciones sobre Android**

* Las compras realizadas por **License Testers** siempre generan eventos de sandbox. aunque el modo sandbox no esté configurado en el SDK.

**Parámetros obligatorios para eventos de prueba**

Asegúrate de que cada evento de compra en sandbox incluya:

* **Ingresos = 0** (para evitar afectar a los reportes reales).
* `af_sandbox_revenue` = precio real del producto (para que se atribuyan los ingresos correctos).
* `af_validated` **= true**. Si es `false`, vuelve atrás y verifica la clave de la tienda.
* `af_validation_type` = `receipt_validation`.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Probar las compras in-app y los ingresos por suscripciones">

**Requisitos previos**:

* Para iOS, asegúrate de que, en App Store Server Notifications en App Store Connect, el endpoint de AppsFlyer esté configurado como tu **Sandbox Server URL**.

  [![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**Para probar las compras in-app y los ingresos por suscripciones**:

1. Dile a tus desarrolladores que sigan las instrucciones de <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration">Android</Anchor>, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">iOS</Anchor>, y <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox">Unity</Anchor> para configurar el entorno sandbox en el conector SDK.
2. Realiza compras de prueba o inicia una suscripción con <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester en Google Play</Anchor>. Para iOS, usa <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>. **Nota**: Un producto de suscripción solo se puede probar una vez por dispositivo. En la práctica, un dispositivo no puede registrar varias compras de prueba de la misma suscripción. Los intentos adicionales no se registrarán.
3. Realiza un evento de prueba de reembolso, renovación de suscripción o cancelación de suscripción con <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester en Google Play</Anchor> y <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight en iOS</Anchor>. **Nota**: Si estás probando un producto de suscripción, deja tiempo para que AppsFlyer reciba una notificación del servidor de la tienda, lo que suele ocurrir unos minutos después de que se realice la compra inicial.
4. En el paso **Verify SDK connector implementation**, haz clic en **Test SDK implementation** Indica si se ha recibido correctamente algún payload del SDK desde Purchase Connector en los últimos 7 días.
5. Comprueba que los eventos de prueba se muestren de una de las siguientes formas:

   * Ve el evento en el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live event viewer</Anchor>.

   * Ve los datos del evento en <Anchor target="_blank" href="/marketers/es/docs/activity-metrics-in-my-dashboards">My Dashboards - Activity View</Anchor>.
6. Comprueba que el evento aparezca en el dashboard de actividad de AppsFlyer. En AppsFlyer, ve a **Analyze > Activity** y, en el gráfico **Activity trend**, abre la pestaña Eventos in-app y selecciona el evento que quieras probar. La compra de una suscripción autorrenovable se llama `af_ars_s2s_sandbox`. El evento incluye:
   * Un valor de ingresos 0 (para no distorsionar los reportes reales de AppsFlyer).
   * Un parámetro `af_sandbox_revenue` que incluye el valor de ingresos del producto comprado, lo que garantiza que se reporten los ingresos correctos.

</Accordion>

<div id="step-5-verify-and-update-settings" />

## Paso 5: Verifica y actualiza la configuración

Después de completar la configuración anterior y guardar el último paso, se te redirige a la vista de configuración activa, donde puedes verificar o actualizar la siguiente configuración:

1. Asegúrate de que el interruptor **Verify purchases with the App Store** esté activado.
2. Marca las siguientes opciones bajo **Compras**:
   * **Prevent duplicate purchases for clean data**: evita registrar transacciones que ya se han reportado.
   * **Automatically measure refunds, cancellations, and negative revenue**: mide los eventos relacionados con reembolsos y los registra como ingresos negativos.
   * **Avoid double-counting revenue from Family Sharing**: evita los ingresos duplicados de Family Sharing. Estos eventos se marcan con `purchase_ownership_type=FAMILY_SHARED` y reportan cero ingresos.
3. Asegúrate de que el **Measure and attribute revenue for auto-renewing subscriptions** interruptor esté activado:
4. El estado de las siguientes configuraciones:
   * La **App Store key** configuración
   * La **Server notification endpoint** configuración
   * Implementa & prueba el conector SDK

<div id="step-6-release-the-app-versions-with-the-sdk-connector" />

## Paso 6: Lanza las versiones de la aplicación con el conector del SDK

Con todos los pasos anteriores listos y el conector SDK de compra de AppsFlyer integrado en tu aplicación, dile a tu desarrollador que publique la versión de la aplicación con el conector SDK integrado.

Sin embargo, antes de que el desarrollador publique la nueva versión de la aplicación, asegúrate de que:

* Los eventos in-app que deseas capturar como compra in-app o suscripción no están bloqueados por una de las reglas de validación que has configurado en AppsFlyer.
* Tu desarrollador debe tener cualquier marca en el entorno de pruebas marcada como falsa.

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

Una vez lanzada la aplicación con el conector SDK, se generarán y estarán disponibles en todos los dashboards de AppsFlyer, así como en reportes de datos agregados y de raw data, incluidos <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">in-app purchase</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">subscription events</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports">Revenue ETL</Anchor>.

**Nota:** Sólo se generarán eventos para los usuarios que hayan actualizado a una versión de la aplicación que incluya el conector SDK. Como resultado, se espera una discrepancia entre los datos de ingresos de la aplicación y los datos de la tienda hasta que la versión actualizada de la aplicación se adopte por completo.

<div id="switch-to-roi360-store-revenue-from-receipt-validation" />

## Cambiar a los ingresos de tienda de ROI360 (desde Validación de recibos)

Si has completado el onboarding de Validación de recibos, pero quieres activar el producto ROI360 Store revenue, haz lo siguiente:

1. En AppsFlyer, desde el menú lateral, abre [<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png) **Configuración** y en **ROI360** selecciona **Configuración de ingresos**.
2. Abre la pestaña **Compras y suscripciones**. Aparece un banner que indica que ROI360 está disponible, pero no activo.
3. Haz clic en **View product comparison** para entender las ventajas, incluida la atribución de reembolsos, el reporte de ingresos netos y la medición completa del ciclo de vida de las suscripciones.
4. Haz clic en **Activate ROI360.**
5. Realiza el paso **Enable App Store Server Notification**. Para obtener más información, consulta [Configurar las notificaciones del servidor de la tienda de aplicaciones](#paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store) o [Configurar las notificaciones del servidor de Google Play](#paso-2-android-configura-las-notificaciones-del-servidor-de-google-play).
6. En la sección **Purchases & subscriptions**, verifica que el **Tipo de producto** esté ahora configurado como **ROI360**.
7. Revisa la configuración actual de tu SDK para asegurarte de que puede dar soporte a la funcionalidad de ingresos de la tienda de ROI360 Store que necesitas.

<div id="note-5" />

> 📘 **Nota:**
>
> Los ingresos de la tienda de ROI360 Store dan soporte a dos métodos de integración: Purchase SDK Connector y Validate and Log. De los dos, te recomendamos usar **Purchase SDK Connector** para beneficiarte de lo siguiente:
>
> * Detección automática de transacciones
> * Medición de ingresos de suscriptores existentes (usuarios suscritos antes de la integración)
> * Soporte para cambios en el precio de las suscripciones, lo que garantiza reportes de ingresos precisos cuando se producen actualizaciones de precios.
>
> Si no necesitas estas capacidades, puedes seguir usando la integración **Validate and Log**.
>
> **Cómo comprobar tu método de integración del SDK**
>
> Para confirmar si tu aplicación usa Purchase SDK Connector o Validate and Log:
>
> 1. Ve al PASO **Integrate SDK Connector**.
> 2. Haz clic en **Test SDK integration**. Verás cuándo recibió AppsFlyer la carga útil del SDK más reciente en los últimos 7 días y si procedía de **Purchase SDK Connector** o de **Validate and Log**.

<div data-zendesk-anchors="h_01KSAG4Y3BP0NWYNCX3AJG47JR=dos-puntos- overview=visi%C3%B3n-general h_01KD31QE0BCW0BX9BNNDK6DJRA=visi%C3%B3n-general h_01KD31QE0BQAQ0CS1FJ46TV6K1=nota step-1-ios-set-up-app-store-connect-keys=paso-1-ios-configura-las-claves-de-app-store-connect h_01KD31QE0BE3ST0TV3KQ1M5AB0=paso-1-ios-configura-las-claves-de-app-store-connect h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos h_01KD31QE0BVQNJZ8PKKYKK9Q79=paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store h_01KD31QE0CZAJ7SH2EECDJ11YN=paso-2-ios-configura-las-notificaciones-del-servidor-de-app-store option-1-recommended-appsflyer-as-the-primary-endpoint=opci%C3%B3n-1-recomendada-appsflyer-como-endpoint-principal h_01KW7HDDAQEHGY33SQ2AHWVJAC=opci%C3%B3n-1-recomendada-appsflyer-como-endpoint-principal option-2-your-endpoint-as-the-primary-endpoint=opci%C3%B3n-2-tu-endpoint-como-endpoint-principal h_01KW7HDDAQK8Z279CEG7N33FKT=opci%C3%B3n-2-tu-endpoint-como-endpoint-principal h_01_roi360_notification_types=advertencia h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=nota-1 step-2-android-set-up-google-play-server-notifications=paso-2-android-configura-las-notificaciones-del-servidor-de-google-play h_01KD31QE0CKP0PTBQ4XCT9NDE1=paso-2-android-configura-las-notificaciones-del-servidor-de-google-play h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=paso-3-implementa-el-conector-sdk h_01KD31QE0CPK1EYVT0BSYTTZFM=paso-3-implementa-el-conector-sdk h_01KD31QE0C65DQ59ZKG8V886JW=nota-2 step-4-verify-sdk-implementation=paso-4-verifica-la-implementaci%C3%B3n-del-sdk h_01KD31QE0C9KGGFVQR6HYR5AYM=paso-4-verifica-la-implementaci%C3%B3n-del-sdk h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=nota-3 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=paso-5-verifica-y-actualiza-la-configuraci%C3%B3n h_01KD31QE0DQP78QG5HRSERR5S9=paso-5-verifica-y-actualiza-la-configuraci%C3%B3n step-6-release-the-app-versions-with-the-sdk-connector=paso-6-lanza-las-versiones-de-la-aplicaci%C3%B3n-con-el-conector-del-sdk h_01KD31QE0D3HX2DEH7FQ1JR4MS=paso-6-lanza-las-versiones-de-la-aplicaci%C3%B3n-con-el-conector-del-sdk switch-to-roi360-store-revenue-from-receipt-validation=cambiar-a-los-ingresos-de-tienda-de-roi360-desde-validaci%C3%B3n-de-recibos h_01KD31QE0DJNJ8T5XSZFCACMQF=cambiar-a-los-ingresos-de-tienda-de-roi360-desde-validaci%C3%B3n-de-recibos h_01KD31QE0DX0VDXKHDZTWTYHHX=nota-4" />
