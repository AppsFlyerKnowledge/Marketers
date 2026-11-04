---
title: Implementación de código de sitio web de Smart Banners para marketers
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-08-12T12:25:35Z'
  id: 4416119954705
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/4416119954705
---
> **De un vistazo:** Agrega el código Smart Banners tu sitio web para convertir a los visitantes de tu sitio web en usuarios de aplicaciones móviles.

<div id="note" />

> 📘 **Nota**
>
> El SDK web de AppsFlyer para Smart Banners v1 quedó en desuso el 8 de noviembre de 2023. Para mostrar Smart Banners en tu sitio web, necesitas actualizar a la v2. <Anchor target="_blank" href="/marketers/es/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Aprender más</Anchor>

<div id="website-code-implementation" />

## Implementación del código del sitio web

Este artículo está dirigido a marketers que desean implementar el código Smart Banners en su sitio web a través de una de las siguientes opciones:

* Google Tag Manager (GTM)
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

Para agregar el código a través de otras plataformas o para realizar cambios en el código según las necesidades (incluyendo agregar parámetros, enlaces profundos, ocultar el banner o integrar la PBA con Smart Banners), consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementación de código de sitio web de Smart Banners para desarrolladores.</Anchor>

**Para implementar el código Smart Banners en tu sitio**:

1. Siga las <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">instrucciones del sitio web en el lugar de trabajo</Anchor> para obtener el código Smart Banners.
2. Usa las instrucciones específicas de la plataforma que se indican a continuación para implementar el código en tu sitio web:

<div id="google-tag-manager" />

<Accordion title="Google Tag Manager">

**Para implementar el código mediante Google Tag Manager**:

1. En GTM, crea una nueva etiqueta.
2. Asigna un nombre a la etiqueta, haz clic en **Configuración de etiqueta** y selecciona **HTML personalizado**.
3. En el cuadro HTML, pega el fragmento de código del Smart Banner. Reemplaza YOUR-BANNER-KEY en el fragmento de código con tu clave de banner real.
4. Haz clic en **Activación** y crea un activador nuevo haciendo clic en el ícono del signo más en la esquina superior derecha de la pantalla.
5. Asigna un nombre al desencadenador y, a continuación, en **Configuración del disparador,** elige **Vista de página**.
6. Si deseas que el banner aparezca en todas las páginas, selecciona **Todas las vistas de página**. Si quieres que el banner aparezca en las páginas seleccionadas, selecciona **Algunas vistas de página** y define la condición para activar la etiqueta. Para obtener más información sobre los activadores, lee <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">Documentación GTM</Anchor>.
7. Haz clic en **Guardar** en la esquina superior derecha.
8. Vuelve a la pantalla de configuración de etiquetas. Verifica que todo esté configurado y haz clic en **Guardar** en la esquina superior derecha.
9. Publica tu contenedor GTM.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**Para implementar el código mediante Adobe Launch Tag Manager**:

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="Paso 1: Crear una propiedad en Adobe Experience Cloud">

**Para crear una propiedad (etiqueta) que aloje el código de los Smart Banners**:

1. Ve a **Adobe Experience Cloud** > **Launch**.
2. En **Adobe Experience Cloud Launch**, haz clic en **Go to Launch** (Ir a Launch).
3. Haz clic en **New Property** (Nueva propiedad).
4. Asigna un nombre a tu propiedad.
5. En **Plataform** (Plataforma), selecciona **Web**.
6. Ingresa el dominio de tu sitio web.
7. Haz clic en **Guardar**.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="Paso 2: Añada el código Smart Banners a la propiedad Adobe Launch">

**Para añadir el código de Smart Banners a la etiqueta**:

1. En la página **Mi propiedad web**, selecciona la pestaña **Reglas**.
2. Dale un nombre a la regla. Recomendado: **AppsFlyer Smart Banners**.
3. En la sección **If** (Si), en **EVENTS** (EVENTOS), haz clic en **+Add** (+Agregar).
   * En **Tipo de evento**, selecciona **Central - Listo para DOM**.
   * Haz clic en **Keep Changes** (Mantener cambios).
4. En la sección **THEN** (ENTONCES), en **Actions** (Acciones), haz clic en **+Add** (+Agregar).
   * En **Action Type** (Tipo de acción) > **Custom Code** (Código personalizado).
   * Selecciona **JavaScript** > **Abrir editor** y pega el fragmento de código del SDK de Smart Banners **sin las etiquetas &lt;script>**.
   * Haz clic en **Keep Changes** (Mantener cambios) para cerrar el editor de códigos.
5. Haz clic en **Guardar**.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="Paso 3: Agrega la etiqueta de Adobe Launch a tu sitio web.">

**Para añadir la etiqueta Adobe Launch a tu sitio web (que carga el código de Smart Banners)**:

