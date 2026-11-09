---
title: Interoperabilidad de SKAdNetwork (SKAN) con Meta ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2026-09-17T00:28:55Z'
  id: 360017095198
  locale: es
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/es/articles/360017095198
---
> **Resumen:** La interoperabilidad permite que Meta ads comparta datos SKAN decodificados con AppsFlyer y que AppsFlyer comparta con Meta ads los bits de medición de CV (mapping).

<Embed title="Interoperabilidad de SKAdNetwork (SKAN) con Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

<div id="skan-interoperability-appsflyer---meta-ads" />

## Interoperabilidad SKAN: AppsFlyer &lt;-> Meta ads

Si trabajas con múltiples partners de ad networks, lo mejor es configurarlo en AppsFlyer. Al hacerlo, las métricas de rendimiento de SKAN, enriquecidas con otras métricas como costo, estarán disponibles a través de la plataforma de AppsFlyer.

<div id="scope-of-skan-interoperability-with-meta-ads" />

#### Alcance de la interoperabilidad SKAN con Meta ads

La interoperabilidad con Meta ads permite lo siguiente:

* AppsFlyer y Meta ads comparten el esquema de valor de conversión (CV) de SKAN, permitiendo que ambos proporcionen métricas de rendimiento.
* AppsFlyer admite todos los objetivos de campaña de Meta ads que permiten la optimización de campañas:
  * Instalación de app móvil (MAI)
  * Engagement de app móvil (MAE)
  * Optimización por valor (VO)
* Después de habilitar la integración SKAN ocurre lo siguiente:
  * El SDK de Facebook deja de actualizar el SKAN CV (*kill switch)*.
  * El SDK de AppsFlyer actualiza el CV.
  * Meta ads comparte datos de postbacks SKAN para incluirlos en el dashboard SKAN y en reportes agregados.

Otras consideraciones:

* Si no habilitas la integración SKAN del partner, en el dashboard SKAN las instalaciones generadas por Meta ads se contabilizan como instalaciones orgánicas.
* En el contexto de la atribución de AppsFlyer (dashboard general):
  * Las instalaciones de usuarios con consentimiento generadas por Meta ads se atribuyen correctamente.
  * Los usuarios sin consentimiento se atribuyen como orgánicos.
* <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implicaciones de iOS 14.5 en el reporte SRN</Anchor>
* Nuestra integración MMP con Meta ads siempre implementa *Advertiser Tracking Enabled*. (Esta información se proporciona de acuerdo con la lista de verificación de la aplicación de Meta ads para iOS 14 de febrero de 2021).

<div id="considerations" />

#### Consideraciones

* Una vez habilitada la interoperabilidad, cada vez que cambies configuraciones de medición no necesitarás repetir el procedimiento de integración MMP descrito en este artículo. Esto significa que no necesitas volver a copiar la URL de conexión MMP.
* En AppsFlyer, si desactivas la medición SKAN, Meta ads ya no podrá obtener el mapeo de CV.
* SDK de AppsFlyer vs. SDK de Facebook: SDK de Facebook: El SDK de Facebook es adecuado si ejecutas campañas únicamente con Meta ads. Si ejecutas campañas con múltiples partners, utilizando el SDK de AppsFlyer podrás visualizar datos de todos los partners.
* Revisa la sección de [discrepancias](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq) de este artículo.

<div id="meta-ads-app-install-ads-guidance" />

#### Guía de Meta ads para anuncios de instalación de apps

Al configurar campañas de instalación de apps iOS 14 en Meta ads, ten en cuenta la siguiente <Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">guía de Meta ads</Anchor>:

* Se permite un máximo de 9 campañas por app, cada una con 5 ad sets.
* No necesitas una cuenta separada para campañas de iOS 14. Puedes ejecutar campañas de iOS 14 desde cuentas existentes.
* Existe una relación entre el método de optimización de Meta ads y el tipo de medición que seleccionas en AppsFlyer de la siguiente manera:
  * **Medición de ingresos**: VO y AEO
  * **Medición de conversiones**: AEO — Incluye eventos estándar de Meta ads y el evento de compra. Debes mapear el evento de app en AppsFlyer al evento correspondiente de Meta ads.

<div id="interoperation-procedures" />

## Procedimientos de interoperabilidad

Completa los siguientes procedimientos para habilitar la interoperabilidad.

Para atribución de instalaciones de apps:

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="Permite que Meta ads comparta datos SKAN con AppsFlyer">

Permite que Meta ads comparta datos SKAN con AppsFlyer Permite que Meta ads comparta datos SKAN con AppsFlyer Si no lo haces, no verás instalaciones SKAN atribuidas a Meta ads en el dashboard SKAN de AppsFlyer.

Este procedimiento debe realizarse una vez por app.

**Para otorgar a Meta ads permiso para compartir datos SKAN con AppsFlyer:**

1. En AppsFlyer, ve a **Colaborar > Integraciones de Partners > Integraciones activas**.
2. Busca y selecciona Meta ads.
3. Ve a la pestaña **SKAN**.

   <Image align="center" alt="skan_repprtiing_-_connected_accounts.png" src="https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png" />
4. Haz clic en **f login**. La cuenta que utilices debe ser una cuenta admin o de anunciante <Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">con los siguientes permisos</Anchor>:
   * Permiso ads\_read. Consulta [verifica que tengas permiso ads\_read](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission).
   * Acceso al app ID anunciado en la configuración de Meta Business Partner.
5. Sigue las instrucciones de la interfaz de usuario.  
   Meta genera un <Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">token de accesp</Anchor> que permite compartir datos con AppsFlyer. Después de completar el proceso, volverás a AppsFlyer.
6. Si es la primera vez que configuras esta integración, verifica que aparezca el estado **Esperando sincronización**.  
   Este mensaje permanecerá hasta que recibamos datos de Meta ads.
7. Espera hasta después de las 02:00 UTC del día siguiente y luego verifica que el estado cambie a **Los datos se extrajeron correctamente.**  
   Los datos del dashboard SKAN se actualizan diariamente a las 08:00 UTC.
8. Lee la sección sobre [diferencias de medición](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook).

</Accordion>

Para la atribución de eventos in-app:

<div id="share-cv-schema-with-facebook" />

<Accordion title="Comparte el esquema CV con Meta ads">

<Image align="center" alt="SKAdNetwork-Facebook-AppsFlyer_integration__5_.png" src="https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png" />

<div id="enabling-appsflyer-skan-interoperation-with-meta-ads" />

#### Habilitar la interoperabilidad SKAN de AppsFlyer con Meta ads

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
      <td><span id="1"></span>
        1
      </td>
      <td>
        Requisitos previos de la app
      </td>
      <td>
        * Implementa el <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">SDK</Anchor> más reciente de AppsFlyer en tu app.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Revisión de configuración SKAN
      </td>
      <td>
        Verifica que la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">solución SKAN</Anchor> de AppsFlyer esté configurada y activada. Esto permite que el SDK de AppsFlyer invoque las APIs de SKAN y configure el CV.

        **Para ver la configuración SKAN**:

        1. En AppsFlyer, ve a **Settings** > **SKAN Conversion Studio**.
        2. Haz clic en el ícono de opciones ⋮ y verifica que **medición de SKAN** esté activado.  
           [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. Selecciona tu modo de medición preferido.  
           Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Toma nota de los nombres exactos de los eventos configurados. Los necesitarás en el siguiente paso. **Nota:** Los nombres distinguen entre mayúsculas y minúsculas.
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        Mapeo de eventos in-app
      </td>
      <td>
        Revisa y, si es necesario, realiza cambios en el mapeo de eventos in-app.

        **Para ver y configurar mapeo de eventos in-app**:

        1. En AppsFlyer, ve a **Colaborar > Integraciones de Partners > Integraciones activas**.
        2. Selecciona **Meta ads**.
        3. [Obligatorio] Desde la pestaña **Integración**, activa **Postback de evento in-app**.
           * Debes mapear el tipo de medición SKAN actualmente seleccionado. El tipo de medición predeterminado es “ingresos”.  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * Verifica que los eventos in-app configurados en la medición SKAN (**evento de AppsFlyer**) estén mapeados a identificadores de eventos de Meta ads (**mapeado al evento de partner**). Si no mapeas los eventos, Meta ads no podrá optimizar y solo contará instalaciones.

             <div id="h_01H8XRMVR5GY77K7GJ4TXGWEHS" />

             > 📘 **Nota:**
             >
             > Al agregar, modificar o eliminar un valor de conversión (CV) en SKAN Conversion Studio, asegúrate de que el evento esté mapeado en **postbacks de eventos in-app**. De lo contrario, el CV no se actualizará en Meta ads.
             >
             > #### <span id="inapp-event-mapping-guide"></span>Guía de mapeo de eventos in-app


        | Tipo de medición | Requisito de mapeo |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#custom">Personalizado</Anchor> | Mapea los eventos in-app configurados en “Personalizado” a los eventos correspondientes de Meta ads.<br /><br />Para reportar ingresos mediante postback debes configurar **Enviar ingresos** en **Valores e ingresos**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* se utiliza para ingresos generales y se mapea al evento de ingresos de Meta ads, normalmente *fb\_mobile\_purchase.*<br /><br />¡Atención! ¡Nota! Está bien mapear más de un evento a *fb\_mobile\_purchase*. |
        | <span id="revenue"></span>Ingresos | Si reportas ingresos mediante postbacks a ad networks, verifica que tus mapeos de postbacks de eventos in-app incluyan los eventos de revenue in-app configurados por ti.<br /><br />*af\_skad\_revenue* se utiliza para ingresos generales y se mapea al evento de ingresos de Meta ads, normalmente *fb\_mobile\_purchase.*<br /><br />¡Atención! ¡Nota! Está bien mapear más de un evento a *fb\_mobile\_purchase*. |
        | <span id="conversion"></span>Conversión | Mapea entre 1 y 6 eventos de conversión a los eventos correspondientes de Meta ads. |

        4. Haz clic en **Guardar integración**.
        5. Desplázate hasta **Configuración de SKAN** y haz clic en **URL de conexión MMP** para copiarla. En la siguiente sección te indicaremos dónde pegar la URL en Meta.

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        Conecta AppsFlyer con Meta ads
      </td>
      <td>
        1. En Meta ads, abre el administrador de eventos y ve a la pestaña **Configuración**.

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. En configuración, haz clic en **Configurar eventos**.

           [<Image alt="mceclip0.jpg" src="https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg" width="503px" />](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)
        3. En el Administrador de eventos, selecciona **Importar desde la aplicación de partner**. **Paso 1**:

           [<Image alt="mceclip1.png" src="https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png" width="503px" />](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. Se mostrará un campo para pegar la **URL de conexión MMP**.   
           Esto actualiza Meta con el mapeo de CV y **le indica al SDK de Facebook de tu app que deje de configurar el CV**. Si la importación desde la aplicación asociada está deshabilitada—[Solucionar problemas](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled).
        5. Sigue las instrucciones de la interfaz de usuario de Meta ads. Ocurrirá una de las siguientes situaciones:
           1. Pegas correctamente la **URL de conexión MMP** en la interfaz de Meta ads. ¡Felicitaciones! ¡Felicidades! Has completado la integración. Lee las siguientes notas.
           2. Al pegar la **URL de conexión MMP** se produce un error y aparece un mensaje en la interfaz de Meta ads. Si ocurre esto:  
              - Espera 24 horas y luego repite este procedimiento.  
              - Si el error persiste (más de 24 horas), contacta al soporte de AppsFlyer.

        Notas

        * Solo necesitas realizar este procedimiento una vez. Esto significa que no necesitas volver a copiar y pegar la URL de conexión después de cambiar la configuración de medición en AppsFlyer. Por ejemplo, si cambias de medición de ingresos a medición de conversiones, Meta ads utilizará la URL existente para obtener el esquema actual.
        * Completar el procedimiento permite que Meta ads obtenga el esquema CV desde AppsFlyer usando una estructura aleatoria propietaria. No existe forma de configurarlo manualmente.
        * Los cambios de configuración de medición pueden tardar hasta 24 horas en reflejarse en Meta ads.
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        Configuración de campañas iOS 14
      </td>
      <td>
        En Meta ads, verifica que la configuración de campañas iOS 14 esté activada.

        Esta configuración se encuentra en la página de configuración de **Campañas de nuevas instalaciones de la app**.

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="turning-off-the-skan-integration" />

<Accordion title="Desactivar la integración SKAN">

Al desactivar la integración de Meta ads, no es suficiente desactivar el botón **Activar partner**; también debes eliminar por separado las conexiones SKAN para detener el registro de datos SKAN.

**Para desactivar la integración SKAN:**

1. En AppsFlyer, ve a **Colaborar > Integraciones de Partners > Integraciones activas.**
2. Busca y selecciona Meta ads.
3. Ve a la pestaña **SKAN**.
4. Haz clic en el ícono de eliminar para la cuenta que deseas quitar.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="Diferencias de medición y tiempo entre los anuncios de AppsFlyer y Meta">

| Elemento | Detalles |
| --- | --- |
| Nombres de eventos in-app | Hasta el 15 de agosto de 2021, los nombres de eventos en el dashboard utilizaban los nombres de eventos de Meta ads. A partir de ahora, esto ya no será así. |
| Métricas de usuarios convertidos en modo ingresos | [Obsoleto desde el 16 de agosto de 2021]<br /><br />~~En modo de ingresos, la métrica de usuarios convertidos (usuarios que pagan) no considera la cantidad de usuarios que reportan ingresos mediante campañas de Meta ads debido a la convención de nombres de ingresos mencionada en la sección anterior (nombres de eventos in-app) mencionada en la sección anterior (nombres de eventos in-app)~~ |
| Disponibilidad más temprana de datos | En la primera sincronización de datos después de la integración, así como en sincronizaciones posteriores, AppsFlyer recibe datos de Meta ads retroactivamente hasta los últimos 7 días. |
| Fecha de instalación | AppsFlyer y Meta ads difieren en la forma en que determinan la fecha de instalación. Tenga en cuenta:<ul><li>Los postbacks SKAN de iOS no contienen una marca de tiempo real de instalación.</li><li>Meta ads considera el momento de llegada del postback como el momento de instalación y toma en cuenta la zona horaria de la app en Meta ads al establecer la fecha.</li><li>AppsFlyer deriva el momento de instalación según la <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#activity-window">configuración de la ventana de actividad</Anchor>. Ni la zona horaria de la app ni la zona horaria de la cuenta publicitaria de Meta ads se consideran en el cálculo.</li></ul> |
| Actualización de datos | <ul><li>Recopilamos datos SKAN de Meta ads a la 01:00 UTC</li><li>Los dashboards y datos agregados se actualizan 7 horas después.</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="Verificación del permiso ads_read">

El permiso ads\_read proporciona a los clientes de Meta ads acceso vía API a datos de rendimiento publicitario para utilizarse en dashboards personalizados y análisis de datos.

**Para verificar que tu cuenta de Meta ads tenga permiso ads\_read:**

1. Ve a tu <Anchor target="_blank" href="https://developers.facebook.com/apps">cuenta de desarrollador de Meta ads.</Anchor>
2. Selecciona un Facebook App ID.
3. Ve a **Casos de uso > Permisos y funciones**.
4. Buscar por `ads_read`.
5. Verifica que `ads_read` tenga el estado “Listo para usar”. Si es así, no se requiere ninguna acción adicional.
6. Si `ads_read` no tiene el estado “Listo para usar”, solicita el permiso y envía la solicitud.
7. Después de que Meta apruebe la solicitud, vuelve a la página de integración de Meta ads en AppsFlyer y haz clic en **Conectar**.  
   **Nota:** Meta recientemente renombró y reorganizó esta sección. Si no ves **Revisión de la app**, esto es esperado. La ubicación correcta para solicitar permisos es **Casos de uso > Permisos y funciones**.

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="Solución de problemas, discrepancias y preguntas frecuentes">

| Acción | Detalles |
| --- | --- |
| <span id="not-seeing-skan-inapp-events-from-meta"></span>¿No ves eventos in-app SKAN provenientes de Meta? | Si ves instalaciones pero no eventos in-app provenientes de campañas SKAN de Meta, esta checklist te ayudará a identificar qué falta.<br /><br />Nota: Si no estás viendo instalaciones, primero revisa la checklist de instalaciones.<br /><br />**<span id="quick-fix-checklist"></span>Checklist rápida de solución**<br /><br />**Paso 1**<ol><li>Confirma el mapeo de eventos SKAN en AppsFlyer.</li><li>Ve a **Configuración** > **SKAN Conversion Studio**.</li><li>Asegúrate de que los eventos in-app que deseas medir estén correctamente mapeados.</li></ol>**Paso 2**<ol><li>Revisa el mapeo de eventos de integración de Meta Ads.</li><li>En AppsFlyer, ve a **Colaborar > Integraciones de Partners > Integraciones activas** y selecciona **Meta ads**.</li></ol><ul><li>Asegúrate de que los mismos nombres de eventos (sensibles a mayúsculas y minúsculas) del SKAN Conversion Studio estén mapeados bajo postbacks de eventos in-app hacia Meta.</li><li>Si estás midiendo ingresos, asegúrate de que af\_skad\_revenue esté incluido y mapeado a fb\_mobile\_purchase.</li></ul>**¿<span id="still-not-working"></span>Sigue sin funcionar?**<br /><br />**>Verificación de volumen mínimo de instalaciones**<ul><li>Necesitas una cantidad mínima de instalaciones por campaña por día provenientes de Meta para que se muestren datos post-instalación de SKAN.</li><li>Las instalaciones por debajo de este umbral aparecen con valores de conversión (CVs) nulos y no se pueden decodificar datos de eventos.</li></ul>Meta no revela este umbral, pero puedes revisar la tasa de Null Conversion value en el dashboard SKAN de tu campaña. Si es ~100%, necesitas aumentar el número de instalaciones. Ajusta los filtros de la audiencia objetivo o incrementa las instalaciones de campaña. |
| <span id="facebook-cant-connect"></span>Meta ads no puede conectarse | **Síntoma**<br /><br />En Meta ads, si recibes el mensaje *no podemos conectarnos. Verifica que estés utilizando la URL correcta. Si el problema continúa, contacta a tu partner app para obtener ayuda.*<br /><br />**Acción correctiva**<br /><br />En AppsFlyer, verifica que hayas habilitado el mapeo de eventos in-app y mapeado tus eventos de AppsFlyer a los eventos de Meta ads. (Descrito en la sección anterior sobre mapeo de eventos in-app)<br /><br />[Guía actualizada el 20 de abril de 2021] |
| <span id="event-priority"></span>Prioridad de eventos | P: ¿Cómo configuro la prioridad de eventos en Meta ads?<br /><br />R: No es necesario configurar prioridades en Meta ads. Esta funcionalidad de prioridad está relacionada con apps que utilizan el SDK de Facebook para configurar el CV. En tu caso, el SDK de AppsFlyer es quien configura el CV. Ignora la opción de prioridad en Meta ads. AppsFlyer mide 6 eventos de conversión sin prioridad.<br /><br />[Guía actualizada el 20 de abril de 2021] |
| <span id="event-occurrences"></span>Ocurrencias de eventos | P: ¿Por qué veo más ocurrencias de eventos en AppsFlyer que en Meta ads?<br /><br />R: Meta ads solo contabiliza entre 0 y 1 ocurrencia de eventos. Por lo tanto, incluso si defines más ocurrencias dentro de un rango, las ocurrencias adicionales solo serán contabilizadas por AppsFlyer. |
| <span id="import-from-partner-app-is-disabled"></span>La importación desde la aplicación del partner está deshabilitada | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**Síntoma**<br /><br />En Meta ads, si **importar desde la app del partner** está deshabilitado, significa que la app nunca envió un evento a Meta ads utilizando un SDK de MMP.<br /><br />**Acción correctiva**<br /><br />Realiza una de las siguientes acciones:<ul><li>Comienza a enviar eventos a Meta ads utilizando el SDK de MMP lo antes posible.</li><li>Comienza a enviar eventos a Meta ads utilizando el SDK de Facebook o App Events API y utiliza uno de los otros flujos para configurar el esquema de conversiones.</li></ul>Una vez hecho esto, después de que los primeros eventos se registren en Meta ads, configura la integración con AppsFlyer.<br /><br />[Guía actualizada el 25 de abril de 2021] |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>Los rangos no pueden superponerse y deben estar en orden consecutivo | **Síntoma**<br /><br />Estás utilizando el modo de medición personalizado SKAN de AppsFlyer. Al importar el esquema de medición a Meta ads aparece el siguiente mensaje: *Los rangos no pueden superponerse y deben estar en orden consecutivo.*<br /><br />**Acción correctiva**<br /><br />Los valores de ingresos en el esquema de conversiones personalizado deben estar en orden ascendente consecutivo.<br /><br />[Guía actualizada el 26 de abril de 2021] |
| <span id="sending-events-to-facebook"></span>Envío de eventos a Meta ads | **P**: ¿Tiene sentido enviar postbacks adicionales de eventos para eventos no seleccionados en la opción de medición CV hacia Meta ads?<br /><br />**A**: Para usuarios con consentimiento, envía el rango completo de eventos para maximizar la capacidad de optimización de Meta ads. |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>Mapear múltiples eventos al mismo evento de Meta ads | **P**: ¿Puedo mapear múltiples eventos in-app a un único evento de Meta ads?<br /><br />**A**: Si múltiples eventos se mapean a un único evento estándar de Meta ads, Meta ads no podrá diferenciar entre ellos. Por lo tanto, Meta ads optimizará hacia el único evento que reconoce. |
| <span id="no-data-to-pull"></span>No hay datos para extraer | **P:** ¿Por qué el estado de conexión muestra “No hay datos para extraer: Comprueba tus permisos para compartir metadatos"?<br /><br />**A**: O bien aún no hay datos SKAN o necesitas iniciar sesión en Meta Ads utilizando un rol de usuario administrador en la cuenta.<br /><br />P: Recibí un mensaje de "No hay datos para extraer: Verifica tus permisos para compartir datos en Meta". Aunque veo detalles de Meta Ads, ¿todo está bien?<br /><br />**A**: Sí. Aunque este mensaje de error pueda aparecer, todo está bien y tus datos serán extraídos. |
| <span id="facebook-data-is-not-in-the-dashboard"></span>Los datos de Meta ads no aparecen en el dashboard | **Síntoma**<br /><br />En la pestaña de integración SKAN aparece el mensaje *Error al extraer datos*.<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**Acción correctiva**<br /><br />Verifica que la cuenta conectada sea una cuenta Facebook admin o una cuenta de anunciante de Meta ads con permiso ads\_read. |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>Hay un error en Meta ads cuando intentas ejecutar campañas iOS 14 | **Síntoma**<br /><br />Todo lo siguiente es verdadero:<ul><li>Recibes un mensaje de error en Meta ads cuando intentas ejecutar una campaña iOS 14</li><li>Recientemente agregaste una nueva app o una app dirigida a niños a la App Store.</li></ul>Esto ocurre porque Meta ads no sabe que estás utilizando un SDK que incluye soporte SKAN. Es decir, el SDK de AppsFlyer.<br /><br />**Acción correctiva**<ol><li>En AppsFlyer, ve a **Colaborar > Integraciones de Partners > Integraciones activas**.</li><li>Busca y selecciona **Meta Ads**.</li><li>Desde la pestaña **Integración**, desactiva **Activar partner.**</li><li>Haz clic en **Guardar integración.**</li><li>Espera 15 segundos.</li><li>Activa **Activar partner.**</li><li>Haz clic en **Guardar integración.**</li><li>Espera hasta 24 horas para que Meta ads reciba la señal.</li></ol> |
| <span id="revenue-reported-by-facebook"></span>Ingresos reportados por Meta Ads | [Actualizado el 12 de julio de 2021]<br /><br />Meta ads deriva los ingresos a partir del CV utilizando tu configuración SKAN. Sin embargo, este no es un cálculo directo y Meta ads utiliza algoritmos para determinar los ingresos.<br /><br />Un síntoma de esto es que los ingresos tengan valores no redondeados incluso si mides ingresos en dólares enteros. |
| <span id="retroactive-data-backfill"></span>Backfill retroactivo de datos | [Actualizado el 23 de diciembre de 2021]<br /><br />A veces no podemos conectarnos a Meta ads para obtener datos, por ejemplo debido a errores de login. No te preocupes. Completaremos las brechas del reporte de los 7 días anteriores la próxima vez que podamos iniciar sesión. |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>AppsFlyer muestra significativamente más instalaciones/eventos/ingresos que Meta ads | En muchos casos, esta discrepancia ocurre porque el dashboard de Meta ads muestra por defecto únicamente instalaciones o eventos click-through, mientras que el dashboard de AppsFlyer muestra tanto instalaciones y eventos click-through como view-through. |
| <span id="agency-integration"></span>Integración de agencia | Si la agencia tiene un rol de usuario administrator en la cuenta de Meta ads del anunciante, podrá realizar el procedimiento descrito en este artículo para habilitar la interoperabilidad SKAN en nombre del anunciante. Los anunciantes tampoco necesitan iniciar sesión en su cuenta de Meta ads. El login de la agencia aparecerá indicado en la cuenta del anunciante. |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>Un CV actualizado no aparece en Meta ads | Al agregar, modificar o eliminar un valor de conversión (CV) en SKAN Conversion Studio, asegúrate de que el evento esté mapeado en **postbacks de eventos in-app**. De lo contrario, el CV no se actualizará en Meta ads. |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>Diferencias en los datos modelados en AppsFlyer y Meta Ads Manager | AppsFlyer modela datos agregados que los reportes básico de SKAN no puede proporcionar. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data">Saber más</Anchor><br /><br />Cuando AppsFlyer modela datos, los datos modelados por Meta ads no se tienen en cuenta, ya que AppsFlyer se basa únicamente en datos confirmados e imparciales. Por lo tanto, pueden existir discrepancias de datos y granularidad entre los reportes de Meta ads Manager y los reportes de AppsFlyer. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de la solución de AppsFlyer SKANetwork</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=interoperabilidad-skan-appsflyer---meta-ads h_01H8XRMVR4JK6ZCGPQJE4D3T26=interoperabilidad-skan-appsflyer---meta-ads scope-of-skan-interoperability-with-meta-ads=alcance-de-la-interoperabilidad-skan-con-meta-ads h_01H8XRMVR4Q7HAJV0B7QB5MDPH=alcance-de-la-interoperabilidad-skan-con-meta-ads considerations=consideraciones h_01H8XRMVR43KEGWARYMD45S0VY=consideraciones facebook-app-install-ads-guidance=gu%C3%ADa-de-meta-ads-para-anuncios-de-instalaci%C3%B3n-de-apps h_01H8XRMVR48NWM47043YWT63HK=gu%C3%ADa-de-meta-ads-para-anuncios-de-instalaci%C3%B3n-de-apps interoperation-procedures=procedimientos-de-interoperabilidad h_01H8XRMVR4NVDZ23572F6KJTA9=procedimientos-de-interoperabilidad h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=habilitar-la-interoperabilidad-skan-de-appsflyer-con-meta-ads h_01H8XRMVR56T3X9MJ6KVJF0Z8W=habilitar-la-interoperabilidad-skan-de-appsflyer-con-meta-ads h_01H8XRMVR5GY77K7GJ4TXGWEHS=nota inapp-event-mapping-guide=gu%C3%ADa-de-mapeo-de-eventos-in-app h_01H8XRMVR5T28Q0E8KP6BZ6CGH=gu%C3%ADa-de-mapeo-de-eventos-in-app additional-information=informaci%C3%B3n-adicional h_01H8XRMVR5WXZ88676PAW9BKC9=informaci%C3%B3n-adicional h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01K7P24YAYSPB84PV0ZGBJ0QB0=quick-fix-checklist h_01K7P2811MRTVRC0D6YGVSXY4C=still-not-working h_01HE7SMBXBCEQM7KF2RG3V16KV=consulta-tambi%C3%A9n" />
