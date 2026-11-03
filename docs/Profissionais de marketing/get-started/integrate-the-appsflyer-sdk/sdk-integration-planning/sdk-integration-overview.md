---
title: Visão geral da integração do SDK
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-08-18T00:15:59Z'
  id: 207032126
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/207032126
---
> **At a glance:** **Resumo:** saiba mais sobre as funcionalidades do SDK da AppsFlyer que estão disponíveis e determine quais APIs você deseja que seu aplicativo Android ou iOS use.

## Sobre o SDK

Assista o vídeo abaixo para ter uma visão geral da integração do SDK.

<Embed title="Visão geral da integração do SDK" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

O SDK fornece a instalação do aplicativo e a funcionalidade de gravação de eventos. Você pode gravar instalações, sessões e eventos in-app. Os eventos in-app incluem, por exemplo, compras in-app ou subir de nível em um jogo. Gravar esses eventos pode ajudar você a avaliar o ROI e a qualidade do usuário.

Este artigo descreve o processo de integração do SDK V6+ e ajuda os gerentes de produto do anunciante (proprietário do aplicativo) a planejar a integração do SDK da AppsFlyer com seu aplicativo Android ou iOS.

A documentação adicional inclui o seguinte:

<Tabs>
<Tab title="Iniciando o SDK no Android native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Documentação de instalação do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-android-sdk-release-notes">Notas de versão</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Documentação de referência do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/fill-out-google-safety-section-form">Seção de segurança de dados no Google Play</Anchor>

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

* <Anchor target="_blank" href="/marketers/pt/docs/updating-to-ios-sdk-v6-and-plugins">Atualização para o iOS SDK V6</Anchor>. Observe que o SDK do iOS V5.4.4 é totalmente operacional com o iOS 14. No entanto, recomendamos a adoção do SDK V6. X para garantir a compatibilidade com futuras versões do iOS.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Documentação de instalação do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Notas de versão</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Documentação de referência do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/preparing-for-the-app-store-review-nutrition-labels">Prepare-se para a avaliação da App Store—tabelas nutricionais</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentação de instalação do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Documentação de referência do SDK para desenvolvedores</Anchor>

</Tab>

<Tab title="CONTEXTO">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentação de instalação do SDK para desenvolvedores</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Documentação de referência do SDK para desenvolvedores</Anchor>

</Tab>
</Tabs>

## Compatibilidade do SDK

O SDK da AppsFlyer é compatível com as seguintes plataformas:

<Tabs>
<Tab title="com o Android">

* Iniciando a partir da versão Android V4.0
* Plataformas que não são mobile baseadas no Android, como Smart TVs (incluindo o Fire TV da Amazon). <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Veja a visão geral de CTV</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">Mercados fora da loja</Anchor> para aplicativos Android, como Amazon e Baidu

</Tab>

<Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Está em conformidade com as redes <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor> da Apple

O SDK é compatível com <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">diversos métodos de atribuição</Anchor>. Os métodos de atribuição que são usados dependem do seguinte:

* A versão do iOS instalada no dispositivo do usuário
* A versão do SDK do iOS instalada no aplicativo

<table><thead><tr><th>Métodos de atribuição compatíveis</th><th>Versão do iOS</th><th>Suporte do SDK para iOS</th><th>Notas</th></tr></thead><tbody><tr><td rowspan="2">Modelagem probabilística</td><td>8 – 14,4</td><td>5.0.0+</td><td> </td></tr><tr><td>14,5+</td><td>6.0.3+</td><td>A modelagem probabilística é limitada ao contexto de mídia própria, promoção cruzada e fluxos consentidos web-to-app.</td></tr><tr><td rowspan="2">ID matching<br/><br/> </td><td>8 - 13</td><td>5.0.0+</td><td>Os usuários podem cancelar o uso do Limit Ad Tracking (LAT).</td></tr><tr><td>14,5+</td><td>6.0.3+</td><td>A transparência de rastreamento de aplicativos (ATT) e o consentimento do usuário são necessários. Para obter mais informações, consulte <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">Configurar o SDK do iOS para oferecer suporte à ATT</a>.</td></tr><tr><td rowspan="2"><a href="./skadnetwork-skan-solution-guide" target="_blank">Proteção contra fraudes</a></td><td>11.3 - 13</td><td rowspan="2">6.2.3<br/><br/> </td><td>A solução de SKAdNetwork (SKAN) é <span>limitada à atribuição de instalação de acordo com a especificação da <a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a>,</span> <span>o que significa que não há valor de conversão.</span> </td></tr><tr><td>14+</td><td><ul><li>A SKAN está sempre disponível nos níveis do iOS e do SDK, independentemente da configuração da ATT.</li><li>O profissional de marketing habilita o SKAN no dashboard da AppsFlyer.</li></ul></td></tr></tbody></table>

A partir do SDK V6.0.8, está disponível a <Anchor target="_blank" href="/marketers/pt/docs/apple-app-clips-integration-guide">atribuição de Apple App Clips</Anchor>. Você também pode ler nosso <Anchor target="_blank" href="https://www.appsflyer.com/pt/resources/others/apple-app-clips">artigo no blog</Anchor> sobre Apple App Clips.

</Tab>
</Tabs>

## Integração do SDK

O processo de instalação e integração do SDK exige que o gerente de produto e o desenvolvedor mobile trabalhem juntos. **Antes** de integrar o SDK ao seu aplicativo, analise todas as tarefas de integração e considere as funcionalidades que você deseja que seu aplicativo use.

### Checklist de planejamento do SDK

Para começar, preparamos uma <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">checklist</Anchor> para ajudar a orientar você durante o processo de planejamento. Para cada tarefa, há links para a documentação do profissional de marketing e do desenvolvedor.

### Tarefas de integração do SDK

A integração básica do SDK inclui as tarefas abaixo. As estimativas de tempo são destinadas apenas como orientação geral.

| Tarefas básicas de integração do SDK | Tempo de planejamento |
| --- | --- |
| Recupere a <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#implementação-da-dev-key-em-seu-app">chave do desenvolvedor da AppsFlyer</Anchor> e envie o link junto com as instruções de instalação e integração para seu desenvolvedor. | 15 minutos |
| Analise as <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#atribuição">considerações de atribuição</Anchor> e determine quais identificadores de dispositivo coletar. | 30 minutos |
| Determine os <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#registro-de-eventos-in-app">eventos in-app</Anchor> que você deseja medir e envie os nomes de eventos e parâmetros de eventos para o desenvolvedor. | 1 hora |
| Android iOS | 30 minutos |
| Determine os métodos para <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#acessando-dados-de-atribuição-e-deep-linking">acessar dados de atribuição</Anchor>. | 30 minutos |
| Quando a integração básica estiver concluída, qualquer usuário da conta com acesso ao painel da AppsFlyer poderá realizar <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#testar-a-integração-do-sdk">testes básicos</Anchor>.<br /><br />Os desenvolvedores podem utilizar registros de depuração no <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">ambiente de desenvolvimento</Anchor>. | 1 hora |

Você pode trabalhar com seus desenvolvedores mobile para implementar essas APIs adicionais no SDK:

| Tarefas adicionais de integração do SDK | Tempo de planejamento |
| --- | --- |
| Determine se o aplicativo requer configuração de <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#métodos-de-atribuição-adicionais">atribuição adicional</Anchor> (por exemplo, métrica de desinstalação ou atribuição de instalação para lojas de aplicativos de terceiros). | 30 minutos |
| Determine <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#sessões">o relatório da sessão do usuário</Anchor>. | 30 minutos |
| Determine os métodos de atribuição a serem <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#mídias-próprias">usados para fontes de mídia próprias</Anchor>. | 1 hora |
| Gerencie as políticas <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#privacidade-do-usuário">de privacidade do usuário</Anchor> para garantir que seu aplicativo esteja em conformidade com os regulamentos de privacidade (GDPR, CCPA). | 1 hora |

> 📘 **Note**
>
> **Consulte também**
>
> * Visão geral da plataforma CTV, PC e console

<div data-zendesk-anchors="about-the-sdk=sobre-o-sdk h_01H9FHRVKE6BHGW05G6YMKF737=sobre-o-sdk sdk-compatibility=compatibilidade-do-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=compatibilidade-do-sdk sdk-integration=integra%C3%A7%C3%A3o-do-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=integra%C3%A7%C3%A3o-do-sdk sdk-planning-checklist=checklist-de-planejamento-do-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=checklist-de-planejamento-do-sdk sdk-integration-tasks=tarefas-de-integra%C3%A7%C3%A3o-do-sdk h_01H9FHRVKERHXY19R97EN86EGP=tarefas-de-integra%C3%A7%C3%A3o-do-sdk" />
