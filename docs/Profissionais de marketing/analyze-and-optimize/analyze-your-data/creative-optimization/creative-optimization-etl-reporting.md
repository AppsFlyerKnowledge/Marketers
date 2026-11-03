---
title: Creative Optimization—ETL relatórios
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-08-19T00:03:10Z'
  id: 19253873174801
  locale: pt
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/pt/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** o Creative Optimization ETL transfere seus dados de performance de criativos para o armazenamento em nuvem diariamente, para carregamento direto nos seus sistemas de business intelligence (BI), sem necessidade de exportações manuais. Escolha entre o **Standard Creative ETL**, que entrega uma estrutura fixa de relatório, e o **Custom Creative ETL**, que permite escolher exatamente quais dimensões, métricas e eventos incluir.

## Sobre o Creative Optimization ETL

O Creative Optimization ETL transfere automaticamente seus dados de performance de criativos para o armazenamento em nuvem diariamente, disponibilizando-os para carregamento programático nos seus sistemas de BI. Duas opções estão disponíveis, dependendo das suas necessidades e do seu plano de assinatura.

O **Standard Creative ETL** é configurado pelo Data Locker e entrega um relatório diário fixo com as principais dimensões de criativos e métricas de performance. Ele está disponível para todos os clientes de Otimização de criativos.

O **Custom Creative ETL** oferece controle total sobre o esquema do seu relatório (as dimensões, métricas e eventos que compõem o seu relatório e a ordem em que aparecem). Configure seu esquema diretamente na interface do Creative ETL, selecionando exatamente as dimensões, métricas, dimensões de IA e Eventos in-app de que você precisa, incluindo detalhamentos de retargeting e atribuição unificada. Ele está disponível para assinantes do plano Premium de Otimização de criativos.

<div id="standard-creative-etl" />

<Accordion title="Standard Creative ETL">

O Creative Optimization Extract Transform Load (ETL) equipa seus analistas de dados com todas as informações necessárias para análise de desempenho criativo. Ele consegue isso transmitindo automaticamente relatórios do Creative Optimization para armazenamento em nuvem para carregamento programático em seus sistemas de BI.

São fornecidos relatórios completos de desempenho no nível do ativo, incluindo todos os principais indicadores de desempenho (KPIs), KPIs de funil superior e inferior, dados de atribuição e dados de ativos do criativo.

O Creative Optimization ETL utiliza o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker</Anchor> para enviar dados de relatórios do Creative Optimization para armazenamento em nuvem. Você pode selecionar vários destinos de armazenamento, como um bucket de propriedade da AppsFlyer na Amazon Web Services (AWS) ou seu próprio armazenamento na AWS, GCS, Yandex, BigQuery, Snowflake e muito mais. O Data Locker é compatível com vários destinos, o que significa que você pode enviar todos os dados para um ou mais destinos, enviar dados específicos para determinados destinos e personalizar a entrega de dados de acordo com suas necessidades.

> 📘 **Atenção**
>
> O Standard Creative ETL tem um esquema fixo e não oferece suporte a eventos in-app, dimensões de IA nem detalhamentos de retargeting/unificados. Para um esquema totalmente personalizável, consulte [Custom Creative ETL](#custom-creative-etl) abaixo.

#### Comece agora

Esta seção descreve como configurar o Data Locker para relatórios de otimização de criativos.

**Pré-requisito**

* Uma assinatura do Premium de Otimização de criativos (entre em contato com seu gerente de sucesso do cliente da AppsFlyer)

**Para configurar o Data Locker:**

1. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">estas instruções</Anchor>.
2. Ao configurar o Data Locker, selecione **Creative** (abaixo de **Selecionar relatórios**), na página de configuração do Data Locker.

#### Editar configuração do Data Locker

Esta seção descreve como editar sua configuração existente do Data Locker para adicionar relatórios do Creative Optimization.

**Para adicionar relatórios do Creative Optimization ao Data Locker:**

1. Em **Integrações** no menu lateral principal da AppsFlyer, clique em **Data Locker**.
2. Selecione **Creative** (abaixo de **Selecionar relatórios**) na página de configuração do Data Locker.

#### Atualização dos dados

Depois de configurado, o relatório de Otimização de criativos é transmitido para o Data Locker uma vez por dia. Cada entrega inclui dados dos últimos 30 dias, transmitidos diariamente em UTC+12. O horário local exato depende do seu fuso horário:

* New York: UTC+12 − 5 = 7:00 AM
* Berlim: UTC+12 + 1 = 1:00 PM
* Xangai: UTC+12 + 8 = 8:00 PM

#### Dados disponíveis

Os seguintes dados do Creative estão disponíveis no Data Locker.

| Campo | Tipo de valor esperado |
| --- | --- |
| data | Sequência de caracteres |
| asset\_link | Sequência de caracteres |
| Data Locker - select Creative.jpg | string |
| fonte\_de\_mídia | Sequência de caracteres |
| campanha | Sequência de caracteres |
| id\_da\_campanha | Sequência de caracteres |
| Anúncio | Sequência de caracteres |
| id\_anúncio | Sequência de caracteres |
| conjunto\_de\_anúncios | Sequência de caracteres |
| id\_conjunto\_de\_anúncios | Sequência de caracteres |
| ativado | Sequência de caracteres |
| conjunto\_de\_anúncios | Sequência de caracteres |
| creative\_first\_seen | string |
| creative\_age | string |
| creative\_type | Sequência de caracteres |
| duration | string |
| end\_card\_type | string |
| geo | string |
| platforma | string |
| Orientação | string |
| Resolução | string |
| impressions | string |
| clicks | string |
| installs | string |
| CTR | string |
| CVR | string |
| IPM | string |
| custo | string |
| eCPI | string |
| reattributions | string |
| reengagements | string |
| CPM (custo por mil impressões) | string |
| roas\_d1 | string |
| roas\_d7 | string |
| roas\_d14 | string |
| roas\_d30 | string |
| roas\_d60 | string |
| roas\_d90 | string |
| retention\_d1 | Sequência de caracteres |
| retention\_d7 | string |
| retention\_d14 | Sequência de caracteres |
| retention\_d30 | string |
| retention\_d60 | Sequência de caracteres |
| retention\_d90 | Sequência de caracteres |
| revenue\_d1 | string |
| revenue\_d7 | Sequência de caracteres |
| revenue\_d14 | Sequência de caracteres |
| revenue\_d30 | string |
| revenue\_d60 | Sequência de caracteres |
| Revenue\_d90 | string |
| partner\_cpm | Sequência de caracteres |
| partner\_ctr | Sequência de caracteres |
| partner\_cvr | Sequência de caracteres |
| partner\_clicks | string |
| partner\_cost | string |
| partner\_ipm | string |
| partner\_impressions | string |
| partner\_installs | string |
| partner\_ecpi | string |

Veja as <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide#standard-metrics-and-dimensions">definições das métricas padrão e das métricas exclusivas da Otimização de criativos</Anchor>.

> 📘 **Atenção**
>
> Quando um anúncio não tem prévia disponível, as colunas `asset_link` e `creative` não serão preenchidas.

Os dados a seguir **não** estão disponíveis no Standard Creative ETL:

* Dimensão personalizada
* Métricas personalizadas
* https://support.appsflyer.com/hc/article_attachments/19284078965009
* Dados de IA (elementos e cenas)
* Dados de retargeting

</Accordion>

<div id="custom-creative-etl" />

<Accordion title="Custom Creative ETL">

O Custom Creative ETL oferece controle total sobre o esquema do seu relatório. Você configura relatórios diretamente na interface do Creative ETL, escolhendo dimensões, métricas, dimensões de IA, detalhamentos por tipo de atribuição e eventos in-app. Os dados são enviados diariamente ao seu destino no Data Locker.

Ao contrário do esquema fixo do Standard Creative ETL, o Custom Creative ETL permite que você crie relatórios exatamente do jeito que precisa:

* **Dados completos de eventos in-app**: inclua até 30 eventos in-app por relatório, com submétricas de contagem de eventos, usuários únicos, receita e custo por ação (CPA).
* **Detalhamentos por tipo de atribuição**: gere relatórios sobre aquisição de usuários, retargeting ou uma visualização unificada que combine ambos.
* **Dimensões de IA**: inclua tags de criativos geradas por IA (tags automáticas e dimensões personalizadas) junto com dados de performance padrão.
* **Configuração self-serve**: crie, edite e gerencie relatórios diretamente na interface do Creative ETL, sem necessidade de configuração de backend nem de envolvimento de um gerente de sucesso do cliente.

#### Antes de começar

Antes de configurar o Custom Creative ETL, verifique se os itens a seguir já estão em vigor:

* O Creative Optimization ETL está **disponível com um plano de assinatura Creative Optimization Premium.** O Custom Creative ETL está disponível exclusivamente no plano Premium. Entre em contato com seu representante da AppsFlyer para confirmar sua assinatura.
* **Permissões de administrador.** Somente usuários administradores podem criar, editar ou excluir configurações de relatórios de ETL.
* **Destino do Data Locker.** O Custom Creative ETL entrega dados a uma conexão do Data Locker. Você deve ter pelo menos uma conexão já configurada ou criar uma durante a configuração do relatório (consulte a Etapa 1 abaixo). Os destinos compatíveis incluem AWS S3, GCS, BigQuery, Snowflake, Azure Blob [beta] e Yandex [beta]. <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#data-freshness-explanations">Saiba mais</Anchor>

#### Configure o Custom Creative ETL

A configuração do Custom Creative ETL é um processo de três etapas: configurar o destino dos dados, definir os detalhes do relatório e selecionar o esquema (as colunas que aparecem na saída do relatório).

**Para configurar o Custom Creative ETL:**

1. Na AppsFlyer, acesse **Export** > **Creative ETL**.
2. Clique em **Criar relatório**.

##### Etapa 1 - Destino

Selecione ou configure a conexão do Data Locker para a qual seu relatório será enviado.

3. No menu suspenso **Data Locker connections**, selecione uma conexão existente.
   * Se você ainda não tiver uma conexão, clique em **+ Nova conexão no Data Locker**. Isso abre a página de configuração do Data Locker. Depois de criar uma conexão, volte para o Creative ETL e selecione-a no menu suspenso.
   * Você pode selecionar várias conexões se quiser que o mesmo relatório seja entregue a mais de um destino.
4. Clique em **próximo**.

##### Etapa 2 - Detalhes

Defina o nome e o tipo do relatório.

5. Insira um **nome do relatório**. Esse nome identifica o relatório na lista de relatórios e não pode ser alterado depois de salvo.

   > 📘 **Atenção**
   >
   > Use apenas letras, números e sublinhados. O nome deve ter entre 2 e 80 caracteres.

6. Selecione um **tipo de relatório**:

| Esta seção descreve como editar sua configuração existente do Data Locker para adicionar relatórios do Creative Optimization. | A descrição |
| --- | --- |
| Aquisição de usuários | Instalações de novos usuários atribuídas à mídia paga |
| Redirecionamento | Atividade de reengajamento e reatribuição |
| Unificado | Visualização combinada de aquisição de usuários e retargeting em um único relatório |

7. Clique em **próximo**.

##### Etapa 3 - Esquema

Selecione as dimensões, métricas, dimensões de IA e eventos in-app para incluir na saída do seu relatório.

> 📘 **O que é um esquema?**
>
> Um esquema define as colunas do seu relatório, quais dimensões (atributos como campanha, geolocalização ou tipo de criativo) e métricas (números de performance, como instalações, CTR ou ROAS) são incluídas e em que ordem. A ordem em que você seleciona os campos na interface do usuário determina a ordem das colunas no arquivo de saída.

9. Em **Dimensions**, selecione as dimensões de criativo e campanha que serão incluídas.

   > 📘 **Atenção**
   >
   > Os campos **Event date** (data de atribuição do evento), **App ID**, **Creative** e **Asset link** são obrigatórios e não podem ser removidos. Dois campos adicionais, `dt` (data da partição) e `version` (versão da execução para cenários de backfill), são sempre incluídos em todos os relatórios, mas ficam ocultos na UI.

10. Em **AI Dimensions**, selecione os campos de tag automática ou de dimensão personalizada que serão incluídos. Esses campos são gerados pelo pipeline de análise de criativos com IA da AppsFlyer.

    > 📘 **Atenção**
    >
    > As dimensões de IA são preenchidas apenas para criativos que foram processados pelo pipeline de tagueamento com IA. Pode haver um atraso até que as tags de IA fiquem disponíveis para criativos enviados recentemente.

11. Em **Metrics**, selecione os KPIs de performance que serão incluídos.
12. Em **eventos in-app**, selecione os eventos a serem incluídos. Cada evento selecionado inclui automaticamente quatro submétricas na saída do relatório: contagem de eventos, usuários únicos, receita e CPA.

    > 🚧 **Importante!**
    >
    > Você pode incluir no máximo **30 eventos in-app** por relatório.

13. Clique em **Salvar** para ativar o relatório.

O relatório agora está configurado. A primeira entrega ocorrerá na próxima execução diária.

#### Editar um relatório existente

Você pode modificar um relatório existente do Custom Creative ETL, incluindo seu schema, tipo de relatório e conexão de dados. Não é possível alterar o nome do relatório depois que o relatório é salvo.

**Para editar um relatório:**

1. No AppsFlyer, vá para **Export** > **Creative ETL**.
2. Na lista de relatórios, clique no ícone **Editar** (lápis) do relatório que você quer modificar.
3. Faça as alterações nas três etapas de configuração.
4. Vá para qualquer uma das seções e selecione a opção desejada.

> 📘 **Atenção**
>
> As alterações no schema se aplicam apenas às execuções futuras do relatório. Os arquivos entregues anteriormente não são atualizados retroativamente.
>
> As dimensões **Data do evento**, **ID do Aplicativo**, **Link do ativo** e **Criativo** são obrigatórias e não podem ser removidas.

Você também pode **duplicar** ou **excluir** um relatório usando os ícones de ação em cada linha.

> 🚧 **Importante!**
>
> Excluir um relatório remove permanentemente a configuração do relatório e todo o histórico de execuções associado. Essa ação não pode ser desfeita.

#### Gerenciamento de relatórios

A página Creative ETL lista todos os relatórios personalizados do Custom Creative ETL configurados para a sua conta. Para cada relatório, você pode ver o nome do relatório, o tipo de relatório e o carimbo de data/hora da última entrega bem-sucedida.

As seguintes ações estão disponíveis nos ícones de ação em cada linha de relatório:

* **Visualizar** (ícone de olho): abre uma visualização somente leitura da configuração completa do relatório.
* **Editar** (ícone de lápis): abre o relatório no modo de edição.
* **Duplicar** (ícone de cópia): cria uma cópia da configuração do relatório.
* **Excluir** (ícone de lixeira) remove permanentemente o relatório e o histórico de execuções.

> 📘 **Observação**
>
> Cada conta pode ter no máximo **5 relatórios ativos de Creative ETL personalizados**.

Se você tiver um relatório padrão de Creative ETL configurado via Data Locker, um banner de notificação aparecerá na parte superior da página do Creative ETL. Ao clicar, você será direcionado ao Data Locker, onde o relatório padrão é configurado.

#### Dados

**Cronograma de entrega**

Os relatórios de Creative ETL personalizado são entregues uma vez por dia. Para monitorar o status da entrega, verifique o carimbo de data/hora de **Última execução bem-sucedida** na lista de relatórios do Creative ETL.

**Janela de lookback**

Cada entrega diária inclui dados de uma janela de lookback de 30 dias. Cada arquivo reflete a janela móvel completa, não apenas o dia mais recente. Ao carregar dados no seu sistema de BI, substitua os dados de todas as datas na janela de entrega em vez de acrescentar apenas as linhas do dia mais recente.

**Estrutura de pastas**

Os arquivos de dados são organizados na sua pasta de entrega com base na configuração escolhida na configuração da conexão do Data Locker:

* **Unificado (padrão):** Todos os aplicativos são incluídos em arquivos de dados unificados. Use o campo `app_id` no nível da linha para distinguir os aplicativos ao consumir os dados.
* **Por aplicativo:** Os dados são organizados em subpastas, uma por aplicativo.

Consulte <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#app-segregation">segregação por aplicativo no Data Locker</Anchor> para saber mais.

#### Referência do esquema

##### Campos obrigatórios

Os campos a seguir estão sempre incluídos em todos os relatórios de Creative ETL personalizado e não podem ser removidos.

| Campo | Tipo de valor esperado | A descrição |
| --- | --- | --- |
| `event_date` | Sequência de caracteres | A data à qual o evento ou a instalação é atribuído |
| `conjunto_de_anúncios` | string | ID do Aplicativo AppsFlyer |
| `Criativo` | string | Nome do criativo |
| `asset_link` | string | URL para a prévia do recurso criativo. Não é preenchido quando não há prévia disponível |
| `dt` | String (YYYY-MM-DD) | Data da partição, a data em que os dados do relatório foram gravados no armazenamento |
| `version` | string | Identificador da versão da execução; é incrementado em reexecuções de preenchimento retroativo no mesmo `dt` |

##### Dados

Você pode selecionar qualquer combinação das seguintes dimensões para incluir no seu relatório.

| Campo | Tipo | A descrição |
| --- | --- | --- |
| `ativado` | string | Nome da aplicação |
| `anúncio` | Sequência de caracteres | Ad name |
| `id_anúncio` | string | ID do anúncio |
| `conjunto_de_anúncios` | Sequência de caracteres | Nome do adset |
| `id_conjunto_de_anúncios` | Sequência de caracteres | ID do conjunto de anúncios |
| `agency` | Sequência de caracteres | Agência responsável pela veiculação do anúncio |
| `Twitter` | Sequência de caracteres | Campaign name |
| `id_da_campanha` | string | ID da campanha |
| `Canal` | string | Canal dentro da hierarquia da fonte de mídia |
| `creative_age` | string | Número de dias em que um criativo foi veiculado, calculado a partir da primeira impressão, clique ou instalação recebida pela AppsFlyer |
| `creative_similarity` | string | Agrupa criativos de imagem e vídeo que compartilham o mesmo tema visual ou conceito |
| `creative_type` | string | Tipo de recurso (por exemplo, imagem, vídeo ou jogável) |
| `duração` | string | Duração do vídeo em segundos (para criativos em vídeo) |
| `end_card` | string | Nome do cartão final |
| `end_card_duration` | string | Duração de exibição do cartão final em segundos |
| `end_card_orientation` | string | Orientação do cartão final (retrato ou paisagem) |
| `end_card_resolution` | string | Resolução do cartão final |
| `end_card_type` | string | Tipo do cartão final |
| `first_seen` | string | Data em que os dados de performance do criativo foram recebidos pela primeira vez |
| `geo` | String (ISO 3166-1 alfa-2) | Código do país |
| `fonte_de_mídia` | string | Canal de mídia (ad network) |
| `Orientação` | string | Orientação do criativo (retrato ou paisagem) |
| `platforma` | string | Plataforma do dispositivo (iOS ou Android) |
| `Resolução` | Sequência de caracteres | Data Locker - select Creative.jpg |
| `Visão geral: use o Data Locker para transmitir relatórios do Creative Optimization de forma automática e contínua para armazenamento em nuvem para carregamento programático eficiente em seus sistemas de BI.` | string | Classificação do tipo de texto do criativo |

##### Dimensões de IA

As dimensões de IA são geradas pelo mecanismo de análise criativa por IA da AppsFlyer e incluem auto-tags, smart tags e dimensões personalizadas.

| Grupo | Prefixo do campo | A descrição |
| --- | --- | --- |
| Auto-tags | `at_` | Tags geradas por IA para elementos criativos, cenas, emoções e atributos narrativos. As tags disponíveis são específicas da conta |
| [Em breve] Smart tags | `cd_ai_label` | Tags inteligentes geradas por IA |
| Dimensão personalizada | `cd_` | Atributos criativos definidos pelo usuário e configurados para a sua conta |

> 📘 **Atenção**
>
> As dimensões de IA são preenchidas apenas para criativos que foram processados pelo pipeline de marcação de IA. Criativos enviados recentemente podem não ter tags de IA disponíveis imediatamente.

##### Metrics

| Campo | Tipo de valor esperado | A descrição |
| --- | --- | --- |
| `impressions` | Inteiro | Número de impressões de anúncios |
| `clicks` | Inteiro | Número de cliques em anúncios |
| `installs` | Inteiro | Número de instalações atribuídas ao criativo |
| `reattributions` | Inteiro | Número de reatribuições (retargeting) |
| `reengagements` | Inteiro | Número de reengajamentos (retargeting) |
| `cost` | Decimal | Gasto total com anúncios |
| `CTR` | Decimal | Taxa de cliques (cliques / impressões) |
| `CVR` | Decimal | Taxa de conversão (instalações / cliques) |
| `IPM` | Decimal | Instalações por mil (instalações por 1,000 impressões) |
| `CPM (custo por mil impressões)` | Decimal | Custo por mil (custo por 1,000 impressões) |
| `eCPI` | Decimal | Custo efetivo por instalação |
| `roas_d0` | Decimal | Retorno sobre o gasto em anúncios no dia 0 |
| `roas_d1` | Decimal | Retorno sobre o gasto em anúncios no dia 1 |
| `roas_d3` | Decimal | Retorno sobre o gasto em anúncios no dia 3 |
| `roas_d7` | Decimal | Retorno sobre o gasto em anúncios no dia 7 |
| `roas_d14` | Decimal | Retorno sobre o gasto em anúncios no dia 14 |
| `roas_d30` | Decimal | Retorno sobre o gasto em anúncios no dia 30 |
| `roas_d60` | Decimal | Retorno sobre o gasto em anúncios no dia 60 |
| `roas_d90` | Decimal | Retorno sobre o gasto em anúncios no dia 90 |
| `retention_d0` | Decimal | Taxa de retenção do dia 0 |
| `retention_d1` | Decimal | Taxa de retenção do dia 1 |
| `retention_d3` | Decimal | Taxa de retenção no dia 3 |
| `retention_d7` | Obrigatório | Taxa de retenção no dia 7 |
| `retention_d14` | Obrigatório | Taxa de retenção no dia 14 |
| `retention_d30` | Obrigatório | Taxa de retenção no dia 30 |
| `retention_d60` | Obrigatório | Taxa de retenção no dia 60 |
| `retention_d90` | Obrigatório | Taxa de retenção no dia 90 |
| `unique_users_0` | Inteiro | Usuários únicos no dia 0 |
| `unique_users_1` | Inteiro | Usuários únicos no dia 1 |
| `unique_users_3` | Inteiro | Usuários únicos no dia 3 |
| `unique_users_7` | Inteiro | Usuários únicos no dia 7 |
| `unique_users_14` | Inteiro | Usuários únicos no dia 14 |
| `unique_users_30` | Inteiro | Usuários únicos no dia 30 |
| `unique_users_60` | Inteiro | Usuários únicos no dia 60 |
| `usuarios_únicos_90` | Inteiro | Usuários únicos no Dia 90 |
| `receita_d0` | Decimal | Receita total no dia 0 |
| `revenue_d1` | Decimal | Receita total no dia 1 |
| `receita_d3` | Decimal | Receita total no dia 3 |
| `revenue_d7` | Decimal | Receita total no dia 7 |
| `revenue_d14` | Decimal | Receita total no dia 14 |
| `revenue_d30` | Decimal | Receita total no dia 30 |
| `revenue_d60` | Decimal | Receita total no dia 60 |
| `Revenue_d90` | Decimal | Receita total no dia 90 |
| `receita_de_anuncios_d0` | Decimal | Receita de anúncios no Dia 0 |
| `receita_de_anuncios_d1` | Decimal | Receita de anúncios no dia 1 |
| `ad_revenue_d3` | Obrigatório | Receita de anúncios no dia 3 |
| `ad_revenue_d7` | Obrigatório | Receita de anúncios no dia 7 |
| `ad_revenue_d14` | Obrigatório | Receita de anúncios no dia 14 |
| `ad_revenue_d30` | Obrigatório | Receita de anúncios no dia 30 |
| `ad_revenue_d60` | Obrigatório | Receita de anúncios no dia 60 |
| `Página 1` | Obrigatório | Receita de anúncios no dia 90 |
| `partner_impressions` | Inteiro | Impressões conforme reportado pela fonte de mídia |
| `partner_clicks` | Inteiro | Cliques conforme reportado pela fonte de mídia |
| `partner_installs` | Inteiro | Instalações conforme reportado pela fonte de mídia |
| `partner_cost` | Obrigatório | Custo conforme reportado pela fonte de mídia |
| `partner_cpm` | Obrigatório | CPM conforme reportado pela fonte de mídia |
| `partner_ctr` | Decimal | CTR |
| `partner_cvr` | Decimal | CVR conforme relatado pela fonte de mídia |
| `partner_ipm` | Decimal | IPM conforme relatado pela fonte de mídia |
| `partner_ecpi` | Decimal | eCPI conforme relatado pela fonte de mídia |
| `partner_video_viewed_2s` | Inteiro | Visualizações de vídeo em 2 segundos (reportadas pelo parceiro) |
| `partner_video_viewed_3s` | Inteiro | Visualizações de vídeo em 3 segundos (reportadas pelo parceiro) |
| `partner_video_viewed_6s` | Inteiro | Visualizações de vídeo em 6 segundos (reportadas pelo parceiro) |
| `partner_engaged_views_6s` | Inteiro | Visualizações engajadas em 6 segundos (reportadas pelo parceiro) |
| `partner_engaged_views_15s` | Inteiro | Visualizações engajadas em 15 segundos (reportadas pelo parceiro) |
| `partner_video_started` | Inteiro | Inícios de vídeo (reportados pelo parceiro) |
| `partner_video_25p_views` | Inteiro | Vídeo reproduzido até 25% (reportado pelo parceiro) |
| `partner_video_50p_views` | Inteiro | Vídeo reproduzido até 50% (reportado pelo parceiro) |
| `partner_video_75p_views` | Inteiro | Vídeo reproduzido até 75% (reportado pelo parceiro) |
| `conclusoes_de_video_do_parceiro` | Inteiro | Conclusões de vídeo (informadas pelo parceiro) |

##### Eventos in-app

Os eventos in-app aparecem no relatório como colunas de métricas no formato `{event_name}.{sub_metric}`. Quando você seleciona um evento, as quatro submétricas são incluídas automaticamente. Por exemplo, selecionar `af_purchase` gera as seguintes colunas: `af_purchase.event_count`, `af_purchase.unique_users`, `af_purchase.revenue` e `af_purchase.cpa`.

| Submétrica | A descrição |
| --- | --- |
| `contagem_de_eventos` | Número total de vezes que o evento foi acionado |
| `utilizadores_únicos` | Número de usuários únicos que acionaram o evento |
| `revenue` | Receita total atribuída ao evento |
| `cpa` | Custo por ação (custo / contagem de eventos do evento) |

Limites:

* Máximo de **30 eventos in-app** por relatório.
* Os eventos disponíveis são específicos da conta e refletem os eventos que seus aplicativos enviam ativamente para a AppsFlyer.

#### Limitações

| Limitação | Atenção |
| --- | --- |
| Relatórios por conta | Máximo de 5 relatórios ativos por conta |
| https://support.appsflyer.com/hc/article_attachments/19276693230353 | Máximo de 30 eventos por relatório |
| Total de colunas por relatório | Máximo de 150 colunas (dimensões + métricas + submétricas de eventos in-app combinadas) |
| Data Locker - select Creative.jpg | Os dados estão disponíveis para uma janela de lookback de 30 dias. Os dados históricos fora desta janela não estão disponíveis. |
| Frequência de entrega | Uma vez por dia. A entrega intradiária não é suportada |
| Disponibilidade da dimensão de IA | As dimensões de IA são preenchidas apenas para criativos processados pelo pipeline de marcação por IA. Criativos enviados recentemente podem apresentar um atraso |
| Limite de métricas personalizadas | Ainda não há suporte |
| Ações de conversão (web) | Ainda não há suporte |
| Seleção de aplicativos | Todos os aplicativos da sua conta são incluídos em cada relatório. A capacidade de filtrar por aplicativos específicos está planejada para uma versão futura |

</Accordion>

## Perguntas frequentes

Uma lista de perguntas frequentes sobre relatórios de ETL.

<div id="whats-the-difference-between-standard-creative-etl-and-custom-creative-etl" />

<Accordion title="Qual é a diferença entre o ETL criativo padrão e o ETL criativo personalizado?">

O **ETL criativo padrão** é configurado na página Select reports do Data Locker e entrega um conjunto fixo de campos (schema) uma vez por dia. Ele não oferece suporte a eventos in-app, retargeting, detalhamentos unificados nem dimensões de IA.

O **ETL criativo personalizado** é configurado diretamente na interface do AppsFlyer com um conjunto de campos totalmente personalizável. Você pode incluir até 30 eventos in-app, dimensões de IA e detalhamentos de aquisição de usuários/retargeting/unificados, sem necessidade de configuração de backend nem do envolvimento de um gerente de sucesso do cliente.

</Accordion>

<div id="can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time" />

<Accordion title="Posso executar o ETL criativo padrão e o ETL criativo personalizado ao mesmo tempo?">

sim, sim, Ambos podem ser executados em paralelo. Se você tiver um relatório de ETL criativo padrão ativo, um banner de notificação aparecerá na página Creative ETL com um link para sua configuração do Data Locker.

</Accordion>

<div id="can-i-have-multiple-custom-creative-etl-reports-with-different-report-types" />

<Accordion title="Posso ter vários relatórios de ETL criativo personalizado com tipos de relatório diferentes?">

sim, sim, Cada relatório é configurado com um único tipo de relatório (Aquisição de usuários, retargeting ou Unificado), e você pode criar até 5 relatórios por conta.

</Accordion>

<div id="how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report" />

<Accordion title="Como adiciono novos eventos in-app a um relatório de ETL criativo personalizado existente?">

Acesse **Export** > **Creative ETL**, clique no ícone **Edit** do relatório, vá para a **Etapa 3 (Schema)** e adicione os novos eventos. As alterações entram em vigor na próxima entrega diária.

</Accordion>

<div id="what-happens-if-a-report-runs-more-than-once-on-the-same-day" />

<Accordion title="O que acontece se um relatório for executado mais de uma vez no mesmo dia?">

Se um relatório for executado novamente (normalmente durante um backfill), cada execução receberá um valor de `version` incrementado. Sempre use a versão mais alta disponível para uma determinada partição `dt`.

</Accordion>

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide">Guia para a otimização de criativos</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports">Relatórios do Data Locker para anunciantes</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup">Configurar o Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Configure e use os relatórios de Cost ETL do ROI360</Anchor>

<div data-zendesk-anchors="about-creative-optimization-etl-reporting=sobre-o-creative-optimization-etl h_01KW7A0CWMCFQA7K6YE909BVW4=sobre-o-creative-optimization-etl h_01KW7A0CWMH2SCPQ917TKASCC7=standard-creative-etl h_01KW7A0CWMJDR014M6JSA2HBHY=aten%C3%A7%C3%A3o get-started=comece-agora h_01KW7A0CWM2SPE4RYFJKZBDKJG=comece-agora edit-data-locker-configuration=editar-configura%C3%A7%C3%A3o-do-data-locker h_01KW7A0CWMAR0E52M7T6PXMCKT=editar-configura%C3%A7%C3%A3o-do-data-locker data-freshness=atualiza%C3%A7%C3%A3o-dos-dados h_01KW7A0CWM9K9J7X64S14TX2AE=atualiza%C3%A7%C3%A3o-dos-dados available-data=dados-dispon%C3%ADveis h_01KW7A0CWM1JYVQXKBDH06X1BA=dados-dispon%C3%ADveis h_01KW7A0CWMT7Q8BFTB8WAT7M0W=aten%C3%A7%C3%A3o-1 h_01KW7A0CWNZMPD7RSX41VNGSCF=custom-creative-etl before-you-begin=antes-de-come%C3%A7ar h_01KW7A0CWNK0R6XAB37E5ZP7KG=antes-de-come%C3%A7ar set-up-custom-creative-etl=configure-o-custom-creative-etl h_01KW7A0CWN2DZFZP3YK23ZW9EH=configure-o-custom-creative-etl h_01KW7A0CWNQJT83A9KAE8E7XHD=etapa-1---destino h_01KW7A0CWNH69H47EF7FAV1FRF=etapa-2---detalhes h_01KW7A0CWN0M4ZFRPQ7BN9TRTC=aten%C3%A7%C3%A3o-2 h_01KW7A0CWNG5PVQNC8ED1RXV28=etapa-3---esquema h_01KW7A0CWNER5KD46VJHE1X0VH=o-que-%C3%A9-um-esquema h_01KW7A0CWNJYPD5TXZ301PMF7S=aten%C3%A7%C3%A3o-3 h_01KW7A0CWN4NWNP10TAYD26GCQ=aten%C3%A7%C3%A3o-6 h_01KW7A0CWNFWY5BYGVPPXTYQ1X=importante edit-an-existing-report=editar-um-relat%C3%B3rio-existente h_01KW7A0CWNVJJTVW1MP0V25ZC5=editar-um-relat%C3%B3rio-existente h_01KW7A0CWNFZCW1NNBY2H0BSDS=aten%C3%A7%C3%A3o-5 h_01KW7A0CWNY50EV4EDS3BWGP6S=importante-1 report-management=gerenciamento-de-relat%C3%B3rios h_01KW7A0CWNRKGS9TJ4Y2H7JD5S=gerenciamento-de-relat%C3%B3rios h_01KW7A0CWNN3MN0S8Z563BYQ97=observa%C3%A7%C3%A3o data-delivery=dados h_01KW7A0CWNS62EYWZ8V41E7RRY=dados schema-reference=refer%C3%AAncia-do-esquema h_01KW7A0CWNWM3JTMEFF8B3SPXG=refer%C3%AAncia-do-esquema h_01KW7A0CWNP32RKD6YW1GNPNEE=campos-obrigat%C3%B3rios h_01KW7A0CWNJRT87NYJQ19YHSSG=dados-1 h_01KW7A0CWNTSGC4BPEBME4WWNC=dimens%C3%B5es-de-ia h_01KW7A0CWNNA03BG2BAQ4MGGMX=aten%C3%A7%C3%A3o-6 h_01KW7A0CWN6H39Q9D7SX2TFXAF=metrics h_01KW7A0CWP4JQSDP8E2BQESE2A=eventos-in-app limitations=limita%C3%A7%C3%B5es h_01KW7A0CWPJ8W3ZE2JZ9YTZFQF=limita%C3%A7%C3%B5es faq=perguntas-frequentes h_01KW9K4YXMJ14TX6FMGYY4811K=perguntas-frequentes h_01KW9K4YXM8E6ZF226DTTVZHK8=whats-the-difference-between-standard-creative-etl-and-custom-creative-etl h_01KW9K4YXMNDT73BPAV1CC5JZ5=can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time h_01KW9K4YXM3F3W45MTNDHS9DM9=can-i-have-multiple-custom-creative-etl-reports-with-different-report-types h_01KW9K4YXMVH2NSM46S63EVX01=how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report h_01KW9K4YXMDQZHF5TZGQE1NR0P=what-happens-if-a-report-runs-more-than-once-on-the-same-day h_01KW7A0CWP90HES8D1S2A1PF6X=consulte-tamb%C3%A9m" />
