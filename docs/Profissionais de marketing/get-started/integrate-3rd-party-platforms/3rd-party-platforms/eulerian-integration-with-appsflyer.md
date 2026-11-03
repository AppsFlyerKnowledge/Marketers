---
title: Integração do Eulerian com AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Eulerian
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
  created_at: '2018-10-02T08:41:24Z'
  edited_at: '2026-08-19T00:10:59Z'
  id: 360001521405
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360001521405
---
> **Em resumo:** a Eulerian, um parceiro integrado da AppsFlyer, concentra-se na análise e na otimização em tempo real de operações de e-marketing. Com base em um sistema abrangente de coleta de dados, a suíte de marketing da Eulerian oferece uma combinação de soluções de atribuição web de marketing e gerenciamento de dados. Essa tecnologia permite que os usuários centralizem, analisem, gerenciem e ativem dados em tempo real.

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Configurando o Eulerian

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Eulerian inclui 4 guias: **Integração, Link de atribuição, Enriquecimento de dados** e **Permissões**. Clique nos itens abaixo para ler sobre a configuração das abas.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

### Configurações gerais

**HostID**

A Eulerian se conecta à AppsFlyer por meio de um Host ID exclusivo. Se você ainda não o tem, deve obtê-lo com a Eulerian para continuar com a integração.

![Eulerian_msc_new_2.png](https://files.readme.io/345b05c3960015bfe1b44dd2a298c4216185c2315fb859378e9e337ba2bf913a-360002665949.png)

Execute as etapas a seguir, conforme necessário:

* Digite o **HostID**
* Ative **Enable** para enviar todas as instalações para a Eulerian

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a Eulerian após instalações de usuários. Use esta seção para definir o envio desses postbacks.

![Eulerian_new_2.png](https://files.readme.io/59cb41cdbec6c06dd4fc2086d238fe2015e5414a474591b23f9a18f8421fb030-360002795789.png)

Selecione **Eventos atribuídos a qualquer parceiro** para enviar postbacks à Eulerian.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Eulerian por meio de postbacks.

![Eulerian_new_3.png](https://files.readme.io/c190a6b05c977c8d5fa2a0e5301cdb5be239e56455b066cba93b8c1ffa6fcd9a-360002795829.png)

1. Digite o HostID novamente.
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado da Eulerian.  <br />Obtenha o ID do evento correspondente na Eulerian e insira-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

6. Clique em **Salvar**.

Depois de salvar, a AppsFlyer começa a enviar dados para a Eulerian para cada instalação orgânica e instalação não orgânica.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para a Eulerian.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

O custo não tem suporte na integração com a Eulerian.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não tem suporte na integração com a Eulerian.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Permissões não estão disponíveis para a Eulerian.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7FC3ME19HXCRQ0XKVQQC=importante setting-up-eulerian=configurando-o-eulerian h_01H9FK7FC309KKTAKZ1K9AHAN5=configurando-o-eulerian h_01H9FK7FC3K3Y8220AG9YK3BP8=integration-tab activate-partner=ativar-parceiro h_01H9FK7FC316DZHE9YKSWQ5A5N=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK7FC4ZBQ2XPTFYQ4C7XH6=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FK7FC4VBY3TEE6HEJZCWWT=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK7FC4KF5QGXA9KQ4YQEA3=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK7FC4H7QSFGWDV1AP0YK6=attribution-link-tab h_01H9FK7FC48YAYF3TGXC2C9EB8=cost-tab h_01H9FK7FC4YAPTGA15172P5TXB=ad-revenue-tab h_01H9FK7FC46W5A1BRSVPBEGJTK=permissions-tab" />
