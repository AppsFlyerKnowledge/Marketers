---
title: Configuração de campanha do Aura from Unity
metadata:
  keywords:
    - Campaign
    - Advertisers
    - Agencies
    - aura
    - ironsource
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-01-27T11:23:49Z'
  edited_at: '2026-08-19T00:24:17Z'
  id: 360005208578
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/360005208578
---
> **Em resumo:** Aura from Unity, um parceiro integrado de ad network da AppsFlyer, é uma plataforma que permite que anunciantes se conectem com usuários quando eles configuram um novo dispositivo.

<Image align="center" alt="aura_logo.png" src="https://files.readme.io/83bca93f3dfe8f6ce9bd74b9141b8c3b4dc01cfcf8f1904c0f992346beee5014-17313206447889.png" />

<div id="aura-from-unity-integration-in-appsflyer" />

## Integração do Aura from Unity na AppsFlyer

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

Conecte-se ao Aura from Unity ativando e definindo parâmetros na aba Integração.

**Para configurar a integração**:

1. Ative **Activate partner**.
2. Em **Configurações gerais**, ative/desative a **Atribuição por view-through**:
   * [Padrão] **Ativar**: ative para atribuir instalações view-through ao Aura from Unity . A janela de lookback é configurada na aba **Link de atribuição**.
   * **Desativar**: as instalações por view-through do parceiro não são atribuídas.
3. **Postbacks padrão** são enviados ao Aura from Unity para:
   * **Instalações**: postbacks são enviados sempre que um usuário instala o aplicativo. Escolha se você quer enviar postbacks para usuários atribuídos ao Aura from Unity ou para todos os usuários, incluindo instalações orgânicas.
   * **Instalações rejeitadas**: com o **Protect360**, postbacks são enviados quando uma <Anchor target="_blank" href="/partners/pt/docs/rejected-attribution-postbacks-to-integrated-partners">instalação é rejeitada devido a fraude</Anchor>. Somente usuários atribuídos ao Aura from Unity são relatados.
4. **Configurações de eventos in-app**: para enviar postbacks, mapeie os IDs dos seus eventos in-app para os IDs in-app do Aura from Unity. Configure os parâmetros da seguinte forma:
   * Ative **postbacks de eventos in-app**.
   * Opção de envio: selecione se você quer enviar **Somente eventos atribuídos a este parceiro** ou **Eventos atribuídos a quaisquer parceiros**, incluindo instalações orgânicas.
   * Clique em **adicionar evento** para adicionar um evento de SDK à lista. Preencha os parâmetros descritos na tabela a seguir.

| Nome da configuração | A descrição |
| --- | --- |
| Nome do evento do SDK | Nome do evento recebido pela AppsFlyer de:<ul><li>SDK integrado ao aplicativo</li><li>Eventos server-to-server</li></ul>**Dica:** Se o evento necessário não estiver na lista, faça uma instalação não orgânica em um dispositivo e verifique novamente. |
| Identificador de evento do parceiro | Nome ou ID exclusivo do evento, conforme definido pela Aura from Unity.<br /><br />Escolha um nome de evento (na lista suspensa) que corresponda o mais próximo possível do evento. |
| Send Revenue (Enviar receita) | [Padrão] **Não ativado:** envia todos os parâmetros in-app para a Aura from Unity, exceto o parâmetro de receita (`af_revenue`).<br /><br />**Ativado**: envia todos os parâmetros in-app, incluindo, quando disponível, o valor da receita. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para fazer a atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para campanhas de aquisição como para retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.  **Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network. 

Para obter a lista completa de Parceiros que oferecem suporte aos dados de custo <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">acesse aqui</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A atribuição da receita de anúncios não está disponível para este Parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Você pode conceder à Aura from Unity permissão para visualizar informações ou configurar alterações na integração. O tipo de permissão varia de acordo com o relacionamento comercial (ad network/agência) que você tem com a Aura from Unity.

**Nota!** É possível conceder permissões à Aura from Unity mesmo que não haja uma integração ativa com ela.

<div id="ad-network-permissions" />

<Accordion title="Permissões da rede de anúncios">

**Para ativar as permissões da ad network**:

1. Ative as **permissões da ad network**.
2. Conceda aos membros da equipe da Aura from Unity acesso a um ou mais dos itens a seguir:
   * **Permitir a configuração da integração**: Permite que o Parceiro configure a aba de integração (exceto postbacks de eventos in-app).
   * **Permitir a configuração de postbacks de eventos in-app**: Permite que o Parceiro mapeie os postbacks de eventos in-app para si mesmo na aba de integração.
   * **Permitir acesso ao seu relatório de retenção**: Permite acesso apenas aos próprios dados de retenção do Parceiro.
   * **Permitir acesso aos seus dados agregados de usuários fidelizados**: Permite acesso apenas aos próprios dados de usuários fidelizados do Parceiro.
   * **Permitir acesso aos seus dados agregados de eventos in-app**: Permite acesso apenas aos próprios dados de eventos in-app do Parceiro.
   * **Permitir acesso aos seus dados agregados de receita:** Permite acesso apenas aos dados de receita atribuídos ao Parceiro.
   * **Permitir ingestão de gasto**: Permite que o Parceiro faça upload de dados de gasto com anúncios para este aplicativo.
   * **Permitir acesso ao seu dashboard do Protect360**: Apenas aos próprios dados do **Protect360** do Parceiro, se o recurso estiver ativado para o anunciante.

</Accordion>

</Accordion>

<div data-zendesk-anchors="aura-integration-in-appsflyer=integra%C3%A7%C3%A3o-do-aura-from-unity-na-appsflyer h_01HKW9GGARZY4X1FAA6BD89K5N=integra%C3%A7%C3%A3o-do-aura-from-unity-na-appsflyer h_01HKW9GGAR9CWWYGRH6C1EMFVM=integration-tab h_01HKW9GGAR9CVKH192FN4P9YND=attribution-link-tab h_01HKW9GGARNCSQ0TAV69550BS8=cost-tab h_01HKW9GGAR0TET4Q5284NHFM7R=ad-revenue-tab h_01HKW9GGAR5ZTPA9R49WN5P7P4=permissions-tab h_01HKW9GGAREEN9YQ065D1ZX1AQ=ad-network-permissions" />
