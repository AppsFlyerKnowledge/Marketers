---
title: >-
  Caso de uso da Google Marketing Platform para mensuração de tráfego de
  terceiros no CMP360
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
  created_at: '2021-03-03T12:42:31Z'
  edited_at: '2026-10-07T12:14:51Z'
  id: 360018228758
  locale: pt
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/pt/articles/360018228758
---
> **Visão geral**: compre tráfego de fontes de mídia terceiras no CM360 e mensure as conversões de aplicativos mobile originadas dessa fonte tanto na AppsFlyer (atribuídas à fonte terceira) quanto no CM360.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

<div id="measurement-of-cm360-with-non-dv360-third-party-media-sources" />

## Mensuração do CM360 para fontes terceiras

A Google Marketing Platform (GMP) reúne seus anúncios e analytics para ajudá-lo a criar conexões de qualidade com seus clientes, descobrir insights mais avançados e impulsionar melhores resultados de marketing.

No contexto da AppsFlyer, a integração padrão do DV360 SRN (dv360\_int) com a GMP permite a fácil atribuição de campanhas do DV360 **gerenciadas no CM360**, sem a necessidade de links de atribuição. A AppsFlyer atribui instalações e reengajamentos ao DV360 através das reivindicações do DV360 SRN usando a integração.

<div id="note" />

> 📘 **Atenção**
>
> * A AppsFlyer atribui campanhas DV360 gerenciadas no CM360 via integração padrão do DV360 SRN, sem a necessidade de links de atribuição. Instalações e reengajamentos são atribuídos ao DV360 através das reivindicações do DV360 SRN que usam a integração. Se você estiver executando campanhas DV360 via CM360, consulte o <Anchor target="_blank" href="/marketers/pt/docs/google-marketing-platform-display-video-360-dv360-integration">guia de integração do DV360</Anchor>.
> * Se a fonte de mídia terceira for uma SRN, a AppsFlyer recomenda não usar a integração descrita nesse artigo para evitar conflitos quando as conversões de um mesmo parceiro são relatadas por meio de duas integrações diferentes. Por exemplo, se a <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup">integração de SRN do Meta Ads</Anchor> estiver ativada na AppsFlyer, mas o CM360 também for utilizado para relatar o tráfego do Meta Ads (facebook\_int) usando o método descrito neste artigo, as conversões podem ser relatadas tanto pelo Meta Ads quanto pelo CM360, sendo que o CM360 captura algumas das conversões que teriam sido reivindicadas pela integração principal do Meta.

<div id="measuring-third-party-traffic-running-via-cm360" />

### Mensuração de tráfego de terceiros via CM360

As seguintes etapas são recomendadas para mensurar fontes de mídia terceiras gerenciadas via CM360, tanto na AppsFlyer quanto no CM360:

<div id="step-1-integrate-the-third-party-media-source-and-gmp-with-appsflyer" />

#### Passo 1: Faça a integração da fonte de mídia terceira e da GMP com a AppsFlyer

Para garantir a atribuição pela AppsFlyer:

* Certifique-se de que a fonte de mídia terceira esteja integrada e ativa, pois ela recebe a atribuição em vez do CM360. Ativar a GMP (dv360\_int) é necessário apenas para garantir que os dados sejam enviados de volta ao CM360.
* Se a fonte de mídia terceira não estiver integrada à AppsFlyer, ela deve ser tratada como uma fonte de mídia personalizada ou própria. Nesse caso, implemente um link de atribuição com qualquer valor PID (media source).

<div id="note-1" />

> 📘 **Atenção**
>
> Para atribuição de agências: a AppsFlyer exige o nome da agência para a atribuição de instalação. Inclua-o usando o parâmetro `af_prt` no link de atribuição ou através do referrer na URL.

<div id="step-2-create-the-required-attribution-links" />

#### Passo 2: crie os links de atribuição necessários

