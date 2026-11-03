---
title: Integração do Localytics com a AppsFlyer
metadata:
  keywords:
    - Localytics
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
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-08-19T00:11:19Z'
  id: 210748626
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/210748626
---
> **Resumo:** o Localytics, um parceiro integrado da AppsFlyer, é uma plataforma de marketing e plataforma de analytics para aplicativos mobile e web. O app analytics do Localytics oferece análise de retenção com base em coortes, funis, segmentação de clientes e análises em tempo real para identificar grupos de usuários com as maiores taxas de fidelidade e valor vitalício. O app marketing do Localytics oferece serviços de automação de marketing para aplicativos ao mensurar o sucesso de longo prazo das campanhas de aquisição de clientes e enviar mensagens in-app e push avançadas e acionáveis aos clientes relevantes quando elas podem ter o maior impacto.

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configurando o Localytics

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Localytics inclui 4 abas: **Integração, Link de atribuição, Enriquecimento de dados** e **Permissões**. Clique nos itens abaixo para ler sobre a configuração das abas.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

[![](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)](https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png)

### Configurações gerais

**ID de atribuição**

O Localytics se conecta à AppsFlyer por meio de um ID de atribuição exclusivo. Se você ainda não o tem, deve obtê-lo com o Localytics para continuar com a integração ou seguir as etapas abaixo.

![Localytics_msc_new_3.png](https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png)

Como obter a App Key do Localytics

* Faça login no dashboard do Localytics
* Clique em **Atribuição** no painel esquerdo
* Selecione **Atribuição de third party**
* Copie a chave de atribuição

[![](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)](https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png)

Configure o Localytics no Dashboard da AppsFlyer.

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Localytics após instalações de usuários. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Localytics para qualquer usuário que baixar o aplicativo.

Depois de concluir a configuração, a AppsFlyer envia os seguintes dados ao Localytics para cada instalação orgânica e não orgânica:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

Clique em **Guardar.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Localytics.

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

As permissões não estão disponíveis para o Localytics.

</Accordion>

## Visualização dos dados de atribuição no console do Localytics

Acesse a tela de Configurações de Atribuição do Localytics e habilite a Atribuição de third party no Localytics para ver os dados da AppsFlyer.

[![](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)](https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png)

[![](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)](https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png)

<div data-zendesk-anchors="h_01H9FKCBM5W16BYJQ6TH9SSBVC=importante setting-up-localytics=configurando-o-localytics h_01H9FKCBM5Z39GPE5772799DB1=configurando-o-localytics h_01H9FKCBM5JZ5V4YMB6S24JA6V=integration-tab activate-partner=ativar-parceiro h_01H9FKCBM5PSZZ5FP1G12M9F63=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FKCBM5N4RB5ZSB61W02368=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FKCBM5STZ79NBP3EFYGMB9=postbacks-padr%C3%A3o h_01H9FKCBM54S067F1Z51E4FXQD=attribution-link-tab h_01H9FKCBM591RG57Q80JZ7FJWY=cost-tab h_01H9FKCBM5Q8P53V34QRQMS0BS=ad-revenue-tab h_01H9FKCBM5GGXX04JEH3DHNV78=permissions-tab viewing-the-attribution-data-in-the-localytics-console=visualiza%C3%A7%C3%A3o-dos-dados-de-atribui%C3%A7%C3%A3o-no-console-do-localytics h_01H9FKCBM5VBM87C2PHNZVZ4RJ=visualiza%C3%A7%C3%A3o-dos-dados-de-atribui%C3%A7%C3%A3o-no-console-do-localytics" />
