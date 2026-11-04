---
title: Meta Ads — Crie campanhas na web para aplicativos de sites
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-20T03:48:34Z'
  id: 46172666260241
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/46172666260241
---
> **At a glance:** Configure uma integração do Meta Ads para o aplicativo do seu site para enviar sinais de conversão web para a Meta via API de Conversões (CAPI). A Meta usa esses sinais para otimizar a segmentação de anúncios e medir a performance da campanha.

<div id="overview" />

## Visão geral

A AppsFlyer permite a integração com o Meta Ads (`metaweb_int`) para campanhas de aplicativos de site. Com essa integração, você registra os dados de atribuição e conversão diretamente pela API de Conversões (CAPI) da Meta. Em seguida, esses dados são usados para otimizar a segmentação de anúncios, mensurar a performance e criar audiências personalizadas.

Veja como funciona: um usuário clica em um anúncio da Meta e acessa seu site. A AppsFlyer registra todos os eventos de conversão que o usuário conclui, como uma compra ou cadastro, e envia esse sinal para a Meta via CAPI. A Meta usa os dados para melhorar a segmentação e avaliar os resultados de campanha.

> 📘 **Atenção**
>
> A integração atual com a Meta Web não oferece suporte para o envio de postbacks de reengajamento para a CAPI.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração com o Meta Ads, verifique se você tem:

* Um aplicativo de site configurado na AppsFlyer. Para mais informações, consulte:
  * <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Adicionar um aplicativo à web</Anchor>
  * <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings">Configurar a atribuição web da AppsFlyer</Anchor>
* <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">Conta empresarial no Gerenciador do Meta Business Manager</Anchor>.

<div id="set-up-meta-ads-web-campaigns-for-website-apps" />

## Configurar campanhas de anúncios da Meta para aplicativos de sites

O processo envolve definir a integração entre o Meta Ads e a AppsFlyer e configurar a campanha em ambas as plataformas. Conclua as duas partes a seguir em sequência.

* [Parte 1: Configurar a integração do Meta Web Ads na AppsFlyer](#parte-1-configurar-a-integração-do-meta-web-ads-na-appsflyer) (obrigatória)
* [Parte 2: Configurar a integração da AppsFlyer no Meta Ads](#parte-2-configurar-a-integração-da-appsflyer-no-meta-ads) (obrigatória)

<div id="part-1-set-up-meta-ads-integration-in-appsflyer" />

## Parte 1: Configurar a integração do Meta Web Ads na AppsFlyer

Comece ativando a integração do Meta Ads e definindo os postbacks que a AppsFlyer envia para a CAPI.

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="Etapa 1: Ative a integração do Meta Ads">

Para ativar a integração do Meta Ads:

1. Na AppsFlyer, no menu lateral, acesse **Colaborar** > **Partner Marketplace**.
2. Pesquise e selecione **Meta Ads**.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração **Integrações ativas**.
4. Na aba **Integração**, selecione **Ativar parceiro**.

   <div id="note-1" />

   > 📘 **Atenção**
   >
   > O botão deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor> enquanto você trabalhar com o parceiro.

5. Preencha o campo **Pixel ID**. Para recuperar seu Pixel ID do Gerenciador do Meta Ads:
   1. No menu lateral do <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Gerenciador de Anúncios</Anchor>, acesse **Todas as ferramentas** > **Gerenciador de eventos**.

      <div id="note-2" />

      > 📘 **Atenção**
      >
      > Certifique-se de selecionar a empresa certa no menu suspenso no canto superior direito.

   2. No menu lateral do **Gerenciador de Eventos**, selecione **Fontes de dados**. Você verá uma lista dos seus pixels. Caso você não encontre um pixel para o negócio selecionado, você pode criá-lo.
   3. Copie o Pixel ID exibido abaixo do nome do pixel e cole-o no campo **Pixel ID** na AppsFlyer.
6. Preencha o campo **Token de acesso**. Para recuperar o token de acesso, siga <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token">estas instruções</Anchor>.
7. Ative a opção **Limitar o uso do Meta Ads sobre informações pessoais dos usuários (CCPA)** para garantir compliance com as <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>.

   <div id="note-3" />

   > 📘 **Atenção**
   >
   > O cumprimento dos requisitos de privacidade (CCPA) limita os dados provenientes de usuários do Meta Ads na Califórnia.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Etapa 2: Configure os postbacks de eventos in-app">

Você pode definir quais eventos de conversão na web a AppsFlyer envia para o Meta Ads ao mapear eventos da AppsFlyer para eventos do Meta Ads. Esses postbacks podem ser visualizados no <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Gerenciador de Eventos da Meta</Anchor>. A Meta usa os eventos mapeados para otimizar campanhas e relatórios.

Para configurar postbacks de eventos in-app:

1. Ative **Postbacks de eventos in-app**.
2. Se necessário, configure a janela de postback de eventos in-app. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">Configuração da janela de postback de evento in-app</Anchor>.
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna **Evento da AppsFlyer**, selecione o nome do evento na lista do menu suspenso. A AppsFlyer recebe o nome do evento do SDK web integrado ao seu site ou dos eventos de servidor para servidor (S2S) que você envia para a AppsFlyer.
5. Na coluna **Mapeado para evento de parceiro**, selecione o evento de parceiro predefinido mais adequado na lista do menu suspenso ou selecione **PERSONALIZADO**.
6. Na coluna **Para usuários de**, selecione a opção de envio do evento:
   * **Apenas este parceiro**: Envie postbacks somente quando esse evento for atribuído ao Meta Ads.
   * **Todos os canais de mídia, incluindo orgânico**: Envie postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.
7. Na coluna **Incluindo**, selecione se os eventos serão enviados com os valores de receita. Veja <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.

   <div id="important" />

   > 🚧 **Importante!**
   >
   > Se você estiver configurando um evento de compra, defina a coluna **Incluindo** como **Valores e receita**. Selecionar qualquer outra opção faz com que o postback falhe.

8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Salvar integração**.

<div id="note-4" />

> 📘 **Note**
>
> Se você também usa o Meta Pixel no seu site, envie o mesmo ID de evento para a AppsFlyer e para a Meta para que a AppsFlyer possa remover a duplicação dos eventos:
>
> * Inclua `af_customer_event_id` no payload do evento que você envia para a AppsFlyer. No SDK web, envie-o dentro de `eventValue`. Na API S2S (server-to-server), envie-o como um campo de nível superior ou dentro de `event_value`.
> * Envie o mesmo valor no evento correspondente do Pixel.
>
> A AppsFlyer encaminha esse valor para a Meta como o ID do evento. A Meta então o usa para desduplicar o evento do lado do servidor que recebe da AppsFlyer em relação ao evento do Pixel, para que a AppsFlyer contabilize a conversão uma única vez.
>
> Se você não enviar `af_customer_event_id`, a AppsFlyer gera um ID de evento automaticamente. Esse ID não corresponderá aos seus eventos do Pixel.
>
> Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">[Beta] Integrar o SDK web da AppsFlyer</Anchor>.

<div id="note-5" />

> 📘 **Atenção**
>
> Se você enviar eventos S2S e quiser que a AppsFlyer envie postbacks para o Meta Ads, verifique se cada evento inclui pelo menos um de `ip`, `user_agent` ou `customer_user_id`. Se os três estiverem ausentes, a AppsFlyer não enviará o postback. Para ver todos os campos de evento compatíveis, consulte <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement#mensurar-um-evento">API Server-to-Server (S2S) para Mensuração de performance web</Anchor>.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-meta-ads" />

## Parte 2: Configurar a integração da AppsFlyer no Meta Ads

Complete as etapas abaixo no Gerenciador do Meta Ads:

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Etapa 1: Defina o tipo, objetivo e metas da campanha.">

1. Faça login no Meta Ads e crie uma campanha.
2. Em **Objetivo da campanha**, selecione uma das seguintes opções:
   * **Vendas**: Isso permite que a Meta otimize visando um evento específico (seu principal KPI).
   * **Tráfego**: Isso permite que a Meta otimize visando cliques em anúncios. Use essa opção somente se você não possui outros KPIs ou se o volume de outros eventos de KPI for muito baixo.
3. [Opcional] Para adicionar um objetivo personalizado, faça o seguinte:

   1. No Meta Ads, selecione o evento personalizado que você deseja definir como objetivo da campanha e marque-o como uma ação de conversão.
   2. Na AppsFlyer, na página de **integração do Meta Web**, em **postbacks de eventos in-app**, mapeie um evento da AppsFlyer para um evento de parceiro personalizado na coluna **Mapeado para evento de parceiro**. Dê a ele o mesmo nome da ação de conversão no Meta Ads.

   <div id="note-6" />

   > 📘 **Atenção**
   >
   > Para saber mais sobre os objetivos da campanha na Meta, consulte a <Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">documentação da Meta</Anchor>.

4. Em **Local de conversão**, selecione **Site**.
5. Em **Pixel**, insira o mesmo Pixel ID que você inseriu para `metaweb_int` no Marketplace de parceiros da AppsFlyer. Para saber mais sobre o Pixel da Meta, consulte a <Anchor target="_blank" href="https://www.facebook.com/business/help/742478679120153">documentação da Meta</Anchor> (é necessário fazer login).
6. Clique em **Próximo**.

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="Etapa 2: Defina o URL de destino">

1. Em **Destino**, no **URL do site**, insira o URL que serve como destino para seu anúncio. Escolha uma das seguintes opções:

   * **URL do site**: Use o URL do seu site quando você quiser que os usuários acessem diretamente seu site e concluam eventos de conversão na web, como uma compra ou assinatura.
   * **Link de atribuição da AppsFlyer (OneLink)**: Use um link de atribuição da AppsFlyer quando você quiser que os usuários sejam redirecionados para o seu aplicativo mobile, com um fallback para o seu site se o app não estiver instalado. Isso é útil quando sua campanha visa tanto usuários de aplicativos quanto da web. Para mais informações, consulte a seção <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Links e experiências do OneLink</Anchor>.

   <div id="important-1" />

   > 🚧 **Importante!**
   >
   > Em alguns casos, o uso de links de atribuição da AppsFlyer pode causar erros. Se isso ocorrer, peça uma solução ao seu representante da Meta ou use o URL do seu site como o URL de destino.

2. Clique em **Criar um parâmetro de URL** para adicionar parâmetros de URL ao URL de destino.
3. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**.
4. Mapeie os parâmetros da AppsFlyer para seus valores da Meta de acordo com a tabela abaixo:

| Parâmetro da AppsFlyer | Valor mapeado na Meta |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#c">`C`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

Exemplo de um URL resultante:

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

<div id="note-7" />

> 📘 **Atenção**
>
> A Meta anexa automaticamente `fbclid={{fbclid}}` ao URL de destino quando o anúncio é clicado.

<div id="tip" />

> 👍 **Observação**
>
> Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha. Exemplo: `campaign-name_web`.

<div id="see-also" />

> 📄 **Veja também**
>
> * Para conferir as práticas recomendadas sobre como criar o URL do seu anúncio com todos os parâmetros relevantes, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a identificação de fontes de tráfego</Anchor>.

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="Etapa 3: Selecione eventos monitorados">

Use a seção **Rastreamento** para selecionar os eventos de conversão promovidos pelo seu anúncio. Você pode configurar eventos através do <Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">Gerenciador de Eventos</Anchor>.

<div id="important-2" />

> 🚧 **Importante!**
>
> Não escolha **Eventos do aplicativo**. Ao fazer isso, a Meta reivindicará essas conversões por meio da SRN API, podendo desalinhar relatórios e otimizações.

</Accordion>

<div id="view-web-attribution-data" />

## Visualizar dados de atribuição web

Veja o que esperar ao revisar seus dados de atribuição após a configuração:

* **Dashboard:** No <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#crossplatform-dashboard">dashboard cross-platform</Anchor>, os dados da web e do aplicativo são apresentados lado a lado, oferecendo uma visão unificada da performance de campanhas em todas as plataformas.
* As **exportações de dados brutos e respostas da API** incluem a Meta Web no campo `media_source` para a atividade web da Meta.

<div id="measure-web-attribution-data-with-web-cost" />

## Mensurar os dados de atribuição web com os custos da web

Você pode ter uma visão completa da performance dos dados de atribuição web e dos dados de custo do Meta Ads no dashboard e nos <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">relatórios do Cost ETL</Anchor>. Para fazer isso, verifique se você tem <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide#sobre-o-roi360">o pacote ROI360</Anchor> e conclua a configuração a seguir:

1. Conecte custos ao aplicativo do seu site via `facebook_int` (não via `metaweb_int`) da aba **Custos** ou da página **Configurações de custo**. Para mais informações sobre como conectar custos, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configure a ROI360 cost API para mensurar dados de custo</Anchor>.
2. Inclua o ID da campanha (`af_c_id`) no URL da landing page. Certifique-se de que o URL inclua toda a hierarquia da campanha para visualizar custos, cliques e impressões correspondentes à atribuição web no nível mais granular.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Cliques e impressões | Cliques e impressões para campanhas na web exigem uma <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide">assinatura do ROI360</Anchor>. |
| Reengajamento | No momento, os postbacks de reengajamento via CAPI não são compatíveis. |

<div id="see-also-1" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview">Mensuração da performance web - visão geral</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KQA78RE9FRENQAK31Q641C0N=vis%C3%A3o-geral h_01KQA78RE9F82ZBVF4YZHZTEEX=aten%C3%A7%C3%A3o prerequisites=pr%C3%A9-requisitos h_01KQA78RE93B09A9YH2FRB3XRR=pr%C3%A9-requisitos set-up-meta-ads-web-campaigns=configurar-campanhas-de-an%C3%BAncios-da-meta-para-aplicativos-de-sites h_01KQA78RE9J681CJ8DQNWJC37H=configurar-campanhas-de-an%C3%BAncios-da-meta-para-aplicativos-de-sites part-1-set-up-meta-ads-integration-in-appsflyer=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-meta-web-ads-na-appsflyer h_01KQA78RE93JYCV2P0DDZC0A4B=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-meta-web-ads-na-appsflyer h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=aten%C3%A7%C3%A3o-1 h_01KQA78REANHAQ88N4MXWM832D=aten%C3%A7%C3%A3o-2 h_01KQA78REA08SNB0BKCJDJZ2R0=aten%C3%A7%C3%A3o-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=importante h_01M520Y7YQYY70W2S24N2AXRG4=aten%C3%A7%C3%A3o-4 part-2-set-up-appsflyer-integration-in-meta-ads=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-meta-ads h_01KQA78REAEZQPDSKZ0GRNKEJJ=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-meta-ads h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=aten%C3%A7%C3%A3o-5 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=importante-1 h_01KQA78REARWGQDCJ4KN3FM120=aten%C3%A7%C3%A3o-6 h_01KQA78REA7MZSG5JZ1XX2C65P=observa%C3%A7%C3%A3o h_01KQA78REA3ZW7W9M3VFSQASB6=veja-tamb%C3%A9m h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=importante-2 view-web-attribution-data=visualizar-dados-de-atribui%C3%A7%C3%A3o-web h_01KQA78REBK1PWXNA1PM9118TA=visualizar-dados-de-atribui%C3%A7%C3%A3o-web measure-web-attribution-data-with-web-cost=mensurar-os-dados-de-atribui%C3%A7%C3%A3o-web-com-os-custos-da-web h_01KNM00RR9TF8JRTJXWN23MF1S=mensurar-os-dados-de-atribui%C3%A7%C3%A3o-web-com-os-custos-da-web traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQAE3JKMQ6ZEATDAEXBC4PT6=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQC27K5KWP3A6HMM2W7N3MVB=veja-tamb%C3%A9m-1" />
