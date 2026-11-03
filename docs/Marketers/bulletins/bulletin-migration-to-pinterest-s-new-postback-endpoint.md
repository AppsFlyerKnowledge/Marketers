---
title: 'Boletín: Migración al nuevo punto final de postback de Pinterest'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-10-20T03:54:38Z'
  id: 37418019002641
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/37418019002641
---

<Table>
  <thead>
    <tr>
      <th>
        Sección.
      </th>
      <th>
        Detalles
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **¿Qué hay de nuevo?**
      </td>
      <td>
        Pinterest ha migrado a un nuevo punto final basado en su infraestructura de API de conversiones (CAPI). Debes actualizar para continuar enviando los eventos de tu aplicación a Pinterest. Descontinuaremos el antiguo punto final el 30 de septiembre de 2025.
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        23/07/2025
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes saber:**
      </td>
      <td>
        Este boletín incluye información relacionada con la fase de migración a CAPI. Para obtener información general sobre la integración de Pinterest, consulta <Anchor target="_blank" href="/marketers/es/docs/pinterest-create-a-mobile-app-integration#configuración-de-eventos-in-app">el artículo de la base de conocimientos</Anchor>.

        La actualización a la nueva configuración de eventos in-app de la API garantizará que la medición de Pinterest continúe sin interrupciones, e incluye también:

        * **Más tipos de «eventos»**: track eventos adicionales para alinearlos mejor con tus objetivos, como: Lead, Search, Category Viewed, Page Visit y más.
          * **Nota:** Los nombres de los eventos para el nuevo punto final de Pinterest V5 son diferentes. A menos que el dashboard se actualice en consecuencia, el reporte de eventos mostrará “desconocido”. Revisa los nuevos nombres de eventos a continuación.
        * **Calidad de los datos mejorada:** Benefíciate de una coincidencia mejorada y una mayor precisión en la atribución.

        La nueva integración requiere tanto un **ID de cuenta de anuncios** como un **Token de acceso**. Para mantener la funcionalidad de postback, los partners deben realizar la transición al nuevo punto final de postbacks antes del 30/09/25.   

        **Cómo encontrar el ID de cuenta de anuncios de Pinterest en AppsFlyer**  
        Puedes encontrar el ID de cuenta de anuncios actual para el reporte de conversiones de AppsFlyer de Pinterest en Pinterest **Business Manager** o en el reporte de Pinterest **Conversions**.

        1. Inicia sesión en tu cuenta comercial de Pinterest (debes estar en un perfil comercial para ver las opciones del Hub).
        2. Escribe o pega https://www.pinterest.com/business/hub/ en tu navegador y presiona Enter.
        3. Mira la columna de navegación de color gris oscuro en el lado izquierdo del Hub. Si la columna está plegada, haz clic en el pequeño icono “≡” (hamburguesa) en la esquina superior izquierda para expandirla.
        4. Desplázate un poco hasta que veas la sección titulada “Administrar negocio”.
        5. Haz clic en Conversiones (se encuentra justo debajo de “Administrar negocio”). Esto abre el dashboard de conversiones, donde puedes revisar las conversiones de AppsFlyer enviadas a Pinterest.
        6. El ID de la cuenta de anuncios estará presente en la URL.
        7. Si varios ID de cuentas de anuncios de Pinterest reciben conversiones clonadas de AppsFlyer, verifica todos los ID de cuentas de anuncios existentes con conversiones en el Pinterest Business Manager. Asegúrate de seleccionar el ID de la cuenta de anuncios principal original para las conversiones de AppsFlyer.

        **Cómo encontrar el Token de acceso de Pinterest en AppsFlyer**  
        Sigue los pasos descritos en el Centro de ayuda de Pinterest <Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">aquí</Anchor>. Una vez en Conversiones de Pinterest, haz clic en **API de conversiones** > **Configuración de la API**, y genera un nuevo token de acceso para la cuenta.  

        **Nota importante:** Si ya has configurado la API de conversiones para Pinterest por separado fuera de AppsFlyer, utiliza también aquí el mismo token de acceso para las conversiones de AppsFlyer.
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes hacer**
      </td>
      <td>
        Sigue las instrucciones que se indican a continuación para configurar y migrar los postbacks de eventos in-app en el dashboard de AppsFlyer.

        1. **Configuración de eventos in-app y gestión de parámetros del dashboard**  
           Actualmente, admitimos los siguientes parámetros del dashboard para asignar tus eventos de AppsFlyer con Pinterest:

           * **ID de la cuenta de anuncios** (visible)
           * **Token de acceso** (visible)
           * **ID de etiqueta** (no visible en el dashboard, pero compatible en el backend para ayudar con la transición a la nueva versión V5. Una vez que la transición al punto final V5 esté completamente soportada, el ID de etiqueta también se eliminará del backend.)

           **Nota:**  
           Para la nueva configuración de postback, debes introducir tanto el **ID de la cuenta de anuncios** como el **Token de acceso** (estos se pueden obtener de Pinterest si aún no están disponibles). **Si falta alguno de estos valores, el postback fallará**. Asegúrate de que ambos parámetros estén correctamente completados en la página de **Integración activa** de Pinterest. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/pinterest-create-a-mobile-app-integration#configuración-de-eventos-in-app">el artículo de la base de conocimientos</Anchor>.  
           Tu cooperación es importante para una transición fluida. Gracias por tu apoyo.
        2. **Asignación de eventos in-app y configuración de postbacks**
           1. Reemplaza y asigna los nombres de eventos actuales de Pinterest a los nuevos nombres de eventos de la API de conversiones de Pinterest en la sección **Nombre del evento para partner**. Por ejemplo, si actualmente estás utilizando `pin_add_to_cart` en la sección de eventos de partner, reemplázalo por `add_to_cart`. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/pinterest-create-a-mobile-app-integration#habilitar-la-atribución-por-impresiones">el artículo de la base de conocimientos</Anchor>.

        | event name (anterior) | event name (nueva API de conversiones) |
        | --- | --- |
        | pin\_add\_to\_cart | añadir\_al\_carrito |
        | pin\_purchase | checkout |
        | pin\_search | search |
        | pin\_registration | signup |
        | pin\_sign\_up | signup |
        | pin\_category\_view | view\_category |
        | add\_cart | añadir\_al\_carrito |
        | start\_checkout | checkout |
        | content\_view | view\_category |

              **Nota:** Si no actualizas los nombres de eventos heredados con los nombres de eventos correctos para la API de conversiones, en Pinterest aparecerá «Other» como nombre de evento, en lugar del nombre de evento correcto.
           2. Selecciona **ventana de postback de eventos in-app** en **Lifetime** para que Pinterest pueda recibir el máximo número de conversiones para la optimización de los anuncios
           3. Selecciona **Todas las fuentes de medios, incluidas las orgánicas** para **A los usuarios de**, para que Pinterest pueda recibir el máximo número de conversiones para la optimización de los anuncios. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/pinterest-create-a-mobile-app-integration#habilitar-la-atribución-por-impresiones">el artículo de la KB</Anchor>.
        3. **Proceso de reversión en caso de problemas**  
           Se recomienda a los anunciantes que monitoricen las conversiones de sus aplicaciones de AppsFlyer en Pinterest para detectar cualquier problema o incidencia con la migración. Por favor, espera hasta 30 minutos para que los datos de conversión de AppsFlyer aparezcan en Pinterest y asegúrate de supervisarlos regularmente durante unos días para validar el éxito de la migración.  

           Los anunciantes pueden volver al punto final heredado omitiendo uno o ambos valores de `account_id` y `access_token` en la configuración de la integración. 

           **Reglas de comportamiento:**

           * Tanto `account_id` como `access_token` están ausentes → Los postbacks se envían al punto final heredado (antiguo).
           * Solo se proporciona `account_id` (es decir, `access_token` está vacío) → Los postbacks se envían al punto final heredado.
           * Solo se proporciona `access_token` (es decir, `account_id` está vacío) → Los postbacks se envían al punto final heredado.
           * Se proporcionan tanto `account_id` como `access_token` → Los postbacks se envían al nuevo punto final.

           Si tienes algún problema, ponte en contacto con el servicio de asistencia de AppsFlyer a través de support@appsflyer.com. Para cualquier problema en Pinterest, ponte en contacto con api-support@pinterest.com o con tu representante de Pinterest.
      </td>
    </tr>
  </tbody>
</Table>
