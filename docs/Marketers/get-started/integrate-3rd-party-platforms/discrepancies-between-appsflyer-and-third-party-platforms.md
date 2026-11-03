---
title: Discrepancias entre AppsFlyer y plataformas de terceros
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-08-22T00:12:29Z'
  id: 19384888063249
  locale: es
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/es/articles/19384888063249
---
> **At a glance:** Conoce las razones de las diferencias de atribución entre AppsFlyer y plataformas de terceros.

## Visión general

Debido a las políticas de intercambio de datos de las fuentes de medios, no todos los <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">datos a nivel de usuario se comparten con plataformas de terceros</Anchor> (como plataformas de análisis y marketing). Por estas razones, pueden existir discrepancias de atribución entre los datos mostrados en plataformas de terceros y los datos de AppsFlyer.

> 📘 **Note**
>
> **Nota:**
>
> Los datos agregados y de analíticas están disponibles desde la plataforma de AppsFlyer sin limitación.

## Restricciones de postbacks en plataformas de terceros

Cuando se trata de enviar postbacks a plataformas de terceros, existen diferentes niveles de restricciones por fuente de medios. Los postbacks pueden no enviarse, enviarse sin atribución o enviarse sin restricciones.

#### Tipos de restricciones de postbacks

<div id="no-postbacks-sent" />

<Accordion title="No se envían postbacks.">

Los postbacks para eventos de raw data restringidos por fuentes de medios, como se detalla en <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">esta tabla</Anchor>, no se envían a plataformas de terceros. Esto significa que las plataformas de terceros no reciben postbacks de dichos eventos, lo que genera menor atribución en su plataforma en comparación con AppsFlyer.

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="Los postbacks se envían sin atribución">

Para eventos distintos de los eventos raw data restringidos, las siguientes ad networks requieren que los anunciantes oculten la fuente de medios al compartir postbacks con plataformas de terceros. AppsFlyer hace esto **sustituyendo la fuente de medios original por atribución orgánica**. Esto significa que los postbacks de dichos eventos enviados a plataformas de terceros no incluyen atribución a la fuente de medios, lo que lleva a una menor atribución en su plataforma en comparación con AppsFlyer:

* Amazon
* Anuncios Meta
* Pinterest
* Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>)
* Anuncios X
* Bing
* Yahoo (Oath: plataformas publicitarias / Yahoo Gemini)

> 📘 **Note**
>
> **Nota:**
>
> Para Meta ads, el comportamiento de los postbacks depende de si el anunciante aceptó los términos de Advanced Mobile Measurement (AMM):
>
> * **AMM no aceptado:** Los postbacks se envían únicamente para instalaciones <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#install-referrer-android-only">atribuidas mediante una referencia de la instalación</Anchor>. Los postbacks no incluyen datos de atribución.
> * **AMM aceptado:** Los postbacks se envían para instalaciones atribuidas mediante <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">todos los métodos de atribución</Anchor>. Sin embargo, los datos del postback no incluyen datos de atribución, lo que significa que todos los postbacks se envían a plataformas de terceros como datos sin atribución (orgánicos).

</Accordion>

<div id="regular-postbacks" />

<Accordion title="Postbacks regulares">

Todos los demás eventos que no están restringidos o cuya fuente de medios no está oculta se envían como postbacks regulares. Esto incluye eventos agregados.

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">Las restricciones de postbacks se aplican a todas las plataformas de terceros integradas con AppsFlyer, incluidas las siguientes:</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>Cloud</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>salesforce.png</td><td>marketing</td><td>MobilePush</td><td>Segmento</td><td>Spoteffects</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>Tapcart</td><td>Tealium</td><td>WebEngage</td><td>Winclap Analytics</td><td>Google Analytics 4</td><td> </td></tr></tbody></table>

## Ejemplos de discrepancias

<div id="example-1" />

<Accordion title="Restricciones de raw data en Mixpanel">

<Tabs>
<Tab title="AMM no aceptado">

