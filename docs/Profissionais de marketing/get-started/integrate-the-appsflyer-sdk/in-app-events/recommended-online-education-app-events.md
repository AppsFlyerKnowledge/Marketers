---
title: Eventos de aplicativos de educação online recomendados
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-08-18T00:14:30Z'
  id: 360019794378
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/360019794378
---
> **Visão geral:** mensure a qualidade dos seus usuários durante toda a jornada de usuário, registrando os eventos in-app sugeridos para seu aplicativo de educação online.

<div id="-online-education" />

## <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Educação online

Os aplicativos de educação online permitem que os usuários aprendam de maneira remota. Os típicos eventos in-app que recomendamos registrar incluem cadastro, tutoriais, cursos finalizados e certificados recebidos.

Gravar eventos pode ajudar a determinar:

* O que os usuários do curso mais querem, oferecendo ideias para direcionamento
* Quais usuários podem passar por retargeting e relembrar que eles possuem tutoriais adicionais para concluir um curso
* Quais cursos e certificados são os mais procurados

<div id="important" />

> 🚧 **Importante!**
>
> * Certifique-se de ler <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">as instruções</Anchor> para os profissionais de marketing sobre a implementação de eventos in-app.
> * Para agilizar o processo de implementação, use nosso <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education">gerador de eventos in-app</Anchor>. Essa ferramenta inclui todos os eventos in-app típicos descritos neste artigo e permite que você modifique os eventos de acordo com as necessidades da sua empresa. Depois de concluído, compartilhe o arquivo com seu desenvolvedor.
> * Para cada evento recomendado incluído neste artigo, há <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education&view=code">exemplos de código</Anchor> para desenvolvedores do iOS, Android e Unity.
> * Instruções detalhadas para o desenvolvedor podem ser encontradas no **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub para desenvolvedores da AppsFlyer</Anchor>.**
>
> Para mais informações sobre como gravar eventos in-app, consulte o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia Eventos avançados dentro do aplicativo</Anchor>.

[![Fluxograma_da_jornada_do_usuário_do_aplicativo_de_educação_on-line_para_eventos_recomendados](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

<div id="recommended-structures-for-predefined-events" />

## Estruturas recomendadas para eventos predefinidos

A seção a seguir oferece uma lista de estruturas de eventos que são típicas da vertical de educação online. Cada estrutura inclui um nome de evento predefinido e os parâmetros de evento sugeridos a serem usados. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Propósito**

Entenda a retenção de seus usuários registrados

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

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Conclusão do tutorial (af_tutorial_complete)">

**Propósito**

Gravar esse evento pode ajudar a determinar:

* Com quais tópicos os usuários podem ter problemas
* Quais tutoriais não têm boa performance e aprimorá-los.
* Associar a atividade geral do usuário com dimensões como receita

**Trigger**

* Quando um usuário conclui um tutorial
* Quando um usuário inicia um tutorial, mas sai sem concluí-lo

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| af\_success | Se o usuário concluiu o tutorial | Sim |
| af\_tutorial\_id | ID do tutorial | 3 |
| af\_content | Nome do tutorial | álgebra |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Propósito**

O registro de compras in-app feitas pelos usuários pode ajudar a:

* Descobrir o LTV de seus usuários e o ROI de suas campanhas em ad networks e agências de anúncios
* Descobrir quais ofertas são mais populares entre os seus usuários
* Fazer referência cruzada de campanhas com itens comprados para otimizar o direcionamento de campanhas

To record and validate this event, see <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Purchase and subscription validation</Anchor>.

**Gatilho**

Quando o usuário acessa a página de agradecimento após uma compra bem-sucedida

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">af\_revenue</Anchor> | A receita estimada de uma compra | 250.99 |
| af\_currency | Código da moeda | USD |
| af\_content\_id | ID do item | 001, 092 |
| order\_id | ID do pedido | 9277 |
| af\_receipt\_id | ID do recibo | 9277 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Estruturas recomendadas para eventos personalizados

A seção a seguir fornece uma lista de estruturas de eventos que incluem nomes de eventos personalizados e os parâmetros de eventos sugeridos para usar. Observe que os eventos in-app podem incluir quaisquer parâmetros de evento que atendam às necessidades da sua empresa.

<div id="complete-exercise-complete_excercise" />

<Accordion title="Exercício completo (complete_excercise)">

**Propósito**

Registrar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários começam, mas não terminam um exercício.

**Trigger**

Quando o usuário completa um exercício

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| course\_name | Nome do curso | álgebra |
| exercise\_name | Nome do exercício | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="Curso completo (course_completed)">

**Propósito**

Gravar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários começam, mas não terminam um curso.

**Trigger**

Quando o usuário completa um curso

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| course\_name | Nome do curso | álgebra |
| course\_completed | Se o curso foi concluído | Sim |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="Certificado emitido (certificate_issued)">

**Propósito**

Registrar esse evento e compará-lo com outros dados para saber mais sobre seus usuários. Por exemplo, você pode saber quantos usuários terminam um curso e redirecioná-los para o próximo.

**Trigger**

Quando um certificado é emitido para o usuário

**Parâmetros do evento**

| Nome | Descrição | Valor de exemplo |
| --- | --- | --- |
| course\_name | Nome do curso | álgebra |
| certificate\_received | Se o certificado foi emitido | Sim |

</Accordion>

<div data-zendesk-anchors="online-education=-educa%C3%A7%C3%A3o-online h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=-educa%C3%A7%C3%A3o-online h_01HGTAYQ9VJ6GS1XVQPG198C8Z=importante recommended-structures-for-predefined-events=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAYQ9VS0DYFSFNEPDCDVTG=estruturas-recomendadas-para-eventos-predefinidos h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=estruturas-recomendadas-para-eventos-personalizados h_01HGTAYQ9V93HET4AZ7XGE0E3V=estruturas-recomendadas-para-eventos-personalizados h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
