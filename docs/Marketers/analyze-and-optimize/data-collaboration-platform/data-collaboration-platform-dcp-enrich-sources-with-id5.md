---
title: Plataforma de colaboración de datos (DCP) - Enriquece fuentes con ID5
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-01-08T07:53:48Z'
  edited_at: '2026-08-12T11:53:51Z'
  id: 42626850533137
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/42626850533137
---
> **De un vistazo:** Enriquece tus datos first-party con identificadores de ID5 para unificar los datos fragmentados de los usuarios y mejorar las tasas de coincidencia con partners de activación, lo que se traduce en audiencias más amplias.

<div id="about-id5-enrichment" />

## Sobre el enriquecimiento con ID5

La Plataforma de Colaboración de Datos de AppsFlyer se integra con ID5, un proveedor líder de soluciones de identidad para la web abierta. ID5 conecta identificadores dispares, como direcciones IP, correos electrónicos con hash (HEM) e ID de publicidad móvil (MAID), en un ID unificado, con la privacidad como prioridad. Esto aumenta las tasas de coincidencia entre los conjuntos de datos de los colaboradores, lo que permite reconocer, vincular y activar a más usuarios en las audiencias. Esta guía explica cómo funciona el enriquecimiento con ID5 en DCP, cómo configurarlo y cómo usarlo para colaboraciones y activación.

**El enriquecimiento con ID5 te ayuda a:**

* Aumentar las tasas de coincidencia entre tus datos first-party y partners de medios o colaboradores
* Maximizar el tamaño de la audiencia objetivo
* Vincular identificadores como HEM, MAID e IP + marca de tiempo en una identidad unificada
* Preparar tu activación para el futuro a medida que desaparecen las cookies de terceros

**Los casos de uso comunes incluyen:**

* **Enriquecimiento de datos first-party de una marca** - Una marca sube su fuente de datos first-party a DCP y la enriquece con ID de ID5 mediante su conexión de ID5.
* **Colaboración entre retailer y marca**: un retailer colabora con una marca y comparte acceso a su suscripción de ID5. Dentro del ámbito de colaboración segura, la marca enriquece los datos de sus clientes mediante la conexión de ID5 del retailer, lo que mejora las tasas de coincidencia sin requerir su propia cuenta directa de ID5.
* **Activación de partners** - Las fuentes enriquecidas se pueden enviar a partners de activación compatibles para aumentar las tasas de coincidencia, lo que significa que se puede encontrar coincidencia para más usuarios de tus datos e incluirlos en las audiencias del partner.

<div id="how-id5-works" />

## Cómo funciona ID5

DCP usa los ID de ID5 devueltos para enriquecer tu fuente, lo que da como resultado una nueva fuente enriquecida disponible para segmentación y activación.

**Dos flujos de enriquecimiento compatibles:**

| Flujo | Descripción | Cuándo usar |
| --- | --- | --- |
| Flujo con etiquetado | El propietario de los datos ya aplica el etiquetado del sitio de ID5 en su dominio, por lo que los datos que sube ya contienen una columna de ID de ID5. | Cuando gestionas directamente el etiquetado de ID5 en tu sitio y quieres usar DCP sin enriquecimiento adicional. |
| Flujo de enriquecimiento de servidor a servidor (S2S) | AppsFlyer envía a ID5 la fuente de datos que has seleccionado, ID5 la enriquece con ID de ID5 y la devuelve a DCP como una fuente enriquecida. | Cuando tu fuente no incluye una columna de ID5 o cuando quieres que AppsFlyer gestione el enriquecimiento automáticamente. |

<div id="get-started-with-id5-enrichment" />

## Comienza con el enriquecimiento de ID5

En esta sección se describe cómo crear una conexión de ID5 en DCP y utilizarla para el enriquecimiento.

**Pré-requisitos:**

* Una cuenta de AppsFlyer con permisos de DCP
* Un token de ID5 (proporcionado por tu gestor de cuentas de ID5)
* Una fuente que contenga al menos uno de los identificadores compatibles: HEM, MAID o IP + marca de tiempo

<div id="create-an-id5-connection" />

<Accordion title="Crear una conexión de ID5">

Para usar el enriquecimiento de ID5, primero crea una conexión de **Data & Identity** en DCP.

1. Accede a la plataforma Data Collaboration Platform haciendo clic en **Collaborate** > **Data Clean Room** en el menú lateral de AppsFlyer.

   <Image align="center" alt="Haz clic en Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="33.49%" />
2. Ve a **Gestionar conexiones** (arriba a la derecha).
3. En la pestaña **Data & Identity**, selecciona **+ New connection**.

   **<Image alt="+New connection.png" src="https://files.readme.io/815ec20e84d85da413dfe9c9358b54d772461e1eeb3dff3ff7c5c31ced1088ac-42729247721873.png" width="72.63%" />**
4. Selecciona **ID5.**

   **<Image alt="Selecciona ID5.png" src="https://files.readme.io/a0c53243318fa7eed48ac5886ff5f3272bec0e6fd83a41117d53473757ab16d7-42729260095633.png" width="66.76%" />**
5. Introduce tu token de ID5 (si procede).
6. Haga clic en **Guardar**.

Una vez guardada, la conexión estará disponible para tus fuentes y colaboraciones (sujeto a permisos).

</Accordion>

<div id="enrich-a-source-with-id5" />

<Accordion title="Enriquecer una fuente con ID5">

Puedes enriquecer tus fuentes mediante el flujo S2S.

**Para enriquecer una fuente:**

