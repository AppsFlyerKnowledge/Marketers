---
title: >-
  Plataforma de Colaboração de Dados (DCP) - Crie visualizações de dados
  personalizadas
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
  created_at: '2024-11-22T12:57:55Z'
  edited_at: '2026-08-19T00:06:49Z'
  id: 30296051098897
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/30296051098897
---
> **Em resumo:** Crie subconjuntos personalizados dos seus dados de fonte existentes sem precisar de SQL nem de conhecimento técnico. As visualizações de dados permitem modificar, refinar e resumir os dados, para que você compartilhe com os colaboradores apenas o que for relevante.

<div id="about-data-views" />

## Sobre visualizações de dados

O Data View Builder permite que você crie uma versão personalizada da sua fonte de dados e a torne relevante para a sua audiência sem modificar o conjunto de dados original. Com elas, você pode realizar funções que modificam, refinam e resumem os dados para que você possa compartilhar apenas o que for relevante, mantendo os dados compartilhados claros e focados e todos os demais dados privados e seguros. Não é necessário ter nenhum conhecimento de SQL, nem da ajuda de um especialista ou engenheiro de dados.

<div id="data-view-functions" />

### Funções do Data View Builder

Com o Builder de visualizações de dados, você pode moldar seus dados aplicando as seguintes funções principais:

* **Filtragem:** filtre seus dados aplicando atributos específicos, como intervalo de tempo, categoria e parâmetros personalizados para focar em informações específicas.
* Em **Personalizar dados**, clique em **Gerenciar campos**.
  * **Transformação:** altere o formato, estrutura e valores dos dados, preparando-os para a análise. Isso cria novas colunas que incorporam insights de dados existentes.
  * **Agregação:** combine múltiplos registros de dados para criar resumos e grupos usando funções de soma, média, contagem, mínimo e máximo.
* **Selecionar campos:** selecione a estrutura da visualização de dados, removendo campos desnecessários e ajustando os tipos de campo.

<div id="the-data-view-builder" />

## Data View Builder

**<Image alt="Nova visualização de dados - Padrão.png" src="https://files.readme.io/b34b61b2fbc092884270ce0daab9a86deae6b423775bcc648ee0eba6f319e8e5-41945719130897.png" width="1598px" />**

<div id="create-a-data-view" />

## Definir visualização de dados

Para começar a criar uma visualização de dados, siga os passos abaixo:

**Pré-requisitos**

Uma <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">conta</Anchor> da AppsFlyer com acesso ao DCP.

<div id="set-the-data-view-general-details" />

<Accordion title="1. Configurar os detalhes gerais">

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**

   <Image alt="Clique em Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="34.74%" />
2. Em **Fontes** , passe o mouse sobre a fonte que você deseja usar para criar a visualização de dados e clique em <Image alt="ellipsis.png" src="https://files.readme.io/d3e33f1864edb1d9d2f8e18c9c7887454018a67e9f7fed054e7134231dba60a2-30296671836433.png" width="0.6%" /> (ícone de Menu) no final da linha.
3. Selecione **Criar visualização de dados**. Você será direcionado para a página **Nova visualização de dados**.

   <Image alt="Criar uma visualização de dados com seta.png" src="https://files.readme.io/f9fbcacabb560da996e1dc009e6cd2c5b78d3ccd42e89e2a3c37e71882577e18-41945719135889.png" width="1500px" />
