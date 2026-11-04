---
title: Configura tu lista de redireccionamiento de dominios permitidos
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-08-12T12:04:40Z'
  id: 25068636064529
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/25068636064529
---
> **En resumen:** Configura una lista de redireccionamiento de dominios permitidos para garantizar que los usuarios sean enviados a dominios verificados y confiables, protegiendo sus datos y salvaguardando la integridad de tu marca.

<div id="about-the-redirect-allowlist" />

## <Image alt="Imagen de la lista de permitidos de redirección principal.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />Sobre la lista de redireccionamientos permitidos

Usa la lista de redireccionamientos permitidos para definir una lista específica de dominios raíz y subdominios a los que se permite redireccionar enlaces, con el fin de proteger tus enlaces de redireccionamientos no autorizados, ataques de phishing y fraudes. Una vez que tu lista de permitidos esté activa, los enlaces que crees a través de AppsFlyer solo redirigirán a los usuarios a las URL web cuyos dominios estén en la lista de permitidos. De lo contrario, los usuarios serán enviados a la app store. La lista de redireccionamientos permitidos se aplica a <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>, a los enlaces de atribución de una sola plataforma mediante la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">integración de partners</Anchor> y a los <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">enlaces de atribución directa</Anchor> para plataformas de CTV, PC y consolas. La lista de redireccionamientos permitidos (y el redireccionamiento web personalizado) está disponible para los suscriptores del plan Growth y Enterprise. Para evitar abusos, los suscriptores del plan Zero deben tener una tarjeta de crédito registrada (no se realizará ningún cargo).

<div id="set-up-your-redirect-allowlist" />

## Configura tu lista de redireccionamientos permitidos

Puedes configurar tu lista de permitidos manualmente o mediante un archivo CSV. Antes de la configuración, se recomienda verificar tu lista de dominios de confianza con tu equipo de seguridad.

<div id="manual-setup" />

<Accordion title="Configuración manual">

**Para configurarlo manualmente:**

1. Desde la barra superior, abre el menú de la cuenta (menú desplegable del correo electrónico) > **Centro de seguridad**

![desde la cuenta, haz clic en el centro de seguridad Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. En la sección **Lista de redirecciones permitidas**, haz clic en **Administrar la lista de redirecciones permitidas**.

<Image alt="Gestiona la lista de redireccionamientos permitidos con arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />  

Se abre la página de la **lista de redireccionamiento permitidos**.

3. En la pestaña **Manual**, introduce un dominio o subdominio raíz en el campo **Nombre de dominio** y, a continuación, haz clic en **Agregar dominio a la lista**.

<Image alt="Agregar dominios manualmente.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* Utiliza únicamente letras, números, guiones y puntos.
* El dominio debe empezar y terminar con una letra o un número y puede tener hasta 253 caracteres.
* No añadas prefijos, como https://.

Consulta también las [características y limitaciones](/docs/set-up-your-domain-redirect-allowlist#características-y-limitaciones) de la lista de permitidos.

Los dominios añadidos se mostrarán en la lista de la derecha.

4. Haz clic en **Guardar lista**.

La lista de permitidos se aplicará a los clics en aproximadamente una hora.

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="Configuración mediante archivo CSV">

**Para configurar mediante la carga de un archivo CSV:**

1. Desde la barra superior, abre el menú de la cuenta (menú desplegable del correo electrónico) > **Centro de seguridad**  

![desde la cuenta, haz clic en el centro de seguridad Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. En la sección **Lista de redirecciones permitidas**, haz clic en **Administrar la lista de redirecciones permitidas**.  
<Image alt="Gestiona la lista de redireccionamientos permitidos con arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />  

Se abre la página de la **lista de redireccionamiento permitidos**.

3. Haz clic en la pestaña **Archivo CSV** y, luego, sigue las **instrucciones del archivo CSV** para crear un archivo que contenga tu lista de dominios.  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. Sube el archivo CSV al campo de carga.

* Una vez cargado el archivo, se analizará y se validarán los valores.
* Los valores válidos se añadirán automáticamente y se mostrarán en la lista de la derecha.
* No se añadirán valores no válidos. La información sobre los valores no válidos se mostrará en la sección **Estado de carga** para que puedas realizar las siguientes acciones: revisar o corregir los valores y volver a subirlos. Consulta las [características y limitaciones](/docs/set-up-your-domain-redirect-allowlist#características-y-limitaciones) de la lista de permitidos para más información.

5. Haz clic en **Guardar lista**.

Una vez guardada, la lista de redireccionamientos permitidos actualizada se aplicará a los clics en aproximadamente una hora.

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="Editar la lista de redireccionamientos permitidos">

Puedes agregar o eliminar dominios de la lista de permitidos en cualquier momento.

**Para eliminar un dominio de la lista de permitidos:**

1. En la lista de la derecha, coloca el cursor sobre el dominio que deseas eliminar y aparecerá un icono de eliminación.
2. Haz clic en el icono de borrar.
3. Haz clic en **Guardar lista** para guardar el cambio.

**Nota:** Una vez guardada, la lista de redireccionamientos permitidos actualizada se aplicará a los clics en aproximadamente una hora.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

| Caducado | Comentarios |
| --- | --- |
| Configuración | <ul><li>Los roles de «Administrador» y «Seguridad» pueden acceder a la lista de redireccionamientos permitidos y administrarla.</li><li>La lista de redireccionamientos permitidos está a nivel de cuenta y se aplica a todas las aplicaciones de la cuenta y a todos los enlaces de AppsFlyer.</li><li>La lista de redireccionamientos permitidos no está disponible para los miembros del equipo asociados a varias cuentas si una cuenta carece de un método de pago.</li><li>Notifica a tus compañeros de trabajo y partes interesadas que gestionan la creación de enlaces de AppsFlyer sobre la aplicación de las listas de redireccionamiento permitidas y los dominios de redireccionamiento permitidos.</li></ul> |
| Aplicabilidad | <ul><li>La lista de permitidos afecta a **todos los enlaces creados a través de AppsFlyer**, ya sea con <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>, los enlaces de atribución para una sola plataforma mediante la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">integración de partners</Anchor> o los <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">enlaces de atribución directa</Anchor> para plataformas de CTV, PC y consolas, independientemente de que se hayan creado antes o después de que se activara la lista de permitidos.</li><li>Incluye en la lista de permitidos los dominios de cualquier URL establecida como valor en la configuración de redireccionamiento de enlaces especificada aquí, ya sea un sitio web o una landing page personalizada, Google Play/App Store u otro sitio web de la tienda de aplicaciones. La lista de permitidos admite y protege las redirecciones para lo siguiente:<ul><li>Parámetros de enlace:<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>Configuración de redireccionamiento de plantillas de OneLink para iOS, Android y ordenador.</li><li>`af_dp` con un valor de URL web, sin embargo, este no es un tipo de valor recomendado. El objetivo de este parámetro es rellenar un <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_dp">esquema URI</Anchor> para abrir la aplicación.</li></ul></li><li>**Las vistas previas de enlaces pueden mostrar contenido alternativo:** Cuando AppsFlyer genera una vista previa social para un enlace, valida los parámetros de redirección del enlace con tu lista de permitidos de redirección. Si no es así, AppsFlyer no obtendrá una vista previa de esa página y mostrará en su lugar una vista previa alternativa.</li></ul> |
| Dominios | <ul><li>La lista de permitidos debe incluir al menos un dominio.</li><li>Solo se permiten dominios o subdominios raíz, no rutas específicas. No incluyas los protocolos `https://` o `http://` en el valor.</li><li>Al agregar un dominio raíz, se aplicará a todos los subdominios del dominio raíz.<br />Por ejemplo, si se agrega el dominio raíz «website.com», también incluirá «abc.website.com» y «xyz.website.com».</li><li>El redireccionamiento solo es compatible con dominios de acceso público.</li><li>No incluyas dominios de AppsFlyer (por ejemplo, onelink.me, app.appsflyer.com) ni otros dominios que tengan su propio mecanismo de redireccionamiento (por ejemplo, bit.ly) para reforzar la previsibilidad del redireccionamiento de tus enlaces.</li><li>Se pueden agregar hasta 100 dominios o subdominios a la lista de permitidos. Para ver la cantidad de dominios ya agregados, dirígete a la lista de redireccionamientos permitidos, donde se indica la cantidad de dominios.</li></ul> |
| Redireccionamiento | Si no estás seguro de si un dominio al que envía tu enlace está permitido:<br /><br />Revisa la lista de permitidos para asegurarte de que está incluida.<br /><br />O<br /><br />Utiliza la herramienta de <Anchor target="_blank" href="/marketers/es/docs/discover-your-campaign-link-parameters-and-behavior">detección de enlaces</Anchor>. Cuando se introduce un enlace, aparecerá una alerta en la columna **Parámetros** (en **Redirección**) si un dominio no está en la lista de permitidos. |

<div data-zendesk-anchors="overview=sobre-la-lista-de-redireccionamientos-permitidos h_01HYTJSH4YMAJ3CV88KZ9JD9XR=sobre-la-lista-de-redireccionamientos-permitidos set-up-your-redirect-allowlist=configura-tu-lista-de-redireccionamientos-permitidos h_01HY0BNRBEN91348744YME42SW=configura-tu-lista-de-redireccionamientos-permitidos h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=caracter%C3%ADsticas-y-limitaciones" />
