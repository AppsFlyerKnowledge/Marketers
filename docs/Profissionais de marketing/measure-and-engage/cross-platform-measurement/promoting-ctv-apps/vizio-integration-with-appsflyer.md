---
title: Integração da Vizio com a AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2026-08-18T00:22:55Z'
  id: 5045234293777
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/5045234293777
---
> **Visão geral:** Integre seu aplicativo (canal) Vizio Connected TV (CTV) com a AppsFlyer para receber dados de atribuição e eventos para suas campanhas na Vizio.

<div id="about-vizio-ctv-attribution" />

## Sobre a atribuição da Vizio CTV

O SmartCast da Vizio para streaming funciona em todas as Vizio TVs.

Os aplicativos de streaming na Vizio podem se integrar com a AppsFlyer via API para receber dados de atribuição e mensuração da performance, indicando quais canais (orgânicos e não orgânicos) e campanhas impulsionam a abertura do app e eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da Vizio API é compatível com:

* Smart TVs da Vizio.
* Atribuição CTV-to-CTV e registro de eventos. Ou seja, atribuição e registo das primeiras aberturas de aplicativos da Vizio (o equivalente a instalações) e eventos que ocorrem no dispositivo Vizio de um usuário.

<div id="vizio-attribution-flow" />

### Fluxo de atribuição da Vizio

<Image align="center" alt="CTV_attribution_flow_-_Vizio__1_.png" src="https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png" />

<div id="integration-procedures" />

## Etapas de integração

A tabela abaixo lista as etapas necessárias para integrar um app da Vizio CTV na AppsFlyer.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários de conta com as permissões adequadas</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu app da Vizio na AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integre a API da AppsFlyer</Anchor> em seu aplicativo, adicionando comandos para relatar os seguintes eventos à AppsFlyer.<ul><li>Primeira abertura do app</li><li>Eventos in-app</li><li>Sessões</li></ul>**Observação**:<ul><li>As instalações devem ser relatadas antes de eventuais eventos in-app e sessões.</li><li>Envie eventos usando a API. Compartilhe com seu desenvolvedor quais eventos devem ser enviados. Verifique se, ao configurar a API, você configurou e mapeou os eventos a serem enviados para a AppsFlyer.</li></ul>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | Desenvolvedor de aplicativos |
| Integração de parceiros | Adicione a Vizio como uma ad network (parceiro integrado) na AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#a-activate-partner">Ativar parceiro</Anchor></li><li>[Opcional] Ativar a **<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#e-install-attribution">atribuição de view-through</Anchor>.**</li></ol> | Marketer |
| Configuração do link | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em dashboards e relatórios</Anchor> | Profissional de marketing/engenheiro de dados |

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | Atualmente sem suporte |
| Atribuição por visualização | O padrão é de 24 horas |
| Dados de custo | Os dados de custos devem ser enviados através de <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> utilizando o método de upload de arquivos por e-mail. |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=sobre-a-atribui%C3%A7%C3%A3o-da-vizio-ctv 01H7Z16QWWCPR309JDKV7H0469=sobre-a-atribui%C3%A7%C3%A3o-da-vizio-ctv vizio-attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o-da-vizio 01H7Z16QWW3GJEAGV0F3JHTKE1=fluxo-de-atribui%C3%A7%C3%A3o-da-vizio integration-procedures=etapas-de-integra%C3%A7%C3%A3o 01H7Z16QWW1WX5F947WPH9HBQX=etapas-de-integra%C3%A7%C3%A3o 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
