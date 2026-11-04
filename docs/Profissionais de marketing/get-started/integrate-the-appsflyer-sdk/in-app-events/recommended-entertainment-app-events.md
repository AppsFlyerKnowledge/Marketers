---
title: Eventos de aplicativo de entretenimento recomendados
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-08-18T00:14:03Z'
  id: 360019699898
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019699898
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada de usuário, registrando os eventos in-app sugeridos para seu aplicativo de entretenimento.

<div id="-entertainment" />

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Entretenimento

Com a crescente exigência de parte dos usuários por conteúdos sob demanda, o mercado de aplicativos de entretenimento se tornou muito competitivo. Os eventos típicos que sugerimos que você grave são assinaturas dos usuários, streaming de conteúdo e quando os usuários fazem download e salvam conteúdo.

Gravar eventos pode ajudar a determinar:

* Quais conteúdos os usuários consomem
* Performance da campanha (de acordo com o conteúdo que os usuários esperam receber)
* Engajamento e uso do usuário

Esses eventos também são relevantes para aplicativos de entretenimento executados nas seguintes smart TVs:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub para desenvolvedores da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como registrar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia de Eventos in-app avançados</Anchor>.

[![Fluxograma_da_jornada_do_usuário_do_app_de_entretenimento_para_eventos_recomendados](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de entretenimento. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | Método que o usuário escolhe para se cadastrar | Facebook, Google, email |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários registrados

**Trigger**

Quando o usuário faz login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Iniciar avaliação (af_start_trial)">

**Propósito**

Muitos serviços de streaming oferecem aos usuários um período de avaliação para usufruir dos recursos premium. Esse evento pode ajudar a:

* Ver quantos usuários se inscrevem para um período de avaliação.
* Se a avaliação faz parte de uma promoção ou de uma colaboração com um parceiro
* Qual promoção levou o usuário a ativar o período de avaliação

Para registrar e validar este evento, consulte <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Validação de compra e assinatura</Anchor>.

**Gatilho**

Quando o usuário se inscreve e ativa o período de avaliação

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| método\_de\_teste | Método para ativar a avaliação | Grátis com um novo telefone, grátis com uma operadora, promoção, código de cupom |
| identificador\_do\_método\_de\_teste | Identificador do método de avaliação | Nome da operadora, por exemplo, **Vodafone**<br /><br />Nome do parceiro, por exemplo, **Meta Ads**<br /><br />Código do cupom, por exemplo, **TRA123** |

<div id="note" />

> 📘 **Observação**
>
> Se você estiver mapeando esse evento para o evento Meta ads StartTrial e quiser associar receita, use o parâmetro af\_price em vez do parâmetro af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Assinatura (af_subscribe)">

**Propósito**

A assinatura é a base dos serviços de streaming. Esse evento pode ajudar a:

* Ver quais campanhas captam usuários que fazem uma assinatura ou cadastro
* Comparar o número de usuários no período de avaliação com o número de usuários com assinatura.
* Determinar o valor da receita gerada a partir de assinaturas e atribuí-lo a campanhas e fontes de mídias

**Gatilho**

* Quando o usuário faz a assinatura com sucesso
* Quando uma assinatura for renovada

Veja nossa Atribuição de assinatura—Visão geral para obter mais informações.

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| new\_subscription | Se a assinatura é nova ou renovada | true / false |
| af\_coupon\_code | Código do cupom, se tiver sido usado durante a assinatura | 3MonthsSubscription |
| coupon\_code\_value | Quanto o cupom deduz do preço inicial | 10% |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | Receita associada à assinatura | 5.95 |
| af\_currency | Moeda do pagamento da assinatura | USD |
| subscription\_method | Método de pagamento usado na assinatura | credit card, e-wallet, PayPal |
| expiration\_date | Data de validade da assinatura | 2018/07/18 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir oferece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="media-play-media_play" />

<Accordion title="Reprodução de mídia (media_play)">

**Propósito**

Registre os eventos em que os usuários reproduzem a mídia que você oferece. Exemplos de mídias: vídeos, música, programas de tv, programas de rádio, entre outros.

Gravar esse evento pode ajudar a determinar:

* Consumo de mídia por tipo e conteúdo
* Os idiomas dos conteúdos transmitidos mais populares
* Duração miníma, máxima e média dos conteúdos transmitidos

**Trigger**

Após um número predefinido, por exemplo, 2 minutos, de conteúdo transmitido.

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de conteúdo que é transmitido | tv show, music |
| af\_content\_id | ID do conteúdo que é transmitido | 092, E34 |
| af\_content | Título do conteúdo, por exemplo, o nome da música ou o título e episódio de um programa de TV | Título do conteúdo |
| duração\_da\_mídia | Duração total da mídia, por exemplo, a duração total de um vídeo. | 5 |
| language | Idioma do conteúdo | en-us, fr, es |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="Minutos de mídia (media_minutes)">

**Propósito**

Minutos de mídia é a quantidade de um determinado item de conteúdo que o usuário consome. Depois da métrica de receita, esta é a métrica mais importante na indústria do streaming pois permite que você tenha uma estimativa de quanto o usuário utiliza o serviço. Ela também permite que você entenda qual é o índice total de uso do serviço e quais conteúdos são mais populares. Esse evento pode ajudar a:

* Ver quais usuários utilizam bastante seu serviço
* Ver quais tipos de mídias e conteúdos são populares

**Trigger**

Um dos seguintes:

* Quando o usuário finaliza a transmissão de um item de mídia
* Quando o usuário encerra a transmissão de um item de mídia

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| minutes\_consumed | Número de minutos em que o usuário engajou com a mídia. Por exemplo, a duração total de um vídeo pode ser de 5 minutos, mas um usuário pode assistir apenas 3 minutos. | 3 |
| af\_content\_type | Tipo de conteúdo que é transmitido | tv show, music |
| af\_content\_id | ID do conteúdo que é transmitido | 092, E34 |
| af\_content | Título do conteúdo, por exemplo, o nome da música ou o título e episódio de um programa de TV | Título do conteúdo |
| duração\_da\_mídia | Duração total da mídia, por exemplo, a duração total de um vídeo. | 5 |
| language | Idioma do conteúdo | en-us, fr, es |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="Mídia baixada (media_downloaded)">

**Propósito**

Destaque a preferencia dos usuários ao registrar a reprodução e o download de mídias, comparando ambos. É possível identificar quais mídias os usuários preferem transmitir e quais mídias eles preferem baixar.

**Gatilho**

Quando um usuário começa o download de uma mídia

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de conteúdo | tv show, music |
| af\_content\_id | ID do conteúdo | 092, E34 |
| af\_content | Título do conteúdo, por exemplo, o nome da música ou o título e episódio de um programa de TV | Título do conteúdo |
| duração\_da\_mídia | Duração total da mídia, por exemplo, a duração total de um vídeo. | 5 |
| language | Idioma do conteúdo | en-us, fr, es |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="Mídia salva (media_saved)">

**Propósito**

Ajuda você a destacar as preferências do usuário

**Trigger**

Sempre que a mídia for salva no dispositivo do usuário

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_content\_type | Tipo de conteúdo | tv show, music |
| af\_content\_id | ID do conteúdo | 092, E34 |
| af\_content | Título do conteúdo, por exemplo, o nome da música ou o título e episódio de um programa de TV | Título do conteúdo |
| duração\_da\_mídia | Duração total da mídia, por exemplo, a duração total de um vídeo. | 5 |
| language | Idioma do conteúdo | en-us, fr, es |

</Accordion>

<div data-zendesk-anchors="entertainment=-entretenimento h_01HGTAX1B0KT8Q6PRE41JCPJ60=-entretenimento h_01HGTAX1B0K2RKYGPFFARM0E1B=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAX1B05C7G67RJPSG3YF66=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=observa%C3%A7%C3%A3o h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAX1B1ATFH70K2BJZ7XW13=estruturas-recomendadas-para-eventos-personalizados h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
