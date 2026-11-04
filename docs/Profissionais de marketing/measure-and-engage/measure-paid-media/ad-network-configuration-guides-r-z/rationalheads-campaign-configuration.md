---
title: Configuração da campanha RationalHeads
metadata:
  keywords:
    - rationalheads
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
  created_at: '2016-04-04T15:30:57Z'
  edited_at: '2026-08-19T00:25:45Z'
  id: 208277926
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/208277926
---
> **Em resumo:** a Remerge, um parceiro integrado de ad network da AppsFlyer, permite que profissionais de marketing de aplicativos veiculem anúncios personalizados e melhor posicionados. Além da atribuição mobile por clique, a Remerge oferece atribuição mobile view-through e retargeting por clique, que podem ser registrados na AppsFlyer.

<div id="setting-up-rationalheads" />

## Configuração da RationalHeads

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da RationalHeads inclui 3 abas ativas: Integração, link de atribuição e Permissões. Clique nos itens abaixo para saber mais sobre a configuração dessas abas.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="general-settings" />

### Configurações gerais

**ID da Parte**

A RationalHeads se conecta à AppsFlyer por meio de um ID da Parte exclusivo. Se você ainda não tiver o ID da Parte e a senha, deverá obtê-los com a RationalHeads para continuar com a integração.

<Image alt="Rationalheads_msc_new_2.png" src="https://files.readme.io/7e93003c13d4fa1e60bee4120307691b618757a7c55a271561827823005b86c3-360002076529.png" width="317px" />

<div id="default-postbacks" />

### Postbacks padrão

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Envie postbacks automáticos para a RationalHeads após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à RationalHeads.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Aqui, você pode mapear seus eventos da AppsFlyer com a RationalHeads por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no lado da RationalHeads.  <br />Obtenha o ID do evento correspondente com a RationalHeads e insira-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à RationalHeads para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais da RationalHeads. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a RationalHeads.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da RationalHeads.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da RationalHeads.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de site IDs usados e utilize o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de site ID</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>,

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas à RationalHeads.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a RationalHeads para ser ativado quando os leads clicarem em um anúncio correspondente.

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

Nesta aba, você pode selecionar as permissões a serem concedidas à RationalHeads, seja o parceiro uma ad network, uma agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a RationalHeads, a aba de permissões está ativa e você pode conceder controle à RationalHeads.

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

<div data-zendesk-anchors="setting-up-rationalheads=configura%C3%A7%C3%A3o-da-rationalheads h_01HJRZB6JCPYZZJ3QWS9BRJPSX=configura%C3%A7%C3%A3o-da-rationalheads h_01HJRZB6JC4GDCV3RVGJBFTPAT=dica h_01HJRZB6JCE5G700RRHGJY3M4A=integration-tab general-settings=configura%C3%A7%C3%B5es-gerais h_01HJRZB6JCXARZ29M8RCP30VBD=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJRZB6JCXR6ZHH3YV05W6JY1=postbacks-padr%C3%A3o activate-partner=ativar-parceiro h_01HJRZB6JCW3C1AWRS4041SKJP=ativar-parceiro inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZB6JDH6A108JYXEST4AQY=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZB6JDG7YQD0ANE4W8C55C=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJRZB6JDM91MC9B4VXCHEW6Z=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJRZB6JDQ148X9J0XCFPVZD1=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJRZB6JDZ27KM6N7GVZX54CW=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJRZB6JDJG6HVCEXMC5S30NM=cost-tab h_01HJRZB6JDTJE0K27Y4XTJG7QX=ad-revenue-tab h_01HJRZB6JDD32KPQ13CTEEMEBB=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJRZB6JD6412B28R5N8MRVH3=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
