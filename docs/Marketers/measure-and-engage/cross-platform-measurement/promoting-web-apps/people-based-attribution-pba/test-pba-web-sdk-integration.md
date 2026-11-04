---
title: Prueba la integración del SDK web de PBA
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2026-08-12T12:11:48Z'
  id: 360012729178
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360012729178
---
> **De un vistazo:** prueba la integración del complemento Web SDK PBA.

<div id="test-pba-web-events" />

## Prueba los eventos web de la PBA

**Principios de uso de la página de prueba.**

Web SDK envía eventos web a PBA, que están disponibles a través de paneles de control de PBA e reportes de raw data, después del procesamiento diario. Para permitir un proceso de prueba eficiente, envía eventos de prueba sin esperar el procesamiento diario. Los eventos de prueba son:

* Analizado y validado al recibirlo.
* Disponible para ti en la interfaz de usuario. Esto incluye errores de procesamiento. Si existen, envía los eventos corregidos nuevamente para asegurarse de que se procesen correctamente.
* Se procesan como cualquier otro evento durante el procesamiento diario. Esto significa que se agregan a los paneles de control y a la raw data.

<div id="web-sdk-integration-test-page" />

#### Página de prueba de integración del SDK web

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**Vista principal de la página**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * Los eventos más recientes aparecen primero.
        * **Caché de eventos**:
          * Contiene hasta 100 eventos.
          * Los eventos más antiguos se eliminan para dar paso a eventos más nuevos.
          * Los eventos almacenados en caché se eliminan después de 24 horas
        * **Controles de página**:
          * **Indicador de frecuencia de actualización**: La página se actualiza automáticamente cada 5 segundos.
          * **Borrar todo**: Borra eventos del caché de forma permanente. **¡Atención!** **Nota:** El caché es común a los sitios web que comparten la misma clave de desarrollo web. Por lo tanto, si otro desarrollador está utilizando la página de prueba, también se borrará para él.
          * **Pausa/inicio**: Pausa la actualización automática. Los nuevos eventos no se muestran hasta que haces clic en iniciar.

        **Columnas de la tabla de eventos**

        | Campo | Descripción |
        | --- | --- |
        | Hora (UTC) | Hora del evento |
        | Tipo de evento | Los tipos de eventos son los siguientes:<br /><br />* Eventos enviados por ti:<br />  * `EVENT`<br />  * `setCustomerUserId`<br />  * `pageLoad`: Enviado por el SDK web cada vez que se carga/actualiza una página en tu sitio web |
        | Contenido del evento | La carga útil del evento, según lo registrado por PBA. |
        | Comentarios | * **Válido**: la PBA recibió y registró el evento. No se requiere ninguna acción adicional.<br />* **Inválido**: lista de errores que requieren acción correctiva. El formato del mensaje de error es:  <br />  nombre del campo del evento: descripción del error<br />* Pasa el cursor sobre los mensajes de error para ver los detalles:  <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **Vista detallada**[<Image alt="mceclip0.png" src="https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png" width="573px" />](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        Haz clic en una fila de evento para mostrar su contenido después del procesamiento. Consulta <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">los parámetros de eventos del SDK web</Anchor> para obtener información adicional.
      </td>
    </tr>
  </tbody>
</Table>

<div id="procedures" />

## Procedimientos

Completa los procedimientos que siguen.

<div id="enable-test-mode" />

<Accordion title="Habilitar modo de prueba">

**Requisitos previos**

Antes de realizar la prueba, <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#installation-and-integration">el SDK web debe implementarse en tu sitio web</Anchor> o en un sitio web de prueba.

**Limitación del navegador**

Si el modo de prueba está habilitado en un navegador determinado, independientemente de la pestaña; el navegador sólo se puede utilizar para conectarse al sitio web especificado y no a ningún otro sitio web. Utiliza un navegador diferente, por ejemplo, Safari en lugar de Chrome, para conectarse desde la misma máquina a un sitio web diferente.

**Para habilitar el modo de prueba:**

1. **Verifica que el SDK esté cargado:**
   1. En AppsFlyer, en el menú superior, selecciona **Mis aplicaciones** > **Ver paquetes de marcas.**
   2. Selecciona la prueba requerida **de integración del SDK web.**  
      Se abre la página de integración. Se muestra la clave de desarrollo web.  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. En una nueva pestaña del navegador, ve a tu sitio web (que tiene instalado el SDK web).
   4. Haz clic derecho y selecciona inspeccionar para abrir las herramientas de desarrollo del navegador.
   5. Vaya a la pestaña **Consola**.
   6. En la consola, ingresa:  

      ```javascript
      ventana.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      Se muestra el ID de la aplicación web.

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. Verifica que webAppID sea idéntica a la clave de desarrollo web en la página **de prueba de integración del SDK web** .
2. **Habilita el modo de prueba**:
   1. En la pestaña del navegador del sitio web, ve a la pestaña **Consola** .
   2. introduce:

      ```javascript
      ventana.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      La función regresa`undefined`.

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **Verifica que el modo de prueba esté habilitado:**
   * En la pestaña **Consola** , ingresa:  

     ```javascript
     ventana.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     El valor de retorno es `true`. Esto indica que el modo de prueba está activo.   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="Enviar eventos de prueba">

* En el modo de prueba, los eventos que envías se muestran en la página de integración de prueba.
* ¡Atención! Nota: Los eventos de prueba se procesan y posteriormente se incluirán en los reportes de la PBA. Para evitar distorsionar los reportes, completa `eventRevenue` con valores bajos (pequeños). Si no se envía ningún valor, PBA lo completa con 0.

Enviar eventos de ejemplo de cada uno de los tipos descritos.

| Paso | Acción<br /><br />(Ingrese comandos) | Página de integración de prueba del SDK web<br /><br />(Resultado esperado) |
| --- | --- | --- |
| 1 | Abre una nueva pestaña en el navegador y navega hasta cualquier página de tu sitio web. | PBA registra un `'pageLoad'` evento cada vez que tu sitio web se abre/actualiza:<br /><br />[<Image alt="PBATestingWebSDKPageLoadEvent_en-us.png" src="https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png" width="226px" />](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Inicia sesión o regístrate en tu sitio web como usuario <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">para activar un evento setCustomerUserId</Anchor>. | [<Image alt="mceclip3.png" src="https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png" width="226px" />](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Comienza a enviar eventos web</Anchor> para verificar que PBA los procese correctamente.<br /><br />**Nota:**<br /><br />Si no se especifica, `eventRevenue` y `eventRevenueCurrency` se rellenan con valores predeterminados:<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[<Image alt="PBAWebSDKTestEventEVENT_en-us.png" src="https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png" width="233px" />](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />Consulta <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Parámetros de eventos del SDK web para obtener detalles adicionales.</Anchor> | [<Image alt="mceclip5.png" src="https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png" width="226px" />](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

<div id="troubleshooting" />

## Resolución de problemas

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="Los eventos no se muestran en la página de prueba.">

1. En las herramientas de desarrollo del navegador, ve a **la**pestaña**Red** .
2. En el campo de filtro, ingresa "websdk".
3. Según el código de respuesta HTTP, procede de la siguiente manera:
   * 200: Comunícate con el soporte técnico de AppsFlyer.
   * 400: Comprueba que todos los parámetros estén encerrados en " ".

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=prueba-los-eventos-web-de-la-pba h_01HKW32BE04AKHFMY853211C1A=prueba-los-eventos-web-de-la-pba web-sdk-integration-test-page=p%C3%A1gina-de-prueba-de-integraci%C3%B3n-del-sdk-web h_01HKW32BE0Z2ZKTBHSCSWVT04N=p%C3%A1gina-de-prueba-de-integraci%C3%B3n-del-sdk-web procedures=procedimientos h_01HKW32BE0VA0X9ZX4Z26EY6CZ=procedimientos h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=resoluci%C3%B3n-de-problemas h_01HKW32BE1HFV0NM64QMASBCCT=resoluci%C3%B3n-de-problemas h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
