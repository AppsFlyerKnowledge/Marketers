---
title: Integração com o Google Analytics — Discrepâncias
metadata:
  keywords:
    - Analytics
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
  created_at: '2021-12-07T13:38:17Z'
  edited_at: '2026-08-18T00:13:06Z'
  id: 4413026674833
  locale: pt
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/pt/articles/4413026674833
---
> **Em resumo:** Entenda as discrepâncias que podem ocorrer entre AppsFlyer e Google Analytics.

<div id="discrepancies-in-data-between-appsflyer-and-google-analytics" />

## Discrepâncias nos dados entre AppsFlyer e Google Analytics

A seguir, estão listados os motivos das discrepâncias entre AppsFlyer e Google Analytics.

<div id="high-volume-of-nonconsenting-ios-145-users" />

<Accordion title="Alto volume de usuários do iOS 14.5+ sem consentimento">

Quando <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">o AAP está habilitado para seu aplicativo</Anchor>, a AppsFlyer não envia postbacks ao Google Analytics para usuários do iOS 14.5+ sem consentimento. Caso seu aplicativo tenha um grande número desses usuários, haverá uma discrepância entre os dashboards da AppsFlyer e do Google Analytics.

</Accordion>

<div id="customer-user-id" />

<Accordion title="ID de usuário cliente">

O Google Analytics associa eventos por ID de usuário do cliente. O ID de usuário do cliente que a AppsFlyer envia por padrão é o GAID ou o IDFA.

Portanto, o Google Analytics considera usuários que reinstalam (usuários que instalam, desinstalam e depois reinstalam) como os mesmos usuários.

<div id="example" />

> 📄 **Exemplo**
>
> Um usuário instala seu aplicativo e depois o desinstala. O usuário então reinstala o aplicativo por meio de uma campanha de retargeting dentro da janela de reatribuição.
>
> O Google Analytics vê esse usuário como o mesmo usuário. No User Explorer do Google Analytics, este usuário tem todos os itens a seguir listados:
>
> * regular-install
> * regular-in-app-event
> * reattribution-install
> * reattribution-in-app-event
>
> A AppsFlyer, por outro lado, vê esse usuário como dois usuários diferentes:
>
> * Um usuário que vem de uma campanha de UA
> * Um usuário que vem de uma campanha de retargeting

Além disso, discrepâncias podem surgir se você implementar os SDKs do GA e da AppsFlyer.

</Accordion>

<div id="time-zone-differences" />

<Accordion title="Diferenças de fuso horário">

Se o fuso horário do seu dashboard do GA for diferente do fuso horário do seu aplicativo na AppsFlyer, os dados podem não se alinhar.

<div id="example-1" />

> 📄 **Exemplo**
>
> O dashboard do seu aplicativo está configurado para GMT+13, e o dashboard do GA está configurado para GMT. Isso significa que o dashboard do seu aplicativo está um dia à frente do dashboard do GA.
>
> Portanto, os dados que aparecem no dashboard do GA em 2 de março só aparecem no dashboard do seu aplicativo se você selecionar 3 de março no filtro de intervalo de datas.

</Accordion>

<div id="duplicate-events" />

<Accordion title="Eventos duplicados">

Se os eventos ocorrerem próximos uns dos outros, tanto a AppsFlyer quanto o Google Analytics poderão descartá-los como eventos duplicados. O <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#how-does-appsflyer-handle-event-deduplication">mecanismo de desduplicação de eventos</Anchor> da AppsFlyer é diferente daquele usado pelo Google Analytics.

Como a AppsFlyer e o Google Analytics desduplicam eventos de maneiras diferentes, pode haver discrepâncias nos dados de eventos.

</Accordion>

<div id="session-count" />

<Accordion title="Contagem de sessões">

A AppsFlyer contabiliza sessões sempre que o aplicativo é aberto ou retorna para o primeiro plano. O Google Analytics contabiliza sessões de acordo com o CID (ID de usuário do cliente) e a atividade.

<div id="example-2" />

> 📄 **Exemplo**
>
> Um usuário abre seu aplicativo, realiza algumas ações e depois envia o aplicativo para o segundo plano. Em seguida, o usuário repete o processo 4 vezes, sempre em um intervalo de cerca de 5 minutos.
>
> Para a AppsFlyer, isso conta como 5 sessões diferentes. No entanto, para o Google Analytics, isso conta como uma única sessão.

Para saber mais sobre como a AppsFlyer e o Google Analytics calculam sessões, confira os recursos abaixo.

1. <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions">Como a AppsFlyer contabiliza sessões</Anchor>
2. <Anchor target="_blank" href="https://support.google.com/analytics/answer/2731565?hl=en">Sessões do Google Analytics</Anchor>

</Accordion>

<div id="google-analytics-views-and-filters" />

<Accordion title="Visualizações e filtros do Google Analytics">

O Google Analytics permite criar diferentes visualizações e aplicar diferentes filtros a elas. Ao comparar dados da AppsFlyer e do Google Analytics, confira se você está visualizando os dados na visualização ***All Web Site Data*** do Google Analytics.

</Accordion>

<div data-zendesk-anchors="discrepancies-in-data-between-appsflyer-and-google-analytics=discrep%C3%A2ncias-nos-dados-entre-appsflyer-e-google-analytics h_01HDP3G48R2XXEQDEAAJYGR9V9=discrep%C3%A2ncias-nos-dados-entre-appsflyer-e-google-analytics h_01HDP3G48RQD3EW0DTRE2252JF=high-volume-of-nonconsenting-ios-145-users h_01HDP3G48RPWDY7ZRG9HM1F5AR=customer-user-id h_01HDP3G48RMGSJSWQDSKW5DXD9=exemplo h_01HDP3G48R2JWF3Y23011NDCAN=time-zone-differences h_01HDP3G48RXFWZX4FQ0V2ZE44D=exemplo-1 h_01HDP3G48RHT7PWSWZZAG27CP0=duplicate-events h_01HDP3G48R1044364MF96QX41E=session-count h_01HDP3G48RHQ3VG6N4HTT1KJFS=exemplo-2 h_01HDP3G48R9571AS0WH7TWQWJP=google-analytics-views-and-filters" />
