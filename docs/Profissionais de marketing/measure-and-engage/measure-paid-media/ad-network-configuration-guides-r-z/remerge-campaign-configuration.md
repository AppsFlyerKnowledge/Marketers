---
title: Configuração da campanha Remerge
metadata:
  keywords:
    - Re-Targeting
    - Retargeting
    - Remerge
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
  created_at: '2017-01-02T16:20:43Z'
  edited_at: '2026-09-10T00:25:20Z'
  id: 115000172003
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/115000172003
---
> **Em resumo:** a Remerge, uma parceira integrada de ad network da AppsFlyer, permite que profissionais de marketing de aplicativos veiculem anúncios personalizados em posições mais adequadas. Além da atribuição mobile por clique, a Remerge oferece atribuição mobile view-through e retargeting por clique, que podem ser registrados na AppsFlyer.

## Como configurar a Remerge

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

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Nota**
>
> Como uma all-installs network, a Remerge prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a Remerge.

### Atribuição de instalação e reengajamento

Esses dois toggles permitem atribuir à Remerge os usuários que apenas visualizaram seu anúncio, mas não clicaram nele.

* Ative ***Atribuição view-through de instalação*** para atribuir à Remerge novas instalações geradas apenas por impressões.
* Ative ***Atribuição view-through de reengajamento*** para atribuir à Remerge novos reengajamentos de usuários existentes gerados apenas por impressões.

### Postbacks padrão

Envie postbacks automáticos para a Remerge após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Remerge.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Remerge.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Remerge por meio de postbacks.  
Se você optar por mapear todos os eventos (incluindo e excluindo os respectivos valores de receita), o evento af\_app\_opened NÃO será enviado para a Remerge.  
Se desejar enviar eventos af\_app\_opened para a Remerge, você deverá adicionar cada evento manualmente.

1. Ative Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Preencha os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta aba, você pode criar os links de atribuição que deseja enviar à Remerge para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais da Remerge. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Remerge.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Remerge.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Remerge.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e utilizar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros do assinante** - use qualquer um dos 5 parâmetros do assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

### Configurações de retargeting

Quando ativado, o AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de clique. Observe que, atualmente, o retargeting é compatível apenas com a atribuição click-through, e não com a atribuição view-through.  
**Parâmetro do link de atribuição:** is\_retargeting.

O exemplo a seguir abaixo é exibido quando o retargeting está ativado.

1. Link padrão vs. OneLink

Selecione a opção de ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Planeje usar somente <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para deep linking

select ***Usar OneLink*** para:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar OneLink altera o link de registro de clique, de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

2. Deep Link URL

Use este campo se o link tiver como objetivo fazer Deep linking de usuários para uma atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição:** af\_dp  
Você pode encontrar mais informações sobre a solução de Deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

3. Janela de reengajamento

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição:** af\_reengagement\_window

### Atribuição de click-through

Esse controle deslizante permite definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras aberturas) que ocorrerem dentro da janela de lookback podem ser atribuídas à Remerge.

**Parâmetro do link de atribuição:** af\_click\_lookback

Veja mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Remerge para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer recebe dados de custo via API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custo da ad network</Anchor> para ver todos os detalhes sobre as dimensões, métricas e recursos compatíveis. **Atenção:** os dados de custo exigem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a Remerge.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Remerge, conforme o parceiro atue como ad network, agência ou até mesmo ambos. Observe que, mesmo que a Atribuição esteja desativada para o Remerge, a aba de permissões está Ativa e você pode conceder Controle ao Remerge.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

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

<div data-zendesk-anchors="setting-up-remerge=como-configurar-a-remerge h_01HJRZQ2X3A955H1T76X8GF35A=como-configurar-a-remerge h_01HJRZQ2X45PTBDQARWHDSJS1V=integration-tab activate-partner=ativar-parceiro h_01HJRZQ2X4PG81M9GYBGPNANGY=ativar-parceiro h_01HJRZQ2X4THDK9AV0MFGKD5GG=nota install-and-reengagement-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o-e-reengajamento h_01HJRZQ2X4KQHXXJH3F4TNABC4=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o-e-reengajamento default-postbacks=postbacks-padr%C3%A3o h_01HJRZQ2X4TY2DT0DTTEMJYWPG=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZQ2X549ZMW6SZGHPG6853=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZQ2X56BEBQ0FHJYCMGE4J=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJRZQ2X5EE1XDFN56VEEPWKM=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HJRZQ2X60JEVJYVK5X934DP4=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJRZQ2X6DGP82VBKNF86S0E0=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJRZQ2X61NZQB1JSMSRMNTH7=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJRZQ2X6M83KFXR58BS4B024=cost-tab h_01HJRZQ2X6GZ51M21S5PTD3NC4=ad-revenue-tab h_01HJRZQ2X67S37CAH31KNVRQPG=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJRZQ2X6CEX8T2A57JHBHERR=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
