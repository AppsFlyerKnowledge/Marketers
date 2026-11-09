---
title: Integração do CleverTap com AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
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
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-08-19T00:10:51Z'
  id: 360001299165
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360001299165
---
> **Em resumo:** o CleverTap é uma nuvem moderna e integrada de retenção que permite que marcas digitais voltadas ao consumidor aumentem a retenção de clientes e o valor do ciclo de vida.

<Image align="center" alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-clevertap" />

## Configurando o CleverTap

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo:

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

**Token da conta**

O CleverTap se conecta ao AppsFlyer por meio de um token de conta exclusivo, região, código de acesso da conta e ID da conta. Se você ainda não tiver esses dados, deverá obtê-los com o CleverTap para continuar com a integração ou seguir as etapas abaixo.

<div id="important-1" />

> 🚧 **Importante!**
>
> Para permitir o envio de postbacks ao CleverTap, conclua **as duas** etapas a seguir:
>
> * Preencha pelo menos **um** dos seguintes campos: account\_token, account\_passcode ou account\_id
> * No SDK do AppsFlyer, defina o valor do ID de usuário do cliente (<Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">iOS, Android</Anchor>). Consulte a [documentação do CleverTap](https://developer.clevertap.com/docs/appsflyer#section-step-2-integration) para ver as orientações sobre qual parâmetro é recomendado usar como Customer User ID. Observe que, se o Customer User ID estiver vazio, os postbacks não serão enviados ao CleverTap.

<Image align="center" alt="CleverTap_msc_new_2.png" src="https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png" />

<div id="obtain-clevertap-account-token" />

### Obtenha o token da conta do CleverTap

**Para obter tokens de conta do CleverTap:**

1. No dashboard do CleverTap, acesse **Settings** no canto superior direito.

   <Image align="center" alt="CleverTap_msc_new_4.png" src="https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png" />
   Na parte superior da tela “Settings”, você verá o ID da conta do CleverTap, o token da conta e o código de acesso ao lado de "Account ID", “Account token” e “Passcode”, respectivamente:

   <Image align="center" alt="CleverTap_msc_new_5.png" src="https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png" />
2. Para revelar os valores, clique nos ícones de 'olho' ao lado de cada campo.
3. Copie os valores e cole-os na página CleverTap do AppsFlyer.

   <div id="note" />

   > 📘 **Nota**
   >
   > * A região depende da URL do dashboard do CleverTap da sua conta:
   > * Se a URL da sua conta for <Anchor target="_blank" href="https://eu1.dashboard.clevertap.com/">https://eu1.dashboard.clevertap.com</Anchor>, a região será EU1, o que significa que os dados da conta estão hospedados em um data center baseado na UE.
   > * Se a URL da sua conta for <Anchor target="_blank" href="https://in1.dashboard.clevertap.com">https://in1.dashboard.clevertap.com</Anchor>, a região será IN1, o que significa que os dados da conta estão hospedados em um data center baseado na IN.
   > * Se a URL da sua conta for [https://aps3.dashboard.clevertap.com](https://aps3.dashboard.clevertap.com), a região será ID, o que significa que os dados da conta estão hospedados em um data center baseado na Indonésia.* A configuração de região diferencia maiúsculas de minúsculas e deve ser usada apenas com letras maiúsculas. Quando letras minúsculas são usadas, o postback será enviado para o servidor padrão (EU1).

4. Finalize a integração de acordo com a <Anchor target="_blank" href="https://developer.clevertap.com/docs/appsflyer#section-step-2-integration">documentação da CleverTap</Anchor>.

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a CleverTap após instalações de usuários. Use essa seção para definir a fonte de usuários para a qual os postbacks são enviados. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

<Image align="center" alt="clevertap-default-postbacks_en-us.png" src="https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png" />

**To send postbacks for any user that downloads the app to CleverTap:** select **All media sources, including organic**.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

<Image align="center" alt="clevertap-in-app-events_en-us.png" src="https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png" />

Nesta seção, você mapeia eventos da AppsFlyer com o parceiro por meio de postbacks.  
Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app.</Anchor>

**Para configurar postbacks de eventos in-app:**

1. Insira todos os tokens obrigatórios.
2. Ative o **postback de eventos in-app.**
3. Clique em **Adicionar evento** para adicionar um evento do SDK à lista.
4. Selecione o **nome do evento de SDK** no menu suspenso.
5. Selecione a opção necessária no menu suspenso Enviar receita:
   * **Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.
   * **Com valores e sem receita:** envia todos os parâmetros excluindo o valor da receita.
   * **Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).
6. Para concluir a configuração de integração, clique em **Salvar integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não se aplicam a este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Os dados de receita de anúncios não se aplicam a este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para a CleverTap.

</Accordion>

<div id="measure-clevertap-owned-media" />

## Meça as mídias próprias da CleverTap

Como a CleverTap é uma plataforma que usa e-mails, SMS, notificações por push etc. para fins de automação de marketing, você pode usar o <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">AppsFlyer OneLink</Anchor> como solução para medir as mídias próprias originadas da CleverTap.

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=importante setting-up-clevertap=configurando-o-clevertap h_01H9FK5JT1ATCHY6WAVB6E2YEW=configurando-o-clevertap h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab activate-partner=ativar-parceiro h_01H9FK5JT12Z1M6WW3GQQF5QVN=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK5JT1FMC6JANBP9KBB0V2=configura%C3%A7%C3%B5es-gerais h_01H9FK5JT1MQKT7KWJ3EVNEA1E=importante-1 obtain-clevertap-account-token=obtenha-o-token-da-conta-do-clevertap h_01H9FK5JT1RVJ1V0CGXSH1XZPM=obtenha-o-token-da-conta-do-clevertap h_01H9FK5JT2QV9CKSZ1N3S4WTGE=nota default-postbacks=postbacks-padr%C3%A3o h_01H9FK5JT2CE0WQ9HAGVGAQA5B=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK5JT2YS7G5WDD4F5MPYVZ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab measure-clevertap-owned-media=me%C3%A7a-as-m%C3%ADdias-pr%C3%B3prias-da-clevertap h_01H9FK5JT2AZTT5936DD88ZZV3=me%C3%A7a-as-m%C3%ADdias-pr%C3%B3prias-da-clevertap" />
