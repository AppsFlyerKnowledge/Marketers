---
title: Período de inactividad de retargeting
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-09-17T00:34:10Z'
  id: 360009305817
  locale: es
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/es/articles/360009305817
---
> **De un vistazo:** Eleva el aumento incremental reorientando a los usuarios inactivos. Configura las ventanas de inactividad por fuente multimedia.

## Periodo de inactividad

Los anunciantes recuperan a los usuarios inactivos por medio de retargeting. Estas campañas suelen tener una buena tasa de conversión y generar un ROAS significativo. Sin embargo, muchas campañas de retargeting tienen un rendimiento inferior, ya que no filtran a los usuarios activos. Para elevar el aumento incremental de las campañas de retargeting, implementa **un tiempo de inactividad mínimo** para filtrar a los usuarios activos.

Al establecer un tiempo de inactividad mínimo, los anunciantes no atribuyen a los usuarios activos. Por ejemplo, si el límite mínimo de inactividad es de tres días, no se atribuyen los usuarios activos en los últimos 0 a 3 días. Se atribuyen los usuarios inactivos durante cuatro o más días. El período de inactividad se aplicó tanto a los escenarios de reatribución como a los de re-engagement. En el caso de la reatribución, la última actividad es la última sesión antes de realizar la desinstalación.

**Reglas de inactividad**

* **Atribuidos:** Usuarios inactivos que no han usado la aplicación durante más tiempo que el período de inactividad definido. Se atribuyen los re-engagements y reinstalaciones de retargeting.
* **No atribuido**: Los usuarios activos que abren la aplicación y no superan el período mínimo de inactividad no se tienen en cuenta y no se atribuyen a la campaña de retargeting.

### Terminología de inactividad de retargeting

| Término | Definición |
| --- | --- |
| Valor máximo | 30 días. |
| Valor predeterminado | 0 (ninguno)  <br />La función **Período de inactividad** no está activa de forma predeterminada para las fuentes multimedia. |
| Actividad del usuario | Instalaciones o sesiones informadas por el SDK o mediante S2S. |
| Dispositivos migrados | La hora de migración es la hora de la última actividad. |

## Escenarios

En los siguientes escenarios de retargeting, el período de inactividad se define para la fuente de medios.

<div id="reattribution" />

<Accordion title="Reatribución">

El escenario del usuario se muestra en la figura siguiente. El usuario:

* desinstala la aplicación y está inactiva
* participa en una campaña de retargeting dirigida por una fuente de medios
* reinstala la aplicación

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| Situación | Umbral de inactividad | Periodo de inactividad del usuario | Resultado |
| --- | --- | --- | --- |
| A | 7 días | 8 días<br /><br />**El usuario estuvo inactivo** durante un período que superó el umbral de inactividad | <ul><li>**Re-atribución** (reinstalación de retargeting)</li><li>Atribuido a la fuente de medios de retargeting A</li></ul> |
| B | 14 días | 5 días<br /><br />El usuario estaba activo. | <ul><li>**Reinstalación orgánica**</li><li>**Reinstalación no orgánica:** si el usuario interactuó con una fuente multimedia de UA.</li><li>La fuente de medios de retargeting A no se puede atribuir debido al umbral de inactividad del usuario.</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="Reengagement">

El escenario del usuario se muestra en la figura siguiente. El usuario:

* instala la aplicación
* está inactivo durante varios días
* posteriormente, participa en una campaña de retargeting, dirigida por una fuente de medios, e inicia la aplicación gestionada por una fuente de medios, e inicia la app

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| Situación | Fuente multimedia Un umbral de inactividad | Periodo de inactividad del usuario | Resultado |
| --- | --- | --- | --- |
| A | 7 días | 8 días<br /><br />**El usuario estuvo inactivo** durante un período que superó el umbral de inactividad | <ul><li>**El re-engagement** se atribuye a la fuente de medios A</li></ul> |
| B | 7 días | 4 días<br /><br />**El usuario usó la aplicación** dentro del período de inactividad establecido. | <ul><li>**Sesión ordinaria**</li><li>La fuente de medios de retargeting A no está atribuida</li></ul> |

