---
title: Envía copias de postback de SKAN directamente a AppsFlyer (iOS 15+)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2026-08-12T12:21:14Z'
  id: 4402320969617
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/4402320969617
---
> **Resumen:** Desde iOS 15, configura tu aplicación para enviar copias de postback a AppsFlyer además de enviarlas a las redes publicitarias. Haciéndolo, AppsFlyer puede validar el valor de conversión (CV) y verificar la integridad del postback. Configura el Push API de AppsFlyer para reenviar copias de postback a un punto final adicional que elijas.

> 📘 **Advertencia**
>
> A lo largo de este artículo, las referencias a **SKAN** incluyen tanto **SKAdNetwork** como el framework más reciente **AdAttributionKit (AAK)**.

## ¿Por qué enviar copias de postback a AppsFlyer?

* Obtén todos los postbacks en un solo lugar: Los postbacks contienen información crucial para los anunciantes—en particular, el CV utilizado para medir la calidad del usuario. En los postbacks, el CV no está cifrado ni forma parte de la firma del postback. Por lo tanto, el CV informado por la red publicitaria no puede ser validado y está expuesto a manipulaciones. AppsFlyer reenviará las copias de postback usando Push API a los puntos finales que definas.
  * Obligatorio para Apple Ads: el reenvío de postbacks es necesario para el reporte de AA SKAN (iOS 15+).
* Consulta las métricas de redescarga; algunas redes publicitarias no comparten datos de redescarga con AppsFlyer. La copia del postback ayuda a completar la imagen.
* Ve los datos de la aplicación del editor
* Revisa el tipo de interacción táctil

**¡Nota!** AppsFlyer aún necesita recibir los postbacks de la red publicitaria, ya que contienen datos adicionales proporcionados por esta (como el nombre de la campaña).

## Configura tu aplicación para enviar copias de postback a AppsFlyer

Según la documentación de Apple, puedes establecer un único punto final de postback de SKAN.

**Para registrar el punto final de AppsFlyer:**

1. Solicita a tu desarrollador de iOS que <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">añada AppsFlyer</Anchor> como un punto final de postback de SKAN en la próxima versión de la aplicación.
2. Envía la aplicación iOS.
3. Los postbacks se enviarán a AppsFlyer una vez que se publique la nueva versión (no desde TestFlight).
4. Puedes ver los postbacks recibidos en el <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">informe de copia de postbacks</Anchor>.

> 🚧 **¡Importante!**
>
> Las aplicaciones sin tráfico SKAN verán el siguiente mensaje incluso después de completar la configuración: Tu aplicación no está configurada para enviar copias de postback de iOS (iOS 15+) a AppsFlyer. Esto es necesario para garantizar la integridad de tu medición SKAN.

## Conceptos erróneos comunes

> 📘 **¡No creas todo lo que escuches!**
>
> ¿Estas afirmaciones son verdaderas o falsas?
>
> ![VerdaderoOFalso.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Los anunciantes todavía dependen de las redes publicitarias para obtener postbacks.
>   * Falso. El anunciante sigue dependiendo de la red publicitaria para interpretar información importante. Por ejemplo, solo la red publicitaria puede relacionar el ID de campaña SKAN con el nombre de la campaña.
> * En cuanto configuro un punto final adicional, se envían copias de todos los postbacks allí.
>   * Falso. La función de punto final adicional solo está disponible para dispositivos con iOS 15 o superior. No se envían copias de postbacks desde dispositivos con versiones anteriores.

## Características y limitaciones

Tras configurar una aplicación para enviar copias de postbacks a AppsFlyer, podría tardar un par de días en aparecer en el panel de control.

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Desarrollador de Apple</Anchor>

<div data-zendesk-anchors="h_01KDSTGH21EG5MT0KFXZ40VMW1=advertencia why-send-postback-copies-to-appsflyer=por-qu%C3%A9-enviar-copias-de-postback-a-appsflyer h_01HE7SV29Y7DNSKAAR91MJX986=por-qu%C3%A9-enviar-copias-de-postback-a-appsflyer configure-your-app-to-send-postback-copies-to-appsflyer=configura-tu-aplicaci%C3%B3n-para-enviar-copias-de-postback-a-appsflyer h_01HE7SV29YDFA5Z0X4WS87YK0Y=configura-tu-aplicaci%C3%B3n-para-enviar-copias-de-postback-a-appsflyer h_01HH9WCVH4C37ZGMRZRB7EQT6B=importante common-misconceptions=conceptos-err%C3%B3neos-comunes h_01HE7SV29YC855TGCXTCT4KHRN=conceptos-err%C3%B3neos-comunes h_01HE7SV29YMMTPH6EKYF3GQYEN=no-creas-todo-lo-que-escuches traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HHH74CC5X0T5M1F86XWMNH9V=caracter%C3%ADsticas-y-limitaciones h_01HE7SX466CMCC03K99H68ZRBN=consulte-tambi%C3%A9n" />
