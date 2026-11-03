---
title: Snapchat — Crie campanhas na web para aplicativos de sites
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-20T03:49:19Z'
  id: 46196482479249
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/46196482479249
---
> **At a glance:** Configure uma integração de anúncios do Snapchat para o aplicativo do seu site para enviar sinais de conversão na web ao Snapchat por meio da API de Conversões.

## Visão geral

A AppsFlyer é compatível com a integração com anúncios do Snapchat (`snapweb_int`) para campanhas do aplicativo do site, permitindo que você reporte dados de atribuição e dados de conversão diretamente pela API de Conversões do Snapchat. O Snapchat usa esses dados para otimizar a segmentação de anúncios e mensurar a performance de campanhas.

Veja como funciona: um usuário clica em um anúncio do Snapchat e acessa seu site. Quando o usuário conclui um evento no site (por exemplo, uma compra ou um cadastro), a AppsFlyer envia o sinal de conversão ao Snapchat por meio da API de Conversões. O Snapchat usa esses dados para otimizar a segmentação de anúncios e mensurar a performance de campanhas.

> 🚧 **Importante!**
>
> Atualmente, a integração não oferece suporte para o envio de postbacks de reengajamento pela Conversions API.

### Pré-requisitos

Antes de ativar a integração do Snapchat Ads para o aplicativo do seu site, certifique-se de que você tenha:

* Um aplicativo de site configurado na AppsFlyer.
* Uma conta empresarial no <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat Ads Manager</Anchor>

### Como configurar o Snapchat Ads para o aplicativo do seu site

A configuração envolve definir a integração entre o Snapchat Ads e a AppsFlyer e configurar a campanha no Snapchat Ads Manager. Isso inclui as seguintes etapas:

