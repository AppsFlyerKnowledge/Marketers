---
title: Configuração da campanha de anúncios do aplicativo Baidu
metadata:
  keywords:
    - Baidu App Ads
    - Baidu
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
  created_at: '2017-06-18T07:40:30Z'
  edited_at: '2026-09-16T00:26:20Z'
  id: 115003044146
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115003044146
---
> **Em resumo:** O Baidu App Ads (Baitong), um parceiro integrado de ad network da AppsFlyer, é uma das maiores plataformas de promoção e distribuição de aplicativos no mercado interno da China, integrando o tráfego mobile de lojas de aplicativos (Baidu Mobile Assistant, Android Market, 91 Mobile Assistant etc.), da Pesquisa Mobile do Baidu, do Super App e dos afiliados do Baidu.

## Configurar o Baidu App Ads (Baitong)

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** A opção **deve permanecer ativa (ativa) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Baidu App Ads inclui 3 abas ativas: integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

No **primeira visita** aqui, você deve ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Baidu App Ads (Baitong) após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

A integração com o Baidu Baitong Ads oferece suporte apenas ao evento de instalação para postbacks padrão.

![baidu-baitong-default-postback.png](https://files.readme.io/c464429db3eae2dac9fbc13df1a56090ef587cd386ed8214eabd21dac653a622-50900467293713.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Baidu App Ads (Baitong) para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do Baidu App Ads (Baitong). Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Baidu App Ads（Baitong).  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Baidu App Ads（Baitong).  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Baidu App Ads（Baitong).  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e utilizar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas ao Baidu App Ads（Baitong).

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para o Baidu App Ads（Baitong) para ser ativado quando os leads clicarem em um anúncio correspondente.

Aba de Custos

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao Twitter, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a RTB House, a guia de permissões estará ativa e você poderá conceder controle à RTB House.

### Permissões da rede de anúncios

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-baidu-app-ads-baitong=configurar-o-baidu-app-ads-baitong h_01HKW6SB83X3G0CV5A8SNB6DSJ=configurar-o-baidu-app-ads-baitong h_01HKW6SB83NPWAQ0HKVJDMSXKR=integration-tab activate-partner=ativar-parceiro h_01HKW6SB83QKQW6D8F72ENFDB1=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HKW6SB83XK3V4FT17PK0X5PZ=postbacks-padr%C3%A3o h_01HKW6SB83G06N2PWR760310XV=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6SB83VTAYK08P42698YRR=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6SB83R8X1PWPTWG528HPY=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6SB84ZA8KXN7A7N9PEZ7X=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6SB840JT24A8QTB6Z7N7T=cost-tab h_01HKW6SB84MV2RYRQQVPYMFFJ8=ad-revenue-tab h_01HKW6SB84XA73Y64M3S8D2V58=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6SB84Q2NWK0Z3YF7ZQ5QJ=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
