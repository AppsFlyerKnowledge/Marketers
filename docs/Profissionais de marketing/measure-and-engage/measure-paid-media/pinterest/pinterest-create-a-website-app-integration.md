---
title: Pinterest—Crie uma integração de aplicativo do seu site
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-14T13:07:07Z'
  edited_at: '2026-08-31T12:31:05Z'
  id: 47721580892433
  locale: pt
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/pt/articles/47721580892433
---
**Resumo:** Configure uma integração do Pinterest para o aplicativo do seu site para enviar eventos de conversão web ao Pinterest para otimização de campanhas e relatórios.

## **Configurar a integração**

**Pré-requisitos:**

* Uma conta no Pinterest
* Um aplicativo de site configurado na AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Saiba mais</Anchor>
* O <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">Web SDK</Anchor> da AppsFlyer ou a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement">API Server-to-Server (S2S)</Anchor> para atribuição web

**Para ativar ou editar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Marketplace**.  
   **Para editar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
2. Selecione o aplicativo do seu site no menu suspenso acima.
3. Procure por Pinterest e clique em **Integrar**.
4. Na aba **Integração**, ative o botão de alternância **Ativar parceiro**.  
   **Atenção:** O botão de alternância deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativado)</Anchor> durante todo o tempo em que você trabalhar com o Pinterest.
5. Complete a configuração na aba **Integração**, conforme descrito abaixo.

## **Aba Integração**

### **Ativar parceiro**

No **primeiro acesso**, ative a opção **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o Pinterest.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

### **Configurações de eventos in-app**

Para enviar postbacks de eventos in-app para o Pinterest, forneça as seguintes credenciais do Pinterest. Essas credenciais são incluídas nos postbacks de eventos enviados ao Pinterest.

* **ID da conta de anúncios** - O identificador exclusivo da sua conta de anúncios do Pinterest.
* **Token de acesso** - Um token de acesso gerado no Pinterest.

Você pode encontrar o ID da conta de anúncios e o token de acesso na interface do Pinterest Ads Manager (consulte a <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id">documentação do Pinterest</Anchor>). Entre em contato com o suporte do Pinterest se precisar de ajuda.

**Para definir as credenciais do Pinterest:**

1. No AppsFlyer, na página **Integração ativa** do Pinterest > aba **Integração**, role até **Configurações de eventos in-app**.
2. Insira os valores do ID da conta de anúncios e do token de acesso nos respectivos campos.

### **Aba Permissões**

Nesta seção, você mapeia seus eventos web da AppsFlyer para eventos do Pinterest por meio de postbacks.

1. Nas configurações da integração com o Pinterest, role até **Postbacks de eventos in-app**.
2. Ative **Postbacks de eventos in-app**.
3. Configure a janela de postback de eventos in-app.
4. Selecione as configurações e mapeamentos de postbacks para eventos.

| **Nome do parâmetro** | **A descrição** |
| --- | --- |
| **AppsFlyer event name** | O nome do evento web, conforme recebido pela AppsFlyer por meio do SDK web integrado ao seu site ou por meio de eventos de servidor para servidor.<br /><br />**Atenção:** Se você não vir o evento desejado na lista, verifique se o evento foi ativado e confira novamente. |
| **Partner event name** | O evento do Pinterest a ser mapeado, selecionado na lista predefinida de eventos do Pinterest. Para ver os nomes dos eventos do Pinterest, consulte a <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">documentação do Pinterest</Anchor>. |
| **To users from** | **Somente este parceiro:** eventos que vêm apenas de usuários atribuídos ao Pinterest.<br /><br />**Todos os canais de mídia, incluindo orgânico:** toda a sua base de usuários fica disponível para ser reportada ao parceiro. |
| **Including** | Selecione se a receita do evento ou os valores dos parâmetros serão enviados ao parceiro no postback. A AppsFlyer pode enviar todos os parâmetros do evento avançado da web, exceto o parâmetro de receita (contido em **af\_revenue**), ou todos os parâmetros, incluindo o valor da receita (se houver). |

> 📘 **Note**
>
> Se você também executa a Pinterest Tag no seu site, envie o mesmo ID de evento para a AppsFlyer e o Pinterest para que a AppsFlyer possa desduplicar os eventos:
>
> * Inclua af\_customer\_event\_id no payload do evento que você envia para a AppsFlyer, dentro de eventValue para o SDK web ou event\_value para a API S2S (server-to-server).
> * Envie o mesmo valor no evento correspondente da Tag.
>
> A AppsFlyer encaminha esse valor ao Pinterest como o ID do evento. Em seguida, o Pinterest usa esse ID para eliminar a duplicidade entre o evento do servidor que recebe da AppsFlyer e o evento da tag, para que a AppsFlyer conte a conversão uma vez.
>
> Se você não enviar af\_customer\_event\_id, a AppsFlyer gera um ID de evento automaticamente. Esse ID não corresponderá aos seus eventos da Tag.
>
> Para mais informações, consulte Integrar o SDK web da AppsFlyer.

5. Clique em **Adicionar evento** para adicionar um evento à lista.

<div data-zendesk-anchors="set-up-pinterest=configurar-a-integra%C3%A7%C3%A3o h_01KV339A5ZGK96JNCNR78PDMNH=configurar-a-integra%C3%A7%C3%A3o integration-tab=aba-integra%C3%A7%C3%A3o h_01KV339A67N4436STPW1VJR585=aba-integra%C3%A7%C3%A3o activate-partner=ativar-parceiro h_01KV339A67H0DSSJ3P84PXGQ2F=ativar-parceiro inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01KV339A68YZBZZ73T8XTBE6BR=configura%C3%A7%C3%B5es-de-eventos-in-app inapp-event-postbacks=aba-permiss%C3%B5es h_01KV339A6BN0CWYX7GCJ19RN0J=aba-permiss%C3%B5es" />
