---
title: >-
  Boletim: Atribuição da primeira instalação para eventos in-app que ocorrem
  após a reinstalação
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-05T15:04:01Z'
  edited_at: '2026-08-19T00:19:00Z'
  id: 25676426941457
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/25676426941457
---
| **Novidades** | Essa melhoria atribui todos os <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#eventos-in-app-pós-instalação">eventos in-app</Anchor> e sessões após um reengajamento ou <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#reattribution">reatribuição</Anchor> à fonte de mídia original que impulsionou essa ação ("primeira instalação") em vez de rotulá-los como "orgânico não atribuído".<br /><br />![Screenshot 2024-06-11 at 8.44.30.png](https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png) |
| --- | --- |
| **Data de início** | 31 de julho de 2024 31 de julho de 2024 31 de julho de 2024 O modo de primeira instalação (first-install mode) se aplica automaticamente apenas a aplicativos adicionados à AppsFlyer durante ou após a data de efetivação. Para aplicativos adicionados antes de 31 de julho de 2024, recomendamos entrar em contato com a AppsFlyer para migrar seus aplicativos existentes para o modo de primeira instalação. |
| **Pré-requisitos** | Nenhuma. |
| **Ações necessárias** | Nenhuma. |
| **O que devo saber?** | Somente usuários que consentiram em compartilhar seu identificador de dispositivo (como IDFA ou GAID) com o aplicativo após a instalação e reinstalação terão seus eventos in-app atribuídos à instalação original Caso contrário, eles serão rotulados como "orgânicos não atribuídos". Caso contrário, eles serão rotulados como "orgânicos não atribuídos". |
| **Qual o impacto?** | <ul><li>Para aplicativos adicionados à AppsFlyer **após 31 de julho de 2024**: Sem alteração</li><li>Para aplicativos adicionados **antes de 31 de julho de 2024**, recomendamos entrar em contato com a AppsFlyer para migrar seus aplicativos existentes para o modo de primeira instalação. Após a migração, pode ocorrer o seguinte:<ul><li>Um aumento potencial no número de eventos e sessões in-app atribuídos à primeira instalação após uma reinstalação, juntamente com uma diminuição correspondente nas atribuições classificadas como "orgânicas" para tais eventos.</li><li>Um aumento potencial na contagem de MAU (Monthly Active Users) para fontes de mídia originalmente atribuídas e uma diminuição na contagem de MAU para fontes orgânicas.</li><li>No dia em que o aplicativo muda para o modo de primeira instalação, a contagem da sessão acaba sendo duplicada. Como resultado, a taxa de retenção no dia 1 para o cohort é mais alta que o esperado.</li></ul></li></ul> |