---
title: 'Optimización Creativa: integraciones de partners'
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-08-12T11:50:13Z'
  id: 18565403047569
  locale: es
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/es/articles/18565403047569
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Configura integraciones de partners para importar automáticamente todos tus datos creativos a Optimización Creativa.

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

<div id="about-partner-integrations" />

## Sobre las integraciones de partners

Una integración de partners importa de manera fluida y continua tus creatividades desde las campañas ejecutadas a través del partner hacia la <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide">Optimización Creativa</Anchor>.

<div id="data-availability" />

### Disponibilidad de datos

Una vez que se agrega una integración de partner:

* El sistema rellena los datos de las creatividades y del rendimiento de AppsFlyer de los últimos 90 días. Por lo general, los datos están disponibles en Optimización Creativa dentro de las 24 horas.
* Los datos de creatividades se siguen extrayendo de los partners integrados dos veces al día, todos los días. Los datos se incorporan y se comparan con otros puntos de datos de rendimiento de AppsFlyer, como atribución, gasto, clics, impresiones, ingresos, etc. (Los datos de rendimiento de AppsFlyer se actualizan cada hora). Los **dashboards de optimización creativa muestran los datos combinados de todos los procesos anteriores y se actualizan una vez al día** **en UTC + 10** (se actualizan todos los datos creativos de los últimos 90 días).

<div id="note" />

> 📘 **Nota**
>
> Para ver los datos de costos de AppsFlyer (como el ROAS), se requiere una <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">suscripción a ROI360</Anchor>.

<div id="media-partner-integrations" />

## Integraciones de partners de medios

Esta sección describe cómo configurar integraciones con cada partner.

<div id="adikteev" />

<Accordion title="Adikteev">

**Requisitos previos:**

* Credenciales para la integración:
  * Correo electrónico (nombre de usuario de Adikteev)
  * Contraseña de Adikteev
  * **Nota:** Estas deben ser las mismas credenciales utilizadas para acceder a tu dashboard de Adikteev.
* Para que podamos extraer todos los datos de costos de Adikteev, el mismo usuario que integró <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">ROI360</Anchor> debería ser el que integre también la Optimización Creativa.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮ en la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Adikteev**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce el correo electrónico y la contraseña.
6. Haz clic en **Guardar**.

**Nota:** Adikteev también es conocido como Trademob (trademob\_int).

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**Requisito previo:**

* Credencial para la integración:
  * Token  
    Contacta con tu gerente de cuenta de Adjoe para obtener el token. Lee la <Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">documentación de Adjoe</Anchor>

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista de **partners**, selecciona **Adjoe GmbH**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce el token.
6. Haz clic en **Guardar**.

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**Requisitos previos:**

* Permisos de cuentas publicitarias para las aplicaciones relevantes que deseas integrar. **Nota**: La autenticación en AppLovin debe ser realizada por el administrador de la cuenta.
* Se requiere un **ID de cuenta**, **clave de API de gestión de campañas** y **clave de API de reportes** de AppLovin. Puedes obtenerlos desde tu dashboard de AppLovin Axon (haz clic en tu cuenta en la parte superior derecha y selecciona las claves).

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:

   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.

   ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en + **Nueva integración**.
3. En la lista **Partner**, selecciona **AppLovin**.
4. Selecciona las aplicaciones que estás promocionando.
5. Ingresa el **ID de cuenta** de AppLovin, la **clave de la API de gestión de campañas** y la **clave de la API de reportes**.
6. Luego haz clic en **Guardar**.

<div id="note-1" />

> 📘 **Nota**
>
> La API de reportes a nivel de activos de AppLovin solo devuelve datos del día anterior. No admite períodos de lookback históricos. Por este motivo, cuando activas la integración, AppsFlyer solo puede empezar a recopilar datos a nivel de recurso a partir de la fecha de activación. Como resultado, la cobertura completa de los datos se genera de forma gradual y, por lo general, se completa en un plazo de 30 días desde la activación.

