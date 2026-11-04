---
title: Configura tu lista de permitidos de API
metadata:
  keywords:
    - OneLink
    - API Policy
    - fraud
    - Advertisers
    - Agencies
    - API access
    - attribution link
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2021-08-22T13:50:14Z'
  edited_at: '2026-08-12T12:04:37Z'
  id: 4406016140817
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/4406016140817
---
> **En resumen:** Protege tu cuenta de AppsFlyer definiendo una lista de permitidos de API.

## [<Image alt="Lista de API permitidas" src="https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png" width="609px" />](https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png)

<div id="overview" />

## Resumen

Protege tus datos contra el acceso no autorizado al configurar una lista de permitidos de API que especifique las direcciones IP que pueden hacer llamadas API a tu cuenta de AppsFlyer. Una vez que tu lista de permitidos esté activa, solo se permitirán las llamadas API provenientes de esas direcciones IP, mientras que se denegarán las llamadas de todas las demás direcciones IP.

<div id="note" />

> 📘 **Nota:**
>
> * Solo los administradores pueden acceder y gestionar la lista de permitidos.
> * El uso de la lista de permitidos es opcional y está inactiva por defecto.
> * La activación de la lista de permitidos se realiza a nivel de cuenta y se aplica a todas las aplicaciones de la cuenta.

<div id="set-up-your-api-allowlist" />

## Configura tu lista de permitidos de API

<div id="set-up-the-api-allowlist" />

<Accordion title="Configura la lista de permitidos">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) altAppsFlyerAdmin\_us-en.pngaltPara configurar y activar la lista de permitidos de API:**

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección de lista de permitidos de API, haz clic en **Gestionar lista de permitidos de API**.
3. Introduce una dirección IP o un rango de direcciones IP en formato estándar:
   * Ejemplos: `192.168.1.1`, `185.114.120.140`
   * Para introducir un rango de direcciones IP, usa este formato: `185.114.120.1/32`(donde `185.114.120.1` es la primera dirección del rango y `185.114.120.32` es la última dirección del rango).
4. Haz clic en **Aplicar.**
5. [Opcional] Haz clic en **+ Añadir** para agregar una dirección IP adicional o un rango a la lista.
6. Haz clic en el botón **Guardar lista**.
7. Ajusta la lista de permitidos a **Activo.**

   **Nota:** La lista de permitidos debe contener al menos una dirección IP o un rango antes de que puedas guardarla y activarla.

</Accordion>

<div id="edit-the-api-allowlist" />

<Accordion title="Editar la lista de permitidos">

Puedes agregar o eliminar direcciones IP de la lista de permitidos en cualquier momento (ya sea que la lista esté activa o no).

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) altAppsFlyerAdmin\_us-en.pngaltPara agregar una dirección IP o un rango:**

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección de lista de permitidos de API, haz clic en **Gestionar lista de permitidos de API**.
3. Haz clic en **+ Añadir** para agregar una dirección IP o un rango a la lista.
4. Introduce una dirección IP o un rango.
5. Haz clic en **Aplicar.**
6. Asegúrate de guardar tus cambios haciendo clic en el botón **Guardar lista**.

   **Nota:** El estado de la lista (activa o inactiva) no cambiará cuando guardes la lista. Asegúrate de verificar el estado del conmutador de **Activo** y actívalo/desactívalo si es necesario.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) altAppsFlyerAdmin\_us-en.pngaltPara eliminar una dirección IP o un rango:**

1. Desde la barra superior, abre el menú de la cuenta (desplegable de dirección de correo electrónico) > **Centro de seguridad**.
2. En la sección de lista de permitidos de API, haz clic en **Gestionar lista de permitidos de API**.
3. Haz clic en el icono de la papelera junto a la dirección IP que deseas eliminar.
4. En la ventana de confirmación, haz clic en **Eliminar.**
5. Asegúrate de guardar tus cambios haciendo clic en el botón **Guardar lista**.

</Accordion>

<div id="api-allowlist-specifications" />

<Accordion title="Especificaciones de Allowlist">

* Para proteger tu cuenta de llamadas API no autorizadas, la lista de permitidos debe estar **Activa** y debe incluir al menos una dirección IP o un rango.
* La lista de permitidos se aplica a todas las <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#aplicaciones-del-token-api-v2">APIs de AppsFlyer que utilizan el token V2.0</Anchor><Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#aplicaciones-del-token-api-v2">. Las llamadas de APIs que utilizan el token API V1.0 serán permitidas desde todas las direcciones API.</Anchor>
* Se pueden agregar hasta 20 direcciones IP o rangos a la lista de permitidos.

</Accordion>

<div data-zendesk-anchors="overview=resumen overview::6f3684c7=resumen h_01HZCCCTT52ZQB9VAF6Q7RRKES=resumen h_01HZCD0681XNKR2HSNCN4GWGA0=resumen h_01HJR00RGQX0CQEHDS9BHBGJD4=nota set-up-your-api-allowlist=configura-tu-lista-de-permitidos-de-api h_01HZCCW4XYJ72Z6KKJPCXQB947=configura-tu-lista-de-permitidos-de-api h_01HJR00RGRQ54R71HY0ZBRM1PM=set-up-the-api-allowlist h_01HJR00RGRD7PK2HR5VS1JENWQ=edit-the-api-allowlist h_01HJR00RGRESGGEW3D6NHHF7VY=api-allowlist-specifications" />
