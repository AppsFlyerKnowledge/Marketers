---
title: 'Plataforma de Colaboración de Datos (DCP): crea vistas de datos personalizadas'
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
  created_at: '2024-11-22T12:57:55Z'
  edited_at: '2026-08-12T11:53:48Z'
  id: 30296051098897
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/30296051098897
---
> **En resumen:** Crea una vista de datos personalizada a partir de una fuente de datos utilizando funciones de transformación y agregación y una herramienta de filtrado de datos. Puedes obtener una vista previa de una muestra de los datos modificados, que refleja los cambios a medida que avanzas.

<div id="about-data-views" />

## Configurar los detalles generales de la vista de datos

Data View Builder te permite crear una versión personalizada de tu fuente de datos y hacerla relevante para tu audiencia prevista sin modificar el conjunto de datos original. Te permiten realizar funciones que modifican, refinan y resumen los datos para que puedas compartir solo lo relevante, manteniendo los datos que compartes claros y enfocados, y manteniendo todos los demás datos privados y seguros. Diseñado para usuarios no técnicos, no se requieren conocimientos de SQL ni ser experto o ingeniero de datos.

<div id="data-view-functions" />

### Funciones de vista de datos

La herramienta Data View Builder incluye las siguientes funciones:

* **Filtrado:** Reduce los datos aplicando atributos seleccionados, como rango de tiempo, categoría o parámetros personalizados para centrarte en información relevante específica.
* En **Personalizar datos**, haz clic en **Administrar campos**.
  * **Seleccionar campos:** Selecciona la estructura de vista de datos eliminando campos innecesarios o ajustando los tipos de campo.
  * **Agregación:** Combinación de múltiples registros de datos para producir resúmenes o grupos mediante funciones como Suma, Promedio, Recuento, Mínimo y Máximo.
* **Selecciona campos** para incluir solo las columnas que necesitas en tu vista de datos y mantener un resultado limpio y con un propósito claro.

<div id="the-data-view-builder" />

## Data View Builder

**<Image alt="Nueva vista de datos - Predeterminado.png" src="https://files.readme.io/b34b61b2fbc092884270ce0daab9a86deae6b423775bcc648ee0eba6f319e8e5-41945719130897.png" width="1598px" />**

<div id="create-a-data-view" />

## Configurar vista de datos

Para empezar a crear una vista de datos, sigue los pasos a continuación:

**Prerrequisitos**

Una <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">cuenta</Anchor> de AppsFlyer con acceso a DCP.

<div id="set-the-data-view-general-details" />

<Accordion title="1. Configurar los detalles generales de la vista de datos">

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.

   <Image align="center" alt="Haz clic en Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="34.74%" />
2. Desde la pestaña **Fuentes**, mantén el puntero sobre la fuente para crear la vista de datos y haz clic en <Image alt="ellipsis.png" src="https://files.readme.io/d3e33f1864edb1d9d2f8e18c9c7887454018a67e9f7fed054e7134231dba60a2-30296671836433.png" width="0.6%" /> (icono Menú) al final de la fila.
3. Selecciona **Crear vista de datos**. Se te dirigirá a la página de **Vista de nuevos datos**.

   <Image align="center" alt="Crear una vista de datos w arrow.png" src="https://files.readme.io/f9fbcacabb560da996e1dc009e6cd2c5b78d3ccd42e89e2a3c37e71882577e18-41945719135889.png" width="1500px" />
