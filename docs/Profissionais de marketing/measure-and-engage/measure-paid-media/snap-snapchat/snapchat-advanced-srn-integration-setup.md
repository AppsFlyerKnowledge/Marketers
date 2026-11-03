---
title: Snapchat – configurando a integração de uma SRN avançada
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-08T00:15:47Z'
  id: 211011983
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/211011983
---
> **At a glance:** Descubra como configurar a integração entre a AppsFlyer e o Snapchat para ativar a métrica de atribuição. O Snapchat é uma SRN avançada (Self-Reporting Network).

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

## Visão Geral

Uma integração avançada de SRN significa que todo o tráfego com <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">consentimento duplo</Anchor> é atribuído e reportado como tráfego SRN regular. Para tráfego não consentido, a AppsFlyer pode atribuir e medir a atribuição com base em cliques e impressões provenientes do Snapchat utilizando <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#como-funciona-a-atribuição-para-srnsavançadas">outros métodos de atribuição</Anchor>, de acordo com as restrições de privacidade.

## Configurar a integração do Snapchat

**Pré-requisito:** Uma conta com o Snapchat. Se você não tiver uma conta, entre em contato com o Snapchat para abrir uma antes de configurar a integração.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   (**Para editar uma integração existente:** Vá para a guia **Collaborate > Partner Integrations > Active integrations**.)
2. Selecione o aplicativo correspondente.
3. Procure o **Snapchat** e selecione-o.
4. Na guia **Integração** , ative o botão de alternância **Activate partner** .  
   **Observação:** o botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com Snapchat**. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação e desativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de parceiros</Anchor>.

<Accordion title="Aba Integração">

A integração é compatível com atribuição de cliques e impressões, custo e audiências.

#### Ativar parceiro

Na **primeira visita** aqui, você deve ativar **Ativar parceiro** para habilitar a configuração.  
Para mais detalhes sobre a ativação do parceiro, consulte <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Ativação e desativação de parceiro</Anchor>.

**Ativar atribuição**

Habilite **Ativar parceiro** para permitir a atribuição ao Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

#### Configurações gerais

**ID do Snap App**

1. No seu Snap Business Manager, vá para Aplicativos e copie o Snap App ID (leia o guia do Snapchat sobre <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">como gerar um Snap App ID</Anchor>).
2. Cole o ID no campo Snap App ID na AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**Se o aplicativo for promovido por uma agência**:

* O Snap App ID só pode ser adicionado pelo anunciante.
* Se a agência estiver sob a mesma organização que você na plataforma de anúncios do Snapchat, use apenas um Snap App ID.
* Se a agência estiver sob uma organização diferente na plataforma de anúncios do Snapchat, peça o Snap App ID da agência para este aplicativo e insira-o neste campo. Vários IDs podem ser inseridos. Pressione Enter após cada ID.

#### Agregada da AppsFlyer

O botão de alternância **Advanced Privacy** (AP) controla quais eventos a AppsFlyer envia para o Snapchat. Essa configuração também é chamada de **Advanced Conversions** no Snapchat.

* **Advanced Privacy OFF**: a AppsFlyer envia todas as instalações, reengajamentos e eventos in-app para o Snapchat para atribuição, incluindo eventos de usuários que não disponibilizaram o IDFA (identificador para anunciantes).  
  **Importante:** Para usar a <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/unified-attribution?language=en_US">solução de atribuição unificada</Anchor> do Snapchat, você deve desativar o botão de alternância Advanced Privacy.
* **Advanced Privacy ON**: a AppsFlyer envia apenas instalações, reengajamentos e eventos in-app de usuários que disponibilizaram o IDFA.

> 📘 **Note**
>
> Uma agência não pode ativar a configuração de privacidade avançada (mesmo quando recebe permissão). Isso é limitado apenas ao anunciante.

#### Compartilhamento de dados de correspondência avançada

Quando o **Compartilhamento de dados de correspondência avançada** está ativado, os campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, são compartilhados com o Snapchat se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

#### Atribuição de instalação

Defina as diferentes janelas de atribuição para atribuir novas instalações (primeiros lançamentos) de usuários que visualizaram, clicaram ou interagiram com seu anúncio. Tenha em conta que apenas as instalações dentro da janela de retrospetiva podem ser atribuídas ao Snapchat.

**Nota:** a atribuição para reinstalações (qualquer instalação que não seja a configuração inicial no dispositivo) não é suportada.

1. Defina a **janela de lookback de clique de instalação** para 1 a 23 horas ou 1 a 30 dias. **Nota:** o Snapchat recomenda alinhar com eles definindo a janela de lookback de clique de instalação como 7 dias.

> 📘 **Note**
>
> A configuração da janela de retrospectiva por clique também determina as janelas de retrospectiva para visualizações engajadas e cliques engajados.

2. [Opcional] Ative a **atribuição de view-through** e configure as janelas de lookback:
   * **Janela de lookback de view-through** entre 1 e 24 horas. **Nota:** O Snapchat recomenda alinhar-se com eles definindo a janela de retrospetiva de visualização da instalação para 1 dia.

#### Atribuição de reengajamento

Configure as diversas janelas de atribuição para contabilizar reaquisições de utilizadores existentes que visualizaram, clicaram ou interagiram com o seu anúncio. Lembre-se que apenas os reengajamentos dentro da janela de retrospetiva podem ser atribuídos ao Snapchat.

1. Defina a **janela de reengajamento de clique de instalação** para 1 a 23 horas ou 1 a 30 dias. **Nota:** o Snapchat recomenda alinhar com eles definindo a janela de lookback de clique de reengajamento como 7 dias.

> 📘 **Note**
>
> A configuração da janela de retrospectiva por cliques de reengajamento também determina as janelas de retrospectiva de reengajamento para visualizações engajadas e cliques engajados.

2. [Opcional] Ative a **atribuição de view-through de reengajamento** e defina as janelas de lookback:
   * **Janela de lookback de view-through** entre 1 e 24 horas. **Nota:** O Snapchat recomenda alinhar-se com eles ao definir a janela de retrospetiva de visualização de reengajamento para 1 dia.
3. Defina a **janela de reengajamento** como 1-23 horas, 1-90 dias ou **Lifetime**.

#### Ignorar usuários ativos para retargeting

Defina um período de tempo para <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window#período-de-inatividade">ignorar reengajamentos e reatribuições</Anchor> de usuários que inicializaram o seu aplicativo. Isto significa que a sua atividade durante o período da janela não é registrada na AppsFlyer.

> 📘 **Note**
>
> As conversões de reengajamento e reatribuição de usuários que estavam **inativos** no período definido **são registradas**.

1. Ative a opção **Ignorar utilizadores ativos para retargeting**.
2. Defina a janela de inatividade.

#### Postback de eventos in-app

Mapeie eventos da AppsFlyer com o parceiro via postbacks. Se o envio de postbacks estiver ativado, isso inclui eventos in-app rejeitados (eventos bloqueados pelo Protect360 ou eventos considerados não compatíveis com as regras de validação de destino).

[![mceclip0.png](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

**Para configurar os postbacks de eventos na aplicação:**

1. Defina o **Partner ID** (se necessário).
2. Ative o **postback de evento in-app.**
3. Defina a **janela de postback de evento in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração da janela de postback de evento in-app</Anchor>).
4. Quando disponível, selecione se deseja enviar eventos automaticamente ou manualmente. Saiba mais sobre como enviar todos os eventos como eles são originalmente.
5. Clique em **Adicionar evento** para adicionar um evento de SDK ou servidor para servidor à lista.
6. Complete os parâmetros necessários.
7. [Opcional] Clique em <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para definir condições para enviar determinados eventos na aplicação ao parceiro.  
   Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">in-app event postbacks</Anchor>.

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer** , depois clique em **Criar personalizado**. Leia mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** Obtenha o ID do evento correspondente do parceiro.</li><li>**Caixa suspensa:** Selecione o evento predefinido da AppsFlyer mais adequado.</li><li>**Como está**: envie os eventos como estão, sem mapeamento de nomes.</li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo as orgânicas**: enviar postbacks para eventos atribuídos a qualquer parceiro e eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envie todos os parâmetros **excluindo** o valor da receita.</li></ul> |

</Accordion>

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Snapchat.

> 📘 **Note**
>
> Para todas as SRNs, como Facebook, Apple Ads, Google Ads e Snapchat, esta guia não é funcional, pois elas não usam links de atribuição externa.

</Accordion>

<Accordion title="Aba de custo">

A integração de custos fornece os seguintes dados agregados:

* Dados de custo para suas campanhas, conjuntos de anúncios, anúncios e níveis de canal. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.Nota: **Os dados de custo exigem uma assinatura do <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.**
* Dados sobre cliques e impressões.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Status de sincronização dos dados de custo">

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Interromper a sincronização de custos do Snapchat">

**Para parar de receber o custo do Snapchat e excluir uma conta do Snapchat conectada:**

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Na coluna de ações, passe o mouse sobre uma conta e clique em **Excluir conexão**</Anchor>.  
  Feito isso, a AppsFlyer deixa de receber dados de custo. Deletar a conexão não afeta os dados históricos.

</Accordion>

> 📘 **Note**
>
> * Certifique-se de que a configuração da sua campanha no Snapchat seja para um aplicativo iOS ou Android, não ambos. Se a campanha for para ambos os aplicativos, a AppsFlyer não pode detalhar o custo por aplicativo e o custo não é exibido na AppsFlyer.
> * Para evitar discrepâncias nos dados de custo, defina o mesmo fuso horário nas configurações do aplicativo e na sua conta de publicidade do Snapchat.
> * Depois de definir o custo do Snap, não altere o nome de nenhuma campanha ativa, conjunto de anúncios ou anúncio único, pois isso pode causar discrepâncias graves ou ausência de dados de custo.

</Accordion>

<Accordion title="Aba de receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<Accordion title="Aba permissões">

Selecione quais <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões você deseja conceder</Anchor> ao Snapchat, para que o parceiro possa acessar seus dados e executar diferentes ações.

> 📘 **Note**
>
> Quando a integração é desativada enquanto o alternador de Permissões ainda está ativado, as permissões continuam a ser concedidas.

</Accordion>

## Web para app: mensuração da atividade no aplicativo para campanhas não relacionadas a apps

A integração da AppsFlyer com o Snapchat permite a mensuração abrangente da atividade no aplicativo, como instalações, reengajamentos e eventos in-app, para campanhas não relacionadas a apps atribuídas ao Snapchat.

Por exemplo, as instalações de aplicativos podem ser mensuradas mesmo quando o destino do anúncio é uma web landing page, permitindo a mensuração da jornada web-to-app (W2A). Para ativar esse tipo de mensuração, ative a opção <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/app-id-tracking">Snap App ID Tracking Toggle</Anchor> no Gerenciador de Anúncios do Snapchat.

Ao seguir estas instruções, você pode mensurar com eficácia a atividade do aplicativo a partir de campanhas não relacionadas a aplicativos do Snapchat e obter insights valiosos sobre o comportamento do usuário.

## Deep linking com o Snapchat

O deep linking com o Snapchat é baseado no uso de um deep link nativo na plataforma do Snapchat, enquanto adiciona parâmetros da AppsFlyer a ele.

Para executar deep linking com o Snapchat:

1. Verifique se o **deep linking** para [retargeting está ativado para o Snapchat](/docs/snapchat-advanced-srn-integration-setup#configure-deep-links-na-plataforma-snap).
2. Verifique se <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">a atribuição de reengajamento está habilitada na AppsFlyer</Anchor>.
3. Pegue o URI do esquema de deep link do aplicativo e adicione **pelo menos** os seguintes parâmetros:
   * **PID** - O canal de mídia neste caso é sempre **snapchat\_int**. Isso permite que todos os dados apareçam no dashboard da AppsFlyer no canal de mídia **Snapchat\_int** .
   * **C -** o nome da campanha relevante
   * **is\_retargeting=true -** Este campo define a campanha como uma campanha de retargeting. Os engajamentos de usuários existentes com a campanha de retargeting são marcados como reengajamentos devido à existência deste campo no URI. Isso garante que os dados do usuário apareçam no painel de retargeting.

> 📘 **Note**
>
> **Exemplo de URI**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Configure deep links na plataforma Snap

1. Acesse o tipo de oportunidade **Direcionar tráfego para o aplicativo** .
2. Adicione o URI do deep link:  
     
   [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### Deferred deep linking com o Snapchat

A AppsFlyer fornece várias soluções para deep linking diferido:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**UDL (Unified deep linking)**</Anchor> : Os cliques do Snapchat incluem um campo <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> (quando o deep link é definido para o anúncio) e têm suporte na solução UDL.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD (Get Conversions Data) API**</Anchor> : esta é a opção recomendada para acessar os dados de conversão dos usuários do Snapchat em tempo real, diretamente no nível do SDK. Os dados retornados na GCD API incluem <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor>, que contém o destino do deep link (destino do usuário no aplicativo).
* **Como usar parâmetros de dados de conversão:** você pode criar uma lógica personalizada para levar o usuário ao seu conteúdo usando outros parâmetros, como o nome da campanha, o nome do conjunto de anúncios ou qualquer outro campo retornado como parte dos dados de atribuição para instalações do Snapchat.

## Configurar o Snapchat para agências

As agências que trabalham em nome de anunciantes podem ativar a integração com o Snapchat e começar a receber atribuição por suas campanhas. Contudo, esta integração tem algumas limitações quando se trata de agências.

### Limitações da agência

* Uma agência pode acessar a integração com o Snapchat somente depois que o anunciante com quem trabalha a ativar do lado dela.
* Os parâmetros de atribuição exibidos na página de integração da agência são herdados da integração do anunciante no **modo visualização** . Isso significa que a agência pode ver como o anunciante configurou as janelas de retrospectiva de atribuição, mas não pode configurá-las sozinha.
* Para eventos pós-atribuição, se o anunciante tiver permissão, uma agência poderá configurar postbacks de eventos in-app.
* Uma agência não pode ativar a Privacidade Avançada, mesmo quando recebe permissão (consulte **Privacidade Avançada** acima).

**Para configurar o Snapchat para agências:**

1. Na AppsFlyer, em **Configuração**, vá para **Marketplace de Parceiros**.
2. Encontre o **Snapchat** e selecione-o.
3. Insira o **ID da conta do Snapchat** da sua agência. Isso identifica o tráfego da agência e o distingue do do anunciante. Você pode inserir até 50 IDs de conta do Snapchat diferentes. Todos os dados de atribuição provenientes das contas inseridas ficam visíveis no dashboard da agência.
4. Clique em **Salvar integração**.

![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> 🚧 **Important**
>
> Os IDs das contas do Snapchat não devem ser compartilhados entre o anunciante e a agência. Se forem compartilhados, todas as instalações do anunciante serão atribuídas automaticamente no dashboard da agência.

## Restrições de dados brutos

* A partir de 1º de março de 2023, as desinstalações do Snapchat não serão incluídas nos relatórios de dados brutos.
* A partir de 12 de setembro de 2023, o Snapchat fornecerá aos anunciantes dados de atribuição de visualização limitados no nível do dispositivo. Para fontes de nível de usuário, como relatórios de dados brutos, mensagens da Push API, relatórios da Pull API, página Exportar dados e Data Locker, apenas os seguintes campos são preenchidos:
  * Fonte de mídia (snapchat\_int)
  * Canal
  * Tipo de toque atribuído (impressão)
  * Tempo de toque atribuído (relatado apenas como data - "dd/mm/aaaa")
  * Nome e ID da campanha (a partir de 15 de dezembro de 2025)
  * Nome e ID do conjunto de anúncios (a partir de 15 de dezembro de 2025)
* A partir de 6 de outubro de 2026, os dados de atribuição de view-through de `snapchat_int` ficam limitados (restritos) apenas nos dados brutos em alguns casos. A lógica das restrições de evento é gerenciada pelo Snapchat.

## Retenção de dados do Snapchat

O Snapchat exige que os provedores de atribuição excluam seus dados no nível do usuário 12 meses após a instalação O Snapchat exige que os provedores de atribuição excluam seus dados no nível do usuário 12 meses após a instalação Isso significa que os eventos realizados por esses usuários 12 meses após a instalação do aplicativo são contados como orgânicos. O Snapchat exige que os provedores de atribuição excluam seus dados no nível do usuário 12 meses após a instalação Isso significa que os eventos realizados por esses usuários 12 meses após a instalação do aplicativo são contados como orgânicos.

Os dados agregados passados permanecem os mesmos.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8F1RWVPTHBDGF3830DY7G7M=vis%C3%A3o-geral setting-up-snapchat-integration=configurar-a-integra%C3%A7%C3%A3o-do-snapchat 01H7WQ47ECTZHPKMG5Z5ZPAND5=configurar-a-integra%C3%A7%C3%A3o-do-snapchat activate-partner=ativar-parceiro 01H7WQ47ECZB5GNCQ0XH68N1DK=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais 01H7WQ47ECQSQPP63H398NTQ6M=configura%C3%A7%C3%B5es-gerais h_01_advanced-privacy=agregada-da-appsflyer advanced-privacy=agregada-da-appsflyer h_01_advanced-matching-data-sharing=compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada advanced-matching-data-sharing=compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o 01H8VVCC8GK8VFPBEPAMVHCAWM=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o reengagement-attribution=atribui%C3%A7%C3%A3o-de-reengajamento 01H8VVCC8HHG5290PYF0BT29QA=atribui%C3%A7%C3%A3o-de-reengajamento ignore-active-users-for-retargeting=ignorar-usu%C3%A1rios-ativos-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usu%C3%A1rios-ativos-para-retargeting inapp-event-postback-settings=postback-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postback-de-eventos-in-app 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync web-to-app-measuring-app-activity-for-nonapp-campaigns=web-para-app-mensura%C3%A7%C3%A3o-da-atividade-no-aplicativo-para-campanhas-n%C3%A3o-relacionadas-a-apps h_01JJMAS0W9WMEPJCQWD9BXAEZ2=web-para-app-mensura%C3%A7%C3%A3o-da-atividade-no-aplicativo-para-campanhas-n%C3%A3o-relacionadas-a-apps deep-linking-with-snapchat=deep-linking-com-o-snapchat 01H7WQ47EDC973V7CPE38QAQE7=deep-linking-com-o-snapchat how-to-set-up-deep-links-on-snap-platform=configure-deep-links-na-plataforma-snap 01H7WQ47EDJAX2DW7A2JJ4XVJN=configure-deep-links-na-plataforma-snap deferred-deep-linking-with-snapchat=deferred-deep-linking-com-o-snapchat 01H7WQ47EDS3MYRN9A9ZPHXG9Z=deferred-deep-linking-com-o-snapchat setting-up-snapchat-for-agencies=configurar-o-snapchat-para-ag%C3%AAncias 01H7WQ47EDARK9SSP47V5MGX18=configurar-o-snapchat-para-ag%C3%AAncias agency-limitations=limita%C3%A7%C3%B5es-da-ag%C3%AAncia h_01HHVGS94CB9XC0T63VFDZ18JS=limita%C3%A7%C3%B5es-da-ag%C3%AAncia raw-data-restrictions=restri%C3%A7%C3%B5es-de-dados-brutos h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=restri%C3%A7%C3%B5es-de-dados-brutos keeping-snapchat-data=reten%C3%A7%C3%A3o-de-dados-do-snapchat 01H7WQ47ED9STKS1CVW5EXYX0Z=reten%C3%A7%C3%A3o-de-dados-do-snapchat" />
