---
title: Integração do Tealium com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2026-08-18T00:12:31Z'
  id: 10820404821393
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/10820404821393
---
> **Visão geral:** Tealium, uma plataforma de dados do cliente (CDP), conecta os dados do cliente na web, dispositivos móveis, IoT e offline. Saiba como compartilhar dados de conversão automaticamente com o Tealium.

<Image align="center" alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

<div id="overview" />

## Visão geral

Ao integrar o Tealium com a AppsFlyer, os clientes com dispositivos móveis podem usar o SDK de atribuição mobile da AppsFlyer para enviar dados de atribuição de conversão diretamente para o perfil Tealium AudienceStream.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para este parceiro, independentemente da seleção configurada para envio de postbacks.

<div id="setting-up-tealium" />

## Configurando o Tealium

Você pode escolher uma das seguintes formas de integrar o Tealium com a AppsFlyer:

* Integração do cliente
* Integração do servidor

<div id="client-side-integration" />

### Integração do cliente

Use comandos remotos para bibliotecas iOS e Android, permitindo que o código nativo seja acionado no SDK da AppsFlyer.

**Para integrar o Tealium usando a integração do cliente:**

* Siga o <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">guia de integração de comando remoto</Anchor>

<div id="server-side-integration" />

### Integração do servidor

Configure o conector do AppsFlyer App Events em sua conta do Customer Data Hub para transmitir dados entre o Tealium e a AppsFlyer em tempo real.

**Para integrar o Tealium usando a integração do servidor:**

* Siga o <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">guia do conector do AppsFlyer App Events</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01H9HWK1ACY09ZVD7WHEQR4MR3=vis%C3%A3o-geral h_01H9HWK1ACA6A743PDY3Q1Y0KV=importante setting-up-tealium=configurando-o-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=configurando-o-tealium clientside-integration=integra%C3%A7%C3%A3o-do-cliente h_01H9HWK1ACH6K0FDTVCHAPSKME=integra%C3%A7%C3%A3o-do-cliente serverside-integration=integra%C3%A7%C3%A3o-do-servidor h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=integra%C3%A7%C3%A3o-do-servidor" />
