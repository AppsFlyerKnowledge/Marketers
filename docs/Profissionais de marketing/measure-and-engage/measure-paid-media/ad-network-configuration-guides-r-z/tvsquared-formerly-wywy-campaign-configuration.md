---
title: Configuração da campanha do TVSquared (antigo WyWy)
metadata:
  keywords:
    - Advertisers
    - TV Squareed
    - Wywy
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-06T08:58:47Z'
  edited_at: '2026-08-19T00:26:18Z'
  id: 213836263
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/213836263
---
> **Em resumo:** TVSquared (antigo WyWy), um parceiro integrado de ad network da AppsFlyer, permite que toda a organização digital — profissionais de marketing, gerentes de produto e cientistas de dados — administre o negócio com base em dados. O TVSquared cria uma visão integrada dos consumidores em vários dispositivos, fornecendo ferramentas para otimizar a experiência do usuário em tempo real.

<div id="setting-up-tvsquared" />

## Como configurar o TVSquared

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

**Observação:** Para o TVSquared, você precisa preencher a aba Integração. As abas restantes não se aplicam ao TVSquared.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A guia Integração é dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

1. Ative ***Activate Partner***.  
   Os parâmetros de integração são exibidos.  

   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
2. Preencha os campos de Configurações gerais:
   * ***SITEID***: preencha o SITEID que você obteve do TVSquared.
   * ***COLLECTORID***: preencha o COLLECTORID obtido do TVSquared.
3. **Postbacks padrão**: a AppsFlyer envia postbacks para o TVSquared após a instalação/reengajamento do usuário. Selecione a opção de envio para a qual o parceiro receberá postbacks:
   * **Eventos atribuídos a qualquer parceiro ou orgânicos**: Todas as instalações, independentemente da fonte, são reportadas ao TVSquared
   * **Desligado**
4. Preencha os campos das configurações de eventos in-app:

* ***SITEID***: preencha o SITEID que você obteve do TVSquared.
* ***COLLECTORID***: preencha o COLLECTORID obtido do TVSquared.
* **customerid:** (opcional) Você pode deixar esse campo em branco.
* (opcional) Ative ***In-App Events Postback***: mapeie seus eventos in-app com o TVSquared usando postbacks. Configure os parâmetros da seguinte forma:
  * Clique em Add Event para adicionar um evento de SDK à lista e preencher os parâmetros.
* Clique em **Salvar integração.**

<div id="note" />

> 📘 **Nota**
>
> De acordo com os termos e condições dos anúncios do Meta e do X Ads, a AppsFlyer não pode compartilhar dados em nível de usuário com nenhum terceiro. Portanto, todas as instalações do Meta ads e do X Ads são enviadas ao TVSquared como orgânico.
>
> Para mais detalhes sobre o compartilhamento de dados com 3rd parties, clique <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">aqui</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para o TVSquared.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para o TVSquared.

</Accordion>

<div data-zendesk-anchors="setting-up-tvsquared=como-configurar-o-tvsquared h_01HF9R4JZ504QNYCQQ8TFDM6FV=como-configurar-o-tvsquared h_01HF9R4JZ5VXT1P5T3RVRXN522=integration-tab activate-partner=ativar-parceiro h_01HF9R4JZ55HMSRD3TNFF05PKZ=ativar-parceiro h_01HF9R4JZ5KWKPCN3ESQ9K27S7=nota h_01HF9R4JZ596NM643Z662BGY0M=attribution-link-tab h_01HF9R4JZ50XY445ABGAPDY962=cost-tab h_01HF9R4JZ5BA74FKFRKY4FPTAS=ad-revenue-tab h_01HF9R4JZ5BV6C6H6V6W53BXXK=permissions-tab" />
