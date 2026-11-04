---
title: Transmissão de dados brutos da Push API
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-08-19T00:04:26Z'
  id: 207034356
  locale: pt
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/pt/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** envie dados brutos de eventos de atribuição para seus endpoints do lado do servidor.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

<div id="push-api" />

## API de push

A Push API transmite dados brutos gerados pela atribuição da AppsFlyer e pela atribuição da SKAdNetwork na forma de mensagens para seus servidores. Você pode selecionar os tipos de mensagens e o conteúdo, além de definir os endpoints de destino.

Os tipos de mensagem disponíveis, a atualização dos dados e os campos dependem da estrutura de atribuição (AppsFlyer ou SKAN), conforme descrito nas seções a seguir.

<div id="appsflyer-attribution-messages" />

<Accordion title="Mensagens de atribuição da AppsFlyer">

Características da mensagem

| Características | Detalhes |
| --- | --- |
| Separação por tipo de mensagem | <ul><li>As mensagens podem ser separadas por endpoint (máximo de 6 endpoints por aplicativo) ou você pode determinar o tipo de mensagem, a depender do valor dos campos listados:<ul><li>nome\_do\_evento</li><li>tipo\_de\_conversão</li><li>campaign\_type</li></ul></li><li>Os valores dos campos, por tipo de mensagem, estão indicados na tabela a seguir.</li></ul>**Exemplo:**<br /><br />Uma mensagem contém o seguinte:<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Use a tabela para determinar se esse evento é o evento de instalação de um usuário orgânico. |
| Atualização dos dados | As mensagens são enviadas logo após o evento ser registrado na plataforma da AppsFlyer. Isso geralmente ocorre em poucos minutos. |
| Conteúdo da mensagem (campos) | <ul><li>As mensagens têm uma estrutura `key:value`.</li><li>Veja os campos disponíveis de <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> na atribuição da AppsFlyer.</li><li>Cada chave representa um campo de dados brutos. Veja a <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#data-fields-dictionary">descrição dos campos de dados brutos na AppsFlyer</Anchor>.</li><li>Chaves em branco ou nulas não são enviadas.</li><li>O exemplo contém campos nulos e vazios. Postbacks reais não têm campos vazios ou nulos. O exemplo fornecido tem um formato JSON.<ul><li>[/docs/ctv-pc-and-console-platform-attribution-concepts](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[com o Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Formato dos campos de carimbo de data/hora | <ul><li>Carimbos de data/hora UTC: `yyyy-mm-dd hh:mm:ss.sss`. Por exemplo, aparece como `2019-09-17 00:09:00.123`. Um evento ocorreu às 18:00 no horário de Tóquio. A hora do evento é convertida em UTC, que é 09:00. A hora registrada é a hora em UTC.</li><li>Carimbos de data/hora do fuso horário selecionado (específico do aplicativo): `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Por exemplo `2019-09-17 18:00:16.000+0900`. Um evento ocorreu às 18:00 no horário de Tóquio. O horário do evento mostrado é registrado como 18:00+09:00. 09:00 é o fuso horário de Tóquio.</li></ul> |

<div id="available-message-types" />

#### Tipos de mensagens disponíveis

<table><thead><tr><th>Contexto de atribuição</th><th>Tipo de mensagem</th><th>campo conversion_type</th><th>campo campaign_type</th><th>campo event_name</th><th>campo event_type</th></tr></thead><tbody><tr><td>Aquisição de usuários</td><td>Instalação\*</td><td>instalação</td><td><p>Não orgânico: UA</p><p>Orgânico: orgânico</p></td><td>instalação</td><td><ul><li>instalação</li><li>organic-install</li></ul></td></tr><tr><td>Aquisição de usuários </td><td>Eventos in-app de instalação</td><td><span>instalação</span></td><td><p>Não orgânico: UA</p><p>Orgânico: orgânico</p></td><td>Nomes de eventos definidos pelo anunciante</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>Redirecionamento</td><td>Reengajamento</td><td>re-engajamento</td><td>retargeting</td><td>re-engajamento</td><td>re-attribution</td></tr><tr><td>Redirecionamento </td><td>Eventos in-app de reengajamento</td><td>re-engajamento</td><td>retargeting</td><td>Nomes de eventos definidos pelo anunciante</td><td>re-engagement-in-app-event</td></tr><tr><td>Redirecionamento </td><td>Re-atribuição </td><td>reinstall</td><td>retargeting</td><td>re-attribution</td><td>re-attribution</td></tr><tr><td>Aquisição de usuários </td><td>Reinstalação</td><td>reinstall</td><td><p>Não orgânico: UA</p><p>Orgânico: orgânico</p></td><td>reinstall</td><td><ul><li>reinstall</li><li>organic-reinstall</li></ul></td></tr><tr><td>Redirecionamento</td><td>Eventos in-app de reatribuição</td><td>reinstall</td><td>retargeting</td><td>Nomes de eventos definidos pelo anunciante</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">\* Algumas instalações relacionadas à atribuição de view-through são atribuídas a uma <a href="./about-raw-data-identifier-restrictions" target="_blank">fonte de mídia restrita.</a> </td></tr></tbody></table>

<div id="unique-fields" />

#### Campos exclusivos

<table><thead><tr><th>Nome exibido</th><th>Nome na Push API</th></tr></thead><tbody><tr><td>Moeda selecionada\*</td><td>moeda_selecionada</td></tr><tr><td>Receita na moeda selecionada</td><td>receita na<br/>moeda selecionada</td></tr><tr><td>Custo na moeda selecionada</td><td>custo na<br/>moeda selecionada</td></tr><tr><td>Fuso horário selecionado para o download do dispositivo</td><td>device_download_time_selected_timezone</td></tr><tr><td>Fuso horário selecionado por hora de atribuição do toque</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Hora de instalação no fuso horário selecionado</td><td>hora da instalação no<br/>fuso horário selecionado</td></tr><tr><td>Hora do evento no fuso horário selecionado</td><td>hora do evento no<br/>fuso horário selecionado</td></tr><tr><td>Fuso horário selecionado(\*)</td><td>selected_timezone</td></tr><tr><td colspan="2">\* Essa é a configuração no nível do aplicativo em vigor no momento em que a mensagem da API é enviada.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Mensagens de atribuição da SKAN">

Essa seção descreve as mensagens (tipos de relatório) disponíveis para SKAN e como identificá-las. Leia o conteúdo e, em seguida, [configure o endpoint de atribuição da SKAN.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

Leitura adicional: <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">campos de dados brutos da SKAN</Anchor>. As mensagens da Push API têm estrutura e campos equivalentes.

Características da mensagem:

| Características | Detalhes |
| --- | --- |
| Separação por tipo de mensagem | <ul><li>Todas as mensagens são enviadas para 1 endpoint definido por você.</li><li>Para determinar o tipo de mensagem, use o campo event\_type.<br />Atenção: usando o campo event\_type, você também pode determinar o campo event\_name e o campo skad\_redownload.</li><li>Os valores do campo event\_type estão indicados na [tabela a seguir](/docs/push-api-streaming-raw-data#tipos-de-mensagens-para-atribuição-da-skan).</li></ul>Exemplo:<br /><br />Uma mensagem contém o seguinte:<ul><li>event\_type: skad-re-download</li></ul>A partir disso, podemos determinar que:<ul><li>Esse é um evento de re-download</li><li>event\_name: install</li><li>skad\_redownload: true</li></ul> |
| Atualização dos dados | <ul><li>Instalações, redownloads e eventos in-app:<ul><li>Processados diariamente</li><li>Enviados para seu endpoint no dia seguinte ao recebimento do postback do iOS pela AppsFlyer</li><li>Espere receber mensagens de eventos entre 08:00 e 11:00 UTC (a hora exata varia)</li><li>Exemplo: postbacks recebidos na segunda-feira são enviados a partir de terça às 08:00 UTC</li></ul></li><li>Postbacks do iOS e cópia de postbacks: As mensagens são enviadas logo após chegarem à AppsFlyer</li></ul> |
| Exemplos de mensagens | A planilha contém exemplos de mensagens. O exemplo fornecido tem um formato JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Exemplos de mensagens SKAN</Anchor>. |

<div id="message-types-for-skan-attribution" />

#### Tipos de mensagens para atribuição da SKAN

| Tipo de mensagem | campo event\_name | campo skad\_redownload | campo event\_type |
| --- | --- | --- | --- |
| Instalações | instalação | <ul><li>Valores possíveis: false, blank, null.</li><li>Se o campo não estiver na mensagem, considere o valor como false.</li></ul> | skad-install |
| Redownloads | instalação | True | skad-re-download |
| Eventos in-app | O nome do evento definido pelo anunciante | O nome do evento definido pelo anunciante | skad-in-app-event |
| Postbacks do iOS | Nunca disponíveis nessa mensagem | Às vezes disponíveis | skad-postback |
| <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Cópia de postbacks</Anchor> | Nunca disponível nessa mensagem | Às vezes disponível | skad-postback-copy |

</Accordion>

<div id="set-up-push-api-endpoints" />

## Configurar endpoints da Push API

<div id="caution" />

> ❗️ **Atenção**
>
> Você não deve usar a Push API para enviar dados atribuídos da AppsFlyer a terceiros pelos seguintes motivos:
>
> * Você pode violar regulamentos de privacidade, como a CCPA, se o usuário optar por não enviar seus dados a terceiros.
> * Algumas fontes de mídia restringem a forma como os dados a nível do usuário fornecidos por elas são usados, compartilhados com terceiros ou ambos. Certifique-se de cumprir os termos de uso da fonte de mídia.
>   Por exemplo, [X Ads,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/) [Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Atenção:  isso não se aplica aos dados SKAN. Use a Push API para enviar dados SKAN para endpoints de terceiros.

Para configurar a Push API, preencha a lista de ações abaixo.

<div id="push-api-setup-checklist" />

#### Checklist de configuração da Push API

<table><thead><tr><th>Etapa </th><th>Atribuição da AppsFlyer</th><th>Atribuição na SKAdNetwork </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>Se você já possui um endpoint ativo da Push API, pode pular essa etapa. </p><p>Complete os <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">requisitos do lado do servidor</a>.</p></td></tr><tr><td>2</td><td>Para atribuição da AppsFlyer, planeje as configurações do endpoint usando a <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">checklist da Push API.</a> </td><td>Não aplicável</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Configure o endpoint de atribuição da AppsFlyer</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Configure o endpoint de atribuição da SKAdNetwork</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Requisitos do lado do servidor (seu servidor)">

Verifique se o seu servidor cumpre com os requisitos listados aqui:

<div id="server-side-requirements" />

#### Requisitos do lado do servidor

| URL do endpoint | <ul><li>Nome de domínio válido</li><li>Número máximo de endpoints exclusivos por aplicativo:<ul><li>AppsFlyer: 6 pontos finais</li><li>SKAdNetwork: 3 pontos finais</li></ul></li></ul> |
| --- | --- |
| Código de retorno do endpoint | Ao receber uma mensagem, seu endpoint deve retornar um código de status HTTP 200. |
| Incluir servidores da AppsFlyer na lista de permissões | Inclua os <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-server-ip-address-ranges-allowlisting">endereços IP</Anchor> do servidor da AppsFlyer na lista de permissões dos seus sistemas de firewall e segurança para garantir a comunicação com o endpoint. |
| Versões TLS | <ul><li>TLS 1.1</li><li>TLS 1.2+ Veja as <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-https-ssl-encryption-policy-support#mensagens-de-saída-appsflyer-como-cliente">cifras compatíveis</Anchor></li></ul> |
| Portas | Portas: 80, 443 |

**Atenção**! Um mecanismo de tempo limite, com duração de 4 segundos, é usado. Se a AppsFlyer não receber uma mensagem de OK durante esse período, isso será considerado uma falha no envio da mensagem.

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Checklist para o planejamento da Push API para atribuição na AppsFlyer">

* Use essa checklist para planejar suas configurações de endpoint de atribuição na AppsFlyer. Os números na figura correspondem aos números de linha no checklist.
* Essa seção não é relevante para a atribuição na SKAdNetwork. Consulte o artigo [configurar a atribuição da SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Ponto final**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

<div id="endpoint-planning-table" />

#### Tabela de planejamento do endpoint

| Não. | Configuração | Detalhes | Use essa coluna para registrar suas configurações planejadas |
| --- | --- | --- | --- |
| 1 | Método | POST ou GET |  |
| 2 | URL do endpoint | - |  |
| 3 | Tipos de mensagem de evento | <ul><li>Selecione pelo menos um tipo de mensagem de evento.</li><li>Para selecionar mensagens de eventos in-app, é necessário gravar um evento no aplicativo. Até você fazer isso, não poderá selecionar mensagens de evento in-app.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Campos</li><li>A lista de campos é comum a todos os tipos de mensagens</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>Aviso**<br />Ao selecionar tudo, você não inclui automaticamente os campos de mensagem que ainda serão adicionados. Para incluir novos campos, você precisa atualizar a seleção manualmente.<br /><br /><br /><br />Selecione os campos obrigatórios.<ul><li>Os campos mais comuns são pré-selecionados por padrão.</li><li>Não enviamos campos vazios/nulos</li></ul> |  |
| 5 | Tipo de evento in-app | Filtre por evento in-app para reduzir o tráfego enviado ao seu endpoint.<ul><li>Selecione um ou mais eventos ou todos os eventos in-app. Atenção! Se o evento não for exibido na lista, procure por ele.</li><li>Você só pode selecionar um evento in-app após ele ter sido gravado pelo menos uma vez. Se necessário, use o <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> para acionar o evento.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Configure o endpoint de atribuição da AppsFlyer">

Todos os membros da equipe com permissões para acessar a API podem fazer alterações nas configurações da Push API. Outros usuários da conta podem visualizar as configurações.

<div id="add-an-appsflyer-attribution-endpoint" />

#### Adicione um endpoint de atribuição da AppsFlyer

1. Na AppsFlyer, na barra lateral, abra **Exportar > Acesso à API. Vá até a seção da Push API.**
2. Clique em **Adicionar endpoint.**   
   **Atenção:** Você pode definir de 1 a 3 endpoints da SKAdNetwork por aplicativo.
3. Selecione um método HTTP: **POST** ou **GET**
4. Insira a **URL** do***Endpoint**.*  Se você receber a mensagem "*essa URL não é segura*", entre em contato com o suporte da AppsFlyer.
5. Selecione um ou mais tipos de evento. **Atenção**: se as mensagens de evento in-app estiverem desativadas, isso significa que nenhum evento in-app foi gravado até o momento.
6. Selecione os campos para preencher a mensagem da Push API. Atenção:
   * campos obrigatórios sempre enviados: App ID, nome do evento, horário do evento, IDFA (iOS) ou Advertising ID (Android)
   * Use os controles representados na figura a seguir para selecionar campos opcionais. [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * Os campos mais comuns são pré-selecionados por padrão. Você pode cancelar as seleções.
     * Selecione os campos opcionais conforme necessário.
     * Use **Limpar tudo** para limpar todos os campos opcionais.
     * Não enviamos campos vazios/nulos e a chave associada. Leve isso em conta ao planejar seus processos de importação/análise.
7. Selecione um ou mais (até 52 eventos) ou **Todos** os eventos in-app.
   * A lista é preenchida por tipos de eventos que já foram gravados. Se estiver faltando um evento, envie um evento desse tipo usando um dispositivo de teste.
8. Clique em **Salvar**.  
   A Push API agora está ativa. Os dados de conversão são enviados para o endpoint.
9. Teste o endpoint usando o procedimento a seguir.

<div id="test-the-endpoint" />

#### Para testar o endpoint:

1. Clique **Enviar teste.**   
   Uma mensagem de resultado do teste é exibida abaixo do botão **Enviar teste**.   
   Uma mensagem de teste é enviada para o endpoint. Se o teste falhar, certifique-se de que você incluiu <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-server-ip-address-ranges-allowlisting">os endereços de IP da AppsFlyer na lista de permissões</Anchor>.   
   **Atenção**! Um mecanismo de tempo limite, com duração de 2 segundos, é usado. Se a AppsFlyer não receber uma mensagem de OK durante esse período, isso será considerado uma falha no envio da mensagem.
2. Verifique se o endpoint recebeu a mensagem de teste.  
   [Veja uma cópia da mensagem enviada.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Configure o endpoint de atribuição da SKAdNetwork">

Todos os membros da equipe com permissões para acessar a API podem fazer alterações nas configurações da Push API. Outros usuários da conta podem visualizar as configurações.

**Para adicionar um endpoint da Push API da SKAdNetwork:**

1. Na AppsFlyer, na barra lateral, abra **Exportar > Acesso à API. Vá até a seção da Push API.**
2. Selecione **SKAdNetwork** como a entidade de atribuição.
3. Clique em **Adicionar Endpoint.**   
   **Observação**: Você pode definir de 1 a 3 endpoints da SKAdNetwork por aplicativo.
4. Selecione um método HTTP: **POST** ou **GET**
5. Insira a **URL** do Endpoint/strong>.  Se você receber a mensagem "*essa URL não é segura*", entre em contato com o suporte da AppsFlyer.
6. Não enviamos campos vazios/nulos e a chave associada. Leve isso em conta ao planejar seus processos de importação/análise.
7. Clique em **Salvar**.  
   A Push API agora está ativa. Os dados são enviados para o endpoint.

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="Configurar token de autenticação">

Usando o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">token de autenticação da Push API</Anchor>, os clientes podem integrar e proteger suas mensagens da Push-API de forma contínua, adicionando um header de autorização personalizável com um token solicitado.  
Você pode personalizar um header de autorização que será enviado com suas mensagens da Push-API, definindo o nome do token e o valor associado a cada app ID. Isso garante que suas mensagens não sejam apenas seguras, mas também adaptadas às suas necessidades específicas.

</Accordion>

<div id="additional-proceduresmanaging-endpoints" />

## Procedimentos adicionais — gerenciando endpoints

Todos os membros da equipe com permissões para acessar a API podem fazer alterações nas configurações da Push API. Outros usuários da conta podem visualizar as configurações.

<div id="change-an-endpoint" />

<Accordion title="Alterar um endpoint">

**Para modificar as configurações do endpoint:**

1. Na AppsFlyer, na barra lateral, abra **Exportar > Acesso à API. Vá até a seção da Push API.**
2. Localize o endpoint a ser modificado.
3. Faça as alterações.
4. Clique em **Salvar**.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Excluir um endpoint">

**Para excluir um endpoint**:

1. Na AppsFlyer, na barra lateral, abra **Exportar > Acesso à API. Role para baixo até a seção "Acesso à Push API".**
2. Clique em **excluir endpoint**.
3. Clique em **salvar.**  
   O endpoint é removido.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Solução de problemas, características e limitações

<div id="test-message-fails" />

<Accordion title="Falha nas mensagens de teste">

Se você não receber a mensagem de teste e restringir o acesso aos seus servidores por endereço IP: certifique-se de que você <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-server-ip-address-ranges-allowlisting">incluiu todos os endereços IP da AppsFlyer na lista de permissões</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Duplicar eventos in-app de retargeting">

Os eventos de retargeting in-app são duplicados quando um evento de compra ocorre como parte da campanha de retargeting durante uma janela de reengajamento de UA. Isso é feito para atribuir receita à fonte de mídia de UA e à fonte de mídia de retargeting.

Você só receberá eventos duplicados se ambos estiverem ativos:

* Eventos in-app à instalação
* Eventos in-app relacionados ao retargeting

<Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">Identificar e desduplicar eventos in-app</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="A seleção de mensagens de eventos in-app está desativada">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* Mensagens de eventos in-app só podem ser selecionadas após a gravação de um evento in-app.
* Use um dispositivo de teste para gerar um evento in-app ou use a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor> para fazer isso manualmente.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Mensagens de push e CloudFront ausentes">

Você está usando Amazon CloudFront como seu endpoint? Nesse caso, verifique se o CloudFront está rejeitando a mensagem com o código 421. Se sim, consulte o artigo <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Como o CloudFront atende solicitações de HTTPS</Anchor>.

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Mensagens de erro de endpoint">

**Sintoma:** a mensagem *essa URL não é segura* é exibida quando você configura a URL do endpoint.

**Ação necessária**: entre em contato com o suporte da AppsFlyer, inclua o App ID, a URL do endpoint e uma captura de tela da mensagem de erro.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Características e limitações">

| **Caraterística** | Observações |
| --- | --- |
| <span id="ad-networks"></span>Redes de anúncios | Disponível |
| <span id="agencies"></span>Agências | Disponível |
| <span id="appspecific-time-zone"></span>Fuso horário específico do aplicativo | Com suporte. |
| <span id="appspecific-currency"></span>Moeda específica do aplicativo | Com suporte. |
| <span id="size-limitations"></span>Limitações de tamanho | Não aplicável |
| <span id="organic"></span>Orgânico | Sim |
| <span id="nonorganic"></span>Não orgânico | Sim |
| <span id="data-freshness"></span>Atualização dos dados | Contínuo |
| <span id="historical-data"></span>Histórico de dados | Indisponível. Se faltarem dados, use a Pull API para obter os dados. No caso da SKAN, você pode obter alguns históricos de dados por meio do Data Locker (limitado pela janela de disponibilidade do Data Locker). |
| <span id="account-owneruser-access"></span>Acesso do proprietário da conta/usuário | Somente o **proprietário da conta** da AppsFlyer pode fazer alterações nas configurações da Push API.<ul><li>Cada conta da AppsFlyer tem **apenas um** proprietário da conta. Esse é o primeiro usuário da AppsFlyer (criado no momento em que a conta foi aberta).</li></ul>Outros usuários de conta podem visualizar as configurações da Push API, mas não podem fazer mudanças. |
| <span id="authentication-token-in-test-messages"></span>Token de autenticação em mensagens de teste | Os headers de [mensagem de teste](#para-testar-o-endpoint) não incluem o token de autenticação. |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="Posso incluir headers personalizados com a solicitação da Push API?">

Não. A Push API é compatível com o uso do header `Authorization` apenas para tokens de autenticação. Headers personalizados adicionais — como `consumer-key` — não são **compatíveis**.

Se você precisar enviar parâmetros extras, inclua-os na URL. Por exemplo:

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Comparando ferramentas de envio de dados brutos</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Configure a Push API usando uma API</Anchor>

<div data-zendesk-anchors="push-api=api-de-push 01H89PJFBPXVKJGGH18CJBJ41W=api-de-push 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=tipos-de-mensagens-dispon%C3%ADveis 01H89PJFBP9DEX520BDGC5PANQ=tipos-de-mensagens-dispon%C3%ADveis unique-fields=campos-exclusivos 01H89PJFBPBK09Q7CRPMM4G7PJ=campos-exclusivos 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=tipos-de-mensagens-para-atribui%C3%A7%C3%A3o-da-skan 01H89PJFBQBFCK5QVWW2X09H28=tipos-de-mensagens-para-atribui%C3%A7%C3%A3o-da-skan set-up-push-api-endpoints=configurar-endpoints-da-push-api 01H89PJFBQZ2FW3ST5V4FW91GS=configurar-endpoints-da-push-api 01H89PJFBQ6WP7ERP0DJ69QZ1G=aten%C3%A7%C3%A3o push-api-setup-checklist=checklist-de-configura%C3%A7%C3%A3o-da-push-api 01H89PJFBQ625A7G3QT5HQJXMW=checklist-de-configura%C3%A7%C3%A3o-da-push-api 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=requisitos-do-lado-do-servidor 01H89PJFBQ2BC5GHX403RD2RAT=requisitos-do-lado-do-servidor 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=tabela-de-planejamento-do-endpoint 01H89PJFBQJXWWPQDKZ387VYX3=tabela-de-planejamento-do-endpoint 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=adicione-um-endpoint-de-atribui%C3%A7%C3%A3o-da-appsflyer h_01JFSS65G8GTZNMY257QCV922M=adicione-um-endpoint-de-atribui%C3%A7%C3%A3o-da-appsflyer test-the-endopoint=para-testar-o-endpoint h_01JFSS6YVP1WFWXSZ7HP7GTDA2=para-testar-o-endpoint 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=procedimentos-adicionais--gerenciando-endpoints 01H89PJFBQ7WV3NM7JR5Z9QEFB=procedimentos-adicionais--gerenciando-endpoints 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01H89PJFBQJDGT1FVHKG9DETHJ=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=veja-tamb%C3%A9m" />
