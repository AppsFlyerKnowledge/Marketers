---
title: Data Clean Room—Configurando serviços de nuvem
metadata:
  keywords:
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
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-08-19T00:05:49Z'
  id: 4591167507217
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** configure um ou mais data warehouses (BigQuery, Snowflake) e/ou buckets de armazenamento em nuvem (Amazon S3, GCS) para compartilhar dados com o Data Clean Room e receber relatórios.

<div id="overview" />

## Visão geral

A preparação para usar o Data Clean Room (DCR) envolve a configuração de:

* Os serviços/locais de nuvem dos quais o DCR lê dados primários de seus sistemas (fontes personalizadas). Esses locais são usados para criar **conexões de entrada.**
* Os serviços de nuvem/locais para os quais o DCR entrega relatórios após o processamento. Esses locais são usados para criar **conexões de saída.**

Criar uma conexão de entrada ou saída é um processo de 2 etapas:

* **Etapa #1 –** Use as interfaces de seus serviços de nuvem selecionados para prepará-los para uso com o DCR (este artigo).
* **Etapa #2 –** Use a plataforma da AppsFlyer para conectá-los ao DCR. (Consulte <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections">Data Clean Room—Trabalhando com conexões</Anchor>).

<div id="note" />

> 📘 **Observação**
>
> Consulte <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#requisitos-de-dados-de-origem">Data Clean Room—Trabalhando com fontes</Anchor> para obter informações completas sobre os requisitos de dados de origem:
>
> * Formato de dados *(para todas as fontes)*
> * Colunas da tabela *(para origens em data warehouses)*
> * Nome e formato do arquivo *(para fontes em buckets de armazenamento em nuvem)*

<div id="supported-cloud-services" />

### Serviços de nuvem compatíveis

Dois tipos de serviços em nuvem são suportados para conexões de entrada e saída para o DCR:

* **Data warehouses:** BigQuery e Snowflake
* **Buckets de armazenamento em nuvem:** Amazon S3 (AWS) e GCS

Você pode usar uma ou qualquer combinação desses serviços para conexões de entrada e saída.

<div id="important" />

> 🚧 **Importante!**
>
> * Se você estiver usando várias fontes personalizadas para um único relatório, elas devem estar localizadas em buckets de armazenamento em nuvem.
> * É muito comum usar o mesmo bucket de armazenamento em nuvem no Amazon S3 ou GCS para conexões de entrada e saída. Certifique-se de seguir as [instruções especiais para essa configuração](/docs/data-clean-room-setting-up-cloud-services#configurando-o-mesmo-bucket-de-armazenamento-em-nuvem-para-conexões-de-entrada-e-saída).

<div id="setting-up-cloud-services-for-inbound-connections" />

## Configurando serviços de nuvem para conexões de entrada

Prepare seus serviços de nuvem selecionados para uso com conexões de entrada DCR de acordo com as instruções nas abas a seguir.

<div id="data-warehouses--bigquery-and-snowflake" />

### Data warehouses – BigQuery e Snowflake

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**Observação:** o procedimento a seguir deve ser realizado pelo administrador do Google Cloud.

**Para criar um conjunto de dados e conceder as permissões DCR:**

1. Faça login no console do Google Cloud.
2. Acesse a página do BigQuery.
3. Em um projeto novo ou existente do Google Cloud, crie um conjunto de dados para uso exclusivo do DCR:
   1. No painel **do lado esquerdo**, clique no botão **Exibir ações** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> à direita do ID do projeto.
   2. Selecione **Criar conjunto de dados.**

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. No painel que se abre **do lado direito**, insira o nome do conjunto de dados e selecione outras opções conforme necessário.
      * Você pode usar qualquer nome que lhe agrade – usando apenas letras, números e sublinhados (\_).
        * **Recomendado:** use um nome que indique que o conjunto de dados está sendo usado para uma conexão de entrada.
      * É altamente recomendável **NÃO** usar a opção **Ativar expiração de tabela**, pois o DCR não conseguiria ler as fontes após a expiração das tabelas.
   4. Clique no botão <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" />.
4. Conceda as permissões DCR ao conjunto de dados:
   1. No painel **do lado esquerdo**, clique no botão **Exibir ações** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> à direita do conjunto de dados que você criou.
   2. Selecione **Compartilhar.**
   3. No painel que se abre **do lado direito**, clique no botão ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png).
   4. Na seção **Adicionar principais**, insira a seguinte conta no campo **Novos principais**:  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. Na seção **Atribuir funções**, selecione **BigQuery > Visualizador de dados do BigQuery.**

      <Image alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. Clique em ***Salvar***.
   7. Clique em **FECHAR** para fechar o painel do lado direito.

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**Observação:** o procedimento a seguir deve ser executado por um **administrador da conta do Snowflake.**

