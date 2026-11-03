---
title: Integración de Luna Labs con AppsFlyer
metadata:
  keywords:
    - postbacks
    - integrated partner
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-08-12T11:59:12Z'
  id: 360019465017
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/360019465017
---
> **De un vistazo:** Luna Labs es una plataforma integral que permite a sus clientes crear, gestionar y optimizar playables y anuncios de video.

> 🚧 **Dos puntos (:)**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Luna Labs

**Requisito previo:** Antes de configurar la integración, asegúrese de ponerse en contacto con el socio y abrir una cuenta con ellos.

**Nueva integración:**

1. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Busca Luna Labs y selecciona **Integrar**.
4. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner. Mantenlo activado mientras trabajes con Luna Labs.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

**Editar integración existente:**

Busca al partner y selecciónalo.

## Integración

Usa la pestaña de integración para la configuración. Las pestañas restantes están inactivas.

> 📘 **Nota:**
>
> Luna Labs no usa sus propios enlaces de atribución. Reciben postbacks de ad networks que ejecutan campañas con anunciantes. Luna Labs solo recibe postbacks de sus propios creativos y solo postbacks que incluyen el parámetro y valor `af_addpb=1`. Consulta más abajo una explicación detallada.

### Activar socio

En la **primera visita**, debes activar **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. **El selector debe estar activado mientras trabajes con el partner**.  
Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación/desactivación del partner</Anchor>.

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Luna Labs tras las instalaciones de los usuarios.

**Nota:** Luna Labs solo puede recibir postbacks de sus propios creativos.

**Para enviar postbacks a Luna Labs:**

1. Asegúrate de que la ad network con la que trabajas junto con Luna Labs esté activada e integrada con AppsFlyer.
2. Asegúrate de que la ad network añada el parámetro `af_addpb=1` al enlace de atribución que la ad network envía a AppsFlyer y a Luna Labs.  
   Este parámetro permite enviar el postback a Luna Labs y les indica que el clic procedía de su creativo.
3. Selecciona **Eventos atribuidos a cualquier partner o de origen orgánico**.

Por ejemplo, si ad-network-X trabaja con una determinada app (id1234567890) y quiere enviar postbacks a Luna Labs, entonces la URL debería tener este aspecto:

```http
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```

<div data-zendesk-anchors="h_01H9FKCW1FJ2QCVVE6HEE640H9=dos-puntos- setting-up-luna-labs=configuraci%C3%B3n-de-luna-labs h_01HJR5M5C0P759S4X5SSJCY501=configuraci%C3%B3n-de-luna-labs integration=integraci%C3%B3n h_01H9FKCW1FE6JCY5FAFF3Y4TGH=integraci%C3%B3n h_01H9FKCW1FNPCF1M7SRWTMNDCW=nota activate-partner=activar-socio h_01H9FKCW1FV00605GYK498JZN9=activar-socio default-postbacks=postbacks-predeterminados h_01H9FKCW1FGMA3FKAY5B9YCJVH=postbacks-predeterminados" />
