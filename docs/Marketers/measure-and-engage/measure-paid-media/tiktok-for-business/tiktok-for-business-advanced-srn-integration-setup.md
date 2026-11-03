---
title: 'TikTok for Business: configuración de integración de Advanced SRN'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-11-03T01:58:45Z'
  id: 6722785184913
  locale: es
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/es/articles/6722785184913
---
> **At a glance:** TikTok for Business (tiktokglobal\_int) es una red de autorreporte (SRN) avanzada que brinda a los propietarios de aplicaciones la capacidad de medir la atribución móvil basada en clics y visualizaciones con AppsFlyer. Esto incluye instalaciones de aplicaciones provenientes de campañas de TikTok tanto móviles como no móviles.

> 📘 **Note**
>
> El 30 de enero de 2023, se agregó la nueva integración de TikTok for Business (SRN avanzado) `tiktokglobal_int`. La integración [Legacy] TikTok for Business `bytedanceglobal_int` se eliminó gradualmente y quedó oficialmente obsoleta el 20 de marzo de 2024. TikTok gestiona la transición y te avisará cuando puedas eliminar la integración anterior. Para evitar la pérdida de datos, asegúrate de mantener ambas integraciones activas durante la fase de transición. Aprende más en el `boletín`.
>
> AppsFlyer admite medir la actividad de la aplicación para [campañas que no son de aplicaciones](#web-a-app-mide-la-actividad-de-la-app-para-campañas-que-no-son-de-app).

<Image alt="TTFB_logo__4C_stacked_black_1.png" src="https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png" width="218px" />

## Visión general

Una integración avanzada de SRN significa que todo el tráfico que incluye un ID de publicidad se atribuye y se informa como tráfico regular de SRN. Cuando no hay disponible un ID de publicidad, AppsFlyer mide la atribución en función de los clics y las impresiones de TikTok, de acuerdo con las restricciones de privacidad.

## Configura TikTok for Business

**Requisito previo:** Antes de configurar la integración, <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contacta con el partner</Anchor> y abre una cuenta con ellos.

**Para activar o editar la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Busca **TikTok for Business** y selecciónalo.
3. Haz clic en **Configurar integración**. Se te dirigirá a la página de configuración de la integración.
4. En la pestaña **Integración**, selecciona la aplicación para la integración y activa **Activar partner**.  
   **Nota:** El conmutador debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración incluye las siguientes pestañas: Integración, enlace de atribución, costo, ingresos por publicidad y permisos. La pestaña **Enlace de atribución** no está disponible para TikTok for Business; las demás pestañas son opcionales.

> 📘 **Note**
>
> Algunas configuraciones difieren para dispositivos iOS y Android.
>
> Al configurar una campaña, el nombre de la campaña no debe empezar ni terminar con un espacio, ya que puede causar discrepancias en dashboards y reportes. Saber más sobre <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">cómo configurar una campaña en TikTok</Anchor>.
>
> Los anuncios que provienen de <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">Search Ads Toggle de TikTok</Anchor> están incluidos en toda la atribución de TikTok. AppsFlyer no recibe datos sobre términos de búsqueda o palabras clave específicos.

<Accordion title="Pestaña Integración">

La pestaña **Integración** incluye varias secciones, como se describe a continuación.

#### Activar partner

Para configurar la integración, primero debes activar el conmutador **Activar partner**. Para más información sobre <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activar y desactivar partners</Anchor>, consulta las integraciones.

#### Compartición avanzada de datos

Solo para aplicaciones iOS: El control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del estado de activación de la opción **Privacidad avanzada (para iOS 14.5 y versiones posteriores)**.

| Uso compartido de datos avanzado: Activado | Uso compartido de datos avanzado: Desactivado |
| --- | --- |
| AppsFlyer comparte todas las instalaciones y reinstalaciones con TikTok. | AppsFlyer comparte instalaciones y reinstalaciones solo de los usuarios que hayan dado su consentimiento. |
| Los postbacks se envían según tu configuración:<ul><li>**Todas las fuentes de medios, incluidas las orgánicas**</li><li>**Solo este partner**</li></ul> | Los postbacks se envían solo para eventos atribuidos al partner<ul><li>**Usuarios que han dado su consentimiento:** Los postbacks siguen la plantilla habitual.</li><li>Al activar la integración (`tiktokglobal_int`), el selector de **Privacidad avanzada** está activado de forma predeterminada.</li></ul> |

> 📘 **Note**
>
> Al activar la integración (`tiktokglobal_int`), el conmutador **Uso compartido avanzado de datos** está desactivado de forma predeterminada.

#### Uso compartido de datos de coincidencia avanzada

Cuando se activa el **uso compartido de datos de coincidencia avanzada**, los campos de coincidencia avanzada, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash y el apellido con hash, se comparten con TikTok si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido avanzado de datos de coincidencia avanzada</Anchor>.

#### Configuración general

**ID de aplicación de TikTok**

Se trata de un código único generado en el Administrador de TikTok Ads, que TikTok utiliza para confirmar la propiedad del anunciante de sus aplicaciones. Aunque no es obligatorio, se recomienda introducir los ID de aplicación de cada una de tus aplicaciones. Esto te ayuda a controlar mejor tus datos en TikTok for Business y desbloquear productos adicionales.

**Para agregar tus ID de aplicación:**

1. [Opcional] Introduce tu <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">ID de aplicación de TikTok</Anchor>, disponible en tu panel de control de TikTok Ads.
2. [Opcional] Para agregar más ID de aplicación:
   1. Después de introducir el primer ID de aplicación, presiona Intro.
   2. Introduce tu siguiente ID de aplicación de TikTok.

> 📘 **Note**
>
> Configurar un ID de aplicación de TikTok no afecta a tus datos en AppsFlyer.
>
> Al migrar a la nueva integración (`tiktokglobal_int`), todos los valores de la integración heredada (`bytedanceglobal_int`) se rellenan automáticamente en este campo.
>
> <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">Saber más sobre los requisitos del ID de aplicación de TikTok para iOS 14</Anchor>.

#### Postbacks predeterminados

Configura cómo enviar postbacks para las **instalaciones** de la aplicación. En el caso de las **instalaciones rechazadas** y los **re-engagements**, los postbacks se envían únicamente a TikTok for Business.

* **Solo este partner** [Predeterminado]: envía postbacks solo cuando el evento se atribuye a este partner; es decir, cuando el usuario que lo realizó proviene de este partner.
* **Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos; es decir, cuando el usuario que lo realizó proviene de cualquier fuente de medios. TikTok for Business recomienda cambiar la selección a **Todas las fuentes de medios, incluidas las orgánicas** para mejorar la optimización.

> 📘 **Note**
>
> Solo para aplicaciones de iOS: el control sobre los datos compartidos con el partner mediante postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del **conmutador Uso compartido avanzado de datos (iOS 14.5 y versiones posteriores)**.
>
> Al migrar desde la integración heredada (`bytedanceglobal_int`) y activar la nueva integración (`tiktokglobal_int`), el estado seleccionado de forma predeterminada para los postbacks de instalaciones es "**Solo este partner**", independientemente de cuál fuera su estado antes de la migración.

#### Atribución de instalación.

Configura las diferentes ventanas de atribución para atribuir nuevas instalaciones (primeros lanzamientos) de usuarios que vieron, hicieron clic o interactuaron con tu anuncio. Ten en cuenta que solo las instalaciones dentro de la ventana de lookback pueden atribuirse a TikTok for Business.

1. Establece la **ventana de lookback de instalaciones por clic** en 1-23 horas o 1-30 días. **Nota:** Nota: TikTok for Business recomienda alinearse con ellos estableciendo la ventana de lookback por click-through en 7 días.

> 📘 **Note**
>
> La configuración de la ventana retrospectiva de clic también determina las ventanas retrospectivas de clics y por impresiones de engagement.

1. [Opcional] Activa la **atribución de instalaciones por visualización** y configura las ventanas de lookback:
   * **Ventana de lookback de instalaciones por visualización** entre 1 y 24 horas. **Nota:** TikTok for Business recomienda alinearte con ellos configurando la ventana de lookback de instalaciones por visualización en 1 día.

> 📘 **Note**
>
> TikTok for Business está implementando medidas avanzadas de privacidad de datos para proteger a los usuarios de sus servicios. A partir del 23 de octubre de 2021, TikTok for Business ofrece a los anunciantes datos limitados de atribución por view-through a nivel de dispositivo. Para fuentes a nivel de usuario, como reportes de raw data, mensajes de Push API, reportes de Pull API, la página Datos exportados y Data Locker, se completan los siguientes campos:
>
> * Fuente de medios (bytedanceglobal\_int)
> * Canal
> * Tipo de toque atribuido (impresión)
> * Hora de toque atribuida (informada solo como fecha, "dd/mm/aaaa")
> * La campaña se reporta como "restringida". Estos datos no están disponibles en GCD. Los reportes de datos agregados siguen mostrando las conversiones por impresiones.
>
> Al migrar desde la integración heredada (`bytedanceglobal_int`) y activar la nueva integración (`tiktokglobal_int`), la configuración de la ventana de lookback (click-through y view-through) se establece en los **valores predeterminados**, independientemente de su estado antes de la migración. Puedes actualizar dicha configuración.

#### Atribución de reinstalaciones

La atribución de reinstalación te permite medir a los usuarios que reinstalan tu aplicación durante su ventana de reatribución y atribuirlos a clics e impresiones elegibles de TikTok.

Cuando está activada, las reinstalaciones se cuentan como nuevas conversiones en las campañas de TikTok y se informan de manera consistente con tus configuraciones de atribución de instalación existentes. Para más información sobre las reinstalaciones, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls">Medir reinstalaciones</Anchor>.

* Para habilitar la atribución de reinstalación, en la pestaña **Integración**, activa la **Atribución de reinstalación**.

> 📘 **Note**
>
> No se necesitan ventanas de lookback separadas para las reinstalaciones. La atribución de reinstalación utiliza el mismo estado de click-through y view-through, así como las ventanas de lookback que tus configuraciones de atribución de instalación.
>
> Cuando está habilitado, se envían postbacks de reinstalación elegibles a TikTok.

#### Atribución de re-engagement

Configura las diferentes ventanas de atribución para atribuir las nuevas interacciones de tus usuarios existentes que vieron, hicieron clic o interactuaron con tu anuncio. Ten en cuenta que solo las nuevas interacciones dentro de la ventana de lookback se pueden atribuir a TikTok for Business.

1. Establece la **ventana de lookback por click-through de re-engagement** en 1-23 horas o 1-30 días. **Nota:** TikTok for Business recomienda alinearse con ellos configurando la ventana de lookback por click-through de re-engagement en 7 días.

> 📘 **Note**
>
> La configuración de la ventana retrospectiva de clic de re-engagement también determina las ventanas retrospectivas de clics y por impresiones de engagement.

1. [Opcional] Activa la **atribución por view-through de re-engagement** y configura las ventanas de lookback:
   * **Ventana de lookback por view-through de re-engagement** entre 1 y 24 horas. **Nota:** TikTok for Business recomienda alinearse con ellos configurando la ventana de lookback por view-through de re-engagement en 1 día.
2. Establece la **Ventana de re-engagements** en 1 a 23 horas, 1 a 90 días o **de por vida**.

> ❗️ **Warning**
>
> Al migrar desde la integración heredada (`bytedanceglobal_int`) y activar la nueva integración (`tiktokglobal_int`), el selector de **Re-engagement** se desactiva de forma predeterminada, independientemente de su estado antes de la migración. Si tu integración heredada tiene <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">campañas de retargeting</Anchor>, asegúrate de activarlas en la nueva integración para garantizar la continuidad.

Aprende más sobre las <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#reengagement-rules-and-windows">reglas y ventanas</Anchor> de re-engagement.

#### Ignorar usuarios activos para retargeting

Establece el período de tiempo de la ventana para <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window#periodo-de-inactividad">ignorar los re-engagements y reatribuciones</Anchor> de los usuarios que lanzaron tu aplicación. Esto significa que su actividad durante el periodo de la ventana no se registra en AppsFlyer.

> 📘 **Note**
>
> **Se registran** las conversiones de re-engagements y reatribución de los usuarios que estuvieron **inactivos** durante el período establecido.

1. Activa **Ignorar usuarios activos para el retargeting**.
2. Configura la ventana de inactividad.

#### Postbacks de eventos in-app

Configura la asignación de eventos in-app con eventos de TikTok for Business, enviados a través de postbacks:

1. Activa **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibe AppsFlyer, procede del SDK integrado en tu aplicación o de eventos de servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer** y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizada</Anchor>.</li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Cuadro desplegable:** Selecciona el evento predefinido de TikTok más adecuado.</li><li>**Tal cual**: Si eliges **Personalizado** en el menú desplegable, AppsFlyer envía los eventos tal como están, sin asignarlos a ninguno de los eventos predefinidos de TikTok. Ten en cuenta que TikTok no utiliza eventos personalizados para la Optimización, sino solo con fines de reportar, por lo que TikTok no recomienda esta configuración. Para más información sobre los eventos estándar y personalizados de TikTok, consulta la <Anchor target="_blank" href="https://ads.tiktok.com/help/article/standard-events-parameters">documentación de TikTok</Anchor>.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner** (predeterminado): Envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks para eventos atribuidos a cualquier partner, así como eventos orgánicos. TikTok for Business recomienda seleccionar **todas las fuentes de medios, incluidas las orgánicas,** para una mejor optimización.</li></ul> |
| **Incluye** | <ul><li>**Sin valores ni ingresos** (predeterminado): Envía solo el evento en sí sin ningún valor de evento.</li><li>**Valores & sin ingresos**: Envía todos los parámetros, excepto el valor de ingresos.</li><li>**Valores & ingresos**: Envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento). TikTok for Business recomienda seleccionar **Valores & ingresos** para una mejor optimización.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
4. Haz clic en **Guardar integración**.
5. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, bajo el nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

> 📘 **Note**
>
> Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner mediante postbacks e <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">informes</Anchor> depende del **uso compartido avanzado de datos (iOS 14.5+ y posteriores)** [selector](#compartición-avanzada-de-datos).
>
> Al migrar a la nueva integración (`tiktokglobal_int`), todos los eventos de postback configurados en la integración heredada (`bytedanceglobal_int`) se rellenan automáticamente con la misma configuración.
>
> * Si un evento está asignado al evento **Pay** de [Legacy] TikTok for Business, se renombra automáticamente a Purchase al migrar a la nueva integración.

</Accordion>

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de Atribución no son relevantes para las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRNs</Anchor> ni para las SRNs avanzadas.

Las SRNs realizan la Atribución en su propia plataforma. La Atribución de las SRNs avanzadas se realiza combinando sus datos de engagement con los datos de AppsFlyer, usando la configuración de Atribución que definiste en la [pestaña Integración](#integration-tab).

</Accordion>

<Accordion title="Pestaña de costos (para costos, clics e impresiones)">

Esta integración proporciona datos agregados sobre costos, clics e impresiones de tus campañas, conjuntos de anuncios, anuncios y geolocalizaciones/países. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.

**Nota:** Los datos sobre clics e impresiones se incluyen en la integración. Sin embargo, los **datos de Costo requieren una** <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">**suscripción a ROI360**</Anchor> **subscription**.

**Para habilitar la conexión de la API para costos, clics e impresiones con TikTok for Business:**

1. Ve a la pestaña **Costo** y activa **Obtener datos de costos**.
2. Haz clic en **Iniciar sesión en TikTok Ads**.
3. En la ventana de TikTok que se abre, inicia sesión en tu cuenta de TikTok y confirma los permisos necesarios.
4. Después de que aparezca un mensaje exitoso en la ventana de TikTok, ciérrala. Los datos de tu cuenta de TikTok ahora aparecen en **Cuentas conectadas**.
5. En **Advertiser account IDs** > **Advertiser ID**: introduce el ID de la cuenta de anunciante de TikTok y haz clic en **Add**.

> 📘 **Note**
>
> Para obtener tu **ID de anunciante** desde tu cuenta comercial de TikTok: Ve a **Usuarios** > **Miembros** y, debajo de la cuenta de Anunciante, podrás ver el ID.
>
> Asegúrate de que el **ID de anunciante** que agregues esté asociado con la **cuenta de TikTok** que conectaste en el paso 2, ya que esta es la cuenta desde la que se recopilarán los datos.
>
> Conecta al menos un **ID de anunciante**. Puedes agregar hasta 30.

1. Haz clic en **Guardar costo**.

#### Para suscriptores de ROI360

* Los Anunciantes y las Agencias que tienen habilitada la API de Costo tanto en la integración heredada `bytedanceglobal_int` como en la integración actual `tiktokglobal_int` pueden ver datos de costo duplicados. Para evitarlo, ve a la integración `bytedanceglobal_int` > pestaña **Costo** y desactiva el interruptor. Sin embargo, al habilitar la nueva integración de costos se recopilan automáticamente los datos de costos de los 5 días anteriores a la fecha de la transición. Esto significa que se espera que la nueva integración muestre datos de costos duplicados para esos 5 días. Por ejemplo, si la integración de costos anterior se deshabilitó el 15 de enero y la nueva integración de costos se habilitó el mismo día, aparecen datos de costos duplicados en la nueva integración de costos entre el 10 y el 14 de enero, aunque la nueva integración de costos solo se habilitó el 15 de enero.
* Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.
* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Consulta el estado de tu API de Costo</Anchor> y la última vez que AppsFlyer logró extraer datos de costo coincidentes, ya sea en el Dashboard de estado de la integración de costo (y de ingresos por anuncios) o en el Dashboard de cada ad network.
* Aprende más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">habilitar la API de costos</Anchor>.

</Accordion>

<Accordion title="Pestaña de ingresos por publicidad">

Para enviar tus datos de ingresos por publicidad a TikTok para la optimización de adquisición de usuarios (UA), puedes configurar <Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners">postbacks de ingresos por publicidad o señales de UA</Anchor>.

Para obtener datos de ingresos por publicidad de Pangle, utiliza la integración de partners de Pangle (ingresos por publicidad).

</Accordion>

<Accordion title="Pestaña de permisos">

En esta sección, puedes seleccionar permisos para otorgar a TikTok for Business acceso a tus datos y realizar diversas acciones.

Ten en cuenta que, incluso después de que la integración se <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactive</Anchor>, el interruptor **permisos de TikTok for Business** sigue concediendo permisos.

Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">concesión de permisos</Anchor>.

</Accordion>

## Enlaces profundos con TikTok for Business

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en">TikTok soporta Deep Linking y Deferred deep linking</Anchor> para varios objetivos de campaña a nivel de Anuncio al crear una campaña, un grupo de anuncios y un Anuncio. La creación de enlaces profundos para que el usuario navegue a contenido específico le permite ofrecer contenido personalizado en función de la interacción del usuario con su anuncio de TikTok.

### Accede a los datos de conversión de TikTok a través de la API GCD de AppsFlyer para Deep Linking

AppsFlyer ofrece una serie de soluciones para enlaces profundos diferidos:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**UDL (Unified deep linking)**</Anchor>: los clics de TikTok incluyen un campo <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> (cuando se configura un deep link para el anuncio) y son compatibles con la solución UDL.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD (Get Conversions Data) API**</Anchor>: esta es la opción recomendada para acceder a los datos de conversión de usuarios de TikTok en tiempo real, directamente a nivel del SDK. Los datos devueltos en la API de GCD incluyen el parámetro <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor>, que contiene el destino real del deep link (destino del usuario dentro de la aplicación).
* **Con los parámetros de datos de conversión,** puedes crear lógica personalizada para dirigir al usuario a tu contenido usando otros parámetros, como el nombre de la campaña, el nombre del conjunto de anuncios o cualquier otro campo que se devuelva en los datos de atribución de las instalaciones de TikTok.

## Web a App: mide la actividad de la App para campañas que no son de App

La integración de AppsFlyer con TikTok permite una medición exhaustiva de la actividad de la App, como instalaciones, re-engagements y eventos in-app, para campañas que no son de App atribuidas a TikTok for Business.

Por ejemplo, las instalaciones de aplicaciones se pueden medir incluso cuando el destino del anuncio es una landing page web, lo que permite medir la trayectoria del usuario web-to-app (W2A).

Al seguir los pasos a continuación en TikTok Ads Manager, puedes medir de manera efectiva la actividad de la aplicación a partir de campañas fuera de la aplicación de TikTok y obtener insights valiosos sobre el comportamiento de los usuarios. También puedes ver la <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en">documentación de TikTok</Anchor>.

1. Ve a la página de la campaña publicitaria de TikTok y selecciona **Editar anuncio**.
2. En **Seguimiento** > **Eventos in-app**, selecciona tu aplicación.
3. Haz clic en **Guardar**.
4. Repite estos pasos para todos los anuncios relevantes de tu campaña.

## Configura TikTok for Business para agencias

Las agencias que trabajan en nombre de los anunciantes pueden activar la integración de TikTok for Business y comenzar a obtener atribución para sus campañas. No obstante, esta integración tiene algunas limitaciones cuando se trata de agencias.

### Limitaciones para agencias

Se aplican las siguientes limitaciones cuando una agencia trabaja con esta integración:

| Rasgo | Descripción |
| --- | --- |
| El acceso depende del anunciante | Una agencia puede acceder a la integración de TikTok for Business solo después de que el anunciante con el que trabaja la haya activado de su lado. |
| Parámetros de atribución de solo lectura | A partir del 1 de enero de 2024, los parámetros de atribución que se muestran en la página de integración de la agencia se heredan de la integración del anunciante en modo de **solo lectura**. Esto significa que la agencia puede ver cómo el anunciante configuró las ventanas de lookback de atribución, pero no puede configurarlas por su cuenta. |
| Sin control sobre Advanced Data Sharing | Una agencia no puede activar la configuración Advanced Data Sharing, incluso si se le concede permiso. Esta configuración está limitada únicamente al anunciante. |
| Configuración del postback de eventos in-app | Con el <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60">permiso</Anchor> del anunciante, una agencia puede configurar postbacks de eventos in-app. |
| Se recomienda la alineación del mapeo | Al asignar postbacks de eventos in-app, recomendamos asegurarse de que la configuración de asignación sea idéntica tanto para la agencia como para el marketer. |

**Para configurar TikTok for Business para agencias:**

1. En AppsFlyer, en **Configuración**, ve al **Partner Marketplace**.
2. Busca **TikTok for Business** y selecciónalo.
3. Introduce el **ID de aplicación de TikTok**.
4. Ingresa el **ID de cuenta de TikTok** de tu agencia. Esto identifica el tráfico de la agencia y lo distingue del anunciante.
5. Haz clic en **Save Integration**.

   <Image alt="tiktok.png" src="https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png" width="664px" />

> 🚧 **Important**
>
> Los ID de cuenta de TikTok for Business no deben compartirse entre el anunciante y la agencia. Si se comparten, todas las instalaciones del anunciante se atribuyen automáticamente en el dashboard de la agencia.

## Enviar eventos in-app complejos a TikTok

Para enviar eventos in-app complejos, es decir, eventos con varios elementos, a TikTok, te recomendamos usar el nuevo objeto de evento `af_order_info`. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/item-level-order-data-for-ad-networks-af-order-info">Datos de pedidos a nivel de artículo para ad networks (af\_order\_info)</Anchor>.

TikTok admite hasta 7 campos dentro de este objeto, lo que permite a los anunciantes compartir varios puntos de datos sobre cada elemento incluido en el evento.

## Reporte de campañas Smart Plus

Smart Plus es un nuevo tipo de campaña de TikTok que permite a los anunciantes probar múltiples creatividades dentro de la misma unidad de anuncio, ayudando a optimizar el performance a través de pruebas creativas automatizadas.

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en">Saber más sobre las campañas Smart Plus</Anchor>.

### Cómo están estructuradas las campañas Smart Plus

A diferencia de las campañas estándar de TikTok, que incluyen tres niveles (campaña, grupo de anuncios y anuncio), las campañas Smart Plus añaden una cuarta capa: creatividad.

1. Campaña
2. Conjunto de anuncios
3. El valor puede tener hasta 4 dígitos.
4. Creatividad

### Cómo se reportan los datos de Smart Plus en AppsFlyer

AppsFlyer mapea los datos de la campaña Smart Plus de TikTok de la siguiente manera:

| Nivel de TikTok | Equivalente de AppsFlyer | Notas |
| --- | --- | --- |
| Campaña | Campaña | Mapeado directamente |
| Grupo de anuncios | Conjunto de anuncios | Mapeado directamente |
| El valor puede tener hasta 4 dígitos. | No correponde | No mapeado en AppsFlyer |
| Creatividad | El valor puede tener hasta 4 dígitos. | Mapeado al nivel de anuncio de AppsFlyer |

> 📘 **Note**
>
> La estructura de mapeo de AppsFlyer para campañas de Smart Plus difiere de TikTok Ads Manager. En TikTok Ads Manager, los reportes se muestran solo hasta el nivel de anuncio sin un desglose creativo dedicado. Sin embargo, AppsFlyer mapea los datos creativos de TikTok directamente al nivel de anuncio. Como resultado, es posible que veas discrepancias al comparar los datos de performance entre AppsFlyer y TikTok.

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H8VVCC8G3ZXZJMHSMJ67GMG4=visi%C3%B3n-general set-up-tiktok-for-business-integration=configura-tiktok-for-business 01H8VVCC8GPY4SEFGK30Q1BJZ6=configura-tiktok-for-business activate-partner=activar-partner 01H8VVCC8G0KR4AA2HD9S8QBKD=activar-partner advanced-data-sharing=compartici%C3%B3n-avanzada-de-datos 01H8VVCC8G0Z6ZHC10KVY9CGGQ=compartici%C3%B3n-avanzada-de-datos h_01_advanced-matching-data-sharing=uso-compartido-de-datos-de-coincidencia-avanzada advanced-matching-data-sharing=uso-compartido-de-datos-de-coincidencia-avanzada general-settings=configuraci%C3%B3n-general 01H8VVCC8GSDPSNN0AJPVZPR8P=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados 01H8VVCC8GW677RN6R6CV35KGG=postbacks-predeterminados install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n 01H8VVCC8GK8VFPBEPAMVHCAWM=atribuci%C3%B3n-de-instalaci%C3%B3n reinstall-attribution=atribuci%C3%B3n-de-reinstalaciones h_01K6D37PG96P2MG99BETK25GYA=atribuci%C3%B3n-de-reinstalaciones reengagement-attribution=atribuci%C3%B3n-de-re-engagement 01H8VVCC8HHG5290PYF0BT29QA=atribuci%C3%B3n-de-re-engagement ignore-active-users-for-retargeting=ignorar-usuarios-activos-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usuarios-activos-para-retargeting inapp-event-postbacks=postbacks-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postbacks-de-eventos-in-app for-roi360-subscribers=para-suscriptores-de-roi360 01H8VVCC8HWDC9A03FRY5BC87Y=para-suscriptores-de-roi360 deep-linking-with-tiktok-for-business=enlaces-profundos-con-tiktok-for-business h_01JJM8MPX2X37WVR86S7786S06=enlaces-profundos-con-tiktok-for-business access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking=accede-a-los-datos-de-conversi%C3%B3n-de-tiktok-a-trav%C3%A9s-de-la-api-gcd-de-appsflyer-para-deep-linking h_01HVQR1TC5WVRDS24R9ZKD2HW2=accede-a-los-datos-de-conversi%C3%B3n-de-tiktok-a-trav%C3%A9s-de-la-api-gcd-de-appsflyer-para-deep-linking measure-app-activity-for-nonapp-campaigns=web-a-app-mide-la-actividad-de-la-app-para-campa%C3%B1as-que-no-son-de-app h_01J7MYAMBQ8M0JN005FSXQDZNS=web-a-app-mide-la-actividad-de-la-app-para-campa%C3%B1as-que-no-son-de-app set-up-tiktok-for-business-for-agencies=configura-tiktok-for-business-para-agencias 01H8VVCC8HVNNQ9PJS4ZQCVDNS=configura-tiktok-for-business-para-agencias agency-limitations=limitaciones-para-agencias h_01HHVGS94CB9XC0T63VFDZ18JS=limitaciones-para-agencias send-complex-in-app-events-to-tiktok=enviar-eventos-in-app-complejos-a-tiktok h_01M22GT5M1VJ691TX74VN18SYX=enviar-eventos-in-app-complejos-a-tiktok smart-plus-campaigns-reporting=reporte-de-campa%C3%B1as-smart-plus h_01K9AGYS6XCDS3193ZAK7Z208F=reporte-de-campa%C3%B1as-smart-plus how-smart-plus-campaigns-are-structured=c%C3%B3mo-est%C3%A1n-estructuradas-las-campa%C3%B1as-smart-plus h_01K9AGYS6XSXJ9DD6XYDHVYMYK=c%C3%B3mo-est%C3%A1n-estructuradas-las-campa%C3%B1as-smart-plus how-smart-plus-data-is-reported-in-appsflyer=c%C3%B3mo-se-reportan-los-datos-de-smart-plus-en-appsflyer h_01K9AGYS6XYT763ST1H1T4SXT8=c%C3%B3mo-se-reportan-los-datos-de-smart-plus-en-appsflyer" />