1. <Anchor target="_blank" href="https://support.google.com/campaignmanager/answer/3040965?hl=en&ref_topic=2826011">Crie um "tracking ad" do CM360</Anchor>
2. Crie um link de atribuição na AppsFlyer:
   * O link de atribuição deve conter a fonte de mídia sobre a qual você pretende reportar, que deve ser uma fonte de mídia de terceiros, e não do GMP. Por exemplo, se o canal de mídia de terceiros for Rocketfuel, use `pid=rocketfuel_int` e não `pid=dv360_int`. <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Saiba mais</Anchor>.
   * Se o seu objetivo for **reengajar usuários existentes abrindo o aplicativo** quando eles clicarem no link do anúncio (em vez de serem redirecionados para a loja de aplicativos), **use o método de esquema URI** para deep linking. Isso requer configurar o link do CM360 com o seguinte:
     * O parâmetro `af_dp` definido para o esquema URI do seu aplicativo.
     * O parâmetro `af_force_deeplink=true` para forçar explicitamente o comportamento de deep linking.
3. Anexe o link de atribuição AppsFlyer ao link CM360:

   <Tabs>
   <Tab title="Android">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&advertising_id=13******-****-****-****-54**********
   ```

   </Tab>

   <Tab title="iOS">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&idfa=13******-****-****-****-54**********
   ```

   </Tab>
   </Tabs>

   * Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters?">estrutura e os parâmetros dos links de atribuição para iOS e Android</Anchor>
   * Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">estrutura e os parâmetros dos links de atribuição para CTV, console e PC</Anchor>

<div id="step-3-set-in-app-event-postbacks" />

#### Passo 3: configure os postbacks de eventos in-app

Para garantir que o CM360 receba postbacks para eventos originados dessas campanhas, recomendamos definir postbacks de eventos in-app em dv360\_int como "Todas as fontes de mídia, incluindo orgânicas".

<div id="using-the-attribution-link" />

### Uso do link de atribuição

Assim que você tiver o link de atribuição, certifique-se de que ele seja usado ao veicular anúncios na fonte de mídia terceira escolhida. Quando uma instalação ocorre, a AppsFlyer atribui a instalação à fonte de mídia terceira selecionada e notifica o parceiro via postbacks. A AppsFlyer então informa ao CM360 sobre a instalação ou qualquer evento in-app subsequente via a integração do DV360, desde que ela esteja ativa.

O resultado final é uma instalação ou evento in-app atribuído à fonte de mídia e também registrado no DCM360.

<div data-zendesk-anchors="google-marketing-platform-cm360-nondv360-thirdparty-media-source-for-click-and-impression-measurement=mensura%C3%A7%C3%A3o-do-cm360-para-fontes-terceiras h_01HN0GE07NDVK8MWQEYMKDFAE6=mensura%C3%A7%C3%A3o-do-cm360-para-fontes-terceiras h_01HVXSGQZP305D7EF1SY56F26B=aten%C3%A7%C3%A3o measuring-thirdparty-traffic-running-via-cm360=mensura%C3%A7%C3%A3o-de-tr%C3%A1fego-de-terceiros-via-cm360 h_01HVK04VANY30B8EX94F9WPBGB=mensura%C3%A7%C3%A3o-de-tr%C3%A1fego-de-terceiros-via-cm360 step-1-integrate-the-thirdparty-media-source-and-gmp-with-appsflyer=passo-1-fa%C3%A7a-a-integra%C3%A7%C3%A3o-da-fonte-de-m%C3%ADdia-terceira-e-da-gmp-com-a-appsflyer h_01HYBRGBH10N9H0WT45NQ65C6R=passo-1-fa%C3%A7a-a-integra%C3%A7%C3%A3o-da-fonte-de-m%C3%ADdia-terceira-e-da-gmp-com-a-appsflyer h_01HYBB2SJEYE0WV2PRY5SK51GB=aten%C3%A7%C3%A3o-1 step-2-create-the-required-attribution-links=passo-2-crie-os-links-de-atribui%C3%A7%C3%A3o-necess%C3%A1rios h_01HYBA8YS1CWHN3APE5SV506TC=passo-2-crie-os-links-de-atribui%C3%A7%C3%A3o-necess%C3%A1rios 01JXQGQPDB66E3HWWEVPXXB8BZ=passo-3-configure-os-postbacks-de-eventos-in-app using-the-attribution-link=uso-do-link-de-atribui%C3%A7%C3%A3o h_01HN0GE07N10T92EKR5B2482KB=uso-do-link-de-atribui%C3%A7%C3%A3o" />
