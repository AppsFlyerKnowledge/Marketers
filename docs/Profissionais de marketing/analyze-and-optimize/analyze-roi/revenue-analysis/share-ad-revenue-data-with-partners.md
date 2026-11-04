---
title: Compartilhar dados de receita de anúncios com parceiros
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-09-16T00:02:06Z'
  id: 24100803679761
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Permita que os parceiros recebam informações de receita de anúncios de redes de mediação para que possam otimizar as campanhas de aquisição de usuários (UA). **Atenção:** É necessário ter uma assinatura ROI360 Advanced.

<div id="about-sharing-ad-revenue-data-with-partners" />

## Compartilhamento de dados de receita de anúncios com parceiros

Permita que suas ad networks responsáveis pela aquisição de usuários recebam dados de receita de anúncios de redes de mediação. Com isso, elas podem usar as informações para otimizar campanhas de UA.

Parceiros podem receber dados de receita de anúncios através de:

* [Sinais de UA para ad networks](#sinais-de-ua-para-ad-networks)
* [Postbacks de eventos de receita de anúncios enviados para ad networks](#postbacks-de-eventos-de-receita-de-anuncios-para-ad-networks)

A tabela a seguir compara as 2 soluções de compartilhamento de dados de receita de anúncios. 

| Solução de compartilhamento de dados de receita de anúncios | Atualização dos dados | Caso de uso | Tipo de integração necessária | Tipo de assinatura necessária |
| --- | --- | --- | --- | --- |
| Sinais de aquisição de usuários | Diária | Dados precisos e completos, normalmente usados para otimização D3 e D7. | <ul><li>Impression-level ou device-level</li><li>Se ambos estiverem configurados, os dados device-level são enviados.</li></ul> | ROI360 Advanced |
| Postbacks | Em tempo real | Dados recentes, normalmente usados para otimização D0 e D1. | Impression-level | ROI360 Advanced |

<div id="procedures" />

## Procedimentos

<div id="ua-signals-for-ad-networks" />

<Accordion title="Sinais de UA para ad networks">

Pode ser que você queira trabalhar com ad networks que recebem sinais de UA. Isso significa que as ad networks responsáveis pela aquisição de usuários podem receber dados de receita de anúncios das redes de mediação e usá-los para otimizar as campanhas de UA de seus clientes.

**Para enviar sinais de UA**:

1. No AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
2. Selecione o parceiro integrado.
3. Acesse a aba de **integração**.
4. Verifique se a opção **Ativar parceiro** está habilitada. Caso contrário, os dados não serão compartilhados.
5. Acesse a aba de **permissões**.
6. Ative as **permissões da ad network**.
7. Ative **Acessar dados brutos de receita de anúncios (sinais de UA)**.
8. Na **opção de envio**, selecione se deseja enviar dados de receita de anúncios apenas deste parceiro (**Somente este parceiro**) ou dados de receita de anúncios de todos os canais de mídia (**Todos os canais de mídia, incluindo orgânico**). **Observação**: Quando **Todos os canais de mídia, incluindo orgânico** está selecionado, os dados de outros parceiros não incluem dados de atribuição.
9. Clique em **Salvar configurações**.
10. Entre em contato com a ad network:
    1. Notifique-a de que você concedeu essas permissões.
    2. Avise-a que ela deve seguir <Anchor target="_blank" href="/partners/pt/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">as instruções necessárias</Anchor> para receber o relatório.

**Lista de parceiros de mediação que podem enviar sinais de UA para ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay mediation (antiga ironSource)
* Admost
* Tradplusad
* Yandex
* Mediação personalizada

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Postbacks de eventos de receita de anúncios para ad networks">

Você pode configurar os postbacks de receita de anúncios para ad networks. Isso significa que as ad networks responsáveis pela aquisição de usuários podem receber dados de receita de anúncios em tempo real das redes de mediação e utilizá-los para otimizar as campanhas de UA de seus clientes. 

<div id="important" />

> 🚧 **Importante!**
>
> * Os postbacks de eventos de receita de anúncios para ad networks só funcionam com os tipos de integração de receita de anúncios Impression-level via SDK e Impression-level (via SDK) com receita de anúncios device-level (via API server-to-server (S2S)) <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipos de integração</Anchor>. Isso significa que seu desenvolvedor deve integrar a <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-roi360-ad-revenue-sdk-api">ad revenue SDK API</Anchor> da AppsFlyer.
> * Embora você possa enviar postbacks de receita de anúncios para parceiros específicos, recomendamos validar como os parceiros usam os dados antes de iniciar a integração.

**Para configurar postbacks de eventos de receita de anúncios**:

1. Pesquise e selecione seu parceiro, seja <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#manage-existing-integrations">no marketplace</Anchor> ou na **Colaborar** > **Integrações de parceiros** > **Integrações** **ativas** página.
2. Na aba **Integração**, ative **Postbacks de eventos in-app**.
3. Selecione o evento af\_ad\_revenue da AppsFlyer. **Atenção:** Algumas integrações permitem que você **selecione todos os eventos**. Recomendamos que você não use essa opção, pois ela exclui os eventos af\_ad\_revenue.
4. Faça o mapeamento para o evento da ad network da seguinte forma:

| Rede de anúncios | Evento para mapear af\_ad\_revenue para | Captura de tela |
| --- | --- | --- |
| Google Ads | ad\_impression | <Image alt="Mapeamento do evento ad_impression do Google Ads" src="https://files.readme.io/883dd04563027d722e7e8e76a50f813c8a955db827cbb92e94cdc650ab7b234d-50421403523601.png" width="238px" /> |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | Nenhum mapeamento necessário |  |
| Mintegral | Nenhum mapeamento necessário |  |
| Smadex | Nenhum mapeamento necessário |  |
| Mistplay | Nenhum mapeamento necessário |  |
| Meta Ads | fb\_mobile\_purchase, para aplicativos iOS  <br />ou  <br />Adimpression, para aplicativos Android  <br /><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping#mapeamento-de-dados-de-receita-de-anúncios-para-otimização-de-campanhas">Guia de mapeamento de evento in-app do Meta Ads</Anchor>. | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok for Business - SRN avançada | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura from Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| SingleTap da Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | Nenhum mapeamento necessário |  |
| Bidease | Nenhum mapeamento necessário |  |
| MAF | Nenhum mapeamento necessário |  |

5. Selecione **uma opção de envio**:
   * **Somente este parceiro**: Envie postbacks somente quando o evento for atribuído a este parceiro, ou seja, o usuário que o realizou veio deste parceiro.
   * **Todos os canais de mídia, incluindo orgânico**: Envie postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos, ou seja, o usuário que o realizou veio de qualquer canal de mídia. **Atenção:** Quando a opção "todas as fontes de mídia, incluindo orgânicas" é selecionada, os postbacks de outros parceiros não contêm dados de atribuição.
6. Clique em **Salvar integração**.

**Lista de parceiros de mediação que podem enviar eventos de receita de anúncios a nível de impressão para ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay mediation (antiga ironSource)
* Admost
* Tradplusad
* Yandex
* Mediação personalizada

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="Lista de ad networks que podem receber sinais de UA e postbacks">

A tabela a seguir mostra as ad networks que podem receber sinais de receita de anúncios de UA e postbacks de redes de mediação.

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">Ad network (parceira)</th><th colspan="2">Suporta</th></tr><tr><th>Sinais de aquisição de usuários</th><th>Postbacks</th></tr></thead><tbody><tr><td>RZR (antiga Aarki)</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aura from Unity</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Google Ads</td><td> </td><td><span>✓</span></td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Modelo híbrido</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Kashkick</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lacuna</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta Ads</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Miniclip</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>Remerge</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>SingleTap da Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok para Empresas</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vivo Global </td><td> </td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Vungle</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Yandex</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO Network</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Descrição |
| --- | --- |
| Tipos de conversão | Tanto os sinais de UA como postbacks de receita de anúncios são compatíveis com dados sobre todos os tipos de conversão: instalações, reatribuições, reengajamentos e reinstalações. |
| Permissões de postback de agências | As agências não podem configurar postbacks de receita de anúncios |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=compartilhamento-de-dados-de-receita-de-an%C3%BAncios-com-parceiros h_01HV6CW4SAF23TT5XZF1SGPVQH=compartilhamento-de-dados-de-receita-de-an%C3%BAncios-com-parceiros procedures=procedimentos h_01HVEEMGMEWDKAXVNHR8C0AHPQ=procedimentos 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=importante additional-information=informa%C3%A7%C3%B5es-adicionais h_01HVE6AREZBPH751WFW70Q7X66=informa%C3%A7%C3%B5es-adicionais h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />
