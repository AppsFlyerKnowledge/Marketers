---
title: Permisos de uso compartido de la plataforma de colaboración de datos (DCP)
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
  created_at: '2025-12-17T10:36:33Z'
  edited_at: '2026-08-12T11:54:08Z'
  id: 42009477902353
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/42009477902353
---
> **En resumen:** Define los permisos de colaboración de la DCP que determinan cómo tu colaborador puede usar tus datos compartidos.

Este artículo describe los permisos disponibles al compartir datos en una colaboración de la plataforma de colaboración de datos (DCP). Los permisos de uso compartido se definen mediante la **política de colaboración** que configuras al <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration">crear una colaboración</Anchor> y especifican qué pueden hacer los colaboradores con tus datos y qué recursos o Partners de activación pueden usar. Además de esta política predeterminada, también se pueden configurar permisos de datos personalizados por fuente. La política de colaboración define lo siguiente:

* [Permisos de datos](#permisos-de-datos)
* [Permisos de acceso](#permisos-de-acceso)

<div id="data-permissions" />

## Permisos de datos

Los permisos de datos que selecciones definen cómo tu colaborador puede usar tus datos asociados y se aplican a todas las fuentes que asocies con la colaboración. Los permisos también se pueden modificar individualmente por fuente.

<Image align="center" alt="Permisos de datos Dic 2025.png" src="https://files.readme.io/1e33caebbe4a8ff14fe84be6ba7f50b82a5fe7c268ba186db0250c7084718d54-42009477892241.png" width="704px" />

<div id="data-permissions-include" />

### Los permisos de datos incluyen:

| Permiso | Nota |
| --- | --- |
| **Hacer visible al colaborador** | Permite al colaborador ver y usar las fuentes que asocies con la colaboración, de acuerdo con los demás permisos que le concedas. Si se desactiva, tus fuentes solo serán visibles para ti. |
| **Consultar datos** | Permite al colaborador consultar los datos y crear reportes agregados. Puedes especificar si el colaborador:<ul><li>**Solo puede consultar datos coincidentes** (conjunto de datos superpuestos): hace referencia a los usuarios comunes de ambas party.<br />**Nota:** Si se selecciona esta opción, el tamaño de la fuente no está disponible.</li><li>**Puede consultar todos los datos** (conjunto de datos Universal): hace referencia a todos los datos que asocies con la colaboración.</li></ul> |
| **Crear audiencias** | Permite al colaborador usar los datos al crear sus <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections">audiencias</Anchor>. Puedes especificar si el colaborador:<ul><li>**Solo puede usar datos coincidentes** (conjunto de datos superpuestos): hace referencia a los usuarios comunes de ambas party.<br />**Nota:** Si se selecciona esta opción, el tamaño de la fuente no está disponible.</li><li>**Puede usar todos los datos** (conjunto de datos Universal): hace referencia a todos los datos que asocies con la colaboración.</li></ul> |
| **Conexiones de partners** | Permite al colaborador enviar las audiencias creadas a partir de tus fuentes a conexiones de Partners para su activación. Al habilitar esta opción, puedes conceder permiso de exportación para:<ul><li>**Todos los Partners conectados** - Al seleccionar esta opción, también puedes **permitir futuras conexiones de Partners**, lo que permite automáticamente la exportación de audiencias a todos los Partners de medios con los que AppsFlyer DCP colabora.</li><li>**Solo partners específicos**<ul><li>Si seleccionas partners específicos, puedes indicar además si permites que tu colaborador use solo sus conexiones de activación o las tuyas (por ejemplo, solo su conexión de Meta o tu conexión de Meta).</li><li>Si seleccionas tus conexiones, tendrás que elegir cuáles de tus cuentas conectadas puede usar el colaborador (por ejemplo, solo tu conexión de Meta A, pero ninguna de tus otras conexiones de Meta).</li></ul></li></ul>**Notas importantes:**<ul><li>Cuando tus colaboradores estén listos para <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences#enviar-audiencia-para-activación">activar audiencias</Anchor> en función de tus fuentes, solo tendrán disponibles las conexiones de Partners para las que les hayas concedido permisos.</li><li>Si no has concedido al colaborador permiso para publicar o exportar audiencias, cuando intente activar una audiencia, la solicitud de activación se te enviará a ti para que la completes.</li></ul> |
| **Exportación de archivos** | Permite al colaborador exportar archivos de audiencias a su cloud bucket. |

<div id="access-permissions" />

## Permisos de acceso

Los permisos de acceso definen los recursos a los que puede acceder tu colaborador. Esto incluye la opción de conceder a tu colaborador acceso a tus <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections#create-data-identity-connections">conexiones de Data & Identity (data resolution)</Anchor>, lo que le permite usar estas conexiones para enriquecer sus fuentes.

**Nota:** Para conceder acceso, la conexión de Data & Identity correspondiente debe estar activa.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

Esta sección describe algunas características y limitaciones clave de los permisos de DCP.

| Característica o limitación | Nota |
| --- | --- |
| **Comportamiento de la audiencia** | <ul><li>Si una audiencia se crea a partir de una sola fuente → los permisos de partner de la fuente determinan qué partners de activación están disponibles.</li><li>Si una audiencia se crea a partir de varias fuentes con permisos de partner distintos →<br />se aplica el mínimo común denominador.<br />**Ejemplo:** La fuente A permite todos los partners; la fuente B permite solo Meta → solo Meta estará disponible para la activación.</li></ul> |
| **Cambios en los permisos** | **Eliminar por completo los permisos de activación:**<ul><li>Cualquier audiencia existente que use la fuente afectada caducará.</li><li>Las nuevas audiencias que usen la fuente se comportarán como hoy (requerirán nuevos permisos de activación).</li></ul>**Eliminar un partner específico:**<ul><li>Si una audiencia existente está conectada solo a ese partner eliminado → la audiencia caducará.</li><li>Si la audiencia está conectada a varios Partners →<br />la audiencia seguirá activa, pero la activación con el Partner eliminado dejará de estar disponible.</li></ul> |

<div data-zendesk-anchors="data-permissions=permisos-de-datos h_01KCKFQH3AVZY9V2KGZE06K3VT=permisos-de-datos data-permissions-include=los-permisos-de-datos-incluyen h_01KCKJHVQ9EGTGAJ9NP021P42Q=los-permisos-de-datos-incluyen access-permissions=permisos-de-acceso h_01KCKFQH3AFBDA50FJ0ZW9Q8J1=permisos-de-acceso traits-and-limitations=especificaciones-y-limitaciones h_01KCKFQH3AEM9WR95S2ZZ6NNNC=especificaciones-y-limitaciones" />
