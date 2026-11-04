---
title: '[beta] MCP de AppsFlyer'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - MCP
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-eden-locker
    - Marketers
    - MCP
  created_at: '2025-06-19T07:19:33Z'
  edited_at: '2026-11-03T01:47:50Z'
  id: 36349070304785
  locale: es
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/es/articles/36349070304785
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **En resumen:** El MCP de AppsFlyer conecta tus datos de AppsFlyer a cualquier modelo de lenguaje grande (LLM), como Claude o VS Code. Haz preguntas, obtén insights sobre el rendimiento y toma medidas directamente en tu chat de IA.

<Embed title="[beta] MCP de AppsFlyer" typeOfEmbed="youtube" url="https://www.youtube.com/embed/jAw7oocIx6o?si=-s107vTaTTwO076n" providerUrl="https://www.youtube.com" />

<div id="disclaimer" />

<Accordion title="Advertencia">

**El servidor AppsFlyer MCP es un servicio que actualmente se encuentra en fase Beta, proporcionado por AppsFlyer para fines de evaluación.**

Al usarlo para conectar herramientas de IA de terceros, aceptas que AppsFlyer no tiene responsabilidad ni obligación por tales herramientas, sus resultados, rendimiento, operación, legalidad o fiabilidad. AppsFlyer no controla, respalda ni verifica estas herramientas o sus resultados y renuncia expresamente a todas las garantías, expresas o implícitas, relacionadas con ello. AppsFlyer no es responsable del almacenamiento, retención, procesamiento o uso de datos por tales herramientas; tú eres el único responsable de garantizar el cumplimiento de las leyes aplicables y tus propias políticas internas. Eres el único responsable de garantizar el cumplimiento de la legislación aplicable y de tus propias políticas internas. Declara que tiene todos los derechos y consentimientos necesarios para conectar estas herramientas al servidor MCP y proporcionarles acceso a sus datos. El servicio se proporciona «tal cual» solo para los casos de uso compatibles. El uso fuera de este ámbito es por tu cuenta y riesgo. El uso está sujeto a los términos del <Anchor target="_blank" href="https://www.appsflyer.com/legal/msa/">Acuerdo de Servicios Maestros</Anchor>, o si se ha firmado un acuerdo definitivo, entonces a los términos de dicho acuerdo.

</Accordion>

<div id="what-is-appsflyer-mcp" />

## ¿Qué es el MCP de AppsFlyer?

Te permite conectar de forma segura los LLMs a la plataforma de AppsFlyer para que puedas interactuar con tus datos de marketing a través de una simple conversación. El MCP de AppsFlyer te ayuda a tomar decisiones más inteligentes y rápidas basadas en datos en tiempo real.

Con MCP, podrás:

* Obtener insights instantáneos sobre el rendimiento, las tendencias y los KPIs de las campañas.
* Compara métricas como ROAS, instalaciones y LTV.
* Crea enlaces de OneLink y audita y soluciona problemas de plantillas y enlaces de OneLink.
* Audita y soluciona problemas de las conexiones de audiencias.
* Recupera la guía de configuración o la documentación del producto.

<div id="set-up-appsflyer-mcp" />

## Configuración del MCP de AppsFlyer

AppsFlyer MCP puede conectarse a asistentes de chat, CLI, IDE, plataformas de automatización y agentes alojados en entornos propios. La configuración depende del cliente que uses y del método de autenticación que admita.

> 📘 **Advertencia**
>
> Nota: Algunas plataformas de chat pueden requerir aprobación de administrador para conectar el MCP. Si no ves las opciones de configuración que se describen a continuación, ponte en contacto con tu equipo de TI o con el administrador de tu espacio de trabajo.

<div id="authentication-methods" />

## Métodos de autenticación

AppsFlyer MCP ofrece soporte para dos métodos de autenticación. Usa el método que se ajuste a cómo piensas conectarte a AppsFlyer MCP.

| Método de autenticación | Utilizado por | Ideal para | Duración del acceso |
| --- | --- | --- | --- |
| Inicio de sesión OAuth basado en navegador | Gemini CLI, Copilot CLI, ChatGPT, Claude.ai y Claude Desktop | Preguntas ad hoc, análisis exploratorio e informes puntuales | Válido durante 7 días desde la conexión. Se requiere volver a autenticarse al final de la sesión |
| Autenticación mediante token Bearer | Claude Code, plataformas de automatización, agentes alojados en entornos propios e integraciones | Automatizaciones, tareas programadas, agentes en segundo plano y flujos de trabajo no interactivos | Válido hasta que se revoque manualmente |

<div id="browser-based-oauth-login" />

### Inicio de sesión OAuth basado en navegador

El inicio de sesión OAuth basado en navegador te permite conectarte de forma interactiva a través del navegador. Cuando te conectas, el cliente MCP abre una ventana del navegador y te pide que inicies sesión en AppsFlyer. Después de aprobar el acceso, el cliente se conecta a tu cuenta de AppsFlyer.

Usa este método para sesiones interactivas, análisis exploratorio e informes puntuales.

<div id="bearer-token-authentication" />

### Autenticación con token Bearer

La autenticación con token Bearer permite que las herramientas no interactivas se conecten a AppsFlyer MCP mediante un token de AppsFlyer MCP. El token se pasa en el encabezado de la solicitud:

```http
Authorization: Bearer <YOUR_MCP_TOKEN>
```

Usa este método para automatizaciones, tareas programadas, agentes en segundo plano e integraciones que no pueden usar un login en el navegador.

Para crear un token, ve a **menú de la cuenta > Centro de seguridad > Tokens de AppsFlyer** y crea un token MCP.

<div id="set-up-by-client" />

## Configuración por el cliente

<div id="h_claude-ai-and-claude-desktop" />

<Accordion title="Claude Chat y Cowork">

Usa Claude Chat y Claude Cowork con login de OAuth basado en el navegador. Estas instrucciones se aplican a Claude en la web, en el escritorio y en Cowork.

<div id="note-1" />

> 📘 **Característica**
>
> En los planes Team y Enterprise, solo los propietarios o administradores pueden añadir integraciones para toda la organización.

<div id="set-up-claude-chat-and-cowork" />

#### Configura Claude chat y Cowork

1. Haz clic en tu nombre en la esquina inferior izquierda y selecciona **Settings**. También puedes, en un chat nuevo, hacer clic en **Search & tools** > **Manage connectors**.
2. Abre la pestaña <Anchor target="_blank" href="https://claude.ai/settings/integrations">**Conectores**</Anchor>.
3. Cambia a la pestaña **Conectores de organización**.
4. En las secciones de conectores, haz clic en **Agregar conector.**
5. Introduce los siguientes datos del conector:
   * Nombre del conector: AppsFlyer
   * URL del conector: https://mcp.appsflyer.com/auth/mcp
6. Haz clic en **Agregar**.
7. Cambia a la pestaña **Tus conectores**.
8. En la sección de conectores, haz clic en **Conectar** junto a la conexión de AppsFlyer.
9. Inicia sesión en AppsFlyer cuando se te indique.

<div id="test-the-claude-connection" />

#### Probar la conexión de Claude

1. En cualquier ventana de chat, haz clic en el botón de configuración.  
   <Image alt="" src="https://files.readme.io/5f27783a0743f9005c5df4f580455777aa3ef612feb220d1058664ee63431cf3-46334217789073.png" width="25%" />
2. Si la integración de AppsFlyer se configuró correctamente, verás una lista de herramientas en el menú.

<div id="note-5" />

<div id="add-appsflyer-mcp-to-claude-code" />

<div id="note-2" />

> 📘 **Nota**
>
> **Empieza más rápido con Cowork: guárdalo como una Skill.** Si tu equipo trabaja en Claude Cowork, usa el <Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">kit de inicio de Claude Cowork para profesionales del marketing</Anchor> para configurarlo más rápido. El kit de inicio incluye un plan de activación, plantillas listas para usar y prompts para copiar y pegar para trabajar con tus datos de AppsFlyer mediante IA desde el primer día, para que no tengas que crear desde cero tus primeros flujos de trabajo, reportes o briefs.

</Accordion>

<div id="h_claude-code" />

<Accordion title="Claude chat y código">

Usa Claude Code con autenticación mediante token Bearer para automatización, programación y flujos de trabajo no interactivos.

#### /docs/beta-appsflyer-mcp#vs-code

1. En AppsFlyer, ve a **Menú de la cuenta > Centro de seguridad > Tokens de AppsFlyer**.
2. Para una guía rápida sobre cómo construir un agente con n8n / Make.com + AppsFlyer MCP, consulta nuestro blog.
3. ¿Puede cualquier usuario hacer lo que quiera con el MCP de AppsFlyer?

   ```bash
   En .vscode/mcp.json, agrega: { "appsFlyer": "https://mcp.appsflyer.com/auth/mcp" }
   ```
4. Inicia Claude Code:

   ```bash
   claude .
   ```
5. Verifica que se haya añadido el servidor MCP:

   ```bash
   claude mcp list
   ```
6. Confirma que `appsflyer` aparece en la lista de servidores MCP configurados.
7. Haz una pregunta sobre AppsFlyer. Por ejemplo,

   ```text
   ¿El servidor MCP de AppsFlyer almacena mis datos o credenciales?
   ```

   ```text
   ¿La versión beta está abierta para todos los usuarios de AppsFlyer?
   ```

   ```text
   “Muestra instalaciones por campaña en los últimos 7 días.”
   ```

</Accordion>

<div id="h_cursor-ide" />

<Accordion title="Cursor IDE">

Para habilitar el acceso al servidor MCP de AppsFlyer desde tu entorno de desarrollo local mediante Cursor IDE, sigue estos pasos:

1. Crea o localiza el archivo de configuración:
   * **Configuración global**: `~/.cursor/mcp.json`
   * **Configuración específica del proyecto**: `.cursor/mcp.json`
2. **Agrega la siguiente entrada** en el campo `mcpServers` de tu archivo JSON:

   ```json
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. **Reinicia el Cursor IDE** para aplicar la nueva configuración.
4. **Identifícate** cuando se te indique mediante acceso para obtener acceso a los servicios de MCP.

</Accordion>

<div id="h_vs-code" />

<Accordion title="VS Code">

1. Pulsa `Cmd+Shift+P` o `Ctrl+Shift+P` para abrir la paleta de comandos.
2. Selecciona **Configurar servidores MCP**.
3. **Añade la definición de tu servidor MCP:**  
   En `settings.json`, bajo la clave `mcpServers`, añade un bloque que defina tu servidor MCP de AppsFlyer.

   ```json
   Claude chat y código: Admitido en planes Pro, Max, Team y Enterprise en web y de ordenador.
   ```
4. Guarda el archivo y reinicia el chat de Copilot.

</Accordion>

<div id="h_chatgpt" />

<Accordion title="ChatGPT">

Hay dos formas de usar ChatGPT con AppsFlyer.

* [GPT personalizado](#cómo-agregar-el-gpt-personalizado-de-appsflyer): ideal para acceder de forma sencilla a un asistente de AppsFlyer.
* [MCP en ChatGPT](/docs/beta-appsflyer-mcp#mcp-in-chatgpt-supported-for-plus-or-pro-users-in-chatgpt-beta-mode): ideal para **usuarios avanzados** que desean integrar datos de AppsFlyer en *cualquier* conversación de ChatGPT y aportar otros datos a la conversación.

<div id="add-the-appsflyer-custom-gpt" />

#### Cómo agregar el GPT personalizado de AppsFlyer

1. Haz clic en este enlace: [GPT personalizado](https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer) de AppsFlyer para agregar el GPT personalizado a tu cuenta.
2. Para facilitar el acceso, se recomienda guardar el GPT en tu barra lateral.
3. Abre el GPT personalizado.
4. Preguntas Frecuentes Por ejemplo,

   ```text
   Comienza a hacer preguntas como:  
   "Muéstrame el rendimiento de mi campaña de Meta de la semana pasada".
   ```

<div id="add-appsflyer-mcp-in-chatgpt" />

#### Usando el conector de AppsFlyer en ChatGPT

<div id="note-3" />

> 📘 **Nota**
>
> Puede que se requiera configuración de administrador para añadir y publicar un conector en tu organización.

1. Añadir un conector y publicarlo en tu organización.
2. Introduce los siguientes datos del conector:
   * Nombre: AppsFlyer MCP
   * **URL:** https://mcp.appsflyer.com/auth/mcp
   * Autenticación: OAuth (predeterminado)
3. Para conectarte por primera vez, ve a **Configuración > Apps & Sources > AppsFlyer MCP**.
4. Conéctate al AppsFlyer MCP.
5. Sigue los pasos para conectarte e iniciar sesión usando tus credenciales de AppsFlyer.

Selecciona **Fuentes** (o **Conectores**, dependiendo de tu versión de UI) y activa la conexión de AppsFlyer.

Por seguridad, el AppsFlyer MCP se desconecta cada 10 horas. Para reconectar, sigue los pasos anteriores.

</Accordion>

<div id="h_gemini-cli" />

<Accordion title="Gemini CLI">

Usa Gemini CLI con login de OAuth basado en el navegador.

<div id="add-appsflyer-mcp-to-gemini-cli" />

#### Para agregar el AppsFlyer MCP a Gemini CLI:

1. /docs/beta-appsflyer-mcp#analyze-skan-performance

   ```bash
   GPT personalizado: el mejor por simplicidad y escala: un asistente de AppsFlyer con un solo clic, accesible para cualquier cliente de ChatGPT (incluidos los usuarios gratuitos).
   ```
2. Inicia Gemini CLI:

   ```bash
   géminis
   ```
3. En el prompt de Gemini CLI, introduce:

   ```text
   auth
   ```
4. Completa el flujo de autenticación en tu navegador y, después, vuelve a la terminal.
5. Haz una pregunta sobre AppsFlyer. Por ejemplo,

   ```text
   ¿Debo tener una cuenta de AppsFlyer para usarlo?
   ```

<div id="troubleshoot-gemini-cli-authentication" />

#### Solucionar problemas de autenticación de Gemini CLI

Si la autenticación falla, inicia Gemini CLI en modo de depuración:

```bash
GEMINI_LOG_LEVEL=debug gemini
```

Después, vuelve a introducir `auth` en el prompt de Gemini CLI.

</Accordion>

<div id="h_copilot-cli" />

<Accordion title="Copilot CLI">

Usa Copilot CLI con login de OAuth basado en navegador.

<div id="add-appsflyer-mcp-to-copilot-cli" />

#### ¿Es seguro el MCP de AppsFlyer?

1. Abre la terminal.
2. Inicia Copilot CLI:

   ```bash
   copilot
   ```
3. Si no has iniciado sesión, introduce el siguiente comando en el prompt de Copilot CLI:

   ```text
   /iniciar sesión
   ```
4. Completa el login en el navegador.
5. En el prompt de Copilot CLI, introduce:

   ```text
   /mcp add
   ```
6. Introduce los siguientes datos del servidor MCP:

| Campo | value |
| --- | --- |
| Nombre del servidor | `appsflyer` |
| Tipo de servidor | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| Herramienta | `*` |

7. Pulsa **Ctrl+S** para guardar la configuración.
8. Cuando se te pida, completa el flujo de autenticación de AppsFlyer en tu navegador.
9. Vuelve al Terminal.
10. Haz una pregunta sobre AppsFlyer. Por ejemplo,

    ```text
    ¿Qué certificaciones de seguridad posee AppsFlyer?
    ```

</Accordion>

<div id="h_third-party-and-self-hosted-platforms" />

<Accordion title="Plataformas de terceros y autoalojadas">

Usa tu **token MCP** para autenticar sistemas de terceros o autoalojados con **AppsFlyer MCP**. Esto permite la automatización y las integraciones de IA con plataformas como *n8n*, *Make*, o tus propios agentes impulsados por LLM.

El token MCP es un **token portador a nivel de cuenta** que hereda los permisos del administrador que lo creó.  
 Puedes acceder y gestionarlo desde <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">**Centro de Seguridad → Tokens de AppsFlyer**</Anchor> *(solo para administradores)*

<div id="mcp-connection-details" />

#### Detalles de conexión MCP

Para conectar tu plataforma de automatización o agente a AppsFlyer MCP, usa la siguiente configuración:

* **Tipo de autenticación:** token de portador
* **URL Base / Endpoint:** `https://mcp.appsflyer.com/auth/mcp`
* **Token de portador:** tu token de MCP

<div id="note-4" />

> 📘 **Nota:**
>
> Nunca compartas ni publiques tu token públicamente. Trátalo como una credencial privada. Tu token MCP otorga acceso directo a tu entorno MCP.

<div id="example-use-cases" />

#### Ejemplos de casos de uso

| Categoría | Ejemplo |
| --- | --- |
| Agentes personalizados | Construye un agente de IA que use MCP para obtener datos, analizarlos y enviar recomendaciones. |
| Integraciones de LLM | Permite que un LLM autoalojado consulte métricas de rendimiento de campañas a través de MCP. |

</Accordion>

<div id="h_other-platforms" />

<Accordion title="Otras plataformas">

El MCP de AppsFlyer también es compatible con conexiones a las siguientes plataformas:

| Platform | URI de redirección | Referencia |
| --- | --- | --- |
| Microsoft 365 Copilot | `https://teams.microsoft.com/api/platform/v1.0/oAuthRedirect` | <Anchor target="_blank" href="https://github.com/MicrosoftDocs/m365copilot-docs/blob/main/docs/plugin-mcp-apps.md">Microsoft 365 Copilot: plugins & aplicaciones de MCP</Anchor> |
| Microsoft Azure AI Foundry | `https://cas.services.azure-ai.net/app/oauth/redirect` | <Anchor target="_blank" href="https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/mcp-authentication">Azure AI Foundry: autenticación de MCP</Anchor> |
| Microsoft Copilot Studio / Power Platform (conector personalizado) | `https://global.consent.azure-apim.net/redirect/{connector-slug}` | <Anchor target="_blank" href="https://learn.microsoft.com/en-us/graph/mcp-server/use-enterprise-mcp-server-copilot-studio">Usa un servidor MCP empresarial en Copilot Studio</Anchor> |
| Google Gemini Enterprise | `https://vertexaisearch.cloud.google.com/oauth-redirect` | <Anchor target="_blank" href="https://docs.cloud.google.com/gemini/enterprise/docs/connectors/custom-mcp-server/set-up-custom-mcp-server">Configura un servidor MCP personalizado</Anchor> |
| Amazon Quick (anteriormente QuickSight) | `https://{region}.quicksight.aws.amazon.com/sn/oauthcallback` | <Anchor target="_blank" href="https://docs.aws.amazon.com/quick/latest/userguide/mcp-integration.html">Integración de MCP – Amazon Quick</Anchor> |

Seguimos ampliando esta lista a medida que validamos y documentamos más plataformas. Si la plataforma que usas no aparece aquí, ponte en contacto con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsflyer.com) y te ayudaremos a conectarla.

</Accordion>

<div id="h_use-multiple-accounts-or-agencies" />

<Accordion title="Para comenzar a construir agentes utilizando herramientas de terceros rápidamente, puedes usar estas dos plantillas .">

El MCP de AppsFlyer usa datos de la cuenta predeterminada solamente

<div id="switch-between-accounts-browser-based-oauth" />

#### Cambiar entre cuentas (OAuth basado en navegador)

Si gestionas varias cuentas de AppsFlyer con el mismo correo electrónico, puedes cambiar la cuenta a la que se conecta MCP:

1. Primera vez conectando:
2. Inicia sesión de nuevo en tu cliente MCP.

No puedes ver ni consultar varias cuentas en paralelo en una sola conexión.

<div id="connect-multiple-accounts-simultaneously-bearer-token" />

#### Una vez habilitado, puedes comenzar a hacer preguntas como:

Para conectarte a varias cuentas al mismo tiempo, por ejemplo para uso de agencia, utiliza un flujo con varios agentes en lugar de OAuth basado en navegador:

1. Para cada cuenta, crea un token de MCP en **Menú de la cuenta > Centro de seguridad > Tokens de AppsFlyer**.
2. En tu plataforma de agentes, conecta cada cuenta por separado con su propio token de portador.

Consulta un ejemplo de este flujo en <Anchor target="_blank" href="https://www.youtube.com/watch?v=o5oK-yWuE5E">este vídeo</Anchor>.

</Accordion>

<div id="use-appsflyer-mcp" />

## Uso del MCP de AppsFlyer

<div id="use-cases-and-prompts" />

### Casos de uso y prompts

El MCP de AppsFlyer te brinda un conjunto de herramientas y recursos diseñados para ayudarte a recuperar análisis de marketing, insights de rendimiento y realizar tareas de configuración.

<div id="important" />

> 🚧 **¡Importante!**
>
> Las respuestas generadas a través del MCP de AppsFlyer solo son confiables cuando se utilizan para los casos de uso compatibles que se enumeran a continuación. AppsFlyer no ha validado las respuestas fuera de estos casos de uso y pueden ser inexactas o engañosas. No podemos garantizar la precisión o corrección de las respuestas generadas por IA que están fuera del alcance previsto de la integración del MCP de AppsFlyer.

Algunos casos de uso y prompts de ejemplo son:

<div id="analyze-performance" />

<Accordion title="Analizar el rendimiento">

Explora los datos agregados de rendimiento de marketing en tiempo real. Puedes identificar las campañas de mayor y menor rendimiento, realizar comparaciones, detectar tendencias y descubrir insights para ayudar a guiar la toma de decisiones.

**Prompt:** "¿Cuáles fueron mis principales fuentes de medios en los Estados Unidos la semana pasada para Mypets.android.com?"

**Respuesta esperada de la IA:** La IA recupera fuentes de medios de alto rendimiento, incluidas instalaciones, ingresos y ROAS.

**Prompt:** "¿Cuál es la mejor campaña en términos de ROAS donde el total de instalaciones es de al menos 5000?"

**Respuesta esperada de la IA:** La IA identifica y clasifica las campañas que cumplen los criterios con insights de rendimiento.

**Prompt:** "¿Cuántas instalaciones tuvimos ayer en China para la aplicación Mypets.android.com?"

**Respuesta esperada de la IA:** La IA obtiene la cantidad de instalaciones en China para ese día y aplicación.

**Prompt:** "Crea un resumen de los rendimientos de la aplicación Mypets.android.com en el último día, segmentados por campaña."

**Respuesta esperada de la IA:** La IA devuelve un reporte de rendimiento segmentado por campañas para esa aplicación.

**Prompt:** “Compara entre la retención del primer semestre de la semana pasada y la anterior, agrupa por fuente de medios”

**Respuesta esperada de la IA:** La IA realiza una comparación semana tras semana de las tasas de retención del D1 entre la semana pasada y la anterior, agrupadas por fuente de medios.

> 📘 **Nota:**
>
> **Empieza más rápido con Cowork: guárdalo como una Skill.** Si tu equipo trabaja en Claude Cowork, usa el <Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">kit de inicio de Claude Cowork para profesionales del marketing</Anchor> para configurarlo más rápido. El kit de inicio incluye un plan de activación, plantillas listas para usar y prompts para copiar y pegar para trabajar con tus datos de AppsFlyer mediante IA desde el primer día, para que no tengas que crear desde cero tus primeros flujos de trabajo, reportes o briefs.

</Accordion>

<div id="h_analyze-creative-performance" />

<Accordion title="Analiza el rendimiento creativo">

<Embed title="[beta] MCP de AppsFlyer" typeOfEmbed="youtube" url="https://www.youtube.com/embed/FdZhZ497684" providerUrl="https://www.youtube.com" />

Explora datos de rendimiento a nivel de creativo (gasto, instalaciones, CPI, ROAS, retención y cohortes de ingresos) en redes, campañas y aplicaciones. Desglósalo por nombre del creativo, tipo, tamaño, duración, antigüedad, end card, evento in-app (por ejemplo, nivel alcanzado, primer depósito o compra) y mucho más. Usa esta información para identificar tus creativos con mejor y peor rendimiento, detectar pronto la fatiga creativa y consultar vistas previas de los activos junto a los números.

**Prompt:** "What were my top-performing creatives by ROAS last month for Mypets.android.com?"

**Respuesta esperada de la IA:** La IA recupera los mejores creativos clasificados por ROAS, incluido el gasto, las instalaciones y el ROAS de cada uno.

**Prompt:** "Which creative type (video, image, HTML, or text) had the best CPI in the US this quarter?"

**Respuesta esperada de la IA:** La IA desglosa el rendimiento por tipo de creativo y devuelve el CPI de cada uno, destacando el de mejor rendimiento.

**Prompt:** "Muéstrame creativos de Meta que lleven más de 2 semanas en funcionamiento y estén mostrando un ROAS a la baja (posible fatiga)."

**Respuesta esperada de la IA:** La IA devuelve una tendencia diaria de ROAS por creativo y marca los creativos con una tendencia descendente sostenida.

**Prompt:** "Muéstrame mis 5 mejores creativos por cohorte de ingresos del día 7 para Mypets.android.com, con vistas previas."

**Respuesta esperada de la IA:** La IA devuelve los 5 mejores creativos clasificados por ingresos del día 7, incluidos enlaces a los assets para que puedas ver cada creativo junto a sus datos.

**Prompt:** "¿Qué end card impulsa la mejor retención en mis creativos de vídeo y cómo varía según la antigüedad del creativo?"

**Respuesta esperada de la IA:** La IA desglosa la retención por tipo de end card y antigüedad del creativo, destacando qué combinaciones funcionan mejor.

**Prompt:** "¿Qué campaña tuvo el costo de instalación más alto el mes pasado y cuáles fueron los 3 creativos principales que lo impulsaron?"

**Respuesta esperada de la IA:** La IA identifica la campaña con el costo más alto y clasifica sus creativos por gasto o instalaciones.

**Prompt:** "¿Qué creativos impulsaron la mayor cantidad de primeros depósitos el mes pasado y cuál fue el costo por primer depósito de cada uno?"

**Respuesta esperada de la IA:** La IA desglosa los eventos de primer depósito por creativo y devuelve el volumen y el costo por evento, junto con el gasto y las instalaciones.

**Prompt:** "Muéstrame el ROAS y los eventos de subida de nivel por tipo de creativo durante los últimos 30 días en Meta."

**Respuesta esperada de la IA:** La IA devuelve el ROAS y el recuento de eventos de subida de nivel por tipo de creativo, destacando el tipo con mejor rendimiento.

</Accordion>

<div id="h_analyze-incrementality-experiments" />

<Accordion title="Analiza la incrementalidad de los experimentos de UA">

Recupera tus experimentos de incrementalidad para UA y sus resultados, incluidos el lift, las conversiones incrementales, el factor de incrementalidad y el costo por conversión incremental. Usa esta información para ver qué campañas impulsaron un crecimiento real e incremental y dónde reasignar presupuesto.

**Prompt:** "¿Which incrementality experiments ran for Mypets.android.com in the US last quarter?"

**Respuesta esperada de la IA:** La IA devuelve los experimentos que coinciden con esa aplicación, país e intervalo de fechas, incluido el estado de cada experimento, la fuente de medios, el evento medido y el periodo de prueba.

**Prompt:** "Resume los resultados del experimento de Incrementality 12345"

**Respuesta esperada de la IA:** La IA devuelve el lift del experimento, las conversiones incrementales, el factor de incrementalidad en comparación con la atribución clásica y el costo por conversión incremental, con el intervalo de credibilidad en el nivel de confianza del experimento.

**Prompt:** "Compara el costo por acción incremental y el ROAS incremental en todos mis experimentos de Incrementality de los últimos 6 meses."

**Respuesta esperada de la IA:** La IA compara en paralelo la eficiencia de tus experimentos completados de los últimos 6 meses y destaca qué campañas generaron el mayor valor incremental por cada dólar de gasto en anuncios.

</Accordion>

<div id="analyze-skan-performance" />

<Accordion title="Analiza el rendimiento de SKAN">

Obtén insights sobre el rendimiento de las campañas de iOS con el framework SKAdNetwork de Apple. Identifica las campañas de mejor rendimiento y analiza las tendencias de KPI para apoyar la toma de decisiones.

**Reinicia Gemini CLI** para aplicar la nueva configuración.

**Prompt:** "¿Cuál fue el ROI por red en el último mes?"  
**Respuesta esperada de la IA:** La IA recupera los resultados de ROI para el período seleccionado y destaca las principales redes.

**Crea o abre un archivo** de configuración según el alcance:

**Prompt:** "¿Qué campañas tienen el CPI más bajo?"  
**Respuesta esperada de la IA:** La IA identifica campañas con el CPI más bajo, clasificando a los mejores desempeñadores.

**Tipo de Autenticación:** Token Portador

**Prompt:** "¿Cuáles fueron las tasas de conversión semanales para el evento af\_subscribed en el último mes?"  
**Respuesta esperada de la IA:** La IA proporciona un desglose semana a semana de las tasas de conversión para el evento e indica la tendencia general.

**Uso de datos**: Los datos se cifran, procesan en tiempo real y nunca se almacenan.

**Prompt:** "¿Qué redes tienen las tasas nulas más altas y qué campañas bajo ellas muestran las tasas nulas más altas?"  
**Respuesta esperada de la IA:** La IA identifica redes con las tasas nulas más altas y describe las campañas específicas que más contribuyen a esas tasas.

</Accordion>

<div id="onelink-management" />

<Accordion title="Gestión de OneLink">

Crea enlaces de OneLink, consulta y audita plantillas y Smart Banners para dar soporte a un enrutamiento coherente y recorridos de usuario precisos. MCP puede ayudarte a resolver problemas, verificar la configuración de enlaces a escala y crear enlaces nuevos a partir de una conversación.

**Prompt:** "Crea un enlace de OneLink en la plantilla HolidayPush2025 para nuestro boletín de correo electrónico, con el nombre de campaña black\_friday y el valor del deep link sale\_page."

**Respuesta esperada de la IA:** La IA encuentra la plantilla y su dominio, resume los parámetros del enlace y te pide que confirmes. Después de que lo apruebes, crea el enlace y devuelve la URL corta.

**Prompt:** "Audita la plantilla 'HolidayPush2025' y muestra todos los enlaces con parámetros."

**Respuesta esperada de la IA:** Tabla CSV con enlaces cortos y valores de parámetros asociados.

**Prompt:** "¿Por qué este OneLink redirecciona a la App Store para los usuarios existentes?"

**Respuesta esperada de la IA:** Solución de problemas de insights que combinan parámetros de enlace y lógica alternativa.

**Prompt:** "Lista todos los enlaces OneLink con QR habilitados para la aplicación TravelBuddy".

**Respuesta esperada de la IA:** Una lista de OneLinks generados con enlaces QR y metadatos asociados.

**Prompt:** "¿Qué parámetros, capacidades y comportamiento de redirección tiene este enlace: https://mypets.onelink.me/abc123?"

**Respuesta esperada de la IA:** La IA devuelve los parámetros del enlace por categoría, sus capacidades habilitadas, como deep linking y retargeting, y cómo redirige a los usuarios según el dispositivo, la plataforma y el estado de instalación.

**Solicitud:** "Enumera todos los Smart Banners activos de mi cuenta."

**Respuesta esperada de la IA:** La IA devuelve los metadatos del banner, incluidos el ID del banner, el nombre, el grupo, el sitio web y el tipo de banner.

**Solicitud:** "Compara el rendimiento de mis dos creatividades de Smart Banner durante los últimos 30 días."

**Respuesta esperada de la IA:** La IA devuelve impresiones, clics e instalaciones de los banners seleccionados en paralelo.

</Accordion>

<div id="knowledge-base-and-developer-support" />

<Accordion title="Base de conocimientos y soporte para desarrolladores">

Accede rápidamente a la documentación de AppsFlyer y a los recursos de DevHub. Obtén respuestas precisas sobre la configuración del SDK, el comportamiento del producto y la lógica de medición, directamente en tu chat de IA.

**Indicador**: "¿Cómo configuro la desduplicación de eventos in-app en Android?"

**Respuesta de IA esperada**: La IA proporciona pasos de configuración, fragmentos de código y mejores prácticas.

**Prompt:** "¿Cuál es la ventana de lookback de atribución para las instalaciones de TikTok?"

**Respuesta de IA esperada**: Explicación basada en las últimas reglas de atribución específicas de la plataforma.

**Prompt:** "¿Cuál es la mejor manera de optimizar el ROAS de mi aplicación con AppsFlyer?"

**Respuesta de IA esperada**: La IA describe palancas estratégicas como la segmentación, la optimización de partners y las mejores prácticas de medición del LTV.

</Accordion>

<div id="apps-management" />

<Accordion title="Gestión de aplicaciones">

Comprende tus aplicaciones facilmente recuperando detalles de configuración clave como ventanas de atribución, tiempos de espera de la sesión, configuración de re-engagement y más. Te permite auditar y comparar la configuración de las aplicaciones en todo tu portfolio para garantizar la coherencia, mejorar la gestión e identificar rápidamente las discrepancias impulsadas por la configuración en tus datos de medición.

**Indicador**: "¿Cuál es la ventana de atribución configurada para mis aplicaciones de juegos?"

**Respuesta de IA esperada**: Una lista de aplicaciones con sus ventanas de atribución configuradas, que destacan cualquier desviación del estándar.

**Indicador**: "¿En cuál de mis aplicaciones tengo una ventana de lookback diferente?"

**Respuesta de IA esperada**: La IA coloca en la superficie las aplicaciones con ventanas de lookback no estándar y muestra sus valores configurados.

**Indicador**: "Enumera todas mis aplicaciones ancladas a iOS que están activas".

**Respuesta de IA esperada**: Una lista de aplicaciones iOS ancladas que están actualmente activas, incluidos los IDs y nombres de las aplicaciones.

**Indicador**: "¿Cuál es la configuración de tiempo de espera de la sesión actual para la aplicación de juegos de AppsFlyer y podría afectar a la atribución de mi re-engagement?"

**Respuesta esperada de la IA:** La IA devuelve la configuración de tiempo de espera de la sesión y explica su impacto en el re-engagement.

</Accordion>

<div id="h_01M6DQ8W2JQ9ECH5VEZPRT7221" />

<Accordion title="Gestión de integraciones de Partners">

Recupera el estado y la configuración de la integración de partners para tus aplicaciones: qué partners están activos, cómo están configurados y si los mapeos de eventos y la configuración de atribución están configurados según lo esperado. Úsalo para auditar el estado de las integraciones y solucionar problemas específicos de partners sin abrir la IU de AppsFlyer HQ.

<div id="note-6" />

> 📘 **Note**
>
> La gestión de integraciones de partners es actualmente de solo lectura. Puedes recuperar y auditar la configuración mediante MCP de AppsFlyer, pero los cambios se siguen teniendo que hacer en la interfaz de usuario de AppsFlyer HQ.

**Prompt:** "¿Qué partners están activos para Mypets.android.com?"

**Respuesta esperada de la IA:** La IA devuelve una lista de integraciones de partners activas para esa aplicación, incluida la categoría del partner, el nombre del partner y la plataforma.

**Prompt:** "¿Qué partners tecnológicos usamos para Mypets.android.com?"

**Respuesta esperada de la IA:** La IA devuelve el subconjunto de integraciones activas clasificadas como partners tecnológicos (integraciones de tipo analítica) para esa aplicación.

**Prompt:** «¿Qué ventana de atribución está configurada para AppLovin en esta aplicación?»

**Respuesta esperada de la IA:** La IA devuelve la ventana de lookback de atribución de instalación configurada para la integración de AppLovin.

**Prompt:** «Muéstrame la configuración completa de Moloco en Mypets.android.com.»

**Respuesta esperada de la IA:** La IA devuelve la configuración completa de la integración, incluida la configuración de atribución, los controles para compartir datos y los mapeos de eventos in-app.

</Accordion>

<div id="audiences-management" />

<Accordion title="Gestión de audiencias">

Obtén visibilidad instantánea de la estructura, la propiedad, las conexiones de los partners y las pruebas activas de la audiencia. Supervisa el estado de las cargas, detecta conexiones fallidas, identifica audiencias obsoletas y comprende cómo está configurada cada audiencia. Usa esta información para optimizar la gestión de campañas multifuncionales.

**Indicador**: "Dame todas las audiencias activas para la aplicación FinancePro".

**Respuesta de IA esperada**: Lista de audiencias con metadatos como fecha de creación, propietario y partners.

**Indicador**: "¿Quién actualizó por última vez a la audiencia 'Usuarios abandonados - Nivel A'?"

**Respuesta de IA esperada**: ID de usuario o correo electrónico con marca de tiempo de la última modificación.

**Indicador**: "Enumera todas las audiencias actualmente en una prueba dividida con Meta y TikTok".

**Respuesta de IA esperada**: Lista de audiencias activas con configuración de prueba y porcentajes divididos.

**Prompt:** "Quiero hacer una prueba de Moloco frente a Google; dame todas las audiencias conectadas a Google."

**Respuesta de IA esperada:** La IA devuelve una lista de audiencias conectadas a Google con su estado actual y su configuración.

**Prompt:** "Voy a cerrar (red), dame una lista de las audiencias activas en funcionamiento."

**Respuesta de IA esperada:** La IA devuelve todas las audiencias activas con sus partners conectados y su estado actual.

**Prompt:** "Dame una lista de todas las audiencias activas, sus partners conectados y sus divisiones actuales."

**ChatGPT: Admitido en todos los planes**/span>/strong>

**Prompt:** "¿Alguna de mis audiencias de Meta está fallando actualmente al cargarse?"

**Respuesta de IA esperada:** La IA devuelve una lista de audiencias conectadas a Meta con estado de carga fallida, incluido el mensaje de error de cada una.

**Prompt:** "Quiero revisar mis campañas de TikTok; ¿qué audiencias conectadas a TikTok están fallando y desde cuándo?"

**Respuesta de IA esperada:** La IA devuelve todas las audiencias conectadas a TikTok con estado fallido y la hora de su última carga correcta.

**Prompt:** "Dame todas las audiencias que no hayan tenido ninguna carga correcta en los últimos 7 días."

**Respuesta de IA esperada:** La IA devuelve una lista de audiencias que no han tenido ninguna carga exitosa en los últimos 7 días y sus estados de conexión actuales.

</Accordion>

<div id="feedback-tool" />

<Accordion title="Herramienta de feedback">

Envía comentarios sobre tu experiencia de uso del MCP de AppsFlyer directamente a través de la interfaz del asistente. Nos ayudará a mejorar y dar forma al futuro del producto.

**Indicador**: "Los análisis proporcionados en la herramienta de análisis son increíbles, muy útiles para nuestra toma de decisiones. Me gustaría que se añadiera la medición de eventos in-app como opción en el análisis."

**Respuesta de IA esperada**: La IA envía la información del mensaje al equipo de producto MCP de AppsFlyer.

</Accordion>

<div id="cost-configuration-integration" />

<Accordion title="Integración de configuración de costos">

Obtén visibilidad y control total sobre tus datos de costos con el MCP de Configuración de Costos.  
 Esta integración te ayuda a maximizar la cobertura de costos, detectar brechas de integración temprano y asegurar que los datos de costos permanezcan completos y precisos en todas las redes publicitarias.

**Indicador**: “¿Qué integraciones de costos activas tengo en mi cuenta de AppsFlyer?”

**Respuesta de IA esperada**: Lista todas las integraciones de costos habilitadas en la cuenta de AppsFlyer del usuario junto con sus IDs de aplicación vinculadas y estado actual.

**Indicador**: “Muéstrame los problemas que tengo en mis integraciones de costos activas.”

**Respuesta de IA esperada**: Muestra una lista de integraciones de costos activas (habilitadas) que tuvieron problemas en los últimos 7 días, ordenadas por red publicitaria y aplicaciones conectadas.

**Indicador**: “¿Qué integraciones de costos debería conectar según mis datos de atribución recientes?”

**Respuesta esperada de la IA:** La IA muestra las ad networks que admiten la integración de costos, pero que aún no están conectadas, clasificadas según el volumen de tráfico reciente por aplicación.

</Accordion>

<div id="ad-revenue-integrations" />

<Accordion title="Integraciones de ingresos por publicidad">

Obtén visibilidad y control sobre tus integraciones de ingresos por anuncios con AppsFlyer MCP. Puedes usar MCP para confirmar qué integraciones de ingresos por anuncios están habilitadas, supervisar su estado, detectar brechas a tiempo y mantener un flujo constante de datos de ingresos por anuncios en tus aplicaciones y partners de monetización.

**Token Portador:** Tu token MCP personal (generado en **AppsFlyer → Centro de Seguridad → Tokens de AppsFlyer**)

Si inicio sesión, ¿tendrá acceso la IA a todos mis datos almacenados en la plataforma de AppsFlyer?

En cualquier chat, haz clic en el **Más** botón (⚙️ o + ícono junto al cuadro de entrada).

**Respuesta de IA esperada:** La IA muestra las integraciones de ingresos por anuncios habilitadas que tuvieron problemas en los últimos 7 días, agrupadas por partner de mediación, tipo de integración y app.

</Accordion>

<div id="user-management-and-role-control" />

<Accordion title="Gestión de usuarios y control de roles">

Optimiza la administración de tu cuenta de AppsFlyer recuperando información completa de usuarios y roles. Esta herramienta permite a los administradores mantener una base de datos clara y garantizar los controles de acceso adecuados de manera eficiente.

**Indicador**: "Lista de usuarios inactivos que no iniciaron sesión en AppsFlyer en los últimos 6 meses"

**Respuesta de IA esperada**: Una lista filtrada que muestra a los usuarios con fechas de último inicio de sesión superiores a 6 meses, o sin ningún inicio de sesión, incluidas sus direcciones de correo electrónico, roles y marcas de tiempo exactas del último inicio de sesión para ayudar a identificar a los usuarios para desactivarlos.

**Indicador**: "Muéstrame todos los usuarios agrupados por sus niveles de permisos y resalta cualquier usuario administrador."

**Respuesta de IA esperada**: Usuarios organizados por tipos de roles (Administrador, miembro del equipo, Espectador, etc.) con los usuarios administradores resaltados claramente, mostrando sus aplicaciones asociadas y los permisos de acceso geográfico.

**Indicador**: "Uno de los miembros del equipo se ha quejado de que no puede iniciar sesión en AppsFlyer. ¿Puedes verificar si su usuario existe y cuál es su estado actual?"

**Respuesta esperada de la IA:** La IA verifica si el usuario existe y devuelve el rol actual del usuario, las aplicaciones asociadas, la fecha del último login y las posibles restricciones de acceso.

**Indicador**: "¿Qué usuarios tienen acceso a más de 5 aplicaciones y cuáles son sus funciones?"

**Control de acceso**: Todo el acceso a la API se rige por tu rol de usuario de AppsFlyer.

</Accordion>

<div id="other-information" />

## Otra información

<div id="h_privacy-and-security" />

<Accordion title="Privacidad y seguridad">

AppsFlyer MCP permite que la herramienta de IA que selecciones consulte datos de AppsFlyer en función de tus permisos existentes.

<div id="data-processing" />

#### Procesamiento de datos

El MCP de AppsFlyer actúa como proxy seguro. Obtiene datos en tiempo real y devuelve solo lo necesario para la consulta. AppsFlyer MCP no archiva ni almacena los resultados de las consultas a largo plazo.

<div id="credentials" />

#### Credenciales

Tu acceso habilita las llamadas de la API en tu nombre, pero tus credenciales nunca se comparten. Los datos a los que se accede a través del MCP de AppsFlyer no se utilizan para entrenar modelos de idiomas grandes (LLM) como Claude. Tus credenciales de AppsFlyer no se comparten con la herramienta de IA.

<div id="permissions" />

#### Permisos

AppsFlyer MCP usa tus permisos existentes de AppsFlyer. Accede usando tus credenciales de AppsFlyer y la IA solo verá a lo que puedes acceder.

No hay ninguna capa de permisos independiente que configurar para el acceso a MCP.

<div id="read-and-write-access" />

#### Acceso de lectura y escritura

La mayoría de las herramientas de MCP de AppsFlyer son solo de lectura y consulta. La excepción es create\_onelink\_link, que crea enlaces de OneLink en tu cuenta. Antes de crear un enlace, la IA te muestra sus detalles y te pide confirmación. No se crea nada hasta que lo apruebes.

<div id="ai-provider-data-usage" />

#### Uso de datos del proveedor de IA

Los datos recuperados por AppsFlyer MCP pueden compartirse con la herramienta de IA que selecciones para responder a tu consulta. Solo se comparten los datos necesarios para generar la respuesta.

AppsFlyer no controla si la herramienta de IA que has seleccionado almacena, procesa o aprende a partir de los datos. Revisa los términos y las políticas de uso de datos de tu proveedor de IA antes de conectar AppsFlyer MCP.

<div id="certifications" />

#### Certificaciones

AppsFlyer cuenta con las certificaciones ISO 27001, ISO 42001 y SOC 2. ISO 42001 es la norma internacional para los sistemas de gestión de IA.

</Accordion>

<div id="tool-mapping" />

<Accordion title="Asignación de herramientas">

Por defecto, todas las herramientas están habilitadas. Recomendamos mantenerlos habilitados para garantizar una funcionalidad completa y evitar problemas durante el uso.

Cada herramienta se asigna a una categoría funcional, como analizar el rendimiento, la gestión de aplicaciones o la gestión de OneLink. Algunas categorías pueden incluir múltiples herramientas.

Consulta la tabla a continuación para obtener una lista completa de herramientas y sus asignaciones de categorías.

<table><thead><tr><th>Categoría</th><th>¿Por qué no funciona la herramienta?</th><th>Descripción</th></tr></thead><tbody><tr><td><a href="An%C3%A1lisis">Analizar el rendimiento</a></td><td>fetch_aggregated_data</td><td>Recupera datos agregados del dashboard con rangos de fechas, agrupaciones, métricas y filtros personalizados.</td></tr><tr><td><a href="#analiza-el-rendimiento-creativo">Analiza el rendimiento creativo</a></td><td>get_creative_performance</td><td>Recupera datos de performance agregados a nivel de creativo (gasto, instalaciones, CPI, ROAS, cohortes de retención y de ingresos) en redes, campañas y aplicaciones, desglosados por nombre del creativo, tipo, tamaño, duración, antigüedad, end card, nombre del evento in-app y más. Incluye enlaces de recursos para las vistas previas de creativos.</td></tr><tr><td rowspan="2"><a href="#h_analyze-incrementality-experiments">Analizar la incrementalidad para experimentos de UA</a></td><td>incrementality_list_experiments</td><td>Enumera los experimentos de incrementalidad filtrados por estado, aplicación, país, fuente de medios e intervalo de fechas.</td></tr><tr><td>incrementality_get_experiment_results</td><td>Obtiene los resultados de un experimento específico, incluidos el lift, las conversiones incrementales, el factor de incrementalidad y el costo por conversión incremental.</td></tr><tr><td rowspan="2"><a href="./beta-appsflyer-mcp#audiences-management">Gestión de aplicaciones</a></td><td>get_apps</td><td>Enumera todas las aplicaciones permitidas organizadas por estado anclado/no anclado con solicitudes de transferencia.</td></tr><tr><td>get_app_settings</td><td>Obtiene todos los ajustes de configuración de la aplicación, incluidas las ventanas de atribución, los controles de privacidad, la gestión de sesiones y las configuraciones específicas de la plataforma.</td></tr><tr><td><a href="#h_01M6DQ8W2JQ9ECH5VEZPRT7221">Gestión de integraciones de Partners</a></td><td>get_app_partner_integration_configuration</td><td>Obtiene la configuración completa de una integración de partner específica, incluida la configuración de atribución, el uso compartido de datos y las asignaciones de eventos in-app.</td></tr><tr><td><a href="./beta-appsflyer-mcp#cost-configuration-integration">Integración de configuración de costos</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>Obtén una visión clara del estado de las integraciones de costos activas junto con las integraciones de costos faltantes en tu cuenta para hacer que el informe de costos sea más completo y preciso.</td></tr><tr><td><a href="#ad-revenue-integrations">Integraciones de ingresos por publicidad</a></td><td><p>list_adrevenue_supported_media_sources</p><p>get_active_adrevenue_integrations</p></td><td>Comprueba qué integraciones están habilitadas, supervisa su estado, detecta deficiencias de configuración y ayuda a mantener la coherencia de los datos de ingresos por anuncios.</td></tr><tr><td><a href="An%C3%A1lisis">Rendimiento de SKAN</a></td><td>skan_get_app_data</td><td>Recupera datos de rendimiento de SKAN agregados. Los datos pueden agruparse por red, campaña o evento, y analizarse en rangos de fechas personalizados.</td></tr><tr><td rowspan="4"><a href='Haz%20clic%20en%20tu%20nombre%20(abajo%20a%20la%20izquierda)%20&gt;%20&lt;strong%20data-start="1494"%20data-end="1506"&gt;Configuraci%C3%B3n,&lt;/strong&gt;%20o%20en%20un%20chat%20nuevo,%20haz%20clic%20en%20&lt;strong&gt;B%C3%BAsqueda%20y%20herramientas&lt;/strong&gt;%20&gt;%20&lt;strong&gt;Administrar%20conectores&lt;/strong&gt;.'>Gestión de OneLink</a></td><td>get_onelink_templates</td><td>Enumera todas las plantillas de OneLink (configuraciones de enrutamiento básicas).</td></tr><tr><td>get_onelink_template_links</td><td>Obtiene todos los enlaces de OneLink creados a partir de una plantilla específica.</td></tr><tr><td>get_onelink_details</td><td>Obtiene detalles de configuración completos para un OneLink específico.</td></tr><tr><td>discover_onelink</td><td>Detecta los parámetros, las capacidades y el comportamiento de redirección de un enlace a partir de una URL corta o larga.</td></tr><tr><td> </td><td>create_onelink_link</td><td>Crea un nuevo enlace corto en una plantilla de OneLink existente. Requiere la confirmación del usuario antes de que se cree el enlace.</td></tr><tr><td> </td><td>list_smart_banners</td><td><p>Enumera los Smart Banners de la cuenta con metadatos, y permite filtrarlos por estado activo y fecha de creación.</p><p><strong>Nota:</strong> list_smart_banners devuelve como máximo 30 banners por cuenta, ordenados primero por los banners activos y después por la fecha de la última modificación.</p></td></tr><tr><td> </td><td>get_smart_banner_performance</td><td>Obtiene el rendimiento de Smart Banner para ID de banner específicos, con granularidad total o diaria.</td></tr><tr><td rowspan="3"><a href="Requisito%20previo%20-%20Se%20necesita%20administrador">Gestión de audiencias</a></td><td>list_active_audiences</td><td>Enumera todas las audiencias activas que se calculan diariamente.</td></tr><tr><td>list_audiences_connections</td><td>Enumera todas las integraciones de partners publicitarios para los datos de audiencia.</td></tr><tr><td>get_audience_connections</td><td>Obtiene conexiones de partners para una audiencia específica.</td></tr><tr><td><a href="Admitido%20en%20planes%20Pro,%20Max,%20Team%20y%20Enterprise%20en%20web%20y%20de%20ordenador.">Base de conocimientos y soporte para desarrolladores</a></td><td>get_public_knowledge</td><td>Busca documentación en la base de conocimientos de AppsFlyer y en el DevHub.</td></tr><tr><td><a href="Actualizaci%C3%B3n">Herramienta de feedback</a></td><td>send_feedback</td><td>Envía comentarios sobre las herramientas o el sistema.</td></tr><tr><td><a href="./beta-appsflyer-mcp#user-management-and-role-control">Gestión de usuarios y control de roles</a></td><td>get_users</td><td>Enumera usuarios y roles de AppsFlyer.</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Uso de múltiples cuentas | AppsFlyer MCP usa datos solo de la cuenta predeterminada. Para cambiar de cuenta o conectar varias cuentas a la vez, consulta [Uso de varias cuentas o agencias](#h_use-multiple-accounts-or-agencies). |
| Enlaces de OneLink | <ul><li>**Creación de enlaces de OneLink:**</li></ul><ul><li>Se pueden crear hasta 10 enlaces al día por cuenta.</li><li>Los enlaces se crean en una plantilla de OneLink existente.</li></ul><ul><li>La herramienta get\_onelink\_template\_links solo incluye enlaces creados desde la página de gestión de OneLink, no enlaces creados mediante API, SDK o creación masiva.</li><li>Discover OneLink (discover\_onelink) no tiene esta restricción. Es compatible con todos los tipos de enlace de AppsFlyer, incluidos los enlaces de una sola plataforma (heredados), los dominios de marca y los enlaces creados mediante la interfaz de usuario, API, SDK o creación masiva.</li></ul> |
| Integraciones de socios | <ul><li>Los detalles de configuración no están disponibles para las integraciones de partners de tipo agencia a través de esta herramienta.</li><li>Las integraciones de partners de tipo agencia y de tipo red publicitaria no son compatibles.</li><li>Las configuraciones de permisos no están disponibles.</li></ul> |
| Límites de tasas | <ul><li>20 solicitudes/minuto</li><li>Audiencias: 350 solicitudes por minuto</li><li>SKAN: Hasta 10.000 filas por consulta</li></ul> |
| Límite de filas | Las consultas de performance de creativos devuelven un máximo de 300 filas por solicitud. La paginación no es compatible actualmente. Si una consulta coincide con más de 300 creativos o campañas, acótala por intervalo de fechas, fuente de medios u otro filtro para mantenerte por debajo del límite. |
| Rango de fechas | <ul><li>3 años</li><li>Máximo 90 días por solicitud</li></ul> |
| Agrupaciones | <ul><li>4 agrupaciones por solicitud</li><li>Como está disponible en el <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics">tablero de SKAN</Anchor></li></ul> |
| Límites de la aplicación | <ul><li>10 aplicaciones por solicitud</li><li>Una aplicación por solicitud (solo iOS)</li></ul> |
| Dimensiones admitidas | Soporta todas las dimensiones disponibles en Mis Tableros |
| Datos agregados | Los datos agregados no son compatibles. Esto incluye niveles de granularidad semanales y mensuales y métricas personalizadas. |
| Actualización | Los datos de SKAN están disponibles con un retraso de hasta 3 días, en UTC. |
| Moneda y zona horaria | Los datos de SKAN están disponibles en USD de forma predeterminada. Se admiten monedas alternativas usando `revenue_alt = true`. Los datos se reportan en UTC. |
| Desactivación de MCP | <ul><li>MCP está habilitado de forma predeterminada y un administrador puede deshabilitarlo en **Cuenta & Perfil > Funciones de IA**.</li><li>Cuando MCP está desactivado, los usuarios no pueden acceder a los datos de AppsFlyer a través de MCP en herramientas de IA externas.</li><li>Las conexiones existentes pueden seguir funcionando hasta que expire la sesión actual.</li><li>Desactivar MCP no afecta a las conexiones habituales de la API ni a otras funciones de IA en AppsFlyer.</li><li>Si se está utilizando un token MCP, primero debes eliminarlo en **Centro de seguridad > Tokens de AppsFlyer**.</li></ul> |

</Accordion>

<div id="troubleshoot-connection-issues" />

## Solucionar problemas de conexión

Si la conexión de AppsFlyer MCP no funciona, sigue los pasos correspondientes a tu método de autenticación.

<div id="h_troubleshoot-browser-based-oauth-login" />

<Accordion title="Login de OAuth basado en el navegador">

Usa esta sección para clientes que se conectan mediante login en el navegador, como Gemini CLI, Copilot CLI, ChatGPT, Claude.ai y Claude Desktop.

1. **Vuelve a autenticar tu sesión.** Las sesiones de OAuth caducan aproximadamente cada 7 días. Vuelve a ejecutar el flujo de conexión y completa de nuevo el login en el navegador.
2. **Completa el flujo de autenticación.** Asegúrate de que el login en el navegador se complete correctamente. Cuando se te solicite, haz clic en **Permitir** o **Aprobar** y, a continuación, vuelve a tu cliente MCP.
3. **Reinicia la sesión.** Reinicia la sesión de tu CLI, chat o aplicación. A continuación, vuelve a conectarte al servidor MCP.
4. **Verifica la configuración del servidor MCP.** Confirma los siguientes valores:

| Campo | value |
| --- | --- |
| Tipo de servidor | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |

5. **Comprueba los permisos del usuario.** Asegúrate de que tu usuario de AppsFlyer tenga acceso a las apps relevantes y a los datos solicitados.

</Accordion>

<div id="h_troubleshoot-bearer-token-authentication" />

<Accordion title="Autenticación con token Bearer">

Usa esta sección para Claude Code, n8n, Make, agentes alojados por tu cuenta y otras herramientas de automatización.

1. **Comprueba si se revocó el token.** Los tokens se pueden revocar manualmente. Es posible que los tokens creados antes del **10 de marzo de 2026, 19:00 UTC** ya no funcionen.
2. **Crea un token MCP nuevo.** Para restaurar el acceso:
   1. Envíanos tus comentarios con el mensaje "Envía comentarios a AppsFlyer" y contacta con el equipo de soporte de AppsFlyer.
   2. Ve a **Menú de la cuenta > Centro de seguridad > Gestión de tokens**.
   3. Localiza los tokens revocados.
   4. Elimina el token revocado.
   5. Crea un token MCP nuevo.
   6. Actualiza tu cliente MCP o automatización con el nuevo token.
3. **Comprueba el encabezado de Authorization.** Asegúrate de que el encabezado use exactamente este formato:

   ```http
   Authorization: Bearer <YOUR_MCP_TOKEN>
   ```
4. **Verifica la configuración del servidor MCP.** Confirma los siguientes valores:

| Campo | value |
| --- | --- |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| Transporte | `HTTP` |
| Encabezado | `Authorization: Bearer <YOUR_MCP_TOKEN>` |

5. **Verifica que el servidor esté registrado.** Para Claude Code, ejecuta lo siguiente:

   ```bash
   claude mcp list
   ```
6. **Vuelve a añadir el servidor MCP si es necesario.**

   ```bash
   https://support.appsflyer.com/hc/en-us/articles/36349070304785--Closed-Beta-MCP#create-and-manage-attribution-links
   ```
7. **Comprueba los permisos del token.** El token de MCP hereda los permisos del administrador que lo creó. Asegúrate de que el token tenga acceso a las apps pertinentes y a los datos solicitados.

</Accordion>

<div id="h_access-and-permission-issues" />

<Accordion title="Problemas de acceso y permisos">

Si la autenticación se realiza correctamente pero el acceso sigue fallando:

* Tu administrador de AppsFlyer puede haber restringido el acceso a MCP.
* Si no tienes acceso a la configuración de Account & Profile, es posible que el acceso a MCP esté bloqueado.
* Contacta con tu administrador de AppsFlyer para habilitar el acceso.
* Asegúrate de que tu usuario o token tenga acceso a las apps pertinentes y a los datos solicitados.

</Accordion>

<div id="h_general-connection-checks" />

<Accordion title="Comprobaciones generales">

Si el problema persiste:

* Asegúrate de que tu cliente sea compatible con MCP.
* Comprueba si las restricciones de red o del firewall bloquean el endpoint de MCP.
* Confirma que la URL de MCP sea correcta:

  ```text
  https://mcp.appsflyer.com/auth/mcp
  ```
* Prueba a volver a conectarte desde una sesión o un entorno nuevos.

</Accordion>

<div data-zendesk-anchors="h_01K9CJ9WQ3JJSYWDMNJ5GP7N04=disclaimer what-is-appsflyer-mcp=qu%C3%A9-es-el-mcp-de-appsflyer h_01JY3G849QAT2GC714FR6CADH2=qu%C3%A9-es-el-mcp-de-appsflyer h_set-up-appsflyer-mcp=configuraci%C3%B3n-del-mcp-de-appsflyer set-up-appsflyer-mcp=configuraci%C3%B3n-del-mcp-de-appsflyer h_01KT8Y9JEJEZ26BRHK530JDB0D=advertencia h_authentication-methods=m%C3%A9todos-de-autenticaci%C3%B3n authentication-methods=m%C3%A9todos-de-autenticaci%C3%B3n h_browser-based-oauth-login=inicio-de-sesi%C3%B3n-oauth-basado-en-navegador browser-based-oauth-login=inicio-de-sesi%C3%B3n-oauth-basado-en-navegador h_bearer-token-authentication=autenticaci%C3%B3n-con-token-bearer bearer-token-authentication=autenticaci%C3%B3n-con-token-bearer h_set-up-by-client=configuraci%C3%B3n-por-el-cliente set-up-by-client=configuraci%C3%B3n-por-el-cliente claude-ai-and-claude-desktop=h_claude-ai-and-claude-desktop h_01KT8Y9JEJQNXK3SZ7M0ETH5RN=caracter%C3%ADstica h_set-up-claude-ai-and-desktop=configura-claude-chat-y-cowork set-up-claude-ai-and-desktop=configura-claude-chat-y-cowork h_test-claude-connection=probar-la-conexi%C3%B3n-de-claude test-claude-connection=probar-la-conexi%C3%B3n-de-claude h_01M09YV6XHR3DPYSHZA127XB50=nota claude-code=h_claude-code h_add-appsflyer-mcp-to-claude-code=nota add-appsflyer-mcp-to-claude-code=nota cursor-ide=h_cursor-ide vs-code=h_vs-code chatgpt=h_chatgpt custom-gpt-available-for-all-packages-including-free-enterprise=c%C3%B3mo-agregar-el-gpt-personalizado-de-appsflyer mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans=usando-el-conector-de-appsflyer-en-chatgpt h_01KT8Y9JEJ806MVHJACM0VNM0K=nota-1 gemini-cli=h_gemini-cli h_add-appsflyer-mcp-to-gemini-cli=para-agregar-el-appsflyer-mcp-a-gemini-cli add-appsflyer-mcp-to-gemini-cli=para-agregar-el-appsflyer-mcp-a-gemini-cli h_troubleshoot-gemini-cli-authentication=solucionar-problemas-de-autenticaci%C3%B3n-de-gemini-cli troubleshoot-gemini-cli-authentication=solucionar-problemas-de-autenticaci%C3%B3n-de-gemini-cli copilot-cli=h_copilot-cli h_add-appsflyer-mcp-to-copilot-cli=es-seguro-el-mcp-de-appsflyer add-appsflyer-mcp-to-copilot-cli=es-seguro-el-mcp-de-appsflyer third-party-and-self-hosted-platforms=h_third-party-and-self-hosted-platforms h_mcp-connection-details=detalles-de-conexi%C3%B3n-mcp mcp-connection-details=detalles-de-conexi%C3%B3n-mcp h_01KT8Y9JEKZRB56RZJXMMN4WV0=nota-2 h_example-use-cases=ejemplos-de-casos-de-uso example-use-cases=ejemplos-de-casos-de-uso other-platforms=h_other-platforms use-multiple-accounts-or-agencies=h_use-multiple-accounts-or-agencies h_switch-between-accounts=cambiar-entre-cuentas-oauth-basado-en-navegador switch-between-accounts=cambiar-entre-cuentas-oauth-basado-en-navegador h_connect-multiple-accounts-simultaneously=una-vez-habilitado-puedes-comenzar-a-hacer-preguntas-como connect-multiple-accounts-simultaneously=una-vez-habilitado-puedes-comenzar-a-hacer-preguntas-como using-appsflyer-mcp=uso-del-mcp-de-appsflyer h_01JY3G1ZEC5Q30KP49RAA7EHRS=uso-del-mcp-de-appsflyer use-cases-and-prompts=casos-de-uso-y-prompts h_01JY3WMZ41HHQ4G13DGV8DPJMW=casos-de-uso-y-prompts h_01JZHT6BA2NX8GXNV8675XNVWT=importante h_01JY3WZE6G2WB6DCWV68G1T36D=analyze-performance h_01M09YV6XJ7AM6S502BT2A594T=nota-3 analyze-creative-performance=h_analyze-creative-performance analyze-incrementality-experiments=h_analyze-incrementality-experiments h_01K7P0A6V86FZ3YQTQ4N5JZ4ZX=analyze-skan-performance h_01JY3VJEQMRDFAFTKZMPZ90RHP=onelink-management h_01JY3VJEQMXD32NSEE0E0FWG60=knowledge-base-and-developer-support h_01K01CE5NQ56HRT967F78ETKMS=apps-management h_01K01CE5NQBW6AADMHEPBQQN7S=audiences-management h_01JY3VJEQNYKZ3Z724XM9JRWZF=feedback-tool h_01K9SHEQBWKK6AC0GD0YQVVJJ9=cost-configuration-integration h_01KGM1A7V6NB16A1Q07V5FQG2M=ad-revenue-integrations h_01K338G5KA09TESMNC6Z88RJCP=user-management-and-role-control other-information=otra-informaci%C3%B3n h_01JZHTJ1FQMXX9GSAN31E8HAYF=otra-informaci%C3%B3n privacy-and-security=h_privacy-and-security h_data-processing=procesamiento-de-datos data-processing=procesamiento-de-datos h_credentials=credenciales credentials=credenciales h_permissions=permisos permissions=permisos h_read-only-access=acceso-de-lectura-y-escritura read-only-access=acceso-de-lectura-y-escritura h_ai-provider-data-usage=uso-de-datos-del-proveedor-de-ia ai-provider-data-usage=uso-de-datos-del-proveedor-de-ia h_certifications=certificaciones certifications=certificaciones h_01K044H4H18ED75GYQWMPDRA4R=tool-mapping h_01K01DT8656BQM1GW0HDHXGCY2=traits-and-limitations h_troubleshoot-connection-issues=solucionar-problemas-de-conexi%C3%B3n troubleshoot-connection-issues=solucionar-problemas-de-conexi%C3%B3n troubleshoot-browser-based-oauth-login=h_troubleshoot-browser-based-oauth-login troubleshoot-bearer-token-authentication=h_troubleshoot-bearer-token-authentication access-and-permission-issues=h_access-and-permission-issues general-connection-checks=h_general-connection-checks" />
