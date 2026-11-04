---
title: Interoperabilidad de SKAN con Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2026-08-12T12:21:03Z'
  id: 360017604077
  locale: es
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/es/articles/360017604077
---
> **En resumen:** La interoperabilidad de SKAN permite a TikTok compartir postbacks de SKAN con AppsFlyer y permite a AppsFlyer compartir tu asignación de medición de valor de conversión con TikTok.

<div id="skan-interoperability-appsflyer---snapchat" />

## Interoperabilidad de SKAN: AppsFlyer &lt;-> Snapchat

Si trabajas con varios partners de redes de publicidad, la mejor práctica es configurar tu integración de SKAN en AppsFlyer. Al hacerlo, las métricas de rendimiento de SKAN, enriquecidas con otras métricas como el costo, están disponibles a través de la plataforma AppsFlyer. 

**Alcance de la interoperabilidad de SKAN con Snapchat**

La interoperabilidad permite que AppsFlyer y Snapchat compartan el asignación de valores de conversión de SKAN, lo que permite que ambos le proporcionen métricas de rendimiento. Si habilitas la integración de partners de Snapchat en AppsFlyer, entonces AppsFlyer proporciona a Snapchat eventos para fines de optimización.

**Guía de anuncios de instalación de la aplicación Snapchat**

Al configurar la campaña de instalación de la aplicación Snapchat iOS 14, tenga en cuenta la siguiente guía de Snapchat:

*A partir del 18 de febrero de 2021, SKAdNetwork estará disponible en Snapchat Ads Manager para todos los anunciantes. Recomendamos que las aplicaciones se configuren y comiencen a probar, para garantizar que no haya interrupciones en la medición o la escala de las campañas de adquisición de aplicaciones de iOS 14 en Snapchat. En el futuro, SKAdNetwork será un requisito para acceder a las ofertas basadas en objetivos de aplicaciones para campañas iOS en Snapchat.*

*Completa la integración de SKAdNetwork en tu panel de control de AppsFlyer MMP y completa la configuración de tu asignación de valor de conversión antes de lanzar los conjuntos de anuncios de SKAdNetwork dentro de Snapchat Ads Manager. La guía de configuración de Snapchat para SKAdNetwork se puede encontrar [aquí](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Requisitos de implementación**

Considera lo siguiente en Snapchat:

* Configura un [ID de aplicación Snap](https://businesshelp.snapchat.com/en-US/a/snap-app-id) para cada aplicación que anuncies en Snapchat.
* Opta por los conjuntos de anuncios de Snapchat para la medición de SKAN.
* Para una aplicación determinada, está limitado a un máximo de 10 conjuntos de anuncios a la vez habilitados para la atribución de SKAN.

<div id="enabling-appsflyer-skan-interoperation-with-snapchat" />

### Habilitación de la interoperabilidad de SKAN de AppsFlyer con Snapchat

La interoperabilidad se logra a través de configuraciones en los paneles de control de AppsFlyer y Snapchat. No se requiere ninguna interoperabilidad en la propia aplicación. Sin embargo, es necesario adoptar el SDK de AppsFlyer más reciente.

<Table>
  <thead>
    <tr>
      <th>
        Paso
      </th>
      <th>
        Acción
      </th>
      <th>
        Detalles
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>
      <td>
        Requisitos previos de la aplicación
      </td>
      <td>
        * Adopta el <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">SDK</Anchor> de AppsFlyer más reciente en tu aplicación.
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        Revisión de la configuración de SKAN
      </td>
      <td>
        Configura y activa la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAN</Anchor> de AppsFlyer

        **Para ver la configuración de SKAN**:

        1. En AppsFlyer, ve a **Ajustes** > **SKAN Conversion Studio**.
        2. Haz clic en las opciones (⋮), y verifica que la **medición de SKAN** esté activada.  

           ![skan-settings.png](https://files.readme.io/e4c36e8f5b10a7a4593a8dc776c4c8c43df88577dae8a812303b2d7b3ee37797-4406452401425.png)
        3. Selecciona el modo de medición que prefieras.  
           Aprender más sobre <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Toma nota del conjunto exacto de nombres de eventos. Los necesitas en el siguiente paso.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        Asignación de eventos in-app
      </td>
      <td>
        Revisa y, si es necesario, realiza cambios en las asignaciones de eventos en la aplicación de Snapchat.

        **Para ver y establecer las asignaciones de eventos in-app**:

        1. En AppsFlyer, ve a **Configuración** > **Integraciones activas**.
        2. Busca y selecciona **Snapchat**.
        3. Desde la pestaña **Integración**, si la opción **Activar partner** no está activada, actívala.
        4. Verifica y, si es necesario, actualiza el ID de la aplicación Snap que se muestra en AppsFlyer con el ID de la aplicación que se muestra en el <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">panel de control de Snapchat</Anchor>.
        5. Si no está activo, activa **Postbacks de eventos in-app**.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png" width="432px" />](https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png)

           Verifica que los **nombres de eventos del SDK** de los eventos in-app que configuraste en la medición de SKAN estén asignados a **identificadores de eventos de Partners,** es decir, a los nombres de eventos de Snapchat. Debes asignar los eventos de tipo de medición SKAN seleccionados actualmente o los eventos en tu <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">asignación de conversión personalizado</Anchor>.   
           [Práctica recomendada]: El tipo de medición predeterminado es “ingresos”.

           <div id="inapp-event-mapping-guide" />

           <div id="in-app-event-mapping-guide" />

           #### Guía de mapeo de eventos in-app

        | Tipo de medición | Requisito de mapeo |
        | --- | --- |
        | Personalizado | Asigna los eventos in-app que configuras en Personalizado a los eventos Snap correspondientes.<br /><br />Para reportar los ingresos por postback, debes establecer Enviar ingresos a **Valores e ingresos**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* se utiliza para los ingresos generales y se asigna al evento de ingresos de Snap.<br /><br />[Práctica recomendada]: Está bien asignar más de un evento a el evento de ingresos de Snap. |
        | Ingresos totales | Asigna af\_skad\_revenue a COMPRA |
        | Conversión | Asigna los eventos de conversión del 1 al 6 a los eventos de Snapchat correspondientes. |
        | Participación | Asigna el evento de participación que configuraste al evento de Snapchat correspondiente. |

        6. Haz clic en **Guardar integración**.
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Permitir que Snapchat comparta postbacks con AppsFlyer
      </td>
      <td>
        1. Ve a tu panel de control de Snapchat.
        2. En **Comparte postbacks con este MMP**, selecciona AppsFlyer.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. Haz clic en **Actualizar**.
      </td>
    </tr>
  </tbody>
</Table>

<div id="additional-information" />

## Información adicional

<div id="discrepancies-guide" />

<Accordion title="Guía de discrepancias">

| Discrepancia | Detalles |
| --- | --- |
| Filtros del panel de control | **Causa de discrepancia**<ul><li>AppsFlyer: El panel de SKAN contiene instalaciones relacionadas con los postbacks de iOS recibidos.</li><li>Snapchat: De forma predeterminada, el panel de control y el reporte de Snapchat incluyen tanto SKAN como instalaciones atribuidas tradicionalmente (IDFA). Filtra el reporte de Snapchat para obtener solo instalaciones de SKAN.</li></ul>**Solución**<br /><br />Alinea los filtros del panel de control de Snapchat para mostrar solo las instalaciones de SKAN como se indica en la captura de pantalla que sigue.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Diferencias en la fecha de instalación | **Causa de discrepancia**<br /><br />Puede haber diferencias entre las fechas de instalación de AppsFlyer y Snapchat como se indica a continuación:<ul><li>AppsFlyer: Deriva la fecha de instalación utilizando la siguiente fórmula: Hora de llegada del postback: 24 horas Ventana de medición (predeterminado: 24 horas). Entonces el ajuste predeterminado es 48 horas. Todas las horas UTC. <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#skan">Actualización de los datos de SKAN.</Anchor></li><li>Snapchat: Generalmente, utiliza la hora de llegada del postback de iOS como fecha de instalación sin ajustes.</li></ul>**Solución**<br /><br />Tenga en cuenta lo anterior al comparar resultados. |

</Accordion>

<div id="see-also" />

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de la solución SKAN de AppsFlyer</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=interoperabilidad-de-skan-appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=interoperabilidad-de-skan-appsflyer---snapchat enabling-appsflyer-skan-interoperation-with-snapchat=habilitaci%C3%B3n-de-la-interoperabilidad-de-skan-de-appsflyer-con-snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=habilitaci%C3%B3n-de-la-interoperabilidad-de-skan-de-appsflyer-con-snapchat inapp-event-mapping-guide=gu%C3%ADa-de-mapeo-de-eventos-in-app h_01HDNZ3SPA742313RAJPYSEHWV=gu%C3%ADa-de-mapeo-de-eventos-in-app additional-information=informaci%C3%B3n-adicional h_01HDNZ3SPASN8P9G5YYQGRFC8F=informaci%C3%B3n-adicional h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=ver-tambi%C3%A9n" />
