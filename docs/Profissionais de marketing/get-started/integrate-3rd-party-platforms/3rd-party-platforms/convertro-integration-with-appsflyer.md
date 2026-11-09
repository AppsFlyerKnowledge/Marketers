---
title: Integração do Convertro com AppsFlyer
metadata:
  keywords:
    - Attribution
    - Convertro
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
  created_at: '2015-12-24T11:37:56Z'
  edited_at: '2026-08-19T00:10:53Z'
  id: 207040636
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207040636
---
> **Em resumo:** o Convertro, um parceiro integrado da AppsFlyer, busca ser a principal ferramenta automatizada para que profissionais de marketing entendam de fato a performance de suas escolhas de publicidade e ajam com base nesses insights o mais rapidamente possível. Eles criaram uma tecnologia que não apenas coleta informações granulares sobre o caminho do cliente até a conversão, mas também é capaz de otimizar cientificamente o mix de marketing e entender automaticamente como realocar o gasto para maximizar o ROI.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-convertro" />

## Configuração do Convertro

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Convertro usa apenas a aba **Integração**.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na sua **primeira visita** aqui, você deverá ativar a opção abaixo. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
**Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

<div id="general-settings" />

### Configurações gerais

**URL da página, ID do site e nome do cliente**

O Convertro se conecta à AppsFlyer por meio de uma URL da página, um ID do site e um nome do cliente exclusivos. Se você ainda não tiver esses dados, deverá obtê-los com o Convertro para continuar com a integração ou seguir as instruções abaixo.

<Image align="center" alt="" src="https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png" />

<div id="obtaining-the-client-name-page-url--site-id-from-the-convertro-platform" />

### Como obter o "Nome do cliente, URL da página & ID do site" na plataforma Convertro

Para obter o nome do cliente, a URL da página e o ID do site, faça login no dashboard do Convertro:

**URL da página:**

<Image align="center" alt="" src="https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png" />

**ID do site:**

<Image align="center" alt="" src="https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png" />

**Nome do cliente:**

<Image align="center" alt="" src="https://files.readme.io/2e5342006bdfff9e3b3c1dffdaed3e9d83ec2fe4c465b7918023a359776cee91-204595606.png" />

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para instalações de usuário do Convertro. Use esta seção para definir o envio desses postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Convertro para qualquer usuário que fizer o download do aplicativo ou selecione **Off**.

Clique em **Guardar.**

<div id="in-app-event-settings" />

### Configurações de eventos in-app

<Image align="center" alt="" src="https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png" />

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Convertro por meio de postbacks.

1. Insira novamente o nome do cliente, o ID do site e a URL da página.
2. Ative a opção Postbacks de eventos in-app.
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no lado do Convertro.  <br />Obtenha o ID do evento correspondente no Convertro e insira-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do rich in-app event para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

Clique em **Guardar**.

Depois que essa configuração é salva, a AppsFlyer começa a enviar os seguintes dados ao Convertro para cada instalação orgânica e instalação não orgânica:

* Parâmetros do Convertro
* Device ID para Android e iOS
* Media Source
* Campaign name
* Hora do clique
* IP do usuário
* User-Agent
* ID de usuário do cliente (opcional, se configurado)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para Convertro.

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

As permissões não estão disponíveis para Convertro.

</Accordion>

<div data-zendesk-anchors="h_01H9FK64HSFKW54BBRVB3W9ZR0=importante setting-up-convertro=configura%C3%A7%C3%A3o-do-convertro h_01H9FK64HS75VDP07DGETASAH7=configura%C3%A7%C3%A3o-do-convertro h_01H9FK64HSK1B1Y9BRWP7AN96R=integration-tab activate-partner=ativar-parceiro h_01H9FK64HS7VJWHF1QCWNYVBX8=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK64HSCAYHB82DZX0JA2ZX=configura%C3%A7%C3%B5es-gerais obtaining-the-client-name-page-url-site-id-from-the-convertro-platform=como-obter-o-nome-do-cliente-url-da-p%C3%A1gina--id-do-site-na-plataforma-convertro h_01H9FK64HSKR8N45RXQQC3VEW1=como-obter-o-nome-do-cliente-url-da-p%C3%A1gina--id-do-site-na-plataforma-convertro default-postbacks=postbacks-padr%C3%A3o h_01H9FK64HTPK69QQ92DJ55RNVM=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK64HTGKXWW0FMN0T445FG=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK64HTCM3H0243FVFDY0ET=attribution-link-tab h_01H9FK64HT9JHKBN5W8H16E6CK=cost-tab h_01H9FK64HTSP070RX7ZCYM7KE3=ad-revenue-tab h_01H9FK64HTCXAMY6TR186EE0M9=permissions-tab" />
