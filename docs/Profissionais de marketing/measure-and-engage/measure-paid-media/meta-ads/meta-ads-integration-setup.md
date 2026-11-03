---
title: Configuração de integração do Meta Ads
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
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
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2026-09-10T12:30:03Z'
  id: 207033826
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/207033826
---
> **Resumo:** saiba mais sobre como integrar o Meta ads com a AppsFlyer.

## Guia de configuração do Meta ads

Quanto tempo leva para começar a atribuir seus anúncios de aplicativos mobile do Meta ads com a AppsFlyer?

Se você já tem o <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">SDK da AppsFlyer integrado em seu aplicativo</Anchor> e já definiu seu aplicativo no Meta ads, a resposta é: menos de um minuto!

Não é necessário implementar o Login do Facebook ou integrar seu aplicativo com o SDK do Facebook para realizar a atribuição mobile. Basta seguir as instruções do [passo a passo da configuração](#configuração-básica-de-atribuição-do-meta-ads) abaixo. Depois, confira as [opções de configuração avançada](#configuração-avançada-de-atribuição-do-meta-ads) para o Meta ads.

## Configuração básica de atribuição do Meta ads

<div id="create-and-retreive-facebook-app-id" />

<Accordion title="Criar e recuperar um Facebook App ID">

Para integrar o Meta Ads na AppsFlyer, primeiro, crie um <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">Facebook App ID</Anchor>, e depois o recupere.

**Para criar uma Facebook App ID**:

1. No **Meta Ads**, acesse o <Anchor target="_blank" href="https://developers.facebook.com/apps">painel do aplicativo.</Anchor>
2. Em **Aplicativos**, clique em **Criar novo aplicativo.**
3. Preencha o nome do seu aplicativo e insira um namespace exclusivo. Certifique-se de adicionar a plataforma correta para seu aplicativo. Caso contrário, as instalações podem não ser atribuídas corretamente.

**Para recuperar o Facebook App ID**:

1. No **Meta Ads**, acesse o <Anchor target="_blank" href="https://developers.facebook.com/apps">painel do aplicativo</Anchor>.
2. Clique no aplicativo desejado.
3. Clique no App ID, que aparece na parte superior esquerda da tela, para copiá-lo.

   [![](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

A AppsFlyer atribui dados por App ID. O mesmo Facebook App ID pode ser usado para [aplicativos Android e iOS](https://developers.facebook.com/docs/app-ads/app-setup/). Observe que, para iOS 14+, o Meta ads limita as contas de anúncios a nove contas por aplicativo.

</Accordion>

<div id="enable-meta-ads-device-level-data" />

<Accordion title="Ativar dados device-level do Meta ads">

A partir de 17 de junho de 2025, o Meta reativou o relatório de **Advanced Mobile Measurement (AMM)**. Assim que você aceitar os termos, você receberá:

* Analytics mobile device-level
* Métricas de atribuição a nível de evento para campanhas do Meta
* Integração completa com seus dashboards e exportações de dados existentes na AppsFlyer

**Para ativar o AMM, siga essas etapas:**

1. Visite <Anchor target="_blank" href="https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms">Meta Ads</Anchor>.
2. Selecione o(s) app ID(s) relevante(s).
3. Aceite os termos de Advanced Mobile Measurement do Meta.

> 🚧 **Importante!**
>
> * Um administrador da conta deve aceitar os termos do AMM.
> * Dados device-level com visibilidade total de atribuição estão disponíveis apenas para novos dispositivos atribuídos após a aceitação dos termos do AMM.
> * Eventos in-app herdam o status de restrição em suas conversões atribuídas. O que isso significa?
>   * Se o evento in-app for atribuído a uma conversão que ocorreu antes da assinatura do contrato de Advanced Mobile Measurement (AMM), o evento permanece restrito.
>   * Se o evento for atribuído a uma conversão que ocorreu após a assinatura do contrato do AMM, o evento estará disponível nos relatórios de dados brutos.

</Accordion>

<div id="set-the-meta-ads-active-integration" />

<Accordion title="Configure a integração ativa do Meta Ads">

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Procure por Meta Ads e, em seguida, selecione-o.
3. Clique em **Integrate**. Você será direcionado para a página de configuração da integração.
4. Na aba **Integração** selecione **Ativar parceiro**.  
   **Atenção:** O toggle deve permanecer ligado (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor>) enquanto você trabalhar com o parceiro.
5. Em **configurações gerais**:

   [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

   * Cole seu [Faceboook app ID](#create-and-retreive-facebook-app-id) no campo **Faceboook app ID**.
   * Cole a chave de decodificação do Install Referrer [do Meta ads](/docs/meta-ads-integration-setup#dados-criptografados-da-google-play-referrer-api-ou-do-install-referrer-do-meta).
6. Ative ou desative o **compartilhamento avançado de dados**, veja [compartilhamento avançado de dados](#advanced_data_sharing) abaixo. (Disponível gradualmente para todas as contas até 14 de outubro de 2024.)
7. Ative ou desative o **compartilhamento de dados de correspondência avançada**; veja [compartilhamento de dados de correspondência avançada](#advanced_matching_data_sharing) abaixo.
8. Clique em **Salvar integração**.

</Accordion>

<div id="optional--configure-recommended-settings" />

<Accordion title="[Opcional] Defina as configurações recomendadas">

[![](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

* Para fazer a correspondência com a janela de lookback de clique do Meta Ads, defina-a para 7 dias.  
  (Observe que [existem alguns casos específicos em que o padrão é diferente](https://www.facebook.com/business/help/395050428485124?id=428636648170202)).
* Para corresponder à janela de lookback de visualização dos anúncios da Meta, defina-a para um dia.
* Para habilitar a atribuição de reinstalação, ative **Atribuição de reinstalação**. A atribuição de reinstalação permite que você mensure usuários que reinstalam seu aplicativo na janela de reatribuição. Você não precisa habilitar a atribuição de exibição ou configurar janelas de lookback para atribuição de reinstalação, pois ela leva sua configuração a partir das configurações de atribuição de instalação. Para mais informações, leia este artigo sobre a <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls">mensuração de reinstalações</Anchor>.

</Accordion>

## Configuração avançada de atribuição do Meta ads

Com a atribuição básica já configurada para o Meta ads, é hora de algumas configurações rápidas e avançadas de atribuição.

<div id="getting-userlevel-data-for-android-installs" />

<Accordion title="Obtendo dados device-level para instalações do Android">

#### Google Play Install Referrer API

O Meta Ads compartilha metadados de campanha para anúncios de aplicativos Android que levam os usuários para a Play Store. Nesse contexto, os campos de atribuição estão disponíveis para os anunciantes na Google Play Install Referrer API, que deve ser <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrada ao seu aplicativo.</Anchor> Os campos fornecidos através da Google Play install referrer API preenchem os relatórios de dados brutos da AppsFlyer com o tipo de correspondência `gp_referrer`. Isso só está disponível após o envio da chave de descriptografia e depois que a instalação é atribuída ao Meta ads. Isso permite que a AppsFlyer atribua usuários que não têm um ID de publicidade (habilitado para LAT).

#### **Install referrer do Meta**

> 📘 **Nota**
>
> o install referrer do Meta permite que a AppsFlyer receba metadados de campanhas de anúncio do armazenamento local de um dispositivo. Veja o [Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer) para aprender como ativar o SDK para acessar o install referrer do Meta.

Além da Google Play install referrer API, o install referrer do Meta permite que a AppsFlyer receba metadados de campanha de anúncios do armazenamento local de um dispositivo. Esses dados são usados para a mensuração de atribuição. As principais diferenças entre a Google Play install referrer API e o install referrer do Meta são:

* O install referrer do Meta pode incluir dados de impressão e de clique, enquanto a Google Play install referrer API está limitada aos dados de clique
* O install referrer do Meta pode incluir dados de várias sessões, enquanto a Google Play install referrer API está limitada apenas aos dados da última sessão (o dispositivo tem que instalar o aplicativo na mesma sessão em que ocorreu o clique)

Como resultado, você pode ver um aumento nas instalações atribuídas ao Meta em relatórios de dados brutos. Quando uma instalação é atribuída através da Google Play install referrer API ou do install referrer do Meta, os dados ficam disponíveis em relatórios de dados brutos. Os campos que podem estar disponíveis para atribuição por meio do install referrer do Meta preenchem os relatórios de dados brutos da AppsFlyer com o tipo de correspondência `fb_referrer` para a atribuição do aplicativo do Facebook e `ig_referrer` para a atribuição a partir do aplicativo do Instagram. Isso só está disponível quando a chave de descriptografia é submetida e uma instalação é atribuída ao Meta ads. A chave de descriptografia do install referrer do Meta é a mesma chave usada para o Google Play install referrer e não precisa ser fornecida à AppsFlyer uma segunda vez.

#### **Campos de atribuição de campanha disponíveis por meio do referrer:**

* ID do anúncio
* Nome do anúncio
* Adset ID
* Nome do Adset
* ID da campanha
* Nome da campanha
* Account ID
* Canal

> 📘 **Nota**
>
> * **Para a Google Play Install Referrer API:**
>   * O SDK da AppsFlyer deve ser **V5.4.0+** para que os dados do referrer sejam transmitidos corretamente. Os dados do referrer têm prioridade sobre os dados fornecidos pela API e não são restritos. Essa solução se aplica à atribuição de click-through e não à atribuição de view-through.
>   * O campo Canal é determinado pelo valor do canal recebido através da Google Play Referrer API (enviado para o Google Play pelo Meta). Se for recebida uma string vazia, o campo canal exibirá "None".
>
> * **Para o install referrer do Meta:** Consulte os <Anchor target="_blank" href="/marketers/pt/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">pré-requisitos e as ações necessárias</Anchor> descritas nesse boletim.

#### Install referrer do Meta – Perguntas frequentes

**Em que casos o install referrer se aplica à atribuição?**

* Para atribuição de instalação:
  * Atribuição de click-through, para todas as campanhas
  * A atribuição de view-through é compatível com todas as campanhas de aplicativos Advantage+ e campanhas manuais de promoção de aplicativos com uma segmentação ampla (por exemplo, em que a idade e o gênero estão definidos como padrão).

* Compatibilidade: Google Play Store e lojas de aplicativos Android que não sejam do Google Play
* Exceções: não inclui campanhas que redirecionam para landing pages

**Para que a "segmentação ampla" é usada no Meta ads?**

A segmentação ampla é necessária para receber dados de view-through. A configuração de campanha inclui:

* Idade: Padrão (18-65+)
* Género: Padrão (todos os gêneros)
* Localização: Grupos de países e países. **Atenção:** Para localizações mais específicas (como cidades ou códigos postais), as campanhas que usam a segmentação por inclusão têm de ser definidas como flexíveis.
* Segmentação detalhada: Os segmentos de interesse, os comportamentos e os dados demográficos avançados são definidos como flexíveis.
* Audiências personalizadas: definir como flexível.
* Para "flexível", deve ser selecionada a opção "Advantage detailed targeting" para campanhas de anúncios: [![](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)

#### Dados criptografados da Google Play Referrer API ou do install referrer do Meta

Os dados da Google Play Referrer API ou do install referrer são criptografados pelo Meta. Estes dados podem ser descriptografados usando uma chave disponível na sua conta de desenvolvedor do Meta. Você deve nos fornecer a chave de descriptografia descrita nas ações necessárias. A chave de descriptografia precisa ser enviada apenas uma vez por aplicativo.

Observe que, se a chave não for fornecida ou tiver sido excluída, há alguns casos em que o Meta Ads ainda é atribuído para a instalação com base no referrer, mesmo sem os campos de atribuição da campanha (mencionados na lista acima). Isso acontece quando:

* O Meta Ads não reivindicou a instalação
* Os dados recebidos da Google Play Referrer API foram recebidos, mas não foram descriptografados
* Esse foi o último clique

**Para obter sua chave de descriptografia do Meta:**

1. Faça login no seu portal de desenvolvedor do Meta.
2. Navegue até **Meus aplicativos** no canto superior direito.
3. Selecione o aplicativo para o qual você gostaria de acessar sua chave de descriptografia.
4. Vá até **Configurações** > **Básico** no lado esquerdo da página. [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Vá até a seção Android e você verá sua chave de descriptografia chamada Chave de descriptografia do referenciador da instalação (Install Referrer decryption key) abaixo do campo Nomes do pacote (Package Names). Atenção: essa é a mesma seção na qual você configurou o nome do pacote e a Google Play Store.

**Para definir a chave de descriptografia na AppsFlyer:**

1. [Obrigatório] Verifique se o SDK da AppsFlyer V5.4+ é a versão utilizada em seu aplicativo. Evite confiar em versões anteriores.
2. Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.
3. Selecione **Meta ads**. [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. Na aba **Integração**, cole a chave em **Chave de descriptografia do install referrer**. Isso deve ser feito apenas uma vez por aplicativo.
5. Clique em **Salvar integração**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Custo, cliques e impressões">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)

Essa integração fornece dados agregados sobre custo, cliques e impressões para suas campanhas, conjuntos de anúncios, anúncios e regiões geográficas/países. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.

**Atenção:** os dados sobre cliques e impressões estão incluídos na integração. No entanto, **os dados de custos requerem uma assinatura do** <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor>.

**Para ativar a Cost API**:

1. Faça login na sua conta de usuário do Meta ads, que está habilitada para gerenciar as campanhas da conta no Meta ads. O login deve ser feito com um usuário que tem permissões para executar todas as campanhas no Meta Business Manager.
2. Acesse a aba **Custo**.
3. Ative **a opção para obter dados de custos, cliques e impressões**.
4. Clique no botão **fazer login**. Você pode fazer login com uma conta business ou admin do Meta ads.
5. Quando solicitado, permita que a AppsFlyer acesse os dados de suas campanhas do Meta.  
   **Atenção:** Na primeira sincronização de dados após a integração, assim como nas sincronizações subsequentes, a AppsFlyer recebe dados do Anúncios da Meta por até 7 dias retroativamente.

**Para excluir uma conta do Meta Ads conectada:** Na coluna ações, passe o mouse sobre uma conta, clique em **Remover conexão.**

> 📘 **Observações**
>
> * Se você já estiver conectado ao Meta ads, quando clicar no botão **f login**, a janela abre e fecha imediatamente. Esse é um comportamento padrão.
> * Se você tiver vários usuários com permissões para o Meta ads, recomendamos que você faça o login para todos eles, para <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">evitar receber dados parciais</Anchor>.

#### Status de sincronização dos dados de custo

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da sua API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes, seja no dashboard de status da integração de custo (e receita de anúncios) seja no dashboard individual da ad network. 

Você pode sincronizar várias contas para extrair dados de custo. Para cada conta sincronizada, a AppsFlyer exibe o status da integração de custo e a última vez que foi feita a extração dos dados de custo correspondentes.

Saiba mais sobre como enriquecer seus dados com <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#perguntas-frequentes-sobre-custos-do-meta-ads">dados de custo, cliques e impressões</Anchor>.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="Mapeamento de eventos in-app">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**Para mapear eventos in-app:**

1. Ative **Postbacks de eventos in-app.**  
   Ao habilitar o mapeamento de eventos in-app no Meta ads para um aplicativo **pela primeira vez**, **af\_app\_open** é automaticamente mapeado para **fb\_mobile\_activate\_app**.
2. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **mapeado para evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no Meta Ads As configurações de mapeamento possíveis são: As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** Campo de texto:obtenha o ID do evento correspondente no Anúncios da Meta.</li><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem mapeamento de nomes.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro**: enviar postbacks apenas quando este evento for atribuído a Meta Ads.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: enviar todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envie todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. Para adicionar um evento SDK ou S2S à lista, clique em **Adicionar evento**.

**Limitações relacionadas aos nomes de eventos:**

* Limitação do tamanho dos nomes de eventos: 2 a 40 caracteres
* Os seguintes caracteres não são permitidos:
  * Dois pontos (:)
  * Ponto (.)
  * Conjuntos de caracteres não latinos (ingleses): desde o dia 12 de janeiro de 2020, o Meta ads rejeita caracteres chineses. A AppsFlyer não testou outros conjuntos de caracteres e você deve usá-los somente depois de verificar com o Meta ads se há suporte para esses conjuntos de caracteres em postbacks.
* Os nomes dos eventos são sensíveis a maiúsculas e minúsculas. Para evitar discrepâncias, use o nome do evento correto para todas as fontes de mídia e versões do aplicativo.

> 📘 **Nota**
>
> o Meta ads pode otimizar suas campanhas com base nos dados de receita de anúncios, <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping#mapeamento-de-dados-de-receita-de-anúncios-para-otimização-de-campanhas">mapeando o evento af\_ad\_revenue para o evento correto do Meta</Anchor>.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribuição de retargeting">

A atribuição de retargeting da AppsFlyer para Meta ads permite que os anunciantes atribuam o engajamento de um usuário existente com um anúncio do Facebook e mensurem a qualidade do usuário, pós-engajamento, usando os relatórios da AppsFlyer. Ela deve ser usada somente se você estiver executando ativamente campanhas direcionadas a seus próprios usuários do Facebook.

1. <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">Ative o retargeting na página Configurações do aplicativo</Anchor> .
2. Na página de parceiro do Meta ads, ative **a atribuição de reengajamento**.
3. Configure a **janela de lookback de reengajamento por click-through**.  
   Que é o período de tempo que se inicia com o clique no anúncio, durante o qual o aplicativo deve ser iniciado para que o clique seja registrado como um reengajamento.  
   Selecione as unidades da janela de lookback (horas ou dias) e defina a barra deslizante para o valor desejado.  
   [![](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Ative a **atribuição de view-through de reengajamento**.
5. Defina o slider da **janela de lookback de view-through de reengajamento** para o valor desejado (até 24 horas). Esse é o período de tempo a partir de uma impressão de anúncio, durante o qual o aplicativo deve ser iniciado para que a impressão seja registrada como um reengajamento.[![](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)
6. Defina a **janela de reengajamento**.  
   Este é o período em que os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting como fonte principal.  
   Você pode definir o valor em dias (1 a 90), horas (até 23) ou até mesmo por tempo vitalício. O padrão é 30 dias.  
   [![](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">atribuição de retargeting da AppsFlyer</Anchor>.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#deep-linking-com-srns">usuários de deep link de SRNs como o Meta ads</Anchor>.

#### Atribuição de campanhas de retargeting do WhatsApp

A AppsFlyer permite a mensuração de campanhas de marketing no WhatsApp, que são usadas para reengajamento, via atribuição de deep linking tanto no iOS quanto no Android.

Quando o **reengajamento** está ativado tanto no **nível de integração** quanto no **nível do aplicativo**, essas campanhas são mensuradas automaticamente, sem exigir nenhuma configuração adicional.

Nos seus dados de atribuição, o campo **canal** exibirá **"WhatsApp"** para esses tipos de campanha.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Compartilhamento avançado de dados">

Quando o **compartilhamento avançado de dados** está ativo, o Meta recebe postbacks e eventos com identificadores a nível de dispositivo para todos os dispositivos, incluindo dispositivos que não tornaram seu advertising ID (IDFA) disponível.

Além disso, quando o **compartilhamento avançado de dados** está ativado, a AppsFlyer atribui esses eventos. Quando desativado, apenas postbacks e eventos de dispositivos com um IDFA são enviados e atribuídos.

Esse método atribui instalações por click-through e view-through no iOS, bem como reengajamentos de deep linking, para dispositivos com opt-out único e duplo. A atribuição se baseia na atribuição de último toque com uma janela de atribuição máxima de 24 horas.

> 📘 **Nota**
>
> Se a opção **compartilhamento avançado de dados** estiver ativa e não estiver recebendo atribuições do Meta, verifique se os eventos compartilhados cumprem os critérios de elegibilidade do Meta. Consulte a <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">documentação Meta</Anchor>.

</Accordion>

<div id="advanced_matching_data_sharing" />

<Accordion title="Compartilhamento de dados de correspondência avançada">

Quando o **compartilhamento de dados de correspondência avançada** está ativado, os campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash, sobrenome com hash e ID de login do Facebook, são compartilhados com a Meta se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

</Accordion>

<div id="use-deep-links-in-meta-ads-campaigns" />

<Accordion title="Usar deep links em campanhas do Meta Ads">

Ao executar campanhas do Meta Ads, você pode usar deep links para enviar usuários diretamente para uma página ou experiência específica in-app. As seções abaixo descrevem como configurar o Deep linking da AppsFlyer no Meta Ads

Antes de selecionar um objetivo de campanha, verifique se o seu aplicativo usa um dos seguintes formatos compatíveis de deep link (DL):

* AppsFlyer OneLink, se o aplicativo tiver integração com Universal Links ou Android App Links
* Links universais da Apple
* Android App Links
* Esquemas URI personalizados
* App Links do Facebook

A tabela abaixo descreve quais objetivos de campanha do Meta Ads são compatíveis com deep links diretos e deep links diferidos (DDL), além das instruções de configuração e limitações de cada um.

| Objetivo de campanha | Deep linking | Deep link diferido (DDL) | Configuração | Limitações e pré-requisitos |
| --- | --- | --- | --- | --- |
| Promoção de aplicativos / instalações | Com suporte. | Com suporte. | Insira a URL de DDL no campo **Deferred Deep Link** no nível do anúncio, na seção **Destination**. | <ul><li>No iOS, o DDL é compatível apenas com <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-aggregate-event-measurement-aem-for-ios">apps com AEM habilitado</Anchor> ou apps com consentimento duplo (Meta + App)</li><li>O DDL exige o SDK do Facebook para iOS e Android.</li></ul> |
| Vendas | Com suporte. | Não suportado | Configure no nível do conjunto de anúncios em **Conversion** ou use as configurações do catálogo. Se necessário, você pode substituir os deep links do catálogo por uma URL de site. | <ul><li>Requer que **Enable Install Tracking** esteja ativo.</li><li>O destino deve ser um app mobile.</li></ul> |
| Tráfico | Com suporte. | Não suportado | Configure no nível do conjunto de anúncios em **Conversion**. Oferece suporte a fallbacks para a App Store ou um site. | <ul><li>Requer que **Enable Install Tracking** esteja ativo.</li></ul> |
| Awareness | Com suporte. | Não suportado | O nome ou ID exclusivo de cada evento, conforme definido no Meta Ads As configurações de mapeamento possíveis são: | <ul><li>Requer que **Enable Install Tracking** esteja ativo.</li></ul> |
| Leads | Com suporte. | Não suportado | Configure ao nível do conjunto de anúncios em **Conversão**. | <ul><li>Requer que **Ativar rastreamento de instalação** esteja ativo.</li></ul> |

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">Guia do OneLink</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Crie um link do OneLink para as suas campanhas</Anchor>

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Cumprir com a Lei de Privacidade do Consumidor da Califórnia (CCPA)">

O cumprimento dos regulamentos de privacidade da CCPA limita os dados provenientes de usuários do Meta ads com sede na Califórnia, EUA.

**Para permitir a conformidade com a CCPA:** Ative a opção **Limitar o uso de informações pessoais dos usuários pelo Meta Ads (CCPA)** na aba **Integração**.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">as leis de proteção de dados</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Registro de receita de anúncios">

[![](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Se seu aplicativo usa Audience Network Ad Revenue do Meta para monetização de anúncios, é possível registrar suas receitas do Meta ads na AppsFlyer. É possível, com ou sem os dados de receitas de compras in-app, ter uma **visão completa das receitas de seus usuários**.

#### Registrar a receita de anúncios do Audience Network do Meta

1. Na aba **Receita de anúncios** , ative **Obter dados de receita de anúncios**.
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.
   * Receita atribuída**: Ou seja, receita com base na fonte de aquisição do usuário.  
     Configure a **Fonte do evento**, que é o evento que representa seu modelo de receita de anúncios da melhor forma possível. Por exemplo, se sua receita for baseada em impressões, é recomendável enviar à AppsFlyer um evento ad\_viewed. O melhor evento pode ser configurado separadamente para cada plataforma de monetização. No entanto, também é possível usar o evento `af_app_opened`. Nesse caso, a receita de anúncios é atribuída para cada vez que o usuário abrir o aplicativo.**
   * **Dados agregados de receita de monetização**: Receita baseada na fonte do anúncio.
3. O evento **receita de anúncios** é exibido. É um campo somente de leitura, que apresenta o novo evento de receita de anúncios chamado [source event]\_monetized (por exemplo, Ad\_Watched\_Monetized, conforme exibido abaixo). O evento de receita de anúncios é apresentado no dashboard como um evento adicional.
4. Clique em **Conectar ao Meta ads** para ativar a coleta da receita de anúncios do Audience Network do Meta. Faça login com suas credenciais do Meta ads para autorizar a receita de anúncios do Audience Network.
5. Insira o **Audience Network App ID (**[**Facebook App ID**](/docs/meta-ads-integration-setup#facebook-app-id)). Obtenha-o no Meta Audience Network.
   * Obtenha o [Facebook App ID](/docs/meta-ads-integration-setup#facebook-app-id).
   * Copie o ID no campo **Audience Network App ID** na AppsFlyer.
6. Clique em **Salvar receita de anúncio**.

</Accordion>

<div id="permissions" />

<Accordion title="Authorization: Bearer">

Ative o Meta Ads para executar várias ações e acessar seus dados de acordo com as permissões disponíveis.

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">conceder permissões a parceiros integrados</Anchor>.

</Accordion>

## Aggregate Event Measurement (AEM) para iOS

A AppsFlyer oferece suporte à solução de AEM do Meta ads. Essa solução ajuda a otimizar as conversões iOS e os eventos in-app, atribuindo também reengajamentos iOS no Meta ads.

## Resolução de problemas de integração do Meta ads

Se você concluiu a integração básica e ainda não consegue ver os resultados do Meta ads no dashboard da AppsFlyer, verifique se você tem novas instalações do Meta ads desde a integração.

Se sim, consulte os principais motivos abaixo para resolver o problema:

<div id="no-idfa-collection" />

<Accordion title="Nenhuma coleta de IDFA">

Conforme indicado no Guia de integração do SDK - iOS, você deve adicionar o AdSupport.framework ao seu projeto para que a coleta do IDFA ocorra. Verifique o relatório de dados brutos de instalações para ver se a coluna do IDFA está vazia ou não. Recomenda-se que seu aplicativo colete IDFA no caso de aplicativos iOS e GAID no caso de aplicativos Android.  
A partir do iOS 14.5, será necessário exibir o prompt da ATT da Apple e obter o consentimento do usuário antes de poder coletar o IDFA.

**Atenção:** A atribuição da SKAdNetwork não é afetada pela disponibilidade do IDFA. No entanto, certifique-se de ativar a opção de campanha do iOS 14 no Meta ads ao configurar campanhas do iOS 14.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="Facebook App ID incorreto">

O Facebook App ID foi configurado incorretamente na AppsFlyer.  
Verifique se o App ID está correto e se ele corresponde ao valor exibido no dashboard do Meta ads.  

Observação - você também pode usar a <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">Graph API do Facebook</Anchor> para validar o seu Facebook App ID.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Status do aplicativo no Meta ads">

O aplicativo deve ser definido no Meta ads como **Live** em vez de **In development** para que a atribuição funcione.

[![](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Tipo incorreto de campanha do Meta ads">

Certifique-se de que a campanha do Meta ads seja para **anúncios de instalação de aplicativos mobile** ou **engajamento no aplicativo mobile**. Para outros objetivos de campanha, para mensurar instalações mobile, o anunciante deve <Anchor target="_blank" href="/marketers/pt/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads">selecionar a opção de **registrar eventos do aplicativo**</Anchor> ao configurar sua campanha do Meta ads.

<div id="aem-attribution-is-not-working" />

<Accordion title="A atribuição AEM não está funcionando">

Se a opção **compartilhamento avançado de dados** estiver ativa e não estiver recebendo atribuições do Meta, verifique se os eventos compartilhados cumprem os critérios de elegibilidade do Meta. Consulte a [documentação do Meta](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Instalação de aplicativos com o Meta ads">

Ao configurar uma campanha de instalação de aplicativo no Meta ads, é possível selecionar o aplicativo em uma lista suspensa ou colar a URL completa da loja no aplicativo. Enquanto ambas as opções funcionam no Meta ads, o segundo método falha na atribuição da AppsFlyer.

Configuração correta – a atribuição funciona.

[![](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)

Configuração incorreta – falha na atribuição.

[![](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

### Atualizações do iOS 14 para Meta ads

A AppsFlyer assegura de que a nossa integração de MMP com o Meta ads sempre implemente o sinalizador *Advertiser Tracking Enabled*. Ou seja, você não precisa executar nenhuma ação na AppsFlyer. Essas informações são oferecidas de acordo com a lista de fevereiro de 2021 de diretrizes do iOS 14 para aplicativos do Meta ads.

> 📄 **Veja também**
>
> * Para considerações sobre o iOS 14, consulte <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads">Interoperação SKAN do Meta ads</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/configuring-meta-campaign-management-partners">Configuração de Meta campaign management partners</Anchor> (<Anchor target="_blank" href="/marketers/pt/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo)</Anchor> / <Anchor target="_blank" href="/marketers/pt/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/pt/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/pt/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=guia-de-configura%C3%A7%C3%A3o-do-meta-ads 01H7YJVNMSZ4WG4HWBZF648HZN=guia-de-configura%C3%A7%C3%A3o-do-meta-ads basic-facebook-attribution-setup=configura%C3%A7%C3%A3o-b%C3%A1sica-de-atribui%C3%A7%C3%A3o-do-meta-ads 01H7YJVNMTFW076FAJZGJWT4R9=configura%C3%A7%C3%A3o-b%C3%A1sica-de-atribui%C3%A7%C3%A3o-do-meta-ads h_01JXYJW7AFB53PY7WHGM05HDMH=create-and-retreive-facebook-app-id h_01JKX03GC8ZSMGCSX84381QW0A=enable-meta-ads-device-level-data h_01JYPKG2RH3R08604V7B3NC5WQ=importante h_01JXYHEFW19DJXXXRNN186E07B=set-the-meta-ads-active-integration %5Boptional%5D-configure-recommended-settings=optional--configure-recommended-settings h_01JXYHEFW15E6K39JY2VBCN79E=optional--configure-recommended-settings advanced-facebook-attribution-setup=configura%C3%A7%C3%A3o-avan%C3%A7ada-de-atribui%C3%A7%C3%A3o-do-meta-ads 01H7YJVNMTHF800PD5CEWPFS49=configura%C3%A7%C3%A3o-avan%C3%A7ada-de-atribui%C3%A7%C3%A3o-do-meta-ads h_01JKX03GC8B4VKC6KJT4CZ9VT8=getting-userlevel-data-for-android-installs h_01JKX2BE00WYHMJ3RX1FK8DQV5=google-play-install-referrer-api meta-install-referrer=install-referrer-do-meta h_01JKX2BNRDHHNJCN257H3QBZ65=install-referrer-do-meta h_01JKX03GC8JRZSD13TVDDM1MWE=nota campaign-attribution-fields-available-via-the-referrer=campos-de-atribui%C3%A7%C3%A3o-de-campanha-dispon%C3%ADveis-por-meio-do-referrer h_01JKX2CF8RE4T5R3V83FS1PBQR=campos-de-atribui%C3%A7%C3%A3o-de-campanha-dispon%C3%ADveis-por-meio-do-referrer h_01JKX03GC9BG4GFDKR7JHG31BQ=nota-1 meta-install-referrer%E2%80%94faq=install-referrer-do-meta--perguntas-frequentes h_01JKX2DSY85X6570AHYKHM34KS=install-referrer-do-meta--perguntas-frequentes encrypted-data-from-google-play-referrer-api-or-meta-install-referrer=dados-criptografados-da-google-play-referrer-api-ou-do-install-referrer-do-meta h_01JKX2E4A44QHKADG4S8ZM9KC5=dados-criptografados-da-google-play-referrer-api-ou-do-install-referrer-do-meta 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=observa%C3%A7%C3%B5es cost-data-sync-status=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo 01H7YJVNMTRQAYG7TY29AX4MZS=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=nota-2 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution whatsapp-retargeting-campaign-attribution=atribui%C3%A7%C3%A3o-de-campanhas-de-retargeting-do-whatsapp h_01KBZ2CAGX18ZZPXQGMPTEPSCP=atribui%C3%A7%C3%A3o-de-campanhas-de-retargeting-do-whatsapp 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01JDH9Y65409Y5E162NWJA25E3=nota-3 h_01KPK96J1G0BY3PPEBN9RB005V=use-deep-links-in-meta-ads-campaigns h_01KPK96J1GZE9ZHQB5NHFCVAG6=consulte-tamb%C3%A9m h_01JKTYRMD70ZGN31FSQ7BXF1HB=comply-with-california-consumer-privacy-act-ccpa 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=registrar-a-receita-de-an%C3%BAncios-do-audience-network-do-meta 01H7YJVNMV1TTHKMMX4TFB2BF3=registrar-a-receita-de-an%C3%BAncios-do-audience-network-do-meta 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=aggregate-event-measurement-aem-para-ios 01H7YJVNMVGFYMHE5FACTD9NS0=aggregate-event-measurement-aem-para-ios meta-ads-integration-troubleshooting=resolu%C3%A7%C3%A3o-de-problemas-de-integra%C3%A7%C3%A3o-do-meta-ads 01H7YJVNMVCAQ6ETKBGCAM31B9=resolu%C3%A7%C3%A3o-de-problemas-de-integra%C3%A7%C3%A3o-do-meta-ads 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign h_01JKTYRMD7YPGJRZXR4Y66BAHG=aem-attribution-is-not-working 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install ios-14-updates-relating-to-facebook=atualiza%C3%A7%C3%B5es-do-ios-14-para-meta-ads 01H7YJVNMVQP5PR6XDHTCPXVDC=atualiza%C3%A7%C3%B5es-do-ios-14-para-meta-ads h_01HDP0Y4CZBZEK5VZ6FG3T31JB=veja-tamb%C3%A9m" />
