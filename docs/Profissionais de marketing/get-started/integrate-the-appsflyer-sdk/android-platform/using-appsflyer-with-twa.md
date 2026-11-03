---
title: Usando AppsFlyer com TWA
metadata:
  keywords:
    - Web View
    - Developers
    - TWA
    - PWA
    - Trusted web activities
    - Progressive web apps
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-26T05:08:01Z'
  edited_at: '2026-08-18T00:13:27Z'
  id: 360002330178
  locale: pt
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/pt/articles/360002330178
---
> **Visão geral:** Use a AppsFlyer com Trusted Web Activities (TWA, atividades web confiáveis) para medir instalações e registrar eventos in-app.

## Introdução

### O que são atividades web confiáveis ​?

As atividades web confiáveis ​​(TWA) são uma nova maneira de integrar conteúdo da web ao seu aplicativo Android. O desafio da TWA é ser capaz de registrar eventos in-app. Este desafio é abordado neste artigo. Para mais informações sobre TWA, veja <Anchor target="_blank" href="https://developers.google.com/web/updates/2019/02/using-twa">aqui</Anchor>.

TWA também pode ser usado com Progressive Web Apps.

### O que são aplicativos web progressivos?

Progressive Web Apps (PWA, aplicativos web progressivos) são aplicativos que oferecem uma experiência semelhante a um aplicativo, mas na verdade são totalmente baseados na web. Uma forma de PWA é um aplicativo Android cujas atividades são baseadas em TWA. Esta é a forma de PWA que abordaremos neste artigo. TWA permite que você incorpore seu PWA em um aplicativo Android independente, permitindo efetivamente que você apresente seu aplicativo PWA existente na Play Store.

A outra forma, puramente baseada na web, não é abordada neste artigo. Para obter mais informações sobre o PWA, veja <Anchor target="_blank" href="https://developers.google.com/web/progressive-web-apps/">aqui</Anchor>.

Esta aba é sobre o PWA incorporado em uma atividade web confiável, um navegador web em tela cheia no aplicativo. Esses aplicativos possuem a <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">classe de aplicativo global Android</Anchor>, mas cujas atividades são exclusivamente baseadas na web.

Esta forma de PWA permite medir instalações. A outra forma de PWA, puramente baseada na web, não oferece a opção de medir instalações.

## TWA

<div id="sending-inapp-events-from-twa" />

<Accordion title="Envio de eventos in-app a partir de TWA">

Os eventos in-app são enviados usando o SDK da AppsFlyer a partir de atividades nativas do aplicativo. Como TWA é baseada na web e não é uma atividade nativa, você não pode enviar eventos in-app usando o SDK da AppsFlyer. Você pode usar <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">eventos in-app de servidor para servidorcomo</Anchor> alternativa. Siga as instruções abaixo para enviar eventos de servidor para servidor com TWA.

### Pré-requisitos

Antes de começar a enviar eventos TWA para a AppsFlyer, faça o seguinte:

1. Adicione o seguinte repositório ao arquivo gradle no nível do projeto:  

   ```java
   maven { url "https://jitpack.io"}
   ```
2. Adicione as seguintes bibliotecas:
   * Para bibliotecas android.support:
     * Adicione o seguinte em seu build.gradle:  
       implementação 'com.github. GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     * Importe as seguintes bibliotecas:

       ```java
       import android.support.customtabs. CustomTabsClient;
       import android.support.customtabs. CustomTabsIntent;
       import android.support.customtabs. CustomTabsServiceConnection;
       import android.support.customtabs. CustomTabsSession;
       import android.support.customtabs.trusted. TrustedWebActivityIntentBuilder;
       import static android.support.customtabs. TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   * Para bibliotecas androidX:
     * Adicione o seguinte em seu build.gradle:  

       ```java
       implementation 'com.github. GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```
     * Importe as seguintes bibliotecas:

       ```java
       import androidx.browser.customtabs. CustomTabsClient;
       import androidx.browser.customtabs. CustomTabsIntent;
       import androidx.browser.customtabs. CustomTabsServiceConnection;
       import androidx.browser.customtabs. CustomTabsSession;
       import androidx.browser.trusted. TrustedWebActivityIntentBuilder;
       ```

### Como buscar o ID da AppsFlyer

Para enviar eventos de servidor para servidor, você precisa do ID da AppsFlyer. Você pode obter o ID da AppsFlyer no Android SDK da AppsFlyer.

Primeiro, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">integrar o Android SDK da AppsFlyer</Anchor>. Você pode então obter o ID da AppsFlyer usando a seguinte API SDK:

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

### Enviando o ID da AppsFlyer para TWA

Você pode enviar o ID da AppsFlyer de duas maneiras:

<div id="append-appsflyer-id-and-customer-user-id-to-url" />

<Accordion title="Anexar ID da AppsFlyer e ID de usuário do cliente ao URL">

Ao criar uma intenção de atividade web confiável, você pode passar parâmetros para seu URL:

```java
private void launchTwa(String cuid, String af_id) {\n\n    CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {\n\n        @Override\n        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {\n            Log.d(LOG_TAG, "onCustomTabsServiceConnected");\n\n            // Configuração da CustomTabsSession usada para criar uma intent\n            mClient = client;\n            CustomTabsSession session = mClient.newSession(null);\n\n            // Criação da intent para iniciar a TWA usando a URL com parâmetros de consulta que podem ser lidos pelo aplicativo web\n            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri + "?cuid=" + cuid + "&appsflyer_id=" + af_id));\n            Intent twaIntent = twaIntentBuilder.build(session);\n\n            startActivity(twaIntent);\n        }\n\n        @Override\n        public void onServiceDisconnected(ComponentName name) {\n            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");\n        }\n    };\n\n    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);\n}
```

#### Como buscar o ID da AppsFlyer

Depois que a atividade web for iniciada, você poderá recuperar o ID da AppsFlyer usando um simples snippet de JavaScript:

```javascript
let url = new URL(document.location.href);
    let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

Depois de obter o ID da AppsFlyer, armazene-o no armazenamento local para uso posterior.

</Accordion>

<div id="sending-appsflyer-id-through-custom-headers" />

<Accordion title="Envio de ID da AppsFlyer por meio de cabeçalhos personalizados">

Você pode passar cabeçalhos personalizados para atividades web confiáveis. O servidor obtém esses cabeçalhos, os configura em cookies e os envia para o navegador. Você pode então recuperar o ID da AppsFlyer usando javascript:

```java
private void launchTwa(String cuid, String af_id) { \n        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {\n\n        @Override\n        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {\n            Log.d(LOG_TAG, "onCustomTabsServiceConnected");\n\n            // Configuração da CustomTabsSession usada para criar uma intent\n            mClient = client;\n            CustomTabsSession session = mClient.newSession(null);\n\n            // Criação da intent para iniciar a TWA usando a URL com parâmetros de consulta que podem ser lidos pelo aplicativo web\n            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);\n            Intent twaIntent = twaIntentBuilder.build(session);\n\n            // Passagem de cabeçalhos personalizados adicionais para a intent para que possam ser lidos pelo aplicativo web\n            Bundle customHeaders = new Bundle();\n            customHeaders.putString("twa_params", "cuid=" + cuid + "&=appsflyer_id" + af_id");\n            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);\n            startActivity(twaIntent);\n        }\n\n        @Override\n        public void onServiceDisconnected(ComponentName name) {\n            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");\n        }\n    };\n\n    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);\n}
```

#### Como buscar o ID da AppsFlyer

JavaScript não fornece uma API para permitir que os desenvolvedores acessem os cabeçalhos. Portanto, o servidor deve enviar os dados de conversão de volta para a atividade web como um cookie. O servidor obtém os cabeçalhos personalizados contendo o ID da AppsFlyer, analisa os dados e os envia para a página web como um cookie.

Quando a página carrega, um snippet JavaScript deve ser definido para buscar o cookie de ID da AppsFlyer.

```javascript
// obter o cookie de dados de conversão 
// função obtida de https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// obter o cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id);
```

</Accordion>

### Enviando o evento in-app

Para enviar eventos in-app, você precisa enviar os dados do evento para o seu servidor e fazer com que ele envie o evento para a AppsFlyer. Existem alguns outros pré-requisitos para enviar eventos in-app:

* <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Chave do desenvolvedor do SDK</Anchor> - **Importante! A chave do desenvolvedor do SDK é um valor confidencial e não deve estar presente no TWA. Se você for usar o TWA e enviar eventos in-app de servidor para servidor, sempre armazene a chave de desenvolvedor do SDK com segurança no lado do servidor.**
* ID do aplicativo - o ID do aplicativo conforme aparece no Android Manifest.xml.

Depois de ter esses três parâmetros (ID da AppsFlyer, chave do desenvolvedor do SDK, ID do aplicativo), você poderá enviar o evento in-app. Sempre que um evento ocorre na atividade da web, você deve enviar uma solicitação ao seu servidor da web para lidar com esse evento. O webserver obtém os dados relacionados ao evento, compõe o evento e envia para a AppsFlyer.

Veja <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile#api-de-eventos-de-servidor-para-servidor-para-mobile">aqui</Anchor> exemplos de como enviar eventos in-app de servidor para servidor.

</Accordion>

<div id="customizing-web-content-with-conversion-data" />

<Accordion title="Personalizando conteúdo da web com dados de conversão">

O SDK da AppsFlyer fornece dados de conversão por meio de duas APIs:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Obter dados de conversão</Anchor> - chamado quando o aplicativo é iniciado pela primeira vez após uma instalação e para lançamentos subsequentes do aplicativo.
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/api-reference#onappopenattribution">Atribuição na abertura do aplicativo</Anchor> - chamada quando o aplicativo está vinculado diretamente ao uso do OneLink.

Você pode usar dados de conversão para personalizar o conteúdo da web.

### Enviando dados de conversão para TWA

Depois de obter os dados de conversão de qualquer um dos métodos listados acima, você pode enviá-los para o seu servidor web. Para fazer isso, use cabeçalhos personalizados:

```java
private void launchTwa(Map<String, String> conversionData, String cuid, String af_id) { \n        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {\n\n        @Override\n        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {\n            Log.d(LOG_TAG, "onCustomTabsServiceConnected");\n\n            // Configuração da CustomTabsSession usada para criar uma intent\n            mClient = client;\n            CustomTabsSession session = mClient.newSession(null);\n\n            // Criação da intent para iniciar a TWA usando a URL com parâmetros de consulta que podem ser lidos pelo aplicativo web\n            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);\n            Intent twaIntent = twaIntentBuilder.build(session);\n\n            // Passagem de cabeçalhos personalizados adicionais para a intent para que possam ser lidos pelo aplicativo web\n            Bundle customHeaders = new Bundle();\n            customHeaders.putString("twa_params", "cuid=" + cuid + "&=" + af_id");\n            customHeaders.putString("conversion_data", conversionData);\n            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);\n            startActivity(twaIntent);\n        }\n\n        @Override\n        public void onServiceDisconnected(ComponentName name) {\n            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");\n        }\n    };\n\n    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);\n}
```

### Buscando os dados de conversão do lado do cliente

JavaScript não fornece uma API para permitir que os desenvolvedores acessem os cabeçalhos. Portanto, o servidor deve enviar os dados de conversão de volta para a atividade web como um cookie. O servidor obtém os cabeçalhos personalizados contendo os dados de conversão, analisa os dados e os envia para a página da web como um cookie.

Quando a página carrega, um snippet JavaScript deve ser definido para buscar o cookie de dados de conversão e personalizar o conteúdo de forma correspondente. Por exemplo, se um usuário instalar o aplicativo a partir de uma campanha de ofertas de voos, você poderá preencher a atividade na web com conteúdo relevante para as ofertas promovidas pela campanha.

```javascript
// obter o cookie de dados de conversão 
// função obtida de https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;\n}\n\n// obter o cookie\nvar conversionData = JSON.parse(getCookie('conversion_data'));\nconsole.log(conversionData);\n/*\ndados de conversão de exemplo:\n{ \n        campaign: "CAMPAIGN_NAME", // "None" se não for especificado no link\n        media_source: "MEDIA_SOURCE", //"None" se não for especificado no link     \n        cost_cents_USD : "0",\n        is_first_launch: true,\n        install_time: "2018-12-30 23:59:39.330",\n        orig_cost: "0.0",\n        af_click_lookback: "7d",\n        click_time: "2018-12-30 23:59:09",\n        cost_cents_USD: "0",\n        af_status: "não orgânico"\n}\n*/
```

Para saber mais sobre casos de uso de dados de conversão, clique <Anchor target="_blank" href="/marketers/pt/docs/conversion-data-payloads-and-scenarios">aqui</Anchor>.

</Accordion>

## PWA

<div id="measuring-installs-for-pwa" />

<Accordion title="Medindo instalações para PWA">

Como acontece com qualquer outro aplicativo Android, você pode integrar o SDK da AppsFlyer ao aplicativo para medir instalações e obter dados de conversão.

Para medir instalações, tudo o que você precisa fazer é integrar o SDK seguindo as instruções <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">aqui</Anchor>.

</Accordion>

<div id="customizing-content-using-conversion-data" />

<Accordion title="Personalização de conteúdo usando dados de conversão">

Você pode personalizar o conteúdo da web de acordo com a campanha que solicita ao usuário a instalação do seu aplicativo. Por exemplo, se um usuário instalar um aplicativo de uma campanha que oferece 20% de desconto em produtos de sua loja virtual. Você pode obter os dados de conversão e aplicar o desconto assim que o aplicativo abrir a atividade na web.

Para saber mais sobre como usar dados de conversão para personalizar conteúdo da web, siga as instruções [aqui](/docs/using-appsflyer-with-twa#enviando-dados-de-conversão-para-twa).

</Accordion>

<div id="recording-events-in-pwa" />

<Accordion title="Gravando eventos no PWA">

PWA faz uso de TWA, que são essencialmente atividades na web. Como TWA é baseada na web e não é uma atividade nativa, você não pode enviar eventos in-app usando o SDK da AppsFlyer. Como alternativa, você pode usar eventos in-app de servidor para servidor.

Siga as instruções [aqui](/docs/using-appsflyer-with-twa#sending-inapp-events-from-twa) para saber como enviar eventos in-app para PWA.

</Accordion>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o what-are-trusted-web-activities=o-que-s%C3%A3o-atividades-web-confi%C3%A1veis- what-are-progressive-web-apps=o-que-s%C3%A3o-aplicativos-web-progressivos prerequisites=pr%C3%A9-requisitos getting-the-appsflyer-id=como-buscar-o-id-da-appsflyer sending-the-appsflyer-id-to-twa=enviando-o-id-da-appsflyer-para-twa retrieving-the-appsflyer-id=como-buscar-o-id-da-appsflyer-1 retrieving-the-appsflyer-id::a3f31d46=como-buscar-o-id-da-appsflyer-2 sending-the-inapp-event=enviando-o-evento-in-app sending-conversion-data-to-twa=enviando-dados-de-convers%C3%A3o-para-twa fetching-the-conversion-data-from-the-clientside=buscando-os-dados-de-convers%C3%A3o-do-lado-do-cliente" />
