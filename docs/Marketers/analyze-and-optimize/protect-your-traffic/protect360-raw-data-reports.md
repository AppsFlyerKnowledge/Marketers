---
title: Informes de datos sin procesar de Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-08-12T11:55:33Z'
  id: 360015179337
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Los informes de datos sin procesar describen las instalaciones y los eventos in-app bloqueados por el motor Protect360, así como por las Reglas de Validación añadidas manualmente.

<div id="about-protect360-raw-data-reports" />

## Sobre los informes de datos sin procesar de Protect360

Informes de datos sin procesar:

* Muestran datos sobre:
  * Clics, instalaciones y eventos in-app identificados como fraudulentos por el motor Protect360.
  * Instalaciones y eventos in-app identificados mediante Reglas de Validación.
* Incluyen el motivo del bloqueo para cada clic, instalación o evento in-app.
* Son utilizados por los anunciantes para conciliar cuentas de redes publicitarias, para la optimización y para ajustar los cuadros de atribución por fraudes posteriores a la atribución.
* Puede que <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">algunos campos estén restringidos o no disponibles</Anchor> si <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">se utiliza AppsFlyer Aggregated Advanced Privacy (AAP)</Anchor>.
* Los tipos de informes y su disponibilidad para descarga, API y Data Locker (depósito S3) se describen en las secciones siguientes.
* La retención de los informes históricos de datos sin procesar es de hasta 90 días, dependiendo de la herramienta de informes y la fuente de los datos sin procesar.

<div id="note" />

> 📘 **Nota**
>
> Debido a las restricciones de datos sin procesar relacionadas con la privacidad, los informes sin procesar pueden mostrar campos con valores vacíos. Un ejemplo de esto son los campos de colaboradores.

<div id="report-types" />

<Accordion title="Tipos de informes">

<div id="protect360-raw-data-report-types" />

#### Tipos de informes de datos sin procesar de Protect360

