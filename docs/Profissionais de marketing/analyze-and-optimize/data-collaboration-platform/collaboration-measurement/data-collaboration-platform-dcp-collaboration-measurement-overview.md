---
title: >-
  Plataforma de colaboração de dados (DCP) - Mensuração de colaboração - Visão
  geral
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-01-27T08:21:27Z'
  edited_at: '2026-10-20T03:37:17Z'
  id: 32143318560017
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/32143318560017
---
> **Resumo:**  Dê os primeiros passos com a mensuração de colaboração, aprendendo seus conceitos fundamentais e procedimentos de configuração.

<div id="the-three-data-sources-of-measurement" />

## As três fontes de dados de mensuração

O modelo de mensuração do DCP atribui eventos de conversão a eventos de engajamento que ocorrem em um contexto de colaboração. Esse processo requer dados de três fontes de dados principais: conversões, engajamentos e mapeamento de campanhas. Cada fonte desempenha um papel crítico no fluxo de atribuição.

<div id="conversions" />

<Accordion title="Conversões">

Os dados de conversão contêm detalhes sobre as ações do usuário, como compras e SKUs (Stock Keeping Units) ou Consumer Packaged Goods (CPGs) associados. Cada instância de conversão representa um único evento de conversão, capturando detalhes como SKU, user ID e hora do evento.

**Exemplos de parâmetros de conversão**

| **Campo** | **Valor** |
| --- | --- |
| `ativado` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `nome_do_evento` | purchase |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |

A AppsFlyer oferece acesso aos eventos de conversão por meio da integração com o seu app usando o SDK da AppsFlyer, ou por meio de fontes de dados personalizadas fornecidas pelos colaboradores. Os eventos de conversão na web e na loja também podem ser fornecidos usando fontes de dados personalizadas.

</Accordion>

<div id="engagements" />

<Accordion title="Engajamentos">

A fonte de engajamento contém detalhes sobre as interações do usuário com anúncios, como cliques ou impressões. Cada instância representa um evento de engajamento e inclui atributos como o ID da campanha, a fonte de mídia e o tipo de toque (por exemplo, clique ou impressão).

**Exemplos de parâmetros de engajamento**

| **Campo** | **Valor** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `fonte_de_mídia` | google |
| `Twitter` | grc\_web\_ftu\_seq |
| `attributed_touch_time` | 2024-09-28T17:05:34 |
| `tipo_de_toque_atribuído` | impression |
| `nome_do_evento` | start\_game |

Para acessar os dados de engajamento, em [campanhas on-site](#onsite-and-offsite-campaign-measurement), você pode configurar novos eventos in-app com dados de atribuição no parâmetro `event_value` usando o SDK da AppsFlyer, ou compartilhar os dados por meio de uma fonte personalizada.

Em [campanhas off-Site](#onsite-and-offsite-campaign-measurement), os dados de engajamento são recebidos de um terceiro, não por meio de eventos in-app ou de uma fonte personalizada.

</Accordion>

<div id="campaign-mapping" />

<Accordion title="Mapeamento de campanhas">

A fonte de mapeamento da campanha nos permite determinar o engajamento que acionou cada conversão. Um registro de mapeamento de campanha vincula eventos de conversão a eventos de engajamento ao associar SKUs ou CPGs a IDs de campanha. O DCP mapeia a fonte de dados de mapeamento de campanha usando as SKUs na fonte de dados de conversão para identificar conversões acionadas por campanha.

**Campos de mapeamento de campanha**

| **Campo** | **Valor** |
| --- | --- |
| `collaborator_name` | fasion\_site |
| `collaborator_id` | 10079 |
| `id_da_campanha` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |

As informações de mapeamento acima são fornecidas à AppsFlyer como uma fonte de dados personalizada.

</Accordion>

<div id="on-site-vs-off-site-campaigns" />

## Considere qual caso se encaixa à sua necessidade.

O DCP mensurar campanhas on-site de maneira diferente das campanhas off-site. Enquanto as campanhas on-site são executadas em uma das plataformas do colaborador, as campanhas off-site são executadas em plataformas de terceiros, como Facebook, Google Ads e outras SRNs. Essas diferenças afetam como as audiências são alcançadas, como os dados são coletados e como a atribuição é realizada.

<div id="offsite-campaigns" />

<Accordion title="Conversões">

Campanhas off-site envolvem engajamentos de usuários em plataformas de terceiros (como Meta ou Google), com conversões ocorrendo nas propriedades próprias do colaborador e atribuídas a esses engajamentos off-site.

* **Exemplo:** Uma marca veicula um anúncio no Facebook direcionado aos dados segmentados de clientes da CMN. Quando os usuários veem o anúncio no Facebook e clicam nele, eles são levados à página do produto da CMN.
* **Atribuição:** A DCP compartilha eventos de conversão com o party, que realiza sua própria atribuição; em seguida, a DCP recupera resultados agregados pela API de reportar do party.

</Accordion>

<div id="onsite-campaigns" />

<Accordion title="Engajamentos">

Campanhas on-site envolvem engajamentos de usuários e conversões que ocorrem nas propriedades próprias de um colaborador (como seu aplicativo ou site), com conversões atribuídas a engajamentos on-site.

* **Exemplo:** Uma marca promove um produto em um site de Commerce Media Network. A audiência inclui compradores anteriores da plataforma CMN, segmentados por parâmetros como interesse por categoria ou histórico de compras. Quando os usuários veem e clicam no banner da campanha, eles são levados à página de detalhes do produto no mesmo site.
* **Atribuição:** A DCP atribui diretamente as conversões às campanhas on-site usando dados de engajamento party do site ou aplicativo do colaborador.

<div id="combined-onsite-and-offsite-campaigns" />

<Accordion title="Mensuração de campanhas on-site e off-site">

Campanhas combinadas envolvem engajamentos de usuários que ocorrem tanto on-site quanto off-site, com conversões ocorrendo nas propriedades próprias do colaborador e atribuídas a engajamentos de qualquer uma das fontes usando mensuração unificada e desduplicação.

* **Exemplo:** Uma marca promove um produto no site da CMN e também veicula anúncios no Facebook segmentados para os clientes da CMN. Os engajamentos e as conversões tanto da campanha on-site quanto da campanha no Facebook são capturados, desduplicados e mensurados em conjunto.
* **Atribuição:** A DCP consolida dados de conversão dos canais on-site e off-site em uma tabela de atribuição compartilhada, aplicando lógica de desduplicação e apresentando métricas unificadas por campanha e SKU.

</Accordion>

</Accordion>

<div id="the-dcp-measurement-process" />

## O processo de mensuração no DCP

O processo de mensuração da DCP define como os registros de conversão de eventos in-app do SDK e arquivos de fonte personalizados são validados, normalizados e associados a engajamentos de campanha em [campanhas on-site e off-site](https://www.notion.so/Collaboration-measurement-Overview-255b7b13af5f80fa83d2dc77e337c960?pvs=21).

<div id="onsite-measurement-flow" />

<Accordion title="Fluxo de mensuração on-site">

O fluxo de mensuração on-site da DCP processa eventos in-app e registros de fonte personalizados coletados no aplicativo móvel ou site da CMN ou do anunciante. A DCP atribui essas conversões internamente usando a lógica de atribuição da AppsFlyer.

O fluxo de mensuração on-site processa dados de conversão e de engajamento originados de duas fontes principais:

* **Eventos in-app (IAEs)** são coletados por meio do SDK da AppsFlyer incorporado ao app mobile do colaborador.
* Os **arquivos de eventos de fonte personalizada** são enviados pelos colaboradores à AppsFlyer.

Ambos os tipos de evento são normalizados em uma estrutura unificada e processados pelo mesmo mecanismo de atribuição.

<div id="1-configure-measurement-sources" />

### 1. Configurar fontes de medição

As etapas desse processo estão descritas abaixo.

* **Eventos in-app:** Os colaboradores identificam quais eventos in-app (por exemplo, compra, cadastro) devem ser mensurados como conversões ou engajamentos. Esses eventos já devem ser coletados pelo SDK da AppsFlyer, e os nomes do aplicativo e do evento devem ser selecionados explicitamente na configuração do DCP.
* **Arquivos de eventos de fonte personalizada:** Os colaboradores configuram o acesso a arquivos de dados externos (por exemplo, do BigQuery, S3 ou Snowflake) e mapeiam campos-chave, como user\_id, campaign\_id e SKU, para o esquema do DCP, para dar suporte à atribuição.

<div id="2-prepare-and-map-conversion-data" />

### 2. Preparar e mapear dados de conversão

O DCP conecta cada evento de conversão que foi mapeado para uma campanha a um evento de engajamento com o mesmo user ID e ID de campanha, criando um registro de conversões atribuídas que contém os detalhes de campanha e conversão.

* A fonte do mapeamento de campanha faz a correspondência entre conversões a engajamentos, mapeando o SKU do evento de conversão para o ID da campanha do evento de engajamento.
* As conversões que não podem ser associadas a nenhuma campanha são marcadas como **orgânicas**.

<div id="3-link-conversions-to-engagements" />

### 3. Vincular conversões a engajamentos

O DCP vincula as conversões correspondentes aos engajamentos usando os seguintes critérios:

* Um **ID de usuário** compartilhado
* O mesmo **ID da campanha**

Isso resulta em registros de conversão atribuídos, enriquecidos com metadados de campanha e de engajamento.

<div id="4-split-multi-sku-conversions" />

### 4. Dividir conversões com vários SKUs

Se um evento de conversão incluir vários SKUs:

* O DCP separa os registros de conversões atribuídas com vários SKUs em registros individuais, cada um representando um único SKU.
* Cada registro reflete a atribuição de um único **alvo de conversão**.

<div id="5-filter-non-target-skus" />

### 5. Filtrar SKUs fora do alvo

Para garantir que apenas as conversões relevantes sejam mantidas:

* O DCP filtra registros de SKUs que não são destinos de conversão para a campanha.

<div id="6-deduplicate-conversion-events" />

### 6. Desduplicar eventos de conversão

Antes da atribuição, o DCP remove duplicatas:

* Registros duplicados da mesma fonte personalizada (por exemplo, uploads repetidos) são descartados.
* Se existir um evento in-app (IAE) correspondente, ele substituirá o registro da fonte personalizada.

<div id="7-apply-attribution-logic" />

### 7. Aplicar lógica de atribuição

O DCP aplica o modelo de atribuição de último toque da AppsFlyer com as seguintes regras:

* **Vários engajamentos por conversão**: o **último toque** é selecionado com base na escala de prioridade da AppsFlyer.
* **Um engajamento vinculado a várias conversões**: somente a **primeira** conversão é atribuída ao engajamento; as conversões adicionais permanecem não atribuídas.

> Para mais detalhes, consulte as prioridades do método de atribuição (cascata de atribuição).

<div id="8-output-attributed-conversion-dataset" />

### 8. Saída: conjunto de dados de conversões atribuídas

A saída final inclui:

* Atribuição a um único engajamento de campanha por conversão
* Registros de conversão no nível de SKU limpos e validados
* O DCP agrega conversões atribuídas para gerar insights, incluindo o total de conversões.
* Registros de conversão prontos para dashboards de análise e exportações

</Accordion>

<div id="offsite-measurement-flow" />

<Accordion title="Fluxo de mensuração off-site">

Os **eventos de conversão off-site** são fornecidos por colaboradores por meio de **arquivos de fonte personalizados** e devem incluir os identificadores necessários para atribuição, como o ID de clique do Google (`gclid`) ou o ID de clique do Facebook (`fbclid`). Esses eventos são compartilhados com plataformas externas, como Google e Meta, que cruzam os dados com seus registros de campanha e retornam **metadados enriquecidos**, incluindo identificadores de campanha, conjunto de anúncios e criativo.

<div id="1-prepare-conversion-data" />

### 1. Preparar dados de conversão

Os registros de conversão são padronizados com base na configuração da colaboração:

* Os colaboradores mapeiam campos personalizados para um esquema DCP unificado de conversão.
* Google Ads e Meta Ads exigem campos específicos; as regras de validação garantem que os mapeamentos atendam aos padrões de cada parceiro antes de continuar.

<div id="2-deduplicate-conversion-events" />

### 2. Desduplicar eventos de conversão

Antes da atribuição, o DCP remove registros duplicados da mesma fonte personalizada (por exemplo, uploads repetidos).

<div id="3-filter-for-sharing-eligibility" />

### 3. Filtrar por elegibilidade de compartilhamento

O DCP verifica se as conversões off-site atendem aos critérios de compartilhamento:

* Há um identificador válido específico do canal (por exemplo, GCLID, FBCLID).
* A conversão corresponde a uma ação de campanha ou a um SKU definido.
* A conversão está dentro da janela de lookback:
  * Meta: 1, 7 ou 28 dias para clique e view-through.
  * Google: definido na plataforma; substituição via API não é compatível.

As conversões que não atenderem a qualquer um dos critérios serão excluídas do compartilhamento com parceiros.

<div id="4-filter-according-to-last-touch-attribution" />

### 4. Filtrar de acordo com a atribuição de último toque

A atribuição é definida com base no touchpoint mais recente:

* Se um ID de clique válido do Google ou da Meta for mais recente, a atribuição será dada a esse parceiro e compartilhada somente com ele.
* Se ambos os IDs de clique existirem na conversão, o mais recente prevalece.

<div id="5-share-with-google-and-meta" />

### 5. Compartilhar com Google e Meta

As conversões qualificadas são compartilhadas com segurança por meio das APIs dos parceiros:

* **Meta:** API de Conversões (CAPI)
* **Google:** API de Conversões Offline (OCI)

Cada conversão é enviada a apenas um parceiro. Os colaboradores devem configurar a conta de destino (ID do conjunto de dados da Meta ou ID da ação de conversão do Google).

<div id="6-google-and-meta-response-enrichment" />

### 6. Enriquecimento de resposta do Google e da Meta

Google e Meta retornam dados de atribuição enriquecidos por meio de suas APIs de insights, incluindo:

* ID da campanha
* ID do conjunto de anúncios
* ID do anúncio
* ID criativa

A AppsFlyer executa a atribuição com base nos registros enriquecidos.

<div id="7-output-attributed-conversion-dataset" />

### 7. Saída: conjunto de dados de conversão atribuída

A saída final inclui:

* Registros de conversão em nível de SKU limpos e validados
* Quando um único evento de engajamento é responsável por vários eventos de conversão, apenas a primeira conversão é atribuída ao engajamento, enquanto as outras permanecem não atribuídas.
* Os registros de conversão estão prontos para dashboards de analytics e exportações

</Accordion>

<div id="combined-onsite-and-offsite-measurement-flow" />

<Accordion title="Fluxo combinado de mensuração on-site e off-site">

Este fluxo descreve como a Data Collaboration Platform (DCP) da AppsFlyer processa dados de conversão de várias fontes, incluindo:

* **Conversões on-site**, que incluem eventos in-app e registros de fonte personalizados coletados no CMN ou no app mobile ou site do anunciante. A DCP atribui essas conversões internamente usando a lógica de atribuição da AppsFlyer.
* **Conversões off-site**, em que os dados de conversão se originam de uma fonte personalizada e são compartilhados com plataformas externas, como Google e Meta. Essas plataformas fazem a correspondência dos dados com seus próprios registros de campanha e retornam metadados enriquecidos, incluindo identificadores de campanha, conjunto de anúncios e criativo.

O fluxo de atribuição off-site e on-site da DCP elimina duplicações, atribui, enriquece e une todos os dados de conversão para gerar um único conjunto de dados unificado de performance.

<Image align="center" alt="Notion 2025-08-25 16.10.35.png" src="https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png" width="1622px" />

<div id="1-on-site-and-off-site-record-processing-is-performed" />

### 1. O processamento de registros no local e fora do local é realizado

Os registros de conversão são padronizados com base na configuração da colaboração:

* Processamento on-site até a etapa 6, inclusive, na atribuição on-site.
* Processamento off-site até a etapa 4, inclusive, na atribuição off-site.

<div id="2-apply-last-touch-attribution" />

### 2. Aplicar atribuição de último toque

A atribuição é definida com base no touchpoint mais recente:

* Se um evento CMN (on-site) for o mais recente, a conversão será atribuída à CMN e não será compartilhada com a Meta nem com o Google.
* Se um ID de clique válido do Google ou da Meta for mais recente, a atribuição irá para esse parceiro e será compartilhada apenas com ele.
* Se ambos os IDs de clique existirem na conversão, o mais recente prevalecerá.

<div id="3-share-with-google-and-meta" />

### 3. Compartilhar com Google e Meta

As conversões qualificadas são compartilhadas de forma segura por meio das APIs dos parceiros:

* **Meta:** API de conversões (CAPI)
* **Google:** API de conversão offline (OCI)

Cada conversão é enviada para apenas um parceiro. Os anunciantes devem configurar a conta de destino (ID do conjunto de dados da Meta ou ID da ação de conversão do Google).

<div id="4-off-site-response-enrichment" />

### 4. Enriquecimento da resposta off-site

Google e Meta retornam dados de atribuição enriquecidos por meio de suas APIs de insights, incluindo:

* ID da campanha
* ID do conjunto de anúncios
* ID do anúncio
* ID criativa

<div id="5-on-site-and-off-site-conversion-merge" />

### 5. Mesclagem de conversões on-site e off-site

O DCP mescla essas conversões off-site com conversões on-site em um conjunto de dados final no qual cada conversão é:

* Atribuída a uma única fonte: Google, Meta ou CMN
* Enriquecida com metadados da campanha
* Pronta para dashboards, exportações e análises de performance

</Accordion>

<div id="set-up-collaboration-measurement" />

## Configurar a mensuração de colaboração

O processo de configuração da mensuração pode ser descrito em seis etapas, cada uma com um artigo dedicado:

1. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-determine-your-collaboration-measurement-use-cas">Determine seu caso de uso de mensuração da colaboração</Anchor>
2. [Prepare as fontes de dados que alimentam o processo de atribuição](https://www.notion.so/Prepare-measurement-data-sources-175b7b13af5f8073918df666dc8c0aa9?pvs=21).
3. [Configure o DCP](https://www.notion.so/Configure-collaboration-measurement-176b7b13af5f805a904acccbbb371a45?pvs=21) para acessar as fontes de dados e realizar a atribuição.
4. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-view-measurement-dashboard">Consumir os dados de mensuração atribuídos em dashboards e relatórios</Anchor>
5. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-view-measurement-reports">O processo de atribuição usa a seguinte lógica:</Anchor>
6. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-run-a-dynamic-query-in-dcp">Executar uma consulta dinâmica</Anchor>

<div data-zendesk-anchors="the-three-data-sources-of-measurement=as-tr%C3%AAs-fontes-de-dados-de-mensura%C3%A7%C3%A3o h_01K3GNC7NFJV6W4NPEXJ4SKSKA=as-tr%C3%AAs-fontes-de-dados-de-mensura%C3%A7%C3%A3o h_01K3GNC7NF2ZASWHYZJCPYHF2D=conversions h_01K3GNC7NFMAQ8S8A0YN79YRM8=engagements h_01K3GNC7NG2QYKV3ZTGYEHMDYT=campaign-mapping onsite-vs-offsite-campaigns=considere-qual-caso-se-encaixa-%C3%A0-sua-necessidade h_01K3GNC7NGP2FXZXQRAS5H8DE1=considere-qual-caso-se-encaixa-%C3%A0-sua-necessidade h_01K3GNC7NGDDSBGTPD7WVH1H2N=offsite-campaigns h_01K3GNC7NGKHSC7W6B5GG3M10Y=onsite-campaigns h_01K3GNC7NGMG4CCSWVJAVEN24E=combined-onsite-and-offsite-campaigns the-dcp-measurement-process=o-processo-de-mensura%C3%A7%C3%A3o-no-dcp h_01K3GNC7NG1S37JPMH31A6RRSR=o-processo-de-mensura%C3%A7%C3%A3o-no-dcp h_01K3GNC7NGKJNH3BX53PJ9HQ90=onsite-measurement-flow 1-configure-measurement-sources=1-configurar-fontes-de-medi%C3%A7%C3%A3o h_01K3GPJQJC29ZJJTMM9BHA97H1=1-configurar-fontes-de-medi%C3%A7%C3%A3o 2-prepare-and-map-conversion-data=2-preparar-e-mapear-dados-de-convers%C3%A3o h_01K3GNC7NGMSPQTGNNCRYVWWW4=2-preparar-e-mapear-dados-de-convers%C3%A3o 3-link-conversions-to-engagements=3-vincular-convers%C3%B5es-a-engajamentos h_01K3GNC7NGJPNZ3EEMHQP5E04V=3-vincular-convers%C3%B5es-a-engajamentos 4-split-multisku-conversions=4-dividir-convers%C3%B5es-com-v%C3%A1rios-skus h_01K3GNC7NG6DX2B825C5B6TVS0=4-dividir-convers%C3%B5es-com-v%C3%A1rios-skus 5-filter-nontarget-skus=5-filtrar-skus-fora-do-alvo h_01K3GNC7NGSED134G0PGDZGPDB=5-filtrar-skus-fora-do-alvo 6-deduplicate-conversion-events=6-desduplicar-eventos-de-convers%C3%A3o h_01K3GNC7NGBDJ2JCY0HQ61412X=6-desduplicar-eventos-de-convers%C3%A3o 7-apply-attribution-logic=7-aplicar-l%C3%B3gica-de-atribui%C3%A7%C3%A3o h_01K3GNC7NG7Y8XZ9VH3SK47DAR=7-aplicar-l%C3%B3gica-de-atribui%C3%A7%C3%A3o 8-output-attributed-conversion-dataset=8-sa%C3%ADda-conjunto-de-dados-de-convers%C3%B5es-atribu%C3%ADdas h_01K3GNC7NGFY21QVJY8QRNHGVK=8-sa%C3%ADda-conjunto-de-dados-de-convers%C3%B5es-atribu%C3%ADdas h_01K3GNC7NHG5GBRC0X4M5DZ6PP=offsite-measurement-flow 1-prepare-conversion-data=1-preparar-dados-de-convers%C3%A3o h_01K3GNC7NH3CP2HMZTFDK050FA=1-preparar-dados-de-convers%C3%A3o 2-deduplicate-conversion-events=2-desduplicar-eventos-de-convers%C3%A3o h_01K3GNC7NHD0REAV4Q4EMEXPPX=2-desduplicar-eventos-de-convers%C3%A3o 3-filter-for-sharing-eligibility=3-filtrar-por-elegibilidade-de-compartilhamento h_01K3GNC7NHX6VN5XV5ADTH92CT=3-filtrar-por-elegibilidade-de-compartilhamento 4-filter-according-to-lasttouch-attribution=4-filtrar-de-acordo-com-a-atribui%C3%A7%C3%A3o-de-%C3%BAltimo-toque h_01K3GNC7NH598P4G6VVSBQNVTF=4-filtrar-de-acordo-com-a-atribui%C3%A7%C3%A3o-de-%C3%BAltimo-toque 5-share-with-google-and-meta=5-compartilhar-com-google-e-meta h_01K3GNC7NHAQMGXH6JJKEWHGV5=5-compartilhar-com-google-e-meta 6-google-and-meta-response-enrichment=6-enriquecimento-de-resposta-do-google-e-da-meta h_01K3GNC7NHVWVZ10A1Y4DW5M6G=6-enriquecimento-de-resposta-do-google-e-da-meta 7-output-attributed-conversion-dataset=7-sa%C3%ADda-conjunto-de-dados-de-convers%C3%A3o-atribu%C3%ADda h_01K3GNC7NHFTD0CKQ2GSNNCE25=7-sa%C3%ADda-conjunto-de-dados-de-convers%C3%A3o-atribu%C3%ADda h_01K3GNC7NHM6HAYCJ9Q1CX359B=combined-onsite-and-offsite-measurement-flow 1-onsite-and-offsite-record-processing-is-performed=1-o-processamento-de-registros-no-local-e-fora-do-local-%C3%A9-realizado h_01K3GNC7NHW2M399S909QZE9H9=1-o-processamento-de-registros-no-local-e-fora-do-local-%C3%A9-realizado 2-apply-lasttouch-attribution=2-aplicar-atribui%C3%A7%C3%A3o-de-%C3%BAltimo-toque h_01K3GNC7NH3XJRK6N0PC8BWPXT=2-aplicar-atribui%C3%A7%C3%A3o-de-%C3%BAltimo-toque 3-share-with-google-and-meta=3-compartilhar-com-google-e-meta h_01K3GNC7NHXMDC2CQQN8Q95DNH=3-compartilhar-com-google-e-meta 4-offsite-response-enrichment=4-enriquecimento-da-resposta-off-site h_01K3GNC7NHVGQNNVWMKZTAQ03D=4-enriquecimento-da-resposta-off-site 5-onsite-and-offsite-conversion-merge=5-mesclagem-de-convers%C3%B5es-on-site-e-off-site h_01K3GNC7NH2PZ2KFBJHTG1ZZTE=5-mesclagem-de-convers%C3%B5es-on-site-e-off-site set-up-collaboration-measurement-in-four-steps=configurar-a-mensura%C3%A7%C3%A3o-de-colabora%C3%A7%C3%A3o h_01K3GNC7NHSCW4C2845N0MVQZM=configurar-a-mensura%C3%A7%C3%A3o-de-colabora%C3%A7%C3%A3o" />
