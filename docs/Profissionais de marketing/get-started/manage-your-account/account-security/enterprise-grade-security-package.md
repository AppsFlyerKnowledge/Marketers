---
title: Pacote de segurança nível enterprise
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
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-10-20T03:41:52Z'
  id: 34053592094737
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/34053592094737
---
> **Resumo:** Aprimore a proteção da sua conta com nosso **pacote de segurança enterprise,** uma oferta premium projetada para o gerenciamento de identidades em nível enterprise, controle de acessos por tokens e visibilidade de auditoria ampliada.

## Introdução

Nossa segurança enterprise reúne três recursos principais, que ajudam a elevar a segurança da sua empresa:

* **Gerenciamento de múltiplos tokens com restrições de serviço**: ampla criação de tokens e controles de acesso granulares em APIs, S2S e OneLink.
* **Audit log API com retenção estendida**: Tenha visibilidade de longo prazo sobre as atividades que ocorrem dentro da plataforma e integre eventos de auditoria à sua estrutura de monitoramento,
* **Provisionamento de SCIM:** automatize e centralize o controle de acesso através do seu provedor de identidade.
* **Lista de IPs permitidos para login:** evite acessos não autorizados, garantindo que o login no dashboard da AppsFlyer seja afeito apenas em redes e IPs da sua confiança.

### Compare os pacotes padrão e enterprise:

| Funcionalidade | Pacote padrão | Pacote de segurança nível enterprise |
| --- | --- | --- |
| [Login único (SSO)](/docs/enterprise-grade-security-package#accordion-item) | Login SSO (apenas para clientes existentes) | SSO SAML 2.0 com provisionamento SCIM para gestão automatizada de usuários e funções |
| [Gestão de tokens](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Gerencie até 2 tokens por tipo (API, S2S ou OneLink) | Gerencie vários tokens por tipo (até 30) com permissões granulares |
| [Acesso a logs de auditoria](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | Acesso apenas à interface do usuário, dados com retenção de 90 dias | Acesso via interface e API, retenção de dados de 180 dias |
| [Gestão de usuários com base em funções (RBAC)](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | Até 10 funções personalizadas | Até 50 funções personalizadas |
| [IP allowlist](/docs/enterprise-grade-security-package#ip-allowlist) | Lista de IPs permitidos para APIs | Lista de IPs permitidos para login e APIs, garantindo uma segurança aprimorada |
| Monitoramento ativo 24h por dia | Incluso | Incluso |
| Autenticação de múltiplos fatores | Incluso | Incluso |

<div id="multitoken-management-with-restrictions" />

<Accordion title="Gerenciamento de múltiplos tokens, com restrições">

Crie e gerencie até **30 tokens** por tipo (API, S2S, OneLink), com **restrições de nível de serviço** que garantem um aumento na eficiência, segurança e controle de tokens.

#### Principais características

* Administradores podem criar até **30 tokens por tipo**, indo além dos 2 tokens disponíveis nos tokens padrão, oferecendo suporte a equipes maiores e fluxos de trabalho mais complexos.​
* Atribua permissões de acesso a serviços específicos a tokens de API, restringindo o acesso a operações mais sensíveis.​
* Tokens podem ser revogados ou redirecionados sem quebrar integrações ou automações.
* Restrinja um token a um aplicativo específico para que ele só possa dar acesso a dados ou executar ações para esse aplicativo.
* Simplifique a colaboração com equipes internas e parceiros externos por meio de permissões específicas de token.

> 📄 **Exemplo**
>
> Crie dois tokens para ajudar manter o acesso de privilégios mínimos e evitar a exposição acidental de dados.
>
> **Token de acesso apenas a dados:** crie um token que possui acesso apenas a dados agregados. Esse token não poderá acessar dados brutos ou realizar ações como alterações na configuração. Use isso para equipes de analytics ou usuários de agência cuja permissão é de somente leitura.
>
> **Token de acesso apenas a configurações:** emita um token que permite que equipes internas gerenciem configurações, sem permitir que elas acessem dados. Isso isola as capacidades administrativas do acesso a dados.
>
> **Token de acesso específico do aplicativo:** crie um token que funcione apenas para um aplicativo. Use este token quando uma equipe interna, um parceiro externo ou uma automação precisar de acesso apenas a um aplicativo específico.

> 📘 **Atenção**
>
> Para informações gerais sobre tokens padrão, veja <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">gerenciando tokens da AppsFlyer</Anchor>.

#### Como acessar e controlar tokens

**Para criar um token restrito**

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) > **Centro de segurança.**
2. Vá para a página **gerenciamento de tokens**.
3. Clique em **criar token**.
4. Selecione o tipo de token:
   * API
   * S2S
   * Os links diretos universais do OneLink
5. Para **tokens de API**, selecione um ou mais serviços no menu **restrição de acesso**.  
   O acesso é binário: acesso total ou nenhum.
6. Selecione o tipo de restrição:
   1. Restrição de serviço: selecione um ou mais serviços na lista suspensa **Restrição de acesso**.
   2. Restrição de aplicativo: selecione o aplicativo ao qual o token pode dar acesso.
7. Clique em **salvar**

**Gerenciar tokens**

Para gerenciar seus tokens, na barra superior, abra o menu da conta (menu suspenso do endereço de e-mail) -> página **Centro de segurança -> gerenciamento de tokens**.

Aqui você pode:

* Visualizar metadados do token: nome, tipo, restrições, criação/expiração
* Excluir tokens individualmente
* Monitorar a atividade do token nos logs de auditoria

> 📘 **Atenção**
>
> Tokens não podem ser editados. Para alterar o acesso, exclua e crie o token novamente.

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="Audit log API e retenção estendida">

Para melhorar as capacidades existentes do log de auditoria, esse recurso introduz uma API para consumo de logs de auditoria e amplia o período de retenção de dados de 90 para 180 dias. Ideal para equipes que precisam de acesso de longo prazo ao logs de ações do usuário ou integrando eventos de auditoria em ferramentas de monitoramento externas como SOC e SEIM.

#### Principais características

* Acesse logs de auditoria programaticamente usando uma API dedicada
* Mantenha logs por até **180 dias**, em comparação com a retenção de 90 dias para logs de auditoria padrão
* Filtre e exporte dados para garantir a compliance, segurança ou uso operacional
* Use tokens para serviços específicos e isolar o acesso ao log
* Exporte dados para ferramentas SIEM, dashboards ou armazenamento em nuvem

> 📘 **Atenção**
>
> Para informações gerais sobre o log de auditoria padrão, consulte <Anchor target="_blank" href="/marketers/pt/docs/audit-log">log de auditoria padrão</Anchor>.

### **Como acessar o log de auditoria via API**

Para usar a Audit Log API:

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail): **centro de segurança.**
2. Em **log de auditoria**, clique em **ver log de auditoria.**
3. Vá para a página **gerenciamento de tokens**.
4. Use um **token de API** existente ou crie um novo.
5. Em **restrição de acesso**, selecione o serviço **Log de auditoria**.
6. Use o token para autenticar solicitações ao endpoint da audit log API.

> 📘 **Atenção**
>
> Certifique-se de salvar seu token de API com segurança. Ele não pode ser recuperado após a criação.

</Accordion>

<div id="accordion-item" />

<Accordion title="Provisionamento SSO e SCIM">

O provisionamento SCIM aprimora as capacidades de SSO da AppsFlyer, automatizando o gerenciamento do ciclo de vida dos usuários diretamente a partir do seu provedor de identidade (IdP), como Okta, Entra ID (Azure), OneLogin, JumpCloud ou IdPs gerenciados que permitem o acesso baseado em atributos. Isso permite que as empresas integrem, atualizem e desativem usuários sem nenhuma intervenção manual.

Ao sincronizar usuários via SCIM, você mantém total controle sobre as permissões de acesso em tempo real. Combinado com o SSO SAML 2.0, isso resulta em uma solução completa de gerenciamento de identidade e acesso para clientes enterprise.

#### **Principais características**

* Crie automaticamente usuários na AppsFlyer com base nos registros do provedor de identidade (IdP).
* Mudanças nas funções ou status dos usuários no IdP são refletidas instantaneamente na AppsFlyer.
* O **SAML 2.0** é usado para garantir um SSO seguro, com o **SCIM** para provisionamento —compatível com os principais IdPs como Okta e Azure AD.

#### **Como configurar o provisionamento SCIM**

Para começar a usar o provisionamento SCIM na AppsFlyer, você precisa:

1. [Configurar SSO](/docs/enterprise-grade-security-package#configuração-de-sso)
2. [Ativar SCIM](/docs/enterprise-grade-security-package#ativar-scim)

#### Configuração de SSO

Para configurar o SSO, você precisa:

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">Configurar a plataforma IdP</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">Configurar SSO na AppsFlyer</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">Testar a configuração do SSO</Anchor>

#### Ativar SCIM

> 📘 **Atenção**
>
> Para ativar o SCIM, o SSO deve ser configurado primeiro.

Para ativar o SCIM, há algumas etapas que devem ser seguidas:

* Siga as [instruções de configuração do IdP](/docs/enterprise-grade-security-package#links-de-instrução-do-idp)
* Configure as [conexões SCIM](/docs/enterprise-grade-security-package#conexões-scim)
* Adicione os [Atributos SCIM](/docs/enterprise-grade-security-package#atributos-scim)
* Adicione [funções](/docs/enterprise-grade-security-package#funções)
* Adicione um [namespace externo](/docs/enterprise-grade-security-package#external-namespace)

#### Links de instrução do IdP

##### As instruções para os IdPs podem ser encontradas abaixo. <Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">Okta</Anchor>, <Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>, <Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">OneLogin</Anchor>, <Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">JumpCloud</Anchor>

#### Conexões SCIM

Nas conexões SCIM, os seguintes campos devem ser preenchidos:

| **String vazia** | **Valor** |
| --- | --- |
| URL base do conector SCIM (endpoint SCIM) | https://hq1.appsflyer.com/api/scim/v2 |
| Campo de identificador único para usuários | userName |
| Método de autenticação: HTTP header "Authorization" | Bearer &lt;<Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Seu token da API da AppsFlyer</Anchor>> |

#### Atributos SCIM

| **Atributo** | **Tipo de valor esperado** | **Obrigatório** | **String vazia** | **Namespace externo** | **A descrição** |
| --- | --- | --- | --- | --- | --- |
| Cargo | ID da campanha reportado pela rede de anúncios à AppsFlyer | ✅ | role | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>Atribua uma função predefinida ou personalizada ao usuário.</li><li>Veja abaixo a lista de funções que devem ser inseridas</li></ul> |
| Permitir acesso a todos os aplicativos futuros | Boolean | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Se habilitado, o usuário terá acesso a novos aplicativos automaticamente. |
| App IDs permitidos | ID da campanha reportado pela rede de anúncios à AppsFlyer | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | Lista de app IDs separados por vírgula. Se quiser permitir todos os aplicativos, deixe esse campo vazio. Caso contrário, selecione "nenhum". |

#### Funções

As funções devem corresponder àquelas <Anchor target="_blank" href="/marketers/pt/docs/user-management#roles-tab">disponíveis na AppsFlyer</Anchor>. A tabela abaixo mostra as funções atuais disponíveis na AppsFlyer e seus valores. Funções personalizadas podem ser adicionadas. Para JumpCloud, veja as [limitações](/docs/enterprise-grade-security-package#limitações) abaixo.

| **Nome exibido** | **Valor** |
| --- | --- |
| Adminitração | admin |
| Gerente de equipe | team\_manager |
| Líder de marketing | marketing\_lead |
| marketing | marketing |
| Marketing-limitado | marketing\_limited |
| Contribuinte | developer |
| Contabilidade | accounting |
| Segurança | security |
| Controle de qualidade | quality\_assurance |
| Função personalizada | [insira o valor da função personalizada] |

#### Limitações

| **Limitação** | **A descrição** |
| --- | --- |
| **JumpCloud - atributos personalizados** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">Atributos personalizados não estão disponíveis</Anchor>. Como solução alternativa, mapeie o campo Função para o campo Endereço de Trabalho. Veja <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">suporte SCIM do JumpCloud</Anchor>. |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="Lista de IPs permitidos para login">

A lista de IPs permitidos aprimorada garante uma melhora na sua segurança, impedindo acessos não autorizados e garantindo que apenas redes confiáveis possam interagir com a plataforma. Esse recurso é especialmente útil para empresas que aplicam políticas de segurança rigorosas ou gerenciam acessos remotos.

#### Principais características

* Reduz ataques bloqueando tentativas de login de IPs desconhecidos.
* Permite especificar endereços IP ou intervalos para garantir que apenas usuários e redes autorizados possam acessar a plataforma.
* Ideal para empresas que usam VPNs ou que exigem controles de acesso mais rigorosos.

#### Adicionando IPs à lista

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) **> Centro de segurança.**
2. Em **Lista de IPs permitidos para login**, clique em **gerenciar lista de IPs permitidos**.
3. Adicione IPs manualmente ou faça o upload de um CSV.
   1. Se adicionar manualmente, insira o endereço IP ou intervalo CIDR e clique em **adicionar IP à lista**.
      1. Exemplos: `192.168.1.1`, `185.114.120.140`
      2. Para introduzir um intervalo de endereços IP, use o seguinte formato: `185.114.120.1/32`  
         (onde `185.114.120.1` é o primeiro endereço do intervalo e `185.114.120.32` é o último endereço do intervalo).
4. IPs adicionados serão mostrados no lado direito na seção: **veja seus IPs na lista de IPs permitidos**.
5. Clique em **salvar lista**.

> 🚧 **Importante!**
>
> * Certifique-se de que os endereços IP ou intervalos que você adicionou estão corretos. Entradas incorretas podem impedir que você acesse sua conta.
> * A lista de permissões deve conter pelo menos um endereço IP ou intervalo antes que você possa salvá-la e ativá-la, e você pode adicionar até 100 endereços IP ou intervalos à lista de permissões.
> * Depois de clicar em salvar lista, as restrições de IP serão aplicadas a partir do seu próximo login.

#### Removendo IPs da lista

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) **> Centro de segurança.**
2. Em **Lista de IPs permitidos para login**, clique em **gerenciar lista de IPs permitidos**.
3. IPs adicionados serão mostrados no lado direito na seção: **veja seus IPs na lista de IPs permitidos**.
4. Clique no ícone de lixo ao lado do endereço IP que deseja excluir.
5. Certifique-se de salvar as suas alterações clicando no botão **salvar lista**.

</Accordion>

<div id="frequently-asked-questions-about-our-security-package" />

<Accordion title="Perguntas frequentes sobre nossa segurança">

#### O que é a segurança nível enterprise da AppsFlyer?

Aumente sua segurança com recursos avançados que vão além das proteções padrão. Obtenha SSO com provisionamento SCIM, controles de acesso granulares, logs de auditoria estendidos e ferramentas de compliance desenvolvidas para a segurança das empresas.

#### Para quem foi desenvolvida a segurança nível enterprise?

Líderes de segurança e TI de empresas que se preparam para auditorias; equipes de compras e jurídico em indústrias regulamentadas que avaliam fornecedores de SaaS; administradores de plataforma que gerenciam requisitos de acesso complexos entre várias equipes e integrações.

#### Como funciona o provisionamento SCIM?

Automatize o gerenciamento do ciclo de vida do usuário conectando-se diretamente ao seu provedor de identidade. O SCIM sincroniza automaticamente o acesso e as funções dos usuários, gerencia onboarding e offboarding instantâneos, bem como elimina o gerenciamento manual de contas e os riscos de acesso órfão.

#### É compatível com quais padrões de compliance?

Prontidão para auditoria dos requisitos de SOC2, ISO 27001 e GDPR com retenção de logs de 180 dias, documentação de acesso abrangente e integração em tempo real com SIEM para monitoramento contínuo e verificação de compliance.

#### Quantas funções e quantos tokens de API posso criar?

Crie até 50 funções personalizadas adaptadas à estrutura da sua empresa e até 30 tokens de API específicos para serviços com permissões granulares. Isole o acesso para diferentes integrações e funções de trabalho enquanto mantém os princípios de menor privilégio.

#### Posso fazer a integração com as minhas ferramentas de segurança existentes?

Sim. Transmita dados de auditoria diretamente para o seu SIEM e ferramentas de segurança através do streaming de logs baseado em API. Habilite o monitoramento em tempo real, a detecção de anomalias e respostas automatizadas de segurança dentro da sua infraestrutura SOC.

#### Quais restrições de rede posso aplicar?

Controle o acesso à plataforma com listas de permissão de IP e restrições geográficas. Defina redes e locais confiáveis para prevenir acesso não autorizado enquanto oferece suporte a equipes remotas e uma colaboração segura com parceiros.

#### Por quanto tempo os logs de auditoria são retidos?

Acesse trilhas de auditoria abrangentes com retenção de logs de 180 dias que captura todas as interações na plataforma. Obtenha visibilidade completa sobre ações de usuários, chamadas de API e padrões de acesso para a documentação de compliance e investigações de segurança.

#### Esse tipo de segurança substitui os recursos padrão?

Não. A segurança nível enterprise adiciona funções avançadas além dos recursos padrão. Você obtém controles aprimorados, automação e visibilidade, mantendo todas as proteções de segurança existentes.

#### Quando posso implementar esses controles de segurança?

Implemente os controles de segurança nivel enterprise rapidamente através da fácil integração de SSO e do provisionamento SCIM automatizado. A maioria das empresas consegue implementar recursos principais em poucos dias, mantendo a continuidade operacional e a produtividade do usuário.

</Accordion>

<div data-zendesk-anchors="intro=introdu%C3%A7%C3%A3o h_01JRA2GVNZCDW8C9VW6GH3G4KE=introdu%C3%A7%C3%A3o compare-the-standard-and-advanced-packages=compare-os-pacotes-padr%C3%A3o-e-enterprise h_01JVS101KETCVDMT1B2WZM89NF=compare-os-pacotes-padr%C3%A3o-e-enterprise h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions key-features=principais-caracter%C3%ADsticas h_01JQXRDEMJF2NT73FP1TFJG63Z=principais-caracter%C3%ADsticas h_01JVRZRXPD4AC1GAMJ2HKC1R9E=exemplo h_01JVRZ0ACA19TGC9WJCZ562B70=aten%C3%A7%C3%A3o how-to-access-and-control-tokens=como-acessar-e-controlar-tokens h_01JQXSE4TTYXTWCKXDHB20KJ1Z=como-acessar-e-controlar-tokens h_01JVRZ9X0D5V765FTXHVHMR807=aten%C3%A7%C3%A3o-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=principais-caracter%C3%ADsticas-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=principais-caracter%C3%ADsticas-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=aten%C3%A7%C3%A3o-2 how-to-access-the-audit-log-via-api=como-acessar-o-log-de-auditoria-via-api h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=como-acessar-o-log-de-auditoria-via-api h_01JVRZ69C2JYY9SK12SEVG3KXF=aten%C3%A7%C3%A3o-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=principais-caracter%C3%ADsticas-2 h_01JV9W8DTENC21GS0380Q9DP8T=principais-caracter%C3%ADsticas-2 how-to-set-up-scim-provisioning=como-configurar-o-provisionamento-scim h_01JV9W8DTFCE7Z0MQP96MK7BQC=como-configurar-o-provisionamento-scim sso-set-up=configura%C3%A7%C3%A3o-de-sso h_01JV9W8DTFHJME1J1JKKJ3NA6C=configura%C3%A7%C3%A3o-de-sso enable-scim=ativar-scim h_01JV9W8DTG50YYPQ9RS91K2CJ4=ativar-scim h_01JVRZ3MC8J0B1E66A47GM5WYZ=aten%C3%A7%C3%A3o-4 idp-instruction-links=links-de-instru%C3%A7%C3%A3o-do-idp h_01JV9WBJCPQ0X5SKVVNK4TBYRR=links-de-instru%C3%A7%C3%A3o-do-idp h_01JV9WTJ33KMJGZGM9P5PRK917=as-instru%C3%A7%C3%B5es-para-os-idps-podem-ser-encontradas-abaixo-okta-entra-id-azure-onelogin-jumpcloud scim-connections=conex%C3%B5es-scim h_01JV9WBNC51WYW03RKWHBTP0AG=conex%C3%B5es-scim scim-attributes=atributos-scim h_01JV9WBS928Z7WKJ2A2CFSWNT4=atributos-scim roles=fun%C3%A7%C3%B5es h_01JV9WBX3JHEMAG62JCASYXB59=fun%C3%A7%C3%B5es limitations=limita%C3%A7%C3%B5es h_01JV9DMY0Y3795TAT3Q1E3PZRM=limita%C3%A7%C3%B5es h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=principais-caracter%C3%ADsticas-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=principais-caracter%C3%ADsticas-3 adding-ips-to-the-list=adicionando-ips-%C3%A0-lista h_01K35NHF44511J17KCXTE073QB=adicionando-ips-%C3%A0-lista h_01K3DGBBVYY08KVYS60F2MYDCW=importante removing-ips-from-the-list=removendo-ips-da-lista h_01K35PGV6Y84JR4CZJ0KGQNWZS=removendo-ips-da-lista h_01K85MXJJ7A9ZTS3PSY2Q0ZDGZ=frequently-asked-questions-about-our-security-package what-is-appsflyers-enterprisegrade-security-package=o-que-%C3%A9-a-seguran%C3%A7a-n%C3%ADvel-enterprise-da-appsflyer h_01K85MZT9TDAV684V6PBBFGPTX=o-que-%C3%A9-a-seguran%C3%A7a-n%C3%ADvel-enterprise-da-appsflyer who-is-the-enterprisegrade-security-package-designed-for=para-quem-foi-desenvolvida-a-seguran%C3%A7a-n%C3%ADvel-enterprise h_01K85N0D7WVGH94HT1B7NY4KTZ=para-quem-foi-desenvolvida-a-seguran%C3%A7a-n%C3%ADvel-enterprise how-does-scim-provisioning-work=como-funciona-o-provisionamento-scim h_01K85N0ZV1CMH5VANHQCEGENAW=como-funciona-o-provisionamento-scim what-compliance-standards-does-this-support=%C3%A9-compat%C3%ADvel-com-quais-padr%C3%B5es-de-compliance h_01K85N1KB8VSR1Y44YJ7CJD4C2=%C3%A9-compat%C3%ADvel-com-quais-padr%C3%B5es-de-compliance how-many-roles-and-api-tokens-can-i-create=quantas-fun%C3%A7%C3%B5es-e-quantos-tokens-de-api-posso-criar h_01K85N26X17PGVN4C6108A47TB=quantas-fun%C3%A7%C3%B5es-e-quantos-tokens-de-api-posso-criar can-i-integrate-with-my-existing-security-tools=posso-fazer-a-integra%C3%A7%C3%A3o-com-as-minhas-ferramentas-de-seguran%C3%A7a-existentes h_01K85N2QW51KDHKE4CQE7VJQHE=posso-fazer-a-integra%C3%A7%C3%A3o-com-as-minhas-ferramentas-de-seguran%C3%A7a-existentes what-network-restrictions-can-i-apply=quais-restri%C3%A7%C3%B5es-de-rede-posso-aplicar h_01K85N37KPK5XTFRRGW62CCN4M=quais-restri%C3%A7%C3%B5es-de-rede-posso-aplicar how-long-are-audit-logs-retained=por-quanto-tempo-os-logs-de-auditoria-s%C3%A3o-retidos h_01K85N3SVXVC6TD85V1PQ4EF2D=por-quanto-tempo-os-logs-de-auditoria-s%C3%A3o-retidos does-this-replace-standard-security-features=esse-tipo-de-seguran%C3%A7a-substitui-os-recursos-padr%C3%A3o h_01K85N4BCQ3NCH1G2P0EFWE3TQ=esse-tipo-de-seguran%C3%A7a-substitui-os-recursos-padr%C3%A3o how-quickly-can-i-implement-these-security-controls=quando-posso-implementar-esses-controles-de-seguran%C3%A7a h_01K85N4VR1FBESRN1QDRYF077A=quando-posso-implementar-esses-controles-de-seguran%C3%A7a" />
