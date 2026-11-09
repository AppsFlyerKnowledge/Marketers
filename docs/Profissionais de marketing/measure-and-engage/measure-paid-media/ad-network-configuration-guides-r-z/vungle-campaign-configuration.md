---
title: Configuração de campanha da Vungle
metadata:
  keywords:
    - Vungle
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-03T08:53:29Z'
  edited_at: '2026-09-09T00:25:43Z'
  id: 207990186
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/207990186
---
> **Visão geral:** a Vungle, um parceiro integrado de ad network da AppsFlyer, oferece uma plataforma de publicidade em vídeo in-app para profissionais de marketing de performance. Além da atribuição mobile baseada em cliques, a Vungle oferece atribuição de custo e view-through, que pode ser registrada na AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vungle.png?v=1" width="91px" />

<div id="setting-up-vungle" />

## Configurando a Vungle

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Se você não tiver uma conta, entre em contato com o parceiro para abrir uma antes de configurar a integração.

**Para ativar a integração:**

1. Na AppsFlyer, acesse a aba **Colaborar > Integrações de parceiros > Marketplace** .  
    **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, ative a opção **Ativar parceiro**.   
    **Observação:** A opção **deve permanecer ativada (ativa) enquanto você trabalhar com o parceiro**.   
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de parceiros.</Anchor>

<div id="tip" />

> 👍 **Atenção**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partners" />

### Ativar parceiros

Conecte-se à Vungle ativando e configurando os parâmetros na aba de integração. A Vungle deve fornecer seu ID exclusivo de network, ***app\_id***; isso é necessário para se conectar à AppsFlyer.

<div id="note" />

> 📘 **Importante!**
>
> Como uma network de todas as instalações, a Vungle prefere receber postbacks de todas as novas instalações do seu Aplicativo, de qualquer fonte, e recomenda selecionar **Todos os canais de mídia, incluindo orgânico** para enviar todos os postbacks de instalação à Vungle.

**Para configurar a integração**:

1. Habilite ***Ativar parceiro***. Veja mais informações sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
2. **Em *Configurações gerais*, habilite/desabilite *a atribuição view-through*:**
   * [Padrão] **Ativar**: ative para atribuir instalações view-through à Vungle. A duração da janela de lookback é configurada na aba Link de atribuição.
   * **Desabilitar**: as instalações view-through do parceiro não são atribuídas.
3. ***Postbacks padrão***: envie postbacks para a Vungle após instalações e reengajamentos de usuários. Use esta seção para definir os usuários que são a fonte desses postbacks. Em ***Opção de envio***,

   * Selecione **Somente eventos atribuídos a este parceiro** para eventos atribuídos a usuários da Vungle.
   * Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para disponibilizar toda a sua base de usuários para ser reportada à Vungle.
4. ***Configurações de* *eventos in-app***: para enviar postbacks à Vungle, mapeie os IDs de eventos in-app para os da Vungle. Configure os parâmetros da seguinte forma:
   * Insira o app\_id da Vungle.
   * Ative ***postbacks de eventos in-app***.
   * Selecione uma ***Opção de envio***.
   * Clique em ***Adicionar evento*** para adicionar um evento SDK à lista. Preencha os parâmetros conforme descrito na tabela a seguir.

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** | Nome do evento recebido pela AppsFlyer de:<ul><li>SDK integrado ao aplicativo</li><li>Eventos server-to-server</li></ul>**Dica:** Se um evento necessário não estiver na lista, faça uma instalação não orgânica em um dispositivo e verifique novamente. |
| **Identificador de evento do parceiro** | Nome ou ID exclusivo do evento, conforme definido pela Vungle.<br /><br />Obtenha na Vungle o ID do evento correspondente ao seu evento de SDK e insira-o no campo de texto. |
| **Send Revenue (Enviar receita)** | [Padrão] **Não ativado:** envia todos os parâmetros in-app para a Vungle, exceto o parâmetro de receita (`af_revenue`).<br /><br />**Habilitado**: envia todos os parâmetros in-app, incluindo, quando disponível, o valor da receita. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Gere e salve links de atribuição e envie-os ao parceiro para atribuir campanhas específicas, conjuntos de anúncios ou anúncios exclusivos, tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.  

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da sua API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Essa seção é relevante somente se você estiver atuando como publisher, exibindo anúncios do parceiro aos usuários. Nesse caso, você certamente deseja mensurar o engajamento dos usuários adquiridos de várias fontes para encontrar as fontes mais lucrativas para você.

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">essas instruções de integração</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Você pode dar à Vungle permissão para visualizar informações ou configurar alterações na integração. O tipo de permissão varia de acordo com o relacionamento comercial (ad network/agência de anúncios) que você tem com a Vungle.

**Observação**: É possível conceder permissões à Vungle mesmo que não haja uma integração ativa com ela.

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

**Para habilitar permissões de ad networks:**

1. Ative ***Permissões de ad networks***.
2. Conceda aos membros da equipe da Vungle acesso a um ou mais dos itens a seguir:

| **Permitir configuração da integração** | Configurar a aba Integração (exceto postbacks de eventos in-app). |
| --- | --- |
| Permitir configuração dos postbacks de eventos in-app | Configurar postbacks de eventos in-app mapeados para a aba Integração. |
| Permitir acesso ao seu relatório de retenção | Dados de retenção do parceiro |
| Permitir acesso aos seus dados agregados de usuários fidelizados | Dados de usuários fiéis do parceiro |
| Permitir acesso aos seus dados agregados de eventos in-app | Dados de eventos in-app do parceiro |
| Permitir acesso aos seus dados de receita agregados | Dados de receita atribuídos ao parceiro. |
| Permitir ingestão de gastos |  |
| Permitir acesso ao seu painel Protect360 | [Se ativado] Dados do Protect360 do parceiro |

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad network</Anchor>.

<div id="agency-permissions" />

### Permissões da agência

Você pode permitir que a Vungle configure seu aplicativo como uma agência.

**Ative permissões de agência:**

1. Ative as permissões de ***agência***.
2. Conceda à Vungle acesso de agência a um ou mais dos itens a seguir:

| **Permitir acesso ao seu painel Protect360** | [Se ativado para sua conta] Dados do Protect360 da agência |
| --- | --- |
| **Permitir acesso aos seus relatórios de retenção e cohort** | Dados de retenção e de coorte da agência |
| **Permitir acesso a dados orgânicos agregados** | Dados orgânicos agregados da agência |
| **Permitir configuração dos postbacks de eventos in-app** | Configure postbacks de eventos in-app mapeados para a guia Integração. |

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-vungle=configurando-a-vungle h_01HJZVD66Q6ZBPGEASQTAQNH3G=configurando-a-vungle h_01HJZVD66QE7BTR3F5QKJZFPMD=aten%C3%A7%C3%A3o h_01HJZVD66QDTZAG9GD153SM2AG=integration-tab activate-partners=ativar-parceiros h_01HJZVD66QG7FHRCEAT7WX7E1R=ativar-parceiros h_01HJZVD66Q9HB72WQM5Y4S60FN=importante h_01HJZVD66Q5HGF9GWKHB87GK2Y=attribution-link-tab h_01HJZVD66R0XX4DB12R25Y3PXM=cost-tab h_01HJZVD66SNVAHYSSFN2RMWHZX=ad-revenue-tab h_01HJZVD66SJT203JAYDQQ29ZEC=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJZVD66S4680GJ0A9SFSGY4Z=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HJZVD66SC6KK9KWHR6WQYGR3=permiss%C3%B5es-da-ag%C3%AAncia" />