| Informe | Descripción |
| --- | --- |
| <span id="installs"></span>Instalaciones | Los informes incluyen:<ul><li>**Instalaciones falsas**: Instalaciones detectadas como fraudulentas por el motor Protect360. Estas no aparecen en ningún panel de AppsFlyer ni en datos sin procesar, excepto en el panel y los datos sin procesar de Protect360.</li><li>**Instalaciones secuestradas**: Instalaciones de usuarios reales donde se roba la atribución, pero Protect360 [corrige la atribución](/docs/protect360-raw-data-reports#corrección-de-atribución-de-instalaciones-secuestradas).</li><li>**Reglas de Validación**: Que bloquearon la instalación o bloquearon la atribución (Protect360 [corrige la atribución](/docs/protect360-raw-data-reports#corrección-de-atribución-de-instalaciones-secuestradas)).</li></ul> |
| <span id="postattribution-installs"></span>Instalaciones posteriores a la atribución | Los informes incluyen instalaciones atribuidas a una fuente de medios, pero posteriormente identificadas como fraudulentas. [Protect360](/docs/protect360-raw-data-reports#corrección-de-atribución-de-instalaciones-secuestradas) [corrige la atribución](/docs/protect360-raw-data-reports#corrección-de-atribución-de-instalaciones-secuestradas). |
| <span id="blocked-inapp-events"></span>Eventos in-app bloqueados | Los informes incluyen eventos in-app provenientes de:<ul><li>**Instalaciones falsas**: Los eventos IAE están bloqueados.</li><li>**Eventos in-app**: Identificados como fraudulentos independientemente de las instalaciones originales.</li><li>**Reglas de Validación**:<ul><li>IAE procedentes de una regla que bloqueó la instalación o la atribución.</li><li>IAE procedentes de una regla que bloqueó el evento in-app.</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>Eventos in-app posteriores a la atribución | Los informes incluyen eventos in-app:<ul><li>Identificados tras la atribución.</li><li>De instalaciones atribuidas a una fuente de medios, pero que luego resultaron ser fraudulentas.</li></ul> |
| <span id="clicks"></span>Clics | Los informes incluyen clics bloqueados con sus motivos. |
| <span id="blocked-install-postbacks"></span>Postbacks de instalación bloqueados | Los informes incluyen copias de los postbacks de rechazo enviados a las fuentes de medios que trajeron instalaciones bloqueadas. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Informes posteriores a la atribución">

* Los informes de fraude de datos sin procesar posteriores a la atribución tienen la misma estructura que los informes de fraude bloqueados.
* El informe posterior a la atribución del mes actual (según la fecha de instalación) se sigue actualizando hasta el séptimo día del mes siguiente (fecha de detección).
* Los informes de datos en bruto de atribución posterior están limitados a los anunciantes. Las agencias necesitan tener los <Anchor target="_blank" href="/partners/es/docs/protect360-for-integrated-partners">permisos</Anchor> habilitados para acceder.
* Los informes contienen eventos de fraude posteriores a la atribución identificados por Protect360 e incluyen todas las fuentes de medios en un solo informe. **Nota**: Si no se identifican eventos de fraude de atribución post-activos para el rango de fechas seleccionado, el informe aparece vacío,
* Los informes de fraude de datos en bruto post-activos están disponibles de la siguiente manera:
  * Interfaz de usuario del panel: limitada a una fuente de medios durante un mes calendario.
  * API de extracción: contiene todas las fuentes de medios. (Limitación: Disponible solo para propietarios de aplicaciones.)

<div id="using-post-attribution-reports" />

#### **Uso de informes post-activos**

* Seleccione cualquier combinación de rangos de fechas de instalación/IAE y de detección según sea necesario.
* Tenga en cuenta que Protect360 realiza la detección post-atribución durante el mes calendario de la instalación y hasta el séptimo día del mes siguiente. Esto significa, por ejemplo, que para las instalaciones de noviembre, Protect360 verifica el fraude hasta el 7 de diciembre.
* La mejor práctica para utilizar esta API de extracción es la siguiente:
  * Supongamos que genera el informe diariamente.
  * Establezca el rango de fechas de instalación a 60 días antes del día actual.
  * Configure el rango de detección desde/hasta el día anterior al actual.  
    Esto significa que obtendrás la lista de fraudes detectados después de la atribución, ayer. Si no generaste el informe durante algunos días, ajusta el rango de fechas de detección y crea el informe.

<div id="example" />

> 📄 **Ejemplo**
>
> **Ejemplo A**: Durante diciembre, se atribuyen 15 instalaciones a example\_media. El 3 de enero, Protect360 identifica a example\_media como un fraude. Como consecuencia, las 15 instalaciones atribuidas a example\_media se enumeran como fraudulentas en el informe de fraude post-atribución para que el propietario de la aplicación tome medidas adicionales.
>
> **Ejemplo B**: Durante diciembre, se atribuyen 15 instalaciones a example\_media. El 9 de enero, Protect360 identifica a example\_media como un fraude. En este caso, Protect360 no toma medidas porque el fraude fue identificado después del cierre del mes, el 7 de enero.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Disponibilidad de datos sin procesar por tipo de herramienta">

<div id="protect360-raw-data-availability-by-tool-type" />

#### Disponibilidad de datos sin procesar de Protect360 por tipo de herramienta

<table><thead><tr><th>Informe</th><th>Actualización de datos</th><th>API de extracción</th><th>Página de exportación de datos</th><th>Casillero de datos</th></tr></thead><tbody><tr><td>Instalaciones</td><td>En tiempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Eventos in-app bloqueados</td><td>En tiempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Clics</td><td>En tiempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Postbacks de instalación bloqueados</td><td>En tiempo real</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Instalaciones posteriores a la atribución</td><td>Diariamente a las 10:00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Eventos in-app posteriores a la atribución</td><td>Diariamente a las 10:00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="5"><p>\* Limitaciones para los informes a través de Data Locker:</p><ul><li>No se admite la transparencia de la agencia. Esto significa que el tráfico gestionado por la agencia no contiene el nombre de la fuente de medios que envía la instalación.</li><li>El informe tiene un conjunto único de campos en comparación con otros informes de Data Locker. Esta lista no se puede modificar.</li><li>Los datos de retargeting no están disponibles en el informe de Instalaciones; solo en el informe de Instalaciones post-atribución. </li></ul></td></tr></tbody></table>

</Accordion>

<div id="getting-raw-data-reports" />

## Obteniendo informes de datos sin procesar

Los informes de datos sin procesar están disponibles para descargar, API de extracción y Data Locker (cubeta S3). También puedes <Anchor target="_blank" href="/partners/es/docs/protect360-for-integrated-partners">dar acceso a socios a los informes</Anchor>.

<div id="download" />

<Accordion title="Descargar">

**Para descargar:**

1. En el panel de Protect360, ve a **Informes de datos sin procesar** > **Bloqueados** o **Post-atribución.**
   * Para los informes posteriores a la atribución, seleccione la fuente del medio y el mes.
2. Seleccione el informe **Protect360 & Validation Rules** para descargar.

**O**

1. En el panel de AppsFlyer, vaya a **Exportar datos**.
2. Seleccione el informe **Protect360 & Validation Rules** para descargar.

**Nota**: Los informes descargados de la página Exportar datos contienen todas las fuentes de medios.

</Accordion>

<div id="pull-api" />

<Accordion title="API de extracción">

**Para descargar informes de datos sin procesar disponibles mediante Pull API:**

**Antes de comenzar:**

Necesita un token Pull API. Obtenga el token de un <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">usuario administrador</Anchor>.

1. Vaya a **Informe > Acceso API.** Se abre la página<Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">API de extracción</Anchor>.
2. En la sección de informes de fraude de Protect360, seleccione la llamada Pull API necesaria.
3. Complete los parámetros según sea necesario. La siguiente tabla enumera los parámetros.
4. Extraiga el informe.

<div id="pull-api-raw-data-report-parameters" />

#### Parámetros del informe de datos sin procesar de la API de extracción

| Parámetro | Descripción | Formato | Obligatorio |
| --- | --- | --- | --- |
| id de la aplicación | ID de la aplicación tal como aparece en AppsFlyer | Cadena | Sí |
| token\_api | Recupere la clave del Dashboard. Vaya a **Informe** > **Acceso a la API.** Solo un usuario administrador puede recuperar el token de API. | Cadena | Sí |
| de | Inicio del rango de fechas:<ul><li>Para las instalaciones, esta es la fecha de instalación.</li><li>Para los eventos dentro de la aplicación, esta es la fecha del evento.</li></ul> | AAAA-MM-DD | Sí |
| a | Fin del rango de fechas:<ul><li>Para las instalaciones, esta es la fecha de instalación.</li><li>Para los eventos dentro de la aplicación, esta es la fecha del evento.</li></ul> | AAAA-MM-DD | Sí |
| nombre\_del\_evento | [Opcional para fraudes en eventos dentro de la aplicación posteriores a la atribución]<br /><br />Filtre eventos por evento en la aplicación. Limite el informe a eventos específicos.  Se pueden incluir uno o más eventos.<br /><br />Ejemplo de uso: `&event_name=af_purchase,af_login` | Cadena | No |
| campos\_adicionales=valor\_de\_motivo\_rechazado | [Opcional para fraudes en eventos dentro de la aplicación posteriores a la atribución]<br /><br />**<Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** muestra el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#protect360">contribuidor válido (fuente de medios) para instalaciones/eventos dentro de la aplicación secuestrados. Rellenado con [**contribuidor[1-3]**](/docs/raw-data-field-dictionary#attribution::2a6fd501) o **orgánico**.</Anchor> | Cadena | No |
| detectar desde | [Opcional para instalaciones posteriores a la atribución]<br /><br />Inicio del rango de fechas de detección de fraude. (El valor predeterminado es de). (Se utiliza en fraudes de instalación posteriores a la atribución). (Se utiliza en fraudes de instalación posteriores a la atribución). | AAAA-MM-DD | No |
| detectar-a | [Opcional para instalaciones posteriores a la atribución]<br /><br />Fin del rango de fechas de detección de fraude. (El valor predeterminado es.) | AAAA-MM-DD | No |

</Accordion>

<div id="data-locker" />

<Accordion title="Casillero de datos">

Data Locker escribe datos sin procesar  en un depósito AWS S3.

<Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports#protect360">Consulte la lista de informes de Protect360 disponibles</Anchor>. 

<Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#aws-cli">Consulte las instrucciones de configuración de Data Locker</Anchor>.

</Accordion>

<div id="protect360-report-structure" />

## Estructura del informe de Protect360

Los informes de Protect360 mantienen la misma estructura general que los campos de los informes de adquisición de usuarios.

Además de los <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">campos habituales de informe de datos sin procesar</Anchor>, los informes de Protect360 también incorporan campos para motivos de redireccionamiento y bloqueo, de la siguiente manera:

<div id="blocked-reasons" />

### Motivos de bloqueo

<div id="click-level-blocked-reasons" />

<Accordion title="Motivos por los que se bloquea el nivel de clic">

A nivel de clic, se bloquean los clics y el proceso de atribución los ignora.

| Motivo del bloqueo | Descripción |
| --- | --- |
| lista negra de IP | Basado en una lista creada dinámicamente (<Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide#ip-denylists">detalles</Anchor>) |
| limitación de clics | Se detectan tasas extremadamente altas de fraude de clics en esa red publicitaria. <Anchor target="_blank" href="/partners/es/docs/protect360-for-integrated-partners#umbral-de-impresiones">Más información</Anchor> |
| firma del clic | La firma en el clic no está validada. <Anchor target="_blank" href="/partners/es/docs/click-signing-for-ad-networks">Más información</Anchor> |
| validación de entrada | Nombre de la fuente de medios no válido |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Motivos por los que se bloquea el nivel de instalación">

A nivel de instalación, identificamos suficiente información durante el momento de la instalación para determinar:

* Una instalación falsa, lo que significa que el usuario que instala la aplicación no es una persona real. En este caso, la atribución está completamente bloqueada.
* Secuestro de atribución, donde el usuario es real pero el compromiso es falsificado. En este caso, se bloquea la actividad fraudulenta y la atribución se reasigna a la primera red publicitaria válida y contribuyente.

Las siguientes tablas enumeran los posibles motivos de bloqueo a nivel de instalación:

<div id="install-level-fake-install-block-sub-reasons" />

#### Nivel de instalación: Motivos para el bloqueo de instalaciones falsas

| Motivo del bloqueo | Submotivo de bloqueo | Descripción |
| --- | --- | --- |
| Bots | parámetros de dispositivo falso | Comportamiento no humano detectado en los parámetros relacionados con el dispositivo durante el proceso de instalación de la aplicación |
| Bots | parámetros de instalación falsos | Se detectó comportamiento no humano en los parámetros relacionados con la instalación durante el proceso de instalación de la aplicación |
| Bots | bayesian\_network | Identificación de patrones fraudulentos mediante redes bayesianas |
| Bots | anomalías en la actividad del usuario | Identifica el comportamiento anómalo o sospechoso de los usuarios dentro de la aplicación mediante modelos de detección de anomalías de comportamiento. Estos modelos:<ul><li>Analizan la actividad del usuario a nivel individual</li><li>Sacan a la luz desviaciones respecto a los patrones esperados</li><li>Detectan agrupaciones de comportamiento que se desvían de los perfiles de usuarios legítimos</li><li>Esta detección ayuda a señalar la actividad de bots que imita a usuarios reales, pero realiza acciones in-app de forma atípica.</li></ul> |
| Bots | validación de la tienda de instalación | Valida que cada instalación procede de una fuente auténtica y esperada. Este mecanismo:<ul><li>Verifica la integridad del canal de adquisición</li><li>Detecta señales de instalación falsificadas o manipuladas</li><li>Rechaza instalaciones que no se ajustan a vías de distribución legítimas</li><li>Al garantizar la legitimidad a nivel de instalación, este método ayuda a bloquear bots que intentan simular instalaciones orgánicas o de pago.</li></ul> |
| Bots | Anomalías de interacción con la app | Marca eventos que no se basan en in-app en las interacciones con la app posteriores a la instalación. Ayuda a identificar comportamientos sospechosos en la transición de la instalación a las aperturas. |
| bots de validación | parámetros del dispositivo no válidos | Desajuste en las expectativas de campos específicos del dispositivo (definido por el cliente) |
| bots de validación | reglas de validación | Reglas en las que el resultado son instalaciones bloqueadas basadas en una regla de validación definida manualmente |
| Bots | capa\_ai | Los modelos de inteligencia artificial se emplean para analizar grandes volúmenes de datos, mejorando las capacidades de detección para identificar actividades fraudulentas en dispositivos e instalaciones. |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### anomalías en ctit, secuestro de instalación

| Motivo del bloqueo | Submotivo de bloqueo | Descripción |
| --- | --- | --- |
| anomalías en ctit | ctit corto | Instalación bloqueada debido a CTIT reducido: Definido por Protect360 |
| secuestro de instalación | referrer\_hijack | Intento de secuestro bloqueado basándose en parámetros de la API de GooglePlay y el SDK de AppsFlyer |
| secuestro de instalación | integración temporalmente bloqueada | Instalación bloqueada porque el socio (pid) tiene tasas de fraude extremadamente altas y anomalías significativas en todo su tráfico |
| secuestro durante la validación | ctit corto | Instalación bloqueada debido a CTIT reducido: Definido por el cliente |
| secuestro durante la validación | ID del sitio vacío | Instalación bloqueada debido a que el ID del sitio no está completado. La implementación de la regla se realiza por etapas |
| secuestro durante la validación | reglas de validación | Reglas donde el resultado es una atribución bloqueada basada en una regla de validación definida manualmente |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Motivos de bloqueo a nivel de clúster">

Cuando se detecta un patrón de fraude, la fuente se coloca en una lista de exclusión. Las instalaciones procedentes de esta fuente excluida están bloqueadas por:

* Una instalación falsa, lo que significa que el usuario que instala la aplicación no es una persona real. En este caso, la atribución está completamente bloqueada.
* Secuestro de atribución, donde el usuario es real pero el compromiso es falsificado. En este caso, se bloquea la participación fraudulenta y se reasigna la atribución a la primera red publicitaria contribuyente válida.

Las siguientes tablas enumeran posibles motivos de bloqueo a nivel de clúster:

<div id="cluster-level-fake-install-block-reasons" />

#### Nivel de clúster: Motivos para el bloqueo de instalaciones falsas

| Motivo del bloqueo | Submotivo de bloqueo | Descripción |
| --- | --- | --- |
| Bots | timestamp\_anomalies | Anomalías relacionadas con tiempos de clic en el flujo de atribución y otras marcas de tiempo recogidas del dispositivo |
| bots, lista negra de sitios | emuladores de dispositivos | Instalaciones generadas a gran escala por scripts automáticos funcionando en entornos virtuales |
| lista negra de sitios | granjas de dispositivos | Altas tasas de dispositivos desconocidos (nuevos) |
| anomalías en el comportamiento | anomalías en el comportamiento | Comportamiento sospechoso en la aplicación comparado con el patrón habitual de los usuarios |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### Nivel de clúster: Motivos por los que se bloquea el secuestro de atribución

| Motivo del bloqueo | Submotivo de bloqueo | Descripción |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | anomalías en ctit | Patrón CTIT anómalo según los estándares de la aplicación |
| inundación de clics | inundación de clics | Volumen de clics anormalmente alto en una distribución extensa de CTIT |
| secuestro de instalación | Comentario | Clics generados por malware a nivel de dispositivo |
| Secuestro de re-engagement | agrupaciones de clics | Detecta intentos fraudulentos de secuestrar la atribución de re-engagement. Estas manipulaciones tienen como objetivo robar el mérito a redes de retargeting legítimas o incluso a usuarios que no vieron ningún anuncio de retargeting.<br />Una vez detectado, la atribución se corrige y se reasigna a:<ul><li>La red de retargeting válida</li><li>El proveedor original de adquisición de usuarios (UA)</li><li>Orgánico, si el usuario instaló la app sin haber estado expuesto a ningún anuncio de retargeting válido</li></ul> |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="Motivos de bloqueo a nivel de aplicación">

Los eventos dentro de la aplicación pueden bloquearse por las siguientes razones:

* La instalación inicial se ha identificado como falsa.
* Debido a una regla de validación establecida.
* Porque nuestro algoritmo detecta fraude.

La siguiente tabla enumera las posibles razones de bloqueo a nivel de aplicación.

<div id="in-app-level-block-reasons" />

#### Razones de bloqueo a nivel de aplicación

| Motivo del bloqueo | Submotivo de bloqueo | Descripción |
| --- | --- | --- |
| Hereda de la instalación | Hereda de la instalación | Instalación inicial identificada como falsa según el motivo a nivel de [instalación](/docs/protect360-raw-data-reports#install-level-blocked-reasons) o [lista de denegados](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) |
| inapps\_bots | parámetros de dispositivo falso | El algoritmo de AppsFlyer detecta el fraude |
| Validación en la tienda de aplicaciones | - | <Anchor target="_blank" href="/marketers/es/docs/legacy-receipt-validation-for-in-app-purchases">Falla la validación del recibo</Anchor> para la compra dentro de la aplicación. |
| validación\_inapps | reglas de validación | Basado en una regla de validación definida manualmente |

</Accordion>

<div id="retargeting" />

### Redireccionamiento

Los datos sin procesar de Protect360 incluyen instalaciones y sesiones fraudulentas de campañas de retargeting (conocidas como re-atribuciones y reenganches, respectivamente). Los datos se muestran utilizando los campos de <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#event">nombre de evento</Anchor>  y <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::e9c68f6c">tipo de conversión de retargeting</Anchor> . Se marcan como:

* Instalación (aplica al nombre del evento, pero no al tipo de conversión de redireccionamiento)
* Re-atribución
* Reengagement
* Reinstalar

Los datos sin procesar de retargeting de Protect360 están disponibles para bloqueos en tiempo real y fraudes identificados después de la atribución de la siguiente manera:

<table><thead><tr><th>Informe </th><th>Exportar datos</th><th>API de extracción</th><th>Casillero de datos</th></tr></thead><tbody><tr><td>Instalaciones</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Instalaciones posteriores a la atribución</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* Datos de reenganche no disponibles</span><br/> </td></tr></tbody></table>

<div id="hijacked-installs-attribution-correction" />

### Corrección de atribución de instalaciones secuestradas

Para instalaciones secuestradas, AppsFlyer bloquea la atribución a la red fraudulenta, atribuyendo la última fuente legítima de contribución.

Para las instalaciones secuestradas usa el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> campo para identificar al contribuyente válido (fuente de medios), es decir, el contribuyente que debería haber recibido originalmente la atribución.

* El **rejected\_reason\_value** se completa con <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor> o **orgánico. Consulta los campos de** contribuidor[1-3] fuente de medios/compañero  **para ver detalles del contribuyente y conciliar.**
* Si los campos de contribuyente no se muestran en tu informe, se pueden añadir desde la página de **Exportar datos**.

**Nota**: Cuando las instalaciones secuestradas se bloquean en tiempo real, las atribuciones correctas se muestran en los paneles e informes de AppsFlyer (no solo en Protect360). Cuando se identifican instalaciones secuestradas después de la atribución, las atribuciones correctas se muestran únicamente en los datos sin procesar de Protect360.

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Nota |
| --- | --- |
| Informes de inapps | Los informes de inapps no incluyen el campo de contribuidor. El campo de contribuidor solo está disponible en el informe de instalaciones. |
| Valores vacíos | Debido a las restricciones de datos sin procesar relacionadas con la privacidad, los informes sin procesar pueden mostrar campos con valores vacíos. Un ejemplo de esto son los campos de colaboradores. |

</Accordion>

<div data-zendesk-anchors="about-protect360-raw-data-reports=sobre-los-informes-de-datos-sin-procesar-de-protect360 h_01HE7S55TCE60A34T6RCNTCQK8=sobre-los-informes-de-datos-sin-procesar-de-protect360 h_01J91EP40Q69KXXF2SR66AM2FQ=nota h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=tipos-de-informes-de-datos-sin-procesar-de-protect360 h_01HE7S55TCKQYTXPV6J54SHM0D=tipos-de-informes-de-datos-sin-procesar-de-protect360 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=uso-de-informes-post-activos h_01HE7S55TC7KCF75KFXHCE3K2K=uso-de-informes-post-activos h_01HE7S55TCR8BKZ0PQ5B14X3X4=ejemplo h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=disponibilidad-de-datos-sin-procesar-de-protect360-por-tipo-de-herramienta h_01HE7S55TCH4CES29C5J3QXQK4=disponibilidad-de-datos-sin-procesar-de-protect360-por-tipo-de-herramienta getting-raw-data-reports=obteniendo-informes-de-datos-sin-procesar h_01HE7S55TC3MRT6E9QV0J0X6FC=obteniendo-informes-de-datos-sin-procesar h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=par%C3%A1metros-del-informe-de-datos-sin-procesar-de-la-api-de-extracci%C3%B3n h_01HE7S55TCRRD95D0QPCXBRF8T=par%C3%A1metros-del-informe-de-datos-sin-procesar-de-la-api-de-extracci%C3%B3n h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=estructura-del-informe-de-protect360 h_01HE7S55TCS91ZC9V3K0VDSVXK=estructura-del-informe-de-protect360 blocked-reasons=motivos-de-bloqueo h_01HE7S55TC1ZEDD5ABD21FCPY2=motivos-de-bloqueo h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=nivel-de-instalaci%C3%B3n-motivos-para-el-bloqueo-de-instalaciones-falsas h_01HE7S55TDHTE5P47N1CCREGZX=nivel-de-instalaci%C3%B3n-motivos-para-el-bloqueo-de-instalaciones-falsas install-level-attribution-hijacking-block-reasons=anomal%C3%ADas-en-ctit-secuestro-de-instalaci%C3%B3n h_01HE7S55TDFA6WGAHE80ECV8CA=anomal%C3%ADas-en-ctit-secuestro-de-instalaci%C3%B3n h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=nivel-de-cl%C3%BAster-motivos-para-el-bloqueo-de-instalaciones-falsas h_01HE7S55TDBES0BY0FF3WKSSVG=nivel-de-cl%C3%BAster-motivos-para-el-bloqueo-de-instalaciones-falsas cluster-level-attribution-hijacking-block-reasons=nivel-de-cl%C3%BAster-motivos-por-los-que-se-bloquea-el-secuestro-de-atribuci%C3%B3n h_01HE7S55TD3M45TH4PY2W805W7=nivel-de-cl%C3%BAster-motivos-por-los-que-se-bloquea-el-secuestro-de-atribuci%C3%B3n h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=razones-de-bloqueo-a-nivel-de-aplicaci%C3%B3n h_01HE7S55TD661EHCV50S9BW5MS=razones-de-bloqueo-a-nivel-de-aplicaci%C3%B3n retargeting=redireccionamiento h_01HE7S55TDSYDC8BWZ8D8DF9JE=redireccionamiento hijacked-installs-attribution-correction=correcci%C3%B3n-de-atribuci%C3%B3n-de-instalaciones-secuestradas h_01HE7S55TD8SDCQJCCYQC0MNES=correcci%C3%B3n-de-atribuci%C3%B3n-de-instalaciones-secuestradas h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />
