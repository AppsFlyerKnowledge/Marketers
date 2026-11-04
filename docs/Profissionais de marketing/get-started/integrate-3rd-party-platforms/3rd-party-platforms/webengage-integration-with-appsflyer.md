---
title: Integração do WebEngage com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-25T13:44:42Z'
  edited_at: '2026-08-19T00:11:56Z'
  id: 7898288493841
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/7898288493841
---
> **Em resumo:** o WebEngage, um parceiro integrado da AppsFlyer, é uma Nuvem de Marketing Inteligente criada para um mundo "mobile-first".

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-webengage" />

## Configurando o WebEngage

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na sua primeira visita, habilite **Ativar parceiro** para configurar a integração. A alavanca deve ser mantida enquanto você trabalhar com o parceiro. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do WebEngage utiliza apenas a aba **Integração**.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">como configurar o cabeçalho da página do parceiro.</Anchor>

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba de integração se divide em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

O WebEngage se conecta à AppsFlyer por meio de uma chave de API e da região do data center do WebEngage.

* **api\_key:** Insira a chave de API. Para obtê-la, faça login na sua conta do WebEngage e siga as <Anchor target="_blank" href="https://docs.webengage.com/docs/appsflyer#step-3-add-webengage-api-key--data-center-region">instruções</Anchor>.
* **Região:** Insira a região em que seus dados serão hospedados: **US** (para o data center dos EUA) ou **IN** (para o data center da Índia). Por padrão, todos os dados são armazenados no data center dos EUA.

![web_mo_engage_general_settings_en-us.png](https://files.readme.io/1297a02a9e280b238a222b14972dc657acffe4566dc49d607178ea43fdc01a77-8089123842705.png) 

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o WebEngage após instalações e reengajamentos de usuários.

* **Desativado**: não envie nenhum postback de instalação.
* **Todos os canais de mídia, incluindo orgânicos**: envie postbacks de eventos atribuídos a qualquer parceiro e de eventos orgânicos.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

<div id="note" />

> 📘 **Nota**
>
> Como uma network de todas as instalações, o WebEngage prefere receber postbacks de todas as novas instalações do seu aplicativo de qualquer fonte, inclusive orgânica. O WebEngage recomenda selecionar **Todos os canais de mídia, incluindo orgânicos**.

<div id="in-app-event-settings" />

### Configurações de eventos in-app

Mapeie eventos da AppsFlyer com o WebEngage por meio de postbacks. Se o envio de postbacks estiver ativado, isso inclui eventos in-app rejeitados (eventos bloqueados pelo Protect360 ou eventos considerados não compatíveis com as regras de validação de destino).

<div id="to-configure-in-app-event-postbacks" />

#### Para configurar postbacks de evento in-app

1. Insira a **api\_key** e a **Região**.
2. Ative **postback de eventos in-app.**
3. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página.
4. Complete os parâmetros necessários.
5. [Opcional] Clique<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />para definir condições para enviar determinados eventos in-app ao parceiro.  
   Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">postbacks de eventos in-app condicionais</Anchor>.

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento da AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo, seja de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados"> mapeamento de eventos personalizados.</Anchor></li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todos os canais de mídia, incluindo orgânicos**: envie postbacks para eventos atribuídos a qualquer parceiro, incluindo eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: enviar todos os parâmetros **excluindo** o valor da receita.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

**Link de atribuição** não tem suporte na integração com este parceiro.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

**Dados de custo** não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

**Receita de anúncios** não tem suporte na integração com este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

**Permissões** não são compatíveis com a integração desse parceiro.

</Accordion>

<div data-zendesk-anchors="h_01H9HWK7APBFK7RWVFH79VW0ME=importante setting-up-webengage=configurando-o-webengage h_01H9HWK7AP6Z398NP3G2BQQBTF=configurando-o-webengage h_01H9HWK7AP3ERT0TM39E6S5M79=integration-tab activate-partner=ativar-parceiro h_01H9HWK7AP3FMR5RMANZCMQ6M0=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9HWK7APG1STZ4Q19QVX4KRY=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9HWK7AP23GK6WWJTB543FEQ=postbacks-padr%C3%A3o h_01H9HWK7APMBSZ1PG8MK88HZFS=nota inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9HWK7APFNAFE9YM2484DDHD=configura%C3%A7%C3%B5es-de-eventos-in-app to-configure-inapp-event-postbacks=para-configurar-postbacks-de-evento-in-app h_01H9HWK7APZM8328V0EV4B5QDN=para-configurar-postbacks-de-evento-in-app h_01H9HWK7AQTZXE7GPX5E9X2ZYN=attribution-link-tab h_01H9HWK7AQ8SXED5KHVD5T4DZZ=cost-tab h_01H9HWK7AQ2JG4BRS784M85Z6E=ad-revenue-tab h_01H9HWK7AQ5YJDY2M96CA05H6P=permissions-tab" />
