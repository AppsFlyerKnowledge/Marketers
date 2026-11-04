---
title: Configurações da conta
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2026-03-15T11:09:02Z'
  edited_at: '2026-08-19T00:15:49Z'
  id: 44784756352273
  locale: pt
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/pt/articles/44784756352273
---
> **Resumo:** Use a página de **configurações da conta** para gerenciar seu perfil pessoal, suas configurações no nível da conta e seus recursos de IA a partir de um único local.

<div id="about-account-settings" />

## **Sobre as configurações da conta**

A página de **configurações da conta** possui três abas:

* [**Perfil**](/docs/account-settings#perfil): contém as informações pessoais da sua conta
* [**Conta**](/docs/account-settings#conta): configurações da conta
* [**Recursos de IA**](/docs/account-settings#recursos-de-ia): controles para o acesso e uso de produtos impulsionados por IA

<div id="profile" />

## **Perfil**

No seu **perfil**, você encontra as informações pessoais da sua conta, como nome da conta, e-mail do proprietário, site e ID da conta.

Você pode revisar as informações da sua conta e atualizar os campos de perfil compatíveis.

<div id="account" />

## **Conta**

Em **conta**, você encontra suas configurações de segurança. Configurações adicionais podem ser adicionadas ao longo do tempo.

<div id="unique-dev-key" />

### <Anchor target="_blank" href="/marketers/pt/docs/dev-key-management">**Dev key exclusiva**</Anchor>

A configuração da **dev key exclusiva** define se a AppsFlyer cria uma dev key específica para cada novo aplicativo.

Quando a opção **criar uma dev key exclusiva por aplicativo para aplicativos futuros** estiver ativada, uma dev key exclusiva será criada automaticamente para cada aplicativo recém-adicionado.

Atenção: essa configuração se aplica apenas a apps criados depois que a configuração foi ativada. Ela não altera as dev keys dos aplicativos existentes.

<div id="ai-capabilities" />

## **Recursos de IA**

Em **recursos de IA**, os administradores podem gerenciar quais produtos impulsionados por IA estão disponíveis para a conta.

### <Anchor target="_blank" href="/marketers/pt/docs/ai-assistant">AI Assistant</Anchor>

O AI Assistant é um analista virtual, que também pode ser usado para acessar informações sobre a AppsFlyer. Use-o para descobrir insights, mensurar sua performance, identificar melhores e piores resultados, explorar tendências de campanha e acessar insights visuais em tabelas e gráficos, diretamente de qualquer página na plataforma.

<div id="appsflyer-mcp" />

### <Anchor target="_blank" href="/marketers/pt/docs/beta-appsflyer-mcp">MCP da AppsFlyer</Anchor>

O MCP conecta seus dados da AppsFlyer a qualquer modelo de linguagem de grande escala (LLM), como Claude ou VS Code. Faça perguntas, acesse insights de performance e escolha como agir diretamente em seu AI chat.

O MCP está ativado por padrão para todas as contas.

Para desativar o MCP, acesse **Conta & perfil > Capacidades de IA**.

Para desativar o MCP:

* Os usuários não podem mais acessar os dados da AppsFlyer por meio do MCP em ferramentas externas de IA.
* As conexões existentes podem continuar funcionando até que a sessão atual expire.
* Isso não afeta as conexões de API.
* Não afeta outros recursos de IA na AppsFlyer.

**Importante:** se um token do MCP estiver em uso, primeiro exclua-o em **Centro de segurança > Tokens da AppsFlyer**.

### <Anchor target="_blank" href="/marketers/pt/docs/beta-agent-hub-overview">Agent Hub</Anchor>

O Agent Hub é uma plataforma centralizada para a gestão de agentes de IA na AppsFlyer, que oferecem insights de marketing práticos diretamente no seu workflow. Esses agentes analisam constantemente seus dados para fornecer resultados valiosos e recomendar ações, tudo dentro do ambiente colaborativo da sua equipe.

Essa configuração está disponível apenas para administradores e é ativada por padrão.

Desativação do Agent Hub:

* Os usuários não podem mais ter acesso ao Agent Hub.
* Todos os agentes existentes são excluídos permanentemente e não podem ser restaurados.
* Qualquer agente ativo é interrompido.
* Se o Agent Hub for ativado novamente mais tarde, os usuários poderão ter acesso a ele novamente, mas terão que criar os agentes do zero.

<div id="permissions" />

## **Authorization: Bearer**

As permissões do usuário definem que pode ser visualizado ou editado na página de **configurações da conta**.

No geral:

* Nem todos os usuários veem as mesmas configurações
* Algumas configurações permitem apenas visualização
* Podem ser necessárias permissões de administrador para alterar os controles da conta ou recursos de IA

<div data-zendesk-anchors="about-account-settings=sobre-as-configura%C3%A7%C3%B5es-da-conta h_01KKRJZMP6CDDSJ6RK8QN4T30A=sobre-as-configura%C3%A7%C3%B5es-da-conta profile=perfil h_01KKRJZMP81BHTCA01W22CRQYG=perfil account=conta h_01KKRJZMP9PQB0BZQ0931D23AH=conta unique-dev-key=dev-key-exclusiva h_01KKRJZMPA9YTMGY0A3A883T0N=dev-key-exclusiva ai-capabilities=recursos-de-ia h_01KKRJZMPCAMQFZM3MKQBTYFVD=recursos-de-ia h_01KKRJZMPCQJBRRA0EM2EF4BYB=ai-assistant appsflyer-mcp=mcp-da-appsflyer h_01KKRJZMPDZQKY9VV25EKCP5YE=mcp-da-appsflyer h_01KKRJZMPEHQHPRJEH9PSDTT00=agent-hub permissions=authorization-bearer h_01KKRJZMPFQJK110AW1CDS23CW=authorization-bearer" />
