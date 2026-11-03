---
title: Configuração da campanha da Xiaomi Ads Network
metadata:
  keywords:
    - XiaoMi
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
  created_at: '2017-03-28T11:08:46Z'
  edited_at: '2026-09-16T00:27:02Z'
  id: 115001605286
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115001605286
---
> **Visão geral:** A Xiaomi, parceira integrada de ad network da AppsFlyer, opera a loja de aplicativos Xiaomi Android, que está entre as 5 principais plataformas de distribuição de aplicativos Android na China, com 5 bilhões de downloads de aplicativos por mês. Além da atribuição mobile baseada em cliques, a Xiaomi também oferece atribuição view-through, que você pode registrar com a AppsFlyer.

## Configurando a Xiaomi

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Observação importante:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração da Xiaomi inclui 3 abas ativas: integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Ativar parceiro

Em seu **primeiro acesso**, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Configurações gerais

**Habilitar a atribuição de view-through**

Alterne para LIGADO se desejar atribuir instalações view-through da Xiaomi. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

![](https://files.readme.io/c01732abe8d1bb3c68acdf84bab50cc46d4f4923b7220e3ca51c399074113c1e-50899866307217.png)

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a Xiaomi após as instalações de usuários e os reengajamentos. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

![xiaomi-default-postbacks.png](https://files.readme.io/ae215140550604649e4345729a7106fa08c15713e003cec534199e3889122b5e-50899866309265.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.  

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

No momento, a integração de dados de custo não é compatível com a Xiaomi.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

No momento, a integração de receita de anúncios não é compatível com a Xiaomi.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas à Xiaomi, independentemente de o parceiro atuar como ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a Xiaomi, a aba de permissões está ativa e você pode conceder controle à Xiaomi.

![ad_network_permissions.png](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-xiaomi=configurando-a-xiaomi h_01HKW6ZDW8D6CD60S25FVQ80FC=configurando-a-xiaomi h_01HKW6ZDW8JK323YYPCSYZ1PKB=integration-tab activate-partner=ativar-parceiro h_01HKW6ZDW8B60R3QAZRMPHVC31=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HKW6ZDW8GW51XT1XXPE7DZ02=postbacks-padr%C3%A3o h_01HKW6ZDW8ERH0MQ2W2YGC5SXB=attribution-link-tab h_01HKW6ZDW8SHGTTVC4V7R1R90K=cost-tab h_01HKW6ZDW8ENFJN342XN66TM19=ad-revenue-tab h_01HKW6ZDW89CE47NF67TJM4AX9=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6ZDW8Y85VBJPQ40MZ5CV5=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
