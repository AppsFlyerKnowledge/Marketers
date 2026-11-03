---
title: Google Ads (AdWords)—perguntas frequentes e discrepâncias
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-08-18T00:29:46Z'
  id: 4417303339921
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/4417303339921
---
> **Resumo:** solucione problemas comuns e discrepâncias relacionados ao Google Ads.

## Perguntas frequentes sobre o Google Ads

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Por que eu não estou vendo cliques do Google Ads?">

Dados agregados de cliques e impressões do Google Ads são coletados assim que você <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">autentica a coleta de impressões, cliques e custo</Anchor> na aba **Custo**.

Os dados de cliques e impressões do Google Ads foram disponibilizados em agosto de 2018, primeiro para aplicativos Android e posteriormente para aplicativos iOS. Portanto, ao analisar dados de cliques de 2018 e anteriormente, os dados de cliques do Google Ads podem estar ausentes ou incompletos.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Por que não estou vendo conversões first_open no Google Ads?">

Se você não está vendo as conversões first\_open no Google Ads como na captura de tela abaixo:

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

Isso significa que você deve importar as conversões no Google Ads. Siga as instruções em <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Como importar conversões</Anchor>.

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="Por que não vejo eventos in-app no Google Ads?">

Siga esta lista de verificação para solucionar problemas de instalações ausentes:

#### Solução rápida

1. **Ative o Google Ads no AppsFlyer**  
   No AppsFlyer, na barra lateral, abra **Collaborate > Active integrations**, pesquise por **Google Ads** e confirme se a integração está ativa.
2. **Importe a conversão** `first_open` **no Google Ads**  
   No Google Ads, acesse a página <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Resumo de conversões</Anchor> e verifique se o evento de conversão `first_open` foi importado. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Importe suas conversões do aplicativo</Anchor>.

#### Ainda não funcionou?

1. **Verifique qual conta do Google Ads importa as conversões**  
   Determine se a **conta MCC ou subconta do Google Ads** é responsável por importar as conversões:

   * **Se estiver usando uma MCC (conta de administrador):** a MCC deve importar a conversão `first_open` em nome de todas as subcontas vinculadas.
   * **Se estiver usando uma subconta:**
     * A MCC deve **compartilhar o ID do link** com a subconta.
     * A subconta também deve **importar a conversão** `first_open` **diretamente**.

   Para mais informações sobre contas MCC do Google Ads, consulte: <Anchor target="_blank" href="/marketers/pt/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>.
2. **Verifique se as conversões** `first_open` **foram removidas**  
   Na página <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Resumo de conversões</Anchor>, verifique se o evento de conversão `first_open` foi removido. Se foi removido, entre em contato com o **suporte do Google** para obter ajuda.
3. **Confirme o ID do link**  
   Verifique se o ID do link no AppsFlyer corresponde ao ID do link no Google Ads.

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="Você está vendo esta tela no Google Ads após o mapeamento de seus eventos in-app no dashboard da AppsFlyer ( etapa 3 da configuração )?">

Use esta lista de verificação para garantir que seus eventos in-app estejam configurados corretamente e sincronizados entre o AppsFlyer e o Google Ads.

#### Lista de soluções rápidas

Siga estas etapas para resolver rapidamente os problemas mais comuns:

