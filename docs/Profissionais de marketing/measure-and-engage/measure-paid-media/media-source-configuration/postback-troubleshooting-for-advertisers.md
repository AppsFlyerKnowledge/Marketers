---
title: Identificação e solução de problemas de postback para anunciantes
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-09-16T00:28:18Z'
  id: 14272573202833
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/14272573202833
---
> **Visão geral:** encontre as principais causas e soluções para o motivo pelo qual seu parceiro não está recebendo os postbacks esperados. Analise cada um dos tópicos abaixo e veja se eles podem ser a causa.

<div id="check-the-integration-toggles" />

## Verifique as alavancas de integração

Diferentes alavancas controlam diferentes partes da integração. O estado da alavanca pode ser o motivo para não receber postbacks.

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Ativar parceiro está desabilitado">

Quando a alavanca <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">**Ativar parceiro**</Anchor> está desativada, as conversões não são atribuídas e os postbacks não são enviados aos parceiros.

<Image align="center" alt="integration_turned_off.png" src="https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png" />

**Para ativar a integração:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **c**
2. Clique no ícone Gerenciar integração do parceiro.
3. A partir da aba **Integração**, ative a alavanca **Ativar parceiro**.

Outro caso pode ser se a alavanca <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">**Ativar parceiro**</Anchor> estiver ativada no momento, mas durante o evento, ela foi desativada. Use o log de auditoria para verificar se a integração do parceiro estava ativa no momento do evento:

* <span id="1703758710.321359"></span>Acesse seu e-mail de usuário (canto superior direito) > **Central de segurança** > **Log de auditoria**.

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="Os postbacks de eventos in-app estão desativados">

A alavanca **<Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Postbacks de eventos in-app</Anchor>** está desativada ou pode ter sido desativada durante o evento. Isso significa que nenhum postback é enviado.

**Para ativar os postbacks de eventos in-app:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiro** > **Integrações ativas.**
2. Clique no ícone Gerenciar integração do parceiro.
3. Na aba **Integração**, role para baixo até a alavanca **Postbacks de eventos in-app** e ative-a.

   <Image align="center" alt="integration-in_app_event_postbacks_toggle.png" src="https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png" />

</Accordion>

<div id="check-the-event-configuration" />

## Verifique a configuração do evento

O evento pode ser configurado de forma que determinados postbacks não sejam enviados.

<div id="the-event-wasnt-configured" />

<Accordion title="O evento não está configurado">

Verifique se o evento está incluído na lista de eventos in-app que foram configurados. Se não estiver definido, um postback não será enviado.

<Image align="center" alt="list_of_in_app_events.png" src="https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png" />

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiro** > **Integrações ativas.**
2. Clique no ícone Gerenciar integração do parceiro.
3. Na aba **Integração**, role para baixo até **Postbacks de eventos in-app** e veja se o nome do evento aparece.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="O evento está configurado incorretamente">

Verifique se o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">mapeamento de eventos</Anchor> está correto. Postbacks de eventos após esse período não são enviados ao parceiro, embora os eventos ainda sejam registrados na AppsFlyer.

<Image align="center" alt="in_app_event_postback_mapping_2.png" src="https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png" />

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="O evento está configurado corretamente, mas com uma condição">

Se uma condição for definida para o evento, o postback será enviado de acordo com a condição. Verifique se há uma condição que limita o envio de postback.

<Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="O evento está configurado para enviar postbacks apenas para o parceiro atribuído">

Verifique se a configuração do evento in-app está definida para enviar postbacks <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#opções-para-envio-de-postbacks">**Somente este parceiro** ou para **Todas as fontes de mídia, incluindo orgânicas**</Anchor>. Se estiver definido como **Somente este parceiro**, somente o parceiro atribuído receberá o postback.

<Image align="center" alt="in_app_event_sending_options.png" src="https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png" />

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="O evento ocorreu fora da janela de configuração">

Os postbacks são enviados de acordo com a configuração da <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">janela de postback</Anchor>. Postbacks de eventos após esse período não são enviados ao parceiro, embora os eventos ainda sejam registrados na AppsFlyer.

<Image align="center" alt="in_app_event_postback_window.png" src="https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png" />

Observe que, para <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor>, os postbacks de eventos in-app são enviados durante o <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention#períodos-de-retenção-de-dados-de-parceiros">período de retenção de dados do parceiro</Anchor>.

</Accordion>

<div id="privacy-restrictions" />

## Restrições de privacidade

Nos casos a seguir, a AppsFlyer não envia postbacks devido a restrições de privacidade.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="O parceiro não é compatível com a privacidade avançada ou não a configurou">

Quando a <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Privacidade avançada</Anchor> está ativada, mas o parceiro não configurou a Privacidade avançada ou não tem compatibilidade com a Privacidade avançada, ele não receberá <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#tipos-de-templates-para-envio-de-postbacks">postbacks agregados de Privacidade Avançada</Anchor>.

<Image align="center" alt="partner_not_supporting_ap_postbacks.png" src="https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png" />

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Restrições de fonte de mídia em plataformas de terceiros">

<Anchor target="_blank" href="/marketers/pt/docs/discrepancies-between-appsflyer-and-third-party-platforms#restrições-de-postback-em-plataformas-externas">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. A AppsFlyer não ativa o compartilhamento de dados no nível de usuário adquiridos por meio dessas fontes de mídia com plataformas ou serviços de terceiros. Todas as instalações de tais fontes de mídia são, portanto, enviadas como orgânicas. Observe que os anúncios da Meta não permitem o compartilhamento de dados com plataformas party.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="O SDK foi configurado para não compartilhar informações com o parceiro">

Um filtro de compartilhamento foi implementado no SDK para impedir que o parceiro receba informações. Esse filtro pode ser ativado por uma solicitação explícita de opt-out do usuário ou em qualquer outro momento durante o ciclo de vida do aplicativo.

Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods#como-impedir-o-compartilhamento-de-dados-com-ad-networks">Impedir o compartilhamento de dados com terceiros</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Diversos

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="O postback foi enviado, mas não aparece na plataforma do parceiro">

Em alguns casos, embora a AppsFlyer envie postbacks para um parceiro, eles não os exibem do lado do parceiro. Nesses casos, entre em contato com o parceiro.

**Para ver se o postback foi enviado da AppsFlyer:**

1. Na AppsFlyer, em **Relatórios** , vá para **Exportação de dados brutos**.
2. Visualize o relatório relevante em **Postbacks** (instalações, eventos in-app, conversões de retargeting, retargeting de eventos in-app).

<Image align="center" alt="postback_reports.JPG" src="https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png" />

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="O evento não ocorreu ou não foi enviado para a AppsFlyer">

Todos os eventos ocorridos podem ser encontrados no <Anchor target="_blank" href="/marketers/pt/docs/activity-dashboard">painel **Atividade**</Anchor> e nos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview?query=raw%20data%20reports">Relatórios de dados brutos</Anchor>. Um evento não exibido significa que não ocorreu ou não foi enviado para a AppsFlyer.

Pode ser que o evento não tenha sido definido no SDK. Nesse caso, você não o verá na plataforma. Verifique a configuração do SDK.  Verifique a configuração do SDK <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#registro-de-eventos-in-app">definida no SDK</Anchor>.

Se você acha que o evento ocorreu, verifique abaixo como ver se ele aparece no painel de atividades ou crie um relatório de dados brutos e procure-o lá.

**Para visualizar o painel Atividade:**

* Na AppsFlyer, em **Painéis**, vá para **Atividade** e selecione o parceiro e o intervalo de datas.

**Para criar um relatório de dados brutos:**

1. Na AppsFlyer, em **Relatórios** , vá para **Exportação de dados brutos**.
2. Clique em **Criar relatório**.
3. Selecione o relatório relevante.
4. Selecione o intervalo de datas e qualquer um dos campos necessários e clique em **Criar**.
5. Faça download do relatório e procure o evento lá.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Diferenças nos fusos horários">

Pode haver discrepâncias no recebimento de postbacks devido à diferença de fuso horário entre a plataforma AppsFlyer e a plataforma do parceiro. Painéis e relatórios da Appsflyer são exibidos de acordo com o fuso horário selecionado.

**Para ver o fuso horário do aplicativo na AppsFlyer:**

1. Na AppsFlyer, em **Configuração** vá para **Configurações do aplicativo**.
2. Visualize o fuso horário do aplicativo em **Localização**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="SRNs sem IDs de publicidade (IDFA/GAID)">

Há vários <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">casos específicos para SRNs</Anchor> nos quais a AppsFlyer não envia postbacks para instalações, aberturas de aplicativos ou eventos in-app.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="Restrições de fonte de mídia em plataformas de terceiros">

<Anchor target="_blank" href="/marketers/pt/docs/discrepancies-between-appsflyer-and-third-party-platforms#restrições-de-postback-em-plataformas-externas">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. A AppsFlyer não pode compartilhar dados no nível do usuário adquiridos por meio desses canais de mídia com plataformas ou serviços de terceiros. Todas as instalações de tais fontes de mídia são, portanto, enviadas como orgânicas. Observe que os Meta ads não compartilham nenhum dado com plataformas de terceiros.

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="Postbacks de Privacidade Avançada">

Quando a Privacidade Avançada (AP) está ativada, os dados ao nível do utilizador de utilizadores sem consentimento que executam o iOS 14.5+ não ficam disponíveis através de postbacks. Os postbacks são enviados de acordo com o <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#tipos-de-templates-para-envio-de-postbacks">template de Privacidade Avançada</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> <Anchor target="_blank" href="/partners/pt/docs/postback-troubleshooting-for-ad-networks">Identificação e solução de problemas para ad networks</Anchor>

<div data-zendesk-anchors="activation-toggles=verifique-as-alavancas-de-integra%C3%A7%C3%A3o h_01H9FT385FY1QJC6M2YVMZF2NC=verifique-as-alavancas-de-integra%C3%A7%C3%A3o h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=verifique-a-configura%C3%A7%C3%A3o-do-evento h_01H9FT385FW71JV2KKZ22TP6TN=verifique-a-configura%C3%A7%C3%A3o-do-evento h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window privacy-restrictions=restri%C3%A7%C3%B5es-de-privacidade h_01H9FT385G84E2A1J64VWG8H4Z=restri%C3%A7%C3%B5es-de-privacidade h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=diversos h_01H9FT385GSWRPKEHKJ4HXCX01=diversos h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=veja-tamb%C3%A9m" />
