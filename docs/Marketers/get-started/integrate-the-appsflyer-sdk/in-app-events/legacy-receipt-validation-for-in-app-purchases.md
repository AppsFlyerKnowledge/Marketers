---
title: '[Versión anterior] Validación de recibo de compras in-app'
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
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
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-08-12T12:00:50Z'
  id: 207032106
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/207032106
---
> 🚧 **Importante:**
>
> Este artículo describe la función de validación de recibos obsoleta. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/bulletin-legacy-receipt-validation-is-deprecated">Boletín: La validación de recibos heredada está en desuso</Anchor>

> **De un vistazo:** Implementa la validación de recibos para proteger contra compras in-app fraudulentas realizadas en las tiendas de aplicaciones de iOS y Android, y asegúrate de que se haya realizado una compra in-app como se informó. **Nota**: Esta es una función heredada. Saber más sobre el nuevo mecanismo de validación de compras in-app, totalmente automático y mejorado <Anchor target="_blank" href="/marketers/es/docs/purchase-and-subscription-validation-overview">mecanismo de validación de compras in-app</Anchor>.

## Flujo de validación de recibos

El flujo de validación de recibos es el siguiente:

1. El usuario realiza una compra in-app.
2. La tienda de aplicaciones notifica a la aplicación de la compra exitosa.
3. El desarrollador de la aplicación llama a la función de validación de recibos del SDK.

   ```
   validateAndLogInAppPurchase
   ```
4. El SDK llama al servicio de validación de AppsFlyer.
5. AppsFlyer valida la compra para asegurarse de que no sea fraudulenta.
6. Al tener éxito, AppsFlyer crea internamente un evento af\_purchase regular. De lo contrario, el evento creado se marca como fraudulento (disponible a través de Protect360).
7. El servicio de validación de AppsFlyer transfiere la respuesta al SDK.
8. El SDK transfiere la respuesta de Validación de recibos a la aplicación (ya sea éxito o fallo).  
   Si la validación de recibos falla, el evento se muestra en el <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#inapp-level-blocked-reasons">reporte de raw data de eventos in-app bloqueados</Anchor> (disponible para los suscriptores de Protect360).

Para detalles sobre la implementación de la validación de recibos, consulta nuestra documentación del SDK para desarrolladores:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">apps de iOS,</Anchor>

**Notas:**

* Para iOS aplicaciones sandbox, es decir, aplicaciones que no están disponibles en la App Store, la validación de recibos requiere <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">algo de código adicional</Anchor>.
* Las compras realizadas en el entorno de sandbox se registran como eventos af\_purchase regulares, y sus ingresos se reflejan en los dashboards y reportes de AppsFlyer.
* El servicio de validación de recibos de AppsFlyer es gratuito para todos los planes de cuenta.
* Para Android, la validación de recibos puede devolver un resultado `null` y considerar que la validación ha fallado si el usuario final no tiene acceso a internet durante la compra.

> 🚧 **Importante:**
>
> Llamar a `validateAndLogInAppPurchase` también genera un evento in-app **af\_purchase**. Por lo tanto, no generes un evento af\_purchase al validar. Hacerlo resulta en eventos de ingresos duplicados.

> 📘 **Nota:**
>
> * *L*a validación de recibos heredada que se explica aquí no es compatible con *StoreKit v2*. Para la versión actual, consulta Configurar la integración con la App Store de iOS.
> * La validación de recibos para compras in-app no es compatible con tiendas de aplicaciones de Android de terceros.

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=importante receipt-validation-flow=flujo-de-validaci%C3%B3n-de-recibos 01JDSM0JDAQXH8QX8ZAXNB0ZMB=flujo-de-validaci%C3%B3n-de-recibos 01JDSM0JDT6Q3WYW9K484QHY2M=importante-1 01JDSM0JD90J3EDMVN6D6Z9J40=nota" />
