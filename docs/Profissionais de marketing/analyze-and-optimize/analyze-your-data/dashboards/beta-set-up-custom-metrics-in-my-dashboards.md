---
title: '[Beta] Configure métricas personalizadas nos Meus dashboards'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2025-01-01T09:21:05Z'
  edited_at: '2026-08-22T00:03:21Z'
  id: 31400289569169
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/31400289569169
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Resumo:** Defina suas próprias métricas e use-as para visualizar dados nos Meus dashboards.

## Sobre métricas personalizadas

Métricas personalizadas permitem que você adapte a análise de dados às suas necessidades únicas, definindo cálculos com base em dados existentes. Elas oferecem mais controle e flexibilidade do que métricas padrão, permitindo que você combine várias métricas, crie projeções e personalize KPIs.

Por exemplo, em vez de métricas genéricas como "receita" ou "cliques", você pode criar fórmulas para seus casos de uso exclusivos, como:

* Previsão de Receita D60 = Receita D1 x 3
* Click-to-purchase rate = Cliques / af\_purchase [usuários únicos]

Métricas personalizadas são compatíveis com todos os tipos de widgets nos Meus dashboards, incluindo tabelas, gráficos e KPIs. Seja você um profissional de marketing acompanhando o ROI da sua campanha, um gerente de produto monitorando o engajamento ou um analista prevendo a performance, métricas personalizadas aprimoram sua capacidade de analisar tendências, identificar oportunidades e tomar decisões baseadas em dados para as necessidades únicas do seu negócio - tudo diretamente do seu dashboard.

**Atenção:** As dimensões personalizadas são criadas no nível da conta, o que significa que diferentes aplicativos na mesma conta da AppsFlyer podem usar as mesmas dimensões personalizadas.

## Procedimentos

<div id="create-a-custom-metric" />

<Accordion title="Criar uma métrica personalizada">

Para criar uma métrica personalizada:

1. No seu dashboard:
   * Clique **+ Criar novo** > **Métricas personalizadas**.
   * Em qualquer gráfico ou tabela, no menu suspenso **Métricas**, clique em **+ Criar métrica personalizada**.
2. Dê um nome para a sua métrica. Na parte superior do editor de métricas personalizadas, insira um nome descritivo para a sua métrica (por exemplo, "IPM").
3. Escolha um **Tipo de métrica**. Selecione se a métrica é numérica, uma porcentagem ou monetária (moeda).
4. Defina sua fórmula de métrica. Aqui, há duas opções:
   * Para começar rápido: use fórmulas sugeridas (exibidas no menu à esquerda do editor de métricas personalizadas). Em seguida, use o editor para editar o modelo de acordo com as suas necessidades específicas - por exemplo, você pode selecionar diferentes eventos in-app ou modificar multiplicadores ou outros parâmetros. Por exemplo, para o modelo `Retention rate D2 / Retention rate D7`, você pode substituir D2 e D7 por diferentes eventos ou períodos de tempo.
   * Use o editor interativo: Adicione métricas e operadores (usando os botões) e números (usando seu teclado) para definir sua fórmula.
5. Visualize a fórmula no campo de fórmula fx.
6. [Opcional] Se você criou a métrica personalizada a partir do dashboard geral, clique em **salvar e adicionar ao gráfico**.  
   Um novo gráfico é criado, incluindo sua métrica personalizada.
7. Clique em **Salvar**.
   * Se você criou a métrica personalizada a partir de um widget, ela é adicionada automaticamente ao gráfico ou tabela.
   * Se você criou a métrica personalizada no dashboard geral, agora pode adicioná-la a qualquer widget que desejar.

</Accordion>

<div id="edit-a-custom-metric" />

<Accordion title="Editar uma métrica personalizada">

Você pode editar uma métrica personalizada tanto a partir do dashboard quanto de um widget específico. **Atenção**! Quaisquer alterações que você fizer em uma métrica personalizada são em nível de conta, o que significa que as alterações afetam a métrica para todos os usuários e dashboards.

