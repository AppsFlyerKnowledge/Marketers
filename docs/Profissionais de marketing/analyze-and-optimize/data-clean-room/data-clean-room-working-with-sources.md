---
title: Data Clean Room—Trabalhando com fontes
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-08-19T00:05:57Z'
  id: 5041487011601
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Configure as fontes de dados personalizadas que você compartilha com o Data Clean Room (DCR) para correspondência com dados de atribuição e para criar relatórios do DCR.

<div id="introduction" />

## Introdução

Muitos relatórios DCR são projetados para corresponder seus **dados de atribuição** aos dados de suas **fontes personalizadas.** Este artigo contém tudo o que você precisa saber sobre como trabalhar com fontes personalizadas, incluindo como:

* [Formatar os dados de origem](/docs/data-clean-room-working-with-sources#requisitos-de-dados-de-origem)
* [Crie a fonte](/docs/data-clean-room-working-with-sources#criando-uma-fonte) dentro do DCR
  * [Nomeie a fonte](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * [Especifique o local](/docs/data-clean-room-working-with-sources#2-specify-the-source-location) de onde o DCR recuperará os dados de origem
  * [Defina a estrutura](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) da fonte (rotulando campos como métricas, dimensões e identificadores)
  * [Salve a fonte](/docs/data-clean-room-working-with-sources#4-save-the-source)
* [Atualize os dados de origem](/docs/data-clean-room-working-with-sources#atualizando-fontes-para-acionar-o-processamento-de-relatórios) regularmente para acionar o processamento de relatórios
* [Trabalhe com as fontes existentes](/docs/data-clean-room-working-with-sources#trabalhar-com-as-fontes-existentes)

> 🚧 **Important**
>
> **Antes de começar**
>
> Antes de criar fontes personalizadas, primeiro você deve:
>
> * [Obrigatório] <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services">Configurar os serviços de nuvem</Anchor> dos quais o DCR recuperará os dados. Dois tipos de serviços em nuvem são suportados:
>   * **Data warehouses:** BigQuery e Snowflake
>   * **Buckets de armazenamento em nuvem:** Amazon S3 (AWS) e GCS
> * [Opcional] <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#criar-conexões-de-entrada">Crie conexões de entrada</Anchor> na plataforma da AppsFlyer para conectar esses serviços em nuvem ao DCR.
>   * Se essas conexões não foram configuradas anteriormente, você será solicitado a configurá-las durante a criação da fonte.

<div id="source-requirements" />

## Requisitos de dados de origem

As fontes devem atender a esses requisitos para evitar erros na criação da fonte e no processamento do relatório.

<div id="data-format" />

<Accordion title="Formato de dados (relevante para todas as fontes)">

Os dados dentro das fontes devem atender a estes requisitos:

* **Data e hora:**
  * **Formato:** aaaa-MMM-dd hh:mm:ss (*por exemplo*, `2023-APR-18 15:30:35`)
  * **Fuso horário:** UTC
* **Números:** máximo 2 dígitos após a vírgula decimal
* **Comprimento da string:** máximo de 256
* **Limitações de caracteres**
  * **Para nomes de campo (cabeçalhos de coluna):** sem espaços ou caracteres especiais
  * **Todos os outros dados:** sem limitações (todos os caracteres são válidos)

</Accordion>

<div id="table-columns" />

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

<div id="file-format" />

<Accordion title="Nome e formato do arquivo (relevante apenas para fontes em depósitos de armazenamento em nuvem)">

Os arquivos de origem armazenados no Amazon S3 ou GCS devem atender a estes requisitos de nome e formato de arquivo:

* O nome do arquivo deve estar em conformidade com <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">os requisitos de nomenclatura DCR</Anchor>
* Formato CSV ou GZIP
  * O arquivo subjacente à compressão GZIP deve ser um arquivo CSV.
* Número de arquivos de fonte de dados por [pasta de dados](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version):
  * **CSV:** máximo 1
  * **GZIP:** no máximo 1 arquivo em uma única parte. Arquivos GZIP de várias partes são compatíveis quando nomeados da seguinte maneira: `filename_part01.gzip`, `filename_part02.gzip`, etc.

</Accordion>

<div id="creating-a-source" />

## Criando uma fonte

O processo de criar uma fonte consiste em **todas as etapas descritas abaixo.** Elas foram separadas em abas para facilitar a leitura.

**Siga essas etapas para criar uma fonte:**

<div id="1-name-the-source" />

<Accordion title="#1: Nomeie a fonte">

1. Vá para a aba **Fontes** do **Data Clean Room.**
2. Clique no botão **+ Nova fonte**.  
   A página **Nova fonte** abre.
3. Insira o nome da fonte no canto superior esquerdo.
   * Esse pode ser qualquer nome exclusivo que ajudará você a identificar a fonte na plataforma DCR. Ele não precisa corresponder ao nome do arquivo.
   * **Importante!** Certifique-se de que o nome da fonte é diferente de todas as outras fontes em sua conta ou você não poderá [salvá-la](/docs/data-clean-room-working-with-sources#4-save-the-source).
   * Requisitos do nome da fonte:
     * Comprimento: 2-80 caracteres
     * Caracteres válidos:
       * letras `(A-Z, a-z)`
       * números `(0-9)`, *não podem ser o primeiro caractere de um nome;*
     * Caracteres inválidos:
       * espaços
       * todos os outros símbolos ou caracteres especiais

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="#2: Especifique a localização da fonte">

**Para especificar a localização da fonte:**

1. Selecione a <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#visão-geral">conexão</Anchor> na qual a fonte será (ou foi) criada.
   * Se não houver conexões definidas em sua conta, a caixa de diálogo **Nova conexão** será aberta, solicitando que você crie uma. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão">estas instruções</Anchor> para criá-la.
   * Se você tiver conexões existentes, mas quiser usar uma nova, clique no botão ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) para abrir a caixa de diálogo **Nova conexão**. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão">estas instruções</Anchor> para criá-la.
2. Continue com as instruções relevantes abaixo com base na localização dos dados de sua fonte.

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

* Permitir que a AppsFlyer gere as pastas facilita o processo. No entanto, você pode optar por criá-las manualmente, de acordo com as instruções <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services">detalhadas aqui</Anchor>.

- or -

* Você pode carregar uma versão protótipo do arquivo de origem diretamente de sua conexão.
  * Antes de começar:
    * Permita que a AppsFlyer crie automaticamente a estrutura da pasta fonte; ou
    * Observação

Se a AppsFlyer gera as pastas, a única informação adicional necessária é o nome que você deseja dar à **pasta fonte.** (Esta é a pasta de nível superior na qual você atualiza a fonte cada vez que deseja utilizá-la para executar uma nova versão do relatório) Você também pode indicar se deseja que a pasta fonte seja criada abaixo de uma pasta principal – frequentemente chamada de **entrada**. Você também pode indicar se deseja que a pasta de origem seja criada dentro de uma pasta-mãe – geralmente chamada de **input.**

**Para concluir a especificação de um local de origem em um bucket de armazenamento em nuvem, insira o nome da pasta de origem.**

* Por padrão, o nome da pasta fonte exibida:
  * É baseado no [nome que você forneceu à fonte](/docs/data-clean-room-working-with-sources#1-name-the-source). Você pode mudar o nome da pasta para atender às suas necessidades, desde que esteja de acordo com os requisitos de nomenclatura do DCR .
  * Indica que será gerado dentro de uma pasta principal denominada **entrada.** Esta pasta serve como pasta principal para todas as fontes que você carrega para o DCR.
    * A pasta **entrada** não é necessária, e você pode removê-la ou dar-lhe um nome diferente, desde que esteja de acordo com os <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">requisitos de nomenclatura do DCR</Anchor>.
    * Embora esta pasta não seja necessária, ter uma pasta **entrada** (ou uma pasta equivalente com um nome diferente) é considerado uma boa prática. É ainda mais recomendado quando você estiver usando o mesmo bucket de armazenamento em nuvem para carregar arquivos de dados (entrada) e receber relatórios (saída).

> 🚧 **Important**
>
> **Importante!**
>
> Se você criou manualmente o caminho da pasta, verifique se a conexão e o caminho inseridos na seção **Local de origem** correspondem ao caminho criado manualmente.

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="#3: Defina a estrutura da fonte">

Para todas as fontes que você compartilha com o DCR para processamento, a AppsFlyer precisa saber como cada campo de dados deve ser usado para criar relatórios. A definição da estrutura de origem consiste em:

* [Carregar os campos de origem](/docs/data-clean-room-working-with-sources#carregar-campos-de-origem)
* [Categorizar cada campo](/docs/data-clean-room-working-with-sources#categorizar-campos) (coluna) como um dos seguintes tipos:
  * **Identificador:** campo que identifica um usuário de aplicativo exclusivo (exemplos podem incluir CUID, AppsFlyer ID, etc.)
    * O objetivo principal dos identificadores no contexto do DCR é unir as fontes de dados para que os dados do usuário correspondentes possam ser combinados.
  * **Dimensão:** um atributo pelo qual você categoriza os usuários do aplicativo (exemplos podem incluir localização, data de instalação, campanha, etc.)
  * **Métrica:** dados numéricos que você coletou com relação a um usuário de aplicativo (exemplos podem incluir receita, número de aberturas do aplicativo, LTV, etc.)
    * Um campo de dados identificado como métrica deve conter **apenas valores numéricos.**

<div id="loading-source-fields" />

#### Carregar campos de origem

Carregue os campos de origem usando as instruções relevantes abaixo:

**Fontes de data warehouses**

Para carregar campos de uma origem localizada em um data warehouse (BigQuery ou Snowflake), clique no botão  ![dcr_load_fields_from_source.png](https://files.readme.io/667761e044a45e9a63bf904ada0ba07917014b5b446379213742510278b5a2dd-14986195290897.png).

> 🚧 **Important**
>
> **Importante!**
>
> Se a tabela de origem selecionada não incluir as [colunas de data e versão](/docs/data-clean-room-working-with-sources#table-columns) necessárias, você receberá um erro.

**Fontes de bucket de armazenamento em nuvem**

Para carregar campos de uma origem localizada em um bucket de armazenamento em nuvem (Amazon S3 ou GCS), você deve carregar um arquivo de origem de protótipo.

Para fins de definição da estrutura da fonte:

* Você pode carregar uma versão protótipo da fonte a partir de um arquivo local.
  * Se você selecionar esta opção, a AppsFlyer sempre cria automaticamente o caminho da pasta de fonte.

- or -

* Conexão de arquivo local (criação automática) Conexão (criação manual)
  * Se você selecionar esta opção, há uma opção adicional a ser feita:
    * Importante!
    * Crie manualmente a estrutura da pasta fonte

**Para carregar seu protótipo de arquivo fonte, siga as instruções na aba correspondente abaixo:**

<Tabs>
<Tab title="Arquivo local">

1. Na seção **Estrutura da fonte**, clique no botão <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Na janela que se abre, selecione **Carregar um arquivo local.**
3. Especifique o arquivo CSV ou GZIP que você deseja carregar, depois clique em OK.

</Tab>

<Tab title="Conexão (criação automática)">

**Para carregar o arquivo da sua conexão e permitir que a AppsFlyer crie a estrutura da pasta de origem:**

1. Na seção **Estrutura da fonte**, clique no botão <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Na janela que se abre, selecione **Carregar da conexão.**
3. Clique no link **Gerar pastas**.
   * A AppsFlyer cria automaticamente a estrutura de pasta necessária e a pasta de origem (na conexão que você especificou, com o nome da pasta de origem que você especificou).
4. Após a estrutura da pasta fonte ter sido criada, uma mensagem de confirmação é exibida, incluindo um link para a pasta fonte. Clique no link fornecido para carregar seu arquivo protótipo para a pasta fonte.
5. Quando o arquivo tiver terminado de carregar, clique em **OK.**

</Tab>

<Tab title="Conexão (criação manual)">

**Para carregar o arquivo fonte a partir de uma estrutura que você criou manualmente:**

1. Na seção **Estrutura da fonte**, clique no botão <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. Na janela que se abre, selecione **Carregar da conexão.**
3. **NÃO** clique em **Gerar pastas.** Em vez disso, carregue o arquivo diretamente na pasta de origem que você criou para ele.
4. Quando o arquivo tiver terminado de carregar, clique em **OK.**

</Tab>
</Tabs>

<div id="categorize-fields" />

#### Categorizar campos

Depois de carregar os campos, a AppsFlyer analisa o arquivo e uma lista de todos os campos de dados (colunas) é exibida na lista **Campos disponíveis**.

**Para categorizar os campos:**

1. Selecione um ou mais campos na lista **Campos disponíveis** à esquerda e use os botões no meio da tela para classificá-los como [identificadores, dimensões ou métricas](/docs/data-clean-room-working-with-sources#3-define-the-source-structure).
   * Quando um campo é categorizado, ele é exibido na lista de categorias relevante no lado direito da tela.
   * Você pode usar a barra de busca para pesquisar os campos das listas.
   * Para remover um campo de uma categoria para a qual ele foi designado, selecione-o na lista de categorias relevantes e use o botão **Remover** para retorná-lo à lista **Campos disponíveis**.
2. Repita este processo até que você tenha categorizado cada campo que deseja incluir nos relatórios do DCR.
   * Não é preciso categorizar cada campo na lista **Campos disponíveis**. Entretanto, um campo deve ser categorizado para que seja utilizado posteriormente em um relatório.
3. Se você editar a fonte antes de [salvá-la](/docs/data-clean-room-working-with-sources#4-save-the-source) e quiser usar campos dos dados de fonte editados, clique no link **Recarregar campos** na parte inferior da lista **Campos disponíveis**.
   * Observe que recarregar a fonte irá substituir os nomes dos campos na lista Campos disponíveis. Quaisquer campos categorizados anteriormente permanecerão nas listas **Identificadores,** **Dimensões,** ou **Métricas**.
   * Se um campo categorizado anteriormente não for encontrado nos dados de origem recarregados, ele ainda será exibido na lista de categorias relevantes, mas será marcado com um ícone de erro.

> 📘 **Note**
>
> **Atenção**
>
> Se você decidir usar campos adicionais desta fonte depois de salvá-la, você pode fazê-lo [editando a estrutura da fonte](/docs/data-clean-room-working-with-sources#editing-the-source-structure).

</Accordion>

<div id="4-save-the-source" />

<Accordion title="#4: Salve a fonte">

**Para salvar a fonte:**

1. [Opcional] Clique <Image alt="DCR_test_source.png" src="https://files.readme.io/c8d2bb2e7062d062a2ed7ddb84472c5acd02fc93b178b2299515b2374a3ad3e3-11240865384849.png" width="43px" /> para verificar a existência de erros no formato ou validade dos campos fonte.
2. Clique em **Salvar** para salvar a fonte.

   A fonte é criada e uma mensagem de confirmação é exibida.

   * Se você carregou a fonte de um arquivo local, salvar a fonte aciona a criação automática da estrutura da pasta, e a mensagem de confirmação exibida inclui um link para a pasta fonte.

   A nova fonte é exibida na lista de todas as fontes existentes na aba **Fontes** do Data Clean Room.

</Accordion>

<div id="updating-sources-to-trigger-report-processing" />

## Atualizando fontes para acionar o processamento de relatórios

Cada vez que você deseja que a AppsFlyer processe um arquivo de fontes de dados e crie um relatório com base nele, você deve fazer o upload de uma nova versão do arquivo para a pasta fonte, dentro de uma série de subpastas aninhadas que indicam a data e o número da versão (além de uma subpasta extra para que a AppsFlyer saiba onde os dados estão).

A AppsFlyer verifica continuamente novas versões de arquivos de origem para a **data atual e 2 dias antes.** Uma nova versão de um relatório é acionada sempre que novas versões dos arquivos de origem são encontradas (incluindo [arquivos \_SUCCESS](/docs/data-clean-room-working-with-sources#_success-files), conforme detalhado abaixo).

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="Subpastas para cada data e versão">

A estrutura das subpastas aninhadas é a seguinte:

* Dentro de cada pasta de fonte de dados --> 1 subpasta para cada data ("pasta de data")
  * **Formato:** `dt=aaaa-mm-dd/`
  * **Exemplo:** `dt=2022-12-15/`
* Dentro de cada pasta de datas --> 1 subpasta para cada versão naquela data ("pasta de versões")
  * **Formato:** `v=n/`
  * **Exemplo:** `v=1/`
  * **Observação:** a pasta da versão é necessária mesmo que você só faça o upload do arquivo uma vez por dia.
* Dentro de cada pasta de versão --> 1 subpasta para indicar a localização dos dados ("pasta de dados")
  * **Formato:** `data/`
  * A pasta de dados é o local para o qual o arquivo da fonte é carregado.

Na maioria dos casos, você usaria chamadas de API ou outros meios programáticos disponíveis para criar automaticamente as pastas de data/versão/dados cada vez que o arquivo da fonte de dados fosse carregado. Para informações adicionais, consulte a referência de API para seu serviço de nuvem: <Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html">AWS</Anchor>, <Anchor target="_blank" href="https://cloud.google.com/storage/docs/reference/libraries">GCS</Anchor>.

</Accordion>

<div id="_success-files" />

<Accordion title="Arquivos _SUCCESS">

Após concluir o upload de um arquivo de fonte de dados para a pasta de dados, você deve fazer o upload de um arquivo vazio chamado `_SUCCESS` para a pasta de **versão**. Isso alerta a AppsFlyer de que um novo arquivo está disponível para ser processado. Na maioria dos casos, você usaria uma API script para gerar e fazer o upload automático desse arquivo.

**Importante!** O upload do arquivo `_SUCCESS` é feito para a pasta **versão**, fora da pasta de dados.

O nome do arquivo \_SUCCESS:

* Deve estar em EM MAIÚSCULA
* Deve ser precedido por um underline `(_)`
* Não deve ter uma extensão de arquivo

Para arquivos GZIP de multi-partes:

* Deve ser feito upload de apenas um arquivo `_SUCCESS` para todas as partes do arquivo.
* O upload do arquivo `_SUCCESS` deve ser feito somente depois que todos os uploads de partes do arquivo estiverem completos.

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="Exemplo (após o carregamento dos arquivos)">

Após o upload dos arquivos da fonte em 2 dias (e após criar programaticamente pastas de data/versão/dados e arquivos `_SUCCESS`), sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" />

</Accordion>

<div id="working-with-existing-sources" />

## Trabalhar com as fontes existentes

Há várias maneiras de trabalhar com fontes existentes. Você inicia estes processos a partir da aba **Fontes** do Data Clean Room:

* [Edite o nome da fonte](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [Edite a estrutura da fonte](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [Exclusão de uma fonte](/docs/data-clean-room-working-with-sources#deleting-a-source) (se não estiver sendo usada para um relatório)

<div id="editing-the-source-name" />

<Accordion title="Edite o nome da fonte">

Para editar o nome da fonte:

1. Vá para a aba **Fontes** do **Data Clean Room.**
2. Na lista de fontes, passe o mouse sobre a fila da fonte que você deseja editar.
3. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que aparece no lado direito da fila.
4. Na página **Editar fonte**, edite o nome da fonte.
5. Clique no botão **Salvar** para salvar a fonte com o novo nome ou **Cancelar** para desfazer suas alterações.

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="Edite a estrutura da fonte">

Para editar a estrutura da fonte:

1. Vá para a aba **Fontes** do **Data Clean Room.**
2. Na lista de fontes, passe o mouse sobre a fila da fonte que você deseja editar.
3. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que aparece no lado direito da fila.
4. Na página **Editar fonte**, os campos que anteriormente eram categorizados como [identificadores, dimensões ou métricas](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) serão exibidos nas listas de categorias relevantes no lado direito da tela.
5. Você pode mover um campo previamente categorizado para uma categoria diferente sem recarregar os campos do arquivo fonte. Para fazer isso:
   1. Primeiro, selecione-o na lista de categorias relevantes e use o botão **Remover** para devolvê-lo à lista **Campos disponíveis**.
   2. Depois, selecione-o na lista **Campos disponíveis** e use os botões no meio da tela para classificá-lo como identificador, dimensão ou métrica.
6. Para trabalhar com campos no arquivo fonte que ainda não tenham sido categorizados, eles devem ser recarregados a partir do local de origem ou de um arquivo local. Faça esta seleção clicando no botão relevante **Recarregar campos** na parte inferior da lista **Campos disponíveis**.
7. A AppsFlyer analisa o arquivo, e uma lista de todos os campos de dados (colunas) anteriormente não categorizados é exibida na lista **Campos disponíveis**.
   * Os campos que anteriormente eram categorizados como identificadores, dimensões ou métricas ainda serão exibidos nas listas de categorias relevantes no lado direito da tela.
   * Se um campo previamente categorizado não for encontrado no arquivo fonte recarregado, ele ainda será exibido na lista de categorias relevante, mas será marcado com um ícone de erro.
8. Selecione um ou mais campos na lista **Campos disponíveis** à esquerda e use os botões no meio da tela para classificá-los como identificadores, dimensões ou métricas.
9. Quando todas as alterações necessárias forem feitas, clique no botão **Salvar** para salvar a fonte com a estrutura atualizada ou **Cancelar** para desfazer suas alterações.

> 🚧 **Important**
>
> **Importante!**
>
> Não se esqueça de fazer alterações correspondentes refletindo a nova estrutura de origem em quaisquer relatórios para os quais esta origem é usada:
>
> * Os campos que foram removidos, estão sem categoria ou foram alterados em relação às categorias anteriores são automaticamente removidos de quaisquer relatórios em que são utilizados.
> * Os novos campos adicionados ou categorizados não são automaticamente incluídos nos relatórios existentes até que você edite as definições do relatório para incluí-los.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="Deletando uma fonte">

1. Vá para a aba **Fontes** do **Data Clean Room.**
2. Na lista de fontes, passe o mouse sobre a fila da fonte que você deseja excluir.
3. Clique no botão de exclusão ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) exibido no lado direito da linha.
4. No diálogo, confirme que você deseja excluir a fonte.
   * Não é possível eliminar uma fonte que está sendo usada por um relatório. Se este for o caso, uma mensagem listará os relatórios nos quais a fonte está sendo utilizada. Para apagar a fonte, você pode:
     * Excluir os relatórios em que está sendo usada; ou
     * Remover os campos de origem das definições dos relatórios em que são utilizados.

</Accordion>

<div id="reference" />

## Referência

<div id="manually-creating-a-folder-structure" />

<Accordion title="Criação manual de uma estrutura de pasta do bucket de armazenamento (relevante somente se você optar por fazer isso)">

Em geral, é mais fácil permitir que a AppsFlyer gere automaticamente a estrutura de pastas necessária como parte do processo de criação da fonte. No entanto, se você deseja criar essas pastas manualmente, pode fazer isso da seguinte maneira.

<div id="create-a-dcr-key-folder" />

#### Crie uma pasta de chave DCR

Para garantir segurança máxima, a pasta diretamente abaixo do bucket (a "pasta de chave DCR") deve ser nomeada com a **chave DCR** alfanumérica de 8 caracteres atribuída à sua conta (por exemplo, `01bcc5fb`). *Observe que isso é diferente de qualquer outra senha ou chave associada à sua conta da AppsFlyer.*

A pasta de chaves DCR geralmente é criada manualmente usando a interface de seu serviço em cloud selecionado.

**Para obter a chave DCR da sua conta, clique no botão da chave DCR na parte superior da página principal do DCR.**

<Image align="center" alt="dcr_key_button.png" src="https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png" />

Após criar a pasta de chaves DCR, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" />

<div id="top-level-input-folder" />

#### Pasta de entrada de nível superior

Embora não seja necessário, a prática recomendada é criar uma pasta de entrada de nível superior diretamente abaixo da pasta de chaves DCR. Esta pasta será dedicada aos arquivos que você fizer upload para o DCR.

A pasta de entrada de nível superior geralmente é criada manualmente usando a interface de seu serviço em cloud selecionado.

* Esta prática é ainda mais importante caso você use o mesmo bucket tanto para fazer o upload de arquivos de dados (entrada) quanto para receber relatórios (saída).
* Você pode nomear essa pasta como quiser, desde que ela esteja de acordo com as <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">exigências de nomenclatura do DCR</Anchor>. Para facilitar a identificação, ela costuma ser denominada como `input/`.

Depois de criar a pasta de entrada de nível superior, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" />

<div id="second-level-folder-for-each-data-source" />

#### Pasta de segundo nível para cada fonte de dados

Você pode fazer o upload regular de diferentes arquivos de fontes de dados para processamento no DCR. A cada uma dessas fontes de dados deve ser atribuída uma pasta separada ("pastas de fontes de dados").

Assim, por exemplo, se você planeja fazer o upload de 2 arquivos no DCR para processamento, todos os dias: *BI-data.csv* e *CRM-data.gzip*, você atribuiria uma pasta para cada uma dessas fontes de dados. Você pode escolher chamar essas pastas `BI-data/` e `CRM-data/`.

As pastas das fontes de dados geralmente são criadas manualmente usando a interface de seu serviço em cloud selecionado.

Após criar 2 pastas de fonte de dados, sua estrutura de bucket/pasta deve ficar assim:

<Image align="center" alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" />

Em cada pasta de fonte de dados, [subpastas aninhadas por data e versão](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version) devem ser criadas sempre que a fonte for atualizada.

</Accordion>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HPKB2ERNRQG73AFA0X7XEDEF=introdu%C3%A7%C3%A3o source-format=requisitos-de-dados-de-origem h_01HPKB2ERPANE0CAXFP9RG5YEH=requisitos-de-dados-de-origem h_01HPKB2ERPQ787V0PAABP7Q2YY=data-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=criando-uma-fonte h_01HPKB2ERPX2T413N3T93YBBZB=criando-uma-fonte h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=locais-de-origem-no-bigquery h_01HPKB2ERQ28JQ2CK16RYZ38G6=locais-de-origem-no-bigquery source-locations-in-snowflake=locais-de-origem-no-snowflake h_01HPKB2ERQWFGF8MN8ZYAXWC87=locais-de-origem-no-snowflake source-locations-in-cloud-storage-buckets=locais-de-origem-em-buckets-de-armazenamento-em-nuvem h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=locais-de-origem-em-buckets-de-armazenamento-em-nuvem h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=carregar-campos-de-origem h_01HPKB2ERQTJPGG68FSEBHVVJA=carregar-campos-de-origem categorize-fields=categorizar-campos h_01HPKB2ERSYCFE1EYTCK550VTK=categorizar-campos h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=atualizando-fontes-para-acionar-o-processamento-de-relat%C3%B3rios h_01HPKB2ERSCPAPB6WE3354ECW9=atualizando-fontes-para-acionar-o-processamento-de-relat%C3%B3rios h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=trabalhar-com-as-fontes-existentes h_01HPKB2ERS5PK2P2XTC4ZMPCMC=trabalhar-com-as-fontes-existentes h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=refer%C3%AAncia h_01HPKB2ERV1KK3J8YX918GCF3M=refer%C3%AAncia h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=crie-uma-pasta-de-chave-dcr h_01HPKB2ERV7MQJ9CK44T92GK2G=crie-uma-pasta-de-chave-dcr toplevel-input-folder=pasta-de-entrada-de-n%C3%ADvel-superior h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=pasta-de-entrada-de-n%C3%ADvel-superior secondlevel-folder-for-each-data-source=pasta-de-segundo-n%C3%ADvel-para-cada-fonte-de-dados h_01HPKB2ERVVFMP81RE8ATZ6SZ8=pasta-de-segundo-n%C3%ADvel-para-cada-fonte-de-dados" />