* [Parte 1: Configurar a integração do Snapchat Ads na AppsFlyer (obrigatória)](#parte-1-configurar-a-integra%C3%A7%C3%A3o-de-an%C3%BAncios-do-Snapchat-no-AppsFlyer)
* [Parte 2: Configurar a integração da AppsFlyer no Snapchat Ads (obrigatória)](Par%C3%A2metro%20da%20AppsFlyer)

## Parte 1: Configurar a integração do Snapchat Ads na AppsFlyer

Comece ativando a integração do Snapchat Ads. Em seguida, configure os postbacks que a AppsFlyer envia para a Conversions API.

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1. Ative a integração do Snapchat Ads">

Para ativar a integração do Snapchat Ads:

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Pesquise e selecione **Snapchat**.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração **Integrações ativas**.
4. Na aba **Integração** selecione **Ativar parceiro**. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.
5. **Pixel ID:** Insira o Pixel ID. Você pode gerá-lo ou recuperá-lo no seu Snapchat Ads Manager seguindo as instruções na <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">documentação de anúncios do Snapchat</Anchor>.
6. **Token de acesso:** Insira o token de acesso. Para criá-lo ou recuperá-lo, siga as <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">instruções na documentação oficial de anúncios do Snapchat</Anchor>.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Configure os postbacks de eventos in-app">

Você pode definir quais eventos de conversão web a AppsFlyer envia para o Snapchat Ads mapeando eventos da AppsFlyer para eventos do Snapchat Ads. Esses postbacks podem ser visualizados no Snapchat Ads Manager. O Snapchat usa os eventos mapeados para otimizar campanhas e relatórios.

Para configurar postbacks de eventos in-app:

1. Ative **Postbacks de eventos in-app**.
2. Se necessário, configure a janela de postback de eventos in-app. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">Configuração de postback de evento in-app</Anchor>.
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna **Evento da AppsFlyer**, selecione o nome do evento na lista. A AppsFlyer recebe o nome do evento do SDK web integrado ao seu site ou de eventos de servidor para servidor (S2S) que você envia para a AppsFlyer.
5. Na coluna **Mapeado para evento de parceiro**, selecione na lista o evento de parceiro predefinido mais adequado.
6. Na coluna **Para usuários de**, selecione a opção adequada:
   * **Somente este parceiro** envia eventos atribuídos aos anúncios do Snapchat.
   * **Todos os canais de mídia, incluindo orgânico** enviam todos os eventos, independentemente da fonte de atribuição.
7. Na coluna **Incluindo**, selecione se você quer enviar eventos com os respectivos valores de receita. Veja <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.
8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.

   > 📘 **Atenção**
   >
   > * Se você estiver configurando um evento de compra, defina a coluna **incluindo** como **Valores e receita**. Selecionar qualquer outra opção faz com que o postback falhe.
   > * Atualmente, você pode configurar apenas o evento de compra para incluir receita.

9. Clique em **Salvar integração**.

> 📘 **Note**
>
> Se você também executar o Snap Pixel no seu site, envie o mesmo ID de evento para a AppsFlyer e para o Snapchat, para que a AppsFlyer possa desduplicar os eventos:
>
> * Inclua `af_customer_event_id` no payload do evento que você envia para a AppsFlyer. No SDK web, envie-o dentro de `eventValue`. Na API S2S (server-to-server), envie-o como um campo de nível superior ou dentro de `event_value`.
> * Envie o mesmo valor no evento do Pixel correspondente.
>
> A AppsFlyer encaminha esse valor ao Snapchat como o ID do evento. O Snapchat então o usa para desduplicar o evento do lado do servidor que recebe da AppsFlyer em relação ao evento do Pixel, para que a AppsFlyer conte a conversão uma única vez.
>
> Se você não enviar `af_customer_event_id`, a AppsFlyer gerará um ID de evento automaticamente. Esse ID não corresponderá aos seus eventos do Pixel.
>
> Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">[beta] Integrar o SDK web da AppsFlyer</Anchor>.

> 📘 **Atenção**
>
> Se você enviar eventos S2S e quiser que a AppsFlyer envie postbacks para o Snapchat Ads, certifique-se de que cada evento inclua `ip` ou `user_agent`. Se ambos estiverem ausentes, a AppsFlyer não envia o postback. Para ver todos os campos de evento compatíveis, consulte <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement#mensurar-um-evento">API Server-to-Server (S2S) para Mensuração de performance web</Anchor>.

</Accordion>

## Parte 2: Configurar a integração da AppsFlyer no Snapchat anúncios

Realize as próximas etapas no Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Defina o tipo, o objetivo e as metas da campanha.">

Você pode escolher qualquer evento in-app padrão enviado pela AppsFlyer como seu objetivo de campanha. Selecione um objetivo de campanha que esteja alinhado aos objetivos de conversão do seu site. Exemplo: impulsionar o tráfego para o seu site ou otimizar as conversões no próprio site.

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. Defina o URL de destino">

1. Em **Destino**, no campo **URL do site**, insira o URL do seu site, ou seja, a página para onde os usuários são direcionados depois de clicarem no seu anúncio. O **URL do site** é a principal opção de destino. Os usuários clicam no anúncio e são redirecionados para o seu site para concluir os eventos de conversão.
2. **[Alternativa] Link de atribuição da AppsFlyer (OneLink):** Se você deseja redirecionar os usuários para o aplicativo mobile, com um fallback para o site, use um link de atribuição da AppsFlyer (OneLink) como URL de destino.
3. Clique em **Criar um parâmetro de URL** para adicionar parâmetros de URL ao URL de destino.
4. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**.
5. Mapeie os parâmetros da AppsFlyer de acordo com os valores do Snapchat.

| Parâmetro da AppsFlyer | Valor mapeado do Snapchat |
| --- | --- |
| `pid` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_canal` | `{{site_source_name}}` |

   * Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha. Exemplo: `campaign-name_web`.

   Para conferir as práticas recomendadas sobre a configuração dos parâmetros de URL e a identificação de fontes de tráfego, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a identificação de fontes de tráfego</Anchor>.

   Exemplo de um URL resultante:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

> 📘 **Atenção**
>
> O Snapchat adiciona automaticamente `ScCid={{ScCid}}` ao URL de destino quando o anúncio é clicado.

</Accordion>

## Visualizar dados de atribuição web

Veja o que esperar ao revisar seus dados de atribuição após a configuração:

* **Dashboard:** No <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#crossplatform-dashboard">dashboard cross-platform</Anchor>, os dados da web e do aplicativo são apresentados lado a lado, oferecendo uma visão unificada da performance de campanhas em todas as plataformas.
* As **exportações de dados brutos e respostas da API** incluem o Snap Web no campo `media_source` para a atividade web do Snap.

## Mensurar os dados de atribuição web com os custos da web

Você pode ter uma visão completa da performance dos dados de atribuição web e dos dados de custo web do Snapchat anúncios no dashboard e nos <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">relatórios de Cost ETL</Anchor>. Para fazer isso, certifique-se de que você tenha <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide#sobre-o-roi360">o pacote ROI360</Anchor> e conclua a configuração a seguir:

1. Conecte custos ao aplicativo do seu site via `snapchat_int` (não via `snapweb_int`) da aba **Custos** ou da página **Configurações de custo**. Para mais informações sobre como conectar custos, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configure a ROI360 cost API para mensurar dados de custo</Anchor>.
2. Inclua o ID da campanha (`af_c_id`) no URL da landing page. Certifique-se de que o URL inclua toda a hierarquia da campanha para visualizar custos, cliques e impressões correspondentes à atribuição web no nível mais granular.

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Cliques e impressões | Cliques e impressões para campanhas na web exigem uma <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide">assinatura do ROI360</Anchor>. |
| Reengajamento | Os postbacks de reengajamento pela Conversions API não estão disponíveis atualmente. |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview">Mensuração da performance web - visão geral</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KQC7RA5R1PS69N3015WY4QRY=vis%C3%A3o-geral h_01KQC7RA5RAY6R70GNHCYWAMRC=importante prerequisites=pr%C3%A9-requisitos h_01KQC7RA5R02QV60T81NX055DM=pr%C3%A9-requisitos how-to-set-up-snapchat-ads-for-your-website-app=como-configurar-o-snapchat-ads-para-o-aplicativo-do-seu-site h_01KQC7RA5RPWP0X927ENN6KJ9V=como-configurar-o-snapchat-ads-para-o-aplicativo-do-seu-site part-1-set-up-snapchat-ads-integration-in-appsflyer=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-snapchat-ads-na-appsflyer h_01KQC7RA5RY1HF9VHC332FVBFR=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-snapchat-ads-na-appsflyer h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=aten%C3%A7%C3%A3o h_01M520TA4E64EARM6R1EV9QPSR=aten%C3%A7%C3%A3o-1 part-2-set-up-appsflyer-integration-in-snapchat-ads=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-snapchat-an%C3%BAncios h_01KQC7RA5REPX0WDDHT7YWDHMC=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-snapchat-an%C3%BAncios h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=aten%C3%A7%C3%A3o-2 view-web-attribution-data=visualizar-dados-de-atribui%C3%A7%C3%A3o-web h_01KQC7RA5SKRWGGCKV71MV8J56=visualizar-dados-de-atribui%C3%A7%C3%A3o-web measure-web-attribution-data-with-web-cost=mensurar-os-dados-de-atribui%C3%A7%C3%A3o-web-com-os-custos-da-web h_01KQC7XYSWPTHVDY5R3EG8H4K2=mensurar-os-dados-de-atribui%C3%A7%C3%A3o-web-com-os-custos-da-web traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQC7RA5SSZB8M8G00NTXG71K=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQC80MBB1KCVVNDSFSJHG5ZT=veja-tamb%C3%A9m" />
