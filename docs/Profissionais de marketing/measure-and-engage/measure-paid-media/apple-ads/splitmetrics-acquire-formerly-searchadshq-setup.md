---
title: Configuração do SplitMetrics Acquire (antigo SearchAdsHQ)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-15T08:21:04Z'
  edited_at: '2026-09-16T00:26:15Z'
  id: 360002249257
  locale: pt
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/pt/articles/360002249257
---
> **Em resumo:** Otimize campanhas do Apple Ads usando o SplitMetrics Acquire. Quando configurado, o AppsFlyer envia postbacks para o SplitMetrics Acquire.

<div id="enabling-apple-ads-attribution" />

## Ativando a atribuição do Apple Ads

Tanto anunciantes quanto agências podem ativar a Atribuição para o Apple Ads.

<div id="note" />

> 📘 **Nota**
>
> Se o anunciante ou a agência desativar a atribuição para o Apple Ads, a atribuição para este aplicativo, incluindo o envio de postbacks para Parceiros de Marketing do Apple Ads, será interrompida.

* **Anunciantes**: siga as instruções abaixo para ativar a atribuição para o Apple Ads.
* **Agências**: <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#agency-setup">siga estas instruções</Anchor> para ativar a atribuição para o Apple Ads.

<div id="setting-up-splitmetrics-acquire-on-appsflyer" />

## Configurando o SplitMetrics Acquire na AppsFlyer

<div id="getting-required-information-from-splitmetrics-acquire" />

### Como obter as informações necessárias no SplitMetrics Acquire

Antes de começar a configurar o SplitMetrics Acquire na AppsFlyer, obtenha seu **client\_id** e o **ID do grupo de campanhas do Apple Ads**.

* Para o client\_id, acesse o dashboard do SplitMetrics Acquire e clique em **Integrations** > **AppsFlyer**. No pop-up que será aberto, copie o ID.
* Para o ID do grupo de campanhas do Apple  Ads Campaign Group ID: **No dashboard do Apple Ads,** obtenha o parâmetro ID do grupo de campanhas do Apple Ads relacionado ao SplitMetrics Acquire. Use a captura de tela a seguir como um guia para localizar o ID.  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

<div id="setting-up-campaigns-on-appsflyer" />

### Configurando campanhas na AppsFlyer

**Para configurar um SplitMetrics Acquire:**

1. **Na AppsFlyer, configure o SplitMetrics Acquire:**
   1. Na AppsFlyer, no menu lateral, selecione **Collaboration** > **Integrações de parceiros** > **Integrações ativas.**
   2. Procure por SplitMetrics Acquire.  
      A lista de parceiros é exibida.
   3. Selecione SplitMetrics Acquire.
   4. Habilite **Ativar parceiro.**
   5. Insira o ID do cliente no campo **client\_id**.
   6. Insira o **ID do grupo de campanhas do Apple Ads** do SplitMetrics Acquire que você obteve na etapa anterior. Insira apenas os dígitos (números).
   7. Clique em **Guardar**.
2. Se quiser registrar atribuições do Apple Ads, ative também a **integração do Apple Ads:**
   1. Na AppsFlyer, no menu lateral, selecione **Collaboration** > **Integrações de parceiros** > **Partner Marketplace**.
   2. Procure e selecione o parceiro. Você é direcionado para a página de configuração do parceiro.
   3. Na aba **Integração**, clique em Ativar parceiro.
   4. Clique em **Salvar Integração**.

<div id="configuring-in-app-event-postbacks" />

#### Configuração dos postbacks de eventos in-app

**Para configurar o postback que deve ser enviado ao SplitMetrics Acquire após eventos in-app:**

1. Digite o client\_id.
2. Ative o **postback de eventos in-app**.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

   

| Nome do parâmetro | A descrição |
| --- | --- |
| SDK Event Name (Nome do evento do SDK) | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado no aplicativo ou por meio de eventos de servidor para servidor. **Dica:** não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| Send Revenue (Enviar receita) | Selecione uma das seguintes opções: Sem valores e sem receita, Valores & sem receita ou Valores & receita. |

5. Clique em **Salvar integração**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=ativando-a-atribui%C3%A7%C3%A3o-do-apple-ads h_01HBB5JWBAZMD5BHPGQYHYQY0Q=ativando-a-atribui%C3%A7%C3%A3o-do-apple-ads h_01HBB5JWBA612TQV90K56H319J=nota setting-up-searchadshq-on-appsflyer=configurando-o-splitmetrics-acquire-na-appsflyer h_01HBB5JWBA6QPV3ZN0FCBK0BHR=configurando-o-splitmetrics-acquire-na-appsflyer getting-required-information-from-searchadshq=como-obter-as-informa%C3%A7%C3%B5es-necess%C3%A1rias-no-splitmetrics-acquire h_01HBB5JWBA6CGAAQAA9DZ4XMNS=como-obter-as-informa%C3%A7%C3%B5es-necess%C3%A1rias-no-splitmetrics-acquire setting-up-campaigns-on-appsflyer=configurando-campanhas-na-appsflyer h_01HBB5JWBAMHKBAMQD4TTQSZ0H=configurando-campanhas-na-appsflyer configuring-inapp-event-postbacks=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app h_01HBB5JWBBHMKT3Z9JKEQJAZZ7=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app" />
