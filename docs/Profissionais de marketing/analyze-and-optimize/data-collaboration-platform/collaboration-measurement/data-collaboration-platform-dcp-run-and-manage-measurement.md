---
title: Plataforma de colaboração de dados (DCP) - execute e gerencie mensurações
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-08-18T00:06:43Z'
  id: 44427723216017
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/44427723216017
---
> **Resumo:** Após configurar a mensuração on-site ou off-site, execute-a como uma mensuração histórica ou em tempo real. Escolha o modo que melhor atende ao seu objetivo: mensurar a performance continuamente ou validar resultados por um período definido.

## Sobre os modos de execução da mensuração

Depois de <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-a-mensuração-de-campanhas-on-site-e-off-site">configurar a mensuração on-site ou off-site</Anchor>, você já pode escolher como executá-la.

Existem dois modos de execução disponíveis:

* **Mensuração em tempo real**: uma mensuração constante atualizada em intervalos regulares para monitorar a performance continuamente à medida que novos dados são adicionados em tempo real no dashboard.
* **Mensuração histórica**: uma mensuração única em um intervalo de datas específico que você pode visualizar e analisar em um dashboard histórico.

### Mensurações históricas vs. mensurações em tempo real

| Tópico | Mensuração histórica | Mensuração em tempo real |
| --- | --- | --- |
| Quando é executada | Execução **sob demanda** (manual) | Execução **automática** diária |
| Fonte de dados | Utiliza **uploads de dados históricos** | Exige **configuração de SDK/ETL** e é executada em intervalos de tempo predefinidos |
| Tipos de fontes disponíveis | <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Adicionar</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Substituir (instantâneo)</Anchor> | <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Adicionar fontes personalizadas do tipo “Adicionar”</Anchor> |
| Seleção do período de tempo | Selecione uma **data de início e término** (a partir dos dados disponíveis) | Selecione uma **data de início** (a plataforma calcula o período histórico na ativação e continua acumulando dados) |
| Quantas por colaboração | Várias | Uma |

### Escolha a mensuração ideal para você

Veja as informações abaixo para decidir qual mensuração melhor atende ao seu objetivo.

**Escolha a mensuração em tempo real se você quiser**

* Uma mensuração constante que continua atualizando à medida que novos dados chegam
* Um dashboard para monitorar a performance continuamente
* Uma configuração destinada a mensurações de longo prazo, sempre ativas (não uma análise pontual)

**Escolha a mensuração histórica se você quiser**

* Executar uma mensuração única para um intervalo de datas específico.
* Analisar a performance após o fim de uma campanha.
* Fazer uma análise do que aconteceria ao alterar a janela de retrocesso para ver como isso afeta a atribuição.

**Dica:** Se você estiver testando sua configuração ou validando um período específico, comece com a **mensuração histórica**. Quando quiser um monitoramento contínuo, mude para a **mensuração em tempo real** e receba atualizações constantes.

## Executar uma mensuração em tempo real

**Antes de começar:**  <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-a-mensuração-de-campanhas-on-site-e-off-site">Configure a campanha de mensuração on-site ou off-site na página Configurações de mensuração</Anchor>.

1. Na página **Configurações de mensuração**, clique em **Executar agora**.

   Se a opção **Executar agora** estiver desativada, suas tarefas estão incompletas. Conclua todas as tarefas de configuração necessárias para executar a mensuração.
2. Na caixa de diálogo **Preparar execução**, selecione **Dashboard em tempo real**.

   > 📘 **Nota**
   >
   > * Se a mensuração usar fontes do tipo <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Substituir</Anchor>, apenas o **dashboard histórico** estará disponível. O **dashboard em tempo real** exige fontes do tipo **Adicionar** (ou eventos do SDK da AppsFlyer) para atualizações automáticas.
   > * Apenas **uma mensuração em tempo real** por vez pode ser executada em uma colaboração. Se você iniciar uma nova mensuração em tempo real enquanto outra já estiver em execução, será necessário pausar a atual.

3. Renomeie o dashboard ou mantenha o nome padrão.
4. Selecione a **data de início da mensuração**. O padrão é a data de hoje, mas você pode selecionar uma data antiga no campo de seleção de datas. (você só pode selecionar datas que existem em suas fontes de dados.)
5. Clique em **Iniciar** para começar a mensuração em tempo real. Você será redirecionado para a página de mensuração de colaboração.
6. Na página de mensuração de colaboração, após as verificações de validação automática serem concluídas, clique em **Executar agora**.

