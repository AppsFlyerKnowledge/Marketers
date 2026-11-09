---
title: Data Locker—configuração de serviços de nuvem
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2026-08-19T00:04:46Z'
  id: 360017603577
  locale: pt
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/pt/articles/360017603577
---
> **Resumo**: configure seu serviço de nuvem para receber dados do Data Locker: GCS, AWS, BigQuery ou Snowflake.

O Data Locker permite que você transmita dados para sua solução de armazenamento selecionada e solução própria, seja um bucket ou data warehouse. Configure seu serviço de nuvem seguindo um dos procedimentos abaixo.

<div id="bucket-cloud-storage" />

## Armazenamento em nuvem com bucket

<div id="gcs-storage" />

<Accordion title="Armazenamento GCS">

Antes de começar, observe o seguinte:

* Esse procedimento deve ser realizado pelo seu administrador do Google Cloud.
* Você pode excluir arquivos do Data Locker que foram registrados após 25 horas ou mais. Não os exclua antes.

**Informações para o administrador do GCS**

O Data Locker é a solução da AppsFlyer para a transmissão de dados para armazenamento.

**Requisitos**

* Crie um bucket no GCS para uso exclusivo do Data Locker. Exclusivo significa que nenhum outro serviço pode registrar dados nesse bucket.
* Nome sugerido para o bucket: `af-datalocker`.
* Conceda permissões do Data Locker usando o procedimento a seguir.

**Para conceder permissões no Data Locker:**

Nesse procedimento, substitua `data-locker-example` usando o nome do bucket que você criou anteriormente para o Data Locker.

1. Faça login em seu console do GCS.
2. Vá para **Storage** > **Storage**browser.

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png" />
3. Selecione o bucket que você criou anteriormente, por exemplo, `data-locker-example`.
4. Acesse a aba **Permissions**.
5. Clique em **+Add**.  
   A janela para adicionar membros é aberta.
6. Preencha da seguinte forma:
   1. **Novos membros**, cole o trecho a seguir.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. Selecione uma função: **Cloud storage** > **Storage Object Admin**.

      <Image align="center" alt="mceclip0.png" src="https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png" />
7. Clique em **Save**.

</Accordion>

<div id="aws-storage" />

<Accordion title="Armazenamento da AWS">

Antes de começar, observe o seguinte:

* Esse procedimento deve ser executado pelo seu administrador da AWS.
* Você pode excluir arquivos do Data Locker que foram registrados após 25 horas ou mais. Não os exclua antes.

**Informações para o administrador da AWS**

O Data Locker é a solução da AppsFlyer para a transmissão de dados para armazenamento.

**Requisitos**

* Criar um bucket da AWS com o nome de af-datalocker-mybucket. O prefixo af-datalocker- é obrigatório. O sufixo é de texto livre.
* Sugerimos af-datalocker-aaaa-mm-dd-hh-mm-texto-livre. Onde aaaa-mm-dd-hh-mm é a data e hora atuais, e você adiciona qualquer outro texto que desejar, conforme descrito na figura a seguir.

**Interface do usuário no console da AWS**

<Image align="center" alt="MyBucket.jpg" src="https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg" />

Depois de criar o bucket, conceda permissões para a AppsFlyer usando o procedimento a seguir.

**Para criar um bucket e conceder permissões da AppsFlyer:**

