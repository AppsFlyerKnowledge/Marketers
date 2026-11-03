---
title: Meça a atribuição no mercado doméstico chinês
metadata:
  keywords:
    - Advertisers
    - China
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-17T12:33:29Z'
  edited_at: '2026-08-19T00:09:43Z'
  id: 360002049858
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/360002049858
---
> **Visão geral:** Atribuição de dispositivos Android sem GAID usando OAID ou IMEI. Melhores práticas para visualizar dados de atribuição no AppsFlyer.

## Atribuição de aplicativos Android no mercado doméstico chinês

Na China, os proprietários de aplicativos enfrentam vários desafios:

* O Google Play Services (GPS) não está ativo na maioria dos dispositivos Android, o que significa que eles não têm GAID.
* O uso de lojas de aplicativos Android de terceiros cria oportunidades de hijacking de loja por fabricantes de dispositivos.
* Os servidores de atribuição são inacessíveis ou demoram para responder.
* Gerenciar e visualizar dados de atribuição do Google Play e de lojas de aplicativos Android de terceiros.

Com o AppsFlyer, esses desafios podem ser superados por meio de:

* Implementar atribuição com base em <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor>
* Usar o IMEI do dispositivo como alternativa ao GAID em dispositivos com Android 28 ou anterior
* Preparar APKs com identificadores exclusivos para detectar hijacking de loja no Android
* Configurar links de atribuição reconhecidos na China

## Preparar o aplicativo

Integre o SDK ao aplicativo e prepare o APK usando um dos métodos de acordo com a versão do Android dos dispositivos-alvo.

<div id="integrate-the-sdk-in-the-app" />

<Accordion title="Integrar o SDK ao aplicativo">

**Use IMEI e/ou OAID em vez de GAID**

Em geral, o Google Play Services não é instalado em dispositivos Android fornecidos na China. Isso significa que não há GAID para usar como identificador exclusivo de atribuição.

Uma alternativa ao uso do GAID é o IMEI e/ou OAID, quando disponíveis, para permitir o registro de atribuição.

**OAID:**

* É um ID de publicidade redefinível pelo usuário, semelhante ao GAID e ao IDFA.
* Requer o SDK Android da AppsFlyer V5.1.0 ou posterior.
* A partir do SDK da AppsFlyer V5.4.0, o SDK tentará coletar o OAID automaticamente por padrão.
* Vários fabricantes concluíram testes de interoperabilidade de atribuição por OAID com a AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">Incluindo Huawei, Lenovo, OPRO, Vivo, Samsung e Xiaomi,</Anchor>

**IMEI**:

* O SDK da AppsFlyer impede o acesso ao IMEI, a menos que seja configurado de outra forma. A premissa geral é que o Google Play Services esteja ativo no dispositivo e que o IMEI não seja necessário. Na China, não é o caso.
* Ao integrar o SDK da AppsFlyer ao seu aplicativo, o acesso ao IMEI precisa ser habilitado.
* Quando necessário, o OAID e o IMEI devem ser implementados simultaneamente para garantir a atribuição independentemente da versão do Android.
* Isso acontece porque o acesso ao IMEI é restrito a partir do <Anchor target="_blank" href="https://developer.android.com/training/articles/user-data-ids">Android 10 (nível 29 da API)</Anchor>, lançado no fim de 2019. Nem o seu aplicativo nem o SDK da AppsFlyer podem coletar esses identificadores. Quando nenhum identificador está disponível, a AppsFlyer recorre à <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">atribuição por modelo probabilístico.</Anchor>

**Antes de começar**:

* É necessário usar o SDK Android da AppsFlyer V5.1.0 ou posterior.

Use um dos procedimentos a seguir:

<div id="oaid-starting-from-android-api-level-29" />

<Accordion title="OAID a partir do nível 29 da API Android">

Há dois métodos para coletar o OAID:

* setCollectOaid
* setOaidData

<Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk#msa-sdk">Instruções para habilitar os métodos da API</Anchor>

</Accordion>

<div id="imei-android-api-level-2328" />

<Accordion title="IMEI no nível 23-28 da API Android">

Há dois métodos para coletar o IMEI:

* setImeiData
* setCollectIMEI(true)

Use o exemplo de código a seguir para integrar o SDK. Este exemplo de código usa o método `onConversionDataSuccess`. Este é o nome do método para obter dados de conversão a partir do SDK V5.0. Se você estiver usando uma versão do SDK anterior à V5.0, o nome do método é `onInstallConversionDataLoaded`. Recomendamos que você atualize para a versão <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">atual do SDK.</Anchor>

**Observação:** o Android no nível 23 da API ou superior exige a permissão do usuário, por meio de um prompt, para acessar o IMEI. Isso pode fazer com que o IMEI seja recuperado após a ativação da API StartTracking. A partir do nível 29 da API, o acesso ao IMEI é restrito.

```java
public class AFApplication extends Application {
    private static final String AF_DEV_KEY = "";
    private static AFApplication instance;
    @Override
    public void onCreate() {
      //Se você quiser mostrar o log de depuração.
      AppsFlyerLib.getInstance().setDebugLog(true);  
 //O desenvolvedor coleta o imei e o ID do Android e depois os envia ao SDK da AppsFlyer.  

	  AppsFlyerLib.getInstance().setImeiData("customer imei");  
 AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");\n      //Ou use as duas APIs abaixo para permitir que o SDK da AppsFlyer colete IMEI & android id, independentemente de \n      //o Google Play Services existir ou não.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);  
      final AppsFlyerConversionListener conversionDataListener = new AppsFlyerConversionListener() {
          @Override
          public void onConversionDataSuccess(Map<String, Object=""> map) {} 
    	  @Override
          public void onConversionDataFail(String error) {}    
    	  @Override
          public void onAppOpenAttribution(Map<string, string=""> map) {}
          @Override
          public void onAttributionFailure(String s) {}
  	};
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
      AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
  }
    @Override
    protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
    public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```

Na primeira inicialização do aplicativo, uma solicitação da permissão READ\_PHONE\_STATE é enviada ao usuário no callback onResume() da MainActivity.

build.gradle no módulo do aplicativo****

```java
allprojects {
    repositories {
       ....
       maven { url 'https://jitpack.io'}
    }
}
dependencies {
    implementation 'com.github.tbruyelle:rxpermissions:0.10.2'
}
```

<Tabs>
<Tab title="MainActivity">

```java
import androidx.appcompat.app. AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       startIMEILogic();
   }
   private void startIMEILogic() {
       SharedPreferences permissions_flags = getSharedPreferences("appsflyer-data", MODE_PRIVATE);
       if (!permissions_flags.contains(Manifest.permission.READ_PHONE_STATE)) {
           requestIMEIPermissions();
       }
   }
   private void requestIMEIPermissions() {
       if (ContextCompat.checkSelfPermission(this,
               Manifest.permission.READ_PHONE_STATE)
               != PackageManager.PERMISSION_GRANTED) {
           ActivityCompat.requestPermissions(this,
                   new String[]{Manifest.permission.READ_PHONE_STATE},
                   MY_PERMISSIONS_REQUEST_READ_PHONE_STATE);
       } else {
           //A permissão já foi concedida
           SharedPreferences. Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, true);
           permissionsFlagsEditor.apply();
       }
   }
   @Override
   public void onRequestPermissionsResult(int requestCode,
                                          String[] permissions, int[] grantResults) {
       if (requestCode == MY_PERMISSIONS_REQUEST_READ_PHONE_STATE) {
           SharedPreferences. Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           boolean granted;
           // Se a solicitação for cancelada, as matrizes de resultados ficarão vazias.
           if (grantResults.length > 0
                   && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
               // a permissão foi concedida!
               granted = true;
               AppsFlyerLib.getInstance().setCollectIMEI(true);
           } else {
               // permissão negada!
               granted = false;
           }
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(0);
           AppsFlyerLib.getInstance().reportTrackSession(this);
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(5);
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, granted);
           permissionsFlagsEditor.apply();
       }
   }
}
```

