---
title: Configuração da campanha do Baidu Native Ads 2.0
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
  created_at: '2019-08-02T04:18:11Z'
  edited_at: '2026-09-16T00:26:26Z'
  id: 360002158958
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360002158958
---
> **Resumo:** o Baidu Native Ads 2.0 é um parceiro integrado de ad network da AppsFlyer.

<div id="setting-up-baidu-native-ads-20" />

## Configuração do Baidu Native Ads 2.0

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Baidu Native Ads 2.0 inclui 3 guias ativas: Integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Guia Integração">

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

O Baidu Native Ads 2.0 se conecta à AppsFlyer por meio de uma **akey** exclusiva. Se você ainda não tiver a chave, deverá obtê-la com o Baidu Native Ads 2.0 para continuar com a integração.

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/fe8f44ee7d58fda9ee6289872903f96c716ab6d1191dd831745445cbced8b316-50899807435409.png" width="417px" />

<div id="default-postbacks" />

### Postbacks padrão

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="552px" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção você pode mapear seus eventos da AppsFlyer com o Baidu Native Ads 2.0 por meio de postbacks. 

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/1d929a3ba75da04165e416843f5037b8e299b12ae190aa9068cc3b317348087c-50899846627601.png" width="598px" />

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
3. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome exclusivo ou ID de cada evento, conforme definido no lado do Baidu Native Ads 2.0.  <br />Obtenha o ID de evento correspondente do Baidu Native Ads 2.0 e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Guia Attribution Link">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Baidu Native Ads 2.0 para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais do Baidu Native Ads 2.0. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Baidu Native Ads 2.0.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Baidu Native Ads 2.0.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos em campanhas específicas do Baidu Native Ads 2.0.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de site IDs e use o parâmetro de subsite ID, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de site ID</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="parametros-de-link-de-atribuicao.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de exibição

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que ocorrem dentro da janela de lookback podem ser atribuídas ao Baidu Native Ads 2.0.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="attribution-link" />

### Link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para o Baidu Native Ads 2.0 para que seja ativado quando os leads clicarem em um anúncio correspondente.

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

As permissões não são compatíveis com a integração desse parceiro.


</Accordion>

<div data-zendesk-anchors="setting-up-baidu-native-ads-20=configura%C3%A7%C3%A3o-do-baidu-native-ads-20 h_01HKW6TZKDHY5D1VZ5PB7VM2MC=configura%C3%A7%C3%A3o-do-baidu-native-ads-20 h_01HKW6TZKDRECSQTP2VSAZZ5V6=integration-tab activate-partner=ativar-parceiro h_01HKW6TZKDY6EEHMK5SJWBW0EH=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW6TZKDGFFMPSZGN8AZWA80=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW6TZKDBAQRP63ST32NN4DN=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6TZKDYHPZXN0TC219XPA1=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6TZKEFVXGP11N8G4C6JTP=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6TZKE5GJV1ZSJTVPG668Q=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HKW6TZKEWA482TABZ8651NPP=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o attribution-link=link-de-atribui%C3%A7%C3%A3o h_01HKW6TZKEWJTMCK86JZN27R1F=link-de-atribui%C3%A7%C3%A3o h_01HKW6TZKEX2JQQNA5JMQ40848=cost-tab h_01HKW6TZKE4N38GCTBK4VDNNF8=ad-revenue-tab h_01HKW6TZKEY7RSV934KZ6XRXM2=permissions-tab" />
