---
title: Configuração da campanha da Cheetah Mobile
metadata:
  keywords:
    - cheetah mobile
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
  created_at: '2016-03-28T10:23:35Z'
  edited_at: '2026-09-10T00:24:00Z'
  id: 209731703
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/209731703
---
> **Em resumo:** a Cheetah Mobile, uma parceira integrada de ad network da AppsFlyer, tem como objetivo fornecer aplicativos líderes para usuários mobile em todo o mundo e conectar usuários a conteúdo personalizado na plataforma mobile. Além da atribuição mobile baseada em cliques, a Cheetah Mobile também oferece atribuição por custo e view-through, que você pode registrar com a AppsFlyer.

## Configurando a Cheetah Mobile

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

### Ativar parceiros

Na **primeira visita** aqui, você deve ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

> 📘 **Nota**
>
> Como uma all-installs network, a Cheetah Mobile prefere receber postbacks de todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Recomendamos selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação à Cheetah Mobile.

### Configurações gerais

**Habilitar a atribuição de view-through**

Alterne para LIGADO se quiser atribuir instalações view-through da Cheetah Mobile. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

Envie postbacks automáticos para a Cheetah Mobile após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Cheetah Mobile.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Cheetah Mobile.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Cheetah Mobile por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido pela Cheetah Mobile.  <br />Obtenha o ID do evento correspondente da Cheetah Mobile e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta aba, você pode criar os links de atribuição que deseja enviar à Cheetah Mobile para atribuir campanhas, conjuntos de anúncios ou anúncios individuais da Cheetah Mobile. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Cheetah Mobile.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Cheetah Mobile.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Cheetah Mobile.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site utilizados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas à Cheetah Mobile.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Cheetah Mobile para ser ativado quando os leads clicarem em um anúncio correspondente.

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas à Cheetah Mobile, desde que não tenha havido outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição por visualização aqui</Anchor>.

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o para a Cheetah Mobile para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Cheetah Mobile envia automaticamente dados criptografados de custo de CPI no link de atribuição para todas as instalações.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Cheetah Mobile, seja o parceiro uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Cheetah Mobile, a guia de permissões estará ativa e você poderá conceder controle à Cheetah Mobile.

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Opção principal*** - defina como Ativado para revelar as opções de permissões da agência
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na aba de integração
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir o acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-cheetah-mobile=configurando-a-cheetah-mobile h_01HKWB1JWHPMM479MHE32NEN3Q=configurando-a-cheetah-mobile h_01HKWB1JWHSGXPW48YRC2XRBK4=integration-tab activate-partners=ativar-parceiros h_01HKWB1JWHQH9FT3TW5CP8G45T=ativar-parceiros h_01HKWB1JWHXRJGWJD2J8RAYFZM=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HKWB1JWHHH6F8H8MA8DYD486=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKWB1JWHMAKZDHQG3MNCFFND=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKWB1JWHSW1S1DSTJEBD4ZW0=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKWB1JWHAGA1EVKGX1EHWSW5=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKWB1JWH7DFXA38WJ0Y2RCV5=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKWB1JWJS6QM7VPSGAY6Y296=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKWB1JWJTM5SH99NH5X8GVRX=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HKWB1JWJANK35Q2RJQ07Y19T=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKWB1JWJN47XHK6WY252SR28=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKWB1JWJG9KX8W7GS5HV0ZVY=cost-tab h_01HKWB1JWJJ4G8TK7F15T7CB4Z=ad-revenue-tab h_01HKWB1JWJS5RF65RD0KMA19GF=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKWB1JWJF19NSD07RBKEZTYX=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HKWB1JWJQ61908VTXKXABGEK=permiss%C3%B5es-da-ag%C3%AAncia" />
