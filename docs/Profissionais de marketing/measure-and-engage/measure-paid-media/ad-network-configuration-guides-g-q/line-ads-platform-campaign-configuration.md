---
title: Configuração de campanhas na plataforma LINE Ads
metadata:
  keywords:
    - Advertisers
    - LINE Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-10T15:26:17Z'
  edited_at: '2026-09-10T00:24:45Z'
  id: 213050543
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/213050543
---
> Visão geral: A plataforma LINE Ads, um parceiro integrado da AppsFlyer, combina um sistema de bidding com segmentação personalizada. Além da atribuição mobile baseada em cliques, a LINE Ads também oferece atribuição de retargeting, que pode ser registrada com a AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lap.png" width="71px" />

<div id="setting-up-line-ads-platform" />

## Configuração da plataforma LINE Ads

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

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="note" />

> 📘 **Observação:**
>
> Como uma all-installs network, a LINE prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER canal, inclusive canais orgânicos. Para fazer isso, selecione **eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a LINE. Essa configuração só pode ser feita pelo proprietário da conta

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

**ID da conta e App ID**

A plataforma LINE Ads se conecta à AppsFlyer através de LINE\_Ad\_account\_id e LINE\_Ad\_app\_ID exclusivos.  
**Para ativar a integração:** Insira o seu <Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions">LINE\_Ad\_account\_id e LINE\_Ad\_app\_ID</Anchor>.

* Insira seu **LINE\_Ad\_account\_id** exclusivo e seu **LINE\_Ad\_app\_ID**.   
  Consulte a <Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions">documentação do Line Ads sobre como criar um ID empresarial</Anchor>.

<div id="connect-multiple-accounts-and-apps" />

#### Conecte várias contas e aplicativos

Você pode conectar várias contas e aplicativos do Line Ads à AppsFlyer adicionando manualmente um parâmetro de ID da conta ou de ID do aplicativo a um link de atribuição, após a criação dele.

<div id="note-1" />

> 📘 **Observação:**
>
> Parâmetros existentes tanto no link de atribuição quanto em **Configurações gerais** geram conflitos. Para evitar isso, consulte a **lógica de prioridade dos parâmetros** descrita abaixo antes de adicionar parâmetros ao link de atribuição.

**Lógica de prioridade dos parâmetros**

* Quando ambos os tipos de parâmetros, ID da conta e ID do aplicativo (line\_ad\_account\_id, line\_ad\_app\_id), estão incluídos no link de atribuição, qualquer ID correspondente definido em Configurações gerais é substituído.
* Quando um dos tipos de parâmetros estiver ausente do link de atribuição, mas tiver sido definido em Configurações gerais, o valor definido nas configurações gerais será incluído na conexão.
* Quando ambos os tipos de parâmetros, ID da conta e ID do aplicativo, estiverem ausentes das Configurações gerais e dos links de atribuição, a integração poderá não funcionar como esperado.

**Para conectar vários parâmetros de ID da conta e ID do aplicativo:**

1. Configure um ou mais <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">links de atribuição</Anchor>.
2. Adicione a cada link de atribuição um parâmetro de ID da conta e um parâmetro de ID do aplicativo, usando letras minúsculas. Veja a parte destacada no exemplo abaixo.

<div id="example" />

> 📄 **Exemplo**
>
> Exemplo de link de atribuição com parâmetros de ID da conta e ID do aplicativo:
>
> ```http
> https://app.appsflyer.com/id123456789?pid=example_int;...line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&...;redirect=false
> ```

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a LINE Ads após instalações e reengajamentos dos usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à LINE Ads.  
Selecione "**Eventos atribuídos a qualquer parceiro ou eventos orgânicos**" para que toda a base de usuários esteja disponível para o parceiro.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nessa seção, você pode mapear seus eventos da AppsFlyer com a LINE Ads via postbacks.

1. Insira novamente o LINE\_Ad\_app\_ID e o LINE\_Ad\_account\_id.
2. Ative a opção Postbacks de eventos in-app.
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Na lista suspensa, selecione um ***nome de evento do SDK***.
5. Na lista suspensa de ***Identificadores de eventos de parceiros*** selecione a opção correspondente.
6. Clique em ***Adicionar evento*** para adicionar nomes de eventos adicionais.
7. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido na LINE Ads.  <br />Obtenha o ID de evento correspondente da LINE Ads e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

<div id="custom-in-app-events-mapping" />

### Mapeamento de eventos in-app personalizados

A AppsFlyer permite que você mapeie qualquer evento in-app personalizado para enviar à LINE, usando a opção CUSTOM Partner Event Identifier (identificador de evento PERSONALIZADO do parceiro).

O nome do evento e o valor do evento (incluindo os parâmetros do evento) configurados no SDK são encaminhados à LINE.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

[Siga essas instruções](https://help.line.me/admanager/web/categoryId/20007423/pc) para ativar o link de atribuição na plataforma LINE Ads.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Os dados de custos não são compatíveis com esse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Não existem configurações de permissão disponíveis para a plataforma LINE Ads.

</Accordion>

<div data-zendesk-anchors="setting-up-line-ads-platform=configura%C3%A7%C3%A3o-da-plataforma-line-ads h_01HKW2TJ83EZSV30XH3CM0HHB7=configura%C3%A7%C3%A3o-da-plataforma-line-ads h_01HKW2TJ83RG7W6F2PZMAY7BXZ=integration-tab h_01HKW2TJ83VEK727ZH9FPH6TPJ=observa%C3%A7%C3%A3o activate-partner=ativar-parceiro h_01HKW2TJ83VPWD1GK99S4MY3ZB=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW2TJ83PFS3TCPHKZ9HY5PE=configura%C3%A7%C3%B5es-gerais connect-multiple-accounts-and-apps=conecte-v%C3%A1rias-contas-e-aplicativos h_01JAA89AWAQ4JZS3522EVZZN8D=conecte-v%C3%A1rias-contas-e-aplicativos 01JB6YF9SFD2TWTZGR0RPVEBTC=observa%C3%A7%C3%A3o-1 01JAT9SYW9C06P185S9TWKAFM0=exemplo default-postbacks=postbacks-padr%C3%A3o h_01HKW2TJ838FFTAR7NQC9WX295=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW2TJ833VC6SGSRNJSZ53WR=configura%C3%A7%C3%B5es-de-eventos-in-app custom-inapp-events-mapping=mapeamento-de-eventos-in-app-personalizados h_01HKW2TJ83GQ7SFKV6YPM49QP1=mapeamento-de-eventos-in-app-personalizados h_01HKW2TJ83JPB6DSW8Z5PCY1SC=attribution-link-tab h_01HKW2TJ839R8NS3PFHCAJGXTZ=cost-tab h_01HKW2TJ835JT0WD3GN4H3XHT5=ad-revenue-tab h_01HKW2TJ83MPGHKGEMDQQYGGJ1=permissions-tab" />
