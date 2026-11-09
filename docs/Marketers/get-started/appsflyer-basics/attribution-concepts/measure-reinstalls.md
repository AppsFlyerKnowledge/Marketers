---
title: Reinstalaciones
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-08-12T11:57:08Z'
  id: 10164066030737
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/10164066030737
---
> **De un vistazo**: Una reinstalación ocurre cuando un usuario instala una aplicación, la desinstala y luego la reinstala. Las reinstalaciones dan como resultado uno de los siguientes tipos de atribución: reinstalación no orgánica, reinstalación orgánica o reatribución (retargeting). Las reinstalaciones ayudan a evitar múltiples cargos para los usuarios que desinstalan e instalan de nuevo.

<div id="what-is-a-reinstall" />

## Qué es una reinstalación

Una reinstalación se produce cuando un usuario elimina una aplicación y luego la reinstala durante la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución.</Anchor>

La reinstalación puede provenir de una campaña de retargeting (reatribución), una fuente orgánica o una fuente no orgánica.

Las reinstalaciones que provienen de una fuente orgánica, o una fuente no orgánica, y se encuentran en la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución</Anchor>, se denominan reinstalaciones.

Las reinstalaciones que provienen de campañas de retargeting se denominan reatribuciones.

Se diferencian en cómo se atribuyen los eventos de reinstalación e in-app.

Si se produce una instalación fuera de la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución</Anchor>, la reinstalación se denomina <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#new-install">nueva instalación</Anchor>. Una nueva instalación se atribuye a la fuente de medios (u orgánica si no se registra ningún engagement) y comienza una nueva ventana de reatribución.

La siguiente tabla muestra lo que AppsFlyer llamaría diferentes reinstalaciones

| Fuente de la reinstalación | ¿Es válida la ventana de reatribución? | ¿El usuario interactuó con una campaña de retargeting antes de reinstalar? | ¿El usuario interactuó con una campaña de UA antes de reinstalar? | Cómo se llama |
| --- | --- | --- | --- | --- |
| De una campaña de retargeting | Sí | Sí | No | Reatribución |
| De una fuente orgánica o no orgánica | Sí | No | Sí o No | Reinstalación |
| De una fuente orgánica o no orgánica | No | No | Sí o No | Nueva instalación |

<div id="why-are-reinstalls-important" />

## Por qué son importantes las reinstalaciones

Además de ser una buena indicación de que los usuarios están volviendo a tu aplicación y que tus campañas están funcionando, es importante realizar una atribución adecuada de las reinstalaciones para ayudar a evitar múltiples cargos para los usuarios que desinstalan e instalan nuevamente dentro de la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución.</Anchor>

