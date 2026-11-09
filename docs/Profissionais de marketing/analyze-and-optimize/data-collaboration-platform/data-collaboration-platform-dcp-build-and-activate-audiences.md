---
title: Plataforma de colaboração de dados (DCP) - crie e ative audiências
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
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-08-18T00:06:57Z'
  id: 24522739719057
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/24522739719057
---
> **Em resumo:** Crie audiências de alto valor em colaborações do DCP usando dados compartilhados e ative-as em sites de parceiros de mídia ou serviços em nuvem para maximizar o impacto da campanha.

<div id="about-dcp-audiences" />

## Sobre as audiências do DCP

O processo de criar audiências a partir de um amplo conjunto de dados envolve a combinação de diferentes conjuntos de dados para gerar dados enriquecidos, que podem ser usados para alcançar exatamente os consumidores que você deseja. A audiência pode ser criada usando conjuntos de dados combinados de mais de uma parte ou fornecidos apenas por uma parte. Em ambos os casos, o colaborador que fornece os dados concede permissões e direitos de acesso de acordo com os termos acordados. Depois de criar uma audiência, você pode enviá-la para seus parceiros de mídia para ativação ou para seu serviço de nuvem.

<div id="build-an-audience" />

## Crie sua audiência

As seguintes ferramentas estão disponíveis:

* **Audience builder visual:** uma ferramenta fácil de usar que permite que usuários sem conhecimentos técnicos criem segmentos de audiências sem precisar de SQL. Permite a segmentação avançada de audiências usando uma interface gráfica.
* **Audience builder com SQL:** uma consulta de SQL que permite consultar os dados sem restrições. Requer experiência com SQL.

<div id="key-features" />

#### Principais características

| Audience builder visual | Audience builder com SQL |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>Suporte a uma fonte de cada colaborador ou várias fontes de um único colaborador | Suporte a várias fontes de ambas as partes |
| <span id="supports-using-overlapping-data-only"></span>No caso de uma fonte para cada colaborador, somente é possível usar dados sobrepostos | Suporte a consultas de todos os dados |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>Suporte à recuperação de valores dentro do intervalo de atributos selecionado | Suporte a consultas de valores além do intervalo selecionado |

Saiba como <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">preparar dados de fonte</Anchor> para maximizar as taxas de correspondência entre conjuntos de dados de colaboradores.

<div id="visual-audience-builder" />

<Accordion title="Audience builder visual">

**Siga as etapas abaixo para criar audiências usando o Audience builder visual:**

<div id="note" />

> 📘 **Nota**
>
> Verifique se você tem a permissão para <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">criar audiências</Anchor>.

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**

   <Image align="center" alt="Clique em Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="245px" />
2. Em **Colaborações**, clique na colaboração relevante.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. Em seguida, clique em **Nova audiência** > **Audience builder visual**.  
   **Atenção:** Pelo menos uma fonte deve ser vinculada antes que você possa criar uma audiência.

   <Image align="center" alt="New Aud Visual audience builder.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. Siga as etapas da demonstração do **Audience builder** abaixo:

<div id="step-1-details-and-sources" />

#### Passo 1: Detalhes e fontes

A audiência pode ser criada usando dados de um único colaborador ou mesclando uma fonte de cada colaborador para criar uma fonte de dados combinada.

<Image align="center" alt="New aud.png" src="https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png" />

