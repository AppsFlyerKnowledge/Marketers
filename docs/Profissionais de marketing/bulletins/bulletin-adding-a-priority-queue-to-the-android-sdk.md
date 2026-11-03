---
title: 'Boletim: adicionando uma fila de prioridade ao SDK do Android'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-19T13:46:02Z'
  edited_at: '2026-10-20T03:56:38Z'
  id: 6971914107025
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/6971914107025
---
| **Novidades** | Na versão 6.7.0, introduzimos algumas mudanças na forma como o SDK lida com as várias solicitações aos servidores da AppsFlyer.<br /><br />Percebemos que há aplicativos que tentam enviar eventos in-app antes de iniciar o SDK. Com essa mudança, garantimos que tudo seja executado na ordem correta. |
| --- | --- |
| **O que vai mudar?** | **Antes da mudança**: nas versões anteriores do SDK, o aplicativo podia enviar eventos in-app para a AppsFlyer antes de chamar o método `start` do SDK (ou seja, antes de a conversão ser enviada ao servidor).<br /><br />**Depois da mudança**: a partir desta versão, a solicitação de conversão é priorizada, e todos os eventos in-app que ocorrem antes da chamada de `start` são armazenados e aguardam o envio da solicitação de conversão. |