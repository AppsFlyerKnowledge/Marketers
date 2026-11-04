---
title: OneLink de marca con tu dominio
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-08-22T00:32:56Z'
  id: 360002329137
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/360002329137
---
> **At a glance:** Los anunciantes que utilicen enlaces OneLink pueden marcarlos con su propio dominio. Esto mejora el rendimiento de la campaña y aumenta la exposición de la marca.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

<div id="branded-domains" />

## Dominios de marca

* Los dominios de marca se utilizan para personalizar los enlaces de atribución con tu marca y dominio. Por ejemplo, como se muestra en la figura anterior:
  * OneLink: abcdef.onelink.me
  * Marca abcdef.com
  * Subdominio: Por ejemplo, app
  * Implementa dominios de marca y usa tu dominio completo, con el enlace de atribución click.abcdef.com
* Los dominios de marca mejoran el rendimiento de la campaña porque:
  * Impulsa la confianza: aprovecha tu marca, garantiza una identidad coherente, elimina la fricción en los viajes de los usuarios y mejora las tasas de CTR.
  * Permite deep linking utilizando tu marca.
  * Son fáciles de implementar y se comportan igual que OneLinks.
  * Promueve el reconocimiento de la marca: tu marca identifica tus campañas, en lugar de un enlace genérico.
  * Permite que los correos electrónicos eviten ser marcados como spam debido a que el enlace no coincide con el correo electrónico del remitente.
  * Los dominios de marca están incluidos en los <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing">planes de suscripción</Anchor> de pago de AppsFlyer.

<div id="principles-of-implementation" />

### Principios de implementación

Los Dominios de Marca se implementan asociando un dominio completo definido en tu Sistema de Nombres de Dominio (DNS) con un subdominio de OneLink (el destino CNAME de AppsFlyer). Esto se logra mediante la configuración estándar en tu DNS y la de un dominio de marca en AppsFlyer. Además, tendrás que realizar algunos cambios menores en tu aplicación para que sea compatible con los dominios de marca.

Necesitarás la ayuda del administrador de DNS, normalmente un miembro de tu equipo de TI o de tu proveedor de hosting DNS, y del desarrollador de la aplicación.

Se pueden asociar varios dominios completos con un solo subdominio de OneLink. Esto significa que puedes tener varias marcas utilizando el mismo subdominio OneLink.

<div id="setting-up-branded-domains" />

### Configuración de dominios de marca

Completa la lista de acciones para configurar un dominio de marca.

|  | Responsabilidad | Acción | Comentarios |
| --- | --- | --- | --- |
| 1 | Marketer asistido por el administrador de DNS | [Configurar un enlace de marca en AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | El administrador de DNS, generalmente un miembro de tu equipo de TI o de tu proveedor de alojamiento de DNS, necesita definir el dominio completo (el host) y establecer un registro CNAME como se describe en el procedimiento. |
| 2 | desarrollador | [Configurar dominios de marca en la aplicación](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Realiza cambios menores en el código de la aplicación. |
| 3 | marketer | [Uso y prueba de dominios de marca](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| Según sea necesario | marketer | [Editar y eliminar dominios de marca](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### Procedimientos

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Configurar un dominio de marca en AppsFlyer">

Configurar un Dominio de Marca consiste en asociar un dominio completo en su DNS con un subdominio OneLink en AppsFlyer como se muestra en la siguiente figura.

**Dominio de marca que apunta a los servidores de AppsFlyer**

![Diagrama de dominio de marca que apunta a los servidores de AppsFlyer](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**Antes de empezar:**

* Elige un nombre de dominio completo, por ejemplo, app.abcdef.com, donde  
  abcdef.com es tu marca. El subdominio, por ejemplo, app, también se puede personalizar.
* Solicita el administrador de DNS que cree el dominio completo (host).
* Solicita que el administrador de DNS configure un registro CNAME para que el dominio completo  
  (dominio de marca) apunte a la URL especificada (es decir, al host de AppsFlyer).  
  Esto se muestra en la figura Dominio de Marca que apunta a los servidores de AppsFlyer (arriba).

**Para asignar tu dominio completo a un subdominio de OneLink**:

1. En AppsFlyer, haz clic en **Engage** > **Branded Domains**.
2. Haz clic en **+ Nuevo dominio de marca**.
3. En el campo **Dominio de marca**, introduce tu dominio completo tal como está configurado en tu DNS. Por ejemplo, **click.abcdef.com Nota:** No pongas un punto después del dominio.
4. Selecciona el subdominio de OneLink de la lista que se muestra. Si no aparece ninguna lista,  
   debes crear una plantilla de OneLink, que proporcionará un  
   subdominio predeterminado.
5. Haz clic en **Siguiente.**
6. Establece un registro CNAME:
   * Si tu dominio apunta correctamente al destino CNAME de AppsFlyer,  
     aparece "AppsFlyer CNAME was found".
   * Si no se encuentra un CNAME, copia el destino CNAME de AppsFlyer, envíalo a tu administrador DNS y pídele que se asegure de que tu dominio completo está asignado al destino CNAME. El administrador de DNS debe asignar tu dominio completo a un destino CNAME de AppsFlyer. De lo contrario, el dominio de marca se crea pero no funciona.

     > 📘 **Note**
     >
     > **Nota:**
     >
     > El registro CNAME debe asignarse en un plazo de 7 días, a partir de la fecha de creación del dominio de marca y hasta la fecha especificada en el cuadro de diálogo de confirmación.  
     > Si el registro CNAME no está asignado en la fecha especificada, debes  
     > [renovar el periodo de 7 días](#renovar-el-plazo-de-7-días-para-asignar-el-registro-cname).

7. Haz clic en **Listo**. Ahora puedes crear nuevos enlaces basados en la plantilla de OneLink con tu dominio de marca.

   > 📘 **Note**
   >
   > **Nota:**
   >
   > * Si ya creaste enlaces basados en tu plantilla de OneLink sin el dominio de marca, seguirán funcionando.
   > * Un nuevo dominio de marca puede tardar hasta 24 horas en empezar a funcionar.


<div id="renew-the-7-day-period-for-mapping-the-cname-record" />

#### Renovar el plazo de 7 días para asignar el registro CNAME

El nuevo dominio de marca no funciona si el registro CNAME de tu dominio completo no se asigna a AppsFlyer en los 7 días siguientes a la creación de tu dominio de marca.

> 📘 **Note**
>
> **Nota:**
>
> Si el registro se asignó después de que expirara el periodo de 7 días, deberás renovar el periodo de 7 días para que el nuevo dominio de marca funcione.

**Para renovar el periodo de 7 días:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Branded Domains.**
2. Ve al dominio de marca que aún no está asignado a AppsFlyer, indicado por el icono de advertencia (![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)).
3. Haz clic en el icono de actualización (<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />) para renovar el periodo de 7 días.

> 📘 **Note**
>
> **Nota:**
>
> Puedes eliminar el dominio de marca haciendo clic en el icono Eliminar (<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />) si decides no renovar el periodo de 7 días. Solo se pueden eliminar los dominios de marca que aún no están asignados a AppsFlyer.

<div id="custom-ssl-certificate-optional" />

#### Certificado SSL personalizado (opcional)

El SSL gestionado por AppsFlyer es la opción predeterminada y recomendada para la mayoría de los clientes, y no requiere ninguna acción adicional porque AppsFlyer gestiona automáticamente la emisión y la renovación del certificado. Si tienes requisitos específicos de seguridad o cumplimiento, puedes optar por usar tu propia entidad emisora de certificados SSL (certificado SSL personalizado) en lugar del SSL gestionado por AppsFlyer. Si eliges esta opción, eres responsable de emitir, cargar, mantener y renovar el certificado. Si el certificado caduca y no se renueva a tiempo, el servicio puede verse interrumpido.

**Para usar un certificado SSL personalizado:**

1. [Crea el dominio de marca](/docs/brand-onelink-with-your-domain#configuración-de-dominios-de-marca).
2. En AppsFlyer, ve a **Engage** > **Branded domains**, pasa el cursor por encima del dominio correspondiente y selecciona el icono "Custom SSL certificate".

   <Image alt="Icono de certificado SSL Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. Rellena el formulario con los datos del certificado.

   <Image alt="rellenar el formulario para generar el archivo CSR file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="722px" />
4. Haz clic en **Download CSR** para descargar una copia del formulario que acabas de rellenar. <Image alt="Descargar archivo CSR.png" src="https://files.readme.io/9a560d19e38593fbc379efc6bdb1e636e1fa34f894dca4b46a23be30019127dd-45231892701585.png" width="254px" />
5. Proporciona el archivo CSR que acabas de descargar a la autoridad de certificación SSL que elijas.
6. Cuando recibas tu nuevo certificado SSL, vuelve a subirlo a AppsFlyer.

<Image alt="Subir nuevo certificado SSL a AppsFlyer.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

> 📘 **Note**
>
> **Nota:**
>
> Los certificados SSL caducan. Eres responsable de renovarlo y subir el certificado actualizado a AppsFlyer antes de que caduque el actual.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Configurar dominios de marca en la aplicación">

* Utiliza las siguientes versiones del SDK:
  * Android V4.10.1 y posteriores
  * iOS V4.10.1 y posteriores
  * Para invitar a un amigo se requiere la versión V5.2.0 o posterior del SDK, tanto para iOS como para Android.

**Consideraciones de implementación del SDK de dominios de marca**

* Cuando se realizan deep linking mediante dominios de marca, el SDK de AppsFlyer no puede obtener los datos de conversión para instalaciones y deep linking.
* Para superarlo, el desarrollador utiliza la API del SDK `setOneLinkCustomDomain` y `oneLinkCustomDomains` para Android e iOS, respectivamente.
* Esta API consulta el dominio de marca, obtiene el dominio OneLink al que está asignado y completa el OneLink.

<Tabs>
<Tab title="Android">

Asegúrate de actualizar el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor> del manifiesto para incluir el dominio de tu marca configurando android:host.

Utiliza esta API antes de inicializar el SDK en la <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">clase de aplicación global de Android</Anchor>

**Ejemplo**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Establece el dominio del enlace de marca. No incluyas https:// como parte del dominio. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Si tienes varios dominios de marca, transfiérelos todos a la API para asegurarte de obtener siempre los datos de conversión y de que puedas crear deep link en la aplicación.

**Ejemplo**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="apps de iOS,">

**Para asociar dominios para Universal Links de iOS:**

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#enabling-associated-domains">Configura</Anchor> el **dominio/subdominio de OneLink** como un dominio asociado en Xcode.
* Configura el **dominio de marca** como <Anchor target="_blank" href="https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains">dominio asociado</Anchor> en Xcode.
* Configura el enlace de marca para poder obtener datos de conversión. Para obtener instrucciones, haz clic en el lenguaje de programación correspondiente.

<Tabs>
<Tab title="Objective C">

Utiliza la API en AppDelegate.m, dentro del método didFinishLaunchingWithOptions:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Si tienes varios dominios de marca, transfiérelos todos a la API para asegurarte de obtener siempre los datos de conversión y de que puedas crear deep link en la aplicación.

**Ejemplo**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

La API debe usarse en AppDelegate.swift, dentro del método didFinishLaunchingWithOptions:

```swift
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions: (NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
          //...
   }
```

Si tienes varios dominios de marca, puedes pasarlos a la API como una serie de cadenas. Esto garantiza que no importa qué enlace de marca se utiliza, siempre obtendrás los datos de conversión y podrás crear deep links en la aplicación.

**Ejemplo**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Uso y prueba de dominios de marca">

**Requisitos previos**:

Antes de utilizar y probar los Dominios de Marca, completa los pasos del [workflow de Dominios de Marca](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Para crear y probar dominios de marca:**

1. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Crea un enlace de OneLink</Anchor> utilizando la plantilla de OneLink asignada al dominio de la marca.
2. Copia el enlace de atribución personalizado en un editor de texto.
3. El enlace de atribución personalizado se compone de un subdominio de OneLink, un ID de OneLink y un ID de enlace personalizado. Reemplaza el subdominio OneLink con el dominio completo del dominio de marca. Ejemplo:

| Enlace de atribución personalizado | Dominio de marca |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. Usa el enlace de marca para <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">probar las instalaciones y deep linking</Anchor>.
5. Si utilizas reportes de raw data como parte de las pruebas, el campo URL original se rellena con los enlaces de marca.

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="Editar, verificar y eliminar dominios de marca">

<div id="edit-a-branded-domain-mapping" />

#### **Editar una asignación de dominio de marca**

Puedes cambiar la asignación de un dominio completo existente a un subdominio OneLink diferente. No es necesario establecer un CNAME.

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Branded Domains.**
2. Ve al dominio de marca que deseas editar.
3. Haz clic en el icono Editar (<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />).
4. Seleccione el nuevo subdominio OneLink.
5. Haz clic en **Siguiente.** No es necesario establecer un CNAME.
6. Haz clic en **Listo**.

> 🚧 **Important**
>
> **Advertencia**
>
> La modificación de los dominios de marca de las campañas activas puede alterar o deshabilitar la funcionalidad del enlace.

<div id="verify-a-branded-domain-mapping" />

#### **Verificar la asignación de un dominio de marca**

Después de cambiar el subdominio OneLink mapeado a tu dominio de marca verifica que el dominio de marca está mapeado correctamente:

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Branded Domains.**
2. Ve al dominio de marca que deseas verificar.
3. Haz clic en el icono Verificar (<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />).

> 📘 **Note**
>
> **Nota:**
>
> Si la verificación falla porque el registro CNAME aún no se ha asignado, dispones de un plazo de hasta 7 días para hacerlo, que finalizará en la fecha especificada en el cuadro de diálogo de error de verificación.
> Si el registro CNAME no está asignado en la fecha especificada, deberás renovar el periodo de 7 días.

<div id="domain-cname-record-no-longer-pointing-to-appsflyer" />

#### **El registro CNAME del dominio ya no apunta a AppsFlyer**

Cambiar tu registro CNAME para que ya no apunte a AppsFlyer resultará en la eliminación del dominio de marca de AppsFlyer.

<div id="delete-a-branded-domain-mapping" />

#### **Eliminar una asignación de dominio de marca**

Para eliminar un dominio de marca, ponte en contacto con tu CSM de AppsFlyer o hello@appsflyer.com.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Solución de problemas, rasgos y limitaciones

<div id="troubleshooting" />

<Accordion title="Resolución de problemas">

| Síntoma | Causa/solución |
| --- | --- |
| El dominio de marca no se puede asignar a una plantilla de OneLink | <ul><li>**Nombre de dominio no válido:** Al asignar un dominio de marca a una plantilla de OneLink, AppsFlyer intenta verificar que el enlace de marca tiene un nombre de dominio válido. Un nombre de dominio válido tiene el formato click.abdef.com</li><li>**El dominio de marca ya está asignado**: Un dominio completo sólo puede asignarse una vez.</li></ul> |
| El dominio de marca no tiene deep linking en la aplicación | <ul><li>[Verifica que el dominio de marca esté operativo](#verificar-la-asignación-de-un-dominio-de-marca)</li><li>**Verificar CNAME**: Asegúrate de que un registro CNAME apunta desde tu dominio de marca a AppsFlyer.</li><li>**Verifica la configuración de deep linking para la plantilla de OneLink**: Es posible que haya un problema con la configuración de deep linking de OneLink. Asegúrate de configurar los deep linking con OneLink.</li><li>**Se ha modificado la asignación de OneLink**: Puedes editar el dominio de marca y asignarlo a un OneLink diferente. Si el OneLink recién asignado tiene diferentes configuraciones de deep linking o no tiene ninguna, es posible que los deep links no funcionen.</li></ul> |
| No hay instalaciones medidas de dominios de marca | <ul><li>**Comprueba la configuración de la plantilla de OneLink**: Asegúrate de que el subdominio de OneLink utilizado para asignar al dominio de marca está asociado a las aplicaciones correctas.</li><li>**Subdominio OneLink cambiado:** Si asignas un dominio de marca a una plantilla de OneLink y el subdominio de OneLink cambia, podría afectar a la atribución.</li><li>**Asegúrate de implementar:** la API setOneLinkCustomDomain en la aplicación.</li></ul> |
| No se han registrado re-engagements de dominios de marca | Asegúrate de que lo siguiente esté activo y configurado:<ul><li><Anchor target="_blank" href="/marketers/es/docs/onelink-guide#configuración-de-onelink">Configura deep linking con OneLink</Anchor>.</li><li>La aplicación utiliza la [API específica del SDK setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer).</li><li><Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#retargeting-settings">El retargeting está habilitado en la configuración de la aplicación</Anchor>.</li></ul> |
| Durante la configuración del dominio de marca, se muestra el mensaje **El dominio no existe** | <ol><li>Contacta con tu administrador de DNS y pídele que investigue.</li><li>Espera a que el administrador de DNS confirme que el dominio está registrado.</li><li>Haz clic en **Volver a verificar**.</li></ol> |
| Durante la configuración del dominio de marca, se muestra el mensaje **No se encontró el CNAME de AppsFlyer**. | <ol><li>Solicita que el administrador de DNS establezca un registro CNAME de modo que el dominio completo (dominio de marca) apunta a la URL especificada (es decir al host de AppsFlyer). Esto se representa en la figura Enlace de Marca apuntando a los servidores de AppsFlyer en esta sección.</li><li>Espera a que el administrador de DNS confirme que el CNAME está activo.</li></ol> |
| **Mensaje de bloqueo** al cargar una página de dominio de marca | Los dominios de marca no incluyen la plantilla ni ningún parámetro. Al usar un dominio de marca, debes agregar la plantilla o los parámetros al final de la URL del dominio de marca.<br /><br />Por ejemplo, si "click.abcdef.com" es tu dominio de marca, si utilizas sólo "**click.abcdef.com"**, aparecerá un mensaje de que **has sido bloqueado**.<br /><br />Debes agregar los parámetros o plantillas al final. Por ejemplo, click.abcdef.com **/A1bc/dc1234ef** |
| Error **err\_cert\_authority\_invalid** al cargar la página de un dominio de marca | Este error indica que tu dominio de marca carece de un certificado HTTPS válido porque no se reconoce la autoridad de certificación. Dado que AppsFlyer certifica tus dominios de marca con Let's Encrypt, es probable que el error se deba a que Let's Encrypt no se reconoce como una Autoridad de certificación (CA) válida de acuerdo con los registros DNS CAA (Autorización de la autoridad de certificación) de tu dominio.<br /><br />**Solución**<br />Por favor, realiza lo siguiente:<ol><li>Determina si tu dominio reconoce Let's Encrypt como CA usando servicios como <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">este</Anchor>.</li><li>Pide a los administradores del sistema que actualicen los registros CAA de tu dominio para incluir Let's Encrypt como una CA autorizada.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Sí ✓ / No **x** | Observaciones |
| --- | --- | --- |
| Acceso de usuario a la cuenta | ✓ |  |
| Acceso a ad network | **x** |  |
| Acceso a la agencia | . | Las agencias no pueden crear dominios de marca (o enlaces OneLink). |
| Transparencia de la agencia | . |  |
| Moneda específica de la aplicación | No aplica |  |
| Zona horaria específica de la aplicación | No aplica |  |
| Disponibilidad de dominios de marca | N/D | Los dominios de marca solo están disponibles con planes de pago elegibles. Si tu plan de suscripción caduca o se cancela, se elimina el acceso a los dominios de marca y los enlaces existentes que utilizan tus dominios de marca dejarán de funcionar. |
| Limitación de caracteres | N/D | Cuando introduzcas tu dominio de marca, el último carácter no puede ser un punto ("."). |
| Actualización de datos | N/D |  |
| Datos históricos | ✓ |  |
| HTTP | . | El protocolo HTTP no es compatible con los enlaces de marca. Se debe utilizar HTTPS. |
| Datos no orgánicos | ✓ |  |
| Datos orgánicos | ✓ |  |
| Limitación de la tasa | ✓ | AppsFlyer organiza los certificados SSL/HTTP de dominios de marca mediante <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, con un límite de frecuencia de 50 nuevos certificados por semana por dominio. |
| Limitaciones de tamaño | N/D |  |
| Renovación de certificados SSL/HTTP | ✓ | Tus certificados SSL/HTTP de dominio de marca gestionados por AppsFlyer se renuevan automáticamente sin que se requiera ninguna acción de tu parte. |

</Accordion>

<div data-zendesk-anchors="branded-domains=dominios-de-marca h_01HFM51V4PE53FQAED68V8Q834=dominios-de-marca principles-of-implementation=principios-de-implementaci%C3%B3n h_01HFM51V4PPJXMCSV5ZVDPT49M=principios-de-implementaci%C3%B3n setting-up-branded-domains=configuraci%C3%B3n-de-dominios-de-marca h_01HFM51V4PH58ZA4ZXHP5J6K2W=configuraci%C3%B3n-de-dominios-de-marca procedures=procedimientos h_01HFM51V4PWWX7TBCHFMPR3QVB=procedimientos h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer renew-the-day=renovar-el-plazo-de-7-d%C3%ADas-para-asignar-el-registro-cname h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=renovar-el-plazo-de-7-d%C3%ADas-para-asignar-el-registro-cname custom-ssl-certificate=certificado-ssl-personalizado-opcional h_01KM0E8VHARA2JRAR2H37QM91Y=certificado-ssl-personalizado-opcional h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=editar-una-asignaci%C3%B3n-de-dominio-de-marca h_01HQ5FJZD6QMNFA45Z2C7CA3ST=editar-una-asignaci%C3%B3n-de-dominio-de-marca verify-a-branded-domain-mapping=verificar-la-asignaci%C3%B3n-de-un-dominio-de-marca h_01HQ5FK5XJNZ1EABJA66RMYBCN=verificar-la-asignaci%C3%B3n-de-un-dominio-de-marca domain-cname-record-no-longer-pointing-to-appsflyer=el-registro-cname-del-dominio-ya-no-apunta-a-appsflyer h_01JSHFECXS00M6BXH8168ZWJE5=el-registro-cname-del-dominio-ya-no-apunta-a-appsflyer delete-a-branded-domain-mapping=eliminar-una-asignaci%C3%B3n-de-dominio-de-marca h_01JSHF5RMXXFJTXC246KKAQBSS=eliminar-una-asignaci%C3%B3n-de-dominio-de-marca troubleshooting-traits-and-limitations=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones h_01HFM51V4PH4YM13DVXENRWF2E=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
