---
title: Gestión de usuarios
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-09-22T00:14:46Z'
  id: 4409128270481
  locale: es
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/es/articles/4409128270481
---
> **En resumen:** Crea y gestiona los usuarios de AppsFlyer de tu cuenta y asígnales permisos para acceder a funciones, aplicaciones y datos.

## Descripción general

Las cuentas de AppsFlyer permiten múltiples usuarios, cada uno con permisos administrados de manera individual. Tu plan de suscripción determina el número máximo de usuarios por cuenta.

Los permisos de cada usuario se definen a lo largo de 3 dimensiones principales:

* **Rol** (capacidad para acceder a funciones y realizar tareas)
* **Acceso a aplicaciones** para aplicaciones actuales y futuras
* **Acceso a datos** por fuente de medios y geolocalización
  * Dos puntos (:) ¡Importante! Algunos dashboards y funciones de AppsFlyer no están disponibles para los usuarios con acceso limitado a los datos (a las fuentes de medios y a las geolocalizaciones). Estos dashboard y funciones se [enumeran aquí](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

Los permisos dentro de cada una de estas dimensiones se asignan de forma independiente. En otras palabras, puedes asignar a un usuario un **rol** con amplias capacidades funcionales, pero permitirle ejercer esas capacidades solo dentro de un conjunto estrechamente definido de aplicaciones, **fuentes de medios y ubicaciones geográficas.** La única excepción es el [rol de administrador](#administrador), como se explica a continuación, que tiene acceso a todas las funcionalidades, aplicaciones, fuentes de medios y zonas geográficas.

Los administradores pueden [agregar usuarios a varias cuentas](#multiple-accounts) para que puedan cambiar fácilmente entre cuentas.

## Página de administración de usuarios

**Para acceder a la página de administración de usuarios:**

* En la barra superior, abre el menú de la cuenta (menú desplegable de direcciones de correo electrónico) > **Administración de usuarios**.

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

<div id="users-tab" />

<Accordion title="Pestaña de usuarios">

La pestaña **Usuarios** muestra una tabla de todos los usuarios existentes en tu cuenta. Este es el punto de partida para crear, administrar y eliminar usuarios.

Consejos para navegar por la pestaña “Usuarios”:

* Haz clic en el encabezado de la columna **Usuario** para ordenar la tabla alfabéticamente (ascendente/descendente).
* Utiliza el cuadro de búsqueda para buscar y mostrar usuarios específicos.
* Haz clic en el icono de filtro <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> en el encabezado de la columna para filtrar los usuarios por su rol (incluidos los roles temporales).
  * Para borrar el filtro, selecciona **Ninguno** en la lista desplegable de filtros.
* Haz clic en el encabezado de la columna **Último inicio de sesión** para ordenar los usuarios por la fecha en que se conectaron por última vez a AppsFlyer.
  * **Consejo:** Utiliza esta función para identificar y [eliminar](#deleting-users) fácilmente a los usuarios inactivos, mantén tu cuenta a salvo de inicios de sesión no autorizados.
* Utiliza las casillas de verificación para seleccionar y [editar varios usuarios](#edición-multiusuario) al mismo tiempo.
* Solo administradores: Haz clic en el icono <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> en la esquina superior derecha de la página para descargar la tabla de usuario completa como un archivo CSV.
  * El archivo descargado incluye las mismas columnas que la tabla de la pestaña **Usuario**.

</Accordion>

<div id="roles-tab" />

<Accordion title="Pestaña Roles">

La pestaña **Roles** muestra una lista de todos los roles definidos en tu cuenta, incluidos:

* [Roles predefinidos](#roles-predefinidos)
* [Roles personalizados](#gestionar-roles-personalizados) que has creado
* Cualquier [rol temporal](#roles-temporales) asignado actualmente a los usuarios

Junto a cada rol, puedes ver el número de usuarios actualmente asignados a ese rol.

Haz clic en el nombre de cualquier rol en el panel izquierdo para mostrar los detalles completos de las capacidades del rol.

</Accordion>

Explora a continuación las acciones disponibles para gestionar eficazmente a tus usuarios y sus roles.

## Administrar usuarios

Los administradores pueden crear nuevos usuarios, agregarlos a varias cuentas, editar sus detalles, como los roles y el acceso que tienen a las aplicaciones y los datos, y eliminar usuarios. Algunas de estas acciones se pueden realizar [en masa utilizando una API dedicada](#crea-usuarios-de-forma-masiva-a-través-de-la-api).

<div id="creating-users" />

<Accordion title="Crear usuario">

<Embed title="Gestión de usuarios" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

La página para crear o editar un usuario incluye varias secciones. Asegúrate de completarlas, como se describe a continuación. Cuando termines de hacer los cambios necesarios, haz clic en **Guardar** en la parte inferior derecha de la página.

#### Detalles del usuario

1. En la pestaña **Usuarios**, haz clic en **Nuevo usuario**.
2. Ingresa el nombre del usuario (obligatorio):
   * Puedes incluir letras, números, espacios, puntos (.), guiones (-), guiones bajos (\_) y comillas simples (') o dobles (").
   * No se permiten otros caracteres especiales.
3. Introduce la dirección de correo electrónico del usuario (obligatorio):

   * Puedes incluir letras, números, apóstrofes ('),ampersands (&), signos de dólar ($), símbolos hash (#), guiones (-), guiones bajos (\_) y puntos (.)
   * No se permiten dos puntos consecutivos (..) ni otros caracteres especiales.
   * Debe terminar con un dominio de correo electrónico válido.

   > 🚧 **¡Importante!**
   >
   > La dirección de correo electrónico de un usuario es la que los identifica en la plataforma de AppsFlyer, lo que significa:
   >
   > * No se puede cambiar más tarde sin eliminar y volver a crear el usuario.
   > * Debe ser una dirección de correo electrónico válida en la que el usuario pueda recibir correos electrónicos.
   > * No se puede asociar con otro usuario en ninguna cuenta de AppsFlyer, [a excepción de los usuarios en cuentas beta](#multiple-accounts). Si la dirección de correo electrónico ya está en uso (ya sea en tu cuenta o en otra), verás el mensaje *No se puede crear este usuario.* Sigue los [pasos para la resolución de problemas a continuación](/docs/user-management#troubleshooting-can-t-create-this-user) para resolver este problema.

4. [Opcional] Selecciona el departamento del usuario.

#### Rol

Selecciona el rol del usuario (obligatorio): un rol predefinido o un rol personalizado que ya hayas creado.

#### Acceso a la aplicación

Selecciona a qué aplicaciones puede acceder el usuario:

* La configuración predeterminada permite el acceso a todas las aplicaciones actuales y futuras de la cuenta. Para cambiar esta configuración, usa las casillas de verificación para seleccionar y deseleccionar aplicaciones.
* Un usuario puede tener acceso a todas las aplicaciones futuras solo si tiene acceso a todas las aplicaciones actuales.

#### Acceso a datos

Establece los niveles de acceso del usuario para fuentes de medios y geos. Decide si otorgar acceso a todos o acceso selectivo a específicos.

> 📘 **Nota:**
>
> Los usuarios con acceso limitado a la fuente de medios o geos no pueden acceder a ciertos [dashboards y funciones](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

#### Fuentes de medios

Por defecto, la configuración **Todo** permite el acceso a todas las fuentes de medios dentro de la cuenta. Esto incluye aquellas que se agregarán en el futuro. Seleccionar fuentes de medios específicas no incluye acceso a futuras fuentes de medios.

> 📘 **Nota:**
>
> * Los usuarios con acceso limitado a la fuente de medios no pueden acceder a ciertos [dashboards y funciones](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).
> * Los roles de administrador y seguridad tienen acceso sin restricciones a todas las fuentes de medios. Esto no se puede cambiar.

**Tipo de fuente de medios:**

Hay dos tipos de fuentes de medios mostradas en la lista:

* **Fuentes de medios pagadas:** Ad networks, ad networks de auto-reporte (SRNs) y agencias
* **<span id="custom_media_sources"></span>Fuente de medios personalizada:** Fuentes de medios predefinidas. Esto puede incluir enlaces de medios propios, enlaces de fuente única, enlaces de OneLink y enlaces que el anunciante creó fuera de AppsFlyer.

**Especificaciones para la lista de fuentes de medios:**

* Presenta fuentes de medios con tráfico de los últimos 24 meses, ordenadas por aquellas con el tráfico más reciente
* Las agencias se agrupan por separado al final de la lista
* Contiene un máximo de 10.000 fuentes de medios:
  * Hasta 5.000 ad networks, SRNs y fuentes de medios personalizadas
  * Hasta 5.000 agencias
* Se actualiza una vez al día. Las fuentes de medios recién añadidas solo son visibles en la lista un día después de que el tráfico haya ingresado al sistema.
* Las fuentes de medios sin tráfico durante más de 5 años se eliminan de la lista.

**Para cambiar la configuración predeterminada:**

1. Bajo **Fuentes de medios**, haz clic en **Todo**.
2. En la lista desplegable, selecciona las fuentes de medios específicas para otorgar acceso al usuario.

Después de guardar estas configuraciones, los dashboards de usuario muestran solo datos de las fuentes de medios seleccionadas.

#### Geolocalizaciones

Selecciona si los usuarios tienen acceso a datos para **Todas** las geos o solo para geos específicas. La configuración predeterminada permite el acceso a todas las geolocalizaciones. El acceso limitado significa que los usuarios no pueden acceder a ciertos [dashboards y funciones](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

**Para cambiar la configuración predeterminada:**

1. En **Geos**, haz clic en **Todo**.
2. En la lista desplegable, selecciona las geos específicos para otorgar acceso al usuario.

#### Activación del usuario

Una vez creado el usuario, puedes verlo en la tabla de usuarios con un icono de sobre ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png). Esto indica que se ha enviado una invitación y que la cuenta está en espera de activación. El usuario debe activar su cuenta mediante el enlace recibido en su correo electrónico. El enlace de activación es válido por 48 horas. Después de que el usuario active su cuenta, el sobre desaparece.

> 📘 **Nota:**
>
> Si el usuario no recibió la invitación o si el enlace ha expirado, puedes [volver a enviar la invitación](/docs/user-management#resending-a-user-invitation).

</Accordion>

<div id="multiple-accounts" />

<Accordion title="Agregar usuarios a varias cuentas">

Los usuarios pueden agregarse a varias cuentas y asignarse a diferentes roles en cada cuenta. Esto ayuda a los usuarios a trabajar en diferentes cuentas sin la necesidad de volver a introducir sus credenciales.

#### Inicia sesión en varias cuentas

Los usuarios pueden iniciar sesión en múltiples cuentas utilizando todos los métodos de inicio de sesión: credenciales (nombre de usuario y contraseña), <Anchor target="_blank" href="/marketers/es/docs/implementing-and-using-2fa-login">2FA</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>.

> 📘 **Nota:**
>
> Al cambiar de cuenta (no durante el login inicial), los usuarios también deben introducir un código de verificación de 6 dígitos enviado a su correo electrónico, independientemente del método de login que hayan usado para iniciar sesión. <Anchor target="_blank" href="/marketers/es/docs/welcome-to-appsflyer#cambiar-entre-tus-cuentas">Consulta este artículo para obtener más información sobre cómo cambiar de cuenta</Anchor>.

#### Cuentas y usuarios compatibles

Las siguientes cuentas admiten tener el mismo usuario en múltiples cuentas: Las siguientes cuentas admiten tener el mismo usuario en múltiples cuentas: Con los permisos adecuados, pueden añadir usuarios a todas sus cuentas. Ver limitaciones a continuación.

#### Limitaciones para añadir usuarios a múltiples cuentas

* Esta función está disponible solo para cuentas de anunciantes y solo para usuarios con permisos de gestión de usuarios apropiados.
* Un usuario puede tener el rol de [propietario de una cuenta](#propietario-de-la-cuenta) para una sola cuenta. En otras cuentas, pueden desempeñar cualquier otro rol.
* Los usuarios que aún no hayan [activado su cuenta](#activación-del-usuario) no podrán ser agregados a otra cuenta.

#### Agregar usuarios a varias cuentas

**Para agregar el mismo usuario a varias cuentas:**

1. Ingresa a la cuenta en la que quieres agregar el usuario.
2. En la barra de menú, haz clic en el **menú desplegable de dirección de correo electrónico** > **Gestión de usuarios**.
3. En la pestaña **Usuarios**, haz clic en **Nuevo usuario**.
4. Ingresa los detalles requeridos, selecciona el rol para el usuario en esta cuenta y haz clic en **Guardar**.
5. Repite los pasos del 1 al 4 para agregar los usuarios a otras cuentas.

</Accordion>

<div id="editing-users" />

<Accordion title="Editar usuario">

Los usuarios se pueden editar uno a la vez o en grupos.

#### Edición individual

**Para editar un usuario individual:**

1. En la pestaña **Usuarios**, haz clic en el botón **Acciones** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> en el extremo derecho de la fila del usuario.
2. Selecciona **Editar** en el menú.
3. Edita la configuración del usuario según sea necesario.
4. Todas las configuraciones excepto la dirección de correo electrónico son editables (incluidos el rol, las aplicaciones, las fuentes de medios y las geolocalizaciones).
5. Haz clic en **Guardar**.

#### Edición multiusuario

La edición multiusuario es una forma eficiente de cambiar los permisos de cuenta de varios usuarios a la vez. El uso de esta función en combinación con las capacidades de búsqueda y filtrado de la pestaña **Usuarios** puede resultar particularmente útil para administrar un gran número de usuarios.

> 📘 **Nota:**
>
> No se pueden asignar usuarios a la función de administrador mediante la edición multiusuario.

**Para editar varios usuarios:**

1. En la pestaña **Usuarios**, selecciona las casillas de verificación del usuario o de los usuarios que deseas editar.
   * Selecciona la casilla de verificación en el encabezado de la columna para seleccionar todos los usuarios visibles.
   * El número de usuarios seleccionados actualmente se muestra en el lado derecho del cuadro de búsqueda. Ten en cuenta que el [propietario de la cuenta](#propietario-de-la-cuenta) no se puede seleccionar y no se incluye en la cantidad de usuarios seleccionados.
2. En la parte superior derecha de la tabla se muestra una serie de botones: **Rol, aplicaciones, fuentes de medios** y **ubicaciones geográficas.**
   * Si uno o más de los usuarios seleccionados tienen acceso a aplicaciones futuras, el botón **Aplicaciones** no estará disponible. (Consulta [Limitaciones del rol temporal](/docs/user-management#limitaciones-de-los-roles-temporales) a continuación).
3. Haz clic en el botón de los permisos que deseas cambiar.
4. Realiza los cambios necesarios utilizando el cuadro de diálogo o las listas desplegables que se muestran.
   * ¡Recuerda que tus cambios se aplican a todos los usuarios seleccionados!
5. Los usuarios editados se resaltan en la tabla y los usuarios aparecen como aparecerán una vez que se guarden los cambios. Sin embargo, aún tienes la oportunidad de revisar tus cambios y confirmarlos o cancelarlos en el siguiente paso.
6. Revisa tus cambios. Haz clic en **Guardar** para confirmar o en **Cancelar** para deshacer la acción.

> 📄 **Ejemplo**
>
> **Escenario:**
>
> * Hay 30 usuarios en tu cuenta. Diez de ellos están en el rol **Marketing – limitado**.
> * Alice, Bill y Charlie acaban de recibir promociones, y quieres cambiarles del rol **Marketing – limitado** al rol **Marketing**.
> * Alice trabajará con la aplicación Astounding. Bill trabajará con la aplicación Beautiful. Charlie trabajará con la aplicación Charming.
>
> **Pasos:**
>
> 1. Utiliza el filtro de rol <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> para ver solo los usuarios en el rol **Marketing – limitado**.
> 2. Cambiar a Alice, Bill y Charlie al rol de **Marketing**:
>    * Selecciona las casillas de verificación de Alice, Bill y Charlie.
>    * Haz clic en el botón **Rol**.
>    * Selecciona **Marketing** en la lista desplegable.
>    * Haz clic en **Guardar** para confirmar.
>    * Ten en cuenta que una vez que confirmes los cambios, el filtro **Rol** se borrará y la tabla mostrará todos los usuarios.
> 3. Proporciona a Alice, Bill y Charlie el acceso adecuado a la aplicación:
>    * Utiliza el cuadro de búsqueda para encontrar a Alice y, a continuación, edita individualmente su usuario para darle acceso a la aplicación Astounding.
>    * Repite estos pasos para Bill y Charlie para darles acceso a Beautiful y Charming, respectivamente.

</Accordion>

<div id="deleting-users" />

<Accordion title="Eliminar usuarios">

Se pueden eliminar varios usuarios de la cuenta de forma masiva.

> 📘 **Nota:**
>
> * El [propietario de la cuenta](/docs/user-management#propietario-de-la-cuenta) no se puede eliminar
> * La eliminación de usuarios es irreversible

<span id="to-delete-users"></span>**Para eliminar usuarios:**

1. En la pestaña **Usuarios**, selecciona las casillas de verificación de los usuarios que deseas eliminar. Puedes utilizar la búsqueda y los filtros para ayudar a encontrar usuarios.
2. Después de seleccionar usuarios, haz clic en el botón **Eliminar** que ahora aparece en la parte superior derecha de la tabla.
3. La ventana de confirmación enumera los usuarios que se eliminarán. Haz clic en **Sí, eliminar** para confirmar la eliminación.

</Accordion>

### Crea usuarios de forma masiva a través de la API

Algunas acciones de gestión de usuarios se pueden realizar en masa utilizando <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-management-overview">una API dedicada</Anchor>:

* [Crear](https://dev.appsflyer.com/hc/reference/bulk-users-post) múltiples usuarios
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">Eliminar</Anchor> múltiples usuarios
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">Obtener</Anchor> detalles de acceso de múltiples usuarios

La API admite las principales funciones de gestión de usuarios en la plataforma e incluye las mismas verificaciones de errores.

## Gestionar roles

Cada usuario de tu cuenta de AppsFlyer debe tener asignado un rol. Cada uno de estos roles define las características específicas de AppsFlyer a las que el usuario puede acceder y las funciones que puede realizar. Encontrarás una lista completa de las capacidades por rol en la pestaña [Roles](#roles-tab) de la página **Administración de usuarios**.

Los roles dentro de AppsFlyer pueden ser [roles predefinidos](#roles-predefinidos), [roles personalizados](#roles-personalizados) o (en ciertas circunstancias) [roles temporales](#roles-temporales).

### Roles predefinidos

AppsFlyer está configurado con muchos roles predefinidos:

* [Administrador — un rol especial](#administrador)
* Administrador de equipo
* Responsable de marketing
* marketing
* Marketing limitado
* Contribuyente
* Contabilidad
* Seguridad
* Garantía de calidad

> 📘 **Nota:**
>
> Para cada uno de estos roles predefinidos, las capacidades funcionales son fijas: no se permite "mezclar y combinar". Sin embargo, puedes cambiar las capacidades funcionales de un usuario en cualquier momento asignándole un rol predefinido o personalizado diferente (excepto el de [propietario de la cuenta](#propietario-de-la-cuenta), como se describe a continuación).

> 📄 **Ejemplo**
>
> Has asignado a Bill Bates el rol de **Administrador del equipo.** Este rol le permite a Bill gestionar las **plantillas de OneLink**, pero no le permite acceder a las páginas **Mi plan** y **Pagos**.
>
> **Pregunta:** ¿Puedo mantener a Bill en el rol de administrador de equipo pero también darle la posibilidad de acceder a las páginas Mi plan y Pagos? ¿Puedo eliminar su capacidad para administrar plantillas de OneLink?
>
> **Respuesta:** No. Mientras Bill permanezca en el rol de administrador de equipo, no puedes darle la posibilidad de acceder a las páginas Mi plan y Pagos. Tampoco puedes eliminar su capacidad para administrar plantillas de OneLink. Por supuesto, puedes asignar un rol diferente a Bill, y sus capacidades cambiarán a las definidas por ese rol. O bien, puedes crear un rol personalizado para Bill que cambie sus capacidades de acuerdo a tus necesidades.

### Administrador

Una cuenta de AppsFlyer puede tener **uno o más administradores**. Este rol tiene varias características únicas:

#### Acceso

El rol de administrador tiene acceso a **todas las capacidades de la cuenta**, incluidas las siguientes:

* Todas las características y funciones
* Todas las aplicaciones actuales y futuras
* Todas las fuentes de medios y geolocalizaciones

Esta característica de "acceso completo" del rol de administrador no se puede cambiar ni limitar.

#### Gestionar tokens

Solo un usuario con un rol de Administrador puede <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">gestionar tokens</Anchor>: crear, renombrar y eliminar tokens de API y de servidor a servidor.

#### Duplicación de roles

El rol de administrador **no se puede duplicar** al crear [roles personalizados](#gestionar-roles-personalizados).

#### Invita a nuevos partners a AppsFlyer

Un usuario con un rol de administrador puede <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#invitar-nuevos-partners-a-appsflyer">enviar un enlace de invitación</Anchor> a través del Partner Marketplace para invitar a un partner que no está integrado con AppsFlyer.

### Propietario de la cuenta

El usuario creado en el momento en que se abrió la cuenta (el **"propietario de la cuenta"**) tiene **asignado el rol de Administrador de forma predeterminada**. El propietario de la cuenta es inicialmente responsable de crear los usuarios adicionales, hasta que se creen usuarios adicionales con capacidades de gestión de usuarios.

Un propietario de cuenta tiene características únicas más allá de las del rol de Administrador que no es el propietario de la cuenta. El propietario de la cuenta **no** se puede eliminar, su rol de administrador no puede ser desactivado ni se puede editar de ninguna otra forma desde la página de [Administración de usuarios](/docs/user-management#página-de-administración-de-usuarios). Si necesitas cambiar el propietario de la cuenta, sigue los **pasos que se indican más abajo**.

### Roles personalizados

Los roles predefinidos en AppsFlyer han sido configurados con las combinaciones específicas de capacidades requeridas en la mayoría de las situaciones. Por esta razón, muchos anunciantes descubren que no necesitan personalizar más los roles. Sin embargo, cuando se requiere una personalización adicional, los roles predefinidos siguen siendo un gran punto de partida para gestionar las capacidades de tus usuarios.

Aprender más sobre [gestión de roles personalizados](#gestionar-roles-personalizados).

### Roles temporales

Si tu cuenta de AppsFlyer existía en nuestro sistema de gestión de usuarios anterior (cuando los únicos tipos de cuenta disponibles eran Administrador y Miembro del Equipo), todos los usuarios se incorporaron al nuevo sistema con sus capacidades sin cambios. Como resultado, la mayoría de estos usuarios aparecen en el sistema actual con **roles temporales**.

Saber más sobre la [administración de roles temporales](#managing-temp-roles).

### Obtener datos de roles a través de la API

A través de la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">API de obtener roles</Anchor>, puedes recuperar una lista de roles actuales y sus atributos correspondientes específicos de tu cuenta.

## Gestionar roles personalizados

<div id="creating-custom-roles" />

<Accordion title="Crear roles personalizados">

* **Requisito previo:** Solo los [propietarios de cuentas](#propietario-de-la-cuenta) o usuarios con [acceso al rol de administrador](#administrador) pueden crear un rol personalizado.

**Para crear un rol personalizado:**

1. En el panel izquierdo de la pestaña **Roles**, debajo de la barra de búsqueda, haz clic en **+ Nuevo rol personalizado**.
2. **Nombre del rol:** Introduce un nombre para el nuevo rol que estás creando.
   * **Nota:** Una vez que hayas guardado un rol personalizado, el nombre del rol no se puede editar.
   * **Recomendación:** Haz que el nombre sea descriptivo y fácilmente identificable más adelante.
3. **Plantilla de rol:** Como punto de partida, selecciona un rol predefinido que se asemeje más a las capacidades y permisos para el nuevo rol personalizado.
4. Ajusta la configuración de la plantilla de rol seleccionada de acuerdo con los requisitos de tu rol personalizado. Los niveles de permiso de todas las capacidades editables se muestran como botones. Haz clic en estos botones para cambiar los niveles de permiso del nuevo rol personalizado. (Asegúrate de desplazarte hacia abajo para ver la lista completa de capacidades).
   * **Nota:** Las capacidades que no aparecen como botones actualmente no se pueden editar.
5. Después de establecer permisos para todas las capacidades relevantes, haz clic en **Guardar rol**.  
   El nuevo rol personalizado se muestra en el panel izquierdo y se puede asignar cuando se crean nuevos usuarios o se editan usuarios existentes.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="Editar roles personalizados">

**Para editar un rol personalizado:**

1. En el panel izquierdo de la pestaña **Roles**, haz clic en el nombre del rol personalizado que deseas editar.
2. Haz clic en el ícono **Editar** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" /> en la esquina superior derecha de la página. La visualización del panel derecho cambia, lo que te permite editar la configuración de permisos del rol.
   * **Nota:** El nombre del rol no se puede editar. Para cambiarlo, debes eliminar el rol y recrear uno nuevo con un nombre diferente.
3. Los niveles de permiso de todas las capacidades editables se muestran como botones. Haz clic en estos botones para cambiar los niveles de permiso del nuevo rol personalizado. (Asegúrate de desplazarte hacia abajo para ver la lista completa de capacidades).
4. Cuando estés satisfecho con todas tus selecciones, haz clic en el botón **Guardar rol**.
5. Los niveles de permiso del rol se cambian para todos los usuarios nuevos y existentes.

> 🚧 **¡Importante!**
>
> Cualquier cambio que realices en un rol personalizado se aplica automáticamente a **todos los usuarios existentes** en ese rol.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="Eliminar roles personalizados">

**Para eliminar un rol personalizado:**

1. En el panel izquierdo de la pestaña **Roles**, haz clic en el nombre del rol personalizado que deseas eliminar.
2. Haz clic en el ícono **Eliminar** <Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" /> en la esquina superior derecha de la página.
3. Confirma que deseas eliminar el rol.
   * Un rol personalizado solo se puede eliminar cuando no hay usuarios asignados. Si hay usuarios asignados actualmente a un rol personalizado, asigna estos usuarios a un rol diferente antes de eliminar el rol personalizado.

</Accordion>

## Situaciones especiales y procedimientos adicionales

<div id="managing-temp-roles" />

<Accordion title="Gestionar roles temporales">

Si tu cuenta utilizaba anteriormente nuestro sistema de administración de usuarios anterior, se asignaban [**roles temporales**](/docs/user-management#roles-temporales) a los usuarios existentes para garantizar que se incorporaran al nuevo sistema sin cambios en sus capacidades.

* A los usuarios con las mismas capacidades se les asignó el mismo rol temporal.
* Utiliza las características de la [pestaña Roles](/docs/user-management#roles-tab) para revisar las capacidades de cada rol temporal y una lista de usuarios que se encuentran actualmente en él.

#### Limitaciones de los roles temporales

Los roles temporales se diseñaron específicamente para permitir una transición fluida desde nuestro sistema de administración de usuarios anterior. Por lo tanto, solo están disponibles en situaciones limitadas:

* Los roles temporales no se pueden asignar a otros usuarios (ya sean nuevos o existentes).
* A un usuario con un rol temporal no se le puede asignar un rol temporal diferente (aunque puedes cambiar las aplicaciones, las fuentes de medios y las geolocalizaciones a las que tiene acceso).
  * Ten en cuenta que el acceso de un usuario a aplicaciones futuras **no se** puede cambiar mientras el usuario tiene un rol temporal.
* Cuando un usuario con un rol temporal se cambia a un rol predefinido, no se puede devolver al rol temporal asignado anteriormente (o a cualquier otro rol temporal).
* Si el último usuario en un rol temporal se elimina, el rol ya no aparecerá en tu cuenta.

> 📄 **Ejemplo**
>
> Tu cuenta utilizó anteriormente nuestro sistema de administración de usuarios anterior. Diana y Edward eran usuarios existentes en el momento en que tu cuenta se movió al nuevo sistema. Diana ahora está en el rol temporal 1, y Edward está en el rol temporal 2.
>
> * Contratas a una nueva empleada, Fiona. Puedes asignar a Fiona cualquiera de los [roles predefinidos](/docs/user-management#roles-predefinidos). Sin embargo, no puedes asignar a Fiona el rol temporal 1 o el rol temporal 2.
> * Diana no se puede mover del rol temporal 1 al rol temporal 2. Sin embargo, puedes asignarle cualquiera de los roles predefinidos. También puedes cambiar su acceso a aplicaciones, fuentes de medios y geolocalizaciones según sea necesario.
> * Si trasladas a Diana del rol temporal 1 al rol Contabilidad, no podrá volver más tarde al rol temporal 1.
> * Si Diana era el último usuario en el rol Temporal 1 cuando la moviste al rol de Contabilidad, el rol Temporal 1 ya no aparecerá en tu cuenta.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="Dashboard y disponibilidad de funciones para usuarios con acceso limitado a la fuente de medios/geolocalización">

Los siguientes dashboards de AppsFlyer **no están disponibles** para los usuarios cuyo acceso está limitado a fuentes de medios y geolocalizaciones específicas:

* Resumen de SKAN
* Estudio de conversión SKAN
* Las alertas de Protect360 se actualizan a la hora UTC diaria.
* Retención
* Atribución people-based
* Incrementalidad

Además, las siguientes funciones de AppsFlyer **no están disponibles** para estos usuarios:

* Pivot
* OneLink
* Reglas de validación
* Audiences (no disponible para usuarios restringidos de fuentes de medios; disponible para usuarios con geolocalización restringida).
* Información del SDK
* Procesamiento del gasto publicitario
* ETL de costos

</Accordion>

<div id="combined-media-source-and-agency-access" />

<Accordion title="Acceso combinado a fuente de medios y agencia">

Cuando concedes a un usuario acceso a una agencia específica **y** a una fuente de medios específica, su acceso a los datos refleja solo la intersección entre ambas. No ven todos los datos de esa agencia en todas las fuentes de medios, ni todos los datos de esa fuente de medios en todas las agencias; solo la parte en la que ambos permisos se superponen.

> 📄 **Ejemplo**
>
> Concedes a un usuario acceso a la agencia B y a la fuente de medios A. La agencia B gestiona instalaciones de la app procedentes de varias fuentes de medios, incluida la fuente de medios A. Este usuario solo ve las instalaciones de la fuente de medios A que gestiona la agencia B, no los datos de la agencia B de otras fuentes de medios ni los datos de la fuente de medios A gestionados por otras agencias.

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="Cambiar el propietario de la cuenta">

Como todos los administradores tienen básicamente los mismos permisos que el propietario de la cuenta, no suele ser necesario cambiar el propietario de la cuenta. Pero si necesitas cambiar el propietario de la cuenta, sigue estos pasos para hacerlo.

> 🚧 **¡Importante!**
>
> El cambio del propietario de la cuenta debe completarse manualmente de acuerdo con los pasos a continuación. No se puede hacer desde la página de **Administración de usuarios**.

#### #1–Asigna a un miembro del equipo el rol de Admin

Solo un usuario con el rol de Admin puede solicitar el cambio de propietario de la cuenta. Por lo tanto, se recomienda:

* Asigna a un miembro del equipo que pueda completar todos los pasos el **Admin** rol.
* El usuario debe activar su cuenta (es decir, iniciar sesión al menos una vez).

#### #1 – Envía una solicitud por correo electrónico

Para iniciar el proceso de cambio del propietario de la cuenta, envía una solicitud por correo electrónico a AppsFlyer **desde el correo electrónico del propietario actual de la cuenta**.

* Asegúrate de que esta sea la dirección de correo electrónico del propietario actual de la cuenta tal como aparece en tu cuenta de AppsFlyer.
* Si el propietario actual de la cuenta ha abandonado tu empresa, pídele a tu equipo de TI que te permita enviar un correo electrónico desde su dirección.

Incluye la siguiente información en tu solicitud:

| Para: | Tu CSM de AppsFlyer o hello@appsflyer.com |
| --- | --- |
| CC: | Correo electrónico del nuevo propietario de la cuenta |
| Asunto: | Solicitud para cambiar el propietario de la cuenta por `{nombre de la cuenta}` |
| Cuerpo: | Mensaje corto que incluye el nombre y el título del nuevo propietario de la cuenta |

Utiliza este correo electrónico de ejemplo como referencia:

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

#### #2 – Próximos pasos

Una vez que se haya procesado el cambio, recibirás una notificación por correo electrónico de AppsFlyer.

* Si deseas que el propietario anterior de la cuenta continúe usando tu cuenta de AppsFlyer, [crea un nuevo usuario](/docs/user-management#creating-users) para él y asígnale un nuevo rol.
* Las API que usan el token v2 no se ven afectadas por cambiar el propietario de la cuenta. <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Saber más sobre cómo administrar tokens</Anchor>.

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="Resolución de problemas: No se puede crear este usuario">

Si recibes el mensaje de error *No se puede crear este usuario* al ingresar la dirección de correo electrónico de un nuevo usuario, generalmente significa que el correo electrónico ya está asociado con un usuario de AppsFlyer (ya sea en tu cuenta o en uno diferente). Sigue los pasos pertinentes a tu situación:

Si el usuario está en tu cuenta:

* Comprueba si el usuario ha activado su cuenta. De lo contrario, [vuelve a enviar la invitación](/docs/user-management#resending-a-user-invitation) si es necesario.
* Si el usuario ha activado su cuenta, pídele que intente iniciar sesión nuevamente con la dirección de correo electrónico asociada con su usuario. Indícale que siga los pasos de **¿Olvidaste tu contraseña?** si es necesario.

Si el correo electrónico del usuario se utiliza en una cuenta diferente o no puedes determinar la cuenta en la que se utiliza el correo electrónico del usuario, selecciona una de las siguientes opciones:

* Elimínalo de la otra cuenta y agrégalo a la tuya (es necesario que tengas los permisos requeridos en la otra cuenta); o
* Agrégalo a tu cuenta con otra dirección de correo electrónico. Debe ser una dirección de correo electrónico válida en la que pueda recibir un correo electrónico; o
* Contacta con tu Customer Success Manager (CSM) o envía un correo electrónico a nuestro equipo de Engagement con el Cliente a [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="Reenviar una invitación a un usuario">

Si un nuevo usuario no recibió su [invitación de activación de cuenta](#activación-del-usuario) o si no se activó dentro de las 48 horas, puedes volver a enviar el correo electrónico de la siguiente manera:

1. En la pestaña **Usuarios**, haz clic en el botón **Acciones** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> en el extremo derecho de la fila del usuario.
   * Ten en cuenta que el usuario todavía se muestra con un icono de sobre ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png), lo que indica que aún no ha activado su cuenta).
2. Selecciona **Reenviar invitación por correo electrónico** en el menú.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Restablecer la autenticación de dos factores (2FA) de un usuario">

Si tu cuenta usa 2FA, puede haber ocasiones en las que necesites restablecer la configuración 2FA de un usuario. Hazlo de la siguiente manera:

1. En la pestaña **Usuarios**, haz clic en el botón **Acciones** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> en el extremo derecho de la fila del usuario.
2. Selecciona **Restablecer 2FA** en el menú.

**Nota:** Un administrador puede restablecer el 2FA de cualquier otro administrador que no sea la suya o la del [propietario de la cuenta](#propietario-de-la-cuenta). Para restablecer la autenticación de dos factores del propietario de la cuenta, contacta con el equipo de soporte de AppsFlyer.

</Accordion>

<div data-zendesk-anchors="background=descripci%C3%B3n-general h_01H9Q9007QP8YMPDVZ57N4M1HD=descripci%C3%B3n-general user-management-page=p%C3%A1gina-de-administraci%C3%B3n-de-usuarios h_01H9Q9007QW1RD3MTTV01Q8QRE=p%C3%A1gina-de-administraci%C3%B3n-de-usuarios h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=administrar-usuarios h_01H9Q9007QYSJZYZMP0C8NA98G=administrar-usuarios h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=detalles-del-usuario h_01HMP4EYM562HFSP80MQQ82B47=detalles-del-usuario h_01H9Q9007Q6SK4391P8C3A147N=importante role=rol h_01HMP4Q56XP10343YFW17VX00W=rol app-access=acceso-a-la-aplicaci%C3%B3n h_01HMP4RDXVRM3Z0WDCJD3P2W8S=acceso-a-la-aplicaci%C3%B3n data-access=acceso-a-datos h_01HMP4SW7RMESGDFNP1KFN7641=acceso-a-datos h_01HR6VBJHTZM48493B29FCWQT8=nota media-sources=fuentes-de-medios h_01HRPRS4BHX2AMR9W4FNGE0N1P=fuentes-de-medios 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=nota-1 geos=geolocalizaciones h_01HRPRVXYFX4P2ZG0H5HPNF2AG=geolocalizaciones user-activation=activaci%C3%B3n-del-usuario h_01HFRCWNR8T5J990TV68K6B45T=activaci%C3%B3n-del-usuario h_01HFRFRQXD1RD66EBRQH0T7Q78=nota-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=inicia-sesi%C3%B3n-en-varias-cuentas h_01J2GN6ZA29SFC12HR4ZVBDFDT=inicia-sesi%C3%B3n-en-varias-cuentas h_01M2ZBMHB9P3FEAFDA637ZH4MC=nota-3 supported-accounts-and-users=cuentas-y-usuarios-compatibles h_01H9Z7XXE0CKRSE191ZN017MGE=cuentas-y-usuarios-compatibles limitations-on-adding-users-to-multiple-accounts=limitaciones-para-a%C3%B1adir-usuarios-a-m%C3%BAltiples-cuentas 01J2GMV7ZYV5G0Q6C18RRY1TY0=limitaciones-para-a%C3%B1adir-usuarios-a-m%C3%BAltiples-cuentas add-users-to-multiple-accounts=agregar-usuarios-a-varias-cuentas h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=agregar-usuarios-a-varias-cuentas h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=edici%C3%B3n-individual h_01H9Q9007R3QW4AYRJBTF0X7B9=edici%C3%B3n-individual multiuser-editing=edici%C3%B3n-multiusuario h_01H9Q9007R4JQPKQS2HVB251GH=edici%C3%B3n-multiusuario h_01H9Q9007R9M9YDMJ2YYNZDW3D=nota-4 h_01H9Q9007RAFXB899YK6CADD9R=ejemplo h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=nota-5 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=crea-usuarios-de-forma-masiva-a-trav%C3%A9s-de-la-api h_01HYASD07FG0HGX22FTHEQ9APP=crea-usuarios-de-forma-masiva-a-trav%C3%A9s-de-la-api more-about-roles=gestionar-roles h_01H9Q9007Q8CMR2RD6E4KN26YE=gestionar-roles predefined-roles=roles-predefinidos h_01H9Q9007Q28D43B6JRP71NDQM=roles-predefinidos h_01J6VZ7ANV3JHJZ5EVBF1BY585=nota-6 h_01H9Q9007QXSGG375PR2SCS7QS=ejemplo-1 admin%E2%80%94a-special-role=administrador h_01H9Q9007Q4A6KETAAGAWEPQQ9=administrador access=acceso h_01HF8N2Z8ZP3HV06XJPMQ19DTK=acceso manage-tokens=gestionar-tokens h_01HV1F5S0FE083B73P8MEYX4FM=gestionar-tokens role-duplication=duplicaci%C3%B3n-de-roles h_01HF8N6DKWYKMBE35QKKB55KEM=duplicaci%C3%B3n-de-roles invite-new-partners-to-appsflyer=invita-a-nuevos-partners-a-appsflyer h_01HVK8EB3SMC09VD8TJND9YWCD=invita-a-nuevos-partners-a-appsflyer account-owner=propietario-de-la-cuenta h_01HF8N69VYE3ZJVFW1ENC0XA62=propietario-de-la-cuenta custom-roles=roles-personalizados h_01H9Q9007QZ7F2TX8B9D1TNYPN=roles-personalizados temp-roles=roles-temporales h_01H9Q9007QE8YT1DNRPNTFQWYH=roles-temporales get-roles-data-via-api=obtener-datos-de-roles-a-trav%C3%A9s-de-la-api h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=obtener-datos-de-roles-a-trav%C3%A9s-de-la-api managing-custom-roles=gestionar-roles-personalizados h_01H9Q9007RQHHNHZ3M38E88YPW=gestionar-roles-personalizados h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=importante-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=situaciones-especiales-y-procedimientos-adicionales h_01H9Q9007RSWFVAZQ5DNVNN7T2=situaciones-especiales-y-procedimientos-adicionales h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=limitaciones-de-los-roles-temporales h_01H9Q9007RJ0CQRGEYNEQJ2QR5=limitaciones-de-los-roles-temporales h_01H9Q9007RHBYD2B6PHQRD7TWV=ejemplo-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01K7B3N5G8R2M4X9Y1D6W0T3PQ=combined-media-source-and-agency-access h_01K7B3N7H9S3N5Y0Z2E7X1U4RT=ejemplo-3 h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=importante-2 1%E2%80%93send-an-email-request=1asigna-a-un-miembro-del-equipo-el-rol-de-admin h_01H9Q9007RSA5406WXCB1E4JRK=1asigna-a-un-miembro-del-equipo-el-rol-de-admin h_01K5P1G80QACK6YMKX4AGJA5ZK=1--env%C3%ADa-una-solicitud-por-correo-electr%C3%B3nico 2%E2%80%93next-steps=2--pr%C3%B3ximos-pasos h_01H9Q9007RZ2X9RAY8067SZETF=2--pr%C3%B3ximos-pasos troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
