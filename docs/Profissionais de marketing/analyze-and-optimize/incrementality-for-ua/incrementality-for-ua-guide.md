---
title: Incrementalidade para UA - Guia
metadata:
  keywords:
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2025-11-18T06:58:45Z'
  edited_at: '2026-08-19T00:07:14Z'
  id: 41021758795025
  locale: pt
  section: Incrementality for UA
  section_id: 40761623209873
  url: https://support.appsflyer.com/hc/pt/articles/41021758795025
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Faça um experimento de incrementalidade para entender o real impacto das suas campanhas de aquisição de usuários (UA).

<Embed title="Incrementalidade para UA - Guia" typeOfEmbed="youtube" url="https://www.youtube.com/embed/vGrLyOvgdN0?si=91ZV8Xw25mmShB_F" providerUrl="https://www.youtube.com" />

<div id="about-incrementality-for-ua" />

## Sobre a Incrementalidade para UA

No marketing omnichannel atual, para entender a real eficácia de uma campanha, é necessário visualizar seus dados por mais de uma lente. A atribuição de último toque continua sendo fundamental para o monitoramento da performance em tempo real e para acessar insights granulares, mas ela não fornece informações sobre se uma campanha gerou um aumento causal real. A Incrementalidade para UA soluciona esse problema, avaliando se as campanhas realmente trazem um aumento no número de novos usuários.

Essa solução complementa a atribuição através de experimentos geográficos cientificamente rigorosos. Esses experimentos automatizados avaliam o aumento causal das suas campanhas, permitindo uma distribuição de orçamento mais inteligente e um processo de tomada de decisões mais confiante.  
Como líder de mercado, a AppsFlyer oferece a Incrementalidade para UA, garantindo uma forma poderosa de mensurar o verdadeiro impacto das suas campanhas. Essa solução oferece insights essenciais ao lado da atribuição, permitindo a mensuração completa em uma plataforma unificada.

**Por que usar a Incrementalidade para UA?**  
Hoje, equipes de aquisição de usuários enfrentam desafios complexos, incluindo jornadas fragmentadas, aumento nas restrições de privacidade e falhas na visibilidade em vários canais. A Incrementalidade para UA ajuda você a superar essas barreiras, revelando o verdadeiro impacto comercial das suas campanhas.

**Com a Incrementalidade para UA, você pode:**

* **Focar na performance real:** acesse insights adicionais para além do engajamento com anúncios e das conversões atribuídas. Entenda quais campanhas realmente impulsionam seu crescimento, conquistando uma visão mais completa da sua atribuição.
* **Fazer comparações diretas:** teste várias campanhas ou fontes de mídia simultaneamente com a distribuição automática de grupos de teste/grupos de controle e o suporte nativo das principais plataformas de anúncios, como Meta, Google Ads e TikTok.
* **Otimizar a distribuição de orçamento:** pare de investir em campanhas de baixo impacto e foque naquelas que impulsionam um aumento real no número de usuários.
* **Automatizar fluxos de trabalho nos experimentos:** pule a configuração manual e evite dependências de BI. A AppsFlyer automatiza o design, execução e análise de experimentos.
* **Mensurar com foco na privacidade:** os experimentos são realizados em dados agregados em nível de geolocalização, seguindo regulamentos de privacidade como a GDPR e a ATT da Apple.

**Sobre testes por geolocalização**

A Incrementalidade para UA usa um design experimental baseado em geolocalização. As regiões geográficas são divididas em grupos estatisticamente semelhantes com base no histórico de instalações ou comportamento de evento. Um grupo é exposto à sua campanha de aquisição de usuários e o outro é retido da exposição. Após a execução do experimento por um período definido, a diferença na performance entre os dois grupos é analisada para revelar qual foi o aumento incremental. A geolocalização é segura, imparcial e não usa dados a nível de usuário.

A Incrementalidade para UA fornece os insights que você precisa para entender o verdadeiro valor incremental das suas campanhas de marketing, sem ser obstruída por dados inconsistentes ou sobreposições de direcionamento. Assim, você acessa uma visão clara da eficácia das suas campanhas, permitindo que você tome decisões melhores e baseadas em dados.

<div id="experiment-design-and-insights" />

## Design e insights do experimento

Vamos explicar como a Incrementalidade para experimentos de UA é estruturada, como trabalhar com eles e como eles fornecem insights causais e confiáveis sobre a performance da campanha.

<div id="understanding-geo-experimentation-explainer" />

<Accordion title="Entendendo a experimentação geográfica">

A Incrementalidade para UA usa experiências baseadas em geolocalização para mensurar o verdadeiro impacto da sua campanha de forma científica. Em vez de segmentar usuários, segmentamos áreas geográficas em regiões de exposição e grupos de controle estatisticamente semelhantes. Essas regiões são selecionadas com base no tamanho e no histórico de comportamento. Os anúncios são exibidos apenas para regiões de teste, enquanto as regiões de controle não recebem exposição. Ao comparar o comportamento dos dois grupos durante o período de espera, podemos mensurar o efeito causal real — não apenas a correlação.

**Os experimentos de geolocalização seguem uma linha do tempo estruturada:**

* **Antes do experimento:** ambos os grupos são igualmente expostos a anúncios das campanhas mensuradas. Durante esse tempo, coletamos dados de base e criamos um modelo que captura a relação histórica entre as regiões de teste e as regiões de controle.
* **Intervenção (o experimento):** as campanhas são ativadas apenas nas regiões de teste. As regiões restantes são impedidas de visualizar anúncios das campanhas mensuradas.
* **Cálculo do efeito causal**: a diferença entre os resultados observados nas regiões de controle e nas regiões teste durante o experimento é somada ao longo do tempo, sendo usada para determinar o impacto cumulativo.

