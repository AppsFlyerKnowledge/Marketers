---
title: 'Audiencias: atributos de los usuarios'
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-07T00:17:44Z'
  id: 360009775517
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen general:** Mejora tu capacidad para segmentar a los usuarios en grupos relevantes añadiendo tus datos sobre sus características en Audiencias.

<Image align="center" alt="UserAttributionNavigationXL3_us-en.png" src="https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png" />

<div id="about-user-attributes" />

## Acerca de los atributos de usuario

Los atributos de usuario, a diferencia de los datos basados en eventos, son características generales que tus usuarios comparten contigo. Pueden ser estáticos, como género, edad, fecha de nacimiento y país; o dinámicos, como la puntuación del usuario en un juego.

Los datos de atributos de usuario se:

* Actualizan mediante la importación de archivos CSV o JSON a través de API.
* Almacenan en formato cifrado.
* Encuentran disponibles para su uso en cualquier conjunto de reglas de audiencia.

Los datos de atributos de usuario **no se comparten con socios publicitarios.**

Los atributos de usuario se alojan a nivel de aplicación o de cuenta, como se describe en este artículo. Si utilizas atributos a nivel de aplicación, el usuario de la cuenta necesita <Anchor target="_blank" href="/marketers/es/docs/user-management#descripción-general">permiso de aplicación</Anchor> para gestionar y usar los atributos.

El siguiente escenario ofrece una explicación detallada de los atributos de usuario.

<div id="scenario-app-marketer-requirements" />

<Accordion title="Escenario: requisitos del marketer de aplicaciones">

Tú, como marketer de aplicaciones, estás ocupado con lo siguiente:

* Mantener 2 aplicaciones de juegos: game\_a y game\_b.
* Lanzar game\_c
* Dirigirte a los usuarios actuales de la aplicación con estos atributos de usuario:
  * Deporte favorito: Cricket
  * Puntuación actual del juego: 15 o más en uno de los juegos actuales

La tabla contiene datos de atributos de usuario de tu CRM. Los conjuntos de reglas de audiencia necesitan acceso a estos datos.   
<Image align="center" alt="UserAttributuesExample_us-en.png" src="https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png" />

**Usa datos de CRM en conjuntos de reglas**

En Audiencias, crea atributos de usuario (deporte favorito y puntuación del juego). Esto permite que el conjunto de reglas acceda a los datos de CRM.

<div id="scenario-user-attributes" />

#### Atributos de usuario del escenario

| Name | Formato | Nivel |
| --- | --- | --- |
| <span id="game-score"></span>Puntuación del juego | **Número**: Te permite establecer reglas como '*ScoreGameB es mayor que 29'*. | **A nivel de aplicación**: La puntuación del usuario se registra para cada juego jugado.<br /><br />Significado: ScoreGameA, ScoreGameB. |
| <span id="favorite-sport"></span>Deporte favorito | **String:** Te permite establecer reglas como '*cuyo deporte favorito es el tenis*'.<br /><br />¡Atención! Los valores distinguen entre mayúsculas y minúsculas. | **A nivel de cuenta**: El deporte favorito del usuario es siempre el mismo independientemente de la aplicación.<br /><br />¡Atención! Un usuario puede tener solo un valor asociado con los atributos a nivel de cuenta. |

**Atributos de usuario en conjuntos de reglas**

Los atributos de usuario funcionan como filtros en los conjuntos de reglas de Audiencias. Este ejemplo utiliza criterios (deporte favorito y puntuación en el juego) que establece el comercializador.

<Image align="center" alt="Ejemplo de atributo de usuario.jpg" src="https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg" width="276px" />

</Accordion>

<div id="implement-user-attributes" />

## Implementar atributos de usuario

Configurar, añadir, gestionar y eliminar atributos de usuario.

<div id="set-up" />

<Accordion title="Configurar">

**Requisito previo**:

Para gestionar atributos a nivel de aplicación, el usuario de la cuenta debe tener permiso para la aplicación.

**Para configurar los atributos de usuario siga estos pasos:**

1. [Añadir atributos de usuario.](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [Puede realizar una de las siguientes acciones:](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Importar datos de atributos de usuario mediante CSV.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Importar datos de atributos de usuario mediante API.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#user-attributes">Implementar atributos de usuario en conjuntos de reglas.</Anchor>

</Accordion>

<div id="add" />

<Accordion title="Añadir">

**Para añadir atributos de usuario:**

1. En AppsFlyer, desde el menú lateral, elija **Interactuar** > **Audiencias**.
2. Haga clic en la pestaña Atributos de usuario.
3. Haga clic en **Agregar atributo de usuario**.

   <Image align="center" alt="Agregar atributo de usuario.png" src="https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png" />
4. Rellene los campos. Las características de los campos se enumeran en la tabla que sigue.
   * **Nombre del atributo**
   * **Formato**
   * **Nivel**
5. Haga clic en **Guardar**.

| Campo | Características |
| --- | --- |
| <span id="attribute-name"></span>Nombre del atributo | <ul><li>Solo caracteres en inglés</li><li>Sin puntuación ni caracteres especiales</li><li>El mismo nombre no puede usarse a nivel de aplicación y de cuenta</li><li>El mismo nombre **puede** emplearse a nivel de aplicación; por ejemplo, en el escenario anterior se utilizan ScoreGameA y ScoreGameB</li></ul> |
| <span id="format"></span>Formato | <ul><li>Texto: Compruebe si el valor del atributo **es** o **no es igual** a un valor de regla especificado. Ejemplo: Es cricket o no es cricket.</li><li>Número: Compruebe si el valor del atributo es mayor, menor o igual a un valor de regla especificado. Ejemplo: Puntuación superior a 15</li></ul> |
| <span id="level"></span>Nivel | <ul><li>Nivel de cuenta: Un atributo no tiene conexión con la aplicación.<br />Ejemplo: género, deporte favorito</li><li>Nivel de aplicación: Un atributo está relacionado con la aplicación. Seleccione las aplicaciones asociadas al atributo.</li></ul> |

**Campos de atributos de usuario**

</Accordion>

<div id="manage" />

<Accordion title="Gestionar">

Para gestionar los atributos de usuario, ve a la pestaña **audiencias** > **Atributos de usuario**.

<Image align="center" alt="AudienciasUserAttributes_us-en.png" src="https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png" />

| Función | Descripción |
| --- | --- |
| <span id="search-and-filter"></span>Buscar y filtrar | Por nombre de atributo, nombre de la aplicación y nivel de atributo. |
| <span id="sort-by"></span>Ordenar por | Haga clic en el encabezado de una columna para ordenar las filas de la tabla. |
| <span id="zd-import-data"></span><span id="import-data"></span>Importar datos | <ul><li>[Importar datos mediante CSV](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[Importar datos a través de API](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>Cambiar la clave de importación de API | **Para cambiar la clave de importación de API:**<ol><li>Haga clic en **Importar datos**.</li><li>Seleccione **API**.</li><li>Haz clic en **Actualizar clave de importación**.</li></ol>**¡Atención!** ¡Nota! **Si los scripts tienen claves integradas, asegúrese de actualizarlos con la nueva clave.** |

Gestionar atributos de usuario

</Accordion>

<div id="delete" />

<Accordion title="Eliminar">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Solo un usuario administrador puede suprimir un atributo.

**Para suprimir un atributo que forma parte de un conjunto de reglas:**

1. Quite el atributo del conjunto de reglas.
2. Elimine el atributo.

</Accordion>

## Importar datos

<div id="import-field-specifications" />

<Accordion title="Especificaciones del campo de importación">

| Campo | Contenido | Formato | Agregar datos  <br />a través de CSV | Eliminar datos mediante CSV |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>id\_del\_dispositivo | Incluye uno de estos ID de usuario:<ul><li>Identificador de anunciante (IDFA)</li><li>GNA Company</li></ul> | Texto | Es obligatorio **device\_id** o **customer\_id** | Es obligatorio indicar **device\_id** o **customer\_id**<br /><br />Para eliminar los datos existentes, no envíe |
| <span id="customer_id"></span>id\_cliente | <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario del cliente</Anchor> | Texto | Es obligatorio indicar **device\_id** o **customer\_id** | Es obligatorio indicar **device\_id** o **customer\_id**<br /><br />Para eliminar los datos existentes, no envíe |
| <span id="app_id"></span>id\_aplicación | **Atributo a nivel de aplicación:** App ID tal como aparece en el dashboard.<br /><br />Para las aplicaciones iOS, incluye el prefijo *ID*.<br /><br />**Atributo a nivel de cuenta**: Rellénalo siempre con * | Texto | Obligatorio | Obligatorio |
| <span id="attribute_key"></span>clave de atributo | Nombre del atributo de usuario, exactamente como se muestra en la pestaña de atributos de usuario. | Texto | Obligatorio | Obligatorio |
| <span id="attribute_value"></span>valor\_del\_atributo | Valor asignado<br /><br />[*Ver limitaciones](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | Texto o número | Obligatorio | No enviar |

Listado de campos de atributos de usuario

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="Importar datos mediante CSV">

Los datos de atributos de usuario se agregan o eliminan mediante un archivo CSV. La figura y el archivo CSV de ejemplo que sigue coinciden con el escenario descrito en este artículo.

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">Ejemplo de atributo de usuario.csv</Anchor>

<Image align="center" alt="ArchivoParaAtributos.png" src="https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png" />

**Requisitos del archivo CSV**

* Sin fila de encabezado
* Contiene todas las columnas enumeradas en la tabla anterior.

<div id="note" />

> 📘 **Nota:**
>
> Este formato CSV sirve para importar datos de atributos de usuario. Si en su lugar vas a importar segmentos de audiencias, consulta <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems">Importar segmentos de audiencia desde sistemas internos</Anchor>, que utiliza un formato CSV distinto y requiere una fila de encabezado.

**Para importar un archivo CSV:**

1. Vaya a la pestaña **Audiencias** > **Atributos de usuario** .
2. Haga clic en **Importar datos**.
3. Seleccione **CSV**.
4. Seleccione una de las siguientes opciones:
   * **Añadir datos**
   * **Eliminar datos**
5. Elija un archivo CSV para importar.
6. Haga clic en **Cargar**; aparecerá un mensaje de estado de carga.

**Nota:** Al importar atributos de usuario, todos los dispositivos asociados conocidos con un ID de cliente también reciben el atributo. Por ejemplo, si un usuario importa 10 dispositivos (por customer\_id) al atributo “Puntaje del juego”, y uno de los customer\_id está asociado a 2 dispositivos (es decir, 2 GAID con el mismo CUID), esta importación incluirá 11 registros de atributos de usuario.

</Accordion>

<div id="import-data-by-api" />

<Accordion title="Importar datos a través de API">

Este método de importación requiere una URL de solicitud y un JSON con datos de atributos de usuario.

1. En el panel de control, obtén las llamadas de solicitud de API preparadas y la plantilla JSON.
2. Rellena la plantilla JSON con tus datos de acuerdo con las [especificaciones de campo](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications).

**Para generar la URL de solicitud de API y la plantilla JSON:**

1. Haz clic en **Importar datos.**
2. Selecciona **API.**
3. Elige una acción:  
   * Actualizar atributos de usuario: Sobrescribir o agregar.
   * Eliminar atributos de usuario.
   * Eliminar datos del usuario: Elimina todos los datos relacionados con un usuario específico. El usuario se identifica mediante su ID de AppsFlyer.
   * Eliminar datos de la aplicación: Elimina todos los datos a nivel de la aplicación.
4. Copia la URL de solicitud de API generada.
5. Copia el cuerpo de la solicitud de API generada.
6. Prepara el JSON (con sus datos de atributos de usuario) utilizando el formato JSON especificado. Para los atributos a nivel de cuenta, configura "app\_ids": ["*"]
7. Prepara la llamada API basándote en la URL y el cuerpo de la solicitud.
8. Envía la solicitud de manera programática.

**Ejemplo de solicitud y JSON**

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

<div id="note-1" />

> 📘 **Nota:**
>
> Debes autenticar la solicitud mediante un encabezado Authorization Bearer con un <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens#appsflyer">token API V2.0</Anchor>

**Ejemplo con múltiples IDs de dispositivos, claves de atributos y valores de atributos**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**Ejemplo con un único ID de dispositivo y múltiples claves y valores de atributos**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**Nota:** Al importar atributos de usuario, todos los dispositivos asociados conocidos con un ID de cliente también reciben el atributo. Por ejemplo, si un usuario importa 10 dispositivos (por customer\_id) al atributo “Puntaje del juego”, y uno de los customer\_id está asociado a 2 dispositivos (es decir, 2 GAID con el mismo CUID), esta importación incluirá 11 registros de atributos de usuario. Limitaciones de importación CSV

</Accordion>

<div id="limitations" />

<Accordion title="Limitaciones">

<div id="general-limitations" />

#### Limitaciones generales

* Solo se admiten números enteros en los datos de importación CSV/API. No se admiten números de tipo flotante (decimales). **Ejemplo:** Un valor de atributo "puntuación" puede ser 90, pero no 90,5.
* No se pueden imprimir ni descargar los datos de atributos de usuario.
* #### <span id="attribute-value-limitations"></span>Limitaciones de los valores de los atributos:

  * No se permiten comas, puntos ni otros caracteres especiales en los valores de los atributos.
  * Existe una limitación de 40 caracteres para un valor de atributo de tipo cadena.
  * Los valores de los atributos no pueden comenzar con 0.

<div id="api-import-limitations" />

#### Limitaciones de importación a través de la API

* Un máximo de 350 solicitudes API por minuto, 10.000 dispositivos para una carga útil simple (10.000 dispositivos con un atributo, 5.000 con dos atributos, etc.)
* Las claves `device_id` y `customer_id` son necesarias para cada llamada de importación. Si desea importar atributos con solo uno de estos identificadores, la llamada debe incluir el "encabezado" del otro identificador con una cadena vacía. Por ejemplo, si desea importar atributos por `device_id` y no por `customer_id`, la llamada debería ser así:

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

<div id="csv-import-limitations" />

#### Limitaciones de importación CSV

* Al agregar valores de atributos de usuario, se permite un máximo de 10 millones de filas por archivo CSV.

</Accordion>

<div data-zendesk-anchors="user-attributes=acerca-de-los-atributos-de-usuario h_01HDNZH1XVX5BYQBPG848M8QZM=acerca-de-los-atributos-de-usuario scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=atributos-de-usuario-del-escenario h_01HDNZH1XW32ZJJRSANBQCTBV0=atributos-de-usuario-del-escenario implement-user-attributes=implementar-atributos-de-usuario h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=implementar-atributos-de-usuario h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=importar-datos h_01HDNZH1XWCXV89YJV7EBJXNK5=importar-datos h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01M45D4VCXXKXV25MQNAKW53ZW=nota h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=nota-1 h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=limitaciones-generales h_01HDNZH1XXZZFA3WHZEE5N24AB=limitaciones-generales attribute-value-limitations=limitaciones-de-los-valores-de-los-atributos h_01GZTGPK2FTHTV4NQ2HKV1HK00=limitaciones-de-los-valores-de-los-atributos api-import-limitations=limitaciones-de-importaci%C3%B3n-a-trav%C3%A9s-de-la-api h_01HDNZH1XX4JWSMSF4672ENWNS=limitaciones-de-importaci%C3%B3n-a-trav%C3%A9s-de-la-api csv-import-limitations=limitaciones-de-importaci%C3%B3n-csv h_01J3APYQ8MXG1SGREVN638R75N=limitaciones-de-importaci%C3%B3n-csv" />
