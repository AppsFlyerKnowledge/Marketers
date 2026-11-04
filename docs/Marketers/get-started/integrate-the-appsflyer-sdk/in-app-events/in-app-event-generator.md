---
title: Generador de eventos in-app
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2026-08-12T12:00:55Z'
  id: 10457123447953
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/10457123447953
---
> **De un vistazo:** Crea automáticamente el código de la aplicación (nativo de Android e iOS, Unity) para enviar eventos in-app definiendo los nombres y el contenido de los eventos según las necesidades de tu negocio.

<div id="introduction" />

## Introducción

Los eventos in-app son una herramienta importante que permite a los **propietarios de aplicaciones medir la calidad de sus usuarios provenientes de diferentes fuentes** en función de las acciones que realizan después de instalar la aplicación. Los eventos también se utilizan a menudo para realizar campañas de marketing basadas en el costo por acción (CPA).

Sin embargo, a menudo más de una persona participa en la definición e integración de eventos in-app en las aplicaciones. Aunque el marketer/gerente de producto define el contenido del conjunto de eventos según las necesidades del negocio, suelen ser necesarios uno o más desarrolladores móviles para implementar la API de eventos in-app en sus aplicaciones.

El <Anchor target="_blank" href="https://evgen.appsflyer.com/">generador de eventos in-app</Anchor> de AppsFlyer **resuelve los desafíos inherentes a esta colaboración esencial entre el marketer y el desarrollador**.

Mediante el uso del generador de eventos in-app, los marketers pueden:

* Utilizar un **conjunto predefinido recomendado de eventos** y parámetros para su vertical.
* Agregar o eliminar eventos/parámetros, descripciones, disparadores y ejemplos predefinidos o personalizados como referencia.
* **Enviar código generado automáticamente** a sus desarrolladores móviles de Android e iOS, **ahorrando días de trabajo,** comunicación redundante y posibles errores.
* **Reutilizar su trabajo** si posteriormente actualizan eventos, agregan nuevos eventos o agregan nuevas aplicaciones.

<div id="using-the-in-app-event-generator" />

## Uso del generador de eventos in-app

**Utiliza el generador de eventos in-app para crear un conjunto de eventos para una nueva aplicación o para actualizar un conjunto existente.**

<div id="creating-a-new-event-set" />

### Creación de un nuevo conjunto de eventos

**Para crear un nuevo conjunto de eventos:**

1. Ve al <Anchor target="_blank" href="https://evgen.appsflyer.com/">generador de eventos in-app</Anchor> e introduce el nombre de tu aplicación.
2. Selecciona una vertical o importa el conjunto de eventos de una aplicación similar que se exportó previamente a un archivo JSON.
3. Agrega o elimina eventos y parámetros, de acuerdo a las necesidades de tu negocio.
4. Haz clic en el botón **`</>` Código** para ver y copiar el código generado para tus desarrolladores: Java (Android nativo), Obj-C/Swift (iOS nativo) o C# (Unity).
5. Haz clic en **Descargar .zip** para guardar el conjunto de eventos para uso futuro o para colaborar con tus desarrolladores y compañeros.

<div id="updating-an-existing-event-set" />

### Actualización de un conjunto de eventos existente

**Para actualizar un conjunto de eventos existente:**

1. Ve al <Anchor target="_blank" href="https://evgen.appsflyer.com/">generador de eventos in-app</Anchor>.
2. Importa un conjunto de eventos de tu aplicación que se exportó previamente a un archivo JSON.
3. Agrega o elimina eventos y parámetros, de acuerdo a las necesidades de tu negocio.
4. Haz clic en el botón **`</>` Código** para ver y copiar el código generado para tus desarrolladores: Java (Android nativo), Obj-C/Swift (iOS nativo) o C# (Unity).
5. Haz clic en **Descargar .zip** para guardar el conjunto de eventos para uso futuro o para colaborar con tus desarrolladores y compañeros.

<div id="adding-events" />

### Adición de eventos

**Para agregar un nuevo evento al conjunto de eventos:**

1. Haz clic en el botón **+ Evento**. El nuevo evento aparece en la parte inferior del conjunto de eventos.
2. Selecciona un evento **predefinido** de la lista de eventos sugeridos (recomendado) o haz clic en **Personalizado** para definir tu propio nombre de evento. Verifica que el nombre del evento no exista ya en el conjunto de eventos.
3. Introduce el propósito del evento, describiendo el escenario comercial.
4. Introduce la acción desencadenante del evento, explicando el momento dentro de la trayectoria del usuario en el que se debe enviar el evento. Esta explicación se agrega como comentario en el código generado para una rápida referencia por parte de los desarrolladores.
5. [Opcional] Agrega uno o más parámetros al evento.

<div id="adding-parameters" />

### Adición de parámetros

**Para agregar un nuevo parámetro al conjunto de eventos:**

1. Haz clic en el botón **+ Agregar parámetro** para el evento relevante.
2. Selecciona un parámetro **predefinido** de la lista de parámetros sugeridos (recomendado).
3. De lo contrario, haz clic en **Personalizado** para definir tu propio nombre de parámetro y pulsa **Enter**.
4. Escribe uno o más valores de parámetros típicos como referencia.
5. Para ayudar a tus desarrolladores, escribe una descripción general, un tipo de campo o la fuente correspondiente para el valor del parámetro en tu aplicación. Esto aparece como un comentario para cada parámetro del evento en el código generado.

**Nota**: <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#predefined-and-custom-events">Los nombres predefinidos</Anchor> permiten la asignación automática de eventos y parámetros a partners y es el método recomendado.

<div id="see-also" />

> 📄 **Consulta también**
>
> * Panel de control de eventos

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HE7T0ZA12E7KHS7WBQ757KF1=introducci%C3%B3n using-the-inapp-event-generator=uso-del-generador-de-eventos-in-app h_01HE7T0ZA2A1KS4NF43GRZB87X=uso-del-generador-de-eventos-in-app creating-a-new-event-set=creaci%C3%B3n-de-un-nuevo-conjunto-de-eventos h_01HE7T0ZA2KQ44P40Y028VVA4K=creaci%C3%B3n-de-un-nuevo-conjunto-de-eventos updating-an-existing-event-set=actualizaci%C3%B3n-de-un-conjunto-de-eventos-existente h_01HE7T0ZA2P2WZ07CT880ZSK0Z=actualizaci%C3%B3n-de-un-conjunto-de-eventos-existente adding-events=adici%C3%B3n-de-eventos h_01HE7T0ZA2Z3D3J014E7E0T13X=adici%C3%B3n-de-eventos adding-parameters=adici%C3%B3n-de-par%C3%A1metros h_01HE7T0ZA2KAH7N44EQ9W5BH5G=adici%C3%B3n-de-par%C3%A1metros h_01HE7T4ZR4AY2J71B3PJKJP490=consulta-tambi%C3%A9n" />
