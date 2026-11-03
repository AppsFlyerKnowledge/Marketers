---
title: Discrepâncias de atribuição entre TikTok for Business e AppsFlyer
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-08-18T00:32:57Z'
  id: 19733501619473
  locale: pt
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/pt/articles/19733501619473
---
> **Em resumo:** Conheça as diferenças nos modelos de atribuição entre TikTok for Business e AppsFlyer.

## Resumo Geral

Sendo ambos importantes no ecossistema de aquisição de utilizadores móveis, TikTok for Business e AppsFlyer utilizam modelos de atribuição diferentes. Isto pode originar discrepâncias entre os dashboards do TikTok for Business e da AppsFlyer. Embora trabalhamos em estreita colaboração com o TikTok for Business para reduzir essas discrepâncias, os anunciantes devem estar atentos às possíveis causas.

## Diferenças nos modelos de atribuição

A tabela abaixo descreve as possíveis razões para as discrepâncias entre o TikTok Ads Manager e os dashboards da AppsFlyer:

<table><thead><tr><th>Motivo</th><th>Gestor de Anúncios TikTok</th><th>A AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Janela de retrospetiva da atribuição por clique</strong></p></td><td><p>A janela padrão é de 7 dias. No entanto, pode ser configurada de forma diferente para aplicações Android e para as que foram transferidas para a autoatribuição do TikTok (TikTok—SRN).</p></td><td><p>A janela padrão é de 7 dias. A janela pode ser ajustada entre 1 e 30 dias. Assegure-se de alinhar com a janela de atribuição do TikTok.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Janela de retrospetiva da atribuição por visualização</strong></p></td><td><p>A janela padrão é de 1 dia. No entanto, pode ser configurada de forma diferente para aplicações Android e para as que foram transferidas para a autoatribuição do TikTok (TikTok—SRN).</p></td><td><p>A janela padrão é de 1 dia. A janela pode ser ajustada entre 1 e 48 horas. Assegure-se de alinhar com a janela de atribuição do TikTok.</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Atribuição de fonte multicanal</strong></p></td><td><p>O TikTok autoatribui instalações independentemente de outras fontes de mídia.</p></td><td><p>A AppsFlyer utiliza a atribuição pelo último clique (saiba mais sobre o <a href="./appsflyer-attribution-model" target="_blank">modelo de atribuição da AppsFlyer</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Atribuição entre dispositivos</strong></p></td><td><p>O TikTok atribui aos utilizadores que realizam ambas as ações de engajamento e instalação usando diferentes dispositivos, como iOS, Android e desktop.</p></td><td><p>A AppsFlyer atribui aos utilizadores só quando o engajamento e instalação ocorrem no mesmo dispositivo.</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Fusos horários diferentes</strong></p></td><td><p>O <a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">fuso horário do TikTok</a> (mostrado ao lado do intervalo de datas) não pode ser ajustado. Foi definido ao criar a conta de anúncios.</p></td><td><p>O fuso horário padrão na AppsFlyer é UTC+0. Para corresponder ao fuso horário no TikTok Events Manager, altere o fuso horário na <a href="./app-settings#localization-time-zone" target="_blank">página de configurações da aplicação</a>.</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>Atribuição no iOS</strong></p></td><td><p>Para apps iOS, o gestor de anúncios do TikTok mostra apenas resultados de atribuição SKAN.</p></td><td><p>Para apps iOS, a AppsFlyer exibe resultados de atribuição SKAN juntamente com a atribuição da AppsFlyer para SRNs e SRNs avançados, além de dados SSOT sem duplicação. Esperamos que apenas os dados SKAN correspondam em ambas as plataformas. </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>Períodos de atribuição de eventos in-app</strong></p></td><td colspan="2"><p>A atribuição em cada plataforma pode variar com base nas janelas de tempo desde a instalação inicial:</p></td></tr><tr><td><span id="day-1-90"></span><p>Dia 1-90</p></td><td colspan="2"><p>Sem discrepâncias na atribuição. Ambas as plataformas atribuem eventos in-app ao tempo de instalação.</p></td></tr><tr><td><span id="day-91-180"></span><p>Dia 91-180</p></td><td rowspan="2"><p>Após 90 dias, os eventos in-app não são relatados no TikTok.</p></td><td><div><div><div>A AppsFlyer continua a atribuir os eventos in-app ao horário de instalação.</div></div></div></td></tr><tr><td><span id="day-180"></span><p>Dia 180+</p></td><td><div><div><div>Devido à <a href="./user-level-data-retention#períodos-de-retenção-de-dados-de-parceiros" target="_blank">política de retenção de dados do TikTok</a>, os eventos in-app passam a ser atribuídos como orgânicos.</div></div></div></td></tr></tbody></table>

## Diferenças nas instalações

Em alguns casos, o TikTok for Business inclui instalações que a AppsFlyer rejeita ou não as considera novas.

### Campanhas de reengajamento

Uma campanha de reengajamento pode fazer com que os utilizadores abram uma app já instalada (**reengajamento**). Quando a AppsFlyer detecta uma instalação prévia da app no mesmo dispositivo, refere-se a essa conversão como uma **reatribuição**.

Os utilizadores são registados na AppsFlyer como **novas aquisições** se instalarem a app pela primeira vez através de uma campanha de reengajamento do TikTok for Business. Adicionalmente, se os utilizadores instalarem a app depois da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição designada</Anchor> **após a instalação inicial, são também considerados novas aquisições.**

Por outro lado, as instalações que ocorram **durante a janela de reatribuição definida** após a instalação original são classificadas como reatribuições. Estas instalações estão visíveis na página de retargeting da AppsFlyer. Contudo, podem ser consideradas novas instalações pelo TikTok for Business.

### Instalações rejeitadas ao utilizar regras de validação e Protect360

As <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação</Anchor> e o <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor> são funcionalidades da AppsFlyer que proporcionam proteção adicional ao rejeitar (bloquear) certas instalações. Ao usar estas funcionalidades, as instalações rejeitadas provenientes do TikTok for Business são bloqueadas pela AppsFlyer, enquanto o TikTok for Business auto-relata essas instalações.

> 📄 **Exemplo**
>
> Jeff, gestor de aquisições da GreatApp, cria uma campanha chamada SPNA, direcionada apenas para falantes de espanhol na América do Norte. Para garantir isso, Jeff estabelece uma regra de validação que apenas aceita utilizadores do Canadá e dos EUA.
> Quando um utilizador do TikTok for Business em Espanha clica e instala a aplicação, o TikTok for Business reporta essa instalação automaticamente, enquanto a AppsFlyer rejeita a instalação que não cumpre a regra de validação.

## Redução de Discrepâncias

Ainda que existam diferenças nos modelos de atribuição, em alguns casos, é possível reduzir as discrepâncias.

### Atribuição por Clique e Visualização

A AppsFlyer suporta tanto a atribuição por clique como por visualização. Para reduzir discrepâncias entre o TikTok for Business e a AppsFlyer, garanta que as janelas de lookback de clique e visualização são consistentes com as definidas pelo TikTok for Business.

> 📄 **Exemplo**
>
> Imagine que a janela de lookback de cliques do TikTok for Business está configurada na AppsFlyer para 1 dia para a sua aplicação `com.greatapp`, enquanto no TikTok for Business está configurada para o valor padrão de 7 dias. Os utilizadores que clicam no anúncio da Greatapp no TikTok, mas lançam a aplicação pela primeira vez após 2 a 7 dias, são atribuídos como utilizadores orgânicos na AppsFlyer, enquanto o TikTok for Business reporta estes utilizadores automaticamente.

### Atribuição de Eventos na Aplicação

As diferenças entre plataformas podem também estar presentes em eventos pós-instalação (por exemplo, compras na aplicação), que são exibidos no TikTok for Business e na AppsFlyer. A tabela seguinte apresenta os motivos mais comuns para estas diferenças e sugere como reduzi-las:

| Motivo | Descrição | Sugestão da AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Autoatribuição** | O TikTok atribui sempre as instalações e os eventos às suas próprias campanhas, enquanto a AppsFlyer os atribui à fonte de aquisição. Tais eventos são indicados como assistências do TikTok na AppsFlyer. | Combine os dados brutos das conversões atribuídas ao TikTok com os dados brutos em que o TikTok é o contribuidor. |
| <span id="unmapped-events"></span>**Eventos não mapeados** | A AppsFlyer recebe eventos originados pelo SDK, mas estes não são mapeados para o TikTok for Business e, portanto, não são enviados. | Garanta <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#postbacks-de-eventos-in-app">o mapeamento com o TikTok for Business</Anchor> para eventos na aplicação que indiquem a qualidade do utilizador. |
| <span id="unsent-revenue"></span>**Receita não enviada** | A AppsFlyer obtém a receita dos eventos originados pelo SDK, mas ela não é enviada para o TikTok for Business. | Assegure-se de incluir a receita ao <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#postbacks-de-eventos-in-app">mapear eventos in-app do TikTok for Business</Anchor>. |
| <span id="missing-event-values-on-tiktok"></span>**Falta de valores de eventos no TikTok for Business** | A AppsFlyer envia parâmetros e valores para o TikTok for Business como parte do mapeamento de eventos, desde que tenham as estruturas corretas. | Desenvolva os seus eventos in-app no SDK de acordo com as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">estruturas recomendadas pela AppsFlyer</Anchor> para mapear completamente os valores dos eventos com o TikTok for Business. |

<div data-zendesk-anchors="overview=resumo-geral h_01HFXTVVZNJQJFAAR1F3HW1D5M=resumo-geral differences-in-attribution-models=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o h_01HFXTVVZN79JX9E5PTXMPB8BS=diferen%C3%A7as-nos-modelos-de-atribui%C3%A7%C3%A3o differences-in-installs=diferen%C3%A7as-nas-instala%C3%A7%C3%B5es h_01HFXTVVZNDQKNW85BBWR0PE2Z=diferen%C3%A7as-nas-instala%C3%A7%C3%B5es reengagement-campaigns=campanhas-de-reengajamento h_01HFXTVVZNA1R59KCA41H2YSBJ=campanhas-de-reengajamento rejected-installs-when-using-validation-rules-and-protect360=instala%C3%A7%C3%B5es-rejeitadas-ao-utilizar-regras-de-valida%C3%A7%C3%A3o-e-protect360 h_01HFXTVVZNJVFHE0W5DTP5PDCG=instala%C3%A7%C3%B5es-rejeitadas-ao-utilizar-regras-de-valida%C3%A7%C3%A3o-e-protect360 01H890CZSYCTQZCAYAZP9TCBBF=exemplo minimizing-discrepancies=redu%C3%A7%C3%A3o-de-discrep%C3%A2ncias h_01HFXTVVZNW9GZB8QYMR1KTNMN=redu%C3%A7%C3%A3o-de-discrep%C3%A2ncias clickthrough-and-viewthrough-attribution=atribui%C3%A7%C3%A3o-por-clique-e-visualiza%C3%A7%C3%A3o h_01HFXTVVZNN45WY997DK9K8WA4=atribui%C3%A7%C3%A3o-por-clique-e-visualiza%C3%A7%C3%A3o h_01HFRQMF6HTT84J4EDFXZMK7CP=exemplo-1 inapp-event-attribution=atribui%C3%A7%C3%A3o-de-eventos-na-aplica%C3%A7%C3%A3o h_01HFXTVVZNG7TKQVY1229X594G=atribui%C3%A7%C3%A3o-de-eventos-na-aplica%C3%A7%C3%A3o" />
