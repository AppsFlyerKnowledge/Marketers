---
title: Integração do Meta Web para aplicativos de PC e console
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-09-16T00:28:54Z'
  id: 18704273772689
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/18704273772689
---
> **Visão geral:** Aprenda como integrar o Meta Web para PC e aplicativos de console, além de configurar campanhas no Meta Web.

> 🚧 **Importante!**
>
> Essa integração está disponível apenas para aplicativos de PC e console como Steam, Epic ou Native PC. Para aplicativos mobile, consulte a página <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup">de configuração de integração do Meta ads</Anchor>.

## Visão geral

Esse artigo contém informações relevantes e um passo-a-passo sobre como configurar e usar o Meta Web para PC e aplicativos de console. Isso inclui:

* [Ativação da integração do parceiro na AppsFlyer](#ativando-o-parceiro-na-appsflyer).
* [Configuração do Meta Web na AppsFlyer](#configuração-do-meta-web-na-appsflyer).
* [Configuração de campanhas na Meta para aplicativos de PC e console](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#configuração-de-campanhas-no-meta-web-para-aplicativos-de-pc-e-console).

### Pré-requisitos

Antes de ativar a integração do Meta Web, certifique-se de que você possui uma [conta comercial no Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

## Ativando o parceiro na AppsFlyer

**Para ativar a integração do parceiro:**

1. Na AppsFlyer, no menu lateral, vá para a aba **Collaborate** > **Partner Integrations > Marketplace** .
2. Pesquise por **Meta Web**.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração.
4. No separador **Integração**, ligue o **Ativar parceiro**.  
   **Nota: <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">O botão de alternância deve permanecer ativado (</Anchor><Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ligado</Anchor>) enquanto trabalhar com o parceiro.**
5. Conclua a configuração usando as abas relevantes, conforme descrito na próxima seção.

## Configuração do Meta Web na AppsFlyer

Nessa etapa da configuração, você também pode configurar postbacks para o Meta Web. A integração do Meta Web (metaweb\_int) usa a ferramenta Conversion API do Meta Ads para que os anunciantes enviem dados de seus **apps de PC e console** diretamente para os servidores do Meta. Esses dados podem incluir ações do usuário como compras, cadastros e outros tipos de conversões realizadas em plataformas fora do ecossistema mobile (sites ou aplicativos). Os dados são usados pelo Meta Ads para otimizar a segmentação de anúncios, mensurar a performance e construir audiências personalizadas para retargeting.

A integração com o Meta Web é compatível apenas com o envio de postbacks de instalações e eventos in-app.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

#### Ativar parceiro

Para configurar a integração, você deve primeiro habilitar o botão **Ativar parceiro**.

#### Configurações gerais

* **ID do pixel:** Insira o ID do pixel. Você pode encontrá-lo em seu Meta Ads Manager:
  1. No menu lateral do <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads manager</Anchor>, vá para **Todas as ferramentas** > **Gerenciador de eventos**.   
     **Atenção:** Certifique-se de selecionar a empresa certa no menu suspenso no canto superior direito.
  2. No menu lateral do **Gerenciador de eventos**, selecione **Fontes de dados**. Você verá uma lista dos seus pixels. Caso você não encontre um pixel para o negócio selecionado, você pode criá-lo.
  3. Copie o Pixel ID exibido abaixo do nome do pixel e cole-o no campo Pixel ID na janela de integração da AppsFlyer.  
     <Image alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **Token de acesso** Insira o token de acesso. Para recuperá-lo, siga [essas instruções](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
* **Limitar a utilização de informações pessoais dos usuários pelo Anúncios da Meta (CCPA):** Ative esta opção para permitir a compliance com as <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>.  
  **Observação:** O cumprimento dos regulamentos de privacidade da CCPA limita os dados provenientes de usuários do Anúncios da Meta com sede na Califórnia.

#### Ative a atribuição de view-through

A AppsFlyer oferece suporte para a atribuição de view-through através de campanhas Meta Web usando um modelo probabilístico (PMOD) e <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> ou uma landing page habilitada para <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>. Isso permite que a AppsFlyer atribua instalações de aplicativos que resultam de usuários que visualizaram um anúncio e depois instalaram o aplicativo, mesmo em diferentes plataformas, sem exigir um clique direto.

Quando um usuário clica em um anúncio do Meta Web e acessa uma landing page habilitada para <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>, a AppsFlyer pode atribuir a instalação do aplicativo mais adiante. Se disponível, `fbclid` será incluído no postback enviado para o Meta, para garantir a confiança na atribuição.

**Para ativar a atribuição de view-through:**

1. Na AppsFlyer, no menu lateral, abra **Integrações Ativas** > **anúncios de Meta web**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

#### Postbacks padrão

Postbacks de instalações são enviados automaticamente somente para o Meta Web. No campo **Para usuários de**, selecione uma das seguintes opções:

* **Somente este parceiro** para garantir que os postbacks de eventos in-app sejam enviados exclusivamente para eventos realizados por usuários que se originaram desse parceiro.
* **Todas as fontes de mídia, incluindo orgânicas,** garantem que os postbacks de eventos in-app sejam enviados para eventos realizados por usuários que vieram deste parceiro, outros parceiros ou de fontes orgânicas.

#### Postbacks de eventos in-app

Configure o mapeamento de postbacks de eventos in-app enviados para o Meta Web. Esses eventos podem ser visualizados no <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Meta Events Manager</Anchor>:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<ul><li>Clique em **adicionar item**, insira o nome do evento e clique em ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png).</li></ul> |
| **mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro.<ul><li>Selecione o evento predefinido mais adequado ou selecione PERSONALIZADO.</li></ul> |
| **para usuários de** | <ul><li>**Somente este parceiro** para garantir que os postbacks de eventos in-app sejam enviados exclusivamente para eventos realizados por usuários que se originaram desse parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas,** garantem que os postbacks de eventos in-app sejam enviados para eventos realizados por usuários que vieram deste parceiro, outros parceiros ou de fontes orgânicas.</li></ul> |
| **incluindo** | **Valores e receita:** Todos os parâmetros de eventos, incluindo o valor da receita (se existir), são enviados no postback. |

3. [Opcional] Clique no ícone **Adicionar condiçãoaltconditional-iae-postbacks-icon.pngalt para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.**
4. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
5. Clique em **Salvar integração.**
6. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

A opção de criar um link de atribuição na AppsFlyer não está disponível no momento. No entanto, você pode usar uma landing page multiplataforma com o SmartScript ou criar um link de atribuição direto (veja a tabela abaixo).

| Opção | Ações | Quem está envolvido |
| --- | --- | --- |
| Landing page multiplataforma | **Recomendado**: Quando sua campanha promove um app disponível em diversas plataformas, como na Epic e na Steam.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor><br /><br /><Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor><ul><li>Certifique-se de que todos os parâmetros de URL relevantes (que serão posteriormente capturados pelo Smart Script) sejam anexados ao URL do anúncio</li><li>Certifique-se de que o script pegue o FBCLID da URL recebida e o adicione ao link gerado. Ou seja, mapear o parâmetro do URL de saída do FBCLID `fbclid` para o parâmetro do URL de entrada `fbclid`. **Nota**! `fbclid`Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro de entrada `fbclid` também deve ser mapeado para um dos parâmetros de saída **.fbclid**</li><li>Opcional Use macros de URL dinâmicas do Meta em vez de codificar os valores manualmente. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Saiba mais</Anchor></li></ul> | Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) |
| Link de atribuição direta | Se você não usa uma landing page multiplataforma, pois você possui somente 1 app em 1 plataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor><ul><li>Certifique-se de que os parâmetros obrigatórios estejam incluídos em seu link:<ul><li>media\_source</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>Template usado para um link de anúncio no Meta Web:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />Exemplo de link de um link de anúncio do Meta Web que leva ao Steam: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**Observação:** O template inclui alguns parâmetros de URL dinâmico compatíveis com o Meta. Se preferir, você pode substituí-los manualmente por valores reais. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Saiba mais sobre os parâmetros de URL dinâmico do Meta</Anchor> | Marketer |

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Indisponível para Meta Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não está disponível para Meta Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Atualmente, as permissões não são concedidas ao Meta Web.

</Accordion>

## Configuração de campanhas no Meta Web para aplicativos de PC e console.

**Ao configurar sua nova campanha**:

* Selecione um objetivo. Recomendamos uma das opções abaixo:
  * **Vendas**: Isso permite que o Meta faça a otimização visando um evento específico (seu principal KPI).
  * **Tráfego**: Isso permite que o Meta faça a otimização visando cliques em anúncios. Essa opção só deve ser usada se você não possui outros KPIs, ou se o volume de outros eventos de KPI for muito baixo.
  * **Personalizado**: se você quiser definir um evento personalizado (como seu objetivo de campanha). **Atenção:** para que o evento personalizado apareça como um objetivo de campanha no dashboard do Meta, primeiro configure o evento personalizado na AppsFlyer.
* Selecione **website** como local de conversão.
* Ao nomear seu pixel de conversão do Facebook, insira o mesmo ID de pixel inserido para metaweb\_int no Partner Marketplace da AppsFlyer.
* Ao selecionar o URL do site como destino do seu anúncio, o URL deve ser:
  * Uma web landing page (recomendado quando o seu aplicativo está disponível em mais de uma plataforma)
  * Store URL (recomendado quando o seu aplicativo está disponível em uma única loja ou plataforma.

## Veja os dados de atribuição de web-to-app

Embora os eventos de conversão baseados na web sejam enviados para a Meta sob o PID original `metaweb_int`, eles são relatados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `Facebook Ads`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visão unificada permite que você analise a performance de campanhas na web e no app em um só local, incluindo relatórios completos de custos na web e no mobile.

### Ver no dashboard

Todas as atribuições de web-to-app do Meta aparecem sob `Facebook Ads` nos dashboards de Visão Geral e de Atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do app e da web dentro dos seus dados do Meta Ads.

### Ver em dados brutos e relatórios da API

* **Exportações de dados brutos e respostas da API** incluem o PID `Facebook Ads` no campo `media_source` para a atividade web do Meta. Para verificar os detalhes da configuração da campanha web, consulte o campo `original_url`, que mostra `metaweb_int` como o PID usado durante a criação de campanhas web.
* **Relatórios de postback** mostram `metaweb_int` como a fonte de mídia original para a qual o postback foi enviado.

## Características e limitações

| Caraterística | Descrição |
| --- | --- |
| Cliques e impressões (limitação temporária) | Cliques e impressões para campanhas direcionadas a aplicativos de PC e console estão temporariamente indisponíveis a partir da Meta SRN (`Facebook Ads`). |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=importante overview=vis%C3%A3o-geral h_01HK4QHRJG6WTN9P6ZG83XQ6AY=vis%C3%A3o-geral prerequisite=pr%C3%A9-requisitos h_01HFXV8HPGCRGYPEW0NPJ0NR0S=pr%C3%A9-requisitos activate-partner=ativando-o-parceiro-na-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=ativando-o-parceiro-na-appsflyer setting-up-metaweb-in-appsflyer=configura%C3%A7%C3%A3o-do-meta-web-na-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=configura%C3%A7%C3%A3o-do-meta-web-na-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=ativar-parceiro h_01HFXV8HPH6X92YETNAGZ910AV=ativar-parceiro transaction-id=configura%C3%A7%C3%B5es-gerais h_01HARQDVEDA206D0BBXBC6WEHH=configura%C3%A7%C3%B5es-gerais enable-viewthrough-attribution=ative-a-atribui%C3%A7%C3%A3o-de-view-through h_01ZXVWB1ZYKK4DP38QY1RMEY6M=ative-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-padr%C3%A3o inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=configura%C3%A7%C3%A3o-de-campanhas-no-meta-web-para-aplicativos-de-pc-e-console h_01HK4S03KVAN99YKXTHAKCT420=configura%C3%A7%C3%A3o-de-campanhas-no-meta-web-para-aplicativos-de-pc-e-console meta%20view=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-webtoapp-attribution-data-from-november-2-2025=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=veja-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-da-api h_01K88J8JFN8W2572N92466YFZQ=ver-em-dados-brutos-e-relat%C3%B3rios-da-api traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KB503RDVWPSFBAPAPW4CNZXM=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
