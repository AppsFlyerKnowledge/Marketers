---
title: Promoción de aplicaciones Android en China
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
  edited_at: '2026-08-12T12:18:32Z'
  id: 115004639203
  locale: es
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/es/articles/115004639203
---
> **De un vistazo:** mejores prácticas para promocionar tu aplicación Android en el mercado chino.

## Aplicaciones Android en China

Considera las siguientes secciones como una lista de comprobación de elementos que debes tener en cuenta si comercializas tu aplicación en China.

### Selección de un identificador

Para lograr una atribución precisa, se requiere un identificador único (ID) que represente al usuario. En los dispositivos donde los servicios de Google Play (GPS) están activos, históricamente este ha sido el ID de publicidad de Google (GAID).

Actualmente, el GPS no está disponible en los dispositivos comercializados en China. Los propietarios de aplicaciones deben usar un ID alternativo basado en el hardware del dispositivo, como el IMEI y el ID de Android.

A partir de [Android 10 (nivel de API  level 29)](https://developer.android.com/training/articles/user-data-ids), lanzado a finales de 2019,  el acceso al IMEI y al ID de Android está restringido. Como consecuencia, no se podrá acceder al IMEI/ID de Android en los dispositivos más nuevos.

Para solucionar esto, existe una alternativa al GAID: el OAID. El OAID (disponible desde finales de 2019) está siendo promovido por fabricantes chinos de dispositivos, por ejemplo, [Huawei](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3030304).

Consulta <Anchor target="_blank" href="/marketers/es/docs/measure-attribution-in-the-chinese-domestic-market">la integración del SDK de AppsFlyer para Android</Anchor>. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

### Soluciones de atribución para el mercado chino

Dado que hay varias tiendas de aplicaciones Android que prestan servicio al mercado chino, AppsFlyer ofrece las soluciones descritas aquí para atribuir instalaciones de Android.

Los usuarios de dispositivos Android en China descargan aplicaciones desde distintas tiendas de aplicaciones Android chinas en lugar de Google Play, y la mayoría de estas tiendas de aplicaciones ofrecen unidades de anuncios para anunciantes de aplicaciones. Entre estas tiendas de aplicaciones, las principales son Tencent MyApp, 360 App Store, Baidu App Store, Xiaomi App Store, OPPO App Store y Huawei App Store.

Por ejemplo, si quieres promocionar tu aplicación Android a través de Tencent Social Ads, Tencent Tui Ads y Wechat Ads, sube la aplicación Android a MyApp (la tienda de aplicaciones Android de Tencent), que al mismo tiempo te aporta instalaciones orgánicas. Las redes publicitarias de la serie de Baidu, 360 Ads, Xiaomi Ads y OPPO Ads funcionan de forma similar.

[![](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)

Mientras tanto, muchas instalaciones de Android se generan a partir de enlaces de descarga de APK en páginas web móviles o en espacios publicitarios in-app.

AppsFlyer ofrece tres soluciones principales para atribuir instalaciones de aplicaciones Android en el mercado chino; usa el método que mejor se adapte a tus necesidades.

<div id="local-android-app-store-that-supports-ad-attribution" />

<Accordion title="Tienda de aplicaciones Android local compatible con la atribución de anuncios">

**Solución:** App Android fuera de la tienda con enlace de atribución

**Descripción:** The well-known Chinese Internet companies or mobile device manufacturers have created their own Android App Stores and Ad Platforms/Ad Networks, taking advantage of their huge traffic resources in China's domestic market. Sin embargo, estas grandes empresas controlan estrictamente el tráfico para comprobar si el usuario que hizo clic en su anuncio descarga la aplicación desde la tienda de aplicaciones de otra empresa. En estas situaciones, tienes que generar una App fuera de la tienda única para cada tienda de aplicaciones de Android. Mientras tanto, puedes usar el enlace de atribución de AppsFlyer para registrar el rendimiento de las campañas publicitarias creadas en las propias plataformas publicitarias/ad networks de esas empresas.

Con este método, puedes atribuir tanto instalaciones orgánicas como instalaciones no orgánicas. Al mismo tiempo, puedes optimizar las campañas publicitarias en términos de unidades de anuncio, conjuntos de anuncios y creativos, etc.

**Ejemplo:** Si quieres promocionar tu aplicación de Android a través de Tencent Social Ads, Tencent Tui Ads y Wechat Ads, debes subir la aplicación de Android a Tencent Android App Store y MyApp, etc., lo que te aporta instalaciones orgánicas al mismo tiempo. Las series de ad networks de Baidu, 360 Ads, Xiaomi Ads y OPPO Ads funcionan todas de la misma manera.

**Preparación:** Para saber cómo atribuir aplicaciones fuera de la tienda, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">aquí</Anchor>.

</Accordion>

<div id="ad-network" />

<Accordion title="Red publicitaria">

**Solución:** Enlace de descarga del APK / APK + enlace de atribución

**Descripción:** Para promocionar aplicaciones de Android en ad networks que no tienen un requisito obligatorio sobre dónde descargar la aplicación, puedes proporcionar simplemente un enlace de descarga del APK o un APK y el enlace de atribución de AppsFlyer a la fuente de medios.

Es fácil y rápido lanzar campañas publicitarias. También es práctico consultar la performance de distintas fuentes de medios en la misma página de resumen de la aplicación.

**Ejemplo:** Bytedance Ads (Toutiao), Sina Weibo, iQiyi

**Preparación:** Configura una aplicación de Android fuera de la tienda y genera distintos enlaces de atribución para diferentes ad networks. Para saber cómo atribuir aplicaciones fuera de la tienda, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">aquí</Anchor>.

</Accordion>

<div id="android-app-store-that-does-not-support-ad-attribution" />

<Accordion title="Tienda de aplicaciones de Android que no admite la atribución de anuncios">

**Solución:** App fuera de la tienda de Android

**Descripción:**  Para las tiendas de aplicaciones de Android que no admiten la atribución de anuncios, todavía puedes usar Apps fuera de la tienda para atribuir todas las instalaciones procedentes de esta tienda de aplicaciones, solo que todas las instalaciones se atribuyen como instalaciones orgánicas.

**Ejemplo:** tienda de aplicaciones de Lenovo, tienda de aplicaciones de Huawei.

**Preparación:** para saber cómo atribuir aplicaciones fuera de la tienda, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">aquí</Anchor>.

</Accordion>

Si estás promocionando tus Apps con más de una de las soluciones mencionadas anteriormente y quieres consultar los datos de todas tus campañas de China en la misma vista del dashboard, puedes usar <Anchor target="_blank" href="/marketers/es/docs/custom-dashboards">Custom Dashboard</Anchor>.

## Fuentes de medios integradas

<Anchor target="_blank" href="/marketers/es/docs/china-domestic-market-ad-network-configuration">Guías de configuración</Anchor>

Fuentes de medios integradas en China:

| Nombre de fuente de medios | Nombre en chino | PID no integrados. | Logotipo |
| --- | --- | --- | --- |
| Anuncios de Tencent | Anuncios de Tencent | tencent\_int | ![ac1.png](https://files.readme.io/68f25ee4e8656ca36ea7ca48b2de7278f709fd93cb06f0db57b31afd27a65c57-115015067906.png) |
| <Anchor target="_blank" href="/marketers/es/docs/bytedance-ads-china-campaign-configuration">Anuncios de ByteDance</Anchor> | Motor Gigante（Toutiao） | bytedance\_int | ![ac2.png](https://files.readme.io/cf43a8ae5a29032e86317f11a4af2beb60dfa8ac986a12f57fac6ddc0b7ae9ae-115015067926.png) |
| <Anchor target="_blank" href="/marketers/es/docs/wechat-ads-campaign-configuration">Anuncios de WeChat</Anchor> | Plataforma pública de WeChat | wechat\_int | ![ac4.png](https://files.readme.io/a1050b99def37cd07093dfebf34cee86f0d71ccb9cc407e5ebe87c3ea594a39b-115015067966.png) |
| <Anchor target="_blank" href="/marketers/es/docs/sina-weibo-ads-campaign-configuration">Anuncios de Weibo</Anchor> | Super Fan Tong de Weibo | sinaweibo\_int | ![ac5.png](https://files.readme.io/6902d459e199231a44deb9d64de0cf3ee8fe96d28e246e0506bbb275a8e225d5-115015247263.png) |
| Anuncios de Sina Fuyi | Sina Fuyi | sinafuyi\_int | ![sinafuyi.logo.png](https://files.readme.io/e3b19f22bbb8ccd9aba37ac1d7f8222f8c90d6510622a59a80d2acf73d1f5dab-360001660797.png) |
| <Anchor target="_blank" href="/marketers/es/docs/baidu-app-ads-campaign-configuration">Anuncios de la app de Baidu</Anchor> | Baidu Baitong | baitong\_int | ![ac6.png](https://files.readme.io/3055bb4a6865304d3117b714d364f84f233a25372ae251fefb07cbd5681bd27e-115015067986.png) |
| <Anchor target="_blank" href="/marketers/es/docs/baidu-mdsp-ads-baiyi-campaign-configuration">Baidu mDSP</Anchor> | Baidu Baiyi | baidumdsp\_int | ![ac7.png](https://files.readme.io/f610964f7895989f3535f9b389fd0c7218b1c44e68a7ba9c539fc0d0a1ee825a-115015068006.png) |
| Anuncios de búsqueda de Baidu | Anuncios de búsqueda de Baidu | baidusearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidusearch.png" width="112px" /> |
| Publicidad nativa de Baidu | Publicidad nativa de Baidu | baidufeedads\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| Publicidad nativa de Baidu 2.0 | Publicidad nativa de Baidu 2.0 | baiduxinxiliu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/xiaomi-ads-network-campaign-configuration">Anuncios de Xiaomi & tienda de aplicaciones</Anchor> | Plataforma de marketing de Xiaomi & tienda de aplicaciones | xiaomichina\_int | <Image alt="ac8.png" src="https://files.readme.io/4976cf0391214984b4bbce7ad66f9df71c72a5eef3c74414d77ad1fe569c19ff-115015068026.png" width="37px" /> |
| Huawei AppGallery en China | Tienda de aplicaciones de Huawei | huaweiappgallerychina\_int | <Image alt="huawei_app_store_logo.png" src="https://files.readme.io/29f84e8d0e90fc5bb85fc86810a45810fd0bc5fea58869c124b8f66354b67c78-10801903185809.png" width="40px" /> |
| Tienda de aplicaciones de OPPO en China | Tienda de software de OPPO | oppostorechina\_int | ![oppo_store_logo.png](https://files.readme.io/30bdc4b4613f423f028eea5adfc6eee714805db65b857c49d6221639f19b3523-10801961659153.png) |
| vivo Anuncios & Tienda de aplicaciones | vivo plataforma de marketing&tienda de aplicaciones | vivoads\_int | <Image alt="vivo_store_logo.png" src="https://files.readme.io/5b3b87a0d4a6c424421d9d1b156cf0b1d81da7b534a53e760227de2726db8445-10802004853009.png" width="41px" /> |
| 360 Anuncios | Plataforma de performance Dianjing 360 | 360\_int | ![ac9.png](https://files.readme.io/b2a47bc04124313c237898040c72ee5eee2e86754333eea35f7b35c4ac0bd7f1-115015068046.png) |
| Anuncios de Ali UC | Ali Huichuan （UC Toutiao） | uctoutiao\_int | ![ac10.png](https://files.readme.io/5a40ba07cd5b23b898849bf1ef6689704de0e4773c354ed52f455ef6418fdd61-115015068086.png) |
| Anuncios de Netease | Netease Yixiao | netease\_int | ![ac11.png](https://files.readme.io/6572ef63727ca2aa95cdf747804ec9b061e744e130dd0285ccda84bd0fdd5820-115015068106.png) |
| iQIYI Anuncios | iQIYI Qilin Shensuan | iqiyi\_int | ![ac12.png](https://files.readme.io/7a3eab06d7e7bd598e750e69ea72c2a127322dbe343c889b025803ca766a5d85-115015247303.png) |
| Anuncios de MOMO | Anuncios de MOMO | momo\_int | ![ac13.png](https://files.readme.io/17478fe1e70278da1ee55522fe0132a7a42e11c36a4b86ebb5fde14a17d9abb2-115015247323.png) |
| YouKu DSP | 阿里妈妈（睿视优酷DSP系统） | youkudsp\_int | <Image alt="ac14.png" src="https://files.readme.io/2aabab6dc35278c15dd687cfb0ae3dee71c372226265b0606b6381ea7d90a8da-115015247343.png" width="98px" /> |
| Kuaishou | Plataforma de gestión publicitaria de Kuaishou | kuaishou\_int | ![ac15.png](https://files.readme.io/801097b7fb9ce7020cddde8db46093fb39ad55a01b4ae282f5ffc44e591c5bd4-115015068126.png) |
| douyu.TV | 斗鱼TV | douyu\_int | ![ac16.png](https://files.readme.io/7ab338fd14e1b35c3eb5c20184a451516a05f98a3fcf605d9a04ccec546105e1-115015247363.png) |
| Anuncios de Bilibili | Plataforma publicitaria de Bilibili | bilibili\_int | ![bilibili.logo.png](https://files.readme.io/f2b2cd2378d48beb8770a89694e441a5bb1dd00b30b1eac540df7f306878b594-360001660817.png) |
| Youdao DSP | Youdao Zhixuan | youdaodsp\_int | ![youdaozhixuan.logo.png](https://files.readme.io/9c9c9fc6b2226e666829373beef151a65ec38393a496bd3563a8649438d4331d-360001660837.png) |
| Anuncios de Meitu China | Plataforma publicitaria de Meitu | meituchina\_int | ![meitu.logo.png](https://files.readme.io/0bc4911d6a5455207e31d1f1a00d7af54c0f3a93167dbfabb33cdd96bb430c2f-360001660857.png) |
| Anuncios de Meiyou | 美柚广告 女人通 | meiyou\_int | ![meiyou.logo.png](https://files.readme.io/413aae7d93717526cfdad51afac4097f22e0c826c79a44d14326f65b1805b6a2-360001660877.png) |
| Oppo | Oppo | oppo\_int | <Image alt="ac17.png" src="https://files.readme.io/6a6aeb9b3675eb5f28b29a47c5fb454c3f5f8fc4c49c856ceccc4e0922c45200-115015247383.png" width="131px" /> |
| Yunshu | 云数（百思不得姐） | yunshu\_int | ![ac18.png](https://files.readme.io/09e91278b253f5c7dcd7c681a52a960b346b0665d20084bb64afb7bf2c94e5ba-115015247403.png) |
| Juego TapTap | TapTap | taptapgame\_int | ![ac19.png](https://files.readme.io/536f59f036f7c4f027308dbd25c6d04db8748c070fd6e2fbbb3816d13cbfa577-115015068146.png) |
| Ipinyou | 品友 | ipinyou\_int | ![ac20.png](https://files.readme.io/54121bb0a388c6e238749ae6166e30fafcd251a94518abaa0e5de02005f078f3-115015068166.png) |
| Hupu | 虎扑 | hupu\_int | ![ac22.png](https://files.readme.io/a463753277f62ef989271ce9433940f02cbbf7a9e11b6dd675c1b81f8207223c-115015068226.png) |
| Chance | 畅思 | chance\_int | ![ac23.png](https://files.readme.io/7dbac1e40c129085b9be9e24937e0e22b0ff16d5bc2e2b75da3a7b83e8f90acd-115015068246.png) |
| Domob China | 多盟 | domobc\_int | ![ac24.png](https://files.readme.io/0a01e63ce107e0fb23602ff13b6f76d05b4f1464dc82016ef4bcfc17fe9c291e-115015247423.png) |
| Adwo | 安沃 | adwo\_int | ![ac26.png](https://files.readme.io/1fa607feffbf2adfc5905c607f45960585f24cf58dd63d434ffa5ba2a1760923-115015068266.png) |
| Youmi | 有米 | youmi\_int | ![ac28.png](https://files.readme.io/d8eeaa83743d8fbb5dc2ee27cf5426ccd81ee7304d3e1cdd3e8f7e113f3b99fc-115015247483.png) |
| Behe | 璧合 | behe\_int | ![ac29.png](https://files.readme.io/653b4e503246e97f7b11a8886737d265d1cd200bf3233d70b5915a0539a5bbe5-115015068286.png) |
| biddingx | 舜飞 | biddingx\_int | <Image alt="biddingx_logo.png" src="https://files.readme.io/20035c58ff95b7f5699e4fd5533c0a542b24382bbeeefdfbc89738091d4f61fd-115011112389.png" width="114px" /> |
| Anuncios de Auto Home | 汽车之家广告平台 | autohome\_int | <Image alt="autohome_logo.png" src="https://files.readme.io/520e07ee6f027dbfd0ce8fde3d7b2e11093e38bd5aaa58a2f91dd4d489376b16-115011049905.png" width="104px" /> |
| <Anchor target="_blank" href="/marketers/es/docs/zhihu-ads-campaign-configuration">Anuncios de Zhihu</Anchor> | 知乎营销平台 | zhihu\_int | <Image alt="zhihu_logo.png" src="https://files.readme.io/049b99c1deae5f494ce426a899f6689521d2b9a531bb0caa2e0d1745e14f5809-115011049925.png" width="87px" /> |
| kkworld | 快看漫画 | kkworld\_int | <Image alt="kkworld_logo.png" src="https://files.readme.io/c7e6f1fc339750a2bb61fc01a54df81d236e9bdb3e99255051ae2f812d5b225f-115011112409.png" width="96px" /> |
| Todos los anuncios de fútbol | 懂球帝广告平台 | allfootball\_int | <Image alt="allfootball_logo.png" src="https://files.readme.io/2522198caeaa17915b6b70c682b8cd772a9dd520f92b76f80d74176ff69c4fa9-115011049945.png" width="98px" /> |
| VoiceAds | 讯飞DSP | voiceads\_int | <Image alt="voiceads_logo.png" src="https://files.readme.io/7c9fdba5a283531bb430bb68e9955e6926697f43bd9b188063795ddca37903cd-115011049985.png" width="97px" /> |
| WiseMedia | 新数DSP | wisemedia\_int | ![wisemedia_logo.png](https://files.readme.io/e0aab2a9b2d989b936c8df207ccd860a008d6c5015ef8c4ad154e254f7b09105-115011050005.png) |
| WPS | WPS办公软件 | wps\_int | ![wps_logo.png](https://files.readme.io/8f85e6f569a29612b85f468a8e91e42e8bf654eac12f4f4b9be42dea02babd1c-115011112429.png) |
| MadhouseChina | 亿动传媒 | madhousechina\_int | ![madhouse_china_logo.png](https://files.readme.io/01b0831cfb73bc0c049c9ae70e34fdd2781871a1bebe40d62d63b346be1c6fbf-115011050025.png) |
| Weidong | Weidong | weidong\_int | <Image alt="weidong.png" src="https://files.readme.io/c355c3e4ae3a0b215ec5caa7a910164f5667bf7d34a308b0b77437540eb9ee56-360002013098.png" width="59px" /> |
| AdinAll | Jugao | adinall\_int | <Image alt="adinall.logo.png" src="https://files.readme.io/29bceececa81b30a55204ea6ac7abe219737441ca4017e5f5944c53d55f3ecc8-360001976997.jpg" width="128px" /> |
| BlackDragon | Heilong | blackdragon\_int | <Image alt="blackdragon.logo.png" src="https://files.readme.io/2247dfaaa2ac63b1ddd09e37963188e3ca9315d0454a1f228f3113bb470a1406-360002076458.png" width="144px" /> |
| chenbai | Chenbai | chenbai\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chenbai.png?v=1" width="136px" /> |
| Dayumob | Zhiqu Media | dayumob\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dayumob.png?v=1" width="136px" /> |
| Idvert | Aiwate | idvert\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/idvert.png?v=1" width="39px" /> |
| Jingmeng | Jingmeng Century | jingmeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jingmeng.png?v=1" width="144px" /> |
| Jusha | Jusha | jusha\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jusha.png?v=1" width="78px" /> |
| Mailuo | 脉络时代 | mailuo\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mailuo.png?v=1" width="144px" /> |
| Manhuaren | 漫画人 | manhuaren\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/manhuaren.png?v=1" width="144px" /> |
| iFeng anuncios | 凤凰凤羽客户平台 | ifeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ifeng.png?v=1" width="144px" /> |
| Qutoutiao anuncios | 趣头条广告 | qutoutiao\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/qutoutiao.png?v=1" width="34px" /> |
| Búsqueda de Shenma | 神马搜索 | smsearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/smsearch.png?v=1" width="81px" /> |
| Sogou Qidian anuncios | 搜狗奇点系统 | sogouqidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sogouqidian.png?v=1" width="117px" /> |
| Sohu XinPinSuan anuncios | 搜狐新品算 | sohuxps\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sohuxps.png?v=1" width="49px" /> |
| Tuia | 推啊 | tuia\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tuia.png?v=1" width="74px" /> |
| Yidian Zixun | 一点资讯 | yidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yidianzixun.png?v=1" width="94px" /> |
| Zhi Zi Yun | 智子云 | zhiziyun\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zhiziyun.png" width="137px" /> |
| Hesheng | 合声 | hesheng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hesheng.png?v=1" width="144px" /> |
| Zuo Ye Bang | 作业帮 | zuoyebang\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuoyebang.png?v=1" width="64px" /> |
| Chuniu | 初牛 | chuniu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chuniu.png?v=1" width="108px" /> |
| Zuiyou | 最右 | zuiyou\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuiyou.png" width="30px" /> |
| Himalaya Ads | 喜马拉雅广告平台 | ximalaya\_int | ![ximalaya.png](https://files.readme.io/0518181234e0529c973f676bb69fcdfe31d4d3acf7551e833c980aa179746832-24508112332177.png) |
| Wifi Master Key Ads | WiFi万能钥匙广告平台 | wifimasterkey\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wifimasterkey.png" width="144px" /> |
| vivo anuncios | Plataforma de marketing de vivo | vivoads\_int | <Image alt="vivo-logo.png" src="https://files.readme.io/fd5eea06d85e2b9993c0fcc961dacc9559d917aea1e78ad1c069546649a8eb86-360003580657.png" width="144px" /> |
| ShiHuo anuncios | Publicidad de ShiHuo | shihuo\_int | <Image alt="__logo.png" src="https://files.readme.io/d5ae526235128f06bcb986130b1e6ae2cb1f66e0d053760a0f6ad9565c5bbfc1-360004371338.png" width="120px" /> |
| OneSavour anuncios | Publicidad de OneSavour | onesavour\_int | <Image alt="onesavour_logo.png" src="https://files.readme.io/e18db5eb6450c5cc1ddd8b5425808a502ee82790e330ccf5a42454cb6260835b-360004371358.png" width="120px" /> |
| Qianka | Qianka | qianka\_int | <Image alt="__.jpeg" src="https://files.readme.io/bd78e74e85eecdd7abf85be01b5bf0bb532941900fe42f6a2e9d9bf91219c5fe-360004682538.jpg" width="112px" /> |
| SMZDM | SMZDM | smzdm\_int | <Image alt="logo.png" src="https://files.readme.io/9b60b9dfafcd03fb7a9573c7588ad04c561c640c8e20fa25480411339d1329ef-24508112360977.png" width="108px" /> |
| MGTV | MangoTV | mgtv\_int | <Image alt="250.png" src="https://files.readme.io/fe9785b8eaea45cd4bcaf383c692ec5676dec7881f3c48a48cc30a561cb55e19-24508112366609.png" width="106px" /> |
| AdView anuncios | Kuaiyou | adview\_int | <Image alt="adview_logo.png" src="https://support.appsflyer.com/hc/article_attachments/24508128427537" width="108px" /> |
| XTrader | Lingji | thextrader\_int | <Image alt="thextrader_logo.png" src="https://files.readme.io/4ed9e29cd48d0afff7690aceae4caf7b2404b0ca0b30095a27d4cb98386149b7-24508112379665.png" width="96px" /> |
| Dianrui | Dianrui | dianrui\_int | <Image alt="dianrui_logo.png" src="https://support.appsflyer.com/hc/article_attachments/24508128447761" width="108px" /> |
| Samsung | Samsung nacional | samsungcheilcn\_int | <Image alt="samsungcheilcn_logo.png" src="https://files.readme.io/65dd1c741e709d32eed929fd6e2d6c0fa49d8eadcb5d40b808a13dbd633bf21d-24508112409489.png" width="104px" /> |
| Netease Music | Música en la nube de NetEase | neteasemusic\_int | ![neteasemusic_logo.png](https://files.readme.io/1c0c44266cc436f12830533a3d2c0baf31fb75ea1d45f619c8483be1fdfa45d3-24508112434321.png) |
| Yixia | Xiaokaxiu（Tecnología Yixia） | yixia\_int | ![yixia_logo.png](https://files.readme.io/6b8da43a2ca3f60203bfb11fec0f033dc826b0f0cdee79022f7d528d699819ce-24508112464401.png) |
| Shenqi | Shenqi Huyu | shenqi\_int | ![shenqi_logo.png](https://support.appsflyer.com/hc/article_attachments/24508128524817) |
| Tangguo | Chuannuo（Anuncios Tangguo） | tangguo\_int | n/a |
| Hotmobi | Hotmobi | hotmobi\_int | <Image alt="hotmobi_logo.png" src="https://files.readme.io/ed50450f617a051d6691c7871e523f4846e949107e4b45d31b72b2be7608365d-24508112495633.png" width="120px" /> |
| Zplay | 掌游天下 | zplay\_int | <Image alt="zplay_logo.png" src="https://support.appsflyer.com/hc/article_attachments/24508128544017" width="120px" /> |
| Yumi Mobi | 玉米移动 | yumimobi\_int | <Image alt="yumimobi.png" src="https://support.appsflyer.com/hc/article_attachments/24508128550289" width="120px" /> |
| Lanpan | 蓝畔 | lanpan\_int | ![lanpan_.png](https://files.readme.io/2cef730097baf95c14bfc07879c0d6b138531cf94f5feef840549aef68656bba-24508112528657.png) |
| Xinlan | 新蓝(新效科技） | xinlan\_int | <Image alt="xinlan.png" src="https://support.appsflyer.com/hc/article_attachments/24508112535185" width="104px" /> |
| Youlan Anuncios | 幽蓝 | youlanad\_int | <Image alt="youlanad.png" src="https://support.appsflyer.com/hc/article_attachments/24508128585361" width="104px" /> |
| Anuncios de Avazu | 艾维邑动 | avazu\_int | <Image alt="avazu.png" src="https://support.appsflyer.com/hc/article_attachments/24508128591377" width="81px" /> |
| Shangbang | 上榜（今日赚） | shangbang\_int | n/d |
| 51bizhi | 51壁纸 | 51bizhi\_int | ![51bizhi.png](https://support.appsflyer.com/hc/article_attachments/24508128598289) |
| Chandashi | 禅大师 | chandashi | ![chandashi.png](https://support.appsflyer.com/hc/article_attachments/24508128611857) |
| Ann9 | 应用雷达 | ann9adnetwork\_int | ![ann9adnetwork.png](https://support.appsflyer.com/hc/article_attachments/24508112580497) |
| Gomo | 久邦数码 | gomo\_int | <Image alt="gomo.png" src="https://support.appsflyer.com/hc/article_attachments/24508112590737" width="112px" /> |
| Vision Móvil | Interacción en la palma de la mano | adzshd\_int | ![adzshd.png](https://support.appsflyer.com/hc/article_attachments/24508112592145) |
| Adjuz | Publicidad en la palma de la mano | adjuz | <Image alt="adjuz.png" src="https://support.appsflyer.com/hc/article_attachments/24508112596113" width="108px" /> |
| Guohe Ads | Publicidad de Guohe | guohe\_int | <Image alt="guohe.png" src="https://support.appsflyer.com/hc/article_attachments/24508112598801" width="99px" /> |
| Mintegral | Mintegral | mingtegral\_int | <Image alt="mintegral.png" src="https://support.appsflyer.com/hc/article_attachments/24508112601361" width="105px" /> |
| Mobvista | Mobvista | mobvista\_int | <Image alt="mobvista.png" src="https://support.appsflyer.com/hc/article_attachments/24508112602513" width="114px" /> |
| Emar | Yima | yima\_int | <Image alt="yima.png" src="https://support.appsflyer.com/hc/article_attachments/24508112606353" width="116px" /> |
| Centrixlink | Yinyi Digital | centrixlink\_int | <Image alt="centrixlink.png" src="https://support.appsflyer.com/hc/article_attachments/24508112615825" width="88px" /> |
| Codrim | Gasto en compras dentro de la aplicación | codrim\_int | <Image alt="codrim.png" src="https://support.appsflyer.com/hc/article_attachments/24508112619153" width="100px" /> |
| lbadvisor | 量江湖（比邻弘科） | lbadvisor | <Image alt="lbadvisor.png" src="https://support.appsflyer.com/hc/article_attachments/24508128662417" width="88px" /> |
| ADYOYU | Yongyu | yoyuad\_int | <Image alt="yoyuad.png" src="https://support.appsflyer.com/hc/article_attachments/24508128664337" width="51px" /> |
| KUAIZI | Kuaizi Technology | kuaizi\_int | <Image alt="kuaizi.png" src="https://support.appsflyer.com/hc/article_attachments/24508112632209" width="96px" /> |
| Yeahmobi | Yeahmobi | yeahmobi\_int | <Image alt="yeahmobi.png" src="https://support.appsflyer.com/hc/article_attachments/24508112635281" width="97px" /> |
| HUYA | HUYA Live | huya\_int | <Image alt="____LOGO.png" src="https://support.appsflyer.com/hc/article_attachments/24508128693521" width="93px" /> |
| MJweather | Moji Weather | mjweather\_int | <Image alt="200-50.jpg" src="https://support.appsflyer.com/hc/article_attachments/24508112654993" width="100px" /> |
| Codoon | 咕咚 | codoon\_int | <Image alt="__logo.png" src="https://support.appsflyer.com/hc/article_attachments/24508128712081" width="112px" /> |
| LongXi DSP | 珑玺DSP | lxdsp\_int | <Image alt="lxdsp_int.png" src="https://support.appsflyer.com/hc/article_attachments/24508112669969" width="112px" /> |

<div data-zendesk-anchors="android-apps-in-china=aplicaciones-android-en-china selecting-an-identifier=selecci%C3%B3n-de-un-identificador attribution-solutions-for-the-chinese-market=soluciones-de-atribuci%C3%B3n-para-el-mercado-chino integrated-media-sources=fuentes-de-medios-integradas" />