</Accordion>

<div id="google-ads" />

<Accordion title="Anuncios de Google">

**Requisitos previos:**

* Permisos de administrador de cuentas publicitarias para las aplicaciones relevantes que deseas integrar.
* Para que podamos extraer todos los datos de creatividades de Google, el mismo usuario que integró <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">ROI360</Anchor> debería ser el que integre también la Optimización Creativa. Si no hay una suscripción a ROI360, entonces debes tener permisos de administrador para todas las aplicaciones y cuentas de anuncios relevantes en Google AdWords.

**Nota:**

* La integración con Google Ads es por usuario, lo que significa que varios usuarios pueden tener integraciones activas simultáneamente.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en + **Nueva integración**.
3. Haz clic en la lista **Partner** y selecciona **Google Ads (AdWords).**
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión en Google**. Se abre la ventana **Iniciar sesión con Google.**
6. Completa el inicio de sesión de Google y proporciona tus permisos. Ten en cuenta que para que AppsFlyer extraiga datos completos, se recomienda que tengas permisos completos.
7. Haz clic en **Guardar**.

**Nota:** Solo admitimos los tipos de anuncios de campañas UAC (ACi, ACe y ACpre). Los datos de los tipos de anuncios no compatibles estarán disponibles en la Optimización Creativa solo en el nivel de anuncio (no en el nivel creativo).

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**Requisitos previos:**

* Credenciales de ironSource para la integración:
  * Clave secreta
  * Token de actualización
  * <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">Descubre</Anchor> dónde encontrar tus credenciales únicas.
* Un rol de usuario Administrador o Colaborador en ironSource. <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">Aprende a configurar los roles de usuario</Anchor>.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **IronSource**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce la clave secreta y el token de actualización.
6. Haz clic en **Guardar**.

**Nota:** Ciertos tipos de anuncios no son compatibles, lo que significa que sus datos en la Optimización Creativa están disponibles solo a nivel de anuncio (no a nivel creativo). Los tipos de anuncios no admitidos incluyen anuncios de Offerwall.

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Liftoff**.
4. Selecciona las aplicaciones que estás promocionando.
5. Contacta con tu CSM de Liftoff para obtener tu nombre de usuario y contraseña de la API de reportes de Liftoff.
6. Haz clic en **Guardar**.

</Accordion>

<div id="facebook-ads" />

<Accordion title="Anuncios de Meta">

**Requisitos previos:**

* Permisos de cuentas publicitarias para las aplicaciones que deseas integrar. **Nota**: La integración con Meta Ads es por usuario, lo que significa que varios usuarios pueden tener integraciones activas simultáneamente.
* Para extraer creatividades que se muestran en páginas internas o externas de Facebook, asegúrate de que el administrador de Facebook Business Center proporcione los permisos necesarios al usuario que configura la integración con Creative.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista de **partners**, selecciona **Meta Ads**.
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión con Meta Ads**.
6. Completa el inicio de sesión y proporciona tus permisos. **Nota**: Para que AppsFlyer extraiga datos completos, te recomendamos que tengas permisos completos.
7. Haz clic en **Guardar**.

**Notas:**

* Debido a que los Meta Flexible Ads proporcionan solo un activo para reportes, solo se muestra el rendimiento asociado con el activo de mejor rendimiento (de un anuncio).
* Ciertos tipos de anuncios no son compatibles, lo que significa que sus datos en la Optimización Creativa están disponibles solo a nivel de anuncio (no a nivel creativo). Los tipos de anuncios no admitidos incluyen anuncios de colecciones y anuncios de compras.

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**Requisitos previos:**

* Credenciales de Mintegral para la integración:
  * Clave de la API
  * Clave de acceso
  * <Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">Descubre</Anchor> dónde encontrar tus credenciales únicas.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Mintegral**.
4. Selecciona las aplicaciones que estás promocionando.
5. Ingresa la **clave de la API** y la **clave secreta**.
6. Haz clic en **Guardar**.

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**Requisitos previos:**

