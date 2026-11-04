---
title: Integração do Medialyzer com a AppsFlyer
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
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-08-18T00:12:01Z'
  id: 14963611180689
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/14963611180689
---
> **Visão geral:** Medialyzer, um parceiro integrado da AppsFlyer, desenvolve e comercializa o software como solução de serviço. A solução permite que planejadores de mídia otimizem suas campanhas de TV para negócios online com base em visitas e conversões geradas imediatamente por veiculação de anúncio de TV.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para este parceiro, independentemente da seleção configurada para envio de postbacks.

<div id="setting-up-medialyzer" />

## Configurando o Medialyzer

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, selecione o aplicativo para a integração e habilite **Ativar parceiro**.  
   **Observação:** a alavanca deve permanecer habilitada (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor>) enquanto você trabalhar com o parceiro.
2. Selecione o aplicativo correspondente.
3. Clique em **Configurar a integração**.
4. Na sua primeira visita, você precisará habilitar a opção **Ativar parceiro** para configurar a integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

<div id="activate-partner" />

#### Ativar parceiro

A configuração é feita na página **Integrações Ativas** , mas para encontrar o parceiro você deve primeiro ir ao <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations">marketplace</Anchor>. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.

<div id="advanced-privacy" />

#### Privacidade avançada

Para aplicativos iOS, a alavanca <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada</Anchor> é exibida. Quando ativada, ela limita o compartilhamento de identificadores de usuário com o parceiro. Observe que, quando o botão <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor> está ativado nas configurações do aplicativo, **Privacidade Avançada (para iOS 14.5+ e posterior)** está ativada e bloqueada por padrão.

<div id="default-postbacks" />

#### Postbacks padrão

A AppsFlyer envia postbacks padrão para o Medialyzer após as instalações do usuário. Use esta seção para <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#f">definir esses postbacks</Anchor>.

* **Desativada**: os postbacks de instalação não são enviados ao Medialyzer.
* **Todas as fontes de mídia, incluindo orgânicas**: postbacks de instalação são enviados para eventos atribuídos a qualquer parceiro e para eventos orgânicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Postback de evento in-app

Nesta seção, você pode mapear seus eventos AppsFlyer com seus parceiros via postbacks.

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento servidor para servidor à lista.
3. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **mapeado para evento parceiro** | Insira o nome de evento correspondente ou ID de cada evento, conforme definido no BPM, ou envie os eventos como estão sem mapeamento de nome. |
| **para usuários de** | Selecione **Todas as fontes de mídia, incluindo orgânicas** para enviar para eventos atribuídos a qualquer parceiro e para eventos orgânicos. |
| **incluindo** | <ul><li>**Sem valores e sem receita**: envie apenas o próprio evento sem parâmetros (valores ou receita).</li><li>**Valores e sem receita**: envie todos os parâmetros **excluindo** o valor da receita.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se houver no evento).</li></ul> |

4. Clique em **Save Integration** (Salvar integração).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Links de atribuição não estão disponíveis para Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba Cost (Custo)">

Os dados de custo não são suportados na integração com o Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Ad Revenue (Receita de anúncios)">

Os dados de receita publicitária não são compatíveis com a integração com o Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

As permissões não estão disponíveis para o Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=importante setting-up-spoteffects=configurando-o-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=configurando-o-medialyzer h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=ativar-parceiro h_01H9FKEAV3DW2A6RQ1NS44FT5F=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01H9FKEAV3T3YCPBYW70QVF540=privacidade-avan%C3%A7ada default-postbacks=postbacks-padr%C3%A3o h_01H9FKEAV3Z1Y09P6E18J8AVX2=postbacks-padr%C3%A3o inapp-event-postbacks=postback-de-evento-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postback-de-evento-in-app h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
