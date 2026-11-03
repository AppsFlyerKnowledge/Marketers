---
title: '[Beta] Visão geral do Agent Hub'
metadata:
  keywords:
    - Advertisers
    - Beta feature
    - Marketers
    - Agent Hub
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agent Hub
  created_at: '2025-11-16T10:18:23Z'
  edited_at: '2026-10-27T03:37:23Z'
  id: 40967933109649
  locale: pt
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/pt/articles/40967933109649
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** O Agent Hub é uma plataforma centralizada da AppsFlyer que permite a gestão de agentes de IA, oferecendo insights de marketing práticos diretamente no seu workflow. Esses agentes fazem uma análise constante dos seus dados para fornecer outputs úteis e recomendar ações, tudo dentro do ambiente colaborativo da sua equipe.

<Embed title="[Beta] Visão geral do Agent Hub" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LEuqdVEXBD0" providerUrl="https://www.youtube.com" />

## Sobre o Agent Hub

Cada agente assume uma tarefa de marketing de ponta a ponta: trabalha com seus dados, chega às próprias conclusões e as entrega onde sua equipe trabalha. O Agent Hub fornece acesso a diversos agentes criados pela AppsFlyer para ajudar a otimizar sua atividade de marketing e descobrir oportunidades de crescimento, além do Agente personalizado, que assume uma tarefa definida por você. Todo agente opera com integridade para dar suporte à tomada de decisões da sua equipe.

## Página do Agent Hub

A página do Agent Hub possui duas abas: **Meus agentes** e **Atividade**. Use-as para gerenciar agentes e revisar execuções que foram concluídas.

Use a aba **Meus agentes** para configurar, implementar e gerenciar agentes. Use a aba **Atividade** para revisar outputs, verificar execuções anteriores, fornecer feedback e analisar o raciocínio da execução com o AI Assistant.

<Accordion title="Meus agentes">

A aba **Meus agentes** mostra os agentes disponíveis para a sua conta.

Use essa aba para:

* Visualizar os agentes disponíveis.
* Configurar e implementar agentes.
* Gerenciar agentes implementados.
* Monitorar o status da última execução a partir do agent card.

#### Pré-requisitos e permissões

Alguns recursos do Agent Hub requerem configuração adicional, a depender do canal que você deseja utilizar para receber notificações.

##### Slack (opcional)

A configuração do Slack somente é necessária se você quiser receber outputs no Slack.

* Sua empresa precisa permitir o uso do aplicativo da AppsFlyer no Slack. Para isso:
  * Vá para o Agent Hub e selecione o agente que deseja usar.
  * Clique em **Conectar ao Slack** na configuração do agente.

Antes de configurar o agente, você deve criar um canal Slack dedicado dentro da sua empresa e convidar o aplicativo do Agent Hub para participar desse canal. Você deve informar o nome do canal para configurar o agente.

Para convidar o aplicativo para um canal:

1. No canal do Slack em que você deseja receber as notificações, digite: **/invite**
2. Escolha a opção de **adicionar um aplicativo ao canal.**

<Image alt="Opção de adicionar um aplicativo ao canal no canal do Slack - detalhes do menu" src="https://files.readme.io/6f4f06ff2a6871c38ab74347b05356b5482a859b3f40b02f01273abd3a10ee84-40967906089745.png" width="624px" />

Selecione **AppsFlyer Agent Hub** -> **Adicionar.**

<Image alt="Aplicativo AppsFlyer Agent Hub selecionado no diretório de apps do Slack com o botão Adicionar" src="https://files.readme.io/6290174c2950340f7766abb94f0080dbbcbd954cc44896a0f0ec1155fdd00524-40967906092049.png" width="624px" />

* As seguintes funções têm acesso total automático:
  * Administrador
  * Marketing manager
  * Gerente de equipe
  * Líder de marketing

* **Outras funções:** Exigem o recurso AI Tools habilitado por meio de <Anchor target="_blank" href="/marketers/pt/docs/user-management">Gestão de usuários</Anchor>.

##### E-mail (opcional)

* E-mails só podem ser enviados para endereços de e-mail que estão conectados a uma conta do AppsFlyer.
* Os usuários devem estar inscritos para receber notificações da AppsFlyer. Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/notifications#quais-notificações-posso-receber">aqui</Anchor>.

Atenção: Em cada agente, você pode configurar até 5 endereços de e-mail.

#### Configure um agente

Agentes podem ser configurados e implementados para funcionar com base em um cronograma ou manualmente. Você também pode configurar para onde o output do agente será enviado, como Slack ou e-mail.

Você pode monitorar o status da última execução diretamente a partir do agent card no Agent Hub. Para visualizar outputs concluídos e histórico de execuções, clique na aba **Atividade**.

Siga os passos abaixo para configurar e implementar um agente.

