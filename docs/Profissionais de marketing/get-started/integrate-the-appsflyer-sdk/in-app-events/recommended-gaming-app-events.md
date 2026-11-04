---
title: Eventos recomendados de aplicativos de jogos
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2026-08-18T00:14:15Z'
  id: 360018941117
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360018941117
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada do usuário, registrando esses eventos in-app sugeridos para seu aplicativo de jogos.

<div id="-gaming" />

## <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" /> Jogos

Aplicativos de jogos incluem gêneros como arcade, estratégia, educação e jogos de azar. Os típicos eventos que sugerimos que você registre são compras in-app, compartilhamento em mídias sociais e convites para amigos. Além disso, você pode incluir eventos como subir de nível e concluir um tutorial no jogo.

Gravar eventos pode ajudar a determinar:

* Quais ofertas os usuários mais compram
* Quão engajados são os usuários
* Quantos usuários postam compartilhamentos nas mídias sociais
* Quantos usuários convidam amigos para instalar o aplicativo

Esses eventos também são relevantes para aplicativos de jogos que são executados nas seguintes plataformas:

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Dispositivos mobile Windows

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=gaming&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o seu desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">developer hub (hub para desenvolvedores) da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma_para_eventos_recomendados jornada_do_utilizador_da_app_de_jogos](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de jogos. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entender a retenção de seus usuários registrados

**Trigger**

Sempre que o usuário fizer login com sucesso

**Parâmetros do evento**

Pode ser enviado sem nenhum parâmetro adicional

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Registro completo (af_complete_registration)">

**Propósito**

Saiba quantos usuários instalaram o aplicativo e concluíram o processo de inscrição e quais métodos de inscrição seus usuários preferem.

**Trigger**

Quando o usuário conclui o processo de inscrição

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_registration\_method | O tipo de método de cadastro | email, facebook |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Propósito**

Muitos aplicativos de jogos permitem que os usuários comprem itens como, por exemplo, moedas, joias ou armas. O registro dessas compras pode ajudar a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Descobrir quais ofertas são mais populares entre os seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

Para registrar e validar este evento, consulte <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Validação de compra e assinatura</Anchor>.

**Trigger**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | A receita estimada de uma compra | 199.99 |
| af\_currency | Código da moeda | THB, USD |
| af\_quantity | Número de itens comprados | 2 |
| af\_content\_id | ID do item | 001, 092 |
| af\_order\_id | ID do pedido | 9277 |
| af\_receipt\_id | ID do recibo | 9277 |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Nível alcançado (af_level_achieved)">

**Propósito**

Um dos principais objetivos dos usuários é subir de nível nos jogos. Muitas vezes, subir de nível desbloqueia novos recursos e estágios no jogo e isso incentiva os usuários a continuar jogando. Registrar a subida de nível pode ajudar a:

* Determinar quais campanhas trazem os usuários mais ativos
* Ver quais tipos de usuários são mais ativos e engajados
* Associar a atividade geral do usuário com medidas como receita

**Trigger**

Quando o usuário chega à página de conclusão de nível

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_level | Nível alcançado pelo usuário | 3 |
| af\_score | Pontuação associada à conquista do usuário | 500 |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Conclusão do tutorial (af_tutorial_complete)">

**Propósito**

Os tutoriais oferecem aos seus usuários orientações sobre como usar o aplicativo. Registrar esse evento pode ajudar a determinar:

* Com quais tópicos os usuários podem ter problemas
* Quais tutoriais não têm bom desempenho

**Trigger**

* Quando um usuário conclui um tutorial
* Quando um usuário inicia um tutorial, mas sai sem concluí-lo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_success | Se o usuário concluiu o tutorial | verdadeiro |
| af\_tutorial\_id | ID do tutorial | 3 |
| af\_content | Nome do tutorial | Getting Started |

</Accordion>

<div id="share-af_share" />

<Accordion title="Compartilhar (af_share)">

**Propósito**

Usuários gostam de compartilhar suas conquistas em jogos nos sites de mídias sociais. Compartilhar cria um reconhecimento da marca e pode incentivar os usuários a fazer o download e instalar seu aplicativo. O registro desse evento pode ajudar você a entender quando é mais provável que os usuários compartilhem o aplicativo com os amigos. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">o registro de compartilhamentos e convites</Anchor>.

**Trigger**

Quando um usuário publica com sucesso um compartilhamento nas mídias sociais

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_description | Motivo para compartilhar nas mídias sociais, por ex. novo recorde ou subida de nível | Novo recorde, subida de nível, jogo ganho |
| platforma | Plataforma usada para postar compartilhamentos | Facebook, WhatsApp, e-mail |

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Convite (af_invite)">

**Propósito**

Saber para quais sites de mídia social os usuários enviam convites e quantos usuários convidaram seus amigos para fazer download e instalar o aplicativo.

**Trigger**

Quando o usuário convida com sucesso um amigo para fazer download e instalar o aplicativo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_description | Contexto do convite | Try this app |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir oferece uma estrutura de eventos que inclui um nome de evento personalizado e o parâmetro de evento sugerido a ser usado. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="bonus-claimed-bonus_claimed" />

<Accordion title="Bônus solicitado (bonus_claimed)">

**Propósito**

Ver quantos usuários solicitaram bônus oferecidos a eles e associar bônus solicitados à atividade e engajamento do usuário.

**Trigger**

Quando o usuário solicita um bônus e ele é atualizado para sua conta

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| bonus\_type | Tipo de bônus que o usuário solicita | Moedas |

</Accordion>

<div data-zendesk-anchors="gaming=-jogos h_01HGTAVT1XSEY0TS9T2R1H1KXV=-jogos h_01HGTAVT1XTXYHV1MTFR20BR6J=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAVT1X4QQS6GREKC0N0VK6=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAVT1XAAPGHBTXE6DT9927=login-af_login h_01HGTAVT1X4V41YCXBEXTV0KFR=complete-registration-af_complete_registration h_01HGTAVT1X64710WYNZHTHD7R5=purchase-af_purchase h_01HGTAVT1X24N9J3BMDHV3S54M=level-achieved-af_level_achieved h_01HGTAVT1X5RN4A1MAE0BFB3B4=tutorial-completion-af_tutorial_completion h_01HGTAVT1X952BV07KGZHK68P6=share-af_share h_01HGTAVT1X7KSTYXZGAKEPCXZM=invite-af_invite recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAVT1YXGTF0E5YQX1C3CJN=estruturas-recomendadas-para-eventos-personalizados h_01HGTAVT1YNH0YAFYX4PR7D6DH=bonus-claimed-bonus_claimed" />
