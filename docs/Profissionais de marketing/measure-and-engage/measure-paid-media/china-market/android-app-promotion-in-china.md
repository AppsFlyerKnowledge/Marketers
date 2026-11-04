---
title: Promoção de aplicativo Android na China
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
  edited_at: '2026-08-19T00:28:10Z'
  id: 115004639203
  locale: pt
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/pt/articles/115004639203
---
> **Resumo:** Melhores práticas para promover seu aplicativo Android no mercado chinês.

<div id="android-apps-in-china" />

## Aplicativos Android na China

Considere as seções a seguir como uma lista de verificação dos itens que você deve avaliar ao divulgar seu aplicativo na China.

<div id="selecting-an-identifier" />

### Seleção de um identificador

Para obter atribuição precisa, é necessário um identificador exclusivo (ID) que represente o usuário. Em dispositivos em que os serviços do Google Play (GPS) estão ativos, historicamente esse identificador tem sido o Google Advertising ID (GAID).

Atualmente, o GPS não está disponível em dispositivos comercializados na China. Os proprietários de aplicativos precisam usar IDs alternativos com base no hardware do dispositivo, como o IMEI e o Android ID.

A partir do [Android 10 (nível da API  level 29)](https://developer.android.com/training/articles/user-data-ids), lançado no final de 2019,  o acesso ao IMEI e ao Android ID é restrito. O efeito disso é que o IMEI/Android ID não ficará acessível em dispositivos mais novos.

Para contornar isso, uma alternativa ao GAID é o OAID. O OAID (disponível desde o final de 2019) está sendo promovido por fabricantes chineses de dispositivos, como a [Huawei](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3030304).

Consulte <Anchor target="_blank" href="/marketers/pt/docs/measure-attribution-in-the-chinese-domestic-market">Integração do SDK da AppsFlyer - Android</Anchor>.Etapa 1:

<div id="attribution-solutions-for-the-chinese-market" />

### Soluções de atribuição para o mercado chinês

Como há várias lojas de aplicativos Android que atendem ao mercado chinês, a AppsFlyer oferece as soluções descritas aqui para atribuir instalações de aplicativos Android.

Usuários de dispositivos Android na China baixam aplicativos de diferentes lojas de aplicativos Android chinesas em vez do Google Play, e a maioria dessas lojas de aplicativos oferece espaços de anúncios para anunciantes de aplicativos. Entre essas lojas de aplicativos, as principais são Tencent MyApp, 360 App Store, Baidu App Store, Xiaomi App Store, OPPO App Store e Huawei App Store.

Por exemplo, se você quiser promover seu aplicativo Android por meio de Tencent Social Ads, Tencent Tui Ads e Wechat Ads, envie o aplicativo Android para o MyApp (loja de aplicativos Android da Tencent), o que também gera instalações orgânicas. As ad networks da série Baidu, 360 Ads, Xiaomi Ads e OPPO Ads operam de forma semelhante.

[![](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)](https://files.readme.io/46e1ad701d488a9c279afedca31ad42522056a328557365f06d7e29eefe60ae2-115015245283.png)

Enquanto isso, muitas instalações de aplicativos Android são geradas por links de download de APK em páginas da web mobile ou em espaços de anúncios in-app.

A AppsFlyer oferece três soluções principais para atribuir instalações de aplicativos Android no mercado da China; use o método mais relevante para suas necessidades.

<div id="local-android-app-store-that-supports-ad-attribution" />

<Accordion title="Loja de aplicativos Android local que oferece suporte à atribuição de anúncios">

**Solução:** Aplicativo Android out-of-store com link de atribuição

**Descrição:** Tradicionais empresas chinesas de Internet ou fabricantes de dispositivos móveis criaram suas próprias lojas de aplicativos Android e plataformas/ad networks, aproveitando seus vastos recursos de tráfego no mercado interno da China. No entanto, essas grandes empresas controlam rigorosamente o tráfego para verificar se o usuário que clicou no anúncio delas faz o download do Aplicativo na App Store de outra empresa. Nessas situações, você precisa gerar um aplicativo out-of-store exclusivo para cada loja de aplicativos Android. Enquanto isso, você pode usar o link de atribuição da AppsFlyer para registrar a performance das campanhas de anúncios criadas nas próprias plataformas de Anúncio/ad networks dessas empresas.

Ao usar esse método, você pode atribuir tanto a instalação orgânica quanto as instalações não orgânicas. Ao mesmo tempo, você pode otimizar campanhas de anúncios em termos de unidades de Anúncio, conjunto de anúncios e criativos etc.

**Exemplo:** Se você quiser promover seu Aplicativo Android por meio de Tencent Social Ads, Tencent Tui Ads e Wechat Ads, precisará fazer upload do Aplicativo Android para a loja de aplicativos Android da Tencent e para a MyApp etc., o que também gera instalações orgânicas. As ad networks da série Baidu, 360 Ads, Xiaomi Ads e OPPO Ads funcionam da mesma forma.

**Preparação:** Para saber como atribuir aplicativos out-of-store, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">aqui</Anchor>.

</Accordion>

<div id="ad-network" />

<Accordion title="Rede de anúncios">

**Solução:** Link de download do APK / APK + Link de atribuição

**Descrição:** Para promover Aplicativos Android em ad networks que não têm um requisito obrigatório sobre de onde fazer o download do Aplicativo, basta fornecer um link de download do APK ou um APK e o link de atribuição da AppsFlyer ao canal de mídia.

É fácil e rápido lançar campanhas de anúncios. Também é prático verificar a performance de diferentes canais de mídia na mesma página de visão geral do aplicativo.

**Exemplo:** Bytedance Ads(Toutiao), Sina Weibo, iQiyi

**Preparação:** Configure um aplicativo out-of-store Android e gere links de atribuição diferentes para diferentes ad networks. Para saber como atribuir aplicativos out-of-store, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">aqui</Anchor>.

</Accordion>

<div id="android-app-store-that-does-not-support-ad-attribution" />

<Accordion title="Loja de aplicativos Android que não oferece suporte à atribuição de anúncios">

**Solução:** aplicativo out-of-store Android

**Descrição:**  Para lojas de aplicativos Android que não oferecem suporte à atribuição de anúncios, você ainda pode usar Out-Of-Store Apps para atribuir todas as instalações vindas desta loja de aplicativos, mas todas as instalações são atribuídas como instalações orgânicas.

**Exemplo:** loja de aplicativos da Lenovo, loja de aplicativos da Huawei.

**Preparação:** para saber como atribuir aplicativos out-of-store, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">aqui</Anchor>.

</Accordion>

Se você estiver promovendo seus aplicativos com mais de uma das soluções mencionadas acima e quiser verificar os dados de todas as suas campanhas na China na mesma visualização do dashboard, poderá usar o <Anchor target="_blank" href="/marketers/pt/docs/custom-dashboards">Dashboard personalizado</Anchor>.

<div id="integrated-media-sources" />

## Canais de mídia integrados

<Anchor target="_blank" href="/marketers/pt/docs/china-domestic-market-ad-network-configuration">Guias de configuração</Anchor>

Canais de mídia integrados na China:

| Nome da fonte de mídia | Nome em chinês | PID | Logo |
| --- | --- | --- | --- |
| Anúncios da Tencent | Publicidade da Tencent | tencent\_int | ![ac1.png](https://files.readme.io/68f25ee4e8656ca36ea7ca48b2de7278f709fd93cb06f0db57b31afd27a65c57-115015067906.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/bytedance-ads-china-campaign-configuration">Anúncios da ByteDance</Anchor> | 巨量引擎（今日头条） | bytedance\_int | ![ac2.png](https://files.readme.io/cf43a8ae5a29032e86317f11a4af2beb60dfa8ac986a12f57fac6ddc0b7ae9ae-115015067926.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/wechat-ads-campaign-configuration">Anúncios do WeChat</Anchor> | Plataforma pública do WeChat | wechat\_int | ![ac4.png](https://files.readme.io/a1050b99def37cd07093dfebf34cee86f0d71ccb9cc407e5ebe87c3ea594a39b-115015067966.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/sina-weibo-ads-campaign-configuration">Anúncios do Weibo</Anchor> | Weibo Super Fensitong | sinaweibo\_int | ![ac5.png](https://files.readme.io/6902d459e199231a44deb9d64de0cf3ee8fe96d28e246e0506bbb275a8e225d5-115015247263.png) |
| Anúncios Sina Fuyi | Sina Fuyi | sinafuyi\_int | ![sinafuyi.logo.png](https://files.readme.io/e3b19f22bbb8ccd9aba37ac1d7f8222f8c90d6510622a59a80d2acf73d1f5dab-360001660797.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/baidu-app-ads-campaign-configuration">Anúncios do Aplicativo Baidu</Anchor> | Baidu Baitong | baitong\_int | ![ac6.png](https://files.readme.io/3055bb4a6865304d3117b714d364f84f233a25372ae251fefb07cbd5681bd27e-115015067986.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/baidu-mdsp-ads-baiyi-campaign-configuration">Baidu mDSP</Anchor> | Baidu Baiyi | baidumdsp\_int | ![ac7.png](https://files.readme.io/f610964f7895989f3535f9b389fd0c7218b1c44e68a7ba9c539fc0d0a1ee825a-115015068006.png) |
| Anúncios de pesquisa da Baidu | Anúncios de pesquisa da Baidu | baidusearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidusearch.png" width="112px" /> |
| Anúncios nativos da Baidu | Anúncios no feed da Baidu（nativos da Baidu） | baidufeedads\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| Anúncios nativos da Baidu 2 | Anúncios no feed da Baidu（nativos da Baidu）2 | baiduxinxiliu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/baidufeedads.png" width="119px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/xiaomi-ads-network-campaign-configuration">Anúncios da Xiaomi & Loja de aplicativos</Anchor> | Plataforma de marketing da Xiaomi & Loja de aplicativos | xiaomichina\_int | <Image alt="ac8.png" src="https://files.readme.io/4976cf0391214984b4bbce7ad66f9df71c72a5eef3c74414d77ad1fe569c19ff-115015068026.png" width="37px" /> |
| Huawei App Gallery na China | Loja de aplicativos da Huawei | huaweiappgallerychina\_int | <Image alt="huawei_app_store_logo.png" src="https://files.readme.io/29f84e8d0e90fc5bb85fc86810a45810fd0bc5fea58869c124b8f66354b67c78-10801903185809.png" width="40px" /> |
| Loja de aplicativos da OPPO na China | Loja de aplicativos da OPPO | oppostorechina\_int | ![oppo_store_logo.png](https://files.readme.io/30bdc4b4613f423f028eea5adfc6eee714805db65b857c49d6221639f19b3523-10801961659153.png) |
| vivo Ads & Loja de aplicativos | vivo plataforma de marketing&loja de aplicativos | vivoads\_int | <Image alt="vivo_store_logo.png" src="https://files.readme.io/5b3b87a0d4a6c424421d9d1b156cf0b1d81da7b534a53e760227de2726db8445-10802004853009.png" width="41px" /> |
| 360 Ads | Plataforma de desempenho Dianjing 360 | 360\_int | ![ac9.png](https://files.readme.io/b2a47bc04124313c237898040c72ee5eee2e86754333eea35f7b35c4ac0bd7f1-115015068046.png) |
| Ali UC Ads | Ali Huichuan （UC Toutiao） | uctoutiao\_int | ![ac10.png](https://files.readme.io/5a40ba07cd5b23b898849bf1ef6689704de0e4773c354ed52f455ef6418fdd61-115015068086.png) |
| Netease Ads | Yixiao da NetEase | netease\_int | ![ac11.png](https://files.readme.io/6572ef63727ca2aa95cdf747804ec9b061e744e130dd0285ccda84bd0fdd5820-115015068106.png) |
| iQIYI Ads | Qilin Shensuan da iQIYI | iqiyi\_int | ![ac12.png](https://files.readme.io/7a3eab06d7e7bd598e750e69ea72c2a127322dbe343c889b025803ca766a5d85-115015247303.png) |
| MOMO Ads | Anúncios MOMO | momo\_int | ![ac13.png](https://files.readme.io/17478fe1e70278da1ee55522fe0132a7a42e11c36a4b86ebb5fde14a17d9abb2-115015247323.png) |
| YouKu DSP | Ali Mama（sistema DSP Ruishi Youku） | youkudsp\_int | <Image alt="ac14.png" src="https://files.readme.io/2aabab6dc35278c15dd687cfb0ae3dee71c372226265b0606b6381ea7d90a8da-115015247343.png" width="98px" /> |
| Kuaishou | Plataforma de gerenciamento de anúncios da Kuaishou | kuaishou\_int | ![ac15.png](https://files.readme.io/801097b7fb9ce7020cddde8db46093fb39ad55a01b4ae282f5ffc44e591c5bd4-115015068126.png) |
| douyu.TV | 斗鱼TV | douyu\_int | ![ac16.png](https://files.readme.io/7ab338fd14e1b35c3eb5c20184a451516a05f98a3fcf605d9a04ccec546105e1-115015247363.png) |
| Anúncios da Bilibili | Plataforma de veiculação de anúncios da Bilibili | bilibili\_int | ![bilibili.logo.png](https://files.readme.io/f2b2cd2378d48beb8770a89694e441a5bb1dd00b30b1eac540df7f306878b594-360001660817.png) |
| Youdao DSP | Youdao Zhixuan | youdaodsp\_int | ![youdaozhixuan.logo.png](https://files.readme.io/9c9c9fc6b2226e666829373beef151a65ec38393a496bd3563a8649438d4331d-360001660837.png) |
| Anúncios da Meitu China | Plataforma de anúncios da Meitu | meituchina\_int | ![meitu.logo.png](https://files.readme.io/0bc4911d6a5455207e31d1f1a00d7af54c0f3a93167dbfabb33cdd96bb430c2f-360001660857.png) |
| Anúncios da Meiyou | Anúncios da Meiyou Mulher Connect | meiyou\_int | ![meiyou.logo.png](https://files.readme.io/413aae7d93717526cfdad51afac4097f22e0c826c79a44d14326f65b1805b6a2-360001660877.png) |
| Oppo | Oppo | oppo\_int | <Image alt="ac17.png" src="https://files.readme.io/6a6aeb9b3675eb5f28b29a47c5fb454c3f5f8fc4c49c856ceccc4e0922c45200-115015247383.png" width="131px" /> |
| Yunshu | 云数（百思不得姐） | yunshu\_int | ![ac18.png](https://files.readme.io/09e91278b253f5c7dcd7c681a52a960b346b0665d20084bb64afb7bf2c94e5ba-115015247403.png) |
| TapTap Game | TapTap | taptapgame\_int | ![ac19.png](https://files.readme.io/536f59f036f7c4f027308dbd25c6d04db8748c070fd6e2fbbb3816d13cbfa577-115015068146.png) |
| Ipinyou | 品友 | ipinyou\_int | ![ac20.png](https://files.readme.io/54121bb0a388c6e238749ae6166e30fafcd251a94518abaa0e5de02005f078f3-115015068166.png) |
| Hupu | 虎扑 | hupu\_int | ![ac22.png](https://files.readme.io/a463753277f62ef989271ce9433940f02cbbf7a9e11b6dd675c1b81f8207223c-115015068226.png) |
| Chance | 畅思 | chance\_int | ![ac23.png](https://files.readme.io/7dbac1e40c129085b9be9e24937e0e22b0ff16d5bc2e2b75da3a7b83e8f90acd-115015068246.png) |
| Domob China | 多盟 | domobc\_int | ![ac24.png](https://files.readme.io/0a01e63ce107e0fb23602ff13b6f76d05b4f1464dc82016ef4bcfc17fe9c291e-115015247423.png) |
| Adwo | 安沃 | adwo\_int | ![ac26.png](https://files.readme.io/1fa607feffbf2adfc5905c607f45960585f24cf58dd63d434ffa5ba2a1760923-115015068266.png) |
| Youmi | 有米 | youmi\_int | ![ac28.png](https://files.readme.io/d8eeaa83743d8fbb5dc2ee27cf5426ccd81ee7304d3e1cdd3e8f7e113f3b99fc-115015247483.png) |
| Behe | 璧合 | behe\_int | ![ac29.png](https://files.readme.io/653b4e503246e97f7b11a8886737d265d1cd200bf3233d70b5915a0539a5bbe5-115015068286.png) |
| biddingx | 舜飞 | biddingx\_int | <Image alt="biddingx_logo.png" src="https://files.readme.io/ce39102d4bb1b167b621a98f549c9d0ed6734574d5114699e5fe5207f1626946-115011049765.png" width="114px" /> |
| Anúncios Auto Home | 汽车之家广告平台 | autohome\_int | <Image alt="autohome_logo.png" src="https://files.readme.io/318da1d84a688f873e25ee59924e1c39268e18aef5f2cb19f2daf2ffbec6dcd5-115011049785.png" width="104px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/zhihu-ads-campaign-configuration">Anúncios do Zhihu</Anchor> | 知乎营销平台 | zhihu\_int | <Image alt="zhihu_logo.png" src="https://files.readme.io/07e4355e4c74541dc943831483a19662425b3a2efdd7dc7acc4a3abdc33506fc-115011049805.png" width="87px" /> |
| kkworld | Kuaikan Manhua | kkworld\_int | <Image alt="kkworld_logo.png" src="https://files.readme.io/23e353ba28fd55eeb0f326aa0035142d29f56abbaf402e836bf00f8191f4d055-115011112269.png" width="96px" /> |
| Todos os anúncios de futebol | Plataforma de anúncios Dongqiudi | allfootball\_int | <Image alt="allfootball_logo.png" src="https://files.readme.io/2522198caeaa17915b6b70c682b8cd772a9dd520f92b76f80d74176ff69c4fa9-115011049945.png" width="98px" /> |
| VoiceAds | 讯飞DSP | voiceads\_int | <Image alt="voiceads_logo.png" src="https://files.readme.io/7c9fdba5a283531bb430bb68e9955e6926697f43bd9b188063795ddca37903cd-115011049985.png" width="97px" /> |
| WiseMedia | 新数DSP | wisemedia\_int | ![wisemedia_logo.png](https://files.readme.io/4d1f177f2f18960f807072c5ac6c6f07c1473d8dae3b85dbdbc9963e8fb707d6-115011049845.png) |
| WPS | Software de escritório WPS | wps\_int | ![wps_logo.png](https://files.readme.io/12a19f0ee8d8501be3c8d9c03a835ac320f1beeaec55aba9ff40dcb3da4060c4-115011049865.png) |
| MadhouseChina | Edomedia | madhousechina\_int | ![madhouse_china_logo.png](https://files.readme.io/01b0831cfb73bc0c049c9ae70e34fdd2781871a1bebe40d62d63b346be1c6fbf-115011050025.png) |
| Weidong | Weidong | weidong\_int | <Image alt="weidong.png" src="https://files.readme.io/c355c3e4ae3a0b215ec5caa7a910164f5667bf7d34a308b0b77437540eb9ee56-360002013098.png" width="59px" /> |
| AdinAll | JuGao | adinall\_int | <Image alt="adinall.logo.png" src="https://files.readme.io/29bceececa81b30a55204ea6ac7abe219737441ca4017e5f5944c53d55f3ecc8-360001976997.jpg" width="128px" /> |
| BlackDragon | Heilong | blackdragon\_int | <Image alt="blackdragon.logo.png" src="https://files.readme.io/2247dfaaa2ac63b1ddd09e37963188e3ca9315d0454a1f228f3113bb470a1406-360002076458.png" width="144px" /> |
| chenbai | Chenbai | chenbai\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chenbai.png?v=1" width="136px" /> |
| Dayumob | Zhiqu Media | dayumob\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dayumob.png?v=1" width="136px" /> |
| Idvert | Aiwate | idvert\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/idvert.png?v=1" width="39px" /> |
| Jingmeng | Jingmeng Century | jingmeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jingmeng.png?v=1" width="144px" /> |
| Jusha | Jusha | jusha\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jusha.png?v=1" width="78px" /> |
| Mailuo | 脉络时代 | mailuo\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mailuo.png?v=1" width="144px" /> |
| Manhuaren | 漫画人 | manhuaren\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/manhuaren.png?v=1" width="144px" /> |
| iFeng Ads | 凤凰凤羽客户平台 | ifeng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ifeng.png?v=1" width="144px" /> |
| Anúncios Qutoutiao | 趣头条广告 | qutoutiao\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/qutoutiao.png?v=1" width="34px" /> |
| Busca Shenma | 神马搜索 | smsearch\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/smsearch.png?v=1" width="81px" /> |
| Anúncios Sogou Qidian | 搜狗奇点系统 | sogouqidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sogouqidian.png?v=1" width="117px" /> |
| Anúncios Sohu XinPinSuan | 搜狐新品算 | sohuxps\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sohuxps.png?v=1" width="49px" /> |
| Tuia | 推啊 | tuia\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tuia.png?v=1" width="74px" /> |
| Yidian Zixun | 一点资讯 | yidian\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yidianzixun.png?v=1" width="94px" /> |
| Zhi Zi Yun | 智子云 | zhiziyun\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zhiziyun.png" width="137px" /> |
| Hesheng | 合声 | hesheng\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hesheng.png?v=1" width="144px" /> |
| Zuo Ye Bang | 作业帮 | zuoyebang\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuoyebang.png?v=1" width="64px" /> |
| Chuniu | 初牛 | chuniu\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chuniu.png?v=1" width="108px" /> |
| Zuiyou | 最右 | zuiyou\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zuiyou.png" width="30px" /> |
| Himalaya Anúncios | 喜马拉雅广告平台 | ximalaya\_int | ![ximalaya.png](https://files.readme.io/4aab1e15ea11f67b9d359acc72e74adc31e3f1f1b180cfd840fe4b2dcad48405-49929445299089.png) |
| Anúncios do Wifi Master Key | WiFi万能钥匙广告平台 | wifimasterkey\_int | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wifimasterkey.png" width="144px" /> |
| vivo Ads | plataforma de marketing da vivo | vivoads\_int | ![vivo-logo.png](https://files.readme.io/fd5eea06d85e2b9993c0fcc961dacc9559d917aea1e78ad1c069546649a8eb86-360003580657.png) |
| ShiHuo Ads | Anúncios MOMO | shihuo\_int | <Image alt="__logo.png" src="https://files.readme.io/d5ae526235128f06bcb986130b1e6ae2cb1f66e0d053760a0f6ad9565c5bbfc1-360004371338.png" width="120px" /> |
| OneSavour Ads | Anúncios da OneSavour | onesavour\_int | <Image alt="onesavour_logo.png" src="https://files.readme.io/e18db5eb6450c5cc1ddd8b5425808a502ee82790e330ccf5a42454cb6260835b-360004371358.png" width="120px" /> |
| Qianka | Qianka | qianka\_int | <Image alt="__.jpeg" src="https://files.readme.io/bd78e74e85eecdd7abf85be01b5bf0bb532941900fe42f6a2e9d9bf91219c5fe-360004682538.jpg" width="112px" /> |
| SMZDM | SMZDM | smzdm\_int | <Image alt="logo.png" src="https://files.readme.io/dcdce2cc3ead9202f4f8b86f237b342a5e0d8bc4f4f8f29a1acf964e9717add9-49929445301393.png" width="108px" /> |
| MGTV | MangoTV | mgtv\_int | <Image alt="250.png" src="https://files.readme.io/816531dfd509852c87f80be59fa53435ed49263156043b68b13b4d6f65723e79-49929499695377.png" width="106px" /> |
| AdView Ads | Kuaiyou | adview\_int | <Image alt="adview_logo.png" src="https://files.readme.io/3f2fcf638630e012df3e9a04e11e68b4bcaae350ec63d0f55e3b6e02aa928156-49929445301521.png" width="108px" /> |
| XTrader | Lingji | thextrader\_int | <Image alt="thextrader_logo.png" src="https://files.readme.io/bad492420d7eec766bb2806e7ae9ea3bce508ef10db0da25e0a2735097b01d06-49929445301649.png" width="96px" /> |
| Dianrui | Dianrui | dianrui\_int | <Image alt="dianrui_logo.png" src="https://files.readme.io/c901df393b1d3aca2db78ad44d43f671365694247e41038221d4b7a34917af1e-49929499696401.png" width="108px" /> |
| Samsung | Samsung China | samsungcheilcn\_int | <Image alt="samsungcheilcn_logo.png" src="https://files.readme.io/0955e4373dabc78e215503b0a364d4b71e131cd12e620f7d24d0fd7645b8e7c2-49929445301777.png" width="104px" /> |
| Netease Music | NetEase Cloud Music | neteasemusic\_int | ![neteasemusic_logo.png](https://files.readme.io/b4d23f259b6542191061595ed3f3cd32ec56a98437c062cd29b67cfd17e9a2cb-49929499698193.png) |
| Yixia | Xiaokaxiu (Yixia Technology) | yixia\_int | ![yixia_logo.png](https://files.readme.io/a5be66c9a5f19999690e1f17b728c86e71094acb142647a43230e29f96615801-49929499698321.png) |
| Shenqi | Shenqi Huyu | shenqi\_int | ![shenqi_logo.png](https://files.readme.io/3ee8b39822e2af4960cc928425553872096fd6e5aa7aecb2a54c9458d9a02370-49929445302033.jpg) |
| Tangguo | Chuannuo (Tangguo anúncios) | tangguo\_int | n/a |
| Hotmobi | Hotmobi | hotmobi\_int | <Image alt="hotmobi_logo.png" src="https://files.readme.io/85c47cbc099d3aea486abd4cd0674fbe4e5b14f3832d4d2e933fb323c15736a9-49929499698961.png" width="120px" /> |
| Zplay | 掌游天下 | zplay\_int | <Image alt="zplay_logo.png" src="https://files.readme.io/c866ed7863d1b89d2eb79f38c7ac450e44ad3e5e65d975828d68f16beec5d356-49929499699217.png" width="120px" /> |
| Yumi Mobi | 玉米移动 | yumimobi\_int | <Image alt="yumimobi.png" src="https://files.readme.io/789fab51c00af21db42f712af80222a346fa0bf95726e0e265198ab3b56f00f5-49929445303313.png" width="120px" /> |
| Lanpan | 蓝畔 | lanpan\_int | ![lanpan_.png](https://files.readme.io/6cd76c3069a78d8e04aba8cc1fdddc23258738a25a8d8b61b83a9121ae0c46df-49929445303697.png) |
| Xinlan | 新蓝(新效科技） | xinlan\_int | <Image alt="xinlan.png" src="https://files.readme.io/3820d3ea27a72164605e08a42d9c2e58e312f65263d58f1af6caef6001f91a24-49929445303825.png" width="104px" /> |
| Youlan Ads | 幽蓝 | youlanad\_int | <Image alt="youlanad.png" src="https://files.readme.io/9563d92d341dc8b426ce85b2b013a6c2536076dc3aaa6813e55db88275d4051f-49929445304081.png" width="104px" /> |
| Avazu Ads | 艾维邑动 | avazu\_int | <Image alt="avazu.png" src="https://files.readme.io/4dd2533d90aa6b65b7157a8f3e98b1d59778cf2ca1fb32a808ec32c5cd95020d-49929445304465.png" width="81px" /> |
| Shangbang | 上榜（今日赚） | shangbang\_int | n/a |
| 51bizhi | 51壁纸 | 51bizhi\_int | ![51bizhi.png](https://files.readme.io/9aa92b4687911f726e5d7140238b89afce499dafe36c8be74d70a6893aeab6c6-49929445304593.jpg) |
| Chandashi | 禅大师 | chandashi | ![chandashi.png](https://files.readme.io/238ffe5d4a1bfb13270c66e78cb9a7a29a7171f03d653145ca53386b7ac2fc30-49929499700625.png) |
| Ann9 | 应用雷达 | ann9adnetwork\_int | ![ann9adnetwork.png](https://files.readme.io/943837f39e0da7e3ed40d47f5094e23aad53b46ab300ac716b6cae9a3882b6e6-49929499701137.png) |
| Gomo | 久邦数码 | gomo\_int | <Image alt="gomo.png" src="https://files.readme.io/9082987c41b2705601bd0b2cf8af0ca454d681111ac997206551a8243d55cdd9-49929445305361.png" width="112px" /> |
| Vision Mobile | Interação na palma da mão | adzshd\_int | ![adzshd.png](https://files.readme.io/49dd10549449cd8cd44be30859cc2be207d8eae84cb94b4c48e53643738efac3-49929445305617.png) |
| Adjuz | Anúncios Juzhang | adjuz | <Image alt="adjuz.png" src="https://files.readme.io/6e9e005e3a8b788005f50bdaed01926c41471d03602ef25b923fb97f6b8ae301-49929499702161.png" width="108px" /> |
| Guohe Ads | Anúncios Guohe | guohe\_int | <Image alt="guohe.png" src="https://files.readme.io/26350c3ce1ae438f6d531b968a09a438c07692a7cb413d677cbd1ed4cdd51773-49929499704209.png" width="99px" /> |
| Mintegral | Mintegral | mingtegral\_int | <Image alt="mintegral.png" src="https://files.readme.io/dd9a6964bd7aebb86e752a29e95bcaeda685a8b861d85e58c94553e7787e6aa8-49929445306385.png" width="105px" /> |
| Mobvista | Mobvista | mobvista\_int | <Image alt="mobvista.png" src="https://files.readme.io/ebf85ed57872c8c9077b128fb0eb2bd2f75ec9cb026a9fac7c86fc28120dee36-49929445306513.png" width="114px" /> |
| Emar | Yima | yima\_int | <Image alt="yima.png" src="https://files.readme.io/0f92d1246ba9d68ce7dc11393d0c67f6cf753e771c844425dbc04c203c392ced-49929499704977.png" width="116px" /> |
| Centrixlink | Yinyi Digital | centrixlink\_int | <Image alt="centrixlink.png" src="https://files.readme.io/3227dbe2a242f1e71b4f6e9ade307a23e514e5b1b5253437fd6e376ba94ec86e-49929499705489.png" width="88px" /> |
| Codrim | Gasto em microtransações | codrim\_int | <Image alt="codrim.png" src="https://files.readme.io/1c803ad92eb642ca8aac67f059d43368206088e3f7145ddeda3bc4ceb142a3e1-49929445307025.jpg" width="100px" /> |
| lbadvisor | 量江湖（比邻弘科） | lbadvisor | <Image alt="lbadvisor.png" src="https://files.readme.io/94ce897a116bdc7da10c0ab717b8576b4643e4f0b78eac16987e6e1c33b6dd28-49929499705617.png" width="88px" /> |
| ADYOYU | 涌玉 | yoyuad\_int | <Image alt="yoyuad.png" src="https://files.readme.io/7849052bd1f307bb547731f345277383c4c3343ff78ac78f218fa38a78314622-49929499705873.png" width="51px" /> |
| KUAIZI | 筷子科技 | kuaizi\_int | <Image alt="kuaizi.png" src="https://files.readme.io/8e3c2f4d1ad9dc5944f9ed263734cd0d6a675ebd6a34e62f128401b445a785aa-49929445307409.png" width="96px" /> |
| Yeahmobi | 易点天下 | yeahmobi\_int | <Image alt="yeahmobi.png" src="https://files.readme.io/8fc80c33f58d56f1e8edd04e9ebdad826e89ecdfb334a054d879eff4318a21f1-49929445307793.png" width="97px" /> |
| HUYA | 虎牙直播 | huya\_int | <Image alt="____LOGO.png" src="https://files.readme.io/6bd6020cb509a5345c1efbeecd8efc16672e4ed0af412e13d711d30c280517cd-49929445308305.png" width="93px" /> |
| MJweather | 墨迹天气 | mjweather\_int | <Image alt="200-50.jpg" src="https://files.readme.io/99943d6d103a8534ae14ee8be7b017113fdd212c2f236a43534e10997f40fc1c-49929499706257.jpg" width="100px" /> |
| Codoon | 咕咚 | codoon\_int | <Image alt="__logo.png" src="https://files.readme.io/31e8e6c3a86d08a0154cbe673ab75526180d726cf170a85cf035998ae09de68a-49929445308945.png" width="112px" /> |
| LongXi DSP | 珑玺DSP | lxdsp\_int | <Image alt="lxdsp_int.png" src="https://files.readme.io/c4ddf6f464af2f38d7f7a5080c7031905815156631c0f3a50c07c02910b26d9e-49929499706769.png" width="112px" /> |

<div data-zendesk-anchors="android-apps-in-china=aplicativos-android-na-china selecting-an-identifier=sele%C3%A7%C3%A3o-de-um-identificador attribution-solutions-for-the-chinese-market=solu%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o-para-o-mercado-chin%C3%AAs integrated-media-sources=canais-de-m%C3%ADdia-integrados" />
