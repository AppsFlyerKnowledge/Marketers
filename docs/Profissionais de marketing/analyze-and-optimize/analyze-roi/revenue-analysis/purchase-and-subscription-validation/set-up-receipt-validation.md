---
title: Configurar a Validação de recibos
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-10-25T01:10:17Z'
  id: 42137474889489
  locale: pt
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/pt/articles/42137474889489
---
> **Resumo:** A validação de recibos mensura a receita de compras in-app e assinaturas e a verifica junto às lojas de aplicativos, garantindo resultados precisos de retorno sobre gasto com anúncios (ROAS).

## Fazer upgrade para a nova Validação de recibos

A Validação de recibos legada será desativada em **7 de setembro de 2026**; consulte o <Anchor target="_blank" href="/marketers/pt/docs/bulletin-legacy-receipt-validation-is-deprecated">Boletim: a Validação de recibos legada foi descontinuada</Anchor>. Se o seu aplicativo usa a Validação de recibos legada, migre para a nova realizando as etapas de configuração abaixo. Antes de começar, revise as principais diferenças e prepare a migração.

<div id="h_migration_key_differences" />

<Accordion title="O que há de novo na Validação de recibos">

| Área | Legado | Nova validação de recibos |
| --- | --- | --- |
| Método do SDK | `validateAndLogInAppPurchase` (legado/v1) | `validateAndLogInAppPurchase` (v2), mesmo nome e nova assinatura no iOS e Android |
| Entrada de preço e moeda | Informado na chamada do SDK | Extraído automaticamente da loja |
| Tipo de compra | Não obrigatório | Parâmetro `PurchaseType` obrigatório (*assinatura* ou *compra avulsa*) |
| Configuração das definições de receita | Não obrigatório | Obrigatório (página Definições de receita) |
| Fonte do valor de `af_revenue` | Valor informado na chamada do SDK | Valor bruto retornado pela loja; qualquer valor personalizado informado na chamada do SDK vai para o objeto `custom_data` do evento |
| Granularidade do evento de compra | Um único evento `af_purchase` para todos os tipos de transação | Eventos distintos por tipo de transação: `af_purchase`, `af_ars_trial_started`, `af_ars_subscription_started` e variantes de sandbox |
| Suporte ao StoreKit 2 (iOS) | Não suportado | Com suporte. |
| Filtragem de fraude | Com limitação | Aprimorado no Android e no iOS |
| Disponibilidade do SDK | Removido do SDK da AppsFlyer v7.0.0+ | Disponível a partir do Android v6.17.5, iOS v6.17.8 e plugins v6.17.8 em diante |
| Registro validado de evento de compra | Com suporte até 7 de setembro de 2026 | Em andamento |

</Accordion>

<div id="h_migration_what_to_plan" />

<Accordion title="Prepare a migração">

Antes de iniciar a migração, revise as seguintes considerações:

* **Faça a migração gradualmente sem interromper a experiência dos usuários existentes.** Habilitar a nova Validação de recibos no dashboard da AppsFlyer não afeta as versões do aplicativo que ainda usam o método legado. Ambos continuam funcionando até a descontinuação do legado em 7 de setembro de 2026.
* **Espere mudanças na receita após a migração.** A nova Validação de recibos usa o valor bruto retornado pela loja, enquanto a Validação de recibos legada usava o valor de receita informado na chamada do SDK. Se a chamada do SDK informou um valor não bruto, os dashboards e os postbacks de parceiros, que agora refletem valores brutos, mostrarão um número diferente após a migração. Para receita líquida, use **ROI360 Store Revenue**. Consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue">Configurar a receita da loja do ROI360</Anchor>.
* **Informe seus parceiros de UA sobre a mudança na receita.** As ad networks que costumavam receber receita não bruta do postback `af_purchase` verão valores diferentes após a migração.
* **Planeje o cronograma de lançamento do seu aplicativo.** Após setembro 7, 2026, os usuários em versões do aplicativo criadas com versões do SDK anteriores ao Android v6.17.5 ou iOS v6.17.8 deixarão de gerar eventos `af_purchase` validados. Lance a nova versão do seu aplicativo com antecedência suficiente para alcançar a maior parte da sua base de usuários antes do encerramento.

</Accordion>

<div id="h_migration_upgrade_path" />

<Accordion title="Mudar para o ROI360 Store Revenue">

Mudar para o ROI360 Store Revenue não exige alteração no SDK, já que ambos os produtos usam o mesmo método `validateAndLogInAppPurchase` (v2). Adicionar o Purchase Connector para detecção automática de compras é opcional.

Para mais informações e instruções de configuração, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue">Configurar a receita da loja no ROI360</Anchor>.

</Accordion>

## Escritórios

> 📘 **Nota**
>
> Para mais informações sobre a Validação de recibos, incluindo como ela funciona e como habilitá-la na AppsFlyer, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation">Sobre a Validação de recibos</Anchor>.

Para configurar a Validação de recibos, conclua as etapas a seguir na ordem:

1. Configurar credenciais da loja (iOS e Android)
   * [iOS](#etapa-1-ios-configurar-as-chaves-do-app-store-connect): Configure as chaves do App Store Connect (chave In-App Purchase, Key ID e Issuer ID) na AppsFlyer para habilitar a Validação de recibos.
   * [Android](#passo-1-android-configure-a-service-account-key-e-permissões): Configure uma conta de serviço do Google Cloud, defina as permissões necessárias no Google Play Console e faça upload da chave JSON da conta de serviço para a AppsFlyer.
2. [Implementar a API do SDK validateAndLog](#3-implementar-o-sdk): Prepare os desenvolvedores para integrar a API do SDK `validateAndLog` da AppsFlyer e configurar o ambiente sandbox para testes.
3. [Testar a implementação da API do SDK validateAndLog](#3-verifique-a-implementação-do-sdk): Faça compras e assinaturas de teste no sandbox no iOS e no Android para verificar se os eventos de Validação de recibos são gerados e registrados corretamente pela AppsFlyer.
4. [Verificar e atualizar configurações](#4-verifique-e-atualize-as-configurações): Confirme se o tipo de produto está definido como Validação de recibos e revise os status da chave da loja e da integração do SDK para garantir a mensuração precisa e contínua da receita.
5. [Lançar as versões do aplicativo com a API do SDK validateAndLog](#5-lance-as-versões-do-aplicativo-com-a-api-do-sdk-validateandlog): Lance versões atualizadas do aplicativo com a API do SDK `validateAndLog` integrada, garantindo que os sinalizadores de sandbox estejam desativados e que os eventos in-app obrigatórios não sejam bloqueados pelas regras de validação.

## Etapa 1 (iOS): configurar as chaves do App Store Connect

Na etapa 1, obtenha as seguintes credenciais no *App Store Connect* e insira-as na página de **Revenue Settings** da plataforma AppsFlyer.

* In-App Purchase key
* ID da chave
* Issuer ID

**Antes de começar**:

* Para configurar as credenciais, você deve realizar ações tanto no App Store Connect quanto na AppsFlyer. Durante a configuração, mantenha as abas da App Store Connect e da AppsFlyer abertas.
* Seu aplicativo iOS requer StoreKit v1 ou v2, que fornece a estrutura necessária para gerenciar compras in-app e assinaturas.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Crie as App Store Connect Keys">

Para definir as credenciais do iOS, siga estas etapas:

1. No App Store Connect, vá para **Users and Access**.

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Vá para **Users and Access** > **Integrations** e, na lista **Keys** , selecione **In-App Purchase**.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Clique em + para gerar uma nova chave de In-App Purchase.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Digite um nome para sua chave de API.
5. Clique em **Gerar**.
6. Clique em **Download In-App Purchase Key** ao lado da chave que você acabou de gerar para fazer o download. **Atenção:** você só pode baixar a chave uma vez.
7. Copie o **Key ID** da chave que você acabou de gerar e cole-o na configuração de compras & assinaturas da AppsFlyer, em **Key ID**.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. Copie o **Issuer ID**. **Observação**: se o **Issuer ID** não aparecer na parte superior da página, crie uma chave de API do App Store Connect (com qualquer nível de acesso). Depois disso, o Issuer ID aparece na parte superior da página da chave de In-App Purchase.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 Definir a chave do App Store Connect">

1. Ative a Validação de recibos. #habilitar-validação-de-recibo
2. Na etapa **App Store Connect keys** , clique em <Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />  **Upload** no campo **In-App Purchase key** para carregar o arquivo p8.
3. Na seção intitulada **App Store Connect keys**, cole os valores que você copiou do App Store Connect.

   * **ID da chave**
   * **Issuer ID**
4. Clique **Validate keys** para garantir que as chaves inseridas estejam corretas. **Observação**: a ação **Validate keys** pode não funcionar se seu aplicativo ainda não tiver sido publicado na App Store.
5. Clique **Save and Next**.

</Accordion>

## Passo 1 (Android). Configure a service account key e permissões

Na etapa 1, obtenha as seguintes credenciais de *Google Play* e *Google Cloud* e insira-as na página **Revenue Settings** na plataforma AppsFlyer.

**Antes de começar**:

* A configuração da mensuração de receita de compras in-app e assinaturas envolve etapas realizadas na <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor> e na <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">interface da AppsFlyer</Anchor>. Recomendamos manter as três abas abertas durante a configuração.
* A configuração na IU da AppsFlyer requer permissões de administrador.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 Vincule sua conta de desenvolvedor do Google Play ao seu projeto do Google Cloud">

**Pré-requisitos**: acesso ao Google Play Console e a um projeto do Google Cloud.

**Para vincular sua conta de desenvolvedor do Google Play ao seu projeto do Google Cloud, siga estas etapas**:

1. No Google Play Console, acesse sua conta de desenvolvedor do Google Play.
2. Vincule a conta ao seu projeto Google Cloud. Para obter instruções, consulte este <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">artigo de ajuda do Google</Anchor>.
3. Ative a Google Play Developer API. Para obter instruções, consulte <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">este artigo de ajuda do Google</Anchor>.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2 Configure sua conta de serviço na plataforma Google Cloud">

**Pré-requisitos**: acesso à plataforma Google Cloud.

**Para configurar sua service account, siga estas etapas**:

1. Crie ou localize a **service account**:

   1. Acesse a seção **Service Accounts** na plataforma Google Cloud e clique **CREATE SERVICE ACCOUNT**.[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Insira os detalhes da service account.[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Copie o endereço de e-mail.[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Clique **Create and continue**.[![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. Na etapa **Grant this service account access to the project** , selecione a função de assinante do **Pub/Sub** .[![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Clique **Continue** > **Done**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Faça o download da service account private key:

   1. Na plataforma Google Cloud, acesse a seção **Service accounts** , localize na lista a conta desejada (a que você acabou de criar) e clique no ícone **More actions** .
   2. Clique **Manage keys**.[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Clique em **Add key** > **Create new key**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. No pop-up **Create private key** popup, under **Key type**, selecione **JSON**, e clique **Create**.[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Clique **Create**. O arquivo JSON de chave privada é baixado.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Salve o arquivo de chave JSON, que você fará o upload para a AppsFlyer mais tarde. **Nota**! Você deve salvar a chave. ela não poderá ser recuperada depois. Se você não salvá-la, terá que criar uma chave totalmente nova.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3 Defina permissões de acesso à API no Google Play Console">

**Pré-requisitos**: acesso ao Google Play Console.

**Observação**: pode levar algum tempo (às vezes até 24 horas) após a configuração das credenciais e permissões da conta de serviço para poder usá-las. Isso pode fazer com que você receba mensagens de erro em etapas posteriores.

**Para definir permissões de acesso à API no Google Play Console**:

1. No Google Play Console, vá para **Users and permissions**, encontre a conta de serviço que você criou, e clique **Invite new users**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Digite o **endereço de e-mail** que você copiou ao configurar sua conta de serviço na etapa 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. Na seção **Permissions** , vá para a aba **Account permissions** , e selecione ambas:

   * Visualizar dados financeiros, pedidos e respostas à pesquisa de cancelamento.
   * Gerenciar pedidos e assinaturas[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. Na aba **App permissions** , clique **Add app,** then select your app. Adicione vários aplicativos, se necessário.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Clique **Invite user**.

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. No popup de confirmação, clique **Send invite**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4 Envie a chave privada da conta de serviço para a AppsFlyer">

Faça o upload e valide a chave JSON do Google que você baixou em [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Pré-requisitos**: acesso de administrador à AppsFlyer.

**Para fazer o upload da chave privada da conta de serviço para a AppsFlyer, siga estas etapas**:

1. <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation#ativando-a-validação-de-recibos">Ative a validação de recibos</Anchor><Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation#ativando-a-validação-de-recibos">.</Anchor>
2. Na etapa **Service Account Key and Permissions** , no campo **Upload Google JSON key** , clique em [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)  **Upload**.
3. Faça o upload do arquivo JSON que você baixou em [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Clique **Validar chave**. **Atenção:**

   * após definir as credenciais e permissões da conta de serviço, pode levar até 24 horas para que você possa usá-las. Isso pode fazer com que você receba mensagens de erro ao tentar validar a chave ou realizar um teste de validação.
   * Para contornar o tempo de espera de 24 horas, no Google Play Console, navegue até qualquer aplicativo, depois vá para **Monetize** > **Products** > **Subscriptions/In-app products**, e faça uma alteração. Por exemplo, edite a descrição do seu produto e salve-a. Por exemplo, edite a descrição do seu produto e salve-a. Isso geralmente atualiza imediatamente as credenciais e permissões da conta. Feito isso, você pode desfazer as alterações.
5. Clique **Next**. A etapa **implementação do SDK** é aberta.

</Accordion>

## 3. Implementar o SDK

Nesta etapa, você prepara seus desenvolvedores para integrar a API `validateAndLog` do SDK e configurar um ambiente sandbox para testes. As versões mínimas do SDK que oferecem suporte à API `validateAndLog` mais recente são **6.17.5** para Android e **6.17.8** para iOS.

Para implementar a API validateAndLog do SDK, siga estas etapas:

1. Na etapa **implementação do SDK**, copie a **mensagem pré-escrita** exibida no dashboard.
2. Envie-a para seus desenvolvedores. ela inclui:

   * o nome e o ID do aplicativo
   * Um link para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">o guia de integração do SDK</Anchor>.
   * Instruções para configurar o ambiente sandbox (`sandbox = true`).
   * Etapas de teste (usando **TestFlight**).

   Essa mensagem fornece todas as informações que os seus desenvolvedores precisam para concluir a integração e começar os testes.
3. Clique **Next**. A etapa **Verify SDK implementation** é aberta.

## 3. Verifique a implementação do SDK

Teste a integração de receita de compras in-app e assinaturas em um ambiente sandbox para confirmar que o conector do SDK está integrado corretamente e que as notificações do servidor estão configuradas corretamente e são recebidas pela AppsFlyer.

<div id="test-sdk-implementation" />

<Accordion title="Testar a implementação do SDK">

Para verificar se a AppsFlyer recebeu payloads `validateAndLog` válidos do seu aplicativo nos últimos 7 dias, execute estas etapas:

1. Na etapa **Verify SDK implementation**, clique em **Test SDK implementation**.
2. Revise os resultados, incluindo o carimbo de data/hora do payload mais recente recebido pela AppsFlyer. Observe que essa verificação confirma apenas que as solicitações estão chegando à AppsFlyer e não verifica a integridade nem a exatidão dos dados.
3. Para validar totalmente a implementação, continue com as etapas de teste abaixo.

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="Considerações sobre o ambiente Sandbox">

No ambiente sandbox:

* Apenas eventos de compra inicial fazem com que a API validateAndLog do SDK produza um evento que é registrado pela AppsFlyer. Um evento de compra in-app é chamado de `af_purchase_sandbox_sdk`. Um evento de assinatura é chamado de `af_ars_sandbox_sdk`.
* Eventos de sandbox têm uma receita de 0.
* Para Android, os testes realizados por testadores de licença resultam em eventos sandbox mesmo que o ambiente sandbox no SDK não esteja configurado.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Teste a receita de compras in-app e assinaturas">

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**Para testar a receita de compras in-app e assinaturas**:

1. Diga aos seus desenvolvedores para seguirem as instruções deles para configurar o ambiente de sandbox para a API do SDK validateAndLog.
2. Faça uma compra de teste ou uma assinatura com o <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester no Google Play</Anchor> e o <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight no iOS</Anchor>.
3. Verifique se os eventos de teste são exibidos de uma das seguintes formas:

   * Visualize o evento no <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">Visualizador de Eventos ao Vivo.</Anchor>
   * Visualize os dados do evento em <Anchor target="_blank" href="/marketers/pt/docs/activity-metrics-in-my-dashboards">My Dashboards - Visualização de atividade</Anchor>.
4. Procure os seguintes eventos de teste:

   * O `af_purchase_sandbox_sdk` para um evento de compra.
   * O `af_ars_sandbox_sdk` para um evento de assinatura.
5. Certifique-se de que os eventos de teste incluam o seguinte:

   * Uma receita com valor **0** (para não distorcer os relatórios reais da AppsFlyer).
   * Um `af_sandbox_revenue` parâmetro que inclui o valor da receita do produto comprado, garantindo que a receita correta seja reportada.
   * Um parâmetro `af_validated` é `true`. Se `af_validated` for `false`, volte para a etapa 2 acima e valide a chave fornecida pela loja
   * Um parâmetro `af_validation_type` é `receipt_validation`.

</Accordion>

## 4. Verifique e atualize as configurações

Depois de concluir a configuração das definições acima e salvar as etapas acima, você será redirecionado para a visualização de configuração ativa, na qual poderá verificar ou atualizar as seguintes configurações:

1. Verifique se o **Tipo de produto** é **Validação de recibos**
2. Verifique se **Verify purchases with the App Store** está ativado.
3. Verifique ou atualize as seguintes configurações:

   * A configuração da **chave da App Store**
   * A configuração da **integração do SDK** setup

## 5. Lance as versões do aplicativo com a API do SDK validateAndLog

Com tudo das etapas anteriores configurado e a API do SDK validateAndLog da AppsFlyer integrada ao seu aplicativo, diga aos seus desenvolvedores para lançarem a versão do aplicativo com a API do SDK validateAndLog integrada.

Antes de os desenvolvedores publicarem a nova versão do aplicativo, certifique-se de que:

* Os eventos in-app que você quer capturar como <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation#eventos-de-compras-in-app-e-parâmetros-para-a-validação-de-recibos">compra in-app ou assinatura</Anchor> não sejam bloqueados por nenhuma das regras de validação que você configurou na AppsFlyer.
* Seus desenvolvedores têm todas as flags de sandbox definidas como `false`.

[<Image alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

Depois que o aplicativo com a API do SDK validateAndLog for lançado, os <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation#eventos-de-compras-in-app-e-parâmetros-para-a-validação-de-recibos">eventos de compra in-app e de assinatura</Anchor> serão gerados e disponibilizados em todos os dashboards da AppsFlyer, bem como em relatórios de dados agregados e relatórios de dados brutos.

Os eventos só são gerados para usuários que atualizaram para uma versão do aplicativo que inclui a API SDK validateAndLog. Como resultado, é esperada uma discrepância entre os dados de receita do aplicativo e os dados da loja até que a versão atualizada do aplicativo seja totalmente adotada.

<div data-zendesk-anchors="h_migrating-from-legacy=fazer-upgrade-para-a-nova-valida%C3%A7%C3%A3o-de-recibos upgrade-to-new-receipt-validation=fazer-upgrade-para-a-nova-valida%C3%A7%C3%A3o-de-recibos whats-new-in-receipt-validation=h_migration_key_differences prepare-the-migration=h_migration_what_to_plan switch-to-roi360-store-revenue=h_migration_upgrade_path overview=escrit%C3%B3rios h_01KD0RY1HMV71TGDZZX7JWM3XJ=escrit%C3%B3rios h_01KD0RY1HMMSR4ZDW5GF4N05P1=nota step-1-ios-set-up-app-store-connect-keys=etapa-1-ios-configurar-as-chaves-do-app-store-connect h_01KD0RY1HM14KNGKADCBMHJXH6=etapa-1-ios-configurar-as-chaves-do-app-store-connect h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=passo-1-android-configure-a-service-account-key-e-permiss%C3%B5es h_01KD0RY1HMG9DGKGEY8XVR3K7Z=passo-1-android-configure-a-service-account-key-e-permiss%C3%B5es h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=3-implementar-o-sdk h_01KD0RY1HN63X3WM1RH19W2HZ5=3-implementar-o-sdk step-3-verify-sdk-implementation=3-verifique-a-implementa%C3%A7%C3%A3o-do-sdk h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=3-verifique-a-implementa%C3%A7%C3%A3o-do-sdk h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=4-verifique-e-atualize-as-configura%C3%A7%C3%B5es h_01KD0RY1HN2HZEW9ANBPNRMXPP=4-verifique-e-atualize-as-configura%C3%A7%C3%B5es step-5-release-the-app-versions-with-the-validateandlog-sdk-api=5-lance-as-vers%C3%B5es-do-aplicativo-com-a-api-do-sdk-validateandlog h_01KD0RY1HNECTDNNHK78F9KDPS=5-lance-as-vers%C3%B5es-do-aplicativo-com-a-api-do-sdk-validateandlog" />
