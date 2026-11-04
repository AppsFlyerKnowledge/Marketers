---
title: Guia de integração do IBM UBX com AppsFlyer
metadata:
  keywords:
    - Analytics
    - IBM
    - UBX
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
  created_at: '2016-07-03T09:06:26Z'
  edited_at: '2026-08-19T00:11:04Z'
  id: 210093266
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/210093266
---
> **Em resumo:** o IBM UBX (Universal Behavior Exchange), um parceiro integrado da AppsFlyer, é um recurso do IBM Marketing Cloud e de outras ofertas do IBM Commerce que permite aos profissionais de marketing controlar toda a integração dos dados dos clientes com um console fácil de usar. Essa funcionalidade de troca aberta de dados oferece uma visão contextual dos comportamentos de compra do cliente em todos os canais, dispositivos e interações, para que os profissionais de marketing possam criar e implementar rapidamente campanhas eficazes, oferecendo experiências significativas instantaneamente, ao mesmo tempo em que impulsionam o ROI.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-ibm" />

## Configurar a IBM

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração da IBM usa apenas a aba **Integration**.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

**Chave de autorização**

A IBM se conecta com a AppsFlyer por meio de uma chave de autorização exclusiva. Se você ainda não a tem, deve obtê-la com a IBM para continuar com a integração ou siga as etapas abaixo.

![IBM_msc_new_2.png](https://files.readme.io/d6dddd7232ba7ecba2ed5bd944f98669902689fc0953afc558fbc6586be8b5cf-360002219269.png)

<div id="obtaining-the-authorization-key" />

### Como obter a chave de autorização

A primeira etapa para configurar um endpoint genérico do publisher de eventos da AppsFlyer é criar um endpoint em branco na interface do UBX.

Para fazer isso, faça login na sua conta do UBX e acesse a aba **Endpoints**

![](https://files.readme.io/8c0833f890c5e2ed2df1c0a8904e1764b341a82f3381c0a1a3fb6effe4f76673-205128323.png)

Em seguida, clique em **Register new endpoint**

![](https://files.readme.io/23c8d4a88eda765fce1b42f9eb2e74b1325160e6d0602dc65a8ab05488598b9e-205053206.png)

Em seguida, selecione **AppsFlyer** e clique em **Next**.

![IBM_1.png](https://files.readme.io/f30b7b27d2ffecf3e562cbe651367306a581d1881325dd141c950b39efac016c-115002600286.png)

Clique em **Próximo**.

![Pasted_image_at_2017_02_23_02_48_PM.png](https://files.readme.io/11a94c4d9f4c9282c230e4cf69f31e0d39f4eb88196313b3cfc103a5bbaba9a4-115002600326.png)

Clique nos 3 pontos à direita no endpoint AppsFlyer recém-gerado e clique em **endpoint details**.

![IBM_3.png](https://files.readme.io/70edd2e14c6c344188dcc65b65b3a8d92081401dd34909f5a4e0dd6bd137b8df-115002599203.png)

Copie a chave de autenticação:

![IBM_Endpoint_details.png](https://files.readme.io/3706f4dd665d8d2a26de9013b03c0e6575d051f2fa5500033e172312a63f09ea-115002601006.png)

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para instalações de usuários da IBM. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Events attributed to any partner or organic** para enviar postbacks à IBM para qualquer usuário que faça o download do aplicativo ou selecione **Off**.

Clique em **Guardar.**

<div id="in-app-event-settings" />

### Configurações de eventos in-app

[![](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)](https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png)

Nesta seção, você pode mapear seus eventos da AppsFlyer com a IBM por meio de postbacks.

1. Insira a chave de autorização novamente.
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pela IBM.  <br />Obtenha o ID de evento correspondente da IBM e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do rich in-app evento para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para IBM.

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

As permissões não estão disponíveis para IBM.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8FS5T9KZ30N87B76QVT5=importante setting-up-ibm=configurar-a-ibm h_01H9FK8FS5QPJYSA7JVY4QNB3S=configurar-a-ibm h_01H9FK8FS5J30GZS634NMG62BQ=integration-tab activate-partner=ativar-parceiro h_01H9FK8FS5SYTBF8A3QX4QGESM=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK8FS5YXRCN83RHG6QBAKS=configura%C3%A7%C3%B5es-gerais obtaining-the-authorization-key=como-obter-a-chave-de-autoriza%C3%A7%C3%A3o h_01H9FK8FS5ZVGX5RK7K72SH6K6=como-obter-a-chave-de-autoriza%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o h_01H9FK8FS5SVF4YQC8AG2V6N8D=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK8FS54N196VQ0XCXJ763Q=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK8FS50TB7TZH9JKEH3Y7H=attribution-link-tab h_01H9FK8FS54P1MYVXGR46TXN7D=cost-tab h_01H9FK8FS600SP0MS1T6PTBMH4=ad-revenue-tab h_01H9FK8FS65VMZK13D2BE5DT09=permissions-tab" />
