---
title: Tabela dinâmica—métricas do usuário
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-08-18T00:03:05Z'
  id: 115001421846
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/115001421846
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral**: Ver diferentes métricas do usuário—LTV, atividade, Protect360 e retenção. Baixe os resultados como arquivos CSV para ingestão por seus sistemas de BI. O pivot é compatível com vários aplicativos em uma única consulta. Use para gerar chamadas de Master API.

## Sobre a página de relatórios de pivô

Usando o Pivot, você gera relatórios personalizados contendo métricas de aquisição de usuários. O Pivot vem com vários relatórios predefinidos para usar como base, a partir da qual você cria seus relatórios personalizados. Os relatórios criados por um determinado usuário estão disponíveis para todos os usuários.

Os relatórios pivot predefinidos disponíveis são:

* Fonte de mídia por data
* Hierarquia completa
* Análise de custos

**Atenção:** Para que os dados da campanha sejam visíveis nos pivôs, as campanhas devem ter instalações.

## Procedimentos do Pivot

Crie e modifique as tabelas pivot existentes na interface do usuário. Para fazê-lo, siga os procedimentos das seções abaixo.

**Para usar o Pivot** :

* Na AppsFlyer, através do menu lateral, selecione **Analisar** > **Eventos**.  
  A lista de relatórios atualmente definidos é exibida.

<div id="pivot-page-controls-and-options" />

<Accordion title="Página do Pivot—controles e opções">

<Table>
  <thead>
    <tr>
      <th>
        Coluna/opção
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Nome
      </td>
      <td>
        Selecione um nome de relatório para exibir a tabela pivot associada.
      </td>
    </tr>
    <tr>
      <td>
        Clique na coluna
      </td>
      <td>
        Algumas colunas, conforme indicado na interface, são ordenadas quando se clica no nome da coluna.
      </td>
    </tr>
    <tr>
      <td>
        Última modificação
      </td>
      <td>
        A última vez em que a estrutura do relatório foi modificada.
      </td>
    </tr>
    <tr>
      <td>
        Modificado por
      </td>
      <td>
        Nome do usuário que modificou a tabela dinâmica.
      </td>
    </tr>
    <tr>
      <td>
        Nome da aplicação
      </td>
      <td>
        * Se um aplicativo incluído: o nome do aplicativo
        * Se vários aplicativos estiverem incluídos: o número de aplicativos
      </td>
    </tr>
    <tr>
      <td>
        Ações
      </td>
      <td>
        | Ação | Observações |
        | --- | --- |
        | Duplicar | Copie um relatório pivot existente. |
        | Renomear | Altere o nome do relatório. |
        | Ver registro do histórico | Veja quem definiu a estrutura do relatório, o que foi feito e quando. |
        | Copiar link da Master API | Gere um URL para extrair os dados por meio da <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>. Para usar a Master API, você precisa obter o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token da API</Anchor> (permissões de administrador necessárias) para usar no cabeçalho de autenticação. |
        | Excluir | Exclua o pivot selecionado. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="Adicionar um relatório pivot">

**Para adicionar um relatório pivot**:

1. Clique em **Adicionar pivot.**  
   A janela do novo pivot é aberto.
2. Insira o nome da tabela pivot.
3. Clique em **Submeter**.  
   A janela Adicionar tabela pivot é aberta.
4. Selecione aplicativos, dimensões e métricas. Defina configurações de filtros e valores a serem exibidos.

| Secção | Descrição |
| --- | --- |
| Aplicativos | Selecione 1 ou mais aplicativos para incluir na tabela pivot. |
| Dimensões | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />Use dimensões para agrupar, estruturar e classificar seus relatórios pivot.<br /><br />**Para selecionar dimensões**:<ol><li>Clique em **Dimensões.**</li><li>Selecione uma dimensão e arraste-a para uma seção. As dimensões têm o seguinte impacto sobre o pivot:<ul><li>5 linhas Linhas: as dimensões colocadas em linhas determinam a hierarquia "agrupar por".</li><li>Colunas Colunas: as dimensões colocadas em colunas multiplicam todo o resultado da tabela de acordo com os valores da dimensão.</li></ul></li></ol> |
| KPIs | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />Os KPIs são agrupados de acordo com o tipo da seguinte forma:<ul><li>Dados de LTV: 5 anos</li><li><Anchor target="_blank" href="/marketers/pt/docs/activity-dashboard#especificações-e-limitações">atividades</Anchor></li><li>Retenção Dia de retenção, taxa de retenção. **Atenção:** Observação: role a tela para baixo na seção de retenção para selecionar Taxas de retenção e Protect360 (para contas com o Protect360 ativado.)</li><li><Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api#kpis">Sobre as métricas.</Anchor></li></ul>Na maioria das vezes, coloque KPIs na seção de valor. Se necessário, os KPIs podem ser usados como uma dimensão.<br /><br />Arraste e solte o KPI para a seção relevante. |
| Valores | Para cada KPI, defina o método de cálculo selecionando um operador:<ul><li>Soma</li><li>Contagem</li><li>Máx</li><li>Mín</li><li>Classificar</li><li>Média</li></ul> |
| Filtros | Coloque os filtros necessários na seção de filtros. Configure como os filtros são definidos:<ul><li>Texto</li><li>Seleção múltipla</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="Visualizar um relatório pivot">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**Para visualizar um relatório pivot**:

