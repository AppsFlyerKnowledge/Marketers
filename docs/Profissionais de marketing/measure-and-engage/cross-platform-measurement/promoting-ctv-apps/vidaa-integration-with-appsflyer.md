---
title: Integração da Vizio com a AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-08-18T00:22:53Z'
  id: 10400222972433
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/10400222972433
---
> **Visão geral:** Integre seu aplicativo Vidaa Connected TV (CTV) com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas na Vidaa.

<div id="about-vidaa-ctv-attribution" />

## Sobre a atribuição da Vidaa CTV

O sistema operacional Vidaa para streaming funciona em todas as TVs da Vidaa.

Os aplicativos de streaming na Vidaa podem se integrar com a AppsFlyer via API para receber dados de atribuição e mensuração de performance, indicando quais canais (orgânicos e não orgânicos) e campanhas impulsionam a abertura do app e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da Vidaa API é compatível com:

* Smart TVs Vidaa.
* Atribuição CTV-to-CTV e registro de eventos. Significado, atribuição e registro em um dispositivo Vidaa.

<div id="integration-procedures" />

## Etapas de integração

A tabela abaixo lista as etapas necessárias para integrar um app da Vidaa CTV na AppsFlyer. Para registrar seu progresso, faça o download dessa <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">planilha</Anchor>.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app da Vidaa na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integre a API da AppsFlyer</Anchor> em seu aplicativo, adicionando comandos para relatar os seguintes eventos à AppsFlyer.<ul><li>Primeira abertura do app</li><li>Eventos in-app</li><li>Sessões</li></ul>**Observação**:<ul><li>A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.</li><li>Envie eventos usando a API. Compartilhe com seu desenvolvedor quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li><li>Para o parâmetro`device_ids` , selecionar o tipo `custom`.</li></ul>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | Desenvolvedor de aplicativos |
| Configuração do link | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Profissional de marketing/engenheiro de dados |

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Canais não orgânicos | Em breve |
| Redirecionamento | Atualmente sem suporte |
| Dados de custo | Os dados de custos devem ser enviados através de <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> utilizando o método de upload de arquivos por e-mail. |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=sobre-a-atribui%C3%A7%C3%A3o-da-vidaa-ctv 01H7Z180QRR77E1GBQ0P0RHVN5=sobre-a-atribui%C3%A7%C3%A3o-da-vidaa-ctv integration-procedures=etapas-de-integra%C3%A7%C3%A3o 01H7Z180QR6HT4R3N9DYSM8WB9=etapas-de-integra%C3%A7%C3%A3o 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
