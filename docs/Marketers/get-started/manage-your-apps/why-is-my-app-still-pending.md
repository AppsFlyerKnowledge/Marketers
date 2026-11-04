---
title: ¿Por qué sigue pendiente mi aplicación?
metadata:
  keywords:
    - Google Play
    - App Store
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2026-08-12T12:05:15Z'
  id: 360001533885
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/360001533885
---
> **De un vistazo:** Sigue el estado de las aplicaciones pendientes de publicación en las tiendas de aplicaciones desde el panel de control de AppsFlyer.

Cuando <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">agregas tu nueva aplicación</Anchor> al panel de control de AppsFlyer, primero debes elegir si la aplicación está pendiente o ya está en el mercado.

Las aplicaciones pendientes en AppsFlyer tienen el mismo aspecto que las aplicaciones activas. Tienen paneles de control accesibles y todas las mediciones de atribución funcionan para ellas. La única diferencia es el logotipo de la aplicación, que se muestra con el logotipo de AppsFlyer en lugar del logotipo de la aplicación real.

![App_pendiente.png](https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png)

<div id="whats-happening" />

## ¿Qué ocurre?

AppsFlyer comprueba automáticamente el estado de las aplicaciones varias veces al día.

Si la aplicación aún no está activa en la tienda cuando AppsFlyer comprueba el estado de la aplicación, aparece como pendiente en el dashboard. Una vez que la aplicación finalmente se envía a iTunes o Google, se actualiza a "activa" y el logotipo cambia al logotipo original de la aplicación.

El estado de la aplicación en el panel de control no tiene ningún efecto sobre la recopilación y medición de datos. Si la aplicación está disponible en Google Play o en la App Store y los usuarios instalan la aplicación e interactúan con ella, los datos de instalación y de los eventos in-app se muestran en el panel de control de la misma manera.

<div id="refreshing-the-app-status" />

## Actualizar el estado de la aplicación

Para que el estado de la aplicación cambie a "activo", AppsFlyer verifica su estado en la tienda. Si estás seguro de que la aplicación está publicada en Google Play o iTunes, pero sigue apareciendo como pendiente en el panel de control, un administrador puede comprobar manualmente su estado.

**Requisito previo**: Disponible para el administrador de la cuenta.

**Para actualizar manualmente el estado de la aplicación:**

1. En el panel de control, haz clic en **Mis aplicaciones** en la esquina superior derecha.
2. Junto a la aplicación pendiente, haz clic en **Actualizar estado.** Si el estado de la aplicación no se ha modificado, esta seguirá apareciendo como pendiente. Si se ha actualizado, el estado se muestra como activa y el logotipo se actualiza.  

   ![app-refersh-status.png](https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png)

<div id="store-country" />

## País de la tienda

Algunas aplicaciones solo están disponibles en Google Play o iTunes para ciertos países. **Es importante configurar el país correcto para una aplicación** para que AppsFlyer pueda verificar y actualizar su estado.

<div id="ios" />

### apps de iOS,

Cuando <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">agregas una aplicación iOS</Anchor> a tu panel de control de AppsFlyer, eliges el país de Apple Store en el que se publica la aplicación. Si se elige el país incorrecto, AppsFlyer no puede actualizar el estado de la aplicación incluso si está publicada.

Para cambiar el país de Apple Store:

1. En AppsFlyer, en el menú lateral, selecciona**Configuración**> **Configuración de la aplicación.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. En **País de App Store**, elige el país correcto.
3. Desplázate hacia abajo y haz clic en **Guardar configuración**.
4. Si la aplicación sigue apareciendo como pendiente, [haz clic en **Actualizar estado**](/docs/why-is-my-app-still-pending#actualizar-el-estado-de-la-aplicación).

### Android

Cuando <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">agregas una aplicación Android</Anchor> a tu panel de control de AppsFlyer, no hay opción para elegir un país de Google Play y está configurado en EE. UU. de manera predeterminada. Si tu aplicación no está publicada en la tienda Google Play de EE. UU., es importante configurar la tienda correcta para la aplicación para que AppsFlyer pueda verificar y actualizar el estado de la aplicación.

Para cambiar el país de Google Play:

1. En AppsFlyer, en el menú lateral, selecciona**Configuración**> **Configuración de la aplicación.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. En **País de App Store**, elige el país correcto.
3. Desplázate hacia abajo y haz clic en **Guardar configuración**.
4. Si la aplicación sigue apareciendo como pendiente, [haz clic en **Actualizar estado**](/docs/why-is-my-app-still-pending#actualizar-el-estado-de-la-aplicación).

<div data-zendesk-anchors="whats-happening=qu%C3%A9-ocurre h_01HKW8NT3DWZMYVDYR13BDZDCT=qu%C3%A9-ocurre refreshing-the-app-status=actualizar-el-estado-de-la-aplicaci%C3%B3n h_01HKW8NT3DY227ASKYX1RC3V5T=actualizar-el-estado-de-la-aplicaci%C3%B3n store-country=pa%C3%ADs-de-la-tienda h_01HKW8NT3DHSDAG9C9225TDNRE=pa%C3%ADs-de-la-tienda ios=apps-de-ios h_01HKW8NT3DMWVGRB0RE3H3BQ36=apps-de-ios h_01HKW8NT3D2V81Z1ZBVQKTYX8T=android" />
