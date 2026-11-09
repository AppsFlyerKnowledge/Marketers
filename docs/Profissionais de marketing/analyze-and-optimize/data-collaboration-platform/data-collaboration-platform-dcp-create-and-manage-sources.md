---
title: Plataforma de colaboração de dados (DCP) - Criar e gerenciar fontes
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-09-23T00:03:18Z'
  id: 24740010687249
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/24740010687249
---
> **At a glance:** Crie e gerencie fontes para compartilhar com segurança seus dados first-party com outros colaboradores.

<div id="about-dcp-sources" />

## Sobre as fontes da DCP

Na plataforma de colaboração de dados (DCP), uma fonte é um conjunto de dados, normalmente carregado para a AppsFlyer a partir do seu armazenamento em nuvem. Essas fontes formam a base de qualquer colaboração, fornecendo os dados que seus colaboradores podem usar para criação e ativação de audiências. Este artigo contém tudo o que você precisa saber sobre como criar e gerenciar suas fontes, incluindo:

* [Requisitos de dados de origem](#requisitos-de-dados-de-origem)
* [Criando fontes](#criar-fonte)
* [Gerenciando suas fontes](#gerenciar-suas-fontes)

<div id="source-data-requirements" />

## Requisitos de dados de origem

Recomenda-se <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">preparar os dados da sua fonte</Anchor> para maximizar as taxas de correspondência entre os conjuntos de dados dos colaboradores e otimizar os resultados da colaboração. Além disso, todas as fontes **devem atender aos seguintes requisitos**.

<Accordion title="Formato dos dados (relevante para todas as fontes)">

Os dados dentro das fontes devem atender a estes requisitos:

* **Data** (somente): aaaa-mm-dd (por exemplo, `2023-04-18`)
* **Data e hora:**
  * **Formato:** aaaa-MMM-dd hh:mm:ss (*por exemplo*, `2023-APR-18 15:30:35`)
  * **Fuso horário:** UTC
* **Números:** máximo 2 dígitos após a vírgula decimal
* **Comprimento da string:** máximo de 256
* **Limitações de caracteres**
  * **Para nomes de campo (cabeçalhos de coluna):** sem espaços ou caracteres especiais
  * **Todos os outros dados:** sem limitações (todos os caracteres são válidos)

</Accordion>

<Accordion title="Colunas da tabela (relevantes apenas para fontes em data warehouses)">

Além dos dados compartilhados para processamento, as tabelas de origem no BigQuery ou Snowflake devem incluir 2 colunas adicionais – uma para **data** e outra para **versão:**

* **Data:**
  * **Cabeçalho da coluna:** `dt`
  * **Tipo de coluna:** data
  * **Formato dos dados:** aaaa-mm-dd (*por exemplo*, `2023-04-18`)
  * **Adicional:** as tabelas do BigQuery devem ser <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">particionadas</Anchor> por esta coluna
* **Versão:**
  * **Cabeçalho da coluna:** `v`
  * **Tipo de coluna:** string
  * **Formato dos dados:** número (por exemplo, `1`, `2`, `3`, `10`)
  * **Importante!** Uma nova versão de um relatório é acionada cada vez que o DCR detecta um novo valor nesta coluna. Para garantir a integridade do seu relatório, certifique-se de preencher a tabela de origem com um conjunto completo de dados sempre que o valor da coluna for alterado.

</Accordion>

<Accordion title="Nome e formato do arquivo (relevante apenas para fontes em buckets de armazenamento em nuvem)">

Os arquivos de origem armazenados no Amazon S3 ou GCS devem atender a estes requisitos de nome e formato de arquivo:

* O nome do arquivo deve estar em conformidade com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura DCR</Anchor>
* Formato CSV ou GZIP
  * O arquivo subjacente à compressão GZIP deve ser um arquivo CSV.
* Número de arquivos de fonte de dados por <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">pasta de dados</Anchor>:
  * **CSV:** máximo 1
  * **GZIP:** no máximo 1 arquivo em uma única parte. Arquivos GZIP com várias partes são compatíveis quando nomeados da seguinte forma: `filename_part01.csv.gz`, `filename_part02.csv.gz`, etc.

</Accordion>

<div id="create-a-source" />

## Criar fonte

**Pré-requisito:** Antes de criar sua fonte, <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configure os serviços de nuvem</Anchor> que a AppsFlyer DCP usará para recuperar seus dados de fonte. Se essas conexões não estiverem configuradas, você será solicitado a fazer isso durante a criação da fonte.

**Para criar uma fonte na DCP, siga as etapas abaixo:**

<Accordion title="Etapa 1: Acessar fontes do DCP">

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Data Clean Room**.

   <Image align="center" alt="Clique em Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="644px" />
2. Clique em **+ Nova fonte** (na página principal ou na guia **Fontes**).

   <Image align="center" alt="sources empty state cropped.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="482px" />
3. Prossiga com as etapas do passo a passo de **Nova fonte** :

</Accordion>

<Accordion title="Etapa 2: Definir nome da fonte">

Insira o nome da fonte. Pode ser qualquer nome exclusivo que ajude você a identificar a fonte. Você também pode adicionar uma descrição opcional sobre a fonte para ajudar a identificar facilmente o que ela contém (por exemplo, "Todas as compras de 2025").

<div id="requirements-and-guidelines" />

#### Requisitos e diretrizes

* Certifique-se de que o **nome da fonte** seja exclusivo entre todas as outras fontes da sua conta. Caso contrário, você não poderá salvar a fonte.
* Ele não precisa corresponder ao nome do arquivo.
* Requisitos do nome da fonte:
  * Tamanho: 2-80 caracteres
  * Caracteres válidos:
    * letras `(A-Z, a-z)`
    * números `(0-9)`,  *não podem ser o primeiro caractere de um nome;*
    * Sublinhado `"_"`
  * Caracteres inválidos:
    * espaços
    * todos os outros símbolos ou caracteres especiais

</Accordion>

<Accordion title="Etapa 3: Definir local da fonte">

**Para especificar a localização da fonte:**

1. Selecione a <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">conexão</Anchor> na qual a fonte será (ou foi) criada.
   * Se não houver conexões definidas em sua conta, a caixa de diálogo **Nova conexão** será aberta, solicitando que você crie uma. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections">estas instruções</Anchor> para criá-la.
   * Se você tiver conexões existentes, mas quiser usar uma nova, clique em **+ Nova conexão** e siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections">estas instruções</Anchor> para criá-la.
2. Continue com as instruções relevantes abaixo, com base em onde os dados da sua fonte estão localizados.

**Atenção:** Para melhor performance quando houver um grande volume de dados, um subconjunto dos seus dados poderá ser armazenado separadamente. Esses dados serão atualizados sempre que a fonte for atualizada e excluídos quando a fonte for excluída.

<div id="source-locations-in-bigquery" />

#### Locais de origem no BigQuery

**Para concluir a especificação do local de origem para origens do BigQuery:**

1. Selecione o conjunto de dados no qual a tabela de origem está localizada.
2. Selecione a tabela na qual os dados de origem estão localizados.

As listas nas quais você faz essas seleções contêm os conjuntos de dados e tabelas disponíveis, respectivamente, no projeto do BigQuery que você especificou ao criar a conexão.

<div id="source-locations-in-snowflake" />

#### Locais de origem no Snowflake

**Para concluir a especificação do local de origem para fontes do Snowflake:**

1. Selecione o compartilhamento que contém os dados de origem.
2. Selecione o esquema no qual a tabela de origem está localizada.
3. Selecione a tabela na qual os dados de origem estão localizados.

As listas das quais você faz essas seleções contêm os compartilhamentos, esquemas e tabelas, respectivamente, na conta do Snowflake que você especificou ao criar a conexão.

<div id="source-locations-in-cloud-storage-buckets" />

#### Locais de origem em buckets de armazenamento em nuvem

Os locais de origem no Amazon S3 ou GCS consistem no bucket de armazenamento em nuvem especificado pela conexão e no caminho da pasta subjacente do qual o DCR lê o arquivo de origem sempre que ele é atualizado.

Depois de especificar a conexão, a AppsFlyer pode gerar automaticamente o caminho da pasta subjacente necessária como parte do processo de criação da fonte.

* Permitir que a AppsFlyer gere as pastas facilita o processo. No entanto, você pode optar por criá-las manualmente, de acordo com as instruções <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">detalhadas aqui</Anchor>.

Se a AppsFlyer gera as pastas, a única informação adicional necessária é o nome que você deseja dar à **pasta fonte.** (Esta é a pasta de nível superior na qual você atualiza a fonte cada vez que deseja utilizá-la para executar uma nova versão do relatório) Você também pode indicar se deseja que a pasta fonte seja criada abaixo de uma pasta principal – frequentemente chamada de **entrada**. Você também pode indicar se deseja que a pasta da fonte seja criada em uma pasta principal – geralmente chamada de **input.**

**Para concluir a especificação de um local de origem em um bucket de armazenamento em nuvem, insira o nome da pasta de origem.**

* Por padrão, o nome da pasta fonte exibida:
  * É baseado no [nome que você deu à fonte](#h_01K1ZHNZEQWRP7ZBK7XJP5F9HA). Você pode alterar o nome da pasta para atender às suas necessidades, desde que ele esteja em conformidade com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura do DCR</Anchor>.
  * Indica que será gerado dentro de uma pasta principal denominada **entrada.** Esta pasta serve como pasta principal para todas as fontes que você carrega para o DCR.
    * A pasta **input** não é necessária, e você pode removê-la ou dar a ela um nome diferente, desde que esteja em conformidade com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura do DCR</Anchor>.
    * Embora esta pasta não seja necessária, ter uma pasta **entrada** (ou uma pasta equivalente com um nome diferente) é considerado uma boa prática. É ainda mais recomendado quando você estiver usando o mesmo bucket de armazenamento em nuvem para carregar arquivos de dados (entrada) e receber relatórios (saída).

<div id="important" />

> 🚧 **Importante!**
>
> Se você criou manualmente o caminho da pasta, verifique se a conexão e o caminho inseridos na seção **Local de origem** correspondem ao caminho criado manualmente.


<div id="source-location-as-local-files" />

#### Local da fonte como arquivos locais

Você também pode fazer upload de dados da fonte usando um arquivo local. No entanto, **é altamente recomendável definir um serviço de nuvem como local da fonte** (fundamental para conjuntos de dados maiores e atualizações automáticas). Um arquivo local é usado principalmente para fins de teste e para você se familiarizar com as funcionalidades da plataforma.

**Para fazer upload de dados da fonte usando um arquivo local:**

Ao selecionar o local da fonte, clique em **Sistema de arquivos local** e em **Avançar**, o que adiciona a opção de fazer upload de arquivos locais do seu dispositivo.

<Image align="center" alt="Selecionar Sistema de arquivos local.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

<div id="note" />

> 📘 **Importante!**
>
> * Tipos de arquivo compatíveis: arquivos .CSV e .GZ (tamanho máximo de 5 GB).
> * Os dados enviados a partir de um arquivo local serão salvos por 180 dias.
> * As atualizações devem ser feitas manualmente.

</Accordion>

<Accordion title="4. Definir método de atualização da fonte">

Ao configurar uma fonte na Plataforma de colaboração de dados (DCP), você deve escolher como deseja que as atualizações dessa fonte sejam tratadas. A DCP oferece dois métodos de sincronização: **Snapshot** e **Append**. Cada método atende a diferentes casos de uso e fluxos de dados:

* **Snapshot** - Esse método faz upload do conjunto de dados completo sempre que a fonte é atualizada, substituindo totalmente o conjunto de dados antigo pelo novo a cada vez. Escolha esse método somente se os uploads do seu arquivo sempre contiverem o conjunto de dados completo e atualizado.
* **Acrescentar** - Esse método faz upload somente de dados novos ou alterados, não do conjunto de dados completo. Os conjuntos de dados antigos não são removidos nem atualizados. É ideal para uploads recorrentes, como relatórios diários ou semanais. Os benefícios incluem uploads menores (o que pode resultar em custos mais baixos de armazenamento em nuvem), performance de upload de dados mais rápida, gerenciamento de registros mais fácil e muito mais.

<Image align="center" alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

<div id="important-1" />

> 🚧 **Importante!**
>
> Determine qual método é o melhor antes de fazer a seleção. Depois que uma opção é selecionada e você clica em **Gerar pastas**, um caminho de arquivo, junto com instruções para processar uploads de dados, é criado no serviço de nuvem selecionado. Para evitar duplicações de pastas e erros, você pode **alterar o método de sincronização apenas uma vez** após a seleção inicial.


<div id="snapshot-upload-requirements" />

#### Requisitos para upload de Snapshot

Use esse método para fazer upload de um arquivo completo e autônomo que substitui totalmente o conjunto de dados anterior sempre que a fonte é atualizada.

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**Serviços de nuvem compatíveis**

* Amazon S3
* Google Cloud Storage (GCS)
* BigQuery
* Snowflake

**<span id="h_01K2A7MAWTCYF3VAWJRRRJFNN5"></span>Siga estas diretrizes para o método de atualização Snapshot:**

1. **Pasta path da fonte**

   Quando você registra uma fonte de armazenamento em nuvem na DCP, um caminho raiz (por exemplo, `input/my_source_folder/`) é definido para essa fonte. Cada vez que você atualiza o conjunto de dados, faz upload de um **snapshot completo** — um arquivo que contém todas as linhas atuais — para essa pasta. Isso garante que a DCP sempre processe a visualização mais atualizada e completa dos dados.
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**Upload de arquivos de snapshot completos**

| Diretriz | Por que isso é importante? | Como cumprir os requisitos |
| --- | --- | --- |
| **Conjunto de dados completo** | A DCP deve substituir totalmente o estado anterior | Gere uma exportação que inclua todos os registros, não apenas as alterações |
| **Pasta particionada por data (**`dt=`) | Permite filtrar por intervalo de datas & gerenciar a retenção | Coloque cada snapshot em `dt=YYYY‑MM‑DD/` |
| **Subpasta de versão (**`v=`) | Permite vários snapshots no mesmo dia | Primeiro upload em `v=1/`; as tentativas de repetição usam `v=2/`, `v=3/` etc. |
| `data/` **subpasta** | Organiza seus arquivos | Armazene arquivos Parquet/CSV/Avro nesta pasta |
| `_SUCCESS` **marcador** | Sinaliza o início da ingestão da DCP | Envie um arquivo vazio com o nome `_SUCCESS` dentro da pasta `v=` depois que todos os arquivos de dados forem carregados |
| **Tipo e tamanho de arquivo compatíveis** |  | <ul><li>Tipos de arquivo compatíveis: .csv ou .gz</li><li>Tamanho máximo do arquivo: 5 GB</li></ul> |

<div id="important-2" />

> 🚧 **Importante!**
>
> O arquivo de snapshot completo (BI-data.csv na captura de tela abaixo) deve ser colocado em:
>
> ```
> /v=1/data/
> ```
>
> Depois, quando o arquivo de dados for enviado, coloque um arquivo `_SUCCESS` vazio em:
>
> ```
> /v=1/
> ```

**Estrutura da pasta:**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/\n└ bucket ┘ └ tenant ┘ └ingestion┘ └source┘└snapshot date┘└ver┘└files┘
```

| Sequência de caracteres | A descrição | Propósito |
| --- | --- | --- |
| `af-dcr-xyz` | Bucket do S3 / GCS | Contêiner de nível superior para todos os dados da DCP |
| `abcd9876/` | ID do tenant / workspace | Mantém os dados de cada cliente isolados |
| `input/` | Área de ingestão | Onde os uploads brutos chegam antes do processamento |
| `source_name1/` | Nome do canal | Conjunto de dados lógico registrado na DCP |
| `dt=2025-mm-dd/` | Data do snapshot | Representa o estado completo do conjunto de dados naquele dia |
| `v=1/` | Versão (opcional) | Oferece suporte a novas tentativas ou snapshots adicionais |
| `agregados/` | Arquivos | Arquivos de snapshot em Parquet / CSV / Avro |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**Exemplo de uma estrutura de snapshot de dois dias:**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

Exemplo de como a estrutura de pastas deve ficar após fazer upload de um snapshot completo dos arquivos da fonte por 2 dias (e criar programaticamente as pastas de data/versão/dados e os arquivos \_SUCCESS): sua estrutura de bucket/pasta pode ficar assim:

<Image align="center" alt="Snapshot example bucket.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />


<div id="append-upload-requirements" />

#### Requisitos de upload de append

Use este método para fazer upload apenas dos dados que mudaram ou foram adicionados desde o upload anterior.

Por que usar Append?

* **Eficiência** – uploads menores
* **Integridade de dados** – preserva o histórico completo de alterações para análises de séries temporais
* **Compliance de privacidade** – simplifica a exclusão de registros & o gerenciamento de consentimento

**Serviços de nuvem compatíveis:** AWS S3 e Google Cloud Storage (GCS)  
**Atenção:** BigQuery e Snowflake não são compatíveis com o método Append e devem usar o método Snapshot.

**Siga estas diretrizes para o método de atualização Append:**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1. **Configuração da pasta de origem**

| Etapa | A descrição |
| --- | --- |
| **Crie / atribua um bucket** | Use um bucket S3 / GCS existente ou deixe que a AppsFlyer provisione um para você |
| **Defina o caminho raiz** | Um caminho com escopo de tenant (por exemplo, `s3://af‑dcr‑xyz/abcd1234/`) é configurado como o diretório input |
| **Segurança** | Conceda ao usuário do serviço permissão de gravação somente neste caminho |

<span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2. **Carregamento de arquivos append (delta)**

| Diretriz | Por que isso é importante? | Como estar em conformidade |
| --- | --- | --- |
| **Cadência de upload** | Mantém baixo o custo de transferência & a sobrecarga operacional | Faça upload diariamente ou agrupe pastas de 7 dias e faça upload semanalmente |
| **Uma pasta por dia** | Permite filtrar por data & evita a varredura de grandes lotes | Coloque o delta de cada dia em `dt=YYYY‑MM‑DD/` |
| **Nomes de arquivo exclusivos** | Evita substituições acidentais | Dê aos arquivos nomes exclusivos neste modelo:`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **Colunas obrigatórias** | Permite o rastreamento de alterações | O arquivo deve incluir:<ul><li>Uma coluna de data para associar registros a um período de referência.<ul><li>Uma coluna de versão para rastrear revisões dos dados.</li></ul></li></ul>**Atenção:** Arquivos sem essas colunas resultarão em um erro de carregamento na DCP. |

<span id="h_01K2A7MAWTV3FY1GZSXQFNX4JS"></span>**Estrutura da pasta:**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/\n└ bucket ┘ └ tenant ┘ └ ingestion ┘ └ fonte ┘ └ partição diária ┘
```

| Sequência de caracteres | Propósito |
| --- | --- |
| `af-dcr-xyz` | Bucket S3/GCS do cliente |
| `abcd1234/` | ID do tenant ou do workspace |
| `input/` | Uploads brutos aguardando ingestão |
| `source_name/` | Fonte lógica do DCP (por exemplo, CRM\_Events) |
| `dt=2025-08-10/` | Pasta de partição diária |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**Exemplo de estrutura de pasta delta semanal:**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**Guia prático: regra geral:**

| Requisito | Por quê | Exemplo |
| --- | --- | --- |
| **Lote semanal (opcional)** | Menos pushes, mesma granularidade | Faça upload de um lote contendo sete pastas `dt=` no mesmo nível |
| **Partições por dia** | Acelera as consultas & os filtros da interface | `s3://your‑bucket/fonte/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

**Conclusão principal:** Mesmo ao fazer upload semanalmente, sempre organize os dados em pastas `dt=YYYY‑MM‑DD` específicas de cada dia.

</Accordion>

<Accordion title="Etapa 5: Mapear campos da fonte">

Mapeie os campos da fonte para os campos da DCP, teste e salve os dados configurados:

1. [Carregue os campos da fonte](#1-carregar-seus-campos-de-fonte)
2. [Configure os campos da fonte](#2-configure-os-campos-de-fonte)
3. [Verifique a inclusão de usuários da UE](#3-verificar-inclusão-de-usuários-da-ue)
4. [Teste os dados da fonte](#4-testar-os-dados-da-fonte)
5. [Salve a fonte](#5-salve-a-fonte)

<div id="1-load-your-source-fields" />

#### 1. Carregar seus campos de fonte

Os campos da fonte são carregados automaticamente. Caso seja necessário fazer o carregamento manualmente, siga as instruções abaixo de acordo com o local da fonte:

**Fontes de data warehouses**

Para carregar campos de uma fonte localizada em um data warehouse (BigQuery ou Snowflake), clique em **Carregar campos da fonte**.

<div id="important-3" />

> 🚧 **Importante!**
>
> Se a tabela de fonte selecionada não incluir as [colunas de data e versão](#h_01HPKB2ERPJ5PVQ2QM5XCYZE0D) obrigatórias, você receberá um erro.

**Fontes de bucket de armazenamento em nuvem**

Para carregar campos de uma origem localizada em um bucket de armazenamento em nuvem (Amazon S3 ou GCS), você deve carregar um arquivo de origem de protótipo.

Para mapear os campos da fonte para os campos da DCP:

* Você pode carregar uma versão protótipo da fonte a partir de um arquivo local.
  * Se você selecionar esta opção, a AppsFlyer sempre cria automaticamente o caminho da pasta de fonte.

                                                                - or -

* Você pode fazer upload de uma versão protótipo do arquivo de fonte diretamente do cloud bucket conectado.
  * Antes de começar:
    * Permita que a AppsFlyer gere automaticamente a pasta na nuvem para o arquivo de fonte, ou
    * [Criar manualmente a pasta na nuvem para o arquivo de fonte](#h_01HPKB2ERVZ88MJ35JC66YDPAB)

**Para carregar seu protótipo de arquivo fonte, siga as instruções na aba correspondente abaixo:**

<Tabs>
<Tab title="Arquivo local">

1. Na seção **Mapear campos da fonte**, clique em **Carregar campos da fonte**.
2. Na janela que se abre, selecione **Carregar um arquivo local.**
3. Especifique o arquivo CSV ou GZIP que você deseja carregar e, em seguida, clique em OK.

</Tab>

<Tab title="Conexão (criação automática)">

**Para carregar o arquivo do cloud bucket conectado e permitir que a AppsFlyer gere a pasta na nuvem para o arquivo de fonte:**

1. Na seção **Mapear campos da fonte**, clique em **Carregar campos da fonte**.
2. Na janela que se abre, selecione **Carregar do cloud bucket.**
3. Clique no link **Gerar pastas**.
   * A AppsFlyer gera automaticamente a estrutura de pastas necessária e a pasta de fonte na nuvem (na conexão que você especificou, com o nome da pasta de fonte que você especificou).
4. Após a estrutura da pasta de fonte ter sido criada, uma mensagem de confirmação é exibida, incluindo um link para a pasta de fonte. Clique no link fornecido para carregar seu arquivo protótipo na pasta de fonte.
5. Quando o arquivo tiver terminado de carregar, clique em **OK.**

</Tab>

<Tab title="Conexão (criação manual)">

**Para carregar o arquivo fonte a partir de uma estrutura que você criou manualmente:**

1. Na seção **Mapear campos da fonte**, clique em **Carregar campos da fonte**.
2. Na janela que se abre, selecione **Carregar do cloud bucket.**
3. **NÃO** clique em **Gerar pastas.** Em vez disso, carregue o arquivo diretamente para [a pasta de fonte que você criou para ele](#h_01HPKB2ERVZ88MJ35JC66YDPAB).
4. Quando o arquivo tiver terminado de carregar, clique em **OK.**

</Tab>
</Tabs>

<div id="2-configure-the-source-fields" />

#### 2. Configure os campos de fonte

Depois de carregar os campos de fonte, cada campo de fonte (coluna) é apresentado com um campo DCP. Revise cada campo de fonte e mapeie-o para o campo DCP apropriado na lista suspensa ao lado dele. Considere o seguinte:

<div id="note-1" />

> 📘 **Importante!**
>
> * Quando ambas as parties compartilham seus dados de fonte, **pelo menos um campo deve ser definido como identificador** para permitir que os dados em nível de usuário correspondam entre as fontes correspondentes. Um identificador é um campo que identifica exclusivamente um usuário do aplicativo (por exemplo, CUID, AppsFlyer ID ou e-mail com hash).
> * Embora não seja obrigatório configurar cada um dos campos de fonte (colunas) carregados, isso é importante para categorização, interpretação eficaz dos dados, apoio à criação de audiências, sugestão de insights e facilitação eficaz de validações.

<div id="ai-assisted-field-type-detection" />

#### Detecção de tipo de campo assistida por IA

A DCP pode sugerir um campo da DCP para cada coluna da fonte usando IA, com base no nome da coluna.

**Para ativar a detecção assistida por IA:**

1. Na seção **Mapear campos da fonte**, procure o banner: "Quer ajuda para mapear os campos rapidamente?" **Ativar o AI Assistant da DCP**." Clique em **Ativar o AI Assistant da DCP**.
2. Quando seus campos forem carregados, clique em **Detectar tipos de campo automaticamente**. A DCP avalia o nome de cada coluna e sugere um campo da DCP para ela.
3. Revise cada sugestão antes de salvar. Você pode aceitar uma sugestão como está ou alterar o mapeamento manualmente, da mesma forma que editaria qualquer outro campo.

Cada campo fica em um destes estados:

* **Mapeado:** a IA encontrou uma única correspondência confiável. Revise e aceite ou altere manualmente.
* **Não foi possível mapear:** a IA não conseguiu determinar um campo. Mapeie-o manualmente ou deixe-o sem mapeamento.

<div id="limitations" />

#### Limitações

* **Limite de colunas:** a detecção por IA é compatível com até 100 colunas por fonte. Fontes com mais colunas exibem uma mensagem de "limite excedido".
* **Tamanho do nome do campo:** nomes de coluna com mais de 100 caracteres não são compatíveis com a detecção por IA.

<div id="important-4" />

> 🚧 **Importante!**
>
> Assim como acontece com campos adicionados manualmente, se um mapeamento sugerido por IA usar um [tipo Lista de...](#importante-7), o arquivo de fonte deve ser carregado ou conectado como Parquet. Arquivos CSV e GZIP não oferecem suporte a colunas do tipo array.

**Para remover um campo:**

* Passe o cursor sobre o lado direito do campo que você deseja remover e clique no ícone de lixeira que aparece ao passar o cursor.

**Para adicionar campos manualmente:**

Essa opção permite incluir um campo na audiência que não está presente no momento na fonte de dados.

1. Clique em **+ Novo campo**. Um campo vazio é adicionado.
2. Insira o nome do campo e selecione seu tipo.

<Image align="center" alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**Os tipos de campo incluem:**

* [**Identificador**](#identificador-vs-lista-de-identificadores)
  * ID Android
  * ID da AppsFlyer
  * CLIQUE
  * E-mail
  * Hashed email
  * E-mail anonimizado (sem pontos)
  * IDFA
  * Endereço IP
  * ID5 Id
  * MediaMath Id
  * Mobile Ad Id
  * Phone number
  * Número de telefone anonimizado (sem o sinal de mais)
  * Platform ID
  * SHA256 hashed ID
  * SHA256 phone number
  * ZIP+5 code
  * ZIP+4 code
  * LUID
  * ID da pessoa
* [**Lista de identificadores**](#identificador-vs-lista-de-identificadores)
  * Endereços de e-mail anonimizados (sem pontos)
  * Números de telefone anonimizados (sem o sinal de mais)
  * Hashed emails
  * Hashed phones
  * E-mails
  * Phones
  * ID5 Ids
  * MediaMath Ids
  * Mobile Ad Ids
  * IDFAs
  * IDs do Android
  * Endereços IP
* Boolean
* Data e hora
  * Date time
  * Date
* DMA (área de mercado designada)
  * ad\_personalization\_enabled
  * Ad user data enabled
  * EU DMA Applies
* Number
  * Double
  * List of Numbers
  * Longo
  * Number
* Caraterística
  * Caraterística
  * App Id
  * List of Text

<div id="identifier-vs-list-of-identifiers" />

#### **Identificador vs. Lista de identificadores:**

Os tipos de identificador contêm um único valor por linha (por exemplo, um e-mail ou um CUID por linha). Os tipos de lista de identificadores contêm uma matriz de valores por linha (por exemplo, uma única linha pode conter vários e-mails com hash ou IDs de dispositivo) — use isto quando uma fonte precisar corresponder a mais de um identificador por registro.

<div id="important-5" />

> 🚧 **Importante!**
>
> Se uma fonte incluir qualquer campo mapeado para um tipo de **Lista de...** tipo (Lista de identificadores, Lista de números ou Lista de texto), o arquivo de fonte deve ser carregado ou conectado como Parquet. Arquivos CSV e GZ não oferecem suporte a colunas do tipo matriz, portanto os campos de lista podem não ser ingeridos corretamente nesses formatos.

<div id="reload-source-fields" />

#### Recarregar campos da fonte

Se a configuração de um dos seus arquivos de dados tiver mudado, você poderá atualizar o arquivo de fonte para refletir as alterações.

<div id="note-2" />

> 📘 **Importante!**
>
> Recarregar a fonte redefine os nomes das colunas na fonte para corresponder aos nomes atualizados do arquivo. Isso substituirá qualquer um dos nomes de campo na lista e o tipo deles.

**Para recarregar campos atualizados de um arquivo:**

1. Clique em **Recarregar campos**.
2. Selecione o local do arquivo.
   * Para um arquivo local: faça upload do arquivo.
   * Para um arquivo do seu serviço de nuvem: clique em **Carregar do cloud bucket** e siga as instruções.
3. Clique em **OK**. Os arquivos atualizados agora são exibidos.

<div id="3-verify-eu-user-inclusion" />

#### 3. Verificar inclusão de usuários da UE

* Selecione **Sim** ou **Não** para a pergunta: **Sua fonte inclui usuários europeus aos quais se aplicam os regulamentos DMA da UE?**

Saiba mais sobre as regulamentações de privacidade da Lei de Mercados Digitais da UE.

<div id="4-test-the-source-data" />

#### 4. Testar os dados da fonte

* [Opcional] Clique em **Teste** para verificar erros no formato ou na validade dos campos da fonte.

<div id="5-save-the-source" />

#### 5. Salve a fonte

* Clique em **Salvar** para salvar a fonte.

Após a confirmação, a nova fonte é adicionada na aba **Fontes**.

<div id="note-3" />

> 📘 **Importante!**
>
> Se você carregou a fonte de um arquivo local, salvar a fonte aciona a criação automática da estrutura da pasta, e a mensagem de confirmação exibida inclui um link para a pasta fonte.

</Accordion>

<div id="manage-your-sources" />

## Gerenciar suas fontes

As fontes que você criou são exibidas na aba **Fontes**. Aqui, você pode editar o nome e a estrutura da fonte, compartilhá-la com um colaborador e excluí-la, desde que ela ainda não esteja sendo usada em uma audiência.

<Accordion title="Editar uma fonte">

1. Vá para a aba **Fontes** do **Data Clean Room**.
2. Na lista de fontes, passe o cursor sobre a fonte que você deseja editar e clique no ícone de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) no fim da linha.
3. Na página **Editar fonte**, edite os campos relevantes, conforme detalhado abaixo.
4. Clique em **Guardar.**

<div id="edit-the-source-name" />

#### Editar o nome da fonte

Ao editar o nome da fonte, siga estes [requisitos de nomenclatura](#requisitos-e-diretrizes).

<div id="edit-the-source-location" />

#### Editar a localização da fonte

1. Na página **Editar fonte** > **Localização da fonte**, selecione uma conexão de dados diferente.
2. Selecione os detalhes relevantes do local.
3. [Opcional] [Teste a fonte](#4-testar-os-dados-da-fonte).
4. Clique em **Guardar.**

<div id="edit-the-field-mapping" />

#### Editar o mapeamento de campos

1. Acesse o mapeamento de campos e faça as alterações necessárias: altere o campo ou atualize o campo DCP mapeado.
2. Clique em **Guardar**.

<div id="important-6" />

> 🚧 **Importante!**
>
> Não se esqueça de fazer alterações correspondentes refletindo a nova estrutura de origem em quaisquer relatórios para os quais esta origem é usada:
>
> * Os campos que foram removidos, tiveram o mapeamento desfeito ou foram alterados em relação ao mapeamento anterior são automaticamente removidos de quaisquer relatórios em que são usados.
> * Os campos recém-adicionados ou mapeados não são incluídos automaticamente nos relatórios existentes até que você edite as definições do relatório para incluí-los.

</Accordion>

<Accordion title="Excluir uma fonte">

Você pode excluir qualquer fonte, exceto quando ela estiver sendo usada em uma audiência. Se esse for o caso, uma notificação especificará as audiências que usam essa fonte. Para habilitar a exclusão da fonte, primeiro você deve excluir a audiência vinculada a ela. Quanto às fontes compartilhadas com você, elas só podem ser excluídas pelo proprietário da fonte.

1. Vá para a aba **Fontes** do **Data Clean Room.**
2. Na lista de fontes, passe o mouse sobre a fila da fonte que você deseja excluir.
3. Clique no ícone de exclusão ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) exibido no lado direito da linha.
4. Na caixa de diálogo, clique em **Excluir** para confirmar.

</Accordion>

<div id="sharing-permissions" />

## Permissões de compartilhamento

A concessão de permissões aos seus colaboradores para visualizar e usar os dados da sua fonte é feita ao <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration">criar colaborações</Anchor>. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-sharing-permissions">permissões de compartilhamento</Anchor>.

<div id="additional-information" />

## Informações adicionais

Esta seção fornece algumas referências adicionais e informações úteis.

<Accordion title="Criar manualmente uma estrutura de pastas do bucket de armazenamento (opcional)">

Em geral, é mais fácil permitir que a AppsFlyer gere automaticamente a estrutura de pastas necessária como parte do processo de criação da fonte. No entanto, se você deseja criar essas pastas manualmente, pode fazer isso da seguinte maneira.

<div id="create-a-dcr-key-folder" />

#### Crie uma pasta de chave DCR

Para garantir segurança máxima, a pasta diretamente abaixo do bucket (a "pasta de chave DCR") deve ser nomeada com a **chave DCR** alfanumérica de 8 caracteres atribuída à sua conta (por exemplo, `01bcc5fb`). *Observe que isso é diferente de qualquer outra senha ou chave associada à sua conta da AppsFlyer.*

A pasta de chaves DCR geralmente é criada manualmente usando a interface de seu serviço em cloud selecionado.

**Para obter a chave DCR da sua conta:**

* Clique no menu de 3 pontos (ações) no canto superior direito e selecione **chave DCR**.

[<Image align="center" alt="Chave DCR.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://support.appsflyer.com/hc/article_attachments/49929203409169)

Após criar a pasta de chaves DCR, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### Pasta de entrada de nível superior

Embora não seja necessário, a prática recomendada é criar uma pasta de entrada de nível superior diretamente abaixo da pasta de chaves DCR. Esta pasta será dedicada aos arquivos que você fizer upload para o DCR.

A pasta de entrada de nível superior geralmente é criada manualmente usando a interface de seu serviço em cloud selecionado.

* Esta prática é ainda mais importante caso você use o mesmo bucket tanto para fazer o upload de arquivos de dados (entrada) quanto para receber relatórios (saída).
* Você pode nomear essa pasta como quiser, desde que ela esteja de acordo com as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">exigências de nomenclatura do DCR</Anchor>. Para facilitar a identificação, ela costuma ser denominada como `input/`.

Depois de criar a pasta de entrada de nível superior, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### Pasta de segundo nível para cada fonte de dados

Você pode fazer o upload regular de diferentes arquivos de fontes de dados para processamento no DCR. A cada uma dessas fontes de dados deve ser atribuída uma pasta separada ("pastas de fontes de dados").

Assim, por exemplo, se você planeja fazer o upload de 2 arquivos no DCR para processamento, todos os dias: *BI-data.csv* e *CRM-data.gzip*, você atribuiria uma pasta para cada uma dessas fontes de dados. Você pode escolher chamar essas pastas `BI-data/` e `CRM-data/`.

As pastas das fontes de dados geralmente são criadas manualmente usando a interface de seu serviço em cloud selecionado.

Após criar 2 pastas de fonte de dados, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

Em cada pasta de fonte de dados, [subpastas aninhadas por data e versão](#nested-subfolders-for-each-date-and-version) devem ser criadas sempre que a fonte for atualizada.

</Accordion>

<div id="privacy-regulations" />

## Regulamentos de Privacidade

Esta seção descreve informações importantes sobre as regulamentações atuais de privacidade.

<Accordion title="Entender a política de consentimento de usuários da UE do Google e suas implicações">

Como parte da aplicação da Lei dos Mercados Digitais (DMA) pelo Google, o Google atualizou sua política de consentimento de usuários da UE em 6 de março de 2024. Como parceiro de atribuição de aplicativos do Google, a AppsFlyer fez as alterações necessárias para dar suporte aos requisitos dessa política, garantindo que os anunciantes maximizem o valor de seus canais de marketing do Google Ads.

<div id="note-4" />

> 📘 **Importante!**
>
> * A aplicação da Lei dos Mercados Digitais (DMA) pelo Google se aplica a todas as plataformas.
> * Saiba mais sobre isso:
>   * <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Insights e recursos sobre a Lei dos Mercados Digitais</Anchor>
>   * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ do Google</Anchor>

<div id="adding-consent-fields" />

#### Adição de campos de consentimento

Ao configurar uma fonte destinada à ativação de audiências no Google e confirmar **Sim** para a pergunta **Sua fonte envolve usuários europeus sujeitos às regulamentações da DMA da UE?** certifique-se de que os campos de consentimento adicionais na tabela abaixo estejam incluídos no arquivo de fonte. Isso permite que a AppsFlyer transfira as informações necessárias ao Google durante o processo de ativação.

**Campos de consentimento adicionais e seus valores de resposta:**

<table><thead><tr><th>String vazia</th><th>Valor da resposta</th><th>Campo explicado</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>verdadeiro/falso</td><td>O usuário está localizado no EEE (Espaço Econômico Europeu), ao qual a DMA se aplica?</td></tr><tr><td><span id="ad_personalization"></span><code>personalização_de_anúncio</code></td><td>\*true/false</td><td>O utilizador deu consentimento à Google para usar os seus dados para publicidade personalizada?</td></tr><tr><td><span id="ad_user_data"></span><code>dados_do_utilizador_anúncio</code></td><td>\*true/false</td><td>O utilizador deu consentimento para enviar os seus dados de utilizador ao Google? </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\* Quando “<strong>true</strong>”, a AppsFlyer inclui os identificadores de usuário que você enviou para os usuários que deram consentimento.<br/>   Quando “<strong>false</strong>”: a AppsFlyer não os inclui, pois eles não foram enviados à AppsFlyer.</td></tr></tbody></table>

<div id="potential-impact-on-the-audience-size" />

#### Possível impacto no tamanho da audiência

O tamanho real e estimado da audiência enviada ao Google pode variar com base no número de usuários que concedem ou negam consentimento.

</Accordion>

<div data-zendesk-anchors="introduction=sobre-as-fontes-da-dcp h_01HPKB2ERNRQG73AFA0X7XEDEF=sobre-as-fontes-da-dcp source-format=requisitos-de-dados-de-origem h_01HPKB2ERPANE0CAXFP9RG5YEH=requisitos-de-dados-de-origem creating-a-source=criar-fonte h_01HPKB2ERPX2T413N3T93YBBZB=criar-fonte requirements-and-guidelines=requisitos-e-diretrizes h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=requisitos-e-diretrizes source-locations-in-bigquery=locais-de-origem-no-bigquery 01HX49VY7D8KG5DCB82BP69BXV=locais-de-origem-no-bigquery source-locations-in-snowflake=locais-de-origem-no-snowflake 01HX49VY7DXH5YN8FF0NFAJBC2=locais-de-origem-no-snowflake source-locations-in-cloud-storage-buckets=locais-de-origem-em-buckets-de-armazenamento-em-nuvem 01HX49VY7D3CSF4SQ79Q7CZKWX=locais-de-origem-em-buckets-de-armazenamento-em-nuvem 01HX49VY7D307DT5VTMGHPF3WA=importante local-file-system=local-da-fonte-como-arquivos-locais h_01HX4SKEGE9NVCA6VYSR77S2DK=local-da-fonte-como-arquivos-locais h_01K1FW3AW2AW4TPDS0ZGPQCMX3=local-da-fonte-como-arquivos-locais h_01HX4T0H6SFQJEWFETKFD1CY6S=importante-1 h_01K29ETW94GQM9YYF5A4Y6DKB6=importante-2 overwrite-method-specifications=requisitos-para-upload-de-snapshot snapshot-upload-requirements=requisitos-para-upload-de-snapshot h_01K1G33RX95KP9TJ4002DDJBCE=requisitos-para-upload-de-snapshot h_01K2A7MAWS5KR16QV0Y8AE39GW=requisitos-para-upload-de-snapshot h_01K2CC62XGAVTD5JH5DYXP0947=importante-3 data-title=requisitos-de-upload-de-append append-delta-upload-requirements=requisitos-de-upload-de-append h_01K2A7MAWT7CRHY1TV5J41MM0D=requisitos-de-upload-de-append h_01K2C6QNJSAH9D3M48T02JHQ3R=requisitos-de-upload-de-append load-the-source-fields=1-carregar-seus-campos-de-fonte h_01HPKB2ERQTJPGG68FSEBHVVJA=1-carregar-seus-campos-de-fonte h_01HPKB2ERRZNPYVVD8GHD7PBPE=importante-4 configure-the-source-fields=2-configure-os-campos-de-fonte h_01HX64YHGHMK352E3RXHBFV0B5=2-configure-os-campos-de-fonte 01HX6HVZ6DK2WH71JVB0J9WPBF=importante-5 h_01K5AI0D3TFIELDTYPEDETECT=detec%C3%A7%C3%A3o-de-tipo-de-campo-assistida-por-ia ai-assisted-field-type-detection=detec%C3%A7%C3%A3o-de-tipo-de-campo-assistida-por-ia h_01K5AI0D3TLIMITATIONS=limita%C3%A7%C3%B5es limitations=limita%C3%A7%C3%B5es h_01K5AI0D3TIMPORTANT=importante-6 identifier-vs-list-of-identifiers=identificador-vs-lista-de-identificadores h_01KYSMJKRA2E13PH2QS671BSKG=identificador-vs-lista-de-identificadores h_01KYSJNEWS5QY5Q13Z11TNJHX1=importante-7 reload-source-fields=recarregar-campos-da-fonte h_01HX6TDNEMJFQM5FA95Y3C1QHD=recarregar-campos-da-fonte h_01HX6WF7YC014Z7ZX359RB5ZRZ=importante-8 verify-eu-user-inclusion=3-verificar-inclus%C3%A3o-de-usu%C3%A1rios-da-ue 01HZKZ2T33TYCQ8J59YGDYN7DK=3-verificar-inclus%C3%A3o-de-usu%C3%A1rios-da-ue test-the-source-data=4-testar-os-dados-da-fonte h_01HX6WGD421PCWEWTN5YJ7V42H=4-testar-os-dados-da-fonte save-the-source=5-salve-a-fonte h_01HYX92EXSJNM5B2PDXEAEBNFS=5-salve-a-fonte h_01HYXC06K3ZWQE867NKBT95RFH=importante-9 working-with-existing-sources=gerenciar-suas-fontes h_01HPKB2ERS5PK2P2XTC4ZMPCMC=gerenciar-suas-fontes edit-the-source-name=editar-o-nome-da-fonte 01J1SMACQHFEVAR8ZC6W8T0BAV=editar-o-nome-da-fonte edit-the-source-location=editar-a-localiza%C3%A7%C3%A3o-da-fonte h_01J1SM789AFJBSD0NG826P98Q4=editar-a-localiza%C3%A7%C3%A3o-da-fonte edit-the-source-structure=editar-o-mapeamento-de-campos h_01J1SNB66WQMBV1GQE4PDQ0NW4=editar-o-mapeamento-de-campos h_01HPKB2ERTYP6BFAESN3MHZSQG=importante-10 permissions=permiss%C3%B5es-de-compartilhamento h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=permiss%C3%B5es-de-compartilhamento reference=informa%C3%A7%C3%B5es-adicionais h_01HPKB2ERV1KK3J8YX918GCF3M=informa%C3%A7%C3%B5es-adicionais creating-a-dcr-key-folder=crie-uma-pasta-de-chave-dcr h_01HPKB2ERV7MQJ9CK44T92GK2G=crie-uma-pasta-de-chave-dcr toplevel-input-folder=pasta-de-entrada-de-n%C3%ADvel-superior h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=pasta-de-entrada-de-n%C3%ADvel-superior secondlevel-folder-for-each-data-source=pasta-de-segundo-n%C3%ADvel-para-cada-fonte-de-dados h_01HPKB2ERVVFMP81RE8ATZ6SZ8=pasta-de-segundo-n%C3%ADvel-para-cada-fonte-de-dados privacy-regulations-eu-digital-markets-act=regulamentos-de-privacidade h_01HZHBF0NZDTXAA3MY1A0BPE5E=regulamentos-de-privacidade h_01HZM4EFRJD483NARKDPPPPXCY=importante-11 adding-consent-fields=adi%C3%A7%C3%A3o-de-campos-de-consentimento h_01HZHBF0NZSDGDYG2ZWNW4KQYD=adi%C3%A7%C3%A3o-de-campos-de-consentimento -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them potential-impact-on-the-audience-size=poss%C3%ADvel-impacto-no-tamanho-da-audi%C3%AAncia h_01HZHBF0NZJBSXNBDFZH4YKNSH=poss%C3%ADvel-impacto-no-tamanho-da-audi%C3%AAncia" />