**Para criar um compartilhamento privado para uso do DCR:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Faça login na conta do Snowflake</Anchor> que contém os dados que você deseja compartilhar com o DCR.
2. Mude sua função para **Accountadmin.**
3. No painel do lado esquerdo, selecione **Compartilhamento privado.**
4. Na página que se abre, selecione a aba **Compartilhado por sua conta** .

   <Image alt="snowflake_private_sharing.png" src="https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png" width="609px" />
5. Clique no botão **Compartilhar**. Na lista que se abre, selecione **Criar um compartilhamento direto.**

   <Image alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />

   <Image alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. Selecione as tabelas e/ou exibições que deseja compartilhar com o DCR e clique em **Concluído.**
7. De acordo com suas necessidades, altere o **Identificador de compartilhamento seguro** e adicione uma descrição opcional.
8. No campo **Adicionar contas na sua região por nome**, insira uma das seguintes contas do Snowflake da AppsFlyer, de acordo com a região da sua conta do Snowflake:

| Região | Conta da AppsFlyer |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Clique no botão **Criar compartilhamento**.

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs" />

### Buckets de armazenamento em nuvem – Amazon S3 e GCS

Você pode usar um ou mais buckets para fazer upload de dados para o DCR (no Amazon S3, GCS ou ambos). No entanto, na maioria dos casos, a estrutura mais fácil de gerenciar inclui um único bucket em um único serviço de nuvem.

