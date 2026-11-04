---
title: Log de auditoria
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
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2026-08-18T00:17:11Z'
  id: 360007971697
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/360007971697
---
> **Num relance:** Identifique e proteja-se contra acessos não autorizados à sua conta da AppsFlyer usando o log de auditoria. Visualize e baixe um resumo da atividade relacionada à segurança na sua conta.

<div id="overview" />

## Visão geral

O **log de auditoria** fornece uma localização central para rever várias atividades na sua conta, tais como inícios de sessão, acesso a dados, chamadas de API, modificações de configuração e permissão para parceiros integrados, regras de validação, audiências e outros eventos significativos. Isso desempenha um papel fundamental para garantir transparência, segurança e o cumprimento das normas de compliance. Para proteger a segurança da sua conta da AppsFlyer, é recomendável que você revise periodicamente **quem** está acessando sua conta e **como** ela está sendo acessada. Os dados do log de auditoria estão disponíveis para os últimos 90 dias.

**Para acessar o log de auditoria:**

1. Na barra superior, abra o menu da conta (menu suspenso do endereço de e-mail): **Central de segurança.**
2. Na seção **Log de auditoria**, clique em Ver log de auditoria.

<div id="using-the-audit-log" />

## Como usar o log de auditoria

O quadro seguinte apresenta uma descrição dos dados fornecidos pelo log de auditoria e um resumo das suas capacidades.

[![audit_log.png](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)

|  | Item | Descrição |
| --- | --- | --- |
| ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png) | Caixa de pesquisa e filtros | Filtre os dados apresentados para se concentrar apenas no que deseja ver:<ul><li>Utilize a caixa de pesquisa para filtrar os dados por um termo específico (como uma ID de aplicação relevante, endereço de e-mail, etc.)</li><li>Utilize o seletor de datas para selecionar em relação a qual período de tempo os dados são exibidos</li><li>Utilize o filtro de serviços para filtrar os dados com base nos serviços específicos acessados:<ul><li>Acesso ao sistema</li><li>Permissões integradas de parceiros</li><li>Gestão de usuários</li><li>Regras de validação</li><li>Chamadas API</li></ul></li></ul>Note que o serviço de **chamadas de API** é desmarcado por padrão para otimizar a legibilidade do relatório. Certifique-se de selecionar esse serviço se quiser incluí-lo no relatório. |
| ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png) | Dados do log de auditoria | Cada entrada no log de auditoria inclui os seguintes dados:<ul><li>**Data e hora:** a data e a hora em que o serviço foi acessado (em UTC)</li><li>**Aplicação/conta acessada:**<ul><li>Para os logins de usuário (acesso ao sistema) e gestão de usuários, essa coluna mostra **Conta** (indicando o acesso ao nível da conta).</li><li>Para chamadas de API, essa coluna mostra o Acesso **à conta** ou o **ID** da aplicação para a qual os dados foram acessados.</li></ul></li><li>**Credenciais**<ul><li>Para acesso ao sistema ou gestão de usuários, essa coluna mostra o endereço de e-mail do usuário que acessa o serviço.</li><li>Para chamadas de API, essa coluna mostra o token de API da AppsFlyer usado (V2)</li></ul></li><li>**Serviço:** o serviço acessado (acesso ao sistema, gestão de usuários ou chamadas de API)</li><li>**Ação:** a ação registada (exemplos: início de sessão, fim de sessão, dados acessados por uma API)</li><li>**Detalhes:** Detalhes adicionais sobre a ação registada</li></ul> |
| ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png) | ![audit_log_download_button.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | Clique no botão de transferência para transferir o log de auditoria como um arquivo CSV.<ul><li>Todas as seleções aplicadas ao relatório, tal como apresentadas na tela (utilizando a caixa de pesquisa e os filtros), são também aplicadas ao arquivo baixado.</li></ul> |

<div id="troubleshooting" />

## Solução de problemas

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="Por que o log de auditoria de um anunciante mostra solicitações de chamadas de API do parceiro?">

Quando um parceiro faz uma solicitação de API numa aplicação pertencente a um anunciante, tanto o parceiro quanto o anunciante veem a solicitação no seu log de auditoria.

Quando um anunciante faz uma solicitação de API utilizando o seu próprio token, este só será apresentado no log de auditoria do anunciante.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01H9Q3XYYBKYSRP3T0R2MP712C=vis%C3%A3o-geral using-the-audit-log=como-usar-o-log-de-auditoria h_01H9Q3XYYBBCB6PXBZBF97QE11=como-usar-o-log-de-auditoria troubleshooting=solu%C3%A7%C3%A3o-de-problemas h_01H9Q3XYYB24R3EATM7R32V0G7=solu%C3%A7%C3%A3o-de-problemas h_01H9Q3XYYCHWJ1NQS389MR311X=why-does-an-advertiser-audit-log-show-partner-api-call-requests" />
