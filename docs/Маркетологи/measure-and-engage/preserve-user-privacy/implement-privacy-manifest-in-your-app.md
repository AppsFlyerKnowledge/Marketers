---
title: Внедрите манифест конфиденциальности в ваше приложение
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
  edited_at: '2026-08-19T00:33:17Z'
  id: 21677433322641
  locale: ru
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ru/articles/21677433322641
---
> **Краткий обзор.** На WWDC23 компания Apple представила новые манифесты конфиденциальности. Благодаря манифестам конфиденциальности разработчики приложений могут предоставить более точное описание внедрения конфиденциальности в своих приложениях. Компания AppsFlyer разработала манифест конфиденциальности для AppsFlyer SDK, подробности которого описаны ниже.

<div id="background" />

## Фон

Благодаря манифестам конфиденциальности разработчик приложения сможет создать запись о категориях данных, которые он собирает через свое приложение самостоятельно и с помощью сторонних зависимостей, таких как сторонние SDK, используемые приложением. Эта информация помогает разработчикам приложений точно представлять внедрение конфиденциальности в своих приложениях, в том числе на этикетках с описанием, которые они предоставляют своим пользователям.

Во многих случаях разработчики приложений не знают, какие данные собирают сторонние SDK и для чего конкретный SDK использует эти данные. Манифест конфиденциальности позволяет сторонним SDK легко передавать эту информацию разработчикам приложений, помогая им создавать точные этикетки с описанием.

<div id="what-are-nutrition-labels" />

### Что такое этикетки с описанием?

Этикетки с описанием предоставляют информацию о практике конфиденциальности приложений в удобном для чтения и понимания формате. Конечные пользователи получают больше прозрачности в отношении того, какие данные и с какой целью собирает приложение. Более подробную информацию об этикетках можно найти <Anchor target="_blank" href="/marketers/ru/docs/preparing-for-the-app-store-review-nutrition-labels">здесь</Anchor>.

<div id="what-is-in-the-appsflyer-privacy-manifest" />

## Что содержится в манифесте конфиденциальности AppsFlyer?

<div id="important" />

> 🚧 **Важно!**
>
> Помимо SDK AppsFlyer, вам придется самостоятельно определять способы сбора данных, API с указанием причины использования и их использования в вашем приложении или других SDK, а также сообщать эту информацию на этикетках с описанием.

AppsFlyer SDK 6.14.0 включает в себя манифест конфиденциальности AppsFlyer. Сюда входят:

* [Использование данных](#использование-данных)
* [API с указанием причины использования](#api-с-указанием-причины-использования)
* [Домены отслеживания](#домены-отслеживания)

<div id="data-usage" />

### Использование данных

Apple требует от разработчиков приложений и SDK фиксировать категории данных и причины, по которым приложение или сторонний SDK собирает такие данные.

Разработчики приложений могут использовать Xcode для создания отчета о конфиденциальности, обобщающего информацию о собранных данных.

Ниже перечислены типы данных, собираемых AppsFlyer SDK, которые включены в Манифест конфиденциальности:

<div id="note" />

> 📘 **Примечание**
>
> Далее предполагается применение настроек программного обеспечения AppsFlyer по умолчанию. Разработчики приложений несут ответственность за то, что они соответствующим образом адаптируют свои собственные манифесты в соответствии с их конкретными конфигурациями и использованием AppsFlyer SDK.

| Имя | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| Идентификатор устройства (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | Да | Да | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| Взаимодействие с продуктами (запуски) | NSPrivacyCollectedDataTypeProductInteraction | Нет | Нет | NSPrivacyCollectedDataTypePurposeAnalytics |

<div id="required-reason-apis" />

### API с указанием причины использования

Apple предоставила список API, для использования которых требуется обоснование. Приложения и SDK, использующие эти API, должны указать их в разделе «API с указанием причины использования» (Required Reason APIs) в Манифесте конфиденциальности. Эти API разделены на категории в зависимости от их функциональности и информации, которую они предоставляют, в соответствии со <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">списком тем Apple</Anchor>. Это API, которые включены в манифест конфиденциальности AppsFlyer SDK версии 6.14.0:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API для меток времени файлов</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API с настройками пользователей по умолчанию</Anchor>

Чтобы уточнить использование API с указанием причины использования, разработчики приложений должны будут объявить категорию API и указать причины использования API из утвержденного списка в манифесте конфиденциальности. Ниже представлены API AppsFlyer и их использование.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK версии 6.14.0 и выше">

| Категория API | Тип категории API | Причина | Комментарии |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API для меток времени файлов</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK использует API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> и <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> для определения даты установки приложения и даты обновления приложения. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API с настройками пользователей по умолчанию</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK хранит данные, необходимые для его работы. Например, ведет учет того, сколько раз запускалось приложение. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK версии 6.13.x и более ранние версии">

| Категория API | Тип категории API | Причина | Комментарии |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">API для меток времени файлов</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK использует API <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> и <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> для определения даты установки приложения и даты обновления приложения. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">API времени загрузки системы</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | Измерение производительности SDK (время выполнения запроса и т.д.) |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">API с настройками пользователей по умолчанию</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK хранит данные, необходимые для его работы. Например, ведет учет того, сколько раз запускалось приложение. |

Для удобства вы можете скопировать следующий фрагмент кода, включающий приведенные выше необходимые причины, и вставить его в свой файл PrivacyInfo.xcprivacy.  

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

<div id="tracking-domains" />

### Домены отслеживания

Любой домен отслеживания, используемый в приложении или стороннем SDK, должен быть записан в манифесте конфиденциальности. Если пользователи не предоставят разрешения на сбор данных (opt-out) через фреймворк App Tracking Transparency (ATT), операционная система iOS будет блокировать весь исходящий трафик к этому домену. AppsFlyer SDK проверяет статус ATT пользователя перед любым запросом к серверу и выполняет запрос, основываясь на том, дал ли пользователь согласие на сбор даннных.

<div id="faq" />

## Вопросы и ответы

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="Есть ли у AppsFlyer SDK с поддержкой манифеста конфиденциальности?">

Да, начиная с версии 6.14.0, SDK полностью поддерживает манифест конфиденциальности.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="Должен ли я сообщать о своем сборе данных?">

Да, помимо AppsFlyer или других SDK, вам придется самостоятельно определять порядок сбора и использования данных и сообщать эту информацию в этикетках с описанием, включая любые изменения, внесенные в конфигурацию SDK AppsFlyer по умолчанию (например, измерение событий в приложении).

</Accordion>

<div data-zendesk-anchors="background=%D1%84%D0%BE%D0%BD h_01HCY4D9EKHYB5B3YNWRCB53F4=%D1%84%D0%BE%D0%BD what-are-nutrition-labels=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%D1%8D%D1%82%D0%B8%D0%BA%D0%B5%D1%82%D0%BA%D0%B8-%D1%81-%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC h_01HCY4ZASEAR69RT3YMHMSE4NP=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%D1%8D%D1%82%D0%B8%D0%BA%D0%B5%D1%82%D0%BA%D0%B8-%D1%81-%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC what-to-consider-when-getting-your-app-ready-to-ios17=%D1%87%D1%82%D0%BE-%D1%81%D0%BE%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D1%82%D1%81%D1%8F-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8-appsflyer h_01HCY4D9EKTKB50BSZD7RBMMYB=%D1%87%D1%82%D0%BE-%D1%81%D0%BE%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D1%82%D1%81%D1%8F-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8-appsflyer h_01HQ5C9WGW669HBWSG4WQMJTGP=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE data-usage=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HQ03P71BG159MCE3VQY4GTMH=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HT9QHRQSKDQ8GR17N7X5QB8N=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 required-reason-apis=api-%D1%81-%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC-%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01HQ03NV880VHFTXQDE8R6ZRZH=api-%D1%81-%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC-%D0%BF%D1%80%D0%B8%D1%87%D0%B8%D0%BD%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D1%8B-%D0%BE%D1%82%D1%81%D0%BB%D0%B5%D0%B6%D0%B8%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01HQ03NV88SJPYKBM66S7X6GP8=%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D1%8B-%D0%BE%D1%82%D1%81%D0%BB%D0%B5%D0%B6%D0%B8%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B 01HQQXSN96D4QTTYHG8CBE8695=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />
