---
title: Configuración de partners de marketing de Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-24T08:47:31Z'
  edited_at: '2026-09-17T00:29:46Z'
  id: 4417694142481
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/4417694142481
---
> **De un vistazo:** Integra con partners de marketing de Snapchat para medir las campañas que ejecutas con ellos. Cuando se configura, AppsFlyer envía postbacks al partner de marketing de Snapchat configurado.

## Configurar un partner de marketing de Snapchat

Sigue los pasos a continuación para configurar tus campañas con cualquiera de los partners de marketing de Snapchat.

* Activa la <Anchor target="_blank" href="/marketers/es/docs/snapchat-advanced-srn-integration-setup">atribución de Snapchat</Anchor>.
* En el dashboard de **Business Manager** de Snapchat, copia el **Snap Account ID** resaltado abajo en verde.

  ![snapchat-dashboard.png](https://files.readme.io/a0942bd27528d4a837edc6eb5d11338bf0622ddc42e382231a8f210aedad1424-50902448760337.png)

Cuando hayas activado Snapchat y obtenido el Snap Account ID, configura el partner de marketing:

1. En AppsFlyer, desde el menú lateral, selecciona **Colaboración** > **Integraciones de partners** > **Integraciones activas.**
2. En el cuadro de búsqueda, introduce el nombre del partner concreto o «Snapchat» para ver la lista completa de partners de marketing de Snapchat.
3. Haz clic en el logotipo del partner que necesites para abrir la ventana de configuración.
4. Activa **Activar partner**.
5. Pega el **Snap account ID** obtenido del dashboard de Snapchat (con los guiones) en el campo **Snap Account ID**.
6. Haga clic en **Guardar**.

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos de instalación y re-engagement a partners. Utiliza esta sección para definir la **fuente de los usuarios** que permite enviar estos postbacks. En algunos casos, el origen de los usuarios está predefinido y no se puede cambiar:

![remerge2.png](https://files.readme.io/4f3f52b3610b3e3bcf0adc6e963f1f2c39cdb0b2de27569c890844aac477b3d0-50902448761873.png)

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a este partner.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para reportarla a este partner.

### Eventos dentro de la aplicación

1. Para enviar postbacks de eventos in-app al partner de marketing de Snapchat que estás configurando, activa Postback de eventos in-app en **ON**.
2. Añade individualmente los eventos in-app (eventos de SDK) que quieras enviar al partner y <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">mapéalos según sea necesario.</Anchor>

> 🚧 **Importante:**
>
> Deshabilitar la atribución de Snapchat impide enviar postbacks a los partners de marketing de Snapchat.

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-snapchat">Interoperabilidad de Snapchat y SKAdNetwork de AppsFlyer</Anchor>

<div data-zendesk-anchors="setting-up-a-snapchat-marketing-partner=configurar-un-partner-de-marketing-de-snapchat h_01HDNZAAS11ADG02FXNPSYYH69=configurar-un-partner-de-marketing-de-snapchat default-postbacks=postbacks-predeterminados h_01HDNZAAS1M2317CKQ13SP11KM=postbacks-predeterminados inapp-events=eventos-dentro-de-la-aplicaci%C3%B3n h_01HDNZAAS1JZPHS32PNFFCR12A=eventos-dentro-de-la-aplicaci%C3%B3n h_01HDNZAAS1PRWK6EVQTTV3YNQM=importante h_01HDNZBZARD9E54VAFVSRQFWEH=v%C3%A9ase-tambi%C3%A9n" />