1. **Nome da audiência:** nome escolhido para a colaboração nessa audiência.
2. **Selecionar fontes -** selecione uma fonte na lista suspensa:
   * Para uma colaboração unilateral: selecione sua própria fonte ou a fonte do seu colaborador.
   * Select a media partner connection.png

     <div id="note-1" />

     > 📘 **Atenção**
     >
     > * **Atenção:** Quando ambas as fontes compartilham usuários que se cruzam, o painel direito mostra um resumo dessa intersecção, fornecendo um número estimado de usuários comuns a ambas as fontes.
     > * As fontes de dados transacionais não estarão disponíveis na lista suspensa de fontes. Veja [Como trabalhar com fontes de dados transacionais](#trabalhar-com-fontes-de-dados-transacionais) abaixo.

3. **Método de combinação de dados:** selecione a partir de quais dados você deseja usar para criar a audiência:
   * **Usuários cruzados** - inclui apenas usuários que aparecem em ambas as fontes (as suas e as do seu colaborador).
   * **Apenas usuários da minha fonte** - inclui apenas usuários que fazem parte da sua fonte. Exclui todos os usuários que aparecem na fonte do seu colaborador.
   * **Apenas usuários da fonte do colaborador** - inclui apenas usuários da fonte do colaborador. Exclui todos os usuários que aparecem na sua fonte.  

     **Atenção:** essas três opções só estarão disponíveis se as permissões da fonte incluírem o seguinte fluxo "**Criar audiências**" > "**Pode usar todos os dados** - **Conjunto de dados universal**", que deve ser ativado. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#permissões-de-compartilhamento">Saiba mais sobre permissões de fonte</Anchor>  

     <Image align="center" alt="can use all data permision enabled w arrow.png" src="https://files.readme.io/6f386c2383c75bf42da6cfdc4d662be0fdf7d623588480825e4a70f453d1f94c-46848627186065.png" width="1556px" />
4. Clique em **Próximo**.

<div id="step-2-define-the-audience" />

#### Passo 2: Definir uma audiência

Depois que as fontes de dados forem selecionadas, você deve escolher quais atributos e valores devem ser incluídos na sua audiência.

1. Clique em **Selecionar coluna** para ver a lista de atributos das fontes.
2. Selecione um atributo, operador e valor de atributo.
   * **Atributos numéricos e de data** podem ser filtrados com os operadores:  
     Equals, Not equals, Greater than, Lower than, Greater than ou equals,  
     Lower than or equals, Between, Last "X" days (que também pode incluir o dia atual)
   * Os **atributos de texto** podem ser filtrados com os operadores:  
     Equals ou Non-equals

     <div id="note-2" />

     > 📘 **Atenção**
     >
     > * Se um atributo não for selecionado, todos os atributos serão incluídos por padrão.
     > * Depois que os valores de atributos forem selecionados, o tamanho da audiência é ajustado.

3. [Opcional] Clique em **+ Condição** para adicionar outro atributo e selecione seus valores.  
   Repita conforme necessário.
4. Clique em **Próximo**.
5. Siga para o próximo passo [Enviar audiência](#enviar-audiência-para-ativação) para ativar a audiência.

<Image align="center" alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

<div id="summary-right-side-preview-pane" />

#### Resumo (painel de visualização à direita)

O painel Resumo é atualizado em tempo real conforme você define sua audiência. Ele fornece uma **faixa estimada de usuários únicos** que podem ser ativados, com base nos identificadores disponíveis nas fontes de dados selecionadas e na sobreposição entre elas.  
Como a ativação da audiência depende de quais identificadores os parceiros de mídia usam no momento da execução, o tamanho da audiência é mostrado como uma faixa, e não como um único número.

**Linhas da fonte vs. usuários únicos**

Os dados de fonte podem conter várias linhas por usuário.  
Por exemplo, a mesma pessoa pode aparecer várias vezes devido a:

* Vários eventos
* Múltiplos dispositivos
* Vários identificadores (por exemplo, CUID, e-mail, telefone)

  As estimativas de tamanho da audiência no DCP são sempre baseadas em usuários únicos, não em linhas brutas.

**Identificadores e faixa estimada de usuários**

Uma única fonte pode incluir mais de um identificador para o mesmo usuário (por exemplo, um CUID e um e-mail com hash), porque diferentes parceiros de mídia oferecem suporte a identificadores diferentes, e o DCP não pode prever qual identificador será usado durante a ativação.

O DCP estima o tamanho da audiência como uma faixa entre mínimo e máximo:

* **Mínimo:** pressupõe a maior sobreposição possível entre os identificadores
* **Máximo:** pressupõe que os identificadores representam usuários diferentes

A audiência realmente ativada ficará em algum ponto dentro dessa faixa, dependendo dos recursos dos parceiros e da correspondência de identificadores.

**Como entender o painel Resumo:**

**Total de usuários**  
Mostra o número máximo de usuários únicos disponíveis em todas as fontes selecionadas antes da aplicação da sobreposição.

**Filtrar audiências:** selecione os filtros desejados para filtrar suas audiências ou aquelas compartilhadas com você.

**Pool de dados estimado**  
Representa o número estimado de usuários únicos compartilhados entre as fontes, expresso como:

* Um intervalo de usuários
* Uma porcentagem da contribuição da sua fonte

Esse pool determina o tamanho máximo da audiência que pode ser ativada em conjunto.

**Tamanho estimado da audiência**  
O tamanho estimado da audiência reflete o intervalo esperado de usuários únicos que correspondem à definição da sua audiência e podem ser ativados. O intervalo:

* Considera a duplicação de identificadores
* Considera a sobreposição entre fontes (se aplicável)
* É ajustado dinamicamente conforme os filtros, as fontes ou as regras mudam

<Image align="center" alt="image (20).png" src="https://files.readme.io/0ba94f26978e2d3f984bd0c8c2fa8e60159420f5765cff358cdd80d6f05e271c-43432443225489.png" />

<div id="note-3" />

> 📘 **Atenção**
>
> A audiência ativada no lado do Parceiro de mídia pode ser menor do que a audiência que você envia, devido a diferentes taxas de correspondência entre Parceiros de mídia.

<div id="working-with-transactional-data-sources" />

#### Trabalhar com fontes de dados transacionais

Fontes de dados transacionais, como compras, pedidos ou eventos que contêm vários registros por usuário, não podem ser usadas diretamente no criador visual de audiências. Isso ocorre porque usar dados transacionais sem agregação pode resultar em contagens incorretas de audiência, tamanhos de audiência inflados e resultados inesperados de segmentação.

Para usar dados transacionais na criação de audiências, primeiro você deve agregá-los em um conjunto de dados no nível do usuário usando a ferramenta Data View. **Para agregar:**

1. Abra a ferramenta <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-customized-data-views">**Data View**</Anchor> e crie uma Data View a partir da fonte transacional.
2. Aplique funções de agregação (como Count, Sum ou Average) para produzir uma linha por usuário.
3. Associe a Data View agregada à colaboração.
4. Use a Data View de dados agregados como sua fonte no Audience Builder.

<Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-customized-data-views#transactional-data-sources">Saiba como agregar dados transacionais usando uma Data View</Anchor>

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="Audience builder com SQL">

Siga as etapas abaixo para criar uma audiência usando o Audience builder com SQL.

<div id="note-4" />

> 📘 **Nota**
>
> Verifique se você tem a permissão para <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">criar audiências</Anchor>.

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**

   <Image align="center" alt="Clique em Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="40.57%" />
2. Em **Colaborações**, clique na colaboração relevante.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. Na colaboração, clique em **Nova audiência** > **Audience builder com SQL**.

   <Image align="center" alt="New Aud SQL audience builder.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. Prossiga com as etapas do passo a passo do **Audience builder**:

<div id="set-details" />

#### Preencha as informações necessárias

Dê um nome à audiência e clique em **próximo**.

<div id="build-query" />

#### Criar consulta

1. Clique no editor para abrir o [SQL builder](#sql-audience-builder).
2. Escreva sua consulta SQL para criar sua audiência. Você pode usar fontes combinadas ou unilaterais.

<div id="note-5" />

> 📘 **Atenção**
>
> Se sua consulta incluir uma fonte de dados transacional, ela deverá incluir lógica de agregação, como COUNT, SUM, AVG, MIN ou MAX, para reduzir os dados a uma linha por usuário antes que possam ser usados para a criação de audiências. Consultas que usam dados transacionais sem agregação não são suportadas. Veja [os padrões de consulta com e sem suporte](#dados-transacionais-em-consultas-sql) abaixo.

3. Clique em **testar** e avalie os resultados de consulta (amostra de audiência) que aparecem abaixo da declaração.
4. Clique em **Continuar** e em **Próximo** para prosseguir com a próxima etapa ou clique em **Salvar como rascunho** e volte mais tarde.
5. Siga o próximo passo para [enviar a audiência](#enviar-audiência-para-ativação).

<div id="the-sql-audience-builder" />

#### Audience builder com SQL

Use o SQL builder para consultar os dados e criar uma audiência. A tabela a seguir descreve as diferentes seções da ferramenta:

| Seção | Descrição |
| --- | --- |
| <span id="left-pane"></span>Painel esquerdo | Apresenta todas as fontes disponíveis para criar uma audiência. Isso pode incluir as suas fontes e aquelas compartilhadas com você. Você só poderá visualizar fontes que podem ser incluídas quando você for <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**criar uma audiência**</Anchor>.<br /><br />Ao selecionar uma fonte, suas informações se expandem e mostram diferentes colunas. |
| <span id="topmiddle-section-text-editor"></span>Seção no meio superior (editor de consultas) | Use o editor de consultas para escrever suas declarações SQL. |
| <span id="bottommiddle-section-context-panel"></span>Seção na parte inferior e no meio (painel de contexto) | Essa seção mostra detalhes dinâmicos com base no objeto selecionado no painel esquerdo:<ul><li>**Ao selecionar uma fonte:** os nomes das colunas ("Nome do campo") e seus tipos correspondentes ("Tipo") são exibidos.</li><li>**Quando uma coluna é selecionada:** os valores da coluna ("Valores distintos") e a contagem de linhas para cada valor ("Contagem") são exibidos.</li><li>**A seguinte execução de consulta:** mostra uma amostra dos resultados da consulta.<br />**Atenção:** como medida de privacidade, a tabela de resultados não exibe valores anonimizados, como e-mails e IDs. Esses valores são mostrados como "Restricted".</li></ul> |
| <span id="right-pane"></span>Painel direito | Essa seção mostra detalhes dinâmicos com base no objeto selecionado:<ul><li>**Ao selecionar uma fonte:** as permissões concedidas para a fonte são exibidas.</li><li>**Ao escrever a consulta SQL:**<ul><li>o status de validez da consulta no canto superior direito da página é exibido. Isso pode incluir qualquer um dos seguintes status:</li><li>**Pronto para ser executado:** nenhum problema encontrado. Você pode testar a consulta e prosseguir para a próxima etapa.</li><li>**Erro de sintaxe:** um erro na sintaxe foi detectado, juntamente com orientação para resolvê-lo.</li><li>**Erro de permissão:** indica a falta de permissões necessárias, com uma dica que detalha quais <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">direitos de acesso são fornecidos para a fonte</Anchor>.</li><li>Mostra um botão de **Teste** no canto superior direito da página. Depois de terminar de escrever sua consulta, você deve testá-la para confirmar a precisão da audiência.<br />Clique em **Testar** para testar sua consulta e avaliar os resultados.</li></ul></li></ul> |

<div id="transactional-data-in-sql-queries" />

#### Dados transacionais em consultas SQL

Ao trabalhar com fontes de dados transacionais no SQL Builder, os seguintes padrões de consulta se aplicam.

**Padrões de consulta compatíveis**

| Padrão | Visão geral |
| --- | --- |
| <span id="single-transactional-source-with-aggregation"></span>Fonte transacional única com agregação | Uma consulta que agrega uma fonte transacional em uma linha por usuário. Por exemplo, agregar registros de compra para gerar uma contagem total de compras por usuário. |
| <span id="transactional-source-joined-to-a-profileuserlevel-source"></span>Fonte transacional unida a uma fonte no nível de perfil/usuário | Permitido quando o lado transacional é agregado antes da junção. Por exemplo, agregar o histórico de compras por usuário e, em seguida, unir o resultado a um conjunto de dados de perfil do cliente. |
| <span id="aggregated-transactional-output-in-downstream-joins"></span>Saída transacional agregada em junções subsequentes | Depois de agregada ao nível do usuário, a saída pode ser usada em outras junções e fluxos de trabalho de criação de audiências e é tratada de forma semelhante a um conjunto de dados no nível do perfil. |

**Padrões de consulta não compatíveis**

| Padrão | Preencha as informações necessárias |
| --- | --- |
| <span id="transactional-source-joined-directly-to-another-transactional-source"></span>Fonte transacional unida diretamente a outra fonte transacional | Junções diretas entre dois conjuntos de dados transacionais, como compras unidas a pedidos, não são suportadas. Essas junções são bloqueadas antes da execução porque podem multiplicar registros, gerar resultados incorretos de audiências e criar expansão transacional. |
| <span id="nonaggregated-transactional-query"></span>Consulta transacional não agregada | Consultas que usam registros transacionais diretamente, sem agregação, não são suportadas. |

</Accordion>

<div id="send-an-audience-for-activation" />

## Enviar audiência para ativação

Depois que uma audiência for criada, ative-a onde ela puder impulsionar resultados. Selecione um destino, como parceiros de mídia para segmentação de campanha ou um bucket de armazenamento em nuvem para uso subsequente, e o DCP atualiza e entrega a audiência diariamente com base nos dados mais recentes da fonte e nas <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#permissões-de-compartilhamento">permissões</Anchor>.

* [**Conectar a audiência a parceiros de mídia**](#h_01J8HNKQ08EVKXA75C9MZB7AW9) - as plataformas de parceiros de mídia incluem Meta Ads, Google Ads e muitos outros. Conectar sua audiência a parceiros de mídia quando quiser realizar campanhas pagas, remarketing ou expansão de lookalike.
* Conectar sua audiência a serviços de nuvem quando precisar do arquivo em modelos de BI, CDPs ou pipelines de enriquecimento interno.

<div id="note-6" />

> 📘 **Nota**
>
> * Os dados que são enviados para ativação são uma lista de user IDs. Isso significa que a lista de user IDs da audiência é atualizada continuamente e enviada para o destino selecionado diariamente.
> * A cada atualização dos dados de origem, a audiência é encaminhada automaticamente para os destinos selecionados.

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Conectar uma audiência a parceiros de mídia">

Envie a audiência para ativação diretamente nas plataformas de parceiros de mídia preferidas, como Meta Ads e <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google Ads</Anchor>. O sistema envia um CSV com user IDs, com anonimização automática se o parceiro precisar.

<div id="note-7" />

> 📘 **Nota**
>
> * Quando você cria uma audiência usando os dados da fonte do seu colaborador, as opções de ativação exibidas dependem das <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-sharing-permissions">permissões</Anchor> concedidas pelo seu colaborador. Somente os parceiros de ativação que eles permitiram para essa fonte estarão disponíveis para você durante a ativação.
> * Se você não tiver permissão para ativar a audiência, a audiência será enviada ao seu colaborador para ativação por parte dele. Nesse caso, sua solicitação de ativação é enviada ao seu colaborador para ativação do lado dele.

**Para conectar a audiência aos parceiros de mídia:**

1. No audience builder, ative **Conectar audiências aos parceiros de mídia**.  

   <Image align="center" alt="Connect audience to media partners.png" src="https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png" />
2. Clique em **+ Conexão de parceiro**.
3. Se nenhuma conexão de parceiro foi estabelecida, crie uma nova:
   1. Clique em **+ Adicionar conexões**.
   2. Selecione o parceiro de mídia relevante (Meta Ads, Google Ads, DV360 ou TikTok).
   3. Insira um nome para a conexão.
   4. Clique em **Login com [nome do parceiro]**. Você será direcionado para a página de login do parceiro. Escolha a conta que você deseja que receba a audiência. Depois, você será direcionado de volta para a janela de diálogo.
   5. Clique em **Selecionar account ID** e selecione o account ID relevante.
   6. Clique em **Salvar**.
4. **[Fazer download do CSV:](#export-audience-to-cloud-services)** faça o download da audiência como um arquivo CSV.

<Image align="center" alt="image (21).png" src="https://files.readme.io/bb7785936d3e79e18adffe31ca8121b5c0a65392508ef0aea76c7dc75e9ce9eb-43432561109777.png" />

</Accordion>

<div id="export-to-cloud-storage" />

<Accordion title="Exportar para serviços de nuvem">

Envie a audiência diretamente para seu bucket de armazenamento em nuvem. A cada atualização da audiência, o DCP exporta automaticamente a versão mais recente para o destino selecionado. Você também pode fazer download da audiência como um arquivo CSV a qualquer momento.

<div id="note-8" />

> 📘 **Atenção**
>
> Antes de exportar, verifique se o bucket do seu armazenamento em nuvem está configurado e conectado ao DCP. Envie sua audiência para seus serviços de nuvem. A audiência é exportada para o serviço de nuvem selecionado usando suas conexões do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>.

**Export audience to cloud.png**

1. No audience builder, ative **Exportar audiências para a nuvem**.
2. No menu suspenso **Conexões de armazenamento em nuvem**, selecione uma conexão existente.
   * Se você ainda não tiver uma conexão, clique em **+ Nova conexão na nuvem**. A caixa de diálogo de conexão é aberta diretamente nesta página, sem sair do DCP. Clique em **Salvar e enviar**. A nova conexão é selecionada automaticamente.
3. Clique em **Salvar e enviar**.

</Accordion>

<div id="manage-audiences" />

## Gerenciar audiências

Você pode visualizar os status das audiências associadas a uma colaboração.

<div id="access-audience-management" />

<Accordion title="Audience builder visual">

**Para visualizar e gerenciar audiências associadas a uma colaboração:**

1. /docs/data-collaboration-platform-dcp-build-and-activate-audiences#visual-audience-builder
2. **Não conectada:** a audiência foi recebida de um colaborador para ativação, mas ainda não está conectada.  
   <Image align="center" alt="Audiences section.png" src="https://files.readme.io/8f8170d6848da0158c7db76938bdb4fa64cb3a9702218fe549e6b6e859d64140-small-43777994824977.png" width="2836px" />

**O que você pode fazer a partir dessa página:**

* **Procurar por uma audiência:** pesquise pelo nome da fonte ou pelo nome da audiência.
* **Classificar audiências:** classifique as audiências clicando em qualquer um dos cabeçalhos de coluna.
* **Ver detalhes da audiência:** Veja detalhes como o nome do colaborador, estatísticas de sobreposição de usuários, [status da audiência](#audience-statuses) e local de ativação.
* **Mais ações:** ao clicar no ícone de 3 pontos de um card de audiência, você pode acessar outras ações:
  * **[Editar:](#edit-the-audience-activation-destination)** altere o destino de ativação da audiência.
  * **Duplicar:** crie uma nova cópia independente da audiência.
    * As fontes da nova audiência e o método de combinação de dados são mantidos bloqueados (não podem ser alterados); os filtros e os destinos de ativação são mantidos pré-preenchidos, mas podem ser editados livremente.
    * Duplicar fica desativado para audiências do SQL Audience Builder e para audiências com o status "Invalid".
  * **Ver histórico de audiência:** veja todas as instâncias da ativação da audiência, com detalhes como o status de conexão e ativação.
  * [Excluir](#delete-an-audience): [exclua](#delete-an-audience) uma audiência
  * **Pausar:** impeça que a audiência seja atualizada e reativada quando a fonte de dados for modificada.

</Accordion>

<div id="edit-the-audience-activation-destination" />

<Accordion title="Editar o destino de ativação da audiência">

Ao criar uma audiência, você pode salvá-la como um rascunho e, em seguida, retornar a ele e editar o destino de ativação (dependendo das suas permissões).

**Para editar o destino de ativação da audiência:**

1. Em **Colaborações**, clique na colaboração relevante.
2. Clique na seção **Audiences** e localize a audiência relevante.
3. Clique no ícone de 3 pontos que aparece ao passar o mouse na audiência e, sem seguida, clique em **editar**.
4. Em "Conectar e exportar" (na parte inferior da página), ative o botão relevante:

   * [Conectar a parceiros de mídia](#connect-an-audience-to-media-partners)
   * [Exportar audiência para serviços de nuvem](#export-to-cloud-storage)

</Accordion>

<div id="delete-an-audience" />

<Accordion title="Excluir uma audiência">

Você pode excluir uma audiência criada em sua conta. Isso a remove permanentemente da sua conta.

**Para excluir uma audiência:**

1. Em **Colaborações**, clique na colaboração relevante.
2. Clique na seção **Audiences** e localize a audiência relevante.
3. Clique no ícone de 3 pontos que aparece ao passar o mouse na audiência e, sem seguida, clique em **excluir**.
4. Confirme a exclusão.

</Accordion>

<div id="view-audience-statuses" />

<Accordion title="Status da audiência">

Você pode visualizar e gerenciar audiências associadas na seção **Audiences** do dashboard de colaboração relevante.

<Image align="center" alt="image (26).png" src="https://files.readme.io/5659a3e30aac91226ecf8d1cf08618b698f063d1412522f2c231459fdfc7fb03-43541066537105.png" width="860px" />

Uma audiência pode ter diferentes status:

* **Ativa:** a audiência foi enviada com sucesso para a(s) plataforma(s) de destino e está disponível para uso em campanhas.
* **Rascunho:** a audiência foi salva como rascunho (e nunca foi conectada, exportada ou enviada).
* **Inválida**: indica que uma fonte ou visualização de dados usada para a audiência expirou, foi excluída ou removida da colaboração.
* **Envio pendente:** a audiência foi enviada ao colaborador para ativação, e está pendente de ativação.
* **Pausada**: a audiência foi pausada manualmente e não será enviada caso novos dados fiquem disponíveis.
* **Suspensa**: a colaboração e suas audiências associadas foram suspensas.

Você também pode visualizar o status do **histórico de upload** de uma audiência.

Para visualizar o histórico de upload:

Clique no menu suspenso ao lado de uma audiência específica e selecione **Visualizar histórico**.

<Image align="center" alt="View history doctored .png" src="https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png" />

**Esses são os diferentes status possíveis:**

* **Resumo:** crie e ative audiências usando as ferramentas do audience builder.
* **Sucesso**: a audiência foi enviada com sucesso para todas as conexões.
* **Falha parcial**: a audiência não pôde ser enviada para uma ou mais conexões.
* **Falha**: ocorreu um problema ao processar oa audiência (por exemplo, devido a dados incompatíveis, restrições de plataforma ou erros de plataforma).
* **N/A:** a audiência está com status de rascunho ou pendente. O status do histórico de upload não se aplica.

</Accordion>

<div data-zendesk-anchors="overview=sobre-as-audi%C3%AAncias-do-dcp h_01HWG1P909NHBXC5VF23BDVVPH=sobre-as-audi%C3%AAncias-do-dcp key-features=crie-sua-audi%C3%AAncia h_01HWG5B2MEJH7M8E9BWA3FQFQ2=crie-sua-audi%C3%AAncia 01KFDX0R4BYSTE1V5G7ATQ6FZS=principais-caracter%C3%ADsticas h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=nota step-1-join-sources=passo-1-detalhes-e-fontes h_01HWFRRGP99KKGBSQ6QB10RD26=passo-1-detalhes-e-fontes h_01KT94AC4N81MBE0DAT7TX2QA7=aten%C3%A7%C3%A3o step-2-build-audiences=passo-2-definir-uma-audi%C3%AAncia h_01HWFRRPFTCFGEHY1AW8G4VMY4=passo-2-definir-uma-audi%C3%AAncia h_01JSEPSRF3FFJJ4S20GJJPJVWF=aten%C3%A7%C3%A3o-1 summary-rightside-preview-pane=resumo-painel-de-visualiza%C3%A7%C3%A3o-%C3%A0-direita h_01KBMPR7BHCTTVE8DR1TCRYAHJ=resumo-painel-de-visualiza%C3%A7%C3%A3o-%C3%A0-direita h_01KBMPK2HXMZ6YNQMJTST9BD8Y=aten%C3%A7%C3%A3o-2 h_transactional-data-visual-builder=trabalhar-com-fontes-de-dados-transacionais working-with-transactional-data-sources=trabalhar-com-fontes-de-dados-transacionais h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=nota-1 step-1-set-details=preencha-as-informa%C3%A7%C3%B5es-necess%C3%A1rias h_01HWG9VX0QB3GFZDARAT5QKHV0=preencha-as-informa%C3%A7%C3%B5es-necess%C3%A1rias step-2-build-query=criar-consulta h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=criar-consulta h_01KT6SCS53699DZXE4EF92WC44=aten%C3%A7%C3%A3o-3 the-sql-audience-builder=audience-builder-com-sql h_01HZM9P2GNCPGJDEA51HCV1Y99=audience-builder-com-sql h_transactional-data-sql-patterns=dados-transacionais-em-consultas-sql transactional-data-in-sql-queries=dados-transacionais-em-consultas-sql send-audience-for-activation=enviar-audi%C3%AAncia-para-ativa%C3%A7%C3%A3o h_01HZMCHKMVXRWK7RXZ7NN65JQX=enviar-audi%C3%AAncia-para-ativa%C3%A7%C3%A3o h_01HZMCRJBBXFEV6JXEHGFXZDZW=nota-2 h_01KFG12R13ADFBY4XBDRGE956V=connect-an-audience-to-media-partners h_01HZMDXEEABQRQE8XMZNE86SRF=nota-3 h_01KFG12R13R9B6ATHTBTKAVAMX=export-to-cloud-storage h_01KY2FJV90NYBVTQBN6K63K9DS=aten%C3%A7%C3%A3o-4 manage-audiences=gerenciar-audi%C3%AAncias h_01HZPWTG23YQ5Y1GAPXT65DK07=gerenciar-audi%C3%AAncias h_01KFBA379S9ZZAKN7FC7X2S297=access-audience-management h_01KFB4HVDZZ0MA4Q69DXKH4YY7=edit-the-audience-activation-destination h_01KFB4HVDZJ08STDXGA7ZP8MM3=delete-an-audience h_01KFB4HVDZFCJNYG6VVWTWVAQ8=view-audience-statuses" />
