---
title: Gerenciando tokens da AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-09-24T00:07:47Z'
  id: 360004562377
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/360004562377
---
> **Visão geral:** Os tokens aumentam a segurança dos dados. Eles permitem que os usuários acessem dados por meio das APIs da AppsFlyer ou recebam dados de eventos usando chamadas de servidor para servidor. Os administradores podem gerenciar vários tokens enquanto mantêm a continuidade dos dados. Ou seja, eles podem criar, renomear e remover tokens de API e de servidor para servidor, conforme necessário.

<div id="important" />

> 🚧 **Importante!**
>
> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)
>
> * Somente administradores podem visualizar e gerenciar tokens. Os usuários da conta não têm acesso à página Tokens.
> * Mantenha seus tokens seguros, pois eles permitem o acesso aos seus dados. Não publique tokens em repositórios de código públicos.
> * É recomendável substituir os tokens a cada 180 dias.

<div id="about-appsflyer-tokens" />

## Sobre os tokens da AppsFlyer

Os tokens são usados para permitir que os usuários acessem dados por meio da API da AppsFlyer e chamadas S2S (servidor para servidor). Os administradores usam os tokens para diversos propósitos:

* Medidas de segurança:
  * Substituir os tokens para resolver problemas específicos de segurança, como comprometimento do token ou suspeita de acesso não autorizado
  * Substituir periodicamente os tokens como parte das atualizações de rotina da política de segurança
* Gestão de diferentes chamadas de API
* Finalidades de teste
* Uso com recursos específicos, como a OneLink API

<div id="reaching-the-tokens-page" />

## Acessando a página de Tokens

1. No topo, abra o menu da conta (menu suspenso do endereço de email) > **Centro de Segurança**.
2. Na seção **Tokens de API da AppsFlyer**, clique em **Gerenciar seus tokens de API da AppsFlyer.** Os tokens atuais são exibidos.

<div id="token-types" />

## Tipos de token

Existem vários tipos de tokens para diferentes propósitos. Por padrão, um token de API é gerado para cada nova conta (token de API V2). Os administradores podem criar no máximo dois tokens para cada tipo, conforme detalhado na tabela abaixo.

| Tipo de token | Uso pretendido |
| --- | --- |
| <span id="api-token"></span>Token da API | Um token JWT (JSON Web Token) usado para autorizar chamadas de API, como Pull API, Cohort API, ROI API e outras. |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> (premium) | Um token exclusivo usado para a OneLink API, que gera links personalizados para o engajamento do usuário em campanhas de grande escala. |
| <span id="s2s-token"></span>Token S2S | Usado para enviar dados usando chamadas de servidor para servidor (S2S). |
| <span id="mcp-token"></span>Token do MCP | Usado para autenticar sistemas de terceiros ou self-hosted com o MCP da AppsFlyer. |

<div id="note" />

> 📘 **Atenção**
>
> Se você estiver integrando um recurso que exige um token dedicado de API V2 (por exemplo, o <Anchor target="_blank" href="/marketers/pt/docs/beta-advanced-security-protect360-module">Módulo de Segurança Avançada</Anchor>) e já tiver atingido o limite de dois tokens, poderá reaproveitar um token de API V2 existente em vez de solicitar um novo — o mesmo token pode servir para vários casos de uso.

<div id="manage-your-tokens" />

## Gerencie seus tokens

Como administrador, você pode gerenciar vários tokens: ou seja, criar, renomear e remover tokens. O uso principal desse recurso seria substituir tokens atuais por novos. Isso é feito primeiro [criando](#criar-um-token) um novo token, implementando-o em seus sistemas e, depois que ele estiver disponível, [excluindo](#excluir-um-token) o token antigo.

<div id="retrieve-tokens" />

### Recuperar tokens

1. Na barra superior, abra o menu da conta (menu suspenso do endereço de e-mail) > **Central de segurança.**
2. Na seção **Tokens de API da AppsFlyer**, clique em **Gerenciar seus tokens de API da AppsFlyer.**
3. Os tokens disponíveis são exibidos.
4. Copie o token necessário.

<div id="create-a-token" />

### Criar um token

1. Na página [**Tokens**](#acessando-a-página-de-tokens), clique em **+ Novo token**.
2. Digite o nome do token.
3. Selecione o tipo de token.
4. Clique em **Criar token**.

<div id="note-1" />

> 📘 **Importante!**
>
> * Os tokens da API V2 ficam ativos imediatamente após serem criados.
> * Os tokens S2S, OneLink e de outros tipos podem levar até 30 minutos para ficar ativos.
>   * Até que a ativação seja concluída, o status do token é **Pendente**.
>   * Use o token somente depois que o status mudar para **Ativo**.
> * Certifique-se de implementar o novo token em seus sistemas

<div id="delete-a-token" />

### Excluir um token

<div id="warning" />

> ❗️ **Atenção**
>
> * Excluir um token pode causar falhas em sistemas que dependem dele.
> * Ao excluir um token, ele é removido da página Tokens, e todas as chamadas do token anterior são rejeitadas.
> * Se você deseja substituir um token, certifique-se de primeiro criar um novo token, implementá-lo e somente depois que ele estiver disponível, ou seja, não estiver no status "Pendente", você poderá excluir o token antigo.

1. Na página [**Tokens**](#acessando-a-página-de-tokens), clique no ícone de edição do token que você deseja renomear.
2. Você deve confirmar a exclusão do token digitando "Deletar token".
3. Clique em **Salvar**.

<div id="applications-of-the-api-v2-token" />

## Aplicações o token API V2

Casos de uso para anunciantes e ad networks que usam o token API V2:

<div id="advertiser" />

### AppsFlyer

| Token API V2 |
| --- |
| <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">Dados brutos da Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Dados agregados da Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/app-list-api-for-app-owners">Obter lista de aplicativos</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/cohort-api">Coorte</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">Relatórios agregados da SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Copiar configurações de integração do parceiro</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Definir chave de descriptografia do install referrer</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">Net Revenue API</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">API OpenDSR</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-management-api">API de importação de audiência</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/beta-advanced-security-protect360-module">Integração do módulo de segurança avançada (Android)</Anchor> |

<div id="ad-network" />

### Rede de anúncios

| Token API V2 |
| --- |
| <Anchor target="_blank" href="/partners/pt/docs/app-list-api-for-ad-networks">Lista de aplicativos para ad networks</Anchor> |
| <Anchor target="_blank" href="/partners/pt/docs/access-to-aggregated-analytics-tools-for-api-partners">Integração com plataformas de gestão de campanhas</Anchor> |
| <Anchor target="_blank" href="/partners/pt/docs/protect360-for-integrated-partners#api-de-relatórios-da-rede-de-anúncios-protect360">Relatórios do Protect360 para parceiros integrados.</Anchor> |
| <Anchor target="_blank" href="/partners/pt/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div id="applications-of-the-s2s-token" />

## Aplicações do token S2S

Casos de uso para anunciantes que usam o token S2S:

<div id="advertiser-1" />

### AppsFlyer

| Token S2S |
| --- |
| <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API de eventos de servidor para servidor (S2S mobile) para mobile</Anchor> |
| <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement">API de eventos de servidor para servidor (S2S mobile) para web</Anchor> |

<div id="ad-network-1" />

### Rede de anúncios

| Token S2S |
| --- |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-appsflyer-preload-referrer-attribution">Atribuição de preload referrer da AppsFlyer</Anchor> |

<div id="note-2" />

> 📘 **Atenção**
>
> Para a maioria das ad networks, a geração de tokens S2S não está mais disponível em autoatendimento. Portanto, os administradores não verão a opção de gerar um token S2S na interface do usuário. A geração de token está disponível em autoatendimento apenas para parceiros específicos.

<div id="applications-for-the-onelink-token" />

## Aplicações para o token OneLink

Casos de uso para anunciantes que usam o token da OneLink API:

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Crie</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">acesse</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">atualize</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">exclua</Anchor> URLs curtas do OneLink com parâmetros personalizados.

<div id="applications-for-the-mcp-token" />

## Aplicativos para o token do MCP

Confira o <Anchor target="_blank" href="/marketers/pt/docs/beta-appsflyer-mcp">artigo do MCP da AppsFlyer</Anchor> para ver os casos de uso disponíveis para tokens do MCP.

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=importante overview=sobre-os-tokens-da-appsflyer h_01HFY5D0E1H66CEB3KMJQEXV4K=sobre-os-tokens-da-appsflyer reaching-the-tokens-page=acessando-a-p%C3%A1gina-de-tokens h_01HFTT570KF3XM9MBSFYRDYN9S=acessando-a-p%C3%A1gina-de-tokens token-types=tipos-de-token h_01HFBR7KP8BZN7KH0BNJ982WK8=tipos-de-token h_01M36NWJZ03NKZVAC2SCTAWBFX=aten%C3%A7%C3%A3o manage-your-tokens=gerencie-seus-tokens h_01HFY5D0E1AF4NYPX31W3VJYQC=gerencie-seus-tokens retrieving-api-tokens=recuperar-tokens h_01HBQN3T2HKEMNC8MSR0THYW2S=recuperar-tokens create-a-token=criar-um-token h_01HFY5D0E1FECQC1HN0EXWMXAV=criar-um-token h_01HFY5D0E1HJFKFPRT8WVNPHDG=importante-1 delete-a-token=excluir-um-token h_01HFY5D0E2B1KXGSFZR0AYAER5=excluir-um-token h_01HFY5D0E2KZYG0J2R7GR1R7W5=aten%C3%A7%C3%A3o-1 applications-of-the-api-v2-token=aplica%C3%A7%C3%B5es-o-token-api-v2 h_01HG64DMW7PYRXBMZN00EQN991=aplica%C3%A7%C3%B5es-o-token-api-v2 v20-token%E2%80%94advertiser-apis=appsflyer h_01HBQN7TBASK192P8D7AEWM9P6=appsflyer v20-token%E2%80%94ad-network-apis=rede-de-an%C3%BAncios h_01HBQN7TBAWAHEQXMYK9V14G0M=rede-de-an%C3%BAncios applications-of-the-s2s-token=aplica%C3%A7%C3%B5es-do-token-s2s h_01HG64M8K1PPY2Z2406MC78EEN=aplica%C3%A7%C3%B5es-do-token-s2s advertiser=appsflyer-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=appsflyer-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=rede-de-an%C3%BAncios-1 ad-network=rede-de-an%C3%BAncios-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=aten%C3%A7%C3%A3o-2 applications-for-the-onelink-token=aplica%C3%A7%C3%B5es-para-o-token-onelink h_01JSKCWS5406YQJP3RR9KAXJC9=aplica%C3%A7%C3%B5es-para-o-token-onelink applications-for-the-mcp-token=aplicativos-para-o-token-do-mcp h_01K9YD2Y9M1C8QDBS5H048XYYD=aplicativos-para-o-token-do-mcp" />
