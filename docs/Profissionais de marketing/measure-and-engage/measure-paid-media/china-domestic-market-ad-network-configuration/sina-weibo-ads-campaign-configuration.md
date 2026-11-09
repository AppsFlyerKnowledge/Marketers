---
title: Configuração de campanha do Sina Weibo Ads
metadata:
  keywords:
    - Advertisers
    - Sina Weibo Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-15T08:37:03Z'
  edited_at: '2026-09-16T00:26:43Z'
  id: 115004134086
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115004134086
---
> **Visão geral:** Sina Weibo Ads, uma ad network e parceira integrada da AppsFlyer, é uma das plataformas de rede social mais populares na China.

<div id="setting-up-sina-weibo-ads" />

## Configurando o Sina Weibo Ads

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   Para editar: vá para **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do Sina Weibo Ads inclui 3 abas ativas: Integração, link de atribuição e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

Essa seção é usada para conectar o parceiro à AppsFlyer. As mensagens relevantes para o anunciante em relação ao parceiro específico também aparecem aqui.

<div id="activate-partners" />

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Postbacks padrão

Se a atribuição/integração estiver habilitada para o parceiro, a AppsFlyer poderá enviar postbacks automáticos para ele após instalações, inicializações, reengajamentos e instalações rejeitadas do usuário. Use esta seção para definir a **fonte dos usuários** para a qual os postbacks são enviados.

<Image align="center" alt="Sina_Weibo_msc_new_2.png" src="https://files.readme.io/0f71568fd13ce9357f07282636e0b86fdbb9e9b1f6ef9db8ba673bb2066881aa-360002277585.png" />

A opção "**Somente eventos atribuídos a este parceiro**", apenas para usuários atribuídos ao parceiro, é selecionada por padrão.

Clique em **Guardar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Sina Weibo Ads para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais do Sina Weibo Ads. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução no Sina Weibo Ads.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Sina Weibo Ads.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos, em campanhas específicas do Sina Weibo Ads.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID de subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID de site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="" src="https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**Estrutura de link de atribuição e parâmetros da AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configurações de retargeting

Você pode adicionar qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Você pode encontrar todos os parâmetros de URL disponíveis da AppsFlyer aqui: <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**Estrutura de link de atribuição e parâmetros da AppsFlyer**</Anchor>

Quando ativado, o AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de cliques. Observe que, atualmente, o retargeting é compatível apenas com a atribuição clicável e não de exibição.

**Parâmetro do link de atribuição**: `is_retargeting`

A configuração abaixo é exibida quando o retargeting está ativado.

<Image align="center" alt="retargeting_settings.png" src="https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png" />

***Link padrão*** **vs.** ***OneLink***

Selecione a opção de ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Você planeja usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep linking

Selecione ***Usar OneLink*** para:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar o OneLink altera o link de registro de clique de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

***Deep Link URL***

Use este campo se o link for destinado a fazer Deep linking dos usuários para qualquer atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição**: `af_dp`  
Você pode encontrar mais informações sobre a solução de Deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

***Janela de reengajamento***

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição**: `af_reengagement_window`

