---
title: Plataforma de colaboração de dados (DCP) - Adicionar conexões
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-08-19T00:06:38Z'
  id: 24603890457617
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/24603890457617
---
> **Resumo:** Configure as conexões da DCP para integrar suas fontes de dados, enriquecer seus dados e exportar audiências para armazenamento na nuvem e parceiros de mídia.

<div id="about-dcp-connections" />

## Sobre as conexões da DCP

As conexões determinam como a DCP ingere seus dados e exporta suas audiências. Depois de <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configurar seus serviços na nuvem</Anchor>, conecte-os à DCP usando o modal **Gerenciar conexões**. Estes são os tipos de conexão disponíveis:

* [**Conexões de fontes**](#create-source-connections): para integrar seus dados first-party à DCP a partir do armazenamento na nuvem ou de um data warehouse.
* [**Conexões de armazenamento na nuvem**](#create-cloud-storage-connections): para exportar suas audiências para seus buckets do Amazon S3 ou do Google Cloud Storage (GCS).
* [**Conexões com parceiros de mídia**](#create-media-partner-connections): para enviar suas audiências às plataformas de anúncios para ativação.
* [**Conexões de dados e identidade**](#create-data-identity-connections): para unificar dados de usuário fragmentados, melhorar as taxas de correspondência e expandir audiências do parceiro.

A DCP é compatível com diferentes serviços na nuvem de acordo com o tipo de conexão. Consulte a tabela abaixo para ver quais serviços você pode usar para cada tipo de conexão:

| Serviços na nuvem | Fonte (entrada) | Exportação do armazenamento na nuvem (saída) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

No Amazon S3 e no Google Cloud Storage, uma única conexão funciona como fonte (entrada) e destino de exportação do armazenamento na nuvem (saída). Ao criar uma conexão de origem para o S3 ou o GCS, você também cria automaticamente uma conexão correspondente de armazenamento na nuvem (exportação), e vice-versa.

<div id="create-source-connections" />

<Accordion title="Criar conexões de origem">

Crie conexões de origem para integrar dados first-party à DCP.

**Para criar uma conexão de origem:**

1. Na AppsFlyer, vá para **Colaborar** > **Data Clean Room.**
2. Clique em **Gerenciar conexões** no canto superior à direita.
3. Acesse a aba **Fonte** e clique em **+ Nova conexão**.  
   <Image alt="2026-07-27_13-30-46.png" src="https://files.readme.io/dec879432c0b9d6ba4eeec2c175dfce145c99652ccabb02d37f3434627f9310f-49189748198289.png" width="529px" />
4. Continue com as [instruções sobre as conexões de serviços na nuvem para dados de origem](#conexões-dos-serviços-na-nuvem-para-dados-de-origem) abaixo.

Você também pode criar uma conexão de origem ao configurar uma fonte. Veja como <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">criar e gerenciar fontes</Anchor> para obter mais instruções.

<div id="note" />

> 📘 **Atenção**
>
> Ao criar uma conexão de origem de entrada para o S3 ou o GCS, você também cria automaticamente uma conexão de saída correspondente de armazenamento na nuvem (e vice-versa). Ao excluir uma conexão do Amazon S3 ou do GCS, você também exclui automaticamente a outra. Como se trata de uma conexão subjacente, ao removê-la de qualquer uma das abas, você também a remove de todos os locais onde é usada.

<div id="cloud-service-connections-for-source-data" />

#### Conexões dos serviços na nuvem para dados de origem

As conexões de origem servem para conectar seus dados de origem à DCP com segurança. Na caixa de diálogo **Nova conexão**, selecione seu serviço na nuvem e preencha os detalhes do seu provedor:

**BigQuery:** Na caixa de diálogo **Nova conexão**, insira o **ID do projeto** do BigQuery para o projeto que contém seus dados de origem. Você pode encontrá-lo na página do BigQuery do seu Google Cloud Console.

**Snowflake:** Na caixa de diálogo **Nova conexão**, insira o **ID da conta do Snowflake** e a **região** da conta que contém seus dados de origem. Para encontrá-los, clique no nome da conta na parte inferior à esquerda do seu console do Snowflake:

**ACCOUNTADMIN** > **Conta** > passe o mouse sobre a conta correspondente > **Copiar identificador da conta**. Consulte a <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">documentação do Snowflake</Anchor> para obter mais detalhes.

<div id="important" />

> 🚧 **Importante!**
>
> Busque o ID com a etiqueta **Locator**. **Não é** o mesmo ID usado para criar conexões de saída do Snowflake.

**Amazon S3 e GCS:** Na caixa de diálogo **Nova conexão**, insira o nome do <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">bucket que você criou</Anchor> para uso exclusivo do Data Clean Room (DCR) da AppsFlyer.

**Salesforce Cloud/CRM:** Veja <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">como configurar uma conexão com o Salesforce</Anchor>.

<div id="local-file-connection" />

#### Conexão de arquivo local

As conexões de arquivos locais permitem que você carregue arquivos de dados do seu computador para a DCP. Essa opção costuma ser usada apenas para testes e não é recomendada para uma ingestão de dados contínua ou em grande escala.

<div id="set-up-a-local-file-connection" />

<Accordion title="Configurar uma conexão de arquivo local">

Uma conexão de arquivo local é usada para testar a plataforma com um arquivo de exemplo. Ela permite que você se familiarize com os recursos da DCP antes de começar a compartilhar dados. Lembre-se: ela não é recomendada para o compartilhamento de dados, tem um período de retenção de dados limitado a 14 dias e não aceita processos de automação.

Uma conexão de arquivo local pode ser <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-da-fonte-como-arquivos-locais">configurada durante a criação da fonte</Anchor>.

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="Criar conexões de armazenamento na nuvem">

As conexões de armazenamento na nuvem permitem que você exporte automaticamente suas audiências da DCP para seu bucket do Amazon S3 ou do Google Cloud Storage (GCS) após cada atualização de audiência.

**Para criar uma conexão de armazenamento na nuvem:**

1. Na AppsFlyer, vá para **Colaborar** > **Data Clean Room.**
2. Clique em **Gerenciar conexões** no canto superior à direita.
3. Acesse a aba **Armazenamento na nuvem** e clique em **+ Nova conexão**.  
   <Image alt="2026-07-27_13-30-34.png" src="https://files.readme.io/1da10127617317d0ff466433c89712d78c104b6a943b4b669e1d7180d22df958-49189843742609.png" width="533px" />
4. Você verá o modal **Nova conexão de armazenamento na nuvem**.
5. No modal **Nova conexão de armazenamento na nuvem**, selecione seu provedor de nuvem: **Google Cloud Storage** ou **Amazon Simple Storage**.
6. Insira o nome do seu bucket:
   * **GCS:** Insira o nome do bucket do GCS no formato `gs://my-bucket`.
   * **S3:** Insira o nome do bucket do S3.
7. Clique em **Testar conexão** para verificar se a DCP consegue se conectar ao seu bucket.
8. Clique em **Salvar**. A nova conexão aparece em **Suas conexões de armazenamento na nuvem** na aba **Armazenamento na nuvem**.

Você também pode criar uma conexão de armazenamento na nuvem a partir do criador de audiências. Veja como <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">criar e ativar audiências</Anchor> para obter as instruções.

<div id="understand-export-path" />

<Accordion title="Conhecer o caminho de exportação">

Cada vez que uma audiência é exportada, a DCP grava essa audiência no seu bucket usando um caminho fixo e previsível:

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**Exemplo de conteúdo da pasta para uma entrega:**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/\n  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv\n  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv\n  └── _SUCCESS
```

| Segmento do caminho | O que significa |
| --- | --- |
| **Etapa 1&lt;bucket>:** | Seu bucket conectado do S3 ou do GCS. |
| dcp-output/audiences/ | Pasta fixa que a DCP cria automaticamente para todas as exportações de audiência. |
| Etapa 1: | O ID exclusivo da colaboração a que pertence essa audiência. Você pode encontrá-lo no URL de colaboração na DCP. |
| t=\_ | O nome da audiência (espaços e caracteres especiais substituídos por sublinhados) + um ID exclusivo. Isso garante que uma audiência excluída e recriada com o mesmo nome nunca substitua nem gere conflitos com os arquivos mais antigos. |
| dt= | A data de entrega. |
| v= | Um número de versão para as exportações dessa audiência. Ele aumenta a cada nova entrega. |
| part-NNNNN--c000.csv | Um dos arquivos de saída para a entrega; consulte “Formato do arquivo e divisão” mais abaixo. |
| \_SUCCESS | Um arquivo marcador vazio criado quando a exportação termina de gravar todos os arquivos parciais. |

<div id="note-1" />

> 📘 **Atenção**
>
> Esta estrutura de pastas é criada e gerenciada automaticamente. Não mude o nome nem a estrutura manualmente. Qualquer processo automatizado que leia estes arquivos deve seguir este padrão de caminho e esperar que \_SUCCESS apareça antes de processar os arquivos parciais, evitando a leitura de uma entrega incompleta.

**Formato de arquivo e divisão**

* As audiências são sempre exportadas como arquivos CSV, não compactados, com duas colunas: `value` (o identificador) e `taxonomy` (o tipo de identificador).
* Audiências maiores podem ser entregues como vários arquivos em vez de apenas um, numerados como `part-00000`, `part-00001`, etc. Por padrão, cada arquivo contém até aproximadamente 500.000 linhas. Por padrão, cada arquivo contém até aproximadamente 500.000 linhas.
* Um único arquivo pode conter uma combinação de tipos de identificador nas mesmas linhas. Filtre usando a coluna `taxonomy` para os identificadores necessários. Os valores comuns de taxonomia incluem `customer_id`, `mobile_ad_id`, `hashed_email` e `hashed_phone_number_without_plus_sha256`.

**Exemplo:**

```
value,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="Criar conexões com parceiros de mídia">

As conexões de saída com parceiros de mídia permitem que você integre suas audiências da DCP a parceiros de mídia compatíveis de maneira segura, ativando campanhas personalizadas nas plataformas deles. Os parceiros de mídia são o principal destino para a ativação de audiências. Saiba como <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-media-partner-connections">configurar conexões específicas com parceiros de mídia</Anchor>.

**Para criar uma conexão com parceiros de mídia:**

1. Na AppsFlyer, vá para **Colaborar** > **Data Clean Room.**
2. Clique em **Gerenciar conexões** no canto superior à direita.
3. Acesse a aba **Parceiros de mídia** e clique em **+ Nova conexão**. Se você já tiver conexões existentes, verá que elas estão listadas em **Parceiros de mídia**.
4. Na caixa de diálogo **Nova conexão com parceiros de mídia**, selecione o parceiro de mídia correspondente.
5. Insira um nome para a conexão.
6. Faça login na conta do parceiro de mídia com suas credenciais e siga as instruções para conceder acesso à AppsFlyer.
7. Clique em **Selecionar ID da conta** e selecione a conta correspondente para a conexão.
8. Clique em **Salvar**. A nova conexão é adicionada à lista de parceiros.

Você também pode criar uma conexão com parceiros de mídia a partir do criador de audiências. Veja como <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">criar e ativar audiências</Anchor> para obter as instruções.

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="Criar conexões de dados e identidade">

As conexões de dados e identidade unificam os dados fragmentados dos usuários para melhorar as taxas de correspondência com os parceiros de ativação. Isso permite maximizar as audiências do parceiro e aumentar o impacto das suas campanhas.

#### ID5

<Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">Enriqueça seus dados first-party com identificadores ID5</Anchor> para unificar os dados fragmentados dos usuários, melhorar as taxas de correspondência com os parceiros de ativação e aumentar o tamanho das audiências do parceiro.

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">DCP - Configure seus serviços na nuvem</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP - Crie e ative audiências</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-media-partner-connections">DCP - Conexões com parceiros de mídia</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">DCP - Enriqueça fontes com ID5</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-guide">Plataforma de colaboração de dados (DCP) - Guia</Anchor>

</Accordion>

<div data-zendesk-anchors="about-dcp-connections=sobre-as-conex%C3%B5es-da-dcp h_01KXX80P91T92MH8KEGHVG3QP1=sobre-as-conex%C3%B5es-da-dcp h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=aten%C3%A7%C3%A3o source-cloud-service-connections=conex%C3%B5es-dos-servi%C3%A7os-na-nuvem-para-dados-de-origem cloud-service-connections-for-source-data=conex%C3%B5es-dos-servi%C3%A7os-na-nuvem-para-dados-de-origem h_01KXX80P914VFMH1T6FQF9KC31=importante local-file-connection=conex%C3%A3o-de-arquivo-local h_01KXX80P91EFCGH3MYV729TGTH=conex%C3%A3o-de-arquivo-local h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=aten%C3%A7%C3%A3o-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=veja-tamb%C3%A9m" />
