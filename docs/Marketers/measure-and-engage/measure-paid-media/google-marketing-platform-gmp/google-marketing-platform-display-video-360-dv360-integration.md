---
title: >-
  Plataforma de marketing de Google: integración de Display & Video 360
  (DV360)
metadata:
  keywords:
    - Advertisers
    - Agencies
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
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2026-09-11T00:27:50Z'
  id: 360017595598
  locale: es
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/es/articles/360017595598
---
> **De un vistazo:** Google Marketing Platform: Display & Video 360 (GMP-DV360) es un partner de la red de autoinformes (SRN) de AppsFlyer que combina publicidad y análisis. La integración entre GMP-DV360 (dv360\_int) combina publicidad y análisis para mejorar las conexiones con los clientes, revelar información y mejorar los resultados de marketing.

> 🚧 **¡Importante!**
>
> Consulta el boletín sobre <Anchor target="_blank" href="/marketers/es/docs/bulletin-supporting-the-new-google-eu-consent-policy">cómo respaldar la nueva política de consentimiento de Google de la UE</Anchor>.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

## Resumen general

La integración GMP-DV360 utiliza el ID de enlace para la medición de la conversión. Puedes trabajar directamente con GMP-DV360, a través de una agencia o de ambas formas, mediante las siguientes integraciones:

* [DV360 para anunciantes](#configuración-de-gmp-dv360-para-anunciantes): Completar una vez: obligatorio
* [DV360 para agencias](#configuración-de-gmp-dv360-para-agencias): Opcional por agencia

> 📘 **Nota**
>
> Recuerda lo siguiente:
>
> * La integración GMP-DV360 está diseñada para reemplazar la integración Legacy GMP DV360/CM (doubleclick\_int), que quedará obsoleta a finales del segundo trimestre de 2024.
> * Para usar la API, ponte en contacto con tu administrador de cuentas de GMP-DV360.

La siguiente tabla describe las soluciones de integración GMP:

| Solución MMP | Descripción | Medidas necesarias para la integración |
| --- | --- | --- |
| DV360 | Integra DV360 con AppsFlyer para medir la atribución de dv360\_int | Completa la integración de los [anunciantes](#configuración-de-gmp-dv360-para-anunciantes) |
| CM360 y DV360 | Compra tráfico de DV360 a través de CM360, medido como atribución de dv360\_int en AppsFlyer. | Completa la integración de los [anunciantes](#configuración-de-gmp-dv360-para-anunciantes) |
| CM360 y fuente de medios de terceros que no sean DV360 | Compra de tráfico de fuentes de medios de terceros y medición de las conversiones de aplicaciones móviles originadas por este tráfico en CM360. | <Anchor target="_blank" href="/marketers/es/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">Mida el tráfico de terceros con CM360</Anchor> |

### Intercambio de datos entre AppsFlyer y GMP - DV360

**Datos proporcionados por AppsFlyer:** AppsFlyer envía postbacks de mensajes a GMP-DV360 en relación con las conversiones y los eventos in-app.

**Datos proporcionados a AppsFlyer:** Cuando GMP-DV360 solicita una conversión, proporciona a AppsFlyer los parámetros de la fuente multimedia. Estos parámetros completan los reportes de análisis y raw data. La siguiente tabla muestra los parámetros de asignación para GMP-DV360 y AppsFlyer.

| GMP | AppsFlyer |
| --- | --- |
| `Tipo de interacción` | `tipo_táctil_atribuido` |
| `timestamp` | `Se establece como TRUE o FALSE.` |
| `line_item_id` | `id_campaña` |
| `Nombre del artículo de línea` | `campaign_name` |
| `Creative ID` | `id_adset` |
| `product_type` | `af_canal` |
| `external_customer_id` | `network_account_id` |
| `id_sitio` | `af_siteid` |
| `insertion_order_id` | `af_sub4` |

## Configuración de GMP-DV360 para anunciantes

**Requisitos previos** 

Antes de configurar la integración, asegúrate de:

* <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">Ponte en contacto con el partner</Anchor> y abre una cuenta con él.
* <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">Obtén el ID de enlace de GMP-DV360</Anchor>.

  > 📘 **Nota:**
  >
  > El ID de enlace de DV360 debe cumplir con lo siguiente:
  >
  > * Debe contener números y letras.
  > * Debe tener más de 20 caracteres.
  > * Android y iOS deben usar cada uno un ID de enlace diferente.


**Para configurar una nueva integración:**  
  
**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

Cuando AppsFlyer consulta GMP-DV360, devuelve los parámetros que aparecen en su respuesta. Estos se asignan a los parámetros de AppsFlyer y al raw data como se detalla en la siguiente tabla.

| GMP: parámetro heredado | Parámetro GMP-DV360 | Parámetro de AppsFlyer | URL del parámetro |
| --- | --- | --- | --- |
| Placement ID | Nombre del artículo de línea | Nombre de la campaña | C |
| Placement ID | ID de artículo de línea | ID de campaña | af\_c\_id |
| ID de sitio | ID de sitio | ID de sitio | af\_siteid |
| Creative ID | Creative ID | ID de anuncio | id\_del\_anuncio\_af |

<span id="activate-partner::e4f2f638"></span>La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

#### Activar partner

Para configurar la integración, primero debes activar el selector **Activar partner**. Aprende más sobre integraciones de <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activación y desactivación de partners</Anchor>

#### Configuración general

**ID de enlace:** Introduce el ID del enlace mencionado en los requisitos previos.

**Usuarios no pertenecientes a la UE:** Decide activar o no a los <Anchor target="_blank" href="/marketers/es/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**usuarios no pertenecientes a la UE**</Anchor>.

<Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

#### Atribución de instalación.

Configura las distintas ventanas de atribución para atribuir las nuevas instalaciones (primeros lanzamientos) de los usuarios que han visto o hecho clic en tu anuncio. Esto significa el tiempo máximo desde el clic o la vista hasta la instalación. Solo las instalaciones realizadas en la ventana retrospectiva pueden atribuirse a Google Marketing Platform: Display & Video 360 (DV360).

1. Establece la **ventana retrospectiva de instalaciones por clics** en 1 a 23 horas o 1 a 30 días.
2. [Opcional] Activa **Instalar la atribución por impresiones** y establece la ventana retrospectiva en 1 a 23 horas o 1 a 30 días.

#### Atribución de re-engagement

Configura las diferentes ventanas de atribución para atribuir los re-engagements de los usuarios actuales que han visto o hecho clic en tu anuncio. Tenga en cuenta que solo las re-engagements dentro de la ventana retrospectiva pueden atribuirse a GMP-DV360.

1. Establece la **ventana retrospectiva de re-engagements por clics** en de 1 a 23 horas o de 1 a 30 días.
2. [Opcional] Activa la <strong>Atribución de re-engagements</strong> por impresiones para establecer las ventanas restrocpectivas en de 1 a 23 horas o de 1 a 7 días.

> 📘 **Nota:**
>
> No se admite la reatribución en las campañas de DV360

Aprende más sobre las <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#reengagement-rules-and-windows">reglas y ventanas</Anchor> de re-engagement.

#### Ventana de recaptación

Establece la ventana de tiempo durante la cual los eventos in-app se atribuyen principalmente a la conversión del reengagement. <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#setup-reengagement-window">Aprender más</Anchor>.

* Establece la **Ventana de re-enagements** en 1 a 23 horas, 1 a 90 días o **de por vida**.

#### Ignorar a los usuarios activos para el retargeting

Establece el período de tiempo de la ventana para <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window#periodo-de-inactividad">ignorar los re-engaments y reatribuciones</Anchor> de los usuarios que lanzaron tu aplicación. Esto significa que su actividad durante el período de tiempo no se registra en AppsFlyer.

> 📘 **Nota**
>
> **Se registran las conversiones de re-engagements y reatribución de los usuarios que estuvieron** inactivos durante **el período establecido.**

1. Activa **Ignorar usuarios activos para el retargeting**.
2. Configura la ventana de inactividad.

#### Postbacks de eventos in-app

Configura la asignación de los eventos in-app con los eventos de GMP-DV360 enviados mediante postbacks:

1. Activa **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Cuadro desplegable:** Selecciona el evento de AppsFlyer predefinido más adecuado.</li></ul>**Nota:**<ul><li>Se recomienda seleccionar un evento estándar de la lista. Sin embargo, para varios eventos CUSTOM, es mejor especificarlos de forma exclusiva, como CUSTOM\_1 y CUSTOM\_2. Esto ayudará a distinguir entre eventos en DV360/CM360.</li><li>Los eventos de AppsFlyer (como`af_purchase`, etc.) siempre se envían con `u` variables, por ejemplo,. `u24=` Esto te ayuda a identificarlos en el CM360, incluso cuando se envían como personalizados.</li><li>CM360 permite un máximo de 10 eventos en total, que pueden ser eventos personalizados o estándar.</li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner** (predeterminado): Envía postbacks solo cuando este evento se atribuya a GMP-DV360.</li><li>**Todas las fuentes de medios, incluidas las orgánicas.** : Envía postbacks para eventos atribuidos a cualquier partner, así como eventos orgánicos.</li></ul> |
| **Incluye** | <ul><li>**Sin valores ni ingresos** (predeterminado):  envía solo el evento en sí sin ningún valor de evento.</li><li>**Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de los ingresos (si existe en el evento).</li></ul> |

3. [Opcional] Haz clic en el icono de **Agregar condición**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
4. Haz clic en **Guardar integración**.
5. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con GMP-DV360:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

> 📘 **Nota**
>
> Solo para aplicaciones iOS: El control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado en el que se active la opción **Privacidad avanzada (para iOS 14.5 y versiones posteriores)**.

#### Asignación de parámetros:

AppsFlyer admite el envío de parámetros adicionales (parámetros u), limitados hasta u26. Los parámetros U están preasignados y fijos por parte de AppsFlyer. Ten en cuenta lo siguiente:

* Como estos parámetros están preasignados, no se pueden configurar parámetros U personalizados adicionales.
* Si faltan datos para un parámetro U específico, AppsFlyer no lo enviará. Por ejemplo, si faltan los datos del proveedor, AppsFlyer no envía U5.

| Parámetro U | Nombre | Valor de ejemplo |
| --- | --- | --- |
| u1= | ID de dispositivo de AF | 1540995037437-2811776739500410055 |
| u2= | ID de usuario de cliente | eaf8a5f2.1836.4686 |
| u3= | **Android**:  <br />ID de publicidad  <br />**iOS**: idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | wifi | Verdadero |
| u5= | Parámetro booleano, verdadero o falso. | Jio%204G |
| u6= | código de país | India |
| u7= | Región | HR |
| u8= | Ingresos por eventos en USD | Gurgaon |
| u9= | tipo de dispositivo | motorola::Moto G (4) |
| u10= | versión de SO | 7 |
| u11= | versión de SDK | v4.8.18 |
| u12= | versión de aplicación | 3.31.1 |
| u13= | marca de tiempo de instalación | 1540995041 |
| u14= | hora de clic | 1546441586 |
| u15= | hora de impresión | 1546441586 |
| u16= | nombre de campaña* | Appinstall\_campaign |
| u17= | ID de campaña | 12345ABC |
| u18= | nombre de conjunto de anuncios* | Appinstall\_adset |
| u19= | ID de conjunto de anuncios | 12345ABC |
| u20= | nombre del anuncio* | Appinstall\_ad |
| u21= | ID de anuncio | 1234567ABCDE |
| u22= | ID de sitio | site\_id\_123456 |
| u23= | hora del evento | 2019-01-04 12:56:35.707 |
| u24= | nombre del evento | af\_compra |
| u25= | valor del evento | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | moneda | EUR |

* Si AppsFlyer no recibe este nombre de parámetro en la respuesta de GMP-DV360, rellena el campo con el ID correspondiente. Por ejemplo, el nombre del conjunto de anuncios mostrará el ID del conjunto de anuncios, que es. `12345ABC`

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Es posible **usar los enlaces de atribución de AppsFlyer con DV360 solo para registrar clics e impresiones**. Estos enlaces NO se emplean para la atribución, y cualquier información adicional que contengan no se analiza ni se utiliza con ningún propósito.

Si quieres medir el número de clics de DV360 en AppsFlyer, debes agregar una dirección URL de atribución de AppsFlyer en el panel de control de DV360. Al hacerlo, asegúrate de que el nombre de la campaña en la URL de atribución **sea idéntico** al Placement ID en DoubleClick (de ser posible) para que AppsFlyer pueda recuperar y anexar los datos de clics en las campañas correctas.

> 🚧 **Importante:**
>
> El uso de enlaces de atribución para **DV360** no es obligatorio.
>
> **Limitación:** Los enlaces de atribución para DV360 que incluyen el parámetro `af_prt` actualmente **no son compatibles con las cuentas de agencia**.

**Si deseas contar clics en AppsFlyer, usa este enlace:**

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

Si deseas contar **impresiones** en AppsFlyer, usa este enlace:

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Pestaña de costos (para costos, clics e impresiones)">

Costo, clics e impresiones son compatibles con esta integración a través de ROI360.

Los clientes de ROI360 pueden crear y editar integraciones de costos en la **pestaña Costo** y en **Configuración de costos**. Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">cómo habilitar la integración de costos</Anchor>.

A partir del 7 de septiembre de 2026, los clics y las impresiones dejarán de reportarse mediante la atribución. Para seguir recibiendo estas métricas, configura la integración de DV360 SRN/Costo.

> 📘 **Anunciante**
>
> Los clics y las impresiones de esta integración se reportan en:
>
> * Paneles de control
> * Informes ETL de costos (solo para clientes de ROI360)
> * Las API agregadas de AppsFlyer
>
> Según cuándo se active la integración de DV360, puede producirse una discrepancia temporal en cada uno de los elementos anteriores:
>
> * Si la activación se realiza el 6 de septiembre o antes, los clics y las impresiones se reportan dos veces durante este periodo: una mediante la atribución de AppsFlyer y otra mediante la API de DV360, por lo que se espera una discrepancia temporal.
> * Activación hasta el 12 de septiembre: se espera una discrepancia en algunas fechas debido al auto-backfill de los últimos 7 días de DV360.
> * Activación después del 12 de septiembre: no se espera ninguna discrepancia.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no son compatibles con esta integración.

</Accordion>

## Configuración de GMP-DV360 para agencias

Las agencias pueden realizar campañas con GMP-DV360 en tu nombre.

#### Configuración de agencias

| Procedimiento realizado por | Procedimiento |
| --- | --- |
| AppsFlyer | <ol><li>Comprueba que has completado la integración entre GMP-DV360 del anunciante.</li><li>En AppsFlyer, en el menú lateral, selecciona Colaborar> **Integraciones activas**.</li><li>Selecciona una agencia.</li><li>Ve a la pestaña de **Permisos** , and desactiva **Permisos de agencias**.</li><li>[Opcional] En la pestaña **Integración**, activa la función de **Postback de eventos in-app**. Esto permite a la agencia activar o desactivar los postbacks por su parte.</li></ol> |
| Agencia | <ol><li>En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.</li><li>Selecciona **Google Marketing Platform - Display & Video 360 (DV360).**</li><li>Ve a la pestaña **Integración**.<br />Se muestra el estado de la integración con GMP. [![mceclip2.png](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)</li><li>Verifica que **Activar Partner** esté **encendido.** Si este no es el caso, el anunciante debe completar la integración de [Integración de GMP-DV360 del anunciante](#configuración-de-gmp-dv360-para-anunciantes).</li><li>Comprueba que los ajustes restantes, como las ventanas retrospectivas y la asignación de eventos in-app, sean correctos. Si es necesario, pídele al anunciante que haga cambios.</li><li>Introduce uno o varios **ID de anunciante de DBM**. El identificador está disponible en tu <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/3423704?hl=en&ref_topic=9133452">panel de control de GMP</Anchor>.</li><li>Haz clic en **Guardar**.</li></ol> |

## Discrepancias entre GMP-DV360

Consulta los posibles motivos de las discrepancias y cómo minimizarlos:

| Causa | Descripción | Consejo de AppsFlyer |
| --- | --- | --- |
| Ventana de atribución por impresiones | Las impresiones en la ventana de atribución de DV360/CM360 son de 14 días, mientras que la ventana predeterminada de AppsFlyer es de 1 día. | Para reducir la discrepancia, configura la ventana de view-through en AppsFlyer en el máximo de 7 días. |
| Asignación incorrecta | La asignación entre AppsFlyer y GMP-DV360 no es correcta. | <ul><li>Verifica el ID del enlace</li><li>Verifica que los eventos in-app estén asignados correctamente</li></ul> |

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data">Configurar la API de costos de ROI360 para medir los datos de costos</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Atribución de Retargeting de AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Mapeo de eventos personalizados</Anchor>

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=importante overview=resumen-general 01H8E4ZJNRMXY183TQCPW15ZQB=resumen-general 01H8DYEV7JPV80T3YAJQQHBA6C=nota data-sharing-between-appsflyer-and-gmp=intercambio-de-datos-entre-appsflyer-y-gmp---dv360 h_01HQ0QJJRMYP3E6B5FVA0V6861=intercambio-de-datos-entre-appsflyer-y-gmp---dv360 advertiser-gmp-integration=configuraci%C3%B3n-de-gmp-dv360-para-anunciantes 01H8DYEV7KYNB2FJG7N1CTEE86=configuraci%C3%B3n-de-gmp-dv360-para-anunciantes h_01KC714WNQWGCM1C1MC8S2PZXH=nota-1 h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=activar-partner general-settings=configuraci%C3%B3n-general 01H8VVCC8GSDPSNN0AJPVZPR8P=configuraci%C3%B3n-general install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n 01H8VVCC8GK8VFPBEPAMVHCAWM=atribuci%C3%B3n-de-instalaci%C3%B3n reengagement-attribution=atribuci%C3%B3n-de-re-engagement 01H8VVCC8HHG5290PYF0BT29QA=atribuci%C3%B3n-de-re-engagement h_01K4AFW71RG9YE5EJE1FQCN4SE=nota-2 reengagement-window=ventana-de-recaptaci%C3%B3n h_01HQ06JCJZD6AMFR2B6GTMSM9S=ventana-de-recaptaci%C3%B3n ignore-active-users-for-retargeting=ignorar-a-los-usuarios-activos-para-el-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-a-los-usuarios-activos-para-el-retargeting h_01HMXNJVHK9C3FT8E04RE0TH99=nota-3 inapp-event-postbacks=postbacks-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postbacks-de-eventos-in-app 01H8VVCC8HDMTY1P2SG31HD61K=nota-4 parameter-mapping=asignaci%C3%B3n-de-par%C3%A1metros h_01HBBJQZSTT1HFENXNACMHFC18=asignaci%C3%B3n-de-par%C3%A1metros 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=importante-1 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions h_01_dv360_cutover_discrepancy=anunciante 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab setting-up-gmp-dv360-for-agencies=configuraci%C3%B3n-de-gmp-dv360-para-agencias 01H8VVCC8HVNNQ9PJS4ZQCVDNS=configuraci%C3%B3n-de-gmp-dv360-para-agencias agency-setup=configuraci%C3%B3n-de-agencias 01H8DYEV7MNFFY9ESFF2S3ETEB=configuraci%C3%B3n-de-agencias gmp-discrepancies=discrepancias-entre-gmp-dv360 01H8DYEV7MTPJMY12AVHX45YFF=discrepancias-entre-gmp-dv360 h_01KYS9JJ9RSTDPHRZWW47DN438=v%C3%A9ase-tambi%C3%A9n" />
