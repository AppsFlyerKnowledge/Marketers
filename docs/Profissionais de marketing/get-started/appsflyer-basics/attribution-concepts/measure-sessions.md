---
title: Medir sessões
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2026-08-18T00:09:45Z'
  id: 360000520785
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/360000520785
---
> **Visão geral**: A métrica das sessões é utilizada pelos anunciantes para medir o engajamento dos usuários do app durante um determinado período.

<Image alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

<div id="sessions-counting-principles" />

## Princípios de contagem das sessões

O número de sessões, também conhecido como lançamento, realizadas pelos usuários é uma métrica importante e utilizada como medida do envolvimento do usuário com o app. Isso está disponível através de vários relatórios e painéis. As sessões são usadas para obter as seguintes métricas:

* Usuários diariamente ativos (DAU)
* Usuários ativos mensais (MAU)
* Retenção
* Usuários fidelizados que usam a configuração padrão de 3 apps abertos

**Atenção!** No caso das sessões orgânicas, a métrica está disponível nos painéis Atividade e Coorte, mas não está disponível no painel Visão geral.

<div id="sessions-calculation" />

### Cálculo das sessões

A métrica de sessões é calculada usando o evento *af\_app\_opened* reportado pelo SDK. No lado do servidor, as 5 primeiras sessões são contabilizadas sem considerar o intervalo de tempo entre elas. Um mecanismo de tempo mínimo entre sessões regula as sessões que são contadas no lado do servidor.

O *evento af\_app\_opened* é apresentado como *inicialização* nos dados brutos das sessões disponíveis através do Data Locker. As sessões não estão disponíveis através de outras ferramentas de relatório. Para facilitar a compreensão, neste artigo, usaremos o termo *af\_app\_opened*.

**Relatórios das sessões**

Uma sessão é comunicada pelo SDK quando ocorre uma das seguintes situações:

* Um usuário inicia o aplicativo.
* Quando o app é trazido do segundo plano para o primeiro plano. O desenvolvedor pode alterar o comportamento do relatório chamando [setMinTimeBetweenSessions.](/docs/measure-sessions#session-reporting-by-the-app-sdk)
* Um relatório de sessão explícito pelo desenvolvedor em apps Android. Por exemplo, isto é implementado por apps utilitários que estão sempre em segundo plano.

**Métrica das sessões**

A métrica de sessões é contabilizada a partir da primeira sessão. A métrica de sessões é contada depois de considerar um tempo mínimo entre o mecanismo de sessões com uma duração predefinida de 10 minutos, conforme descrito no exemplo que se segue.

<div id="minimum-time-between-sessions-mechanism" />

## Mecanismo de tempo mínimo entre sessões

O mecanismo tem impacto na contagem das sessões. **Atenção!** Considere que se o tempo mínimo entre sessões for longo, mais de uma hora, e os usuários não abrirem o app muitas vezes por dia, algumas métricas relacionadas com as sessões, como DAU e a retenção, podem ser impactadas. Isto é especialmente verdadeiro no caso dos apps em que os usuários abrem o app normalmente uma vez por dia. 

<div id="description-and-example" />

<Accordion title="Descrição e exemplo">

O mecanismo regula as sessões que são contadas. Uma sessão é contada se o tempo mínimo permitido entre sessões tiver passado.

O fluxo é o seguinte: Uma sessão é contada → É iniciado um temporizador de contagem regressiva → As sessões reportadas durante a contagem regressiva são ignoradas.

**Exemplo**

Pressuposto: O tempo mínimo permitido entre as definições das sessões é de 10 minutos.

| Caso de exemplo | Tempos de relatório da sessão (número de minutos desde as 00:00) | Número de sessões contadas | Sessões ignoradas |
| --- | --- | --- | --- |
| E | 0, 10, 20, 30 | 4 | Nenhum |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="Definição do temporizador">

* Valor padrão: 10 Minutos
* Os valores possíveis são:

  * 1-60 Minutos
  * 1 a 24 horas

**Para definir o tempo mínimo permitido entre sessões do temporizador:**

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Configurações do aplicativo**.
2. Definir o **Tempo mínimo entre sessões.**
3. Clique em **Salvar definições**.   
   A alteração entra em vigor no prazo de uma hora.

</Accordion>

<div id="sessions-related-topics" />

## Tópicos relacionados com as sessões

<div id="retargeting-sessions" />

<Accordion title="Sessões de retargeting">

* As sessões de retargeting estão disponíveis a partir de 12 de julho de 2020.
* As sessões de retargeting estão disponíveis em:
  * Retargeting e tipo de visualização unificada no painel de visão geral.
  * As visualizações de Cohort relevantes, ou seja, retargeting e unificada. 
    * No caso da exibição unificada, se as sessões foram atribuídas a uma fonte de mídia de UA e retargeting, a fonte de mídia de retargeting prevalecerá e a fonte de mídia de UA não será exibida.
    * Atualização dos dados Diariamente, às 13:00 UTC.
  * Data Locker: Os relatórios de sessões de retargeting podem ser ativados; eles incluem sessões de reengajamento e de reatribuição. 
    * Atualização dos dados Atraso de 6 horas.
* Durante as janelas de reengajamento, as sessões são atribuídas tanto ao UA como ao canal de mídia de retargeting. Da mesma forma, outros eventos in-app de reengajamento são <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">duplamente atribuídos</Anchor>.
* No caso do Google Ads e do X Ads, para evitar postbacks duplicados, o evento *af\_app\_opened* é enviado uma vez.

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="Sessões de postbacks para parceiros">

É possível enviar postbacks de sessões de parceiros para que seja enviado um <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">postback</Anchor> para cada sessão contada.

* Para enviar o postback: Mapeie explicitamente *af\_app\_opened* para um evento de parceiro. Atenção! No relatório de dados brutos da AppsFlyer, disponível através do Data Locker, este evento é refletido como uma *inicialização.*
* Considere que este é um evento de grande volume e que muitos parceiros não querem recebê-lo.

<div id="note" />

> 📘 **Observação**
>
> O mapeamento de `af_app_opened` só é compatível com parceiros que têm a opção **Enviar Sessões** ativada.

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="Relatório de sessão pelo app (SDK)">

**Lado do app:** O SDK envia *af\_app\_opened* sempre que o app é aberto ou trazido para o primeiro plano depois de considerar a definição *setMinTimeBetweenSessions* do SDK.

**Do lado do servidor:** As sessões reportadas pelo app são contadas e registradas tendo em conta o mecanismo de tempo mínimo entre sessões. As sessões contadas são atribuídas utilizando as mesmas <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">regras de atribuição</Anchor> que outros eventos in-app.

<div id="explicit-sessions-reporting-by-the-developer-android-apps-only" />

#### **Comunicação explícita de sessões pelo desenvolvedor (apenas aplicações Android)**

Use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession">logSession</Anchor> no Android para reportar explicitamente uma sessão. Não está disponível uma chamada equivalente no iOS.

* Os apps que funcionam continuamente em segundo plano podem exigir alguma lógica implementada pelo desenvolvedor para reportar sessões. Por exemplo, apps utilitários como os economizadores de bateria, os inicializadores, os bloqueios de tela e os apps antivírus. Para estes tipos de apps, considere a possibilidade de comunicar uma sessão diariamente à meia-noite ou em outro intervalo adequado ao app.
* Em outros casos, talvez você queira contar as sessões quando os usuários realizam alguma ação in-app, como apertar o botão de *limpar a memória*, etc.

<div id="setting-minimum-time-between-app-launches" />

#### **Definir o tempo mínimo entre inicializações de apps**

No SDK, defina o tempo mínimo que pode decorrer entre duas sessões para que elas sejam reportadas separadamente.

Use ***setMinTimeBetweenSessions,*** ou seja evento af\_app\_opened, para controlar o período mínimo de tempo que deve decorrer entre sessões para que cada uma delas seja relatada.

* [Padrão] cinco segundos. Isto significa que têm de passar pelo menos 5 segundos antes de ser comunicada outra sessão.
* A API permite definir o tempo mínimo necessário entre sessões.

**A `setMinTimeBetweenSessions` referência do SDK:**

<Tabs>
<Tab title="Android">

Consulte [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions) a referência do Android SDK para:

</Tab>

<Tab title="iOS">

Consulte a seção [`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions) na referência do SDK do iOS

</Tab>

<Tab title="Unity">

Consulte [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions) a referência do Unity SDK

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=princ%C3%ADpios-de-contagem-das-sess%C3%B5es h_01HB8NDPNKERK1RR1Y09V2R2CC=princ%C3%ADpios-de-contagem-das-sess%C3%B5es sessions-calculation=c%C3%A1lculo-das-sess%C3%B5es h_01HB8NDPNKFW6S28A3TC7W5J3C=c%C3%A1lculo-das-sess%C3%B5es minimum-time-between-sessions-mechanism=mecanismo-de-tempo-m%C3%ADnimo-entre-sess%C3%B5es h_01HB8NDPNKF32E34M3CBJ6GMP8=mecanismo-de-tempo-m%C3%ADnimo-entre-sess%C3%B5es h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=t%C3%B3picos-relacionados-com-as-sess%C3%B5es h_01HB8NDPNKPTJX56Q2SVAB6V6T=t%C3%B3picos-relacionados-com-as-sess%C3%B5es h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=observa%C3%A7%C3%A3o h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=comunica%C3%A7%C3%A3o-expl%C3%ADcita-de-sess%C3%B5es-pelo-desenvolvedor-apenas-aplica%C3%A7%C3%B5es-android h_01HB8NTFMR3Y9GHFP3EWMAATHY=comunica%C3%A7%C3%A3o-expl%C3%ADcita-de-sess%C3%B5es-pelo-desenvolvedor-apenas-aplica%C3%A7%C3%B5es-android setting-minimum-time-between-app-launches=definir-o-tempo-m%C3%ADnimo-entre-inicializa%C3%A7%C3%B5es-de-apps h_01HB8NTMC1JYPDWYG9YC8RNSEQ=definir-o-tempo-m%C3%ADnimo-entre-inicializa%C3%A7%C3%B5es-de-apps" />
