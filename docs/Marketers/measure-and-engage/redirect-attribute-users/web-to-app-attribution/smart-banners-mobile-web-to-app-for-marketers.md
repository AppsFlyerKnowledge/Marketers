---
title: 'Smart Banners: mobile web-to-app (para marketers)'
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-08-12T12:25:38Z'
  id: 360000764837
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/360000764837
---
> **En resumen:** Convierte a los visitantes de tu sitio web en usuarios de la aplicación móvil con smart banners.

[![](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)

<div id="note" />

> 📘 **Nota:**
>
> El SDK web de AppsFlyer para Smart Banners v1 quedó en desuso el 8 de noviembre de 2023. Para mostrar Smart Banners en tu sitio web, necesitas actualizar a la v2. <Anchor target="_blank" href="/marketers/es/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Saber más</Anchor>

<div id="smart-banners" />

## Banners inteligentes

Smart Banners:

* **Se muestran en el sitio web móvil de tu marca** para aumentar las tasas de conversión para usuarios de alta intención.
* Miden la calidad de las aplicaciones que vienen de los visitantes del sitio web móvil.
* Permite una atribución móvil precisa de la campaña web a la aplicación para TODAS las fuentes de medios, incluidas las SRNs.
* Los Smart Banners pueden atribuir mediante la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#tipos-de-atribución-por-engagement-de-usuario">atribución por clics, la atribución por impresiones</Anchor> y el recuento de impresiones:
  * **Clics:** Un usuario hace clic en los Smart Banners y procede a la instalación.
  * **Impresiones:** Cuando se carga el banner (el usuario ve el banner), envía un evento de recuento de impresiones a AppsFlyer.

El flujo es el siguiente:

1. Un usuario hace clic en un anuncio y se lo dirige al sitio web móvil del anunciante.
2. [Aparece](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic) un Smart Banner en el sitio web móvil del anunciante.
3. El usuario hace clic en el Smart Banner y:
   * **Si la aplicación no está instalada**, se dirige al usuario a la tienda de aplicaciones para que instale la aplicación.
   * **Si la aplicación está instalada** y se han configurado Universal Links, App Links, y/o enlaces URI, la aplicación se inicia directamente.
4. El usuario llega al contenido in-app, en el contexto de la promoción.
5. El usuario se atribuye a la fuente de medios que mostró el anuncio original.

**¿Quién está involucrado?**

* El desarrollador del sitio web solo tiene que <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation">introducir un fragmento de código en el HTML del sitio web</Anchor>.
* Para el resto de acciones, solo se requiere al marketer.

---

**Requisitos previos**

* Una cuenta de AppsFlyer con al menos una aplicación
* No se admite la capacidad de medir el número de usuarios que hicieron clic en el banner pero lo cerraron.

---

**Tiempo requerido**

Aproximadamente 20 minutos.

---

**Resultado**

* Los visitantes del sitio web que hagan clic en el CTA se envían a la tienda de aplicaciones o página web correcta según su dispositivo.
* Los usuarios de aplicaciones móviles que hacen clic en el CTA pueden obtener un deep link a la aplicación.
* Los usuarios se atribuyen desde el clic/instalación a las fuentes de medios originales o a tus propias fuentes de medios.
* El rendimiento del banner se puede ver en la página de rendimiento y en las tarjetas.

---

---

<div id="example" />

> 📄 **Ejemplo**
>
> Mark trabaja como marketer para el exitoso servicio de entrega de comida llamado "Feed Me".
>
> Mark quiere convertir a los visitantes del sitio web móvil de Feed Me en usuarios de la aplicación.
>
> Para ello, Mark utiliza Smart Banners usando sus propios elementos visuales y textos.
>
> Los Smart Banners funcionan con tecnología OneLink. Cuando los visitantes del sitio web móvil hacen clic en el CTA, **automáticamente los dirige a la tienda de aplicaciones o landing page correspondiente**, donde es fácil para ellos instalar la aplicación. Cuando los usuarios móviles existentes hacen clic en el CTA, se inicia la aplicación.
>
> AppsFlyer **atribuye el clic/instalación a la fuente de medios y la campaña definidas por Mark**.

<div id="important" />

> 🚧 **Importante:**
>
> Utiliza Smart Banners de AppsFlyer o el Smart Banner de la aplicación de Safari de iOS, pero no ambos. El uso de ambos puede causar problemas de visualización en tu sitio web móvil y dar lugar a discrepancias de atribución.

<div id="setup" />

## Configuración

Completa los siguientes procedimientos para configurar un Smart Banner que:

* Dirija a los usuarios desde tu sitio móvil, a través de un Smart Banner, a la tienda de aplicaciones o a la página de aplicaciones en función de su dispositivo.
* Atribuye el clic o la instalación a tu propia fuente de medios mediante OneLink.

<div id="1-website-workplace-setup" />

<Accordion title="1. Configuración del workplace del sitio web">

<div id="prepare-your-mobile-site-to-display-smart-banners-for-the-first-time" />

#### Para preparar tu sitio móvil para mostrar Smart Banners por primera vez

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Web-to-app** > **Smart Banners** > **Ir a Smart Banners**.
2. Haz clic en **Comenzar**. El asistente de configuración te guiará a través de los pasos requeridos (a continuación). Para configurar más workplaces en el sitio web, consulta más abajo.
3. Introduce un nombre para el workplace del sitio web.
4. Haz clic en **Crear**. Se abre el workplace del sitio web.
5. Copia el **fragmento de código** del banner.
6. Implementa el fragmento de código en tu sitio web. Esta tarea se realiza una sola vez por sitio web.
   * Para agregar el código a tu sitio web a través de Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace o WordPress, consulta <Anchor target="_blank" href="/marketers/es/docs/smart-banners-website-code-implementation-for-marketers">Implementación de código de sitio web de Smart Banners para marketers</Anchor>.
   * Para agregar el código a través de otras plataformas o para realizar cambios en el código según las necesidades (incluyendo agregar parámetros, deep linking, ocultar el banner o integrar la PBA con Smart Banners), consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementación de código de sitio web de Smart Banners para desarrolladores.</Anchor>
7. [opcional] Copia la **clave web**. (Esta clave ya existe como parte del fragmento de código).
8. Haz clic en **Continuar**.

<div id="to-create-website-workplaces-after-the-first-time" />

#### Para crear workplaces del sitio web después de la primera vez

1. En AppsFlyer, desde el menú lateral, ve a **Engage** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Haz clic en el menú de opciones
3. selecciona **Nuevo workplace del sitio web**
4. Introduce un nombre para el workplace del sitio web.
5. Haz clic en **Crear**. Se abre el workplace del sitio web.
6. Copia el **fragmento de código** del banner.
7. Implementa el fragmento de código en tu sitio web. Esta tarea se realiza una sola vez por sitio web.
   * Para agregar el código a tu sitio web a través de Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace o WordPress, consulta <Anchor target="_blank" href="/marketers/es/docs/smart-banners-website-code-implementation-for-marketers">Implementación de código de sitio web de Smart Banners para marketers</Anchor>.
   * Para agregar el código a través de otras plataformas o para realizar cambios en el código según las necesidades (incluyendo agregar parámetros, deep linking, ocultar el banner o integrar la PBA con Smart Banners), consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementación de código de sitio web de Smart Banners para desarrolladores.</Anchor>
8. [opcional] Copia la **clave web**. (Esta clave ya existe como parte del fragmento de código).
9. Haz clic en **Continuar**.

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. Configuración del grupo de banners">

Los grupos de banners contienen uno o más banners. Desde aquí, podrás:

* Seleccionar la plantilla de OneLink utilizada por el grupo de banners, que contiene las aplicaciones móviles a las que redirigir a los visitantes de tu sitio web.
* Configurar un esquema específico de deep linking
* Definir tus reglas de targeting, programación, comportamiento y detalles de atribución utilizados por todos los banners del grupo de banners.
* Configurar qué páginas activan los banners del grupo de banners cuando se visitan.

**Para configurar o duplicar un grupo de banners:**

1. En AppsFlyer, desde el menú lateral, ve a **Engage** > **Web-to-app** > **Smart Banners**.
2. **Para configurar un grupo de banners por primera vez**
   1. <span class="af-ol-a"></span>En el lado izquierdo, haz clic en **Agregar grupo de banners**.
   2. Sigue los pasos 5 y siguientes.
3. **Para configurar grupos de banners adicionales**
   1. <span class="af-ol-a"></span>Ve a la pestaña **Studio**.
   2. Haz clic en **+ Nuevo**.
   3. Sigue los pasos 5 y siguientes.
4. **Para duplicar un grupo de banners**
   1. <span class="af-ol-a"></span>Haz clic en el icono **Duplicar** que se encuentra junto al icono de eliminar.
5. Introduce un nombre único para el **nombre del grupo de Banners**. El nombre debe reflejar un tema general común entre los banners que se definan para el grupo de banners (por ejemplo, la aplicación anunciada).
6. Selecciona la plantilla de OneLink para el grupo de banners.
7. [opcional] Configura el **esquema URI** para el grupo de banners como alternativa para los usuarios de Universal Links y Android App Links. Esto rara vez es necesario, ya que de forma predeterminada, el valor se toma de la plantilla de OneLink. Configura esto para el grupo de banners solo si necesitas un valor diferente al de la plantilla.
8. <span id="attributed-sources"></span>Establece las **fuentes atribuidas** principales y alternativas para que se atribuyan con las nuevas instalaciones provenientes de este grupo de banners.   
    **Nota sobre el reenvío de ID de clic:** FBCLID, GCLID, WBRAID y GBRAID se reenvían automáticamente a la URL saliente si están disponibles en la URL entrante. Para los ID de clic de Google, si también se encuentra el parámetro “palabra clave”, coloca el valor de la palabra clave en la URL saliente como el valor de af\_keywords.

   Usa la siguiente tabla para elegir la mejor opción para el enlace personalizado:

<div id="param-table" />

| Opción | Cuándo seleccionar | Comentarios |
| --- | --- | --- |
| **Usar parámetros UTM** | Selecciona cuando la mayoría de los visitantes no orgánicos llegan al sitio web móvil desde fuentes con parámetros UTM. | ◦ Nombre de la fuente de medios (pid) = UTM\_Source   <br />◦ Campaign (c) = UTM\_campaign  <br />◦ Si UTM\_source o UTM\_campaign no están, los nombres estáticos se usan como alternativa. |
| **Usar parámetros del enlace entrante de atribución** | Selecciona cuando la mayoría de los visitantes no orgánicos llegan al sitio web móvil desde las redes de publicidad por clics que utilizan los enlaces de atribución de AppsFlyer. | ◦ Todos los parámetros disponibles del enlace de atribución entrante de AppsFlyer se agregan al enlace del Smart Banner.<br /><br />◦ Si existe un parámetro tanto en el enlace entrante de atribución de AppsFlyer como en el Smart Banner, el parámetro entrante tiene prioridad en el enlace personalizado final. |
| **Agregar otro parámetro de atribución** | Si lo deseas, agrega datos de atribución adicionales relacionados con el sitio web. Esto permite un análisis granular de cada instalación. | Por ejemplo, para los sitios de eCommerce, crea enlaces personalizados idénticos para cada tipo de categoría de producto, que se diferencien por los valores de af\_adset (por ejemplo: "af\_adset=fruit"). |
| **Usar parámetros de atribución predeterminados** | ◦ Selecciona cuando:  ▪ La mayoría de los visitantes del sitio web móvil son orgánicos.   ▪ Los visitantes no orgánicos no acceden al sitio web desde ad networks de clics o desde fuentes con parámetros UTM. ◦ Puedes personalizar los valores de los parámetros. | **Importante:** La mejor práctica es seleccionar UTM o parámetros de enlace de atribución entrante, ya que los parámetros de atribución de Smart Banners predeterminados se utilizan de todos modos en el enlace personalizado como alternativa si los nombres de la fuente de medios, la campaña o el canal no están disponibles. |

9. [Recomendado] Configura el parámetro de atribución por defecto **Nombre del canal** para atribuir todas las instalaciones procedentes del Smart Banner al canal especificado. Esto te permite agregar información de varias fuentes de medios bajo el mismo canal en el **reporte de cohortes**, el **dashboard general**, el **reporte de retención** y más.
10. <span id="2-banner-group-setup-step10"></span>[Opcional] Activa el **Retargeting** si planeas usar el grupo de banners para registrar los re-engagements realizados por los usuarios que hacen clic en el banner. Para obtener más información sobre el Retargeting, consulta la <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">guía de atribución de retargeting</Anchor>.

    <div id="important-1" />

    > 🚧 **Importante**
    >
    > Para que el retargeting funcione, también necesitas:
    >
    > * <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#habilitar-el-retargeting-para-la-aplicación">Habilitar el retargeting para la aplicación</Anchor>


    Los usuarios existentes que hacen clic en los enlaces de banner sin retargeting (UA) impulsados por OneLink también inician la aplicación y tienen la misma experiencia de usuario. Sin embargo, sus re-engagements se registran como sesiones habituales, lo que significa que es imposible medir el éxito de la campaña de medios.
11. [Opcional] Activa **Ignorar a los usuarios activos para el retargeting** y selecciona la ventana de inactividad. Esto agrega el parámetro af\_inactivity\_window=[número de días] a tus enlaces de grupos de Smart Banners, y todos los usuarios activos durante el periodo se ignoran para el retargeting.
12. Establece la ventana de re-engagement para determinar el período de tiempo posterior al re-engagement, donde los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting.
    * Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.
    * La ventana de reengagement se agrega al enlace en el parámetro af\_reengagement\_window.
13. <span id="dismissal-behaviour"></span>[Opcional] Configura el **Comportamiento de rechazo**, es decir, el tiempo mínimo permitido entre el rechazo de un banner del grupo por parte del usuario, hasta que el mismo banner se muestre otra vez al usuario. Selecciona una de las siguientes opciones:
    * A tiempo: 1 hora, 1 día o 1 semana.
    * Próxima sesión: es decir, la sesión que tiene lugar en una pestaña o ventana diferente, después de que el usuario cierre el banner.
    * Nunca: el banner no se muestra de nuevo. **Nota**:
      * Si el usuario borra la caché del navegador o ve el sitio en modo de navegación privada, se perderá la configuración Comportamiento de rechazo.
      * El comportamiento de rechazo se aplica al banner que el usuario desestima; aún se pueden mostrar otros banners del grupo de banners.
14. [Opcional] Configura la **limitación de frecuencia**.  La limitación de frecuencia determina cuántas veces se muestra cada banner en el grupo de banners a un usuario único. Puedes elegir entre **Sin límite** (donde siempre se muestran los banners) o **Limitar la visualización de banners**.

    Por ejemplo, si un grupo de banners consta de tres banners y el límite de frecuencia se establece en uno, cada banner del grupo aparecerá una vez por usuario. En este escenario, después de tres visitas, el usuario habrá visto los tres banners dentro del grupo. No obstante, a partir de la cuarta visita, el usuario ya no encontrará ningún banner del grupo. Cuando el límite de frecuencia se establece en dos, cada banner del grupo se mostrará dos veces por usuario, requiriendo un total de seis visitas para alcanzar el límite máximo del grupo.
15. [Opcional] Establece en qué **sistema operativo** mostrar los banners:
    * Todos los sistemas operativos móviles.
    * Solo Android o solo iOS.
16. [Opcional] **Programa** la activación del grupo de banners: empezar inmediatamente (por defecto) o configurar una campaña de tiempo limitado.
17. [Opcional] Configura las **Ubicaciones** para las que se activa el grupo de banners.
    1. <span class="af-ol-a"></span>Selecciona **En todo el mundo** para mostrar este grupo de banners a todos los usuarios. Si es necesario, excluye a los visitantes procedentes de diferentes regiones, países o estados.
    2. Selecciona la opción **Elegir una ubicación específica** para mostrar este grupo de banners a los usuarios de una o más ubicaciones específicas.
18. [Opcional] Configura **Mostrar en páginas**, es decir, en qué páginas se puede mostrar el grupo de banners a los visitantes:
    * [Predeterminado] **Mostrar en todas las páginas** del sitio web. **Nota**: Recomendamos definir al menos un grupo de banners para todas las páginas como alternativa.
    * **Mostrar en páginas específicas**: Especifica qué debe o no contener la página o URL para mostrar banners.
      * Puedes elegir:
        * **Página específica**: Especifica el host y/o la ruta de la página en la que mostrar el banner. Las consultas ingresadas no se tendrán en cuenta. Ejemplo: http://www.example.com/path?query
        * **Ruta URL y consulta**: Ingresa la ruta y/o consulta que determina si se muestra o no el banner. Ejemplo: path?query. **Nota**: No introduzcas una URL completa, como http://www.example.com/path?query. Introduce solo la ruta y/o la consulta.

* Se pueden agregar hasta 15 condiciones usando y/o.
* Si hay un conflicto entre las condiciones, el banner no se mostrará.

1. Haz clic en **Crear grupo de banners**.
2. [Opcional] Para volver a editar el grupo de banners, pasa el cursor por encima de **Targeting y comportamiento** y haz clic en **Editar**.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Mark es el marketer de un servicio de entrega de comida llamado "Feed Me". Decide crear una campaña para la venta de ciruelas de la aplicación. Mark decide usar un envío masivo de SMS, así como redes de publicidad y Google para la campaña.
>
> En preparación para la campaña, Mark:
>
> * Selecciona usar los parámetros de atribución de enlaces entrantes y los parámetros UTM (con parámetros predeterminados como alternativa para los clics que no provienen ni de un enlace entrante ni de una campaña UTM).
> * Proporciona a la red de publicidad un enlace de atribución único para usarlo en la campaña para dirigir a los usuarios a la página de venta de ciruelas en el sitio móvil Feed Me. El enlace incluye el parámetro URL de redirección (af\_r), con la URL a la página de venta de ciruelas:`http://feedme.com/plums_link`.
> * Prepara una campaña de Google Ads para los usuarios que visitan páginas en la web móvil que contienen "plums\_utm".
> * Para los SMS, agrega parámetros de atribución únicos para usarlos en el enlace de la campaña para dirigir a los usuarios a la página de venta de ciruelas en el sitio móvil de Feed Me. El enlace incluye el parámetro pid, con la URL a la página de venta de ciruelas:`http://feedme.com/plums_link?pid=sms&c=plums`.
>
> Las campañas empiezan a funcionar.
>
> Los usuarios:
>
> * Ven el anuncio de la venta de ciruelas y hacen clic para acceder al sitio móvil de Feed Me.
> * Los clics de Google Ads y los demás clics llegan a la página de aterrizaje del enlace entrante, y el Smart Banner correspondiente se activa por página.
> * Ven el Smart Banner en el sitio móvil y hacen clic en él.
> * Llegan a la aplicación Feed Me, la descargan y la instalan.
> * Al iniciar la aplicación, son dirigidos a la venta de ciruelas.
> * Se atribuyen a las fuentes de medios correctas que los llevaron al sitio móvil de Feed Me.

<div id="targeting--behavior" />

#### Targeting y comportamiento

El panel Targeting y comportamiento te muestra la configuración que estableciste para ese grupo de banners. Para editar dicha configuración, haz clic en el icono de edición.

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. Configuración de banner">

**Para crear un banner en un grupo de banners:**

1. Haz clic en **Banner nuevo** para acceder a la página **Editar banners**.
2. Configura el **Nombre** del banner.
3. Crea una **creatividad de diseño**:
   1. <span class="af-ol-a"></span>Haz clic en **Diseñar creatividad** para configurar la creatividad del banner.

      Se abre una ventana para elegir una plantilla de banner.

      [![](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)
   2. Pasa el cursor por encima de una **plantilla creativa** y haz clic en **Crear** para acceder a la página de configuración de **Crear creatividad**.
   3. Personaliza todos los elementos en la creatividad del Smart Banner. Para hacerlo, selecciona los elementos por nombre o haz clic en ellos en la imagen de vista previa. **Nota:** No todos los elementos están disponibles en todas las plantillas.
      * Título
      * Descripción
      * Estrellas de calificación
      * Botón Cerrar
      * Call to action
      * Logo de la aplicación
      * Antecedentes
      * Posición del banner
      * Relleno del banner (para ajustar el tamaño del banner)
      * Transparencia del dispositivo
      * Para imágenes, utiliza uno de los siguientes tipos de archivos: jpeg, jpg, png. **Nota**: El formato webp no es compatible.  Las recomendaciones para las imágenes son:

| Tipo de plantilla | Tamaño máximo del archivo de imagen | Proporción de imagen | Altura de la imagen | Ancho de la imagen |
| --- | --- | --- | --- | --- |
| Mínimo | 300 KB | 3:1 (ancho x alto) | 70 px | Ajustado para adaptarse al dispositivo |
| Estándar | 300 KB | 3:1 (ancho x alto) | 70 px | Ajustado para adaptarse al dispositivo |
| Mejorado | 300 KB | 9:4 (ancho x altura) | 110 px | Ajustado para adaptarse al dispositivo |
| Opción múltiple | 300 KB | 9:4 (ancho x altura) | 110 px | Ajustado para adaptarse al dispositivo |
| Promocional | 300 KB | 4:5 (ancho x altura) | 300 px | Ajustado para adaptarse al dispositivo |
| Superposición de opciones múltiples | 300 KB | 9:4 (ancho x altura) | 110 px | Ajustado para adaptarse al dispositivo |
| Intersticial | 700 KB | 9:16 (ancho x altura) | Ajustado para adaptarse al dispositivo | Ajustado para adaptarse al dispositivo |

   4. Haz clic en **Revisar** para revisar la creatividad del banner y probar su apariencia en diferentes dispositivos. **Nota**: Los banners pueden parecer ligeramente diferentes en las campañas activas en comparación con las imágenes de vista previa.
   5. Si se necesitan cambios, haz clic en **Volver al editor**.
   6. Haz clic en **Listo** para volver a la página de configuración del banner.
4. [Opcional] Agrega parámetros de atribución personalizados. Por ejemplo, `ad_adset` y `af_ad`. **Nota**: Los parametros `pid`, `c`, y `channel` no se pueden agregar a nivel de banner, ya que pertenecen al nivel de grupo de banner.
5. Tras finalizar y guardar la creatividad nueva, el estado del banner pasa a activo. Usa el conmutador de **Estado** para cambiar entre los estados **Activo** y **Pausado**.
6. Haz clic en **Guardar todo** para guardar tu trabajo o en **Guardar todo y cerrar** para guardar tu trabajo y cerrar la página de configuración del banner.

<div id="example-2" />

> 📄 **Ejemplo**
>
> Para obtener consejos y trucos, consulta nuestra <Anchor target="_blank" href="https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing">hoja de referencia sobre Smart Banners</Anchor>.

</Accordion>

<div id="4-testing" />

<Accordion title="4. Pruebas">

Una vez que la creatividad está lista, es el momento de probarla **antes** de ponerla en marcha y activarla para tus usuarios.

**Para probar una creatividad de Smart Banner:**

**Requisito previo**: Requisito previo: asegúrate de que el fragmento de código del Smart Banner esté integrado en tu sitio web.

1. En la página **Probar creatividad**, introduce el enlace a tu página web donde está integrado el SDK de Smart Banners (consulta [Smart Banners para desarrolladores](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2)).
2. Haz clic en **Generar**.
3. Copia el enlace generado y envíalo a tu dispositivo de prueba, o escanea el QR code con el dispositivo de prueba. **El enlace o QR debe redirigirte a la página web y mostrar un banner con la creatividad.**
4. Haz clic en **Editar creatividad** para volver a la configuración de la creatividad, o haz clic en **Listo** para guardar la creatividad.

</Accordion>

<div id="view-banner-performance" />

## Para ver el rendimiento del banner:

Puedes ver y comparar el rendimiento de todos tus banners en la página de rendimiento.

Puedes obtener una vista rápida del rendimiento de banners específicos en sus tarjetas de rendimiento individuales.

Los datos de rendimiento del banner incluyen:

* Impresiones
* Cierre del banner
* Clics
* Instalaciones
* Reengagements
* Reatribuciones
* Tasa de clics (CTR). Fórmula: Clics/impresiones * 100
* Tasa de conversión (CVR). Fórmula: Atribuciones/clics * 100

**Nota**:

* Los datos se basan en la zona horaria UTC.
* La actualización de los datos es <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">continua</Anchor>.
* Los datos mostrados son por banner y plantilla de OneLink. Esto significa que si tu banner y tu plantilla de OneLink están configurados para más de una aplicación (por ejemplo, una aplicación Android y una aplicación iOS), los datos de rendimiento que se muestran son para más de una aplicación.
* El CVR puede ser mayor de lo esperado, a veces incluso superior al 100%, ya que se cuentan tanto las atribuciones de visualización como las de clic.

<div id="performance-page" />

<Accordion title="Página de rendimiento">

La página de rendimiento te permite ver y comparar los datos de rendimiento de todos tus Smart Banners, hasta los últimos 90 días.

**Para ver la página de rendimiento**:

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Web-to-app** > **Smart Banners** > **Performance**.
2. Selecciona el rango de fechas para el que deseas ver el rendimiento. El rango de fechas predeterminado es de los últimos 7 días.
3. [Opcional] Activa **Mostrar solo los banners actualmente activos**. Si está activado, los datos de los banners que están en pausa o que no están activos actualmente no se muestran, incluso si estuvieron activos durante el rango de fechas seleccionado. Los datos de rendimiento se muestran para el rango de fechas seleccionado.

</Accordion>

<div id="performance-cards" />

<Accordion title="Tarjetas de rendimiento">

Puedes ver los datos de rendimiento de los últimos 7 días para cualquier banner.

**Para ver el rendimiento del banner**:

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Selecciona el workplace del sitio web y el grupo de banners para el que deseas ver el rendimiento.
3. Posiciona el cursor sobre cualquiera de los banners del grupo de banners. Se muestran los datos de rendimiento de la semana pasada.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="banner-group-display-logic" />

<Accordion title="Lógica de visualización del grupo de banners">

AppsFlyer tiene en cuenta lo siguiente al determinar qué Smart Banner mostrar o si se muestran:

* ¿Existen reglas (comportamiento de rechazo, frecuencia máxima, ubicaciones, mostrar en las páginas, etc.) configuradas para los grupos de anuncios?
* ¿El usuario final cumple con las condiciones de las reglas y califica para ver un banner?

Si la respuesta a ambas preguntas es sí, es decir, hay reglas, y el usuario califica para ver un banner, AppsFlyer elige un banner para mostrar como se explica en la siguiente tabla.

| Configuración del grupo de banners | Qué banners se muestran | Ejemplo |
| --- | --- | --- |
| Grupo de banners individuales | AppsFlyer divide uniformemente la visualización de todos los banners activos en todos tus grupos de banners entre todos los usuarios elegibles. | • Ejemplo 1: Hay 1 banner activo. Se muestra a todos los usuarios.<br /><br />• Ejemplo 2: Hay 2 banners. El 50% de los usuarios ve el banner 1 y el otro 50% ve el banner 2.<br /><br />• Ejemplo 3: Hay 3 banners, 1/3 de los usuarios elegibles ven cada banner.<br /><br />• Ejemplo 4: No hay banners activos. No se muestra nada. |
| Varios grupos de banners con reglas idénticas | AppsFlyer divide uniformemente la visualización de todos los banners activos en todos tus grupos de banners entre todos los usuarios elegibles. | Hay 2 grupos de banners (A y B), cada uno con 3 banners (con un total de 6 banners). 1/6 de los usuarios elegibles ven cada uno de los banners. |
| Varios grupos de banners con varias reglas | AppsFlyer divide uniformemente la visualización de todos los banners activos *del grupo de banners con reglas que describen y coinciden más específicamente con los usuarios*. Si los grupos de banners son igualmente específicos de diferentes formas, se muestran los banners de todos estos grupos de banners. | • Ejemplo 1: Hay 2 grupos de banners, A y B. El grupo de banners A está configurado para mostrarse en todo el mundo, y el grupo de banners B está configurado para mostrarse en Japón. El grupo de banners B es más específico, por lo que solo los banners de ese grupo se muestran a los usuarios de todo el mundo (excepto a los usuarios de Ucrania). Si el grupo de banners B no tiene banners activos, no se muestra nada.<br /><br />• Ejemplo 1: Hay 2 grupos de banners, A y B. El grupo de banners A está configurado para mostrarse en todo el mundo y el grupo de banners B está configurado para mostrarse en Japón. El grupo de banners B es más específico, por lo que solo los banners de ese grupo se muestran a los usuarios de Japón. Si el grupo no tiene banners activos, no se muestra nada.<br /><br />• Ejemplo 3: Hay 2 grupos de banners, A y B. El grupo de banners A se mostrará en Japón y el grupo de banners B se mostrará en abril. Ambos grupos de banners son igualmente específicos, pero de diferentes maneras. Por lo tanto, en Japón, en abril, se muestran banners de ambos grupos de banners, ya que ninguno de los dos tiene prioridad sobre el otro. |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="Pruebas A/B del rendimiento de banners">

Puedes realizar pruebas A/B de los banners comparando su rendimiento en el dashboard de rendimiento. Para obtener datos adicionales relacionados con la atribución, se recomienda agregar el `af_adset` , `af_ad` u otros parámetros de atribución (excepto`pid`,`c`, y`channel`) con un valor único para cada creatividad de banner o grupo de banners. Utiliza esos parámetros para comparar el rendimiento de cada grupo de banners cuando visualices datos en los dashboards y reportes de AppsFlyer.

</Accordion>

<div id="faq" />

## Preguntas frecuentes

<div id="why-does-my-banner-not-display" />

<Accordion title="¿Por qué no se muestra mi banner?">

Esto se debe a la frecuencia máxima establecida en tu grupo de banners. La limitación de frecuencia determina cuántas veces se muestra el banner a un usuario único. Por ejemplo, si la frecuencia máxima está establecida en tres y un usuario visita el sitio cuatro veces, el usuario ve el banner en las primeras 3 visitas, pero no en la cuarta ni en las posteriores. La frecuencia máxima se puede deshabilitar. Selecciona un valor de frecuencia máxima o desactiva la frecuencia máxima.

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="¿Puedo usar mi propia fuente para mi banner?">

Sí. puedes configurar tu propia fuente utilizada en tu sitio web para tu banner, siguiendo las [instrucciones disponibles en el centro de desarrollo](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font).

* Requiere un desarrollador de sitios web para su implementación.
* La fuente se aplicará a todos los banners del sitio web y a todos los elementos de texto dentro del banner.
* La fuente no se puede ver en el editor creativo.
* Después de implementarlo, [prueba tu banner creativo](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing).
* Si la fuente no se muestra correctamente, vuelve a enviar tu banner en el [editor creativo](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="¿Puedo agregar parámetros a la URL de mis Smart Banners?">

Sí, invocando las dos funciones siguientes en tu smart script:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">showBanner</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="¿Los Smart Banners admiten deep linking?">

Sí. Para ello, agrega el <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">parámetro deep\_link\_value</Anchor> de una de las siguientes formas:

* En la IU de AppsFlyer, agrega un parámetro de atribución estático personalizado durante la [configuración del banner](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).
* Utiliza additionalParams en la función [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) para agregar el parámetro a la URL antes de mostrar el banner.
* Utiliza la función <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor> para agregar el parámetro a la URL después de que aparezca el banner.

Asegúrate de que tu desarrollador implemente el comportamiento deseado del deep\_link\_value.

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="¿Los Smart Banners pueden mostrar contenido diferente en función de si los usuarios tienen la aplicación instalada o no?">

N.º Si no sabes si los usuarios tienen o no la aplicación, te recomendamos que realices la llamada a la acción correspondiente a ambos. Por ejemplo: "Ir a la aplicación" o "Abrir la aplicación".

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="¿Los parámetros de URL entrantes originales permanecen disponibles para la URL de Smart Banner cuando los usuarios se alejan de la landing page del banner y luego regresan a ella?">

Sí. Si la URL entrante original contiene un parámetro utm\_source o pid, la URL original se guarda durante la sesión de navegación y los parámetros se aplican a la URL del banner de salida.

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="¿Puedo configurar mis banners para que se muestren en mi sitio móvil, pero no en mi aplicación wrapper/híbrida?">

Sí. Para hacerlo, cuando implementes Smart Banners en una aplicación wrapper/híbrida y cargues la página del banner desde la aplicación (y no desde un navegador web), no uses la función [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=), ya que esta muestra el banner en la aplicación. Alternativamente, usa la función <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner">hideBanner</Anchor>.

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="¿Los Smart Banners admiten la accesibilidad web?">

Estamos comprometidos a garantizar que todos tus usuarios, incluidos los que tienen discapacidades, puedan acceder e interactuar plenamente con los Smart Banners.

Como tal, tratamos de hacer que la accesibilidad web de nuestros Smart Banners sea compatible y seguimos las mejores prácticas estándar WCAG 2.1 al proporcionar los atributos HTML relevantes en los elementos de Smart Banner.

Sin embargo, determinar los requisitos de accesibilidad relevantes para tus propios usos previstos de dichos Smart Banners es tu exclusiva responsabilidad. Tú eres el único responsable de garantizar que los Smart Banners que utilices sigan siendo accesibles para todos los usuarios, de acuerdo con los requisitos relevantes de accesibilidad web.

Ten en cuenta que varios cambios en el Smart Banner pueden afectar su compatibilidad con los requisitos de accesibilidad relevantes, incluyendo, por ejemplo, al editar los colores y el tamaño de los elementos internos del banner.

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

<Accordion title="Si se elimina un Smart Banner de un grupo de banners, ¿se eliminarán también los datos asociados con ese grupo de banners?">

N.º Los datos de atribución no se eliminan si se elimina un Smart Banner.

</Accordion>

<div id="troubleshooting--traits-and-limitations" />

## Solución de problemas, características y limitaciones

| Caducado | Nota |
| --- | --- |
| División de la visualización de banners | AppsFlyer divide uniformemente la visualización de banners activos para los usuarios. No es posible seleccionar qué banners específicos mostrar más o menos. Por ejemplo, si hay 2 banners en un grupo, cada uno se muestra al 50% de los usuarios. No se puede cambiar a una división de 70%-30%. |
| Parámetros personalizados | • Los siguientes caracteres especiales no están permitidos en los parámetros personalizados: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, / • Si defines un parámetro usando uno de estos caracteres especiales, el parámetro no se guarda. |
| Cambio de nombre | Se pueden cambiar los nombres de los grupos de banners y los nombres de los banners. Los datos de rendimiento no se ven afectados y se mantienen. |
| Número de clics/cierres de botones | Los datos están disponibles a partir del 17 de febrero de 2026. Los datos se conservan durante 90 días. |
| Página específica | Cuando configuras tu grupo de banners para mostrar banners en una página específica, la regla de banners solo aplica al host/ruta que ingreses. Si no hay una coincidencia perfecta (por ejemplo, si la página de tu sitio tiene cadenas adicionales no incluidas en la configuración de la regla), la regla no aplica. |
| Tablets | • Los Smart Banners están diseñados para dispositivos móviles y es posible que sus resoluciones no estén optimizadas para tablets con pantallas grandes. • Es posible que los navegadores de las tablets no se reconozcan como dispositivos móviles. |
| El banner se muestra junto a un área vacía. | Cuando encuentres este comportamiento, evalúa su causa utilizando los siguientes criterios:<ul><li>Verifica que el fragmento de código del SDK no se haya implementado más de una vez en la página web.</li><li>Asegúrate de que la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">`showBanner`</Anchor> función no se ha implementado varias veces.</li></ul> |

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=nota smart-banners=banners-inteligentes h_01HB5W700PWY5G45BYNWPKAC52=banners-inteligentes h_01HB5W700QQMYSEFBBXVJ97M0M=ejemplo h_01HB5W700QGWTWDXBNB2GAPQ3B=importante setup=configuraci%C3%B3n h_01HB5W700QVNYJT48VAP9Y7HQS=configuraci%C3%B3n h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=para-preparar-tu-sitio-m%C3%B3vil-para-mostrar-smart-banners-por-primera-vez h_01HB5W700QE7MDBSN5GH4E7ABR=para-preparar-tu-sitio-m%C3%B3vil-para-mostrar-smart-banners-por-primera-vez to-create-website-workplaces-after-the-first-time=para-crear-workplaces-del-sitio-web-despu%C3%A9s-de-la-primera-vez h_01HB5W700Q57WXKFSWXNF22QZ1=para-crear-workplaces-del-sitio-web-despu%C3%A9s-de-la-primera-vez h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=importante-1 h_01HB5W700QYJ9NR5F4VT59NG2Q=ejemplo-1 targeting-behavior=targeting-y-comportamiento h_01HB5W700QYC48YTJY9B8JT0XM=targeting-y-comportamiento h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=ejemplo-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=para-ver-el-rendimiento-del-banner h_01HB5W700Q6WHMVFNSVM2E9JXN=para-ver-el-rendimiento-del-banner h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=informaci%C3%B3n-adicional h_01HB5W700Q9XD8MGEK0B3ZZJS3=informaci%C3%B3n-adicional h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance faq=preguntas-frecuentes h_01HB5W700Q90F1KMASF94EZWEM=preguntas-frecuentes h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility h_01JSVH17EH97S8B7EBCD4QHS1Q=if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed traits-and-limitations=soluci%C3%B3n-de-problemas-caracter%C3%ADsticas-y-limitaciones h_01HB5W700RXHC22QGXDX4GG1AR=soluci%C3%B3n-de-problemas-caracter%C3%ADsticas-y-limitaciones" />
