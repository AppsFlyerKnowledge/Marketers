---
title: Configurar la validación de recibos
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-10-25T01:10:17Z'
  id: 42137474889489
  locale: es
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/es/articles/42137474889489
---
> **En resumen:** La Validación de recibos mide los ingresos de las compras in-app y las suscripciones, y los verifica con las tiendas de aplicaciones, lo que garantiza resultados precisos de Retorno de la inversión publicitaria (ROAS).

<div id="upgrade-to-new-receipt-validation" />

## Actualizar a la nueva validación de recibos

La validación de recibos heredada se desactivará el **7 de septiembre de 2026**; consulta el <Anchor target="_blank" href="/marketers/es/docs/bulletin-legacy-receipt-validation-is-deprecated">Boletín: La validación de recibos heredada está obsoleta</Anchor>. Si tu aplicación usa la validación de recibos heredada, migra a la nueva siguiendo los pasos de configuración que se indican a continuación. Antes de empezar, revisa las diferencias principales y prepara la migración.

<div id="h_migration_key_differences" />

<Accordion title="Novedades en la validación de recibos">

| Área | Heredado | Nueva validación de recibos |
| --- | --- | --- |
| Método del SDK | `validateAndLogInAppPurchase` (legacy/v1) | `validateAndLogInAppPurchase` (v2), mismo nombre y nueva firma en iOS y Android |
| Entrada de precio y moneda | Se pasa en la llamada del SDK | Se extrae automáticamente de la tienda |
| Tipo de compra | No es obligatorio | Parámetro `PurchaseType` obligatorio (*subscription* o *one-time purchase*) |
| Configuración de ingresos | No es obligatorio | Obligatorio (página de configuración de ingresos) |
| Fuente del valor de `af_revenue` | Valor pasado en la llamada del SDK | Valor bruto devuelto por la tienda; cualquier valor personalizado que se pase en la llamada del SDK llega al objeto `custom_data` del evento |
| Granularidad del evento de compra | Un único evento `af_purchase` para todos los tipos de transacción | Eventos distintos por tipo de transacción: `af_purchase`, `af_ars_trial_started`, `af_ars_subscription_started` y variantes de sandbox |
| Soporte de StoreKit 2 (iOS) | No compatible | Compatible |
| Filtrado de fraude | Limitado | Mejorado en Android e iOS |
| Disponibilidad del SDK | Eliminado del SDK de AppsFlyer v7.0.0+ | Disponible a partir de Android v6.17.5, iOS v6.17.8 y plugins v6.17.8 |
| Registro validado del evento de compra | Con soporte hasta el 7 de septiembre de 2026 | En curso |

</Accordion>

<div id="h_migration_what_to_plan" />

<Accordion title="Prepara la migración">

Antes de iniciar la migración, revisa las siguientes consideraciones:

* **Migra gradualmente sin afectar a los usuarios existentes.** Activar la nueva validación de recibos en el dashboard de AppsFlyer no afecta a las versiones de la aplicación que siguen usando el método heredado. Ambos siguen funcionando hasta la retirada del sistema heredado el 7 de septiembre de 2026.
* **Espera cambios en los ingresos después de la migración.** La nueva Validación de recibos usa el valor bruto que devuelve la tienda, mientras que la Validación de recibos heredada usaba el valor de ingresos enviado en la llamada al SDK. Si la llamada al SDK enviaba un valor no bruto, los dashboards y los postbacks de partners, que ahora reflejan valores brutos, mostrarán una cifra distinta después de la migración. Para los ingresos netos, usa **ROI360 Store Revenue**. Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue">Configurar ROI360 store revenue</Anchor>.
* **Informa a tus partners de UA sobre el cambio en los ingresos.** Las ad networks que antes procesaban ingresos no brutos del postback `af_purchase` verán valores distintos después de la migración.
* **Planifica el cronograma de lanzamiento de tu aplicación.** Después del 7 de septiembre de 2026, los usuarios que tengan versiones de la aplicación compiladas con versiones del SDK anteriores a Android v6.17.5 o iOS v6.17.8 dejarán de generar eventos `af_purchase` validados. Lanza la nueva versión de tu aplicación con suficiente antelación para llegar a la mayoría de tu base de usuarios antes de la descontinuación.

