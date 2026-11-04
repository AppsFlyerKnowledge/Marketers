---
title: Bundles de marca e configurações de PBA
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
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
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2026-08-18T00:23:43Z'
  id: 360000646498
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360000646498
---
> **Resumo:** os bundles de marca consolidam a atribuição, os eventos, as visitas e a receita de aplicativos e sites relacionados à sua marca. Use a página de configurações de bundles de marca para marcar eventos de conversão, integrar com o Google Ads e muito mais.

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

<div id="about-brand-bundles" />

## Sobre bundles de marca

As marcas operam em um ecossistema que inclui tanto propriedades da web como do mobile. Como anunciante, ter o quadro completo da performance da marca em todas as plataformas–web e mobile–é necessário. No PBA, os bundles de marcas consolidam os dados de propriedades mobile e da web em uma única entidade para fins de análise e acesso aos dados brutos. Etapa 1:

<div id="what-is-a-web-app" />

> 📘 **O que é um aplicativo na web?**
>
> Um aplicativo na web é uma <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">entidade criada por você na AppsFlyer</Anchor> que especifica um site para o qual você deseja mensurar a performance.
>
> * A entidade de aplicativo da web foi adicionada à AppsFlyer em 9 de fevereiro de 2022. Antes dessa data, nossos clientes inseriam o domínio do bundle (pacote) da marca como uma configuração separada ao criar um bundle da marca. Agora, primeiro você cria um aplicativo na web que define o domínio e, em seguida, inclui esse aplicativo web ao criar um bundle.
> * Se você já possuía bundles de marcas em 9 de fevereiro de 2022, você verá que agora há um aplicativo da web na sua página **Meus aplicativos**, que corresponde a cada um desses bundles. **Não se preocupe!** Seu tráfego da web está sendo atribuído exatamente como era antes, e não houve outras alterações nos dashboards do PBA ou nos relatórios de dados brutos.

**Informações básicas sobre o bundle de marca:**

* Um bundle de marca contém exatamente 1 aplicativo da web *(obrigatório)* e 1 ou mais aplicativos mobile *(opcional).*
* Um aplicativo (web ou mobile) pertence a apenas 1 bundle.
* Os aplicativos não podem ser excluídos de um bundle ou movidos de um bundle para outro sem [excluir o bundle original](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle).
  * Na exclusão do bundle, a AppsFlyer deixa de atribuir dados de PBA para o bundle, e o acesso aos seus dados históricos não fica mais disponível.

<div id="accessing-brand-bundles" />

## Acessando bundles de marca

Acesse a página **Bundles de marca** para gerenciar seus bundles de marca e suas configurações:

* Na AppsFlyer, no menu superior, selecione **Meus aplicativos** > **Exibir bundles de marca.**  
                           - ou -
* Na AppsFlyer, no menu lateral, selecione **Configurações** > **Bundles de marca**.

<div id="managing-brand-bundles" />

## Gerenciamento de bundles de marca

Para adicionar, excluir ou gerenciar bundles de marca, selecione uma das opções abaixo na página **Bundles de marca**:

| Opção | Detalhes |
| --- | --- |
| Adicionar um bundle de marca | Abra a página **Criar bundle**  <br />Siga as [instruções abaixo](/docs/pba-brand-bundles-and-settings#add-brand-bundle) para criar um novo bundle. |
| Dashboard do PBA | Abra o dashboard da marca |
| ID do agrupamento de marca | Copie o brand bundle ID para a área de transferência |
| Chave do desenvolvedor web | Copie a chave do desenvolvedor da web para a área de transferência |
| Selecione um agrupamento existente para atualizar as configurações e opções do bundle de marca | Opções disponíveis:<ul><li>Marcar eventos como eventos de conversão:<ul><li>[Configurações de evento da web](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[Configurações de eventos in-app](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Exclusão de domínio](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/pt/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Integração do Google Ads</Anchor></li></ul> |
| Ícone Excluir | [Exclua o bundle de marca selecionado](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (após confirmar que gostaria de fazer isso) |

<div id="add-brand-bundle" />

<Accordion title="Adicionar bundle de marca">

Antes de continuar, verifique se todos os aplicativos que você deseja incluir no bundle foram adicionados à sua conta. Depois que um bundle de marca é criado, os aplicativos que ele inclui não podem ser alterados sem [excluir o bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) e recriá-lo.

**Para adicionar um bundle de marca:**

1. Na página [Bundles de marca](/docs/pba-brand-bundles-and-settings#acessando-bundles-de-marca), clique em **Adicionar bundle de marca.**
2. Insira o **nome do bundle da marca** (qualquer nome que você queira usar para identificar o bundle).
3. Selecione os aplicativos a serem incluídos no bundle.

   **Atenção:** os aplicativos incluídos em outros bundles não estão disponíveis para seleção.

   * App na web *[obrigatório]*: Selecione 1 aplicativo web disponível.
   * Aplicativos mobile *[opcional]:* Selecione os aplicativos mobile disponíveis que você deseja incluir no bundle.
     * Os aplicativos mobile não são necessários para criar um bundle.
     * Não há limite para o número de aplicativos mobile que você pode incluir em um bundle.
4. Clique em Criar bundle.

<div id="important" />

> 🚧 **Importante!**
>
> Os bundles de marcas não podem ser criados nas seguintes circunstâncias:
>
> * O aplicativo web selecionado para inclusão no bundle não aponta para uma URL válida.
> * O aplicativo web e um aplicativo mobile Android selecionados para inclusão no bundle têm o mesmo App ID.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Configurações de evento da web">

Existem dois tipos de eventos na web: **padrão** e **conversão**. Para focar e priorizar seus esforços de otimização, defina alguns eventos como eventos de conversão.

* O PBA atribui eventos de conversão e eventos padrão da mesma maneira.
* Os relatórios de <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">dados brutos</Anchor> incluem eventos padrão e de conversão.
* Os dashboards de PBA incluem apenas eventos de conversão.
* Um tipo de evento pode ser alterado a qualquer momento; no entanto, a alteração não é retroativa.

**Para definir eventos de conversão:**

1. Na página [Bundles de marca](/docs/pba-brand-bundles-and-settings#acessando-bundles-de-marca), selecione o bundle da marca.  
   A página **Atualizar bundles de marca** é aberta.
2. Vá para a aba **Configurações de eventos web**.
3. Ative **Marcar como evento de conversão** conforme necessário.
4. Clique em **Atualizar bundle.**

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="Configurações de eventos in-app">

[Padrão] Eventos in-app com receita são marcados como eventos de conversão. **Atenção!** Se você alterar os eventos padrão, marque explicitamente os eventos in-app de receita.

**Para marcar eventos in-app como eventos de conversão:**

1. Na página [Bundles de marca](/docs/pba-brand-bundles-and-settings#acessando-bundles-de-marca), selecione o bundle da marca.  
   A página **Atualizar bundles de marca** é aberta.
2. Vá para a aba **Configurações de eventos in-app**.
3. Ative **Marcar como evento de conversão** conforme necessário.
4. Clique em **Atualizar bundle.**

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Exclusão de domínio">

Um mecanismo de exclusão de domínio, parte das <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules">regras de PBA de fonte de mídia,</Anchor> é implementado para evitar:

* Autoatribuição: em outras palavras, a AppsFlyer não atribuirá eventos ao site definido no próprio aplicativo web e aos domínios que você especificar que estão associados a esse site.
* Atribuição ou gravação de eventos associados a domínios que não fazem parte da sua marca, mas participam do fluxo do usuário (por exemplo, gateways de pagamento).

| Tipo de domínio | Descrição | Impacto da exclusão |
| --- | --- | --- |
| Primário | O domínio do **aplicativo web** incluído no bundle da marca. Isso inclui subdomínios.<br /><br />Por exemplo, se o seu domínio for mydomain.co.za, subdomínios como um.mydomain.co.za, b.mydomain.co.za serão excluídos automaticamente. <br /><br />O domínio de um aplicativo web não pode ser alterado sem [excluir](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) e recriar o aplicativo web. (Isso também significa excluir o bundle no qual o aplicativo web está incluído). | Sem autoatribuição |
| Interno | Liste outros domínios que fazem parte da sua marca, por exemplo, meudominio.com, meudominio.in, meudominio.co.ng, abc.com | Sem autoatribuição |
| Externo (listado por você) | Domínios diretamente usados pelo seu site, mas que não fazem parte da marca. Isso inclui gateways de pagamento, sites de processamento de pagamentos etc. | <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules#visit-recognition-rules">Visitas são desconsideradas</Anchor> |
| Externo (listado pela AppsFlyer) | Domínios listados pela AppsFlyer e sempre excluídos.<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>A lista de domínios automáticos não pode ser editada. | <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules#visit-recognition-rules">Visitas são desconsideradas</Anchor> |

**Para excluir domínios internos ou externos:**

1. Na página [Bundles de marca](/docs/pba-brand-bundles-and-settings#acessando-bundles-de-marca), selecione o bundle da marca.  
   A página **Atualizar bundles de marca** é aberta.
2. Vá para a aba **Exclusão de domínios**.
3. Clique em **Adicionar domínio.**
4. Insira um nome de domínio.
5. Selecione um tipo de domínio: **Interno** ou **Externo.**
6. Clique em **Adicionar domínio.**  
   Demora uma hora para que a exclusão entre em vigor.

</Accordion>

<div id="faq" />

## Perguntas frequentes

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="Posso incluir o mesmo aplicativo em mais de um bundle?">

**Não.** Depois que um aplicativo é adicionado a um bundle, ele não pode ser adicionado a outro bundle.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="Posso adicionar ou remover aplicativos depois de criar um bundle?">

**Não.** Depois que um bundle é criado, os aplicativos incluídos nele não podem ser alterados.

**Por que?** Cada aplicativo tem seus próprios dados, e a AppsFlyer usa esses dados para analisar a jornada do usuário entre plataformas (web e aplicativo). Se um aplicativo foi alterado, isso envolveria um conjunto diferente de dados que não é compatível com os dados anteriores.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="Como adiciono ou removo (excluo) aplicativos de um bundle?">

Para alterar o bundle no qual um aplicativo está incluído, exclua o bundle original e crie um novo que inclua o aplicativo.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="O que acontece se eu excluir um bundle?">

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### FAQ - o que acontece se eu excluir um bundle

Se você excluir um bundle:

* A AppsFlyer para de atribuir o bundle.
* Os dados do bundle são retidos (ou seja, não são excluídos permanentemente), mas o bundle em si não pode ser restaurado para visualizar os dados.

  **Por que?** Um novo agrupamento usa uma chave do desenvolvedor web diferente, por isso, mesmo que ele inclua os mesmos aplicativos, o agrupamento original não é restaurado.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="Por que não consigo adicionar certos aplicativos em um bundle?">

* **Administradores:** se você não conseguir selecionar um aplicativo ao criar um bundle, verifique se o aplicativo foi adicionado à sua conta da AppsFlyer e não está incluído em outro bundle.
* **Outros usuários da conta:** fale com um administrador da conta para garantir que você tenha a função e as permissões necessárias para acessar os aplicativos que está tentando adicionar.

</Accordion>

<div id="page-404" />

<Accordion title="Por que recebo o erro 'não conseguimos encontrar essa página' quando tento visualizar ou criar um bundle de marca?">

Você provavelmente não se inscreveu no PBA. Por favor, entre em contato com seu CSM ou envie uma mensagem para [hello@appsflyer.com](mailto:hello@appsflyer.com) para atualizar seu pacote.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/onboarding-guide-to-people-based-attribution">Guia de onboarding para PBA</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">Introdução ao PBA</Anchor>

<div data-zendesk-anchors="about-brand-bundles=sobre-bundles-de-marca h_01HE0Y2A3A5W86YY44RWCTKM1Y=sobre-bundles-de-marca h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=o-que-%C3%A9-um-aplicativo-na-web accessing-brand-bundles=acessando-bundles-de-marca h_01HE0Y2A3A7265NYM7GVBZVXEN=acessando-bundles-de-marca managing-brand-bundles=gerenciamento-de-bundles-de-marca h_01HE0Y2A3A272QJ4ZQH7VXJWCC=gerenciamento-de-bundles-de-marca h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=importante h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=perguntas-frequentes h_01HE0Y2A3AB24NCNPAYFC0J4YH=perguntas-frequentes h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=faq---o-que-acontece-se-eu-excluir-um-bundle h_01HE0Y2A3B276FV92EYBCZRA6C=faq---o-que-acontece-se-eu-excluir-um-bundle h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01JTQF9DZZZ5JFN43Y5KJJV943=page-404 h_01HE0Y2KTXS06WHN57MQ91AD09=veja-tamb%C3%A9m" />
