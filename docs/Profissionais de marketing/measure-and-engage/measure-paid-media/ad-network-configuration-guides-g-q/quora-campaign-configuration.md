---
title: Configuração de campanhas do Quora
metadata:
  keywords:
    - Advertisers
    - Quora
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-02-17T12:56:30Z'
  edited_at: '2026-08-19T00:25:42Z'
  id: 360000974737
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/360000974737
---
> **Visão geral:** o Quora, um dos parceiros integrados da AppsFlyer, é uma das comunidades online de perguntas & respostas mais populares. Mais de 300 milhões de visitantes únicos acessam o Quora todos os meses para fazer perguntas e ler respostas esclarecedoras. O público amplo e engajado do Quora é um dos principais motivos pelos quais profissionais de marketing têm obtido sucesso ao anunciar no Quora.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/quora.png?v=1" width="83px" />

<div id="setting-up-quora" />

## Configurando o Quora

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Em sua **primeira visita**, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Quora inclui 3 guias ativas: **Integração, link de atribuição** e **Permissões**. Clique nos itens abaixo para ler sobre a configuração das abas.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

Postbacks padrão

Envie postbacks automáticos para o Quora após instalações de usuários.

<div id="note" />

> 📘 **Nota**
>
> A opção **Somente eventos atribuídos a este parceiro** é a única disponível no Quora e vem selecionada por padrão.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao Quora, quer o parceiro atue como ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para o Quora, a aba de permissões fica ativa e você pode conceder controle ao Quora.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-quora=configurando-o-quora h_01HKW851RK4MHYEW1AY2E2KH5Q=configurando-o-quora h_01HKW851RK9KMV6PJ7YEN7ZMW2=dica h_01HKW851RKYQ0T9XY74EXB4GWX=integration-tab activate-partner=ativar-parceiro h_01HKW851RKD56502S4PSX8096T=ativar-parceiro h_01HKW851RM09VR496Q7XFB3EMY=nota h_01HKW851RM4HP8EVGKD2EJH529=attribution-link-tab h_01HKW851RM4DGBABR81ZJZHBYW=cost-tab h_01HKW851RMQ0KY4CMWP7N4F2T4=ad-revenue-tab h_01HKW851RMV5A43RS3ZFZEPW8Z=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW851RM2G6Y4J4KQBHAEF3A=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />
