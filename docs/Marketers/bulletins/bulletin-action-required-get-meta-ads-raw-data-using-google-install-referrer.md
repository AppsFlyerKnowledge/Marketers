---
title: >-
  Boletín: Acción requerida: obtén raw data de Anuncios de Meta usando el
  referente de instalación de Google
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2026-10-20T03:56:30Z'
  id: 4409322107537
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **¿Qué hay de nuevo?**
      </td>
      <td>
        Obtén raw data de la campaña de Anuncios de Meta de los anuncios que dirigen a Google Play Store mediante el referente de instalación.
      </td>
    </tr>
    <tr>
      <td>
        **Qué ha cambiado**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        A partir del 29 de octubre de 2021, los datos de atribución a nivel de usuario (raw data) de los usuarios traídos por Meta Ads **después** de esta fecha están restringidos. Anuncios de Meta pone estos datos a disposición de MMP como AppsFlyer, pero no a disposición de los anunciantes.

        Sin embargo, si el anuncio dirige a los usuarios a Google Play Store, los campos de atribución están disponibles para los anunciantes en la Referencia de instalación de Google, que debe <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrarse en tu aplicación.</Anchor> Los campos proporcionados a través del referente completan los reportes de raw data de AppsFlyer disponibles para ti y permiten que AppsFlyer atribuya a los usuarios que no tienen un ID de publicidad (habilitado para LAT).

        El uso del mecanismo de referente requiere AppsFlyer SDK V5.4+

        **Nota:** Los datos del referente tienen prioridad sobre los datos proporcionados por la API y no están restringidos.

        Anuncios de Meta cifra los datos del referente y los descifra utilizando una clave disponible en tu cuenta de desarrollador de Anuncios de Meta. Debes proporcionarnos la clave de descifrado que se describe en la fila de acciones requeridas.

        **Campos de atribución de campaña disponibles a través del referente:**

        * Ad ID
        * Nombre de anuncio
        * ID de adset
        * Nombre del conjunto de anuncios
        * Campaign ID
        * Nombre de la campaña
        * ID de cuenta
        * Channel
        * Tipo de anuncio (este campo aún no está disponible)

        **Nota**:

        * No hay otros campos disponibles a través del referente.
        * Esta solución se aplica a la atribución por clics y no a la atribución por impresiones.
        * Los datos del referente no se aplican a las campañas de re-engagement, ya que los usuarios no pasan por la tienda.

        **¿Cuándo implementará AppsFlyer este cambio?**

        * A partir del 29 de octubre de 2021:
          * Se implementan restricciones de Anuncios de Meta a los datos de clics (en otras palabras, el raw data de atribución).
          * Los anunciantes pueden actualizar la clave de descifrado del referente en AppsFlyer.
        * A partir del 3 de noviembre de 2021:
          * AppsFlyer completa el raw data y atribuye utilizando los datos proporcionados por el mecanismo de referente.
      </td>
    </tr>
    <tr>
      <td>
        **Resumen de disponibilidad de datos**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">Cómo se atribuye</th><th rowspan="2">Fuente de datos de atribución</th><th colspan="2">Datos disponibles para anunciantes </th><th>Comentarios</th></tr><tr><th>Datos sin procesar</th><th>Datos agregados</th><th> </th></tr><tr><td>Por clics</td><td>Referente (se implementa en las aplicaciones de Android descargadas de Google Play Store)</td><td>disponible</td><td>disponible</td><td><ul><li>Datos de atribución de usuarios LAT disponibles.</li><li>El referente tiene prioridad sobre los datos de MMP si ambos están disponibles.</li><li>No es aplicable a las campañas de re-engagement.</li></ul></td></tr><tr><td>Por clics</td><td>MMP API</td><td>Restringido\*</td><td>disponible</td><td> </td></tr><tr><td>Por impresiones</td><td>MMP API</td><td>Restringido\*</td><td>disponible</td><td>El mecanismo de referente no es compatible.</td></tr><tr><td colspan="5"><p><strong>Nota:</strong> Cuando la disponibilidad de los datos está restringida:</p><ul><li><ul><li>Las postbacks de eventos de instalación e in-app se envían solo a las redes de publicidad restrictivas. Los partners externos, como los partners de analíticas, no reciben postbacks para la atribución restringida. </li><li>Los postbacks no atribuidos (que no contienen campos de atribución) se envían a las redes de publicidad que se configuraron para recibir todos los eventos (incluidos los orgánicos y los no atribuidos). Esto incluye a los partners de administración de campañas de Meta.</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Acción requerida**
      </td>
      <td>
        **Para obtener tu clave de descifrado de Anuncios de Meta:**

        [La siguiente información se basa en la información proporcionada por Facebook]

        1. Inicia sesión en tu portal del desarrollador de Meta.
        2. Ve a **Mis aplicaciones** en la esquina superior derecha.
        3. Selecciona la aplicación para la que deseas acceder a tu clave de descifrado.
        4. Ve a **Configuración** > **Básica** en el lado izquierdo de la página.

           [![FBUIforKey.png](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)
        5. Desplázate hacia abajo hasta la sección **Android** y verás tu clave de descifrado con la etiqueta **Clave de descifrado de la Referencia de instalación** debajo del campo **Nombres de paquete**. **Nota**: Esta es la misma sección en la que configuraste el nombre de tu paquete y Google Play Store.

        **Para habilitar el mecanismo de referente en AppsFlyer.**

        1. [Obligatorio] Verifica que AppsFlyer SDK V5.4+ esté adoptado en tu aplicación. No confíes en versiones anteriores.
        2. Realice una de las siguientes acciones:
           1. [Próximamente] Configura la clave de descifrado a través de la API.
           2. Para establecer la clave de descifrado a través de la interfaz de usuario:
              1. En AppsFlyer, ve a **Configuración** > **Integraciones activas**.
              2. Selecciona Meta ads.  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. En la pestaña **Integración**, pega la clave en **Referencia de instalación** **Clave de descifrado**.
           4. Haz clic en **Guardar integración**.
      </td>
    </tr>
    <tr>
      <td>
        **Actualizar la clave de descifrado a través de API**
      </td>
      <td>
        **[En breve]**

        Lanzaremos una API que actualiza la clave de descifrado.
      </td>
    </tr>
    <tr>
      <td>
        **Disponibilidad de raw data en el futuro**
      </td>
      <td>
        * Si los datos de atribución se obtienen a través del mecanismo de referente, los datos no están restringidos y están disponibles a través de los reportes de raw data.
        * Si los datos de atribución se obtienen a través de la API, entonces los raw data de los usuarios traídos por Meta Ads se asignan a la fuente de medios *restringida*
        * Este cambio no tiene ningún impacto en el raw data de los usuarios traídos antes del cambio. En otras palabras, antes del 29 de octubre de 2021, 08:00 UTC.
      </td>
    </tr>
    <tr>
      <td>
        **Qué sigue igual**
      </td>
      <td>
        AppsFlyer sigue recibiendo datos a nivel de dispositivo de los anuncios de Meta, lo que significa que nuestras capacidades de atribución e informes (incluyendo la atribución multitáctil, LTV, ROI, análisis de cohortes, informes de retención, protección contra fraudes, audiencias, y otros servicios) permanecen sin cambios. Consulta las <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">herramientas de generación de reportes agregados y analíticos</Anchor>.

        **Nota**: Si nos proporcionas la clave de descifrado, podemos atribuir a los usuarios que no tienen un ID de publicidad (habilitado para LAT). Esto mejora la precisión de la atribución.
      </td>
    </tr>
    <tr>
      <td>
        **Cambios en la atribución**
      </td>
      <td>
        El Deferred Deep Linking a través de GCD estará disponible para las aplicaciones Android mediante el mecanismo de referente de instalación de Google. No está disponible para aplicaciones de iOS.
      </td>
    </tr>
    <tr>
      <td>
        **Preguntas ftecuentes**
      </td>
      <td>
        * **¿Es necesario actualizar la clave de descifrado del referente de instalación?**  
          Una vez enviada, no es necesario actualizar la clave de descifrado.
        * **¿Cuándo puedo ver los datos de nivel de usuario en los reportes de raw data?**  
          Los datos de nivel de usuario se muestran en los reportes de raw data una vez que se envía una clave de descifrado de referente de instalación válida y se atribuye una instalación a Anuncios de Meta.
        * **¿Están disponibles los datos de atribución de nivel de usuario para las instalaciones que ocurrieron entre el 29 de octubre de 2021 y el 3 de noviembre de 2021?**  
          Lamentablemente, estos datos no están disponibles.
      </td>
    </tr>
  </tbody>
</Table>
