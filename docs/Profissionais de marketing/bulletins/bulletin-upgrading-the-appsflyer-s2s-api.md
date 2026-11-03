---
title: 'Boletim: Atualização da API S2S da AppsFlyer'
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
  created_at: '2023-11-28T16:26:35Z'
  edited_at: '2026-04-30T17:21:39Z'
  id: 20509378973457
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/20509378973457
---
| **Novidades** | Para oferecer uma experiência mais segura no uso de APIs e reduzir fraudes, a AppsFlyer atualizou a API de servidor para servidor para eventos in-app. O endpoint atual será futuramente descontinuado, mas recomendamos que você já comece a planejar a transição.<br /><br />A AppsFlyer está desenvolvendo uma solução para parceiros de tecnologia externos que enviam dados em seu nome. |
| --- | --- |
| **Data de início** | 12 de dezembro de 2023 |
| **Pré-requisitos** | Apenas um administrador pode atualizar a nova API S2S. |
| **Ação necessária** | Atualize os campos abaixo para enviar eventos in-app S2S para a AppsFlyer:<ol><li>Acesse <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_s2s_inappevent">esta página</Anchor>.</li><li>Substitua a URL:<br />De <Anchor target="_blank" href="https://api2.appsflyer.com/inappevent">https://api2.appsflyer.com/inappevent</Anchor><br />Para <Anchor target="_blank" href="https://api3.appsflyer.com/inappevent">https://api3.appsflyer.com/inappevent</Anchor></li><li>Atualize o cabeçalho de autorização: substitua a dev key pela <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">**nova chave S2S**</Anchor>.</li><li>Se você envia eventos S2S para a AppsFlyer por meio de um parceiro integrado (como Segment, Tealium, Amplitude, mParticle, RevenueCat ou outros), entre em contato com seu parceiro para descobrir como atualizar a integração.</li></ol> |
| **Ação recomendada** | **Antes de atualizar a nova API em todas as suas chamadas em produção:**<br /><br />Recomendamos enviar alguns eventos in-app de teste para o novo endpoint e **garantir que nenhum erro seja retornado**. |
| **O que você precisa saber** | Se você tiver dúvidas sobre os eventos de fraude enviados para o endpoint antigo após atualizar a nova API, entre em contato com seu CSM ou com a equipe da AppsFlyer. Certifique-se de incluir os IDs de aplicativos relevantes.<br /><br />Após concluir a migração, a AppsFlyer bloqueará o antigo endpoint da API para esses aplicativos, assim todas as chamadas fraudulentas serão bloqueadas. |
| **Quem precisa atualizar a nova API?** | Somente os anunciantes devem atualizar a nova API S2S para eventos in-app. |
| **Sobre a API S2S** | Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">tokens de API e S2S</Anchor>. |