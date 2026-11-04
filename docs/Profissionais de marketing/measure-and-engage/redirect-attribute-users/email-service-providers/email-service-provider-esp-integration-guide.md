---
title: Guia de integração de provedores de serviços de e-mail (ESP)
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
  edited_at: '2026-09-24T00:16:09Z'
  id: 360004556077
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Crie campanhas de e-mail com ESPs integrados usando branded links e deep linking do OneLink para criar experiências que impulsionam a conversão de usuários.

<div id="about-esp-integration" />

## Sobre a integração de ESPs

O marketing por e-mail é uma maneira simples, poderosa e eficaz de interagir com clientes. Muitos profissionais de marketing utilizam provedores de serviços de e-mail (ESPs) para enviar campanhas de e-mail em escala para seus usuários. Embora esse pareça ser um processo direto e simples, que oferece a jornada perfeita que você imaginou para seus usuários mobile, alguns problemas costumam aparecer.

**Qual é o desafio?**

Os problemas surgem como resultado da forma como o ESP lida com seus analytics, adotando um processo que costuma quebrar deep links e afetar negativamente a experiência do usuário mobile. Deep linking se refere ao envio de usuários diretamente para um local específico dentro do seu app, que é uma funcionalidade crucial para efetuar a conversão. Fornecer uma experiência de deep linking sem obstáculos em campanhas de e-mail enviadas por ESPs é um verdadeiro desafio, pois os ESPs "encapsulam" os deep links para fins de medição, o que quebra a associação de domínio do app necessária para links universais do iOS e Android App Links. Infelizmente, isso resulta em:

* Roteamento de usuários para sites móveis em vez de realizar o deep linking diretamente para o app
* Usando o método de deep linking do esquema de URI, que é menos seguro e fornece uma experiência de usuário ruim

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**Qual é a solução?**

Para evitar esses problemas e fornecer aos usuários móveis a melhor experiência, clique em seu ESP na seção abaixo e siga as instruções de integração específicas. Alguns ESPs são compatíveis com a solução de integração da AppsFlyer que permite que a AppsFlyer sirva de intermediária entre o servidor ESP e seu nome de domínio. Seu papel como proxy permite o fornecimento de arquivos de associação (AASA / links de ativos), o que facilita o deep linking.

A solução de integração de ESP da AppsFlyer é um recurso premium. Se quiser saber mais sobre isso ou fazer a introdução, entre em contato conosco pelo e-mail [hello@appsflyer.com](mailto:hello@appsflyer.com).

<div id="supported-esps" />

## ESPs compatíveis

Campanhas de e-mail ESP para usuários de aplicativos móveis podem causar problemas de atribuição e links diretos. Para evitar esses problemas, clique no seu ESP na seção abaixo e siga as instruções especificadas.

| Lista de ESPs compatíveis | Usa o método de integração da AppsFlyer |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Acoustic logo" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="86px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/adobe-esp-integration-with-appsflyer"><Image alt="Adobe logo" src="https://files.readme.io/62926ce91dac3216426360869fc3d3adfe7a73e009cca47ecabb4a41b973b457-51177578838545.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="AWS SES logo" src="https://files.readme.io/371a43248e0c88469a5a4599c501da148745c3b12d080f114dbb385ef9a7f899-46799108961937.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Blueshift logo" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Braze logo" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="CleverTap logo" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Customer.io logo" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Emarsys logo" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="ExpertSender logo" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Insider logo" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Klaviyo logo" src="https://files.readme.io/4144e48e7c072ec2034671752a02398e98bb023cda647f37986e953772d97f89-41351882139409.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="MailExpress logo" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Mailgun logo" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Mindbox logo" src="https://files.readme.io/5fdc6f90d39879c994298762de429528719f9be0f08e78ac25f1d2a6240d20f2-50865749335057.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Moengage logo" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Ongage logo" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="ESP logo (nome não confirmado)" src="https://files.readme.io/25e13e60d862c3694e698ecd66d1a26e5d8e1a1849c5ded15ad308e1c8d99b6e-44854095773457.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="RD Station logo" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Reteno logo" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Sailthru logo" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="SendGrid logo" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="SparkPost logo" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" height="40px" /></Anchor> | Yes |

<div id="other-esps" />

## Outros ESPs

Veja uma lista de outros ESPs que, embora não sejam compatíveis com a integração de ESP da AppsFlyer, têm seus próprios métodos para lidar com os problemas de atribuição e deep linking discutidos acima. Para implementar esses métodos, localize seu ESP na seção abaixo e siga as instruções de integração nos links fornecidos.

| 53798 KB ORACLE (1).png | Usa o método de integração da AppsFlyer |
| --- | --- |
| Bloomreach | Sem. Usa um método de redirecionamento próprio Usa um método de redirecionamento próprio Saiba como <Anchor target="_blank" href="/marketers/pt/docs/bloomreach-integration-with-appsflyer">fazer a integração com a Bloomreach.</Anchor> |
| 53798 KB EmailLabs (1).png | Não. Usa um método de redirecionamento próprio Usa um método de redirecionamento próprio Saiba como <Anchor target="_blank" href="/marketers/pt/docs/emaillabs-integration-with-appsflyer">fazer a integração com a EmailLabs</Anchor>. |
| Iterable | Não. Usa um método de redirecionamento próprio Usa um método de redirecionamento próprio Saiba como <Anchor target="_blank" href="/marketers/pt/docs/iterable-integration-with-appsflyer">fazer a integração com a Iterable.</Anchor> |
| Oracle | Sem. Usa um método de redirecionamento próprio Usa um método de redirecionamento próprio Saiba como <Anchor target="_blank" href="/marketers/pt/docs/oracle-responsys-integration-with-appsflyer">integrar com a Oracle</Anchor>. |
| salesforce.png | Não. Usa um método de redirecionamento próprio Usa um método de redirecionamento próprio Saiba como <Anchor target="_blank" href="/marketers/pt/docs/salesforce-marketing-cloud-sfmc-integration-with-appsflyer">fazer a integração com a Salesforce</Anchor>. |

<div data-zendesk-anchors="overview=sobre-a-integra%C3%A7%C3%A3o-de-esps h_01J3JHJCCASM6E5QYJB5VHQ8HK=sobre-a-integra%C3%A7%C3%A3o-de-esps supported-email-service-providers=esps-compat%C3%ADveis h_01H92VH355BQ13SP72VNJEKW1E=esps-compat%C3%ADveis h_01K06J2Z9QRW4VPVBP6QT81W8Y=outros-esps" />
