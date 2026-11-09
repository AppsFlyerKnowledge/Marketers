---
title: Integração do Insider com a AppsFlyer
metadata:
  keywords:
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
  created_at: '2021-01-03T11:23:45Z'
  edited_at: '2026-08-19T00:11:06Z'
  id: 360016827838
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360016827838
---
> **Resumo:** o Insider, um parceiro integrado da AppsFlyer, é uma plataforma de marketing e analytics para aplicativos mobile e web. O Insider oferece segmentação preditiva e personalização em tempo real em web, web mobile, aplicativo mobile e canais de anúncios.

<Image align="center" alt="rockerbox-logo_en-us.png" src="https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png?v=1" />

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-insider" />

## Configurando o Insider

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

O Insider se conecta com a AppsFlyer por meio de um identificador exclusivo do parceiro.

**Para obter seu identificador,** faça login na plataforma **Insider** e copie o identificador no canto superior direito do dashboard.

<Image align="center" alt="insider-partner-ID_en-us.png" src="https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png" />

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Insider após instalações de usuários. Use essa seção para definir a fonte de usuários para a qual os postbacks são enviados. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

**Para enviar postbacks para qualquer usuário que fizer o download do aplicativo para o Insider**, selecione **Todos os canais de mídia, incluindo orgânico**.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

<Image align="center" alt="insider-partner-field.png" src="https://files.readme.io/ad4b4a5e9d688be93b20ccf645c779c361390cc95e2a2acbab7299408b7478bf-4403354160785.png" />

Nesta seção, você mapeia eventos da AppsFlyer com o parceiro através de postbacks. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app.</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Insira o **parceiro Insider**, encontrado no canto superior direito do dashboard do **Insider**.

   <Image align="center" alt="insider-partner-ID_en-us.png" src="https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png" />
2. Na AppsFlyer, ative o **postback de eventos in-app.**
3. Clique em **Adicionar evento** para adicionar um evento de SDK à lista.
4. Selecione o **nome do evento de SDK** no menu suspenso.
5. Insira o **identificador de evento do parceiro**.
6. Selecione a **opção de envio**.
7. Selecione a opção necessária no menu suspenso Enviar receita:
   * **Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.
   * **Com valores e sem receita:** envia todos os parâmetros excluindo o valor da receita.
   * **Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).
8. Para concluir a configuração de integração, clique em **Salvar integração**.

<div id="note" />

> 📘 **Atenção**
>
> Para ativar os postbacks, defina o InsiderID como o CUID.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são aplicáveis à integração com esse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é aplicável à integração com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para este parceiro.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8YZMFS4XHX69CG90A18K=importante setting-up-insider=configurando-o-insider h_01H9FK8YZM63N7HF514RVFPMJY=configurando-o-insider h_01H9FK8YZN7D4R6TBABMDB3K3K=integration-tab activate-partner=ativar-parceiro h_01H9FK8YZNMN9QBRS33WPZQWPB=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK8YZNAFP5G2B277YPNY68=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FK8YZNZWSD64K3R2TVHCE2=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK8YZN15KPHHA58XRABRD4=configura%C3%A7%C3%B5es-de-eventos-in-app h_01K88DMNP3SKDE93SXGXJXTE0C=aten%C3%A7%C3%A3o h_01H9FK8YZNJ86KQT59H9RD5CJA=attribution-link-tab h_01H9FK8YZN99ZBQQFBZF26HJZJ=cost-tab h_01H9FK8YZNAJ1XW7TSQWT7PYPW=ad-revenue-tab h_01H9FK8YZQTKN1SFMN9M0CKVYM=permissions-tab" />
