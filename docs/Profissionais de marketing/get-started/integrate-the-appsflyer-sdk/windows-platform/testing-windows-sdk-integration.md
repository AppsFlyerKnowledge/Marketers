---
title: Testando a integração do SDK do Windows
metadata:
  keywords:
    - Testing
    - Windows
    - SDK
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
  created_at: '2016-11-15T12:35:48Z'
  edited_at: '2026-08-19T00:15:19Z'
  id: 217924503
  locale: pt
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/pt/articles/217924503
---
> **Visão geral:** teste a integração do seu aplicativo do Windows com a AppsFlyer.

* Atualmente, não há outra maneira de testar com o Windows Referrer além de enviar o aplicativo para a Windows App Store.
* Ao testar com o Windows Referrer, você deve estar ciente das seguintes restrições:
  * Você deve estar conectado à loja.
  * Seu dispositivo não deve ter a atualização Windows 10 Anniversary Update.
  * Seu dispositivo nunca deve ter tido o aplicativo (o referrer do Windows é vitalício — mesmo se você estiver na allowlist ou tiver aguardado mais de 90 dias, não receberá atribuição de referrer).

<div id="test-sdk-integration" />

## Teste a integração do SDK

1. É obrigatório testar a integração do SDK em um dispositivo de teste registrado. Para registrar seu dispositivo de teste, siga as etapas <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">aqui</Anchor>.
2. Abra o dashboard da AppsFlyer e escolha o aplicativo que está testando.
3. Selecione SDK Integration Tests no menu de navegação.
4. Três opções de testes são apresentadas:

* Instalação não orgânica
* https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg
* Deep linking

<Image align="center" alt="" src="https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png" />

<div id="testing-non-organic-install" />

## Testando instalações não orgânicas

1. Selecione um dos seus dispositivos registrados na lista suspensa
2. Selecione de onde está instalando o aplicativo (Windows Store ou Outro)
3. Escaneie o QR code gerado com seu dispositivo de teste registrado e siga as instruções no dispositivo.
4. Aguarde até que a instalação não orgânica seja registrada na página de teste de integração, indicando que o teste foi bem-sucedido. Isso pode levar até dois minutos. Se o aplicativo não registrar uma instalação não orgânica até esse momento, consulte o guia de solução de problemas exibido na página de teste de integração.

<div id="testing-in-app-events" />

## Teste de eventos in-app

1. Selecione um dos seus dispositivos de teste registrados no menu suspenso e clique em Next.
2. Abra seu aplicativo e comece a gerar eventos in-app.
3. Você verá um registro desses eventos conforme eles são registrados em tempo real.

<div id="testing-deep-linking" />

## Testando deep linking

1. O OneLink deve ser definido no seu aplicativo para testar o Deep Linking. Consulte <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">o guia do OneLink</Anchor>
2. Selecione um dos seus dispositivos de teste registrados no menu suspenso e clique em Next.
3. Escaneie o QR code com seu dispositivo de teste registrado e siga as instruções no seu dispositivo.
4. Aguarde até que o link profundo seja registrado com sucesso na página de teste de integração.

<div data-zendesk-anchors="test-sdk-integration=teste-a-integra%C3%A7%C3%A3o-do-sdk testing-nonorganic-install=testando-instala%C3%A7%C3%B5es-n%C3%A3o-org%C3%A2nicas testing-inapp-events=teste-de-eventos-in-app testing-deep-linking=testando-deep-linking" />
