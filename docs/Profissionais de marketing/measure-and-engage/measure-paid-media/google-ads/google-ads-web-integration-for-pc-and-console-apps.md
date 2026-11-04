---
title: Integração web do Google Ads para aplicativos de PC e console
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-09-16T00:27:50Z'
  id: 21768823915665
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/21768823915665
---
> **Resumo:** use as campanhas do Google Ads na web para promover seus aplicativos em plataformas de PC e console e ativar sua atribuição. A AppsFlyer oferece suporte às campanhas do Google na web usando landing pages multiplataforma ou links de atribuição direta.

<div id="note" />

> 📘 **Nota**
>
> Este artigo foca em campanhas na web que promovem aplicativos para PC ou Console. Se você deseja criar campanhas na web que promovem aplicativos mobile, veja <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns">Google Ads (AdWords) - Criar campanhas baseadas na web</Anchor>.

<div id="overview" />

## Visão geral

Esse artigo contém informações relevantes e um passo-a-passo sobre como configurar e usar o Google Ads para aplicativos de PC e console. Isso inclui:

* [Ativação da integração do parceiro na AppsFlyer](/docs/google-ads-web-integration-for-pc-and-console-apps#ativar-parceiro-na-appsflyer).
* /docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer
* Configuração de campanhas no Google Ads para aplicativos de PC e console.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração com o Google Ads na web, verifique se você tem:

* Um aplicativo para PC ou console
* Uma conta da AppsFlyer
* Um token de acesso do Google com o <Anchor target="_blank" href="https://developers.google.com/identity/protocols/oauth2/scopes">escopo OAuth necessário</Anchor>. Você pode verificar os escopos associados ao seu token de acesso no Google Developer Console.
* <Anchor target="_blank" href="/marketers/pt/docs/user-management">Usuários de contas com as funções/permissões necessárias</Anchor> e acesso aos aplicativos relevantes na AppsFlyer

<div id="activate-partner-in-appsflyer" />

## Ativar parceiro na AppsFlyer

**Para ativar a integração do parceiro:**

1. Na AppsFlyer, no menu lateral, acesse a guia **Colaborar** > **Integrações de parceiros > Marketplace** .
2. Pesquise por **Google Ads Web** e selecione-o ou clique em **Integrar**.
3. Você será direcionado para a página de configuração.
4. Na aba **Integração** selecione **Ativar parceiro**.  
   **Atenção:** O toggle deve permanecer ligado (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor>) enquanto você trabalhar com o parceiro.
5. Conclua a configuração usando as abas relevantes, conforme descrito na próxima seção.

<div id="set-up-google-ads-web-in-appsflyer" />

## Configurando o Google Ads Web na AppsFlyer

Nessa etapa da configuração, você também pode configurar postbacks para o Google Ads. A integração do Google Ads Web (googleads\_int) usa uma ferramenta de API fornecida pelo Google Ads para que os anunciantes enviem dados de seus **aplicativos de PC e console** diretamente para os servidores do Google. Esses dados podem incluir ações do usuário como compras, cadastros e outros tipos de conversões realizadas em plataformas fora do ecossistema mobile (sites ou aplicativos). Os dados são usados pelo Google Ads para otimizar a segmentação de anúncios, mensurar a performance e construir audiências personalizadas para retargeting.

A integração com o Google Ads é compatível apenas com o envio de postbacks de instalações e eventos in-app.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

<div id="activate-partner" />

#### Ativar parceiro

Para configurar a integração, você deve primeiro habilitar o botão **Ativar parceiro** .

<div id="general-settings" />

#### Configurações gerais

<div id="note-1" />

> 📘 **Nota**
>
> A mensagem de erro de "token ausente" deixará de aparecer assim que você fizer o login com o Google e permitir que a AppsFlyer recupere o token na etapa abaixo. Se o erro persistir após o login, <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">verifique se o seu token tem as permissões necessárias.</Anchor>

1. **First open conversion ID**: Insira o ID da ação de conversão `First open` que você definiu no Google Ads. Para encontrar o ID:
   1. Vá para a plataforma Google Ads e abra a aba **Detalhes** da página de ação de conversão de **First open**.
   2. Copie o valor do parâmetro de consulta `ctid=*` da URL da página. Por exemplo, se `ctid=123456789`, insira `123456789` na caixa **First open conversion action ID**.
2. Insira seu **Customer ID**. Você pode encontrá-lo em seu Google Ads Manager:
   1. Faça login na sua conta do Google Ads.
   2. No canto superior direito, clique no ícone da conta do Google e role para baixo até encontrar o Customer ID.
   3. Se você tiver várias contas do Google Ads executando campanhas para seu aplicativo, será necessário usar o Customer ID de um gerente (MCC) para o rastreamento de conversões entre contas. Cole o **MCC ID** (e não o Customer ID de uma conta específica) nas caixas de texto **Customer ID** e **MCC Customer ID** (mesmo ID para ambas).   
      Se você usar apenas uma única conta do Google Ads para executar anúncios, basta colar o ID da conta na caixa de texto **Customer ID** e deixar a **MCC Customer ID** vazia. Veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Instruções do Google sobre como configurar uma conta MCC</Anchor>.
3. Para permitir que a AppsFlyer envie conversões para o Google Ads, clique em **Login com o Google**.
4. Selecione a conta de administrador da conta MCC da qual você recuperou o Customer ID na etapa anterior.
5. Clique em **Permitir**

<div id="enable-view-through-attribution" />

#### ative a atribuição de view-through

A AppsFlyer oferece suporte para a atribuição de view-through através de campanhas Google Web usando um <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#criar-uma-landing-page-com-o-onelink-smart-script">Smart Script</Anchor> ou uma landing page habilitada para <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#crie-uma-landing-page-com-os-smart-banners-do-onelink">Smart Banner</Anchor>. Isso permite a atribuição de instalação de aplicativos por modelagem probabilística (PMOD), que é acionada por impressões de anúncios, mesmo quando os usuários não clicam diretamente no anúncio.

Quando um usuário vê um anúncio do Google e acessa uma landing page habilitada para <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#criar-uma-landing-page-com-o-onelink-smart-script">Smart Script</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page">Smart Banner</Anchor>, a AppsFlyer pode atribuir a instalação resultante de volta à impressão original da web, com um acompanhamento cross-platform.

Quando disponível, a AppsFlyer inclui o `gclid` no postback para o Google.

**Para ativar a atribuição de view-through:**

1. Na AppsFlyer, no menu lateral, abra **Integrações Ativas** > **Google Ads Web**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Abra a aba **Atribuição**.
6. Vá até a seção **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar as alterações.

<div id="default-postbacks" />

#### Postbacks padrão

Postbacks de instalações são enviados automaticamente somente para o Google Ads para web.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configure o mapeamento de postbacks de eventos in-app enviados para o Google Ads para web. Esses eventos podem ser visualizados no Google Ads Manager:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<ul><li>Clique em **adicionar item**, insira o nome do evento e clique em ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png).</li></ul> |
| **mapeado para evento do parceiro** | O Conversion Action ID de cada evento, conforme definido do lado do parceiro.<ol><li><span class="af-ol-a"></span>Na página de **Metas de Conversão** do Google Ads, clique na ação de conversão que você criou.</li><li>Na página de **Detalhes** da Ação de Conversão, copie o **Conversion Action ID** do parâmetro `ctId=` da URL.</li><li>Volte para a AppsFlyer e cole esse dado. Por exemplo, se `ctid=123456789`, cole `123456789`.</li></ol> |
| **para usuários de** | **Somente esse parceiro:** Os postbacks de eventos in-app são enviados apenas para eventos atribuídos a esse parceiro, ou seja, o usuário que realizou esses eventos chegou ao seu app a partir desse parceiro em específico. |
| **incluindo** | **Valores e receita:** Todos os parâmetros de eventos, incluindo o valor da receita (se existir), são enviados no postback. |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir as condições</Anchor> para um evento.
4. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
5. Clique em **Salvar integração.**
6. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita os passos de integração para a aplicação selecionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

A opção de criar um link de atribuição na AppsFlyer não está disponível no momento. No entanto, você pode usar uma landing page multiplataforma com o SmartScript ou criar um link de atribuição direto (veja a tabela abaixo).

| Opção | Ações | Quem está envolvido |
| --- | --- | --- |
| Landing page multiplataforma | **Recomendado**: Quando sua campanha promove um app disponível em diversas plataformas, como na Epic e na Steam.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor><br /><br /><Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor><ul><li>Certifique-se de que todos os parâmetros de URL relevantes (que serão posteriormente capturados pelo Smart Script) sejam anexados à URL do anúncio</li><li>Certifique-se de que o script pegue o FBCLID da URL recebida e o adicione ao link gerado. Ou seja, mapeie o parâmetro da URL de saída do FBCLID `gclid` para o parâmetro da URL de entrada `gclid`. **Atenção**! Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro de entrada `gclid` também deve ser mapeado para um dos parâmetros de saída `af_sub[1-5]`.</li></ul> | Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) |
| Link de atribuição direta | Se você não usa uma landing page multiplataforma, pois você possui somente 1 app em 1 plataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor><ul><li>Certifique-se de que os parâmetros obrigatórios estejam incluídos em seu link:<ul><li>media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**Atenção:** O parâmetro <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">Google click identifier (GCLID)</Anchor> é adicionado automaticamente pelo Google Ads a um clique de saída se você estiver usando <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">auto-tagging</Anchor>. Se o auto-tagging estiver desativadi na sua conta do Google Ads, adicione `gclid={gclid}` à URL do tracking template do Google Ads.</li></ul></li><li>Para os parâmetros af\_camapign\_id, af\_adset\_id e af\_ad\_id, você pode usar as macros de [parâmetros de value track](https://support.google.com/google-ads/answer/6305348) (parâmetro de URL dinâmico) do Google. Todos os outros parâmetros devem ser configurados manualmente.</li><li>Não inclua o parâmetro af\_dp.</li></ul>**Modelo a ser usado na maioria das plataformas (Epic, Steam, Xbox, PlayStation, etc.)** :<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Exemplo de link que leva à Steam**: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Modelo para usar SOMENTE em aplicativos do Google PC e Mac**:<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Exemplo de link que leva ao Google PC**: `https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | Marketer |

<div id="tip" />

> 👍 **Dica**
>
> Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web)

</Accordion>

<div id="set-up-campaigns-in-google-ads-web-for-pc-and-console-apps" />

## Configuração de campanhas no Google ads Web para apps de PC e console

Ao configurar uma nova campanha, você pode direcionar os usuários para:

* Uma Landing page multiplataforma: Recomendado em casos em que a sua campanha promove um app disponível em diversas plataformas, como na Epic e na Steam.
* Uma única loja: um link de atribuição direta deve ser usado quando você tem apenas 1 aplicativo em 1 plataforma.

Leia as instruções para configurar campanhas para redirecionar os usuários para qualquer uma dessas opções nas seções a seguir.

**Atenção:** Durante a configuração da campanha, é possível que você queira configurar suas próprias ações e metas de conversão. As instruções sobre como fazer isso também estão detalhadas nas seções a seguir.

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="Campanhas que redirecionam para uma landing page multiplataforma">

**Para configurar uma campanha que redireciona os usuários para uma landing page multiplataforma**:

1. Configure a landing page conforme descrito na [seção de links de atribuição.](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)
2. Faça login no Google Ads e crie uma nova campanha.
3. Selecione um objetivo.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * Todos os objetivos são aplicáveis, exceto “Promoção de aplicativos” (que só pode ser usada para campanhas de apps mobile).
   * Recomendamos que você configure o objetivo da campanha de “Vendas” para otimização com base em eventos específicos no aplicativo.
4. Selecione as metas de conversão.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * Por padrão, as metas de campanha predefinidas são exibidas no nível da conta. Você pode manter essa configuração ou remover aquelas que não são relevantes para a sua campanha.
   * Se você não encontrar a meta desejada, [adicione a ação e a meta de conversão](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * Você também pode editar suas metas predefinidas na página de conversões.
5. Selecione o tipo de campanha.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * Todos os tipos de campanha são aplicáveis, exceto “Compras”, que exige um catálogo de produtos e se limita a domínios verificados.
6. Insira a URL da landing page como a URL final do Google.

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="Campanhas que redirecionam para uma única loja de aplicativos">

**Para configurar uma campanha que redireciona os usuários para uma única plataforma e loja de aplicativos**:

1. Configure um link de atribuição direta conforme descrito na seção [link de atribuição](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab).
2. Faça login no Google Ads e crie uma nova campanha.
3. Selecione um objetivo.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * Todos os objetivos são aplicáveis, exceto “Promoção de aplicativos” (que só pode ser usada para campanhas de apps mobile).
   * Recomendamos que você configure o objetivo da campanha de “Vendas” para otimização com base em eventos específicos no aplicativo.
4. Selecione as metas de conversão.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * Por padrão, as metas de campanha predefinidas são exibidas no nível da conta. Você pode manter essa configuração ou remover aquelas que não são relevantes para a sua campanha.
   * Se você não encontrar a meta desejada, [adicione a ação e a meta de conversão](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * Você também pode editar suas metas predefinidas na página de conversões.
5. Selecione o tipo de campanha.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * Todos os tipos de campanha são aplicáveis, exceto “Compras”, que exige um catálogo de produtos e se limita a domínios verificados.
6. Insira o link que será usado como URL final do Google.
   * Esse deve ser o destino final da web para o qual você deseja redirecionar seus usuários. Pode ser qualquer URL da web, incluindo uma landing page da web ou URL da loja. Por exemplo: `https://store.steampowered.com/app/{appid}/{myapp}/`.
   * A URL final não pode ser uma URL da AppsFlyer, pois isso pode fazer com que a sua campanha seja rejeitada. Use somente um endereço direto da web que não tenha redirecionamentos.
7. Insira seu link de atribuição direta da AppsFlyer como Tracking Template URL do Google.
   * Para que o rastreamento paralelo funcione conforme o esperado, a URL final deve ser colocada no parâmetro `{lpurl}` ValueTrack na Tracking Template URL do Google, conforme especificado.
   * Não inclua o parâmetro af\_dp.

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="Crie ações e metas de conversão">

No Google Ads, você pode selecionar ações e metas de conversão a partir da lista predefinida ou criar as suas próprias.

**Importante!** Para que a AppsFlyer envie um evento de "first open" de volta, você precisa criar uma ação de conversão e nomeá-la como "first open".

**Para criar suas próprias ações e metas de conversão**:

1. Na página de visão geral da sua conta do Google Ads, no menu lateral, selecione **metas** > **conversões** > **resumo**.
2. Clique em **+ Nova ação de conversão**.
3. Selecione **Conversões offline** como sua fonte de dados de ações de conversão.
4. Selecione **importar** na lista de tipos de conversão e, em seguida, selecione **importação manual usando API ou uploads** > **acompanhar conversões a partir de cliques**.

   <div id="note-2" />

   > 📘 **Nota**
   >
   > Se a **importação manual via API ou uploads** não estiver disponível:
   >
   > 1. <span class="af-ol-a"></span>Selecione **CRM, arquivos ou outras fontes de dados** > **rastrear conversões a partir de cliques**.
   > 2. Na **fonte de dados**, selecione **pular etapa e configurar a fonte de dados mais tarde**.

5. Clique em **continuar**.  
   Um formulário é exibido.
6. Preencha o formulário e clique em **criar e continuar** para concluir a criação do seu rastreador de conversões.
7. Para **otimização de metas e ações**, selecione uma categoria para mapear sua ação de conversão.  
   **Atenção:** a otimização de campanhas do Google Ads é feita por categoria, não por ação específica. Se você quiser que suas campanhas sejam otimizadas para uma única ação, mapeie somente essa ação para essa categoria. Por exemplo, se você quiser que sua campanha seja otimizada para a ação “instalar”, mapeie a ação “instalar” para a categoria desejada, por exemplo, “outros”. Em seguida, você poderá selecionar essa categoria como a meta da campanha.
8. Copie o conversion action ID do Google Ads e insira-o no campo **mapeado para o evento do parceiro.** O **conversion action ID** é usado como o partner event ID ao mapear o nome do evento do AppsFlyer para o partner event ID na configuração de postbacks de eventos in-app. Para copiar o conversion action ID do Google Ads:
   1. <span class="af-ol-a"></span>Na página de **metas de conversão** do Google Ads, clique na ação de conversão que você criou.
   2. Na página de **detalhes** da ação de conversão, copie o **conversion action ID** do parâmetro `ctId=` da URL e cole-o.
9. Clique em **criar e continuar**.
10. Clique em **terminar**.

</Accordion>

<div id="view-web-to-app-attribution-data-from-november-2-2025" />

## Ver dados de atribuição de web-to-app (a partir de 2 de novembro de 2025)

Embora os eventos de conversão baseados na web sejam enviados para o Google sob o PID original `googleads_int`, eles são registrados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `googleadwords_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visão unificada permite que você analise a performance de campanhas na web e no app em um só local, incluindo relatórios completos de custos na web e no mobile.

<div id="view-in-the-dashboard" />

### Ver no dashboard

Todas as atribuições de web-to-app do Google aparecem sob `googleadwords_int` nos dashboards de visão geral e de atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do app e da web dentro dos seus dados do Google Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver em dados brutos e relatórios de API

* **Exportações de dados brutos e respostas da API** incluem o PID `googleadwords_int` no campo `media_source` para a atividade web do Google. Para verificar os detalhes da configuração da campanha na web, consulte o campo `original_url`, que mostra `googleads_int` como o PID usado durante a criação de campanhas na web.
* **Relatórios de postback** mostram `googleads_int` como a fonte de mídia original para a qual o postback foi enviado.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Descrição |
| --- | --- |
| Cliques e impressões (limitação temporária) | Cliques e impressões para campanhas direcionadas a aplicativos de PC e console estão temporariamente indisponíveis via Google SRN (`googleadwords_int`). |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=nota overview=vis%C3%A3o-geral h_01HK4QHRJG6WTN9P6ZG83XQ6AY=vis%C3%A3o-geral prerequisites=pr%C3%A9-requisitos h_01HFXV8HPGCRGYPEW0NPJ0NR0S=pr%C3%A9-requisitos activate-partner=ativar-parceiro-na-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=ativar-parceiro-na-appsflyer setting-up-metaweb-in-appsflyer=configurando-o-google-ads-web-na-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=configurando-o-google-ads-web-na-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=ativar-parceiro h_01HFXV8HPH6X92YETNAGZ910AV=ativar-parceiro transaction-id=configura%C3%A7%C3%B5es-gerais h_01HARQDVEDA206D0BBXBC6WEHH=configura%C3%A7%C3%B5es-gerais h_01JK8XJJWQK5MEJF7GTC5C1707=nota-1 enable-viewthrough-attribution=ative-a-atribui%C3%A7%C3%A3o-de-view-through h_01ZXVWB0GZKWB53KTBWJ51RMBM=ative-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-padr%C3%A3o inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=dica setting-up-campaigns-in-meta-web-for-pc-and-console-apps=configura%C3%A7%C3%A3o-de-campanhas-no-google-ads-web-para-apps-de-pc-e-console h_01HK4S03KVAN99YKXTHAKCT420=configura%C3%A7%C3%A3o-de-campanhas-no-google-ads-web-para-apps-de-pc-e-console h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=nota-2 google%20view-web-to-app=ver-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app-a-partir-de-2-de-novembro-de-2025 view-webtoapp-attribution-data-from-november-2-2025=ver-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app-a-partir-de-2-de-novembro-de-2025 h_01K88H6ETM23EV0PTR8GS13KRN=ver-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app-a-partir-de-2-de-novembro-de-2025 view-in-the-dashboard=ver-no-dashboard h_01K88H6ETMG7007CJ0ADD8VQH4=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-de-api h_01K88H6ETM502Z2XDC63602FGD=ver-em-dados-brutos-e-relat%C3%B3rios-de-api traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KB5085FX7G6Y5E200KVH0ABJ=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
