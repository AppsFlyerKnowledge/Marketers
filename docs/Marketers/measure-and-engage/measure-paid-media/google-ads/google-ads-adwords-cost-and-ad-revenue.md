---
title: 'Google Ads (AdWords): costos e ingresos por publicidad'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-08-22T00:28:17Z'
  id: 4417309205521
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/4417309205521
---
> **At a glance:** Habilita los datos de costo de Google Ads y los ingresos por anuncios en AppsFlyer.

<div id="cost-clicks-and-impressions" />

## Costo, clics e impresiones

La integración de costos proporciona los siguientes datos agregados:

* Datos de costos a nivel de tus campañas, conjuntos de anuncios, geolocalizaciones/países y canal. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.  
  **Nota:** Los datos de costos requieren una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Datos sobre clics, impresiones y datos enriquecidos (palabras clave, nombres de campañas y conjunto de anuncios).

> 📘 **Note**
>
> * Se admiten cuentas MCC.
> * Asegúrate de que la configuración de tu campaña en Google Ads sea para una app de iOS o de Android; no para ambas. Si la campaña es para ambas aplicaciones, AppsFlyer no puede desglosar el costo por aplicación y muestra el costo combinado de ambas aplicaciones.
> * Los datos de costos, clics e impresiones no están disponibles actualmente para las campañas de prerregistro debido a limitaciones en la API de Google Ads.

Para ver los datos de costos, clics e impresiones en el panel de control de AppsFlyer, deberá conectarse a través de la página de configuración de Google Ads. Una vez establecida la conexión, AppsFlyer comienza a consultar costos, clics e impresiones de Google Ads para todas sus campañas existentes.

Leer más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">configurar el costo en Google Ads</Anchor>.

Lee más sobre cómo Google define los clics y las visualizaciones.

Lee más sobre las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">limitaciones de Google Ads</Anchor>.

**Después de la configuración, los datos deberían aparecer en pocas horas**.

> 👍 **Tip**
>
> Los usuarios pueden confirmar que han iniciado sesión en la cuenta correcta de Google Ads al verificar la dirección de correo electrónico que aparece en la esquina superior derecha del panel de control de Google Ads.
>
> Si la cuenta de Google Ads es una subcuenta de una cuenta MCC, el ID que aparece en la esquina superior derecha es el ID de MCC,  y el ID de la subcuenta aparece en la esquina superior izquierda.
>
> Si no es la cuenta correcta, cierre sesión para salir de la cuenta y vuelva a iniciar sesión con la dirección de correo electrónico de otra cuenta de Google.

<div id="cost-data-sync-status" />

### Estado de sincronismo de datos de costos

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual. 

Google Adwords le permite sincronizar varias cuentas para extraer datos de costos. Para cada cuenta sincronizada, AppsFlyer muestra el estado de integración de costos y la última vez que AppsFlyer pudo extraer datos de costos coincidentes.

<div id="stopping-google-cost-sync" />

### Cómo detener la sincronización de costos de Google

**Para dejar de sincronizar los costos de Google, elimina la conexión de la cuenta de Google:**

* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Ve a la pestaña de costos, en la columna de acciones, coloca el cursor sobre una cuenta y haz clic en Eliminar conexión.</Anchor> Una vez eliminado, AppsFlyer deja de recibir el costo. Eliminar la conexión no afecta los datos anteriores.

<div id="recording-ad-revenue-with-google-ads" />

## Cómo registrar los ingresos por publicidad con Google Ads

La integración de ingresos de Google Ads (AdWords) está en desuso desde el 30 de noviembre de 2020. Para los datos de ingresos por publicidad, los clientes de AdWords deben migrar a <Anchor target="_blank" href="/marketers/es/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>.

<Accordion title="Preguntas frecuentes">

**P.** ¿Por qué no puedo ver los datos de costos?

**R.** Hay varias razones posibles por las que no ves los datos:

* Al iniciar sesión, es importante verificar que se esté usando la cuenta de Google correcta.  
  Si se inicia sesión con una cuenta de Google incorrecta, no se extraen ni se muestran los datos de costos. En ese caso, debes eliminar la aplicación de los permisos de aplicaciones de Google e iniciar sesión con la cuenta correcta. Para eso, sigue los pasos a continuación:
  1. Haga clic en la siguiente URL: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor>
  2. Elimine la opción AppsFlyer Cost (Costos de AppsFlyer) de Google e inicie sesión nuevamente.
* En algunos casos, la integración de costos de la agencia está activada, pero no genera costos porque el usuario de la agencia que inició sesión no tiene acceso al ID de cliente correcto de Google Ads. Esto hace que el anunciante vea unos datos de costos incompletos.

  Asegúrate de que el usuario de la agencia que inicia sesión en la pestaña Costo tenga acceso al ID de cliente de Google Ads configurado en la pestaña Integración.

  <Image alt="" src="https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png" width="457px" />
* El uso de espacios o caracteres especiales en campañas de búsqueda de iOS o páginas de aterrizaje de Android puede ocasionar problemas a la hora de hacer coincidir los datos de costos con los datos de clics, lo que deriva en la imposibilidad de reportar los costos.
* Cuando una agencia desactiva una integración de costos después de que se haya cobrado el costo, pero el anunciante sigue teniendo una integración de costos activa, los datos se asocian al anunciante solo a partir del día en que la agencia desactiva la integración.

**P.** ¿Dónde están mis datos de clics basados en geolocalización?

**R.** En algunos casos, AppsFlyer recibe datos parciales de clics por geolocalización de Google. Cuando esto sucede, AppsFlyer completa la información faltante sobre clics de otras fuentes de Google, que no incluyen los datos por geolocalización. Por lo tanto, cuando se agrupa por geolocalización, es posible que la cantidad total de clics de las campañas de Google no coincida con la de otra dimensión de agrupamiento.

</Accordion>

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Campañas activas e inactivas | La integración de Google admite reportes de costos para **campañas inactivas**, en los siguientes casos:<ul><li>Campañas de aplicaciones para instalaciones (tipo de campaña ACI)</li><li>Campañas de aplicaciones para engagements (tipo campaña ACE)</li><li>Las campañas inactivas son campañas para las que no se registró ninguna instalación o conversión en AppsFlyer.</li></ul>Para esas campañas de apps, AppsFlyer desglosa los datos de costo por canal, de acuerdo con los datos de atribución. Por ejemplo, ACI\_Display, ACI\_Youtube, ACI\_Search.<br /><br />Para las campañas que no son ACI o ACE, AppsFlyer solo reporta los costos de las **campañas activas**, lo que significa que al menos una conversión o instalación se ha registrado en AppsFlyer. Se reportan costos para la ventana de 7 días de la conversión/instalación. |
| Campañas Performance Max | Las campañas Performance Max no admiten el desglose de datos de costo por país/geo. |

</Accordion>

**Consulta también**

* Para conocer las consideraciones relacionadas con iOS 14, consulta <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads">Interoperabilidad de SKAdNetwork de Google Ads con AppsFlyer</Anchor>.

<div data-zendesk-anchors="cost-clicks-and-impressions=costo-clics-e-impresiones h_01HDP2SMHJ26S1BCER3KKZ8H14=costo-clics-e-impresiones cost-data-sync-status=estado-de-sincronismo-de-datos-de-costos h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=estado-de-sincronismo-de-datos-de-costos stopping-google-cost-sync=c%C3%B3mo-detener-la-sincronizaci%C3%B3n-de-costos-de-google h_01HDP2SMHJPEDKKZF9SBXW56KG=c%C3%B3mo-detener-la-sincronizaci%C3%B3n-de-costos-de-google recording-ad-revenue-with-google-ads=c%C3%B3mo-registrar-los-ingresos-por-publicidad-con-googleads h_01HDP2SMHKC9TSZZZPFFNK8TPH=c%C3%B3mo-registrar-los-ingresos-por-publicidad-con-googleads" />
