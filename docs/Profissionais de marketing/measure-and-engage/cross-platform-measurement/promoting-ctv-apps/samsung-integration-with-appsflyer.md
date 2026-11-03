---
title: Integração da Samsung com a AppsFlyer
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-06T00:11:38Z'
  id: 5860544738065
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/5860544738065
---
> **At a glance:** Integre seu aplicativo Samsung Connected TV (CTV) com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas na Samsung.

## Sobre a atribuição da Samsung CTV

O Samsung Tizen para streaming funciona em todas as TVs da Samsung.

Os aplicativos de streaming CTV na Samsung podem se integrar à AppsFlyer via API para receber dados de atribuição e mensuração de performance sobre quais fontes (orgânicas e não orgânicas) e campanhas impulsionam a abertura do aplicativo e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da Samsung API é compatível com:

* Samsung Smart TVs.
* Atribuição de CTV para CTV e registro de eventos, o que significa que a atribuição e o registro ocorrem no dispositivo Samsung do usuário.

### Fluxo de atribuição da Samsung

![[CONFIRM: Diagrama do fluxo de atribuição de CTV da Samsung, mostrando dados de instalação, sessão e eventos in-app sendo movidos do aplicativo Samsung para a AppsFlyer via API S2S ou SDK]](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

## Procedimentos de integração

A tabela abaixo lista as etapas necessárias para integrar um app da Samsung CTV na AppsFlyer.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | Para integrar seu aplicativo CTV da Samsung à AppsFlyer:<ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários de conta com as permissões adequadas</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app da Samsung na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S ou SDK) | Há dois métodos de integração que você pode usar: server-to-server (S2S) e SDK.<br /><br />Para o método S2S, integre a API da AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">em seu aplicativo, adicionando comandos para relatar os seguintes eventos à AppsFlyer.</Anchor><ul><li>Primeira abertura do app</li><li>https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg</li><li>Sessions</li></ul>**<span id="h_01M349521V96NRS5CJKXZKMA6P"></span>Importante!**<ul><li>Reporte instalações antes de eventos in-app e sessões.</li><li>Envie eventos usando a API. Informe ao seu desenvolvedor quais eventos enviar e verifique se você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li></ul><br /><br />Para reportar engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engajamento por impressão</Anchor>.<br /><br />Para o método SDK, consulte o developer hub e acesse a documentação da Samsung. | Desenvolvedor de aplicativos |
| Integração de parceiros | Adicione a Samsung como uma ad network (parceiro integrado) na AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#a-activate-partner">Ativar parceiro</Anchor></li><li>[Opcional] Ative a <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#e-install-attribution">**atribuição de view-through**</Anchor>.</li></ol> | Marketer |
| Configuração do OneLink | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Técnico de marketing/engenheiro de dados |

## Características e Limitações

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente não compatível |
| Dados de custo | Importe dados de custo via <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Importação de custo</Anchor> usando o método de upload de arquivo **por e-mail** . Você também pode extrair dados **via API** para Google, Meta ou TikTok. |
| Regiões suportadas | A compatibilidade com campanhas de CTV e preload varia por região, como segue.<ul><li>A AppsFlyer oferece suporte a campanhas de Connected TV (CTV) apenas nos EUA, incluindo o compartilhamento de postbacks com a Samsung por meio da integração com a plataforma DSP (demand-side platform) da Samsung (`samsungdsp_int`).</li><li>Na região EMEA (Europa, Oriente Médio e África), a AppsFlyer oferece suporte a campanhas de CTV sem compartilhar postbacks com a Samsung por meio da integração Samsung EMEA DSP (`samsungemea_int`).</li><li>Outras regiões não oferecem suporte a campanhas de CTV.</li><li>A AppsFlyer oferece suporte a campanhas de preload globalmente.</li></ul> |

<div data-zendesk-anchors="about-samsung-ctv-attribution=sobre-a-atribui%C3%A7%C3%A3o-da-samsung-ctv 01H7Z17A1QPJQH9R5MRBVTMG37=sobre-a-atribui%C3%A7%C3%A3o-da-samsung-ctv samsung-attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o-da-samsung 01H7Z17A1Q03CEJT848FRFHDPQ=fluxo-de-atribui%C3%A7%C3%A3o-da-samsung integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o 01H7Z17A1QQN4FYJXZFS5FP2NY=procedimentos-de-integra%C3%A7%C3%A3o traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01H7Z17A1QVW58B2FZE7SDJHHJ=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
