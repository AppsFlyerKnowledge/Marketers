---
title: Discrepâncias entre a atribuição da AppsFlyer e das lojas de aplicativos
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2026-08-18T00:09:48Z'
  id: 207040726
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/207040726
---
> **Visão geral**: descubra as principais causas de discrepâncias entre a atribuição da AppsFlyer e das lojas de aplicativos, além de acessar dicas para minimizar esse problema.

## Discrepâncias de atribuição

Existem diferenças inerentes nos modelos de atribuição usados por todos os players no ecossistema mobile. O mesmo se aplica à AppsFlyer e às principais lojas de aplicativos: (iOS) App Store e (Android) Google Play. **Observação**: nesse artigo, as duas lojas serão chamadas de loja(s) de aplicativos.

Em alguns casos, por conta das diferenças nos modelos de atribuição, a loja de aplicativos registra mais instalações do que a AppsFlyer. Em acontece o contrário, ou seja, a AppsFlye registra mais instalações que a loja de aplicativos.

<Image alt="AF_vs_app_stores.png" src="https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png" width="605px" />

> 📘 **Observação**
>
> Discrepâncias não afetam a precisão da contagem de instalações **não orgânicas** porque o modelo de atribuição da AppsFlyer credita uma instalação por clique no anúncio. Isso se aplica até a um usuário específico que possui mais de um dispositivo registrado na loja de aplicativos.

### Por que a AppsFlyer faz menos atribuições

Veja abaixo os motivos para que isso aconteça:

| Causa | Lojas de aplicativos | A AppsFlyer | Dica da AppsFlyer |
| --- | --- | --- | --- |
| **Definições das instalações** | As lojas de aplicativos registram instalações depois que o usuário baixa e instala um app, mesmo que depois o usuário não abra o aplicativo. | A AppsFlyer registra novas instalações somente após a primeira abertura do app.<br /><br />**Os usuários que nunca abrem um app não são contados na AppsFlyer**, mesmo que eles façam o download e a instalação (segundo as definições das lojas de aplicativos). | Cerca de 90% dos downloads de aplicativos mobile resultam em pelo menos uma abertura, mas isso pode variar significativamente em diferentes regiões geográficas e verticais. |
| **Data de registro da instalação** | As lojas de aplicativos gravam a data do download como o dia da instalação. | A AppsFlyer grava a data da primeira abertura do app como o dia da instalação. | Na AppsFlyer, use períodos de tempo mais longos como seu intervalo de datas de query (consulta) para minimizar essa discrepância. |
| **Fusos horários** | Os dados são exibidos de acordo com o fuso horário local do anunciante. | Por padrão, os dados são exibidos usando o fuso horário UTC±00:00. | Você pode definir um fuso horário no aplicativo para reduzir essa discrepância (<Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">detalhes aqui</Anchor>). |
| **O usuário do Android desinstala e reinstala dentro da janela de reatribuição definida** | Em algumas visualizações, o Google Play mostra **duas** **instalações** para o mesmo usuário, sem considerar o tempo decorrido desde a primeira instalação. Outras visualizações mostram **usuários únicos** e, portanto, estão mais alinhadas com a AppsFlyer. | Dentro da janela de reatribuição (por padrão, 3 meses) a partir da hora da instalação original, o usuário que reinstala não é considerado como novo. | Você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">definir a janela de reatribuição</Anchor> de 1 a 24 meses. |
| **Um usuário do iOS desinstala e reinstala dentro da janela de reatribuição definida** | O iTunes conta uma nova instalação sempre que o usuário desinstala e reinstala. | Dentro da janela de reatribuição (por padrão, 3 meses) a partir da hora da instalação original, o usuário que reinstala não é considerado como novo. | Você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">definir a janela de reatribuição</Anchor> de 1 a 24 meses. |

### Por que a AppsFlyer faz mais atribuições

Veja abaixo os motivos para que isso aconteça:

| Causa | Lojas de aplicativos | A AppsFlyer | Dica da AppsFlyer |
| --- | --- | --- | --- |
| **Atualização de uma instalação existente de uma versão que não continha o SDK da AppsFlyer para uma versão que contém o SDK da AppsFlyer** | As lojas de aplicativos consideram isso como o mesmo usuário, não como uma nova instalação. | A AppsFlyer mostra a atualização como instalação orgânica. | <ul><li>Esse pico geralmente apresenta uma queda após alguns dias, conforme a maioria dos usuários termina de atualizar o aplicativo.</li><li>Novas contas podem <Anchor target="_blank" href="/marketers/pt/docs/migration-to-appsflyer-from-other-vendors#migração-de-dispositivosopcional">migrar seus usuários existentes</Anchor> para a AppsFlyer para evitar esse salto</li></ul> |
| **Fraudes de reset de device ID e Limit Ad Tracking** | As lojas de aplicativos consideram isso como o mesmo usuário, não como uma nova instalação. | A AppsFlyer interpreta essa ocorrência como uma nova instalação em um novo dispositivo. | Nossa <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">solução antifraudes, Protect360,</Anchor> detecta se seu aplicativo está sofrendo esses tipos de fraudes. |
| **Instalações provenientes <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">de mercados fora da loja</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-factory-preinstall-using-manifest-android">pré-instalações</Anchor>** | O Google Play não registra essas instalações. | A AppsFlyer conta essas instalações. | Se você estiver anunciando em um <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">mercado fora da loja</Anchor>, consulte nossa documentação e faça a configuração correta. |
| **O usuário do Android desinstala e reinstala após a janela de reatribuição definida expirar** | Em algumas visualizações, o Google Play mostra usuários únicos (independentemente do tempo decorrido desde a primeira instalação), enquanto outras visualizações mostram duas instalações únicas para o mesmo usuário e, portanto, estão mais alinhadas com a AppsFlyer. | Quando a janela de reatribuição (3 meses por padrão) expira, a reinstalação é considerada uma nova instalação regular na AppsFlyer. Isso significa que o mesmo usuário é contabilizado duas vezes. | Você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">definir a janela de reatribuição</Anchor> de 1 a 24 meses. |

<div data-zendesk-anchors="attribution-discrepancies=discrep%C3%A2ncias-de-atribui%C3%A7%C3%A3o h_01HNWP7A6GQC5ZX6WKBW411DVG=discrep%C3%A2ncias-de-atribui%C3%A7%C3%A3o h_01HNWP7A6GZJS246548Q5AFPZR=observa%C3%A7%C3%A3o why-appsflyer-attributes-less=por-que-a-appsflyer-faz-menos-atribui%C3%A7%C3%B5es h_01HNWP7A6G85PR1R66Q3KCRPNW=por-que-a-appsflyer-faz-menos-atribui%C3%A7%C3%B5es why-appsflyer-attributes-more=por-que-a-appsflyer-faz-mais-atribui%C3%A7%C3%B5es h_01HNWP7A6GVVWMV6HECXQFTJT6=por-que-a-appsflyer-faz-mais-atribui%C3%A7%C3%B5es" />
