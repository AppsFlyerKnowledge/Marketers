---
title: ROI360 - visão geral para custos agregados
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-06T00:02:11Z'
  id: 207040526
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Saiba mais sobre as formas de os anunciantes agregarem e visualizarem dados de custos de marketing.

## Custos agregados

O ROI360 faz o seguinte:

* Fornece dados agregados de custo de publicidade e métricas de performance de LTV (valor vitalício) relacionadas a custo. Esses dados são disponibilizados nos dashboards e relatórios de performance. As métricas relacionadas a custo disponíveis incluem retorno sobre o investimento (ROI), retorno sobre gasto com anúncios (ROAS), cliques, impressões, ROI da campanha e custo efetivo médio por instalação (eCPI) ao longo do tempo.
* Abrange os custos de publicidade em todas as plataformas, incluindo apps mobile, navegadores web, TV conectada (CTV), PCs e consoles.
* É compatível com diferentes modelos de custo usados pelo canal de mídia, por exemplo, custo por instalação (CPI), custo por ação (CPA), custo por clique (CPC) e custo por mil (CPM).
* Registra o custo por API, Cost Import (upload de arquivos CSV) e <Anchor target="_blank" href="/marketers/pt/docs/view-aggregated-cost-data-for-attribution-links">custo no link de atribuição</Anchor>.
* Permite que as agências acessem dados de custo do ROI360 para anunciantes com uma assinatura do ROI360.

Os seguintes dados estão disponíveis para anunciantes sem uma assinatura do ROI360:

* <Anchor target="_blank" href="/marketers/pt/docs/view-aggregated-cost-data-for-attribution-links">Dados de custo no link de atribuição</Anchor>
* Dados de cliques e impressões de self-reporting network (SRN), que você configura na guia **custo** do parceiro SRN integrado

## Princípios de agregação de dados de custos

Vamos falar sobre os princípios básicos da agregação de dados de custo.

<div id="cost-aggregation-methods" />

<Accordion title="Métodos de agregação de custos">

A AppsFlyer obtém dados de custo dos canais de mídia usando um ou mais métodos. Se um canal de mídia reportar custo por mais de um método, o [mecanismo de priorização de custos](#cost-prioritization-mechanism) determina quais dados a AppsFlyer usa. Isso evita que os dados de custo sejam inflados.

Depois que a AppsFlyer processa os dados, eles são exibidos no fuso horário UTC (padrão) ou de acordo com as configurações de <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">fuso horário específico do aplicativo</Anchor>.

<table><thead><tr><th>Método de agregação de custos</th><th>Modelos de custo compatíveis</th><th>Granularidade dos dados</th><th>Atualização de dados</th><th>Observações</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>Todos</td><td>O nível depende da integração</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Intradiária</a></td><td>Os dados podem mudar após o evento de custo porque a AppsFlyer tenta recuperar dados de até 7 dias antes (dependendo do canal de mídia). Isso permite que a AppsFlyer leve em conta as alterações retroativas feitas pelo canal de mídia.</td></tr><tr><td><a href="./import-cost-data" target="_blank">Cost Import (upload de arquivo)</a></td><td>Todos</td><td>O nível depende do arquivo enviado</td><td>Até 4 horas após a importação</td><td>Você pode reverter o custo reportado e enviar dados corrigidos por até 90 dias.</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">Custo no link de atribuição</a></td><td>IPCCPI</td><td>Nível do usuário</td><td><p>Mínimo: em tempo real</p><p>Máximo: Até 4 horas após o link ser clicado</p></td><td>Não é possível fazer alterações</td></tr><tr><td colspan="5">\* As integrações de API entre canais de mídia e a AppsFlyer são feitas pela Cost API ou pela InCost API (nunca por ambas). A API usada e a granularidade dos dados fornecida dependem do canal de mídia.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Disponibilidade de dados de custo e relatórios">

A tabela no final desta seção indica onde os dados de custo estão disponíveis.

Para entender a tabela, as explicações abaixo se aplicam, a menos quando indicado de outra forma:

#### Custo na visualização de UA

A AppsFlyer classifica os dados de custo da campanha como aquisição de usuários (UA) com base em regras de correspondência que variam conforme o canal de mídia, como mostrado abaixo.

| Canais de mídia | Regra de correspondência |
| --- | --- |
| Google Ads, DV360, Facebook, TikTok, Apple Search Ads e Aura | A AppsFlyer classifica o custo como UA se registrar pelo menos uma instalação, um clique ou uma impressão em até ±10 dias da data da instalação (a data em que o canal de mídia reporta o custo). |
| Todos os outros canais de mídia | A AppsFlyer classifica o custo como UA se registrar pelo menos uma instalação, um clique ou uma impressão na própria data de processamento do canal de mídia. Nenhuma janela de ±10 dias se aplica. |

> 📘 **Importante!**
>
> Isso se aplica a ambas as linhas. A AppsFlyer baseia as correspondências no canal de mídia, no ID da campanha e na agência.

#### Custo na visualização unificada

A visualização unificada inclui dados de custo para todas as campanhas do aplicativo selecionado, independentemente de existirem instalações, cliques ou impressões dentro de ±10 dias a partir data em que o custo é informado (instalação).

#### Exemplo

Os exemplos a seguir mostram como a janela de ±10 dias afeta onde o custo aparece:

* Se um canal de mídia que usa a janela de ±10 dias reporta o custo da campanha X em 15 de março e a campanha X tem pelo menos um clique, instalação ou impressão entre 5 e 25 de março, o custo de 15 de março aparece na UA e na visualização unificada.
  * Se não houver atividade nesse intervalo de tempo, o custo de 15 de março aparece **apenas na visualização unificada**. Para canais de mídia que fazem a correspondência apenas pela data de processamento, a mesma regra se aplica ao próprio dia 15 de março, sem janela de ±10 dias.

#### Disponibilidade de dados de custos e relatórios

| Método de relatório | Tipo de visualização/dados | Aceita alterações no nome da campanha | Observações |
| --- | --- | --- | --- |
| Dashboard de Visão Geral | <ul><li>UA</li><li>Unificado</li></ul> | Sim | Os dados de retargeting não incluem dados de custo. O custo para retargeting é exibido na visualização unificada. |
| Dashboard de atividades | UA | Sim |  |
| Dashboard de cohort | <ul><li>UA</li><li>Unificado</li></ul> | Sim | <ul><li>Os dados de retargeting não incluem dados de custo.</li><li>Esses dados unificados estão disponíveis apenas para campanhas com pelo menos uma instalação, um clique ou uma impressão registrados dentro de ±10 dias da data de reporte do custo (data de instalação) para Google Ads, DV360, Facebook, TikTok, Apple Search Ads e Aura. Para todos os outros canais de mídia, esses dados estão disponíveis apenas para campanhas com atividade registrada na mesma data de processamento do custo.</li></ul> |
| API de Coorte | <ul><li>UA</li><li>Unificado</li></ul> | Sim | Esses dados unificados estão disponíveis apenas para campanhas com pelo menos uma instalação, um clique ou uma impressão registrados dentro de ±10 dias da data de reporte do custo (data de instalação) para Google Ads, DV360, Facebook, TikTok, Apple Search Ads e Aura. Para todos os outros canais de mídia, esses dados estão disponíveis apenas para campanhas com atividade registrada na mesma data de processamento do custo. |
| Dashboard da SKAN | SKAN | Não | Este dashboard exibe instalações da SKAdNetwork (SKAN), junto com dados de custo de **todas** as instalações (incluindo instalações não SKAN). |
| SKAN Aggregated Performance API | SKAN | Sem | Esta API exibe instalações da SKAN, junto com dados de custo de **todas** as instalações (incluindo instalações não SKAN). |
| Dashboard Pivot | UA | Não |  |
| Master API | UA | Sem |  |
| Dashboard personalizado | UA | Não |  |
| ETL de custos | Unificado | Sim | Todos os dados de custos disponíveis são exibidos. |
| Pull API agregada | UA | Não |  |
| API de push | Dados brutos de cliques (não agregados) | Irrelevante |  |
| Pull API de dados brutos | Dados brutos de cliques (não agregados) | Irrelevante |  |
| Relatório do Data Locker | Dados brutos de cliques (não agregados) | Irrelevante | Data Locker Cohort é incompatível com o custo. |

> 📘 **Importante!**
>
> Os pontos a seguir se aplicam à tabela:
>
> * A granularidade dos dados pode variar de acordo com o tipo de dashboard/relatório. A ferramenta <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> contém o conjunto completo de dados. Isso inclui detalhes da hierarquia da campanha (canal de mídia, nome da campanha, anúncio, adset e as dimensões disponíveis no canal de mídia, incluindo geolocalização, canal, ID do site e palavras-chave).
> * Os dados de custos relatados no link de atribuição estão disponíveis em relatórios de dados brutos.
> * Se um canal de mídia não for compatível com alterações no nome da campanha, os dois nomes da campanha serão exibidos: um com dados de atribuição e outro com dados de custo. Nenhum dos nomes da campanha inclui o quadro completo dos dados.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Mecanismo de priorização de custos">

Para um determinado canal de mídia, o custo pode ser fornecido por mais de um método de agregação. Para evitar a inflação de custos, um mecanismo de priorização do custo da campanha decide quais dados de custo aparecem na plataforma. A AppsFlyer dá prioridade com base no método de agregação. A prioridade, da maior para a menor, é: Custo no link de atribuição > Cost API > Cost Import.

![Diagrama que mostra a ordem de priorização do custo: custo no link de atribuição, depois Cost API e depois Cost Import](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

O mecanismo de priorização de custos afeta os relatórios de dados agregados e dashboards. Isso não afeta os dados de custo do link de atribuição nos relatórios de dados brutos, conforme observado acima.

**Considerações**:

* O mecanismo de prioridade atua no nível das campanhas. Isso significa que, se você receber dois inputs de custo para uma campanha por mecanismos diferentes, eles competirão entre si, e o de maior prioridade prevalecerá para toda a campanha.
  * Em qualquer dia em que haja dados de custo para um aplicativo e canal de mídia (ou agência) específicos via Cost API, a AppsFlyer ignora os dados de custo no link de atribuição.
* Se você alterar os métodos de agregação de custos, a alteração terá um impacto retroativo. Os dados históricos de custos agregados podem mudar.
* Uma alteração no método de custos agregados afeta o tráfego gerado por agências da mesma forma. Isso inclui agências transparentes e não transparentes.

> 📄 **Exemplo**
>
> **Cenário:** Uma fonte de mídia relata o custo no link de atribuição, mas você decide habilitar a Cost API na fonte de mídia.
>
> **Resultado:** A AppsFlyer agrega o custo do link de atribuição e da Cost API. Como a Cost API tem prioridade, a AppsFlyer ignora o custo no link de atribuição.

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="Divisão de custos">

Alguns canais de mídia reportam os dados de custo da campanha sem um App ID associado. Quando isso acontece, a AppsFlyer completa o(s) ID(s) do aplicativo usando dados de engajamento e atribuição.

A AppsFlyer combina os aplicativos com base naqueles associados aos cliques, impressões e conversões da campanha dentro de um **intervalo de ±10 dias** em torno da data de custo informada.

Se o processo resultar em múltiplos aplicativos correspondidos, a AppsFlyer redistribui o custo da campanha da seguinte forma:

#### Divisão proporcional (por conversões)

Se houver conversões (instalações, reatribuições e reengajamentos) na data de custo reportada, a AppsFlyer divide o custo proporcionalmente com base no número de conversões de cada aplicativo.

**Exemplo**: Se o custo total no D1 for **US$ 100** e a campanha gerar **60 instalações no iOS** e **40 instalações no Android**, então:

* iOS: **US$ 60**
* Android: **US$ 40**

> 📘 **Observações**
>
> A divisão proporcional (baseada em conversão) se aplica apenas quando a granularidade de conversão disponível na atribuição corresponde exatamente à granularidade que o canal de mídia informa para os dados de custo. Quando as duas correspondem apenas parcialmente, a AppsFlyer não consegue mapear o custo para as conversões de cada aplicativo, então aplica a divisão igual entre os aplicativos correspondentes.

#### Divisão igual (sem conversões)

Se não houver conversões na data de custo reportada, a AppsFlyer divide o custo igualmente entre os aplicativos correspondentes.

**Exemplo**: Se o custo total no D1 for **US$ 100** e a campanha tiver impressões, mas nenhuma conversão nessa data, então:

* iOS: **US$ 50**
* Android: **US$ 50**

#### Limitações

As seguintes limitações se aplicam a este recurso:

* A AppsFlyer dá suporte a este recurso para campanhas cross-platform e web-to-app (W2A) do Google, TikTok e DV360 (campanhas com um objetivo de campanha diferente de mobile/app).
* **Campanhas Google Performance Max (PMAX)**: a divisão proporcional (baseada em conversão) não se aplica. A API do Google não reporta a granularidade de ID do anúncio nem de geolocalização para campanhas PMAX, então a AppsFlyer divide o custo igualmente entre os aplicativos correspondentes, independentemente do número de conversões por aplicativo. No nível da campanha, quando todas as plataformas (iOS, Android etc.) estão selecionadas no dashboard, o custo total ainda corresponde ao custo informado pelo Google.

</Accordion>

## Informações adicionais

<div id="ad-networks-supporting-cost-api" />

<Accordion title="Lista de fontes de mídia que oferecem suporte para a Cost API">

A tabela a seguir (disponível para download) lista todos os canais de mídia compatíveis com a Cost API, com a granularidade de dados disponível para cada uma delas:

* Dimensões
* Funcionalidades compatíveis e suas características
* Métricas (conforme relatado pelas fontes de mídia)

Baixar arquivo: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv">CSV</Anchor>, <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLSX</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="Alteração dos nomes de campanha">

A AppsFlyer exibe campanhas usando o ID da campanha como chave.

Para evitar anomalias de exibição, certifique-se de que:

* Cada campanha tem um ID de campanha exclusivo.
* Não use o mesmo nome de campanha com diferentes IDs de campanha.

<Anchor target="_blank" href="/marketers/pt/docs/campaign-name-changes">Saiba mais sobre as alterações nos nomes das campanhas</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="Custos sem instalações">

**Por que vejo dados de custos sem instalações?** Isso acontece quando um canal de mídia fornece o custo em um nível mais alto da hierarquia (por exemplo, no nível da campanha), mas fornece informações de performance (cliques e instalações) em um nível mais baixo da hierarquia de publicidade (por exemplo, no nível do anúncio ou do adset).

A AppsFlyer completa os dados de custos para dimensões em falta a partir de uma hierarquia de nível superior. Isto garante uma visão completa dos dados de custos em qualquer nível e reduz discrepâncias internas.

> 📄 **Exemplo**
>
> Um anunciante realiza uma campanha. A hierarquia da publicidade é a seguinte:
>
> * **Fonte de mídia**: media\_eg
> * **Campanha**: campaign\_eg
> * **Adsets**: **adset\_1**, **adset\_2**
>
> A tabela a seguir mostra informações relacionadas ao canal de mídia.
>
> Hierarquia: Todas as fontes de mídia > media\_eg
>
>
>
> | Campanha | Custo | Instalações |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | US$ 200 | 1000 |
> | campaign\_zz | US$ 300 | 2000 |
>
>
>
> Ao detalhar campaign\_eg, você vê o nível do conjunto de anúncios.
>
> Hierarquia: Todas as fontes de mídia > media\_eg > campaign\_eg
>
>
>
> | Conjunto de anúncios | Custo | Instalações |
> | --- | --- | --- |
> | Nenhuma. | $100 |  |
> | adset\_1 | N/D | 30 |
> | adset\_2 | N/D | 70 |
>
>
>
> Nesse caso, a AppsFlyer fornece o custo de $100 da campaign\_eg no nível da campanha. Ao detalhar até o nível do adset, que neste caso é o nível mais baixo da hierarquia, a AppsFlyer não consegue detalhar o custo por adset.
>
> Para contornar isso, a AppsFlyer detalha o custo no nível da campanha e o exibe em uma linha separada. Nesse caso, o adset é exibido como None, e o campo de instalações permanece em branco.

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="Conversão de moeda de custos">

Se a moeda do custo da campanha fornecida pelo canal de mídia for diferente da moeda definida para o aplicativo na plataforma, a AppsFlyer converte o custo para a moeda definida para o aplicativo da seguinte forma:

* A AppsFlyer obtém as taxas de <Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>.
* A AppsFlyer atualiza as taxas de câmbio de hora em hora para dados de até sete dias atrás.
* A AppsFlyer realiza conversões de moeda usando a última taxa conhecida.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caraterísticas e limitações">

| Caraterística | A descrição |
| --- | --- |
| Agências | <ul><li>Quando agências confiáveis realizam campanhas de forma transparente, os anunciantes podem ver o custo exibido em dashboards e relatórios com visualização unificada. [Saiba mais sobre a disponibilidade dos dados de custo e relatórios](#cost-data-availability-and-reports)</li><li>Se um anunciante encerrar seu relacionamento com uma agência e a agência tiver o custo configurado para o aplicativo, a AppsFlyer continuará extraindo os dados de custo mesmo que o anunciante desative as permissões da agência no nível do aplicativo. Para evitar isso, o anunciante precisa pedir à agência que desative sua integração de custos na AppsFlyer antes de desativar as permissões da agência.</li><li>Para alguns canais de mídia, as agências precisam entrar em contato com o anunciante para ativar a integração, e a interface da AppsFlyer solicita que façam isso. Para esses canais de mídia, as agências e os anunciantes devem garantir que, quando o canal de mídia enviar dados, eles incluam o parâmetro `af_prt`, necessário para a atribuição de custos da agência.</li><li>Para X Ads, os dados de custo de campanhas que apenas têm instalações SKAN não estão disponíveis para agências. O anunciante deve configurar a integração de custos. Somente o anunciante pode visualizar os dados.</li></ul> |
| Atualização dos dados da API | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intradiária</Anchor> (exceto Moloco)</li><li>Os dados da Mintegral estão disponíveis via API no dia seguinte, aproximadamente 4 horas após o término do dia anterior. Por exemplo, se o evento ocorreu no Dia 1, os dados de custo estarão disponíveis no Dia 2, aproximadamente às 4:00.</li></ul> |
| Unificado | Os dados de gasto com anúncios exibem o nome de campanha mais recente reportado. Isso se aplica apenas aos dados agregados, não aos próprios dados brutos. |
| Fuso horário | Se um canal de mídia for compatível com apenas um fuso horário, e esse fuso horário for diferente do definido nas configurações do aplicativo, a AppsFlyer usará o fuso horário do canal de mídia. |
| Plataformas CTV, PC e console | Para aplicativos nessas plataformas, importe dados por meio do <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Ad Spend Ingestion</Anchor> usando o método de upload por e-mail.<br /><br />Você também pode extrair dados via API do Google, da Meta ou do TikTok nas seguintes plataformas:<ul><li>Steam</li><li>PC nativo</li><li>Smart Cast</li><li>Tizen</li><li>Quest</li></ul> |
| Multiplataforma | Os dados de custo não estão disponíveis para cliques e impressões entre plataformas, ou seja, a impressão/clique pode ocorrer em uma plataforma e a instalação do aplicativo em outra. |
| Aplicativos fora da loja | Os dados de custos da Mintegral não estão disponíveis para aplicativos fora da loja (outras plataformas que não o Google Play e a App Store). |
| Geografia | A análise por geo/país não está disponível para Mistplay bundled campaigns (campanhas segmentadas para vários países). Para essas campanhas, geo é apresentado como N/D. |
| Smadex | Os dashboards e os relatórios de Cost ETL podem exibir dados de custo e dados de atribuição separadamente. Isso acontece quando a Smadex inclui outros elementos (como o ID do inventário) no valor do site value ID. |
| Apple Search Ads | Para relatórios SKAN, os dados de custo ASA não estão disponíveis no dashboard da SKAN ou na Pull API, uma vez que a Apple não inclui dados a nível de campanha nos postbacks da SKAN. No entanto, os dados de custo estão disponíveis nos relatórios single-source-of-truth (SSOT) por meio da integração clássica da AppsFlyer. |
| Limite de caracteres da dimensão de dados de custo | Para os canais de mídia listados abaixo, as dimensões a seguir não podem exceder os comprimentos de caracteres especificados. Se você não cumprir esses limites, a AppsFlyer excluirá os valores de dimensão do relatório.<ul><li>`app_id`: até 100 caracteres</li><li>`publisher`: até 250 caracteres</li><li>`partner`: até 250 caracteres</li><li>`campaign`: até 250 caracteres</li><li>`campaign_id`: até 250 caracteres</li><li>`adset`: até 250 caracteres</li><li>`adset_id`: até 250 caracteres</li><li>`ad`: até 250 caracteres</li><li>`ad_id`: até 250 caracteres</li><li>`site_id`: até 250 caracteres</li><li>`site_name`: até 250 caracteres</li><li>`channel`: até 250 caracteres</li><li>`ad_account`: até 250 caracteres</li><li>`ad_account_name`: até 250 caracteres</li></ul>As limitações se aplicam apenas às seguintes fontes de mídia:<ul><li>`mintegral_int`</li><li>`moloco_int`</li><li>`applovin_int`</li><li>`liftoff_int`</li><li>`aura_int`</li><li>`tiktokglobal_int`</li><li>`pinterest_int`</li><li>`vungle_int`</li><li>`iossearchads_int`</li></ul> |
| Disponibilidade de dados da Cost API | A AppsFlyer exibe dados de custo da API apenas para clientes com um recurso ROI360 ativo. Se o ROI360 for desativado, os dados de custo de fontes de API ficarão indisponíveis, e o dashboard exibirá apenas dados de custo baseados em CPI. |
| Mintegral: granularidade ao nível do anúncio | Para obter relatórios de custo com granularidade no nível do anúncio da Mintegral, cada conta de anúncio exige as seguintes permissões de ad network: **Sub/Package × Creative dimension**. |

</Accordion>

<div data-zendesk-anchors="cost-aggregation=custos-agregados h_01HC7K2Y627P56F5JH9QT47GB2=custos-agregados principles-of-cost-data-aggregation=princ%C3%ADpios-de-agrega%C3%A7%C3%A3o-de-dados-de-custos h_01HC7K2Y62ZC932EDX00YP7DAW=princ%C3%ADpios-de-agrega%C3%A7%C3%A3o-de-dados-de-custos h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-in-the-ua-view=custo-na-visualiza%C3%A7%C3%A3o-de-ua h_01KGS7NM964HW175AW2CF59P5K=custo-na-visualiza%C3%A7%C3%A3o-de-ua h_01M3VZAVTP7F3TF607B49TGZQ4=importante cost-in-unified-view=custo-na-visualiza%C3%A7%C3%A3o-unificada h_01KGS7QG5GNKG1YVACWQKCQFZ4=custo-na-visualiza%C3%A7%C3%A3o-unificada example=exemplo h_01KGS7R5SJ3NSVJAHG3BM922VS=exemplo cost-data-availability-and-reports::865c5bcd=disponibilidade-de-dados-de-custos-e-relat%C3%B3rios h_01HC7K2Y62ZY6HWG5TJDEPHZKH=disponibilidade-de-dados-de-custos-e-relat%C3%B3rios h_01M3VZAVTPK4Q2X817ER2CW62D=importante-1 h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=exemplo-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split proportional-split-by-conversions=divis%C3%A3o-proporcional-por-convers%C3%B5es h_01KHR3PQTNMDX8AGM1C73N7SMK=divis%C3%A3o-proporcional-por-convers%C3%B5es h_01KZ8TMT06KNYFZ7VBX1GY07JB=observa%C3%A7%C3%B5es equal-split-no-conversions=divis%C3%A3o-igual-sem-convers%C3%B5es h_01KHR3PQTPG8GTHV64MFCM628H=divis%C3%A3o-igual-sem-convers%C3%B5es limitations=limita%C3%A7%C3%B5es h_01KHR3PQTPPJYKXRYKNHM4W95A=limita%C3%A7%C3%B5es list-of-ad-networks=informa%C3%A7%C3%B5es-adicionais h_01HC7K2Y63T9GK0WW95YM39B5C=informa%C3%A7%C3%B5es-adicionais h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=exemplo-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations" />
