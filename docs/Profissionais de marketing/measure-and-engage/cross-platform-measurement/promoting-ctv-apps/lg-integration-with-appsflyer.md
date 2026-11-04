---
title: Integração da LG com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Developers
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
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-08-19T00:22:00Z'
  id: 7341725624081
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/7341725624081
---
> **Resumo:** Integre seu aplicativo da LG Connected TV (CTV) com a AppsFlyer para receber dados de atribuição e de eventos para suas campanhas na LG.

<div id="about-lg-ctv-attribution" />

## A atribuição da LG CTV

O sistema operacional LG Web para streaming funciona em todas as TVs da LG.

Os aplicativos de streaming na LG podem se integrar com a AppsFlyer via API para receber dados de atribuição e mensuração da performance, indicando quais canais (orgânicos e não orgânicos) e campanhas impulsionam a abertura do app e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da LG API é compatível com:

* Smart TVs da LG.
* Atribuição CTV-to-CTV e registro de eventos. Significado, atribuição e registro em um dispositivo LG.

<div id="integration-procedures" />

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar um app da LG CTV na AppsFlyer.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app da LG na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S ou SDK) | Existem dois métodos de integração que podem ser utilizados: S2S e SDK.<br /><br />Para o método S2S, integre a API da AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">em seu aplicativo, adicionando comandos para relatar os seguintes eventos à AppsFlyer.</Anchor><ul><li>Primeiras aberturas do app</li><li>Eventos in-app</li><li>Sessões</li></ul>**Observação**:<ul><li>A primeira abertura do app deve ser relatada antes de eventuais eventos in-app e sessões.</li><li>Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li></ul>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor><br /><br />Para o método SDK, consulte o hub de desenvolvedores para a <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">documentação da LG</Anchor>. | Desenvolvedor do aplicativo |
| Integração de parceiros | Adicione a LG Ads como uma ad network (parceiro integrado) na AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#a-activate-partner">Ativar parceiro</Anchor></li><li>[Opcional] Ativar a<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#e-install-attribution">**atribuição de view-through**.</Anchor></li></ol> | Marketer |
| Configuração do link | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Profissional de marketing/Engenheiro de dados |

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente não compatível |
| Dados de custo | Os dados de custos devem ser enviados através de <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> utilizando o método de upload de arquivos por e-mail. |
| Atribuição | A LG Ads utiliza modelação probabilística para atribuição; o ID matching não está disponível no momento. |
| Customer ID | Preencha esse parâmetro com o Customer ID da LG (`cust_id`) obtido da LG Ads. |
| Atribuição determinística | Há uma opção para ativar a correspondência determinística do ID do anúncio para atribuição. Para isso, é necessário que:<ul><li>A LG deve realizar uma análise jurídica antes que os aplicativos de parceiros de conteúdo possam ser habilitados para exibir o ID do anúncio.</li><li>Essa análise jurídica envolve o parceiro de conteúdo trabalhando diretamente com a LG Electronics e exige que ambas as partes assinem um acordo jurídico.</li><li>Os aplicativos de parceiros de conteúdo devem integrar a funcionalidade para coletar e transmitir o ID do anúncio da LG e lançar uma atualização do aplicativo iniciada pelo usuário para começar a exibir o ID do anúncio para a AppsFlyer.</li><li>Para mais informações, entre em contato com o seu CSM da AppsFlyer e  com [partnerships@lgads.tv](mailto:partnerships@lgads.tv)</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral das plataformas CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-lg-ctv-attribution=a-atribui%C3%A7%C3%A3o-da-lg-ctv 01H7Z17N0YAAGTDPMGZ89F7AVB=a-atribui%C3%A7%C3%A3o-da-lg-ctv integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z17N0Y8RE5PS15N2JG5NRH=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
