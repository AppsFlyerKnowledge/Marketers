---
title: Explicando instalações auxiliadas
metadata:
  keywords:
    - Attribution
    - installs
    - Assisted
    - multi-touch
    - reporting
    - assisted intalls
    - Advertisers
    - Agencies
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
  created_at: '2015-12-24T10:21:25Z'
  edited_at: '2026-08-18T00:09:39Z'
  id: 207040506
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/207040506
---
> **Visão geral:** mensure o impacto mais amplo das fontes de mídia que engajaram seus usuários e deram assistência antes do último toque.

## Instalações assistidas

<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/assisted-installs-mobile-advertising-assists/">Instalações assistidas</Anchor> (também conhecidas como atribuição multi-touch) são instalações nas quais a fonte de mídia/campanha não foi responsável pelo último toque, mas recebeu um toque do usuário antes da instalação e durante a janela de atribuição, desempenhando um papel importante para a instalação final. Uma instalação pode incluir até 3 instalações assistidas.

Os dados analíticos de instalações assistidas estão disponíveis nos níveis da fonte de mídia e da campanha para medir o impacto mais amplo de cada fonte de mídia e campanha.

### Visualizar métricas de instalações assistidas no painel Visão geral

**Para visualizar instalações assistidas no painel Visão geral**:

1. Na AppsFlyer, no menu lateral, selecione **analisar** > **visão geral**.
2. Selecione o relatório de visão geral detalhada.
3. Vá até os gráficos de tendência temporal.
4. Selecione a dimensão **Fonte de mídia** ou **Campanha**.
5. Selecione a métrica **Instalações assistidas**.  
   O gráfico de instalações assistidas é exibido. O azul indica instalações não orgânicas e o laranja indica instalações assistidas. ![AssitedInstallWidget.png](https://files.readme.io/a2fb5fb1f7414ede9a96858e325688d0c60b2ff910e24bc86e5597160c7548ca-33302646504977.png)

### Por que as assistências são importantes?

Em muitos casos, os usuários potenciais se familiarizam com um aplicativo através da fonte que deu assistência, mas não finalizam a instalação por algum motivo. Assim, medir e reconhecer assistências é importante na otimização e métrica de campanhas.

### Relatórios de instalações auxiliadas

A AppsFlyer atribui até 3 ad networks contribuintes, além do canal que recebeu a atribuição final da instalação.

Nos dashboards e relatórios agregados, as ad networks contribuintes (que podem ser até 3) são consolidadas na métrica "instalações assistidas". Ou seja, 1 instalação pode incluir a participação de até 3 instalações assistidas.

Nos relatórios de dados brutos, os dados das ad networks contribuintes são categorizados em campos separados, dos colaboradores de 1 a 3.

[![](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)](https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png)

Para cada uma das redes contribuintes, o relatório de dados brutos inclui o seguinte:

* Nome da rede (Fonte de mídia)
* Nome da campanha
* Tempo de engajamento (tempo de toque)
* Tipo de engajamento (clique ou impressão)
* Nome da agência envolvida (parceiro), se houver
* Tipo de correspondência (<Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::cecc12c5">O mesmo que os tipos de correspondência de instalação.</Anchor>)

Veja os <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#relatórios-de-jornada-do-usuário">dados brutos da jornada do usuário.</Anchor>

> 📘 **Atenção**
>
> **Canais de mídia com restrições de dados em nível de usuário**
>  Se um <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">canal de mídia restringir dados em nível de usuário</Anchor>, ele não poderá ser atribuído como contribuinte ou assist para uma Atribuição vencedora. Isso significa que determinadas fontes não aparecem como contribuintes, mesmo que tenham engajado o usuário antes da instalação.

> 📘 **Atenção**
>
> Várias das principais ad networks <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">restringem o compartilhamento de seus dados com plataformas de terceiros</Anchor>, incluindo agências. Portanto, as instalações assistidas não aparecem no painel da agência para essas redes.

Nos relatórios de dados brutos, os dados das networks contribuintes são divididos em campos separados para **Contributors 1–3**.

### Campo de total de candidatos

Além dos campos **Contributors 1–3**, o campo `total_candidates` mostra o número de engajamentos (como cliques ou impressões) associados ao mesmo dispositivo no momento da instalação ou do reengajamento.

No entanto, nem todo engajamento contabilizado em `total_candidates` é elegível para atribuição. Por exemplo, alguns engajamentos podem ter sido:

* Fora da janela de lookback
* Bloqueados pela proteção contra fraude
* Afetados pelas configurações de integração do aplicativo ou do parceiro
* Sem atender de outra forma às condições de atribuição da AppsFlyer

Na prática, isso significa:

* Se a instalação foi atribuída a orgânico, é porque nenhum dos engajamentos em `total_candidates` atendeu a todas as condições exigidas para atribuição.
* Se não houver contribuidores, será pelo mesmo motivo: os engajamentos registrados em `total_candidates` não eram elegíveis para atuar como contribuidores.

Em resumo, `total_candidates` indica os engajamentos recebidos, que não são necessariamente candidatos válidos para atribuição. É possível ver um valor nesse campo e ainda assim ter a instalação atribuída a orgânico ou sem contribuidores.

> 📘 **Considerações para agências**
>
> O suporte da AppsFlyer não fornecerá explicações no nível de engajamento nem detalhamentos de `total_candidates` devido à complexidade da lógica de atribuição.

<div data-zendesk-anchors="assisted-installs=instala%C3%A7%C3%B5es-assistidas h_01HCBC922K9PCDXGDCCVEARADH=instala%C3%A7%C3%B5es-assistidas view-assisted-installs-metrics-in-the-overview-dashboard=visualizar-m%C3%A9tricas-de-instala%C3%A7%C3%B5es-assistidas-no-painel-vis%C3%A3o-geral h_01HCBC922KRHB043FK1CQRKXDA=visualizar-m%C3%A9tricas-de-instala%C3%A7%C3%B5es-assistidas-no-painel-vis%C3%A3o-geral why-are-assists-important=por-que-as-assist%C3%AAncias-s%C3%A3o-importantes h_01HCBC922KDAG8T27KK2JGRE7C=por-que-as-assist%C3%AAncias-s%C3%A3o-importantes assisted-installs-reporting=relat%C3%B3rios-de-instala%C3%A7%C3%B5es-auxiliadas h_01HCBC922KJV54QW6G85SN2JM7=relat%C3%B3rios-de-instala%C3%A7%C3%B5es-auxiliadas h_01KSFPXWNAX8FZ6H2ZKN1Z2TJQ=aten%C3%A7%C3%A3o h_01HCBC922K5HKF94JCY7C88R88=aten%C3%A7%C3%A3o-1 total-candidates-field=campo-de-total-de-candidatos h_01K453B1K1X7QVJHPQ505P745N=considera%C3%A7%C3%B5es-para-ag%C3%AAncias" />
