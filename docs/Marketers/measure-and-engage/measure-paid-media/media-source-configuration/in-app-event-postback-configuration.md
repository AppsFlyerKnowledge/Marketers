---
title: Configuración de postback de eventos in-app
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-09-29T00:13:44Z'
  id: 208439256
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/208439256
---
> **En resumen:** Mide el engagement en la app y la calidad de tus usuarios, optimizando las campañas con datos de eventos internos.

## Visión general

Los eventos in-app permiten a los marketers evaluar el engagement en la app y la calidad de usuarios de diversas fuentes y desarrollar estrategias de adquisición efectivas. Las ad networks aprovechan la información de eventos in-app para optimizar y realizar campañas de costo por acción/evento. Las ad networks reciben datos de eventos in-app mediante postbacks, que se envían en tiempo real. <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">Descubre más sobre eventos enriquecidos in-app</Anchor>.

## Selección de eventos in-app para postbacks

Los marketers pueden seleccionar qué eventos in-app quieren enviar como postbacks a las ad networks mediante la configuración descrita en este artículo.

> 📘 **Nota**
>
> * Entre los eventos in-app se incluyen **eventos rechazados**, como aquellos bloqueados por Protect360 o que no cumplen con las normas de validación de objetivos.
> * Si la sección **Postbacks de eventos in-app** no aparece en la pestaña **Integración**, significa que el partner aún no ha configurado el registro de eventos in-app con AppsFlyer durante su configuración preliminar. El partner puede contactar con AppsFlyer a través del <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget del asistente de partner</Anchor> para completar la integración.

## Ventana de postback de eventos in-app

La ventana de postback de eventos in-app permite a los marketers que trabajan con redes en un modelo CPA (costo por acción) configurar periodos post-conversión tras los cuales no se envían más postbacks.

Por ejemplo, si los eventos dentro de 15 días de una instalación implican un costo, configura la ventana de esta manera:

<Image alt="Ventana de postback de eventos in-app configurada en 15 días" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

Los postbacks posteriores a este período no se envían y no se notifica a la red, pero AppsFlyer sigue registrando los eventos y atribuyéndolos a la red.

Los postbacks se envían siempre según la configuración **actual** de la ventana. Consulta el siguiente ejemplo:

| 1 de enero | La ventana es de 15 días.<br /><br />Un usuario instala una app. |
| --- | --- |
| 2 de enero | La ventana se cambia a 10 días. |
| 14 de enero | El usuario realiza una compra.<br /><br />El postback no se envía a la ad network porque el evento no se encuentra dentro de la ventana actual (10 días). |
| 15 de enero | La ventana se cambia a 20 días. |
| 18 de enero | El usuario realiza otra compra.<br /><br />Esta vez se envía el postback, porque el evento se encuentra dentro de la ventana actual (20 días). |

