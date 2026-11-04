---
title: Campo de identificación de usuario del cliente (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
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
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-09-12T00:12:23Z'
  id: 207032016
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/207032016
---
> **At a glance:** El CUID te permite agrupar eventos del mismo usuario en distintos dispositivos, fuentes de medios o canales.

<div id="what-is-cuid" />

## ¿Qué es el CUID?

El ID de usuario del cliente (CUID) es un identificador de usuario único. Normalmente, el propietario de la aplicación lo genera y lo establece en el momento del registro del usuario. El CUID permite a los propietarios de aplicaciones seguir el recorrido de los usuarios en diferentes dispositivos.

<div id="example" />

> 📘 **Ejemplo**
>
> Un usuario con dos o más dispositivos tiene el mismo CUID en todas las apps. Cada vez que el usuario realiza un evento en un dispositivo móvil o de escritorio, el SDK registra el evento junto con el CUID. Esto posibilita que el anunciante combine los datos de los dispositivos en una vista integral del usuario.
>
> Algunos casos de uso:
>
> * Las compras in-app realizadas por el mismo usuario en la misma app en varios dispositivos (teléfono, tableta, TV, ordenador) se pueden unificar en una única vista.
> * Puedes compartir datos de rendimiento del usuario entre varias plataformas (escritorio, móvil, TV) para lograr una experiencia de usuario integral.

<div id="setting-the-cuid" />

## Configuración del CUID

Se recomienda establecer el CUID lo antes posible durante el flujo de inicialización del SDK para que el mayor número posible de eventos pueda asociarse a un CUID.

<Tabs>
<Tab title="Android nativo">

Una vez que el CUID esté disponible, puedes establecerlo llamando a `setCustomerUserID`. Solo puedes asociar el CUID con eventos in-app que se produzcan después de configurarlo. Por lo tanto, el evento de instalación no incluirá el CUID cuando llames a `start` antes de `setCustomerUserID`.

<div id="associate-the-cuid-with-the-install-event" />

### Asociar el CUID con el evento de instalación

Si necesitas asociar el evento de instalación al CUID, te recomendamos configurarlo antes de llamar a `start`.

**Importante:** Recuerda que establecer el CUID antes de `start` puede bloquear al SDK para que no envíe el evento de instalación y, por tanto, impedir que se produzca la atribución. Esto puede ocurrir, por ejemplo, cuando el usuario inicia la aplicación por primera vez y luego sale antes de que el SDK pueda establecer el CUID.

En Android, puedes ejecutar el método `start` y configurar el CUID desde la clase global `Application` o desde una clase `Activity` , según la implementación de la app. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#selecciona-en-qué-clase-iniciar-el-sdk">Selecciona en qué clase iniciar el SDK</Anchor>.

<div id="if-the-sdk-starts-in-the-application-class" />

#### Si el SDK se inicia en la clase Application

Si quieres asociar el CUID con el evento de instalación al iniciar desde la clase global `Application`class, asegúrate de retrasar el envío del evento de instalación usando el `waitForCustomerUserId` método. Este método pone al SDK en modo de espera hasta que se configure el CUID.

Nota: Si por algún motivo falla la configuración del CUID, el SDK permanecerá en modo de espera y no enviará ningún evento.

<div id="if-the-sdk-starts-in-an-activity-class" />

#### Si el SDK se inicia en una clase de Activity

Si quieres asociar el CUID con el evento de instalación al iniciar desde una clase `Activity` class, no tienes que retrasar el envío del evento de instalación. Simplemente llama a `setCustomerUserId` antes de llamar a `start`.

<div id="developer-instructions" />

#### Instrucciones para desarrolladores

Indica al desarrollador lo siguiente:

* Usa `waitForCustomerUserId` si el SDK se inicia en la clase global `Application`
* Enlaces para desarrolladores:
  * Si quieres asociar el CUID con el evento de instalación, consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event">aquí</Anchor>.

</Tab>

<Tab title="iOS nativo">

Utiliza el método `customerUserId` para establecer el CUID. La ubicación de `customerUserId`  en relación con el método `start` determina qué eventos puedes asociar con el CUID.

* Si llamas a `customerUserId` antes de llamar a `start`, el SDK asocia el CUID con la instalación y los siguientes eventos in-app
* Si lo llamas después de `start`, el SDK solo asocia el CUID con los eventos registrados después de configurarlo.

<div id="developer-instructions-1" />

#### Instrucciones para desarrolladores

Indica al desarrollador que consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id">Setting the Customer User ID</Anchor> en el Dev Hub.

</Tab>

<Tab title="Unity">

<div id="developer-instructions-2" />

#### Instrucciones para desarrolladores

Indica al desarrollador que consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Setting the Customer User ID</Anchor> en el Dev Hub.

</Tab>

<Tab title="React Native">

<div id="developer-instructions-3" />

#### Instrucciones para desarrolladores

Indica al desarrollador que consulte la referencia de la API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid">setCustomerUserId</Anchor> en el Dev Hub.

</Tab>

<Tab title="Web">

Para ver la guía completa de implementación, consulta <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk#6-configurar-customer-user-id">Set customer user ID</Anchor> en Integrate AppsFlyer Web SDK.

</Tab>
</Tabs>

<div id="cuid-and-privacy" />

## CUID y privacidad

AppsFlyer valora y respeta la privacidad de tus usuarios y <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">no permite la recopilación ni la transferencia de datos personales sensibles a la plataforma de AppsFlyer.</Anchor>

Para proteger la privacidad de tus usuarios, no debes diseñar el CUID de forma que contenga información que identifique directamente al usuario. Esto incluye números de seguro social o de identificación nacional.

Si el CUID contiene la dirección de correo electrónico o el número de teléfono de un usuario, debes aplicarle hash antes de enviarlo a AppsFlyer. No envíes nunca CUID sin aplicar Hashing que contengan datos personales a AppsFlyer.

<div id="see-also" />

> 📘 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reportes-del-viaje-del-usuario">Reportes de la trayectoria del usuario</Anchor> (para obtener más información sobre el CUID en los reportes de raw data)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Prácticas recomendadas por Google para evitar el envío de Información Personal Identificable (PII)</Anchor>

<div data-zendesk-anchors="what-is-cuid=qu%C3%A9-es-el-cuid h_01HAJ00DVHRSDBS4FFKM16JFER=qu%C3%A9-es-el-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=ejemplo setting-the-cuid=configuraci%C3%B3n-del-cuid h_01HAJ00DVHDGM133A72HD5JXER=configuraci%C3%B3n-del-cuid associate-the-cuid-with-the-install-event=asociar-el-cuid-con-el-evento-de-instalaci%C3%B3n h_01HAJ00DVHDE9V2MT6JQF8SAH3=asociar-el-cuid-con-el-evento-de-instalaci%C3%B3n if-the-sdk-starts-in-the-application-class=si-el-sdk-se-inicia-en-la-clase-application h_01HAJ00DVH746B6YJVF70PMZJ8=si-el-sdk-se-inicia-en-la-clase-application if-the-sdk-starts-in-an-activity-class=si-el-sdk-se-inicia-en-una-clase-de-activity h_01HAJ00DVHYZBER40RJH0GM8KF=si-el-sdk-se-inicia-en-una-clase-de-activity developer-instructions-android=instrucciones-para-desarrolladores h_01HAJ00DVHZBZCRA1VGYJY44VY=instrucciones-para-desarrolladores developer-instructions::31dbab4b=instrucciones-para-desarrolladores h_01HAJ00DVH2RV902D6G224A4QY=instrucciones-para-desarrolladores developer-instructions-unity=instrucciones-para-desarrolladores h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=instrucciones-para-desarrolladores developer-instructions-react=instrucciones-para-desarrolladores h_01M25Y3EFC7BJAYE9YEJYA4S5A=instrucciones-para-desarrolladores cuid-and-privacy=cuid-y-privacidad h_01HAJ00DVH4987JGZZVDA1NB29=cuid-y-privacidad h_01HE7RXTEPQAWV03276TDEPG0V=ver-tambi%C3%A9n" />