</Accordion>

<div id="h_migration_upgrade_path" />

<Accordion title="Cámbiate a ROI360 Store Revenue">

Cambiar a ROI360 Store Revenue no requiere ningún cambio en el SDK, ya que ambos productos usan el mismo método `validateAndLogInAppPurchase` (v2). Añadir el Purchase Connector para la detección automática de compras es opcional.

Para obtener más información e instrucciones de configuración, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue">Configurar los ingresos de la tienda en ROI360</Anchor>.

</Accordion>

<div id="overview" />

## Visión general

<div id="note" />

> 📘 **Nota:**
>
> Para obtener más información sobre la Validación de recibos, incluido cómo funciona y cómo activarla en AppsFlyer, consulta <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation">Acerca de la Validación de recibos</Anchor>.

Para configurar la Validación de recibos, sigue estos pasos en este orden:

1. Configurar las credenciales de la tienda (iOS y Android)
   * [iOS](#paso-1-ios-configurar-las-claves-de-app-store-connect): Configura las claves de App Store Connect (clave de In-App Purchase, ID de clave e ID del emisor) en AppsFlyer para activar la Validación de recibos.
   * [Android](#paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos): Configura una cuenta de servicio de Google Cloud, define los permisos necesarios en Google Play Console y sube la clave JSON de la cuenta de servicio a AppsFlyer.
2. [Implementar la API del SDK validateAndLog](#2-implementar-sdk): Prepara a los desarrolladores para integrar la API del SDK `validateAndLog` de AppsFlyer y configurar el entorno sandbox para las pruebas.
3. [Probar la implementación de la API del SDK validateAndLog](#3-verificar-la-implementación-del-sdk): Realiza compras y suscripciones de prueba en el entorno sandbox en iOS y Android para verificar que se generan los eventos de Validación de recibos y que AppsFlyer los registra correctamente.
4. [Verificar y actualizar la configuración](#4-verifica-y-actualiza-los-ajustes): Confirma que el tipo de producto esté configurado como Validación de recibos y revisa los estados de la clave de la tienda y de la integración del SDK para garantizar una medición precisa y continua de los ingresos.
5. [Lanzar las versiones de la aplicación con la API del SDK validateAndLog](#paso-5-lanza-las-versiones-de-la-aplicación-con-la-api-validateandlog-del-sdk): Lanza versiones actualizadas de la aplicación con la API del SDK `validateAndLog` integrada, asegurándote de que las marcas de sandbox estén desactivadas y de que los eventos in-app obligatorios no estén bloqueados por las reglas de validación.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## Paso 1 (iOS): Configurar las claves de App Store Connect

En el paso 1, obtén las siguientes credenciales de *App Store Connect* e introdúcelas en la página de **Configuración de ingresos** de la plataforma de AppsFlyer.

* Clave de compra in-app
* ID de clave
* ID del emisor

**Antes de empezar**:

* La configuración de las credenciales implica pasos realizados tanto en App Store Connect como en AppsFlyer. Durante la configuración, mantén abiertas las pestañas App Store Connect y AppsFlyer.
* Tu aplicación de iOS requiere StoreKit v1 o v2, que proporciona el framework para gestionar las compras y suscripciones in-app.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Crear las claves de App Store Connect">

Para configurar las credenciales de iOS, sigue estos pasos:

1. En App Store Connect, ve a **Usuarios y acceso**.

   <Image align="center" alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" />
2. Ve a **Usuarios y acceso** > **Integraciones** y, en la lista de **Claves** , selecciona **Compra in-app**.

   <Image align="center" alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" />
3. Haz clic en + para generar una nueva clave de compra in-app.

   <Image align="center" alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" />
4. Ingresa un nombre para tu clave de API.
5. Haz clic en **Generar**.
6. Haz clic en **Descargar clave de compra in-app** junto a la clave que acabas de generar para descargarla. **Nota**: Solo puedes descargar la clave una vez.
7. Copia el **ID de clave** de la clave que acabas de generar y pégalo en la configuración de compras y suscripciones de AppsFlyer & para **ID de clave**.

   <Image align="center" alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" />
8. Copia el **ID del emisor**. **Nota**: Si el **ID del emisor** no se muestra en la parte superior de la página, crea una clave de API de App Store Connect (con cualquier nivel de acceso). Después de eso, el ID del emisor aparece en la parte superior de la página para la clave de compra in-app.

   <Image align="center" alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" />

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 Configurar la clave de App Store Connect">

1. Habilita la Validación de recibos. #habilitar-validación-de-recibo
2. En el paso **App Store Connect keys** , haz clic en <Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />  **Upload** en el campo **In-App Purchase key** para cargar el archivo p8.
3. En la sección titulada **Claves de App Store Connect keys**, pega los valores que copiaste de App Store Connect.

   * **ID de clave**
   * **ID del emisor**
4. Haz clic **Validar claves** para asegurarte de que las claves que has introducido sean correctas. **Nota**: La acción **Validar claves** puede no funcionar si tu app aún no se ha publicado en la App Store.
5. Haz clic en **Guardar y Siguiente**.

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## Paso 1 (Android). Configurar la clave de cuenta de servicio y los permisos

En el paso 1, obtén las siguientes credenciales de *Google Play* y *Google Cloud* y e introdúcelas en la página de **Configuración de ingresos** de la plataforma de AppsFlyer.

**Antes de empezar**:

* La configuración de la medición de las compras in-app y de los ingresos por suscripción implica pasos que se realizan en la <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console,</Anchor> y la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">interfaz de usuario de AppsFlyer</Anchor>. Te recomendamos que mantengas un control de los tres lugares abiertos durante toda la configuración.
* La configuración en la interfaz de usuario de AppsFlyer requiere permisos de administrador.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 Vincula tu cuenta de desarrollador de Google Play a tu proyecto de Google Cloud">

**Requisitos previos**: acceso a Google Play Console y a un proyecto de Google Cloud.

**Para vincular tu cuenta de desarrollador de Google Play a tu proyecto de Google Cloud, sigue estos pasos**:

1. En Google Play Console, ve a tu cuenta de desarrollador de Google Play.
2. Vincula la cuenta a tu proyecto de Google Cloud. Para obtener instrucciones, consulta este <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">tema de ayuda de Google</Anchor>.
3. Habilita la API para desarrolladores de Google Play. Para obtener instrucciones, consulta <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">este tema de ayuda de Google</Anchor>.

   <Image align="center" alt="" src="https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png" />

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2 Configura tu cuenta de servicio en Google Cloud Platform">

**Requisitos previos**: acceso a Google Cloud Platform.

**Para configurar tu cuenta de servicio, sigue estos pasos**:

1. Crea o localiza la **cuenta de servicio**:

   1. <span class="af-ol-a"></span>Ve a la sección **Cuentas de servicio** de Google Cloud platform y haz clic **CREATE SERVICE ACCOUNT**.[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Rellena los datos de la cuenta de servicio.[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Copia la dirección de correo electrónico.[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Haz clic en **Create and continue**.[![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. En el paso **Otorgar a esta cuenta de servicio acceso al proyecto** , selecciona el rol de **Pub/Sub** suscriptor.[![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Haz clic **Continuar** > **Hecho**.

      <Image align="center" alt="" src="https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png" />
2. Descarga la clave privada de la cuenta de servicio:

   1. <span class="af-ol-a"></span>En Google Cloud platform, ve a la sección **Cuentas de servicio** , busca en la lista la cuenta que quieres (la que acabas de crear) y haz clic en el icono **More actions** .
   2. Haz clic en **Manage keys**.[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Haz clic en **Agregar clave** > **Crear nueva clave**.

      <Image align="center" alt="" src="https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png" />
   4. En la ventana emergente **Crear clave privada** para **Tipo de clave**, selecciona **JSON**, y haz clic **Crear**.[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Haz clic **Crear**. Se descarga el archivo JSON de la clave privada.

      <Image align="center" alt="" src="https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png" />
   6. Guarda el archivo de clave JSON, que se cargará en AppsFlyer más tarde.   
      [Práctica recomendada]: Debes guardar la clave. no se podrá recuperar más adelante. Si no la guardas, tendrás que crear una clave completamente nueva.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3 Establecer permisos de acceso a la API en Google Play Console">

**Requisitos previos**: acceso a Google Play Console.

**Nota**: Puede llevar un tiempo (a veces hasta 24 horas) después de configurar las credenciales y los permisos de la cuenta de servicio hasta poder utilizarlos. Esto puede provocar errores en pasos posteriores.

**Para establecer permisos de acceso a la API en Google Play Console**:

1. En Google Play Console, ve a **Usuarios y permisos**, busca la cuenta de servicio que has creado y haz clic **Invitar a nuevos usuarios**.

   <Image align="center" alt="" src="https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png" />
2. Introduce la **dirección de correo electrónico** que copiaste al configurar tu cuenta de servicio en el paso 1.2.1.3.

   <Image align="center" alt="" src="https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png" />
3. En la sección **Permisos** , ve a la pestaña **Permisos de cuenta** y selecciona ambas opciones:

   * Ver los datos financieros, los pedidos y las respuestas a la encuesta de cancelación.
   * Gestionar los pedidos y las suscripciones.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. En la pestaña **Permisos de la aplicación** , haz clic en **Agregar aplicación,** luego selecciona tu aplicación. Agrega varias aplicaciones si es necesario.

   <Image align="center" alt="" src="https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png" />
5. Haz clic **Invitar al usuario**.

   <Image align="center" alt="" src="https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png" />
6. En la ventana emergente de confirmación, haz clic **Enviar invitación**.

   <Image align="center" alt="" src="https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png" />

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4 Cargar la clave privada de la cuenta de servicio en AppsFlyer">

Carga y valida la clave JSON de Google que descargaste en [el paso 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Requisitos previos**: acceso de administrador a AppsFlyer.

**Para cargar la clave privada de la cuenta de servicio en AppsFlyer, sigue estos pasos**:

1. <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation#activar-la-validación-de-recibos">Activar la validación de recibos</Anchor><Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation#activar-la-validación-de-recibos">.</Anchor>
2. En el paso **Service Account Key and Permissions**, en el campo **Upload Google JSON key** , haz clic [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload**.
3. Carga el archivo JSON que descargaste en [el paso 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Haz clic **Validar clave**. **Nota:**

   * Después de configurar las credenciales y los permisos de la cuenta de servicio, puede pasar algún tiempo (a veces incluso 24 horas) hasta que se puedan utilizar. Esto puede hacer que recibas errores al intentar validar la clave o realizar una prueba de validación.
   * Para evitar el tiempo de espera de 24 horas, en la Google Play Console, ve a cualquier aplicación, luego ve a **Monetize** > **Products** > **Subscriptions/In-app products**, y realiza un cambio. Por ejemplo, edita la descripción de tu producto y guárdalo. Esto suele actualizar inmediatamente las credenciales y los permisos de la cuenta. Luego puedes deshacer los cambios.
5. Haz clic **Siguiente**. Se abre el paso **Implementación del SDK**.

</Accordion>

<div id="step-2-implement-sdk" />

## 2. Implementar SDK

En este paso, preparas a tus desarrolladores para integrar la API `validateAndLog` del SDK y configurar un entorno sandbox para las pruebas. Las versiones mínimas del SDK que dan soporte a la API `validateAndLog` más reciente son **6.17.5** para Android y **6.17.8** para iOS.

Para implementar la API validateAndLog del SDK, sigue estos pasos:

1. En el paso **Implementación del SDK**, copia el **mensaje predefinido** que se muestra en el dashboard.
2. Envíalo a tus desarrolladores. incluye:

   * El nombre y el ID de aplicación
   * Un enlace a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">la guía de integración del SDK</Anchor>.
   * Instrucciones para configurar el entorno sandbox (`sandbox = true`).
   * Pasos de prueba (con **TestFlight**).

   Este mensaje proporciona toda la información que tus desarrolladores necesitan para completar la integración y comenzar las pruebas.
3. Haz clic **Siguiente**. Se abre el paso **Verificar implementación del SDK**.

<div id="step-3-verify-sdk-implementation" />

## 3. Verificar la implementación del SDK

Prueba la integración de ingresos por compras in-app y suscripciones en un entorno sandbox para confirmar que el conector del SDK está correctamente integrado y que las notificaciones del Servidor están correctamente configuradas y son recibidas por AppsFlyer.

<div id="test-sdk-implementation" />

<Accordion title="Prueba de implementación de SDK">

Para comprobar si AppsFlyer ha recibido payloads válidos de `validateAndLog` de tu App en los últimos 7 días, realiza estos pasos:

1. En el paso **Verificar implementación del SDK**, haz clic en **Probar implementación del SDK**.
2. Revisa los resultados, incluida la marca de tiempo del payload más reciente que ha recibido AppsFlyer. Ten en cuenta que esta comprobación solo confirma que las solicitudes llegan a AppsFlyer y no verifica si los datos están completos o son correctos.
3. Para validar completamente la implementación, continúa con los pasos de prueba que se indican a continuación.

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="Consideraciones sobre el entorno de pruebas">

En un entorno de pruebas:

* Solo los eventos de compra iniciales hacen que la API validateAndLog del SDK produzca un evento que es registrado por AppsFlyer. Un evento de compra in-app se llama `af_purchase_sandbox_sdk`. Un evento de suscripción se llama `af_ars_sandbox_sdk`.
* Los eventos de Sandbox tienen ingresos de 0.
* Para Android, las pruebas realizadas por License Testers dan como resultado eventos sandbox aunque el entorno sandbox no esté configurado en el SDK.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Probar las compras in-app y los ingresos por suscripciones">

<Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" />

**Para probar los ingresos por compras in-app y suscripciones**:

1. Pide a tus desarrolladores que sigan sus instrucciones para configurar el entorno sandbox para la API validateAndLog del SDK.
2. Haz una compra o suscripción de prueba con <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester en Google Play</Anchor> y <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight en iOS</Anchor>.
3. Verifica que los eventos de prueba se muestren de una de las siguientes maneras:

   * Consulta el evento en el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live Event Viewer.</Anchor>
   * Consulta los datos del evento en <Anchor target="_blank" href="/marketers/es/docs/activity-metrics-in-my-dashboards">My Dashboards - Activity View</Anchor>.
4. Busca los siguientes eventos de prueba:

   * El `af_purchase_sandbox_sdk` para un evento de compra.
   * El `af_ars_sandbox_sdk` para un evento de suscripción.
5. Asegúrate de que los eventos de prueba incluyan lo siguiente:

   * Un valor de ingresos de **0** (para no distorsionar los reportes reales de AppsFlyer).
   * Un `af_sandbox_revenue` parámetro que incluye el valor de ingresos del producto comprado, garantizando que se reporten los ingresos correctos.
   * Un parámetro `af_validated` con el valor `true`. Si `af_validated` es `false`, vuelve al paso 2 anterior y valida la clave proporcionada por la tienda
   * Un parámetro `af_validation_type` con el valor `receipt_validation`.

</Accordion>

<div id="step-4-verify-and-update-settings" />

## 4. Verifica y actualiza los ajustes

Después de completar la configuración de los ajustes anteriores y guardar los pasos anteriores, se te redirige a la vista de configuración activa, donde puedes verificar o actualizar los siguientes ajustes:

1. Verifica que el **Tipo de producto** sea **Validación de recibos**
2. Asegúrate de que **Verify purchases with the App Store** esté activado.
3. Verifica o actualiza los siguientes ajustes:

   * La configuración de la **App Store key**
   * La **configuración de la integración del SDK** setup

<div id="step-5-release-the-app-versions-with-the-validateandlog-sdk-api" />

## Paso 5. Lanza las versiones de la aplicación con la API validateAndLog del SDK

Con todo lo de los pasos anteriores configurado y la API validateAndLog del SDK de AppsFlyer integrada en tu aplicación, indica a tus desarrolladores que publiquen la versión de la aplicación con la API validateAndLog del SDK integrada.

Antes de que los desarrolladores publiquen la nueva versión de la aplicación, asegúrate de que:

* Los eventos in-app que quieres capturar como <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation#eventos-y-parámetros-de-compra-in-app-para-la-validación-de-recibos">compra in-app o suscripción</Anchor> no están bloqueados por ninguna de las reglas de validación que has configurado en AppsFlyer.
* Tus desarrolladores tienen todas las marcas de sandbox configuradas como `false`.

<Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />

Una vez que se lance la aplicación con la API validateAndLog del SDK, <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation#eventos-y-parámetros-de-compra-in-app-para-la-validación-de-recibos">los eventos de compra in-app y de suscripción</Anchor> se generarán y estarán disponibles en todos los dashboards de AppsFlyer, así como en los reportes de datos agregados y de raw data.

Los eventos solo se generan para los usuarios que han actualizado a una versión de la aplicación que incluye la API validateAndLog del SDK. Como resultado, es normal que haya una discrepancia entre los datos de ingresos de la aplicación y los datos de la tienda hasta que la versión actualizada de la aplicación se adopte por completo.

<div data-zendesk-anchors="h_migrating-from-legacy=actualizar-a-la-nueva-validaci%C3%B3n-de-recibos upgrade-to-new-receipt-validation=actualizar-a-la-nueva-validaci%C3%B3n-de-recibos whats-new-in-receipt-validation=h_migration_key_differences prepare-the-migration=h_migration_what_to_plan switch-to-roi360-store-revenue=h_migration_upgrade_path overview=visi%C3%B3n-general h_01KD0RY1HMV71TGDZZX7JWM3XJ=visi%C3%B3n-general h_01KD0RY1HMMSR4ZDW5GF4N05P1=nota step-1-ios-set-up-app-store-connect-keys=paso-1-ios-configurar-las-claves-de-app-store-connect h_01KD0RY1HM14KNGKADCBMHJXH6=paso-1-ios-configurar-las-claves-de-app-store-connect h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos h_01KD0RY1HMG9DGKGEY8XVR3K7Z=paso-1-android-configurar-la-clave-de-cuenta-de-servicio-y-los-permisos h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=2-implementar-sdk h_01KD0RY1HN63X3WM1RH19W2HZ5=2-implementar-sdk step-3-verify-sdk-implementation=3-verificar-la-implementaci%C3%B3n-del-sdk h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=3-verificar-la-implementaci%C3%B3n-del-sdk h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=4-verifica-y-actualiza-los-ajustes h_01KD0RY1HN2HZEW9ANBPNRMXPP=4-verifica-y-actualiza-los-ajustes step-5-release-the-app-versions-with-the-validateandlog-sdk-api=paso-5-lanza-las-versiones-de-la-aplicaci%C3%B3n-con-la-api-validateandlog-del-sdk h_01KD0RY1HNECTDNNHK78F9KDPS=paso-5-lanza-las-versiones-de-la-aplicaci%C3%B3n-con-la-api-validateandlog-del-sdk" />
