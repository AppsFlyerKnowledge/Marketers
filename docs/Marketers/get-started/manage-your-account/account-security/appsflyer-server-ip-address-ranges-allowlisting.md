---
title: Rangos de direcciones IP del servidor de AppsFlyer (lista de permisos)
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2026-08-12T12:04:14Z'
  id: 207447093
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/207447093
---
> **De un vistazo:** Direcciones IP de AppsFlyer utilizadas para solicitudes de API salientes.

## Rangos de direcciones IP del servidor de AppsFlyer

Las direcciones IP enumeradas están controladas por y para el uso de AppsFlyer. La lista cambia de vez en cuando de acuerdo con nuestra capacidad y los requisitos operativos. Hacemos todo lo posible por hacer cambios en la lista con poca frecuencia.

Las API de AppsFlyer brindan servicios de atribución y reportes a anunciantes y partners. Estos servicios incluyen:

* Envío de postbacks
* Envío de mensajes de Push API

Si usas dispositivos de perímetro de red, como firewalls y servidores proxy, debes pedirle a tu equipo de seguridad que te permita agregar las direcciones IP de AppsFlyer como se indica en esta <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv">lista de IP permitidas.</Anchor>

El 16 de febrero de 2022, descartamos las direcciones IP heredadas y las eliminamos de la lista de permitidos.

Las direcciones permitidas utilizan los siguientes bloques CIDR:

* [45.92.116.0/22]
* [194.28.46.0/23]

### Cargar Audiences

Si usas dispositivos de perímetro de red, como firewalls y servidores proxy, debes pedirle a tu equipo de seguridad que te permita agregar las direcciones IP de AppsFlyer como se indica en esta [lista de IP permitidas para Audiences](https://support.appsflyer.com/hc/article_attachments/16888953497617).

Aprende más sobre <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Audiences</Anchor>.

### Pull API y servidor a servidor (S2S)

Pull API y S2S no se ven afectados por las direcciones enumeradas en este artículo. Sin embargo, verifica que el dominio *\*.appsflyer.com* esté permitido y que no esté bloqueado de ninguna manera.

<div data-zendesk-anchors="appsflyer-server-ip-address-ranges=rangos-de-direcciones-ip-del-servidor-de-appsflyer uploading-audiences=cargar-audiences pull-api-and-servertoserver-s2s=pull-api-y-servidor-a-servidor-s2s" />
