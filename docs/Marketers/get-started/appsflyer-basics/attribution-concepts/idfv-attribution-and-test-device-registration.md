---
title: Atribución con IDFV y registro de dispositivos de prueba
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-08-15T13:44:35Z'
  edited_at: '2026-08-17T11:49:54Z'
  id: 17798709514001
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/17798709514001
---
> **At a glance:** IDFV es un identificador único que iOS asigna a las aplicaciones del mismo proveedor. Puedes usarlo para atribuir instalaciones procedentes de campañas de promoción cruzada y registrar dispositivos de prueba.

IDFV (Identifier for Vendor) es un identificador único que iOS genera al instalar la primera aplicación que posee el proveedor. Cuando se instala otra aplicación del proveedor en el mismo dispositivo, se le asigna el mismo IDFV. Si se eliminan del dispositivo todas las aplicaciones del proveedor, el IDFV también se elimina y se genera otro distinto cuando las aplicaciones del proveedor se vuelven a instalar.

Según Apple: «El ID para proveedores (IDFV) puede usarse para realizar análisis en aplicaciones del mismo proveedor de contenido. En este caso, no es necesario utilizar el [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) framework. El IDFV no puede combinarse con otros datos para rastrear a un usuario entre aplicaciones y sitios web propiedad de otras empresas. Sigues siendo plenamente responsable de garantizar que tu recopilación y uso del IDFV cumplen la legislación aplicable.»

IDFV tiene los siguientes usos en AppsFlyer:

* [Atribución de promociones cruzadas](/docs/idfv-attribution-and-test-device-registration#idfv-en-la-atribución-de-promoción-cruzada)
* [Registro de dispositivos de prueba](/docs/idfv-attribution-and-test-device-registration#idfv-para-el-registro-de-dispositivos-de-prueba)

## IDFV en la atribución de promoción cruzada

IDFV puede usarse para la coincidencia en un escenario de atribución de promoción cruzada. En este escenario, se muestra un anuncio al usuario dentro de una aplicación de tu empresa. El anuncio promociona otra aplicación que también es propiedad de tu empresa.

<div id="how-does-crosspromotion-attribution-using-idfv-work" />

<Accordion title="¿Cómo funciona la atribución de promoción cruzada con IDFV?">

1. Se muestra un anuncio de la aplicación promocionada dentro de una de las aplicaciones del proveedor. El mismo proveedor también es propietario de la aplicación promocionada.
2. Al hacer clic en el anuncio o verlo, el SDK notifica a AppsFlyer el evento de clic o de impresión correspondiente. El SDK asocia el IDFV de la aplicación **promocionadora** con el evento (el SDK recopiló automáticamente el IDFV cuando la aplicación promocionadora se inició por primera vez).
3. Después de instalar y abrir la aplicación promocionada, el SDK notifica a AppsFlyer el evento de instalación. Este evento incluye el IDFV de la **aplicación promocionada** .
4. Al recibir el evento de instalación, AppsFlyer intenta hacerlo coincidir con el engagement de clic o impresión correspondiente. Si ambos eventos comparten el mismo IDFV, el evento de instalación se atribuye a la campaña de promoción cruzada.

</Accordion>

<div id="a-few-examples-of-idfv-attribution" />

<Accordion title="Algunos ejemplos de atribución de promoción cruzada con IDFV">

La coincidencia de IDFV se utiliza para la atribución de promoción cruzada en los siguientes casos:

* **Campañas de correo electrónico y SMS propios:** Se envía un correo electrónico o un mensaje SMS a los usuarios de otras aplicaciones del mismo proveedor que la aplicación promocionada. Este mensaje incluye un enlace de atribución que contiene el IDFV recopilado del evento de instalación de la aplicación original del proveedor. A continuación, AppsFlyer hace coincidir este IDFV con el IDFV asignado al evento de instalación de la aplicación promocionada.
* **Campañas de notificaciones push:** Una notificación push activada por el SDK de una aplicación del mismo proveedor que la aplicación promocionada contiene un enlace de atribución con el IDFV integrado. AppsFlyer hace coincidir el IDFV de la notificación push con el IDFV asociado al evento de instalación de la aplicación promocionada.

</Accordion>

## IDFV para el registro de dispositivos de prueba

Los anunciantes realizan pruebas durante el proceso de onboarding de AppsFlyer para verificar que su aplicación puede registrar y enviar correctamente eventos de instalación. El IDFV actúa como identificador único que permite a AppsFlyer reconocer los dispositivos utilizados para las pruebas.

<div id="why-identify-devices-as-test-devices" />

<Accordion title="¿Por qué identificar dispositivos como dispositivos de prueba?">

AppsFlyer trata de forma diferente los eventos de instalación procedentes de dispositivos de prueba para permitir varias instalaciones de la misma aplicación. Esto suele ser necesario para realizar pruebas de integración. Para que AppsFlyer reconozca estos eventos como procedentes de dispositivos de prueba, el IDFV del dispositivo de prueba se registra en la **Test Device** página accesible a través del **User Account** menú.

</Accordion>

<div id="why-use-idfv-as-an-identifier-in-test-device-registration" />

<Accordion title="¿Por qué usar IDFV como identificador en el registro de dispositivos de prueba?">

El registro del dispositivo de prueba también puede hacerse con IDFA. Sin embargo, una aplicación de iOS no tiene acceso al IDFA cuando la aplicación no implementa App Tracking Transparency (ATT) o cuando el usuario no da su consentimiento para compartir datos personales. En estos casos, podemos usar el acceso al IDFV para identificar el dispositivo de prueba, porque no depende de ATT.

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-marketers">Atribución de promociones cruzadas para marketers</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices#cómo-registrar-tu-dispositivo-con-idfv">Cómo registrar tu dispositivo de prueba con IDFV</Anchor>

<div data-zendesk-anchors="idfv-in-crosspromotion-attribution=idfv-en-la-atribuci%C3%B3n-de-promoci%C3%B3n-cruzada h_01H9041HQ7H18541W83A72B85B=idfv-en-la-atribuci%C3%B3n-de-promoci%C3%B3n-cruzada h_01H9041HQ7JE11FTWTD0XYQWRS=how-does-crosspromotion-attribution-using-idfv-work a-few-examples-of-idfv-attribution%E2%80%A6=a-few-examples-of-idfv-attribution h_01H9041HQ7YDCTJQYBYDVJZPW0=a-few-examples-of-idfv-attribution idfv-for-test-device-registration=idfv-para-el-registro-de-dispositivos-de-prueba h_01H9041HQ8ZC679PX7HWRMG1YC=idfv-para-el-registro-de-dispositivos-de-prueba h_01H9041HQ8K76JD72VR4EXCEZB=why-identify-devices-as-test-devices h_01H9041HQ8WS1GEAY6RGV10PF5=why-use-idfv-as-an-identifier-in-test-device-registration h_01HG809S72YC5W61GGN0CE6TP1=v%C3%A9ase-tambi%C3%A9n" />
