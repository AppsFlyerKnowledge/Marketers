---
title: Configuração de campanha da Taptica
metadata:
  keywords:
    - taptica
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
  created_at: '2016-07-05T13:00:06Z'
  edited_at: '2026-09-08T00:25:14Z'
  id: 210118726
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/210118726
---
> **Em resumo:** a Taptica, um parceiro integrado de ad network da AppsFlyer, fornece soluções de marketing focadas em dados que impulsionam a execução e oferecem insights poderosos sobre a marca no mobile. Além da atribuição mobile baseada em cliques, a Taptica oferece atribuição de custo, retargeting e view-through, que podem ser registradas na AppsFlyer.

Para configurar suas campanhas com a Taptica, siga as etapas abaixo.

<div id="setting-up-taptica" />

## Configurando a Taptica

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da Taptica inclui 3 abas ativas: Integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o toggle **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

**Habilitar a atribuição de view-through**

Alterne para LIGADO se desejar atribuir instalações view-through da Taptica. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a Taptica após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Taptica.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Taptica.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear os eventos da AppsFlyer com a Taptica por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado da Taptica.  <br />Obtenha o ID do evento correspondente da Taptica e configure no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta aba, você pode criar os links de atribuição que deseja enviar à Taptica para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais da Taptica. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Taptica.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Taptica.  
  **Parâmetros do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos, em campanhas específicas da Taptica.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros do assinante** - use qualquer um dos 5 parâmetros do assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configurações de retargeting

Quando ativado, o AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de cliques. Observe que, atualmente, o retargeting é compatível apenas com a atribuição por clique e não com a atribuição view-through.  
**Parâmetro do link de atribuição:** is\_retargeting.

O exemplo a seguir abaixo é exibido quando o retargeting está ativado.

1. Link padrão vs. OneLink

Selecione a opção de ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Planeja usar somente <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep linking

select ***Use OneLink*** for:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar o OneLink altera o link de registro de cliques de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

2. Deep Link URL

Use este campo se o link se destinar a fazer deep linking de usuários para qualquer atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição:** af\_dp  
Você pode encontrar mais informações sobre a solução de deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

3. Janela de reengajamento

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas à Taptica.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Taptica para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas à Taptica, desde que não tenha havido nenhum outro clique relevante em anúncio.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o para a Taptica para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta guia, você pode selecionar as permissões a serem concedidas à Taptica, caso o parceiro atue como ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Taptica, a guia de permissões fica ativa e você pode conceder controle à Taptica.

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

<div id="agency-permissions" />

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Alternância principal*** - defina como Ativado para mostrar as opções de permissões da agência
* ***Permitir acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-taptica=configurando-a-taptica h_01HJS1NM4SSXEM83HWQPMV9JAF=configurando-a-taptica h_01HJS1NM4SNMBHCFKNFQJRJ76B=dica h_01HJS1NM4T0TJ91WZ3PTSYS4QQ=integration-tab activate-partner=ativar-parceiro h_01HJS1NM4TBMQFKSD8MR28XDRZ=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HJS1NM4TY71SZX6HF2FEWDJM=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJS1NM4T5KWZJBPW9NZX9B4E=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1NM4TJC317ZJA7ZP5FG93=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1NM4TAXE0PSFQFZ8WY335=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJS1NM4TY8VCKQAHAGYKC4S2=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HJS1NM4TFKAC93D0SMZD3AYJ=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJS1NM4T5NMQ360S8YTGMSF6=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS1NM4T3J870BWR9GXMR4E1=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HJS1NM4V649HCT6JY4HE6J0J=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJS1NM4VGNJ66P6ARHJA5Z1X=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJS1NM4VHFKRTYAEZ3X4FKF7=cost-tab h_01HJS1NM4VG74QAEFKJPZ3PCP7=ad-revenue-tab h_01HJS1NM4V01E1KECDG0WX3D59=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJS1NM4VKSJT38G04FFN400F=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HJS1NM4VMP8CG58Z134BB6CW=permiss%C3%B5es-da-ag%C3%AAncia" />
