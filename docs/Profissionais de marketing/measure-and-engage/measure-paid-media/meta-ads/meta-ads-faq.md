---
title: Perguntas frequentes sobre o Meta Ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
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
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-08-19T00:29:39Z'
  id: 4410472805649
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/4410472805649
---
> **Resumo**: encontre respostas para perguntas frequentes sobre o uso do Meta Ads na AppsFlyer.

<div id="meta-ads-faq" />

## Perguntas frequentes sobre o Meta Ads

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="Não consigo ver cliques de campanhas do Meta Ads no dashboard da AppsFlyer">

Por padrão, o Meta Ads envia apenas dados de conversão e engajamento. No entanto, você também pode começar a acessar <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#cost-clicks-and-impressions">dados de cliques, impressões e custos para suas campanhas do Meta Ads</Anchor>.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="A AppsFlyer pode mostrar o nível da campanha e grupos de anúncios?">

Sim. Na verdade, a AppsFlyer também mostra o nível de anúncio único, então você tem 3 níveis de detalhamento com o Meta Ads, campanhas >> grupos de anúncios >> anúncios.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Os dados do Meta Ads são exibidos em tempo real?">

Sim, todas as instalações e eventos in-app subsequentes são mostrados em tempo real. No entanto, cliques, impressões e dados de custo que a AppsFlyer acessa em um formulário agregado do Meta Ads chegam periodicamente no intervalo de poucas horas.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="Quando posso ver dados de uma nova campanha na AppsFlyer?">

Para ver dados de novos anúncios, conjuntos de anúncios e campanhas no Meta Ads, é preciso gerar pelo menos uma instalação.

Por exemplo, um novo anúncio gerou 100 cliques sem nenhuma instalação e não aparece no dashboard e nos dados da AppsFlyer. Outro anúncio tem apenas um clique e uma instalação, mas é exibido na AppsFlyer.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="Como posso obter mais instalações do Meta Ads?">

Se você ativou o retargeting para o Meta Ads, você pode obter até 100% mais instalações em suas campanhas de aquisição de usuários, de graça!  
Como? Leia <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#what-is-srn-mistargeting">aqui</Anchor>.

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="Como posso obter dados de instalação device-level no Android usando o Google Play e os Install Referrers da Meta?">

#### Google Play Install Referrer API

A Google Play Install Referrer API permite que os anunciantes recuperem dados de atribuição, como informações de campanha de instalações que se originaram na Google Play Store. Essa API deve ser <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrada ao seu aplicativo</Anchor> e envia dados de referrer quando o aplicativo é aberto pela primeira vez após a instalação. Os campos de atribuição estarão disponíveis nos relatórios de dados brutos da AppsFlyer com a correspondência `gp_referrer` quando a chave de descriptografia for enviada.

<div id="meta-install-referrer" />

#### Install Referrer da Meta

O Install Referrer da Meta fornece metadados adicionais da campanha, armazenados localmente no dispositivo. Isso pode ser acessado através do [SDK da AppsFlyer](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer). Ele complementa o Install Referrer do Google Play, fornecendo dados mais detalhados, incluindo dados de clique e impressão, além de potencialmente incluir múltiplas sessões. A atribuição via Install Referrer da Meta usa tipos de correspondência como `fb_referrer` (Facebook) e `ig_referrer` (Instagram).

<div id="campaign-attribution-fields" />

#### Campos de atribuição de campanha

* ID do anúncio
* Ad name
* Adset ID
* Nome do Adset
* ID da campanha
* Campaign name
* Account ID
* Canal

<div id="sdk-and-setup-notes" />

#### Notas e configuração do SDK

* A versão 5.4.0+ do SDK da AppsFlyer é necessária para os dados de referrer do Google Play.
* O suporte para referrer da Meta depende da configuração do SDK. Veja <Anchor target="_blank" href="/marketers/pt/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">esse boletim</Anchor> para mais detalhes de implementação.

<div id="submitting-the-decryption-key" />

#### Enviar Decryption Key

Ambos os tipos de referrer exigem uma chave de descriptografia da conta de desenvolvedor da Meta. Você só precisa fornecer essa chave uma vez por aplicativo: Em seguida: Em seguida:

1. Faça login no portal de desenvolvedor da Meta.
2. Vá para **My Apps** e selecione o aplicativo relevante.
3. Vá para **Settings > Basic** e procure por "Install Referrer decryption key."
4. No AppsFlyer, vá para **Colaborar > Integrações ativas > Meta ads**.
5. Cole a chave no campo **Install Referrer Decryption Key** e salve.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="A AppsFlyer disponibiliza os dados brutos do Meta Ads para agências?">

Não. Não temos permissão para fornecer dados brutos do Meta Ads para agências, porque as agências são consideradas terceiros em se tratando dos termos de serviços da Meta.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="Não vejo dados brutos do Meta Ads nos relatórios de instalação e de eventos in-app">

Por padrão, o Meta Ads não permite a distribuição de dados device-level que contêm informações de atribuição irrestritas. No entanto, se você aceitar os Termos do Meta Advanced Mobile Measurement (AMM), poderá acessar dados de atribuição device-level sem restrições para o Meta Ads. Para saber mais, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">ativar dados device-level para Meta ads</Anchor>.

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="Há alguma coluna específica para o Meta Ads nos relatórios de performance da AppsFlyer?">

Sim. Os relatórios de performance possuem estruturas de coluna estática em qualquer combinação de fonte de mídia selecionada, que apresentam informações até o nível de campanha.  
No entanto, quando você faz o download de relatórios de performance APENAS para o Meta Ads, a AppsFlyer adiciona 4 colunas a eles, que apresentam informações até o nível do anúncio único! As colunas adicionadas são Adset Name, Adset ID, Adgroup (por exemplo, anúncio único) Name e Adgroup ID.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Posso trabalhar com Meta campaign management partners e mensurar a performance com a AppsFlyer?">

Sim. A AppsFlyer é integrada a dezenas de Meta campaign management partners. Esses parceiros podem ser configurados para atribuição na página Integrações ativas no dashboard.

Para mais detalhes sobre como configurar a atribuição com <Anchor target="_blank" href="/marketers/pt/docs/configuring-meta-campaign-management-partners">Meta campaign management partners</Anchor>, clique aqui.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="O que devo fazer ao receber o seguinte aviso?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Verifique o Facebook App ID e confira se há alguma restrição geográfica ou de idade no Facebook App ID.
* Se a atribuição já estiver funcionando, isso significa que o aplicativo já está disponível no Meta Developer Portal e você pode ignorar com segurança essa mensagem de erro.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="O que acontece com janelas de lookback diferentes das janelas do Meta Ads?">

Clique de 7 dias e visualização de 1 dia são as janelas de lookback máximas e padrão para o Meta Ads.

Configurar janelas mais curtas na AppsFlyer diminui a atribuição de anúncios da Meta na AppsFlyer. Por outro lado, configurar janelas mais longas resulta em mais atribuição do lado da AppsFlyer do que da Meta.

Portanto, para minimizar discrepâncias, recomendamos configurar a janela de lookback do Meta Ads na AppsFlyer para cliques de 7 dias e visualizações de 1 dia.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="Quais são os parâmetros de API do Meta?">

Em algumas APIs da AppsFlyer, os parâmetros da Meta têm nomes diferentes dos exibidos no dashboard, por motivos de compatibilidade com versões anteriores. Consulte a tabela abaixo:

| Dados de conversão | Dados brutos da AppsFlyer | Meta |
| --- | --- | --- |
| Twitter | Twitter | campaign\_group\_name |
| id\_da\_campanha | ID da campanha | campaign\_group\_id |
| adgroup | As ad | adgroup\_name |
| adgroup\_id | ID do anúncio | adgroup\_id |
| conjunto\_de\_anúncios | Conjunto de anúncios | campaign\_name |
| id\_conjunto\_de\_anúncios | Adset ID | id\_da\_campanha |
| agency | parceira | N/D |
| is\_fb | Media Source | is\_fb |
| af\_canal | Canal | publisher\_platform |
| af\_siteid | ID do site | publisher\_platform quando o valor de `publisher_platform` não é igual a `facebook`, senão, `null`. |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Por quanto tempo consigo visualizar os dados a nível de usuário do Meta Ads na AppsFlyer?">

O Meta Ads exige que os provedores de atribuição excluam seus dados a nível de usuário seis meses após a instalação. Isso significa que os eventos realizados por esses usuários seis meses após a instalação do aplicativo são contados como orgânicos.  
Os dados agregados antigos permanecem os mesmos.  
Isso é relevante para todos os canais do Facebook (aplicativo do Facebook, Instagram, Messenger e AudienceNetwork).

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Os Universal Links para iOS e os App Links para Android são compatíveis com o Meta Ads?">

Universal Links para iOS e App Links para Android são compatíveis e podem ser usados no Meta Ads. Para mais informações, consulte a <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Central de ajuda da Meta</Anchor>.

* Para anúncios estáticos (não-catálogos), os Universal Links para iOS e os App Links para Android são compatíveis apenas em campanhas nas quais **o aplicativo** é selecionado como destino.
* Para anúncios dinâmicos, Universal Links, App Links e esquemas URI podem ser usados conforme descrito [aqui](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Observação**: Universal Links e App Links são compatíveis apenas com anúncios pagos.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Os Universal Links e os App Links são compatíveis com conteúdo não pago no Meta?">

Os Universal Links e os App Links somente são compatíveis com anúncios pagos. Em conteúdos sociais não pagos, pode ser necessário configurar uma social app landing page ou um esquema URI para redirecionar ou fazer o deep link de usuários.

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="A atribuição AEM não está funcionando">

Se a opção **compartilhamento avançado de dados** estiver ativa e não receber atribuições da Meta, verifique se os eventos compartilhados cumprem os critérios de elegibilidade da Meta. Consulte a [documentação da Meta](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="Os links do OneLink podem ser usados para abrir aplicativos e para o deep linking em anúncios dinâmicos de produtos do Meta?">

Sim. Links do OneLink com App Links, Universal Links ou esquemas URI configurados são compatíveis com anúncios de produtos dinâmicos. Você pode usar links do OneLink no seu feed de dados para catálogos usados em anúncios dinâmicos nos campos **applink.ios\_url** e **applink.android\_url.**

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="Eventos de conversão não são enviados para o Meta Ads">

Você pode ter o pacote Zero, que não inclui essa atribuição.

</Accordion>

<div id="can-i-use-get" />

<Accordion title="Posso usar o Get Conversion Data (GCD) para recuperar dados de conversão da Meta?">

**Sim**. Você pode continuar usando o **GCD** para recuperar dados de conversão da Meta, dependendo da configuração do seu aplicativo e da situação do contrato do AMM:

* Se o SDK do Facebook estiver integrado ao seu aplicativo:

  Conforme explicado na <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#deferred-deep-linking">documentação de deferred deep linking (DDL)</Anchor>, você pode recuperar os dados de DDL e usá-los via GCD.
* Se o SDK do Facebook não estiver integrado ao seu aplicativo:

  Você ainda pode recuperar os **nomes de campanha, adset e anúncios** via GCD, desde que <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#meta-ads">o contrato do Meta Advanced Mobile Measurement (AMM) esteja assinado</Anchor>. Nesse caso, você pode usar esses valores para aplicar sua própria **lógica de deep linking personalizada**.

<div id="note" />

> 📘 **Nota**
>
> As políticas de compartilhamento de dados da Meta podem influenciar o nível de detalhes disponíveis através do GCD. Certifique-se de que o AMM esteja assinado para ampliar os dados disponíveis no nível das campanhas.

</Accordion>

<div id="meta-ads-cost-faq" />

## Perguntas frequentes sobre custos do Meta Ads

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Como receber dados de custo do Meta Ads no dashboard da AppsFlyer">

A AppsFlyer recebe dados de gastos (incluindo cliques e impressões) de campanhas do Meta Ads se uma ou mais instalações ocorreram durante os 7 dias anteriores.

Se uma campanha do Meta Ads envolve várias plataformas (Android, iOS, desktop etc.), o custo no dashboard é específico da plataforma e é calculado pelo Meta Ads.

<Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Recebendo custos do Meta Ads incluindo cliques e impressões</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Exemplo de custo no Meta Ads">

Um anunciante executa campanhas usando o Meta Ads. Na AppsFlyer, o anunciante vê o seguinte:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

As informações de custo são enviadas pelo Meta Ads para a AppsFlyer. O número de **instalações** é calculado pela AppsFlyer usando as regras de atribuição. Como resultado, o eCPI calculado pelo Meta Ads é geralmente diferente do calculado pela AppsFlyer.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Não consigo ver dados de custo antigos do Meta Ads no dashboard da AppsFlyer">

Após realizar o primeiro login de administrador do Meta Ads conforme descrito acima, a AppsFlyer recebe os dados de custo do Meta Ads em até 7 dias retroativos para as campanhas existentes. Os dados de custo não estão disponíveis antecipadamente.

Nas sincronizações subsequentes, a AppsFlyer recebe dados dos últimos 7 dias. Isso significa que os dados de custo, cliques e impressões são coletados para todas as campanhas que têm pelo menos 1 conversão durante os últimos 7 dias.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="Posso interromper a sincronização de dados de custo?">

Para interromper a sincronização de dados de custo com o Meta Ads, <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">remova a AppsFlyer da sua integração de negócios na sua conta do Meta Ads</Anchor>.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="Os dados de custo funcionaram bem por alguns meses, mas pararam de aparecer">

O Meta Ads pode reconfigurar essa permissão para obter os dados de custo em um intervalo de alguns meses. Se você perceber que os dados de custos pararam de aparecer no dashboard, repita os passos para login de administrador do Meta Ads.

Se o usuário administrador alterar sua senha do Meta Ads, os passos para realizar o login também devem ser repetidos.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="Acabei de clicar no meu anúncio do Facebook há 5 minutos. Por que não vejo o clique na AppsFlyer?">

A AppsFlyer obtém cliques agregados, impressões e dados de custo do Meta Ads periodicamente, no intervalo de algumas horas. Portanto, pode levar algumas horas para que essas ações apareçam no dashboard da AppsFlyer.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Posso obter dados brutos de cliques e impressões do Meta Ads?">

Como a AppsFlyer só obtém dados de cliques agregados e de impressões do Meta Ads, o conjunto completo de cliques e impressões brutos não fica disponível. Os únicos cliques e impressões brutos disponíveis nos relatórios brutos são os que resultaram em instalações.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="Há limitações dos dados de custo do Meta Ads por geolocalização?">

Se você filtrar por geolocalização no dashboard da AppsFlyer, poderá ver o resumo e a análise dos dados de custo do Meta Ads.

Esses dados estão disponíveis somente para "Mobile App Install Campaigns" no Meta Ads.

Além disso, o custo por dados geográficos está disponível apenas para campanhas de plataforma única. Isso significa que as campanhas que têm um conjunto de anúncios segmentado para Android e um conjunto de anúncios segmentado para iOS não podem ter dados de custo específicos por área geográfica. **Para obter todos os dados de custo, dedique uma campanha para cada plataforma**.

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="Quais são as limitações dos dados de custo do Meta Ads na Master API?">

O Meta Ads não oferece suporte ao agrupamento de dados de custo por geolocalização ou por canal simultaneamente nos <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">relatórios da Master API</Anchor>.

Para criar um relatório com todos os dados de custo, agrupe-os apenas por uma dessas dimensões.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="Por que o custo total mostrado na Meta e na AppsFlyer não coincide?">

Existem diferenças entre o Meta Ads e os modelos de atribuição da AppsFlyer. Essas diferenças podem levar a discrepâncias nos dados de custo do Meta Ads:

* **Atribuição entre dispositivos**: às vezes, isso pode causar problemas, pois uma campanha para uma plataforma (iOS/Android) mostra uma instalação com seu respectivo custo para outra plataforma.
* **Campanhas para dispositivos fora do mobile**: nessas campanhas, como as campanhas de link click do Meta Ads, os usuários de desktop podem eventualmente instalar aplicativos mobile. Nesse caso, a AppsFlyer não mostra custos. No entanto, se o clique do link foi realizado pelo mesmo dispositivo que instalou o app, os dados da receita serão coletados.  
  Por exemplo, um usuário do Facebook clica em um anúncio que leva à página inicial do anunciante em um computador desktop. Uma semana depois, o mesmo usuário instala o aplicativo iOS do anunciante em um dispositivo iPhone. Enquanto a instalação é atribuída e exibida no dashboard da AppsFlyer, o custo da instalação entre plataformas não é.
* **Campanhas com 0 resultados nos últimos 7 dias**: a AppsFlyer só sincroniza o custo de campanhas que tiveram instalações/conversões nos últimos 7 dias. Se o custo do Meta Ads acabou de ser configurado, as campanhas que ficaram inativas por mais de 7 dias antes disso não mostrarão o custo.
* **Anúncios excluídos e arquivados**: O custo de anúncios excluídos e arquivados não é informado pela Meta para a AppsFlyer, mas esse custo é refletido no dashboard da Meta. Isso pode causar uma discrepância entre os relatórios da Meta e da AppsFlyer quando comparamos dados no nível da campanha.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="Por que o cálculo da AppsFlyer para eCPI é diferente do custo calculado pelo Meta Ads, enquanto o custo total é idêntico?">

O custo por instalação é calculado dividindo o custo total pelo número de instalações. Como a <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-discrepancies">AppsFlyer conta as instalações de uma forma diferente da Meta</Anchor>, geralmente o eCPI será diferente entre os dois.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="Por que os dados de custo não incluem dados de todas as campanhas?">

Quando um usuário que faz o login no Meta Ads (conforme descrito acima) não tem acesso a algumas das campanhas em execução, o resultado são campanhas exibidas no dashboard da AppsFlyer, mas sem alguns dados de custo, cliques e impressão.

**Atenção**: embora vários usuários do Meta Ads possam ter permissão para executar campanhas no Meta Business Manager, apenas um é necessário para realizar o login no Meta Ads em si.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="Os dados de custo do Meta Ads são exibidos para campanhas de retargeting?">

Os dados de custo e ROI para campanhas de retargeting podem ser encontrados na **visãounificada dos <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">relatórios de cohort</Anchor>.**

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="Por que a janela de configuração de custo do Meta Ads fecha antes do login?">

Se você estiver conectado ao Meta Ads no mesmo navegador em que está executando a configuração, a janela se conectará automaticamente ao Meta Ads usando essas credenciais. Se o acesso já foi concedido à AppsFlyer, não há nada a fazer e a janela fecha.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Por que há uma discrepância nos dados de custo para aplicativos na loja da Amazon?">

Ao contrário dos dados da AppsFlyer, o Meta Ads não faz distinção entre dados de custo de aplicativos Android e aplicativos da Amazon, que são baseados no Android. Portanto, os dados de custo de usuários da Amazon podem ser atribuídos para campanhas direcionadas a outros usuários Android em vez de campanhas originais da Amazon.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="Como posso conectar os dados de custo de uma nova conta do Meta Ads enquanto minha conta antiga ainda está vinculada?">

Se você deseja mudar para uma nova conta de anúncios, mas seu custo do Meta Ads já está vinculado via AppsFlyer com sua conta antiga, você precisa desconectar a conta de anúncios via Meta Ads e conectar a nova conta na AppsFlyer.

1. No Meta Ads, vá para **Settings** > **Business Integration**.
2. Na aba **Active**, remova a integração da AppsFlyer.  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Acesse o dashboard da AppsFlyer e conecte o custo com a nova conta de anúncio.

</Accordion>

<div id="facebook-sdk-faq" />

## Perguntas frequentes sobre o SDK do Facebook

<div id="who-needs-facebooks-sdk" />

<Accordion title="Quem precisa do SDK do Facebook?">

Seu aplicativo pode já ter o SDK do Facebook integrado a ele, antes de integrar o SDK da AppsFlyer. Ou então, você pode estar se perguntando se realmente precisa do SDK do Facebook além do SDK da AppsFlyer. E, se precisar, os dois podem coexistir sem duplicação de relatórios?

Seu aplicativo não requer o SDK do Facebook para:

* **Aquisição de usuários**: geralmente, o SDK da AppsFlyer faz toda a atribuição de aquisição de usuários mobile dos seus usuários do Meta Ads, incluindo engajamentos, instalações, sessões e eventos pós-instalação.
* **Deep linking:** para abrir o aplicativo quando o link é clicado e fazer um deep link dos usuários para uma página ou atividade específica no aplicativo, você pode usar o OneLink, sem o SDK do Facebook. Você pode usar Universal Links, App Links e esquemas URI para fazer isso. Para mais informações, consulte a <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Central de Ajuda da Meta</Anchor>.  

  **Atenção:**  
  Para anúncios estáticos (não-catálogos), os Universal Links para iOS e os App Links para Android são compatíveis apenas em campanhas nas quais o **aplicativo** é selecionado como destino.  
  Por exemplo, se você configurar uma campanha de awareness na Meta, como essa campanha não permite que o **aplicativo** seja selecionado como destino, não é possível usar Universal Links e App Links.  

  Para anúncios dinâmicos, Universal Links, App Links e esquemas URI podem ser usados conforme descrito[aqui.](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)  

  O Meta Ads recorta a URL do OneLink e a usa para criar um link do aplicativo do Meta Ads que abre o app e faz o deep linking do usuário.

Seu aplicativo requer o SDK do Facebook além do SDK da AppsFlyer para:

* **Deferred deep linking**:  
  Os valores DDL do Meta Ads não estão disponíveis nos dados de conversão. Os clientes devem coordenar com a Meta e, normalmente, o SDK do Facebook é necessário para acessar esses dados.
* **Dados das campanhas de anúncios de produtos dinâmicos**: Você só pode obter dados para anúncios de produtos dinâmicos do SDK do Facebook.
* **Outros recursos do Meta Ads**: Você pode precisar do SDK do Facebook por razões não relacionadas à atribuição, como autenticação, monetização de anúncios, compartilhamento social, convites do usuário, etc.

<div id="note-1" />

> 📘 **Nota**
>
> As informações e recomendações acima sobre deep linking e deferred deep linking são baseadas em testes precisos que realizamos usando as ferramentas de demonstração/visualização disponíveis no Meta Ads, que usam um mecanismo diferente dos live ads.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Evitar duplicatas com o SDK do Facebook">

Se você tiver <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">os SDKs da AppsFlyer e do Facebook no seu aplicativo</Anchor>, as instalações e os eventos in-app serão informados via SDK do Facebook e, em seguida, via postbacks para servidores do Meta Ads por meio da AppsFlyer. Como você pode evitar relatórios duplicados?

* **Para instalações**, a Meta desduplica as instalações. Isso significa **que não há duplicação** e cada instalação é contada apenas uma vez.
* **Para eventos in-app**, o Meta Ads não faz a desduplicação, podendo levar a uma contagem dupla e a relatórios imprecisos de eventos in-app. Para evitar essa duplicação, considere uma das seguintes opções:
  * Não configure eventos no SDK do Facebook
  * Para Android, desative o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping">mapeamento de eventos in-app do Meta Ads</Anchor> na AppsFlyer.  
    Observe que, para habilitar a atribuição de SKAN para iOS 14.5+, você precisará <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">mapear eventos in-app para o Meta Ads</Anchor>.

</Accordion>

<div id="meta-ads-attribution-faq" />

## Perguntas frequentes sobre atribuição com o Meta Ads

<div id="attributing-agencies-with-facebook" />

<Accordion title="Atribuição de agências com o Meta Ads">

Agências e parceiros de gerenciamento de campanhas da Meta podem executar e atribuir campanhas do Meta Ads em nome dos anunciantes na AppsFlyer ou até mesmo junto com as próprias campanhas dos anunciantes no Meta Ads. Para que as campanhas da agência sejam atribuídas à agência, o nome da campanha DEVE começar com o nome da agência.

Observe que para usuários do iOS 14, apenas **uma** agência pode executar campanhas para uma conta de anúncios específica. Veja mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads#interoperabilidade-do-skan-appsflyer---anúncios-meta">Meta Ads e interoperabilidade da SKAdNetwork na AppsFlyer</Anchor>.

Para mais informações sobre agências e atribuição de instalações no Meta Ads, <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts#configurações-srn">acesse aqui</Anchor>.

Além disso, **as agências não podem alterar as janelas de lookback do Meta Ads e controlar o retargeting**. É necessário pedir ao anunciante que ele faça essas alterações se forem necessárias.

Além disso, as agências não podem modificar nenhum postback de eventos in-app enviado para o Meta Ads. Isso se deve ao requisito do Meta Ads para receber informações sobre todas as instalações, incluindo aquelas que não são atribuídas a ele (e, portanto, podem não ser trazidas pela agência).

A imagem abaixo mostra todas as configurações que precisam ser feitas pelo anunciante para que a agência possa gerenciar as campanhas no Meta Ads:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Atribuição do Meta Ads para aplicativos externos do Android">

O Meta Ads não permite criar campanhas de instalação de aplicativos mobile para aplicativos Android que estão em mercados fora da loja, como o Baidu.

No entanto, você pode anunciar e registrar instalações para aplicativos fora da loja no Meta Ads, seguindo estas instruções:

1. O desenvolvedor precisa preparar um APK separado para cada mercado fora da loja que você usa para anunciar seu aplicativo. Mais detalhes <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">aqui</Anchor>.
2. Crie uma campanha de **tráfego** ou **conversões** no Meta Ads, com a atribuição mobile ativada, que envia leads para uma landing page.
3. A página inicial deve incluir um botão **Baixar o aplicativo**, que se vincula diretamente ao mercado fora da loja em que o APK existe.
4. O lead clica no botão e é redirecionado ao mercado fora da loja. Depois de concluir a instalação, a AppsFlyer atribui o usuário ao Meta Ads, por meio da MMP API.

<div id="note-2" />

> 📘 **Nota**
>
> A mesma solução se aplica a aplicativos no Google Play e na App Store, que <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">exigem o uso de uma landing page</Anchor> antes do redirecionamento.

Para instruções específicas sobre a atribuição de aplicativos na Amazon, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">aqui</Anchor>.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="O que é uma atribuição cruzada do Meta Ads para Android e iOS?">

O Meta Ads identifica os usuários com base na conta do Meta Ads. Alguns usuários têm dispositivos iOS e Android associados à mesma conta.

Se esse usuário clicar ou visualizar um anúncio do seu aplicativo em um dispositivo Android, mas instalá-lo em um dispositivo iOS, o Meta Ads se considera como responsável pela instalação. Como resultado, um nome de campanha do Android aparece no dashboard do iOS.

<div id="example" />

> 📄 **Exemplo**
>
> André está usando seu dispositivo Android. Ao usá-lo, ele clica em um anúncio de campanha da Meta no Android para um aplicativo chamado **Bubbles**. Ele não baixa o aplicativo.
>
> Um dia depois, ele decide baixar o aplicativo **Bubbles** organicamente em seu dispositivo iOS e o inicia.
>
> Nessa situação, a atribuição da AppsFlyer pega a campanha do Meta Ads no Android e a apresenta no dashboard do iOS, onde André fez o download e abriu o app.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="O que são os canais do Meta Ads?">

Com o Meta Ads, você pode ver os dados divididos não apenas por campanhas, conjuntos de anúncios e anúncios, mas também por canais do Meta Ads (chamados de Placements):

* **Facebook** - usuários do aplicativo do Facebook
* **Instagram** - usuários do aplicativo do Instagram
* **Messenger** - usuários do aplicativo do Facebook Messenger
* **AudienceNetwork** - usuários de outros aplicativos que pertencem ou estão afiliados ao Meta Ads
* **Threads** - usuários do aplicativo do Threads
* **WhatsApp** - usuários do aplicativo do WhatsApp

Use esses dados para comparar a qualidade dos usuários que você obtém através de diferentes canais.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=perguntas-frequentes-sobre-o-meta-ads h_01HD1JTW2EP1MY3DD9136E9CHC=perguntas-frequentes-sobre-o-meta-ads h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=install-referrer-da-meta meta-install-referrer=install-referrer-da-meta h_attribution_fields=campos-de-atribui%C3%A7%C3%A3o-de-campanha campaign-attribution-fields=campos-de-atribui%C3%A7%C3%A3o-de-campanha h_sdk_requirements=notas-e-configura%C3%A7%C3%A3o-do-sdk sdk-requirements=notas-e-configura%C3%A7%C3%A3o-do-sdk h_decryption=enviar-decryption-key decryption-key=enviar-decryption-key h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=nota facebook-ads-cost-faq=perguntas-frequentes-sobre-custos-do-meta-ads h_01HD1JTW2EEVD1PDPFW15K45CE=perguntas-frequentes-sobre-custos-do-meta-ads h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=perguntas-frequentes-sobre-o-sdk-do-facebook h_01HD1JTW2FPRCVGBF7CG7ZMKXF=perguntas-frequentes-sobre-o-sdk-do-facebook h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=nota-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=perguntas-frequentes-sobre-atribui%C3%A7%C3%A3o-com-o-meta-ads h_01HD1JTW2F2JV2BMDS40HFG6K0=perguntas-frequentes-sobre-atribui%C3%A7%C3%A3o-com-o-meta-ads h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=nota-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=exemplo h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />
