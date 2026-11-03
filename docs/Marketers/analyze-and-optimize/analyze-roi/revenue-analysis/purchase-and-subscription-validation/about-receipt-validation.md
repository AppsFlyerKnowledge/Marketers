---
title: Sobre la validación de recibos
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
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-08-22T00:01:33Z'
  id: 42136725767569
  locale: es
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/es/articles/42136725767569
---
> **At a glance:** Entiende cómo la validación de recibos mide los ingresos de las compras in-app y las suscripciones y los verifica con las tiendas de aplicaciones, asegurando una medición precisa de los ingresos.

Los anunciantes pueden usar la validación de recibos para validar y medir las compras in-app de Google Play y la App Store.

La validación básica de recibos es gratuita para todos los planes de cuenta.

> 📘 **Note**
>
> Considera usar nuestra solución de ingresos de tienda premium ROI360 para beneficiarte del cálculo de ingresos netos, cobertura completa del funnel de suscripción, manejo de reembolsos y detección y deduplicación de compras automatizadas. Para más información y una comparación entre las dos soluciones, consulta Las dos soluciones para la validación de compras y suscripciones.

## ¿Cómo funciona la validación de recibos?

El flujo de validación de recibos es el siguiente:

1. El usuario realiza una compra in-app.
2. La tienda de aplicaciones notifica a la aplicación de la compra exitosa.
3. El desarrollador de la aplicación llama al método de validación de recibos del SDK: `validateAndLogInAppPurchase`
4. El SDK llama al servicio de validación de AppsFlyer.
5. AppsFlyer valida la compra para asegurarse de que no sea fraudulenta.
6. Tras la validación exitosa, AppsFlyer registra la compra o suscripción.
7. Si la validación de recibos falla, el evento se muestra en el <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#blocked-inapp-events">Reporte de raw data de eventos in-app bloqueados</Anchor> (disponible para suscriptores de Protect360) y en la <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">Página de visualización de eventos en vivo</Anchor> con el parámetro `af_validated` establecido en `false`.
8. El servicio de validación de AppsFlyer transfiere la respuesta al SDK.
9. El SDK transfiere la respuesta de validación de recibos a la aplicación (ya sea éxito o fallo).

## Activar la validación de recibos

Para activar la validación de recibos, sigue estos pasos:

1. In AppsFlyer, from the side menu, open **Settings** and under **ROI360** select **Revenue Settings**.
2. Abre la pestaña **Compras y suscripciones**.
3. En el paso 1, **elegir tipo de producto**, selecciona **Validación de recibos**.
4. Haz clic en **Guardar y siguiente** para proceder a configurar la validación de recibos.

## Configurar la validación de recibos

Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-receipt-validation">Configurar la validación de recibos</Anchor><Anchor target="_blank" href="/marketers/es/docs/set-up-receipt-validation#3-verificar-la-implementación-del-sdk">.</Anchor>

## Eventos y parámetros de compra in-app para la validación de recibos

Todos los eventos predefinidos comparten las siguientes propiedades:

* Se procesan como eventos S2S.
* Están disponibles en los dashboards y en los reportes de raw data como eventos in-app orgánicos o no orgánicos.
* Se pueden enviar a los partners mediante postbacks.
* Se pueden utilizar en SKAN Conversion Studio.

**Los eventos registrados para las compras in-app son:**

* `af_purchase` - Producción
* `af_purchase_sandbox_sdk` - Entorno de pruebas

**Eventos de suscripción:**

* `af_ars_trial_started` - Suscripción con el período de prueba iniciado.
* `af_ars_subscriptions_started` - Suscripción de pago (sin período de prueba) iniciada, producción
* `af_ars_sandbox_sdk` - Suscripción de prueba o de pago iniciada, sandbox

**El evento incluye los siguientes parámetros predefinidos:**

* `af_product_id`
* `af_transaction_id` (Solo para iOS)
* `af_purchase_token` (Solo para Android)
* `af_revenue` (para eventos de sandbox - `af_sandbox_revenue`)
* `af_currency`
* `af_store` (app\_store / play\_store)
* `af_environment` (sandbox/producción)
* `af_validation_type` (receipt\_validation)

**Parámetros personalizados adicionales:**

* Cualquier parámetro personalizado adicional enviado en la llamada del SDK aparecerá en el campo `custom_data` en los reportes de raw data

## Cambiar de ingresos de tienda de ROI360 a validación de recibos

Si actualmente usas ingresos de tienda de ROI360 y deseas cambiar a validación de recibos, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, abre <Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" />**Configuración**altsettings-roi.pngalt y, en **ROI360**, selecciona **Configuración de ingresos**.
2. En la pestaña **Compras y suscripciones**, confirma que el **Tipo de producto** esté actualmente configurado en **ROI360**.
3. Haz clic en <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="2.07%" />.
4. Aparece un mensaje que describe el impacto de cambiar a la validación de recibos:
   * Las características de ROI360, como la atribución de reembolsos, la medición de renovación de suscripciones y los cálculos de ingresos netos, estarán deshabilitadas.
   * La precisión de los datos puede disminuir.
   * El conector de compras no es compatible con la validación de recibos.
   * Solo se admite el método SDK `validateAndLogInAppPurchase`.
5. Revisa la tabla de comparación, si es necesario, haciendo clic en '**Ver comparación de productos'**.
6. Si aún deseas continuar, haz clic en **Cambiar** para confirmar el cambio.
7. Después de cambiar, el **Tipo de producto** se actualiza a **Validación de recibos,** y la pantalla refleja la configuración simplificada.
8. Necesitarás volver a validar lo siguiente:
   * **Implementación del SDK** para el método validateAndLog

## Características y limitaciones

| Caducado | Nota |
| --- | --- |
| Tiendas compatibles | • Play Store  <br />• App Store  <br />• Para cualquier otra tienda (third-party), debes enviar manualmente los eventos de compra in-app. |
| Aplicaciones sandbox de iOS | Para aplicaciones de sandbox de iOS, es decir, aplicaciones que no están en vivo en la App Store, 'Validar la clave' siempre mostrará un estado inválido |

<div data-zendesk-anchors="how-does-receipt-validation-work=c%C3%B3mo-funciona-la-validaci%C3%B3n-de-recibos h_01KD0PBEK0M2NEZJ95QXBA1H3W=c%C3%B3mo-funciona-la-validaci%C3%B3n-de-recibos enable-receipt-validation=activar-la-validaci%C3%B3n-de-recibos h_01KD0PBEK0BZNW8YP02EW0DHH4=activar-la-validaci%C3%B3n-de-recibos set-up-receipt-validation=configurar-la-validaci%C3%B3n-de-recibos h_01KD0PBEK1GZSJQPTP0P2TJMNJ=configurar-la-validaci%C3%B3n-de-recibos inapp-purchase-events-and-parameters-for-receipt-validation=eventos-y-par%C3%A1metros-de-compra-in-app-para-la-validaci%C3%B3n-de-recibos h_01KD0PBEK1DVMRXR64EMSWT75W=eventos-y-par%C3%A1metros-de-compra-in-app-para-la-validaci%C3%B3n-de-recibos switch-from-roi360-store-revenue-to-receipt-validation=cambiar-de-ingresos-de-tienda-de-roi360-a-validaci%C3%B3n-de-recibos h_01KD0PBEK1AKE1XM2XVTCNTJ68=cambiar-de-ingresos-de-tienda-de-roi360-a-validaci%C3%B3n-de-recibos traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KD0PBEK1HQKTGM7JP2KYPJAR=caracter%C3%ADsticas-y-limitaciones" />