* Você pode configurar o mesmo bucket para uso com conexões de entrada e saída seguindo [estas instruções](/docs/data-clean-room-setting-up-cloud-services#configurando-o-mesmo-bucket-de-armazenamento-em-nuvem-para-conexões-de-entrada-e-saída).

<span id="both-cloud-services"></span>Os seguintes requisitos são relevantes para os buckets em ambos os serviços em cloud:

* **Uso:** o bucket deve ser para uso exclusivo do Data Clean Room da AppsFlyer. Em outras palavras, nenhum outro serviço pode escrever dados no bucket.
* **Permissões:** o serviço AppsFlyer DCR deve receber permissões do bucket. Veja instruções para conceder essas permissões nas abas para cada serviço em nuvem abaixo.
* **Nome:** o nome do bucket deve começar com `af-dcr-` ou `af-datalocker-`
  * Exemplo: `af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>**Requisitos de nomenclatura do DCR:** os seguintes requisitos de nomenclatura se aplicam a todas as entidades de dados DCR (buckets, pastas e arquivos):
  * Comprimento máximo: 200 caracteres
  * Caracteres válidos:
    * letras `(A-Z, a-z)`
    * números `(0-9)`,  *não pode ser o primeiro caractere de um nome*
    * hifens `(-)`,  *não pode ser o primeiro caractere de um nome*
    * Caracteres inválidos:
      * espaços
      * todos os outros símbolos ou caracteres especiais
    * Caracteres utilizados apenas para fins especiais:
      * * sinais de igual `(=)`, *somente quando necessário em* datas e nomenclaturas das pastas de versão
        * sublinhado `(_)`, *somente quando utilizado para identificar as partes* <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#file-format">de arquivos GZIP multipartes</Anchor> *ou para nomear* \_SUCCESS files
        * pontos `(.)`, *somente diretamente antes das extensões de nomes de arquivo* `(.csv, .gzip)`

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**Observação:** o seguinte procedimento deve ser realizado por seu administrador AWS.

**Para criar um bucket e conceder permissões da AppsFlyer:**

1. Faça login no console da AWS.
2. Vá para o serviço S3.
3. Crie o bucket:
   1. Clique em **Criar bucket**.
   2. Complete o **Nome do bucket**, começando com `af-dcr-` ou `af-datalocker-` e seguido pelo seu texto (de acordo com os [requisitos de nomenclatura DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) acima).
   3. Clique em **Criar bucket**.
4. <span id="step-4"></span>Conceda permissões de bucket à AppsFlyer:
   1. Selecione o bucket que você criou.
   2. Acesse a aba **Permissões**.
   3. Na seção **Política do bucket**, clique em **Editar.** A janela **Editar política do bucket** é aberta.
   4. <span id="code-snippet"></span>Cole o seguinte code snippet na janela.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
              ]
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-dcr-mybucket",
              "arn:aws:s3:::af-dcr-mybucket/*"
            ]
          }
        ]
      }
      ```
5. No code snippet, substitua *`af-dcr-mybucket`* (nas 2 linhas em que ele aparece) pelo nome do bucket que você criou.  
   **Atenção**! *Ao substituir o nome do bucket no snippet, certifique-se de não escrever* `/*` *sobre a segunda linha em que o nome do bucket aparece.*
6. Clique em **Salvar alterações**.

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**Observação:** o procedimento a seguir deve ser realizado pelo administrador do Google Cloud.

**Para criar um bucket e conceder permissões da AppsFlyer:**

1. Faça login no console do GCS.
2. Vá para a página do Cloud Storage Browser.
3. Crie o bucket:
   1. Clique em **Criar bucket.**
   2. Insira as informações do bucket na página **Criar um bucket** . Inclua o nome do bucket, começando com `af-dcr-` ou `af-datalocker-` e seguido pelo seu texto (de acordo com os [requisitos de nomenclatura DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) acima).
   3. Clique em **Continuar.**
   4. Clique em **Criar.**
4. Conceda permissões de bucket à AppsFlyer:
   1. Selecione o bucket que você criou.
   2. Acesse a aba **Permissões**.
   3. Na seção de permissões, clique em **+ Adicionar.**  
      A janela **Adicionar membros** abre.
   4. Na caixa **Novos membros**, insira a seguinte conta:  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. Na lista **Função**, selecione **Armazenamento em nuvem** > **Administração do armazenamento.**  

      ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
   6. Clique em ***Salvar***.

</Accordion>

<div id="setting-up-cloud-services-for-outbound-connections" />

## Configurando serviços de nuvem para conexões de saída

O DCR entrega relatórios para seus serviços de nuvem selecionados usando o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>.

* **Observação:** para receber relatórios do DCR não é necessário uma assinatura premium do Data Locker. Se você estiver interessado em receber outros relatórios da AppsFlyer por meio do Data Locker, entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsflyer.com).

Seus relatórios DCR podem ser entregues em um ou mais locais em seus serviços de nuvem (independentemente de você usar ou não os mesmos serviços para conexões de entrada). Prepare-os para uso com conexões de saída de acordo com as instruções nas abas a seguir.

<div id="data-warehouses--bigquery-and-snowflake-1" />

### Data warehouses – BigQuery e Snowflake

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

**Observação:** o procedimento a seguir deve ser realizado pelo administrador do Google Cloud.

**Para criar um conjunto de dados e conceder permissões do Data Locker:**

1. Faça login no console do Google Cloud.
2. Acesse a página do BigQuery.
3. Em um projeto novo ou existente do Google Cloud, crie um conjunto de dados para uso exclusivo do Data Locker:
   1. No painel **do lado esquerdo**, clique no botão **Exibir ações** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> à direita do ID do projeto.
   2. Selecione **Criar conjunto de dados.**

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. No painel que se abre **do lado direito**, insira o nome do conjunto de dados e selecione outras opções conforme necessário.
      * Você pode usar qualquer nome que lhe agrade – usando apenas letras, números e sublinhados (\_).
        * **Recomendado:** use um nome que indique que o conjunto de dados está sendo usado para uma conexão de saída.
      * É altamente recomendável **NÃO** usar a opção **Ativar expiração de tabela**, pois o Data Locker não conseguiria gravar relatórios no conjunto de dados após a expiração das tabelas.
   4. Clique no botão <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" />.
4. Conceda permissões do Data Locker ao conjunto de dados:
   1. No painel **do lado esquerdo**, clique no botão **Exibir ações** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> à direita do conjunto de dados que você criou.
   2. Selecione **Compartilhar.**
   3. No painel que se abre **do lado direito**, clique no botão ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png).
   4. Na seção **Adicionar principais**, insira a seguinte conta no campo **Novos principais**:  
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. Na seção **Atribuir funções**, selecione **BigQuery > Editor de dados do BigQuery.**

      <Image alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. Clique em ***Salvar***.
   7. Clique em **FECHAR** para fechar o painel do lado direito.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

O procedimento para preparar o Snowflake para conexões de saída é concluído em combinação com o <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#snowflake-outbound">procedimento para criar a própria conexão de saída</Anchor>.

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs-1" />

### Buckets de armazenamento em nuvem – Amazon S3 e GCS

O procedimento para preparar buckets de armazenamento em nuvem para conexões de saída é muito semelhante ao de prepará-los para [conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#configurando-serviços-de-nuvem-para-conexões-de-entrada) (incluindo as instruções relevantes para ambos os serviços de armazenamento em nuvem).

As instruções nas abas abaixo se aplicam quando você usa um bucket **apenas para conexões de saída.**

* Se você usar o mesmo bucket para conexões de entrada e saída, siga as [instruções especiais para essa configuração](/docs/data-clean-room-setting-up-cloud-services#configurando-o-mesmo-bucket-de-armazenamento-em-nuvem-para-conexões-de-entrada-e-saída).

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

Siga as instruções para criar um [bucket do Amazon S3 para conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (sem alterações nesse procedimento).

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

Siga as instruções para criar um [bucket GCS para conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). Na etapa 4 desse procedimento, insira a seguinte conta na caixa **Novos membros**:  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Accordion>

<div id="setting-up-the-same-cloud-storage-bucket-for-both-inbound-and-outbound-connections" />

## Configurando o mesmo bucket de armazenamento em nuvem para conexões de entrada e saída

Conforme mencionado anteriormente, é comum usar o mesmo bucket no Amazon S3 ou GCS para conexões de entrada e saída.

As instruções para esta configuração variam apenas ligeiramente das [instruções para conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#configurando-serviços-de-nuvem-para-conexões-de-entrada). Eles diferem, no entanto, dependendo se você está:

* criar um novo bucket para uso com conexões de entrada e saída DCR; ***ou***
* modificando um bucket usado anteriormente apenas para Data Locker para um agora usado para conexões DCR de entrada e saída

As instruções para ambos os cenários estão incluídas nas abas abaixo:

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

<div id="creating-a-new-bucket-for-inboundoutbound-connections" />

#### Criando um novo bucket para conexões de entrada/saída

Siga as instruções para criar um [bucket do Amazon S3 para conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (sem alterações nesse procedimento).

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker" />

#### Modificando um bucket existente usado anteriormente apenas para o Data Locker

A modificação de um bucket existente que você usou anteriormente apenas para o Data Locker requer a alteração das permissões do bucket (para permitir o acesso tanto pelo DCR quanto pelo Data Locker).

**Para modificar as permissões do bucket:**

1. Faça login no console da AWS.
2. Vá para o serviço S3.
3. Selecione o bucket usado anteriormente apenas para o Data Locker.
4. Acesse a aba **Permissões**.
5. Na seção **Política do bucket**, clique em **Editar.** A janela **Editar política do bucket** é aberta.
6. **Substitua o conteúdo** da janela pelo seguinte trecho de código:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```

   * No code snippet, substitua *`af-dcr-mybucket`* (nas 2 linhas em que ele aparece) pelo nome do bucket que você criou.
   * **Atenção**! *Ao substituir o nome do bucket no snippet, certifique-se de não escrever* `/*` *sobre a segunda linha em que o nome do bucket aparece.*
7. Clique em **Salvar alterações**.

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

<div id="creating-a-new-bucket-for-inboundoutbound-connections-1" />

#### Criando um novo bucket para conexões de entrada/saída

Siga as instruções para criar um [bucket GCS para conexões de entrada](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). Modifique a etapa 4 desse procedimento para inserir as **2 contas** a seguir na caixa **Novos membros** :  
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker-1" />

#### Modificando um bucket existente usado anteriormente apenas para o Data Locker

A modificação de um bucket existente que você usou anteriormente apenas para o Data Locker requer a alteração das permissões do bucket (para permitir o acesso tanto pelo DCR quanto pelo Data Locker).

**Para modificar as permissões do bucket:**

1. Faça login no console do GCS.
2. Vá para a página do Cloud Storage Browser.
3. Selecione o bucket usado anteriormente apenas para o Data Locker.
4. Acesse a aba **Permissões**.
5. Na seção **Permissões**, clique em **+ Adicionar.**  
   A janela **Adicionar membros** abre.
6. Na caixa **Novos membros**, insira a seguinte conta:  
   `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. Na lista **Função**, selecione **Armazenamento em nuvem** > **Administração do armazenamento.**  

   ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
8. Clique em ***Salvar***.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=vis%C3%A3o-geral h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=observa%C3%A7%C3%A3o supported-cloud-services=servi%C3%A7os-de-nuvem-compat%C3%ADveis h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=servi%C3%A7os-de-nuvem-compat%C3%ADveis h_01J6Y2P4CM8VDWCD5XH91DJPYX=importante setting-up-cloud-services-inbound=configurando-servi%C3%A7os-de-nuvem-para-conex%C3%B5es-de-entrada h_01J6Y2P4CM61DEXMWB626X25TT=configurando-servi%C3%A7os-de-nuvem-para-conex%C3%B5es-de-entrada data-warehouses-inbound=data-warehouses--bigquery-e-snowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=data-warehouses--bigquery-e-snowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs h_01J6Y2P4CMCJDT2W6C52MF71TB=buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound setting-up-cloud-services-outbound=configurando-servi%C3%A7os-de-nuvem-para-conex%C3%B5es-de-sa%C3%ADda h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=configurando-servi%C3%A7os-de-nuvem-para-conex%C3%B5es-de-sa%C3%ADda data-warehouses-outbound=data-warehouses--bigquery-e-snowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=data-warehouses--bigquery-e-snowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=configurando-o-mesmo-bucket-de-armazenamento-em-nuvem-para-conex%C3%B5es-de-entrada-e-sa%C3%ADda h_01J6Y2P4CN2ARMJKRSAFZNN59G=configurando-o-mesmo-bucket-de-armazenamento-em-nuvem-para-conex%C3%B5es-de-entrada-e-sa%C3%ADda h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=criando-um-novo-bucket-para-conex%C3%B5es-de-entradasa%C3%ADda h_01J6Y2P4CN216K0VZSWRP699TF=criando-um-novo-bucket-para-conex%C3%B5es-de-entradasa%C3%ADda modifying-an-existing-bucket-previously-used-only-for-data-locker=modificando-um-bucket-existente-usado-anteriormente-apenas-para-o-data-locker h_01J6Y2P4CNDW888XTMKAMZAFCS=modificando-um-bucket-existente-usado-anteriormente-apenas-para-o-data-locker h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=criando-um-novo-bucket-para-conex%C3%B5es-de-entradasa%C3%ADda-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=criando-um-novo-bucket-para-conex%C3%B5es-de-entradasa%C3%ADda-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=modificando-um-bucket-existente-usado-anteriormente-apenas-para-o-data-locker-1 h_01J6Y2P4CNYCTVGN6CH0748S24=modificando-um-bucket-existente-usado-anteriormente-apenas-para-o-data-locker-1" />
