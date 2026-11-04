---
title: >-
  Plataforma de colaboração de dados (DCP) - Execute uma consulta dinâmica na
  DCP
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-10-15T11:14:42Z'
  edited_at: '2026-10-20T03:55:04Z'
  id: 51953788887569
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/51953788887569
---
> **Resumo:** Dynamic Query permite que você execute suas próprias consultas SQL diretamente nos dados da sua Plataforma de colaboração de dados (DCP). Consulte seus próprios dados, seus próprios dados de atribuição da AppsFlyer ou dados compartilhados em uma colaboração para responder a perguntas específicas sem configurar um relatório.

<div id="about-dynamic-query" />

## Sobre o Dynamic Query

O Dynamic Query permite que você execute consultas ad hoc e personalizadas nos seus dados da DCP em tempo real para responder às suas perguntas específicas de colaboração com rapidez e eficiência.

* Permita que um colaborador segmente melhor seus dados antes de criar uma audiência.
* Crie sua própria lógica de mensuração de campanha com o Dynamic Query.

O Dynamic Query funciona de forma diferente, dependendo se você consulta seus próprios dados ou dados compartilhados em uma colaboração.

<div id="before-you-start" />

## Antes de começar

Antes de executar qualquer consulta, <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configure o destino do seu cloud bucket</Anchor>. Esta etapa é obrigatória, porque toda consulta é executada no seu próprio cloud bucket e grava os resultados diretamente no seu armazenamento. A AppsFlyer não armazena os resultados das suas consultas, então seus dados permanecem no seu próprio ambiente de nuvem.

<div id="run-a-query-on-your-own-data" />

## Execute uma consulta nos seus próprios dados

As seções a seguir abordam como acessar e consultar dados que pertencem a você. O painel Fontes aqui lista apenas as fontes que pertencem a você. Nesta visualização, você não pode adicionar a fonte de um colaborador. Se quiser consultar dados compartilhados com você em uma colaboração, consulte [Execute uma consulta com dados de colaboração](#).

<div id="access-dynamic-query" />

### Acesse o Dynamic Query

1. Na AppsFlyer, acesse o menu lateral > **Colaborar** > **Data Clean Room**.
2. Selecione a aba **Dynamic Query**.

<div id="write-your-query-on-your-own-data" />

### Escreva sua consulta nos seus próprios dados

1. Navegue pelos campos da fonte no painel Fontes. Clique em um campo para visualizar seus valores distintos.

   <div id="note" />

   > 📘 **Importante!**
   >
   > Isso ajuda seus filtros a corresponder aos dados reais antes de você escrever a consulta. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboração de dados (DCP) - Criar e gerenciar fontes</Anchor>.

2. Escreva sua consulta livremente, em nível bruto ou agregado, como preferir. Todas as fontes aqui pertencem a você, então não há verificação de permissão nem exigência de GROUP BY.

   <div id="note-1" />

   > 📘 **Importante!**
   >
   > Se você também for cliente da AppsFlyer, poderá consultar seus dados de atribuição da AF dessa forma também, mas os resultados são apenas agregados, mesmo sendo seus próprios dados.


<div id="run-a-query-with-collaboration-data" />

## Execute uma consulta com dados de colaboração

As seções a seguir explicam como obter acesso e consultar os dados compartilhados com você em uma colaboração. Para consultar apenas os dados que pertencem a você, consulte [Executar uma consulta nos seus próprios dados](#).

<div id="access-dynamic-query-in-a-collaboration" />

### Acesse o Dynamic Query em uma colaboração

1. Na AppsFlyer, vá para o menu lateral > **Collaborate** > **Data Clean Room**.
2. Selecione a guia **Colaborações** e, em seguida, selecione a colaboração relevante.
3. Selecione a guia **Dynamic Query**.

Quando você consulta dados compartilhados em uma colaboração, o Dynamic Query pode acessar todas as fontes <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">adicionadas a essa colaboração</Anchor>.

<div id="write-your-query-with-collaboration-data" />

### Escreva sua consulta com dados de colaboração

1. Explore os campos da fonte no painel Fontes. Clique em um campo para visualizar os valores distintos.

   <div id="note-2" />

   > 📘 **Importante!**
   >
   > Isso ajuda seus filtros a corresponderem aos dados reais antes de você escrever a consulta. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboração de dados (DCP) - Criar e gerenciar fontes</Anchor>.

2. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-sharing-permissions">Verifique o tipo de permissão da fonte</Anchor> para determinar se sua consulta precisa de um join. Há dois tipos de permissão:

   

| Tipo de permissão | Join necessário? | Nível do resultado |
| --- | --- | --- |
| Interseccionado | Sim, você deve fazer join com sua própria fonte | Somente agregados |
| Todos os dados | Não, você pode consultá-la livremente | Somente agregados |

3. Escreva sua consulta com uma cláusula GROUP BY ou uma função de agregação, como `COUNT(*)`.

   <div id="important" />

   > 🚧 **Importante:**
   >
   > Uma fonte que não pertence a você sempre retorna resultados agregados, independentemente do tipo de permissão sob o qual ela foi compartilhada. Os resultados em nível bruto permanecem disponíveis apenas para fontes que pertencem a você.


<div id="explore-sample-queries" />

## Explore consultas de exemplo

Os exemplos a seguir mostram como cada tipo de permissão funciona na prática.

<div id="h_01M56WAZ8WGKHMG3BJYXNYHJT4" />

<Accordion title="Encontre candidatos para colaboração entre marcas">

Esta consulta usa a permissão Todos os dados para encontrar as principais marcas em uma colaboração por contagem de clientes e receita nos últimos 60 dias.

```sql
SELECT
    t.brand_name,
    COUNT(DISTINCT t.hashed_email) AS total_clients,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 60) AND current_date()
GROUP BY t.brand_name
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8WWJ78CQCK17FXWCWF" />

<Accordion title="Crie um segmento de retargeting para clube de fidelidade">

Esta consulta usa a permissão Interseccionado. Ela faz join dos dados do seu clube de fidelidade com os dados de compras de um colaborador, por país, nos últimos 30 dias.

```sql
SELECT
    t.country,
    COUNT(DISTINCT l.hashed_email) AS loyalty_members,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
JOIN <my_loyalty_club_table> l ON l.hashed_email = t.hashed_email  -- required join satisfies intersection permission
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
    AND t.brand_name = '<collaborator_brand_name>'
GROUP BY t.country
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8W6KN04JZN06T75A9A" />

<Accordion title="Descubra audiências antes de uma campanha de aquisição de usuários (UA)">

Esta consulta usa a permissão All Data para segmentar as transações de um colaborador por país e categoria, para que você possa descobrir audiências de alto valor antes de criar uma para aquisição de usuários.

```sql
SELECT
    t.country,
    t.category,
    COUNT(DISTINCT t.hashed_email) AS total_buyers,
    COUNT(*)                       AS total_purchases,
    SUM(t.revenue)                 AS total_revenue,
    AVG(t.revenue)                 AS avg_order_value
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
GROUP BY t.country, t.category
ORDER BY total_buyers DESC
LIMIT 20;
```

</Accordion>

<div id="view-and-download-query-results" />

## Visualize e faça download dos resultados da consulta

As seções a seguir explicam como executar sua consulta e gerenciar os resultados.

<div id="h_01M56WAZ8WXC0X46H2P3AY3GFX" />

<Accordion title="Modos de execução do Dynamic Query">

Toda consulta é executada em um de dois modos:

* **Dados de amostra** (padrão) são executados em um pequeno subconjunto dos seus dados, para que você possa refinar a consulta antes de executá-la no conjunto de dados completo.
* **Todos os dados** é executado na fonte completa. Somente este modo tem um botão **Download**.

<div id="note-3" />

> 📘 **Importante!**
>
> Não confunda o modo de execução **Todos os dados** com o tipo de permissão **All Data**. Os tipos de permissão controlam o que um colaborador pode acessar. Os modos de execução controlam quanto da sua própria consulta você executa.

</Accordion>

<div id="h_01M56WAZ8W2E7P4S60T0WJ4NNF" />

<Accordion title="Histórico de consultas">

Sua consulta e os resultados permanecem no lugar enquanto você navega entre abas e planilhas. Você pode abrir várias planilhas para trabalhar em consultas diferentes ao mesmo tempo.

Selecione **Todas as execuções** para ver o histórico das suas consultas, incluindo o status e a duração de cada execução, realizada no modo Dados de amostra ou Todos os dados.

</Accordion>

<div id="h_01M56WAZ8WCVEVWRQK68736H02" />

<Accordion title="Limites de resultados e downloads">

Os resultados são exibidos em páginas de 100 linhas, com até 10 páginas (1.000 linhas no total). Para ver tudo, faça download dos resultados. A contagem total de resultados sempre aparece, mesmo que seja maior do que o que está sendo exibido. Essa contagem é limitada a 10 milhões, então, se sua contagem real de resultados for de 20 milhões, a contagem exibida ainda mostrará 10 milhões.

Você pode fazer download de até 1 milhão de linhas diretamente. Se os resultados forem maiores, a Dynamic Query redirecionará você para o seu <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">cloud bucket</Anchor>. Seu cloud bucket armazena até 10 milhões de linhas. Se precisar de mais, entre em contato com seu Customer Success Manager (CSM) para expandir esse limite.

</Accordion>

<div id="privacy-and-query-restrictions" />

## Privacidade e restrições de consulta

A Dynamic Query aplica proteções de privacidade em vários níveis:

* Fontes que não pertencem a você sempre retornam resultados agregados; consulte [Executar uma consulta com dados de colaboração](#).
* Campos de identificador do tipo chave, como AppsFlyer ID, Android ID e IDFA (identificador para anunciantes), sempre retornam como valores com hash nos resultados da consulta.
* Valores distintos não estão disponíveis para campos categorizados como chaves, como AppsFlyer ID ou Android ID, ao navegar pelo painel Fontes.

<div id="traits-and-limitations" />

## Especificações e limitações

| Caraterística | Descrição |
| --- | --- |
| Limite de exibição de resultados | 1,000 rows (100 rows por página, até 10 páginas) |
| Limite de download | 1 milhão de linhas diretamente, 10 milhões de linhas pelo seu cloud bucket; entre em contato com seu CSM para expandir |
| Configuração do cloud bucket | Obrigatória antes de você executar qualquer consulta, não apenas antes de fazer download |
| Modos de execução | Dados de amostra (padrão, sem download) e Todos os dados (fonte completa, download disponível) |

<div id="see-also" />

## Consulte também

* <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-dynamic-query">Data Clean Room - Consulta dinâmica</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-guide">Plataforma de colaboração de dados (DCP) - Guia</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-sharing-permissions">Permissões de compartilhamento da Plataforma de colaboração de dados (DCP)</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">Plataforma de colaboração de dados (DCP) - Criar uma colaboração</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">Dicionário de campo de dados brutos</Anchor>

<div data-zendesk-anchors="h_01M56WAZ8VZKYM6TP7AYGKQA52=sobre-o-dynamic-query h_01M56WAZ8VQ4D6NHCNJ463ZJE4=antes-de-come%C3%A7ar h_01M56WAZ8VPZPM8P1H0DNVTTA6=execute-uma-consulta-nos-seus-pr%C3%B3prios-dados h_01M56WAZ8VQ4NNZEYAX4ZAZCFZ=acesse-o-dynamic-query h_01M56WAZ8VPG7QEAPSSBG11N11=escreva-sua-consulta-nos-seus-pr%C3%B3prios-dados h_01M56WAZ8VDWA030BB53YP1TR2=importante h_01M56WAZ8VBVRQV8B7J0TA21ZM=importante-1 h_01M56WAZ8V82DRQ92ZPC3KFZYJ=execute-uma-consulta-com-dados-de-colabora%C3%A7%C3%A3o h_01M56WAZ8VK33RR50SWQYV7KE0=acesse-o-dynamic-query-em-uma-colabora%C3%A7%C3%A3o h_01M56WAZ8WXRM23PDCTA11APA2=escreva-sua-consulta-com-dados-de-colabora%C3%A7%C3%A3o h_01M56WAZ8WM0ZHFDKTT7AZ1CG8=importante-2 h_01M56WAZ8W01XKEQDYVZCQ23ZZ=importante-3 h_01M56WAZ8W348ZTS79F23MAP3C=explore-consultas-de-exemplo h_01M56WAZ8WZ23RCK7TYQC2FPZD=visualize-e-fa%C3%A7a-download-dos-resultados-da-consulta h_01M56WAZ8WK936BRP4F7VHG954=importante-4 h_01M56WAZ8W471Z9B14ZJ3V41VC=privacidade-e-restri%C3%A7%C3%B5es-de-consulta h_01M56WAZ8WCVFPD8JMHQ39HMEJ=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01M56WAZ8WBY66ZBNHSNGFAJKD=consulte-tamb%C3%A9m" />