1. Faça login na AppsFlyer.
2. No menu à esquerda, acesse o **Agent Hub.**
3. No agente que você deseja configurar e implementar, clique em **implementar**.
4. Na página seguinte, defina as configurações necessárias do agente.
5. Adicione seu endereço de e-mail ou conecte seu workspace do Slack, se relevante.
   1. Certifique-se de que o canal do Slack foi configurado. [Veja os pré-requisitos](#pré-requisitos-e-permissões).
6. Selecione um cronograma de execução (atualmente baseado em UTC; fusos horários adicionais serão adicionados em breve).
7. Clique em **Implementar agente**.

O agente aparece em **Meus agentes**. Veja **Agentes predefinidos** e **Agente personalizado** abaixo para conferir a lista completa de agentes disponíveis e o que cada um faz.

</Accordion>

<Accordion title="Aba Atividade">

A aba **Atividade** mostra os outputs do agente após a conclusão de uma execução. Ela aparece quando pelo menos um agente concluiu outputs na sua conta.

Use essa aba para revisar a atividade recente do agente, visualizar outputs anteriores, fornecer feedback e fazer perguntas ao AI Assistant sobre uma execução específica.

A aba Atividade inclui duas seções:

| Seção | Descrição |
| --- | --- |
| Última atividade | Mostra a última execução concluída para cada instância do agente. |
| Execuções anteriores | Mostra execuções concluídas nos últimos 30 dias. |

Você pode filtrar a atividade por:

* Aplicativo
* Instância do agente

Atenção: o filtro de agente se baseia na instância específica do agente, não no tipo de agente.

#### Ver atividade de output

Para ver a atividade de output:

1. Vá para o **Agent Hub**.
2. Clique na aba **Atividade**.
3. Selecione os filtros de aplicativo ou instâncias relevantes.
4. Clique em uma execução para expandi-la.

A execução expandida mostra o mesmo output enviado por Slack ou e-mail.

A partir da execução expandida, você pode:

* Copiar o output.
* Avaliar o output como positivo ou negativo.
* Adicionar feedback por escrito.
* Clique em **Analisar atividade** para fazer perguntas sobre a execução ao AI Assistant.

#### Analise a atividade com o AI Assistant

Use **Analisar atividade** para fazer perguntas ao AI Assistant sobre uma execução específica que foi concluída.

O recurso **Analisar atividade** está disponível para todos os agentes. O AI Assistant abre no contexto da execução selecionada. Ele pode ajudá-lo a entender como o agente chegou ao output final, quais dados foram utilizados e quais fatores foram considerados ou descartados.

Isso não é um bate-papo geral com o agente. O AI Assistant responder apenas a perguntas sobre a execução selecionada. Ele não realiza novo trabalho do agente, não acessa dados fora da execução nem faz previsões.

Para fazer perguntas ao AI Assistant sobre uma execução:

1. Vá para o **Agent Hub**.
2. Clique na aba **Atividade**.
3. Clique em uma execução para expandi-la.
4. Clique em **Analisar atividade**.
5. Selecione uma pergunta sugerida ou digite sua própria pergunta.

Por exemplo, você pode digitar:

* Explique seu raciocínio.
* Em quais dados isso se baseou?
* Por que essa descoberta foi priorizada?
* Quais fatores o agente considerou?
* Quais fatores o agente descartou?

##### Perguntas possíveis

| Você pode perguntar sobre | Você não pode perguntar sobre |
| --- | --- |
| Como o agente chegou a um output | Dados que não foram incluídos na execução |
| Dados que o agente usou para a execução | Nova análise que não fazia parte da execução |
| Por que as descobertas foram priorizadas ou descartadas | Previsões futuras |
| O contexto e o raciocínio da execução selecionada | Recomendações gerais de otimização fora do contexto da execução |

#### Observações

Ao usar a aba **Atividade** e **Analisar atividade**, lembre-se:

* O AI Assistant deve estar ativado para a conta. Se o AI Assistant estiver desativado, **Analisar atividade** não estará disponível. Veja <Anchor target="_blank" href="/marketers/pt/docs/account-settings#agent-hub">configurações da conta</Anchor>.
* O histórico de atividades inclui execuções concluídas apenas nos últimos 30 dias.
* Excluir um agente também exclui sua atividade anterior, incluindo outputs, descobertas e dados de raciocínio. Essa ação não pode ser desfeita.
* O AI Assistant responder apenas a perguntas sobre a execução selecionada. Não realiza novas análises, não acessa dados fora da execução nem faz previsões.

</Accordion>

## Tipos de agentes

O Agent Hub inclui dois tipos de agentes: o agente personalizado, que você mesmo configura para um trabalho que define, e agentes prontos para uso, que você implementa como estão.

<div id="h_01M3PDTFQDFQNMHTWKP23JV1A8" />

<Accordion title="[Beta fechado] Agente personalizado">

Enquanto os agentes prontos para uso no Agent Hub executam tarefas específicas e predefinidas, o agente personalizado executa um trabalho que você adapta às suas necessidades específicas. Escreva a tarefa em linguagem simples, escolha o aplicativo, revise o plano elaborado pelo agente e defina como e quando você quer receber os resultados. O agente então faz o trabalho de ponta a ponta, sob demanda ou em uma programação, e envia o output para você.

Analisa os dados, executa a tarefa especificada e entrega os resultados solicitados. Pode ser uma lista ranqueada, um resumo semanal de performance, uma investigação de causa raiz, uma recomendação com as evidências por trás dela ou uma análise ad hoc complexa. O output assume o formato de que o trabalho precisa.

Você passa as instruções como passaria para um analista da sua equipe, e ele funciona da mesma forma: confirma o que entendeu, mostra como pretende abordar o trabalho e como define cada termo, e só executa depois que você concorda.

#### Criar um agente personalizado

Três etapas: definir o agente, revisar o plano e, depois, configurar e fazer o deploy.

##### Etapa 1: Definir o agente

1. No AppsFlyer, vá para **Agent Hub** no menu à esquerda.
2. No cartão do Agente personalizado, clique em **Criar**.
3. Em **Selecione seu aplicativo**, selecione o aplicativo. Um aplicativo por agente.
4. (Opcional) Defina os filtros de **Geo** e de **canal de mídia**. Deixe-os em branco para incluir tudo.
5. Em **Tarefa**, descreva a função ou clique em um prompt pronto para uso e edite-o conforme as suas necessidades.
6. Clique em **Gerar plano**.

##### Etapa 2: Revisar o plano do agente

O agente transforma sua tarefa em um plano e mostra para você antes de executar qualquer coisa. É aqui que você detecta uma tarefa mal interpretada ou uma definição que não corresponde à forma como sua equipe mede.

| Seção do plano | O que verificar |
| --- | --- |
| Objetivo | Reformulação do cargo em uma linha. |
| Plano do agente | Como o agente vai executar o trabalho. |
| Configurações | Todas as métricas, janelas e limites da sua tarefa, detalhados: o que significa "retenção no dia 7", o que significa "queda significativa" e quais canais de mídia estão no escopo. Edite tudo o que for diferente das suas próprias definições. |
| Classificar | O aplicativo, a geolocalização e o canal de mídia aos quais o agente será aplicado. |

A partir daqui:

* **Editar** altera qualquer campo; em seguida, clique em **Salvar alterações**.
* **Começar de novo** leva você de volta à tarefa.
* **Aceitar plano** leva você adiante.

##### Etapa 3: Configurar e implementar

1. Digite um **nome do agente**.
2. Em **Selecione como você quer receber os resultados**, selecione **Slack**, **E-mail** ou ambos.
   * Slack: clique em **Conectar ao Slack** se o espaço de trabalho ainda não estiver conectado e, em seguida, selecione o canal.
   * E-mail: até cinco endereços de usuários da AppsFlyer.
3. Em **Agendamento de execução**, selecione uma das opções.
4. Clique em **Implementar agente**.

Os agendamentos são executados em UTC.

O agente aparece em **Meus agentes**. O cartão mostra o status da execução mais recente. As execuções concluídas ficam em **Atividade** e podem ser filtradas por aplicativo e nome do agente.

<div id="h_01M3PDTFQESQY349XK0SNH5NB8" />

<Accordion title="Em quais dados o agente personalizado atua">

O agente personalizado tem duas fontes de dados, dados em nível de evento e dados agregados, e escolhe entre elas com base na tarefa; você não precisa especificar. Em algumas tarefas, o agente usa as duas fontes em uma única execução. Nesses casos raros, a mesma métrica pode mostrar valores ligeiramente diferentes entre as duas partes de uma execução. Para entender qual fonte o agente usou durante uma execução, explore o raciocínio do agente usando o recurso **Analisar atividade**.

**Dados de nível de evento.** Eventos brutos em todo o funil, do engajamento à atividade no aplicativo. É isso que diferencia o agente personalizado de um dashboard: você pode definir suas próprias métricas e proporções, trabalhar no nível do usuário individual e rastrear sequências de eventos.

| Incluso | Atenção |
| --- | --- |
| Engajamentos | Cliques e Impressões |
| Instalações e reengajamentos | Conversões |
| Sessions | Eventos de abertura do aplicativo |
| https://support.appsflyer.com/hc/article_attachments/19284078965009 | Incluindo a receita de compras in-app |
| Dados | Canal de mídia, campanha, geo até o nível de cidade, dispositivo, versão do sistema operacional, versão do aplicativo, anúncio, ID do site e outros campos de eventos brutos |
| Período dos dados | Últimos 30 dias |

**Dados de atividade e de cohort (agregados).** Todos os pontos de dados disponíveis no My Dashboards, incluindo custo.

| Incluso | Atenção |
| --- | --- |
| Metrics | Instalações, conversões, primeiras visitas, sessões, contagem de eventos, usuários únicos, usuários ativos, receita, receita líquida, receita média por usuário (ARPU), receita por usuário único, contagem por usuário único, taxa de retenção |
| Eventos in-app, conversões, desinstalações, sessões | Contagem, usuários únicos, receita, receita líquida, contagem do primeiro evento |
| Métricas de custo | Gasto (custo), eCPI, ROAS, ROI |
| Dados | Canal de mídia, canal, ID e nome da campanha, Ad set ID e nome, ID e nome do anúncio, ID do site, agência, palavras-chave, sub\_param\_1, categoria e tipo de engajamento e destino, App ID unificado, plataforma, loja de aplicativos da instalação, versão do aplicativo e versão do sistema operacional e código do país (conversão), tipo de evento agregado (conversão, sessão, in-app, desinstalação), nome do evento, nome e tipo da conversão, tipo de monetização, is-attributed, is-organic, is-primary-attribution, data do evento (somente cohort), data do evento (conversão), dias após a conversão, moeda do cliente |
| Período dos dados | Três anos para atividade, dois anos para cohort |

Os dados agregados estão em USD e na moeda da sua conta. Os dados agregados de cohort têm granularidade diária.

**Limitações atuais.** Essas limitações são temporárias e vão evoluir à medida que o agente personalizado sair da beta.

* Engajamento e custo ficam em fontes diferentes. Cliques e impressões existem apenas nos dados em nível de evento; custo existe apenas nos dados agregados. O agente não consegue unir os dois, então métricas que os combinam, como CPC, CPM, CTR, IPM e CPA, não retornam resultados. As métricas baseadas em custo que não precisam de dados de engajamento (gasto, eCPI, ROAS, ROI) funcionam como esperado.
* Dados ausentes: dados gerados por Audiences, SKAdNetwork, SSOT, Protect360, Creative e incrementalidade; receita de anúncios e receita de assinaturas (a receita cobre apenas compras in-app).
* Métricas ou dimensões personalizadas que você definiu nos seus dashboards não estão incluídas.
* As dimensões agregadas incluem dados apenas a partir de junho de 2025 para plataforma, sub\_param\_1, destino de engajamento, tipo de engajamento e fonte (orgânico vs. não orgânico).
* Quando não há dados, o agente mostra 0, não N/A.
* "Primeiras visitas" e "revisitas" estão disponíveis apenas para aplicativos web.

> 📘 **Importante!**
>
> Pode haver discrepâncias entre os números brutos de eventos e os dados do dashboard. Os números no nível do evento (dados brutos) e os números agregados (dashboard) nem sempre vão corresponder; pequenas diferenças entre os dois são esperadas. Os números agregados devem corresponder aos do My Dashboards para o mesmo aplicativo e as mesmas datas.

</Accordion>

<div id="h_01M3PDTFQEF8ZPV4PP04YGNGBK" />

<Accordion title="Escreva uma boa tarefa">

A qualidade do plano que o agente cria depende da qualidade do briefing. Inclua o máximo possível do que se aplicar:

1. **O trabalho.** O que você quer que seja feito, em linguagem simples. Verbos ajudam: comparar, classificar, sinalizar, encontrar, recomendar, resumir.
2. **Período.** Uma janela definida, por exemplo, "a última semana completa" ou "os últimos 14 dias versus os 14 anteriores". Deixe hoje de fora; os dados dele ainda estão parciais.
3. **Escopo.** A geolocalização, o canal de mídia, a campanha ou a plataforma que importam. Você também pode definir geolocalização e canal de mídia como filtros acima da caixa de tarefa.
4. **Métricas e limites.** Nomeie seus KPIs e como você os define. "Uma queda de mais de 10% em relação à semana anterior conta como significativa" dá ao agente uma regra que ele pode aplicar.
5. **Output que você deseja.** Se for importante, diga: "uma tabela ordenada por gasto", "um breve resumo com as três principais conclusões" ou "apenas sinalização, sem narrativa".
6. **Por quê.** Uma linha de contexto ajuda o agente a decidir o que priorizar.

Consulte **Pré-requisitos e permissões** acima para ver os detalhes de configuração.

</Accordion>

<div id="h_01M3PDTFQE6GP95M541FYHG15N" />

<Accordion title="Revisar e refinar uma execução">

Execuções concluídas aparecem em **Atividade** com o mesmo conteúdo enviado para o Slack ou por e-mail. Em uma execução, você pode copiar o output, dar um joinha para cima ou para baixo, adicionar feedback por escrito e abrir [Analisar atividade](#analise-a-atividade-com-o-ai-assistant) para perguntar ao AI Assistant como o agente chegou ao resultado.

Se uma execução voltar vazia ou fora do esperado, leia o raciocínio antes de mudar a tarefa. Em [Analisar atividade](#analise-a-atividade-com-o-ai-assistant), pergunte quais dados o agente usou, por que chegou a esse resultado e o que mudar no plano. Reescrever a tarefa no escuro normalmente produz uma resposta errada diferente. Depois, edite o plano ou a tarefa e execute o agente novamente.

Se o raciocínio também voltar vazio, talvez você tenha solicitado dados que ainda não existem. Consulte **Limitações** acima, revise o prompt e tente novamente.

> 📘 **Importante!**
>
> Você não pode voltar ao prompt original depois de salvar e implantar um agente. Você só pode editar o plano aprovado do agente.

Consulte a [página do Agent Hub](#página-do-agent-hub) e [Analisar atividade com o AI Assistant](#analise-a-atividade-com-o-ai-assistant) acima para ver mais detalhes.

</Accordion>

<div id="h_01M3PDTFQE2XA949N4GPBSHVKY" />

<Accordion title="Gerenciar um agente personalizado">

No cartão do agente em **Meus agentes**, você pode executar o agente agora, editar a configuração dele (nome, entrega, agendamento) ou excluí-lo.

Excluir um agente também exclui seu histórico, incluindo outputs e raciocínio. Essa ação não pode ser desfeita.

</Accordion>

<div id="h_01M3PDTFQEENY4TB2QY7M1MPN9" />

<Accordion title="É bom saber">

* Um aplicativo por agente. Crie um agente separado para cada aplicativo.
* A atividade mantém as execuções dos últimos 30 dias.

</Accordion>

</Accordion>

<div id="h_01M3PDTFQEDCZ7AJFC1FCTHERZ" />

<Accordion title="Agentes prontos para uso">

Agentes prontos para uso já estão prontos para implantação como estão: escolha um, configure-o e deixe que ele seja executado nos seus dados. A tabela abaixo traz um resumo do que cada agente faz. Expanda uma seção para ver os detalhes completos antes de implementar.

<div id="h_01M3PDTFQET68PRA9CN49CQ8Q7" />

<Accordion title="Identificar oportunidades criativas">

**Função.** Encontra os criativos com melhor performance para você e mostra onde eles ainda não estão em execução. O agente avalia a performance dos criativos em todos os seus parceiros nos últimos 30 dias, classifica os vencedores e, em seguida, verifica cada parceiro para ver quais desses vencedores estão ausentes. Você recebe uma lista de posicionamentos específicos para adicionar, com os números por trás de cada um.

**No que funciona.** Gasto e ROAS no nível do criativo entre parceiros nos últimos 30 dias. Requer otimização de criativos.

**O que uma execução entrega.** Criativos com melhor performance, com gasto e ROAS, além de, para cada parceiro, quais desses criativos não estão atualmente em execução e o motivo para adicioná-los. Entregue no Slack ou por e-mail.

**Frequência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQE2WB2SNWBCS81C2DE" />

<Accordion title="Resumos executivos personalizados">

**Função.** Escreve a atualização de performance que, de outra forma, você montaria manualmente para gerentes e stakeholders. O agente lê seus dados de analytics agregados, identifica as tendências, os destaques e as mudanças relevantes do período e transforma tudo em um resumo com recomendações, pronto para encaminhar.

**No que funciona.** Dados de analytics agregados em todos os seus aplicativos e canais de mídia. Nenhuma assinatura premium é necessária.

**O que uma execução entrega.** Um resumo por escrito: tendências principais, destaques e piores desempenhos, mudanças relevantes e próximas etapas recomendadas. Entregue no Slack ou por e-mail.

**Frequência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQEB9MKH44X5XX4AGDT" />

<Accordion title="Análise de Deep Research">

**Função.** Executa uma análise semanal do que mudou e por quê. Toda segunda-feira, o agente compara as duas semanas completas mais recentes (de segunda a domingo) e analisa dados brutos no nível do evento, entre parceiros, geolocalizações, versões de sistema operacional e versões de SDK, para encontrar mudanças que os dashboards agregados não conseguem mostrar, incluindo problemas de configuração que parecem mudanças de performance.

**No que funciona.** Dados brutos e consolidados no nível do evento. O agente exclui deliberadamente a semana atual para evitar dados parciais ou ainda não consolidados. Por exemplo, na segunda-feira, 26 de janeiro, ele compara 12 a 18 de janeiro com 5 a 11 de janeiro. Nenhuma assinatura premium é necessária.

**O que uma execução oferece.** Um relatório escrito sobre mudanças relevantes de uma semana para outra, o que as impulsiona e os problemas de configuração identificados ao longo do caminho. Entregue no Slack ou por e-mail.

**Cadência.** Semanalmente, às segundas-feiras ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQEPFMS38RWXT923VX7" />

<Accordion title="Detectar anomalias de performance">

**Tarefa.** Monitora seus principais KPIs todos os dias e avisa quando algo muda sem que devesse. O agente compara cada métrica à sua faixa esperada, sinaliza anomalias positivas ou negativas significativas e explica o que mudou e onde: um pico de CPI em um parceiro, uma queda de IPM em uma geo ou uma campanha que caiu vertiginosamente.

**No que atua.** Dados diários de KPI em parceiros, campanhas e geos. Não requer assinatura premium.

**O que uma execução oferece.** Alertas em estilo de história: qual métrica mudou, quanto mudou, em qual parceiro, campanha ou geo, e o motivo mais provável. Entregue no Slack ou por e-mail.

**Cadência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQEFHYR29GN1XMRM16N" />

<Accordion title="Detectar problemas de configuração">

**Tarefa.** Audita sua configuração de mensuração e alerta sobre lacunas que degradam silenciosamente a qualidade dos dados. O agente verifica integrações inativas no SKAdNetwork e em custo, atribuição de view-through desativada via modelo probabilístico e outros problemas de configuração, para que você os identifique antes que distorçam a leitura de uma campanha.

**No que atua.** Status de integração e configuração em seus aplicativos e parceiros. Não requer assinatura premium.

**O que uma execução oferece.** Alertas com cada problema encontrado, onde ele está e como corrigi-lo. Entregue no Slack ou por e-mail.

**Cadência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQEP6E7D4TF5G4PX1KV" />

<Accordion title="Monitorar lançamentos de aplicativos">

**Tarefa.** Mantém você por dentro dos lançamentos do seu próprio aplicativo sem precisar esperar pela equipe de desenvolvimento. O agente monitora os lançamentos nas lojas de aplicativos do iOS e Android, avisa quando uma versão entra no ar, acompanha o progresso da distribuição e destaca as mudanças relevantes para marketing: novos recursos, mudanças no comportamento in-app e eventos adicionados ou removidos. Assim, você pode alinhar as campanhas de UA com o que realmente está no aplicativo.

**Em que atua.** Dados de lançamento na loja de aplicativos e definições de eventos in-app dos seus aplicativos. Não requer assinatura premium.

**O que uma execução fornece.** Alertas de lançamento com versão, status de rollout e um resumo das mudanças relevantes para marketing. Entregue no Slack ou por e-mail.

**Frequência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M3PDTFQEEKJQTRKEC9GK4TE6" />

<Accordion title="Otimizar estratégia anti-fraudes (Protect360)">

**Tarefa.** Busca sinais iniciais de fraude no seu tráfego e mostra o que fazer a respeito. O agente analisa seus dados do Protect360 em busca de padrões emergentes, reporta as principais descobertas e recomenda ações que reduzem a exposição à fraude sem comprometer a performance.

**Em que atua.** Dados do Protect360. Requer o Protect360 e os recursos da versão beta fechada do Protect360.

**O que uma execução fornece.** Descobertas e recomendações no dashboard do Protect360.

**Frequência.** Semanalmente, às segundas-feiras ou sob demanda.

</Accordion>

<div id="h_01M57AQ8G83P5H1JDJ4FM9ETCV" />

<Accordion title="Mensurar a incrementalidade de UA">

**Tarefa.** O agente **Mensurar a incrementalidade de UA** orienta você por todo o ciclo de vida dos testes de incrementalidade, para que você não precise ser especialista para executá-los. Ele define o que testar, explica o que os resultados do seu experimento significam e recomenda ações de marketing concretas — transformando uma curva de aprendizado íngreme e especializada em um fluxo de trabalho guiado para mensurar o impacto causal do seu gasto com UA paga: quais instalações ou eventos aconteceram por causa dos seus anúncios, em comparação com o Growth que você teria capturado de qualquer forma.

**No que atua.** Instalações, eventos in-app, receita e dados de custo dos últimos 90 dias; todos os dados de experimento de incrementalidade para UA.

**O que uma execução entrega.** Um relatório estruturado em três partes: (1) seu estado atual de UA e a análise de experimentos ativos ou concluídos, (2) um plano sequencial de testes que define o que testar em seguida e por que isso importa para o seu orçamento e (3) ações de marketing recomendadas — aumentar, manter, cortar ou testar novamente.

**Cadência.** É executado conforme uma programação, semanalmente por padrão. Você pode aumentar a frequência para até diariamente ou acioná-lo ad hoc para ter uma leitura atualizada sempre que precisar.

**Configurar.** Exige uma assinatura premium do produto incrementalidade para UA. Inicie o agente no Agent Hub e selecione um aplicativo, país e métrica de sucesso; em seguida, defina a cadência (ou execute ad hoc). O agente herda qualquer política de design geo existente de incrementalidade para UA.

**É bom saber.** O agente recomenda — ele nunca move orçamento nem inicia um experimento por conta própria; você aprova e age. Os agentes são específicos por aplicativo, país e evento. Por exemplo, seus aplicativos Android e iOS exigiriam dois agentes separados. Como acontece com qualquer output de IA, sempre valide antes de agir.

</Accordion>

<div id="h_01M3PDTFQEP2RQW39AD8127J19" />

<Accordion title="Verificação da integridade da web">

**Função.** Audita como seu aplicativo web coleta eventos e atribui conversões a fontes de marketing. O relatório mostra o que está funcionando, sinaliza problemas que podem tornar a atribuição imprecisa e recomenda melhorias para a sua implementação.

**No que atua.** As configurações de atribuição do aplicativo web selecionado e os dados recentes de SDK ou server-to-server. As verificações cobrem coleta de dados, eventos e receita, links de campanha, referrers, identidade e configuração entre plataformas. A janela de análise padrão é de sete dias.

**O que cada execução entrega.** Um relatório com duas seções: o que foi verificado e está em ordem, e as melhorias recomendadas. As descobertas incluem números de suporte, uma correção recomendada e um status verde, amarelo ou vermelho com base no impacto.

**Cadência.** Configurável pelas opções padrão de agendamento ou sob demanda.

</Accordion>

<div id="h_01M5VP47MCYYQVP89CJN9KZ4BP" />

<Accordion title="[Beta fechada] Otimize a parcela de voz dos anúncios da Apple">

**Trabalho.** Mantém a sua parcela de voz (SoV) dos anúncios da Apple nas suas palavras-chave principais dentro da faixa que você definiu, sem pagar a mais. SoV, também chamada de parcela de impressões, é a porcentagem de pesquisas qualificadas para uma palavra-chave em que o seu anúncio apareceu. Quando uma palavra-chave sai da meta, o agente recomenda uma mudança de lance: aumentar o lance máximo de custo por toque (CPT máx.) para recuperar participação ou reduzi-lo para parar de pagar a mais.

**Como o agente verifica seu SoV.** A Apple divulga o SoV com um dia de atraso, mas o leilão muda ao longo do dia. Para fechar essa lacuna, o agente estima seu SoV a cada hora com base nos dados de veiculação de hoje. Ele calibra a estimativa em relação ao SoV oficial da Apple do dia anterior. Você fica sabendo das mudanças em poucas horas.

**Em que ele atua.** Dados horários dos anúncios da Apple no nível da palavra-chave (impressões, toques, gasto e lance máximo de CPT atual) e o relatório diário de parcela de impressões da Apple. O agente coleta ambos pela sua conexão com os anúncios da Apple em **Configurações de custo** e usa os últimos 30 dias como histórico. Requer ROI360.

**O que uma execução entrega.** Para cada palavra-chave e geolocalização fora da faixa-alvo, uma execução entrega:

* A faixa de SoV mais recente da Apple e se a palavra-chave está acima ou abaixo da meta.
* A mudança de lance recomendada em %.
* O lance máximo de CPT exato, atual e recomendado, para cada campanha e grupo de anúncios em que a palavra-chave é veiculada.

As palavras-chave que estão dentro da meta ou ainda não têm recomendação aparecem no final. Enviado para o Slack ou por e-mail, e para a guia **Atividade**.

**Aplicar uma recomendação.** Na guia **Atividade**, cada mudança de lance aparece como um cartão. Clique em **Aplicar** para enviar o lance recomendado ao Apple Ads, edite o lance e depois clique em **Aplicar** ou clique em **Rejeitar**. Nada muda no Apple Ads até você aplicar uma recomendação.

**Cadência.** As opções de agendamento de execução são:

* **No acionamento:** O agente envia uma mensagem apenas quando há uma recomendação nova ou alterada. A frequência da verificação depende de como o agente verifica sua SoV. Consulte **Como o agente verifica sua SoV** nesta seção.
* **Sem agendamento:** O agente é executado apenas quando você o executa manualmente.

**Configurar. Para implementar o agente:**

1. Em **Configurações de custo**, conecte o Apple Ads com a conta que executa suas palavras-chave.

   > 📘 **Importante!**
   >
   > Conecte o Apple Ads com permissões de **Leitura & gravação** e uma conta que não seja de agência. Read & Write permite aplicar alterações de bids diretamente no Agent Hub. Com acesso de somente leitura, você recebe recomendações, mas não pode aplicá-las. Você precisa alterar os bids manualmente no Apple Ads.

2. No **Agent Hub**, no card **Otimizar Share of Voice do Apple Ads**, clique em **Implementar agente**.
3. Digite um **Nome do agente** ou mantenha o nome preenchido automaticamente.
4. Em **Selecione seu aplicativo iOS**, selecione o aplicativo. Um aplicativo por agente.
5. Em **Palavras-chave**, insira pelo menos uma e no máximo três palavras-chave, conforme configuradas nas suas campanhas do Apple Ads.
6. Em **Geo do Apple Ads**, selecione até cinco geolocalizações.
7. Em **Faixa de Share of Voice alvo**, selecione a faixa, por exemplo, 81-90%.
8. Em **Selecione como você quer receber os resultados**, selecione **Slack**, **E-mail** ou ambos.
9. Em **Agendamento de execução**, selecione **No acionamento** ou **Sem agendamento**.
10. Clique em **Implementar agente**.

**Ainda não há recomendação.** Uma palavra-chave e uma geo podem mostrar esse status em dois casos:

* Não há dados suficientes. Por exemplo, a palavra-chave tem baixo volume de pesquisa e a Apple não reporta a SoV para ela, ou a palavra-chave não é executada nessa geolocalização.
* O lance mudou recentemente. O agente espera para ver o efeito da mudança antes de recomendar novamente.

**Limitações.** Lembre-se destas limitações:

* **A primeira execução acontece no dia seguinte.** Depois que você implementa um novo agente, ele preenche retroativamente 30 dias de histórico na manhã seguinte (UTC). O agente só começa a ser executado depois que o preenchimento retroativo é concluído.
* **Conexão do Apple Ads.** A conexão do Apple Ads em **Configurações de custo** deve ser de uma conta que não seja uma agência. Para aplicar alterações de bid, são necessárias permissões de leitura & gravação.
* **O bidding automatizado não é compatível.** Se uma campanha usar bidding automatizado no Apple Ads, as palavras-chave dela não terão um bid máximo manual de CPT. O agente não pode recomendar nem aplicar uma alteração de bid para elas.
* **Use campanhas com uma única geolocalização.** O Apple Ads define um bid por palavra-chave por grupo de anúncios, para todos os países segmentados pela campanha. Se uma campanha segmentar vários países, uma alteração de bid para uma geolocalização também a altera para os outros. A recomendação pode não ser precisa.
* **Escopo por agente.** Um aplicativo, até três palavras-chave e até cinco geolocalizações. Crie mais agentes para mais palavras-chave ou geolocalizações.

**Bom saber.** O agente nunca altera um bid por conta própria. Você aprova cada alteração. Como acontece com qualquer output de IA, valide as recomendações antes de aplicá-las.

</Accordion>

</Accordion>

<Accordion title="Posso criar meus próprios agentes?">

Sim. O agente personalizado permite que você defina a tarefa que quer realizar. Veja **Agente Personalizado** acima.

</Accordion>

<Accordion title="O Agent Hub está disponível para todos os tipos de conta?">

Sem. Atualmente, o Agent Hub está disponível apenas para anunciantes.

</Accordion>

<Accordion title="Todos os agentes estão disponíveis para todos?">

A disponibilidade dos agentes varia com base na sua assinatura da AppsFlyer e no acesso a produtos premium. Entre em contato com seu CSM para detalhes específicos.

</Accordion>

<Accordion title="Administradores podem desativar o Agent Hub de uma conta?">

sim, Os administradores podem gerenciar a disponibilidade do Agent Hub em **Configurações da conta > Recursos de IA**.

Por padrão, o Agent Hub fica disponível para a conta.

Se um administrador desativá-lo:

* Todos os usuários perdem acesso ao Agent Hub.
* Todos os agentes existentes são excluídos permanentemente e não podem ser restaurados.
* Qualquer agente ativo é interrompido.

Se um administrador ativar o Agent Hub novamente mais tarde, os usuários poderão acessá-lo novamente, mas deverão criar e implementar agentes do zero.

Consulte <Anchor target="_blank" href="/marketers/pt/docs/account-settings#agent-hub">Configurações da conta</Anchor> para mais informações.

</Accordion>

<Accordion title="Onde posso receber notificações?">

Você pode receber notificações por e-mail ou Slack. As notificações por e-mail exigem que você esteja inscrito para receber notificações de recursos de IA na Central de notificações.

</Accordion>

<Accordion title="Por que não estou recebendo notificações por e-mail?">

Se você concluiu os pré-requisitos para notificações por e-mail, mas ainda não recebe e-mails do Agent Hub, talvez você já tenha cancelado anteriormente o recebimento de e-mails da AppsFlyer. Entre em contato com o nosso suporte para assistência.

</Accordion>

<Accordion title="A AppsFlyer treina modelos de IA nos meus dados?">

Sem. A AppsFlyer não usa seus dados para treinar nenhum modelo de IA. A IA pode produzir resultados imprecisos ou incompletos, por isso reveja os outputs antes de agir com base neles.

</Accordion>

<div data-zendesk-anchors="about-agent-hub=sobre-o-agent-hub h_01KA62R2NX6YEFMVG0SN0Y7NQ9=sobre-o-agent-hub agent-hub-page=p%C3%A1gina-do-agent-hub h_01KQF6P3ED1KB47THJP8J3KAE5=p%C3%A1gina-do-agent-hub prerequisites-and-permissions=pr%C3%A9-requisitos-e-permiss%C3%B5es h_01KQF8YAEDQW52YMK3W4FE2KE1=pr%C3%A9-requisitos-e-permiss%C3%B5es h_01KQF8H9A6FPB3VVBWAAXM257W=slack-opcional h_01KQF8HEEMRBFK1K54VH2YDPSC=e-mail-opcional set-up-an-agent=configure-um-agente h_01KQF8T91KTZ01YKJD8JT6G0ZJ=configure-um-agente view-activity-output=ver-atividade-de-output h_01KQF6P3EJMJDMF0BWWXQA091K=ver-atividade-de-output analyze-activity-with-ai-assistant=analise-a-atividade-com-o-ai-assistant h_01KQF6P3EMCX0HQKPVQ89S9VGF=analise-a-atividade-com-o-ai-assistant h_01KQF6P3EPWHV7J742F3S4Q0GY=perguntas-poss%C3%ADveis notes=observa%C3%A7%C3%B5es h_01KQF7NTQYDGA17KCCMTNYY72H=observa%C3%A7%C3%B5es agent-types=tipos-de-agentes h_01M3PDTFQDAEVRHJYK4ZJXQ3DH=tipos-de-agentes create-a-custom-agent=criar-um-agente-personalizado h_01M3PDTFQEJA8GAE579P1AZG0E=criar-um-agente-personalizado step-1-define-the-agent=etapa-1-definir-o-agente h_01M3PDTFQECPBKDEXMQMPZJTCS=etapa-1-definir-o-agente step-2-review-the-agent-plan=etapa-2-revisar-o-plano-do-agente h_01M3PDTFQEF9QCN15FKMRST3GW=etapa-2-revisar-o-plano-do-agente step-3-configure-and-deploy=etapa-3-configurar-e-implementar h_01M3PDTFQE7FN9GPTJ5GEKSNVG=etapa-3-configurar-e-implementar h_01M3PDTFQEZJGPZ0AY4ZWRDR8D=importante h_01M3PDTFQENS64JZYT2Y56QMXQ=importante-1 h_01M5VP47MCS7HM339EW9AT6NGG=importante-2" />
