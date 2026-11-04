---
title: Notas de versão do Android SDK da AppsFlyer
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-11-02T01:06:43Z'
  id: 115001256006
  locale: pt
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/pt/articles/115001256006
---
> **Visão geral:** consulte as notas de versão do SDK para um resumo das últimas alterações feitas ao nosso Android SDK. Desenvolvedores que desejam acessar informações mais detalhadas devem acessar as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">notas de lançamento do Android no Dev Hub</Anchor>.

**No próximo ciclo fixo de seis meses, as versões legadas do SDK para iOS e Android deixarão de ter suporte.** O objetivo desse ciclo é trazer um aviso prévio para que as equipes se planejem com antecedência e garantam a funcionalidade do aplicativo, evitando interrupções. A atualização para a versão mais recente do SDK garante acesso aos novos recursos, além de uma estabilidade aprimorada e suporte contínuo.

<div id="important" />

> 🚧 **Importante!**
>
> Para garantir uma transição fácil, recomendamos que os desenvolvedores de aplicativos atualizem para a versão mais recente do SDK antes da data final.

<div id="end-of-support-vs-deprecated" />

## Data final de suporte vs. data de desativação

A AppsFlyer faz uma distinção entre o status **desativada** e **sem suporte** para diferenciar o nível de suporte e o impacto na mensuração de dados.

* **Versões desativadas:** versões do SDK que não são mais recomendadas devido a problemas conhecidos, como bugs críticos. Essas versões ainda podem enviar dados para a AppsFlyer, mas o uso contínuo não é recomendado. Queremos ressaltar a importância da atualização para uma versão mais recente.
* **Versões sem suporte:** versões do SDK para as quais a mensuração foi totalmente interrompida em todas as plataformas. Para Android e iOS, instalações, sessões e eventos in-app deixam de ser mensurados. O tráfego vindo dessas versões retorna um código de status 400 (a menos que ele seja especificamente excluído pela equipe de produto), o que significa que o SDK tentará enviar chamadas de API que serão rejeitadas pelos servidores da AppsFlyer, impedindo o processamento dos dados.

<div id="android-sdk-releases" />

## Lançamentos do Android SDK

A tabela abaixo traz as notas de lançamento para as versões do Android SDK que possuem suporte, incluindo datas de lançamento e atualizações importantes para desenvolvedores. Para mais informações específicas para desenvolvedores, veja nosso <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">guia de integração do Android SDK para desenvolvedores</Anchor>.

