---
title: Guía de integración del proveedor de servicios de correo electrónico (ESP)
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
  edited_at: '2026-09-28T00:16:00Z'
  id: 360004556077
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Crea campañas de correo electrónico con ESP integrados mediante enlaces de la marca OneLink y deep linking para disfrutar de experiencias de usuario fluidas que impulsen la conversión.

## Acerca de la integración ESP

El marketing por correo electrónico es una forma sencilla, potente y eficaz de interactuar con los clientes y clientes potenciales. Muchos marketers confían en los proveedores de servicios de correo electrónico (ESP) para enviar campañas de correo electrónico a gran escala a sus usuarios. Y si bien este debería ser un proceso sencillo y directo, que ofrezca la experiencia de usuario móvil perfecta que imaginas, no suele ser así.

**¿Cuál es el desafío?**

Los problemas surgen como resultado de la forma en que el ESP típico maneja sus análisis, lo que tiende a romper los deep links y afectar negativamente a la experiencia del usuario móvil. Deep linking se refiere a enviar a los usuarios directamente a una ubicación específica dentro de tu aplicación, que es una funcionalidad crucial para lograr la conversión. Proporcionar una experiencia fluida de deep linking en las campañas de correo electrónico enviadas por los ESPs es un verdadero desafío, ya que los ESPs «envuelven» los deep links con fines de medición, lo que rompe la asociación entre aplicaciones y dominios requerida para los Universal Links de iOS y los Android App Links. Lamentablemente, esto resulta en:

* Dirigir a los usuarios a sitios web móviles en lugar de enviarlos a la aplicación
* Utilizar el método de deep linking del esquema URI, que es menos seguro y proporciona una mala experiencia de usuario

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**¿Cuál es la solución?**

Para evitar estos problemas y ofrecer a los usuarios móviles la mejor experiencia, haz clic en tu ESP en la sección siguiente y sigue las instrucciones de integración específicas. Algunos ESPs son compatibles con una solución de integración de AppsFlyer que permite a AppsFlyer actuar como intermediario entre el servidor ESP y tu nombre de dominio. Su función como proxy permite el suministro de archivos de asociación (AASA o enlaces de activos), lo que facilita el deep linking.

La solución de integración ESP de AppsFlyer es una función premium. Si quieres saber más o empezar, ponte en contacto con nosotros en [hello@appsflyer.com](mailto:hello@appsflyer.com).

## ESPs compatibles

Las campañas de correo electrónico ESP para usuarios de aplicaciones móviles pueden causar problemas con la atribución y los deep linking. Para evitar estos problemas, haz clic en tu ESP en la sección siguiente y sigue las instrucciones específicas.

| Lista de ESPs compatibles | Soporta la integración beta de AppsFlyer |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Acoustic" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="86px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/adobe-esp-integration-with-appsflyer"><Image alt="Logo de Adobe" src="https://files.readme.io/62926ce91dac3216426360869fc3d3adfe7a73e009cca47ecabb4a41b973b457-51177578838545.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de AWS SES" src="https://files.readme.io/371a43248e0c88469a5a4599c501da148745c3b12d080f114dbb385ef9a7f899-46799108961937.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Blueshift" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Braze" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de CleverTap" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Customer.io" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Emarsys" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de ExpertSender" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Insider" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Klaviyo" src="https://files.readme.io/4144e48e7c072ec2034671752a02398e98bb023cda647f37986e953772d97f89-41351882139409.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de MailExpress" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Mailgun" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Mindbox" src="https://files.readme.io/5fdc6f90d39879c994298762de429528719f9be0f08e78ac25f1d2a6240d20f2-50865749335057.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Moengage" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Ongage" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de ESP (nombre sin confirmar)" src="https://files.readme.io/25e13e60d862c3694e698ecd66d1a26e5d8e1a1849c5ded15ad308e1c8d99b6e-44854095773457.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de RD Station" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Reteno" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de Sailthru" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de SendGrid" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" height="40px" /></Anchor> | Sí |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Logo de SparkPost" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" height="40px" /></Anchor> | Sí |

## Otros ESPs

Aquí tienes una lista de otros ESPs que, aunque no cuentan con el soporte de la integración ESP de AppsFlyer, tienen sus propios métodos para gestionar los problemas de atribución y Deep Linking comentados anteriormente. Para implementar sus métodos, busca tu ESP en la sección siguiente y sigue sus instrucciones de integración en los enlaces proporcionados.

| 53798 KB ORACLE (1).png | https://support.appsflyer.com/hc/article_attachments/38922843662097 |
| --- | --- |
| Bloomreach | N.º Utiliza su propio método de redirección Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/bloomreach-integration-with-appsflyer">integrar Bloomreach.</Anchor> |
| 53798 KB EmailLabs (1).png | N.º Utiliza su propio método de redirección Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/emaillabs-integration-with-appsflyer">integrar EmailLabs</Anchor>. |
| Iterable | N.º Utiliza su propio método de redirección Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/iterable-integration-with-appsflyer">integrar Iterable.</Anchor> |
| Oracle | N.º Utiliza su propio método de redirección. Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/oracle-responsys-integration-with-appsflyer">integrar con Oracle</Anchor>. |
| salesforce.png | N.º Utiliza su propio método de redirección Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/salesforce-marketing-cloud-sfmc-integration-with-appsflyer">integrar Salesforce</Anchor>. |

<div data-zendesk-anchors="overview=acerca-de-la-integraci%C3%B3n-esp h_01J3JHJCCASM6E5QYJB5VHQ8HK=acerca-de-la-integraci%C3%B3n-esp supported-email-service-providers=esps-compatibles h_01H92VH355BQ13SP72VNJEKW1E=esps-compatibles h_01K06J2Z9QRW4VPVBP6QT81W8Y=otros-esps" />
