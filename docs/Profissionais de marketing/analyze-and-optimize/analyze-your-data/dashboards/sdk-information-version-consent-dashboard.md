---
title: Dashboard de informações do SDK (versão e consentimento)
metadata:
  keywords:
    - SDK Information
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2026-08-18T00:04:17Z'
  id: 115000805366
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/115000805366
---
> **Visão geral:** Visão do dashboard das taxas de adoção do SDK e do sistema operacional (iOS, Android), além das métricas de consentimento do ATT no iOS.

## Dashboard de adoção de versão e consentimento do ATT

Os dados no dashboard são derivados do evento af\_open (sessão) e não estão relacionados a eventos de instalação. O dashboard tem as seguintes seções principais: 

* Informações da versão do SDK; disponíveis para todas as plataformas (Android e  iOS)
* Métricas de consentimento do ATT e adoção do iOS 16.1+ (que oferece o potencial de dados do SKAN 4)

**Para visualizar o dashboard de informações do SDK**:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Informações do SDK**.
2. Defina o período da atividade.   
   As métricas apresentadas são descritas nas seções a seguir.

<div id="sdk-information-ios-and-android" />

<Accordion title="Informações do SDK (iOS e Android)">

A seguir, são mostradas as métricas de versão disponíveis para aplicativos iOS e Android usando a data mais recente de abertura (inicialização) do aplicativo

| Usuários por | Exemplo |
| --- | --- |
| Receita | Observe a introdução da versão V1.4.28 do aplicativo em 20 de maio de 2021<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| Versão do SDK | Observe a introdução do SDK V6.1.4 em 20 de maio de 2021<br /><br />[![UsersBySDKVersion.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| Versão do sistema operacional | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| Tipo do dispositivo | [![UsersByDevice.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS e métricas do ATT">

A versão do iOS adotada pelos seus usuários pode influenciar o tipo de dados disponível. Por exemplo, se os usuários tiverem iOS 16.1+, os dados do SKAN 4 estarão potencialmente disponíveis.

O <Anchor target="_blank" href="/marketers/pt/docs/att-implications-ios-14-and-deprecation-of-lat">status do ATT</Anchor> é definido pelo iOS e reportado à AppsFlyer pelo seu aplicativo. Os possíveis valores de status do ATT são:

* **Autorizado**: o usuário concedeu consentimento explícito para ser rastreado
* **Negado**: o usuário explicitamente não concordou em ser rastreado ou o LAT estava ativado antes de o usuário atualizar para o iOS 14+
* **Não determinado**: o prompt de ATT não foi exibido ou o usuário não respondeu
* **Restrito**: a Apple não permite que o usuário seja rastreado

**Considere o seguinte:**

* As métricas do gráfico são calculadas usando eventos únicos de abertura do aplicativo por usuário em uma determinada data. Ou seja, se um usuário não abriu o aplicativo em uma determinada data, ele não é contabilizado nas métricas dessa data.
* iOS and ATT metrics only include the <Anchor target="_blank" href="/marketers/pt/docs/att-implications-ios-14-and-deprecation-of-lat#valores-att-definidos-pela-apple">valores de ATT definidos pela Apple</Anchor>; não valores adicionais definidos pela AppsFlyer.
* As métricas da taxa de consentimento são calculadas usando a fórmula: Autorizado / (Autorizado + Negado) x 100

#### Métricas de adoção do iOS e de ATT para aplicativos iOS

| Gráfico | Exemplo e observações |
| --- | --- |
| O status da ATT do aplicativo é aberto | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />Refere-se a usuários com iOS 14+ que abrem o aplicativo em uma determinada data. Isso significa que as métricas exibem o status de ATT do usuário na data especificada. |
| Consentimento por versão do aplicativo | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| Tendência de consentimento | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| Taxa de adoção de usuários do iOS 16.1 | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="version-adoption-and-att-consent-dashboard=dashboard-de-ado%C3%A7%C3%A3o-de-vers%C3%A3o-e-consentimento-do-att h_01HGX98Q4FRVS2B35BVT683D5W=dashboard-de-ado%C3%A7%C3%A3o-de-vers%C3%A3o-e-consentimento-do-att h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 att-and-ios-adoption-metrics-for-ios-apps=m%C3%A9tricas-de-ado%C3%A7%C3%A3o-do-ios-e-de-att-para-aplicativos-ios h_01HGX98Q4G0C4XTC1DSVP96M19=m%C3%A9tricas-de-ado%C3%A7%C3%A3o-do-ios-e-de-att-para-aplicativos-ios" />
