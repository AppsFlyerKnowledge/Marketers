---
title: Configuração de Campanha do vivo Ads
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
  created_at: '2019-08-29T08:24:47Z'
  edited_at: '2026-09-16T00:26:54Z'
  id: 360002358897
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360002358897
---
> **Em resumo:** o vivo Ads é um parceiro integrado de ad network da AppsFlyer.

## Configurando o vivo Ads

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** A opção **deve permanecer ativada (ativa) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do vivo Ads inclui 2 abas ativas: Integração e link de atribuição. Clique nos itens abaixo para ler sobre a configuração de abas.

<div id="integration-tab" />

<Accordion title="Guia Integração">

A integração com o vivo Ads oferece suporte apenas ao evento de instalação no postback padrão.

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

### Habilitar a atribuição de view-through

Alterne para LIGADO se quiser atribuir instalações view-through do vivo Ads. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="456px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Guia Attribution Link">

Nesta aba, você pode criar os links de atribuição que deseja enviar ao vivo Ads para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do vivo Ads. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução no vivo Ads.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do vivo Ads.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do vivo Ads.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e utilizar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações do ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="479px" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do Link de Atribuição da AppsFlyer**</Anchor>.

### Atribuição por clique

Essa barra deslizante permite que você defina o **tempo máximo desde o clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao vivo Ads.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

![viewthrough_en-us.png](https://files.readme.io/47ff5d900d8edfdc30f2d2c0588f5e06fc3b44e71aeab630d1b5df2ea8c2db47-50900334036625.png)

### Link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o ao vivo Ads para ser ativado quando os leads clicarem em um anúncio correspondente. 

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro desta janela de lookback, após uma impressão de anúncio, são atribuídas ao vivo Ads, desde que não tenha havido nenhum outro clique relevante em anúncio.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o ao vivo Ads para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

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

As permissões não são compatíveis com a integração com este parceiro.

</Accordion>

<div data-zendesk-anchors="setting-up-vivo-ads=configurando-o-vivo-ads h_01HKW6Y9CJED5RV97WWSYQNBDG=configurando-o-vivo-ads h_01HKW6Y9CJZ1YPFBQH1W0QV21G=integration-tab activate-partner=ativar-parceiro h_01HKW6Y9CJC0EWH84B7GW29VJM=ativar-parceiro enable-viewthrough-attribution=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through h_01HKW6Y9CJ8PNMN2ANR3E3WK1H=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01HKW6Y9CJDY5XHWXN3CK0YGK8=postbacks-padr%C3%A3o h_01HKW6Y9CKQXSWXNK1VEXQFEPA=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6Y9CKSHBWNBH0RY3X3RR3=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-por-clique h_01HKW6Y9CKE86Z1Z4QZH0M665T=atribui%C3%A7%C3%A3o-por-clique attribution-link=link-de-atribui%C3%A7%C3%A3o h_01HKW6Y9CKNB685ZYXB8RM1P41=link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HKW6Y9CKV48NRWSXD0ZKY3M0=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW6Y9CKV6XY1BCD9XX42XZ7=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW6Y9CKZ0TMJ1F3H8X2W733=cost-tab h_01HKW6Y9CKB65QFDTKX4AW3P23=ad-revenue-tab h_01HKW6Y9CKV3KJ5X5ECEF2JJ8N=permissions-tab" />
