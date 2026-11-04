---
title: People Based Attribution x Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2026-08-18T00:24:01Z'
  id: 360001305617
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360001305617
---
> **Visão geral**: diferenças entre People Based Attribution (PBA) e Google Analytics

<div id="pba-compared-to-google-analytics" />

## PBA comparado ao Google Analytics

O PBA e o Google Analytics são soluções de análise e métricas de conversão da web. Cada um se concentra em diferentes aspectos da métrica. O PBA também oferece benefícios adicionais.

* O PBA é uma autoridade de atribuição independente e isenta que se concentra na métrica de atribuição. O PBA atribui conversões e receita a fontes de mídia e campanhas que trazem usuários ao seu site.
* O Google Analytics concentra-se mais em análise da web. O Google Analytics se concentra mais em análises da web, reunindo, analisando e agregando dados relacionados ao comportamento do usuário. Com o Google Analytics, você pode analisar, por exemplo, o comportamento do usuário, funis e eventos da web.

<div id="benefits-of-pba-over-google-analytics" />

### Benefícios do PBA em relação ao Google Analytics

Veja abaixo os benefícios do PBA em relação ao Google Analytics:

* O PBA inclui:
  * Métrica web-to-app. Essa métrica informa quantos usuários passam do seu site para o seu aplicativo. Ela também informa quais fontes e campanhas de mídia levam os usuários ao seu site que, posteriormente, instalam seu aplicativo.
  * <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">Dados brutos para conversões e eventos</Anchor> que você pode acessar em seus próprios sistemas de BI. Isso oferece a capacidade e o poder de executar sua análise.

<div id="reasons-for-differences" />

### Razões para as diferenças

Se você comparar dados do PBA e do Google Analytics, consulte as seguintes razões para a diferenças nos dados.

<div id="sdk-implementation" />

#### Implementação do SDK

A maneira como você implementa o PBA e o Google Analytics pode afetar a coleta de dados.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="O Google Analytics mostra mais sessões e visitantes">

<div id="cause" />

#### Causa

Se o Google Analytics carregar antes dos usuários do Web SDK que retornam ou que passam curtos períodos de tempo no seu site, esses não são contados no PBA. Isso causa discrepâncias nos dados para sessões e visitantes.

<div id="solution" />

#### solução

É altamente recomendável posicionar o SDK da Web para que seja carregado o mais cedo possível.

Se você <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#integrar-o-web-sdk-no-site">carregar o SDK diretamente ou através de Google Tag Manager</Anchor>, o carregamento final do SDK pode causar discrepâncias significativas.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="O Google Analytics mostra mais dados para sessões, campanhas e conversões">

<div id="cause-1" />

#### Causa

O SDK da Web está presente apenas em determinadas páginas. O Google Analytics está presente em todas as páginas. Como resultado, o Google Analytics coleta dados de todo o seu site, já o SDK da Web coleta dados apenas de determinadas páginas. Isso causa discrepâncias nos dados para sessões, visitantes, campanhas e conversões.

<div id="solution-1" />

#### solução

Implemente o SDK da Web em todas as páginas do seu site.

</Accordion>

<div id="dashboard-settings" />

### Configurações do painel

As configurações do painel, como fuso horário e filtro de dados, podem afetar a forma como os dados são apresentados.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Configurações de fuso horário - discrepâncias nos dados">

<div id="cause-2" />

#### Causa

Se as configurações de fuso horário no Google Analytics forem diferentes daquelas no painel do PBA, você poderá encontrar discrepâncias.

<div id="example" />

> 📄 **Exemplo**
>
> O painel da AppsFlyer está configurado para UTC e o painel do GA para UTC +13. Isso significa que seu painel do GA estará à frente do painel da AppsFlyer em um dia.
>
> Portanto, os dados de 2 de março que aparecem no dashboard da AppsFlyer só aparecem no seu dashboard do GA se você selecionar 3 de março no filtro de período.

<div id="solution-2" />

#### solução

Certifique-se de que as configurações de fuso horário sejam as mesmas na AppsFlyer e no Google Analytics.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Filtros de dados - discrepâncias nos dados">

<div id="issue" />

#### Problema

Tanto a AppsFlyer quanto o Google Analytics permitem filtrar dados de acordo com a data, fontes de mídia atribuídas, campanhas e eventos. Filtros diferentes na AppsFlyer e no Google Analytics podem gerar visualizações diferentes para os mesmos dados.

<div id="solution-3" />

#### solução

Ao comparar dados dos dois painéis, verifique se nenhum filtro foi aplicado ao conjunto de dados.

</Accordion>

<div id="conversions-and-events" />

### Conversões e eventos

Diferentes modelos de atribuição, janelas de lookback, a forma como você envia eventos e configurações de cookies podem afetar a coleta e o processamento de dados.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Janela de lookback - discrepâncias na métrica de conversão">

<div id="cause-3" />

#### Causa

Se você tiver diferentes janelas de lookback no Google Analytics e no PBA, poderão ocorrer discrepâncias nos dados de atribuição.

<div id="solution-4" />

#### solução

A janela de lookback do PBA é sempre de 30 dias. Certifique-se de definir uma janela de lookback de 30 dias no Google Analytics quando você <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">escolher o seu modelo de atribuição</Anchor>.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Modelo de atribuição - discrepâncias na métrica de conversão">

<div id="cause-4" />

#### Causa

Diferentes modelos de atribuição no PBA e no Google Analytics podem causar discrepâncias nos dados de atribuição.

<div id="solution-5" />

#### solução

O Google Analytics oferece <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">modelos de atribuição padrão</Anchor> para você escolher. No entanto, o PBA opera em um modelo de atribuição de último toque não direto com janela de lookback de 30 dias. Certifique-se de escolher um modelo de atribuição de último toque não direto no Google Analytics.

</Accordion>

<div id="sending-events" />

<Accordion title="Enviando eventos">

<div id="issue-1" />

#### Problema

Ambos SDK do Google Analytics e SDK da Web permitem enviar eventos. Se você implementar uma lógica para enviar eventos ao Google Analytics e outra para enviar eventos ao PBA, discrepâncias poderão surgir.

<div id="solution-6" />

#### solução

Ao enviar eventos, verifique o seguinte:

* Certifique-se de que o mesmo gatilho se aplica a ambos
* Certifique-se de enviar o evento para o Google Analytics e o PBA

Clique <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#princípios-do-registro-de-eventos">aqui</Anchor> para saber como enviar eventos usando o SDK da Web.

</Accordion>

<div id="cookies" />

<Accordion title="Cookies">

Tanto o PBA quanto o Google Analytics usam cookies para reconhecer usuários.

<div id="cookie-settings-in-google-analytics" />

#### Configurações de cookies no Google Analytics

Embora seja recomendado permitir que o SDK do Google Analytics lide automaticamente com as configurações de cookie, você ainda pode <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">configurar e alterar as configurações de cookie</Anchor>. Qualquer alteração nas configurações de cookies pode causar discrepâncias.

<div id="setting-cookie-expiration" />

#### Definindo a validade de cookies

O Google Analytics permite que você defina a validade dos cookies. Se você configurar o cookie do Google Analytics para expirar antes do cookie do SDK da Web, discrepâncias poderão ocorrer.

<div id="example-1" />

> 📄 **Exemplo**
>
> Mark é um visitante constante do seu site há mais de um ano e está cogitando assinar um conteúdo premium.
>
> Seu desenvolvedor configurou o cookie do Google Analytics para expirar após um ano. O SDK da Web, no entanto, define o cookie para expirar após dois anos.
>
> Quando Mark finalmente começa a assinatura e a conversão é registrada, o cookie do Google Analytics não é mais válido e outro é definido em seu lugar.
>
> O resultado final é que o Google Analytics mostra dois usuários, ambos são Mark, com apenas um deles tendo uma conversão associada. O PBA, no entanto, mostra um usuário para Mark e o mesmo usuário que possui uma conversão associada.
>
> Isso significa que sua taxa de conversão no Google Analytics é menor que a do PBA.

<div id="setting-cookie-subdomain" />

#### Definindo o subdomínio de cookies

O Google Analytics permite que você defina cookies para subdomínios, já o PBA define apenas cookies no domínio de nível superior.

<div id="example-2" />

> 📄 **Exemplo**
>
> Você configura um cookie para o subdomínio **store.mywebsite.com**. Sharon visita seu site e depois acessa sua loja online em **store.mywebsite.com**. O Google Analytics a considera como **como dois usuários diferentes**.
>
> Como o PBA define apenas cookies no domínio de nível superior **mywebsite.com**, considera Sharon em **mywebsite.com** and **store.mywebsite.com** como o mesmo usuário.
>
> O resultado final são dois usuários no Google Analytics e um usuário no PBA.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=pba-comparado-ao-google-analytics benefits-of-pba-over-google-analytics=benef%C3%ADcios-do-pba-em-rela%C3%A7%C3%A3o-ao-google-analytics reasons-for-differences=raz%C3%B5es-para-as-diferen%C3%A7as sdk-implementation=implementa%C3%A7%C3%A3o-do-sdk cause=causa solution=solu%C3%A7%C3%A3o cause::49d3e519=causa-1 solution::447e7ac9=solu%C3%A7%C3%A3o-1 dashboard-settings=configura%C3%A7%C3%B5es-do-painel cause::30244d2c=causa-2 solution::f1a0e066=solu%C3%A7%C3%A3o-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=problema solution::df8f3921=solu%C3%A7%C3%A3o-3 conversions-and-events=convers%C3%B5es-e-eventos cause::b346571c=causa-3 solution::4bb14ac9=solu%C3%A7%C3%A3o-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=causa-4 solution::b2be4a33=solu%C3%A7%C3%A3o-5 issue::b412f5ba=problema-1 solution::39b4d7d6=solu%C3%A7%C3%A3o-6 cookie-settings-in-google-analytics=configura%C3%A7%C3%B5es-de-cookies-no-google-analytics setting-cookie-expiration=definindo-a-validade-de-cookies setting-cookie-subdomain=definindo-o-subdom%C3%ADnio-de-cookies" />
