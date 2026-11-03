---
title: Configurar a receita da loja do ROI360
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-08-19T00:01:41Z'
  id: 42158608158353
  locale: pt
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/pt/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** Configure a solução de receita da loja ROI360 da AppsFlyer.

> 🚧 **Importante!**
>
> A receita da loja do ROI360 está disponível apenas para os clientes do plano premium. Para verificar seu plano ou uma atualização, entre em contato com seu Customer Success Manager (CSM).

## Escritórios

> 📘 **Nota**
>
> Para mais informações sobre o ROI360, incluindo como ele funciona e como habilitá-lo na AppsFlyer, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue">Sobre a receita de loja do ROI360</Anchor>.

Para configurar a Receita de loja do ROI360, conclua as etapas a seguir na ordem indicada:

1. Configure as credenciais da loja (iOS e Android):
   * [iOS:](#etapa-1-ios-configurar-as-chaves-do-app-store-connect) Configure as chaves do App Store Connect (chave de In-App Purchase, Key ID e Issuer ID) na AppsFlyer.
   * [Android](#etapa-1-android-configure-a-chave-da-conta-de-serviço-e-as-permissões): Configure uma conta de serviço do Google Cloud, defina as permissões necessárias no Google Play Console e faça upload da chave JSON da conta de serviço para a AppsFlyer.
2. Configure as notificações do servidor (iOS e Android):
   * [iOS](#etapa-2-ios-configurar-notificações-do-servidor-da-app-store): Configure as App Store Server Notifications, enviando as notificações diretamente para a AppsFlyer (recomendado) ou encaminhando-as do seu próprio endpoint, e valide a integração.
   * [Android](#etapa-2-android-configurar-notificações-do-servidor-do-google-play): Configure as notificações para desenvolvedores em tempo real do Google Play (RTDN), permitindo que o Google Play envie notificações diretamente para a AppsFlyer (recomendado) ou encaminhando-as via Pub/Sub.
3. [Implemente o SDK Connector](#etapa-3-implementar-o-conector-do-sdk): prepare os desenvolvedores para integrar o AppsFlyer Purchase SDK Connector.
4. [Verifique a implementação do SDK](#etapa-4-verifique-a-implementação-do-sdk): teste compras in-app e assinaturas em sandbox nas duas plataformas para confirmar que os eventos do SDK e as notificações do servidor são recebidos e processados corretamente pela AppsFlyer.
5. [Verifique e atualize as configurações](#etapa-5-verifique-e-atualize-as-configurações): revise e confirme os status da validação de compras, do tratamento de reembolsos, da mensuração de assinaturas e da integração da loja para garantir a atribuição contínua e precisa da receita entre plataformas.
6. [Lance as versões do aplicativo](#etapa-6-lance-as-versões-do-aplicativo-com-o-conector-do-sdk): lance versões atualizadas do aplicativo com o SDK Connector integrado, garantindo que os sinalizadores de sandbox estejam desativados e que as regras de validação permitam os eventos de receita necessários.

## Etapa 1 (iOS): configurar as chaves do App Store Connect

Na etapa 1, obtenha as seguintes credenciais do App Store Connect e insira-as na página Configurações de receita na plataforma da AppsFlyer

* In-App Purchase key
* ID da chave
* Issuer ID

**Antes de começar**:

Para configurar as credenciais, você deve realizar ações tanto no App Store Connect quanto na AppsFlyer. Durante a configuração, mantenha as abas da App Store Connect e da AppsFlyer abertas.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Crie as App Store Connect Keys">

Para definir as credenciais do iOS, siga esta etapa:

1. Na App Store Connect, vá para **Users and Access**

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Vá para **Users and Access** > **Integrations** e, na lista **Keys** , selecione **In-App Purchase**.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Clique + para gerar uma nova chave de In-App Purchase.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Digite um nome para sua chave de API.
5. Clique em **Gerar**.
6. Clique em **Download In-App Purchase Key** ao lado da chave que você acabou de gerar para baixá-la. **Atenção:** você só pode baixar a chave uma vez.
7. Copie o **Key ID** da chave que você acabou de gerar e cole-o na configuração de compras & assinaturas da AppsFlyer, em **Key ID**.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. Copie o **Issuer ID**. **Observação**: se o **Issuer ID** não for exibido na parte superior da página, crie uma chave de API do App Store Connect (com qualquer nível de acesso). Depois disso, o Issuer ID aparecerá no topo da página para a In-App Purchase key.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 Defina a chave do App Store Connect no AppsFlyer">

1. <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#ativar-a-receita-da-loja-do-roi360">Habilite a receita de loja do ROI360</Anchor>.
2. Na etapa **App Store Connect keys** , clique em [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload** no **In-App Purchase key** campo para fazer upload do arquivo p8.
3. Na seção **App Store Connect keys**, cole os valores que você copiou do App Store Connect.

   * **ID da chave**

   * **Issuer ID**
4. Clique **Validar chaves** para garantir que as chaves inseridas estão corretas. **Observação: a Validate key** pode não funcionar se seu aplicativo ainda não tiver sido publicado na loja de aplicativos.
5. clique em **Salvar e próximo**

</Accordion>

## Etapa 1 (Android): Configure a chave da conta de serviço e as permissões

Obtenha as seguintes credenciais do App Store Connect e insira-as na página de Configurações de receita dentro da plataforma AppsFlyer.

**Antes de começar**:

* A configuração da mensuração de receita de compras in-app e assinaturas envolve etapas realizadas no <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, no <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor> e na <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">interface da AppsFlyer</Anchor>. Recomendamos manter as três abas abertas durante a configuração.
* A configuração na interface da AppsFlyer requer permissões de administrador.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1. Vincule sua conta de desenvolvedor do Google Play ao seu projeto do Google Cloud">

**Pré-requisitos**: Acesso ao Google Play Console e ao Google Cloud Project.

**Para vincular sua Conta de Desenvolvedor do Google Play ao seu Projeto do Google Cloud, siga estas etapas**:

1. No Google Play Console, acesse sua Google Play Developer Account.
2. Vincule a conta ao seu projeto Google Cloud. Para mais instruções, consulte este <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">artigo de ajuda do Google</Anchor>.
3. Ative a Google Play Developer API. Para mais instruções, consulte <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">este artigo de ajuda do Google</Anchor>.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2. Configure sua Service Account no Google Cloud Platform">

**Pré-requisitos**: Acesso ao Google Cloud Platform.

**Para configurar sua conta de serviço, siga estas etapas**:

1. Crie ou localize a **Service Account**:
   1. Acesse a seção **Service accounts** na Google Cloud Platform e clique em **Create Service Account**.

      [![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Insira os detalhes da service account.

      [![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Copie o endereço de e-mail.

      [![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Clique em **criar e continuar**.

      [![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. Na etapa **Grant this service account access to the project** , selecione a função de assinante do **Pub/sub** .

      [![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Clique em **Continue** > **Done**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Baixe a **Service Account Private Key**:
   1. Na Google Cloud Platform, acesse a seção **Service accounts** , encontre na lista a conta desejada (a que você acabou de criar) e clique no ícone **More actions** .
   2. Clique em **Manage keys**.

      [![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Clique em **Add key** > **Create new key**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. No pop-up **Create private key** , em **Key type** , selecione **JSON** , e clique em **Create**.

      [![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Clique em **criar**. O arquivo JSON de chave privada é baixado.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Salve o arquivo JSON, que será enviado para a AppsFlyer mais tarde. **Nota**! Você deve salvar a chave; ela não pode ser recuperada depois. Se você não salvá-la, terá que criar uma nova chave.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3. Defina permissões de acesso à API no Google Play Console.">

**Pré-requisitos**: acesso ao Google Play Console.

**Observação**: pode levar algum tempo (às vezes até 24 horas) após a configuração das credenciais e permissões da conta de serviço para poder usá-las. Isso pode fazer com que você receba mensagens de erro em etapas posteriores.

**Para definir permissões de acesso à API no Google Play Console**:

1. No Google Play Console, vá para **Users and permissions**, encontre a conta de serviço que você criou e clique **Invite new users**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Digite o **endereço de e-mail** que você copiou ao configurar sua conta de serviço na etapa 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. Na seção **Permissions** , vá para a aba **Account permissions** e selecione as duas opções:

   * Visualizar dados financeiros, pedidos e respostas à pesquisa de cancelamento.
   * Gerenciar pedidos e assinaturas[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. Na aba **App permissions** , clique **Add app,** then select your app. Adicione vários aplicativos, se necessário.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Clique **Invite user.**

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. Na janela pop-up de confirmação, clique **Send invite**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4. Envie a Service Account Private Key para a AppsFlyer">

Faça o upload e valide a chave JSON do Google que você baixou na [etapa 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Pré-requisitos**: acesso de administrador à AppsFlyer.

**Para fazer o upload da Service Account Private Key para a AppsFlyer, siga estas etapas**:

1. <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#ativar-a-receita-da-loja-do-roi360">Ative a receita da loja do ROI360</Anchor>.
2. Na etapa **Service Account Key and Permissions** , no campo **Upload Google JSON key** , clique [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)  **(Upload icon).**
3. Faça o upload do arquivo JSON que você baixou em [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Clique **Validate Key.** **Observação:**
   * após definir as credenciais e permissões da conta de serviço, pode levar até 24 horas para que você possa usá-las. Isso pode fazer com que você receba mensagens de erro ao tentar validar a chave ou realizar um teste de validação.
   * Para contornar o tempo de espera de 24 horas, no Google Play Console, navegue até qualquer aplicativo e, em seguida, vá para **Monetize** > **Products** > **Subscriptions/In-app products**, e faça uma alteração. Por exemplo, edite a descrição do seu produto e salve-a. Por exemplo, edite a descrição do seu produto e salve-a. Isso deve atualizar instantaneamente as credenciais e permissões da conta. Feito isso, você pode desfazer as alterações.
5. Clique **Salvar e Próximo**.

</Accordion>

## Etapa 2 (iOS): Configurar notificações do servidor da App Store

Configure como as notificações da App Store são recebidas na AppsFlyer.

* Se você já tiver um endpoint de notificações do servidor da App Store configurado no App Store Connect (por exemplo, seu próprio backend ou outro serviço), escolha entre **Opção 1 (recomendada)** ou **Opção 2**.
* Se você ainda não configurou um endpoint no App Store Connect, escolha a **Opção 1**.

#### Opção 1 (Recomendada) - AppsFlyer como endpoint principal

Substitua a URL de notificação existente do App Store Connect pelo endpoint da AppsFlyer e adicione seu endpoint anterior na AppsFlyer como destino de encaminhamento. A lógica e os fluxos de trabalho atuais da sua assinatura permanecem inalterados e continuam funcionando como esperado.

O fluxo de notificações para esta opção é o seguinte:

1. A App Store Connect envia notificações para a AppsFlyer
2. A AppsFlyer as processa para o ROI360
3. A AppsFlyer encaminha todas as notificações para o seu endpoint existente **em tempo real**

Para usar esta opção, conclua as etapas [2.1](#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](#22-send-notifications-directly-to-appsflyer) e [2.4](#24-test-the-server-notifications-integration).

#### Opção 2 - Seu endpoint como endpoint principal

Se você preferir manter seu endpoint existente como destino principal, configure seu servidor para encaminhar notificações do servidor da App Store para a AppsFlyer.

Para usar esta opção, ignore as etapas 2.1 e 2.2 e conclua as etapas [2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer) e [2.4](#24-test-the-server-notifications-integration)

> 📘 **Atenção**
>
> A Apple oferece suporte a apenas um endpoint de notificações do servidor da App Store por aplicativo e envia todos os tipos de notificação para ele, não apenas notificações de compra e de assinatura. A AppsFlyer usa as notificações de compra e assinatura para mensurar a receita. Ela confirma o recebimento de qualquer outro tipo à Apple, para que a Apple pare de tentar novamente, mas não o processa nem toma nenhuma providência em relação a ele.
>
> Se o seu aplicativo depende de tipos de notificação além de compras e assinaturas (por exemplo, notificações de consentimento), certifique-se de que essas notificações cheguem ao seu próprio servidor:
>
> * **Opção 1:** Mantenha a AppsFlyer como endpoint principal e habilite o encaminhamento (etapa 2.1). A AppsFlyer encaminha uma cópia de todas as notificações para o seu endpoint em tempo real, sem alterações em relação à forma como a Apple as enviou, incluindo os tipos que a AppsFlyer não processa.
> * **Opção 2:** Mantenha seu próprio endpoint como destino principal para que seu servidor receba e processe diretamente todos os tipos de notificação, e encaminhe notificações de compra e assinatura para a AppsFlyer.

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="Endpoint de notificações do servidor da AppsFlyer">

Para copiar o endpoint de notificações do servidor da AppsFlyer, siga essas etapas:

1. **Na AppsFlyer,** na etapa **App Store server notifications** , copie o endpoint de notificações do servidor da AppsFlyer.
2. Se você já tinha outro endpoint de notificações do servidor da App Store e quer que a AppsFlyer encaminhe notificações para ele, selecione **Encaminhar uma cópia das notificações para seu servidor (relevante apenas para a opção 1).**
3. Insira seu endpoint na caixa de texto exibida.

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="2.2 Enviar notificações diretamente para a AppsFlyer">

Para enviar notificações diretamente para a AppsFlyer, configure a AppsFlyer como endpoint principal de notificações do servidor da App Store.

1. No **App Store Connect**, na seção **App Information** , vá para **App Store Server Notifications** e, ao lado de **Production Server URL**, clique em **Edit**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Cole [o endpoint de notificações do servidor da AppsFlyer copiado da AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), selecione **Version 2 Notifications** e clique em **Save**. **Observação:** As notificações da versão 1 não têm mais suporte. Se o seletor de versão da notificação não aparecer no Apple Store Connect, isso significa que você já está usando a versão 2.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. Na seção **App Information** , vá para **App Store Server Notifications** e, ao lado de **Sandbox Server URL**, clique em **Edit**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
4. Cole [o endpoint de notificações do servidor da AppsFlyer copiado da AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), selecione **Version 2 Notifications** e clique em **Save**. **Observação:** As notificações da versão 1 não são mais compatíveis. Se o seletor de versão de notificação não aparecer no App Store Connect, isso significa que você já está usando a versão 2.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 [Opcional] Encaminhar notificações do seu endpoint para a AppsFlyer">

Use esta etapa somente se quiser manter seu endpoint como destino principal das notificações do servidor da loja de aplicativos, em vez de enviar as notificações diretamente para a AppsFlyer.

Essa opção não é a configuração recomendada e requer implementação no backend. Se você já configurou a AppsFlyer como endpoint principal na etapa **2.2** acima, pule esta etapa.

Para encaminhar notificações do servidor do seu endpoint para a AppsFlyer, siga essas etapas:

1. In **App Store Connect**, na seção **App Information**, role até **App Store Server Notifications** e, ao lado de **Production Server URL**, clique em **Edit**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Cole **a URL do endpoint do seu servidor**.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. Selecione **Version 2 Notifications. Note:** As notificações da versão 1 não são **mais compatíveis**. Se o seletor de versão da notificação não aparecer no Apple Store Connect, isso significa que você já está usando a versão 2.
4. Clique em **Salvar**.
5. In **App Store Connect**, na seção **App Information**, role até **App Store Server Notifications** e, ao lado de **Sandbox Server URL**, clique em **Edit**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
6. Cole **a URL do endpoint do seu servidor**.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. Selecione **Version 2 Notifications. Note:** As notificações da versão 1 não são **mais compatíveis**.
8. Clique em **Salvar**.
9. Configure seu backend para encaminhar as notificações do servidor da Apple para a URL do endpoint de notificações da AppsFlyer. As solicitações devem corresponder exatamente ao payload da App Store, conforme recebido da Apple. Consulte <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">os requisitos de formato da Apple</Anchor>.

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 Teste a integração das notificações do servidor">

Para confirmar se a AppsFlyer está recebendo corretamente as notificações do servidor da App Store, ou se você configurou recentemente o endpoint e ainda não recebeu notificações do servidor:

1. Na AppsFlyer, acesse a etapa **App Store server notifications**.
2. Clique em **Test integration**. A AppsFlyer envia uma solicitação de notificação de teste para a Apple, verifica se alguma notificação válida foi recebida da Apple nos últimos 7 dias e exibe um dos seguintes resultados:

   * Uma confirmação informando se notificações válidas foram recebidas.
   * Uma mensagem de status indicando que nenhuma notificação foi encontrada.

   > 📘 **Nota**
   >
   > A Apple pode levar alguns segundos para enviar a mensagem de teste.


   * Se o status continuar inválido, aguarde alguns instantes e tente novamente.
   * Depois que o teste for bem-sucedido, ou quando você estiver pronto para continuar, clique em **Salvar e avançar**.

</Accordion>

## Etapa 2 (Android): Configurar notificações do servidor do Google Play

Para receber dados de receita de compras in-app e assinaturas do Google Play, selecione entre as seguintes opções:

* (Recomendado) O Google Play envia as notificações diretamente para a AppsFlyer. Com essa opção, nenhuma cópia de notificação pode ser encaminhada para seu endpoint. Se quiser selecionar essa opção, saiba mais em [Enviar notificações do Google Play diretamente para a AppsFlyer](#21-send-google-play-notifications-directly-to-appsflyer).
* O Google Play envia as notificações primeiro para você, e então elas são encaminhadas para a AppsFlyer. Se você escolher essa opção, saiba mais em [Encaminhar notificações do Google Play para a AppsFlyer.](#22--optional--forward-google-play-notifications-to-appsflyer)

**Pré-requisitos**: Acesso ao Google Play Console e à interface da AppsFlyer.

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="2.1 Enviar notificações do Google Play diretamente à AppsFlyer">

1. Na AppsFlyer, na etapa 2,**Configurar notificações do servidor do Google Play**, selecione **Permitir que o tópico da AppsFlyer receba mensagens RTDN diretamente do Google**.
2. Copie o tópico da AppsFlyer para a área de transferência.
3. Em **Google Play Console** > **Home**, selecione para visualizar seu aplicativo. O painel é aberto.

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. Vá para **Monetize with Play** > **Monetization setup**, e na seção **Google Play Billing** certifique-se de que **Enable real-time notification** esteja selecionado.

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. No campo **Topic name** , cole o endereço do tópico da AppsFlyer que você copiou.

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. Para **Notification content**, selecione **Subscriptions, voided purchases, and all one-time products**.

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. Clique **Save Changes**. Pode levar um tempo (às vezes até 24 horas) para que essa alteração tenha algum efeito. Por isso, é importante esperar antes de testar.

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="2.2 [Opcional] Encaminhe notificações do Google Play para a AppsFlyer">

**Observação**: esta etapa é apenas para quando você não escolheu o método recomendado para receber do Google Play os dados de receita de compras in-app e assinaturas, enviando notificações diretamente para a AppsFlyer. Se você completou as etapas para o método recomendado, para criar um tópico onde a AppsFlyer recebe diretamente as notificações RTDN do Google Play, pule essa etapa.

Se você quiser configurar a AppsFlyer como assinante do seu tópico PUB/SUB existente, continue com as instruções abaixo.

**Pré-requisitos**: Acesso ao Google Cloud Platform e à interface da AppsFlyer.

**Para encaminhar notificações do Google Play para a AppsFlyer**:

1. Na AppsFlyer, no menu lateral, acesse **Settings** > **Revenue Settings**,
2. Selecione seu aplicativo,
3. Na guia **Purchases & subscriptions** tab, selecione **Forward your RTDN topic messages to AppsFlyer**.
4. Copie a URL do endpoint para a área de transferência.
5. No Google Cloud Platform, em seu projeto, pesquise por **Pub/Sub**.

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. Em **Pub/Sub** , vá para a seção **Topics** e verifique se você tem um tópico pub/sub dedicado para assinaturas.

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. Em **Pub/Sub,** vá para a seção **Subscriptions** e clique **Create Subscriptions**.

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. Insira o **Subscription ID**.

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. Selecione o tópico relevante do pub/sub no menu suspenso.

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. Para **Delivery type**, selecione **Push**.

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. Cole a **Endpoint URL** que você copiou da AppsFlyer.

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. Em **Expiration period**, selecione **Never expire**.

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. Clique **Create**.

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. Vá para a seção **Subscriptions** e clique no nome do tópico desejado.

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. Copie o nome do tópico para a área de transferência.

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. No **Google Play Console**, vá para **Monetize with Play** > **Monetization setup** No **Google Play Console**, vá para **Monetize with Play** > **Monetization setup** e, na seção **Google Play Billing** , cole no campo Topic name o nome do tópico que você copiou na etapa anterior.

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. Para **Notification content**, selecione **Subscriptions, voided purchases, and all one-time products**.

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. Clique **Save changes**. Pode levar um tempo (às vezes até 24 horas) para que essa alteração tenha algum efeito. Por isso, é importante esperar antes de testar.

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 Enviar uma notificação de teste da Google Play Console">

Para verificar se as notificações do desenvolvedor em tempo real (RTDN) do Google Play são recebidas corretamente pela AppsFlyer, envie uma notificação de teste do Google Play Console:

1. Clique em **Send test notification**. Isso envia uma mensagem RTDN de teste para o tópico do Pub/Sub configurado para a AppsFlyer.

   <Image alt="image (33).png" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />
2. Em **Google Play Billing**, localize a seção Topic name.
3. No menu à esquerda, navegue até **Monetise with Play** → **Monetisation setup**.
4. Vá para o Google Play Console.

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 Confirmar a entrega da notificação na AppsFlyer">

1. Quando o teste for bem-sucedido, ou quando você estiver pronto para prosseguir, clique em **Save and next**.
2. Resultado: a AppsFlyer exibe se alguma notificação foi recebida nos últimos 7 dias.
   * Se for bem-sucedido, a interface mostrará a data e a hora da notificação mais recente.
   * Se nenhuma tiver sido recebida, a interface indicará que nenhuma notificação foi encontrada nos últimos 7 dias.
   * Se nenhum status aparecer, revise sua configuração do Pub/Sub e reenvie a notificação de teste.
3. Na etapa **Google Play Server Notifications**, clique em **Test integration**.

</Accordion>

</Accordion>

## Etapa 3: Implementar o Conector do SDK

Nessa etapa, você preparará seus desenvolvedores para integrar o Purchase SDK Connector da AppsFlyer e configurar o ambiente sandbox para testes.

Para implementar o SDK connector, siga essas etapas:

1. Na etapa **Implement SDK Connector**, copie a **mensagem pré-escrita** exibida no dashboard.
2. Envie-a para seus desenvolvedores. Ela inclui:
   * o nome e o ID do aplicativo
   * Um link para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">o guia de integração do SDK</Anchor>.
   * Instruções para configurar o ambiente sandbox (`sandbox = true`)
   * Etapas de teste (usando **TestFlight**)

Essa mensagem fornece todas as informações que os seus desenvolvedores precisam para concluir a integração e começar os testes.

> 📘 **Nota**
>
> O conector usa detecção automática de transações. Como alternativa, você pode implementar o método `validateAndLog` do SDK para registrar manualmente cada transação. Esse método não oferece suporte a todos os recursos disponíveis no conector. Para ver detalhes sobre as duas opções de integração do SDK, consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">a documentação do DevHub</Anchor>.

## Etapa 4: Verifique a implementação do SDK

Teste a integração de receita de compras in-app e assinaturas em um ambiente sandbox para confirmar que o conector do SDK está corretamente integrado e que as notificações do servidor estão configuradas e são recebidas pela AppsFlyer.

<div id="test-sdk-implementation" />

<Accordion title="Testar a implementação do SDK">

Para verificar se a AppsFlyer recebeu payloads válidos de eventos de compra e assinatura do seu aplicativo nos últimos 7 dias, siga estas etapas:

1. Na etapa **Verifique a implementação do SDK**, clique em **Testar implementação do SDK**.
2. Revise os resultados, incluindo o registro de data/hora do payload mais recente recebido pela AppsFlyer.

   > 📘 **Nota**
   >
   > Esse teste confirma apenas que as solicitações estão chegando à AppsFlyer e não verifica a integridade nem a correção dos dados.

3. Para validar totalmente a implementação, continue com as etapas de teste abaixo.

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="Eventos e parâmetros de sandbox">

* O conector do SDK gera eventos apenas para a transação inicial em sandbox:
  * Compra in-app: `af_purchase_sandbox_sdk`
  * Assinatura: `af_ars_sandbox_sdk`
* A AppsFlyer processa notificações do servidor somente se o evento do SDK da transação original tiver sido registrado.
  * Compra in-app S2S: `af_purchase_sandbox_s2s`
  * Assinatura S2S: `af_ars_sandbox_s2s`
* Se o SDK nunca registrar a transação original. nenhum evento S2S será criado.

**Considerações sobre iOS**

* Se `af_purchase_sandbox_sdk` incluir `af_sandbox_revenue`, ele será mapeado para um `af_purchase` de produção.
* Se não houver receita, ele será mapeado para um `af_purchase_free` de produção.

**Considerações sobre Android**

* Compras feitas por **License Testers** sempre geram eventos de sandbox. mesmo que o modo sandbox não esteja configurado no SDK.

**Parâmetros obrigatórios para eventos de teste**

Certifique-se de que todo evento de compra no sandbox inclua:

* **Receita = 0** (para evitar afetar relatórios reais).
* `af_sandbox_revenue` = preço real do produto (para que a receita correta seja atribuída).
* `af_validated` **= true**. Se for `false`, volte e verifique a chave da loja.
* `af_validation_type` = `receipt_validation`.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Teste a receita de compras in-app e assinaturas">

**Pré-requisitos**:

* Para iOS, certifique-se de que, em App Store Server Notifications no App Store Connect, o endpoint da AppsFlyer esteja configurado como sua **URL do servidor de sandbox**.

  [![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**Para testar a receita de compras e assinaturas in-app**:

1. Diga aos seus desenvolvedores para seguirem as instruções de <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration">Android</Anchor>, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">iOS</Anchor>, and <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox">Unity</Anchor> para configurar o ambiente sandbox no SDK Connector.
2. Faça compras de teste ou inicie uma assinatura usando o <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester no Google Play</Anchor>. Para iOS, use o <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>. **Observação**: um produto de assinatura pode ser testado apenas uma vez por dispositivo. Na prática, um dispositivo não pode registrar várias compras de teste da mesma assinatura. As tentativas adicionais não serão registradas.
3. Faça um evento de teste de reembolso, renovação de assinatura ou cancelamento de assinatura usando o <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester no Google Play</Anchor> e o <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight no iOS</Anchor>. **Observação**: se você estiver testando um produto de assinatura, aguarde a AppsFlyer receber uma notificação do servidor da loja, o que normalmente ocorre em alguns minutos após a compra inicial.
4. Clique em **Testar integração do SDK**. Você verá quando o payload mais recente do SDK foi recebido pela AppsFlyer nos últimos 7 dias e se ele se originou no **Purchase SDK Connector** ou no **Validate and Log**.
5. Verifique se os eventos de teste são exibidos de uma das seguintes formas:

   * Visualize o evento no <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">Visualizador de eventos ao vivo</Anchor>.

   * Visualize os dados do evento em <Anchor target="_blank" href="/marketers/pt/docs/activity-metrics-in-my-dashboards">My Dashboards - Activity View</Anchor>.
6. Verifique se o evento aparece no dashboard de Atividade da AppsFlyer. Na AppsFlyer, vá para **Analisar > Atividade** e, no gráfico **Tendência de atividade**, abra a aba Eventos in-app e selecione o evento para testar. Uma compra de assinatura com renovação automática é chamada de `af_ars_s2s_sandbox`. O evento inclui:
   * Uma receita com valor 0 (para não distorcer os relatórios reais da AppsFlyer).
   * Um parâmetro `af_sandbox_revenue` que inclui o valor da receita do produto comprado, garantindo que a receita correta seja reportada.

</Accordion>

## Etapa 5: Verifique e atualize as configurações

Depois de concluir a configuração das definições acima e salvar a última etapa, você será redirecionado para a visualização da configuração ativa, em que poderá verificar ou atualizar as seguintes configurações:

1. Certifique-se de que o **Verify purchases with the App Store** botão de alternância esteja ativado.
2. Verifique as seguintes opções em **compras**:
   * **Prevent duplicate purchases for clean data**: Evita registrar transações que já foram reportadas.
   * **Automatically measure refunds, cancellations, and negative revenue**: Mensura eventos relacionados a reembolsos e os registra como receita negativa.
   * **Avoid double-counting revenue from Family Sharing**: Evita a contagem duplicada da receita do Family Sharing. Esses eventos são marcados com `purchase_ownership_type=FAMILY_SHARED` e reportam receita zero.
3. Certifique-se de que o **Measure and attribute revenue for auto-renewing subscriptions** botão de alternância esteja ativado:
4. O status das seguintes configurações:
   * A **App Store key** configuração
   * A **endpoint de notificação do servidor** configuração
   * Implementar & testar o SDK Connector

## Etapa 6: Lance as versões do aplicativo com o conector do SDK

Com tudo configurado a partir das etapas anteriores, e o purchase SDK connector da AppsFlyer integrado ao seu aplicativo, diga ao seu desenvolvedor para liberar a versão do aplicativo com o SDK connector integrado.

No entanto, antes que o desenvolvedor libere a nova versão do aplicativo, certifique-se de que:

* Os eventos in-app que você deseja capturar como compra-inapp ou assinatura não sejam bloqueados por regras de validação que você configurou na AppsFlyer.
* Seu desenvolvedor deve ter sinalizadores de área restrita marcados como falsos.

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

Depois que o aplicativo com o conector do SDK for lançado, os <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">eventos de compra in-app</Anchor> e os <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">eventos de assinatura</Anchor> serão gerados e disponibilizados em todos os dashboards da AppsFlyer, bem como em relatórios de dados agregados e relatórios de dados brutos, incluindo <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports">Revenue ETL</Anchor>.

**Observação:** Os eventos só serão gerados para usuários que atualizaram para uma versão do aplicativo que inclui o conector do SDK. Como resultado, é esperada uma discrepância entre os dados de receita do aplicativo e os dados da loja até que a versão atualizada do aplicativo seja totalmente adotada.

## Migrar para a receita da loja do ROI360 (da Validação de recibos)

Se você concluiu o Onboarding da Validação de recibos, mas quer ativar o produto de receita da loja do ROI360, faça o seguinte:

1. Na AppsFlyer, no menu lateral, abra [<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png) **Configurações** e, em **ROI360** selecione **Configurações de receita**.
2. Abra a aba **Compras e assinaturas**. Um banner é exibido informando que o ROI360 está disponível, mas não está ativo.
3. Clique em **View product comparison** para entender os benefícios, incluindo atribuição de reembolsos, reportar receita líquida e mensuração completa do ciclo de vida de assinaturas.
4. Clique em **Activate ROI360.**
5. Realize a etapa **Enable App Store Server Notification**. Para mais informações, consulte [Configurar notificações do servidor da App Store](#etapa-2-ios-configurar-notificações-do-servidor-da-app-store) ou [Configurar notificações do servidor do Google Play](#etapa-2-android-configurar-notificações-do-servidor-do-google-play).
6. Na seção **Compras & assinaturas**, verifique se o **Tipo de produto** agora está definido como **ROI360**.
7. Revise sua configuração atual do SDK para garantir que ela possa oferecer suporte à funcionalidade de receita da loja do ROI360 de que você precisa.

> 📘 **Nota**
>
> A receita da loja do ROI360 oferece suporte a dois métodos de integração: Purchase SDK Connector e Validate and Log. Dos dois, recomendamos usar o **Purchase SDK Connector** para se beneficiar de:
>
> * Detecção automática de transações
> * Mensuração da receita de assinantes existentes (usuários inscritos antes da integração)
> * Suporte a alterações no preço da assinatura, garantindo relatórios de receita precisos quando houver atualizações de preços.
>
> Se você não precisar desses recursos, poderá continuar usando a integração **Validate and Log**.
>
> **Como verificar seu método de integração do SDK**
>
> Para confirmar se o seu aplicativo usa o Purchase SDK Connector ou o Validate and Log:
>
> 1. Acesse a etapa **Integrate SDK Connector**.
> 2. Clique em **Testar integração do SDK**. Na etapa **Verify SDK connector implementation**, clique em **Test SDK implementation** Isso indica se alguma carga útil do SDK foi recebida com sucesso do Purchase Connector nos últimos 7 dias.

<div data-zendesk-anchors="h_01KSAG4Y3BP0NWYNCX3AJG47JR=importante overview=escrit%C3%B3rios h_01KD31QE0BCW0BX9BNNDK6DJRA=escrit%C3%B3rios h_01KD31QE0BQAQ0CS1FJ46TV6K1=nota step-1-ios-set-up-app-store-connect-keys=etapa-1-ios-configurar-as-chaves-do-app-store-connect h_01KD31QE0BE3ST0TV3KQ1M5AB0=etapa-1-ios-configurar-as-chaves-do-app-store-connect h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=etapa-1-android-configure-a-chave-da-conta-de-servi%C3%A7o-e-as-permiss%C3%B5es h_01KD31QE0BVQNJZ8PKKYKK9Q79=etapa-1-android-configure-a-chave-da-conta-de-servi%C3%A7o-e-as-permiss%C3%B5es h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=etapa-2-ios-configurar-notifica%C3%A7%C3%B5es-do-servidor-da-app-store h_01KD31QE0CZAJ7SH2EECDJ11YN=etapa-2-ios-configurar-notifica%C3%A7%C3%B5es-do-servidor-da-app-store option-1-recommended-appsflyer-as-the-primary-endpoint=op%C3%A7%C3%A3o-1-recomendada---appsflyer-como-endpoint-principal h_01KW7HDDAQEHGY33SQ2AHWVJAC=op%C3%A7%C3%A3o-1-recomendada---appsflyer-como-endpoint-principal option-2-your-endpoint-as-the-primary-endpoint=op%C3%A7%C3%A3o-2---seu-endpoint-como-endpoint-principal h_01KW7HDDAQK8Z279CEG7N33FKT=op%C3%A7%C3%A3o-2---seu-endpoint-como-endpoint-principal h_01_roi360_notification_types=aten%C3%A7%C3%A3o h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=nota-1 step-2-android-set-up-google-play-server-notifications=etapa-2-android-configurar-notifica%C3%A7%C3%B5es-do-servidor-do-google-play h_01KD31QE0CKP0PTBQ4XCT9NDE1=etapa-2-android-configurar-notifica%C3%A7%C3%B5es-do-servidor-do-google-play h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=etapa-3-implementar-o-conector-do-sdk h_01KD31QE0CPK1EYVT0BSYTTZFM=etapa-3-implementar-o-conector-do-sdk h_01KD31QE0C65DQ59ZKG8V886JW=nota-2 step-4-verify-sdk-implementation=etapa-4-verifique-a-implementa%C3%A7%C3%A3o-do-sdk h_01KD31QE0C9KGGFVQR6HYR5AYM=etapa-4-verifique-a-implementa%C3%A7%C3%A3o-do-sdk h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=nota-3 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=etapa-5-verifique-e-atualize-as-configura%C3%A7%C3%B5es h_01KD31QE0DQP78QG5HRSERR5S9=etapa-5-verifique-e-atualize-as-configura%C3%A7%C3%B5es step-6-release-the-app-versions-with-the-sdk-connector=etapa-6-lance-as-vers%C3%B5es-do-aplicativo-com-o-conector-do-sdk h_01KD31QE0D3HX2DEH7FQ1JR4MS=etapa-6-lance-as-vers%C3%B5es-do-aplicativo-com-o-conector-do-sdk switch-to-roi360-store-revenue-from-receipt-validation=migrar-para-a-receita-da-loja-do-roi360-da-valida%C3%A7%C3%A3o-de-recibos h_01KD31QE0DJNJ8T5XSZFCACMQF=migrar-para-a-receita-da-loja-do-roi360-da-valida%C3%A7%C3%A3o-de-recibos h_01KD31QE0DX0VDXKHDZTWTYHHX=nota-4" />
