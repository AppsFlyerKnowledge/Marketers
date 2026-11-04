---
title: Configuração da campanha Hotstar
metadata:
  keywords:
    - Campaign
    - configuration
    - integrated partner
    - Advertisers
    - hotstar
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-12-19T09:52:42Z'
  edited_at: '2026-09-10T12:24:59Z'
  id: 360004428658
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/360004428658
---
> **Em resumo:** a Hotstar, parceira integrada da AppsFlyer, é um importante serviço de streaming com suporte a anúncios na Índia.

![](https://cdn.appsflyer.com/marketplace/static/logo/hotstar.png)

<div id="hotstar-integration-in-appsflyer" />

## Integração da Hotstar no AppsFlyer

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Se você não tem uma conta, entre em contato com o parceiro para abrir uma antes de configurar a integração.

**Para ativar a integração:**

1. Na AppsFlyer, acesse a aba **Colaborar > Integrações de parceiros > Marketplace** .  
    **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, ative a opção **Ativar parceiro**.   
    **Observação:** A opção **deve permanecer ativada (ativa) enquanto você trabalhar com o parceiro**.   
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de parceiros.</Anchor>

<div id="integration-tab" />

<Accordion title="Aba Integração">

Conecte-se ao Hotstar ativando e definindo os parâmetros na guia de integração.

**Para configurar a integração**:

1. Ative **Ativar parceiro.**
2. **Em** **Configurações gerais** **ative/desative** **Atribuição view-through:**
   * [Padrão] **Ativar**: Ative para atribuir instalações view-through à Hotstar. A duração da janela de lookback é configurada na aba Link de atribuição.
   * **Desativar**: as instalações view-through do parceiro não são atribuídas.
3. **Postbacks padrão**: Envie postbacks ao Hotstar após a instalação do aplicativo pelo usuário. Somente os usuários atribuídos ao Hotstar são reportados.
4. **Configurações de eventos in-app**: para enviar postbacks, mapeie os IDs dos seus eventos in-app para os IDs in-app da Hotstar. Configure os parâmetros da seguinte forma:
   * Ative **os postbacks de eventos in-app**.
   * Opção de envio: **Somente eventos atribuídos a este parceiro** podem ser enviados para a Hotstar.
   * Clique em **adicionar evento** para adicionar um evento de SDK à lista. Preencha os parâmetros conforme descrito na tabela a seguir.

| Nome da configuração | A descrição |
| --- | --- |
| Nome do evento do SDK | Nome do evento recebido pela AppsFlyer de:<ul><li>SDK integrado ao aplicativo</li><li>Eventos server-to-server</li></ul>**Dica:** Se um evento necessário não estiver na lista, faça uma instalação não orgânica em um dispositivo e verifique novamente. |
| Identificador de evento do parceiro | Nome ou ID exclusivo do evento, conforme definido pelo Hotstar. Obtenha no Hotstar o ID do evento correspondente ao seu evento do SDK e insira-o no campo de texto. |
| Send Revenue (Enviar receita) | [Padrão] **Não habilitado:** Envie todos os parâmetros in-app ao Hotstar, exceto o parâmetro de receita (`af_revenue`).<br /><br />**Habilitado**: Envie todos os parâmetros in-app, incluindo, quando disponível, o valor da receita. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Gere links de atribuição de clique e de impressão para serem usados pela Hotstar. A tabela a seguir explica a diferença entre link de clique e link de impressão, bem como a relevância das janelas de lookback.

| Tipo de link de atribuição | Ativação do link | Janela de lookback |
| --- | --- | --- |
| Click-through rate | Um lead clica em um anúncio exibido pelo Hotstar | A janela de lookback de **click-through** é o **tempo máximo entre o clique e a instalação**.<br /><br />O Hotstar recebe uma atribuição se um lead clicar e instalar um aplicativo antes que a janela de lookback expire.<br /><br />**Nome do parâmetro**: `af_click_lookback`  <br />**Valor padrão**: 7 dias  <br />**Intervalo:** 1-23 horas ou 1-30 dias |
| Impressão | Um lead visualiza um anúncio (por pelo menos 1 segundo) exibido pelo Hotstar | A janela de lookback de **view-through** é o **tempo máximo entre a impressão e a instalação**.<br /><br />O Hotstar recebe uma atribuição se um lead visualizar (impressão) um aplicativo e depois o instalar antes que a janela de lookback expire. Isso se aplica se não houver outros cliques em anúncios relevantes.<br /><br />**Nome do parâmetro**: `af_viewthrough_lookback`  <br />**Valor padrão**: 1 dia  <br />**Intervalo:** 1-23 horas ou 1-7 dias |

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">a estrutura do link e os parâmetros</Anchor>.

**Parâmetros típicos do link:**

| Parâmetro | Nome do parâmetro | A descrição |
| --- | --- | --- |
| Campaign | C | Nome da campanha |
| Conjunto de anúncios | af\_adset | Nome do conjunto de anúncios. Use para diferenciar entre conjuntos de anúncios em uma campanha |
| Ad name | af\_ad | O nome do anúncio específico. Use para diferenciar entre criativos em um conjunto de anúncios |
| Hora em que o postback foi recebido pela AppsFlyer  <br />Para Google Ads e Meta ads, este é o momento em que a AppsFlyer obtém os dados da API de anúncios do Google e da Meta, respectivamente. | af\_siteid  <br />af\_sub\_siteid | ID do publisher usado para atribuir instalações a publishers específicos.<br /><br />**Boa prática!** Se houver muitos publishers,<ul><li>Limite o número de IDs de site em uso.</li><li>Use o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder o limite de IDs de site</Anchor>.</li></ul> |
| Parâmetros do assinante | af\_sub1 até af\_sub5 | Use para inserir valores:<ul><li>Os parâmetros são analisados e incluídos no relatório de dados brutos.</li><li>Use-os para realizar a agregação ou a filtragem de dados.</li></ul> |

**Para gerar os links de atribuição**:

1. Selecione um nome na lista suspensa **Nome do parâmetro** e defina o valor do parâmetro.
2. Para adicionar mais parâmetros, clique em **Adicionar parâmetro** e repita a etapa anterior.
3. Defina a duração da janela de lookback de cliques.
4. Defina a duração da janela de lookback de exibição.
5. Copie os links de atribuição de clique e impressão para usar em suas campanhas do Hotstar.  
   **Observação**: a AppsFlyer não salva links de Parceiros.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A atribuição de custo não está disponível para este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A atribuição de receita de anúncios não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Você pode dar ao Hotstar permissão para visualizar informações ou configurar alterações na integração. O tipo de permissão varia de acordo com o relacionamento comercial (ad network/agência) que você tem com o Hotstar.

**Observação**: é possível conceder permissões ao Hotstar mesmo que não haja uma integração ativa com ele.

<div id="ad-network-permissions" />

#### Permissões da rede de anúncios

**Para ativar as permissões da ad network**:

1. Ative as **permissões da ad network**.
2. Dê aos membros da equipe do Hotstar acesso a um ou mais dos itens a seguir:
   * **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
   * **Permitir configurar postbacks de evento in-app** - permite que o parceiro mapeie os postbacks de evento in-app para si mesmo na aba de integração
   * **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
   * **Permitir acesso aos seus dados agregados de usuários fidelizados** - apenas aos próprios dados de usuários fidelizados do parceiro
   * **Permitir acesso aos seus dados agregados de eventos in-app** - apenas aos próprios dados de eventos in-app do parceiro
   * **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
   * **Permitir ingestão de gastos** - é no nível do aplicativo.
   * **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante.

</Accordion>

<div data-zendesk-anchors="hotstar-integration-in-appsflyer=integra%C3%A7%C3%A3o-da-hotstar-no-appsflyer h_01HKA2884DABDCZ8DGY7456A4X=integra%C3%A7%C3%A3o-da-hotstar-no-appsflyer h_01HKA2884DMN9DT8KJQNMJ7P73=integration-tab h_01HKA2884D16FT48173A5TQ44G=attribution-link-tab h_01HKA2884EPHWNNT5MGNNPC5G2=cost-tab h_01HKA2884EPQCRQBX9RRV5YEDK=ad-revenue-tab h_01HKA2884E57SB3X86W6QVB80Y=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKA2884EECK51Z5NQKSGWE96=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
