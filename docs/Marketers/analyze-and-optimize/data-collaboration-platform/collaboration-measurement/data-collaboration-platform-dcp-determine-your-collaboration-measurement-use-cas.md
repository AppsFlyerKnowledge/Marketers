---
title: >-
  Plataforma de colaboración de datos (DCP): determina tu caso de uso para medir
  la colaboración
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-02-25T15:52:06Z'
  edited_at: '2026-08-12T11:53:19Z'
  id: 32964487756561
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/32964487756561
---
> **En resumen:** identifica tu escenario de colaboración y asegúrate de saber qué datos debes proporcionar, quién es responsable de ellos y en qué formato debes enviarlos.

## Visión general

DCP da soporte a diversos casos de uso on-site y off-site. Cada caso de uso requiere una configuración distinta, en la que se especifica qué colaborador es responsable de preparar cada fuente de datos y en qué formato deben configurarse los datos.

Este artículo tiene como objetivo ayudar a las Commerce Media Networks (CMN) y a los anunciantes (marcas) a identificar qué caso de uso les aplica. Una vez determinado el caso de uso adecuado, el propietario de la colaboración puede asignar las tareas necesarias de preparación y configuración a los colaboradores correspondientes (para obtener más información sobre la asignación de tareas, consulta: <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configuration-task-assignment">Asignar configuración de tareas</Anchor>.)

Aquí es donde entra en juego el árbol de decisión de casos de uso. Sirve como guía estructurada para ayudarte a especificar tu caso de uso y recibir las instrucciones de preparación correspondientes.

## ¿Cómo ayuda el árbol de decisión?

Según la configuración, es posible que un colaborador deba preparar y configurar las tareas de conversiones y campañas, mientras que el otro puede ser responsable de preparar las tareas de engagement o de partners de medios. El árbol de decisión ayuda al propietario de la colaboración a determinar qué colaborador debe tener asignada cada tarea y proporciona enlaces a las instrucciones correspondientes.

### ¿Qué árbol de decisión necesito: on-site u off-site?

Puedes usar dos árboles de decisión: uno para campañas on-site y otro para campañas off-site. Para determinar qué árbol de decisiones es el adecuado, ten en cuenta dónde se **sirve el anuncio** y dónde se **produce la conversión**.

* Usa el [árbol de decisiones de campañas off-site](#el-árbol-de-decisión-de-la-campaña-off-site) si el anuncio se muestra en una plataforma publicitaria externa (por ejemplo, Facebook, Google) fuera de tus propiedades propias y operadas.
* Usa el [árbol de decisiones de campañas on-site](#el-árbol-de-decisión-para-campañas-on-site) si el anuncio se sirve dentro de tu ecosistema y la conversión se produce en tu plataforma.

## El árbol de decisión para campañas on-site

En el escenario de campaña on-site, la conversión se produce en una plataforma propiedad de la CMN o del anunciante y operada por ellos. Esto lleva a la pregunta inicial del árbol de decisión on-site: ¿en qué plataforma se produce la conversión, en la de la CMN o en la del anunciante?

Responde a la pregunta inicial eligiendo la respuesta correcta y sigue ampliando las ramas que correspondan a tus condiciones específicas.

#### **¿En qué plataforma se produce la conversión?**

<div id="the-conversions-take-place-on-the-cmn-platform" />

<Accordion title="Las conversiones se producen en la plataforma de la CMN">

<div id="the-cmn-platform-is-an-app" />

<Accordion title="La plataforma de la CMN es una aplicación">

Si la plataforma de la CMN es una aplicación, sigue las instrucciones que aparecen a continuación para cada tipo de datos:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de tareas de conversiones en el sitio</Anchor></li></ul> |
| Engagements | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fuente de engagement</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Evento in-app de engagement</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configuración de tareas de engagement</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de tareas de ventanas de lookback</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-cmn-platform-is-a-website" />

<Accordion title="La plataforma CMN es un sitio web">

Si la plataforma CMN es un sitio web, sigue las instrucciones que aparecen a continuación para cada tipo de datos:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de tareas de conversiones en el sitio</Anchor></li></ul> |
| Engagements | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fuente de engagement</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configuración de tareas de engagement</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de tareas de ventanas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**O**

<div id="the-conversions-take-place-on-the-advertiser-platform" />

<Accordion title="Las conversiones tienen lugar en la plataforma del anunciante">

<div id="the-advertiser-platform-is-an-app" />

<Accordion title="La plataforma del anunciante es una aplicación">

Si la plataforma del anunciante es una aplicación, sigue las instrucciones que aparecen abajo para cada tipo de datos:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de tareas de conversiones on-site</Anchor></li></ul> |
| Engagements | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fuente de engagement</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Evento in-app de engagement</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configuración de tareas de engagements</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de tareas de ventanas de lookback</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-advertiser-platform-is-a-website" />

<Accordion title="La plataforma del anunciante es un sitio web">

Si la plataforma del anunciante es un sitio web, sigue las instrucciones que aparecen abajo para cada tipo de datos:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de tareas de conversiones on-site</Anchor></li></ul> |
| Engagements | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Fuente de engagement</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-engagements-task">Configuración de la tarea de engagement</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de la tarea de ventanas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

## El árbol de decisión de la campaña off-site

En el escenario de campaña off-site, el anuncio se muestra en una plataforma publicitaria externa, como Facebook o Google. Esto lleva a la pregunta inicial en el árbol de decisión off-site: ¿qué cuenta en la plataforma publicitaria externa se utiliza para mostrar el anuncio: la del CMN o la del anunciante?

Responde a la pregunta inicial eligiendo la respuesta correcta y sigue ampliando las ramas que correspondan a tus condiciones específicas.

#### **¿Qué cuenta de la plataforma externa muestra el anuncio?**

<div id="the-cmn-external-platform-account" />

<Accordion title="La cuenta de la plataforma externa de CMN muestra el anuncio">

<div id="the-conversions-take-place-on-the-cmn-platform::e7b94fc0" />

<Accordion title="Las conversiones se producen en la plataforma CMN">

<div id="the-cmn-platform-is-an-app::76ead17" />

<Accordion title="La plataforma CMN es una aplicación">

Si la plataforma CMN es una aplicación, sigue las instrucciones que se indican a continuación para cada tarea:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones on-site</Anchor></li></ul> |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de la tarea de campañas</Anchor></li></ul> |
| Socios de medios | CMN | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de la tarea de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No es relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de ventanas de lookback</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-cmn-platform-is-a-website::5144f168" />

<Accordion title="La plataforma CMN es un sitio web">

Si la plataforma CMN es un sitio web, sigue las instrucciones que aparecen abajo para cada tarea:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones en el sitio</Anchor></li></ul> |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de la tarea de campañas</Anchor></li></ul> |
| Socios de medios | CMN | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de la tarea de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de ventanas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**O**

<div id="the-conversions-take-place-on-the-advertiser-platform::aa9e89bf" />

<Accordion title="Las conversiones se producen en la plataforma del anunciante">

<div id="the-advertiser-platform-is-an-app::d36436f5" />

<Accordion title="La plataforma del anunciante es una aplicación">

Si la plataforma del anunciante es una aplicación, sigue las instrucciones que aparecen abajo para cada tarea:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones en el sitio</Anchor></li></ul> |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Socios de medios | CMN | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de tareas de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de ventanas de atribución retrospectiva</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-advertiser-platform-is-a-website::b70163fb" />

<Accordion title="La plataforma del anunciante es un sitio web">

Si la plataforma del anunciante es un sitio web, sigue las instrucciones que aparecen a continuación para cada tarea:

| Tarea | Preparado y configurado por | Cómo preparar | Cómo configurar |
| --- | --- | --- | --- |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de tareas de conversiones en el sitio</Anchor></li></ul> |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Socios de medios | CMN | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de tareas de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de ventanas de atribución retrospectiva</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

**O**

<div id="the-advertisers-external-platform-account" />

<Accordion title="La cuenta del Anunciante en la plataforma externa muestra el anuncio">

<div id="the-conversions-take-place-on-the-cmn-platform::7b0781d3" />

<Accordion title="Las conversiones se producen en la plataforma CMN">

<div id="the-cmn-platform-is-an-app::413a6003" />

<Accordion title="La plataforma CMN es una aplicación">

Si la plataforma CMN es una aplicación, sigue las instrucciones que aparecen a continuación para cada tarea:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones en el sitio</Anchor></li></ul> |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de la tarea de campañas</Anchor></li></ul> |
| Socios de medios | AppsFlyer | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de la tarea de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN/Anunciante | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de las ventanas de lookback</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-cmn-platform-is-a-website::95667666" />

<Accordion title="La plataforma CMN es un sitio web">

Si la plataforma CMN es un sitio web, sigue las instrucciones que aparecen a continuación para cada tarea:

| Tarea | Preparado y configurado por | Aprende a preparar | Aprende a configurar |
| --- | --- | --- | --- |
| Conversiones | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones en el sitio</Anchor></li></ul> |
| Campañas | CMN | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de la tarea de campañas</Anchor></li></ul> |
| Socios de medios | AppsFlyer | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de la tarea de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN | No es relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de las ventanas de lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

**O**

<div id="the-conversions-take-place-on-the-advertiser-platform::51470bc6" />

<Accordion title="Las conversiones tienen lugar en la plataforma del anunciante">

<div id="h_01K3BAV1SP7RWP7K9TM7Y6MJVX" />

<Accordion title="La plataforma del anunciante es una app">

Si la plataforma del anunciante es una app, sigue las instrucciones que aparecen a continuación para cada tarea:

| Tarea | Preparado y configurado por | Aprende cómo prepararte | Aprende cómo configurar |
| --- | --- | --- | --- |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Evento in-app de conversión</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones on-site</Anchor></li></ul> |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de la tarea de campañas</Anchor></li></ul> |
| Socios de medios | AppsFlyer | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de la tarea de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN | No es relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de las ventanas de lookback</Anchor></li></ul> |

</Accordion>

**O**

<div id="the-advertiser-platform-is-a-website::8cb255ef" />

<Accordion title="La plataforma del anunciante es un sitio web">

Si la plataforma del anunciante es un sitio web, sigue las instrucciones que aparecen a continuación para cada tarea:

| Tarea | Preparado y configurado por | Aprende cómo prepararte | Aprende cómo configurar |
| --- | --- | --- | --- |
| Conversiones | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Fuente de conversión (personalizada)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-conversions-task#configurar-las-conversiones-de-campañas-on-site">Configuración de la tarea de conversiones on-site</Anchor></li></ul> |
| Campañas | AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#preparar-la-fuente-de-mapeo-de-la-campaña">Fuente de mapeo de campaña</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-campaigns-task">Configuración de tareas de campañas</Anchor></li></ul> |
| Socios de medios | AppsFlyer | No relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-media-partners-task">Configuración de tareas de partners de medios</Anchor></li></ul> |
| Ventanas de lookback | CMN | No es relevante | <ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-the-lookback-windows-task">Configuración de ventanas de atribución retrospectiva</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01JSKXR18RP691PT3Y5JGAJKF8=visi%C3%B3n-general how-does-the-decision-tree-help=c%C3%B3mo-ayuda-el-%C3%A1rbol-de-decisi%C3%B3n h_01K3JR6NJ906S2HZC7YRWWFT2P=c%C3%B3mo-ayuda-el-%C3%A1rbol-de-decisi%C3%B3n which-decision-tree-do-i-need-onsite-or-offsite=qu%C3%A9-%C3%A1rbol-de-decisi%C3%B3n-necesito-on-site-u-off-site h_01K3JR7AZFWJMTBZGAKYS4BFJS=qu%C3%A9-%C3%A1rbol-de-decisi%C3%B3n-necesito-on-site-u-off-site the-onsite-use-case-decision-tree=el-%C3%A1rbol-de-decisi%C3%B3n-para-campa%C3%B1as-on-site h_01JSKXR18R4A4WFPTQVB1DVV5Y=el-%C3%A1rbol-de-decisi%C3%B3n-para-campa%C3%B1as-on-site on-which-platform-does-the-conversion-take-place=en-qu%C3%A9-plataforma-se-produce-la-conversi%C3%B3n h_01JSM17ZMGCF1FWQPM7T04C0MM=en-qu%C3%A9-plataforma-se-produce-la-conversi%C3%B3n h_01JSKXR18RTDSJ6W40D5JVFSS5=the-conversions-take-place-on-the-cmn-platform h_01JSKXR18R9A9MCZ7TPJHXWMBC=the-cmn-platform-is-an-app h_01JSKXR18RWSJTR5AKDBRGP0QS=the-cmn-platform-is-a-website h_01JSKXR18R083C5FY5FTESJDAZ=the-conversions-take-place-on-the-advertiser-platform h_01JSKXR18RH3SCQJRJA7QBVS6Y=the-advertiser-platform-is-an-app h_01JSKXR18R3N816VYJ4910VYGA=the-advertiser-platform-is-a-website the-offsite-use-case-decision-tree=el-%C3%A1rbol-de-decisi%C3%B3n-de-la-campa%C3%B1a-off-site h_01JSKXR18R38YJZ2S410J4EH43=el-%C3%A1rbol-de-decisi%C3%B3n-de-la-campa%C3%B1a-off-site which-account-on-the-external-platform-displays-the-ad=qu%C3%A9-cuenta-de-la-plataforma-externa-muestra-el-anuncio h_01JSM18A2R9015RWB05BE0YK7Q=qu%C3%A9-cuenta-de-la-plataforma-externa-muestra-el-anuncio h_01JSKXR18R4EKMWCYKFTBAEPH9=the-cmn-external-platform-account h_01JSKXR18RCKD3E841EQ2RC03B=the-conversions-take-place-on-the-cmn-platform::e7b94fc0 h_01JSKXR18R5115TP1BYE07TJ7V=the-cmn-platform-is-an-app::76ead17 h_01JSKXR18RCBGH6F8SNSRN2CJG=the-cmn-platform-is-a-website::5144f168 h_01JSKXR18RGQX77NM72G4WAC08=the-conversions-take-place-on-the-advertiser-platform::aa9e89bf h_01JSKXR18R61CTQ0VMRKD184VE=the-advertiser-platform-is-an-app::d36436f5 h_01JSKXR18RSQC7MCYZ5JE2VP3B=the-advertiser-platform-is-a-website::b70163fb h_01JSKXR18SYFX87XBSBNPJXAFA=the-advertisers-external-platform-account h_01JSKXR18S6TQMNW6PD65G67AQ=the-conversions-take-place-on-the-cmn-platform::7b0781d3 h_01JSKXR18SCDQXAN5NFQ1W17K2=the-cmn-platform-is-an-app::413a6003 h_01JSKXR18SDCDQX4SJ24ADZA18=the-cmn-platform-is-a-website::95667666 h_01JSKXR18S123PXD3FN2N11GCN=the-conversions-take-place-on-the-advertiser-platform::51470bc6 h_01JSKXR18STJV3GGW83123W7XC=the-advertiser-platform-is-a-website::8cb255ef" />
