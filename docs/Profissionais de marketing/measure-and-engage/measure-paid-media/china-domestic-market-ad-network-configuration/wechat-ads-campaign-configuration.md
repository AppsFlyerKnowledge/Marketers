---
title: Configuração da campanha de anúncios no WeChat
metadata:
  keywords:
    - Wechat Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-06-18T06:41:29Z'
  edited_at: '2026-09-16T00:26:57Z'
  id: 115003044106
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115003044106
---
> **Em resumo:** Saiba como mensurar suas campanhas com o WeChat na AppsFlyer.

## Introdução

O WeChat, um dos parceiros integrados da AppsFlyer, é um aplicativo chinês multifuncional de mensagens, rede social e pagamento mobile desenvolvido pela Tencent.

Para configurar suas campanhas com o WeChat, siga as etapas abaixo.

## Configurar sua campanha no WeChat

Antes de prosseguir com a integração do WeChat na AppsFlyer, configure a campanha no WeChat.

No WeChat, faça o seguinte:

1. Preencha e verifique a chave da Tencent
2. Escolha o tipo de conversão na lista:

   * não relacionada
   * Registro
   * Compras
   * Adicionar ao carrinho

   Atenção: o WeChat permite apenas um destino de conversão por aplicativo.
3. Insira a [URL de atribuição de clique](#attribution-link-tab) da AppsFlyer

![wechat-configuration.png](https://files.readme.io/228ee10ef3dc113ae8af8de0f283b144206db1857f6d1f9169355f294155b8f8-50900431174033.png)

Depois de inserir essas informações, confirme-as clicando no botão destacado. Na próxima etapa, você receberá a *encrypt\_key* e a *sign\_key*:

![wechat-keys.png](https://files.readme.io/cd7a2406ae9981eaabb4089813c9a1b847f0e6f750b9c0c0a0ac5e726dfe44be-50900431177361.png)

Copie as chaves e use-as ao configurar a campanha na AppsFlyer.

### Configurar campanha do WeChat como agência

As agências têm diferentes tipos de conta no WeChat. Dependendo do tipo de conta, algumas agências podem criar metas de conversão, e outras não.

Se sua conta permitir criar uma meta de conversão, você poderá prosseguir seguindo as instruções acima.

Se você não tiver permissão para criar uma meta de conversão, poderá ver no WeChat uma meta criada por outra conta que gerencia o mesmo aplicativo. Nesse caso, peça ao anunciante que forneça o *encrypt\_key* e o *sign\_key* e use-os para configurar a campanha na AppsFlyer.

## Configuração do WeChat na AppsFlyer

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace.Para editar**: na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   **Atenção importante:** O botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o parceiro**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do WeChat inclui 4 guias: Integração, Link de atribuição, Enriquecimento de dados e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Nota**
>
> Como uma all-installs network, o WeChat prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, incluindo orgânica. Recomenda-se selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação ao WeChat.

### Configurações gerais

**ID do parceiro**

O WeChat se conecta à AppsFlyer por meio de três parâmetros exclusivos:

1. ID de assinatura
2. ID do aplicativo WeChat
3. Chave de criptografia

Se você ainda não tiver o Sign ID, o WeChat App ID e a Encrypt Key, deverá obtê-los do WeChat para continuar com a integração.

<Image alt="wechat-integration-general-settings.png" src="https://files.readme.io/f1e0675a26116b628629b07616a7b9b86e8413ee36d7504f415207cb1590cb82-50900431178001.png" width="390px" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos ao WeChat após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

![wechat-default-postbacks.png](https://files.readme.io/1a2703b97a71bf82bcc77f5393459bc94b5443b83a4c4965d2624eda0e9f166f-50900402778129.png)

Selecione **Somente eventos** **atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao WeChat.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada ao WeChat.

### Configurações de eventos in-app

Nesta seção, você pode mapear os eventos da AppsFlyer com o WeChat por meio de postbacks.

![wechat_in_app_event_postbacks.png](https://files.readme.io/cd6234df4809b27044e361ad8835d4ae92100c491e0aa7c8f003336cdf2ad49d-50900431180561.png)

1. Insira a Encrypt Key novamente.
2. Insira o Sign ID
3. Insira o ID do aplicativo WeChat
4. Mude o botão Postbacks do evento in-app para ATIVO
5. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
6. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
7. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento conforme definido pelo WeChat.  <br />Obtenha o ID do evento correspondente do WeChat e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado ao parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se ele existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao WeChat para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais do WeChat. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o WeChat.  
  **Parâmetro do link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do WeChat.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos em campanhas específicas do WeChat.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder os limites do ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas ao WeChat.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

[![](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)](https://files.readme.io/86114a765dea30da658a676d1a7506c6ba385bdf8ebcf7241a1ce85f8c413077-50900402782737.png)

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o ao WeChat para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Ative a integração de custos da Tencent para receber dados de custo do WeChat.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nenhuma configuração de permissão está disponível para este parceiro.

</Accordion>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HKW6Z36NGCWC0R6EQX49S34J=introdu%C3%A7%C3%A3o setting-up-your-campaign-on-wechat=configurar-sua-campanha-no-wechat h_01HKW6Z36NTSGCDQM553YMHHDH=configurar-sua-campanha-no-wechat setting-up-wechat-campaign-as-an-agency=configurar-campanha-do-wechat-como-ag%C3%AAncia h_01HKW6Z36N8S8KSBNMR8A54RRN=configurar-campanha-do-wechat-como-ag%C3%AAncia setting-up-wechat-on-appsflyer=configura%C3%A7%C3%A3o-do-wechat-na-appsflyer h_01HKW6Z36N3JSYEWJZH74M5WWJ=configura%C3%A7%C3%A3o-do-wechat-na-appsflyer h_01HKW6Z36PDGTT3EERY8F4VA79=integration-tab activate-partner=ativar-parceiro h_01HKW6Z36P0EQF829NW3GDXKEN=ativar-parceiro h_01HKW6Z36P806MHV6N3D1N9HW3=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW6Z36P51EG4BW7WA3JGSKN=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW6Z36P3D4EPKC6ZZK94YVF=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6Z36PA90WEJMFH7BZMD72=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6Z36PRBT2X6F5BHYW06E1=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6Z36P73H79MVFXQ29K2M6=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6Z36P95C7CT1J6YS5CQN8=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6Z36PEAPM8RAKB0RM9RES=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6Z36PEG0T9WQQRNY19EVG=cost-tab h_01HKW6Z36WE1SDC7KZHCMTPA0T=ad-revenue-tab h_01HKW6Z36W6QKR583X4Q4BNBZ4=permissions-tab" />
