---
title: 中国国内安卓市场归因指南
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
  edited_at: '2026-10-14T10:09:58Z'
  id: 360002049858
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002049858
---
> **概要：** 还可以通过归因数据，

## 中国国内安卓市场归因指南

针对国内安卓市场的特殊性，广告主通常面临如下挑战：

* Google Play服务（GPS）在大多数Android设备上无效，也就意味着没有GAID。
* 服务器响应时效可能偏慢

AppsFlyer为您提供了以下解决方案：

* 适配主流厂商OAID
* 鉴于国内安卓生态不会使用GAID，我们将根据 OAID 或设备IMEI进行归因，以替代GAID
* 除了提供归因的媒体渠道字段，还会提供商店/渠道包字段，保证每一条激活数据包含用户完整转化路径：从渠道的点击/曝光数据，到最终APK下载来源，可以轻松识别商店劫持
* 配置为中国市场专门制定的归因链接（即点击监测链接）。

## 准备应用

请参照以下说明，集成SDK。请务必注意不同的Android API版本对应不同的设备ID收集场景，请根据情况上报设备ID。

<div id="integrate-the-sdk-in-the-app" />

<Accordion title="集成SDK上报设备ID">

**请务必确认上报OAID给AppsFlyer (针对中低安卓版本仍需收集IMEI的场景，请务必确保向终端用户授权）**

通常，国内的Android设备上没有Google Play Service。也就是说GAID在国内安卓归因的部分基本上无效。

作为替代，国内会使用OAID或IMEI作为归因使用的设备唯一标志符。

**OAID：**

* 可重置广告ID，类似GAID或IDFA。
* 需要AppsFlyer Android SDK 5.1.0或更高版本。
* 从AppsFlyer SDK V5.4.0开始，AF SDK默认将尝试自动收集OAID（前提仍需部署厂商相关设置，详见OAID集成文档）
* AppsFlyer已经与多家手机厂商完成了OAID对接，且完成归因协同测试。<Anchor target="_blank" href="/marketers/zh/docs/android-oaid-implementation-in-the-sdk">包括：华为，联想，OPPO，Vivo，三星和小米</Anchor>等

**IMEI**:

* AppsFlyerSDK收集IMEI的前提是，如发现设备内有Google Play Service，则默认不收集IMEI。除非另行设置。因为在海外市场，如果设备上存在Google Play Services，是不允许收集IMEI的。而在中国市场，GPS占比较低，IMEI仍在安卓系统中低版本被用做归因。
* 您集成AppsFlyer SDK时，请注意，无论您是自行收集IMEI上报给AF，还是直接使用AppsFlyer SDK收集IMEI，都会受到终端用户授权结果的影响（如果您的客户端有设置授权提示），因此终端用户同意授权获取IMEI，AppsFlyer才会有可能获取IMEI数据。
* 2019年末发布的 Android 10（API level 29） 进行了隐私权限变更，禁止获取IMEI。
* 同时，OAID或IMEI的上报方法都是两种，您可以选择自己收集上报给AF，或使用AF SDK 直接收集。在没有设备ID的情况下，AppsFlyer会通过 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">概率模型进行归因。</Anchor>

**温馨提示以下信息** ：

* 需要AppsFlyer Android SDK V5.1.0或更高版本

参考以下场景上报：

<div id="oaid-starting-from-android-api-level-29" />

<Accordion title="Android API level 29 禁止收集IMEI改用OAID">

由于Android API level 29 开始禁止收集IMEI，国内会采用OAID作为主要的归因设备ID。具体上报OAID有两种方法：

* setCollectOaid
* setOaidData

<Anchor target="_blank" href="/marketers/zh/docs/android-oaid-implementation-in-the-sdk#msa-sdk">具体请参考上报OAID指南</Anchor>

</Accordion>

<div id="imei-android-api-level-2328" />

<Accordion title="Android API level 23-28 可收集IMEI但请务必向终端用户获得授权">

上报IMEI有两种方法：

* setImeiData
* setCollectIMEI(true)

使用以下代码示例集成SDK。即通过客户端直接获取归因数据，SDK版本V 5.0以上，该方法的名称为onConversionDataSuccess。当然，我们推荐您升级到SDK最新版本。

**请注意：注意： Android API级别23或更高版本需要终端用户授权（可能会涉及客户端弹窗提示）才能获取IMEI。这有可能会导致在激活StartTracking API之后才开始收集IMEI。从Android 10（API level 29）开始，安卓禁止收集IMEI。**

```java
Public class AFApplication extends Application {
   private static final String AF_DEV_KEY = "";
   private static AFApplication instance;
   @Override
   public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true); //Developer collect the imei and android id, then send them to AppsFlyer SDK.
	  AppsFlyerLib.getInstance().setImeiData("customer imei"); 
	  AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Or use the two APIs below let AppsFlyer SDK collect IMEI & android id
      //no matter if the Google Play Service exists or not.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);
      //Configure the min time between two sessions, the recommendation is 2 seconds。
      AppsFlyerLib.getInstance().setMinTimeBetweenSessions(2);
      final AppsFlyerConversionListener conversionDataListener = new 
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

在应用程序首次启动时，将在MainActivity的onResume()调用后向用户发送READ\_PHONE\_STATE的权限请求。

app模块中的build.gradle

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

```java
import androidx.appcompat.app.AppCompatActivity;
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
           //Permission was already granted
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, true);
           permissionsFlagsEditor.apply();
       }
   }
   @Override
   public void onRequestPermissionsResult(int requestCode,
                                          String[] permissions, int[] grantResults) {
       if (requestCode == MY_PERMISSIONS_REQUEST_READ_PHONE_STATE) {
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           boolean granted;
           // If request is cancelled, the result arrays are empty.
           if (grantResults.length > 0
                   && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
               // permission was granted!
               granted = true;
               AppsFlyerLib.getInstance().setCollectIMEI(true);
           } else {
               // permission denied!
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

```java
public class MainActivity extends AppCompactActivity {
    @Override
    protected void onResume() {
        super.onResume();
        final RxPermissions rxPermissions = new RxPermissions(this);
         if(RxPreference.Instance().getBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, false){
          return;
         }
         if(rxPermissions.isGranted(Manifest.permission.READ_PHONE_STATE)) {
            return;
         }
          RxPreference.Instance().putBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, true);
        rxPermissions.request(Manifest.permission.READ_PHONE_STATE)
                .subscribe(granted -> {
                    if (granted) {  
AppsFlyerLib.getInstance().setImeiData("customer imei");  
AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");  
//or  
AppsFlyerLib.getInstance().setCollectIMEI(true);  
AppsFlyerLib.getInstance().setCollectAndroidID(true);  
//NOTE: Here the report session API is reportTrackSession() not the startTracking()
                        AppsFlyerLib.getInstance().reportTrackSession(AFApplication.getAppInstance());
                    } else {
                    }
                });
    }
}
```

Android API level 22 或以下用户授权后可收集IMEI

</Accordion>

上报IMEI有两种方法：

* setImeiData
* setCollectIMEI(true)

使用以下代码示例集成SDK。**请注意：** 此方法名称适用于SDK V5以上。我们建议您升级到SDK 5.0.0。要了解更多信息，请点击<Anchor target="_blank" href="/marketers/zh/docs/links-to-appsflyer-sdk-release-notes">这里</Anchor> 。

```java
 public class AFApplication extends Application {
    private static final String AF_DEV_KEY = "";
    private static AFApplication instance;
    @Override
    public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true);  
 //Developer collect the imei and android id, then send them to AppsFlyer SDK.  
 AppsFlyerLib.getInstance().setImeiData("customer imei");  
 AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Or use the two APIs below to let AppsFlyer SDK collect IMEI & android id no matter the 
      //Google Play Service is exist or not.
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


</Accordion>

<div id="preparing-the-apk" />

<Accordion title="集成打包APK">

查看归因数据的三种方案：

* 假设应用程序已在AppsFlyer中添加，可使用此方法。要使用该方法继续至[准备APK /manifest](/docs/measure-attribution-in-the-chinese-domestic-market#准备apk-manifest)下面的部分。

### 在AppsFlyer中添加应用程序

（1）使用Pending App，暨**待批准或尚未发布** 选项创建应用程序，在使用此方案之前可咨询您的客户经理。 （2）使用常规安卓商店外APK追踪(out of store)方式添加应用，请注意用这种方式添加，除了在面板操作，还需要客户端配置相对应的channel名称。具体步骤如下。

2. 单击 **添加App** 。   
   添加应用窗口打开。
3. 选择 **安卓第三方APK 。**
4. 填写以下字段：   
   * **Android包名** ：示例com.appsflyer
   * 流量入口名称 Channel名称 ： 必须与manifest中配置的channel名称完全一致，大小写敏感。参考下一部分所述。最佳做法是可将此字段设置为 **cn** ，配置channel后，物理包名不改变，但af后台显示的包名会添加channel后缀，示例com.appsflyer-cn.
   * **App URL**

**请注意**：注意 ：App URL指APK下载地址或第三方商店产品页地址。添加app后如需修改跳转地址，可通过在链接中添加“&af\_r”跳转参数修改。

### 准备APK /manifest

1. 将以下内容添加到manifest中以识别来自中国的流量：

   ```java
   < meta-data android:name="CHANNEL" android:value="cn_market">
   ```

   **请注意：注意： 参数区分大小写。我们建议您将渠道名称设置为** cn **。若使用Pending App的方法，不需要操作此步骤。**
2. 选择以下方法之一来识别商店名称（AF\_STORE）：
   * AF\_STORE值对于每个商店都必须是唯一的。

     ```xml
     <meta-data android:name="AF_STORE" android:value="example_store"/>
     ```

     **--或者--**
   * API方法调用setOutOfStore API以设置AF\_STORE值。为每个商店设置唯一AF\_STORE值。(注意：如果您使用的国内第三方应用商店较多，建议使用此方法)   

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("example_store")
     ```

AF\_STORE API上报字段在原始数据和群组报告中显示字段名称为 install app store .目前包含该字段的报告和API包括：

* 群组分析
* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据报告</Anchor>

</Accordion>

## 其他注意事项

<div id="workaround-for-stores-without-attribution-link-support" />

<Accordion title="不支持归因链接的国内第三方应用商店解决方案">

而国内部分第三方应用商店（或部分广告位），不支持使用归因链接进行归因记录。针对这种问题，请参考以下两种解决方案：

* install\_app\_store字段:(推荐）在没有归因链接的情况下进行安装时，AppsFlyer会将安装归因于自然安装。通过使用 install\_app\_store 字段，您可以识别实际的安装源，即带来安装的国内第三方应用商店。请注意：注意：install\_app\_store字段值是通过上节中描述的AF\_STORE参数设置的。
* <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-factory-preinstall-using-manifest-android">使用“假”预装的方式</Anchor> 。使用Manifest中设置的预装渠道号。这种方案的缺点是，一旦含有预装的APK包泄露到市场，归因信息有可能会不准确（只要有新用户激活此APK，则用户会被归因为此渠道下的非自然安装）。使用此方法时，请确保您拥有适当的商业条款来保护您的APK。

</Accordion>

<div id="china-domestic-attribution-links" />

<Accordion title="国内专用归因链接">

在准备归因链接时，请您考虑以下因素：

**中国市场专门制定的归因链接**

对于包含国内（中国）流量的媒体来源，请使用此处详述的域链接。这些链接是为中国市场专门制定的，可以提供卓越的用户体验。

即带有中国国旗标识的归因链接： https://app.aflink.com (aflink.com)

对于OneLink归因链接，请使用带有中国国旗标识的归因链接：[https://go.onelnk.com](https://go.onelnk.com)（onelnk.com）注意：在使用onelnk.com域名之前，请联系您的AppsFlyer客户经理。

请注意，在微信中，只有 **onelnk.com** 被列入白名单，可以完成跳转，而 **onelink.me** 被阻止

**使用af\_r**

使用 af\_r 确保用户被跳转到APK下载的URL或者国内第三方应用商店，而不是到Google Play商店。

请注意：注意：通常，中国国内对接的媒体渠道在默认的归因链接模板中已设置 & redirect = false 的参数。即跳转由广告平台执行，而不是由AppsFlyer执行。

</Accordion>

<div id="detecting-store-hijacking" />

<Accordion title="识别商店劫持">

如果存在安装劫持的情况，设备会弹出警告窗口，建议用户直接从设备（手机）制造商的应用程序商店，安装/更新应用程序。一旦用户选择同意，用户会跳转至制造商的第三方应用商店并进行APK下载。这意味着设备制造商已经劫持了此次安装。

以下示例分别对正常转化路径和被劫持的转化路径进行说明描述：

**正常转化路径**

用户点击媒体渠道A的广告，然后立即下载应用或跳转到媒体渠道指定的国内第三方应用商店A下载APP。在AppsFlyer中，会记录到以下归因数据：

* **媒体渠道** ：媒体渠道A
* **Install app store** ：媒体渠道指定的国内第三方应用商店A

**被劫持的转化路径**

用户点击媒体渠道A的广告。在启动下载时，设备上会弹出一个警告窗口，提示用户从设备制造商的应用商店下载应用程序。如果用户同意，用户会跳转至制造商的第三方应用商店B下载APK。在AppsFlyer中，会记录到以下归因数据：

* **媒体渠道** ：媒体渠道A
* **Install app store** ：设备制造商的应用商店B

**识别AppsFlyer中的劫持事件**

要识别被劫持的安装，您可以对比媒体渠道和install-app-store（安装应用商店）字段。如果预期的安装应用商店与实际的安装应用商店不匹配，则表示安装劫持。

</Accordion>

<div data-zendesk-anchors="attribution-android-apps-in-the-chinese-domestic-market=%E4%B8%AD%E5%9B%BD%E5%9B%BD%E5%86%85%E5%AE%89%E5%8D%93%E5%B8%82%E5%9C%BA%E5%BD%92%E5%9B%A0%E6%8C%87%E5%8D%97 preparing-the-app=%E5%87%86%E5%A4%87%E5%BA%94%E7%94%A8 adding-the-app-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E6%B7%BB%E5%8A%A0%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F preparing-the-apkmanifest=%E5%87%86%E5%A4%87apk-manifest additional-attribution-considerations=%E5%85%B6%E4%BB%96%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9" />
