---
title: Integración de Tapcart
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2026-08-12T11:59:41Z'
  id: 4411720533905
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/4411720533905
---
> **En resumen:** Utiliza Tapcart para aprovechar las capacidades de AppsFlyer en tu aplicación.

<div id="introduction" />

## Introducción

Tapcart facilita el envío de tus datos a AppsFlyer y la utilización de sus capacidades. Al desarrollar tu aplicación con Tapcart, el SDK de AppsFlyer se implementa en la aplicación de forma predeterminada. Una vez que hayas registrado tus datos a través de Tapcart, los datos, incluidos las instalaciones orgánicas y no orgánicas, se muestran en AppsFlyer.

<div id="integrating-tapcart-with-appsflyer" />

## Integrando Tapcart con AppsFlyer

El SDK de AppsFlyer te permite medir instalaciones, desinstalaciones, referencias, interacciones de usuarios con push notifications, realizar deep linking, manejar escenarios de privacidad de usuarios y más.

Sigue <Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">esta página de Tapcart</Anchor> para aprender cómo integrar Tapcart con AppsFlyer.

<div id="default-in-app-events-configured-in-the-appsflyer-sdk" />

## Eventos predeterminados en la aplicación configurados en el SDK de AppsFlyer

Después de que Tapcart haya integrado el SDK de AppsFlyer en tu aplicación, los siguientes eventos in-app se registran cada vez que un usuario los realiza:

* Registro completado
* Iniciar sesión
* Buscar
* Vista del contenido
* Vista de la lista
* Agregar a la lista de deseos
* Agregar al carrito
* Proceso de pago iniciado
* Compra
* Compra finalizada
* Eliminar del carrito
* Primera compra

<div id="enable-deep-linking-with-appsflyer" />

## Habilitar deep linking con AppsFlyer

**Para habilitar deeplinking con AppsFlyer, necesitas proporcionar a Tapcart los siguientes parámetros:**

1. **Clave de desarrollador** Identificador único y token de autenticación utilizado para configurar un SDK, cifrar sus mensajes y autenticar un cliente, una cuenta o un programa de llamada a una API.  
   Las aplicaciones en la misma cuenta generalmente tienen la misma clave de desarrollador. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/app-settings#sdk-authentication-dev-key">clave de desarrollador</Anchor>.
2. **ID de plantilla de OneLink:** Este es el ID para la plantilla de OneLink utilizada para generar tus URLs de OneLink. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">crear una plantilla de OneLink</Anchor>.  
   **Para obtener el ID de una plantilla específica:**  
   1. En AppsFlyer, ve a **Experiencias y Deep Linking** > **Enlaces personalizados de OneLink**.
   2. En el menú de **plantilla de OneLink**, selecciona la plantilla requerida.
   3. Copia el ID que se muestra en el lado derecho.  
       [![OneLink-template-id.png](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)
3. **URL de OneLink:** una URL de OneLink específica generada en AppsFlyer para una campaña específica. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">cómo generar tu OneLink</Anchor>.

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01JQ6D9NCM8K3E6GS12V2CR1CH=introducci%C3%B3n integrating-tapcart-with-appsflyer=integrando-tapcart-con-appsflyer h_01JQ6D9NCM95VJB19G2F7SDRG1=integrando-tapcart-con-appsflyer default-inapp-events-configured-in-the-appsflyer-sdk=eventos-predeterminados-en-la-aplicaci%C3%B3n-configurados-en-el-sdk-de-appsflyer h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=eventos-predeterminados-en-la-aplicaci%C3%B3n-configurados-en-el-sdk-de-appsflyer enable-deep-linking-with-appsflyer=habilitar-deep-linking-con-appsflyer h_01JQ6D9NCMC97JQ759B44M9TDJ=habilitar-deep-linking-con-appsflyer" />
