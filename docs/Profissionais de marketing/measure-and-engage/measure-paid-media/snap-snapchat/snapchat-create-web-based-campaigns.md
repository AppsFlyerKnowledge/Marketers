---
title: Crie campanhas baseadas na web para Snapchat
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
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-09-16T00:30:21Z'
  id: 41365000854161
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/41365000854161
---
> **Resumo:** Use campanhas web do Snapchat Ads para atribuir conversões web-to-app a partir do Snapchat Ads

<div id="overview" />

## Visão geral

A AppsFlyer é compatível com a integração com o Snapchat Ads (`snapweb_int`) para campanhas baseadas na web, permitindo que você reporte dados de atribuição e conversão diretamente por meio da Events API do Snapchat. Os dados são então usados pelo Snapchat Ads para otimizar a segmentação de anúncios, mensurar a performance e criar audiências personalizadas.

<div id="important" />

> 🚧 **Importante!**
>
> Atualmente, a integração com o Snapchat Web não aceita o envio de postbacks de reengajamento para a API.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração do Snapchat Web, verifique se você possui uma conta comercial.

<div id="how-to-create-a-snapchat-ads-web-campaign" />

### Como criar uma campanha web do Snapchat Ads

Este artigo contém informações relevantes e um passo a passo sobre como configurar uma campanha web no Snapchat Ads para apps mobile com a AppsFlyer. Assim, vamos explicar como configurar a integração entre Snapchat Ads e AppsFlyer, como definir a configuração da campanha em ambas as plataformas e como criar landing pages com o Smart Script ou Smart Banners do OneLink.

O processo de configuração inclui as seguintes etapas obrigatórias:

