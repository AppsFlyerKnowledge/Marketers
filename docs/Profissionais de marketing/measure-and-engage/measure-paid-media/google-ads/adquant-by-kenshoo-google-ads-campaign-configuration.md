---
title: Adquant by Kenshoo - Configuração da campanha no Google Ads
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Kenshoo
    - Adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-12-09T07:43:55Z'
  edited_at: '2026-08-19T00:28:20Z'
  id: 360000654357
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/360000654357
---
> **Visão geral:** Otimize campanhas do Google Adwords usando o Adquant by Kenshoo. Quando configurado, o AppsFlyer envia postbacks para o Adquant.

<div id="setting-up-adquant-by-kenshoo" />

## Configuração do Adquant by Kenshoo

**Pré-requisitos:** Antes de criar uma integração, certifique-se de entrar em contato com o parceiro e abrir uma conta com ele.

**Nova integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Selecione o aplicativo correspondente.
3. Procure por Adquant by Kenshoo e selecione **Integrar**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Mantenha essa opção ativada enquanto você trabalhar com o Adquant by Kenshoo.
5. Configure as abas restantes conforme necessário abaixo.

**Editar integração existente:**

**Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.

<div id="note" />

> 📘 **Nota**
>
> O ID do cliente do Google Ads deve ser inserido **sem** hifens.

6. Na sua conta do **Google Ads**, copie o ID do cliente (sem hifens) do canto superior esquerdo e cole-o no parâmetro **Ads Customer ID** da AppsFlyer, conforme mostrado nas capturas de tela abaixo.

<Image align="center" alt="" src="https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png" />

7. Insira o **Action Identifier**, o **Disable\_Country\_Sending** (fornecido pela Adquant) e o número do **Google Ads Customer ID** nos campos apropriados.

<div id="in-app-events" />

### https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg

1. Para enviar postbacks de eventos in-app para o Adquant by Kenshoo, alterne In-App Events Postback para **ON**.

2. Adicione individualmente os eventos in-app que você deseja enviar para o Adquant by Kenshoo e mapeie-os para o campo **Partner Event Identifier**.

3. Selecione **Send Revenue** para enviar todos os parâmetros, incluindo o valor da receita (caso exista no evento).

4. Clique em **Salvar**.

<div id="important-note" />

> 📘 **Observação importante**
>
> * Desativar a atribuição do Google Ads impede o envio de postbacks para os parceiros do Google Ads.
> * Você pode configurar várias contas do Google Ads (CID) para enviar postbacks (etapa 5), separando cada CID com uma vírgula.

<div data-zendesk-anchors="setting-up-adquant-by-kenshoo=configura%C3%A7%C3%A3o-do-adquant-by-kenshoo h_01HKA1JQRK5BVGW13P72YEXZT7=configura%C3%A7%C3%A3o-do-adquant-by-kenshoo h_01HKA1JQRKGDMZHTVSPVDSV463=nota inapp-events=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HKA1JQRK4YNEXKAHVBYP3EC1=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HKA1JQRKZJJ4RXCCVSS1BG7Z=observa%C3%A7%C3%A3o-importante" />
