---
title: Eliminando cosas en AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-08-12T12:03:45Z'
  id: 360000603117
  locale: es
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/es/articles/360000603117
---
> **En resumen:** Descubre cómo los anunciantes pueden eliminar aplicaciones para detener la atribución, eliminar fuentes de medios o borrar datos relacionados con el usuario.

<Image alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

## Elimina el historial del usuario

Algunas regulaciones de privacidad, como el GDPR o la CCPA, otorgan a los usuarios un *derecho de eliminación*.

**Escenario:** Un usuario solicita que se borren los datos relacionados con él. El GDPR requiere que esto se haga en un plazo de 30 días.

**Acción requerida:** Usa la <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">API OpenDSR</Anchor> para enviar una solicitud de eliminación.

## Deja de atribuir instalaciones a una fuente de medios

AppsFlyer recoge información de instalaciones y eventos para tus fuentes de medios configuradas. Si una fuente de medios está configurada para la atribución, se atribuyen nuevas instalaciones.

**Escenario:** Si dejas de ejecutar campañas en una fuente de medios sin clics, impresiones o instalaciones, la atribución se detiene. Sin embargo, los eventos in-app de los usuarios existentes siguen siendo registrados y atribuidos.

**Acción requerida para dejar de atribuir instalaciones a una fuente de medios:**

* **SKAN (para aplicaciones iOS):**
  1. <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#disable-skan-measurement">Desactiva la medición de SKAN</Anchor>.
  2. Para <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta ads</Anchor>, también debes eliminar las conexiones SKAN para detener el registro de datos SKAN.
* **SRN:** <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#desactivar-la-integración-de-un-partner">Desactiva la integración de partners</Anchor>.
* **No SRN:**  
  1. No SRN:  
     1. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#desactivar-la-integración-de-un-partner">Desactiva la integración de partners</Anchor>.
  3. Los clics e instalaciones entrantes desde el enlace de atribución de AppsFlyer en tus anuncios se siguen registrando y atribuyendo. Asegúrate de que los anuncios mostrados a los clientes potenciales ya no contengan una atribución de AppsFlyer.
* **Medios propios:**
  * Deja de usar enlaces personalizados relevantes de OneLink.

## Eliminar o borrar una aplicación

Tienes la opción de eliminar temporalmente una aplicación.

#### Eliminar temporalmente una aplicación

Cuando se elimina temporalmente una aplicación, se detiene la grabación de datos, la aplicación no aparece en el dashboard y se muestra atenuada en la página “Mis aplicaciones”. Sin embargo, la aplicación permanece asociada a la cuenta y puede restaurarse. Al restaurar la aplicación, se conservan los datos históricos, como la configuración de la aplicación, las agencias aprobadas y los tokens.

> 📘 **Nota:**
>
> La eliminación de una aplicación se realiza de forma individual. Sin embargo, puedes <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#gestiona-tus-aplicaciones-en-bloque-a-través-de-la-api">eliminar varias aplicaciones a través de la API</Anchor> .

**Para eliminar una aplicación:**

1. En la barra superior, haz clic en **Mis apps**.Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. Selecciona un menú de acciones de la aplicación.
3. Haz clic en **Eliminar** ***y*** luego confirma.  
   La aplicación se elimina y ya no se muestra en la lista de aplicaciones.

**Para restaurar una aplicación que fue eliminada:**

* Contacta con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsFlyer.com) para iniciar el proceso. Una vez que el CSM haya restaurado la aplicación, podrás volver a añadirla a tu cuenta.

## Transferir aplicaciones entre cuentas

Consulta esta guía para más detalles: <Anchor target="_blank" href="/marketers/es/docs/transferring-apps-between-accounts">Transferencia de aplicaciones entre cuentas</Anchor>.

## Elimina tu cuenta o cambia tu plan de suscripción

Contacta con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsFlyer.com)

<div data-zendesk-anchors="delete-user-history=elimina-el-historial-del-usuario h_01HNZ7TNZM4P5APM2B1WQ4X7S5=elimina-el-historial-del-usuario stop-attributing-installs-to-a-media-source=deja-de-atribuir-instalaciones-a-una-fuente-de-medios h_01HNZ7VPA16065PGCSZDMQZ3ZC=deja-de-atribuir-instalaciones-a-una-fuente-de-medios delete-an-app=eliminar-o-borrar-una-aplicaci%C3%B3n h_01HNZ7XKEFRNEWGQZ58T7H0KDH=eliminar-o-borrar-una-aplicaci%C3%B3n removing-an-app=eliminar-temporalmente-una-aplicaci%C3%B3n h_01J52J31FDKSPNWSD5J2V5BYTW=eliminar-temporalmente-una-aplicaci%C3%B3n h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=nota transfer-apps-between-accounts=transferir-aplicaciones-entre-cuentas h_01HNZ7ZW7ZKDSD2TTEX55PYB91=transferir-aplicaciones-entre-cuentas delete-your-account-or-downgrade-your-subscription-plan=elimina-tu-cuenta-o-cambia-tu-plan-de-suscripci%C3%B3n h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=elimina-tu-cuenta-o-cambia-tu-plan-de-suscripci%C3%B3n" />
