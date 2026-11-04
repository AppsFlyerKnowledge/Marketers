---
title: 'Boletín: Actualización de la integración de la API de costos de Unity Ads'
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-10-20T03:55:24Z'
  id: 26078530790289
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/26078530790289
---
| **¿Qué hay de nuevo?** | AppsFlyer tiene una integración de API con Unity que nos permite obtener datos de costos. La API se actualizará pronto. Por lo tanto, debes actualizar tu integración para seguir recibiendo los datos de costos de Unity. |
| --- | --- |
| **Fecha de actualización** | Agosto 6, 2024 |
| **Lo que debes saber:** | <ul><li>Unity presenta una nueva integración de API de costos.</li><li>La antigua integración de la API de costos puede obtener datos de costos hasta su fecha de caducidad, el 1 de octubre de 2024.</li></ul> |
| **Lo que debes hacer** | Debes actualizar tus credenciales para la nueva integración de la API de costos de Unity para seguir recibiendo datos de costos después del 1 de octubre de 2024.<br /><br />Las credenciales requeridas son:<ul><li>ID principal de organización</li><li>Clave secreta de la cuenta de servicio</li><li>ID de clave de cuenta de servicio</li></ul>Sigue las instrucciones de las siguientes secciones para actualizar la integración de costos de Unity en AppsFlyer. La integración consta de 2 pasos:<ol><li>[Obtén las nuevas credenciales de Unity](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[Actualiza la integración de la API de costos de Unity introduciendo las credenciales en AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Procedimientos de integración de API de costos de Unity

La integración de la API de costos de Unity requiere dos pasos:

1. Obtén las nuevas credenciales de Unity.
2. Actualiza la integración de la API de costos de Unity introduciendo las credenciales en AppsFlyer.

Los pasos se describen en las siguientes secciones.

<div id="get-unity-credentials" />

<Accordion title="Obtén las credenciales de Unity">

Las credenciales requeridas para la integración de la API de costos de Unity son:

* ID principal de organización
* Clave secreta de la cuenta de servicio
* ID de clave de cuenta de servicio

**Nota**: Se recomienda crear una nueva cuenta de servicio de Unity para obtener la clave secreta y el ID de la clave. A continuación, proporcionamos instrucciones sobre cómo hacerlo.

**Para configurar una cuenta de servicio de Unity y obtener las credenciales necesarias para la integración de la API de costos de Unity**:

1. Inicia sesión en tu cuenta de Unity Cloud.
2. En el menú de la izquierda, ve a **Grow (Unity Ads User Acquisition)** > **Settings**.  
    [![](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)
3. Busca, copia y guarda el **Organization Core ID**.  
   ID principal de organización de ejemplo: 5773102414648
4. En el menú de la izquierda, ve a **Grow (Unity Ads User Acquisition)** > **`{}` API Management** y, en la sección **Stats API v2.0** , **haz clic en Service Account.**  
    [![](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)
5. Haz clic en **+ Nuevo** para crear una nueva cuenta de servicio.  
    [![](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)
6. En la sección **Claves** , haz clic en **+ Añadir clave** para crear una clave para la cuenta de servicio.  
    [![](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)
7. Copia y guarda el **ID de la clave** y la **clave secreta**. **Nota**: Esta es la única vez que puedes acceder a la clave secreta, ¡así que asegúrate de guardarla ahora!
   * Ejemplo de clave secreta de cuenta de servicio: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Ejemplo de ID de clave secreta de cuenta de servicio: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      [![](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)
8. En la sección **Funciones de la organización**, haz clic en **+ Administrar funciones de la organización**.  
    [![](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)
9. En **Editar funciones en la organización**, establece **Crecimiento** en **Advertise Stats API MMP Viewer**.  
    [![](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="Actualiza la integración de la API de costos de Unity en AppsFlyer">

**Para actualizar la API de costo de Unity en AppsFlyer**:

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas** y selecciona **Unity**.
2. Haz clic en **Gestionar integración**.
3. Abre la pestaña **Costo** del partner integrado.
4. Activa el interruptor **Obtener datos de costo** . Se muestran los requisitos para conectarse al partner.
5. Ingresa tus credenciales de Unity.
6. Haz clic en **Guardar costo**.
7. Haz clic en **Probar conexión**.  
   * La API está activa. AppsFlyer recopila datos del socio 6 veces al día, en promedio una vez cada cuatro horas.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data">Aprende más sobre la conexión de integraciones de costos</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=procedimientos-de-integraci%C3%B3n-de-api-de-costos-de-unity h_01J11ZP5XG6VDSQKRWASAYK4QJ=procedimientos-de-integraci%C3%B3n-de-api-de-costos-de-unity h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
