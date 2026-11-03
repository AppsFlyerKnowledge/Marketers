---
title: '[Legacy] Configuração da integração do X Ads (antigo Twitter Ads)'
deprecated: true
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-06-22T11:41:06Z'
  edited_at: '2026-09-16T00:30:39Z'
  id: 36433415114769
  locale: pt
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/pt/articles/36433415114769
---
> **Resumo:** integre sua conta do X Ads com a AppsFlyer para exibir dados de atribuição de campanhas do X Ads.

## Conectando sua conta do X Ads à AppsFlyer

<Accordion title="Assista">

<Embed title="[Legacy] Configuração da integração do X Ads (antigo Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Leia">

> 📘 **Antes de começar:**
>
> Certifique-se de ter <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">adicionado um método de pagamento</Anchor> à sua conta do X Ads. Caso contrário, você não poderá ativar a integração do parceiro na AppsFlyer.

1. Acesse sua conta do X Ads em <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   Se você não for automaticamente direcionado para a página de anúncios, clique no botão Anúncios no canto superior esquerdo.
2. Quando solicitado a selecionar uma campanha **Simple (NEW)** ou **Advanced**, selecione **Advanced**.
3. Em **Campaign objective**, selecione **App Installs** ou **App re-engagements**, depois clique em **Next**.

   ![twitter-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. Escolha seu aplicativo e clique no link da **parceira de mensuração mobile** .
5. Na página **Conversion tracking** , clique em **Go to AppsFlyer**. 

   ![twitter-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. Uma notificação é exibida informando que você está prestes a deixar o Twitter Ads para acessar o site da AppsFlyer. Clique em **Go to AppsFlyer** e faça login no seu dashboard.

   <Image alt="twitter-go-to-appsflyer.png" src="https://files.readme.io/bca10eea5032a495fd38c996d0aa4a9f2db8a285211e6cf0860dd6f21bcfa670-36433422307601.png" width="576px" />
7. Na AppsFlyer, no menu lateral, selecione **Collaborate** > **Partner Integrations > Marketplace** guia.
8. Procure por **X Ads** e selecione-o.
9. Em **Integração** , aceite os Termos e condições do X Ads para Mobile App Conversion Recording (MACT) e clique em Salvar integração.
10. Habilite **Ativar parceiro** e clique em **Fazer login com o X Ads**.
11. Autorize a AppsFlyer a usar sua conta do X Ads clicando em **Autorizar aplicativo**.

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Habilite novamente a opção **Ativar parceiro** para exibir as configurações da aba **Integração** e ativar a atribuição.  
    **Atenção:** o toggle deve permanecer ativo enquanto você trabalhar com o parceiro. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
13. Selecione suas contas do X Ads para ativá-las e, em seguida, clique em **Salvar e fechar**.

    ![twitter_account_name.png](https://files.readme.io/d74e9b3edd08c4ca3396b95ae20e20db99bcbe1a220318403bd6c9d6f9600282-36433415108497.png)

</Accordion>

## Configuração de atribuição do X Ads

Para acessar uma descrição detalhada do header da página de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A **aba de integração** se divide em diferentes seções, conforme descrito abaixo. O <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">parceiro deve ser ativado</Anchor> na primeira visita para permitir sua configuração.

### Conta de anúncios conectada

Selecione as contas para ativar a atribuição.

![Twitter_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

### Atribuição de click-through

Use a barra deslizante para definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao X Ads.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 30 dias. Recomendamos definir a janela de lookback de click-through para 14 dias, para alinhar com o X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente instalações (primeiras aberturas) que acontecem durante essa janela de lookback, após uma impressão de anúncio, são atribuídas ao X Ads, desde que não haja nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias. Recomendamos definir a janela de visualização de lookback para 1 dia para corresponder à janela do X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

### Configurações de reengajamento

Para campanhas de retargeting no X Ads, a AppsFlyer oferece **Reengajamento** somente para a mensuração. Nesse caso, isso representa o engajamento de um usuário que já tem o app instalado com uma campanha de retargeting. **Atualmente, a mensuração de reatribuição não é compatível com o X Ads.**

> 🚧 **Importante!**
>
> Certifique-se de que o retargeting esteja habilitado para o aplicativo na página de configurações do aplicativo. Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">aqui</Anchor>.

#### Janela de lookback de reengajamento por click-through

Defina a duração da **Janela de lookback de reengajamento por clique** (o período máximo após o clique em um anúncio, durante o qual um usuário redirecionado pode ser atribuído ao anúncio). Você pode definir o valor em horas (até 23) ou dias (1 a 30).

![twitter-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

#### Janela de lookback de reengajamento por view-through

Para começar a atribuir impressões de anúncios de retargeting, ative a **Atribuição de reengajamento por exibição**.

Em seguida, defina a duração da **Janela de lookback de reengajamento por exibição** (o período máximo depois de um anúncio ser visualizado, durante o qual um usuário redirecionado pode ser atribuído ao anúncio). Você pode definir o valor em horas (até 23) ou dias (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### Janela de reengajamento

Defina a duração da **Janela de reengajamento** (o período em que os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting). Você pode definir os valores em dias (1 a 90), horas (até 23) ou até mesmo vitalícios:

![Twitter-reengagement-window.png](https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png)

### Configurações de eventos in-app

Nessa seção você pode mapear os eventos da AppsFlyer com o parceiro por meio de postbacks.

[![Os postbacks seguem o](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**Para configurar os postbacks de eventos na aplicação:**

1. Defina o **Partner ID** (se necessário).
2. Ative o **postback de eventos in-app.**
3. Clique em **Adicionar evento** para adicionar um SDK ou evento S2S à lista.
4. Preencha os parâmetros necessários de acordo com a tabela abaixo.

| Parâmetro | A descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. Possíveis <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">configurações de mapeamento</Anchor>:<ul><li>**Campo de texto:** Obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li><li>**Como está**: envie os eventos como estão, sem mapeamento de nomes.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<br /><br /><br /><br />**<span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>Nota**<br />Para que o X Ads receba postbacks atribuídos à agência, você deve selecionar **Todas as fontes de mídia, incluindo orgânicas**. Caso contrário, o X Ads não receberá tais postbacks.<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: enviar todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envie todos os parâmetros **excluindo** o valor da receita.</li></ul> |

5. [Opcional] Clique em <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para definir condições para enviar determinados eventos in-app ao parceiro.  
   Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">postbacks de eventos in-app condicionais</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

O X Ads não utiliza links de atribuição para atribuição.

> 📘 **Atenção**
>
> Para todas as <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">redes de autorrelato (SRNs)</Anchor>, como Meta ads, Apple Search Ads, Google Ads, X Ads, etc., essa aba não é funcional, pois elas não utilizam links externos de atribuição.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba custo">

A integração de custos fornece os seguintes dados agregados:

* Dados de custo para suas campanhas, conjuntos de anúncios, anúncios, canal e geo/países. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.  
  **Atenção:** os dados de custo requerem uma assinatura <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Dados sobre cliques, impressões e dados enriquecidos (palavras-chave, nomes de campanha e nomes de conjunto de anúncios).

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não está disponível no momento para o X Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao X Ads, independentemente do parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que mesmo que a atribuição esteja desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao X Ads.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

### Permissões da ad network

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos dados agregados de usuário fiéis** — apenas aos dados de usuários fieis do parceiro
* **Permitir acesso aos dados agregados de eventos in-app** — apenas aos dados de eventos in-app próprios do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre como conceder <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad network.</Anchor>

### Permissões da agência

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">conceder permissões de agência</Anchor>.

</Accordion>

## Vídeo de configuração avançada do X Ads

<Accordion title="Assista">

<Embed title="[Legacy] Configuração da integração do X Ads (antigo Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| Caraterística | Observações |
| --- | --- |
| Atribuição de pre-roll indisponível | O X Ads não é compatível com a atribuição de MMPs para campanhas de pre-roll. |
| Nomes | O dashboard mostra IDs em vez de nomes para **line item names** (nomes de conjuntos de anúncios) e **post names** (nomes de anúncios). Isso acontece pois a AppsFlyer recebe do X Ads somente os IDs desses elementos, e não seus nomes. |
| Custo (3) | Para X Ads, os dados de custo de campanhas (que têm apenas instalações SKAN, sem instalações "comuns") não estão disponíveis para agências. A integração de custo deve ser configurada pelo anunciante. E os dados só podem ser visualizados pelo anunciante. |

Especificações e limitações

</Accordion>

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=conectando-sua-conta-do-x-ads-%C3%A0-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=conectando-sua-conta-do-x-ads-%C3%A0-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=antes-de-come%C3%A7ar twitter-ads-attribution-setup=configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-do-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-do-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=conta-de-an%C3%BAncios-conectada h_01HDJVBAEZD89BSGHQTPR84HSC=conta-de-an%C3%BAncios-conectada clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HDJVBAEZFJWQ6FD4Q4GSPD76=atribui%C3%A7%C3%A3o-de-click-through viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HDJVBAEZ2H91WBHNSMRQYQ7H=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o reengagement-settings=configura%C3%A7%C3%B5es-de-reengajamento h_01HDJVBAEZZR1W06YH4XJSBKHV=configura%C3%A7%C3%B5es-de-reengajamento h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=importante reengagement-clickthrough-lookback-window=janela-de-lookback-de-reengajamento-por-click-through h_01HDJVBAEZ59ERYD2WQQYK6T37=janela-de-lookback-de-reengajamento-por-click-through reengagement-viewthrough-lookback-window=janela-de-lookback-de-reengajamento-por-view-through h_01HDJVBAEZSCK7430NJ8AMQYVY=janela-de-lookback-de-reengajamento-por-view-through reengagement-window=janela-de-reengajamento h_01HDJVBAEZCMWY5X47FEEFXTBX=janela-de-reengajamento inapp-event-postback-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=aten%C3%A7%C3%A3o h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network h_01HDJVBAF0BMSCKF6J9NJ019YJ=permiss%C3%B5es-da-ad-network agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HDJVBAF0W3ZE7J93CRE8EBRP=permiss%C3%B5es-da-ag%C3%AAncia advanced-twitter-ads-setup-video=v%C3%ADdeo-de-configura%C3%A7%C3%A3o-avan%C3%A7ada-do-x-ads h_01HDJVBAF0SJ93TNQ8WSFVE91P=v%C3%ADdeo-de-configura%C3%A7%C3%A3o-avan%C3%A7ada-do-x-ads h_01HGWGG2422VR9PFV88AMEHNT8=traits-and-limitations" />
