---
title: Eventos in-app – Visão geral
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-08T00:07:15Z'
  id: 115005544169
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/115005544169
---
> **At a glance:** registre eventos pós-instalação feitos no aplicativo (como login, cadastro ou compra in-app) atribuídos a fontes de mídia e campanhas.

<div id="why-record-in-app-events" />

## Por que registrar eventos in-app?

Os eventos in-app oferecem informações sobre o que está acontecendo no seu aplicativo e são a ferramenta ideal para determinar o valor dos usuários do app e a **qualidade do tráfego proveniente de diferentes fontes de mídia**. O registro de eventos in-app ajuda você a mensurar indicadores-chave de performance (KPIs), como ROI (Return on Investment) e LTV (Lifetime Value).

Quando os usuários realizam cadastros, concluem tutoriais, adicionam itens ao carrinho de compras ou finalizam compras, os dados de eventos in-app podem gravar os eventos detalhadamente. A implementação de eventos in-app é obrigatória para todos os fins de análise pós-instalação.

<div id="about-in-app-events" />

## Sobre eventos in-app

Um evento in-app inclui um nome de evento e pode incluir parâmetros de evento. Quando você adiciona parâmetros de evento a um evento in-app, ele é denominado como um evento avançado no aplicativo. Os parâmetros do evento oferecem mais contexto e informações sobre o evento que ocorre. Por exemplo, embora ele seja útil para saber que um usuário fez uma reserva de hotel, os parâmetros do evento podem oferecer detalhes como o tipo de compra, destino e receita.

<Image align="center" alt="travel.png" src="https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png" />

<div id="tip" />

> 👍 **Dica**
>
> Quer saber mais sobre eventos in-app? Confira esse <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">curso curto e informativo</Anchor> no Portal de Aprendizado da AppsFlyer.

<div id="predefined-and-custom-events" />

### Eventos predefinidos e personalizados

Os eventos in-app que você deseja enviar exigem que o desenvolvedor implemente o código quando aplicável ao seu app. Os nomes de eventos e os parâmetros de eventos são classificados da seguinte forma:

* **Predefinidos**: são nomes de eventos e parâmetros de eventos que costumam ser usados entre aplicativos diferentes. É altamente recomendável usar <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#nomes-de-eventos-predefinidos">nomes de eventos predefinidos</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#parâmetros-de-eventos-predefinidos">parâmetros de eventos</Anchor> tanto quanto possível, pelos seguintes motivos:
  * A nomenclatura predefinida permite o mapeamento automático de eventos para parceiros.
  * Se a AppsFlyer decidir alterar o nome de qualquer parâmetro de evento ou evento, sua implementação será compatível com versões anteriores.
* Personalizado: são nomes de eventos e parâmetros que você define para cenários de usuário específicos que ocorrem no aplicativo. Você pode usar qualquer nome de evento personalizado ou string de nome de parâmetro, mas lembre-se que eventos personalizados precisam de manutenção por parte do desenvolvedor. Veja [dicas](/docs/in-app-events-overview#tips) e [limitações](/docs/in-app-events-overview#limitations).

<div id="revenue-in-in-app-events" />

## Receita em eventos in-app

Entenda como enviar eventos de receita para a AppsFlyer e mapear os parâmetros que os eventos incluem. Vale observar que, com uma assinatura do ROI360, você obtém dados de custo e receita mais precisos e atualizados (incluindo dados de receita de compras in-app, assinaturas e anúncios). <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-cost-and-revenue-data">Saiba mais sobre o ROI360</Anchor>

<Accordion title="Event revenue">

`af_revenue` é o parâmetro padrão para reportar receita. A receita enviada em `af_revenue` alimenta todas as métricas de receita nos produtos da AppsFlyer (dashboards, LTV, cohort, ROAS, ROI) e é incluída nos postbacks para parceiros. Use-o sempre com eventos in-app que representam a receita real segundo a lógica do seu negócio.

Se você também quiser reportar receita com sua própria lógica aplicada, por exemplo, após taxas da loja de aplicativos e deduções de impostos, também poderá enviar `af_net_revenue`. Isso é um complemento ao `af_revenue`, não um substituto. Veja [Receita líquida](#net-revenue) abaixo.

* <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#record-revenue">Registrar a receita no SDK</Anchor>
* Registrar a receita na Unity

Você também pode registrar uma receita negativa caso um usuário cancele uma compra ou emitir um reembolso. Para registrar a receita negativa, basta acrescentar o sinal de menos (-) ao valor da receita que você enviou para `af_revenue`

O valor da receita deve conter apenas números (e ponto decimal, se necessário):

* **Não** inclua outros caracteres ou formate o valor da receita de outra forma. Isso significa sem vírgulas, símbolos monetários (por exemplo, $), caracteres especiais ou texto.
* A AppsFlyer fornece o valor da receita com **precisão de até cinco casas decimais**.
* O intervalo desse valor deve estar entre -1.000.000 a 1.000.000 em dólares ou o equivalente na moeda original. Valores fora dessa faixa estão incluídos em relatórios de dados brutos, mas não em relatórios agregados.
* Exemplo: 1234,56
* Quando a receita é enviada como string, o valor entre aspas deve ser válido. Por exemplo: "1234,56".

<div id="note" />

> 📘 **Importante!**
>
> A AppsFlyer apresenta a receita exata enviada pelo SDK. Isso não inclui cálculos de VAT ou comissões da loja de aplicativos, etc., a menos que tenham sido incluídos pelo desenvolvedor no lado do SDK antes de ser enviado para a AppsFlyer. Se você quiser reportar a receita após essas deduções, envie-a também em `af_net_revenue` (consulte [Receita líquida](#net-revenue)).

`af_currency` representa a moeda informada em `af_revenue` (ou `af_price`). Se estiver faltando `af_currency` nos parâmetros do evento, o AppsFlyer o envia com o valor padrão "USD".

Você pode usar `af_price` como um parâmetro monetário que não é contado como receita (como em um evento de “Adicionar ao carrinho”). Esse parâmetro se refere ao preço do item individual. O valor total de todas as compras aparece no parâmetro `af_revenue`.

</Accordion>

<Accordion title="Net revenue">

O parâmetro `af_net_revenue` oferece uma forma opcional e adicional de reportar receita quando você quiser aplicar sua própria lógica ao valor da receita, por exemplo, receita após taxas da loja de aplicativos, deduções de impostos, margem bruta ou taxas de serviço.

`af_net_revenue` **não substitui** `af_revenue`. Continue enviando `af_revenue` normalmente e adicione `af_net_revenue` ao mesmo tempo quando quiser fazer o reporte líquido.

* A moeda segue `af_currency` (USD por padrão), de forma semelhante a `af_revenue`.
* Como não há uma constante predefinida do SDK para `af_net_revenue`, você deve enviá-lo como um parâmetro personalizado com a chave `af_net_revenue`.
* A receita líquida alimenta as métricas Net (Receita líquida, ROI líquido, ROAS líquido, ARPU líquido e lucro líquido) em <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#metrics">My Dashboards</Anchor>.

<div id="note-1" />

> 📘 **Atenção**
>
> Se você usar <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue">receita da loja ROI360</Anchor>, `af_net_revenue` será preenchido automaticamente para eventos de compra in-app e assinatura, portanto você não precisa enviar `af_net_revenue` para esses eventos. A receita líquida é igual à receita bruta menos as taxas da loja de aplicativos e os impostos.

</Accordion>

<Accordion title="Moeda da receita">

É importante entender como a AppsFlyer lida com configurações e conversão de moeda.

A AppsFlyer lida com a diferença entre a moeda definida no aplicativo e e a moeda dos eventos in-app usando a conversão de moeda.

<Image align="center" alt="revenue_normalization_flow.png" src="https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png" />

O diagrama acima ilustra o seguinte processo:

1. Os eventos in-app são enviados - cada evento com uma moeda diferente
2. A AppsFlyer padroniza todas as moedas para USD
3. A AppsFlyer processa os dados de receita
4. Os dados de receita no dashboard são exibidos de acordo com as configurações de moeda no aplicativo
5. A AppsFlyer preenche os dados de receita em relatórios de dados brutos tanto na moeda do evento como na moeda da configuração do aplicativo

A AppsFlyer usa <Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor> para a conversão de moeda. A taxa de câmbio é atualizada de hora em hora. A taxa de câmbio é atualizada a cada hora Sempre que a AppsFlyer faz uma conversão de moeda, ela usa a taxa de câmbio da atualização da última hora.

<div id="currency-conversion" />

#### Conversão de moeda

<span id="h_01HDBZW9XERK3VN1GS8GHM911W"></span>**Exemplo**

Nas suas configurações do aplicativo, você configura a sua moeda para GBP. Um usuário da França compra um produto no seu app. O preço é apresentado em EUR (€). O evento in-app que você envia para a AppsFlyer tem essa aparência:

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE,200);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR"); AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
```

Neste caso, a AppsFlyer converte a receita de EUR para USD e depois, converte para GBP. Vamos assumir que a taxa de câmbio é de 1 euro = 1,13 dólares. Assim, 200 euros se transformam em 226,85 dólares. Em seguida, a AppsFlyer faz a conversão de USD para GBP. GBP. Vamos assumir que a taxa de câmbio é de 1 dólar = 0,78 libras. Assim, 226,85 dólares se transformam em 176,92 libras.

<div id="currency-display" />

#### Exibição da moeda

<Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-currency">A moeda é definida nas configurações do aplicativo</Anchor>. A moeda que você define nas configurações do aplicativo é a moeda que aparece no dashboard. Não importa a moeda que você envia nos eventos in-app, a receita no dashboard é sempre apresentada na moeda que você definiu nas configurações do aplicativo.

<span id="h_01HDBZW9XEQNG1RDH7A8H002ZD"></span>**Exemplo**

Por exemplo, vamos supor que você enviou eventos in-app com moedas diferentes daquela definida nas configurações do aplicativo ou sem definir moeda como um todo. Nesse exemplo, a moeda nas configurações do aplicativo está definida para **GBP**.

Você envia três eventos in-app para a AppsFlyer.

1. O Evento A tem uma receita de **234** e **GBP** como moeda.
2. O Evento B tem uma receita de **171** e **EUR** como moeda.
3. O Evento C tem uma receita de **171**, mas não tem **nenhuma moeda** especificada.

<div id="revenue-data-in-the-dashboard" />

#### Dados de receita no dashboard

A receita que aparece no dashboard é o **valor convertido** da moeda do evento in-app para USD e depois para a moeda definida nas configurações do aplicativo.

Se nenhuma moeda for especificada no evento, a **AppsFlyer usa USD como padrão**. O dashboard exibe o evento e a receita da seguinte forma:

| Eventos in-app | Usuários únicos | Número de ações | Resultados |
| --- | --- | --- | --- |
| E | 1 | 1 | £234 |
| B | 1 | 1 | £149,4 - convertido de EUR para USD e depois para GBP. |
| C | 1 | 1 | £132,9 - por padrão, o valor é definido como USD, já que nenhuma moeda foi especificada. Convertido diretamente de USD para GBP. |

<div id="revenue-data-in-raw-data-reports" />

#### Dados de receita em relatórios de dados brutos

Se você definir a moeda como **GBP** nas configurações do aplicativo, mas enviar eventos com moedas diferentes, os relatórios de dados brutos mostram a receita tanto na moeda das configurações do aplicativo como na moeda dos eventos in-app.

Se você definir a moeda como **GBP** nas configurações do aplicativo, mas envia eventos in-app sem moeda, o relatório de dados brutos exibe a receita na moeda das configurações do aplicativo e em dólares.

O relatório de dados brutos de eventos in-app mostra o evento e a receita da seguinte forma:

| Evento | Receita do evento | Moeda da receita do evento | Receita do evento em GBP |
| --- | --- | --- | --- |
| E | 234 | GBP | 234 |
| B | 171 | EUR | 149,4 - convertido de EUR para USD e depois para GBP. |
| C | 171 | USD | 132,9 por padrão usa USD, pois nenhuma moeda é especificada. Convertido diretamente de USD para GBP. |

</Accordion>

<div id="sending-events" />

## Enviar eventos

Há várias formas de enviar eventos in-app para a AppsFlyer:

* <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">**SDK da AppsFlyer:**</Anchor> essa é a forma mais comum de enviar eventos. Você pode enviar eventos avançados in-app que gravam ações do usuário no aplicativo usando a API de eventos in-app da AppsFlyer no nível do SDK.
* <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">**API Server-to-Server (S2S):**</Anchor> Use a API Server-to-Server (S2S) para enviar eventos que ocorrem fora do app mobile, diretamente para a AppsFlyer. Por exemplo, se você tiver um usuário ativo na web e em outras plataformas mobile, pode gravar os eventos nas duas fontes e atribuí-los ao mesmo usuário na AppsFlyer. Pode ser um evento in-app ou outros eventos, como eventos de site, eventos de call center ou compras em sua loja física.
* <Anchor target="_blank" href="/marketers/pt/docs/legacy-receipt-validation-for-in-app-purchases">**Validação de recibos**</Anchor>: esse é um mecanismo seguro onde a plataforma de pagamento, como Apple e Google, valida que a compra in-app ocorreu conforme relatado. A validação de compras é a principal ferramenta para evitar eventos de receita fraudulentos. Ela também ajuda na visualização da receita real e filtra compras incompletas no aplicativo.
* <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-for-hybrid-apps">**Apps híbridos**</Anchor> esses aplicativos combinam visualizações nativas e conteúdo HTML e também podem registrar eventos in-app. No entanto, como o SDK só pode enviar eventos do lado nativo, os desenvolvedores precisam encaminhar todos os dados do evento para o código nativo.

<div id="setting-up-in-app-events" />

## Configurando eventos in-app

O processo de configuração de eventos in-app requer que o profissional de marketing e o desenvolvedor trabalhem juntos da seguinte forma:

| Passo | Cargo | Função | Detalhes |
| --- | --- | --- | --- |
| 1 | Marketer | Determine os eventos in-app que você deseja mensurar. [Defina](/docs/in-app-events-overview#defining-an-inapp-event) e comunique os <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#nomes-de-eventos-predefinidos">nomes do evento</Anchor> e os <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#parâmetros-de-eventos-predefinidos">parâmetros do evento</Anchor> ao seu desenvolvedor. | É recomendado começar com 3 a 5 eventos que podem ser usados como KPIs para mensurar a qualidade de seus usuários (por exemplo, compras, cadastro e compartilhamento). Os parâmetros de evento são opcionais e você pode usar qualquer parâmetro de evento com qualquer nome de evento.<br /><br />Consulte [Eventos recomendados por verticais de negócios](/docs/in-app-events-overview#recommended-events-by-business-vertical) para eventos in-app típicos. |
| 2 | Desenvolvedor | Implemente o código no seu app, quando aplicável. | A documentação do desenvolvedor está <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">aqui</Anchor>. |
| 3 [Opcional] | Marketer | Trabalhe com o desenvolvedor para definir o <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">campo de Customer User ID (CUID)</Anchor>. | Esse campo ajuda a enriquecer os dados de eventos in-app, fazendo referência cruzada entre os dados de atribuição da AppsFlyer e seus outros dados, usando o CUID como chave. |
| 4 [Opcional] | Marketer | <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">Mapeie eventos</Anchor> para parceiros relevantes no dashboard. | Essa é uma tarefa contínua, dependendo dos parceiros com os quais você possui integração. |

<Accordion title="Definindo seus eventos in-app">

Depois de determinar os eventos in-app que você deseja mensurar, use nosso <Anchor target="_blank" href="https://evgen.appsflyer.com/">gerador de eventos in-app</Anchor> para definir os eventos e parâmetros da seguinte forma:

1. Selecione o nome de evento mais adequado ao cenário que você deseja registrar.
2. Selecione os parâmetros do evento que você deseja associar ao evento. Escolha parâmetros que oferecem um contexto adicional ao evento e enriquecem os dados.
3. Faça o download do arquivo completo do gerador de eventos in-app e compartilhe-o com seu desenvolvedor.

<span id="h_01HDBZW9XFN2B8AC18VW99G8Z6"></span>**Exemplo**

Um profissional de marketing de um aplicativo de eCommerce quer registrar o tipo de conteúdo que os usuários visualizam para entender melhor quais categorias são as mais populares e conectar as visualizações de produtos às vendas de produtos.

A tabela a seguir mostra um exemplo da estrutura de eventos que o profissional de marketing passa para o desenvolvedor:

<table><thead><tr><th>Nome do evento</th><th>Parâmetros do evento</th><th>Valores dos parâmetros</th><th>Quando o evento é acionado?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_preço</td><td>Preço do produto</td><td rowspan="3"><span>Quando um usuário visualiza uma determinada página de detalhes de um produto</span></td></tr><tr><td><span>af_content_type</span></td><td><span>Nome da categoria de produto, por exemplo: sapatos</span></td></tr><tr><td><span>af_content_id</span></td><td><span>ID do produto, por exemplo, SKU</span></td></tr></tbody></table>

</Accordion>

<Accordion title="Eventos recomendados por vertical">

A tabela a seguir oferece links para artigos que incluem os exemplos e fluxos de eventos in-app típicos que sugerimos que sejam registrados por vertical.

| Vertical de negócios | Título do artigo |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events">Eventos recomendados para apps de jogos</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events">Eventos recomendados para apps de eCommerce</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-entertainment-app-events">Eventos recomendados para apps de entretenimento</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-finance-and-banking-app-events">Eventos recomendados para apps de finanças e bancos</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-p2p-lending-app-events">Eventos recomendados para apps de empréstimos P2P</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-online-education-app-events">Eventos recomendados para apps de educação online</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-ride-hailing-app-events">Eventos recomendados para apps de transporte</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-flight-booking-app-events">Eventos recomendados para apps de reserva de voos</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events">Eventos recomendados para apps de reserva de hotéis</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-healthcare-app-events">Eventos recomendados para apps de saúde</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-telecommunication-app-events">Eventos recomendados para apps de telecomunicações</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-ewallet-app-events">Eventos recomendados para apps de eWallet</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/pt/docs/recommended-sports-betting-events">Eventos recomendados para apostas esportivas</Anchor> |

</Accordion>

<Accordion title="Visualizar dados de eventos in-app">

Eventos in-app são atribuídos à fonte de mídia responsável pela instalação ao longo da vida útil do usuário. Os dados de eventos são apresentados como <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">dados de Lifetime Value ou de Atividade</Anchor>.

Você pode visualizar os dados de eventos in-app nos seguintes locais:

* Página de visão geral do dashboard: Exibe a performance de aquisição de usuários (UA) de LTV em tempo real. **Observação**: Isso inclui a receita dividida entre usuários orgânicos e não orgânicos, reportada por meio de eventos in-app, e a receita de retargeting que recebe <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">dupla atribuição</Anchor>.
* Página de eventos: exibe a performance do LTV de evenos in-app entre fontes de mídia
* <Anchor target="_blank" href="/marketers/pt/docs/activity-dashboard">Página de atividade</Anchor>: exibe as atividades in-app para o intervalo de datas selecionada.
* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatório de dados brutos de eventos in-app</Anchor>: Fornece dados de atividades, ou seja, uma lista cronológica das ações efetuadas por toda a base de usuários. Esse relatório inclui valores de parâmetros de eventos, por exemplo:

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Observação: o relatório de dados brutos é um recurso premium.

<div id="note-2" />

> 📘 **Nota**
>
> Os valores dos parâmetros de eventos in-app estão disponíveis exclusivamente em <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#eventos-in-app">relatórios de dados brutos de eventos in-app</Anchor>. Eles não são exibidos nos dashboards de Visão Geral, Eventos ou Atividade, nem nos relatórios de dados agregados.

</Accordion>

<Accordion title="Dicas">

Ao definir nomes e parâmetros de eventos no aplicativo, lembre-se:

* Para garantir a consistência dos dados nos relatórios de dados brutos, recomendamos definir e utilizar os mesmos nomes e estruturas de eventos in-app em todas as plataformas.
* Use um número mínimo de eventos para facilitar a comparação da qualidade dos usuários vindos de diferentes fontes.
* **É importante garantir a privacidade dos seus usuários.** **Não preencha valores de eventos in-app com dados restritos que possam identificá-los diretamente**. **Por exemplo, endereço de e-mail, nome, número de identidade e, em alguns locais, código postal. Para mais informações sobre dados restritos, consulte a** <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">**política de privacidade dos serviços**</Anchor>.
* Observe que a AppsFlyer coleta o endereço de IP dos dispositivos durante os <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">engajamentos. Em algumas jurisdições ou cenários de uso, o endereço IP pode ser considerado informação de identificação pessoal (PII). Usamos o endereço de IP para derivar a ampla localização geográfica (cidade, bairro) do dispositivo, mas não o endereço específico. Se necessário, você pode optar por</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/apply-ip-masking-to-user-data">mascarar endereços de IP</Anchor> para que eles não apareçam nos relatórios de dados brutos.
* Eventos in-app são a única fonte de dados de receita na AppsFlyer. Você pode anexar um valor de receita específico a cada evento e visualizá-lo no dashboard do seu aplicativo. Para saber mais sobre os [parâmetros de monetização](/docs/in-app-events-overview#revenue-events), consulte a imagem [altrevenue\_data.pngalt](/docs/in-app-events-overview#revenue-events)  ![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)

</Accordion>

<Accordion title="Limitações">

Ao definir nomes e parâmetros de eventos no aplicativo, lembre-se:

* Recomendamos usar apenas caracteres alfa-numéricos minúsculos (a-z e 0-9) para seus nomes de eventos in-app. Os nomes de eventos diferenciam maiúsculas de minúsculas, o que significa que af\_purchase e af\_PURCHASE são dois eventos diferentes nos dados brutos. No entanto, em relatórios e dashboards agregados (por exemplo, Visão geral ou Eventos), apenas letras minúsculas são permitidas e, portanto, podem ser exibidos como um único evento.
* Há um limite de 300 eventos exclusivos por dia. <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">Saiba mais</Anchor>
* Os usuários exclusivos são contados somente para os primeiros 100 eventos após a instalação do aplicativo.
* Os nomes dos eventos não podem começar com esses caracteres: " = + -
* Os valores de evento não devem conter o caractere + , exceto em URLs codificadas ou codificadas conforme <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>.
* Os nomes de eventos não podem conter espaços vazios. Você pode usar espaços sublinhados (underline, ou traços baixos) antes ou depois do nome do evento.
* Os valores dos eventos não devem ultrapassar 2.000 caracteres para evitar serem abreviados em relatórios de dados brutos. Porém, se o evento for originado a partir do SDK, aconselhamos que você fique abaixo de 1.000 caracteres para garantir que o payload não seja truncado ao ser enviado na solicitação HTTP.
* Se você incluir a URL de referência como um valor de evento, ela deverá ser <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">codificada por URL</Anchor>.
* Os anúncios da Meta têm algumas limitações em relação a nomes de eventos e parâmetros. Leia sobre as limitações <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">aqui</Anchor>.

</Accordion>

<div id="faq" />

## Perguntas frequentes

A seção a seguir inclui várias perguntas frequentes sobre eventos in-app.

<Accordion title="Como faço para usar o parâmetro de receita?">

Você pode enviar valores de receitas com qualquer nome de parâmetro e evento. No entanto, para registrar a receita (incluindo [receita negativa](/docs/in-app-events-overview#revenue-events)) nos dados brutos e agregados da AppsFlyer, você deve usar o parâmetro `af_revenue`. Sempre use ele com eventos no aplicativo que representam a geração de receita real em sua lógica de negócios.

`af_currency` representa a moeda que é mencionada em `af_revenue` (ou `af_price`). Se estiver faltando `af_currency` nos parâmetros do evento, o AppsFlyer o envia com o valor padrão "USD". Para mais informações sobre o parâmetro `af_revenue`, consulte o [guia de atribuição de receita](/docs/in-app-events-overview#revenue-events).

Se você também quiser reportar receita com sua própria lógica aplicada, por exemplo, após taxas e impostos, envie `af_net_revenue` como um parâmetro personalizado junto com `af_revenue`. `af_net_revenue` não substitui `af_revenue`. Para mais informações, consulte [Receita líquida](#net-revenue).

</Accordion>

<Accordion title="Como a AppsFlyer atribui eventos?">

Os eventos in-app são atribuídos ao canal original da mídia da instalação do aplicativo.

Após a instalação de um aplicativo (primeira abertura do aplicativo), a AppsFlyer utiliza vários <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">métodos de atribuição</Anchor> para determinar a atribuição da instalação. Ao mesmo tempo, o SDK da AppsFlyer cria um novo e exclusivo <Anchor target="_blank" href="/marketers/pt/docs/about-device-identifiers#appsflyer-id">ID da AppsFlyer</Anchor>, que está associado com os detalhes de atribuição.

Cada evento in-app posterior, realizado pelo mesmo dispositivo no aplicativo, tem esse ID. Isso permite que a AppsFlyer atribua o evento ao canal de mídia original. Os anunciantes podem usar esse recurso para acompanhar a jornada completa do usuário no aplicativo.

Eventos de usuários que passaram recentemente por retargeting podem ter <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">dupla atribuição</Anchor>.

A AppsFlyer atribui eventos de instalações atribuídas como **orgânicas** quando:

* Os termos do canal da mídia [ditam a exclusão dos dados no nível de usuário](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* O usuário exclui os dados armazenados no dispositivo, forçando a criação de um novo ID da AppsFlyer.

</Accordion>

<Accordion title="Os eventos são registrados se um dispositivo estiver offline?">

Se um usuário iniciar um evento quando a conexão à internet estiver indisponível, a Appsflyer ainda pode realizar o registro do evento. Como funciona:

1. O SDK envia os eventos para os servidores da AppsFlyer e aguarda uma resposta bem-sucedida.
2. Se o SDK não receber uma resposta bem-sucedida, o evento será armazenado no cache.
3. Uma vez que a próxima resposta bem-sucedida é recebida, o evento armazenado é enviado para o servidor novamente.
4. Se houver vários eventos no cache, eles serão enviados para o servidor, um após o outro.

<div id="note-3" />

> 📘 **Nota**
>
> O cache do SDK pode armazenar até 40 eventos, o que significa que apenas os primeiros 40 eventos que acontecem offline são salvos. Tudo o que se segue, até a próxima resposta bem-sucedida, é descartado.
>
> A hora do evento que aparece nos dados brutos é a hora em que o evento é enviado à AppsFlyer após o dispositivo ficar online novamente. Não é a hora real do evento.

</Accordion>

<Accordion title="O que são eventos complexos e como faço para configurá-los?">

Eventos complexos in-app permitem o envio de vários eventos em uma única chamada de API. Eles são úteis quando você deseja ver várias ações de usuários intimamente relacionadas agrupadas, por exemplo adicionar vários produtos à cesta em uma única sessão.

Recomendamos usar o objeto `af_order_info` para enviar eventos in-app complexos para ad networks compatíveis. Para mais detalhes, consulte <Anchor target="_blank" href="/marketers/pt/docs/item-level-order-data-for-ad-networks-af-order-info">Dados de pedido em nível de item para ad networks (af\_order\_info)</Anchor>.

**Exemplo** (formato recomendado, um campo por array de itens):

```json
{
  "af_order_info": {
    "sku": ["ID1", "ID2", "ID3"],
    "revenue": [4.99, 9.99, 2.50],
    "qty": [1, 1, 2]
  }
}
```

Consulte <Anchor target="_blank" href="/marketers/pt/docs/item-level-order-data-for-ad-networks-af-order-info">Dados de pedido em nível de item para ad networks (af\_order\_info)</Anchor> para ver a lista completa de campos (até 7 campos por item) e o formato alternativo de um objeto por item.

Como alternativa, você ainda pode estruturar o evento usando `af_content` como um array JSON. Cada objeto na matriz deve incluir `id` e `quantity`. `af_content_list` é opcional e pode ser omitido.

<span id="h_01KSMX2ECGTDXQP3G9PZW1PFQD"></span>**Exemplo**

```json
{
  "af_revenue": 4.99,
  "af_currency": "USD",
  "af_order_id": "12345",
  "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
}
```

<div id="important" />

> 🚧 **Importante!**
>
> Se a string `af_content` exceder 1 000 caracteres, a AppsFlyer poderá enviar o evento para a Meta sem o parâmetro `fb_content`. Se `af_content_list` também estiver ausente nesse caso, a Meta não receberá dados de identificação do produto. Mantenha `af_content` abaixo de 1.000 caracteres para eventos que incluam muitos itens.

Para mais informações sobre eventos complexos no Meta Ads, consulte <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping#enviar-eventos-in-app-complexos-para-anúncios-da-meta">enviar eventos in-app complexos para o Meta Ads</Anchor>.

**Observação:** No <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#limitations">Audiences</Anchor> da AppsFlyer, arrays não são compatíveis em atributos de evento; apenas números ou strings.

</Accordion>

<Accordion title="Posso adicionar vários itens a uma única transação?">

Você pode adicionar vários itens a uma única transação. Em vez de valores únicos por parâmetro de evento, pode usar um array de itens descrevendo a transação, separados por vírgulas. O formato deve ser uma string JSON.

<span id="h_01HDBZW9XFB9TAT8W4CGNP1892"></span>**Exemplo**

Na mesma transação, o Sr. Smith compra duas camisas idênticas, um par de sapatos e um chapéu de uma loja online dos EUA. A sequência em que cada item é listado deve ser idêntica para cada.

```json
"{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
```

Os múltiplos itens são enviados como um array nos <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">postbacks</Anchor>. No momento, o Meta ads e o Twitter não conseguem processar parâmetros de array corretamente. Para ajudar com esse problema, a AppsFlyer soma o número de itens (`af_quantity`) em vez de enviá-lo para essas networks de autoatribuição (SRNs) como um array. No nosso exemplo, o Meta Ads receberia `af_quantity=4`.

<div id="notes" />

> 📘 **Observações**
>
> * No <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#limitations">Audiences</Anchor> da AppsFlyer, arrays não são compatíveis em atributos de evento; apenas números ou strings.
> * Vários itens podem ser usados com os seguintes eventos in-app:
>   `af_add_to_cart`, `af_add_to_wishlist`, `af_tutorial_completion`, `af_initiated_checkout`, `af_purchase`, `af_rate`, `af_spent_credits`, `af_content_view`, `af_travel_booking`, `af_update`

</Accordion>

<Accordion title="Como a AppsFlyer lida com a desduplicação de eventos?">

Temos um mecanismo de desduplicação de eventos in-app. Ele verifica todos os eventos in-app para ver se há um evento in-app idêntico que veio do mesmo appsflyer\_id menos de 10 segundos antecipadamente. Se tal evento for encontrado, o mecanismo remove a duplicação.

Dois eventos são considerados idênticos se os seguintes campos em ambos eventos forem iguais:

* Nome do evento
* Valor do evento
* ID da aplicação
* ID da AppsFlyer

<div id="note-4" />

> 📘 **Nota**
>
> A deduplicação funciona somente para eventos in-app que forem enviados do SDK.
>
> Os eventos in-app S2S não são desduplicados.

</Accordion>

<Accordion title="Por quanto tempo a AppsFlyer retém dados user-level e quais são as obrigações de exclusão?">

A AppsFlyer retém dados brutos user-level com base no tipo de integração e nos requisitos do parceiro. Os dados agregados podem ser retidos por até cinco anos.

Os períodos de retenção podem variar entre canais de mídia e métodos de entrega (por exemplo, Data Locker ou Pull API) e podem mudar devido a obrigações legais, contratuais ou de parceiros.

Após a exclusão, os eventos relacionados a usuários excluídos são exibidos como orgânicos. Dados agregados antigos não são alterados. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention#obrigações-de-retenção-e-exclusão-de-dados">Obrigações de retenção e exclusão de dados</Anchor>.

</Accordion>

<Accordion title="Preciso adicionar o parâmetro OS (sistema operacional) aos meus eventos?">

* O SDK do Android e o SDK do iOS adicionam automaticamente o parâmetro OS (sistema operacional).
* Para a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor>, desde 1 de julho de 2021, você deve enviar o parâmetro OS (sistema operacional) para aplicativos iOS. Se você não enviar esse parâmetro, os dados serão considerados como tendo vindo de um usuário do iOS 14.5, e isso afeta a forma como os <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">dados brutos são disponibilizados</Anchor>.

</Accordion>

<Accordion title="Como posso garantir a desduplicação de eventos no lado do parceiro?">

Se o mesmo evento também for carregado diretamente para a network (por exemplo, ao desenvolver internamente suporte para a API de conversão do parceiro), você pode garantir que o parceiro consiga desduplicar o evento, enviando um `event_id` semelhante tanto pela integração direta com a CAPI quanto pela AppsFlyer. Para fazer isso, inclua um campo chamado “af\_customer\_event\_id” no campo `event_value` e envie o mesmo valor no campo `event_id`, enviado diretamente ao parceiro pelo lado do anunciante.

Esta solução é compatível com `metaweb_int`, `tiktokweb_int`, `snapweb_int`, `pinterest_int`  e `pinterest_int`.

</Accordion>

<div id="see-also" />

## Veja também

* <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Configuração de postback de eventos in-app</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=por-que-registrar-eventos-in-app h_01HDBZW9XEBTY13MG4AN93RNCD=por-que-registrar-eventos-in-app about-inapp-events=sobre-eventos-in-app h_01HDBZW9XEBDSDA9T5X5B6KGTG=sobre-eventos-in-app h_01HDBZW9XE3Z40JE9576C4XSF4=dica predefind-and-custom-events=eventos-predefinidos-e-personalizados 01J9XGXGC7R9B19MMX4CQV7DAY=eventos-predefinidos-e-personalizados revenue-in-inapp-events=receita-em-eventos-in-app 01J9XGXGC990R3AG0R0XT9E5Y7=receita-em-eventos-in-app h_01M43GXKW5NCRE5MJG45EG9AYX=importante h_NETREVENUE0002=aten%C3%A7%C3%A3o currency-conversion=convers%C3%A3o-de-moeda h_01HDBZW9XEMGA5RAW0DBBPV3FQ=convers%C3%A3o-de-moeda currency-display=exibi%C3%A7%C3%A3o-da-moeda h_01HDBZW9XE85YC3JHG58YYAB8F=exibi%C3%A7%C3%A3o-da-moeda revenue-data-in-the-dashboard=dados-de-receita-no-dashboard h_01HDBZW9XEVWB9045N0YEVWE6Z=dados-de-receita-no-dashboard revenue-data-in-raw-data-reports=dados-de-receita-em-relat%C3%B3rios-de-dados-brutos h_01HDBZW9XEGYFD3W9FT1N3ZGQW=dados-de-receita-em-relat%C3%B3rios-de-dados-brutos sending-events=enviar-eventos h_01HDBZW9XFESG6MP9QF1XCJKE6=enviar-eventos setting-up-inapp-events=configurando-eventos-in-app h_01HDBZW9XF13AGRCN2HJ18RHS2=configurando-eventos-in-app 01JEWW8YB6A91VT8Z4PM9NCV00=nota faq=perguntas-frequentes h_01HDBZW9XF5H24H2HCJKKHCRTE=perguntas-frequentes h_01HDBZW9XFCDMKNWJ75AWHC2Y0=nota-1 h_01KSMX2ECGNMX39RD2F6ZHQEK4=importante-1 h_01HDBZW9XFJ68WSM3066NVRATS=observa%C3%A7%C3%B5es h_01HDBZW9XFWKN7W90PSVMX73FS=nota-2 h_01HDNZ708FN0N286R5HDQGMNGZ=veja-tamb%C3%A9m" />
