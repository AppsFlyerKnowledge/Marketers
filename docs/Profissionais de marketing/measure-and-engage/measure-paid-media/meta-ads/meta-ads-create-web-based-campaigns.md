---
title: Meta Ads — Crie campanhas na web
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
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-09-16T00:28:43Z'
  id: 25646834966033
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/25646834966033
---
> **Resumo:** Use campanhas web do Meta Ads para atribuir conversões web-to-app partir do Meta Ads

<div id="overview" />

## Visão geral

A AppsFlyer é compatível com a integração com o Meta Ads (`metaweb_int`) para campanhas baseadas na web, permitindo que você reporte dados de atribuição e conversão diretamente por meio da Conversion API (CAPI) do Meta. Os dados são então usados pelo Meta Ads para otimizar a segmentação de anúncios, mensurar a performance e construir audiências personalizadas.

<div id="note" />

> 📘 **Nota**
>
> Atualmente, a integração com o Meta Web não oferece suporte para o envio de postbacks de reengajamento para a CAPI.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração do Meta Ads, certifique-se de que você possui uma [conta comercial no Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

<div id="how-to-create-a-meta-web-ads-campaign" />

### Como criar uma campanha web no Meta Ads

Esse artigo contém informações relevantes e um passo-a-passo sobre como configurar uma campanha web no Meta Ads para mobile, PC e apps de console com a AppsFlyer. Assim, vamos explicar como configurar a integração entre Meta Ads e AppsFlyer, como definir a configuração da campanha em ambas as plataformas e como criar landing pages com o Smart Script ou Smart Banners do OneLink.  
O processo de configuração inclui as seguintes etapas obrigatórias:

* [Configurar a integração do Meta Web Ads na AppsFlyer](#configurar-a-integração-do-meta-web-ads-na-appsflyer) (obrigatório)
* [Configurar a integração da AppsFlyer no Meta Ads](#configurar-a-integração-da-appsflyer-no-meta-ads) (obrigatório)

E as seguintes etapas opcionais:

* [Crie uma página inicial com o OneLink Smart Script (opcional](#crie-uma-landing-page-com-o-onelink-smart-script))
* [Crie uma página inicial com os banners inteligentes do OneLink](#crie-uma-página-inicial-com-os-smart-banners-do-onelink) (opcional)

<div id="set-up-meta-web-ads-integration-in-appsflyer" />

## Configurar a integração do Meta Web Ads na AppsFlyer

Comece ativando a integração do Meta Ads e definindo os postbacks que a AppsFlyer envia para o CAPI.

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Ative a integração do Meta Web Ads">

Para ativar a integração do Meta Web Ads:

1. Na AppsFlyer, no menu lateral, vá para **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
2. Pesquise por **Meta Web** e selecione-a. Você será direcionado para a página de configuração.
3. Na aba **Integração** selecione **Ativar parceiro**. **Atenção:** O botão deve permanecer ativado (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ligado</Anchor>) enquanto trabalhar com o parceiro.
4. Desative a **Privacidade avançada** (se você estiver configurando uma integração de aplicativos iOS).
5. **Compartilhamento de dados de correspondência avançada:** Ative para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash, sobrenome com hash e ID de login do Facebook, com a Meta, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.
6. Preencha o campo **Pixel ID**. Você pode recuperar o ID do pixel do seu Meta Ads Manager:
   1. <span class="af-ol-a"></span>No menu lateral do [Ads manager](https://www.facebook.com/ads/manager), vá para **Todas as ferramentas** > **Gerenciador de eventos**. **Atenção:** Certifique-se de selecionar a empresa certa no menu suspenso no canto superior direito.
   2. No menu lateral do **Gerenciador de eventos**, selecione **Fontes de dados**. Você verá uma lista dos seus pixels. Caso você não encontre um pixel para o negócio selecionado, você pode criá-lo.
   3. Copie o ID do pixel exibido abaixo do nome do pixel.  
      e cole-o no  
      Campo **Pixel ID** na AppsFlyer.
7. Preencha o campo **Token de acesso**. Para recuperar o token de acesso, siga [estas instruções](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
8. Ative a opção **Limitar o uso do Meta Ads sobre informações pessoais dos usuários (CCPA)** para garantir compliance com as <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>. **Observação**: O cumprimento dos regulamentos de privacidade da CCPA limita os dados provenientes de usuários do Anúncios da Meta com sede na Califórnia.

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. Ative a atribuição de view-through">

A AppsFlyer oferece suporte para a atribuição de view-through através de campanhas Meta Web usando um [Smart Script](#set-up-smart-script-crossplatform-landing-page) ou uma landing page habilitada para [Smart Banner](#set-up-smart-banners-landing-page). Isso permite a atribuição de instalação de aplicativos por modelagem probabilística (PMOD), que é acionada por impressões de anúncios, mesmo quando os usuários não clicam diretamente no anúncio.

Quando um usuário clica em um anúncio do Meta Web e acessa uma landing page habilitada para [Smart Script](#set-up-smart-script-crossplatform-landing-page) ou [Smart Banner](#set-up-smart-banners-landing-page), a AppsFlyer pode atribuir a instalação do aplicativo mais adiante. Se disponível, `fbclid` será incluído no postback enviado para o Meta, para garantir a confiança na atribuição.

**Para habilitar a atribuição de view-through para Meta Web:**

1. Na AppsFlyer, na barra lateral, abra **Collaborate** > **Partner Integrations > Active Integrations** > **Meta web ads**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[Opcional]** Ative a **Prioridade equivalente de atribuição cross-platform** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. Configure os postbacks de eventos in-app">

Atualmente, as instalações são os únicos eventos que acionam postbacks padrão automáticos para o Meta Ads. Para outros tipos de eventos, você pode criar postbacks personalizados mapeando eventos da AppsFlyer para eventos do Meta Ads, que podem ser visualizados no [Meta Events Manager.](https://www.facebook.com/business/help/1541268312717919?id=818859032317965)  
Para definir os postbacks de eventos in-app, faça o seguinte:

1. Ative **Postbacks de eventos in-app.**
2. Se necessário, defina a janela de postback de eventos in-app (leia mais sobre a configuração da janela de postback de eventos in-app em geral <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">neste artigo</Anchor>).
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna de **eventos da AppsFlyer**, selecione o nome do evento na caixa suspensa. A AppsFlyer recebe o nome do evento do SDK integrado ao seu aplicativo ou dos eventos de servidor para servidor.
5. Na coluna **mapeado para o evento do parceiro,** selecione na caixa suspensa o evento de parceiro predefinido mais adequado ou selecione PERSONALIZADO.
6. Na coluna **oara usuários de**, selecione a opção de envio para o evento:
   * **Apenas este parceiro**: enviar postbacks apenas quando este evento for atribuído a Meta Ads.
   * **Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.
7. Na coluna **including**, selecione se os eventos serão enviados com os valores de receita. Veja a seção <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.

   <div id="note-1" />

   > 📘 **Nota**
   >
   > Se você estiver configurando um evento de compra, defina a coluna **including** para **Values and revenue**. Selecionar qualquer outra opção fará com que o postback falhe.

8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Guardar Integração**.
10. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
    1. <span class="af-ol-a"></span>No canto superior esquerdo clique no nome do aplicativo para abrir a lista de aplicativos.
    2. Selecione um aplicativo diferente a partir da lista suspensa.
    3. Repita as etapas de integração para o aplicativo selecionado.

<div id="note-2" />

> 📘 **Atenção**
>
> Ao enviar eventos S2S para `metaweb_int`, o payload S2S deve incluir os parâmetros `ua` (User Agent) e `ip` (IP address). Esses valores são obrigatórios para a otimização de campanhas via Meta CAPI. A AppsFlyer os inclui automaticamente nos eventos do SDK. Para eventos S2S, os anunciantes devem enviá-los explicitamente. Leia <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API de eventos de servidor para servidor para mobile</Anchor>.

</Accordion>

<div id="set-up-appsflyer-integration-in-meta-ads" />

## Configurar a integração da AppsFlyer no Meta Ads

Execute as próximas etapas no Meta Ads Manager.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Defina o tipo, o objetivo e as metas da campanha">

1. Faça login no Meta Ads e crie uma campanha.
2. Em **Objetivo da campanha**, selecione uma das seguintes opções: [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **Vendas**: Isso permite que o Meta faça a otimização visando um evento específico (seu principal KPI).
   * **Tráfego**: Isso permite que o Meta faça a otimização visando cliques em anúncios. Essa opção só deve ser usada se você não possui outros KPIs, ou se o volume de outros eventos de KPI for muito baixo.
3. [Opcional] Se você quiser adicionar um objetivo personalizado às opções acima, faça o seguinte:
   1. <span class="af-ol-a"></span>No Meta Ads, selecione o evento personalizado que você deseja definir como objetivo da campanha e marque-o como uma ação de conversão em Meta Ads.
   2. Na AppsFlyer, na página de **integração do Meta Web**, em **Postbacks de eventos in-app, mapeie um evento** da AppsFlyer para um evento de parceiro personalizado (na coluna de eventos **mapeados para parceiros**) e nomeie-o com o mesmo nome da ação de conversão no Meta Ads.

      <div id="note-3" />

      > 📘 **Nota**
      >
      > Para saber mais sobre os objetivos da campanha no Meta, consulte a [documentação da Meta](https://www.facebook.com/business/help/175683976191028).

4. Em **Local de conversão**, selecione **Website**. [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. Em **Pixel**, insira o mesmo ID de pixel que você inseriu para `metaweb_int` no Marketplace de parceiros da AppsFlyer. Para saber mais sobre o Meta Pixel, consulte a [documentação do Meta](https://www.facebook.com/business/help/742478679120153) (é necessário fazer login).
6. Clique em **Próximo**.

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. Definir URL de destino">

1. Em **Destination**, na **URL do site**, insira a URL que serve como destino para seu anúncio. A URL deve ser para um dos seguintes:

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **Uma página inicial na web:** O uso é recomendado quando:

     * Você tem um aplicativo em várias plataformas.
     * Você deseja usar a landing page para fornecer mais informações sobre o produto anunciado.
     * Você quer usar a página de destino para coletar mais dados.

     Para todos esses casos de uso, crie uma [landing page com um Smart Script](#crie-uma-landing-page-com-o-onelink-smart-script) ou [um Smart Banner](#crie-uma-página-inicial-com-os-smart-banners-do-onelink).
   * **Links de atribuição da AppsFlyer**: O uso de links de atribuição da AF (OneLink, plataforma única ou multiplataforma) é recomendado quando você deseja que o usuário seja redirecionado diretamente para a loja para baixar o aplicativo sem antes visitar uma página inicial.

     <div id="important" />

     > 🚧 **Importante!**
     >
     > Às vezes, o uso de links de atribuição de AF pode levar a erros. Se isso ocorrer, peça uma solução aos representantes da Meta ou simplesmente use uma página de destino da web como URL de destino.

2. Clique em **Criar um parâmetro de URL** para adicionar os parâmetros de URL ao URL (seja um URL de página de destino ou um link de atribuição de AF).
3. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. Mapeie os parâmetros da AppsFlyer de acordo com seus valores do Meta.

   * Se a URL de destino for **uma landing page, um link de atribuição do OneLink ou um link de atribuição de plataforma única, mapeie os seguintes parâmetros da AF para** os equivalentes no Meta: 

| Parâmetro AF | Valor mapeado no Meta |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#c">`C`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     Um exemplo da URL resultante deve ser:

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * Se o APK do seu aplicativo NÃO estiver hospedado na Google Play Store, adicione o parâmetro <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> e mapeie-o para a URL da loja. Exemplo: `https://Add-your-store-url.com`.
   * Se a URL de destino for um **PC ou uma loja de console**, crie o link seguindo as instruções na tabela abaixo. Para informações adicionais, consulte: <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Links de atribuição direta da plataforma CTV, PC e console</Anchor>

<table><thead><tr><th colspan="2">Estrutura do link de atribuição</th></tr></thead><tbody><tr><td>URL base</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Parâmetros de caminho obrigatórios</td><td><ul><li>platform<br/>Exemplo: steam</li><li>app_id<br/>Exemplo: 123456</li></ul></td></tr><tr><td>Parâmetros de consulta obrigatórios</td><td><ul><li>media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Outros parâmetros</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#parâmetros" target="_blank">Ver todos os parâmetros</a></td></tr><tr><td>Estrutura da URL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     Mapeie os seguintes parâmetros da AppsFlyer para seus equivalentes Meta:

| Parâmetro AF | Valor mapeado do Meta |
| --- | --- |
| `media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     Um exemplo de URL multiplataforma:

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   <div id="note-4" />

   > 📘 **Nota**
   >
   > O Meta adiciona `fbclid={{fbclid}}` à URL de destino automaticamente quando o anúncio é clicado


   <div id="tip" />

   > 👍 **Dica**
   >
   > Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web)


<div id="note-5" />

> 📘 **Atenção**
>
> Para obter um guia abrangente sobre os parâmetros do link de AF, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-do-link-de-atribuição">Parâmetros do link de atribuição.</Anchor>

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. Selecione eventos monitorados">

Use a seção Rastreamento para selecionar os eventos de conversão promovidos pelo seu anúncio (a configuração dos eventos é feita por meio do [Gerenciador de Eventos](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)).

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

<div id="important-1" />

> 🚧 **Importante!**
>
> Certifique-se de não escolher **Eventos de aplicativos**, pois o Meta reivindicará essas conversões usando a SRN API, o que pode causar desalinhamentos de relatórios e de otimização.

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## Crie uma landing page com o OneLink Smart Script

**Jornada do usuário:** O usuário clica em um anúncio Meta e é direcionado para seu site mobile. Ele chegam a uma página com botões de CTA, solicitando que ele faça download do seu aplicativo de uma ou mais plataformas. Clicar no botão redireciona o usuário para a loja.

<div id="end-to-end-data-flow" />

<Accordion title="Fluxo de dados de ponta a ponta">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. O URL do anúncio do Meta inclui o parâmetro `pid=metaweb_int`. Quando o usuário clica no anúncio, um parâmetro `fbclid` é automaticamente anexado ao URL clicado.
2. O usuário é redirecionado para o destino da URL - uma página de destino contendo um script inteligente.
3. Quando a landing page é carregada, o Smart Banner envia uma impressão para a AppsFlyer contendo os parâmetros da URL de entrada. A impressão permitirá a atribuição de visualização completa na página inicial da web. Para saber mais sobre impressões e atribuição de visualizações, clique <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aqui</Anchor>.
4. O Smart Script gera os URLs de saída para os botões de CTA na página com base nos parâmetros do URL de entrada, incluindo o parâmetro `fbclid`. Os botões podem levar a:
   * Google Play e App Store por meio de um link de atribuição do OneLink.
   * Lojas de várias plataformas (por exemplo, CTV, Epic e Steam). Nesse caso de uso, o Smart Script gera um único link de atribuição de plataforma para cada plataforma, levando à loja da plataforma especificada.
   * Download de um arquivo APK para o dispositivo do usuário.
5. Quando o usuário clica no botão CTA, o clique é acionado e registrado na AppsFlyer.
6. Em seguida, ele é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um [referenciador de instalação](https://www.appsflyer.com/glossary/install-referrer/) estiver disponível.
9. Um postback contendo os `fbclid` parâmetros e outros parâmetros do evento é gerado e enviado ao Meta por meio da API CAPI. O Meta usa o parâmetro `fbclid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Configurar uma página inicial do Smart Script">

Para configurar suas campanhas do Meta Ads, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Como criar templates do OneLink</Anchor>.
2. Crie um script inteligente. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Como criar um script inteligente do OneLink</Anchor>.

   <div id="note-6" />

   > 📘 **Nota**
   >
   > As instruções abaixo se concentram nas etapas específicas necessárias para configurar uma campanha do Meta Ads com o Smart Script. Para um guia abrangente sobre como configurar campanhas de Smart Script, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Como criar um Smart Script do OneLink</Anchor> no artigo de configuração do <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>.

3. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados ao URL de entrada, abra o Meta Ads Manager e verifique os parâmetros de URL definidos durante a criação do URL de destino. Para mais informações, consulte: [Configurar URL de destino](#b-set-destination-url).
4. Mapeie os parâmetros de URL de entrada necessários para a campanha de Meta Ads com os parâmetros de URL de saída que serão enviados à AppsFlyer quando o usuário clicar no botão CTA:
   * **PID**: Certifique-se de que o Smart Script pegue o valor do parâmetro `pid=metaweb_int` da URL de entrada e o mapeie para os parâmetros correspondentes na URL de saída.
   * **FBCLID**: O parâmetro `fbclid` é essencial para enviar com sucesso postbacks de eventos in-app para o Meta. O mapeamento do parâmetro FBCLID da URL de saída depende da sua versão do Smart Script:

     * SDK versão 2.8.1 e superior O parâmetro `fbclid` é encaminhado automaticamente para o parâmetro de URL de saída quando presente na URL de entrada, eliminando a necessidade de mapeamento manual.
     * Versão 2.8.0 e inferior: O parâmetro `fbclid` deve ser mapeado manualmente na seção de **mapeamento de parâmetros de URL** da página do **Smart Script**:
       1. Em **Mapeamento para**, selecione **parâmetro personalizado**.
       2. Em **parâmetro de URL de saída** e **parâmetros de URL de entrada**, insira **fbclid**.

     <div id="note-7" />

     > 📘 **Nota**
     >
     > Para exibir nos relatórios de dados brutos da AppsFlyer, o `fbclid` parâmetro de entrada também deve ser mapeado (além do parâmetro de saída `fbclid`) para um dos parâmetros de saída. `af_sub[1-5]` Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>.


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar uma landing page multiplataforma do Smart Script">

Para configurar suas campanhas do Meta Ads com o smart script para páginas de destino multiplataforma, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Como criar templates do OneLink</Anchor>.
   * Ative seu template do OneLink para atribuição multiplataforma, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#crie-ou-edite-um-template-do-onelink-para-atribuição-cross-platform">aqui.</Anchor>
2. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados ao URL de entrada. Para revisar os parâmetros anexados ao URL de entrada, abra o Meta Ads Manager e examine os parâmetros de URL definidos durante a criação do URL de destino. Para obter mais informações, consulte [Definir URL de destino](#b-set-destination-url).
3. Decida para cada parâmetro de entrada o parâmetro de saída para o qual ele será mapeado. Por exemplo, `af_site_id` o URL de entrada será mapeado para o URL `af_site_id` de saída.
4. Decida o valor padrão para os parâmetros de saída obrigatórios que não podem estar vazios.
5. Envie ao desenvolvedor as seguintes informações:
   * Seu mapeamento de parâmetros de entrada e saída. O desenvolvedor criará um script que gera um URL direto de saída com base no mapeamento de parâmetros de entrada e saída.
   * Os valores padrão dos parâmetros. O script preencherá os parâmetros de URL de saída com os valores padrão sempre que não houver valores de parâmetros de URL de entrada correspondentes.
   * Se você estiver usando um link de atribuição do OneLink, envie o ID do domínio e do template para seu desenvolvedor. O desenvolvedor usa isso para criar o URL de saída do OneLink. Por exemplo: `yourbrand.onelink.me/A1b2` exemplo de domínio de marca: `click.yourbrand.com/A1b2`
   * Envie ao seu desenvolvedor os seguintes links do Dev Hub:
     * [Exemplos de instruções e códigos](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre como criar URLs diretos de saída para plataformas não móveis.
     * [Uma demonstração e instruções](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) para criar uma página inicial multiplataforma.
   * Lembre seu desenvolvedor de incluir o parâmetro de entrada `fbclid` no URL de saída.

     <div id="note-8" />

     > 📘 **Nota**
     >
     > Para exibir nos relatórios de dados brutos da AppsFlyer, o `fbclid` parâmetro de entrada também deve ser mapeado (além do parâmetro de saída `fbclid`) para um dos parâmetros de saída. `af_sub[1-5]`


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Crie uma página inicial com os Smart Banners do OneLink

**Jornada do usuário:** O usuário clica em um anúncio Meta e é direcionado para seu site mobile. Eles chegam a uma página e um Smart Banner é exibido com um CTA para baixar o aplicativo na loja de aplicativos.

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="Fluxo de dados de ponta a ponta">

1. O URL do anúncio do Meta inclui o parâmetro `pid=metaweb_int`. Quando o usuário clica no anúncio, um parâmetro `fbclid` é automaticamente anexado ao URL clicado.
2. O usuário é redirecionado para o destino da URL - uma página inicial que contém um Smart Banner.
3. Quando a página inicial é carregada, o Smart Banner envia um evento de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impressão</Anchor> para a AppsFlyer contendo os parâmetros do URL de entrada. Essa impressão permite a atribuição de view-through para a landing page. Para saber mais sobre atribuição de impressões e de view-through, clique <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">aqui</Anchor>.
4. O Smart Banner gera a URL de saída para o botão CTA no banner. O URL de saída é baseado nos parâmetros do URL de entrada, incluindo o parâmetro `fbclid`. O Smart Banner pode gerar somente links baseados no OneLink.
5. Quando o usuário clica no botão CTA do Smart Banner, o clique é acionado e registrado na AppsFlyer.
6. O usuário é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se o referenciador de instalação estiver disponível.
9. Um postback contendo os `fbclid` parâmetros e outros parâmetros do evento é gerado e enviado ao Meta por meio da API CAPI. O Meta usa o parâmetro `fbclid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Configurar uma página inicial de Smart Banners">

Para configurar suas campanhas de Smart Banners do Meta Ads, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Como criar templates do OneLink</Anchor>.
2. Crie um Smart Banner.

   <div id="note-9" />

   > 📘 **Nota**
   >
   > As instruções abaixo se concentram nas etapas específicas necessárias para configurar uma campanha do Meta Ads com Smart Banners. Para obter um guia abrangente sobre como configurar campanhas de Smart Banners, consulte a <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#configuração">seção de configuração</Anchor> do artigo <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners —mobile web-to-app (para profissionais de marketing).</Anchor>

3. Defina os parâmetros do Smart Banner para campanhas do Meta Ads:
   * Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Mais importante ainda, `pid=metaweb_int` e `fbclid` estão disponíveis na URL de entrada para permitir que o Smart Banner os colete. Esses dois parâmetros são necessários para atribuição e envio de postbacks para o Meta Ads. Para revisar os parâmetros que são anexados ao URL de entrada, abra o Meta Ads Manager e examine os parâmetros de URL definidos durante a criação do URL de destino, consulte: [Configurar URL de destino](#b-set-destination-url).

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Veja os dados de atribuição de web-to-app

Embora os eventos de conversão baseados na web sejam enviados para a Meta sob o PID original `metaweb_int`, eles são relatados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `Facebook Ads`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visão unificada permite que você analise a performance de campanhas na web e no app em um só local, incluindo relatórios completos de custos na web e no mobile.

<div id="view-in-the-dashboard" />

### Ver no dashboard

Todas as atribuições de web-to-app do Meta aparecem sob `Facebook Ads` nos dashboards de Visão Geral e de Atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do app e da web dentro dos seus dados do Meta Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver em dados brutos e relatórios da API

* **Exportações de dados brutos e respostas da API** incluem o PID `Facebook Ads` no campo `media_source` para a atividade web do Meta. Para verificar os detalhes da configuração da campanha web, consulte o campo `original_url`, que mostra `metaweb_int` como o PID usado durante a criação de campanhas web.
* **Relatórios de postback** mostram `metaweb_int` como a fonte de mídia original para a qual o postback foi enviado.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Custo, cliques e dados de impressões | Dados de custo, cliques e impressões para Meta Ads Web (`metaweb_int`) estão disponíveis através da integração do Meta Ads (`Facebook Ads`).<ul><li>Para obter os dados, certifique-se de conectar a conta da ad network ao PID principal (`Facebook Ads`):<ul><li>Com assinatura do ROI360: na página **Configurações de Custo**.</li><li>Sem assinatura do ROI360: na página **Integração Ativa** (aba **Custos**).</li></ul></li><li>Para visualizar dados de custo, cliques e impressões para campanhas de Meta Ads Web, certifique-se de que o campaign ID (<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) tenha sido incluído no link de atribuição.</li><li>O link de atribuição deve incluir toda a hierarquia da campanha para visualizar dados de custo, cliques e impressões vinculados à atribuição em um nível mais granular.</li></ul> |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=vis%C3%A3o-geral h_01J8CYG29BETYPZ03A1X54M3ZF=nota prerequisite=pr%C3%A9-requisitos h_01HZKNS17JTCXE4JMZ64NEVPS6=pr%C3%A9-requisitos how-to-create-a-meta-ads-campaign=como-criar-uma-campanha-web-no-meta-ads h_01HZKNS17JERCAKZHK43ZQWARJ=como-criar-uma-campanha-web-no-meta-ads set-up-meta-ads-integration-in-appsflyer=configurar-a-integra%C3%A7%C3%A3o-do-meta-web-ads-na-appsflyer h_01HZKNS17J284R2MAN42WV7F0S=configurar-a-integra%C3%A7%C3%A3o-do-meta-web-ads-na-appsflyer h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=nota-1 h_01_s2s_metaweb_ua_ip=aten%C3%A7%C3%A3o set-up-appsflyer-integration-in-meta-ads=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-meta-ads h_01HZKNS17JJWX7N9W6BN05B57C=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-meta-ads h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=nota-2 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=importante h_01J2V9WF300WDY0PWV68TDR9TT=nota-3 h_01K88MSNRX9QFQ49FN2MXPMADX=dica 01J2V903C36X5K6VRPGQQGWFMW=aten%C3%A7%C3%A3o-1 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=importante-1 create-landing-page-with-onelink-smart-script=crie-uma-landing-page-com-o-onelink-smart-script h_01HZKNS17KPJMP74HQKWY022T2=crie-uma-landing-page-com-o-onelink-smart-script h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=nota-7 h_01HZKNS17K2W4XJB0BH87RZYTJ=nota-6 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=nota-6 create-landing-page-with-onelink-smart-banners=crie-uma-p%C3%A1gina-inicial-com-os-smart-banners-do-onelink h_01HZKNS17KH8NQ68RPZGMEAQTV=crie-uma-p%C3%A1gina-inicial-com-os-smart-banners-do-onelink h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=nota-7 meta%20view=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-webtoapp-attribution-data-from-november-2-2025=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-da-api h_01K88J8JFN8W2572N92466YFZQ=ver-em-dados-brutos-e-relat%C3%B3rios-da-api traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01JEZXJNF1C932KGAEFS4P5D51=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
