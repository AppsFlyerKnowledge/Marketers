---
title: URL largas de OneLink
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-08-22T00:33:24Z'
  id: 360017132597
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/360017132597
---
> **En resumen:** Comprende la diferencia entre las URL cortas y largas de OneLink y cómo crear URL largas fuera de AppsFlyer.

## **Los enlaces personalizados de OneLink:**

* Funcionan en todos los canales de marketing de medios para redirigir a los usuarios a: 
  * La URL/tienda de aplicaciones correcta.
  * Abrir la aplicación y luego enlazar profundamente a los usuarios a una actividad in-app específica.
* Permiten la personalización de la marca. Lo que significa que la URL tiene tu <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">dominio de marca</Anchor>, en lugar del subdominio de OneLink.
* Pueden ser URL cortas o largas:
  * Las URL cortas se crean en AppsFlyer (ya sea <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">en la interfaz de usuario</Anchor> o a través de <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">SDK</Anchor>).
  * URL largas:
    * Se pueden crear en la interfaz de usuario de AppsFlyer o fuera de AppsFlyer.
    * Contienen cualquier parámetro que desees.
    * Se pueden utilizar para generar una gran cantidad de enlaces personalizados de OneLink aplicando tus propias fórmulas simples en una hoja de cálculo.   
      **Notas**:
      * Los enlaces creados en una hoja de cálculo no son visibles (y no se pueden editar) en ninguna interfaz de usuario de AppsFlyer.
      * Este método de hoja de cálculo es diferente de <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">Realizar acciones masivas de OneLink mediante CSV</Anchor>, que crea URL cortas en masa.
    * No caducan, lo que significa que no hay límite de tiempo de vida (TTL).**Consideraciones sobre URL largas:**
    * Las URL largas son transparentes, lo que significa que todos los parámetros del enlace son visibles para el público y pueden ser potencialmente manipulados.
    * Es posible que las URL largas no quepan en navegadores, SMS u otros lugares con limitaciones de caracteres.

### URL largas de OneLink

* Actualizar los parámetros de la URL corta de OneLink en el Dashboard de AppsFlyer no cambia el ID del shortlink, por lo que no es necesario sustituir ni volver a distribuir la URL ni ningún QR code asociado, incluso si ya está en uso.
* AppsFlyer aplica sin problemas los parámetros actualizados para la atribución y el reportando, lo que garantiza que el QR code siga funcionando y refleje automáticamente los cambios.

## Procedimientos

**Para crear una URL larga de OneLink fuera de la interfaz de usuario de AppsFlyer:**

1. Crea una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>.
2. Registra la URL base de OneLink, es decir, el dominio de la plantilla de OneLink + el ID de la plantilla.  
   Ejemplo: 
   * Dominio de plantilla OneLink: `yourbrand.onelink.me`
   * ID de plantilla: `1a6f`
   * URL base de OneLink: `yourbrand.onelink.me/1a6f`
   * Ejemplo de dominio de marca: `yourbrand.com/1a6f`
3. Añade un `?` a la URL, seguido de cualquier parámetro que desees agregar.
   * Consulta la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">lista de parámetros de AppsFlyer</Anchor>.
   * Para agregar más de un parámetro, utiliza `&`.  
     Ejemplo: `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**Para obtener las URL largas de los enlaces personalizados de OneLink que crees en la interfaz de usuario de AppsFlyer:**

1. En AppsFlyer, ve a **Enlaces personalizados de OneLink**.  
   Se muestra la lista de OneLinks.  
   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Ve al enlace para el que deseas la URL larga y, en la columna **Acciones** , haz clic en **Obtener URL**.  
   Se muestra la URL larga.

<div data-zendesk-anchors="onelink-long-urls=los-enlaces-personalizados-de-onelink 01JBXQENR6QHQ1HXQQQ5NBBMKN=los-enlaces-personalizados-de-onelink advantages-of-a-short-onelink-url-compared-to-a-long-url=url-largas-de-onelink h_01JGXTFWS509NW0ESM1CZZ1KZM=url-largas-de-onelink procedures=procedimientos h_01JBXQTQ3DXPTP9BY06QKXN3NP=procedimientos" />
