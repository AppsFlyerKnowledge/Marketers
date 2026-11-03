---
title: Configuração de campanha do Unity Ads
metadata:
  keywords:
    - Unity Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2026-09-10T00:25:55Z'
  id: 208005086
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/208005086
---
> **Visão geral:** Unity Ads, um parceiro integrado de ad network da AppsFlyer, é uma ad network de vídeo para iOS e Android. Além da atribuição mobile baseada em cliques, o Unity Ads oferece custo, receita publicitária e atribuição de visualização, que podem ser registrados na AppsFlyer.

Para configurar suas campanhas com Unity Ads, siga as etapas abaixo.

## Configurando o Unity Ads

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

### Ativar parceiros

Na primeira visita, você precisará habilitar o botão **Ativar parceiro** para configurar a integração. O botão deve permanecer ativado enquanto você trabalhar com o parceiro.  
Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

### Configurações gerais

**Enviando o ID do dispositivo (ID de publicidade) para o Unity**

Na parte superior da aba Integração, há uma observação informando que o Unity Ads requer o envio do ID do dispositivo para cada instalação. Isso é feito automaticamente, você não precisa fazer nada.

[![Unity_msc_new_2.png](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)

**ID do jogo Unity Ads**

Unity Ads requer conexão com a AppsFlyer por meio de um ID de jogo exclusivo. Se você não sabe qual é o seu, pode obtê-lo diretamente no Unity Ads ou encontrá-lo após fazer o upload do jogo, em **Aplicativos** > **Campanhas**, conforme mostrado na captura de tela abaixo.

[![](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)

A plataforma do Unity Ads mapeia um aplicativo para um único ID de jogo do Unity Ads, por nível de conta (anunciantes e agências terão diferentes IDs de jogo IDs para o mesmo aplicativo). Várias contas na plataforma do Unity Ads não podem executar o mesmo aplicativo com diferentes IDs de jogo.

**Habilitar a atribuição de exibição (view-through)**

Ative esta opção para atribuir instalações de exibição do Unity Ads. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

![Unity_ads_msc_new_3.png](https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png)

### Postbacks padrão

![Screen_Shot_2022-07-28_at_13.07.25.png](https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png)

Envie postbacks automáticos para o Unity Ads após as instalações e reengajamentos do usuário. Use esta seção para definir a fonte dos usuários que permitem o envio desses postbacks:

* **Somente este parceiro**: para eventos provenientes apenas de usuários atribuídos ao Unity Ads.
* Leia mais sobre como o Unity Ads define cliques e visualizações.

> 📘 **Observação**
>
> Como uma rede de todas as instalações, o Unity Ads prefere receber postbacks para todas as novas instalações do seu aplicativo de qualquer fonte e eles recomendam selecionar **Todas as fontes de mídia, incluindo orgânicas,** para enviar todos os postbacks de instalação para o Unity Ads.

### Configurações de eventos in-app

Mapeie eventos da AppsFlyer com o parceiro via postbacks. Se o envio de postback estiver ativado, isso inclui eventos in-app rejeitados (eventos bloqueados pelo Protect360 ou eventos considerados não compatíveis com as regras de validação de direcionamento).

[![](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)

#### Para configurar postbacks de evento in-app

1. Digite o **game\_id**. Certifique-se de que o game\_id esteja correto e seja o mesmo usado para a atribuição de instalação.
2. Ative **Postbacks de eventos in-app.**
3. Defina a **janela de postback do evento in-app**, se necessário (leia mais sobre<Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app"> configuração da janela de postback do evento in-app</Anchor>).
4. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista.
5. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.<br />**Dica** : não vê o evento que você está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados"> mapeamento de eventos personalizados.</Anchor></li></ul> |
| **mapeado para evento parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID do evento correspondente do parceiro.</li><li>**Caixa suspensa:** selecione o evento AppsFlyer predefinido mais adequado.</li><li>**Como está**: envie os eventos como estão, sem mapeamento de nomes.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro, bem como eventos orgânicos. De acordo com Unity Ads, esta opção é recomendada.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento). De acordo com Unity Ads, esta opção é recomendada.</li><li>**Valores sem receita**: enviar todos os parâmetros **excluindo** o valor da receita.</li></ul> |

> 🚧 **Importante!**
>
> Selecione o evento SDK/servidor para servidor correto e o identificador de evento do parceiro correspondente. Não duplique eventos (não passe os mesmos eventos sob diferentes nomes de evento SDK/servidor para servidor).

> 📘 **Observação**
>
> Você pode enviar <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de receita publicitária</Anchor> para o Unity ads para que eles possam otimizar campanhas usando dados de receita publicitária:
>
> * **Nome do evento:** af\_ad\_revenue
> * **Mapeado para:** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Gere e salve links de atribuição e envie-os ao parceiro para atribuir campanhas específicas, conjuntos de anúncios ou anúncios exclusivos, tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura de links de atribuição e parâmetros</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

**Observações:**

* Quando o público de um aplicativo Android inclui crianças, o Unity envia IDs de publicidade zerados.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba Cost (Custo)">

Custo por clique não é compatível. A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. 

**Observação**:

* Os dados de custo requerem uma assinatura do ROI360.
* Os dados de custo do Unity Ads podem ser recebidos apenas para downloads provenientes do Google Play ou da Apple App Store. Para Android, os dados de custo para lojas de aplicativos Android de terceiros não são compatíveis.
* O custo de agência não é compatível com custo por clique ou API. Os anunciantes podem enviar dados de custos da agência por meio <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">do Ad Spend Ingestion</Anchor>.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>. **Observação**: para integrações de custo com Unity, todos os apps que possuem a mesma chave de API devem conter o mesmo Org ID. Caso contrário, a extração de dados de custos será afetada. Certifique-se de selecionar o **ID principal da organização**.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Receita publicitária">

Essa seção é relevante somente se você estiver atuando como publisher, exibindo anúncios do parceiro aos usuários. Nesse caso, você certamente deseja mensurar o engajamento dos usuários adquiridos de várias fontes para encontrar as fontes mais lucrativas para você.

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instruções de integração</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Nesta aba, você pode selecionar as permissões para conceder o Unity Ads para executar determinadas ações. Observe que, mesmo que a atribuição esteja desativada para o Unity Ads, a aba de permissões está ativa e você pode conceder permissões de Unity Ads.  
Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">as permissões que você pode conceder</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=configurando-o-unity-ads h_01HAPVZ510GTJRY1NXE0T3SMR6=configurando-o-unity-ads h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=ativar-parceiros h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HAPVZ510EZ3HKJQVPMKHV5FH=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HAPVZ511MRQXKPC78HR61X9P=postbacks-padr%C3%A3o h_01HAPVZ511CCXS93Y714STGQ67=observa%C3%A7%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HAPVZ511CJ6JP49HYG9T6RPF=configura%C3%A7%C3%B5es-de-eventos-in-app to-configure-inapp-event-postbacks=para-configurar-postbacks-de-evento-in-app h_01HAPVZ511RMEVNASSTJNXKCJG=para-configurar-postbacks-de-evento-in-app h_01HAPVZ511AV30DEKMZ0YB5ZBD=importante h_01HAPVZ511PC45Q5FEXQMZ4MFC=observa%C3%A7%C3%A3o-1 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
