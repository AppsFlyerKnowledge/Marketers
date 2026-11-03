---
title: Integração do Xbox com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2026-08-18T00:22:38Z'
  id: 14504812967057
  locale: pt
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/pt/articles/14504812967057
---
> **Visão geral:** Integre seu aplicativo do Xbox com a AppsFlyer para receber dados de atribuição e de eventos para suas campanhas no Xbox.

## Atribuição no Xbox

O sistema operacional do Xbox para consoles e apps de CTV é executado em todos os Xbox.

Aplicativos do Xbox podem se integrar à AppsFlyer por meio da S2S API para receber dados de atribuição e mensuração de performance que informam quais canais (orgânicos) e campanhas impulsionam a abertura do aplicativo e outros eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da Xbox API é compatível com:

* Xboxes.
* Atribuição e registro de eventos para apps do Xbox. Significado, atribuição e registro no dispositivo Xbox.

## Etapas de integração

A tabela abaixo lista as etapas necessárias para integrar um app do Xbox na AppsFlyer.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app do Xbox na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integre a API da AppsFlyer</Anchor> em seu aplicativo, adicionando comandos para relatar os seguintes eventos à AppsFlyer.<ul><li>Primeira abertura do app</li><li>Eventos in-app</li><li>Sessões</li></ul>**Observação**:<ul><li>A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.</li><li>Para o parâmetro `device_ids`, selecionar o tipo `custom`.</li><li>Envie eventos usando a API. Compartilhe com seu desenvolvedor quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li></ul>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | Desenvolvedor de aplicativos |
| Configuração de relatórios | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Profissional de marketing/engenheiro de dados |

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente sem suporte |
| Dados de custo | Os dados de custos devem ser enviados através de <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> utilizando o método de upload de arquivos por e-mail. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=atribui%C3%A7%C3%A3o-no-xbox 01H7Z1NEAJMRWKHS4K168V0753=atribui%C3%A7%C3%A3o-no-xbox integration-procedures=etapas-de-integra%C3%A7%C3%A3o 01H7Z1NEAJJY4ZRVKY74ACXAAR=etapas-de-integra%C3%A7%C3%A3o 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
