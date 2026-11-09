---
title: Configuração de postback de eventos in-app
metadata:
  keywords:
    - In-App Events
    - Advertisers
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
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-09-28T00:13:32Z'
  id: 208439256
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/208439256
---
> **Resumo:** mensure o engajamento no aplicativo, a qualidade dos seus usuários e otimize campanhas usando dados de eventos in-app.

<div id="overview" />

## Visão geral

Os eventos in-app permitem que os profissionais de marketing mensurem o engajamento no aplicativo e a qualidade do usuário de diferentes canais, para que eles criem uma estratégia de aquisição de usuários apropriada. As ad networks usam informações de eventos in-app para otimizar campanhas e executar campanhas de custo por ação/evento. As ad networks recebem dados de eventos in-app por meio de postbacks, que são enviados em tempo real. <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Saiba mais sobre eventos in-app avançados</Anchor>.

<div id="postback-in-app-event-selection" />

## Seleção de eventos in-app em postbacks

Os profissionais de marketing podem selecionar quais eventos in-app querem enviar por postback para ad networks, usando as configurações descritas neste artigo.

<div id="note" />

> 📘 **Atenção**
>
> * Eventos in-app incluem **eventos rejeitados**, ou seja, eventos in-app bloqueados pelo Protect360 ou eventos que não estão em conformidade com as regras de validação de destino.
> * Se a seção **Postbacks de eventos in-app** não aparecer na aba **Integração**, isso significa que o parceiro ainda não configurou os registros de eventos in-app com a AppsFlyer durante a configuração preliminar. O parceiro pode entrar em contato com a AppsFlyer utilizando o <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget do assistente de parceiro</Anchor> para concluir a integração.

<div id="in-app-event-postback-window" />

## Janela de postback de eventos in-app

A janela de postbacks de eventos in-app permite que os profissionais de marketing que trabalham com ad networks em <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#cpa">CPA (custo por aquisição)</Anchor> configurem janelas de pós-conversão após as quais os postbacks de eventos não são mais enviados.

Por exemplo, se você for cobrado por eventos que ocorram dentro de 15 dias após a instalação de um usuário, defina a janela da seguinte forma:

<Image align="center" alt="Janela de postback de evento in-app definida como 15 dias" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

Os postbacks após esse período não são enviados, e a network não é notificada, mas a AppsFlyer ainda registra os eventos e os atribui à ad network.

Os postbacks são sempre enviados com base na configuração da janela **atual**. Veja o exemplo a seguir:

| 1 de janeiro | A janela é de 15 dias.<br /><br />Um usuário instala um aplicativo. |
| --- | --- |
| 2 de janeiro | A janela é alterada para 10 dias. |
| 14 de janeiro | O usuário faz uma compra.<br /><br />O postback não é enviado para a ad network porque o evento não se enquadra na janela atual (10 dias). |
| 15 de janeiro | A janela é alterada para 20 dias. |
| 18 de janeiro | O usuário faz outra compra.<br /><br />Desta vez, o postback é enviado, porque o evento se enquadra na janela atual (20 dias). |

<div id="note-1" />