* [Configurar a integração web do Snapchat Ads na AppsFlyer](#configurar-a-integração-web-do-snapchat-ads-na-appsflyer) (obrigatória)
* [Configurar a integração da AppsFlyer no Snapchat Ads](#configurar-a-integração-da-appsflyer-no-snapchat-ads) (obrigatória)

E as seguintes etapas opcionais:

* [Criar uma landing page com o OneLink Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) (opcional)
* [Criar uma landing page com OneLink Smart Banners](#crie-uma-landing-page-com-os-smart-banners-do-onelink) (opcional)

<div id="set-up-snapchat-ads-web-integration-in-appsflyer" />

## Configurar a integração web do Snapchat Ads na AppsFlyer

Comece ativando a integração web do Snapchat Ads. Em seguida, configure os postbacks que a AppsFlyer envia para a Events API.

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1. Ative a integração web do Snapchat Ads">

Para ativar a integração web do Snapchat Ads:

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações com parceiros** > **Marketplace de parceiros**.
2. Pesquise **Snapchat Web** e selecione-o.
3. Clique em **Configurar a integração**. Você será direcionado para a página de configuração de **Integrações ativas**.
4. Na aba **Integração** selecione **Ativar parceiro**. O botão deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor> enquanto você trabalhar com o parceiro.
5. Desative a **Privacidade Avançada** (se estiver configurando uma integração de aplicativo iOS).
6. **Compartilhamento de dados de correspondência avançada:** Ative para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, com o Snapchat, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.
7. **ID do pixel:** Insira o ID do pixel. Você pode gerá-lo ou recuperá-lo do seu Snapchat Ads Manager seguindo as instruções detalhadas na [documentação oficial do Snapchat Ads](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
8. **Token de acesso:** Insira o token de acesso. Para gerá-lo ou recuperá-lo, siga as [instruções na documentação oficial do Snapchat Ads](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Ative a atribuição de view-through">

A AppsFlyer oferece suporte para a atribuição de view-through através de campanhas web do Snapchat usando uma landing page habilitada para [Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [Smart Banners](#set-up-smart-banners-landing-page). Isso permite a atribuição de instalação de aplicativos por modelagem probabilística (PMOD), que é acionada por impressões de anúncios, mesmo quando os usuários não clicam diretamente no anúncio.

Se disponível, `ScCid` será incluído no postback enviado para o Snapchat, para garantir a confiança na atribuição.

**Para ativar a atribuição de view-through do Snapchat Web:**

1. Na AppsFlyer, no menu lateral, abra **Integrações ativas** > **Snapchat Ads Web**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[Opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba do **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Configure os postbacks de eventos in-app">

Atualmente, as instalações são os únicos eventos que acionam postbacks padrão automáticos para o Snapchat Ads. Para todos os outros tipos de eventos, você pode criar postbacks personalizados ao mapear eventos da AppsFlyer para eventos do Snapchat Ads. Esses postbacks podem ser visualizados no Snapchat Ads Manager.

Para definir os postbacks de eventos in-app, faça o seguinte:

1. Ative os **postbacks de eventos in-app**.
2. Se necessário, defina a janela de postback de eventos in-app (leia mais sobre a configuração da janela de postback de eventos in-app em geral neste <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">artigo</Anchor>).
3. Clique em **Adicionar evento** para adicionar um evento à lista.
4. Na coluna **Eventos da AppsFlyer**, selecione o nome do evento da lista. A AppsFlyer recebe o nome do evento do SDK integrado no aplicativo ou de eventos de server-to-server.
5. Na coluna **Mapeado para eventos de parceiro,** selecione o evento de parceiro predefinido mais adequado na lista.
6. Na coluna **Para usuários de**, selecione **Somente este parceiro** para garantir que os postbacks de eventos in-app sejam enviados apenas para eventos realizados por usuários que se originaram desse parceiro.
7. Na coluna **including**, selecione se os eventos serão enviados com os valores de receita. See <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Dados a incluir nos postbacks</Anchor>.

   <div id="note" />

   > 📘 **Nota**
   >
   > * Se você estiver configurando um evento de compra, defina a coluna **including** para **Values and revenue**. Selecionar qualquer outra opção fará com que o postback falhe.
   > * Atualmente, você só pode configurar o evento de compra para incluir receita.

8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Salvar integração**.
10. [Opcional] Após salvar a integração, ainda na página de configuração, você pode integrar mais aplicativos com o parceiro:
    1. <span class="af-ol-a"></span>No canto superior esquerdo, selecione o nome do aplicativo para abrir a lista de apps.
    2. Selecione um aplicativo diferente na lista.
    3. Repita as etapas acima para o aplicativo selecionado.

</Accordion>

<div id="set-up-appsflyer-integration-in-snapchat-ads" />

## Configurar a integração da AppsFlyer no Snapchat Ads

Realize as próximas etapas no Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Defina o tipo, objetivo e metas da campanha.">

Você pode escolher qualquer evento in-app predefinido da AppsFlyer como sua meta de campanha ou escolher "PAGE\_VIEW" se quiser otimizar para instalações de aplicativos mobile.

<div id="warning" />

> ❗️ **Aviso**
>
> Certifique-se de não escolher **Eventos de aplicativos,** pois o Snapchat reivindicará essas conversões usando a SRN API, o que pode causar desalinhamentos nos relatórios e na otimização.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Defina a URL de destino">

1. Em **Destino**, na **URL do site**, insira a URL que serve como destino para seu anúncio. A URL deve ser para:
   * **Uma landing page na web:** O uso é recomendado quando:

     * Você tem um aplicativo em várias plataformas.
     * Você deseja usar a landing page para fornecer mais informações sobre o produto anunciado.
     * Você quer usar a landing page para coletar mais dados.

     Para todos esses casos de uso, crie uma [landing page com um Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [um Smart Banner](#crie-uma-landing-page-com-os-smart-banners-do-onelink).
   * **Links de atribuição da AppsFlyer:** O uso de links de atribuição da AppsFlyer (OneLink, plataforma única ou multiplataforma) é recomendado quando você deseja que os usuários sejam redirecionados diretamente para a loja para baixar o aplicativo sem antes visitar uma landing page.
2. Clique em **Criar um parâmetro de URL** para adicionar os parâmetros de URL à URL (seja uma URL de landing page ou um link de atribuição da AppsFlyer).
3. Em **Parâmetros personalizados**, clique em **Adicionar parâmetro**.

   [<Image alt="Screenshot 2025-11-26 at 8.56.29.png" src="https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png" width="2810px" />](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. Mapeie os parâmetros da AppsFlyer de acordo com os valores do Snapchat.
   * Se a URL de destino for **uma landing page, um link de atribuição do OneLink ou um link de atribuição de plataforma única**, mapeie os seguintes parâmetros da AppsFlyer para os equivalentes no Snapchat:

| Parâmetro AF | Valor mapeado do Snapchat |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#c">`C`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_canal`</Anchor> | `{{site_source_name}}` |

     Um exemplo da URL resultante deve ser:

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * Se o APK do seu aplicativo NÃO estiver hospedado na Google Play Store, adicione o parâmetro <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> e mapeie-o para a URL da loja. Exemplo: `https://Add-your-store-url.com`.

* Se a URL de destino for um **PC ou uma loja de console**, crie o link seguindo as instruções na tabela abaixo. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Links de atribuição direta das plataforma de CTV, PC e console</Anchor>

| Estrutura do link de atribuição |  |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parâmetros de caminho obrigatórios | ▪ Exemplo de platform: steam  <br />▪ Exemplo de app\_id: 123456 |
| Parâmetros de consulta obrigatórios | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| Outros parâmetros | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links#parâmetros">Ver todos os parâmetros</Anchor> |
| Estrutura da URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  Mapeie os seguintes parâmetros da AppsFlyer para os equivalentes no Snapchat:

| Parâmetro AF | Valor mapeado do Snapchat |
| --- | --- |
| `media_source` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_canal`</Anchor> | `{{site_source_name}}` |

  * Para simplificar a análise da campanha, inclua o tipo de campanha, (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web).

  Um exemplo de URL multiplataforma:

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  <div id="note-1" />

  > 📘 **Nota**
  >
  > O Snapchat adiciona automaticamente `ScCid={{ScCid}}` à URL de destino quando o anúncio é clicado.


  > 📄
  >
  > Para um guia abrangente sobre os parâmetros do link da AppsFlyer, consulte os <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-do-link-de-atribuição">parâmetros do link de atribuição</Anchor>.


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## Criar uma landing page com o OneLink Smart Script

**Jornada do usuário:** O usuário clica em um anúncio do Snapchat e é direcionado para seu site mobile. Ele acessa uma página com botões CTA que o incentivam a baixar o aplicativo de uma ou mais plataformas. Ao clicar em um botão, o usuário é direcionado para a loja de aplicativos.

<div id="endtoend-data-flow" />

<Accordion title="Fluxo de dados de ponta a ponta">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. A URL do anúncio do Snapchat inclui o parâmetro `pid=snapweb_int`. Quando o usuário clica no anúncio, um parâmetro `ScCid` é automaticamente anexado à URL.
2. O usuário é redirecionado para o destino da URL: uma landing page que contém um Smart Script.
3. Quando a landing page é carregada, o Smart Banner envia uma impressão para a AppsFlyer contendo os parâmetros da URL de entrada. A impressão permitirá a atribuição de view-through na landing page da web. Para saber mais sobre impressões e atribuição de view-through, leia <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">este artigo</Anchor>.
4. O Smart Script gera as URLs de saída para os botões CTA na página com base nos parâmetros da URL de entrada, incluindo parâmetro `ScCid`. Os botões podem levar a:
   * Google Play e App Store por meio de um link de atribuição do OneLink.
   * Lojas de várias plataformas (exemplo: CTV, Epic e Steam). Nesse caso, o Smart Script gera um único link de atribuição para cada plataforma, levando à loja especificada.
   * Download de um arquivo APK para o dispositivo do usuário.
5. Quando o usuário clica no botão CTA, o clique é acionado e registrado na AppsFlyer.
6. Em seguida, ele é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um [install referrer](https://www.appsflyer.com/glossary/install-referrer/) estiver disponível.
9. Um postback com os parâmetros de `ScCid` e outros parâmetros do evento é gerado e enviado ao Snapchat por meio da Events API. O Google usa o parâmetro `ScCid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Configurar uma landing page de Smart Script">

Para configurar suas campanhas do Snapchat Ads, siga estas etapas:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
2. Crie um Smart Script. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">como criar um Smart Script do OneLink</Anchor>.

   <div id="note-2" />

   > 📘 **Nota**
   >
   > As instruções abaixo descrevem as etapas específicas necessárias para configurar uma campanha do Snapchat Ads com o Smart Script. Para um guia abrangente sobre como configurar campanhas de Smart Script, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Como criar um OneLink Smart Script</Anchor> no artigo de configuração do <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2</Anchor>.

3. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o Snapchat Ads Manager e verifique os parâmetros de URL definidos durante a criação da URL de destino. Para obter mais informações, veja como [definir uma URL de destino](#2-set-destination-url).
4. Mapeie os parâmetros de URL de entrada necessários para a campanha do Snapchat Ads para os parâmetros de URL de saída. Esses parâmetros são enviados para a AppsFlyer quando o usuário clica no botão CTA:
   * **PID**: Certifique-se de que o Smart Script pegue o valor do parâmetro `pid=snapweb_int` da URL de entrada e o mapeie para os parâmetros correspondentes na URL de saída.
   * **ScCid**: O parâmetro `ScCid` é necessário para enviar com sucesso postbacks de eventos in-app para o Snapchat. O parâmetro `ScCid` deve ser mapeado manualmente na seção de **mapeamento de parâmetros de URL** da página do **Smart Script**:

     1. Em **Mapeamento para**, selecione **Parâmetro personalizado**.
     2. Em **Parâmetro de URL de saída** e **Parâmetros de URL de entrada,** insira **ScCid**.

     > 📘 **Nota**
     >
     > Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro `ScCid` de entrada também deve ser mapeado (além do parâmetro `ScCid` de saída) para um dos parâmetros de saída `af_sub[1–5]`.


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Configurar uma landing page multiplataforma do Smart Script">

Para configurar suas campanhas do Snapchat Ads com o Smart Script para landing pages multiplataforma, siga estas etapas:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
   * Habilite seu template do OneLink para atribuição multiplataforma. Para mais informações, veja como <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#crie-ou-edite-um-template-do-onelink-para-atribuição-cross-platform">criar ou editar um template do OneLink para atribuição multiplataforma</Anchor>.
2. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o Snapchat Ads Manager e analise os parâmetros de URL definidos durante a criação da URL de destino. Para obter mais informações, veja como [definir uma URL de destino](#2-set-destination-url).
3. Para cada parâmetro de entrada, decida o parâmetro de saída para onde ele será mapeado. Por exemplo, o parâmetro `af_site_id` na URL de entrada será mapeado para o parâmetro de `af_site_id` na URL de saída.
4. Decida o valor padrão para os parâmetros de saída obrigatórios que não podem estar vazios.
5. Envie ao seu desenvolvedor as seguintes informações:
   * Seu mapeamento de parâmetros de entrada e saída. O desenvolvedor criará um script que gera uma URL direta de saída com base no mapeamento de parâmetros de entrada e saída.
   * Os valores padrão dos parâmetros. O script preencherá os parâmetros de URL de saída com os valores padrão sempre que não houver valores de parâmetros de URL de entrada correspondentes.
   * Se você estiver usando um link de atribuição do OneLink, envie o ID do domínio e do template para seu desenvolvedor. O desenvolvedor usa isso para criar a URL de saída do OneLink. Exemplos: `yourbrand.onelink.me/A1b2` ou `click.yourbrand.com/A1b2`
   * Envie ao seu desenvolvedor os seguintes links do Dev Hub:
     * [Exemplos de instruções e códigos](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre como criar URLs de saída para plataformas não mobile.
     * [Uma demonstração e instruções](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) sobre como criar uma landing page multiplataforma.

* Lembre seu desenvolvedor de incluir o parâmetro de entrada `ScCid` na URL de saída.

  <div id="note-4" />

  <div id="note-3" />

  > 📘 **Nota**
  >
  > Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro `ScCid` de entrada também deve ser mapeado (além do parâmetro `ScCid` de saída) para um dos parâmetros `af_sub[1-5]` de saída.


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Crie uma landing page com os Smart Banners do OneLink

**Jornada do usuário:** O usuário clica em um anúncio do Snapchat e é direcionado para seu site mobile. Ele acessa uma página onde há um Smart Banner com um botão CTA para baixar o app na loja de aplicativos.

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="Fluxo de dados de ponta a ponta">

1. A URL do anúncio do Snapchat inclui o parâmetro `pid=snapweb_int`. Quando o usuário clica no anúncio, um parâmetro `ScCid` é automaticamente anexado à URL.
2. O usuário é redirecionado para o destino da URL: uma landing page que contém um Smart Banner.
3. Quando a landing page é carregada, o Smart Banner envia uma <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impressão</Anchor> para a AppsFlyer contendo os parâmetros da URL de entrada. Essa impressão permite a atribuição de view-through para a landing page. Para saber mais sobre impressões e atribuição de view-through, veja como <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">criar uma URL de impressão personalizada</Anchor>.
4. O Smart Banner gera a URL de saída para o botão CTA no banner. A URL de saída é baseada nos parâmetros da URL de entrada, incluindo o parâmetro `ScCid`. O Smart Banner pode gerar somente links baseados no OneLink.
5. Quando o usuário clica no botão CTA do Smart Banner, o clique é acionado e registrado na AppsFlyer.
6. Em seguida, ele é redirecionado para a loja e baixa o aplicativo.
7. Quando o usuário abre o aplicativo, o evento de instalação é registrado na AppsFlyer.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um install referrer estiver disponível.
9. Um postback com os parâmetros de `ScCid` e outros parâmetros do evento é gerado e enviado ao Snapchat por meio da Events API. O Google usa o parâmetro `ScCid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Configurar uma landing page do Smart Banner">

Para configurar suas campanhas de Smart Banners do Snapchat Ads, siga estas etapas:

1. Configure o template para os links de atribuição do OneLink da campanha. Para obter mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar templates do OneLink</Anchor>.
2. Crie um Smart Banner.

   <div id="note-5" />

   > 📘 **Nota**
   >
   > As instruções abaixo descrevem as etapas específicas necessárias para configurar uma campanha do Snapchat Ads com Smart Banners. Para obter um guia abrangente sobre como configurar campanhas de Smart Banners, consulte a <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#configuração">seção de configuração</Anchor> do artigo <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners — web-to-app mobile (para profissionais de marketing)</Anchor>.

3. Defina os parâmetros do Smart Banner para campanhas do Snapchat Ads:

   * Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada.
   * Para revisar os parâmetros anexados à URL de entrada, abra o Snapchat Ads Manager e analise os parâmetros de URL definidos durante a [criação da URL de destino](#2-set-destination-url).

   <div id="note-6" />

   > 📘 **Nota**
   >
   > Mais importante ainda, `pid=snapweb_int` e `ScCid` estão disponíveis na URL de entrada para permitir que o Smart Banner os colete. Esses dois parâmetros são necessários para atribuição e envio de postbacks para o Snapchat Ads.


</Accordion>

<div id="view-web-to-app-attribution-data" />

## **Ver os dados de atribuição de web-to-app**

Embora os eventos de conversão baseados na web sejam enviados para o Snapchat sob o PID original `snapweb_int`, eles são relatados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `snapchat_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visualização unificada permite que você analise a performance das campanhas na web e no app em um só local, incluindo relatórios completos de custos na web e no mobile.

<div id="view-in-the-dashboard" />

### **Ver no dashboard**

Todas as atribuições de web-to-app do Snapchat aparecem sob `snapchat_int` nos dashboards de Visão Geral e de Atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do app e da web dentro dos seus dados do Snapchat Ads.

<div id="view-in-raw-data-and-api-reports" />

### **Ver em dados brutos e relatórios de API**

* **Exportações de dados brutos e respostas de API** incluem o PID `snapchat_int` no campo `media_source` para a atividade web do Google. Para verificar os detalhes da configuração da campanha web, consulte o campo `original_url`, que mostra `snapchat_int` como o PID usado durante a criação de campanhas web.
* **Relatórios de postback** mostram `snapweb_int` como a fonte de mídia original para onde o postback foi enviado.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Dados de custo | Os dados de custo para campanhas baseadas na web do Snapchat Ads (`snapweb_int`) não são recuperados automaticamente. Em vez disso, eles devem ser importados manualmente usando um dos <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data#procedimentos">dois métodos disponíveis: upload de arquivo via e-mail ou upload manual via interface da AppsFlyersnapweb\_int. Isso se aplica a todos os usuários, incluindo assinantes do ROI360.</Anchor> |
| Cliques e impressões (limitação temporária) | Cliques e impressões para campanhas web estão temporariamente indisponíveis na SRN do Snapchat (`snapchat_int`). |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KB2W28THC55F0AJ0KZJPQ6S5=vis%C3%A3o-geral h_01KB2W28THSST3148Y5Y07PJ7S=importante prerequisites=pr%C3%A9-requisitos h_01KB2W28THW7E6TRVTTHJZ9BP4=pr%C3%A9-requisitos how-to-create-a-snapchat-ads-web-campaign=como-criar-uma-campanha-web-do-snapchat-ads h_01KB2W28THTST7HWTJA9TTGPGG=como-criar-uma-campanha-web-do-snapchat-ads set-up-snapchat-ads-web-integration-in-appsflyer=configurar-a-integra%C3%A7%C3%A3o-web-do-snapchat-ads-na-appsflyer h_01KB2W28THQJF8K4AWTRXNA3RX=configurar-a-integra%C3%A7%C3%A3o-web-do-snapchat-ads-na-appsflyer h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=nota set-up-appsflyer-integration-in-snapchat-ads=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-snapchat-ads h_01KB2W28TJVZ1BX94SZYH1K5EM=configurar-a-integra%C3%A7%C3%A3o-da-appsflyer-no-snapchat-ads h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=aviso h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=nota-1 create-a-landing-page-with-onelink-smart-script=criar-uma-landing-page-com-o-onelink-smart-script h_01KB2W28TJQA1TBXXQ7MA1F0CB=criar-uma-landing-page-com-o-onelink-smart-script h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=nota-5 h_01KB2W28TJZMQEDSNVWRZCNXYD=nota-4 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=nota-4 create-a-landing-page-with-onelink-smart-banners=crie-uma-landing-page-com-os-smart-banners-do-onelink h_01KB2W28TJM0X7K5Z7M2120MT9=crie-uma-landing-page-com-os-smart-banners-do-onelink h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=nota-5 h_01KB2W28TKRH3NC73J2JHNSMWD=nota-6 view-webtoapp-attribution-data=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01KB2W28TKDAV34JGYJKF2VT43=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01KB2W28TKNWYXJX189EP2HPN2=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-de-api h_01KB2W28TKJ1MAMM00KY3M3S2W=ver-em-dados-brutos-e-relat%C3%B3rios-de-api traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KB2W28TKFY74YBXHD91QP9V0=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
