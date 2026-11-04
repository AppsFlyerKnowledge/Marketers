---
title: Integración de Movable Ink con AppsFlyer
metadata:
  keywords:
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-09-05T11:55:13Z'
  edited_at: '2026-08-12T12:24:40Z'
  id: 28109258392977
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/28109258392977
---
> **De un vistazo:** Configura una integración con Movable Ink para crear recorridos de usuario únicos impulsados por IA en tus campañas de marketing y en tu contenido in-app.

## ![53374 Imagen de la base de conocimientos de Movable Ink.png](https://files.readme.io/0f1a5d3d6b60cccdb8be113c9fd4f3603c7c3ed0ad8573a153709391d29b2c3b-28624891792401.png)

<div id="about-the-integration" />

## Sobre la integración

Movable Ink es un partner de optimización de contenido dinámico que ofrece experiencias personalizadas al cliente en varios canales, como correo electrónico, notificaciones push y SMS. La integración entre AppsFlyer y Movable Ink te permite crear recorridos únicos y personalizados impulsados por IA en tus campañas de marketing y en tu contenido in-app.

<div id="set-up-the-integration" />

## Configura la integración

**Prerrequisitos**

* Para las campañas de correo electrónico, tendrás que tener implementada la integración con tu proveedor de servicios de correo electrónico (ESP).  
  Puedes consultar <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">aquí</Anchor> una lista de los ESP compatibles con AppsFlyer
* Integración del fragmento de código del <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-urlresolver-client">resolver de URL</Anchor> de AppsFlyer en tus aplicaciones móviles (se encarga de resolver el enlace encapsulado de Movable Ink).
* OneLink está configurado y es compatible con Universal Links/App Links. <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Más información</Anchor>

**Configura la integración:**

1. **En Movable Ink:** Inicia sesión en tu cuenta de Movable Ink (si necesitas ayuda, ponte en contacto con tu representante de Movable Ink o con su equipo de experiencia del cliente).
2. Crea tu contenido en **Studio** y finaliza la configuración de tu campaña.
3. Obtén el enlace de Movable Ink para usarlo en campañas de correo electrónico:
   * * Ve a la página **Finish & Export** page.
     * Haz clic en los tres puntos («…») debajo de la sección **Copy Creative Tag** y elige **Copy Link URL**.   
       **Nota:** Finaliza la configuración de tu campaña antes de copiar la URL del enlace.
     * Copia la URL HREF del enlace copiado (resaltada) y guárdala para más tarde. Se utilizará como valor de enlace en el enlace final.   
       <Image alt="Imagen resaltada de Movable Ink.png" src="https://files.readme.io/a2ccca4d6053e1448094dd83478610693b13a7f04a77aaaff7d12305533e8fbe-28405439389201.png" width="1130px" />
4. **En AppsFlyer:** Ve a la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">plantilla de OneLink</Anchor> específica que usarás para la campaña y recupera los siguientes puntos de datos para la integración:
   * * **Dominio de OneLink:** El subdominio para la generación de OneLink en AppsFlyer.
     * **ID de plantilla:** ID de la plantilla a la que se hace referencia o de la creada para la campaña.
     * **PID**: La identificación única de la fuente de medios.  
       El valor recomendado es el nombre del ESP.
5. Monta tu enlace con la estructura de enlace que aparece a continuación. 

   **Estructura del enlace:**

   `https://{{onelink.domain}}/{{template_id}}?pid={{pid_value}}&c={{link_name}}deep_link_value={{mi_link_from_creative_tag}}`

   **Fecha y hora del toque del contributor[n]**

   Aquí tienes un ejemplo de cómo queda un enlace después de añadir los parámetros obligatorios de la tabla siguiente.

   https://link.movableink.com/oskuw854?pid=BRAZE&deep_link_value=https://www.movable-ink-2563.com/p/cp/ee0e28529389f573/c?url=https%3A%2F%2Fwww.movable-ink-2563.com%2Fp%2Frp%2F9011ea048ec4bf03%2Furl&url_sig=D4QtmtC8vqJhU7

   

| Parámetro | Nota | Valor de ejemplo | Advertencia | Obtener de |
| --- | --- | --- | --- | --- |
| `{{onelink.domain}}` | Tu dominio de AppsFlyer | mink.onelink.com |  | UI de AppsFlyer |
| `{{template_id}}` | ID de la plantilla de enlace configurada en AppsFlyer | 1a6f |  | UI de AppsFlyer |
| `{{pid_value}}` | ID del ESP o de la fuente de medios | Nombre del ESP |  | UI de AppsFlyer |
| `{{mi_link_from_creative<br /><br />\n<br /><br />_tag}}` | El enlace HREF de clic de la etiqueta creativa de Movable Ink. Disponible en la página Finish & Export (consulta la imagen en el paso 3.) | https://www.movable-ink-2563<br /><br />.com /p/cp /ee0e28529389f573<br /><br />/curl=https %3A%2 F%2Fwww.<br /><br />movableink2563 .com %2Fp%2<br /><br />Frp%2F9011ea048e c4b f03%2<br /><br />Furl&url \_sig=D4QtmtC8vqJhU7 | El enlace debe estar codificado. | Movable Ink |

   <div id="note" />

   > 📘 **Advertencia**
   >
   > Si los valores de `af_android_url`, `af_ios_url` y `af_web_dp` son idénticos, puedes acortar el enlace usando `af_r` en su lugar. Si hay otro parámetro con el mismo valor, pide a tu gerente de éxito del cliente de AppsFlyer que active la función de duplicación de parámetros.

6. Utiliza el nuevo enlace en tu campaña.  
   **Nota:** El enlace HREF de Movable Ink que has copiado y pegado debería estar codificado. Sin embargo, **si utilizas el enlace en una campaña de correo electrónico a través de tu ESP, los parámetros del ESP no deben codificarse**.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

Consulta más <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#características-y-limitaciones">características y limitaciones de los enlaces de atribución</Anchor>.

<div data-zendesk-anchors="about-the-integration=sobre-la-integraci%C3%B3n h_01J8HQFV2ZYYN7G1FDA1DH1GV3=sobre-la-integraci%C3%B3n h_01J8HX53FVT1N4MG2HPE743RTS=sobre-la-integraci%C3%B3n set-up-the-integration=configura-la-integraci%C3%B3n h_01J710N8QBFHSX9BS6H0NFY918=configura-la-integraci%C3%B3n 01J9GSWGHBA01N227MCEV91YMV=advertencia traits-and-limitations=especificaciones-y-limitaciones h_01J9GAS3T6STFKHD4C6Z6GYFMF=especificaciones-y-limitaciones" />
