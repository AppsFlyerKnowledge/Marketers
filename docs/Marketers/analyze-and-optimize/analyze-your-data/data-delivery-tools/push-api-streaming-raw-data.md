---
title: "Transmisión\t de raw data de la Push API"
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-08-22T00:04:33Z'
  id: 207034356
  locale: es
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/es/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Transmite eventos de atribución de raw data a tus endpoints del lado del servidor.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## API Push

La Push API transmite el raw data generado por la atribución de AppsFlyer y la atribución de SKAdNetwork (SKAN) como mensajes a tus servidores. Puedes seleccionar los tipos y el contenido de los mensajes y establecer los endpoints de destino.

Los tipos de mensajes disponibles, la actualización de los datos y los campos dependen del framework de atribución (AppsFlyer o SKAN) como se describe en las secciones siguientes.

<div id="appsflyer-attribution-messages" />

<Accordion title="Mensajes de atribución de AppsFlyer">

Características del mensaje

| Características | Detalles |
| --- | --- |
| Segregación de tipos de mensajes | <ul><li>Los mensajes se pueden segregar por endpoint (máximo de 6 endpoint por aplicación) o puedes determinar el tipo de mensaje examinando el valor de los campos enumerados:<ul><li>nombre\_del\_evento</li><li>tipo\_de\_conversión</li><li>tipo\_campaña</li></ul></li><li>Los valores de los campos, por tipo de mensaje, se indican en la tabla a seguir.</li></ul>**Ejemplo:**<br /><br />Un mensaje contiene lo siguiente:<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Usa la tabla para determinar que este evento es el evento de instalación de un usuario orgánico. |
| Actualización de los datos | Los mensajes se envían poco después de que el evento se registra en la plataforma de AppsFlyer. Esto suele ser en cuestión de minutos. |
| Contenido del mensaje (campos) | <ul><li>Los mensajes tienen una estructura de `key:value`.</li><li>Consulta los campos de la <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> de atribución de AppsFlyer disponibles.</li><li>Cada clave representa un campo de raw data. Consulta la <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#data-fields-dictionary">descripción de los campos de raw data en AppsFlyer</Anchor>.</li><li>Las claves en blanco o nulas no se envían en absoluto.</li><li>El ejemplo contiene campos nulos y vacíos. Los postbacks reales no tienen campos vacíos ni nulos. El ejemplo proporcionado tiene un formato JSON.<ul><li>[apps de iOS,](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Formato de los campos de marca de tiempo | <ul><li>Marcas de tiempo UTC: `yyyy-mm-dd hh:mm:ss.sss`. Por ejemplo, se muestra como `2019-09-17 00:09:00.123`. Un evento tuvo lugar a las 18:00, hora de Tokio. La hora del evento se convierte a UTC, que es a las 09:00. La hora registrada es la de UTC.</li><li>Marcas de tiempo de la zona horaria seleccionada (específicas de la aplicación): `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Por ejemplo `2019-09-17 18:00:16.000+0900`. Un evento tuvo lugar a las 18:00, hora de Tokio. La hora del evento que se muestra se registra como 18:00+09:00. 09:00 es la zona horaria de Tokio.</li></ul> |

#### Tipos de mensajes disponibles

<table><thead><tr><th>Contexto de atribución</th><th>Tipo de mensaje</th><th>campo conversion_type</th><th>campo campaign_type</th><th>campo event_name</th><th>campo event_type</th></tr></thead><tbody><tr><td>Adquisición de usuarios</td><td>Instalación\*</td><td>instalar</td><td><p>No orgánico: UA</p><p>Orgánico: organic</p></td><td>instalar</td><td><ul><li>instalar</li><li>organic-install</li></ul></td></tr><tr><td>Adquisición de usuarios </td><td>Instalación de eventos in-app</td><td><span>instalar</span></td><td><p>No orgánico: UA</p><p>Orgánico: organic</p></td><td>Nombres de eventos definidos por el anunciante</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>Reorientación</td><td>Reengagement</td><td>re-engagement</td><td>redireccionamiento</td><td>re-engagement</td><td>Reatribución</td></tr><tr><td>Reorientación </td><td>Eventos in-app de recaptación</td><td>re-engagement</td><td>redireccionamiento</td><td>Nombres de eventos definidos por el anunciante</td><td>re-engagement-in-app-event</td></tr><tr><td>Reorientación </td><td>Re-atribución </td><td>Reinstalación</td><td>redireccionamiento</td><td>Reatribución</td><td>Reatribución</td></tr><tr><td>Adquisición de usuarios </td><td>Reinstalación</td><td>Reinstalación</td><td><p>No orgánico: UA</p><p>Orgánico: organic</p></td><td>Reinstalación</td><td><ul><li>Reinstalación</li><li>organic-reinstall</li></ul></td></tr><tr><td>Reorientación</td><td>Eventos in-app de reatribución</td><td>Reinstalación</td><td>redireccionamiento</td><td>Nombres de eventos definidos por el anunciante</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">\* Algunas instalaciones relacionadas con la atribución por impresiones se atribuyen a la <a href="./about-raw-data-identifier-restrictions" target="_blank">fuente de medios restringida.</a> </td></tr></tbody></table>

#### Campos exclusivos

<table><thead><tr><th>Nombre para mostrar</th><th>Nombre de la Push API</th></tr></thead><tbody><tr><td>Divisa seleccionada\*</td><td>selected_currency</td></tr><tr><td>Ingresos en la divisa seleccionada</td><td>ingresos en la<br/>moneda seleccionada</td></tr><tr><td>Costo en la divisa seleccionada</td><td>costo en la<br/>moneda seleccionada</td></tr><tr><td>Zona horaria seleccionada para la hora de descarga del dispositivo</td><td>device_download_time_selected_timezone</td></tr><tr><td>Zona horaria seleccionada para la hora de toque atribuido</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Zona horaria seleccionada para la hora de instalación</td><td>hora de instalación en la zona<br/>horaria seleccionada</td></tr><tr><td>Zona horaria seleccionada para la hora del evento</td><td>hora del evento en la zona<br/>horaria seleccionada</td></tr><tr><td>Zona horaria seleccionada(\*)</td><td>selected_timezone</td></tr><tr><td colspan="2">\* Esta es la configuración vigente a nivel de aplicación en el momento en que se envía el mensaje API.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Mensajes de atribución de SKAN">

Esta sección describe los mensajes (tipos de reportes) disponibles para SKAN y cómo identificar los mensajes. Lee esta sección y, a continuación, [Configura el endpoint de atribución de SKAN.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

Lectura relacionada: <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">Campos de raw data de SKAN</Anchor>. Los mensajes de la Push API tienen la estructura y los campos equivalentes.

Características del mensaje:

| Características | Detalles |
| --- | --- |
| Segregación de tipos de mensajes | <ul><li>Todos los mensajes se envían a un endpoint que has configurado.</li><li>Para determinar el tipo de mensaje, usa el campo event\_type.<br />Nota: con el campo event\_type, también puedes determinar el campo event\_name y el campo skad\_redownload.</li><li>Los valores del campo event\_type se indican en la [siguiente tabla](/docs/push-api-streaming-raw-data#tipos-de-mensajes-para-la-atribución-de-skan).</li></ul>Ejemplo:<br /><br />Un mensaje contiene lo siguiente:<ul><li>tipo de evento: skad-re-download</li></ul>A partir de esto, podemos determinar que:<ul><li>Este es un evento de redescarga</li><li>event\_name: install</li><li>skad\_redownload: true</li></ul> |
| Actualización de los datos | <ul><li>Instalaciones, redescarga y eventos in-app:<ul><li>Procesado a diario</li><li>Enviados a tu endpoint el día siguiente a la recepción del postback de iOS por parte de AppsFlyer</li><li>Seguramente recibirán mensajes de eventos de 08:00 a 11:00 UTC (la hora exacta varía)</li><li>Ejemplo: Los postbacks recibidos el lunes se envían a partir del martes a las 08:00 UTC</li></ul></li><li>Copia de postbacks de iOS y postbacks: Los mensajes se envían poco después de que llegan a AppsFlyer</li></ul> |
| Ejemplo de mensajes | La hoja de cálculo contiene ejemplos de mensajes. El ejemplo proporcionado tiene un formato JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Mensajes de ejemplo de SKAN</Anchor>. |

#### Tipos de mensajes para la atribución de SKAN

| Tipo de mensaje | campo event\_name | campo skad\_redownload | campo event\_type |
| --- | --- | --- | --- |
| Instalaciones | instalar | <ul><li>Valores posibles: false, blank, null.</li><li>Si el campo no está en el mensaje, considera el valor como false.</li></ul> | skad-install |
| Redescargas | instalar | Verdadero | skad-re-download |
| Eventos in-app | Nombre del evento configurado por el anunciante | Nombre del evento configurado por el anunciante | skad-in-app-event |
| Postbacks de iOS | Nunca disponible en este mensaje | A veces disponible | skad-postback |
| <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Copia de postbacks</Anchor> | Nunca disponible en este mensaje | A veces disponible | skad-postback-copy |

</Accordion>

## Configurar los endpoints de Push API

> ❗️ **Precaución**
>
> No uses la Push API para enviar datos atribuidos a AppsFlyer a terceros por los siguientes motivos:
>
> * Puedes infringir las normas de privacidad, como la CCPA, si el usuario eligió la exclusión opcional para no enviar sus datos a terceros.
> * Algunas fuentes de medios restringen la forma en que se utilizan, comparten con terceros o ambos los datos proporcionados por los usuarios. Asegúrate de cumplir con los términos de uso de la fuente de medios.
>   Por ejemplo, [X Ads,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/) [Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Nota:  Esta precaución no se aplica a los datos de SKAN. Usa la Push API para enviar datos SKAN a endpoints de terceros.

Para configurar la Push API, completa la lista de acciones.

#### Lista de verificación de configuración de la Push API

<table><thead><tr><th>Paso </th><th>Atribución de AppsFlyer</th><th>Atribución de SKAdNetwork </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>Si ya tienes un endpoint de la Push API activo, puedes omitir este paso. </p><p>Completa los <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">requisitos del lado del servidor</a>.</p></td></tr><tr><td>2</td><td>Para la atribución de AppsFlyer, planifica la configuración del endpoint con la <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">lista de verificación de planificación de la Push API.</a> </td><td>No aplicable</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Configura el endpoint de atribución de AppsFlyer</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Configura el endpoint de atribución de SKAdNetwork</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Requisitos del lado del servidor (tu servidor)">

Asegúrate de que tu servidor cumpla con los siguientes requisitos:

#### Requisitos del lado del servidor

| URL de endpoint | <ul><li>Nombre de dominio válido</li><li>Número máximo de endpoints únicos por aplicación:<ul><li>AppsFlyer: 6 puntos de conexión</li><li>SKAdNetwork: 3 puntos de conexión</li></ul></li></ul> |
| --- | --- |
| Código de respuesta del endpoint | Al recibir un mensaje, tu endpoint debe devolver un código de estado HTTP 200. |
| Agregar los servidores de AppsFlyer a la lista de permitidos | Agrega a la lista de permitidos las <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">direcciones IP</Anchor> de los servidores de AppsFlyer en tus firewalls y sistemas de seguridad para garantizar la comunicación con el endpoint. |
| Versiones del TLS | <ul><li>TLS 1.1</li><li>TLS 1.2+ Ver <Anchor target="_blank" href="/marketers/es/docs/appsflyer-https-ssl-encryption-policy-support#mensajes-salientes-appsflyer-como-cliente">cifras admitidas</Anchor></li></ul> |
| Puertos | Puertos: 80, 443 |

[Práctica recomendada]: ¡**Importante**! Se utiliza un mecanismo de tiempo de espera que tiene una duración de 4 segundos. Si AppsFlyer no recibe un mensaje de OK durante este tiempo, AppsFlyer lo considera como un error en el envío del mensaje.

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Lista de verificación de planificación de la Push API para la atribución de AppsFlyer">

* Usa esa lista de verificación para planificar la configuración de tus endpoints de atribución de AppsFlyer. Los números en la figura coinciden con los números de fila en la lista de verificación.
* Esta sección no es relevante para la atribución de SKAdNetwork. Consulta [Configurar la atribución de SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Punto final**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

#### Tabla de planificación de los endpoints

| N.º | Configuración | Detalles | Usa esta columna para registrar la configuración planificada |
| --- | --- | --- | --- |
| 1 | Método | POST o GET |  |
| 2 | URL de endpoint | - |  |
| 3 | Tipos de mensajes de evento | <ul><li>Selecciona al menos un tipo de mensaje de evento.</li><li>Para seleccionar mensajes de eventos in-app, debes atribuir un evento in-app. Si no lo haces, no podrás seleccionar mensajes de eventos in-app.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Campos</li><li>La lista de campos es común para todos los tipos de mensajes.</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>Advertencia**<br />Seleccionar todo no incluye automáticamente los campos de mensaje que se añadan en el futuro. Para incluir campos nuevos, debes actualizar la selección manualmente.<br /><br /><br /><br />Selecciona los campos requeridos.<ul><li>Los campos más comunes ya están seleccionados de forma predeterminada.</li><li>No enviamos campos vacíos o nulos</li></ul> |  |
| 5 | Tipo de eventos in-app | Filtra por eventos in-app para reducir el tráfico enviado a tu endpoint.<ul><li>Selecciona uno o más, o todos los eventos in-app. ¡Atención! ¡Nota! Si el evento no aparece en la lista, búscalo.</li><li>Solo puedes seleccionar un evento in-app después de que se haya atribuido al menos una vez. Si es necesario, usa <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> para disparar el evento.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Configura el endpoint de atribución de AppsFlyer">

**Nota:** Solo el [propietario de la cuenta](/docs/push-api-streaming-raw-data#specifications-and-limitations) de AppsFlyer puede realizar cambios en la configuración de la Push API. Los demás usuarios de la cuenta pueden ver la configuración.

#### Para agregar un endpoint de atribución de AppsFlyer:

1. Ve a **Reporte > Acceso a la API.** Desplázate hacia abajo hasta la sección Push API.
2. Haz clic en **Agregar endpoint.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
3. Selecciona un método HTTP: **POST** o **GET**
4. Ingresa la **URL del endpoint**. Si recibes el mensaje de que esta URL no es segura, contacta con el soporte técnico de AppsFlyer.
5. Selecciona uno o más tipos de eventos. **Nota**: Si los mensajes de eventos in-app están deshabilitados, significa que no se han atribuido eventos in-app hasta el momento.
6. Selecciona los campos para completar el mensaje de la Push API. Nota:
   * Los campos obligatorios siempre se envían: Estos son: ID de la aplicación, nombre del evento, hora del evento, IDFA para iOS o ID de publicidad para Android.
   * Usa los controles representados en la figura a continuación para seleccionar campos opcionales. [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * Los campos más comunes ya están seleccionados de forma predeterminada. Puedes cancelar las selecciones.
     * Selecciona campos opcionales según sea necesario.
     * Usa **Borrar todo** para desactivar todos los campos opcionales seleccionados.
     * No enviamos campos nulos o vacíos y la clave asociada. Ten esto en cuenta al planificar tus procedimientos de análisis/importación.
7. Selecciona uno o más (hasta 52 eventos) o **Todos** los eventos in-app.
   * La lista se completa por tipos de eventos que ya se han atribuido. Si falta un evento, envía un evento que contenga este tipo utilizando un dispositivo de prueba.
8. Haz clic en **Guardar**.  
   La Push API ahora está activa. Los datos se envían al endpoint.
9. Prueba el endpoint utilizando el procedimiento que sigue.

#### Para probar el endpoint:

1. Haz clic en **Enviar prueba.**   
   Aparece un mensaje de resultado de la prueba debajo del botón **Enviar prueba**.   
   Se envía un mensaje de prueba al endpoint. Si la prueba falla, asegúrate de que <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">las direcciones IP de AppsFlyer estén en la lista de permitidos</Anchor>.   
   ¡Nota! Esto solo estará disponible para:
   * Aplicaciones guardadas previamente en modo SKAN 4 en el estudio de conversión.   
     ¡**Importante**! Se utiliza un mecanismo de tiempo de espera que tiene una duración de 2 segundos. Si AppsFlyer no recibe un mensaje de OK durante este tiempo, AppsFlyer lo considera como un error en el envío del mensaje.
   * Comprueba que tu endpoint recibió el mensaje de prueba.  
     [Ver una copia del mensaje enviado.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Configura el endpoint de atribución de SKAdNetwork">

**Nota:** Solo el [propietario de la cuenta](/docs/push-api-streaming-raw-data#specifications-and-limitations) de AppsFlyer puede realizar cambios en la configuración de la Push API. Los demás usuarios de la cuenta pueden ver la configuración.

**Para agregar un endpoint de la Push API de SKAdNetwork:**

1. Ve a **Reporte > Acceso a la API. Ve a** Reporte > Acceso a la API **Desplázate hacia abajo hasta la sección Push API.**
2. Selecciona **SKAdNetwork** como entidad atribuidora.
3. Haz clic en **Agregar endpoint.**   
   **Nota**: Puedes definir de 1 a 3 endpoint de SKAdNetwork por aplicación.
4. Selecciona un método HTTP: **POST** o **GET**
5. Ingresa la **URL** del **endpoint**. Si recibes el mensaje de que esta URL no es segura, contacta con el soporte técnico de AppsFlyer.
6. No enviamos campos nulos o vacíos y la clave asociada. Ten esto en cuenta al planificar tus procedimientos de análisis/importación.
7. Haz clic en **Guardar**.  
   La Push API ahora está activa. Los datos de conversión continúan enviándose al endpoint.

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="Configurar el token de autenticación">

Con el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">token de autenticación</Anchor> de la Push API, los clientes pueden integrar y proteger sin problemas sus mensajes de la Push API agregando un encabezado de autorización personalizable con un token solicitado.  
Puedes personalizar un encabezado de autorización que se enviará con tus mensajes de la Push API, definiendo el nombre del token y el valor asociados con cada ID de aplicación. Esto garantiza que tus mensajes no solo sean seguros, sino que también se adapten a tus requisitos específicos.

</Accordion>

## Procedimientos adicionales: gestión de endpoints

**Nota:** Solo el [propietario de la cuenta](/docs/push-api-streaming-raw-data#specifications-and-limitations) de AppsFlyer puede realizar cambios en la configuración de la Push API. Los demás usuarios de la cuenta pueden ver la configuración.

<div id="change-an-endpoint" />

<Accordion title="Cambiar un endpoint">

**Para modificar la configuración del endpoint:**

1. Ve a **Reporte > Acceso a la API. Ve a** Reporte > Acceso a la API **Desplázate hacia abajo hasta la sección Push API.**
2. Localiza el endpoint a modificar.
3. Haz las modificaciones.
4. Haz clic en **Guardar**.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Eliminar un endpoint">

**Para eliminar un endpoint**:

1. Ve a **Reporte > Acceso a la API. Ve a** Reporte > Acceso a la API **Desplázate hacia abajo hasta la sección Acceso a la Push API.**
2. Haz clic en **Eliminar endpoint**.
3. Haz clic en **Guardar**.  
   Se elimina el endpoint.

</Accordion>

## Solución de problemas, rasgos y limitaciones

<div id="test-message-fails" />

<Accordion title="Fallo del mensaje de prueba">

Si no recibes el mensaje de prueba y restringes el acceso a tus servidores por dirección IP: asegúrate de que <Anchor target="_blank" href="/marketers/es/docs/appsflyer-server-ip-address-ranges-allowlisting">todas las direcciones IP de AppsFlyer estén en la lista de permitidos</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Duplicar eventos in-app de retargeting">

Los eventos in-app de retargeting se duplican cuando se lleva a cabo un evento de compra como parte de una campaña de retargeting durante la ventana de re-engagement de la UA. Esto se hace para atribuir ingresos tanto a la fuente de medios de la UA como a la fuente de medios de retargeting.

Solo obtendrás un evento duplicado si has habilitado ambos:

* Instalación de eventos in-app
* Eventos de retargeting en la aplicación

<Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">Identificar y deduplicar eventos in-app</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="La selección de mensajes de eventos in-app está deshabilitada">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* Los mensajes de eventos in-app solo se pueden seleccionar después de que se haya atribuido un evento in-app.
* Usa un dispositivo de prueba para generar un evento in-app o usa la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor> para hacerlo manualmente.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Faltan mensajes push y CloudFront">

¿Estás utilizando Amazon CloudFront como endpoint? Si es así, verifica si CloudFront está rechazando el mensaje con el código de rechazo 421. Si este es el caso, consulta <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Elegir cómo CloudFront atiende las solicitudes HTTPS</Anchor>

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Mensajes de error del endpoint">

**Síntoma:** El mensaje *esta URL no es segura* aparece cuando configuras la URL del endpoint.

**Acción requerida**: Contacta con el soporte técnico de AppsFlyer; incluye el ID de aplicación, la URL del endpoint y una captura de pantalla del mensaje de error.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| **Caducado** | Observaciones |
| --- | --- |
| <span id="ad-networks"></span>Redes publicitarias | No disponible |
| <span id="agencies"></span>Agencias | No disponible |
| <span id="appspecific-time-zone"></span>Zona horaria específica de la aplicación | Compatible |
| <span id="appspecific-currency"></span>Moneda específica de la aplicación | Compatible |
| <span id="size-limitations"></span>Limitaciones de tamaño | No aplicable |
| <span id="organic"></span>Orgánico | Sí |
| <span id="nonorganic"></span>No orgánico | Sí |
| <span id="data-freshness"></span>Actualización de los datos | Continuo |
| <span id="historical-data"></span>Datos históricos | No admitido. Si faltan datos, utiliza la Pull API para obtener los datos. En el caso de SKAN, puedes obtener algunos datos históricos a través de Data Locker (limitado por la ventana de disponibilidad de Data Locker). |
| <span id="account-owneruser-access"></span>Acceso del propietario/usuario de la cuenta | Solo el **propietario de la cuenta** de AppsFlyer puede realizar cambios en la configuración de la Push API.<ul><li>Cada cuenta de AppsFlyer tiene **solo un** propietario de cuenta. Este es el primer usuario de AppsFlyer (creado en el momento de abrir la cuenta).</li></ul>Los demás usuarios de la cuenta pueden ver la configuración de la Push API, pero no pueden realizar cambios. |
| <span id="authentication-token-in-test-messages"></span>Token de autenticación en mensajes de prueba | Los encabezados de los [mensajes de prueba](#para-probar-el-endpoint) no incluyen el token de autenticación. |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="¿Puedo incluir encabezados personalizados con la solicitud de Push API?">

N.º La Push API admite el uso del encabezado `Authorization` solo para tokens de autenticación. **No** se admiten encabezados personalizados adicionales, como `consumer-key`.

Si necesitas pasar parámetros adicionales, inclúyelos en la URL. Por ejemplo:

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Comparación de herramientas de entrega de raw data</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Configuración de la Push API usando una API</Anchor>

<div data-zendesk-anchors="push-api=api-push 01H89PJFBPXVKJGGH18CJBJ41W=api-push 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=tipos-de-mensajes-disponibles 01H89PJFBP9DEX520BDGC5PANQ=tipos-de-mensajes-disponibles unique-fields=campos-exclusivos 01H89PJFBPBK09Q7CRPMM4G7PJ=campos-exclusivos 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=tipos-de-mensajes-para-la-atribuci%C3%B3n-de-skan 01H89PJFBQBFCK5QVWW2X09H28=tipos-de-mensajes-para-la-atribuci%C3%B3n-de-skan set-up-push-api-endpoints=configurar-los-endpoints-de-push-api 01H89PJFBQZ2FW3ST5V4FW91GS=configurar-los-endpoints-de-push-api 01H89PJFBQ6WP7ERP0DJ69QZ1G=precauci%C3%B3n push-api-setup-checklist=lista-de-verificaci%C3%B3n-de-configuraci%C3%B3n-de-la-push-api 01H89PJFBQ625A7G3QT5HQJXMW=lista-de-verificaci%C3%B3n-de-configuraci%C3%B3n-de-la-push-api 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=requisitos-del-lado-del-servidor 01H89PJFBQ2BC5GHX403RD2RAT=requisitos-del-lado-del-servidor 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=tabla-de-planificaci%C3%B3n-de-los-endpoints 01H89PJFBQJXWWPQDKZ387VYX3=tabla-de-planificaci%C3%B3n-de-los-endpoints 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=para-agregar-un-endpoint-de-atribuci%C3%B3n-de-appsflyer h_01JFSS65G8GTZNMY257QCV922M=para-agregar-un-endpoint-de-atribuci%C3%B3n-de-appsflyer test-the-endopoint=para-probar-el-endpoint h_01JFSS6YVP1WFWXSZ7HP7GTDA2=para-probar-el-endpoint 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=procedimientos-adicionales-gesti%C3%B3n-de-endpoints 01H89PJFBQ7WV3NM7JR5Z9QEFB=procedimientos-adicionales-gesti%C3%B3n-de-endpoints 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones 01H89PJFBQJDGT1FVHKG9DETHJ=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=consulta-tambi%C3%A9n" />