Asimismo, la atribución de eventos in-app desde reinstalaciones a la fuente de medios original (primera instalación) proporciona a los anunciantes una mejor imagen de cómo se involucran los usuarios. También muestra cuán efectivas son las campañas de UA y los anuncios de retargeting. Para obtener más información, consulta los [eventos in-app](/docs/measure-reinstalls#eventos-in-app) a continuación.

<div id="reinstall-flow-and-outcome" />

## Flujo de reinstalación y resultado

<div id="reinstall" />

<Accordion title="Reinstalación">

Después de la primera instalación de la aplicación, el usuario la desinstala y luego vuelve a instalarla durante la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución</Anchor>. Una reinstalación puede provenir de una campaña orgánica o de UA (ver [ejemplos](/docs/measure-reinstalls#examples)).

Sucede lo siguiente:

* La instalación NO se atribuye: no aparece en el panel de control, ni en los datos.
* Los partners solo pueden recibir postbacks de reinstalación si admiten esta capacidad y AppsFlyer les ha concedido permisos explícitos. Los anunciantes pueden elegir enviar postbacks de reinstalación solo a este partner o a todas las fuentes de medios, incluidas las orgánicas, en la página **Integración activa** del partner, en la sección de postbacks de *instalación*.
* Consulta los [eventos in-app](/docs/measure-reinstalls#eventos-in-app) para obtener información sobre cómo se atribuyen los eventos in-app

</Accordion>

<div id="reattribution" />

<Accordion title="Reatribución">

Después de la primera instalación de la aplicación, el usuario la desinstala, luego se involucra con una campaña de retargeting y la reinstala durante la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#ventana-de-reatribución">ventana de reatribución</Anchor>.

Sucede lo siguiente:

* La instalación se atribuye a la fuente de medios de retargeting en la vista de retargeting y unificada del panel de control general.
  * La vista de adquisición de usuarios no contiene reatribuciones.
* Todos los siguientes eventos in-app se atribuyen a la fuente de medios de retargeting (ver [eventos in-app](/docs/measure-reinstalls#eventos-in-app) para más información).
* Se envía un postback de instalación a la fuente de medios de retargeting.

Para obtener más información sobre la atribución de retargeting, haz clic <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">aquí</Anchor>.

</Accordion>

<div id="post-reinstall-in-app-events" />

## Eventos in-app

Los eventos in-app realizados por un usuario después de una reinstalación se atribuyen como orgánicos, no orgánicos o no atribuidos, según el estado de **atribución de los eventos posteriores a la reinstalación** (consulta a continuación). Un ejemplo de un evento in-app es un usuario que reinstala una aplicación y luego realiza una compra in-app.

<Image align="center" alt="" src="https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg" />

<div id="postreinstall-events-attribution-state" />

<Accordion title="Estado de atribución de los eventos posteriores a la reinstalación">

<table><thead><tr><th>Atribución de reinstalaciones</th><th>Después de una reinstalación</th><th>Después de una reatribución</th></tr></thead><tbody><tr><td><strong>Atribuido como in-apps orgánicos</strong></td><td>orgánico sin atribuir</td><td>Reorientación</td></tr><tr><td> <strong>Atribuido a la primera instalación</strong><span>(1)</span> </td><td>fuente de medios de la primera instalación</td><td>Retargeting <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) Ver limitaciones a continuación</span></p><p><span>(2) En el campo de fuente primaria. La fuente de medios de la primera instalación se enumerará en el campo de fuente secundaria (<span>tú solo lo verás en el raw data).</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="unattributed-organic-inapps" />

<Accordion title="In-apps orgánicos sin atribuir">

Reinstalación

* Todos los eventos in-app se contabilizan como orgánicos o se descartan por completo <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">según el método de reporte</Anchor>.
* Los eventos in-app se reportarán con conversion\_type y campaign\_type como "unknown".
* La fecha utilizada para agregar datos depende del evento:
  * Para la mayoría de los eventos in-app originados en un SDK, se utiliza la fecha de descarga de la aplicación para agregar datos; no la fecha de la reinstalación.
  * Para eventos de ingresos por publicidad (af\_ad\_revenue) enviados por el conector del SDK, se utiliza la fecha de la reinstalación para agregar datos.

Reatribución

* Todos los eventos in-app se atribuyen a la fuente de medios de retargeting.

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Atribuido a la primera instalación">

<div id="note" />

> 📘 **Nota**
>
> El modo de primera instalación se aplica automáticamente a las aplicaciones añadidas a AppsFlyer el 31 de julio de 2024 o después. Para las aplicaciones añadidas antes de esta fecha, te recomendamos que contactes con AppsFlyer para migrar tus aplicaciones existentes al modo de primera instalación.

Proporciona a los anunciantes una mejor imagen de cómo están involucrados los usuarios. Muestra cuán efectivas son las campañas de UA y los anuncios de retargeting al atribuir eventos in-app a la fuente original en lugar de orgánicos.

* Todos los eventos in-app generados a partir de las reinstalaciones se atribuyen a la instalación original. (1) La hora de instalación del evento in-app atribuido será la hora de la primera instalación, no la de la reinstalación. Por ejemplo, si hubo una instalación el 1 de marzo y luego una reinstalación el 5 de marzo, y si la opción «Atribución de eventos posteriores a la reinstalación» está habilitada, cualquier compra realizada después de la reinstalación se atribuirá a la hora de instalación del 1 de marzo.
* Todos los eventos in-app se atribuyen al anuncio de retargeting en la fuente primaria y a la instalación original en la fuente secundaria. (2)

(1) Ver [limitaciones a continuación.](/docs/measure-reinstalls#limitations)

(2) Esto solo lo verás en el raw data.

<div id="note-1" />

> 📘 **Prerrequisitos**
>
> Los datos de KPI orgánicos en el panel de control pueden mostrar un valor más bajo con la **atribución de eventos posteriores a la reinstalación** establecida en **Atribuido a la primera instalación**, ya que algunos de esos números ahora pueden atribuirse a una fuente de medios no orgánica.

<div id="examples-for-first-install-mode-attribution" />

#### Ejemplos de atribución en el modo de primera instalación.

**Ejemplo 1**

Un usuario instala la aplicación (día 0), realiza una compra por 10 USD y luego desinstala la aplicación.

Al día siguiente (día 1), el usuario reinstala la aplicación y realiza una compra de 5 USD.

<Image align="center" alt="Reinstall_1.jpg" src="https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg" />

Dado que el usuario ya realizó una compra antes de reinstalar, no habrá un recuento adicional de usuarios únicos.

| Fuente de medios | usuario(s) | Af\_purchase:<br /><br />Usuarios únicos<br /><br />Día 0 | Af\_purchase:<br /><br />Usuarios únicos<br /><br />Día 1 (acumulativo) | Ingresos<br /><br />Día 0 | Ingresos<br /><br />Día 1 (acumulativo) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | $15 |

Veremos un incremento en los ingresos bajo el mismo `device_identifier`.

| Appsflyer\_id | Identificador de dispositivo | Fuente de medios | Nombre del evento | Fecha del evento |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | instalar | día 0 |
| 111 | XXX | media\_source\_A | af\_compra | día 0 |
| 222 | XXX | orgánica | Reinstalación | día 1 |
| 222 | XXX | media\_source\_A | af\_compra | día 1 |

**Ejemplo 2**

Un usuario instala la aplicación (día 0), realiza una compra y luego desinstala la aplicación.

Al día siguiente (día 1), el usuario reinstala la aplicación desde una campaña de UA y realiza una compra.

| Fuente de medios | Nombre del evento | Fecha del evento | Reinstalación | Atribución de eventos in-app |
| --- | --- | --- | --- | --- |
| media\_source\_A | instalar | día 0 | media\_source\_A |  |
| media\_source\_A | af\_compra | día 0 |  | media\_source\_A |
| media\_source\_B | Reinstalación | día 1 | media\_source\_B |  |
| media\_source\_B | af\_compra | día 1 |  | media\_source\_A |

</Accordion>

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<Accordion title="Confirma que los eventos in-app se atribuyen a la instalación original">

Puedes verificar en tu reporte de raw data que tus eventos in-app posteriores a la reinstalación están en modo de primera instalación siguiendo estos pasos:

* Comprueba el campo `install_time` en el evento in-app. Si refleja la hora de la instalación original (no la de la reinstalación), el evento se atribuye a la primera instalación.
* Verifica el `device_id` (GAID o IDFA). Sigue siendo el mismo en todas las instalaciones y reinstalaciones, por lo que puedes usarlo para hacer referencia al evento de la instalación original.
* Ten en cuenta que el `appsflyer_id` del evento in-app difiere del valor de la instalación original. AppsFlyer genera un nuevo ID de AppsFlyer después de cada reinstalación.

</Accordion>

<div id="limitations" />

<Accordion title="Limitaciones">

* Solo los usuarios que hayan dado su consentimiento para compartir su identificador de dispositivo (como el IDFA o GAID) con la aplicación, tanto para la instalación como para la reinstalación, tendrán sus eventos in-app atribuidos a la instalación original.
  * Los identificadores de dispositivo en la primera instalación y la reinstalación deben coincidir.
* La reinstalación debe ocurrir dentro de la <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#reengagement-rules-and-windows">ventana de reatribución</Anchor> de la última instalación registrada.
* Cada instalación y reinstalación seguirá teniendo su propio `appsflyer_id` único.
* Los paneles de control no diferencian entre un evento in-app después de la instalación o reinstalación.
  * Es posible ver esto a través del raw data.
* El SDK de Windows de AppsFlyer no mide las reinstalaciones.

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## Cómo aparecen los datos en los paneles de control de AppsFlyer

<table><thead><tr><th colspan="2"> </th><th>Reinstalación no orgánica</th><th>Reinstalación orgánica </th><th>Reatribución</th></tr></thead><tbody><tr><td colspan="2">La reinstalación en sí</td><td>No visto</td><td>No visto</td><td>Fuente de medios de retargeting\*</td></tr><tr><td rowspan="2">Atribuciones de eventos in-app en el futuro</td><td>Eventos posteriores a la reinstalación establecidos en <strong>Atribuidos como in-apps orgánicos</strong> </td><td>Orgánicos sin atribuir</td><td>Orgánicos sin atribuir</td><td>Fuente de medios de retargeting</td></tr><tr><td>Eventos posteriores a la reinstalación establecidos en <strong>Atribuidos a la primera instalación</strong> </td><td>Primera fuente de medios</td><td>Primera fuente de medios</td><td>Campaña de retargeting</td></tr><tr><td colspan="5">\*Solo en el panel de control general.</td></tr></tbody></table>

<div id="reinstalls-raw-data-reports" />

## Reportes de raw data de reinstalaciones

<div id="prerequisites" />

> 🚧 **Prerrequisitos**
>
> Requiere habilitarlo. Comunícate con tu CSM para discutirlo.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">Reporte de ejemplo de reinstalaciones como un archivo CSV</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### Cómo se atribuyen los eventos de instalación e in-app

<table><thead><tr><th colspan="2"> </th><th>Reinstalación no orgánica</th><th>Reinstalación orgánica </th><th>Reatribución</th><th>Instalación no orgánica</th><th>Instalación orgánica</th></tr></thead><tbody><tr><td colspan="2">Atribuido a </td><td>Campaña de UA</td><td>Orgánico</td><td>Campaña de retargeting</td><td>Campaña de UA</td><td>Orgánico</td></tr><tr><td rowspan="2">Atribución de eventos en el futuro</td><td>Eventos posteriores a la reinstalación establecidos en <strong>Atribuidos como in-apps orgánicos</strong> </td><td>Orgánico</td><td>Orgánico</td><td>Campaña de retargeting</td><td>Campaña de UA</td><td>Orgánico</td></tr><tr><td>Eventos posteriores a la reinstalación establecidos en <strong>Atribuidos a la primera instalación</strong> </td><td>Primera instalación</td><td>Primera instalación</td><td>Campaña de retargeting</td><td>Campaña de UA</td><td>Orgánico</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### Disponibilidad de reportes de reinstalación

* Los reportes de raw data de reinstalaciones están disponibles utilizando las herramientas de entrega detalladas en la tabla que sigue.
* Los reportes tienen la misma estructura y se rellenan de manera similar a los reportes de instalaciones, en que:
  * Los campos de **Fuente de medios** se rellenan utilizando la fuente de medios que trajo la reinstalación u orgánica.
  * **Tiempo de instalación**: se interpreta como tiempo de reinstalación, es decir, la hora de la primera apertura de la aplicación después de la reinstalación.
  * **Nombre del evento:** *Reinstall*

| Método de entrega de reportes | Reinstalación no orgánica | Reinstalación orgánica |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Exportar datos</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">API pull</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Casillero de datos</Anchor> | ✓ | ✓ |
| API push | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=qu%C3%A9-es-una-reinstalaci%C3%B3n 01H7SZVZPGHBQ7VM8TMWRD3CE4=qu%C3%A9-es-una-reinstalaci%C3%B3n why-are-reinstalls-important=por-qu%C3%A9-son-importantes-las-reinstalaciones 01H7SZVZPG6T2AW9B3EMT29AQQ=por-qu%C3%A9-son-importantes-las-reinstalaciones reinstall-flow-and-outcome=flujo-de-reinstalaci%C3%B3n-y-resultado 01H7SZVZPGVQCNCQ7TCZMYM33T=flujo-de-reinstalaci%C3%B3n-y-resultado 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=eventos-in-app 01H7SZVZPGBYRWZGAZRT36EFGH=eventos-in-app h_01K47GSZ90CKBGPCZFGQBD1PMK=postreinstall-events-attribution-state 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install h_01KHJV7J6H5KKMZVZN8XPW4CEZ=nota 01H7SZVZPH5YGSMPGW7NPKXJAF=prerrequisitos with-attributed-to-the-first-install-enabled=ejemplos-de-atribuci%C3%B3n-en-el-modo-de-primera-instalaci%C3%B3n 01H7SZVZPHH3DS9J4VRD70VTX6=ejemplos-de-atribuci%C3%B3n-en-el-modo-de-primera-instalaci%C3%B3n h_01K47KBXE2NXXQFMS4RPJ0RA4T=confirm-inapps-are-attributed-to-the-original-install 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=c%C3%B3mo-aparecen-los-datos-en-los-paneles-de-control-de-appsflyer 01H7SZVZPHHQS4NHEDATD7ZP9V=c%C3%B3mo-aparecen-los-datos-en-los-paneles-de-control-de-appsflyer reinstalls-raw-data-reports=reportes-de-raw-data-de-reinstalaciones 01H7SZVZPHPWN8REBQ5CWVFNJT=reportes-de-raw-data-de-reinstalaciones 01H7SZVZPHCVDPDDYD6HHNFMMK=prerrequisitos-1 how-the-install-and-inapp-events-are-attributed=c%C3%B3mo-se-atribuyen-los-eventos-de-instalaci%C3%B3n-e-in-app 01H7SZVZPHQT8XS3ZBA4W682GB=c%C3%B3mo-se-atribuyen-los-eventos-de-instalaci%C3%B3n-e-in-app availability-of-reinstall-reports=disponibilidad-de-reportes-de-reinstalaci%C3%B3n 01H7SZVZPH6NY7FMG9YHDBB95R=disponibilidad-de-reportes-de-reinstalaci%C3%B3n" />
