---
title: Data Clean Room—Trabalhando com conexões
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
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-08-18T00:06:07Z'
  id: 13886278812817
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** Conecte seus serviços de nuvem ao Data Clean Room para fazer upload de dados e receber relatórios.

## Escritórios

Depois de configurar seus serviços de nuvem para uso com o Data Clean Room (DCR), a próxima etapa é conectá-los ao DCR.

* As conexões a partir das quais o DCR lê dados first-party dos seus sistemas são chamadas **inbound connections.** Você usa essas conexões ao configurar suas fontes de dados personalizadas.
* As conexões por meio das quais o DCR entrega relatórios após o processamento são chamadas de **conexões de saída.** Você usa essas conexões ao configurar seus relatórios.

## Criar conexões de entrada

Você pode optar por criar conexões de entrada de uma destas formas:

* Antes de usá-las para criar fontes; ***ou***
* Como parte do processo de criação da fonte.

De qualquer forma, o processo é o mesmo, e você pode usar as conexões criadas exatamente da mesma maneira. A única diferença é o momento e a forma como você inicia o processo.

**Para criar uma nova conexão de entrada fora do processo de criação da fonte:**

1. Na parte superior da página principal do DCR no AppsFlyer, clique no botão **Gerenciar conexões**:

   [![dcr_manage_connections_button.png](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)

   * Se houver conexões de entrada existentes na sua conta, você verá a caixa de diálogo **Gerenciar conexões**. Nela, clique no botão ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) para abrir a caixa de diálogo **Nova conexão**.
   * Se você estiver criando a primeira conexão de entrada da sua conta, a caixa de diálogo **Nova conexão** será aberta automaticamente.
2. Continue com as instruções na seção [Concluir a conexão](#concluir-a-conexão) abaixo.

**Para criar uma nova conexão de entrada como parte do processo de criação da fonte:**

1. Crie a conexão enquanto você <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#2-specify-the-source-location">especifica o local da fonte</Anchor>.
   * Se não houver conexões definidas em sua conta, a caixa de diálogo **Nova conexão** será aberta, solicitando que você crie uma.
   * Se você tiver conexões existentes, mas quiser usar uma nova, clique no ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) botão para abrir a **Nova conexão**caixa de diálogo.
2. Continue com as instruções na seção [Concluir a conexão](#concluir-a-conexão) abaixo.

#### Concluir a conexão

Na caixa de diálogo **Nova conexão**, selecione o serviço de nuvem que você está conectando ao DCR e, em seguida, continue com as instruções na guia relevante abaixo.

<Image alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

Na caixa de diálogo **Nova conexão**, insira o **ID do projeto** do BigQuery do projeto que contém sua fonte de dados personalizada.

* Você pode obter essas informações na página do BigQuery do Console do Google Cloud.

  <Image alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

Na caixa de diálogo **Nova conexão**, insira o **ID da conta do Snowflake** e a **região** da conta que contém sua fonte de dados personalizada. Você pode obter essas informações clicando no nome da conta no menu no canto inferior esquerdo do console do Snowflake:

* **ACCOUNTADMIN** > **Conta** > passe o mouse sobre a conta correspondente > **Copiar identificador da conta**. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Consulte a documentação do Snowflake aqui</Anchor>.

![ui-snowsight-account-identifier.png](https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png)

</Accordion>

<div id="s3-gcs-inbound" />

<Accordion title="Amazon S3 e GCS">

Na caixa de diálogo **Nova conexão**, insira o nome do <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs">bucket que você criou</Anchor> para uso exclusivo do DCR.

</Accordion>

## Criar conexões de saída

O DCR entrega relatórios para seus serviços de nuvem selecionados usando o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>. Como os relatórios são entregues via Data Locker, as conexões de saída do DCR são, na verdade, conexões do Data Locker. Você pode optar por criar essas conexões de uma destas formas:

* Antes de usá-las para criar relatórios (começando pela página do Data Locker na AppsFlyer); ***ou***
* Como parte do processo de criação de relatórios (começando pela página do DCR na AppsFlyer).

De qualquer forma, o processo é praticamente o mesmo, e você pode usar as conexões criadas exatamente da mesma maneira.

> 📘 **Nota**
>
> para receber relatórios do DCR não é necessário uma assinatura premium do Data Locker. Se você estiver interessado em receber outros relatórios da AppsFlyer por meio do Data Locker, entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Para criar uma nova conexão de saída fora do processo de criação de relatórios:**

1. No menu de navegação lateral esquerdo da AppsFlyer, selecione **Relatório > Data Locker.**  
   * Se houver conexões do Data Locker existentes na sua conta, você será direcionado para a página principal do Data Locker. De lá, clique no botão ![dcr_dl_new_connection_button.png](https://files.readme.io/8261a480674822371c6e585f995a496a6b5682dd935351375db200bbb1272689-13919327056657.png) no canto superior direito para abrir a caixa de diálogo **Nova conexão**.
   * Se você estiver criando a primeira conexão do Data Locker da sua conta, verá a página **Primeiros passos** do Data Locker. Clique no botão ![dcr_dl_get_started_button.png](https://files.readme.io/3176ed5c35cba0939dd36de8c1136d15dc8ce27ee2891894ef65dba92fc7e91a-13919329616657.png) para abrir a caixa de diálogo **Nova conexão**.
2. Continue com as instruções na seção [Concluir a conexão](#concluir-a-conexão-1) abaixo.

**Para criar uma nova conexão de saída como parte do processo de criação de relatórios:**

1. Crie a conexão enquanto estiver <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">definindo o destino do relatório</Anchor>.
   * Se não houver conexões definidas em sua conta:
     * Uma nova aba será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá.
   * clique no botão ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) :
     * Uma nova aba será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá.
2. Continue com as instruções na seção [Concluir a conexão](#concluir-a-conexão-1) , abaixo.
3. Depois de criar a conexão, retorne à aba DCR em seu navegador e selecione a conexão recém-criada na lista de conexões do Data Locker.

#### Concluir a conexão

> 🚧 **Importante!**
>
> A opção **AppsFlyer AWS Bucket** não deve ser usada para relatórios de DCR.

Na caixa de diálogo **Nova conexão**, selecione o serviço de nuvem ao qual você está se conectando e, em seguida, continue com as instruções na guia relevante abaixo.

[![dcr_dl_new_connection_dialog.png](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

1. Na caixa de diálogo **Nova conexão**, insira um nome para a conexão e selecione a opção **BigQuery**.
2. Insira o **ID do projeto** e o **nome do conjunto de dados** para o projeto do BigQuery que contém o <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#bigquery-outbound">conjunto de dados que você criou</Anchor> para o Data Locker.  
   * Você pode obter essas informações na página do BigQuery do seu Console do Google Cloud.

     <Image alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />
3. Clique no botão ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) para garantir que o Data Locker esteja conectado ao conjunto de dados.
4. Clique em **Salvar** para criar a conexão.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

O procedimento para conectar o Snowflake ao Data Locker é um processo de 2 etapas:

* **[Etapa #1](/docs/data-clean-room-working-with-connections#step-1) –** No AppsFlyer, crie a conexão inicial.
  * Isso permite que sua conta do Snowflake acesse um compartilhamento do Snowflake do AppsFlyer.
* **[Etapa #2](/docs/data-clean-room-working-with-connections#step-2) –** Na sua conta do Snowflake, crie um banco de dados a partir do compartilhamento.
  * Isso cria um banco de dados na sua conta que faz referência às tabelas no compartilhamento do AppsFlyer.

**Observação:** o procedimento a seguir deve ser executado por um **administrador da conta do Snowflake.**

<span id="step-1"></span>**Etapa #1 (criar a conexão inicial) –**

1. Na caixa de diálogo **Nova conexão**, insira um nome para a conexão e selecione a opção **Snowflake**.
2. Insira a região da sua conta do Snowflake e o ID da conta.
   * Você pode obter essas informações clicando no nome da conta no canto inferior esquerdo do console do Snowflake e, em seguida, passando o cursor sobre o nome da conta na janela pop-up. **Importante!** Busque o ID com a etiqueta **Locator.** Este **NÃO** é o mesmo ID que o usado para criar conexões de entrada do Snowflake.  

     <Image alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />
3. Clique no botão ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) para garantir que o Data Locker esteja conectado à sua conta do Snowflake.
4. Clique em **Salvar** para criar a conexão.

<span id="step-2"></span>**Etapa #2 (criar um banco de dados a partir do compartilhamento)** –

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Faça login na sua conta Snowflake</Anchor>.
2. Mude sua função para **Accountadmin.**
3. No painel à esquerda, selecione **Private Sharing.**
4. Na página que se abre, selecione a aba **Shared With You** .
5. No compartilhamento cujo nome começa com **APPSFLYER**, clique no botão **Get data** ![snowflake_get_data_button.png](https://files.readme.io/fbda3603d504f08980bd5329aad49e5e0c562e1de556ffb0e04ad4a1abbac89c-13930725492497.png).
6. [Opcional] Na caixa de diálogo **Get Data**, altere o nome padrão do banco de dados conforme suas necessidades e selecione, além de Accountadmin, as funções que podem acessar o banco de dados.
7. Clique em **Get Data** para criar o banco de dados.

</Accordion>

<div id="s3-gcs-outbound" />

<Accordion title="Amazon S3 e GCS">

1. Na caixa de diálogo **New connection** do Data Locker, insira um nome para a conexão; em seguida, selecione a opção **Amazon S3** ou **GCS**.
2. Insira o nome do <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services#buckets-de-armazenamento-em-nuvem--amazon-s3-e-gcs">bucket que você criou</Anchor> para o uso exclusivo do DCR.

</Accordion>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01HKA1AS2QGDTPW85WA07K35M0=escrit%C3%B3rios creating-inbound-connections=criar-conex%C3%B5es-de-entrada h_01HKA1AS2QRRBJAYNKSWWZXE3N=criar-conex%C3%B5es-de-entrada complete-the-connection-inbound=concluir-a-conex%C3%A3o h_01HKA1AS2Q06F07RDD8W384RE2=concluir-a-conex%C3%A3o h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QQZWFMRQD0T0FNQM5=s3-gcs-inbound creating-outbound-connections=criar-conex%C3%B5es-de-sa%C3%ADda h_01HKA1AS2QAV9DJWZQ2703TS0Z=criar-conex%C3%B5es-de-sa%C3%ADda h_01HKA1AS2Q76NP9FY7S4H0QP4D=nota complete-the-connection-outbound=concluir-a-conex%C3%A3o-1 h_01HKA1AS2RKTWNY2ZR7VYAJC90=concluir-a-conex%C3%A3o-1 h_01HKA1AS2R7RFWKM2W89QSEH3V=importante h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound h_01HKA1AS2RBTK8NZF09BYWDX2G=s3-gcs-outbound" />
