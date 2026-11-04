---
title: >-
  Adquant by Kenshoo, parceiro de marketing do Apple Ads — configuração da
  campanha
metadata:
  keywords:
    - kenshoo
    - Advertisers
    - apple search ads
    - Agencies
    - adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2018-09-20T07:53:06Z'
  edited_at: '2026-09-16T00:26:05Z'
  id: 360001491269
  locale: pt
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/pt/articles/360001491269
---
> **Em resumo:** Otimize campanhas do Apple Ads usando o Adquant by Kenshoo. Quando configurado, o AppsFlyer envia postbacks para o Adquant.

<div id="enabling-sending-postbacks-to-adquant-apple-ads-marketing-partner" />

## Habilitando o envio de postbacks para o Adquant (parceiro de marketing do Apple Ads)

Tanto anunciantes quanto agências podem habilitar a atribuição para o Apple Ads.

<div id="note" />

> 📘 **Nota**
>
> Se o anunciante ou a agência desativar a atribuição para o Apple Ads, a atribuição para este aplicativo, incluindo o envio de postbacks para Parceiros de marketing do Apple Ads, será interrompida.

* **Anunciantes:** siga as instruções abaixo para habilitar a atribuição para o Apple Ads.
* **Agências:** <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#agency-setup">siga estas instruções</Anchor> para habilitar a atribuição para o Apple Ads.

<div id="configuring-adquant-by-kenshoo" />

### Configurar o Adquant by Kenshoo

**Para configurar o Adquant:**

1. Se necessário, ative **a integração do Apple Search Ads:**
   1. No AppsFlyer, no menu lateral, selecione **Collaboration** > **Partner Marketplace**.
   2. Procure e selecione o parceiro. Você é direcionado para a página de configuração do parceiro.
   3. Na aba **Integração**, clique em Ativar parceiro.
   4. Clique em **Salvar Integração**.
2. **No seu dashboard do Apple Ads**: obtenha o parâmetro Apple Ads Campaign Group ID relacionado ao Adquant. Use a captura de tela a seguir como um guia para localizar o ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **No AppsFlyer, configure o Adquant:**
   1. No AppsFlyer, no menu lateral, selecione **Collaborate** > **Partner Integrations.**
   2. Pesquise o parceiro de marketing do Apple Ads Adquant by Kenshoo.  
      A lista de parceiros de marketing é exibida.
   3. Selecione o parceiro de marketing do Apple Ads Adquant by Kenshoo.
   4. Habilite **Ativar parceiro.**
   5. Insira o **Apple Ads Campaign ID** do Adquant que você obteve na etapa anterior. Insira apenas os dígitos (números).
   6. Em **action\_identifier**, insira o domínio usado para a entrega do postback.
   7. [Opcional] **Não permita o compartilhamento da geolocalização do usuário:** para interromper o compartilhamento da geolocalização do usuário, em **Disable\_Country\_Sending** digite `1`.
   8. Clique em **Guardar**.

<div id="default-postbacks" />

### Postbacks padrão

Os postbacks exibidos são enviados automaticamente quando o parceiro é ativado.

<div id="configuring-in-app-events-postback" />

### Configuração do postback de eventos in-app

**Para configurar postbacks de eventos in-app:**

1. Insira o acion\_identifier.
2. Ative o **postback de eventos in-app**.
3. Clique em **Add Event** para adicionar um evento de SDK ou um evento servidor a servidor à lista.
4. Complete os seguintes parâmetros:

   

| Nome do parâmetro | A descrição |
| --- | --- |
| <span id="appsflyer-event"></span>**Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos S2S.<br />**Dica**: Não vê o evento que você está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado.</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**Mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">As configurações de mapeamento possíveis</Anchor> são:<ul><li>**Campo de texto:** Obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa dropdown:** Selecione o evento de parceiro predefinido mais adequado.</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem mapear o nome do evento.</li></ul> |
| <span id="for-users-from"></span>**para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Somente esse parceiro**: Envie postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que o executou o evento veio deste parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: Enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos - ou seja, o usuário que o executou veio de qualquer fonte de mídia.</li></ul> |
| <span id="including"></span>**Incluindo** | Selecione <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">quais dados do evento</Anchor> você deseja compartilhar com o parceiro no postback:<ul><li>**Sem valores e sem receita**: Envie apenas o evento em si, sem nenhum parâmetro (valores ou receita).</li><li>**Com valores e sem receita**: Envie todos os parâmetros, com **exceção** do valor da receita.</li><li>**Valores e receita**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li></ul> |

5. Clique em **Salvar integração**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-adquant-apple-search-ads-marketing-partner=habilitando-o-envio-de-postbacks-para-o-adquant-parceiro-de-marketing-do-apple-ads h_01HKW0AW61TW7TGPB4KX4XYVCB=habilitando-o-envio-de-postbacks-para-o-adquant-parceiro-de-marketing-do-apple-ads h_01HKW0AW61RDVXCB37PAFKAXW3=nota configuring-adquant-by-kenshoo=configurar-o-adquant-by-kenshoo h_01HKW0AW61QT8823TXVYB7JWTC=configurar-o-adquant-by-kenshoo default-postbacks=postbacks-padr%C3%A3o h_01HKW0AW61EKKGK1NSKBDXSDJC=postbacks-padr%C3%A3o configuring-inapp-events-postback=configura%C3%A7%C3%A3o-do-postback-de-eventos-in-app h_01HKW0AW6184ZH4H6JEJPBNXSH=configura%C3%A7%C3%A3o-do-postback-de-eventos-in-app" />
