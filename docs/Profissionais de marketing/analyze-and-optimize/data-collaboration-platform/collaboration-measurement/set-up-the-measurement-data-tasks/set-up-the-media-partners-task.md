---
title: Configure a tarefa de Parceiros de mídia
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
  created_at: '2025-08-18T11:36:01Z'
  edited_at: '2026-08-18T00:06:29Z'
  id: 38191067035153
  locale: pt
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/pt/articles/38191067035153
---
> **Visão geral:** Saiba como configurar parceiros de mídia para campanhas off-site.

Antes de compartilhar conversões qualificadas com os Parceiros de mídia da sua <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campanha off-site</Anchor> e receber, em resposta, dados de performance agregados, primeiro você precisa conectar o DCP à conta de mídia que ativa a campanha. Essa conexão informa à AppsFlyer como enviar os dados de conversão ao Parceiro de mídia.

<div id="prerequisites" />

## Pré-requisitos

Antes que a tarefa de Parceiros de mídia possa ser configurada, o proprietário da colaboração precisa atribuí-la ao colaborador que possui a conta de terceiros (por exemplo, Facebook ou Google). Para obter mais informações, consulte Atribuir tarefas de configuração

<div id="create-a-media-partner-connection" />

<Accordion title="Criar uma conexão com um Parceiro de mídia">

<div id="note" />

> 📘 **Observação:**
>
> A tarefa **Parceiros de mídia** aparece na página **Configurações de mensuração** somente quando você configura uma <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campanha off-site</Anchor> que usa uma fonte personalizada como método de provisionamento. Para obter mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task#set-conversion-data-provision-method">Definir o método de provisionamento de dados de conversão</Anchor>

Para selecionar ou criar uma conexão com um Parceiro de mídia, siga estas etapas:

1. Na página **Configurações de mensuração** , clique na **tarefa Parceiros de mídia** .

   <div id="note-1" />

   > 📘 **Observação:**
   >
   > * Se a caixa de diálogo **Parceiros de mídia** estiver bloqueada, isso significa que a tarefa **Parceiros de mídia** foi atribuída ao seu colaborador e que você não pode visualizar seu conteúdo. Se você for o proprietário da colaboração, poderá desbloqueá-la e reatribuir a tarefa a si mesmo. No entanto, todas as configurações anteriores serão excluídas, e a tarefa será redefinida.
   > * Se o painel **Parceiros de mídia** estiver esmaecido, peça ao proprietário da colaboração para atribuir a você a tarefa de conversão.

2. Na caixa de diálogo Media partners, clique **+ Connect media partner** .
3. Na caixa de diálogo **Conectar parceiro de mídia** , crie ou selecione uma conexão de parceiro de mídia para a conta de mídia que ativa a campanha:
   * **Se houver uma conexão existente disponível, selecione-a:**
     * Na lista suspensa **Selecionar conexão** , escolha uma conexão existente.
   * **Se não houver conexões, crie uma:**
     1. Clique **+ Nova conexão** .
     2. Na janela **Nova conexão com parceiro de mídia** , selecione um parceiro de mídia, como **Meta Ads** ou **Google Ads** .
     3. No campo **Nome da conexão** , insira um nome para a nova conexão.
     4. Clique **Login no [Media Partner]** e conclua a autenticação na janela de login do parceiro de mídia.
     5. Clique em **Salvar** após a conclusão da autenticação. Depois de salva, a nova conexão é selecionada automaticamente no menu suspenso **Selecionar conexão** da caixa de diálogo **Conectar parceiro de mídia**.

</Accordion>

<div id="set-the-google-ads-conversion-action-id-parameter" />

<Accordion title="Defina o parâmetro ID da ação de conversão do Google Ads">

Se o seu parceiro de mídia for o Google Ads, forneça ao DCP o parâmetro ID da ação de conversão. O ID da ação de conversão é obtido na sua conta do Google Ads e incluído nos dados de conversão enviados ao Google Ads. A ação de conversã**o** deve ser do tipo `UPLOAD_CLICKS`.

Para saber mais sobre a ação de conversão do Google Ads, consulte a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12216226?hl=en">documentação do Google Ads</Anchor>.

Para definir o ID da ação de conversão do Google Ads, siga estas etapas:

1. No menu suspenso **Select connection**, selecione uma conexão de anúncios do Google.
2. Na caixa de diálogo **Connect media partner**, preencha **pelo menos um** dos seguintes campos com o ID da ação de conversão do Google Ads. **Observação:** Você pode usar o mesmo ID em vários ativos da web ou de mobile e pode deixar alguns ativos sem atribuição. No entanto, os ativos sem um ID da ação de conversão não serão atribuídos.

   * **Ação de conversão da web:** o ID da ação de conversão usado para eventos de conversão criados no site do colaborador. Ela deve ser uma **ação de conversão** do tipo `UPLOAD_CLICKS`.
   * **Ação de conversão do aplicativo (por aplicativo):** o ID da ação de conversão usado para eventos de conversão criados no aplicativo do colaborador. Insira o ID da ação de conversão correspondente, também do tipo `UPLOAD_CLICKS`.

   <div id="note-2" />

   > 📘 **Observação:**
   >
   > Essas ações de conversão devem ser mantidas **exclusivamente para a mensuração do DCP** e não devem ser usadas para outro tráfego.

3. Clique em **Concluído** para voltar à caixa de diálogo principal.
4. Confirme se a conexão está listada e clique em **Salvar**.
5. Na página **Measurement settings** , verifique se o parceiro de mídia exibe uma marca de seleção verde e o status como **Connected**.

</Accordion>

<div id="set-the-meta-ads-meta-pixel-and-dataset-id-parameters" />

<Accordion title="Defina os parâmetros Meta Pixel e ID do conjunto de dados do Meta Ads">

Se o seu parceiro de mídia for o Meta Ads, forneça ao DCP os parâmetros Meta Pixel e ID do conjunto de dados. O Meta Pixel e o ID do conjunto de dados são obtidos na sua conta do Meta Ads e incluídos nos dados de conversão enviados ao Meta Ads.

Consulte a documentação do Meta Ads sobre o <Anchor target="_blank" href="https://www.facebook.com/business/help/952192354843755?id=1205376682832142">Meta Pixel</Anchor> e o <Anchor target="_blank" href="https://www.facebook.com/business/help/5818684664831465?id=490360542427371">ID do conjunto de dados</Anchor>.

Para definir o ID da ação de conversão do Meta Ads, siga estas etapas:

1. No menu suspenso **Select connection**, selecione uma conexão do Meta Ads.
2. Na caixa de diálogo **Conectar parceiro de mídia**, preencha **pelo menos um** dos campos a seguir com os IDs da Meta ou do Pixel. **Observação:** Você pode deixar alguns ativos não atribuídos. No entanto, os ativos sem um ID de ação de conversão não serão atribuídos.

   * **Meta Pixel:** O ID usado para eventos de conversão criados no site do colaborador.
   * **ID do Dataset (por aplicativo):** O ID usado para eventos de conversão criados no aplicativo do colaborador.

   <div id="warning" />

   > ❗️ **Atenção**
   >
   > O Dataset e o Meta Pixel devem atender às seguintes condições:
   >
   > * Ser criado especificamente para o DCP.
   > * Não deve **receber conversões diretamente** do cliente.
   > * O Meta Pixel e o ID do Dataset são intercambiáveis.


   <div id="note-3" />

   > 📘 **Observação:**
   >
   > O **usuário do sistema** cujas credenciais são compartilhadas com o DCP deve:
   >
   > * Ter **acesso** ao Dataset.
   > * Receber a permissão **ads\_read** .

3. Clique em **Concluído** para retornar à caixa de diálogo principal.
4. Confirme se a conexão está listada e clique **Salvar**.
5. Na página **Configurações de mensuração** , verifique se o parceiro de mídia mostra uma marca de seleção verde e o status como **Conectado**.

</Accordion>

<div data-zendesk-anchors="prerequisites=pr%C3%A9-requisitos h_01K3G4VZX9X67EG0AA7GASSR51=pr%C3%A9-requisitos h_01K3G4VZX9QBCX8NGQJ6GV02CS=create-a-media-partner-connection h_01K3G4VZX90X7GFX0S274EP5Y4=observa%C3%A7%C3%A3o h_01K3G4VZX9GX7JRZ7ZJPSG50VS=observa%C3%A7%C3%A3o-1 h_01K3G4VZX9S8V2DVCNGNBHEFAD=set-the-google-ads-conversion-action-id-parameter h_01K3G4VZX93P0K0B0R4DR1JMB3=observa%C3%A7%C3%A3o-2 h_01K3G4VZX9WC21793Q33431PCB=set-the-meta-ads-meta-pixel-and-dataset-id-parameters h_01K3G4VZX9KADAF2XXFEWVXG81=aten%C3%A7%C3%A3o h_01K3G4VZXAQBHPPE91WM7R2REH=observa%C3%A7%C3%A3o-3" />