1. Accede a la plataforma Data Collaboration Platform haciendo clic en **Collaborate** > **Data Clean Room** en el menú lateral de AppsFlyer.
2. Ve a la pestaña **Sources** y pasa el cursor sobre la fuente correspondiente.
3. En el menú de acciones, selecciona **Enrich**.

   <Image align="center" alt="Enrich.png" src="https://files.readme.io/51c3f33da62d84ec9214e178e3bbaef15d6a03a32827ad393166db0dcd9a70fd-42729376739473.png" width="245px" />
4. Haz clic en **Start enrichment**.
5. Cuando termine el flujo de enriquecimiento, tendrás una nueva fuente conectada a la fuente original con la incorporación de ID de ID5.  
   **Nota:** Si alguna vez se elimina la fuente original, la nueva fuente también se eliminará.

</Accordion>

<div id="grant-id5-permissions-in-a-collaboration" />

<Accordion title="Conceder permisos de ID5 en una colaboración">

Los propietarios de la colaboración pueden permitir que los colaboradores usen una conexión de ID5 en una colaboración (sujeto al acuerdo comercial con ID5).

**Para conceder permisos de ID5 a un colaborador:**

1. Accede a la plataforma de colaboración de datos haciendo clic en **Collaborate** > **Data Clean Room** en el menú lateral de AppsFlyer.
2. En la pestaña **Collaborations**, abre una colaboración existente o <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration">crea una nueva</Anchor>.
3. Haz clic en **Collaboration with «your collaborator»**

   **<Image alt="Actualizar política de colaboración.png" src="https://files.readme.io/25d707c47bed9f5f60cd1ba521c4b48f41afbb0e36949f0ffa35cecf9a932ddc-42838633495313.png" width="58.95%" />**
4. Haz clic en **Editar la política de colaboración**.

   <Image align="center" alt="Haz clic en Editar la política de colaboración.png" src="https://files.readme.io/07aab2a3165d26779e94f62eb8487893bc725dfa3ad4c406de576480e2ed6c13-42838633497489.png" width="80.3%" />
5. Haz clic en **Permisos de acceso**.

   **<Image alt="Haz clic en Permisos de acceso.png" src="https://files.readme.io/b239775d71e1fa1dcc23537e73e35b80bff0184c9ee2aa213f644d90251284f3-42838633499281.png" width="78.62%" />**
6. Activa la **conexión de ID5**.

   <Image align="center" alt="Permisos de ID5.png" src="https://files.readme.io/f2831ec4f775b51ef419da33444198de6aabfde3b27d83cc9af623eaed4a865c-42789059643793.png" width="79.6%" />
7. Haga clic en **Guardar**.

Luego, los colaboradores pueden asociar sus propias fuentes a la colaboración y enriquecerlas usando la conexión de ID5 del partner.

</Accordion>

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

En esta sección se describen algunas características y limitaciones clave.

| Característica / limitación | Nota |
| --- | --- |
| Primer enriquecimiento y actualizaciones diarias | La primera ejecución del enriquecimiento empieza de inmediato y suele completarse en unas horas.<br /><br />Después de la ejecución inicial, el enriquecimiento continúa a diario a una hora de procesamiento fija, lo que garantiza asignaciones de identidad actualizadas.<br /><br />Puedes pausar el enriquecimiento en cualquier momento para detener las actualizaciones diarias. |
| Dependencia de la fuente | Si se elimina la fuente original, la fuente enriquecida se elimina automáticamente. |
| Alcance de la activación | En una colaboración, un anunciante puede usar datos enriquecidos para la activación, pero no puede descargarlos ni consultarlos. |
| Restricciones de estado | Solo puedes enriquecer fuentes con el estado **Activo**. |
| Latencia del enriquecimiento | Las fuentes con estado **Waiting** o **Processing** siguen enriqueciéndose, pero solo pueden usarse cuando alcanzan el estado **Activo**. |
| Ventana de retención | ID5 almacena las asignaciones durante 14–90 días, según la actividad. |
| Requisito del identificador | Si la fuente no tiene HEM, MAID o IP + marca de tiempo, el enriquecimiento se desactiva. |
| Conflictos de conexión | Una colaboración solo puede incluir una conexión de ID5. Si ambas partes tienen sus propias conexiones de ID5, no se podrá usar ninguna de ellas dentro de la colaboración. En este caso, cada parte debe enriquecer sus datos por separado en su propio entorno, y después solo se podrán usar en la colaboración las fuentes enriquecidas resultantes. |

<div data-zendesk-anchors="about-id5-enrichment=sobre-el-enriquecimiento-con-id5 h_01KD7VPW5NX5QHVPJWX5YCGXAH=sobre-el-enriquecimiento-con-id5 how-id5-works=c%C3%B3mo-funciona-id5 h_01KD7VPW5NW24X53QQE2ZVDA2N=c%C3%B3mo-funciona-id5 get-started-with-id5-enrichment=comienza-con-el-enriquecimiento-de-id5 h_01KD7VPW5P0FEEAET9RXVPSECY=comienza-con-el-enriquecimiento-de-id5 h_01KD80FBKDHB6HKTTMXFDPGH5E=create-an-id5-connection h_01KD80FBKE4Q8TMNW7WFCN4QGC=enrich-a-source-with-id5 h_01KD80FBKE6TB00E8PZCFWST6M=grant-id5-permissions-in-a-collaboration traits-and-limitations=especificaciones-y-limitaciones h_01KD7VPW5P5XV61Z3X2CWZ7GV9=especificaciones-y-limitaciones" />
