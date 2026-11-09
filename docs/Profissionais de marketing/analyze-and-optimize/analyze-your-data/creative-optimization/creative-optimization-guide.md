---
title: Guia para a otimização de criativos
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2026-09-24T00:01:47Z'
  id: 18564718580625
  locale: pt
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/pt/articles/18564718580625
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** a otimização de criativos permite reunir todos os dados de recursos de criativos de todas as suas campanhas em uma única plataforma, para que você possa analisar seu desempenho, descobrir quais criativos funcionam melhor e tomar melhores decisões baseadas em dados. Os dados são de LTV, o que significa que as métricas exibidas são para conversões que ocorreram a partir de criativos durante o intervalo de datas selecionado.

<Image align="center" alt="Main image -Default view.jpg" src="https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg" />

<div id="about-creative-optimization" />

## Sobre a otimização de criativos

A **otimização de criativos** é o seu local centralizado para mensurar a performance dos criativos usados em todas as suas campanhas. Ele permite que você reúna facilmente todos os seus recursos criativos de todos os canais de mídia em um só lugar, ou em seu sistema de BI, e analise seu desempenho por dimensões selecionadas, em múltiplas campanhas, canais e muito mais. A otimização de criativos permite que você analise diferentes métricas e KPIs para obter insights críticos antes de planejar, selecionar e produzir seu próximo lote de criativos.

Os dashboards da otimização de criativos permitem que você mensure a performance de vídeos, imagens, HTML e texto e veja a performance deles ao longo do tempo, em todos os canais. Cada criativo é analisado, agregado e combinado usando algoritmos de IA poderosos. Isso significa que os mesmos criativos usados para diferentes campanhas e fontes de mídia são identificados e exibidos como um só nos dashboards, independentemente da convenção de nomenclatura, ID do anúncio ou quaisquer outros metadados.

Use o <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-overview-dashboard">dashboard de visão geral da solução de otimização de criativos</Anchor> para visualizar seus dados em diversos tipos de gráficos informativos ou em uma tabela detalhada, que fornece todas as informações necessárias para otimizar e selecionar os melhores criativos para suas campanhas.

Com o <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-discovery-ai-dashboard">dashboard de descoberta da otimização de criativos</Anchor>, que se baseia em IA, você não precisa mais usar sua intuição para criar assets de sucesso. Tenha uma visão abrangente de todos os seus criativos ou se aprofunde no desempenho de cenas e elementos individuais para obter o máximo de insights baseados em dados.

<Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-etl-reporting">O ETL da otimização de criativos</Anchor> permite que seus analistas de dados acessem todas as informações necessárias para avaliar sua performance criativa, enviando relatórios automaticamente para seu armazenamento em nuvem e garantindo um carregamento programático eficiente em seus sistemas de BI.

Com a otimização de criativos, você pode:

* Aprender rapidamente quais criativos, cenas e elementos funcionam e quais não funcionam
* Otimizar seus assets com base em dados
* Aumentar a performance e o ROI do criativo
* Produzir os criativos de maior sucesso
* Identificar o declínio da eficácia dos criativos ao longo do tempo/canais/campanhas e tomar decisões informadas de otimização
* E mais

<div id="creative-assets" />

## Assets criativos

Essa seção fornece informações sobre os assets criativos que mensuramos.

<div id="supported-asset-types" />

<Accordion title="Tipos de assets compatíveis">

Os tipos de assets compatíveis incluem:

* Vídeos
* Imagens
* Anúncios em carrossel (apenas Meta)
* HTML (incluindo Playable)
* Texto

<div id="notes" />

> 📘 **Observações**
>
> * Os assets que podem ser visualizados no dashboard incluem imagens, vídeos e texto.
> * O recurso "semelhança criativa" ainda não está disponível para
>   anúncios de carrossel.

</Accordion>

<div id="matching-creatives" />

<Accordion title="Criativos correspondentes">

A solução de otimização de criativos tem a capacidade única de identificar quais assets são iguais em múltiplos canais e campanhas, independentemente de convenções de nomenclatura ou IDs. Isso é feito por algoritmos de IA e visão computacional que combinam propriedades como contexto visual, som e pixeis. Além disso:

* Os criativos correspondentes devem ter a mesma proporção, como retrato, paisagem ou quadrado.
* Vídeos com durações diferentes são considerados criativos diferentes.

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="Mensurando criativos com vários assets">

**Como a otimização de criativos avalia o criativo de um anúncio com múltiplos assets?**

Meta Advantage + (criativos dinâmicos) e campanhas universais para apps (UAC) do Google podem incluir criativos de anúncios com vários assets. No entanto, a AppsFlyer não detalha os dados no nível do asset. O Meta Ads fornece dados até o **nível do anúncio** e o Google fornece dados apenas até o **nível do grupo de anúncios**. Para esses tipos de criativos de anúncios, a AppsFlyer usa modelagem de dados para dividir os dados de performance entre os assets.

<div id="example" />

> 📄 **Exemplo**
>
> Vamos supor que você tenha um criativo de anúncio no Facebook com vários assets. O Facebook atribui um total de 100 instalações, divididas em assets da seguinte forma: **o asset A** tem 60 instalações e **o asset B** tem 40 instalações, conforme mensurado pelo Facebook. Na AppsFlyer, vamos supor que o anúncio seja atribuído com 50 instalações (devido a diferenças de atribuição inerentes entre a AppsFlyer e <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor>). Para permitir a análise em nível de asset, a AppsFlyer distribui os dados de performance (impressões, cliques, instalações e custo) com base na proporção de métricas de assets em relação ao total, conforme ilustrado abaixo.
>
> Portanto, **para o asset A, temos:**
> 60 instalações divididas por 60+40 (instalações totais atribuídas pelo Facebook) = 0,6
> Então multiplicamos 0,6 por 50 (número de instalações atribuídas pela AppsFlyer) = 30 instalações
>
> **Para o asset B, temos:**
> 40 instalações divididas por 60+40 (instalações totais atribuídas pelo Facebook) = 0,4
> Então multiplicamos 0,4 por 50 (número de instalações atribuídas pela AppsFlyer) = 20 instalações
>
> Assim, o criativo do anúncio é atribuído com um total de 50 instalações pela AppsFlyer, mas o volume de instalações por asset é mantido, o que significa que **o asset A** gerou mais instalações do que **o asset B**, em nosso exemplo.
> As métricas do fundo do funil, como receita e ROAS, também são calculadas com base nessa proporção.
>
> <Image align="center" alt="Creative_data_example_en-us.png" src="https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png" />

</Accordion>

<div id="using-the-dashboard" />

## Como usar o dashboard

Essa seção fornece um resumo completo do dashboard principal: como usar filtros, as várias métricas e dimensões disponíveis para obter os dados criativos que você deseja e como salvar e compartilhar a visualização do dashboard.

<Image align="center" alt="Filter bar and metrics -Default view.jpg" src="https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg" />

<div id="filter-bar" />

<Accordion title="Barra de filtro">

A primeira etapa na configuração do seu dashboard é selecionar as opções de filtros. Todos os filtros se aplicam ao dashboard de visão geral e de descoberta.

<Image align="center" alt="filter_bar.jpg" src="https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg" />

**Para selecionar filtros do dashboard**:

1. Selecione seu:
   * **Aplicação**
   * **Intervalo de datas:** Um criativo é exibido no dashboard quando há dados de conversão para o criativo durante o intervalo de datas selecionado. Os dados são de LTV, o que significa que as métricas exibidas são para conversões que ocorreram a partir de criativos durante o intervalo de datas selecionado.
   * [Tipo de visualização](#view-type)
2. Clique no ícone + para adicionar qualquer uma das seguintes opções de filtros, entre elas:
   * **Dimensões e métricas**
   * **Filtros numéricos**, disponíveis para todas as métricas com as seguintes opções:
     * Maior que - exibe criativos com valores maiores ou iguais à métrica escolhida
     * Menor que - exibe criativos com valores abaixo da métrica escolhida

Além das [métricas e dimensões padrão](/docs/creative-optimization-guide#standard-metrics-and-dimensions), o dashboard de otimização de criativos oferece várias métricas e dimensões exclusivas.

</Accordion>

<div id="view-type" />

<Accordion title="Tipo de visualização">

Os dados criativos nos dashboards são apresentados em 3 tipos de visualização separadas: unificada, aquisição de usuários (UA) e retargeting:

* **Unificada** - exibe todos os dados criativos de UA e anúncios/conjuntos de anúncios de retargeting.
* **Aquisição de usuários** - exibe dados de criativos associados apenas a anúncios/conjuntos de anúncios de UA.
* **Retargeting** - exibe dados de criativos associados apenas a anúncios/conjuntos de anúncios de retargeting. Os dados de custos também estão disponíveis aqui.

<Image align="center" alt="View_types.jpg" src="https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg" />

</Accordion>

<div id="creative-optimization-roi360" />

<Accordion title="Otimização de criativos + ROI360">

Com uma assinatura do ROI360, os dados de custo exibidos nos dashboards da otimização de criativos são obtidos com o ROI360, que consolida e processa dados de custo de ad networks parceiras, além de incluir métricas adicionais baseadas em custo. Sem essa assinatura, esses dados são obtidos dos relatórios dos seus parceiros de mídia integrados. Recomendamos que você use o ROI360 para acessar dados de custo mais completos. A tabela abaixo explica o que muda quando você usa o ROI360 em conjunto com a otimização de criativos.

| Com o ROI360 | Sem o ROI360 |
| --- | --- |
| <ul><li><Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-cost-and-revenue-data#ferramentas-de-custo">Possui dados conforme relatado por qualquer método do ROI360</Anchor>.</li><li><Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-cost-and-revenue-data#ferramentas-de-custo">Possui todas as capacidades de relatórios de custos do ROI360</Anchor>.</li><li>O Creative ETL inclui dados de custo (requer uma assinatura avançada do ROI360).</li></ul> | <ul><li>Os dados de custo, conforme relatados diretamente por seus parceiros integrados, estão limitados aos dashboards de Otimização de criativos, não ao Creative ETL.</li></ul> |

/docs/roi360-guide-cost-and-revenue-data

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="Métricas e dimensões padrão">

As métricas/dimensões padrão disponíveis no dashboard incluem:

| Métrica/dimensão | Descrição |
| --- | --- |
| Impressões | Número de visualizações do criativo |
| Cliques | Número de cliques em anúncios que possuem esse criativo |
| Conversões | <ul><li>Instalações - Número de usuários únicos que instalam o aplicativo</li><li>Reengajamentos - Número de usuários únicos que abrem o aplicativo após interagir com uma campanha de retargeting</li><li>Reatribuições - Número de usuários únicos que reinstalam o aplicativo depois de interagir com uma campanha de retargeting</li></ul> |
| Custo | Custo dos criativos |
| CTR (taxa de cliques) | Taxa (%) de usuários que clicaram em um anúncio em relação ao total de visualizações. Fórmula: Cliques/impressões x 100 |
| CVR (taxa de conversão) | Taxa (%) de usuários que completam a jornada desde o clique até a atribuição (instalações, reengajamentos e reatribuições). Fórmula: Conversões/cliques x 100 |
| IPM (instalações por mil) | Instalações por mil. Número de instalações a cada 1.000 impressões de usuários (visualização de anúncios) |
| eCPI (Custo efetivo por instalação) | eCPI exclui instalações orgânicas e calcula o custo por <Anchor target="_blank" href="/marketers/pt/docs/about-organic-and-non-organic-installs">atribuições não orgânicas</Anchor> (instalações, reengajamentos e reatribuições). Fórmula: Custo total disponível / todas as atribuições não orgânicas. |
| CPM (custo por mil) | Custo de 1.000 impressões de anúncios. Fórmula: Gasto total com criativos / número de impressões) x 1.000 |
| Plataforma | Refere-se ao sistema operacional (por exemplo, Android) com o Android) |
| Canal | Segmentação de tráfego entre fontes de mídia  <br />(por exemplo: YouTube para Google, Instagram para Meta ads, etc.) YouTube para Google, Instagram para anúncios da Meta etc.) YouTube para Google, Instagram para anúncios da Meta etc.) |
| Geografia | País/localização |
| IDs | <ul><li>Criativo</li><li>Anúncio</li><li>Conjunto de anúncios</li><li>Campanha</li></ul> |
| Agência | Exibe dados criativos de agências selecionadas |
| Receita (D0, D1, D3, D7, D14, D30, D60, D90) | Receita de cohort relatada à AppsFlyer |
| ROAS (D0, D1, D3, D7, D14, D30, D60, D90) | Retorno do investimento em anúncios por cohort (%). Calcula a receita gerada por unidade de gasto com anúncio. Fórmula: Receita / custo x 100 |
| Usuários únicos (D0, D1, D3, D7, D14, D30, D60, D90) | Usuários únicos de um cohort que interagiram com seu aplicativo até o dia especificado a partir da instalação |
| Retenção (D0, D1, D3, D7, D14, D30, D60, D90) | Taxa em cohort (%) de usuários que continuam usando seu serviço ou produto durante um período predeterminado<br /><br />**Atenção:** os dados estão alinhados com o dashboard de cohort da AppsFlyer. |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="Métricas e dimensões exclusivas">

As métricas/dimensões exclusivas disponíveis no dashboard incluem:

| Métrica/dimensão | Descrição |
| --- | --- |
| Exibições | Exibe o número de campanhas/conjuntos de anúncios/anúncios em que um criativo específico é exibido nos diferentes canais |
| [Métricas de parceiros](/docs/creative-optimization-guide#partner-dimensions-and-metrics) | Dados provenientes diretamente de parceiros integrados (não de dados de atribuição da AppsFlyer) |
| Semelhanças entre criativos | Agrupa criativos que são quase idênticos (mas com pequenas diferenças) e permite comparar sua performance para determinar a versão mais bem-sucedida. Por exemplo, imagens semelhantes com orientações diferentes (retrato vs. paisagem) seriam agrupadas, assim como vídeos semelhantes em idiomas diferentes. Essa dimensão só se aplica a imagens e vídeos. |
| Creative age | Exibe o número de dias que um criativo foi executado como parte de uma campanha. Sua idade é calculada a partir da primeira impressão, clique ou instalação recebida pela AppsFlyer (o timestamp de "primeira visualização" do criativo) e pode variar de acordo com as dimensões selecionadas. Por exemplo, se um criativo for inserido em uma campanha em um dia específico, depois for adicionado a outra campanha em um dia diferente, e ambas as campanhas e dimensões de idade do criativo forem adicionadas ao filtro, a idade final será igual à do primeiro upload.<br /><br />**Atenção:** para criativos em campanhas que começaram a ser executadas antes de serem ingeridas no painel do Creative, a AppsFlyer exibe os dados, que incluem até 90 dias antes da ingestão. Por exemplo, se um criativo esteve em execução por mais de 90 dias antes da ingestão, a “idade do criativo” exibida será inicialmente 90, mas depois continuará a crescer cumulativamente a cada dia. |
| Criativo visto pela primeira vez | Exibe criativos de acordo com a primeira vez em que os dados de performance (que costumam ser de impressão) foram recebidos. O cálculo da "idade do criativo" é acionado a partir dessa data. |
| Duration | Duração em segundos de um asset criativo (aplicável a vídeos) |
| Resolução | Tamanho de um asset criativo em pixeis (aplicável a imagens e vídeos)<br /><br />**Atenção:** exibimos a resolução real que foi fornecida aos usuários pelos seus parceiros de mídia integrados. Ela pode ser uma resolução diferente daquela que foi originalmente enviada para eles. |
| Orientação | Orientação de um asset criativo, como retrato, quadrado ou paisagem |
| Mês | Detalhamento da performance por mês |
| Week | Detalhamento da performance por semana |
| Cartões finais | Refere-se a anúncios estáticos que podem ser exibidos no final dos anúncios em vídeo e que geralmente contêm informações básicas sobre o aplicativo promovido. A capacidade de agrupar criativos por end cards fornece insights adicionais para a otimização de criativos. Por exemplo, você pode comparar a mesma tela final com diferentes vídeos para identificar a melhor combinação. Você pode visualizar criativos pelos seguintes dados de end card:<ul><li>Nome do cartão final</li><li>ID do cartão final</li><li>Duração do cartão final</li><li>Resolução do cartão final</li><li>End card orientation</li><li>Tipo do cartão final</li></ul>**Observações:**<ul><li>Os dados do end card estão disponíveis para os seguintes parceiros: AppLovin, IronSource, Moloco, UnityAds, Snapchat e YouAppi.<ul><li>Atualmente, somente o ironSource, Unity Ads e Snap oferecem nomes exclusivos de end cards. Para todos os outros parceiros, esses nomes serão idênticos aos nomes dos criativos nos dashboards.</li></ul></li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="Métricas personalizadas">

Crie métricas personalizadas para mensurar a performance dos seus criativos exatamente como você desejar.

**Para criar uma métrica personalizada:**

1. Clique no menu suspenso no canto superior direito do dashboard e selecione **Métricas personalizadas**  
   **![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)**
2. **Preencha o formulário:**
   * **Nome** - Insira um nome de métrica exclusivo
   * **Tipo** - Selecione um tipo Numérico, Porcentagem ou Moeda
   * **Descrição** - Insira uma descrição (opcional)
   * **Fórmula métrica** – Crie uma fórmula clicando em **+ Adicionar fórmula**.    
     * *Métricas* incluem impressões, cliques, instalações, CTR, CVR, CPM, IPM, custo, eCPI, reatribuições, reengajamentos, receita, ROAS, retenção, usuários únicos, aparições, métricas de parceiros
     * Combine com vários *Operadores, Números* e/ou *Eventos in-app*
     * Eventos in-app específicos são selecionados no menu suspenso. Para cada evento in-app, você pode adicionar qualquer métrica por evento separadamente para obter insights altamente específicos, por exemplo, receita de af\_purchase + contagem de af\_login.  
       <Image align="center" alt="" src="https://files.readme.io/2b8bdaa8c1fb47c7e78b59e7e24f37aa3248800c7a3ed5cc821c2e11622a93fe-30129836915729.png" width="892px" />
3. Clique em **Salvar**.  
   Sua nova métrica personalizada será criada e exibida na barra de filtros e nas configurações da tabela com "Personalizada" ao lado.

**Atenção:**

* Você pode criar até 30 métricas personalizadas por conta.
* Você pode passar o mouse sobre a tag "Personalizada" nas configurações da tabela para ver a descrição.

Métricas personalizadas também podem ser editadas ou excluídas.

**Para editar:**

1. Clique no menu suspenso **Editar métrica personalizada existente** (no formulário **Métricas personalizadas** ) e selecione a que deseja editar.  
   <Image align="center" alt="" src="https://files.readme.io/b792e08152482bed11ea8ce5ea5795c3df961c257d07397b5b4d787f40a8ea2e-30129836916369.png" width="892px" />
2. Faça as alterações desejadas e clique em **Salvar**.  
   Faça as alterações desejadas e clique em **Salvar**  
   **Atenção:** você também pode clicar em Salvar como /strong>para salvá-la como uma nova métrica personalizada.

**Para deletar:**

* **Para excluir:** depois de selecionar a métrica personalizada que deseja excluir no menu suspenso, clique no ícone excluir.  
  <Image align="center" alt="" src="https://files.readme.io/8370c5bfec23ef2ac15e266e98be357e496aef51fa14ca5b4c853b0b38910a10-30129810517393.png" width="546px" />

</Accordion>

<div id="partner-dimensions-and-metrics" />

<Accordion title="Dimensões e métricas do parceiro">

Métricas de parceiros são dados provenientes diretamente de parceiros de mídia integrados (e não de dados de atribuição da AppsFlyer). As métricas variam de acordo com o parceiro e podem incluir impressões, cliques, conversões, custo e % de reprodução do vídeo. As métricas podem ser selecionadas nos filtros, visualizadas em todo o dashboard e adicionadas à tabela.

A tabela a seguir lista todos os parceiros de otimização de criativos, com a granularidade de dados disponível para cada um:

* Dimensões
* Métricas (conforme reportado pelas ad networks)
* Funcionalidades compatíveis e suas características

Baixar arquivo: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=csv">CSV</Anchor>, <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=xlsx">XLS</Anchor>

<div id="to-set-up-partner-metrics" />

#### **Para configurar métricas de parceiros:**

Basta adicionar uma nova integração de parceiro e as métricas dos parceiros compatíveis serão automaticamente inseridas na otimização de criativos (o Unity Ads é uma exceção e segue **instruções específicas**). Depois de configuradas, essas métricas são exibidas com a palavra "Parceiro" ao lado.

<Image align="center" alt="partner metrics image.jpg" src="https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg" />

**Instruções e considerações:**

<div id="applovin-metrics" />

<Accordion title="Métricas do AppLovin">

**Atenção:**

* Devido a uma restrição na API AppLovin, apenas até 45 dias de dados históricos estão disponíveis. Normalmente, a AppsFlyer pode exibir até 90 dias de dados históricos, no entanto, devido à restrição do AppLovin, apenas 45 dias de dados do AppLovin estão disponíveis.
* Os dados criativos da AppsFlyer estão alinhados com o relatório probabilístico AppLovin (não com o relatório faturável).

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Métricas do Google Ads">

**Atenção:**

* Haverá diferenças no número de instalações relatadas pelo Google Ads e pela AppsFlyer devido a diferentes lógicas de atribuição.
* Haverá diferenças entre o Google e a AppsFlyer para todas as métricas. Isso se deve ao fato de que as métricas dos parceiros do Google são baseadas no relatório de visualização de assets do Google, enquanto os dados da AppsFlyer estão alinhados à visualização do grupo de anúncios do Google. Esses relatórios não estão alinhados entre si em termos de desempenho. Por exemplo, o número total de impressões de recursos em um grupo de anúncios específico não será igual ao total de impressões relatado pelo grupo de anúncios.
* Existem diferenças entre o produto de otimização de criativos e a plataforma Google AdWords. Ao comparar a visualização de assets entre a plataforma Google e a AppsFlyer pode haver pequenas diferenças devido a: 1. Fusos horários (a otimização de criativos está em UTC+0). 2. Taxa de atualização dos dados (diferença entre a ocorrência do evento e a disponibilidade dos dados na plataforma).

</Accordion>

<div id="meta-ads" />

<Accordion title="Métricas do Meta Ads">

**Atenção:**

* Haverá diferenças no número de instalações relatadas pelo Meta Ads e pela AppsFlyer devido a diferentes lógicas de atribuição.
* O Meta não relata instalações no nível de asset para iOS, portanto não está disponível na otimização de criativos.

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Métricas do Unity Ads">

**Para obter métricas de parceiros do Unity Ads:**

1. No dashboard de otimização de criativos, clique no ícone  ⋮  no canto superior direito para acessar as **Integrações**.  
   <Image align="center" alt="icon for creative integrations.jpg" src="https://files.readme.io/5af3cc395743cf305a9d19dca41dc53c7cbf82e18434d2eb335c9e58a4245456-21366803702033.jpg" />
2. Clique em **+ Nova integração**.
3. Selecione **Unity Ads** na lista suspensa **Parceiro**.  
   <Image align="center" alt="New integration - Unity Ads.jpg" src="https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg" />
4. Insira o Unity **Key ID**, **Secret Key** e **Organization Core ID** para a integração (veja as instruções de <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-partner-integrations#unity-ads">integração de parceiros</Anchor> acima para saber como obtê-los).
5. Em **Métricas do parceiro** , insira a **chave de API** do Unity e o **Organization ID**. Você pode obter essas credenciais seguindo as instruções abaixo. **Atenção:** se você tiver uma integração de custo ROI360 com Unity Ads, também poderá obter as credenciais de lá.
   * **Para obter a chave da API:**
     1. Faça login na sua plataforma Unity Gaming Services.
     2. Clique em **Products** no menu lateral e, sem seguida, clique em **Grow**.  
        <Image align="center" alt="ID da organização do Unity, etapa 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" />
     3. Clique em **Unity Ads User Acquisition**.  
        <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="312px" />
     4. Clique em **API management**.  
        <Image align="center" alt="Unity-from API mngmt, obtenha a chave API w arrow.jpg" src="https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg" />
     5. Copie a chave da API
   * **Para obter o Organization ID:**
     1. Na Unity Ads, clique em **Products** no menu lateral e, em seguida, clique em **Grow**.  
        <Image align="center" alt="ID da organização do Unity, etapa 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="583px" />
     2. Clique em **Unity Ads User Acquisition**.
     3. <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="336px" />
     4. Clique em **Configurações**.   
        <Image align="center" alt="Obtenha instruções do ID principal da organização 2 arrows.jpg" src="https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg" />
     5. Copie o **Organization ID**

<div id="note" />

> 📘 **Observação:**
>
> Recomendamos que você insira as credenciais das métricas do parceiro ao configurar uma nova integração. No entanto, isso não é obrigatório. Você pode salvar a integração e adicionar as credenciais posteriormente. Mas observe que extraímos 90 dias de dados do parceiro a partir do momento em que a integração do parceiro é criada, portanto, não inserir as credenciais da métrica do parceiro pode resultar na perda de dados.

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="Salvar e compartilhar visualizações">

Depois de selecionar seus filtros, você pode salvar suas configurações para acessar rapidamente as informações que você deseja ver – portanto, não há necessidade de selecionar novamente os filtros sempre que fizer login. A visualização salva se aplica a ambos os dashboards de descoberta e de visão geral da solução de otimização de criativos. Você pode salvar uma visualização do dashboard como privada ou compartilhada. As visualizações compartilhadas são visíveis para outros usuários da conta. Além disso, você pode compartilhar visualizações do dashboard com outras pessoas por meio da URL de compartilhamento.

**Atenção:** Um ponto indicador laranja aparece ao lado da visualização atual se você fez alterações nas configurações do dashboard sem salvar.

<div id="save-private-dashboard-view" />

#### **Salvar visualização do dashboard em modo privado**

**Para salvar uma visualização em modo privado (visível apenas para você):**

1. No topo do dashboard que está sendo exibido, clique no ícone de dropdown, certifique-se de que o menu tenha o ícone privado selecionado e, em seguida, clique **+ Salvar como novo dashboard privado.**  
   <Image align="center" alt="" src="https://files.readme.io/c1ed2ac6917fa105641f054623ad87a562f4b80042379301c8736bffaa57a22e-25381406386065.png" />
2. Digite um nome para o dashboard e clique **Salvar**.
3. Use os ícones do menu para editar e excluir visualizações, alterar as configurações de compartilhamento de privado para compartilhado ou marcar uma visualização como favorita, definindo-a como a visualização padrão a ser exibida ao fazer login.

<div id="save-shared-dashboard-view" />

#### **Salvar visualização do dashboard em modo compartilhado**

**Para salvar uma visualização em modo compartilhado (visível para outros usuários da conta):**

1. No topo do dashboard que está sendo exibido, clique no ícone de dropdown, certifique-se de que o menu tenha o ícone compartilhado selecionado e, em seguida, clique **+ Salvar como novo dashboard compartilhado.**  
   **![](https://files.readme.io/d4a7f206d49ddea230883ee6e119caab119164fa3bee9d0c3f02d487c9cf8a36-25381406390033.png)**
2. Digite um nome para o dashboard e clique **Salvar**.  
   A visualização está salva e aparece na lista de visualizações do dashboard para todos os outros usuários da conta.
3. Use os ícones do menu para editar e excluir visualizações, alterar as configurações de compartilhamento de compartilhado para privado ou marcar uma visualização como favorita, definindo-a como a visualização padrão a ser exibida ao fazer login.

<div id="share-view-url" />

#### **Compartilhar URL de visualização**

**Para compartilhar uma URL de visualização com outro usuário da conta:**

* Clique no ícone no canto superior direito do dashboard para copiar a URL da página e, em seguida, compartilhe-a.  
  Clique no ícone no canto superior direito do dashboard para copiar a URL da página e compartilhe-a.  
  <Image align="center" alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />
  **Atenção:** URLs de visualização podem ser compartilhadas mesmo para dashboards privados.Clique no ícone no canto superior direito do dashboard para copiar a URL da página e compartilhe-a.  
  <Image align="center" alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />
  **Atenção:** URLs de visualização podem ser compartilhadas mesmo para dashboards privados. Quando a URL do dashboard privado é aberta, o nome do relatório que é exibido é "Relatório Não Salvo".

</Accordion>

<div id="custom-tags" />

## Tags personalizadas

Agrupe e analise seus criativos com base nas tags que você carrega ou nos identificadores exclusivos armazenados nos nomes dos arquivos. Essa seção descreve as diferentes maneiras de criar tags personalizadas, que aparecem como dimensões que você pode selecionar nos filtros e visualizar nos dashboards.

<div id="custom-dimensions" />

<Accordion title="Tags personalizadas via CSV">

Você pode adicionar dimensões personalizadas ao dashboard. Essas dimensões personalizadas e os criativos marcados são adicionados por meio de arquivo CSV e alinhados com os criativos atuais usados nas diversas campanhas. Use esse recurso para visualizar, organizar, classificar e filtrar criativos por quaisquer dimensões e tags personalizadas que você desejar.

<div id="create-and-manage-custom-dimensions" />

<Accordion title="Crie e gerencie dimensões personalizadas">

O processo de criação e gerenciamento de dimensões personalizadas inclui as três ações a seguir:

1. Fazer download de um arquivo CSV do dashboard da otimização de criativos que contém os criativos atuais.
2. Criar novas dimensões ou alterar dimensões e tags atuais. Cada heading de coluna no arquivo CSV é o nome da dimensão personalizada (por exemplo: “Color”). Todos os criativos nessa coluna serão marcados com a dimensão personalizada e exibidos sob essa tag no dashboard. Você pode adicionar ou alterar qualquer uma das dimensões ou tags personalizadas por meio do arquivo CSV. **Atenção:** o novo CSV não precisa incluir tags e dimensões personalizadas criadas anteriormente; apenas aquelas que você deseja editar ou adicionar.
3. Fazer upload do arquivo CSV atualizado no dashboard da otimização de criativos. Os dados estarão disponíveis em cerca de 30 minutos.

Os procedimentos para download e upload do arquivo CSV estão descritos abaixo:

**Para fazer download de um arquivo CSV com criativos atuais:**

1. Clique no<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />menu no canto superior direito.  
   <Image align="center" alt="Main menu highlighted.jpg" src="https://files.readme.io/be14a3ab1a9aba6dc20816e53ad692b1697d15a185053cf523d2ae8451842350-21367268248465.jpg" />
2. Clique em **Download do arquivo de tags personalizadas**
3. Selecione quais criativos você deseja incluir no arquivo (todos os criativos ou apenas os criativos exibidos atualmente, excluindo os criativos filtrados).
4. Clique em **Baixar**.

Faça as adições ou alterações desejadas no arquivo, salve-o e envie-o novamente no dashboard.

**Para fazer o upload do arquivo CSV para o dashboard de otimização de criativos.**

1. Clique no<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />menu no canto superior direito.
2. Clique em **Enviar arquivo de tags personalizadas**.
3. Selecione um arquivo.  
   Certifique-se de estar ciente de todas as diferentes [considerações e limitações](/docs/creative-optimization-guide#traits-and-limitations) ao enviar um arquivo CSV.
4. Clique em **Fazer upload para o dashboard**.

Os dados estarão disponíveis em cerca de 30 minutos.

</Accordion>

<div id="example-csv" />

<Accordion title="Exemplo de CSV">

Aqui está um exemplo de arquivo CSV de dimensões personalizadas (que você baixa a partir do dashboard). Cada heading de coluna (na linha 1) é o nome de uma dimensão personalizada (por exemplo: “Theme” ou "Variant"). Você pode incluir dimensões adicionais ou alterar as existentes. Você também pode adicionar ou alterar as tags (por exemplo: “3 Moves" ou "DarkPalette").

<Image align="center" alt="Screen_Shot_2022-08-08_at_16.25.23.png" src="https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações da dimensão personalizada">

* As dimensões personalizadas aparecem com uma tag “Personalizada” nos filtros e na tabela.

<Image align="center" alt="Custom_tag.png" src="https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png" width="477px" />

* Você pode adicionar até 15 dimensões personalizadas.
* O tamanho do arquivo de upload é limitado a 1 MB.
* As dimensões e nomes de tags existentes podem ser alterados atualizando o arquivo CSV e fazendo seu upload novamente. **Atenção:** Você pode atualizar ou adicionar apenas uma dimensão por upload de arquivo.
* As dimensões personalizadas definidas no arquivo CSV se aplicam no nível da conta, ou seja, para todos os aplicativos e usuários.
* Cada criativo pode ter uma tag por dimensão. Por exemplo, se "Color" for a dimensão personalizada, a tag poderá ter apenas uma cor, como vermelho.
* Ao criar ou editar as dimensões personalizadas, certifique-se de não alterar o creative\_id para evitar substituições e discrepâncias.

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="Tags de convenção de nomes">

Você pode criar tags personalizadas com base nas convenções de nomenclatura de seus assets criativos. Essas tags personalizadas aparecerão como dimensões que você pode selecionar nos filtros e visualizar em todo o dashboard.

Isso é útil para equipes de marketing e de criação cujos criativos são nomeados intencionalmente, com identificadores exclusivos incorporados aos nomes. Esses criativos podem ser marcados automaticamente pelos identificadores integrados e agrupados para fins de análise e otimização.

<div id="create-and-manage-name-convention-tags" />

<Accordion title="Criar e editar tags de convenção de nomes">

**Para criar tags de convenção de nomes:**

1. Clique no ícone  ⋮  no canto superior direito e selecione **Tags de convenção de nomes**.  
   A janela **Gerenciar tags de convenção de nomes** é exibida.  
   <Image align="center" alt="Name convention tags main window.jpg" src="https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg" width="795px" />
2. Em **Criar novo tipo de convenção de nome**, insira os detalhes:
   * **Nome** - Dê ao novo tipo de convenção um nome único.
   * **Separador** - O caractere que separa cada seção. Por exemplo, em um criativo chamado “enUS\_bluegalaxy\_launch.mp4”, cada seção é separada por “\_”. “\_” é o separador.
   * **Número de seções** – por exemplo, em um criativo chamado “enUS\_bluegalaxy\_launch.mp4”, há 3 seções separadas por “\_”.  
     **Atenção:** o tipo de arquivo não está incluído nas tags.
   * **Aplicativo** (opcional) – você pode incluir todos os aplicativos ou limitar tags apenas a criativos associados a determinados aplicativos.
   * **Fonte de mídia** (opcional): você pode incluir todas as fontes de mídia ou limitar tags a criativos executados apenas em determinadas fontes de mídia.
3. Adicione os detalhes da tag personalizada:
   * **Número da seção** - Selecione o número da seção da tag que você deseja criar.
   * **Nome da tag personalizada** - Crie um nome clicando em **+ Criar nova tag personalizada** ou selecione um nome existente.
   * **Formato** - selecione como as tags devem aparecer em toda a tabela/dashboard: em maiúsculas, minúsculas ou original (como ela aparece originalmente no nome do criativo).  
     Você pode inserir tags personalizadas adicionais clicando em **+ Adicionar tag personalizada**.
4. Antes de salvar, você pode visualizar como suas tags personalizadas serão aplicadas aos criativos clicando em **Baixar arquivo de visualização** (opcional). Isso fará o download de um arquivo com todos os criativos que correspondem ao tipo de convenção de nomes que você está criando, com todos eles marcados de acordo com as novas tags.
5. Clique em **Salvar**.  
   As tags serão aplicadas e estarão disponíveis no dashboard em algumas horas.

**Para editar tags de convenção de nomes:**

1. Clique no ícone  ⋮  no canto superior direito e selecione **Tags de convenção de nomes**.
2. Clique no menu suspenso **Editar tipo de convenção de nome** para fazer sua seleção.
3. Faça as alterações necessárias e clique em **Salvar**.

**Para excluir um tipo de convenção de nome:**

1. Clique no menu suspenso **Editar tipo de convenção de nome** e selecione a que deseja excluir.
2. Clique em <Image alt="ícone de excluir.jpg" src="https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg" width="19px" /> que aparece quando você passa o mouse à direita da sua seleção.  
   **Atenção:** as tags personalizadas associadas não serão mais aplicadas aos seus criativos. Pode levar algumas horas para que a alteração entre em vigor.

<div id="name-tag-traits-and-limitations" />

<Accordion title="Características e limitações da tag de nome">

* Você pode criar até 10 tipos de convenção de nomes diferentes (e as tags personalizadas associadas).
* Se tags personalizadas que foram enviadas por meio de arquivo CSV entrarem em conflito com as tags de convenção de nomes que você criou, as tags CSV carregadas terão precedência e somente essas tags serão aplicadas.

</Accordion>

</Accordion>

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Fonte de dados | Todos os dados de performance nos dashboards da otimização de criativos (além das métricas do parceiro) vêm do modelo de atribuição da AppsFlyer. **Atenção:** Lembre-se que existem diferenças inerentes nos modelos de atribuição usados por diversas plataformas de publicidade e players do ecossistema mobile, o que pode explicar as discrepâncias entre os seus relatórios. |
| Múltiplos assets | Para criativos que incluem vários assets, apenas um asset é exibido (geralmente o vídeo, quando aplicável). |
| Atualização dos dados | Os dashboards de visão geral e Discovery da otimização de criativos são atualizados uma vez por dia às 10:00 UTC (atualizando os dados de criativos dos últimos 90 dias).<br /><br />Dependendo do seu fuso horário, a atualização diária ocorre às:<ul><li>Nova York: 5:00 AM EST / 6:00 AM EDT</li><li>Berlim: 11:00 AM CET / 12:00 PM CEST</li><li>Xangai: 6:00 PM CST</li></ul>Para outros locais, converta 10:00 UTC para o seu fuso horário local.<br /><br />**Atenção:** Os dados em otimização de criativos são atualizados uma vez por dia, enquanto o Dashboard Overview principal da AppsFlyer é atualizado em tempo real, o que pode causar discrepâncias temporárias. |
| Moeda | Todas as métricas monetárias na otimização de criativos estão em USD. |

</Accordion>

<div data-zendesk-anchors="overview=sobre-a-otimiza%C3%A7%C3%A3o-de-criativos 01H7SZ8R9ZWZ81WHV26P00YAYP=sobre-a-otimiza%C3%A7%C3%A3o-de-criativos creative-assets=assets-criativos 01H7SZ8RA14Q5D32EY5J0WMVYA=assets-criativos 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types h_01HMXES26N1X3KAFRKKCC9NFXW=observa%C3%A7%C3%B5es 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=exemplo creative-dashboard=como-usar-o-dashboard 01H7SZ8RA1JX2TCQHB5XW21EK8=como-usar-o-dashboard 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01HJDKZWTQVTPSJXP2HWSMD8W6=creative-optimization-roi360 h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-dimensions-and-metrics partner-table=para-configurar-m%C3%A9tricas-de-parceiros 01H7SZ8RA2VJ9466WSMN3WHR90=para-configurar-m%C3%A9tricas-de-parceiros 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=observa%C3%A7%C3%A3o 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views save-private-dashboard-view=salvar-visualiza%C3%A7%C3%A3o-do-dashboard-em-modo-privado h_01HYT77DSHZ6FE0MSQS83FRGW0=salvar-visualiza%C3%A7%C3%A3o-do-dashboard-em-modo-privado save-shared-dashboard-view=salvar-visualiza%C3%A7%C3%A3o-do-dashboard-em-modo-compartilhado 01HYT89BRYKRG44AT9MZWKZJNY=salvar-visualiza%C3%A7%C3%A3o-do-dashboard-em-modo-compartilhado share-view-url=compartilhar-url-de-visualiza%C3%A7%C3%A3o h_01HYT8GXVJV8Q6GKBDHTTJ1SM2=compartilhar-url-de-visualiza%C3%A7%C3%A3o custom-tags=tags-personalizadas h_01H9J4Z9V9SJBTE63C358FME95=tags-personalizadas h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations additional-information=informa%C3%A7%C3%B5es-adicionais h_01J1VPMV85CT5ZJNN3BW4FCW0D=informa%C3%A7%C3%B5es-adicionais" />
