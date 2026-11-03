---
title: >-
  Uso de Firebase y Google Tag Manager con AppsFlyer: Configuración de Google
  Tag Manager
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2026-08-22T00:12:13Z'
  id: 4410481509393
  locale: es
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/es/articles/4410481509393
---
> **At a glance:** Instrucciones para configurar el envío de eventos reportados a través de Firebase SDK a AppsFlyer en Google Tag Manager.

## Configuración de Google Tag Manager

Esta sección describe la configuración necesaria en la interfaz de usuario de Google Tag Manager (GTM). Todos los pasos descritos en esta sección son necesarios para que GTM envíe eventos a AppsFlyer. Sigue los pasos en el orden listado.

Los siguientes pasos son para Google Tag Manager en aplicaciones móviles. Si la interfaz de usuario que ves en tu Google Tag Manager es diferente a las capturas de pantalla en los distintos pasos, verifica lo siguiente:

1. Tu contenedor de Google Tag Manager está configurado para aplicaciones móviles.
2. El contenedor es la versión v5. Para más información, haz clic <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7003315">aquí</Anchor>.

> 📘 **Note**
>
> **Nota:**
>
> Los pasos descritos en esta sección se refieren a un evento de compra, pero son relevantes para cualquier evento que quieras enviar.

<div id="1-creating-event-parameter-variables" />

<Accordion title="1. Crear variables de los parámetros del evento">

Las variables de los parámetros del evento permiten a Google Tag Manager obtener datos del evento. Cuando se envía el evento, se pasan las variables AppsFlyer ID y Dev Key junto con él. Google Tag Manager luego evalúa su valor y así las obtiene. Los datos del evento tienen dos funciones:

1. Proporcionar a Google Tag Manager el AppsFlyer ID y Dev Key
2. Proporcionar a Google Tag Manager el nombre del evento y los parámetros del evento

<Tabs>
<Tab title="ID de dispositivo y clave de desarrollo de AppsFlyer">

Siempre que Google Tag Manager envía un evento a AppsFlyer, debe enviarlo con el AppsFlyer ID y Dev Key. La Dev Key permite a Google Tag Manager comunicarte con los servidores de AppsFlyer. El AppsFlyer ID le indica a AppsFlyer a qué usuario debe atribuir el evento.

1. En Google Tag Manager, haz clic en ***Variables*** y luego haz clic en ***New***
2. Asigna a la variable el nombre "AppsFlyer Dev Key" y haz clic en ***Configuración de la variable***
3. Selecciona ***Parámetro del evento***
4. Selecciona ***Parámetro personalizado***
5. En el campo ***Parámetro del evento*** , introduce "dev\_key" y guarda
6. Repite también el proceso para el ID de AppsFlyer: asigna a la variable el nombre "AppsFlyer Device ID" e introduce "af\_id" en el campo ***Parámetro del evento***

> 📘 **Note**
>
> **Ejemplo**
>
> A continuación se muestra una captura de pantalla de la interfaz de usuario de GTM. Muestra la configuración final del parámetro del evento:
>
> ![event_parameter_variable_dev_key.png](https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png)

> 🚧 **Important**
>
> **Importante:**
>
> Para iOS, debe configurarse un Parámetro del Evento adicional. Sigue el mismo flujo mencionado anteriormente. Crea una variable y nómbrala "Apple App ID". En el campo Parámetro del Evento, introduce "apple\_app\_id" y guarda.

El siguiente paso es crear y configurar las variables AppsFlyer ID y Dev Key dentro de la app. Este paso se explica en la sección <Anchor target="_blank" href="/marketers/es/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#configuración-de-eventos-en-la-aplicación">Envío de eventos</Anchor>.

</Tab>

<Tab title="Ingresos y precio">

La mayoría de los eventos dentro de la app requieren parámetros de valor de evento. En este caso, son los parámetros af\_revenue y af\_price, pero puedes enviar cualquier parámetro de evento. Ahora que el evento está configurado en la app, se necesitan crear las variables de ingresos y precio en Google Tag Manager. Estas variables se usan después en la etiqueta del evento de compra.

1. En Google Tag Manager, crea dos variables de Parámetro del Evento para af\_revenue y af\_price.
2. Para "af\_revenue", nombra la variable "Ingresos" y configura la ***Clave del Parámetro del Evento*** como "af\_revenue".
3. Para "af\_price", nombra la variable "Precio" y configura la ***Clave del Parámetro del Evento*** como "af\_price".