> 📘 **Note**
>
> **Ejemplo 1**
>
> Un anunciante utiliza Meta ads para publicar un anuncio. También trabaja con Mixpanel para comprender mejor cómo los usuarios interactúan y se comportan dentro de su app. El anunciante comprueba para ver el número de instalaciones atribuidas a los Meta Ads en el último mes:
>
>
>
> | En AppsFlyer | En Mixpanel |
> | --- | --- |
> | El anunciante ve 100 instalaciones atribuidas a Meta Ads.<br /><br />30 de las instalaciones fueron atribuidas mediante el parámetro `gp_referrer`. Estos eventos no están restringidos y aparecen en los reportes de raw data. | El anunciante ve solo 30 instalaciones atribuidas como orgánico.<br /><br />Mixpanel no recibe postbacks para los 70 eventos restringidos. Los postbacks de las 30 instalaciones atribuidas mediante el parámetro `gp_referrer` se envían como orgánicos. |

</Tab>

<Tab title="AMM aceptado">

> 📘 **Note**
>
> **Ejemplo 1**
>
> Un anunciante utiliza Meta ads para publicar un anuncio y ha aceptado los términos de AMM. También trabaja con Mixpanel para comprender mejor cómo los usuarios interactúan y se comportan dentro de su app. El anunciante revisa la cantidad de instalaciones atribuidas a Meta ads durante el último mes:
>
>
>
> | En AppsFlyer | En Mixpanel |
> | --- | --- |
> | El anunciante ve 100 instalaciones atribuidas a Meta ads.<br /><br />El reporte de raw data de instalaciones incluirá las 100 instalaciones, no solo las atribuidas mediante el método gp\_referrer. | El anunciante ve 100 instalaciones atribuidas como orgánico.<br /><br />Debido a que AMM fue aceptado, Mixpanel recibe postbacks para las 100 instalaciones. Sin embargo, ninguno de los postbacks incluye datos de atribución, por lo que todas las instalaciones aparecen como orgánicas. |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="Restricciones de raw data en MoEngage">

> 📘 **Note**
>
> **Ejemplo 2**
>
> Un anunciante utiliza Pinterest para publicar un anuncio. También trabaja con MoEngage para obtener insights sobre engagement de clientes. El anunciante revisa cuántos eventos “Agregar a la lista de deseos” fueron atribuidos a Pinterest durante el último mes:
>
>
>
> | En AppsFlyer | En MoEngage |
> | --- | --- |
> | El anunciante ve 97 eventos "Agregar a la lista de deseos" atribuidos a Pinterest. | El anunciante no ve ningún "Agregar a la lista de deseos" eventos atribuidos a Pinterest. MoEngage no recibió postbacks de eventos click-through y view-through de Pinterest porque son eventos restringidos. |

</Accordion>

<div id="example-3" />

<Accordion title="Restricciones en Airship">

> 📘 **Note**
>
> **Ejemplo 3**
>
> Un anunciante utiliza Bing para publicar un anuncio. También trabaja con Airship para optimizar el viaje del usuario en su app móvil. El anunciante revisa cuántos eventos de compra fueron atribuidos a Bing durante el último mes:
>
>
>
> | En AppsFlyer | En Airship |
> | --- | --- |
> | El anunciante ve 35 eventos de compra atribuidos a Bing. | El anunciante ve 84 eventos de compra provenientes de fuentes orgánicas. 35 de ellos provinieron de Bing, pero no podrían saberlo porque esos eventos de compra aparecen como orgánicos. |

</Accordion>

> 📘 **Note**
>
> **Ver también**
>
> Preguntas frecuentes sobre <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#preguntas-frecuentes">restricciones de contenido raw data</Anchor>.

<div data-zendesk-anchors="Overview=visi%C3%B3n-general h_01HCVTKD7ZH991A8JF7XCNNE91=visi%C3%B3n-general postback-restrictions=restricciones-de-postbacks-en-plataformas-de-terceros h_01HDDR9JG5303R38QCAB2ZF6CW=restricciones-de-postbacks-en-plataformas-de-terceros types-of-postback-restrictions=tipos-de-restricciones-de-postbacks h_01HE05EXEFJF6SGYTKZ78FPP7Z=tipos-de-restricciones-de-postbacks h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=ejemplos-de-discrepancias h_01HCW4HS35ZTAEWPXB9JKCR725=ejemplos-de-discrepancias h_01HDDS499QJTX5RJY6CR98BDFB=example-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3" />
