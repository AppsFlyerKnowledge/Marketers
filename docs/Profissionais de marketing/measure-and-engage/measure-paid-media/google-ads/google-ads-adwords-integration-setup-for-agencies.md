---
title: Integração do Google Ads para agências
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-09-16T00:27:42Z'
  id: 115003669983
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/115003669983
---
> **Visão geral:** configurando a integração do Google Ads com a AppsFlyer — como uma agência.

Tanto os anunciantes quanto as agências devem configurar ativamente o sistema. O vídeo abaixo mostra as etapas que devem ser feitas pelo anunciante e pela agência para permitir que a agência meça e atribua o tráfego mobile ao aplicativo do anunciante usando o Google Ads.

A configuração permite que a AppsFlyer atribua conversões a uma agência a partir do dashboard da AppsFlyer.

Antes que a Agência possa iniciar o processo, o anunciante deve primeiro configurar a integração do Google Ads. Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">aqui</Anchor>.

<div id="enabling-agency-attribution-of-google-ads" />

## Habilitar a atribuição de agência do Google Ads

A AppsFlyer oferece suporte para configurações de agência com o Google Ads. É essencial que o anunciante e a agência tenham contas separadas no Google Ads para permitir que a AppsFlyer atribua os dados corretamente.

<div id="setting-up-google-ads-attribution-for-agencies" />

## Configurar a atribuição do Google Ads para agências

Para iniciar a atribuição de campanhas do Google Ads pela agência com a AppsFlyer, siga estas etapas:

<Accordion title="Assistir">

<Embed title="Integração do Google Ads para agências" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Ler">

<div id="advertiser-prestep-enabling-the-agency-access-to-google-ads" />

<Accordion title="Pré-etapa do anunciante: permitir que a agência acesse o Google Ads">

**Pré-requisitos:**

* Na AppsFlyer, conceda à agência acesso ao aplicativo ,segundo as instruções indicadas <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">aqui</Anchor>.
* Na AppsFlyer, <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">ative</Anchor> o parceiro do Google Ads.

**Para compartilhar o ID do link do anunciante:**

1. No Google, acesse o Dashboard do Google Ads e clique no ícone ***Ferramentas***

![Google_Ag_1.png](https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png)

2. Selecione ***Contas vinculadas***.

![Google_Ag_2.png](https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png)

