---
title: Configuración de la cuenta
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
  created_at: '2026-03-15T11:09:02Z'
  edited_at: '2026-08-12T12:03:42Z'
  id: 44784756352273
  locale: es
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/es/articles/44784756352273
---
> **En resumen:** Utiliza la página de **Configuración de la cuenta** para gestionar tu perfil personal, la configuración a nivel de cuenta y las capacidades de IA desde un solo lugar.

<div id="about-account-settings" />

## **Acerca de la configuración de la cuenta**

La página de **Configuración de la cuenta** tiene tres pestañas:

* [**Perfil**](/docs/account-settings#perfil): Los detalles de tu cuenta personal
* [**Cuenta**](/docs/account-settings#cuenta): Configuraciones a nivel de cuenta
* [**Capacidades**](/docs/account-settings#capacidades-de-ia): Controles para productos impulsados por IA y acceso

<div id="profile" />

## **Perfil**

La sección de **Perfil** muestra los detalles de tu cuenta personal, como el nombre de la cuenta, correo electrónico del propietario, sitio web y el ID de la cuenta.

Utiliza esta sección para revisar la información de tu cuenta y actualizar los campos de perfil admitidos.

<div id="account" />

## **Cuenta**

La sección de **Cuenta** incluye la configuración de seguridad a nivel de cuenta. Se pueden agregar configuraciones adicionales de auto-servicio para la cuenta con el tiempo

### <Anchor target="_blank" href="/marketers/es/docs/dev-key-management">**Unique Dev Key**</Anchor>

La configuración de la **Unique Dev Key** controla si AppsFlyer crea una clave de desarrollo única para cada nueva aplicación.

Cuando se habilita la opción de **crear una Unique Dev Key por aplicación para futuras aplicaciones**, se generará automáticamente una nueva y única para cada aplicación añadida recientemente.

Nota: Esta configuración solo se aplica a las aplicaciones creadas después de que se active la opción. No cambia las Dev Keys de las aplicaciones existentes.

<div id="ai-capabilities" />

## **Capacidades de IA**

La sección de **capacidades de IA** permite a los administradores gestionar qué productos impulsados por IA están disponibles para la cuenta.

<div id="ai-assistant" />

### <Anchor target="_blank" href="/marketers/es/docs/ai-assistant">Asistente de IA</Anchor>

El Asistente de IA es tu propio analista virtual y ayudante de conocimiento de la plataforma en AppsFlyer. Utilízalo para descubrir insights, medir el rendimiento, identificar los mejores y peores desempeños, descubrir tendencias de campañas y explorar insights visuales como tablas y gráficos, directamente desde cualquier página de la plataforma.

### <Anchor target="_blank" href="/marketers/es/docs/beta-appsflyer-mcp">AppsFlyer MCP</Anchor>

El MCP de AppsFlyer conecta tus datos de AppsFlyer a cualquier modelo de lenguaje grande (LLM), como Claude o VS Code. Haz preguntas, obtén insights sobre el rendimiento y toma medidas directamente en tu chat de IA.

MCP está habilitado de forma predeterminada para todas las cuentas.

Para deshabilitar MCP, ve a **Cuenta & perfil > Capacidades de IA**.

Deshabilitando el MCP:

* Los usuarios ya no pueden acceder a los datos de AppsFlyer a través del MCP en herramientas de IA externas.
* Las conexiones existentes pueden seguir funcionando hasta que expire la sesión actual.
* No afecta las conexiones API regulares
* No afecta otras capacidades de IA en AppsFlyer

**Importante:** Si se está utilizando un token MCP, primero debes eliminarlo en **Centro de Seguridad > Tokens de AppsFlyer**.

<div id="agent-hub" />

### <Anchor target="_blank" href="/marketers/es/docs/beta-agent-hub-overview">Hub de agentes</Anchor>

El Agent Hub es la plataforma centralizada de AppsFlyer para gestionar agentes impulsados por IA que ofrecen insights de marketing procesables de forma proactiva directamente en tu flujo de trabajo. Estos agentes analizan constantemente tus datos para ofrecer resultados valiosos y recomendar pasos procesables, todo ello dentro del entorno colaborativo de tu equipo.

Esta configuración solo está disponible para administradores y está habilitada de forma predeterminada.

Deshabilitar Agent Hub:

* Los usuarios ya no tienen acceso a Agent Hub.
* Todos los agentes existentes se eliminarán de forma permanente y no podrán restaurarse.
* Todas las ejecuciones activas de agentes se detendrán.
* Si Agent Hub se vuelve a habilitar más adelante, los usuarios podrán acceder a él nuevamente, pero deberán crear agentes desde cero.

<div id="permissions" />

## **Permisos**

Lo que puedes ver o editar en la página **Configuración de la cuenta** depende de tus permisos de usuario.

En general:

* No todos los usuarios pueden ver la misma configuración
* Algunas configuraciones pueden ser solo de visualización
* Se pueden requerir permisos de administrador para cambiar controles a nivel de cuenta o relacionados con la IA

<div data-zendesk-anchors="about-account-settings=acerca-de-la-configuraci%C3%B3n-de-la-cuenta h_01KKRJZMP6CDDSJ6RK8QN4T30A=acerca-de-la-configuraci%C3%B3n-de-la-cuenta profile=perfil h_01KKRJZMP81BHTCA01W22CRQYG=perfil account=cuenta h_01KKRJZMP9PQB0BZQ0931D23AH=cuenta h_01KKRJZMPA9YTMGY0A3A883T0N=unique-dev-key ai-capabilities=capacidades-de-ia h_01KKRJZMPCAMQFZM3MKQBTYFVD=capacidades-de-ia ai-assistant=asistente-de-ia h_01KKRJZMPCQJBRRA0EM2EF4BYB=asistente-de-ia h_01KKRJZMPDZQKY9VV25EKCP5YE=appsflyer-mcp agent-hub=hub-de-agentes h_01KKRJZMPEHQHPRJEH9PSDTT00=hub-de-agentes permissions=permisos h_01KKRJZMPFQJK110AW1CDS23CW=permisos" />
