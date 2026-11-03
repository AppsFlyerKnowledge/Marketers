---
title: '[Beta] Atribución de re-engagement multiplataforma basada en usuarios'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2026-04-05T12:40:10Z'
  edited_at: '2026-08-12T11:56:20Z'
  id: 45444294953361
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/45444294953361
---
> **Resumen:** Descubre cómo la atribución de re-engagement multiplataforma asigna crédito a las fuentes de medios que hacen que los usuarios existentes regresen a tu producto en distintas plataformas.

## Acerca de la atribución de re-engagement multiplataforma

La atribución de re-engagement multiplataforma amplía el modelo de <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-attribution">Atribución multiplataforma basada en usuarios</Anchor> para incluir la medición de cohortes de usuarios basada en el engagement publicitario más reciente, además de la fuente de adquisición original.

En la atribución de adquisición de usuarios multiplataforma, toda la actividad de un usuario se atribuye a la fuente de medios original que generó su primera conversión, utilizando un Customer User ID (CUID) persistente para vincular eventos entre dispositivos y plataformas. Esto te brinda una vista unificada del viaje de cada usuario, sin importar dónde tenga lugar.

La atribución de re-engagement multiplataforma añade una capa a este modelo. En lugar de atribuir siempre el crédito a la fuente de adquisición original, también asigna crédito a las fuentes de medios que hacen que los usuarios existentes regresen a tu producto después de un período de inactividad. Esto te permite medir el verdadero impacto de tus campañas en toda tu línea de productos, no solo en el dispositivo o plataforma donde se ejecutaron.

Así es como se relacionan ambos modelos:

|  | Atribución de adquisición de usuarios multiplataforma | Atribución de re-engagement multiplataforma |
| --- | --- | --- |
| **Qué mide** | Primera conversión y toda la actividad posterior | Reactivación de usuarios existentes después de un período de inactividad |
| **El crédito se asigna a** | Fuente de adquisición original | Fuente de medios de re-engagement (por ejemplo, Meta) |
| **Alcance** | Todos los eventos dentro de la ventana de restauración de inactividad | Solo los eventos que ocurren dentro de la ventana de re-engagement |
| **Configuración** | Configurado a nivel de línea de producto | Opcional, configurado sobre la configuración de adquisición de usuarios a nivel de línea de producto |

La atribución de re-engagement funciona junto con la adquisición de usuarios, por lo que puedes ver tanto la fuente que adquirió inicialmente a un usuario como la fuente que hizo que regresara, todo en la misma vista de reporte.

## ¿Cómo funciona la atribución de re-engagement?

Para que un evento in-app se atribuya a una fuente de medios de re-engagement, deben cumplirse todas las siguientes condiciones:

* **El re-engagement multiplataforma está habilitado:** La atribución de re-engagement debe estar habilitada para la línea de producto en tu configuración de AppsFlyer.
* **El CUID está presente:** El evento debe incluir un Customer User ID (CUID) válido que coincida con un CUID visto anteriormente en la misma línea de producto. Así es como AppsFlyer identifica a un usuario recurrente en lugar de uno nuevo.
* **La ventana de inactividad de retargeting ha finalizado:** El CUID no debe haberse visto durante al menos el período definido por la ventana de inactividad para re-engagement desde su última aparición. Si el evento ocurre dentro de esta ventana, no se considera un re-engagement y se atribuye a la fuente de adquisición original.
* **El evento ocurre dentro de la ventana de re-engagement:** Una vez que se detecta una atribución de re-engagement válida, se abre la ventana de re-engagement. Solo los eventos in-app que ocurren dentro de esta ventana se atribuyen a la fuente de medios de re-engagement. Los eventos que ocurren después de que se cierra la ventana se atribuyen a la fuente de adquisición original.

## Ejemplo de viajes de usuario con re-engagement multiplataforma

Los siguientes ejemplos muestran el mismo viaje de usuario dos veces: primero sin re-engagement multiplataforma y luego con re-engagement habilitado. Comparar ambos casos muestra exactamente cómo el re-engagement modifica la atribución.

<div id="user-journey-without-re-engagement" />

<Accordion title="Viajes de usuario sin re-engagement">

Considera un viaje de usuario en tres plataformas. Un anuncio de Google impulsa a un usuario a instalar una app móvil, donde se registra utilizando un Customer User ID. Más adelante, un anuncio de Meta impulsa al mismo usuario a visitar la plataforma web, donde inicia sesión con el mismo Customer User ID. Después de iniciar sesión, el usuario realiza dos compras en móvil: $100 y $50.

