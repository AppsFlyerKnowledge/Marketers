---
title: 'Aviso: la validación de recibos heredada está en desuso'
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T11:33:45Z'
  edited_at: '2026-10-20T03:54:26Z'
  id: 42133487071121
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/42133487071121
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | **El 7 de septiembre de 2026, AppsFlyer dejará de dar soporte al servicio backend heredado de validación de recibos.** A partir de esa fecha, cualquier aplicación que llame al método heredado `validateAndLogInAppPurchase`, independientemente de la versión del SDK, no recibirá ninguna respuesta de validación, y los eventos `af_purchase` validados y registrados por ese método dejarán de registrarse en AppsFlyer.<br /><br />Además, el método heredado se eliminará del SDK a partir de AppsFlyer SDK v7.0.0. Las aplicaciones que se actualicen a la versión v7.0.0 o posterior no podrán llamar al método heredado.<br /><br />Para seguir midiendo las compras validadas, AppsFlyer ofrece dos alternativas:<ul><li>**Validación de recibos**, una solución gratuita que valida las compras con las tiendas de aplicaciones mediante el nuevo método del SDK `validateAndLogInAppPurchase` (v2).</li><li>**ROI360 Store Revenue**, una solución premium de medición de ingresos que incluye seguimiento de reembolsos, visibilidad completa del ciclo de vida de las suscripciones y cálculo de ingresos netos.</li></ul> |
| **Fecha de entrada en vigor** | Se aplican las siguientes fechas:<ul><li>Fecha de actualización: 17 de junio de 2026</li><li>Fecha de retirada completa: 7 de septiembre de 2026</li></ul> |
| **Lo que debes saber:** | <ul><li>**Ahora es obligatorio completar el onboarding.** A diferencia de Legacy, la nueva validación de recibos solo funciona después de configurar el tipo de producto y las credenciales de la tienda en AppsFlyer. Sin esta configuración, el SDK devuelve un error.</li><li>**Los ingresos brutos sustituyen a los valores de ingresos personalizados.** La nueva validación de recibos registra los ingresos brutos que devuelve la tienda, no el valor que pasas en la llamada al SDK. Si antes pasabas un valor personalizado (por ejemplo, el valor neto después de deducir la comisión de la tienda), espera ver diferencias en los dashboards y los postbacks de partners después de la migración. Para los ingresos netos, usa ROI360 Store Revenue.</li><li>**Los dashboards y los postbacks solo usan el precio y la moneda de la respuesta de validación de la tienda.** A diferencia de Legacy, el nuevo `validateAndLogInAppPurchase` no acepta ni el precio ni la moneda en la llamada al SDK. Estos valores se extraen directamente de la respuesta de validación de la tienda. Cualquier `af_revenue` que pases como parámetro adicional se guarda en el objeto `custom_data` del evento, pero no se usa para los dashboards ni los postbacks.</li><li>**Nuevo parámetro obligatorio:** `PurchaseType`. Indica al SDK si la transacción es una compra puntual o una suscripción.</li></ul> |
| **Lo que debes hacer** | Para migrar a una de las dos soluciones (antes del 7 de septiembre de 2026), haz una de las siguientes acciones:<ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-receipt-validation">Configura la validación de recibos</Anchor> (incluye una sección para clientes que migran desde Legacy)</li><li><Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue">Configuración de Store Revenue de ROI360</Anchor></li></ul>Para más información, consulta:<ul><li><Anchor target="_blank" href="/marketers/es/docs/purchase-and-subscription-validation-overview#comparación-entre-la-validación-de-recibos-y-store-revenue-de-roi360">Una comparación lado a lado de la Validación de recibos y Store Revenue de ROI360</Anchor></li><li>Las [preguntas frecuentes](#preguntas-frecuentes) a continuación</li></ul> |

<div id="faq" />

## PREGUNTAS FRECUENTES

<div id="h_faq_01" />

<Accordion title="¿Cómo sé cuáles de mis aplicaciones siguen usando la Validación de recibos Legacy?">

Legacy no aparece como tipo de producto en la página de configuración de ingresos, así que no puedes confirmar si se usa Legacy solo desde la interfaz de usuario. Usa los siguientes métodos en conjunto:

* **Primero, revisa el raw data.** Busca eventos `af_purchase` con `event_source: SDK` y `is_receipt_validated: true`. Son posibles candidatos, pero las llamadas a `logEvent` pueden generar eventos similares, así que esto por sí solo no es concluyente.
* **Confírmalo en el código del SDK.** Si tu aplicación llama a `validateAndLogInAppPurchase` con la firma heredada, está en Legacy. La firma heredada incluye:
  * **Android:** clave de licencia, payload JSON, precio, divisa
  * **iOS:** ID de producto, precio, divisa, ID de transacción
* **Contacta con tu CSM.** Pueden confirmar cuáles de tus aplicaciones siguen en Legacy.

</Accordion>

<div id="h_faq_02" />

<Accordion title="¿Qué ocurre exactamente el 7 de septiembre de 2026?">

El servicio backend de la Validación de recibos Legacy se apaga. A partir de ese día:

* Cualquier llamada al método heredado `validateAndLogInAppPurchase` no devuelve ninguna respuesta de validación, independientemente de la versión del SDK.
* Los eventos `af_purchase` validados y registrados por ese método dejan de registrarse en AppsFlyer.
* Los dashboards, el raw data y los postbacks de partners ya no reciben datos de compra de Legacy.

Para seguir capturando compras validadas, migra a una de las alternativas compatibles antes del 7 de septiembre de 2026.

</Accordion>

<div id="h_faq_03" />

<Accordion title="¿Activar la nueva validación de recibos afectará a las versiones activas de mi aplicación que aún llaman al método heredado?">

N.º Los dos productos funcionan en paralelo hasta el 7 de septiembre de 2026. Habilitar la nueva validación de recibos en AppsFlyer no afecta a las versiones de la aplicación que siguen llamando al método heredado. Siguen funcionando como antes hasta la fecha de retirada.

</Accordion>

<div id="h_faq_04" />

<Accordion title="¿Qué ocurre con los usuarios que usan versiones antiguas de la aplicación y nunca las actualizan?">

Los usuarios que usan versiones antiguas de la aplicación seguirán generando eventos `af_purchase` validados hasta el 7 de septiembre de 2026. Para seguir obteniendo datos de compras validados, lanza la versión actualizada de tu aplicación con suficiente antelación para llegar a la mayor parte de tu base de usuarios antes de la retirada.

</Accordion>

<div id="h_faq_05" />

<Accordion title="¿Puedo cambiar más adelante de la validación de recibos a ROI360 Store Revenue?">

Sí. Ambos productos usan el mismo método del SDK `validateAndLogInAppPurchase` (v2), así que cambiar de la validación de recibos a ROI360 Store Revenue no requiere ningún cambio en el SDK ni lanzar una nueva versión de la aplicación. Para hacer el cambio, modifica el **Tipo de producto** en la página **Configuración de ingresos** y completa la configuración adicional de ROI360 (notificaciones del servidor de App Store para iOS y Google Play RTDN para Android). Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-store-revenue#cambiar-a-los-ingresos-de-tienda-de-roi360-desde-validación-de-recibos">Cambiar a ROI360 Store Revenue desde la validación de recibos</Anchor>.

Si quieres ir un paso más allá y habilitar la detección automática de compras, una cobertura completa del ciclo de vida de las suscripciones (incluidas las renovaciones, las mejoras de plan y los suscriptores existentes) y la gestión de cambios de precio de suscripciones, integra el componente del SDK **Purchase Connector**. Eso requiere una actualización de la aplicación, pero es opcional. El flujo manual `validateAndLogInAppPurchase` (v2) funciona en ROI360 Store Revenue sin él.

</Accordion>

<div id="h_faq_06" />

<Accordion title="¿Puedo omitir por completo la validación de compras de AppsFlyer?">

Sí. Puedes reportar eventos de compra in-app con la API estándar `logEvent`. Pero te perderás lo siguiente:

* La validación de recibos frente a las tiendas de aplicaciones, que filtra las compras fraudulentas
* La marca `af_validated` en los eventos: se establece en `true` cuando AppsFlyer verifica correctamente la compra con la tienda y en `false` cuando falla. Sin validación, esta marca no aparece.
* Postbacks de ingresos precisos para tus partners de UA. Sin validación, cualquier `af_revenue` que envíes se registra y se envía a las redes tal cual, sin confirmar que la compra se haya producido realmente

Por estos motivos, AppsFlyer recomienda usar la validación de recibos o ROI360 Store Revenue en lugar de omitir la validación por completo.

</Accordion>

<div id="h_faq_07" />

<Accordion title="¿Qué ocurre si el servicio de validación de Apple o Google sufre una interrupción?">

Depende del producto que uses:

* **Validación de recibos:** la devolución de llamada del SDK devuelve un código de error. Tu aplicación debe gestionar el error e implementar su propia lógica de reintento.
* **Ingresos de la tienda ROI360:** AppsFlyer reintenta la validación automáticamente una vez que el servicio de la tienda se recupera y vuelve a generar los eventos que se hayan perdido durante la ventana de la interrupción.

</Accordion>

<div id="h_faq_08" />

<Accordion title="¿Por qué cambiaron los ingresos de mi Dashboard después de la migración?">

La fuente de ingresos cambió. Legacy usaba el valor que pasabas en la llamada al SDK. La nueva Validación de recibos usa los ingresos brutos que devuelve la tienda. Si antes pasabas un valor personalizado, por ejemplo, los ingresos netos después de deducir la comisión de la tienda, tus Dashboards y los postbacks de partners reflejarán una cifra diferente después de la migración.

Si necesitas los ingresos netos, usa **ROI360 Store Revenue**. Registra tanto los ingresos brutos como los netos (brutos menos las comisiones e impuestos de la tienda).

</Accordion>

<div id="h_faq_09" />

<Accordion title="¿Qué pasa con mi valor personalizado de af_revenue ?">

Si sigues pasando el valor `af_revenue`, se conserva en el evento dentro del objeto `custom_data`. Los Dashboards y los postbacks de partners usan el valor bruto de la respuesta de la tienda, no tu valor personalizado.

</Accordion>

<div id="h_faq_10" />

<Accordion title="¿Verán mis partners los nuevos ingresos brutos en los postbacks?">

Sí. Después de la migración, los postbacks de `af_purchase` incluyen los ingresos brutos de la tienda. Si antes pasabas un valor personalizado en Legacy, tus partners verán una cifra diferente. Asegúrate de informar a tus partners de UA antes de implementar la migración, sobre todo a los partners que usan datos de ingresos para la optimización de campañas.

</Accordion>

<div id="h_faq_11" />

<Accordion title="¿Cómo cambian los nombres de los eventos después de la migración?">

Legacy generaba un único evento `af_purchase` para todos los tipos de transacción. La nueva Validación de recibos usa nombres de eventos distintos:

* Compra puntual: `af_purchase`
* Inicio de prueba: `af_ars_trial_started`
* Inicio de suscripción: `af_ars_subscription_started`
* Compra en sandbox: `af_purchase_sandbox_sdk`
* Suscripción o prueba en sandbox: `af_ars_sandbox_sdk`

Los eventos de todo el ciclo de vida de la suscripción (renovaciones, cancelaciones, reembolsos y mejoras) solo están disponibles en ROI360 Store Revenue. Para consultar la lista completa de eventos, consulta <Anchor target="_blank" href="/marketers/es/docs/about-receipt-validation">Acerca de la Validación de recibos</Anchor>.

</Accordion>

<div id="h_faq_12" />

<Accordion title="¿Puedo usar la respuesta de validación del SDK para controlar el acceso al contenido comprado?">

La nueva Validación de recibos sigue devolviendo un resultado de validación a la devolución de llamada del SDK, que puedes usar para controlar el acceso al contenido comprado. El resultado es más preciso porque se basa en los mecanismos de validación más recientes que proporcionan el Apple App Store y Google Play, por lo que la señal que recibes en la devolución de llamada es más fiable.

</Accordion>

<div id="h_faq_13" />

<Accordion title="¿Cómo distingue el nuevo método entre suscripciones y compras únicas?">

El nuevo `validateAndLogInAppPurchase` requiere un parámetro `PurchaseType` obligatorio. Configúralo como `one-time` o `subscription` en función del tipo de transacción.

</Accordion>

<div id="h_faq_14" />

<Accordion title="¿Por qué el SDK devuelve «Purchase validation is not enabled for this app in AppsFlyer»?">

Tu app ha integrado el nuevo método `validateAndLogInAppPurchase` (v2), pero el producto no está configurado en el Dashboard de AppsFlyer. Abre **Configuración > ROI360 > Configuración de ingresos > Compras & suscripciones**, selecciona **Validación de recibos** o **ROI360** y completa los pasos de configuración.

</Accordion>

<div id="h_faq_15" />

<Accordion title="¿Por qué mi nueva compilación del SDK solo registra eventos de sandbox y no af_purchase ?">

`af_purchase` solo se registra para transacciones de producción. Las transacciones de sandbox se registran como `af_purchase_sandbox_sdk`. Para generar un evento `af_purchase` real, haz la prueba a través de un flujo de producción (no TestFlight en iOS, no Licensed Tester en Android).

</Accordion>

<div data-zendesk-anchors="faq=preguntas-frecuentes how-do-i-know-which-apps-still-use-legacy=h_faq_01 what-happens-on-september-7-2026=h_faq_02 will-enabling-new-receipt-validation-affect-live-apps=h_faq_03 what-happens-to-users-on-old-app-versions=h_faq_04 can-i-switch-from-receipt-validation-to-roi360-later=h_faq_05 can-i-skip-appsflyer-purchase-validation-entirely=h_faq_06 what-happens-if-store-validation-service-has-outage=h_faq_07 why-did-my-dashboard-revenue-change-after-migration=h_faq_08 where-does-custom-af-revenue-go=h_faq_09 will-partners-see-new-gross-revenue-in-postbacks=h_faq_10 are-event-names-different-in-new-receipt-validation=h_faq_11 sdk-validation-response-for-content-gating=h_faq_12 do-i-need-to-change-anything-for-subscriptions-vs-one-time=h_faq_13 sdk-returning-purchase-validation-not-enabled=h_faq_14 new-sdk-build-only-logging-sandbox-events=h_faq_15" />
