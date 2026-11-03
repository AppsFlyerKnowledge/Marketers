---
title: Configurações do aplicativo
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-19T13:33:47Z'
  id: 211719806
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/211719806
---
> **At a glance:** saiba mais sobre as configurações que afetam a atribuição e a análise do aplicativo em todas as fontes de mídia.

## Configurações do aplicativo

**Acesso:**

* Um administrador (ou outros usuários com permissões apropriadas) pode **alterar** as configurações do aplicativo.
* Todos os usuários da conta com acesso a um aplicativo específico podem **visualizar** as configurações do aplicativo.

**Para alterar ou visualizar configurações do aplicativo:**

1. Na AppsFlyer, no menu lateral, selecione **Configurações**> **Configurações do aplicativo**. **Etapa 1**:
2. Veja as configurações e faça as alterações necessárias na página de Configurações do Aplicativo.
3. Clique em **Salvar configurações**.

> 📘 **Importante!**
>
> Você também pode alterar muitas dessas configurações para vários aplicativos ao mesmo tempo, em vez de fazer isso um por um. Procure o botão **Aplicar a aplicativos adicionais** ao lado de uma configuração alterada. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.

### Configurações gerais do aplicativo

<Table>
  <thead>
    <tr>
      <th>
        Configuração
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        Autenticação SDK: Dev key
      </td>
      <td>
        * A dev key autentica eventos enviados pelo aplicativo ou pelo S2S para a AppsFlyer.
        * Ela é exclusiva para cada conta da AppsFlyer e usada por todos os aplicativos da conta.
        * A chave está disponível na página Configurações do aplicativo para qualquer usuário da conta com acesso a esse aplicativo.
        * [Opcional] Uma chave de aplicativo individual pode ser atribuída em determinados cenários. Entre em contato com seu CSM para falar sobre isso.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        Privacidade Avançada Agregada (aplicativos do iOS)
      </td>
      <td>
        Quando ativados, os dados de atribuição a nível de usuário não estão disponíveis para os anunciantes. Postbacks e dados de eventos compartilhados com parceiros são agregados e anônimos (mais sobre a estrutura <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade avançada agregada</Anchor>).

        Quando desativados, os dados de atribuição a nível de usuário estão disponíveis para todos os parceiros como dados agregados e podem ser definidos para cada parceiro individualmente.

        Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        Analytics: Definir a metrica de usuários fieis
      </td>
      <td>
        * O gatilho para designar um usuário como um usuário fidelizado. A opção padrão definida quando você adiciona o aplicativo é: três inicializações de aplicativo.
        * Após atribuir os eventos in-app, você pode usar um evento in-app como o evento de gatilho.
          * [Padrão] 3 inicializações do aplicativo.
          * A definição de um usuário leal é um indicador da qualidade do usuário. Considere usar o <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> para combater fraudes.
          * Alterar essa configuração afeta os dados de maneira retroativa, o que significa que os dados de histórico de usuários fieis são recalculados.
        * Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="minimum-time-between-sessions"></span>
        Tempo mínimo entre as sessões
      </td>
      <td>
        Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        País da loja de aplicativos
      </td>
      <td>
        Define o país da loja de aplicativos em que o aplicativo está disponível. Essa definição afeta o aplicativo, conforme detalhado aqui.

        * **Como alterar o status do aplicativo de pendente para ativo**:
          * <Anchor target="_blank" href="/marketers/pt/docs/why-is-my-app-still-pending">Quando o aplicativo se torna ativo</Anchor>, a AppsFlyer verifica a loja usando a configuração do país para recuperar detalhes sobre o aplicativo, como seu ícone.
          * Se o aplicativo não for encontrado no país da loja definido, a AppsFlyer não poderá alterar o status do aplicativo de pendente para ativo.
        * O comportamento do redirecionamento é impactado pela definição, dependendo do cenário, conforme detalhado na tabela a seguir.

        | Tipo de usuário | Cenário de redirecionamento |
        | --- | --- |
        | <span id="mobile"></span>Mobile | Usuários geralmente clicam nos links de atribuição de outros aplicativos mobile. Ao clicar, o sistema operacional determina o país da loja de aplicativos para o qual os usuários são redirecionados:<br /><br />* **Android** redireciona com base no IP do usuário/localização.<br />* **iOS** redireciona para a loja de aplicativos associada à conta do iTunes ativa no dispositivo. |
        | <span id="mobile-and-web"></span>Mobile e web | Quando os usuários da web clicam nos links de atribuição, em **sites** (mobile e desktop), o redirecionamento inicial é para a store definida em países da app store.<br /><br />Na tentativa de instalação, o sistema operacional os redireciona para a loja do país, conforme descrito para dispositivos móveis na linha anterior. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | A partir do iOS 13, <Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPads exibem a versão desktop dos sites</Anchor> . Isso significa que o tipo de usuário (mobile ou web) não é relevante. Um clique em um link de atribuição vai para o site da área de trabalho e, depois disso, as regras de redirecionamento são as dos usuários da web. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        Localização: Fuso horário
      </td>
      <td>
        A configuração padrão do app é UTC. <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">Sobre o fuso horário do app.</Anchor>

        Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        Localização: Moeda
      </td>
      <td>
        * Define a moeda específica do aplicativo que é usada para as seguintes métricas:
          * Custo
          * Eventos/receita in-app
          * Receita de anúncios
        * A definição padrão do aplicativo é USD.
          * A alteração de moeda está disponível para aplicativos sem receitas ou custos.
          * Para aplicativos novos, a moeda é configurada quando o aplicativo é adicionado.
        * Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.

        #### Ferramentas de relatórios afetadas pela moeda do aplicativo

        | Ferramenta de relatório | Opções de moeda disponíveis |
        | --- | --- |
        | <span id="dashboards"></span>Painéis | Moeda específica do aplicativo |
        | <span id="export-data-page"></span>Página de Export data | Moeda específica do aplicativo |
        | <span id="push-api"></span>API de push | Moeda específica do aplicativo e USD disponíveis simultaneamente |
        | <span id="pull-api"></span>Extrair API | Dados agregados: Moeda específica do aplicativo<br /><br />Dados brutos: USD selecionável ou moeda específica do aplicativo |
        | <span id="master-api"></span>Master API | USD selecionável ou moeda específica do aplicativo |
        | <span id="data-locker"></span>Relatório do Data Locker | Apenas USD |
      </td>
    </tr>
  </tbody>
