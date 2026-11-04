---
title: Configuração de campanhas da Mobusi
metadata:
  keywords:
    - Advertisers
    - Mobusi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-14T09:59:36Z'
  edited_at: '2026-09-10T00:24:52Z'
  id: 217909583
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/217909583
---
> **Em resumo:** a Mobusi, uma parceira integrada da AppsFlyer, é uma empresa de aquisição de usuários mobile e serviços de marketing com expertise em publicidade de performance.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobusi.png?v=1" width="119px" />

<div id="setting-up-mobusi" />

## Como configurar a Mobusi

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

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a Mobusi após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

<div id="in-app-event-postbacks-settings" />

### Configurações de postback de evento in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Mobusi por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome exclusivo ou ID de cada evento, conforme definido no lado da Mobusi.  <br />Obtenha o ID do evento correspondente da Mobusi e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros do evento in-app avançado são enviados ao parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta aba, você pode criar os links de atribuição que deseja enviar à Mobusi para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais da Mobusi. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

Adicionar parâmetros ao link de atribuição aqui permite que você faça análises detalhadas posteriormente. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Mobusi.  
  **Parâmetro do link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Mobusi.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Mobusi.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de site IDs usados e usar o parâmetro de subsite ID, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de site ID</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição do AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas à Mobusi.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie para a Mobusi para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custo não está disponível para a Mobusi.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a Mobusi.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Mobusi, seja o parceiro uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Mobusi, a aba de permissões está ativa e você pode conceder controle à Mobusi.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobusi=como-configurar-a-mobusi h_01HKW6QHJZQ1FJ0GWJNPN4NNCF=como-configurar-a-mobusi h_01HKW6QHK0B8EK4AA8R7SF706S=integration-tab activate-partner=ativar-parceiro h_01HKW6QHK07P5N6SQGAY5MPJ65=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HKW6QHK0DCP5VMNDE41TVSNE=postbacks-padr%C3%A3o inapp-event-postbacks-settings=configura%C3%A7%C3%B5es-de-postback-de-evento-in-app h_01HKW6QHK0Z6HEB561G5TK0D3M=configura%C3%A7%C3%B5es-de-postback-de-evento-in-app h_01HKW6QHK09DD7AX0XJ43FHT37=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6QHK0NE8NBPAK2M7SJY42=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6QHK0ZWZYDJ9YV65A2QWK=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6QHK0A6J59W4RN5Z9MW9P=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6QHK0R77NY5CDRQEV1EB1=cost-tab h_01HKW6QHK0B3252ZXHPYM4BP7B=ad-revenue-tab h_01HKW6QHK0HDSBTAKEWZETYH02=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6QHK0H2SMDE61MSXNZP9D=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
