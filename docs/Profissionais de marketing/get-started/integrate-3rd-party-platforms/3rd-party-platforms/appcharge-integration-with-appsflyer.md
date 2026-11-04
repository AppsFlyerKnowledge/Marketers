---
title: Integração do Appcharge com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-06-17T13:21:47Z'
  edited_at: '2026-08-19T00:10:41Z'
  id: 36292113943825
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/36292113943825
---
> **Em resumo:** o Appcharge, parceiro integrado da AppsFlyer, é um provedor de tecnologia de comércio para gaming especializado no processamento de pagamentos fora dos ecossistemas tradicionais de lojas de aplicativos. Por meio da integração com a AppsFlyer, o Appcharge pode enviar automaticamente para a AppsFlyer dados de compras e reembolsos da loja web, permitindo uma visão mais completa do retorno sobre gasto com anúncios (ROAS) e do valor vitalício (LTV).

<div id="about-appcharge" />

## Sobre o Appcharge

<Anchor target="_blank" href="https://appcharge.com/">Appcharge</Anchor>, parceiro integrado da AppsFlyer, é uma plataforma direct-to-consumer (D2C) criada para publishers de gaming mobile. A integração ajuda publishers a monitorar compras da loja web, um canal de receita essencial fora das lojas de aplicativos tradicionais. Ao enviar dados de compras e reembolsos diretamente para a AppsFlyer, o Appcharge permite cálculos precisos de retorno sobre gasto com anúncios (ROAS) com base na receita líquida, gerando melhores insights sobre a performance da campanha e o valor vitalício (LTV) do jogador.

A integração do Appcharge ajuda você a:

* Atribuir e mensurar a performance de e-commerce
* Garantir que o LTV esteja sendo reportado a partir das compras da loja web
* Atribuir compras da loja web a campanhas de marketing
* Manter a consistência com os dados da sua campanha mobile

Este guia orienta você na configuração da integração do Appcharge.

<div id="set-up-the-integration" />

## Configurando o Amplitude

**Pré-requisitos:**

* Você tem uma conta ativa do Appcharge. Caso contrário, entre em contato com o parceiro (Appcharge) e abra uma conta com ele antes de configurar a integração.
* Sua conta da AppsFlyer inclui as permissões necessárias para configurar integrações de parceiros.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. **Observação:** Essa opção deve permanecer habilitada <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativada)</Anchor> enquanto você trabalhar com o parceiro.
5. Complete a configuração usando a aba **Integração**, conforme descrito abaixo.

**Para ativar ou editar a integração:**

**Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.

<div id="integration-tab" />

<Accordion title="Aba de integração">

<div id="activate-partner" />

#### Ativar parceiro

Na sua primeira visita, você precisará habilitar a opção **Ativar parceiro** para configurar a integração. O toggle deve permanecer ativado enquanto você trabalhar com o Appcharge. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

<div id="advanced-privacy" />

#### Privacidade avançada

Para aplicativos iOS, o toggle <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada</Anchor> é exibido. Quando ativada, ela limita o compartilhamento de identificadores de usuário com o parceiro. Observe que, quando o <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">toggle de Privacidade Avançada Agregada</Anchor> é ativado nas Configurações do aplicativo, **Privacidade Avançada (para iOS 14+ e versões posteriores)** é ativada e bloqueada por padrão.

<div id="default-postbacks" />

#### Postbacks padrão

A AppsFlyer envia postbacks padrão para o Appcharge após as instalações de usuários. Use esta seção para <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">configurar esses postbacks</Anchor>.

* **Desativado:** Postbacks de instalação não são enviados à Appcharge.  
   **Observação:** A integração da Appcharge com a AppsFlyer não requer o envio de postbacks de instalação. Portanto, é recomendável defini-la como Desativado.
* **Todos os canais de mídia, incluindo orgânicos:** Postbacks de instalação são enviados para eventos atribuídos a qualquer parceiro e para eventos orgânicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com seus parceiros por meio de postbacks.

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. Ative **Postbacks de eventos in-app**.
2. Clique em **Adicionar evento** para adicionar um evento de SDK ou evento servidor para servidor à lista.
3. Complete os seguintes parâmetros:
4. Clique em **Salvar Integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Os links de atribuição não estão disponíveis na Appcharge.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Os dados de custo não têm suporte na integração com a Appcharge.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

Os dados de receita de anúncios não têm suporte na integração com a Appcharge.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

As permissões não estão disponíveis na Appcharge.

</Accordion>

<div id="identify-appcharge-events-in-appsflyer" />

## Identifique eventos da Appcharge no AppsFlyer

A Appcharge envia ao AppsFlyer dois tipos de eventos in-app mobile:

* `ac_af_purchase` - Quando um usuário conclui uma compra com sucesso
* `ac_af_refund` - Quando um reembolso é concluído

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

Suporte para PC / Console - a integração do AppsFlyer com a Appcharge não tem suporte para aplicativos de PC / Console.

</Accordion>

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de Parceiros</Anchor>.

<div data-zendesk-anchors="integration-types=sobre-o-appcharge h_01J3DB8MCNQKKKCV1M39KN7Q0H=sobre-o-appcharge setting-up-appcharge=configurando-o-amplitude h_01HST42K52JKQ70F7Y5PHDZAZ5=configurando-o-amplitude h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=ativar-parceiro h_01HST42K52RCTSGRNRCJ1C70NP=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01HST42K52BBJ6JS5KM0WCN6CF=privacidade-avan%C3%A7ada default-postbacks=postbacks-padr%C3%A3o h_01HST47F5BXWV5W8BNHS9M2MTN=postbacks-padr%C3%A3o inapp-event-postbacks=postbacks-de-eventos-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postbacks-de-eventos-in-app h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab identifying-appcharge-events-in-appsflyer=identifique-eventos-da-appcharge-no-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=identifique-eventos-da-appcharge-no-appsflyer h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations" />
