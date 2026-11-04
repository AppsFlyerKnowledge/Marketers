---
title: Configuração de campanhas da Persona.ly RTB
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
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-08-19T00:25:37Z'
  id: 18699025653265
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/18699025653265
---
> **Resumo:** Persona.ly RTB (personalyrtb\_int), um parceiro integrado da AppsFlyer, é uma DSP mobile-first que opera no mundo todo. Usando um bidder proprietário e algoritmos de machine learning, a Persona.ly oferece soluções de UA e retargeting transparentes, orientadas por performance e altamente segmentadas.

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

<div id="setting-up-personaly-rtb" />

## Como configurar a Persona.ly RTB

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A integração com a Persona.ly RTB oferece suporte para a atribuição de click-through e view-through.  
A janela de configuração inclui as seguintes abas: integração, link de atribuição, custo, receita de anúncios e permissões. Para a Persona.ly RTB, as abas disponíveis são as de integração, link de atribuição e permissões.

<div id="note" />

> 📘 **Observação**
>
> * Algumas configurações são diferentes para dispositivos iOS e Android
> * Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">configurar integrações de parceiros</Anchor>

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

<div id="activate-partner" />

#### Ativar parceiro

Para configurar a integração, primeiro deve <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#ativar-parceiro">ligar</Anchor> o botão de alternância **Ativar parceiro**. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativar e desativar integrações de parceiros</Anchor>.

<div id="note-1" />

> 📘 **Nota**
>
> Como uma ad network "all-install", a Persona.ly RTB prefere receber postbacks para todas as novas instalações do seu app vindas de qualquer fonte. Para fazer isso, selecione **Todos os canais de mídia, incluindo orgânicos** para enviar todos os postbacks de instalação para a Persona.ly RTB.

<div id="advanced-privacy" />

#### Privacidade avançada

Somente para aplicativos iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do status da **Privacidade Avançada (para iOS 14.5+ em diante)** :

| Privacidade avançada: ativada | Privacidade avançada: desativada |
| --- | --- |
| Postbacks são enviados apenas para eventos atribuídos ao parceiro | Postbacks são enviados de acordo com sua configuração:<ul><li>**Todas as fontes de mídia, inclusive orgânicas**</li><li>**Somente este parceiro**</li></ul> |
| Os postbacks são enviados de acordo com o <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks">template de privacidade avançada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Dados agregados e anônimos</Anchor> são compartilhados com o parceiro, o que significa que nenhum dado no nível do usuário (ID do dispositivo) é compartilhado. |  |

<div id="transaction-id" />

#### ID da transação

Somente para aplicativos iOS, quando **Compartilhar ID de transação SKAN** está ativado, você permite que a AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartilhe o ID da transação dos postbacks da SKAdNetwork</Anchor> com a Persona.ly RTB. Ao fazer isso, a Persona.ly RTB pode decodificar seus Valores de conversão da SKAdNetwork.

<div id="install-attribution" />

#### Atribuição de instalação

Para atribuir instalações com view-through da Persona.ly RTB, ative **Atribuição de instalação com view-through**. O cursor de lookback de view-through está disponível na [aba do link de atribuição](#attribution-link-tab).

<div id="default-postbacks" />

#### Postbacks padrão

Para enviar postbacks automáticos para parceiros vinculados às ações dos usuários antes da abertura do app, defina qual é a fonte desses usuários:

* Para **instalações**, selecione uma das opções abaixo:
  * **Somente este parceiro:** envie postbacks somente quando a instalação for atribuída a este parceiro, ou seja, quando o usuário que instalou o aplicativo veio da Persona.ly RTB.
  * **Todas as fontes de mídia, incluindo orgânicas**: enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos — ou seja, o usuário que instalou o aplicativo veio de qualquer fonte de mídia.
* Para **instalações rejeitadas** e **reengajamentos:** os postbacks são enviados apenas para a Persona.ly RTB.

<div id="in-app-event-postbacks" />

#### Envios de eventos na aplicação

Configure o mapeamento de eventos in-app com eventos da Persona.ly RTB, enviados via postbacks:

1. Ative **postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para incluir um SDK ou evento de servidor para servidor. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID de evento correspondente do parceiro.</li><li>**Menu suspenso:** selecione o AppsFlyer event pré-definido mais adequado</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem o mapeamento de nomes.</li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro**: Envie postbacks apenas quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas:** Envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: envia apenas o evento em si sem nenhum valor de evento.</li><li>**Valores e receita**: envia todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envia todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a<Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app"> configuração dessa janela aqui</Anchor>).
5. Clique em **Salvar integração.**
6. [Opcional] Após salvar a integração, ainda na página de configuração, você pode integrar mais aplicativos com o parceiro:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione a partir da lista suspensa.
   3. Repita as <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#integration-tab">etapas de integração</Anchor> para o aplicativo selecionado.

<div id="note-2" />

> 📘 **Observação**
>
> Somente para aplicativos iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> **depende do** <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">status da</Anchor> Privacidade Avançada (para iOS 14.5+ em diante).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição, enviando-os para o parceiro para atribuir campanhas, conjuntos de anúncios ou anúncios individuais - tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros dos links de atribuição</Anchor>. **Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não está disponível para a Persona.ly RTB.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Selecione quais <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões conceder</Anchor> à Persona.ly RTB para acessar seus dados e executar diferentes ações.

<div id="note-3" />

> 📘 **Observação**
>
> Quando a integração é <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">desativada</Anchor>, mas o botão de permissões ainda está ativado, as permissões permanecem concedidas.

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=como-configurar-a-personaly-rtb 01H88VAJH3VENKYVRQY5RXN63P=como-configurar-a-personaly-rtb 01H88VAJH3BYZSXQGGZZJQ9N0C=observa%C3%A7%C3%A3o 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=ativar-parceiro 01H88VAJH34GP7FK1KTJGRDPM7=ativar-parceiro h_01HBB9EEMJ55BQDJ1ZEJT136ZF=nota advanced-privacy=privacidade-avan%C3%A7ada 01H88VAJH3G5FAR7RRNDEPNGME=privacidade-avan%C3%A7ada transaction-id=id-da-transa%C3%A7%C3%A3o h_01HARQDVEDA206D0BBXBC6WEHH=id-da-transa%C3%A7%C3%A3o install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HA6PNN6RJYTNXRAS3M9EA4M4=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-padr%C3%A3o inapp-event-postbacks=envios-de-eventos-na-aplica%C3%A7%C3%A3o 01H88VAJH3AS37MVF75GANWX4B=envios-de-eventos-na-aplica%C3%A7%C3%A3o 01H88VAJH36MYZ9W1YPWA92Z1Z=observa%C3%A7%C3%A3o-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=observa%C3%A7%C3%A3o-2" />
