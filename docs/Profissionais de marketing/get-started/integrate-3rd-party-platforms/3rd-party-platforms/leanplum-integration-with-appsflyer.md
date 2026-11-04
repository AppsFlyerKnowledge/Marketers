---
title: Integração do Leanplum com a AppsFlyer
metadata:
  keywords:
    - Leanplum
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
  created_at: '2016-08-08T13:41:18Z'
  edited_at: '2026-08-19T00:11:14Z'
  id: 211487846
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/211487846
---
> **Em resumo:** o Leanplum, um parceiro integrado da AppsFlyer, é uma plataforma de marketing mobile projetada para ações inteligentes. Sua solução integrada oferece engajamento por meio de mensagens e da experiência in-app. O Leanplum oferece mensagens, automação, edição de aplicativo, personalização, testes A/B e analytics.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-leanplum" />

## Configurando o Leanplum

Os clientes do Leanplum podem se integrar à AppsFlyer enviando ao Leanplum um postback que contém informações do publisher. Isso permite visualizar esses dados no analytics do Leanplum, bem como usá-los para segmentação em testes A/B ou campanhas de marketing, usando o menu de segmentação e direcionamento do Leanplum.

Antes de ativar a integração com a AppsFlyer, primeiro você deve confirmar que a integração do Leanplum está usando o mesmo Device ID que a AppsFlyer. Isso é importante porque o Leanplum associa a instalação do usuário ao postback usando o Device ID; portanto, se não corresponderem, o Leanplum não poderá reportar os dados.

Por padrão, o Leanplum coleta o IDFV para iOS e o hash MD5 do endereço MAC para Android, mas isso pode ser alterado facilmente para IDFA no iOS e GAID no Android com uma linha de código. Para saber como alterar o formato do Device ID para Android e iOS, clique <Anchor target="_blank" href="https://docs.leanplum.com/docs/which-device-id-format-should-i-use">aqui</Anchor>.

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Leanplum usa apenas a aba **Integração**.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

**ID do aplicativo e chave do cliente**

O Leanplum se conecta à AppsFlyer por meio de um ID do aplicativo e uma chave do cliente exclusivos. Se você ainda não os tiver, deverá obtê-los com o Leanplum para continuar com a integração ou seguir as etapas abaixo.

![Leanplum_msc_new_3.png](https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png)

**Envio de IDFA ou IDFV**

Se a opção estiver ativa, o IDFV será enviado em um postback. Se nenhum IDFV for encontrado, o IDFA será enviado como alternativa.

Se a opção estiver inativa, o IDFA será enviado em um postback. Se nenhum IDFA for encontrado, o IDFV será enviado como alternativa.

Se nenhum dos dois estiver disponível, nenhum postback será enviado.

<div id="obtaining-the-app-id-and-client-key" />

### Como obter o ID do aplicativo e a chave do cliente

Clique no seu nome no canto superior direito da tela e selecione **Configurações do aplicativo**

![](https://files.readme.io/fcb9bb4fab1eec1db130904c2c4856529f58582bd8c9c04f08200ed82c0fcb80-206117303.png)

Selecione um aplicativo e clique em **Keys & Settings**

[![](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)

![](https://files.readme.io/cd638732b197f03c6194b8bae7b8f726a6e4c16661702fdad48054a35ce333e5-206117343.png)

<div id="default-postbacks" />

### Postbacks padrão

O AppsFlyer pode enviar postbacks automáticos para instalações de usuários do Leanplum. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Leanplum para qualquer usuário que baixar o aplicativo.

Clique em **Guardar.**

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Leanplum.

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

Permissões não estão disponíveis para o Leanplum.

</Accordion>

<div id="viewing-user-attribution-data-in-leanplum" />

## Visualizando dados de atribuição do usuário no Leanplum

Depois de configurar a integração entre o Leanplum e o AppsFlyer, você pode acessar as informações usando o menu de segmentação do Leanplum:

[![](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)

Esse menu está disponível nas seções Analytics, Messages, A/B Tests e Usuários da plataforma Leanplum. Você pode filtrar, agrupar e criar coortes com base nesses dados no Analytics, filtrar por esses dados na seção Usuários e segmentar com base nesses dados no Analytics e em A/B Tests.

<div data-zendesk-anchors="h_01H9FKB51R253NAXWEKSYVRZ3P=importante setting-up-leanplum=configurando-o-leanplum h_01H9FKB51RA35X0G19ZPN2KAQ7=configurando-o-leanplum h_01H9FKB51VVVS5C4WEQ4FKHH4H=integration-tab activate-partner=ativar-parceiro h_01H9FKB51VY7QASRV8XW8KRZK1=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FKB51VA8A6XZYM3W6AVNMH=configura%C3%A7%C3%B5es-gerais obtaining-the-app-id-and-client-key=como-obter-o-id-do-aplicativo-e-a-chave-do-cliente h_01H9FKB51VFGCW21AG0BYWGFXZ=como-obter-o-id-do-aplicativo-e-a-chave-do-cliente default-postbacks=postbacks-padr%C3%A3o h_01H9FKB51V63GPAS3R1GBWNTWR=postbacks-padr%C3%A3o h_01H9FKB51VR8160P1RQK994DGZ=attribution-link-tab h_01H9FKB51VEJWHZXKENFASR9NG=cost-tab h_01H9FKB51V7C44MGTWR3RNX4D8=ad-revenue-tab h_01H9FKB51VY9V478W297NB58EM=permissions-tab viewing-user-attribution-data-in-leanplum=visualizando-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-no-leanplum h_01H9FKB51VHAYS1STK6GQE4515=visualizando-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-no-leanplum" />
