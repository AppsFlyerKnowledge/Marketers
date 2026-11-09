---
title: >-
  Boletín: Actualiza las credenciales de la App Store para la validación de
  recibos de ROI360 para iOS
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-08-28T09:24:00Z'
  edited_at: '2026-10-20T03:54:47Z'
  id: 27880822483985
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/27880822483985
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | AppsFlyer pasará el flujo de validación de ROI360 iOS a las nuevas APIs de validación de compras in-app de Apple, ya que la API actual será eliminada.  <br />Para garantizar que tus datos de ingresos de iOS se sigan validando con precisión y en tiempo real, deberás actualizar tus credenciales de la App Store en la plataforma AppsFlyer.  <br />Si tu aplicación aún usa Apple Server Notifications Versión 1, también deberás cambiar a la Versión 2 antes de actualizar las credenciales. |
| **Fecha de actualización** | 04/02/2025 |
| **Lo que debes saber:** | Este cambio afecta a las aplicaciones que usan ROI360 para la validación de ingresos por compras y suscripciones in-app en iOS.<br />Al actualizar al nuevo flujo de validación de iOS, te beneficiarás de:<ul><li>Validación mejorada en tiempo real con la Apple Store mediante nuevos puntos de conexión de Apple.</li><li>No hay cambios en la estructura o los parámetros de los eventos in-app.</li><li>Se han actualizado las respuestas de los resultados de validación en el conector del SDK de compras de AppsFlyer, incluido un nuevo código `store_status` para las validaciones fallidas.</li><li>No se requieren cambios en la implementación de tu SDK.</li></ul>**Nota:** La validación de recibos basada en StoreKit 2 solo es compatible con las nuevas credenciales de la App Store. Asegúrate de completar la actualización si tu aplicación usa StoreKit 2 para garantizar que la validación siga funcionando.<br /><br />Apple puede cancelar la API anterior en cualquier momento, por lo que recomendamos encarecidamente actualizar tus credenciales para mantenerse a la vanguardia de cualquier posible interrupción. |
| **Lo que debes hacer** | Para completar la configuración:<ol><li>Generar clave de compra in-app desde App Store Connect.</li><li>Carga la clave nueva en la sección Configuración de ingresos de la plataforma de AppsFlyer.</li></ol>Si tu aplicación utiliza la Versión 1 de Apple Server Notifications, debes cambiar a la Versión 2 antes de actualizar tus credenciales. Verás un mensaje en la página de Configuración de ingresos si esto se aplica a tu aplicación como requisito previo.<br /><br />Sigue las instrucciones detalladas a continuación:<ul><li>[Actualiza las credenciales de la App Store para la validación del recibo de ROI360 iOS](#obtener-credenciales-ios)</li><li>[Configurar la versión 2 del Apple Server Notifications](#enviar-notificaciones-de-la-app-store-directamente-a-appsflyer)</li></ul> |

<div id="send-app-store-notifications-directly-to-appsflyer" />

<Accordion title="Configurar la versión 2 del Apple Server Notifications">

Si tu aplicación ya utilizaba la versión 1 de Apple Server Notifications, debes cambiar a la versión 2 en App Store Connect antes de actualizar tus credenciales de validación. (Si esto se aplica a tu aplicación, verás un mensaje en la página de **Configuración de ingresos**.)

**Configurar la versión 2 del Apple Server Notifications**

1. En **App Store Connect**, en la **Información de la aplicación** sección, desplázate hasta **App Store Server Notifications.**

   <Image align="center" alt="image (24).png" src="https://files.readme.io/8e9c92cdf87303b58a6b604640b4f7adb3cf56c03e57df053e9d486b89345547-33812520143505.png" width="2009px" />
2. Para la **URL del servidor de producción**, haz clic en **Editar**.
3. No cambies la URL en la casilla **URL del servidor de producción** .

   <Image align="center" alt="image (25).png" src="https://files.readme.io/fc7737793f2e7982e3e92d30dec45d7def98ef8ec6c3186ebbdf32a78f217a3d-33812683240977.png" width="1182px" />
4. En **Versión de notificaciones**, selecciona **Notificaciones de la versión 2**.
5. Haz clic en **Guardar**.
6. En la sección **App Store Server Notifications**, haz clic en **Editar** para la **URL del servidor Sandbox**.
7. Repite los pasos 3-5.

</Accordion>

<div id="get-ios-credentials" />

<Accordion title="Actualiza las credenciales de la App Store para la validación del recibo de ROI360 iOS">

Las credenciales necesarias para la integración de la API de compras in-app de iOS son las siguientes:

* Clave de compra in-app
* ID de clave
* ID del emisor

**Antes de empezar**:

* La actualización de las claves implica pasos realizados tanto en App Store Connect como en AppsFlyer. Durante la configuración, mantén abiertas las pestañas App Store Connect y AppsFlyer.
* Necesitas permisos de administrador para configurar claves en AppsFlyer.

**Para actualizar las credenciales de iOS**:

1. En App Store Connect, ve a **Usuarios y acceso** <Image alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" width="486px" />
2. Ve a **Users and Access** > **Integrations** y, en la lista de **Keys**, selecciona **In-App Purchase**.  
   <Image align="center" alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" width="532px" />
3. Haz clic en + para generar una nueva clave de In-App Purchase.  
   <Image align="center" alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" width="384px" />
4. Ingresa un nombre para tu clave de API.
5. Haz clic en **Generar**.
6. Haz clic en **Download In-App Purchase Key** junto a la clave que acabas de generar para descargarla. **Nota**: Solo puedes descargar la clave una vez.
7. En **AppsFlyer**, en el menú lateral, selecciona **Configuración** > **Configuración de ingresos**.
8. Selecciona tu app en la lista.
9. En la pestaña **Purchases & subscriptions**, haz clic en **Update keys**. <Image alt="" src="https://files.readme.io/edcb9ef1c24f58b911792e924ca69173c487261e2ef35cf1a21270251c50e586-33405937635601.png" width="549px" />
10. En **New keys**, en el campo **In-App Purchase key**, haz clic en el **Upload icon** ( <Image alt="upload-2.png" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="15px" />) para cargar el archivo p8.
11. En App Store Connect, copia el **Key ID** de la clave que acabas de generar y pégalo en la configuración de compras & suscripciones de AppsFlyer para **Key ID**. <Image alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" width="484px" />
12. En App Store Connect, copia el **Issuer ID** y pégalo en la configuración de compras & suscripciones de AppsFlyer para **Issuer ID**. **Nota**: Si el **ID del emisor** no se muestra en la parte superior de la página, crea una clave de API de App Store Connect (con cualquier nivel de acceso). Después de eso, el ID del emisor aparecerá en la parte superior de la página para la clave de compra in-app. 

    <Image align="center" alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" width="474px" />
13. En la configuración de compras y suscripciones de AppsFlyer, haz clic en **Validar claves** para asegurarte de que las claves que has introducido sean correctas.
14. Haz clic en **Actualizar claves**. Una vez actualizadas las claves, tu aplicación pasará completamente al nuevo flujo de validación de iOS de Apple.

</Accordion>

<div data-zendesk-anchors="h_01JP2XAKZABDJYB9ZQS4N3ST4Z=send-app-store-notifications-directly-to-appsflyer h_01J14M3C6WNXPJJQHVWVNFB4GS=get-ios-credentials" />
