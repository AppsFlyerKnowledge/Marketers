---
title: Configuração da integração do ChatGPT Ads (OpenAI)
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-30T03:39:01Z'
  id: 48439655791249
  locale: pt
  section: Measure paid media
  section_id: 6550990672401
  url: https://support.appsflyer.com/hc/pt/articles/48439655791249
---
> **Resumo:** O ChatGPT Ads, um parceiro integrado da AppsFlyer, é a plataforma de anúncios da OpenAI. Configure a integração para mensurar e atribuir instalações de aplicativos mobile, eventos in-app e conversões da web geradas pelas suas campanhas do ChatGPT Ads.

<div id="about-the-integration-with-chatgpt-ads" />

## Sobre a integração com o ChatGPT Ads

A integração da AppsFlyer com o ChatGPT Ads (OpenAI) permite que você mensure e atribua instalações de aplicativos, eventos in-app e conversões da web geradas pelas suas campanhas do ChatGPT Ads. Ela é compatível com a mensuração de sites e apps mobile.

* **App mobile:** a AppsFlyer atribui instalações e reengajamentos às suas campanhas do ChatGPT Ads e envia postbacks de eventos in-app.
* **Site:** a AppsFlyer envia eventos da web, como visualizações de página, conteúdo e compra, registrados pelo Web SDK da AppsFlyer para a Conversions API (CAPI) do ChatGPT Ads, além (ou em vez) do pixel JavaScript do ChatGPT Ads.

Se você também executar o pixel do ChatGPT Ads no seu site, o ChatGPT Ads elimina as duplicações entre os eventos do lado do servidor (enviados pela API de conversões, ou CAPI) e os eventos do pixel usando um ID de evento compartilhado, para que você possa executar a CAPI e o pixel em paralelo sem inflar suas contagens de conversão.

