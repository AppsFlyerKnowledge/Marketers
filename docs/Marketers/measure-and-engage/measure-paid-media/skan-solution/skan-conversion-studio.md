---
title: Estudio de conversión SKAN
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
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2026-08-12T12:21:33Z'
  id: 4403727223185
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/4403727223185
---
> **Resumen**: Utiliza SKAN Conversion Studio para definir qué interacciones de usuario en la aplicación se van a medir y durante cuánto tiempo. Mide los ingresos, la conversión, la participación y la retención durante un periodo limitado después de la instalación. Al añadir la medición de Fuente Única de Verdad, te informamos si el usuario fue atribuido tanto por AppsFlyer como por SKAN.

<Embed title="SKAN 4 Conversion Studio (incluyendo ventana de bloqueo)" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

## Aspectos básicos del SKAN Conversion Studio

Dentro del flujo de atribución de SKAdNetwork (SKAN), un dispositivo iOS envía postbacks de SKAN que contienen los valores de conversión más recientes (CV) después de cada ventana de medición.

Para SKAN 3 y versiones anteriores, hay un postback que llega después de que termina la ventana de actividad inicial. La ventana de actividad puede ser de 12 horas a 63 días. El CV se limita a 6 bits, resultando en 64 valores posibles (0-63).

Para SKAN 4, llegan 3 postbacks después de que finaliza cada una de las 3 ventanas, tras los días 2, 7 y 35, respectivamente. Para:

* Ventana 1, el CV fino se limita a 6 bits, resultando en 64 valores posibles (0-63).
* En las Ventanas 1-3, el CV grueso se limita a un nivel bajo, medio o alto. (Las Ventanas 2 y 3 no tienen CV finos).

Estas limitaciones de CV significan que puede que necesites tomar decisiones difíciles sobre cómo utilizar esos 64 posibles valores para CV finos y 3 posibles valores para CV gruesos.

Conversion Studio te ofrece la máxima flexibilidad para aprovechar al máximo cada valor y bit. Determinas con precisión qué datos de medición deben codificarse dentro del CV, incluyendo qué actividad medir y durante cuánto tiempo durante el periodo después de la instalación. Existen varios modos de medición que puedes emplear para configurar los ajustes de tu CV.

| Tipo | Modo de medición | Descripción | Ventana de actividad |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Práctica recomendada]<br /><br />[Predeterminado] | Configura una combinación de mediciones de ingresos, conversiones (eventos en la aplicación) y participación durante 3 ventanas de medición ajustables.<br /><br />Las 3 ventanas miden períodos de tiempo diferentes y no superpuestos posteriores a la instalación. Por ejemplo, la ventana 2 mide del día 3 al 7 después de la instalación, y no del 0 al 7. | <ul><li>Ventana 1: 1-2 días</li><li>Ventana 2: 3-7 días</li><li>Ventana 3: 8-35 días</li></ul> |
| Flexible | Personalizado | Configura una combinación de mediciones de ingresos, conversiones (eventos en la aplicación) y participación durante una ventana de actividad ajustable. | 12-1512h (por defecto es hasta 72 horas, aunque se puede ampliar) |
| Fijo* | Ingresos<br /><br />[Heredado] | Mide los ingresos utilizando uno de los siguientes intervalos:<ul><li>$1-$630 en incrementos de $10</li><li>$1-$63 en incrementos de $1</li><li>$0.01-$0.63 en incrementos de $0.01</li></ul> | 24 horas |
| Fijo* | Conversión<br /><br />[Heredado] | Selecciona de 1 a 6 eventos en la aplicación. | 24 horas |
| Fijo* | Participación<br /><br />[Heredado] | Número de veces que un usuario realiza un evento | 24 horas |
| Flexible | <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">Descodificar</Anchor> | <ul><li>Crea tu propio mapeo de evento a CV y configura el CV directamente en la aplicación. Usa esta opción si no puedes integrar el SDK de AppsFlyer en tu aplicación. Para utilizar Decode, ve a **SKAN Conversion Studio,** haz clic en opciones (⋮) y selecciona **Subir archivo de mapeo personalizado**.</li></ul> | 12-1512h (63 días) |

*Los modos fijos estarán indisponibles para nuevas aplicaciones a partir del 23/06/2024.  Todas las funcionalidades están disponibles en los modos Personalizado y SKAN4.

**Consejo!** Prueba Conversion Studio. En AppsFlyer, ve a > **Configuración** > **SKAN Conversion Studio**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Principios y definiciones de medición">

**Definiciones**

* **Ventana de medición SKAN**: Aplicable para SKAN 4+. Existen 3 períodos de tiempo (ventanas) en los que se mide la actividad del usuario posterior a la instalación:
  * Ventana 1: 1-2 días
  * Ventana 2: 3-7 días
  * Ventana 3: 8-35 días
  * Las 3 ventanas miden períodos de tiempo diferentes y no superpuestos posteriores a la instalación. Por ejemplo, la ventana 2 mide del día 3 al 7 después de la instalación, y no del 0 al 7.
* **Ventana de actividad:** Aplicable para SKAN 3 y anteriores. Tiene una duración establecida, con un predeterminado de 24 horas, comenzando desde la primera vez que se abre la aplicación. Si está usando SKAN 4+, pero los dispositivos de usuario o las redes publicitarias aún no admiten SKAN 4, la ventana de actividad tiene una duración de 48 horas.
* **Valor de conversión (CV)**: Es la medida de la calidad del usuario reportada en los postbacks enviados por iOS al final de las ventanas SKAN 4 o, para SKAN 3 y anteriores, al final de la Ventana de Actividad. El SDK de AppsFlyer configura los CV automáticamente para ti. No obstante, si desea configurar el CV, utilice <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> para cargar su archivo de mapeo de CV.
  * Para SKAN 4+, existen tanto valores de conversión finos como gruesos.
* **Capacidad de valores de conversión:** Cantidad de CV necesarios para mapear su configuración. Cuantos más componentes y elementos de medición seleccione, mayor será la capacidad de valores de conversión requerida. Cada rango o elemento de configuración seleccionado consume capacidad de valores de conversión. (¡Y cada unidad de configuración adicional incluida en un componente único lo consume exponencialmente!) [Ejemplos de uso máximo de CV.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* Fuente Única de la Verdad (SSOT): <Anchor target="_blank" href="/marketers/es/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Mecanismo para señalar</Anchor> si el usuario fue atribuido por SKAN y otro método de coincidencia de atribución. Se utiliza el indicador para eliminar datos duplicados de instalación en los datos sin procesar de SKAN y para calcular métricas reales de rendimiento.
* **Componentes de medición**:  
  * **Ingresos:** Mide los ingresos generados
  * **Evento dentro de la app**: Mide la conversión (número de usuarios únicos que realizan un evento),  
    la participación (número de veces que se realizó un evento) o ambos.
  * **Embudo**: Mide la ocurrencia de eventos dentro de la app en base a una lista de eventos secuenciales en un embudo. A un usuario que realiza cualquier evento en el embudo se le considera haber realizado todos los eventos anteriores a ese.
  * **Prioridad**: Un componente que incluye ingresos, eventos en la app, o ambos.

**Principios**

* **![Admin.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Solo administrador:** Solo un administrador puede guardar la configuración de Conversion Studio. Los usuarios de la cuenta pueden ver la configuración.
* En cualquier momento dado, solo un modo está activo.
* Para un modo específico, AppsFlyer asigna las combinaciones definidas por su configuración a CVs. Puede [ver y descargar la tabla de mapeo](/docs/skan-conversion-studio#view-cv-mapping).
* En la aplicación, AppsFlyer establece el CV después de cada acción medible del usuario utilizando el modo de medición activo cuando un usuario abre la app por primera vez.
* iOS considera el <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">anonimato del público de Apple</Anchor> antes de completar el CV en el postback.
* Las acciones del usuario que ocurren después del final de una ventana no se consideran.
* Panel de control y reportes de SKAN:
  * El diseño y las métricas del panel de control SKAN dependen del modo y la configuración.
  * El diseño se actualiza diariamente según el modo activo a medianoche UTC. El diseño actualizado debería estar disponible a las 05:00 UTC.
  * En SKAN 4, Custom y Decode, no están disponibles los datos orgánicos para eventos dentro de la app y los ingresos generales.

#### **Principios S2S**

Las acciones medibles se pueden reportar a través de la API [de servidor a servidor (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Considere lo siguiente para cada modo:

* SKAN 4 y Personalizado: S2S está siempre activo.
* Descodificar: S2S no es adecuado para el modo de decodificación y no está disponible. AppsFlyer no establece el CV en este modo.
* [Legado] Modos de ingresos, conversión y participación: Debe activar la [grabación de eventos S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api) antes de enviar eventos.

</Accordion>

## Configuración de valores de conversión en SKAN Conversion Studio

Existen varios modos disponibles en SKAN Conversion Studio para establecer valores de conversión:

* SKAN 4: Utilice distintos componentes de medición, como ingresos, eventos en la app, prioridad y Fuente Única de Verdad, para determinar qué se mide durante cada una de las tres ventanas de medición.
* Personalizado: Utilice distintos componentes de medición, como ingresos, eventos en la app, prioridad y Fuente Única de Verdad, para determinar qué se mide durante la Ventana de Actividad.
* [Legado] Modos fijos: Mida el valor del usuario utilizando una de las siguientes mediciones:
  * Ingresos
  * Conversión
  * Participación

Para más información sobre los distintos modos de medición, consulte las siguientes secciones.

> 🚧 **Importante:**
>
> La configuración de valores de conversión en SKAN Conversion Studio debe ser realizada por un administrador o un usuario con permisos de **Gestión** en **SKAN Conversion Studio**.
>
> **Para ver o modificar permisos de usuario:**
>
> 1. En AppsFlyer, en la parte superior derecha, haz clic en tu dirección de correo electrónico.
> 2. Selecciona **Gestión de Usuarios**> Selecciona el usuario.
> 3. Si es necesario, otorga al usuario los permisos **Gestión** en **SKAN Conversion Studio**. Para más información sobre los permisos, consulta <Anchor target="_blank" href="/marketers/es/docs/user-management">Gestión de Usuarios</Anchor>.
>
> *Nota: Es posible que los usuarios cuyo acceso esté limitado a fuentes de medios y geolocalizaciones específicas no puedan ver ni acceder a SKAN Conversion Studio.

<div id="skan-4" />

<Accordion title="SKAN 4">

En SKAN 4, utilizas diferentes componentes de medición, como ingresos, eventos dentro de la aplicación, prioridades y la Fuente Única de Verdad, para determinar qué se mide durante cada una de las tres ventanas de medición. Estos componentes, en conjunto, crean tu modo de medición SKAN 4.

Si estás actualizando a SKAN 4 desde un modo SKAN anterior, tu asignación de esquema actual se transfiere a la configuración detallada de la ventana 1. AppsFlyer asigna automáticamente los valores aproximados para las ventanas 1-3.

Para configurar manualmente SKAN 4, prueba con diferentes opciones. A medida que realizas cambios, el resumen de **Capacidad de valor de conversión** se actualiza. Optimiza tus ajustes para capturar los datos más valiosos sin superar la capacidad. Consulta [Cálculo de la capacidad del valor de conversión.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![Contador de capacidad.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Nota: Si estás actualizando a SKAN 4 desde un modo SKAN anterior, tu esquema de mapeo actual se utiliza para mediciones detalladas, y AppsFlyer mapea automáticamente los valores generales por ti. Y si eres nuevo en SKAN, AppsFlyer te ofrece una asignación predeterminada inicial.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara configurar manualmente los valores de conversión en Conversion Studio usando el modo SKAN 4:**

1. En el panel de control de AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio.**
2. Haz clic en las opciones (⋮) para mostrar el menú de opciones y asegúrate de que la **medición SKAN** esté activada.   
   [Práctica recomendada]: **¡Nota**! Si está desactivado, el SDK no llamará a funciones SKAN de iOS como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Selecciona el modo de medición **SKAN 4.0**.
4. Haz clic en **Continuar**.  
   Se abre la configuración para el CV detallado de **Ventana 1 (1-2 días)**.
5. [Opcional] Activa **Fuente Única de Verdad (SSOT)**.  
   El mecanismo SSOT marca (y elimina duplicados) las instalaciones reportadas por más de un método de coincidencia de atribución. <Anchor target="_blank" href="/marketers/es/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Más información</Anchor>
6. Haz clic en **+ Agregar medición** para añadir diferentes [componentes de medición](/docs/skan-conversion-studio#componentes-de-medición).  
   Las siguientes secciones detallan las opciones de configuración y los componentes. Úsalas como guías mientras experimentas con las diferentes configuraciones de medición de SKAN:
   * Ingresos
   * Evento en la aplicación
   * Embudo
   * Prioridad
7. Haz clic en **Aproximado** y repite los pasos 6 y 7 para configurar el CV aproximado de la **Ventana 1 (1-2 días)**.   
   **Nota**:
   * Solo están disponibles los componentes de medición de ingresos y eventos en la aplicación.
   * El CV bajo debe ser una sesión de usuario para asegurar que se envíe el postback.
8. [Opcional] Activa **Bloquear ventana** y establece la condición (ya sea el tiempo o el valor de conversión aproximado) para bloquear la ventana SKAN antes del valor predeterminado. [Más información](/docs/skan-conversion-studio#lock-window)
9. Haga clic en **Ventana 2 (3 a 7 días)** y repita los pasos 6 a 8 para configurar el CV de la ventana 2.   
   **Nota**:
   * Solo están disponibles los componentes de medición de ingresos y eventos en la aplicación.
   * [Recomendado] Un CV bajo debería corresponder a una sesión de usuario.
10. Haga clic en **Ventana 3 (8-35 días)** y repita los pasos 6 a 8 para configurar el CV de la ventana 3.   
    **Nota**:
    * Solo están disponibles los componentes de medición de ingresos y eventos en la aplicación.
    * [Recomendado] Un CV bajo debería corresponder a una sesión de usuario.
11. Haga clic en **Guardar**.
12. Verifique que las asignaciones de postback de eventos en la aplicación de su socio correspondan con los eventos que ha configurado.

</Accordion>

<div id="custom" />

<Accordion title="Personalizado">

En el modo Personalizado, se utilizan componentes de medición como ingresos, eventos en la aplicación, prioridad y Fuente única de verdad para determinar qué se mide y establecer una ventana de actividad que defina la duración y los intervalos de medición. Todos estos componentes juntos crean tu modo de medición personalizado.

Para establecer el modo Personalizado, prueba con diferentes opciones. Al realizar cambios, se actualiza el resumen de la **capacidad del valor de conversión**. Optimiza tus ajustes para capturar los datos más valiosos sin superar la capacidad. Consulta [Cálculo de la capacidad del valor de conversión.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![Contador de capacidad.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Nota: De forma predeterminada, AppsFlyer muestra SKAN 4 en Conversion Studio. Para volver a un modo anterior, haz clic en el icono de opciones (⋮) para mostrar el menú de opciones y selecciona Revertir a la versión anterior de SKAN.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara establecer manualmente los valores de conversión en Conversion Studio usando el modo Personalizado:**

1. En el panel de control de AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio.**
2. Haz clic en las opciones (⋮) para mostrar el menú de opciones y asegúrate de que la **medición SKAN** esté activada.   
   [Práctica recomendada]: **¡Nota**! Si está desactivado, el SDK no llamará a funciones SKAN de iOS como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Selecciona el modo de medición **Personalizado**.
4. Haz clic en **Continuar**.
5. [Opcional] Activa **Fuente Única de Verdad (SSOT)**.  
   El mecanismo SSOT marca (y elimina duplicados) las instalaciones reportadas por más de un método de coincidencia de atribución. <Anchor target="_blank" href="/marketers/es/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Más información</Anchor>
6. Haz clic en **+ Agregar medición** para incorporar diferentes componentes de medición.  
   Las siguientes secciones detallan las opciones de configuración y los componentes. Úsalas como guías mientras experimentas con las diferentes configuraciones de medición de SKAN:
   * Ingresos
   * Evento en la aplicación
   * Embudo
   * Prioridad
7. Configura la duración de la ventana de actividad (12 horas-63 días) durante la cual deseas medir la actividad del usuario.  
   El **Temporizador de actividad** predeterminado te permite establecer la ventana entre 24 y 72 horas. Y la configuración predeterminada del **Intervalo** te permite fijar 12 o 24 horas. Usa **Ventana personalizada** para ampliar la ventana de actividad hasta 63 días y establecer intervalos más prolongados.
8. Haga clic en **Guardar**.
9. Verifique que las asignaciones de postback de eventos en la aplicación de su socio correspondan con los eventos que ha configurado.

</Accordion>

<div id="fixed-modes" />

<Accordion title="[Antiguo] Modos fijos">

> 📘 **Nota:**
>
> Los modos fijos no estarán disponibles para nuevas aplicaciones a partir del 23/06/2024.  Todas las funcionalidades son compatibles con los modos Custom y SKAN4.

Con los modos fijos puedes medir el valor del usuario utilizando una de las siguientes métricas:

* * Ingresos
  * Conversión
  * Participación

Al modificar la configuración del modo, se actualiza el resumen de la **capacidad del valor de conversión**. Optimiza tus ajustes para capturar los datos más valiosos sin superar la capacidad. Consulta [Cálculo de la capacidad del valor de conversión.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![Contador de capacidad.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**¡Atención!**

* La medición en modo fijo corresponde a una ventana de actividad de 24 horas que empieza con la primera apertura de la app.
* Si deseas enviar eventos a través de S2S, debes habilitar explícitamente [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api).

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara establecer manualmente los valores de conversión en Conversion Studio usando un modo fijo:**

1. En el panel de control de AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio.**
2. Haga clic en el icono (⋮) para mostrar el menú de opciones y:
   * Asegúrese de que la **medición SKAN** esté activada.   
     [Práctica recomendada]: **¡Nota**! Si está desactivado, el SDK no llamará a funciones SKAN de iOS como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * [Opcional] [Habilite el envío de eventos por S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Disponible si el modo seleccionado es ingresos, conversión o participación.
3. Seleccione un modo de medición fijo.
4. Siga la información y las instrucciones en la tabla siguiente para el modo de medición fijo que eligió.
5. Haga clic en **Guardar**.
6. Verifique que las asignaciones de postback de eventos en la aplicación de su socio correspondan con los eventos que ha configurado.

#### Medición en modo fijo

| Modo de medición | Descripción |
| --- | --- |
| Ingresos totales | ![IngresosFijos.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Ingresos generados durante la ventana de actividad de 24 horas.**<br /><br />Seleccione una tasa de conversión a USD de una de las siguientes opciones:<ul><li>0,01 $ para medir hasta 0,63 $</li><li>1 $ para medir hasta 63 $</li><li>10 $ para medir hasta 630 $</li></ul>AppsFlyer completa automáticamente 63 rangos de medición de ingresos. Asegúrese de que el nombre del evento `af_skad_revenue` esté correctamente asignado para los socios. En el panel, los ingresos se registran como el máximo del rango. Por ejemplo, si el rango es $60-$61, el ingreso registrado es $61. ¡Atención! ¡Nota! Los ingresos personalizados utilizan un método diferente para su cálculo.<br /><br />**Métricas disponibles:**<ul><li>Ingresos<ul><li>ROI (Retorno de la Inversión)</li><li>ROAS (Retorno de la Inversión Publicitaria)</li><li>ARPU (Ingresos medios por usuario): Ingresos/usuarios que instalan la aplicación</li><li>Tasa de conversión de usuarios: Usuarios que realizan una compra/usuarios que instalan la aplicación</li><li>Costo Efectivo por Adquisición (eCPA)</li></ul></li></ul> |
| Conversión | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**Eventos in-app realizados una o más veces durante la ventana de actividad de 24 horas.**<br /><br />**Configuración**:<ul><li>Seleccione de 1 a 6 eventos in-app para medir de la lista desplegable. Limitación: La lista se limita a los 300 eventos más importantes ocurridos en los últimos 30 días.</li><li>En el panel de SKAdNetwork, seleccione un evento determinado como el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">evento de conversión</Anchor>.</li></ul>**Métricas por evento in-app:**<ul><li>Cantidad de usuarios que realizan un evento<ul><li>Tasa de conversión: Usuarios que realizan el evento de conversión/usuarios que instalan la aplicación</li><li>Costo Efectivo por Adquisición (eCPA)</li><li>Sesiones (utiliza el evento *af\_app\_opened*)</li></ul></li></ul>Ejemplo de recuentos de usuarios:<ul><li>Registro completado</li><li>Realizó una compra</li><li>Alcanzó un nivel de juego</li></ul>**¡Aclaración! ¡Aclaración!** Utilice la medición de conversión para contar **si** un usuario realizó un evento. Para contar cuántas veces un usuario realiza un evento, utilice la medición de interacción. |
| Participación | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Número de veces que el usuario realizó un evento específico en la aplicación durante el periodo de actividad**<br /><br />**Configuración:**<ul><li>Seleccione un evento en la aplicación del menú desplegable.</li><li>La selección dentro de la aplicación también se denomina Evento de Conversión.</li><li>Rango de valores: 0-63</li></ul>**Métricas para el evento en la aplicación**:<ul><li>Cantidad de usuarios que realizan el evento<ul><li>Número medio de eventos por usuario</li><li>Tasa de conversión</li><li>Costo Efectivo por Adquisición (eCPA)</li><li>Sesiones</li></ul></li></ul>Ejemplos:<ul><li>Medir el número de veces:<ul><li>Un usuario abrió la aplicación</li><li>El usuario vio un anuncio</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Descodificar">

Crea tu propio mapeo de CV a evento y configura el CV en la aplicación tú mismo. Usa esta opción si no puedes integrar el SDK de AppsFlyer en tu aplicación.

**Para usar Decode**:

1. En el panel de control de AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio.**
2. Haga clic en el icono (⋮) para mostrar el menú de opciones y:
   * Asegúrese de que la **medición SKAN** esté activada.   
     [Práctica recomendada]: **¡Nota**! Si está desactivado, el SDK no llamará a funciones SKAN de iOS como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Sube tu archivo de mapeo de Decode.
3. Haga clic en **Guardar**.
4. Verifique que las asignaciones de postback de eventos en la aplicación de su socio correspondan con los eventos que ha configurado.

</Accordion>

## Componentes de medición

<div id="single-source-of-truth" />

<Accordion title="Fuente única de verdad">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png"/></p><p>El mecanismo <a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Fuente única de verdad (SSOT)</a> marca (y elimina duplicados) las instalaciones informadas por más de un método de coincidencia de atribuciones. En otras palabras, SKAN y otro método. La bandera está disponible en los informes de datos sin procesar de SKAN y se tiene en cuenta al calcular métricas en el panel de control <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#panel-de-vista-general-para-la-fuente-única-de-verdad" target="_blank">vista SSOT</a>. </p></td></tr><tr><td>Obligatorio</td><td>No</td></tr><tr><td>Uso múltiple permitido</td><td>No</td></tr><tr><td>Opciones de configuración</td><td><p>Si SSOT está activado, el CV se configura de modo que pueda marcar si un usuario está atribuido por SKAN y otro método de coincidencia de atribuciones. </p><p>¿Dónde se utiliza la bandera SSOT?</p><ul><li>Vista SSOT del panel de control de AppsFlyer</li><li>Los informes de datos sin procesar de SKAN tienen el campo <em>af_attribution_flag</em>. Si es verdadero, el usuario fue atribuido tanto por SKAN como por otro método. </li><li>Informes API de atribuciones agregadas de SKAN.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="Componente de evento en la aplicación">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioEvento en la aplicación.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        Obligatorio
      </td>
      <td>
        No
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiple permitido
      </td>
      <td>
        Sí
      </td>
    </tr>
    <tr>
      <td>
        Opciones de configuración
      </td>
      <td>
        Seleccione un evento dentro de la aplicación; a continuación, configure los rangos de acuerdo con su objetivo de medición de esta manera:

        * **Solo conversión:** Configure un único rango de 0 a 1
        * **Interacción y conversión:** Configure múltiples rangos con los seleccionados
      </td>
    </tr>
    <tr>
      <td>
        Rangos para el engagement
      </td>
      <td>
        Para evaluar la interacción, debe crear rangos de ocurrencia. Cuando se reporta una ocurrencia del evento de interacción seleccionado, SKAN la asocia con el rango adecuado según el número de ocurrencias del evento.

        **Características**

        * Cada rango contiene un rango de ingresos que consiste en un valor **desde** y un valor **hasta**. El valor inferior no se incluye en el rango; sin embargo, el valor superior sí se incluye. Por ejemplo, un rango de 5 a 10 significa mayor que 5 hasta, e incluyendo, 10.
        * El rango con el valor más bajo siempre comienza en 0 (pero no incluye el 0 en sí mismo).
        * Puede crear tantos rangos como desee; sin embargo, recuerde que cada rango afecta la capacidad de su valor de conversión.
        * Los rangos deben ser secuenciales (sin huecos entre ellos).

        **Medición de la interacción usando rangos**

        * Cuando se reporta la ocurrencia de un evento, SKAN asocia la ocurrencia con el rango correspondiente. Las ocurrencias registradas se basan en el promedio del rango. El valor se redondea al entero más cercano. Por ejemplo, 5.7 se redondea a 6.
        * Si el número de ocurrencias supera el valor máximo del rango más alto, se asocian con el rango de mayor valor. El número de ocurrencias registradas es el valor promedio del rango más alto. En otras palabras, se ignora el número real de ocurrencias.
        * En los datos en bruto, están disponibles tanto el número real de ocurrencias como los rangos.

        **Ejemplo:**

        En la imagen se muestran los siguientes rangos de ocurrencia:

        Los rangos de ocurrencia establecidos son:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Se registra el número de ocurrencias utilizando los rangos de la siguiente manera:

        | Ejemplo | Número de ocurrencias informadas por el SDK | Rango asociado | Número de ocurrencias notificadas |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        Limitación
      </td>
      <td>
        Un evento específico dentro de la aplicación se puede asociar una vez con este componente.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Componente de ingresos">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        Obligatorio
      </td>
      <td>
        No
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiple permitido
      </td>
      <td>
        Sí, si se utiliza la fuente de ingresos del evento en la aplicación.
      </td>
    </tr>
    <tr>
      <td>
        Opciones de configuración
      </td>
      <td>
        Los ingresos totales de todos los flujos pueden registrarse mediante un solo evento o por flujos individuales seleccionando eventos específicos en la aplicación que generen ingresos.

        Se permiten las siguientes opciones de fuentes de ingresos:

        * **Ingresos totales**
          * Los ingresos totales, que incluyen todos los ingresos de eventos en la aplicación y la publicidad (cuando sea relevante), pueden medirse con un solo evento `af_skad_revenue`. Asegúrese de que el nombre del evento `af_skad_revenue` esté correctamente asignado a los socios.
          * El componente se puede incluir una sola vez.
        * **Evento en la aplicación**
          * Se puede medir diferentes flujos de ingresos seleccionando eventos concretos en la aplicación dentro del esquema SKAN. Tras añadir la medición de ingresos, seleccione "evento en la aplicación" en la opción de fuente de ingresos. Asegúrese de que todos los eventos estén debidamente mapeados a las redes publicitarias.  
            Nota: Al medir ingresos de eventos específicos en la aplicación, `af_skad_revenue` no debe ser mapeado.
          * El componente se puede utilizar varias veces.
          * Si informa ingresos vía postback a redes publicitarias, verifique que el mapeo de sus postbacks de eventos en la aplicación incluya los eventos de ingresos que haya configurado.
      </td>
    </tr>
    <tr>
      <td>
        Rangos
      </td>
      <td>
        Para medir los ingresos, es necesario crear rangos de ingresos. Cuando se informan ingresos, SKAN asocia los ingresos reportados con el rango correspondiente.

        **Características**

        * Cada rango contiene un intervalo de ocurrencia compuesto por un valor **desde** y un valor **hasta**. El valor inferior no se incluye en el rango, pero el valor superior sí. Por ejemplo, un rango de 5 a 10 significa mayor que 5 hasta, e incluyendo, 10.
        * El rango con el valor más bajo siempre comienza en 0 (pero no incluye el 0 en sí mismo).
        * Puede crear tantos rangos como desee; sin embargo, recuerde que cada rango afecta la capacidad de su valor de conversión.
        * Los rangos deben ser secuenciales (sin huecos entre ellos).
        * Las cantidades están en USD.
        * Si ejecuta campañas en anuncios de Meta, debe tener 4 o más rangos.
        * Los valores del rango pueden tener hasta 4 cifras después del punto decimal.

        **Registro de ingresos utilizando rangos**

        * Cuando se reportan los ingresos, SKAN asocia los ingresos al rango adecuado. Los ingresos registrados equivalen al valor promedio del rango.
        * Si los ingresos reportados superan el valor promedio del rango de mayor valor, se asocian a este último.   
          [Práctica recomendada]: **¡Nota**! El valor registrado de los ingresos es el promedio de este rango. En otras palabras, no se considera el monto exacto de los ingresos.
        * En los datos sin procesar están disponibles tanto los ingresos registrados como el rango asociado.

        **Ejemplo:**

        En la imagen, se muestran los siguientes rangos de ingresos:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Los ingresos se registran con los siguientes rangos:

        | Ejemplo | Ingresos reportados por el SDK | Rango asociado | Ingresos registrados |
        | --- | --- | --- | --- |
        | 1 | 5 | A | $2,5 |
        | 2 | 6 | B | $ 7.5 |
        | 3 | 10 | B | $ 7.5 |
        | 4 | 125 | C | $15 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Componente del embudo">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![Embudo de valor de conversión.png](https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png)
      </td>
    </tr>
    <tr>
      <td>
        Obligatorio
      </td>
      <td>
        No
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiple permitido
      </td>
      <td>
        No
      </td>
    </tr>
    <tr>
      <td>
        Opciones de configuración
      </td>
      <td>
        Presente un conjunto secuencial de eventos en un embudo. Puesto que la ocurrencia de un solo evento se considera como la de todos los eventos precedentes, el orden en que se listan es crucial, como se muestra en el siguiente ejemplo.
      </td>
    </tr>
    <tr>
      <td>
        Ejemplo
      </td>
      <td>
        Un embudo incluye los eventos a, f, b, k y z, como se ilustra en la imagen anterior.

        | Ejemplo | Evento realizado | Eventos registrados |
        | --- | --- | --- |
        | 1 | un | un |
        | 2 | b | a, f, b |
        | 3 | z | a, f, b, k, z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Componente de medición de prioridades">

Utilice el componente de medición de prioridades, parte del modo personalizado, para clasificar los recorridos de acción del usuario en la app según su lógica comercial, de modo que las mediciones de alta prioridad sobrescriban las de baja prioridad. Esto le permite decidir qué medir en cada paso del embudo de conversión.

Cada prioridad (máximo de 63) puede incluir ingresos, eventos dentro de la app o ambos. Cuando un usuario realiza eventos en la app, AppsFlyer determina qué prioridad se adapta a las acciones realizadas y ajusta el CV en consecuencia.

Para facilitar la comprensión, comparemos el uso de Personalizado con y sin el componente de prioridad. **Sin** prioridad, AppsFlyer asigna todas las combinaciones de medición posibles a los CV. Mientras que **con** prioridad, solo las combinaciones de medición que hayas establecido explícitamente se asignan a los CV.

La prioridad se explica mejor en el [ejemplo detallado](/docs/skan-conversion-studio#priority-measurement-detailed-example) de este artículo.

**Principios de prioridad**

* Puedes establecer entre 1 y 63 niveles de prioridad. La cantidad disponible depende de tu ventana de actividad y la configuración de Fuente Única de Verdad.
* La prioridad 1 siempre tiene la mayor prioridad. La prioridad con el número más alto tiene la prioridad más baja.
* Una prioridad se compone de [ingresos](/docs/skan-conversion-studio#revenue-component) o [eventos dentro de la aplicación](/docs/skan-conversion-studio#inapp-event-component), o de ambos componentes. Una prioridad puede contener múltiples eventos en la aplicación y flujos de ingresos.
* No se puede configurar un embudo en la prioridad. Sin embargo, configura múltiples eventos en la aplicación dentro de una prioridad para medir la conversión del usuario en un embudo.
* Para utilizar el componente de medición de prioridad, no se pueden tener otros componentes como eventos en la aplicación o ingresos configurados.

**Para establecer la medición utilizando prioridad:**

1. En AppsFlyer, dirígete a **SKAN Conversion Studio.**
2. Selecciona **Personalizado** y haz clic en **Continuar**.
3. Si es necesario, haz clic en **Eliminar** para borrar la configuración actual.
4. Haz clic en **+ Añadir medición**. Selecciona **Prioridad**.   
   Se muestra prioridad 1.  

   [![CVmapping.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Selecciona un componente de medición entre:
   * Ingresos
   * Evento en la aplicación
6. Completa los campos según la interfaz de usuario.
   * Considera que una prioridad puede consistir en ingresos, eventos en la aplicación, o ambos.
   * Los valores de los rangos de ocurrencias de eventos e ingresos pueden estar en orden ascendente (creciente) o descendente (decreciente), pero deben ser continuos. Por ejemplo, los siguientes rangos son continuos: 1-5, 5-8, 8-10, y así sucesivamente. Un rango determinado se puede utilizar más de una vez (repetitivo) si la segunda vez que se usa forma parte de una combinación única y es el mismo rango que la última prioridad con rango. Por ejemplo, 1-5, 1-5 + añadir al carrito.  
     **Ejemplo de aumento y disminución de ingresos**

| Evento | Ocurrencia | Ingresos |
| --- | --- | --- |
| Evento P1\_a | 2-3 | 5-50 dólares |
| Evento P2\_a | 2-3 | 0-5 dólares |
| Evento P3\_a | 1-2 | 5-50 dólares |
| Evento P4\_a | 1-2 | 0-5 dólares |
| Evento P5\_a | 0-1 | 5-50 dólares |
| Evento P6\_a | 0-1 | 0-5 dólares |

7. Haz clic en **Validar**.  
   Aparece el mensaje **La prioridad es válida**. Si no es así, corrige tu prioridad antes de continuar.
8. Realice una de las siguientes acciones:
   * Para añadir una prioridad, haz clic en **+ Añadir prioridad.** La prioridad existente número 1 se desplaza hacia abajo y se convierte en la prioridad número 2. Complete la configuración de prioridades como se explicó anteriormente.
   * Para eliminar una prioridad, haga clic en … > **Eliminar.**
   * Para ajustar el nivel de prioridad, haga clic en **Opciones** (⋮) y elija **Cambiar orden** o **Establecer como prioridad más baja**.
   * Para duplicar una prioridad, haga clic en **Opciones** (⋮) y seleccione **Duplicar**.
   * Haga clic en **Guardar** para finalizar la configuración de prioridades.

</Accordion>

<div id="lock-window" />

<Accordion title="Ventana de bloqueo">

**Nota**: La ventana de bloqueo solo es aplicable para SKAN 4 y versiones superiores.

<table><tbody><tr><td colspan="2"><img alt="bloquear_ventana.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></td></tr><tr><td>Uso</td><td>Por defecto, las ventanas de SKAN miden el valor del usuario en momentos específicos después de la instalación. Puede bloquear las ventanas anticipadamente y recibir postbacks con todos los datos disponibles. Para hacerlo, establezca las condiciones para cuándo bloquear las ventanas.</td></tr><tr><td>Obligatorio</td><td>No</td></tr><tr><td>Uso múltiple permitido</td><td>Sí, uno para cada ventana SKAN</td></tr><tr><td>Opciones de condición</td><td><p>La ventana de bloqueo ofrece dos opciones para bloquear la ventana SKAN de forma anticipada:</p><ul><li>Tiempo: Debes elegir un tiempo post-instalación (antes del tiempo predeterminado) para cerrar la ventana. <strong>Nota</strong>: El cierre basado en tiempo no tiene efecto a menos que el usuario abra la aplicación.</li><li>Valor grueso alto: En cuanto se alcanza el valor grueso alto, la ventana se cierra.</li></ul></td></tr><tr><td>Impacto del uso de la ventana de bloqueo</td><td>Los postbacks de SKAN no contienen información sobre cuándo se cierra una ventana, por lo que el estado de la ventana de bloqueo no se considera al estimar el tiempo de instalación. Por ello, bloquear la ventana anticipadamente podría afectar la precisión de las estimaciones del tiempo de instalación.</td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Ventana de actividad">

**Nota**:

* La ventana de actividad es solo relevante para SKAN 3 y versiones anteriores (es decir, modos personalizados y fijos).
* Si está usando SKAN 4+, pero los dispositivos de usuario o las redes publicitarias aún no admiten SKAN 4, la ventana de actividad tiene una duración de 48 horas.

<table><tbody><tr><td colspan="2"><img alt="ventana_de_actividad_flexible.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></td></tr><tr><td>Obligatorio</td><td>Sí </td></tr><tr><td>Uso múltiple permitido</td><td>No</td></tr><tr><td>Características temporales</td><td><ul><li>El temporizador tiene una duración fija, que usted determina, y funciona en paralelo con el temporizador de iOS.</li><li>Por el contrario, el temporizador de iOS tiene una duración inicial de 24 horas. Cada vez que aumenta el valor de conversión, el temporizador se restablece.</li><li>Duración predeterminada: 24 horas.</li><li>La medición se detiene cuando alguno de los temporizadores alcanza 0. </li></ul></td></tr><tr><td>Duración del temporizador</td><td><ul><li>Rango: 12-72 horas. Para más opciones, consulte <strong>Medición flexible</strong> en esta tabla.  </li><li>Cuando el temporizador termina, AppsFlyer deja de medir.</li><li>Si la duración del temporizador supera las 24 horas, el usuario debe estar activo en la aplicación al menos una vez por intervalo. De lo contrario, la medición puede finalizar antes de tiempo, porque AppsFlyer no puede impedir que el temporizador de iOS llegue a 0, lo que implica que iOS finaliza la medición. </li></ul></td></tr><tr><td>Intervalo</td><td><p>12 o 24 horas. Los intervalos afectan la precisión del rango de tiempo de última actividad y del tiempo de instalación. Para más opciones, consulte <strong>Medición flexible</strong> en esta tabla. </p><p>El rango de tiempo de última actividad está disponible en los informes de datos en bruto en las columnas <em>min_install_time</em> y <em>max_install_time</em>, y se utiliza para determinar el tiempo de instalación como se describe en esta sección.</p><p>Ejemplo:</p><ul><li>La duración del temporizador se establece en 48 horas.</li><li>El usuario estuvo activo por última vez durante la hora 40.</li><li>Dependiendo de la configuración del intervalo, el rango de tiempo de última actividad es: <br/> <ul><li>Intervalo de 12 horas: 36–48 horas</li><li>Intervalo de 24 horas: 24–48 horas</li></ul></li></ul></td></tr><tr><td>Tiempo de instalación</td><td><p>El tiempo de instalación se calcula de la siguiente manera:</p><p><code>Tiempo de instalación = Hora de llegada del postback - [Promedio del intervalo de última actividad] - [Retraso del postback de iOS]</code></p><ul><li> <code>Postback arrival time</code>:  Hora en la que se recibió por primera vez el postback de iOS directamente desde el dispositivo; generalmente, por la red publicitaria. </li><li> <code>Average last-active range</code> considera el CV y se calcula así:<ul><li>Si CV = 0, se supone que el último rango activo es 0. </li><li>Si CV &gt; 1 o CV = nulo: Usando min_install_time y max_install_time, estos se configuran basándose en el intervalo y la última vez que se detectó al usuario activo en la aplicación.  Por ejemplo, si el intervalo es 12, al ver al usuario por última vez 25 horas después de la instalación, el resultado es [24 + 36] / 2 = 30. </li></ul></li><li> <code>iOS postback delay</code>: [24 + 48] / 2 = 36. Considere que el temporizador de iOS finaliza 24 horas después del último cambio en el CV y el postback se envía entre 0 y 24 horas después. <strong>36 horas es una constante</strong>. </li></ul></td></tr><tr><td>Opciones de configuración</td><td><p>La ventana de actividad se compone de dos configuraciones: duración e intervalos. </p><ul><li>Duración: De 24 a 72 horas con intervalos de 24 horas. Máximo 3 intervalos.</li><li>Duración: De 12 a 72 horas con intervalos de 12 horas. Máximo 6 intervalos.</li></ul></td></tr><tr><td>Impacto de modificar la duración de la ventana de actividad</td><td><ul><li>El postback se envía entre 0 y 24 horas después de que el temporizador de iOS expire. </li><li>Inicialmente, el temporizador de iOS está configurado para finalizar después de 24 horas. </li><li>Si configuras la ventana de actividad en más de 24 horas, el usuario debe estar activo al menos una vez por intervalo para asegurar que el temporizador de iOS no expire.</li></ul></td></tr><tr><td><p>Consideraciones sobre las redes publicitarias</p></td><td><ul><li>La duración predeterminada del temporizador es de 24 horas.</li><li>Puedes establecer una duración distinta, pero antes, verifica con tus socios de red publicitaria si admiten un período diferente al predeterminado. </li><li><span>Al utilizar la ventana de 24 horas, puedes mejorar tus métricas dividiendo el período en 2 intervalos, cada uno de 12 horas. De este modo, sabrás si el usuario continuó usando la aplicación después de las primeras 12 horas. </span></li></ul></td></tr><tr><td>Ejemplo de requisitos de capacidad de rango</td><td>La imagen de esta sección muestra un temporizador de 60 horas con un intervalo de 12 horas. </td></tr><tr><td>Opciones de ventana de actividad flexible</td><td><p>La medición flexible te permite establecer una ventana de actividad más larga con granularidad horaria. Lo mismo ocurre con los ajustes de intervalo. Los ajustes cuentan con las siguientes características:</p><ul><li>Ventana de actividad:<ul><li>Rango: 12-1512 horas (63 días)  </li><li>Granularidad: 1 hora</li></ul></li><li>Intervalos:<ul><li>Rango: <span>Mínimo de 1 hora y cualquier otro múltiplo de la ventana de actividad</span> </li><li>Granularidad de 1 hora</li></ul></li></ul><p>Consideración: La relación entre la ventana de actividad y los intervalos debe ser un número entero.</p><p>Mejores prácticas: No establezcas el intervalo en más de 24 horas, ya que esto reduce la precisión de la estimación del tiempo de instalación.</p></td></tr></tbody></table>

</Accordion>

## Información adicional

<div id="view-cv-mapping" />

<Accordion title="Ver el mapeo de CV">

* Consulta los eventos asignados a un CV seleccionándolo. Los eventos mapeados se muestran debajo de la tabla.
* Descarga la tabla de mapeo de CV como un archivo CSV. Haz clic en **Descargar archivo de mapeo.**
* Obtén el mapeo de CV utilizando la <Anchor target="_blank" href="/marketers/es/docs/skan-cv-schema-api-for-advertisers">API de esquema de CV de SKAN para anunciantes</Anchor>.

<Image alt="SKAN_download_mapping.png" src="https://files.readme.io/62dc60da0001c0eccc96791f3f3320f8ea0bc24db3977af4390643c5a95a5ad3-46095838352401.png" width="2482px" />

#### Columnas del archivo de mapeo CSV

| Columna | Descripción |
| --- | --- |
| id\_aplicación |  |
| valor de conversión | Valor del CV:<ul><li>0-63</li><li>Bajo, medio o alto</li></ul> |
| nombre\_del\_evento |  |
| contador\_de\_eventos\_min | El límite inferior del rango del contador de eventos |
| contador\_máximo\_de\_eventos | <ul><li>El límite superior del rango del contador de eventos.</li><li>En los informes generados por AppsFlyer, el número de eventos se calcula utilizando la siguiente fórmula: Roundup ([min\_event\_counter + max\_event\_counter]) / 2</li></ul> |
| min\_event\_revenue | El límite inferior del rango de ingresos del evento en USD |
| ingresos máx. por evento | <ul><li>El límite superior del rango de ingresos del evento en USD</li><li>En los informes generados por AppsFlyer, los ingresos se calculan utilizando la siguiente fórmula: ([min\_event\_revenue + max\_event\_revenue]) / 2)</li></ul> |
| tiempo mín. post-instalación | El límite inferior, en horas post-instalación, indica cuándo estuvo activo el usuario por última vez en la app. |
| tiempo máx. post-instalación | El límite superior, en horas post-instalación, indica cuándo estuvo activo el usuario por última vez en la app. |
| último cambio de configuración | La fecha en la que guardaste la configuración en SKAN Conversion Studio. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Fórmula de capacidad de valor de conversión">

Como se explicó anteriormente, el número máximo de valores de conversión disponibles es 64. La fórmula siguiente calcula cuántos valores de conversión disponibles usa el modo.

```http
(duración del tiempo de actividad en horas / tamaño del intervalo en horas) * \n(número de rangos de ingresos + 1 ) * \n(número de rangos de eventos in-app + 1 ) * \n(número de pasos en un funnel + 1)
```

Ajusta la fórmula para incluir todos los componentes de medición

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Ejemplos de CV personalizados maximizados">

#### Ejemplo 1

| Componente | Descripción |
| --- | --- |
| Ventana de actividad | <ul><li>Duración: 24 horas</li><li>Intervalo: 24 horas es 1 intervalo</li></ul> |
| Ingresos | <ul><li>Los ingresos se reportan mediante un único evento dentro de la app (en general)</li><li>Rangos de ingresos: 15</li></ul> |
| Dentro de la aplicación | Ninguno |
| Embudo | 3 eventos dentro de la aplicación |

#### Ejemplo 2

| Componente | Descripción |
| --- | --- |
| Ventana de actividad | <ul><li>Duración: 24 horas</li><li>Intervalo: 12 horas son 2 intervalos</li></ul> |
| Ingresos | <ul><li>Los ingresos se reportan clasificados por tipo utilizando 2 eventos distintos dentro de la app</li><li>Rangos de ingresos: 3 (por evento dentro de la app)</li></ul> |
| Conjunto para conversión en la aplicación | 1 evento dentro de la aplicación para medir la conversión; cada uno requiere 1 rango |
| Embudo | Ninguno |

#### Ejemplo 3

| Componente | Descripción |
| --- | --- |
| Ventana de actividad | <ul><li>Duración: 24 horas</li><li>Intervalo: 24 horas es 1 intervalo</li></ul> |
| Ingresos | <ul><li>Los ingresos se reportan mediante un único evento dentro de la app (en general)</li><li>Rangos de ingresos: 3</li></ul> |
| Conjunto para interacción en la aplicación | <ul><li>2 eventos dentro de la aplicación para medir las ocasiones de interacción</li><li>Rangos de ocurrencia: 3 por evento dentro de la aplicación</li></ul> |
| Embudo | Ninguno |

#### Ejemplo 4

| Componente | Descripción |
| --- | --- |
| Ventana de actividad | <ul><li>Duración: 48 horas</li><li>Intervalo: 12 horas divididas en 4 intervalos</li></ul> |
| Ingresos | <ul><li>Los ingresos se reportan mediante un único evento dentro de la app (en general)</li><li>Rangos de ingresos: 7</li></ul> |
| Conjunto para conversión en la aplicación | 1 evento dentro de la aplicación para medir la conversión; requiere 1 rango |
| Embudo | Ninguno |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Ejemplo detallado de medición por prioridad">

En una aplicación de compras, el anunciante quiere enfocar la medición en:

* Acciones de usuarios **no pagadores**
* Ingresos de usuarios **pagadores**

De este modo, el anunciante utiliza CVs para registrar de manera más precisa los ingresos. Estos requisitos de medición se traducen en un conjunto de prioridades como se detalla en la tabla siguiente.

Considera:

* La máxima prioridad siempre es 1.   
  [Práctica recomendada]: **¡Nota**! Los números de prioridad no tienen una correspondencia directa con los CVs. Las asignaciones de CV se muestran en la interfaz de usuario.
* El número máximo de prioridades es 63. El número real disponible depende de la ventana de actividad y de si está activada la Fuente Única de Verdad.
* Cada prioridad consta de un rango de ingresos o un rango de ocurrencias de eventos en la aplicación, o ambos.
* Valores del rango: El valor inferior del límite no se incluye en el rango, pero el valor del límite superior sí se incluye. Por ejemplo, el rango $5-$10 no incluye el valor 5 pero sí incluye el valor 10.

#### Ejemplo de configuración de prioridades de medición

<table><thead><tr><th>Prioridad #</th><th>Rango de ingresos</th><th>Evento en la aplicación</th></tr></thead><tbody><tr><td>1 [Prioridad más alta]</td><td>$5 - $10</td><td>send_recommendation</td></tr><tr><td>2</td><td>$5 - $10</td><td>--</td></tr><tr><td>3</td><td>$0-$5</td><td>send_recommendation</td></tr><tr><td>4</td><td>$0-$5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>añadir_al_carrito</td></tr><tr><td>6</td><td>--</td><td>send_recommendation</td></tr><tr><td>7 [Prioridad más baja]</td><td>--</td><td>añadir_al_carrito</td></tr><tr><td colspan="3">-- Sin valor establecido</td></tr></tbody></table>

La siguiente tabla contiene escenarios de recorrido del usuario. Cada escenario contiene la lista de acciones realizadas por el usuario durante su recorrido y la prioridad determinada por AppsFlyer.

En la tabla:

* Las acciones múltiples se separan utilizando >
* El valor entre paréntesis (), es la prioridad determinada por AppsFlyer una vez que el usuario completa la acción. Usando la prioridad, AppsFlyer actualiza el CV en la aplicación.

#### Escenarios de la experiencia del usuario

| Escenario de la experiencia del usuario | Acciones del usuario y prioridad |
| --- | --- |
| A | add\_to cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Compra de $3 (4) |
| D | Compra de $6 (2) |
| E | Compras de $6 (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="[Legado] Ejemplos de modo fijo">

> 📘 **Nota:**
>
> Los modos fijos no estarán disponibles para nuevas aplicaciones a partir del 23/06/2024. Todas las funcionalidades son compatibles con los modos Custom y SKAN4.

#### Ejemplo A: Medición de ingresos

| Factor | Observaciones |
| --- | --- |
| Escenario | <ul><li>20 usuarios instalan la aplicación y realizan las siguientes compras:<ul><li>9 usuarios, cada uno realiza una compra de $10</li><li>5 usuarios, cada uno realiza una compra de $5</li><li>1 usuario realiza una compra de $1, luego de $3, luego de $5 y finalmente de $1. En total, $10.</li></ul></li><li>Datos de costos proporcionados por la API de la red publicitaria: $30</li></ul> |
| Configuración de SKAN | <ul><li>Selecciona el tipo de medición: ingresos</li><li>Establecer factor de conversión: 1 unidad de conversión = $1</li><li>Evento de conversión designado: En el SDK, debes enviar ingresos utilizando el parámetro *af\_revenue*.</li></ul> |
| Métricas seleccionadas | Métricas relacionadas con los ingresos disponibles<ul><li>Instalaciones: 20</li><li>Ingresos: $125</li><li>Conversiones: 15</li><li>ARPU: $6,25</li><li>Retorno de la inversión: 316%</li></ul> |
| Número de filas de datos sin procesar por informe | <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">Los reportes de raw data están disponibles a través de Data Locker</Anchor><ul><li>Postbacks del dispositivo: 20 filas</li><li>Instalaciones: 20 filas</li><li>Eventos dentro de la aplicación: 15 filas. ¡Atención! ¡Nota! El usuario que realiza múltiples compras está representado por una sola fila de $10.</li></ul> |
| Consideraciones para desarrolladores | Se reconocen los eventos que generan ingresos |

#### Ejemplo B: Medición de conversiones

<Table>
  <thead>
    <tr>
      <th>
        Factor
      </th>
      <th>
        Observaciones
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Ejemplo
      </td>
      <td>
        * 5 usuarios (A-E) instalan la aplicación
        * Realizan entre 0 y 3 eventos diferentes dentro de la aplicación, como se muestra en la tabla.
        * Datos de costos proporcionados por la API de la red publicitaria: $30

        #### Eventos dentro de la aplicación realizados por los usuarios

        |  | en la aplicación-1 | en la aplicación-2 | en la aplicación-3 |
        | --- | --- | --- | --- |
        | Usuario A | Realizado | Realizado | - |
        | Usuario B | Realizado | - | Realizado |
        | Usuario C | Realizado | Realizado | - |
        | Usuario D | Realizado | Realizado | - |
        | Usuario E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuración de atribución de SKAdNetwork
      </td>
      <td>
        Selecciona el tipo de medición: Conversión

        * Seleccionar eventos in-app: in-app-1, in-app-2, in-app-3
        * En el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">panel</Anchor> de SKAdNetwork, selecciona uno de los eventos para calcular la métrica de usuarios convertidos. Puedes cambiar el evento seleccionado según sea necesario.
      </td>
    </tr>
    <tr>
      <td>
        Métricas seleccionadas
      </td>
      <td>
        #### Métricas relacionadas con la aplicación disponibles

        | Métrica | Aplicación | en la aplicación-1 | in-app -2 | in-app -3 |
        | --- | --- | --- | --- | --- |
        | Instalaciones | 5 |  |  |  |
        | Conversiones | 4 |  |  |  |
        | Usuarios únicos |  | 4 | 3 | 1 |
        | Costo Efectivo por Adquisición (eCPA) | $7,5 |  |  |  |

        **¡Atención!** ¡Nota! **Dado que el evento de conversión designado es in-app 1, se utiliza el valor 4 para calcular las métricas a nivel de la aplicación y para las métricas in-app-1.**
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">Los reportes de raw data están disponibles a través de Data Locker</Anchor>

        * Postbacks del dispositivo: 5 filas
        * Instalaciones: 5 filas
        * Eventos dentro de la aplicación: 8 filas
      </td>
    </tr>
    <tr>
      <td>
        Consideraciones para desarrolladores
      </td>
      <td>
        * Asegúrate de enviar los eventos dentro de la aplicación que realizan los usuarios.
        * La solución SKAdNetwork no toma en cuenta los valores de los eventos, exceptuando aquellos relacionados con la medición de ingresos.
      </td>
    </tr>
  </tbody>
</Table>

#### Ejemplo C: Medición del compromiso

<Table>
  <thead>
    <tr>
      <th>
        Factor
      </th>
      <th>
        Observaciones
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Ejemplo
      </td>
      <td>
        Cinco usuarios instalan la aplicación y la abren el número de veces indicado en la tabla.

        #### Aperturas de la aplicación

        |  | Número de veces que se realiza el evento |
        | --- | --- |
        | Usuario A | 63 |
        | Usuario B | 10 |
        | Usuario C | 5 |
        | Usuario D | 1 |
        | Usuario E | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuración de atribución de SKAdNetwork
      </td>
      <td>
        * Selecciona el tipo de medición: Engagement
        * Evento de conversión asignado: af\_app\_opened Nota: Puedes utilizar cualquier evento disponible. Puedes utilizar cualquier evento disponible.
      </td>
    </tr>
    <tr>
      <td>
        Métricas seleccionadas
      </td>
      <td>
        Métricas de ejemplo disponibles

        * Instalaciones: 5
        * Conversiones: 4
        * Sesiones: 79
      </td>
    </tr>
    <tr>
      <td>
        Número de filas de datos sin procesar por informe
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">Los reportes de raw data están disponibles a través de Data Locker</Anchor>

        * Postbacks del dispositivo: 5 filas
        * Instalaciones: 5 filas
        * Eventos dentro de la aplicación: 4 filas; una fila equivale a una única sesión  
          Nota: En este ejemplo, hay cuatro filas diferentes porque cuatro usuarios únicos realizaron este evento.  
          Para contar y calcular el número de ocurrencias reales de eventos, las filas tendrán un recuento mínimo y máximo de eventos adjuntos.
      </td>
    </tr>
    <tr>
      <td>
        Consideraciones para desarrolladores
      </td>
      <td>
        Cada vez que el usuario realiza el evento de compromiso seleccionado, envía el evento dentro de la aplicación. SKAdNetwork cuenta cuántas veces envías el evento.
      </td>
    </tr>
  </tbody>
</Table>

<div id="skan-conversion-studio-api" />

<Accordion title="API de SKAN Conversion Studio">

Si tienes muchas aplicaciones para las que deseas configuraciones similares de valores de conversión SKAN, podría ser un desafío y consumir mucho tiempo diseñar el esquema para cada aplicación de forma individual en el interfaz de Conversion Studio. Para ahorrar tiempo y esfuerzo, puedes configurar tu esquema SKAN en el interfaz de usuario una vez y luego utilizar la API de SKAN Conversion Studio para aplicar ese mismo esquema en múltiples aplicaciones. **Nota**: La API solo admite esquemas configurados en la interfaz de usuario usando SKAN 4 o modos de medición personalizados.

**Para utilizar la API de SKAN Conversion Studio**:

1. Obtén el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token API</Anchor>. Un administrador debe recuperar el token.
2. Entrega a tu desarrollador el token API para que lo use en el encabezado de autenticación.
3. Proporciona a tus desarrolladores los ID de las aplicaciones de:
   * La aplicación para la cual está configurado el esquema SKAN en la interfaz de usuario (es decir, la aplicación de la que deseas copiar el esquema SKAN).
   * Todas las aplicaciones que deseas que tengan el mismo esquema.
4. Indica a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">instrucciones de la API de SKAN Conversion Studio</Anchor> en el centro de desarrolladores.

**Nota**:

* La API puede usarse para copiar el esquema a una aplicación por cada llamada API. No obstante, tu desarrollador puede luego crear un script para copiar el esquema necesario a múltiples aplicaciones.
* La API de SKAN Conversion Studio no está disponible para agencias.

</Accordion>

<div id="skan-schema-analysis" />

<Accordion title="Análisis del esquema de SKAN">

Comprende cómo se están utilizando tus valores de conversión, identifica las configuraciones de esquema con bajo rendimiento y perfecciona tu configuración de medición de SKAN basándote en datos de uso reales.

Los insights de distribución de valores de conversión se componen de tres pestañas que te ayudan a optimizar diferentes aspectos de tu esquema de SKAN:

* Pestaña Valores de conversión
* Pestaña de ingresos
* Pestaña Eventos

#### **Pestaña Valores de conversión**

Consulta qué valores de conversión se están usando realmente y cuáles no.

Una distribución equilibrada de valores de conversión asegura que su esquema SKAN capture efectivamente el comportamiento del usuario. Los valores de conversión no utilizados indican combinaciones de medición infrautilizadas, lo que lleva a una capacidad SKAN desperdiciada y oportunidades de optimización perdidas.

* Muestra la frecuencia de cada valor de conversión durante los últimos 7 días de postbacks.
* Destaca los valores que recibieron 0 postbacks.
* Ayuda a optimizar la asignación de valores y a evitar desperdiciar capacidad de medición.
* Especialmente útil para las aplicaciones que utilizan esquemas basados en prioridades.

**Umbral para identificar valores no utilizados**  
✅ Se utilizan todos los CV  
⚠️ Si al menos un CV no tiene postbacks, se muestra este símbolo de error.

#### **Pestaña de ingresos**

Comprueba si tus buckets de ingresos definidos coinciden con el gasto real de los usuarios.

La precisión de los ingresos se puede mejorar optimizando los rangos de ingresos predefinidos de SKAN. SKAN informa el valor promedio de cada rango, que puede no reflejar el gasto real de los usuarios. Los rangos desalineados crean discrepancias, lo que conduce a reportar ingresos de forma inexacta y afecta al ROAS y a la asignación del presupuesto.

El gráfico muestra la distribución de los usuarios de pago entre tus buckets de ingresos definidos. Cuando hay una discrepancia entre el gasto real de los usuarios y los ingresos medios por usuario de pago (ARPPU) reportados, se proporciona una recomendación para revisar el esquema.

* Muestra si tu esquema incluye el mapeo de ingresos.
* Muestra cómo se distribuyen los usuarios de pago entre distintos rangos de gasto.
* Identifica discrepancias entre los ingresos medios por usuario de pago (ARPPU) y el gasto real.
* Sugiere actualizaciones del esquema para mejorar la precisión de los ingresos.
* Si tu aplicación cumple los requisitos para el Modelo de recomendación de ingresos, también se mostrará un cálculo personalizado de precisión del ARPPU basado en tu esquema.

**Umbral de error de informes**

✅ Error de ingresos ≤ 3%

⚠️ Error de ingresos > 3%

#### **Pestaña de eventos**

Asegúrate de que tus eventos mapeados a SKAN se produzcan con la frecuencia suficiente para aportar valor.

Esta pestaña muestra si al menos un evento in-app está mapeado a SKAN.

El gráfico muestra el porcentaje de instalaciones que activaron cada evento mapeado durante la primera ventana de actividad. Se destacan los eventos con baja frecuencia o sin ninguna ocurrencia, lo que te ayuda a garantizar un uso óptimo de tu esquema de conversión.

Asegurarte de que todos los eventos seleccionados ocurran dentro de la primera ventana de actividad evita capacidad de medición sin usar y te ayuda a aprovechar al máximo los valores de conversión disponibles.

* Aparece si al menos un evento está mapeado en el esquema.
* Se oculta si ningún evento mapeado registró instalaciones en los últimos 7 días.
* Muestra el porcentaje de instalaciones que activaron cada evento mapeado durante la primera ventana de actividad.
* Destaca los eventos que ocurren con poca frecuencia o no ocurren en absoluto.
* Ayuda a evitar eventos infrautilizados que desperdician el potencial del esquema.

**Umbral de frecuencia de eventos**

✅ Todos los eventos ≥ 3 % de instalaciones

⚠️ Uno o más eventos < 3 %

</Accordion>

</Accordion>

## Procedimientos adicionales

<div id="change-skan-measurement-mode" />

<Accordion title="Cambiar el modo de medición de SKAN">

Considera:

* Una vez que empieces a utilizar el modo de medición SKAN 4, no es recomendable volver a un modo anterior.
* Al realizar cambios en la configuración, estos comienzan a tener efecto a partir de las 00:00 AM UTC y comienza un período de transición. Durante este período, decodificamos el valor de conversión utilizando las configuraciones más recientemente seleccionadas. Sin embargo, un postback que llega ahora se relaciona con una instalación que ocurrió en el pasado.
* El número de instalaciones reportadas no está relacionado con el cambio de configuración y es preciso.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Desactivar la medición SKAN">

Para desactivar la medición de SKAdNetwork:

1. En AppsFlyer, ve a **Configuración** > **SKAN Conversion Studio.**
2. Haz clic en ⋮.
3. Desactiva la medición de **SKAdNetwork.**   
   Entre otras funciones, el SDK deja de llamar a funciones SKAN como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Haz clic en **Guardar cambios.**

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Reportar eventos mediante API de servidor a servidor">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Tanto el SDK como la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">API de servidor a servidor (S2S)</Anchor> pueden enviar eventos en la aplicación a los servidores de AppsFlyer.

El flujo S2S es el siguiente:

* Ocurre un evento relacionado con el usuario en los servidores del anunciante. La aplicación puede estar abierta o cerrada en ese momento.
* Los servidores de los anunciantes informan del evento a AppsFlyer mediante S2S.
* AppsFlyer calcula el valor de conversión actualizado y luego:
  * Si la aplicación está abierta en el dispositivo del usuario, el SDK es notificado con el valor actualizado. El SDK actualiza el valor de conversión de iOS en el dispositivo.
  * Si la aplicación no está abierta en el dispositivo del usuario, el servidor espera hasta que la aplicación se abra para notificar al SDK del valor de conversión. Esto debe suceder antes de que expire la ventana de actividad. Si la notificación falla, el evento es descartado.

**Versión del SDK requerida**

* Adopte la última versión del SDK en la aplicación. **¡Atención!** No se requiere ninguna acción adicional por parte del desarrollador.

**Para implementar el envío de eventos dentro de la aplicación mediante API de servidor a servidor:**

1. Realice una de las siguientes acciones:
   * Si el modo seleccionado es SKAN 4 o Personalizado:
     * No es necesario realizar cambios en la configuración.
   * Si el modo seleccionado es ingresos, conversión o interacción:
     1. En AppsFlyer, ve a **Configuración** > **SKAN Conversion Studio.**
     2. Haga clic en las opciones (⋮).
     3. Active **Registrar eventos dentro de la aplicación enviados por la API de servidor a servidor**.
2. Envíe eventos mediante S2S.

**Limitación**

* Si implementa la *anonimización de usuario* para un usuario determinado, no podrá enviar eventos por S2S para ese usuario.

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Añadir SSOT a las mediciones de modo fijo">

> 📘 **Nota:**
>
> Los modos fijos no estarán disponibles para nuevas aplicaciones a partir del 23/06/2024. Todas las funcionalidades son compatibles con los modos Custom y SKAN4.

Si tiene configurado el modo de medición de Ingresos o Participación, la Fuente Única de Verdad (SSOT, que deduplica e informa con precisión los datos de iOS) no es compatible. <Anchor target="_blank" href="/marketers/es/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Obtenga más información sobre SSOT</Anchor>

**Para habilitar SSOT cuando tiene configurado el modo Ingresos o Participación**:

1. En AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio**.
2. Desplácese hacia abajo hasta su modo de medición activo.
3. Haga clic en **+ Agregar fuente única de verdad**.
   * La opción Fuente Única de Verdad se activa automáticamente.
   * Los rangos de medición del modo fijo se modifican mínimamente para permitirle a SSOT cierto espacio para valores de conversión.
4. Haga clic en **Guardar**.

<div id="conversion-value-decrease" />

<Accordion title="Disminución del valor de conversión">

En el modo [SKAN 4](/docs/skan-conversion-studio#skan-4), puedes aumentar o disminuir el valor de conversión (CV). Por defecto, el CV está configurado para aumentar. Si permites que los valores de conversión disminuyan, el postback incluirá el último valor de la ventana al enviar ingresos negativos, incluso si antes era mayor. Esta función es relevante tanto para valores de conversión detallados como generales en las [tres ventanas.](/docs/skan-conversion-studio#measurement-principles-and-definitions)   
**Nota:** El valor de los ingresos por anuncios nunca será negativo.

Para habilitar la disminución del valor de conversión:

1. En AppsFlyer, vaya a **Configuración** > **SKAN Conversion Studio**.
2. Selecciona el modo de medición **SKAN 4.0**.
3. Haz clic en las opciones (⋮) para mostrar el menú de opciones y:
   * Asegúrate de que la opción **Permitir disminución de conversión** esté activada.   
     **¡Nota! Esto solo estará disponible para:
     * Aplicaciones guardadas previamente en modo SKAN 4 en el estudio de conversión.
     * Usuarios con acceso de edición**
     * Aplicaciones guardadas previamente en modo SKAN 4 en el estudio de conversión.
     * Usuarios con acceso de edición

#### Ejemplos

**Ejemplos con ingresos negativos**

| CV | Ingresos | Evento en la aplicación |
| --- | --- | --- |
| 3 | $20 - $30 |  |
| 2 | $10 - $20 | af\_add\_to\_cart |
| 1 | $0 - $10 |  |
| 0 | Estados Unidos y Canadá | instalar |

**Ejemplo 1**

El usuario realizó una compra de $5: el CV aumentará a 1.  
 Luego, el usuario realizó una compra de $20: el CV aumentará a 3.  
 Luego, el usuario realizó una compra de -$10: el CV disminuirá a 1.  
 Luego, el usuario realizó un evento de añadir al carrito: el CV aumentará a 2.

**Ejemplo 2**

El usuario realizó una compra de $25: el CV aumentará a 3.  
 Luego, el usuario activó añadir al carrito: el CV se mantendrá en 3.  
 Luego, el usuario realizó una compra de -$20: el CV disminuirá a 1.

**Ejemplo de un esquema dentro de la aplicación**

| CV | Evento en la aplicación |
| --- | --- |
| 3 | af\_compra |
| 2 | af\_add\_to\_cart |
| 1 | sesión |
| 0 | instalar |

**Ejemplo**

El usuario realizó un evento de sesión: el CV aumentará a 1.  
 Luego, el usuario realizó un evento de compra: el CV aumentará a 3.  
 Luego, el usuario realizó otro evento de sesión: el CV se mantendrá en 3.

</Accordion>

<div id="support-anonymized-users" />

<Accordion title="Compatibilidad con usuarios anónimos">

Activar la opción **Admitir usuarios anónimos** asegura que los valores de conversión de SKAN se actualicen con precisión para los <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods#anonimiza-la-información-del-usuario">usuarios anónimos</Anchor>, protegiendo su privacidad.

> 🚧 **¡Importante!**
>
> Esta función es relevante solo para aquellas aplicaciones que utilizan el <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods#anonimiza-la-información-del-usuario">método de anonimización de usuario</Anchor> para eliminar y encriptar toda la información que identifica al usuario. Para asegurar informes precisos por parte de SKAN, estas aplicaciones deben activar la opción **Admitir usuarios anónimos**.

¿Por qué es necesario?  
SKAN utiliza identificadores para actualizar los valores de conversión según la actividad posterior a la instalación. Cuando una aplicación llama al **método de anonimización de usuario** después de iniciar el método, el sistema podría no ser capaz de asociar algunos eventos posteriores a la instalación con la instalación original, provocando actualizaciones inexactas de los valores de conversión.  
Al activar la opción **Admitir usuarios anónimos**, el sistema crea identificadores en hash para todos los usuarios al momento de la instalación. Esto permite que la aplicación asocie correctamente la actividad del usuario con la instalación original, incluso si el usuario se anonimiza posteriormente, asegurando una correcta información.

</Accordion>

</Accordion>

<div id="ssot-mapping-patterns" />

<Accordion title="Patrones de mapeo de SSOT">

Cuando Single Source of Truth (SSOT) está habilitado en tu esquema SKAN, puedes configurar cómo se estructuran los valores de conversión. Esto permite una mejor alineación con tus objetivos de reportes y tus necesidades estratégicas de atribución.

Los patrones de mapeo definen cómo se organizan los valores de conversión (CVs) para representar diferentes tipos de instalación. Estas incluyen instalaciones atribuidas mediante los métodos clásicos de atribución de AppsFlyer e instalaciones no atribuidas.  
AppsFlyer admite dos patrones de mapeo:

#### **Mitad y mitad**

* Divide los CV en dos mitades:
  * La mitad inferior representa niveles crecientes de engagement.
    * Lógica: CV con `af_attribution_flag=false`
  * La mitad superior duplica la mitad inferior, pero marca explícitamente los valores como atribuidos mediante los métodos clásicos de atribución de AppsFlyer.
    * Lógica: duplicados de los CV inferiores con `af_attribution_flag=true`

#### **Emparejamiento**

* Agrupa los CV en pares.
  * A cada CV le sigue inmediatamente otro que representa el mismo nivel de engagement, pero está marcado explícitamente y atribuido mediante la atribución clásica.
  * Garantiza un orden ascendente de los CV y representa de forma coherente niveles crecientes de engagement del usuario
  * Lógica: a cada CV le sigue su duplicado marcado con `af_attribution_flag=true`

#### Cómo configurar los patrones de mapeo

Para usar los patrones de mapeo:

1. Habilita SSOT en tu esquema SKAN.
2. En el editor de esquemas, haz clic en el menú **Más opciones** (tres puntos).
3. Selecciona **Mapping pattern**.
4. Elige el patrón que prefieras:
   * **Mitad y mitad** (predeterminado)
   * **Emparejamiento**
5. Revisa la vista previa del esquema actualizada y la vista de calendario.
6. Guarda tu esquema.

#### **Preguntas frecuentes**

**P: ¿Qué ocurre si SSOT está deshabilitado?**  
R: El selector de patrones de asignación no está disponible cuando SSOT está desactivado.

**P: ¿Puedo volver al patrón predeterminado?**  
A: Sí. **Half-and-half** es el valor predeterminado y se puede volver a seleccionar en cualquier momento.

**P: ¿Estos cambios se reflejan en las API del esquema?**  
A: Sí. Todos los patrones seleccionados se reflejan en las API del esquema SKAN tanto para anunciantes como para redes.

**P: ¿Pueden dos CV tener el mismo evento pero distintas marcas de SSOT?**  
A: Sí. Ahora esto se considera un comportamiento válido según la lógica de validación actualizada.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Especificaciones | Observaciones |
| --- | --- |
| Agencias | Las agencias tienen <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding#acceso-a-skan-conversion-studio">acceso limitado al SKAN Conversion Studio de los anunciantes</Anchor>. |
| Valores aproximados | <ul><li>Hasta 10 componentes de medición.</li><li>Al utilizar más de una medición, deben registrarse todos los eventos para que se codifique el valor de coversión.</li></ul> |
| Eventos orgánicos en la aplicación | En los modos SKAN 4, Custom y Decode, las métricas orgánicas de los eventos in-app y los ingresos globales no están disponibles. |
| Datos ambiguos | Después de cambiar la configuración de SKAN, durante las siguientes 48 a 72 horas, los datos en el panel y los informes sin procesar son ambiguos. Por problemas con el temporizador de iOS, no está claro si la configuración utilizada para decodificar los postbacks coincide con la configuración empleada para codificarlos anteriormente. |
| Restricciones de geolocalización | Es posible que los usuarios cuyo acceso esté limitado a fuentes de medios y geolocalizaciones específicas no puedan ver ni acceder a SKAN Conversion Studio. |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=aspectos-b%C3%A1sicos-del-skan-conversion-studio 01H7Z08MFDASBCBJD18QTXYSXK=aspectos-b%C3%A1sicos-del-skan-conversion-studio 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=principios-s2s 01H7Z08MFDWRGVNXB62Z6CT1G7=principios-s2s setting-up-conversion-values-in-skan-conversion-studio=configuraci%C3%B3n-de-valores-de-conversi%C3%B3n-en-skan-conversion-studio 01H7Z08MFDB76C6Z5SSXHFT71P=configuraci%C3%B3n-de-valores-de-conversi%C3%B3n-en-skan-conversion-studio 01H7Z08MFDEAYHJAG9XA2TGBWV=importante 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes h_01J14HX28C9TFDP0MDRYWFV6Q3=nota fixed-mode-measurement=medici%C3%B3n-en-modo-fijo 01H7Z08MFDAYVJKJBT08R82N26=medici%C3%B3n-en-modo-fijo 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=componentes-de-medici%C3%B3n 01H7Z08MFDFE345QWHF77RGTD7=componentes-de-medici%C3%B3n 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=informaci%C3%B3n-adicional 01H7Z08MFET64PSAVMREQ4HP4S=informaci%C3%B3n-adicional 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=columnas-del-archivo-de-mapeo-csv 01H7Z08MFETCB428W1TXTH2HJ8=columnas-del-archivo-de-mapeo-csv 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=ejemplo-1 01H7Z08MFEXME7RV67XTZRDWJE=ejemplo-1 example-2=ejemplo-2 01H7Z08MFEHRF4656X5AR301D8=ejemplo-2 example-3=ejemplo-3 01H7Z08MFEK0725CN35TP3MPYT=ejemplo-3 example-4=ejemplo-4 01H7Z08MFES7W3EF2JJ8B75K99=ejemplo-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=ejemplo-de-configuraci%C3%B3n-de-prioridades-de-medici%C3%B3n 01H7Z08MFFXAAC37MBV0ES6ADQ=ejemplo-de-configuraci%C3%B3n-de-prioridades-de-medici%C3%B3n user-journey-scenarios=escenarios-de-la-experiencia-del-usuario 01H7Z08MFFJ9TQMH0Q93B7N1A8=escenarios-de-la-experiencia-del-usuario 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples h_01JJH6WZY2QMKAR1C7B5JTMMKE=nota-1 example-a-revenue-measurement=ejemplo-a-medici%C3%B3n-de-ingresos 01H7Z08MFFVKZN3Y2R1ZEVEW4D=ejemplo-a-medici%C3%B3n-de-ingresos example-b-conversion-measurement=ejemplo-b-medici%C3%B3n-de-conversiones 01H7Z08MFFNBA5786R5XZDA5FG=ejemplo-b-medici%C3%B3n-de-conversiones inapp-events-performed-by-users=eventos-dentro-de-la-aplicaci%C3%B3n-realizados-por-los-usuarios 01H7Z08MFFA7C6HWQPADZXQQNC=eventos-dentro-de-la-aplicaci%C3%B3n-realizados-por-los-usuarios inapp-related-metrics-available=m%C3%A9tricas-relacionadas-con-la-aplicaci%C3%B3n-disponibles 01H7Z08MFF1PEE91J5CJN1GC7V=m%C3%A9tricas-relacionadas-con-la-aplicaci%C3%B3n-disponibles example-c-engagement-measurement=ejemplo-c-medici%C3%B3n-del-compromiso 01H7Z08MFF8V718C23PQ2NG3C3=ejemplo-c-medici%C3%B3n-del-compromiso app-opens=aperturas-de-la-aplicaci%C3%B3n 01H7Z08MFF4PRHSR8NCJ1Q78WM=aperturas-de-la-aplicaci%C3%B3n 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api h_01K15P5NJ4CGSH4YR9JXD93PD9=skan-schema-analysis conversion-values-tab=pesta%C3%B1a-valores-de-conversi%C3%B3n h_01K15P7QQSDHNY1ZN3FC37XTHP=pesta%C3%B1a-valores-de-conversi%C3%B3n revenue-tab=pesta%C3%B1a-de-ingresos 01K15PMAQGDZ4SFKEERXVRR0C2=pesta%C3%B1a-de-ingresos events-tab=pesta%C3%B1a-de-eventos 01K15PZK56TVQ6WHGYCA54AA4Q=pesta%C3%B1a-de-eventos additional-procedures=procedimientos-adicionales 01H7Z08MFFPZ4GKM5GFMAE2HDJ=procedimientos-adicionales 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements h_01JJH6WZY2R2H1F9ZBGTR0FDNM=nota-2 h_01HKVT9N2KFJQGCWVMGP59YWRH=conversion-value-decrease examples=ejemplos h_01HM3C8BEG5Z7ZRY12MF3Q4W4K=ejemplos 01JCWF4HM4KKB0WC8MN00SV4XK=support-anonymized-users 01JCWFY9RZ7JSC63TVBTPRCYHH=importante-1 h_01JRFAN7GT7K18ADDAYGVQ4GGT=ssot-mapping-patterns half-and-half=mitad-y-mitad h_01JRFB0793MK8H75T7CGTNPDCK=mitad-y-mitad pairing=emparejamiento h_01JRFB1B9A44CRYVBRTK4CRQGP=emparejamiento how-to-configure-mapping-patterns=c%C3%B3mo-configurar-los-patrones-de-mapeo h_01JRFBAGEZP2GT3XZW4RT255M3=c%C3%B3mo-configurar-los-patrones-de-mapeo faq=preguntas-frecuentes h_01JRFBBYER8QMW5XMBBCWFGDP1=preguntas-frecuentes 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
