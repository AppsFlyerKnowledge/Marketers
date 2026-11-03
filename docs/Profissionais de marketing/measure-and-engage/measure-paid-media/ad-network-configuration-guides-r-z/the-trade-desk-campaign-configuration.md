---
title: Configuração da campanha do The Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2026-09-15T00:24:59Z'
  id: 360000894849
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360000894849
---
> **Visão geral:** o Trade Desk, um parceiro integrado de ad network da AppsFlyer, usa sua solução de anúncios mobile aprimorada para criar campanhas estratégicas, escaláveis e inteligentes que atendam às necessidades dos usuários de vários dispositivos. O Trade Desk oferece atribuição mobile por clique, view-through e retargeting por clique, e tudo isso pode ser registrado através da AppsFlyer.

## Configurando o Trade Desk (TTD)

Siga estas etapas para ativar a métrica da campanha da AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Etapa 1: definir eventos de conversão no TTD">

1. No menu esquerdo da sua página do anunciante TTD, clique em **DADOS**.
2. No menu superior, clique em **Adicionar dados do aplicativo**.
3. Insira os seguintes campos na página **Criar dados do aplicativo**:
   * **Nome do aplicativo:** insira o nome do aplicativo.
   * **Sistema operacional:** selecione **Android** ou **iOS**.   
     **Observação:** o TTD é compatível com CTV em ambas as opções Android e iOS.
   * **Fornecedor de acompanhamento:** selecione **AppsFlyer**.
   * **Eventos:** clique em **ADICIONAR EVENTO** para adicionar eventos de conversão e digite os campos:
     * **NOME DO EVENTO**: digite o nome do evento.  
       **Observação:** certifique-se de que o nome esteja escrito exatamente como na AppsFlyer, incluindo as letras maiúscula e minúsculas, espaços e símbolos.
     * [Opcional] **DESCRIÇÃO**: adicione uma descrição.
     * [Opcional] **UTILIZAÇÃO DE DADOS COLETADOS**: selecione **Atribuição**. Esta opção inclui tanto a atribuição como o retargeting.
     * Para adicionar mais eventos, clique em **ADICIONAR EVENTO** e repita o processo.
   * **Fonte de crédito de conversão**: selecione a qual fonte atribuir as conversões, seja AppsFlyer ou The Trade Desk.   
     **Observação**:
     * Para mensurar Cross-Device e compra de TTD, selecione **The Trade Desk**.   
       Para uma visão holística da métrica não apenas no TTD, selecione **AppsFlyer**.
     * Nunca altere esta seleção durante uma campanha.
     * Certifique-se de selecionar a fonte correta antes de clicar em **CRIAR DADOS DO APLICATIVO**. Você não pode mudar sua fonte de crédito de conversão durante uma campanha.
4. Clique em **CRIAR DADOS DO APLICATIVO**.

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Etapa 2: definir eventos de conversão na AppsFlyer">

Para que a AppsFlyer defina eventos de conversão e permita que você envie postbacks de eventos para TTD, primeiro você precisa [integrar TTD com a AppsFlyer](/docs/the-trade-desk-campaign-configuration#integração-do-ttd-com-a-appsflyer) e definir as seguintes configurações:

* Configurações de integração (incluindo a configuração de postbacks de eventos)
* Link de atribuição
* Authorization: Bearer

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Etapa 3: mapear eventos de conversão definidos da AppsFlyer">

1. A partir do menu esquerdo do TTD, clique em **CAMPANHAS**.
2. Vá até **Campanhas** e selecione uma campanha da lista.
3. Clique em **Editar reportes e atribuição**.
4. Clique em **ADICIONAR FONTE DOS DADOS DE CONVERSÃO**.
5. Em **FONTES DOS DADOS DE CONVERSÃO**, selecione ou digite **AppsFlyer**. Os eventos da AppsFlyer agora são mapeados para eventos do TTD.
6. **CONCEITO ENTRE DISPOSITIVOS**:
   * Se na [Etapa 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Fonte de crédito de conversão) você escolheu que as conversões fossem atribuídas pelo TTD, selecione aqui **Household** para ver as conversões em todos os canais disponíveis (como mobile in-app e CTV).
   * Se você escolheu AppsFlyer na [Etapa 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), selecione aqui **Nenhum**.
7. Clique em **SALVAR**.

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Etapa 4: adicionar rastreadores de cliques e impressões aos criativos da campanha">

Nesta etapa, você adicionará os rastreadores de cliques e impressões que foram criados na AppsFlyer a cada um dos criativos no TTD.

1. Em **CAMPANHAS**, no menu esquerdo do TTD, clique em **CRIATIVOS** na aba superior.
2. Selecione um criativo a partir da lista de criativos associados à campanha atual.
3. Vá até **Acompanhamento**.
4. Copie o [link de atribuição](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) view-through da AppsFlyer e cole-o no campo URL de rastreamento de impressões do pixel 1x1.
5. Copie o link de atribuição click-through da AppsFlyer e cole-o no campo URL de click-through.
6. Clique **SALVAR ALTERAÇÕES**.
7. Repita esta etapa para cada um dos criativos associados à campanha.

</Accordion>

> 📘 **Observação**
>
> Se você escolheu que as conversões sejam atribuídas pelo TTD (na [Etapa 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), você pode editar as janelas de atribuição:
>
> 1. A partir do menu de ícones à direita de qualquer página TTD, clique na roda dentada para abrir a opção **Preferências do anunciante**.
> 2. Vá até **Janela de atribuição** e clique no botão de edição à direita.
> 3. Na página **Gerenciar janelas de atribuição**, edite as janelas de atribuição:
>    * **Janelas de deduplicação:** o número de conversões que você pode ver em um determinado período de tempo.
>    * **Janelas de atribuição da campanha:** o período de tempo desde a exposição do anúncio até a conversão.
> 4. Clique em **SALVAR**.

## Integração do TTD com a AppsFlyer

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do TTD inclui três abas ativas: Integração, Link de Atribuição e Permissões. Clique nos itens abaixo para ler sobre a configuração de abas.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

#### Ativar parceiro

Na sua primeira visita, você precisará habilitar a opção **Ativar parceiro** para configurar a integração. Essa opção deve permanecer ativada enquanto você trabalhar com TTD.  
Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

#### Privacidade avançada

Para aplicativos de iOS, há a opção <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">ativar Privacidade Avançada</Anchor>. Quando ativada, ela limita o compartilhamento de identificadores de usuários com o parceiro. Observe que quando a <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor> é ativada nas configurações do aplicativo, a opção **ativar Privacidade Avançada** é ativada por padrão. 

#### Configurações gerais

**Rastreador e identificação do anunciante**

O Trade Desk se conecta com a AppsFlyer através de um ID de rede único. Se você ainda não tem o Tracker\_ID e o advertiserid, você deve obtê-lo do Trade Desk para continuar com a integração.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Ativar atribuição de exibição**

Habilite **Ativar atribuição de exibição** para atribuir instalações de exibição a partir do The Trade Desk. O cursor de lookback de exibição está disponível na aba do link de atribuição (conforme descrito abaixo).

#### Postbacks padrão

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Envie postbacks automáticos para o The Trade Desk após as instalações e reengajamentos do usuário. Use esta seção para definir a fonte dos usuários que permitem o envio desses postbacks:

* **Somente este parceiro**: apenas para eventos provenientes de usuários atribuídos ao The Trade Desk.
* **Todas as fontes de mídia, incluindo orgânicas**: para ter toda a sua base de usuários disponível para ser relatada ao The Trade Desk.

> 📘 **Observação**
>
> Como uma network de todas as instalações, a The Trade Desk prefere receber postbacks de todas as novas instalações do seu aplicativo de qualquer fonte e recomenda selecionar **Todos os canais de mídia incluindo orgânico** para enviar todos os postbacks de instalação para a The Trade Desk.

#### Configurações de eventos in-app

Mapeie eventos da AppsFlyer com o TTD através de postbacks. Se o envio de postback estiver ativado, isso inclui eventos in-app rejeitados (eventos bloqueados pelo Protect360 ou eventos considerados não compatíveis com as regras de validação de destino).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**Para configurar postbacks de eventos in-app:**

1. Digite o **advertiserid** e o **Tracker\_ID**.
2. Ative **postback de eventos in-app.**
3. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
4. Quando disponível, selecione se deseja enviar eventos automaticamente ou manualmente. Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">enviar todos os eventos como eles são</Anchor>.
5. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página.
6. Complete os parâmetros necessários.
7. [Opcional] Clique em<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />para definir as condições para o envio de certos eventos in-app para o TTD.  
   Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">postbacks condicionais de eventos in-app</Anchor>.

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados"> mapeamento de eventos personalizados.</Anchor></li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: enviar todos os parâmetros **excluindo** o valor da receita.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Gerar e salvar links de atribuição e enviá-los à TTD para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para a UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.

#### Parâmetros do link de atribuição

Adicionar parâmetros ao link de atribuição permite realizar análises detalhadas. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui. Ao salvar o link de atribuição, todos os parâmetros configurados nesta aba são salvos.

Selecione quais parâmetros você deseja adicionar ao link de atribuição.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

#### Parâmetros padrão

| Nome | Descrição | Parâmetro |
| --- | --- | --- |
| ID do site | Defina seu parâmetro de site ID para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de site IDs e use o parâmetro de subsite ID, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de site ID</Anchor>. | af\_siteid |
| Nome da campanha | Adicione o nome de sua campanha para comparar diferentes campanhas em execução com o TTD. | C |
| ID da campanha | Adicione seu ID de campanha. | af\_c\_id |
| Adset ID | Adicione seu adset ID para comparar a performance de todos os seus anúncios por conjunto de anúncios. | af\_adset |
| ID do anúncio | Adicione seu ID do anúncio. | af\_ad\_id |

Você pode adicionar outros parâmetros para o link de atribuição. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estabelecer o link de atribuição</Anchor> e sobre o link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">estrutura e parâmetros</Anchor>.

#### Parâmetros para métrica de CTV

Você pode medir o tráfego de CTV com a AppsFlyer adicionando os seguintes parâmetros e valores:

| Parâmetro | Valor | Comentários |
| --- | --- | --- |
| redirect | false |  |
| af\_xplatform\_vt\_lookback | 1h a 72h | Qualquer valor entre 1 a 72 horas pode ser inserido |

#### Atribuição de cliques

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

Use a barra deslizante para definir o tempo máximo entre o clique e a instalação. Somente instalações (primeiras inicializações) que ocorrem dentro da janela de lookback são atribuídas.

Intervalo da janela de lookback: 1 a 23 horas ou 1 a 30 dias.

Parâmetro de link de atribuição: af\_click\_lookback

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques</Anchor>.

**Link de atribuição de clique:** contém todos os parâmetros que você incluiu na configuração do link de atribuição. Você pode copiar o link e enviá-lo ao parceiro para ser ativado quando seus contatos clicarem em um anúncio correspondente.

#### Atribuição de exibição

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Use a barra deslizante para definir o tempo máximo desde a impressão até a instalação. Somente instalações (primeiras inicializações) que acontecerem durante essa janela de lookback, após uma impressão de anúncio, serão atribuídas ao parceiro, desde que não haja outros cliques em relevantes.

Intervalo da janela de lookback: 1 a 24 horas

Parâmetro de links de atribuição: af\_viewthrough\_lookback

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição de view-through</Anchor>.

**Link de atribuição de exibição:** contém todos os parâmetros que você incluiu na configuração do link de atribuição. Você pode copiar o link e enviá-lo ao parceiro para ser ativado quando seus contatos clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba Cost (Custo)">

A integração de custos não está disponível para o The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Ad Revenue (Receita de anúncios)">

A receita de anúncios não está disponível para o The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Nesta aba, você pode selecionar as permissões para conceder ao The Trade Desk, quer atuem como uma ad network, agência, ou mesmo ambas. Observe que mesmo que a atribuição seja desativada para o Trade Desk, a aba de permissões pode estar ativa e você pode conceder controle ao The Trade Desk.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

#### **Permissões da rede de anúncios**

* **Permitir a configuração da integração:** permitir que o TTD configure a aba de integração, exceto em caso de postbacks de eventos in-app
* **Permitir a configuração de postbacks de eventos in-app:** permitir que o TTD configure o mapeamento de postback de evento in-app para si mesmo, na aba de integração
* **Permitir acesso ao seu relatório de retenção:** somente para os dados de retenção do próprio TTD
* **Permitir acesso a seus dados agregados de usuários fiéis:** somente para os dados de usuários fiéis do próprio TTD
* **Permitir o acesso aos dados agregados de seus eventos:** somente para os próprios dados de eventos in-app do TTD
* **Permitir acesso a seus dados de receita agregados:** somente para os dados de receita atribuídos ao TTD
* **Permitir acesso ao seu painel de controle Protect360:** somente para os dados do próprio Protect360 do TTD, desde que você tenha este recurso ativado

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=configurando-o-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=configurando-o-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=observa%C3%A7%C3%A3o integrating-ttd-with-appsflyer=integra%C3%A7%C3%A3o-do-ttd-com-a-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=integra%C3%A7%C3%A3o-do-ttd-com-a-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=ativar-parceiro h_01HH2DHQWYME21J7JV176N71P2=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01HH2DHQWYFJB3ZCWVZZ048AQP=privacidade-avan%C3%A7ada general-settings=configura%C3%A7%C3%B5es-gerais h_01HH2DHQWYN3CZZCFT9X2R2N9J=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HH2DHQWY1GPVP5W5R4XV2H9C=postbacks-padr%C3%A3o h_01HH2DHQWY284121FR8HSFGH45=observa%C3%A7%C3%A3o-1 inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HH2DHQWY0XM70BPE7222XE78=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o h_01HH2DHQWY4GXPMCV5JEBFERG6=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o default-parameters=par%C3%A2metros-padr%C3%A3o h_01HH2DHQWYZSECQWRQEKDB9KZH=par%C3%A2metros-padr%C3%A3o parameters-for-measuring-ctv=par%C3%A2metros-para-m%C3%A9trica-de-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=par%C3%A2metros-para-m%C3%A9trica-de-ctv clickthrough-attribution=atribui%C3%A7%C3%A3o-de-cliques h_01HH2DHQWYCFGJK4ZT9CXFX3X3=atribui%C3%A7%C3%A3o-de-cliques viewthrough-attribution=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HH2DHQWYP6S95MRAS39Q4RTT=atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HH2DHQWYCWYQFBDA19Z9BA8W=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
