---
title: Discrepâncias entre a AppsFlyer e plataformas externas
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-08-19T00:12:30Z'
  id: 19384888063249
  locale: pt
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/pt/articles/19384888063249
---
> **At a glance:** **Resumo**: Entenda as diferenças entre a atribuição da AppsFlyer e de plataformas externas.

## Visão geral

Devido a políticas de compartilhamento de dados dos canais de mídia, <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">nem todos os dados a nível do usuário são compartilhados com plataformas externas</Anchor> (como plataformas de marketing e analytics). Por isso, talvez existam discrepâncias na atribuição entre os dados exibidos em plataformas externas e os dados da AppsFlyer.

> 📘 **Note**
>
> **Atenção**
>
> Os dados agregados e analíticos da AppsFlyer estão disponíveis sem limitação.

## Restrições de postback em plataformas externas

Quando se trata do envio de postbacks para plataformas externas, vemos diferentes níveis de restrições nos canais de mídia. Os postbacks podem não ser enviados, ser enviados sem atribuição ou enviados sem nenhuma restrição.

#### Tipos de restrições de postbacks

<div id="no-postbacks-sent" />

<Accordion title="Nenhum postback é enviado">

Postbacks de eventos de dados brutos restritos por canal de mídia, conforme descritos <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">nessa tabela</Anchor>, não são enviados para plataformas externas. Isso significa que essas plataformas não recebem postbacks desses eventos, levando a uma atribuição mais restrita em comparação com a AppsFlyer.

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="Postbacks são enviados sem atribuição">

As ad networks listadas abaixo exigem que os anunciantes censurem o nome do canal de mídia para eventos que não são eventos restritos de dados brutos em postbacks compartilhados com plataformas externas. Na AppsFlyer, **o canal de mídia original é substituído por atribuição orgânica**. Isso significa que os postbacks desses eventos não incluem a atribuição para o canal de mídia. Como resultado, vemos uma atribuição mais restrita nessas plataformas em comparação com a AppsFlyer:

* Amazon
* Meta Ads
* Pinterest
* Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">Termos de Serviço</Anchor>)
* AppsFlyer
* Bing
* Yahoo (Oath: Plataformas de anúncios / Yahoo Gemini)

> 📘 **Note**
>
> **Atenção**
>
> Para o Meta Ads, o comportamento de postback depende de o anunciante ter aceitado ou não os termos da Mensuração Mobile Avançada (AMM):
>
> * **AMM não permitida**: os postbacks são enviados apenas para instalações <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#install-referrer-android-only">atribuídas por um install referrer</Anchor>. Os postbacks não incluem dados de atribuição.
> * **AMM permitida**: os postbacks são enviados para instalações atribuídas por <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">todos os métodos de atribuição</Anchor>. No entanto, os dados de postback não incluem dados de atribuição, ou seja, todos os postbacks são enviados para plataformas externas como dados não atribuídos (orgânicos).

</Accordion>

<div id="regular-postbacks" />

<Accordion title="Postbacks padrão">

Todos os outros eventos que não são restritos ou cujo canal de mídia não foi censurado, são enviados como postbacks padrão. Isso inclui eventos agregados.

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">As restrições de postback se aplicam a todas as plataformas externas integradas com a AppsFlyer. Exemplos:</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>Nuvem</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>salesforce.png</td><td>marketing</td><td>MobilePush</td><td>Segmento</td><td>Spoteffects</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>Tapcart</td><td>Tealium</td><td>WebEngage</td><td>Winclap Analytics</td><td>Google Analytics 4</td><td> </td></tr></tbody></table>

## Exemplos de discrepâncias

<div id="example-1" />

<Accordion title="Restrições de dados brutos no Mixpanel">

<Tabs>
<Tab title="AMM não permitida">

> 📘 **Note**
>
> **Exemplo 1**
>
> Um anunciante usa o Meta Ads para criar um anúncio. Ele também está trabalhando com o Mixpanel para entender melhor como os usuários se comportam e interagem com seu app. Ele verifica o número de instalações atribuídas ao Meta Ads no último mês:
>
>
>
> | Na AppsFlyer | No Mixpanel |
> | --- | --- |
> | Um anunciante vê 100 instalações atribuídas ao Meta Ads.<br /><br />30 das instalações foram atribuídas usando o parâmetro `gp_referrer`. Esses eventos não são restritos e aparecem nos relatórios de dados brutos. | Um anunciante vê somente 30 instalações atribuídas ao orgânico.<br /><br />O Mixpanel não recebe postbacks para os 70 eventos restritos. Os postbacks para as 30 instalações atribuídas usando o `gp_referrer` são enviados como orgânicos. |

</Tab>

<Tab title="AMM permitida">

> 📘 **Note**
>
> **Exemplo 1**
>
> Um anunciante usa o Meta Ads para criar um anúncio e aceita os termos da AMM. Ele também está trabalhando com o Mixpanel para entender melhor como os usuários se comportam e interagem com seu app. Ele verifica o número de instalações atribuídas ao Meta Ads no último mês:
>
>
>
> | Na AppsFlyer | No Mixpanel |
> | --- | --- |
> | Um anunciante vê 100 instalações atribuídas ao Meta Ads.<br /><br />O relatório de dados brutos da instalação incluirá todas as 100 instalações, não apenas as instalações atribuídas pelo método gp\_referrer | Um anunciante vê 100 instalações atribuídas a canais orgânicos.<br /><br />Como a AMM é permitida, o Mixpanel recebe postbacks para todas as 100 instalações. No entanto, nenhum dos postbacks inclui dados de atribuição, então todas as instalações aparecem como orgânicas. |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="Restrições de dados brutos na MoEngage">

> 📘 **Note**
>
> **Exemplo 2**
>
> Um anunciante usa o Pinterest para criar um anúncio. Ele também está trabalhando com a MoEngage para receber insights sobre o engajamento dos seus clientes. O anunciante verifica quantos eventos de "Adicionar à wishlist" foram atribuídos ao Pinterest no último mês:
>
>
>
> | Na AppsFlyer | Na MoEngage |
> | --- | --- |
> | O anunciante vê 97 eventos de "Adicionar à wishlist" atribuídos ao Pinterest. | Ele não vê nenhum evento de "Adicionar à wishlist" atribuído ao Pinterest. A MoEngage não recebeu postbacks de click-through e view-through do Pinterest, pois esses são eventos restritos. |

</Accordion>

<div id="example-3" />

<Accordion title="Restrições no Airship">

> 📘 **Note**
>
> **Exemplo 3**
>
> Um anunciante usa o Bing para criar um anúncio. Ele também está trabalhando com o Airship para otimizar a jornada dos usuários em seu app mobile. O anunciante verifica quantos eventos de compra foram atribuídos ao Bing no último mês:
>
>
>
> | Na AppsFlyer | No Airship |
> | --- | --- |
> | O anunciante vê 35 eventos de compra atribuídos ao Bing. | O anunciante vê 84 eventos de compra de canais orgânicos. 35 deles vieram do Bing, mas o anunciante não consegue identificar isso, pois os eventos de compra são exibidos como orgânicos. |

</Accordion>

> 📘 **Note**
>
> **Veja também**
>
> Perguntas frequentes sobre as <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#perguntas-frequentes">restrições de conteúdo de dados brutos</Anchor>.

<div data-zendesk-anchors="Overview=vis%C3%A3o-geral h_01HCVTKD7ZH991A8JF7XCNNE91=vis%C3%A3o-geral postback-restrictions=restri%C3%A7%C3%B5es-de-postback-em-plataformas-externas h_01HDDR9JG5303R38QCAB2ZF6CW=restri%C3%A7%C3%B5es-de-postback-em-plataformas-externas types-of-postback-restrictions=tipos-de-restri%C3%A7%C3%B5es-de-postbacks h_01HE05EXEFJF6SGYTKZ78FPP7Z=tipos-de-restri%C3%A7%C3%B5es-de-postbacks h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=exemplos-de-discrep%C3%A2ncias h_01HCW4HS35ZTAEWPXB9JKCR725=exemplos-de-discrep%C3%A2ncias h_01HDDS499QJTX5RJY6CR98BDFB=example-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3" />
