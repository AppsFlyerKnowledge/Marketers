---
title: Alertas de Experiências de Incrementalidade
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2023-03-05T12:31:35Z'
  edited_at: '2024-11-20T07:43:51Z'
  id: 13479545385489
  locale: pt
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/pt/articles/13479545385489
---
> **Visão Geral:** Compreenda os alertas e resolva-os para garantir a precisão dos resultados das suas experiências.

<Image align="center" alt="exp_alerts_doctored.jpg" src="https://files.readme.io/3981e4a4bd66206d9b5986cc1b573f67e1ab836042a1f73518f48a1ea17b6568-35266706078481.jpg" />

<div id="about-experiment-alerts" />

## Sobre os Alertas de Experiências

Após <Anchor target="_blank" href="/marketers/pt/docs/run-an-incrementality-for-remarketing-experiment">configurar uma experiência de incrementalidade</Anchor>, poderá encontrar alertas no painel de controle de incrementalidade. Esses alertas foram criados para ajudar a identificar questões que possam comprometer a integridade e a exatidão dos resultados das experiências. Fornecem informações detalhadas sobre problemas e sugerem medidas que podem ser tomadas para resolvê-los, assegurando resultados precisos. Este artigo oferece uma visão geral detalhada dos diferentes tipos de alertas e das ações recomendadas para resolver os problemas.

<div id="alert-types" />

## Tipos de Alertas

Os alertas de experiências estão divididos nas seguintes categorias:

<div id="experiment-setup" />

<Accordion title="Configuração da Experiência">

<div id="audience-deletion-or-control-group-removal" />

#### Exclusão de público ou remoção do grupo de controlo

Experiências com públicos excluídos ou cujo grupo de controlo foi removido. Em ambos os casos, um erro 404 aparecerá ao visitar a página da experiência.

**Para resolver e restaurar os resultados da experiência:**  
Se o **público-alvo foi removido** - entre em contacto com o seu CSM para que seja restaurado manualmente.  
Se o **grupo de controlo foi removido** - divida novamente o público e configure o grupo de controlo para a mesma percentagem que estava antes.

<div id="more-suitable-campaign-srns-only" />

#### Campanha Mais Adequada? (apenas SRNs)

Este alerta é relevante apenas para as Self Reporting Networks (SRNs). O alerta surge quando uma campanha está ligada a uma experiência, mas os dados sugerem que uma campanha mais adequada existe para atingir o público-alvo.  
Uma "campanha mais adequada" é uma campanha ativa durante o período da experiência que atinge o grupo de teste de forma mais eficaz do que a campanha configurada (e não tem o grupo de controlo como alvo).

**Ações recomendadas:** Verifique se a campanha correta está ligada.

**Nota:** Garanta também que o público-alvo não está incluído na configuração de segmentação de outras campanhas.

<div id="no-impressions-non-srns-only" />

#### Sem Impressões (apenas não SRNs)

Quando são realizados testes de incrementalidade em campanhas de redes de anúncios não SRN, a AppsFlyer requer impressões dos utilizadores para calcular com a máxima precisão o impacto incremental dessas campanhas. Sem impressões, os resultados não serão exibidos na página do teste.

Este alerta descreve uma situação em que, por algum motivo, não estamos a receber dados de impressões da campanha ligada.

**Ações a tomar:** Verifique se está a receber impressões do parceiro de media e se a campanha testada está ativa e a exibir anúncios.

</Accordion>

<div id="experiment-background-environment" />

<Accordion title="Contexto da experiência">

<div id="background-campaign-one-or-multiple" />

#### Campanha de fundo (uma ou várias)

Este alerta surge quando existem campanhas paralelas, muito grandes e não relacionadas, que têm um impacto muito maior no público do que a campanha configurada na experiência.

Como pode isto acontecer?  
Não é incomum existirem campanhas não relacionadas em segundo plano, mas se estas tiverem um orçamento mais elevado ou operarem mais intensamente, podem ofuscar a campanha configurada e, consequentemente, afetar os resultados do teste.

