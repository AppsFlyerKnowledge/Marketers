---
title: Integração do Spoteffects com AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Webeffects
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-09-06T14:38:15Z'
  edited_at: '2026-08-19T00:11:45Z'
  id: 115004574426
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/115004574426
---
> **Visão geral:** Spoteffects, um parceiro integrado da AppsFlyer, desenvolve e comercializa a solução de software como serviço. A solução permite que planejadores de mídia otimizem suas campanhas de TV para lojas online e sites com base em visitas e conversões geradas imediatamente por anúncio.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-spoteffects" />

## Configuração do Spoteffects

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Spoteffects usa apenas a guia ***Integração***.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para instalações de usuários do Spoteffects. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Spoteffects para qualquer usuário que fizer download do aplicativo ou selecione **Desativado**.

Clique em **Guardar.**

<div id="in-app-event-settings" />

### Configurações de eventos in-app

[![](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)](https://files.readme.io/97da1d47ab9bfa3855d18dcd60f3a263b8a631c477b354dc32486170b7708e96-360002201165.png)

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Spoteffects por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou o ID de cada evento, conforme definido no lado do Spoteffects.  <br />Obtenha o ID de evento correspondente do Spoteffects e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento rich in-app ao parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

Clique em **Guardar**.

Depois de salvar a configuração, a AppsFlyer envia os seguintes dados ao Spoteffects para cada instalação orgânica e não orgânica:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Spoteffects.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para o Spoteffects.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJYD7AZTFXKESY1KHW52S=importante setting-up-spoteffects=configura%C3%A7%C3%A3o-do-spoteffects h_01H9HWJYD75MTKJBMSZRFAG66Q=configura%C3%A7%C3%A3o-do-spoteffects h_01H9HWJYD7MAWK9S226YWPZJ8G=integration-tab activate-partner=ativar-parceiro h_01H9HWJYD7X6KEFF3VEZEP4PGM=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01H9HWJYD7PW2TCYJRA815YNQE=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWJYD7SK47G91GF9J9Q2ZB=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWJYD8RJM9BDX9RKSCC4RY=attribution-link-tab h_01H9HWJYD81VXJPT5D2TKQQN9C=cost-tab h_01H9HWJYD8XBV0V0KDNY955JCT=ad-revenue-tab h_01H9HWJYD8B9AQMVVMT16EH602=permissions-tab" />
