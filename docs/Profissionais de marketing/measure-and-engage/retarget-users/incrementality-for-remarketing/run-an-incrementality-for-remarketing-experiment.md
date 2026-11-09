---
title: Execute uma experiência de Incrementalidade
metadata:
  keywords:
    - Advertisers
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
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2026-08-19T00:35:38Z'
  id: 360014225577
  locale: pt
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/pt/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Realize uma experiência de Incrementalidade para compreender o verdadeiro impacto das suas campanhas de remarketing.

<Image align="center" alt="KB_toggle_final. jpg" src="https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg" />

<div id="about-the-experiment" />

## Sobre a experiência

O teste de <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">Incrementalidade</Anchor> mede o impacto real das suas campanhas através de testes A/B que avaliam com precisão o “aumento incremental” – a diferença entre as conversões que ocorreram devido às suas campanhas de remarketing e aquelas que teriam ocorrido de qualquer forma.

Os resultados são fundamentais para compreender o valor efetivo gerado pelos seus investimentos em marketing. Com os testes de Incrementalidade, é possível ver objetivamente o impacto de canais e campanhas específicos, permitindo tomar decisões mais acertadas sobre a alocação de orçamento e otimização de campanhas.

A AppsFlyer simplifica os testes de Incrementalidade com um processo automatizado que começa na criação da audiência. O novo público é automaticamente dividido entre parceiros de mídia conectados e um grupo de controlo, através do ativar alternado “Medir impacto incremental”. O grupo de controlo é essencial nos testes, consistindo na parte do público que é mantida afastada dos parceiros. Uma vez guardada a audiência, uma experiência de Incrementalidade é criada automaticamente. Depois de lançar as suas campanhas com os parceiros e assegurar-se de que as campanhas corretas estão ligadas, poderá ver os resultados da experiência no painel de Incrementalidade.

<div id="get-started" />

## Iniciar

