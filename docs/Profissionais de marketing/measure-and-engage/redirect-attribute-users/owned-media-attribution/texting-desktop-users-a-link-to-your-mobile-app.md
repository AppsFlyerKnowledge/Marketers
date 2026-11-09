---
title: >-
  Enviar mensagens de texto aos usuários de desktop com um link para seu
  aplicativo móvel
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-08-18T00:35:53Z'
  id: 360003799658
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/360003799658
---
> **Visão geral:** Converta usuários de desktop em usuários de app mobile usando provedores de SMS e o OneLink.

<Image align="center" alt="text-me-the-app-web-form.png" src="https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png" />

<div id="introduction" />

## Introdução

Se a sua marca tiver tanto um aplicativo web quanto um app mobile, os usuários web no desktop podem decidir, em algum momento, que querem instalar o app mobile.

Para ajudar com isso e oferecer uma melhor experiência do usuário, você pode enviar por SMS um link direto para o aplicativo. Essa é a forma mais rápida de ajudar na instalação do aplicativo.

Dessa forma, eles não precisam abrir a loja de aplicativos no dispositivo mobile, encontrar o seu aplicativo e instalá-lo. Quando você economiza tempo e esforço dos usuários, é mais provável que eles convertam e instalem o seu app mobile.

<div id="note" />

> 📘 **Nota**
>
> Oferecemos outra solução para <Anchor target="_blank" href="/marketers/pt/docs/qr-to-app-conversion">conversão de desktop para web</Anchor> que exige apenas que você publique um QR code (gerado a partir do seu OneLink) no seu site para desktop.

<div id="requirements" />

## Requisitos

Para enviar aos usuários de desktop, por SMS, um link para o seu app mobile, você precisa do seguinte:

1. Uma conta em um provedor de SMS, como Twilio, AWS SNS ou bandwidth.com.
2. Um ambiente de backend em que você possa lidar com a lógica de envio de links por SMS para os usuários.
3. Um link personalizado multiplataforma, como o <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.

<div id="setting-up" />

## Configuração

A seção a seguir apresenta uma visão geral de alto nível dos requisitos discutidos anteriormente.

<div id="sms-provider-account-to-text-a-link-to-the-app" />

### Conta em provedor de SMS para enviar um link para o aplicativo

Crie uma conta com qualquer provedor de SMS. Depois, você poderá enviar links para o seu app mobile a um grande número de usuários a qualquer momento.

Consulte a lista a seguir com alguns provedores populares que oferecem suporte a várias linguagens de programação e têm APIs abrangentes para vários casos de uso:

* <Anchor target="_blank" href="https://www.twilio.com/docs/sms/send-messages">Twilio</Anchor>
* <Anchor target="_blank" href="https://dev.bandwidth.com/messaging/about.html">bandwidth</Anchor>
* <Anchor target="_blank" href="https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html">AWS SNS</Anchor>
* <Anchor target="_blank" href="https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/">Braze</Anchor>
* <Anchor target="_blank" href="https://www.airship.com/platform/channels/sms/">Airship</Anchor>
* [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
* <Anchor target="_blank" href="https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel">Mixpanel</Anchor>

<div id="a-backend-environment-to-communicate-with-the-sms-provider" />

### Um ambiente de backend para se comunicar com o provedor de SMS

Os provedores de SMS exigem tokens de autenticação para usar os serviços deles. Além disso, os números de telefone dos usuários são dados sensíveis. Por esses motivos, a melhor opção é processar tudo no seu backend.

<div id="a-multi-platform-custom-link" />

### Um link multiplataforma personalizado

Um link personalizado multiplataforma redireciona o usuário para a loja de aplicativos ou o destino correto de acordo com o dispositivo que ele usa. Dessa forma, você pode enviar o mesmo link para qualquer usuário, independentemente do dispositivo que ele usa.

<div id="texting-the-app-to-users" />

## Enviar o aplicativo por SMS aos usuários

Esta seção descreve o fluxo de envio, por SMS, de um link para o aplicativo aos usuários. Ela também explica como acompanhar o número de usuários que instalam o aplicativo a partir do link.

<div id="create-a-multi-platform-onelink" />

### Criar um OneLink multiplataforma

Crie um OneLink multiplataforma para inserir no SMS. Ao criar o link, você tem a opção de definir o canal de mídia e a campanha. Sugerimos que você defina o canal de mídia e a campanha da seguinte forma:

* canal de mídia: website
* campanha: text-me-the-app

Ao enviar o OneLink por SMS, é melhor usar a versão curta do link do OneLink.

Para saber como criar o link, veja <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">aqui</Anchor>.

<div id="set-up-an-sms-topic-in-your-sms-provider-account" />

### Configure um tópico de SMS na conta do seu provedor de SMS

Nesta etapa, você cria um tópico ou mensagem de SMS que contém o OneLink para o aplicativo. Esse SMS é enviado quando os usuários preenchem e enviam um formulário com o número de telefone deles. Quando os usuários enviam o formulário, seu backend recebe a solicitação e se comunica com a API do provedor de SMS para enviar o link.

<div id="set-up-a-web-form-to-collect-phone-numbers" />

### Configure um formulário web para coletar números de telefone

No seu website, nas páginas que você escolher, configure um call-to-action para incentivar os usuários a instalar o aplicativo. O call-to-action deve abrir um formulário web por meio do qual os usuários possam enviar seus números de telefone.

<div id="apply-logic-in-your-backend" />

### Aplique lógica no seu backend

Ao enviar o formulário, o website deve enviar uma solicitação ao seu backend. O backend recebe o número de telefone e envia uma solicitação ao provedor de SMS para enviar por SMS um link para o aplicativo ao telefone do usuário.

Consulte a API e a documentação do seu provedor de SMS para saber como criar a lógica no seu backend.

<div id="how-attribution-works-when-sending-a-link-to-the-app" />

## Como a Atribuição funciona ao enviar um link para o Aplicativo

 Não há como incluir o ID de publicidade ao enviar por mensagem de texto um link para o aplicativo para usuários de desktop. Portanto, a AppsFlyer recorre à <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">Atribuição usando Modelo probabilístico</Anchor>.

A AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows#janela-de-lookback-de-modelagem-probabilística">limita a janela de lookback</Anchor> para cliques de Modelo probabilístico para manter a precisão. Os limites são:

* iOS: até 24 horas
* Android (Google Play): até uma hora
* Android (fora da loja): até 24 horas

Incentive seus usuários a instalar o mais próximo possível do clique para que a AppsFlyer possa atribuir com precisão a instalação ao link enviado por mensagem de texto. Você pode fazer isso oferecendo cupons, descontos ou créditos de jogo.

<div id="people-based-attribution" />

## Atribuição baseada em pessoas

Há outras formas, além de enviar por mensagem de texto um link para o aplicativo, pelas quais os usuários convertem da web para o aplicativo. Nem sempre fica claro de onde esses usuários vêm e quais canais de mídia e campanhas contribuem para a conversão deles.

Para ter mais insights sobre quantos usuários da web se convertem em usuários de app mobile e quais canais de mídia e campanhas estão envolvidos no processo, use a Atribuição baseada em pessoas.

A Atribuição baseada em pessoas (PBA) reúne dados de campanhas da web e de app mobile. Os dados consolidados ajudam você a analisar as jornadas dos usuários entre plataformas e a transição dos usuários da web para apps mobile.

Para saber mais, consulte <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">aqui</Anchor>.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01KQS4E94MVN7NEEDR7ESA17K9=introdu%C3%A7%C3%A3o h_01KQS4E94MSP2PQ0RVAHS2JY8R=nota requirements=requisitos h_01KQS4E94MVYA0EZ7Y0FCMZEBC=requisitos setting-up=configura%C3%A7%C3%A3o h_01KQS4E94MF2BZZ5AXP67R7YRW=configura%C3%A7%C3%A3o sms-provider-account-to-text-a-link-to-the-app=conta-em-provedor-de-sms-para-enviar-um-link-para-o-aplicativo h_01KQS4E94MYPEBKN80CNHCV1DG=conta-em-provedor-de-sms-para-enviar-um-link-para-o-aplicativo a-backend-environment-to-communicate-with-the-sms-provider=um-ambiente-de-backend-para-se-comunicar-com-o-provedor-de-sms h_01KQS4E94MW7DWRGPNX8D98W46=um-ambiente-de-backend-para-se-comunicar-com-o-provedor-de-sms a-multiplatform-custom-link=um-link-multiplataforma-personalizado h_01KQS4E94MP2Q29S7892GGT0QM=um-link-multiplataforma-personalizado texting-the-app-to-users=enviar-o-aplicativo-por-sms-aos-usu%C3%A1rios h_01KQS4E94MGBCX0TM5AGHXPX0Z=enviar-o-aplicativo-por-sms-aos-usu%C3%A1rios create-a-multiplatform-onelink=criar-um-onelink-multiplataforma h_01KQS4E94MQSWQ9S0CHNJG8B77=criar-um-onelink-multiplataforma set-up-an-sms-topic-in-your-sms-provider-account=configure-um-t%C3%B3pico-de-sms-na-conta-do-seu-provedor-de-sms h_01KQS4E94MG7KGB8HQVT11717J=configure-um-t%C3%B3pico-de-sms-na-conta-do-seu-provedor-de-sms set-up-a-web-form-to-collect-phone-numbers=configure-um-formul%C3%A1rio-web-para-coletar-n%C3%BAmeros-de-telefone h_01KQS4E94MNPRC5AJ9EJD4GPG3=configure-um-formul%C3%A1rio-web-para-coletar-n%C3%BAmeros-de-telefone apply-logic-in-your-backend=aplique-l%C3%B3gica-no-seu-backend h_01KQS4E94MA810B0QRSMDQ0FQM=aplique-l%C3%B3gica-no-seu-backend how-attribution-works-when-sending-a-link-to-the-app=como-a-atribui%C3%A7%C3%A3o-funciona-ao-enviar-um-link-para-o-aplicativo h_01KQS4E94MC8C19RCCPV52G7N1=como-a-atribui%C3%A7%C3%A3o-funciona-ao-enviar-um-link-para-o-aplicativo peoplebased-attribution=atribui%C3%A7%C3%A3o-baseada-em-pessoas h_01KQS4E94MJ0C6Q82H67R22S2W=atribui%C3%A7%C3%A3o-baseada-em-pessoas" />
