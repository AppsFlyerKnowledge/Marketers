---
title: Extensão do SDK do Adobe Launch
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2026-08-19T00:14:25Z'
  id: 360000939097
  locale: pt
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/pt/articles/360000939097
---
> **At a glance:** **Visão geral:** Envie dados para o SDK do Adobe Launch e o SDK da AppsFlyer com a implementação única da extensão do SDK do Adobe Launch da AppsFlyer.

<div id="overview" />

## Visão geral

O SDK do Adobe Launch é parte integrante da Adobe Experience Platform. O Adobe Experience Platform ajuda as empresas a reunir, consolidar e analisar dados de várias aplicações e plataformas. Permite aos proprietários de empresas e programadores compreender melhor o comportamento dos clientes para otimizar a experiência e o fornecimento de conteúdos. Se seu aplicativo implementar o SDK do Adobe Launch e o SDK da AppsFlyer, será possível enviar dados para ambos com uma única implementação da **extensão do SDK do Adobe Launch da AppsFlyer**. Isso reduz a complexidade global do seu processo de desenvolvimento e contribui para uma base de código mais limpa e de fácil manutenção.

> 📘 **Note**
>
> **Importante!**
>
> Se estiver usando a extensão do Adobe Launch, não é necessária a <Anchor target="_blank" href="/marketers/pt/docs/adobe-analytics-integration-with-appsflyer">integração padrão do Adobe Analytics</Anchor>.

<div id="prerequisites" />

## Pré-requisitos

São necessárias algumas coisas antes de integrar a extensão Adobe SDK da AppsFlyer.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="Recupere a sua chave do desenvolvedor da AppsFlyer">

![dev_key.png](https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png)

1. No painel do seu aplicativo, clique em ***Configurações do aplicativo*** abaixo de ***Configurações*** no menu à esquerda.
2. Em ***Instalação do SDK***, copie ***chave do desenvolvedor***.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="Obtenha seu ID do aplicativo">

* Para Android: o ID da aplicação é o nome do pacote, por exemplo, exemplo.com.app.
* Para iOS: o ID da aplicação é o ID do iTunes da aplicação sem o prefixo *id*, por exemplo, 123456748.

</Accordion>

<div id="step-1-configuring-adobe-launch" />

## Passo 1: Configuração do Adobe Launch

Siga as instruções aqui para configurar o Adobe Launch.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Crie uma nova propriedade no Adobe Launch">

![Observação](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Faça login no Adobe Experience Cloud.
2. Selecione ***Lançamento***.
3. Clique em ***Ir para lançamento***.
4. Clique em *Nova propriedade*.
5. Dê um nome à propriedade e selecione ***Mobile***.
6. Clique em ***Salvar***.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 Instalar as extensões necessárias do Adobe Launch">

Instale as seguintes extensões no Adobe Launch:

![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics - conecte os dados registrados do SDK ao módulo Adobe Analytics.
* Extensão SDK da AppsFlyer - envia dados e eventos para a Adobe e a AppsFlyer usando o SDK do Adobe Launch.
* Perfil do Adobe - permite que o SDK armazene dados num perfil do lado do cliente.
* Adobe Mobile Core - permite a configuração do SDK para mobile e fornece acesso a eventos e condições do ciclo de vida predefinidos.

<div id="installing-adobe-analytics-extension" />

#### Instalar a extensão do Adobe Analytics

1. Faça login no Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Crie um conjunto de relatórios</Anchor>.
3. Faça login novamente no Adobe Launch.
4. Na lista de propriedades, clique na propriedade que criou anteriormente.
5. Clique em ***Extensões***.
6. Pesquise e instale ***Adobe Analytics***.
7. Em ***Conjuntos de relatórios***especifique o conjunto de relatórios criados no passo 2.
8. Clique em ***Salvar***.

<div id="installing-appsflyer-sdk-extension" />

#### Instalar a extensão SDK da AppsFlyer

1. Selecione ***Extensões*** novamente.
2. Procure e instale a ***extensão do SDK da AppsFlyer***.
3. Em ***ID do aplicativo iOS da AppsFlyer***especifique o ID do aplicativo iOS que obteve no passo dos pré-requisitos.
4. Em ***Chave do desenvolvedor da AppsFlyer*** especifique a chave do desenvolvedor que você obteve na etapa de pré-requisitos.
5. Ative ***Enviar dados de atribuição para o Adobe Analytics***. Observe que existem algumas <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">restrições ao compartilhamento de dados ao nível do usuário com plataformas de análise de terceiros</Anchor>.
6. Clique em ***Salvar***.

<div id="install-profile-and-mobile-core-extension" />

#### Instale a extensão Profile e Mobile Core

1. Selecione ***Extensões*** novamente.
2. Procure e instale ***Perfil***.
3. Procure e instale ***Mobile Core***.
   * Ao instalar o Mobile Core, basta guardar a extensão tal como está. Não é necessário especificar o ***servidor do Experience Cloud***.

</Accordion>

<div id="step-2-implementing-appsflyer-adobe-sdk-extension" />

## Passo 2: Implementação da extensão do SDK da AppsFlyer para Adobe

Siga as instruções nesta seção para implementar a extensão do SDK do Adobe no seu aplicativo.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 Adicione o SDK ao aplicativo">

![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Na sua propriedade do Adobe, selecione ***Ambientes***.
2. Selecione o ambiente para o qual pretende implementar o SDK.
3. No lado direito, clique no ícone da caixa.
4. Copie os trechos de código da janela que será aberta e siga as instruções. Se o Adobe estiver sendo configurado pelo profissional de marketing, envie estes trechos de código ao programador do aplicativo.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 Publicando o ambiente">

Para completar a implementação do SDK, é necessário publicar o ambiente numa biblioteca.

![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Na sua propriedade Adobe, selecione ***Publicar***.
2. Clique em ***Adicionar nova biblioteca***.
3. Dê um nome e, em Ambiente, selecione ***Desenvolvimento***.
4. Clique em ***Salvar e compilar para desenvolvimento***.
5. Quando a compilação estiver concluída, em ***Desenvolvimento***clique nos três pontos ao lado da biblioteca e selecione ***Enviar para aprovação***.
6. Em ***Enviado***clique nos três pontos ao lado da biblioteca e selecione ***Compilar para teste***.
7. Quando a compilação estiver concluída, clique nos três pontos ao lado da biblioteca e selecione ***Aprovar para publicação***.
8. Em ***Aprovar***clique nos três pontos ao lado da biblioteca e selecione ***Compilar e publicar na produção***.

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 Como adicionar o referenciador da instalação do Android ao seu aplicativo">

O referenciador da instalação do Android melhora a precisão da atribuição, protege contra fraudes na instalação e muito mais. É compatível com o SDK da AppsFlyer para Android versão 4.8.6.

> 📘 **Note**
>
> **Importante!**
>
> O Google desativou o[BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html) em março de 2020.
>
> * Essa alteração não afeta o aplicativo.
> * Você ainda pode precisar do BroadcastReceiver para atribuição fora da loja. Verifique com a loja onde o aplicativo está listado para ter certeza.
> * Implementar o referenciador de instalação é obrigatório agora.

Há duas formas de adicionar o referenciador da instalação ao seu aplicativo:

* Usando o Gradle (recomendado)
* Como adicionar o referenciador da instalação manualmente

<Tabs>
<Tab title="Como adicionar o referenciador da instalação usando o Gradle Como adicionar o referenciador da instalação manualmente">

Adicione o referenciador da instalação do Android como uma dependência. Você pode encontrar a versão mais recente <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">aqui</Anchor>.

1.
   ```java
   dependencies {
   //certifique-se de usar a versão mais recente do SDK: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Sincronize o projeto para recuperar as dependências - veja a seguinte captura de tela:![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

Os desenvolvedores que estiverem usando ProGuard, e quiserem usar a API do novo referenciador do Google, devem definir o seguinte regra do ProGuard:`-dontwarn com.android.installreferrer`

</Tab>

<Tab title="https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Baixe o aar do referenciador da instalação</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Adicione-o ao projeto</Anchor>
3. Adicione a seguinte permissão ao manifesto: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 Definindo permissões necessárias">

Adicionar permissões ajuda a aumentar a taxa de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">atribuição de modelagem probabilística</Anchor>. Também permite que o SDK envie mais dados, como Wifi e dados da rede da operadora. Você pode encontrar esses dados em <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatórios de dados brutos</Anchor> e usá-los para análise e otimização de campanhas.

<div id="add-required-permissions" />

#### Adicionando permissões necessárias

1. Adicione as seguintes permissões ao AndroidManifest.xml:  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Opcional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

<div id="using-the-adobe-sdk-extension" />

## Usando a extensão do SDK do Adobe

Agora você pode começar a usar a extensão do SDK do Adobe para enviar dados para o Adobe e para a AppsFlyer.

> 📘 **Note**
>
> **Importante!**
>
> Atualmente, a extensão do SDK do Adobe Launch apenas suporta a obtenção de dados de conversão e o envio de eventos. No entanto, ao adicionar a extensão do SDK do Adobe Launch à sua aplicação, o SDK da AppsFlyer também é adicionado. Como consequência, qualquer funcionalidade atualmente em falta na extensão do SDK Adobe pode ser implementada usando o SDK da AppsFlyer.

<div id="sending-events" />

<Accordion title="Enviando eventos">

Os eventos in-app fornecem insight do que está acontecendo em seu aplicativo. Recomendamos reservar um tempo e definir os eventos que você deseja registrar. O registro de eventos in-app ajuda a mensurar KPIs como ROI (retorno sobre o investimento) e LTV (Lifetime Value).

A extensão do SDK do Adobe Launch permite enviar dados de eventos in-app para o Adobe e para a AppsFlyer. Em seguida, você pode usar o Adobe Analytics para analisar o comportamento do usuário e a AppsFlyer para analisar o ROI e o LTV.

<Tabs>
<Tab title="Android iOS">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param"); MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="Exemplo">

```java
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

O envio dos eventos conforme especificado no código acima cria um evento no painel da AppsFlyer chamado af\_purchase com uma receita de 200 USD. Este evento também é enviado e aparece no Adobe Analytics.

Todos os <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">dados de conversão</Anchor> que são enviados com eventos são prefixados por ***Appsflyer***. Consulte a tabela a seguir para mais detalhes.

| Variáveis de dados de conversão prefixadas |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Os dados de conversão estão disponíveis no Analysis Workspace do Adobe Analytics. Para mais informações sobre como migrar as regras de processamento do Adobe Mobile Services para o Adobe Analytics, consulte [a documentação da Adobe](https://experienceleague.adobe.com/en/docs/analytics/technotes/migrate-mobile).

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="Use-o para deep linking e deferred deep linking.">

Os deep links e deferred deep linking permitem melhorar a sua experiência de usuário. Eles permitem abrir o aplicativo em atividades específicas e personalizar o conteúdo de acordo com os dados da campanha.

Para obter dados do deep linking, implemente os callbacks de extensão.

<Tabs>
<Tab title="Android iOS">

Na classe de aplicações globais, implemente o seguinte código:

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// dados de conversão retornados 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "este é o primeiro lançamento e uma instalação não orgânica!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// deep link direto - redirecionar usuário
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="Exemplo">

Em AppDelegate.m, implemente o seguinte código:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"este é o primeiro lançamento e uma instalação não orgânica!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

<div id="connecting-appsflyer-conversion-data" />

## Obtenha dados de conversão da AppsFlyer

Os dados de conversão são enviados com eventos para a plataforma Adobe. Estas variáveis permitem aplicar lógica e regras às dimensões, métricas ou filtros do relatório.

1. Faça login na sua conta do Adobe Analytics.

   ![](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)
2. Navegue até **Admin** > **Report Suites**
3. Selecione o Report Suite que foi configurado durante a implementação do Adobe Analytics.
4. Selecione **Geral** > **Regras de processamento**.
5. Crie regras de processamento para mapear as variáveis de contexto da AppsFlyer para eVars.

Consulte a tabela a seguir para mapear as variáveis de contexto da AppsFlyer:

| **Nome recomendado para mapear** | **Dados de conversão** |
| --- | --- |
| Janela de visualização da AppsFlyer | appsflyer.af\_click\_lookback |
| Tempo de instalação da AppsFlyer | appsflyer.install\_time |
| Custo AppsFlyer Centavos US | appsflyer.cost\_cents\_USD |
| Fonte de mídia AppsFlyer | appsflyer.media\_source |
| Conjunto de Anúncios AppsFlyer | appsflyer.af\_adset |
| Hora do Clique AppsFlyer | appsflyer.click\_time |
| Custo Original AppsFlyer | appsflyer.orig\_cost |
| Campanha AppsFlyer | appsflyer.campaign |

<div id="using-appsflyer-mapped-conversion-data-for-analytics-and-analysis" />

### Usando os dados de conversão mapeados da AppsFlyer para análises

Todos os dados provenientes do SDK estão disponíveis no conjunto de relatórios do Adobe Analytics que está conectado ao aplicativo.

É possível usar os dados e suas dimensões e métricas relacionadas nos relatórios e painéis gerados do Adobe Analytics. Esses dados também estão disponíveis no painel da AppsFlyer para atribuição e análise de eventos in-app.