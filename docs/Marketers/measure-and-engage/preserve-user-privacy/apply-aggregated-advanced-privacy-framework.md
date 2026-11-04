---
title: Framework de Privacidad Avanzada Agregada
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-08-12T12:23:31Z'
  id: 360018515798
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/360018515798
---
> **En resumen:** A partir de la disponibilidad general de iOS 14.5+ y la aplicación de la ATT por parte de Apple, los anunciantes utilizan el framework de Privacidad Avanzada Agregada (AAP) para controlar la disponibilidad de los datos de atribución a nivel de usuario de la plataforma.

<div id="aggregated-advanced-privacy-aap-framework" />

## Framework de Privacidad Avanzada Agregada (AAP)

El framework de Privacidad Avanzada Agregada (AAP) de AppsFlyer evita el seguimiento de aplicaciones y sitios web propios de diferentes empresas y la capacidad de identificar de forma exclusiva a un usuario o dispositivo. AAP utiliza los niveles de privacidad de Apple App Tracking Transparency como referencia mínima para sus umbrales de preservación de la privacidad.

El framework brinda a los anunciantes la capacidad de controlar la disponibilidad de datos de atribución a nivel de usuario a través de la plataforma de AppsFlyer.

A partir de iOS 14.5, la disponibilidad general y el cumplimiento de la ATT de Apple, si la AAP está activada, los datos de atribución a nivel de usuario para usuarios sin consentimiento que ejecutan iOS 14.5+ no estarán disponibles para anunciantes o partners. **Nota**: Incluso cuando AAP está desactivado, los datos a nivel de usuario no se pueden usar para identificar de forma única un dispositivo.

La AAP no tiene impacto alguno en la disponibilidad de los datos de atribución agregados y los reportes de análisis para anunciantes y partners.

<div id="aap-impacted-features" />

### Funciones afectadas por la AAP

Si la AAP está activada, los datos proporcionados por el raw data se ven afectados y algunos campos están restringidos o no están disponibles. Esto afecta a los datos proporcionados por las siguientes herramientas:

* Casillero de datos
* Pull API de raw data
* API Push
* Página de exportación del dashboard
* Postbacks a redes
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">API para obtener datos de conversión (GCD)</Anchor> en el contexto de la API de datos del lado del cliente a nivel de usuario

La disponibilidad de datos se ve afectada cuando la AAP está activada de la siguiente manera:

* Activa o desactiva la **Privacidad avanzada agregada** según sea necesario.
* **Clic, impresión y datos de clics bloqueados (fraude):** <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#identifier-restriction">Los identificadores relacionados con el usuario y el dispositivo</Anchor> no están disponibles.
* **Deferred deep linking**: Si implementas el Deferred Deep Linking en medios pagados, usa la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">API de dep links unificados (UDL).</Anchor> La antigua API, que utiliza GCD, no se puede usar en el contexto de usuarios que no consienten. En el caso de los medios propios, el deferred deep linking es compatible a través de GCD y la API de deferred deep linking más reciente.

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## Principios de disponibilidad de datos en la Privacidad Avanzada Agregada

Cuando la AAP se aplica a los datos de un usuario determinado, la disponibilidad de los datos depende del estado de la ATT de ese usuario y de la fuente de medios que trae al usuario.

**Definiciones:**

* **Datos de atribución a nivel usuario:** Registros de datos que contienen identificadores a nivel de dispositivo vinculados a la atribución a nivel de usuario
* Datos de atribución limitados para anunciantes:
  * Disponible: Identificadores a nivel de dispositivo. (El IDFA está disponible si se da el consentimiento del usuario).
  * No disponible: parámetros de atribución recibidos a través del enlace de atribución del publisher (por ejemplo, `pid` y `c`). <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">Lista de campos restringidos y no disponibles para anunciantes</Anchor> AKA fuente de medios restringida.
* **Datos de atribución limitados para partners:**
  * Disponible: detalles de campaña agregados.
  * Datos de nivel de usuario que pueden ayudar a identificar al usuario, como ID de AppsFlyer, datos personalizados, ID de usuario del cliente (CUID), ID de clic, IDFA, IDFV, IMEI, agente de usuario y dirección IP.

Los términos definidos se utilizan en la figura y las secciones siguientes para describir los datos disponibles para anunciantes y partners.

![Advanced Privacy Framework: anunciantes (4).png](https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png)

La privacidad avanzada se comporta de manera diferente cuando se sirve en la web y se debe utilizar el parámetro af\_media\_type=web o af\_media\_type=app. Consulta <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campañas-web">aquí</Anchor> para obtener más información.

<div id="paid-and-owned-media-data-availability" />

### Disponibilidad de datos de medios pagados y propios

<div id="paid-media" />

<Accordion title="Medios pagados">

Los medios pagados incluyen ad networks móviles con integraciones en la plataforma de AppsFlyer con las que los anunciantes ejecutan campañas.

<div id="paid-media-data-availability-by-att-status" />

#### Disponibilidad de datos de medios pagados por estado de la ATT

<table><thead><tr><th rowspan="2">Tipo de medio</th><th colspan="2">Estado de la ATT</th><th colspan="2">Datos disponibles para:</th></tr><tr><th>Aplicación del publisher</th><th>Aplicación del anunciante</th><th>Anunciante</th><th>Red publicitaria</th></tr></thead><tbody><tr><td rowspan="4">Aplicación</td><td>Autorizado</td><td>Autorizado</td><td>Datos de atribución a nivel usuario</td><td>Datos de atribución a nivel usuario</td></tr><tr><td>No autorizado</td><td>Autorizado</td><td>Datos de atribución limitados para anunciantes </td><td>Datos de atribución limitados para partners</td></tr><tr><td>Autorizado</td><td>No autorizado</td><td>Datos de atribución limitados para anunciantes </td><td>Datos de atribución limitados para partners</td></tr><tr><td>No autorizado</td><td>No autorizado</td><td>Datos de atribución limitados para anunciantes </td><td>Datos de atribución limitados para partners</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>Web</p></td><td>N/D</td><td>Autorizado</td><td>Datos de atribución a nivel usuario</td><td>Datos de atribución a nivel usuario</td></tr><tr><td>N/D</td><td>No autorizado</td><td>Datos de atribución limitados para anunciantes </td><td>Datos de atribución limitados para partners</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Medios propios">

El framework de App Tracking Transparency de Apple se aplica solo a los datos recopilados de diferentes empresas. Por lo tanto, los datos de atribución a nivel de usuario de medios propios están disponibles para los anunciantes independientemente del estado de consentimiento de la ATT del usuario.

Los medios propios incluyen campañas de marketing digital utilizadas por los anunciantes para llegar a los clientes. Esto incluye campañas de correo electrónico, promociones cruzadas, push notifications, etc. En AppsFlyer, las campañas que usan ad networks no se consideran medios propios.

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## Controlando la Privacidad Agregada Avanzada

<div id="aap-central-switch" />

<Accordion title="Privacidad Avanzada Agregada (AAP): alternar a nivel de aplicación">

La AAP es un selector de nivel de aplicación que controla la configuración de la privacidad avanzada para todos los partners de la aplicación seleccionada. El selector de AAP se encuentra en la página de **Configuración de la aplicación**. Cuando el selector de AAP está activado, los selectores de **Privacidad Avanzada** para todos los partners de la aplicación seleccionada se activan automáticamente y no se pueden modificar. Cuando está desactivado, los anunciantes pueden ir a la integración de cada partner de forma individual y activar la **Privacidad Avanzada**.

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

<div id="aap-enabled" />

#### AAP habilitada

