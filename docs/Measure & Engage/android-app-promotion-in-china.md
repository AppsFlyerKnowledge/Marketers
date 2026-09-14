---
title: "Android app promotion in China"
excerpt: "Learn the best practices and attribution solutions for promoting your Android app in the Chinese market."
---
At a glance: Best practices to promote your Android app in the Chinese market.

## Android apps in China

Treat the sections that follow as a checklist of items that you should consider if you market your app in China.

### Selecting an identifier

To achieve accurate attribution a unique identifier (ID) that represents the user is required. On devices where Google Play services (GPS) are active this historically has been the Google advertising ID (GAID).

At present GPS is not available on devices marketed in China. App owners are required to use alternative ID based on device hardware being IMEI and Android ID.

Starting with [Android 10 (API level 29)](https://developer.android.com/training/articles/user-data-ids), released in late 2019, access to the IMEI and Android ID is restricted. The effect of this is that the IMEI/Android ID won't be accessible on newer devices.

To overcome this, an alternative to GAID, is OAID. OAID (available starting late 2019) is being promoted by Chinese device manufacturers, for example, [Huawei](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3030304).

See [AppsFlyer SDK Integration - Android](https://support.appsflyer.com/hc/articles/360002049858-Guide-for-attributing-out-of-market-Android-apps-in-China-).

### Attribution solutions for the Chinese market

Since there are multiple Android App stores that serve the Chinese market, AppsFlyer provides the solutions described here to attribute Android installs.

Chinese Android device users download apps from different Chinese Android App Stores instead of Google Play and most of these App Stores provide ad units for App Advertisers. Among these App Stores the main ones are Tencent MyApp, 360 App Store, Baidu App Store, Xiaomi App Store, OPPO App Store and Huawei App Store.

For example, if you want to promote your Android App via Tencent Social Ads, Tencent Tui Ads and Wechat Ads, upload the Android app to MyApp (Tencent Android App Store), which brings you organic installs at the same time. Baidu series ad networks, 360 Ads, Xiaomi Ads, OPPO Ads all operate in a similar way.

Meanwhile, many Android installs are generated from APK download links in mobile web pages or in-app ad space.

AppsFlyer provides three main solutions to attribute Android App installs in China market, use the method most relevant to your needs.

### Local android app store that supports ad attribution

**Solution:** Android out-of-store app with attribution Link

**Description:** The well-known Chinese Internet companies or mobile device manufacturers have created their own Android App Stores and Ad Platforms/Ad Networks, taking advantage of their huge traffic resources in China's domestic market. However, these big companies strictly control traffic to see if the user who clicked on their ad downloads the App from the App Store of a different company. In such situations, you have to generate a unique out-of-Store App for each Android App Store. Meanwhile, you can use the AppsFlyer attribution link to record the performance of the ad campaigns built on those companies’ own Ad platforms/Ad Networks.

By using this method, you can attribute both organic install and non-organic installs. At the same time, you can optimize ad campaigns in the term of ad units, ad set and creatives, etc.

**Example:** If you want to promote your Android App via Tencent Social Ads, Tencent Tui Ads, and Wechat Ads, you must upload the Android App to Tencent Android App Store and MyApp, etc, which brings you organic installs at the same time. Baidu series ad networks, 360 Ads, Xiaomi Ads, OPPO Ads all work in the same way.

**Preparation:** How to attribute out-of-store apps, click [here](https://support.appsflyer.com/hc/articles/207447023).

### Ad network

**Solution:** APK Download Link / APK + Attribution Link

**Description:** To promote Android Apps in Ad Networks that have no mandatory requirement on where to download the App, you can simply provide an APK Download Link or an APK and the AppsFlyer attribution link to the media source.

It is easy and fast to launch ad campaigns. It is also convenient to check the performance of different media sources at the same app overview page.

**Example:** Bytedance Ads(Toutiao), Sina Weibo, iQiyi

**Preparation:** Set up one Android out-of-store app, and generate different attribution links for different ad networks. To learn how to attribute out-of-store apps, click [here](https://support.appsflyer.com/hc/articles/207447023).

### Android app store that does not support ad attribution

**Solution:** Android out-of-store app

**Description:** For Android App Stores that do not support ad attribution, you can still use Out-Of-Store Apps to attribute all the installs coming from this App Store, only all the installs are attributed as organic installs.

**Example:** Lenovo app store, Huawei app store.

**Preparation:** how to attribute out-of-store apps, click [here](https://support.appsflyer.com/hc/articles/207447023).

If you are promoting your apps with more than one of the solutions mentioned above and you want to check the data of all your China campaigns int the same dashboard view, you can use [Custom Dashboard](https://support.appsflyer.com/hc/articles/212750286-AppsFlyer-s-Custom-Dashboard-Premium-).

## Integrated media sources

[Configuration guides](https://support.appsflyer.com/hc/sections/6552066355601-China-domestic-market-ad-network-configuration)

Integrated media sources in China:

| Media source name | Chinese name | PID | Logo |
| --- | --- | --- | --- |
| [Tencent Ads](https://support.appsflyer.com/hc/articles/360000264689) | 腾讯广告 | tencent\_int | ![ac1.png](https://files.readme.io/dd4dde79f0de93c5ee072166222231658df8dd6f793192b40fafc3d7a09be648-ac1.png) |
| [Bytedance Ads](https://support.appsflyer.com/hc/articles/115003019403) | 巨量引擎（今日头条） | bytedance\_int | ![ac2.png](https://files.readme.io/e433c7b245e9e59eaabad91e5267ff66048f8ea9f7e2bf2f1d8d96bafadc91b1-ac2.png) |
| [WeChat Ads](https://support.appsflyer.com/hc/articles/115003044106) | 微信公众平台 | wechat\_int | ![ac4.png](https://files.readme.io/df27fc2d7fe5e4ecb803d4ab0707a516b7e7eef984a16d0b6e6f5da2b9e1abc9-ac4.png) |
| [Weibo Ads](https://support.appsflyer.com/hc/articles/115004134086) | 微博超级粉丝通 | sinaweibo\_int | ![ac5.png](https://files.readme.io/d363aab7711b2d520ba4f5f0b4b1d65dd348fe93c4a6284de884b587383fec04-ac5.png) |
| Sina Fuyi Ads | 新浪扶翼 | sinafuyi\_int | ![sinafuyi.logo.png](https://files.readme.io/a3fff3cd69b7cd2443cf9b118859afbbcb59c0403ed9a69e622b985f2971d979-sinafuyi.logo.png) |
| [Baidu App Ads](https://support.appsflyer.com/hc/articles/115003044146) | 百度百通 | baitong\_int | ![ac6.png](https://files.readme.io/023e26b458c3c0618e310acd1f5e4d6995e96ba7e142dd0ebca2224f62fc823c-ac6.png) |
| [Baidu mDSP](https://support.appsflyer.com/hc/articles/115004330446) | 百度百易 | baidumdsp\_int | ![ac7.png](https://files.readme.io/bb650b5c3cb0186dbbaeb6230462b02d515f72fab74a39a4f4098cc78b42bd78-ac7.png) |
| Baidu Search Ads | 百度搜索广告 | baidusearch\_int | ! |
| Baidu Native Ads | 百度信息流广告（百度原生） | baidufeedads\_int | ! |
| Baidu Native Ads 2.0 | 百度信息流广告（百度原生）2.0 | baiduxinxiliu\_int | ! |
| [Xiaomi Ads & App Store](https://support.appsflyer.com/hc/articles/115001605286-How-to-Configure-a-Campaign-with-Xiaomi-Ads-Network) | 小米营销平台 & 应用商店 | xiaomichina\_int | ![ac8.png](https://files.readme.io/b7d9541e0f9602181f879685ba1623f342e666970791488381161149e95e5086-ac8.png) |
| Huawei App Gallery in China | 华为应用商店 | huaweiappgallerychina\_int | ![huawei_app_store_logo.png](https://files.readme.io/29f84e8d0e90fc5bb85fc86810a45810fd0bc5fea58869c124b8f66354b67c78-10801903185809.png) |
| OPPO App Store in China | OPPO软件商店 | oppostorechina\_int | ![oppo_store_logo.png](https://files.readme.io/30bdc4b4613f423f028eea5adfc6eee714805db65b857c49d6221639f19b3523-10801961659153.png) |
| vivo Ads & App Store | vivo营销平台&应用商店 | vivoads\_int | ![vivo_store_logo.png](https://files.readme.io/5b3b87a0d4a6c424421d9d1b156cf0b1d81da7b534a53e760227de2726db8445-10802004853009.png) |
| 360 Ads | 360点睛实效平台 | 360\_int | ![ac9.png](https://files.readme.io/7ab3fd1b8db39fdc2ca2061a963a2c6ac3ed83be0f2fcc0db7bdd214ca17f2ce-ac9.png) |
| Ali UC Ads | 阿里汇川 （UC头条） | uctoutiao\_int | ![ac10.png](https://files.readme.io/6ba93e195ace24c0ea6dd4d0e93ccf2602f22be56e9a36409f13870aec77de2f-ac10.png) |
| Netease Ads | 网易易效 | netease\_int | ![ac11.png](https://files.readme.io/1c0290236fba996561162188e099ec694f119af7733313be35711a6d20267009-ac11.png) |
| iQIYI Ads | 爱奇艺奇麟神算 | iqiyi\_int | ![ac12.png](https://files.readme.io/aef33a6a9bfc7b42a96aec726e3098ff17c51ae0a378fcf96626d21c653b4dd0-ac12.png) |
| MOMO Ads | 陌陌广告 | momo\_int | ![ac13.png](https://files.readme.io/86d51b660c29256e273bc3c95be2434de79f154369aadc51913a37d588964852-ac13.png) |
| YouKu DSP | 阿里妈妈（睿视优酷DSP系统） | youkudsp\_int | ![ac14.png](https://files.readme.io/cd7861ff98d8ef7d5e592f566a062574f2f3d00a8153c4af9e7c6c52ea1b3a4b-ac14.png) |
| Kuaishou | 快手广告管理平台 | kuaishou\_int | ![ac15.png](https://files.readme.io/d343a8d10e71b5a2d8b22ba662d0c6347e98504f156757e8001334755b30021d-ac15.png) |
| douyu.TV | 斗鱼TV | douyu\_int | ![ac16.png](https://files.readme.io/9c68cc497965717c570f1340fc147105fc413a7b6554fb5675d5c9e00e52817b-ac16.png) |
| Bilibili Ads | 哔哩哔哩广告投放平台 | bilibili\_int | ![bilibili.logo.png](https://files.readme.io/8c25fe6af4c8d7db9d3819aed6c9be93c9d3fa6dd6bcca12624be9ee5dfd514c-bilibili.logo.png) |
| Youdao DSP | 有道智选 | youdaodsp\_int | ![youdaozhixuan.logo.png](https://files.readme.io/064a8f835094078950ba074d17cd98ef176510a54f70626bdb3d3952c20a016c-youdaozhixuan.logo.png) |
| Meitu China Ads | 美图广告平台 | meituchina\_int | ![meitu.logo.png](https://files.readme.io/202a4c2b9b4de5e9c3a1459fe1079e1c9fb769c08895f386882a80d3b27db321-meitu.logo.png) |
| Meiyou Ads | 美柚广告 女人通 | meiyou\_int | ![meiyou.logo.png](https://files.readme.io/b1eff273e3fba31a4ef268b92a03afa5c22d2f8ec7abd40eb4cd4c33a4665c68-meiyou.logo.png) |
| OPPO | OPPO | oppo\_int | ![ac17.png](https://files.readme.io/e08759d89b8cd98dc36d2ad74f06f5a619cc3203a076e7b052704975317518b9-ac17.png) |
| Yunshu | 云数（百思不得姐） | yunshu\_int | ![ac18.png](https://files.readme.io/8d3ad62114e73d6efc277fce282147f157cc71e6a6f4cd425a125d58c9c540df-ac18.png) |
| TapTap Game | TapTap | taptapgame\_int | ![ac19.png](https://files.readme.io/ddb4c7ddf69d86358add9c2d05d35cc35f7fcf0c8b65638ebd3060261be665ec-ac19.png) |
| Ipinyou | 品友 | ipinyou\_int | ![ac20.png](https://files.readme.io/5762063976f787473c9b0e26d65c4a3983eecff3c8efeff3542ad5a5608f51db-ac20.png) |
| Hupu | 虎扑 | hupu\_int | ![ac22.png](https://files.readme.io/de435baeba4cfaa6da05525894e1b58b839c2945626a0c6079103a3944918682-ac22.png) |
| Chance | 畅思 | chance\_int | ![ac23.png](https://files.readme.io/c2f6f264c8538316a3d5b759d11af5548425a8f95d5a1ef67d530d0452d99ca1-ac23.png) |
| Domob China | 多盟 | domobc\_int | ![ac24.png](https://files.readme.io/5ca87c2f0041a9d07b317d57bc35b9ac51f93b7e8220ec66c1126572c7359126-ac24.png) |
| Adwo | 安沃 | adwo\_int | ![ac26.png](https://files.readme.io/b6c0d07afcf4513ccdc13244ebb5336f319e460f784b538875532bc3643cc36a-ac26.png) |
| Youmi | 有米 | youmi\_int | ![ac28.png](https://files.readme.io/f5a17889f8777a4ddd5b130b5cfdfcf54bfc8dcda541c84d9f7a7f06e6ecbc76-ac28.png) |
| Behe | 璧合 | behe\_int | ![ac29.png](https://files.readme.io/afd4509fe986459577bc4f70bb985eb75ce698c7125e63e73ac4b0e23d4e0e72-ac29.png) |
| biddingx | 舜飞 | biddingx\_int | ![biddingx_logo.png](https://files.readme.io/f5f0b9654351e20962f704f5ca936211062d43e8529bbbe8c4ede6d1693cc044-biddingx_logo.png) |
| Auto Home Ads | 汽车之家广告平台 | autohome\_int | ![autohome_logo.png](https://files.readme.io/2389335b20f77e94a22c5ad0b2d4d7673eb88505ed5b830240804b6f3f1ca8f0-autohome_logo.png) |
| [Zhihu Ads](https://support.appsflyer.com/hc/articles/360001758338) | 知乎营销平台 | zhihu\_int | ![zhihu_logo.png](https://files.readme.io/83ae8c6e70b1aaa71addf8da9224bb1fa50a55052c25d00c61bff2dd7c87cca0-zhihu_logo.png) |
| kkworld | 快看漫画 | kkworld\_int | ![kkworld_logo.png](https://files.readme.io/8a424012e518e3908b9a9ee18aa6c3ef6f2e32992717ddb6aa8ec93576c361a9-kkworld_logo.png) |
| All Football Ads | 懂球帝广告平台 | allfootball\_int | ![allfootball_logo.png](https://files.readme.io/9d6a6bcaeb7d91b9baf38ef602383e03724ac8d4137c5962d792f5a55916191a-allfootball_logo.png) |
| VoiceAds | 讯飞DSP | voiceads\_int | ![voiceads_logo.png](https://files.readme.io/6cab8ebc8e2741351f1b716e2068988f3123f68e2e52f6f96a192afa0756ea39-voiceads_logo.png) |
| WiseMedia | 新数DSP | wisemedia\_int | ![wisemedia_logo.png](https://files.readme.io/13853d4d5fc67c568775457ae541128ead8142cf439f5ae7fd59c3cf26d49aed-wisemedia_logo.png) |
| WPS | WPS办公软件 | wps\_int | ![wps_logo.png](https://files.readme.io/0df62e39f006b3e1b55192280d61ada130c5299eb5f40b682fd5fe8db7f198b5-wps_logo.png) |
| MadhouseChina | 亿动传媒 | madhousechina\_int | ![madhouse_china_logo.png](https://files.readme.io/1778603a51bb8fd0525530f73af189763dbc7f1c6556f9245b4a0f0f74ebd482-madhouse_china_logo.png) |
| Weidong | 微动 | weidong\_int | ![weidong.png](https://files.readme.io/5e4992efe133ea21e4291d91231c0d7015cf8c2be8ece1ea45643acdd791cc74-weidong.png) |
| AdinAll | 聚告 | adinall\_int | ![adinall.logo.png](https://files.readme.io/65aab4bbe08e60a0401654b6b121e80b5e6c57b0c129740aa9ed3fd96df252b5-adinall.logo.png) |
| BlackDragon | 黑珑 | blackdragon\_int | ![blackdragon.logo.png](https://files.readme.io/e9edd70ecf6750c091648f58e9ec619016284a027bc67408ce67d09c6b422f42-blackdragon.logo.png) |
| chenbai | 宸百 | chenbai\_int | ! |
| Dayumob | 智渠传媒 | dayumob\_int | ! |
| Idvert | 艾瓦特 | idvert\_int | ! |
| Jingmeng | 京盟世纪 | jingmeng\_int | ! |
| Jusha | 巨鲨 | jusha\_int | ! |
| Mailuo | 脉络时代 | mailuo\_int | ! |
| Manhuaren | 漫画人 | manhuaren\_int | ! |
| iFeng Ads | 凤凰凤羽客户平台 | ifeng\_int | ! |
| Qutoutiao Ads | 趣头条广告 | qutoutiao\_int | ! |
| Shenma Search | 神马搜索 | smsearch\_int | ! |
| Sogou Qidian Ads | 搜狗奇点系统 | sogouqidian\_int | ! |
| Sohu XinPinSuan Ads | 搜狐新品算 | sohuxps\_int | ! |
| Tuia | 推啊 | tuia\_int | ! |
| Yidian Zixun | 一点资讯 | yidian\_int | ! |
| Zhi Zi Yun | 智子云 | zhiziyun\_int | ! |
| Hesheng | 合声 | hesheng\_int | ! |
| Zuo Ye Bang | 作业帮 | zuoyebang\_int | ! |
| Chuniu | 初牛 | chuniu\_int | ! |
| Zuiyou | 最右 | zuiyou\_int | ! |
| Himalaya Ads | 喜马拉雅广告平台 | ximalaya\_int | ![ximalaya.png](https://support.appsflyer.com/hc/article_attachments/360002781137/ximalaya.png) |
| Wifi Master Key Ads | WiFi万能钥匙广告平台 | wifimasterkey\_int | ! |
| vivo Ads | vivo营销平台 | vivoads\_int | ![vivo-logo.png](https://files.readme.io/4d192fd4b29237cfffcbd6446f622d026ecf7460c4c167678d314541af8a9693-vivo-logo.png) |
| ShiHuo Ads | 识货广告 | shihuo\_int | ![__logo.png](https://files.readme.io/cb8076f754e31df2af1d45842f721bcabdb3d93462e5bf35d559281164cbb824-__logo.png) |
| OneSavour Ads | OneSavour广告 | onesavour\_int | ![onesavour_logo.png](https://files.readme.io/d856370b4a1db2828f3a7073e180671b25eef760212cec731a8c29af66aa4b27-onesavour_logo.png) |
| Qianka | 钱咖 | qianka\_int | ![__.jpeg](https://files.readme.io/cfcab4dc5ffd2a079b791dabcf5d63e347f48f383d7b8baa7945236f930b19dc-__.jpeg) |
| SMZDM | 什么值得买 | smzdm\_int | ![logo.png](https://support.appsflyer.com/hc/article_attachments/360005790558/logo.png) |
| MGTV | 芒果TV | mgtv\_int | ![250.png](https://support.appsflyer.com/hc/article_attachments/360005790578/250.png) |
| AdView Ads | 快友 | adview\_int | ![adview_logo.png](https://support.appsflyer.com/hc/article_attachments/360006700317/adview_logo.png) |
| XTrader | 灵集 | thextrader\_int | ![thextrader_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775358/thextrader_logo.png) |
| Dianrui | 点锐 | dianrui\_int | ![dianrui_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775378/dianrui_logo.png) |
| Samsung | 三星国内 | samsungcheilcn\_int | ![samsungcheilcn_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775478/samsungcheilcn_logo.png) |
| Netease Music | 网易云音乐 | neteasemusic\_int | ![neteasemusic_logo.png](https://support.appsflyer.com/hc/article_attachments/360006700477/neteasemusic_logo.png) |
| Yixia | 小咖秀（一下科技） | yixia\_int | ![yixia_logo.png](https://support.appsflyer.com/hc/article_attachments/360006700497/yixia_logo.png) |
| Shenqi | 神奇互娱 | shenqi\_int | ![shenqi_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775498/shenqi_logo.png) |
| Tangguo | 传诺（糖果广告） | tangguo\_int | n/a |
| Hotmobi | Hotmobi | hotmobi\_int | ![hotmobi_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775538/hotmobi_logo.png) |
| Zplay | 掌游天下 | zplay\_int | ![zplay_logo.png](https://support.appsflyer.com/hc/article_attachments/360006775578/zplay_logo.png) |
| Yumi Mobi | 玉米移动 | yumimobi\_int | ![yumimobi.png](https://support.appsflyer.com/hc/article_attachments/360006775598/yumimobi.png) |
| Lanpan | 蓝畔 | lanpan\_int | ![lanpan_.png](https://support.appsflyer.com/hc/article_attachments/360006700577/lanpan_.png) |
| Xinlan | 新蓝(新效科技） | xinlan\_int | ![xinlan.png](https://support.appsflyer.com/hc/article_attachments/360006775618/xinlan.png) |
| Youlan Ads | 幽蓝 | youlanad\_int | ![youlanad.png](https://support.appsflyer.com/hc/article_attachments/360006775718/youlanad.png) |
| Avazu Ads | 艾维邑动 | avazu\_int | ![avazu.png](https://support.appsflyer.com/hc/article_attachments/360006700637/avazu.png) |
| Shangbang | 上榜（今日赚） | shangbang\_int | n/a |
| 51bizhi | 51壁纸 | 51bizhi\_int | ![51bizhi.png](https://support.appsflyer.com/hc/article_attachments/360006775838/51bizhi.png) |
| Chandashi | 禅大师 | chandashi | ![chandashi.png](https://support.appsflyer.com/hc/article_attachments/360006700677/chandashi.png) |
| Ann9 | 应用雷达 | ann9adnetwork\_int | ![ann9adnetwork.png](https://support.appsflyer.com/hc/article_attachments/360006775858/ann9adnetwork.png) |
| Gomo | 久邦数码 | gomo\_int | ![gomo.png](https://support.appsflyer.com/hc/article_attachments/360006775878/gomo.png) |
| Vision Mobile | 掌上互动 | adzshd\_int | ![adzshd.png](https://support.appsflyer.com/hc/article_attachments/360006775898/adzshd.png) |
| Adjuz | 巨掌广告 | adjuz | ![adjuz.png](https://support.appsflyer.com/hc/article_attachments/360006700717/adjuz.png) |
| Guohe Ads | 果合广告 | guohe\_int | ![guohe.png](https://support.appsflyer.com/hc/article_attachments/360006700777/guohe.png) |
| Mintegral | Mintegral | mingtegral\_int | ![mintegral.png](https://support.appsflyer.com/hc/article_attachments/360006700797/mintegral.png) |
| Mobvista | Mobvista | mobvista\_int | ![mobvista.png](https://support.appsflyer.com/hc/article_attachments/360006700857/mobvista.png) |
| Emar | 亿玛 | yima\_int | ![yima.png](https://support.appsflyer.com/hc/article_attachments/360006775938/yima.png) |
| Centrixlink | 隐逸数字 | centrixlink\_int | ![centrixlink.png](https://support.appsflyer.com/hc/article_attachments/360006775958/centrixlink.png) |
| Codrim | 氪金 | codrim\_int | ![codrim.png](https://support.appsflyer.com/hc/article_attachments/360006700837/codrim.png) |
| lbadvisor | 量江湖（比邻弘科） | lbadvisor | ![lbadvisor.png](https://support.appsflyer.com/hc/article_attachments/360006775978/lbadvisor.png) |
| ADYOYU | 涌玉 | yoyuad\_int | ![yoyuad.png](https://support.appsflyer.com/hc/article_attachments/360006701357/yoyuad.png) |
| KUAIZI | 筷子科技 | kuaizi\_int | ![kuaizi.png](https://support.appsflyer.com/hc/article_attachments/360006701397/kuaizi.png) |
| Yeahmobi | 易点天下 | yeahmobi\_int | ![yeahmobi.png](https://support.appsflyer.com/hc/article_attachments/360006701457/yeahmobi.png) |
| HUYA | 虎牙直播 | huya\_int | ![____LOGO.png](https://support.appsflyer.com/hc/article_attachments/360008824198/____LOGO.png) |
| MJweather | 墨迹天气 | mjweather\_int | ![200-50.jpg](https://support.appsflyer.com/hc/article_attachments/360009924837/200-50.jpg) |
| Codoon | 咕咚 | codoon\_int | ![__logo.png](https://support.appsflyer.com/hc/article_attachments/360009924537/__logo.png) |
| LongXi DSP | 珑玺DSP | lxdsp\_int | ![lxdsp_int.png](https://support.appsflyer.com/hc/article_attachments/360010023738/lxdsp_int.png) |