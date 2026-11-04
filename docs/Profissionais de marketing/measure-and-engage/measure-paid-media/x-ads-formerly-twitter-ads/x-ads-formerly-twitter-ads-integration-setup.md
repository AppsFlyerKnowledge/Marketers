---
title: Configuração de integração do X Ads (antigo Twitter Ads)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-09-16T00:30:45Z'
  id: 4410472471825
  locale: pt
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/pt/articles/4410472471825
---
> **Resumo:** integre sua conta do X Ads com a AppsFlyer para exibir dados de atribuição de campanhas do X Ads.

<div id="overview" />

## Visão geral

O X Ads é uma network avançada de self-reporting (SRN), que permite à AppsFlyer oferecer suporte à mensuração de campanhas do X Ads por meio da sua gama de métodos de mensuração que preservam a privacidade.

<div id="x-ads-attribution-flow-in-appsflyer" />

### Fluxo de atribuição do X Ads na AppsFlyer

**O fluxo de atribuição da AppsFlyer para o X Ads é o seguinte:**

1. A AppsFlyer recebe todos os dados de engajamento do X Ads via integração servidor a servidor (S2S) e atribui os engajamentos da seguinte forma:
   * Se tanto o evento de instalação quanto o de engajamento incluírem um mobile advertiser ID (MAID), a AppsFlyer faz o ID matching determinístico.
   * Se a instalação ou o engajamento não tiver um ID de publicidade, será usado um modelo probabilístico para atribuição, a menos que o cliente tenha configurado isso de outra forma.
2. A AppsFlyer envia todos os postbacks de instalação para o X Ads através da integração, mesmo quando instalação não é atribuída ao X Ads.
3. Quando o usuário rejeita o consentimento da App Tracking Transparency (ATT) e a Privacidade Avançada (AP) está ativa, certos campos dentro dos postbacks enviados ao X Ads se tornam restritos. Esses são os campos restritos:

   * X Ads engagement ID
   * Hashed device ID
   * Endereço IP
   * User-Agent

   [![_- seleção visual.png](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Conectando sua conta do X Ads à AppsFlyer

<div id="h_01HDJVBAEZATGM580CNC7BCVTN" />

<div id="note" />

> 📘 **Nota**
>
> Antes de começar, certifique-se de que você adicionou um método de pagamento à sua conta do X Ads. Caso contrário, você não poderá ativar a integração do parceiro na AppsFlyer.

1. Faça login na sua conta do X Ads em <Anchor target="_blank" href="https://business.x.com/en/advertising">X Ads.</Anchor>  
   Se você não for automaticamente levado para a página de anúncios, clique no botão Ads no canto superior esquerdo.
2. Quando solicitado a selecionar uma campanha **Simple (NEW)** ou **Advanced**, selecione **Advanced**.
3. Em **Campaign objective**, selecione **App Installs** ou **App re-engagements**, depois clique em **Next**.

   ![X-Ads-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. Escolha seu app e então clique no link **mobile measurement partner** .
5. Na página **Conversion tracking** , clique em **Go to AppsFlyer**.

   ![X-Ads-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. Uma notificação é exibida informando que você está prestes a deixar o Twitter Ads para acessar o site da AppsFlyer. Clique em **Go to AppsFlyer** e faça login no seu dashboard.
7. Na AppsFlyer, no menu lateral, selecione **Collaborate** > **Partner Integrations > Marketplace** aba.
8. Procure por **X Ads** e selecione-o.
9. Em **Integração** , aceite os Termos e condições do X Ads para Mobile App Conversion Recording (MACT) e clique em Salvar integração.
10. Habilite **Ativar parceiro** e clique em **Fazer login com o X Ads**.
11. Autorize a AppsFlyer a usar sua conta do X Ads clicando em **Autorizar aplicativo**.
12. Habilite novamente a opção **Ativar parceiro** para exibir as configurações da aba **Integração** e ativar a atribuição.  
    **Atenção:** o toggle deve permanecer ativo enquanto você trabalhar com o parceiro. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
13. Selecione suas contas do X Ads para ativá-las e, em seguida, clique em **Salvar e fechar**.

<div id="x-ads-attribution-setup" />

## Configuração de atribuição do X Ads

Para acessar uma descrição detalhada do header da página de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A **aba de integração** se divide em diferentes seções, conforme descrito abaixo. O <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">parceiro deve ser ativado</Anchor> na primeira visita para permitir sua configuração.

<div id="ad-account-connected" />

### Conta de anúncios conectada

Selecione as contas para ativar a atribuição.

![X-Ads_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

**Atenção:** Você pode conectar até 200 contas de anúncios na AppsFlyer. Para evitar atingir esse limite e garantir a atribuição contínua para todas as contas ativas, recomendamos remover quaisquer contas de anúncios que não estejam mais em uso.

<div id="advanced-privacy" />

### Privacidade avançada

Somente para aplicativos iOS: O toggle de **Privacidade Avançada (AP)** permite que você controle a quantidade de dados do usuário compartilhados com o X Ads nos postbacks. Essa configuração está em compliance com os requisitos de privacidade do iOS 14.5+.  
Quando o toggle AP está ativado:

* <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">modelo de Privacidade Avançada</Anchor>.
* Apenas <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">dados agregados e anônimos</Anchor> são compartilhados. Nenhum identificador a nível de dispositivo está incluído.

<div id="note-1" />

> 📘 **Atenção**
>
> * O toggle de Privacidade Avançada fica **ativado por padrão** assim que você ativa a integração do X Ads.
> * De acordo com o X Ads, manter a Privacidade Avançada **ativa** pode resultar em **menos** eventos de campanha em seus relatórios, limitando a otimização de performance no X Ads.

<div id="click-through-attribution" />

### Atribuição de click-through

Use a barra deslizante para definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao X Ads.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 30 dias. Recomendamos definir a janela de lookback de click-through para 14 dias, para alinhar com o X Ads.

![X-Ads_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

<div id="view-through-attribution-lookback-window" />

### Janela de lookback de atribuição de view-through

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente instalações (primeiras aberturas) que acontecem durante essa janela de lookback, após uma impressão de anúncio, são atribuídas ao X Ads, desde que não haja nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias. Recomendamos definir a janela de visualização de lookback para 1 dia para corresponder à janela do X Ads.

![X-Ads_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

<div id="reinstall-settings" />

### Configurações de reinstalação

Para habilitar a atribuição de reinstalação, ative **Atribuição de reinstalação**. A atribuição de reinstalação permite que você mensure usuários que reinstalam seu aplicativo na janela de reatribuição.

Não é necessário configurar janelas de lookback para atribuição de reinstalação, pois os valores são retirados das configurações de atribuição de instalação. Para mais informações, leia este artigo sobre a <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls">mensuração de reinstalações</Anchor>.

<div id="re-engagement-settings" />

### Configurações de reengajamento

Para campanhas de retargeting no X Ads, a AppsFlyer oferece suporte somente para a mensuração de **reengajamento**. Nesse caso, isso representa o engajamento de um usuário que já tem o app instalado com uma campanha de retargeting.

<div id="important" />

> 🚧 **Importante!**
>
> Certifique-se de que o retargeting esteja habilitado para o aplicativo na página de configurações do aplicativo. Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">aqui</Anchor>.

A atribuição de retargeting do X Ads inclui somente conversões de reengajamento.

Ative o botão de **atribuição de reengajamento** para começar a atribuir reengajamentos para o X Ads.

<div id="re-engagement-click-through-lookback-window" />

#### Janela de lookback de reengajamento por click-through

Defina a duração da **Janela de lookback de reengajamento por clique** (o período máximo após o clique em um anúncio, durante o qual um usuário redirecionado pode ser atribuído ao anúncio). Você pode definir o valor em horas (até 23) ou dias (1 a 30).

![X-Ads-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

<div id="re-engagement-view-through-lookback-window" />

#### Janela de lookback de reengajamento por view-through

Para começar a atribuir impressões de anúncios de retargeting, ative a **Atribuição de reengajamento por exibição**.

Em seguida, defina a duração da **Janela de lookback de reengajamento por exibição** (o período máximo depois de um anúncio ser visualizado, durante o qual um usuário redirecionado pode ser atribuído ao anúncio). Você pode definir o valor em horas (até 23) ou dias (1-7):

![X-Ads-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

<div id="re-engagement-window" />

#### Janela de reengajamento

Defina a duração da **Janela de reengajamento** (o período em que os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting). Você pode definir os valores em dias (1 a 90), horas (até 23) ou até mesmo vitalícios:

<Image alt="X-Ads-reengagement-window.png" src="https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png" width="628px" />

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuários ativos para retargeting

Defina um período de inatividade para evitar o registro de conversões de retargeting para usuários ativos dentro do período especificado. Veja mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window">período de inatividade de retargeting</Anchor>.

<div id="in-app-event-postback-settings" />

### Configurações de postbacks de eventos in-app

Nessa seção você pode mapear os eventos da AppsFlyer com o parceiro por meio de postbacks.

[![Os postbacks seguem o](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**Para configurar postbacks de eventos in-app:**

1. Defina o **Partner ID** (se necessário).
2. Ative o **postback de eventos in-app.**
3. Clique em **Adicionar evento** para adicionar um SDK ou evento S2S à lista.
4. Preencha os parâmetros necessários de acordo com a tabela abaixo.

| Parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. Selecione o evento AppsFlyer predefinido mais adequado. |
| **para usuários de** | Selecione a opção de envio para o evento:<br /><br /><br /><br />**Nota**<br />Para que o X Ads receba postbacks atribuídos à agência, você deve selecionar **Todas as fontes de mídia, incluindo orgânicas**. Caso contrário, o X Ads não receberá tais postbacks.<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: enviar todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envie todos os parâmetros **excluindo** o valor da receita.</li></ul> |

5. [Opcional] Clique em <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para definir condições para enviar determinados eventos na aplicação ao parceiro.  
   Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">postbacks de eventos in-app condicionais</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

O X Ads não utiliza links de atribuição para atribuição.

<div id="note-2" />

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

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não está disponível para a X Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao X Ads, independentemente do parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que mesmo que a atribuição esteja desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao X Ads.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da ad network

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos dados agregados de usuário fiéis** — apenas aos dados de usuários fieis do parceiro
* **Permitir acesso aos dados agregados de eventos in-app** — apenas aos dados de eventos in-app próprios do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre como conceder <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad network.</Anchor>

<div id="agency-permissions" />

### Permissões da agência

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">conceder permissões de agência</Anchor>.

</Accordion>

<div id="x-ads-features" />

## Recursos do X Ads

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="Mobile app promotion no X Ads">

O Mobile App Promotion do X Ads é um método utilizado para promover aplicativos no X Ads. Isso permite que os anunciantes promovam seus aplicativos usando um design exclusivo para o card de um aplicativo, impulsionando instalações, engajamento e deep linking. Os usuários podem facilmente instalar e colaborar com aplicativos diretamente a partir da linha do tempo do X Ads.

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="Web-to-App: mensurando a atividade no app para campanhas fora do app (apenas Android)">

A integração da AppsFlyer com o X Ads permite a mensuração da atividade do aplicativo — incluindo instalações, reengajamentos e eventos in-app — para **outras campanhas** fora do mobile no Android.

Por exemplo, mesmo que o destino do anúncio seja uma **web landing page**, as instalações do aplicativo e outras atividades pós-instalação ainda podem ser mensuradas, permitindo a mensuração da jornada do usuário web-to-app (W2A).

Para mensurar a atividade do aplicativo a partir de outras campanhas no X e obter insights valiosos sobre o comportamento do usuário, siga essas etapas no X Ads Manager:

1. Vá para o formulário de criação de campanha no X Ads Manager.
2. Em **Delivery**, ative a mensuração de **App Conversions** para ativar o rastreamento de instalações e conversões no aplicativo resultantes da campanha. Veja mais detalhes na <Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">documentação do X Ads</Anchor> (em *"Measuring app conversions on non-app objectives"*).

<div id="important-1" />

> 🚧 **Importante!**
>
> No momento, essa funcionalidade está disponível **apenas para Android**.

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="Interoperação da SKAN no X Ads e na AppsFlyer">

O X Ads envia dados de postback da SKAdNetwork por meio de uma API dedicada. Os dados de SKAN do X Ads são exibidos no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard da SKAN</Anchor>.

O X Ads enriquece os postbacks da SKAN com os seguintes campos de dados:

* Campaign name
* ID da campanha
* Nome do Adset
* Adset ID

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="Privacidade do usuário no X Ads">

Os anunciantes e usuários do X Ads podem controlar como eles compartilham informações com anunciantes e parceiros de negócios:

* A partir de **31 de julho de 2021**, os anunciantes que **não estão inscritos** no programa de Advanced Mobile Measurement (AMM) do X Ads não receberão mais dados a nível de usuário do X Ads MACT. Como resultado, **todos os dados do X Ads serão restritos** nas ferramentas de dados brutos da AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">Saiba mais sobre as restrições de dados do X Ads.</Anchor>
* Se o anunciante estiver no programa AMM e o usuário tiver reconhecido o aviso de privacidade, **nenhuma restrição de dados brutos se aplicará**.
* Independentemente do status do AMM, se o usuário estiver na União Europeia e concordou em compartilhar dados com parceiros comerciais, **nenhuma restrição de dados brutos se aplicará**.
* Se o usuário estiver na União Europeia e **não** concordou em compartilhar dados com parceiros comerciais, as**restrições de dados brutos serão aplicadas**.
* Os dados de atribuição agregados são corretamente refletidos na AppsFlyer e não são afetados pela política do X Ads.

Através do programa AMM, os anunciantes podem receber dados de usuário mais completos, concedendo o direito de realizar uma auditoria ao X Ads. Essa auditoria garante que os dados do X Ads sejam usados exclusivamente para fins de mensuração, de acordo com os padrões da indústria e as leis de proteção de dados.

<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">Saiba mais sobre o programa AMM na seção de FAQ</Anchor>. Para mais detalhes, entre em contato com seu Account Manager do X Ads.

</Accordion>

<div id="advanced-srn-parameter-names" />

## Nomes de parâmetros de Advanced SRN

Os seguintes campos na integração de Advanced SRN do X Ads **substituem** os campos legados no dashboard, relatórios agregados e dados brutos em nível de evento na AppsFlyer.

| **AppsFlyer**  <br />**Coluna de dados** | **SRN Legada** | SRN Avançada |
| --- | --- | --- |
| **PID** | Twitter | Twitter |
| **Nome da campanha** | Nome da campanha | Campaign name |
| **ID da campanha** | Campaign ID  <br />(base36: diferente do dashboard do X, por exemplo 21I3V9) | Campaign ID  <br />(base10: igual ao dashboard do X, por exemplo 123456789) |
| **Nome do adset** | Line Item ID  <br />(base36: diferente do dashboard do X, por exemplo 21I3V9) | Nome do item da linha |
| **Adset ID** | Line Item ID  <br />(base36: diferente do dashboard do X, por exemplo 21I3V9) | Line Item ID  <br />(base10: igual ao dashboard do X, por exemplo 123456789) |
| **Nome do anúncio** | Tweet ID | Ad Name  <br />(se disponível) |
| **ID do anúncio** | Tweet ID | Tweet ID |
| **Tipo de correspondência** | srn | id\_matching / probabilistic |

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Atribuição de pre-roll indisponível | O X Ads não é compatível com a atribuição de MMPs para campanhas de pre-roll. |
| Nome do anúncio "sem título" | O nome do anúncio não é um campo obrigatório no modelo de dados do X Ads (antigo Twitter), portanto, ele pode estar ausente. Quando o nome do anúncio não está definido no X Ads Manager, a AppsFlyer o exibe como **"untitled".** |
| Custo | Para X Ads, os dados de custo de campanhas (que têm apenas instalações SKAN, sem instalações "comuns") não estão disponíveis para agências. A integração de custos deve ser configurada pelo anunciante. Os dados só podem ser visualizados pelo anunciante. |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01JV7CGQNZNEM3P98K6KSYKB0D=vis%C3%A3o-geral xads-attribution-flow-in-appsflyer=fluxo-de-atribui%C3%A7%C3%A3o-do-x-ads-na-appsflyer h_01JZG83EKX39SF8355EW62C462=fluxo-de-atribui%C3%A7%C3%A3o-do-x-ads-na-appsflyer connecting-your-X-Ads-ads-account-to-appsflyer=conectando-sua-conta-do-x-ads-%C3%A0-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=conectando-sua-conta-do-x-ads-%C3%A0-appsflyer h_01JV7D6AWYQ981HY6C130B021B=nota X-Ads-ads-attribution-setup=configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-do-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-do-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=conta-de-an%C3%BAncios-conectada h_01HDJVBAEZD89BSGHQTPR84HSC=conta-de-an%C3%BAncios-conectada xads_advanced_privacy_toggle=privacidade-avan%C3%A7ada advanced-privacy=privacidade-avan%C3%A7ada h_01JV7HVQJ2GTP74G6JYB300E71=aten%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HDJVBAEZFJWQ6FD4Q4GSPD76=atribui%C3%A7%C3%A3o-de-click-through viewthrough-attribution-lookback-window=janela-de-lookback-de-atribui%C3%A7%C3%A3o-de-view-through h_01HDJVBAEZ2H91WBHNSMRQYQ7H=janela-de-lookback-de-atribui%C3%A7%C3%A3o-de-view-through reinstall-settings=configura%C3%A7%C3%B5es-de-reinstala%C3%A7%C3%A3o h_01HDJVBAF0XRWRZJQSS4STH7YN=configura%C3%A7%C3%B5es-de-reinstala%C3%A7%C3%A3o reengagement-settings=configura%C3%A7%C3%B5es-de-reengajamento h_01HDJVBAEZZR1W06YH4XJSBKHV=configura%C3%A7%C3%B5es-de-reengajamento h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=importante reengagement-clickthrough-lookback-window=janela-de-lookback-de-reengajamento-por-click-through h_01HDJVBAEZ59ERYD2WQQYK6T37=janela-de-lookback-de-reengajamento-por-click-through reengagement-viewthrough-lookback-window=janela-de-lookback-de-reengajamento-por-view-through h_01HDJVBAEZSCK7430NJ8AMQYVY=janela-de-lookback-de-reengajamento-por-view-through reengagement-window=janela-de-reengajamento h_01HDJVBAEZCMWY5X47FEEFXTBX=janela-de-reengajamento ignore-active-users=ignorar-usu%C3%A1rios-ativos-para-retargeting h_01JVC3PWDR9KHEFBQF5NWHCQJN=ignorar-usu%C3%A1rios-ativos-para-retargeting inapp-event-postback-settings=configura%C3%A7%C3%B5es-de-postbacks-de-eventos-in-app h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=configura%C3%A7%C3%B5es-de-postbacks-de-eventos-in-app h_01HDJVBAEZATGM580CNC7BCVTN=nota h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=aten%C3%A7%C3%A3o-1 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network h_01HDJVBAF0BMSCKF6J9NJ019YJ=permiss%C3%B5es-da-ad-network agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HDJVBAF0W3ZE7J93CRE8EBRP=permiss%C3%B5es-da-ag%C3%AAncia x-ad-features=recursos-do-x-ads h_01JZWQA6DXRZ17SRVT4HM2MQSH=recursos-do-x-ads h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=importante-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=nomes-de-par%C3%A2metros-de-advanced-srn advanced-srn-parameter-names=nomes-de-par%C3%A2metros-de-advanced-srn traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01JYGPBHHNQARG3GRMQJA95JKD=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