**Ações a tomar:**

* Aumente o impacto da sua campanha elevando o orçamento.
* Verifique se o público testado se sobrepõe ao público-alvo da campanha de fundo (pode ser verificado com a funcionalidade de sobreposição de audiências do parceiro).
* Confirme se o público testado se sobrepõe à campanha de fundo não relacionada.
* Ajuste a segmentação do público testado.
* Caso tenham sido tomadas medidas para minimizar o impacto das campanhas de fundo, estabeleça a data de início do teste após estas mudanças terem sido aplicadas.

**Nota:** **É aconselhável minimizar a segmentação do público-alvo testado com outras campanhas.**

</Accordion>

<div id="linked-campaign-performance" />

<Accordion title="Desempenho da campanha associada">

<div id="audience-overlap" />

#### Sobreposição de audiência

A campanha conectada está a segmentar audiências que se sobrepõem. Isto significa que a configuração de segmentação da campanha ligada inclui mais de uma audiência.  
Além disso, as diversas audiências na configuração da campanha testada sobrepõem-se. Isto irá resultar na segmentação para fora do público testado, incluindo o grupo de controlo desse mesmo público.

**Ações a tomar:**  
Atualize a segmentação da campanha para incluir apenas o público testado e remova todos os públicos adicionais.

<div id="control-group-is-targeted" />

#### Grupo de controlo a ser segmentado

Este aviso indica que a campanha configurada está a segmentar o grupo de controlo, quando apenas deveria visar o grupo de teste.

**Como é que isto pode acontecer?**

* A experiência foi ligada à campanha errada.
* A campanha no lado do parceiro de media foi configurada para atingir utilizadores fora do público-alvo (saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/run-an-incrementality-for-remarketing-experiment#verifique-as-funcionalidades-de-expansão-de-público">recursos de expansão de público-alvo</Anchor> no Facebook e no Google).
* A rede não está a aplicar a configuração de segmentação.

**Ações a tomar:**  
Verifique os cenários comuns mencionados acima e contacte o seu CSM caso tenha dúvidas. Em alguns casos, dependendo da relevância da exposição do grupo de controlo à campanha, não há solução, sendo necessário criar um novo experimento de Incrementalidade.

Se a infração for relativamente pequena, basta garantir que o alvo do grupo de controlo foi interrompido. Acompanhe o aviso na interface do utilizador do experimento e veja se o alerta ainda aparece após alguns dias.

<div id="detailed-targeting-toggle-is-enabled" />

#### A alternância de segmentação detalhada está ativada

A segmentação detalhada é uma funcionalidade disponível em algumas redes de anúncios que permite afinar quem vê os seus anúncios. Este alerta aparecerá se a alternância de segmentação detalhada da campanha estiver ativada. Quando ativada, permitirá que a campanha alcance fora do público configurado.

**Ações recomendadas:**  
Certifique-se de que a alternância de segmentação detalhada está desativada na configuração da campanha do parceiro.

<div id="low-activity" />

#### Baixa atividade

A campanha não está a exibir anúncios ou está a exibir muito poucos anúncios ao público-alvo.

**Ações a tomar:** Investigue o problema no lado do parceiro de media para entender por que razão a campanha não está a apresentar anúncios.

<div id="multiple-audiences-connected" />

#### Múltiplos públicos conectados

A configuração de segmentação da campanha inclui múltiplos públicos. Isto pode resultar na segmentação de pessoas fora do público testado ou do grupo de controlo, afetando, por fim, os resultados dos testes.

**Ações a tomar:**  
Uma prática recomendada para os testes de incrementalidade é que a campanha testada se dirija apenas a um público específico.

<div id="out-of-audience-targeting" />

#### Segmentação fora do público alvo

A campanha testada está a atingir utilizadores que não fazem parte do grupo de teste do público-alvo. Parte das despesas da campanha está a ser utilizada para apresentar anúncios a utilizadores que não estão relacionados com o público testado e que não são considerados no teste de incrementalidade.

Portanto, ao aplicar recursos em utilizadores não relacionados, as métricas que envolvem custos da campanha, como o iROAS e o CPiA, poderão ser influenciadas. Estas métricas incluem todo o custo da campanha, abrangendo também o gasto com anúncios direcionados a utilizadores fora do público-alvo, mas não contabilizam as suas conversões.

**Como é que isto pode acontecer?**

* A experiência foi ligada à campanha errada.
* A campanha no lado do parceiro de media foi configurada para atingir utilizadores fora do público-alvo (saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/run-an-incrementality-for-remarketing-experiment#verifique-as-funcionalidades-de-expansão-de-público">recursos de expansão de público-alvo</Anchor> no Facebook e no Google).
* A rede não está a aplicar a configuração de segmentação.

**Ações a tomar:**  
Assegure-se de que a configuração da segmentação da campanha abrange apenas o público-alvo testado e que esta configuração impede que a campanha se dirija a pessoas fora deste público.

</Accordion>

<div data-zendesk-anchors="about-experiment-alerts=sobre-os-alertas-de-experi%C3%AAncias h_01HNZPQJDA5D7Q04CDKMYCW763=sobre-os-alertas-de-experi%C3%AAncias types-of-alerts=tipos-de-alertas h_01HE7R6CQ5R9HAYG83B3903AY8=tipos-de-alertas h_01HE7R6CQ5SNX6VYFD18501JYT=experiment-setup audience-deletion-or-control-group-removal=exclus%C3%A3o-de-p%C3%BAblico-ou-remo%C3%A7%C3%A3o-do-grupo-de-controlo h_01HE7R6CQ5DM1QNN1E55TGDKKH=exclus%C3%A3o-de-p%C3%BAblico-ou-remo%C3%A7%C3%A3o-do-grupo-de-controlo more-suitable-campaigns-srns-only=campanha-mais-adequada-apenas-srns h_01HE7R6CQ518RS50X87243M7BV=campanha-mais-adequada-apenas-srns no-impressions-received-nonsrns-only=sem-impress%C3%B5es-apenas-n%C3%A3o-srns h_01HE7R6CQ57DV8D642APE01JV0=sem-impress%C3%B5es-apenas-n%C3%A3o-srns h_01HE7R6CQ5XFAE56PTX6RRZD5J=experiment-background-environment background-campaign-one-or-multiple=campanha-de-fundo-uma-ou-v%C3%A1rias h_01HE7R6CQ5AZW1RB7XJH4GEEBT=campanha-de-fundo-uma-ou-v%C3%A1rias h_01HE7R6CQ5C6009QZK6TQS6QGC=linked-campaign-performance audience-overlap=sobreposi%C3%A7%C3%A3o-de-audi%C3%AAncia h_01HE7R6CQ6X5C0D4E519W535PH=sobreposi%C3%A7%C3%A3o-de-audi%C3%AAncia control-group-is-targeted=grupo-de-controlo-a-ser-segmentado h_01HE7R6CQ5NFH58H8ZNRG6E4MG=grupo-de-controlo-a-ser-segmentado detailed-targeting-toggle-is-enabled=a-altern%C3%A2ncia-de-segmenta%C3%A7%C3%A3o-detalhada-est%C3%A1-ativada h_01HKSTD08WK37RHM5DM922GGWF=a-altern%C3%A2ncia-de-segmenta%C3%A7%C3%A3o-detalhada-est%C3%A1-ativada low-activity=baixa-atividade h_01HE7R6CQ6C76SZEAN0R93H9QN=baixa-atividade multiple-audiences-connected=m%C3%BAltiplos-p%C3%BAblicos-conectados h_01HKSTFSKDTD2Z8HKCCX2MWBJQ=m%C3%BAltiplos-p%C3%BAblicos-conectados outofaudience-targeting=segmenta%C3%A7%C3%A3o-fora-do-p%C3%BAblico-alvo h_01HE7R6CQ6TVCGW5X8GBX0AJKS=segmenta%C3%A7%C3%A3o-fora-do-p%C3%BAblico-alvo" />
