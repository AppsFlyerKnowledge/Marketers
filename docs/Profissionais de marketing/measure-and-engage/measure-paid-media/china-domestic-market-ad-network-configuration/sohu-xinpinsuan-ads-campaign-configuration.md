---
title: Configuração de campanha do Sohu XinPinSuan Ads
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-05T08:57:46Z'
  edited_at: '2026-09-16T00:26:46Z'
  id: 360001953697
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360001953697
---
> **Em resumo:** o Sohu XinPinSuan Ads é um parceiro de ad network integrado ao AppsFlyer.

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Sohu XinPinSuan Ads inclui 3 abas ativas: Integração, link de atribuição e permissões. Clique nos itens abaixo para saber mais sobre a configuração dessas abas.

<div id="integration-tab" />

<Accordion title="Guia Integração">

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">aqui</Anchor>.**

<div id="default-postbacks" />

### Postbacks padrão

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="520px" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a AD\_NETWORK por meio de postbacks. 

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png" width="611px" />

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
3. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado da AD\_NETWORK.  <br />Obtenha o ID do evento correspondente da AD\_NETWORK e configure no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado ao parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcada** - a AppsFlyer envia todos os parâmetros incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Guia Attribution Link">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Sohu XinPinSuan Ads para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do Sohu XinPinSuan Ads. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Sohu XinPinSuan Ads.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Sohu XinPinSuan Ads.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina os nomes dos anúncios para comparar diferentes criativos em conjuntos de anúncios específicos de campanhas específicas do Sohu XinPinSuan Ads.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="parâmetros-do-link-de-atribuição.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a Estrutura e os Parâmetros do Link de Atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de exibição

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao Sohu XinPinSuan Ads.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows#janelas-de-lookback">janela de lookback de clique aqui</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="click-attribution-link" />

### Link de atribuição de cliques

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Sohu XinPinSuan Ads para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custo">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Ad Revenue (Receita publicitária)">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Guia Permissions">

Nessa aba, você pode selecionar as permissões a serem concedidas à Sohu XinPinSuan Ads, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para o Sohu XinPinSuan Ads, a aba de permissões está ativa e você pode conceder controle ao Sohu XinPinSuan Ads.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

* ***Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de eventos in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW6XEHPM944AN2AZY3GQD77=integration-tab activate-partner=ativar-parceiro h_01HKW6XEHQFNWXN83X5C5N4HR9=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HKW6XEHQJEDMSAF5N7MBFZTJ=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6XEHQB43GJ6CSXG930ZYX=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6XEHQP53XF1H89ZRDKVTK=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6XEHQN7KDEZE629D50998=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HKW6XEHQCCCDMXXAYD7GEYS0=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o click-attribution-link=link-de-atribui%C3%A7%C3%A3o-de-cliques h_01HKW6XEHQQ6333VSWK2D3JVWF=link-de-atribui%C3%A7%C3%A3o-de-cliques h_01HKW6XEHQTJBXHEBY52A1MCWP=cost-tab h_01HKW6XEHQ69P4GY9QMZS9WCQJ=ad-revenue-tab h_01HKW6XEHQD3FS5YQ7EDDNC7QA=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6XEHQ4W2Z79GJW45RZ5KN=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