**Para editar uma dimensão personalizada do dashboard**:

1. No seu dashboard, clique em **+ Criar novo** > **Métricas personalizadas**.
2. No menu do lado esquerdo do editor de métricas personalizadas, em "minhas métricas personalizadas", encontre a métrica que você deseja editar e clique no ícone **Editar**.
3. Faça as alterações que desejar na fórmula da métrica personalizada.
4. Clique em **Salvar**.

Para editar uma dimensão personalizada de um widget

1. Em qualquer gráfico ou tabela, no menu suspenso **Métricas**, encontre a métrica que deseja editar e clique no ícone **Editar**.
2. No menu do lado esquerdo do editor de métricas personalizadas, em "minhas métricas personalizadas", encontre a métrica que você deseja editar e clique no ícone **Editar**.
3. Faça as alterações que desejar na fórmula da métrica personalizada.
4. Clique em **Salvar**.

</Accordion>

<div id="delete-a-custom-metric" />

<Accordion title="Deletar uma métrica personalizada">

Você pode deletar uma métrica personalizada tanto a partir do dashboard quanto de um widget específico. **Atenção**! Quaisquer exclusões de uma métrica personalizada são em nível de conta, o que significa que a métrica é removida para todos os usuários e dashboards.

**Para deletar uma dimensão personalizada do dashboard**:

1. No seu dashboard, clique em **+ Criar novo** > **Métricas personalizadas**.
2. No menu do lado esquerdo do editor de métricas personalizadas, em "minhas métricas personalizadas", encontre a métrica que você deseja excluir e clique no ícone **Deletar**.

Para excluir uma dimensão personalizada de um widget

* Em qualquer gráfico ou tabela, no menu suspenso **Métricas**, encontre a métrica que deseja deletar e clique no ícone **Excluir**.

</Accordion>

## Informações adicionais

<div id="best-practices" />

<Accordion title="Práticas recomendadas">

* **Comece pequeno**: Comece com métricas básicas e adicione complexidade progressivamente conforme necessário e à medida que você se familiariza mais com o desenvolvimento de fórmulas.
* **Alinhe com os seus objetivos**: Garanta que cada métrica se relacione a um objetivo ou dúvida de negócios específico.
* **Documente suas fórmulas**: Mantenha uma documentação das suas fórmulas personalizadas para atualizações ou debugging fáceis.
* **Revise periodicamente** Avalie regularmente suas métricas para garantir que elas permaneçam relevantes.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Acessibilidade em nível de conta | Todos os membros da conta podem criar, visualizar, editar e excluir qualquer métrica personalizada. Isso inclui métricas criadas por outros usuários. |
| Limite de métricas personalizadas | <ul><li>As métricas personalizadas têm um limite de 100 métricas personalizadas por conta.</li><li>No momento, as métricas personalizadas são compatíveis apenas com o detalhamento diário. Os detalhamentos semanais e mensais não são suportados.</li></ul> |
| Complexidade da fórmula | Máximo de 5 métricas por fórmula de métrica personalizada. |
| Restrição | Métricas personalizadas não podem ser usadas como componentes em outras fórmulas de métricas personalizadas. |

</Accordion>

<div data-zendesk-anchors="about-custom-metrics=sobre-m%C3%A9tricas-personalizadas h_01H8XWQHPERAEDQVD275TFVC5B=sobre-m%C3%A9tricas-personalizadas procedures=procedimentos h_01H8XWQHPESY4DDDJSTR0JDHNB=procedimentos h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-metric h_01H8XWQHPE22WZ46RTNCYKX96F=edit-a-custom-metric h_01H8XWQHPED4PFPJP2044FT1H8=delete-a-custom-metric additional-information=informa%C3%A7%C3%B5es-adicionais 01JGGT56V05BJRCV9Q572JJR3W=informa%C3%A7%C3%B5es-adicionais 01JGK1XAVB3M5KDA59A9ZASM2K=best-practices h_01H8XWQHPF7WZ7B5Q7T9CHADRK=traits-and-limitations" />
