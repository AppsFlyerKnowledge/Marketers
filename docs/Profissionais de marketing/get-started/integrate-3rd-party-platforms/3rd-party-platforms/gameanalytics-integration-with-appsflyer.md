---
title: Integração do GameAnalytics com a AppsFlyer
metadata:
  keywords:
    - GameAnalytics
    - integrated partner
    - Advertisers
    - Ad Networks
    - game
    - game analytics
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
  created_at: '2015-12-24T11:42:56Z'
  edited_at: '2026-08-19T00:11:01Z'
  id: 207447143
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207447143
---
> **Resumo:** O GameAnalytics, um parceiro integrado da AppsFlyer, é uma ferramenta gratuita poderosa que ajuda desenvolvedores a entender o comportamento dos jogadores para que possam melhorar o engajamento, reduzir a rotatividade e aperfeiçoar a monetização. Ajuda a visualizar os principais KPIs de gaming numa única visualização prática e oferece benchmarking in-game para ver como as suas métricas se comparam com mais de 14.000 títulos semelhantes.

Leva apenas alguns minutos para configurar e é totalmente gratuito — sem limites de uso nem recursos premium ocultos! Se você prefere ver a plataforma em ação antes de integrá-la ao seu título, basta se cadastrar para ver um jogo de demonstração com dados pré-preenchidos.

A plataforma é confiável para mais de 40.000 desenvolvedores de jogos no mundo todo, de indies a estúdios mundialmente renomados, e processa mais de cinco bilhões de eventos únicos todos os dias em 2+ bilhões de dispositivos. O GameAnalytics é amplamente integrado, com SDKs para todos os principais motores de jogo e plataformas. Você pode se cadastrar gratuitamente hoje em https://gameanalytics.com/

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configuração do GameAnalytics

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo:

A janela de configuração do Game Analytics usa apenas a ***integração*** guia.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

### Configurações gerais

**Chave do jogo**

O Game Analytics se conecta à AppsFlyer por meio de uma chave do jogo exclusiva. Se você ainda não a tem, deve obtê-la no Game Analytics para continuar com a integração.

![Game_Analytics_msc_new_2.png](https://files.readme.io/0c629a74c16d6d8a861ee3ec344de68516a6224e9d6f5afb4b7d89fe78baa49f-360002199865.png)

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para instalações de usuários do Game Analytics. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Game Analytics para qualquer usuário que fizer o download do aplicativo, ou selecione **Off**.

### Configurações de eventos in-app

[![](https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png)](https://files.readme.io/64dd102e95aacda70cb8c0cde471c5c31d6b744543089a2d00a1ab1640fbb1c3-360002219789.png)

Nesta seção, você pode mapear os eventos da AppsFlyer com o Game Analytics por meio de postbacks.

1. Insira a chave do jogo novamente.
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no lado do Game Analytics.  <br />Obtenha o ID do evento correspondente no Game Analytics e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do rich in-app event para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se ele existir no evento). |

Clique em **Guardar**.

Depois que essa configuração for salva, a AppsFlyer começará a enviar os seguintes dados para o Game Analytics para cada Instalação não orgânica:

* game\_key
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Game Analytics.

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

As permissões não estão disponíveis para o Game Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7ZH27GNEHRZ5KKVH5CHY=importante setting-up-gameanalytics=configura%C3%A7%C3%A3o-do-gameanalytics h_01H9FK7ZH24E9AD7Z0J94NS0JJ=configura%C3%A7%C3%A3o-do-gameanalytics h_01H9FK7ZH3VPBE965Z8MCVXSMQ=integration-tab activate-partner=ativar-parceiro h_01H9FK7ZH3D2H5AWW0DMBQP9R3=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK7ZH3E32TT8EGAYWPRWBE=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FK7ZH3P0HSQGR2409BFA2F=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK7ZH366RDSY36QVVWJMJN=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK7ZH39J4Q7W5XSFZAEZWH=attribution-link-tab h_01H9FK7ZH37FQ6RN80E90TH4K9=cost-tab h_01H9FK7ZH3GE3G69AA03KJK499=ad-revenue-tab h_01H9FK7ZH3RQJQPAYSZBR208H7=permissions-tab" />
