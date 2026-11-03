---
title: Implementa el manifiesto de privacidad en tu aplicación
metadata:
  keywords:
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
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-08-12T12:23:42Z'
  id: 21677433322641
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/21677433322641
---
> **En resumen:** En la WWDC23, Apple presentó nuevos avisos de privacidad. Con los avisos de privacidad, los desarrolladores de aplicaciones pueden proporcionar descripciones más precisas de las prácticas de privacidad de sus aplicaciones. AppsFlyer ha creado un aviso de privacidad para el SDK de AppsFlyer y los detalles se explican a continuación.

## Antecedentes

Con los avisos de privacidad, un desarrollador de aplicaciones podrá crear un registro de las categorías de datos que recopila a través de su aplicación de forma independiente y mediante el uso de dependencias de terceros, como los SDK de terceros utilizados por la aplicación. Esta información ayuda a los desarrolladores de aplicaciones a representar con precisión las prácticas de privacidad en sus aplicaciones, incluso a través de las etiquetas nutricionales que proporcionan a sus usuarios.

En muchos casos, los desarrolladores de aplicaciones no saben qué datos recopilan los SDK de terceros ni para qué usa los datos un SDK específico. El aviso de privacidad permite a los SDK de terceros transmitir fácilmente esta información a los desarrolladores de la aplicación, lo que les ayuda a crear etiquetas nutricionales precisas.

### ¿Qué son las etiquetas nutricionales?

Las etiquetas nutricionales proporcionan información sobre las prácticas de privacidad de las aplicaciones en un formato fácil de leer y entender. Los usuarios finales tienen más transparencia en cuanto a los datos que recopila la aplicación y con qué propósito. Para obtener más información sobre las etiquetas nutricionales, consulta <Anchor target="_blank" href="/marketers/es/docs/preparing-for-the-app-store-review-nutrition-labels">aquí</Anchor>.

## ¿Qué contiene el aviso de privacidad de AppsFlyer?

> 🚧 **¡Importante!**
>
> Además del SDK de AppsFlyer, tendrás que determinar tu propia recopilación de datos, la razón requerida, la API y el uso en tu aplicación u otros SDK, y reportar esa información en las etiquetas nutricionales.

El SDK 6.14.0 de AppsFlyer incluye el aviso de privacidad de AppsFlyer. Esto incluye:

* [Uso de datos](#uso-de-datos)
* [APIs de Razón Requerida](#apis-de-razón-requerida)
* [Seguimiento de dominios](#dominios-de-seguimiento)

### Uso de datos

Apple exige a los desarrolladores de apps y SDK que registren la categoría de datos y los motivos por los que la app o el SDK de terceros recopilan dichos datos.

Luego, los desarrolladores de aplicaciones pueden usar Xcode para crear un reporte de privacidad en el que se resuma la información sobre los datos recopilados.

Los siguientes son los tipos de datos recopilados por el SDK de AppsFlyer y que se incluyen en el aviso de privacidad:

> 📘 **Nota**
>
> A continuación se asumen las configuraciones predeterminadas del software de AppsFlyer. Los desarrolladores de aplicaciones son responsables de garantizar que adaptan su propio aviso de acuerdo con sus configuraciones y usos específicos del SDK de AppsFlyer.

| Nombre | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| ID del dispositivo (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | Sí | Sí | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| Interacción con el producto (lanzamientos) | NSPrivacyCollectedDataTypeProductInteraction | No | No | NSPrivacyCollectedDataTypePurposeAnalytics |

### APIs de Razón Requerida

Apple proporcionó una lista de API que requieren un razonamiento para su uso. Las aplicaciones y los SDK que utilizan estas API deben detallarlas en la sección API de motivos obligatorios del aviso de privacidad. Estas API se dividen en categorías según su funcionalidad y la información que proporcionan según <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">la lista de temas de Apple.</Anchor> Estas son las API que se incluyen en el aviso de privacidad de la versión 6.14.0 del SDK de AppsFlyer:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API de marca de tiempo de archivos</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API predeterminadas por el usuario</Anchor>

Para aclarar el uso de las API de razón requerida, los desarrolladores de aplicaciones deberán declarar la categoría de la API y especificar los motivos por los que la utilizan. A continuación se muestran las API de AppsFlyer y su uso.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK versión 6.14.0 y superior">

| Categoría de API | Tipo de categoría de API | Motivo | Comentarios |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API de marca de tiempo de archivos</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | El SDK usa las API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> y <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> para determinar la fecha de la instalación de la aplicación y de la actualización de la aplicación. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API predeterminadas por el usuario</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA 92.1 | El SDK almacena los datos necesarios para su funcionamiento. Por ejemplo, mantener el número de veces que se lanzó la aplicación. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="Versiones 6.13.x y anteriores del SDK">

| Categoría de API | Tipo de categoría de API | Motivo | Comentarios |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API de marca de tiempo de archivos</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | El SDK usa las API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> y <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> para determinar la fecha de la instalación de la aplicación y de la actualización de la aplicación. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">API de tiempo de arranque del sistema</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | Mide el rendimiento del SDK (tiempo que tardó en ejecutarse una solicitud, etc.) |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API predeterminadas por el usuario</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA 92.1 | El SDK almacena los datos necesarios para su funcionamiento. Por ejemplo, mantener el número de veces que se lanzó la aplicación. |

Para tu comodidad, puedes copiar el siguiente fragmento de código, que incluye las razones requeridas anteriores, y pegarlo en tu archivo PrivacyInfo.xcPrivacy. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

### Dominios de seguimiento

Cualquier dominio de seguimiento utilizado en una aplicación o en un SDK de terceros debe registrarse en el aviso de privacidad. Si los usuarios no conceden permisos (exclusión voluntaria) a través del marco de transparencia del seguimiento de aplicaciones (ATT), el sistema operativo iOS bloqueará todo el tráfico saliente a ese dominio. El SDK de AppsFlyer comprueba el estado de ATT del usuario antes de cualquier solicitud del servidor y ejecuta la solicitud en función de si el usuario ha optado por participar.

## Preguntas frecuentes

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="¿AppsFlyer tiene un SDK compatible con el aviso de privacidad?">

Sí, a partir de la versión 6.14.0, el SDK es totalmente compatible con el aviso de privacidad.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="¿Tengo que informar sobre mi propia recopilación de datos?">

Sí, además de AppsFlyer u otros SDK, tendrás que determinar tu propia recopilación y uso de datos y reportar esa información en las etiquetas nutricionales, incluidos los cambios de configuración realizados en las configuraciones predeterminadas del SDK de AppsFlyer (por ejemplo, la medición de eventos in-app).

</Accordion>

<div data-zendesk-anchors="background=antecedentes h_01HCY4D9EKHYB5B3YNWRCB53F4=antecedentes what-are-nutrition-labels=qu%C3%A9-son-las-etiquetas-nutricionales h_01HCY4ZASEAR69RT3YMHMSE4NP=qu%C3%A9-son-las-etiquetas-nutricionales what-to-consider-when-getting-your-app-ready-to-ios17=qu%C3%A9-contiene-el-aviso-de-privacidad-de-appsflyer h_01HCY4D9EKTKB50BSZD7RBMMYB=qu%C3%A9-contiene-el-aviso-de-privacidad-de-appsflyer h_01HQ5C9WGW669HBWSG4WQMJTGP=importante data-usage=uso-de-datos h_01HQ03P71BG159MCE3VQY4GTMH=uso-de-datos h_01HT9QHRQSKDQ8GR17N7X5QB8N=nota required-reason-apis=apis-de-raz%C3%B3n-requerida h_01HQ03NV880VHFTXQDE8R6ZRZH=apis-de-raz%C3%B3n-requerida h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=dominios-de-seguimiento h_01HQ03NV88SJPYKBM66S7X6GP8=dominios-de-seguimiento faq=preguntas-frecuentes 01HQQXSN96D4QTTYHG8CBE8695=preguntas-frecuentes h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />
