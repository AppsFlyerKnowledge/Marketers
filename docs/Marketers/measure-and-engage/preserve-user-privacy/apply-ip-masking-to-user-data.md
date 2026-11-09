---
title: Aplicar el enmascaramiento de IP a los datos del usuario
metadata:
  keywords:
    - IP masking
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
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2026-08-12T12:23:34Z'
  id: 208879066
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/208879066
---
> **En resumen:** cómo enmascarar las direcciones IP de los usuarios de la app en los Reportes de raw data de AppsFlyer y en los postbacks enviados a Partners.

<div id="ip-masking" />

## Enmascaramiento de IP

Al activar el enmascaramiento de IP:

* Las direcciones IP de los usuarios no aparecen en los Reportes de raw data ni se proporcionan mediante postbacks a Partners
* El campo de dirección IP se rellena con el valor 1.1.1.1

<div id="note" />

> 📘 **Nota:**
>
> * Las instalaciones que se produjeron antes de activar el enmascaramiento de IP no se enmascaran
> * El <Anchor target="_blank" href="/marketers/es/docs/meta-ads-aggregate-event-measurement-aem-for-ios#compartición-de-datos-de-aem">uso compartido de datos de AEM</Anchor> para anuncios de Meta no es compatible ni con eventos de servidor a servidor ni con eventos de SDK cuando el enmascaramiento de IP está activado. Esto significa que los datos no se comparten con Anuncios de Meta.

<div id="example" />

> 📄 **Ejemplo**
>
> * La configuración del enmascaramiento de IP sigue esta secuencia: desactivado, activado y, después, desactivado.
> * Tres usuarios instalan la app en fechas distintas, como se muestra en la tabla de instalación de la app
> * La siguiente tabla de enmascaramiento de IP y Reporte de raw data muestra el estado de la configuración de enmascaramiento de IP y los datos raw data relacionados en las fechas correspondientes.
>
> Instalaciones de la app:
>
>
>
> | Submotivo de fraude | ID de usuario | Dirección IP |
> | --- | --- | --- |
> | 2 de enero | Usuario\_A | 192.0.2.1 |
> | 7 de enero | Usuario\_B | 192.0.2.33 |
> | 14 de enero | Usuario\_C | 203.0.113.1 |
>
>
>
> Enmascaramiento de IP y raw data:
>
>
>
> | Fecha | Estado de la configuración de enmascaramiento de IP | Reporte de raw data |
> | --- | --- | --- |
> | 1 de enero | Desactivado | Usuario A 192.0.2.1 |
> | 2 de enero | en | Usuario\_A 192.0.2.1 |
> | 8 de enero | en | Usuario\_A 192.0.2.1  <br />Usuario\_B 1.1.1.1 |
> | 9 de enero | Desactivado | Usuario\_A 192.0.2.1  <br />Usuario\_B 1.1.1.1 |
> | 15 de enero | Desactivado | Usuario\_A 192.0.2.1  <br />Usuario\_B 1.1.1.1  <br />Usuario\_C 203.0.113.1 |

<div id="turn-on-ip-masking" />

## Activar el enmascaramiento de IP

El enmascaramiento de IP se configura por app y afecta a las instalaciones de todas las fuentes.

**Para habilitar el enmascaramiento de IP:**

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación.**
2. Desplázate hasta **Configuración avanzada**.
3. Activa **Enmascarar direcciones IP**.

<div id="ip-masking-in-raw-data-reports" />

## Enmascaramiento de IP en reportes de raw data

Cuando el enmascaramiento de IP está activado:

* Las nuevas instalaciones y los eventos in-app muestran una dirección IP de 1.1.1.1.
* Los <Anchor target="_blank" href="/marketers/es/docs/determine-user-location">parámetros relacionados con la ubicación</Anchor>, como el país y la ciudad, siguen apareciendo en los reportes de raw data.

**Ejemplo de reporte de raw data**

<Image align="center" alt="ip_masking.png" src="https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png" />

<div data-zendesk-anchors="ip-masking=enmascaramiento-de-ip h_01HA91HHADCTT7QS2K79TJEY2C=enmascaramiento-de-ip h_01HA92HF3ZYR2NBTXQ1S2AHCAA=nota h_01HA91HHAD7BCXRZW6AD9NRDBN=ejemplo enabling-ip-masking=activar-el-enmascaramiento-de-ip h_01HA91HHAEM220CE8805GFQYKR=activar-el-enmascaramiento-de-ip ip-masking-in-raw-data-reports=enmascaramiento-de-ip-en-reportes-de-raw-data h_01HA91HHAE14D6ES1ERNK93VY9=enmascaramiento-de-ip-en-reportes-de-raw-data" />
