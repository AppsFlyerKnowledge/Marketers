---
title: '[Legacy] Configuração do OneLink Smart Script V1'
deprecated: true
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2026-08-18T00:36:01Z'
  id: 4415354290321
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/4415354290321
---
> **Visão geral:** configure o OneLink Smart Script para converter e atribuir os visitantes do seu site mobile, provenientes de qualquer canal, em usuários do aplicativo mobile. **Nota**: Embora não seja obrigatório, considere migrar para <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="setup" />

## Configuração

Existem duas versões do OneLink Smart Script:

<Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recomendado)**</Anchor>: Se você estiver configurando o OneLink Smart Script pela primeira vez, essa é a versão ideal. A parte do trabalho de desenvolvimento é mais fácil e também pode ser configurada usando o Google Tag Manager. **Nota**: Embora não seja obrigatório, considere migrar para a V2. 

**OneLink Smart Script V1 (legado)**: Se você já tem o OneLink Smart Script configurado, use a documentação desta versão para manter e editar este script. 

<div id="responsibilities" />

<Accordion title="Responsabilidades">

| **Quem está envolvido**<ul><li>**Anunciante**:<ul><li>Decide o que a URL de saída deve conter. Isso inclui quais dados de atribuição anexar ao link e os dados necessários para deep linking. Seja manipulando a URL de entrada ou forçando determinados valores.</li><li>Certifica-se de que todas as campanhas que levam ao site mobile tenham URLs de entrada com parâmetros que funcionem para o script.</li></ul></li><li>**Desenvolvedor da web**:<ul><li>Configura os dados para inicializar o script.</li><li>Insere os setters necessários para gerar as URLs de saída do OneLink com base nos parâmetros da URL de entrada fornecidos pelo profissional de marketing. Isto inclui parâmetros obrigatórios e opcionais.</li><li>Incorpora o script ao site ou página/s específica(s).</li></ul></li></ul> |
| --- |
| **Pré-requisitos**<ul><li>Uma conta no AppsFlyer com pelo menos uma aplicação.</li><li>Um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor> que serve como o valor do [parâmetro OneLinkURL](/docs/legacy-onelink-smart-script-v1-setup#parameters).</li></ul> |

**Para implementar o script na página web**:

1. Decida quais parâmetros/valores a URL de saída do OneLink gerada automaticamente deve conter. Consulte a [lista de parâmetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) que você pode usar.
   * Certifique-se de que todas as campanhas com URLs de entrada tenham parâmetros com os quais o script funcione (e que possa usar como os parâmetros **pid** e **c**).
2. Forneça a [lista de parâmetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) ao desenvolvedor da web.
3. Diga ao desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script">instruções do dev</Anchor> e implementar o script para que o link de saída correto seja gerado.

</Accordion>

<div id="parameters" />

<Accordion title="Parâmetros">

<div id="parametersvalues-provided-to-the-developer-to-implement-the-smart-script" />

#### Parâmetros/valores fornecidos ao desenvolvedor para implementar o Smart Script

| Parâm./valor | Considerações | Registre suas respostas (para que o desenvolvedor as utilize) |
| --- | --- | --- |
| oneLinkURL (obrigatório) | <ul><li>Forneça o domínio do template do OneLink + ID do template. **Observação:** Não é uma URL de link personalizada do OneLink!</li><li>Exemplo: **suamarca.onelink.me/A1b2**</li><li>Exemplo de domínio de marca: **clique.suamarca.com/A1b2**</li></ul> |  |
| pidKeysList (canais de mídia) | <ul><li>Liste todos os parâmetros de canal de mídia na URL de entrada que serão usados como parâmetro de canal de mídia (pid) na URL de saída.</li><li>Exemplo: ['af\_pid', 'utm\_source']</li></ul> |  |
| pidOverrideList | <ul><li>Para os canais de mídia que você quer alterar no link de saída, liste os valores de canal de mídia na URL de entrada junto com os valores pelos quais deseja substituí-los.</li><li>Exemplo: `{<br />'twitter': 'twitter_int',<br />'snapchat': 'snapchat_int',<br />'some_social_net': 'some_social_net_int'<br />}`</li></ul> |  |
| pidStaticValue | <ul><li>Indique qual será o seu "fallback" de canal de mídia.</li><li>Se um parâmetro de canal de mídia não for encontrado na sua pidKeysList, o pidStaticValue será usado como o canal de mídia (pid) na URL de saída.</li><li>Exemplo: 'website' ou 'landing\_page'</li></ul> |  |
| campaignKeysList (campanhas) | <ul><li>Liste todos os parâmetros de campanha na URL de entrada que serão inseridos como o parâmetro de campanha (c) na URL de saída.</li><li>Exemplo: ['af\_campaign', 'utm\_campaign']</li></ul> |  |
| campaignStaticValue | <ul><li>Indique qual será a sua campanha "fallback".</li><li>Se um parâmetro de campanha não for encontrado na sua campaignKeysList, o campaignStaticValue será usado como a campanha (c) na URL de saída.</li><li>Exemplo: 'website' ou 'landing\_page'</li></ul> |  |
| gclIdParam | <ul><li>Informe como o parâmetro que leva a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor> será chamado.<br />**Nota**! Para exibir relatórios de dados brutos na AppsFlyer, o parâmetro deve ser um dos **af\_sub[1-5]**.</li></ul> |  |
| skipList | <ul><li>Liste as strings no referenciador HTTP que desativam o Smart Script para um clique específico (por exemplo, Twitter ou Facebook). Se as strings forem encontradas, o Smart Script não será executado. Isso pode ser útil para SRNs como X Ads e Meta ads, para os quais os cliques já são relatados.</li><li>Se você quiser que o Smart Script sempre seja executado, inclusive para SRNs, diga ao desenvolvedor para passar uma lista de exclusão vazia.</li></ul> |  |
| Outros parâmetros de consulta | <ul><li>Liste quaisquer outros parâmetros que você queira incluir na URL de saída do OneLink para atribuição ou deep linking.</li><li>Adicione um **deep\_link\_value** para deep linking.<ul><li>Além de adicionar o parâmetro, você e seu desenvolvedor precisam implementar a lógica de deep linking. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Saiba mais</Anchor>.</li></ul></li><li>Você pode usar parâmetros da URL de entrada ou forçar um valor estático.</li></ul> |  |

</Accordion>

<div id="use-cases" />

## casos de uso

As seções a seguir trazem alguns casos de uso do Smart Script para cenários de campanhas/canais de mídia comuns.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads — atribuição multiplataforma">

O Meta ads é um SRN que não usa links de atribuição externa.

Na primeira abertura do aplicativo, a AppsFlyer consulta os anúncios da Meta para verificar se o usuário já interagiu anteriormente (nos últimos <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-discrepancies#atribuição-de-cliques-e-de-exibição">7 dias</Anchor>) com um anúncio do aplicativo. Se o usuário tiver se engajado com um anúncio do Facebook do anunciante, os anúncios da Meta fazem a autoatribuição. O Meta ads também faz atribuição multiplataforma, o que significa que o usuário pode interagir com qualquer tipo de campanha, mobile ou não, em qualquer plataforma, para ser autoatribuído pelo Meta ads.

**Ação**: informe ao seu desenvolvedor para usar o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script#skip-clicks-from-twitter-or-facebook">método skipList</Anchor> para desabilitar o Smart Script para anúncios da Meta (ou quaisquer outras strings que você quiser). Se os anúncios da Meta ou qualquer uma das strings na skip list aparecer no referenciador HTTP do clique, o Smart Script retornará `null`.

**Observação**: a atribuição entre plataformas dos anúncios da Meta pode ser afetada quando os usuários optam por não compartilhar o Device ID, como era esperado para usuários do iOS 14 durante 2021.

</Accordion>

<div id="google-ads-gclid-and-utm-parameters" />

<Accordion title="Google Ads — parâmetros GCLID e UTM">

O processo usual para a atribuição de instalação de campanhas do Google Ads (que carregam um parâmetro GCLID) exige que os cliques sejam redirecionados para a URL da página da loja do aplicativo.

Como, neste caso, você está redirecionando leads do Google Ads para uma página web/landing page, o script extrai o parâmetro GCLID da URL da campanha de instalação do Google Ads e o insere na URL de saída, no parâmetro de saída de sua escolha **af\_sub[1-5].** **Atenção!** Isso se aplica às campanhas de instalação. Para campanhas de pesquisa não-ACI, ou seja, campanhas de reengajamento, o Google pode ser atribuído como canal de mídia, apesar do output do Smart Script.

**Pré-requisito**: No dashboard do Google, <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">ative a auto-tagging</Anchor>.   
Com o auto-tagging ativado, a URL contém o parâmetro *GCLID* parameter.

**Para configurar o script para o Google Ads**:

1. Faça uma lista dos nomes dos parâmetros de canal de mídia e de campanha que estão nos links de entrada.  
   Por exemplo: **utm\_source** e **utm\_campaign**.
2. Selecione um parâmetro na URL de saída para conter o GCLID.  
   Recomendação: selecione **af\_sub[1-5]**, para que os dados sejam exibidos nos relatórios de dados brutos da AppsFlyer.
3. Forneça-os na [lista de parâmetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) ao desenvolvedor web.

**Resultado**:

* Os valores dos parâmetros de canal de mídia e de campanha (**utm\_source** e **utm\_campaign**) no link de entrada são usados para preencher os valores dos parâmetros **pid** e **c** no link de saída.
* Na URL de saída, o GCLID é o valor do parâmetro **af\_sub[1-5]** .

**Para notificar o Google Ads sobre essas instalações:**

1. Obtenha os dados do GCLID no parâmetro af\_sub[1-5] via CSV, ou Push API em tempo real para cada instalação.
2. Faça upload dos dados de GCLID para o Google, <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">manualmente</Anchor> ou por meio da <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">API do Adwords</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> Essa solução GCLID não é oficialmente recomendada pelo Google. Caso o Google desative o parâmetro GCLID, alteraremos o script para que ele aceite as mudanças. Siga o artigo clicando no botão **seguir** no topo do artigo, para ser informado quando houver uma atualização do artigo ou script.

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="Links de SRNs, mídias próprias e de outros canais de mídia">

<Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor> como Snapchat ou X Ads funcionam de maneira diferente do Google Ads ou de uma plataforma entre plataformas, como os anúncios da Meta. As campanhas dessas SRNs levam seus usuários à página web/landing page, e você é cobrado de acordo com os clicking leads, sem nenhuma relação com qualquer usuário mobile derivado.

Para essas SRNs, a configuração do script é a mesma que para links de mídias próprias, ou outros canais de mídia que você possa usar.

**Para configurar o script**:

1. Faça uma lista dos canais de mídia e dos nomes dos parâmetros de campanha que estão nos links de entrada.
2. Forneça-os na [lista de parâmetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) ao desenvolvedor web.  
   O tipo de SRN/canal de mídia deve ser o valor do canal de mídia na URL de entrada, e o script o encontra e o usa como o valor de **pid** na URL de saída do OneLink por trás do botão de download na página web/landing page. Se você quiser alterar o **pid** de saída, forneça o valor do canal de mídia de entrada e o valor de substituição de **pid** na lista de substituição de pid.

**Resultado**: para essas SRNs/canais de mídia, os valores dos parâmetros de canal de mídia e de campanha no link de entrada são usados para preencher os valores dos parâmetros **pid** e **c** no link de saída.

<div id="example" />

> 📄 **Exemplo**
>
> **URL recebida**: https://hotel.me/af_pid=twitter&af_c=big_social
>
> **URL de saída**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Link de atribuição da AppsFlyer">

Os links de atribuição da AppsFlyer podem ser usados quando o canal de mídia é uma ad network de clique. Ao configurar esse link na AppsFlyer, você tem a opção de adicionar um parâmetro ***Redirection URL path (af\_r)*** com o caminho de URL desejado para seu site web mobile, para atribuição de campanha web para aplicativo. 

**Resultado**: Se os parâmetros **af\_r** e **af\_redirect=true** estiverem no link de entrada, o script da landing page não fará alterações. Ele deixa os links diretos da web/página de destino para as lojas de aplicativos como estão. 

<div id="example-1" />

> 📄 **Exemplo**
>
> **URL de entrada**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_redirect=true&af_r=hotel.me
>
> **URL de saída**: Igual

</Accordion>

<div id="desktop" />

<Accordion title="Desktop">

A maioria dos casos de uso nesse artigo são de usuários provenientes de dispositivos mobile. Portanto, quando direcionados do site mobile para uma loja de aplicativos, eles podem baixar seu aplicativo imediatamente.

No entanto, os usuários de desktop não devem ser enviados imediatamente para uma loja de aplicativos, pois seu dispositivo (desktop ou laptop) não é compatível com downloads de aplicativos mobile.

**Para configurar o script para usuários de desktop**:

* Em seu <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>, defina uma URL de destino para **Quando o link for clicado em desktop**. A URL deve redirecionar para uma página inicial/landing page. A landing page pode conter um formulário web onde os usuários preenchem seus dados para receber um SMS ou um e-mail com um link para baixar o aplicativo. Cabe a você criar o formulário da web e fornecer a URL para ele no script.

**Resultado:** O script detecta o dispositivo ou a plataforma em que o usuário está. Se for desktop, o script gera uma URL de saída do OneLink que redireciona o usuário para sua página web/landing page dedicada.

Consulte também <Anchor target="_blank" href="/marketers/pt/docs/qr-to-app-conversion">Conversão de desktop para aplicativo</Anchor>.

</Accordion>

<div id="limitations" />

<Accordion title="Limitações">

| Limitação | Considerações |
| --- | --- |
| Gerenciador de tags | O Smart Script não pode ser implementado por meio de um gerenciador de tags. Consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor> como uma solução alternativa de atribuição web-to-app. |

</Accordion>

<div data-zendesk-anchors="setup=configura%C3%A7%C3%A3o h_01HDNWHSY8HM30HV1PAF5C3M4E=configura%C3%A7%C3%A3o h_01HDNWHSY8J65EB1RZCFP1606H=responsibilities h_01HDNWHSY8CH29FQ2V5DCG2XSP=parameters parametersvalues-provided-to-the-developer-to-implement-the-smart-script=par%C3%A2metrosvalores-fornecidos-ao-desenvolvedor-para-implementar-o-smart-script h_01HDNWHSY8WSPX47VB43MC516Q=par%C3%A2metrosvalores-fornecidos-ao-desenvolvedor-para-implementar-o-smart-script use-cases=casos-de-uso h_01HDNWHSY8N77ZH4CK49ZQ2KZB=casos-de-uso facebook-ads%E2%80%94crossplatform-attribution=facebook-ads-crossplatform-attribution h_01HDNWHSY85QFABA6FAX1XTEPE=facebook-ads-crossplatform-attribution google-ads%E2%80%94gclid-and-utm-parameters=google-ads-gclid-and-utm-parameters h_01HDNWHSY878JTPZSN719KF1Y5=google-ads-gclid-and-utm-parameters h_01HDNWHSY8BJH39TAN46W7HE4G=nota h_01HDNWHSY8NER2M8X4DGHCWYPJ=srns-owned-media-and-other-media-source-links h_01HDNWHSY828Q587S28GYB85VR=exemplo h_01HDNWHSY8K1AFSEA1RY04KXJ9=appsflyer-attribution-links h_01HDNWHSY8DDTA6VATN0XXBEY5=exemplo-1 h_01HDNWHSY821DADGKATKH12PSJ=desktop h_01HDNWHSY80QA9CC4S2BPBTJYG=limitations" />
