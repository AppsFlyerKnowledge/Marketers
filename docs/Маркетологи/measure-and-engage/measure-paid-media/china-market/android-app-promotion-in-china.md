---
title: Продвижение Android-приложения в Китае
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-09-12T08:13:46Z'
  edited_at: '2026-09-01T00:29:12Z'
  id: 115004639203
  locale: ru
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/ru/articles/115004639203
---
> **Кратко:** практические рекомендации по продвижению вашего Android-приложения на китайском рынке.

<div id="android-apps-in-china" />

## Android-приложения в Китае

Рассматривайте следующие разделы как контрольный список того, что нужно учесть при продвижении приложения в Китае.

<div id="selecting-an-identifier" />

### Выбор идентификатора

Для точной атрибуции требуется уникальный идентификатор (ID), представляющий пользователя. На устройствах, где активны сервисы Google Play (GPS), исторически для этого использовался рекламный идентификатор Google (GAID).

В настоящее время GPS недоступны на устройствах, продаваемых в Китае. Владельцы приложений должны использовать альтернативные идентификаторы на основе аппаратных данных устройства, например IMEI и Android ID.

Начиная с [Android 10 (уровень API  29)](https://developer.android.com/training/articles/user-data-ids), выпущенной в конце 2019 года, доступ к IMEI и Android ID ограничен. В результате IMEI/Android ID будут недоступны на более новых устройствах.

Для решения этой проблемы в качестве альтернативы GAID используется OAID. OAID (доступный с конца 2019 года) продвигается китайскими производителями устройств, например [Huawei](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3030304).

См. <Anchor target="_blank" href="/marketers/ru/docs/measure-attribution-in-the-chinese-domestic-market">Интеграция AppsFlyer SDK – Android</Anchor>.

<div id="attribution-solutions-for-the-chinese-market" />

### Решения для атрибуции на китайском рынке

Поскольку китайский рынок обслуживают несколько магазинов приложений Android, AppsFlyer предоставляет описанные здесь решения для атрибуции установок Android-приложений.

Пользователи Android-устройств в Китае загружают приложения из различных китайских магазинов приложений Android вместо Google Play, и большинство этих магазинов приложений предоставляют рекламные форматы для рекламодателей приложений. Среди этих магазинов приложений основными являются Tencent MyApp, 360 App Store, Baidu App Store, Xiaomi App Store, OPPO App Store и Huawei App Store.

Например, если вы хотите продвигать свое Android-приложение через Tencent Social Ads, Tencent Tui Ads и Wechat Ads, загрузите Android-приложение в MyApp (магазин приложений Tencent для Android), что одновременно принесет вам органические установки. Рекламные сети Baidu, 360 Ads, Xiaomi Ads и OPPO Ads работают схожим образом.

<Image align="center" alt="" src="https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png" />

При этом многие установки Android генерируются по ссылкам на загрузку APK на страницах мобильного веба или в рекламных местах внутри приложения.

AppsFlyer предлагает три основных решения для атрибуции установок приложения Android на рынке Китая. Используйте метод, который лучше всего соответствует вашим потребностям.

<div id="local-android-app-store-that-supports-ad-attribution" />

<Accordion title="Локальный магазин приложений Android с поддержкой атрибуции рекламы">

**Решение:** Android-приложение, установленное вне магазина, со ссылкой для атрибуции

**Описание:** TИзвестные китайские интернет-компании или производители мобильных устройств создали собственные магазины приложений Android и рекламные платформы/рекламные сети, используя свои огромные ресурсы трафика на внутреннем рынке Китая. Однако эти крупные компании строго контролируют трафик, чтобы видеть, загружает ли пользователь, который кликнул по их рекламе, приложение из магазина приложений другой компании. В таких случаях необходимо создавать уникальное приложение, установленное вне магазина, для каждого магазина приложений Android. При этом вы можете использовать ссылку атрибуции AppsFlyer, чтобы отслеживать эффективность кампаний, созданных на собственных рекламных платформах и в рекламных сетях этих компаний.

С помощью этого метода можно атрибутировать как органические, так и неорганические установки. При этом вы можете оптимизировать рекламные кампании по рекламным блокам, группам объявлений, креативам и т. д.

**Пример:** Если вы хотите продвигать свое приложение Android через Tencent Social Ads, Tencent Tui Ads и Wechat Ads, необходимо загрузить приложение Android в Tencent Android App Store и MyApp и т. д., что одновременно приносит вам органические установки. Серия рекламных сетей Baidu, 360 Ads, Xiaomi Ads и OPPO Ads работают одинаково.

**Подготовка:** Чтобы узнать, как атрибутировать приложения, установленные вне магазина, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">здесь</Anchor>.

</Accordion>

<div id="ad-network" />

<Accordion title="Реклама ShiHuo">

**Решение:** Ссылка для загрузки APK / APK + ссылка атрибуции

**Описание:**  Для магазинов приложений Android, которые не поддерживают атрибуцию рекламы, вы все равно можете использовать приложения, установленные вне магазина, чтобы атрибутировать все установки из этого магазина приложений, однако все эти установки будут атрибутированы как органические установки.

Запускать рекламные кампании легко и быстро. Также удобно проверять эффективность разных медиаисточников на одной и той же странице обзора приложения.

**Пример:** Bytedance Ads(Toutiao), Sina Weibo, iQiyi

**Подготовка:** Настройте одно приложение Android, установленное вне магазина, и создайте разные ссылки атрибуции для разных рекламных сетей. Чтобы узнать, как атрибутировать приложения, установленные вне магазина, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">здесь</Anchor>.

</Accordion>

<div id="android-app-store-that-does-not-support-ad-attribution" />

<Accordion title="Магазин приложений Android, не поддерживающий атрибуцию рекламы">

**Решение:** Приложение Android, установленное вне магазина

**Описание:**  Для магазинов приложений Android, которые не поддерживают атрибуцию рекламы, вы все равно можете использовать приложения, установленные вне магазина, чтобы атрибутировать все установки из этого магазина приложений, однако все эти установки будут атрибутированы как органические установки.

**Пример:** Lenovo App Store, Huawei App Store.

**Подготовка:** чтобы узнать, как атрибутировать приложения, установленные вне магазина, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">здесь</Anchor>.

</Accordion>

Если вы продвигаете свои приложения с помощью нескольких из указанных выше решений и хотите просматривать данные по всем своим кампаниям в Китае в одном представлении дэшборда, вы можете использовать <Anchor target="_blank" href="/marketers/ru/docs/custom-dashboards">пользовательский дэшборд</Anchor>.

<div id="integrated-media-sources" />

## Интегрированные медиаисточники

<Anchor target="_blank" href="/marketers/ru/docs/china-domestic-market-ad-network-configuration">Руководства по настройке</Anchor>

Интегрированные медиаисточники в Китае:

| Название медиаисточника | Название на китайском | pid | Логотип |
| --- | --- | --- | --- |
| Tencent Ads | 腾讯广告 | tencent\_int | ![ac1.png](https://files.readme.io/68f25ee4e8656ca36ea7ca48b2de7278f709fd93cb06f0db57b31afd27a65c57-115015067906.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/bytedance-ads-china-campaign-configuration">Bytedance Ads</Anchor> | 巨量引擎（今日头条） | bytedance\_int | ![ac2.png](https://files.readme.io/cf43a8ae5a29032e86317f11a4af2beb60dfa8ac986a12f57fac6ddc0b7ae9ae-115015067926.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/wechat-ads-campaign-configuration">WeChat Ads</Anchor> | Платформа официальных аккаунтов WeChat | wechat\_int | ![ac4.png](https://files.readme.io/a1050b99def37cd07093dfebf34cee86f0d71ccb9cc407e5ebe87c3ea594a39b-115015067966.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/sina-weibo-ads-campaign-configuration">Weibo Ads</Anchor> | 微博超级粉丝通 | sinaweibo\_int | ![ac5.png](https://files.readme.io/6902d459e199231a44deb9d64de0cf3ee8fe96d28e246e0506bbb275a8e225d5-115015247263.png) |
| Реклама Sina Fuyi | 新浪扶翼 | sinafuyi\_int | ![sinafuyi.logo.png](https://files.readme.io/e3b19f22bbb8ccd9aba37ac1d7f8222f8c90d6510622a59a80d2acf73d1f5dab-360001660797.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/baidu-app-ads-campaign-configuration">Baidu App Ads</Anchor> | 百度百通 | baitong\_int | ![ac6.png](https://files.readme.io/3055bb4a6865304d3117b714d364f84f233a25372ae251fefb07cbd5681bd27e-115015067986.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/baidu-mdsp-ads-baiyi-campaign-configuration">Baidu mDSP</Anchor> | Baidu Baiyi | baidumdsp\_int | ![ac7.png](https://files.readme.io/f610964f7895989f3535f9b389fd0c7218b1c44e68a7ba9c539fc0d0a1ee825a-115015068006.png) |
| Поисковая реклама Baidu | Поисковая реклама Baidu | baidusearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidusearch.png" width="112px" /> |
| Нативная реклама Baidu | Нативная реклама Baidu | baidufeedads\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| Нативная реклама Baidu 2 | Нативная реклама Baidu 2.0 | baiduxinxiliu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/xiaomi-ads-network-campaign-configuration">Реклама Xiaomi & магазин приложений</Anchor> | Маркетинговая платформа Xiaomi & магазин приложений | xiaomichina\_int | <Image alt="ac8.png" src="https://files.readme.io/4976cf0391214984b4bbce7ad66f9df71c72a5eef3c74414d77ad1fe569c19ff-115015068026.png" width="37px" /> |
| Huawei AppGallery в Китае | Huawei AppGallery | huaweiappgallerychina\_int | <Image alt="huawei_app_store_logo.png" src="https://files.readme.io/29f84e8d0e90fc5bb85fc86810a45810fd0bc5fea58869c124b8f66354b67c78-10801903185809.png" width="40px" /> |
| Магазин приложений OPPO в Китае | Магазин приложений OPPO | oppostorechina\_int | ![oppo_store_logo.png](https://files.readme.io/30bdc4b4613f423f028eea5adfc6eee714805db65b857c49d6221639f19b3523-10801961659153.png) |
| vivo Реклама & магазин приложений | vivo营销平台&应用商店 | vivoads\_int | <Image alt="vivo_store_logo.png" src="https://files.readme.io/5b3b87a0d4a6c424421d9d1b156cf0b1d81da7b534a53e760227de2726db8445-10802004853009.png" width="41px" /> |
| 360 Ads | 360点睛实效平台 | 360\_int | ![ac9.png](https://files.readme.io/b2a47bc04124313c237898040c72ee5eee2e86754333eea35f7b35c4ac0bd7f1-115015068046.png) |
| Ali UC Ads | 阿里汇川 （UC头条） | uctoutiao\_int | ![ac10.png](https://files.readme.io/5a40ba07cd5b23b898849bf1ef6689704de0e4773c354ed52f455ef6418fdd61-115015068086.png) |
| Netease Ads | 网易易效 | netease\_int | ![ac11.png](https://files.readme.io/6572ef63727ca2aa95cdf747804ec9b061e744e130dd0285ccda84bd0fdd5820-115015068106.png) |
| iQIYI Ads | 爱奇艺奇麟神算 | iqiyi\_int | ![ac12.png](https://files.readme.io/7a3eab06d7e7bd598e750e69ea72c2a127322dbe343c889b025803ca766a5d85-115015247303.png) |
| MOMO Ads | 陌陌广告 | momo\_int | ![ac13.png](https://files.readme.io/17478fe1e70278da1ee55522fe0132a7a42e11c36a4b86ebb5fde14a17d9abb2-115015247323.png) |
| YouKu DSP | 阿里妈妈（睿视优酷DSP系统） | youkudsp\_int | <Image alt="ac14.png" src="https://files.readme.io/2aabab6dc35278c15dd687cfb0ae3dee71c372226265b0606b6381ea7d90a8da-115015247343.png" width="98px" /> |
| Kuaishou | Рекламная платформа Kuaishou | kuaishou\_int | ![ac15.png](https://files.readme.io/801097b7fb9ce7020cddde8db46093fb39ad55a01b4ae282f5ffc44e591c5bd4-115015068126.png) |
| douyu.TV | 斗鱼TV | douyu\_int | ![ac16.png](https://files.readme.io/7ab338fd14e1b35c3eb5c20184a451516a05f98a3fcf605d9a04ccec546105e1-115015247363.png) |
| Реклама Bilibili | Рекламная платформа Bilibili | bilibili\_int | ![bilibili.logo.png](https://files.readme.io/f2b2cd2378d48beb8770a89694e441a5bb1dd00b30b1eac540df7f306878b594-360001660817.png) |
| Youdao DSP | Youdao Zhixuan | youdaodsp\_int | ![youdaozhixuan.logo.png](https://files.readme.io/9c9c9fc6b2226e666829373beef151a65ec38393a496bd3563a8649438d4331d-360001660837.png) |
| Реклама Meitu в Китае | Рекламная платформа Meitu | meituchina\_int | ![meitu.logo.png](https://files.readme.io/0bc4911d6a5455207e31d1f1a00d7af54c0f3a93167dbfabb33cdd96bb430c2f-360001660857.png) |
| Реклама Meiyou | Реклама Meiyou Woman Connect | meiyou\_int | ![meiyou.logo.png](https://files.readme.io/413aae7d93717526cfdad51afac4097f22e0c826c79a44d14326f65b1805b6a2-360001660877.png) |
| Oppo | Oppo | oppo\_int | <Image alt="ac17.png" src="https://files.readme.io/6a6aeb9b3675eb5f28b29a47c5fb454c3f5f8fc4c49c856ceccc4e0922c45200-115015247383.png" width="131px" /> |
| Yunshu | Юньшу（Байсыбудэцзе） | yunshu\_int | ![ac18.png](https://files.readme.io/09e91278b253f5c7dcd7c681a52a960b346b0665d20084bb64afb7bf2c94e5ba-115015247403.png) |
| TapTap Game | TapTap | taptapgame\_int | ![ac19.png](https://files.readme.io/536f59f036f7c4f027308dbd25c6d04db8748c070fd6e2fbbb3816d13cbfa577-115015068146.png) |
| Ipinyou | Пинью | ipinyou\_int | ![ac20.png](https://files.readme.io/54121bb0a388c6e238749ae6166e30fafcd251a94518abaa0e5de02005f078f3-115015068166.png) |
| Hupu | Хупу | hupu\_int | ![ac22.png](https://files.readme.io/a463753277f62ef989271ce9433940f02cbbf7a9e11b6dd675c1b81f8207223c-115015068226.png) |
| Chance | Чансы | chance\_int | ![ac23.png](https://files.readme.io/7dbac1e40c129085b9be9e24937e0e22b0ff16d5bc2e2b75da3a7b83e8f90acd-115015068246.png) |
| Domob China | Домэн | domobc\_int | ![ac24.png](https://files.readme.io/0a01e63ce107e0fb23602ff13b6f76d05b4f1464dc82016ef4bcfc17fe9c291e-115015247423.png) |
| Adwo | 安沃 | adwo\_int | ![ac26.png](https://files.readme.io/1fa607feffbf2adfc5905c607f45960585f24cf58dd63d434ffa5ba2a1760923-115015068266.png) |
| Youmi | 有米 | youmi\_int | ![ac28.png](https://files.readme.io/d8eeaa83743d8fbb5dc2ee27cf5426ccd81ee7304d3e1cdd3e8f7e113f3b99fc-115015247483.png) |
| Behe | 璧合 | behe\_int | ![ac29.png](https://files.readme.io/653b4e503246e97f7b11a8886737d265d1cd200bf3233d70b5915a0539a5bbe5-115015068286.png) |
| biddingx | 舜飞 | biddingx\_int | <Image alt="biddingx_logo.png" src="https://files.readme.io/ce39102d4bb1b167b621a98f549c9d0ed6734574d5114699e5fe5207f1626946-115011049765.png" width="114px" /> |
| Auto Home Ads | 汽车之家广告平台 | autohome\_int | <Image alt="autohome_logo.png" src="https://files.readme.io/318da1d84a688f873e25ee59924e1c39268e18aef5f2cb19f2daf2ffbec6dcd5-115011049785.png" width="104px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/zhihu-ads-campaign-configuration">Zhihu Ads</Anchor> | 知乎营销平台 | zhihu\_int | <Image alt="zhihu_logo.png" src="https://files.readme.io/07e4355e4c74541dc943831483a19662425b3a2efdd7dc7acc4a3abdc33506fc-115011049805.png" width="87px" /> |
| kkworld | 快看漫画 | kkworld\_int | <Image alt="kkworld_logo.png" src="https://files.readme.io/23e353ba28fd55eeb0f326aa0035142d29f56abbaf402e836bf00f8191f4d055-115011112269.png" width="96px" /> |
| All Football Ads | 懂球帝广告平台 | allfootball\_int | <Image alt="allfootball_logo.png" src="https://files.readme.io/2522198caeaa17915b6b70c682b8cd772a9dd520f92b76f80d74176ff69c4fa9-115011049945.png" width="98px" /> |
| VoiceAds | 讯飞DSP | voiceads\_int | <Image alt="voiceads_logo.png" src="https://files.readme.io/7c9fdba5a283531bb430bb68e9955e6926697f43bd9b188063795ddca37903cd-115011049985.png" width="97px" /> |
| WiseMedia | 新数DSP | wisemedia\_int | ![wisemedia_logo.png](https://files.readme.io/4d1f177f2f18960f807072c5ac6c6f07c1473d8dae3b85dbdbc9963e8fb707d6-115011049845.png) |
| WPS | WPS办公软件 | wps\_int | ![wps_logo.png](https://files.readme.io/12a19f0ee8d8501be3c8d9c03a835ac320f1beeaec55aba9ff40dcb3da4060c4-115011049865.png) |
| MadhouseChina | 亿动传媒 | madhousechina\_int | ![madhouse_china_logo.png](https://files.readme.io/01b0831cfb73bc0c049c9ae70e34fdd2781871a1bebe40d62d63b346be1c6fbf-115011050025.png) |
| Weidong | 微动 | weidong\_int | <Image alt="weidong.png" src="https://files.readme.io/c355c3e4ae3a0b215ec5caa7a910164f5667bf7d34a308b0b77437540eb9ee56-360002013098.png" width="59px" /> |
| AdinAll | 聚告 | adinall\_int | <Image alt="adinall.logo.png" src="https://files.readme.io/29bceececa81b30a55204ea6ac7abe219737441ca4017e5f5944c53d55f3ecc8-360001976997.jpg" width="128px" /> |
| BlackDragon | 黑珑 | blackdragon\_int | <Image alt="blackdragon.logo.png" src="https://files.readme.io/2247dfaaa2ac63b1ddd09e37963188e3ca9315d0454a1f228f3113bb470a1406-360002076458.png" width="144px" /> |
| chenbai | 宸百 | chenbai\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chenbai.png?v=1" width="136px" /> |
| Dayumob | 智渠传媒 | dayumob\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dayumob.png?v=1" width="136px" /> |
| Idvert | 艾瓦特 | idvert\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/idvert.png?v=1" width="39px" /> |
| Jingmeng | 京盟世纪 | jingmeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jingmeng.png?v=1" width="144px" /> |
| Jusha | 巨鲨 | jusha\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jusha.png?v=1" width="78px" /> |
| Mailuo | 脉络时代 | mailuo\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mailuo.png?v=1" width="144px" /> |
| Manhuaren | 漫画人 | manhuaren\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/manhuaren.png?v=1" width="144px" /> |
| iFeng реклама | 凤凰凤羽客户平台 | ifeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ifeng.png?v=1" width="144px" /> |
| Qutoutiao реклама | 趣头条广告 | qutoutiao\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/qutoutiao.png?v=1" width="34px" /> |
| Поиск Shenma | 神马搜索 | smsearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/smsearch.png?v=1" width="81px" /> |
| Sogou Qidian реклама | 搜狗奇点系统 | sogouqidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sogouqidian.png?v=1" width="117px" /> |
| Sohu XinPinSuan реклама | 搜狐新品算 | sohuxps\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sohuxps.png?v=1" width="49px" /> |
| Tuia | 推啊 | tuia\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tuia.png?v=1" width="74px" /> |
| Yidian Zixun | 一点资讯 | yidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yidianzixun.png?v=1" width="94px" /> |
| Zhi Zi Yun | 智子云 | zhiziyun\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zhiziyun.png" width="137px" /> |
| Hesheng | 合声 | hesheng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hesheng.png?v=1" width="144px" /> |
| Zuo Ye Bang | 作业帮 | zuoyebang\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuoyebang.png?v=1" width="64px" /> |
| Chuniu | 初牛 | chuniu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chuniu.png?v=1" width="108px" /> |
| Zuiyou | 最右 | zuiyou\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuiyou.png" width="30px" /> |
| Himalaya Ads | 喜马拉雅广告平台 | ximalaya\_int | ![ximalaya.png](https://files.readme.io/51013f9759cf85994beeca24023c5e5c6c905ad98ba69648471578215b99b050-49929476570769.png) |
| Wifi Master Key Ads | WiFi万能钥匙广告平台 | wifimasterkey\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wifimasterkey.png" width="144px" /> |
| vivo реклама | Маркетинговая платформа vivo | vivoads\_int | ![vivo-logo.png](https://files.readme.io/fd5eea06d85e2b9993c0fcc961dacc9559d917aea1e78ad1c069546649a8eb86-360003580657.png) |
| ShiHuo реклама | Реклама | shihuo\_int | <Image alt="__logo.png" src="https://files.readme.io/d5ae526235128f06bcb986130b1e6ae2cb1f66e0d053760a0f6ad9565c5bbfc1-360004371338.png" width="120px" /> |
| OneSavour реклама | Реклама OneSavour | onesavour\_int | <Image alt="onesavour_logo.png" src="https://files.readme.io/e18db5eb6450c5cc1ddd8b5425808a502ee82790e330ccf5a42454cb6260835b-360004371358.png" width="120px" /> |
| Qianka | Qianka | qianka\_int | <Image alt="__.jpeg" src="https://files.readme.io/bd78e74e85eecdd7abf85be01b5bf0bb532941900fe42f6a2e9d9bf91219c5fe-360004682538.jpg" width="112px" /> |
| SMZDM | Что стоит купить | smzdm\_int | <Image alt="logo.png" src="https://files.readme.io/e347c2b397413ff905e5d05762f155b9876a135b0040d39dc347a814a5e7a873-49929476574225.png" width="108px" /> |
| MGTV | 芒果TV | mgtv\_int | <Image alt="250.png" src="https://files.readme.io/21eeb809bed57280ff010ca6a1088c4675a5c0f6817ac975fb538a10ad0cb47c-49929507363729.png" width="106px" /> |
| AdView Ads | Kuaiyou | adview\_int | <Image alt="adview_logo.png" src="https://files.readme.io/5b4dccebeb537b5f22747449361081bf2a41658c029ecd35cfc01e07d2cc3db9-49929476574609.png" width="108px" /> |
| XTrader | 灵集 | thextrader\_int | <Image alt="thextrader_logo.png" src="https://files.readme.io/f78627fc0a7c757cce3130bdab5c03ac6cf2e8e73659f6cb4c32208e53e7f82d-49929507364369.png" width="96px" /> |
| Dianrui | 点锐 | dianrui\_int | <Image alt="dianrui_logo.png" src="https://files.readme.io/3cf84a169f1491048397d377c439e92ffcb8658180281a13aa6997533c5bb9db-49929507364753.png" width="108px" /> |
| Samsung | 三星国内 | samsungcheilcn\_int | <Image alt="samsungcheilcn_logo.png" src="https://files.readme.io/d678815c206f2fcb35ea325be0aa8207650e26d04dc431491c047c535ba25ecb-49929476579089.png" width="104px" /> |
| Netease Music | NetEase Cloud Music | neteasemusic\_int | ![neteasemusic_logo.png](https://files.readme.io/cebb88912db6394ad3ba042d715dfd4482da5a37ea0dd338ce4a7e25a6d83016-49929476579473.png) |
| Yixia | 小咖秀（一下科技） | yixia\_int | ![yixia_logo.png](https://files.readme.io/e0bce43bc7e61e1e4b45bf8a81187917ce8f813248f8b45b2b13196f42af16c6-49929476580497.png) |
| Shenqi | 神奇互娱 | shenqi\_int | ![shenqi_logo.png](https://files.readme.io/fcfb801d2f0ad5cbf76b94a6b6980015d94b63f5c06ab2b89e617a69b1836d77-49929507366033.jpg) |
| Tangguo | 传诺（糖果广告） | tangguo\_int | — |
| Hotmobi | Hotmobi | hotmobi\_int | <Image alt="hotmobi_logo.png" src="https://files.readme.io/e671b7daf36745ef2aed9b419f3a98ef58c970d15ca2636d6ddfb2b910030762-49929507366161.png" width="120px" /> |
| Zplay | 掌游天下 | zplay\_int | <Image alt="zplay_logo.png" src="https://files.readme.io/9e6dd554f216868840d4bc1ad220d35154259497eec46f3e0b2e386a6920a6f9-49929507366417.png" width="120px" /> |
| Yumi Mobi | 玉米移动 | yumimobi\_int | <Image alt="yumimobi.png" src="https://files.readme.io/4b480b6e47505cbf56244ecfe8a1b61ba4da6707decad069eda3e6447c03c2f7-49929476581777.png" width="120px" /> |
| Lanpan | 蓝畔 | lanpan\_int | ![lanpan_.png](https://files.readme.io/d9572a456c09333e12164264e4f4d9ae3d74a6ba861497ecb38393d8e8037413-49929476582289.png) |
| Xinlan | 新蓝(新效科技） | xinlan\_int | <Image alt="xinlan.png" src="https://files.readme.io/5847293c5e4e83eca8ffe027d19d8d56b95229ae0f978ef18d533d7fb96f0b93-49929507366929.png" width="104px" /> |
| Youlan Ads | 幽蓝 | youlanad\_int | <Image alt="youlanad.png" src="https://files.readme.io/babca43bd2f9ca6c96dc1eb61092afd0b176d6a8a9bcb94f3aaafb0afeaff329-49929507367057.png" width="104px" /> |
| Реклама в Avazu | 艾维邑动 | avazu\_int | <Image alt="avazu.png" src="https://files.readme.io/3f33c13507855214e7fb62d526a219feddd91c82a6ef28a8f50212698b7bd392-49929507367185.png" width="81px" /> |
| Shangbang | 上榜（今日赚） | shangbang\_int | н/д |
| 51bizhi | 51壁纸 | 51bizhi\_int | ![51bizhi.png](https://files.readme.io/b268bdf946603b860f434f1dc382e5f3aabd9e4b83deeeb1f47a7f809a00c95a-49929476583697.jpg) |
| Chandashi | 禅大师 | chandashi | ![chandashi.png](https://files.readme.io/1f7d3efd680e30c0b60f8e70dac5d1f27a59d1bc4962e8067439b22723f5abcf-49929476585873.png) |
| Ann9 | 应用雷达 | ann9adnetwork\_int | ![ann9adnetwork.png](https://files.readme.io/5dde58d772c17eb72275399da79f927e7e235adccebe6f101e010e720688d294-49929507369233.png) |
| Gomo | 久邦数码 | gomo\_int | <Image alt="gomo.png" src="https://files.readme.io/64aeed688065a2a1469fc7b53fa206508f8398efcdb5260499bb5b2705bb3fa4-49929507369617.png" width="112px" /> |
| Vision Mobile | 掌上互动 | adzshd\_int | ![adzshd.png](https://files.readme.io/4796574f7bbdedbbae4eaf599c517dce7e467454a248c2358b4ccf568755698f-49929507369745.png) |
| Adjuz | 巨掌广告 | adjuz | <Image alt="adjuz.png" src="https://files.readme.io/cfb38f6b68101f214fae977d46db824f2df5565ce7aeb3e6793bdf44b59b3131-49929507369873.png" width="108px" /> |
| Guohe Ads | 果合广告 | guohe\_int | <Image alt="guohe.png" src="https://files.readme.io/fa925aea14a9d1052a0f56163c1a3ac512606086787b3457a18b27e437896f9d-49929476586641.png" width="99px" /> |
| Mintegral | Mintegral | mingtegral\_int | <Image alt="mintegral.png" src="https://files.readme.io/b7d110378c30268d84e1134f99ed43935f68916dfb5d30255ee4f2b53bee5046-49929507370129.png" width="105px" /> |
| Mobvista | Mobvista | mobvista\_int | <Image alt="mobvista.png" src="https://files.readme.io/64ba25ad73353c508106a5343dd88d7275eafb9ab48482a72cc329a7cb741ff9-49929476587921.png" width="114px" /> |
| Emar | 亿玛 | yima\_int | <Image alt="yima.png" src="https://files.readme.io/c79dc442423943f0e0aba77f461c7ea0d412745adf589f4e98f5613a8e6fb900-49929507371921.png" width="116px" /> |
| Centrixlink | 隐逸数字 | centrixlink\_int | <Image alt="centrixlink.png" src="https://files.readme.io/c80f9820fa3e8c9d739837b5a5bcc069254ae12bdb97d6890ed092e6d80aec20-49929476588689.png" width="88px" /> |
| Codrim | 氪金 | codrim\_int | <Image alt="codrim.png" src="https://files.readme.io/62db4a4652e382ca130b32cbe4e359be13198efda515655d6de685c648e7dddf-49929476588945.jpg" width="100px" /> |
| lbadvisor | 量江湖（比邻弘科） | lbadvisor | <Image alt="lbadvisor.png" src="https://files.readme.io/12b524c69d7ac37d7ab6efeb041388e49115e4edb1dc972d83bc42dc530a165a-49929507373329.png" width="88px" /> |
| ADYOYU | 涌玉 | yoyuad\_int | <Image alt="yoyuad.png" src="https://files.readme.io/83bcf55412e218167c8276450f20b7ea697b62f470631bdff583c0a059a24ba0-49929476589585.png" width="51px" /> |
| KUAIZI | 筷子科技 | kuaizi\_int | <Image alt="kuaizi.png" src="https://files.readme.io/ad7df253a7365bc85f8cd07427070a6385fa47f3252bd420109c878091cc8981-49929476589841.png" width="96px" /> |
| Yeahmobi | 易点天下 | yeahmobi\_int | <Image alt="yeahmobi.png" src="https://files.readme.io/cecb0354d318cd1954fd17eeb13c36a277ac26c9a5bf74e4e8fc04bebb180bd3-49929507374097.png" width="97px" /> |
| HUYA | 虎牙直播 | huya\_int | <Image alt="____LOGO.png" src="https://files.readme.io/c32e2f9e23a3a5a44a499428634132a99b01bf33f55d736488ab304b7f28ba0c-49929476590225.png" width="93px" /> |
| MJweather | 墨迹天气 | mjweather\_int | <Image alt="200-50.jpg" src="https://files.readme.io/b0df0bc14313a811f81e5447bb339cac4defa1c9c1f2be328732768b5c5831da-49929507374609.jpg" width="100px" /> |
| Codoon | 咕咚 | codoon\_int | <Image alt="__logo.png" src="https://files.readme.io/1295a7a31bc6ddf65955ebdcd0f7046ee033f8a1df6dbb45de5df5d97b261b47-49929507375121.png" width="112px" /> |
| LongXi DSP | 珑玺DSP | lxdsp\_int | <Image alt="lxdsp_int.png" src="https://files.readme.io/47f511ffdffc686b22ec2a0b91cf789b12bc69ffb2d6c60966f3c4be839ee4ce-49929507375377.png" width="112px" /> |

<div data-zendesk-anchors="android-apps-in-china=android-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BA%D0%B8%D1%82%D0%B0%D0%B5 selecting-an-identifier=%D0%B2%D1%8B%D0%B1%D0%BE%D1%80-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0 attribution-solutions-for-the-chinese-market=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BD%D0%B0-%D0%BA%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%BE%D0%BC-%D1%80%D1%8B%D0%BD%D0%BA%D0%B5 integrated-media-sources=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B8" />
