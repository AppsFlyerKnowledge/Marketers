---
title: Configuración de la aplicación
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-19T14:13:26Z'
  id: 211719806
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/211719806
---
> **At a glance:** Descubre las configuraciones que influyen en la atribución y el análisis de tu aplicación a través de todas las fuentes de medios.

<div id="app-settings" />

## Configuración de la aplicación

**Acceso:**

* Un administrador (u otros usuarios con los permisos adecuados) puede **modificar** la configuración de la aplicación.
* Todos los usuarios de la cuenta con acceso a una aplicación específica pueden **consultar** su configuración.

**Para modificar o consultar la configuración de la aplicación:**

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. Consulta las configuraciones y realiza los cambios necesarios en la página de configuración de la aplicación.
3. Haz clic en **Guardar configuración.**

<div id="note" />

> 📘 **Nota:**
>
> También puedes cambiar muchos de estos ajustes para varias apps a la vez, en lugar de hacerlo de una en una. Busca el botón **Aplicar a apps adicionales** junto a un ajuste modificado. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar ajustes a varias aplicaciones a la vez</Anchor>.

<div id="general-app-settings" />

### Configuración general de la aplicación

<Table>
  <thead>
    <tr>
      <th>
        Configuración
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        Autenticación del SDK: Clave de desarrollador
      </td>
      <td>
        * La clave de desarrollador autentica los eventos enviados por la aplicación o S2S a AppsFlyer.
        * La clave es única para cada cuenta y la utilizan todas las aplicaciones de la misma cuenta.
        * La clave está disponible en la página de configuración de la aplicación para cualquier usuario con acceso a esa aplicación.
        * [Opcional] Se puede asignar una clave individual para la aplicación en ciertos escenarios. Contacta con tu CSM para discutir sobre esto.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        Privacidad Avanzada Agregada (aplicaciones iOS)
      </td>
      <td>
        Cuando está activada, los datos de atribución a nivel de usuario no están disponibles para los anunciantes. Los datos de eventos y postbacks compartidos con partners son agregados y anónimos (más detalles sobre el framework de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad Avanzada Agregada</Anchor>).

        Cuando está desactivada, los datos de atribución a nivel de usuario están disponibles para todos los partners como datos agregados y pueden configurarse para cada partner individualmente.

        También puedes cambiar este ajuste para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar ajustes a varias aplicaciones a la vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        Análisis: Definir el trigger del usuario leal
      </td>
      <td>
        * El trigger para identificar a un usuario como leal. La opción por defecto cuando agregas la aplicación es 3 aperturas de la aplicación.
        * Después de atribuir eventos in-app, puedes utilizar un evento interno como evento desencadenante.
          * [Por defecto] 3 aperturas de la aplicación.
          * La configuración de usuario leal es indicativa de la calidad del usuario. Considera utilizar <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> para combatir el fraude.
          * Cambiar esta configuración afecta los datos de manera retroactiva, recalculando los datos históricos de usuarios leales.
        * También puedes cambiar este ajuste para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar ajustes a varias aplicaciones a la vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="minimum-time-between-sessions"></span>
        Tiempo mínimo entre sesiones
      </td>
      <td>
        También puedes cambiar este ajuste para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar ajustes a varias aplicaciones a la vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        País de la tienda de aplicaciones
      </td>
      <td>
        Configura el país de la tienda de aplicaciones donde la aplicación está disponible. Esta configuración afecta a la aplicación como se detalla aquí.

        * **Cambio del estado de la aplicación de pendiente a activa**:
          * <Anchor target="_blank" href="/marketers/es/docs/why-is-my-app-still-pending">Cuando la aplicación se activa</Anchor>, AppsFlyer consulta la tienda utilizando la configuración de país para obtener detalles de la aplicación, como el icono.
          * Si no se encuentra la aplicación en el país establecido en la tienda, AppsFlyer no podrá cambiar su estado de pendiente a activa.
        * El comportamiento de redirección depende de la configuración según el escenario, como se detalla en la siguiente tabla.

        | Tipo de usuario | Escenario de redirección |
        | --- | --- |
        | <span id="mobile"></span>Móvil | Normalmente, los usuarios hacen clic en enlaces de atribución dentro de otras aplicaciones móviles. Al hacer clic, el sistema operativo determina el país de la tienda a la que se redirecciona a los usuarios:<br /><br />* **Android** redirecciona según la IP o ubicación del usuario.<br />* **iOS** redirecciona a la tienda de aplicaciones asociada con la cuenta de iTunes activa en el dispositivo. |
        | <span id="mobile-and-web"></span>Móvil y web | Cuando los usuarios web hacen clic en enlaces de atribución en **sitios web** (tanto móviles como ordenadores), la redirección inicial es a la tienda del país establecido en la tienda de aplicaciones.<br /><br />Al intentar instalar, el sistema operativo los redirecciona a la tienda del país según lo descrito para móviles en la fila anterior. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | Desde iOS 13, <Anchor target="_blank" href="https://www.apple.com/ipados/features/">los iPads ofrecen la versión de ordenador de los sitios web</Anchor>. Esto implica que el tipo de usuario (móvil o web) no es relevante. Un clic en un enlace de atribución lleva al sitio de escritorio y, a partir de ahí, las reglas de redirección son las aplicables a los usuarios web. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        Localización: Zona horaria
      </td>
      <td>
        La configuración predeterminada de la aplicación es UTC. <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">Sobre de la zona horaria de la aplicación.</Anchor>

        El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        Localización: Moneda
      </td>
      <td>
        * Esto define la divisa específica de la aplicación que se utiliza para las siguientes métricas:
          * Costo
          * Ingresos de eventos in-app
          * Ingresos de anuncios
        * La configuración predeterminada de la aplicación es USD.
          * El cambio de moneda está disponible para aplicaciones que no tienen ingresos ni costos.
          * En el caso de nuevas aplicaciones, la moneda se establece al añadir la aplicación.
        * El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>.

        <div id="reporting-tools-impacted-by-app-currency" />

        #### Herramientas de reportes afectadas por la moneda de la aplicación

        | Herramienta de reportes | Opciones de moneda disponibles |
        | --- | --- |
        | <span id="dashboards"></span>Paneles de control | Moneda específica de la aplicación |
        | <span id="export-data-page"></span>Página de exportación de datos | Moneda específica de la aplicación |
        | <span id="push-api"></span>API Push | Moneda específica de la aplicación y USD disponibles simultáneamente |
        | <span id="pull-api"></span>API Pull | Datos agregados: Moneda específica de la aplicación<br /><br />Raw data: USD seleccionable o moneda específica de la aplicación |
        | <span id="master-api"></span>API maestra | USD seleccionable o moneda específica de la aplicación |
        | <span id="data-locker"></span>Casillero de datos | Solo USD |
      </td>
    </tr>
  </tbody>
</Table>

<div id="attribution-settings" />

### Configuración de atribución

<div id="note-1" />

> 📘 **Nota:**
>
> Los ajustes de esta tabla se aplican a las aplicaciones móviles (iOS y Android). Es posible que algunos ajustes no estén disponibles o que funcionen de forma diferente en las aplicaciones web.

| Configuración | Descripción |
| --- | --- |
| <span id="reattribution-window"></span>Ventana de reatribución | La <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> es el periodo que comienza desde la fecha de la primera instalación, durante el cual las reinstalaciones no pueden atribuirse como nuevas instalaciones.<ul><li>[Predeterminado] Tres meses</li><li>Rango de valores: 1-24 meses</li></ul>El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Atribución por visualización mediante modelado probabilístico | <ul><li>Si está deshabilitado, habilita el modelado probabilístico por impresiones.</li><li>Después de habilitar el modelado probabilístico de visualización, también debe activar la atribución por visualización en la pestaña de integración de la ad network.</li><li>El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Para ello, el fingerprinting ya debe estar habilitado. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>.</li></ul> |
| <span id="reengagement-attribution"></span>Atribución de re-engagement | Lectura relacionada: <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Guía de retargeting</Anchor><br /><br />**Para habilitar la atribución de re-engagement:**<ul><li>En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**, y activa la **Atribución de re-engagement**.</li></ul>Además de la configuración de la aplicación, también debes <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#retargeting-settings">realizar configuraciones específicas para cada partner</Anchor>.<br /><br />La configuración del <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#ventanas-de-exclusión">**tiempo mínimo entre conversiones de re-engagement**</Anchor> se usa para evitar que una ventana de re-engagement termine antes de su duración establecida.<br /><br />También puedes cambiar esta configuración para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. Cuando se aplique de forma masiva, también verás un paso de confirmación antes de que el cambio surta efecto; esto no se aplica al cambiar una aplicación individual. |
| <span id="minimum-time-between-reengagement-conversions"></span>Tiempo mínimo entre conversiones de recaptación (re-engagement) | Impide que una ventana de re-engagement existente finalice antes de que termine la duración configurada. Lectura relacionada: <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#ventanas-de-exclusión">Guía de atribución de retargeting</Anchor>.<br /><br />También puedes cambiar esta configuración para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |
| <span id="organic-search-seo-mobile-app-attribution"></span>Atribución de re-engagement de aplicaciones móviles para SEO (búsqueda orgánica) y AEO | Lectura relacionada: <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribución de búsqueda orgánica</Anchor><br /><br />**Para activar la atribución de SEO/AEO:**<ul><li>En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación** y activa la **atribución de re-engagement de aplicaciones móviles en SEO (búsqueda orgánica) y AEO.**</li></ul>También puedes cambiar esta configuración para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |
| <span id="uninstall-measurement"></span>Medición de desinstalaciones | <Anchor target="_blank" href="/marketers/es/docs/measure-uninstalls">La medición de desinstalaciones</Anchor> está relacionada con las instalaciones que ocurren cuando la medición está activa.<br /><br />Este ajuste está disponible solo para aplicaciones de iOS y Android.<br /><br />**Para habilitar la medición de desinstalaciones:**<ol><li>Completa lo siguiente según el sistema operativo:<ul><li>**iOS**: Las aplicaciones que implementan la función de atribución de desinstalación en iOS deben cargar aquí el certificado P12.</li><li>**Android**: Para la atribución de desinstalación en Android, las aplicaciones requieren definir una clave de servidor Firebase/GCM aquí.</li></ul></li><li>Activa la **Medición de desinstalaciones**.</li><li>Haz clic en **Guardar configuración**.</li></ol>**Para detener la medición de desinstalaciones:**<ol><li>Desactiva la **Medición de desinstalaciones**.</li><li>Haz clic en **Guardar configuración.**</li></ol>El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |

<div id="advanced-settings" />

### Configuraciones avanzadas

| Configuración | Descripción |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Enmascarar direcciones IP | Cuando está activado, las <Anchor target="_blank" href="/marketers/es/docs/apply-ip-masking-to-user-data">direcciones IP de los dispositivos de los usuarios finales se ocultan</Anchor> en los reportes de raw data y en los postbacks enviados a partners desde la aplicación actualmente seleccionada.<br /><br />También puedes cambiar esta configuración para varias aplicaciones a la vez. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Detección de reinstalaciones usando almacenamiento en el dispositivo (solo iOS) | Detecta reinstalaciones sin depender de IDs de publicidad. Esto se realiza almacenando la última fecha de instalación de la aplicación en el almacenamiento local seguro del dispositivo (en iOS, el Keychain). Determinar si una instalación fue una reinstalación o una nueva instalación te permite desduplicar reinstalaciones de tus NOI, haciendo que el análisis de atribución sea más preciso. Nota: Para este fin, solo se almacena en el almacenamiento local del dispositivo la fecha de la última instalación de la app; no se almacena ningún otro identificador del dispositivo (por ejemplo, IDFA, IDFV).<br /><br />El soporte para cambiar esta configuración en varias aplicaciones a la vez estará disponible pronto. Saber más en <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplicar la configuración a varias aplicaciones a la vez</Anchor>. |
| <span id="ios-103-redirect-fallback"></span>Alternativa de redirección en iOS 10.3 | [Obsoleto] Para iOS 10.3+. Hemos simplificado el flujo para los usuarios de iOS y ya no se utiliza este parámetro. <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Redirecciones en iOS</Anchor>.<br /><br />Esta opción está disponible únicamente para aplicaciones iOS. |
| <span id="change-app-name"></span>Cambiar nombre de la aplicación | <ul><li>El nombre de la app se muestra en el dashboard y en los reportes de datos. Esto es útil si tienes distintas versiones de la misma app, por ejemplo, por motivos de distribución regional.</li><li>Este cambio afecta cómo se muestra la app. El ID de la app, que se utiliza para identificarla al usar varias APIs de AppsFlyer, **permanece igual**.</li><li>Los nombres están limitados a 50 caracteres.</li></ul> |
| <span id="outofstore-app-url"></span>URL de la app fuera de la tienda | <ul><li>Configura la URL de descarga de la app como destino predeterminado de redirección para los enlaces de atribución asociados con la app.</li><li>Este campo es obligatorio para las aplicaciones de Android especificadas como fuera de la tienda.</li><li>Una vez configurada, la URL se aplicará como destino predeterminado de redirección en aproximadamente una hora.</li></ul> |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Guía de atribución de retargeting</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribución de búsqueda orgánica</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/apply-settings-to-multiple-apps-at-once">Aplica la configuración a varias apps a la vez</Anchor>

<div data-zendesk-anchors="app-settings=configuraci%C3%B3n-de-la-aplicaci%C3%B3n 01ECHQME56X51MDW9TMA6DBNCK=configuraci%C3%B3n-de-la-aplicaci%C3%B3n h_01M22QK1N5EMMPVZ7ZJ55Z3YFF=nota general-app-settings=configuraci%C3%B3n-general-de-la-aplicaci%C3%B3n h_01HAVS8CVPQKSDKCEM3YHHJ99Y=configuraci%C3%B3n-general-de-la-aplicaci%C3%B3n reporting-tools-impacted-by-app-currency=herramientas-de-reportes-afectadas-por-la-moneda-de-la-aplicaci%C3%B3n h_01HAVS8CVQESWAQXKDW5SNVHCJ=herramientas-de-reportes-afectadas-por-la-moneda-de-la-aplicaci%C3%B3n attribution-settings=configuraci%C3%B3n-de-atribuci%C3%B3n h_01HAVS8CVQN1YYTT7S49VGB3J0=configuraci%C3%B3n-de-atribuci%C3%B3n h_01M1XPKX6DECQPK4R9X6Y4KMBP=nota-1 advanced-settings=configuraciones-avanzadas h_01HAVS8CVQTKXVXSMT5KNYZ3T4=configuraciones-avanzadas h_01HDPCC9465DR4A3CCXYQC2M56=consulta-tambi%C3%A9n" />
