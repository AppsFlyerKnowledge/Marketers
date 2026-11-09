---
title: Guía de Audiences
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-08-12T12:26:08Z'
  id: 115002689186
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Aumenta la eficacia de tus campañas de adquisición de usuarios y de remarketing utilizando Audiences de AppsFlyer para crear y conectar segmentos de audiencia con tus redes de partners.

<Image align="center" alt="Intro_image.png" src="https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png" />

<div id="audiences-basics" />

## Conceptos básicos de Audiences

Audiences de AppsFlyer te permite crear fácilmente segmentos de audiencia y conectarlos con tus canales propios y pagos, para que puedas ofrecer campañas personalizadas para lograr un mejor engagement y rendimiento. Y una vez enviada tu campaña, también podrás ver las métricas de rendimiento en Audiences.

Una audiencia es un segmento de usuarios actuales o anteriores de tu aplicación que cumplen con los criterios específicos que definas. Las audiencias se pueden basar en características personales, comportamiento, actividad in-app, fuente de atribución, ingresos generados, ubicación geográfica, tipo de dispositivo y más.

**Paso 1: Crea tu audiencia en AppsFlyer:** puedes crear una audiencia personalizada desde cero, importar una o seleccionar de nuestra lista prediseñada y totalmente personalizable de "Audiencias sugeridas", que te ahorran tiempo y se basan en las mejores prácticas de la industria.

**Paso 2: Conecta la audiencia:** una vez que hayas creado tu audiencia, el siguiente paso es conectarla a tus partners de medios desde AppsFlyer, que envía identificadores para los miembros de esa audiencia a los partners y crea la audiencia en los sistemas de los partners. Esto les permite ofrecer anuncios específicos solo a estos usuarios. Las audiencias se actualizan y envían automáticamente a los partners una vez al día. Además, puedes cargar una audiencia en servicios de terceros, como los buckets de Amazon S3, o descargarla como archivo CSV directamente desde el dashboard.

Toda la información necesaria para cargar datos de audiencia a un partner anunciante se especifica en una conexión de partner. Puedes tener varias conexiones para un solo partner anunciante (utilizando diferentes cuentas, información de inicio de sesión, etc.) Puedes tener varias conexiones para un solo partner anunciante (utilizando diferentes cuentas, información de inicio de sesión, etc.) Con el fin de permitir el cumplimiento de los requisitos de privacidad de iOS 14.5 y otras consideraciones de privacidad de los usuarios, **Audiences te permite tener un control total para determinar qué identificadores se comparten con los partners**, tanto a nivel cuenta como para cada conexión de partner.

<div id="audience-split-and-incrementality-testing" />

### Pruebas de incrementalidad y división de audiencia

Las pruebas de <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">incrementalidad</Anchor> miden el impacto real de tus campañas con pruebas A/B que miden con precisión el “aumento incremental”, es decir la diferencia entre las conversiones que ocurrieron como resultado de tus campañas de marketing y las que habrían sucedido de todos modos. AppsFlyer Audiences establece el escenario para las pruebas con una función opcional que divide la audiencia entre los partners de medios seleccionados y un grupo de control, para que puedas usar el dashboard de incrementalidad para comprender el verdadero valor de tus campañas.

<div id="get-started" />

## Empezar

Sigue estos pasos para comenzar con Audiencias:

|  | Pasos |
| --- | --- |
| 1 | En AppsFlyer, desde el menú lateral, selecciona **Engage** > **Audiences**.<br /><br />**Nota:** Audiences es una función premium. Si necesitas ayuda para empezar, contacta con tu Customer Success Manager o envíanos un correo a [hello@appsflyer.com](mailto:hello@appsflyer.com) |
| 2 | Establece la <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política</Anchor> del nivel de cuenta para compartir identificadores de usuario con los partners. |
| 3 | Crea una nueva audiencia:<ul><li>[Audiencia personalizada](/docs/audiences-guide#create-a-custom-audience): crea tu audiencia desde cero.</li><li>[Audiencia sugerida](/docs/audiences-guide#create-a-suggested-audience): audiencias prediseñadas y personalizables basadas en las mejores prácticas de la industria.</li><li><Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems">Importar audiencia</Anchor>: importa segmentos de audiencia desde tus sistemas internos (como BI o CRM).</li></ul> |
| 4 | Conecta la audiencia con uno o varios partners de medios. |
| Opcional | [Dividir la audiencia entre partners y un grupo de control](/docs/audiences-guide#audience-split-and-control-groups) |
| Opcional | <Anchor target="_blank" href="/marketers/es/docs/audiences-create-better-audiences-with-user-attribute-data">Importar atributos de usuario</Anchor> |

<div id="create-and-manage-audiences" />

## Crear y gestionar las audiencias

Esta sección describe cómo crear y gestionar audiencias y configurar pruebas de incrementalidad.

<div id="create-a-custom-audience" />

<Accordion title="Crear una audiencia personalizada">

Una audiencia personalizada se construye desde cero utilizando cualquier conjunto de reglas y filtros que desees.

**Para crear una audiencia personalizada:**

1. En AppsFlyer, desde el menú lateral, elige **Engage** > **Audiences**.
2. Haz clic en **Nueva audiencia**.
3. Selecciona **Audiencia personalizada**.  
   Aparecerá la pestaña **Crear**.
4. Ingresa un **nombre de audiencia** único.  
   **Nota:** Los nombres de la audiencia no pueden incluir caracteres especiales (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ } \ | ~) ( ) [ ] { }` \ | ~)
5. Selecciona la plataforma: **Android** o **iOS**.
6. Selecciona el [identificador de usuario](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
7. [Predeterminado] **ID del dispositivo**: Evalúa las reglas únicamente por ID del dispositivo.
8. **ID de cliente**: evalúa las reglas agrupando dispositivos utilizando el CUID. (Usa este método después de verificar que tus datos tienen CUID válidos.)
9. Selecciona **Nuevo conjunto de reglas** o, si deseas agregar los usuarios de una audiencia existente, haz clic en **Audiencia existente** y, a continuación, selecciona la audiencia específica de la lista.
10. Crea la audiencia con la interfaz de usuario como guía. Para obtener información específica sobre las opciones de reglas, consulta [Todo sobre los conjuntos de reglas](/docs/audiences-guide#todo-sobre-los-conjuntos-de-reglas).
11. Combina conjuntos de reglas utilizando los operadores y, o, excluir.
12. A medida que desarrollas tu audiencia, los paneles de la derecha actualizan automáticamente la audiencia estimada y los tamaños de subida por partner.
13. Completa la definición de la audiencia y haz clic en **Siguiente**.  
    Aparece la ventana **Conexión de audiencia**. Aquí es donde [conectas la audiencia a tus partners de medios](/docs/audiences-guide#connect-an-audience-to-media-partners).

<div id="notes" />

> 📘 **Características**
>
> * Puedes tener hasta 100 audiencias personalizadas/sugeridas activas a la vez.
> * Los nombres de audiencia pueden ser visibles en tus sitios de partners de medios conectados. Tenlo en cuenta para no incluir información confidencial.

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="Crear una audiencia sugerida">

Las audiencias sugeridas te permiten explorar y descubrir **segmentos de audiencia listos para usar, basados en las mejores prácticas de la industria.** Puedes seleccionar una audiencia, personalizarla y conectarla con tus redes de partners para realizar campañas de marketing dirigidas de forma óptima.

Elige entre más de 30 audiencias dentro de las **categorías de Adquirir, Activar, Captar, Monetizar y audiencias específicas de la industria.** Las audiencias son 100 % personalizables, por lo que puedes crear la audiencia exacta que necesitas. Las audiencias incluyen:

* Convertir clics en anuncios en instalaciones
* Obtener similares
* Listas de supresión
* Fomentar el registro
* Fomentar la compra
* Monetizar a los compradores
* Y mucho más...

<div id="example-use-case" />

> 📄 **Ejemplo de caso de uso**
>
> Este ejemplo ilustra un caso de uso típico. Supongamos que quieres instar a los usuarios activos de tu aplicación, que aún no han comprado, a realizar su primera compra. Puedes seleccionar a la audiencia "Fomentar la compra" y personalizarla para especificar qué evento define una compra in-app. A continuación, puedes conectar a la audiencia con tus partners y realizar una campaña promocional que les incite a realizar una compra y les lleve a la página de compra de la aplicación.
>
> <Image align="center" alt="Encourage_purchase_image_this_one.jpeg" src="https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg" />

**Para crear una audiencia sugerida:**

1. En AppsFlyer, desde el menú lateral, elige **Engage** > **Audiences**.
2. Haz clic en **Nueva audiencia**.
3. Selecciona **Audiencia sugerida**.
4. Selecciona la aplicación.
5. Explora las distintas categorías y selecciona una audiencia que coincida con tus objetivos.   
   **Nota:** Algunas audiencias requieren que agregues <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">eventos in-app específicos</Anchor> para definir los criterios de la audiencia. Si el <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure#nombres-de-eventos-predefinidos">evento predefinido</Anchor> de AppsFlyer ya se ha configurado en tu aplicación, quedará preseleccionado. Si no, necesitarás seleccionar el evento personalizado apropiado del menú desplegable. <Image alt="Seleccionar_un_evento__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />
6. Haz clic en **Seleccionar y personalizar**.
7. Ingresa un **nombre de audiencia** único.  
   **Nota:** Los nombres de la audiencia no pueden incluir caracteres especiales (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ } \ | ~) ( ) [ ] { }` \ | ~)
8. Selecciona la plataforma: Android o iOS.
9. Selecciona el [identificador de usuario](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
   * [Predeterminado] **ID del dispositivo**: Evalúa las reglas únicamente por ID del dispositivo.
   * **ID de cliente**: evalúa las reglas agrupando dispositivos utilizando el CUID. (Usa este método después de verificar que tus datos tienen CUID válidos.)
10. Si deseas personalizar aún más la audiencia añadiendo [conjuntos de reglas](/docs/audiences-guide#todo-sobre-los-conjuntos-de-reglas) adicionales, puedes hacerlo haciendo clic en **+ Filtro**. Cuando hayas terminado, haz clic en **Siguiente**.   
    Aparece la ventana **Conexión de audiencia**. Aquí es donde [conectas la audiencia a tus partners de medios](/docs/audiences-guide#connect-an-audience-to-media-partners).

<div id="notes-1" />

> 📘 **Característica**
>
> * Acciones en lote
> * Los nombres de audiencia pueden ser visibles en tus sitios de partners de medios conectados. Tenlo en cuenta para no incluir información confidencial.

</Accordion>

<div id="import-an-audience" />

<Accordion title="Importar una audiencia">

Puedes <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems">importar segmentos de audiencia predefinidos</Anchor> desde tus sistemas internos (como BI y CRM) a Audiencias de AppsFlyer, y utilizarlo como punto central para conectar y mantener todos tus segmentos de audiencia con tus partners de publicidad. Además, te permite disfrutar de las funciones de Audiencias, como la coincidencia de identificadores/enriquecimiento de datos y las métricas de campaña conectadas.

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Conectar una audiencia con partners de medios">

Una vez definida tu audiencia, el siguiente paso es conectarla con tus partners de medios.

**Para conectar a tu audiencia con los partners de medios:**

1. Después de definir tu nueva audiencia en la página **Crear** de la audiencia, haz clic en **Siguiente**. Aparece la ventana **Conexión de audiencia**.
2. Haz clic en **+ Conexión de partner**, y luego realiza una de las siguientes acciones:
   * **Para agregar una nueva conexión**, haz clic en **+ Agregar conexión de partner** (consulta la sección [Crear una nueva conexión](/docs/audiences-guide#create-a-new-connection) para obtener instrucciones detalladas).
   * **Para seleccionar entre conexiones existentes:**
     1. Busca la conexión de partner.
     2. Selecciona una o más conexiones existentes.
     3. Haz clic en **Guardar**.  
        Se abre la ventana de conexión de audiencias.
     4. [Opcional] [Dividir una audiencia entre partners y un grupo de control](/docs/audiences-guide#audience-split-and-control-groups)
     5. [Opcional] [Copiar los grupos divididos a S3](/docs/audiences-guide#audience-split-and-control-groups).
3. Haz clic en **Guardar**.  
   Una vez conectada, la audiencia se actualiza y se envía diariamente a los partners.

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="Ejemplo: ID del dispositivo vs CUID">

La evaluación de reglas de audiencia se realiza utilizando un identificador de usuario de la aplicación. Selecciona una opción de:

* [Por defecto] **ID de dispositivo:** El cumplimiento del conjunto de reglas se evalúa utilizando el ID de dispositivo (GAID o IDFA/IDFV). Cuando cumple con el conjunto de reglas, el ID de dispositivo se agrega a la lista de audiencias. **Nota:** El ID de dispositivo se compartirá con los partners solo cuando lo permita tu política de identificadores de usuarios.
* <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">**ID de cliente (CUID)**</Anchor>:
  * El cumplimiento normativo del conjunto de reglas se evalúa agrupando todos los ID de dispositivos asociados con el mismo CUID. Si el grupo cumple con el conjunto de reglas, los ID de dispositivo que componen el grupo se agregan a la audiencia. **Nota**: El CUID en sí no forma parte de la lista de audiencias y no se envía a los partners de medios.
  * Consideraciones de la implementación del CUID
    * Asegúrate de que tus datos están completados con CUID válidos.
    * Los usuarios de aplicaciones (dispositivos) sin CUID se ignoran.
    * Cuando un ID de dispositivo se relaciona con un CUID, los datos históricos de audiencia para el usuario se actualizan de forma retroactiva y se incluyen en las construcciones de audiencia en el futuro. **Nota**: No se realiza ningún cambio en el raw data.
    * Si un ID de dispositivo está asociado a dos CUIDs diferentes, se utiliza el CUID asociado más recientemente.
    * Al construir una audiencia con CUID como identificador, la asociación CUID debe haber sido recibida por AppsFlyer en la instalación (no solo en eventos posteriores a la instalación) para una asociación completa con los dispositivos relevantes y un enriquecimiento exitoso con identificadores de dispositivos (es decir, GAID, IDFA). <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">Saber más</Anchor>

<Image align="center" alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

<div id="example-device-id-vs-cuid" />

> 📄 **Notas relacionadas con eventos in-app :**
>
> Una audiencia de usuarios que gastaron más de 5 $.
>
>
>
> | ID de  <br />publicidad | CUID | Compra $ |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | Ninguno | 50 |
>
>
>
> | Regla evaluada por | ID de dispositivo incluidos en la audiencia | Explicación |
> | --- | --- | --- |
> | ID de dispositivos | B, D | A y C no están incluidos: el gasto fue inferior a 5 $ |
> | CUID | A, B, C | * A y C tienen el mismo CUID (99): el gasto combinado es de 6 $.<br />* D se ignora: no hay CUID |
>
>
>
> **<span id="h_01K0PAQ4SFXBK0TZ3MH07PWN4A"></span>Notas:**
>
> El mismo método para sumar el gasto entre los ID de dispositivo agrupados por CUID, que se muestra en el ejemplo anterior, también se aplica a otros atributos numéricos (por ejemplo, la puntuación).



</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="División de audiencia y grupos de control">

Usa el botón de alternancia que divide la audiencia entre los partners y un grupo de control para establecer sin esfuerzo el escenario para las pruebas A/B y la <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">medición de la incrementalidad</Anchor> para obtener los insights cruciales que necesitas sobre el impacto de la campaña. Cuando está habilitada, la función divide aleatoriamente la audiencia entre tus partners seleccionados y un grupo de control. El grupo de control es la parte de la audiencia que se retiene de los partners y es un requisito necesario para la medición de la incrementalidad. Puedes ajustar cualquiera de los porcentajes de división que desees y deshabilitar o volver a habilitar la división por audiencia.

| Característica | Descripción |
| --- | --- |
| Audiencia dividida | <ul><li>Esta función divide aleatoriamente la audiencia entre tus partners seleccionados y un grupo de control. **Está habilitada de forma predeterminada para los suscriptores de incrementalidad** y se puede desactivar o volver a activar fácilmente en cualquier momento.</li><li>Divide las audiencias por una variedad de razones, como pruebas A/B y medición de la incrementalidad.</li><li>**Nota:** Modificar una asignación dividida existente entre partners causa la redistribución de toda la audiencia. Esto puede afectar negativamente la validez de las pruebas A/B y hará que los experimentos de incrementalidad activos terminen y se reinicien como nuevos experimentos.</li></ul> |
| Grupo de control | Una parte de la audiencia se retiene en un grupo de control, que no se envía a ningún partner:<ul><li>Los grupos de control se utilizan en pruebas A/B y para medir el aumento incremental de tus campañas de marketing.</li><li>El 15 % de la audiencia (o superior) se recomienda para un grupo de control efectivo.</li><li>El porcentaje mínimo del grupo control necesario para ejecutar un experimento de incrementalidad es del 1 %.</li></ul> |
| Enviar una copia de las listas divididas a un bucket S3 | Los archivos CSV que contienen las listas de audiencias divididas y grupos de control se pueden enviar a un bucket S3 de Amazon.<ul><li>**Nota**: Esto no es lo mismo que definir Amazon S3 como un partner conectado.</li><li>Las listas de audiencias se pueden descargar en un archivo CSV. Usa el archivo CSV, por ejemplo, para enviarlo a partners que no están integrados con AppsFlyer.</li></ul> |

**Para dividir a la audiencia y realizar otras acciones de los partners:**

1. En el panel izquierdo de AppsFlyer, ve a **Engage** > **Audiences**.
2. En la pestaña **Audiences**, selecciona la audiencia.
3. Ve a la pestaña **Conectar**.  
   [![audience_split_1200px.png](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png)](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png) La configuración actual muestra:
   * El panel superior derecho muestra la audiencia total estimada y los tamaños de carga (para todos los partners).
   * La parte inferior derecha presenta una visualización de:
     * Tamaño de carga estimado para cada partner
     * Superposición de partners (para audiencias que no están divididas)
4. Realiza cualquiera de las siguientes acciones:

<Table>
  <thead>
    <tr>
      <th>
        Acción
      </th>
      <th>
        Procedimiento
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        Dividir una audiencia entre partners y grupos de control
      </td>
      <td>
        1. Asegúrate de que el botón **Dividir audiencia/Medir impacto incremental** esté habilitado.
           * El total del grupo de control y la división entre partners combinados debe ser del 100 %.
           * Si no deseas incluir el grupo de control en la división: asigna 0 %.
           * A todos los partners conectados se les debe asignar una parte de la división (no asignar a un partner el 0 %).
           * Para ver el total asignado: desplázate hacia abajo; se muestra el porcentaje total dividido.
        2. Ingresa el porcentaje asignado a:
           * **Grupo de control:** se recomienda un 15 % o más.
           * Ingresa un porcentaje dividido por conexión.
           * Desplázate hacia abajo para mostrar la asignación total en porcentaje, y asegúrate de que la asignación total sea del 100 %.
           * Haz clic en **Guardar división**.
           * Haz clic en **Guardar**.
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        Copiar grupos divididos a S3
      </td>
      <td>
        **Para enviar una copia de la lista de audiencias divididas a un bucket S3:**

        1. Haz clic en **Copiar los grupos divididos en S3**.
        2. Selecciona una conexión.
        3. Haz clic en **Guardar**.

        Los archivos se envían utilizando la siguiente estructura de directorio y nombre de archivo:

        * **Directorio**:

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp\
          ```
        * **Nombre de archivo**: el nombre del partner o grupo de control.  
           Nota: Si falla la conexión con el partner y no se carga el archivo, se agregará la palabra **"failed"** al nombre del partner (por ejemplo, *partner\_name\_failed.csv*).
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        Crear y agregar una conexión nueva
      </td>
      <td>
        **Para agregar una conexión nueva:**

        1. Haz clic en **Agregar** **conexión** **de partner.**
        2. Escribe el nombre de la conexión.
        3. Selecciona un partner.
        4. Completa este procedimiento siguiendo las instrucciones en la interfaz de usuario.
        5. Haz clic en **Agregar conexión de partner**.
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        Agregar o eliminar una conexión existente
      </td>
      <td>
        **Para eliminar o agregar una conexión existente:**

        1. Pasa el cursor sobre la conexión del partner.
        2. Haz clic en el icono "Quitar".
        3. Haz clic en **Guardar**.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="Gestionar las audiencias">

**Administra las audiencias desde el dashboard de Audiences:**

1. En el panel izquierdo de AppsFlyer, ve a **Engage** > **Audiences**.
2. Las siguientes opciones están disponibles:

| Opción | Descripción |
| --- | --- |
| <span id="create-a-new-audience"></span>Crear una nueva audiencia | Crear una nueva audiencia |
| <span id="change-audience-settings"></span>Cambiar la configuración de una audiencia | Haz clic en un **nombre de audiencia** y realiza una de las siguientes acciones:<ul><li>En la pestaña **Crear**: ve y cambia conjuntos de reglas.</li><li>En la pestaña **Conectar**: configura la audiencia dividida y las opciones del grupo de control.</li></ul> |
| <span id="actions"></span>Acciones | En el icono <Image alt="3_dots_icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> que aparece a la derecha al pasar el cursor sobre una audiencia en la página principal de Audiences:<ul><li>**Ver historial**: muestra el historial de carga de la audiencia, incluido el tamaño de la audiencia, y la división entre partners.</li><li>**Cargar ahora**: envía la audiencia a los partners conectados.</li><li>**Descargar como CSV**:<ul><li>Genera y descarga la lista de audiencias como archivos CSV que incluyen los identificadores que selecciones. Solo se descargarán los datos que cumplan con tu <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuarios</Anchor>.</li><li>Se genera un archivo para cada partner.</li><li>Los archivos se descargan después del cálculo de la audiencia, que puede tardar un poco después de crear o modificar una audiencia.</li><li>Los archivos descargados tienen un límite de 5 millones de registros. Para archivos más grandes, envía el archivo a un <Anchor target="_blank" href="/marketers/es/docs/audiences-partner-connections#amazon-s3">S3 bucket</Anchor>.</li><li>Solo se actualizará diariamente y se mantendrá actualizada una audiencia que esté conectada a redes de partners. Si la audiencia no está conectada a redes de partners, no se mantendrá actualizada más allá de la fecha de creación de la misma. Si deseas descargar la información más reciente, puedes duplicar la audiencia para volver a crearla (véase más abajo) y, a continuación, descargar el CSV de la audiencia duplicada.</li></ul></li><li>**Duplicar**:<ul><li>Copia la definición de la audiencia.</li><li>Cuando dupliques una audiencia, asígnale un nombre único.</li><li>[Opción] Elimina uno o más de los partners conectados durante la duplicación.</li></ul></li><li>**Calcular ahora**: [Para audiencias importadas] recalcula la cantidad de usuarios de una audiencia. Úsala según sea necesario para actualizar el tamaño de la audiencia si no parece correcto.</li><li>**<span id="pause"></span>Pausar:**</li></ul><ul><li>Al pausar la audiencia, se inactiva para que ya no se calcule ni se cargue a los partners conectados (se conservan los datos de audiencia existentes de los últimos 3 años).</li><li>Puedes pausar las audiencias que no utilizas para mantenerte dentro del número máximo permitido de audiencias activas. Puedes tener hasta 100 audiencias personalizadas/sugeridas activas y hasta 500 audiencias importadas activas a la vez.</li></ul>**Para pausar una audiencia:**<ol><li>Coloca el cursor sobre la audiencia en la página principal de Audiences para que el icono <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> (menú acciones) aparezca a la derecha.</li></ol>![Actions menu.jpg](https://files.readme.io/d7ad8445c7e886ef4669155391419c9bb5538552f9a0bc1dabaa85a4ad819a1e-46335625065873.jpg)<ol><li>Haz clic en el icono y selecciona **Pausar**.</li></ol>Ahora la audiencia está en pausa.<br /><br />También puedes pausar varias audiencias a la vez marcando la casilla junto a las audiencias y luego haciendo clic en **Pausar** que aparecerá en la parte superior derecha.<ul><li>**Eliminar:** elimina permanentemente la audiencia.</li></ul> |
| <span id="bulk-actions"></span>Acciones en lote | Realiza la misma acción en varias audiencias. Para usar acciones en lote, selecciona dos o más audiencias y después selecciona una de las siguientes acciones en lote:<ul><li>**Cargar ahora**</li><li>**Mostrar superposición de audiencias**: muestra la superposición de audiencias entre las audiencias seleccionadas.</li><li>**Eliminar**</li></ul> |

</Accordion>

<div id="all-about-rulesets" />

## Todo sobre los conjuntos de reglas

Aprende a utilizar los conjuntos de reglas para definir tus audiencias.

<div id="audience-segmentation-rulesets" />

<Accordion title="Conjuntos de reglas de segmentación de audiencia">

<Image align="center" alt="audience_segmentation_rulesets.jpg" src="https://files.readme.io/4407da232d372a98afcd30df3a832f6ef38bb55a6b02640587f44c7501b014f2-46335625066897.jpg" />

* Un conjunto de reglas de segmentos de audiencia consiste en una o varias reglas que permiten un filtrado preciso.
* Combina conjuntos de reglas utilizando los operadores y, o, excluir.
* A medida que las reglas se definen y se superponen, el tamaño estimado de la audiencia se muestra en tiempo real.
* Los conjuntos de reglas se pueden duplicar haciendo clic en el icono <Image alt="duplicate_icon.png" src="https://files.readme.io/c4e2321280c4141e70c499adc92837d663fd29942b1c88532c6f2f3327efc400-46335667603729.png" width="17px" />.
* Cuando una audiencia se compone de varios conjuntos de reglas, usa la visualización superpuesta para comprender mejor los segmentos de la audiencia.
* El [identificador de usuario](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) utilizado para evaluar las reglas es el ID de dispositivo [predeterminado] o el ID de usuario de cliente (CUID).

Los ejemplos que siguen ilustran la implementación del conjunto de reglas en varios escenarios.

</Accordion>

<div id="ruleset-examples" />

<Accordion title="Ejemplos de conjuntos de reglas">

<div id="example-location-based-rule" />

> 📄 **Ejemplo: Regla basada en la ubicación**
>
> Usuarios de Nueva York que desinstalaron la aplicación en el último mes
>
> <Image align="center" alt="example_location_based_rule.jpg" src="https://files.readme.io/7ee7e2b9e8f06dc47c93148767fd67d87855a05cd09ba06f2dd2c0ea9dc29607-46335625068817.jpg" />

<div id="example-user-attributes-based-rule" />

> 📄 **Ejemplo: Regla basada en atributos de usuario**
>
> Usuarios que iniciaron la aplicación en los últimos 7 días al menos una vez y cuya arma favorita es una espada.
>
> <Image align="center" alt="example_user_attributes_based_rule.jpg" src="https://files.readme.io/8ab97cdccd2a1b33b671b1f686ca642306197ccf5151ca2ba9836db8ca496d03-46335625073809.jpg" />

<div id="example-revenue" />

> 📄 **Ejemplo: Ingresos**
>
> Usuarios que instalaron la aplicación durante los últimos siete días y gastaron 1 $
>
> <Image align="center" alt="example_revenue.jpg" src="https://files.readme.io/d7768bec78ff5981639da4e1c8e1a3121961464c0a5932bf8f542f27979358a8-46335625074833.jpg" />

<div id="example-owned-media-filter" />

> 📄 **Ejemplo: Filtro de medios propios**
>
> Crea audiencias objetivo que consistan en usuarios que fueron atribuidos a fuentes de medios propias específicas, como redes sociales (excluyendo publicidad pagada), SMS, correo electrónico, recomendaciones, web o códigos QR. También puedes elegir su nivel de granularidad y dirigirte a los usuarios que proceden de una fuente de medios, una campaña, un conjunto de anuncios o un anuncio individual específicos.
>
> Aquí tienes un ejemplo con los usuarios que abrieron la aplicación al menos una vez en los últimos 7 días y cuya instalación se atribuyó a una campaña de correo electrónico específica, así como a conjuntos de anuncios y anuncios específicos.
>
> <Image align="center" alt="Owned_media_example.jpg" src="https://files.readme.io/4b9c076f5299f4f59524a7f816964f4db2c8edd73690aa899e34fcac0d145628-46335667611409.jpg" />
>
> La audiencia se puede utilizar para volver a captar a estos usuarios con mensajes personalizados en medios propios o de pago, o como una lista de exclusión para evitar que vean anuncios irrelevantes o innecesarios al ejecutar campañas.

<div id="example-remarketing" />

> 📄 **Ejemplo: Remarketing**
>
> Uso de clics y visualizaciones para un remarketing eficaz. Para convertir a estos usuarios, debes convencerlos un poco o enviarles un recordatorio amable. Estos usuarios tienen una alta probabilidad de conversión, por lo que el remarketing con ellos puede producir resultados significativamente mejores que la publicidad en segmentos nuevos. Crea audiencias precisas para el remarketing basadas en los datos de clics e impresiones recopilados.
>
> Crea una audiencia de usuarios potenciales que hicieron clic en un anuncio, pero que no instalaron en los últimos dos días.
>
> <Image align="center" alt="example_remarketing.jpg" src="https://files.readme.io/715c42d56c0deffdb4d28acd213f4a5da62de75bbcd6834a927b9226d2fea43e-46335667613329.jpg" />
>
> Estos son usuarios que, en el pasado reciente, estaban lo suficientemente interesados en tu aplicación móvil como para hacer clic en tu anuncio, pero por algún motivo no instalaron la aplicación o la instalaron, pero no la iniciaron. Algunos usuarios solo necesitan un recordatorio (push) para instalarla. Es posible que otras personas necesiten ver más pantallas o funciones en tu aplicación para finalmente convertirse. Por lo tanto, si tienes una creatividad principal que usas en audiencias nuevas, podría ser mejor usar una creatividad diferente para las audiencias que hicieron clic, pero no instalaron.

</Accordion>

<div id="ruleset-filters" />

<Accordion title="Filtros de conjuntos de reglas">

* Un conjunto de reglas consiste en una o varias reglas.
* Hay varias categorías de filtros de conjuntos de reglas como Eventos, Ingresos, Geolocalización, Atribución, Atributos de usuario, Dispositivos y Medios propios.
* Las reglas tienen diferentes parámetros y configuraciones, tal como se indica en la tabla a continuación.

<table><tbody><tr><td colspan="3"><h4><span id="events"></span>Eventos</h4><p><img alt="engagement_filter_with_A___B.jpg" src="https://files.readme.io/ea3063532ff666f6d8a0f90d55c86007d8a54b25017d93ed7bc19e0d727d9193-46335625077777.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Visualizó un anuncio</li><li>Hizo clic en un anuncio</li><li>Instaló la aplicación</li><li>No instaló la aplicación</li><li>Inició la aplicación</li><li>No inició la aplicación</li><li>Desinstaló la aplicación </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Período y frecuencia </p></td></tr><tr><td colspan="3"><h4><span id="in-app-events"></span><span id="inapp-events"></span>Eventos in-app</h4><p><img alt="in-app_event_filter.jpg" src="https://files.readme.io/1bb8a78b3c64ab8e0d01c1e2be63e9bdd00b2be2396335b3a01289b0b0837593-46335625078929.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Realizó el evento [<em>nombre del evento</em>]</li><li>No realizó el evento [<em>nombre del evento]</em> </li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Período y frecuencia </p></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Atributo del evento + valor:</p><ul><li>Es</li><li>No es</li><li>Mayor que</li><li>Menor que</li><li><a href="./audiences-guide#contains-does-not-contain-logic">Obtener similares</a></li><li><a href="./audiences-guide#contains-does-not-contain-logic">Ten en cuenta:</a></li></ul></td></tr><tr><td colspan="3"><p><br /><br /><strong><span id="h_01K5EHGKDPWS16HP9Q7KX9JXFY"></span>Notas sobre eventos in-app</strong><br /></p><ul><li>La lista de eventos in-app se actualiza <a href="./about-data-freshness-and-timezone-support#procesamiento-diario" target="_blank">diariamente.</a> </li><li>Si se selecciona <strong>Realizó el evento</strong> y el evento in-app tiene atributos asociados a este, puedes filtrar por valor de atributo de evento in-app. </li><li><p>Los eventos in-app, de forma predeterminada, están limitados a 100 valores únicos por atributo. Por ejemplo, si el evento es "purchase" y el atributo es "content-type", solo puede haber 100 (o menos) tipos de contenido posibles. Sin embargo, los valores numéricos son ilimitados.<br/>Si hay atributos (parámetros) de eventos in-app y valores que no aparecen en la lista, puedes añadirlos manualmente haciendo clic en <strong>Agregar atributo de evento</strong> &gt; <strong>Agregar elemento</strong>.<br/> </p><p><strong><img alt="Add_item.jpg" src="https://files.readme.io/00d62c7edfa556c3ecb50842003fb64ecde848413f1b81fd100f3da7257bc38e-46335625079825.jpg"/></strong></p></li><li>- Todos los elementos de eventos agregados manualmente deben introducirse solo como tipo de cadena (texto). No deben agregarse valores numéricos y no funcionarán correctamente.</li><li>- Cuando se agrega un elemento de evento manualmente, el "Tamaño estimado de la audiencia" puede no reflejarse con precisión. <br/>Si necesitas que aparezcan más de 100 atributos/valores en la lista, también puedes ponerte en contacto con tu CSM o enviar un correo electrónico a hello@appsflyer.com.</li></ul><h4><span id="contains--does-not-contain-logic"></span><strong><span id="contains-does-not-contain-logic"></span>Lógica de contiene / no contiene:</strong></h4><p><strong>Contiene:</strong> Hace coincidir a los usuarios cuyos valores de atributos del evento contienen una palabra o varias palabra(s) específicas. La coincidencia es parcial y no distingue entre mayúsculas y minúsculas. Por ejemplo, la palabra clave "bag" coincide con atributos como "handbag" o "Bag".</p><p><strong>No contiene:</strong> Hace coincidir a los usuarios cuyos valores de atributos del evento no contienen las palabras especificadas. La lógica de coincidencia también es parcial y no distingue entre mayúsculas y minúsculas.</p><p><br /><br /><strong><span id="h_01K5EH9WVTEX56980MCR81ZAHH"></span>Notas sobre la lógica de Contiene</strong><br /></p><ul><li>Longitud mínima de la palabra clave: 2 caracteres.</li><li>Número máximo de entradas permitidas por regla: 1 palabra clave por condición AND.</li><li>No se admiten atributos formados solo por números y caracteres especiales.</li><li>La compatibilidad multilingüe incluye caracteres acentuados y no latinos (p. ej., é, ü o caracteres coreanos).</li><li>Cuando se utilizan los operadores "Contiene" o "No contiene", el tamaño estimado de la audiencia y el tamaño estimado de la carga no están disponibles. </li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>Ingresos</h4><p><img alt="revenue_filter.jpg" src="https://files.readme.io/e896abde88511e5675074d5e4d995ed810637be8327c7c157ddf65668839fd4a-46335625080209.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Ingresos totales por compras in-app</li><li>Ingresos totales por publicidad</li><li>Ingresos totales </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Es</li><li>Mayor que</li><li>Menor que </li></ul><p><strong>Definiciones:</strong></p><ul><li> <strong>Ingresos totales por compras in-app:</strong> valor total de todos los eventos reportados usando el parámetro <code>af_revenue</code> para un dispositivo/CUID específico</li><li> <strong>Ingresos totales por publicidad:</strong> ingresos totales por publicidad generados por un dispositivo/CUID específico</li><li> <strong>Ingresos totales:</strong> Ingresos totales por compras in-app + Ingresos totales por publicidad</li></ul><p><strong>Notas:</strong></p><ul><li>Para usar los filtros de <strong>Ingresos totales por publicidad</strong> e <strong>Ingresos totales</strong>, la <a href="./roi360-guide-ad-revenue-attribution" target="_blank">Atribución de ingresos por publicidad</a> debe estar implementada en tu cuenta de AppsFlyer.</li><li>Todas las opciones de filtrado de los ingresos se miden en USD.</li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>Geografía</h4><p><img alt="location_filter.jpg" src="https://files.readme.io/62f6144d23ef23070e2d6d8891a420691633a466d1b8d76365b4d82f40c725c6-46335625081361.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Ubicación </li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Es</li><li>No es</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p><strong>Opciones de ubicación</strong></p><ul><li>País</li><li>Estado</li><li>Ciudad</li></ul></td></tr><tr><td colspan="3"><p><strong>Notas relativas a la ubicación:</strong></p><ul><li>Si seleccionas varios países, no podrás seleccionar estados.</li><li>Si seleccionas varios estados, puedes seleccionar ciudades.</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>Medios propios</h4><p><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://files.readme.io/0d15fa734e11164e6e525e26c66291c52144586c8c35dad77a71e471cbf3326d-46335667621649.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Fuente de medios propia</li><li>Campaña en medios propios</li><li>Conjunto de anuncios en medios propios</li><li>Anuncio en medios propios</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Es</li><li>No es</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Valores como:</p><ul><li>Correo electrónico</li><li>SMS</li><li>Web</li><li>Redes sociales (excluyendo la publicidad pagada)</li><li>Códigos QR</li><li>Referencias</li><li>Campañas de medios, conjuntos de anuncios y anuncios específicos</li></ul></td></tr><tr><td colspan="3"><p>Puedes crear audiencias objetivo que consistan en usuarios que fueron atribuidos a fuentes de medios propias específicas. Además, puedes elegir el nivel de granularidad y dirigirte a los usuarios que proceden de una fuente de medios propia, campaña, conjunto de anuncios y/o anuncio individual específicos.</p><p>Utiliza las audiencias que crees para volver a captar a los usuarios con mensajes personalizados en medios propios o de pago, o como listas de exclusión para evitar que vean anuncios irrelevantes o innecesarios al ejecutar campañas de adquisición de usuarios o reengagement.</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>Dispositivo</h4><p><img alt="device_filter.jpg" src="https://files.readme.io/184cd84f83b94c38f53ca5a9ef67a4f2c6ad8f8a78d832f6c7979a2c88f61cb5-46335667623441.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Marca del dispositivo</li><li>Modelo de dispositivo</li><li>Versión de la aplicación</li><li>Versión de SO</li><li>Operador</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Es</li><li>No es </li></ul></td><td> <img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/> Valor seleccionado</td></tr><tr><td colspan="3"><h4><span id="attribution"></span>Atribución</h4><p><img alt="Attribution_filter.jpg" src="https://files.readme.io/c7aee01564562bc7d468d6b2bd59ff3d26a028d19382dfdbc35c3fe700f214e7-46335625087249.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Orgánico</li><li>Reorientación</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Falso</li><li>Verdadero</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>Atributos de usuario</a></h4><p><img alt="user_attribute_filter.jpg" src="https://files.readme.io/add34f52509bf733f10364691e32ab88331a1caee4bbc4627fb665ec3826422d-46335625088145.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><p>Nombre de atributo de usuario</p></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Tipo de cadena<ul><li>Es</li><li>No es</li></ul></li><li>Tipo de número<ul><li>Es</li><li>Es mayor a</li><li>Es inferior a</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/><br/>Para cadena: Selecciona un valor</p><p>Para el número: Introduce un valor</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="Combinar conjuntos de reglas">

**Para combinar un conjunto de reglas con una audiencia existente:**

1. Ve a **Engage** > **Audiences.**
2. Haz clic en **Agregar audiencia**.  
   Aparecerá la pestaña **Crear**.
3. Ingresa un **nombre de audiencia** único.
4. Selecciona la plataforma: **Android** o **iOS**.
5. [Opcional] Selecciona **Configuración avanzada** para seleccionar el [identificador de usuario](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
   * [Predeterminado] **ID de dispositivo**: evalúa las reglas solo por ID de dispositivo.
   * **ID de usuario de cliente**: evalúa las reglas agrupando dispositivos utilizando el CUID. Usa este método después de verificar que tus datos tienen CUID válidos.
6. Haz clic en **Audiencia existente**, y luego selecciona la audiencia específica.
7. Selecciona un operador: y, o, excluir.

**Limitaciones:**

* La audiencia existente debe estar en la misma plataforma (como iOS o Android) que la audiencia nueva.
* No se puede utilizar una audiencia basada en una audiencia existente.
* No se puede utilizar una audiencia importada.

</Accordion>

<div id="create-and-manage-partner-connections" />

## Crear y administrar conexiones de partners

Esta sección describe cómo crear y gestionar conexiones de partners de medios.

<div id="create-a-new-connection" />

<Accordion title="Crear una nueva conexión">

La pestaña **Conexiones** muestra todas las conexiones de tus partners y el estado de cada una. Toda la información necesaria para cargar datos de audiencia a un partner anunciante se especifica en una conexión de partner. Puedes tener varias conexiones para un solo partner anunciante (utilizando diferentes cuentas, información de inicio de sesión, etc.)

**Para agregar una conexión nueva:**

1. Ir a **Engage** > **Audiences > Conexiones**.
2. Haz clic en **+ Nueva conexión**.  

   **Nota:** Si estás creando una nueva conexión de partner desde dentro del creador de audiencias, haz clic en **+ Agregar conexión de partner** en la ventana **Administrar conexiones de audiencias**.
3. Selecciona un **Nombre de partner**.
4. Ingresa un **Nombre de conexión**.  

   **Nota:** Debe ser un nombre nuevo que nunca se utilizó al crear otras conexiones.
5. Completa los campos/datos de inicio de sesión obligatorios para el partner. Algunos partners tienen <Anchor target="_blank" href="/marketers/es/docs/audiences-partner-connections">instrucciones detalladas sobre cómo conectarse.</Anchor>   

   **Nota:** Las credenciales deben ser únicas. Para evitar la creación de conexiones duplicadas, se te bloqueará de crear la nueva conexión si las credenciales ya han sido utilizadas para otra conexión de socio.
6. Selecciona los identificadores de usuarios que autorizas para compartir con este partner.
   * Los identificadores compatibles varían según el partner. Solo aparecerán en la lista los identificadores compatibles con el partner seleccionado.
   * Solo se cargarán los identificadores que cumplan con tu <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuario a nivel cuenta.</Anchor> Verás un mensaje de advertencia si seleccionas un identificador que no está permitido por la política de tu cuenta.  
     <Image align="center" alt="doctored_connection_image.jpg" src="https://files.readme.io/5de138c4a2c2a3f26bebc6bd14d9703408a986dc4f8c53235d4be337784603af-46335625091345.jpg" />
7. Haz clic en **Guardar**. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

</Accordion>

<div id="manage-connections" />

<Accordion title="Gestionar conexiones">

**Para gestionar una conexión existente:**

1. Selecciona un partner.
2. Selecciona una conexión. ![Edit_connection_screen.jpg](https://files.readme.io/8c13e9dc04e98ca959b9ca250ff4954079d71e4ccd4cb2047f9037f31def0aeb-46335625091729.jpg)
3. Realiza cualquiera de las siguientes acciones:

| Opción | Procedimiento |
| --- | --- |
| <span id="change-the-connection-name"></span>Cambiar el nombre de la conexión | **Para cambiar el nombre de la conexión,** edítalo directamente en el campo **Nombre de conexión**. |
| <span id="reconnect"></span>Reconectar | **Para volver a conectar:**<ol><li>Si el estado muestra que la conexión está inactiva, haz clic en **Reconectar**.</li><li>Actualiza las credenciales de conexión o inicia sesión en el partner para volver a autenticar de acuerdo con las instrucciones de la interfaz de usuario.</li></ol> |
| <span id="modify-user-identifiers"></span>Modificar identificadores de usuarios | **Para modificar los identificadores de usuario,** selecciona/deselecciona los identificadores de usuario que autorizas para compartir con este partner. Solo se cargarán los identificadores que cumplan con tu <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuario a nivel cuenta</Anchor>. |
| <span id="delete-connection"></span>Eliminar conexión | **Para eliminar una conexión:**<ol><li>Si hay alguna audiencia conectada, elimínala de la siguiente manera:<ol><li>Selecciona la audiencia.</li><li>La pestaña Conexiones de audiencias se abre en una pestaña nueva.</li><li>Elimina la conexión.</li><li>Cierra la pestaña.</li></ol></li><li>Repite este procedimiento hasta que no haya audiencias conectadas a la conexión.</li><li>Haz clic en **Eliminar conexión**.</li></ol> |

</Accordion>

<div id="dashboard-and-metrics" />

## Dashboard y métricas

Esta sección describe las características y las métricas de la campaña que aparecen en el dashboard.

<div id="audiences-dashboard" />

<Accordion title="Dashboard de Audiences">

<Image align="center" alt="new_dashboard_image_doctored.jpg" src="https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg" />

| Columna | Descripción |
| --- | --- |
| <span id="audience-name"></span>Nombre de audiencia | Nombre de audiencia |
| <span id="size"></span>Tamaño | Todos los usuarios que coinciden con los criterios de audiencia |
| <span id="upload-size"></span>Tamaño de la carga | Tamaño estimado de audiencia disponible para cargar después de aplicar tu <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificador de usuario</Anchor> a nivel de cuenta y los identificadores seleccionados para las conexiones de partners enlazados.<br /><br />**Nota:** El tamaño real en el lado del partner puede ser diferente por varias razones, incluyendo:<ul><li>El proceso de asignación de partners.</li><li>El tamaño de la carga para iOS refleja el número de segmentos enriquecidos basados en IDFVs que pueden incluir IDFAs duplicados. La deduplicación se realiza al subirlo al lado del partner, lo que puede causar discrepancias en el tamaño.</li></ul> |
| <span id="app-name"></span>Nombre de la aplicación | Las aplicaciones a las que se hace referencia en la definición de la audiencia. Estas no son necesariamente las aplicaciones dirigidas por las campañas que utilizan la audiencia. |
| <span id="upload-to"></span>Cargar en | <ul><li>Íconos de partners a los que se envía la audiencia.</li><li><Image alt="SplitAudiences.png" src="https://files.readme.io/85891dd56649980b8324ee9680e8e0d73898dc3f18a66428c147bc689ba08201-46335667629457.png" width="36px" /> indica que la audiencia está dividida entre partners.</li></ul> |
| <span id="incrementality"></span>Incrementalidad | Esta columna se muestra si te suscribes a <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">Incrementalidad.</Anchor> Los estados incluyen:<ul><li>**Pendiente**: período inicial de recopilación de datos (48 horas) a partir de la fecha de inicio de la campaña.</li><li>**Enlazar campaña**: selecciona la(s) campaña(s) relevante(s) para vincular al experimento. Si tenemos una sugerencia de campaña para ti, será preseleccionada (con cualquier sugerencia adicional ordenada por relevancia en la lista desplegable).</li><li>**Activo**: el experimento está en curso.</li><li>**Completado**: el experimento ha finalizado.</li></ul>Al hacer clic en un estado, accederás al dashboard de Incrementalidad. |
| <span id="upload-status"></span>Estado de carga | <ul><li>El estado actual de la carga de la audiencia.</li><li>La sugerencia muestra la fecha y hora de la carga más reciente.</li><li>En caso de falla, haz clic en **Ver detalles** y realiza la acción correctiva de acuerdo con el mensaje de error detallado que se muestra.</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="Métricas de campaña">

<div id="metrics-hash" />

#### hash de métricas

<div id="campaign-metrics-basics" />

#### Conceptos básicos de métricas de campaña

La sección **Métricas de campaña** del dashboard de Audiences muestra datos de las campañas que utilizaron una audiencia para el targeting (ya sea para la inclusión, exclusión o como base de una audiencia similar).

* Usar una audiencia para el targeting (y decidir cómo se usa) es parte de la configuración de las campañas con partners de medios. Los partners de medios varían en cuanto a cómo se pueden utilizar las audiencias.

**Partners compatibles:** actualmente, los datos están disponibles para Anuncios de Meta, Google Ads y Snapchat. La sección **Métricas de campaña** del dashboard solo es visible si tienes audiencias conectadas a partners admitidos.

**Para ver las métricas de la campaña:**

1. Desplázate hasta el extremo derecho del dashboard de Audiences para que la sección **Métricas de campaña** sea completamente visible.
2. Utiliza el selector de fechas para seleccionar el plazo para el que deseas mostrar los datos. (De forma predeterminada, el dashboard muestra los datos de los últimos 7 días).

**Para descargar métricas de campaña** **para el período de tiempo seleccionado:**

1. Haz clic en el botón **Exportar** en la parte superior del dashboard de Audiences.
2. Una vez que se ha generado el archivo, se descarga automáticamente.


<div id="summary-view" />

#### Resumen

La vista de **métricas de campaña** inicial muestra datos de campaña resumidos para cada audiencia:

[<Image align="center" alt="campaign_metrics_summary_view.jpg" src="https://files.readme.io/a7fb8a1909ca9536914822008dc140cb66270d3ff9ceec8d09647a9f81b463ae-46335625093649.jpg" width="433px" />](https://support.appsflyer.com/hc/article_attachments/30621031359377)

| Columna | Descripción |
| --- | --- |
| <span id="campaigns"></span>Campañas | Número total de campañas que utilizaron la audiencia para el targeting durante el período de tiempo seleccionado (las campañas se ejecutan solo con partners admitidos) |
| <span id="campaign-cost"></span>Costo de la campaña | Costo total de estas campañas durante el plazo seleccionado |
| <span id="campaign-revenue"></span>Ingresos de la campaña | Ingresos totales atribuidos a estas campañas durante el plazo seleccionado |

<div id="detailed-view" />

#### Vista detallada

Desde la vista de resumen, haz clic en el icono <Image alt="show_detailed_view_icon.png" src="https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png" width="24px" /> para ingresar a la vista detallada para la audiencia seleccionada. (El icono <Image alt="show_detailed_view_icon.png" src="https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png" width="24px" /> aparece en el extremo derecho de una fila cuando coloca el mouse en cualquier lugar de esa fila).

La vista detallada muestra los datos desglosados por partners y campañas compatibles:

[<Image align="center" alt="campaign_metrics_detailed_view.jpg" src="https://files.readme.io/cee8910e07bdf6707feeda39dd5e480b19b27fad801dd99d501c2c1ceb4bb49d-46335667634193.jpg" />](https://support.appsflyer.com/hc/article_attachments/30621015096593)

Si la audiencia seleccionada se utilizó para el objetivo de más de una aplicación, utiliza la lista desplegable ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png) para filtrar los datos por aplicación.

Haz clic en el enlace **dashboard general** ![pin_B.png](https://files.readme.io/b8c902aab2ca2f748dfe647dab3f52e66f6c161d173cb3cf53dbf4ecdc1edef1-46335667637009.png) para ver las campañas en dicho dashboard:

* El dashboard se abrirá en una nueva pestaña del navegador, filtrado automáticamente por las campañas relevantes.
* Si el **enlace del dashboard general** está deshabilitado, puedes habilitarlo seleccionando una sola aplicación de la lista desplegable![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png). Una vez habilitado el enlace, al hacer clic en él, se accederá al dashboard general de la aplicación seleccionada.

| Columna | Descripción |
| --- | --- |
| <span id="cost"></span>Costo | Costo de la campaña durante el plazo seleccionado (en total, luego desglosado por partners y campaña compatibles) |
| <span id="revenue"></span>Ingresos | Ingresos atribuidos a las campañas durante el período de tiempo seleccionado (en total, luego desglosados por partners y campañas compatibles) |
| <span id="daily-reach"></span>Alcance diario | El número promedio de usuarios únicos por día que vieron anuncios de la campaña durante el período de tiempo seleccionado (según lo informado por el partner) |

<div id="data-sources-and-availability" />

#### Fuentes de datos y disponibilidad

Es más fácil comprender la disponibilidad de los datos de **métricas de campaña** cuando observamos de dónde provienen los datos:

* **Datos del partner:** si seleccionas la(s) audiencia(s) a las que se dirigirán campañas específicas a través de tus partners de medios, solo estos pueden proporcionar cierta información:
  * La conexión de una audiencia con una campaña (en otras palabras, el hecho de que esa campaña utilizó una audiencia en particular para el targeting)
  * La cantidad de usuarios únicos por día que vieron anuncios de la campaña ("alcance diario")
* **Datos de AppsFlyer:** Los datos de costos e ingresos son proporcionados por AppsFlyer.

<div id="partner-data-availability" />

<Accordion title="Disponibilidad de datos de partners">

Los datos se reportan solo para las campañas que se ejecutan con [partners admitidos](/docs/audiences-guide#conceptos-básicos-de-métricas-de-campaña).

* **Nota:** Google Ads no admite la generación de reportes de alcance diario.

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="Disponibilidad de datos de AppsFlyer">

Los datos de costos e ingresos están disponibles en el contexto de las **métricas** de la campaña si se reportan para tus aplicaciones en otras áreas de AppsFlyer (por ejemplo, los paneles de control de información general y eventos).

* Los datos de costos requieren una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">ROI360</Anchor>.
* Los datos de ingresos requieren que hayas configurado la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">atribución de ingresos por publicidad</Anchor> y/o la <Anchor target="_blank" href="/marketers/es/docs/roi360-revenue-attribution-overview">atribución de ingresos de eventos in-app</Anchor>.

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="¿Por qué no veo los datos de las métricas de campaña para las campañas que se ejecutan con partners compatibles?">

Los datos de métricas de campaña solo están disponibles para:

* Campañas que están conectadas a una audiencia.
* Campañas que se ejecutan en sitios de partners de medios compatibles.
* Campañas activas dentro del rango de fechas principal seleccionado.
* Campañas desde las que recibimos el tráfico de instalación, dentro del rango de fechas seleccionado en el filtro de métricas de campaña.
* Usuarios configurados para la conexión de partners que tienen permisos para recibir datos a nivel de campaña. Para ver estos datos, cambia los permisos del usuario con el partner o utiliza diferentes credenciales en la configuración de conexión del partner.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

Ten en cuenta las siguientes características y limitaciones.

<div id="traits" />

<Accordion title="Características">

| Caducado | Compatible | Observaciones |
| --- | --- | --- |
| Redes de publicidad | . |  |
| Agencias | . |  |
| Transparencia de agencias | . |  |
| Zona horaria específica de la aplicación | N/D |  |
| Moneda específica de la aplicación | N/D |  |
| Protección de datos | ✓ | Los datos de tu audiencia pueden procesarse para respaldar las capacidades de Audiences impulsadas por IA. Los datos de tu cuenta nunca se comparten y se utilizan únicamente para mejorar los modelos internos y las predicciones. |
| Limitaciones de tamaño | N/D |  |
| Datos no orgánicos | ✓ | Incluidos |
| Datos orgánicos | ✓ | Incluidos |
| Actualización de datos | Diaria UTC | <ul><li>Las actualizaciones se envían a los partners diariamente</li><li>Las listas de eventos in-app en el creador de reglas se actualizan diariamente.</li></ul> |
| Datos históricos | ✓ | Audiences tiene acceso a los datos de eventos in-app de 90 días antes de la fecha de suscripción de Audiences (para clics e impresiones, es 31 días antes). Los datos están completamente disponibles una vez que se completa el proceso de rellenado (que puede tardar hasta 2 semanas). |
| Acceso de usuario a la cuenta | ✓ | <ul><li>Algunas funciones, como la descarga de CSV, la configuración de S3 y las conexiones de partners de Slack requieren permiso de cuenta de usuario para acceder al raw data.</li><li>Como medida de seguridad, si se ha eliminado la cuenta de un usuario que creó una audiencia, AppsFlyer deja de cargar los datos de esa audiencia a los partners de medios. Para verificar el estado de carga de tus audiencias, ve a **Engage** > **Audiences**. Para reactivar la audiencia, duplícala y configura los ajustes de [audiencia dividida](/docs/audiences-guide#audience-split-and-control-groups).</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="Limitaciones">

| Limitaciones | Observaciones |
| --- | --- |
| Datos de atribución | Los datos de clics e impresiones solo contienen dispositivos que tienen un advertising\_id/idfa en su URL de clic original. Los dispositivos de los usuarios de las SRN, que no utilizan enlaces de atribución externos, no se incluyen en los datos de clics para las audiencias. |
| Creación de audiencia | <ul><li>Los nombres de la audiencia no se pueden cambiar en el lado de los partners conectados.</li><li>Al crear una audiencia, solo se muestran los 100 eventos principales. Sin embargo, cuando comienzas a ingresar un nombre de evento, se muestran todos los eventos.</li><li>Cuando se utiliza el filtro Ingresos totales dentro del creador de query, el tamaño estimado de la audiencia no está disponible. Esto no afecta el proceso de creación de una audiencia.</li></ul> |
| Conexiones | No se admite la creación de conexiones de partners duplicadas (conexiones con la misma cuenta / inicio de sesión / ID de propiedad / etc.) y resultará en errores. |
| Descargar archivo CSV de audiencia | El archivo de descarga tiene un límite de 5 millones de registros. |
| Audiencias importadas | No puedes combinar audiencias importadas con otras audiencias o conjuntos de reglas. |
| Audiencias activas | Las audiencias que estén inactivas se pausarán. Esto significa que ya no se calcularán ni se cargarán a partners conectados. La audiencia siempre se puede “reanudar” haciendo clic en Cargar ahora. Esto reanudará los cálculos y las cargas automáticas de la audiencia a los partners como antes. |
| No compatible | Lo siguiente no es compatible con AppsFlyer Audiences:<ul><li><Anchor target="_blank" href="/marketers/es/docs/audiences-partner-connections#google-ads">Google Ads</Anchor>: Las campañas UAC no son compatibles. Se admiten otros tipos de campaña.</li><li>Windows phone OS</li><li>Valores de eventos anidados</li></ul> |
| Número de audiencias | <ul><li>Puedes crear hasta 100 audiencias por día.</li><li>Puedes tener hasta 100 audiencias personalizadas/sugeridas activas a la vez.</li><li>Puedes tener hasta 500 audiencias importadas activas a la vez.</li></ul> |
| Conjuntos de reglas | <ul><li>Dentro de los conjuntos de reglas, los eventos in-app se limitan a 100 valores únicos por atributo. Por ejemplo, si el evento es "purchase" y el atributo es "content-type", solo puede haber 100 (o menos) tipos de contenido posibles. Sin embargo, los valores numéricos son ilimitados. Si se requieren más valores por atributo, contacta con tu CSM o envía un correo electrónico a hello@appsflyer.com.</li><li>Solo se admiten números enteros (completos) en los filtros de conjuntos de reglas numéricos. No se admiten números de tipo flotante (decimales). Ejemplo: Los ingresos in-app de $1 USD se admiten, pero los de $1,5 USD no.</li></ul> |
| Reporte S2S | Asegúrate de que los identificadores de usuario (IDFV o IDFA) se envíen en la carga útil de eventos in-app S2S y que el IDFV o IDFA sea consistente con la recopilación del SDK de AppsFlyer. Esto asegurará que no se pierda ningún dato y que los cálculos de la audiencia sean precisos. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">Guía de incrementalidad</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/run-an-incrementality-for-remarketing-experiment">Ejecución de un experimento de incrementalidad</Anchor>

<div data-zendesk-anchors="audiences-basics=conceptos-b%C3%A1sicos-de-audiences h_01HBQMA619CKEESZD3ADSP3PSB=conceptos-b%C3%A1sicos-de-audiences audience-split-and-incrementality-testing=pruebas-de-incrementalidad-y-divisi%C3%B3n-de-audiencia h_01HBQMA619KMJFVX7Y8MXMMQ6N=pruebas-de-incrementalidad-y-divisi%C3%B3n-de-audiencia get-started=empezar h_01HBQMA619118PWF4TA98C4X0B=empezar create-and-manage-audiences=crear-y-gestionar-las-audiencias h_01HBQMA619DBX2C7DRY7MSV3P9=crear-y-gestionar-las-audiencias h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01JXA0GDBMBX541W6P63XXDVKQ=caracter%C3%ADsticas h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=ejemplo-de-caso-de-uso h_01JXA0WJFMSHA710CTNF84BPQ5=caracter%C3%ADstica h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=notas-relacionadas-con-eventos-in-app- 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences h_01HT04HW2VBB9ZY28V5KQ5K2AJ=pause all-about-rulesets=todo-sobre-los-conjuntos-de-reglas h_01HBQMA61ANB4K0TCJ4WBHMV8D=todo-sobre-los-conjuntos-de-reglas h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=ejemplo-regla-basada-en-la-ubicaci%C3%B3n h_01HBQMA61ATB7NYKBP7CD6SZZH=ejemplo-regla-basada-en-atributos-de-usuario h_01HBQMA61APWHKS4EP2NKABSQD=ejemplo-ingresos 01ECF4ZD0MJ8HVQCC54YHFE6DX=ejemplo-filtro-de-medios-propios h_01JRAGFYEQ28R6RQNPEK6WZV2F=ejemplo-remarketing h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01K5EHBY8ESJFS3GKJW1RCB99X=contains-does-not-contain-logic h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=crear-y-administrar-conexiones-de-partners h_01HBQMA61C6WS72DQ8FXVR0KVW=crear-y-administrar-conexiones-de-partners h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=dashboard-y-m%C3%A9tricas h_01HBQMA61C6WPFFR1F8P0HE4KA=dashboard-y-m%C3%A9tricas h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics metrics-hash=hash-de-m%C3%A9tricas h_01HBQMA61CMF3WZFPXKY89076K=hash-de-m%C3%A9tricas campaign-metrics-basics=conceptos-b%C3%A1sicos-de-m%C3%A9tricas-de-campa%C3%B1a h_01HBQMA61C4D5HFCDY83HNF5K7=conceptos-b%C3%A1sicos-de-m%C3%A9tricas-de-campa%C3%B1a summary-view=resumen h_01HBQMA61DW9Z84G8CH1RNY2RF=resumen h_01K3R8C7GK77FNVZ3N0C3XZGYG=resumen detailed-view=vista-detallada h_01HBQMA61D3VHDKD103EMN61YH=vista-detallada data-sources-and-availability=fuentes-de-datos-y-disponibilidad h_01HBQMA61DB595QKRTPE97F94E=fuentes-de-datos-y-disponibilidad h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HBQMA61DT46P43FNSRC1KGAX=caracter%C3%ADsticas-y-limitaciones h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=consulta-tambi%C3%A9n" />
