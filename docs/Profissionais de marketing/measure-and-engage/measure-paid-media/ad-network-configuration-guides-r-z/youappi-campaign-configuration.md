---
title: Configuração de campanhas da YouAppi
metadata:
  keywords:
    - Advertisers
    - YouAppi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-20T07:14:26Z'
  edited_at: '2026-08-19T00:26:47Z'
  id: 212932106
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/212932106
---
> **Visão geral:** YouAppi, um parceiro integrado de ad network da AppsFlyer, é uma plataforma líder em growth marketing mobile para marcas premium de mobile. Além da atribuição mobile baseada em cliques, a YouAppi também oferece atribuição de custo, receita de anúncios, retargeting e view-through, que podem ser registradas com a AppsFlyer.

Para configurar suas campanhas com a YouAppi, siga as etapas abaixo.

<div id="setting-up-youappi" />

## Configurando a YouAppi

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A configuração da YouAppi inclui 4 abas ativas: Integração, link de atribuição, custo e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="note" />

> 📘 **Nota**
>
> Como uma all-installs network, a YouSppi prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a YouAppi.

<div id="general-settings" />

### Configurações gerais

**trackerToken**

A YouAppi se conecta à AppsFlyer por meio de um trackerToken. Se você ainda não tem o trackerToken, deve obtê-lo com a YouAppi para continuar com a integração.

**Habilitar a atribuição de view-through**

Alterne isso para LIGADO se quiser atribuir instalações view-through da YouAppi. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a YouAppi após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à YouAappi.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à YouAppi.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a YouAppi por meio de postbacks.

1. Digite o trackerToken novamente.
2. Ative Postbacks de eventos in-app.
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a este parceiro** para eventos provenientes **apenas** de usuários atribuídos a este parceiro.  
   **- Eventos atribuídos a qualquer parceiro ou orgânico** para que toda a sua base de usuários esteja disponível para ser reportada ao parceiro.
4. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no seu aplicativo ou de eventos server-to-server.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no lado da YouAppi.  <br />Obtenha o ID de evento correspondente da YouAppi e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Youappi para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais da Youappi. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Youappi.  
  **Parâmetro do link de atribuição:** c
* **Conjunto de anúncios** - defina o nome do conjunto de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Youappi.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina o nome do anúncio para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Youappi.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações do ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas à YouAppi.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o à YouAppi para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente instalações (primeiras aberturas) que acontecem durante essa janela de lookback, após uma impressão de anúncio, são atribuídas à YouAppi, desde que não haja nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o à YouAppi para ser ativado quando um anúncio correspondente for assistido, normalmente durante 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas à YouAppi, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que mesmo que a atribuição esteja desativada para a YouAppi, a aba de permissões está ativa e você pode conceder controle à YouAppi.

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

<div id="agency-permissions" />

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Opção principal*** - defina como Ativado para exibir as opções de permissões da agência
* ***Permitir acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-youappi=configurando-a-youappi h_01HK29DCA2B0VJM46KYCPWZ0V0=configurando-a-youappi h_01HK29DCA3XH6B98018C6G5MQY=dica h_01HK29DCA3J3TVPAEEH00T1RS8=integration-tab activate-partner=ativar-parceiro h_01HK29DCA3E890TQ7MZ8BEEA5J=ativar-parceiro h_01HK29DCA3KGV3S44XQ52ZV8YM=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HK29DCA3SR6BGN8PD8X4R198=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HK29DCA390TAZGD1A1EM06VY=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK29DCA3VQRZT8SYTQ5T0Z8F=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HK29DCA3ESN9EA4RKE1F6HE9=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HK29DCA3CJ5J19D7MGN9ZAWB=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HK29DCA3BGEC5VVC2X00M6HQ=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HK29DCA30YW2PTWKF0HSPG9Q=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HK29DCA3DSF3D8GETECYCZXE=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HK29DCA33HGQRRNXN096W2HY=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HK29DCA3PRMEEYGB15JWD5N7=cost-tab h_01HK29DCA4KNSAG2XYZQNX26S9=ad-revenue-tab h_01HK29DCA4EV987C7GPPXSKS7V=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HK29DCA4ZEYMM46NYRH6VWW1=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HK29DCA4923EKBV6X8DBCWFZ=permiss%C3%B5es-da-ag%C3%AAncia" />
