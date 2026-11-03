---
title: Incorpore as taxas da agência aos custos da campanha
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2021-06-03T13:53:23Z'
  edited_at: '2026-08-19T00:01:07Z'
  id: 4402103019665
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/4402103019665
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** As regras de taxa de agência fazem parte do recurso premium ROI360 da AppsFlyer, que permite que os anunciantes adicionem as taxas percentuais que as agências cobram pelo tráfego para que possam ver o custo total da campanha.

## Escritórios

As regras de taxa de agência são definidas pelo anunciante (com privilégios de administrador da conta AppsFlyer) no Builder de regras, usando condições personalizadas que adicionam percentuais de taxa ao custo das campanhas de agência para aplicativos específicos e/ou canais de mídia.

O ROI360 usa a regra de taxa de agência para calcular o custo total do anúncio com a taxa, com base na API da ad network e no custo do link de Atribuição. O cálculo se aplica em todos os níveis de granularidade (campanha, conjunto de anúncios etc.). Os resultados são exibidos nos seus dashboards, relatórios e no Cost ETL; não nos dashboards e relatórios da agência ou da ad network. **Observação**: Os relatórios do Cost ETL têm campos adicionais para taxas de agência.

As regras de agência ajudam os anunciantes a:

* Entender o custo real de suas campanhas de anúncios
* Economizar tempo e esforço manual para gerar relatórios sobre dados de custo
* Gerenciar a performance da agência
* Analisar com precisão os dados históricos de custo

## Procedimentos

Consulte as seções a seguir para ver instruções sobre como visualizar, adicionar, editar e excluir regras. Todos os procedimentos exigem privilégios de administrador da AppsFlyer.

<div id="view-rule-list" />

<Accordion title="Ver lista de regras">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para visualizar todas as regras de taxa de agência criadas na sua conta**:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Controle de custo.**  
   A tela Controle de custo exibe a lista de regras de agência. As regras são categorizadas nos seguintes status possíveis:
   * **Ativo:** A data de início da regra é hoje ou anterior, e as regras já calcularam dados de taxa pelo menos uma vez.
   * **Inativo:** A data de término da regra está no passado (ou seja, antes de hoje).
   * **Agendado:** Há dados aguardando processamento. Depois de criar uma regra ou editar a data/o preço, a regra fica como Agendada até ser processada e, em seguida, muda para Ativo ou Inativo.
   * **Falha:** A regra não consegue calcular por motivos técnicos.
2. Filtre as regras na lista usando as opções de filtro: Parceiro, Aplicativo e canal de mídia.

</Accordion>

<div id="add-rule" />

<Accordion title="Adicionar regra">

A interface de usuário do criador de regras foi projetada para criação de regras interativa. **Dica!** Familiarize-se e teste o criador de regras antes de ler este artigo em detalhes.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para adicionar uma nova regra**:

1. No AppsFlyer, no menu lateral, selecione **Configurações** > **Controle de custos.**
2. Clique em + **Adicionar regra de taxas de agência**.  
   A tela da regra de taxas de agência é exibida.
3. Selecione um parceiro (agência).
4. Escolha um ou mais aplicativos ou selecione **Todos os aplicativos**. Se você selecionar **Todos os aplicativos**, a regra será aplicada a todos os seus aplicativos, incluindo os aplicativos adicionados à sua conta no futuro.
5. Selecione uma ou mais fontes de mídia ou marque Todas as fontes de mídia. Se você marcar Todas as fontes de mídia, a regra se aplica a todas as fontes de mídia, incluindo as adicionadas no futuro.
   * Se a agência com a qual você trabalha não for transparente, a opção **Todos os canais de mídia** será selecionada por padrão, e você não poderá selecionar um canal de mídia específico.
   * Se o aplicativo selecionado não for transparente, a lista suspensa de canal de mídia permanecerá desabilitada, a menos que o aplicativo selecionado na lista suspensa contenha anúncios da Meta ou anúncios da X, pois esses são sempre transparentes.
6. Insira uma data de início.
7. [Opcional] Insira uma data de término.
8. Insira o percentual da taxa de agência. Pode ser um número entre 100 e -100 (para refletir descontos ou reembolsos da agência).
9. Clique em **Criar regra**.

> 📘 **Observação:**
>
> Os erros a seguir podem impedir a criação da sua regra:
>
> * Um campo obrigatório não foi preenchido. Para resolver, verifique se todos os campos obrigatórios foram preenchidos.
> * A lógica da regra entra em conflito com uma regra existente. Para resolver, altere o aplicativo ou o canal de mídia.

</Accordion>

<div id="edit-duplicate-or-delete-a-rule" />

<Accordion title="Editar, duplicar ou excluir uma regra">

**Considerações:**

Ao editar ou excluir uma regra, os dados calculados anteriormente (até 90 dias no passado) são substituídos:

* No caso de uma regra editada, o custo total reflete o percentual atualizado da taxa de agência.
* No caso de uma regra excluída, a taxa de agência é removida do custo total.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para editar, duplicar ou excluir uma regra**:

1. Na [lista de regras](/docs/incorporate-agency-fees-into-campaign-costs#view-rule-list), passe o cursor sobre a regra que você quer editar, duplicar ou excluir.
2. Clique no **Menu** ⋮ no lado direito.
3. Selecione a ação que você deseja realizar.

> 📘 **Observação:**
>
> A agência e a data de início de uma regra não podem ser editadas após a criação da regra. Se você precisar alterá-las, exclua a configuração antiga e crie uma nova regra.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| Caraterística | Observações |
| --- | --- |
| Agências e ad networks | Agências e ad networks não podem visualizar regras nem ver os dados de custo total de anúncios resultantes das regras de taxa de agência em seus dashboards e relatórios. |
| Relevância dos dados | <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intradiário</Anchor>. Os cálculos iniciais podem levar até 5 horas para serem exibidos. |
| Histórico de dados | As regras podem ser criadas e impactar dados de até 90 dias no passado. |
| Frequência de processamento de regras | Novas regras de taxa de agência são processadas a cada **4 horas**. Isso significa que uma regra pode levar até **4 horas** para ser aplicada. |

Especificações e limitações

</Accordion>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01HFV23CD24HQVC82NNNBDKFRH=escrit%C3%B3rios procedures=procedimentos h_01HFV23CD38RXRT59DNGZAADV1=procedimentos h_01HFV23CD3F5ZPT4D3X8PHJS4T=view-rule-list h_01HFV23CD3MZSZDKTH8CZAY954=add-rule h_01HFV23CD3W6J9QSPHBV9NE19S=observa%C3%A7%C3%A3o h_01HFV23CD3SHHR1HRK6DX4QCET=edit-duplicate-or-delete-a-rule h_01HFV23CD3QH6X0WJEAFTMXNMD=observa%C3%A7%C3%A3o-1 h_01HFV23CD3E486GBA5XBSN41RA=traits-and-limitations" />