</Table>

### Configurações de atribuição

> 📘 **Importante!**
>
> As configurações nesta tabela se aplicam a apps móveis (iOS e Android). Algumas configurações podem não estar disponíveis ou podem funcionar de forma diferente para aplicativos web.

| Configuração | Descrição |
| --- | --- |
| <span id="reattribution-window"></span>Janela de reatribuição | A <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor> é um período que começa nos dados da primeira instalação, durante os quais as reinstalações não podem ser atribuídas como novas instalações.<ul><li>[Padrão] Três meses</li><li>Intervalo de valores: 1-24 meses</li></ul>Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Atribuição de view-through através de modelagem probabilística | <ul><li>Se desativado, ative a modelagem probabilística de view-through.</li><li>Após ativar a modelagem probabilística de view-through, você também deve ativar a atribuição de view-through na aba de integração da ad network.</li><li>Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Isso exigirá que o fingerprinting já esteja ativado. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>.</li></ul> |
| <span id="reengagement-attribution"></span>Atribuição de reengajamento | Leitura adicional: <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Guia de retargeting</Anchor><br /><br />**Para ativar a atribuição de reengajamento:**<ul><li>**Na AppsFlyer, no menu lateral, selecione** **Configurações** > **Configurações do app** e ative Atribuição de reengajamento.</li></ul>Além da configuração do aplicativo, você também deve <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#retargeting-settings">fazer configurações por parceiro</Anchor>.<br /><br />O <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#janelas-de-exclusão">**tempo mínimo entre a configuração de conversões de reengajamento**</Anchor> é usado para evitar o encerramento de uma janela de reengajamento existente antes de sua duração definida.<br /><br />Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. Quando isso for aplicado em massa, você também verá uma etapa de confirmação antes que a alteração entre em vigor — isso não se aplica quando você altera um aplicativo individualmente. |
| <span id="minimum-time-between-reengagement-conversions"></span>Intervalo mínimo entre conversões de reengajamento | Impede que uma janela de reengajamento existente termine antes do fim do período definido. Leitura adicional: <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#janelas-de-exclusão">Guia de atribuição de retargeting</Anchor>.<br /><br />Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |
| <span id="organic-search-seo-mobile-app-attribution"></span>Atribuição de reengajamento de app mobile por SEO (pesquisa orgânica) e AEO | Leitura adicional: <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribuição de pesquisa orgânica</Anchor><br /><br />**Para ativar a atribuição de SEO / AEO:**<ul><li>Na AppsFlyer, no menu lateral, selecione **Configurações** > **Configurações do aplicativo**, ative **Atribuição de reengajamento de app mobile por SEO (pesquisa orgânica) e AEO**</li></ul>Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |
| <span id="uninstall-measurement"></span>Mensuração de desinstalação | A <Anchor target="_blank" href="/marketers/pt/docs/measure-uninstalls">mensuração de desinstalação</Anchor> avalia dados que se referem a instalações que ocorrem quando a mensuração de desinstalação está ativada.<br /><br />Essa configuração está disponível apenas para aplicativos iOS e Android.<br /><br />**Para habilitar a mensuração de desinstalação:**<ol><li>Complete de acordo com o sistema operacional o seguinte:<ul><li>**iOS**: aplicativos que implementam o recurso de atribuição de desinstalação do iOS precisam fazer upload do certificado P12 aqui.</li><li>**Android**: os aplicativos exigem que uma chave de servidor FireBase/GCM seja definida aqui para atribuição de desinstalação do Android.</li></ul></li><li>Ative a **mensuração de desinstalação**.</li><li>Clique em **Salvar configurações**</li></ol>**Para interromper a mensuração de desinstalação:**<ol><li>Desative a **mensuração de desinstalação**.</li><li>Clique em **Salvar configurações**.</li></ol>Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |

### Configurações avançadas

| Configuração | Descrição |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Mascarar endereços IP | Quando ativado, <Anchor target="_blank" href="/marketers/pt/docs/apply-ip-masking-to-user-data">os endereços IP dos dispositivos do usuário final são mascarados</Anchor> em relatórios de dados brutos e em postbacks enviados aos parceiros do aplicativo selecionado.<br /><br />Você também pode alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Detecção de reinstalação usando armazenamento no dispositivo (somente iOS) | Detecte reinstalações sem depender de advertising IDs. Isto é feito armazenando a última data de instalação do aplicativo no armazenamento local seguro no dispositivo (no iOS, o Keychain). Determinar se uma instalação foi uma reinstalação ou uma nova instalação permite que você deduza reinstalações a partir de seus NOIs, tornando a análise de atribuição mais precisa. Observação: apenas a data da última instalação do aplicativo é armazenada no armazenamento local do dispositivo para essa finalidade — nenhum outro identificador do dispositivo (por exemplo, IDFA, IDFV) é armazenado.<br /><br />Em breve, haverá suporte para alterar essa configuração para vários aplicativos de uma só vez. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários aplicativos de uma só vez</Anchor>. |
| <span id="ios-103-redirect-fallback"></span>Redirecionamento de fallback para iOS 10.3 | [Obsoleto] Para iOS 10.3+. Simplificamos o fluxo para usuários do iOS e esse parâmetro não está mais em uso. <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">Redirecionamentos para iOS</Anchor>.<br /><br />Essa opção está disponível apenas para aplicativos do iOS. |
| <span id="change-app-name"></span>Alterar o nome do aplicativo | <ul><li>O nome do aplicativo, que é exibido no dashboard e nos relatórios de dados. Isso é útil se você tiver versões diferentes do mesmo aplicativo, por exemplo, por motivos de distribuição regional.</li><li>Essa mudança impacta a exibição do aplicativo. O App ID, usado para identificar o aplicativo em várias APIs da AppsFlyer, **permanece inalterado**.</li><li>Os nomes são limitados a 50 caracteres.</li></ul> |
| <span id="outofstore-app-url"></span>URL de aplicativos fora da loja | <ul><li>Defina o URL de download que será usado como destino para o redirecionamento padrão dos links de atribuição associados ao app.</li><li>Campo é obrigatório para aplicativos Android identificados como fora da loja.</li><li>Uma vez configurada, a URL será aplicada como destino predefinido para redirecionamento dentro de cerca de uma hora.</li></ul> |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Guia de atribuição para retargeting</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Atribuição de pesquisa orgânica</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/apply-settings-to-multiple-apps-at-once">Aplicar configurações a vários apps de uma só vez</Anchor>

<div data-zendesk-anchors="app-settings=configura%C3%A7%C3%B5es-do-aplicativo 01ECHQME56X51MDW9TMA6DBNCK=configura%C3%A7%C3%B5es-do-aplicativo h_01M22QK1N5EMMPVZ7ZJ55Z3YFF=importante general-app-settings=configura%C3%A7%C3%B5es-gerais-do-aplicativo h_01HAVS8CVPQKSDKCEM3YHHJ99Y=configura%C3%A7%C3%B5es-gerais-do-aplicativo reporting-tools-impacted-by-app-currency=ferramentas-de-relat%C3%B3rios-afetadas-pela-moeda-do-aplicativo h_01HAVS8CVQESWAQXKDW5SNVHCJ=ferramentas-de-relat%C3%B3rios-afetadas-pela-moeda-do-aplicativo attribution-settings=configura%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o h_01HAVS8CVQN1YYTT7S49VGB3J0=configura%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o h_01M1XPKX6DECQPK4R9X6Y4KMBP=importante-1 advanced-settings=configura%C3%A7%C3%B5es-avan%C3%A7adas h_01HAVS8CVQTKXVXSMT5KNYZ3T4=configura%C3%A7%C3%B5es-avan%C3%A7adas h_01HDPCC9465DR4A3CCXYQC2M56=veja-tamb%C3%A9m" />
