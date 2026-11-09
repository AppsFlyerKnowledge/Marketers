---
title: Explicando a janela de reatribuição
metadata:
  keywords:
    - Retargeting
    - Re-Attribution
    - reattribution
    - Advertisers
    - Ad Networks
    - re-attribution window
    - reattribution window
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-05-23T08:55:35Z'
  edited_at: '2026-08-18T00:09:55Z'
  id: 115002587066
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/115002587066
---
> **Resumo:** Visão geral: conheça a janela de reatribuição, durante a qual as reinstalações não são atribuídas como novas instalações.

<div id="re-attribution-window" />

## Janela de reatribuição

A janela de reatribuição é um período de tempo que começa na primeira vez que um usuário instala o aplicativo e continua por uma duração definida pelo anunciante (padrão de 90 dias). Durante a janela de reatribuição, os aplicativos reinstalados não são registrados como novas instalações e não geram um novo postback de instalação, a menos que tenham origem em uma campanha de **retargeting**.

<Image align="center" alt="ReAttributionWindow_us-en.png" src="https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png" />

<div id="setting-the-re-attribution-window" />

### Configurando a janela de reatribuição

A janela de reatribuição:

* É configurada na página  <Anchor target="_blank" href="/marketers/pt/docs/app-settings">Configurações do aplicativo</Anchor>
* Seu valor padrão é 90 dias (3 meses)
* Tem um intervalo de 1 a 24 meses

As instalações são avaliadas com relação à configuração no momento da instalação. Assim, se você mudar a configuração, isso terá um impacto sobre as futuras instalações (reinstalações) sem considerar as instalações anteriores.

* **Alterar a janela de reatribuição de 90 para 30 dias**:
  * Instalar em 1º de setembro.
  * A janela de reatribuição muda em 2 de setembro.
  * Uma reinstalação até 1º outubro é considerada uma reinstalação. A partir de 2 de outubro, ela é considerada como uma nova instalação.
* **Alterar a janela de reatribuição de 30 para 90 dias**:
  * Instalar em 1º de setembro.
  * A janela de reatribuição muda em 2 de setembro.
  * Uma reinstalação em 15 de outubro é considerada uma reinstalação por causa da janela atual de 90 dias.
  * Uma reinstalação em 15 de dezembro é considerada uma nova instalação porque já se passaram mais de 90 dias desde a instalação em 1º de setembro.

<div id="re-attribution-window-use-cases" />

## Casos de uso da janela de reatribuição

<div id="first-install" />

<Accordion title="Primeira instalação">

Um lead (que nunca teve o aplicativo instalado) engaja com uma campanha de aquisição ou retargeting de usuários e instala o aplicativo mobile.

Em seguida:

* Uma nova instalação (ou uma instalação orgânica, se não for registrado nenhum engajamento), é atribuída ao canal de mídia nos dashboards de aquisição de usuários e dados
* Uma nova janela de reatribuição começa
* Os postbacks de instalação e de eventos in-app são enviados para o canal de mídia atribuído quando configurados.
* Os seguintes eventos in-app também são atribuídos ao mesmo canal de mídia

</Accordion>

<div id="reinstall" />

<Accordion title="Reinstalação">

Após a primeira instalação do aplicativo, o usuário o desinstala e reinstala durante a janela de reatribuição.

Em seguida:

* A instalação NÃO é atribuída - não aparece no dashboard, nem nos dados
* NENHUM postback de instalação é enviado para qualquer canal de mídia
* Dependendo do estado da <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#overview">**Atribuição de eventos pós-reinstalação**</Anchor> , os eventos na aplicação desses utilizadores são atribuídos como orgânicos ou à instalação original.

</Accordion>

<div id="reattribution" />

<Accordion title="Re-atribuição">

Após a primeira instalação do aplicativo, durante a janela de reatribuição, o usuário desinstala, depois se engaja com uma campanha de retargeting e reinstala.  
Isto é chamado de reatribuição.

Em seguida:

* A instalação é atribuída ao canal de mídia de retargeting nas visualizações de retargeting e na visão unificada do dashboard de Visão Geral. Em outras palavras, a visualização de aquisição do usuário não contém reatribuições.
* Todos os eventos a seguir são atribuídos ao canal de mídia de retargeting
* Um postback de instalação é enviado para o canal de mídia de retargeting

Para mais informações sobre a atribuição de retargeting, clique <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">aqui</Anchor>.

</Accordion>

<div id="new-install" />

<Accordion title="Nova instalação">

O usuário desinstala o aplicativo. Então, após o término da janela de reatribuição, o usuário reinstala. Essa reinstalação é considerada uma primeira instalação e traz os mesmos resultados:

* Uma nova instalação (ou uma instalação orgânica, se não for registrado nenhum engajamento), é atribuída ao canal de mídia nos dashboards de aquisição de usuários e dados
* **Uma nova janela de reatribuição começa**
* Os postbacks de instalação e de eventos in-app são enviados para o canal de mídia atribuído quando configurados.
* Os seguintes eventos in-app também são atribuídos ao mesmo canal de mídia

</Accordion>

<div id="ios-app-restored-from-icloud-backup" />

<Accordion title="Aplicativo iOS restaurado do backup do iCloud">

Independentemente da janela de reatribuição, quando um aplicativo passa pelo backup do iCloud e, posteriormente, é restaurado (no mesmo dispositivo ou em outro dispositivo), a AppsFlyer não considera isso como uma nova instalação ou reinstalação. Um utilizador que restaura uma app do iCloud mantém o seu ID AppsFlyer e os dados de atribuição.

</Accordion>

<div data-zendesk-anchors="reattribution-window=janela-de-reatribui%C3%A7%C3%A3o h_01H95B0F8XEX9RFXW8W6QBQJBY=janela-de-reatribui%C3%A7%C3%A3o setting-the-reattribution-window=configurando-a-janela-de-reatribui%C3%A7%C3%A3o h_01H95B0F8X2YQWBB9H0WFXPK8C=configurando-a-janela-de-reatribui%C3%A7%C3%A3o reattribution-window-use-cases=casos-de-uso-da-janela-de-reatribui%C3%A7%C3%A3o h_01H95B0F8Y4T13VYEN2D7T5GHR=casos-de-uso-da-janela-de-reatribui%C3%A7%C3%A3o h_01H95B0F8Y58QFRSJ9TV3J34EX=first-install h_01H95B0F8YBY482KHT09CZNT9E=reinstall h_01H95B0F8YCQV3H6ZSZE0DF5VV=reattribution h_01H95B0F8Y046Q80V0S8YZ1DWG=new-install h_01H95B0F8Y6M7W02ZSNYCN66PD=ios-app-restored-from-icloud-backup" />
