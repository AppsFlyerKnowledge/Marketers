---
title: Configure links cross-platform para campanhas em múltiplos dispositivos
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2026-09-16T00:20:38Z'
  id: 6966260647185
  locale: pt
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/pt/articles/6966260647185
---
> **Resumo:** entenda como promover, atribuir e mensurar instalações de aplicativos de acordo com as visualizações de anúncios em outras plataformas. Por exemplo, instalações de aplicativos mobile para anúncios visualizados em dispositivos de CTV, instalações de aplicativos de console de jogos para anúncios visualizados em dispositivos mobile ou desktops (web) e instalações de aplicativos de CTV para anúncios visualizados em dispositivos mobile ou desktop (web).

## Visão geral

Com os links de atribuição cross-platform da AppsFlyer (URLs de impressão), você pode atribuir instalações de uma plataforma de acordo com as visualizações de anúncios exibidos em outra plataforma. Instalações múltiplas dentro da mesma residência podem ser atribuídas à mesma impressão entre plataformas.

### Como funciona a lógica de atribuição?

* As impressões são identificadas no AppsFlyer pelo ID do modelo OneLink e atribuídas a cada plataforma definida no modelo.
* As instalações são identificadas pelo aplicativo e pela plataforma.
* Lógica de correspondência: as impressões no nível do modelo são associadas ao lançamento específico do aplicativo por meio de atribuição probabilística. Qualquer variante do aplicativo no grupo pode ser associada.

## Crie ou edite um template do OneLink para atribuição cross-platform

Um único template oferece suporte ao seu aplicativo em várias plataformas (o que significa que um mesmo template funciona em todas as plataformas). No modelo, você define todas as variantes de plataforma do seu aplicativo (mobile, CTV, desktop, console) agrupadas.

1. Crie ou edite um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">template do OneLink</Anchor> para atribuição entre plataformas.
2. Em **atribuição cross-platform**, clique no **botão de editar ->** **ativar atribuição cross-platform**
3. No menus suspenso da plataforma relevante, selecione o aplicativo desejado. **Atenção:** cada aplicativo pode ser adicionado a apenas um template do OneLink que possui a atribuição cross-platform ativada. [<Image alt="Atribuição cross-platform.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

## Configure a integração de parceiros cross-platform

Para configurar a atribuição cross-platform usando URLs de impressão cross-platform, configure a integração do parceiro para cada aplicativo alvo.

> 🚧 **Importante!**
>
> Certifique-se de ativar a integração do parceiro, seguindo as etapas abaixo para todos os aplicativos que você selecionou no template do OneLink (veja a [seção acima](#crie-ou-edite-um-template-do-onelink-para-atribuição-cross-platform)). Se a integração estiver desativada para um dos aplicativos escolhidos, a atribuição cross-platform não ocorrerá.

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<Accordion title="Passo 1: selecione o aplicativo na integração do parceiro">

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas**
2. Escolha um parceiro integrado.
3. Em **Integração**, no menu suspenso **Aplicativo**, selecione o aplicativo desejado.

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="Passo 2: ative a atribuição de view-through">

Para links que serão usados por parceiros integrados, ative a atribuição de view-through.

1. Em **Integração**, ative Atribuição de view-through para instalação.
2. Clique em **Salvar integração**.

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="Passo 3: crie um link de atribuição (URL de impressão cross-platform).">

Para criar um <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">link de atribuição</Anchor> (URL de impressão cross-platform) para redes integradas:

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiro** > **Integrações ativas** e selecione o parceiro integrado.
2. Em **Link de atribuição**, ao criar um <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">link do OneLink</Anchor>, selecione Usar OneLink.
3. Selecione o template do OneLink que você criou para a atribuição cross-platform.
4. Vá até **Atribuição de view-through**.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. Ative a **atribuição cross-platform**.`af_xplatform=true` Essa ação adiciona o parâmetro `af_xplatform=true` ao link de atribuição de impressão e confere ao link capacidades de atribuição cross-platform. Sem esse parâmetro, a URL funciona como uma URL de impressão regular que não pode atribuir múltiplas instalações à mesma impressão.
6. Configure a **janela de lookback de atribuição de view-through entre plataformas**. Essa ação adiciona o parâmetro `af_xplatform_vt_lookback` ao link de atribuição e indica o número de horas (até 72h) desde que uma impressão ocorreu. Durante ese período, a instalação do aplicativo pode ser atribuída à impressão.
7. Adicione quaisquer parâmetros de atribuição adicionais conforme necessário. Use convenções de nomenclatura que identifiquem sua campanha cross-platform. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais</Anchor> sobre os parâmetros que você pode adicionar para dados e métricas adicionais. Link de exemplo:

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. Forneça o link para que a ad network o coloque por trás do anúncio exibido nas plataformas de CTV, PC ou console.

> 🚧 **Importante!**
>
> Para mídia própria e parceiros não integrados, adicione parâmetros conforme necessário.  <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais</Anchor> sobre os parâmetros que você pode adicionar para dados e métricas adicionais.

</Accordion>

<div id="equal-priority-advanced-setting" />

<Accordion title="Avançado: configuração de prioridade equivalente (opcional)">

Você pode atribuir **prioridade equivalente** a cliques e impressões na atribuição cross-platform. Essa configuração avançada permite que a AppsFlyer encare impressões (por exemplo, em CTV ou consoles) como tendo a mesma prioridade de atribuição que cliques. Para mais informações, veja nosso artigo sobre <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#prioridades-do-método-de-atribuição-cascata-de-atribuição">métodos de prioridade de atribuição</Anchor>.

**Para habilitar a prioridade equivalente:**

1. Na seção de configuração cross-platform, selecione a opção **Prioridade equivalente**.
2. Clique em **Salvar**.

> 📘 **Atenção**
>
> Ativar a opção de prioridade equivalente pode fazer com que a AppsFlyer priorize sua própria atribuição em relação a outras fontes. Use essa configuração com cautela e apenas se ela estiver alinhada com sua estratégia geral de atribuição.

</Accordion>

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| <span id="attribution-window"></span>Janela de atribuição | Entre 1-72 horas, dependendo do parâmetro `af_xplatform_vt_lookback` da janela de lookback (o padrão é 24 horas). |
| <span id="retargeting"></span>Redirecionamento | <ul><li>Reatribuição: disponível para cross-platform-to-mobile. Indisponível para outras plataformas.</li><li>Reengajamento: Indisponível</li></ul> |
| <span id="attribution-method"></span>Método de atribuição | Atribuição de view-through com modelagem probabilística |
| <span id="household-attribution"></span>Atribuição a nível doméstico | Disponível. Instalações múltiplas dentro da mesma residência podem ser atribuídas à mesma impressão entre plataformas. |
| <span id="reporting"></span>Relatórios | <ul><li>Instalações cross-platform estão disponíveis nos dashboards e relatórios da AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/getting-started-with-appsflyer-dashboards">Dashboards</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">relatórios</Anchor> de dados agregados e</li><li><Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatórios</Anchor> de dados brutos</li></ul></li><li>Impressões cross-platform não são exibidas em dashboards a nível de aplicativo. No entanto, eles estão disponíveis no <Anchor target="_blank" href="/marketers/pt/docs/data-locker-advertiser-reports#user-journey">relatório de engajamento cross-platform</Anchor> via Data Locker.</li><li>Certifique-se de usar as convenções de nomenclatura de parâmetros para identificar facilmente sua campanha cross-platform.</li></ul> |
| <span id="ip-masking"></span>Mascaramento de IP | O mascaramento de IP para engajamentos cross-platform não está disponível, pois essa é uma característica a nível de aplicativo. Se o `ip_masking` estiver configurado, a instalação não será atribuída ao engajamento cross-platform. |
| <span id="ctvto-mobile"></span>CTV-to-mobile | Fluxos de atribuição de CTV-to-mobile estão disponíveis apenas para [parceiros integrados](/docs/set-up-cross-platform-links-for-multi-device-campaigns#list-of-ad-networks) que têm autorização para realizar campanhas cross-platform. |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>Links de atribuição cross-platform em dispositivos mobile | Quando um link de atribuição cross-platform é visualizado em um dispositivo mobile, a atribuição é determinada pela lógica padrão de modelagem probabilística, não pelo fluxo de atribuição cross-platform projetado para <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>, PC e consoles. Consequentemente, impressões mobile não são elegíveis para a implementação da [prioridade equivalente](#step-3-enable-equal-priority-for-crossplatform-impressions), [janela de lookback estendida](#attribution-window) ou [atribuição interna](#household-attribution), que estão disponíveis para impressões genuínas entre plataformas. |
| <span id="agency-permissions"></span>Permissões da agência | Agências não podem ativar a "prioridade de atribuição equivalente entre plataformas". Essa configuração é copiada diretamente das configurações definidas para uma ad network específica. |

## Discrepâncias

AppsFlyer e tvScientific usam modelos de atribuição diferentes. Isso pode causar discrepâncias entre os dashboards da tvScientific e da AppsFlyer. Veja os motivos abaixo:

| Causa | tvScientific | A AppsFlyer |
| --- | --- | --- |
| Modelo de linha de base | Modelo de atribuição de crédito compartilhado | Modelo de atribuição de último toque |
| Janela de lookback | Até 30 dias | Até 72 horas |
| Redirecionamento | Atribuição de novos usuários (instalações) e usuários recorrentes (reengajamentos) | Apenas novos usuários são atribuídos (instalações) |
| Atribuição de custo | O custo é atribuído à impressão independentemente do sistema operacional | O custo é atribuído à impressão em diferentes sistemas para iOS e Android |

## Perguntas frequentes

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<Accordion title="É necessário ativar a atribuição de view-through por meio de modelagem probabilística?">

Não. A opção de atribuição de view-through por meio da modelagem probabilística nas configurações do seu aplicativo não precisa estar ativada para que a atribuição de view-through funcione entre plataformas.

</Accordion>

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<Accordion title="Por que não vejo impressões para minhas campanhas cross-platform no dashboard?">

Impressões cross-platform não são exibidas nos dashboards a nível de aplicativo. Isso ocorre porque uma impressão de CTV pode levar a várias conversões em diferentes aplicativos, e não há uma maneira precisa de conectar essas impressões a cada aplicativo. Você pode acessar os dados de impressões no <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-data-via-data-locker#tipos-de-relatórios-e-disponibilidade">relatório de engajamento cross-platform no Data Locker</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8V0RV7X8JEVEJ36TJB1X43D=vis%C3%A3o-geral app-group-vs-individual-app-%E2%80%93-attribution-logic=como-funciona-a-l%C3%B3gica-de-atribui%C3%A7%C3%A3o h_01KANVNVCY6JFTJ1SVK3DGM54C=como-funciona-a-l%C3%B3gica-de-atribui%C3%A7%C3%A3o step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=crie-ou-edite-um-template-do-onelink-para-atribui%C3%A7%C3%A3o-cross-platform h_01HVECG1TZ8B5GH28CZM2186BF=crie-ou-edite-um-template-do-onelink-para-atribui%C3%A7%C3%A3o-cross-platform set-up-crossplatform-attribution=configure-a-integra%C3%A7%C3%A3o-de-parceiros-cross-platform h_01HVECG1TZSDTP0WBG7XYM509G=configure-a-integra%C3%A7%C3%A3o-de-parceiros-cross-platform 01JEKG3V0C75G782RC7CE9DAV2=importante h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=importante-1 h_01K2HBZKX0EJHSVCXJJ97NMVXZ=equal-priority-advanced-setting equal-priority-impact-note=aten%C3%A7%C3%A3o h_01K2HBZKX0ECJPTQMPPXC3JBVC=aten%C3%A7%C3%A3o traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HVED5DJPFR5XCWYDSYCHMCR6=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es discrepancies=discrep%C3%A2ncias h_01HVED5DJPMP3AQDTN3GM77T2F=discrep%C3%A2ncias faq=perguntas-frequentes h_01HVED5DJPBPDSZ0AAY1RG8NEZ=perguntas-frequentes h_01K4AC2J63B4MBTDGZHH7ACRCG=does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on why-don%E2%80%99t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard h_01K4AC2J63KBF8X20DMNPW1GTK=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />
