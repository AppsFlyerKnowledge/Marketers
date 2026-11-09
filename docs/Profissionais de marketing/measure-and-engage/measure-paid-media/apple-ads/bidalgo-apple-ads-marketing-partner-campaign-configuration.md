---
title: Parceiro de marketing da Bidalgo para Apple Ads — configuração da campanha
metadata:
  keywords:
    - Apple Search Ads
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-26T10:33:54Z'
  edited_at: '2026-09-16T00:26:11Z'
  id: 360001340429
  locale: pt
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/pt/articles/360001340429
---
> **Em resumo:** Otimize campanhas do Apple Ads usando a Bidalgo. Quando configurado, a AppsFlyer envia postbacks para a Bidalgo.

<div id="enabling-sending-postbacks-to-bidalgo-apple-ads-marketing-partner" />

## Ativar o envio de postbacks para a Bidalgo (parceiro de marketing do Apple Ads)

<div id="note" />

> 📘 **Nota**
>
> Se o anunciante ou a agência desativar a atribuição para o Apple Ads, a atribuição para este aplicativo, incluindo o envio de postbacks para parceiros de marketing do Apple Ads, é interrompida.

Tanto anunciantes quanto agências podem habilitar a atribuição para Apple Ads.

* **Anunciantes:** sigam as instruções abaixo sobre como habilitar a atribuição para o Apple Ads.
* **Agências:** <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#agency-setup">siga estas instruções</Anchor> para habilitar a atribuição para Apple Ads.

<div id="configuring-bidalgo" />

### Configurando a Bidalgo

**Para configurar a Bidalgo:**

1. Se necessário, ative **a integração do Apple Search Ads:**
   1. No AppsFlyer, no menu lateral, selecione a guia **Collaboration** > **Partner Integrations > Partner Marketplace** tab.
   2. Procure e selecione o parceiro. Você é direcionado para a página de configuração do parceiro.
   3. Na aba **Integração**, clique em Ativar parceiro.
   4. Clique em **Salvar Integração**.
2. **No seu dashboard do Apple Ads**: obtenha o parâmetro de ID do Grupo da Campanha do Apple Ads relacionado à Bidalgo. Use a captura de tela a seguir como um guia para localizar o ID.

   <Image align="center" alt="ASACGroupID.png" src="https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png" />
3. **Na AppsFlyer, configure a Bidalgo:**
   1. Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações ativas**.
   2. Pesquise por Bidalgo – parceiro de marketing do Apple Ads.  
      A lista de parceiros é exibida.
   3. Selecione Bidalgo – parceiro de marketing do Apple Ads.
   4. Habilite **Ativar parceiro.**
   5. Insira o **ID da Campanha do Apple Ads** da Bidalgo que você obteve na etapa anterior. Insira apenas os dígitos (números).
   6. Clique em **Guardar**.

<div id="default-postbacks" />

### Postbacks padrão

Instalações e reengajamentos são enviados automaticamente quando o parceiro é ativado.

<div id="configuring-in-app-events-postbacks" />

### Configuração dos postbacks de eventos in-app

**Para configurar postbacks de eventos in-app:**

1. Ative o **postback de eventos in-app**.
2. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
3. Complete os seguintes parâmetros:

   

| Nome do parâmetro | A descrição |
| --- | --- |
| SDK Event Name (Nome do evento do SDK) | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado no aplicativo ou por meio de eventos de servidor para servidor. **Dica:** não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| Send Revenue (Enviar receita) | Selecione uma das seguintes opções: Sem valores e sem receita, Com valores e sem receita ou Com valores e com receita. |

4. Clique em **Salvar Integração**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-bidalgo-apple-search-ads-marketing-partner=ativar-o-envio-de-postbacks-para-a-bidalgo-parceiro-de-marketing-do-apple-ads h_01HKW0AZ05126SWNF374821AAH=ativar-o-envio-de-postbacks-para-a-bidalgo-parceiro-de-marketing-do-apple-ads h_01HKW0AZ05SXCVY0M3M7R07KG6=nota configuring-bidalgo=configurando-a-bidalgo h_01HKW0AZ06QFMYPJF95XQRAK99=configurando-a-bidalgo default-postbacks=postbacks-padr%C3%A3o h_01HKW0AZ06SPXE8K9JQN60B8T2=postbacks-padr%C3%A3o configuring-inapp-events-postbacks=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app h_01HKW0AZ06F0169D59AWKQJN87=configura%C3%A7%C3%A3o-dos-postbacks-de-eventos-in-app" />