1. En la página **My web property** (Mi propiedad web), selecciona la pestaña **Environments** (Entornos).
2. Busca la fila con el entorno que deseas publicar (desarrollo o producción).
   * En el encabezado **INSTALL** (INSTALAR), haz clic en el ícono de la caja en la fila correspondiente; normalmente se trata de un entorno de producción.
   * Consulta la sección sobre la publicación del entorno **Adobe Launch**.
3. En el cuadro de diálogo **Web Install Instructions** (Instrucciones de instalación web):
   * Copia el fragmento de código del script.
   * Cierra el cuadro de diálogo.
4. Pega el fragmento de código en la etiqueta &lt;head> de tu sitio web.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="Paso 4: Publicar el entorno de Adobe Launch">

**Publica el entorno para activar la etiqueta de Adobe Launch**:

1. En la página **My web property** (Mi propiedad web), ve a la pestaña **Publishing** (Publicación).
2. En la sección **Development** (Desarrollo), haz clic en **Add New Library** (Agregar biblioteca nueva).
   1. Asigna un nombre a la biblioteca y elige un entorno.
   2. En **Resource Changes** (Cambio de recursos), haz clic en **Add a Resource** (Agregar un recurso).
   3. Haz clic en **Reglas** > **Cargar Smart Banners** > **Últimos** > **Seleccionar y crear una revisión nueva**.
   4. Haz clic en **Guardar**.
3. En la sección **Development** (Desarrollo):
   1. Junto a la biblioteca recién creada, haz clic en el menú de acciones (3 puntos) y selecciona **Crear para desarrollo**.
   2. Haz clic de nuevo en el menú de acciones y selecciona **Enviar para aprobación**.
4. En la sección **Submitted** (Enviado):
   1. Haz clic en el menú de acciones y selecciona **Crear para escenario**.
   2. Haz clic de nuevo en el menú de acciones y selecciona **Aprobar para publicar**.
5. En la sección **Aprobado**, haz clic en el menú de acciones y selecciona **Crear y publicar en producción.** El proceso ya está completo.

</Accordion>

Ahora, cuando tu sitio web se cargue en el dispositivo móvil, se mostrará la creatividad activa del banner. Para mostrar solo el banner en determinadas páginas o según las acciones del usuario, consulta las <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">reglas de Adobe Launch</Anchor>.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**Para implementar el código en tu sitio web de Shopify**:

1. En tu panel de control de Shopify, ve a **Canales de venta** > **Tienda online** > **Temas**.  
   Se muestra tu tema actual.
2. Haz clic en **Acciones** > **Editar código**.  
   Se abre la página de edición de código para tu tema.
3. En la carpeta Diseño, haz clic en el archivo que comienza con el **tema `{/}`**.  
   Aparece el código de la página web.
4. En el código, justo debajo&lt;head>, pega tu código de Smart Banners.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

Para implementar el código en tu sitio web de Wix:

1. En tu panel de control de Wix, haz clic en **Configuración.**
2. En la sección avanzada de la página de configuración, haz clic en **Código personalizado**.
3. Haz clic en **+ Agregar código personalizado**.
4. En el cuadro **Pega el fragmento de código aquí**, pega el código de Smart Banners.
5. En el cuadro Nombre, escribe un nombre para el código. Recomendado: AppsFlyer Smart Banners.
6. En **Añadir código a las páginas**, selecciona dónde mostrar tus banners. Elige entre:
   * Todas las páginas
   * Elige páginas específicas
7. Haz clic en **Aplicar**.  
   La página de códigos personalizados ahora debería mostrar tu código. Asegúrate de que esté colocado en la sección de la **cabeza**.

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**Para implementar el código en tu sitio web de Squarespace**:

1. En tu panel de control de Squarespace, haz clic en **Sitio web**.
2. Haz clic en **Configuración**.
3. Haz clic en **Avanzado**.
4. Haz clic en **Inyección de código**.
5. En la sección **Encabezado**, pega el código de Smart Banners.
6. Haz clic en Guardar.

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**Para implementar el código en tu sitio web de WordPress**:

1. En tu panel de control de WordPress, haz clic en **Apariencia** > **Editor de temas**.  
   Se abre la página Editar temas y se muestra el código CSS de tu sitio web.
2. En **Archivos de temas**, haga clic en **Encabezado del tema (header.php)**.
3. En el código que aparece, debajo&lt;head>, pega el código de Smart Banners.
4. Haz clic en **Actualizar archivo**.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#installation-and-integration">Integración de PBA con Smart Banners</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=nota website-code-implementation=implementaci%C3%B3n-del-c%C3%B3digo-del-sitio-web h_01HBT97B1Z0F4B8E9GQWJEE6BH=implementaci%C3%B3n-del-c%C3%B3digo-del-sitio-web h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=consulta-tambi%C3%A9n" />
