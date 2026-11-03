---
title: Gerador de eventos in-app
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
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2026-08-18T00:13:47Z'
  id: 10457123447953
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/10457123447953
---
> **Visão geral:** crie automaticamente o código do aplicativo (nativo do Android e iOS, Unity) para enviar eventos in-app, definindo os nomes e o conteúdo dos eventos de acordo com suas necessidades de negócios.

## Introdução

Os eventos in-app são uma ferramenta importante para **os proprietários de aplicativos medirem a qualidade de seus usuários provenientes de diferentes fontes** com base nas ações que eles executam após a instalação do aplicativo. Os eventos também costumam ser usados para realizar campanhas de marketing baseadas em CPA.

No entanto, muitas vezes, mais de uma pessoa está envolvida na definição e integração de eventos in-app nos aplicativos. Embora o profissional de marketing/gerente de produto defina o conteúdo do conjunto de eventos de acordo com as necessidades de negócios, geralmente é necessário que um ou mais desenvolvedores mobile implementem a API de eventos in-app em seus aplicativos.

O <Anchor target="_blank" href="https://evgen.appsflyer.com/">gerador de eventos in-app</Anchor> da AppsFlyer **resolve os desafios inerentes a essa colaboração essencial entre o profissional de marketing e o desenvolvedor**.

Ao usar o gerador de eventos in-app, os profissionais de marketing podem:

* Usar um **conjunto recomendado predefinido de eventos** e parâmetros para sua vertical.
* Adicionar ou remover eventos/parâmetros, descrições, acionadores e exemplos predefinidos ou personalizados para referência.
* **Enviar código gerado automaticamente** para seus desenvolvedores mobile Android e iOS– **economizando dias de trabalho,** comunicação redundante e possíveis erros.
* **Reutilizar seu trabalho** se eles atualizarem eventos posteriormente, adicionarem novos eventos ou adicionarem novos aplicativos.

## Usar o gerador de eventos in-app

**Use o gerador de eventos in-app para criar um conjunto de eventos para um novo aplicativo ou para atualizar um conjunto existente.**

### Criar um novo conjunto de eventos

**Para criar um novo conjunto de eventos:**

1. Acesse o <Anchor target="_blank" href="https://evgen.appsflyer.com/">gerador de eventos in-app</Anchor> e insira o nome do seu aplicativo.
2. Selecione uma vertical ou importe o conjunto de eventos de um aplicativo semelhante que foi exportado anteriormente para um arquivo JSON.
3. Adicione ou remova eventos e parâmetros, de acordo com as necessidades do seu negócio.
4. Clique no botão **`</>` Code** para visualizar e copiar o código gerado para seus desenvolvedores: Java (nativo Android), Obj-C/Swift (nativo iOS) ou C# (Unity).
5. Clique em **Download .zip** para salvar o conjunto de eventos para uso futuro ou para colaborar com desenvolvedores e colegas.

### Atualizar um conjunto de eventos existente

**Para atualizar um conjunto de eventos existente:**

1. Acesse o <Anchor target="_blank" href="https://evgen.appsflyer.com/">gerador de eventos in-app</Anchor>.
2. Importe um conjunto de eventos do seu aplicativo que foi exportado anteriormente para um arquivo JSON.
3. Adicione ou remova eventos e parâmetros, de acordo com as necessidades do seu negócio.
4. Clique no botão **`</>` Code** para visualizar e copiar o código gerado para seus desenvolvedores: Java (nativo Android), Obj-C/Swift (nativo iOS) ou C# (Unity).
5. Clique em **Download .zip** para salvar o conjunto de eventos para uso futuro ou para colaborar com desenvolvedores e colegas.

### Adicionar eventos

**Para adicionar um novo evento ao conjunto de eventos:**

1. Clique no botão **+ Evento**. O novo evento aparece na parte inferior do conjunto de eventos.
2. Selecione um evento **pré-definido** na lista de eventos sugeridos (recomendado) ou clique em **Personalizado** para definir seu próprio nome de evento. Verifique se o nome do evento ainda não existe no conjunto de eventos.
3. Informe o objetivo do evento, descrevendo o cenário do negócio.
4. Insira a ação do acionador para o evento, explicando o tempo na jornada do usuário em que o evento deve ser enviado. Esta explicação é adicionada como um comentário no código gerado para pelos desenvolvedores rápida referência.
5. [Opcional] Adicione um ou mais parâmetros ao evento.

### Adicionar parâmetros

**Para adicionar um novo parâmetro ao conjunto de eventos:**

1. Clique no botão **+ Adicionar parâmetro** para o evento relevante.
2. Selecione um parâmetro **predefinido** na lista sugerida de parâmetros (recomendado).
3. Caso contrário, clique em **Custom** para definir seu próprio nome de parâmetro e pressione **Enter**.
4. Digite um ou mais valores de parâmetros típicos para referência.
5. Para ajudar seus desenvolvedores, digite uma descrição geral, tipo de campo ou a fonte correspondente para o valor do parâmetro em seu aplicativo. Isso aparece como um comentário para cada parâmetro de evento no código gerado.

**Observação**: <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#predefined-and-custom-events">a nomenclatura predefinida</Anchor> permite o mapeamento automático de eventos e parâmetros para parceiros e é o método recomendado.

> 📄 **Veja também**
>
> * Painel de eventos

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HE7T0ZA12E7KHS7WBQ757KF1=introdu%C3%A7%C3%A3o using-the-inapp-event-generator=usar-o-gerador-de-eventos-in-app h_01HE7T0ZA2A1KS4NF43GRZB87X=usar-o-gerador-de-eventos-in-app creating-a-new-event-set=criar-um-novo-conjunto-de-eventos h_01HE7T0ZA2KQ44P40Y028VVA4K=criar-um-novo-conjunto-de-eventos updating-an-existing-event-set=atualizar-um-conjunto-de-eventos-existente h_01HE7T0ZA2P2WZ07CT880ZSK0Z=atualizar-um-conjunto-de-eventos-existente adding-events=adicionar-eventos h_01HE7T0ZA2Z3D3J014E7E0T13X=adicionar-eventos adding-parameters=adicionar-par%C3%A2metros h_01HE7T0ZA2KAH7N44EQ9W5BH5G=adicionar-par%C3%A2metros h_01HE7T4ZR4AY2J71B3PJKJP490=veja-tamb%C3%A9m" />
