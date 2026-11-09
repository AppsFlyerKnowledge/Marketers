---
title: Configuración de campañas de RZR (anteriormente Aarki)
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-09-11T00:23:35Z'
  id: 360000423105
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360000423105
---
> **De un vistazo:** RZR, un partner integrado de la ad network de AppsFlyer, es un DSP móvil muy conocido. RZR ofrece atribución móvil basada en clics y view-through. Además, RZR también ofrece retargeting basado en clics que puedes registrar con AppsFlyer.

<Image align="center" alt="Logotipo horizontal de RZR con degradado negro (3).png" src="https://files.readme.io/b1064bdec0e836399c583c3f55e5e79a81380a9a8d86eeaee19391b6d09f2bbd-small-46161100230545.png" width="58.83%" />

<div id="setting-up-rzr" />

## Configuración de RZR

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>En la **primera visita**, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El interruptor DEBE estar ENCENDIDO mientras trabajes con el partner. Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention"><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como ad network de TODAS las instalaciones, RZR prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a RZR.

<div id="general-settings" />

### Configuración general

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**ID de socio**

<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>RZR se conecta con AppsFlyer a través de un ID de red único. Si todavía no tienes el ID de red, debes obtenerlo de RZR para continuar con la integración.

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**Habilitar la atribución por impresiones**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>Pon esta opción en ON si quieres atribuir instalaciones view-through de RZR. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>Envía postbacks automáticos a RZR después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a RZR. Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para reportarla a RZR.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>En esta sección, puedes asignar tus eventos de AppsFlyer a RZR mediante postbacks.

**Para configurar postbacks de eventos in-app:**

1. Activa **Postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Nota |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de socio** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono de **Agregar condición**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
4. Haz clic en **Guardar integración**.
5. [Opcional] Tras guardar la integración, mientras permanezcas en la página de configuración, puedes integrar más aplicaciones con el socio:
   1. Desde la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente de la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a RZR para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de RZR. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span>Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* <span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span>**<span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>Campaña** - añádela para comparar diferentes campañas en funcionamiento con Aarki. **Parámetro de enlace de atribución:** c
* <span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span>**Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Aarki. **Parámetro de enlace de atribución:** af\_adset
* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**Nombre del anuncio** - configura nombres de conjuntos de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos en campañas específicas de Aarki. **Parámetro del enlace de atribución:** af\_ad
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit"><span id="01ECJ9TJKGEPHEXZ60NAN9JPWG"></span>superar las limitaciones del ID de sitio</Anchor>. **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de datos sin procesar, lo que los hace muy útiles para realizar la agregación o el filtrado de datos. **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**<span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>sobre la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>Cuando esta opción está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide"><span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir &is\_retargeting=true al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clics y no con la atribución view-through.**Parámetro del enlace de atribución:** is\_retargeting.

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1. Enlace estándar vs. OneLink

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>Selecciona la opción ***enlace de atribución estándar*** si:

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>No necesitas un enlace profundo con la URL o
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>Planeas usar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>esquemas de URI</Anchor> para deep linking

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>Selecciona ***Use OneLink*** para:

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>Utilizar un solo enlace para aplicaciones de Android y iOS, o
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>Ten en cuenta que al seleccionar OneLink, el enlace de registro de clics cambia de una URL específica de la aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>URL de OneLink</Anchor>.

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. URL de deep link

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>Utiliza este campo si el enlace está pensado para dirigir a los usuarios mediante deep linking a cualquier actividad específica dentro de tu aplicación.**Parámetro del enlace de atribución:** af\_dp Puedes encontrar más información sobre la solución de deep linking de AppsFlyer en <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink"><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>esta guía.</Anchor>

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3. Ventana de recaptación

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span>**Parámetro del enlace de atribución:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribución por clic

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeros inicios) que se produzcan dentro de la ventana de lookback pueden atribuirse a RZR.

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span>**Parámetro del enlace de atribución:** af\_click\_lookback

<span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows"><span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span>ventana de lookback de clics aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a RZR para que se active cuando los leads hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>Este control deslizante te permite establecer el **tiempo máximo entre la impresión y la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a RZR, siempre que no haya habido ningún otro clic en el anuncio correspondiente.

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>atribución view-through aquí</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a RZR para que se active cuando se vea un anuncio correspondiente, generalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual. 

<div id="warning" />

#### Advertencia

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>Una vez definido el costo en RZR, no cambies el nombre de ninguna campaña, conjunto de anuncios o anuncio individual en funcionamiento, ya que esto puede causar discrepancias graves o la falta de datos de costos.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

<span id="01ECJ9TJKQNQBY77FTTFRZ0PGS"></span>RZR no admite datos de ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a RZR, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para RZR, la pestaña de permisos seguirá activa y podrás otorgarle el control a RZR.

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>Permitir la configuración de la integración*** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* <span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span><span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

<span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span>permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>Selector principal*** - actívalo para mostrar las opciones de permisos de la agencia
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span>***Permitir la configuración de postbacks de eventos in-app*** - permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir el acceso a tu reporte de retención*** - solo para los propios datos de retención de la agencia

<span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia"><span id="01ECJ9TJKRMD549KXA59E682CH"></span>permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-aarki=configuraci%C3%B3n-de-rzr h_01HJR5M5C0P759S4X5SSJCY501=configuraci%C3%B3n-de-rzr h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab activate-partner=activar-socio 01ECJ9TJKE15MJE7WS26VP52A0=activar-socio h_01J4KWRE6ECKEWEG4WP10N3BF7=nota general-settings=configuraci%C3%B3n-general 01ECJ9TJKFGQQVWA7SA3PRS690=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados 01ECJ9TJKF7G9KMGMGMAD414ZF=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app 01ECJ9TJKFWH38NKYPDEZR4FRV=configuraci%C3%B3n-de-eventos-in-app h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n 01ECJ9TJKFD91X9DQXB8PV3840=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting 01ECJ9TJKGJF1FS642MEM6WX4A=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic 01ECJ9TJKHWMXAZYWNMVPDS8NY=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n 01ECJ9TJKJ0EQE45TB9S0WS2ZB=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through 01ECJ9TJKJ72AN26F2FQ8VVKQ4=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones 01ECJ9TJKJZV9PADNEETA6GFRZ=enlace-de-atribuci%C3%B3n-de-impresiones h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab warning=advertencia 01ECJ9TJKQ8A7BFZR3MJ5H35CA=advertencia h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab ad-network-permissions=permisos-de-ad-network 01ECJ9TJKQ9E3A5863Z3TRVAWZ=permisos-de-ad-network agency-permissions=permisos-de-la-agencia 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=permisos-de-la-agencia" />
