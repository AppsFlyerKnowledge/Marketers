---
title: Obtener datos de postbacks de SKAN de Google Ads
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
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-09-10T00:29:42Z'
  id: 4403215779857
  locale: es
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/es/articles/4403215779857
---
> **De un vistazo:** Permite que Google comparta el contenido de tus postbacks de iOS de la aplicación SKAdNetwork (SKAN) con AppsFlyer.

<div id="get-skan-postback-data-from-google-ads" />

## Obtener datos de postbacks de SKAN de Google Ads

Si trabajas con varios partners de redes de publicidad, es mejor configurarlo en AppsFlyer. Al hacerlo, las métricas de rendimiento de SKAN para todos tus partners de redes de publicidad, enriquecidas con otras métricas como el costo, están disponibles a través de la plataforma AppsFlyer.

**Alcance de los reportes de SKAN con Google Ads**

* Google Ads comparte los postbacks de SKAN agregados de iOS que recibe con AppsFlyer en el contexto de campañas de aplicaciones iOS. Estos postbacks representan instalaciones de múltiples canales como display y YouTube, pero generalmente excluyen la mayor parte de las búsquedas, ya que SKAN no admite el seguimiento de la web a aplicación en este momento.
* AppsFlyer decodifica el postback y luego actualiza el panel de control de SKAN y los reportes (incluido el reporte de raw data de postbacks).
* <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implicaciones de iOS 14.5 en los reportes de SRN</Anchor>

**Consideraciones**:

Al recibir el postback de iOS, Google determina la hora del último clic utilizando las señales de servicio de anuncios. Sin embargo, AppsFlyer considera la hora del clic como la hora de instalación. Esto puede dar lugar a diferencias entre los paneles de control de AppsFlyer y Google.

Debido a la metodología de generación de reportes de clics de Google y su actualización retroactiva de datos a diario, AppsFlyer extrae los datos de los 45 días anteriores y muestra la instalación bajo el último clic antes de la fecha de instalación.  Por ejemplo, un clic el 1 de julio se puede reportar a AppsFlyer hasta el 15 de agosto. AppsFlyer muestra esta instalación bajo la fecha de clic reportada por Google. Esto afecta a los <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#reporting-options">reportes</Anchor> de la siguiente manera:

* Los informes de estadísticas agregadas y el panel de control se actualizan retroactivamente.
* Los <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">reportes de raw data</Anchor> no cambian retroactivamente. Los datos (proporcionados a través de Data Locker) se proporcionan en carpetas según la fecha en que Google proporcionó los datos a AppsFlyer (fecha de llegada de datos).

<div id="set-up-interoperation" />

## Configurar la interoperación

Para configurar la interoperación con Google Ads, completa los pasos en las siguientes pestañas.

<Accordion title="Configurar postbacks">

**Para configurar el envío de postbacks:**

| Paso | Acción | Detalles |
| --- | --- | --- |
| 1 | Revisión de la configuración de SKAN | Verifica que la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">solución SKAN</Anchor> de AppsFlyer esté configurada y activada. Al hacerlo, el SDK de AppsFlyer puede llamar a las API de SKAN y establecer el valor de conversión.<br /><br />**Para revisar la configuración de SKAN**:<ol><li>En AppsFlyer, ve a **Ajustes** > **SKAN Conversion Studio**.</li><li>Haz clic en opciones (⋮), y verifica que **la medición de SKAN** esté activada.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Selecciona el modo de medición que prefieras.<br />Obtén más información sobre <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Toma nota de los nombres exactos de los eventos configurados. Los necesitarás en el siguiente paso. **¡Nota**! Los nombres distinguen entre mayúsculas y minúsculas.</li></ol> |
| 2 | Asignación de eventos in-app en AppsFlyer | **Para ver y configurar la asignación de eventos in-app**:<ol><li>En AppsFlyer, ve a **Colaborar** > **Integraciones activas**.</li><li>Selecciona **Google Ads**.</li><li>En la pestaña **Integración**, verifica que **Activar partner** esté activado. Si no, primero debes completar la <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">integración con Google Ads</Anchor>.</li><li>En la sección **Postbacks de eventos in-app**:<ol><li>Si no está activo, activa **Postbacks de eventos in-app**.</li><li>La práctica recomendada es asignar los eventos relacionados con el tipo de medición seleccionado actualmente. ¡Atención! En el caso de la medición de ingresos, asigna af\_skad\_revenue al evento de ingresos de Google correspondiente.</li></ol></li><li>Desplázate hasta el final de la página.</li><li>Haz clic en **Guardar integración**.</li></ol> |

</Accordion>

<Accordion title="Permitir que Google Ads comparta datos de SKAN con AppsFlyer">

Para poder ver las instalaciones de SKAN atribuidas a Google Ads en el panel de control de SKAN de AppsFlyer, debes permitir que Google Ads comparta datos de SKAN con AppsFlyer.

**Para otorgar a Google Ads permiso para compartir datos SKAN con AppsFlyer:**

