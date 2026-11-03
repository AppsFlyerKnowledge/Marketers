---
title: Integração do Xsolla com a AppsFlyer
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
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-08-19T00:12:01Z'
  id: 23593013687185
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/23593013687185
---
> Resumo: Xsolla, um parceiro integrado da AppsFlyer, é um parceiro de tecnologia de gaming commerce especializado no processamento de pagamentos fora das plataformas tradicionais de aplicativos. A integração entre o Xsolla e a AppsFlyer permite que o Xsolla automatize as compras feitas na Web Shop e que a receita seja enviada para a AppsFlyer, mostrando o ROAS e LTV completos de um jogo, incluindo compras feitas na Web Shop do Xsolla.

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Tipos de integração

Existem dois métodos de integração disponíveis:

* [Integração com parceiros de tecnologia](#configurando-a-integração-do-parceiro-de-tecnologia): Essa integração permite que o Xsolla envie compras e receita da Web Shop como eventos mobile, melhorando o ROAS e LTV da campanha mobile, mostrando dados além das compras padrão da loja de aplicativos.
* [Integração de PBA Web SDK](#configurando-a-integração-do-pba-web-sdk): Essa integração permite que o Xsolla envie compras e receita da Web Shop como eventos da web, permitindo que a AppsFlyer mensure a performance das campanhas da web, enviando usuários do jogo diretamente para a Web Shop.

**Pré-requisitos:**

* Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.
* Para que a integração funcione corretamente, certifique-se de compartilhar Customer User ID (CUID) com a AppsFlyer, e que ele faça a correspondência do user ID compartilhado com o Xsolla. Isso permite que os usuários façam login na Web Shop do Xsolla e garante que os dados do usuário sejam enviados com precisão para a AppsFlyer.

## Configurando a integração do parceiro de tecnologia

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   **Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na sua primeira visita, você precisará habilitar a opção **Ativar parceiro** para configurar a integração. Essa opção deve permanecer ativada enquanto você trabalhar com o Xsolla. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração utiliza apenas a aba **Integração**.

<div id="integration-tab" />

<Accordion title="Aba de integração">

#### Ativar parceiro

A configuração é feita na página **Integrações Ativas** , mas para encontrar o parceiro você deve primeiro ir ao <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations">marketplace</Anchor>. Essa opção deve permanecer ativada enquanto você trabalhar com o Xsolla. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

#### Privacidade avançada

Para aplicativos iOS, o toggle <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada</Anchor> é exibido. Quando ativada, ela limita o compartilhamento de identificadores de usuário com o parceiro. Observe que, quando o botão <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor> está ativado nas configurações do aplicativo, <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada (para iOS 14.5+ e posterior)</Anchor> está ativada e bloqueada por padrão.

#### Postbacks padrão

A AppsFlyer envia postbacks padrão para o Xsolla após as instalações. Use esta seção para <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">configurar esses postbacks</Anchor>.

* **Desativado**: Postbacks de instalação não são enviados para o Xsolla.  
  **Atenção:** A integração do Xsolla com a AppsFlyer não requer o envio de postbacks de instalação. Portanto, recomendamos que você deixe a opção desativada.
* **Todas as fontes de mídia, incluindo orgânicas:** Postbacks de instalação são enviados para eventos atribuídos a qualquer parceiro e para eventos orgânicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### Postbacks de eventos in-app

Nessa seção você pode mapear os eventos da AppsFlyer com o parceiro por meio de postbacks.

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para incluir um evento do SDK ou de servidor para servidor na lista.
3. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br /><br />**Atenção:**<ul><li>Para o Xsolla, certifique-se de adicionar o evento af\_login ou qualquer outro evento que represente o login do usuário no aplicativo, conforme mostrado na captura de tela acima.</li></ul> |
| **mapeado para evento do parceiro** | Digite o nome do evento correspondente que você deseja enviar para o Xsolla. A nomenclatura do Xsolla é flexível e qualquer nome pode ser usado nesse campo. |
| **para usuários de** | Selecione **Todas as fontes de mídia, incluindo orgânicas** para enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos. |
| **incluindo** | <ul><li>**Sem valores e sem receita**: Envie apenas o evento em si, sem qualquer parâmetro (valores ou receita).</li><li>**Valores e sem receita**: Envie todos os parâmetros, com **exceção** do valor da receita.</li><li>**Valores e receita**: Envie todos os parâmetros de evento, **incluindo** o valor da receita (se existir no evento).</li></ul>Atenção: A integração do Xsolla com a AppsFlyer não requer o envio de valores ou receita. Portanto, qualquer opção selecionada é aplicável. |

4. Clique em **Salvar integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Links de atribuição não estão disponíveis para o Xsolla.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Os dados de custo não são compatíveis com a integração com o Xsolla.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

Os dados de receita de anúncios não são compatíveis com a integração com o Xsolla.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

As permissões não estão disponíveis para o Xsolla.

</Accordion>

## Configurando a integração do PBA Web SDK

Essa integração permite o acesso a dados e insights de LTV (Lifetime value) para analisar a performance do aplicativo dentro do dashboard do PBA.

**Para configurar a integração:**

1. **Na AppsFlyer:** <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Adicione o aplicativo Xsolla.</Anchor> Selecione <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web-pba">Web (PBA)</Anchor> como plataforma e insira as seguintes informações:
   * Use seu domínio da Web Shop como URL do aplicativo web. Por exemplo, se seu domínio da Web Shop for [www.webshop.com](http://www.webshop.com,), use ele como sua URL do aplicativo web.
   * Use qualquer valor como o nome do aplicativo.
2. **Na AppsFlyer:** <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#add-brand-bundle">Adicione o bundle Xsolla</Anchor> com as seguintes informações:
   1. Insira qualquer nome de bundle como o nome do bundle.
   2. Selecione o aplicativo web que você criou na etapa anterior como o aplicativo web do bundle.
3. **No Xsolla:** Conecte a AppsFlyer à sua Conta de Publisher do Xsolla:
   1. Abra seu projeto em sua <Anchor target="_blank" href="https://publisher.xsolla.com/">Conta de Publisher</Anchor>.
   2. Selecione seu site e clique em **configurar**.
   3. Na aba de **configurações do site**, vá para a seção de **aplicativos**.
   4. Em **AppsFlyer**, clique em **conectar**.  
      [![xsolla-connect.jpg](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)
   5. No campo **AppsFlyer Dev Key**, insira a dev key da AppsFlyer. Veja abaixo como [encontrar a dev key na AppsFlyer.](/docs/xsolla-integration-with-appsflyer#como-encontrar-a-web-dev-key-na-appsflyer)
   6. Clique em **conectar**.

#### Como encontrar a web dev key na AppsFlyer

1. Na página **meus aplicativos**, clique em **ver bundles de marc**a.
2. Clique no ícone de copiar na linha do bundle Xsolla.

![xsolla-brand-bundle2.jpg](https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg)

## Identificando os eventos do Xsolla no AppsFlyer

### Integração de parceiro técnico (S2S):

O Xsolla envia 2 eventos in-app para a AppsFlyer:

* **xsolla-billing-payment** - Item comprado
* **xsolla-billing-refund** - Reembolso de compra

Ambos os eventos fazem parte dos eventos in-app do aplicativo mobile.

### Integração do Web SDK:

O Xsolla envia à AppsFlyer vários eventos da web, personalizados para a atividade específica do anunciante. O mais importante é chamado "PURCHASE" e contém a receita de compras.  
Os eventos da web do Xsolla aparecem nos relatórios de atribuição da web do PBA e nos relatórios brutos de "Eventos da web" do DataLocker.

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

Suporte para PC / Console - a integração da AppsFlyer com o Xsolla não é compatível com aplicativos de PC / Console nessa fase

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Documentação do Xsolla</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=importante integration-types=tipos-de-integra%C3%A7%C3%A3o h_01J3DB8MCNQKKKCV1M39KN7Q0H=tipos-de-integra%C3%A7%C3%A3o setting-up-xsolla=configurando-a-integra%C3%A7%C3%A3o-do-parceiro-de-tecnologia h_01HST42K52JKQ70F7Y5PHDZAZ5=configurando-a-integra%C3%A7%C3%A3o-do-parceiro-de-tecnologia h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=ativar-parceiro h_01HST42K52RCTSGRNRCJ1C70NP=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01HST42K52BBJ6JS5KM0WCN6CF=privacidade-avan%C3%A7ada default-postbacks=postbacks-padr%C3%A3o h_01HST47F5BXWV5W8BNHS9M2MTN=postbacks-padr%C3%A3o inapp-event-postbacks=postbacks-de-eventos-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postbacks-de-eventos-in-app h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=configurando-a-integra%C3%A7%C3%A3o-do-pba-web-sdk h_01J3DEZZHDPSRZRXDV6FD4HY6Q=configurando-a-integra%C3%A7%C3%A3o-do-pba-web-sdk finding-the-web-dev-key-in-appsflyer=como-encontrar-a-web-dev-key-na-appsflyer h_01J3F247QEAFGRW7CEP941KZE9=como-encontrar-a-web-dev-key-na-appsflyer identifying-xsollas-events-in-appsflyer=identificando-os-eventos-do-xsolla-no-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=identificando-os-eventos-do-xsolla-no-appsflyer tech-partner-s2s-integration=integra%C3%A7%C3%A3o-de-parceiro-t%C3%A9cnico-s2s h_01JMHXS5MZ7B781WNNVYMDGGFY=integra%C3%A7%C3%A3o-de-parceiro-t%C3%A9cnico-s2s web-sdk-integration=integra%C3%A7%C3%A3o-do-web-sdk h_01JMHXX7VBPPS7GQ0VBGWRPT7X=integra%C3%A7%C3%A3o-do-web-sdk h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=veja-tamb%C3%A9m" />
