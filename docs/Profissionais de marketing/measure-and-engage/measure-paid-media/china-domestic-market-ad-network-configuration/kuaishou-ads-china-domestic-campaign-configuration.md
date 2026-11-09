---
title: Configuração da campanha de anúncios Kuaishou (China doméstica)
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
  created_at: '2019-06-05T06:07:11Z'
  edited_at: '2026-09-16T00:26:30Z'
  id: 360001748437
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360001748437
---
> **Em resumo:** a Kuaishou é um parceiro integrado de ad network da AppsFlyer.

<div id="setting-up-kuaishou" />

## Configuração do Kuaishou

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Kuaishou inclui 3 abas ativas: Integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="default-postbacks" />

### Postbacks padrão

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Kuaishou por meio de postbacks.

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png" />

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
3. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome exclusivo ou o ID de cada evento, conforme definido no lado do iQIYI Ads.  <br />Obtenha o ID do evento correspondente do iQIYI Ads e configure no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Gere e salve links de atribuição e envie-os ao parceiro para atribuir campanhas específicas, conjuntos de anúncios ou anúncios exclusivos, tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

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

Nessa aba, você pode selecionar as permissões a serem concedidas ao Kuaishou, independentemente de o parceiro atuar como uma ad network, uma agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para o Kuaishou, a aba de permissões está ativa e você pode conceder controle ao Kuaishou.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

* ***Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-kuaishou=configura%C3%A7%C3%A3o-do-kuaishou h_01HKW6VK4HFZYAY2XC7Y6QGXD4=configura%C3%A7%C3%A3o-do-kuaishou h_01HKW6VK4HMKVSRH9PXH6ASDGJ=integration-tab activate-partner=ativar-parceiro h_01HKW6VK4HWBBP9W3BMTC8KQBJ=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HKW6VK4H4SQP4Q5QXC683R38=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6VK4HW50X9Z2WJ5X9RP90=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6VK4HKFCXKQNN0RY16B10=attribution-link-tab h_01HKW6VK4JSK4JFC0XD2JM7JJ6=cost-tab h_01HKW6VK4JSCS6M01R6SF1V9YB=ad-revenue-tab h_01HKW6VK4JEEBKB2G0H3WFRB8W=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW6VK4JY5YG805PZQ7EG1VM=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
