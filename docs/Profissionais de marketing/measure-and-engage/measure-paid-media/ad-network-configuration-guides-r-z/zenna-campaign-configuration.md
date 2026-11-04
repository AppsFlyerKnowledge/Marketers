---
title: Configuração de campanhas da Zenna
metadata:
  keywords:
    - Advertisers
    - Zenna
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-10-23T06:52:44Z'
  edited_at: '2026-09-10T00:26:22Z'
  id: 115005277446
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/115005277446
---
> **Em resumo:** A Zenna, uma ad network parceira integrada à AppsFlyer, oferece uma solução de aquisição de usuários baseada em performance exclusivamente para jogos mobile.

<div id="setting-up-zenna" />

## Configurando a Zenna

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

No **primeiro acesso**, você precisará ativar o botão de alternância ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

Postbacks padrão

Envie postbacks automáticos para a Zenna após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

<div id="note" />

> 📘 **Nota**
>
> A opção **Somente eventos atribuídos a este parceiro** é a única disponível com a Zenna e vem selecionada por padrão.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Zenna por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
3. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos S2S.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido pela Zenna.  <br />Obtenha o ID do evento correspondente da Zenna e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Zenna para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais da Zenna. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Zenna.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Zenna.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Zenna.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e utilizar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a Estrutura e os Parâmetros do Link de Atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas à Zenna.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Zenna para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas à Zenna, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a Zenna, a aba de permissões está ativa e você pode conceder controle à Zenna.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-zenna=configurando-a-zenna h_01HK29KRYQHED4BDRQTXX3QCQG=configurando-a-zenna h_01HK29KRYQV8ZB97MB7N8KQYAC=integration-tab activate-partner=ativar-parceiro h_01HK29KRYQ8P16VHDBZMR7464W=ativar-parceiro h_01HK29KRYQPVTA71RT3V3KMD0Q=nota inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK29KRYQBZ8A63YRC7B8MC5P=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK29KRYQ458XWFHVQK58DQ5Z=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HK29KRYQM4SEJ3JERHK4XP66=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HK29KRYR6E498ZJM8AYEYMZ2=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HK29KRYRBM7ZN2956V3GY1X7=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HK29KRYR203VFA2SX4HAWQVV=cost-tab h_01HK29KRYR03B6TKGVEZXF7CRK=ad-revenue-tab h_01HK29KRYREKNX908FP46XNJT5=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HK29KRYRW98Q8XS91DK5BTAA=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
