---
title: Plataforma de Colaboración de Datos (DCP) - Construir y activar audiencias
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-08-12T11:53:39Z'
  id: 24522739719057
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/24522739719057
---
> **En resumen:** Crea audiencias de alto valor en colaboraciones de DCP con datos compartidos y actívalas en sitios de partners de medios o en servicios en la nube para maximizar el impacto de la campaña.

<div id="about-dcp-audiences" />

## Sobre DCP

El proceso de construir audiencias a partir de un vasto conjunto de datos implica combinar conjuntos de datos para generar datos enriquecidos, que pueden ser aprovechados para alcanzar precisamente a los consumidores que deseas alcanzar. La audiencia puede ser creada utilizando conjuntos de datos combinados de ambas partes o proporcionados solo por una parte. En ambos casos, el colaborador que proporciona los datos otorga permisos y derechos de acceso de acuerdo con los términos acordados. Después de construir la audiencia, puedes enviarla a tus partners de medios para activación o a tu servicio en la nube.

<div id="build-an-audience" />

## Construye tu audiencia

Las siguientes herramientas están disponibles para construir tus audiencias:

* **Constructor visual de audiencias:** El constructor visual de audiencias es una herramienta fácil de usar que permite a los usuarios no técnicos crear segmentos de audiencia sin necesidad de habilidades en SQL. Permite una segmentación avanzada de audiencias utilizando una interfaz gráfica.
* **Creador de audiencias SQL:** Una consulta SQL que permite consultar los datos sin restricciones. Requiere experiencia en SQL.

<div id="key-features" />

#### Características principales

| Constructor visual de audiencias | Creador de audiencias SQL |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>Soporta el uso de una fuente de cada parte colaboradora o múltiples fuentes de un colaborador | Soporta múltiples fuentes de ambas partes |
| <span id="supports-using-overlapping-data-only"></span>Para una fuente de cada colaborador, solo soporta el uso de datos superpuestos | Soporta consultar todos los datos |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>Soporta recuperar valores dentro del rango de atributos seleccionados. | Admite consultar valores más allá del rango de atributos |

Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">preparar los datos de origen</Anchor> para maximizar las tasas de coincidencia entre los conjuntos de datos de los colaboradores.

<div id="visual-audience-builder" />

<Accordion title="Constructor visual de audiencias">

**Sigue los pasos a continuación para construir tus audiencias utilizando el Constructor de Audiencias Visual:**

> 📘 **Note**
>
> Asegúrate de tener el permiso de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">Construir audiencias</Anchor> para crear una audiencia.

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.

   <Image align="center" alt="Haz clic en Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="245px" />
2. Desde la pestaña **Colaboraciones**, haz clic en la colaboración relevante.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. En la colaboración, haz clic en **Nueva audiencia** > **Constructor de audiencias visual**.  
   **Nota:** Al menos una fuente debe estar asociada antes de que puedas construir una audiencia./strong>

   <Image align="center" alt="New Aud Visual audience builder.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. Procede con los pasos del viaje del **Constructor de audiencias** a continuación:

<div id="step-1-details-and-sources" />

#### Paso 1: Detalles y fuentes

La audiencia se puede crear utilizando datos de un solo colaborador o fusionando una fuente de cada colaborador para habilitar una fuente de datos combinada.

<Image align="center" alt="Nueva aud.png" src="https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png" />

1. **Nombre de audiencia:** Nombra la colaboración de audiencia.
2. **Seleccionar fuentes:** Selecciona una fuente de la lista desplegable:
   * Para una colaboración unilateral: selecciona tu propia fuente o la fuente de tu colaborador.
   * Select a media partner connection.png

     > 📘 **Advertencia**
     >
     > * **Nota:** Cuando ambas fuentes comparten usuarios en común, el panel derecho muestra un resumen de la intersección de fuentes, proporcionando un conteo estimado de usuarios comunes a ambas fuentes.
     > * Las fuentes de datos transaccionales no estarán disponibles en el menú desplegable de origen. Consulta [Trabajo con fuentes de datos transaccionales](#trabajar-con-fuentes-de-datos-transaccionales) más abajo.

3. **Método de combinación de datos:** Selecciona de qué datos deseas construir la audiencia:
   * **Usuarios en común** - Incluye solo usuarios que aparecen en ambas fuentes (la tuya y la de tu colaborador).
   * **Usuarios solo de mi fuente** - Incluye solo usuarios de tu fuente. Excluye a todos los usuarios que aparecen en la fuente de tu colaborador.
   * **Usuarios solo de la fuente del colaborador** - Incluye solo usuarios únicos de la fuente asociada de tu colaborador. Excluye a todos los usuarios que aparecen en tu fuente.  

     **Nota:** Las tres opciones solo estarán disponibles si los permisos de la fuente tienen "**Construir Audiencias**" > "**Pueden usar todos los datos** - **Conjunto de datos universal**" habilitados. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#permisos-de-uso-compartido">Saber más sobre los permisos de la fuente</Anchor>  

     <Image align="center" alt="can use all data permision enabled w arrow.png" src="https://files.readme.io/6f386c2383c75bf42da6cfdc4d662be0fdf7d623588480825e4a70f453d1f94c-46848627186065.png" width="1556px" />
4. Haz clic en **Siguiente**.

<div id="step-2-define-the-audience" />

#### Paso 2: Definir la audiencia

Después de seleccionar las fuentes de datos, este paso implica elegir qué atributos y valores incluir en tu audiencia.

1. Haz clic en **Seleccionar columna** para ver la lista de atributos de las fuentes.
2. Selecciona un atributo, operador y valor de atributo.
   * **Atributos numéricos y de fecha** se pueden filtrar con los operadores:  
     Iguales, Diferentes, Mayor que, Menor que, Mayor o igual que,  
     Menor o igual que, Entre, Últimos "X" días (también puede incluir el día actual)
   * **Atributos de texto** se pueden filtrar con los operadores:  
     Iguales o Diferentes

     > 📘 **Nota**
     >
     > * Si no se selecciona un atributo, todos los atributos se incluyen por defecto.
     > * Una vez que se seleccionan los valores de los atributos, se ajusta el tamaño de la audiencia.

3. [Opcional] Haz clic en **+ Condición** para agregar otro atributo y seleccionar sus valores.  
   Repite según sea necesario.
4. Haz clic en **Siguiente**.
5. Continúa con el siguiente paso [Enviar la audiencia](#enviar-audiencia-para-activación) para activar la audiencia.

<Image align="center" alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

<div id="summary-right-side-preview-pane" />

#### Resumen (panel de vista previa de la derecha)

El panel Resumen se actualiza en tiempo real a medida que defines tu audiencia. Proporciona un **rango estimado de usuarios únicos** que se pueden activar, en función de los identificadores disponibles en las fuentes de datos seleccionadas y su solapamiento.  
Como la activación de la audiencia depende de qué identificadores usan los partners de medios en el momento de la ejecución, el tamaño de la audiencia se muestra como un rango en lugar de como un único número.

**Filas de fuente vs. usuarios únicos**

Los datos de origen pueden contener varias filas por usuario.  
Por ejemplo, la misma persona puede aparecer varias veces debido a:

* Varios eventos
* Varios dispositivos
* Varios identificadores (p. ej., CUID, correo electrónico, teléfono)

  Las estimaciones del tamaño de la audiencia en DCP siempre se basan en usuarios únicos, no en filas sin procesar.

**Identificadores y rango estimado de usuarios**

Una sola fuente puede incluir más de un identificador para el mismo usuario (por ejemplo, tanto un CUID como un correo electrónico con hash), ya que distintos partners de medios admiten distintos identificadores y DCP no puede predecir qué identificador se usará durante la activación.

DCP estima el tamaño de la audiencia como un rango mínimo-máximo:

* **Mínimo:** asume el mayor solapamiento posible entre identificadores
* **Máximo:** asume que los identificadores representan a usuarios distintos

La audiencia activada real estará en algún punto dentro de este rango, en función de las capacidades del partner y de la coincidencia de identificadores.

**Cómo entender el panel Resumen:**

**Usuarios totales**  
Muestra el número máximo de usuarios únicos disponibles en todas las fuentes seleccionadas antes de aplicar el solapamiento.

**Filtrar audiencias:** Selecciona filtrar por tus audiencias o aquellas compartidas contigo.

**Conjunto de datos estimado**  
Representa el número estimado de usuarios únicos compartidos entre las fuentes, expresado como:

* Un rango de usuarios
* Un porcentaje de tu contribución de origen

Este grupo determina la audiencia máxima que se puede activar conjuntamente.

**Tamaño estimado de la audiencia**  
El tamaño estimado de la audiencia refleja el rango esperado de usuarios únicos que coinciden con la definición de tu audiencia y que se pueden activar. El rango:

* Tiene en cuenta la duplicación de identificadores
* Tiene en cuenta la superposición entre fuentes (si corresponde)
* Se ajusta dinámicamente a medida que cambian los filtros, las fuentes o las reglas

<Image align="center" alt="image (20).png" src="https://files.readme.io/0ba94f26978e2d3f984bd0c8c2fa8e60159420f5765cff358cdd80d6f05e271c-43432443225489.png" />

> 📘 **Advertencia**
>
> La audiencia activada del lado del partner de medios puede ser menor que la audiencia que envías debido a las distintas tasas de coincidencia de los partners de medios.

<div id="working-with-transactional-data-sources" />

#### Trabajar con fuentes de datos transaccionales

Las fuentes de datos transaccionales, como compras, pedidos o eventos que contienen varios registros por usuario, no se pueden usar directamente en el creador visual de audiencias. Esto se debe a que usar datos transaccionales sin agregación puede dar lugar a recuentos de audiencia incorrectos, tamaños de audiencia inflados y resultados de segmentación inesperados.

Para usar datos transaccionales para la creación de audiencias, primero debes agregarlos en un conjunto de datos de nivel de usuario mediante la herramienta Data View. **Para agregar:**

1. Abre la herramienta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-customized-data-views">**Data View**</Anchor> y crea una Data View a partir de la fuente transaccional.
2. Aplica funciones de agregación (como Count, Sum o Average) para generar una fila por usuario.
3. Asocia la Data View agregada con la colaboración.
4. Usa la Data View agregada como tu fuente en el Creador de audiencias.

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-customized-data-views#transactional-data-sources">Descubre cómo agregar datos transaccionales con una Data View</Anchor>

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="Creador de audiencias SQL">

Sigue los pasos a continuación para construir tu audiencia utilizando el creador de audiencia SQL.

<div id="note-4" />

> 📘 **Note**
>
> Asegúrate de tener el permiso de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">Construir audiencias</Anchor> para crear una audiencia.

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.

   <Image align="center" alt="Haz clic en Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="40.57%" />
2. Desde la pestaña **Colaboraciones**, haz clic en la colaboración relevante.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. En la colaboración, haz clic en **Nueva audiencia** > **creador de audiencia SQL**.

   <Image align="center" alt="New Aud SQL audience builder.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. Procede con los pasos del viaje del **Generador de audiencia**:

<div id="set-details" />

#### Establecer detalles

Nombra la audiencia y haz clic en **Siguiente**.

<div id="build-query" />

#### Construir consulta

1. Haz clic en el editor para abrir el [creador SQL](#sql-audience-builder).
2. Escribe tu consulta SQL para construir tu audiencia. Puedes usar fuentes unidas o de un solo lado.

<div id="note-5" />

> 📘 **Advertencia**
>
> Si tu consulta incluye una fuente de datos transaccional, debe incluir lógica de agregación, como COUNT, SUM, AVG, MIN o MAX, para reducir los datos a una fila por usuario antes de poder usarla para la creación de audiencias. No se admiten las consultas que usan datos transaccionales sin agregación. Consulta [los patrones de consulta compatibles y no compatibles](#datos-transaccionales-en-consultas-sql) a continuación.

3. Haz clic en **Probar** y revisa los resultados de la consulta (audiencia de prueba) que se muestran debajo de la declaración de consulta.
4. Haz clic en **Continuar** y luego en **Siguiente** para proceder con el siguiente paso del recorrido del **Creador de audiencia**, o **Guardar como borrador** y reanudar más tarde.
5. Continúa a [Enviar la audiencia](#enviar-audiencia-para-activación).

<div id="the-sql-audience-builder" />

#### El creador de audiencia SQL

Usa el creador SQL para consultar los datos y crear una audiencia. La siguiente tabla describe las secciones en el generador:

| Sección | Hallazgos clave |
| --- | --- |
| <span id="left-pane"></span>Panel izquierdo | Presenta todas las fuentes disponibles para crear tu audiencia. Esto puede incluir tus fuentes y las que se compartieron contigo. Solo podrás ver las fuentes a las que tienes el <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**Permiso para construir audiencia**</Anchor>.<br /><br />Seleccionar una fuente la expande para revelar las columnas correspondientes. |
| <span id="topmiddle-section-text-editor"></span>Sección superior-media (editor de consultas) | El editor de consultas para escribir tus declaraciones SQL. |
| <span id="bottommiddle-section-context-panel"></span>Sección inferior-media (panel de contexto) | Esta sección muestra dinámicamente detalles basados en el objeto seleccionado del panel izquierdo:<ul><li>**Al seleccionar una fuente:** Muestra los nombres de las columnas ("Nombre del campo") y sus tipos correspondientes ("Tipo").</li><li>**Cuando se selecciona una columna:** Muestra los valores de las columnas ("Valores distintos") y el conteo de filas para cada valor ("Conteo").</li><li>**Después de la ejecución de la consulta:** Muestra una muestra de los resultados de la consulta.<br />**Nota:** Como medida de privacidad, la tabla de resultados no muestra valores encriptados, como correos electrónicos e IDs. Estos valores se muestran como “Restringido”.</li></ul> |
| <span id="right-pane"></span>Panel derecho | Esta sección muestra dinámicamente detalles basados en el objeto seleccionado:<ul><li>**Al seleccionar una fuente:** Muestra los permisos otorgados para la fuente.</li><li>**Mientras escribes la consulta SQL:**<ul><li>Muestra el estado de validez de la consulta en la parte superior derecha de la página. Esto puede incluir cualquiera de los siguientes estados:</li><li>**Listo para ejecutar:** No se encontraron problemas. Puedes probar la consulta y proceder al siguiente paso.</li><li>**Error de sintaxis:** Se detectó un error de sintaxis junto con orientación sobre cómo resolverlo.</li><li>**Error de permiso:** Indica la falta de permisos requeridos, con un tooltip que detalla qué <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">derechos de acceso se proporcionan para la fuente</Anchor>.</li><li>Muestra un **Botón de Prueba** en la parte superior derecha de la página. Una vez que hayas terminado de escribir tu consulta, debes probarla para confirmar la precisión de la audiencia prevista.<br />Haz clic en **Prueba** para probar tu consulta y examinar los resultados.</li></ul></li></ul> |

<div id="transactional-data-in-sql-queries" />

#### Datos transaccionales en consultas SQL

Al trabajar con fuentes de datos transaccionales en el Creador de SQL, se aplican los siguientes patrones de consulta.

**Patrones de consulta compatibles**

| Patrón | Descripción |
| --- | --- |
| <span id="single-transactional-source-with-aggregation"></span>Fuente transaccional única con agregación | Una consulta que agrega una fuente transaccional para obtener una fila por usuario. Por ejemplo, agregar registros de compra para obtener un recuento total de compras por usuario. |
| <span id="transactional-source-joined-to-a-profileuserlevel-source"></span>Fuente transaccional unida a una fuente de perfil o de nivel de usuario | Se permite cuando el lado transaccional se agrega antes de la unión. Por ejemplo, agregar el historial de compras por usuario y, después, unir el resultado a un conjunto de datos de perfil de cliente. |
| <span id="aggregated-transactional-output-in-downstream-joins"></span>Salida transaccional agregada en uniones posteriores | Una vez agregada al nivel de usuario, la salida se puede usar en otras uniones y flujos de trabajo de creación de audiencias, y se trata de forma similar a un conjunto de datos de nivel de perfil. |

**Patrones de consulta no compatibles**

| Patrón | General |
| --- | --- |
| <span id="transactional-source-joined-directly-to-another-transactional-source"></span>Fuente transaccional unida directamente a otra fuente transaccional | No se admiten uniones directas entre dos conjuntos de datos transaccionales, como compras unidas a pedidos. Estas uniones se bloquean antes de la ejecución porque pueden multiplicar registros, producir resultados de audiencias incorrectos y crear expansión transaccional. |
| <span id="nonaggregated-transactional-query"></span>Consulta transaccional no agregada | No se admiten las consultas que usan registros transaccionales directamente, sin agregación. |

</Accordion>

<div id="send-an-audience-for-activation" />

## Enviar audiencia para activación

Después de crear una audiencia, actívala donde pueda impulsar resultados. Selecciona un destino, como partners de medios para el targeting de campañas o un bucket de almacenamiento en la nube para su uso posterior, y DCP actualiza y entrega la audiencia a diario en función de los datos más recientes de la fuente y de los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#permisos-de-uso-compartido">permisos</Anchor>.

* [**Conectar la audiencia a partners de medios**](#h_01J8HNKQ08EVKXA75C9MZB7AW9) - Las plataformas de partners de medios incluyen Meta Ads, Google Ads y muchas más. Conecta tu audiencia a partners de medios cuando quieras ejecutar campañas de pago, remarketing o expansión de públicos similares.
* [**Exportar la audiencia a tus servicios en la nube**](#h_01HZPCCXTT91FQSTSEXN8GS2Y5)- El almacenamiento en la nube se gestiona a través de AppsFlyer Data Locker. Conecta a tu audiencia con servicios en la nube cuando necesites el archivo en modelos BI, CDPs o canales de enriquecimiento interno.

<div id="note-6" />

> 📘 **Note**
>
> * Los datos que se envían para activación son una lista de IDs de usuario. Esta lista se actualiza continuamente y se envía a los destinos seleccionados a diario.
> * Con cada actualización de los datos de origen, la audiencia se reenvía automáticamente a los destinos seleccionados.

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Conectar una audiencia con partners de medios">

Envía la audiencia para activación directamente en tus plataformas de partners de medios preferidas, como Meta Ads y <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google Ads</Anchor>. El sistema reenvía un CSV de IDs de usuario, encriptados automáticamente si el partner lo requiere.

<div id="note-7" />

> 📘 **Note**
>
> * Cuando creas una audiencia con los datos de la fuente de tu colaborador, las opciones de activación que ves dependen de los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-sharing-permissions">permisos</Anchor> que te haya concedido tu colaborador. Durante la activación, solo tendrás disponibles los partners de activación que haya permitido para esa fuente.
> * Si tu colaborador no te concedió permisos para publicar o exportar audiencias, igualmente puedes enviar una solicitud de activación. En este caso, tu solicitud de activación se envía a tu colaborador para que la active por su parte.

**Para conectar la audiencia a partners de medios:**

1. Dentro del generador de audiencias, activa **Conectar audiencias a partners de medios**.  

   <Image align="center" alt="Connect audience to media partners.png" src="https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png" />
2. Haz clic en **+ Conexión de partners**.
3. Si no se establecieron conexiones con partners, crea una nueva conexión con un partners:
   1. Haz clic en **+ Agregar conexión**.
   2. Selecciona el partner de medios relevante (Meta Ads, Google Ads, DV360 o TikTok).
   3. Ingresa un nombre para la conexión.
   4. Haz clic en **Iniciar sesión con [nombre del partner]**. Serás enviado a la página de inicio de sesión del partner. Elige la cuenta para recibir la audiencia. Luego, serás dirigido de vuelta a la ventana de diálogo.
   5. Haz clic en **Seleccionar ID de cuenta** y selecciona el ID de cuenta relevante.
   6. Haz clic en **Guardar**.
4. Haz clic en **Guardar y enviar**.

<Image align="center" alt="image (21).png" src="https://files.readme.io/bb7785936d3e79e18adffe31ca8121b5c0a65392508ef0aea76c7dc75e9ce9eb-43432561109777.png" />

</Accordion>

<div id="export-to-cloud-storage" />

<Accordion title="Exportar a servicios en la nube">

Envía la audiencia directamente a tu bucket de almacenamiento en la nube. Con cada actualización de la audiencia, DCP exporta automáticamente la versión más reciente al destino que hayas seleccionado. También puedes descargar la audiencia como archivo CSV en cualquier momento.

<div id="note-8" />

> 📘 **Advertencia**
>
> Antes de exportar, asegúrate de que tu bucket de almacenamiento en la nube esté configurado y conectado a DCP. Envía a la audiencia a tus servicios en la nube. La audiencia se exporta al servicio en la nube seleccionado utilizando tus <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">conexiones de AppsFlyer Data Locker</Anchor>.

**Export audience to cloud.png**

1. Dentro del generador de audiencias, activa **Exportar audiencias a la nube**.
2. En el menú desplegable **Conexiones de almacenamiento en la nube**, selecciona una conexión existente.
   * Si todavía no tienes una conexión, haz clic en **+ New cloud connection**. El cuadro de diálogo de conexión se abre directamente en esta página, sin salir de DCP. Haz clic en **Guardar y enviar**. La nueva conexión se selecciona automáticamente.
3. [**Descargar CSV**](#export-audience-to-cloud-services): Descarga la audiencia como un archivo CSV.

</Accordion>

<div id="manage-audiences" />

## Gestionar las audiencias

Ver y gestionar las audiencias asociadas con una colaboración.

<div id="access-audience-management" />

<Accordion title="Constructor visual de audiencias">

**Para ver y gestionar las audiencias asociadas con una colaboración:**

1. Puedes ver y gestionar las audiencias asociadas desde la sección **Audiencias** del dashboard de colaboración relevante.
2. [Constructor de audiencias SQL](#sql-audience-builder) (requiere experiencia en SQL)  
   <Image align="center" alt="Audiences section.png" src="https://files.readme.io/8f8170d6848da0158c7db76938bdb4fa64cb3a9702218fe549e6b6e859d64140-small-43777994824977.png" width="2836px" />

**Lo que puedes hacer desde esta página:**

* **Buscar una audiencia:** Busca por el nombre de la fuente o el nombre de la audiencia.
* **Ordenar audiencias:** Ordena las audiencias haciendo clic en cualquiera de los encabezados de columna.
* **Ver detalles de la audiencia:** Ver detalles, como el nombre del colaborador, estadísticas sobre usuarios superpuestos, [estado de la audiencia](#audience-statuses), y ubicación de activación.
* **Más acciones:** Hacer clic en el ícono del menú de 3 puntos de una tarjeta de audiencia abre acciones adicionales disponibles:
  * [**Editar:**](#edit-the-audience-activation-destination) Modifica el destino de activación de la audiencia.
  * **Duplicar:** Crea una copia nueva e independiente de la audiencia.
    * Las fuentes y el método de combinación de datos de la nueva audiencia se mantienen bloqueados (no se pueden cambiar); los filtros y los destinos de activación se mantienen precompletados, pero son totalmente editables.
    * Duplicar está deshabilitado para las audiencias del Creador de audiencias SQL y para las audiencias con el estado "Invalid".
  * **Ver historial de audiencia:** Ve todas las instancias de la activación de la audiencia, con detalles como la conexión y el estado de activación.
  * [**Eliminar:**](#delete-an-audience) Elimina la audiencia.
  * **Pausar:** Evita que la audiencia sea actualizada y reactivada cuando se modifica la fuente de datos.

</Accordion>

<div id="edit-the-audience-activation-destination" />

<Accordion title="Edita el destino de activación de la audiencia">

Mientras construyes una audiencia, puedes guardarla como un borrador y luego volver a ella y editar el destino de activación (dependiendo de tus permisos).

**Para editar el destino de activación de la audiencia:**

1. Desde la pestaña **Colaboraciones**, haz clic en la colaboración relevante.
2. Haz clic en la sección **Audiencias** y localiza la audiencia relevante.
3. Haz clic en el ícono de menú de 3 puntos que aparece al pasar el cursor sobre la audiencia > **Editar**.
4. En “Conectar y exportar” (en la parte inferior de la página de la audiencia), activa lo que sea relevante:

   * [Conectar con partners de medios](#connect-an-audience-to-media-partners)
   * [Exportar audiencia a servicios en la nube](#export-to-cloud-storage)

</Accordion>

<div id="delete-an-audience" />

<Accordion title="Eliminar una audiencia">

Puedes eliminar una audiencia creada en tu cuenta. Hacer esto la elimina permanentemente de tu cuenta.

**Para eliminar una audiencia:**

1. Desde la pestaña **Colaboraciones**, haz clic en la colaboración relevante.
2. Haz clic en la sección **Audiencias** y localiza la audiencia relevante.
3. Haz clic en el ícono de menú de 3 puntos que aparece al pasar el cursor en audiencia > **Eliminar**.
4. Confirma la eliminación.

</Accordion>

<div id="view-audience-statuses" />

<Accordion title="Estados de la audiencia">

Puedes ver los estados de las audiencias asociadas con una colaboración.

<Image align="center" alt="image (26).png" src="https://files.readme.io/5659a3e30aac91226ecf8d1cf08618b698f063d1412522f2c231459fdfc7fb03-43541066537105.png" width="860px" />

Hay varios estados que una audiencia puede tener:

* **Activo:** La audiencia fue enviada con éxito a la(s) plataforma(s) de destino y está disponible para su uso en campañas.
* **Borrador:** La audiencia fue guardada como un borrador (nunca fue conectada, exportada o entregada).
* **Inválido**: Indica que una fuente o vista de datos utilizada para la audiencia ha expirado, ha sido eliminada o retirada de la colaboración.
* **Entrega pendiente:** La audiencia fue enviada al colaborador para activación, y está pendiente de activación.
* **Pausado**: La audiencia ha sido pausada manualmente y no se enviará cuando nuevos datos estén disponibles.
* **Suspendido**: La colaboración y sus audiencias asociadas han sido suspendidas.

También puedes ver el estado de **Historial de carga** de una audiencia.

Para ver el historial de carga:

Haz clic en el menú desplegable junto a la audiencia específica y selecciona **Ver historial**.

<Image align="center" alt="View history doctored .png" src="https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png" />

**Los estados del historial de carga incluyen:**

* **No conectado:** La audiencia fue recibida de un colaborador para activación, pero aún no está conectada.
* **Éxito**: La audiencia fue enviada con éxito a todas las conexiones.
* **Fallo parcial**: La audiencia no pudo ser enviada a una o más conexiones.
* **Error**: Hubo un problema al procesar la audiencia (por ejemplo, debido a datos incompatibles, restricciones de plataforma o errores de plataforma).
* **N/A:** La audiencia está en estado de borrador o pendiente. El estado del historial de cargas no es aplicable.

</Accordion>

<div data-zendesk-anchors="overview=sobre-dcp h_01HWG1P909NHBXC5VF23BDVVPH=sobre-dcp key-features=construye-tu-audiencia h_01HWG5B2MEJH7M8E9BWA3FQFQ2=construye-tu-audiencia 01KFDX0R4BYSTE1V5G7ATQ6FZS=caracter%C3%ADsticas-principales h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=note step-1-join-sources=paso-1-detalles-y-fuentes h_01HWFRRGP99KKGBSQ6QB10RD26=paso-1-detalles-y-fuentes h_01KT94AC4N81MBE0DAT7TX2QA7=advertencia step-2-build-audiences=paso-2-definir-la-audiencia h_01HWFRRPFTCFGEHY1AW8G4VMY4=paso-2-definir-la-audiencia h_01JSEPSRF3FFJJ4S20GJJPJVWF=nota summary-rightside-preview-pane=resumen-panel-de-vista-previa-de-la-derecha h_01KBMPR7BHCTTVE8DR1TCRYAHJ=resumen-panel-de-vista-previa-de-la-derecha h_01KBMPK2HXMZ6YNQMJTST9BD8Y=advertencia-1 h_transactional-data-visual-builder=trabajar-con-fuentes-de-datos-transaccionales working-with-transactional-data-sources=trabajar-con-fuentes-de-datos-transaccionales h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=note-1 step-1-set-details=establecer-detalles h_01HWG9VX0QB3GFZDARAT5QKHV0=establecer-detalles step-2-build-query=construir-consulta h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=construir-consulta h_01KT6SCS53699DZXE4EF92WC44=advertencia-2 the-sql-audience-builder=el-creador-de-audiencia-sql h_01HZM9P2GNCPGJDEA51HCV1Y99=el-creador-de-audiencia-sql h_transactional-data-sql-patterns=datos-transaccionales-en-consultas-sql transactional-data-in-sql-queries=datos-transaccionales-en-consultas-sql send-audience-for-activation=enviar-audiencia-para-activaci%C3%B3n h_01HZMCHKMVXRWK7RXZ7NN65JQX=enviar-audiencia-para-activaci%C3%B3n h_01HZMCRJBBXFEV6JXEHGFXZDZW=note-2 h_01KFG12R13ADFBY4XBDRGE956V=connect-an-audience-to-media-partners h_01HZMDXEEABQRQE8XMZNE86SRF=note-3 h_01KFG12R13R9B6ATHTBTKAVAMX=export-to-cloud-storage h_01KY2FJV90NYBVTQBN6K63K9DS=advertencia-3 manage-audiences=gestionar-las-audiencias h_01HZPWTG23YQ5Y1GAPXT65DK07=gestionar-las-audiencias h_01KFBA379S9ZZAKN7FC7X2S297=access-audience-management h_01KFB4HVDZZ0MA4Q69DXKH4YY7=edit-the-audience-activation-destination h_01KFB4HVDZJ08STDXGA7ZP8MM3=delete-an-audience h_01KFB4HVDZFCJNYG6VVWTWVAQ8=view-audience-statuses" />