> 📘 **Atenção**
>
> Quando você seleciona a [**configuração Todos os canais de mídia, incluindo orgânico**](#opções-para-envio-de-postbacks), o parceiro que a configurou recebe um postback para cada evento de conversão que o anunciante recebe. Isso acontece mesmo que o anunciante tenha atribuído o evento a outro parceiro, desde que o evento tenha ocorrido dentro da janela de postback que a AppsFlyer define para o parceiro que configurou a configuração.

<div id="default-postback-window" />

### Janela de postback padrão

Quando se começa a configurar os postbacks de eventos in-app, a janela padrão é automaticamente definida para seis meses.

<div id="note-2" />

> 📘 **Atenção**
>
> Se você começou a usar postbacks de eventos in-app com um parceiro específico antes de 30 de julho de 2019, a janela padrão é vitalícia. Isso significa que postbacks de eventos in-app sempre são enviados.

<div id="who-can-configure-postback-windows" />

### Quem pode configurar janelas de postback

As seguintes funções podem configurar janelas de postback:

* Profissionais de marketing
* Agências, se receberem a **permissão** de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">configurar postbacks de eventos in-app</Anchor>.  
  **Observação:** um profissional de marketing e uma agência que trabalham com a mesma ad network podem configurar janelas de postback separadamente, com base em seus contratos com a network.
* Parceiros, se receberem a **permissão** de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">configurar postbacks de eventos in-app</Anchor>.

<div id="event-mapping" />

## Mapeamento de eventos

Cada profissional de marketing pode dar um nome diferente a um evento do mesmo tipo. Esses nomes de eventos também podem ser diferentes dos nomes dos parceiros.

Por exemplo, quando um usuário compra algo através de um aplicativo, um profissional de marketing pode chamá-lo de `purchase`, ou uma identificação menos informativa, como `event5`, enquanto um parceiro pode chamá-lo de `purchase_event`

Para garantir que os eventos do profissional de marketing correspondam aos mesmos eventos dos parceiros, os nomes dos eventos devem ser mapeados.

<div id="note-3" />

> 📘 **Atenção**
>
> Os eventos mapeados na aba integração para um parceiro específico se aplicam tanto a postbacks padrão quanto a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postbacks da SKAdNetwork (SKAN).</Anchor>

<div id="mapping-methods" />

### Métodos de mapeamento

Cada parceiro decide qual dos métodos a seguir deve ser usado para mapear seus eventos in-app:

* [Inserir o ID do evento do parceiro](/docs/in-app-event-postback-configuration#enter-the-partner-event-id)
* [Selecionar o ID do evento na lista](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Enviar eventos como eles estão (não mapeados)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

<div id="note-4" />

> 📘 **Atenção**
>
> * Nem todos os métodos de mapeamento aparecem para todos os parceiros
> * Você pode [dar permissão ao parceiro](/docs/in-app-event-postback-configuration#mapeamento-de-eventos-por-ad-networks) para fazer o mapeamento propriamente dito.

<Accordion title="ptInserir o ID do evento do parceiro">

* **Evento da AppsFlyer**: a partir da lista de eventos do seu aplicativo, selecione um evento.
* **mapeado para o evento do parceiro**: no campo de texto, insira o ID do evento conforme recebido do parceiro que corresponde ao seu evento do aplicativo (evento da AppsFlyer)

<div id="note-5" />

> 📘 **Importante!**
>
> * Os nomes dos eventos são sensíveis a maiúsculas e minúsculas. Para evitar discrepâncias, certifique-se de usar o nome de evento correto para todas as fontes de mídia e versões do aplicativo.
> * Ao digitar um nome de evento, você pode usar espaços sublinhados (underline, ou traços baixos) antes ou depois do nome do evento. Utilize os espaços sublinhados somente se o nome do evento enviado pela AppsFlyer tiver os mesmos espaços sublinhados.

<Image align="center" alt="Inserção de um ID de evento no campo de texto de mapeado para o evento do parceiro" src="https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png" />

</Accordion>

<Accordion title="Selecione um ID de evento a partir da lista">

* **Evento da AppsFlyer**: a partir da lista de eventos do seu aplicativo, selecione um evento.
* **Mapeado para o evento do parceiro**: Selecione da lista de eventos de parceiros predefinidos o evento que corresponde ao evento da sua aplicação (o evento AppsFlyer).

<Image align="center" alt="Seleção de um evento predefinido do parceiro na lista suspensa de ID do evento" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

</Accordion>

<Accordion title="Envie eventos como eles estão (não mapeados)">

Alguns parceiros preferem receber postbacks de eventos in-app não mapeados, o que significa que os nomes dos eventos são enviados da forma como são nomeados no seu aplicativo. Não importa se o evento é chamado `purchase`, `acquisition` ou `event5`.

Você pode escolher quais eventos não mapeados você quer enviar para o parceiro:

* **Adicionar manualmente:** Selecione eventos específicos.
* **Enviar todos os eventos (exceto desinstalações e sessões)**. Isso não inclui desinstalações, sessões (inicializações do aplicativo), e o evento `af_app_open`.

<div id="note-6" />

> 📘 **Importante!**
>
> Para evitar que os anunciantes compartilhem informações demais sem querer com plataformas de plataforma de analytics de terceiros, removemos a opção **Enviar todos os eventos (exceto desinstalações e sessões)** dessas plataformas a partir de março de 2019. As plataformas analíticas configuradas antes desta data ainda mantêm essa opção de configuração.

**Para adicionar eventos manualmente:**

1. Clique em **Adicionar evento**.
2. Selecione as opções de postback:
   * **Evento da AppsFlyer**: a partir da lista de eventos do seu aplicativo, selecione um evento.
   * **para usuários de**: selecione a [opção de envio](/docs/in-app-event-postback-configuration#opções-para-envio-de-postbacks) para o evento.
   * **Incluindo**: Selecione [quais dados incluir](/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks) no postback.
3. Repita esse procedimento para mais eventos.

<Image align="center" alt="Adição manual de eventos não mapeados com opções de envio e inclusão de dados" src="https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png" />

**Para enviar todos os eventos:**

1. Selecione **Enviar todos os eventos (exceto desinstalações e sessões)**.
2. Selecione as opções de postback:  
   * **Para usuários de**: Escolha a [opção de envio](/docs/in-app-event-postback-configuration#opções-para-envio-de-postbacks) para todos os eventos.
   * **Incluindo**: Escolha [quais dados incluir](/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks) para todos os eventos no postback.

<Image align="center" alt="Envio de todos os eventos não mapeados sem mapeamento individual de eventos" src="https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png" />

</Accordion>

Para mais informações sobre o mapeamento de eventos, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>.

<div id="options-for-sending-postbacks" />

### Opções para envio de postbacks

Para cada evento, você pode escolher em qual caso enviar os postbacks (dentro da janela do postback):

* **Somente este parceiro**: Envie postbacks somente quando o evento for atribuído a este parceiro, ou seja, quando o usuário que o realizou vier deste parceiro.
* **Todos os canais de mídia, incluindo orgânico**: Envie postbacks para todos os canais de mídia em eventos atribuídos a qualquer parceiro e para eventos orgânicos, ou seja, quando o usuário que o realizou vier de qualquer canal de mídia. **Observação**: Quando **Todos os canais de mídia, incluindo orgânico** estiver selecionado, os postbacks de outros parceiros não conterão dados de atribuição.

<div id="data-to-include-in-the-postbacks" />

### Dados a incluir nos postbacks

Você pode escolher que tipo de dados de eventos você deseja compartilhar com o parceiro no postback. Escolha uma das seguintes opções:

* **Sem valores e sem receita**: Envie apenas o evento em si, sem qualquer parâmetro (valores ou receita).
* **Com valores e sem receita**: Envie todos os parâmetros, com **exceção** do valor da receita.
* **Valores e receita**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).
* **Valores, receita & receita líquida**: Envie todos os parâmetros do evento, incluindo os valores de receita e receita líquida (se existirem no evento).

<div id="note-7" />

> 📘 **Importante!**
>
> A opção **Valores, receita e receita líquida** requer uma assinatura **ROI360 Advanced** e está disponível apenas para eventos `af_purchase*` e `af_ars_*`.

É recomendável compartilhar a receita se você quiser que as ad networks otimizem suas campanhas e melhorem os resultados. Entretanto, compartilhar a receita não é obrigatório. Certifique-se de permitir o compartilhamento de receitas somente para eventos que tenham `af_revenue` ou`af_projected_revenue` configurados em seu valor de evento. Caso contrário, as ad networks recebem eventos com um valor de receita vazio.

<div id="share-revenue" />

#### Compartilhar receita

Nos postbacks, `af_revenue` e `af_currency` são escritos fora do JSON do `event_value` como **monetary** e **currency**, e podem ser enviados separadamente. Exemplo de estrutura de postback:

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

Quando a opção **Valores, receita e receita líquida** é selecionada, `af_net_revenue` também pode ser escrita fora do JSON do `event_value` como **net-monetary** e enviada separadamente. Exemplo de estrutura de postback:

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

<div id="note-8" />

> 📘 **Importante!**
>
> Ao escolher **Sem valores e sem receita** ou **Com valores e sem receita**, os respectivos parâmetros são mascarados com N/A.

<div id="tip" />

> 👍 **Observação**
>
> Você também pode configurar seus postbacks de eventos in-app para enviar a receita líquida em vez da receita bruta no parâmetro padrão de receita: **monetary**. Para ter acesso à essa configuração, entre em contato com seu Customer Success Manager (CSM).

<span id="h_01HBZCRNKGBEDSBZEY87KYQ60G"></span>**Exemplo**

Um profissional de marketing envia um evento de compra com o seguinte `event_value`:

```json
{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}
```

A tabela abaixo mostra como os parâmetros são enviados:

| Nome do campo | event\_value | monetário | símbolos monetários | net-monetary |
| --- | --- | --- | --- | --- |
| **Sem valores e sem receita** | N/D | Sequência de caracteres | N/D | Sequência de caracteres |
| **Com valores e sem receita** | `{"af_currency":"N/A","af_content_id":"1234567","af_revenue":"N/A","af_content_type":"category_a"}&monetary=N/A&content_id=1234567` | N/D | N/D | Sequência de caracteres |
| **Valores e receita** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}&monetary=50.87&content_id=1234567` | 50.87 | USD | N/D |
| **Valores, receita e receita líquida** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_net_revenue":35.61,"af_content_type":"category_a"}&monetary=50.87&net-monetary=35.61&content_id=1234567` | 50.87 | USD | 35.61 |

<div id="conditional-in-app-event-postbacks" />

### Postbacks condicionais de eventos in-app

Filtre postbacks de eventos in-app usando várias condições que podem ser mapeadas para diferentes eventos. Somente os eventos que atendem às condições do filtro são enviados aos parceiros, incluindo self-reporting networks (SRNs) e parceiros de analytics. Use esse recurso para:

* Otimizar a segmentação, personalização e retenção de usuários
* Minimizar dados
* Proteger a privacidade dos usuários

<span id="h_01HBZCRNKHRTMHP3JPFVCS8D6N"></span>**Exemplo**

Um profissional de marketing com um aplicativo de gaming quer otimizar campanhas veiculadas por meio de uma ad network, mas apenas para usuários que passam do nível 10 ou do nível 50, ou para usuários que gastam US$3 em compras in-app.

<Image align="center" alt="Exemplo de condições de postback de evento in-app para atingir o nível 10, o nível 50 ou uma compra de US$3" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />

**As condições para esse evento são definidas da seguinte maneira:**

* Quando ***nível*** é igual a ***10***, mapeie para *`fb_mobile_level_acheived`*  
  Caso contrário (**OU**),
* Quando ***nível*** é igual a ***50***, mapeie para *`fb_mobile_level_acheived`*  
  Caso contrário (**OU**),
* Quando ***custo*** é igual a ***3***, mapeie para *`fb_mobile_purchase`*

**Para configurar condições para um evento:**

1. Na página de integração do parceiro, <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">configure e mapeie</Anchor> os eventos in-app necessários para enviar a esse parceiro.
2. Clique no ícone Adicionar condição ![Add condition icon](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) do evento desejado.
3. Insira os campos de condição, como aparecem no <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#event-values">valor do evento</Anchor>:
   * Nome da propriedade
   * Valor
   * Evento parceiro para mapear a condição (usando qualquer uma dessas [opções de mapeamento](/docs/in-app-event-postback-configuration#métodos-de-mapeamento))
4. Você pode adicionar mais condições, certifique-se de inserir todos os campos da condição existente.
5. Clique em **salvar integração.**

<div id="considerations" />

#### Considerações

Ao configurar as condições, certifique-se de que as seguintes considerações sejam atendidas para que o evento seja enviado ao parceiro:

<Accordion title="Estrutura da condição">

* Tanto a propriedade quanto seu valor na condição devem corresponder aos dados do evento.
* Atualmente, as condições só podem ser definidas como "iguais".
* Estruturas complexas, como arrays, não são suportadas.

</Accordion>

<Accordion title="Múltiplas condições para um evento">

* O número máximo de condições por evento é 5.
* Pelo menos uma condição deve ser atendida para que o postback seja enviado, mas apenas uma condição é executada.
* Cada condição é verificada por ordem de aparecimento, e a primeira condição a ser atendida é executada.
* Cada condição é mapeada separadamente. O nome do evento do parceiro é então alterado para **Baseado nas condições**.
* Mais de uma condição pode ter a mesma propriedade ou o mesmo valor, mas nenhuma das duas condições pode ter a mesma propriedade e o mesmo valor.
* Mais de uma condição pode ser mapeada para o mesmo evento.

</Accordion>

<div id="note-9" />

> 📘 **Importante!**
>
> * É recomendável testar esse recurso com um aplicativo de teste ou eventos menores para entender seu impacto na otimização da campanha.
> * Para ver o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">conteúdo do postback</Anchor>, você pode baixar o relatório de postbacks de dados brutos.

<div id="editing-multiple-events" />

### Editando vários eventos

Ao mapear eventos, os valores nos campos **para usuários de** e **incluindo** podem ser editados para vários eventos em uma única ação.

**Para editar vários eventos:**

1. Selecione os eventos a serem atualizados.
2. Clique em **Ações em massa.**
3. Selecione a nova configuração a ser aplicada a todos os eventos selecionados:
   * **Para usuários de** (escolha somente uma opção)
     * Somente este parceiro
     * Todas as fontes de mídia, incluindo orgânicas
   * **Incluindo** (escolha apenas uma opção)
     * Sem dados (padrão)
     * Valores sem receita
     * Valores e receita

<Image align="center" alt="Painel de ações em massa para editar as configurações 'para usuários de' e 'incluindo' em vários eventos" src="https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png" />

<div id="custom-events" />

### Eventos personalizados

A lista de eventos disponíveis para mapeamento mostra apenas os eventos já relatados pelo SDK ou por eventos S2S enviados para a AppsFlyer. Se o evento que você deseja mapear não aparecer na lista suspensa, isso pode acontecer pelos seguintes motivos:

* Nenhum usuário realizou o evento ainda
* A última vez em que o evento ocorreu foi há mais de duas semanas atrás
* Você tem uma grande lista de eventos ativos

**Em qualquer um desses casos, para mapear o evento para o ID do parceiro:**

1. Na lista suspensa, clique em **+ Adicionar item**.
2. Na caixa de texto, insira o nome do evento que deseja adicionar.
3. Clique na marca de seleção para confirmar. O evento que você adicionou agora aparece na lista e pode ser selecionado. ![Confirmação de um novo nome de evento personalizado](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. Associe o evento ao identificador do parceiro.
5. Clique em **Salvar integração** para certificar-se de que o mapeamento será registrado.

<div id="note-10" />

> 📘 **Importante!**
>
> * Adicionar eventos personalizados à página de postback não os extrai automaticamente do seu app. É necessário configurar os eventos no SDK ou S2S para garantir o funcionamento correto. Veja <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#enviar-eventos">como enviar eventos para a AppsFlyer</Anchor>.
> * Quando um evento personalizado é adicionado em um parceiro específico, ele é adicionado à lista de eventos de todos os parceiros, para que você possa vê-lo na lista suspensa de eventos de qualquer parceiro.
> * Veja <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#tips">dicas</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#limitations">limitações</Anchor> para configurar nomes e parâmetros de eventos.

**Agências e ad networks:**

* Não podem adicionar eventos personalizados
* Só podem visualizar e/ou mapear eventos depois que o profissional de marketing adicionou o evento e concedeu as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões</Anchor> necessárias.

<div id="event-mapping-by-ad-networks" />

## Mapeamento de eventos por ad networks

Os profissionais de marketing podem permitir que as ad networks mapeiem os eventos por conta própria. Para isso, um profissional de marketing deve conceder as permissões relevantes à ad network:

1. Na página **Integrações ativas**, encontre o parceiro ao qual você deseja conceder permissão.
2. Na aba Permissões, altere o botão **Permitir configurar postbacks de eventos in-app** para **ON**.

<Image align="center" alt="Botão de alternância de permissão para permitir a configuração de postbacks de evento in-app para uma ad network" src="https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png" />

Depois que a ad network receber as permissões, ela poderá mapear os eventos seguindo as instruções em [Digitar o ID do evento no campo de texto](#métodos-de-mapeamento).

<div id="event-mapping-by-agencies" />

## Mapeamento de eventos por agências

Os profissionais de marketing podem permitir que as agências configurem postbacks de eventos no aplicativo.

<div id="note-11" />

> 📘 **Importante!**
>
> Se tanto o anunciante quanto a agência habilitarem o mesmo postback de evento in-app para a mesma ad network, a AppsFlyer envia o postback uma única vez. Isso evita a duplicação de relatórios para o evento.

**Para dar permissão à agência para configurar postbacks in-app:**

1. Encontre a agência na página **Integrações ativas**.
2. Selecione se a agência pode compartilhar todos os eventos ou somente aqueles atribuídos à ad network específica.
3. Selecione se a agência tem permissão para enviar receitas de eventos.
4. Selecione os eventos específicos que a agência tem permissão para compartilhar.

<Image align="center" alt="Configurações de compartilhamento de eventos e permissão de receita da agência" src="https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png" />

<span id="h_01HDP3XHBPA5GZEVERMBN43JH0"></span>**Veja também**

* <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Eventos in-app avançados, visão geral</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">Eventos in-app avançados, estrutura do evento</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HE0FQ1AB6NQCTKFTDW22SRYC=vis%C3%A3o-geral postback-inapp-event-selection=sele%C3%A7%C3%A3o-de-eventos-in-app-em-postbacks h_01HBZCRNKGH1PAK8RC846PPRTS=sele%C3%A7%C3%A3o-de-eventos-in-app-em-postbacks h_01HBZCRNKGQTJ4VJ00TVTS14N2=aten%C3%A7%C3%A3o inapp-event-postback-window=janela-de-postback-de-eventos-in-app h_01HBZCRNKGS71QGK5506N07K84=janela-de-postback-de-eventos-in-app h_01K9MBNYC6PPHXSZ3KNVNSDASJ=aten%C3%A7%C3%A3o-1 default-postback-window=janela-de-postback-padr%C3%A3o h_01HBZCRNKGV5CREN5K0RBDMBH6=janela-de-postback-padr%C3%A3o h_01HBZCRNKGVXN233AFFHG42NW9=aten%C3%A7%C3%A3o-2 who-can-configure-postback-windows=quem-pode-configurar-janelas-de-postback h_01HBZCRNKG7AECFSBXV2WDD9AR=quem-pode-configurar-janelas-de-postback event-mapping=mapeamento-de-eventos h_01HBZCRNKG7SZ4T41BY60BAJZN=mapeamento-de-eventos h_01HBZCRNKGT64TE2XYK9VS4ATD=aten%C3%A7%C3%A3o-3 mapping-methods=m%C3%A9todos-de-mapeamento h_01HBZCRNKG4EF9MSY696SD5VQ9=m%C3%A9todos-de-mapeamento h_01HBZCVAGPSNDJMWRWENEP45N7=aten%C3%A7%C3%A3o-4 h_01HBZCRNKG1E63DZRSDWTB8CJN=importante h_01HBZCRNKGXJ683VHFTE277ER9=importante-1 options-for-sending-postbacks=op%C3%A7%C3%B5es-para-envio-de-postbacks h_01HBZCRNKG1VN7E6TVCPDW7M73=op%C3%A7%C3%B5es-para-envio-de-postbacks data-to-include-in-the-postbacks=dados-a-incluir-nos-postbacks h_01HBZCRNKGESY50NSZGTVPT25M=dados-a-incluir-nos-postbacks h_01KRKDVVV246YZYGM5G2ZJR63W=importante-2 sharing-revenue=compartilhar-receita 01J9Y0T400M5Z62Q9CKF8M75WR=compartilhar-receita h_01KRKDVVV2YF4XMKNCVEG1FFSG=importante-3 h_01KRKDVVV242YPHP2W8EWTBSMD=observa%C3%A7%C3%A3o conditional-inapp-event-postbacks=postbacks-condicionais-de-eventos-in-app h_01HBZCRNKG5X3B2NJZZP6ER2CX=postbacks-condicionais-de-eventos-in-app considerations=considera%C3%A7%C3%B5es h_01HBZCRNKHBR57YVHZQP7NJBAP=considera%C3%A7%C3%B5es h_01HBZCRNKHF6TFP0N302D7DCMD=importante-4 editing-multiple-events=editando-v%C3%A1rios-eventos h_01HBZCRNKHHD3WC4GTJT9NSJ4C=editando-v%C3%A1rios-eventos custom-events=eventos-personalizados h_01HBZCRNKH754PANWSZ4FMXJVQ=eventos-personalizados h_01HBZCRNKH4PVR3FEMTMERW3M1=importante-5 event-mapping-by-ad-networks=mapeamento-de-eventos-por-ad-networks h_01HBZCRNKH1GCZY17R04WTZ0MQ=mapeamento-de-eventos-por-ad-networks event-mapping-by-agencies=mapeamento-de-eventos-por-ag%C3%AAncias h_01HBZCRNKHHF3E6CZNQQG0Q4VS=mapeamento-de-eventos-por-ag%C3%AAncias h_01K5B6QS6YXKMJSEWE2WFT5AQC=importante-6" />
