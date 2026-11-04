---
title: Guia da Fonte Única da Verdade (SSOT) para atribuição no iOS
metadata:
  keywords:
    - iOS
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-08-19T00:30:45Z'
  id: 4410634145425
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/4410634145425
---
> **Num relance**: No âmbito do ambiente iOS 14+, a AppsFlyer reúne dados de vários métodos de correspondência de atribuição, como IDFA, IDFV, SKAN, Apple Search Ads, entre outros, para oferecer uma visão global do desempenho das campanhas de aplicações. Nenhum método de atribuição sozinho oferece uma visão completa do desempenho das aplicações. O desafio é garantir que um utilizador seja contado apenas uma vez, pois o mesmo pode ser atribuído por múltiplos métodos. O mecanismo de Fonte Única da Verdade (SSOT) da AppsFlyer resolve precisamente esse desafio. Os relatórios e métricas SSOT são verdadeiros e precisos, contabilizando o mesmo utilizador uma só vez.

<Embed title="Guia da Fonte Única da Verdade (SSOT) para atribuição no iOS" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

<div id="about-single-source-of-truthtrue-ios-performance-data" />

## Acerca da Fonte Única da Verdade: dados reais de desempenho no iOS

Desde o iOS 14, a AppsFlyer atribui utilizadores iOS utilizando dados de várias fontes, incluindo SKAdNetwork, utilizadores com consentimento ATT, modelização probabilística, insights baseados em incrementalidade e APIs específicas para Apple Search Ads. A falta do IDFA torna praticamente impossível associar os métodos de atribuição sem haver duplicação de dados.

O mecanismo SSOT elimina dados duplicados de instalação e corrige a atribuição de utilizadores inicialmente atribuídos de forma errada. Ou seja, utilizadores atribuídos como orgânicos que deveriam ter sido atribuídos a uma fonte de mídia não orgânica. Assim, o número de instalações atribuídas a uma campanha é ajustado e as métricas relacionadas com custos e receitas, como eCPI, ROI e ROAS, são calculadas corretamente.

De forma simples, o mecanismo SSOT sinaliza as instalações SKAN que também são atribuídas através de outro tipo de correspondência. Esse sinalizador é levado em consideração no cálculo de métricas agregadas para evitar contar o mesmo utilizador em duplicado. Da mesma forma, utiliza-se o sinalizador ao processar dados SKAN em bruto.

Para incluir o sinalizador SSOT nos seus dados, é necessário ativar o SSOT no Conversion Studio.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Ative a Fonte Única da Verdade">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**Para ativar o SSOT:**

1. Antes de começar, considere a política de faturação de <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Fonte Única da Verdade</Anchor> da AppsFlyer.
2. No AppsFlyer, vá a **Definições** > **SKAN Conversion Studio**.
3. Selecione o modo **Personalizado**.
4. Ative a **Fonte Única da Verdade.**
5. Complete as definições conforme necessário.

Consulte o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

</Accordion>

<div id="overview-dashboard-single-source-of-truth-view" />

## Visualização do painel de visão geral da Fonte Única da Verdade

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

A visualização da Fonte Única da Verdade, disponível através do painel de visão geral, oferece uma visão completa das métricas de desempenho não orgânicas. Na visualização:

* As métricas de instalação são precisas.
* As métricas relacionadas a custo e receita, que dependem da métrica de instalação, incluindo eCPI, ARPU e ROAS, são calculadas corretamente.
* Métricas orgânicas ajustadas após a contabilização de instalações mal atribuídas.

Esta secção destaca as diferenças e características únicas da visualização SSOT. Partimos do princípio de que está familiarizado com o painel de visão geral.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Ative a visualização da Fonte Única da Verdade">

Os dados na visualização SSOT ficam disponíveis 3 a 5 dias após a ativação da Fonte Única da Verdade no Conversion Studio.

**Para ativar a visualização da Fonte Única da Verdade**:

1. Antes de começar, verifique se a <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#single-source-of-truth">Fonte Única da Verdade</Anchor> no Conversion Studio está ativada.
2. No AppsFlyer, vá a **Painel** > **Visão Geral.**   
   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Clique em ▼.
