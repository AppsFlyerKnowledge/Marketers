---
title: >-
  Usando Firebase e Google Tag Manager com AppsFlyer—Configuração do Google Tag
  Manager
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2026-08-19T00:12:04Z'
  id: 4410481509393
  locale: pt
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/pt/articles/4410481509393
---
> **At a glance:** **Numa olhadela:** Instruções para configurar o envio de eventos, reportados via Firebase SDK, para AppsFlyer no Google Tag Manager.

<div id="google-tag-manager-setup" />

## Configuração do Google Tag Manager

Esta secção discute a configuração necessária na interface do utilizador do Google Tag Manager (GTM). Todos os passos descritos nesta secção são necessários para que o GTM envie eventos para AppsFlyer. Siga os passos pela ordem indicada.

Os seguintes passos são para o Google Tag Manager em aplicações móveis. Se a interface do seu Google Tag Manager for diferente das capturas de ecrã nos vários passos, verifique o seguinte:

1. O conteúdo do seu Google Tag Manager está configurado para aplicações móveis.
2. O contentor é o v5. Para mais informações, clique <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7003315">aqui</Anchor>.

> 📘 **Note**
>
> **Atenção**
>
> Os passos descritos nesta secção referem-se a um evento de compra, mas são relevantes para qualquer evento que deseje enviar.

<div id="1-creating-event-parameter-variables" />

<Accordion title="1. Criar variáveis de parâmetros de eventos">

As variáveis de parâmetros de eventos permitem que o Google Tag Manager obtenha dados do evento. Quando o evento é enviado, as variáveis ID do AppsFlyer e Dev Key são passadas junto com ele. O Google Tag Manager avalia então o valor dessas variáveis e é assim que as obtém. Os dados do evento têm duas funções:

1. Fornecer ao Google Tag Manager o ID do AppsFlyer e a Dev Key
2. Fornecer ao Google Tag Manager o nome do evento e os parâmetros do evento

<Tabs>
<Tab title="ID do dispositivo AppsFlyer e Dev Key Receita e Preço">

Sempre que o Google Tag Manager enviar um evento para o AppsFlyer, deve enviá-lo com o ID do AppsFlyer e a Dev Key. A Dev Key permite que o Google Tag Manager comunique com os servidores do AppsFlyer. O ID do AppsFlyer permite que o AppsFlyer saiba a qual utilizador atribuir o evento.

1. No Google Tag Manager, clique em ***Variáveis*** e depois em ***Novo***
2. Dê o nome à variável de "Chave de Desenvolvedor AppsFlyer" e clique em ***Configuração da Variável***.
3. Escolha ***Parâmetro de Evento***.
4. Escolha ***Parâmetro Personalizado***.
5. No campo ***Parâmetro de Evento*** , introduza "dev\_key" e guarde.
6. Repita o processo para o ID AppsFlyer também - nomeie a variável de "ID do Dispositivo AppsFlyer" e introduza "af\_id" no campo ***Parâmetro de Evento*** .

> 📘 **Note**
>
> **Exemplo**
>
> Abaixo está uma captura de ecrã da interface do GTM. Mostra a configuração final do parâmetro de evento:
>
> <Image align="center" alt="event_parameter_variable_dev_key.png" src="https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png" />

> 🚧 **Important**
>
> **Importante!**
>
> Para iOS, deve ser configurado um Parâmetro de Evento adicional. Siga o mesmo fluxo listado acima. Crie uma variável e nomeie-a "Apple App ID". No campo Parâmetro de Evento, introduza "apple\_app\_id" e guarde.

O próximo passo é criar e definir as variáveis ID e Chave de Desenvolvedor AppsFlyer dentro da aplicação. Este passo é discutido na secção <Anchor target="_blank" href="/marketers/pt/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#configurar-eventos-no-app">Envio de Eventos</Anchor>.

</Tab>

<Tab title="Receita e preço">

A maioria dos eventos in-app requer parâmetros de valor de evento. Neste caso, são os parâmetros af\_revenue e af\_price, mas pode enviar quaisquer parâmetros de evento. Agora que o evento está configurado na aplicação, é necessário criar variáveis de receita e preço no Google Tag Manager. Estas variáveis serão usadas mais tarde na tag de evento de Compra.

1. No Google Tag Manager, crie duas variáveis de Parâmetro de Evento para af\_revenue e af\_price.
2. Para "af\_revenue", nomeie a variável "Receita" e defina a ***Chave do Parâmetro de Evento*** para "af\_revenue".
3. Para "af\_price", nomeie a variável "Preço" e defina a ***Chave do Parâmetro de Evento*** para "af\_price".

