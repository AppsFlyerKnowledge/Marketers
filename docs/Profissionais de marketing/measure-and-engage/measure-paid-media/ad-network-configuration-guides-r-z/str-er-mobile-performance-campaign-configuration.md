---
title: Configuração de campanha do Ströer Mobile Performance
metadata:
  keywords:
    - Stroer
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
  created_at: '2016-12-19T09:26:27Z'
  edited_at: '2026-08-19T00:26:05Z'
  id: 115000068903
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/115000068903
---
> **Visão geral:** o Ströer Mobile Performance, um parceiro integrado de ad network da AppsFlyer, oferece exposição internacional adequada a apps móveis por meio de sua network global exclusiva. Além da atribuição mobile baseada em cliques, o Ströer Mobile Performance fornece dados de custo, que podem ser registrados na AppsFlyer.

Para configurar suas campanhas com o Ströer Mobile Performance, siga as etapas abaixo.

## Configuração do Ströer Mobile Performance

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do Ströer Mobile Performance inclui 3 abas ativas: Integração, link de atribuição e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiros

Em sua **primeira visita** aqui, você precisará ativar o botão de alternância **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Configurações gerais

**Token de segurança**

O Ströer Mobile Performance se conecta à AppsFlyer por meio de um token de segurança exclusivo. Se você ainda não o tem, deve obtê-lo com o Ströer Mobile Performance para continuar com a integração.

### Postbacks padrão

Envie postbacks automáticos para o Ströer Mobile Performance após instalações e reengajamentos dos usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao Ströer Mobile Performance.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Ströer Mobile Performance por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pelo Ströer Mobile Performance.  <br />Obtenha o ID do evento correspondente no Ströer Mobile Performance e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Ströer Mobile Performance para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do Ströer Mobile Performance. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Ströer Mobile Performance.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Ströer Mobile Performance.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Ströer Mobile Performance.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e utilizar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações do ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas à Ströer Mobile Performance.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie o link para a Ströer Mobile Performance para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Ströer Mobile Performance envia automaticamente dados de custo de CPI no link de atribuição para todas as instalações.

Para ver a lista completa de parceiros compatíveis com dados de custo, clique <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">aqui</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Ströer Mobile Performance, independentemente de o parceiro atuar como ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a Ströer Mobile Performance, a aba de permissões está ativa e você pode conceder controle à Ströer Mobile Performance.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo.

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-str%C3%B6er-mobile-performance=configura%C3%A7%C3%A3o-do-str%C3%B6er-mobile-performance h_01HJS1HC2Q3DAFRS8VJ9F3N5DP=configura%C3%A7%C3%A3o-do-str%C3%B6er-mobile-performance h_01HJS1HC2QQKDQR5EF5DBJMYRQ=dica h_01HJS1HC2Q5YXB8Q8XNNMGG44S=integration-tab activate-partners=ativar-parceiros h_01HJS1HC2QYD5B3ZM06SVE42SK=ativar-parceiros default-postbacks=postbacks-padr%C3%A3o h_01HJS1HC2QK20MTWR68JNP49QV=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1HC2R1WET88A5HX3F20W7=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1HC2RVNDZD3AC967A38KN=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJS1HC2RBBX2BMHVPSPW3VD5=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJS1HC2RQADFCQ2MHD0E60NC=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS1HC2RMPPRFZR2X02KGDD0=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS1HC2R1PVYA6N2QSHHFWVZ=cost-tab h_01HJS1HC2R34B2SQDBW4D3JEC5=ad-revenue-tab h_01HJS1HC2RZX1WPTF60M0ARKTV=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJS1HC2RW0SPDXWBA7H6SRGP=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