</Tab>

<Tab title="MainActivity (legado)">

```java
public class MainActivity extends AppCompactActivity {
    @Override
    protected void onResume() {
        super.onResume();
        final RxPermissions rxPermissions = new RxPermissions(this);
         if(RxPreference. Instance().getBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, false){
          return;
         }
         if(rxPermissions.isGranted(Manifest.permission.READ_PHONE_STATE)) {
            return;
         }
          RxPreference. Instance().putBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, true);
        rxPermissions.request(Manifest.permission.READ_PHONE_STATE)
                .subscribe(granted -> {
                    if (granted) {  
AppsFlyerLib.getInstance().setImeiData("customer imei");  
AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");  
//ou  
AppsFlyerLib.getInstance().setCollectIMEI(true);  
AppsFlyerLib.getInstance().setCollectAndroidID(true);  
//Observação: aqui, a API de relatório de sessão é reportTrackSession(), não startTracking()
                        AppsFlyerLib.getInstance().reportTrackSession(AFApplication.getAppInstance());
                    } else {
                    }
                });
    }
}
```

</Tab>
</Tabs>

</Accordion>

Há dois métodos para coletar o IMEI:

* setImeiData
* setCollectIMEI(true)

Use o exemplo de código a seguir para integrar o SDK. **Observação:** o exemplo de código usa o método `onConversionDataSuccess` para obter dados de conversão. Esse é o nome do método a partir do SDK V5. Se você estiver usando uma versão do SDK anterior à 5.0, o nome do método é `onInstallConversionDataLoaded`. Recomendamos que você atualize para o SDK 5.0.0. Clique <Anchor target="_blank" href="/marketers/pt/docs/links-to-appsflyer-sdk-release-notes">aqui</Anchor> para saber mais.

```java
 Public class AFApplication extends Application {
   private static final String AF_DEV_KEY = "";
   private static AFApplication instance;
   @Override
   public void onCreate() {
      //Se você quiser mostrar o log de depuração.
      AppsFlyerLib.getInstance().setDebugLog(true); //O desenvolvedor coleta o IMEI e o ID do Android e, em seguida, os envia para o SDK da AppsFlyer. AppsFlyerLib.getInstance().setImeiData("customer imei"); 
	  AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Ou use as duas APIs abaixo para permitir que o SDK da AppsFlyer colete o IMEI & android id
      //independentemente de o Google Play Service existir ou não.
      AppsFlyerConversionListener() {
       @Override
       public void onConversionDataSuccess(Map<String, Object=""> map) {}
       @Override
       public void onConversionDataFail(String error) {}
       @Override
       public void onAppOpenAttribution(Map<string, string=""> map) {}
       @Override
       public void onAttributionFailure(String s) {}
     }
     AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
     AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
   }  
   @Override
     protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
  public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```


</Accordion>

<div id="preparing-the-apk" />

<Accordion title="Preparando o APK">

Selecione como os dados de atribuição serão exibidos na AppsFlyer entre as opções a seguir:

* (melhores práticas) **Aplicativo único:** Os dados de todas as lojas de aplicativos Android de terceiros (mercado interno da China) são exibidos em um único aplicativo, mas separado. Isso significa que você verá todos os dados de atribuição das lojas chinesas locais em um único aplicativo na AppsFlyer. Para usar este método, continue na seção a seguir para [adicionar o aplicativo na AppsFlyer](/docs/measure-attribution-in-the-chinese-domestic-market#adicione-o-aplicativo-à-appsflyer).
* **Aplicativo único consolidado com a loja Google Play:** A atribuição tanto das lojas de aplicativos de terceiros quanto da loja Google Play é exibida como uma única entidade. Essa opção exige que o nome do pacote da loja Google Play e das lojas de terceiros seja idêntico. O uso desta opção pressupõe que o aplicativo já esteja definido na AppsFlyer. Para usar este método, continue em [preparação do APK/manifest](/docs/measure-attribution-in-the-chinese-domestic-market#preparando-o-apkmanifest) na seção a seguir.
* **Vários aplicativos** significa que os dados de atribuição de cada loja são mostrados em um aplicativo separado. Por exemplo, cada um dos itens a seguir é mostrado separadamente: Google Play Store, loja de terceiros A, loja de terceiros B e assim por diante. Para usar este método, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">vários aplicativos</Anchor>.

### Adicione o aplicativo à AppsFlyer

**Para adicionar o aplicativo à AppsFlyer**:

1. Na AppsFlyer, clique em **My Apps**.
2. Clique em **Add App**.  
   A janela Add Your App é aberta.
3. Selecione **Android out of store APK**.
4. Preencha os seguintes campos:  
   * **Nome do pacote Android**: texto livre
   * **Nome do canal**: deve ser idêntico ao nome do canal no manifesto, conforme explicado na seção a seguir. A melhor prática é definir este campo como **cn\_market**.
   * **URL do aplicativo**

**Observação**: você pode criar o aplicativo usando a opção **Pendente de aprovação ou não publicado**, mas isso não é recomendado. Consulte seu CSM antes de usar este método.

### Preparando o APK/manifest

**Para preparar um APK/manifest separado para cada loja de aplicativos de terceiros, faça o seguinte:**

1. Adicione o seguinte ao manifest para identificar o tráfego da China:

   ```java
   < meta-data android:name="CHANNEL" android:value="cn_market">
   ```

   **Observação:** Os parâmetros diferenciam maiúsculas e minúsculas. Recomendamos que você defina o canal como **cn\_market**.
2. Escolha um dos métodos a seguir para identificar a loja:
   * **Método do manifest:** Adicione a seguinte linha ao arquivo AndoridManifest.xml. O valor de AF\_STORE precisa ser exclusivo para cada loja.

     ```xml
     <meta-data android:name="AF_STORE" android:value="example_store"/>
     ```

     **--OU--**
   * **Método da API:** Prepare um APK separado para cada loja de aplicativos de terceiros. Faça a chamada para a API setOutOfStore para configurar o valor AF\_STORE. Defina um valor exclusivo para cada loja.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("example_store")
     ```

Os métodos descritos definem o parâmetro AF\_STORE, que por sua vez define o campo install\_app\_store nos dados de atribuição. Esse campo está disponível em:

* Análise de cohort
* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatórios de dados brutos</Anchor>

</Accordion>

## Considerações adicionais sobre atribuição

<div id="workaround-for-stores-without-attribution-link-support" />

<Accordion title="Solução alternativa para lojas sem suporte a links de atribuição">

Muitas lojas de aplicativos Android de terceiros na China também vendem tráfego, o que significa que também são uma plataforma de anúncios. Em alguns casos, essas lojas não oferecem suporte ao uso de links de atribuição. As seguintes soluções alternativas podem ser usadas:

* install\_app\_store field: (recomendado) Quando a instalação ocorre sem um link de atribuição, a AppsFlyer atribui a instalação a instalações orgânicas. Ao usar o campo install\_app\_store, você pode identificar a fonte real da instalação. Observação: o campo install\_app\_store é definido usando o parâmetro AF\_STORE descrito na seção anterior.
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-factory-preinstall-using-manifest-android">Nome de pré-instalação</Anchor> no arquivo manifest. Usar o nome de pré-instalação contido no manifest. A desvantagem desse método é que, se o APK de pré-instalação vazar para o mercado, as informações de atribuição ficarão incorretas. Ao usar esse método, verifique se você tem os termos comerciais adequados para proteger seu APK.

</Accordion>

<div id="china-domestic-attribution-links" />

<Accordion title="Links de atribuição domésticos da China">

Ao preparar links de atribuição, leve em consideração o seguinte:

**Links baseados na China**

Para canais de mídia que têm apenas tráfego doméstico (chinês), use os links de domínio detalhados aqui. Esses links são reconhecidos na China e oferecem uma experiência superior ao usuário.

Para links de atribuição regulares, use: https://app.aflink.com - (aflink.com)

Para links de atribuição do OneLink, use: https://go.onelnk.com (onelnk.com) Observação: antes de usar o domínio onelnk.com, entre em contato com seu CSM da AppsFlyer.

Observe que, no WeChat, apenas **onelnk.com** está na lista de permissões, enquanto **onelink.me** está bloqueado

**Use af\_r**

Use af\_r para garantir que os usuários sejam redirecionados para uma URL de download de APK ou para uma loja de APK, e não para a Google Play Store.

Observação: com frequência, os canais de mídia integrados domésticos da China têm esse parâmetro definido como &redirect=false no modelo de URL de atribuição padrão. Isso significa que o redirecionamento será feito pelas plataformas de anúncios, e não pela AppsFlyer.

Para mais informações sobre canais de mídia integrados:  
<Anchor target="_blank" href="/marketers/pt/docs/android-app-promotion-in-china">Promoção de aplicativo Android na China</Anchor>

</Accordion>

<div id="detecting-store-hijacking" />

<Accordion title="Detecção de hijacking de loja">

Em cenários de loja de aplicativos de terceiros, os usuários primeiro instalam o aplicativo na loja de terceiros do canal de mídia (ad networks). No caso de hijacking de instalação, um pop-up de aviso sugere que o usuário instale/atualize o aplicativo diretamente da loja de aplicativos do fabricante do dispositivo (telefone). Se o usuário concordar, ele será redirecionado para fazer o download na loja de aplicativos do fabricante e o APK será baixado. Isso significa que o fabricante do dispositivo sequestrou a instalação.

O exemplo a seguir ilustra um fluxo legítimo e um fluxo sequestrado:

**Fluxo legítimo**

Um usuário do aplicativo clica em um anúncio exibido pela media-example e faz o download do aplicativo imediatamente ou é redirecionado para a legitimate-app-store para fazer o download do aplicativo. Na AppsFlyer, as seguintes informações de atribuição são registradas:

* **Canal de mídia**: media-example
* **Loja de aplicativos de instalação**: legitimate-app-store

**Fluxo sequestrado**

Um usuário do aplicativo clica em um anúncio exibido por media-example. Quando o download é iniciado, um pop-up de aviso aparece, sugerindo que o usuário faça o download do aplicativo na loja de aplicativos do fabricante do dispositivo. Se o usuário concordar, será redirecionado para a loja do fabricante e fará o download do aplicativo. No AppsFlyer, as seguintes informações de atribuição são registradas:

* **Canal de mídia:** media-example
* **install-app-store**: manufacturer-store

**Identificando o evento de sequestro no AppsFlyer**

Para identificar a instalação sequestrada, compare os campos canal de mídia e install-app-store. Uma discrepância entre o install-app-store esperado e o install-app-store real indica um sequestro de instalação.

</Accordion>

<div data-zendesk-anchors="attribution-android-apps-in-the-chinese-domestic-market=atribui%C3%A7%C3%A3o-de-aplicativos-android-no-mercado-dom%C3%A9stico-chin%C3%AAs preparing-the-app=preparar-o-aplicativo adding-the-app-in-appsflyer=adicione-o-aplicativo-%C3%A0-appsflyer preparing-the-apkmanifest=preparando-o-apkmanifest additional-attribution-considerations=considera%C3%A7%C3%B5es-adicionais-sobre-atribui%C3%A7%C3%A3o" />
