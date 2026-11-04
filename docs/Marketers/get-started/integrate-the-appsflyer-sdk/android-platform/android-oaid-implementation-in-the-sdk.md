---
title: Implementación del OAID de Android en el SDK
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2024-06-13T19:08:40Z'
  id: 360006278797
  locale: es
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/es/articles/360006278797
---
> **En resumen:** Recopila el OAID de Android para atribuir las instalaciones de tiendas de aplicaciones Android de terceros.

<div id="about-oaid" />

## Acerca del OAID

El identificador de dispositivo anónimo abierto (OAID) es un identificador único que el usuario puede restablecer para dispositivos Android. Fue presentado por la Mobile Security Alliance (MSA), el Instituto de Investigación de la Información y las Comunicaciones de China y los fabricantes de dispositivos, como una alternativa para preservar la privacidad a los identificadores de dispositivos que no se pueden restablecer, como el IMEI.

El OAID generalmente se usa para la medición de anuncios y la atribución de instalaciones en dispositivos donde los servicios de Google Play no están disponibles (es decir, donde el ID de publicidad de Google no existe).

<span id="supported-devices"></span>El OAID se puede leer en todos los dispositivos que utilizan un SDK proporcionado por MSA, o en dispositivos Huawei que utilizan el SDK principal de Huawei Mobile Service (HMS).

<div id="integration" />

## Integración

La integración del OAID consta de 3 pasos:

1. Integración de un SDK para generar y proporcionar el OAID (ya sea el SDK de MSA o el SDK de Huawei HMS).
2. Integración del módulo de plugin de OAID de AppsFlyer.
3. Integración del SDK de AppsFlyer.

**Nota**:

* Para aplicaciones destinadas a ser utilizadas en China, se debe utilizar el SDK de MSA.
* Para aplicaciones destinadas a ser utilizadas a nivel global en dispositivos Huawei, se debe utilizar la biblioteca de Huawei HMS.

<div id="msa-sdk" />

<Accordion title="SDK de MSA">

**Para integrar y utilizar el SDK de MSA**:

1. Sigue las instrucciones en el [sitio web de MSA](http://www.msa-alliance.cn/col.jsp?id=120) para registrar tu aplicación.
   * Registrarla te permite descargar el SDK.
   * Como parte del proceso de registro, recibes un archivo de certificado que debe agregarse a la aplicación.
2. Diles a tus desarrolladores que sigan sus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">instrucciones de integración</Anchor>.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="SDK de Huawei HMS">

**Para integrar y utilizar el SDK de Huawei HMS**:

* Diles a tus desarrolladores que sigan sus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">instrucciones de integración</Anchor>.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="opting-out-of-oaid-collection" />

<Accordion title="Exclusión de la recopilación del OAID">

Una vez que se completa la integración del OAID, el SDK intenta recopilar el OAID automáticamente. Si quieres evitar la recopilación del OAID para ciertos usuarios, pide al desarrollador que utilice lo siguiente:

<Tabs>
<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor> o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Android">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor> o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="Configuración manual del OAID">

Si tu aplicación ya recopila el OAID, puedes omitir la integración del plugin de OAID de AppsFlyer y simplemente configurar el valor de OAID en el SDK de AppsFlyer manualmente, utilizando la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">API setOaidData</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=acerca-del-oaid h_01HG8PXBZS1SN3SY3AAH1EKMNP=acerca-del-oaid integration=integraci%C3%B3n h_01HG8PXBZS26P9X1TQ7J4WQNF5=integraci%C3%B3n h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=informaci%C3%B3n-adicional h_01HG8PXBZSW5HNTTDRQ7DFFF4D=informaci%C3%B3n-adicional h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
