---
title: Plataforma de colaboração de dados (DCP) - Configure seus serviços na nuvem
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
  created_at: '2024-04-28T14:01:34Z'
  edited_at: '2026-08-18T00:07:19Z'
  id: 24604528827921
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/24604528827921
---
> **Em resumo:** Configure seus serviços na nuvem para que você possa conectar seus dados de fonte à DCP e exportar audiências para seus buckets de armazenamento na nuvem.

## Sobre a configuração de serviços em nuvem

A DCP usa dois tipos de conexões para mover dados entre seus serviços na nuvem e a plataforma:

* **Conexões de fonte:** Permitem que você conecte seus dados próprios à DCP para colaboração e criação de audiências.
* **Conexões de armazenamento na nuvem:** Permitem que você exporte suas audiências para seus buckets de armazenamento na nuvem após cada atualização de audiência.

A configuração de uma conexão é um processo de duas etapas:

* **Etapa 1:** Use a interface do seu serviço em nuvem para prepará-lo para uso com a DCP.
* **Etapa 2:** Conecte-o à DCP na plataforma AppsFlyer. Consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections">Data Collaboration Platform (DCP) - Adicionar conexões</Anchor>.

A tabela abaixo mostra quais serviços têm suporte para cada tipo de conexão:

| Serviços na nuvem | Fonte (entrada) | Armazenamento em nuvem (saída) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

Para Amazon S3 e GCS, a mesma configuração e as mesmas permissões de bucket se aplicam tanto às conexões de fonte quanto às de armazenamento em nuvem, portanto não é necessária uma configuração separada para cada direção. A criação de uma conexão de fonte cria automaticamente uma conexão correspondente de armazenamento em nuvem (e vice-versa), e excluir uma exclui a outra, já que na prática é uma única conexão subjacente compartilhada entre as duas abas.

## Configure seus cloud services

Selecione abaixo seu serviço em nuvem para ver as instruções de configuração.

<div id="amazon-s3" />

<Accordion title="Amazon S3">

Use as instruções a seguir para preparar um bucket do Amazon S3 para uso com a DCP.

> 📘 **Atenção**
>
> O procedimento a seguir deve ser realizado pelo seu administrador da AWS.

**Para criar um bucket:**

1. Faça login no console da AWS.
2. Vá para o serviço S3.
3. Crie o bucket:
   1. Clique em **Create bucket**.
   2. Preencha o **Nome do bucket**, começando com `af-dcr-`

       e seguido pelo seu texto, de acordo com os [requisitos de nomenclatura do DCR](#dcr-naming-requirements).
   3. Clique em **Create bucket**.

**Para conceder permissões ao bucket da AppsFlyer:**

1. Selecione o bucket que você criou.
2. Acesse a aba **Permissões**.
3. Na seção **Política do bucket**, clique em **Editar**. A janela **Editar política do bucket** é aberta.
4. Cole o seguinte code snippet na janela:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [
             "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",
             "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
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
5. No snippet, substitua `af-dcr-mybucket` (nas duas linhas em que ele aparece) pelo nome do bucket que você criou.
6. Vá para qualquer uma das seções e selecione a opção desejada.

> 🚧 **Importante!**
>
> Ao substituir o nome do bucket no snippet, não substitua `/*` na segunda linha em que o nome do bucket aparece.

</Accordion>

<div id="google-cloud-storage-gcs" />

<Accordion title="Google Cloud Storage (GCS)">

Use as instruções a seguir para preparar um bucket do GCS para uso com o DCP.

> 📘 **Atenção**
>
> O procedimento a seguir deve ser realizado pelo administrador do Google Cloud.

**Para criar um bucket:**

1. Faça login em seu console do GCS.
2. Vá para a página do Cloud Storage Browser.
3. Crie o bucket:
   1. Clique em **Create bucket**.
   2. Insira as informações do bucket na página **Criar um bucket**. Inclua o nome do bucket, começando com `af-dcr-`

       e seguido pelo seu texto, de acordo com os [requisitos de nomenclatura do DCR](#dcr-naming-requirements).
   3. Clique em **continuar.**
   4. Clique em **criar**.

**Para conceder permissões ao bucket da AppsFlyer:**

1. Selecione o bucket que você criou.
2. Acesse a aba **Permissões**.
3. Na seção **Permissões**, clique em **+ Adicionar**. A janela **Adicionar membros** é aberta.
4. Na caixa **Novos membros**, insira as seguintes contas:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   * `af-data-delivery@af-raw-data.iam.gserviceaccount.com`
5. Na lista **Função**, selecione **Cloud storage** > **Administrador do armazenamento**.
6. Clique em **Guardar**.

</Accordion>

<div id="bigquery" />

<Accordion title="BigQuery">

O BigQuery oferece suporte apenas a conexões de fonte. Use as instruções a seguir para criar um conjunto de dados e conceder permissões à AppsFlyer.

> 📘 **Atenção**
>
> O procedimento a seguir deve ser realizado pelo administrador do Google Cloud.

**Para criar um conjunto de dados:**

1. Faça login no console do Google Cloud.
2. Acesse a página do BigQuery.
3. Em um projeto novo ou existente do Google Cloud, crie um conjunto de dados para uso exclusivo do DCP:
   1. No painel do lado esquerdo, clique no ícone de menu de três pontos (**Exibir ações**) à direita do ID do projeto.
   2. Selecione **Criar conjunto de dados**.
   3. No painel que se abre do lado direito, insira o nome do conjunto de dados e selecione outras opções conforme necessário.
      * Você pode usar qualquer nome: apenas letras, números e sublinhados.
        * **Recomendado:** use um nome que indique que o conjunto de dados está sendo usado para uma conexão de fonte.
      * Não use a opção **Ativar expiração de tabela**, pois o DCP não conseguirá ler seus dados após a expiração das tabelas.
   4. Clique em **Criar conjunto de dados**.

**Para conceder permissões à AppsFlyer no conjunto de dados:**

1. No painel do lado esquerdo, clique no ícone de menu de três pontos (**Exibir ações**) à direita do conjunto de dados que você criou.
2. Selecione **Compartilhar**.
3. No painel que se abre do lado direito, clique em **Adicionar entidade**.
4. Na seção **Adicionar entidades**, insira a seguinte conta no campo **Novas entidades**:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
5. Na seção **Atribuir funções**, selecione **BigQuery** > **Visualizador de dados do BigQuery**.
6. Clique em **Guardar**.
7. Clique em **Fechar** para fechar o painel do lado direito.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

O Snowflake oferece suporte apenas a conexões de origem. Use as instruções a seguir para criar um compartilhamento privado para uso pelo DCP.

> 📘 **Atenção**
>
> O procedimento a seguir deve ser realizado por um **Accountadmin** do Snowflake.

**Para criar um compartilhamento privado:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Faça login na conta do Snowflake</Anchor> que contém os dados que você deseja compartilhar com o DCP.
2. Altere sua função para **Account admin**.
3. No painel do lado esquerdo, selecione **Compartilhamento privado**.
4. Na página que se abre, selecione a aba **Compartilhado pela sua conta**.
5. Clique em **Compartilhar**. Na lista que se abre, selecione **Criar um compartilhamento direto**.
6. Selecione as tabelas e/ou exibições que você deseja compartilhar com o DCP e clique em **Concluído**.
7. Altere o **Identificador de compartilhamento seguro** e adicione uma descrição opcional, conforme necessário.
8. No campo **Adicionar contas na sua região por nome**, insira a conta do Snowflake da AppsFlyer para a sua região:

| Região | Conta da AppsFlyer |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Clique em **Criar compartilhamento**.

</Accordion>

<div id="salesforce-cloudcrm" />

<Accordion title="Salesforce Cloud/CRM">

O Salesforce Cloud/CRM dá suporte somente a conexões de fonte. Consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">DCP - Integração com o Salesforce Data Cloud</Anchor> para obter instruções de configuração.

</Accordion>

## Especificações e limitações

| Caraterística | Descrição |
| --- | --- |
| Serviços de nuvem compatíveis | O Amazon S3 e o GCS dão suporte a conexões de fonte e de armazenamento em nuvem. O BigQuery, o Snowflake e o Salesforce Cloud/CRM dão suporte somente a conexões de fonte. |
| Uso do bucket | Os buckets do S3 e do GCS devem ser de uso exclusivo do DCP. Nenhum outro serviço pode escrever dados no bucket. |
| <span id="dcr-naming-requirements"></span>Requisitos de nomenclatura do DCR | Os seguintes requisitos de nomenclatura se aplicam a todas as entidades de dados do DCR, incluindo buckets, pastas e arquivos:<ul><li>**Comprimento máximo:** 200 caracteres</li><li>**Caracteres válidos:** letras (A-Z, a-z), números (0-9), hífens (-)</li><li>**Caracteres inválidos:** espaços e todos os outros símbolos ou caracteres especiais</li><li>Números e hífens não podem ser o primeiro caractere de um nome</li><li>**Somente caracteres de propósito específico:**<ul><li>Sinais de igual (=): somente em <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">nomes de pastas de data e versão</Anchor></li><li>Sublinhados {"(_):"} somente em <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#file-format">nomes de arquivos GZIP com várias partes</Anchor> ou em arquivos <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#_success-files">{"_SUCCESS"}</Anchor></li><li>Pontos (.): somente imediatamente antes das extensões de nome de arquivo (.csv, .gzip)</li></ul></li></ul> |
| Nomenclatura do bucket | Os nomes dos buckets devem começar com `af-dcr-` seguido do seu texto. Exemplo: `af-dcr-example-bucket`. |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections">DCP - Adicionar conexões</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP - Crie e ative audiências</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">DCP - Criar e gerenciar fontes</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-guide">Plataforma de colaboração de dados (DCP) - Guia</Anchor>

<div data-zendesk-anchors="about-cloud-service-setup=sobre-a-configura%C3%A7%C3%A3o-de-servi%C3%A7os-em-nuvem h_01KY1VRHDTX2W1YC4QX1N093GF=sobre-a-configura%C3%A7%C3%A3o-de-servi%C3%A7os-em-nuvem set-up-your-cloud-services=configure-seus-cloud-services h_01KY1VRHDT63WWBPNNN3QC9N49=configure-seus-cloud-services h_01KY1VRHDT2GRP2MMYTKFNRN3P=amazon-s3 h_01KY1VRHDTYMG39CRENZC971RS=aten%C3%A7%C3%A3o h_01KY1VRHDVV1ZHTVV5SXGXRZ59=importante h_01KY1VRHDVS3S0F22T0EQ5MCKY=google-cloud-storage-gcs h_01KY1VRHDVX4KYCT627NN92TCT=aten%C3%A7%C3%A3o-2 h_01KY1VRHDVR3CZAZK0PGXDBWRC=bigquery h_01KY1VRHDV8Q3TRG7TBM5TRDYM=aten%C3%A7%C3%A3o-2 h_01KY1VRHDVSE9WJSDFXYV7W2R3=snowflake h_01KY1VRHDVDDK9B8Y7DKA5GA75=aten%C3%A7%C3%A3o-3 h_01KY1VRHDV9PJQMAGBY52G9RS8=salesforce-cloudcrm traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KY1VRHDVT3PYP5QVKNKQ803G=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KY1VRHDVEWNCDKZYCGWD1SRM=consulte-tamb%C3%A9m" />
