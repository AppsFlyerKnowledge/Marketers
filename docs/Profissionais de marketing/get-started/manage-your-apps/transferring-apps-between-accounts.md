---
title: Transferência de aplicativos entre contas
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-09-23T00:07:55Z'
  id: 360001336005
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/360001336005
---
> **At a glance:** transfira aplicativos entre contas da AppsFlyer, seguindo as etapas descritas neste artigo (esse processo pode ser feito apenas por administradores).

![Animação do processo de transferência de aplicativo mostrando as etapas do assistente de transferência](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

## Transferência de aplicativos entre contas

Para transferir um aplicativo entre contas da AppsFlyer, os proprietários de ambas as contas (conforme representados por seus administradores de conta da AppsFlyer) devem preencher os pré-requisitos de transferência necessários e concordar com a transferência.

### Pré-requisitos

* Verifique se você tem os e-mails da conta do remetente e do destinatário (admin)
* Ambas as contas devem estar ativas. Contas suspensas não podem enviar ou receber aplicativos.
* Nenhuma das contas pode ter faturas pendentes
* A transferência de aplicativos entre contas só pode ser feita por um <Anchor target="_blank" href="/marketers/pt/docs/user-management#proprietário-da-conta">proprietário da conta</Anchor>. Ela não pode ser realizada por uma função de administrador.
* A transferência do aplicativo deve ser para uma conta com o plano Growth ou Enterprise. <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">Saiba mais</Anchor>

### Processo de transferência de aplicativos

Veja a seguir uma visão geral do processo de transferência de aplicativos:

1. O remetente solicita que a AppsFlyer transfira os aplicativos selecionados e insira o endereço de e-mail da conta do destinatário.
2. O destinatário é notificado e concorda em receber os aplicativos.
3. Ambos recebem um aviso de transferência pendente (por e-mail e na página **Meus aplicativos**).   
   **Observação:** enquanto a transferência estiver pendente, qualquer administrador pode excluir a solicitação de transferência do aplicativo (ou seja, cancelar a transferência).
4. A AppsFlyer transfere os aplicativos. Se um pré-requisito estiver incompleto, a AppsFlyer entrará em contato com a parte correspondente para garantir a conclusão.

<Accordion title="Escopo de transferência de aplicativos">

A tabela a seguir detalha quais recursos e configurações do aplicativo são transferidos. Observe que o remetente pode, a seu critério, excluir determinadas configurações e informações de configuração antes da transferência.

<table><thead><tr><th>Item</th><th>Transferido/<br/>não transferido</th><th>Detalhes/critérios</th></tr></thead><tbody><tr><td>Configurações do aplicativo </td><td>Transferido</td><td> <strong>Critério:</strong> O remetente pode excluir a chave do servidor Firebase/GCM antes da transferência. </td></tr><tr><td rowspan="2">Parceiros integrados</td><td>Transferido</td><td><p>Configurações de integração, custo e receita (incluindo dados de custo e receita)</p><p><strong>Critério:</strong> se o destinatário não precisar que parceiros integrados sejam transferidos, o remetente deverá desativá-los e excluir suas configurações e credenciais (incluindo configurações de custo e receita de anúncios).</p></td></tr><tr><td>Não</td><td><p>Ad network e permissões de agência</p><p>Configurações e credenciais do Twitter</p></td></tr><tr><td>Gestão de links</td><td>Não</td><td><p>Templates e links do OneLink não são transferidos automaticamente, mas podem ser enviados pelo seu CSM. </p><p>Para transferir templates e links, fale com seu CSM ou envie uma mensagem para <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>. <br/><strong>Atenção:</strong> Links em massa são transferidos automaticamente junto com o modelo.</p><ul><li>O remetente pode excluir links obsoletos antes de realizar a transferência.</li><li>Os tokens da API do OneLink não podem ser transferidos entre contas. Você precisará usar um <a href="./managing-appsflyer-tokens" target="_blank">token</a> da sua nova conta.</li></ul><p>A lista de permissões de redirecionamento de domínio também não é transferida automaticamente. Se a lista de permissões da conta de destino ainda não incluir os domínios do aplicativo transferido, os links que usam esses domínios deixarão de funcionar após a transferência. Antes ou imediatamente após a transferência, configure a <a href="./set-up-your-domain-redirect-allowlist" target="_blank">lista de permissões de redirecionamento de domínio</a> na conta de destino.</p></td></tr><tr><td>API de push</td><td>Transferido</td><td><p><strong>Critério:</strong></p><ul><li>Se o destinatário não precisar que as configurações da Push API (endpoints) sejam transferidas, o remetente deve excluí-las. Caso contrário, os dados continuarão sendo enviados aos endpoints definidos pelo remetente.</li><li>Como alternativa, o destinatário pode alterar essas configurações para garantir que o remetente não receba dados no nível do usuário. </li></ul></td></tr><tr><td>Smart Banners</td><td>Não</td><td>Banners, grupos de banners, criativos e sites não são transferidos. </td></tr><tr><td>Smart Script</td><td>Não</td><td>Smart Scripts criados na interface do usuário da AppsFlyer não estarão disponíveis na nova conta. </td></tr><tr><td>Agências</td><td>Não</td><td>As agências perdem o acesso ao aplicativo.</td></tr><tr><td>Audiências</td><td>Não transferido</td><td>As audiências são excluídas.</td></tr><tr><td>Cost import</td><td>N/D</td><td>O histórico de arquivos de cost import não podem ser acessados pelo destinatário. No entanto, isso não afeta o histórico de custo. </td></tr><tr><td>Relatório do Data Locker</td><td>Não transferido</td><td>O aplicativo é removido da configuração do Data Locker e a conta do destinatário deixa de receber dados do aplicativo. </td></tr><tr><td>Histórico de dados</td><td>Transferido</td><td> </td></tr><tr><td>Pacotes de marca PBA</td><td>Não transferido</td><td><p>O bundle não estará mais disponível para o remetente se algum dos aplicativos relacionados for transferido. O destinatário não pode acessar dados de PBA.</p><p>Isso significa que, se o cliente precisar continuar usando PBA em sua nova conta, precisará excluir o web bundle antes que a transferência do aplicativo seja concluída; caso contrário, não conseguirá criar o mesmo web bundle na nova conta.</p></td></tr><tr><td>Dados do Protect360</td><td>Transferido</td><td><p>Se um aplicativo for transferido de uma conta sem um recurso Protect360 para uma conta que tenha esse recurso: </p><ul><li>A detecção de fraude começa somente após a conclusão da transferência.</li><li>Se a conta de destino tiver o recurso disponível apenas durante parte do tempo, os dados de fraude ficarão disponíveis somente a partir da data de início do recurso, e não retroativamente.</li><li>Nenhuma detecção de fraude ocorre durante o processo de transferência.</li></ul></td></tr><tr><td>Dados brutos e agregados</td><td>Transferido</td><td> </td></tr><tr><td>SDK dev key</td><td>Transferido</td><td> </td></tr><tr><td>Regras de validação</td><td>Transferido</td><td> </td></tr></tbody></table>

</Accordion>

## Procedimentos de transferência

Para solicitar a transferência de um ou mais aplicativos para outra conta da AppsFlyer, inicie o processo e você será guiado pelo assistente na interface do usuário.

<Accordion title="Remetente">

**Para enviar uma solicitação de transferência**:

1. Entre em contato com o administrador destinatário:
   1. Revise e concorde com o [escopo de transferência de apps](/docs/transferring-apps-between-accounts#app-transfer-scope). Certifique-se de que ambos estejam cientes do que será ou não será transferido e que ambos estejam devidamente preparados.
   2. Solicite que o destinatário forneça o e-mail de administrador que ele usa na AppsFlyer.
2. Siga um dos procedimentos abaixo:
   * Para transferir um aplicativo: No menu superior > **Meus Aplicativos** > Abrir menu de ação do aplicativo (...) > Selecione **Transferir aplicativo**.
   * Para transferir 2 ou mais aplicativos: No menu superior > **Meus Aplicativos** > Abrir menu de ação do aplicativo (...) > Selecione **Transferir aplicativo**.
3. Escolha o aplicativo ou aplicativos que você deseja transferir.
4. Clique em **Próximo**.
5. Insira o endereço de e-mail do destinatário.
6. Clique em **Próximo**.
7. Leia e assine os termos e condições.
   * Você e o destinatário receberão uma notificação (por e-mail) de que a solicitação foi enviada com sucesso.
   * Você receberá uma notificação (por pop-up) se a solicitação exigir qualquer ação por parte da AppsFlyer.
   * Os apps aparecem na página **Meus apps** como transferência pendente para o `<e-mail do destinatário>`. Nessa fase, ainda é possível excluir a solicitação.

     ![Página Meus aplicativos do remetente mostrando um aplicativo listado como transferência pendente, com a opção Solicitar exclusão](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<Accordion title="Remetente">

1. Fale com o remetente para revisar o [escopo da transferência do aplicativo](/docs/transferring-apps-between-accounts#app-transfer-scope). Certifique-se de que ambos estejam cientes do que será ou não será transferido e que ambos estejam devidamente preparados.
2. Você receberá uma notificação por e-mail informando que o remetente iniciou a solicitação de transferência.
3. Na página **Meus apps**, clique em **Revisar solicitação**. Uma solicitação pode incluir um ou mais aplicativos.

   ![Página Meus aplicativos do destinatário mostrando uma solicitação de transferência de aplicativo pendente, com a opção Revisar solicitação](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. Revise e aprove ou rejeite cada solicitação.
5. Leia e, caso esteja de acordo, assine os termos e condições.
6. Você e o remetente serão notificados por e-mail de que a solicitação foi aceita.
7. Aplicativos transferidos aparecem na página **Meus apps**.

</Accordion>

<Accordion title="Excluir solicitação de transferência">

Antes da finalização da transferência, o processo pode ser excluído (cancelado) pelo administrador de origem ou pelo destinatário.

**Para excluir uma solicitação de transferência de aplicativos:**

* **Administrador remetente**: No menu superior > **Meus aplicativos** > **Transferência pendente para [e-mail]** > clique em **Excluir solicitação**.   
  Ambas as partes serão notificadas (e-mail).
* **Administrador destinatário**:
* No menu superior > **Meus aplicativos** > **Transferência pendente** > clique em **Rejeitar**.   
  Ambas as partes serão notificadas (e-mail).

</Accordion>

<div data-zendesk-anchors="app-transfer-between-accounts=transfer%C3%AAncia-de-aplicativos-entre-contas h_01HJR1G7Q71H5DAH1G9QFSYK35=transfer%C3%AAncia-de-aplicativos-entre-contas prerequisites=pr%C3%A9-requisitos h_01HJR1G7Q7T1Q768MTTR3Y542X=pr%C3%A9-requisitos app-transfer-process=processo-de-transfer%C3%AAncia-de-aplicativos h_01HJR1G7Q7EDJZ4E1T17GWYGTP=processo-de-transfer%C3%AAncia-de-aplicativos transfer-procedures=procedimentos-de-transfer%C3%AAncia h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=procedimentos-de-transfer%C3%AAncia" />
