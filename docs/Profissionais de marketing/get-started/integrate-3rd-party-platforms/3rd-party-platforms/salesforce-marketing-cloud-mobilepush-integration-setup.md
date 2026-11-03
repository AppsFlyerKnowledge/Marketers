---
title: Configuração da integração do Salesforce Marketing Cloud MobilePush
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2023-09-26T14:07:39Z'
  id: 10590769196817
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/10590769196817
---
> **Visão geral:** Salesforce Marketing Cloud MobilePush, um parceiro integrado da AppsFlyer, é uma plataforma de engajamento de usuários para equipes de marketing, crescimento e engajamento.

## Visão geral

O Salesforce Marketing Cloud MobilePush permite que você crie e envie mensagens push direcionadas com base em dados do consumidor entre canais. Isso ajuda a incentivar o uso do aplicativo e aumentar o ROI. Com o MobilePush, você pode ver como os usuários navegam pelo seu aplicativo, desde os produtos que visualizam até o tempo gasto em cada página. A integração do MobilePush permite:

* Impulsionar o engajamento e o mCommerce
* Obter insights valiosos do usuário
* Criar facilmente campanhas entre canais
* Segmentar e agendar mensagens

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para este parceiro, independentemente da seleção configurada para envio de postbacks.

## Configurar o Salesforce Marketing Cloud MobilePush

A maior parte da configuração é feita no Salesforce (etapas 1 a 4). A etapa 5 é feita na AppsFlyer.

### Etapa 1: configure o SDK do MobilePush

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Implemente a configuração do SDK do MobilePush</Anchor>

### Etapa 2: provisionamento para notificações push

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Crie um certificado `.p12`</Anchor>

### Etapa 3: ative as notificações push do aplicativo

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Implemente as notificações push</Anchor>

### Etapa 4: configure as notificações push do aplicativo

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Crie e envie mensagens por push para dispositivos móveis</Anchor>

> 📘 **Observação**
>
> Ao criar uma notificação push na nuvem de marketing do Salesforce, uma <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">chave personalizada</Anchor> precisa ser adicionada para que a AppsFlyer possa atribuir o PID correto e os atributos de campanha. Use `AF_xxxxxxxxx` como a chave personalizada.

### Etapa 5: configure notificações push na AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Configure o SDK do iOS usando o OneLink (etapa 3 neste link)</Anchor>

> 📘 **Observação**
>
> Certifique-se de que a chave personalizada `AF_xxxxxxxxx` inserida na [etapa 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#etapa-4-configure-as-notificações-push-do-aplicativo) tenha o mesmo valor inserido na função `addPushNotificationDeepLinkPath`.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01H9HWK3F5TQZ8YQZBHGBZACPG=vis%C3%A3o-geral h_01H9HWK5DM87JTDVFND0KB965G=importante setting-up-salesforce-marketing-cloud-mobilepush=configurar-o-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=configurar-o-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=etapa-1-configure-o-sdk-do-mobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=etapa-1-configure-o-sdk-do-mobilepush step-2-provision-for-push-notifications=etapa-2-provisionamento-para-notifica%C3%A7%C3%B5es-push h_01H9HWK3F5RNCZG340E0CT5XJC=etapa-2-provisionamento-para-notifica%C3%A7%C3%B5es-push step-3-enable-app-push-notifications=etapa-3-ative-as-notifica%C3%A7%C3%B5es-push-do-aplicativo h_01H9HWK3F5E4W8FG35V4JTFN7F=etapa-3-ative-as-notifica%C3%A7%C3%B5es-push-do-aplicativo step-4-set-up-app-push-notifications=etapa-4-configure-as-notifica%C3%A7%C3%B5es-push-do-aplicativo h_01H9HWK3F5K8V8AVADXNNG25GY=etapa-4-configure-as-notifica%C3%A7%C3%B5es-push-do-aplicativo h_01H9HWK3F5VG2GBCE93B69AADH=observa%C3%A7%C3%A3o step-5-set-up-push-notifications-in-appsflyer=etapa-5-configure-notifica%C3%A7%C3%B5es-push-na-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=etapa-5-configure-notifica%C3%A7%C3%B5es-push-na-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=observa%C3%A7%C3%A3o-1" />
