---
title: Configuração de campanha da MoEngage
metadata:
  keywords:
    - MoEngage
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
  created_at: '2017-06-25T07:50:18Z'
  edited_at: '2026-08-19T00:11:29Z'
  id: 115003139643
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/115003139643
---
> **Em resumo:** MoEngage, uma plataforma de engajamento do cliente de terceiros integrada ao AppsFlyer, é uma plataforma de engajamento do cliente agentic desenvolvida para o mundo mobile-first.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-moengage" />

## Configurando a MoEngage

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na sua primeira visita, habilite **Ativar parceiro** para configurar a integração. A alavanca deve ser mantida enquanto você trabalhar com o parceiro. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">como configurar o cabeçalho da página do parceiro.</Anchor>

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba **Integração** é dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

A MoEngage se conecta ao AppsFlyer por meio de um ID do Aplicativo, uma chave do Aplicativo e o data center da MoEngage. Se você ainda não tiver o ID do Aplicativo e a chave do Aplicativo, deverá obtê-los primeiro para continuar com a integração:

* **APP\_ID:** Insira o ID do aplicativo. Para obtê-lo, faça login na sua conta da MoEngage no menu à esquerda e acesse **Settings** > **App Settings**.
* **MoEngage Data Center:** Especifique o data center da MoEngage no qual você se cadastrou. Saiba mais sobre <Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage">Data Centers na MoEngage</Anchor>.
* **APP\_KEY:** Insira a chave de API do aplicativo. Para obtê-la, faça login na sua conta da MoEngage e acesse **Settings** > **Analytics**.

![moengage_general_settings_en-us.png](https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png)

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a MoEngage após instalações de usuários. Escolha uma das seguintes opções:

* **Desativado**: Não envie nenhum postback de instalação.
* **Todos os canais de mídia, incluindo orgânicos**: Envie postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Nota**
>
> Como uma network de todas as instalações, a MoEngage prefere receber postbacks de todas as novas instalações do seu aplicativo de qualquer fonte, incluindo orgânicas. A MoEngage recomenda selecionar **Todos os canais de mídia, incluindo orgânicos**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

**Link de Atribuição** não é compatível com a integração com este parceiro.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

**Dados de custo** não são compatíveis com a integração com este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

**Receita de anúncios** não é compatível com a integração com este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

**Permissões** não são compatíveis com a integração com este parceiro.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJPMX1TXBZY6C94HQ7J85=importante setting-up-moengage=configurando-a-moengage h_01H9HWJPMXN58VV9SQQPY4T5HZ=configurando-a-moengage h_01H9HWJPMX946NS52DTPAZWVEK=integration-tab activate-partner=ativar-parceiro h_01H9HWJPMX46NV79HHGRRD6D56=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9HWJPMXPZ5QV9D08CJMHMHS=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9HWJPMX0TZ496PP8EY3H336=postbacks-padr%C3%A3o h_01H9HWJPMX4CHJ9MADEQBSDMGY=nota h_01H9HWJPMXJVWPK67W5X88GYHZ=attribution-link-tab h_01H9HWJPMXQ07XNN8Y79P5DCAN=cost-tab h_01H9HWJPMX8MC1GSD2VD3QQ82Y=ad-revenue-tab h_01H9HWJPMXKYXVCH3HRA2FCPSQ=permissions-tab" />
