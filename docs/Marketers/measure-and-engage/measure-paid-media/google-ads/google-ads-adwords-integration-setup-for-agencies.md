---
title: Integración de Google Ads para agencias
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-09-17T00:27:16Z'
  id: 115003669983
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/115003669983
---
> **De un vistazo:** Configurar la integración de Google Ads con AppsFlyer, como agencia.

Tanto los anunciantes como las agencias deben configurar activamente el sistema. El siguiente video muestra los pasos requeridos por el anunciante y la agencia para permitir que la agencia mida y atribuya el tráfico móvil a la aplicación del anunciante mediante Google Ads.

La configuración permite a AppsFlyer atribuir conversiones a una agencia desde el panel de control de AppsFlyer.

Antes de que la agencia pueda comenzar el proceso, el anunciante primero debe configurar la integración de Google Ads. Para más detalles, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">aquí</Anchor>.

<div id="enabling-agency-attribution-of-google-ads" />

## Habilitación de la atribución de Google Ads a las agencias

AppsFlyer admite las configuraciones de agencias con Google Ads. Es esencial que el anunciante y la agencia tengan cuentas separadas de Google Ads para permitir que AppsFlyer atribuya los datos correctamente.

<div id="setting-up-google-ads-attribution-for-agencies" />

## Configurar la atribución de Google Ads para agencias

Para iniciar la atribución a agencias de campañas de Google Ads con AppsFlyer, sigue estos pasos:

<Accordion title="Ver">

<Embed title="Integración de Google Ads para agencias" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Leer">

<div id="advertiser-prestep-enabling-the-agency-access-to-google-ads" />

<Accordion title="Paso previo del anunciante: permitir que la agencia acceda a Google Ads">

**Requisitos previos:**

* En AppsFlyer, otorga a la agencia acceso a la aplicación siguiendo las instrucciones <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">aquí</Anchor>.
* En AppsFlyer, <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">activa</Anchor> el partner de Google Ads.

**Para compartir el ID de enlace del anunciante:**

1. En Google, ve al panel de control de Google Ads, haz clic en el ícono ***Tools (Herramientas)***

<Image align="center" alt="Google_Ag_1.png" src="https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png" />

2. Selecciona ***Cuentas vinculadas***.

<Image align="center" alt="Google_Ag_2.png" src="https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png" />

3. En App Analytics Provider (Proveedor de analíticas de aplicaciones), busca AppsFlyer. Selecciona Options (Opciones).

4. Haz clic en ***Share with another account (Compartir con otra cuenta)***.

<Image align="center" alt="Google_Ag_3.png" src="https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png" />

5. Inserta el **ID de cliente de Google Ads de la agencia.**

<Image align="center" alt="Google_Ag_4.png" src="https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png" />

6. Haz clic en ***Siguiente***. Haz clic en ***Enviar invitación***.Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

<Image align="center" alt="Google_Ag_5.png" src="https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png" />

El anunciante ahora puede ver que la solicitud de invitación se ha enviado a la Agencia. Cuando la agencia acepta la invitación, el estado cambia a Sharing (Compartiendo).

Para obtener más información sobre cómo compartir tu ID de enlace de Google Ads, haz clic <Anchor target="_blank" href="https://support.google.com/adwords/answer/7365001">aquí</Anchor>.

<Image align="center" alt="Google_Ag_6.png" src="https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png" />

</Accordion>

<div id="agency-step-1-accepting-the-link-id" />

<Accordion title="Paso 1 de la agencia: aceptar el ID del enlace">

En el panel de control de Google Ads Words, la agencia recibe una invitación y debe aceptar el enlace.

<Image align="center" alt="Google_Ag_7.png" src="https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png" />

La agencia puede ver que el estado del enlace ahora está activo.

<Image align="center" alt="Google_ag_8.png" src="https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png" />

</Accordion>

<div id="agency-step-2-setting-up-google-ads-on-appsflyer" />

<Accordion title="Paso 2 de la agencia: configurar Google Ads en AppsFlyer">

Una agencia puede configurar varios ID de cliente de Google Ads, si es necesario.

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners**.
2. Busca y selecciona **Google Ads**.

   <Image align="center" alt="gads-search.png" src="https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png" />

   ***Activar partner*** debe estar ACTIVADO y el ***ID de enlace*** definido por el anunciante. Estas configuraciones están en gris para la agencia.

   <Image align="center" alt="gads_agency-integration-link-id.png" src="https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png" />