1. Faça login no console da AWS.
2. Vá para o serviço S3.
3. **Para criar o bucket**:
   1. Clique em **Create bucket**.
   2. Preencha o **Bucket name** da seguinte forma: Comece com **e depois adicione qualquer outro texto conforme descrito anteriormente.**
   3. Especifique uma das regiões [disponíveis no AWS](#regiões-disponíveis-no-aws).
   4. Clique em **Create bucket.**
4. **Para conceder permissões à AppsFlyer:**
   1. Selecione o bucket.
   2. Vá para **Permissions**.
   3. Na seção **Política de bucket**, clique em **Editar**.   
      A janela Bucket policy se abre.
   4. Cole o seguinte snippet na janela.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. No snippet, substitua `af-data-locker-my-bucket` pelo nome do bucket que você criou.
6. [Opcional] Adicione suporte para buckets criptografados KMS. Para isso, em **Key Policy**, selecione Switch to policy view e cole o seguinte snippet em Statement array.

   ```json
   {
         "Sid": "Allow use of the key",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     },
   ```
7. Clique em **Save changes**.
8. Conclua o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">procedimento de configuração do Data Locker.</Anchor>

<div id="supported-aws-regions" />

#### **Regiões disponíveis no AWS**

No AWS, o Data Locker funciona nas seguintes regiões:

* Ásia-Pacífico (Tóquio): `ap-northeast-1`
* Ásia-Pacífico (Seul): `ap-northeast-2`
* Ásia-Pacífico (Mumbai): `ap-south-1`
* Ásia-Pacífico (Cingapura): `ap-southeast-1`
* Ásia-Pacífico (Sydney): `ap-southeast-2`
* Canadá (Central): `ca-central-1`
* UE (Frankfurt): `eu-central-1`
* UE (Irlanda): `eu-west-1`
* UE (Londres): `eu-west-2`
* América do Sul (São Paulo): `sa-east-1`
* Leste dos EUA (N. Leste dos EUA (N. Leste dos EUA (Virgínia do Norte): `us-east-1`
* Leste dos EUA (Ohio): `us-east-2`
* Oeste dos EUA (N. Oeste dos EUA (N. Oeste dos EUA (Califórnia do Norte): `us-west-1`
* Oeste dos EUA (Oregon): `us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Azure storage">

Antes de começar, observe o seguinte:

* O procedimento deve ser feito pelo administrador do Azure Cloud.
* Você pode excluir arquivos do Data Locker que foram registrados após 25 horas ou mais. Não os exclua antes.

**Informações para o administrador do Azure**

O Data Locker é a solução da AppsFlyer para o envio de dados para a sua conta de armazenamento.

**Para definir uma conta de armazenamento para o Data Locker:**

1. No seu portal Azure, vá para [Azure storage accounts.](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) e clique em <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Create** para criar uma nova conta de armazenamento e extrair dados da Appsflyer.
2. **Na aba** Basic **-> Project details**, selecione a partir das opções:
   1. Um **Subscription.**
   2. Um **Resource Group.**  
      Opcional: se não houver nenhum grupo de recursos, clique em **Create new** para criar um novo.
3. Em **Instance details:**
   1. Digite um **nome para a conta de armazenamento.**
   2. Selecione uma **região** no menu suspenso.
4. Clique em **Next: Advanced >**
5. Na aba **Security**, selecione **Enable Hierarchical namespace.**
6. Clique em Review -> Create.
7. [Feito isso, volte para](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) suas contas de armazenamento do Azure e selecione a conta recém-criada.
8. Vá para **Access keys** e copie seu **nome da conta de armazenamento** e uma das suas **chaves**.
9. Vá para **Storage browser -> Blob containers** e clique em <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Adicionar contêiner.**
   1. Digite um **nome** para o novo container.
   2. Clique em **Create.**
10. Feito isso, na AppsFlyer, vá para Data Locker **-> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />Nova conexão.**
11. Na nova conexão:
    1. escolha um nome para a sua conexão.
    2. Selecione **Azure Blob.**
    3. Digite o **nome do container** do Azure no campo **nome do bucket** (que você criou na etapa 9).
    4. Digite seu **nome da conta de armazenamento** copiado da etapa 8.
    5. Digite a **chave** que você copiou na etapa 8.
    6. Clique em **Testar conexão**.
    7. **Salve.**

</Accordion>

<div id="yandex" />

<Accordion title="[Beta] Yandex Cloud storage">

Antes de começar, observe o seguinte:

* O procedimento nesta seção precisa ser executado pelo administrador do Yandex Cloud.
* Você pode excluir arquivos do Data Locker que foram registrados após 25 horas ou mais. Não os apague antes.

**Informações para o administrador do Yandex**

O Data Locker é a solução da AppsFlyer para a transmissão de dados para armazenamento.

**Para criar um bucket e conceder permissões do Data Locker:**

1. No <Anchor target="_blank" href="https://console.cloud.yandex.com/">console do Yandex Cloud</Anchor>, vá para a aba **Contas de serviço** e clique em **Criar conta de serviço**.
2. Dê um nome para a conta, por exemplo, `af-datalocker`.
3. Crie uma chave de acesso estática para a conta de serviço. Na conta de serviço:
   1. Clique em **Create a new key**.
   2. Selecione**Create static access key**.
   3. Salve o **Key ID** e a **Secret Key**.
4. Conceda a permissão **storage.editor** à sua nova conta de serviço .
   1. Nas configurações do bucket, vá para **Acessar vínculos** (Access Bindings) e clique em **Atribuir vínculos** (Assign bindings).
   2. Para sua nova conta de serviço, adicione a função **storage.editor** e clique em **Salvar**.
5. Entre em contato com seu CSM da AppsFlyer para habilitar o Yandex no Data Locker.
6. Depois de ativado, use o ID da chave e a chave secreta durante <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">a configuração do Data Locker</Anchor>.

</Accordion>

<div id="data-warehouse-cloud-storage" />

## Armazenamento em nuvem com data warehouse

<div id="bigquery" />

<Accordion title="BigQuery">

Esse procedimento deve ser feito pelo administrador do BigQuery.

**Informações para o administrador do BigQuery**

O Data Locker é a solução da AppsFlyer para a transmissão de dados para armazenamento.

**Requisitos**

* Criar um conjunto de dados do BigQuery

**Para criar um conjunto de dados do BigQuery:**

1. No BigQuery, crie um projeto ou use um projeto existente.
2. No projeto, clique em **CREATE DATASET**. [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Forneça um ID adequado para o conjunto de dados.

   <div id="note" />

   > 📘 **Nota**
   >
   > certifique-se de que o projeto ou dataset de destino esteja vinculado a uma conta de cobrança ativa. Sem uma conta de cobrança, o Data Locker não pode criar ou gravar em tabelas no BigQuery, e o processo de configuração da conexão pode falhar.

4. Conceda à AppsFlyer o acesso ao conjunto de dados. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Veja as instruções do BigQuery</Anchor>
   * Para **Add principal**, use o seguinte usuário da AppsFlyer: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * Em **Assign roles**, selecione BigQuery Data Editor.
5. Conclua as configurações restantes conforme solicitado.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Conecte o Data Locker à sua conta Snowflake. Ao fazer isso, os dados são enviados para o Snowflake e continuam disponíveis no armazenamento em nuvem selecionado.

**Considerações para desenvolvedores de BI**

* A taxa de atualização de dados é a mesma dos dados fornecidos em um bucket.
* A estrutura de tabela e coluna dos dados é equivalente àquela encontrada nos dados disponíveis diretamente em um bucket de Data Locker.
* À medida que as linhas são adicionadas ao compartilhamento do Snowflake, a coluna `_ingestion_time` é preenchida no fuso horário local do sistema (não UTC). Para garantir a exclusividade da linha e evitar a ingestão da mesma linha mais de uma vez:
  1. Salve o `max_ingestion_time` por tabela ingerida.
  2. Sempre que executar seu processo de ingestão, faça a ingestão apenas de linhas onde `_ingestion_time > max_ingestion_time`

Conclua os procedimentos a seguir para conectar o Snowflake ao Data Locker.

<div id="snowflake-connector-procedures" />

#### **Procedimentos do conector Snowflake**

**Para obter o ID e a região da sua conta Snowflake**:

1. No Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">faça login na sua conta</Anchor>.
2. Na barra de menus, selecione seu nome.  
   O ID da sua conta e a região são exibidas.

   <Image align="center" alt="Snowflake account details" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />

**Para conectar o Data Locker ao Snowflake**:

1. Na AppsFlyer, acesse **relatórios** > **Data Locker**.
2. Selecione Snowflake.
3. Insira a região e o localizador da conta Snowflake usando as informações que você recebeu anteriormente do Snowflake.
4. Clique em **Salvar**.

**Para** **criar um banco de dados a partir de um compartilhamento no Snowflake**:

1. No Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">faça login na sua conta</Anchor>.
2. Mude a função para **Accountadmin**. Consulte <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share.">Criar um banco de dados a partir de um compartilhamento.</Anchor>
3. Selecione **Shares**.
4. Selecione o compartilhamento da AppsFlyer. Por exemplo, APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Clique em **Create Database from Secure Share** e preencha com os detalhes necessários. **Atenção**! Você deve carregar os dados do banco de dados compartilhado em suas tabelas, pois os dados no banco de dados compartilhado só estão disponíveis por um período limitado (atualmente 14 dias).
6. Em seu banco de dados, as tabelas importadas são exibidas. Os nomes e estruturas das tabelas são equivalentes aos dos buckets do Data Locker.

</Accordion>

<div id="traits-and-limitations" />

## Características e Limitações

| Caraterística | A descrição |
| --- | --- |
| Conexão com a nuvem da AppsFlyer | Relatórios não podem ser armazenados em formato descompactado |
| Mudança de localização do dataset do BigQuery | Se você mudar a localização do dataset no BigQuery, você precisa salvar novamente a sua conexão na AppsFlyer. Como nenhuma mudança real na configuração é exigida nas configurações de conexão da AppsFlyer, o botão **salvar** não é exibido. Para ativar o botão, faça uma alteração temporária, salve a conexão, e depois reverta a alteração e salve a conexão novamente. |
| Regiões com suporte para Snowflake | **Regiões com suporte para AWS:**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-south-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**Regiões com suporte para Azure:**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>west-europe</li><li>west-us-2</li></ul>**Regiões com suporte para GCP**<ul><li>Suporte limitado. Entre em contato com o suporte do AppsFlyer para verificar a disponibilidade para a sua região.</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=armazenamento-em-nuvem-com-bucket h_01HE2SPKYZWFXA63YD5NK4KJRD=armazenamento-em-nuvem-com-bucket h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=regi%C3%B5es-dispon%C3%ADveis-no-aws h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=regi%C3%B5es-dispon%C3%ADveis-no-aws %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=armazenamento-em-nuvem-com-data-warehouse h_01HE2SPKYZ77X8WP9ZNRB1D05B=armazenamento-em-nuvem-com-data-warehouse h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=nota h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=procedimentos-do-conector-snowflake h_01HE2SPKYZ11B1MJYX2HRCS07D=procedimentos-do-conector-snowflake traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KYVRP8CVMD01EZY5561W2RCJ=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
