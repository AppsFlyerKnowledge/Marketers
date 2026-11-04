---
title: >-
  Plataforma de colaboração de dados (DCP) - Prepare os dados de origem para
  ingestão
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-08-18T00:07:16Z'
  id: 43205325114897
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/43205325114897
---
> **Resumo:** Prepare seus dados de origem para maximizar as taxas de correspondência entre os conjuntos de dados dos colaboradores e otimizar os resultados da colaboração.

<div id="about-data-preparation" />

## Sobre a preparação de dados

A <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-guide">plataforma de colaboração de dados (DCP)</Anchor> da AppsFlyer foi concebida para ingerir e processar dados em grande escala: transacionais, no nível do usuário ou uma combinação de ambos, proveniente de vários colaboradores. Depois da ingestão, a DCP pode fazer a correspondência de usuários entre conjuntos de dados por meio de identificadores compartilhados (por exemplo, e-mails com hash ou números de telefone com hash) e permitir fluxos de trabalho de colaboração baseados em dados.

Este artigo descreve:

* Os tipos de dados que a DCP pode processar (transacionais, no nível do usuário ou uma combinação de ambos)
* Como estruturar os dados para maximizar as taxas de correspondência entre os colaboradores e otimizar a correspondência realizada pelos parceiros na ativação
* Quais estruturas de dados são recomendadas e quais não são
* Como lidar com identificadores de múltiplos valores ao usar arquivos CSV

<div id="understand-data-types" />

## Compreender os tipos de dados

A maioria das fontes utilizadas em colaborações envolve um ou ambos os tipos de dados:

* **Dados no nível do usuário (identidade)**
  * **Objetivo:** Representar cada usuário e os identificadores utilizados para a correspondência
  * **Estrutura recomendada:** Uma linha por usuário
* **Dados transacionais (evento)**
  * **Objetivo:** Representar ações do usuário (compras, visitas e transações)
  * **Estrutura típica:** Várias linhas por usuário (porque um usuário pode ter muitas transações)

<div id="data-structuring-guidelines" />

## Diretrizes para estruturação de dados

Esta seção descreve as diretrizes para estruturação de dados da DCP e as práticas recomendadas.

<div id="workflow-and-structuring-guidelines" />

<Accordion title="Estruturas de dados recomendadas">

**Para estruturar seus dados de origem ao otimizar a ingestão e maximizar os resultados na DCP:**

1. Certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-de-dados-de-origem">cumprir os requisitos de formatação dos dados de origem</Anchor>.
2. Para obter os melhores resultados, **estruture os dados de identidade como uma linha por usuário e inclua todos os identificadores disponíveis para esse usuário.** Consulte as [estruturas de identificadores recomendadas](#estruturas-de-identificadores-recomendadas).
   * Se os usuários tiverem vários endereços de e-mail ou números de telefone, utilize formatos baseados em arrays (como Parquet, BigQuery ou Snowflake).
3. Verifique se as [diretrizes de hashing](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner) estão sendo seguidas.
4. Para conjuntos de dados transacionais (e outros tipos de dados, quando aplicável), **utilize a ferramenta de visualização de dados da DCP para criar um subconjunto dos seus dados** voltado para negócios, com privacidade preservada e otimizado para colaboração, e compartilhá-lo no lugar das tabelas brutas. [Por que as visualizações de dados são recomendadas](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended).

Embora outras estruturas possam ser usadas, talvez elas não sejam ideais para aproveitar a DCP ao máximo. Veja as [estruturas de dados que não são recomendadas](#data-structures-that-arent-recommended).

<div id="recommended-identifier-structures" />

#### Estruturas de identificadores recomendadas

Para maximizar as taxas de correspondência, recomenda-se enviar os dados de identidade no nível do usuário em uma única linha por usuário, sempre que possível, e incluir todos os identificadores disponíveis em uma estrutura que represente com precisão como os usuários são identificados.

**Opção 1: Uma linha por usuário e um valor por tipo de identificador**

**Simples e eficaz.**

Use quando cada usuário tiver, no máximo, um e-mail com hash, um número de telefone com hash, etc.

**Exemplo**

| ID do usuário | E-mails com hash | Números de telefone com hash |
| --- | --- | --- |
| 123 | 5d41402 | 152d234b70 |
| 456 | 7d793037 |  |
| 789 |  | 0e6e5414 |

**Por que é recomendada**

* Mais simples de preparar e ingerir
* Fácil de validar e solucionar problemas
* Alta performance de correspondência quando os identificadores estão completos e consistentes (tanto para correspondência com conjuntos de dados de colaboradores quanto para correspondência com parceiros de mídia na ativação)

**Melhor opção**

* Ideal para uploads baseados em CSV
* Funciona muito bem no Parquet / BigQuery / Snowflake

**Opção 2: Arrays (listas) de identificadores para campos de múltiplos valor**

**Ideal para precisão quando os usuários têm vários e-mails e números de telefone.**

Use quando um usuário tiver múltiplos valores do mesmo tipo de identificador, como:

* Vários e-mails com hash
* Vários números de telefone com hash

Essa estrutura deve ser representada como **arrays nativos**.

**Exemplo**

| ID do usuário | E-mails com hash | Números de telefone com hash | MAID |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**Por que é a melhor opção**

* Reflete como os dados de identidade costumam ser armazenados internamente
* Não é preciso adivinhar quantas “colunas de e-mail” podem ser necessárias
* Evita alterações de esquema em andamento
* Maximiza o potencial de correspondência (para conjuntos de dados dos colaboradores e para correspondência com parceiros de mídia na ativação) ao permitir vários identificadores por usuário

**Melhor opção**

* Parquet (S3/GCS)
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="Lista de verificação prática para estruturação de dados">

<div id="identity-user-level-dataset-checklist" />

#### Lista de verificação do conjunto de dados de identidade (nível do usuário)

* Uma linha representa um usuário.
* Inclua todos os identificadores disponíveis (e-mails com hash, números de telefone com hash, MAID, etc.).
* Se existirem múltiplos valores (por exemplo, vários e-mails), use arrays nativos sempre que possível.
* Evite listas nas células, “email\_1/email\_2/email\_3" e estruturas de identidade com várias linhas.

<div id="transactional-events-dataset-checklist" />

#### Lista de verificação do conjunto de dados transacionais (eventos)

* Mantenha as linhas de evento/transação inalteradas. Veja [exemplos de dados transacionais](#appendix-a-transactional-data-examples)
* Use as [visualizações de dados](#appendix-c-why-dataviews-matter-and-recommended) para criar resumos no nível do usuário prontos para colaboração, quando apropriado.

<div id="data-views-checklist" />

#### Lista de verificação de visualizações de dados

* Crie [visualizações de dados](#appendix-c-why-dataviews-matter-and-recommended) voltadas para negócios (prontas para audiências, resumidas e padronizadas).
* Compartilhe visualizações de dados em vez de tabelas brutas com dados confidenciais sempre que possível.
* Minimize os campos compartilhados, limitando-os apenas ao necessário (para proteção da privacidade e dos negócios).
* Considere o uso de dados agregados para reduzir o acesso a dados confidenciais e melhorar a eficiência.

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="Formatos de ingestão e serviços em nuvem compatíveis">

A DCP permite a ingestão através de vários serviços em nuvem, como:

* AWS S3
* Google Cloud Storage
* BigQuery
* Snowflake

<div id="format-guidance" />

#### Diretrizes de formato

* Use **CSV (separado por vírgula)** quando cada usuário tiver **um valor por tipo de identificador** (um e-mail, um número de telefone, etc.).
* Quando os usuários podem ter **múltiplos valores** do mesmo tipo de identificador (por exemplo, vários e-mails com hash), prefira **formatos compatíveis com arrays**:
  * Parquet (comum em big data)
  * BigQuery (os arrays são incorporados)
  * Snowflake (os arrays são incorporados)

**Atenção:**

* “Arrays” significa apenas “uma lista de valores”.
* O Parquet e os arrays no BigQuery/Snowflake são padrão, e a maioria das equipes de dados oferece suporte nativo.

Veja os [assets de exemplo específicos do conector (AWS S3, GCS, BigQuery e Snowflake](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)).

<div id="data-structures-that-arent-recommended" />

<Accordion title="Estruturas de dados que não são recomendadas">

Certos tipos de estruturação de dados são ideais para a ingestão na DCP, mas outros não. Abaixo está uma lista de estruturas de dados que **não são recomendadas**:

<div id="avoid-multiple-columns-for-the-same-identifier-type" />

#### Evite várias colunas para o mesmo tipo de identificador

Exemplos como “e-mail primário/secundário/terciário” devem ser evitados.

**Exemplos a evitar**

| ID do usuário | E-mail (hash 1) | E-mail (hash 2) | E-mail (hash 3) |
| --- | --- | --- | --- |
| 123 | a1b2 | c3d4 |  |
| 456 | z9y8 |  |  |

**Por que evitar**

* O número de valores por usuário é imprevisível
* Problemas com excesso de colunas manutenção de esquemas

<div id="avoid-lists-inside-a-single-cell-free-text" />

#### Evite listas dentro de uma única célula (texto livre)

Mesmo que pareça conveniente, está sujeito a erros.

**Exemplos a evitar**

| ID do usuário | E-mails com hash (texto) |
| --- | --- |
| 123 | a1b2 · c3d4 · e5f6 |

**Por que evitar**

* Não é um verdadeiro tipo de array
* Problemas de formatação/escape são comuns
* Pequenas inconsistências podem interromper a ingestão

<div id="avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table" />

#### Evite várias linhas por usuário para identificadores (quando seu objetivo é uma tabela de identidade do usuário)

Mantenha uma única linha por usuário sempre que possível, sem distribuir os dados de identidade entre várias linhas.

**Exemplos a evitar**

| ID do usuário | Tipo de identificador | Valor do identificador |
| --- | --- | --- |
| 123 | hashed\_email | a1b2 |
| 123 | hashed\_email | c3d4 |

**Por que evitar**

* Requer processamento extra para reconstruir os usuários
* Maior risco de duplicatas e inconsistências
* Menos eficiente em escala

**Observação:** Várias linhas por usuário são normais para tabelas transacionais, mas não são ideais para a tabela de identidade (nível do usuário) utilizada para correspondência.

</Accordion>

</Accordion>

<div id="additional-information" />

## Informações adicionais

Esta secção fornece informações adicionais e aprofundadas sobre tópicos relevantes.

<div id="appendix-a-transactional-data-examples" />

<Accordion title="Exemplos de dados transacionais">

Os dados transacionais/eventos podem ter várias linhas por usuário:

| ID da transação | ID do usuário | Data da transação | Valor | Categoria |
| --- | --- | --- | --- | --- |
| t\_001 | 123 | 10/01/2025 | 120.00 | Mercado |
| t\_002 | 123 | 10/15/2025 | 45.00 | Farmácia |
| t\_003 | 456 | 10/20/2025 | 300.00 | Eletrônica |

**Recomendado**

* Ingestão de dados transacionais em sua estrutura natural
* Use a ferramenta de visualização de dados para produzir uma visualização no nível do usuário pronta para colaboração (por exemplo, gasto nos últimos 30 dias, afinidade de categoria e resumos de recência/frequência)

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="Assets de exemplos específicos do conector (AWS S3, GCS, BigQuery e Snowflake)">

<div id="what-does-arraylist-of-identifiers-mean" />

### O que significa “array/lista de identificadores”?

Às vezes, um único usuário pode ter mais do que um e-mail ou número de telefone (por exemplo, um pessoal e outro profissional). Em vez de adicionar colunas extras ou usar campos de texto pouco estruturados, representamos esses dados como uma lista de valores.

| ID do usuário | E-mails com hash (lista) |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

<div id="1-aws-s3-and-gcs-connector-parquet" />

### 1. Conector do AWS S3 e do GCS (Parquet)

**O que a amostra de identidade deve conter (esquema)**

| Campo | Tipo | Observações |
| --- | --- | --- |
| user\_id | string | Uma linha por usuário |
| hashed\_emails | array de strings | Identificador de múltiplos valores (recomendado) |
| hashed\_phones | array de strings | Identificador de múltiplos valores (recomendado) |
| maid | string | Identificador adicional (opcional) |

O Parquet oferece suporte nativo a listas; recomendado quando os usuários têm vários e-mails/números de telefone.

<div id="2-bigquery-connector-table-preview-and-schema-screenshot" />

### 2. Conector do BigQuery (visualização da tabela e captura de tela do esquema)

**Exemplo de esquema de identidade (BigQuery)**

| Campo | Tipo | Modo |
| --- | --- | --- |
| user\_id | STRING | NULLABLE |
| hashed\_emails | STRING | REPEATED (ARRAY) |
| hashed\_phones | STRING | REPEATED (ARRAY) |
| maid | STRING | NULLABLE |

Os arrays são nativos no BigQuery (campos REPEATED). Essa é a abordagem recomendada quando existem vários e-mails/números de telefone.

<div id="3-snowflake-connector-table-preview-and-schema-screenshot" />

### 3. Conector do Snowflake (visualização da tabela e captura de tela do esquema)

**Exemplo de esquema de identidade (Snowflake)**

| Campo | Tipo | Observações |
| --- | --- | --- |
| USER\_ID | VARCHAR | Uma linha por usuário |
| HASHED\_EMAILS | ARRAY | Identificador de múltiplos valores |
| TELEFONES\_COM\_HASH | ARRAY | Identificador de múltiplos valores |
| MAID | VARCHAR | Opcional |

O Snowflake oferece suporte a campos semelhantes a listas (arrays). Essa abordagem é preferível à criação de colunas email\_1/email\_2/email\_3.

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="Por que as visualizações de dados são recomendadas">

As <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-customized-data-views">visualizações de dados</Anchor> são subconjuntos personalizados das suas fontes de dados existentes que você pode criar sem alterar o conjunto de dados original. Com elas, você pode realizar funções que modificam, refinam e resumem os dados para que você possa compartilhar apenas o que for relevante nas colaborações, mantendo os dados compartilhados claros e focados e todos os demais dados privados e seguros. Por que usar as visualizações de dados em colaborações?

<div id="are-business-oriented-and-easier-to-collaborate-with" />

#### São voltadas para negócios e facilitam a colaboração

* As visualizações de dados permitem que você apresente os dados em uma estrutura organizada e voltada para negócios (por exemplo, “Visualização de identidade do cliente”, “Visualização de audiência elegível”, “Visualização de resumo de compras”) em vez de registros brutos ou esquemas transacionais complexos.
* Elas ajudam a padronizar definições (por exemplo, “cliente ativo”, “gasto total dos últimos 30 dias”) para que ambos os lados estejam alinhados, com a mesma lógica.

<div id="are-more-privacy-safe-by-design" />

#### São projetadas para oferecer maior proteção à privacidade

* As visualizações de dados aceitam a minimização de dados: você pode compartilhar apenas os campos e linhas necessários para a colaboração, em vez de expor conjuntos de dados brutos completos.
* Elas reduzem os riscos à privacidade, permitindo que você:
  * Exclua atributos desnecessários
  * Limite a granularidade (por exemplo, compartilhe métricas agregadas em vez de transações no nível da linha)
  * Compartilhe apenas os identificadores necessários para a correspondência (e não outras colunas confidenciais)

<div id="protect-sensitive-business-data" />

#### Proteja dados confidenciais de negócios

* As tabelas transacionais brutas podem conter sinais altamente confidenciais de negócios (por exemplo, comportamento de compras detalhado, padrões de preços, relacionamentos/relações comerciais e IDs internos).
* As visualizações de dados permitem que você compartilhe apenas o que é necessário para a colaboração:
  * Exemplo: compartilhe dados agregados por categoria em vez de detalhes no nível do item
  * Exemplo: compartilhe faixas de gastos ou métricas resumidas em vez dos valores exatos de cada item
* Isso reduz o risco de revelar acidentalmente informações competitivas ou proprietárias.

<div id="can-make-your-data-more-cost-effective-and-performant" />

#### Pode tornar seus dados mais econômicos e com uma performance melhor

As visualizações de dados podem ser estruturadas de uma maneira mais leve e eficiente, geralmente reduzindo:

* Dados verificados
* Tempo de processamento
* Custos de processamento

Estruturar previamente uma visualização pronta para colaboração (especialmente visualizações agregadas) pode tornar a colaboração mais rápida e previsível do ponto de vista operacional.

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="Upload de múltiplos IDs/keys e comportamento de correspondência por plataforma">

**Upload de identificadores da DCP**

| Parceiro/plataforma | Tipos de identificador compatíveis | Modo de upload | Comportamento do upload | Prioridade do identificador (para parceiros de tipo único) |
| --- | --- | --- | --- | --- |
| Meta | E-mail, número de telefone, IDFA, GAID, ID Android, nome, sobrenome, DOB, cidade, estado, CEP e país | Todos os tipos compatíveis | Upload de todos os tipos de identificadores compatíveis | N/A - upload de tudo |
| Google | E-mail, número de telefone, IDFA, GAID, Android ID e Customer ID | Tipo único | Upload de um tipo de identificador por audiência | 1. E-mail 2. Número de telefone 3. IDs mobile 4. Customer ID |
| Tiktok | E-mail, número de telefone, IDFA, GAID e Android ID | Todos os tipos compatíveis | Upload de todos os tipos de identificadores compatíveis | N/A - upload de tudo |
| Pinterest | E-mail, número de telefone, IDFA e GAID | Tipo único | Upload de um tipo de identificador por audiência | 1. E-mail 2. Número de telefone 3. IDs mobile |
| Infillion | E-mail, número de telefone, IDFA, GAID e MM-UUID | Todos os tipos compatíveis | Upload de todos os tipos compatíveis agrupados em até 3 arquivos | N/A - upload de tudo |
| TheTradeDesk | E-mail e número de telefone | Tipo único | Upload de um tipo de identificador por audiência | 1. E-mail 2. Número de telefone Mobile IDs |
| Data Locker da AppsFlyer | Identificadores disponíveis | Todos os tipos combinados | Fornece todos os identificadores em um único arquivo combinado | N/A - entrega tudo |

| Plataforma | É possível enviar vários IDs por usuário? | É possível fazer a correspondência com qualquer um deles? | É possível combinar vários IDs? | Modelo de correspondência (prático) | Observações |
| --- | --- | --- | --- | --- | --- |
| Meta | Sim | Sim | Sim | Determinístico, qualquer ID / combinação | E-mail, número de telefone, MAID, fbp/fbc: todos avaliados; comportamento mais robusto de correspondência |
| Google | Sim | Com limitação | Não | Determinístico e priorizado | Um ID já identifica o usuário; os IDs não são combinados para formar uma correspondência |
| Tiktok | Sim | Sim | Sim | Determinístico, qualquer ID / combinação | Muito semelhante à Meta; ttclid: alta eficácia para eventos |
| Pinterest | Sim | Parcial | Com limitação | Determinístico e centrado no ID | Principalmente e-mail + MAID; reforço limitado entre IDs |
| The Trade Desk (TTD) | Sim | Via grafo de IDs | Sim (via grafo) | Determinístico via grafo de identidade | UID2 + MAID+ cookies identificados por meio de grafos EUID/UID2 |
| Infillion | Sim | Via grafo de IDs | Sim (via grafo) | Determinístico via grafo do parceiro | Depende do OmniID/da resolução de identidade do parceiro |

**Principais considerações para o planejamento da ativação**

* **Meta e TikTok**
  * Envie tudo o que tiver
  * Verdadeiro comportamento de “qualquer ID”
  * As melhores plataformas para ativação em clean room com múltiplos identificadores
* **Google**
  * Envie vários IDs para cobertura
  * Não espere reforço entre diferentes IDs
  * O domínio do e-mail/número de telefone é real
* **TTD e infillion**
  * A correspondência de qualidade depende mais da participação no grafo de identidade
  * A cobertura de UID2/OmniID é mais importante do que a quantidade bruta de identificadores
* **Pinterest**
  * Comportamento mais semelhante ao do Google do que ao da Meta
  * Benefício limitado além do e-mail + MAID

**Resumo**

* Apenas Meta e TikTok permitem correspondência nativa por qualquer ID
* O Google é determinístico, mas a correspondência é feita por um único ID
* Plataformas web abertas fazem a correspondência por meio de grafos de identidade, e não de IDs brutos

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="Diretrizes para formatação de dados com hash dos parceiros de mídia">

**Regras de normalização universais:**  
Antes de aplicar hash aos dados, quase todas as plataformas exigem as seguintes etapas de normalização para garantir a precisão da correspondência:

* **Texto:** Converta para letras minúsculas e remova todos os espaços em branco no início e no final.
* **Número de telefone:** Converta para o formato E.164 (por exemplo, +15551234567)
* **Hashing:** SHA-256 é o padrão, embora algumas plataformas aceitem MD5 ou SHA-1.

| Parceiro de mídia | Diretrizes para e-mails | Diretrizes para números de telefone | Diretrizes para Mobile IDs (MAID) | Nuances específicas da plataforma e lógica de correspondência | Referências relevantes |
| --- | --- | --- | --- | --- | --- |
| Google anúncios / DV360 | Formato: Letras minúsculas, sem espaços em branco. Inclua o domínio. Regra do Gmail: para @gmail.com / @googlemail.com, remova os pontos (.) antes do “@” e os sufixos depois de (+). Hashing: SHA-256 (codificação hexagonal). | Formato: E.164 (exemplo: +16505551212). Deve incluir o código do país. Hashing: SHA-256. | Formato: IDFA (iOS) ou GAID (Android). Hashing: não use hash. | Prioridade de correspondência: determinística e priorizada (1. E-mail 2. Número de telefone 3. IDs mobile). Não combina vários IDs para formar uma correspondência (identificação por um único ID). DV360 PAIR: O DV360 também oferece suporte ao protocolo PAIR para a correspondência segura entre publishers e anunciantes. | <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/remarketing/audience-segments/customer-match/get-started">Comece a usar o Customer Match (Google Ads API)</Anchor> |
| Meta (Facebook / Instagram) | Formato: Letras minúsculas, sem espaços em branco. Hashing: SHA-256 obrigatório.<br /><br />**Observação:** A Meta não remove pontos dos endereços de e-mail como parte da sua normalização para hashing. Antes da aplicação de hash para a Meta, você deve converter para letras minúsculas e remover os espaços em branco no início e no final. Enviar um e-mail com hash sem pontos (“e-mail com hash (sem pontos)” no mapeamento da fonte na DCP) não corresponderá ao próprio hash da Meta e resultará em taxas de correspondência reduzidas para usuários do domínio de e-mail. Essa variante de identificador destina-se a parceiros que necessitam da remoção de pontos (por exemplo, Google Ads) e não deve ser utilizada para ativações do Facebook/Meta. | Formato: Remova símbolos, letras e zeros à esquerda. Inclua o código do país (exemplo: 16505551212). Hashing: SHA-256. | Formato: IDFA ou GAID. Hashing: não use hash. Letras minúsculas, com hífens. | Lógica de correspondência: Usa a lógica “qualquer um deles”; combina vários IDs (e-mail, número de telefone, MAID, etc.) para identificar um usuário, reforçando a correspondência entre diferentes IDs.<br /><br />CAPI: Requer client\_ip\_address e client\_user\_agent sem hash para a correspondência no navegador. | <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters/">Parâmetros de informações do cliente - Conversions API</Anchor> |
| Tiktok | Formato: Letras minúsculas, sem espaços. Hashing: SHA-256. | Formato: E.164 (+[código do país][número]). Também é aceito sem o sinal de mais. Hashing: SHA-256. | Formato: GAID (Android) ou IDFA (iOS). Letras: Todos maiúsculas ou todas minúsculas. Hashing: SHA-256 ou MD5. | Lógica de correspondência: Semelhante à Meta, usa a lógica de correspondência determinística “qualquer um deles”, onde qualquer ID válido é suficiente.<br /><br />Tamanho da audiência: Requer um mínimo de 1.000 usuários correspondentes para ativar uma audiência personalizada. | <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-create-a-custom-audience-with-a-customer-file">Como criar uma audiência personalizada com um arquivo de cliente</Anchor> |
| The Trade Desk (UID2) | Formato: mesma “regra do Gmail” do Google (remover pontos e sinais de mais). Codificação: bytes brutos codificados em Base64 (44 caracteres). | Formato: E.164. Hashing: SHA-256. Codificação: bytes brutos codificados em Base64. | Formato: AAID (minúsculas) / IDFA (maiúsculas). Hashing: SHA-256, MD5 ou SHA-1. | Lógica de correspondência: determinística via grafo de identidade. A correspondência depende da participação no grafo, e não da cobertura de IDs brutos.<br /><br />Nuance crítica: Os bytes brutos do hash devem ser codificados em Base64. A codificação da string hexadecimal resultará em erro. |  |
| Pinterest | Formato: deve incluir “@”. Hashing: SHA-256, MD5 ou SHA-1. | Formato: E.164. Remova caracteres especiais (espaços e hífens). Hashing: SHA-256, MD5 ou SHA-1. | Formato: IDFA ou GAID. Hashing: SHA-256, MD5 ou SHA-1. | Lógica de correspondência: "Centrada no ID". A correspondência é determinada principalmente por e-mail e MAID. O benefício de fornecer outros IDs é limitado, já que o reforço entre IDs é menor em comparação com a Meta. Comportamento do upload: upload de um tipo de identificador por audiência. | Diretrizes para ingestão e estruturação de dados da DCP |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=sobre-a-prepara%C3%A7%C3%A3o-de-dados h_01KFX4HVTT50TZMY2YF37B1C4R=sobre-a-prepara%C3%A7%C3%A3o-de-dados data-types=compreender-os-tipos-de-dados h_01KFX4HVTTAMFEGJQEYXXWG9PT=compreender-os-tipos-de-dados data-ingestion-recommendations=diretrizes-para-estrutura%C3%A7%C3%A3o-de-dados h_01KFX4HVTT2Q2EV4GAC6M8R4A2=diretrizes-para-estrutura%C3%A7%C3%A3o-de-dados h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines recommended-identifier-structures=estruturas-de-identificadores-recomendadas h_01KFXB0KEF59QCYET0R8XNH84D=estruturas-de-identificadores-recomendadas h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=lista-de-verifica%C3%A7%C3%A3o-do-conjunto-de-dados-de-identidade-n%C3%ADvel-do-usu%C3%A1rio h_01KFZNGRC0XX7YYBYT09M49YFA=lista-de-verifica%C3%A7%C3%A3o-do-conjunto-de-dados-de-identidade-n%C3%ADvel-do-usu%C3%A1rio transactional-events-dataset-checklist=lista-de-verifica%C3%A7%C3%A3o-do-conjunto-de-dados-transacionais-eventos h_01KFZNJ7YKCT1YFYE400CNY6SP=lista-de-verifica%C3%A7%C3%A3o-do-conjunto-de-dados-transacionais-eventos dataviews-checklist=lista-de-verifica%C3%A7%C3%A3o-de-visualiza%C3%A7%C3%B5es-de-dados h_01KFZNKBXJQ4S89YHCGKP8J5F4=lista-de-verifica%C3%A7%C3%A3o-de-visualiza%C3%A7%C3%B5es-de-dados h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats format-guidance=diretrizes-de-formato h_01KFX6XSNACVR9JWZWZW12F6C4=diretrizes-de-formato h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended avoid-multiple-columns-for-the-same-identifier-type=evite-v%C3%A1rias-colunas-para-o-mesmo-tipo-de-identificador h_01KFX72MNYH1CSKWZAGZ2XETXY=evite-v%C3%A1rias-colunas-para-o-mesmo-tipo-de-identificador avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=evite-listas-dentro-de-uma-%C3%BAnica-c%C3%A9lula-texto-livre h_01KFX70V3BHNK93SKCRGGDVY3W=evite-listas-dentro-de-uma-%C3%BAnica-c%C3%A9lula-texto-livre avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table=evite-v%C3%A1rias-linhas-por-usu%C3%A1rio-para-identificadores-quando-seu-objetivo-%C3%A9-uma-tabela-de-identidade-do-usu%C3%A1rio h_01KFX70V3BJE2PR7132QE27C4V=evite-v%C3%A1rias-linhas-por-usu%C3%A1rio-para-identificadores-quando-seu-objetivo-%C3%A9-uma-tabela-de-identidade-do-usu%C3%A1rio additional-information=informa%C3%A7%C3%B5es-adicionais h_01KFZJ2PNKB4X962VKCKSYVFFB=informa%C3%A7%C3%B5es-adicionais h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=o-que-significa-arraylista-de-identificadores h_01KFX4HVTVPHZQFNRWDH9VCEZQ=o-que-significa-arraylista-de-identificadores 1-aws-s3-and-gcs-connector-parquet=1-conector-do-aws-s3-e-do-gcs-parquet h_01KFX4HVTVNQZY9A8AGEBBHF6Y=1-conector-do-aws-s3-e-do-gcs-parquet 2-bigquery-connector-table-preview-and-schema-screenshot=2-conector-do-bigquery-visualiza%C3%A7%C3%A3o-da-tabela-e-captura-de-tela-do-esquema h_01KFX4HVTVCMB0H1B76TCK36SF=2-conector-do-bigquery-visualiza%C3%A7%C3%A3o-da-tabela-e-captura-de-tela-do-esquema 3-snowflake-connector-table-preview-and-schema-screenshot=3-conector-do-snowflake-visualiza%C3%A7%C3%A3o-da-tabela-e-captura-de-tela-do-esquema h_01KFX4HVTVN9MSWFB7ZRT9MVCG=3-conector-do-snowflake-visualiza%C3%A7%C3%A3o-da-tabela-e-captura-de-tela-do-esquema h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=s%C3%A3o-voltadas-para-neg%C3%B3cios-e-facilitam-a-colabora%C3%A7%C3%A3o h_01KFX4HVTV43QFEQARSB2N49Z5=s%C3%A3o-voltadas-para-neg%C3%B3cios-e-facilitam-a-colabora%C3%A7%C3%A3o are-more-privacysafe-by-design=s%C3%A3o-projetadas-para-oferecer-maior-prote%C3%A7%C3%A3o-%C3%A0-privacidade h_01KFX4HVTVJA8Q3FTQB8A94MA1=s%C3%A3o-projetadas-para-oferecer-maior-prote%C3%A7%C3%A3o-%C3%A0-privacidade protect-sensitive-business-data=proteja-dados-confidenciais-de-neg%C3%B3cios h_01KFX4HVTVF8A0PM90FA6XA0V5=proteja-dados-confidenciais-de-neg%C3%B3cios can-make-your-data-more-costeffective-and-performant=pode-tornar-seus-dados-mais-econ%C3%B4micos-e-com-uma-performance-melhor h_01KFX4HVTVJ70HV606Y8KE4JD1=pode-tornar-seus-dados-mais-econ%C3%B4micos-e-com-uma-performance-melhor h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />
