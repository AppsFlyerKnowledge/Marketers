---
title: Recriar relatórios clássicos em relatórios avançados
metadata:
  keywords:
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2026-06-15T08:16:54Z'
  edited_at: '2026-08-18T00:05:01Z'
  id: 47741416390161
  locale: pt
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/pt/articles/47741416390161
---
> **Em resumo:** Se você estiver migrando dos relatórios brutos clássicos do Data Locker, use este guia para encontrar as seleções exatas de filtros que reproduzem cada relatório clássico nos <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">Relatórios avançados</Anchor>.

## Escritórios

O Data Locker clássico entregava a jornada do usuário em vários tópicos de relatório separados. Os Relatórios avançados consolidam tudo isso em um relatório por produto de dados, cujo escopo você reduz usando filtros no nível do relatório.

Os três Relatórios avançados e os tópicos clássicos que eles substituem são:

* O **relatório avançado** de **Engagements** substitui os tópicos clássicos de cliques e impressões.
* O **relatório avançado** de **Conversions** substitui os tópicos clássicos de instalações, conversões de retargeting e instalações de CTV.
* O **relatório avançado** de **End-user events** substitui os tópicos clássicos de eventos in-app, sessões, eventos in-app de CTV, sessões de CTV e desinstalações.

Para recriar um relatório clássico específico, aplique os filtros no nível do relatório descritos nas seções abaixo. Para ver a lista completa de filtros disponíveis por relatório, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports#filtros-no-nível-do-relatório">Filtros no nível do relatório</Anchor>.

## Recriar relatórios clássicos no relatório avançado Engagements

No Relatório avançado Engagements, defina o filtro **Tipo de campanha** para corresponder à categoria do relatório clássico (por exemplo, Aquisição de usuários ou retargeting) e o filtro **Tipo de engajamento** para corresponder ao tipo de evento (por exemplo, cliques ou impressões).

| Relatório clássico | Filtro de tipo de campanha | Filtro de tipo de engajamento |
| --- | --- | --- |
| Aquisição de usuários – Cliques | Aquisição de usuários | `Clique` + `Clique engajado` |
| Aquisição de usuários – impressões | Aquisição de usuários | `View` + `Engaged view` |
| Retargeting – Cliques | Redirecionamento | `Clique` + `Clique engajado` |
| Retargeting – Impressões | Redirecionamento | `View` + `Engaged view` |

## Recriar relatórios clássicos no relatório avançado Conversions

No Relatório avançado Conversions, defina o filtro **Tipo de conversão** para corresponder à categoria do relatório clássico (por exemplo, Aquisição de usuários ou retargeting) e o filtro **Grupo de plataformas** para corresponder à plataforma (por exemplo, mobile ou CTV).

| Relatório clássico | Filtro de tipo de conversão | Filtro de grupo de plataforma | O que você pensa sobre isso |
| --- | --- | --- | --- |
| Aquisição de usuários – Instalações | Aquisição de usuários | Mobile | <ul><li>O valor do campo `conversion_name` é `INSTALL`.</li><li>Abrange instalações orgânicas e não orgânicas.</li></ul> |
| Retargeting – Conversões | Redirecionamento | Mobile | <ul><li>O valor do campo `conversion_name` é `RE-ENGAGEMENT` ou `RE-ATTRIBUTION`.</li><li>Abrange apenas instalações não orgânicas.</li></ul> |
| CTV – Instalações | Aquisição de usuários | CTV | <ul><li>O valor do campo `conversion_name` é `INSTALL`.</li><li>Abrange instalações orgânicas e não orgânicas.</li></ul> |

## Recrie relatórios clássicos no relatório avançado de eventos do usuário final

No Relatório avançado de eventos do usuário final, defina o filtro **Tipo de conversão** para corresponder à categoria do relatório clássico (por exemplo, Aquisição de usuários ou retargeting) e o filtro **Grupo de plataforma** para corresponder à plataforma (por exemplo, mobile ou CTV).

| Relatório clássico | Filtro de tipo de evento do usuário final | Filtro de tipo de conversão | Filtro de grupo de plataforma | O que você pensa sobre isso |
| --- | --- | --- | --- | --- |
| Aquisição de usuários – Eventos in-app | `No aplicativo` | Aquisição de usuários | Mobile | <ul><li>Abrange eventos in-app orgânicos e não orgânicos.</li></ul> |
| Retargeting – Eventos in-app | `No aplicativo` | Redirecionamento | Mobile | <ul><li>Abrange apenas eventos in-app não orgânicos.</li><li>Defina **É atribuição primária** como `True` para desduplicar eventos de retargeting publicados mais de uma vez.</li></ul> |
| Aquisição de usuários – Sessões | `Sessão` | Aquisição de usuários | Mobile | <ul><li>Abrange sessões orgânicas e não orgânicas.</li></ul> |
| Retargeting – Sessões | `Sessão` | Redirecionamento | Mobile | <ul><li>Abrange apenas não orgânico.</li></ul> |
| CTV – Eventos in-app | `No aplicativo` | qualquer valor | CTV |  |
| CTV – Sessões | `Sessão` | qualquer valor | CTV |  |

## Especificações e limitações

| Caraterística | A descrição |
| --- | --- |
| Relatórios não reproduzíveis | Engajamentos entre plataformas, reinstalações e reinstalações orgânicas não são reproduzíveis usando os relatórios avançados. |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">Sobre os Relatórios avançados do Data Locker</Anchor>

<div data-zendesk-anchors="about-recreating-classic-reports=escrit%C3%B3rios h_01KV55PGFSSE3GWZ9ZW0TXSVNB=escrit%C3%B3rios reproduce-classic-reports-in-the-engagements-advanced-report=recriar-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-engagements h_01KV55PGFSBHV59ZA7KFVQVM1S=recriar-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-engagements reproduce-classic-reports-in-the-conversions-advanced-report=recriar-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-conversions h_01KV55PGFSK35M9XC7EHVDX53X=recriar-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-conversions reproduce-classic-reports-in-the-end-user-events-advanced-report=recrie-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-de-eventos-do-usu%C3%A1rio-final h_01KV55PGFSCD4AQQWRBY0MHJGK=recrie-relat%C3%B3rios-cl%C3%A1ssicos-no-relat%C3%B3rio-avan%C3%A7ado-de-eventos-do-usu%C3%A1rio-final traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KV55PGFSF8QVSBAWA3XN7A8W=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KV8SEHV9KVY6R5HQA6K2M2JZ=consulte-tamb%C3%A9m" />
