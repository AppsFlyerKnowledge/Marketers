---
title: Explicación de la ventana de reatribución
metadata:
  keywords:
    - Retargeting
    - Re-Attribution
    - reattribution
    - Advertisers
    - Ad Networks
    - re-attribution window
    - reattribution window
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
  created_at: '2017-05-23T08:55:35Z'
  edited_at: '2026-08-12T11:57:21Z'
  id: 115002587066
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/115002587066
---
> **En resumen:** De un vistazo: Aprende sobre la ventana de reatribución, durante la cual las reinstalaciones no se atribuyen como instalaciones nuevas.

## Ventana de reatribución

La ventana de reatribución es una ventana de tiempo que comienza la primera vez que un usuario instala la aplicación y continúa durante la duración establecida por el anunciante (por defecto 90 días). Durante la ventana de reatribución, las reinstalaciones de la aplicación no se registran como nuevas instalaciones y no generan un postback de nueva instalación a menos que se originen en una campaña de **retargeting**.

[![ReAttributionWindow_us-en.png](https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png)](https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png)

### Configuración de la ventana de reatribución

La ventana de reatribución:

* se establece en la página <Anchor target="_blank" href="/marketers/es/docs/app-settings">Configuración de la aplicación</Anchor>
* el valor predeterminado es 90 días (3 meses)
* tiene un rango de 1 a 24 meses

Las instalaciones se evalúan en relación con la configuración en el momento de la instalación. Por lo tanto, si se cambia la configuración, afecta a las instalaciones (reinstalaciones) a partir de ese momento, sin tener en cuenta las instalaciones anteriores.

* **Cambiar la ventana de reatribución de 90 a 30 días**:
  * Se instala el 1 de septiembre.
  * La ventana de reatribución cambia el 2 de septiembre.
  * Una reinstalación hasta el 1 de octubre se considera una reinstalación. A partir del 2 de octubre, se considera una nueva instalación.
* **Cambiar la ventana de reatribución de 30 a 90 días**:
  * Se instala el 1 de septiembre.
  * La ventana de reatribución cambia el 2 de septiembre.
  * Una reinstalación el 15 de octubre es una reinstalación debido a la ventana actual de 90 días.
  * Una reinstalación el 15 de diciembre es una instalación nueva porque han transcurrido más de 90 días desde la instalación el 1 de septiembre.

## Casos de uso de la ventana de reatribución

<div id="first-install" />

<Accordion title="Primera instalación">

Un usuario potencial (que nunca ha instalado la aplicación) interactúa con una campaña de adquisición de usuarios o retargeting e instala la aplicación móvil.

Sucede lo siguiente:

* Se atribuye una nueva instalación (u orgánica, si no se registra ningún engagement) a la fuente de medios en los paneles de control y los datos de adquisición de usuarios.
* Comienza una nueva ventana de reatribución.
* Los postbacks de instalaciones y eventos in-app se envían a la fuente de medios atribuida si está configurada.
* Los siguientes eventos in-app también se atribuyen a la misma fuente de medios.

</Accordion>

<div id="reinstall" />

<Accordion title="Reinstalar">

Después de la primera instalación de la aplicación, el usuario la desinstala y vuelve a instalar durante la ventana de reatribución.

Sucede lo siguiente:

* La instalación NO se atribuye: no aparece en el panel de control, ni en los datos.
* NO se envía un postback de instalación a ninguna fuente de medios.
* Dependiendo del estado de <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#overview">**Atribución de eventos posteriores a la reinstalación**</Anchor> , los eventos en la aplicación de estos usuarios que reinstalan se atribuyen a la instalación orgánica o a la original.

</Accordion>

<div id="reattribution" />

<Accordion title="Re-atribución">

Después de la primera instalación de la aplicación, durante la ventana de reatribución, el usuario la desinstala y luego interactúa con una campaña de retargeting y la reinstala.  
Esto se llama reatribución.

Sucede lo siguiente:

* La instalación se atribuye a la fuente de medios de retargeting en la vista de retargeting y unificada del panel de control general. En otras palabras, la vista de adquisición de usuarios no contiene reatribuciones.
* Todos los siguientes eventos in-app se atribuyen a la fuente de medios de retargeting.
* Se envía un postback de instalación a la fuente de medios de retargeting.

Para obtener más información sobre la atribución de retargeting, haz clic <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">aquí</Anchor>.

</Accordion>

<div id="new-install" />

<Accordion title="Nueva instalación">

El usuario desinstala la aplicación. Luego, cuando termina la ventana de reatribución, el usuario vuelve a instalarla. Esta reinstalación se considera una primera instalación y aporta los mismos resultados:

* Se atribuye una nueva instalación (u orgánica, si no se registra ningún engagement) a la fuente de medios en los paneles de control y los datos de adquisición de usuarios.
* **Comienza una nueva ventana de reatribución.**
* Los postbacks de instalaciones y eventos in-app se envían a la fuente de medios atribuida si está configurada.
* Los siguientes eventos in-app también se atribuyen a la misma fuente de medios.

</Accordion>

<div id="ios-app-restored-from-icloud-backup" />

<Accordion title="Aplicación de iOS restaurada desde la copia de seguridad de iCloud">

Independientemente de la ventana de reatribución, cuando se realiza una copia de seguridad de una aplicación mediante iCloud y luego se restaura (en el mismo dispositivo o en otro), AppsFlyer no la cuenta como una instalación nueva o reinstalación. Un usuario que restaura una aplicación desde iCloud conserva su ID de AppsFlyer y sus datos de atribución.

</Accordion>

<div data-zendesk-anchors="reattribution-window=ventana-de-reatribuci%C3%B3n h_01H95B0F8XEX9RFXW8W6QBQJBY=ventana-de-reatribuci%C3%B3n setting-the-reattribution-window=configuraci%C3%B3n-de-la-ventana-de-reatribuci%C3%B3n h_01H95B0F8X2YQWBB9H0WFXPK8C=configuraci%C3%B3n-de-la-ventana-de-reatribuci%C3%B3n reattribution-window-use-cases=casos-de-uso-de-la-ventana-de-reatribuci%C3%B3n h_01H95B0F8Y4T13VYEN2D7T5GHR=casos-de-uso-de-la-ventana-de-reatribuci%C3%B3n h_01H95B0F8Y58QFRSJ9TV3J34EX=first-install h_01H95B0F8YBY482KHT09CZNT9E=reinstall h_01H95B0F8YCQV3H6ZSZE0DF5VV=reattribution h_01H95B0F8Y046Q80V0S8YZ1DWG=new-install h_01H95B0F8Y6M7W02ZSNYCN66PD=ios-app-restored-from-icloud-backup" />
