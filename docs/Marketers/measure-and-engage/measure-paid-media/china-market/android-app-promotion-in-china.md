---
title: "Android app promotion in China"
excerpt: "Best practices to promote your Android app in the Chinese market."
x-zendesk:
  id: 115004639203
  url: https://support.appsflyer.com/hc/en-us/articles/115004639203-Android-app-promotion-in-China
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China market
  section_id: 6552042145425
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-09-12T08:13:46Z'
  edited_at: '2023-02-15T13:15:04Z'
---
## Android apps in China

Treat the sections that follow as a checklist of items that you should consider if you market your app in China.

### Selecting an identifier

To achieve accurate attribution a unique identifier (ID) that represents the user is required. On devices where Google Play services (GPS) are active this historically has been the Google advertising ID (GAID).

At present GPS is not available on devices marketed in China. App owners are required to use alternative ID based on device hardware being IMEI and Android ID.

Starting with [Android 10 (API  level 29)](https://developer.android.com/training/articles/user-data-ids), released in late 2019,  access to the IMEI and Android ID is restricted. The effect of this is that the IMEI/Android ID won't be accessible on newer devices.

To overcome this, an alternative to GAID, is OAID. OAID (available starting late 2019) is being promoted by Chinese device manufacturers, for example, [Huawei](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3030304).

See[AppsFlyer SDK Integration - Android](/docs/measure-attribution-in-the-chinese-domestic-market).

### Attribution solutions for the Chinese market

Since there are multiple Android App stores that serve the Chinese market, AppsFlyer provides the solutions described here to attribute Android installs.

Chinese Android device users download apps from different Chinese Android App Stores instead of Google Play and most of these App Stores provide ad units for App Advertisers. Among these App Stores the main ones are Tencent MyApp, 360 App Store, Baidu App Store, Xiaomi App Store, OPPO App Store and Huawei App Store.

For example, if you want to promote your Android App via Tencent Social Ads, Tencent Tui Ads and Wechat Ads, upload the Android app to MyApp (Tencent Android App Store), which brings you organic installs at the same time. Baidu series ad networks, 360 Ads, Xiaomi Ads, OPPO Ads all operate in a similar way.

[![](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)

Meanwhile, many Android installs are generated from APK download links in mobile web pages or in-app ad space.

AppsFlyer provides three main solutions to attribute Android App installs in China market, use the method most relevant to your needs.

<Accordion title="Local android app store that supports ad attribution">

**Solution:** Android out-of-store app with attribution Link

**Description:** The well-known Chinese Internet companies or mobile device manufacturers have created their own Android App Stores and Ad Platforms/Ad Networks, taking advantage of their huge traffic resources in China's domestic market. However, these big companies strictly control traffic to see if the user who clicked on their ad downloads the App from the App Store of a different company. In such situations, you have to generate a unique out-of-Store App for each Android App Store. Meanwhile, you can use the AppsFlyer attribution link to record the performance of the ad campaigns built on those companies’ own Ad platforms/Ad Networks.

By using this method, you can attribute both organic install and non-organic installs. At the same time, you can optimize ad campaigns in the term of ad units, ad set and creatives, etc.

**Example:** If you want to promote your Android App via Tencent Social Ads, Tencent Tui Ads, and Wechat Ads, you must upload the Android App to Tencent Android App Store and MyApp, etc, which brings you organic installs at the same time. Baidu series ad networks, 360 Ads, Xiaomi Ads, OPPO Ads all work in the same way.

**Preparation:** How to attribute out-of-store apps, click [here](/docs/set-up-multi-store-android-attribution).

</Accordion>

<Accordion title="Ad network">

**Solution:** APK Download Link / APK + Attribution Link

**Description:** To promote Android Apps in Ad Networks that have no mandatory requirement on where to download the App, you can simply provide an APK Download Link or an APK and the AppsFlyer attribution link to the media source.

It is easy and fast to launch ad campaigns. It is also convenient to check the performance of different media sources at the same app overview page.

**Example:** Bytedance Ads(Toutiao), Sina Weibo, iQiyi

**Preparation:** Set up one Android out-of-store app, and generate different attribution links for different ad networks. To learn how to attribute out-of-store apps, click [here](/docs/set-up-multi-store-android-attribution).

</Accordion>

<Accordion title="Android app store that does not support ad attribution">

**Solution:** Android out-of-store app

**Description:**  For Android App Stores that do not support ad attribution, you can still use Out-Of-Store Apps to attribute all the installs coming from this App Store, only all the installs are attributed as organic installs.

**Example:** Lenovo app store, Huawei app store.

**Preparation:** how to attribute out-of-store apps, click [here](/docs/set-up-multi-store-android-attribution).

</Accordion>

If you are promoting your apps with more than one of the solutions mentioned above and you want to check the data of all your China campaigns int the same dashboard view, you can use [Custom Dashboard](/docs/custom-dashboards).

## Integrated media sources

[Configuration guides](/docs/china-domestic-market-ad-network-configuration)

Integrated media sources in China:

| Media source name | Chinese name | PID | Logo |
| --- | --- | --- | --- |
| Tencent Ads | 腾讯广告 | tencent\_int | ![ac1.png](https://files.readme.io/68f25ee4e8656ca36ea7ca48b2de7278f709fd93cb06f0db57b31afd27a65c57-115015067906.png) |
| [Bytedance Ads](/docs/bytedance-ads-china-campaign-configuration) | 巨量引擎（今日头条） | bytedance\_int | ![ac2.png](https://files.readme.io/cf43a8ae5a29032e86317f11a4af2beb60dfa8ac986a12f57fac6ddc0b7ae9ae-115015067926.png) |
| [WeChat Ads](/docs/wechat-ads-campaign-configuration) | 微信公众平台 | wechat\_int | ![ac4.png](https://files.readme.io/a1050b99def37cd07093dfebf34cee86f0d71ccb9cc407e5ebe87c3ea594a39b-115015067966.png) |
| [Weibo Ads](/docs/sina-weibo-ads-campaign-configuration) | 微博超级粉丝通 | sinaweibo\_int | ![ac5.png](https://files.readme.io/6902d459e199231a44deb9d64de0cf3ee8fe96d28e246e0506bbb275a8e225d5-115015247263.png) |
| Sina Fuyi Ads | 新浪扶翼 | sinafuyi\_int | ![sinafuyi.logo.png](https://files.readme.io/e3b19f22bbb8ccd9aba37ac1d7f8222f8c90d6510622a59a80d2acf73d1f5dab-360001660797.png) |
| [Baidu App Ads](/docs/baidu-app-ads-campaign-configuration) | 百度百通 | baitong\_int | ![ac6.png](https://files.readme.io/3055bb4a6865304d3117b714d364f84f233a25372ae251fefb07cbd5681bd27e-115015067986.png) |
| [Baidu mDSP](/docs/baidu-mdsp-ads-baiyi-campaign-configuration) | 百度百易 | baidumdsp\_int | ![ac7.png](https://files.readme.io/f610964f7895989f3535f9b389fd0c7218b1c44e68a7ba9c539fc0d0a1ee825a-115015068006.png) |
| Baidu Search Ads | 百度搜索广告 | baidusearch\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/baidusearch.png) |
| Baidu Native Ads | 百度信息流广告（百度原生） | baidufeedads\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png) |
| Baidu Native Ads 2.0 | 百度信息流广告（百度原生）2.0 | baiduxinxiliu\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png) |
| [Xiaomi Ads & App Store](/docs/xiaomi-ads-network-campaign-configuration) | 小米营销平台 & 应用商店 | xiaomichina\_int | ![ac8.png](https://files.readme.io/4976cf0391214984b4bbce7ad66f9df71c72a5eef3c74414d77ad1fe569c19ff-115015068026.png) |
| Huawei App Gallery in China | 华为应用商店 | huaweiappgallerychina\_int | ![huawei_app_store_logo.png](https://files.readme.io/29f84e8d0e90fc5bb85fc86810a45810fd0bc5fea58869c124b8f66354b67c78-10801903185809.png) |
| OPPO App Store in China | OPPO软件商店 | oppostorechina\_int | ![oppo_store_logo.png](https://files.readme.io/30bdc4b4613f423f028eea5adfc6eee714805db65b857c49d6221639f19b3523-10801961659153.png) |
| vivo Ads & App Store | vivo营销平台&应用商店 | vivoads\_int | ![vivo_store_logo.png](https://files.readme.io/5b3b87a0d4a6c424421d9d1b156cf0b1d81da7b534a53e760227de2726db8445-10802004853009.png) |
| 360 Ads | 360点睛实效平台 | 360\_int | ![ac9.png](https://files.readme.io/b2a47bc04124313c237898040c72ee5eee2e86754333eea35f7b35c4ac0bd7f1-115015068046.png) |
| Ali UC Ads | 阿里汇川 （UC头条） | uctoutiao\_int | ![ac10.png](https://files.readme.io/5a40ba07cd5b23b898849bf1ef6689704de0e4773c354ed52f455ef6418fdd61-115015068086.png) |
| Netease Ads | 网易易效 | netease\_int | ![ac11.png](https://files.readme.io/6572ef63727ca2aa95cdf747804ec9b061e744e130dd0285ccda84bd0fdd5820-115015068106.png) |
| iQIYI Ads | 爱奇艺奇麟神算 | iqiyi\_int | ![ac12.png](https://files.readme.io/7a3eab06d7e7bd598e750e69ea72c2a127322dbe343c889b025803ca766a5d85-115015247303.png) |
| MOMO Ads | 陌陌广告 | momo\_int | ![ac13.png](https://files.readme.io/17478fe1e70278da1ee55522fe0132a7a42e11c36a4b86ebb5fde14a17d9abb2-115015247323.png) |
| YouKu DSP | 阿里妈妈（睿视优酷DSP系统） | youkudsp\_int | ![ac14.png](https://files.readme.io/2aabab6dc35278c15dd687cfb0ae3dee71c372226265b0606b6381ea7d90a8da-115015247343.png) |
| Kuaishou | 快手广告管理平台 | kuaishou\_int | ![ac15.png](https://files.readme.io/801097b7fb9ce7020cddde8db46093fb39ad55a01b4ae282f5ffc44e591c5bd4-115015068126.png) |
| douyu.TV | 斗鱼TV | douyu\_int | ![ac16.png](https://files.readme.io/7ab338fd14e1b35c3eb5c20184a451516a05f98a3fcf605d9a04ccec546105e1-115015247363.png) |
| Bilibili Ads | 哔哩哔哩广告投放平台 | bilibili\_int | ![bilibili.logo.png](https://files.readme.io/f2b2cd2378d48beb8770a89694e441a5bb1dd00b30b1eac540df7f306878b594-360001660817.png) |
| Youdao DSP | 有道智选 | youdaodsp\_int | ![youdaozhixuan.logo.png](https://files.readme.io/9c9c9fc6b2226e666829373beef151a65ec38393a496bd3563a8649438d4331d-360001660837.png) |
| Meitu China Ads | 美图广告平台 | meituchina\_int | ![meitu.logo.png](https://files.readme.io/0bc4911d6a5455207e31d1f1a00d7af54c0f3a93167dbfabb33cdd96bb430c2f-360001660857.png) |
| Meiyou Ads | 美柚广告 女人通 | meiyou\_int | ![meiyou.logo.png](https://files.readme.io/413aae7d93717526cfdad51afac4097f22e0c826c79a44d14326f65b1805b6a2-360001660877.png) |
| OPPO | OPPO | oppo\_int | ![ac17.png](https://files.readme.io/6a6aeb9b3675eb5f28b29a47c5fb454c3f5f8fc4c49c856ceccc4e0922c45200-115015247383.png) |
| Yunshu | 云数（百思不得姐） | yunshu\_int | ![ac18.png](https://files.readme.io/09e91278b253f5c7dcd7c681a52a960b346b0665d20084bb64afb7bf2c94e5ba-115015247403.png) |
| TapTap Game | TapTap | taptapgame\_int | ![ac19.png](https://files.readme.io/536f59f036f7c4f027308dbd25c6d04db8748c070fd6e2fbbb3816d13cbfa577-115015068146.png) |
| Ipinyou | 品友 | ipinyou\_int | ![ac20.png](https://files.readme.io/54121bb0a388c6e238749ae6166e30fafcd251a94518abaa0e5de02005f078f3-115015068166.png) |
| Hupu | 虎扑 | hupu\_int | ![ac22.png](https://files.readme.io/a463753277f62ef989271ce9433940f02cbbf7a9e11b6dd675c1b81f8207223c-115015068226.png) |
| Chance | 畅思 | chance\_int | ![ac23.png](https://files.readme.io/7dbac1e40c129085b9be9e24937e0e22b0ff16d5bc2e2b75da3a7b83e8f90acd-115015068246.png) |
| Domob China | 多盟 | domobc\_int | ![ac24.png](https://files.readme.io/0a01e63ce107e0fb23602ff13b6f76d05b4f1464dc82016ef4bcfc17fe9c291e-115015247423.png) |
| Adwo | 安沃 | adwo\_int | ![ac26.png](https://files.readme.io/1fa607feffbf2adfc5905c607f45960585f24cf58dd63d434ffa5ba2a1760923-115015068266.png) |
| Youmi | 有米 | youmi\_int | ![ac28.png](https://files.readme.io/d8eeaa83743d8fbb5dc2ee27cf5426ccd81ee7304d3e1cdd3e8f7e113f3b99fc-115015247483.png) |
| Behe | 璧合 | behe\_int | ![ac29.png](https://files.readme.io/653b4e503246e97f7b11a8886737d265d1cd200bf3233d70b5915a0539a5bbe5-115015068286.png) |
| biddingx | 舜飞 | biddingx\_int | ![biddingx_logo.png](https://files.readme.io/20035c58ff95b7f5699e4fd5533c0a542b24382bbeeefdfbc89738091d4f61fd-115011112389.png) |
| Auto Home Ads | 汽车之家广告平台 | autohome\_int | ![autohome_logo.png](https://files.readme.io/520e07ee6f027dbfd0ce8fde3d7b2e11093e38bd5aaa58a2f91dd4d489376b16-115011049905.png) |
| [Zhihu Ads](/docs/zhihu-ads-campaign-configuration) | 知乎营销平台 | zhihu\_int | ![zhihu_logo.png](https://files.readme.io/049b99c1deae5f494ce426a899f6689521d2b9a531bb0caa2e0d1745e14f5809-115011049925.png) |
| kkworld | 快看漫画 | kkworld\_int | ![kkworld_logo.png](https://files.readme.io/c7e6f1fc339750a2bb61fc01a54df81d236e9bdb3e99255051ae2f812d5b225f-115011112409.png) |
| All Football Ads | 懂球帝广告平台 | allfootball\_int | ![allfootball_logo.png](https://files.readme.io/2522198caeaa17915b6b70c682b8cd772a9dd520f92b76f80d74176ff69c4fa9-115011049945.png) |
| VoiceAds | 讯飞DSP | voiceads\_int | ![voiceads_logo.png](https://files.readme.io/7c9fdba5a283531bb430bb68e9955e6926697f43bd9b188063795ddca37903cd-115011049985.png) |
| WiseMedia | 新数DSP | wisemedia\_int | ![wisemedia_logo.png](https://files.readme.io/e0aab2a9b2d989b936c8df207ccd860a008d6c5015ef8c4ad154e254f7b09105-115011050005.png) |
| WPS | WPS办公软件 | wps\_int | ![wps_logo.png](https://files.readme.io/8f85e6f569a29612b85f468a8e91e42e8bf654eac12f4f4b9be42dea02babd1c-115011112429.png) |
| MadhouseChina | 亿动传媒 | madhousechina\_int | ![madhouse_china_logo.png](https://files.readme.io/01b0831cfb73bc0c049c9ae70e34fdd2781871a1bebe40d62d63b346be1c6fbf-115011050025.png) |
| Weidong | 微动 | weidong\_int | ![weidong.png](https://files.readme.io/c355c3e4ae3a0b215ec5caa7a910164f5667bf7d34a308b0b77437540eb9ee56-360002013098.png) |
| AdinAll | 聚告 | adinall\_int | ![adinall.logo.png](https://files.readme.io/29bceececa81b30a55204ea6ac7abe219737441ca4017e5f5944c53d55f3ecc8-360001976997.jpg) |
| BlackDragon | 黑珑 | blackdragon\_int | ![blackdragon.logo.png](https://files.readme.io/2247dfaaa2ac63b1ddd09e37963188e3ca9315d0454a1f228f3113bb470a1406-360002076458.png) |
| chenbai | 宸百 | chenbai\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/chenbai.png?v=1) |
| Dayumob | 智渠传媒 | dayumob\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/dayumob.png?v=1) |
| Idvert | 艾瓦特 | idvert\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/idvert.png?v=1) |
| Jingmeng | 京盟世纪 | jingmeng\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/jingmeng.png?v=1) |
| Jusha | 巨鲨 | jusha\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/jusha.png?v=1) |
| Mailuo | 脉络时代 | mailuo\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/mailuo.png?v=1) |
| Manhuaren | 漫画人 | manhuaren\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/manhuaren.png?v=1) |
| iFeng Ads | 凤凰凤羽客户平台 | ifeng\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/ifeng.png?v=1) |
| Qutoutiao Ads | 趣头条广告 | qutoutiao\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/qutoutiao.png?v=1) |
| Shenma Search | 神马搜索 | smsearch\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/smsearch.png?v=1) |
| Sogou Qidian Ads | 搜狗奇点系统 | sogouqidian\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/sogouqidian.png?v=1) |
| Sohu XinPinSuan Ads | 搜狐新品算 | sohuxps\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/sohuxps.png?v=1) |
| Tuia | 推啊 | tuia\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/tuia.png?v=1) |
| Yidian Zixun | 一点资讯 | yidian\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/yidianzixun.png?v=1) |
| Zhi Zi Yun | 智子云 | zhiziyun\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/zhiziyun.png) |
| Hesheng | 合声 | hesheng\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/hesheng.png?v=1) |
| Zuo Ye Bang | 作业帮 | zuoyebang\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/zuoyebang.png?v=1) |
| Chuniu | 初牛 | chuniu\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/chuniu.png?v=1) |
| Zuiyou | 最右 | zuiyou\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/zuiyou.png) |
| Himalaya Ads | 喜马拉雅广告平台 | ximalaya\_int | ![ximalaya.png](https://support.appsflyer.com/hc/article_attachments/360002781137/ximalaya.png) |
| Wifi Master Key Ads | WiFi万能钥匙广告平台 | wifimasterkey\_int | ![](https://cdn.appsflyer.com/marketplace/static/logo/wifimasterkey.png) |
| vivo Ads | vivo营销平台 | vivoads\_int | ![vivo-logo.png](https://files.readme.io/fd5eea06d85e2b9993c0fcc961dacc9559d917aea1e78ad1c069546649a8eb86-360003580657.png) |
| ShiHuo Ads | 识货广告 | shihuo\_int | ![__logo.png](https://files.readme.io/d5ae526235128f06bcb986130b1e6ae2cb1f66e0d053760a0f6ad9565c5bbfc1-360004371338.png) |
| OneSavour Ads | OneSavour广告 | onesavour\_int | ![onesavour_logo.png](https://files.readme.io/e18db5eb6450c5cc1ddd8b5425808a502ee82790e330ccf5a42454cb6260835b-360004371358.png) |
| Qianka | 钱咖 | qianka\_int | ![__.jpeg](https://files.readme.io/bd78e74e85eecdd7abf85be01b5bf0bb532941900fe42f6a2e9d9bf91219c5fe-360004682538.jpg) |
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