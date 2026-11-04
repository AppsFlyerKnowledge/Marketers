---
title: Editar mensurações de receita líquida usando a Tax API
metadata:
  keywords:
    - Revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-08-19T00:02:18Z'
  id: 30468586765841
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** Configure como a AppsFlyer calcula a receita líquida de compras in-app e assinaturas usando a API de Receita Líquida para personalizar as taxas de comissão da loja e as regras fiscais por aplicativo. Isso garante que seus relatórios reflitam com precisão os ganhos reais, incluindo casos com taxas de comissão fora do padrão ou regras fiscais específicas.

O produto de receita da loja ROI360 calcula a receita líquida de compras in-app e assinaturas ao deduzir automaticamente da receita bruta a comissão da loja e os impostos. A configuração padrão reflete as taxas de comissão e regras fiscais padrão aplicadas pela App Store e pelo Google Play. Se a comissão da sua loja for diferente ou se você operar em um país com tratamento fiscal especial, use a API de Receita Líquida para substituir a configuração padrão.

A API de Receita Líquida é implementada por meio de duas APIs REST que permitem configurar taxas de comissão da loja e regras fiscais para aplicativos individuais.

* [Taxas de comissão da loja](https://dev.appsflyer.com/hc/reference/post_store-commission-rates): crie, atualize, obtenha ou exclua taxas de comissão da loja para um ou mais aplicativos. Cada aplicativo pode ter uma taxa de comissão específica com base em vários programas da loja.
* [Regras de alíquota de imposto](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id): crie ou obtenha regras de alíquota de imposto personalizadas para um aplicativo específico.

Para mais informações sobre como a receita líquida é calculada, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#true-revenue">Receita líquida</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> A receita líquida é exibida nos Relatórios de dados brutos e em My Dashboards como métricas líquidas (Receita líquida, ROI líquido, ROAS líquido, ARPU líquido, Lucro líquido).

<div id="ios" />

<div id="update-tax-rate-rules" />

## Atualizar regras de alíquota de imposto

O imposto é informado por padrão para qualquer transação medida pelo ROI360 usando a configuração de taxa de imposto padrão. Em *países com impostos incluídos*, em que o imposto está incluído no preço de tabela, a receita líquida é calculada após a dedução do imposto. Por exemplo, no Reino Unido, a AppsFlyer desconta o valor total de imposto e comissão da loja. Em *países com impostos excluídos*, como os EUA, em que o preço de tabela não inclui imposto, os parâmetros de receita e receita líquida não incluem imposto por padrão.

Para definir as regras de alíquota de imposto usando a API de Receita Líquida, siga estas etapas:

1. Conclua as etapas a seguir nas configurações de receita da loja do ROI360:

   <Accordion title="/docs/ctv-pc-and-console-platform-attribution-concepts">

   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-1-ios-configurar-as-chaves-do-app-store-connect">1. Configure as chaves do App Store Connect</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-2-ios-configurar-notificações-do-servidor-da-app-store">3. Configure as notificações do servidor da App Store</Anchor>

   </Accordion>

   <div id="android" />

   <Accordion title="com o Android">

   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-1-android-configure-a-chave-da-conta-de-serviço-e-as-permissões">1. Configure a service account key e permissões</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-2-android-configurar-notificações-do-servidor-do-google-play">3. Configure notificações do servidor do Google Play</Anchor>

   </Accordion>

2. Forneça ao seu programador:
   * O <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token da API V2</Anchor> a ser usado como a chave de autorização.
   * Os parâmetros e valores que contêm informações sobre quais impostos devem ser calculados, conforme descrito na tabela a seguir.
3. Peça ao seu programador para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-tax-rate-rule">instruções da tax API</Anchor> para criar regras de taxa de imposto. **Atenção:** a API permite um arquivo JSON no corpo da solicitação. <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">Esse arquivo JSON</Anchor> exibe todos os países disponíveis e suas taxas de imposto padrão. O programador pode editá-lo ou usá-lo sem alterações na API.

<div id="tax-rate-api-parameters" />

### Edite as taxas de impostos usando a Tax API

| Parâmetro | Obrigatório | Observações |
| --- | --- | --- |
| `tax_name` | Sim | <ul><li>Nome que aparece na fatura do cliente, descrevendo o tipo específico de imposto.</li><li>Exemplo: Vendas, IVA, GST</li></ul> |
| `tax_rate` | Sim | <ul><li>O valor deve ser maior que 0. Número com até 4 casas decimais representando o percentual do imposto a ser cobrado.</li><li>Exemplo: 7,25</li></ul> |
| `tax_exclusive` | Não | <ul><li>Parâmetro booleano, true ou false.</li><li>False significa que o imposto está incluído na receita total.</li><li>True significa que o imposto é adicionado à receita total declarada. Por exemplo, nos EUA e no Canadá, o preço de tabela não inclui o imposto sobre vendas.</li><li>O padrão é false.</li></ul> |
| `país` | Não | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Código ISO de duas letras para o país</Anchor> ao qual o imposto é aplicado.</li><li>Exemplo: CA</li><li>Atenção: o código implementado para o Reino Unido é UK, não GB.</li></ul> |
| `subdivision` | Não | <ul><li>Para alguns países, pode haver uma subdivisão ou estado adicional.</li><li>Manuseado de acordo com <Anchor target="_blank" href="https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm">os códigos de subdivisão ISO 3166-2.</Anchor></li><li>Deve incluir o código do país e o código da subdivisão.</li><li>Exemplo: US-CA</li></ul> |
| `postal_code` | Não | <ul><li>String de letras e/ou números</li><li>Exemplo: L4J8E3</li></ul> |
| `deduction_order` | Não | <ul><li>Enum, que pode ser **0**, **1** ou **2**:<ul><li>0 significa que a comissão da loja é deduzida primeiro da receita bruta e o imposto é deduzido do valor restante.</li><li>1 significa que a taxa é deduzida primeiro da receita bruta, enquanto a comissão da loja é deduzida do valor restante.</li><li>2 significa que tanto o imposto quanto a comissão da loja são deduzidos da receita total.</li></ul></li></ul> |

<div id="set-up-store-commission-rates" />

## Definir taxas de comissão da loja

Por padrão, a AppsFlyer aplica a lógica padrão de comissão da loja ao calcular a receita líquida. Os padrões da App Store são específicos por região (consulte <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#true-revenue">Sobre a receita da loja ROI360</Anchor> para ver as taxas atuais por vitrine). Se o seu aplicativo operar com taxas reduzidas ou não padrão da loja, use a API de Receita Líquida para substituir a taxa de comissão da loja no nível do aplicativo.

Alguns exemplos:

* Seu aplicativo se qualifica para taxas reduzidas da loja, como:
  * Programa Apple App Store para pequenas empresas (comissão de 15%; 12% na China continental (CN))
  * Faixa de taxa de serviço de 15% do Google Play (primeiro US$ 1 milhão em ganhos anuais)
* A comissão da sua loja muda ao longo do tempo e, como a AppsFlyer não tem visibilidade sobre o status da comissão da sua loja, você precisa atualizar manualmente a taxa aplicada usando a API de Receita Líquida, por exemplo:
  * Aplicar uma comissão reduzida quando seu aplicativo se tornar elegível para uma taxa mais baixa da loja
  * Reverter para a lógica de comissão padrão da loja quando a taxa reduzida não se aplicar mais

<div id="ios::f410adfc" />

<div id="update-store-commission-with-the-net-revenue-api" />

### Atualize a comissão da loja com a API de Receita Líquida

Você pode usar a API de Receita Líquida para gerenciar as configurações de comissão da loja das seguintes maneiras:

* Revise as configurações existentes enviando uma solicitação GET para recuperar as taxas de comissão da loja dos aplicativos na conta
* Aplique uma comissão personalizada enviando uma solicitação POST com a taxa de comissão obrigatória
* Reverta para a lógica padrão enviando uma solicitação DELETE para o aplicativo relevante

Antes de usar a API:

1. Conclua as etapas a seguir nas configurações de receita da loja do ROI360:

   <Accordion title="/docs/ctv-pc-and-console-platform-attribution-concepts">

   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-1-ios-configurar-as-chaves-do-app-store-connect">1. Configure as chaves do App Store Connect</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-2-ios-configurar-notificações-do-servidor-da-app-store">3. Configure as notificações do servidor da App Store</Anchor>

   </Accordion>

   <div id="android::659c7976" />

   <Accordion title="com o Android">

   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-1-android-configure-a-chave-da-conta-de-serviço-e-as-permissões">1. Configure a service account key e permissões</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#etapa-2-android-configurar-notificações-do-servidor-do-google-play">3. Configure as notificações do servidor do Google Play</Anchor>

   </Accordion>

2. Prepare as seguintes informações:
   * Token da API V2 a ser usado como chave de autorização
   * Taxa de comissão da loja a ser aplicada (valores compatíveis: 1%–30%)
   * ID(s) do aplicativo a que a comissão personalizada se aplica
3. Observe os seguintes detalhes de configuração:
   * A comissão da loja é configurada **por aplicativo**
   * Os valores compatíveis são **1%–30%**
   * A configuração se aplica **somente a novos eventos recebidos**
   * Se nenhuma comissão personalizada for definida, a AppsFlyer usa a **lógica de comissão padrão da loja**

Para conhecer as estruturas completas de solicitações e exemplos, consulte a [documentação da API de receita líquida do Net Revenue](https://dev.appsflyer.com/hc/reference/overview-7).

<div data-zendesk-anchors="h_01KEFDF4KD0DCMP5DGE7ZJDBGX=nota update-tax-rate-rules=atualizar-regras-de-al%C3%ADquota-de-imposto h_01KEFDF4KDJ5PVS3AW46BS57NC=atualizar-regras-de-al%C3%ADquota-de-imposto ios=atualizar-regras-de-al%C3%ADquota-de-imposto h_01KEFDRXY0FWKKK0DK6PS340TC=atualizar-regras-de-al%C3%ADquota-de-imposto h_01KEFDRXY0RTBH293JQXFWYAM2=android tax-rate-api-parameters=edite-as-taxas-de-impostos-usando-a-tax-api h_01KEFDF4KD60SEVBQ8G228PEXD=edite-as-taxas-de-impostos-usando-a-tax-api set-up-store-commission-rates=definir-taxas-de-comiss%C3%A3o-da-loja h_01KEFDF4KDP4PFKFQ0D9FN8P5D=definir-taxas-de-comiss%C3%A3o-da-loja update-store-commission-with-the-net-revenue-api=atualize-a-comiss%C3%A3o-da-loja-com-a-api-de-receita-l%C3%ADquida h_01KEFDF4KDVTHTGKJ35CQ1GQ1E=atualize-a-comiss%C3%A3o-da-loja-com-a-api-de-receita-l%C3%ADquida ios::f410adfc=atualize-a-comiss%C3%A3o-da-loja-com-a-api-de-receita-l%C3%ADquida h_01KEFDWVDFBPP7NPSZV0PRGKPZ=atualize-a-comiss%C3%A3o-da-loja-com-a-api-de-receita-l%C3%ADquida h_01KEFDWVDFZPHJP6EG0CPNG5A0=android::659c7976" />
