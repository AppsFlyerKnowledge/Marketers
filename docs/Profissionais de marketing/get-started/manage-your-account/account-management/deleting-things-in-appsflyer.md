---
title: Como remover itens na AppsFlyer
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
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-08-19T00:15:51Z'
  id: 360000603117
  locale: pt
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/pt/articles/360000603117
---
> **Visão geral:** entenda como remover aplicativos e interromper a atribuição, remover canais de mídia ou excluir dados de usuários.

<Image alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

## Remover histórico do usuário

Alguns regulamentos de privacidade, como a GDPR e a CCPA, dão aos usuários o *direito de exclusão* de seus dados.

**Cenário:** um usuário solicita que você exclua todos os dados relacionados a ele. A GDPR exige que isso seja feito dentro de 30 dias.

**Ação necessária:**  use a <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">OpenDSR API</Anchor> para enviar uma solicitação de exclusão.

## Parar de atribuir instalações a um canal de mídia

A AppsFlyer coleta informações de instalação e eventos para os canais de mídia configurados. Se um canal de mídia estiver configurado para atribuição, novas instalações serão atribuídas.

**Cenário:** se você parar campanhas em um determinado canal de mídia sem cliques, impressões ou instalações, a atribuição será interrompida. No entanto, os eventos in-app de usuários existentes continuam sendo registrados e atribuídos.

**Ação necessária:**

* **SKAN (para apps do iOS):**
  1. <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#disable-skan-measurement">Desativar a mensuração da SKAN</Anchor>.
  2. No <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor> e no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta Ads</Anchor>, você também deve remover as conexões da SKAN para interromper o registro de dados.
* **SRN:** <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#desativar-uma-integração-de-parceiro">Desativar a integração do parceiro</Anchor>.
* 1. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#desativar-uma-integração-de-parceiro">Desativar a integração do parceiro</Anchor>.
  2. Os cliques e instalações recebidos a partir do link de atribuição da AppsFlyer continuam a ser registrados e atribuídos. Certifique-se de que os anúncios exibidos para leads não contenham um link de atribuição da AppsFlyer.
* **Mídias próprias:**
  * Interrompa o uso de links personalizados relevantes do OneLink.

## Remover ou excluir um aplicativo

Você tem a opção de remover temporariamente um aplicativo.

#### Remova temporariamente um aplicativo

Quando um aplicativo é temporariamente removido, o registro de dados é interrompido, o app não aparece mais no dashboard e fica desabilitado na página “My Apps”. No entanto, o aplicativo permanece associado à conta e pode ser restaurado. Ao restaurar o aplicativo, os dados históricos como definições, agências aprovadas e tokens continuam disponíveis.

> 📘 **Nota**
>
> Os aplicativos são removidos individualmente. No entanto, você pode <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#gerencie-seus-aplicativos-em-massa-através-da-api">remover vários aplicativos via API</Anchor>.

**Para excluir um aplicativo:**

1. Na barra superior, clique em **My Apps**.
2. Selecione um menu de ações do aplicativo.
3. Clique em **Remover** e ***confirme***.  
   O aplicativo é excluído e deixa de ser exibido na lista de apps.

**Para restaurar um aplicativo que foi excluído:**

* Entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsFlyer.com). Depois que seu CSM restaurar o aplicativo, você poderá adicioná-lo novamente à sua conta.

## Transferir aplicativos entre contas

Para mais informações, acesse esse guia: <Anchor target="_blank" href="/marketers/pt/docs/transferring-apps-between-accounts">Transferência de aplicativos entre contas</Anchor>.

## Excluir sua conta ou fazer o downgrade do plano de assinatura

Entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsFlyer.com).

<div data-zendesk-anchors="delete-user-history=remover-hist%C3%B3rico-do-usu%C3%A1rio h_01HNZ7TNZM4P5APM2B1WQ4X7S5=remover-hist%C3%B3rico-do-usu%C3%A1rio stop-attributing-installs-to-a-media-source=parar-de-atribuir-instala%C3%A7%C3%B5es-a-um-canal-de-m%C3%ADdia h_01HNZ7VPA16065PGCSZDMQZ3ZC=parar-de-atribuir-instala%C3%A7%C3%B5es-a-um-canal-de-m%C3%ADdia delete-an-app=remover-ou-excluir-um-aplicativo h_01HNZ7XKEFRNEWGQZ58T7H0KDH=remover-ou-excluir-um-aplicativo removing-an-app=remova-temporariamente-um-aplicativo h_01J52J31FDKSPNWSD5J2V5BYTW=remova-temporariamente-um-aplicativo h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=nota transfer-apps-between-accounts=transferir-aplicativos-entre-contas h_01HNZ7ZW7ZKDSD2TTEX55PYB91=transferir-aplicativos-entre-contas delete-your-account-or-downgrade-your-subscription-plan=excluir-sua-conta-ou-fazer-o-downgrade-do-plano-de-assinatura h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=excluir-sua-conta-ou-fazer-o-downgrade-do-plano-de-assinatura" />
