---
title: Configure e use os relatórios de Cost ETL do ROI360
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
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
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2026-08-19T00:01:15Z'
  id: 360008849238
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** O Cost ETL, parte do ROI360 da AppsFlyer, fornece dados de custo de campanha com a melhor granularidade disponível por fonte de mídia. Os dados, atualizados até 4 vezes por dia, são enviados para seu serviço de nuvem, prontos para serem carregados nos seus sistemas de BI.

[![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)

O Cost ETL, parte do ROI360 da AppsFlyer, fornece dados de custo de campanha com a melhor granularidade disponível por fonte de mídia. Até 4 vezes por dia, os dados são atualizados e enviados ao seu serviço de nuvem no Data Locker, prontos para serem carregados nos seus sistemas de BI.

Você pode enviar relatórios facilmente para vários destinos em nuvem de uma só vez. Isso agiliza o trabalho de transição de um serviço de nuvem para outro, pois os dados ficam acessíveis em vários serviços simultaneamente.

Os relatórios de Cost ETL incluem dados de custo vinculados à atribuição da AppsFlyer, incluindo métricas de atribuição como instalações, reatribuições e reengajamentos.

## Quatro tipos de relatórios de Cost ETL

A AppsFlyer oferece quatro tipos de relatórios de Cost ETL, oferecendo suporte a diferentes necessidades de análise.

* **Summary report:** (padrão) dados de custo de alto nível agregados por fonte de mídia. Recomendado para a análise das métricas de custo e performance em um nível amplo.
* **Geo report:** (opcional) dados de custo divididos por país (códigos de 2 letras), como US, CA e BR. Recomendado para a análise de performance e de custos a nível local.
* **Channel report:** (opcional) dados de custo segmentados por canal (por exemplo, YouTube, Shopping). Recomendado para a análise da performance a nível de canal e análise de custos.  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?single=true&output=csv">Ver arquivo de amostra</Anchor>.
* **All Cost Report**: uma visão abrangente dos dados de custos dentro e fora do mobile, provenientes diretamente das ad networks, sem dados de atribuição. Atualmente disponível para Google Ads, Meta Ads e TikTok.  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSdjA_4tdWBxxbI_ZM7mcZzCKhrWxQ-0m1DPIig-gMTpnDyLBDE_RGJ5zskNFpbsg/pub?gid=559626950&single=true&output=csv">Ver arquivo de amostra.</Anchor>

  > 📘 **Nota**
  >
  > Para começar a receber dados do Google Ads e Meta Ads no relatório de todos os custos, entre em contato com seu representante da AppsFlyer.


### Tabela de visão geral dos tipos de relatório de Cost ETL

<table><thead><tr><th> </th><th>Summary</th><th>Geografia</th><th>Canal</th><th><strong>Relatório de todos os custos</strong></th></tr></thead><tbody><tr><td><strong>Para acessar o relatório</strong></td><td>Ative o Cost ETL. O Summary report é selecionado por padrão.</td><td>Ative o Cost ETL e selecione o Geo report.</td><td>Ative o Cost ETL e selecione o Channel report.</td><td>Ative o Cost ETL e selecione o <strong>Geo</strong> report. (o All Cost report não possui um seletor específico na página do Cost ETL)</td></tr><tr><td><strong>Onde encontrar o relatório</strong></td><td>Depende do serviço de conector de nuvem escolhido. Pode ser uma pasta (Summary) ou uma tabela dedicada.</td><td>Depende do serviço de conector de nuvem escolhido. Pode ser uma pasta (Geo) ou uma tabela dedicada.</td><td>Depende do serviço de conector de nuvem escolhido. Pode ser uma pasta (Channel) ou uma tabela dedicada.</td><td>Depende do serviço de conector de nuvem escolhido. Pode ser uma pasta (All Cost) ou uma tabela dedicada.</td></tr><tr><td><strong>Tipo de cobertura</strong></td><td><p>Custo mobile: sem limitações.<br/>CTV e custo da web - limitado a:<br/> </p><ol><li>Campanhas com pelo menos uma conversão</li><li>A fonte de custo é a InCost API, Cost Import, ou CPI</li></ol></td><td>Igual à do Summary report.</td><td>Igual à do Summary report.</td><td>Custo mobile, web, CTV, PC e console do Google Ads, Meta Ads e TikTok.</td></tr><tr><td><strong>Cobertura da fonte de mídia</strong></td><td>Sem limitações</td><td>Sem limitações</td><td>Sem limitações</td><td><ul><li> <strong>TikTok:</strong> os dados são adicionados automaticamente.</li><li> <strong>Google e Meta:</strong> entre em contato com seu CSM para ativar.</li></ul></td></tr><tr><td><strong>Granularidade do esquema</strong></td><td>Com base na configuração do cliente nas configurações de Cost ETL.</td><td><p>Com base na configuração do cliente nas configurações de Cost ETL.</p><p><br/>Para o Meta, a dimensão do canal não tem valores.</p></td><td><p>Com base na configuração do cliente nas configurações de Cost ETL.</p><p><br/>Para o Meta, a dimensão geo não tem valor.</p></td><td><p>Com base na configuração do cliente nas configurações de Cost ETL.</p><p>Para o Meta, a dimensão channel não é compatível.<br/><strong>Plataforma:</strong> uma nova dimensão da ad network que indica onde a campanha é executada (por exemplo, mobile, desktop, tablet).</p></td></tr><tr><td><strong>Dados de atribuição</strong></td><td>Com suporte.</td><td>Com suporte.</td><td>Com suporte.</td><td><p>Não compatível</p><p><br/>Os valores das métricas de atribuição são exibidos como zero (0), se forem configurados pelo cliente para fazer parte do esquema de Cost ETL.</p></td></tr><tr><td><strong>ID da aplicação</strong></td><td>Se a ad network não oferecer suporte à granularidade do App ID, o App ID é extraído dos dados de atribuição.</td><td>Igual à do Summary report.</td><td>Igual à do Summary report.</td><td><p>Extraído da ad network.</p><p><br/>Se o App ID não for relatado, o valor é considerado "unknown".</p></td></tr><tr><td><strong>Fonte de custo</strong></td><td>Integração da API (Cost + InCost), Cost Import, CPI</td><td>Igual à do Summary report.</td><td>Igual à do Summary report.</td><td>Somente integração da API.</td></tr><tr><td><strong>CNC</strong></td><td>Com suporte.</td><td>Com suporte.</td><td>Com suporte.</td><td>Não compatível</td></tr><tr><td><strong>Dados da agência</strong></td><td>Com suporte.</td><td>Com suporte.</td><td>Com suporte.</td><td><ul><li> <strong>Facebook e Meta:</strong> Indisponível.</li><li> <strong>TikTok:</strong> Disponível apenas para campanhas com App ID na AppsFlyer.</li></ul></td></tr><tr><td><strong>Taxa da agência</strong></td><td>Com suporte.</td><td>Com suporte.</td><td>Com suporte.</td><td>Indisponível. O valor é sempre 0.</td></tr><tr><td><strong>Pouca atualização</strong></td><td colspan="4">Os dados são coletados da ad network seis vezes por dia.<br/>Os relatórios podem ser entregues até 4 vezes por dia (com base na configuração do cliente).</td></tr></tbody></table>

## Detalhes do relatório

<div id="data-freshness" />

<Accordion title="Atualização dos dados">

Os dados de custo da campanha são registrados:

* No seu bucket para visualização, transferência e carregamento de dados de custos nos seus sistemas.
* Para todos os aplicativos que você escolher incluir no Cost ETL, por dia e por versão.
* Até 4 vezes por dia (atualização dos dados: <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">intradiário)</Anchor>.
* Para o dia atual e nos 6 dias anteriores (referidos como 7 dias neste artigo), bem como os dias 14, 29 e 88. Leve isso em consideração no seu processo de carregamento de dados.
  * Exemplo: Para a data de 14 de outubro de 2024, o arquivo contém dados de 14 de outubro (o dia atual), 13 de outubro (1 dia atrás), 12 de outubro (2 dias atrás), 11 de outubro (3 dias atrás), 10 de outubro (4 dias atrás), 9 de outubro (5 dias atrás), 8 de outubro (6 dias atrás), 30 de setembro (14 dias atrás), 15 de setembro (29 dias atrás) e 18 de julho (88 dias atrás).
  * Os dados retroativos permitem atualizações e correções ao relatar os dados de custos.
* Para custos que correspondem a atribuição, clique ou impressão.  
  **Atenção:**
  * Os dados relativos aos últimos 7 dias são extraídos novamente do canal de mídia. Os dados relativos aos dias 14, 29 e 88 são processados novamente.
  * Apenas os dados de custos são atualizados retroativamente; não os dados de atribuição.

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Diretório e estrutura de nomes de arquivos">

Os dados registrados no serviço de nuvem ou bucket têm o diretório e a estrutura de arquivos descritos a seguir:

* Quando o Cost ETL termina de registrar em um diretório, uma flag é definida através da criação de um arquivo de *sucesso*. Esse é sempre o timestamp de data/hora mais recente no diretório.
* O número de pastas/arquivos é o seguinte:
  * Resumo: Até 4 pastas de versão por dia.
    * Cada pasta de versão contém arquivos parquet com 7 dias de dados.
  * Relatório de geo ou canal: Cada relatório contém até 4 pastas de versão por dia.
    * Cada pasta de versão contém arquivos parquet que contêm dados com numeração a partir de 1.
  * [Beta fechado] Todos os custos: Com base na dimensão geo, contém até 4 arquivos por dia.

#### Estrutura do diretório de conexão do Data Locker

`///t=/dt=/v=<1/2/3/4>/`

| **Variável** | **Conteúdo** |
| --- | --- |
| client-bucket | Nome do bucket conforme configurado no serviço de nuvem |
| DL-generated-partition | Partição gerada, exclusiva por cliente |
| connection-name | Nome da conexão conforme definido durante a configuração do Data Locker |
| t | O nome do relatório específico. Seja:<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li><li>[Beta fechado] cost\_etl\_all\_cost\_geo</li></ul> |
| dt | <ul><li>A data do relatório, ou seja, a data em que o relatório foi enviado.</li><li>AAAA-MM-DD</li></ul> |
| S | <ul><li>A versão cronológica do relatório por dia (até 4 relatórios diários)</li><li>Números inteiros entre 1-4</li></ul> |
| Parquet file number | <ul><li>Numerados a partir de 00000</li><li>Exemplo: `part-`</li></ul> |

#### Estrutura do diretório de conexão do Cost ETL

`<nome do bucket do anunciante>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/<dimensão>/<nome do arquivo/<número do arquivo parquet>`

| **Variável** | **Conteúdo** |
| --- | --- |
| advertiser\_bucket\_name | Tal como definido na configuração do Cost ETL: af-xpend-cost-etl-&lt;af-account-id>-[sufixo do nome do seu bucket] |
| cost\_etl | Sempre cost\_etl |
| version | Versão do Cost ETL |
| data | Data do custo<br /><br />Formato: aaaa-mm-dd |
| batch | Número 1-4, |
| dimension | Dimensão dos dados:<ul><li>geo</li><li>canal</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Parquet file number | <ul><li>Numerados a partir de 00000</li><li>Exemplo: `part-`</li></ul> |

**Exemplo:** Para a primeira extração de dados de 23 de junho de 2020, a estrutura do nome do diretório e do arquivo é a seguinte: `/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

</Accordion>

<div id="file-fields" />

<Accordion title="Campos de arquivo">

#### Campos/Dimensões

| **Campo** | **Observações** | **Sempre preenchido** | **Formato** | **Incluído no arquivo de resumo** |
| --- | --- | --- | --- | --- |
| Anúncio | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| ad\_account | <ul><li>Conta de anúncios da qual foram extraídos os dados de custos</li><li>Relevante para networks nas quais a conexão é feita através de oAuth (login com as suas credenciais), por exemplo, no Google Ads ou Meta Ads</li></ul> | Não | Sequência de caracteres | - |
| id\_anúncio | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| conjunto\_de\_anúncios | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| id\_conjunto\_de\_anúncios | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| af\_bid\_strategy | Estratégia de bidding mapeada e normalizada pela AppsFlyer. Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Sequência de caracteres | - |
| af\_cost\_model | Modelo de custo mapeado e normalizado pela AppsFlyer. Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Sequência de caracteres | - |
| agency | Agência responsável pela colocação do anúncio | Não | Sequência de caracteres | - |
| conjunto\_de\_anúncios | ID do aplicativo na plataforma da AppsFlyer | Sim | Sequência de caracteres | ✓ |
| bid\_amount | Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Número inteiro | - |
| bid\_strategy | Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Sequência de caracteres | - |
| Twitter | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| id\_da\_campanha | Componente da hierarquia publicitária | Não | Sequência de caracteres | - |
| campaign\_objective | Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Sequência de caracteres | - |
| canal | Dimensão na hierarquia da publicidade | Não | Sequência de caracteres | - |
| cost\_model | Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Sequência de caracteres | - |
| símbolos monetários | Moeda do gasto do anunciante conforme configurada para o app na AppsFlyer | Sim | String de 3 caracteres em conformidade com a norma ISO-4217 | ✓ |
| data | Data em que o custo foi reportado pelo canal de mídia | Sim | String aaaa-mm-dd | ✓ |
| geo | Dimensão na hierarquia da publicidade | Não | Cadeia de 2 caracteres em conformidade com a norma ISO 3166 | ✓ |
| keyword\_id | ID dos termos da palavra-chave no ASA | Sim | Sequência de caracteres | - |
| keyword\_term | Palavra(s) usada(s) pelo usuário na pesquisa online | Sim | Sequência de caracteres | - |
| fonte\_de\_mídia | Canal de mídia responsável pela exibição do anúncio | Sim | Sequência de caracteres | ✓ |
| original\_bid\_amount | Componente das propriedades da campanha. <Anchor target="_blank" href="/marketers/pt/docs/campaign-properties-in-cost-etl-reports">Saiba mais</Anchor> | Não | Número inteiro | - |
| original\_currency | Moeda do custo tal como reportada pela ad network antes de quaisquer conversões | Sim | String de 3 caracteres em conformidade com a norma ISO-4217 | - |
| os | Sistema operacional do dispositivo. Valores possíveis:<ul><li>Android</li><li>Windows Phone</li><li>ios</li></ul> | Sim | Sequência de caracteres | - |
| platforma | A plataforma usada para executar a campanha (mobile, tablet, desktop e CTV) | Somente All Cost report | Sequência de caracteres | - |
| id\_do\_site | ID do editor | Não | Sequência de caracteres | - |
| Fuso horário | <ul><li>Fuso horário dos dados tal como estão armazenados na AppsFlyer</li><li>Às vezes, as ad networks comunicam dados em um fuso horário diferente daquele definido na AppsFlyer. Esse ponto de dados ajuda a explicar as discrepâncias de custo entre a AppsFlyer e as ad networks</li></ul> | Sim | Sequência de caracteres | - |

#### Métricas

| **Campo** | **Observações** | **Sempre preenchido** | **Formato** | **Incluído no arquivo de resumo** |
| --- | --- | --- | --- | --- |
| ccvr | <ul><li>Custo por conversão</li><li>Fórmula: Custo / (instalações + reatribuições + reengajamentos)</li></ul> |  | Número inteiro | - |
| clicks | <ul><li>Contado pela AppsFlyer.</li><li>Inclui UA e retargeting.</li><li><Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types#engaged_click">Engaged clicks</Anchor> são subtraídos do número total de cliques.</li></ul> |  | Número inteiro | ✓ |
| clicks\_discrepancy | <ul><li>Diferença entre as impressões contadas pela ad network e pela AppsFlyer</li><li>Desconsidere essa métrica se:<ul><li>não há uma correspondência entre o custo e a atribuição.</li><li>A ad network não é compatível com <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">cliques relatados.</Anchor></li></ul></li></ul> |  | Número inteiro | - |
| cost | Valor das despesas (incluindo taxas de agências, se relevante) |  | Valor | ✓ |
| cost\_without\_fees | Custo menos a taxa de agência. Contado pela AppsFlyer | Sim | Número inteiro | - |
| cpi | <ul><li>Contado pela AppsFlyer</li><li>Fórmula: Custo / instalações</li></ul> |  | Número inteiro | - |
| CTR | <ul><li>Taxa de clique. Contado pela AppsFlyer</li><li>Fórmula: Cliques / impressões</li></ul> | Não | Número inteiro | - |
| CVR | <ul><li>Taxa de conversão. Contado pela AppsFlyer</li><li>Fórmula: Instalações / cliques</li></ul> |  | Número inteiro | - |
| cvvr | <ul><li>Taxa de visualização de vídeo concluída Contadas pela AppsFlyer</li><li>Fórmula: Número de conclusões do vídeo / impressões do vídeo</li></ul> |  | Número inteiro | - |
| ecpc | <ul><li>Contado pela AppsFlyer</li><li>Fórmula: Custo / cliques</li></ul> |  | Número inteiro | - |
| ecpm | <ul><li>Contado pela AppsFlyer</li><li>Fórmula: (Custo / impressões) x 1.000</li></ul> |  | Número inteiro | - |
| taxas | Taxas que uma agência cobra para além do custo normal do anúncio. Contadas pela AppsFlyer | Sim | Número inteiro | - |
| impressions | <ul><li>Contado pela AppsFlyer.</li><li>Inclui UA e retargeting.</li><li><Anchor target="_blank" href="/marketers/pt/docs/about-enriched-engagement-types#engaged_view">Engaged views</Anchor> são subtraídas do número total de impressões.</li></ul> | Sim.<br /><br />Se não estiver disponível nenhum valor para uma determinada métrica, ela é preenchida com 0. | Número inteiro | ✓ |
| impressions\_discrepancy | <ul><li>Diferença entre as impressões contadas pela ad network e pela AppsFlyer</li><li>Desconsidere essa métrica se:<ul><li>não há uma correspondência entre o custo e a atribuição.</li><li>A ad network não é compatível com <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">impressões relatadas.</Anchor></li></ul></li></ul> |  | Número inteiro | - |
| installs | Contado pela AppsFlyer |  | Número inteiro | ✓ |
| installs\_discrepancy | <ul><li>Diferença entre as impressões contadas pela ad network e pela AppsFlyer</li><li>Desconsidere essa métrica se:<ul><li>não há uma correspondência entre o custo e a atribuição.</li><li>A ad network não é compatível com <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">conversões relatadas.</Anchor></li></ul></li></ul> |  | Número inteiro | - |
| original\_cost | Custo conforme reportado pela ad network, na moeda informada pela ad network antes de qualquer conversão de moeda (taxas de agência calculadas pela AppsFlyer são adicionadas quando relevante) |  | Valor | - |
| original\_cost\_without\_fees | Custo original, conforme reportado pela ad network, sem taxas de agência | Sim | Número inteiro | - |
| re\_attributions | Contado pela AppsFlyer |  | Número inteiro | ✓ |
| re\_engagements | Contado pela AppsFlyer |  | Número inteiro | ✓ |
| reported\_clicks | Contado pelo canal de mídia |  | Número inteiro | ✓ |
| reported\_conversions | Contado pelo canal de mídia |  | Número inteiro |  |
| reported\_cvr | <ul><li>Taxa de conversão reportada</li><li>Fórmula: Conversões reportadas / cliques reportados</li></ul> |  | Número inteiro | - |
| reported\_impressions | Contado pelo canal de mídia |  | Número inteiro | ✓ |
| video\_25p\_views | 25% do vídeo reproduzido Reportado pela ad network 75% do vídeo reproduzido Reportado pela ad network |  | Número inteiro | - |
| video\_50p\_views | Vídeo reproduzido 50%% 75% do vídeo reproduzido Reportado pela ad network |  | Número inteiro | - |
| video\_75p\_views | Vídeo reproduzido 75%% 75% do vídeo reproduzido Reportado pela ad network Padronização entre ad networks |  | Número inteiro | - |
| video\_completions | Reportado pela ad network |  | Número inteiro | - |

</Accordion>

## Procedimentos

<div id="set-up-cost-etl" />

<Accordion title="Configurar Cost ETL">

Esse procedimento de configuração deve ser feito por um usuário administrador.

**Antes de começar**:

A configuração do Cost ETL requer:

* Um serviço de nuvem configurado com permissão para que a AppsFlyer registre dados nele. Isso significa que você precisa configurar 1 ou mais dos seguintes serviços de nuvem:
  * Bucket da <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
  * Bucket do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
  * [Beta] <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [Beta] Bucket do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
  * Data warehouse do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
  * Warehouse do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>
* Você precisa ser administrador da conta da AppsFlyer e do acesso à interface do usuário da AppsFlyer para concluir a configuração do Cost ETL.

[**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **Para configurar o Cost ETL:**

1. Na AppsFlyer, no menu lateral, selecione **Exportar** > **Cost ETL**.
2. Selecione ou configure uma **conexão de dados**:
   * Se você já tiver conexões de dados configuradas, no menu suspenso de **Conexão**, selecione as conexões desejadas para o Cost ETL.  
     [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * Se você ainda não tiver uma conexão de dados, clique em **+ Nova conexão no Data Locker** e crie uma conexão lá:  
     [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
     1. Dê um nome à sua conexão.  
        [<Image alt="" src="https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png" width="2100px" />](https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png)
     2. **Selecione um destino para os dados no seu cloud service**. Faça uma das seguintes opções:
        * Selecione **S3**.  
          [<Image alt="" src="https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png" width="945px" />](https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png)
          1. Insira o nome do seu bucket S3 da AWS. O prefixo `af-`af-af- é obrigatório e deve ser inserido manualmente.
          2. Clique em **Testar conexão**.
          3. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          4. Selecione se deseja **tornar essa conexão compatível com a Adobe Experience Platform**.
          5. Clique em **Salvar**.
          6. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
        * Selecione **GCS**.  
          [<Image alt="" src="https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png" width="944px" />](https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png)
          1. Insira o **nome do bucket do GCS**.
          2. Clique em **Testar conexão**.
          3. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          4. Selecione se deseja **tornar essa conexão compatível com a Adobe Experience Platform**.
          5. Clique em **Salvar**.
          6. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
        * [Beta] Selecione **Azure**.  
          [<Image alt="" src="https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png" width="943px" />](https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png)
          1. Insira seu **Nome de conexão**, **Nome da conta de armazenamento** e **Chave**.
          2. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          3. Selecione se deseja **tornar essa conexão compatível com a Adobe Experience Platform**.
          4. Clique em **Save**.
          5. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
        * [Beta] Selecione **Yandex**.  
          [<Image alt="" src="https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png" width="944px" />](https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png)
          1. Insira o **nome do bucket**, **a chave de acesso**e **a chave secreta**.
          2. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          3. Selecione se deseja **tornar essa conexão compatível com a Adobe Experience Platform**.
          4. Clique em **Save**.
          5. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
        * Selecione **BigQuery**.  
          [<Image alt="" src="https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png" width="945px" />](https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png)
          1. Insira o project ID do BigQuery e o nome do conjunto de dados.
          2. Clique em **Testar conexão**.
          3. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          4. Clique em **Save**.
          5. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
        * Selecione **Snowflake**.  
          [<Image alt="" src="https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png" width="944px" />](https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png)
          1. Insira sua região e o ID da conta do Snowflake.
          2. Clique em **Testar conexão**.
          3. Verifique se uma mensagem de erro indicando que o bucket path é inválido é exibida.
          4. Clique em **Save**.
          5. Na configuração do Cost ETL, no menu suspenso de **Conexão**, selecione o serviço de nuvem que você criou.
3. Clique em **Próximo**.  
   [<Image alt="" src="https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png" width="746px" />](https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png)
4. Configure o relatório **Version schedule (UTC)**:  
   [<Image alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />](https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png)
   1. Selecione quantos relatórios receber por dia (1, 2, 3 ou 4).
   2. Selecione a hora em que deseja receber os relatórios. [Saiba mais](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. Clique em **Próximo**.
5. Configure os detalhes do relatório:
   1. Selecione 1 ou mais aplicativos para incluir nos relatórios. Selecione **Adicionar todos os aplicativos futuros** para incluir automaticamente os apps que você adicionar no futuro.  
      [<Image alt="" src="https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png" width="566px" />](https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png)
   2. Selecione os relatórios que melhor atendem às suas necessidades de análise. Consulte as descrições na seção [Tipos de relatório](#report-types).
      * O **Summary report** é selecionado por padrão.
      * Para receber um relatório de All cost, é necessário selecionar o **Geo report**.  
        [<Image alt="" src="https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png" width="1921px" />](https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png)
   3. Selecione as dimensões a serem incluídas nos relatórios. **Atenção:** Se você optar por receber o relatório Geo, a dimensão de geo será incluída por padrão. Se você optar por receber o relatório Canal, a dimensão do canal será incluída por padrão.   
      [<Image alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" width="1921px" />](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
   4. Selecione as métricas a serem incluídas nos relatórios.   
      [<Image alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" width="1863px" />](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
6. Clique em **Aplicar**.

</Accordion>

<div id="edit-or-change-connection" />

<Accordion title="Editar ou alterar conexão">

Você pode editar ou alterar conexões para obter dados enviados para locais diferentes (ou adicionais).

**Atenção:** Depois de mudar para uma conexão existente, você não poderá reverter para a sua conexão anterior do Cost ETL.

#### Editar conexão

**Para os editar detalhes de conexão**:

1. Na AppsFlyer, no menu lateral, selecione **Exportar** > **Cost ETL**.
2. Na seção **Conexão de dados**:
   * Para conexões do Data Locker, no menu suspenso **Conexão**, passe o mouse sobre a conexão que você deseja editar. Os detalhes da conexão são exibidos. Clique em **Editar no Data Locker**.  
     [<Image alt="" src="https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png" width="695px" />](https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png)
   * Para conexões de Cost ETL, clique no menu suspenso **detalhes de conexão**. Os detalhes da conexão são exibidos.  
     [<Image alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />](https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png)
3. Siga as instruções na tela para editar seus detalhes de conexão.
4. Clique em **Salvar alterações** ou em **Aplicar** conforme solicitado.

#### Alterar conexão do Data Locker

**Para mudar de uma conexão para outra**:

1. Na AppsFlyer, no menu lateral, selecione **Exportar** > **Cost ETL**.
2. Na seção **Conexão de dados**:
   * Se você já tiver as conexões do Data Locker que deseja configurar, no menu suspenso de **Conexão**, selecione as conexões desejadas para Cost ETL.  
     [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * Se você ainda não tiver uma conexão do Data Locker que deseja configurar, clique em **+ Nova conexão no Data Locker** e crie uma conexão lá. Em seguida, volte para as configurações de Cost ETL e selecione-a no menu suspenso de **Conexão**.  
     [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
3. Clique em **Salvar alterações**.

#### Mudar a conexão do Cost ETL para Data Locker

**Antes de começar**:

* Depois de alternar para uma conexão Data Locker, você não poderá voltar para sua conexão de Cost ETL anterior.
* Ao alternar para uma conexão Data Locker, a estrutura de folder path muda para o seguinte formato, sem afetar os dados do relatório:

  `///t=/dt=/v=<1/2/3/4>/`

**Para mudar de uma conexão de Cost ETL para uma conexão Data Locker**:

1. Na AppsFlyer, no menu lateral, selecione **Exportar** > **Cost ETL**.
2. Em **Conexão de dados**, clique em **Conexões do Data Locker**.  
   [<Image alt="" src="https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png" width="631px" />](https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png)
3. Siga um desses procedimentos para configurar a conexão do Data Locker:
   * Se você já tiver as conexões de dados que deseja configurar, no menu suspenso de **Conexão**, selecione as conexões desejadas para o Cost ETL.  
     [<Image alt="" src="https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png" width="501px" />](https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png)
   * Se você ainda não tiver a conexão de dados que deseja configurar, clique em **+ Nova conexão no Data Locker** e crie uma conexão lá. Em seguida, volte para as configurações de Cost ETL e selecione-a no menu suspenso de **Conexão**.  
     [<Image alt="" src="https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png" width="631px" />](https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png)
4. Clique em **Salvar alterações**.

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="Alterar propriedade de objetos no AWS">

No AWS, por padrão, quando a AppsFlyer registra objetos no seu bucket, o proprietário do objeto é a AppsFlyer. Dependendo do seu processo de envio de dados, talvez você precise alterar a propriedade predefinida para você - o proprietário do bucket.

**Para alterar a propriedade dos objetos no seu bucket**:

1. Entre no AWS Management Console e abra o console do Amazon S3 em <Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>.
2. Na lista **Buckets**, escolha o nome do bucket para o qual você deseja ativar o Object Ownership S3.
3. Acesse a aba de **Permissions**.
4. Em **Object Ownership,** clique em **Edit**.
5. Selecione o **propietário do bucket desejado.**
6. Clique em **Save**.

</Accordion>

## Práticas recomendadas

<div id="report-schedule" />

<Accordion title="Cronograma de relatório">

As configurações de cronograma de relatório permitem que você acesse os dados mais atualizados quando precisar.

Ao escolher seu cronograma de relatório:

* Selecione a hora em que o relatório será exibido - o mais próximo possível da hora em que você começa a processar dados em seu sistema de BI.
* Se você tiver qualquer ad network que forneça os dados do dia anterior mais tarde do que os outras, configure um relatório adicional no momento em que os dados dessa ad network estiverem prontos.

</Accordion>

<div id="override-data" />

<Accordion title="Substituir dados">

Ao extrair e analisar os seus dados, recomendamos extrair dados para uma data e um lote específicos, ou que substitua todos os dados anteriores para os dias que o lote atual fornece. Caso contrário, você poderá ver os mesmos dados repetidos.

Por exemplo, o lote 1 em 20 de fevereiro contém dados de 14 a 20 de fevereiro. Mas os lotes registrados em 19 de fevereiro também continham dados de 14 a 19 de fevereiro. Substitua os dados dos dias anteriores recebidos em 19 de fevereiro pelos dados recebidos no lote mais recente de 20 de fevereiro.

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="Geo versus canal">

Nem todas as ad networks fornecem dados para todas as dimensões em conjunto. Os dados de geo e de canal no Meta ads são os exemplos mais comuns. É por isso que são fornecidos dois conjuntos de dados separados. É garantido que o conjunto de dados de geo contém dados geográficos e que o conjunto de dados de canais contém dados de canais.

Em muitos casos e para muitos canais de mídia, os dados nos conjuntos geo e de canais serão idênticos. Como tal, consuma um dos conjuntos de dados (geo ou canal), de acordo com o que melhor se adequa às suas necessidades.

Se o acordo de integração com um determinado canal de mídia não incluir o canal, fazendo com que esse canal fique em branco, tratamos esses dados como se contivessem o canal.

</Accordion>

<div id="aggregate-data" />

<Accordion title="Dados agregados">

O Cost ETL fornece dados flexíveis e granulares tão detalhados quanto podem ser extraídos da ad network. Para extrair informações úteis de quantidades tão grandes de dados, recomenda-se a agregação dos dados da forma que melhor se adapte às necessidades da sua empresa. Por exemplo, se você precisar compreender os dados de custos a nível da campanha e de país, use essas dimensões.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="Padronização entre ad networks">

Nem todas as ad networks fornecem dados com a mesma granularidade. Por exemplo, o Meta Ads não fornece dados de site ID cost, enquanto o X Ads não fornece dados geo cost. Preste atenção nesses casos quando for agregar dados no Cost ETL e certifique-se de analisar dados parecidos ao comparar ad networks.

</Accordion>

<div id="compare-data" />

<Accordion title="Comparar dados">

O Cost ETL fornece informações sobre todos os seus dados de custos. Algumas campanhas fornecidas no Cost ETL não aparecem em alguns dashboards da AppsFlyer - por exemplo, dados de campanhas inativas, ou seja, campanhas sem nenhuma instalação registrada. Para comparar os dados, procure um campaign ID específico no dashboard de visão geral e compare-o com os seus dados de custo no Cost ETL. <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">Saiba mais sobre a disponibilidade dos dados de custos</Anchor>

</Accordion>

<div id="combine-geo-report-and-all-cost-report" />

<Accordion title="Combinar Geo report e All Cost report">

Para obter dados de custo completos relacionados à atribuição para Google, Meta, TikTok (mobile e não mobile) e outras fontes de mídia (somente mobile), use a seguinte consulta:

```sql
with etl as (
    select *
    from etl
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

allcost as (
    select *
    from allcost
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

main as (
    select
        case when etl.date is null then 'all cost' else 'cost etl' end as report,
        coalesce(etl.date, allcost.date) as date,
        coalesce(etl.app_id, allcost.app_id) as app_id,
        etl.os,
        allcost.platform,
        coalesce(etl.media_source, allcost.media_source) as media_source,
        coalesce(etl.agency, allcost.agency) as agency,
        coalesce(etl.campaign_id, allcost.campaign_id) as campaign_id,
        coalesce(etl.campaign, allcost.campaign) as campaign,
        coalesce(etl.adset_id, allcost.adset_id) as adset_id,
        coalesce(etl.adset, allcost.adset) as adset,
        coalesce(etl.ad_id, allcost.ad_id) as ad_id,
        coalesce(etl.ad, allcost.ad) as ad,
        coalesce(etl.geo, allcost.geo) as geo,
        coalesce(etl.channel, allcost.channel) as channel,
        coalesce(etl.site_id, allcost.site_id) as site_id,
        coalesce(etl.ad_account, allcost.ad_account) as ad_account,
        coalesce(etl.keyword_id, allcost.keyword_id) as keyword_id,
        coalesce(etl.keywords, allcost.keywords) as keywords,
        coalesce(etl.campaign_objective, allcost.campaign_objective) as campaign_objective,
        coalesce(etl.af_cost_model, allcost.af_cost_model) as af_cost_model,
        coalesce(etl.bid_strategy, allcost.bid_strategy) as bid_strategy,
        coalesce(etl.af_bid_strategy, allcost.af_bid_strategy) as af_bid_strategy,
        coalesce(etl.currency, allcost.currency) as currency,
        coalesce(etl.cost, allcost.cost) as cost,
        coalesce(etl.impressions, allcost.impressions) as impressions,
        coalesce(etl.clicks, allcost.clicks) as clicks,
        coalesce(etl.installs, allcost.installs) as installs,
        coalesce(etl.re_attributions, allcost.re_attributions) as re_attributions,
        coalesce(etl.re_engagements, allcost.re_engagements) as re_engagements,
        coalesce(etl.original_cost, allcost.original_cost) as original_cost,
        coalesce(etl.reported_impressions, allcost.reported_impressions) as reported_impressions,
        coalesce(etl.reported_clicks, allcost.reported_clicks) as reported_clicks,
        coalesce(etl.reported_conversions, allcost.reported_conversions) as reported_conversions,
        coalesce(etl.ctr, allcost.ctr) as ctr,
        coalesce(etl.cvr, allcost.cvr) as cvr,
        coalesce(etl.ecpm, allcost.ecpm) as ecpm,
        coalesce(etl.cpi, allcost.cpi) as cpi,
        coalesce(etl.ccvr, allcost.ccvr) as ccvr,
        coalesce(etl.cvvr, allcost.cvvr) as cvvr,
        coalesce(etl.reported_cvr, allcost.reported_cvr) as reported_cvr,
        coalesce(etl.install_diff, allcost.install_diff) as install_diff,
        coalesce(etl.click_diff, allcost.click_diff) as click_diff,
        coalesce(etl.impression_diff, allcost.impression_diff) as impression_diff,
        coalesce(etl.ecpc, allcost.ecpc) as ecpc,
        coalesce(etl.video_25p_views, allcost.video_25p_views) as video_25p_views,
        coalesce(etl.video_50p_views, allcost.video_50p_views) as video_50p_views,
        coalesce(etl.video_75p_views, allcost.video_75p_views) as video_75p_views,
        coalesce(etl.video_completions, allcost.video_completions) as video_completions
    from etl
    full join allcost
        on etl.date = allcost.date
        and etl.app_id = allcost.app_id
        and etl.media_source = allcost.media_source
        and etl.campaign_id = allcost.campaign_id
        and etl.adset_id = allcost.adset_id
        and etl.ad_id = allcost.ad_id
        and etl.channel = allcost.channel
        and etl.geo = allcost.geo
        and etl.agency = allcost.agency
        and etl.site_id = allcost.site_id
        and etl.keyword_id = allcost.keyword_id
),

dedup as (
    select *,
           row_number() over (
               partition by date, media_source, agency, campaign_id, adset_id, ad_id, geo, channel, site_id, keyword_id
               order by report desc, cost desc
           ) as rank_for_dedup
    from main
)

select *
from dedup
where rank_for_dedup = 1;
```

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="Combinar relatórios do Cost ETL e de Cohort">

Você pode combinar relatórios de Cost ETL custo com relatórios agregados de Cohort (ou relatórios padrão de Cohort via Data Locker) em seu sistema de BI. Juntos, eles oferecem uma visão mais completa da sua performance de marketing com dados atualizados e precisos (incluindo cliques, impressões, custo, receita, eventos in-app, etc). Você pode usar esses dados combinados para acessar seu ROAS, CPA, etc. <Anchor target="_blank" href="/marketers/pt/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Saiba mais</Anchor>

</Accordion>

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Fuso horário | Se o fuso horário for alterado, os dados de custos aparecem duplicados no dia e no dia seguinte à alteração. <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">Saiba mais</Anchor> |
| Atualização dos dados | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intradiário</Anchor>. Durante a configuração do Cost ETL, você define o cronograma de relatórios, ou seja, quando você deseja que os relatórios sejam enviados.</li><li>Os dados geralmente chegam no intervalo de uma hora antes da hora selecionada. Portanto, se você deseja que um relatório seja enviado até as 6h, ele chegará entre as 5 e 6h.</li></ul>**Atenção:** Quando os dados de custos chegam ao seu bucket, a transferência de dados para os seus sistemas de BI pode variar muito, dependendo do tamanho do relatório e do arquivo parquet, que pode ir de alguns KBs a muitos GBs. |
| Relatório de todos os custos | <ul><li>Não inclui dados de custo para campanhas de Google Performance Max.</li><li>Sem suporte para alterações no nome da campanha</li></ul> |
| Dados de custo de campanhas SKAN | <ul><li>O Cost ETL somente fornece dados de custo para campanhas na SKAN se a campanha tiver pelo menos uma conversão clássica.</li><li>Para campanhas que têm somente conversões da SKAN, os dados de custo só estão disponíveis se:<ul><li>A ad network relacionada é o Twitter (X) ou Meta, ou</li><li>A integração com a ad network é marcada como Campanha inativa (Coluna M= "Sim" <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">nessa lista</Anchor>).</li></ul></li></ul> |
| Suporte para aplicativos de CTV e PC | Aplicativos de PC e CTV não estão disponíveis para relatórios de Cost ETL. |
| Disponibilidade de custo do Google Web e Meta Web | Para incluir dados de custo de <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#configurar-a-integração-do-google-ads-na-appsflyer">Google Web (`pid=googleads_int`</Anchor>) e <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#como-criar-uma-campanha-web-no-meta-ads">Meta Web (`pid=metaweb_int`)</Anchor> no relatório All Cost, você deve criar uma conexão de custo na aba Custo das suas integrações ativas do <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google Ads (`pid=googleadwords_int`)</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads (`pid=facebook_int`)</Anchor>. Sem essas conexões, os dados de custo do Google e do Meta Web não aparecerão no relatório. |

</Accordion>

<div data-zendesk-anchors="four-types-of-cost-etl-reports=quatro-tipos-de-relat%C3%B3rios-de-cost-etl h_01K4WKGHP4S2B23R0Z57NFESPE=quatro-tipos-de-relat%C3%B3rios-de-cost-etl h_01JZJVXY0BA25QM9PK4YRT8DZ6=nota cost-etl-report-comparison-table=tabela-de-vis%C3%A3o-geral-dos-tipos-de-relat%C3%B3rio-de-cost-etl h_01K4WN2VMPZYA6273EDW7CSJZ9=tabela-de-vis%C3%A3o-geral-dos-tipos-de-relat%C3%B3rio-de-cost-etl report-details=detalhes-do-relat%C3%B3rio h_01JYXKJFYG6FKM8S6C8GYHPK6T=detalhes-do-relat%C3%B3rio h_01JYXKJFYGE8SHR071RNXW5V97=data-freshness h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure data-locker-connection-directory-structure=estrutura-do-diret%C3%B3rio-de-conex%C3%A3o-do-data-locker h_01JD4P98XF9S47EDHP38VXW1XS=estrutura-do-diret%C3%B3rio-de-conex%C3%A3o-do-data-locker cost-etl-connection-directory-structure=estrutura-do-diret%C3%B3rio-de-conex%C3%A3o-do-cost-etl h_01JKWMF6V57C35F1A0BVH18CY1=estrutura-do-diret%C3%B3rio-de-conex%C3%A3o-do-cost-etl h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=camposdimens%C3%B5es h_01HA29GW8PQATB4K5VJP1HD4NW=camposdimens%C3%B5es metrics=m%C3%A9tricas h_01HA29GW8PZTS7XDWGYWXFZPYG=m%C3%A9tricas procedures=procedimentos 01JCZDRERADNNX04RT752793PG=procedimentos 01JCZP8A5W67W66N886KHNRR4A=set-up-cost-etl 01JCZME67YK848NM0RJTM1J5ZG=edit-or-change-connection edit-connection=editar-conex%C3%A3o h_01JCZMGC8J41Y7H4JGZDVWYDJS=editar-conex%C3%A3o change-data-locker-connections=alterar-conex%C3%A3o-do-data-locker h_01JCZNQF3QE7P8PBQPKXZK1SA2=alterar-conex%C3%A3o-do-data-locker change-from-cost-etl-to-data-locker-connection=mudar-a-conex%C3%A3o-do-cost-etl-para-data-locker h_01JKWMF6V70W9FA90SSKJ77R2Z=mudar-a-conex%C3%A3o-do-cost-etl-para-data-locker h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership best-practices=pr%C3%A1ticas-recomendadas h_01HA29GW8QKPQXE4GHECAC5R5X=pr%C3%A1ticas-recomendadas h_01J0NRD227RQR50CMNW60SF7SK=report-schedule h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01K4WNM1ZFSMFZEV3V2HQ5PYQE=combine-geo-report-and-all-cost-report h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports additional-information=informa%C3%A7%C3%B5es-adicionais h_01HA286GA6WPYVNN7KCXK7DGFM=informa%C3%A7%C3%B5es-adicionais h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