3. La Agencia establece su ID de cliente de Google Ads.

   Ingresa **todos** los ID de cliente de Google Ads (**subcuentas**) de las cuentas de Google Ads en las que la agencia ejecuta campañas para la aplicación del anunciante.

   Puedes encontrar el ID de cliente de Google Ads haciendo clic en la flecha en la esquina superior izquierda y abriendo así el Panel de navegación.

   <Image align="center" alt="" src="https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png" />
4. Para medir la ejecución de campañas de retargeting en Google Ads, solicita al anunciante que active **Google Ads Retargeting**. Una vez hecho esto, puedes configurar la **ventana de re-engagement**.

   <Image align="center" alt="gads-agency-retargeting.png" src="https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png" />
5. Te recomendamos configurar la ventana de ***atribución retrospectiva por clics*** en **30 días** para que coincida con el valor de Google Ads.

   <Image align="center" alt="gads-click-through.png" src="https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png" />
6. Para el caso de la atribución por impresiones, se recomienda **1 día** para que coincida con el valor de Google Ads. La escala te permite personalizar la cantidad de horas o días después de visualizar un anuncio, período durante el cual se puede atribuir la impresión a este partner.

   <Image align="center" alt="gads-view-through.png" src="https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png" />
7. ***Atribución de reinstalaciones***:
   * Para habilitar la atribución de reinstalaciones, actívala.
   * No es necesario activar la atribución por impresiones o configurar ventanas retrospectivas para la atribución de reinstalaciones, ya que los valores se toman de la configuración de atribución de instalaciones.
8. Haz clic en ***Guardar & cerrar***.

</Accordion>

<div id="agency-step-3-mapping-your-inapp-events" />

<Accordion title="Paso 3 de la agencia: asignación de tus eventos in-app">

1. Haz clic en la pestaña **Eventos in-app**.

2. Selecciona enviar eventos in-app desde solo instalaciones de Google Ads o desde todos los eventos in-app a Google Ads.  
<Image align="center" alt="" src="https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png" />

3. Asigna todos los eventos in-app que deseas enviar a Google Ads, con los eventos predefinidos de Google Ads.

<Image align="center" alt="" src="https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png" />

4. Haz clic en ***Guardar***.

<div id="important" />

> 🚧 **¡Importante!**
>
> Importa las acciones de primera apertura e in-app a Google Ads para comenzar a contar las conversiones tanto en Google Ads como en tu panel de control de AppsFlyer.
>
> Para poder importar, debes iniciar la aplicación y realizar los eventos in-app asignados al menos una vez.

<div id="note" />

> 📘 **Nota**
>
> * Puede tardar hasta 6 horas en cambiar el estado de las nuevas conversiones de sin conversión reciente a registrando conversión.
> * Si una agencia trabaja con una cuenta de MCC y la aplicación se promociona a través de varias subcuentas de MCC, todas las subcuentas deben configurarse en el campo de **ID de cliente de Google Ads** (como se ve en la captura de pantalla anterior).
>   En tal caso, no es necesario configurar el ID del cliente de la cuenta de MCC.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Paso 4 de la agencia: medir las conversiones de tu aplicación (obligatorio)">

(**Solo para administradores de Google Ads** )

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Para que Google Ads registre tus conversiones nuevas, **debes iniciar tu aplicación y ejecutar tus eventos in-app asignados** por lo menos una vez. Para probar aplicaciones de iOS, debes recopilar el identificador de anunciante (IDFA) para ver el evento. Las conversiones de eventos pueden tardar hasta 6 horas en agregarse a la cola. Una vez agregadas, puedes importarlas, y las conversiones nuevas cambian de estado y pasan de “No recent conversion” (Ninguna conversión reciente) a “recording conversion" (registro de conversión en curso).

1. Vuelve a la página **Overview** (Información general) de tu cuenta de Google Ads y ve a **TOOLS AND SETTINGS** (Herramientas y configuración) > **Measurement** (Medición) > **Conversions** (Conversiones).  
   <Image align="center" alt="conversions_overview_en-us__1_.png" src="https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png" />
2. Haz clic en **+ New conversion action** (Nueva acción de conversión).   
   <Image align="center" alt="New_conversion_action_en-us__2_.png" src="https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png" />
3. Selecciona **App** (Aplicación) en la lista de tipos de conversión, luego selecciona **Third-party app analytics** (Analíticas de aplicaciones de terceros) y haz clic en **Continue** (Continuar).  
   <Image align="center" alt="select_app_en-us__3_.png" src="https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png" />
4. Marca la casilla junto a **first\_open** de todas tus aplicaciones, y de cada evento que quieras importar.

   <div id="note-1" />

   > 📘 **Nota**
   >
   > Debes volver a importar si se cambia el **identificador de evento de partner** en Google Ads, o si es PERSONALIZADO y el nombre del evento correspondiente ha cambiado en AppsFlyer.


   Haz clic en **Import and Continue** (Importar y continuar) y, a continuación, haz clic en **Done** (Listo).   
   <Image align="center" alt="select_events_to_import_en-us__4_.png" src="https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png" />
5. Ahora puedes ver tus eventos de conversión de terceros en la página **Conversions** (Conversiones) > **Summary** (Resumen). Si un evento no aparece en la lista o se ha eliminado de la lista de conversiones de Google Ads, haz clic en **Ver todas las acciones de conversión**. Aparecerá el filtro **Status** (Estado).   
   <Image align="center" alt="conversions_summary_en-us__5_.png" src="https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png" />
6. Haz clic en **Estado** y selecciona **Todos** para ver todos los eventos, incluidos los deshabilitados y eliminados.  
   <Image align="center" alt="conversion_action_status__6_.png" src="https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png" />
7. ¡Felicitaciones! ¡Felicitaciones! Ya estás midiendo campañas móviles de Google Ads con AppsFlyer.

<div id="note-2" />

> 📘 **Nota**
>
> Asegúrese de que su configuración de "include in conversions" (incluir en conversiones) esté alineada con los objetivos de su campaña de Google Ads. Para más información, consulta con tu representante de Google o consulta la documentación de Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">aquí</Anchor>.

</Accordion>

</Accordion>

Para ver el vídeo «Configuración de la atribución de Google Ads para anunciantes», <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#configuración-de-la-atribución-de-google-ads-para-anunciantes">haz clic aquí</Anchor>.

Para obtener detalles sobre cómo los anunciantes pueden atribuir varias agencias/cuentas de Google Ads de MCC, haz clic <Anchor target="_blank" href="/marketers/es/docs/recording-multiple-agency-mcc-google-ads-accounts">aquí</Anchor>.

<div id="agencies-collecting-cost-clicks-and-impression-data" />

## Agencias: recopilación de datos de costos, clics e impresiones

Las agencias pueden <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#cost-tab">recuperar datos de costo</Anchor> de Google Ads, que también incluyen los datos de clics e impresiones.

Los datos de costos se muestran tanto en los paneles de control de la agencia como en los de los anunciantes, a nivel de campaña.

Si la agencia es transparente, en el panel de control del anunciante, los datos de costos se muestran en las campañas de Google Ads. Si no es así, los datos se muestran en las campañas de la agencia.

<div data-zendesk-anchors="enabling-agency-attribution-of-google-ads=habilitaci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-a-las-agencias h_01HKA1J5ES5T65NT5QMY5ZGXP6=habilitaci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-a-las-agencias setting-up-google-ads-attribution-for-agencies=configurar-la-atribuci%C3%B3n-de-google-ads-para-agencias h_01HKA1J5ESJYS902S9Z3YY5FV9=configurar-la-atribuci%C3%B3n-de-google-ads-para-agencias h_01HKA1J5ESF3ZK9E9PKM9AN8C8=advertiser-prestep-enabling-the-agency-access-to-google-ads h_01HKA1J5ETKV3H3KYBEYQZMSXA=agency-step-1-accepting-the-link-id h_01HKA1J5ET2BV8GHXZS5T8KCGZ=agency-step-2-setting-up-google-ads-on-appsflyer h_01HKA1J5ETH4TTVDSP0HNK6F0Q=agency-step-3-mapping-your-inapp-events h_01HKA1J5ETK5PXYFPXPBVH0HJQ=importante h_01HKA1J5ETNQ1FCBMVTQED74HG=nota h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=importante-1 h_01HKA1J5ETNTFKKDF6NC635H3W=nota-1 h_01HKA1J5ETEWJN8MH9NPWTWX0F=nota-2 agencies-collecting-cost-clicks-and-impression-data=agencias-recopilaci%C3%B3n-de-datos-de-costos-clics-e-impresiones h_01HKA1J5ETPYE7B2NFPFHA05YT=agencias-recopilaci%C3%B3n-de-datos-de-costos-clics-e-impresiones" />
