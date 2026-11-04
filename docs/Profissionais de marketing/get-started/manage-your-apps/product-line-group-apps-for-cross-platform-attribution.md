---
title: 'Linha de produto: agrupe aplicativos para atribuição multiplataforma'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-09-30T07:06:57Z'
  edited_at: '2026-09-10T00:16:47Z'
  id: 39524780935185
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/39524780935185
---
> **Visão geral:** Agrupe aplicativos específicos de cada plataforma em uma única marca usando a Linha de Produto. Desbloqueie a atribuição multiplataforma e os insights da jornada do usuário em aplicativos mobile, web e CTV usando um Customer User ID (CUID) unificado.

<div id="about-product-line" />

## Sobre a Linha de Produto

A Linha de Produto permite organizar diferentes versões de plataforma do mesmo aplicativo (como Android, iOS, web e CTV) sob uma única marca. Isso simplifica o gerenciamento de aplicativos e permite uma atribuição multiplataforma contínua, com base em um identificador de usuário do cliente (CUID).

Com as Linhas de Produto, você pode:

* Mensurar o LTV do usuário em todos os dispositivos (LTV)
* Analisar o comportamento em todas as plataformas
* Agrupar internamente aplicativos sob a mesma marca
* Ative a mensuração de reengajamento multiplataforma

  Observação: a mensuração de reengajamento multiplataforma é opcional. Ao ativá-la, a AppsFlyer pode atribuir a atividade elegível de usuários recorrentes ao canal de mídia que reengajou o usuário em todas as plataformas. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-re-engagement-attribution">Mensuração de reengajamento multiplataforma</Anchor>.

Por exemplo, se um usuário instala seu aplicativo no iOS, faz login no aplicativo do PlayStation e transmite conteúdo pela Samsung TV, você pode ver toda a jornada dele como um único usuário.

Para ter uma visão mais completa das Linhas de Produto, consulte <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-attribution">Atribuição multiplataforma baseada em usuário</Anchor>.

<div id="how-to-set-up-a-product-line" />

## Como configurar uma Linha de Produto

<div id="prerequisites" />

### Pré-requisitos

* O **CUID (Customer User Identifier)** deve ser um identificador consistente (como um ID de login ou e-mail com hash) em todas as plataformas.
* Implemente a **configuração do SDK de CUID ou** [**s2s**](https://dev.appsflyer.com/hc/docs/set-customer-user-id).
* Garanta que o aplicativo defina o CUID em cada inicialização para reconhecer o mesmo usuário em diferentes dispositivos e sessões.

<div id="how-to-create-a-product-line" />

### Como criar uma Linha de Produto

1. Acesse **My Apps**.
2. Na barra superior, clique em **Criar linha de produto**.
3. Selecione até 30 aplicativos para incluir -> **Criar**.
4. Na nova janela:
   1. Adicione um **nome da Linha de Produto.**
   2. Ative **Começar a mensurar e analisar entre plataformas.**  
      Observação: sem essa opção ativada, a atribuição entre plataformas não funcionará.
   3. Selecione a **janela de inatividade.**
   4. Selecione se você deseja ativar a mensuração de reengajamento entre plataformas.
      1. Selecione a **janela de reengajamento**.
      2. Selecione a **janela de inatividade para reengajamento.**
5. No lado direito, você verá todos os aplicativos na Linha de Produto.
6. Clique em **criar**.
7. Envie as **instruções de implementação do CUID** ao seu desenvolvedor.

**Observação:** A atribuição de reengajamento entre plataformas funciona com base na atribuição entre plataformas. Antes de ativar o reengajamento, você deve criar uma Linha de Produto, ativar a atribuição entre plataformas e enviar eventos com um CUID válido. Para saber como a atribuição de reengajamento funciona entre plataformas, consulte <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-re-engagement-attribution">Atribuição de reengajamento entre plataformas</Anchor>.

<div id="how-to-remove-an-app-from-a-product-line" />

<Accordion title="Como remover um aplicativo de uma Linha de Produto">

<div id="important" />

> 🚧 **Importante!**
>
> Não é recomendável remover um aplicativo de uma Linha de Produto. Quando um aplicativo é removido ou movido, as configurações de atribuição entre plataformas dele são redefinidas, e eventos futuros não estarão qualificados para atribuição entre plataformas até que um novo mapeamento seja criado.

1. Acesse **My Apps**.
2. Na seção **Product Lines**, clique na Linha de Produto que você deseja editar.
3. No lado direito da janela, você verá todos os aplicativos na Linha de Produto.
4. Passe o cursor sobre o aplicativo que você deseja remover e clique no **X** desse aplicativo.
5. Depois de remover o aplicativo, clique em **Update** na parte inferior da janela.

</Accordion>

<div id="how-to-add-an-app-to-a-product-line" />

<Accordion title="Como adicionar um aplicativo a uma Linha de Produto">

1. Acesse **My Apps**
2. Na seção **All Apps**, passe o cursor sobre o aplicativo que você deseja adicionar e selecione a caixa de seleção.
3. No banner superior, selecione **Add to Product Line**.
4. Selecione a Linha de Produto à qual você deseja adicionar o aplicativo.
5. Confirme se tudo está correto na janela da Linha de Produto e clique em **Update** na parte inferior da janela.

</Accordion>

<div id="how-to-delete-a-product-line" />

<Accordion title="Como excluir uma linha de Produto">

<div id="important-1" />

> 🚧 **Importante!**
>
> Não é recomendável excluir uma linha de Produto. Quando uma linha de Produto é removida, as configurações de atribuição entre plataformas são redefinidas e eventos futuros não serão elegíveis para atribuição entre plataformas até que um novo mapeamento seja criado.

1. Acesse **My Apps**.
2. Na seção **Product Lines**, clique nos três pontos na linha de Produto que você quer remover.
3. Selecione **Excluir linha de Produto**.

</Accordion>

<div id="traits-and-limitations" />

## Especificações e limitações

| Caraterística | Descrição |
| --- | --- |
| Agrupamento de aplicativos | Os aplicativos devem pertencer à mesma marca |
| Máximo de aplicativos | Até 30 aplicativos por linha de Produto |
| Apenas uma linha de Produto | Um aplicativo pode pertencer a apenas uma linha de Produto por vez |
| Requisito de CUID | Obrigatório apenas para atribuição entre plataformas |
| Janela de restauração de inatividade | 14–390 dias (padrão: 90 dias) |
| Impacto da remoção de aplicativo | Remover um aplicativo redefine as configurações de atribuição<br /><br />Remover um aplicativo de uma linha de Produto afeta a atribuição entre plataformas a partir desse momento.<br /><br />• Eventos in-app futuros do aplicativo removido não são elegíveis para atribuição entre plataformas nessa linha de Produto, porque os eventos devem vir de aplicativos que pertencem à linha de Produto.<br /><br />• Os resultados históricos não são reprocessados retroativamente |

<div id="faqs" />

## Perguntas frequentes

**Posso usar linhas de Produto apenas para organizar aplicativos?**  
Sim. Deixe a alternância entre plataformas **desativada** para agrupar aplicativos apenas para gerenciamento.

**O que acontece se eu remover um aplicativo de uma linha de Produto?**  
Não é recomendável remover um aplicativo de uma linha de Produto. Quando um aplicativo é removido ou movido, as configurações de atribuição entre plataformas são redefinidas, e eventos futuros não serão qualificados para atribuição entre plataformas até que um novo mapeamento seja criado.

**A criação de uma Linha de Produto tem algum impacto nos resultados clássicos de Atribuição do AppsFlyer?**

Não, criar uma Linha de Produto não tem impacto nos resultados clássicos de Atribuição do AppsFlyer no nível do dispositivo

<div data-zendesk-anchors="about-product-line=sobre-a-linha-de-produto h_01K6CQ3YXD9QGGMM08WJWNKX65=sobre-a-linha-de-produto how-to-set-up-a-product-line=como-configurar-uma-linha-de-produto h_01K6CQ3YXHBXVHE2V0WATR74T5=como-configurar-uma-linha-de-produto prerequisites=pr%C3%A9-requisitos h_01K6CQ3YXHXXYXKKQ3Q7B6N9JQ=pr%C3%A9-requisitos how-to-create-a-product-line=como-criar-uma-linha-de-produto h_01K6CQ3YXKBMS7NZSH0GSJMTBM=como-criar-uma-linha-de-produto h_01K6CQ8MJFXS6WNWE0GPV18NPT=how-to-remove-an-app-from-a-product-line h_01K6CQPY31VW8BS7DR2TSKRPZZ=importante h_01K6CQ8MJFRD9R9SNZ84D6QQB4=how-to-add-an-app-to-a-product-line h_01K6CQ8MJF61375RE001YMMS4E=how-to-delete-a-product-line h_01K6CQPY31DB9DKQJEBX1PXDPT=importante-1 traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01K6CQ3YXZM5F0DVGTAQNHHN9B=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es faqs=perguntas-frequentes h_01K6CQD81T4VNMMNVH0X9SZ1TT=perguntas-frequentes" />
