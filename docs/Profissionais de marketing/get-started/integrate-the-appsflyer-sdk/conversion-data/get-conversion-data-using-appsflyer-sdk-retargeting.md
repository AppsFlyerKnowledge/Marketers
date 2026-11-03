---
title: Obtenha dados de conversão usando o SDK da AppsFlyer
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-09-24T00:06:12Z'
  id: 4410481260817
  locale: pt
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/pt/articles/4410481260817
---
> **At a glance:** **Visão geral:** Saiba como as reatribuições e os reengajamentos se refletem nos dados de conversão para jornadas de usuários SRN e não SRN.

## Conversão de retargeting

O retargeting inclui dois tipos de conversões, reatribuição ou reengajamento.

> 👍 **Tip**
>
> Os dados de conversão para retargeting nem sempre fornecem uma indicação clara quanto ao tipo de conversão. Consulte [fontes alternativas de dados de conversão](#fontes-de-dados-de-conversão-alternativas).

## Reatribuição com SRNs

Quando um usuário é reatribuído por meio de uma SRN, a carga dos dados de conversão não indica que se trata de uma campanha de retargeting. Como as SRNs não usam links de atribuição, não há como definir um parâmetro `is_retargeting=true` no link de atribuição. Para **SRNs compatíveis com retargeting**, a AppsFlyer determina se o usuário deve ser reatribuído ou não.

Isso significa que não há como determinar, no nível do SDK, se uma instalação vem de uma campanha de retargeting.

> 📘 **Note**
>
> Definir o nome da campanha de forma que indique o retargeting **não é um método infalível**. Veja [exemplos para saber mais](#exemplos-de-aquisição-e-reatribuição-de-usuários-mistos).

## Reatribuição com ad networks regulares

A atribuição a ad networks depende de links de atribuição. Sejam links de atribuição regulares ou OneLink, com retargeting, o link de atribuição sempre tem o parâmetro `is_retargeting=true`is\_retargeting=trueis\_retargeting=true definido nele.

<Accordion title="Campanha de retargeting com Criteo">

#### Link de atribuição

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### Carga de dados de conversão

```json
 Observação:
```

* `retargeting_conversion_type` parâmetro - esse parâmetro indica o tipo de retargeting. Pode ser reatribuição, reengajamento ou nenhum.
* Parâmetro `is_retargeting: true` - esse parâmetro indica que a instalação é uma instalação reatribuída
* `af_reengagement_window`: A janela de atribuição de reengajamento é o número de dias no qual um evento pode ser atribuído a um **usuário reengajado**. Como essa é uma conversão de nova atribuição, esse parâmetro é redundante.

</Accordion>

## Reatribuição com deferred deep linking

Muitas vezes, é possível que você queira criar deep links para usuários reatribuídos que, por serem reatribuídos, não têm o aplicativo instalado. Por exemplo, você define uma campanha com o intuito de trazer de volta os usuários que desinstalaram o aplicativo. A campanha promove um produto ou serviço e você deseja atender os usuários com conteúdo relacionado ao produto ou serviço que você anuncia.

Isso é conhecido como deferred deep linking. A carga de dados de conversão para deferred deep linking vem do método `onConversionDataSuccess`.

<Accordion title="Deferred deep linking com SRNs">

Para implementar deferred deep linking com SRNs, é necessário aplicar uma lógica adicional às campanhas de SRN. Use os dados na resposta `onConversionSuccess`, como campanha, adset e adgroup, para redirecionar seus usuários de forma programática.

#### Dados de conversão para deferred deep linking com Anúncios da Meta

<Tabs>
<Tab title="Android iOS">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"não orgânico",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="Exemplo">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Você pode usar os dados na resposta getConversionData, como campanha, adset etc., para redirecionar seus usuários de forma programática e mostrar conteúdo relevante para eles.

> 📘 **Note**
>
> O aplicativo é um aplicativo de eCommerce especializado em roupas esportivas. Um usuário que não tem o aplicativo instalado interage com um anúncio e instala o aplicativo. Depois que o aplicativo é iniciado, o SDK retorna os dados de conversão. O desenvolvedor faz com que o aplicativo abra a atividade de **coleção de tênis de corrida de verão** (campanha) na loja e mostre a categoria **tênis de corrida para mulheres** (adset).

</Accordion>

<Accordion title="Deferred deep linking com links de atribuição">

Existem três maneiras de fazer o deep linking dos usuários:

#### Esquemas URI

Ao usar esquemas URI, tanto para links de atribuição quanto para OneLink, o link de atribuição e o payload são os seguintes:

**Link de atribuição**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**Os links diretos universais do OneLink**

```http
// OneLink curto
  https://dhba.onelink.me/2rAD/71ba577e

  //OneLink longo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Carga útil**

```json
Android iOS
```

* `af_deeplink: true` - quando esse parâmetro aparece e é definido como true, procure os campos `scheme` e `host`
* `scheme` e `host` - esses campos vêm do parâmetro `af_dp` no link de atribuição e indicam o esquema e a atividade para os quais o usuário deve receber deep linking

#### Universal Links do iOS e App Links do Android

Essas são as outras duas das três maneiras de realizar deep linking.

Ao usar Universal Links ou App Links, o OneLink e o payload são os seguintes:

**Os links diretos universais do OneLink**

```http
// OneLink curto
  https://dhba.onelink.me/2rAD/71ba577e

  //OneLink longo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Carga útil**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Campo `shortlink` - este é o campo que indica de qual OneLink específico o usuário vem. Isso ajuda o desenvolvedor a saber como proceder em termos de iniciar uma atividade e veicular conteúdo. Outros campos, como `campaign`, também podem ser usados para essa finalidade.

> 🚧 **Important**
>
> O campo `shortlink` não aparece no payload ao usar o OneLink longo.
>
> Em ambos os casos (OneLink curto ou longo), recomendamos adicionar um parâmetro personalizado que indique a atividade. Por exemplo, `&deep_link_activity=shoes_cateogry`

> 📘 **Note**
>
> Usar Universal Links e App Links só é possível com o OneLink.

</Accordion>

## Reengajamento com SRNs

Assim como nas campanhas de reatribuição, quando um usuário é reengajado por meio de uma SRN, os dados de conversão não indicam que se trata de uma campanha de reengajamento.

## Reengajamento com ad networks regulares

Aqui também, a carga dos dados de conversão não indica que o usuário vem de uma campanha de reengajamento. Para superar essa limitação, você pode definir o nome da campanha para indicar um reengajamento.

## Reengajamento com deep linking

Uma parte importante do reengajamento é enviar o usuário para uma atividade específica. Por exemplo, se você anunciar algum produto ou promoção. Nesses casos, recomendamos que você envie os usuários que clicam no anúncio diretamente para a atividade do aplicativo desse produto ou venda.

Para fazer isso, você usa deep linking. Os dados de conversão no deep linking são muito importantes. Eles contêm as informações necessárias para o desenvolvedor personalizar a experiência do usuário e encaminhá-lo para a atividade correta.

<Accordion title="Reengajamento: deep linking com SRNs">

Os dados de conversão não estão disponíveis quando um usuário reengajado vem de uma SRN. O desenvolvedor precisa usar os métodos de SRN para obtê-lo na inicialização do aplicativo.

</Accordion>

<Accordion title="Reengajamento: deep linking com ad networks">

Quando um usuário é engajado novamente e o aplicativo é iniciado, os seguintes dados de conversão ficam disponíveis no método `onAppOpenAttribution`:

Para iOS e Android, ao usar a versão curta do OneLink, os dados de conversão são um mapa estruturado de todos os parâmetros no link:

Exemplo:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* O desenvolvedor do aplicativo pode usar tais parâmetros, como `af_dp` e nome da campanha, para direcionar o usuário a uma atividade específica e exibir o conteúdo relevante.

> 🚧 **Important**
>
> Recomendamos usar a versão curta do OneLink. Clique <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">aqui</Anchor> para saber mais.

Outro motivo para usar a versão curta do OneLink é a estrutura de dados de conversão que a versão longa retorna. Ao usar a versão longa, os dados de conversão são um mapa com um único campo chamado `link` que contém todo o OneLink longo.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

## Fontes de dados de conversão alternativas

* A Push API oferece uma carga de conversão detalhada que indica reatribuição ou reengajamento. A cargas da Push API incluem um campo chamado `re_targeting_conversion_type`. Esse campo indica o tipo de conversão, seja reatribuição ou reengajamento. Para saber mais, consulte nosso <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">guia de Push API</Anchor>.
* Os relatórios de dados brutos também contêm indicadores para o tipo de conversão. No relatório de dados brutos para conversões de retargeting, há uma coluna chamada ***nome do evento***. O valor nessa coluna é ***reengajamento*** ou ***reatribuição*** de acordo com o tipo de conversão.

## Exemplos de aquisição e reatribuição de usuários mistos

> 📘 **Note**
>
> 1. Um usuário instala seu aplicativo e o desinstala. O ato de instalação coloca o usuário em uma <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>. Você define uma campanha de aquisição de usuários (não retargeting) com o Meta ads. Você também configura a integração da AppsFlyer com Meta Ads para permitir retargeting. Enquanto ainda está na janela de reatribuição, o usuário vê o anúncio, clica nele e reinstala o aplicativo. De acordo com a AppsFlyer, o usuário é um usuário reatribuído. Isso se deve a dois fatores:
>
>    1. A configuração com o Meta ads permite o retargeting
>    2. O usuário está na janela de reatribuição
>
>    Nesse caso, o nome da campanha não indica a reatribuição.
> 2. Vamos pegar o mesmo exemplo, só que desta vez o usuário está fora da janela de reatribuição. Nesse caso, a instalação é uma nova instalação não orgânica.
> 3. Vamos avaliar outro exemplo. Você define uma campanha de retargeting no Meta ads. Alguns usuários se deparam com a campanha e instalam o app. No entanto, esses usuários instalam o aplicativo pela primeira vez. Esses usuários não são considerados usuários reatribuídos. Em vez disso, a AppsFlyer os considera como usuários provenientes de uma campanha de aquisição de usuários.

<div data-zendesk-anchors="retargeting-conversion=convers%C3%A3o-de-retargeting h_01EHQ74JS84509GT6M93SZA4HX=convers%C3%A3o-de-retargeting reattribution-with-srns=reatribui%C3%A7%C3%A3o-com-srns h_01JNBRN0TBCVKBP6X6GCK3ADG9=reatribui%C3%A7%C3%A3o-com-srns reattribution-with-regular-ad-networks=reatribui%C3%A7%C3%A3o-com-ad-networks-regulares h_01JNBRN0TCF7YC76661XNS78AD=reatribui%C3%A7%C3%A3o-com-ad-networks-regulares attribution-link=link-de-atribui%C3%A7%C3%A3o h_01JNBRN0TCP9CAHV3X4QD0AVRS=link-de-atribui%C3%A7%C3%A3o conversion-data-payload=carga-de-dados-de-convers%C3%A3o h_01JNBRN0TCXAZKYVYY56Q4GVHN=carga-de-dados-de-convers%C3%A3o reattribution-with-deferred-deep-linking=reatribui%C3%A7%C3%A3o-com-deferred-deep-linking h_01JNBRN0TCECNRZ5ZBH2WWAWHV=reatribui%C3%A7%C3%A3o-com-deferred-deep-linking conversion-data-for-deferred-deep-linking-with-facebook=dados-de-convers%C3%A3o-para-deferred-deep-linking-com-an%C3%BAncios-da-meta h_01JNBRN0TC3NAE862BG274DRWW=dados-de-convers%C3%A3o-para-deferred-deep-linking-com-an%C3%BAncios-da-meta uri-schemes=esquemas-uri h_01JNBRN0TC909V4TNCEK4ZP83H=esquemas-uri ios-universal-links-and-android-app-links=universal-links-do-ios-e-app-links-do-android h_01JNBRN0TCH7HYZ4BCZTNS89SS=universal-links-do-ios-e-app-links-do-android reengagement-with-srns=reengajamento-com-srns h_01JNBRN0TCT2F11CQ4H8208JCB=reengajamento-com-srns reengagement-with-regular-ad-networks=reengajamento-com-ad-networks-regulares h_01JNBRN0TCNTAAD47ZTTK3NWYJ=reengajamento-com-ad-networks-regulares reengagement-with-deep-linking=reengajamento-com-deep-linking h_01JNBRN0TCGN9Y8ZHSEC4HMKPM=reengajamento-com-deep-linking alternative-conversion-data-sources=fontes-de-dados-de-convers%C3%A3o-alternativas h_01JNBRN0TCZ8T35W3AAA4HVD9M=fontes-de-dados-de-convers%C3%A3o-alternativas examples-of-mixed-user-acquisition-and-reattribution=exemplos-de-aquisi%C3%A7%C3%A3o-e-reatribui%C3%A7%C3%A3o-de-usu%C3%A1rios-mistos h_01JNBRN0TC13RAZ73AFV6G92VB=exemplos-de-aquisi%C3%A7%C3%A3o-e-reatribui%C3%A7%C3%A3o-de-usu%C3%A1rios-mistos" />
