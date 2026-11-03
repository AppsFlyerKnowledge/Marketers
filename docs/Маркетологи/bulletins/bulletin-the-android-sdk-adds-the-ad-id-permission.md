---
title: 'Бюллетень: Android SDK добавляет разрешение AD_ID'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2026-08-18T00:21:31Z'
  id: 7569900844689
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/7569900844689
---
> **Краткий обзор.** Начиная с AppsFlyer SDK для Android версии 6.8.0, разрешение AD\_ID объявляется в файле AndroidManifest.xml в SDK.

| **Фон** | В начале 2022 года компания Google объявила об изменении поведения сервисов Google Play и получении рекламного идентификатора Android.<br /><br />Согласно <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">объявлению</Anchor>, приложения с таргетингом на Android 13 (API 33) и выше, должны будут указать в файле манифеста обычное разрешение сервисов Google Play, чтобы получить доступ к рекламному идентификатору устройства.<br /><br />Разрешение предоставляется приложению во время установки и не вызывает никаких действий со стороны пользователя. |
| --- | --- |
| **Что изменилось?** | Начиная с AppsFlyer SDK для Android версии 6.8.0, разрешение AD\_ID объявляется в файле AndroidManifest.xml в SDK. После создания приложения манифест в SDK по умолчанию сливается с манифестом вашего приложения, и разрешение добавляется, даже если приложение явно не заявило о разрешении. Если разрешение есть и в приложении, и в SDK, оно работает нормально — коллизий не возникнет. |
| **Что вы должны знать** | <ul><li>Если вы используете SDK 6.8.0 и у вас есть разрешение AD\_ID в манифесте вашего приложения, вы можете при желании удалить его из манифеста и позволить SDK добавить его за вас.</li><li>Если вы используете версию SDK **старше** 6.8.0 и ваше приложение предназначено для Android 13 (API 33) и выше, вам следует добавить в приложение разрешение AD\_ID, чтобы SDK мог получить доступ к рекламному идентификатору.</li><li>**Приложения, ориентированные на детей:** Согласно <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">политике Google</Anchor>, приложения, предназначенные для детей, не должны передавать рекламный идентификатор. Если вы создаете приложение для детей и используете SDK 6.8.0 и выше, вам необходимо отозвать разрешение AD\_ID. См. инструкции для разработчиков <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">здесь</Anchor>.</li></ul> |