</Accordion>

## Configuración de partners

<div id="srn" />

<Accordion title="nombres de SRN reservados">

Los SRN que admiten períodos de inactividad tienen esta función configurada en la pestaña Integración.

**Para definir un período de inactividad para las redes de autorreporte (SRN) que admiten el retargeting:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas.**
2. Selecciona un SRN.
3. En la pestaña **Integración**, desplázate hacia abajo. Habilitar **Ignorar usuario activo para el retargeting**
4. Establece **la ventana de inactividad** (de 1 a 30 días). (de 1 a 30 días).
5. Haz clic en **Guardar integración**.

[![Inactivity_window_SRN.png](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="Sin SRN (haz clic en redes de publicidad)">

**Para definir un período de inactividad para las empresas que no son SRN y que admiten el retargeting:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas.**
2. Selecciona una red de publicidad.
3. Ve a la pestaña **Enlace de atribución**, desplázate hacia abajo y habilita **Ignorar usuario activo para el retargeting**.
4. Establece **la ventana de inactividad** (de 1 a 30 días).  
    El parámetro **Periodo de inactividad** `af_inactivity_window` se añade al enlace de atribución, por ejemplo, «&af\_inactivity\_window=7d». Si la función está deshabilitada, no aparece en el enlace de atribución.

[![](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)

</Accordion>

<div id="agencies" />

<Accordion title="Agencias">

#### nombres de SRN reservados

Agencia (permiso otorgado por el anunciante)

**Para acceder a la configuración del período de inactividad:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas.**
2. Selecciona un SRN.
3. En la pestaña **Integración**, realiza los ajustes como se muestra en la tabla siguiente.

| nombres de SRN reservados | Agencia |
| --- | --- |
| DoubleClick | <ul><li>Activar/desactivar el retargeting</li><li>Configurar un período de inactividad</li></ul> |
| Anuncios de Google | <ul><li>No se puede activar o desactivar el retargeting</li><li>Si una agencia tiene permisos, puede configurar un período de inactividad</li></ul> |
| Meta ads/X Ads/Snapchat | No puedo acceder a la configuración del **Período de inactividad** y retargeting |

#### Sin SRN

partner (admite el retargeting)

**Para definir un período de inactividad para las empresas que no son SRN y que admiten el retargeting:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas.**
2. Selecciona una red de publicidad que no sea de SRN. Ve a la pestaña > **Enlace de atribución.**

</Accordion>

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Enlaces de prueba | Si utilizas un dispositivo de prueba registrado, asegúrate de eliminar el parámetro `af_inactivity_window` del enlace de prueba. De lo contrario, la instalación puede atribuirse incorrectamente como *Orgánico* en lugar de atribuirse al enlace de prueba. |

<div data-zendesk-anchors="inactivity-period=periodo-de-inactividad h_01H9JS3QKW5S7VP9YW05CB6STR=periodo-de-inactividad retargeting-inactivity-terminology=terminolog%C3%ADa-de-inactividad-de-retargeting h_01H9JS3QKXMBS95RG06A9JXGT0=terminolog%C3%ADa-de-inactividad-de-retargeting scenarios=escenarios h_01H9JS3QKXWDX8Y58GX1G5HNYY=escenarios h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=configuraci%C3%B3n-de-partners h_01H9JS3QKXGNFM8499G52458B2=configuraci%C3%B3n-de-partners h_01H9JS3QKXCAHG91VS6VSVJTTT=srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=nombres-de-srn-reservados h_01H9JS3QKX88HQYJ5881W7VXF2=nombres-de-srn-reservados nonsrn=sin-srn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=sin-srn traits-and-limitations=especificaciones-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especificaciones-y-limitaciones" />