1. **Verifique os postbacks de eventos no AppsFlyer** (para instruções passo a passo, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">Configure o Google Ads no AppsFlyer.</Anchor>)
   1. Acesse a **guia de integração do Google Ads** no AppsFlyer.
   2. Verifique se os postbacks estão configurados corretamente para cada evento in-app que você quer mensurar.
   3. Em **For users from**, selecione *All media sources, including organic,* para garantir que o Google Ads receba os dados dos eventos.
   4. (Opcional) Após a configuração inicial, ajuste essa seleção para eventos específicos, se necessário.
2. **Acione um evento in-app de teste**
   1. Inicie seu aplicativo.
   2. Para aplicativos iOS, verifique se a coleta do IDFA está ativada, permitindo que o aplicativo rastreie.
   3. Realize manualmente os eventos in-app mapeados (por exemplo, compra ou inscrição).
3. **Importar eventos no Google Ads**
   1. No Google Ads, clique em **Ferramentas e conversões**.
   2. Verifique o **Resumo da ação de conversão**.
   3. Importe os eventos in-app relevantes. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Importar as conversões do seu aplicativo</Anchor>.

      > 📘 **Nota**
      >
      > As conversões podem levar até 6 horas para aparecer após a realização do evento.


#### Ainda não funcionou?

Se você modificou o identificador do evento do parceiro no Google Ads (por exemplo, se ele estiver rotulado como `CUSTOM`) e alterou o nome do evento correspondente no AppsFlyer, será necessário reimportar os eventos para o Google Ads.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Posso interromper a sincronização de custos do Google?">

Para interromper a sincronização de custos com o Google siga estes passos:

1. Vá para as <Anchor target="_blank" href="https://myaccount.google.com/permissions">permissões de conta no Google</Anchor>.
2. Clique em Remover ao lado de AppsFlyer Google Cost.  
   ![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="Eu preciso criar e importar session_start?">

Isso depende do tipo de campanha que você está executando. Se você estiver executando uma campanha de reengajamento, recomendamos que você crie e importe `session_start` para mensurar engajamentos.

Isso não é obrigatório para campanhas de aquisição de usuários.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Posso enviar informações de desinstalação para o Google Ads?">

Sim.  
**Para começar a enviar eventos de desinstalação para o Google:**

1. Mapeie o evento af\_uninstall como um evento personalizado na janela de configuração do Google Ads.
2. Importe essa conversão no Google.
3. O Google reconhece eventos se recebidos na janela de atribuição do Google (iniciada com o engajamento do anúncio e com duração de 30 a 90 dias). Os eventos recebidos pelo Google após o término da janela não são registrados no Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="Quais dados do Google Ads a AppsFlyer exibe?">

Você pode visualizar dados nos seguintes níveis: campanha, canal, adset e geo.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="Eu preciso configurar alguma coisa para criar listas de audiências no Google Ads com base nos dados da AppsFlyer?">

Não. Essa informação já está configurada na API do Google e baseia-se na sua configuração de eventos in-app.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="Estou executando uma campanha de aplicativo, por que não consigo ver dados ou eventos de conversão na AppsFlyer ou no dashboard do Google Ads?">

É muito provável que você ainda não tenha importado eventos. Para obter detalhes sobre como importar eventos, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aqui</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="O que faço se houver várias contas?">

Não há problema algum em usar várias contas do Google Ads com a AppsFlyer. A AppsFlyer funciona com um único Link ID. Portanto, deve ser gerado apenas um Link ID no Google Ads, que pode ser compartilhado entre várias contas. Para mais informações, clique <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">aqui</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="O que acontece com os Link IDs criados em nível de MCC Vs. Nível de Conta">

Link IDs no nível de MCC ou de conta são compatíveis com a AppsFlyer. Recomendamos trabalhar em conjunto com seu representante do Google Ads para garantir que a sua conta seja estruturada corretamente. Para mais informações, clique <Anchor target="_blank" href="/marketers/pt/docs/recording-multiple-agency-mcc-google-ads-accounts">aqui</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="O que é rastreamento paralelo?">

O rastreamento paralelo do Google Ads permite que sua landing page seja carregada mais rapidamente, reduzindo o problema de visitas perdidas. Como consequência, as conversões aumentam e a performance do anúncio melhora. Com o rastreamento paralelo, os usuários são enviados para a URL final, diretamente do seu anúncio, antes de enviá-los para os links de atribuição, enquanto a mensuração de cliques ocorre em segundo plano.

Para uma explicação completa sobre o rastreamento paralelo, clique <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">aqui</Anchor>.

#### O que é necessário?

Para que o rastreamento paralelo funcione como pretendido, a URL final deve corresponder à que está na URL da campanha e ser colocada no <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">parâmetro ValueTrack do Google.</Anchor>

Isso é feito ao:

* Usar um link de atribuição de uma única plataforma (não recomendado)
  * O parâmetro af\_r deve ser usado na URL
* Usar um <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">link longo do OneLink</Anchor> (recomendado)
  * Tendo os seguintes parâmetros de URL incluídos na URL da campanha
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * af\_dp não deve ser usado
  * Adicione sua URL final (URL de destino) ao parâmetro ValueTrack do Google. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">Saiba mais</Anchor>

Por exemplo,

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}  
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Observação: para ver todos os parâmetros compatíveis, consulte este [artigo](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter).

Clique aqui para ver como configurar campanhas de anúncios do Google na web com rastreamento paralelo.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="Como configurar uma campanha com configuração Android ou iOS">

> 🚧 **Importante!**
>
> A AppsFlyer é compatível com todas as campanhas de aplicativo habilitadas pelo Google Ads.
>
> O Google é uma SRN (Self Reporting Network). Para obter mais informações sobre como o fluxo de atribuição funciona para essas redes, clique <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">aqui</Anchor>.
>
> A AppsFlyer pode apresentar qualquer informação de campanha fornecida pelo Google. O tipo de campanha (busca, vídeo, exibição e reengajamento) e as informações associadas são determinados pelo Google. Recomendamos que você configure campanhas de aplicativos. Para mais informações sobre outros tipos de campanha, você deve entrar em contato com o seu representante do Google. Para mais detalhes sobre essas campanhas, clique <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">aqui</Anchor>.

<div id="android-configuration-for-google-ads" />

<Accordion title="Configuração do Android para o Google Ads">

Para oferecer suporte à atribuição do Android, certifique-se de que seu aplicativo seja compatível com a coleta GAID (ID de publicidade do Google) e que ela seja enviada para a AppsFlyer por meio do nosso SDK.

#### Criar registros de conversões (instalações)

Para mais detalhes sobre como criar registros de conversões, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">aqui</Anchor>.

<span id="inapp_events"></span>Google Ads - Configuração do Android - Envio de eventos in-app

Se você quiser mensurar ainda mais o sucesso das suas campanhas de instalação de aplicativos no Google, você pode enviar eventos in-app para sua conta do Google Ads a partir de sua conta da AppsFlyer.

#### Criar uma conversão (eventos in-app)

Para mais detalhes sobre como mensurar suas conversões no aplicativo, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aqui</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Configuração do iOS para o Google Ads">

#### Google Ads - Configuração de iOS: campanhas de aplicativos

Campanhas de aplicativos permitem promover seu aplicativo iOS no Google Search, YouTube e Display em um único local de configuração.

Geralmente, o próprio Google não consegue acompanhar as instalações no iOS a partir de campanhas de pesquisa, pois os cliques vêm de fontes da web móveis, impedindo que o Google obtenha o IDFA dos dispositivos e a realização de correspondência de ID.

Em contrapartida, a **busca do iOS** **em** Campanhas de aplicativos pode ser atribuída pelo Google Ads, para anúncios que são apresentados no aplicativo Google Search.

#### Criar registros de conversões (instalações)

Para mais detalhes sobre como criar registros de conversões, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">aqui</Anchor>.

#### Google Ads - Configuração do iOS - como enviar eventos in-app

Se você quiser mensurar ainda mais o sucesso das suas campanhas de instalação de aplicativos no Google, você pode enviar eventos in-app para sua conta do Google Ads a partir de sua conta da AppsFlyer.

#### Criar uma conversão (eventos in-app)

Para mais detalhes sobre como mensurar suas conversões no aplicativo, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aqui</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Por quanto tempo a AppsFlyer guarda os dados no nível dos usuários do Google Ads?">

O Google Ads exige que os provedores de atribuição excluam seus dados no nível do usuário seis meses após a instalação. Isso significa que os eventos realizados por esses usuários seis meses após a instalação do aplicativo são contados como orgânicos.

Os dados agregados permanecem os mesmos.

Isso se aplica a todos os canais do Google Ads.

</Accordion>

## Discrepâncias do Google Ads

Às vezes existem discrepâncias entre o dashboard do Google Ads e o dashboard da AppsFlyer.

Embora estejamos trabalhando em conjunto com o Google para minimizar essas discrepâncias, os anunciantes devem estar cientes dos seguintes motivos:

#### iOS e Android

| **Causa** | **Google Ads** | **A AppsFlyer** |
| --- | --- | --- |
| **Conversões modeladas e conversões de ICM** | O Google Ads mostra instalações modeladas geradas pela modelagem interna do Google e não mostra instalações modeladas com base em ICM. | O AppsFlyer mostra instalações modeladas geradas pelo Google ICM (declarações probabilísticas) e não mostra instalações modeladas internamente pelo Google. |
| **Instalações assistidas (também conhecida como atribuição Multi-touch)** | O Google Ads, como uma SRN, atribui todas as instalações pós-engajamento com o Google Ads, dentro da sua janela de atribuição. | A AppsFlyer atribui o último clique na jornada do usuário e trata os engajamentos anteriores como <Anchor target="_blank" href="/marketers/pt/docs/measure-assisted-installs">assistências</Anchor>. |
| **Hora da instalação** | O Google Ads  atribui a conversão ao horário do clique. | A AppsFlyer atribui a conversão ao horário de abertura do app (app open). |
| **Fusos horários** | Varia - baseado na localização | Varia - baseado na localização |
| **Janela de atribuição** | 30 dias | A integração do Google é definida como 30 dias por padrão (pode ser modificada). |
| **Conversões de view-through** | As conversões VT são exibidas somente na coluna **Todas as conversões** e não na coluna **Conversões** , a menos que definido de outra forma no Google Ads. | A AppsFlyer mostra o número total de instalações, instalações de clique e instalações VT. |
| **Reinstalações** | O Google Ads mostra reinstalações como uma conversão session\_start. | A AppsFlyer atribui e exibe as reinstalações (ou seja, as reatribuições) como parte dos dados de retargeting. |
| **Eventos in-app** | O Google Ads atribui o evento in-app ao horário do clique. | No dashboard da AppsFlyer, eventos in-app são atribuídos de acordo com o horário da instalação. Nos relatórios de dados brutos, a AppsFlyer atribui eventos in-app de acordo com o horário do evento. |
| **Regras de validação** | O Google recebe todas as informações da AppsFlyer, independentemente das regras de validação. | A AppsFlyer pode deduzir uma série de instalações com base em suas regras de validação. |
| **Custo - canais de campanha do Google Ads** | Relatórios de custo do Google para todos os canais de uma determinada campanha - YouTube, display e busca. | A AppsFlyer obtém dados de custo do Google para todos os canais de uma campanha, mas atribui somente conversões do YouTube e exibe canais na campanha de aplicativo no iOS. Como consequência, o CPI geral na AppsFlyer é maior. |
| **Instalações SKAN** | A partir da Google Ads API V10+, o dashboard do Google Ads não diferencia entre instalações com did\_win=TRUE e did\_win=NULL. A diferenciação se dá apenas nos dados brutos. | A partir da Google Ads API V10+, a AppsFlyer exibe apenas instalações de postbacks com did\_win=TRUE. Como resultado, o número de instalações na AppsFlyer pode ser menor. |
| **Eventos first\_open** | O Google Ads obtém eventos do Firebase onde o DMA é implementado corretamente e, posteriormente, são reivindicados eventos consentidos pelo DMA. | O Google Ads também obtém os mesmos eventos da AppsFlyer em que o DMA é implementado incorretamente, fazendo com que todos os eventos sejam relatados como não consentidos pelo DMA, sem reivincidação do Google.<ul><li>Para verificar se o DMA foi implementado corretamente, faça o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page#download-report">download do relatório de dados brutos</Anchor>  e foque nos campos especificados <Anchor target="_blank" href="/marketers/pt/docs/bulletin-dma-support-in-raw-data-reports">neste boletim</Anchor>.</li><li>Consulte [o Dev Hub](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance) para saber como implementar o DMA no SDK</li></ul> |
| **Eventos de retargeting** | O Google Ads pode reivindicar um reengajamento com `ad_type=ClickToDownload` na resposta. | A AppsFlyer conta o `ad_type=ClickToDownload` como um evento de conversão de UA em vez de um reengajamento. Como resultado, o número de reengajamentos na AppsFlyer pode ser menor. |

> 📘 **Observações**
>
> * Enquanto o Google Ads mostra todas as instalações de uma campanha de retargeting no mesmo lugar, no dashboard de visão geral da AppsFlyer, a visualização de UA exibe novas instalações, a visualização de retargeting exibe reatribuições e a visualização unificada exibe ambas.
> * Ao comparar dados do dashboard do Google Ads e da AppsFlyer, certifique-se de que os dados no dashboard do Google Ads sejam dados importados de terceiros (AppsFlyer). Dados importados do Firebase ou do Google Play são estruturados de forma diferente e não são inteiramente comparáveis com os dados da AppsFlyer. Para saber como importar dados da AppsFlyer para o dashboard do Google Ads, clique <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aqui</Anchor>.
> * Para comparar os eventos de instalação (first\_open no Google Ads), certifique-se de fazer uma busca detalhada de eventos de instalação no relatório de conversão no Google Ads. O Google Ads pode mostrar todas as conversões (podem ser instalações, compras, assinaturas), por isso é importante selecionar somente aqueles eventos de instalação dentre todos os eventos de conversão.

> 📄 **Veja também**
>
> * Para considerações relacionadas ao iOS 14, consulte <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads">Interoperabilidade do SKAdNetwork do Google Ads com a AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-faq=perguntas-frequentes-sobre-o-google-ads h_01HA1SM7D91QPG17WH752FBAFT=perguntas-frequentes-sobre-o-google-ads h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=solu%C3%A7%C3%A3o-r%C3%A1pida h_01K5DZBDMSBDKAFHVVPYD6YKRK=solu%C3%A7%C3%A3o-r%C3%A1pida still-not-working=ainda-n%C3%A3o-funcionou h_01K5DZBDMSVTE6M2J235ST85DE=ainda-n%C3%A3o-funcionou h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=lista-de-solu%C3%A7%C3%B5es-r%C3%A1pidas h_01K7NT8FVC1T557GPG7ZCYX33J=lista-de-solu%C3%A7%C3%B5es-r%C3%A1pidas h_01K7PAH7VDS7NGW6R6HERGXK9H=nota still-not-working::77f3165b=ainda-n%C3%A3o-funcionou-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=ainda-n%C3%A3o-funcionou-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=o-que-%C3%A9-necess%C3%A1rio h_01HA1SM7DAMNG8X22VNWMKBJ8R=o-que-%C3%A9-necess%C3%A1rio h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=importante h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=criar-registros-de-convers%C3%B5es-instala%C3%A7%C3%B5es h_01HA1SM7DBF9KDRNEV25KJHGHN=criar-registros-de-convers%C3%B5es-instala%C3%A7%C3%B5es create-a-conversion-inapp-events=criar-uma-convers%C3%A3o-eventos-in-app h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=criar-uma-convers%C3%A3o-eventos-in-app h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads---configura%C3%A7%C3%A3o-de-ios-campanhas-de-aplicativos h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads---configura%C3%A7%C3%A3o-de-ios-campanhas-de-aplicativos creating-conversion-recording-installs::6a56eb4b=criar-registros-de-convers%C3%B5es-instala%C3%A7%C3%B5es-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=criar-registros-de-convers%C3%B5es-instala%C3%A7%C3%B5es-1 google-ads-ios-configuration-sending-inapp-events=google-ads---configura%C3%A7%C3%A3o-do-ios---como-enviar-eventos-in-app h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads---configura%C3%A7%C3%A3o-do-ios---como-enviar-eventos-in-app creating-a-conversion-inapp-events=criar-uma-convers%C3%A3o-eventos-in-app-1 h_01HA1SM7DBCQYSJ3R67F0856QK=criar-uma-convers%C3%A3o-eventos-in-app-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=discrep%C3%A2ncias-do-google-ads h_01HA1SM7DBA7KK1DXFCE2G0QTP=discrep%C3%A2ncias-do-google-ads both-ios-and-android=ios-e-android h_01HA1SM7DB18BTDKK5BK4949HX=ios-e-android h_01HA1SM7DBSTAREA36YWRRRG82=observa%C3%A7%C3%B5es h_01HDP2XBSEJVQ5G0MD0V5R05CM=veja-tamb%C3%A9m" />
