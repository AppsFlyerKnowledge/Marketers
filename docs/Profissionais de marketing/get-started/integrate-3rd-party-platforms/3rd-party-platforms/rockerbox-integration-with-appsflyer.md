---
title: Integração da Rockerbox com a AppsFlyer
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
  created_at: '2020-11-23T14:55:00Z'
  edited_at: '2026-08-19T00:11:37Z'
  id: 360015760757
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360015760757
---
> **Visão geral:** Saiba como compartilhar dados automaticamente da AppsFlyer para a Rockerbox, uma plataforma de marketing e plataforma de analytics para aplicativos mobile e web.

![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/rockerbox.png)

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configuração da Rockerbox

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

### Ativar parceiro

Esta opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativação de parceiros</Anchor>.

### Configurações gerais

**ID da conta da Rockerbox**

**Para conectar sua conta da Rockerbox à AppsFlyer,** insira o ID da sua conta em **ID da conta da Rockerbox**.   
O ID da sua conta da Rockerbox está disponível na plataforma da Rockerbox em **Settings** > **Account** > **General**.

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a Rockerbox após instalações de usuários. Use esta seção para definir a fonte dos usuários para a qual os postbacks serão enviados para cada evento. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

Para enviar postbacks para a Rockerbox de qualquer usuário que fizer o download do aplicativo, selecione **Todos os canais de mídia, incluindo orgânico**.

### Configurações de eventos in-app

![rockerbox-in-app-events_en-us.png](https://files.readme.io/3fc74bb16d6a1222d1d244bbb1083ff247e3315d0fc7060e0ec3e8ad30a07233-360013891517.png)

Nesta seção, você mapeia eventos da AppsFlyer com o parceiro através de postbacks. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Insira o **ID da conta da Rockerbox**.
2. Ative o **postback de eventos in-app.**
3. Clique **Adicionar evento** para adicionar um evento de SDK à lista.
4. Selecione o **nome do evento de SDK** no menu suspenso.
5. Selecione a opção necessária no menu suspenso Enviar receita:
   * **Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.
   * **Com valores e sem receita:** envia todos os parâmetros excluindo o valor da receita.
   * **Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).
6. Para concluir a configuração de integração, clique em **Salvar integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não se aplicam à integração com esse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não se aplica à integração com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para este parceiro.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJW82HZ9FR31VHHRBZ3EM=importante setting-up-rockerbox=configura%C3%A7%C3%A3o-da-rockerbox h_01H9HWJW83BKP8DSYTV6YGPHK7=configura%C3%A7%C3%A3o-da-rockerbox h_01H9HWJW83WDGQKKMM942NPA1S=integration-tab activate-partner=ativar-parceiro h_01H9HWJW83Z4NGT000091AHX0Z=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9HWJW832NQBPK2VS6TS1QK7=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9HWJW83CGMBADDBP7EJTR9N=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWJW84H4SDVRNZAG1D6N0D=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWJW84G6GXMBTGMHTDPM6R=attribution-link-tab h_01H9HWJW84BZNHN4DRKA33WCVK=cost-tab h_01H9HWJW848DRTKBF3AKR5KYC5=ad-revenue-tab h_01H9HWJW84NTZWKP2FP2WK4FZD=permissions-tab" />