Incrementalidade é um recurso premium. Siga estes passos para iniciar o teste de Incrementalidade. Para mais detalhes sobre cada etapa, veja [Configurar a experiência](/docs/run-an-incrementality-for-remarketing-experiment#configurar-o-experimento) abaixo.

|  | Etapas |
| --- | --- |
| 1 | [**Conheça os objetivos do seu teste**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />Maximize o potencial dos resultados da sua experiência definindo objetivos claros e uma hipótese para o resultado. |
| 2 | [**Criar o público-alvo e dividir grupos**](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)<br /><br />Em <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Públicos-alvo</Anchor>:<ul><li>Configure a audiência.</li><li>Ligue-a às redes de anúncios.</li><li>O público é dividido em grupos de teste e de controlo automaticamente, através de uma opção ativada (para subscritores de Incrementalidade, em públicos criados após 11 de janeiro de 2023).O AppsFlyer Audiences envia membros do grupo de teste para redes de anúncios e retém os do grupo de controlo.</li></ul> |
| 3 | [**Lançar a campanha e a experiência**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>Nas redes de anúncios, crie e lance uma campanha que tem como alvo os utilizadores do público.</li><li>O experimento de Incrementalidade é criado automaticamente (para subscritores do Incrementalidade).</li></ul>Os membros do grupo de teste são expostos a anúncios. O grupo de controlo não é exposto. |
| 4 | [**Analise os resultados**](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)<ul><li>A análise de incrementalidade é apresentada no <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#dashboard-de-incrementalidade">painel de incrementalidade</Anchor>.</li><li>Os dados em nível de linha estão disponíveis nos <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#relatórios-de-dados-brutos">relatórios de dados brutos de incrementalidade</Anchor> (através do Data Locker).</li></ul>Os conhecimentos obtidos através de experiências de incrementalidade bem conduzidas permitem otimizar as suas campanhas de marketing para alcançar o máximo impacto positivo. Por exemplo, pode ajudá-lo a identificar a melhor mensagem para um público-alvo, o melhor material criativo ou promoção, a fonte de mídia mais eficaz, entre outros. |

<div id="set-up-the-experiment" />

## Configurar o experimento

<div id="know-your-test-objectives" />

<Accordion title="Conheça os objetivos do teste">

Como em qualquer experimento, é fundamental definir exata e claramente o que está a testar (variáveis) e qual o resultado esperado (a hipótese). A tabela a seguir fornece diretrizes e práticas recomendadas para desenhar o seu experimento:

| Variáveis/Hipótese | Diretrizes e melhores práticas |
| --- | --- |
| Público | Descreva o público que pretende testar. Escolha um público já configurado no AppsFlyer Audiences ou crie um novo que satisfaça os seus critérios de teste. |
| Tamanho do público | Selecione um público com uma grande base de utilizadores e um evento com altas taxas de conversão. É mais provável que um tamanho amostral grande resulte em <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#statistical-significance">resultados estatisticamente significativos</Anchor>.<br /><br />**Prática recomendada:** Um público de pelo menos 50.000 utilizadores, distribuídos entre 1 a 3 redes de anúncios + o grupo de controlo. |
| Campanha | Descreva a campanha (mensagens, incentivos, etc.). |
| Percentagem do grupo de controlo | O grupo de controlo é automaticamente estipulado para 15% do tamanho do público (a prática recomendada varia entre 15% e 25%). |
| Grupo de teste | Determine as redes de anúncios que deseja testar. A percentagem de divisão é repartida igualmente entre elas (mas pode ajustar a percentagem de público que será direcionada para cada uma).<br /><br />**Prática recomendada:** 1 a 3 redes de anúncios |
| Hipótese | Defina o resultado esperado da experiência.<br /><br />Pode parecer contraintuitivo prever o resultado antes de começar, mas formular uma hipótese é vital para o desenho experimental; é isso que o ajuda a interpretar os resultados.<br /><br />**Prática recomendada:** Formule uma hipótese que seja facilmente testável usando percentagens reais, em vez de estimativas vagas. Por exemplo:<ul><li>***15% mais utilizadores comprarão um upgrade*** é uma hipótese que se pode testar facilmente.</li><li>***Um número significativamente maior de utilizadores comprará um upgrade*** é mais difícil de testar.</li></ul> |

<div id="example" />

> 📄 **Exemplo**
>
> Com base nas orientações acima, poderá definir uma experiência semelhante à seguinte.
>
>
>
> | Variáveis/Hipótese | Exemplo |
> | --- | --- |
> | Público | Utilizadores que concluíram o registo mas não efetuaram uma compra |
> | Tamanho do público | 100.000 |
> | Campanha | Uma campanha que oferece um vale de desconto a utilizadores que façam uma compra num determinado período |
> | Percentagem do grupo de controlo | 15% do tamanho do público-alvo |
> | Grupo de teste | Envie o restante público para:<br /><br />* Rede A (42% do público)<br />* Rede B (43% do público) |
> | Hipótese | A taxa de utilizadores do grupo de teste que interagem com a campanha de remarketing e fazem uma compra será 10% superior à dos utilizadores do grupo de controlo. |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="Crie o público-alvo e divida os grupos">

Depois de definir os objetivos, o próximo passo é configurar o público a testar:

1. No AppsFlyer Audiences, <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#criar-e-gerenciar-audiências">crie um público</Anchor> (ou divida um público existente que satisfaça os requisitos do seu design experimental).
2. No separador **Conectar** do público selecionado:
   * Conecte o público a 1 a 3 parceiros de rede de anúncios.
   * Certifique-se que a opção que <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#audience-split-and-control-groups">divide o público</Anchor> está ativada (é **ativada automaticamente para subscritores de Incrementalidade, em públicos criados após 11 de janeiro de 2023**). Caso contrário, clique no botão para ativá-la.  
      Caso contrário, clique no botão de alternância para ativá-lo.  
     <Image align="center" alt="Measure_inc_impact_toggle.jpg" src="https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg" />
   * O grupo de controlo é automaticamente definido para 15% (recomendado).
   * O restante público é dividido igualmente entre os parceiros de rede de anúncios selecionados.
     * A percentagem total de divisão deve somar 100% (incluindo o grupo de controlo).

Após guardar o público com a divisão ativada, será automaticamente lançada uma experiência de Incrementalidade (apenas para subscritores de Incrementalidade). Estas experiências podem ser visualizadas no painel Incrementality com o prefixo "[Auto]" antes do título.

<Image align="center" alt="Auto_before_title.jpg" src="https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg" />

**Notas Importantes:**

* Enquanto a experiência estiver a decorrer, evite fazer alterações na configuração do público. Alterações nos parceiros, nome do público ou outras definições podem gerar análises estatísticas imprecisas.  
  **Prática recomendada:** Mesmo após o fim de uma experiência, se precisar alterar a definição de um público já testado, duplique primeiro o público e faça as alterações na nova cópia. Isto assegura a integridade contínua dos dados históricos no painel Incrementality.
* Modificar a configuração de divisão e parceiro de um público existente encerrará o experimento de incrementalidade atual e iniciará um novo.
* #### <span id="check-for-audience-expansion-features"></span>Verifique as funcionalidades de expansão de público:

Tanto os anúncios do Meta como os do Google Ads possuem uma funcionalidade opcional que permite que as campanhas alcancem além de uma lista de público-alvo configurada para expandir o seu alcance. Se esta funcionalidade estiver ativada, influenciará os experimentos de incrementalidade e poderá gerar resultados imprecisos. **Por favor, verifique se esta função está desativada.**

Nos anúncios Meta, a funcionalidade chama-se “Público-alvo personalizado com vantagem”. Esta aparece ao nível do conjunto de anúncios e vem ativada por predefinição.

<Image align="center" alt="imagem__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />
No Google Ads, designa-se “Expansão de público-alvo”.

<Image align="center" alt="Google_Ads_Incrementality_limitation_cropped.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="Inicie a campanha e o experimento">

**Execute as seguintes ações:**

<div id="1-configure-campaigns-on-ad-networks" />

#### 1. Configurar campanhas nas redes de anúncios

O primeiro passo é criar uma campanha que tenha como alvo os utilizadores do seu público e lançá-la ao nível da rede de anúncios (para cada rede de anúncios onde o público está a ser carregado).

* **Importante!** Para obter resultados de teste precisos, configure a campanha para que seja direcionada **apenas** aos utilizadores do público-alvo em teste; não inclua utilizadores de outras fontes.
* Se o público testado for recém-criado, pode demorar até 24 horas para ficar disponível na plataforma de publicidade.

<div id="2-ensure-the-correct-campaign-is-linked-to-the-experiment" />

#### 2. Assegure-se de que a campanha correta está associada à experiência

Uma nova experiência de incrementalidade inicia-se automaticamente quando um novo público é criado com a opção “Medir impacto incremental” ativada (ou se esta opção for ativada recentemente num público já existente). A campanha mais relevante é ligada automaticamente à experiência, mas pode alterá-la, se preferir.

**Para associar ou alterar uma campanha:**

1. No **painel de Incrementalidade** > experiência específica > clique em **Editar experiência**

<Image align="center" alt="Edit_experiment.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

Ou

Em **Públicos**, localize o público específico > clique em **+ Ligar campanha** na coluna Incrementalidade.

<Image align="center" alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

Surge uma janela que permite associar campanhas.

<Image align="center" alt="Link_campaign_to_experiment_window.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. Selecione a campanha relevante para cada rede de anúncios.

**Nota:** O menu suspenso será preenchido com campanhas provenientes dos seus parceiros de mídia. Quando os dados estiverem disponíveis, as campanhas no menu serão ordenadas de acordo com a probabilidade de serem usadas para comunicar com o público específico. A principal sugestão será pré-selecionada para si.

3. Clique em **Guardar**.

A campanha está agora associada à experiência.

<div id="manually-create-an-experiment" />

#### Criar uma experiência manualmente

Se é assinante do Incrementality e criou o seu público após 11 de janeiro de 2023, não precisa de criar uma experiência manualmente. As experiências são criadas automaticamente para os seus públicos (surgindo no painel de Incrementalidade com "[Auto]" antes do título). Se prefere criar uma experiência manual para um público mais antigo ou por outra razão, siga estes passos.

**Para criar manualmente uma nova experiência de incrementalidade:**

* Na AppsFlyer, no menu lateral, selecione **Otimizar** > **Incrementalidade**.
* Na página **Experiências de Incrementalidade**, clique em **Nova Experiência**.
* Siga os passos no assistente para criar o experimento. As instruções detalhadas são fornecidas à medida que avança em cada etapa.

  <div id="notes" />

  > 📘 **Cada coluna representa um parâmetro**
  >
  > Passo 2 do assistente – Configuração da audiência
  >
  > <Image align="center" alt="" src="https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png" width="603px" />
  >
  > No passo 2 do assistente, deve selecionar a **data a partir da qual os membros da audiência serão incluídos no experimento.**
  >
  > Por padrão, esta é a data em que a audiência foi inicialmente dividida com um grupo de controlo. Para garantir resultados precisos do experimento, deve alterar esta data se ocorrer uma das seguintes situações:
  >
  > * Se você tiver feito alterações na definição da audiência selecionada (<Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#tudo-sobre-conjuntos-de-regras">conjuntos de regras de segmentação de audiência</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#user-identifier-device-id-vs-customer-id">identificador de usuário</Anchor> etc.) → altere esta data para corresponder à última data em que essas alterações na definição da audiência foram feitas. → altere esta data para corresponder à última data em que essas alterações na definição da audiência foram feitas.
  > * Se estiver a testar uma nova campanha numa audiência pré-existente → altere esta data para a data em que lançou a nova campanha.
  >
  > **Passo 3 do assistente – Definir metas**
  >
  > <Image align="center" alt="Step_3_Set_targets.jpg" src="https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg" />
  >
  > É aqui que seleciona a aplicação de destino e os KPIs.
  >
  > **Nota:** Todos os outros KPIs estarão disponíveis no final do experimento, mesmo que não tenham sido selecionados.
  >
  > Passo 4 do assistente – Revisão
  >
  > <Image align="center" alt="" src="https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png" width="583px" />
  >
  > No passo 4 do assistente, pede-se que defina o **período do experimento.**
  >
  > * Por padrão, um experimento é configurado para decorrer durante 30 dias a partir de quando é criado. Este é o período mínimo recomendado para a execução de um experimento.
  > * Selecione a opção **Continuar experimento indefinidamente** se desejar que o experimento continue até decidir encerrar.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="Analise os resultados">

Os resultados iniciais do experimento estão disponíveis no <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#dashboard-de-incrementalidade">painel de incrementalidade</Anchor> cerca de 48 horas após o lançamento das campanhas nas redes de anúncios (atualizado <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor>). Poderá ver <Anchor target="_blank" href="/marketers/pt/docs/understand-incrementality-for-remarketing-experiment-alerts">alertas na página do experimento</Anchor> que ajudam a identificar questões que podem comprometer a precisão dos resultados e sugerem ações para resolvê-las.

<Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#relatórios-de-dados-brutos">Os relatórios de dados brutos de incrementalidade</Anchor> estão disponíveis no Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Guia de audiências</Anchor>

<div data-zendesk-anchors="overview=sobre-a-experi%C3%AAncia h_01HARVCSMM80QXXXKJC8TX7CKC=sobre-a-experi%C3%AAncia get-started=iniciar h_01HARVCSMMYJVN6GJ3TB46P8AC=iniciar set-up-the-experiment=configurar-o-experimento h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=configurar-o-experimento h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=exemplo h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=verifique-as-funcionalidades-de-expans%C3%A3o-de-p%C3%BAblico h_01HARVCSMMXNE4NCWSQZ9SHK1J=verifique-as-funcionalidades-de-expans%C3%A3o-de-p%C3%BAblico h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-configurar-campanhas-nas-redes-de-an%C3%BAncios h_01HARVCSMMVXJWCT2BX3CVC3VT=1-configurar-campanhas-nas-redes-de-an%C3%BAncios 2-link-campaigns-to-experiment=2-assegure-se-de-que-a-campanha-correta-est%C3%A1-associada-%C3%A0-experi%C3%AAncia h_01HARVCSMNAWNYEY83NC6Y5XV4=2-assegure-se-de-que-a-campanha-correta-est%C3%A1-associada-%C3%A0-experi%C3%AAncia manually-create-an-experiment=criar-uma-experi%C3%AAncia-manualmente h_01HARVCSMNZVWK8Z36ER1HH10W=criar-uma-experi%C3%AAncia-manualmente h_01HARVCSMN5944HRD9N7YEKT3P=cada-coluna-representa-um-par%C3%A2metro h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=consulte-tamb%C3%A9m" />