4. Selecione Visão Geral Lite.  
   O botão da Fonte Única da Verdade é exibido.  
   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Ative a Fonte Única da Verdade.
6. Ocorre uma das seguintes situações:
   * Exibição das métricas e gráficos do painel.  
     As secções seguintes descrevem os dados disponíveis. Consulte as secções seguintes sobre os dados apresentados.  
     Guarde a visualização SSOT como um novo relatório. Para fazer isso:  
     1. Clique em ▼.
     2. Clique em **+ Guardar novo relatório.**
     3. Introduza um nome para o relatório.
     4. Clique em **Guardar**.
   * Os dados não são exibidos. Considere que pode demorar entre 3 a 5 dias após ativar o SSOT até que os dados sejam exibidos. Aguarde que este período termine e visite novamente o painel de controlo.

Desative o interruptor SSOT a qualquer momento para visualizar dados regulares com as dimensões não disponíveis na visualização SSOT.  Isso permite-lhe explorar os dados em detalhe.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="Considerações sobre a visualização SSOT">

Na visualização SSOT:

* **Valores de conversão (CV) nulos**: Modelados. Utiliza-se aprendizagem automática avançada para modelar um valor nulo atribuído pela AppsFlyer ou SKAN, usando o [sinalizador af\_attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#campo-de-sinalização-de-atribuição). Se atribuídas à SKAN, todas as métricas pós-instalação da SKAN são incluídas no dashboard do SSOT. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data">Saiba mais</Anchor>
* **Redownloads**: Incluídos na métrica de instalações. Não há separação entre instalações e redownloads.
* **Fuso horário**: As instalações e eventos reportados pela AppsFlyer são exibidos em UTC ou no fuso horário local da aplicação, conforme definido na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de definições da aplicação</Anchor>. Para dados reportados pelo SKAN, as instalações e eventos são apresentados em UTC, exceto para os dados do Meta e Google SKAN, nos quais o fuso horário é baseado no configurado nas suas contas Meta e Google, respetivamente.
* **Moeda**: Exibida em USD ou na moeda local da aplicação, conforme definido na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de definições da aplicação</Anchor>.
* **Métricas de receita (D2, D7):** Inclui dados modelados para contabilizar postbacks SKAN incompletos ou ausentes (valores de conversão nulos) Coortes mais longas (D14, D21, D30) são exportadas pelo relatório do SSOT no Data Locker Coortes mais longas (D14, D21, D30) são exportadas pelo relatório do SSOT no Data Locker

<div id="filter-considerations" />

#### Considerações sobre os filtros

Considere o impacto dos filtros na apresentação dos dados e nas métricas, conforme descrito nas tabelas seguintes.

| Filtro | Consideração |
| --- | --- |
| Fonte Única da Verdade | Para visualizar as métricas da Fonte Única da Verdade, verifique se o controlo está ativado. |
| Tipo de visualização | <ul><li>**Aquisição de utilizadores:** A visualização preferida para dados SSOT.</li><li>**Retargeting**: O SKAN não suporta retargeting.</li><li>**Unificado**: Campanhas de instalação contêm dados SSOT. Campanhas de retargeting não são afetadas pelo SSOT.</li></ul> |
| Datas | <ul><li>[Prática recomendada] Escolha um intervalo de datas superior a sete dias que não inclua os três dias mais recentes para obter resultados precisos.</li><li>A primeira data disponível é normalmente 3 dias após a ativação do SSOT. A AppsFlyer determina esta data.</li><li>Exemplo de seleção de data ideal:<ul><li>Se a data atual for 10 de fevereiro e tiver ativado o SSOT a 29 de janeiro. Pode selecionar de 1 a 7 de fevereiro.</li></ul></li><li>Alguns dados (como receitas) podem estar disponíveis apenas 8 dias após a ativação do SSOT.</li><li>As instalações do Google SKAN podem ser reportadas com um atraso de até 45 dias.</li></ul> |
| Filtros de campanhas | Filtros disponíveis para hierarquia de campanhas:<ul><li>Fonte de mídia</li><li>Campanha</li></ul> |
| Principais KPIs | Os principais KPIs disponíveis no painel SSOT permitem ver:<ul><li>Aquisição de utilizadores: Tanto orgânica como não orgânica</li><li>Duplicados SKAN</li><li>Retargeting: Reengajamentos e reatribuições</li><li>Custo</li><li>eCPI</li></ul>Para cada KPI, existe um valor percentual. Este valor mostra a relação do KPI apresentado com o intervalo de datas paralelo anterior. Por exemplo, esta semana em comparação com a semana passada, ou quaisquer dias selecionados no intervalo de datas em comparação com o mesmo número de dias anteriores: Por exemplo, se apresentar um aumento de X% nas instalações, significa que o período paralelo anterior teve X% menos instalações. |
| Gráficos | **Dimensões disponíveis:**<ul><li>Método de atribuição:<ul><li>Modelos AF: Instalações correspondidas por mais de um método, incluindo SKAN. No dashboard, o registo SKAN é desconsiderado para evitar a dupla contagem da mesma instalação. Nos dados brutos SKAN, o af\_attribution\_flag da instalação é definido como verdadeiro.</li><li>Exclusivos SKAN: Instalações correspondidas apenas pelo SKAN e por nenhum outro método. Nos dados brutos SKAN, o af\_attribution\_flag da instalação é definido como falso.</li></ul></li><li>Tipo de atribuição</li><li>Tipo de toque atribuído</li><li>Campanha</li><li>ID da campanha</li><li>Fonte de mídia</li><li>Fonte</li><li>ID da aplicação (para alguns gráficos)</li><li>Geo (as geos SKAN são <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#geo">modeladas</Anchor>)</li><li>Nome do evento na aplicação (referindo-se ao nome de um evento específico dentro da aplicação, conforme configurado no SKAN Conversion Studio).</li></ul>**Métricas:**<br /><br />Conforme descrito nas seções de métricas. |
| Tabela | **Agrupamentos:**<ul><li>[Padrão] A tabela é organizada por origem de mídia e campanha.</li><li>As opções de agrupamento incluem: Fonte de mídia, tipo de atribuição, método de atribuição, campanha, ID da campanha, tipo de interação atribuída, data, fonte, localização geográfica e suas combinações. **Nota**: As áreas SKAN são <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#geo">modeladas</Anchor>.</li><li>Caso selecione um agrupamento cujas dimensões aplicam-se apenas ao tráfego não orgânico, a tabela mostra N/A para a fonte de mídia orgânica.</li></ul>**Métricas:**<br /><br />Conforme descrito nas seções de métricas. |

</Accordion>

<div id="metrics" />

<Accordion title="Métricas">

Métricas disponíveis no painel SSOT:

| Métrica | Descrição e considerações |
| --- | --- |
| Agrupamentos | <ul><li>[Padrão] A tabela é organizada por origem de mídia e campanha.</li><li>As opções de agrupamento incluem: Fonte de mídia, tipo de atribuição, método de atribuição, campanha, ID da campanha, tipo de interação atribuída, data, fonte e suas combinações.</li><li>Caso selecione um agrupamento cujas dimensões aplicam-se apenas ao tráfego não orgânico, a tabela mostra N/A para a fonte de mídia orgânica.</li></ul> |
| **Atribuições SSOT** | **Resumo das instalações, reatribuições e reengajamentos do SSOT nas datas selecionadas.**<ul><li>**Não orgânico: A campanha que atrai o utilizador. O mecanismo SSOT assegura que uma instalação seja contabilizada apenas uma vez.**</li><li>**Métricas orgânicas.**</li></ul> |
| Total | Número de instalações, reatribuições e reengajamentos. |
| Instalações | Número de utilizadores únicos que instalam a aplicação. Calculado como instalações atribuídas pela AppsFlyer em campanhas UA, mais o número de novas instalações e redownloads reportados pela SKAN após remoção de duplicados. |
| Reatribuições | As métricas de retargeting estão disponíveis nos tipos de exibição Unificado e Retargeting. Considere que o SKAN não oferece suporte a retargeting. |
| Reengajamentos | As métricas de retargeting estão disponíveis nos tipos de exibição Unificado e Retargeting. Considere que o SKAN não oferece suporte a retargeting. |
| **Outras métricas** | **Diversas métricas adicionais relacionadas ao SSOT e desempenho publicitário.** |
| Duplicados SKAN | Número de instalações SKAN com af\_attribution\_flag=true |
| Cliques | Dados de cliques e impressões reportados pelas redes publicitárias via API. O mecanismo SSOT não altera as métricas de ponto de contato. |
| Impressões | Dados de cliques e impressões reportados pelas redes publicitárias via API. O mecanismo SSOT não altera as métricas de ponto de contato. |
| Taxa de conversão | Cliques para instalação |
| Custo (€) | Dados de <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">custo de campanha</Anchor> reportados pelas redes de anúncios via API. Exibições de dados para campanhas com ao menos uma instalação. O mecanismo SSOT não influencia o custo total reportado. Afeta apenas as métricas calculadas com base nos números de instalação. |
| eCPI médio ($) | A métrica de custo efetivo por instalação é calculada usando as métricas de instalação da visualização SSOT. Exclui instalações orgânicas. |
| CPM (custo por mil impressões) | Custo por mil (1000 impressões). Fórmula: (Custo/Impressões) * 1000 |
| CPC | Custo por clique. Fórmula: Custo/Clicks |
| Cliques através | Número de atribuições que ocorrem após um utilizador clicar num anúncio (CTA) |
| Click-through rate | Taxa de clique. Fórmula: Clicks/Impressões |
| Visualizações através | <span id="simple-tabpanel-2"></span>Número de atribuições que ocorrem após um utilizador visualizar um anúncio (VTA) |
| Receita (D2) | <ul><li>Inclui dados modelados para contabilizar postbacks SKAN incompletos ou ausentes (valores de conversão nulos)</li></ul>Receita SKAN e Clássica (incluindo receita de anúncios) para a primeira janela de medição SKAN (D2):<ul><li>**Receita SKAN:** Receita de instalações SKAN (onde af\_attribution\_flag=false/null). Baseado nas definições de valor de conversão para <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#revenue-component">receita no Conversion Studio</Anchor>, e no período da janela de medição.</li><li>Receita Clássica: Receita gerada por utilizadores da aplicação após uma instalação atribuída pelo método Clássico e dentro da janela de medição SKAN.</li><li>Para usuários do SKAN 4 no Conversion Studio, estes dados correspondem a dois dias após a instalação. Para quem utiliza SKAN 3 no Conversion Studio, os dados são baseados na janela de atividade do SKAN definida, seja esta superior ou inferior a dois dias.</li><li>**Exemplo**:<ul><li>A janela de atividades é de 24h.</li><li>Os eventos de receita ocorrem no dia seguinte à instalação (Dia X+1), mas dentro da janela de atividade de 24 horas.<ul><li>Para as receitas reportadas tanto pela SKAN quanto pela AF, a contabilização é feita conforme ocorre dentro da janela de 24 horas (mesmo que aconteça num dia diferente do da instalação).</li></ul></li></ul></li></ul>**Dica**: Para aumentar a precisão da receita SKAN:<ul><li>Siga as <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instruções de receita do SKAN.</Anchor></li><li>Usar as recomendações de receita.</li></ul> |
| Receita D7 | <ul><li>Inclui dados modelados para contabilizar postbacks SKAN incompletos ou ausentes (valores de conversão nulos)</li><li>Inclui dados modelados, além da janela de medição do SKAN, até sete dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor></li><li>Necessita de dados de receita D2 para modelagem.</li></ul> |
| ARPU D2 | Receita média por utilizador.<br /><br />Fórmula: Receita/Utilizadores únicos<br /><br />Para usuários do SKAN 4 no Conversion Studio, estes dados correspondem a dois dias após a instalação. Para quem utiliza SKAN 3 no Conversion Studio, os dados são baseados na janela de atividade do SKAN definida, seja esta superior ou inferior a dois dias. |
| ARPU D7 | Inclui dados modelados, além da janela de medição do SKAN, até sete dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor> |
| ROAS D2 | Retorno sobre o investimento em publicidade (%).<br /><br />Fórmula: Receita/Custo * 100<br /><br />Para usuários do SKAN 4 no Conversion Studio, estes dados correspondem a dois dias após a instalação. Para quem utiliza SKAN 3 no Conversion Studio, os dados são baseados na janela de atividade do SKAN definida, seja esta superior ou inferior a dois dias. |
| ROAS d7 | Inclui dados modelados, além da janela de medição do SKAN, até sete dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor> |
| ROI D2 | Retorno sobre o investimento (%).<br /><br />Fórmula: (Receita - Custo)/Custo * 100<br /><br />Para usuários do SKAN 4 no Conversion Studio, estes dados correspondem a dois dias após a instalação. Para quem utiliza SKAN 3 no Conversion Studio, os dados são baseados na janela de atividade do SKAN definida, seja esta superior ou inferior a dois dias. |
| ROI D7 | Inclui dados modelados, além da janela de medição do SKAN, até sete dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor> |
| Lucro Bruto D2 | Lucro após deduzir o custo da campanha.<br /><br />Fórmula: Receita - Custo<br /><br />Para usuários do SKAN 4 no Conversion Studio, estes dados correspondem a dois dias após a instalação. Para quem utiliza SKAN 3 no Conversion Studio, os dados são baseados na janela de atividade do SKAN definida, seja esta superior ou inferior a dois dias. |
| Lucro Bruto D7 | Inclui dados modelados, além da janela de medição do SKAN, até sete dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor> |
| **Métricas de eventos na aplicação** | **Métricas referentes a eventos específicos na aplicação (IAEs)** |
| Utilizadores Únicos do Evento (D2) | Utilizadores únicos que realizam o evento, medidos através de uma combinação de AppsFlyer e SKAN, incluindo dados modelados de valores nulos. Para quem utiliza o SKAN 4, estes dados são acumulados nos primeiros 2 dias após a instalação. Para quem utiliza o SKAN 3, os dados são uma acumulação de dias pós-instalação com base na janela de atividades definida. |
| Utilizadores Únicos do Evento (D7) | Utilizadores únicos que realizam o evento, modelados com base numa combinação de AppsFlyer e SKAN. Inclui dados modelados, além da janela de medição do SKAN, até 7 dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#inapp-event-ltv">Saiba mais</Anchor><br /><br />Nota: Os utilizadores únicos em (D7) também incluem utilizadores únicos em D2. |
| eCPA do Evento (D2) | Custo Efetivo por Ação: Custo/utilizadores únicos a realizar o evento. |
| eCPA do Evento (D7) | Custo Efetivo por Ação: Custo/utilizadores únicos a realizar o evento. Inclui dados modelados, além da janela de medição do SKAN, até 7 dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#inapp-event-ltv">Saiba mais</Anchor> |
| Conversão de Eventos (D2) | Taxa (%) de utilizadores únicos que realizam o evento, em proporção aos utilizadores que atribuem (ou seja, instalam, reengajam ou reatribuem). Fórmula: Utilizadores únicos / atribuições * 100. |
| Conversão de Eventos (D7) | Taxa (%) de utilizadores únicos que realizam o evento, em proporção aos utilizadores que atribuem (ou seja, instalam, reengajam ou reatribuem). Fórmula: Utilizadores únicos / atribuições * 100. Inclui dados modelados, além da janela de medição do SKAN, até 7 dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#inapp-event-ltv">Saiba mais</Anchor> |
| Receita do evento (D2) | Receita gerada com este evento, dentro dos dias definidos após a instalação |
| Receita do evento (D7) | Receita gerada com este evento nos dias definidos após a instalação. Inclui dados modelados, além da janela de medição do SKAN, até 7 dias após a instalação. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#inapp-event-ltv">Saiba mais</Anchor> |

</Accordion>

<div id="how-does-ssot-work" />

## Como funciona o SSOT

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Compreender a duplicação de atribuições modeladas SKAN-AF">

Atribuições SKAN e modeladas AF operam de formas distintas, cada uma com características e limitações próprias. Assim, cada instalação pode ser atribuída a uma fonte de mídia não orgânica:

* Exclusivamente através do SKAN ou modelo AF (atribuição única).
* Simultaneamente por SKAN e modelo AF (duplicados). Neste caso, o mecanismo SSOT assinala uma instalação duplicada do SKAN com a bandeira: af\_attribution\_flag=TRUE. E, no painel SSOT, apenas uma instalação é exibida ao invés de duas.
* Nem pelo SKAN nem pelo modelo AF, indicando que a instalação é orgânica.

Os cenários de atribuição possíveis no modelo SKAN-AF são ilustrados no diagrama de Venn abaixo.

![altskan_af_model_diagram.pngalt](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

A tabela a seguir detalha os motivos para cada cenário de atribuição.

| Apenas SKAN | Só o modelo AF | Ambos SKAN e modelo AF | Nem SKAN nem modelo AF |
| --- | --- | --- | --- |
| <ul><li>A fonte de mídia é um SRN, o dispositivo do utilizador possui iOS 14.5+, e o utilizador não fornece consentimento duplo para ATT.</li><li>A fonte de mídia não é SRN, o dispositivo do utilizador possui iOS 14.5+, a modelação probabilística não está disponível, e o utilizador não fornece consentimento duplo ATT.</li></ul> | <ul><li>O dispositivo do utilizador possui iOS 14.4 ou anterior.</li><li>A fonte de mídia não suporta SKAN.</li><li>A instalação ocorreu através de um fluxo de web-para-aplicação (SKAN apenas suporta app-to-app).</li><li>A instalação é via retargeting (não suportado pelo SKAN)</li></ul> | Não existem limitações e tanto o SKAN quanto um modelo AF atribuem a instalação.<br /><br />Isto gera instalações duplicadas, e é quando o SSOT é necessário para eliminar as duplicações. | O utilizador é orgânico |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="Funcionamento do mecanismo SSOT">

O SSOT funciona conforme detalhado na imagem seguinte.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**Como funciona o mecanismo SSOT?**

O mecanismo SSOT está presente no SDK da AppsFlyer na sua aplicação, no dispositivo do utilizador, e na plataforma AppsFlyer da seguinte maneira:

**Dispositivo do utilizador:**

* O utilizador abre a aplicação pela primeira vez. A plataforma AppsFlyer tenta atribuir o utilizador. A capacidade de atribuição depende do tipo de campanha e do estado de consentimento do utilizador (ATT).
* Se a atribuição for bem-sucedida, o SDK define o bit de atribuição no Valor de Conversão (CV).
* O fluxo normal da SKAdNetwork continua sem alterações. Ou seja, a atividade do utilizador continua a ser medida e o CV é ajustado até que a janela de medição termine.
* Posteriormente, o iOS envia o postback.

**Plataforma AppsFlyer**

* A AppsFlyer recebe o postback do iOS, decodifica o valor de conversão, e expõe o valor do bit de atribuição através do af\_attribution\_flag conforme detalhado na tabela seguinte.

**Considerações**

* De modo geral, a AppsFlyer não considera as reinstalações. No contexto do SSOT, o estado de reinstalação não é levado em conta. Isso significa que o SSOT não elimina instalações SKAN duplicadas oriundas de reinstalações no contexto da análise SSOT, e isso não afeta a configuração do sinal af\_attribution.

<div id="attribution-flag-field" />

#### **Campo de sinalização de atribuição**

| Indicador SSOT no Valor de Conversão | Significado | Campo af\_attribution\_flag |
| --- | --- | --- |
| Ativado | O SSOT está ativado no Conversion Studio e a AppsFlyer conseguiu atribuir o utilizador. | Verdadeiro |
| Desligado | O SSOT está ativado no Conversion Studio e a AppsFlyer não conseguiu atribuir o utilizador. | Falso |
| -- | O SSOT está desativado no Conversion Studio. | Nulo |

**Como o af\_attribution\_flag (bit de atribuição) afeta as ferramentas de relatórios?**

* Painel do SKAN: Reflete apenas o desempenho reportado pelos postbacks do SKAN. Portanto, o sinal af\_attribution não é considerado e os duplicados não são eliminados.
* Relatórios <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">agregados de desempenho</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">dados brutos</Anchor> do SKAN: O af\_attribution\_flag está disponível nestes relatórios. Utilize-o conforme as suas necessidades de relatório. Ao unir dados SKAN com os da AppsFlyer, utilize o indicador para eliminar dados duplicados. Isto aplica-se tanto a relatórios de dados brutos como agregados.
* Visualização de SSOT no painel de visão geral: Os dados de todos os métodos de atribuição, como SKAN, IDFA, IDFV, Apple Search Ads, entre outros, são combinados numa única visão após a remoção dos dados SKAN duplicados.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Métricas derivadas da combinação de dados de múltiplos métodos de atribuição">

Ao combinar dados SKAN com outros métodos de atribuição, utilize o af\_attribution\_flag para remover dados duplicados. Isto aplica-se tanto a relatórios de dados brutos como agregados.

As métricas exemplificativas seguintes podem ser calculadas com o af\_attribution\_flag:

* Instalações não orgânicas
* Instalações orgânicas
* eCPI
* Coorte de receita

Fórmula para calcular métricas de exemplo:

| Descrição da métrica | Designação | Fórmula |
| --- | --- | --- |
| Instalações não orgânicas da AppsFlyer | E | Instalações não orgânicas reportadas pela AppsFlyer |
| Instalações únicas do SKAN | B | Instalações SKAN onde af\_attribution\_flag=false |
| Todas as instalações não orgânicas | C | A + B |
| Instalações orgânicas | J | Instalações totais - C<br /><br />**Nota**: Instalações totais refere-se a todas as instalações registadas pelo SDK da AppsFlyer, independentemente da atribuição. |
| eCPI da campanha | E | Custo / C |
| Coorte de receita | F | Adicione o seguinte:<ul><li>Receita de utilizadores definida por A, incluindo eventos gerados no período inicial após a instalação, correspondentes à sua janela de medição SKAN.</li><li>Receita do SKAN onde af\_attribution\_flag = false</li></ul> |
| Receita orgânica D2 | G | Receita total D2 - receita D2 das instalações A e B |
| Utilizadores únicos IAE orgânicos D2 | H | Total de utilizadores únicos D2 IAE – utilizadores únicos de evento D2 das instalações A e B |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Visualização de SSOT | O SSOT apenas está disponível se houver pelo menos um retorno de SKAN para cada um dos últimos cinco dias que inclua `af_attribution_flag=true`. |
| Total de instalações | Em alguns casos, pode haver mais instalações exibidas quando o SSOT está ativado em comparação a quando ele está desativado. Uma das razões é que a modelação de valores de conversão nulos pode afetar o cálculo da data de instalação e causar diferenças ao comparar instalações em datas semelhantes. Além disso, o total de instalações pode ser inflacionado se os CVs nulos não forem modelados, já que cada instalação SKAN é contabilizada como única (com o indicador ). |
| Resultados | As receitas e outras métricas relacionadas (ARPU, ROAS, ROI, lucro bruto) são suportadas desde 1 de setembro de 2022. |
| Agências | Os utilizadores de agências podem visualizar a visualização SSOT no painel de visão geral. |
| Redes de anúncios | <ul><li>As redes de anúncios podem aceder à visualização SSOT no painel de visão geral para ver os dados atribuídos à sua fonte de mídia. Para visualizar o SSOT, é necessário que:<ul><li>O anunciante tenha o SSOT ativado no Conversion Studio.</li><li>A rede de anúncios esteja a executar campanhas SKAN.</li><li>A rede de anúncios tenha as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões necessárias</Anchor> do anunciante para aceder aos dados agregados.</li></ul></li><li>As redes de anúncios podem receber sinais SSOT através de postbacks SKAN adicionando o campo macro skad\_af\_attribution\_flag. <Anchor target="_blank" href="/partners/pt/docs/skan-integration-guide-for-ad-networks#receber-dados-da-appsflyer">Saiba mais</Anchor></li></ul> |
| Métricas D7 | Métricas D7 para tráfego orgânico estão disponíveis a partir de 16 de fevereiro de 2025.<br /><br />As métricas D7 podem estar ausentes ou ser inferiores às métricas D2 se:<ul><li>O intervalo de datas incluir datas para as quais ainda não passaram 8 dias.</li><li>Os dados modelados não estão disponíveis. Por exemplo, se não houver dados de receita para 14 dias. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor></li><li>A configuração do SKAN Conversion Studio foi alterada nos últimos 14 dias.</li><li>Existem menos de 10 instalações para uma determinada data.</li></ul> |
| Alterações na configuração do SKAN Conversion Studio | Quando altera a configuração do SKAN Conversion Studio, podem surgir imprecisões nos dados SSOT durante cerca de 96 horas. Isto deve-se ao facto de a AppsFlyer começar imediatamente a descodificar os postbacks SKAN com o novo esquema, embora continuem a chegar postbacks de instalações codificadas com o esquema anterior. |
| Dados reportados pela AF | <ul><li>Os dados relatados por AF, às vezes chamados de dados do modelo AF, referem-se a dados de instalações ou outros eventos atribuídos por meio de outro método de atribuição da AppsFlyer, em oposição ao SKAN.</li><li>O objetivo do painel SSOT é evitar a duplicação de instalações e eventos atribuídos por meio do SKAN e de outro método da AppsFlyer.</li><li>Se você ativar o SSOT, mas quiser visualizar os dados anteriores à ativação do SSOT, o painel do SSOT exibirá apenas os dados relatados pelo AF.</li></ul> |
| Eventos in-app | Os eventos in-app (como dimensões) e suas métricas estão disponíveis apenas para:<ul><li>Estão disponíveis os eventos que ocorreram durante o período da Janela 1.</li></ul> |
| Atraso do postback do SKAN | Quando os postbacks do SKAN chegam com atraso significativo, por exemplo, da API do Google, o que pode levar até 15 dias, os dados de dias posteriores (como D7) podem inicialmente parecer inferiores aos de dias anteriores (como D2). Esse atraso pode afetar a precisão do modelo de SSOT. Por esse motivo, recomendamos esperar pelo menos 15 dias após a data de instalação para que os dados sejam totalmente preenchidos antes de avaliar a precisão do modelo. |

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * Painel de visão geral
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia da solução SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Estúdio de conversão SKAN</Anchor>

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=acerca-da-fonte-%C3%BAnica-da-verdade-dados-reais-de-desempenho-no-ios 01H8TZV6P41Z3ZEZ8VS86DK1J9=acerca-da-fonte-%C3%BAnica-da-verdade-dados-reais-de-desempenho-no-ios 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=visualiza%C3%A7%C3%A3o-do-painel-de-vis%C3%A3o-geral-da-fonte-%C3%BAnica-da-verdade 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=visualiza%C3%A7%C3%A3o-do-painel-de-vis%C3%A3o-geral-da-fonte-%C3%BAnica-da-verdade 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=considera%C3%A7%C3%B5es-sobre-os-filtros 01H8TZV6P4QXEXYWSXKDB7B5SV=considera%C3%A7%C3%B5es-sobre-os-filtros 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=como-funciona-o-ssot 01H8TZV6P4K8VXNKDR7JHM8PFW=como-funciona-o-ssot 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=campo-de-sinaliza%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o 01H8TZV6P5SSKDTKV4BV3TTA7D=campo-de-sinaliza%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=consulte-tamb%C3%A9m" />