**Regressão baseada em tempo (TBR)**

No centro do nosso experimento geográfico está a regressão baseada em tempo (TBR, do inglês Time-Based Regression). A TBR é usada para calcular aumentos, prevendo o que teria acontecido na ausência de uma intervenção de marketing. Ou seja, comparamos os resultados observados em uma região de teste (onde a intervenção é feita) com os resultados previstos com base na relação histórica entre uma região de controle (não exposta à intervenção) e uma região de teste.

**Como funciona**

* Criação de geodesigns de regiões de controle e regiões de teste:
  * A AppsFlyer analisa o histórico de instalações ou comportamento de eventos in-app por aplicativo e usa a TBR em milhares de conjuntos aleatórios de regiões de controle/regiões de teste por diferentes períodos de tempo, identificando aquelas com menor diferença entre si.
* Período pré-teste:
  * Antes de começar a intervenção, os dados são coletados tanto para as regiões de controle quanto para as regiões de teste.
  * Um modelo de regressão é criado para capturar a relação entre a série de tempo da região de teste e a região de controle.
* Previsão de contradições:
  * Usando o modelo desenvolvido no período pré-teste, os resultados esperados para a região de controle (se nenhuma intervenção ocorreu) são previstos durante o período de teste. Eles são chamados de “contra-factuais”.
* Período de teste:
  * Para as campanhas que fazem parte do experimento de incrementalidade, as regiões de retenção predeterminadas são automaticamente excluídas da visualização de anúncios durante a duração do experimento.
* Cálculo do efeito causal:
  * O efeito causal da intervenção em cada ponto de tempo é a diferença entre o resultado observado na região de controle e sua previsão contra-factual.
* Efeitos cumulativos:
  * Essas diferenças são resumidas ao longo do tempo para determinar o impacto cumulativo da intervenção (por exemplo, aumento total em instalações ou conversões).
* Aumento causado por marketing:
  * O aumento causado por marketing é o efeito cumulativo que quantifica os resultados incrementais impulsionados por atividades de marketing em comparação com os resultados esperados sem ele.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

A Incrementalidade para UA ajuda você a solucionar seus principais desafios de crescimento, revelando o verdadeiro impacto comercial das suas campanhas. Veja abaixo alguns casos de uso comuns em que os testes de incrementalidade baseados em geolocalização adicionam valor crítico.

1. **Otimize a distribuição de orçamentos em todas as plataformas de anúncios**  
   **Desafio:** As métricas de atribuição mostram uma performance semelhante em várias plataformas, mas você não tem certeza do que realmente está impulsionando seu crescimento. **Solução:** Faça testes de incrementalidade paralelos usando várias células entre plataformas. Use os resultados para identificar qual plataforma causa um aumento real, redistribuindo seu orçamento de acordo.
2. **Validar a performance de novos canais ou formatos**  
   **Desafio:** Você está testando um novo canal ou plataforma de anúncios, mas as métricas iniciais são inconsistentes ou infladas por conta da sobreposição de direcionamento. **Solução:** Faça testes de geolocalização para isolar o impacto do novo canal no seu mix. Determine se ele contribui com novas instalações líquidas ou apenas canibaliza as existentes.
3. **Compreender o impacto das campanhas de marca**  
   **Desafio:** As campanhas de marca têm uma boa performance nos relatórios de atribuição, mas você não tem certeza se os usuários teriam convertido sem elas. **Solução:** Faça experimentos geográficos para descobrir se os anúncios de marca ou display realmente influenciam o comportamento do usuário ou se eles apenas captam a demanda existente.
4. **Comparar estratégias de campanha na mesma plataforma**  
   **Desafio:** Você quer testar duas estratégias criativas (por exemplo, vídeo vs. carrossel) ou tipos de bids (por exemplo, maximizar instalações vs. ROAS) dentro da mesma rede. **Solução:** Faça um experimento com várias células, atribuindo cada estratégia a uma célula diferente. Compare o aumento incremental de cada um e escolha o vencedor.
5. **Redistribuir investimentos de mercados saturados para mercados escaláveis**  
   **Desafio:** Mercados mais maduros trazem retornos menores e custos de aquisição maiores. No entanto, os dados de atribuição não são o suficiente para esclarecer se você está alcançando novos usuários. **Solução:** Os testes de aumento de geolocalização mostram se as campanhas nesses mercados ainda são incrementais. Caso contrário, transfira seu orçamento para regiões inexploradas ou subvalorizadas, que apresentam maior potencial.

</Accordion>

<div id="selecting-campaigns" />

<Accordion title="Selecionando o que você deve mensurar">

Vamos falar sobre quais são as melhores campanhas que devem ser selecionadas para seus experimentos. Algumas considerações:

* **Impacto:** Quais testes podem influenciar a sua estratégia como um todo? Muitas vezes, isso significa que você deve começar seus testes com suas maiores iniciativas, pois entender como elas realmente afetam o seu crescimento levará a otimizações significativas.
* **Volume de conversão:** Bons experimentos precisam de dados suficientes. Para cada campanha mensurada, foque em no mínimo 5.000 instalações ou eventos mensais, de acordo com o principal KPI que você deseja mensurar
* **Exploração:** A incrementalidade é uma ferramenta incrível para testar algo novo, como entrar em um novo mercado ou lançar um novo canal.
* **Ter uma hipótese ou pergunta de teste claras:** Como qualquer outro experimento científico, pensar bem sobre qual é a sua principal pergunta contribuirá para a eficácia e a acionabilidade do seu experimento de incrementalidade. Por exemplo, você espera que um canal seja mais incremental do que o outro? Como isso afetará sua estratégia de marketing se sua hipótese for comprovada ou descartada?

</Accordion>

<div id="understanding-experiment-results" />

<Accordion title="Entendendo os resultados do experimento e usando os insights">

**Os principais resultados de KPI do experimento incluem:**

* **Aumento (%):** O impacto causal da atividade de marketing analisada, mensurada como as conversões adicionais (por exemplo, instalações ou eventos in-app) que a sua campanha realmente impulsionou, para além do que teria acontecido naturalmente sem essa campanha.
* **Conversões incrementais:** O número de instalações ou eventos impulsionados pela campanha mensurada.
* **Custo por instalação incremental** / **Custo por evento incremental:** O custo médio de cada conversão incremental, com base no investimento em anúncios da campanha.
* **Fator de incrementalidade:** A proporção entre instalações ou eventos incrementais (conforme mensurados pelo experimento) e instalações ou eventos de atribuição clássicos (conforme mensurados na atribuição clássica da AppsFlyer).

Veja a lista completa de KPIs de experimentos na [seção sobre o dashboard.](#conhecendo-o-dashboard)

Para que os insights de incrementalidade sejam realmente práticos, a AppsFlyer fornece tanto os KPIs de aumento (%) quanto de incrementalidade a nível de campanha.

**Otimização com base em aumento (%):**

<strong>A. A. </strong>A. Sem aumento:  
O objetivo final do marketing é gerar resultados incrementais. Se a sua campanha foi mensurada para não ter um aumento (regiões de controle estão com a mesma performance das regiões de teste), isso significa que ela não está trazendo nenhum valor adicional e deve ser otimizada para trazer um crescimento significativo. Se sua campanha não tiver um aumento, considere o seguinte:

* Transfira seus orçamentos para mais campanhas ou canais incrementais.
* Otimize: Como em qualquer outra campanha de baixa performance, você pode melhorá-la ajustando bids, metas, público-alvo, criativos e outros fatores relevantes. Em seguida, você pode executar outro experimento de incrementalidade para monitorar se os resultados melhoraram.
* Para fazer o diagnóstico dos fatores que podem estar afetando seus resultados, verifique sua configuração tecnológica, segmentação, mix de canais, posicionamentos, orçamentos, palavras-chave, criativos e sobreposições de campanhas. Essas informações serão muito úteis para a sua otimização e para garantir resultados incrementais no futuro.

**B.** B. **B. Aumento positivo:**  
Um aumento positivo significa que a sua campanha está gerando resultados incrementais além dos resultados que seriam conquistados sem os seus esforços de marketing. Primeiro, você deve validar se todos os seus esforços de marketing estão gerando um aumento positivo. Quando o aumento é positivo, considere o seguinte:

* Aumente o investimento em plataformas/canais/campanhas para ampliar seu crescimento.
* Amplie o alcance, expandindo audiências ou locais para aumentar o impacto.
* Identifique os fatores de crescimento, redobrando o sucesso e priorizando as melhores estratégias.
* Compare campanhas ou canais com base no aumento: O aumento é uma medida relativa calculada por meio da comparação entre as regiões de controle e as regiões de teste. Por isso, comparar campanhas com base no aumento pode ser um desafio. Por exemplo, se ambas as campanhas tiverem o mesmo impacto, mas uma delas atingir um número significativamente maior de usuários ou tiver um valor de gastos significativamente maior, seu aumento será maior.  
  Tente comparar campanhas que sejam semelhantes em gastos e alcance e que geralmente tenham como alvo as mesmas regiões geográficas.
* Se você está começando a mensurar a incrementalidade para o seu aplicativo ou negócio, é possível que você ainda não tenha uma referência sólida para determinar o nível exato de aumento positivo esperado de uma determinada campanha, canal ou investimento. Nesse caso, recomendamos que você faça a otimização usando os KPIs de incrementalidade a nível de campanha da AppsFlyer, conforme descrito abaixo.

**Otimização com base em KPIs de incrementalidade a nível de campanha:**

<strong>A. A. </strong>A. Total de conversões incrementais e métricas de custo:  
Assim como na atribuição clássica, o volume total de conversões incrementais e o investimento em anúncios necessário para gerar essas conversões fornecem métricas claras e acionáveis para a otimização. Você pode usar a contagem de conversões de incrementalidade a nível de campanha e o custo por conversão incremental para determinar se uma campanha atende às suas metas de volume e ROI, avaliando a sua performance em comparação a outras campanhas ou canais.

<strong>B. B. </strong>B. Acesse os dados de incrementalidade e atribuição clássicos lado a lado  
Para a contagem de conversões a nível de campanha e o custo por conversão, o dashboard de Incrementalidade apresenta dados de atribuição clássicos (último toque) E dados de incrementalidade lado a lado, permitindo que você entenda a relação entre os dois modelos e aplique seus aprendizados em uma escala maior.  
Quando analisadas separadamente, a atribuição clássica (“último toque”) e a incrementalidade são dois modelos de atribuição diferentes, cada um com suas próprias vantagens e desvantagens:

* A atribuição clássica (“último toque”) ocorre em tempo real, sendo padronizada, altamente escalável e granular. Portanto, ela permite a otimização a nível de usuário tanto do lado do anunciante quanto por meio de algoritmos de plataformas de anúncios em tempo real. No entanto, ela fornece uma visão mais clara do engajamento no final do funil, sem oferecer provas científicas causais.
* A incrementalidade é uma ótima ferramenta para provar cientificamente o impacto causal e é ideal para a mensuração omnichannel. No entanto, ela fornece insights agregados (a nível de campanha), além de ser periódica e mais difícil de escalar.

Quando usados em conjunto, os dois modelos fornecem uma visão holística da performance do seu marketing. O fator de incrementalidade da AppsFlyer apresenta a relação entre os dados de atribuição clássicos, que são a “linha de base” usada para uma otimização de marketing contínua, e os dados de incrementalidade usados para mensurar o impacto causal. Veja como você pode usar os fatores de incrementalidade para a otimização:

* **Fator de incrementalidade superior a 100%:** A incrementalidade mensurou mais conversões do que a atribuição clássica para a mesma campanha. Por exemplo, uma taxa de 110% significa que as instalações incrementais são 10%% mais altas do que as instalações mensuradas usando a atribuição clássica. Esse aumento nas conversões também se traduz em uma redução no custo por conversão, já que mais conversões são geradas pelo mesmo valor investido.  
  Se o fator de incrementalidade for superior a 100%, considere o seguinte:
  * Redistribua seu orçamento de acordo com a queda no custo por conversão incremental.
  * Avalie seus bids e metas de otimização de acordo com o custo por conversão incremental e o retorno incremental do investimento em anúncios.
  * Aplique esse fator a campanhas semelhantes antes de tomar futuras decisões de marketing. Por exemplo, se suas campanhas de vídeo apresentam consistentemente um fator de incrementalidade de 110% para instalações de aplicativos quando mensuradas em experimentos de incrementalidade, você pode considerar que as instalações na atribuição clássicas para campanhas semelhantes são 10% maiores (ou seja, cada 100 instalações de atribuição clássicas são, na verdade, mais próximas de 110 instalações).
* **Fator de incrementalidade abaixo de 100%:** A incrementalidade mensurou menos conversões do que a atribuição clássica para a mesma campanha. Por exemplo, uma taxa de 90% significa que as instalações incrementais são 10% menores do que as instalações mensuradas usando a atribuição clássica. Essa queda nas conversões também se traduz em um aumento no custo por conversão, já que menos conversões são geradas pelo mesmo valor investido. Se o fator de incrementalidade for inferior a 100%, considere o seguinte:
  * Redistribua seu orçamento de acordo com o aumento no custo por conversão incremental.

* * Avalie seus bids e metas de otimização de acordo com o custo por conversão incremental e o retorno incremental do investimento em anúncios.
  * Implemente esse fator em campanhas semelhantes para informar futuras decisões de marketing. Por exemplo, se suas campanhas de vídeo apresentam consistentemente um fator de incrementalidade de cerca de 90% para instalações de aplicativos quando mensuradas em experimentos de incrementalidade, você pode considerar que as instalações na atribuição clássicas para campanhas semelhantes são 10% menores (ou seja, cada 100 instalações de atribuição clássicas são, na verdade, mais próximas de 90 instalações).

</Accordion>

<div id="pausing-or-extending-experiments" />

<Accordion title="Pausar ou prolongar experimentos">

**Considere pausar experimentos (antes do padrão 30 dias) se:**

* As métricas de aumento, fator de incrementalidade e custo permaneceram estáveis por mais de 7 dias.
* Há uma boa justificativa para obter resultados mais rápidos às custas de métricas de incrementalidade potencialmente menos precisas ou menos “padronizadas”.

**Considere prolongar os experimentos (além dos 30 dias padrão) se:**

* O volume da campanha foi menor do que o esperado e deve aumentar para além do mínimo de conversões incrementais diárias.
* A janela de conversão para o evento mensurado é excepcionalmente longa, exigindo mais tempo para que os usuários sejam convertidos.

</Accordion>

<div id="get-started" />

## Iniciar

Para começar a usar a Incrementalidade para UA, siga os passos abaixo:

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Pré-requisitos**

* Uma <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">conta da</Anchor> AppsFlyer com uma assinatura de **Incrementalidade para UA** (peça ao seu CSM para ativá-la).
* O <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide">SDK da AppsFlyer</Anchor> instalado nos seus aplicativos mobile.
* Seu aplicativo deve ter pelo menos 120 dias de dados de instalação.

<div id="create-the-experiment-" />

<Accordion title="Primeiros passos Primeiros passos Passo 1: criar experimento">

O primeiro passo é criar um experimento.

**Para criar um experimento:**

1. Acesse “Incrementalidade para UA” clicando em **Otimizar** > **Incrementalidade para UA**, no menu lateral da AppsFlyer.

   <Image alt="Click Inc for UA new.png" src="https://files.readme.io/4170287cc98e038272fd91ee36cbf775a33b8a418920c7fabe54e32cff5789cd-41021731857041.png" width="254px" />
2. Clique em **+ Novo experimento**
3. **Preencha o formulário do experimento:**
   1. **Insira o nome do experimento:** Crie um nome descritivo para o experimento e clique em **Próximo**.
   2. **Defina seu geodesign:** Selecione o aplicativo, o país e a métrica principal que você deseja mensurar. A AppsFlyer usa isso para calcular a distribuição ideal entre as regiões expostas e as regiões de holdout do seu experimento.

      <Image alt="etapa 2 design de geolocalização.png" src="https://files.readme.io/3a901bd4dcccb788b1d0cc8f118cbdb0c682b570b470d13deba4f6ce0f852c3b-41021758781713.png" width="335px" />

      Assim que você envia o formulário, a AppsFlyer analisa seu geodesign, o que costuma levar apenas alguns minutos. Seu geodesign estará pronto para uso ou indisponível:

      * **Pronto:** Seu geodesign está aprovado e já pode ser utilizado. Agora você pode continuar com o experimento.
      * **Indisponível:** Atualmente, o geodesign não atende aos requisitos para validar um experimento, com base nos dados disponíveis para o aplicativo, o país e as métricas selecionados. Você pode enviá-lo novamente após 30 dias, porque a elegibilidade pode mudar à medida que seu aplicativo coleta mais dados.

      <div id="note" />

      > 📘 **Atenção**
      >
      > Se existirem regras de geodesign para o aplicativo e país selecionados, elas serão aplicadas automaticamente quando o geodesign for calculado. Consulte a [Política de geodesign](#h_01_geo-design-policy) para saber mais.


      <div id="note-1" />

      > 📘 **Observação**
      >
      > Cada país tem um certo número de **células** disponíveis para o seu experimento. Uma célula é constituída por um par de grupos de teste e de controle, estruturados de forma a serem semelhantes entre si e para todo o país. Você pode usar várias células em um experimento para uma comparação direta de diferentes campanhas entre fontes de mídia ou usá-las individualmente em experimentos separados.
      >
      > O número de células disponíveis depende do tamanho geográfico do país, da distribuição da população e dos níveis de atividade do aplicativo — fatores que afetam a capacidade de criar pares estatisticamente válidos de teste/controle. Países com regiões mais granulares e ativas oferecem mais células, permitindo mais experimentos.


      * **Selecionar um aplicativo** - selecione o aplicativo relevante para o experimento.
      * **Selecionar um país** - selecione o país onde você deseja executar o experimento. Clique em **Próximo**.
      * Selecione a **métrica principal** que você deseja mensurar. Pode ser uma instalação ou um evento in-app.
   3. **Configure os detalhes da campanha:**

* Você precisará selecionar uma conexão de **fonte de mídia** para cada célula do experimento. Esse é a fonte de mídia onde a sua campanha é executada. Se não houver conexões, você poderá [criar uma nova conexão](#Connections).
* Em seguida, selecione as campanhas correspondentes para mensurar no experimento.  
  Os experimentos de incrementalidade podem ser configurados para mensurar campanhas individuais (por exemplo, “Como está a campanha do Google em comparação à campanha da Meta”) ou a fonte de mídia ao selecionar várias campanhas em uma única célula do experimento (por exemplo, “Como está a performance do Google em comparação com a performance da Meta?”).  

  Escolha entre:  
  **Nível de campanha:** para mensurar o impacto de uma única campanha dentro de uma fonte mídia  
  **Nível de canal:** para mensurar o impacto conjunto de várias campanhas dentro de uma fonte de mídia

  **Atenção:** Se forem selecionadas várias campanhas em uma célula:

  * Todas as campanhas selecionadas irão compartilhar as mesmas regiões de holdout.
  * Os insights de incrementalidade serão apresentados a nível de célula, e não a nível de campanha individual.

    <Image alt="Inc para UA - Definir detalhes da campanha.png" src="https://files.readme.io/c92c2b785ea80d2c89fd06033b008a3618e04d88a3cc286e923acf88b5924261-45947468030097.png" width="64.57%" />
* Assim que um geodesign for aprovado, você verá a análise do experimento:
  * **Regiões de holdout:** As regiões que não foram expostas às suas campanhas durante o experimento
  * **Regiões expostas:** As regiões expostas às suas campanhas, usadas como base de mensuração
  * **Regras de geodesign:** Suas regras ativas e as regiões que elas abrangem. [Saiba mais](#h_01_geo-design-policy)
* Ao selecionar o nome da campanha, você verá o número mínimo de instalações ou eventos incrementais (com base na métrica principal selecionada) necessários para mensurar o impacto positivo da sua campanha com alta confiança estatística. Isso é conhecido como o “efeito detectável mínimo” do experimento. Certifique-se de que a campanha selecionada gere pelo menos esse número de conversões.

  **Dica** Escolha uma campanha que atenda ou exceda esse mínimo para garantir resultados confiáveis e estatisticamente válidos.
* Você pode adicionar células de experimento adicionais, se desejar. Para adicionar: Clique em **+ Célula de experimento** e selecione a conexão e a campanha correspondentes. Uma célula é constituída por um par de grupos de teste e de controle, estruturados de forma a serem semelhantes entre si e para todo o país. Você pode usar várias células em um experimento para uma comparação direta de diferentes campanhas nas fontes de mídia ou usá-las individualmente em experimentos separados.  

  Depois de configurar as células, clique em **Próximo**.

4. **Revise a configuração** - verifique se o resumo do experimento está certo e, em seguida, clique em **iniciar experimento**.  
   O experimento começa. Os resultados iniciais serão exibidos dentro de 24 horas.

   <div id="note-2" />

   > 📘 **Observação**
   >
   > Quando o experimento terminar, as campanhas conectadas retornarão às suas configurações de direcionamento anteriores. Isso garante a continuidade e consistência da campanha e permite que você retome suas atividades de UA sem precisar reconfigurar o direcionamento manualmente.
   >
   > **Exemplo**  
   > Vamos supor que você realizou um experimento nos Estados Unidos usando três cidades designadas. Durante o experimento, sua campanha estava restrita apenas a essas cidades. Quando o experimento terminar, a campanha retomará automaticamente seu direcionamento original — como “Estados Unidos (todos os locais)” — conforme foi configurado antes do experimento ter ocorrido.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="3. Analise os resultados e acesse seus insights">

<span id="zd-access-the-experiment-dashboard"></span><span id="access-the-experiment-dashboard"></span>Você pode ver os resultados do experimento no dashboard do experimento.

#### Acessar o dashboard do experimento

1. Acesse a Incrementalidade para experimentos de UA clicando em **Otimizar** > **Incrementalidade para UA**, no menu lateral da AppsFlyer.

   <Image alt="from Oprimize click Incrementality UA.png" src="https://files.readme.io/922e084c955b3220a5bc3ac82079515f2c07bc4bc1bc3861343132452cc4fc08-41021731858321.png" width="210px" />
2. Clique em um experimento específico para acessar o dashboard do experimento.

   ![Experiments table (1).png](https://files.readme.io/ffc37ed1e7381c73883933cb0de7a84495dd737e050849760e427e36d2b9918d-41021758785041.png)

<div id="a-tour-of-the-dashboard" />

#### Conhecendo o dashboard

[**![New Incrementality dashboard.png](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)**](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)

**A parte superior do dashboard exibe 2 gráficos visuais:**

* O **Aumento: Gráfico de regiões de teste vs. regiões de controle** - mostra o aumento incremental por célula do experimento.
* A **Linha do tempo do experimento: Gráfico de regiões de teste vs. regiões de controle** - mostra uma comparação lado a lado das instalações incrementais por dia no intervalo de datas do experimento, por célula.

A seção central do dashboard exibe os **KPIs de experimento** por célula de campanha, fonte de mídia e campanha:

* **Instalações de atribuição clássica:** O número de instalações que a campanha contribuiu, mensuradas por atribuição clássica.
* **Instalações de incrementalidade:** O número de instalações que a campanha contribuiu, conforme mensuradas pelo experimento.
* **Fator de incrementalidade:** A proporção entre instalações incrementais (mensuradas pelo experimento) e instalações/eventos na atribuição clássica. Por exemplo, uma taxa de 110% significa que as instalações incrementais são 10% mais altas do que as instalações mensuradas usando a atribuição clássica.
* **Custo de atribuição clássico por instalação:** O custo médio de cada instalação atribuída, com base no investimento em anúncios da campanha.
* **Custo de incrementalidade por instalação:** O custo médio de cada instalação incremental, com base no investimento em anúncios da campanha.
* **Aumento** - Quantas instalações/eventos adicionais ocorreram por causa da sua campanha, em comparação com o resultado que seria obtido sem ela. Calculado como: Aumento (%) = (performance real no grupo de teste (regiões excluídas - performance prevista no grupo de teste) / performance prevista no grupo de teste x 100 x -1.
* **Confiança:** O nível de confiança estatística de que o aumento é maior que zero.  

  Para saber mais sobre como ler os resultados, consulte [Entendendo os resultados do experimento e usando os insights](#understanding-experiment-results).

O gráfico de **instalações incrementais cumulativas** está na parte inferior do dashboard, que mostra as instalações incrementais cumulativas por célula.

**Observação:** Se a mensuração do **nível de canal** estiver selecionada (várias campanhas em uma célula):

* Todas as campanhas selecionadas irão compartilhar as mesmas regiões de holdout.
* Os insights de incrementalidade serão apresentados a nível de célula, e não a nível de campanha individual.

[<Image alt="Channel level experiments dashboard cropped narrower.png" src="https://files.readme.io/4bcf80c6427e58d13b7ab0380033cb7e34852bd402150b2c05c075e5db3604a3-small-46014061198353.png" width="2862px" />](https://files.readme.io/4bcf80c6427e58d13b7ab0380033cb7e34852bd402150b2c05c075e5db3604a3-small-46014061198353.png)

</Accordion>

<div id="manage" />

## Gerenciar

Essa seção explica como gerenciar suas conexões, a política de geodesign e os experimentos.

<div id="Connections" />

<Accordion title="Conexões">

Conexões se referem à integração entre a Incrementalidade para UA e seus parceiros de mídia. Elas possibilitam a vinculação de campanhas e a execução de experimentos em plataformas conectadas.

**Para adicionar conexões de fonte de mídia:**

1. Acesse “Incrementalidade para UA” clicando em **Otimizar** > **Incrementalidade para UA**, no menu lateral da AppsFlyer.
2. Clique na aba **Conexões** e depois em **+ Nova conexão**.

   <Image alt="from Connections tab click +New connection w arrow.png" src="https://files.readme.io/e9df79d34ec3d94e89f51f42b132f8ba475225b46246d044d2a720991b0900e0-41021731865745.png" width="465px" />
3. Selecione uma fonte de mídia para conectar.

   <Image alt="Add connection.png" src="https://files.readme.io/c9eab02131220cd28683a717745bff852da28847a4164fa27b5be4780cd98018-41021731866897.png" width="409px" />
4. Insira suas credenciais para fazer login e criar a conexão.

</Accordion>

<div id="h_01_geo-design-policy" />

<Accordion title="Política de geodesign">

A política de geodesign permite que você defina regras de geodesign para seu experimento a nível de conta. As regras são definidas por aplicativo e país, sendo aplicadas automaticamente a todos os geodesigns calculados depois que uma regra é salva.

Use regras de geodesign para cumprir as restrições legais, proteger mercados de alto valor ou isolar regiões afetadas por testes paralelos.

<div id="geo-design-rule-types" />

#### Tipos de regras de geodesign

Três tipos de regras estão disponíveis:

| Tipo de regra | O que faz | Exemplo de caso de uso |
| --- | --- | --- |
| **Não usar holdout** | Estas regiões nunca são inseridas em grupos de holdout, mas ainda podem estar em grupos expostos. Suas campanhas nessas regiões nunca são pausadas nem interrompidas pelo experimento. | Um mercado de alta performance que deve permanecer ativo em todos os momentos. |
| **Não segmente** | Estas regiões estão totalmente excluídas da segmentação de campanhas. Elas não aparecerão em grupos expostos ou de holdout. | Um mercado onde os anúncios são legalmente restritos. |
| **Excluir da análise** | Estas regiões permanecerão na segmentação de campanhas para manter a atividade normal de anúncios, mas não serão incluídas em grupos expostos ou de holdout. | <ul><li>Regiões que executam testes de geo-lift em paralelo e que podem distorcer os resultados.</li><li>Regiões que executam testes de geo-lift em paralelo ou que têm ações de marketing locais previstas, podendo distorcer os resultados.</li></ul> |

<div id="set-up-a-geo-design-rule" />

#### Configure uma regra de geodesign

**Para configurar uma regra geodesign:**

1. Em “Incrementalidade para UA”, clique na aba **Configurações avançadas**.
2. Na seção **Política de geodesign**, clique em **+ Nova regra de geodesign**.
3. Na caixa de diálogo **Nova regra de geodesign**, selecione o **aplicativo** e o **país** aos quais essa regra se aplica.
4. Em **Regras**, configure cada regra:
   1. Selecione o tipo de **Regra de geodesign:** Não usar holdout, não segmentar ou excluir da análise.
   2. Selecione as **regiões** (estados ou sub-regiões, de acordo com cada país). Você pode pesquisar por nome ou código.
5. Para adicionar outro tipo de regra para o mesmo aplicativo e país, clique em **+ Adicionar regra**.
6. Revise o painel **Resumo** à direita, que é atualizado em tempo real à medida que você faz seleções.
7. Clique em **Salvar**.

Agora a regra está ativa e será aplicada a todos os geodesigns calculados para o aplicativo e o país selecionados no futuro.

<div id="delete-a-geo-design-rule" />

#### Exclua uma regra de geodesign

**Para eliminar uma regra de geodesign:**

1. Na seção **Política de geodesign**, localize a regra que você pretende excluir.
2. Abra o menu de ações e selecione **Excluir**.
3. Confirme no diálogo **Excluir regra?** .

<div id="note-3" />

> 📘 **Observação**
>
> A exclusão de uma regra não afeta os experimentos ativos. Se havia regras anteriores (ou nenhuma regra), elas permanecem em vigor para qualquer experimento que já esteja em execução. A exclusão de uma regra apenas remove-a de futuros geodesigns/experimentos.

<div id="view-geo-design-rules-in-an-experiment" />

#### Veja as regras de geodesign em um experimento

Assim que um geodesign for aprovado e você estiver configurando seu experimento, você verá uma seção de análise da região (marcada como **Regras aplicáveis**) que mostra:

* **Regiões de holdout:** As regiões que não foram expostas às suas campanhas durante o experimento
* **Regiões expostas:** As regiões expostas às suas campanhas, usadas como base de mensuração
* **Regras de exclusão:** As regras ativas (não usar holdout, não segmentar ou excluir da análise) e as regiões específicas que elas abrangem

No relatório do experimento, você pode ver a análise geográfica completa ao selecionar **Análise de geodesign** no menu de ações. Isso mostra a mesma análise acima, exibindo as regras que estavam ativas quando o experimento foi criado. Para gerenciar as regras, clique em **Gerenciar política de geodesign** na parte inferior do painel.

<div id="traits-and-limitations" />

#### Características e limitações

Ao trabalhar com regras de geodesign, lembre-se:

| Caraterística | Descrição |
| --- | --- |
| Escopo | As regras são aplicadas por combinação de aplicativo e país. |
| Granularidade geográfica | As regiões são definidas a nível estadual ou subregional, de acordo com cada país. |
| Persistência das regras | As regras permanecem ativas até serem excluídas. |
| Retroatividade | As regras aplicam-se apenas aos geodesigns calculados depois que uma regra é salva. As experiências ativas não são afetadas. |

</Accordion>

<div id="Experiments" />

<Accordion title="Experimentos">

Você pode visualizar e gerenciar todos os seus experimentos em um só lugar.

**Para visualizar e gerenciar seus experimentos:**

Em **Incrementalidade para UA**, clique na aba **Experimentos**.

[![Experiments table.png](https://files.readme.io/61958568e19f243855237465d132935a339ab18f24b5a8c8318d411239b7fd8b-41021758787089.png)](https://files.readme.io/61958568e19f243855237465d132935a339ab18f24b5a8c8318d411239b7fd8b-41021758787089.png)

Para cada experimento, você pode ver:

* **Nome do experimento**
* **Aplicativo** - classificável
* **País** - classificável
* **Fonte de mídia**
* **Datas** - intervalo de datas do experimento
* [**Status**](#coluna-de-status) - você pode ver o número de dias restantes no experimento ou quando ele é concluído.
* **aumento**

<div id="status-column" />

#### **Coluna de status**

* **Concluído** - o período do experimento terminou
* **Ativo** - experimento está sendo executado no momento
* **Pendente** - experimento pendente de resultados (primeiras 24 horas)
* **Em análise** - design em análise (24 horas até a resposta)
* **Pronto** - design foi avaliado e considerado adequado
* **Indisponível** - design foi revisado e não foi considerado adequado

Passe o mouse sobre o experimento para acessar o ícone de<Image alt="action menu.png" src="https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png" width="16px" /> ações.

<Image alt="Experiments menu.png" src="https://files.readme.io/5e25e2b4b7f9651ad6a510916b9ee2b2a45d4064a0801a24baa6e3d62bde81a0-41021731868049.png" width="254px" />

A partir daqui você pode:

* Ver detalhes do experimento
* Prolongar a duração do experimento
* Parar experimento

</Accordion>

<div id="extend-experiment" />

<Accordion title="Prolongar experimento">

**Para prolongar um experimento:**

No experimento, clique no ícone de <Image alt="action menu.png" src="https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png" width="16px" /> ações (no canto superior direito) e selecione **Prolongar duração do experimento**.

<Image alt="Extend experiment.png" src="https://files.readme.io/191463618d7bcdba2210e71bf38719c8d5af9951a5282a98cc1e3bc87a7e853b-41021731869329.png" width="336px" />

Isso prolongará o experimento por mais 14 dias.

</Accordion>

<div id="stop-experiment" />

<Accordion title="Parar experimento">

**Para interromper um experimento:**

No experimento, clique no ícone de ⠇ ações (no canto superior direito) e selecione **Parar experimento**.

<Image alt="Stop experiment.png" src="https://files.readme.io/2622bca9bafa7894d4ca967f13d6626eb3cd53554720d134d8092ebb0d561740-41021731870609.png" width="331px" />

</Accordion>

<div id="traits-and-limitations-1" />

## Características e limitações

Esta seção descreve algumas das principais características e limitações da Incrementalidade para UA.

<div id="key-traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Descrição |
| --- | --- |
| País | Atualmente, a Incrementalidade para UA é compatível com testes feitos nos Estados Unidos, Índia, México, Brasil, Japão e Alemanha. Outros países serão adicionados à medida que eles se tornam disponíveis. |
| Geossegmentação de campanhas disponível | A Incrementalidade para UA é compatível com campanhas que visam um único país. Campanhas que visam vários países ou regiões específicas dentro de um país (por exemplo, estados ou cidades) não são compatíveis. |
| Histórico de dados de engajamento de aplicativos | O aplicativo deve ter pelo menos 120 dias de dados de instalação e/ou eventos in-app disponíveis. |
| Instalações não orgânicas mensais mínimas | Cada aplicativo mensurado deve gerar pelo menos 10.000 instalações não orgânicas por mês para executar um experimento válido. |

</Accordion>

<div data-zendesk-anchors="overview=sobre-a-incrementalidade-para-ua h_01HBB6EJ8SQ3776WCVQZA4MJ6M=sobre-a-incrementalidade-para-ua get-started=design-e-insights-do-experimento h_01JZQ4N4PEKTP1TZTDQ191ZDM3=design-e-insights-do-experimento h_01JZQ4Q1C035S9EXVJX8YR3PEA=understanding-geo-experimentation-explainer h_01K049CDW93B3C7VZSNFQ1AD0N=use-cases h_01JZQ4Q1C0BZAH7E0J2T1SCPD0=selecting-campaigns h_01JZQ4Q1C0Z3M002TWYKB8SS3M=understanding-experiment-results h_01JZQ4Q1C0NWWVD8ENVJB50RMD=pausing-or-extending-experiments h_01HBB6EJ8S2T9JHKVWH1JK1FPD=iniciar h_01HBB6EJ8SVV71R5W9Z96D7WCG=create-the-experiment- h_01K2F27SEQF8N38FMCW8PSFB36=aten%C3%A7%C3%A3o h_01KVA5SPC58YXP67G86Z2CHGDF=observa%C3%A7%C3%A3o h_01K2F1FQ0NN5YPWK5026Y7935D=observa%C3%A7%C3%A3o-1 01JV7F4ECQAY0PJNV2A94E5GA9=analyze-the-results h_01JZJ70C1C0ZRD8WMCKZBHKCEP=acessar-o-dashboard-do-experimento a-tour-of-the-dashboard=conhecendo-o-dashboard h_01JZJ70K0QTGZ2V3T1TJ1VG08H=conhecendo-o-dashboard manage=gerenciar h_01JZ88Y5TQJCYQ2057RASHCP9D=gerenciar h_01HBB6EJ8T4RRKJY632180KZWM=Connections geo-design-policy=h_01_geo-design-policy geo-design-rule-types=tipos-de-regras-de-geodesign h_01KVA5SPC5PCR7BAK971PGHMCW=tipos-de-regras-de-geodesign set-up-a-geo-design-rule=configure-uma-regra-de-geodesign h_01KVA5SPC5X3VRK60AJ74TJFCS=configure-uma-regra-de-geodesign delete-a-geo-design-rule=exclua-uma-regra-de-geodesign h_01KVA5SPC54N4ECEMHJW2PV9K7=exclua-uma-regra-de-geodesign h_01KVA5SPC5GY7SVPT8BAFF1BPT=observa%C3%A7%C3%A3o-2 view-geo-design-rules-in-an-experiment=veja-as-regras-de-geodesign-em-um-experimento h_01KVA5SPC5K7M0AEYVGVCAMY4W=veja-as-regras-de-geodesign-em-um-experimento geo-design-policy-traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KVA5SPC61N9H7PEKYRX01M9Y=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01K2HQ7M74PGY2BC2X1KJ1F0Z4=Experiments status-column=coluna-de-status h_01K9VPG89HGV9BK8W94WC7WH8Q=coluna-de-status h_01K2HMD3QVJX9KYPQ7GS91KQ6Y=extend-experiment h_01JZ894VWK49JW8M97GMTC5JPX=stop-experiment traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es-1 h_01KAZQSWB0H9SM7W9PADRJ9B3N=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es-1 h_01KAZQQMBP5AHE8KQ5V71TCVAY=key-traits-and-limitations" />
