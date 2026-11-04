---
title: Configuração de campanha do Yeahmobi
metadata:
  keywords:
    - yeah-mobi
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
  created_at: '2016-03-28T10:00:25Z'
  edited_at: '2026-09-10T00:26:17Z'
  id: 209731663
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/209731663
---
> **Visão geral:** Yeahmobi, um parceiro integrado de ad network da AppsFlyer, é uma ad network de vídeo para iOS e Android. Além da atribuição mobile baseada em cliques, a Yeahmobi fornece dados de custo, que podem ser registrados com a AppsFlyer.

Para configurar suas campanhas com a Yeahmobi, siga as etapas abaixo.

<div id="setting-up-yeahmobi" />

## Configurando o Yeahmobi

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partners" />

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  

Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a Yeahmobi após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Yeahmobi.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Yeahmobi.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Yeahmobi por meio de postbacks.

1. Ative Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a este parceiro** para eventos provenientes **apenas** de usuários atribuídos a este parceiro.  
   **- Eventos atribuídos a qualquer parceiro ou orgânico** para que toda a sua base de usuários esteja disponível para ser reportada ao parceiro.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Preencha os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pela Yeahmobi.  <br />Obtenha o ID de evento correspondente da Yeahmobi e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Yeahmobi para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais da Yeahmobi. Observe que a AppsFlyer **não** salva os links de atribuição do parceiro gerados por você.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Yeahmobi.  
  **Parâmetro do link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Yeahmobi.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos em campanhas específicas da Yeahmobi.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros do assinante** - use qualquer um dos 5 parâmetros do assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**estrutura e parâmetros do link de atribuição e parâmetros da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas à Yeahmobi.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Yeahmobi para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Yeahmobi envia automaticamente dados de custo de CPI no link de atribuição para todas as instalações.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao parceiro, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que mesmo se a atribuição estiver desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao parceiro.

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos seus dados agregados de usuários fidelizados*** - apenas aos dados de usuários fidelizados do próprio parceiro
* ***Permitir acesso aos seus dados agregados de eventos in-app** -* apenas aos dados de eventos in-app do próprio parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

<div id="agency-permissions" />

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Opção principal*** - defina como Ativado para revelar as opções de permissões da agência
* ***Permitir configurar postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-yeahmobi=configurando-o-yeahmobi h_01HK290F4KYKPR30MW5EH7XSTG=configurando-o-yeahmobi h_01HK290F4KJ4JB72D32RPWBA26=integration-tab activate-partners=ativar-parceiros h_01HK290F4KQVRHB6VB089A9VFH=ativar-parceiros default-postbacks=postbacks-padr%C3%A3o h_01HK290F4KVZPHFD23EKC88BNJ=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK290F4KAK84A1M36VNTFM84=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK290F4KKVB38XP7VP5KSR7V=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HK290F4KV3CNJXW6DP7PSTFQ=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HK290F4M10V9K1AWF8M8JXD1=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HK290F4MV18FSH7GEPBPJESC=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HK290F4MY2F9SX963Q1GGFTV=cost-tab h_01HK290F4MHPH43P52J5ZV9ZC3=ad-revenue-tab h_01HK290F4MZ8MKZVEZPAY8ZBEV=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HK290F4MEXVTJJGAB2BAEGM5=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HK290F4MHH62HP0KRBN9FK9W=permiss%C3%B5es-da-ag%C3%AAncia" />
