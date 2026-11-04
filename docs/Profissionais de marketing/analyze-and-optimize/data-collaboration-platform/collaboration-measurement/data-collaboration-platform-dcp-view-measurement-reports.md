---
title: Plataforma de colaboração de dados (DCP) – Ver relatórios de mensuração
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
  created_at: '2025-04-03T14:39:29Z'
  edited_at: '2026-10-22T03:38:50Z'
  id: 34060852331153
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/34060852331153
---
> **Em resumo:** Personalize seus relatórios de mensuração definindo campos do relatório, níveis de agregação, cronogramas e conexões na nuvem.

Os relatórios de mensuração da Plataforma de colaboração de dados (DCP) fornecem métricas de alto nível, como cliques, impressões e ROAS por campanha. Eles também podem incluir métricas e dimensões adicionais com base no acesso concedido.

Os relatórios são enviados diretamente para o armazenamento em nuvem ou data warehouse conectados. Você pode receber relatórios em um formato predefinido ou personalizá-los para incluir as métricas e dimensões específicas de que precisa.

<div id="what-are-dimensions-and-metrics" />

<Accordion title="O que são dimensões e métricas?">

O relatório de mensuração de colaboração é um relatório agregado que resume os dados agrupando e combinando registros individuais. Ele fornece insights de alto nível, em vez de dados brutos em nível de usuário.

Os campos do relatório são divididos em dois tipos: *dimensões* e *métricas*. Cada um deles pode ser dividido ainda mais em *campos básicos* e *campos calculados*.

<div id="dimensions" />

### Dados

Uma dimensão é uma categoria de agrupamento que agrega dados em nível de evento em registros do relatório. Por exemplo, se o canal de mídia for selecionado como a dimensão do relatório, cada linha conterá dados agregados de todos os eventos atribuídos a esse canal de mídia. O número de linhas é igual ao número de canais de mídia.

Adicionar mais dimensões aumenta a granularidade do agrupamento. Por exemplo, selecionar Data do evento, canal de mídia e campanha resulta em uma linha para cada combinação exclusiva desses campos.

### Metrics

Uma métrica é um dado numérico agrupado com base nas dimensões selecionadas.

Por exemplo, se receita for selecionada como a métrica e canal de mídia for a única dimensão, o relatório exibirá a receita total por canal de mídia.

Quando várias dimensões são selecionadas, como Data do evento, canal de mídia e campanha, a receita é agrupada pela combinação desses campos.

Ao selecionar uma métrica, escolha a função de agregação. Por exemplo, para a métrica de receita, você selecionaria a função **SUM**.

<div id="what-are-basic-and-calculated-fields" />

### O que são campos básicos e campos calculados?

Dimensões e métricas podem ser campos básicos ou campos calculados.

* **Campos básicos:** os campos básicos contêm dados brutos de fontes ou eventos in-app.
* **Campos calculados:** os campos calculados usam campos básicos para calcular valores usando funções definidas.

</Accordion>

<div id="create-a-predefined-report" />

## Criar um relatório predefinido

Para gerar um relatório predefinido, siga estas etapas:

1. No AppsFlyer, no menu lateral, vá para **Collaborate** > **Data Clean Room**.
2. Na página da **Plataforma de Colaboração de Dados** , selecione a colaboração relevante.
3. Na página de colaboração, clique em **Criar relatório.**
4. Na caixa de diálogo exibida, clique em **Approve report.** O relatório é enviado ao seu serviço de nuvem conectado usando um nome e uma programação predefinidos.

<div id="create-a-custom-report" />

## Criar um relatório personalizado

Para criar um relatório personalizado, siga estas etapas:

<div id="1-open-the-new-report-page" />

<Accordion title="1. Abra a página Novo relatório">

1. No AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room**.
2. Na página da **Plataforma de Colaboração de Dados** , selecione a colaboração relevante.
3. No dashboard de mensuração, clique em <Image alt="" src="https://files.readme.io/ed483d2c2b845f1274b3cf84887ea15e0b0384a5f1cf3a5148b1fb8458cd6ec9-34061156892177.png" width="25%" /> **Criar relatório.**
4. Na caixa de diálogo exibida, clique em <Image alt="" src="https://files.readme.io/317ded6d0dbe6b0acfee8d3b8c7898dbab1c9b7ae621802fa867f2a6069f5d79-34061156893457.png" width="25%" /> **Personalizar**.
5. Na página **Novo relatório**, execute as etapas listadas.

</Accordion>

<div id="2-set-the-report-type" />

<Accordion title="2. Defina o tipo de relatório">

Na etapa **Tipo de relatório**, selecione <Image alt="" src="https://files.readme.io/c94890451d831a5a3f1f12b6f42c1c86de1453c175c40cc450e915f6f1f128ad-34061156898449.png" width="3.47%" />  **Commerce media measurement,** em seguida, clique em **Avançar.**

</Accordion>

<div id="3-set-the-report-scope" />

<Accordion title="3. Defina o escopo do relatório">

Na etapa **Filtros e fontes de dados**:

1. Na caixa **Nome do relatório**, insira um nome para o relatório.
   * Pode ser qualquer nome que ajude você a identificar o relatório na plataforma DCR.
   * **Importante!** Certifique-se de que o nome do relatório seja diferente de todos os outros relatórios na sua conta ou você não conseguirá <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">salvar o relatório</Anchor>.
   * Requisitos do nome do relatório:
     * Tamanho: 2-80 caracteres
     * Caracteres válidos:
       * letras **(A-Z, a-z)**
       * números **(0-9)**, *não podem ser o primeiro caractere de um nome*
       * um hífen (-), *não pode ser o primeiro caractere de um nome*
     * Caracteres inválidos:
       * espaços
       * todos os outros símbolos ou caracteres especiais
2. Na caixa **Nome da colaboração**, selecione a colaboração relevante.
3. No controle deslizante **Período**, defina o intervalo do relatório em dias (1-180). Somente eventos de conversão atribuídos que ocorrerem no intervalo selecionado aparecerão no relatório. O intervalo é calculado retroativamente a partir do dia do relatório.
4. Clique em **próximo**.

</Accordion>

<div id="4-set-the-report-dimensions-and-metrics" />

<Accordion title="4. Defina as dimensões e métricas do relatório">

Se quiser personalizar o relatório, você poderá selecionar as [dimensões e métricas](#what-are-dimensions-and-metrics) do relatório. Para ver uma lista completa dos campos do relatório, consulte [o esquema do relatório](#esquema-do-relatório) neste artigo.

Para definir as dimensões e métricas do relatório, siga estas etapas:

1. Na etapa **Structure**, na lista **Dimension from sources**, selecione os campos que você quer que sejam incluídos no relatório.
2. Se quiser criar um [campo calculado](#o-que-são-campos-básicos-e-campos-calculados), clique em **+ Calculated field** e consulte [Criar campo calculado](#criar-campo-calculado) neste artigo.
3. Você pode incluir o campo no relatório como dimensão ou como métrica.
   * Para incluir o campo no relatório como dimensão, clique em **Set as dimension**.
   * Para incluir o campo no relatório como métrica, clique em **Set as metric**.
4. Se você definir o campo como métrica, selecione a função de agregação:
   * **Soma:** O valor da métrica é a soma dos valores no nível do evento agregados no registro do relatório. Por exemplo, a métrica de receita é a soma de  `sku_revenue` de todos os eventos agrupados no registro.
   * **Contagem:** O valor da métrica é a contagem dos valores no nível do evento agregados no registro do relatório. Por exemplo, a métrica de conversões é a contagem de todas as conversões incluídas no registro agrupado.
   * **Contagem distinta**: O valor da métrica é o número de valores únicos de um determinado campo nos eventos agrupados no registro do relatório. Por exemplo, se a métrica selecionada for a contagem distinta de `sku` e um registro agrupado incluir 10 eventos com 4 SKUs diferentes, o valor da métrica será **4**.
5. Para alterar o nome de exibição do campo, passe o cursor sobre o campo e clique em **Edit display name.**

<div id="create-calculated-field" />

#### Criar campo calculado

Os campos calculados contêm valores calculados a partir de valores básicos usando uma função especificada.

Para criar ou editar um campo calculado, faça o seguinte:

1. Para criar ou editar um campo calculado, faça uma das seguintes ações
   * **Criar**: Clique em **+ Calculated field.**
   * **Editar**: Passe o cursor sobre o campo calculado e clique no menu de ações → Edit calculated field.
2. Na caixa de diálogo **Editar** ou **Novo campo calculado**, faça o seguinte:
   1. Na caixa **Campo**, insira o nome do campo.
   2. Na lista **Definir função**, escolha a função usada para calcular o novo valor.
3. Defina a função de acordo com a tabela abaixo:

| **Função** | **A descrição** | **Exemplo de cálculo** | **Descrição do exemplo** |
| --- | --- | --- | --- |
| `ADD` | Soma de dois números | `Cliques + Impressões` | Total de interações (cliques + impressões de anúncios). |
| `ARRAY SIZE` | Transforma a matriz de strings JSON em seu tamanho | `ARRAY_SIZE(Products_Clicked)` | Número de produtos em que um usuário clicou em uma campanha (do JSON). |
| `CASE WHEN` | Devolve um valor quando a primeira condição é atendida, ou ELSE | `CASE WHEN Conversions > 0 THEN 'Successful' ELSE 'Failed' END` | Classifica a performance da campanha com base nas conversões. |
| `CONCAT` | Concatenação de duas strings | `CONCAT(Campaign_Name, ' - ', Region)` | Combina o nome da campanha com a região para reportar. |
| `CONST` | Retorna o seu parâmetro | `CONST('Limite de orçamento de marketing: $5000')` | Retorna um valor constante para referência de orçamento. |
| `DATETIME DIFF` | Período em unidades selecionadas entre `start` e `end` | `DATETIME_DIFF(End_Date, Start_Date, 'day')` | Calcula a duração da campanha em dias. |
| `MAX` | Máximo de dois números | `MAX(Click_Through_Rate, Conversion_Rate)` | Encontra o maior valor entre CTR e taxa de conversão. |
| `MIN` | Mínimo de dois números | `MIN(Budget_Remaining, Daily_Spend_Limit)` | Garante que os gastos não excedam o orçamento diário. |
| `MULTIPLY` | Multiplicação de dois números | `Conversions * Avg_Order_Value` | Calcula a receita total das conversões. |
| `REGEX EXTRACT` | Extrai o primeiro grupo por regex | `REGEX_EXTRACT(Ad_Text, 'PromoCode: (\\w+)')` | Extrai o código promocional do texto do anúncio usando regex. |
| `SUBSTRING` | Substring de uma string do índice `start` ao `end` | `SUBSTRING(Campaign_ID, 0, 5)` | Extrai os 5 primeiros caracteres do ID da campanha. |
| `SUBTRACT` | Subtração de dois números | `Budget_Allocated - Budget_Spent` | Calcula o orçamento restante da campanha. |


</Accordion>

<div id="5-manage-dimension-priority" />

<Accordion title="5. Gerenciar a prioridade de dimensão">

Grupos de dimensões com muito poucos eventos no nível do usuário podem entrar em conflito com as regulamentações de privacidade de dados.

Para resolver isso, o **DCR mescla grupos pequenos** com grupos maiores eliminando as dimensões com a maior especificidade.

Por padrão, as dimensões são removidas na ordem inversa de sua posição na lista **Dimensões do relatório**. No entanto, você pode ajustar a ordem padrão e aplicar uma prioridade de reagrupamento diferente para preservar as dimensões mais importantes para você. Para saber mais, veja um <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-creating-attribution-data-reports#preservando-a-privacidade-ao-agrupar-por-dimensão-reagrupamento">exemplo de reagrupamento</Anchor>.

**Para alterar a prioridade da dimensão:**

1. Na etapa **Gerenciar prioridade da dimensão**, clique em **Gerenciar prioridade da dimensão.**
2. Arraste a dimensão para reorganizar a ordem.
   * A dimensão rotulada como **Prioridade mais alta** (no topo da lista) significa que ela será a última a ser eliminada se o reagrupamento for necessário.
3. [Opcional] Para aplicar o reagrupamento às dimensões de origem personalizadas:
   1. Clique em **Usar opções avançadas para refinar o reagrupamento**
   2. Selecione dimensões de origem personalizadas às quais você gostaria de aplicar o reagrupamento.
   3. As dimensões selecionadas são adicionadas à **lista Manage dimension priority** .
      * Por padrão, essas dimensões são adicionadas ao final da lista como a **Menor prioridade** para reagrupamento. No entanto, você pode reordená-las da mesma forma que as dimensões de dados de atribuição, conforme descrito acima.
4. Clique **Avançar** para salvar suas alterações.
   * A **lista Dimensões do relatório** na tela principal permanece em sua ordem original, mas a ordem revisada foi salva. (Clique novamente no **botão Manage dimension priority** para revisar ou editar sua seleção.)

</Accordion>

<div id="6-set-the-report-schedule-and-destination" />

<Accordion title="6. Defina a programação e o destino do relatório">

O DCP entrega relatórios aos serviços de nuvem selecionados por você usando <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>. Portanto, especificar o destino do relatório envolve selecionar ou criar uma conexão com o Data Locker.

**Para definir a programação e o destino do relatório:**

1. Na etapa **Configurações**, na seção **Programação**, selecione a programação do relatório (diária, semanal ou mensal).
2. Dependendo do intervalo selecionado, selecione a hora, o dia da semana ou o mês do relatório.
3. Na seção **Destino**, selecione na lista de conexões do Data Locker disponíveis em sua conta da AppsFlyer.
   * Se não houver conexões definidas em sua conta:
     * Uma nova aba será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Uma caixa de diálogo **Nova conexão** será aberta. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
   * Se você tiver conexões existentes, mas quiser usar uma nova, clique em **+ Nova conexão no Data Locker**:
     * Uma nova aba será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Uma caixa de diálogo **Nova conexão** será aberta. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
     * Depois de criar a conexão, volte para a aba DCP no navegador e selecione a conexão recém-criada na lista de conexões do Data Locker.
4. Para receber notificações de status do relatório via API, ative **Notificações de status do relatório** e, no campo de endpoint da API, insira o URL da API.
5. Clique em **Save** para salvar o relatório.
6. O novo relatório agora é exibido na guia **Relatórios** .

</Accordion>

<div id="report-scheme" />

## Esquema do relatório

O relatório é composto pelas seguintes dimensões e métricas, categorizadas como campos calculados e campos de atribuição:

<div id="calculated-fields" />

<Accordion title="Campos calculados">

| **Campo** | **A descrição** |
| --- | --- |
| `clicks` | Número total de cliques no anúncio. |
| `CTR` | Taxa de cliques (cliques divididos por impressões). |
| `event_date` | Data em que o evento ocorreu. |
| `impressions` | Número de vezes que o anúncio foi exibido. |
| `total_revenue` | Receita total gerada em todos os eventos. |
|  |  |

</Accordion>

<div id="attribution-fields" />

<Accordion title="Campos de atribuição">

| **Campo** | **Descrição** |
| --- | --- |
| `Exportar página de dados: fuso horário selecionado pelo aplicativo.` | Identificador exclusivo do anúncio. |
| `ad_name` | Nome do anúncio. |
| `ad_type` | Tipo de anúncio (por exemplo, banner, vídeo). |
| `Versão do sistema operacional no momento da conversão` | Identificador exclusivo do conjunto de anúncios. |
| `adset_name` | Nome do conjunto de anúncios. |
| `advertising_id` | ID do dispositivo redefinível pelo usuário (por exemplo, GAID). |
| `android_id` | Device ID permanente do Android. |
| `Preenchido para posicionamento de anúncio de CTV` | Identificador exclusivo do aplicativo. |
| `Indica se o usuário permite que o Google use seus dados a nível de usuário para mensuração e anúncios personalizados (true) ou não (false).` | O nome do aplicativo. |
| `app_version` | A versão do aplicativo. |
| `appsflyer_id` | ID exclusivo atribuído pela AppsFlyer. |
| `Fuso horário (do cliente) no momento da conversão` | Identificador exclusivo da campanha. |
| `campaign_name` | Nome da campanha. |
| `Disponível apenas em relatórios avançados.` | Canal de mídia (por exemplo, YouTube). |
| `Versão do SDK da AppsFlyer` | Cidade do usuário com base na localização do IP. |
| `Disponível apenas em relatórios avançados.` | Código de país ISO 3166-1 alfa-2 (por exemplo, US, GB). |
| `cuid` | Identificador exclusivo do cliente/usuário. |
| `device_category` | Tipo de dispositivo (por exemplo, celular, tablet). |
| `DMA (área de mercado designada)` | Nome do evento (por exemplo, instalação, compra). |
| `event_revenue` | Receita gerada a partir do evento. |
| `idfa` | ID de anúncio do iOS que pode ser redefinido pelo usuário. |
| `idfv` | ID do fornecedor atribuído pelo iOS. |
| `Número real` | A plataforma (iOS, Android etc.). |
| `Nome do Adset` | Região do usuário com base na localização do IP. |
| `sku_revenue` | Receita associada a um SKU específico. |
| `Sequência de caracteres` | Estado do usuário com base na localização do IP. |

</Accordion>

<div id="scheme-fields" />

<Accordion title="Campos do esquema">

| **Campo** | **A descrição** | **Disponibilidade no site** | **Disponibilidade fora do site** |
| --- | --- | --- | --- |
| conversões | Número de conversões | verdadeiro | FALSO |
| Count\_AFID | Número total de usuários únicos | verdadeiro | verdadeiro |

</Accordion>

<div data-zendesk-anchors="h_01JQY1FA02JN6VR67HJ5118SFF=what-are-dimensions-and-metrics dimensions=dados h_01JR5NBE6NQ22QCFZG9XRVGM45=dados h_01JR5NC59TQ45QPWP7JG6BQKXX=metrics what-are-basic-and-calculated-fields=o-que-s%C3%A3o-campos-b%C3%A1sicos-e-campos-calculados h_01JQY33FZ2H59YZVVXBN9J61RE=o-que-s%C3%A3o-campos-b%C3%A1sicos-e-campos-calculados create-a-predefined-report=criar-um-relat%C3%B3rio-predefinido h_01JQY1FA03AXH588Z5C9HCJHMS=criar-um-relat%C3%B3rio-predefinido create-a-custom-report=criar-um-relat%C3%B3rio-personalizado h_01JQY1FA038V0V1PKBF1CC0B5J=criar-um-relat%C3%B3rio-personalizado h_01JQY1FA035K7VWX4BDC796SVT=1-open-the-new-report-page h_01JQY1FA03Z0W8N8PFVGEC3HRM=2-set-the-report-type h_01JQY1FA03CWP0GSJY46CEJRJY=3-set-the-report-scope h_01JQY1FA03WA8NNB4RT1VBK0F5=4-set-the-report-dimensions-and-metrics create-calculated-field=criar-campo-calculado h_01JQY1FA03PA40NCTZXHWGQ86C=criar-campo-calculado h_01JQY1FA03TMN4N7V3F83EK4EY=5-manage-dimension-priority h_01JQY1FA03PRSGHSKNTKNV4NH3=6-set-the-report-schedule-and-destination report-scheme=esquema-do-relat%C3%B3rio h_01JQY1FA03S41J7TR5HAF6G8PW=esquema-do-relat%C3%B3rio h_01JQY1FA0494AK29M0R7ZRJ4DT=calculated-fields h_01JQY1FA0486WK4GHV5G3TZ77V=attribution-fields h_01JQY1FA04DTN2C6A541J25RZJ=scheme-fields" />
