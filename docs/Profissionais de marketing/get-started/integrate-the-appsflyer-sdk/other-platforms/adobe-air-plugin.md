---
title: Plugin do Adobe AIR
metadata:
  keywords:
    - github
    - Adobe
    - Air
    - Advertisers
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
  created_at: '2013-12-09T11:32:45Z'
  edited_at: '2026-08-18T00:15:07Z'
  id: 207032226
  locale: pt
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/pt/articles/207032226
---
> **Visão geral:** integre o SDK da AppsFlyer a aplicativos iOS/Android desenvolvidos com a plataforma de desenvolvimento Adobe AIR para medir instalações, eventos in-app, canais de mídia e muito mais.

<div id="plugin-information" />

## Informações do plugin

Plataformas compatíveis:

* com o Android
* iOS 6+

Com base em:

* iOS AppsFlyer SDK V6.0.3
* Android AppsFlyer SDK V5.4.1

<div id="installation-and-implementation" />

## Instalação e implementação

<div id="installation" />

<Accordion title="Instalação">

Faça download do arquivo <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/AppsFlyerAIRExtension.ane">AppsFlyerAIRExtension.ane</Anchor> na pasta bin. Adicione o ANE ao seu projeto e verifique se a IDE está configurada para empacotá-lo.

Se o item a seguir não tiver sido adicionado automaticamente, adicione-o ao APP\_NAME-app.xml:

```html Markup
<extensions>
  <extensionID>com.appsflyer.adobeair</extensionID>
</extensions>
```

<div id="notes-for-android-apps" />

> 📘 **Observações para aplicativos Android**
>
> * No dashboard da AppsFlyer, você precisará adicionar o prefixo "air." ao nome do pacote, pois ele é adicionado automaticamente pelo Air. Por exemplo - um aplicativo com o nome de pacote "**com.test.android**", deve definir o ID do aplicativo no dashboard da AppsFlyer como "**air.com.test.android**".
> * Adicione as permissões a seguir ao Android Manifest (na descrição do aplicativo `APP_NAME-app.xml`):
>
>   ```html Markup
>   <uses-permission android:name="android.permission.INTERNET"/>
>   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
>   <uses-permission android:name="com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE" />
>   ```
> * Adicione a metatag a seguir ao Android Manifest, dentro da tag application (na descrição do aplicativo `APP_NAME-app.xml`):
>
>
>   ```html Markup
>   meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
>   ```
>
> Como resultado, seu Manifest deve ficar assim:
>
> [![](https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png)](https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png)
>
> **Importante:** devido a algumas limitações no <Anchor target="_blank" href="https://help.adobe.com/en_US/air/build/WS5b3ccc516d4fbf351e63e3d118666ade46-7fd9.html">ADT</Anchor>, após a criação do APK, faltam alguns arquivos importantes.
>
> Para adicionar esses arquivos (com a ajuda de **script automatizado** ):
>
> 1. Coloque em um único diretório de sua escolha:
>    * Arquivo APK
>    * Keystore usada para assinar o APK
>    * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/af_apk_fix.sh">af\_apk\_fix.sh script</Anchor>
> 2. Execute `./af_apk_fix.sh` e insira as informações solicitadas quando elas forem pedidas.
>
> Veja o que o script está fazendo. Em caso de qualquer problema, você pode executar essas etapas manualmente:
>
> 1. Decodifique o APK usando <Anchor target="_blank" href="https://ibotpeaches.github.io/Apktool/">apktool</Anchor>. Isso criará a pasta nome\_do\_aplicativo.
>    `apktool d app_name.apk`
> 2. Faça o download do [jar/aar do SDK da AppsFlyer](https://repo.maven.apache.org/maven2/com/appsflyer/af-android-sdk/5.4.1/af-android-sdk-5.4.1.aar) da mesma versão usada no APK.
> 3. Extraia os arquivos `a-` e `b-` do jar (renomeando o jar para zip) e coloque-os na pasta com o apk descompilado em `app_name/unknown/com/appsflyer/internal`
> 4. Edite o `apktool.yml` adicionando estas linhas em `unknownFiles:`
>
>    ```
>    com/appsflyer/internal/b-: '0'
>    com/appsflyer/internal/a-: '0'
>    ```
>
>    Veja a captura de tela de exemplo a seguir.
>
>    [![](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)
> 5. Compile o APK novamente (ele aparecerá na pasta `app_name/dist` ).
>    `apktool b app_name`
> 6. Assine o APK.
>
>    ```html Markup
>    jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore myKeystore.keystore app_name/dist/app_name.apk myKey
>    ```
> 7. Execute zipalign no apk (para poder fazer upload para o Google Play)
>
>    ```html Markup
>    zipalign -f -v 4 app_name/dist/app_name.apk app_name/dist/zipalign_app_name.apk
>    ```
> 8. Verifique o zipalignment
>
>    ```html Markup
>    zipalign -c -v 4 app_name/dist/zipalign_app_name.apk
>    ```
> 9. Seu apk `zipalign_app_name.apk` está pronto para usar!

</Accordion>

<div id="implementation" />

<Accordion title="Implementação">

Importe a extensão da AppsFlyer para o seu projeto:

```html Markup
import AppsFlyerInterface;
```

Crie a interface da AppsFlyer:

```html Markup
private static var appsFlyer:AppsFlyerInterface; 
appsFlyer = new AppsFlyerInterface();
```

[Opcional] Se você quiser fazer deep linking ou acessar os dados de conversão da AppsFlyer no aplicativo, registre o listener de conversão:

```html Markup
appsFlyer.registerConversionListener();
```

Defina a chave de desenvolvedor e o ID do aplicativo iOS (opcional) e inicialize o SDK:

```html Markup
appsFlyer.appsFlyer.init("DevKey", "iOSAppID");
```

Inicialize o registro de sessão (registre automaticamente inicializações do aplicativo e transições do segundo plano para o primeiro plano) com a DevKey e o ID do aplicativo iOS (opcional):

```html Markup
appsFlyer.start("DevKey", "iOSAppID");
```

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep linking">

Para receber as informações relevantes da AppsFlyer do deep link usado:

1. Registre os seguintes listeners de eventos:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.APP_OPEN_ATTRIBUTION, eventHandler); // sucesso 
   appsFlyer.addEventListener(AppsFlyerEvent.ATTRIBUTION_FAILURE, eventHandler); // erro
   ```
2. Trate a resposta no respectivo manipulador de evento:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("Evento da AppsFlyer: " + event.type + "; \nDados: " + event.data);
   }
   ```

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deep linking diferido">

Para receber os dados de conversão da instalação atual:

1. Registre os seguintes listeners de evento:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_DATA_LOADED, eventHandler); // sucesso
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_FAILED, eventHandler); //erro
   ```
2. Trate a resposta no respectivo manipulador de evento:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("Evento da AppsFlyer: " + event.type + "; \nDados: " + event.data);
   }
   ```

</Accordion>

<div id="imei-and-android-id-collection-android-only" />

<Accordion title="Coleta de IMEI e ID do Android (somente Android)">

**Importante!** Aplicativos com serviços do Google Play devem evitar a coleta de IMEI, pois isso viola a política do Google Play.

Por padrão, o IMEI e o ID do Android não são coletados pelo SDK se a versão do sistema operacional for superior ao KitKat (4.4) e o dispositivo contiver o Google Play Services.

Para enviar explicitamente esses IDs à AppsFlyer, os desenvolvedores podem usar as APIs a seguir e colocá-las antes de inicializar o SDK.

Se o aplicativo NÃO tiver o Google Play Services, o SDK coleta o IMEI e o Android ID.

**Ativar/desativar a coleta de IMEI (desativada por padrão)**

```html Markup
appsFlyer.setCollectIMEI(bool);
```

**Definir dados de IMEI manualmente**

```html Markup
appsFlyer.setImeiData("imeiString");
```

**Ativar/desativar a coleta de ID do Android (desativada por padrão)**

```html Markup
appsFlyer.setCollectAndroidID(bool);
```

**Definir dados de ID do Android manualmente**

```html Markup
appsFlyer.setAndroidIdData("AndroidIDString");
```

</Accordion>

<div id="api-reference" />

## Referência da API

<div id="api-methods" />

<Accordion title="Métodos de API">

<Table>
  <thead>
    <tr>
      <th>
        YouTube video player
      </th>
      <th>
        A descrição
      </th>
      <th>
        Assinatura/exemplo
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        logEvent
      </td>
      <td>
        Registra eventos in-app.
      </td>
      <td>
        ```html Markup
        var param:String = "Deposit";
        var value:String = '{"amount":10, "FTDLevel":"-"}';
        appsFlyer.logEvent(param, value);
        ```
      </td>
    </tr>
    <tr>
      <td>
        iniciar
      </td>
      <td>
        Envie um evento de registro de sessão, independentemente do estado do aplicativo.
      </td>
      <td>
        ```html Markup
        appsFlyer.start();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setAppUserId
      </td>
      <td>
        Obtenha a ID do usuário conforme usada no aplicativo.
      </td>
      <td>
        ```html Markup
        appsFlyer.setAppUserId("user_id_as_used_in_the_app");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setUserEmails
      </td>
      <td>
        Obtenha o e-mail do usuário.
      </td>
      <td>
        ```html Markup
        appsFlyer.setUserEmails("example@example.com");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setCurrency
      </td>
      <td>
        Defina a moeda para registrar eventos de receita, por exemplo, USD.
      </td>
      <td>
        ```html Markup
        appsFlyer.setCurrency("USD");
        ```
      </td>
    </tr>
    <tr>
      <td>
        stop
      </td>
      <td>
        Use quando quiser desativar todos os registros do SDK devido à compliance legal e de privacidade. Após a execução desta API, nosso SDK não se comunicará mais com nossos servidores.
      </td>
      <td>
        ```html Markup
        appsFlyer.stop();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setDebug
      </td>
      <td>
        Ative/desative os logs de depuração do AppsFlyer.

        **Importante:** Não lance o aplicativo nas lojas de aplicativos com os logs de depuração ativados.
      </td>
      <td>
        ```html Markup
        appsFlyer.setDebug(bool);
        ```
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="plugin-information=informa%C3%A7%C3%B5es-do-plugin installation-and-implementation=instala%C3%A7%C3%A3o-e-implementa%C3%A7%C3%A3o api-reference=refer%C3%AAncia-da-api" />
