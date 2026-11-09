---
title: Configuração dos parceiros de marketing do Snapchat
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
  created_at: '2022-01-24T08:47:31Z'
  edited_at: '2026-09-16T00:30:13Z'
  id: 4417694142481
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/4417694142481
---
> **Em resumo:** Integre-se aos parceiros de marketing do Snapchat para medir as campanhas que você executa com eles. Quando configurado, o AppsFlyer envia postbacks para o parceiro de marketing do Snapchat configurado.

<div id="setting-up-a-snapchat-marketing-partner" />

## Configuração de um parceiro de marketing do Snapchat

Siga as etapas abaixo para configurar suas campanhas com qualquer um dos parceiros de marketing do Snapchat.

* Ative a <Anchor target="_blank" href="/marketers/pt/docs/snapchat-advanced-srn-integration-setup">atribuição do Snapchat</Anchor>.
* No dashboard do Snapchat **Business Manager**, copie o **Snap Account ID** destacado abaixo em verde.

  <Image align="center" alt="snapchat-dashboard.png" src="https://files.readme.io/a0942bd27528d4a837edc6eb5d11338bf0622ddc42e382231a8f210aedad1424-50902448760337.png" />

Depois de ativar o Snapchat e obter o Snap Account ID, configure o parceiro de marketing:

1. No AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações de parceiros** > **Integrações ativas.**
2. Na caixa de pesquisa, insira o nome do parceiro específico ou "Snapchat" para ver a lista completa de parceiros de marketing do Snapchat.
3. Clique no logotipo do parceiro necessário para abrir a janela de configuração.
4. Ative **Activate partner**.
5. Cole o **Snap account ID** obtido no dashboard do Snapchat (com os hífens) no campo **Snap Account ID**.
6. Clique em **Guardar**.

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos de instalação e reengajamento aos parceiros. Use esta seção para definir a **fonte dos usuários** que permitem enviar esses postbacks. Em alguns casos, a fonte dos usuários é predefinida e não pode ser alterada:

<Image align="center" alt="remerge2.png" src="https://files.readme.io/4f3f52b3610b3e3bcf0adc6e963f1f2c39cdb0b2de27569c890844aac477b3d0-50902448761873.png" />

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos a este parceiro.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para que toda a sua base de usuários fique disponível para ser reportada a este parceiro.

<div id="in-app-events" />

### https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg

1. Para enviar postbacks de eventos in-app ao parceiro de marketing do Snapchat que você está configurando, alterne o In-App Events Postback para **ON**.
2. Adicione individualmente os eventos in-app (eventos de SDK) que você deseja enviar ao parceiro e <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">mapeie-os conforme necessário.</Anchor>

<div id="important" />

> 🚧 **Importante!**
>
> Desabilitar a atribuição do Snapchat impede o envio de postbacks aos parceiros de marketing do Snapchat.

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-snapchat">Interoperação Snapchat e AppsFlyer SKAdNetwork</Anchor>

<div data-zendesk-anchors="setting-up-a-snapchat-marketing-partner=configura%C3%A7%C3%A3o-de-um-parceiro-de-marketing-do-snapchat h_01HDNZAAS11ADG02FXNPSYYH69=configura%C3%A7%C3%A3o-de-um-parceiro-de-marketing-do-snapchat default-postbacks=postbacks-padr%C3%A3o h_01HDNZAAS1M2317CKQ13SP11KM=postbacks-padr%C3%A3o inapp-events=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HDNZAAS1JZPHS32PNFFCR12A=httpssupportappsflyercomhcarticle_attachments19284078965009 h_01HDNZAAS1PRWK6EVQTTV3YNQM=importante h_01HDNZBZARD9E54VAFVSRQFWEH=consulte-tamb%C3%A9m" />
