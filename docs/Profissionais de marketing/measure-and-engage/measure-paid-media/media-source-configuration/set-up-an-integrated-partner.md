---
title: Configure um parceiro integrado
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-09-01T00:30:10Z'
  id: 4410395957521
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/4410395957521
---
> **Resumo:** ative a mensuração de atribuição, envie postbacks aos parceiros e ative outras funcionalidades de integração configurando a conexão do seu parceiro na AppsFlyer.

<div id="overview" />

## Visão geral

Parceiros, fontes de mídia e plataformas externas se integram à AppsFlyer através da API. Este artigo contém as instruções genéricas para ativar e configurar a integração, incluindo a geração de links de atribuição para ad networks não-SRN.

* Este guia não se aplica a SRNs. Use o artigo específico para <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRN</Anchor>.
* Algumas ad networks possuem artigos específicos.
* Antes de configurar, fale com o parceiro e abra uma conta com ele.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Tipos de parceiros no ecossistema">

A imagem abaixo mostra os diferentes tipos de parceiros que compõem o ecossistema de atribuição.

[![Ecosystem.jpg](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)

**Leitura relacionada**: O <Anchor target="_blank" href="https://www.appsflyer.com/pt/performance-index/">Performance Index da AppsFlyer</Anchor> classifica as fontes de mídia mobile por categoria e região.

| Tipo de parceiro | Descrição |
| --- | --- |
| Redes de anúncios | Executam campanhas em seu nome. |
| Agências | Usam seus conhecimentos para obter usuários de alta qualidade executando campanhas em seu nome. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/view-agency-data">dados da agência</Anchor>. |
| Parceiros de marketing | Os parceiros de marketing se especializam em trabalhar com ad networks específicas. Exemplos: Parceiros de gerenciamento de campanhas da Meta, parceiros de marketing do Apple Search Ads e parceiros de marketing do X. |
| Retargeting networks | Ad networks especializadas em campanhas de retargeting. |
| Plataformas de terceiros | Fornecem serviços relacionados a BI, como análise e automação de marketing. |
| Detecção de fraudes | Sistemas de detecção de fraude externos de terceiros que não fazem parte da solução antifraude Protect360 da AppsFlyer. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Parceiros nas integrações de parceiros">

Todos os parceiros, fontes de mídia e outras plataformas integradas à AppsFlyer podem ser encontrados na página de integrações de parceiros. Você pode encontrar seus parceiros <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativos e inativos</Anchor> e procurar novos parceiros para se conectar.

**Para procurar e filtrar todos os parceiros, fontes de mídia ou outras plataformas na página de integrações de parceiros:**

* Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações de parceiros**. Você pode usar os vários filtros de pesquisa.

<div id="invite-new-partners-to-appsflyer" />

#### Convide novos parceiros para a AppsFlyer

Se o parceiro com quem você está trabalhando ainda não estiver integrado à AppsFlyer, você <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#convide-novos-parceiros-para-a-appsflyer">poderá enviar um link de convite</Anchor>.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Seus parceiros integrados ativos">

A aba de integrações ativas na página “Integrações de parceiros” mostra todos os seus parceiros integrados <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativos</Anchor>. Nessa aba, você pode saber mais sobre um parceiro e gerenciar sua integração.

<div id="note" />

> 📘 **Observação:**
>
> A lista de parceiros mostrada na aba **Integrações ativas** varia de acordo com o aplicativo selecionado. Você pode ver quais parceiros estão conectados a outros aplicativos clicando no aplicativo no canto superior esquerdo e selecionando um aplicativo diferente.

**Para ver todos os seus parceiros ativos:**

* Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiro** > **Integrações ativas**.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="Sobre a página de configuração do parceiro">

A página está estruturada da seguinte forma:

* **Header**, contendo:
  * Nome do parceiro
  * Link para um artigo dedicado ao parceiro. Caso não exista um artigo dedicado, será apresentado este artigo.
  * Status da integração
  * Aplicativo selecionado
* **Abas de configurações**: as abas disponíveis dependem do tipo de parceiro e dos recursos compatíveis.
* **Rodapé**:
  * **Voltar à lista**: retorne à lista de Integrações ativas usando as opções de filtro selecionadas anteriormente.
  * **Mensagem de status:** status atual dos dados da aba (por exemplo, salvando, salvo, erro, alterações não salvas).
  * **Descartar alterações:** desfaz as últimas alterações, sem salvar.
  * **Salvar:** salva apenas as configurações da aba atual.

<div id="applicable-settings-tabs-per-partner-type" />

#### Abas de configurações aplicáveis por tipo de parceiro

<table><thead><tr><th> </th><th colspan="2">Aba de Configurações</th><th> </th></tr><tr><th>Tipo de parceiro</th><th>Integração </th><th>Authorization: Bearer</th><th>Observações</th></tr></thead><tbody><tr><td>Fonte de mídia</td><td>S</td><td>S</td><td><p><strong>Guias adicionais disponíveis</strong>: Custo, receita de anúncios, link de atribuição</p><p>Incluindo ad networks, redes afiliadas, publishers diretos, anúncios programáticos,  ad networks internas da China e redes de retargeting.<br/>Para SRNs, a aba de link de atribuição não se aplica.</p></td></tr><tr><td>Agência </td><td>Não</td><td>S</td><td>Agências independentes que não funcionam como ad networks</td></tr><tr><td>Plataforma externa</td><td>S</td><td>Não</td><td>Plataformas de análise ou automação de marketing</td></tr><tr><td>Parceiro de marketing </td><td>S</td><td>Não</td><td> </td></tr></tbody></table>

</Accordion>

<div id="set-up-a-partner-non-srn" />

## Configurar um parceiro (não-SRN)

<div id="important" />

> 🚧 **Importante!**
>
> Ao ativar uma integração de parceiro, certos dados, incluindo informações pessoais (por exemplo, Advertising ID, endereço IP), serão, por padrão, compartilhados com eles por você. Por favor, certifique-se de que você tem a base legal e os direitos apropriados para compartilhar esses dados. Você pode limitar o compartilhamento de dados com um parceiro seguindo as instruções fornecidas no <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">framework de Privacidade Avançada Agregada</Anchor> e nos artigos sobre <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">métodos de proteção da privacidade no SDK</Anchor>.

**Para acessar as configurações e configurar suas campanhas com o parceiro:**

Pesquise e selecione o seu parceiro, em [Integrações de parceiros](/docs/set-up-an-integrated-partner#partners-in-the-marketplace).

<div id="note-1" />

> 📘 **Observação:**
>
> A etapa [Configurações gerais](#d-general-settings) na aba **Integração** é obrigatória para todos os parceiros Você também deve preencher a aba **Link de atribuição** para ad networks não-SRN. Você também deve preencher a aba **Link de Atribuição** para ad networks não SRN. As abas restantes são opcionais.

<div id="integration-tab" />

<Accordion title="Aba de integração">

As integrações dos parceiros variam nos seus requisitos e podem conter um subconjunto de todas as opções descritas nesta seção. Existem algumas diferenças entre as configurações do iOS e do Android.

![set_up_an_integrated_partner.png](https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png)

Complete as seções conforme necessário.

<div id="integration-sections" />

#### Seções de integração

A tabela a seguir inclui diferentes seções da página de integração. Algumas seções estão disponíveis para todos, outras são específicas por integração.

<Table>
  <thead>
    <tr>
      <th>
        Seção
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a-activate-partner"></span>
        Ativar parceiro
      </td>
      <td>
        Antes de compartilhar links de atribuição com um parceiro, você deve habilitar **Ativar parceiro** e concluir as seções restantes da aba Integração.

        * Não use **Ativar parceiro** para pausar ou desativar a atribuição de uma campanha
        * A desativação da integração de parceiros **pode causar danos irreversíveis às campanhas ativas**.
        * Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação do parceiro</Anchor> e como a sua desativação pode te afetar.

        **Para ativar um parceiro integrado**:

        1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros**.
        2. Procure e selecione o parceiro. Você é direcionado para a página de configuração do parceiro.
        3. Ative <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">**Ativar parceiro**</Anchor>.
        4. Clique em **Salvar integração.**
        5. [Opcional] Para permitir que o parceiro <Anchor target="_blank" href="/marketers/pt/docs/manage-data-access-permissions">visualize os dados atribuídos a ele</Anchor>, certifique-se de [ativar as permissões para ad network](/docs/set-up-an-integrated-partner#permissões-da-ad-network) na aba [Permissões](/docs/set-up-an-integrated-partner#permissions-tab).
      </td>
    </tr>
    <tr>
      <td><span id="b-advanced-privacy"></span>
        Privacidade avançada
      </td>
      <td>
        Somente para aplicativos iOS:  
        Quando a **Privacidade Avançada (para iOS 14.5 e versões mais recentes)** está ativa, você pode <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">controlar quais dados você deseja compartilhar</Anchor> com o parceiro através de postbacks e relatórios. Isso limita o compartilhamento de identificadores de usuários com o parceiro. Quando o botão <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor> está ativado nas configurações do app, a **Privacidade Avançada (para iOS 14.5 e versões mais recentes)** é ativada e não pode ser desativada.
      </td>
    </tr>
    <tr>
      <td><span id="c-transaction-id"></span>
        ID da transação
      </td>
      <td>
        Somente para aplicativos iOS:  
        Quando **compartilhar transaction ID da SKAN** está ativado, você <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartilha o transaction ID dos postbacks da SKAdNetwork</Anchor> com o parceiro. Ao fazer isso, o parceiro pode descriptografar os seus valores de conversão da SKAdNetwork.
      </td>
    </tr>
    <tr>
      <td><span id="d-general-settings"></span>
        Configurações gerais
      </td>
      <td>
        **Partner ID — Credenciais**  
        Alguns parceiros exigem credenciais para que a AppsFlyer se integre a eles. Os parceiros referem-se a esse ID como app ID, account ID, user ID ou network ID. Se esse campo for exibido, obtenha o ID do dashboard do parceiro e insira-o no campo.
      </td>
    </tr>
    <tr>
      <td><span id="non-eu-users"></span>
        Usuários fora da UE
      </td>
      <td>
        Decida se você deseja ou não ativar a opção <Anchor target="_blank" href="/marketers/pt/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Usuários fora da UE**</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        Atribuição de instalação
      </td>
      <td>
        Defina as diferentes janelas de atribuição para atribuir novas instalações (primeiras inicializações) de usuários que visualizaram ou clicaram no seu anúncio. A janela de lookback de atribuição é o tempo máximo entre um clique ou visualização do seu anúncio até à instalação, durante o qual as instalações podem ser atribuídas ao parceiro.

        * **Janela de lookback de click-through:** Defina o período máximo, após o click-to-app dentro do qual uma instalação pode ser atribuída ao clique.

        **Atribuição de view-through: Ative para começar a atribuir novas instalações feitas por usuários que visualizam seu anúncio, mas não clicam nele.**

        * **Janela de lookback de view-through:** Defina o período máximo, após uma visualização, dentro do qual uma instalação pode ser atribuída à visualização.

        <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Saiba mais sobre as janelas de lookback</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        Atribuição de reengajamento
      </td>
      <td>
        Ative e configure as janelas de lookback para começar a atribuir reengajamentos dos seus usuários existentes. Para não SRNs, essa configuração está disponível na aba Integração ou na aba do [link de atribuição](/docs/set-up-an-integrated-partner#configurações-de-retargeting).

        * **Janela de lookback de clique de reengajamento:** Defina o período máximo, após um click-to-app, dentro do qual a abertura de um aplicativo pode ser atribuída ao clique como um reengajamento.

        **Atribuição de view-through para reengajamento:** Ative para começar a atribuir reengajamentos dos seus usuários existentes, que visualizam seu anúncio, mas não clicam nele.

        * **Janela de lookback de reengajamento por view-through:** Defina o período máximo, após uma visualização, dentro do qual a abertura de um app pode ser atribuída à visualização como um reengajamento.

        <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Saiba mais sobre as janelas de lookback</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="reengagement-window"></span>
        Janela de reengajamento
      </td>
      <td>
        Defina a janela de tempo, durante a qual os eventos do aplicativo são atribuídos principalmente à conversão de reengajamento. <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#setup-reengagement-window">Saiba mais</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        Ignorar usuários ativos para retargeting
      </td>
      <td>
        Defina um período de inatividade para evitar o registro de conversões de retargeting para usuários ativos dentro do período especificado. Veja mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window">período de inatividade de retargeting</Anchor>.

        Para <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor>:

        1. Na aba Integração, ative a **atribuição de reengajamento**.
        2. Ative a opção **Ignorar usuários ativos para retargeting**.
        3. Defina a **janela de inatividade**.

        **Para não SRNs:**

        1. Na aba do link de atribuição, ative **configurações de retargeting**.
        2. Ative a opção **Ignorar usuários ativos para retargeting**.
        3. Defina a **janela de inatividade**.
      </td>
    </tr>
    <tr>
      <td><span id="e-cross-platform-attribution"></span>
        Atribuição cross-platform
      </td>
      <td>
        Quando a **prioridade de atribuição igual** está ativada, as impressões entre plataformas durante o período de tempo selecionado têm prioridade igual para atribuição.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        Atribuição de preload
      </td>
      <td>
        Quando a **atribuição de preload** está ativada, as instalações são atribuídas a <Anchor target="_blank" href="/marketers/pt/docs/measure-preload-campaigns-with-google-play-install">campanhas de preload</Anchor>. Defina a **janela de lookback de preload** para determinar quanto tempo após a ativação do dispositivo uma instalação de preload pode ser atribuída ao parceiro.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        Prioridade de atribuição igual
      </td>
      <td>
        Quando a **prioridade de atribuição igual para preload** está ativada, o engajamento durante a janela de lookback selecionada tem a mesma <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">prioridade de atribuição</Anchor> dos cliques determinísticos.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        Compartilhamento avançado de dados
      </td>
      <td>
        Quando **Compartilhamento avançado de dados** está ativado, dados adicionais são compartilhados com o parceiro por meio do link de atribuição.  
        **Atenção:** essa opção de compartilhamento é diferente do <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-aggregate-event-measurement-aem-for-ios#compartilhamento-de-dados-da-aem">compartilhamento de dados do AEM Advanced do Meta ads</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="default-postbacks"></span>
        Postbacks padrão
      </td>
      <td>
        Quando a integração de parceiros está ativada, são enviados postbacks padrão aos parceiros sobre as ações do usuário que ocorrem antes da abertura do aplicativo, como instalações, instalações rejeitadas e reengajamentos.

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **Observação:**
        >
        > * Eventos rejeitados são eventos in-app bloqueados pelo <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor> ou eventos que não estão em conformidade com a validação de destino. No caso de eventos rejeitados, confirme com o parceiro se a integração de eventos de rejeição com a AppsFlyer foi ativada.
        > * Parceiros podem receber postbacks padrão para instalações e reengajamentos. Em alguns casos, eles também podem receber postbacks de eventos in-app.

        **Para configurar postbacks padrão para o parceiro**, defina a origem de usuários para enviar os postbacks:

        * **Somente esse parceiro:** Envie postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que executou o evento veio deste parceiro.  
          **Atenção:** nos seguintes casos, os postbacks padrão são sempre definidos como **somente esse parceiro**:
          * Instalações rejeitadas
          * Agências (com [permissões](/docs/set-up-an-integrated-partner#permissões-da-agência))
        * **Todas as fontes de mídia, incluindo orgânicas:** Enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos - ou seja, o usuário que o executou veio de qualquer fonte de mídia.
        * **Desativado**: Não envie os postbacks padrão para esse parceiro.
      </td>
    </tr>
    <tr>
      <td><span id="g-in-app-event-postback-configuration"></span>
        <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Postbacks de eventos in-app</Anchor>
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#mapeamento-de-eventos">Mapeie</Anchor> os eventos da AppsFlyer com os eventos do parceiro por meio de postbacks. Se o envio de postback estiver ativado, isso inclui eventos in-app rejeitados (eventos bloqueados pelo Protect360 ou eventos considerados não compatíveis com as regras de validação de destino).

        **Para configurar postbacks de eventos in-app:**

        1. Defina o **Partner ID** (se necessário).
        2. Ative **postback de eventos in-app.**
        3. Defina a **janela de postback de eventos in-app**, se necessário (leia mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração da janela de postback de eventos in-app</Anchor>).
        4. Clique em **Adicionar evento** para adicionar um SDK ou evento S2S à lista.
        5. Complete os parâmetros necessários de acordo com o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">método de mapeamento</Anchor>.
        6. [Opcional] Clique em <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">configurar condições</Anchor> para o envio de certos eventos in-app para o parceiro.

        | Nome do parâmetro | Descrição |
        | --- | --- |
        | <span id="appsflyer-event"></span>**Evento da AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos S2S.  <br />**Dica**: Não consegue encontrar o evento que procura?<br /><br />* Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.<br />* Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>. |
        | <span id="mapped-to-partner-event"></span>**mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">As configurações de mapeamento possíveis</Anchor> são:<br /><br />* **Campo de texto:** obtenha o ID do evento correspondente no parceiro.<br />* **Caixa suspensa:** Selecione o evento predefinido mais adequado.<br />* **Sem alterações**: envie os eventos como eles estiverem, sem mapear o nome do evento. |
        | <span id="for-users-from"></span>**para usuários de** | Selecione a opção de envio para o evento:<br /><br />* **Somente esse parceiro:** Envie postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que executou o evento veio deste parceiro.<br />* **Todas as fontes de mídia, incluindo orgânicas:** Envie postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos, ou seja, quando o usuário que os realizou tiver vindo de qualquer fonte de mídia. |
        | <span id="including"></span>**incluindo** | Selecione <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">quais dados do evento</Anchor> você deseja compartilhar com o parceiro no postback:<br /><br />* **Sem valores e sem receita**: Envie apenas o evento em si, sem qualquer parâmetro (valores ou receita).<br />* **Com valores e sem receita**: Envie todos os parâmetros, com **exceção** do valor da receita.<br />* **Valores e receita**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento). |

         Observações:

        * Os eventos mapeados na aba Integração para um parceiro específico são aplicáveis para postbacks padrão e <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN</Anchor>.
        * Os postbacks são enviados aos parceiros em tempo real.
        * O nome do evento na AppsFlyer pode ser selecionado ou digitado.  
          Os valores digitados podem conter espaços sublinhados (sublinhados) antes ou depois do nome do evento. Utilize espaços sublinhados apenas se o nome do evento enviado pela AppsFlyer tiver os mesmos espaços sublinhados.
        * **Importante:** Os nomes dos eventos são sensíveis a maiúsculas e minúsculas. Para evitar discrepâncias, certifique-se de usar o nome de evento correto para todas as fontes de mídia e versões do aplicativo.
        * Se a seção **Postback de eventos in-app** não existir na aba **Integração**, significa que o parceiro ainda não configurou o registro de eventos in-app com a AppsFlyer em sua configuração preliminar. O parceiro pode entrar em contato com a AppsFlyer usando o <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget partner assistant</Anchor> para concluir a integração.
        * Para evitar que os anunciantes compartilhem muitas informações com plataformas de terceiros sem querer, removemos a opção **Enviar todos os eventos (exclui desinstalações, sessões e af\_ad\_revenue)** para as plataformas externas desde de março de 2019. As plataformas externa configuradas antes dessa data mantêm essa opção de configuração.

        Leitura relacionada

        * Configuração de <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>
        * Configuração de <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks">postbacks de receita de anúncios</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        Salve a integração
      </td>
      <td>
        Clique em **Salvar integração** após fazer as mudanças.
      </td>
    </tr>
    <tr>
      <td><span id="i-connect-more-apps-optional"></span>
        Conectar mais aplicativos (opcional)
      </td>
      <td>
        Após salvar a integração, enquanto permanece na página de configuração, você pode integrar mais aplicativos com o parceiro.

        1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
        2. Selecione um aplicativo diferente na lista suspensa.
        3. Repita as etapas de integração para o aplicativo selecionado.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Gere e salve links de atribuição para o uso de ad networks de cliques (não SRN) e envie o link de atribuição ao parceiro para atribuir determinadas campanhas, conjuntos de anúncios ou anúncios únicos.

**Atenção:** SRNs não implementam links de atribuição gerados pelos anunciantes, portanto, essa aba não é relevante para as campanhas de SRN.

**Para gerar um link de atribuição**:

1. Selecione **usar um link de plataforma única** ou **usar OneLink**.

   Selecione **usar um link de plataforma única** no caso de uma das seguintes situações:

   * Você planeja usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">esquemas de URI</Anchor> para abrir o aplicativo.
   * Você não precisa usar um deep link com a URL.

   Selecione **Usar o OneLink** no caso de uma das seguintes situações:

   * Você quer um único link tanto para aplicativos Android quanto para iOS.
   * Você quer usar App Links do Android ou Universal Links do iOS para abrir o aplicativo.
   * Você quer recursos de deep linking.

   **Atenção:** selecionar OneLink altera a gravação de links de clique do aplicativo específico para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.
2. Se você selecionou **Usar OneLink**:
   1. Selecione qual template do OneLink você deseja usar para abrir o aplicativo (e potencialmente o deep link).
   2. [Opcional] Insira o **valor do deep link**.
   3. [Opcional] Insira o **valor adicional do deep link**.
3. Adicione parâmetros para <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-específicos-para-android">Android</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-específicos-do-ios">iOS</Anchor>, conforme necessário.
4. [Opcional] Selecione parâmetros de atribuição adicionais.

<div id="attribution-link-parameters" />

#### Parâmetros do link de atribuição

[![attribution-link-parameters-en_us.png](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)

Adicionar parâmetros ao link de atribuição permite que você faça análises detalhadas. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os e incluindo seus novos valores aqui. Ao salvar o link de atribuição, todos os parâmetros configurados nesta aba são salvos.

Selecione quais parâmetros você deseja adicionar ao link de atribuição.

<div id="attribution-link-parameters-1" />

#### Parâmetros do link de atribuição

| Nome | Descrição | Parâmetro do link de atribuição |
| --- | --- | --- |
| Campanha | **Parâmetro necessário.**  <br />Compare diferentes campanhas em execução com a fonte de mídia. | C |
| Conjunto de anúncios | Compare diferentes conjuntos de anúncios em campanhas específicas da fonte de mídia. | af\_adset |
| Nome do anúncio | Compare diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da fonte de mídia. | af\_ad |
| Site ID e Sub Site ID | **Parâmetro necessário.**<br /><br />Defina o site ID para atribuir instalações a publishers específicos.<br /><br />O site ID deve ser enviado para a AppsFlyer no link de atribuição, pois ele:<ul><li>Proporciona clareza e transparência sobre o publisher.</li><li>É usado pela AppsFlyer para identificar e eliminar publishers fraudulentos e outros clusters de tráfego.</li></ul>Atenção: a ausência de site ID não afeta a atribuição. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#site-id-parameter">parâmetro de site ID</Anchor><br /><br />Se houver muitos publishers, aconselhamos que você limite o número de site IDs usados e use o parâmetro de subsite ID para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">ultrapassar as limitações de site ID</Anchor>. | af\_siteid e af\_sub\_siteid |
| Parâmetros do assinante | Use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

Você pode adicionar outros parâmetros ao link de atribuição digitando-o em uma nova caixa de parâmetros. Você pode usar todos os <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">parâmetros de URL disponíveis da AppsFlyer.</Anchor> Observe que apenas o esquema de URI e os parâmetros do OneLink são codificados no link de atribuição.

<div id="retargeting-settings" />

#### Configurações de retargeting

**Quando o retargeting está ativado**: A AppsFlyer reconhece um link como de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de aquisição de usuário, ao adicionar `&is_retargeting=true` ao link de atribuição.  
**Parâmetro do link de atribuição:** is\_retargeting

Para usar o seu link para retargeting:

1. Ative as **configurações de retargeting**.
2. [Opcional] Insira um esquema de URI se quiser que um esquema de URI abra o aplicativo.  
   **Atenção:**
   * Os esquemas de URI são recomendados como um método alternativo para abrir o aplicativo se os Universal Links e App Links falharem.
   * Se você adicionar um esquema de URI aqui, ele substituirá quaisquer outros esquemas de URI que já estiverem nas configurações do template do OneLink.
   * O esquema URI é adicionado ao link através do parâmetro af\_dp.
3. [Opcional] Ative **Ignorar usuários ativos para retargeting**.
4. Defina a janela inativa para determinar quais usuários são considerados ativos e inativos.
5. Configure a janela de reengajamento para determinar o período após o reengajamento, onde os eventos in-app do usuário são atribuídos ao canal de mídia de retargeting.
   * Você pode definir o valor em dias (1 a 90), horas (até 23) ou até mesmo vitalício.
   * A janela de reengajamento é adicionada ao link no parâmetro af\_reengagement\_window.

<div id="click-through-attribution" />

#### Atribuição de click-through

Use a configuração para definir o **tempo máximo do clique à instalação**. Somente instalações (primeiras inicializações) que ocorrem dentro da janela de lookback são atribuídas.

Intervalo permitido: 1-23 horas ou 1-30 dias.

**Parâmetro do link de atribuição:** af\_click\_lookback

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques</Anchor>.

**Clique no link de atribuição**

[![click-through-attribution-link_en-us.png](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)

Esse é o link de atribuição que contém todas as informações de configuração definidas para ele. Você pode salvar o link para futuras referências clicando em **Salvar link de atribuição**.

**Para copiar o link de atribuição de cliques:**

1. Clique em **Salvar link de atribuição.**
2. Copie o link gerado.

Envie o link para o parceiro para ser ativado quando seus leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

#### Janela de lookback de atribuição de view-through

Defina o **tempo máximo entre a impressão e a instalação**. Somente instalações (primeiras inicializações) que acontecerem durante essa janela de lookback, após uma impressão de anúncio, serão atribuídas ao parceiro, desde que não haja outros clique em anúncio relevante.

Você pode personalizar esse valor para 1-24 horas.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição de view-through</Anchor>.

**Link de atribuição para impressões**

[![impressions-attribution-link_en-us.png](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)

O link de atribuição para impressões contém dados semelhantes aos do link de registo de cliques, com exceção da diferente janela de retroatividade. Você pode salvar o link para futuras referências clicando em **Salvar link de atribuição**.

Clique em Salvar link de atribuição e copie o link gerado.

**Para copiar o link de atribuição de impressões:**

1. Clique em **Salvar link de atribuição.**
2. Copie o link gerado.

Envie-o ao parceiro para ser ativado quando um anúncio correspondente for visto, normalmente durante um segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

* Os dados de custo são reportados pelos seus parceiros integrados com base nos cliques ou através da Cost API.
* A prática recomendada é implementar a API de custo (requer assinatura do ROI360).
* A Cost API inclui relatórios de cliques e impressões. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.

<div id="note-2" />

> 📘 **Observação:**
>
> Se um anunciante usar uma agência para gerir as suas campanhas, a agência, e não o anunciante, deve integrar-se com os parceiros relevantes. Caso contrário, se tanto o anunciante como a agência se integrarem num parceiro usando as mesmas credenciais para a mesma app, os dados de custo são duplicados.

<div id="enabling-cost-data-by-api" />

#### Ativação de dados de custo por API

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<div id="cost-data-sync-status" />

#### Status de sincronização dos dados de custo

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

Se você atua como um publisher exibindo anúncios no seu aplicativo, a função de receita de anúncios permite atribuir a receita de anúncios à fonte de mídia que trouxe o usuário. <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">Sobre a atribuição de receitas de anúncios.</Anchor>

<div id="enable-ad-revenue-attribution" />

#### Ativar atribuição da receita de anúncios

1. Verifique para ver para qual método, <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">agregação ou atribuição a nível do usuário</Anchor>, o parceiro oferece suporte.
2. Siga o método apropriado no <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#implementação">guia de integração de receitas de anúncios.</Anchor>

<div id="ad-revenue-api-status-messages" />

#### Mensagens de status da Ad Revenue API

| Estado | Observações/ação necessária |
| --- | --- |
| Ativo | A conexão está em ativa e extraindo dados. |
| Não foram encontrados dados para extrair. | A conexão foi bem sucedida. O parceiro não tinha nenhum dado relacionado a esse aplicativo. |
| A API do parceiro não está respondendo. Entre em contato com o suporte da AppsFlyer. | O servidor do parceiro não está respondendo à AppsFlyer. |
| Credenciais inválidas. Introduza as credenciais atualizadas. |  |
| Algo deu errado. Entre em contato com o suporte da AppsFlyer. | Há um problema técnico. |
| Os dados do parceiro ainda não estão disponíveis. Se o problema persistir, entre em contato com o suporte da AppsFlyer. |  |
| Os dados estão sendo processados e estarão disponíveis em breve. | No momento estamos processando os dados recebidos do parceiro. Os dados estarão disponíveis nos dashboards e relatórios. |
| Os dados nunca foram extraídos com sucesso | Se esse status persistir por mais uma hora, entre em contato com o suporte da AppsFlyer. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Conceda permissões específicas para que as networks e agências acessem seus dados e realizarem várias ações.

* Você não precisa que a integração com o parceiro esteja ativa para conceder permissões.
* **Rede de anúncios configurada por uma agência:** quando a configuração do parceiro é executada por uma agência, o anunciante não consegue visualizar o status de ativação da ad network ou as permissões concedidas.
* Se a sua associação com o parceiro for unicamente como agência, use as **Permissões da agência** em vez das **Permissões da ad network**. Ao ativar as permissões de agência, você autoriza que a agência controle as permissões da ad network. Para obter mais informações, veja <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding#o-que-significa-obter-permissão-de-um-profissional-de-marketing">O que significa obter permissão de um profissional de marketing</Anchor>.
* As permissões são atribuídas ao aplicativo atualmente selecionado.

<div id="ad-network-permissions" />

#### Permissões da ad network

Ao ativar as **permissões da ad network**, você permite que a ad network acesse o seu dashboard, possibilitando a concessão de permissões adicionais, conforme detalhado na tabela abaixo.

<div id="note-3" />

> 📘 **Observação:**
>
> Qualquer permissão de acesso está limitada aos dados pertencentes à ad network.

**Para conceder permissões a uma ad network e aos membros da sua equipe:**

1. Ative as **permissões da ad network**.

   * Seu aplicativo aparece no dashboard da ad network.
   * O administrador da ad network tem permissão para <Anchor target="_blank" href="/marketers/pt/docs/manage-data-access-permissions">acessar dados básicos sobre o aplicativo.</Anchor>

   **Atenção:** Os membros da equipe da ad network são gerenciados diretamente pela ad network. Se você deseja que um membro específico da equipe tenha acesso, entre em contato com sua ad network. <Anchor target="_blank" href="/partners/pt/docs/user-management-for-ad-networks#criando-um-usuário">Saiba mais</Anchor>
2. Selecione permissões adicionais para conceder à ad network:

| **Permissão** | **Recurso concedido** |
| --- | --- |
| <span id="configure-integration"></span>Configurar integração | A ad network pode alterar parâmetros na aba de integração, exceto ao configurar postbacks de eventos in-app. |
| <span id="configure-inapp-event-postbacks"></span>Configurar postbacks de eventos in-app | A ad network pode /span>configurar postbacks de eventos in-app Isso significa que ela pode criar, configurar (mapear) e alterar as configurações de postback. Isso significa que ela pode criar, configurar (mapear) e alterar as configurações de postback.<br /><br />**Atenção**! Quando esse recurso e a permissão de **configurar integração** estão ativados, o parceiro tem acesso a todos os eventos. Isso inclui tráfego orgânico e não-orgânico de todos os canais de mídia. |
| <span id="access-retention-report"></span>Acessar os relatórios de retenção e cohort | A ad network pode acessar apenas os dados de retenção/coorte criados pelos usuários trazidos pela ad network. |
| <span id="access-aggregate-loyal-users-data"></span>Acesse dados agregados de usuários fidelizados | Clique em <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">**Ativar parceiro.**</Anchor> |
| <span id="access-aggregate-conversions-data"></span>Acessar dados agregados de conversões | A ad network pode acessar seus relatórios de métricas de eventos de conversão agregados. Isso inclui instalações, reengajamentos, reinstalações e reatribuições. Exemplo: <Anchor target="_blank" href="/partners/pt/docs/aggregated-campaign-performance-report-for-ad-networks">Relatório agregado de performance de campanhas para ad networks.</Anchor> |
| <span id="access-aggregate-inapp-events-data"></span>Acessar dados agregados de eventos in-app | A ad network pode:<ul><li>Acessar relatórios de dados agregados de eventos in-app. O acesso inclui todos os dados de eventos in-app do aplicativo selecionado, incluindo os do Protect360. Isso significa que eles podem acessar eventos além daqueles definidos na configuração de postback.</li><li>Acessar relatórios agregados de dados de monetização de anúncios, que podem incluir eventos de monetização de anúncios de outros canais de mídia.</li></ul> |
| <span id="view-validation-rules"></span>Ver regras de validação | A ad network pode visualizar informações da <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">regra de validação</Anchor>. |
| <span id="access-aggregate-revenue-data"></span>Acessar dados agregados de receita | **A ad network pode acessar** relatórios agregados de receitas de anúncios e in-app atribuídos aos usuários que eles trouxeram. **Atenção:** Essa permissão não identifica diretamente o parceiro de receita de anúncios. No entanto, se você definiu o nome do evento de monetização com o nome do parceiro, você pode revelar, sem querer, a identidade da rede de monetização. |
| <span id="use-ad-spend-ingestion"></span>Use a ingestão de gastos com anúncios | A ad network pode:<ul><li><Anchor target="_blank" href="/partners/pt/docs/ad-revenue-signals-for-ua-ad-networks">A ad network pode</Anchor> <Anchor target="_blank" href="/partners/pt/docs/ad-revenue-signals-for-ua-ad-networks">acessar seus dados de receita de anúncios para otimizar a aquisição de usuários.<br />**Atenção**: essa permissão está disponível somente para apps com uma assinatura do</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.</li><li>Envie os arquivos de gastos de anúncios para processamento.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Acessar o dashboard do Protect360 e dados brutos | A ad network pode:<ul><li>Acessar o dashboard do Protect360 (incluindo <Anchor target="_blank" href="/marketers/pt/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>).</li><li>Acessar o Protect360, Regras de Validação e dados brutos, se fizerem parte do plano de assinatura/span> O ProtectLITE não inclui acesso a dados brutos. ProtectLITE não disponibiliza acesso aos dados brutos.</li></ul>**Atenção**: quando você tem uma assinatura do <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor>, a ad network pode ver o dashboard completo. Sem uma assinatura do Protect360, eles podem ver o dashboard lite. |
| <span id="access-ad-revenue-raw-data"></span>Acesse os dados brutos de receita de anúncios | Acessar a <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">janela Ingestão de Gastos com Anúncios. Essa janela apresenta apenas os aplicativos para os quais eles têm permissão de acesso.   <br />**Observação:** esta permissão está disponível apenas para aplicativos com uma</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> assinatura. |

<div id="agency-permissions" />

#### Permissões da agência

Leia tudo sobre <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding#o-que-significa-obter-permissão-de-um-profissional-de-marketing">o que as agências podem fazer</Anchor> quando recebem permissões.

<div id="important-1" />

> 🚧 **Importante!**
>
> Ao trabalhar com agências, desativar um parceiro integrado não desativa automaticamente certos recursos de atribuição para as agências conectadas a esse parceiro:
>
> Para desativar esses recursos para agências, o anunciante deve desativar manualmente as seguintes configurações antes de desativar o parceiro:
>
> 1. Atribuição de instalação de view-through
> 2. Prioridade de atribuição igual entre plataformas
>
> Depois de desativar essas opções, o anunciante deverá seguir com a desativação do parceiro.
>
> **Atenção:** Se o anunciante desativar o parceiro sem desativar essas configurações primeiro, as agências poderão continuar usando os recursos de atribuição.

**Cuidado:** as instalações da agência que ocorrem enquanto o controle está desativado não são atribuídas à agência e não aparecem no dashboard e nos dados da agência. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#permissões-da-agência">ativação da agência</Anchor>.

**Para conceder permissões a uma agência:**

1. Ative as **Permissões da agência**.
2. Selecione as permissões que deseja conceder à agência:

| **Permissão** | **Capacidade concedida** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Mudar a configuração de Privacidade Avançada | A agência pode alterar a configuração <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">de compartilhamento de dados de privacidade avançada</Anchor> de uma ad network.   <br />**Atenção: Essa permissão não se aplica ao TikTok for Business e Snapchat. Para estas integrações, a configuração de Privacidade Avançada fica esmaecida, refletindo a configuração do anunciante.** |
| <span id="access-retention-and-cohort-reports"></span>Acessar aos relatórios de retenção e cohort | A agência pode acessar apenas os dados de retenção/coorte criados pelos usuários trazidos pela agência. |
| <span id="access-aggregate-organic-data"></span>Acesse dados orgânicos agregados | A agência pode acessar dados orgânicos agregados |
| <span id="view-validation-rules::6872643b"></span>Ver regras de validação | A agência pode consultar os detalhes das regras de validação. |
| <span id="add-validation-rules"></span>Adicionar regras de validação | **A agência pode adicionar** e editar regras de validação. Disponível quando **Visualizar regras de validação** está ativado.   <br />**Nota**: As agências não podem editar regras criadas pelos anunciantes. |
| <span id="access-rawdata-reports"></span>Acessar relatórios de dados brutos | A agência pode acessar relatórios de dados brutos para o tráfego atribuído a ela. Os anunciantes não podem limitar os eventos que uma agência pode ver nos relatórios. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Acessar o dashboard do Protect360 e dados brutos | A agência pode:<ul><li>acessar o dashboard agregado do Protect360</li><li>acessar o Protect360, regras de validação e dados brutos se fizerem parte do plano de assinatura</li></ul>**Atenção:** Para anunciantes que trabalham com ad networks através de uma agência - para que tanto a ad network como a agência tenham acesso aos dados, o anunciante deve integrar tanto a agência quanto a ad network na AppsFlyer e conceder-lhes permissão para acessar os dados. Se apenas a agência for integrada e tiver permissão, a ad network não terá acesso aos dados. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Configurar postbacks de eventos in-app | A agência pode configurar postbacks de eventos in-app de eventos específicos que você selecionar:<ul><li>**Adicionar evento:** no menu suspenso, selecione os eventos que você deseja permitir que a agência acesse.</li></ul>As opções a seguir se aplicam aos eventos selecionados:<ul><li>**Enviar receita dos eventos:** quando ativado, a agência pode configurar o envio de eventos incluindo seu valor monetário.</li><li>**Opção de envio:**<ul><li>**Somente esse parceiro:** quando selecionado, a agência pode configurar o envio de postbacks apenas para eventos atribuídos ao seu próprio tráfego trazido</li><li>**Todas as fontes de mídia, incluindo orgânicas:** Quando selecionada, a agência pode configurar o envio de postbacks para eventos atribuídos a todas as outras fontes de mídia, agências e usuários orgânicos.</li></ul></li></ul> |

Saiba mais sobre <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts#acesso-da-agência-aos-dados-de-marketing">trabalhar com agências</Anchor>.

</Accordion>

<div id="test-the-integration" />

## Teste a integração

Após concluir a integração do parceiro e antes de iniciar campanhas com o novo parceiro, é essencial testar a integração. É mais provável que ocorram erros durante a configuração inicial. Testar com antecedência evita o risco de gastar recursos consideráveis, apenas para descobrir que seus dados de atribuição estão ausentes ou incorretos.

<div id="note-4" />

> 📘 **Observação:**
>
> Antes de testar a integração, certifique-se de primeiro <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers">testar o aplicativo para integração básica do SDK,</Anchor> incluindo as instalações orgânicas e não orgânicas.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Teste o link de atribuição para não-SRNs">

Ad networks regulares, que consistem em 99,5% de todas as ad networks integradas, usam links de atribuição da AppsFlyer. De modo semelhante, a atribuição de mídia própria é realizada usando os <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">links OneLink</Anchor> da AppsFlyer.

Como a atribuição correta depende dos parâmetros nos links de atribuição, teste esses links antes de começar a executar uma campanha com uma ad network não SRN ou um link de atribuição personalizado.

**Para testar os links de atribuição:**

1. Crie um [link de atribuição](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Envie o novo link de atribuição para o seu dispositivo de teste <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registrado</Anchor> (por e-mail ou QR code).
3. Clique no link e certifique-se de que você é redirecionado para a app store.
4. Instale o aplicativo.
5. Inicie o aplicativo.
6. Verifique se a instalação aparece no dashboard da AppsFlyer, embaixo do nome da fonte de mídia do parceiro. Aguarde até 30 minutos para que a instalação apareça no dashboard.
7. Aprofunde a análise até ao nível da campanha (selecionando o parceiro no **filtro de origem de mídia** no topo da página de visão geral) para confirmar se a instalação aparece com o nome correto da campanha.
8. Se necessário, continue a detalhar e verifique também os níveis de conjunto de anúncios e anúncios individuais.

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Teste a integração com SRN">

SRNs, como Meta Ads, Apple Ads e Google Ads, não dependem de links de atribuição externos para fins de atribuição. Ao invés disso, SRNs recebem consultas da AppsFlyer, fazem a atribuição por si próprios e retornam a resposta. Portanto, não é viável testar a integração separadamente do sistema da rede, ao contrário do que acontece com ad networks tradicionais. Você deve testar separadamente a integração com cada SRN com a qual você trabalha.

**Para testar a integração com SRN**[:](/docs/set-up-an-integrated-partner)

1. Fa;ca a configuração completa da SRN na AppsFlyer de acordo com o <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">guia específico de configuração da SRN</Anchor>.
2. Execute uma nova campanha de baixo orçamento com o parceiro de SRN.
3. Quando o dashboard do parceiro exibe novas instalações, verifique se elas aparecem no dashboard da AppsFlyer com o nome da fonte de mídia do parceiro.
4. No dashboard de Visão geral, analise detalhadamente até o nível da campanha e selecione o parceiro no **Filtro de fonte de mídia** para verificar se a instalação aparece sob o nome correto da campanha. Aguarde até 30 minutos para que a instalação apareça no dashboard.
5. Se necessário, continue a análise detalhada para verificar os níveis de conjunto de anúncios e de anúncio único.

Se tudo estiver certo, você pode começar a executar novas campanhas de orçamento elevado com o parceiro. Testar a integração uma vez por parceiro SRN é suficiente. Ou seja, não é necessário testar por campanha.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Teste os dados brutos">

Se seu plano de assinatura com a AppsFlyer inclui acesso a dados brutos, eles devem ser testados.

**Para testar dados brutos**:

1. Depois de executar o teste mencionado anteriormente, acesse **Relatórios** > <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">**Exportar Dados**</Anchor>.
2. Selecione a fonte de mídia testada.
3. Aguarde até 15 minutos a partir da instalação e, em seguida, faça o download do relatório de instalações.
4. Verifique se o registro de instalações do parceiro existe e inclui parâmetros como fonte de mídia, nome da campanha, tipo e hora do toque, device ID (caso aplicável), nome da agência (chamada de "Parceiro" no relatório) e outros.

<div id="important-2" />

> 🚧 **Importante!**
>
> Algumas ad networks requerem ações especiais para permitir a coleta de dados brutos a nível do usuário.
>
> Se você vir uma nova instalação no dashboard, mas não a vir nos dados brutos, consulte o guia específico da Central de Ajuda da ad network, por exemplo - <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">Twitter</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H80XGTBQ6MAK3VG0X6QMAYMP=vis%C3%A3o-geral 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=convide-novos-parceiros-para-a-appsflyer 01H80XGTBQRJ78XCGNZBTJVYEQ=convide-novos-parceiros-para-a-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=observa%C3%A7%C3%A3o 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=abas-de-configura%C3%A7%C3%B5es-aplic%C3%A1veis-por-tipo-de-parceiro 01H80XGTBQPP74G38YNNYVXWP2=abas-de-configura%C3%A7%C3%B5es-aplic%C3%A1veis-por-tipo-de-parceiro set-up-a-partner-nonsrn=configurar-um-parceiro-n%C3%A3o-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=configurar-um-parceiro-n%C3%A3o-srn 01JDM949M75Q3BAG6M65DYMHZT=importante 01H80XGTBQZXZARZCM61CMG0K3=observa%C3%A7%C3%A3o-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=se%C3%A7%C3%B5es-de-integra%C3%A7%C3%A3o 01H80XGTBQ0531M2RS3DH7E4Z0=se%C3%A7%C3%B5es-de-integra%C3%A7%C3%A3o d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBQ4MPGGKSZW0D9GG9H=observa%C3%A7%C3%A3o-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o 01H80XGTBRPENCTCRK8PPYSCGX=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o attribution-link-parameters::3874dfb8=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o-1 01H80XGTBR8630SEV80K9RD6V9=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o-1 retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting 01H80XGTBRT57QMPRENYSS81Z3=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through 01H80XGTBREZTJ6B0Y08JCKN1E=atribui%C3%A7%C3%A3o-de-click-through viewthrough-attribution-lookback-window=janela-de-lookback-de-atribui%C3%A7%C3%A3o-de-view-through 01H80XGTBRXC1YYX4FW94NDR2Z=janela-de-lookback-de-atribui%C3%A7%C3%A3o-de-view-through 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=observa%C3%A7%C3%A3o-3 enabling-cost-data-by-api=ativa%C3%A7%C3%A3o-de-dados-de-custo-por-api 01H80XGTBRV6BHWS76HWHK933M=ativa%C3%A7%C3%A3o-de-dados-de-custo-por-api cost-data-sync-status=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo 01H80XGTBRPWREFYFXA0A6VD47=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=ativar-atribui%C3%A7%C3%A3o-da-receita-de-an%C3%BAncios 01H80XGTBRHE9PPRA9X46M4TGZ=ativar-atribui%C3%A7%C3%A3o-da-receita-de-an%C3%BAncios ad-revenue-api-status-messages=mensagens-de-status-da-ad-revenue-api 01H80XGTBRNT4K4ZNPKVV25ESJ=mensagens-de-status-da-ad-revenue-api 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network 01H80XGTBRS9BTT2F8F95BCE9Z=permiss%C3%B5es-da-ad-network h_01HGFD78GRX9P2G58W21QZN4X7=observa%C3%A7%C3%A3o-4 agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia 01H80XGTBRTVP407AAA77N090E=permiss%C3%B5es-da-ag%C3%AAncia h_01KC9MDDRPTB05PV6NCGZVFRMJ=importante-1 test-the-integration=teste-a-integra%C3%A7%C3%A3o 01H80XGTBSEWPHCPQF29XD6Y4W=teste-a-integra%C3%A7%C3%A3o 01H80XGTBSTHG2FC2M31F83RGK=observa%C3%A7%C3%A3o-5 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=importante-2" />
