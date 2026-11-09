---
title: Bidalgo - Google Ads — Configuração de campanha
metadata:
  keywords:
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
  created_at: '2018-07-19T11:46:44Z'
  edited_at: '2026-08-19T00:28:23Z'
  id: 360001325405
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/360001325405
---
> **Visão geral:** Bidalgo, parceira integrada da AppsFlyer, é uma provedora líder de soluções de inteligência artificial para ajudar profissionais de app marketing a escalar seu Growth.

<div id="set-up-bidalgo-integration" />

## Configurar a integração com a Bidalgo

**Pré-requisitos:** Antes de criar uma integração, certifique-se de entrar em contato com o parceiro e abrir uma conta com ele.

**Nova integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Selecione o aplicativo correspondente.
3. Procure a Bidalgo e selecione **Integrate**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Mantenha-a ativada enquanto você trabalhar com a Bidalgo.
5. Configure as demais abas conforme necessário abaixo.

**Editar integração existente:**

**Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.

<div id="note" />

> 📘 **Nota**
>
> O ID de cliente do Google Ads deve ser inserido **sem** hífens.

6. Na sua conta do **Google Ads**, copie o ID de cliente (sem hífens) no canto superior esquerdo e cole-o no parâmetro **Ads Customer ID** da AppsFlyer, conforme mostrado nas capturas de tela a seguir.

<Image align="center" alt="" src="https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png" />

7. Insira o número no campo **ID de cliente do Google Ads**.

<div id="in-app-events" />

### https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg

1. Para enviar postbacks de eventos in-app para a Bidalgo, alterne a opção In-App Events Postback para **ON**.

2. Adicione individualmente os eventos in-app que você deseja enviar para a Bidalgo e mapeie-os para o campo **Partner Event Identifier**.

3. Selecione **Send Revenue** para enviar todos os parâmetros, incluindo o valor da receita (caso exista no evento).

4. Clique em **Guardar**.

<div id="important-note" />

> 📘 **Observação importante**
>
> * Desativar a atribuição do Google Ads impede o envio de postbacks para Parceiros do Google Ads.
> * Você pode configurar várias contas do Google Ads (CID) para enviar postbacks (etapa 5), separando cada CID com uma vírgula.

<div data-zendesk-anchors="set-up-bidalgo-integration=configurar-a-integra%C3%A7%C3%A3o-com-a-bidalgo h_01HKA1JNXMRJ8059FAJAEQ6RK5=configurar-a-integra%C3%A7%C3%A3o-com-a-bidalgo h_01HKA1JNXM5R15CBVQ2WHT99Z9=nota inapp-events=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HKA1JNXM59W74725961FZA27=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HKA1JNXMASTQ9X2144JCKKNQ=observa%C3%A7%C3%A3o-importante" />