[![](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)

Como el re-engagement no está habilitado en este escenario, toda la actividad se atribuye a Google Ads, la fuente de adquisición original. Las compras de $100 y $50, así como ambas activaciones de plataforma (móvil y web), se atribuyen a Google. Meta no recibe crédito dentro de la atribución multiplataforma, aunque su anuncio impulsó la instalación web.

| Fuente de medios | Atribuciones totales | Adquisición de usuarios | Reenganches | Activaciones de plataforma | Móvil | Web | Característica |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 2 | 1 | 1 | $150 |
| Meta | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

</Accordion>

<div id="user-journey-with-re-engagement" />

<Accordion title="Viaje de usuario con re-engagement">

El viaje de usuario es idéntico al anterior. La diferencia es que la línea de producto tiene habilitado el re-engagement.

[![](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)

En este caso, la ventana de inactividad de retargeting determina si el inicio de sesión en web impulsado por Meta califica como un evento de re-engagement. La ventana comienza a contar desde la última vez que se vio el Customer User ID, que fue durante el registro en móvil. Si transcurre suficiente tiempo antes del inicio de sesión en web, es decir, si ocurre fuera de la ventana de inactividad para re-engagement, Meta recibe crédito por el re-engagement.

Una vez que Meta recibe crédito por el re-engagement, se abre la ventana de re-engagement. Cualquier evento in-app que ocurra dentro de esta ventana se atribuye a Meta. En este ejemplo, la compra de $100 ocurre dentro de la ventana de re-engagement y se atribuye a Meta. La compra de $50 ocurre fuera de la ventana de re-engagement y vuelve a atribuirse a Google.

| Fuente de medios | Atribuciones totales | Adquisición de usuarios | Reenganches | Activaciones de plataforma | Móvil | Web | Característica |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 1 | 1 | 0 | $50 |
| Meta | 1 | 0 | 1 | 1 | 0 | 1 | $100 |

</Accordion>

## Configurar la atribución de re-engagement multiplataforma

Para configurar la atribución de re-engagement multiplataforma, debes aplicar algunos ajustes específicos de re-engagement en AppsFlyer además de la configuración de tu línea de producto. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution#cómo-crear-una-línea-de-producto">Cómo crear una línea de producto</Anchor>.

## Ver resultados de atribución multiplataforma

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/end-user-events-cross-platform-report-in-data-locker">Reporte multiplataforma de eventos de usuario final en Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#crossplatform-dashboard">El dashboard multiplataforma</Anchor>

<div data-zendesk-anchors="about-cross-platform-re-engagement-attribution=acerca-de-la-atribuci%C3%B3n-de-re-engagement-multiplataforma h_01KNEVA6TAJZRZYS11Z0Q59AQJ=acerca-de-la-atribuci%C3%B3n-de-re-engagement-multiplataforma how-does-re-engagement-attribution-work=c%C3%B3mo-funciona-la-atribuci%C3%B3n-de-re-engagement h_01KNEVA6TASWZ0S6HH5QT0ZZF0=c%C3%B3mo-funciona-la-atribuci%C3%B3n-de-re-engagement a-cross-platform-re-engagement-user-journey-example=ejemplo-de-viajes-de-usuario-con-re-engagement-multiplataforma h_01KNEVA6TA5PVF5E8YWFE13QAQ=ejemplo-de-viajes-de-usuario-con-re-engagement-multiplataforma h_01KNEVA6TAPFZ48SHNN1F8Y8P5=user-journey-without-re-engagement h_01KNEVA6TA0ZRG6Z6A38JGEFAQ=user-journey-with-re-engagement set-up-cross-platform-re-engagement-attribution=configurar-la-atribuci%C3%B3n-de-re-engagement-multiplataforma h_01KNEVH8QZ2K59BJX0HZ908FXR=configurar-la-atribuci%C3%B3n-de-re-engagement-multiplataforma view-cross-platform-attribution-results=ver-resultados-de-atribuci%C3%B3n-multiplataforma h_01KNEVH8QZNV046JAF9PRADK4E=ver-resultados-de-atribuci%C3%B3n-multiplataforma h_01KNEVH8QZK4J276D8RPBH15JY=ver-tambi%C3%A9n" />
