---
title: Implementar la validación de la instalación de Apple App Store (iTunes)
metadata:
  keywords:
    - Validation
    - iTunes
    - Apple
    - Store Install
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-07-02T08:36:31Z'
  edited_at: '2026-08-12T11:54:50Z'
  id: 115003285626
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/115003285626
---
> **De un vistazo:** Evita la atribución de actividades fraudulentas usando el servicio de validación de instalación de Apple para cualquier instalación de iOS (tanto orgánica como no orgánica).

<div id="receipt-validation-flow" />

## Flujo de validación de recibos

El flujo de validación de recibos es el siguiente:

1. El SDK de AppsFlyer recopila los datos del recibo de instalación de Apple y los envía con el mensaje de inicio a los servidores de AppsFlyer.
2. Los servidores de AppsFlyer validan estos datos del recibo mediante el servicio de validación de instalación de Apple.
3. Si el servicio de validación de instalación de Apple responde con códigos de error que indican que la instalación no es válida:
   * La instalación se rechaza y no aparece en nuestro Dashboard
   * La ad network no recibe ningún postback ni ninguna llamada a la API para la instalación invalidada
   * La instalación y todos los eventos in-app correspondientes se registran en los Reportes de raw data de Protect360: Installs y Blocked in-app events.

<div id="notes" />

> 📘 **Notas**
>
> * La versión del SDK de iOS de AppsFlyer debe ser 6.9.2+
> * Dispositivos iOS con iOS versión 7+ son compatibles con la validación de la instalación.
> * Hay casos en los que Apple no proporciona datos del recibo de instalación y, por tanto, AppsFlyer considera que se trata de una instalación válida en términos de la Validación de la instalación de la tienda de aplicaciones. Sin embargo, Protect360 puede bloquear esta instalación por otros motivos de fraude.

<div data-zendesk-anchors="receipt-validation-flow=flujo-de-validaci%C3%B3n-de-recibos h_01JR7ST09GNZ2NTMP8D2YQ1DCH=flujo-de-validaci%C3%B3n-de-recibos h_01JR7ST09G5QFHFTWK98NCJE97=notas" />
