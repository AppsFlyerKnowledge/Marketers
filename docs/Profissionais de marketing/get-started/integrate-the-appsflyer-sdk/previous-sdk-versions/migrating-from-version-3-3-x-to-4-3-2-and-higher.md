---
title: Migração da versão 3.3. X para a 4.3. X e superiores
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2016-02-03T10:37:42Z'
  edited_at: '2026-08-19T00:14:48Z'
  id: 207606796
  locale: pt
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/pt/articles/207606796
---
> **Em resumo:** considerações sobre a migração de versões do SDK Android da AppsFlyer.

Foram feitas alterações importantes na integração do SDK Android.

As principais alterações são:

* O SDK agora é um singleton, o que significa que todas as chamadas às APIs devem ser feitas da seguinte forma:

```java
AppsFlyerLib.getInstance().setCustomerUserId("myId");
```

* **SetAppsFlyerKey()** – este método foi removido; como resultado, esperamos receber a chave de desenvolvedor usando o novo método init: AppsFlyerLib.getInstance().startTracking(this,"YOUR\_APPSFLYER\_DEV\_KEY")
* **sendTracking()**, **onActivityPause()**, **onActivityResume()** foram removidos. O SDK detecta os lançamentos automaticamente
* **Deep Link** - para atividades com suporte a deep linking, o desenvolvedor deve chamar:

```java
AppsFlyerLib.getInstance().sendDeepLinkData(this) no onCreate()
```

da atividade exibida.

Isso só é necessário se o aplicativo não estiver em execução em segundo plano.

* **Logging** - o valor padrão da flag de logging foi alterado para false. Além disso, se a flag estiver desativada, nenhum log será exibido (correção de bug). Para ativar a flag de logging, o desenvolvedor deve chamar:

AppsFlyerLib.getInstance().setDebugLog(true);

Para ver o Guia de integração do SDK da AppsFlyer para Android, clique <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">aqui</Anchor>.

**Migração para a versão 4.4 e posteriores**

O SDK Android da AppsFlyer v4.4 **não oferece mais suporte ao seguinte receptor** no manifesto:

```html Markup
<receiver android:name="com.appsflyer. AppsFlyerLib">
  <intent-filter>
    <action android:name="android.intent.action.PACKAGE_REMOVED"/>
    <data android:scheme="package"/>
  </intent-filter> 
</receiver>
```

Se você estiver usando a versão 4.4.0+, **remova este receptor do seu arquivo de manifesto**.

O único receptor **obrigatório** para o SDK é o seguinte:

```html Markup
<receiver
  android:name="com.appsflyer. MultipleInstallBroadcastReceiver"
  android:exported="true">
    <intent-filter>
      <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>
```