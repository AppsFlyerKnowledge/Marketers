---
title: Política de control de versiones del SDK de AppsFlyer
metadata:
  keywords:
    - iOS
    - Android
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
  created_at: '2021-11-30T10:43:19Z'
  edited_at: '2026-08-12T12:02:42Z'
  id: 4412316953105
  locale: es
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/es/articles/4412316953105
---
> **Resumen:** Conoce la política de control de versiones del SDK de AppsFlyer y las versiones que mantenemos.

<div id="about-versioning" />

## Sobre el control de versiones

A lo largo de los años, AppsFlyer ha lanzado muchas versiones del SDK. Cada versión del SDK llama a una versión específica de la API. La intención de la política de control de versiones es definir cuánto tiempo durará una API para las versiones del SDK.

<div id="why-do-we-need-version-control" />

## ¿Por qué necesitamos el control de versiones?

El propósito del control de versiones incluye lo siguiente:

* Te ayuda a saber con antelación cuándo dejará de ser compatible una API para las versiones del SDK integradas en tus apps. Esto es importante porque la adopción de nuevas versiones lleva tiempo, lo que significa que tus usuarios pueden tardar un tiempo en actualizar a una versión más reciente de la app.
* Mejora la estabilidad (la compatibilidad con versiones anteriores se mantiene durante 2,5 años), lo que elimina errores inesperados al utilizar versiones muy antiguas del SDK.
* Te permite aprovechar las nuevas funciones que requieren actualizar el SDK.

<div id="sdk-version-lifecycles" />

## Ciclo de vida de las versiones del SDK

Se garantiza que una versión de la API funcionará durante 2,5 años. Cada vez que se publique una nueva versión principal o secundaria del SDK, AppsFlyer establecerá una fecha de fin del soporte para la versión secundaria anterior (incluidas todas sus versiones de parche).

**Las versiones heredadas del SDK para iOS y Android dejarán de recibir soporte siguiendo un ciclo fijo de seis meses.** Este ciclo está diseñado para avisar con antelación, lo que ayuda a los equipos a planificar con tiempo y mantener la funcionalidad completa de la app sin interrupciones. Actualizar a la versión más reciente del SDK garantiza el acceso a las funciones más recientes, una mayor estabilidad y soporte continuo.

<div id="important" />

> 🚧 **¡Importante!**
>
> Para garantizar una transición sin problemas, se recomienda a los desarrolladores de apps actualizar a la versión más reciente del SDK antes de la fecha de fin del soporte.

<div id="end-of-support-vs-deprecated" />

## Fin del soporte vs Obsoleto

AppsFlyer distingue entre las versiones del SDK **Obsoletas** y **Fin del soporte** para aclarar el nivel de soporte y el impacto en la medición de datos.

* **Versiones obsoletas:** Versiones del SDK que ya no se recomiendan debido a problemas conocidos, como errores críticos. Estas versiones aún pueden enviar datos a AppsFlyer, pero no se recomienda seguir utilizándolas. Se recomienda encarecidamente actualizar a una versión compatible.
* **Versiones de fin del soporte:** Versiones del SDK cuya medición se detiene por completo en todas las plataformas. Tanto en Android como en iOS, no se medirán las instalaciones, las sesiones ni los eventos in-app. Todo el tráfico procedente de estas versiones (salvo que AppsFlyer lo excluya específicamente) recibirá un código de estado 400. Esto significa que el SDK intentará enviar llamadas a la API con normalidad, pero los servidores de AppsFlyer las rechazarán y los datos no se procesarán.

<div id="what-happens-when-an-sdk-version-has-reached-its-end-of-support-date" />

## ¿Qué ocurre cuando una versión del SDK alcanza su fecha de fin del soporte?

Una vez que una versión del SDK alcanza su fecha de fin del soporte, los servidores de AppsFlyer dejarán de medir las instalaciones, las sesiones y los eventos in-app. Los eventos que lleguen a estos endpoints simplemente se rechazarán.

Dado que la adopción lleva tiempo, se **recomienda encarecidamente** que tu desarrollador actualice a la versión más reciente del SDK con suficiente antelación a la fecha de fin del soporte.

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/appsflyer-android-sdk-release-notes">Notas de la versión del SDK de AppsFlyer para Android</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">Notas de la versión del SDK de AppsFlyer para iOS</Anchor>

<div data-zendesk-anchors="about-versioning=sobre-el-control-de-versiones h_01HE7RHYC4YGZWF9EKK96RPMAN=sobre-el-control-de-versiones why-do-we-need-version-control=por-qu%C3%A9-necesitamos-el-control-de-versiones h_01HE7RHYC4QSVTA4ZCHTKYQSAT=por-qu%C3%A9-necesitamos-el-control-de-versiones sdk-version-lifecycles=ciclo-de-vida-de-las-versiones-del-sdk h_01HE7RHYC41QN657ZTEQ0P45GD=ciclo-de-vida-de-las-versiones-del-sdk h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=fin-del-soporte-vs-obsoleto h_01JVHEKR4MTFV0FDHMTQW00BCS=fin-del-soporte-vs-obsoleto what-happens-when-an-sdk-version-is-sunset=qu%C3%A9-ocurre-cuando-una-versi%C3%B3n-del-sdk-alcanza-su-fecha-de-fin-del-soporte h_01HE7RHYC4EVSNA2F4DQ1594DH=qu%C3%A9-ocurre-cuando-una-versi%C3%B3n-del-sdk-alcanza-su-fecha-de-fin-del-soporte h_01HE7RPQBD858TQSF27NFGGP43=consulta-tambi%C3%A9n" />
