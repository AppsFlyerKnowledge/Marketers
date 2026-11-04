---
title: Configuração da campanha do Baidu mDSP Ads (Baiyi)
metadata:
  keywords:
    - Advertisers
    - Baidu mDSP
    - Baiyi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-24T07:22:04Z'
  edited_at: '2026-09-16T00:26:23Z'
  id: 115004330446
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115004330446
---
> **Visão geral:** o Baidu mDSP Ads (Baiyi), um parceiro integrado de ad network da AppsFlyer, é um provedor de soluções de publicidade e faz parte da Baidu, o mecanismo de busca dominante na China, com mais de 70% de participação de mercado.

<div id="setting-up-baidu-mdso-ads-baiyi" />

## Configuração do Baidu mDSP Ads (Baiyi)

1. No AppsFlyer, no menu lateral, selecione **Colaborar** **> Integrações de Parceiros** > **Marketplace de Parceiros**.
2. Pesquise o parceiro e selecione-o. Você é direcionado para a página de configuração da integração.

A janela de configuração do Baidu mDSP Ads (Baiyi) inclui 2 abas ativas: Integração e link de atribuição. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita**, você deve ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Baidu mDSP Ads (Baiyi) após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

![baidu-mdsp-default-postbacks.png](https://files.readme.io/fdde731527468b9837efa2230c5416f3393024b8c4eec8b44339086a2f31b984-360002069005.png)

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Baidu mDSP Ads (Baiyi) por meio de postbacks.

![baidu-mdsp-in-app-events.png](https://files.readme.io/fa515fac11e82be11bb55bb9b198ac63681ecdb713f0f6537f4ca7bf0c60e5b1-360002069085.png)

1. Ative a opção Postbacks de eventos in-app.
2. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
3. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no Baidu mDSP Ads (Baiyi).  <br />Obtenha o ID de evento correspondente no Baidu mDSP Ads (Baiyi) e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Baidu mDSP Ads (Baiyi) para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais do Baidu mDSP Ads (Baiyi). Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Baidu mDSP Ads (Baiyi).  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Baidu mDSP Ads (Baiyi).  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos, dentro de campanhas específicas do Baidu mDSP Ads (Baiyi).  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para obter mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição do AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao Baidu mDSP Ads (Baiyi).

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

![baidu-mdsp-click-through.png](https://files.readme.io/19f6616cc1e62ec8888a72625ce936acdb6e8e63e4a4cd4273cdc99fd2297a93-360002075089.png)

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para o Baidu mDSP Ads (Baiyi) para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para o Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para o Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

A configuração de permissões não está disponível para o Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="create-conversion-rule-at-baidu-mdsp-ads" />

## Criar regra de conversão no Baidu mDSP Ads

Faça login no Baidu mDSP Ads em http://baiyi.baidu.com/ e acesse **Tool** >> **Apps**:

![mDSP_4.png](https://files.readme.io/90f99229f6bffe9b9edbf0469f9b4e66ca9c5c55184eb542e250ef6a9bd76aee-115014006086.png)

Clique em **Criar novo aplicativo**.

![mDSP_5.png](https://files.readme.io/c034e3238fbd6021fefc44ff8b1cf8b4d39c3f9043b02074c3bdccce2747ac48-115014006106.png)

Insira todas as informações relevantes nos campos.

Adicione o link de atribuição do AppsFlyer **na caixa URL de feedback**:

![mDSP_6.png](https://files.readme.io/6692275131ee49b62febcb558457f7f1a1fbd167f3d3f61d976e1cb248a61388-115014006906.png)

***OBSERVAÇÃO***: para aplicativos iOS, adicione o aplicativo inserindo o **Appid**. Para aplicativos Android, adicione o aplicativo de duas maneiras:  
1. Conectar-se ao aplicativo que você enviou para a plataforma de desenvolvedores da Baidu ([http://app.baidu.com/](http://app.baidu.com/)) ou  
2. Inserindo a página de download do APK ou fazendo upload do APK nela.

Em seguida, clique no botão de envio no final da página.

**2. Criar anúncios de promoção de aplicativo no Baidu mDSP Ads**.

Clique em **Gerenciamento de campanhas** >> **Criar nova campanha**:

![mDSP_7.png](https://files.readme.io/aab8866a1969e403247c97018aae1d65d456ce4e261412035ef91a1862f509b9-115014006926.png)

Na seção **2. Configurar unidade de anúncio** >> Acesse **Objetivos**, escolha instalação do aplicativo >> Preencha as demais informações relacionadas e envie a campanha de anúncio para verificação:

![mDSP_8.png](https://files.readme.io/da064e6811b4c749a20757d711186dc705070629887cdf2e7b514cc17274af75-115014006946.png)

<div data-zendesk-anchors="setting-up-baidu-mdso-ads-baiyi=configura%C3%A7%C3%A3o-do-baidu-mdsp-ads-baiyi h_01HKW6TN4YBTMR1ZDH77D7SK7N=configura%C3%A7%C3%A3o-do-baidu-mdsp-ads-baiyi h_01HKW6TN4YM927W1VAKNWFQ0SJ=integration-tab activate-partner=ativar-parceiro h_01HKW6TN4Y4EXABZTJ2VE4QRTK=ativar-parceiro inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6TN4YYDKNGCSJB4MARK52=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6TN4Y2D2K419172AZJXR6=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6TN4YQTMGSMPGR01FR658=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6TN4Y9ZP7SXMTD0XGNPGV=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6TN4Y5A1PT6RCVCFYRG9Q=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6TN4Z02V726B7379TMBC0=cost-tab h_01HKW6TN4Z01YZWHMGF5N1KC50=ad-revenue-tab h_01HKW6TN4Z3KCEFDW9YA2A2BZV=permissions-tab create-conversion-rule-at-baidu-mdsp-ads=criar-regra-de-convers%C3%A3o-no-baidu-mdsp-ads h_01HKW6TN4ZWEA7683C8MFAT4AY=criar-regra-de-convers%C3%A3o-no-baidu-mdsp-ads" />
