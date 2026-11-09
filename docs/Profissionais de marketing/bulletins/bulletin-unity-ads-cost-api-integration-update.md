---
title: 'Boletim: Atualização da integração da API de custos do Unity Ads'
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-08-18T00:21:21Z'
  id: 26078530790289
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/26078530790289
---
| **Novidades** | A AppsFlyer tem uma integração de API com o Unity que nos permite obter dados de custo. A API será atualizada em breve. Portanto, é necessário atualizar a integração para continuar a obter os dados do custo do Unity. |
| --- | --- |
| **Data de atualização** | 6 de agosto de 2024 |
| **Tudo o que você precisa saber** | <ul><li>O Unity está introduzindo uma nova integração da API de custos.</li><li>A antiga integração da API de custos pode obter dados de custos até à sua data de expiração, 1 de outubro de 2024.</li></ul> |
| **O que é preciso fazer** | Você deve atualizar as suas credenciais para a nova integração da API de custos do Unity para continuar a obter dados de custos após 1 de outubro de 2024.<br /><br />As credenciais necessárias são:<ul><li>ID principal da organização</li><li>Chave secreta da conta de serviço</li><li>ID da chave da conta de serviço</li></ul>Siga as nossas instruções nas seções seguintes para atualizar a integração do custo do Unity na AppsFlyer. A integração tem 2 etapas:<ol><li>[Obter as novas credenciais do Unity](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[Atualize a integração da API de custos do Unity inserindo as credenciais na AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Procedimentos de integração da API de custo unitário

A integração da API de custos do Unity requer 2 passos:

1. Obter as novas credenciais do Unity.
2. Atualize a integração da API de custos do Unity inserindo as credenciais na AppsFlyer.

As etapas são descritas nas seções seguintes.

<div id="get-unity-credentials" />

<Accordion title="Obter credenciais do Unity">

As credenciais necessárias para a integração da API de custos do Unity são:

* ID principal da organização
* Chave secreta da conta de serviço
* ID da chave da conta de serviço

**Observação**: Recomenda-se a criação de uma nova conta de serviço do Unity para obter a chave secreta e o ID da chave. Fornecemos instruções sobre como o fazer abaixo.

**Para configurar uma conta de serviço do Unity e obter as credenciais necessárias para a integração da API de custos do Unity**:

1. Faça login na sua conta do Unity Cloud.
2. No menu do lado esquerdo, acesse **Grow (Aquisição de utilizadores do Unity Ads)** > **Configurações**.  
    <Image align="center" alt="" src="https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png" />
3. Encontre, copie e salve o **ID principal da organização**.  
   Exemplo de ID principal da organização: 5773102414648
4. No menu do lado esquerdo, acesse **Grow (Aquisição de usuários do Unity Ads)** > `{}` **API Management** e, na seção **Stats API v2.0** , **clique em Conta de serviço.**  
    <Image align="center" alt="" src="https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png" />
5. Clique em **+ Novo** para criar uma nova conta de serviço.  
    <Image align="center" alt="" src="https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png" />
6. Na seção **Chaves** , clique em **+ Adicionar chave** para criar uma chave para a conta de serviço.  
    <Image align="center" alt="" src="https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png" />
7. Copie e guarde o **ID da chave** e a **Chave secreta**. **Observação**: Esta é a única vez em que pode você pode acessar a chave secreta, por isso não se esqueça de salvá-la!
   * Exemplo de chave secreta da conta de serviço: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Exemplo de chave secreta da conta de serviço ID da chave: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      <Image align="center" alt="" src="https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png" />
8. Na seção **Funções da organização**, clique em **+ Gerenciar funções da organização**.  
    <Image align="center" alt="" src="https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png" />
9. Em **Editar funções na organização**, defina **Growth** como **Advertise Stats API MMP Viewer**.  
    <Image align="center" alt="" src="https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png" />

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="Atualizar a integração da API de custos do Unity na AppsFlyer">

**Para atualizar a API de custos do Unity na AppsFlyer**:

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações ativas** e selecione **Unity**.
2. Clique em **Gerenciar integração**.
3. Abra a aba de **Custo** do parceiro integrado
4. Ative a alavanca **Obter dados de custo**. Você verá os requisitos para se conectar ao parceiro.
5. Insira suas credenciais do Unity.
6. Clique em **Salvar custo**.
7. Clique em **Testar conexão**.  
   * A API está ativa. A AppsFlyer coleta dados do parceiro 6 vezes por dia, em média uma vez a cada quatro horas.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data">Saiba mais sobre como conectar as integrações de custo</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o-da-api-de-custo-unit%C3%A1rio h_01J11ZP5XG6VDSQKRWASAYK4QJ=procedimentos-de-integra%C3%A7%C3%A3o-da-api-de-custo-unit%C3%A1rio h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
