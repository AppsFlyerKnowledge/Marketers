---
title: Configuração do SearchAds.com (da MobileAction)
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
  created_at: '2021-06-20T13:34:38Z'
  edited_at: '2026-09-16T00:26:13Z'
  id: 4402846897041
  locale: pt
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/pt/articles/4402846897041
---
> **Em resumo:** Otimize campanhas do Apple Ads usando o SearchAds.com da MobileAction. Quando configurado, o AppsFlyer envia postbacks para o SearchAds.com.

<div id="enabling-apple-ads-attribution" />

## Ativação da atribuição do Apple Ads

Para poder enviar postbacks para o SearchAds.com, primeiro ative a atribuição do Apple Ads. Isso pode ser feito pelo anunciante ou por uma agência.

<div id="note" />

> 📘 **Nota**
>
> Se o anunciante ou a agência desativar a atribuição do Apple Ads, os postbacks para o SearchAds.com e outros parceiros de marketing do Apple Ads serão interrompidos.

* **Anunciantes**: siga as instruções abaixo para ativar a atribuição do Apple Ads.
* **Agências**: <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#agency-setup">siga estas instruções</Anchor> para ativar a atribuição do Apple Ads.

<div id="setting-up-searchadscom-in-appsflyer" />

## Configurando o SearchAds.com no AppsFlyer

<div id="getting-required-information-from-searchadscom" />

### Como obter as informações necessárias do SearchAds.com

Antes de começar a configurar o SearchAds.com na AppsFlyer, obtenha sua **api\_key** e o **ID do grupo de campanhas do Apple Ads**.

* Para obter a api\_key, acesse o dashboard do SearchAds.com e clique em **Integrations** > **AppsFlyer**. No pop-up que se abrir, copie o ID. [![Chave de API do SearchAds.com](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)
* Para o ID do grupo de campanhas do Apple Ads: no **dashboard do Apple Ads,** obtenha o ID do grupo de campanhas do Apple Ads para o grupo de campanhas relevante:

  <Image align="center" alt="apple-search-ads-campaign-group-id.png" src="https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png" />

<div id="setting-up-campaigns-in-appsflyer" />

### Configuração de campanhas no AppsFlyer

**Para configurar o SearchAds.com:**

1. Se necessário, ative **a integração do Apple Search Ads:**
   1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Marketplace de parceiros**.
   2. Procure e selecione o parceiro. Você é direcionado para a página de configuração do parceiro.
   3. Na aba **Integração**, clique em Ativar parceiro.
   4. Clique em **Salvar Integração**.
2. **Na AppsFlyer, configure o SearchAds.com:**
   1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas.**
   2. Pesquise por SearchAds.com (da MobileAction).  
      A lista de parceiros é exibida.
   3. Selecione SearchAds.com (da MobileAction).
   4. Habilite **Ativar parceiro.**
   5. Insira a chave de API no campo **api\_key**.
   6. Insira o **ID da campanha do Apple Ads** do SearchAds.com. Insira apenas os dígitos (números).
   7. Clique em **Guardar**.

<div id="configuring-in-app-event-postbacks" />

#### Configuração dos postbacks de eventos in-app

**Para configurar o postback que deve ser enviado para a SearchAds.com após eventos in-app:**

1. Insira a **api\_key**.
2. Ative o **postback de eventos in-app**.
3. Selecione **Enviar todos os eventos**.
4. Em **Enviar receita**, selecione **Valores&Receita**.
5. Clique em **Salvar integração**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=ativa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-apple-ads h_01HKW0B2AZ40F0N9A7YYGTHCE0=ativa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-apple-ads h_01HKW0B2AZ411647BAS75M5BG6=nota setting-up-searchadscom-in-appsflyer=configurando-o-searchadscom-no-appsflyer h_01HKW0B2AZWC9AQBAYDWFPAKQN=configurando-o-searchadscom-no-appsflyer getting-required-information-from-searchadscom=como-obter-as-informa%C3%A7%C3%B5es-necess%C3%A1rias-do-searchadscom h_01HKW0B2AZ49R66CMJ747M485M=como-obter-as-informa%C3%A7%C3%B5es-necess%C3%A1rias-do-searchadscom setting-up-campaigns-in-appsflyer=configura%C3%A7%C3%A3o-de-campanhas-no-appsflyer h_01HKW0B2AZ419YS071HNXHPZXY=configura%C3%A7%C3%A3o-de-campanhas-no-appsflyer configuring-inapp-event-postbacks=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app h_01HKW0B2AZ4GHJE5SQHB3ZSZ8D=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app" />
