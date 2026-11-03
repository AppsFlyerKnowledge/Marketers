---
title: Relatórios de dados brutos do Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-08-19T00:07:52Z'
  id: 360015179337
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** Os relatórios de dados brutos descrevem as instalações e os eventos na aplicação bloqueados pelo motor Protect360, assim como as regras de validação adicionadas manualmente.

## Sobre os relatórios de dados brutos do Protect360

Relatórios de dados brutos:

* Apresentam dados sobre:
  * Cliques, instalações, e eventos na aplicação identificados como fraudulentos pelo motor Protect360.
  * Instalações e eventos na aplicação identificados através de regras de validação.
* Incluir a razão do bloqueio para cada clique, instalação ou evento na aplicação.
* São usados pelos anunciantes para reconciliar contas de redes de publicidade, otimizar e ajustar painéis de atribuição para fraudes pós-atribuição.
* Podem ter <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">alguns campos restritos ou indisponíveis</Anchor> se <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada (AAP) da AppsFlyer</Anchor>.
* Os tipos de relatórios e a sua disponibilidade para download, API, e Data Locker (bucket S3) são descritos nas secções seguintes.
* A retenção de relatórios históricos de dados brutos é de até 90 dias, dependendo da ferramenta de relatório e da origem dos dados brutos.

> 📘 **Nota**
>
> Devido a restrições nos dados brutos relacionadas com a privacidade, os relatórios podem apresentar campos com valores vazios. Um exemplo disso são os campos de contribuidor.

<div id="report-types" />

<Accordion title="Tipos de relatório">

#### Tipos de relatório de dados brutos do Protect360