* Para poder extraer las creatividades, necesitarás un rol en Moloco de <Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">"Workplace Owner" o "Ad Account Owner"</Anchor>.
* Acceso a tu clave API de Moloco.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el icono ⋮ en la parte superior derecha del dashboard para acceder a **Integraciones Creativas**.![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Moloco**.
4. Selecciona las aplicaciones que estás promocionando.
5. Ingresa tu clave API de Moloco.
6. Haz clic en **Guardar**.

**Nota**:

* Ciertos tipos de anuncios no son compatibles, lo que significa que sus datos en la Optimización Creativa están disponibles solo a nivel de anuncio (no a nivel creativo). Los tipos de anuncios no admitidos incluyen anuncios de CTV.

</Accordion>

<div id="personaly" />

<Accordion title="Persona.ly">

**Requisitos previos:**

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     <Image alt="Icono de menú principal y barra de filtros.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Haz clic en **+ Nueva integración**.
3. En la lista de **Partners**, selecciona **Persona.ly**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce la **clave API** de Persona.ly (puedes obtenerla en tu cuenta de Persona.ly).
6. Haz clic en **Guardar**.

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**Requisitos previos:**

* Para poder extraer contenido creativo, necesitas tener un rol de "Creador" o "Administrador" de Reddit.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Reddit**.
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión con Reddit**.
6. Completa el inicio de sesión y proporciona tus permisos. **Nota**: Para que AppsFlyer extraiga datos completos, te recomendamos que tengas permisos completos.
7. Haz clic en **Guardar**.

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**Requisitos previos:**

* Credenciales para la integración (**Nota**: Estas son las mismas credenciales que se utilizan para acceder al dashboard de Remerge. Consulta la <Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">documentación de Remerge</Anchor>):
  * Correo electrónico del usuario
  * Contraseña

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el icono ⋮ en la parte superior derecha del dashboard para acceder a **Integraciones Creativas**.![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Remerge**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce el correo electrónico y la contraseña.
6. Haz clic en **Guardar**.

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**Requisitos previos:**

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     <Image alt="Icono de menú principal y barra de filtros.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Haz clic en **+ Nueva integración**.
3. En la lista de **Partners**, selecciona **Reddit**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce la **clave API** de RevX (ponte en contacto directamente con tu gestor de cuenta de RevX para obtenerla).
6. Haz clic en **Guardar**.

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**Requisitos previos:**

* Credenciales de Smadex para la integración (**Nota**: Éstas son las mismas credenciales que se utilizan para acceder a tu dashboard de Smadex):
  * Correo electrónico
  * Contraseña

**Para agregar una integración:**

1. **Inicia sesión en Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el icono ⋮ en la parte superior derecha del dashboard para acceder a **Integraciones Creativas**.![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista de **partners**, selecciona **Smadex**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce las credenciales requeridas.
6. Haz clic en **Guardar**.

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

**Requisitos previos:** Permisos de cuentas publicitarias para las aplicaciones relevantes que deseas integrar. **Nota**: La integración con Snapchat es por usuario, lo que significa que varios usuarios pueden tener integraciones activas simultáneamente.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista de **Partners**, selecciona **Snapchat**.
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión con Snapchat**. Se abre la **ventana.**
6. Completa el inicio de sesión y proporciona tus permisos. Ten en cuenta que para que AppsFlyer extraiga datos completos, se recomienda que tengas permisos completos.
7. Haz clic en **Guardar**.

**Nota:** Ciertos tipos de anuncios no son compatibles, lo que significa que sus datos en la Optimización Creativa están disponibles solo a nivel de anuncio (no a nivel creativo). Los tipos de anuncios no admitidos incluyen anuncios de colección.

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**Requisitos previos:**

* Permisos de cuentas publicitarias para las aplicaciones relevantes que deseas integrar. **Nota**: La integración con TikTok es por usuario, lo que significa que varios usuarios pueden tener integraciones activas simultáneamente.
* Para extraer datos creativos de Spark Ads, asegúrate de que el administrador de TikTok Business Center proporcione los permisos necesarios al usuario que configura la integración con Creative.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **TikTok**.
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión con TikTok**. Se abre la **ventana.**
6. Completa el inicio de sesión y proporciona tus permisos. Ten en cuenta que para que AppsFlyer extraiga datos completos, se recomienda que tengas permisos completos.
7. Haz clic en **Guardar**.

<div id="notes" />

> 📘 **Notas**
>
> * El 30 de enero de 2023, se agregó la nueva integración `tiktokglobal_int` de **TikTok for Business—Advanced SRN**, mientras que la integración `bytedanceglobal_int` de **TikTok for Business [Legacy]** se está eliminando gradualmente y quedará obsoleta en marzo de 2024. Más información en este <Anchor target="_blank" href="/marketers/es/docs/bulletin-tiktok-for-business-advanced-srn">boletín</Anchor>.
>   * Si la antigua integración (bytedanceglobal\_int) sigue activa después de que se integre la nueva (tiktokglobal\_int), habrá una duplicación de datos de rendimiento en Optimización Creativa, ya que se extraerán de ambas redes.
>   * Los elementos creativos no se duplicarán ya que la IA identifica los activos reales.
>   * Eliminar la antigua integración no eliminará los datos históricos del producto.
>   * Para extraer todos los datos necesarios, quien conecta TikTok SRN debe tener los permisos necesarios (se recomienda un administrador de cuenta publicitaria).
> * Ciertos tipos de anuncios no son compatibles, lo que significa que sus datos en la Optimización Creativa están disponibles solo a nivel de anuncio (no a nivel creativo). Los tipos de anuncios no admitidos incluyen:

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**Requisitos previos:**

* Credenciales de la cuenta de servicio de Unity para la integración:
  * ID de clave
  * Clave secreta
  * ID principal de organización

[Consulta las instrucciones para recuperar las credenciales.](/docs/creative-optimization-partner-integrations#instrucciones-para-recuperar-las-credenciales)

* Los siguientes roles de cuenta de servicio (organización) seleccionados dentro de Unity:
  * El rol de **Administrador de la API de Publicidad** es necesario para extraer creatividades.
  * El rol de **Visualizador de Estadísticas de la API de Anunciantes** es necesario si deseas extraer métricas de Unity (además de creatividades). <Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">Saber más</Anchor>

**Nota:** Si estos roles no están disponibles para ti, por favor contacta a tu CSM de Unity Ads.

<div id="instructions-for-retrieving-the-credentials" />

#### Instrucciones para recuperar las credenciales

**Para recuperar el ID de clave y la clave secreta:**

1. Inicia sesión en Unity Ads.
2. En el panel lateral del menú principal, haz clic en **Administración** y luego en **Cuentas de servicio**.
3. Haz clic en la cuenta de servicio específica.
4. Haz clic en **+ Agregar clave**.  
   Esto muestra el ID de clave y la clave secreta.
5. Copia el **ID de clave** y la **clave secreta**.  
   ![Unity: imagen.jpg para obtener el ID de clave & la clave secreta](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

**Para** **recuperar el** <Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**ID core de la organización:**</Anchor>

1. Dentro de Unity Ads, haz clic en **Productos** en el menú lateral.
2. Haz clic en **Crecer**.  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. Haz clic en **Adquisición de usuarios de Unity Ads**.  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. Haz clic en **Configuración**.  
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. Copia el **ID core de la organización**.

<div id="to-select-a-service-account-organization-role" />

#### **Para seleccionar un rol de cuenta de servicio (organización):**

1. En el dashboard de Unity, haz clic en **Administración**.  
   **<Image alt="Org roles step 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. Haz clic en **Cuentas de servicio**.
3. Haz clic en la cuenta de servicio correspondiente y luego en **+ Administrar roles de la organización**.  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. En el menú desplegable **Growth**, selecciona los siguientes roles de organización de la cuenta de servicio:
   * **Advertisers API Stats Viewer**, para extraer métricas de Unity.
   * Uno de los otros roles a continuación, para atraer a las creatividades:
     * Advertise API Admin
     * Advertise API Viewer
     * Editor de paquetes de creatividades de la API de anuncios  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. Haz clic en **Guardar**.

**Nota:** Si no tienes acceso a estos roles, contacta con tu Customer Success Manager de Unity o envía un correo electrónico a [unityads-support@unity3d.com](mailto:unityads-support@unity3d.com) para solicitar los permisos necesarios.

<div id="to-add-a-unity-integration-to-the-creative-dashboard" />

#### **Para agregar una integración de Unity al dashboard de creatividades:**

1. En el dashboard de **Optimización Creativa**, realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **Unity Ads**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce el ID de clave, la clave secreta y el ID principal de la organización.
6. Ingresa la información de las <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide#partner-metrics::e592ecd3">métricas del partner</Anchor> para obtener también las métricas reportadas por Unity Ads (opcional).
7. Haz clic en **Guardar**.

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads (anteriormente Twitter Ads)">

**Requisitos previos:**

* Para poder extraer creatividades, necesitas tener un rol de "Administrador de cuenta" o "Administrador de anuncios" de X Ads.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     <Image alt="Icono de menú principal y barra de filtros.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **X Ads**.
4. Selecciona las aplicaciones que estás promocionando.
5. Haz clic en **Iniciar sesión con X Ads**.
6. Completa el inicio de sesión y proporciona tus permisos. **Nota**: Para que AppsFlyer extraiga datos completos, te recomendamos que tengas permisos completos.
7. Haz clic en **Guardar**.

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**Requisito previo:**

Credenciales de YouAppi para la integración:

* Token  
  **Nota**: Puedes contactar con el administrador de tu cuenta en YouAppi para obtener el token. Para más información, consulta la <Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">documentación de YouAppi</Anchor>.

**Para agregar una integración:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮  de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     ![Icono de menú principal y barra de filtros.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Haz clic en **+ Nueva integración**.
3. En la lista **Partner**, selecciona **YouAppi**.
4. Selecciona las aplicaciones que estás promocionando.
5. Introduce el token.
6. Haz clic en **Guardar**.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="creative-integrations-dashboard" />

<Accordion title="Dashboard de integraciones creativas">

El dashboard de integraciones creativas es donde puedes agregar nuevas integraciones de partners de medios. Para agregar una nueva integración, sigue las [instrucciones específicas de cada partner](/docs/creative-optimization-partner-integrations#disponibilidad-de-datos).

Una vez agregado, el dashboard muestra el estado de todas tus integraciones actuales, con las siguientes columnas:

| Columna | Descripción |
| --- | --- |
| Fuente de medios | El nombre del partner integrado, por ejemplo, Meta Ads o ironsource\_int. Expande la columna de partner para ver todas las diferentes conexiones del partner. Por ejemplo, cada usuario podría tener su propia conexión. |
| Aplicación | La lista de aplicaciones por partner integrado y conexión de usuario específica. |
| Actualización de integración | La fecha en que se actualizaron por última vez las configuraciones de integración de partner. |
| Estado de la cobertura | La cantidad de datos de rendimiento creativo de la integración de partner disponibles en los dashboards y reportes de Optimización Creativa:<ul><li>**Baja**: A todas las aplicaciones incluidas en esta integración les faltan datos.</li><li>**Parcial**: A algunas aplicaciones incluidas en esta integración les faltan datos.</li><li>**Alta**: Todas las aplicaciones incluidas en esta integración tienen datos.</li><li>**En curso**: Espera hasta 24 horas para obtener una actualización del estado.</li><li>**No hay datos**: No hay datos de este partner durante los últimos 30 días.</li></ul>Haz clic en el estado para ver el desglose del estado de cobertura por aplicación. El estado por aplicación significa diferentes cosas dependiendo de si eres suscriptor de ROI360 o no.<br /><br />**Para no suscriptores de ROI360:**<ul><li>**Alta**: La aplicación tiene muchos datos disponibles. Esto significa que las creatividades retiradas cubren más del 85% del total de instalaciones de aplicaciones (según lo informado por AppsFlyer) en los últimos 30 días.</li><li>**Baja**: Faltan datos en la aplicación. Lo que significa que las creatividades retiradas cubren menos del 85% del total de instalaciones de aplicaciones (según lo informado por AppsFlyer) en los últimos 30 días.</li></ul>**Para suscriptores de ROI360:**<ul><li>**Alta**: Las creatividades cubrieron más del 85% del costo medido por AppsFlyer ROI360 en los últimos 30 días.</li><li>**Baja**: Los anuncios creativos retirados cubrieron menos del 85% del costo medido por AppsFlyer ROI360 en los últimos 30 días.<br />**Ejemplo**:<ul><li>AppsFlyer obtiene datos para la fuente de medios "Red A" con un gasto total en anuncios de $100.</li><li>La Creatividad 1 tuvo un gasto en anuncios de $85 y la Creatividad 2 tuvo $15.</li><li>Si AppsFlyer extrae datos de la Creatividad 1, eso cubre el 85% del costo, por lo que es una cobertura "alta".</li><li>Si AppsFlyer extrae solo datos de la Creatividad 2, eso cubre solo el 15% del costo, por lo que es una cobertura "baja".</li></ul></li></ul>**Tanto para suscriptores de ROI360 como para no suscriptores de ROI360:**<ul><li>**En curso**: Espera hasta 24 horas para obtener una actualización del estado.</li><li>**Pocos datos**: Asegúrate de que el partner esté integrado correctamente, siguiendo las [instrucciones específicas del partner](/docs/creative-optimization-partner-integrations#disponibilidad-de-datos).</li><li>**No hay datos**: No hay datos de esta aplicación durante los últimos 30 días.<ul><li>Asegúrate de que la configuración general de AppsFlyer esté completa y funcionando (no específicamente para Creative).</li><li>Asegúrate de que tu aplicación esté activa y haya tráfico.<br />Si la integración la gestiona una agencia, asegúrate de que la integración sea correcta, siguiendo las [instrucciones de la agencia](/docs/creative-optimization-partner-integrations#agencies).</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="Integraciones con agencias">

<div id="add-an-agency-integration" />

#### Agrega una integración de agencia

Puedes integrarte con los partners de tu agencia para extraer tus datos en el dashboard de creatividades.

**Para agregar una integración de agencia:**

1. Inicia sesión en **Optimización Creativa** y realiza una de las siguientes acciones:
   * Si no tienes ninguna integración de partner, haz clic en + **Agregar nueva integración**.
   * De lo contrario, haz clic en el ícono ⋮ de la parte superior derecha del dashboard para acceder a **Integraciones creativas**.  
     <Image alt="Icono de menú principal y barra de filtros.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Haz clic en **+Nueva integración**.
3. Después de seleccionar el partner y las aplicaciones en la ventana de integración de partners, haz clic en **Configuración avanzada: Menú desplegable de la Agencia** y selecciona la agencia relevante.  

   <Image alt="Agencias creativas.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. Haz clic en **Guardar**.  
   Se añade la integración de la agencia.

**Notas:**

* Para cada agencia cuyos datos de creatividades desees ver en el dashboard, deberás crear una integración de partner separada con la casilla de verificación "Agencia" seleccionada.
* Los datos están disponibles únicamente en el caso de agencias transparentes. <Anchor target="_blank" href="/marketers/es/docs/view-agency-data">Saber más</Anchor>
* Los datos de creatividades se extraerán únicamente de la agencia. Esto significa que si has seleccionado Google Ads como partner, como en el ejemplo anterior, pero también tienes campañas ejecutándose directamente con Google Ads, necesitarás crear una integración de partner adicional para Google Ads.

<div id="grant-dashboard-access-to-an-agency" />

#### Concede acceso al dashboard a una agencia

Puedes conceder a tus agencias acceso para ver sus propios datos de rendimiento creativo en el dashboard de Optimización Creativa si tienen una <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts">cuenta de agencia</Anchor> de AppsFlyer. Esto podría servir para mejorar la transparencia y la colaboración.

**Para habilitar el acceso:**

1. Desde el menú lateral de AppsFlyer, haz clic en **Colaborar** > **Partner Marketplace**  

   **<Image alt="From Collaborate click Partner Marketplace.png" src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. Busca la agencia asociada relevante en la barra de búsqueda en la parte superior de la página, luego haz clic en el partner.

   <Image alt="Search bar.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. En la página del partner, ve a la pestaña **Permisos** y habilita **Permisos de agencia**.

   <Image alt="Agency permissions.png" src="https://files.readme.io/b307601f9b41800a146c664bdd9f6d24a5398be9022801505419aebb0741162c-39258856594705.png" width="71.31%" />
4. Luego habilita **Acceso al dashboard de Optimización Creativa**  

   La agencia ahora tendrá acceso para ver tus creatividades compartidas en su dashboard. Para las agencias que aún no han configurado una cuenta de agencia de AppsFlyer y les gustaría hacerlo, pueden aprender más <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding">aquí.</Anchor>

</Accordion>

<div id="update-credentials" />

<Accordion title="Actualizar credenciales">

Una vez que se configuran ciertas integraciones de partners, sus credenciales a nivel de cuenta no se pueden cambiar (esto no se aplica a Meta Ads, Google Ads, TikTok y AppLovin). Si necesita actualizar las credenciales de un partner:

1. En la página **Integraciones Creativas**, selecciona el expansor a la izquierda del partner para abrir sus conexiones.
2. Haz clic en el icono de menú <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> a la derecha de la conexión, luego haz clic en **Eliminar integración**. ![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. Crea una nueva integración para el partner con las credenciales actualizadas.

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=sobre-las-integraciones-de-partners h_01HAP6JQEFKAFK96WDBN0MERB6=sobre-las-integraciones-de-partners media-partner-integrations=disponibilidad-de-datos h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=disponibilidad-de-datos h_01K4M4JF53A3J1R5VACNVN4X8A=nota h_01HC7W736NDRRAJ95Z28JS2J46=integraciones-de-partners-de-medios h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=nota-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=notas 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads instructions-for-retrieving-the-credentials=instrucciones-para-recuperar-las-credenciales h_01GT6Z998RCBQWKDC9YGPJQGN6=instrucciones-para-recuperar-las-credenciales to-select-a-service-account-organization-role=para-seleccionar-un-rol-de-cuenta-de-servicio-organizaci%C3%B3n h_01GT6ZFTGKMR18DTNVX706DH1R=para-seleccionar-un-rol-de-cuenta-de-servicio-organizaci%C3%B3n to-add-a-unity-connection-to-the-creative-dashboard=para-agregar-una-integraci%C3%B3n-de-unity-al-dashboard-de-creatividades h_01GT6ZS52ZWY47BCT2NJVCFFEP=para-agregar-una-integraci%C3%B3n-de-unity-al-dashboard-de-creatividades 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=informaci%C3%B3n-adicional h_01HC7WCZ143S29PGTVNFEX962Y=informaci%C3%B3n-adicional 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies add-an-agency-integration=agrega-una-integraci%C3%B3n-de-agencia h_01K5PE1K1G75KEF9HXMAW9YP2F=agrega-una-integraci%C3%B3n-de-agencia grant-dashboard-access=concede-acceso-al-dashboard-a-una-agencia h_01K5PE1WK5AE2MX235B8FA4YJ0=concede-acceso-al-dashboard-a-una-agencia 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />
