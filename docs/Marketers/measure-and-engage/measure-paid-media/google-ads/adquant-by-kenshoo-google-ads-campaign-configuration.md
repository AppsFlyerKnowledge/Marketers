---
title: Adquant by Kenshoo - Google Ads—Configuración de campañas
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Kenshoo
    - Adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-12-09T07:43:55Z'
  edited_at: '2026-08-12T12:18:45Z'
  id: 360000654357
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/360000654357
---
> **En resumen:** Optimiza las campañas de Google Adwords usando Adquant by Kenshoo. Una vez configurado, AppsFlyer envía postbacks a Adquant.

## Configuración de Adquant by Kenshoo

**Requisito previo:** Antes de configurar la integración, asegúrate de ponerte en contacto con el partner y abrir una cuenta con ellos.

**Nueva integración:**

1. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Busca Adquant by Kenshoo y selecciona **Integrar**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. Mantenlo activado mientras trabajes con Adquant by Kenshoo.
5. Configura las pestañas restantes según sea necesario a continuación.

**Editar integración existente:**

Busca al partner y selecciónalo.

> 📘 **Nota:**
>
> El ID de cliente de Google Ads debe introducirse **sin** guiones.

6. Desde tu cuenta de **Google Ads**, copia el ID de cliente (sin guiones) de la esquina superior izquierda y pégalo en el parámetro **Ads Customer ID** de AppsFlyer, como se muestra en las capturas de pantalla a continuación.

[![](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)

7. Introduce el **Action Identifier**, **Disable\_Country\_Sending** (proporcionado por Adquant) y el número de **Google Ads Customer ID** en los campos correspondientes.

### Eventos dentro de la aplicación

1. Para enviar postbacks de eventos in-app a Adquant by Kenshoo, activa In-App Events Postback en **ON**.

2. Añade individualmente los eventos in-app que quieras enviar a Adquant by Kenshoo y asígnalos al campo **Partner Event Identifier**.

3. Selecciona **Send Revenue** para enviar todos los parámetros, incluido el valor de ingresos (si existe en el evento).

4. Haz clic en **Save**

> 📘 **Nota Importante**
>
> * Desactivar la atribución para Google Ads evita enviar postbacks a Google Ads Partners.
> * Puedes configurar varias cuentas de Google Ads (CID) para enviar postbacks (paso 5) separando cada CID con una coma.

<div data-zendesk-anchors="setting-up-adquant-by-kenshoo=configuraci%C3%B3n-de-adquant-by-kenshoo h_01HKA1JQRK5BVGW13P72YEXZT7=configuraci%C3%B3n-de-adquant-by-kenshoo h_01HKA1JQRKGDMZHTVSPVDSV463=nota inapp-events=eventos-dentro-de-la-aplicaci%C3%B3n h_01HKA1JQRK4YNEXKAHVBYP3EC1=eventos-dentro-de-la-aplicaci%C3%B3n h_01HKA1JQRKZJJ4RXCCVSS1BG7Z=nota-importante" />
