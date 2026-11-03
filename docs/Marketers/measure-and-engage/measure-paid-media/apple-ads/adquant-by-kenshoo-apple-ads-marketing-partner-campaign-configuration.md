---
title: >-
  Adquant by Kenshoo, partner de marketing de Apple Ads: configuración de
  campaña
metadata:
  keywords:
    - kenshoo
    - Advertisers
    - apple search ads
    - Agencies
    - adquant
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
  created_at: '2018-09-20T07:53:06Z'
  edited_at: '2026-09-17T00:25:41Z'
  id: 360001491269
  locale: es
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/es/articles/360001491269
---
> **De un vistazo:** Optimiza las campañas de Apple Ads con Adquant by Kenshoo. Una vez configurado, AppsFlyer envía postbacks a Adquant.

## Habilitar el envío de postbacks a Adquant (partner de marketing de Apple Ads)

Tanto los anunciantes como las agencias pueden habilitar la atribución para Apple Ads.

> 📘 **Nota:**
>
> Si el anunciante o la agencia deshabilita la atribución para Apple Ads, se detiene la atribución para esta aplicación, incluido el envío de postbacks a Apple Ads Partners de marketing.

* **Anunciantes:** siguen las instrucciones que aparecen a continuación para habilitar la atribución para Apple Ads.
* **Agencias:** <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#agency-setup">sigan estas instrucciones</Anchor> para habilitar la atribución para Apple Ads.

### Configuración de Adquant by Kenshoo

**Para configurar Adquant:**

1. Si es necesario, activa la **integración de Apple Search Ads:**
   1. En AppsFlyer, en el menú lateral, selecciona **Collaboration** > **Partner Marketplace**.
   2. Busca y selecciona al partner. Serás dirigido a la página de configuración del partner.
   3. En la pestaña **Integración**, selecciona **Activar partner**.
   4. Haz clic en **Guardar integración**.
2. **En tu dashboard de Apple Ads**: obtén el parámetro Apple Ads Campaign Group ID relacionado con Adquant. Utiliza la captura de pantalla a seguie como guía para localizar el ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **En AppsFlyer, configura Adquant:**
   1. En AppsFlyer, desde el menú lateral, selecciona **Collaborate** > **Partner Integrations.**
   2. Busca el partner de marketing de Apple Ads Adquant by Kenshoo Apple Ads marketing partner.  
      Se muestra la lista de partners de marketing.
   3. Selecciona el partner de marketing de Apple Ads Adquant by Kenshoo.
   4. Activa **Activar partner.**
   5. Introduce el **Apple Ads Campaign ID** de Adquant que recuperaste en el paso anterior. Ingresa solo los dígitos (números).
   6. En **action\_identifier**, introduce el dominio utilizado para la entrega de postbacks.
   7. [Opcional] **No permitas compartir la geolocalización del usuario:** Para dejar de compartir la geolocalización del usuario, en **Disable\_Country\_Sending** escribe `1`.
   8. Haga clic en **Guardar**.

### Postbacks predeterminados

Los postbacks mostrados se envían automáticamente cuando se activa el partner.

### Configuración del postback de eventos in-app

**Para configurar postbacks de eventos in-app:**

1. Introduce el action\_identifier.
2. Activa **In-app events postback**.
3. Haz clic en **Add Event** para añadir un evento de SDK o de servidor a servidor a la lista.
4. Completa los siguientes parámetros:

   

| Nombre del parámetro | Nota |
| --- | --- |
| <span id="appsflyer-event"></span>**Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**Asignado al evento asociado** | El nombre o ID único de cada evento, tal como lo define el partner. Existen <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">varias configuraciones de asignación</Anchor>:<ul><li>**Campo de texto:** Obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de partner predefinido más adecuado.</li><li>**Tal cual**: Envía los eventos tal como son, sin mapear el nombre del evento.</li></ul> |
| <span id="for-users-from"></span>**Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos, es decir, el usuario que los realizó provino de cualquier fuente de medios.</li></ul> |
| <span id="including"></span>**Incluye** | Selecciona <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">qué datos del evento</Anchor> compartir con el partner en el postback:<ul><li>**Sin valores y sin ingresos**: Envía solo el evento en sí, sin ningún parámetro (valores o ingresos).</li><li>**Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: Envía todos los parámetros del evento, **incluyendo** el valor de los ingresos (si existe en el evento).</li></ul> |

5. Haz clic en **Guardar integración**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-adquant-apple-search-ads-marketing-partner=habilitar-el-env%C3%ADo-de-postbacks-a-adquant-partner-de-marketing-de-apple-ads h_01HKW0AW61TW7TGPB4KX4XYVCB=habilitar-el-env%C3%ADo-de-postbacks-a-adquant-partner-de-marketing-de-apple-ads h_01HKW0AW61RDVXCB37PAFKAXW3=nota configuring-adquant-by-kenshoo=configuraci%C3%B3n-de-adquant-by-kenshoo h_01HKW0AW61QT8823TXVYB7JWTC=configuraci%C3%B3n-de-adquant-by-kenshoo default-postbacks=postbacks-predeterminados h_01HKW0AW61EKKGK1NSKBDXSDJC=postbacks-predeterminados configuring-inapp-events-postback=configuraci%C3%B3n-del-postback-de-eventos-in-app h_01HKW0AW6184ZH4H6JEJPBNXSH=configuraci%C3%B3n-del-postback-de-eventos-in-app" />
