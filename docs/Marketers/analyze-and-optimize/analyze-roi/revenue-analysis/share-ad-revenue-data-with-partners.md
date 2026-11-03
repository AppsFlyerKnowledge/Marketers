---
title: Comparte datos de ingresos publicitarios con partners
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-09-17T00:02:08Z'
  id: 24100803679761
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Permite que los partners reciban información de ingresos publicitarios de redes de mediación para que puedan optimizar sus campañas de UA (adquisición de usuarios). **Nota**: Esto requiere una suscripción avanzada a ROI360.

## Sobre el uso compartido de datos de ingresos publicitarios con partners

Puedes permitir que las ad networks responsables de la adquisición de usuarios reciban datos de ingresos publicitarios de las redes de medios. Los partners pueden utilizar esta información para optimizar sus campañas de UA.

Los partners pueden recibir datos de ingresos publicitarios a través de:

* [Señales de UA para ad network](#ua-signals-for-ad-networks)
* [Postbacks de ingresos publiciarios para ad networks](#ad-revenue-event-postbacks-for-ad-networks)

La siguiente tabla compara las 2 soluciones para compartir datos de ingresos publicitarios. 

| Solución de intercambio de datos de ingresos publicitarios | Actualización de los datos | Caso de uso | Tipo de integración requerido | Tipo de suscripción requerido |
| --- | --- | --- | --- | --- |
| Señales UA | A diario | Datos precisos y completos, comúnmente utilizados para la optimización D3 y D7. | <ul><li>Nivel de impresión o nivel de dispositivo</li><li>Si ambos están configurados, se envían datos a nivel de dispositivo</li></ul> | ROI360 Avanzado |
| Devoluciones de mensajes | En tiempo real | Datos frescos, comúnmente utilizados para la optimización D0 y D1. | Nivel de impresión | ROI360 Avanzado |

## Procedimientos

<div id="ua-signals-for-ad-networks" />

<Accordion title="Señales de UA para ad networks">

Es posible que desees trabajar con ad networks que puedan recibir señales de UA. Esto significa que las ad networks responsables de la adquisición de usuarios pueden recibir datos de ingresos publicitarios de redes de mediación y usarlos para optimizar las campañas de UA de sus clientes.

**Para enviar señales UA a una ad network**:

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas**.
2. Selecciona el partner integrado.
3. Ve a la pestaña **Integración**.
4. Verifica que **Activar partner** esté encendido. De lo contrario, los datos no se comparten.
5. Ve a la pestaña **Permisos**.
6. Activa los **permisos de ad network**.
7. **Accede al raw data de los ingresos por publicidad (señales UA)**.
8. En **Opción de envío**, selecciona si quieres enviar datos de ingresos publicitarios solo de este partner (**Solo este partner**) o de todas las fuentes de medios (**Todas las fuentes de medios, incluidas las orgánicas**). **Nota**: Cuando se selecciona **Todas las fuentes de medios, incluidas las orgánicas**, los datos de otros partners no incluyen Datos de atribución.
9. Haz clic en **Guardar configuración**.
10. Contacta con la ad network:
    1. Notifícale que has concedido los permisos.
    2. Diles que sigan <Anchor target="_blank" href="/partners/es/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">sus instrucciones</Anchor> para recibir el reporte.

**Lista de partners de mediación que pueden enviar señales de UA a las ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Mediación de Unity LevelPlay (anteriormente ironSource)
* Admost
* Tradplusad
* Yandex
* Mediación personalizada

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Postbacks de eventos de ingresos publiciarios para ad networks">

Puedes configurar los postbacks de los ingresos por publicidad para las ad networks. Esto significa que las ad networks responsables de la adquisición de usuarios pueden recibir datos en tiempo real de las redes de medios sobre los ingresos por publicidad y usarlos para optimizar las campañas de UA de sus clientes. 

> 🚧 **¡Importante!**
>
> * Los postbacks de eventos de ingresos publicitarios a ad networks solo funcionan con los <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipos de integración</Anchor> de ingresos publicitarios a nivel de impresión a través del SDK y a nivel de impresión (a través del SDK) con nivel de dispositivo (a través de la API de servidor a servidor (S2S)). Esto significa que tu desarrollador debe integrar la <Anchor target="_blank" href="/marketers/es/docs/integrate-the-roi360-ad-revenue-sdk-api">API del SDK de ingresos publicitarios de AppsFlyer</Anchor>.
> * Aunque puedes enviar postbacks de ingresos publicitarios a partners específicos, te recomendamos validar cómo usan los datos antes de iniciar la integración.

**Para configurar postbacks de eventos de ingresos por publicidad**:

1. Busca y selecciona a tu partner, ya sea <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#manage-existing-integrations">desde el marketplace</Anchor> o desde la **Colaborar** > **Integraciones de partners** > **Integraciones** **activas** página.
2. En la pestaña **Integración**, desplázate hacia abajo y activa los **postbacks de eventos in-app**.
3. Selecciona el evento af\_ad\_revenue de AppsFlyer. **Nota**: Algunas integraciones de ad networks tienen la opción de **Seleccionar todos los eventos**. No utilices esta opción, ya que excluye los eventos de af\_ad\_revenue.
4. Asócialo al evento de la ad network de la siguiente manera:

| Red publicitaria | Evento para asignar af\_ad\_revenue a | Captura de pantalla |
| --- | --- | --- |
| Anuncios de Google | ad\_impression | <Image alt="Asignación del evento ad_impression de Google Ads" src="https://files.readme.io/883dd04563027d722e7e8e76a50f813c8a955db827cbb92e94cdc650ab7b234d-50421403523601.png" width="238px" /> |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | No es necesario asignarlo |  |
| Mintegral | No es necesario asignarlo |  |
| Smadex | No es necesario asignarlo |  |
| Mistplay | No es necesario asignarlo |  |
| Anuncios de Meta | fb\_mobile\_purchase, para apps de iOS  <br />o  <br />Adimpression, para apps de Android  <br /><Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping#mapeo-de-datos-de-ingresos-por-anuncios-para-la-optimización-de-campañas">Guía de asignación de eventos in-app de Meta Ads</Anchor>. | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok for Business: SRN avanzada | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura de Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| SingleTap de Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | No es necesario asignarlo |  |
| Bidease | No es necesario asignarlo |  |
| MAF | No es necesario asignarlo |  |

5. Selecciona una opción de **envío de usuario** para el evento:
   * **Solo este partner**: envía postbacks solo cuando el evento se atribuye a este partner, es decir, cuando el usuario que lo realizó proviene de este partner.
   * **Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos; es decir, el usuario que los realizó proviene de cualquier fuente de medios. **Nota**: Cuando se seleccionan todas las fuentes de medios, incluidas las orgánicas, los postbacks de otros partners no contienen datos de atribución.
6. Haz clic en **Guardar integración**.

**Lista de partners de mediación que pueden enviar eventos de ingresos publicitarios a nivel de impresión a las ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Mediación de Unity LevelPlay (anteriormente ironSource)
* Admost
* Tradplusad
* Yandex
* Mediación personalizada

</Accordion>

## Información adicional

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="Lista de ad networks que pueden recibir señales de UA y postbacks">

La siguiente tabla enumera las ad networks que pueden recibir señales de ingresos publicitarios de UA y postbacks de redes de medios.

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">Ad network (partner)</th><th colspan="2">Soportes</th></tr><tr><th>Señales UA</th><th>Devoluciones de mensajes</th></tr></thead><tbody><tr><td>RZR (anteriormente Aarki)</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aura de Unity</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Anuncios de Google</td><td> </td><td><span>✓</span></td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Híbrido</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Kashkick</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lacuna</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Anuncios de Meta</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Miniclip</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>Remerge</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>SingleTap de Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok para empresas</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vivo Global </td><td> </td><td><span>✓</span></td></tr><tr><td>Voodoo Ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Vungle</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Yandex</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO Network</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Tipos de conversión | Tanto las señales de UA como los postbacks de ingresos publicitarios respaldan datos sobre todos los tipos de conversión: instalaciones, reatribuciones, re-engagement y reinstalaciones. |
| Permisos de postback de la agencia | Las agencias no pueden configurar postbacks de ingresos publicitarios |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=sobre-el-uso-compartido-de-datos-de-ingresos-publicitarios-con-partners h_01HV6CW4SAF23TT5XZF1SGPVQH=sobre-el-uso-compartido-de-datos-de-ingresos-publicitarios-con-partners procedures=procedimientos h_01HVEEMGMEWDKAXVNHR8C0AHPQ=procedimientos 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=importante additional-information=informaci%C3%B3n-adicional h_01HVE6AREZBPH751WFW70Q7X66=informaci%C3%B3n-adicional h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />
