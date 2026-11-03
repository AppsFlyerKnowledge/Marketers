---
title: Integração da Liquid com a AppsFlyer
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-08-19T00:11:16Z'
  id: 207040626
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207040626
---
> **Resumo:** a Liquid, parceira integrada da AppsFlyer, automatiza suas campanhas e processos sem a necessidade de acionar sua equipe de TI. O mecanismo de regras inteligentes deles atua com base no comportamento do usuário e em análises avançadas.

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configurando a Liquid

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.**

### Configurações gerais

**Token da API**

A Liquid se conecta ao AppsFlyer por meio de um token de API exclusivo. Se você ainda não tem esse token, solicite-o à Liquid para continuar com a integração ou siga as instruções abaixo.

[![](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)

### Como obter o token de API

Você pode encontrar o token de API fazendo login no dashboard da Liquid.

* Clique no ícone **Configurações**
* Copie o token da API de produção
* Insira o APP\_TOKEN que você recebeu da Liquid

### Postbacks padrão

O AppsFlyer pode enviar postbacks automáticos para instalações de usuários da Liquid. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks à Liquid para qualquer usuário que fizer o download do aplicativo ou selecione **Desativado**.

Clique em **Guardar.**

Depois que essa configuração for salva, o AppsFlyer começa a enviar os seguintes dados à Liquid para cada instalação orgânica e não orgânica:

* Token do Aplicativo
* customer\_user\_id conforme definido no SDK
* Fonte de mídia
* Nome da campanha

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para a Liquid.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Permissões não estão disponíveis para a Liquid.

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=importante setting-up-liquid=configurando-a-liquid h_01H9FKBW5QMJTARZ6KZ41QT1BN=configurando-a-liquid h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab activate-partner=ativar-parceiro h_01H9FKBW5RRYW1JTK2S9V4V6SA=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FKBW5RB52QQKVF5TMFVKKT=configura%C3%A7%C3%B5es-gerais obtaining-the-api-token=como-obter-o-token-de-api h_01H9FKBW5RCGHVJRJEBQW4KNGD=como-obter-o-token-de-api default-postbacks=postbacks-padr%C3%A3o h_01H9FKBW5RVYXPEEFDG948P1XV=postbacks-padr%C3%A3o h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
