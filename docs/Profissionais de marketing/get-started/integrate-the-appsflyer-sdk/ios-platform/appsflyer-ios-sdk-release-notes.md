---
title: Notas de lançamento do iOS SDK da AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Release Notes
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-11-02T01:07:18Z'
  id: 115001224823
  locale: pt
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/pt/articles/115001224823
---
> **Resumo:** As notas de versão do SDK fornecem um resumo das últimas mudanças no SDK do iOS. Desenvolvedores que desejam acessar informações mais detalhadas devem acessar as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">notas de lançamento no Dev Hub</Anchor>.

**No próximo ciclo fixo de seis meses, as versões legadas do SDK para iOS e Android deixarão de ter suporte.** O objetivo desse ciclo é trazer um aviso prévio para que as equipes se planejem com antecedência e garantam a funcionalidade do aplicativo, evitando interrupções. A atualização para a versão mais recente do SDK garante acesso aos novos recursos, além de uma estabilidade aprimorada e suporte contínuo.

<div id="important" />

> 🚧 **Importante!**
>
> Para garantir uma transição fácil, recomendamos que os desenvolvedores de aplicativos atualizem para a versão mais recente do SDK antes da data final.

<div id="end-of-support-vs-deprecated" />

## Data final de suporte vs. data de desativação

A AppsFlyer faz uma distinção entre o status **desativada** e **sem suporte** para diferenciar o nível de suporte e o impacto na mensuração de dados.

* **Versões desativadas:** versões do SDK que não são mais recomendadas devido a problemas conhecidos, como bugs críticos. Essas versões ainda podem enviar dados para a AppsFlyer, mas o uso contínuo não é recomendado. Queremos ressaltar a importância da atualização para uma versão mais recente.
* **Versões sem suporte:** versões do SDK para as quais a mensuração foi totalmente interrompida em todas as plataformas. Para Android e iOS, instalações, sessões e eventos in-app deixam de ser mensurados. O tráfego vindo dessas versões retorna um código de status 400 (a menos que ele seja especificamente excluído pela AppsFlyer), o que significa que o SDK tentará enviar chamadas de API que serão rejeitadas pelos servidores da AppsFlyer, impedindo o processamento dos dados.

<div id="ios-sdk-release-notes" />

## Notas de lançamento do iOS SDK

A tabela abaixo traz as notas de lançamento para as versões do iOS SDK que possuem suporte, incluindo datas de lançamento e atualizações importantes para desenvolvedores. Para mais informações específicas para desenvolvedores, veja nossos <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">guias de integração do iOS SDK para desenvolvedores</Anchor>.

| Versão | Data de lançamento | Observações |
| --- | --- | --- |
| 7.0.4 | 2026-10-27 | <ul><li>Melhoria no tratamento de endereços de e-mail do Gmail na API `setUserEmail`.</li></ul> |
| 7.0.3 | 10/12/2026 | <ul><li>O SDK agora é compatível com googleAdManager e cloudX como parceiros de mediação de receita de anúncios.</li><li>Foi adicionado um campo de receita líquida que os desenvolvedores podem associar a eventos in-app, para reportar a receita com mais precisão.</li><li>Foi reduzida a pegada de memória do SDK.</li></ul> |
| 7.0.1 | 24/07/2024 | <ul><li>Os aplicativos agora podem fornecer ao SDK um e-mail, número de telefone, nome e ID de login do Facebook do cliente com hashing para compartilhamento com parceiros de ad network. O SDK não coleta essas informações por conta própria. O aplicativo fornece essas informações, e apenas valores com hashing são enviados, nunca em texto simples.</li><li>Os métodos `setUserEmails` e `setPhoneNumber` foram removidos. Os desenvolvedores que usam esses métodos devem migrar para `setUserEmail` e `setUserPhone`</li></ul> |
| 6.18.1 | 21/09/2025 | <ul><li>Corrigido um problema em que as solicitações de validação de compra do Purchase Connector que falhavam devido a um erro de network eram permanentemente perdidas após a reinicialização do aplicativo.</li></ul> |
| 6.18.0 | 28/11/2022 | <ul><li>Adicionado suporte para buscar AppTransaction, uma representação do download de um aplicativo, assinada criptograficamente pela loja de aplicativos.</li><li>Correções de bugs e melhorias</li></ul> |
| 6.17.9 | 15/10/2026 | <ul><li>28/08/2o24</li><li>Corrigido um problema em que o ID de usuário do cliente definido pelo aplicativo não era enviado no evento de instalação.</li></ul> |
| 6.17.8 | 21/08/2025 | <ul><li>Recursos de debugging estendidos</li></ul> |
| 6.17.7 | 15/07/2025 | <ul><li>Corrigimos um problema na busca de dados da ICM library do Google</li></ul> |
| 6.17.6 | 24/06/2025 | <ul><li>Corrigimos um problema introduzido na v6.17.3 que poderia causar uma falha quando o SDK tentava enviar dados do ICM para o AppsFlyer.</li></ul> |
| 6.17.5  <br />data de desativação | 23/04/2025 | <ul><li>**Essa versão está obsoleta e não deve ser usada.**</li></ul> |
| 6.17.4  <br />Desativada | 27/08/2025 | <ul><li>**Essa versão está obsoleta e não deve ser usada.**</li><li>Corrigimos um problema em que, em casos raros, o aplicativo falhava ao inicializar o SDK.</li></ul> |
| 6.17.3  <br />Desativada | 18/02/2025 | <ul><li>**Essa versão está obsoleta e não deve ser usada.**</li><li>Lógica atualizada para melhorar a precisão na busca de dados no ICM library do Google.</li></ul> |
| 6.17.2 | 15/07/2025 | <ul><li>Atualizamos a `validateAndLogInAppPurchase` API (beta)</li><li>Aprimoramos a gestão de tokens do Apple Search Ads (ASA) para apps que coletam o consentimento à ATT (AppTrackingTransparency).</li></ul> |
| 6.17.1 | 10/06/2024 | <ul><li>Adicionamos suporte para mensuração de <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16203286">Google Integrated Conversion</Anchor> (ICM).</li><li>Corrigimos um problema que causava o aparecimento de um popup de login da App Store ao executar o SDK em um ambiente de desenvolvimento.</li></ul> |
| 6.17.0 | 23/09/2024 | <ul><li>Melhorias de estabilidade e performance</li></ul> |
| 6.16.2 | 15/10/2025 | <ul><li>Atualização técnica necessária para liberar essa versão nos plugins</li></ul> |
| 6.16.1 | 15/02/2023 | <ul><li>API atualizada para o envio manual de dados de consentimento de DMA para a AppsFlyer.</li></ul> |
| 6.16.0 | 19/01/2025 | <ul><li>Suporte adicionado para as APIs StoreKit 2 da Apple para relatórios de assinatura e compras in-app através do Purchase Connector. Atualmente, esse recurso está em beta fechado.</li></ul> |
| 6.15.3 | 03/07/2024 | Manutenção do SDK |
| 6.15.2 | 10/06/2024 | <ul><li>Corrigimos um problema com a transmissão de eventos no Purchase Connector. Essa correção não afeta nenhuma versão de produção do Purchase Connector e está relacionada à sua atualização para a versão 6.15.x.</li></ul> |
| 6.15.1 | 26/04/2024 | <ul><li>Corrigimos um problema com a detecção de reinstalação que ocorria quando dois ou mais aplicativos do mesmo fornecedor estavam instalados no dispositivo.</li></ul> |
| 6.15.0 | 19/04/2024 | <ul><li>Adicionamos a `logAdRevenue` API para enviar dados de receita de anúncios para a AppsFlyer. **Atenção:** A partir dessa versão, o AdRevenue Connector não deve mais ser usado; ele deve ser substituído pelo método `logAdRevenue`. Para mais detalhes, consulte [aqui](https://dev.appsflyer.com/hc/docs/ad-revenue-2).</li><li>Atualizações internas relacionadas ao Purchase Connector. Os aplicativos que usam o Purchase Connector e atualizam para essa versão do SDK também devem atualizar seu Purchase Connector para a versão 6.15.0.</li></ul> |
| 6.14.6  <br />Fim do suporte:  <br />2027-03-08 | 18/04/2024 | <ul><li>Corrigimos um problema em que o SDK estava fazendo chamadas redundantes para a `getConversionData` API (GCD) ao iniciar uma nova sessão; isso não afeta a mensuração.</li></ul> |
| 6.14.5  <br />Fim do suporte:  <br />2027-03-08 | 07/04/2024 | <ul><li>Corrigimos um problema em que o SDK enviava os dados de consentimento manual configurados pelo aplicativo, mesmo que o código para enviar o consentimento manual tivesse sido removido.</li></ul> |
| 6.14.4  <br />Fim do suporte:  <br />03/08/2027 | 10/06/2024 | <ul><li>Atualizamos o Privacy Manifest para o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">Strict-Mode SDK</Anchor>.</li></ul> |
| 6.14.3  <br />Fim do suporte:  <br />03/08/2027 | 04/01/2024 | <ul><li>Corrigimos a mesclagem automatizada do Privacy Manifest para apps que usam o Cocoapods.</li></ul> |
| 6.14.2  <br />Fim do suporte:  <br />03/08/2027 | 19/08/2024 | Manutenção do SDK |
| 6.14.1  <br />Fim do suporte:  <br />03/08/2027 | 17/12/2024 | <ul><li>Adicionamos suporte para o fluxo atualizado de validação de compras. Atualmente, esse recurso está em beta fechado. Saiba mais.</li></ul> |
| 6.14.0  <br />Fim do suporte:  <br />03/08/2027 | 24/08/2023 | <ul><li>Adicionamos suporte para Privacy Manifest. <Anchor target="_blank" href="/marketers/pt/docs/implement-privacy-manifest-in-your-app">Saiba mais sobre o Privacy Manifest na AppsFlyer</Anchor>.</li><li>Adicionamos uma assinatura XCFramework ao SDK, permitindo que os desenvolvedores que usam o Xcode 15 validem a origem e a autenticidade do SDK.</li></ul> |
| 6.13.2  <br />Fim do suporte:  <br />03/08/2027 | 20/07/2023 | <ul><li>Corrigimos um problema que fazia com que a abertura de apps que usam SPM e Xcode 15.3 falhasse. Veja as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132">notas de versão do desenvolvedor</Anchor> para mais informações.</li></ul> |
| 6.13.1  <br />Fim do suporte:  <br />03/08/2027 | 28/06/2023 | <ul><li>Corrigimos o problema de envio de dados de consentimento para usuários aos quais a GDPR não se aplica em um fluxo de consentimento de CMP (DMA).</li></ul> |
| 6.13.0   <br />Fim do suporte:  <br />2027-03-08 | 08/02/2024 | <ul><li>Adicionamos suporte para a nova política de consentimento do Google na UE</li></ul> |

<div id="unsupported-sdk-versions" />

## Versões sem suporte

As seguintes versões do SDK atingiram o status de **fim de suporte**. Essas versões não podem mais enviar dados para a AppsFlyer e seu tráfego será rejeitado.

| Versão | Data de lançamento | Observações |
| --- | --- | --- |
| 6.12.3 | 24/05/2023 | <ul><li>Um novo parâmetro de `original_link` foi adicionado ao callback de deep linking no fluxo de resolução de provedores de serviços de e-mail (ESPs).</li><li>Todas as referências ao iAd Framework foram removidas.</li></ul> |
| 6.12.2 | 25/04/2023 | Manutenção do SDK |
| 6.12.1 | 02/04/2023 | <ul><li>Correção de um problema na SKAdNetwork 4.0 que fazia com que valores da conversão parciais fossem relatados como "None"</li><li>Correção de uma falha na implementação do tvOS</li></ul> |
| 6.12.0 | 15/02/2023 | Suporte de bitcode removido do SDK |
| 6.11.2 | 13/06/2023 | Correção de um problema identificado na v6.11.0, em que ao chamar `validateAndLogInAppPurchase` (a API legada para validação de compra e logging) o log do evento de compra não ocorria.   <br />  <br />**Importante:** Se você estiver usando `v6.11.0` ou `v6.11.1` e a `validateAndLogInAppPurchase` API, atualize para essa versão. |
| 6.11.1 | 26/03/2024 | Manutenção do SDK |
| 6.11.0 | 05/03/2024 | <ul><li>Novo nome de domínio da AppsFlyer na URL usada pelo SDK para enviar solicitações aos servidores da AppsFlyer.</li><li>Alteração no comportamento da API setHost quando valores vazios ou nulos são enviados. [Saiba mais](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 19/07/2022 | O parâmetro `link` foi adicionado ao payload UDL dos cenários de Direct Deep Linkinig (deep linking direto). |
| 6.10.0 | 15/02/2023 | Suporte para SKAdNetwork 4.0. <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Saiba mais sobre a solução da AppsFlyer para SKAdNetwork</Anchor> |
| 6.9.2  <br />Fim do suporte:  <br />08/09/2025 | 31/01/2023 | A estrutura de solicitação interna para obter dados de conversão (GCD) foi atualizada. **Observação:** os dados de resposta permanecem os mesmos. |
| 6.9.1  <br />Fim do suporte:  <br />08/09/2025 | 19/07/2022 | A estrutura de solicitação interna para obter dados de conversão (GCD) foi atualizada. **Observação:** os dados de resposta permanecem os mesmos. |
| 6.9.0  <br />Fim do suporte:  <br />08/09/2025 | 06/11/2022 | A API interna para relatórios AdRevenue foi atualizada. A partir dessa versão, somente o [conector genérico (Generic Connector) para AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2) é compatível.<br /><br />Essa versão do SDK é compatível com o AdRevenue Connector `V6.9.0`. |
| 6.8.1  <br />Fim do suporte:  <br />08/09/2025 | 09/08/2022 | Detecção de reinstalação: aprimoramos a capacidade de detectar e relatar reinstalações usando o armazenamento no dispositivo. Esse recurso pode ser controlado no dashboard da AppsFlyer na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de Configuração do aplicativo</Anchor>. |
| 6.8.0  <br />Fim do suporte:  <br />03/03/2025 | 19/07/2022 | Para detecção de reinstalação, use o SDK V6.8.1+ |
| 6.7.0  <br />Fim do suporte:  <br />03/03/2025 | 19/06/2022 | Atualize a implementação da SKAdNetwork para usar a Apple API atualizada, `updatePostbackConversionValue`, introduzida no iOS 15.4.<br /><br />Isso não afeta os dados enviados da SKAdNetwork e não requer nenhuma alteração no código do aplicativo. |
| 6.6.1  <br />Fim do suporte:  <br />03/03/2025 | 16/05/2022 | Manutenção do SDK |
| 6.6.0  <br />Fim do suporte:  <br />03/03/2025 | 01/05/2022 | Adicionamos mais parâmetros ao callback `didResolveDeepLink` da UDL para o fluxo Direct Deep Linking (usuários existentes). <Anchor target="_blank" href="/marketers/pt/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Clique aqui para mais informações</Anchor>. |
| 6.5.4  <br />Fim do suporte:  <br />03/03/2025 | 23/03/2022 | Manutenção do SDK |
| 6.5.3  <br />Fim do suporte:  <br />03/03/2025 | 02/03/2022 | **Correção de bug:** correção de um problema com uma invocação dupla de `didResolveDeepLink` em links baseados em esquemas URI. |
| 6.5.2  <br />Fim do suporte:  <br />03/03/2025 | 26/01/2022 | Manutenção do SDK |
| 6.5.1  <br />Fim do suporte:  <br />03/03/2025 | 03/01/2022 | Manutenção do SDK |
| 6.5.0  <br />Fim do suporte:  <br />03/03/2025 | 22/12/2021 | Refatoração e mudanças internas. |
| 6.4.4  <br />Fim do suporte:  <br />03/03/2025 | 12/12/2021 | Manutenção do SDK |
| 6.4.3  <br />Fim do suporte:  <br />03/03/2025 | 30/11/2021 | Correção de estabilidade para MacOS 10.14.6 com xcframework. |
| 6.4.2  <br />Fim do suporte:  <br />03/03/2025 | 28/10/2021 | Manutenção do SDK |
| 6.4.1  <br />Fim do suporte:  <br />03/03/2025 | 24/10/2021 | Estabilidade resolvida em aplicativos Unity. |
| 6.4.0  <br />Fim do suporte:  <br />03/03/2025 | 12/09/2021 | **API adicionada:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`, que permite que você configure quais parceiros o SDK deve excluir do compartilhamento de dados.</Anchor><br /><br />A partir dessa versão, `setSharingFilter` e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor> foram desativados. |
| 6.3.5  <br />Fim do suporte: 31/08/2024 | 19/08/2021 | **API adicionada**: [`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />A partir dessa versão, o idioma não é mais coletado automaticamente pelo SDK. |
| 6.3.4  <br />Fim do suporte: 31/08/2024 | 21/07/2021 | <ul><li>**Correção de bug:** correção de um problema com a execução do SDK em simuladores XCode 12.5</li><li>Pequenas correções e atualizações.</li></ul> |
| 6.3.2  <br />Fim do suporte: 31/08/2024 | 17/06/2021 | Logs de debug aprimorados. |
| 6.3.1  <br />Fim do suporte: 31/08/2024 | 02/06/2021 | Manutenção do SDK |
| 6.3.0  <br />Fim do suporte: 31/08/2024 | 13/05/2021 | <ul><li>Suporte Apple Silicon: adicionamos suporte para executar o SDK em um simulador usando dispositivos Mac com o chipset M1</li><li>A partir dessa versão, o SDK é compatível com iOS `9`+. O iOS `8` não é mais compatível.</li><li>SDK de modo estrito no iOS: suporte adicionado para o gerenciador de dependências Carthage</li><li>Atualização técnica para a OneLink API</li></ul> |
| 6.2.6  <br />Fim do suporte: 31/08/2024 | 25/04/2021 | <ul><li>Correção de bug: as regras da SKAdNetwork não carregavam quando a inicialização do SDK era feita após `didFinishLaunchingWithOptions`</li><li>Correção de bug: caso extremo, em que`waitForATTUserAuthorization` fazia com que o evento de inicialização fosse enviado sem IDFA, mesmo em casos em que o usuário consentia com o compartilhamento de dados</li><li>Permitir que o SDK seja executado em dispositivos iOS 8</li><li>Limpeza e remoção de código e dados não utilizados</li></ul> |
| 6.2.5  <br />Fim do suporte: 31/08/2024 | 06/04/2021 | Refatoração, limpeza e remoção de dados não utilizados do SDK.<br /><br />A partir dessa versão:<ul><li>O método `setShouldCollectDeviceName` foi desativado e não retorna o nome do dispositivosetShouldCollectDeviceName</li><li>O parâmetro `wifi` enviado do SDK está definido como `False`</li></ul> |
| 6.2.4  <br />Fim do suporte: 31/08/2024 | 15/03/2021 | Correção de bug relacionado ao modo de mensuração de receita SKAdNetwork e eventos in-app que contêm o parâmetro `AF_REVENUE`.<br /><br />A partir desta versão, no caso de mensuração de receita: qualquer evento contendo `AF_REVENUE` afeta o valor de conversão. Antes dessa alteração, o valor de conversão era definido apenas se estivesse na estrutura do evento `AF_PURCHASE`.<br /><br />**Atenção:** se você implementar a mensuração de receita da SKAdNetwork, deverá atualizar para essa versão. |
| 6.2.3  <br />Fim do suporte: 31/08/2024 | 07/03/2021 | Correção de bug relacionado à chamada de `updateConversionValue` da SKAdNetwork. |
| 6.2.2  <br />Fim do suporte: 31/08/2024 | 18/02/2021 | Manutenção do SDK |
| 6.2.1  <br />Fim do suporte: 31/08/2024 | 15/02/2021 | Suporte para <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">relatórios de eventos por S2S</Anchor> |
| 6.2.0  <br />Fim do suporte: 31/08/2024 | 07/02/2021 | API adicional: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4  <br />Fim do suporte: 31/08/2024 | 2021-01-12 | Manutenção do SDK |
| 6.1.3  <br />Fim do suporte: 31/08/2024 | 24/12/2024 | <ul><li>API adicional: <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>(compatível com Movable Ink)</li><li>Suporte para <Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2  <br />Fim do suporte: 31/08/2024 | 03/12/2020 | Manutenção do SDK |
| 6.1.1  <br />Fim do suporte: 31/08/2024 | 17/11/2020 | Introdução ao <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">modo estrito do SDK</Anchor> |
| 6.1.0  <br />Fim do suporte: 31/08/2024 | 09/11/2020 | Suporte para <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">Unified deep linking API</Anchor> |
| 6.0.8  <br />Fim do suporte: 31/08/2024 | 28/10/2020 | Suporte para a <Anchor target="_blank" href="/marketers/pt/docs/apple-app-clips-integration-guide">atribuição de Apple App Clips</Anchor>. |
| 6.0.7  <br />Fim do suporte: 31/08/2024 | 21/10/2020 | Manutenção do SDK |
| 6.0.6  <br />Fim do suporte: 31/08/2024 | 20/10/2020 | Manutenção do SDK |
| 6.0.5  <br />Fim do suporte: 31/08/2024 | 08/10/2020 | Manutenção do SDK |
| 6.0.4  <br />Fim do suporte: 31/08/2024 | 30/09/2020 | Suporte a vários redirecionamentos de ESPs |
| 6.0.3  <br />Fim do suporte: 31/08/2024 | 06/09/2020 | <ul><li>Alteração no nome da API:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>O SDK coleta o IDFA por padrão para iOS 14 (assim como para versões anteriores do iOS)</li></ul> |
| 6.0.2   <br />Fim do suporte: 31/08/2024 | 27/08/2020 | <ul><li>Alteração no nome da API:<br />deviceLoggingDisabled --> anonymizeUser</li><li>A caixa de diálogo AppTrackingTransparency (ATT) é necessária para coletar o IDFA para iOS 14</li><li>Adicionamos suporte para atribuição de promoção cruzada com IDFV</li></ul> |
| 6.0.1 beta  <br />Fim do suporte: 31/08/2024 | 06/08/2020 | <ul><li>Suporte adicionado para <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">atribuição da SKAdNetwork</Anchor>, com o intuito de ajudar os anunciantes a mensurar o sucesso das suas campanhas sem violar a privacidade do usuário</li></ul> |
| 6.0.0 beta  <br />Fim do suporte: 31/08/2024 | 04/08/2020 | <ul><li>Recursos de debugging estendidos</li><li>Grandes alterações na API e na funcionalidade do SDK. [Saiba mais](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan">Guia introdutório ao iOS 14, ATT e SKAdNetwork</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o h_01JVHEKR4MTFV0FDHMTQW00BCS=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o ios-sdk-v6=notas-de-lan%C3%A7amento-do-ios-sdk 01H8W3DDM1BYRSPMFTA3TCY8EQ=notas-de-lan%C3%A7amento-do-ios-sdk unsupported-sdk-versions=vers%C3%B5es-sem-suporte h_01JVHGN5NVRMGN9SJ5DWEAJYN3=vers%C3%B5es-sem-suporte h_01HE7RE2EPQX872DKNDBJ2G2QE=veja-tamb%C3%A9m" />