Leia aqui [como configurar o retargeting](/docs/sina-weibo-ads-campaign-configuration#criando-campanhas-de-retargeting-no-dashboard-de-anúncios-do-weibo) no dashboard do Sina Weibo.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que ocorrem dentro da janela de lookback podem ser atribuídas ao Sina Weibo Ads.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<Image align="center" alt="configurações de clique do Sina Weibo" src="https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png" />

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para o Sina Weibo Ads para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para o Sina Weibo Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao parceiro, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que mesmo se a atribuição estiver desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao parceiro.

<Image align="center" alt="sina-weibo-permissions.png" src="https://files.readme.io/a22be58687921e80108fe4b2cbd2863d9277a938a751ed5c666f147d78041c05-360002799478.png" />

Use estas alavancas para dar à ad network as permissões para lidar com sua própria configuração para seu aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div id="setting-appsflyer-attribution-on-weibo-ads-dashboard" />

## Definindo a atribuição da AppsFlyer no dashboard de anúncios do Weibo

Faça login no Sina Weibo Ads, usando este link: [https://ad.weibo.com/](https://ad.weibo.com)

Acesse a página **Tools** para fazer upload dos seus aplicativos na seção Apps Management:

<Image align="center" alt="" src="https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png" />

Clique para adicionar novos aplicativos:

<Image align="center" alt="" src="https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png" />

Android: insira a página de download do APK (terminada em .apk) ou faça upload do arquivo APK.

iOS: insira o link do iTunes.

<div id="setting-the-attribution-link" />

### Como configurar o link de atribuição

Acesse a página **promoções** e crie uma nova série de anúncios

<Image align="center" alt="" src="https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png" />

Se você quiser adquirir novos usuários para seu aplicativo, selecione o tipo de anúncio **Aumentar instalações do aplicativo**, conforme mostrado abaixo:

<Image align="center" alt="" src="https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png" />

<div id="setup-ad-series" />

### Configurar série de anúncios

Escolha qual aplicativo será divulgado:

<Image align="center" alt="" src="https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png" />

Defina os recursos da audiência, o orçamento e os períodos de promoção:

<Image align="center" alt="" src="https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png" />

<div id="uploading-ad-creatives-and-set-the-attribution-link" />

### Como fazer upload de criativos de anúncios e configurar o link de atribuição

O Weibo oferece quatro formatos de anúncio para promover instalações de aplicativos:

* Postagem do Weibo
* Cards grandes
* Card do aplicativo
* Aplicativo com 9 fotos

Todos os formatos de anúncio oferecem suporte à Atribuição da AppsFlyer.

<Image align="center" alt="" src="https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png" />

Insira o link de atribuição da AppsFlyer

<div id="example" />

> 📄 **Exemplo**
>
> ```http
> https://app.appsflyer.com/com.king.candycrushsaga?pid=sinaweibo_int&c=creative1
> 	&clickid={IMP}&md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false
> ```

<Image align="center" alt="" src="https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png" />

Conclua as configurações adicionais e publique o anúncio.

<div id="note" />

> 📘 **Nota**
>
> * Você pode visualizar o formato do anúncio na parte superior direita da página de configuração do criativo do anúncio.
> * Se você não estiver usando deep linking na campanha de anúncio, deixe o campo de deep link em branco.

<div id="creating-retargeting-campaigns-on-weibo-ads-dashboard" />

## Criando campanhas de retargeting no dashboard de anúncios do Weibo

No nível da campanha de anúncios, configure o direcionamento, o orçamento e o horário da campanha:

<Image align="center" alt="sina-weibo-retargeting.png" src="https://files.readme.io/8225fbfd74d16bb1a3e2e816933cb22d5f581a219ee35dd7f9d5285bacd49d2d-360002715577.png" />

No nível do anúncio, configure o deep link e o link de atribuição da AppsFlyer:

1. Escolha ***deeplink+app*** e cole o deep link no campo correspondente:

   <Image align="center" alt="sina-weibo-retargeting-deeplink.png" src="https://files.readme.io/dc5666893ff99dcb808a15aa2e41396b359617e2f6271f246a10893d4b05eebe-360002715557.png" />

   <div id="example-1" />

   > 📄 **Exemplo**
   >
   > ```http
   > myapp://products/page1&pid=sinaweibo_int&is_retargeting=true
   > ```

2. Copie o link de atribuição do dashboard da AppsFlyer com todos os parâmetros obrigatórios e cole-o no campo do link de atribuição:

   <Image align="center" alt="sina-weibo-retargeting-links.png" src="https://files.readme.io/edd0861728e19a0bc0e23641161c2365cf5c41eeccaa801bd4e8c3392215fe83-360002799598.png" />

   <div id="example-2" />

   > 📄 **Exemplo**
   >
   > ```http
   > https://app.appsflyer.com/com.mycompany.myapp?pid=sinaweibo_int&c=test&clickid={IMP}
   > &md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false&is_retargeting=true
   > ```


   <div id="note-1" />

   > 📘 **Nota**
   >
   > Observe que todos os parâmetros a seguir devem ser incluídos tanto no deep link quanto no link de atribuição e devem ser idênticos em ambos os links:
   >
   > * `&pid=sinaweibo_int` — parâmetro de ID do parceiro que identifica o Sina Weibo como canal de mídia
   > * `&c=campaign_name` — parâmetro que identifica uma campanha específica
   > * `&is_retargeting=true` — parâmetro que identifica um anúncio como parte de uma campanha de retargeting
   >
   > Se você usar Deferred deep linking, inclua também os seguintes parâmetros:
   >
   > * `&af_adset=adset_name`
   > * `&af_ad=ad_name`
   >
   > Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">estrutura e os parâmetros dos links de atribuição da AppsFlyer</Anchor> e os [links de atribuição](#attribution-link-tab) do Sina Weibo.

<div data-zendesk-anchors="setting-up-sina-weibo-ads=configurando-o-sina-weibo-ads h_01HKW6X6G9WGKHT7MXM3BKYX40=configurando-o-sina-weibo-ads h_01HKW6X6G9865NFC261ZCPC4AM=integration-tab activate-partners=ativar-parceiros h_01HKW6X6G98F7ERDGKN7K5PDVE=ativar-parceiros h_01HKW6X6GAR48FSFX7DVEWAMX8=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GA0FPN5EMR68FH2HSR=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HKW6X6GA287ZKAWG69497WRN=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6X6GABBB9ZP8GP87JYZAE=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GAY9GP9P57RFPSFTVN=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GADFS59WJT2GHYQ317=cost-tab h_01HKW6X6GAG7TM4WFNJFHGY9QN=ad-revenue-tab h_01HKW6X6GAK8PN5PBFPZTGC0ES=permissions-tab setting-appsflyer-attribution-on-weibo-ads-dashboard=definindo-a-atribui%C3%A7%C3%A3o-da-appsflyer-no-dashboard-de-an%C3%BAncios-do-weibo h_01HKW6X6GA96QHGJY220JF5DF4=definindo-a-atribui%C3%A7%C3%A3o-da-appsflyer-no-dashboard-de-an%C3%BAncios-do-weibo setting-the-attribution-link=como-configurar-o-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GA6XJSV02NTNDSRZ19=como-configurar-o-link-de-atribui%C3%A7%C3%A3o setup-ad-series=configurar-s%C3%A9rie-de-an%C3%BAncios h_01HKW6X6GAJBYM89RYH65BAVNH=configurar-s%C3%A9rie-de-an%C3%BAncios uploading-ad-creatives-and-set-the-attribution-link=como-fazer-upload-de-criativos-de-an%C3%BAncios-e-configurar-o-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GC2RHPJXWZAX8S758B=como-fazer-upload-de-criativos-de-an%C3%BAncios-e-configurar-o-link-de-atribui%C3%A7%C3%A3o h_01HKW6X6GCNS88DFZTMM7BXMKT=exemplo h_01HKW6X6GCBQNG4Q2RHJPCRCKS=nota creating-retargeting-campaigns-on-weibo-ads-dashboard=criando-campanhas-de-retargeting-no-dashboard-de-an%C3%BAncios-do-weibo h_01HKW6X6GE2RVQGSN9JM63SZYA=criando-campanhas-de-retargeting-no-dashboard-de-an%C3%BAncios-do-weibo h_01HKW6X6GEKZWAPZ6V2EXGY9SA=exemplo-1 h_01HKW6X6GFQQSY19CRREVR8GRY=exemplo-2 h_01HKW6X6GF815M1XE9HF631F1W=nota-1" />
