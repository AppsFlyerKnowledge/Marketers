---
title: Руководство по интеграции поставщика услуг электронной почты (ESP)
metadata:
  keywords:
    - Email
    - Advertisers
    - Developers
    - Premium
    - Email service providers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-12-31T10:43:24Z'
  edited_at: '2026-09-28T00:16:09Z'
  id: 360004556077
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Создавайте рассылки по электронной почте с интегрированными ESP, используя фирменные ссылки OneLink и перенаправление по диплинкам для удобного пользовательского опыта, способствующего конверсии.

<div id="about-esp-integration" />

## Об интеграции с ESP

Маркетинг-рассылка — это простой и эффективный способ взаимодействия с клиентами и потенциальными покупателями. Многие маркетологи полагаются на поставщиков услуг электронной почты (ESP) для отправки масштабных рассылок своим пользователям. И хотя этот процесс должен быть простым и понятным, обеспечивая идеальный путь мобильного пользователя, обычно это не так.

**В чем сложность?**

Проблемы возникают в результате того, каким образом типичный ESP обрабатывает свою аналитику, что, как правило, нарушает диплинки и негативно сказывается на опыте мобильных пользователей. Диплинкинг — это отправка пользователей непосредственно в определенное место внутри вашего приложения, что является важнейшей функцией для достижения конверсии. Обеспечение плавного перехода по диплинкам (глубоким ссылкам) в рассылках по электронной почте, отправляемых ESP, представляет собой настоящую проблему, поскольку ESP "оборачивают" диплинки для целей измерения, что нарушает связь между приложением и доменом, необходимую для универсальных ссылок iOS и Android App Links. Это, к сожалению, приводит к следующему:

* Перенаправление пользователей на мобильные сайты вместо перенаправления в приложение по диплинку.
* Использование метода диплинкинга со схемой URI, который менее безопасен и обеспечивает плохой пользовательский опыт.

<Image align="center" alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**Каково решение?**

Чтобы избежать этих проблем и обеспечить пользователям мобильных устройств наилучший опыт, выберите своего ESP в разделе ниже и следуйте конкретным инструкциям по интеграции. Некоторые ESP поддерживаются в решении для интеграции AppsFlyer, которое позволяет AppsFlyer выступать в качестве посредника между сервером ESP и вашим доменным именем. Эта роль прокси позволяет предоставлять файлы ассоциаций (AASA / ссылки на активы), что облегчает диплинкинг.

Решение для интеграции ESP в AppsFlyer — это премиум-функция. Если вы хотите узнать больше или приступить к работе, свяжитесь с нами по адресу [hello@appsflyer.com](mailto:hello@appsflyer.com).

<div id="supported-esps" />

## Поддерживаемые ESP

Рассылки по электронной почте от ESP для пользователей мобильных приложений могут вызвать проблемы с атрибуцией и диплинкингом. Чтобы избежать этих проблем, нажмите на своего ESP в разделе ниже и следуйте конкретным инструкциям по ссылке.

| Список поддерживаемых ESP | Использует метод интеграции AppsFlyer |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Acoustic" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="86px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/adobe-esp-integration-with-appsflyer"><Image alt="Логотип Adobe" src="https://files.readme.io/62926ce91dac3216426360869fc3d3adfe7a73e009cca47ecabb4a41b973b457-51177578838545.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип AWS SES" src="https://files.readme.io/371a43248e0c88469a5a4599c501da148745c3b12d080f114dbb385ef9a7f899-46799108961937.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Blueshift" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Braze" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип CleverTap" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Customer.io" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Emarsys" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип ExpertSender" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Insider" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Klaviyo" src="https://files.readme.io/4144e48e7c072ec2034671752a02398e98bb023cda647f37986e953772d97f89-41351882139409.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип MailExpress" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Mailgun" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Mindbox" src="https://files.readme.io/5fdc6f90d39879c994298762de429528719f9be0f08e78ac25f1d2a6240d20f2-50865749335057.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Moengage" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Ongage" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип ESP (название не подтверждено)" src="https://files.readme.io/25e13e60d862c3694e698ecd66d1a26e5d8e1a1849c5ded15ad308e1c8d99b6e-44854095773457.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип RD Station" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Reteno" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип Sailthru" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип SendGrid" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" height="40px" /></Anchor> | Да |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Логотип SparkPost" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" height="40px" /></Anchor> | Да |

<div id="other-esps" />

## Другие ESP

Ниже приведен список других ESP, которые, хотя и не поддерживаются интеграцией ESP AppsFlyer, имеют собственные методы решения вопросов атрибуции и диплинкинга, описанных выше. Чтобы реализовать соответствующие методы, найдите своего ESP в разделе ниже и следуйте инструкциям по интеграции по указанным ссылкам.

| 53798 KB ORACLE (1).png | Использует метод интеграции AppsFlyer |
| --- | --- |
| Bloomreach | № Использует собственный метод перенаправления Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/bloomreach-integration-with-appsflyer">настроить интеграцию с Bloomreach.</Anchor> |
| 53798 KB EmailLabs (1).png | Нет. Использует собственный метод перенаправления Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/emaillabs-integration-with-appsflyer">настроить интеграцию с EmailLabs</Anchor>. |
| Iterable | Нет. Использует собственный метод перенаправления Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/iterable-integration-with-appsflyer">настроить интеграцию с Iterable.</Anchor> |
| Oracle | № Использует собственный метод перенаправления Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/oracle-responsys-integration-with-appsflyer">настроить интеграцию с Oracle.0></Anchor> |
| salesforce.png | Нет. Использует собственный метод перенаправления Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/salesforce-marketing-cloud-sfmc-integration-with-appsflyer">настроить интеграцию с Salesforce</Anchor>. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-esp h_01J3JHJCCASM6E5QYJB5VHQ8HK=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-esp supported-email-service-providers=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-esp h_01H92VH355BQ13SP72VNJEKW1E=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-esp h_01K06J2Z9QRW4VPVBP6QT81W8Y=%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%B5-esp" />