* La atribución agregada está disponible. Esto incluye, por ejemplo, dashboard general y herramientas de reportes como Cohorte y Master API.
* [Los interruptores de partners de privacidad avanzada](#partner-advanced-privacy-switch) están activados y no se pueden modificar. ¡Atención! ¡Nota! Están bloqueados en posición.
* La disponibilidad de los datos a nivel de usuario hacia anunciantes y partners es limitada, tal como se define en la [sección anterior](/docs/apply-aggregated-advanced-privacy-framework#principios-de-disponibilidad-de-datos-en-la-privacidad-avanzada-agregada).

<div id="aap-disabled" />

#### AAP deshabilitada

* Los datos de atribución a nivel de usuario están disponibles para los anunciantes.
* La configuración de la Privacidad Avanzada por partner se puede establecer individualmente.

*Antes de desactivar la AAP, considera si hacerlo hará que los datos de atribución a nivel de usuario estén disponibles para terceros y cómo estos usarán los datos. Debes trabajar estrechamente con tus asesores legales y profesionales en relación con la forma en que Apple define el seguimiento. Nada de lo que se indica aquí es asesoramiento legal. Se proporciona para tu información y comodidad.*

**Para establecer la configuración de Privacidad Avanzada Agregada**:

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.
2. Activa o desactiva **Aggregated Advanced Privacy**  según sea necesario.
3. Haz clic en **Guardar**.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Privacidad Avanzada (AP): alternar a nivel de partner">

Si la AAP está deshabilitada, los anunciantes pueden establecer la configuración de Privacidad Avanzada para cada ad network individualmente.

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**Para desactivar la Privacidad Avanzada de un partner:**

1. Verifica que el selector central de la AAP esté desactivado, en la página **Configuración de la aplicación**.
2. En el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
3. Selecciona la ad network.
4. En la pestaña **Integración**, desactiva la **Privacidad avanzada.**

**Cambiar la configuración de la AAP e impacto en la configuración de Privacidad avanzada del partner**

Como se indicó anteriormente, la configuración de la AAP anula la configuración de privacidad avanzada (AP) a nivel de partner. Sin embargo, si más tarde desactivas la AAP (el selector central), la configuración de Privacidad avanzada a nivel de partner individual vuelve a su estado anterior. Es decir, de la siguiente manera:

* En el pasado, has desactivado la AAP y algunas configuraciones de AP de partners.
* Más tarde activas la AAP. Recuerda, cuando la AAP está activada, anula la configuración de los partners y se considera que todos los partners están activados.
* Ahora vuelves a desactivar la AAP. Es decir, se aplican las configuraciones individuales de los partners. Entonces, para algunos partners, la configuración ya está desactivada.

</Accordion>

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

## Implicaciones de la Privacidad Avanzadas Agregada para tus partners

<div id="ad-networks" />

<Accordion title="Redes publicitarias">

<div id="postbacks-to-ad-network-partners" />

#### **Postbacks a partners de ad networks**

La <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">AAP afecta a las ad networks</Anchor> en relación con los datos que se comparten con ellas y se alinea con los principios de AAP que se aplican a los anunciantes en el contexto de una ad network. Los datos compartidos con las ad networks se realizan a través de postbacks, que difieren entre la ad network atribuida y la no atribuida.

Las reglas de compartición de datos descritas se aplican a una ad network determinada si cualquiera de los siguientes selectores está activado:

* AAP: Toggle a nivel de aplicación
* AP: Toggle a nivel de partner

<div id="postbacks-for-attributed-ad-networks" />

#### **Postbacks para ad networks atribuidas**

En el caso de la red atribuida, el tipo de postback utilizado para compartir datos depende del estado de consentimiento del usuario de la siguiente manera:

* **Usuarios que dan su consentimiento:** Postback regular que contiene datos de atribución a nivel de usuario, incluidos identificadores.
* **Usuarios de iOS que no dan su consentimiento:** Postback de Privacidad Avanzada (AP) que contiene datos de atribución limitados. Contiene detalles de la campaña y no identificadores.
  * **Requisito previo:** Para que una ad network obtenga postbacks de AP, debe tener integración de AP con AppsFlyer. Sin la integración, no se envía ningún postback para los usuarios que no dan su consentimiento.
  * **Excepción:** Para las instalaciones atribuidas a Apple Search Ads (ASA), cuando una ad network que no admite Privacidad Avanzada establece los postbacks de instalación en **Todas las fuentes de medios, incluidas las orgánicas**, Apple Search Ads (ASA) aún envía postbacks de instalación a ad networks independientemente del estado de Privacidad Avanzada del lado del anunciante.

Los diversos escenarios de consentimiento del usuario y los tipos de postback utilizados se ilustran en la siguiente figura.

![AAP: anuncio atribuido networks.png](https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png)

La privacidad avanzada se comporta de manera diferente cuando se sirve en la web y se debe utilizar el parámetro af\_media\_type=web o af\_media\_type=app. Consulta <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campañas-web">aquí</Anchor> para obtener más información.

<div id="postbacks-for-unattributed-partners" />

#### **Postbacks para partners no atribuidos**

Los postbacks no atribuidos se envían a una red cuando la opción de envío en la pestaña de integración del partner integrado está establecida en *todas las fuentes de medios, incluidas las orgánicas* y ese partner no se atribuye al evento como se ilustra en la figura siguiente.

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

Los diversos escenarios de consentimiento del usuario y el tipo de postback utilizado se ilustran en el siguiente diagrama de flujo.

![AAP - Unattributed ad networks.png](https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png)

La privacidad avanzada se comporta de manera diferente cuando se sirve en la web y se debe utilizar el parámetro af\_media\_type=web o af\_media\_type=app. Consulta <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campañas-web">aquí</Anchor> para más información.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Partners de análisis">

La AAP afecta a los partners de análisis en relación con los datos compartidos con ellos y está alineado con los principios de AAP que se aplican a los anunciantes en el contexto del partner de análisis.  Los datos se comparten con el partner a través de postbacks.

Las reglas de compartición de datos descritas se aplican a un partner determinado si cualquiera de los siguientes selectores está activado:

* AAP: Toggle a nivel de aplicación
* AP: Toggle a nivel de partner

Los postbacks que contienen datos de atribución a nivel de usuario, incluidos los identificadores de usuarios, se envían para los usuarios que dan su consentimiento. No se envían postbacks en el caso de usuarios que no dan su consentimiento.

Los diversos escenarios de consentimiento del usuario y el tipo de postback utilizados se ilustran en la siguiente figura.

![AAP - Analytics partner.png](https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png)

La privacidad avanzada se comporta de manera diferente cuando se sirve en la web y se debe utilizar el parámetro af\_media\_type=web o af\_media\_type=app. Consulta <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campañas-web">aquí</Anchor> para obtener más información.

</Accordion>

<div id="agencies" />

<Accordion title="Agencias">

**Disponibilidad de datos**: El impacto de AAP en las agencias es similar al de los anunciantes. Si el raw data está disponible para la agencia para una aplicación determinada y la AAP se aplica a los datos de un usuario determinado, los datos están disponibles de acuerdo con las reglas de [datos de atribución limitada para anunciantes](/docs/apply-aggregated-advanced-privacy-framework#principios-de-disponibilidad-de-datos-en-la-privacidad-avanzada-agregada).

**Agencia que cambia la configuración de Privacidad avanzada de una ad network:**

* Si la AAP está desactivada, se puede establecer la configuración de Privacidad Avanzada de cada partner integrado.
* De forma predeterminada, solo los anunciantes pueden cambiar la configuración de Privacidad Avanzada; sin embargo, el anunciante puede dar permiso explícito a la agencia para establecer la configuración de Privacidad Avanzada de las ad networks habilitadas por la agencia.

**Otorgar permiso a una agencia para establecer la Privacidad Avanzada**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

**Para permitir que una agencia establezca la Privacidad Avanzada**:

1. En el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Seleccionar la agencia.
3. En la pestaña **Permisos**, activa **Cambiar** **la configuración de privacidad avanzada.**
4. Haz clic en **Guardar**.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Guía de privacidad avanzada y framework de postback para ad networks</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=framework-de-privacidad-avanzada-agregada-aap h_01HDPDE0H3SYFWBHK59HBV2P6N=framework-de-privacidad-avanzada-agregada-aap aapimpacted-features=funciones-afectadas-por-la-aap h_01HDPDE0H339BPACN235V70MWW=funciones-afectadas-por-la-aap data-availability-principles-in-aggregated-advanced-privacy=principios-de-disponibilidad-de-datos-en-la-privacidad-avanzada-agregada h_01HDPDE0H3QBE60DVBZ1MWNB9N=principios-de-disponibilidad-de-datos-en-la-privacidad-avanzada-agregada paid-and-owned-media-data-availability=disponibilidad-de-datos-de-medios-pagados-y-propios h_01HDPDE0H326EXNCQHPVJWXK3H=disponibilidad-de-datos-de-medios-pagados-y-propios h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=disponibilidad-de-datos-de-medios-pagados-por-estado-de-la-att h_01HDPDE0H3SACYAV19WQD9TCQ3=disponibilidad-de-datos-de-medios-pagados-por-estado-de-la-att h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=controlando-la-privacidad-agregada-avanzada h_01HDPDE0H4VQC2DWAV68Q9VDVQ=controlando-la-privacidad-agregada-avanzada h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap-habilitada h_01HDPDE0H4SC810EBK7ZGQ02K0=aap-habilitada aap-disabled=aap-deshabilitada h_01HKHPGQ1R6HZEXSRTX7ATVWE9=aap-deshabilitada h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=implicaciones-de-la-privacidad-avanzadas-agregada-para-tus-partners h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=postbacks-a-partners-de-ad-networks h_01HDPDE0H47ENYTWRVFPX0VTZC=postbacks-a-partners-de-ad-networks postbacks-for-attributed-ad-networks=postbacks-para-ad-networks-atribuidas h_01HDPDE0H4B01YG577QZCG7TA7=postbacks-para-ad-networks-atribuidas postbacks-for-unattributed-partners=postbacks-para-partners-no-atribuidos h_01HDPDE0H63ZMV255SN7EKDRMV=postbacks-para-partners-no-atribuidos h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=consulta-tambi%C3%A9n" />