1. El procedimiento que sigue debe realizarlo el anunciante. Si se trata de una agencia, tanto la agencia como el anunciante tienen que activar la medición de SKAN.
2. En AppsFlyer, ve a **Colaborar** > **Integraciones activas**.
3. Busca y selecciona **Google Ads**.
4. Ve a la pestaña **SKAN** . <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. Si **aparece el mensaje temporalmente no disponible**, la mayoría de las veces significa que hay un bloqueador de anuncios activo. Si es así, desactiva el bloqueador de anuncios y vuelve a cargar la página. Si este no es el caso, ponte en contacto con el equipo de soporte de AppsFlyer.  ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. Haz clic en **Conectar** **Google Ads**.
   * Debes iniciar sesión en Google Ads utilizando un rol de usuario Administrador en la cuenta.
   * Si la cuenta de Google está asociada con varias aplicaciones, inicia sesión una vez y se autorizarán todas las aplicaciones. En otras palabras, no hay necesidad de autorizar por aplicación.
   * AppsFlyer extrae datos de todas las aplicaciones AppsFlyer de iOS a las que está asociada tu cuenta de Google, independientemente de la configuración de activación del partner de la aplicación.
7. Sigue las instrucciones de la interfaz de usuario.
8. En algunos casos, es posible que se te pida que otorgues permiso a AppsFlyer para **administrar tus campañas de AdWords.** Si es así, debes habilitar el permiso. No te preocupes, no modificaremos la configuración de tu campaña. [<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. Comprueba que aparece el estado de la cuenta **en espera de sincronización** .  
   Este mensaje persiste hasta que obtengamos datos de Google Ads (máximo 24 horas).
10. Espera hasta después de las 02:00 UTC del día siguiente y verifica que el estado cambie a **activo.**  
    Los datos del dashboard SKAN se actualizan diariamente a las 08:00 UTC. **Nota**! Como se describe en el apartado de consideraciones, Google puede actualizar los datos retroactivamente durante 45 días.
11. Lee sobre las [diferencias de medición](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

<div id="additional-information" />

## Información adicional

<Accordion title="Desactivar la integración de SKAN">

Al desactivar la integración de Google Ads, no basta con desactivar el selector **Activar partner**, sino que debes eliminar por separado las conexiones de SKAN para detener el registro de datos de SKAN.

**Para desactivar la integración de SKAN:**

1. En AppsFlyer, ve a **Colaborar** > **Integraciones activas**.
2. Busca y selecciona Google Ads.
3. Ve a la pestaña **SKAN**.
4. Haz clic en el icono de eliminación de la cuenta que deseas eliminar.

</Accordion>

<Accordion title="Diferencias de medición y tiempo entre AppsFlyer y Google Ads">

| Elemento | Detalles |
| --- | --- |
| Disponibilidad de datos más temprana | Los datos están disponibles a partir de la fecha en que habilitas la integración según la hora UTC. Debido a que Google utiliza la hora de clic, las instalaciones anteriores a la fecha de inicio pueden mostrarse retroactivamente. |
| Fecha de instalación | Google establece la hora de instalación en la hora estimada del último clic antes de la instalación. Es Google quien determina la hora de clic utilizando señales de servicio de anuncios.<br /><br />Se debe tener en cuenta lo siguiente al comparar las fuentes de medios y el panel de control en AppsFlyer:<ul><li>AppsFlyer no considera la zona horaria de la aplicación ni la zona horaria de la cuenta de anuncios de Google Ads.</li><li>Google puede reportar las instalaciones retroactivamente durante 45 días después de la fecha de clic.</li><li>En el caso de otras fuentes de medios, derivamos la hora de instalación utilizando la hora de llegada del postback.</li></ul> |
| Instalaciones | Desde la API V10+ de Google Ads, AppsFlyer solo muestra las instalaciones de postbacks con did\_win=TRUE. Como resultado, el número de instalaciones en AppsFlyer puede ser menor que en el panel de Google Ads. |

</Accordion>

<Accordion title="Resolución de problemas y preguntas frecuentes">

| Elemento | Detalles |
| --- | --- |
| Envío de eventos a Google Ads | **P**: ¿Tiene sentido enviar postbacks de eventos adicionales a Google Ads para los eventos no seleccionados en la opción de medición del valor de conversión?<br /><br />**R**: Para los usuarios con consentimiento, envía toda la gama de eventos para maximizar la capacidad de optimización de Google Ads. |
| Asignar varios eventos al mismo evento de Google Ads | **P**: ¿Puedo asignar varios eventos in-app a un evento de Google Ads?<br /><br />**R**: Si se asignan varios eventos a un evento estándar de Google Ads, Google Ads no puede diferenciar entre los eventos. Entonces, Google Ads optimizará hacia el evento que reconozca. |
| Tipos de campaña admitidos | **P:** ¿Qué tipos de campañas de Google Ads son compatibles?<br /><br />**R**: Campañas iOS de web a aplicación y de aplicación a aplicación que incluyen búsqueda, video, etc. |
| No hay datos que extraer | **P:** ¿Por qué muestra el estado de la conexión "No hay datos que extraer: comprueba tus permisos de uso compartido de datos de Google"?<br /><br />**R**: O bien aún no hay datos de SKAN, o debes iniciar sesión en Google Ads usando un rol de usuario Administrador en la cuenta. |

</Accordion>

<Accordion title="Especificaciones y limitaciones">

| Espec | Descripción |
| --- | --- |
| Vistas involucradas | Las vistas involucradas se cuentan como clics y los postbacks se envían para ellas como para cualquier atribución de clics. |
| Actualización de los datos | <ul><li>Recopilamos datos de SKAN de Google Ads diariamente a partir de la 01:00 UTC.</li><li>Los paneles de control y los datos agregados se actualizan 7 horas después.</li><li>Google experimenta ocasionalmente retrasos en su pipeline de SKAN, por lo que los datos pueden llegar más tarde de lo habitual y los datos de Single Source of Truth (SSOT) también pueden verse afectados.<ul><li>Una vez que Google entrega los datos retrasados, se actualizan de forma retroactiva.</li></ul></li></ul> |
| Reportes disponibles | Los datos de Google Ads están disponibles en el panel de control de SKAN, los informes de estadísticas agregadas y los reportes de raw data. Consulta las <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#reporting-options">opciones de reporting de SKAN</Anchor>. |
| Agencias | Si la agencia tiene un rol de usuario Administrador en la cuenta de Google Ads del anunciante, puede realizar el procedimiento indicado en este artículo para habilitar la interoperación de SKAN de Google en nombre del anunciante. Los anunciantes tampoco necesitan iniciar sesión en sus Google Ads. El inicio de sesión de la agencia se indica en la cuenta del anunciante. |

</Accordion>

<Accordion title="¿No ves instalaciones de SKAN de Google Ads?">

Usa esta lista de verificación para confirmar que la configuración es correcta y que los datos pueden llegar al dashboard de SKAN de AppsFlyer.

**Checklist rápida de solución**

1. Comprueba el estado de la integración.
   * Confirma que la integración de Google Ads está activa en AppsFlyer.
   * En la pestaña **SKAN**, verifica que el estado muestre **Activo**. Si muestra **Temporalmente no disponible**, desactiva cualquier bloqueador de anuncios y vuelve a cargar la página.
2. Autoriza la conexión de Google Ads si todavía no está conectada.
   * Haz clic en el **inicio de sesión de Google Ads**.
   * Inicia sesión con una cuenta de administrador de Google Ads y permite que AppsFlyer gestione las campañas de AdWords si se te solicita.
3. Espera la sincronización.
   * Después de iniciar sesión, el estado muestra **Esperando sincronización**.
   * Cuando AppsFlyer empiece a recibir datos de SKAN de Google, el estado cambiará a **Activo**; esto puede tardar hasta 24 horas.
   * Desplázate hasta el final de la página.

**¿Sigue sin funcionar?**

Si has completado los pasos anteriores y las instalaciones siguen sin mostrarse, comprueba lo siguiente:

* Si el estado muestra "No data to pull: Check your Google data-sharing permissions", Google aún no ha compartido datos de SKAN o necesitas iniciar sesión en Google Ads con un rol de usuario de Administrador.
* Asegúrate de que estás ejecutando campañas específicas de SKAN en Google Ads y de que has iniciado sesión con una cuenta de administrador.
* Comprueba directamente los recuentos de instalaciones en Google Ads:

  1. El procedimiento que sigue debe realizarlo el anunciante, la agencia, o ambos.
  2. Haz clic en el icono **Reports** > **Goals and conversions** > **SKAdNetwork conversions**.
  3. Si ves "Error loading report — This report is incompatible with the current view filters", haz clic en **Clear view filters**.
  4. Usa la búsqueda de columnas (icono de lupa) para encontrar y añadir columnas específicas de SKAN, como **SKAdNetwork conv. segmento de valor**.

  Si no hay instalaciones en Google, tampoco las habrá en AppsFlyer. Consulta con tu representante de Google para entender por qué no hay instalaciones.

**Bien saberlo**

* Los datos de SKAN se recopilan de Google Ads a diario a partir de las 01:00 UTC. A veces, los datos de Google pueden tardar hasta dos días más en llegar.
* Solo se admiten campañas de iOS Web-to-app y App-to-app para la medición de SKAN.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de soluciones SKAN de AppsFlyer</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=obtener-datos-de-postbacks-de-skan-de-google-ads h_01HCHYGCVJA3C8WJS8JH7BG0CD=obtener-datos-de-postbacks-de-skan-de-google-ads set-up-interoperation=configurar-la-interoperaci%C3%B3n h_01HCHYGCVJY5KT4J6RQS0BJ90G=configurar-la-interoperaci%C3%B3n additional-information=informaci%C3%B3n-adicional h_01HCHYGCVJTS53PCGK21BEZB2T=informaci%C3%B3n-adicional h_01HE7RMSECNDW9VD9XY6H01H55=consulta-tambi%C3%A9n" />
