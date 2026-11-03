---
title: Perguntas frequentes gerais sobre integração de SDK
metadata:
  keywords:
    - Advertisers
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
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-08-18T00:15:57Z'
  id: 207033546
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/207033546
---
> **At a glance:** **Visão geral:** o SDK da AppsFlyer permite que você anuncie seu aplicativo com segurança e atribua, vincule e colete informações comportamentais de seus usuários que usam dispositivos móveis. Você pode configurar e começar a trabalhar com qualquer rede de anúncios e/ou plataforma em questão de minutos, não semanas ou meses!

## Como instalar e atualizar o SDK da AppsFlyer?

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Para saber como instalar e atualizar o SDK da AppsFlyer, consulte o Dev Hub.</Anchor> **Observação**: atualizar o SDK requer o lançamento de uma nova versão do seu aplicativo nas lojas.

## É difícil integrar o SDK da AppsFlyer?

Em menos de uma hora, um desenvolvedor experiente pode preparar aplicativos para atribuição com a AppsFlyer. Em seguida, é necessário apenas alguns minutos por aplicativo.

<Anchor target="_blank" href="/marketers/pt/docs/other-platforms">Confira os guias de integração do SDK da AppsFlyer para</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">iOS</Anchor>, Unity e outras plataformas.

## O SDK da AppsFlyer afeta o tempo de download do aplicativo?

Os pacotes SDK da AppsFlyer são projetados e desenvolvidos para terem um efeito quase zero *no desempenho do aplicativo.* Todas as versões do SDK são leves e geralmente ocupam menos de 1% do tamanho de um aplicativo. Em outras palavras, **o efeito no tempo geral de download do aplicativo é mínimo**.

* SDK para Android: ~ 300 KB
* SDK para iOS: ~ 3,4 MB

## O SDK da AppsFlyer afeta o desempenho do aplicativo?

As APIs SDK da AppsFlyer são, principalmente, métodos *setter/getter* *ou de serviços web assíncronos rápidos que enviam/recebem* dados dos servidores da AppsFlyer. Isso significa que as APIs do SDK têm um efeito insignificante no desempenho do aplicativo.

Em outras palavras, **o SDK da** **AppsFlyer não tem efeito no desempenho do aplicativo ou na experiência do usuário**.

## Posso registrar eventos in-app que ocorrem fora do meu aplicativo?

Embora a comunicação de <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">servidor a servidor</Anchor> com a AppsFlyer seja possível, integrar o SDK (e atualizá-lo periodicamente) é o **método recomendado, pois o SDK verifica a comunicação atualizada e segura entre o aplicativo e os** servidores da AppsFlyer. Eventos S2S, uma vez gravados, estão disponíveis em toda a plataforma, incluindo painéis, dados brutos e analytics.

<div data-zendesk-anchors="how-to-install-and-update-the-appsflyer-sdk=como-instalar-e-atualizar-o-sdk-da-appsflyer h_01HSXBYM9WMD9CDX03RFHM0JY1=como-instalar-e-atualizar-o-sdk-da-appsflyer is-it-hard-to-integrate-the-appsflyer-sdk=%C3%A9-dif%C3%ADcil-integrar-o-sdk-da-appsflyer h_01HMTWQHQRGE6Z2BM1BBQY04H1=%C3%A9-dif%C3%ADcil-integrar-o-sdk-da-appsflyer does-the-appsflyer-sdk-affect-app-download-time=o-sdk-da-appsflyer-afeta-o-tempo-de-download-do-aplicativo h_01HMTWQHQRQQ47CAJCA4Y0AASZ=o-sdk-da-appsflyer-afeta-o-tempo-de-download-do-aplicativo does-the-appsflyer-sdk-affect-app-performance=o-sdk-da-appsflyer-afeta-o-desempenho-do-aplicativo h_01HMTWQHQRXBPQN75J0KM48AJ2=o-sdk-da-appsflyer-afeta-o-desempenho-do-aplicativo can-i-record-inapp-events-that-occur-outside-my-app=posso-registrar-eventos-in-app-que-ocorrem-fora-do-meu-aplicativo h_01HMTWQHQSP646Y8KVZSBA01TF=posso-registrar-eventos-in-app-que-ocorrem-fora-do-meu-aplicativo" />
