---
title: Configuração da campanha do MoPub Acquire
metadata:
  keywords:
    - CrossInstall
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
  created_at: '2016-06-20T11:27:42Z'
  edited_at: '2026-09-10T00:24:57Z'
  id: 211187263
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/211187263
---
> **Em resumo:** o MoPub Acquire (antigo Crossinstall, uma empresa X Ads) é um parceiro integrado da AppsFlyer. O MoPub Acquire é uma plataforma de demanda exclusiva para dispositivos móveis, especializada em anúncios jogáveis em escala. Além da atribuição mobile baseada em cliques, o MoPub Acquire também oferece atribuição de custo e view-through, que você pode registrar com a AppsFlyer.

<Image alt="MoPub Acquire, uma empresa do Twitter" src="https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png" width="104px" />

<div id="setting-up-mopub-acquire" />

## Como configurar o MoPub Acquire

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

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

**Para habilitar a integração deste parceiro**, ative **Ativar parceiro**.  
A alavanca deve ser mantida enquanto você trabalhar com o parceiro. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativação de parceiros</Anchor>.

**Habilitar a atribuição de view-through**

Ative essa opção se quiser atribuir instalações por view-through do MoPub Acquire. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para o MoPub Acquire após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao MoPub Acquire.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear os eventos da AppsFlyer com o MoPub Acquire por meio de postbacks.

**Para configurar postbacks de eventos in-app:**

1. Ative o **postback de evento in-app**.
2. Defina a **janela de postback de evento in-app** (saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração da janela de postback de evento in-app</Anchor>).
3. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista.
4. Complete os parâmetros necessários:

| Nome do parâmetro | A descrição |
| --- | --- |
| Nome do evento do SDK | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica**: Não vê o evento que você está procurando? Digite o nome do evento do SDK, clique em **Criar personalizado** e mapeie normalmente. Leia mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado</Anchor>. |
| Opção de envio | Selecione a opção de envio para o evento:<ul><li>**Somente eventos atribuídos a este parceiro** para eventos provenientes **apenas** de usuários atribuídos a este parceiro.</li><li>**Eventos atribuídos a qualquer parceiro ou orgânico** para que toda a sua base de usuários esteja disponível para ser reportada ao parceiro.</li></ul> |
| Send Revenue (Enviar receita) | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao MoPub Acquire para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais do MoPub Acquire.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o MoPub Acquire.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do MoPub Acquire.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do MoPub Acquire.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, recomendamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
   **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas ao MoPub Acquire.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para o MoPub Acquire para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro dessa janela de lookback, após uma impressão de anúncio, serão atribuídas ao MoPub Acquire, desde que não tenha havido outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o para o MoPub Acquire para ser ativado quando um anúncio correspondente for visualizado.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao MoPub Acquire. Observe que, mesmo se a atribuição estiver desativada para o MoPub Acquire, a aba de permissões estará ativa e você poderá conceder controle ao MoPub Acquire. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">Saiba quais permissões você pode conceder ao MoPub Acquire</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mopub-acquire=como-configurar-o-mopub-acquire h_01HFP4C4JDPYDGM3RBSQCNHC3T=como-configurar-o-mopub-acquire h_01HFP4C4JDRMK87B48F4MV5B91=integration-tab activate-partner=ativar-parceiro h_01HFP4C4JD5A9RZP6HBBM2WFHZ=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HFP4C4JDAK0N210GAH978CM0=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HFP4C4JDEW2YBFCFR0MN6G91=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HFP4C4JDWBC03HBEZ13HP3NS=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HFP4C4JDWAWKMT1CSPQSCNMZ=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HFP4C4JDW2DRVVHXJ8ZAT9W5=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HFP4C4JDTXJYH4S1EZ4HYJWG=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HFP4C4JDDWH23CVQMJNH2V70=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HFP4C4JDYXBYAP5AYBN54A4B=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HFP4C4JDP8NDDRHGXM0Y7XM7=cost-tab h_01HFP4C4JDBWCER854NDKTYRW8=ad-revenue-tab h_01HFP4C4JDRYYPW6W2PNA8J8P3=permissions-tab" />
