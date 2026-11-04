---
title: Configuração da campanha no Yandex Direct
metadata:
  keywords:
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
  created_at: '2021-03-30T10:52:06Z'
  edited_at: '2026-08-19T00:26:42Z'
  id: 360018910138
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360018910138
---
> **Em resumo:** o Yandex Direct é uma plataforma de publicidade que permite executar campanhas de aquisição de usuários e campanhas de retargeting na Pesquisa do Yandex, bem como em milhares de aplicativos e sites na network de publicidade do Yandex.

<div id="set-up-yandex-direct" />

## Configurar o Yandex Direct

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do Yandex Direct inclui 3 guias ativas: **Integração, link de atribuição** e **Permissões**.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar **Ativar parceiro** para permitir a configuração dos parâmetros da aba de integração. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação/desativação de parceiros</Anchor>.

<div id="advanced-privacy" />

### Privacidade avançada

Somente para apps iOS, **Ativar privacidade avançada (para iOS 14.5 e acima)** controla quais dados são compartilhados com o parceiro por meio de postbacks e relatórios. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#b-advanced-privacy">Saiba mais sobre privacidade avançada</Anchor>.

<div id="transaction-id" />

### ID da transação

Apenas para apps iOS. Quando **Compartilhar ID da transação da SKAN** está ativado, você <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartilha o ID da transação dos postbacks da SKAdNetwork</Anchor> com o parceiro. Ao fazer isso, o parceiro pode descriptografar os seus valores de conversão da SKAdNetwork.

<div id="general-settings" />

### Configurações gerais

As seguintes configurações gerais estão disponíveis para o Yandex Direct.

<div id="yandex-ecom-feed-counter-id" />

#### ID do contador do feed de e-commerce do Yandex

Insira o número da tag do Metrika em **ID do contador do feed de e-commerce do Yandex** se você estiver executando campanhas de Smart Banner com seu feed de produtos.

<div id="yandex-app-id" />

#### ID do aplicativo no Yandex

Insira o **ID do aplicativo no Yandex** obtido no Yandex Direct.

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para o Yandex Direct após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente este parceiro** para eventos provenientes apenas de usuários atribuídos ao Yandex Direct.  
Selecione **Todos os canais de mídia, incluindo orgânico** para disponibilizar toda a sua base de usuários para ser reportada ao Yandex Direct.

Como uma network de todas as instalações, o Yandex Direct prefere receber postbacks de todas as novas instalações do seu aplicativo, de todas as fontes, e recomenda selecionar **Todos os canais de mídia, incluindo orgânico**.

<div id="in-app-events-postbacks" />

### Postbacks de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app enviados ao Yandex Direct.

1. Ative **postbacks de eventos in-app**.
2. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
3. Clique em **Adicionar evento** para adicionar um evento de SDK à lista.
4. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Preencha os parâmetros obrigatórios</Anchor>.
5. Clique em **Guardar integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer recebe dados de custo via API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Atenção:** os dados de custo exigem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>. **Observação**: adicione o ID da campanha (af\_c\_id=`{campaign_id}`) aos seus links para garantir um relatório de custo preciso. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais</Anchor>

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Os dados de receita de anúncios não estão disponíveis para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao Yandex Direct, seja para o parceiro atuar como ad network, agência ou até mesmo como ambos. Observe que, mesmo que a Atribuição esteja desativada para o Yandex Direct, a aba Permissões está ativa e você pode conceder Controle ao Yandex Direct. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">Configure as permissões para o Yandex Direct</Anchor>.

</Accordion>

<div data-zendesk-anchors="set-up-yandex-direct=configurar-o-yandex-direct h_01HJZW81YDFP6ZV188XP3H4H54=configurar-o-yandex-direct h_01HJZW81YD3S8BEE6MNT30VYZH=integration-tab activate-partner=ativar-parceiro h_01HJZW81YD1JA5N01HT248PR8K=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01HJZW81YDNWAEKA2DP0QPPQRC=privacidade-avan%C3%A7ada transaction-id=id-da-transa%C3%A7%C3%A3o h_01HJZW81YD8QEETTP4NSG2QCPQ=id-da-transa%C3%A7%C3%A3o general-settings=configura%C3%A7%C3%B5es-gerais h_01HJZW81YDT69PGFTJMQ8WTYN2=configura%C3%A7%C3%B5es-gerais yandex-ecom-feed-counter-id=id-do-contador-do-feed-de-e-commerce-do-yandex h_01HJZW81YD18MW2BNGTZCZM7ZW=id-do-contador-do-feed-de-e-commerce-do-yandex yandex-app-id=id-do-aplicativo-no-yandex h_01HJZW81YDTQ0Q4H39GVJMHYNG=id-do-aplicativo-no-yandex default-postbacks=postbacks-padr%C3%A3o h_01HJZW81YDZDYDES5ZPRQ5BEC3=postbacks-padr%C3%A3o inapp-events-postbacks=postbacks-de-eventos-in-app h_01HJZW81YDMTRZ2VG8S9B48GTD=postbacks-de-eventos-in-app h_01HJZW81YE8XP6Q9RA9XTCKX2T=attribution-link-tab h_01HJZW81YES6M13VVJMTAB6KXQ=cost-tab h_01HJZW81YE7CYXEDFZKWZYVYET=ad-revenue-tab h_01HJZW81YERG3X6RG9Z2CM3YSF=permissions-tab" />
