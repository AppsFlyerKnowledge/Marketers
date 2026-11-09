---
title: Configuração de campanhas do Meiyou Ads
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - meiyou
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-01T03:26:18Z'
  edited_at: '2026-09-16T00:26:33Z'
  id: 360002141597
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360002141597
---
> **Em resumo:** o Meiyou Ads é um parceiro integrado de ad network da AppsFlyer.

<div id="setting-up-meiyou-ads" />

## Configurando o Meiyou Ads

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Meiyou Ads inclui 3 abas ativas: Integração, link de atribuição e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Guia Integração">

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

O Meiyou Ads se conecta à AppsFlyer por meio de uma **chave** exclusiva. Se você ainda não tiver a chave, deverá obtê-la com o Meiyou Ads para continuar com a integração.

<Image align="center" alt="mceclip3.png" src="https://files.readme.io/451f74c0a6b45926f89a3f2a5d04b6ef240184c4862b576bee0d0a2b7a832f30-50900150950417.png" />

**Habilitar a atribuição de view-through**

Alterne para LIGADO se quiser atribuir instalações view-through do Meiyou Ads. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="548px" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear os eventos da AppsFlyer com o Meiyou Ads por meio de postbacks.

**Chave**

O Meiyou Ads se conecta com a AppsFlyer por meio de uma chave exclusiva. Se você ainda não tiver a chave, deverá obtê-la com o Meiyou Ads para continuar com a integração.

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/32b1c68531c7aa752514f9b1c13c4438cddef2e93d2ca04ab287d46acecda15e-50900150956305.png" width="661px" />

1. Defina aqui a chave do Meiyou Ads
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido pelo Meiyou Ads.  <br />Obtenha o ID do evento correspondente no Meiyou Ads e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Guia Attribution Link">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Meiyou Ads para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do Meiyou Ads. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/3a9b086aa1a76dc64289a512eec56885d108dce5c2778580fc0b2962f00c8a95-50900150957201.png" />

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução no Meiyou Ads.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Meiyou Ads.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Meiyou Ads.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de exibição

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas à Meiyou Ads.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="click-attribution-link" />

### Link de atribuição de cliques

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie para o Meiyou Ads para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas ao Meiyou Ads, desde que não tenha havido nenhum outro clique relevante em anúncio.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição por visualização aqui</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png" />

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie para o Meiyou Ads para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.


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

Nesta aba, você pode selecionar as permissões a serem concedidas ao Meiyou Ads, seja o parceiro uma ad network, uma agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para o Meiyou Ads, a aba de permissões está ativa e você pode conceder controle ao Meiyou Ads.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

* ***Permitir configurar a integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de eventos in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-meiyou-ads=configurando-o-meiyou-ads h_01HKW6VQGVGFA45SQK1KANQ10Q=configurando-o-meiyou-ads h_01HKW6VQGV71MM2T401TGHEMHA=integration-tab activate-partner=ativar-parceiro h_01HKW6VQGV3HG1ZTR41BD43ZTC=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW6VQGVNG13KARWZBSD59KX=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW6VQGV32R49RCEKCYK1G18=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6VQGVHCVWR4KDHTH24D17=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6VQGVV9X64XHW48VGW6E6=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6VQGVZJ36JVCZ3SW7Z3YD=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HKW6VQGWZQQZWT476QT496YF=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o click-attribution-link=link-de-atribui%C3%A7%C3%A3o-de-cliques h_01HKW6VQGWG7BH11EK5HQACKVY=link-de-atribui%C3%A7%C3%A3o-de-cliques viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HKW6VQGWFJEJYD9KG8BH9EX0=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW6VQGWXCB2W13TM4WAGWE1=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW6VQGWY3AFFTN0DP8BCV7S=cost-tab h_01HKW6VQGWARB4409DWKVDY45W=ad-revenue-tab h_01HKW6VQGW20F6TTCBPGDH57JW=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6VQGWXBME473RXA5K1217=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
