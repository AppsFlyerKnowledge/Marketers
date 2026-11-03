---
title: TikTok for Business — Crie campanhas na web para aplicativos de sites
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
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-08-31T12:32:28Z'
  id: 46191822292113
  locale: pt
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/pt/articles/46191822292113
---
> **Resumo:** Configure uma integração do TikTok Web Ads para o aplicativo do seu site para enviar sinais de conversão na web ao TikTok através da Events API.

## Visão geral

Funciona assim: quando um usuário clica em um anúncio do TikTok e acessa seu site, realizando um evento na web (por exemplo, uma compra ou um cadastro), a AppsFlyer envia esses sinais para o TikTok via Events API. O TikTok usa esses dados para otimizar a segmentação de anúncios e mensurar a performance de campanhas.

Você pode definir quais eventos de conversão na web a AppsFlyer envia para o TikTok Ads ao mapear eventos da AppsFlyer para eventos do TikTok Web Ads. Esses postbacks podem ser visualizados no TikTok Ads Manager e os eventos são mapeados pelo TikTok para otimizar campanhas e relatórios.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview">Mensuração da performance web - visão geral</Anchor>

> 🚧 **Importante!**
>
> Atualmente, a integração não oferece suporte para o envio de postbacks de reengajamento pela Events API.

### Pré-requisitos

Antes de ativar a integração do TikTok Web Ads para seus aplicativos de sites, certifique-se de que você tenha:

* Um aplicativo de site configurado na AppsFlyer.
* Uma conta empresarial no <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok Ads Manager</Anchor>

### Como configurar o TikTok Web Ads para aplicativos de site

O processo envolve definir a integração entre o TikTok Web Ads e a AppsFlyer e configurar a campanha no TikTok Ads Manager. Isso inclui as seguintes etapas:

* [Parte 1:](#parte-1-configurar-a-integração-do-tiktok-web-ads-na-appsflyer) [Configurar a integração do TikTok Web Ads na AppsFlyer](#parte-1-configurar-a-integração-do-tiktok-web-ads-na-appsflyer) (obrigatório)
* [Parte 2: Configurar a integração da AppsFlyer no TikTok Web Ads](#parte-2-configurar-a-integração-da-appsflyer-no-tiktok-web-ads) (obrigatória)

## Parte 1: Configurar a integração do TikTok Web Ads na AppsFlyer

Comece ativando a integração do TikTok Web Ads e definindo os postbacks que a AppsFlyer envia para a Events API.

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1. Ative a integração do TikTok Web Ads">

Para ativar a integração do TikTok Web Ads:

1. Na AppsFlyer, no menu lateral, acesse **Colaborar** > **Partner Marketplace**.
2. Pesquise e selecione **TikTok For Business - Advanced SRN** (ou `tiktokweb_int`).
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração **Integrações ativas**.
4. Na aba **Integração** selecione **Ativar parceiro**. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.
5. **Pixel ID:** Insira o Pixel ID. Você pode gerá-lo ou recuperá-lo do seu TikTok Ads Manager seguindo as instruções detalhadas na <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">documentação do TikTok.</Anchor>
6. **Token de acesso:** Insira o token de acesso. Para gerá-lo ou recuperá-lo, siga a <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">documentação do TikTok</Anchor>.
7. **Limitar o uso do TikTok Web Ads sobre informações pessoais dos usuários (CCPA).** **Ative essa opção para garantir compliance com as <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>.**

> 📘 **Atenção**
>
> O cumprimento dos requisitos de privacidade (CCPA) limita os dados provenientes de usuários do TikTok Web Ads na Califórnia ou em outros estados com leis semelhantes nos EUA.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Configure os postbacks de eventos in-app">

A AppsFlyer permite a integração com o TikTok Web Ads (`tiktokweb_int`) para campanhas de aplicativos de site. Com essa integração, você gera relatórios de dados de atribuição e conversão diretamente pela Events API do TikTok. Esses postbacks podem ser visualizados no TikTok Ads Manager e os eventos são mapeados pelo TikTok para otimizar campanhas e relatórios.

Para configurar postbacks de eventos in-app:

1. Ative **Postbacks de eventos in-app**.
2. Se necessário, configure a janela de postback de eventos in-app. Saiba mais sobre a configuração da janela de postback de evento in-app em <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">Configuração de postback de evento in-app</Anchor>.
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna **Evento da AppsFlyer**, selecione o nome do evento na lista suspensa. A AppsFlyer recebe o nome do evento pelo SDK web integrado ao seu site ou pelos eventos de servidor para servidor (S2S) que você envia para a AppsFlyer.
5. Na coluna **Mapeado para evento de parceiro**, selecione o evento de parceiro predefinido mais adequado.
6. Na coluna **Para usuários de**, selecione a opção adequada:
   * **Somente este parceiro**, para enviar eventos atribuídos apenas aos anúncios da web do TikTok.
   * **Todos os canais de mídia, incluindo orgânico**, para enviar todos os eventos independentemente da fonte de atribuição.
7. Na coluna **Incluindo**, selecione se os eventos serão enviados com os respectivos valores de receita. Veja <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.

   > 📘 **Atenção**
   >
   > * Se você estiver configurando um evento de compra, defina a coluna **Incluindo** como **Valores e receita**. Selecionar qualquer outra opção fará com que o postback falhe.
   > * Atualmente, apenas o evento de compra pode ser configurado para incluir receita.

8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Salvar integração**.

> 📘 **Note**
>
> Se você também executa o TikTok Pixel no seu site, envie o mesmo ID do evento para a AppsFlyer e o TikTok, para que a AppsFlyer possa eliminar duplicidades nos eventos:
>
> * Inclua `af_customer_event_id` no payload do evento que você envia para a AppsFlyer, dentro de `eventValue` para o SDK web ou `event_value` para a API S2S (servidor para servidor).
> * Envie o mesmo valor no evento correspondente do Pixel.
>
> A AppsFlyer encaminha esse valor ao TikTok como ID do evento. Em seguida, o TikTok usa isso para eliminar duplicidades entre o evento do servidor que recebe da AppsFlyer e o evento do Pixel, para que a AppsFlyer conte a conversão uma única vez.
>
> Se você não enviar `af_customer_event_id`, a AppsFlyer gera um ID de evento automaticamente. Esse ID não corresponderá aos seus eventos do Pixel.
>
> Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">[Beta] Integrar o SDK web da AppsFlyer</Anchor>.

</Accordion>

## Parte 2: Configurar a integração da AppsFlyer no TikTok Web Ads

Realize as próximas etapas no TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Defina o tipo, objetivo e metas da campanha.">

Você pode escolher qualquer evento in-app padrão enviado pela AppsFlyer como seu objetivo de campanha. Selecione um objetivo de campanha que esteja alinhado aos objetivos de conversão do seu site. Exemplo: impulsionar o tráfego para o seu site ou otimizar as conversões no próprio site.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Defina a URL de destino">

1. Em **Destino**, no campo **URL do site**, insira o URL do seu site, ou seja, a página para onde os usuários são direcionados depois de clicarem no seu anúncio.

   O **URL do site** é a principal opção de destino. Os usuários clicam no anúncio e são redirecionados para o seu site para concluir os eventos de conversão.
2. **[Alternativa] Link de atribuição da AppsFlyer (OneLink):** Se você deseja redirecionar os usuários para o aplicativo mobile, com um fallback para o site, use um link de atribuição da AppsFlyer (OneLink) como URL de destino.
3. Clique em **Criar um parâmetro de URL** para adicionar parâmetros de URL ao URL de destino.
4. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**.
5. Mapeie os parâmetros da AppsFlyer de acordo com seus valores do TikTok.

| Parâmetro da AppsFlyer | Valor mapeado no TikTok |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `C` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   > 📘 **Atenção**
   >
   > Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha. Exemplo: `campaign-name_web`.


   Para conferir as práticas recomendadas sobre a configuração dos parâmetros de URL e a identificação de fontes de tráfego, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a identificação de fontes de tráfego</Anchor>.

   Exemplo de um URL resultante:

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   > 📘 **Atenção**
   >
   > O TikTok anexa automaticamente `ttclid={{ttclid}}` ao URL de destino quando o anúncio é clicado.


</Accordion>

## Visualizar dados de atribuição web

Eventos de conversão na web são registrados com o PID `tiktokweb_int` no campo `media_source`. Para visualizar dados de atribuição web, use relatórios de dados brutos e filtre por `media_source = tiktokweb_int` para separar as conversões de aplicativos de sites.

Os relatórios de dashboard para campanhas de aplicativos de sites ainda não estão disponíveis. Uma visão unificada para relatórios que permite analisar a performance de campanhas na web junto com outros canais será lançada em breve.

## Meça custo, cliques e impressões

Meça custo, cliques e impressões do TikTok juntamente com seus dados de atribuição web no dashboard e nos relatórios de custo do ETL (somente para clientes do ROI360).

1. Para obter dados de custo do TikTok para campanhas de aplicativos de sites no relatório **All Cost**, conecte sua conta de anúncios à integração de custos do TikTok (`tiktokglobal_int`) através da página **Configurações de custo** ou da aba **Custo**. Para ver instruções passo a passo, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data">Configure a API de custo do ROI360 para mensurar dados de custo</Anchor>.
2. **Adicione o ID da campanha à URL da sua landing page:** inclua `af_c_id` junto com a hierarquia completa da campanha na URL da landing page. Isso garante que custo, cliques e impressões sejam correspondidos aos seus dados de atribuição web no nível mais granular.

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Reengajamento | Os postbacks de reengajamento pela Events API não estão disponíveis atualmente. |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KQC152Q49R7P96BPMMZGVZWS=vis%C3%A3o-geral h_01KQC25PY3PPRTQBJ7K8NV3JWQ=veja-tamb%C3%A9m h_01KQC152Q42VT7XKTGCEJV7V7S=importante prerequisites=pr%C3%A9-requisitos h_01KQC152Q4A31VJ1JTXWJG6CN0=pr%C3%A9-requisitos how-to-set-up-tiktok-ads-for-your-website-app=como-configurar-o-tiktok-web-ads-para-aplicativos-de-site h_01KQC152Q4S1VTK7BGWPHHD27W=como-configurar-o-tiktok-web-ads-para-aplicativos-de-site part-1-set-up-tiktok-ads-integration-in-appsflyer=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-tiktok-web-ads-na-appsflyer h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=parte-1-configurar-a-integra%C3%A7%C3%A3o-do-tiktok-web-ads-na-appsflyer h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=aten%C3%A7%C3%A3o h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=aten%C3%A7%C3%A3o-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-tiktok-web-ads h_01KQC152Q4NKQHF75Y14XCCFNH=parte-2-configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-tiktok-web-ads h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=aten%C3%A7%C3%A3o-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=aten%C3%A7%C3%A3o-3 view-web-attribution-data=visualizar-dados-de-atribui%C3%A7%C3%A3o-web h_01KQC152Q45QE5M5BGD4RJNFR9=visualizar-dados-de-atribui%C3%A7%C3%A3o-web h_01KQD9Z1XY7AB3CDE4FGHTKLM=me%C3%A7a-custo-cliques-e-impress%C3%B5es measure-cost-clicks-and-impressions=me%C3%A7a-custo-cliques-e-impress%C3%B5es traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQC152Q45WC7HNZ64T98JJ6Y=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