| Relatório | Descrição |
| --- | --- |
| <span id="installs"></span>Instalações | Os relatórios incluem:<ul><li>**Instalações falsas**: Instalações identificadas como fraudulentas pelo motor Protect360. Estas não aparecem em nenhum painel ou dados brutos da AppsFlyer, exceto no painel e dados brutos do Protect360.</li><li>**Instalações sequestradas**: Instalações de utilizadores reais onde a atribuição é roubada, mas o Protect360 [corrige a atribuição](/docs/protect360-raw-data-reports#correção-de-atribuição-para-instalações-sequestradas).</li><li>**Regras de validação**: Que bloqueiam a instalação ou a atribuição (o Protect360 [corrige a atribuição](/docs/protect360-raw-data-reports#correção-de-atribuição-para-instalações-sequestradas)).</li></ul> |
| <span id="postattribution-installs"></span>Instalações pós-atribuição | Os relatórios incluem instalações atribuídas a uma fonte de media, mas posteriormente identificadas como fraudulentas. [O Protect360](/docs/protect360-raw-data-reports#correção-de-atribuição-para-instalações-sequestradas) [corrige a atribuição](/docs/protect360-raw-data-reports#correção-de-atribuição-para-instalações-sequestradas). |
| <span id="blocked-inapp-events"></span>Eventos na aplicação bloqueados | Os relatórios incluem eventos na aplicação de:<ul><li>**Instalações falsas**: Os IAEs estão bloqueados.</li><li>**Eventos na aplicação**: Identificado como fraudulento, independentemente das instalações originais.</li><li>**Regras de validação**:<ul><li>IAEs resultantes de uma regra que bloqueou a instalação ou a atribuição.</li><li>IAEs resultantes de uma regra que bloqueou o evento dentro da aplicação.</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>Eventos in-app pós-atribuição | Os relatórios incluem eventos in-app:<ul><li>Identificados pós-atribuição.</li><li>Instalações atribuídas a uma fonte de mídia, mas posteriormente identificadas como fraudulentas.</li></ul> |
| <span id="clicks"></span>Cliques | Os relatórios incluem cliques bloqueados com os respetivos motivos. |
| <span id="blocked-install-postbacks"></span>Postbacks de instalação bloqueados | Os relatórios incluem cópias dos postbacks de rejeição enviados para fontes de mídia que registaram instalações bloqueadas. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Relatórios pós-atribuição">

* Os relatórios de fraude de dados brutos pós-atribuição têm a mesma estrutura dos relatórios de fraude bloqueada.
* O relatório pós-atribuição do mês atual (pela data de instalação) continua a ser atualizado até ao sétimo dia do mês seguinte (data de deteção).
* Os relatórios de dados brutos pós-atribuição estão disponíveis apenas para anunciantes. As agências necessitam de <Anchor target="_blank" href="/partners/pt/docs/protect360-for-integrated-partners">permissões</Anchor> ativadas para aceder.
* Os relatórios incluem eventos de fraude pós-atribuição identificados pelo Protect360 e abrangem todas as fontes de mídia num único relatório. **Nota**: Se não forem identificados eventos de fraude pós-atribuição para o intervalo de datas selecionado, o relatório será devolvido vazio,
* Os relatórios de fraude de dados brutos pós-atribuição estão disponíveis da seguinte forma:
  * Interface do utilizador do painel: limitada a uma fonte de mídia por um mês de calendário.
  * API Pull: inclui todas as fontes de mídia. (Limitação: Disponível apenas para proprietários de aplicações.)

#### **Utilização de relatórios pós-atribuição**

* Selecione qualquer combinação de intervalos de datas de instalação/IAE e deteção conforme necessário.
* Tenha em conta que o Protect360 realiza a deteção pós-atribuição durante o mês da instalação e até ao sétimo dia do mês seguinte. Isto significa, por exemplo, que para instalações em novembro, o Protect360 verifica fraudes até 7 de dezembro.
* A prática recomendada para utilizar esta API Pull é a seguinte:
  * Suponha que obtém o relatório diariamente.
  * Defina o intervalo de datas de instalação para os 60 dias anteriores ao dia atual.
  * Defina o intervalo de deteção para a data anterior ao dia atual.  
    Isso significa que receberá a lista das fraudes pós-atribuição detetadas ontem. Se não tiver extraído o relatório durante alguns dias, ajuste o intervalo de datas de deteção e extraia o relatório.

> 📄 **Exemplo**
>
> **Exemplo A**: Durante dezembro, 15 instalações são atribuídas à example\_media. A 3 de janeiro, o Protect360 identifica a example\_media como uma fraude. Como resultado, as 15 instalações atribuídas à example\_media são listadas como fraudulentas no relatório de fraude pós-atribuição, para ação adicional por parte do proprietário da aplicação.
>
> **Exemplo B**: Durante o mês de dezembro, foram atribuídas 15 instalações à example\_media. A 9 de janeiro, o Protect360 identifica a example\_media como uma fraude. Neste caso, não será tomada qualquer ação pelo Protect360 porque a fraude foi identificada após o fecho do mês, a 7 de janeiro.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Disponibilidade de dados brutos por tipo de ferramenta">

#### Disponibilidade de dados brutos do Protect360 por tipo de ferramenta

<table><thead><tr><th>Relatório</th><th>Relevância dos dados</th><th>Extrair API</th><th>Página de Exportação de Dados</th><th>Armazenamento de dados</th></tr></thead><tbody><tr><td>Instalações</td><td>Em tempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Eventos na aplicação bloqueados</td><td>Em tempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Cliques</td><td>Em tempo real</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Postbacks de instalação bloqueados</td><td>Em tempo real</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Instalações pós-atribuição</td><td>Diariamente às 10h00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Eventos in-app pós-atribuição</td><td>Diariamente às 10h00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="5"><p>\* Limitações para relatórios via Data Locker:</p><ul><li>A transparência da agência não é suportada. Isso significa que o tráfego gerado pela agência não contém o nome da fonte de mídia que envia a instalação.</li><li>O relatório possui um conjunto único de campos em comparação com outros relatórios do Data Locker. Esta lista não pode ser alterada.</li><li>Os dados de retargeting não estão disponíveis no relatório de instalações; apenas no relatório de instalações pós-atribuição. </li></ul></td></tr></tbody></table>

</Accordion>

## Obtenção de relatórios de dados brutos

Os relatórios de dados brutos estão disponíveis por download, Pull API e Data Locker (bucket S3). Pode também <Anchor target="_blank" href="/partners/pt/docs/protect360-for-integrated-partners">dar acesso aos parceiros aos relatórios</Anchor>.

<div id="download" />

<Accordion title="Baixar">

**Para fazer download:**

1. No painel do Protect360, aceda a **Relatórios de dados brutos** > **Bloqueados** ou **Pós-atribuição.**
   * Para relatórios pós-atribuição, escolha a fonte de mídia e o mês.
2. Selecione o relatório **Protect360 e Regras de Validação** para descarregar.

**OU**

1. No painel da AppsFlyer, vá a **Exportar Dados**.
2. Selecione o relatório **Protect360 e Regras de Validação** para descarregar.

**Nota**: Os relatórios descarregados da página Exportar Dados incluem todas as fontes de mídia.

</Accordion>

<div id="pull-api" />

<Accordion title="Extrair API">

**Para descarregar os relatórios de dados brutos disponíveis via Pull API:**

**Antes de começar:**

É necessário um token Pull API. Obtenha o token de um <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">utilizador administrador</Anchor>.

1. Vá a **Relatório > Acesso à API.** A <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">página da API Pull</Anchor> abre-se.
2. Na secção de relatórios de fraude do Protect360, escolha a chamada Pull API necessária.
3. Preencha os parâmetros conforme necessário. A tabela seguinte apresenta os parâmetros.
4. Extraia o relatório.

#### Parâmetros do relatório de dados brutos da API Pull

| Parâmetro | Descrição | Formato | Obrigatório |
| --- | --- | --- | --- |
| ID\_da\_aplicação | ID da aplicação conforme aparece na AppsFlyer | Sequência de caracteres | Sim |
| api\_token | Recupere a chave do painel. Vá a **Relatório** > **Acesso à API.** Somente um utilizador administrador pode recuperar o token API. | Sequência de caracteres | Sim |
| de | Início do intervalo de datas:<ul><li>Para instalações, esta é a data de instalação.</li><li>Para eventos na app, esta é a data do evento.</li></ul> | AAAA-MM-DD | Sim |
| para | Fim do intervalo de datas:<ul><li>Para instalações, esta é a data de instalação.</li><li>Para eventos na app, esta é a data do evento.</li></ul> | AAAA-MM-DD | Sim |
| nome\_do\_evento | [Opcional para fraude de eventos na app pós-atribuição]<br /><br />Filtrar eventos por eventos na aplicação. Restringa o relatório a eventos específicos.  Pode incluir um ou mais eventos.<br /><br />Exemplo de uso: `&event_name=af_purchase,af_login` | Sequência de caracteres | Não |
| campos\_adicionais=valor\_motivo\_rejeitado | [Opcional para fraude de eventos na app pós-atribuição]<br /><br />**<Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** exibe o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#protect360">contribuinte válido (fonte de mídia) para instalações ou eventos na app que foram sequestrados. Preenchido com [**contributor[1-3]**](/docs/raw-data-field-dictionary#attribution::2a6fd501) ou **orgânico**.</Anchor> | Sequência de caracteres | Não |
| detetar de | [Opcional para instalações pós-atribuição]<br /><br />Início do intervalo de datas para deteção de fraude. (A predefinição é a partir de.) (O padrão é começar de.) (Usado em fraude de instalação pós-atribuição.) (O padrão é começar de.) (Usado em fraude de instalação pós-atribuição.) | AAAA-MM-DD | Não |
| detetar até | [Opcional para instalações pós-atribuição]<br /><br />Fim do intervalo de datas para deteção de fraude. (O padrão é finalizar em.) | AAAA-MM-DD | Não |

</Accordion>

<div id="data-locker" />

<Accordion title="Armazenamento de dados">

O Data Locker grava dados brutos num bucket AWS S3.

<Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#protect360">Consulte a lista de relatórios disponíveis do Protect360</Anchor>. 

<Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#aws-cli">Veja as instruções de configuração do Data Locker</Anchor>.

</Accordion>

## Estrutura do relatório Protect360

Os relatórios do Protect360 têm a mesma estrutura geral que os campos dos relatórios de aquisição de utilizadores.

Para além dos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">campos normais do relatório de dados brutos</Anchor>, os relatórios do Protect360 também incluem campos para retargeting e motivos de bloqueio, conforme apresentado a seguir:

### Razões para bloqueio

<div id="click-level-blocked-reasons" />

<Accordion title="Razões para bloqueio ao nível de clique">

Ao nível de clique, os cliques são bloqueados e o processo de atribuição ignora-os.

| Motivo do bloqueio | Descrição |
| --- | --- |
| ip\_lista negra | Baseado numa lista criada dinamicamente (<Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide#ip-denylists">detalhes</Anchor>) |
| limitação\_de\_cliques | Foram detetadas taxas extremamente elevadas de fraude de cliques nessa rede de publicidade. <Anchor target="_blank" href="/partners/pt/docs/protect360-for-integrated-partners#limitação-de-impressões">Saiba mais</Anchor> |
| assinatura de clique | A assinatura do clique não é validada. <Anchor target="_blank" href="/partners/pt/docs/click-signing-for-ad-networks">Saiba mais</Anchor> |
| validação\_de\_entrada | Nome da fonte de media inválido |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Razões para bloqueio ao nível de instalação">

Ao nível de instalação, conseguimos identificar informações suficientes no momento da instalação para determinar:

* Uma instalação falsa, significando que o utilizador que instala a aplicação não é uma pessoa real. Nesse caso, a atribuição é completamente bloqueada.
* Roubo de atribuição, onde o utilizador é real, mas o envolvimento é falsificado. Nesse caso, o envolvimento fraudulento é bloqueado e a atribuição é reatribuída à primeira rede de publicidade válida que contribuiu.

As tabelas seguintes listam as possíveis razões de bloqueio ao nível de instalação:

#### Nível de instalação: Razões secundárias para bloqueio de instalações falsas

| Motivo do bloqueio | Submotivo do bloqueio | Descrição |
| --- | --- | --- |
| Bots | parâmetros\_de\_dispositivo\_falsos | Comportamento não humano detetado em parâmetros relacionados com o dispositivo durante o processo de instalação da aplicação |
| Bots | parâmetros\_instalação\_falsa | Comportamento não humano detetado nos parâmetros relacionados com a instalação durante o processo de instalação da aplicação |
| Bots | rede\_bayesiana | Identificação de padrões fraudulentos através de redes bayesianas |
| Bots | anomalias na atividade dos usuários | Identifica comportamento anormal ou suspeito do usuário no aplicativo usando modelos de detecção de anomalias comportamentais. Esses modelos:<ul><li>Analisam a atividade do usuário em nível individual</li><li>Destacam desvios em relação aos padrões esperados</li><li>Detectam agrupamentos de comportamento que divergem dos perfis legítimos de usuários</li><li>Essa detecção ajuda a sinalizar a atividade de bots que imitam usuários reais, mas executam ações in-app de formas atípicas.</li></ul> |
| Bots | validação de loja | Valida que cada instalação se origina de uma fonte autêntica e esperada. Este mecanismo:<ul><li>Verifica a integridade do canal de aquisição</li><li>Detecta sinais de instalação falsificados ou manipulados</li><li>Rejeita instalações que não se alinham a canais de distribuição legítimos</li><li>Ao garantir a legitimidade no nível da instalação, esse método ajuda a bloquear bots que tentam falsificar instalações orgânicas ou pagas.</li></ul> |
| Bots | Anomalias de interação no aplicativo | Sinaliza eventos não in-app em interações no aplicativo pós-instalação. Ajuda a identificar comportamentos suspeitos na transição da instalação para a abertura do aplicativo. |
| validação\_robôs | parâmetros\_de\_dispositivo\_inválidos | Incompatibilidade de expectativas em campos específicos do dispositivo - definido pelo cliente |
| validação\_robôs | regras\_de\_validação | Regras onde o resultado são instalações bloqueadas com base em regras de validação definidas manualmente |
| Bots | ai\_layer | Modelos de IA são usados para analisar grandes volumes de dados, aprimorando as capacidades de detecção para identificar atividades fraudulentas em dispositivos e instalações. |

#### Nível de instalação: Motivos secundários para bloqueios de sequestro de atribuição

| Motivo do bloqueio | Submotivo do bloqueio | Descrição |
| --- | --- | --- |
| anomalias\_ctit | ctit\_curto | Instalação bloqueada devido a CTIT curto: Definido pelo Protect360 |
| sequestro\_de\_instalação | sequestro\_de\_referenciador | Tentativa de sequestro bloqueada com base nos parâmetros da API do GooglePlay e do SDK da AppsFlyer |
| sequestro\_de\_instalação | integração\_temporariamente\_bloqueada | Instalação bloqueada porque o parceiro (pid) apresenta taxas de fraude extremamente altas e anomalias significativas em todo o tráfego |
| sequestro\_de\_validação | ctit\_curto | Instalação bloqueada devido a CTIT curto: Definido pelo cliente |
| sequestro\_de\_validação | site\_id\_vazio | Instalação bloqueada devido a ID do site não preenchido. A implementação da regra ocorre por fases |
| sequestro\_de\_validação | regras\_de\_validação | Regras em que o resultado é atribuição bloqueada com base em uma regra de validação definida manualmente |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Razões de bloqueio ao nível do cluster">

Quando se deteta um padrão de fraude, a fonte da fraude é colocada na lista de exclusões. As instalações provenientes desta lista de exclusão são bloqueadas devido a:

* Uma instalação falsa, significando que o utilizador que instala a aplicação não é uma pessoa real. Nesse caso, a atribuição é completamente bloqueada.
* Roubo de atribuição, onde o utilizador é real, mas o envolvimento é falsificado. Neste caso, o engajamento fraudulento é bloqueado e a atribuição é reatribuída à primeira rede de anúncios válida.

As tabelas seguintes apresentam possíveis razões para bloqueios ao nível do cluster:

#### Nível de cluster: Motivos de bloqueio de instalação falsa

| Motivo do bloqueio | Submotivo do bloqueio | Descrição |
| --- | --- | --- |
| Bots | anomalias\_temporais | Anomalias relacionadas com tempos de clique no fluxo de atribuição e outros registros de data e hora obtidos do dispositivo |
| bots, lista\_negra\_de\_sites | emuladores\_de\_dispositivos | Instalações geradas em larga escala por scripts automáticos em ambientes virtuais |
| lista\_negra\_de\_sites | fazendas\_de\_dispositivos | Altas taxas de dispositivos desconhecidos (novos) |
| anomalias\_comportamentais | anomalias\_comportamentais | Comportamento suspeito dentro da aplicação em comparação com o padrão comum de comportamento do utilizador da aplicação |

#### Nível de cluster: Razões para bloqueio de sequestro de atribuição

| Motivo do bloqueio | Submotivo do bloqueio | Descrição |
| --- | --- | --- |
| anomalias\_ctit, sequestro\_de\_instalação | anomalias\_ctit | Padrão de CTIT anormal em relação aos padrões da aplicação |
| inundação\_de\_cliques | inundação\_de\_cliques | Volume de cliques anormalmente alto em distribuições de CTIT longas |
| sequestro\_de\_instalação | aglomerados\_de\_cliques | Cliques gerados por malware a nível do dispositivo |
| Hijacking de reengajamento | Clusters de cliques de reengajamento | Detecta tentativas fraudulentas de sequestrar a atribuição de reengajamento. Essas manipulações visam roubar o crédito de Retargeting Networks legítimas ou até mesmo de usuários que não viram nenhum anúncio de retargeting.<br />Depois de detectada, a atribuição é corrigida e reatribuída a:<ul><li>A network de retargeting válida</li><li>O provedor original de aquisição de usuários (UA)</li><li>Orgânico, se o usuário instalou o Aplicativo sem ter sido exposto a nenhum anúncio de retargeting válido</li></ul> |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="Razões para bloqueios ao nível da aplicação">

Os eventos na aplicação podem ser bloqueados pelos seguintes motivos:

* A instalação inicial foi identificada como falsa.
* Devido a uma regra de validação estabelecida.
* Porque o nosso algoritmo deteta fraude.

A tabela a seguir lista os possíveis motivos de bloqueio a nível da aplicação.

#### Motivos de bloqueio a nível da aplicação

| Motivo do bloqueio | Submotivo do bloqueio | Descrição |
| --- | --- | --- |
| Herda da instalação | Herda da instalação | Instalação inicial identificada como falsa com base no motivo de [instalação](/docs/protect360-raw-data-reports#install-level-blocked-reasons) ou [lista de exclusão](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) |
| inapps\_bots | parâmetros\_de\_dispositivo\_falsos | Algoritmo da AppsFlyer deteta fraude |
| validação\_na\_loja\_de\_apps | - | A <Anchor target="_blank" href="/marketers/pt/docs/legacy-receipt-validation-for-in-app-purchases">validação do recibo</Anchor> para compras na aplicação falha. |
| validação\_inapps | regras\_de\_validação | Baseado na regra de validação definida manualmente |

</Accordion>

### Redirecionamento

Os dados brutos do Protect360 incluem instalações e sessões fraudulentas de campanhas de redirecionamento (conhecidas como reatribuições e reengajamentos, respetivamente). Os dados são apresentados utilizando os campos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#event">nome do evento</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::e9c68f6c">tipo de conversão de retargeting</Anchor> . Estão marcados como um dos seguintes:

* Instalação (aplica-se ao nome do evento, mas não ao tipo de conversão de retargeting)
* Reatribuição
* Reengajamento
* Reinstalação

Os dados brutos de retargeting do Protect360 estão disponíveis para bloqueios em tempo real e fraudes identificadas após a atribuição da seguinte forma:

<table><thead><tr><th>Relatório </th><th>Exportar dados</th><th>Extrair API</th><th>Armazenamento de dados</th></tr></thead><tbody><tr><td>Instalações</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Instalações pós-atribuição</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* Dados de reengajamento não disponíveis</span><br/> </td></tr></tbody></table>

### Correção de atribuição para instalações sequestradas

Para instalações sequestradas, a AppsFlyer bloqueia a atribuição à rede fraudulenta e, em alternativa, atribui à última fonte legítima de contribuição.

Para instalações sequestradas, use o campo <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> para identificar o colaborador válido (fonte de media), ou seja, o contribuidor que deveria ter recebido a atribuição originalmente.

* O campo **rejected\_reason\_value** é preenchido com <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor> ou **orgânico. Verifique os campos** colaborador[1-3] fonte de media/parceiro **para visualizar os detalhes do contribuidor e reconciliar.**
* Se os campos de contribuidor não aparecerem no seu relatório, podem ser adicionados na página de **Exportar dados**.

**Nota**: Quando as instalações sequestradas são bloqueadas em tempo real, as atribuições corretas são exibidas nos dashboards e relatórios da AppsFlyer (não apenas no Protect360). Quando as instalações usurpadas são identificadas após a atribuição, as atribuições corretas são mostradas apenas nos dados brutos do Protect360.

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Comentário |
| --- | --- |
| Relatórios nas aplicações | Os relatórios nas aplicações não incluem o campo de contribuidor. Os campos de contribuidor estão disponíveis apenas no relatório de instalações. |
| Valores em branco | Devido a restrições nos dados brutos relacionadas com a privacidade, os relatórios podem apresentar campos com valores vazios. Um exemplo disso são os campos de contribuidor. |

</Accordion>

<div data-zendesk-anchors="about-protect360-raw-data-reports=sobre-os-relat%C3%B3rios-de-dados-brutos-do-protect360 h_01HE7S55TCE60A34T6RCNTCQK8=sobre-os-relat%C3%B3rios-de-dados-brutos-do-protect360 h_01J91EP40Q69KXXF2SR66AM2FQ=nota h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=tipos-de-relat%C3%B3rio-de-dados-brutos-do-protect360 h_01HE7S55TCKQYTXPV6J54SHM0D=tipos-de-relat%C3%B3rio-de-dados-brutos-do-protect360 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=utiliza%C3%A7%C3%A3o-de-relat%C3%B3rios-p%C3%B3s-atribui%C3%A7%C3%A3o h_01HE7S55TC7KCF75KFXHCE3K2K=utiliza%C3%A7%C3%A3o-de-relat%C3%B3rios-p%C3%B3s-atribui%C3%A7%C3%A3o h_01HE7S55TCR8BKZ0PQ5B14X3X4=exemplo h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=disponibilidade-de-dados-brutos-do-protect360-por-tipo-de-ferramenta h_01HE7S55TCH4CES29C5J3QXQK4=disponibilidade-de-dados-brutos-do-protect360-por-tipo-de-ferramenta getting-raw-data-reports=obten%C3%A7%C3%A3o-de-relat%C3%B3rios-de-dados-brutos h_01HE7S55TC3MRT6E9QV0J0X6FC=obten%C3%A7%C3%A3o-de-relat%C3%B3rios-de-dados-brutos h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=par%C3%A2metros-do-relat%C3%B3rio-de-dados-brutos-da-api-pull h_01HE7S55TCRRD95D0QPCXBRF8T=par%C3%A2metros-do-relat%C3%B3rio-de-dados-brutos-da-api-pull h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=estrutura-do-relat%C3%B3rio-protect360 h_01HE7S55TCS91ZC9V3K0VDSVXK=estrutura-do-relat%C3%B3rio-protect360 blocked-reasons=raz%C3%B5es-para-bloqueio h_01HE7S55TC1ZEDD5ABD21FCPY2=raz%C3%B5es-para-bloqueio h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=n%C3%ADvel-de-instala%C3%A7%C3%A3o-raz%C3%B5es-secund%C3%A1rias-para-bloqueio-de-instala%C3%A7%C3%B5es-falsas h_01HE7S55TDHTE5P47N1CCREGZX=n%C3%ADvel-de-instala%C3%A7%C3%A3o-raz%C3%B5es-secund%C3%A1rias-para-bloqueio-de-instala%C3%A7%C3%B5es-falsas install-level-attribution-hijacking-block-reasons=n%C3%ADvel-de-instala%C3%A7%C3%A3o-motivos-secund%C3%A1rios-para-bloqueios-de-sequestro-de-atribui%C3%A7%C3%A3o h_01HE7S55TDFA6WGAHE80ECV8CA=n%C3%ADvel-de-instala%C3%A7%C3%A3o-motivos-secund%C3%A1rios-para-bloqueios-de-sequestro-de-atribui%C3%A7%C3%A3o h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=n%C3%ADvel-de-cluster-motivos-de-bloqueio-de-instala%C3%A7%C3%A3o-falsa h_01HE7S55TDBES0BY0FF3WKSSVG=n%C3%ADvel-de-cluster-motivos-de-bloqueio-de-instala%C3%A7%C3%A3o-falsa cluster-level-attribution-hijacking-block-reasons=n%C3%ADvel-de-cluster-raz%C3%B5es-para-bloqueio-de-sequestro-de-atribui%C3%A7%C3%A3o h_01HE7S55TD3M45TH4PY2W805W7=n%C3%ADvel-de-cluster-raz%C3%B5es-para-bloqueio-de-sequestro-de-atribui%C3%A7%C3%A3o h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=motivos-de-bloqueio-a-n%C3%ADvel-da-aplica%C3%A7%C3%A3o h_01HE7S55TD661EHCV50S9BW5MS=motivos-de-bloqueio-a-n%C3%ADvel-da-aplica%C3%A7%C3%A3o retargeting=redirecionamento h_01HE7S55TDSYDC8BWZ8D8DF9JE=redirecionamento hijacked-installs-attribution-correction=corre%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-para-instala%C3%A7%C3%B5es-sequestradas h_01HE7S55TD8SDCQJCCYQC0MNES=corre%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-para-instala%C3%A7%C3%B5es-sequestradas h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />
