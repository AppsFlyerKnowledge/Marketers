---
title: Integração da Luna Labs com a AppsFlyer
metadata:
  keywords:
    - postbacks
    - integrated partner
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-08-19T00:11:21Z'
  id: 360019465017
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360019465017
---
> **Em resumo:** a Luna Labs é uma plataforma completa que permite que seus clientes criem, gerenciem e otimizem playables e anúncios em vídeo.

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configurando a Luna Labs

**Pré-requisito:** Antes de configurar a integração, certifique-se de contactar o parceiro e abrir uma conta com eles.

**Nova integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Selecione o aplicativo correspondente.
3. Procure a Luna Labs e selecione **Integrar**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    Mantenha essa opção ativada enquanto você trabalhar com a Luna Labs.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

**Editar integração existente:**

**Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.

## integração

Use a aba Integração para a configuração. As abas restantes estão inativas.

> 📘 **Nota**
>
> A Luna Labs não usa links de atribuição próprios. Eles recebem postbacks de ad networks que executam campanhas com anunciantes. A Luna Labs recebe postbacks apenas para os próprios criativos e somente postbacks que incluem o parâmetro `af_addpb=1` e o respetivo valor. Veja mais detalhes abaixo.

### Ativar parceiro

No **primeiro acesso**, você precisa ativar **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. **A opção deve permanecer ativada enquanto você trabalhar com o parceiro**.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação/desativação de parceiros</Anchor>.

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a Luna Labs após instalações de usuários.

**Observação:** a Luna Labs pode receber postbacks apenas para os próprios criativos.

**Para enviar postbacks para a Luna Labs:**

1. Verifique se a ad network com a qual você trabalha em conjunto com a Luna Labs está ativada e integrada à AppsFlyer.
2. Verifique se a ad network adiciona o parâmetro `af_addpb=1` ao link de atribuição enviado à AppsFlyer e à Luna Labs pela ad network.  
   Esse parâmetro permite enviar o postback para a Luna Labs e informa que o clique veio do criativo deles.
3. Selecione **Eventos atribuídos a qualquer parceiro ou orgânico**.

Por exemplo, se a ad-network-X estiver trabalhando com determinado aplicativo (id1234567890) e quiser enviar postbacks para a Luna Labs, a URL deverá ser semelhante a esta:

```http
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```

<div data-zendesk-anchors="h_01H9FKCW1FJ2QCVVE6HEE640H9=importante setting-up-luna-labs=configurando-a-luna-labs h_01HJR5M5C0P759S4X5SSJCY501=configurando-a-luna-labs integration=integra%C3%A7%C3%A3o h_01H9FKCW1FE6JCY5FAFF3Y4TGH=integra%C3%A7%C3%A3o h_01H9FKCW1FNPCF1M7SRWTMNDCW=nota activate-partner=ativar-parceiro h_01H9FKCW1FV00605GYK498JZN9=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01H9FKCW1FGMA3FKAY5B9YCJVH=postbacks-padr%C3%A3o" />
