---
title: integración de deltaDNA con AppsFlyer
metadata:
  keywords:
    - deltaDNA
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-09-04T06:41:51Z'
  edited_at: '2026-09-11T00:10:42Z'
  id: 212247706
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/212247706
---
> **At a glance:** deltaDNA, partner integrado de AppsFlyer, es la plataforma líder de analítica en tiempo real y marketing para juegos móviles. La combinación de funcionalidad de datos profundos líder en el mercado, rendimiento ultraalto y un entorno flexible y abierto permite a los usuarios maximizar el engagement y el valor del ciclo de vida mediante la segmentación de jugadores, el modelado predictivo y las intervenciones dirigidas en tiempo real.

> 🚧 **Important**
>
> **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="integrating-with-deltadna" />

## Integración con deltaDNA

> 🚧 **Important**
>
> **Importante:**
>
> El userID del SDK de deltaDNA, tanto si se genera automáticamente como si lo proporciona el juego, debe establecerse como ID de usuario del cliente en el SDK de AppsFlyer para garantizar que los datos de atribución recibidos de AppsFlyer se apliquen al usuario correcto. Esto solo debe hacerse en compilaciones del juego integradas con el entorno LIVE en el lado de deltaDNA.

1. Si usas un ID de usuario propio y rellenas este ID tanto en el parámetro custom\_user\_id de AppsFlyer como en el parámetro user de deltaDNA – no es necesario implementar código adicional.
2. Si no usas un ID de usuario propio, debes tomar la propiedad userID de deltaDNA e implementarla en el SDK de AppsFlyer en el parámetro **customer\_user\_id**. El siguiente código debe implementarse después de que ambos SDK se hayan iniciado.

<Tabs>
<Tab title="Android">

```java
AppsflyerLib.getInstance().setCustomerUserId(DDNA.instance().getUserId())
```

</Tab>

<Tab title="apps de iOS,">

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = [DDNASDK sharedInstance].userID;
```

</Tab>

<Tab title="Unity">

```swift
AppsFlyer.setCustomerUserID (DDNA.Instance.UserID)
```

</Tab>
</Tabs>

Sigue las instrucciones a continuación para configurar la integración con deltaDNA

**En deltaDNA:**

1. Crea un evento AppsFlyerAttribution en deltaDNA con la herramienta Event Management

![Delta DNA 1](https://files.readme.io/e5224bbaa730d997699e1a930425946f69a2b86ef94e241b4ba6fdb9ad978c66-206781083.png)

2. Obtén la clave del entorno Live en la página Game Details del Dashboard de deltaDNA:

![Delta DNA 2](https://files.readme.io/6b28184264dfd695000e8bfae9538862a3e17ea6f9d355af0996ccf107b4e6c2-206768886.png)

**En AppsFlyer, activa o edita la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona la pestaña **Collaborate** > **Partner Integrations > Marketplace**.  
   **Para editar**: En AppsFlyer, en el menú lateral, selecciona la pestaña **Collaborate** > **Partner Integrations > Active Integrations**.
2. Busca **deltaDNA** y selecciónalo.
3. Haz clic en **Configurar integración**. Serás redirigido a la página de configuración de integración.
4. En la pestaña **Integración**, selecciona la Aplicación para la integración y activa **Activar partner**.  
   **Nota:** El conmutador debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.
5. Introduce la Enviorment\_key obtenida de la consola de deltaDNA (consulta la sección 2).
6. Establece la **opción de envío** en **Todas las fuentes de medios, incluidas las orgánicas**.
7. Haz clic en **Guardar integración**.

Una vez que hayas guardado la configuración, AppsFlyer envía los siguientes datos a deltaDNA para cada instalación orgánica y no orgánica:

* Clave del entorno
* ID de usuario
* Tiempo de instalación
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.

> 📘 **Note**
>
> **Nota:**
>
> deltaDNA rechaza los postbacks de instalación de AppsFlyer si no se ha definido ningún ID de usuario del cliente ni UserID.

<div id="viewing-the-attribution-data-in-the-deltadna-console" />

## Ver los datos de atribución en la consola de deltaDNA

Los datos de atribución recibidos de AppsFlyer se pueden usar para:

* Filtrar gráficos de medidas
* Crear dashboards personalizados y reportes
* Ejecutar análisis detallados
* Crear segmentos de jugadores personalizados para hacer targeting a los jugadores con campañas y ofertas personalizadas.

El filtro Canal de adquisición, situado en la parte superior de todos los gráficos de Measure, las matrices de retención y los predictores de LTV y retención, usa la Fuente de medios de AppsFlyer y se basa en ella.

![Delta DNA 3](https://files.readme.io/21cf4f1c8641351a1ecc200d8b95d7558b92f4daf38f49975601d996a0fcfb86-206781123.png)

Hay 8 parámetros de atribución que AppsFlyer puede enviar a deltaDNA para que los uses en tus análisis, reportes y consultas. Todos llevan el prefijo **afAttr.**   
*Por ejemplo. afAttrCampaign, afAttrAgency, afAttrMediaSource para la campaña, la agencia y la fuente de medios, respectivamente.*

Todos los parámetros de atribución se enumeran en **appsFlyerAttribution**, que se añade a tu pantalla de gestión de eventos.

![Delta DNA 4](https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png)

Úsalos para crear consultas de análisis y reportes personalizados en cualquiera de las herramientas Analyze de deltaDNA.

![Delta DNA 5](https://files.readme.io/f4b9d0320feb3990182a0c9a835a18565ba959fabf7269c45a4651506666f941-206768946.png)

<div data-zendesk-anchors="integrating-with-deltadna=integraci%C3%B3n-con-deltadna h_01H9FK6N8V597T8AY0RF0H6CZW=integraci%C3%B3n-con-deltadna viewing-the-attribution-data-in-the-deltadna-console=ver-los-datos-de-atribuci%C3%B3n-en-la-consola-de-deltadna h_01H9FK6N8W8011X3JVG2EZ66H4=ver-los-datos-de-atribuci%C3%B3n-en-la-consola-de-deltadna" />
