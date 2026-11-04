---
title: Integração do Winclap Analytics com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-09-04T11:07:12Z'
  edited_at: '2026-09-16T00:11:41Z'
  id: 360002403537
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360002403537
---
> **Em resumo:** o Winclap Analytics, um parceiro integrado da AppsFlyer, usa dados de atribuição da AppsFlyer para BI e análises pós-atribuição.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-winclap" />

## Configurar a Winclap

A configuração é feita na página **Integrações ativas**, mas para encontrar o parceiro você deve primeiro ir ao <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations">Marketplace de parceiros</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> **Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.
>
> **Para ativar a integração:**
>
> 1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace.Para editar**: na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
> 2. Selecione o aplicativo correspondente.
> 3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
> 4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.
>     [Saiba mais sobre a ativação de parceiros](#).
> 5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A configuração do Winclap Analytics usa apenas a aba ***Integração***.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** a esta página, você deve ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">aqui</Anchor>.**

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Winclap Analytics após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

![integração do winclap analytics - postbacks padrão](https://files.readme.io/a45d8d7ab4687876d8dea4b026580d80f4b34c151b00c3c47a701771d16582aa-50896714399761.png)

Para **instalações**, selecione:

* (Padrão) ***Somente este parceiro*** para eventos provenientes apenas de usuários atribuídos à Winclap.
* ***Todos os canais de mídia, incluindo orgânico*** para enviar postbacks para qualquer usuário que fizer download do aplicativo para a Winclap.

Para **reengajamentos**, os postbacks podem ser enviados para ***Somente este parceiro***.

Depois de salvar esta configuração, a AppsFlyer envia os seguintes dados ao Winclap Analytics para cada instalação, tanto orgânica quanto não orgânica:

* ID de clique
* Campaign name
* Agente de usuário
* Hora do clique
* IP
* Country
* CIDADE
* Subpublisher
* Device ID para Android & iOS
* Operadora
* Idioma
* ID da aplicação
* Receita
* Nome da aplicação
* Tempo de Instalação

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear quais eventos in-app enviar ao Winclap Analytics usando postbacks:

[![winclap analytics - configuração de postback de evento in-app](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)

1. Ative a opção ***Postbacks de eventos in-app*** para ON.
2. Defina a ***janela de postback de evento in-app***, se necessário (saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração da janela de postback de evento in-app</Anchor>).
3. Clique em ***Adicionar evento*** para adicionar um evento SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica**: Não encontra o evento que está procurando? Digite o nome do evento do SDK, clique em **Criar personalizado** e mapeie normalmente. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado</Anchor>. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pela Winclap.  <br />Obtenha com a Winclap o ID correspondente para cada um dos eventos que você deseja reportar e insira-o neste campo. |
| **Opção de envio** | Selecione a opção de envio para o evento:  <br />**Somente este parceiro** para eventos provenientes **somente** de usuários atribuídos a este parceiro  <br />**Todos os canais de mídia, incluindo orgânico** para disponibilizar toda a sua base de usuários para ser reportada ao parceiro |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

5. Clique em ***Salvar***.

Depois que essa configuração é salva, a AppsFlyer envia os seguintes dados para a Winclap Analytics para cada evento não orgânico:

* ID de clique
* Nome do evento
* Valor do evento
* Event revenue
* Moeda dos eventos in-app
* Receita do evento em USD
* Campaign name
* Agente de usuário
* Hora do clique
* IP
* Country
* CIDADE
* Sub publisher
* Device ID para Android & iOS
* Operadora
* Idioma
* ID da aplicação
* Receita
* Nome da aplicação
* Tempo de Instalação

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para a Winclap Analytics.

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

As permissões não estão disponíveis para a Winclap Analytics.

</Accordion>

<div data-zendesk-anchors="h_01H9HWQK6JA2194MPE8PVQJ346=importante setting-up-winclap=configurar-a-winclap h_01H9HWQK6JAQ2GCHHGQ57PJ570=configurar-a-winclap h_01H9HWQK6JRZ1KVDJK00PZR7T9=nota h_01H9HWQK6JX9MAD64MQ1HPK4T0=integration-tab activate-partner=ativar-parceiro h_01H9HWQK6JKRB5MDE43RKV3SEH=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01H9HWQK6JP4HQHRFC011KW6XQ=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWQK6J1MEK67XDMAMKAQKW=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWQK6JBH1M2MZQM12R0SAR=attribution-link-tab h_01H9HWQK6JG46BGNRMR8ZM9W2J=cost-tab h_01H9HWQK6J7HHJWKVB55WE1VW9=ad-revenue-tab h_01H9HWQK6J6BD0ER2M9Z7GYGSM=permissions-tab" />