* Selecione um relatório na página do Pivot para exibi-lo.
* Opções de exibição de relatório:

| Secção | Descrição |
| --- | --- |
| (1) Dimensões selecionadas | A primeira coluna contém as dimensões selecionadas para os agrupamentos do relatório. As dimensões são agrupadas de acordo com a ordem na página de edição do pivot. No exemplo acima, a dimensão principal é o nome do aplicativo, seguido pela fonte de mídia e terminando com a data de instalação. |
| (2) Métricas | As colunas restantes são os KPIs selecionados como **Valores** na página de edição do pivot. No exemplo acima, o primeiro KPI são as impressões, seguidas de cliques, instalações etc. |
| (3) Filtros | Os filtros definidos para o relatório na página de edição dinâmica aparecem aqui. Você pode digitar sua string de filtragem ou selecionar vários itens nas caixas suspensas.<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| (4) Data selecionada | Use o seletor de período para refinar sua busca para datas específicas. Você pode selecionar seu próprio período personalizado ou usar um dos botões de período predefinido. |
| (5) Ações | Você pode acessar as mesmas ações por relatório dinâmico disponíveis na [lista de relatórios dinâmicos](/docs/pivot-table-user-metrics#view-a-pivot-report). |

</Accordion>

## Características e Limitações

<div id="traits-and-limitations::e6883df" />

<Accordion title="Características e Limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso da ad network ao relatório | Não |
| Acesso de agência | Não |
| Transparência das agências | Sim |
| Fuso horário específico do aplicativo | Sim<br /><br />Exceção: Exceção: em todos os casos a seguir, a AppsFlyer ignora o fuso horário específico do aplicativo e usa como fuso horário padrão UTC +0:<ul><li>O relatório contém dados de vários aplicativos, e os aplicativos têm fusos horários diferentes.</li><li>Todos os aplicativos têm o mesmo fuso horário e o fuso horário de pelo menos um dos aplicativos foi alterado durante o período do relatório da coorte. Para determinar o período do relatório:<ul><li>data\_inicial A primeira data no intervalo de datas de conversão.</li><li>Data final. Data final: é calculada somando o número de dias na duração da exibição à última data no período da conversão. Exemplo: Última data: Jan 1, 2019 Duração do relatório: 30 dias Data final. Jan 31, 2019</li></ul></li></ul> |
| Moeda específica da aplicação | Os resultados sempre retornam em USD. |
| Dados orgânicos | Incluso |
| Dados não orgânicos | Incluso |
| Atualização dos dados | Atualização de dados: Diariamente. A atualização dos dados é equivalente à da <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>. |
| Acesso do utilizador à conta | Sim |
| Retargeting da receita | Incluso |
| Mudanças no nome da campanha | A tabela dinâmica não alinha o custo do nome da campanha ao nome da campanha mais recente relatado. Isso significa que cada nome de campanha usado terá um custo associado a ele. |
| Dados de retargeting | <ul><li>Em geral, use <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Cohorte</Anchor> para visualizar dados de retargeting.</li><li>KPIs de atividade para tráfego de após 1 de fevereiro de 2025 incluem dados unificados (UA e retargeting juntos).</li></ul> |
| Dados de custo | A AppsFlyer obtém dados de custo principalmente por meio da API de custo. Os dados são oferecidos pelos parceiros integrados. <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">Lista de dimensões por parceiro integrado.</Anchor> |
| Parcela de retenção | Para acessar a parcela de retenção, inclua as instalações no relatório. |
| Máximo de linhas por relatório | 200 mil |
| Dados históricos | <ul><li>Dados de LTV: 25 meses (2 anos + 1 mês)</li><li>Dados de atividade: 3 anos</li></ul> |
| DAU médio e MAU médio | Ao usar DAU médio ou MAU médio com a agregação Soma em qualquer agrupamento (por exemplo, canal de mídia ou campanha), os totais podem incluir contagens de usuários duplicadas. Isso ocorre quando um usuário realiza tanto uma instalação quanto um reengajamento no período selecionado, fazendo com que ele apareça em vários agrupamentos. |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=sobre-a-p%C3%A1gina-de-relat%C3%B3rios-de-piv%C3%B4 h_01HJR8389QPFKR9X6V52N7PHMM=sobre-a-p%C3%A1gina-de-relat%C3%B3rios-de-piv%C3%B4 pivot-procedures=procedimentos-do-pivot h_01HJR8389QPNRX8Y26VQWN0ZXP=procedimentos-do-pivot pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HJR8389SPJZG6AYGABB17V1N=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
