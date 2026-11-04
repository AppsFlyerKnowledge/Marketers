---
title: TikTok for Business — Crie campanhas na web
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
  created_at: '2025-10-31T12:09:51Z'
  edited_at: '2026-09-16T00:30:34Z'
  id: 40496161157521
  locale: pt
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/pt/articles/40496161157521
---
> **Resumo:** Use campanhas web do TikTok Ads para atribuir conversões Web-to-app do TikTok Ads

<div id="overview" />

## Escritórios

A AppsFlyer é compatível com a integração com o TikTok Ads (`tiktokweb_int`) para campanhas de aquisição de usuários baseadas na web, permitindo que você reporte dados de atribuição e conversão diretamente por meio da Events API do TikTok. O TikTok pode então usar esses dados para otimizar a segmentação de anúncios, mensurar a performance e criar audiências personalizadas.

<div id="important" />

> 🚧 **Importante!**
>
> Atualmente, a integração com o TikTok web não oferece suporte ao envio de postbacks de reengajamento para a CAPI.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração do TikTok web, certifique-se de que você possui uma conta comercial no [TikTok Ads Manager](https://getstarted.tiktok.com/grow-your-business-gb?lang=en&attr_source=google&attr_source=google&attr_medium=search-br-ad&attr_medium=search-br-ad&attr_adgroup_id=155057567247&attr_adgroup_id=155057567247&attr_term=tiktok%20ads%20manager&attr_term=tiktok%20ads%20manager&no_parent_redirect=1&no_parent_redirect=1&creative=%7BGenZCopy%7D&matchtype=e&gad_source=1&gad_campaignid=20368896948&gbraid=0AAAAACeGRgRdqveOjiUJwxN0-j9g7VjPg&gclid=Cj0KCQjwmYzIBhC6ARIsAHA3IkTKsL0d1xAZLIO_9GIkDDIJR-jZs9jDGVa1hTDbsLzcxZl2j6p7ITcaAhf1EALw_wcB).

<div id="how-to-create-a-tiktok-web-ads-campaign" />

### Como criar uma campanha web no TikTok Ads

Este artigo contém informações relevantes e um passo a passo sobre como configurar uma campanha web no TikTok Ads para apps mobile com a AppsFlyer. Assim, vamos explicar como configurar a integração entre TikTok Ads e AppsFlyer, como definir a configuração da campanha em ambas as plataformas e como criar landing pages com o OneLink Smart Script ou OneLink Smart Banners.

O processo de configuração inclui as seguintes etapas obrigatórias:

* [Configurar a integração do TikTok Web Ads na AppsFlyer](#configurar-a-integração-do-tiktok-web-ads-na-appsflyer) (Obrigatório)
* [Configurar a integração da AppsFlyer no TikTok Ads](#configurar-a-integração-da-appsflyer-no-tiktok-ads) (Obrigatório)

E as seguintes etapas opcionais:

* <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#crie-uma-landing-page-com-o-onelink-smart-script">#create-a-landing-page-with-onelink-smart-script</Anchor> (opcional)
* [Criar uma landing page com OneLink Smart Banners](#crie-uma-landing-page-com-os-smart-banners-do-onelink) (opcional)

<div id="set-up-tiktok-web-ads-integration-in-appsflyer" />

## Configurar a integração do TikTok Web Ads na AppsFlyer

Comece ativando a integração do TikTok web e definindo os postbacks que a AppsFlyer envia para a Events API.

<div id="1-activate-the-tiktok-web-ads-integration" />

<Accordion title="1. Ative a integração do TikTok Web Ads">

Para ativar a integração do TikTok Web Ads:

1. Na AppsFlyer, no menu lateral, abra **Colaborar** > **Integrações de parceiros** > **Marketplace de parceiros**.
2. Pesquise por **TikTok Web** (ou `tiktokweb_int`) e selecione-o. Você será direcionado para a página de configuração.
3. Na aba **Integração** selecione **Ativar parceiro**. O botão deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor> enquanto você trabalhar com o parceiro.
4. Desative a **Privacidade Avançada** (se estiver configurando uma integração de aplicativo iOS).
5. **Compartilhamento de dados de correspondência avançada:** Ative essa opção para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, com o TikTok, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.
6. **ID do pixel:** Insira o ID do pixel. Você pode gerá-lo ou recuperá-lo no seu TikTok Ads Manager seguindo as instruções detalhadas <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">AQUI</Anchor>.
7. **Token de acesso:** Insira o token de acesso. Para gerá-lo ou recuperá-lo, siga <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">estas instruções</Anchor>
8. **Limitar o uso, pelo TikTok Ads, de informações pessoais dos usuários (CCPA):** Ative esta opção para permitir a compliance com as <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>.

   <div id="note" />

   > 📘 **Nota**
   >
   > O cumprimento das regulamentações de privacidade da CCPA limita os dados provenientes de usuários de anúncios do TikTok baseados na Califórnia ou em outros estados sensíveis dos EUA.


</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Ative a atribuição de view-through">

A AppsFlyer oferece suporte para a atribuição de view-through em campanhas web do TikTok usando uma landing page habilitada para [Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [Smart Banner](#crie-uma-landing-page-com-os-smart-banners-do-onelink). Isso permite a atribuição de instalação de aplicativos por modelagem probabilística (PMOD), que é acionada por impressões de anúncios, mesmo quando os usuários não clicam diretamente no anúncio.

Quando um usuário clica em um anúncio web do TikTok e acessa uma landing page habilitada para [Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [Smart Banner](#crie-uma-landing-page-com-os-smart-banners-do-onelink), a AppsFlyer pode atribuir a instalação do aplicativo mais adiante. Se disponível, o `ttclid` será incluído no postback para o TikTok a fim de aumentar a confiabilidade da atribuição.

**Para habilitar a atribuição de view-through do TikTok web:**

1. Na AppsFlyer, no menu lateral, abra **Integrações ativas** > **anúncios web do TikTok**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[Opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba do **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Etapa 2: Configure os postbacks de eventos in-app">

Atualmente, as instalações são os únicos eventos que acionam postbacks padrão automáticos para o TikTok Ads. Para outros tipos de eventos, você pode criar postbacks personalizados mapeando eventos da AppsFlyer para eventos do TikTok Ads, que podem ser visualizados no TikTok Ads Manager.

Para definir os postbacks de eventos in-app, faça o seguinte:

1. Ative os **postbacks de eventos in-app**.
2. Se necessário, defina a janela de postback de eventos in-app (leia mais sobre a configuração da janela de postback de eventos in-app em geral in <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">este artigo</Anchor>).
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna **evento da AppsFlyer** , selecione o nome do evento na caixa suspensa. A AppsFlyer recebe o nome do evento do SDK integrado no aplicativo ou de eventos de server-to-server.
5. Na coluna **mapeado para o evento do parceiro** column, selecione na caixa suspensa o evento de parceiro predefinido mais adequado.
6. Na coluna **Para usuários de** , selecione **Somente este parceiro** para garantir que os postbacks de eventos in-app sejam enviados exclusivamente para eventos realizados por usuários que se originaram desse parceiro.
7. Na coluna **Incluindo** , selecione se os eventos serão enviados com os valores de receita. See <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.

   <div id="note-1" />

   > 📘 **Nota**
   >
   > * Se você estiver configurando um evento de compra, defina a coluna **including** para **Values and revenue**. Selecionar qualquer outra opção fará com que o postback falhe.
   > * Atualmente, apenas o evento de compra pode ser configurado para incluir receita.

8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Salvar integração**.
10. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
    1. No canto superior esquerdo clique no nome do aplicativo para abrir a lista de aplicativos.
    2. Selecione um aplicativo diferente a partir da lista suspensa.
    3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<div id="set-up-appsflyer-integration-in-tiktok-ads" />

## Configurar a integração da AppsFlyer no TikTok Ads

Execute as próximas etapas no TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Defina o tipo, objetivo e metas da campanha.">

Você pode escolher qualquer evento in-app predefinido enviado pela AppsFlyer como objetivo da sua campanha ou escolher “Download” se quiser otimizar para instalações de aplicativos mobile.

<div id="warning" />

> ❗️ **Atenção**
>
> Se quiser garantir que seus eventos de conversão acionados por web-to-app sejam enviados pela TikTok Events API, ignore <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#measuring-app-activity-for-nonapp-campaigns">estas etapas</Anchor> ao criar a campanha; caso contrário, o TikTok atribuirá essas conversões por meio da SRN API, o que pode causar desalinhamentos nos relatórios e na otimização.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Defina a URL de destino">

1. Em **Destino**, na **URL do site**, insira a URL que serve como destino para seu anúncio. A URL deve ser para:
   * **Uma landing page na web:** O uso é recomendado quando:
     * Você tem um aplicativo em várias plataformas.
     * Você deseja usar a landing page para fornecer mais informações sobre o produto anunciado.
     * Você quer usar a página de destino para coletar mais dados.

       Para todos esses casos de uso, crie uma landing page habilitada para [Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [Smart Banner](#crie-uma-landing-page-com-os-smart-banners-do-onelink)-enabled landing page.
   * **Links de atribuição da AF:** Usar links de atribuição da AF (OneLink, plataforma única ou multiplataforma) é recomendado quando você deseja que o usuário seja redirecionado diretamente para a loja para fazer o download do aplicativo sem antes visitar uma landing page.
2. Clique em **Criar um parâmetro de URL** para adicionar os parâmetros de URL à URL (seja uma URL de landing page ou um link de atribuição da AppsFlyer).
3. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**.
4. Mapeie os parâmetros da AppsFlyer de acordo com seus valores do TikTok. Os parâmetros que você mapeará dependem de a URL de destino apontar para uma landing page, um link de atribuição ou uma loja de PC ou console.

   <div id="landing-page-or-attribution-link" />

   #### Landing page ou link de atribuição

   Se a URL de destino for **uma landing page, um link de atribuição do OneLink ou um link de atribuição de plataforma única**, mapeie os seguintes parâmetros da AppsFlyer para seus equivalentes no TikTok:

| Parâmetro AF | Valor mapeado no TikTok |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `tiktokweb_int` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#c">`c`</Anchor>* | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * Para simplificar a análise da campanha, inclua o tipo de campanha, (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web).

   Um exemplo da URL resultante deve ser:

   ```
   https://app.appsflyer.com/{app_id}?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
   ```

   Se o APK do seu aplicativo NÃO estiver hospedado na Google Play Store, adicione o parâmetro <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> e mapeie-o para a URL da loja. Exemplo: `https://Add-your-store-url.com`.

   <div id="pc-or-console-store" />

   #### Loja de PC ou console

   Se a URL de destino for um **PC ou uma loja de console**, crie o link seguindo as instruções na tabela abaixo. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Links de atribuição direta das plataforma de CTV, PC e console</Anchor>

| Componente do link | Valor |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parâmetros de caminho obrigatórios | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| Parâmetros de consulta obrigatórios | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Outros parâmetros | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links#parâmetros">Ver todos os parâmetros</Anchor> |
| Estrutura da URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

   Mapeie os seguintes parâmetros da AppsFlyer para seus equivalentes do TikTok:

| Parâmetro AF | Valor mapeado no TikTok |
| --- | --- |
| `media_source` | `tiktokweb_int` |
| `af_campaign` * | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * Para simplificar a análise da campanha, inclua o tipo de campanha, (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web).

   Um exemplo de URL multiplataforma:

   ```
   https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__campaign_id__&af_campaign=__campaign_name__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
   ```

   <div id="note-2" />

   > 📘 **Nota**
   >
   > O TikTok adiciona o `ttclid={{ttclid}}` à URL de destino automaticamente quando o anúncio é clicado


</Accordion>

## Criar uma landing page com o OneLink Smart Script

**Jornada do usuário:** O usuário clica em um anúncio do TikTok e é direcionado para seu site web mobile. Ele chegam a uma página com botões de CTA, solicitando que ele faça download do seu aplicativo de uma ou mais plataformas. Ao clicar em um botão, o usuário é direcionado para a loja de aplicativos.

<div id="endtoend-data-flow" />

<Accordion title="Fluxo de dados de ponta a ponta">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. A URL do anúncio do TikTok inclui o  `pid=tiktokweb_int` parâmetro. Quando o usuário clica no anúncio, um `ttclid` parâmetro é automaticamente anexado à URL clicada.
2. O usuário é redirecionado para o destino da URL: uma landing page que contém um Smart Script.
3. Quando a landing page é carregada, o Smart Banner envia uma impressão para a AppsFlyer contendo os parâmetros da URL de entrada. A impressão permitirá a atribuição de view-through na landing page da web. Para saber mais sobre impressões e atribuição de view-through, leia <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">este artigo</Anchor>.
4. O Smart Script gera as URLs de saída para os botões CTA na página com base nos parâmetros da URL de entrada, incluindo o `ttclid` parâmetro. Os botões podem levar a:
   * Google Play e App Store por meio de um link de atribuição do OneLink.
   * Lojas de várias plataformas (exemplo: CTV, Epic e Steam). Nesse caso, o Smart Script gera um único link de atribuição para cada plataforma, levando à loja especificada.
   * Download de um arquivo APK para o dispositivo do usuário.
5. Quando o usuário clica no botão CTA, o clique é acionado e registrado na AppsFlyer.
6. Em seguida, ele é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelo probabilístico ou, se um [install referrer](https://www.appsflyer.com/glossary/install-referrer/) estiver disponível, deterministicamente.
9. Um postback contendo os `ttclid` parâmetros e outros parâmetros de evento é gerado e enviado ao TikTok por meio da Events API. O TikTok usa o `ttclid` parâmetro para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Configurar uma landing page de Smart Script">

Para configurar suas campanhas do TikTok Ads com o Smart Script, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
2. Crie um Smart Script. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">como criar um Smart Script do OneLink</Anchor>.

   <div id="note-3" />

   > 📘 **Nota**
   >
   > As instruções abaixo se concentram nas etapas específicas necessárias para configurar uma campanha do TikTok Ads com o Smart Script. Para um guia abrangente sobre como configurar campanhas de Smart Script, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Como criar um OneLink Smart Script</Anchor> no artigo de configuração do <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2</Anchor>.

3. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o TikTok Ads Manager e verifique os parâmetros de URL definidos durante a criação da URL de destino. Para obter mais informações, consulte  [Set destination UR](#2-set-destination-url)[L](#set-destination-url).
4. Mapeie os parâmetros de URL de entrada necessários para a campanha do TikTok Ads com os parâmetros de URL de saída que serão enviados à AppsFlyer quando o usuário clicar no botão CTA:
   * **PID**: Certifique-se de que o Smart Script pegue o valor do parâmetro `pid=tiktokweb_int` da URL de entrada e o mapeie para os parâmetros correspondentes na URL de saída.
   * **TTCLID**: O `ttclid` parâmetro é essencial para enviar com sucesso postbacks de eventos in-app para o TikTok. O `ttclid` parâmetro deve ser mapeado manualmente na **seção de mapeamento de parâmetros de URL** da página do **Smart Script** page:

     1. Em **Mapeamento para**, selecione **Parâmetro personalizado**.
     2. Em **Outgoing URL parameter** e **Incoming URL parameters** insira **ttclid**.

     <div id="note-4" />

     > 📘 **Nota**
     >
     > Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro de entrada `ttclid` também deve ser mapeado (além do parâmetro de saída `ttclid` ) para um dos parâmetros de saída `af_sub[1-5]` .


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar uma landing page multiplataforma do Smart Script">

Para configurar suas campanhas do TikTok Ads com o Smart Script para páginas de destino multiplataforma, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
   * Ative seu template do OneLink para atribuição multiplataforma, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#crie-ou-edite-um-template-do-onelink-para-atribuição-cross-platform">aqui</Anchor>.
2. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o TikTok Ads Manager e examine os parâmetros de URL que você definiu ao criar a URL de destino. Para obter mais informações, veja como <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">definir uma URL de destino</Anchor>.
3. Para cada parâmetro de entrada, decida o parâmetro de saída para onde ele será mapeado. Por exemplo, o parâmetro `af_site_id` na URL de entrada será mapeado para o parâmetro de `af_site_id` na URL de saída.
4. Decida o valor padrão para os parâmetros de saída obrigatórios que não podem estar vazios.
5. Envie ao seu desenvolvedor as seguintes informações:
   * Seu mapeamento de parâmetros de entrada e saída. O desenvolvedor criará um script que gera uma URL direta de saída com base no mapeamento de parâmetros de entrada e saída.
   * Os valores padrão dos parâmetros. O script preencherá os parâmetros de URL de saída com os valores padrão sempre que não houver valores de parâmetros de URL de entrada correspondentes.
   * Se você estiver usando um link de atribuição do OneLink, envie o ID do domínio e do template para seu desenvolvedor. O desenvolvedor usa isso para criar a URL de saída do OneLink. Exemplos: `yourbrand.onelink.me/A1b2` ou `click.yourbrand.com/A1b2`
   * Envie ao seu desenvolvedor os seguintes links do Dev Hub:
     * [Exemplos de instruções e códigos](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre como criar URLs de saída para plataformas não mobile.
     * [Uma demonstração e instruções](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) sobre como criar uma landing page multiplataforma.

* Lembre seu desenvolvedor de incluir o parâmetro de entrada `ttclid` na URL de saída.

  <div id="note-5" />

  > 📘 **Nota**
  >
  > Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro de entrada `ttclid` também deve ser mapeado (além do parâmetro de saída `ttclid` ) para um dos parâmetros de saída `af_sub[1-5]` .


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Crie uma landing page com os Smart Banners do OneLink

**Jornada do usuário:** O usuário clica em um anúncio do TikTok e é direcionado para o seu site mobile. Ele acessa uma página onde há um Smart Banner com um botão CTA para baixar o app na loja de aplicativos.

<div id="endtoend-data-flow::e62b5c1b" />

<Accordion title="Fluxo de dados de ponta a ponta">

1. A URL do anúncio do TikTok inclui o  `pid=tiktokweb_int` parâmetro. Quando o usuário clica no anúncio, um parâmetro `ttclid` é automaticamente anexado à URL clicada.
2. O usuário é redirecionado para o destino da URL: uma landing page que contém um Smart Banner.
3. Quando a landing page é carregada, o Smart Banner envia uma <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impressão</Anchor> para a AppsFlyer contendo os parâmetros da URL de entrada. Essa impressão permite a atribuição de view-through para a landing page. Para saber mais sobre impressões e atribuição de view-through, leia <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">este artigo</Anchor>.
4. O Smart Banner gera a URL de saída para o botão CTA no banner. A URL de saída é baseada nos parâmetros da URL de entrada, incluindo o `ttclid` parâmetro. O Smart Banner pode gerar somente links baseados no OneLink.
5. Quando o usuário clica no botão CTA do Smart Banner, o clique é acionado e registrado na AppsFlyer.
6. Em seguida, ele é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um install referrer estiver disponível.
9. Um postback com os parâmetros de `ttclid` e outros parâmetros de evento é gerado e enviado ao TikTok por meio da Events API. O TikTok usa o parâmetro `ttclid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Configurar uma landing page do Smart Banner">

Para configurar suas campanhas de Smart Banners do TikTok Ads, faça o seguinte:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
2. Crie um Smart Banner.

   <div id="note-6" />

   > 📘 **Nota**
   >
   > As instruções abaixo se concentram nas etapas específicas necessárias para configurar uma campanha do TikTok Ads com Smart Banners. Para obter um guia abrangente sobre como configurar campanhas de Smart Banners, consulte a <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#configuração">seção de configuração</Anchor> do artigo <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners — web-to-app mobile (para profissionais de marketing)</Anchor>.

3. Defina os parâmetros do Smart Banner para campanhas do TikTok Ads:
   * Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Mais importante ainda, o `pid=tiktokweb_int` e `ttclid` estão disponíveis na URL de entrada para permitir que o Smart Banner os colete. Esses dois parâmetros são necessários para atribuição e envio de postbacks para o TikTok Ads. Para revisar os parâmetros que são anexados à URL de entrada, abra o TikTok Ads Manager e examine os parâmetros de URL definidos durante a criação da URL de destino. Consulte: <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">Configurar URL de destino</Anchor>.

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Veja os dados de atribuição de web-to-app

Embora os eventos de conversão baseados na web sejam enviados ao TikTok sob o PID original `tiktokweb_int`, eles são relatados no dashboard da AppsFlyer e nos relatórios de dados brutos sob o PID `tiktokglobal_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visualização unificada permite que você analise a performance das campanhas na web e no aplicativo em um só lugar, incluindo relatórios completos de custos na web e no mobile.

<div id="view-in-the-dashboard" />

### Ver no dashboard

Todas as atribuições de Web-to-app do TikTok aparecem sob `tiktokglobal_int` nos dashboards de visão geral e de atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do aplicativo e da web nos seus dados do TikTok Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver em dados brutos e relatórios da API

As exportações de dados brutos e as respostas da API incluem o PID `tiktokglobal_int` no campo `media_source` para a atividade web do TikTok. Para verificar os detalhes da configuração da campanha na web, confira o campo `original_url`, que mostra o PID `tiktokweb_int` usado durante a criação da campanha na web.

<div id="measure-cost-clicks-and-impressions" />

## Meça custo, cliques e impressões

Você pode medir custo, cliques e impressões do TikTok junto com seus dados de atribuição Web-to-app no dashboard e nos relatórios Cost ETL (somente para clientes ROI360):

1. Conecte o TikTok como uma integração de custo no seu app mobile:  
   Vá até a aba **Cost** ou a página **Cost Settings** e conecte via `tiktokglobal_int`. Para ver instruções passo a passo, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data">Configurar a ROI360 Cost API para mensurar dados de custo</Anchor>.
2. Adicione o ID da campanha à URL da sua landing page:  
   Inclua `af_c_id` junto com a hierarquia completa da campanha na URL da landing page. Isso garante que o custo, os cliques e as impressões sejam associados aos seus dados de atribuição web no nível mais granular.

<div id="note-7" />

> 📘 **Atenção**
>
> Os dados de custo estão disponíveis apenas para clientes ROI360. Cliques e impressões estão disponíveis para todos os clientes que concluírem essa configuração.

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01K8X2TS8CYRY1XVQNEABWHVF4=escrit%C3%B3rios h_01K8X2TS8C356J1VSAG70EB8HF=importante prerequisites=pr%C3%A9-requisitos h_01K8X2TS8CEFSS92A9MRE7MQD1=pr%C3%A9-requisitos how-to-create-a-tiktok-web-ads-campaign=como-criar-uma-campanha-web-no-tiktok-ads h_01K8X2TS8CXP0R5WQN14W8S8G3=como-criar-uma-campanha-web-no-tiktok-ads set-up-tiktok-web-ads-integration-in-appsflyer=configurar-a-integra%C3%A7%C3%A3o-do-tiktok-web-ads-na-appsflyer h_01K8X2TS8CQDNNX59WDW38V24X=configurar-a-integra%C3%A7%C3%A3o-do-tiktok-web-ads-na-appsflyer h_01K8X2TS8CYNWESDXCCFCE4TTA=1-activate-the-tiktok-web-ads-integration h_01K8X2TS8C4HNWR2Z3MTMKQ92Q=nota h_01K8X2TS8C3RDCEX0R8HJGCARH=2-enable-viewthrough-attribution h_01K8X2TS8CP915Y7C5WSEYAJQV=3-set-inapp-event-postbacks h_01K8X2TS8CYD41E31EJ0ES76HP=nota-1 set-up-appsflyer-integration-in-tiktok-ads=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-tiktok-ads h_01K8X2TS8CNQEQCB9SBVESBJ9H=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-tiktok-ads h_01K8X2TS8CZCGK55A71SVDRFXJ=1-set-the-campaign-type-objective-and-goals h_01K8X2TS8C8AFR6M3ME0SPP4QN=aten%C3%A7%C3%A3o h_01K8X2TS8CC4ZTST3Y5Q2RRVTC=2-set-destination-url landing-page-or-attribution-link=landing-page-ou-link-de-atribui%C3%A7%C3%A3o h_01K8X5E9VSFTD53NCA03KYT80P=landing-page-ou-link-de-atribui%C3%A7%C3%A3o pc-or-console-store=loja-de-pc-ou-console h_01K8X5XC69TDW2DNFWFYRN9TMF=loja-de-pc-ou-console h_01K8X2TS8DQ70RSFHBGM7ZHRYE=nota-2 create-a-landing-page-with-onelink-smart-script=criar-uma-landing-page-com-o-onelink-smart-script h_01K8X2TS8DZ62VHY2W7SCBSWEN=criar-uma-landing-page-com-o-onelink-smart-script h_01K8X2TS8D7X7YT9FBDPZPVAH3=endtoend-data-flow h_01K8X2TS8DJ54M3H11PTXVE2JF=set-up-a-smart-script-landing-page h_01K8X2TS8DFS70S7YNA89R6N95=nota-6 h_01K8X2TS8DZT5GG7BW41A3FA4B=nota-5 h_01K8X2TS8DMTGJNQX3B3VXAM0W=set-up-a-smart-script-crossplatform-landing-page h_01K8X2TS8DZEY18AMT5J14VW42=nota-5 create-a-landing-page-with-onelink-smart-banners=crie-uma-landing-page-com-os-smart-banners-do-onelink h_01K8X2TS8DAAN8JGJNJGJKD6PP=crie-uma-landing-page-com-os-smart-banners-do-onelink h_01K8X2TS8DC94419514NK8Y98S=endtoend-data-flow::e62b5c1b h_01K8X2TS8E5EHDFX6RW34TQN4A=set-up-a-smart-banners-landing-page h_01K8X2TS8EC16VZXC9JZJ9Y3VG=nota-6 TikTok-view=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-webtoapp-attribution-data-from-november-2-2025=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-da-api h_01K88J8JFN8W2572N92466YFZQ=ver-em-dados-brutos-e-relat%C3%B3rios-da-api h_01_measure-cost-clicks-impressions-tiktok-w2a=me%C3%A7a-custo-cliques-e-impress%C3%B5es measure-cost-clicks-impressions-tiktok-w2a=me%C3%A7a-custo-cliques-e-impress%C3%B5es h_01_tiktok_w2a_cost_note=aten%C3%A7%C3%A3o-1" />
