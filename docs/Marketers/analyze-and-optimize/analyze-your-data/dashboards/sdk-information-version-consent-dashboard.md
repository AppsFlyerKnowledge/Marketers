---
title: Dashboard de información del SDK (versión y consentimiento)
metadata:
  keywords:
    - SDK Information
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2026-08-12T11:51:01Z'
  id: 115000805366
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/115000805366
---
> **De un vistazo:** vista del dashboard de las tasas de adopción del SDK y del sistema operativo (iOS, Android), así como de las métricas de consentimiento de ATT en iOS.

<div id="version-adoption-and-att-consent-dashboard" />

## Dashboard de adopción de versiones y consentimiento de ATT

Los datos del dashboard se derivan del evento af\_open (sesión) y no están relacionados con los eventos de instalación. El dashboard tiene las siguientes secciones principales: 

* Información sobre la versión del SDK; disponible para todas las plataformas (Android y  iOS)
* Métricas de consentimiento de ATT y adopción de iOS 16.1+ (que ofrece la posibilidad de disponer de datos de SKAN 4)

**Para ver el dashboard de información del SDK**:

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Información del SDK**.
2. Define el rango de fechas de actividad.   
   Las métricas mostradas se describen en las secciones siguientes.

<div id="sdk-information-ios-and-android" />

<Accordion title="Información del SDK (iOS y Android)">

A continuación se muestran las métricas de versión disponibles para las apps de iOS y Android, usando la fecha más reciente de apertura de la app (inicio)

| Usuarios por | Ejemplo |
| --- | --- |
| Versión de la aplicación | Observa la introducción de la versión de la app V1.4.28 el 20 de mayo de 2021<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| Versión del SDK | Observa la introducción del SDK V6.1.4 el 20 de mayo de 2021<br /><br />[![UsuariosPorVersionDeSDK.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| Versión del sistema operativo | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| Tipo de dispositivo | [![UsuariosPorDispositivo.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS y ATT metrics">

La versión de iOS que adoptan tus usuarios puede influir en el tipo de datos disponible. Por ejemplo, si los usuarios tienen iOS 16.1+, los datos de SKAN 4 pueden estar disponibles.

El <Anchor target="_blank" href="/marketers/es/docs/att-implications-ios-14-and-deprecation-of-lat">estado de ATT</Anchor> lo establece iOS y tu app lo reporta a AppsFlyer. Los valores posibles del estado de ATT son:

* **Autorizado**: el usuario otorgó su consentimiento explícito para que se le haga track
* **Denegado**: el usuario no aceptó explícitamente que se le hiciera track o LAT estaba activado antes de que el usuario actualizara a iOS 14+
* **No determinado**: no se mostró la solicitud de ATT o el usuario no respondió
* **Restringido**: Apple no permite que se le haga track al usuario

**Ten en cuenta:**

* Las métricas del gráfico se calculan mediante eventos únicos de apertura de la aplicación por parte de usuarios en una fecha determinada. Es decir, si un usuario no abrió la aplicación en una fecha determinada, ese usuario no se contabiliza en las métricas de esa fecha.
* iOS y ATT metrics solo incluyen los <Anchor target="_blank" href="/marketers/es/docs/att-implications-ios-14-and-deprecation-of-lat#valores-att-definidos-por-apple">valores de ATT definidos por Apple</Anchor>; no los valores adicionales definidos por AppsFlyer.
* Las métricas de la tasa de consentimiento se calculan con la fórmula: Autorizado / (Autorizado + Denegado) x 100

<div id="att-and-ios-adoption-metrics-for-ios-apps" />

#### Métricas de ATT y adopción de iOS para aplicaciones iOS

| Gráfico | Ejemplo y observaciones |
| --- | --- |
| Se abre el estado de la ATT de la aplicación | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />Se refiere a los usuarios con iOS 14+ que abren la aplicación en una fecha determinada. Esto significa que las métricas muestran el estado de ATT del usuario en la fecha determinada. |
| Consentimiento por versión de la aplicación | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| Tendencia de consentimiento | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| Tasa de adopción por parte de los usuarios de iOS 16.1 | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="version-adoption-and-att-consent-dashboard=dashboard-de-adopci%C3%B3n-de-versiones-y-consentimiento-de-att h_01HGX98Q4FRVS2B35BVT683D5W=dashboard-de-adopci%C3%B3n-de-versiones-y-consentimiento-de-att h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 att-and-ios-adoption-metrics-for-ios-apps=m%C3%A9tricas-de-att-y-adopci%C3%B3n-de-ios-para-aplicaciones-ios h_01HGX98Q4G0C4XTC1DSVP96M19=m%C3%A9tricas-de-att-y-adopci%C3%B3n-de-ios-para-aplicaciones-ios" />
