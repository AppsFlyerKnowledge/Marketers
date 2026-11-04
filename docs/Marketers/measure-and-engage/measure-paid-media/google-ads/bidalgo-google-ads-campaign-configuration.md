---
title: Bidalgo - Google Ads—Configuración de la campaña
metadata:
  keywords:
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-19T11:46:44Z'
  edited_at: '2026-08-12T12:18:47Z'
  id: 360001325405
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/360001325405
---
> **En pocas palabras:** Bidalgo, un partner integrado de AppsFlyer, es un proveedor líder de soluciones de inteligencia artificial para ayudar a los app marketers a escalar su crecimiento.

<div id="set-up-bidalgo-integration" />

## Configurar la integración de Bidalgo

**Requisito previo:** Antes de configurar la integración, asegúrate de ponerte en contacto con el partner y abrir una cuenta con ellos.

**Nueva integración:**

1. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Busca Bidalgo y selecciona **Integrate**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. Déjalo activado mientras trabajes con Bidalgo.
5. Configura las pestañas restantes según sea necesario a continuación.

**Editar integración existente:**

Busca al partner y selecciónalo.

<div id="note" />

> 📘 **Nota:**
>
> El ID de cliente de Google Ads debe introducirse **sin** guiones.

6. Desde tu cuenta de **Google Ads**, copia el ID de cliente (sin guiones) de la esquina superior izquierda y pégalo en el parámetro **ID de cliente de AppsFlyer Ads**, como se muestra en las siguientes capturas de pantalla.

[![](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)

7. Introduce el número en el campo **ID de cliente de Google Ads**.

<div id="in-app-events" />

### Eventos dentro de la aplicación

1. Para enviar postbacks de eventos in-app a Bidalgo, cambia el interruptor de In-App Events Postback a **ON**.

2. Añade individualmente los eventos in-app que quieras enviar a Bidalgo y asígnalos al campo **Partner Event Identifier**.

3. Selecciona **Send Revenue** para enviar todos los parámetros, incluido el valor de ingresos (si existe en el evento).

4. Haga clic en **Guardar**.

<div id="important-note" />

> 📘 **Nota Importante**
>
> * Desactivar la atribución para Google Ads impide enviar postbacks a los partners de Google Ads.
> * Puedes configurar varias cuentas de Google Ads (CID) para enviar postbacks (paso 5) separando cada CID con una coma.

<div data-zendesk-anchors="set-up-bidalgo-integration=configurar-la-integraci%C3%B3n-de-bidalgo h_01HKA1JNXMRJ8059FAJAEQ6RK5=configurar-la-integraci%C3%B3n-de-bidalgo h_01HKA1JNXM5R15CBVQ2WHT99Z9=nota inapp-events=eventos-dentro-de-la-aplicaci%C3%B3n h_01HKA1JNXM59W74725961FZA27=eventos-dentro-de-la-aplicaci%C3%B3n h_01HKA1JNXMASTQ9X2144JCKKNQ=nota-importante" />
