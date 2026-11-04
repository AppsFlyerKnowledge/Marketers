---
title: Compartición avanzada de datos de Advanced Matching
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-20T03:38:32Z'
  id: 47876839961489
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/47876839961489
---
> **At a glance:** Advanced-Matching Data Sharing permite que los identificadores de usuario con Hashing, como el correo electrónico y el número de teléfono, se reenvíen de AppsFlyer a las ad network seleccionadas, lo que permite a los Partners atribuir eventos a engagement con anuncios sin un ID de dispositivo.

<div id="about-advanced-matching-data-sharing" />

## Acerca de la compartición de datos de Advanced Matching

A medida que los identificadores de dispositivo están menos disponibles, las ad network dependen cada vez más de datos propios para hacer coincidir el engagement con anuncios. La compartición de datos de Advanced Matching cubre esta carencia reenviando identificadores con hash a los Partners compatibles en un formato conforme con la privacidad.

La función es opcional y se configura por Partners. Cuando está habilitada en una red compatible, AppsFlyer reenvía identificadores con hash junto con datos de evento para instalaciones, re-engagements y eventos in-app.

> 🚧 **Important**
>
> Todos los identificadores deben estar hashed con SHA-256 antes de llegar a AppsFlyer, ya sea en el dispositivo mediante el SDK o del lado del servidor mediante la Server-to-Server (S2S) API. Los datos en texto sin formato nunca se reciben, almacenan ni reenvían, y cualquier valor que no supere la validación se descarta en el momento de la ingesta.

<div id="supported-partners" />

### Socios compatibles

Advanced-Matching Data Sharing está disponible para las siguientes redes:

| Fuente de medios | ID de partner (PID) | Campos admitidos |
| --- | --- | --- |
| Bliss Point Media | blisspointmedia\_int | Correo electrónico hashed |
| Google | googleads\_int | Correo electrónico hashed, número de teléfono hashed |
| Meta | facebook\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Meta | metweb\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed, ID de login de Facebook |
| Moloco | moloco\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Anuncios de ChatGPT | openai\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Pinterest | pinterest\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Snapchat | snapchat\_int | Correo electrónico hashed, número de teléfono hashed |
| Snapchat | snapweb\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| TikTok | tiktokglobal\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| TikTok | tiktokweb\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Reddit | reddit\_int | Correo electrónico hashed, número de teléfono hashed |
| Rokt | roktv2\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |
| Roku | rokuads\_int | Correo electrónico hashed, número de teléfono hashed |
| Smadex | smadex\_int | Correo electrónico hashed, número de teléfono hashed, nombre hashed, apellido hashed |

<div id="the-end-to-end-flow" />

## Flujo integral

Esto es lo que ocurre desde el momento en que se recupera un identificador hasta el momento en que llega a un partner:

1. La aplicación o el backend recuperan un identificador (dirección de correo electrónico, número de teléfono u otro tipo compatible).
2. El SDK de AppsFlyer normaliza y aplica hash automáticamente al identificador con SHA-256, o el servidor lo hace antes de enviarlo mediante la API S2S.
3. El SDK o el servidor envía el identificador con hash a AppsFlyer junto con el evento (instalación, reinstalación, re-engagement o evento in-app).
4. Si Advanced-Matching Data Sharing está habilitado para el partner, AppsFlyer reenvía el hash junto con la carga útil del evento.
5. El partner usa el hash para asociar el evento a un usuario conocido, lo que mejora la precisión de la atribución y la calidad de la coincidencia.

> 📘 **Note**
>
> Los identificadores con hashing solo se reenvían a los partners para los que Advanced-Matching Data Sharing está habilitado. Cuando la configuración está desactivada para un partner, no se comparte ningún dato con hash con ese partner, incluso si hay identificadores en el evento.

<div id="how-hashed-user-identifiers-reach-appsflyer" />

## Cómo llegan los identificadores de usuario con hashing a AppsFlyer

Los identificadores con hash llegan a AppsFlyer de dos formas: a través del SDK o de la API S2S. En ambos casos, solo se aceptan valores correctamente sometidos a hashing. En las secciones siguientes se describe cada método.

<div id="send-hashed-identifiers-with-the-sdk" />

<Accordion title="Enviar identificadores con hash mediante el SDK">

El SDK V7.0.1 incorpora métodos para pasar identificadores sin procesar a los SDK de AppsFlyer para Android e iOS. El SDK normaliza y aplica hash a los datos de entrada antes de enviarlos a AppsFlyer.

El SDK realiza los siguientes pasos en orden:

1. Normaliza la entrada según los requisitos de cada partner.
2. Aplica hashing al valor normalizado con SHA-256.
3. Envía solo el valor con hashing a AppsFlyer. La entrada sin procesar nunca sale del dispositivo.

El SDK rechaza los valores no válidos con un error y no los envía a AppsFlyer.

> 📘 **Note**
>
> Hay soporte para Android e iOS a partir del SDK V7.0.1.

Los siguientes métodos están disponibles en el SDK de AppsFlyer para pasar identificadores:

* `setUserEmail` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuseremail">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuseremail">iOS</Anchor>)
* `setUserFbLoginId` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfbloginid">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfbloginid">iOS</Anchor>)
* `setUserFirstName` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfirstname">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfirstname">iOS</Anchor>)
* `setUserLastName` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserlastname">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserlastname">iOS</Anchor>)
* `setUserPhone` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserphone">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserphone">iOS</Anchor>)

Para conocer los detalles de implementación, consulta los <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib">métodos del SDK de Android</Anchor> y los <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib">métodos del SDK de iOS</Anchor>.

</Accordion>

<div id="send-hashed-identifiers-with-the-s2s-api" />

<Accordion title="Envía identificadores con hash con la API S2S">

Al enviar eventos mediante la API S2S de eventos in-app, los identificadores deben normalizarse y aplicarse con hash en el servidor antes del envío. La API acepta los siguientes campos:

| Campo | Description |
| --- | --- |
| `email_hashed` | Dirección de correo electrónico con hash |
| `phone_number_hashed` | Número de teléfono con hash, solo dígitos |
| `phone_number_e164_hashed` | Número de teléfono con hash en formato E.164 |
| `first_name_hashed` | Nombre con hash |
| `last_name_hashed` | Apellido con hash |
| `fb_login_id` | ID de login de Facebook (sin hash; se transmite tal cual) |

> 🚧 **Important**
>
> Todos los campos de esta tabla (excepto `fb_login_id`) se validan con el formato SHA-256. AppsFlyer descarta silenciosamente los valores que no coinciden y no los reenvía a ningún partner. Procesa con normalidad los demás campos del evento.

</Accordion>

<div id="why-are-there-two-phone-number-fields" />

### ¿Por qué hay dos campos de número de teléfono?

Las redes comparan eventos al cotejar el hash que AppsFlyer reenvía con el hash del número de teléfono del usuario que tienen almacenado. Como el mismo número, al normalizarse en un formato diferente, genera un hash distinto, ambas partes deben aplicar el hash a partir del mismo formato para que haya coincidencia. Como las redes normalizan los números de teléfono de forma distinta y AppsFlyer recibe valores ya hasheados, deben enviarse ambas versiones para cubrir todos los partners compatibles.

* `phone_number_hashed`: para Meta y Snapchat. Formato de normalización antes de aplicar el hash: `16501234567`
* `phone_number_e164_hashed`: para Google y TikTok. Formato de normalización antes de aplicar el hash: `+16501234567`

<div id="normalize-and-hash-identifiers" />

## Normalizar y aplicar hashing a los identificadores

Normaliza el valor sin procesar exactamente como se describe a continuación; después, aplica hashing con SHA-256 y envía el resumen hexadecimal en minúsculas.

<div id="email-emailhashed" />

<Accordion title="Correo electrónico (email_hashed)">

Normaliza y aplica hash a la dirección de correo electrónico de la siguiente manera:

1. Elimina todos los espacios en blanco.
2. Convierte a minúsculas.
3. Aplica hashing con SHA-256.

**Fecha y hora del toque del contributor[n]**

`User@Example.COM` → `user@example.com` → hash SHA-256

</Accordion>

<div id="phone-number-digits-only-phonenumberhashed" />

<Accordion title="Número de teléfono, solo dígitos (phone_number_hashed)">

Use esto para Meta, Reddit, Pinterest y Snapchat. Normaliza y aplica hash al número de teléfono de la siguiente manera:

1. Añade delante el código de país.
2. Elimina todos los símbolos, letras y ceros iniciales.
3. Aplica hash con SHA-256.

**Ejemplo:**

`+1 (650) 123-4567` → `16501234567` → hashing con SHA-256

</Accordion>

<div id="phone-number-e164-phonenumbere164hashed" />

<Accordion title="Número de teléfono, E.164 (phone_number_e164_hashed)">

Use esto para Google, TikTok y Roku. Normaliza y aplica hash al número de teléfono de la siguiente manera:

1. Añade delante el código de país.
2. Elimina todos los símbolos, letras y ceros iniciales.
3. Añade el signo `+` al principio.
4. Aplica hashing con SHA-256.

**Fecha y hora del toque del contributor[n]**

`+1 (650) 123-4567` → `+16501234567` → Hashing SHA-256

</Accordion>

<div id="first-name-firstnamehashed-and-last-name-lastnamehashed" />

<Accordion title="Nombre (first_name_hashed) y apellido (last_name_hashed)">

Normaliza y aplica hash al nombre de la siguiente manera:

1. Elimina todos los espacios en blanco.
2. Convierte a minúsculas.
3. Aplica hashing con SHA-256.

</Accordion>

<div id="facebook-login-id-fbloginid" />

<Accordion title="ID de login de Facebook (fb_login_id)">

Envía el ID de login de Facebook sin procesar tal como lo proporciona el SDK de Facebook Login. Este campo no se aplica hashing.

</Accordion>

<div id="turn-on-advanced-matching-data-sharing" />

## Activa el uso compartido de datos de Advanced Matching

Advanced-Matching Data Sharing se controla por partner y por aplicación, y debe habilitarse explícitamente para cada red.

**Para activar el intercambio de datos con coincidencia avanzada:**

1. En AppsFlyer, en el menú lateral, selecciona **Collaborate > Active Integrations**.
2. Busque al socio y selecciónelo.
3. Activa **Uso compartido de datos de Advanced Matching**.
4. Haz clic en **Guardar integración**.

Cuando el uso compartido de datos de Advanced Matching está activado, cualquier evento que incluya uno o más campos de identificador compatibles reenviará esos campos al partner.

> 📘 **Note**
>
> Desactivar el uso compartido de datos de Advanced Matching detiene inmediatamente el uso compartido de datos con Hashing con ese partner. No afecta a otros ajustes de integración, incluidos los postbacks y los datos de eventos.

<div id="privacy-and-data-handling" />

## Privacidad y tratamiento de datos

Cuando el uso compartido de datos de Advanced Matching está activado para un partner, AppsFlyer empieza a reenviar a esa red identificadores de usuario con Hashing junto con los datos de eventos. Antes de activarlo, confirma lo siguiente:

* Existe una base legal (conforme a las leyes de privacidad aplicables, como el Reglamento general de protección de datos (RGPD) o la California Consumer Privacy Act (CCPA)) para compartir estos datos con el partner.
* Has actualizado tu política de privacidad y, cuando es necesario, has obtenido el consentimiento del usuario.
* Tus prácticas de uso compartido de datos se ajustan a los términos del partner.

> 🚧 **Important**
>
> AppsFlyer no procesa ni almacena información de identificación personal (PII) en texto sin formato. Todos los campos de ID se validan en la ingesta: los valores que no se ajustan al formato SHA-256 se descartan y nunca se reenvían a ningún Partner.

<div id="faq" />

## Preguntas frecuentes

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<Accordion title="¿Es Advanced-Matching Data Sharing lo mismo que la función de correo electrónico y teléfono con hash de las audiencias?">

N.º Son mecanismos distintos. Las audiencias crean listas de Usuario para Ad Targeting. Advanced-Matching Data Sharing reenvía identificadores con hash junto con eventos individuales para mejorar las tasas de coincidencia a nivel de Partner. AppsFlyer tiene previsto consolidar ambos métodos y usar el nuevo método de recuperación de datos tanto para Advanced-Matching Data Sharing como para audiencias.

</Accordion>

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<Accordion title="¿Qué ocurre si envío un valor con hash no válido?">

AppsFlyer elimina el campo durante la ingesta y no lo reenvía a ningún partner. Procesa con normalidad los demás campos del evento.

</Accordion>

<div id="do-i-need-to-send-all-supported-fields" />

<Accordion title="¿Tengo que enviar todos los campos compatibles?">

N.º Solo es necesario incluir los identificadores disponibles y relevantes para los Partners configurados. Los campos que faltan no se reenvían.

</Accordion>

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<Accordion title="¿Mejorará Advanced-Matching Data Sharing la Atribución de instalación?">

La mayoría de los partners no usan correo electrónico con hash ni teléfono con hash para la correspondencia de instalación, re-engagement o reinstalación. El envío de estos campos ayuda sobre todo a que los partners hagan una mejor correspondencia de los eventos in-app por su parte. No afecta a la atribución de AppsFlyer.

</Accordion>

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<Accordion title="¿Recibe AppsFlyer alguna vez identificadores de usuario en texto sin formato?">

N.º Los identificadores siempre se someten a hashing antes de llegar a AppsFlyer, ya sea en el dispositivo a través del SDK o del lado del servidor a través de la API S2S. AppsFlyer solo acepta valores con hash.

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=acerca-de-la-compartici%C3%B3n-de-datos-de-advanced-matching h_01KVFJHWK1TYAPPMZDYFAP0RX0=acerca-de-la-compartici%C3%B3n-de-datos-de-advanced-matching supported-partners=socios-compatibles h_01KVFJHWK1VTJZH53FKNE8NZ59=socios-compatibles the-endtoend-flow=flujo-integral h_01KVFJHWK1JQ7J838YNDTYDD4A=flujo-integral how-hashed-user-identifiers-reach-appsflyer=c%C3%B3mo-llegan-los-identificadores-de-usuario-con-hashing-a-appsflyer h_01KVFJHWK197KW8YBQ1NBD9XT1=c%C3%B3mo-llegan-los-identificadores-de-usuario-con-hashing-a-appsflyer h_01M4ZE5P7QWCWP3FMXPM572R3R=send-hashed-identifiers-with-the-sdk h_01M4ZE5P7Q6W3G4JPQKRSSWSX6=send-hashed-identifiers-with-the-s2s-api h_why-two-phone-fields=por-qu%C3%A9-hay-dos-campos-de-n%C3%BAmero-de-tel%C3%A9fono why-are-there-two-phone-number-fields=por-qu%C3%A9-hay-dos-campos-de-n%C3%BAmero-de-tel%C3%A9fono normalize-and-hash-identifiers=normalizar-y-aplicar-hashing-a-los-identificadores h_01KVFJHWK16KQ1X1WFTTTFFND3=normalizar-y-aplicar-hashing-a-los-identificadores h_01M4ZE5P7Q0NJXDVM5MP0S2SKC=email-emailhashed h_01M4ZE5P7QDR4PVS9XZ68J6KW5=phone-number-digits-only-phonenumberhashed h_01M4ZE5P7Q2Z4APXNAWVJ8FES9=phone-number-e164-phonenumbere164hashed h_01M4ZE5P7Q98VNS456PMVXQQXC=first-name-firstnamehashed-and-last-name-lastnamehashed h_01M4ZE5P7QEXVV2EPX3Q550586=facebook-login-id-fbloginid turn-on-advancedmatching-data-sharing=activa-el-uso-compartido-de-datos-de-advanced-matching h_01KVFJHWK27C5FA358M526EJED=activa-el-uso-compartido-de-datos-de-advanced-matching privacy-and-data-handling=privacidad-y-tratamiento-de-datos h_01KVFJHWK2BN2T7BTXANAWAX4B=privacidad-y-tratamiento-de-datos faq=preguntas-frecuentes h_01KVFJHWK2XB5VF8V2KPG62QYV=preguntas-frecuentes h_01M4ZE5P7Q0NE2H8D3N7AX5301=is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature h_01M4ZE5P7QCKZYS7399QED62F5=what-happens-if-i-send-an-invalid-hash-value h_01M4ZE5P7QT2SG5DBKZ3GTTZ8S=do-i-need-to-send-all-supported-fields h_01M4ZE5P7QZQJA45VV4XV00VAD=will-advancedmatching-data-sharing-improve-install-attribution h_01M4ZE5P7QVF3HQ2Q8HKAB7W98=does-appsflyer-ever-receive-plaintext-user-identifiers" />
