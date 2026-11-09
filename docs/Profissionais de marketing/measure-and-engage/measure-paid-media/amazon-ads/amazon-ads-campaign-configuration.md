---
title: Configuração de campanhas na Amazon Ads
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-09-10T12:27:00Z'
  id: 11904659502737
  locale: pt
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/pt/articles/11904659502737
---
> **Resumo:** Com a Amazon Ads (amazondsp\_int), uma parceira de <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRN</Anchor> integrada da AppsFlyer, os proprietários de aplicativos conseguem mensurar cliques e atribuição baseada em visualizações com a AppsFlyer para TV, tablet e mobile.

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" />

<div id="activate-partner" />

## Ativar parceiro

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   Para editar: vá para **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="complete-the-setup-in-amazon-ads" />

## Concluir a configuração na Amazon Ads

Complete as etapas abaixo na Amazon Ads:

1. Verifique se o seu aplicativo está cadastrado na Amazon Ads. Leia a seção <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">Register apps</Anchor> na documentação da Amazon Ads.
2. Ao criar campanhas na Amazon Ads, certifique-se de associar as conversões relevantes à campanha. Leia a seção <Anchor target="_blank" href="https://advertising.amazon.com/help/GMQBB4PRFK8C33AE">Assign a conversion definition to a campaign</Anchor> na documentação da Amazon Ads.

<div id="setting-up-amazon-ads" />

## Configurar Amazon Ads

A integração com Amazon Ads permite atribuição de cliques e impressões. A janela de configuração inclui os seguintes separadores: Integração, Link de Atribuição, Custo, Receita de Anúncio e Permissões. Para Amazon Ads estão disponíveis os separadores Integração e Permissões.

<div id="note" />

> 📘 **Observação**
>
> Esta integração é aceita em aplicativos Android, iOS ou Fire. O iOS também é compatível via SKAN.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

<div id="activate-partner-1" />

#### Ativar parceiro

Para configurar a integração, primeiro deve [ligar](/docs/amazon-ads-campaign-configuration#ativar-parceiro) o botão de alternância **Ativar parceiro**. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativar e desativar integrações de parceiros</Anchor>.

<div id="general-settings" />

#### Configurações Gerais

**ID do Anunciante Amazon**

Esta é uma chave única da Amazon para o anunciante, gerada pela própria Amazon. O ID do Anunciante da Amazon é necessário para concluir a integração e permitir a atribuição ao Amazon Ads. Para localizar o ID do Anunciante da Amazon:

* **Para anunciantes de autoatendimento:** O seu ID de anunciante encontra-se na consola de relatórios do Amazon Ads, sob o nome do anunciante, no separador "Anunciantes" do "Amazon DSP Campaign Manager".
* **Para anunciantes de serviços geridos:** Solicite ao seu gestor de contas da Amazon o seu ID de anunciante.
* Se você usar várias contas da Amazon Ads para o mesmo aplicativo (e, consequentemente, tiver vários IDs de anunciante), configure a integração da seguinte forma:
  1. Na Amazon Ads, selecione uma conta de anúncios e nomeie como **conta de origem**. Nomeie todas as outras contas de anúncios como **contas de destino**.
  2. Entre em contato com a equipe de contas da Amazon para configurá-la no backend da plataforma.
  3. Na AppsFlyer, insira o ID de anunciante da Amazon associado à conta de origem. Isso aplicará a configuração da integração a todas as contas de destino relacionadas.

**ID do aplicativo da Amazon**

* **Para aplicações Android:** O nome do pacote. Por exemplo: `com.example.app`
* **Para aplicações Fire TV ou Fire tablet:** O ASIN do produto (Número Padrão de Artigo da Amazon)
* **Para aplicativos iOS:** O ID do aplicativo na loja sem a parte "`id`" (exemplo:`12345678`).
* **Para** <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#dashboard-único-vs-dashboard-por-loja">**aplicações de dashboard único**</Anchor> (dashboards que combinam dados do Google Play e da loja Amazon para a mesma aplicação Appsflyer): Insira o nome do pacote Android como ID do pacote.  
  **Nota: <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">Certifique-se de que a aplicação está</Anchor> <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">registada</Anchor> como uma aplicação Android na conta Amazon Ads.**

<div id="install-attribution" />

#### Atribuição de instalação

Configure as janelas de atribuição para cliques e visualizações para instalações (primeiros lançamentos). Note que apenas as instalações dentro da janela de retrospetiva são atribuídas ao Amazon Ads.

**Nota:** A atribuição para reinstalações (qualquer instalação que não seja a configuração inicial no dispositivo) não é suportada.

1. Configure a **janela de retrospetiva de cliques para instalação** entre 1-24 horas ou 1-14 dias.  
   **Nota:** A Amazon Ads recomenda ajustar a janela de retrospetiva de cliques para 14 dias, para alinhar à sua janela de atribuição e evitar discrepâncias.
2. [Opcional] Ative a **atribuição de visualização para instalação** e defina a **janela de retrospetiva de visualização** para 1-24 horas.   
   **Nota:** A Amazon Ads recomenda configurar a janela de retrospetiva de visualização para 14 dias, para se alinhar à sua janela de atribuição e evitar discrepâncias.

<div id="re-engagement-attribution" />

#### Atribuição de reengajamento

Ative a função **Atribuição de reengajamento** e configure as diferentes janelas de atribuição para reengajamentos dos usuários que visualizaram, clicaram ***ou interagiram*** com seu anúncio. Observe que apenas reengajamentos dentro da janela de lookback podem ser atribuídos à Amazon Ads.

1. [Opcional] Ative a **Atribuição de reengajamento** e configure a janela de retrospetiva:
   * Defina a **janela de retrospetiva de cliques para reengajamento** entre 1-23 horas ou 1-14 dias.
2. [Opcional] Ative a **atribuição de visualização para reengajamento** e defina as janelas de retrospetiva:
   * Defina a **janela de lookback de visualização de reengajamento** para 1-23 horas ou 1-14 dias.
3. Defina a **janela de reengajamento** para 1-23 horas, 1-90 dias ou**vitalícia**.

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuários ativos para redirecionamento

Defina um período de tempo para <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window#período-de-inatividade">ignorar reengajamentos e reatribuições</Anchor> de usuários que inicializaram o seu aplicativo. Isto significa que a sua atividade durante o período da janela não é registada na AppsFlyer.

<div id="note-1" />

> 📘 **Observação**
>
> **São registradas** as conversões de reengajamento e reatribuição de usuários que estavam **inativos** no período de tempo definido.

1. Ative a opção **Ignorar utilizadores ativos para retargeting**.
2. Defina a **janela de inatividade** entre 1 e 30 dias.  
   **Nota:** A Amazon Ads recomenda ajustar a janela de inatividade para 7 dias para alinhar com as suas diretrizes e evitar discrepâncias.

<div id="in-app-event-postbacks" />

#### Envios de eventos na aplicação

Configure o mapeamento dos eventos na aplicação com eventos da Amazon Ads, enviados através de postbacks.

**Para configurar os postbacks de eventos na aplicação:**

1. Ative os **postbacks de eventos na aplicação**.
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **Criar evento personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados.</Anchor></li></ul> |
| **mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. Na lista de eventos de parceiros predefinidos, selecione o evento que corresponde ao evento do seu aplicativo (o evento da AppsFlyer).<br /><br />**Observações:**<ul><li>Você pode selecionar OUTRO para eventos que não correspondem diretamente ao evento do seu aplicativo.</li><li>Quando a mensuração de reengajamento estiver ativada, recomendamos não mapear o evento `af_app_opened` ou mapeá-lo apenas para `OTHER`. Isso evitará possíveis duplicações ao enviar o evento.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro**: Envie postbacks apenas quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de media, incluindo as orgânicas**: Envie postbacks para eventos atribuídos a qualquer parceiro, bem como eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Sem dados (padrão)**: Envie apenas o evento em si, sem qualquer valor de evento.</li><li>**Valores e receitas**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: Envie todos os parâmetros, **exceto** o valor da receita.</li></ul> |

   <div id="note-2" />

   > 📘 **Nota**
   >
   > Se você enviar seu evento in-app para a AppsFlyer via S2S, a Amazon recomenda incluir o endereço IP. Isso permite que a AppsFlyer envie o código do país, onde o evento está localizado, para a Amazon, ajudando na classificação das regras do DMA. Isso garante a máxima otimização dos seus eventos in-app.

3. [Opcional] Clique no ícone **Adicionar condiçãoaltconditional-iae-postbacks-icon.pngalt para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.**
4. Clique em **Guardar integração**.
5. [Opcional] Após guardar a integração, permanecendo na página de configuração, pode integrar mais das suas aplicações com o parceiro:
   1. No canto superior esquerdo, sob o nome do parceiro, clique no nome da aplicação para abrir a lista de aplicações.
   2. Selecione uma aplicação diferente na lista suspensa.
   3. Repita os [passos de integração](#integration-tab) para a aplicação selecionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não são relevantes para Amazon Ads. A atribuição é realizada através da combinação de dados de interação dos Amazon Ads com dados da AppsFlyer, utilizando as janelas de retargeting configuradas no [separador Integração](#integration-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Separador de Custos, Cliques e Impressões">

Os dados de custos, cliques e impressões não estão disponíveis para Amazon Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não está disponível para Amazon Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Selecione as permissões a conceder à Amazon Ads para que possa aceder aos seus dados e realizar várias ações.

<div id="note-3" />

> 📘 **Observação**
>
> * Quando a integração é <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">desativada</Anchor>, mas o botão de permissões ainda está ativado, as permissões permanecem concedidas.
> * Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">conceder permissões</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/setting-up-amazon-fire-tv-ad-attribution">Configurando a atribuição de anúncios na Amazon Fire TV</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/attribution-discrepancies-between-amazon-ads-and-appsflyer">Discrepâncias de atribuição entre a AppsFlyer e Amazon Ads</Anchor>

<div id="deferred-deep-linking" />

## Deep linking diferido

* Os deep links não são aceitos na Amazon Ads.
* Deferred deep links: ambos os métodos da AppsFlyer para deferred deep links não são aceitos na Amazon Ads:
  * O [UDL](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) (deep link unificado) não é compatível com SRNs
  * A [GCD](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking) (obtenção de dados de conversão) não funcionará na Amazon Ads porque os dados de atribuição são [restritos](/docs/amazon-ads-campaign-configuration#restrições-de-dados-brutos).

<div id="raw-data-restrictions" />

## Restrições de dados brutos

Os dados brutos dos Amazon Ads são <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">restritos na plataforma AppsFlyer</Anchor>. Assim, o canal de mídia é indicado como “restrito” e os detalhes da campanha estão nulos. Cliques e impressões da Amazon Ads não são incluídos nos relatórios de dados brutos.

<div id="ctv-to-mobile-attribution" />

## Atribuição CTV-to-mobile

A Amazon pode atribuir instalações de aplicativos mobile a campanhas de CTV (TV conectada), como aquelas no Prime Video. Isso ocorre quando um usuário que visualiza o anúncio de CTV está logado em um aplicativo da Amazon no mobile.

**Nota:** **não há indicador de relatório** que mostre explicitamente a campanha como CTV. Para melhorar a visibilidade e a mensuração, recomendamos incluir `CTV` no nome da campanha quando aplicável.

<div id="support-amazon-eu-consent-policy" />

## Suporte à política de consentimento da Amazon na UE

A Amazon Ads está atualizando sua política de consentimento na UE em preparação para o <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Digital Markets Act (DMA)</Anchor>. Como uma parceira de atribuição de aplicativos da Amazon, a AppsFlyer está fazendo as mudanças necessárias para se adaptar à nova política e garantir que anunciantes tirem o máximo proveito dos seus anúncios na Amazon. A política atualizada passa a valer em 30 de junho de 2026.

<div id="note-4" />

> 📘 **Atenção**
>
> A atualização da política de consentimento na UE se aplica somente a dados (instalações, reengajamentos e eventos in-app) de usuários na UE, no Reino Unido ou na Suíça (CH).

Para garantir compliance, envie as informações de consentimento do DMA à AppsFlyer através do mesmo método usado para o <Anchor target="_blank" href="/marketers/pt/docs/support-google-eu-consent-policy">consentimento do DMA do Google</Anchor>.

<div id="dma-consent-methods" />

### Métodos de consentimento do DMA

Atualmente, a AppsFlyer disponibiliza dois métodos de compartilhamento do consentimento do DMA:

| Método | Detalhes |
| --- | --- |
| **Manual** | O único campo exigido pela Amazon é `ad_user_data_enabled`. |
| <Anchor target="_blank" href="https://iabeurope.eu/transparency-consent-framework/">**TCF**</Anchor> **(Estrutura de Transparência e Consentimento)** | Se você usar uma Consent Management Platform (CMP), certifique-se de que o Vendor ID da Amazon Ads (**793**) esteja na lista de permissão para fornecedores. |

<div id="note-5" />

> 📘 **Atenção**
>
> A Amazon também disponibiliza sinais de consentimento através da <Anchor target="_blank" href="https://iabtechlab.com/gpp/">Global Privacy Platform (GPP)</Anchor>, mas a AppsFlyer ainda não é compatível com esse método.

<div id="see-also-1" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">Envie o consentimento do DMA via SDK da AppsFlyer</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-overview">Envie o consentimento do DMA via S2S da AppsFlyer</Anchor> (pesquise por `consent_data`)

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Agências | A integração da Amazon Ads ainda não está disponível para agências. Por esse motivo, ela pode ser gerenciada apenas pela conta do anunciante. |
| Impressões, cliques e custos | Os dados de impressões, cliques e custos ainda não estão disponíveis para a integração. |
| Deep links | [Deep links não são aceitos na integração](#deep-linking-diferido). |
| Reinstalações e reatribuições | Reinstalações e reatribuições não são aceitos na integração. |
| Atribuição de preload | A mensuração de preload não faz parte dessa integração, mas pode ser obtida através da integração legada amazon\_int. |
| Limitação de postbacks | No Android, quando o campo `advertiserIdEnabled` é definido como "false", a instalação ou o reengajamento não serão enviados para a Amazon mesmo se o Advertiser ID estiver disponível. |

<div data-zendesk-anchors="activate-partner=ativar-parceiro 01H88VAJH3B5ESK12D3ATMMVZ8=ativar-parceiro complete-the-setup-in-amazon-ads=concluir-a-configura%C3%A7%C3%A3o-na-amazon-ads h_01KMG57HR62CC9TX495SG3WSRD=concluir-a-configura%C3%A7%C3%A3o-na-amazon-ads setting-up-amazon-dsp-integration=configurar-amazon-ads 01H88VAJH3VENKYVRQY5RXN63P=configurar-amazon-ads 01H88VAJH3BYZSXQGGZZJQ9N0C=observa%C3%A7%C3%A3o 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=ativar-parceiro-1 01H88VAJH34GP7FK1KTJGRDPM7=ativar-parceiro-1 general-settings=configura%C3%A7%C3%B5es-gerais 01H88VAJH3F2FJK5YP3M2V7RWD=configura%C3%A7%C3%B5es-gerais install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o 01H88VAJH3SSG6ZNV7XQ46W5CX=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o reengagement-attribution=atribui%C3%A7%C3%A3o-de-reengajamento h_01J4RC3GR8B04RNFSD61QK45C0=atribui%C3%A7%C3%A3o-de-reengajamento ignore-active-users-for-retargeting=ignorar-usu%C3%A1rios-ativos-para-redirecionamento h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usu%C3%A1rios-ativos-para-redirecionamento h_01HMXNJVHK9C3FT8E04RE0TH99=observa%C3%A7%C3%A3o-1 inapp-event-postbacks=envios-de-eventos-na-aplica%C3%A7%C3%A3o 01H88VAJH3AS37MVF75GANWX4B=envios-de-eventos-na-aplica%C3%A7%C3%A3o 01JEXXHXMEC5M7N1BDSGS3ZZ51=nota 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=observa%C3%A7%C3%A3o-2 h_01HDNZ59NQEDFC3D8JYGENR1NR=consulte-tamb%C3%A9m deferred-deep-linking=deep-linking-diferido 01J9G5FQGB0219RGWVW06BQPG7=deep-linking-diferido raw-data-restrictions=restri%C3%A7%C3%B5es-de-dados-brutos 01JBY7HD39BA9ZNR2N2TYYPBW3=restri%C3%A7%C3%B5es-de-dados-brutos ctvtomobile-attribution=atribui%C3%A7%C3%A3o-ctv-to-mobile h_01JZG6S5TB1888XG9560MKEBF3=atribui%C3%A7%C3%A3o-ctv-to-mobile support-amazon-eu-consent-policy=suporte-%C3%A0-pol%C3%ADtica-de-consentimento-da-amazon-na-ue h_01KP0DJ73P9FRX51SR3RS4YWVP=suporte-%C3%A0-pol%C3%ADtica-de-consentimento-da-amazon-na-ue h_01KP0DJ73PDB7FM1RG0VV99707=aten%C3%A7%C3%A3o dma-consent-methods=m%C3%A9todos-de-consentimento-do-dma h_01KP0DJ73PG0JMWG3WAWCKXE1S=m%C3%A9todos-de-consentimento-do-dma h_01KP0DJ73PNPYT0TRWF089VE9R=aten%C3%A7%C3%A3o-1 h_01KP0DJ73PC4ABGRPRDAR7BW5B=consulte-tamb%C3%A9m-1 traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