3. Em "Provedor de Análise de Aplicativos" (App Analytics Provider, encontre a AppsFlyer. Selecione Opções.

4. Clique em ***Compartilhar com outra conta***.

![Google_Ag_3.png](https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png)

5. Insira o **ID de cliente do Google Ads da agência**

![Google_Ag_4.png](https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png)

6. Clique em ***Avançar***. Clique em ***Enviar convite.***

![Google_Ag_5.png](https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png)

O anunciante agora pode ver que o pedido de convite foi enviado para a Agência. Quando a Agência aceita o convite, o status muda para "Compartilhado" (Sharing).

Para mais detalhes sobre como compartilhar o seu ID de Link do Google Ads, clique <Anchor target="_blank" href="https://support.google.com/adwords/answer/7365001">aqui</Anchor>.

![Google_Ag_6.png](https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png)

</Accordion>

<div id="agency-step-1-accepting-the-link-id" />

<Accordion title="Etapa 1 da agência: aceitar o ID do link">

No dashboard do Google AdWords, a Agência recebe um convite e deve aceitar o link.

![Google_Ag_7.png](https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png)

A Agência pode ver que o status do link agora está Ativo.

![Google_ag_8.png](https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png)

</Accordion>

<div id="agency-step-2-setting-up-google-ads-on-appsflyer" />

<Accordion title="Etapa 2 da agência: configurar o Google Ads na AppsFlyer">

Uma agência pode configurar vários IDs de cliente do Google Ads, se necessário.

1. **Na AppsFlyer, no menu lateral, selecione** **Colaboração** > Integrações de parceiros.
2. Pesquise e selecione **Google Ads**.

   ![gads-search.png](https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png)

   A opção ***Ativar parceiro*** deve estar LIGADA e o ***ID do link*** deve ser definido pelo anunciante. Essas configurações estão indisponíveis para a agência.

   ![gads_agency-integration-link-id.png](https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png)
3. A agência define seu ID de cliente do Google Ads.

   Insira **todos os** IDs de cliente do Google Ads (**subcontas**) das contas do Google Ads nas quais a agência está veiculando campanhas para o aplicativo do anunciante.

   Você pode encontrar o ID do cliente do Google Ads clicando na seta no canto superior esquerdo e abrindo o Painel de Navegação.

   [![](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)
4. Para medir as campanhas de retargeting em andamento no Google Ads, peça ao anunciante par ativar **Retargeting do Google Ads**. Depois disso, você poderá configurar a **Janela de Reengajamento**.

   ![gads-agency-retargeting.png](https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png)
5. Recomendamos definir a janela de lookback de atribuição de cliques para **30 dias**, para corresponder ao valor do Google Ads.

   ![gads-click-through.png](https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png)
6. A exibição recomendada é de **1 dia**, para corresponder ao valor do Google Ads. A escala permite que você personalize o número de horas/dias após a visualização de um anúncio, durante o qual a impressão pode ser atribuída a esse parceiro.

   ![gads-view-through.png](https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png)
7. ***Atribuição de reinstalação***:
   * Para habilitar a atribuição de reinstalação, ative-a.
   * Não é necessário ativar a atribuição de visualização ou configurar janelas de lookback para a atribuição de reinstalação, uma vez que os valores são obtidos a partir das configurações de atribuição de instalação.
8. Clique em ***Salvar & Fechar***.

</Accordion>

<div id="agency-step-3-mapping-your-inapp-events" />

<Accordion title="Etapa 3 da agência: mapeando seus eventos in-app">

1. Clique na aba **Eventos in-app**.

2. Selecione para enviar eventos in-app somente instalações do Google Ads ou para enviar todos os eventos in-app para o Google Ads.  
[![](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)

3. Mapeie todos os eventos in-app que você deseja enviar para o Google Ads com os eventos predefinidos do Google Ads.

[![](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)

4. Clique em ***Salvar***.

<div id="important" />

> 🚧 **Importante!**
>
> Importe as primeiras ações de abertura e ações in-app para o Google Ads para começar a contar as conversões no Google Ads e no seu dashboard da AppsFlyer.
>
> Para poder importar, você deve iniciar o aplicativo e realizar seus eventos in-app mapeados pelo menos uma vez.

<div id="note" />

> 📘 **Observação**
>
> * Pode levar até 6 horas até que as novas conversões mudem o status de "Nenhuma Conversão Recente" para "Registrando a Conversão".
> * Se uma agência trabalha com uma conta da MCC e o aplicativo é promovido por meio de várias subcontas da MCC, todas as subcontas deverão ser configuradas no campo **ID do cliente do Google Ads** (como visto na captura de tela acima).
>   Nesse caso, não há necessidade de configurar o ID do cliente da conta MCC.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Etapa 4 da agência: mensure as conversões do aplicativo (obrigatório)">

(**Google Ads** **somente administrador)**

<div id="important-1" />

> 🚧 **Importante!**
>
> Para que o Google Ads registre suas novas conversões, **você precisa iniciar o aplicativo e realizar seus eventos in-app mapeados** pelo menos uma vez. Para testar aplicativos iOS, você deve coletar o IDFA para ver o evento. Pode levar até 6 horas para que os eventos de conversão sejam adicionados à fila. Depois de adicionados, você pode importá-los e as novas conversões mudam de status de “Sem conversão recente” para “registrando conversão".

1. Volte para a página **Visão geral** na sua conta do Google Ads e vá para **FERRAMENTAS E CONFIGURAÇÕES** > **Mensuração** > **Conversões**.  
   [![conversions_overview_en-us__1_.png](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)
2. Clique **+ Nova ação de conversão**.   
   [![New_conversion_action_en-us__2_.png](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)
3. Selecione **App** na lista de tipos de conversão, depois selecione **Analytics de app de terceiros** e clique em **Continuar**.  
   [![select_app_en-us__3_.png](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)
4. Marque a caixa ao lado de **first\_open** em todos os seus aplicativos e para cada evento que você quiser importar.

   <div id="note-1" />

   > 📘 **Observação**
   >
   > Você precisa reimportar se o **identificador de Partner Event** no Google Ads for alterado ou se o nome do evento correspondente for CUSTOM, e o nome do evento correspondente for alterado na AppsFlyer.


   Clique em **Importar e continuar**, depois clique em **OK**.  
   [![select_events_to_import_en-us__4_.png](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)
5. Agora você pode ver seus eventos de conversão de terceiros no site na página **Conversões** > **Resumo**. Se um evento não aparecer na lista ou tiver sido removido da lista de conversões do Google Ads, clique em **Ver todas as ações de conversão**. O filtro **Status** aparece.   
   [![conversions_summary_en-us__5_.png](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)
6. Clique em **Status** e selecione Todos para visualizar todos os eventos, incluindo os desativados e removidos.  
   [![conversion_action_status__6_.png](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)
7. Parabéns! Agora você está mensurando campanhas mobile do Google Ads com a AppsFlyer!

<div id="note-2" />

> 📘 **Observação**
>
> Certifique-se de que sua configuração para "incluir em conversões" esteja alinhada com os seus objetivos de campanha no Google Ads. Para mais informações, consulte seu representante do Google ou a documentação do Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">aqui</Anchor>.

</Accordion>

</Accordion>

<Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#configuração-da-atribuição-do-google-ads-para-anunciantes">Clique aqui</Anchor> para assistir ao vídeo "Configurando a Atribuição do Google Ads para Anunciantes".

Para obter detalhes sobre como os anunciantes podem atribuir contas do Google Ads de várias agências/MCC, clique <Anchor target="_blank" href="/marketers/pt/docs/recording-multiple-agency-mcc-google-ads-accounts">aqui</Anchor>.

<div id="agencies-collecting-cost-clicks-and-impression-data" />

## Agências: coleta de dados de custo, cliques e impressão

As agências podem <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#cost-tab">recuperar dados de custo</Anchor> do Google Ads, que também incluem os dados de cliques e impressões.

Os dados de custo são exibidos em ambos os dashboards da agência e do anunciante, a nível de campanha.

Se a agência for transparente, no dashboard do anunciante os dados de custo serão exibidos nas campanhas do Google Ads. Caso contrário, os dados são exibidos nas campanhas da agência.

<div data-zendesk-anchors="enabling-agency-attribution-of-google-ads=habilitar-a-atribui%C3%A7%C3%A3o-de-ag%C3%AAncia-do-google-ads h_01HKA1J5ES5T65NT5QMY5ZGXP6=habilitar-a-atribui%C3%A7%C3%A3o-de-ag%C3%AAncia-do-google-ads setting-up-google-ads-attribution-for-agencies=configurar-a-atribui%C3%A7%C3%A3o-do-google-ads-para-ag%C3%AAncias h_01HKA1J5ESJYS902S9Z3YY5FV9=configurar-a-atribui%C3%A7%C3%A3o-do-google-ads-para-ag%C3%AAncias h_01HKA1J5ESF3ZK9E9PKM9AN8C8=advertiser-prestep-enabling-the-agency-access-to-google-ads h_01HKA1J5ETKV3H3KYBEYQZMSXA=agency-step-1-accepting-the-link-id h_01HKA1J5ET2BV8GHXZS5T8KCGZ=agency-step-2-setting-up-google-ads-on-appsflyer h_01HKA1J5ETH4TTVDSP0HNK6F0Q=agency-step-3-mapping-your-inapp-events h_01HKA1J5ETK5PXYFPXPBVH0HJQ=importante h_01HKA1J5ETNQ1FCBMVTQED74HG=observa%C3%A7%C3%A3o h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=importante-1 h_01HKA1J5ETNTFKKDF6NC635H3W=observa%C3%A7%C3%A3o-1 h_01HKA1J5ETEWJN8MH9NPWTWX0F=observa%C3%A7%C3%A3o-2 agencies-collecting-cost-clicks-and-impression-data=ag%C3%AAncias-coleta-de-dados-de-custo-cliques-e-impress%C3%A3o h_01HKA1J5ETPYE7B2NFPFHA05YT=ag%C3%AAncias-coleta-de-dados-de-custo-cliques-e-impress%C3%A3o" />
