---
title: Configuración de partners de postback de Google Ads
metadata:
  keywords:
    - postbacks
    - Integration
    - Advertisers
    - Agencies
    - google ads
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
  created_at: '2021-11-16T09:36:56Z'
  edited_at: '2026-08-12T12:19:13Z'
  id: 4411047077905
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/4411047077905
---
> **De un vistazo:** Permite que los partners de postback de Google ayuden a ejecutar tus campañas de Google Ads.

Algunos partners (por ejemplo, Bidalgo, Adquant), denominados **partners de postback de Google Ads**, son similares a los de las agencias. Ayudan a sus clientes anunciantes a ejecutar campañas de Google Ads, pero requieren obtener postbacks para las conversiones de Google Ads.

Estos partners de postback de Google Ads (GAPP) también pueden recopilar postbacks para las instalaciones de Google Ads adquiridas directamente por el anunciante, o incluso por otras agencias (consulta los [casos de uso](/docs/google-ads-postback-partners-configuration#casos-de-uso-de-partners-de-postback-de-google-ads)). Utilizando la información de postbacks, los GAPP pueden optimizar las campañas de Google Ads para la aplicación.

<div id="important" />

> 🚧 **¡Importante!**
>
> Los partners de postback de Google Ads **NO** se atribuyen con instalaciones ni eventos en AppsFlyer.

El anunciante necesita una cuenta activa de Google Ads <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">configurada</Anchor> en AppsFlyer, y también configurar el GAPP específico en AppsFlyer para permitirle enviar postbacks.

Otros GAPP integrados con AppsFlyer: Blackbox, Appreciate, Marin Software, Miramedia, Mpbisummer, Protonads, Springrain.

<div id="google-ads-postback-partner-setup" />

## Configuración del partner de postback de Google Ads

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas** .

2. Escribe el nombre del GAPP con el que te gustaría trabajar en el cuadro de búsqueda y selecciónalo de la lista desplegable.

<div id="tip" />

> 👍 **Consejo**
>
> Introduce "Google Ads" en el cuadro de búsqueda y presiona Entrar para recibir la lista de GAPP.

3. Haz clic en el GAPP requerido para abrir su configuración de integración.

4. En tu cuenta de **Google Ads**, copia el ID de cliente (sin guiones):

<Image align="center" alt="" src="https://files.readme.io/7afd536d06b1aca68744a83925ecac86fcef4cc47225826af20120f128da004f-21414601345681.png" />

5. Pega el número en el campo **ID de cliente de Google Ads**.

6. Configura la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">sección de Postback de eventos in-app</Anchor>.

7. Haz clic en **Guardar**.

<div id="important-notes" />

> 📘 **Notas importantes**
>
> * Desactivar la atribución para Google Ads también deja de enviar postbacks a los GAPP.
> * Puedes configurar varias cuentas de anuncios (CID) para enviar postbacks (paso 5) separando cada CID con una coma.
>
>   ![zds_Agency_multiple.png](https://files.readme.io/36112b9a08ca1e6a2150523e1ec39eda5c28a4be826e9f776f5dbd7b1d0c5378-21414553418897.png)
> * Para trabajar con múltiples GAPP, las campañas para cada GAPP deben ejecutarse desde cuentas de Google separadas. Si cambias de un GAPP a otro, asegúrate de desactivar primero la configuración de GAPP en AppsFlyer.

<div id="google-ads-postback-partners-use-cases" />

## Casos de uso de partners de postback de Google Ads

<div id="use-case-1-advertiser-postbacks-only" />

<Accordion title="Caso de uso 1: solo postbacks de anunciante">

Un anunciante ejecuta campañas de Google Ads y desea que el tráfico de sus cuentas de Google Ads se envíe al GAPP X.

1. El anunciante <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> Google Ads
2. El anunciante [configura](/docs/google-ads-postback-partners-configuration#configuración-del-partner-de-postback-de-google-ads) GAPP X: Google Ads

El anunciante debe ingresar todos sus CID (ID de cuenta de anuncios) en la configuración de GAPP X - Google Ads.

</Accordion>

<div id="use-case-2-active-agency-with-advertiser-postbacks-only" />

<Accordion title="Caso de uso 2: agencia activa, solo con postbacks de anunciante">

Tanto un anunciante como una agencia están ejecutando campañas de Google Ads, el anunciante desea que solo se envíe su tráfico a GAPP X.

1. El anunciante <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> Google Ads
2. La agencia <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> Google Ads (solo para que su tráfico se les atribuya como agencia)
3. El anunciante [configura](/docs/google-ads-postback-partners-configuration#configuración-del-partner-de-postback-de-google-ads) GAPP X: Google Ads

El anunciante debe ingresar ÚNICAMENTE sus CID en la configuración de GAPP X: Google Ads.

</Accordion>

<div id="use-case-3-active-advertiser-with-agency-postbacks-only" />

<Accordion title="Caso de uso 3: anunciante activo, solo con postbacks de agencia">

Un anunciante y una agencia están ejecutando campañas de Google Ads, la agencia desea que solo se envíe su tráfico a GAPP X.

1. El anunciante <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> Google Ads
2. La agencia <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> Google Ads
3. La agencia [configura](/docs/google-ads-postback-partners-configuration#configuración-del-partner-de-postback-de-google-ads) GAPP X: Google Ads

La agencia debe ingresar ÚNICAMENTE sus CID en la configuración de GAPP X: Google Ads

</Accordion>

<div id="use-case-4-advertiser-agency-postbacks" />

<Accordion title="Caso de uso 4: postbacks de anunciante y agencia">

Un anunciante y una agencia están ejecutando campañas de Google Ads, tanto el anunciante como la agencia quieren que su tráfico se envíe a GAPP X.

1. El anunciante <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> Google Ads
2. La agencia <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> Google Ads
3. El anunciante [configura](/docs/google-ads-postback-partners-configuration#configuración-del-partner-de-postback-de-google-ads) GAPP X: Google Ads para sus CID
4. La agencia [configura](/docs/google-ads-postback-partners-configuration#configuración-del-partner-de-postback-de-google-ads) GAPP X: Google Ads para sus CID

Ten en cuenta que estos deben ser CID diferentes entre el anunciante y la agencia.

</Accordion>

<div id="available-parameters-for-gapps" />

## Parámetros disponibles para GAPP

**El contenido de los postbacks depende de la integración inicial de las GAPP con AppsFlyer** y no está relacionado con ninguna configuración de anunciante. Por lo tanto, dos GAPP cualesquiera pueden tener parámetros de postback definidos de manera diferente.

Por ejemplo, `campaign type`, `city`, `carrier` y `ad_type` son parámetros que pueden existir o no en cualquier postback de GAPP.

Hay dos fuentes para los parámetros de postback de GAPP:

1. **Macros de AppsFlyer**: para obtener detalles de todas las macros disponibles en los postbacks de AppsFlyer, haz clic <Anchor target="_blank" href="/partners/es/docs/postback-macros-for-ad-networks">aquí</Anchor>.
2. **Respuesta de Google**: con cada instalación atribuida a Google Ads, AppsFlyer recibe información relevante de Google. Los siguientes son parámetros disponibles en los postbacks de datos de GAPP, tal como los recibió AppsFlyer de Google Ads (para obtener descripciones detalladas de los parámetros, haz clic <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs#sample_responses">aquí</Anchor>)
   * ID de eventos publicitarios
   * ID de campaña
   * Nombre de la campaña
   * Tipo de campaña
   * ID de cliente externo (CID)
   * Tipo de red
   * Subtipo de red
   * Cadena
   * ID del video
   * ID del grupo de anuncios
   * Creative ID
   * Palabra clave
   * Tipo de coincidencia
   * Ubicación
   * Tipo de interacción
   * Tipo de anuncio
   * Métrica de conversión
   * Ubicación

<div id="note" />

> 📘 **Nota**
>
> La información disponible se basa únicamente en la información enviada por Google a AppsFlyer. Si, por alguna razón, Google no envía la información de una instalación, AppsFlyer no puede pasarla al GAPP.

<div data-zendesk-anchors="h_01HKA1HTJ4VW4YRXMSVG7WBTJM=importante google-ads-postback-partner-setup=configuraci%C3%B3n-del-partner-de-postback-de-google-ads h_01HKA1HTJ5BE5EVQJ2T9HSHKQC=configuraci%C3%B3n-del-partner-de-postback-de-google-ads h_01HKA1HTJ5BJTTS15QC44M63B2=consejo h_01HKA1HTJ5KSD1CVJ4FKDSATJX=notas-importantes google-ads-postback-partners-use-cases=casos-de-uso-de-partners-de-postback-de-google-ads h_01HKA1HTJ5DX0Z2ZCGX07EX15F=casos-de-uso-de-partners-de-postback-de-google-ads h_01HKA1HTJ5T2XJJ4M9YZ1S52SF=use-case-1-advertiser-postbacks-only h_01HKA1HTJ5EFADYE33NQVP1NBQ=use-case-2-active-agency-with-advertiser-postbacks-only h_01HKA1HTJ5H4KK2M94QY0VFRSA=use-case-3-active-advertiser-with-agency-postbacks-only h_01HKA1HTJ537CYXEBQRCV5FSPK=use-case-4-advertiser-agency-postbacks available-parameters-for-gapps=par%C3%A1metros-disponibles-para-gapp h_01HKA1HTJ5H0SXEMBVB6K2EZ91=par%C3%A1metros-disponibles-para-gapp h_01HKA1HTJ55XWMX90KSYTGFB6C=nota" />
