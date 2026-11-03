---
title: Configuração de campanhas da Avow GmbH
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-09-13T07:21:40Z'
  edited_at: '2026-08-19T00:24:19Z'
  id: 18523546870929
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/18523546870929
---
> **Visão geral:** a AVOW GmbH (avow1\_int) é um parceiro integrado com contas de ad networks e agências, permitindo que os anunciantes executem campanhas de aquisição de usuários em dispositivos mobile. Além da atribuição mobile baseada em cliques, a Avow GmbH também oferece a atribuição de view-through, que pode ser registrada na AppsFlyer.

![avow_icon.png](https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png)

## Ativar parceiro

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione**colaborar**> **Partner Marketplace**.  
   **Para editar**: na AppsFlyer, no menu lateral, selecione **colaborar** > **integrações ativas**
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na aba **integração**, selecione o aplicativo para a integração e clique em **ativar parceiro**.   
   **Observação:** essa opção deve permanecer habilitada (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor>) enquanto você trabalhar com o parceiro.   
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

## Configuração da Avow GmbH

A integração com a Avow GmbH oferece suporte para a atribuição de click-through e view-through. A janela de configuração inclui as seguintes abas: integração, link de atribuição, custo, receita de anúncios e permissões. Para a Avow GmbH, as abas disponíveis são as de integração, link de atribuição e permissões.

> 📘 **Observação**
>
> * Algumas configurações são diferentes para dispositivos iOS e Android
> * Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">configurar integrações de parceiros</Anchor>

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **integração** inclui várias seções, conforme descrito abaixo.

#### Ativar parceiro

Para configurar a integração, você deve primeiro <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#ativar-parceiro">habilitar</Anchor> o botão **ativar parceiro**. Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativar e desativar integrações de parceiros</Anchor>.

#### Privacidade avançada

Somente para aplicativos iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do status da **Privacidade Avançada (para iOS 14.5+ em diante)** :

| Privacidade avançada: ativada | Privacidade avançada: desativada |
| --- | --- |
| Postbacks são enviados apenas para eventos atribuídos ao parceiro | Postbacks são enviados de acordo com sua configuração:<ul><li>**Todas as fontes de mídia, inclusive orgânicas**</li><li>**Somente esse parceiro**</li></ul> |
| Os postbacks são enviados de acordo com o <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks">template de privacidade avançada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Dados agregados e anônimos</Anchor> são compartilhados com o parceiro, o que significa que nenhum dado no nível do usuário (ID do dispositivo) é compartilhado. |  |

#### Configurações gerais

**token**

Adicione o token de verificação fornecido pelo especialista da AVOW (AM/BDM).

#### Atribuição de instalação

Para atribuir instalações com view-through obtidas na Avow GmbH, ative a **atribuição de instalação com view-through**. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

#### Postbacks padrão

Postbacks de instalações e de instalações rejeitadas são enviados somente para esse parceiro.

#### Configurações de eventos in-app

**token**

Adicione o token de verificação fornecido pelo especialista da AVOW (AM/BDM).

#### Postback de eventos in-app

Configure o mapeamento de eventos in-app com eventos da Avow GmbH, enviados via postbacks:

1. Ative **postbacks de eventos in-app.**
2. Clique em **adicionar evento** para incluir um SDK ou evento de servidor para servidor. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **AppsFlyer Event**, depois clique em **criar personalizado**. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID de evento correspondente do parceiro.</li><li>**Menu suspenso:** selecione o AppsFlyer event pré-definido mais adequado</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem o mapeamento de nomes.</li></ul> |
| **para utilizadores de** | **Apenas esse parceiro:** os postbacks de eventos in-app são enviados apenas para eventos atribuídos a esse parceiro, ou seja, o usuário que realizou esses eventos chegou ao seu app a partir desse parceiro em específico. |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: envia apenas o evento em si, sem nenhum valor de evento.</li><li>**Valores e receita**: envia todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envia todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. [Opcional] Clique no ícone **adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Defina a **janela de postback de eventos in-app**, se necessário (saiba mais sobre a<Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app"> configuração dessa janela aqui</Anchor>).
5. Clique em **salvar integração.**
6. [Opcional] Após salvar a integração, ainda na página de configuração, você pode integrar mais aplicativos com o parceiro:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione a partir da lista suspensa.
   3. Repita as <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#integration-tab">etapas de integração</Anchor> para o aplicativo selecionado.

> 📘 **Observação**
>
> Somente para aplicativos iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> **depende do** <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">status da</Anchor> Privacidade Avançada (para iOS 14.5+ em diante).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição, enviando-os para o parceiro para atribuir campanhas, conjuntos de anúncios ou anúncios individuais - tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros dos links de atribuição</Anchor>. **Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de custo">

Os dados de custo não estão disponíveis para a Avow GmbH.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba de receita de anúncios">

A receita de anúncios não está disponível para a Avow GmbH.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Selecione as permissões que você deseja conceder à Avow GmbH, para que o parceiro possa acessar seus dados e executar diferentes ações.

> 📘 **Observação**
>
> * Quando a integração é <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">desativada</Anchor> enquanto a opção Permissões ainda está ativada, as permissões permanecem inalteradas.
> * Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">conceder permissões</Anchor>.

</Accordion>

<div data-zendesk-anchors="activate-partner=ativar-parceiro 01H88VAJH3B5ESK12D3ATMMVZ8=ativar-parceiro setting-up-amazon-dsp-integration=configura%C3%A7%C3%A3o-da-avow-gmbh 01H88VAJH3VENKYVRQY5RXN63P=configura%C3%A7%C3%A3o-da-avow-gmbh 01H88VAJH3BYZSXQGGZZJQ9N0C=observa%C3%A7%C3%A3o 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=ativar-parceiro-1 01H88VAJH34GP7FK1KTJGRDPM7=ativar-parceiro-1 advanced-privacy=privacidade-avan%C3%A7ada 01H88VAJH3G5FAR7RRNDEPNGME=privacidade-avan%C3%A7ada general-settings=configura%C3%A7%C3%B5es-gerais 01H88VAJH3F2FJK5YP3M2V7RWD=configura%C3%A7%C3%B5es-gerais install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HA6PNN6RJYTNXRAS3M9EA4M4=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HA79D908WB6G9FFDKDJNVHEM=configura%C3%A7%C3%B5es-de-eventos-in-app inapp-event-postbacks=postback-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postback-de-eventos-in-app 01H88VAJH36MYZ9W1YPWA92Z1Z=observa%C3%A7%C3%A3o-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=observa%C3%A7%C3%A3o-2" />
