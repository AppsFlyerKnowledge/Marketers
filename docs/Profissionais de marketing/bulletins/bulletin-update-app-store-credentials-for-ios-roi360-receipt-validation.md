---
title: >-
  Boletim: Atualizar credenciais da App Store para validação de recibos do iOS
  no ROI360
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-08-28T09:24:00Z'
  edited_at: '2026-10-20T03:54:49Z'
  id: 27880822483985
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/27880822483985
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | A AppsFlyer fará a transição do fluxo de validação do ROI360 no iOS para as novas APIs de validação de compras in-app da Apple, uma vez que a API atual foi desativada pela Apple.  <br />Para garantir que os seus dados de receita do iOS sejam validados com precisão e em tempo real, você precisará atualizar suas credenciais da App Store na plataforma da AppsFlyer.  <br />Se o seu aplicativo ainda usa a versão 1 para Apple Server Notifications, você também terá que mudar para as notificações da versão 2 antes de atualizar as credenciais. |
| **Data da atualização** | 02/04/2025 |
| **O que você precisa saber** | Essa mudança afeta aplicativos que usam o ROI360 para validação de receita de compras in-app e assinaturas no iOS.<br />Ao atualizar para o novo fluxo, você se beneficiará de:<ul><li>Validação em tempo real aprimorada com a Apple Store usando novos endpoints da Apple.</li><li>Nenhuma alteração na estrutura ou parâmetros de eventos in-app.</li><li>Resultados de validação atualizados nas respostas do Purchase SDK Connector da AppsFlyer, incluindo um novo código `store_status` para validações que falharam.</li><li>Nenhuma alteração na sua implementação do SDK é necessária.</li></ul>**Atenção:** a validação de recibos baseada em StoreKit 2 é compatível apenas com as novas credenciais da App Store. Certifique-se de concluir a atualização se seu aplicativo usar o StoreKit 2 para garantir uma validação contínua.<br /><br />A Apple pode desativar APIs antigas a qualquer momento, por isso recomendamos que você atualize suas credenciais para se antecipar a quaisquer possíveis interrupções. |
| **O que você precisa fazer** | Para completar a configuração:<ol><li>Gere a In-App Purchase Key na App Store Connect.</li><li>Carregue a nova chave na seção de configurações de receita da plataforma AppsFlyer.</li></ol>Se o seu aplicativo estiver usando a versão 1 para Apple Server Notifications, você deve mudar para a versão 2 antes de atualizar suas credenciais. Se isso for válido para o seu aplicativo, você verá uma mensagem na página de configurações de receita.<br /><br />Siga as instruções abaixo:<ul><li>[Atualize as credenciais da App Store para validação de recibos do ROI360 no iOS](#obter-credenciais-ios)</li><li>[Configure a versão 2 para Apple Server Notifications](#enviar-notifica%C3%A7%C3%B5es-da-app-store-diretamente-para-a-appsflyer)</li></ul> |

<div id="send-app-store-notifications-directly-to-appsflyer" />

<Accordion title="Configure a versão 2 para Apple Server Notifications">

Se o seu aplicativo usava a versão 1, você deve mudar para a versão 2 na App Store Connect antes de atualizar suas credenciais de validação. (Se isso for válido para o seu aplicativo, você verá uma mensagem na página de **configurações de receita**.)

**Para configurar a versão 2 para Apple Server Notifications:**

1. Na **App Store Connect**, em **App Information**, vá até **App Store Server Notifications.**

   <Image alt="image (24).png" src="https://files.readme.io/8e9c92cdf87303b58a6b604640b4f7adb3cf56c03e57df053e9d486b89345547-33812520143505.png" width="2009px" />
2. Em **Production Server URL**, clique em **Edit**.
3. Não mude a URL na caixa **Production Server URL**.

   <Image alt="image (25).png" src="https://files.readme.io/fc7737793f2e7982e3e92d30dec45d7def98ef8ec6c3186ebbdf32a78f217a3d-33812683240977.png" width="1182px" />
4. Em **Notification Version**, selecione **Version 2 Notifications**.
5. Clique em **Save**.
6. Em **App Store Server Notifications**, clique em **Edit** para **Sandbox Server URL**.
7. Repita as etapas 3-5.

</Accordion>

<div id="get-ios-credentials" />

<Accordion title="Atualizar as credenciais da App Store para validação de recibos do ROI360 no iOS">

As credenciais necessárias para a integração da In-App Purchase API no iOS são:

* In-App Purchase  key
* ID da chave
* Issuer ID

**Antes de começar**:

* Para atualizar as chaves, as etapas devem ser realizadas tanto na App Store Connect quanto na AppsFlyer. Durante a configuração, mantenha as abas da App Store Connect e da AppsFlyer abertas.
* Você precisa de permissões de administrador para configurar chaves na AppsFlyer.

Para atualizar as credenciais do iOS:

1. Na App Store Connect, vá para **Users and Access** <Image alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" width="486px" />
2. Vá para **Users and Access** > **Integrations** e, na lista **Keys**, selecione **In-App Purchase**.  
   <Image alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" width="532px" />
3. Clique + para gerar uma nova In-App Purchase key.  
   <Image alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" width="384px" />
4. Digite um nome para sua chave de API.
5. Clique em **Generate**.
6. Clique em **Download In-App Purchase Key** ao lado da chave que você acabou de gerar para baixá-la. **Atenção:** você só pode baixar a chave uma vez.
7. **Na AppsFlyer, no menu lateral, selecione** configurações **>** configurações de receita.
8. Selecione seu aplicativo na lista.
9. Na aba **compras e assinaturas**, clique em **atualizar chaves**. <Image alt="" src="https://files.readme.io/edcb9ef1c24f58b911792e924ca69173c487261e2ef35cf1a21270251c50e586-33405937635601.png" width="549px" />
10. Em **novas chaves**, no campo **In-App Purchase key**, clique no **ícone de upload** ( <Image alt="upload-2.png" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="15px" />) para fazer o upload do arquivo p8.
11. Na App Store Connect, copie o **Key ID** da chave que você acabou de gerar e cole-o na configuração de compras e assinaturas da AppsFlyer, em **Key ID**. <Image alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" width="484px" />
12. Na App Store Connect, copie o **Issuer ID** e cole-o na configuração de compras e assinaturas da AppsFlyer em **Issuer ID**. **Atenção:** se o **Issuer ID** não for exibido na parte superior da página, crie uma chave de API da App Store Connect (com qualquer nível de acesso). Depois disso, o Issuer ID aparecerá no topo da página para a In-App Purchase key. 

    <Image alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" width="474px" />
13. Nas configurações de compras e assinaturas da AppsFlyer, clique em **validar chaves** para garantir que as chaves que você inseriu estão corretas.
14. Clique em **atualizar chaves**. Uma vez que as chaves forem atualizadas, seu aplicativo estará totalmente pronto para o novo fluxo de validação do iOS.

</Accordion>

<div data-zendesk-anchors="h_01JP2XAKZABDJYB9ZQS4N3ST4Z=send-app-store-notifications-directly-to-appsflyer h_01J14M3C6WNXPJJQHVWVNFB4GS=get-ios-credentials" />