4. Preencha os seguintes campos:
   * **Nome da visualização de dados:** escolha um nome para a sua visualização de dados. Pode ser qualquer nome que te ajudará a identificar essa visualização. Veja os [requisitos e diretrizes de nomenclatura](#requisitos-e-diretrizes-de-nomenclatura) abaixo.
   * **Descrição:** Forneça uma descrição. Isso aparece como uma dica quando você passa o mouse sobre o nome da visualização de dados na aba **Fontes** . Recomendamos que você insira os principais objetivos e manipulações de dados realizadas.

<div id="naming-requirements-and-guidelines" />

#### Requisitos e diretrizes de nomenclatura

* Certifique-se de que o nome seja exclusivo em comparação a todas as outras fontes e sub-fontes em sua conta. Caso contrário, você não poderá salvá-lo.
* Para integrações em nuvem, o nome não precisa corresponder ao nome do arquivo.
* Requisitos de nome:
  * Tamanho: 2-80 caracteres
  * Caracteres válidos:
    * letras (A-Z, a-z)
    * números (0-9), *não podem ser o primeiro caractere de um nome;*
  * Caracteres inválidos:
    * espaços
    * sublinhado
    * todos os outros símbolos ou caracteres especiais

</Accordion>

<div id="h_01K4SDE8H7R9YZYXMRVXV5GZSV" />

<Accordion title="3. Filtre seus dados">

Você pode aplicar filtros para restringir seus dados usando atributos selecionados, permitindo que você se concentre em informações específicas e relevantes.

**Para aplicar filtros:**

1. Em **Filtros**, clique em **Filtre seus dados**.
2. Clique em **Selecionar coluna** e selecione a coluna a ser filtrada.
3. Clique em **Operador** > **Igual** ou **Não igual**.
4. Insira um valor.
5. [Opcional] Clique em **+ Condição** para adicionar uma condição ao filtro.

<div id="note" />

> 📘 **Nota**
>
> * Você pode adicionar quantas condições forem necessárias, usando as operações E e OU.
> * Múltiplas condições são processadas de acordo com a ordem lógica padrão, com prioridade dada às operações E sobre OU.
> * Ao usar funções ou filtros em campos de datas (colunas), certifique-se de que os valores das datas estejam em conformidade com o formato de data específico para a função selecionada. Quaisquer discrepâncias podem atrapalhar o funcionamento das opções fornecidas.

</Accordion>

<div id="transform-aggregate-and-filter-data" />

<Accordion title="3. Criar campos calculados (opcional)">

Os campos calculados permitem usar funções para adicionar novos campos, alterar o formato e os valores dos dados ou combinar registros usando lógica, cálculos ou agregação.

**Para criar um campo de Transformação ou Agregação:**

1. Selecione a aba **Transformação** ou **Agregação** e clique em + **Novo campo**.
2. Em **Transformar e agregar**, clique em **Criar campo**.
3. Clique em **Definir função**, e selecione uma função na [lista de funções](#list-of-functions-and-use-case-examples). Os campos relevantes nos quais você deve inserir as informações necessárias são adicionados automaticamente.
4. Para campos de **agregação** :  A seção **Agrupar por** será aberta automaticamente, e você poderá selecionar o campo que define como os dados agregados serão agrupados.
5. [Opcional] Clique **+ Novo campo** para adicionar mais campos de **Transformação** ou **Agregação**. Você pode adicionar quantos campos forem necessários.

<div id="group-by" />

#### **Agrupar por**

Agrupe seus dados em categorias significativas ao aplicar uma agregação. Quando você adiciona uma função de agregação, a seção Agrupar por é aberta automaticamente e permite selecionar os campos que determinam como os dados são agrupados. Por exemplo, você pode agrupar os resultados por país, ID do usuário ou linha de produto para calcular totais ou contagens para cada grupo.

<Image alt="Agrupar por.png" src="https://files.readme.io/40fc355847acf7269c6fcd2b505ed182b407d4c668f717612b53c5fd88506443-41967849623057.png" width="58.2%" />  

Selecione na aba [Transformar e Agregar](#transform-aggregate-and-filter-data) os campos relevantes para edição e faça as alterações necessáriasSelecione na aba [Transformar e Agregar](#transform-aggregate-and-filter-data) os campos relevantes para edição e faça as alterações necessárias**Observação:** Os primeiros campos selecionados são os identificadores selecionados na fonte original.

Uma vez criado, o novo campo:

* Para campos de **Agregação**:
* É incluído na lista de campos disponíveis para uso em todas as funções e filtros.
* É incluído na lista de campos na seção [selecionar campos](#select-fields) .

<div id="zd-list-of-functions-and-use-case-examples" />

<div id="list-of-functions-and-use-case-examples" />

#### Lista de funções e exemplos de casos de uso

<div id="transformation-functions" />

#### **Funções de Transformação**

* **SE:** Uma declaração condicional que executa ações diferentes com base no fato de que uma condição especificada é verdadeira ou falsa.
* **CONCAT:** Concatenação de duas strings
* **CONST:** Retorna o parâmetro da função CONCAT
* **MENOR QUE:** Retorna o menor de dois valores
* **MAIOR QUE:** Retorna o maior de dois valores

<div id="example-transformation" />

#### **Exemplo: Transformação**

Você quer indicar quais produtos foram comprados do colaborador enquanto oculta compras de outras marcas com as quais você está trabalhando.

<div id="aggregate-functions" />

#### **Funções agregadas**

* **CONTAR:** Retorna o número de linhas.
* **SOMA:** Retorna a soma de todos os valores.
* **MÉDIA:** Retorna a média de todos os valores.
* **MÍN:** Retorna os valores mínimos de dois números
* **MÁX:** Retorna os valores máximos de dois números

<div id="example-aggregation" />

#### **Exemplo: Agregação**

Você quer contar o número total de compras por usuário e somar o preço total que ele pagou.

<div id="example-aggregation-with-a-condition" />

#### Exemplo: Agregação com uma condição

Você quer acessar os dados das últimas compras feitas por usuários localizados na Alemanha, que compraram produtos da P&G.

</Accordion>

<div id="select-fields" />

<Accordion title="4. Selecionar campos">

A estrutura da visualização de dados inclui campos da fonte de dados original e quaisquer campos de dados personalizados criados dentro do Data View Builder. A partir daqui você pode remover campos (exceto pelo campo identificador) ou rearranjar sua ordem.

<div id="note-1" />

> 📘 **Nota**
>
> * Você só pode ajustar o tipo de campo a partir da fonte original, não a partir da visualização de dados.
> * Funções de **Transformação** e **Agregação**: use-as para criar campos personalizados.
> * Remover um campo quando uma função de agregação é aplicada diminui a granularidade dos dados, o que pode impactar os resultados na visualização de dados.

<div id="adjust-field-types" />

<Accordion title="Ajustar tipos de campo">

Revise cada campo e selecione o tipo de dado desejado na lista suspensa, caso queira alterá-lo.

</Accordion>

<div id="remove-fields" />

<Accordion title="Remover campos">

Você pode remover qualquer um dos campos, exceto o campo identificador. Se houver vários campos de identificador, você poderá remover todos, exceto um. Uma visualização de dados deve conter pelo menos um campo de identificador.

**Para remover um campo:**

1. Passe o mouse sobre o lado direito do campo que você deseja remover.
2. Clique no ícone da lixeira que aparece. O campo agora aparece na seção **Removido** com um botão **Restaurar** que permite que você restaure o campo removido.
3. Clique em [Salvar](#save-your-data-view).

</Accordion>

<div id="restoring-temporarily-removed-fields" />

<Accordion title="Restaurando campos removidos temporariamente">

Quando um campo é removido da lista, ele é colocado na seção **Removido** . Enquanto você não tiver salvo a visualização de dados, você pode restaurá-lo clicando no botão **Restaurar**.

</Accordion>

</Accordion>

<div id="save-your-data-view" />

<Accordion title="5. Salvar visualização de dados">

**Painel lateral**

O painel lateral (lado direito da página) apresenta dois conjuntos de dados, um da fonte original e outro da visualização de dados criada a partir dela. Cada conjunto inclui o nome da tabela e sua descrição, número de campos e número de linhas, juntamente com uma tabela de amostra que contém cinco linhas de dados. Quando funções e filtros são aplicados à visualização de dados, o painel lateral reflete essas mudanças, permitindo que você verifique os dados enquanto os modifica e os compare com a versão original.

![Visualização de dados - painel lateral.png](https://files.readme.io/c1dae932618bf2ded68a30853474ce9d6107fdb09541a5d12ac3ddcf4def0101-41945719138577.png)

Você pode salvar a visualização de dados a qualquer momento. Uma vez salvo, ele é adicionado sob a fonte de dados original na lista de fontes, e você pode [editar, compartilhar ou deletar](#gerenciar-visualizações-de-dados).

**Para salvar a visualização de dados:**

Clique em **Salvar** na parte inferior da página.

</Accordion>

<div id="h_01JVSEG13462Z4XXD1NE8GW1HE" />

<Accordion title="Passo 6: Passo 6: Compartilhe sua visualização de dados em uma colaboração (opcional)">

Você pode <Anchor target="_blank" href="You%20can%20share%20(associate)%20your%20data%20view%20in%20a%20collaboration,%20enabling%20a%20brand%20collaborator%20to%20view%20and%20perform%20actions%20with%20it%20(based%20on%20the%20permissions%20you%20set).">associate your data view with a collaboration</Anchor>, permitindo que colaboradores da marca a visualizem e realizem ações com ela (com base nas permissões que você definir).  
**Observação:** Para associar uma visualização de dados a uma colaboração, você deve ser o criador da colaboração ou ter sido convidado para ela.

<div id="note-2" />

> 📘 **Nota**
>
> Se você criou esta visualização de dados para agregar uma fonte transacional para a criação de audiências, associe-a à colaboração relevante. A visualização de dados agregados deve ser associada à colaboração antes de ficar disponível como fonte no Audience Builder. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration">Saiba como associar fontes a uma colaboração</Anchor>.

</Accordion>

<div id="use-cases" />

## casos de uso

Esta seção apresenta alguns casos de uso comuns para visualizações de dados.

<div id="common-use-cases" />

<Accordion title="Casos comuns">

As visualizações de dados são úteis quando você precisa personalizar e controlar o acesso aos dados para diferentes audiências ou finalidades comerciais. Aqui estão alguns cenários comuns:

* **Relatórios específicos por marca**  
  Se você trabalha com várias marcas usando uma única fonte de dados, pode criar visualizações de dados separadas para cada marca, mostrando apenas os dados relevantes para cada uma delas. Isso mantém os dados limpos, focados e em conformidade com limites de privacidade ou concorrência.
* **Colaboração interna**  
  Compartilhe visualizações personalizadas com diferentes equipes, como marketing, produto ou vendas, para que cada equipe veja apenas os campos e registros relevantes para seu trabalho. Isso evita confusão e garante que cada equipe trabalhe com o subconjunto correto de dados.
* **Compartilhamento de dados com clientes**  
  Ao compartilhar relatórios ou insights com clientes ou parceiros externos, as visualizações de dados permitem excluir informações sensíveis ou irrelevantes, sem deixar de oferecer visibilidade completa sobre os dados que importam para eles.
* **Filtragem por categoria ou região**  
  Você pode criar visualizações filtradas por país, linha de produtos ou outras dimensões, facilitando o foco em segmentos de mercado ou unidades de negócio específicas sem sobrecarregar os relatórios com dados não relacionados.
* **Resumo de dados**  
  Aplique agregação para resumir métricas importantes, como o total de compras por região ou a atividade do usuário ao longo do tempo, para que seus colaboradores vejam insights de alto nível em vez de dados brutos.
* **Preparação de dados transacionais**  
  Se sua fonte contiver dados transacionais, como compras, pedidos ou eventos com vários registros por usuário, use uma visualização de dados para agregá-los em um conjunto de dados no nível do usuário antes de compartilhá-los para a criação de audiências. Isso evita tamanhos inflados de audiências e garante resultados precisos de segmentação. Consulte [Como usar fontes de dados transacionais](#h_transactional-data-sources) abaixo.

</Accordion>

<div id="transactional-data-sources" />

<Accordion title="Fontes de dados transacionais">

Dados transacionais se referem a fontes que contêm vários registros por usuário (por exemplo, compras, pedidos ou eventos). Se você estiver trabalhando com uma fonte de dados transacionais, deverá agregá-la em um conjunto de dados no nível do usuário antes que ela possa ser usada para a criação de audiências no Audience Builder.

<div id="note-3" />

> 📘 **Nota**
>
> Quando você abre uma fonte de dados transacionais diretamente ou é redirecionado para cá a partir do Audience Builder, um banner é exibido confirmando que a agregação é obrigatória. A visualização de dados agregados também deve ser associada à colaboração relevante antes de ficar disponível como fonte no Audience Builder.

**Por que a agregação é obrigatória**

Conjuntos de dados transacionais podem conter vários registros por usuário. Usá-los diretamente na criação de audiências pode resultar em contagens incorretas de audiências, tamanhos inflados de audiências e resultados inesperados de segmentação. A agregação dos dados gera uma linha por usuário, tornando-os adequados para fluxos de trabalho de audiências.

**Para preparar dados transacionais para uso no Audience Builder, siga estas etapas:**

1. Crie uma visualização de dados a partir da fonte transacional (consulte [Criar uma visualização de dados](#definir-visualização-de-dados) acima).
2. Aplique funções de agregação, como Contagem, Soma, Média, Mín. ou Máx., para gerar uma linha por usuário.
3. Aplique filtros, se necessário, para refinar o conjunto de dados.
4. Associe a visualização de dados agregada à colaboração (consulte a [Etapa 6](#h_01JVSEG13462Z4XXD1NE8GW1HE) acima).
5. Use a visualização de dados agregada como fonte no Audience Builder.

<Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Saiba como criar audiências</Anchor>

</Accordion>

<div id="manage-data-views" />

## Gerenciar visualizações de dados

As visualizações de dados aparecem na aba **Fontes** , sob a fonte original. Você pode editar, deletar ou compartilhar com colaboradores.

<div id="edit-details" />

<Accordion title="Editar visualização de dados">

Você pode modificar a descrição da visualização de dados ou os rótulos usados na descrição.

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. Em **Fontes**, clique no nome da fonte. As visualizações de dados associadas são mostradas.
3. Passe o mouse sobre a visualização de dados para modificá-la e clique em [<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="2.39%" />](/docs/data-collaboration-platform-dcp-create-customized-data-views#share-a-data-view) (ícone de editar) no final da linha.
4. Edite a descrição e/ou os rótulos aplicados.

</Accordion>

<div id="delete-a-data-view" />

<Accordion title="Excluir uma visualização de dados">

**Para excluir uma visualização de dados:**

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. Em **Fontes**, clique no nome da fonte. As visualizações de dados associadas são mostradas.
3. Passe o mouse sobre a visualização de dados para modificá-la e clique em **Excluir fonte** no final da linha.

Uma visualização de dados também pode ser excluída de uma colaboração.

**Detalhes:** dê um nome e descreva a visualização de dados

* Os colaboradores perdem o acesso às visualizações de dados compartilhadas com eles (associadas) por meio de uma colaboração.
* As audiências baseadas na visualização de dados não podem mais ser usadas.

</Accordion>

<div id="share-a-data-view" />

<Accordion title="Compartilhar uma visualização de dados">

Compartilhe sua visualização de dados com o colaborador e forneça a ele as permissões necessárias

1. Na plataforma Data Collaboration Platform, acesse a guia **Collaborations** > colaboração específica.
2. No dashboard da colaboração, clique no menu de ações no canto superior direito > **Associated sources**.

   <Image alt="Associate source new UI.png" src="https://files.readme.io/3730b39bb5754260b74632591dffe3fcf54e6c73ff114ba0a8853f277e1e709a-43751907286161.png" width="1539px" />
3. Selecione sua visualização de dados (fonte) no menu suspenso para associá-la à colaboração.  

   <Image alt="select data view.png" src="https://files.readme.io/f1681e5a4096459cbc570531494a8a7be8e4f835d95e4435217b0e8e15715772-43751923329937.png" width="783px" />  
   Feito isso, clique em **Salvar**.
4. **Opcional:** defina permissões de dados personalizadas na fonte da visualização de dados.

   Você pode definir permissões personalizadas (diferentes da política geral de permissões de dados). **Para definir permissões de dados personalizadas na fonte da sua visualização de dados:**

   No menu de 3 pontos ao lado da fonte da visualização de dados, clique em **Editar permissões**.  

   <Image alt="Edit permissions new.png" src="https://files.readme.io/58c785d7fdda52aa159153676d5875e718ceae2f31f987706b79509eb8251151-43752564819985.png" width="1330px" />
5. Selecione as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#permissões-de-compartilhamento">permissões de compartilhamento</Anchor> relevantes.

<div id="note-4" />

> 📘 **Nota**
>
> Você só pode compartilhar visualizações de dados criadas a partir das suas fontes.

</Accordion>

<div data-zendesk-anchors="overview=sobre-visualiza%C3%A7%C3%B5es-de-dados 01JD9Z4WKKDWS2EQND0SY7EADZ=sobre-visualiza%C3%A7%C3%B5es-de-dados data-view-functions=fun%C3%A7%C3%B5es-do-data-view-builder 01JD9Z4WKMTZ18E13E6V3KZYB3=fun%C3%A7%C3%B5es-do-data-view-builder the-data-view-builder=data-view-builder 01JD9Z4WKNREMCMB9PNSVVQ024=data-view-builder set-a-data-view=definir-visualiza%C3%A7%C3%A3o-de-dados 01JD9Z4WKRD4V4A07WT5YG42RZ=definir-visualiza%C3%A7%C3%A3o-de-dados 01JD9Z4WKWQJJE9Q8EMQY8NCMD=set-the-data-view-general-details naming-requirements=requisitos-e-diretrizes-de-nomenclatura 01JD9Z4WKX3BGN7V9V1V1YBYWT=requisitos-e-diretrizes-de-nomenclatura 01JDEVRX2EV64YQN2JE901CEK8=nota 01JD9Z4WM1EQVKS9B4EHMTHW41=transform-aggregate-and-filter-data group-by=agrupar-por h_01KC69N1HAVXE2NVB6DZRJG91N=agrupar-por 01JD9Z4WMDV8B7P8W5E13J7HNJ=list-of-functions-and-use-case-examples transformation-functions=fun%C3%A7%C3%B5es-de-transforma%C3%A7%C3%A3o h_01JDA45VWKH2ZKVBTK87VFVKTB=fun%C3%A7%C3%B5es-de-transforma%C3%A7%C3%A3o example-transformation=exemplo-transforma%C3%A7%C3%A3o h_01JDA4611HFFEA17352NSNCJYX=exemplo-transforma%C3%A7%C3%A3o aggregate-functions=fun%C3%A7%C3%B5es-agregadas h_01JDA467NV99FDAXJCXYSD5PBF=fun%C3%A7%C3%B5es-agregadas example-aggregation=exemplo-agrega%C3%A7%C3%A3o h_01JDA46DWD6G3S4S5FM48KWQXA=exemplo-agrega%C3%A7%C3%A3o example-aggregation-with-a-condition=exemplo-agrega%C3%A7%C3%A3o-com-uma-condi%C3%A7%C3%A3o 01JDETVS9XQ9XCNEFVCSC8GAJR=exemplo-agrega%C3%A7%C3%A3o-com-uma-condi%C3%A7%C3%A3o 01JD9Z4WMJ9XFBXPJAM6RNRP96=select-fields 01JD9Z4WMJJGXG9XXSW6Q6S5KE=nota-1 01JD9Z4WMKA2J94AYW9VXKKVKQ=adjust-field-types 01JD9Z4WMM4QQDP749R7H93Z67=remove-fields 01JD9Z4WMNHXCP4Q66C1TN67Y4=restoring-temporarily-removed-fields 01JD9Z4WMQGY8DCEWMPGX8FC2Y=save-your-data-view h_transactional_share_note=nota-2 use-cases=casos-de-uso h_01JVSHYGNEFEKP713NNYSSZPS2=casos-de-uso h_01JVSHX282XSCWMN2JRZJ593KN=common-use-cases h_01KT964QX4EW74REN13T1TBKGN=transactional-data-sources h_transactional_banner_note=nota-3 manage-data-views=gerenciar-visualiza%C3%A7%C3%B5es-de-dados 01JD9Z4WMRFS0S408ZJ2YKBZF3=gerenciar-visualiza%C3%A7%C3%B5es-de-dados 01JD9Z4WMT7GG4JV91JE5KAJ4X=edit-details 01JD9Z4WMZGV916XJ77V3NR1HK=delete-a-data-view 01JD9Z4WN3VX56JDWK937D1WXH=share-a-data-view 01JDA2A87RG8V8RZW4EB1B2K56=nota-4" />