> 📘 **Nota**
>
> Cuando seleccionas la opción [**Todas las fuentes de medios, incluidas las orgánicas**](#opciones-para-enviar-postbacks), el partner que la configuró recibe un postback por cada evento de conversión que recibe el anunciante. Esto ocurre incluso si el anunciante atribuyó el evento a otro partner, siempre que el evento se produjera dentro de la ventana de postback que AppsFlyer define para el partner que configuró la opción.

### Ventana de postback predeterminada

Al empezar a configurar postbacks de eventos in-app, la ventana predeterminada se establece automáticamente en seis meses.

> 📘 **Nota**
>
> Si empezaste a usar postbacks de eventos in-app con un partner específico antes del 30 de julio de 2019, la ventana predeterminada es Tiempo de vida. Esto significa que los postbacks de eventos in-app siempre se envían.

### ¿Quién puede configurar ventanas de postback?

Los siguientes roles pueden configurar ventanas de postback:

* Marketers
* Agencias, si se les conceden los **permisos para configurar postbacks de eventos in-app** <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">correspondientes</Anchor>.  
  **Nota:** Un marketer y una agencia que trabajen con la misma ad network pueden configurar las ventanas de postback por separado, según sus contratos con la red.
* Partners, si se les conceden los **permisos para configurar postbacks de eventos in-app** <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">correspondientes</Anchor>.

## Mapeo de eventos

Cada marketer puede asignar un nombre diferente a un evento del mismo tipo. Dichos nombres de eventos también pueden diferir de los nombres de los partners.

Por ejemplo, cuando un usuario adquiere algo a través de una aplicación, un marketer puede llamarlo `compra`, o usar un ID menos informativo, como `evento5`, y un partner podría llamarlo `purchase_event`.

Para asegurarse de que los eventos del marketer coincidan con los mismos eventos que los de los partners, los nombres de los eventos deben mapearse.

> 📘 **Nota**
>
> Los eventos mapeados en la pestaña Integración para un partner específico se aplican tanto a los postbacks estándar como a los <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postbacks de SKAdNetwork (SKAN)</Anchor>

### Métodos de mapeo

Cada postback decide cuál de los siguientes métodos se usará para mapear sus eventos in-app:

* [Introducir el ID del evento del partner](/docs/in-app-event-postback-configuration#enter-the-partner-event-id)
* [Seleccionar el ID del evento de la lista](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Enviar eventos tal cual están (no mapeados)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

> 📘 **Nota**
>
> * No todos los métodos de mapeo aparecen para todos los partners.
> * Puedes [darle permiso al partner](/docs/in-app-event-postback-configuration#mapeo-de-eventos-por-ad-networks) para que realice el mapeo él mismo.

<Accordion title="Introducir el ID del evento del partner">

* **Evento de AppsFlyer**: De la lista de eventos in-app, selecciona un evento.
* **asignado al evento del partner**: en el campo de texto, introduce el ID del evento recibido del partner, que corresponde al evento de tu aplicación (evento de AppsFlyer)

> 📘 **Nota:**
>
> * Los nombres de los eventos distinguen entre mayúsculas y minúsculas. Para evitar discrepancias, asegúrate de utilizar el nombre de evento correcto para todas las fuentes de medios y versiones de la aplicación.
> * Al escribir el nombre de un evento, puedes emplear guiones bajos antes o después del nombre del evento. Asegúrate de usar guiones bajos solo cuando el nombre del evento enviado desde AppsFlyer tenga exactamente los mismos guiones.

![Introducir un ID de evento en el campo de texto asignado al evento del partner](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)

</Accordion>

<Accordion title="Selecciona un ID de evento de la lista">

* **Evento de AppsFlyer**: En la lista de eventos de tu aplicación, selecciona un evento.
* **Asignado al evento del partner**: En la lista de eventos predefinidos del partner, selecciona el evento que corresponde al evento de tu aplicación (evento de AppsFlyer).

![Selección de un evento predefinido del partner en la lista desplegable de ID del evento](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

</Accordion>

<Accordion title="Enviar eventos tal y como están (sin mapear)">

Algunos partners prefieren recibir postbacks de eventos in-app sin asignar, lo que significa que los nombres de los eventos se envían tal como se denominan en tu aplicación. No importa si el evento se llama `compra`, `adquisición` o `evento5`.

Puedes elegir qué eventos no mapeados enviar al partner:

* **Agregar manualmente:** Selecciona eventos específicos.
* **Enviar todos los eventos (excluye desinstalaciones y sesiones)**. Esto no incluye desinstalaciones, sesiones (inicios de aplicación) ni el evento `af_app_opened`.

> 📘 **Nota:**
>
> Para evitar que los anunciantes compartan demasiada información de forma involuntaria con plataformas de análisis de terceros, hemos eliminado la opción **Enviar todos los eventos (excluye desinstalaciones y sesiones)** para estas plataformas desde marzo de 2019. Las plataformas de análisis configuradas antes de esta fecha aún mantienen esta opción.

**Para agregar eventos manualmente:**

1. Haz clic en **Agregar evento**.
2. Elige las opciones de postback:
   * **Evento de AppsFlyer**: De la lista de eventos de tu aplicación, selecciona un evento.
   * **para usuarios de**: Selecciona la [opción de envío](/docs/in-app-event-postback-configuration#opciones-para-enviar-postbacks) para el evento.
   * **incluyendo**: Selecciona [qué datos incluir](/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks) en el postback.
3. Repite este procedimiento para más eventos.

![Adición manual de eventos sin mapear con opciones de envío y de inclusión de datos](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**Para enviar todos los eventos:**

1. Selecciona **Enviar todos los eventos (excluye desinstalaciones y sesiones)**.
2. Elige las opciones de postback:  
   * **para usuarios de**: Selecciona la [opción de envío](/docs/in-app-event-postback-configuration#opciones-para-enviar-postbacks) para todos los eventos.
   * **incluyendo**: Selecciona [qué datos incluir](/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks) para todos los eventos en el postback.

![Envío de todos los eventos sin mapear sin asignación individual de eventos](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

Para más información sobre el mapeo de eventos, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>.

### Opciones para enviar postbacks

Para cada evento, puedes elegir en qué casos enviar los postbacks (dentro de la ventana de postback):

* **Solo este partner**: Envía postbacks solo cuando el evento se atribuya a este partner, es decir, cuando el usuario que lo realizó provenga de este partner.
* **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks a todas las fuentes de medios para los eventos atribuidos a cualquier partner y para los eventos orgánicos, es decir, cuando el usuario que lo realizó provenga de cualquier fuente de medios. **Nota**: Cuando se selecciona **Todas las fuentes de medios, incluidas las orgánicas**, los postbacks de otros partners no contienen datos de atribución.

### Datos a incluir en los postbacks

Puedes elegir qué tipo de datos de eventos compartir con el partner en el postback. Selecciona una de las siguientes opciones:

* **Sin valores y sin ingresos**: Envía solo el evento en sí, sin ningún parámetro (valores o ingresos).
* **Valores y sin ingresos**: Envía todos los parámetros **excluyendo** el valor de los ingresos.
* **Valores e ingresos**: Envía todos los parámetros del evento, **incluyendo** el valor de los ingresos (si existe en el evento).
* **Valores, ingresos & ingresos netos**: Envía todos los parámetros del evento, incluidos los valores de ingresos e ingresos netos (si existen en el evento).

> 📘 **Nota:**
>
> La opción **Valores, ingresos & ingresos netos** requiere una suscripción a **ROI360 Advanced** y solo está disponible para los eventos `af_purchase*` y `af_ars_*`.

Se recomienda compartir los ingresos si deseas que las ad networks optimicen tus campañas y mejoren tus resultados. Sin embargo, compartir los ingresos no es obligatorio. Asegúrate de habilitar la distribución de ingresos solo para eventos que tengan `af_revenue` o `af_projected_revenue` definidos en su valor de evento. De lo contrario, las ad networks recibirán eventos sin valor de ingresos.

#### Compartir ingresos

En los postbacks, `af_revenue` y `af_currency` se escriben fuera del event\_value JSON como **monetary** y **currency** y pueden enviarse por separado. Ejemplo de estructura del postback: `https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)`

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

Cuando se selecciona la opción **Valores, ingresos & ingresos netos**, `af_net_revenue` también puede escribirse fuera del JSON de `event_value` como **net-monetary** y enviarse por separado. Ejemplo de estructura del postback: `https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)`

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

> 📘 **Nota:**
>
> Al elegir las opciones con **Sin valores y sin ingresos** o **Con valores y sin ingresos**, los parámetros respectivos se enmascaran con N/A.

> 👍 **Consejo**
>
> También puedes configurar los postbacks de eventos in-app para enviar ingresos netos en lugar de ingresos brutos en el parámetro estándar de ingresos (monetary). Para obtener acceso a esta configuración, ponte en contacto con tu Customer Success Manager (CSM).

<span id="h_01HBZCRNKGBEDSBZEY87KYQ60G"></span>**Ejemplo**

Un marketer envía un evento de compra con el siguiente valor del evento:  
`{"af_currency":"USD","af_content_id":"1234567",  "af_revenue":50.87,"af_content_type":"category_a"}`

```json
Vista general
```

La tabla a continuación muestra cómo se envían los parámetros:

| Nombre del campo | event\_value | monetario | moneda | net-monetary |
| --- | --- | --- | --- | --- |
| **Sin valores y sin ingresos** | N/D | No aplica | No aplica | No aplica |
| **Con valores y sin ingresos** | `{"af_currency":"N/A","af_content_id":"1234567", "af_revenue":"N/A","af_content_type":"category_a"} &monetary=N/A&content_id=1234567` | N/D | No aplica | No aplica |
| **Nota** | `{"af_currency":"USD","af_content_id":"1234567", "af_revenue":50.87,"af_content_type":"category_a"} &monetary=1.856918&content_id=1234567` | 50.87 | USD (Dólar estadounidense) | N/D |
| **Con valores y con ingresos** | `Nota` | 50.87 | USD (Dólar estadounidense) | 35.61 |

### Postbacks condicionales de eventos in-app

Filtra los postbacks de eventos in-app utilizando múltiples condiciones que pueden asignarse a diferentes eventos. Solo se envían a los partners los eventos que cumplen las condiciones del filtro, incluidas las self-reporting networks (SRN) y los partners de análisis. Utiliza esta función para:

* Optimizar la segmentación, personalización y retención de usuarios
* Minimizar datos
* Proteger la privacidad del usuario

<span id="h_01HBZCRNKHRTMHP3JPFVCS8D6N"></span>**Ejemplo**

Un marketer con una aplicación de juegos quiere optimizar campañas que se ejecutan a través de una ad network, pero solo para los usuarios que superen el nivel 10 o el nivel 50, o para los usuarios que gasten $3 en compras in-app.

![Ejemplo de condiciones de postback de eventos in-app para alcanzar el nivel 10, el nivel 50 o una compra de $3](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

**Así se establecen las condiciones para este evento:**

* Nota
* Nota
* Cuando el ***costo*** es igual a ***3***, se asigna a *`fb_mobile_purchase`*.

**Para establecer condiciones para un evento:**

1. En la página de integración con el partner, <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">define y asigna</Anchor> los eventos in-app necesarios para enviar al partner.
2. Haz clic en el icono![Add condition icon](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) Añadir condición del evento requerido.
3. Introduce los campos de condición, tal como aparecen en el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#event-values">valor del evento</Anchor>:
   * Nombre de la propiedad
   * Valor
   * Evento asociado para asignar la condición (utilizando cualquiera de estas [opciones de mapeo](/docs/in-app-event-postback-configuration#métodos-de-mapeo))
4. Puedes añadir más condiciones, pero asegúrate de haber introducido primero todos los campos de la condición existente.
5. Haz clic en **Guardar integración**.

#### Consideraciones

Al configurar las condiciones, asegúrate de que se cumplan las siguientes consideraciones para que el evento se envíe al partner:

<Accordion title="Estructura de la condición">

* Tanto la propiedad como el valor de la condición deben coincidir con los datos del evento.
* Actualmente, solo se pueden establecer condiciones como “iguales”.
* No se admiten estructuras complejas como matrices.

</Accordion>

<Accordion title="Múltiples condiciones para un evento">

* El número máximo de condiciones por evento es 5.
* Se debe cumplir al menos una condición para que se envíe el postback, pero solo se ejecuta una.
* Cada condición se comprueba por orden de aparición, y la primera condición que se cumple es la que se ejecuta.
* Cada condición se asigna por separado. El nombre del evento del partner se cambia a **Según condiciones**.
* Más de una condición puede tener la misma propiedad o el mismo valor, pero no pueden compartir ambos.
* Se puede asignar más de una condición al mismo evento.

</Accordion>

> 📘 **Nota:**
>
> * Es recomendable probar esta función con una aplicación de prueba o para eventos menores para evaluar su impacto en la optimización de campañas.
> * Para ver el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">contenido del postback</Anchor>, puedes descargar el reporte de postback de raw data.

### Editar múltiples eventos

Durante la asignación de eventos, los valores de los campos **para usuarios de** e **incluyendo** se pueden editar en varios eventos con una sola acción.

**Para editar varios eventos:**

1. Selecciona los eventos a actualizar.
2. Haz clic en **Acciones masivas.**
3. Selecciona la nueva configuración que se aplicará a todos los eventos seleccionados:
   * **para usuarios de** (elige solo una opción)
     * Solo este partner
     * Todas las fuentes de medios, incluidas las orgánicas.
   * **incluyendo** (elige solo una opción)
     * Sin datos (predeterminado)
     * Valores sin ingresos
     * Valores e ingresos

![Panel de acciones masivas para editar la configuración de "para usuarios desde" e "incluyendo" en varios eventos](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)

### Eventos personalizados

La lista de eventos disponibles para asignar muestra solo los eventos ya informados por el SDK o desde eventos enviados de servidor a servidor hacia AppsFlyer. Si el evento que quieres asignar no aparece en la lista desplegable, puede deberse a alguna de las siguientes razones:

* Aún no hay ningún usuario que haya realizado el evento
* La última vez que ocurrió el evento fue hace más de dos semanas.
* Tienes una gran cantidad de eventos activos

**En cualquiera de estos casos, para asignar el evento al ID de partner:**

1. En la lista desplegable, haz clic en **+ Añadir elemento**.
2. En el cuadro de texto, introduce el nombre del evento que deseas añadir.
3. Haz clic en la marca de verificación para confirmar. El evento que has añadido ahora aparece en la lista y puedes seleccionarlo. ![Confirmación de un nuevo nombre de evento personalizado](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. Asocia el evento con el identificador del partner.
5. Haz clic en **Guardar integración** para asegurarte de que se registre el mapeo.

> 📘 **Nota:**
>
> * Agregar eventos personalizados en la página de postback no los extrae automáticamente de tu aplicación. Los eventos deben configurarse en el SDK o S2S para que funcionen correctamente. Consulta <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#envío-de-eventos">cómo enviar eventos a AppsFlyer</Anchor>.
> * Cuando se añade un evento personalizado en un partner específico, se añade a la lista de eventos de todos los partners, por lo que puedes verlo en la lista desplegable de eventos de cualquier partner.
> * Consulta los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#tips">consejos</Anchor> y las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#limitations">limitaciones</Anchor> para definir nombres y parámetros de eventos.

**Agencias y ad networks:**

* No pueden añadir eventos personalizados
* Solo puedes ver y/o mapear eventos después de que el especialista en marketing haya añadido el evento y concedido los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos</Anchor> necesarios.

## Mapeo de eventos por ad networks

Los marketers pueden permitir que las ad networks mapeen los eventos y deshabiliten los postbacks por sí mismos. Para ello, un especialista en marketing debe otorgar los permisos pertinentes a la ad network:

1. En la página **Integraciones activas**, busca el partner al que quieras dar permiso.
2. En la pestaña de Permisos, cambia el interruptor **Permitir configurar postbacks de eventos in-app** a **ACTIVADO**.

![Permitir configurar el interruptor de permisos de postbacks de eventos in-app para una ad network](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

Una vez que la ad network haya recibido los permisos, podrá mapear los eventos siguiendo las instrucciones de la [Introducir el ID del evento en el campo de texto](#métodos-de-mapeo).

## Mapeo de eventos por agencias

Los marketers pueden permitir que las agencias configuren postbacks de eventos in-app.

> 📘 **Nota:**
>
> Si tanto el anunciante como la agencia habilitan el mismo postback de evento in-app a la misma ad network, AppsFlyer envía el postback solo una vez. Esto evita la duplicación de reportes del evento.

**Para otorgar a la agencia permiso para configurar postbacks in-app:**

1. Encuentra la agencia en la página **Integraciones activas**.
2. Selecciona si la agencia puede compartir todos los eventos o solo aquellos atribuidos a la ad network específica.
3. Selecciona si la agencia puede enviar ingresos por eventos.
4. Selecciona los eventos específicos que la agencia puede compartir.

![Configuración de permisos para compartir eventos e ingresos de la agencia](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

<span id="h_01HDP3XHBPA5GZEVERMBN43JH0"></span>**Consulta también**

* <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">Vista general de los eventos enriquecidos in-app</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">Estructura de eventos enriquecidos in-app</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HE0FQ1AB6NQCTKFTDW22SRYC=visi%C3%B3n-general postback-inapp-event-selection=selecci%C3%B3n-de-eventos-in-app-para-postbacks h_01HBZCRNKGH1PAK8RC846PPRTS=selecci%C3%B3n-de-eventos-in-app-para-postbacks h_01HBZCRNKGQTJ4VJ00TVTS14N2=nota inapp-event-postback-window=ventana-de-postback-de-eventos-in-app h_01HBZCRNKGS71QGK5506N07K84=ventana-de-postback-de-eventos-in-app h_01K9MBNYC6PPHXSZ3KNVNSDASJ=nota-1 default-postback-window=ventana-de-postback-predeterminada h_01HBZCRNKGV5CREN5K0RBDMBH6=ventana-de-postback-predeterminada h_01HBZCRNKGVXN233AFFHG42NW9=nota-2 who-can-configure-postback-windows=qui%C3%A9n-puede-configurar-ventanas-de-postback h_01HBZCRNKG7AECFSBXV2WDD9AR=qui%C3%A9n-puede-configurar-ventanas-de-postback event-mapping=mapeo-de-eventos h_01HBZCRNKG7SZ4T41BY60BAJZN=mapeo-de-eventos h_01HBZCRNKGT64TE2XYK9VS4ATD=nota-3 mapping-methods=m%C3%A9todos-de-mapeo h_01HBZCRNKG4EF9MSY696SD5VQ9=m%C3%A9todos-de-mapeo h_01HBZCVAGPSNDJMWRWENEP45N7=nota-4 h_01HBZCRNKG1E63DZRSDWTB8CJN=nota-5 h_01HBZCRNKGXJ683VHFTE277ER9=nota-6 options-for-sending-postbacks=opciones-para-enviar-postbacks h_01HBZCRNKG1VN7E6TVCPDW7M73=opciones-para-enviar-postbacks data-to-include-in-the-postbacks=datos-a-incluir-en-los-postbacks h_01HBZCRNKGESY50NSZGTVPT25M=datos-a-incluir-en-los-postbacks h_01KRKDVVV246YZYGM5G2ZJR63W=nota-7 sharing-revenue=compartir-ingresos 01J9Y0T400M5Z62Q9CKF8M75WR=compartir-ingresos h_01KRKDVVV2YF4XMKNCVEG1FFSG=nota-8 h_01KRKDVVV242YPHP2W8EWTBSMD=consejo conditional-inapp-event-postbacks=postbacks-condicionales-de-eventos-in-app h_01HBZCRNKG5X3B2NJZZP6ER2CX=postbacks-condicionales-de-eventos-in-app considerations=consideraciones h_01HBZCRNKHBR57YVHZQP7NJBAP=consideraciones h_01HBZCRNKHF6TFP0N302D7DCMD=nota-9 editing-multiple-events=editar-m%C3%BAltiples-eventos h_01HBZCRNKHHD3WC4GTJT9NSJ4C=editar-m%C3%BAltiples-eventos custom-events=eventos-personalizados h_01HBZCRNKH754PANWSZ4FMXJVQ=eventos-personalizados h_01HBZCRNKH4PVR3FEMTMERW3M1=nota-10 event-mapping-by-ad-networks=mapeo-de-eventos-por-ad-networks h_01HBZCRNKH1GCZY17R04WTZ0MQ=mapeo-de-eventos-por-ad-networks event-mapping-by-agencies=mapeo-de-eventos-por-agencias h_01HBZCRNKHHF3E6CZNQQG0Q4VS=mapeo-de-eventos-por-agencias h_01K5B6QS6YXKMJSEWE2WFT5AQC=nota-11" />