## Executar uma mensuração histórica

**Antes de começar:**  <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-a-mensuração-de-campanhas-on-site-e-off-site">Configure a campanha de mensuração on-site ou off-site na página Configurações de mensuração</Anchor>.

1. Em **Configurações de mensuração**, clique em **Executar agora**.  
   Se a opção **Executar agora** estiver desativada, suas tarefas estão incompletas. Conclua todas as tarefas de configuração necessárias para executar a mensuração.
2. Na caixa de diálogo **Preparar execução**, selecione **Dashboard histórico**.
3. Renomeie o dashboard ou mantenha o nome padrão.
4. Selecione o **intervalo de datas da mensuração** (você só pode selecionar datas que existem em suas fontes de dados):
   * Defina a **data de início**.
   * Defina a **data de término**.
5. Clique **Iniciar** para começar a mensuração histórica. Você será redirecionado para a página de mensuração de colaboração.
6. Na página de mensuração de colaboração, após as verificações de validação automática serem concluídas, clique em **Executar agora**.

## Gerenciar mensurações

Após configurar e executar sua mensuração, gerencie-a no painel de mensuração da página de mensuração de colaboração. Você pode pausar ou reiniciar a mensuração em tempo real, ajustar datas, executar mensurações históricas novamente ou duplicar uma mensuração para criar uma nova execução.

### Página de mensuração de colaboração

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

<div id="pause-or-restart-live-measurement" />

<Accordion title="Pausar ou reiniciar a mensuração em tempo real">

#### Legenda

* **A** - O painel de mensuração
* **B** - A mensuração selecionada
* **C** - O botão “Compartilhado”
* **D** - O menu de opções

1. Abra a página de mensuração de colaboração.
2. Selecione **Dashboard em tempo real** no painel de mensuração ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)).
3. Abra o menu de opções ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)) e clique em **Configurações de mensuração**.
4. Na página **Configurações de mensuração**, escolha uma das etapas abaixo:
   * Para **pausar** a atribuição em tempo real, desative a opção **Ativar mensuração**, e confirme **Pausar mensuração?** na caixa de diálogo.
   * Para **reiniciar** a atribuição em tempo real, ative a opção **Ativar mensuração**.

</Accordion>

<div id="change-measurement-start-and-end-dates" />

<Accordion title="Alterar as datas de início e término da mensuração">

Você pode alterar:

* A **data de início** para uma mensuração em tempo real ou
* As **datas de início e término** para uma mensuração histórica.

Para alterar as datas de início e término da mensuração, siga estas etapas:

1. Abra a página de mensuração de colaboração.
2. Selecione a mensuração no painel de mensuração ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)).
3. Abra o menu de opções ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)) e clique em **Configurações de mensuração**.
4. Na página **Configurações de mensuração**, clique no ícone de edição.
5. Clique na data de início ou término.
6. Selecione a nova data no campo de seleção de datas.

</Accordion>

<div id="rerun-a-historical-measurement" />

<Accordion title="Executar uma mensuração histórica novamente">

Ao executar uma mensuração histórica novamente, você recalcula a atribuição usando os dados mais recentes. Os resultados atuais são substituídos pelos novos.

1. Abra a página de mensuração de colaboração.
2. Selecione a mensuração no painel de mensuração ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)).
3. Abra o menu de opções ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)) e clique em **Executar novamente**.
4. Na mensagem exibida, clique em **Executar novamente**.
5. Na página de mensuração de colaboração, após as verificações de validação automática serem concluídas, clique em **Executar agora**.

</Accordion>

<div id="duplicate-a-live-or-historical-measurement" />

<Accordion title="Duplicar uma mensuração histórica ou em tempo real">

A duplicação cria uma nova mensuração com base em uma configuração existente. Você pode atualizar as configurações e executá-la como uma nova mensuração.

1. Abra a página de mensuração de colaboração.
2. Selecione a mensuração no painel de mensuração ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)).
3. Abra o menu de opções ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)) e clique em **Duplicar**.
4. Na página **Configurações de mensuração** duplicada, personalize a mensuração de acordo com suas necessidades.

</Accordion>

<div id="share-a-dashboard" />

<Accordion title="Compartilhar um dashboard">

Você pode compartilhar um dashboard com seus colaboradores ao ativar a opção **Compartilhado**. Quando a opção **Compartilhado** está ATIVADA, o dashboard (e os resultados de mensuração) está disponível para outros usuários na colaboração.

Quando a opção **Compartilhado** está ATIVADA, as permissões dos colaboradores variam de acordo com sua **atribuição ou não atribuição** ao dashboard.

* **Usuários atribuídos podem:**
  * Abrir e **visualizar o dashboard**
  * Abrir as **configurações de mensuração** e **editar apenas as tarefas atribuídas a eles.**

* **Usuários atribuídos não podem:**
  * Ativar ou desativar a opção **Compartilhado** =(compartilhar ou não compartilhar)
  * Executar a mensuração **novamente**

* **Usuários não atribuídos** têm acesso mais limitado, mesmo que o dashboard seja compartilhado (exemplo: talvez eles não vejam o resumo dos resultados; também não poderão executar a mensuração novamente nem compartilhar o dashboard).

Para compartilhar um dashboard:

1. Abra a página de mensuração de colaboração e selecione o **dashboard** que você deseja compartilhar no painel de mensuração ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)).
2. Ative a opção **Compartilhado** ([C](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#página-de-mensuração-de-colaboração)). O dashboard estará disponível na página de mensuração de colaboradores.
3. Desative a opção **Compartilhado** para interromper o compartilhamento. Quando a opção estiver desativada, apenas você (e usuários com permissões) poderão acessar o dashboard.

</Accordion>

<div data-zendesk-anchors="about-the-measurement-run-modes=sobre-os-modos-de-execu%C3%A7%C3%A3o-da-mensura%C3%A7%C3%A3o h_01KJW81RSZPK2Y1PSAF9FSMXB6=sobre-os-modos-de-execu%C3%A7%C3%A3o-da-mensura%C3%A7%C3%A3o live-vs-historical-measurements=mensura%C3%A7%C3%B5es-hist%C3%B3ricas-vs-mensura%C3%A7%C3%B5es-em-tempo-real h_01KJW81RSZBG5ZC8HE9WFXE34D=mensura%C3%A7%C3%B5es-hist%C3%B3ricas-vs-mensura%C3%A7%C3%B5es-em-tempo-real choose-the-measurement-you-need=escolha-a-mensura%C3%A7%C3%A3o-ideal-para-voc%C3%AA h_01KJW81RSZQG21Z0MRHWPMD69F=escolha-a-mensura%C3%A7%C3%A3o-ideal-para-voc%C3%AA run-a-live-measurement=executar-uma-mensura%C3%A7%C3%A3o-em-tempo-real h_01KJW81RT0Q1RWEHZP66B5141M=executar-uma-mensura%C3%A7%C3%A3o-em-tempo-real h_01KJW81RT0N37ARE5570X7MYJF=nota run-a-historical-measurement=executar-uma-mensura%C3%A7%C3%A3o-hist%C3%B3rica h_01KJW81RT0QECMGBTRFSETA5A8=executar-uma-mensura%C3%A7%C3%A3o-hist%C3%B3rica manage-measurements=gerenciar-mensura%C3%A7%C3%B5es h_01KJW81RT046RE5FVHPGEDMCC5=gerenciar-mensura%C3%A7%C3%B5es the-collaboration-measurement-page=p%C3%A1gina-de-mensura%C3%A7%C3%A3o-de-colabora%C3%A7%C3%A3o h_01KJWNTR04PRG54W0GZVGQY72X=p%C3%A1gina-de-mensura%C3%A7%C3%A3o-de-colabora%C3%A7%C3%A3o legend=legenda h_01KJWNF8NAJ9NT5T8NAVTCMZVA=legenda h_01KJW81RT0A148W49X0BR0V9YM=pause-or-restart-live-measurement h_01KJW81RT0GYDCZCXXV2G5EJD7=change-measurement-start-and-end-dates h_01KJW81RT054CCYMTKFN7TS1XV=rerun-a-historical-measurement h_01KJW81RT0RKQJRCTRVP36YBKV=duplicate-a-live-or-historical-measurement h_01KJW81RT0C3R95JQVPGSZ043B=share-a-dashboard" />
