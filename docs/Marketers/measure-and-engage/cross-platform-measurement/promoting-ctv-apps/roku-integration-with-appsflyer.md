---
title: Integración de Roku con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2026-08-12T12:10:17Z'
  id: 4404257169169
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/4404257169169
---
> **En resumen** Rokuads\_int es una integración de SRN que permite a los anunciantes integrar su aplicación móvil o de Roku CTV con Roku Ads para recibir atribuciones y datos de eventos para sus campañas en Roku Ads.

## Sobre Roku Ads Attribution

Roku es una ad network única que tiene inventario publicitario tanto en Connected TV (CTV) como en aplicaciones móviles. La integración de SRN entre AppsFlyer y Roku Ads permite a los anunciantes medir múltiples trayectorias de usuario, incluyendo:

* CTV-to-CTV: Anuncios de CTV que impulsan instalaciones y eventos de aplicaciones de CTV.
* Mobile-to-mobile: Anuncios de aplicaciones móviles que impulsan instalaciones y eventos de aplicaciones móviles.
* CTV-to-mobile y mobile-to-CTV: Impresiones de anuncios en una plataforma que conducen a instalaciones y eventos en una plataforma diferente.

### Flujo de atribución de Roku

[<Image alt="54525 inline.jpg" src="https://files.readme.io/5634ed65702e1d4c90250a7f7b4448c225d5f769936b2a120ddbac1a76752c09-39534517801617.jpg" width="895px" />](https://support.appsflyer.com/hc/article_attachments/39654452910737)

## Configurando la integración de Roku Ads para anunciantes

**Requisito previo:** Antes de configurar la integración, asegúrate de [ponerte en contacto con el partner](#) y abrir una cuenta con ellos. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
    Para editar: Ve a **Colaborar** > **Integraciones activas.Para editar:** En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Selecciona la aplicación correspondiente.
3. Busca al partner (`rokuads_int`) y selecciónalo.
4. En la pestaña **Integración**, selecciona **Activar partner**.  
    **Nota:** El conmutador debe permanecer ON (activado) mientras trabajes con el partner. [Saber más sobre la activación de partners](#).
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Para ver una descripción detallada del encabezado de la ventana de configuración del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

**Nota:** Hay algunas diferencias entre la configuración de aplicaciones de iOS, Android y Roku.

<div id="integration-tab" />

<Accordion title="Pestaña integración">

#### Configuración general

* **ID del grupo de eventos:** Introduce el ID del grupo de eventos para conectar tu aplicación a AppsFlyer.
  * **ID de Grupo de Eventos:** Ingresa el ID de Grupo de Eventos, obtenido del Administrador de Roku Ads, para conectar tu aplicación a AppsFlyer. Para más información, consulta la <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/11885912-setting-up-an-integration-with-appsflyer-a-mobile-measurement-partner-mmp">documentación de Roku Ads</Anchor>.
  * **Clientes de servicios gestionados**: Ponte en contacto con tu representante de Roku para obtener tu ID de grupo de eventos.
* **Compartir datos avanzados:**  Cuando esté ON, Roku recibirá postbacks y datos de eventos con direcciones IP para todos los dispositivos, incluidos aquellos que no han hecho disponible su ID de Publicidad (IDFA). Mantener la Compartición Avanzada en OFF asegura que este partner solo recibirá postbacks y datos de eventos para dispositivos que han hecho disponible el IDFA.
* **Uso compartido de datos de Advanced Matching:** Cuando está activado, Roku recibe campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre y el apellido con hash, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.
* **Uso limitado de datos:** Activa para indicar que Roku Ads debe limitar su uso de información personal para un evento dado, en estados específicos de Estados Unidos. Para más información, consulta la <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/8766138-limited-data-use">documentación de Roku Ads</Anchor>.

#### Atribución de instalación

Configura las diferentes ventanas de atribución para atribuir nuevas instalaciones (primeros lanzamientos) de usuarios que vieron, hicieron clic o interactuaron con tu anuncio. **Nota:** No se admite la atribución de reinstalaciones (cualquier instalación que no sea la inicial en el dispositivo).

* Establece la **ventana de lookback de click-through** en 1-23 horas o 1-14 días. **Nota:** Roku Ads recomienda establecerlo en 14 días.
* [Opcional] Activa la **Atribución de instalaciones view-through** y establece la **Ventana de lookback view-through de instalaciones** en 1-23 horas o 1-14 días. **Nota:** Roku Ads recomienda 14 días.

#### Atribución de re-engagement

* Establece la **ventana de lookback click-through de re-engagements** en 1-23 horas o 1-14 días. **Nota:** Roku Ads recomienda 14 días.
* [Opcional] Activa la **Atribución view-through de re-engagements** y establece la **ventana de lookback view-through de re-engagements** en 1-23 horas o 1-14 días. **Nota:** Roku Ads recomienda 14 días.
* Establece la **Ventana de re-engagements** en 1-23 horas, 1-90 días o **de por vida**.

[Saber más sobre las reglas y ventanas de re-engagement](#).

#### Ignorar usuarios activos para el retargeting

Establece un marco de tiempo para ignorar los re-engagements de usuarios que lanzaron tu aplicación dentro del marco de tiempo. Esto significa que su actividad durante el marco de tiempo no se atribuye. Para más información, consulta el <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window#periodo-de-inactividad">período de inactividad</Anchor>.

1. Activa **Ignorar usuarios activos para retargeting**.
2. Configura la **ventana de inactividad**.

#### Atribución multiplataforma

La atribución multiplataforma está habilitada por defecto para esta integración.

* Establece la **ventana de lookback multiplataforma** en 1-23 horas o 1-3 días.
* La ventana de prioridad igual multiplataforma está configurada en 3 horas. Cuando está habilitado, las impresiones multiplataforma reportadas por Roku se elevan a la misma prioridad que los clics de otras redes.

#### Postbacks de eventos in-app

Mapea los eventos in-app de AppsFlyer a los eventos de Roku Ads, enviados a través de postbacks:

1. Activa **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor. |
| **Asignado a un evento de partner** | Selecciona de la lista de eventos predefinidos de Roku. Consulta el <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#nombres-de-eventos-predefinidos">mapeo sugerido</Anchor> de eventos de Appsflyer a eventos de Roku Ads.  <br />**Nota:** Roku no admite el envío de eventos personalizados. |
| **Para usuarios de** | <ul><li>**Solo este partner** (predeterminado): Envía postbacks solo cuando este evento se atribuye a este partner.<br />O</li><li>**Todas las fuentes de medios, incluidas las orgánicas:** Envía postbacks para eventos atribuidos a cualquier partner, así como eventos orgánicos.</li></ul> |
| **Incluye** | <ul><li>**Sin valores ni ingresos** (predeterminado): Envía solo el evento en sí sin ningún valor de evento.</li><li>Con valores y sin ingresos: Envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Con valores y con ingresos:** Envía todos los parámetros del evento, incluyendo el valor de los ingresos (si existe en el evento).</li></ul> |

* [Opcional] Haz clic en el icono **Agregar condición** para establecer condiciones para un evento.
* Haz clic en **Guardar integración**.
* [Opcional] Para integrar más aplicaciones:
  1. Desde la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
  2. Selecciona otra aplicación de la lista.
  3. Repite la configuración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de atribución no son relevantes para las SRNs o SRNs avanzadas.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos (para costos, clics e impresiones)">

La integración de costos no está disponible para Roku Ads en esta fase.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no están disponibles para Roku Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes elegir qué permisos otorgar a Roku Ads, independientemente de si actúan como una ad network, una agencia o ambas. Incluso si la atribución está deshabilitada para Roku Ads, la pestaña de Permisos permanece activa y aún puedes otorgarles acceso.

Después de habilitar los permisos para Roku Ads, puedes agregar miembros del equipo y asignarles acceso según los permisos seleccionados. **Nota:** Los permisos solo se pueden otorgar a empleados de Roku Ads que tengan una cuenta de miembro del equipo de ad network en AppsFlyer.

**Para otorgar permisos a los miembros del equipo de ad network, sigue estos pasos:**

1. Haz clic en **Añadir miembro del equipo**.
2. Ingresa el correo electrónico del miembro del equipo de la ad network.
3. Haz clic en **Añadir**.

> 🚧 **¡Importante!**
>
> * Cuando le otorgas permiso a Roku Ads para configurar la integración y cambiar los postbacks de eventos in-app, les permites acceder potencialmente a todos los eventos de atribución, incluido el tráfico orgánico y no orgánico de todas las fuentes de medios.
> * Los cambios que realiza Roku Ads anulan la configuración actual, incluso si tu (el anunciante) los estableces.

#### Tipos de permisos que los anunciantes pueden otorgar a Roku Ads

| Permiso | Capacidad concedida |
| --- | --- |
| Configurar integración | Permite que el partner configure la pestaña de integración, excepto los postbacks de eventos in-app. |
| Configura los postbacks de eventos in-app | Permitir que el partner configure el postback de eventos in-app.<br /><br />**¡Importante!** Combinado con "Configurar integración", esto otorga acceso a todos los eventos de atribución, incluidos el tráfico orgánico y no orgánico de todas las fuentes de medios. |
| Acceso al reporte de retención | Permitir acceso solo a los propios datos de retención del partner. |
| Accede a datos agregados de usuarios leales | Permitir que el partner acceda a tu métrica de usuarios leales. |
| Accede a datos de conversión agregados | Permitir acceso a métricas de instalaciones, re-engagement, re-instalaciones y re-atribuciones. Un ejemplo es <Anchor target="_blank" href="/partners/es/docs/aggregated-campaign-performance-report-for-ad-networks">Reportes de rendimiento de campañas agregadas</Anchor>. |
| Acceso a datos agregados de eventos in-app | Otorgar al partner acceso a todos los datos de eventos in-app, incluidos los datos de Protect360, no solo los eventos configurados en el mapeo de postback.  <br />Esto también incluye acceso a datos de monetización de anuncios, que pueden contener eventos de otras fuentes de medios. |
| Ver reglas de validación | Permitir que el partner vea los detalles de tu regla de validación. |
| Acceder a los datos de ingresos agregados | Permitir acceso a datos de ingresos publicitarios para optimización de UA. |
| Usar importación de costos | Permitir que el partner cargue datos de costos utilizando la Importación de Costos. |
| Accede a la consola Protect360 y raw data | <ul><li>El acceso a datos en raw data está disponible solo si tu suscripción incluye Protect360, Reglas de Validación o Raw Data.</li><li>Otorga acceso al dashboard de Protect360, incluido ProtectLITE.</li><li>**Nota:** ProtectLITE incluye acceso al dashboard pero no proporciona acceso a raw data.</li></ul> |

</Accordion>

## Configurando la integración de Roku Ads para agencias

Las agencias que trabajan en nombre de los anunciantes pueden activar la integración de Roku Ads y comenzar a obtener atribución por sus campañas. Sin embargo, esta integración tiene algunas limitaciones para las agencias.

### Limitaciones para agencias

* Una agencia puede acceder a la integración de Roku Ads solo después de que el anunciante con el que trabaja la haya activado en su lado.
* Los parámetros de atribución que se muestran en la página de integración de la agencia se heredan de la integración del anunciante en modo de solo visualización.

**Para configurar Roku Ads para agencias:**

1. En AppsFlyer, desde la barra lateral, abre <Image alt="colaborar.png" src="https://files.readme.io/70400e32ef967b981aabd47faf97880368585fdf52ad29c0d4c2d4c31751e6a3-37844129188753.png" width="2%" /> **Colaborar** > **Partner Marketplace**.
2. Encuentra **Roku Ads (rokuads\_int)** y selecciónalo.
3. Ingresa el **ID de Cuenta de Roku Ads** de tu agencia. Esto identifica el tráfico de la agencia y lo distingue del anunciante.
4. Haz clic en **Guardar integración**.

> ❗️ **Advertencia**
>
> Los IDs de cuenta de Roku Ads NO DEBEN ser compartidos entre el anunciante y la agencia. Si se comparten, TODAS las instalaciones del anunciante se atribuyen automáticamente en el dashboard de la agencia.

<div data-zendesk-anchors="overview=sobre-roku-ads-attribution roku-attribution-flow=flujo-de-atribuci%C3%B3n-de-roku 01H7Z13QPBTKZ9BVCMGASYEM0R=flujo-de-atribuci%C3%B3n-de-roku setting-up-roku-ads=configurando-la-integraci%C3%B3n-de-roku-ads-para-anunciantes general-settings=configuraci%C3%B3n-general h_01K0P7PHA89T432XNW0C4BZ4VH=configuraci%C3%B3n-general install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n h_01K0P7PHA8X7E7MC7JNVG86JAV=atribuci%C3%B3n-de-instalaci%C3%B3n reengagement-attribution=atribuci%C3%B3n-de-re-engagement h_01K0P7PHA8GR0SYPNKSP4D90AF=atribuci%C3%B3n-de-re-engagement ignore-active-users-for-retargeting=ignorar-usuarios-activos-para-el-retargeting h_01K0P7PHA85619R1SM4SR49TQ3=ignorar-usuarios-activos-para-el-retargeting crossplatform-attribution=atribuci%C3%B3n-multiplataforma h_01K0P7PHA80KKG06719ZWE8JB0=atribuci%C3%B3n-multiplataforma inapp-events-postbacks=postbacks-de-eventos-in-app h_01K0P7PHA89Y8W70NTF40S6PC4=postbacks-de-eventos-in-app cost-tab-for-cost-clicks-and-impressions=cost-tab h_01K0P7PHA840N225ABCSGTTCAN=importante types-of-permissions-advertisers-can-grant-to-roku-ads=tipos-de-permisos-que-los-anunciantes-pueden-otorgar-a-roku-ads h_01K0P7PHA8D7WQR02129YADZZP=tipos-de-permisos-que-los-anunciantes-pueden-otorgar-a-roku-ads setting-up-agencies=configurando-la-integraci%C3%B3n-de-roku-ads-para-agencias setting-up-roku-ads-integration-for-agencies=configurando-la-integraci%C3%B3n-de-roku-ads-para-agencias agency-limitations=limitaciones-para-agencias h_01K0P7PHA8MSV6Q13P9ATAX8SJ=limitaciones-para-agencias h_01K0P7PHA8KXP5H9WXJ1J2VFR2=advertencia" />
