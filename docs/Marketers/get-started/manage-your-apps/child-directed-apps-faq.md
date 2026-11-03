---
title: 'Aplicaciones para niños: Preguntas frecuentes'
metadata:
  keywords:
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-08-12T12:05:03Z'
  id: 18324823209745
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/18324823209745
---
**En resumen:** Obtén respuestas a preguntas frecuentes sobre apps para niños.

## Visión general

Existen muchas políticas, leyes y regulaciones sobre aplicaciones para niños para proteger la privacidad de ellos. Los principales son [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) y [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1). En los últimos años, plataformas como iOS y Android han implementado políticas para mejorar la privacidad de los niños. Al crear una app, una de las primeras cosas que hay que hacer es determinar si está dirigida solo a niños o a un público mixto (tanto niños como adultos). Aprende de <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">esta guía</Anchor> cómo implementar una solución de atribución compatible para aplicaciones dirigidas a niños.

## Agregando una aplicación para niños

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="¿Qué pasos debo seguir al agregar una aplicación para niños?">

1. <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Sigue el Agregar una app wizard</Anchor>.
2. Para el paso 2 del wizard, <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#definir-el-público-objetivo-de-la-aplicación">consulta las instrucciones sobre las aplicaciones para niños</Anchor>.
3. Después de agregar la aplicación:
   * Implementa la <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#implementación-de-la-clave-de-desarrollo-en-tu-aplicación">clave de desarrollo</Anchor> en el SDK
   * Incluye <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">controles de privacidad</Anchor> adecuados

 Descubre más detalles sobre la [implementación de herramientas de cumplimiento de normas con redes publicitarias](#implementando-las-herramientas-de-cumplimiento-de-appsflyer).

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="Al agregar una nueva aplicación, ¿qué sucede después de marcarlo como dirigido para niños?">

Dos semanas después de agregar la aplicación, recibirás una notificación pidiéndote que confirmes que has implementado controles de privacidad para tus aplicaciones para niños. Después de confirmar, recibirás un mensaje de confirmación. Siempre puedes acceder al mensaje de confirmación desde el centro de notificaciones o ver los detalles de confirmación en el <Anchor target="_blank" href="/marketers/es/docs/audit-log">registro de auditoría</Anchor>.

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="¿Puedo cambiar mi selección de una aplicación para niños?">

En esta etapa, una vez que seleccionas si una aplicación está dirigida a niños o no, tu selección no se puede revertir. Esta opción solo es posible mientras se agrega la aplicación.

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="¿Cómo puedo ver si alguien de mi equipo marcó una aplicación como dirigida a niños?">

Una vez confirmado que una aplicación es para niños, hay dos formas de ver la confirmación:

* **Centro de notificaciones:** En la barra de menú, haz clic en el icono de notificaciones![icon del centro de notificaciones.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png) y busca la notificación de confirmación.
* **Registro de auditoría:**
  1. Desde la barra del menú, accede al menú de usuario (desplegable de correo electrónico).
  2. Selecciona **Centro de seguridad**.
  3. En la sección**Registro de auditoría** , haz clic en **Ver registro de auditoría.**.Puedes ver los detalles de confirmación en el servicio **Mis aplicaciones**.

</Accordion>

## Implementando las herramientas de cumplimiento de AppsFlyer

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="¿Cómo sé qué herramienta utilizar?">

Cuando tu app está pensada para niños o un público mixto (niños y adultos), puedes usar cualquiera de las herramientas recomendadas de <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">esta guía</Anchor> que se alineen con los requisitos legales. Descubre más recursos del SDK en la parte inferior de esta página. 

#### Ejemplos de herramientas de cumplimiento de normas y su uso

<table><thead><tr><th>Herramienta</th><th>apps de iOS,</th><th>Android</th><th>Disponibilidad de raw data</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">SDK estricto</a>: </p><p>Asegura que el IDFA no se envíe a AppsFlyer. Por lo general, esto se recomienda para aplicaciones para niños.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Disponible solo para anunciantes</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p>El SDK estándar que utiliza la API <a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisabadvertisingIdentifiers</kbd></a> :</p><p>Asegura que AAID (ID de publicidad de Android de Google) no se envía a AppsFlyer. Por lo general, esto se recomienda para aplicaciones para niños.</p></td><td>- </td><td><span><span>✓</span></span></td><td>Disponible solo para anunciantes</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p>El SDK estándar con una age gate (puerta de edad) que utiliza la <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">función<kbd>setSharingFilterForPartners</kbd></a>  para redes publicitarias <strong>específicas</strong> : </p><p>Impide que dichas redes publicitarias accedan a los datos cuando los usuarios están por debajo de la age gate\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Limitado para redes publicitarias específicas</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p>El SDK estándar con una age gate que utiliza la <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">función<kbd>setSharingFilterForPartners</kbd></a>  para <strong>todas</strong> las redes publicitarias:</p><p>Impide que todas las redes publicitarias accedan a los datos cuando los usuarios se encuentran por debajo de la age gate\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Disponible solo para anunciantes</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">Solo SKAN</a>:</p><p>Garantiza que el ID de publicidad no se comparta con otras redes publicitarias.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Disponible solo para anunciantes</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>Soluciones sin SDK (menos recomendado):</p><p><span>Configura tus propios servidores para enviar datos a AppsFlyer como alternativa al envío de datos a través del </span><span>SDK.</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Según tu configuración</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p><a href="./apply-aggregated-advanced-privacy-framework" target="_blank">Marco de Privacidad Avanzada Agregada</a>: </p><p>Hace cumplir los niveles de privacidad de la ATT de Apple, asegurando que los datos a nivel de usuario <span>no estén disponibles </span><span>para los anunciantes o las redes publicitarias</span>.</p></td><td><span><span>✓</span></span></td><td>- </td><td>No disponible para anunciantes o redes publicitarias</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* Cuando se aplica un bloque de age gate, los datos a nivel de usuario que no se encuentran por debajo de ella están disponibles en los reporte de raw data.</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="¿Cómo afecta el uso de las herramientas de la guía a la atribución?">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">La guía de soluciones de cumplimiento de normas de AppsFlyer</Anchor> ofrece diferentes herramientas, cada una con [diferentes niveles de control](#how-do-i-know-which-tool-to-use). El impacto en la atribución varía según la herramienta específica que elijas implementar.

Cuando se utiliza una herramienta que limita el envío de datos del usuario, como el ID de dispositivo, se utilizan otros métodos de atribución, como <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">modelado probabilístico</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#install-referrer-android-only">Install referrer (para Android)</Anchor>.

Las herramientas que no envían datos a nivel de usuario se consideran que preservan la privacidad y permiten recibir datos agregados de campañas.

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="No sé si la red de anuncios con la que estoy trabajando cumple las normas, ¿qué debo hacer?">

Muchas veces no está claro si las redes publicitarias con las que colaboras cumplen con las leyes pertinentes. Puedes remitir esta pregunta a la red de anuncios. Si no cumplen con las normas o no estás seguro, puedes evitar compartir con ellos tus datos. Puedes utilizar la función **<Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`SetSharingFilterForPartners`</Anchor>** para especificar qué redes publicitarias bloquear para que no reciban los datos de tu aplicación. También puedes utilizar esta función para bloquear todas las redes publicitarias. Ver más [ejemplos de herramientas de cumplimiento de normas](#ejemplos-de-herramientas-de-cumplimiento-de-normas-y-su-uso).

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="¿Necesito implementar las herramientas de cumplimiento de AppsFlyer si la red de anuncios cumple con las normas?">

Siempre se deben implementar herramientas de cumplimiento de AppsFlyer. Cuáles son adecuados para tus necesidades depende de la audiencia de tu app. Puedes utilizar la función **<Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor>**  (“MediaSourceName”) si la red publicitaria con la que estás trabajando se ha comprometido a tratar los datos que has compartido con ellos únicamente como un procesador de datos para fines limitados permitidos por COPPA, GDPR, las leyes y reglas aplicables u otras reglas de plataforma que lo requieran y con el consentimiento adecuado.

Esto se aplica a cada una de las redes publicitarias con las que estás trabajando.

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="¿Qué datos estoy compartiendo con las redes publicitarias? ¿Qué control tengo sobre esto? ¿Qué control tengo sobre esto?">

Las redes publicitarias que no son <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRNs</Anchor> reciben tus datos mediante postbacks. Pueden definir qué eventos incluir en los postbacks. Los postbacks de instalación se envían de forma predeterminada para la atribución, mientras que los postbacks de eventos in-app solo se envían si has <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">configurado eventos específicos</Anchor> para que se envíen. Siempre que el SDK no bloquee o restrinja los postbacks, pueden contener datos a nivel de usuario relacionados con las contrataciones de los usuarios de la aplicación (instalaciones, eventos in-app y re-engagements).

A excepción de los postbacks, las redes publicitarias y las agencias tienen <Anchor target="_blank" href="/marketers/es/docs/manage-data-access-permissions">acceso limitado a los datos a través de la plataforma</Anchor>.

**Para saber qué datos se enviaron a las redes publicitarias a través de postbacks:**

* Descarga <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#postbacks">reportes de postback</Anchor> del menú **Reportes** > **Exportar Raw Data**

**Para controlar qué datos estás enviando:**

* Utiliza cualquiera de las herramientas de cumplimiento de SDK, como <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor>, para bloquear o restringir el envío de ciertos datos.
* Elige a quién estás enviando <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>, ya sea a la red de anuncios a la que se atribuye el evento o a todas las fuentes de medios, incluidas las orgánicas.

**Para controlar la disponibilidad de datos de atribución a nivel de usuario para usuarios de iOS:**

* Utiliza el <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">marco de Privacidad Avanzada Agregada</Anchor> para aplicar los niveles de privacidad de la ATT de Apple. Esto garantiza que los datos a nivel de usuario, aunque se utilizan para la atribución, no estén disponibles en AppsFlyer para anunciantes o redes publicitarias. Los datos agregados están disponibles sin limitaciones.

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="¿Necesito el SDK si mi aplicación está dirigida a niños y todas las redes publicitarias están bloqueadas?">

El SDK registra los eventos de tu app, como instalaciones, re-engagement y eventos in-app. Sin el SDK, no hay atribución. Puedes <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#privacidad-del-usuario">preservar la privacidad del usuario con el SDK</Anchor> y mostrar solo datos agregados.

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Vista general de la integración del SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">SDK: Métodos de preservación de la privacidad</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#privacidad-del-usuario">SDK: Configuración de la privacidad del usuario</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">Medidas de privacidad de AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HA20EGWDBSNAFZ7WNXJFFRRV=visi%C3%B3n-general general-questions=agregando-una-aplicaci%C3%B3n-para-ni%C3%B1os h_01H9ZK2THJVFYQ49HHRYKZZNEK=agregando-una-aplicaci%C3%B3n-para-ni%C3%B1os h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=implementando-las-herramientas-de-cumplimiento-de-appsflyer h_01HGZ5VAJHNJVM2ENFZ3DEAK42=implementando-las-herramientas-de-cumplimiento-de-appsflyer h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=ejemplos-de-herramientas-de-cumplimiento-de-normas-y-su-uso h_01HHEED2AQTW7G0MJJZDZV2B09=ejemplos-de-herramientas-de-cumplimiento-de-normas-y-su-uso standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=consulta-tambi%C3%A9n" />
