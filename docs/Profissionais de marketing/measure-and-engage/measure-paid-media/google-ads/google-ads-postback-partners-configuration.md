---
title: Configuração de parceiros de postback do Google Ads
metadata:
  keywords:
    - postbacks
    - Integration
    - Advertisers
    - Agencies
    - google ads
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
  created_at: '2021-11-16T09:36:56Z'
  edited_at: '2026-08-19T00:28:48Z'
  id: 4411047077905
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/4411047077905
---
> **Visão geral:** habilite parceiros de postback do Google Ads para ajudar a executar suas campanhas do Google Ads.

Alguns parceiros (por exemplo, Bidalgo, Adquant), chamados de **Parceiros de postback do Google Ads**, são semelhantes às agências. Eles ajudam os seus clientes que são anunciantes a veicular campanhas do Google Ads, mas precisam receber postbacks para conversões do Google Ads.

Esses parceiros de postback do Google Ads (GAPPs - Google Ads Postback Partners) também podem coletar postbacks de instalações do Google Ads adquiridas diretamente pelo anunciante ou até mesmo por outras agências (consulte [Casos de uso](/docs/google-ads-postback-partners-configuration#casos-de-uso-de-parceiros-de-postback-do-google-ads)). Usando as informações dos postbacks, os GAPPs são capazes de otimizar as campanhas do Google Ads para o aplicativo.

<div id="important" />

> 🚧 **Importante!**
>
> Os parceiros de postback do Google Ads **NÃO** são atribuídos a instalações ou eventos na AppsFlyer.

O anunciante precisa de uma conta ativa do Google Ads <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">configurada</Anchor> na AppsFlyer, além de ter que configurar o GAPP específico na AppsFlyer para permitir o envio de postbacks para ele.

Outros GAPPs integrados com a AppsFlyer: Blackbox, Appreciate, Marin Software, Miramedia, Mpbisummer, Protonads, Springrain.

<div id="google-ads-postback-partner-setup" />

## Configuração do parceiro de postback do Google Ads

1. Na AppsFlyer, vá para o menu lateral e selecione**colaborar**>**integrações ativas**.

2. Digite o nome do GAPP com o qual você gostaria de trabalhar na caixa de pesquisa e selecione-o na lista suspensa.

<div id="tip" />

> 👍 **Dica**
>
> Insira "Google Ads" no campo de parceiros integrados para receber a lista de GAPPs.

3. Clique no GAPP necessário para abrir sua configuração de integração.

4. Na sua conta do **Google Ads**, copie o ID do cliente (sem hifens):

![](https://files.readme.io/7afd536d06b1aca68744a83925ecac86fcef4cc47225826af20120f128da004f-21414601345681.png)

5. Cole o número no campo **ID de cliente do Google Ads**.

6. Configure a seção <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Postback de eventos in-app.</Anchor>

7. Clique em **Salvar**.

<div id="important-notes" />

> 📘 **Observações importantes**
>
> * Desativar a atribuição do Google Ads também impede o envio de postbacks para GAPPs.
> * Você pode configurar várias contas do Ads (CID) para enviar postbacks (etapa 5), separando cada CID com uma vírgula.
>
>   ![zds_Agency_multiple.png](https://files.readme.io/36112b9a08ca1e6a2150523e1ec39eda5c28a4be826e9f776f5dbd7b1d0c5378-21414553418897.png)
> * Para trabalhar com vários GAPPs, as campanhas para cada GAPP devem ser executadas em contas separadas do Google. Ao mudar de um GAPP para outro, certifique-se de desativar a primeira configuração de GAPPs na AppsFlyer.

<div id="google-ads-postback-partners-use-cases" />

## Casos de uso de parceiros de postback do Google Ads

<div id="use-case-1-advertiser-postbacks-only" />

<Accordion title="Caso de uso 1 - Somente postbacks do anunciante">

Um anunciante está executando campanhas do Google Ads e deseja que o tráfego de suas contas do Google Ads seja enviado para o GAPP X.

1. O anunciante <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> o Google Ads
2. O anunciante [configura](/docs/google-ads-postback-partners-configuration#configuração-do-parceiro-de-postback-do-google-ads) o GAPP X - Google Ads

O anunciante deve inserir todos os CIDs (IDs da conta do Ads) na configuração do GAPP X - Google Ads.

</Accordion>

<div id="use-case-2-active-agency-with-advertiser-postbacks-only" />

<Accordion title="Caso de uso 2 - Agência ativa, apenas com postbacks de anunciantes">

Um anunciante e uma agência estão executando campanhas do Google Ads. No entanto, o anunciante quer que apenas o seu tráfego seja enviado para o GAPP X.

1. O anunciante <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> o Google Ads
2. A agência <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> o Google Ads (para que somente o seu tráfego seja atribuído a eles como uma agência)
3. O anunciante [configura](/docs/google-ads-postback-partners-configuration#configuração-do-parceiro-de-postback-do-google-ads) o GAPP X - Google Ads

O anunciante deve inserir SOMENTE seus CIDs na configuração do GAPP X - Google Ads.

</Accordion>

<div id="use-case-3-active-advertiser-with-agency-postbacks-only" />

<Accordion title="Caso de uso 3 - Anunciante ativo, apenas com postbacks de agência">

Um anunciante e uma agência estão executando campanhas do Google Ads, a agência quer que apenas o seu tráfego seja enviado para o GAPP X.

1. O anunciante <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> o Google Ads
2. A agência <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> o Google Ads
3. A agência [configura](/docs/google-ads-postback-partners-configuration#configuração-do-parceiro-de-postback-do-google-ads) o GAPP X - Google Ads

A agência deve inserir SOMENTE seus CIDs na configuração do GAPP X - Google Ads

</Accordion>

<div id="use-case-4-advertiser-agency-postbacks" />

<Accordion title="Caso de uso 4 - Postbacks do anunciante e da agência">

Um anunciante e uma agência estão executando campanhas do Google Ads, tanto o anunciante quanto a agência querem que seu tráfego seja enviado para o GAPP X.

1. O anunciante <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">configura</Anchor> o Google Ads
2. A agência <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies">configura</Anchor> o Google Ads
3. O anunciante [configura](/docs/google-ads-postback-partners-configuration#configuração-do-parceiro-de-postback-do-google-ads) o GAPP X - Google Ads para seus CIDs
4. A agência [configura](/docs/google-ads-postback-partners-configuration#configuração-do-parceiro-de-postback-do-google-ads) o GAPP X - Google Ads para seus CIDs

Observe que esses devem ser CIDs diferentes entre o anunciante e a agência.

</Accordion>

<div id="available-parameters-for-gapps" />

## Parâmetros disponíveis para GAPPs

**O conteúdo dos postbacks depende da integração inicial dos GAPPs com a AppsFlyer** e não está relacionado a nenhuma configuração de anunciante. Portanto, quaisquer dois GAPPs podem ter parâmetros de postback definidos de forma diferente.

Por exemplo, `campaign type`, `city`, `carrier` e `ad_type` são parâmetros que podem ou não aparecer em qualquer postback do GAPP.

Existem duas fontes para os parâmetros de postback do GAPP:

1. **Macros da AppsFlyer** - para saber mais detalhes sobre todas as macros disponíveis nos postbacks da AppsFlyer, clique <Anchor target="_blank" href="/partners/pt/docs/postback-macros-for-ad-networks">aqui</Anchor>.
2. **Resposta do Google** - para cada instalação atribuída ao Google Ads, a AppsFlyer recebe informações relevantes do Google. A seguir estão os parâmetros disponíveis nos postbacks de GAPPs, conforme recebido pela AppsFlyer a partir do Google Ads (para informações detalhadas sobre os parâmetros, clique <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs#sample_responses">aqui</Anchor>)
   * ID de eventos de anúncio
   * ID da campanha
   * Nome da campanha
   * Tipo de campanha
   * ID do cliente externo (CID)
   * Tipo de rede
   * Subtipo de rede
   * Carimbo de data/hora
   * ID de vídeo
   * ID do grupo de anúncios
   * ID criativa
   * Palavra-chave
   * Tipo de correspondência
   * Posicionamento
   * Tipo de interação
   * Tipo de anúncio
   * Métrica de conversão
   * Localização

<div id="note" />

> 📘 **Observação**
>
> As informações disponíveis se baseiam exclusivamente nas informações enviadas pelo Google para a AppsFlyer. Se, por algum motivo, o Google não enviar as informações de uma instalação, a AppsFlyer não poderá repassá-las para o GAPP.

<div data-zendesk-anchors="h_01HKA1HTJ4VW4YRXMSVG7WBTJM=importante google-ads-postback-partner-setup=configura%C3%A7%C3%A3o-do-parceiro-de-postback-do-google-ads h_01HKA1HTJ5BE5EVQJ2T9HSHKQC=configura%C3%A7%C3%A3o-do-parceiro-de-postback-do-google-ads h_01HKA1HTJ5BJTTS15QC44M63B2=dica h_01HKA1HTJ5KSD1CVJ4FKDSATJX=observa%C3%A7%C3%B5es-importantes google-ads-postback-partners-use-cases=casos-de-uso-de-parceiros-de-postback-do-google-ads h_01HKA1HTJ5DX0Z2ZCGX07EX15F=casos-de-uso-de-parceiros-de-postback-do-google-ads h_01HKA1HTJ5T2XJJ4M9YZ1S52SF=use-case-1-advertiser-postbacks-only h_01HKA1HTJ5EFADYE33NQVP1NBQ=use-case-2-active-agency-with-advertiser-postbacks-only h_01HKA1HTJ5H4KK2M94QY0VFRSA=use-case-3-active-advertiser-with-agency-postbacks-only h_01HKA1HTJ537CYXEBQRCV5FSPK=use-case-4-advertiser-agency-postbacks available-parameters-for-gapps=par%C3%A2metros-dispon%C3%ADveis-para-gapps h_01HKA1HTJ5H0SXEMBVB6K2EZ91=par%C3%A2metros-dispon%C3%ADveis-para-gapps h_01HKA1HTJ55XWMX90KSYTGFB6C=observa%C3%A7%C3%A3o" />
