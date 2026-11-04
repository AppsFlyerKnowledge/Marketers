---
title: Data Locker para profissionais de marketing
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2026-08-19T00:04:44Z'
  id: 360000877538
  locale: pt
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/pt/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** o Data Locker envia seus dados de relatório para um cloud storage para que eles sejam carregados em seus sistemas de BI. Você pode selecionar diferentes destinos de armazenamento: um bucket da AppsFlyer na AWS ou um armazenamento de sua propriedade na AWS, GCS, Yandex, BigQuery e Snowflake. O Data Locker é compatível com [múltiplos destinos](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination). Isso significa que você pode enviar todos os dados para múltiplos destinos, segregar dados por destino, ou escolher uma combinação de ambos.

## Visão geral

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

No Data Locker, selecione seus aplicativos, fontes de mídia, eventos e relatórios a serem incluídos nos dados que a Appsflyer envia para as suas opções selecionadas de cloud storage. Em seguida, carregue dados programaticamente em seus sistemas.

<div id="data-locker-features" />

<Accordion title="Data Locker — recursos">

| Funcionalidade | Descrição |
| --- | --- |
| [Opções de armazenamento (nuvem)](/docs/data-locker-for-marketers#storage-options) | O Data Locker pode enviar seus dados para qualquer um dos seguintes provedores de serviços na nuvem:<ul><li>Armazenamento de propriedade da AppsFlyer no AWS</li><li><Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup">Armazenamento de sua propriedade</Anchor> em:<ul><li>AWS</li><li>GCS</li><li>[Beta] Azure Blob</li><li>[Beta] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Você pode definir mais de um destino no Data Locker. Isso significa que você pode enviar todos ou alguns de seus dados para [diferentes destinos](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination).<br /><br />**Exemplos**<ul><li>Separe os dados por tipo de relatório. Envie dados brutos para GCS e dados agregados para Snowflake.</li><li>Separe os dados por aplicativo e envie os dados por grupo de aplicativos para diferentes buckets.</li></ul> |
| Multiaplicativos | Envie dados de 1, mais ou todos os aplicativos na sua conta. Quando você adiciona aplicativos à conta, eles podem ser incluídos automaticamente. |
| Janela de disponibilidade | 14 dias |
| [Segregação de dados](/docs/data-locker-for-marketers#app-segregation) | Opções de segregação de dados disponíveis (relevantes para bucket cloud storage):<ul><li>[Padrão] **Unificado:** Dados de todos os aplicativos combinados. O campo de app ID em nível de linha é usado para identificar o aplicativo em arquivos de dados.</li><li>**Segregado por aplicativo:** Os dados de cada aplicativo estão em uma pasta separada. O nome da pasta consiste no app ID.</li></ul> |
| Opções de formato de dados | <ul><li>Para bucket cloud storage:<ul><li>CSV</li><li>PARQUET</li><li><Anchor target="_blank" href="/marketers/pt/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>Data warehouse</li></ul> |
| Atualização dos dados | A atualização depende do tipo de relatório<ul><li>**Por hora:** dados gerados continuamente; por exemplo, instalações e dados de eventos in-app são transmitidos poucas horas após o evento chegar à AppsFlyer.</li><li>**Diária:** relatórios como os de desinstalações são gerados diariamente e ficam prontos no dia seguinte.</li><li>**Versionada:** se o mesmo relatório for gerado várias vezes para o mesmo período, um mecanismo de controle de versão estará em vigor.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Relatórios disponíveis via Data Locker">

<Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports">Relatórios disponíveis via Data Locker</Anchor>

</Accordion>

<div id="set-data-locker-report-settings" />

## Definir configurações do relatório do Data Locker

Para configurar o Data Locker, siga as etapas abaixo para conectar seu cloud service, definir as configurações de exportação e personalizar o conteúdo do relatório:

<div id="1-set-up-your-cloud-service" />

<Accordion title="1. Configure seu cloud service">

Você pode conectar seu Data Locker a um ou mais provedores de cloud service. Veja a seguir as instruções sobre como configurá-los para trabalhar com o Data Locker:

* Bucket da <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
* Bucket do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
* [Beta] <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure Blob</Anchor>
* [Beta] Bucket da <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
* Data warehouse do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
* Data warehouse do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>

**Atenção**! Se você não tiver uma assinatura do Data Locker e tentar acessar a análise de cohort ou os dados da SKAN, você deve completar um dos procedimentos acima.

</Accordion>

<div id="2-add-a-connection-to-your-cloud-service" />

<Accordion title="2. Adicione uma conexão ao seu cloud service">

Após configurar sua conta de cloud service para trabalhar com o Data Locker (veja "Configurar seu cloud service" acima), crie uma conexão no Data Locker usando as credenciais da sua conta. Você pode criar até duas conexões.

<div id="note" />

> 📘 **Nota**
>
> Por padrão, cada conta pode ter até **2 conexões do Data Locker**. Se você precisar adicionar mais conexões, entre em contato com seu Customer Success Manager (CSM).

Para criar uma conexão para o seu cloud provider, siga os seguintes passos:

1. Na AppsFlyer, no menu lateral, vá para **Relatórios** > **Data Locker**.
2. À direita, clique em **Nova conexão.**
3. Em **Nome da conexão** insira o nome da sua conexão. Use apenas letras minúsculas, dígitos e hífens "-"
4. Clique no ícone do cloud service ao qual você deseja se conectar.
5. Dependendo da opção que você selecionou, insira as seguintes informações de conexão.

   <div id="aws-cloud-bucket-connection" />

   <Accordion title="Conexão de bucket da AWS cloud">

   Antes de configurar a conexão com a AWS, crie um bucket da AWS. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#aws-storage">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira o nome do seu bucket S3 da AWS. O prefixo `af-` é obrigatório e deve ser inserido manualmente.
   2. Clique em **Testar conexão**.
   3. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   4. Selecione se deseja **tornar esta conexão compatível com a Adobe Experience Platform**. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).
   5. Clique em **Salvar**.

   </Accordion>

   <div id="gcs-cloud-bucket-connection" />

   <Accordion title="Conexão de bucket do GCS cloud">

   Antes de configurar a conexão GCS, crie um bucket no GCS. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#gcs-storage">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira o **nome do bucket do GCS**.
   2. Clique em **Testar conexão**.
   3. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   4. Selecione se deseja **tornar esta conexão compatível com a Adobe Experience Platform**. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).
   5. Clique em **Salvar**.

   </Accordion>

   <div id="azure-cloud-bucket-connection" />

   <Accordion title="Conexão de bucket da Azure cloud">

   Antes de configurar a conexão da Azure, abra uma conta de armazenamento na Azure. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#beta--azure-storage">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira seu **Nome de conexão**, **Nome da conta de armazenamento** e **Chave**.
   2. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   3. Selecione se deseja **tornar esta conexão compatível com a Adobe Experience Platform**. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).
   4. Clique em **Salvar**.

   </Accordion>

   <div id="yandex-cloud-bucket-connection" />

   <Accordion title="Conexão do bucket do Yandex Cloud">

   Antes de configurar a conexão com a AWS, crie uma conta de serviço no Yandex. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#yandex">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira o **nome do bucket**, **a chave de acesso**e **a chave secreta**.
   2. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   3. Selecione se deseja **tornar esta conexão compatível com a Adobe Experience Platform**. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).
   4. Clique em **Salvar**.

   </Accordion>

   <div id="bigquery-data-warehouse-connection" />

   <Accordion title="Conexão com o data warehouse do BigQuery">

   Antes de configurar a conexão do BigQuery, crie um conjunto de dados no BigQuery. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#bigquery">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira o project ID do BigQuery e o nome do conjunto de dados.
   2. Clique em **Testar conexão**.
   3. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   4. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).

   </Accordion>

   <div id="snowflake-data-warehouse-connection" />

   <Accordion title="Conexão do data warehouse do Snowflake">

   Antes de configurar a conexão com o Snowflake, abra uma conta no Snowflake. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#snowflake">aqui</Anchor>.

   Para configurar a conexão:

   1. Insira sua região e account ID do Snowflake.
   2. Clique em **Testar conexão**.
   3. Verifique se uma mensagem de erro indicando que o caminho do bucket é inválido não é exibida.
   4. Se selecionado, clique em **Salvar** e continue a [selecionar filtros de nível global](#select-global-level-filters).

   </Accordion>

6. Clique em **Salvar.** A **seção de configurações de output do relatório** é exibida.

<div id="note-1" />

> 📘 **Nota**
>
> Você pode [usar o log de auditoria](#track-connection-changes-in-the-audit-log) para confirmar se uma conexão foi criada, atualizada ou excluída, e quem fez a alteração.

</Accordion>

<div id="3-set-the-report-output-settings" />

<Accordion title="3. Defina as configurações de output do relatório">

Após estabelecer a conexão com o cloud service, você pode continuar a definir as configurações gerais de outputs de relatórios do seu Data Locker. **Se o seu cloud service for BigQuery ou Snowflake, você pode pular essa etapa**.

1. Em **Configurações de output do relatório**, selecione a estrutura de pastas ([segregação de dados](/docs/data-locker-for-marketers#app-segregation)):
   * **Unificado** (padrão): Os arquivos de relatório incluem registros de todos os aplicativos.
   * **Segregado por aplicativo:** Cada arquivo de relatório é dedicado a um aplicativo.
2. Selecione o formato do arquivo de relatórios: Parquet (padrão) ou CSV.
3. Selecione o tipo de compactação de arquivo que você deseja:
   * Snappy (disponível apenas para arquivos Parquet)
   * GZIP
4. Selecione o número máximo de linhas que você deseja em seu arquivo: 10 mil, 25 mil, 50 mil, 100mil, 200 mil ou 500 mil. Mais linhas significam menos arquivos, mas um tamanho de arquivo maior.

   <div id="note-2" />

   > 📘 **Nota**
   >
   > Em **Expected path**, veja os padrões de caminho para seus relatórios. Atenção: O caminho real pode ser diferente do exibido.


</Accordion>

<div id="select-global-level-filters" />

<Accordion title="4. Selecione filtros de nível global">

Os filtros de nível global permitem que você **filtre seus relatórios por aplicativos ou fontes de mídia**. Esses filtros se aplicam à maioria dos relatórios na sua conta do Data Locker, mas você também pode configurá-los no nível do relatório (veja [7-selecionar-os-filtros-do-nível-do-relatório](#select-the-report-level-filters) abaixo). Se o mesmo filtro for aplicado em ambos os níveis, o filtro de nível de relatório tem prioridade.

Para aplicar um filtro, faça o seguinte:

1. Em **Relatórios**, clique no filtro e selecione os itens a serem incluídos no relatório. Por exemplo, clique <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> no filtro **Apps** e selecione os aplicativos a serem incluídos nos relatórios.
2. Em seguida, clique no botão Enter (⏎).

</Accordion>

<div id="5-select-the-report" />

<Accordion title="5. Selecione o grupo de relatórios">

Selecione os relatórios que você deseja obter em seu cloud service. Os relatórios estão listados em grupos. Clicar no nome do grupo de relatórios expande ou recolhe os grupos.

* Para selecionar um relatório, clique em <Image alt="down.png" src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" width="20px" /> para expandir o grupo de relatórios. Para cada relatório no grupo, as seguintes informações são apresentadas:
  * **Nome do relatório:** O título do relatório.
  * **Nome do conjunto de dados:** O nome do conjunto de dados que contém os registros do relatório.
  * **Atualização dos dados:** Com que frequência o relatório é atualizado com novos registros (por exemplo, a cada hora, diariamente ou em versões).
  * **Campos:** o número de campos (ou colunas) que você selecionou para o relatório em comparação com o número total de campos disponíveis para seleção.

</Accordion>

<div id="customize-or-duplicate" />

<Accordion title="6. Personalize ou duplique o relatório">

Após selecionar um ou mais relatórios de um grupo de relatórios, você pode optar por **personalizar o relatório original** ou **criar uma cópia personalizada separada** duplicando-o. Isso permite que você personalize os campos e filtros do relatório de acordo com suas necessidades específicas, sem afetar a versão original.

**Opção A: Personalize o relatório original**

1. Clique no botão de <Image alt="customize.png" src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" width="20px" /> **personalizar** ao lado do nome do relatório.
2. O editor de relatórios será aberto, permitindo que você selecione campos e aplique filtros.
3. As alterações serão salvas na configuração original do relatório.

*Atenção: Isso modifica como o relatório é entregue ao seu cloud storage.*

**Opção B: Duplicar o relatório**

* Clique em <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="5px" /> ao lado do nome do relatório.
* Selecione <Image alt="duplicate2.png" src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" width="17px" /> **Duplicar** no menu suspenso.
* Uma cópia do relatório será criada, nomeada com o prefixo `copy_of_`.
* O relatório duplicado é aberto em modo de edição para maior personalização.

*Dica: Duplicar é ideal para criar variações de um relatório para diferentes casos de uso.*

Após escolher entre personalizar ou duplicar, configure os campos do relatório conforme descrito na próxima etapa.

</Accordion>

<div id="6-select-the-report-fields" />

<Accordion title="7. Selecione os campos do relatório">

Uma vez que você escolheu personalizar ou duplicar um relatório, o próximo passo é definir quais campos de dados devem ser incluídos. Cada relatório fornece um conjunto completo de campos disponíveis e você pode personalizar sua seleção para incluir apenas o que é relevante para sua análise ou integração. Por padrão, todos os campos são selecionados, mas você pode refinar o relatório escolhendo manualmente campos específicos.

Selecione os campos a serem incluídos no relatório:

1. No diálogo do relatório selecionado, em **Campos**, passe o mouse sobre qualquer campo para ver sua descrição.

   [![HQ1_2024-08-26_15.44.23.png](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)
2. Verifique os campos que deseja incluir no relatório ou desmarque os campos que deseja excluir.
3. Clique em **Aplicar** para salvar suas configurações.

**Copiar os campos de outro relatório**

Você pode copiar os campos de outro relatório como ponto de partida e, em seguida, continuar a selecionar ou desmarcar campos para ajustar seu relatório.

1. Na aba **Campos**, desmarque qualquer campo aleatório.
2. Clique em **Extrair esquema do relatório**.
3. Selecione o relatório do qual você deseja copiar os campos.
4. Continue selecionando ou desmarcando campos.
5. Para restaurar a seleção original do relatório, clique em <Image alt="Sem título 4.png" src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" width="15px" /> **Atualizar**.

</Accordion>

<div id="7-select-the-reportlevel-filters" />

<Accordion title="8. Selecione os filtros a nível de relatório">

Os filtros a nível de relatório permitem que você **filtre um único relatório por aplicativos, fontes de mídia ou outras dimensões**. Você também pode definir filtros que se aplicam a todos os relatórios em sua conta; veja [selecionar filtros a nível global](#select-global-level-filters). Por padrão, os filtros a nível de relatório são definidos para as configurações de filtro a nível global, mas você pode atualizá-los para configurações personalizadas que se aplicam apenas ao relatório selecionado.

Para selecionar os filtros a serem aplicados a um relatório específico:

1. Passe o mouse sobre o relatório específico que você deseja personalizar.
2. Clique em <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="6px" /> para abrir o menu de ações e selecione <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="20px" /> **Editar relatório**.
3. Abra a aba **Filtros**. Os filtros estão configurados para as configurações de filtro a nível global.
4. Clique no filtro e selecione os itens a serem incluídos no relatório. Por exemplo, clique no filtro <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> **Apps** e selecione os aplicativos a serem incluídos nos relatórios.
5. Em seguida, clique no botão Enter (⏎). Essa seleção substitui as configurações a nível global.
6. (Opcional) Para o relatório **Inapps** , você pode definir o filtro **Evento in-app**. Digite seus nomes de maneira precisa para selecioná-los.
7. Clique em **Aplicar** para salvar suas configurações.

</Accordion>

<div id="8-remove-legacy-fields" />

<Accordion title="9. Remova campos legados">

Os campos não utilizados são aqueles que foram anteriormente incluídos no esquema do relatório, mas agora foram excluídos. Recomendamos remover esses campos para garantir que seu relatório contenha apenas informações relevantes. Antes de fazer quaisquer alterações, certifique-se de que seus workflows e integrações não dependem deles.

**Para remover campos legados específicos**

1. Abra a aba **campos legados**.
2. Ative: **incluir campos legados no relatório**.
3. Desmarque os campos que deseja excluir.
4. Clique em **aplicar**.
5. Salve as configurações de conexão.

**Para remover todos os campos legados:**

1. Abra a aba de campos legados.
2. Desativar: **incluir campos legados no relatório**.

<div id="note-3" />

> 📘 **Nota**
>
> Se você quiser incluir campos não utilizados no relatório, mas não consegue fazer isso porque a lista de campos legados está desativada e bloqueada, entre em contato com seu Customer Success Manager.

<div id="non-empty-legacy-fields" />

#### Campos legados não vazios

A maioria dos campos legados está vazio ou `null`. No entanto, alguns deles contêm valores, mas ainda são considerados sem uso porque:

* Eles aparecem no relatório com um nome diferente (renomeado).
* Eles foram excluídos do esquema do relatório (obsoleto).

[Baixar a lista de campos legados não vazios (CSV).](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

</Accordion>

<div id="9-save-the-connection" />

<Accordion title="10. Salve a conexão">

Clique em **Salvar** e o primeiro envio de dados aparecerá no seu cloud service dentro de 3 horas. Os cronogramas de atualização de dados subsequentes são específicos para cada relatório.

<div id="important" />

> 🚧 **Importante!**
>
> As alterações nas configurações do Data Locker levam até 3 horas para entrar em vigor.

</Accordion>

<div id="set-user-permissions" />

## Permissões do usuário

Tanto os administradores quanto os membros da equipe, com as permissões corretas, podem acessar o Data Locker.

* Os administradores podem acessar a página do Data Locker, criar e gerenciar todas as conexões, adicionar editores e atribuir proprietários a conexões existentes.
* Os membros da equipe podem acessar a página do Data Locker, editar conexões existentes ou criar novas conexões. Eles não podem gerenciar a propriedade (ou seja, definir novos proprietários e editores), mesmo que eles sejam proprietários da conta.

<div id="manage-data-locker-access-and-ownership-admins" />

### Administradores

<div id="hourly-folders" />

<div id="give-data-locker-access" />

#### Pastas por hora

* Para fornecer a um membro da equipe permissão para acessar o Data Locker, atribua a ele um <Anchor target="_blank" href="/marketers/pt/docs/user-management#gerenciar-funções">papel</Anchor> de **gestão** no **Data Locker**.

<div id="manage-ownership-and-editors" />

#### Gerenciar propriedade e editores

Para transferir a propriedade ou adicionar um membro da equipe como editor em uma conexão existente:

1. Para transferir a propriedade ou adicionar um membro da equipe como editor em uma conexão existente, clique no ícone do menu de opções <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="1.18%" /> dentro da conexão existente e, em seguida, clique em **Gerenciar propriedade** para alterar o proprietário da conexão ou adicionar a permissão de edição.
2. Características
3. Altere o proprietário da conexão ou adicione um editor.

<div id="review-filters-after-changing-ownership" />

#### Revise os filtros após alterar a propriedade

Se você alterar o proprietário de uma conexão do Data Locker para um usuário com restrições de acesso a dados (por exemplo, limitado por aplicativo, canal de mídia, agência ou país), os filtros existentes em [nível global](#select-global-level-filters) ou [nível de relatório](#7-select-the-reportlevel-filters) poderão ser redefinidos para corresponder às permissões do novo proprietário.

Após transferir a propriedade, revise os filtros e confirme se a conexão reflete o escopo de dados pretendido.

Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/audit-log">Log de auditoria</Anchor>

<div id="note-4" />

> 📘 **Nota**
>
> Nas conexões AF AWS, não há opção de **gerenciar propriedade** mesmo para administradores, uma vez que apenas administradores podem editar, excluir ou criar novas conexões em AF AWS. Essa precaução tem como objetivo evitar a exposição das credenciais do bucket.

<div id="data-storage-architecture" />

## Arquitetura do armazenamento de dados

<div id="zd-overview" />

<div id="overview" />

<Accordion title="Visão geral">

A estrutura dos dados no armazenamento depende de se os dados são enviados para armazenamento em nuvem ou para um data warehouse. A estrutura de pastas descrita aqui se aplica ao armazenamento (buckets). No caso de armazenamento em data warehouse, considere que a referência a pastas se aplica a exibições.

Os dados são registrados na opção de armazenamento selecionada por você. No caso de cloud storage, o armazenamento é de propriedade da AppsFlyer na AWS ou de sua propriedade na AWS, GCS ou Yandex. Você pode mudar as opções de armazenamento a qualquer momento ou enviar alguns ou todos os seus dados para múltiplas opções de armazenamento.

Os dados de bucket cloud storage são organizados em uma estrutura de pastas hierárquica, de acordo com o tipo de relatório, data e hora. A figura a seguir contém um exemplo dessa estrutura:

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

Os dados de um determinado relatório estão contidos nas pastas de hora (h) associadas a esse relatório:

* O número de pastas de hora depende da atualização dos dados do relatório (por hora ou diária).
* Os dados são fornecidos em arquivos compactados Snappy ou GZIP, ou arquivos não compactados, com formato Parquet ou CSV.
* Os arquivos de dados consistem em colunas (campos).
* A estrutura do esquema (campo) dos <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#user-journey">relatórios de jornada do usuário</Anchor> é idêntica entre si e depende dos campos selecionados por você. Cada um dos outros relatórios tem seus próprios campos explícitos, também conhecidos como relatórios sem esquema. Consulte os <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#user-journey">relatórios de marketing do Data Locker</Anchor> para ver relatórios disponíveis e links para as especificações do relatório.

</Accordion>

<div id="folder-structure" />

<Accordion title="Estrutura de pastas">

| Pasta | Descrição |
| --- | --- |
| Subscription ID | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>A pasta de nível superior no bucket depende do proprietário e do provedor do armazenamento. No geral, a pasta de nível superior é seu Subscription ID, mas em alguns casos, por exemplo, se você usar Cyberduck, o ID é definido no marcador de página e não é exibido na estrutura da pasta.</li><li>A pasta *data-locker-hourly* contém os tópicos do relatório. As pastas acima desse nível dependem da propriedade do bucket e do provedor de serviços cloud.</li></ul>**Exemplos de estrutura de pastas com base no proprietário do bucket e no provedor cloud**<ul><li>**Bucket da AppsFlyer**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**Seu repositório AWS**: *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**Seu repositório GCS:** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Tópico (t) | O tipo de relatório está relacionado ao assunto do relatório. |
| Data (dt) | Essa é a data dos dados relacionados. No caso de dados brutos, significa a data em que o evento ocorreu. No caso de dados agregados, a data do próprio relatório. |
| Hora (h ou version) | As pastas de data são divididas em pastas **por hora (h)** ou **version**, dependendo do tipo de relatório.<br /><br />**Pastas por hora**<br /><br />As pastas h estão relacionadas ao horário em que os dados foram recebidos pela AppsFlyer. Por exemplo, eventos de instalação recebidos entre 14:00 e 15:00 UTC são gravados no arquivo h=14. Atenção! Há um atraso de cerca de 1 a 3 horas, entre o momento em que os dados chegam à AppsFlyer até que a pasta h seja registrada no Data Locker. Por exemplo, a pasta h=14 é escrita 1 hora depois às 15:00 UTC.<br /><br />**Características da pasta por hora**:<ul><li>Existem 24 pastas h enumeradas de 0 a 23. Por exemplo, h=0, h=1 e assim por diante.</li><li>Uma pasta tardia, h=late, contém eventos do dia anterior que chegam depois da meia-noite. Ou seja, eventos que chegam das 00:00 às 02:00 UTC do dia seguinte. Por exemplo, se um usuário instalar um aplicativo na segunda-feira às 08:00 UTC e o evento chegar na terça-feira às 01:00 UTC, o evento será gravado na pasta tardia de segunda-feira.</li><li>Os dados que chegam depois das 02:00 UTC são transmitidos para a pasta da data e hora reais de chegada.</li><li>Certifique-se de que os dados na pasta h=late sejam consumidos. Eles não estão contidos em nenhuma outra pasta.</li><li>Pasta \_temporary:**Em alguns casos, geramos uma pasta temporária (temporary) dentro de uma pasta h. Desconsidere pastas e subpastas temporárias. Exemplo: /t=impressions/dt=2021-04-11/h=18/**\_temporary.</li></ul>**Relatórios diários**<ul><li>Os relatórios de dados brutos com atualização diária de dados são armazenados na pasta h=23. O relatório de desinstalação geralmente está na pasta h=2, mas pode estar em qualquer pasta.</li><li>Os relatórios de cohort e incrementalidade são armazenados diretamente na pasta dt.</li><li>Os relatórios versionados seguem uma convenção diferente descrita nesta seção.</li></ul>**Considerações sobre o relatório por hora para aplicativos que não usam o horário UTC.**<br /><br />Para garantir que você obtenha todos os dados de um determinado dia do calendário, você deve consumir as pastas de acordo com o dia definido pelo fuso horário do aplicativo conforme detalhado:<ul><li>**Fuso horário do hemisfério leste:** Para obter todos os dados de uma determinada data do calendário, você deve consumir pastas de acordo com o horário e a data UTC. Exemplo: o fuso horário do seu aplicativo é UTC+10 (Sydney, Austrália). Para obter todos os dados horários relacionados à terça-feira (Sydney), você deve consumir as seguintes pastas: Segunda-feira h=14–23 e tarde, Terça-feira h=0–13 e 14-15 Por que você deve consumir Terça-feira h=14-15? Alguns dados podem chegar atrasados. Portanto, as pastas h=14—15 podem conter eventos que chegam atrasados. Você deve filtrar event\_time para alinhar com o dia do calendário do aplicativo em relação a UTC.</li><li>**Fuso horário do hemisfério oeste:** Para obter todos os dados de uma determinada data do calendário, você deve consumir pastas de acordo com o horário e a data UTC. Exemplo: o fuso horário do seu aplicativo é UTC-7 (Los Angeles). Para obter todos os dados horários relacionados a terça-feira (Los Angeles), você deve acessar as seguintes pastas: Terça-feira h=7–23 e tarde, Quarta-feira h=0–6 e 7-8. Por que você deve consumir quarta-feira h=7-8? Alguns dados podem chegar atrasados. Portanto, as pastas h=7—8 podem conter eventos que chegam atrasados. Você deve filtrar event\_time para alinhar com o dia do calendário do aplicativo em relação a UTC.</li></ul>**<span id="version-folders"></span>Pastas versionadas**<br /><br />Alguns relatórios têm uma opção versionada Alguns relatórios têm uma opção versionada Isso significa que os dados mais atualizados para um determinado dia são fornecidos várias vezes. Alguns relatórios têm uma opção versionada Isso significa que os dados mais atualizados para um determinado dia são fornecidos várias vezes. Como os dados podem continuar a ser atualizados devido a dados que chegam atrasados ou dados mais precisos, o mesmo relatório tem várias versões em que a versão mais recente é a mais precisa.<br /><br />Os relatórios de um determinado dia estão contidos na pasta de versões daquele dia. Cada versão está contida em uma pasta separada cujo nome é definido usando um carimbo de data/hora Epoch que identifica exclusivamente o relatório.<br /><br />Seus processos de importação de dados devem considerar que os dados podem ser gravados retroativamente. Por exemplo, em 14 de janeiro, os dados podem ser gravados na pasta 1º de janeiro. Se o bucket for de sua propriedade, considere usar a notificação de serviço de nuvem para acionar o processo de importação (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>) |

</Accordion>

<div id="app-segregation" />

<Accordion title="Segregação de aplicativos">

Para armazenamento em bucket na nuvem, os dados são fornecidos em arquivos de dados unificados contendo os dados de todos os aplicativos selecionados ou segregados em pastas por aplicativo. A segregação está dentro da pasta h, conforme descrito na tabela a seguir.

| Tipo de segregação | Descrição |
| --- | --- |
| [Padrão] Unificado | Os dados de todos os aplicativos são fornecidos em arquivos de dados unificados. Ao consumir os dados, use o campo app\_id no nível da linha para distinguir entre aplicativos.<br /><br />**Exemplo de arquivos de dados estão na pasta h=2**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />A convenção de nomenclatura de arquivos de dados é unique\_id.gz.<ul><li>Seu processo de carregamento de dados deve:<ul><li>Carregar dados depois que a flag \_SUCCESS for definida.</li><li>Carregar todos os arquivos na pasta que tenham uma extensão *.gz* Não desenvolva seu processo de importação usando lógica de numeração de part. Carregar todos os arquivos na pasta que tenham uma extensão *.gz* Não desenvolva seu processo de importação usando lógica de numeração de part. Não desenvolva seu processo de importação usando lógica de numeração de part.</li></ul></li></ul> |
| Segregado por aplicativo | A pasta contém subpastas por aplicativo. Os arquivos de dados de um determinado aplicativo estão contidos na pasta do aplicativo. Na figura a seguir, a pasta h=19 contém pastas de aplicativos. Cada pasta do aplicativo contém os arquivos de dados associados. Atenção! Os arquivos de dados não contêm o app\_id, você deve determinar o app\_id usando a pasta.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />Em cada pasta do aplicativo, a convenção de nomenclatura é unique\_id.gz:<ul><li>Seu processo de carregamento de dados deve:<ul><li>Carregar dados depois que a flag \_SUCCESS for definida.</li><li>Carregar todos os arquivos na pasta que tenham uma extensão *.gz* Não desenvolva seu processo de importação usando lógica de numeração de part. Carregar todos os arquivos na pasta que tenham uma extensão *.gz* Não desenvolva seu processo de importação usando lógica de numeração de part. Não desenvolva seu processo de importação usando lógica de numeração de part.</li></ul></li></ul>Limitação: essa opção não está disponível para relatórios de People-Based Attribution. |

</Accordion>

<div id="data-files" />

<Accordion title="Arquivos de dados">

Os arquivos de dados dependem do tipo de segregação.

<table><thead><tr><th>Conteúdo</th><th colspan="2">Detalhes</th></tr></thead><tbody><tr><td>Flag de conclusão</td><td colspan="2"><p>A última flag de arquivo (conclusão) é definida quando todos os dados de uma determinada pasta h tiverem sido gravados. </p><ul><li>Não leia dados em uma pasta antes de verificar se a flag _SUCCESS existe.</li><li>A flag _SUCCESS é definida mesmo nos casos em que não há dados para gravar em uma determinada pasta e a pasta está vazia.</li><li>Atenção! Na opção segregação por aplicativo, a flag é definida na pasta h e não nas pastas individuais do aplicativo. Consulte as figuras na seção anterior. </li></ul></td></tr><tr><td>Tipos de arquivo</td><td colspan="2"><ul><li>Os dados são fornecidos em arquivos compactados Snappy ou GZIP, ou arquivos não compactados, com formato Parquet ou CSV.</li><li>Depois de descompactar, os arquivos de dados estarão no formato Parquet ou CSV de acordo com suas configurações.</li></ul></td></tr><tr><td>Sequência de colunas (arquivos CSV) </td><td colspan="2"><p>No caso de arquivos CSV, a sequência de campos nos relatórios é sempre a mesma. Quando adicionamos novos campos, eles são adicionados à direita dos campos existentes. </p><p>Sobre isso: </p><ul><li>A estrutura de colunas dos relatórios de jornada do usuário é idêntica. Isso significa que você pode ter procedimentos de carregamento de dados semelhantes para diferentes tipos de relatório. Você seleciona os campos contidos nos relatórios. O significado do campo está detalhado no <a href="./raw-data-field-dictionary" target="_blank">dicionário de dados brutos</a>.</li><li>Os relatórios que têm uma indicação de FF na seção de disponibilidade do relatório não aderem à estrutura de coluna comum. </li></ul></td></tr><tr><td>Considerações sobre o preenchimento de campos</td><td colspan="2"><p><strong>Campos em branco ou vazios:</strong> Alguns campos são preenchidos com <em>null</em> ou estão vazios. Isso significa que, no contexto de um certo relatório, não há dados a reportar. Em geral, <em>null</em> significa que esse campo não é preenchido no contexto de um determinado relatório e tipo de aplicativo. "Em branco" significa que o campo é relevante em seu contexto, mas nenhum dado foi encontrado para preenchê-lo. </p><p>No caso da fonte de mídia restrita, o conteúdo dos campos restritos é definido como nulo. </p><p>No geral, considere null e em branco como a mesma coisa. Não há dados disponíveis. </p><p><strong>Fuso horário e moeda</strong></p><p>As configurações de fuso horário e moeda específicas do aplicativo não afetam os dados gravados no Data Locker. O seguinte se aplica: </p><ul><li> <strong>Fuso horário</strong>: As datas e horas estão em UTC.</li><li> <strong>Moeda</strong>: o campo event_revenue_usd está em USD.</li></ul><p><strong>Valores com vírgulas:</strong> As vírgulas estão contidas entre aspas duplas ", por exemplo,<code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="Opções de armazenamento">

<div id="caution" />

> ❗️ **Cuidado!**
>
> Se você estiver usando a opção de armazenamento própria do profissional de marketing:
>
> * Verifique se você está em conformidade com os regulamentos de privacidade de dados, como a GDPR e políticas de retenção de dados de ad network/SRN.
> * Não use a solução de armazenamento própria para enviar dados a terceiros.

* Os dados são registrados em um proprietário de armazenamento de sua escolha da seguinte forma:
  * Armazenamento da AppsFlyer
  * Armazenamento do cliente — AWS, GCS, Azure, Yandex, BigQuery e Snowflake
* Você pode alterar a seleção de armazenamento a qualquer momento.
* Se você alterar o armazenamento, acontecerá o seguinte:
  * Começamos a registrar no armazenamento recém-selecionado dentro de uma hora.
  * Continuamos registrando no armazenamento existente durante um período de transição de 7 dias. O tempo de expiração do período de transição é exibido na interface do usuário. Use o período de transição para atualizar seus processos de carregamento de dados. Você pode reiniciar o período de transição ou reverter para o bucket da AppsFlyer, se necessário.
  * **Mudança de armazenamento:** você pode migrar de uma opção de armazenamento para outra usando a opção de multi-armazenamento e enviando dados para múltiplos destinos simultaneamente. Uma vez concluídos a migração e os testes, exclua a opção de armazenamento de que você não precisa mais.

|  | Armazenamento de propriedade da AppsFlyer (AWS) | Armazenamento de propriedade do profissional de marketing (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Nome do bucket | Definido pela AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>: Sem restrição</li><li><Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: Configurado por você. Deve ter o prefixo af-.</li></ul>Exemplo: `af-datalocker-your-bucket-name` |
| Propriedade de armazenamento | A AppsFlyer | Marketer |
| Plataforma de armazenamento | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Credenciais para acessar os dados | Disponível na interface de usuário do Data Locker para os administradores da sua conta da AppsFlyer | Não conhecido pela AppsFlyer. Use as credenciais fornecidas pelo provedor da nuvem. |
| Retenção de dados | Os dados são excluídos após 14 dias | Responsabilidade do profissional de marketing |
| Solicitações de exclusão de dados | Responsabilidade da AppsFlyer | Responsabilidade do profissional de marketing |
| Segurança | A AppsFlyer controla o armazenamento. O cliente tem acesso de leitura. | O profissional de marketing controla o armazenamento<ul><li>**AWS**: A AppsFlyer requer a permissão getObject, ListBucket, DeleteObject, PutObject para o bucket. O bucket deve ser dedicado ao uso da AppsFlyer. Não o use para outros fins.</li><li>**GCS**: Consulte o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup">artigo de configuração do GCS</Anchor>.</li></ul> |
| Capacidade de armazenamento | Gerenciado pela AppsFlyer | Gerenciado pelo profissional de marketing |
| Controle de acesso usando endpoints VPC com políticas de bucket | Não aplicável | [Opcional] No AWS, se você implementar a segurança de endpoint VPC no nível do bucket, será necessário dar permissão aos servidores da AppsFlyer. |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **Aviso aos agentes de segurança no caso de armazenamento controlado pelo cliente**

Considere:

* O bucket ou destino é de uso exclusivo da AppsFlyer. Não deve haver outra entidade envolvida em um determinando destino.
* Você pode excluir dados no destino 25 horas após gravarmos os dados.
* Os dados que gravamos no destino são uma cópia dos dados que já estão em nossos servidores. Os dados continuam em nossos servidores de acordo com nossa política de retenção.
* Por razões técnicas, às vezes deletamos e reescrevemos os dados. Por isso, precisamos de permissões de exclusão e listagem. Nenhuma permissão é um risco de segurança para você. No caso da lista, somos a única entidade escrevendo no bucket. No caso de exclusão, podemos regenerar os dados.
* Para informações adicionais, você pode entrar em contato com nossa equipe de segurança através do e-mail [hello@appsflyer.com](mailto:hello@appsflyer.com) ou do seu CSM.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="Princípios de conexões múltiplas (mais de um destino)">

No Data Locker você pode enviar alguns ou todos os seus dados para dois destinos (definidos nas configurações de conexão). Por exemplo, você pode enviar dados do App A para AWS, e dados do App B para GCS.

Cada conexão consiste em um conjunto completo de configurações do Data Locker, incluindo um destino. As configurações de conexão são independentes umas das outras.

Ao administrar suas conexões, considere:

* Nas configurações do Data Locker, as conexões são mostradas em abas. Cada conexão tem sua própria aba de configuração a partir da qual você pode gerenciar a conexão. O ícone de cada aba representa o tipo de armazenamento.
* Para ver os detalhes da conexão, duplicar uma conexão, ou excluir uma conexão, clique em ⋮ (opções).

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="track-connection-changes-in-the-audit-log" />

<Accordion title="Acompanhe alterações de conexão no log de auditoria">

Você pode visualizar as alterações de conexão do Data Locker no log de auditoria, disponível no centro de segurança no dashboard da AppsFlyer. Use o log de auditoria para confirmar se uma alteração foi feita, quando ela ocorreu e quem a fez. Isso pode ajudar a resolver problemas como dados ausentes ou mudanças inesperadas de conexão, sem que você precise entrar em contato com o suporte.

Você pode acompanhar os seguintes eventos:

* Nova conexão criada
* Conexão atualizada
* Conexão desativada
* Conexão excluída

**Para acessar o log de auditoria:**

1. Na barra de navegação superior, abra o menu da conta em <Image alt="HQ1 2025-05-05 10.48.04.png" src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" width="4.24%" />.
2. Selecione **Centro de segurança.**
3. Na seção do **log de auditoria**, clique em Ver log de auditoria.
4. Filtrar por serviço: **Datalocker** para ver entradas relacionadas.

Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/audit-log">Log de auditoria.</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e Limitações">

| **Caraterística** | Observações |
| --- | --- |
| Redes de anúncios | Não deve ser usado por ad networks |
| Agências | Não deve ser usado por agências |
| Fuso horário específico do aplicativo | Não aplicável. As pastas do Data Locker são divididas em horas usando UTC. Os eventos reais contêm horários em UTC. Você pode converter os horários para qualquer outro fuso horário conforme necessário. Independentemente do fuso horário do aplicativo, o atraso da ocorrência do evento até que seja registrado no Data Locker permanece o mesmo. |
| Moeda específica do aplicativo | Indisponível |
| Limitações de tamanho | Não aplicável |
| Atualização dos dados | Os dados são atualizados de acordo com a atualização específica dos dados do relatório, detalhada <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#relatórios-de-dados-brutos">neste artigo</Anchor>. |
| Histórico de dados | Indisponível. Se você precisar do histórico de dados, alguns relatórios, mas não todos, oferecem essa opção por meio da Pull API. |
| Dados restritos | Os campos em alguns relatórios são restritos devido a limitações de privacidade. <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">Saiba mais</Anchor> |
| Acesso do usuário | Somente <Anchor target="_blank" href="/marketers/pt/docs/user-management">usuários da conta com as permissões necessárias</Anchor> podem configurar o Data Locker. |
| Aplicativo único/múltiplos aplicativos | Suporte para múltiplos aplicativos. O Data Locker funciona no nível da conta |
| Máximo de conexões | Por padrão, cada conta pode ter até **2 conexões do Data Locker**. Para solicitar conexões adicionais, **entre em contato com seu CSM**. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolução de problemas">

* **Sintoma**: não é possível recuperar dados usando o AWS CLI
* **Mensagem de erro**: ocorreu um erro (AccessDenied) ao chamar a operação ListObjectsV2: Acesso negado.
* **Causa**: as credenciais AWS que estão sendo usadas não são as credenciais corretas para o bucket da AppsFlyer. Isso pode ser causado por ter credenciais múltiplas ou inválidas no seu dispositivo.
* Solução:
  1. Use um método diferente, como [Cyberduck](/docs/data-locker-for-marketers#cyberduck) para acessar o bucket, ou seja, não a CLI. Faça isso para verificar se as credenciais que você está usando estão funcionando. Se você conseguir se conectar usando o Cyberduck, isso indica um problema no cache das credenciais.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">Atualize o cache de credenciais do AWS</Anchor>.  
     **Captura de tela do AWS** ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

<div id="aws-data-retrieval" />

## Recuperação de dados do AWS

Use sua ferramenta de recuperação de dados de AWS preferida, a AWS CLI ou uma das ferramentas descritas nas seções a seguir. Atenção! As instruções exatas são adequadas para buckets de propriedade da AppsFlyer. Ajuste as instruções conforme necessário se você estiver se conectando ao seu bucket.

<div id="aws-cli" />

<Accordion title="CLI da AWS">

**Antes de começar**:

* Instale o CLI da AWS no seu computador.
* Na AppsFlyer, acesse o Data Locker e recupere as informações contidas no painel de credenciais.

**Para usar o AWS CLI**:

1. Abra o terminal. Para fazer isso no Windows, &lt;Windows> + &lt;R>, clique em **OK**.  
   A janela da linha de comando é aberta.
2. Digite **aws configure.**
3. Digite a Chave de acesso da AWS como aparece no painel de credenciais.
4. Digite sua chave secreta da AWS conforme aparece no painel de credenciais.
5. Digite **eu-west-1.**
6. Clique em Enter (None).

Use os comandos da CLI a seguir, conforme necessário.

Nos comandos a seguir, o valor de `{home-folder}` pode ser encontrado

**Para listar pastas em seu bucket:**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### Para listar arquivos e pastas

Há três tipos de pastas no seu repositório do Data Locker:

* Tipo de relatório `t=`
* Data `dt=`
* Hora `h=`

Para listar todos os relatórios de um tipo de relatório específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

Para listar todos os relatórios de um tipo de relatório específico para um dia específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

Para listar todos os relatórios de um relatório específico, em uma hora específica de um dia específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=instalações/dt=2019-01-17/h=23
```

Para fazer o download de arquivos de uma data específica:

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

**Antes de começar**:

* Instale o cliente Cyberduck.
* Na AppsFlyer, acesse o Data Locker e recupere as informações contidas no painel de credenciais.

**Para configurar o Cyberduck**:

1. No Cyberduck, clique em Action.
2. Selecione **New Bookmark**. A janela será aberta.
3. No primeiro campo (marcado como [1] na captura de tela abaixo) selecione **Amazon S3**. [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. Preencha os campos da seguinte maneira:
   * **Nickname:** texto livre
   * **Servidor:** s3.amazonaws.com
   * **Access Key ID:** copie a chave de acesso da AWS como ela aparece no painel de credenciais na AppsFlyer
   * **Secret Access Key:** copie a chave secreta do bucket conforme ela aparece no painel de credenciais da AppsFlyer.
   * **Path**: `{Nome do bucket}/{pasta Home}` Por exemplo: **af-ext-reports/1234-abc-ffffffff**
5. Feche a janela. Para fazer isso, clique no X no canto superior direito da janela.
6. Selecione a conexão.  
   Os diretórios de dados são exibidos.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Navegador Amazon S3">

**Antes de começar**:

* Instale o navegador Amazon S3.
* Na AppsFlyer, acesse o Data Locker e recupere as informações contidas no painel de credenciais.

**Para configurar o navegador Amazon S3**:

1. No navegador S3, clique em **Accounts** > **Add** **New Account**.  
   A janela Add New Account é aberta. [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. Preencha os campos da seguinte maneira:
   * **Account Name**: texto livre.
   * **Access Key ID**: copie a chave de acesso da AWS conforme exibida no painel de credenciais.
   * **Secret Access Key**: copie a Chave Secreta do bucket conforme ela aparece no painel de credenciais.
   * Selecione **Encrypt Access Keys** com uma senha e insira uma senha. Anote essa senha.
   * Selecione **Use secure transfer.**
3. Clique em **Save changes**.
4. Clique em **Buckets** > **Add External Bucket**.  
   A janela Add External Bucket é aberta.  
   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. Digite o **nome do bucket.** O nome do bucket tem o seguinte formato: `{Nome do Bucket}/{Pasta Home}`. Os valores necessários para o nome do bucket e a pasta Home aparecem na janela de credenciais.
6. Clique em **adicionar bucket externo.** O bucket é criado e é exibido no painel esquerdo da janela.  
   Agora você pode acessar os arquivos do Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports">Relatórios disponíveis via Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Como selecionar a ferramenta certa de envio de dados brutos</Anchor>

<div data-zendesk-anchors="data-locker=vis%C3%A3o-geral h_01HE2S6FANNTNB580CMHNX34YA=vis%C3%A3o-geral data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker set-data-locker-report-settings=definir-configura%C3%A7%C3%B5es-do-relat%C3%B3rio-do-data-locker h_01JS45N2DNWZBHP5PH8ZG6FBTF=definir-configura%C3%A7%C3%B5es-do-relat%C3%B3rio-do-data-locker h_01JS45N2DNEZZJRF2RKG1RM9NK=1-set-up-your-cloud-service h_01JS45N2DNVA0SHBA49G42GNFE=2-add-a-connection-to-your-cloud-service h_01K22P5FWJ96CPFJPW0XDCHNNJ=nota h_01JS4ASE6J6X1DD33PEGQAPXPA=aws-cloud-bucket-connection h_01JS4ASE6J587JPHAMCSBA2Z92=gcs-cloud-bucket-connection h_01JS4ASE6J4NC7M0TRFDT7F2X7=azure-cloud-bucket-connection h_01JS4ASE6JKFTM3FYAEKFHRW2M=yandex-cloud-bucket-connection h_01JS4ASE6JKV8WJG68RMHKVCE5=bigquery-data-warehouse-connection h_01JS4ASE6JBNE5BK04QDRM7CW4=snowflake-data-warehouse-connection h_01JTFRHNRRJB76JBXXT1TBNRBY=nota-1 h_01JS45N2DN8JTMQCK76PDBBWA4=3-set-the-report-output-settings h_01JSBTCZ5569RCV6W6QWT400R7=nota-2 h_01JS45N2DNMQAGFVHDDD5JGF2M=select-global-level-filters h_01JS45N2DN388YVP29DDBBBFBP=5-select-the-report h_01JVPJ9CG45JREBKP3ZQXKZWRZ=customize-or-duplicate h_01JS45N2DP4FK9EZYNTY2GX2GK=6-select-the-report-fields h_01JS45N2DPN7B73X0TRC82JW87=7-select-the-reportlevel-filters h_01JS45N2DPYYABS9NXFXP23ARA=8-remove-legacy-fields h_01JS45N2DPYNBG9VPCZJ481DFE=nota-3 nonempty-legacy-fields=campos-legados-n%C3%A3o-vazios h_01JSCC6KZNKJAVYSFCDDSE80YW=campos-legados-n%C3%A3o-vazios h_01JS45N2DPH1QAREYGN5H20T8R=9-save-the-connection h_01JS45N2DPNPXAEZ74J0ETP7BS=importante set-user-permissions=permiss%C3%B5es-do-usu%C3%A1rio h_01KH8D60TDTNS4EWNXJ4JPGXZ2=permiss%C3%B5es-do-usu%C3%A1rio manage-data-locker-access-and-ownership-admins=administradores h_01KH8D60TEFX2MCW00JT94F9AQ=administradores give-data-locker-access=pastas-por-hora h_01KH8D60TE541XMXWCVK0HZTJA=pastas-por-hora manage-ownership-and-editors=gerenciar-propriedade-e-editores h_01KH8D60TF69FN7KMBPMZHBW27=gerenciar-propriedade-e-editores review-filters-after-changing-ownership=revise-os-filtros-ap%C3%B3s-alterar-a-propriedade h_01KH8D60TFYMEY8FEPR4YKJRYJ=revise-os-filtros-ap%C3%B3s-alterar-a-propriedade h_01KH8D60TGVN75TMS9QES0G6CQ=nota-4 architecture=arquitetura-do-armazenamento-de-dados data-storage-architecture=arquitetura-do-armazenamento-de-dados h_01HE2S6FAN4H9DQ5HBTKSNJ72B=arquitetura-do-armazenamento-de-dados h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure hourly-folders=pastas-por-hora h_01HE2S6FAN7PBZ8M86FQVSN5KQ=pastas-por-hora h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=cuidado notice-to-security-officers-in-the-case-of-customercontrolled-storage=aviso-aos-agentes-de-seguran%C3%A7a-no-caso-de-armazenamento-controlado-pelo-cliente h_01HE2S6FANRVGYPRWWFA50JAQ4=aviso-aos-agentes-de-seguran%C3%A7a-no-caso-de-armazenamento-controlado-pelo-cliente h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination additional-information=informa%C3%A7%C3%B5es-adicionais h_01HE2S6FAP4SA77B0SX7R8JMTY=informa%C3%A7%C3%B5es-adicionais h_01JTFQMKN0046SNBB4YSRJMQG9=track-connection-changes-in-the-audit-log h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=recupera%C3%A7%C3%A3o-de-dados-do-aws h_01HE2S6FAPJMKX567HSAR16TCN=recupera%C3%A7%C3%A3o-de-dados-do-aws h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=para-listar-arquivos-e-pastas h_01HE2S6FAP31H9NK6V870FGXZF=para-listar-arquivos-e-pastas h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=veja-tamb%C3%A9m" />
