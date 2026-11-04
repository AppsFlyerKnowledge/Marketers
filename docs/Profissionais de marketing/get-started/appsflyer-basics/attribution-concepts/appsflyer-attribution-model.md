---
title: Modelo de atribuição da AppsFlyer
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
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
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-08-19T00:09:00Z'
  id: 207447053
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/207447053
---
> **Resumo:** a AppsFlyer determina a fonte de mídia que motiva um usuário a instalar ou reengajar com um aplicativo, atibuindo a ação do usuário a essa fonte usando o modelo de atribuição da AppsFlyer.

[![](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)

<div id="what-is-attribution" />

## O que é atribuição?

**Atribuição** é o ato de determinar o que fez com que um usuário instalasse um aplicativo ou executasse atos pós-instalação, como reengajamento ou reatribuição. O resultado da atribuição pode ser:

* **Uma fonte de mídia não orgânica**: o usuário interagiu (geralmente por meio de impressão ou clique) com uma fonte de mídia.
* **Orgânica**: o usuário não interagiu com uma fonte de mídia. Atenção! Para facilitar a compreensão, muitas vezes nos referimos a um usuário como sendo *atribuído organicamente*. Sabemos que isso não é exatamente verdadeiro, pois os usuários que instalam organicamente não são atribuídos.

A atribuição é essencial para otimizar a aquisição de usuários, esforços de reengajamento e resultados.

<div id="what-is-an-app-install" />

## O que é uma instalação de aplicativo?

O **Modelo de atribuição** é um conjunto de regras que determina como o crédito de um evento é atribuído aos touchpoints nos caminhos de conversão. Cada um dos players do ecossistema de marketing, Google Play, App Store, Apple, plataformas de CTV, PC e console, ad networks como Meta Ads e X Ads e empresas de mensuração mobile têm seus próprios modelos de atribuição. Cada um contabiliza instalações e eventos de maneira diferente.

O importante não é a diferença entre os modelos, mas sim que as regras sejam claras e aplicadas de maneira imparcial. Isso permite que os anunciantes otimizem campanhas e comparem a qualidade da performance dos seus usuários.

É importante entender os modelos e regras de atribuição dos players com os quais você trabalha. O mais importante é entender o modelo e as nuances dos métodos compatíveis com a AppsFlyer.

Na AppsFlyer, um evento atribuível acontece quando um dos seguintes eventos ocorre:

* No contexto da aquisição de usuários:Uma **instalação** é registrada e atribuída depois que o usuários baixa e inicia o aplicativo. Isso significa que, na AppsFlyer, o **timestamp de data/hora de uma instalação é a primeira inicialização**. Por outro lado, as ad networks usam o tempo de engajamento e as app stores usam a hora do download.
* No contexto do [retargeting](/docs/appsflyer-attribution-model#retargeting-attribution):
  * **Re-engajamento**
  * **Re-atribuição**

<div id="attribution-methods" />

## Métodos de atribuição

A AppsFlyer usa vários métodos de atribuição, listados na tabela a seguir:

<table><tbody><tr><td>Método</td><td>Usa o device ID</td><td>Técnica</td><td>Atribuído por</td><td>Android (Google Play e lojas de terceiros)</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Universal Windows Platform (UWP)</td><td>Plataformas CTV, PC e console (3)</td></tr><tr><td> <a href="#install-referrer-android-only">Referrer</a> (1)</td><td>Sim</td><td>Determinístico</td><td>A AppsFlyer</td><td>Sim (2)</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td> <a href="#device-id-matching">Correspondência de Device ID</a> (1)</td><td>Não</td><td>Determinístico</td><td>A AppsFlyer</td><td>Sim</td><td>Sim</td><td>Não</td><td>Sim</td></tr><tr><td> <a href="#probabilistic-modeling">Modelagem probabilística</a> (1)</td><td>Não</td><td>Probabilístico</td><td>A AppsFlyer</td><td>Não</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td> <a href="#preload-campaigns">Pré-carregamento</a> (1)</td><td>Não</td><td>Determinístico</td><td>A AppsFlyer</td><td>Sim</td><td>Não</td><td>Sim</td><td>Não</td></tr><tr><td><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork (SKAN)</a></td><td>Não</td><td>Determinístico</td><td>Apple</td><td>Não</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td> <a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a> (1)</td><td>Não</td><td>Determinístico</td><td>Apple</td><td>Não</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td> <a href="./appsflyer-attribution-model#deep-link">Deep link</a> (1)</td><td>Não</td><td>Determinístico</td><td>A AppsFlyer</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td colspan="8">(1) Às vezes aparece como método de atribuição "Clássico" nos dashboards e relatórios da AppsFlyer(2) Compatível com algumas lojas de terceiros.<br/>(2) Compatível com algumas lojas de terceiros.<br/>(3) Veja a <a href="./ctv-pc-and-console-platform-attribution-concepts#plataformas-compatíveis" target="_blank">lista completa de plataformas de <span>CTV, PC e console</span></a> </td></tr></tbody></table>

<div id="attribution-method-priorities-attribution-waterfall" />

### Prioridades do método de atribuição (cascata de atribuição)

Em uma nova instalação, se houver mais de um contrato válido, a **AppsFlyer prioriza cliques ao invés de impressões e métodos determinísticos no lugar de métodos probabilísticos**. Os métodos de atribuição são utilizados de acordo com as prioridades mostradas no gráfico.

[<Image alt="watefall.png" src="https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png" width="1378px" />](https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png)

Veja abaixo as descrições detalhadas dos modelos de atribuição da AppsFlyer.

<div id="install-referrer-android-only" />

<Accordion title="Install referrer (apenas Android)">

* Os aplicativos Android baixados do Google Play e algumas outras lojas de aplicativos são geralmente atribuídos pelo método de install referrer. O referrer fornece a URL original, que recebeu um clique antes de redirecionar para a loja Android. Esse é o principal método para atribuição do Android. No momento, Google Play, a loja de aplicativos da Huawei, a Samsung Galaxy Store e a Xiaomi GetApps Store são compatíveis com a atribuição do referenciador da instalação. <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Atribuição alternativa da loja de aplicativos usando o referrer.</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Meta install referrer:</Anchor> A AppsFlyer tem suporte para a atribuição de Meta Ads para aplicativos do Android, recebendo metadados de campanhas de anúncios do armazenamento local de um dispositivo. Esses dados são usados para mensuração de atribuição (atribuição Meta no dispositivo).

</Accordion>

<div id="device-id-matching" />

<Accordion title="Correspondência de ID do dispositivo">

Um método clássico de atribuição em que a ad network, que possui acesso ao dispositivo do usuário, envia o device ID para a AppsFlyer através da URL de clique ou ao notificar a AppsFlyer de que uma impressão foi exibida. Isso permite que a AppsFlyer faça a correspondência do click device ID com o device ID coletado pelo SDK da AppsFlyer.

O device ID matching é o principal método de atribuição no iOS.

Os IDs disponíveis são:

* **Dispositivos iOS**: IDFA, IDFV
* **Dispositivos Android: com Google Play Services:** GAID
* **Dispositivos Android sem Google Play Services:** OAID, Android ID, IMEI, Fire ID

Os device IDs podem ser encriptados utilizando SHA1 ou MD5 em links de atribuição.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Device ID matching para redes de autorrelato (SRNs)">

Um método de atribuição clássico onde, após a primeira abertura do app, a AppsFlyer verifica nas configurações do aplicativo se o tráfego de alguma das <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">redes de auto-elato</Anchor> (SRNs) é esperado, como Meta Ads, Snapchat, e Google Ads.

A AppsFlyer consulta as SRNs relevantes usando a ID do dispositivo exclusiva da nova instalação. A consulta utiliza APIs dos Mobile Measurement Partners (MMP), conforme definido pelas SRNs. Com base na resposta, a AppsFlyer pode atribuir novos usuários a uma SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="Modelagem probabilística">

A AppsFlyer usa a modelagem probabilística como um método estatístico seguro para criar relatórios de performance das campanhas de marketing de aplicativos. Esse modelo gera relatórios agregados de performance a nível de campanha.

**Características de implementação**

* Usa estatísticas e não é baseado em IDs exclusivos.
* Ele estima quantas instalações ou engajamentos seguiram as campanhas de marketing próprias de um desenvolvedor — anúncios, links de sites, e-mails, QR codes, SMS ou outras Mídias próprias — para o aplicativo desse desenvolvedor.
* Ele usa apenas os sinais necessários para gerar um relatório agregado.
* O resultado é um relatório de performance da campanha, não uma identificação de qualquer dispositivo ou usuário individual.
* Métodos determinísticos de atribuição, ou seja, cliques com referrer ou ID matching recebem prioridade se ocorrerem dentro da janela de lookback.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Campanhas de preloa">

Nas campanhas de preload, aplicativos são instalados no dispositivo por um parceiro de preload, seja na fábrica ou na ativação do dispositivo. Os parceiros de preload são:

* Fabricante do equipamento original (OEM na sigla em inglês)
* Plataformas de descoberta de aplicativos
* Operadoras móveis

Existem 3 métodos para atribuir campanhas de preload. Todos os três métodos podem ser usados simultaneamente. Eles não interferem nos mecanismos um do outro.

Os 3 métodos e algumas das principais especificações estão descritos na tabela a seguir. Clique nos links para saber mais sobre cada método de preload.

<table><thead><tr><th>Método de atribuição preload</th><th>Caso de uso</th><th>Informações do activation-to-app launch do dispositivo\*</th><th>Janela de lookback\*\*</th><th>Tipo de correspondência nos dados brutos</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">AppsFlyer referrer</a>\*</td><td><ul><li>Pré-instalado na fábrica</li><li>Pré-instalado na ativação do dispositivo</li></ul></td><td>Sim</td><td><ul><li>Até 180 dias</li><li>O padrão é 90 dias</li></ul></td><td><ul><li>Preload: preload_rfr</li><li>Clique para fazer download: af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Instalação automática do Google Play</a>\*\*</td><td>Pré-instalado na ativação do dispositivo (para apps do Google Play)</td><td>Não</td><td><ul><li>Até 180 dias</li><li>O padrão é 90 dias</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pré-instalado na fábrica via propriedade do sistema ou manifest (Android)</a>\*\*</td><td><ul><li>Pré-instalado na fábrica</li><li>Pré-instalado na ativação do dispositivo</li></ul></td><td>Não</td><td>Sem limite</td><td>preload_conf</td></tr><tr><td colspan="5"><p>A solução AppsFlyer referrer preload fornece visibilidade e capacidade de métrica entre a ativação do primeiro dispositivo e a primeira inicialização do aplicativo. Isso permite que você veja quantos dispositivos foram ativados com o aplicativo pré-instalado nos dispositivos por um parceiro específico e, em seguida, veja quando o aplicativo é iniciado pela primeira vez.</p><p>Para os dois outros métodos, a atribuição é determinada somente após o usuário inicializar o aplicativo pela primeira vez - o número de dispositivos que tiveram o aplicativo instalado antes da primeira inicialização não está disponível.</p><p>\*\* Pode levar dias ou semanas, a partir do momento em que o usuário liga seu dispositivo até que ele abra o aplicativo pré-instalado pela primeira vez. Consequentemente, a AppsFlyer dá a maior prioridade às campanhas de preload na determinação da atribuição, com janelas de lookback mais longas.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Deep link">

Um método clássico de atribuição para reengajamentos apenas, quando os usuários não são redirecionados para uma loja de aplicativos para fazer o download do app. Portanto, as informações na URL podem ser conectadas diretamente ao clique (e subsequente abertura do aplicativo). Esse método de atribuição é chamado de deep link, pois é a URL do deep link que carrega as informações usadas para atribuir o reengajamento.

</Accordion>

<div id="attribution-methods-per-media-source-and-appsflyer-feature" />

### Métodos de atribuição por fonte de mídia e recurso da AppsFlyer

Consulte as seções a seguir para uma análise completa sobre quais métodos de atribuição específicos são compatíveis, dependendo do/da:

* Fonte de mídia: própria ou paga
* Recurso da AppsFlyer usado
* Dispositivo do usuário: Android ou iOS

<div id="owned-media" />

<Accordion title="Mídia própria">

<table><thead><tr><th rowspan="2">Fonte de mídia</th><th rowspan="2">Funcionalidade</th><th colspan="2">Método de atribuição</th></tr><tr><th>com o Android</th><th>/docs/ctv-pc-and-console-platform-attribution-concepts</th></tr></thead><tbody><tr><td>Mídias próprias: e-mail (incluindo ESPs), SMS, posts de mídias sociais, influenciadores/afiliados, impressão etc.</td><td><a href="./onelink-guide" target="_blank"><span>Os links diretos universais do OneLink</span></a></td><td><ul><li>Referenciador da instalação</li><li>Parâmetros de modelagem probabilística para ad networks</li></ul></td><td>Modelagem probabilística</td></tr><tr><td rowspan="2">Site mobile próprio/landing page com tráfego de entrada pago ou orgânico</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Smart Banners</a></td><td><ul><li>Referenciador da instalação</li><li>Modelagem probabilística</li></ul></td><td>Modelagem probabilística</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">OneLink Smart Script</a></td><td><ul><li>Referenciador da instalação</li><li>Modelagem probabilística</li></ul></td><td>Modelagem probabilística</td></tr><tr><td rowspan="2">Aplicativos mobile próprios</td><td><a href="./user-invite-attribution" target="_blank">Convites de usuários/indicação</a></td><td><ul><li>Referenciador da instalação</li><li>Modelagem probabilística</li></ul></td><td>Modelagem probabilística</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Promoção cruzada</a></td><td><ul><li>Referenciador da instalação</li><li>Correspondência de ID do dispositivo</li></ul></td><td>Atribuição de reinstalação no mesmo dispositivo.</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Mídia paga">

<table><thead><tr><th rowspan="2">Fonte de mídia</th><th colspan="3">Método de atribuição</th></tr><tr><th>com o Android</th><th>/docs/ctv-pc-and-console-platform-attribution-concepts</th><th><strong>Plataformas CTV, PC e console</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRNs</a></td><td>Correspondência de ID do dispositivo</td><td><ul><li>Device ID matching usando IDFV (iOS)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td>Correspondência de ID do dispositivo</td></tr><tr><td><ul><li>Redes de anúncios (não SRNs) por meio de <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">links de atribuição para parceiros</a> </li><li><span>Plataformas CTV, PC e console</span></li></ul></td><td><ul><li>Referenciador da instalação</li><li>Correspondência de ID do dispositivo</li><li>Modelagem probabilística</li></ul></td><td><ul><li>Privacidade Avançada Agregada (AAP)</li><li>Modelagem probabilística </li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pré-instalado no dispositivo</a></td><td>Pré-instalações</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

<div id="user-engagement-attribution-types" />

## Tipos de atribuição de engajamento do usuário

A atribuição é realizada com base em engajamentos click-through e view-through, usando os vários métodos de mensuração de campanha da AppsFlyer.

<div id="clickthrough-attribution" />

<Accordion title="Atribuição de click-through">

A maioria das instalações são resultado dos cliques do usuário em anúncios como banners, vídeos e intersticiais.

Após o clique no anúncio, a AppsFlyer abre uma janela de lookback por clique com uma duração padrão de 7 dias. Instalações que ocorrem dentro do prazo da janela de lookback não são orgânicas e são atribuídas à fonte de mídia. Instalações que ocorrem após a duração da janela de lookback são consideradas orgânicas. Muitas vezes mencionado como organicamente atribuído.

* Uma janela de lookback de cliques de sete dias é considerada o padrão da indústria. Defina a duração da janela de acordo com seu contrato com a fonte de mídia.
* Alinhe as janelas de lookback de SRN com a duração determinada pela SRN.

<table><thead><tr><th rowspan="2"> <strong>Tipo de atribuição</strong> </th><th rowspan="2"> <strong>Método de atribuição</strong> </th><th rowspan="2">Alcance</th><th rowspan="2">Padrão</th></tr></thead><tbody><tr><td rowspan="2"><p>Click-through</p><p>(Todos os parceiros integrados)</p></td><td>Referrer, ID Matching</td><td>1–30 dias</td><td>7 dias</td></tr><tr><td>Modelagem probabilística</td><td>0–24 horas</td><td><ul><li>Adaptável</li><li>Determinado pela AppsFlyer</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Saiba mais sobre janelas de lookback</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="Atribuição de view-through">

Usuários que visualizam anúncios, mas não clicam neles, podem ser atribuídos à ad network responsável pelo anúncio.

A janela de lookback para atribuição de view-through:

* Menor do que a de atribuição de click-through
* Configurável.

Isso é especialmente útil para video ad networks que costumam ter CTRs baixos em seus anúncios em vídeo, mas também para ad networks tradicionais que veiculam anúncios normais.

Nos casos em que um clique e uma impressão ocorrem, **o clique sempre prevalece**, uma vez que ele é um engajamento ativo.

<table><thead><tr><th><strong>Tipo de atribuição</strong></th><th><strong>Método de atribuição</strong></th><th><strong>Alcance</strong></th><th> <strong>Padrão</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>View-through (para (<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">parceiros integrados selecionados</a>)</p></td><td>Correspondência de ID</td><td>0-24 horas</td><td>1 dia</td></tr><tr><td>Modelagem probabilística</td><td>0-24 horas</td><td><ul><li>Adaptável</li><li>Determinado pela AppsFlyer</li></ul></td></tr></tbody></table>

**Para habilitar a atribuição de visualização engajada:**

* Configure a janela de lookback na <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#janela-de-lookback-de-atribuição-de-view-through">janela de configuração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">Saiba mais sobre a atribuição de view-through</Anchor>

</Accordion>

<div id="engaged-click-attribution" />

<Accordion title="Atribuição de cliques engajados">

Cliques engajados ocorrem quando os usuários clicam em um anúncio e permanecem no mesmo contexto — interagindo com o anúncio — sem serem redirecionados para a loja de aplicativos ou para abrir o app. Por exemplo, as interações podem incluir permanecer dentro de um anúncio jogável, interagir com elementos dentro do anúncio, ou continuar navegando pelo conteúdo dentro do container do anúncio. Para mais Informações, veja: <Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types">Novos tipos de engajamento.</Anchor>

* A janela de lookback de cliques engajados para ID matching é de 1 a 30 dias. O padrão é 2 dias.
* A janela de lookback para modelagem probabilística é de 0 a 24 horas. O padrão é adaptativo.
* Defina a duração da janela de acordo com seu contrato com a fonte de mídia.
* O clique engajado é compatível com parceiros integrados selecionados.
* Cliques engajados compartilham a mesma prioridade de atribuição que click-to-download e click-to-app.

| Tipo de atribuição | Método de atribuição | Alcance | Padrão |
| --- | --- | --- | --- |
| Clique engajado (para parceiros integrados selecionados) | Correspondência de ID | 1–7 dias  <br /> 1-23 horas | 2 dias |
|  | Modelagem probabilística | 0–24 horas | <ul><li>Adaptável</li><li>Determinado pela AppsFlyer</li></ul> |

<Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Saiba mais sobre janelas de lookback</Anchor>

</Accordion>

<div id="engaged-view-attribution" />

<Accordion title="Atribuição de visualização engajada">

As visualizações engajadas ocorrem quando os usuários veem um anúncio e realizam uma ação qualificada como assistir a um vídeo além de um certo limite ou interagir com uma unidade de anúncio, sem clicar. Essas ações indicam o nível de intenção e são usados para atribuir a instalação. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types">Novos tipos de engajamento.</Anchor>

* A janela de lookback de visualizações engajadas é de 0 a 24 horas para atribuição determinística e probabilística.
* A janela de lookback padrão para atribuição determinística é de 2 dias.
* A visualização engajada é compatível com parceiros integrados selecionados.
* Visualizações engajadas compartilham a mesma prioridade de atribuição que cliques engajados e click-to-app.

| Tipo de atribuição | Método de atribuição | Alcance | Padrão |
| --- | --- | --- | --- |
| Visualização engajada (para parceiros integrados selecionados) | Correspondência de ID | 1–7 dias  <br /> 1-23 horas | 2 dias |
|  | Modelagem probabilística | 0–24 horas | <ul><li>Adaptável</li><li>Determinado pela AppsFlyer</li></ul> |

**Para ativar a atribuição de view-through:**

* Configure a janela de lookback na <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#janela-de-lookback-de-atribuição-de-view-through">janela de configuração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">Saiba mais sobre a atribuição de view-through</Anchor>

</Accordion>

<div id="advanced-attribution-topics" />

## Tópicos de atribuição avançada

<div id="in-app-events" />

<Accordion title="Eventos in-app">

A AppsFlyer utiliza o ID do dispositivo ou um ID exclusivo da AppsFlyer para atribuições (instalação, reinstalação ou reatribuição) com o objetivo de **atribuir eventos in-app à fonte de mídia**. Os anunciantes podem usar essas informações para acompanhar as jornadas do usuário nos dados brutos de seus aplicativos. Nos dados agregados diários, o ID do dispositivo/ID da AppsFlyer é usado para calcular o número de usuários únicos, como por exemplo o número de usuários exclusivos que realizam um evento in-app.

Para mais informações sobre atribuição de eventos, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">aqui</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Instalações assistidas">

O AppsFlyer atribui integralmente apenas uma fonte de mídia por instalação, normalmente de acordo com o último clique no anúncio ou a última impressão do anúncio (se não houve nenhum clique).

Instalações assistidas (também conhecidas como atribuição multitouch) são instalações em que a fonte/campanha de mídia não foi o último ponto de contato, mas alcançou o usuário antes da instalação e o toque ocorreu na janela de lookback de atribuição.

As redes auxiliares são mostradas como colaboradoras para a instalação na AppsFlyer.

Para mais detalhes, clique <Anchor target="_blank" href="/marketers/pt/docs/measure-assisted-installs">aqui</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Reinstalações">

Uma reinstalação ocorre quando um usuário instala o aplicativo, o desinstala e então o reinstala. A atribuição de reinstalação é regulada pela <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor> da seguinte forma:

* Se a reinstalação ocorrer após a expiração da janela de reatribuição: uma nova instalação é registrada.
* Se a reinstalação ocorrer durante a janela de reatribuição, ocorre um dos seguintes eventos:
  * Se o usuário engajou com uma campanha de retargeting antes da reinstalação: uma <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">reinstalação de retargeting</Anchor> (ou seja, reatribuição) será registrada.
  * Se o usuário não engajou com uma campanha ou se engajou com uma campanha de UA: nenhuma instalação é registrada. Dependendo do status da <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#overview">**atribuição de eventos após a instalação**</Anchor>, os eventos de reinstalação desses usuários são atribuídos à instalação orgânica ou à instalação original.

Para testes de dispositivos e múltiplas instalações, <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registre</Anchor> o dispositivo na AppsFlyer. Se você não registrar o dispositivo, apenas a primeira instalação será registrada.

A AppsFlyer oferece uma melhor precisão na atribuição de reinstalações iOS sem o advertising ID. Você pode ativar essa funcionalidade na <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">página de configurações do aplicativo</Anchor>.

<div id="reinstalling-ios-apps-that-are-backed-up-in-icloud" />

#### Reinstalando aplicativos iOS que têm backup no iCloud

Quando é feito o backup de um aplicativo usando o iCloud e posteriormente restaurado (no mesmo ou em outro dispositivo), a AppsFlyer não conta como uma nova instalação ou reinstalação. Um usuário que restaura um aplicativo do iCloud mantém seu ID da AppsFlyer e dados de atribuição.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribuição de retargeting">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Um usuário que reinstala um aplicativo dentro da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor> (90 dias por padrão) é considerado uma reatribuição. Se essa instalação ocorrer depois do engajamento com uma campanha de retargeting, ela será registrada como reinstalação de retargeting, ou seja, reatribuição, e será relatada em <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">retargeting</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="Atualizações do app">

* Quando os usuários existentes atualizam o aplicativo para uma versão seguinte, isso não é tratado como um evento de atribuição contável, se o usuário foi atribuído anteriormente pela AppsFlyer. Atenção! Se você migrar para a AppsFlyer de um MMP diferente, os usuários existentes no primeiro aplicativo aberto, após a migração, serão atribuídos como orgânicos.
* Métricas relacionadas ao número de usuários por versão do aplicativo estão disponíveis no <Anchor target="_blank" href="/marketers/pt/docs/sdk-information-version-consent-dashboard">dashboard de informações do SDK.</Anchor>

</Accordion>

<div data-zendesk-anchors="what-is-attribution=o-que-%C3%A9-atribui%C3%A7%C3%A3o 01H8GG9XPSS8KA9CHPD6ECNR2J=o-que-%C3%A9-atribui%C3%A7%C3%A3o what-is-an-app-install=o-que-%C3%A9-uma-instala%C3%A7%C3%A3o-de-aplicativo 01EDRHGMTXK94Y97DPKFAMCJ5B=o-que-%C3%A9-uma-instala%C3%A7%C3%A3o-de-aplicativo attribution-methods=m%C3%A9todos-de-atribui%C3%A7%C3%A3o 01EDRHGMTXCRNVXS9JGHQ1JAQT=m%C3%A9todos-de-atribui%C3%A7%C3%A3o attribution-waterfall=prioridades-do-m%C3%A9todo-de-atribui%C3%A7%C3%A3o-cascata-de-atribui%C3%A7%C3%A3o h_01JBC8582ABTE00W29PM5Y5X0B=prioridades-do-m%C3%A9todo-de-atribui%C3%A7%C3%A3o-cascata-de-atribui%C3%A7%C3%A3o 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns h_01K0XWKWQ7TJ2DBT1JZPY5Q4F6=deep-link attribution-methods-per-media-source-and-appsflyer-feature=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-por-fonte-de-m%C3%ADdia-e-recurso-da-appsflyer 01H8GG9XPTXDR41QANF4XVSZMM=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-por-fonte-de-m%C3%ADdia-e-recurso-da-appsflyer 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=tipos-de-atribui%C3%A7%C3%A3o-de-engajamento-do-usu%C3%A1rio 01EDRHGMTX7851H14R20F9KNAN=tipos-de-atribui%C3%A7%C3%A3o-de-engajamento-do-usu%C3%A1rio 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution h_01K0XYZWBVPSXT0T6XGPQT20X8=engaged-view-attribution advanced-attribution-topics=t%C3%B3picos-de-atribui%C3%A7%C3%A3o-avan%C3%A7ada 01EDRHGMTYYXBSCDPKXCDK1641=t%C3%B3picos-de-atribui%C3%A7%C3%A3o-avan%C3%A7ada 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events h_01K0XWKWQ7J20YKEND9A43DRNR=assisted-installs 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=reinstalando-aplicativos-ios-que-t%C3%AAm-backup-no-icloud 01EDRHGMTYDSNJKQNPNYFXJPAZ=reinstalando-aplicativos-ios-que-t%C3%AAm-backup-no-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