> 📘 **Note**
>
> **Ejemplo**
>
> A continuación se muestra una captura de pantalla de la interfaz de usuario de GTM. Muestra la configuración final del parámetro del evento:
>
> ![event_parameter_variable_revenue.png](https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png)

> 📘 **Note**
>
> **Nota:**
>
> El ejemplo aquí muestra cómo crear variables de parámetro del evento para los parámetros de evento de Ingresos y Precio. Puedes crear variables de parámetro del evento para cualquier tipo de parámetro del evento, de acuerdo con el evento que se envíe.

</Tab>
</Tabs>

</Accordion>

<div id="2-creating-a-trigger-for-the-purchase-event" />

<Accordion title="2. Crear un disparador para el evento de compra">

Para que Google Tag Manager sepa si el evento debe enviarse a AppsFlyer, se debe configurar un activador para el evento.

1. En Google Tag Manager, haz clic en ***Triggers*** y luego en ***New***
2. Nombra el activador como "Purchase" y haz clic en ***Trigger Configuration***
3. Elige ***Custom***
4. Elige ***Some Events***
5. En las condiciones, configura el activador para que se dispare cuando ***Event Name*** sea igual a "af\_purchase"
6. Haz clic en ***Save***

> 📘 **Note**
>
> **Ejemplo**
>
> A continuación se muestra una captura de pantalla de la interfaz de usuario de GTM. Muestra la configuración final del activador:
>
> ![trigger_purchase_event.png](https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png)

</Accordion>

<div id="3-creating-a-tag-for-the-purchase-event" />

<Accordion title="3. Creación de una etiqueta para el evento de compra">

Ahora que las variables necesarias y el activador del evento están configurados, puedes crear la etiqueta del evento de compra.

1. En Google Tag Manager, haz clic en ***Tags*** y luego en ***New***
2. Nombra la etiqueta como "Purchase" y haz clic en ***Tag Configuration***
3. Elige ***AppsFlyer***
4. En el campo ***Application ID*** , configura la variable incorporada App ID

   > 🚧 **Important**
   >
   > **Importante:**
   >
   > Para iOS, configura la variable personalizada "apple\_app\_id" en el campo ***Application ID*** .

5. En el campo ***Dev Key*** , elige la variable "AppsFlyer Dev Key"
6. En el campo ***AppsFlyer Device ID*** , elige la variable "AppsFlyer Device ID"
7. En el campo Event Name, configura la variable incorporada ***Event Name***
8. En el campo ***Event Currency*** , establece el código de tu moneda, por ejemplo, USD
9. Haz clic dos veces en ***Add Event Value***
10. Configura lo siguiente:  
    ***Key***: af\_revenue, ***Value***: elige la Variable de Parámetro del Evento "Revenue"  
    ***Key***: af\_price, ***Value***: elige la Variable de Parámetro del Evento "Price"
11. En la sección ***Triggering*** , configura el ***Firing Trigger*** como el activador de eventos "Purchase"
12. Haz clic en ***Save***

> 📘 **Note**
>
> **Ejemplo**
>
> A continuación se muestra una captura de pantalla de la interfaz de usuario de GTM. Muestra la configuración final de la etiqueta:
>
> ![purchase_tag.png](https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png)

</Accordion>

<div id="4-publishing-the-tag-manager-container" />

<Accordion title="4. Publicación del contenedor del administrador de etiquetas">

Después de cada cambio en Google Tag Manager (agregar etiquetas, etc.), debes descargar el contenedor y añadirlo a la carpeta raíz de tu aplicación:

* Android - app/src/main/assets/containers
* iOS - carpeta raíz/container

Construye e instala la aplicación en un dispositivo de prueba y revisa el registro de depuración para ver que el evento se desencadena y se envía.

</Accordion>

<div data-zendesk-anchors="google-tag-manager-setup=configuraci%C3%B3n-de-google-tag-manager h_01HE7SFG97FKSVAY5QHVHGF3GV=configuraci%C3%B3n-de-google-tag-manager h_01HE7SFG97YVYNT385MNFA9ECN=1-creating-event-parameter-variables h_01HE7SFG98XGBMTA7ZF8XSNF29=2-creating-a-trigger-for-the-purchase-event h_01HE7SFG98R4DGTRWXE247MRPK=3-creating-a-tag-for-the-purchase-event h_01HE7SFG98R2KGRRDA9TQTYD3B=4-publishing-the-tag-manager-container" />