> 📘 **Note**
>
> **Exemplo**
>
> Abaixo está uma captura de ecrã da interface do GTM. Mostra a configuração final do parâmetro de evento:
>
> <Image align="center" alt="event_parameter_variable_revenue.png" src="https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png" />

> 📘 **Note**
>
> **Atenção**
>
> O exemplo aqui mostra como criar variáveis de parâmetro de evento para os parâmetros de evento Receita e Preço. Pode criar variáveis de parâmetro de evento para qualquer tipo de parâmetro de evento, de acordo com o evento que é enviado.

</Tab>
</Tabs>

</Accordion>

<div id="2-creating-a-trigger-for-the-purchase-event" />

<Accordion title="2. Criar um gatilho para o evento de compra.">

Para que o Google Tag Manager saiba se o evento deve ser enviado para o AppsFlyer, um disparador para o evento deve ser configurado.

1. No Google Tag Manager, clique em ***Disparadores*** e depois em ***Novo***.
2. Nomeie o disparador como "Compra" e clique em ***Configuração do Disparador***.
3. Escolha ***Personalizado***.
4. Escolha ***Alguns Eventos***.
5. Nas condições, defina o disparador para ser ativado quando o ***Nome do Evento*** for igual a "af\_purchase".
6. Clique em ***Salvar***.

> 📘 **Note**
>
> **Exemplo**
>
> Abaixo está uma captura de ecrã da interface do GTM. Aqui está a configuração final do disparador:
>
> <Image align="center" alt="trigger_purchase_event.png" src="https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png" />

</Accordion>

<div id="3-creating-a-tag-for-the-purchase-event" />

<Accordion title="3. Criar um tag para o evento de compra">

Agora que as variáveis necessárias e o disparador do evento estão configurados, você pode criar o tag para o evento de Compra.

1. No Google Tag Manager, clique em ***Tags*** e depois em ***Novo***.
2. Nomeie o tag como "Compra" e clique em ***Configuração do Tag***.
3. Escolha ***AppsFlyer***.
4. No campo ***ID da Aplicação*** , defina a variável interna do ID da App.

   > 🚧 **Important**
   >
   > **Importante!**
   >
   > Para iOS, defina a variável personalizada "apple\_app\_id" no campo ***ID da Aplicação*** .

5. No campo ***Chave de Desenvolvedor*** , escolha a variável "AppsFlyer Dev Key".
6. No campo ***ID do Dispositivo AppsFlyer*** , escolha a variável "AppsFlyer Device ID".
7. No campo Nome do Evento, defina a variável interna ***Nome do Evento***.
8. No campo ***Moeda do Evento*** , defina o código da sua moeda, por exemplo, USD.
9. Clique duas vezes em ***Adicionar Valor do Evento***.
10. Nota
11. Na ***secção de Disparos***, defina o ***Disparador de Ativação*** para o disparador do evento "Compra".
12. Clique em ***Salvar***.

> 📘 **Note**
>
> **Exemplo**
>
> Abaixo está uma captura de ecrã da interface do GTM. Aqui está a configuração final do Tag:
>
> <Image align="center" alt="purchase_tag.png" src="https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png" />

</Accordion>

<div id="4-publishing-the-tag-manager-container" />

<Accordion title="4. Publicação do container do tag manager">

Após cada alteração no Google Tag Manager (adição de tags, etc.), você deve baixar o container e adicioná-lo à pasta raiz da sua aplicação:

* Android - app/src/main/assets/containers
* iOS - pasta raiz/container

Compile e instale a aplicação num dispositivo de teste e verifique o log de depuração para ver se o evento é ativado e enviado.

</Accordion>

<div data-zendesk-anchors="google-tag-manager-setup=configura%C3%A7%C3%A3o-do-google-tag-manager h_01HE7SFG97FKSVAY5QHVHGF3GV=configura%C3%A7%C3%A3o-do-google-tag-manager h_01HE7SFG97YVYNT385MNFA9ECN=1-creating-event-parameter-variables h_01HE7SFG98XGBMTA7ZF8XSNF29=2-creating-a-trigger-for-the-purchase-event h_01HE7SFG98R4DGTRWXE247MRPK=3-creating-a-tag-for-the-purchase-event h_01HE7SFG98R2KGRRDA9TQTYD3B=4-publishing-the-tag-manager-container" />
