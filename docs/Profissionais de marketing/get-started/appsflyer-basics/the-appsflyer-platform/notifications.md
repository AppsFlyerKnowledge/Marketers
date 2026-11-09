---
title: Notificações
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-08-19T00:10:18Z'
  id: 33732395637905
  locale: pt
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/pt/articles/33732395637905
---
> **Resumo:** gerencie notificações importantes da sua conta na AppsFlyer.

Você pode receber notificações por e-mail quando certos eventos ocorrerem na sua conta. Nas suas **preferências de notificação**, você pode optar por receber ou não essas notificações.

<div id="accessing-and-configuring-notification-preferences" />

## Configurar preferências de notificação

<div id="to-access-notifications" />

### Para acessar notificações

* Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) > **Notificações por e-mail.**
* No ícone de sininho dentro da plataforma, clique em > **Ícone de configurações.**

<div id="configuring-notifications" />

### Configurando notificações

Para receber um aviso, ative-o na lista de notificações disponíveis.

Para parar de recebê-lo, desative-o.

Atenção: Algumas notificações estão disponíveis apenas por e-mail. A aba de notificação apenas por e-mail mostra as [configurações](/docs/notifications#notificações-somente-por-e-mail) de notificação.

<div id="what-notifications-can-i-receive" />

## Quais notificações posso receber?

As seguintes opções estão disponíveis:

* Gestão da conta e plano
* Problemas transacionais ou de cobrança
* Alertas relacionados à privacidade
* Insights e configurações
* Recursos colaborativos
* Recursos de IA

Atenção: Algumas notificações estão disponíveis apenas por e-mail. Mais informações podem ser encontradas [aqui.](/docs/notifications#email-notification)

Para receber uma notificação específica, ela deve estar:

* **Disponível na conta da AppsFlyer da sua empresa.** Se uma notificação não estiver disponível na conta da sua empresa, a opção para ativá-la não é mostrada.
  * Por exemplo, se a sua empresa não assina a Push API, essa notificação não aparece como uma opção.
* Disponível para você, com base nas suas permissões de usuário. Se uma notificação estiver relacionada a uma ferramenta ou recurso ao qual você não tem permissões de uso, a opção fica desativada.

  *  Por exemplo, se você não tiver permissões para adicionar ou editar parceiros integrados, a opção de ativar ou desativar uma notificação relacionada à configuração de parceiros integrados fica desativada.

<div id="when-will-i-receive-notifications" />

## Quando vou receber as notificações?

Se você escolheu receber uma notificação específica, você receberá um e-mail quando o evento de trigger para essa notificação ocorrer, mas **só quando** esse evento acontecer nos **aplicativos e fontes de mídia** aos quais você possui acesso.

<div id="example" />

<Accordion title="Exemplo">

Considere o seguinte cenário:

* Sua empresa tem 3 aplicativos na AppsFlyer: Aplicativo A, Aplicativo B e Aplicativo C.
* Cada aplicativo tem integrações ativas com 2 fontes de mídia (parceiros integrados): Google Ads e TikTok.
* Seu usuário na AppsFlyer tem permissões para:
  * Adicionar/editar parceiros integrados
  * Acessar dados do Aplicativo C
  * Acessar dados do Google Ads
* Você optou por receber uma notificação sempre que houver uma alteração nas configurações de parceiros integrados.

Resultado:

* Você **não** receberá notificações quando houver alterações na configuração de um parceiro integrado para os aplicativos A e B.
* Você **não** receberá notificações quando houver alterações de configuração do TikTok para o aplicativo C.
* Você **receberá** notificações quando houver alterações na configuração do Google Ads para o aplicativo C.

</Accordion>

<div id="where-will-i-receive-notifications" />

## Quando vou receber as notificações?

As notificações podem ser recebidas no [ícone de sininho](/docs/notifications#bell-notification) [e-mail](/docs/notifications#email-notification) ou [Slack](/docs/notifications#slack-notification). 

<div id="bell-notification" />

<Accordion title="Notificação no sininho">

O ícone de notificação dde sininho fica na barra superior à esquerda do seu menu de conta (menu suspenso do endereço de e-mail).

Ao clicar no ícone de engrenagem, você é levado às [preferências de notificação](/docs/notifications#configurar-preferências-de-notificação).

</Accordion>

<div id="email-notification" />

<Accordion title="Notificações por e-mail">

As notificações são enviadas para o e-mail associado à sua conta da AppsFlyer.

Algumas notificações estão disponíveis apenas por e-mail. Essas configurações de notificação podem ser encontradas na aba **Notificações somente por e-mail**.

<div id="note" />

> 📘 **Atenção**
>
> Todos os e-mails de notificação da AppsFlyer são enviados por [notifications@appsflyer.com](mailto:notifications@appsflyer.com)

<div id="email-only-notifications" />

#### Notificações somente por e-mail

A tabela a seguir lista as notificações disponíveis e os eventos que as acionam:

| Notificação | Evento de trigger |
| --- | --- |
| Alterações na configuração de parceiros integrados | <ul><li>Um novo parceiro integrado foi ativado</li><li>Um parceiro integrado existente foi desativado</li><li>Uma alteração é feita nas configurações de um parceiro integrado existente</li></ul> |
| Falhas na Push API | 5% ou mais das mensagens da Push API de um aplicativo falham dentro de um período de 12 horas |
| Falhas de conexão do Audiences | Há falhas de conexão com parceiros que exigem a sua atenção. |
| Integrações suspensas para receita de anúncios | Uma integração de receita de anúncios foi suspensa após exibir um status de aviso por mais de 30 dias. |
| Falha nos dados de receita de anúncios | Uma integração de receita de anúncios não está recebendo dados |
| Alterações de configuração de custo de parceiro integrado | Um membro da equipe alterou as configurações da integração de custos |
| Falhas na conexão com a SKAN | Há um problema com a sua integração da SKAN no Google Ads ou Meta que exige a sua atenção. Pode ser necessário excluir a integração atual e fazer o login novamente. |

</Accordion>

<div id="slack-notification" />

<Accordion title="Notificações por Slack">

**Configurar notificações por Slack**

Para configurar as notificações por Slack, o Slack precisa estar conectado:

1. Na página de preferências de notificação, clique no botão de **Integrações** no canto superior direito da página.
2. Clique em **Conectar**.
3. Revise e aprove o pedido de permissões.
   1. **Se você é o administrador do Slack**:
      1. No Slack, clique no espaço de trabalho do Slack.  
         <Image align="center" alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />
         Atenção: Certifique-se de que o espaço de trabalho mostrado é o que você deseja conectar.
      2. Vá para **Ferramentas e configurações** -> **Gerenciar aplicativos**
      3. No painel de **Admin**, selecione **Solicitações**.
      4. Na aba **Necessita revisão**, clique nos três pontos ao lado do pedido do aplicativo da AppsFlyer.
      5. Clique em **Aprovar** e depois aprove o seguinte pop-up.
      6. Volte para a **página de integração da AppsFlyer** e clique no botão **Permitir**.
   2. **Se você não é o administrador do Slack**:
      1. Solicite a permissão ao seu administrador do Slack para conectar o Slack à AppsFlyer.
      2. O administrador do Slack **deve** realizar todos os passos acima. Enquanto isso:
      3. O conector do Slack mostra o status pendente.
      4. Quando o seu administrador do Slack aprovar a conexão, clique em **Conectar** para iniciar a integração e passar do status de pendente para conectado.

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=configurar-prefer%C3%AAncias-de-notifica%C3%A7%C3%A3o h_01HKA254W4XDVNP816N46N59ZV=configurar-prefer%C3%AAncias-de-notifica%C3%A7%C3%A3o to-access-notifications=para-acessar-notifica%C3%A7%C3%B5es h_01JQ66J4YSCSX7ZGG81XHGJ3MM=para-acessar-notifica%C3%A7%C3%B5es configuring-notifications=configurando-notifica%C3%A7%C3%B5es h_01HKA254W497H0SKTZ33CVSA4P=configurando-notifica%C3%A7%C3%B5es what-notifications-can-i-receive=quais-notifica%C3%A7%C3%B5es-posso-receber h_01HKA254W47XRG1D3HZ6VBZ2BH=quais-notifica%C3%A7%C3%B5es-posso-receber when-will-i-receive-notifications=quando-vou-receber-as-notifica%C3%A7%C3%B5es h_01JQ66BX52MV5WQ7RXH6SY3QHK=quando-vou-receber-as-notifica%C3%A7%C3%B5es h_01JQ6EYTZ13FHYERT48K3J25SV=example where-will-i-receive-notifications=quando-vou-receber-as-notifica%C3%A7%C3%B5es-1 h_01HKA254W4Z95M335V7KWAJA6N=quando-vou-receber-as-notifica%C3%A7%C3%B5es-1 h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=aten%C3%A7%C3%A3o emailonly-notifications=notifica%C3%A7%C3%B5es-somente-por-e-mail h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=notifica%C3%A7%C3%B5es-somente-por-e-mail h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />
