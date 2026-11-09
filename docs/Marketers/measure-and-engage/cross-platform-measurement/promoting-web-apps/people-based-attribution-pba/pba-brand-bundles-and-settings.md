---
title: Paquetes y configuraciones de marca de PBA
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2026-08-12T12:11:16Z'
  id: 360000646498
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360000646498
---
> **En resumen:** Los paquetes de marca consolidan la atribución, los eventos, las visitas y los ingresos de las aplicaciones y los sitios web relacionados con la marca. Utiliza la página de configuración del paquete de marca para marcar eventos de conversión, integrar con Google Ads y más.

<Image align="center" alt="BrandBundles.png" src="https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png" />

<div id="about-brand-bundles" />

## Sobre los paquetes de marca

Las marcas operan en un ecosistema que abarca tanto propiedades web como móviles. Como anunciante, se necesita una imagen completa del rendimiento de la marca en todas las plataformas (web y móvil). En PBA, los paquetes de marca consolidan los datos de las propiedades web y móviles en una sola entidad para fines de análisis y raw data. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

<div id="what-is-a-web-app" />

> 📘 **¿Qué es una aplicación web?**
>
> Una aplicación web es una <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">entidad que has creado en AppsFlyer</Anchor> que especifica un sitio web para el cual deseas medir el rendimiento.
>
> * La entidad de aplicación web se agregó a AppsFlyer el 9 de febrero de 2022. Antes de esa fecha, ingresaste el dominio del paquete de marca como una configuración separada al crear un paquete de marca. Ahora, primero creas una aplicación web que define el dominio, luego incluyes esa aplicación web al crear un paquete.
> * Si tenías paquetes de marca existentes el 9 de febrero de 2022, verás que ahora tienes una aplicación web en la página **Mis aplicaciones** correspondiente a cada uno de esos paquetes. **¡No te preocupes!** Tu tráfico web se está atribuyendo igual que antes y no se han producido otros cambios en los dashboards de PBA ni en los reportes de raw data.

**Conceptos básicos del paquete de marca:**

* Un paquete de marca contiene exactamente 1 aplicación web *(obligatorio)* y 1 o más aplicaciones móviles *(opcional).*
* Una aplicación (web o móvil) solo puede pertenecer a 1 paquete.
* Las aplicaciones no se pueden eliminar de un paquete ni mover de un paquete a otro sin [eliminar el paquete original](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle).
  * Al eliminar el paquete, AppsFlyer deja de atribuir datos de PBA para el paquete y el acceso a sus datos históricos ya no está disponible.

<div id="accessing-brand-bundles" />

## Acceso a paquetes de marca

Accede a la página **Paquetes de marca** para administrar los paquetes de marca y su configuración:

* En AppsFlyer, en el menú superior, selecciona **Mis aplicaciones** > **Ver paquetes de marcas**.  
  - o -
* En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Paquetes de marca**.

<div id="managing-brand-bundles" />

## Gestión de paquetes de marca

Para agregar, eliminar o administrar paquetes de marca, selecciona una de estas opciones en la página **Paquetes de marca**:

| Opción | Detalles |
| --- | --- |
| Agregar un paquete de marca | Abre la página **Crear paquete**  <br />Sigue las [instrucciones a continuación](/docs/pba-brand-bundles-and-settings#add-brand-bundle) para crear un paquete nuevo. |
| Dashboard de PBA | Abre el dashboard de marca. |
| ID de paquete de marca | Copia el ID del paquete de marca en el portapapeles |
| Clave de desarrollador web | Copia la clave de desarrollador web en el portapapeles |
| Selecciona un paquete existente para actualizar la configuración y las opciones del paquete de marca | Opciones disponibles:<ul><li>Marcar eventos como eventos de conversión:<ul><li>[Configuración de eventos web](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[Configuración de eventos in-app](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Exclusión de dominios](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/es/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Integración de Google Ads</Anchor></li></ul> |
| Icono “Eliminar” | [Elimina el paquete de marca seleccionado](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (después de confirmar tu decisión de hacerlo). |

<div id="add-brand-bundle" />

<Accordion title="Agregar paquete de marca">

Antes de continuar, asegúrate de que todas las aplicaciones que deseas incluir en el paquete se hayan añadido a tu cuenta. Una vez que se ha creado un paquete de marca, las aplicaciones que incluye no se pueden cambiar sin [eliminar el paquete](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) y volver a crearlo.

**Para agregar un paquete de marca:**

1. En la página [Paquetes de marca](/docs/pba-brand-bundles-and-settings#acceso-a-paquetes-de-marca), haz clic en **Agregar paquete de marca.**
2. Ingresa el nombre del **paquete de marca** (cualquier nombre que desees usar para identificar el paquete).
3. Selecciona las aplicaciones para incluir en el paquete.

   **Nota:** Las aplicaciones que están incluidas en otros paquetes no están disponibles para su selección.

   * *[Requerido]* Aplicación web: Selecciona 1 aplicación web disponible.
   * [Opcional]: *Aplicaciones móviles* Selecciona las aplicaciones móviles disponibles que deseas incluir en el paquete.
     * No se requieren aplicaciones móviles para crear un paquete.
     * No hay límite para la cantidad de aplicaciones móviles que puedes incluir en un paquete.
4. Haz clic en Crear paquete.

<div id="important" />

> 🚧 **Importante:**
>
> Los paquetes de marca no se pueden crear en las siguientes circunstancias:
>
> * La aplicación web seleccionada para su inclusión en el paquete no apunta a una URL válida.
> * La aplicación web y una aplicación móvil Android seleccionadas para su inclusión en el paquete tienen el mismo ID de aplicación.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Configuración de eventos web">

Hay dos tipos de eventos web: **estándar** y de **conversión**. Para enfocar y priorizar tus esfuerzos de optimización, configura algunos eventos como eventos de conversión.

* La PBA atribuye eventos estándar y de conversión de la misma manera.
* Los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reportes raw data</Anchor> incluyen eventos estándar y de conversión.
* Los dashboards de PBA incluyen solo eventos de conversión.
* Un tipo de evento se puede cambiar en cualquier momento; sin embargo, el cambio no es retroactivo.

**Para configurar eventos de conversión:**

1. En la página [Paquetes de marca](/docs/pba-brand-bundles-and-settings#acceso-a-paquetes-de-marca), selecciona el paquete de marca.  
   Se abre la página **Actualizar paquetes de marca**.
2. Ve a la pestaña de **Configuración del evento web**.
3. Activa **Marcar como evento de conversión** según sea necesario.
4. Haz clic en **Actualizar paquete**.

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="Configuración de eventos in-app">

[Predeterminado] Los eventos in-app que tienen ingresos se marcan como eventos de conversión. **¡Nota!** Si cambias los eventos predeterminados, debes marcar explícitamente los eventos in-app de ingresos tú mismo.

**Para marcar eventos in-app como eventos de conversión:**

1. En la página [Paquetes de marca](/docs/pba-brand-bundles-and-settings#acceso-a-paquetes-de-marca), selecciona el paquete de marca.  
   Se abre la página **Actualizar paquetes de marca**.
2. Ve a la pestaña de **Configuración de eventos in-app.**
3. Activa **Marcar como evento de conversión** según sea necesario.
4. Haz clic en **Actualizar paquete**.

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Exclusión de dominios">

Se implementa un mecanismo de exclusión de dominios, que forma parte de las <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules">reglas de fuentes de medios de PBA</Anchor>, para evitar:

* Autoatribución: En otras palabras, AppsFlyer no atribuirá eventos al sitio web definido en la propia aplicación web ni a los dominios que especifiques que están asociados con ese sitio web.
* Atribuir o registrar eventos asociados con dominios que no son parte de tu marca, pero participan en el flujo de usuarios (Por ejemplo, payment gateways).

| Tipo de dominio | Descripción | Impacto de la exclusión |
| --- | --- | --- |
| Principal | El dominio de la **aplicación web** incluida en el paquete de marca. Esto incluye los subdominios.<br /><br />Por ejemplo: si tu dominio es mydomain.co.za, los subdominios como a.mydomain.co.za, b.mydomain.co.za se excluyen automáticamente. <br /><br />El dominio de una aplicación web no se puede cambiar sin [eliminar](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) y volver a crear la aplicación web. (Esto también significa eliminar el paquete en el que se incluye la aplicación web). | Sin autoatribución |
| Interno | Enumera otros dominios que forman parte de tu marca, por ejemplo, mydomain.com, mydomain.in, mydomain.co.ng, abc.com | Sin autoatribución |
| Externo (listado por ti) | Dominios utilizados directamente por tu sitio web, pero que no son parte de la marca. Estos incluyen payment gateways, sitios de procesamiento de pagos, etc. | <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules#visit-recognition-rules">Las visitas no se tienen en cuenta</Anchor> |
| Externo (listado por AppsFlyer) | Dominios listados por AppsFlyer y siempre excluidos.<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>La lista de dominios automáticos no se puede editar. | <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules#visit-recognition-rules">Las visitas no se tienen en cuenta</Anchor> |

**Para excluir dominios internos o externos:**

1. En la página [Paquetes de marca](/docs/pba-brand-bundles-and-settings#acceso-a-paquetes-de-marca), selecciona el paquete de marca.  
   Se abre la página **Actualizar paquetes de marca**.
2. Ve a la pestaña **Exclusión de dominios**.
3. Haz clic en **Agregar dominio**.
4. Ingresa un nombre de dominio.
5. Selecciona un tipo de dominio: **Interno** o **Externo**.
6. Haz clic en **Agregar dominio**.  
   La exclusión tarda una hora en surtir efecto.

</Accordion>

<div id="faq" />

## Preguntas frecuentes

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="¿Puedo incluir la misma aplicación en más de un paquete?">

**No.** Una vez que se agrega una aplicación a un paquete, no se puede agregar a otro paquete.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="¿Puedo agregar o eliminar aplicaciones después de crear un paquete?">

**No.** Una vez que se ha creado un paquete, las aplicaciones incluidas en él no se pueden cambiar.

**¿Por qué?** ¿Por qué? **Debido a que cada aplicación tiene sus propios datos y AppsFlyer utiliza estos datos para analizar la trayectoria del usuario en todas las plataformas (web y aplicación). Si una aplicación cambia, esto implicaría un conjunto de datos diferente que no es compatible con los datos anteriores.**

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="¿Cómo agrego o elimino aplicaciones de un paquete?">

Para cambiar el paquete en el que se incluye una aplicación, elimina el paquete original y crea uno nuevo que incluya la aplicación.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="¿Qué sucede si elimino un paquete?">

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### Preguntas frecuentes ¿Qué sucede si elimino un paquete?

Si eliminas un paquete:

* AppsFlyer deja de atribuir el paquete.
* Los datos del paquete se conservan (en otras palabras, no se eliminan de forma permanente), pero el paquete en sí no se puede restaurar para ver los datos.

  **¿Por qué?** Un nuevo paquete utiliza una clave de desarrollo web diferente, por lo que, aunque incluya las mismas aplicaciones, el paquete original no se restaura.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="¿Por qué ciertas aplicaciones no están disponibles para agregarlas a un paquete?">

* **Administradores:** Si no puedes seleccionar una aplicación al crear un paquete, asegúrate de que la aplicación se haya agregado a tu cuenta de AppsFlyer y no esté incluida en otro paquete.
* **Otros usuarios de la cuenta:** Consulta con un administrador de la cuenta para asegurarte de que tienes el rol y los permisos necesarios para acceder a las aplicaciones que intentas agregar.

</Accordion>

<div id="page-404" />

<Accordion title="¿Por qué recibo el error 'No pudimos encontrar esa página' cuando intento ver o crear un paquete de marca?">

Probablemente no te suscrito a PBA. Contacta con tu CSM o con [hello@appsflyer.com](mailto:hello@appsflyer.com) para actualizar tu paquete.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/onboarding-guide-to-people-based-attribution">Guía de onboarding de PBA</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">Introducción a PBA</Anchor>

<div data-zendesk-anchors="about-brand-bundles=sobre-los-paquetes-de-marca h_01HE0Y2A3A5W86YY44RWCTKM1Y=sobre-los-paquetes-de-marca h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=qu%C3%A9-es-una-aplicaci%C3%B3n-web accessing-brand-bundles=acceso-a-paquetes-de-marca h_01HE0Y2A3A7265NYM7GVBZVXEN=acceso-a-paquetes-de-marca managing-brand-bundles=gesti%C3%B3n-de-paquetes-de-marca h_01HE0Y2A3A272QJ4ZQH7VXJWCC=gesti%C3%B3n-de-paquetes-de-marca h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=importante h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=preguntas-frecuentes h_01HE0Y2A3AB24NCNPAYFC0J4YH=preguntas-frecuentes h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=preguntas-frecuentes-qu%C3%A9-sucede-si-elimino-un-paquete h_01HE0Y2A3B276FV92EYBCZRA6C=preguntas-frecuentes-qu%C3%A9-sucede-si-elimino-un-paquete h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01JTQF9DZZZ5JFN43Y5KJJV943=page-404 h_01HE0Y2KTXS06WHN57MQ91AD09=consulta-tambi%C3%A9n" />
