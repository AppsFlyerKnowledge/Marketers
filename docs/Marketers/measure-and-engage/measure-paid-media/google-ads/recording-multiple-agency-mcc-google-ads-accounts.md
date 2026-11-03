---
title: Registro de múltiples cuentas de Google Ads de agencia/MCC
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2026-08-12T12:19:19Z'
  id: 115004970386
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/115004970386
---
> **En resumen:** Configura el registro de diferentes cuentas de Google Ads para que el tráfico se atribuya correctamente.

## Introducción

El tráfico de Google Ads suele provenir de varias cuentas, como agencias especializadas en Google Ads o incluso de diferentes equipos locales dentro de la organización del propietario de la aplicación. Es importante comprender cómo configurar los registros de diferentes cuentas de Google Ads para que la atribución vaya a las partes correctas.

Este artículo cubre estos casos, desde las agencias de medición hasta el uso de MCC y también MCC de MCC.

> 📘 **Nota**
>
> Lo siguiente es aplicable **solamente** a los clientes que utilizan la nueva API de Google Ads.

Para obtener más información sobre la configuración de cuentas de agencia en Google Ads, <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies">haz clic aquí</Anchor>.

## Definiciones importantes

* **ID de enlace**: **identificador único de una aplicación móvil definido en Google Ads**.

> 📘 **Nota**
>
> Las versiones de Android e iOS de la misma aplicación requieren diferentes ID de enlace.

* **ID de cliente**: **identificador único de una cuenta de Google Ads**.  
  Cada cuenta puede anunciar varios ID de enlace, por ejemplo, para todas las aplicaciones de la empresa. Al enlazar cuentas de agencia con aplicaciones existentes en el panel de control de AppsFlyer, puedes definir hasta 10 ID de cliente.
* **MCC**: una cuenta de administrador de Google Ads (MCC, anteriormente llamada Mi Centro de Clientes) es una **herramienta de Google Ads para gestionar varias cuentas de Google Ads**.  
  Con una cuenta MCC, puedes enlazar varias cuentas para poder verlas en una sola ubicación (<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">Leer más</Anchor>).

## Configurar el registro de Google Ads

AppsFlyer puede registrar un único ID de enlace por aplicación. **Cuando varias cuentas manejan la misma aplicación, todas deben usar el mismo ID de enlace.** Esto debe configurarse en el panel de control de AppsFlyer para fines de atribución.

### Compartir el ID de enlace de Google con otra cuenta

Los propietarios de aplicaciones que tengan una sola cuenta de Google Ads o que planeen trabajar con agencias que administran tráfico de Google Ads deben usar el método que se describe a continuación.

El propietario de la aplicación puede compartir cualquier ID de enlace con cualquier otra cuenta, identificada por su ID de cliente, como se muestra en la captura a continuación. Aquí encontrarás más detalles más sobre cómo <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies#configurar-la-atribución-de-google-ads-para-agencias">compartir el ID del enlace con una agencia</Anchor>.

> 🚧 **Importante**
>
> * Si MCC es el administrador de registros para las subcuentas, no es necesario compartir el ID de enlace de MCC con las subcuentas. Sin embargo, si una subcuenta bajo el MCC es su propio administrador de registros, entonces el MCC debe compartir el ID de enlace con el administrador de registros de la subcuenta.
> * Importación de conversiones: Si el MCC es el administrador de registros, MCC es responsable de importar las conversiones de las subcuentas que controla. Sin embargo, si una subcuenta de MCC es su propio administrador de registros, esa subcuenta también debe importar las conversiones.

> 📘 **Nota:**
>
> * En el panel de control de Google Ads, haz clic en (3 puntos) >> ***Linked accounts (Cuentas enlazadas)*** >> ***Third-party app analytics details (Detalles de análisis de aplicaciones de terceros)*** [![](https://files.readme.io/63ae5d2642a8e288a0318f26263a7e484a1c9f152114fcd24aa37f4db660e027-49754322618641.png)](https://files.readme.io/63ae5d2642a8e288a0318f26263a7e484a1c9f152114fcd24aa37f4db660e027-49754322618641.png)
> * La otra cuenta debe aprobar la "participación".
> * Como resultado, la otra cuenta está autorizada para publicar campañas de Google Ads para la aplicación.

> 👍 **Consejo**
>
> AppsFlyer recomienda compartir el ID de enlace de la cuenta principal del anunciante con las otras cuentas, en lugar de generar directamente ID de enlace en esas cuentas. Esta es la opción más rápida, y también permite una fácil separación entre el anunciante y las agencias una vez que se completa el trabajo mutuo.

## MCC

Las agencias o grandes anunciantes, que administran varias cuentas de Google Ads, a menudo utilizan un MCC (Mi Centro de Clientes), que permite ver todas sus cuentas en una sola ubicación.

Durante la configuración del MCC, es posible configurar si el MCC o las subcuentas administran las conversiones.

[![MCC_1_new.png](https://files.readme.io/aa79522705c9b190d44100d48674dec763cf2d28711dcb76a3e15023543d971c-49754339000721.png)](https://files.readme.io/aa79522705c9b190d44100d48674dec763cf2d28711dcb76a3e15023543d971c-49754339000721.png)

Esta configuración se puede modificar posteriormente si es necesario.

![mmc-googleads-settings.png](https://files.readme.io/309b8e6a4771f4780b4bf7cb9b7f461a640667d5aa6e9770b4798341fa920a02-49754322623761.png)

## MCC de los MCC

[![](https://files.readme.io/f1ce5d1a2b059f8cafccd0d8665b5fb200a3af1be5a402e70ececb060b7a1626-49754322624017.png)](https://files.readme.io/f1ce5d1a2b059f8cafccd0d8665b5fb200a3af1be5a402e70ececb060b7a1626-49754322624017.png)

Los grandes anunciantes que trabajan con varias agencias pueden usar una cuenta de MCC de MCC. Similar a la cuenta estándar de MCC. Se recomienda que el MCC de nivel más alto de MCC o anunciante sea el que genere el ID de enlace. La configuración correcta de esta estructura requiere que las subcuentas seleccionen el nivel correcto de MCC (muy probablemente, el nivel más alto de MCC) como administrador de registros. Si esta es la configuración utilizada, no es necesario compartir el ID de enlace con las subcuentas y las conversiones de importación en el nivel más alto son suficientes.

> 👍 **Consejo**
>
> Para obtener información adicional sobre los MCC y las jerarquías de cuentas, consulta los enlaces a continuación:
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">Enlazar cuentas a tu administrador de cuentas</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">Visualización de la jerarquía de la cuenta de administrador</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">Trabajar con cuentas administradas</Anchor>
>
> Si tienes preguntas sobre las estructuras de las cuentas y recomendaciones, consulta con tu representante de Google.

## Abrir una campaña de Google Ads

Un MCC no puede abrir una campaña de Google Ads directamente. Más bien, esto debe hacerse a través de una subcuenta estándar de Google Ads.

Hay dos opciones para el registro de conversiones:

1. **MCC administra el registro de subcuentas**  
   Común para cuando hay diferentes equipos dentro de la misma empresa, por ejemplo, **una cuenta de Google Ads por cada región geográfica de la misma empresa**.  
   El MCC mantiene la configuración de registro (Administrador de registros) para todas sus subcuentas. Cualquier cambio en la configuración de registro se realiza solo en el nivel de MCC y todas las subcuentas lo heredan automáticamente.  
   El MCC también necesita importar las conversiones, lo que se hace una vez y cubre todas las subcuentas, y también obtener los ID de enlace compartidos para las subcuentas.
2. **Las subcuentas gestionan su propio registro**  
   Común para las cuentas que no están conectadas, excepto por una sola entidad que las atiende, por ejemplo, **una agencia que atiende a diferentes cuentas de clientes anunciantes**.  
   La importación de las conversiones, en este caso, debe realizarse con cada subcuenta por separado. AppsFlyer registra un único ID de enlace por aplicación, por lo que para el registro móvil, el MCC o el anunciante deben compartir el ID de enlace con las subcuentas.

Las conversiones en Google Ads SOLO se pueden importar después de que ocurra la primera instancia de cualquier conversión, ya sea de instalación o evento in-app.

<div data-zendesk-anchors="introduction=introducci%C3%B3n important-definitions=definiciones-importantes setting-up-google-ads-recording=configurar-el-registro-de-google-ads sharing-google-link-id-with-another-account=compartir-el-id-de-enlace-de-google-con-otra-cuenta mcc-of-mccs=mcc-de-los-mcc opening-a-google-ads-campaign=abrir-una-campa%C3%B1a-de-google-ads" />