Inclua esse ID compartilhado como `af_customer_event_id` na carga útil do evento que você envia para a AppsFlyer. Veja [Integre seu site](#integrar-seu-site) abaixo.

<div id="set-up-the-integration" />

## Configurar a integração

Configure a integração separadamente para cada site e app mobile que você deseja mensurar. Você precisará de um Pixel ID e de uma API key da sua conta do ChatGPT Ads (OpenAI) Ads Manager para cada um.

**Pré-requisitos:**

* Antes de configurar a integração, abra uma conta no ChatGPT Ads.
* Seus sites e apps mobile são configurados na AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Saiba mais</Anchor>

**Para configurar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Marketplace**.  
   **Para editar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
2. Configure a integração para seu:

* [**App mobile:**](#integrar-seu-aplicativo-mobile) atribua instalações, reengajamentos e eventos in-app a campanhas do ChatGPT Ads.
* [**Site:**](#integrar-seu-site) envie eventos de conversão da web para a Conversions API do ChatGPT Ads, com a desduplicação em relação ao pixel do ChatGPT Ads.

<div id="integrate-your-mobile-app" />

## Integrar seu aplicativo mobile

Siga as etapas abaixo para configurar a atribuição e os postbacks de eventos in-app para o ChatGPT Ads no seu aplicativo mobile.

**Para integrar seu app mobile:**

1. Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Marketplace**.
2. Selecione seu app mobile no menu suspenso.  
   **Atenção:** você deverá repetir todas as etapas para cada plataforma onde seu aplicativo é executado, como Android e iOS.
3. Pesquise **ChatGPT Ads (OpenAI)** e clique em **Integrar**.
4. Complete a configuração nas abas descritas abaixo.

<div id="integration-tab" />

<Accordion title="Aba de integração">

<div id="activate-partner" />

#### Ativar parceiro

**Para ativar a integração:**

Habilite o botão **Ativar parceiro**.

**Aviso importante:** Essa opção **deve permanecer habilitada** enquanto você trabalhar com o ChatGPT Ads. Ao desativar a integração, você também desativará a atribuição e os postbacks para suas campanhas.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

<div id="general-settings" />

#### Configurações gerais

Insira as seguintes credenciais:

* **Pixel ID:** Um pixel é criado no seu ChatGPT Ads Manager. Você pode obtê-lo na aba de conversões na sua conta do Ads Manager.
* **API key:** Uma API key é necessária para autenticar chamadas da Events API. Você pode obtê-la na aba de conversões na sua conta do Ads Manager.   
  **Observação:** Certifique-se de usar a API key de conversões em vez da API key de gerenciamento de anúncios, pois as permissões necessárias exigem a CAPI key.

<div id="advanced-privacy" />

##### **Agregada da AppsFlyer**

O botão de alternância de Privacidade Avançada (AP) controla como os eventos são enviados para a OpenAI para usuários do iOS (14.5 ou superior) que não disponibilizaram o IDFA (do lado do anunciante ou do publisher):

* Privacidade avançada **desativada**: os eventos são enviados com todos os identificadores de usuário disponíveis (IPs, agente etc.), mesmo quando o IDFA não está disponível.
* Privacidade avançada **ativada**: somente os eventos atribuídos a `openai_int` são enviados, e esses postbacks incluem apenas dados de atribuição. Todos os identificadores em nível de usuário são removidos do postback antes do envio.

> 📘 **Note**
>
> A OpenAI não coleta nem compartilha o IDFA em dispositivos iOS, então a única maneira de garantir que os postbacks sem atribuição sejam enviados é desativar a privacidade avançada.

<div id="advanced-matching-data-sharing" />

##### **Compartilhamento de dados de correspondência avançada**

Ative essa opção para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, com o ChatGPT Ads, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

<div id="default-postbacks" />

#### Postbacks padrão

Um postback é uma notificação de servidor para servidor que a AppsFlyer envia ao ChatGPT Ads para informar um evento atribuído (como uma instalação ou uma ação dentro do aplicativo). Seus postbacks são exibidos nesta seção. Descubra como <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">configurar os postbacks de instalação e reatribuição</Anchor>.

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">configuração de postbacks padrão</Anchor>.

<div id="in-app-event-settings" />

#### Configurações de eventos in-app

Para enviar postbacks de eventos in-app ao ChatGPT Ads, insira as credenciais necessárias:

* Pixel ID
* chave de API

Para mais informações, consulte as [configurações gerais](#configurações-gerais).

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configure os postbacks de eventos in-app para enviar ao ChatGPT Ads. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Saiba mais</Anchor>

**Para ativar postbacks de eventos in-app:**

Ative a opção **Postbacks de eventos in-app**.

**Janela de postback de eventos in-app**

Defina o período após uma instalação, reatribuição ou reengajamento, durante o qual a AppsFlyer envia postbacks de eventos in-app ao ChatGPT Ads. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Saiba mais</Anchor>

**Mapeie seus eventos**

Para garantir que seus eventos correspondam aos eventos correspondentes no ChatGPT Ads, mapeie os nomes dos seus eventos. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">Saiba mais</Anchor>

O ChatGPT Ads aceita os seguintes eventos padrão, além de um fallback **personalizado** para qualquer evento não incluído abaixo:

| Nome do evento do ChatGPT Ads | Quando usar |
| --- | --- |
| página\_visualizada | O usuário acessa ou visualiza uma página importante. |
| conteúdo\_visualizado | O usuário visualiza um produto, lista, artigo ou conteúdo específico. |
| item\_adicionado | O usuário adiciona um ou mais itens ao carrinho, pacote ou seleção. |
| checkout\_started | O usuário inicia o checkout. |
| order\_created | Compra concluída. |
| registo\_concluído | O usuário conclui o cadastro de uma conta ou um evento. |
| lead\_created | O usuário envia um formulário de lead ou solicita contato. |
| appointment\_scheduled | O usuário agenda uma reunião, demonstração ou consultoria. |
| período\_de\_avaliação\_iniciado | Início do teste gratuito. |
| subscription\_created | Início da assinatura paga. |
| app\_opened | O usuário abre o app mobile. |
| personalizado | Qualquer evento não incluído na taxonomia padrão. |

**Desduplicação de eventos**

Se você também executar o pixel do ChatGPT Ads no seu site, envie o mesmo ID de evento para a AppsFlyer e o ChatGPT Ads para que a AppsFlyer possa eliminar duplicações entre os eventos:

* Inclua `af_customer_event_id` na carga útil do evento que você envia para a AppsFlyer, dentro de eventValue para o SDK web ou de event\_value para a API S2S (server-to-server).
* Envie o mesmo valor no evento de Pixel correspondente.

A AppsFlyer encaminha esse valor para o ChatGPT Ads como o ID do evento. O ChatGPT Ads então o usa para desduplicar o evento do lado do servidor que recebe da AppsFlyer em relação ao evento do Pixel, para que a AppsFlyer conte a conversão uma vez.

Se você não enviar `af_customer_event_id`, a AppsFlyer gera um ID de evento automaticamente. Esse ID não corresponderá aos seus eventos de Pixel.

Para mais informações, consulte Integrar o SDK web da AppsFlyer Web.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

O ChatGPT Ads (OpenAI) aceita links de atribuição.

<div id="choose-your-attribution-type" />

#### Escolha um tipo de atribuição

Decida se você quer:

1. Envie os usuários diretamente para a loja de aplicativos. Se sim, você precisará criar um link de atribuição de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor> como URL final, com base nas necessidades da sua campanha e nas configurações de segmentação.   

   OU
2. Use uma landing page como destino do seu anúncio e, em seguida, use <Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">Smart Script</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> para direcionar o usuário à App Store ou ao Google Play (enquanto cria um link que permitirá a atribuição).

<div id="select-parameters" />

#### Selecionar parâmetros

Selecione os parâmetros do link de atribuição que deseja incluir.

* Selecione os parâmetros do link de atribuição que você quer incluir (por exemplo, **Nome da campanha** e **ID do site**) e defina sua **janela de lookback de click-through** (7 dias é o padrão recomendado pela AppsFlyer). A AppsFlyer gera automaticamente seu link de atribuição para usar nas suas campanhas do ChatGPT Ads.
* Os seguintes parâmetros de URL podem ser preenchidos automaticamente pelo ChatGPT usando estas macros de URL dinâmicas:
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`
* As macros do campo de nome não estão disponíveis.

<div id="important" />

> 🚧 **Importante:**
>
> * Para que a AppsFlyer capture o ID de clique do ChatGPT Ads e o envie de volta ao ChatGPT Ads, use `clickid={oppref}` se seus anúncios levarem diretamente para a App Store ou o Google Play. Quando o destino do anúncio for uma landing page com Smart Script, certifique-se de capturar o parâmetro de entrada `oppref` e mapeá-lo para `clickid` na URL de saída.
> * O ChatGPT Ads só resolve macros (como `{campaign_id}`) quando os parâmetros correspondentes são colocados no campo **Parâmetros de rastreamento**, e não no campo **URL de destino do anúncio**. Cole seus parâmetros de consulta (por exemplo, `af_c_id={campaign_id}`) no campo **Parâmetros de rastreamento** e use o campo **URL de destino do anúncio** apenas para a própria URL de destino.

**Atenção:** O link gerado inclui `openai_int` (ID da integração do ChatGPT Ads na AppsFlyer).

Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">links de atribuição.</Anchor>

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Atualmente, não há integrações de Cost API para o ChatGPT Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba de receita de anúncios">

Os dados de receita de anúncios não podem ser extraídos do ChatGPT Ads. Use postbacks ou sinais de UA para compartilhar dados de receita de anúncios para otimização de campanhas.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Ative a opção **Permissões da ad network** para conceder à equipe do ChatGPT Ads acesso aos seus dados. Depois de ativá-la, selecione as permissões individuais que você deseja conceder, como configurar a integração, acessar relatórios de retenção e de cohort ou visualizar dados agregados de conversão e receita. Observe que, mesmo com a atribuição desativada para o ChatGPT Ads, você ainda pode conceder permissões.

Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões</Anchor>.

</Accordion>

<div id="integrate-your-website" />

## Integrar seu site

Siga as etapas abaixo para configurar o envio de eventos do lado do servidor ao ChatGPT Ads para seu site.

**Para integrar seu site:**

1. Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros** > **Marketplace**.
2. Selecione o seu aplicativo de site no menu suspenso.
3. Pesquise **ChatGPT Ads (OpenAI)** e clique em **Integrar**.
4. Complete a configuração na aba de integração, conforme descrito abaixo.

<div id="integration-tab::2739744d" />

<Accordion title="Aba de integração">

<div id="activate-partner-1" />

#### Ativar parceiro

**Para ativar a integração:**

Habilite o botão **Ativar parceiro**.

**Aviso importante:** Essa opção **deve permanecer habilitada** enquanto você trabalhar com o ChatGPT Ads. Ao desativar a integração, você também desativará o envio de eventos para seu site.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

<div id="in-app-event-settings-1" />

#### Configurações de eventos in-app

Para enviar postbacks de eventos ao ChatGPT Ads, insira as seguintes credenciais:

* **Pixel ID:** Um pixel é criado no seu ChatGPT Ads Manager. Você pode obtê-lo na aba de conversões na sua conta do Ads Manager.
* **API key:** Uma API key é necessária para autenticar chamadas da Events API. Você pode obtê-la na aba de conversões na sua conta do Ads Manager.

**Compartilhamento de dados de correspondência avançada:** Ative essa opção para compartilhar campos de correspondência avançada (como e-mail, número de telefone, nome e sobrenome com hashes) com o ChatGPT Ads, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

<div id="in-app-event-postbacks-1" />

#### Postbacks de eventos in-app

Configure os postbacks de eventos para enviar ao ChatGPT Ads. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Saiba mais</Anchor>

**Para ativar postbacks de eventos:**

Ative a opção **Postbacks de eventos in-app**.

**Mapeie seus eventos**

Para garantir que seus eventos correspondam aos eventos equivalentes no ChatGPT Ads, mapeie os nomes dos seus eventos. Consulte a tabela de eventos padrão anterior para ver os eventos compatíveis com o ChatGPT Ads. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">Saiba mais</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="Aba do link de atribuição">

O ChatGPT Ads (OpenAI) não usa links de atribuição externos para integrações de sites. O Web SDK da AppsFlyer mensura eventos da web e os envia diretamente para a Conversions API do ChatGPT Ads, portanto, não é necessário configurar a atribuição baseada em links.

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="Aba de custo">

Os dados de custo não estão disponíveis para integrações de sites com o ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="Aba de receita de anúncios">

Os dados de receita de anúncios não estão disponíveis para integrações de sites com o ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="Aba de permissões">

As permissões não estão disponíveis para integrações de sites com o ChatGPT Ads.

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Descrição |
| --- | --- |
| País | <Anchor target="_blank" href="https://help.openai.com/en/articles/20001245-ads-manager-availability">Lista de países</Anchor> onde o ChatGPT Ads Manager está disponível. |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Integrações de parceiros</Anchor>

<div data-zendesk-anchors="about-the-integration=sobre-a-integra%C3%A7%C3%A3o-com-o-chatgpt-ads h_01KWS8SS8RE2VQ275MFB7CT39J=sobre-a-integra%C3%A7%C3%A3o-com-o-chatgpt-ads set-up-the%20integration=configurar-a-integra%C3%A7%C3%A3o h_01H95QTA3Z5HXW39AHAF8FMFWH=configurar-a-integra%C3%A7%C3%A3o integrate-your-mobile-app=integrar-seu-aplicativo-mobile h_01KWVBQG0G85W6QJ8AT2520GTX=integrar-seu-aplicativo-mobile h_01KWVK5J7FBA81238JD4AD0219=integration-tab activate-partner=ativar-parceiro h_01H95QTA3ZGEM34HY1A7NC8NX7=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01KWVKHV36H34XCHYBFRHNF8TB=configura%C3%A7%C3%B5es-gerais h_01M39MMERMEBK470T0NDCVRN2E=agregada-da-appsflyer h_01M39MP266X5KME19RBVQZRDE6=compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada default-postbacks=postbacks-padr%C3%A3o h_01KWVKZJ7AZ8Z4CFM8J0PV071A=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01JTDP2T0BFP5WP03X5EMXVAWA=configura%C3%A7%C3%B5es-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app h_01KWVMZC74AQSN7BDQP2QQWBT4=postbacks-de-eventos-in-app h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=escolha-um-tipo-de-atribui%C3%A7%C3%A3o choose-your-attribution-type=escolha-um-tipo-de-atribui%C3%A7%C3%A3o h_01_select-parameters=selecionar-par%C3%A2metros select-parameters=selecionar-par%C3%A2metros h_01M254BFC0V68RJ6B903D8XKD3=importante h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab integrate-your-website=integrar-seu-site h_01KWVSJRYSQEH12C5RH7BN4CC2=integrar-seu-site h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=ativar-parceiro-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=ativar-parceiro-1 inapp-event-settings::a3adef08=configura%C3%A7%C3%B5es-de-eventos-in-app-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=configura%C3%A7%C3%B5es-de-eventos-in-app-1 inapp-event-postbacks::c3d06354=postbacks-de-eventos-in-app-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=postbacks-de-eventos-in-app-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KX3DAS0FBTKGKE7CZJTDTY2X=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KWVT1XJ2FKP1CACRV24C1R8E=veja-tamb%C3%A9m" />
