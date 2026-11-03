---
title: Integração do Amazon Vega OS com AppsFlyer
metadata:
  keywords:
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-01-19T07:36:38Z'
  edited_at: '2026-08-18T00:22:40Z'
  id: 42971481283601
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/42971481283601
---
> **Visão geral:** Integre seu aplicativo de TV conectada (CTV) do Amazon Vega OS com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas no Amazon Vega OS.

## **Sobre a atribuição de CTV do Amazon Vega OS**

O Amazon Vega OS para streaming funciona em todos os dispositivos Amazon Vega OS.

Os aplicativos de CTV em streaming no Amazon Vega OS podem se integrar com a AppsFlyer via API para receber dados de atribuição e mensuração de performance sobre quais fontes (orgânicas) e campanhas impulsionam a abertura do aplicativo e os eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da API do Amazon Vega OS oferece suporte a:

* Smart TVs com Amazon Vega OS.
* Atribuição CTV-to-CTV e registro de eventos. Ou seja, atribuição e registro no dispositivo Amazon Vega OS do usuário.

## **Procedimentos de integração**

A tabela abaixo lista as tarefas necessárias para integrar seu aplicativo de CTV do Amazon Vega OS com a AppsFlyer. Para registrar seu progresso, faça o download desta [planilha](https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx).

| **Função** | **Ações** | **Quem está envolvido** |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li>[Crie uma conta](https://www.appsflyer.com/get-started/)</li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu aplicativo de CTV do Amazon Vega OS no AppsFlyer</Anchor> usando a <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#amazon-vega-os">estrutura de ID do aplicativo Amazon Vega</Anchor>.</li></ul> | Marketer |
| Integração da API com o seu app (via S2S) | [Integre a API de CTV do AppsFlyer](https://dev.appsflyer.com/hc/reference/overview-4) ao seu aplicativo de CTV com comandos para reportar os seguintes eventos ao AppsFlyer.<ul><li>Primeira abertura do app</li><li>https://support.appsflyer.com/hc/article_attachments/19284078965009</li><li>Sessions</li></ul>**Nota**<ul><li>As instalações devem ser relatadas antes de eventuais eventos in-app e sessões.</li><li>Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li><li>Para o parâmetro `device_ids` , selecione o tipo `vegaid`.</li><li>Para reportar engajamentos de mídias próprias, integre a [API de engajamento de impressões](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)</li></ul> | Desenvolvedor do aplicativo |
| Configuração do OneLink | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em painéis e relatórios</Anchor> | Profissional de marketing/engenheiro de dados |

## Especificações e limitações

| Caraterística | Observações |
| --- | --- |
| Canais não orgânicos | Em breve |
| Redirecionamento | Atualmente não compatível |
| Dados de custos | <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Os dados de custos devem ser enviados através de</Anchor> Cost Import utilizando o método de upload de arquivos por e-mail. |

### **Consulte também**

* <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral das plataformas CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-amazon-vega-os-ctv-attribution=sobre-a-atribui%C3%A7%C3%A3o-de-ctv-do-amazon-vega-os h_01KFAJYYX01B4E6CDMCH6REGY9=sobre-a-atribui%C3%A7%C3%A3o-de-ctv-do-amazon-vega-os integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o h_01KFAJYYX0WZY682B0SSWJM40V=procedimentos-de-integra%C3%A7%C3%A3o traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KFAJYYX0E95XEYQCQPCTN700=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es see-also=consulte-tamb%C3%A9m h_01KFAJYYX00K3RKMYB9QX6KXKN=consulte-tamb%C3%A9m" />
