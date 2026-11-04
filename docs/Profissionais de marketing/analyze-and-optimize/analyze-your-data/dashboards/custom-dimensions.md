---
title: Dimensões personalizadas
metadata:
  keywords:
    - dashboard
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2023-06-06T09:28:20Z'
  edited_at: '2026-08-19T00:03:42Z'
  id: 15920604187921
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/15920604187921
---
> **Visão geral:** defina suas próprias dimensões e use-as para agrupar e visualizar dados no painel Visão geral.

<Embed title="Dimensões personalizadas" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/tvcdofnwjo" providerUrl="https://fast.wistia.com" />

<div id="overview" />

## Visão geral

As dimensões personalizadas permitem que você use dimensões existentes para criar suas próprias dimensões para análise de dados relevantes para os objetivos do seu negócio. Essas dimensões podem ser usadas em todos os widgets no painel Visão geral para agrupar dados e ajudar você a obter insights mais profundos e tomar decisões orientadas por dados que se alinham aos seus objetivos de negócios.

As dimensões personalizadas são criadas no nível da conta, o que significa que diferentes aplicativos na mesma conta da AppsFlyer podem usar as mesmas dimensões personalizadas.

<div id="benefits" />

### Benefícios

* Insights personalizados: defina e colete dados específicos para as necessidades do seu negócio. Ao capturar informações adicionais além das dimensões padrão, você pode obter insights mais profundos e uma compreensão mais abrangente de seus dados.
* Análise segmentada: agrupe e analise seus dados com base em atributos ou características relevantes específicas para obter uma visão mais detalhada do comportamento do usuário, segmentos de clientes ou desempenho do produto.
* Relatórios aprimorados: crie painéis e relatórios personalizados que se alinham com seus requisitos exclusivos de relatórios.
* Tomada de decisão aprimorada: ao capturar dimensões personalizadas que se alinham com os objetivos do seu negócio, você pode tomar decisões mais informadas. As dimensões personalizadas fornecem o contexto necessário para avaliar o impacto de diferentes variáveis e fatores em seus principais indicadores de desempenho (KPIs), ajudando você a identificar tendências, padrões e oportunidades de otimização.

<div id="example-use-cases" />

### Exemplo de casos de uso

| Exemplo de caso de uso | Descrição |
| --- | --- |
| Intenção da campanha | <ul><li>Com base nos nomes das suas campanhas.</li><li>Selecione nomes dos valores para diferenciar os vários objetivos da campanha. Por exemplo: rotule um branding como "brd" e uma campanha de aquisição de usuários como "new" ou "ua".</li><li>Inclua os nomes dos valores em seus nomes de campanha. Por exemplo: "US\_Facebook\_BRD" ou "UK\_Google\_new".</li><li>A AppsFlyer analisa o nome da campanha e agrupa dados com base em seus rótulos.</li></ul> |
| Regiões | <ul><li>Com base nas geolocalizações.</li><li>Agrupe várias áreas geolocalizações/países em regiões. Por exemplo: agrupe EUA, Canadá e México em "América do Norte" ou use diferentes áreas geográficas para criar agrupamentos para Europa, APAC etc.</li><li>A AppsFlyer agrupa dados com base nos valores de sua região (América do Norte, Europa, Ásia-Pacífico, entre outros).</li></ul> |
| Mídia própria x mídia paga | <ul><li>Com base em fontes de mídia.</li><li>Agrupe diferentes fontes de mídia em "próprias" e "pagas". Por exemplo: agrupe SMS e post no Facebook no valor "propriedade" e Facebook e Google no valor "pago".</li><li>A AppsFlyer agrupa os dados dessas fontes de mídia nos valores "própria" e "paga", respectivamente.</li></ul> |
| Cidades | <ul><li>Com base nos nomes das suas campanhas.</li><li>Os valores incluem as cidades para as quais você tem campanhas específicas em seus nomes de campanha. Por exemplo: "US\_Facebook\_NY" para Nova York e "US\_Google\_SF" para São Francisco.</li><li>A AppsFlyer analisa o nome da campanha e agrupa dados com base nas cidades.</li></ul> |
| Gerente de UA | <ul><li>Com base em fontes de mídia.</li><li>Agrupe diferentes fontes de mídia de acordo com membros específicos da equipe. Por exemplo: agrupe as campanhas do Google e do Facebook no valor "Kevin" e as campanhas do TikTok e do Instagram no valor "Natasha".</li><li>A AppsFlyer agrupa dados dessas fontes de mídia nos valores "Kevin" e "Natasha", respectivamente.</li></ul> |

<div id="procedures" />

## Procedimentos

<div id="create-a-custom-dimension" />

<Accordion title="Criar uma dimensão personalizada">

**Para criar uma dimensão personalizada**:

1. No painel Visão geral, faça uma das opções:
   * Clique no **ícone Menu (⋮)** > **Dimensões personalizadas**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * Em qualquer gráfico ou tabela, no dropdown **Mostrar para** ou **Agrupar por**, clique em **+ Criar dimensão personalizada**.
2. Se esta for a primeira vez que você cria uma dimensão personalizada, clique em **+ Nova dimensão**.  
   A aba **Criar** é aberta.
3. Insira um nome e uma descrição para sua dimensão. Escolha o nome e a descrição que ajudarão você a identificar essa dimensão personalizada nas opções de agrupamento do painel.
4. Defina os possíveis valores de dimensão. Pode haver até 10 valores por dimensão. Para cada valor:
   1. Digite um nome do valor.
      * Exemplo: para uma dimensão personalizada chamada "intenção da campanha", os valores podem ser "branding" e "ua". Veja mais exemplos de casos de uso.
   2. Defina as regras para quando o nome do valor deve ser usado. Pode haver até 10 regras por valor.
      * Cada regra inclui a dimensão existente na qual o valor se baseia, operadores e valores do operador.
      * Exemplo: se o nome da campanha incluir "brd" ou "brnd", o nome do valor será "branding". Veja mais exemplos de casos de uso.
      * A tabela a seguir mostra os diferentes componentes usados na definição de uma dimensão.

<table><thead><tr><th>Nome do valor</th><th>Dimensão (para basear o valor)</th><th>Operador</th><th>Valor do operador</th></tr></thead><tbody><tr><td rowspan="3">Você decide os possíveis nomes de valor para sua dimensão personalizada.</td><td>Fonte de mídia</td><td rowspan="2">Selecione: <ul><li>É</li><li>Contém</li><li>Começa com</li><li>Termina com</li></ul></td><td><ul><li>Sequência de caracteres</li><li>Seleção dropdown (se o operador for "é")</li></ul></td></tr><tr><td>Nome da campanha</td><td>Sequência de caracteres</td></tr><tr><td>Geografia</td><td>É </td><td>Seleção dropdown</td></tr></tbody></table>

5. Clique em **Salvar**.

</Accordion>

<div id="delete-or-edit-a-custom-dimension" />

<Accordion title="Excluir ou editar uma dimensão personalizada">

**Para excluir ou editar uma dimensão personalizada**:

1. No painel Visão geral, faça uma das opções:
   * Clique no **ícone Menu** > **Dimensão personalizada**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * Em qualquer gráfico ou tabela, no dropdown **Mostrar para** ou **Agrupar por**, clique em **+ Criar dimensão personalizada**.
2. Clique na aba **Editar**.
3. Selecione ou pesquise uma dimensão personalizada.
4. Para excluir a dimensão, clique no ícone **Excluir** ao lado da dimensão selecionada.
5. Para editar a dimensão, faça as alterações desejadas nas configurações de dimensão personalizada e clique em **Salvar**.

</Accordion>

<div id="view-custom-dimension-data" />

<Accordion title="Visualizar dados de dimensão personalizada">

Dimensões personalizadas podem ser usadas para agrupar e exibir dados em todos os widgets no painel Visão geral.

**Para visualizar dados de dimensão personalizada**:

1. No painel Visão geral, acesse qualquer widget de gráfico ou painel.
2. No dropdown **Mostrar topo** ou **Agrupar por**, procure em Dimensões personalizadas a dimensão personalizada que deseja usar.  
   [![](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)
3. Os dados do gráfico ou tabela são exibidos em um agrupamento usando sua dimensão personalizada

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificações e limitações">

| Especificação | Observações |
| --- | --- |
| Dimensões personalizadas | Até 10 dimensões personalizadas podem ser criadas. |
| AppsFlyer | Não é possível visualizar ou editar dimensões personalizadas feitas por agências. |
| Agências | <ul><li>Pode criar e editar suas próprias dimensões personalizadas e visualizá-las em seu painel.</li><li>Não é possível editar ou visualizar dimensões personalizadas feitas pelo anunciante.</li></ul> |
| Redes de anúncios | Não é possível visualizar, criar ou editar dimensões personalizadas. |
| Métricas SKAN | Quando Uma única fonte confiável (SSOT) está desativada e os dados são agrupados por uma dimensão personalizada, as métricas SKAN não são exibidas. |
| Métricas | Quando SSOT está ativada e os dados são agrupados por uma dimensão personalizada com base na geolocalização, os dados não são exibidos. |
| Authorization: Bearer | Qualquer membro da equipe pode criar novas dimensões e editar dimensões existentes, mesmo que tenham sido criadas por outro membro da equipe. |
| Diferenciação de maiúsculas e minúsculas | Não. Maiúsculas e minúsculas são tratadas da mesma forma. |
| Valores de dimensão | <ul><li>Pode haver até 10 valores de dimensão personalizados.</li><li>Ao combinar dados com valores de dimensões personalizados, é dada prioridade às dimensões com valor de classificação mais alto. Exemplo:<ul><li>Para a dimensão Mídia paga versus mídia própria, você define o Valor 1 como mídia paga se a fonte de mídia for o Facebook, e o Valor 2 como mídia própria se a fonte de mídia for o Facebook.</li><li>O Facebook pode ser agrupado em mídia paga ou própria com base nas suas configurações, mas a AppsFlyer dá prioridade à configuração Valor 1 (paga).</li></ul></li></ul> |
| Operadores | O operador "não contém" ainda não está disponível. |
| Regras de dimensão | Você pode ter até 10 regras para um valor de dimensão. Elas estão conectados por "or" ("ou"). O conector "and" ("e" )ainda não está disponível. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=vis%C3%A3o-geral h_01H8XWQHPERAEDQVD275TFVC5B=vis%C3%A3o-geral benefits=benef%C3%ADcios h_01H8XWQHPE85376WV1Q9SPQ2NM=benef%C3%ADcios example-use-cases=exemplo-de-casos-de-uso h_01H8XWQHPETE03XG9GGV9EBA2H=exemplo-de-casos-de-uso procedures=procedimentos h_01H8XWQHPESY4DDDJSTR0JDHNB=procedimentos h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-dimension h_01H8XWQHPE22WZ46RTNCYKX96F=delete-or-edit-a-custom-dimension h_01H8XWQHPED4PFPJP2044FT1H8=view-custom-dimension-data h_01H8XWQHPF7WZ7B5Q7T9CHADRK=specifications-and-limitations" />
