---
title: Usuários únicos
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-08-11T09:52:33Z'
  edited_at: '2026-08-18T00:09:59Z'
  id: 27435981457553
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/27435981457553
---
> **Visão geral:** Saiba como usuários únicos são contados e usados em métricas nos painéis e relatórios da AppsFlyer.

<div id="about-unique-users" />

## Sobre usuários únicos

Um usuário único é um termo que se refere a um dispositivo atribuído cuja presença é contada apenas uma vez, independentemente de quantas ações um usuário executa no dispositivo.

É um cálculo usado em uma ampla variedade de métricas de marketing, incluindo:

* Instalações: O número de usuários únicos que baixaram e instalaram o aplicativo.
* Taxa de retenção: Percentagem diária de usuários únicos com uma sessão.
* Usuários único do evento: Número de usuários únicos (atribuições) que executam o evento.
* Daily active users (DAU): Número de usuários únicos (contados apenas uma vez) que abriram o aplicativo pelo menos uma vez durante o dia.
* E muitos mais.

O cálculo de usuários únicos é baseado no ID do dispositivo (como IDFA ou GAID). Se nenhum ID de dispositivo estiver disponível (como para iOS SKAN), o ID do AppsFlyer será usado. Isso garante que um usuário seja contado uma vez, já que o ID do dispositivo ou o ID da AppsFlyer é o mesmo para todas as ações, independentemente de quantas sessões ou ações ele execute.

<div id="use-cases" />

## Casos de uso

Embora o cálculo de usuário único geralmente seja simples, às vezes surgem dúvidas sobre certos comportamentos ou ações do usuário. Os casos de uso a seguir explicam como usuários únicos são contados em algumas dessas instâncias mais complicadas.

<div id="install-and-reinstall" />

<Accordion title="Instalar e reinstalar">

<Image align="center" alt="" src="https://files.readme.io/8b9f3c442f98c056069b4449c7e5115cbea828a64ace3a98e0090fb0d8d1d8d6-27455116159889.png" />

A instalação e a reinstalação têm o mesmo ID do dispositivo/ID da AppsFlyer. Portanto, apenas 1 usuário único é contabilizado. Ambos os eventos in-app são atribuídos ao mesmo usuário único da primeira instalação.

**Observação**:

* Se uma reinstalação não incluir um ID de dispositivo/ID da AppsFlyer, ela não poderá ser conectada à primeira instalação e será considerada "orgânica não atribuída". Eventos pós-reinstalação após reinstalações orgânicas não atribuídas não são incluídos na contagem de usuários únicos.
* Pode haver outros motivos para que os eventos não sejam atribuídos como orgânicos. Nesses casos, os eventos também não são incluídos na contagem de usuários únicos.

</Accordion>

<div id="install-and-reattribution" />

<Accordion title="Instalação e reatribuição:">

<Image align="center" alt="" src="https://files.readme.io/40420c5ea201ba7cf13d03e5968d20c2fffaa31b74c47ae36cd917cccbaae353-27453973190289.png" />

A instalação e a reatribuição têm o mesmo ID do dispositivo/ID da AppsFlyer. Porém, neste caso, a AppsFlyer também leva em consideração o parâmetro `is_retargeting=true` portanto, o evento após a reatribuição é contado como um usuário único adicional. Portanto, 2 usuários únicos são contabilizados.

* No painel Visão geral, a visualização do UA exibe 1 usuário único, pois os reengajamentos de retargeting não são mostrados na visualização de UA. O mesmo vale para relatórios de UA.
* No painel Visão geral, a visualização de retargeting exibe 1 usuário único, pois as instalações de UA não são mostradas na visualização de retargeting. O mesmo vale para relatórios de retargeting.
* No painel Visão geral, a visualização unificada exibe 2 usuários únicos, 1 conectado à primeira instalação e o 2º conectado ao reengajamento. O mesmo vale para relatórios unificados.

</Accordion>

<div id="install-and-reengagement" />

<Accordion title="Instalação e reengajamento">

<Image align="center" alt="" src="https://files.readme.io/68da5544f49809910ae4618f509707a99962e601a7d5a6631a771318e33e1248-49929266336529.png" />

A instalação e o reengajamento têm o mesmo ID do dispositivo/ID da AppsFlyer. Porém, neste caso (assim como em reatribuições), a AppsFlyer também leva em consideração o parâmetro `is_retargeting=true` portanto, o evento após a reatribuição é contado como um usuário único adicional. Portanto, 2 usuários únicos são contabilizados.

* No painel Visão geral, a visualização do UA exibe 1 usuário único, pois as reatribuições de retargeting não são mostradas na visualização de UA. O mesmo vale para relatórios de UA.
* No painel Visão geral, a visualização de retargeting exibe 1 usuário único, pois as instalações de UA não são mostradas na visualização de retargeting. O mesmo vale para relatórios de retargeting.
* No painel Visão geral, a visualização unificada exibe 2 usuários únicos, 1 conectado à primeira instalação e o 2º conectado à reatribuição. O mesmo vale para relatórios unificados.

</Accordion>

<div id="unattributed-inapp-events" />

<Accordion title="Eventos in-app não atribuídos">

<Image align="center" alt="" src="https://files.readme.io/94bf078bcf4ba26a1dc4ca323a1b4a7543cfb4e3fc8b780d0d29713c4266aa95-27455116170001.png" />

Quando um evento in-app não é atribuído, ou seja, ocorre após uma reinstalação, mas por algum motivo não está vinculado à primeira instalação, ele não é incluído na contagem de usuários únicos. Isso pode ocorrer quando não há um ID de dispositivo disponível para a reinstalação, mas também pode haver outros motivos. <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#unattributed-organic-inapps">Saiba mais</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Atenção |
| --- | --- |
| Eventos de receita de anúncio<br /><br />(af\_ad revenue) | <ul><li>A contagem de usuários únicos é compatível com eventos de receita de anúncio para:<ul><li>Métricas diárias da coorte</li><li>Métricas de atividade</li><li>Métricas SKAN</li></ul></li><li>A contagem de usuários únicos não é compatível com eventos de receita de anúncio para:<ul><li>Métricas cumulativas de coorte</li><li>Métricas de LTV via método de atribuição clássico. **Observação**: Para esclarecer, isso significa que, ao analisar um painel com visualização SSOT, a métrica de usuário único para eventos de receita de anúncios está disponível para dados SKAN, mas não para dados de atribuição clássica.</li></ul></li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=sobre-usu%C3%A1rios-%C3%BAnicos 01H7Z1003GTTMRY072BXWDFNP0=sobre-usu%C3%A1rios-%C3%BAnicos use-cases=casos-de-uso h_01J52T4MT63JVJEQ050E2BXMVQ=casos-de-uso h_01J52T9B4ZZH1TBW98YM5MY675=install-and-reinstall h_01J52T9B4ZYWQAGS3QHG99G3AS=install-and-reattribution h_01J531V2AKW8QP33B6K8QFH72R=install-and-reengagement h_01J52WPCZEBFP4RR0Y4ZC5TABK=unattributed-inapp-events h_01J52ZHXKYDG77PE70QZV63KY3=traits-and-limitations" />