| Versão | Data de lançamento | Notas |
| --- | --- | --- |
| 7.0.4 | 10/01/2026 | <ul><li>Melhoria na gestão de endereços de e-mail do Gmail na API `setUserEmail`</li></ul> |
| 7.0.2 | 2026-10-19 | <ul><li>Adicionado suporte para geração de relatório de receita de anúncios para dois novos parceiros de mediação de anúncios: Google Ad Manager e CloudX.</li><li>Adicionado um novo parâmetro de evento para reportar a receita líquida.</li><li>melhorias de estabilidade e performance</li></ul> |
| 7.0.1 | 26/11/2025 | <ul><li>Agora, os aplicativos podem fornecer ao SDK um e-mail, número de telefone, nome e ID de login do Facebook do cliente com hash para compartilhar com parceiros de ad network. O SDK não coleta essas informações por conta própria. O aplicativo fornece essas informações, e apenas valores com hash são enviados, nunca em texto simples.</li><li>Os métodos `setUserEmails` e `setPhoneNumber` foram removidos. Os desenvolvedores que os usam devem mudar para `setUserEmail` e `setUserPhone`</li></ul> |
| 6.18.1 | 15/10/2025 | <ul><li>Corrigido um problema no Purchase Connector em que validações de compra que falhavam devido a problemas de conectividade eram armazenadas em cache e não eram tentadas novamente, o que podia resultar na ausência de dados de compra.</li></ul> |
| 6.18.0 | 28/17/2022 | <ul><li>Atualização técnica: melhorias de estabilidade e performance</li></ul> |
| 6.17.6 | 28/11/2022 | <ul><li>Corrigido um problema em que o valor de AF\_STORE definido pelo aplicativo não estava sendo enviado pelo SDK.</li></ul> |
| 6.17.5 | 10/06/2024 | <ul><li>Melhorias e correções de estabilidade</li><li>Adicionada a capacidade de acionar a `start`API de convite do usuáriostart antes de chamar `stop`/depois de chamar</li></ul> |
| 6.17.4 | 15/07/2025 | <ul><li>Atualizamos a integração entre o SDK e o Módulo de Segurança Avançado. Versão compatível com a versão 2.0.0 e versões mais recentes do módulo de segurança.</li><li>Se você estiver usando o Módulo de Segurança Avançado e quiser atualizar o SDK para v6.17.4, você também deve atualizar o Módulo de Segurança para v2.0.0.</li></ul> |
| 6.17.3 | 18/08/2025 | <ul><li>`waitForCustomerUserId`Correção de bugwaitForCustomerUserId: Correção relacionada à ofuscação no **UDL**`waitForCustomerUserId`</li></ul> |
| 6.17.2 | 17/02/2025 | <ul><li>Atualização técnica: atualizado para targetSDKVersion 35</li></ul> |
| 6.17.1 | 28/07/2025 | <ul><li>Atualizamos a `validateAndLogInAppPurchase` API para validação de compras no aplicativo (atualmente em beta)</li><li>Adicionamos a integração com a Google Play Integrity API para permitir a verificação da integridade do dispositivo através do Google Play</li></ul> |
| 6.17.0 | 24/04/2025 | <ul><li>Adicionamos suporte para a coleta de AppSet ID. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id">Instruções para desenvolvedores</Anchor></li></ul> |
| 6.16.2 | 02/03/2025 | <ul><li>Corrigimos um problema que poderia causar erros de compilação ao integrar o SDK.</li></ul> |
| 6.16.1 | 16/05/2023 | <ul><li>API atualizada para o envio manual de dados de consentimento de DMA para a AppsFlyer.</li></ul> |
| 6.16.0 | 17/12/2024 | <ul><li>Suporte adicionado para atribuição de preload na Samsung. <Anchor target="_blank" href="/marketers/pt/docs/set-up-appsflyer-preload-referrer-attribution#preload-referrer-da-samsung">Saiba mais</Anchor>.</li><li>Suporte adicionado para mensuração de receita na Privacy Sandbox attribution API (beta fechado).</li><li>Atualizamos o Dexguard para v9.8.12 para resolver problemas de estabilidade e melhorar a segurança.</li></ul> |
| 6.15.2 | 10/10/2024 | <ul><li>Melhorias e correções de estabilidade</li><li>Atualizações internas relacionadas à Attirbution API do Privacy Sandbox</li></ul> |
| 6.15.1 | 18/04/2024 | Atualização de versões:<ul><li>targetSDKVersion: v34</li><li>Gradle: v8.7</li><li>Java: v17</li></ul> |
| 6.15.0 | 31/07/2024 | <ul><li>Adicionamos o método `logAdRevenue` para enviar dados de receita de anúncios para a AppsFlyer. **Atenção:** a partir dessa versão, o AdRevenue Connector não deve mais ser usado; ele deve ser substituído pelo método `logAdRevenue`. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Saiba mais</Anchor></li></ul> |
| 6.14.2  <br />Fim do suporte:  <br />03/08/2027 | 10/06/2024 | <ul><li>Corrigimos um problema ao buscar o Meta Install Referrer em aplicativos criados com a Unity.</li></ul> |
| 6.14.1  <br />Fim do suporte:  <br />03/08/2027 | 29/01/2024 | Manutenção do SDK |
| 6.14.0  <br />Fim do suporte:  <br />03/08/2027 | 17/12/2024 | <ul><li>Adicionamos suporte para o fluxo atualizado de validação de compras. Atualmente, esse recurso está em beta fechado. Saiba mais.</li><li>Integração atualizada do Huawei Referrer. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">Saiba mais</Anchor>.</li></ul> |
| 6.13.1  <br />Fim do suporte:  <br />03/08/2027 | 25/10/2023 | Manutenção do SDK |
| 6.13.0  <br />Fim do suporte:  <br />03/08/2027 | 08/02/2024 | <ul><li>Adicionamos suporte para a nova política de consentimento do Google na UE (DMA)</li></ul> |

<div id="unsupported-sdk-versions" />

## Versões sem suporte

As seguintes versões do SDK atingiram o status de **fim de suporte**. Essas versões não podem mais enviar dados para a AppsFlyer e seu tráfego será rejeitado.

| Versão | Data de lançamento | Notas |
| --- | --- | --- |
| 6.12.6 | 02/08/2023 | Manutenção do SDK |
| 6.12.5 | 12/09/2021 | <ul><li>Adicionamos o parâmetro `original_link` ao callback de deep linking no fluxo de resolução de ESPs.</li></ul> |
| 6.12.4 | 25/10/2023 | <ul><li>Dexguard atualizado para a versão 9.4.16 para melhorar a estabilidade do SDK.</li></ul> |
| 6.12.3 | 29/06/2023 | Manutenção do SDK |
| 6.12.2 | 06/06/2023 | <ul><li>Corrigimos um bug que fazia o aplicativo travar em alguns dispositivos com Android 8.1.0 e Android 11.</li></ul> |
| 6.12.1 | 16/05/2023 | <ul><li>Corrigimos um problema com o atraso da abertura da Play Store em promoções cruzadas.</li><li>Corrigimos um bug que fazia o aplicativo travar em alguns dispositivos.</li></ul> |
| 6.12.0 | 25/04/2023 | <ul><li>Obsoleto - use a versão 6.12.1.</li></ul> |
| 6.11.2 | 28/06/2023 | <ul><li>Corrigimos um bug que fazia o aplicativo travar em alguns dispositivos.</li></ul> |
| 6.11.1 | 06/06/2023 | <ul><li>Obsoleto - use a versão 6.12.1.</li><li>Corrigimos um bug em que o aplicativo às vezes travava após inicializar o SDK.</li></ul> |
| 6.11.0 | 16/05/2023 | <ul><li>Correção de um problema que às vezes fazia o aplicativo travar em alguns dispositivos quando o SDK tentava obter o Google Play Referrer</li></ul> |
| 6.10.3 | 29/05/2024 | Manutenção do SDK |
| 6.10.2 (desativada) |  | Descontinuado |
| 6.10.1 | 01/03/2023 | <ul><li>Corrigimos um problema que às vezes fazia com que aplicativos em dispositivos Samsung fechassem ao inicializar o SDK. Esse problema afetou aplicativos com o SDK V6.6.0 e versões posteriores.</li></ul> |
| 6.10.0 | 13/02/2023 | <ul><li>Novo domínio da AppsFlyer para comunicação entre os servidores do SDK e da AppsFlyer.</li><li>API setHost alterada quando valores vazios ou nulos são enviados. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Saiba mais</Anchor></li></ul> |
| 6.9.4  <br />Fim do suporte:  <br />08/09/2025 | 06/12/2022 | <ul><li>Correção de um problema em que o envio de um evento de receita de anúncios do conector do ad revenue SDK acionava uma chamada para o ouvinte da conversão.</li><li>Correção de um problema que às vezes fazia com que os aplicativos congelassem quando um evento de receita de anúncios era enviado do conector do ad revenue SDK.</li></ul> |
| 6.9.3  <br />Fim do suporte:  <br />08/09/2025 | 19/07/2022 | <ul><li>A estrutura de solicitação interna para obter dados de conversão (GCD) foi atualizada. **Observação:** os dados de resposta permanecem os mesmos.</li><li>Correção de um problema em que o SDK acionava uma solicitação GCD quando o aplicativo tinha o ConversionListener definido como nulo.</li></ul> |
| 6.9.2  <br />Fim do suporte:  <br />08/09/2025 | 02/10/2022 | <ul><li>Correção de um problema relacionado a um atraso na solicitação de validação de compra usando a API validateAndLogInAppPurchase.</li></ul> |
| 6.9.1  <br />Fim do suporte:  <br />08/09/2025 | 19/09/2022 | Manutenção do SDK |
| 6.9.0  <br />Fim do suporte:  <br />08/09/2025 | 06/06/2023 | <ul><li>Compatibilidade com Xiaomi GetApps Store Referrer adicionada.</li><li>Atualizada a API interna para geração de relatórios de receita de anúncios. A partir desta versão, apenas o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">conector genérico do ad revenue SDK</Anchor> é compatível.</li></ul> |
| 6.8.2  <br />Fim do suporte:  <br />08/09/2025 | 29/08/2022 | <ul><li>Correção de um problema crítico com o mecanismo de armazenamento em cache do SDK introduzido na V6.7.0, fazendo com que os eventos armazenados em cache fossem enviados várias vezes.</li></ul> |
| 6.8.1  <br />6.8.1(desativada)  <br />Fim do suporte:  <br />08/09/2025 | 2022-08-24 | <ul><li>**Desativada.** Por favor, use a V6.8.2.</li></ul> |
| 6.8.0  <br />6.8.1(desativada)  <br />Fim do suporte:  <br />08/09/2025 | 2022-07-18 | <ul><li>**Desativada.** Por favor, use a V6.8.2.</li><li>A <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection">`enableLocationCollection`</Anchor> API foi removida do SDK. O aplicativo ainda pode relatar os dados de localização do usuário enviando-os para o SDK diretamente por meio da API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation">`logLocation`</Anchor>.</li><li>Adicionamos a permissão `com.google.android.gms.permission.AD_ID` do `AndroidManifest.xml` ao SDK. Saiba mais sobre isso <Anchor target="_blank" href="/marketers/pt/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">aqui</Anchor>.</li><li>Correção de um problema relacionado à otimização e ofuscação usando R8.</li></ul> |
| 6.7.0  <br />6.8.1(desativada)  <br />Fim do suporte:  <br />08/09/2025 | 19/06/2022 | <ul><li>**Desativada.** Por favor, use a V6.8.2.</li><li>A maneira como o SDK lida com solicitações para os servidores da AppsFlyer foi alterada. Após essa alteração, a solicitação de relatório da primeira abertura do app (conversão) será priorizada em relação a eventos in-app e outros tipos de solicitações. Saiba mais <Anchor target="_blank" href="/marketers/pt/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">aqui</Anchor>.</li><li>**Nova API**: use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata">`setDisableNetworkData`</Anchor> para cancelar a coleta de informações sobre a rede de celular (nome da operadora).</li></ul> |
| 6.6.1  <br />Fim do suporte:  <br />03/03/2025 | 16/05/2022 | Manutenção do SDK |
| 6.6.0  <br />Fim do suporte:  <br />03/03/2025 | 01/05/2022 | <ul><li>Adicionamos mais parâmetros ao callback `onDeepLinking` da UDL para o fluxo Direct Deep Linking (usuários existentes). <Anchor target="_blank" href="/marketers/pt/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Clique aqui para mais informações</Anchor>.</li></ul> |
| 6.5.4  <br />Fim do suporte:  <br />03/03/2025 | 23/03/2022 | Manutenção do SDK |
| 6.5.3  <br />Fim do suporte:  <br />03/03/2025 | 29/06/2023 | <ul><li>**Correção de bug:** correção de problema com a criação de links de convite de usuário que contêm caracteres especiais.</li></ul> |
| 6.5.2  <br />Fim do suporte:  <br />03/03/2025 | 26/01/2022 | <ul><li>Correção de problema com a resoluão de URLs para deferred deep linking em UDL.</li><li>Atualizado para DexGuard 9.2</li><li>Refatoração e mudanças internas.</li></ul> |
| 6.5.1  <br />Fim do suporte:  <br />03/03/2025 | 29/12/2021 | <ul><li>Resolução de deeplink com UDL para aplicativos que usam a <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#channel-name">opção out-of-Store with Channel</Anchor></li></ul> |
| 6.5.0  <br />Fim do suporte:  <br />03/03/2025 | 07/12/2021 | <ul><li>Refatoração e mudanças internas.</li></ul> |
| 6.4.3  <br />Fim do suporte:  <br />03/03/2025 | 14/11/2021 | <ul><li>Corrigimos um bug introduzido na `V6.4.2` com `LinkGenerator` que causava a criação de links com parâmetros de URL ausentes.</li></ul> |
| 6.4.2  <br />Fim do suporte:  <br />03/03/2025 | 24/10/2021 | Foram resolvidos:<ul><li>Parâmetro `pid` anexado duas vezes às URLs personalizadas gerados pelo `LinkGenerator`.</li><li>`/` extra adicionado ao valor `af_dp` ao usar o `LinkGenerator` para criar esquemas URI personalizados.</li><li>Tanto o IMEI quanto o AndroidID eram coletados, caso o aplicativo acionasse a coleta de apenas um deles.</li></ul> |
| 6.4.1  <br />Fim do suporte:  <br />03/03/2025 | 17/10/2021 | Resolvido o erro de compilação ao usar a versão Gradle anterior à V3.5.4. |
| 6.4.0  <br />Fim do suporte:  <br />03/03/2025 | 12/09/2021 | **Nova API:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">, que permite que você configure quais parceiros o SDK deve excluir do compartilhamento de dados.</Anchor><br /><br />A partir dessa versão, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter">`setSharingFilter`</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor> foram desativados. |
| 6.3.2<br /><br />Fim do suporte: 31/08/2024 | 06/06/2021 | **Nova API**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />Fim do suporte: 31/08/2024 | 26/05/2021 | <ul><li>**Nova API**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Adicionada a capacidade de acionar a `start`API de convite do usuáriostart antes de chamar `stop`/depois de chamar</li><li>`waitForCustomerUserId`Correção de bugwaitForCustomerUserId: Corrigimos um problema em que a chamada para **não era liberada mesmo após a chamada para `waitForCustomerUserIdsetCustomerUserId`**</li></ul> |
| 6.3.0  <br />Fim do suporte: 31/08/2024 | 2021-04-29 | <ul><li>`waitForCustomerUserId`Correção de bugwaitForCustomerUserId: Invocação incorreta de uma falha **na solicitação de envio de um evento in-app`waitForCustomerUserId`**</li><li>**Correção de bug**: coleta de métricas do sensor de movimento (para detecção de fraude)</li><li>**Bugfix**: correção relacionada à ofuscação no <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor></li><li>Atualização técnica para a OneLink API</li></ul> |
| 6.2.3  <br />Fim do suporte: 31/08/2024 | 17/12/2024 | Manutenção do SDK |
| 6.2.0  <br />Fim do suporte: 31/08/2024 | 07/02/2021 | <ul><li>**Nova API**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />Fim do suporte: 31/08/2024 | 2021-01-12 | <ul><li>Compatibilidade com DexGuard V9 adicionada</li></ul> |
| 6.1.3  <br />Fim do suporte: 31/08/2024 | 24/12/2024 | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#record-push-notifications">Nova API</Anchor>: `addPushNotificationDeepLinkPath`addPushNotificationDeepLinkPath(compatível com Movable Ink)</li></ul> |
| 6.1.1  <br />Fim do suporte: 31/08/2024 | 03/12/2020 | <ul><li>Suporte adicional para o Samsung Galaxy Store referrer</li><li>Pequenas correções de bugs e melhorias de performance.</li></ul> |
| 6.1.0  <br />Fim do suporte: 31/08/2024 | 09/11/2020 | <ul><li>Compatibilidade com <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">API unificada de deep linking</Anchor> adicionada</li></ul> |
| 6.0.1  <br />Fim do suporte: 31/08/2024 | 28/10/2020 | Manutenção do SDK |
| 6.0.0  <br />Fim do suporte: 31/08/2024 | 14/10/2020 | <ul><li>Grandes alterações na funcionalidade do SDK e na API, incluindo descontinuação e alterações no nome do método. [Saiba mais](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-sdk-version-control-policy">Política de controle de versões da AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o h_01JVHEKR4MTFV0FDHMTQW00BCS=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o android-sdk-v6=lan%C3%A7amentos-do-android-sdk h_01H9ZPCP8RWF24WAZ6YYMA1GS0=lan%C3%A7amentos-do-android-sdk deprecated-versions=vers%C3%B5es-sem-suporte 01JHFAXXV51DHADQ7P2Q6RHFX0=vers%C3%B5es-sem-suporte h_01HDNZ774ME3SVT89JS7R4MSKE=veja-tamb%C3%A9m" />