4. Configura los siguientes campos:
   * **Nombre de la vista de datos:** Ingresa un nombre para la vista de datos. Este puede ser cualquier nombre único que te ayude a identificarlo. Consulta los [requisitos y pautas de nomenclatura](#requisitos-y-directrices-sobre-nomenclatura) a continuación.
   * **Descripción:** Proporciona una descripción. Esto aparece como un consejo al pasar el cursor sobre el nombre de la vista de datos en la pestaña **Fuentes**. Se recomienda destacar los objetivos principales y las manipulaciones de datos realizadas.

<div id="naming-requirements-and-guidelines" />

#### Requisitos y directrices sobre nomenclatura

* Asegúrate de que el nombre sea único entre todas las demás fuentes y subfuentes de tu cuenta. De lo contrario, no podrás guardarlo.
* Para las integraciones en la nube, no es necesario que el nombre coincida con el nombre del archivo.
* Requisitos del nombre:
  * Longitud: 2-80 caracteres
  * Caracteres válidos:
    * Letras (A-Z, a-z)
    * Números (0-9), *no pueden ser el primer carácter de un nombre;*
  * Caracteres inválidos:
    * Espacios
    * Guion bajo
    * todos los demás símbolos o caracteres especiales

</Accordion>

<div id="h_01K4SDE8H7R9YZYXMRVXV5GZSV" />

<Accordion title="2. Filtra tus datos">

Puedes aplicar filtros para acotar los datos utilizando atributos seleccionados, ayudándote a centrarte en información específica y relevante.

**Para aplicar filtros:**

1. En **Filtros**, haz clic en **Filtrar datos**.
2. Haz clic en **Seleccionar columna** y selecciona la columna a filtrar.
3. Haz clic en **Operador** > **Igual** o **Diferente**.
4. Introduce un valor.
5. [Opcional] Haz clic en **+ Condición** para agregar una condición al filtro.

> 📘 **Note**
>
> * Puedes agregar tantas condiciones como sea necesario, utilizando las operaciones AND y OR.
> * Se procesan múltiples condiciones según el orden lógico estándar, dando prioridad a las operaciones AND sobre las OR.
> * Cuando uses funciones o filtros en campos de tipo de fecha (columnas), asegúrate de que los valores de fecha se ajusten al formato de fecha admitido específico de la función seleccionada. Cualquier discrepancia puede conducir a elecciones subóptimas entre las opciones proporcionadas.

</Accordion>

<div id="transform-aggregate-and-filter-data" />

<Accordion title="3. Crear campos calculados (opcional)">

Los campos calculados te permiten usar funciones para añadir campos nuevos, cambiar el formato y los valores de los datos, o combinar registros mediante lógica, cálculos o agregación.

**Para crear un campo de transformación o agregación:**

1. Selecciona la pestaña **Transformación** o **Agregado** y haz clic en + **Campo nuevo**.
2. En **Transformar y agregado**, haz clic en **Crear campo**.
3. Haz clic en **Establecer función** y selecciona una función de la [lista de funciones](#list-of-functions-and-use-case-examples). Los campos relevantes para ingresar la información requerida se agregan automáticamente.
4. Para los campos de **agregación** :  La sección **Agrupar por** se abrirá automáticamente y podrás seleccionar el campo que define cómo se agruparán los datos agregados.
5. [Opcional] Haz clic en **+ Campo nuevo** para agregar más campos de **transformación** o **agregación**. Puedes agregar tantas como sea necesario.

<div id="group-by" />

#### **Agrupar por**

Agrupa tus datos en categorías significativas al aplicar una agregación. Cuando añades una función de agregación, la sección Agrupar por se abre automáticamente y te permite seleccionar el campo(s) que determinan cómo se agrupan los datos. Por ejemplo, puedes agrupar los resultados por país, ID de usuario o línea de producto para calcular totales o recuentos de cada grupo.

<Image align="center" alt="Agrupar por.png" src="https://files.readme.io/40fc355847acf7269c6fcd2b505ed182b407d4c668f717612b53c5fd88506443-41967849623057.png" width="58.2%" />

**Para seleccionar los campos por los que agrupar:**   
Haz clic  **+Field** para añadir campos.  
**Nota:** Los primeros campos seleccionados son los identificadores seleccionados en la fuente original.

Una vez creado, el nuevo campo:

* Para los campos de **agregación**:
* Incluido en la lista de campos disponibles para usar en todas las funciones y filtros.
* Incluido en la lista de campos en la sección [Seleccionar campos](#select-fields).

<div id="zd-list-of-functions-and-use-case-examples" />

<div id="list-of-functions-and-use-case-examples" />

#### Lista de funciones y ejemplos de casos de uso

<div id="transformation-functions" />

#### **Funciones de transformación**

* **IF:** Una declaración condicional que ejecuta diferentes acciones en función de si una condición especificada es verdadera o falsa.
* **CONCAT:** Concatenación de dos cadenas
* **CONST:** Devuelve el parámetro de la función CONCAT
* **LEAST:** Devuelve el menor de dos valores
* **GREATEST:** Devuelve el mayor de dos valores

<div id="example-transformation" />

#### **Ejemplo: Transformación**

Quieres indicar los productos comprados al colaborador mientras enmascaras las compras de otras marcas con las que trabajas.

<div id="aggregate-functions" />

#### **Funciones agregadas**

* **COUNT:** Devuelve el número de filas.
* **SUM:** Devuelve la suma de todos los valores.
* **AVG:** Devuelve el promedio de todos los valores.
* **MIN:** Devuelve los valores mínimos de dos números
* **MAX:** Devuelve los valores máximos de dos números

<div id="example-aggregation" />

#### **Ejemplo: Agregación**

Quieres contar la cantidad total de compras por usuario y sumar el precio total que pagaron.

<div id="example-aggregation-with-a-condition" />

#### Ejemplo: Agregación con una condición

Deseas datos sobre las últimas compras realizadas por usuarios ubicados en Alemania y que compraron productos de P&G.

</Accordion>

<div id="select-fields" />

<Accordion title="4. Seleccionar campos">

La estructura de la vista de datos incluye campos de la fuente de datos original y cualquier campo de datos personalizado creado dentro del Data View Builder. Desde aquí puedes eliminar campos (excepto el campo identificador) o reorganizar su pedido.

> 📘 **Note**
>
> * El ajuste del tipo de campo solo se puede realizar desde la fuente original, no desde la vista de datos.
> * Si has creado un campo nuevo que utiliza una función de agregación, los campos disponibles en la selección solo serán los que estén en el apartado **Agrupar por** de la función.
> * Eliminar un campo de los campos seleccionados no afectará a los resultados de la función de agregación.

<div id="adjust-field-types" />

<Accordion title="Ajustar tipos de campo">

Revisa cada campo y selecciona el tipo de datos apropiado de la lista desplegable junto a él para cambiarlo.

</Accordion>

<div id="remove-fields" />

<Accordion title="Eliminar campos">

Puedes eliminar cualquiera de los campos excepto el campo identificador. Si hay varios campos de ID, puedes eliminar todos excepto uno. Una vista de datos debe contener al menos un campo de ID.

**Para eliminar un campo:**

1. Mantén el puntero sobre el lado derecho del campo que deseas eliminar.
2. Haz clic en el icono de la papelera que aparece. El campo ahora aparece en la sección **Eliminado** con un botón **Restaurar** que te permite recuperar el campo eliminado.
3. Haz clic en [Guardar](#save-your-data-view).

</Accordion>

<div id="restoring-temporarily-removed-fields" />

<Accordion title="Restablecer campos eliminados temporalmente">

Cuando se elimina un campo de la lista, se coloca en la sección **Eliminado**. Si no has guardado la vista de datos, puedes restaurarla haciendo clic en el botón **Restaurar**.

</Accordion>

</Accordion>

<div id="save-your-data-view" />

<Accordion title="Paso 5. Revisa y guarda tu vista de datos">

**Panel lateral**

El panel lateral del lado derecho de la página presenta dos conjuntos de datos, uno de la fuente original y otro de la vista de datos creada a partir de ella. Cada conjunto incluye el nombre y la descripción de la tabla, la cantidad de campos y la cantidad de filas, junto con una tabla de muestra que contiene cinco filas de datos. Cuando se aplican funciones y filtros a la vista de datos, el panel lateral refleja estos cambios, lo que te permite verificar los datos mientras los modificas y compararlos con la versión original.

<Image align="center" alt="Vista de datos - panel lateral.png" src="https://files.readme.io/c1dae932618bf2ded68a30853474ce9d6107fdb09541a5d12ac3ddcf4def0101-41945719138577.png" />

Puedes guardar la vista de datos en cualquier etapa. Una vez guardado, se agrega bajo la fuente de datos original en la lista de fuentes y puedes [editarlo, compartirlo o eliminarlo](#guardar-vista-de-datos).

**Para guardar la vista de datos:**

Haz clic en **Guardar** en la parte inferior de la página.

</Accordion>

<div id="h_01JVSEG13462Z4XXD1NE8GW1HE" />

<Accordion title="Paso 6. Comparte tu vista de datos en una colaboración (opcional)">

Puedes <Anchor target="_blank" href="You%20can%20share%20(associate)%20your%20data%20view%20in%20a%20collaboration,%20enabling%20a%20brand%20collaborator%20to%20view%20and%20perform%20actions%20with%20it%20(based%20on%20the%20permissions%20you%20set).">asociar tu vista de datos a una colaboración</Anchor>, lo que permite a los colaboradores de marca verla y realizar acciones con ella (según los permisos que configures).  
**Nota:** Para asociar una vista de datos a una colaboración, debes ser el creador de la colaboración o haber sido invitado a ella.

> 📘 **Note**
>
> Si has creado esta vista de datos para agregar una fuente transaccional para la creación de audiencias, asegúrate de asociarla a la colaboración correspondiente. La vista de datos agregada debe estar asociada a la colaboración antes de que esté disponible como fuente en el Creador de audiencias. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration">Descubre cómo asociar fuentes a una colaboración</Anchor>.

</Accordion>

<div id="use-cases" />

## CASOS DE USO

En esta sección se describen algunos casos de uso habituales de las vistas de datos.

<div id="common-use-cases" />

<Accordion title="Casos de uso comunes">

Las vistas de datos son útiles cuando necesitas adaptar y controlar el acceso a los datos para distintas audiencias o finalidades empresariales. Aquí tienes algunos escenarios habituales:

* **Informes específicos por marca**  
  Si trabajas con varias marcas usando una sola fuente de datos, puedes crear vistas de datos independientes para cada marca y mostrar solo los datos relevantes para cada una. Esto mantiene los datos limpios y centrados, y respeta los límites de privacidad o competencia.
* **Colaboración interna**  
  Comparte vistas personalizadas con distintos equipos, como marketing, producto o ventas, para que cada equipo vea solo los campos y registros relevantes para su trabajo. Esto evita confusiones y garantiza que cada equipo trabaje con el subconjunto de datos adecuado.
* **Uso compartido de datos con clientes**  
  Al compartir reportes o insights con clientes o partners externos, las vistas de datos te permiten excluir información sensible o irrelevante y, al mismo tiempo, ofrecer visibilidad completa sobre los datos que les importan.
* **Filtrado por categoría o región**  
  Puedes crear vistas filtradas por país, línea de producto u otras dimensiones, lo que facilita centrarte en segmentos de mercado o unidades de negocio concretos sin saturar los reportes con datos no relacionados.
* **Resumen de datos**  
  Aplica agregación para resumir métricas clave, como el total de compras por región o la actividad del usuario a lo largo del tiempo, para que tus colaboradores vean insights de alto nivel en lugar de raw data.
* **Preparación de datos transaccionales**  
  Si tu fuente contiene datos transaccionales, como compras, pedidos o eventos con varios registros por usuario, usa una vista de datos para agregarlos en un conjunto de datos a nivel de usuario antes de compartirlo para la creación de audiencias. Esto evita tamaños de audiencia inflados y garantiza resultados de segmentación precisos. Consulta [Uso de fuentes de datos transaccionales](#h_transactional-data-sources) más abajo.

</Accordion>

<div id="transactional-data-sources" />

<Accordion title="Fuentes de datos transaccionales">

Los datos transaccionales hacen referencia a fuentes que contienen varios registros por usuario (por ejemplo, compras, pedidos o eventos). Si trabajas con una fuente de datos transaccionales, debes agregarla en un conjunto de datos a nivel de usuario antes de poder usarla para la creación de audiencias en el Creador de audiencias.

> 📘 **Note**
>
> Cuando abres directamente una fuente de datos transaccionales o se te redirige aquí desde el Creador de audiencias, se muestra un banner que confirma que es necesaria la agregación. La vista de datos agregada también debe estar asociada a la colaboración correspondiente antes de estar disponible como fuente en el Creador de audiencias.

**Por qué es necesaria la agregación**

Los conjuntos de datos transaccionales pueden contener varios registros por usuario. Usarlos directamente en la creación de audiencias puede dar lugar a recuentos de audiencia incorrectos, tamaños de audiencia inflados y resultados de segmentación inesperados. La agregación de los datos produce una fila por usuario, lo que lo hace adecuado para los flujos de trabajo de audiencias.

**Para preparar datos transaccionales para usarlos en Audience Builder, sigue estos pasos:**

1. Crea una vista de datos a partir de la fuente transaccional (consulta [Crear una vista de datos](#configurar-vista-de-datos) más arriba).
2. Aplica funciones de agregación, como Count, Sum, Average, Min o Max, para generar una fila por usuario.
3. Aplica filtros si es necesario para refinar el conjunto de datos.
4. Asocia la vista de datos agregados con la colaboración (consulta el [Paso 6](#h_01JVSEG13462Z4XXD1NE8GW1HE) más arriba).
5. Usa la vista de datos agregados como fuente en Audience Builder.

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Descubre cómo crear audiencias</Anchor>

</Accordion>

<div id="manage-data-views" />

## Guardar vista de datos

Las vistas de datos aparecen en la pestaña **Fuentes**, debajo de la fuente original. Puedes editarlos, eliminarlos o compartirlos con los colaboradores.

<div id="edit-details" />

<Accordion title="Editar vista de datos">

Puedes modificar la descripción de la vista de datos o las etiquetas utilizadas en la descripción.

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la pestaña **Fuentes**, haz clic en el nombre de la fuente. Se muestran las vistas de datos asociadas.
3. Mantén el puntero sobre la vista de datos para modificar y haz clic en [<Image alt="editar-subdominio.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="2.39%" />](/docs/data-collaboration-platform-dcp-create-customized-data-views#share-a-data-view) (icono Editar) al final de la fila.
4. Edita la descripción o las etiquetas aplicadas.

</Accordion>

<div id="delete-a-data-view" />

<Accordion title="Eliminar una vista de datos">

**Para eliminar una vista de datos:**

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la pestaña **Fuentes**, haz clic en el nombre de la fuente. Se muestran las vistas de datos asociadas.
3. Mantén el puntero sobre la vista de datos para modificarla y haz clic en **Eliminar fuente** al final de la fila.

La vista de datos se elimina.

**Detalles:** Nombra y describe la vista de datos

* Los colaboradores pierden acceso a las vistas de datos compartidas con ellos (asociadas) a través de una colaboración.
* Las audiencias basadas en la vista de datos ya no se pueden usar.

</Accordion>

<div id="share-a-data-view" />

<Accordion title="Compartir una vista de datos">

Comparte tu vista de datos con el colaborador y dale permisos.

1. En la plataforma Data Collaboration Platform, ve a la pestaña **Collaborations** > colaboración específica.
2. En el dashboard de la colaboración, haz clic en el menú de acciones en la parte superior derecha > **Fuentes asociadas**.

   <Image align="center" alt="Associate source new UI.png" src="https://files.readme.io/3730b39bb5754260b74632591dffe3fcf54e6c73ff114ba0a8853f277e1e709a-43751907286161.png" width="1539px" />
3. Selecciona tu vista de datos (fuente) en el menú desplegable para asociarla a la colaboración.  
   Haz clic en **Guardar**.
4. **Opcional:** Configura permisos de datos personalizados en la fuente de la vista de datos.

   Puedes configurar permisos personalizados (es decir, distintos de la política general de permisos de datos). **Para configurar permisos de datos personalizados en la fuente de tu vista de datos:**

   En el menú de 3 puntos situado junto a la fuente de la vista de datos, haz clic en **Editar permisos**.  

   <Image align="center" alt="Editar permisos new.png" src="https://files.readme.io/58c785d7fdda52aa159153676d5875e718ceae2f31f987706b79509eb8251151-43752564819985.png" width="1330px" />
5. Selecciona los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#permisos-de-uso-compartido">permisos de uso</Anchor> compartido pertinentes.

> 📘 **Note**
>
> Solo puedes compartir vistas de datos creadas a partir de tus fuentes.

</Accordion>

<div data-zendesk-anchors="overview=configurar-los-detalles-generales-de-la-vista-de-datos 01JD9Z4WKKDWS2EQND0SY7EADZ=configurar-los-detalles-generales-de-la-vista-de-datos data-view-functions=funciones-de-vista-de-datos 01JD9Z4WKMTZ18E13E6V3KZYB3=funciones-de-vista-de-datos the-data-view-builder=data-view-builder 01JD9Z4WKNREMCMB9PNSVVQ024=data-view-builder set-a-data-view=configurar-vista-de-datos 01JD9Z4WKRD4V4A07WT5YG42RZ=configurar-vista-de-datos 01JD9Z4WKWQJJE9Q8EMQY8NCMD=set-the-data-view-general-details naming-requirements=requisitos-y-directrices-sobre-nomenclatura 01JD9Z4WKX3BGN7V9V1V1YBYWT=requisitos-y-directrices-sobre-nomenclatura 01JDEVRX2EV64YQN2JE901CEK8=note 01JD9Z4WM1EQVKS9B4EHMTHW41=transform-aggregate-and-filter-data group-by=agrupar-por h_01KC69N1HAVXE2NVB6DZRJG91N=agrupar-por 01JD9Z4WMDV8B7P8W5E13J7HNJ=list-of-functions-and-use-case-examples transformation-functions=funciones-de-transformaci%C3%B3n h_01JDA45VWKH2ZKVBTK87VFVKTB=funciones-de-transformaci%C3%B3n example-transformation=ejemplo-transformaci%C3%B3n h_01JDA4611HFFEA17352NSNCJYX=ejemplo-transformaci%C3%B3n aggregate-functions=funciones-agregadas h_01JDA467NV99FDAXJCXYSD5PBF=funciones-agregadas example-aggregation=ejemplo-agregaci%C3%B3n h_01JDA46DWD6G3S4S5FM48KWQXA=ejemplo-agregaci%C3%B3n example-aggregation-with-a-condition=ejemplo-agregaci%C3%B3n-con-una-condici%C3%B3n 01JDETVS9XQ9XCNEFVCSC8GAJR=ejemplo-agregaci%C3%B3n-con-una-condici%C3%B3n 01JD9Z4WMJ9XFBXPJAM6RNRP96=select-fields 01JD9Z4WMJJGXG9XXSW6Q6S5KE=note-1 01JD9Z4WMKA2J94AYW9VXKKVKQ=adjust-field-types 01JD9Z4WMM4QQDP749R7H93Z67=remove-fields 01JD9Z4WMNHXCP4Q66C1TN67Y4=restoring-temporarily-removed-fields 01JD9Z4WMQGY8DCEWMPGX8FC2Y=save-your-data-view h_transactional_share_note=note-2 use-cases=casos-de-uso h_01JVSHYGNEFEKP713NNYSSZPS2=casos-de-uso h_01JVSHX282XSCWMN2JRZJ593KN=common-use-cases h_01KT964QX4EW74REN13T1TBKGN=transactional-data-sources h_transactional_banner_note=note-3 manage-data-views=guardar-vista-de-datos 01JD9Z4WMRFS0S408ZJ2YKBZF3=guardar-vista-de-datos 01JD9Z4WMT7GG4JV91JE5KAJ4X=edit-details 01JD9Z4WMZGV916XJ77V3NR1HK=delete-a-data-view 01JD9Z4WN3VX56JDWK937D1WXH=share-a-data-view 01JDA2A87RG8V8RZW4EB1B2K56=note-4" />
