---
title: Configure a ROI360 cost API para mensurar dados de custo
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-23T01:09:27Z'
  id: 360008850257
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360008850257
---
> **At a glance:** Obtenha dados agregados de custo de marketing, incluindo métricas de performance de LTV (Lifetime Value) relacionadas a custo, usando a API de custo no nível da conta da fonte de mídia.

<div id="overview" />

## Retorna um objeto JSON com os dados brutos de consentimento do DMA conforme enviados do anunciante para a AppsFlyer

O ROI360 fornece dados agregados de custo de marketing, incluindo métricas de performance de LTV relacionadas a custo, no nível da conta de anúncios.

As integrações de custos são configuradas em **Configurações de custo**, em que cada integração se conecta a uma conta de canal de mídia e mede o custo de todos os aplicativos selecionados. Dependendo da ad network, isso pode incluir aplicativos mobile, de CTV, de PC e console e web. Conecte cada conta de canal de mídia uma vez para ativar o custo para vários aplicativos.

As integrações de custo também podem ser criadas e editadas na guia **Custo** do Partner Marketplace. Qualquer ponto de entrada gera a mesma integração no nível da conta.

<div id="note" />

> 📘 **Importante!**
>
> O acesso a **Configurações de custo** é controlado de acordo com as permissões de cada função. Se você não conseguir acessar as **configurações de custo**, peça ao seu administrador para atualizar suas permissões na página **Gerenciamento do usuário**. No caso, você precisa de permissão para gerenciar **conexões de custo**.

<div id="create-a-new-api-cost-integration" />

## Criar uma nova integração de custos de API

Toda integração de custos segue as mesmas duas etapas: autenticar com o canal de mídia e, em seguida, nomear a integração e selecionar os aplicativos que ela abrange. Alguns canais de mídia exigem uma etapa adicional para que a AppsFlyer possa associar seus aplicativos aos identificadores usados no sistema deles.

Após a configuração inicial, os dados de custo aparecem no dashboard na próxima extração de dados, agendada a cada quatro horas, seis vezes por dia.

<div id="h_01M43Y9WQ8WCXWQ0S9ZAT59CWW" />

<Accordion title="Etapa 1: Forneça as credenciais">

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **ROI360** > **Configurações de custo**.
2. Clique em **+ Nova integração**, selecione o canal de mídia e depois clique em **Próximo**.
3. Dependendo do canal de mídia, você verá uma das seguintes opções:
   * **Login:** faça login com sua conta da ad network e conclua o fluxo de autenticação. A AppsFlyer valida a conexão e nomeia a integração com base na conta que você conectou.
   * **Credenciais:** forneça credenciais estáticas e preencha os campos exibidos para esse canal de mídia, por exemplo, nome de usuário e senha ou uma chave da API. Os nomes dos campos variam de acordo com o canal de mídia. As credenciais estáticas não são validadas durante a configuração.
4. Renomeie a integração se quiser usar um nome diferente ou mantenha o nome padrão. O nome pode ter no máximo 50 caracteres e funciona como um rótulo para ajudar você a identificar a integração depois, o que é importante se você criar mais de uma para o mesmo canal de mídia.

</Accordion>

<div id="h_01M43Y9WQ8HK1N0GJNW5BH4MPZ" />

<Accordion title="Etapa 2: Selecione os aplicativos">

Clique em **Selecionar aplicativos** e escolha os aplicativos abrangidos por esta integração. Você pode selecionar qualquer aplicativo ao qual tenha permissão de acesso — mobile, web, CTV ou qualquer outra plataforma que você use para executar suas campanhas. Clique em **Aplicar** e depois em **Próximo**.

Se o canal de mídia exigir uma etapa adicional, continue para a [Etapa 3](#additional-steps-specific-media-sources-only) abaixo. Caso contrário, clique em **Salvar integração**.

</Accordion>

<div id="additional-steps-specific-media-sources-only" />

<Accordion title="Etapa 3: Etapas adicionais (apenas para canais de mídia específicos)">

Alguns canais de mídia exigem uma etapa adicional depois que você seleciona os aplicativos. Adicione o mapeamento aos nomes de pacote e IDs de bundle ou aos IDs de site.

<div id="map-apps-to-package-names-or-bundle-ids" />

#### Mapeie aplicativos para nomes de pacote ou IDs de bundle

Há canais de mídia que identificam aplicativos pelo nome do pacote do Android ou pelo ID de bundle do iOS, por exemplo, a AppLovin.

Como parte da configuração de custo, depois que você selecionar seus aplicativos, insira o nome exato do pacote ou o ID de bundle de cada aplicativo, como aparece no sistema do canal de mídia. Todo aplicativo exige um valor de mapeamento. Clique em **Guardar integração**.

<div id="map-apps-to-site-ids" />

#### Mapeie aplicativos para IDs de site

Para canais de mídia que identificam aplicativos por ID de site, por exemplo, a Liftoff.

Depois que você selecionar seus aplicativos, escolha um parâmetro de ID de site padrão. Isso se aplica a todos os aplicativos da integração. Padrões disponíveis:

* `${APP_ID}`
* `${APP_NAME}`
* `${APP_ID}_${APP_NAME}`
* `${APP_NAME}_${APP_ID}`

Para substituir o padrão em um aplicativo específico, selecione um parâmetro diferente no menu suspenso **ID de site** desse aplicativo. Use isso quando o ID de site de um aplicativo estiver formatado de forma diferente no sistema do canal de mídia. Clique em **Guardar integração**.

<div id="note-1" />

> 📘 **Importante!**
>
> O mapeamento de ID de site garante que as macros de ID de site do link de atribuição da AppsFlyer correspondam ao valor que o canal de mídia espera. Se o seu link de atribuição usar macros diferentes do mapeamento que você selecionar, os dados de ID de site não serão preenchidos corretamente.

<div id="select-which-ad-account-to-pull-cost-from" />

#### Selecione de qual conta de anúncio extrair o custo

Em alguns canais de mídia, como o TikTok, um login pode ter acesso a várias contas de anúncio. Depois de fazer login no canal de mídia, você precisa selecionar a conta de anúncio específica.

</Accordion>

<div id="edit-and-delete-an-integration" />

## Editar e excluir uma integração

Isso funciona da mesma forma para todas as integrações, independentemente do ponto de entrada, **Configurações de custo** ou a guia **custo**, que você usou para criá-la.

<div id="h_01M43Y9WQ804YMN8TZ7HGYSQH7" />

<Accordion title="Editar uma integração de custos">

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **ROI360** > **Configurações de custo**.
2. Clique no canal de mídia que você quer editar.
3. Na página do canal de mídia, clique na conta específica que você quer editar.
4. Na guia **Aplicativos**, clique em **Editar** para adicionar ou remover aplicativos e, em seguida, salve as alterações.

Os aplicativos adicionados a uma integração que usa uma etapa adicional precisam ser mapeados antes que você possa salvar as alterações. A guia **Detalhes da integração** mostra as configurações da conexão.

</Accordion>

<div id="h_01M43Y9WQ89XKB2CN2EY4TG2AD" />

<Accordion title="Excluir uma integração de custos">

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **ROI360** > **Configurações de custo**.
2. Clique no canal de mídia do qual você quer excluir.
3. Na página do canal de mídia, na coluna **Ação**, clique no ícone de exclusão da conta específica que você quer remover.
4. Na caixa de diálogo de confirmação, clique em **Sim, excluir**.

A coleta de dados de custo é interrompida imediatamente. Os dados históricos de custo não são afetados.

</Accordion>

<div id="h_01M43Y9WQ8ANZY2KNHKMV67YNY" />

<Accordion title="Transferir um aplicativo para outra conta">

As integrações de custos são desconectadas automaticamente quando um aplicativo é transferido para outra conta.

</Accordion>

<div id="view-cost-api-status" />

## Ver o status da API de custo

O status da integração de custos é informado em dois níveis.

* **Nível do aplicativo:** cada aplicativo incluído em uma integração tem seu próprio status. É aqui que o estado real da coleta de dados é informado.
* **Nível da conexão:** cada integração mostra um único status, derivado dos status dos aplicativos dentro dela. Quando todos os aplicativos compartilham o mesmo status, a conexão mostra esse status. Quando os aplicativos têm status diferentes, a conexão mostra **Misto**. Misto não indica um problema com a conexão em si, significa que os aplicativos não estão em um estado uniforme. Abra a integração para ver quais aplicativos foram afetados.

O status está disponível nos seguintes locais:

| Onde: | Nível exibido |
| --- | --- |
| Configurações de custo | Nível da conexão e nível do aplicativo |
| Dashboard do status da integração de custo | Nível do aplicativo, em todos os canais de mídia com integração de custos ativada na sua conta e na conta da agência com a qual você trabalha. O status misto não é exibido. |
| Aba de custo | Nível do aplicativo, para um aplicativo e um canal de mídia por vez |

<div id="view-status-in-cost-settings" />

<Accordion title="Ver status em Configurações de custo">

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **ROI360** > **Configurações de custo**.
2. Selecione o canal de mídia relevante. A coluna **Status** mostra o status no nível da conexão para cada integração.
3. Para ver o status no nível do aplicativo, clique na linha da integração para abrir a página **Integração de custos** e, em seguida, veja o status de cada aplicativo na lista.

</Accordion>

<div id="view-status-in-cost-tab" />

<Accordion title="Ver status na guia Custo">

Relevante para canais de mídia compatíveis com a obtenção de dados de custo via API. Esta visualização mostra o status do aplicativo selecionado, junto com a última vez em que a AppsFlyer extraiu com sucesso os dados de custo correspondentes para ele.

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Integrações ativas**.
2. Selecione o canal de mídia.
3. Na lista de aplicativos acima da barra de guias, selecione o aplicativo cujo status de custo você quer ver.
4. Clique na guia **Custo** para ver o status e o horário da última sincronização.

</Accordion>

<div id="h_01M43Y9WQ8H8ANPDEGYCH0T0MF" />

<Accordion title="Tabela de status">

A tabela a seguir lista todos os status de integração de custos e o que cada um significa.

| Estado | Observações/ação necessária |
| --- | --- |
| Ativo | A integração está habilitada e conectada com sucesso ao canal de mídia. A AppsFlyer está extraindo dados de custo. |
| Conta de anunciante não ativada | A conta de anúncios conectada não está ativada para a coleta de dados de custo no canal de mídia. Entre em contato com o canal de mídia para habilitar o acesso à API da conta e, em seguida, reconecte a integração. |
| Erro geral | Ocorreu uma falha inesperada durante a obtenção. A AppsFlyer tenta novamente na próxima obtenção agendada. Se o status persistir, entre em contato com o suporte da AppsFlyer. |
| Credenciais inválidas | A AppsFlyer não consegue obter dados por meio da API porque as credenciais não são válidas. Reconecte-se usando as credenciais corretas. |
| Credenciais ausentes | Você não configurou as credenciais para esta integração. Adicione as credenciais necessárias em Configurações de custo ou na guia Custo do parceiro. |
| Nenhuma campanha ativa | Geralmente, a integração obtém o custo apenas das campanhas que têm conversões na AppsFlyer. Nesta obtenção, nenhuma campanha desse tipo foi encontrada durante o período selecionado. Nenhuma ação é necessária. A AppsFlyer informa que esta obtenção foi bem-sucedida. |
| Sem dados | A API do parceiro respondeu, mas não retornou dados. Isso geralmente acontece porque suas campanhas estão pausadas e não há dados para obter. Nenhuma ação é necessária, a menos que você espere que as campanhas estejam em execução. Se estiverem, revise a integração. |
| A API do parceiro não está respondendo | O servidor do parceiro integrado não está respondendo à AppsFlyer, ou a API do parceiro limitou a taxa da solicitação. A AppsFlyer tenta novamente na próxima obtenção agendada. Aguarde seis horas. Se o status persistir, entre em contato com o suporte da AppsFlyer. |
| A API do parceiro não está retornando dados para as informações fornecidas. Verifique a configuração | O canal de mídia não retornou dados apesar de haver campanhas ativas (campanhas com conversões na AppsFlyer), o que indica uma configuração incorreta no nível do canal de mídia. Reconecte a conta via OAuth e verifique se a conta de anúncio correta foi selecionada. |
| Aguardando sincronização | A conta ou o aplicativo ainda está sincronizando com a ad network. Aguarde a sincronização ser concluída. |
| Misto | Exibido apenas na página Configurações de custo > Canal de mídia, quando os aplicativos em uma integração têm status diferentes. Abra a página de integração para ver o status de cada aplicativo. Não exibido no dashboard de status. |

</Accordion>

<div id="cost-integration-and-agencies" />

## Integração de custos e agências

Se um anunciante usar uma agência para gerenciar suas campanhas, recomendados que a agência, e não o anunciante, integre-se com os parceiros relevantes. Caso contrário, se tanto o anunciante como a agência se integrarem a um parceiro usando as mesmas credenciais para o mesmo app, os dados de custo são duplicados.

Se um anunciante parar de trabalhar com uma agência, os dados de custo ainda serão extraídos se a agência ainda tiver custo configurado para o aplicativo. O anunciante deve pedir à agência para excluir a integração de custos dela para que esses dados deixem de ser extraídos.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Considerações |
| --- | --- |
| Agências | As agências não podem usar as configurações de custo para realizar integrações de custos em vários aplicativos ao mesmo tempo, mas podem usar a aba Custo no Partner Marketplace para fazer isso. |
| Aplicativos futuros herdam automaticamente o recurso de configurações de custo das configurações de custo em nível de conta | Atualmente indisponível. |
| Comportamento dos dados de custo quando o anunciante e a agência se conectam à mesma ad network | Se um anunciante ou uma agência se conectarem à integração de custo para a mesma conta de ad network (exemplo: Google Ads), os dados de custo são extraídos da conta que recebe a atribuição. Exemplo: o anunciante se conecta usando credenciais de anunciante, a agência se conecta usando credenciais de agência, e a atribuição é atribuída à conta da agência. Resultado: o ROI360 extrai dados de custo da conexão da agência, e a conexão do anunciante aparece como Sem dados. |
| Desconexão automática da integração de custos do Google | As integrações de custos que apresentam o status Sem dados ou Credenciais inválidas por mais de 365 dias consecutivos são desconectadas automaticamente. Atualmente, isso se aplica apenas às integrações de custos do Google. |
| Configuração da lista de IDs de anunciante do TikTok | Configure a lista de IDs de anunciante no nível da conta usando apenas IDs conectados ao usuário do TikTok na ad network. Os IDs de anunciante adicionados à lista que não estiverem alinhados com o usuário na ad network não retornam dados de custo. |

<div data-zendesk-anchors="overview=retorna-um-objeto-json-com-os-dados-brutos-de-consentimento-do-dma-conforme-enviados-do-anunciante-para-a-appsflyer h_01K9S0A1PRMX3VBGHTNQ8C5FJW=retorna-um-objeto-json-com-os-dados-brutos-de-consentimento-do-dma-conforme-enviados-do-anunciante-para-a-appsflyer h_01M43Y9WQ83AK0KTKB9XM8FGM6=importante create-a-new-api-cost-integration=criar-uma-nova-integra%C3%A7%C3%A3o-de-custos-de-api h_01K9S0A1PTQW9YJM3C4LKZRHFB=criar-uma-nova-integra%C3%A7%C3%A3o-de-custos-de-api h_01K9S0A1PVCXZ3NQ7MWFKTJRH8=additional-steps-specific-media-sources-only h_01M43Y9WQ8HNRN4ZKWRBT9QY9G=mapeie-aplicativos-para-nomes-de-pacote-ou-ids-de-bundle site-id-mapping=mapeie-aplicativos-para-ids-de-site h_01K3DGA6SKDTTPY8Q1JBTCTY7H=mapeie-aplicativos-para-ids-de-site h_01M43Y9WQ8V94HB74M6CAKC9PB=importante-1 h_01M43Y9WQ8P3XATJS0TBB27ZPQ=selecione-de-qual-conta-de-an%C3%BAncio-extrair-o-custo deleting-cost-integrations=editar-e-excluir-uma-integra%C3%A7%C3%A3o h_01K3DGA6SKF8ZA5M9AW6DA0V3J=editar-e-excluir-uma-integra%C3%A7%C3%A3o view-cost-api-status=ver-o-status-da-api-de-custo h_01K9S0A1PWRNK08ZQXCF5V3YTM=ver-o-status-da-api-de-custo h_01K9S0A1PXJQF2NVC9ZRMLK6HT=view-status-in-cost-settings h_01K9S0A1PYMBX4RQJZC8TNVK3F=view-status-in-cost-tab cost-integration-and-agencies=integra%C3%A7%C3%A3o-de-custos-e-ag%C3%AAncias h_01K9S0A1PZQXN4RTC7VWBLKM9H=integra%C3%A7%C3%A3o-de-custos-e-ag%C3%AAncias specification-and-limitation=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01K3DGA6SKVZ347ZDY599S0Y7Y=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
