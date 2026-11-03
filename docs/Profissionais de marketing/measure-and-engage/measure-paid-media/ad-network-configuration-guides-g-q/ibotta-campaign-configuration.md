---
title: Configuração de campanha da Ibotta
metadata:
  keywords:
    - Advertisers
    - Ibotta
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-02-18T07:55:23Z'
  edited_at: '2026-09-09T00:24:12Z'
  id: 360000295445
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/360000295445
---
> **Em resumo:** a Ibotta, uma parceira de ad network integrada à AppsFlyer, facilita para os consumidores ganhar cashback em compras do dia a dia por meio de um único aplicativo para smartphone.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ibotta.png?v=1" width="119px" />

## Configurando a Ibotta

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Se você não tiver uma conta, entre em contato com o parceiro para abrir uma antes de configurar a integração.

**Para ativar a integração:**

1. Na AppsFlyer, acesse a guia **Colaborar > Integrações de parceiros > Marketplace**.  
    **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na guia **Integração**, ative o botão de alternância **Ativar parceiro**.   
    **Observação:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**.   
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de parceiros.</Anchor>

> 👍 **Atenção**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Ativar parceiro

Em seu **primeiro acesso**, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Postbacks padrão

Envie postbacks automáticos para a Ibotta após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Ibotta.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Ibotta por meio de postbacks.

> 👍 **Atenção**
>
> Para uma integração simples e rápida, selecione **Enviar todos os eventos excluindo o valor da receita** ou **Enviar todos os eventos incluindo o valor da receita**

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado da Ibotta.  <br />Obtenha o ID do evento correspondente da Ibotta e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Ibotta para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais da Ibotta. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Ibotta.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Ibotta.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Ibotta.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder</Anchor> as limitações de ID do site.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para obter mais informações sobre **<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">a Estrutura e os parâmetros do link de atribuição da AppsFlyer</Anchor>.**

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas à Ibotta.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Ibotta para que seja ativado quando os leads clicarem em um anúncio correspondente.

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

Nesta guia, você pode selecionar as permissões a serem concedidas à Ibotta, caso o parceiro atue como uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Ibotta, a guia de permissões continua ativa e você pode conceder controle à Ibotta.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos seus dados agregados de usuários fidelizados*** - apenas aos dados de usuários fidelizados do próprio parceiro
* ***Permitir acesso aos seus dados agregados de eventos in-app** -* apenas aos dados de eventos in-app do próprio parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-ibotta=configurando-a-ibotta h_01HKA2KDA0JDAF8VEXFH57Q9DP=configurando-a-ibotta h_01HKA2KDA0TVNGZQ7EN899112F=aten%C3%A7%C3%A3o h_01HKA2KDA05VRNN6YYTBS0AAYD=integration-tab activate-partner=ativar-parceiro h_01HKA2KDA0GA8GHDP2177EYV3Z=ativar-parceiro inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKA2KDA0J38WY51ZCP77J7A6=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKA2KDA0HKAP9ACF2V8ZCPHX=aten%C3%A7%C3%A3o-1 h_01HKA2KDA0QG78TCTKQKPZR0JV=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKA2KDA0YP8SYP4YJ5NG5QSN=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKA2KDA0VPPYRMPY3S11ASX5=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKA2KDA0CZSSXW8DTCBTQ022=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKA2KDA18SHG1YAZNTE3TBZ8=cost-tab h_01HKA2KDA1JS9YF2WEEHR2K5TD=ad-revenue-tab h_01HKA2KDA1EF0F3JG3F81V3FHG=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKA2KDA1Y2XEFHMV3XWQDDKW=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
