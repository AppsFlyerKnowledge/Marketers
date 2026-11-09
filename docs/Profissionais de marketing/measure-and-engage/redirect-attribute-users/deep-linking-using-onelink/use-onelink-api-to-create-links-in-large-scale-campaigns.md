---
title: Use a OneLink API para criar links em campanhas de grande escala
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-10-29T01:24:07Z'
  id: 360001250345
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** a OneLink API te ajuda a engajar usuários finais usando suas mídias próprias, criando links personalizados em campanhas em grande escala, via SMS e mais. Use-o para criar jornadas integradas e sem fricção entre canais, aprofundar o engajamento e melhorar a conversão.

<div id="about-onelink-api" />

## OneLink API

A API OneLink é um recurso premium que permite transformar qualquer canal próprio em um caminho direto para o seu app mobile. Ao gerar links curtos personalizados de forma programática, você pode oferecer jornadas do usuário customizadas em escala, aprofundar o engajamento e impulsionar mais conversões em SMS, e-mail, sites, posts sociais e muito mais. Forneça o OneLink ID e a chave da OneLink API ao desenvolvedor.

* https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link
* Parâmetros relacionados à atribuição, usados para mensurar e monitorar esforços de marketing, como canal de mídia, campanha e asset.**Atenção**: O parâmetro de canal de mídia (pid) é obrigatório.
* Parâmetros de personalização, que permitem configurar uma experiência de usuário personalizada ao abrir o aplicativo a partir de um link relevante. Esses parâmetros permitem que você envie usuários para um conteúdo personalizado no aplicativo. Por exemplo, uma página de produto específica, código de cupom ou promoção.
* Gere grandes volumes de links curtos e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-qr">QR codes</Anchor> automaticamente.
* Personalize o TTL (Time To Live) e o comportamento de renovação por caso de uso. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-onelink-short-url-ttls-automatically-extend">Saiba mais</Anchor>
* Aplique uma validação rigorosa de parâmetros para garantir um comportamento de redirecionamento previsível e uma mensuração confiável.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">Consulte o uso da cota</Anchor> para gerenciar o consumo.

<div id="example" />

> 📄 **Exemplo**
>
> Um aplicativo global de viagens gera milhões de links curtos contextuais diariamente em experiências de CRM, e-mail e QR. Usando a API OneLink v2.0, a plataforma de automação cria deep links por usuário que respeitam localidade, nível de fidelidade e destinos específicos in-app — ao mesmo tempo em que mantém a governança e a mensuração consistente em todos os mercados. Copie o ID do template do OneLink.

<div id="get-started" />

## Iniciar

**A OneLink API é um recurso premium que é usado para:**

**Pré-requisito:** Uma conta da AppsFlyer. Para acessar a API OneLink, fale com o seu CSM ou envie uma mensagem para hello@appsflyer.com.

**Para configurar a OneLink API:**

1. Copie o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#tipos-de-token">token da OneLink API</Anchor>.
2. <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Crie um template do OneLink</Anchor>.
3. Todas as solicitações feitas após ultrapassar essa cota não são atendidas, e os links não são criados; a chamada de API recebe o código de erro 429 com a mensagem "Cota mensal excedida".  

   <Image align="center" alt="" src="https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg" />
4. Compartilhe o ID do template e o token da API com o desenvolvedor e peça que ele siga estas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">instruções</Anchor>.

<div id="dashboard" />

## **Painel**

O dashboard da OneLink API exibe seu uso diário, mensal e trimestral da API. Isso ajuda você a monitorar seu consumo em relação ao limite da cota mensal. 

Para visualizar o dashboard da OneLink API: 

Na AppsFlyer, no menu lateral, selecione **Engajar** > **OneLink API**.

<div id="use-cases" />

## casos de uso

Os casos de uso a seguir destacam formas comuns de usar a API OneLink para criar jornadas contextuais e sem fricção no seu aplicativo.

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<Accordion title="Jornadas entre plataformas (CTV, desktop, web-to-app)">

Gere links de curta duração ou por sessão que ajudam os usuários a transitar sem fricção entre dispositivos. Exemplos comuns incluem QR codes em anúncios de TV ou fluxos de “escanear para continuar” no desktop que levam os usuários diretamente para a etapa correta in-app.

**Valor:** Continuidade sem fricção e melhor conversão entre dispositivos.

</Accordion>

<div id="crmpowered-channels-sms-email-whatsapp" />

<Accordion title="Canais impulsionados por CRM (SMS, e-mail, WhatsApp)">

Crie links curtos personalizados por usuário no momento do envio para mensagens de alta intenção, como alertas de queda de preço, listas de espera, reconquista de usuários, lembretes de cobrança ou fluxos de login mágico.

**Valor:** Personalização em escala com atribuição consistente.

</Accordion>

<div id="offline-and-qrbased-engagement" />

<Accordion title="Engajamento offline e baseado em QR">

Produza links escaneáveis para materiais em loja, recibos, embalagens ou sinalização de eventos. Você pode atualizar as configurações de destino sem reimprimir os materiais físicos.

**Valor:** Roteamento dinâmico e atribuição offline sem reimprimir os materiais físicos.

</Accordion>

<div id="referral-and-advocate-sharing" />

<Accordion title="Compartilhamento de indicações e de defensores">

Ative links curtos compartilháveis para programas de indicação de influenciadores, criadores ou clientes, com parâmetros personalizáveis e roteamento pronto para atribuição.

**Valor:** Mensuração escalável e atribuição precisa para indicações.

</Accordion>

<div id="traits-and-limitations" />

## **Características e limitações**

Esta seção lista algumas das principais características e limitações da API OneLink. Diga ao desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">instruções no dev hub</Anchor>.

| Caraterística | Considerações |
| --- | --- |
| Limite de cota da API | <ul><li>O limite de uso da OneLink API para criar, editar ou excluir links do OneLink é de 7,5 milhões por mês (fuso horário UTC), por conta.</li><li>As solicitações POST, PUT e DELETE contam para esse limite. As solicitações GET e GET QR não contam para a cota.</li><li>Todas as solicitações feitas após exceder essa cota não são atendidas; a chamada de API recebe o código de status 429 com a mensagem "Monthly quota exceeded".</li><li>Você pode verificar quanto da cota foi usado/quanto ainda resta de uma destas formas:<br />• Acessando a página da API OneLink na plataforma AppsFlyer para ver o histórico de uso dos últimos 4 meses, ou<br />• Usando a API GET quota para recuperar o status atual da sua cota.<br />Você também pode usar a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">API GET quota</Anchor> para acionar alertas internos quando seu uso se aproximar do limite definido.</li></ul> |
| Visibilidade do link | <ul><li>Os links criados por meio da API não aparecem na lista de links personalizados do OneLink no dashboard da AppsFlyer.</li></ul>af\_dp |

<div data-zendesk-anchors="h_01HJR5MAKKNH236MVDZ03X1B1P=onelink-api h_01HJR5MAKKTDRPS0WQ44VN594X=exemplo get-started=iniciar h_01KATK4KWTGSHTW5BEY8TEE5JD=iniciar dashboard=painel h_01KATKWCPHZB1MKCJ8DVDYZ1B3=painel use-cases=casos-de-uso h_01KAGQNZZA0NM19KV29QZ9ZDKP=casos-de-uso h_01KBJ92FSTKCH9KXGWKJAF1DFH=crossplatform-journeys-ctv-desktop-webtoapp h_01KBJ92FST51NKDB465N76EX3M=crmpowered-channels-sms-email-whatsapp h_01KBJ92FST5H7V5S13TZ502VJV=offline-and-qrbased-engagement h_01KBJ92FST4FP4ZES5T643DD3R=referral-and-advocate-sharing traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KAGQP00QZ2VBE9EY3SNPHGBP=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
