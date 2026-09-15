---
title: "SKAN integrated partners list"
excerpt: "Lists of ad network partners having SKAN integration with AppsFlyer, and ad network Apple SKAdNetwork IDs."
---
**At a glance:** Lists of ad network partners having SKAN integration with AppsFlyer, Ad network Apple SKAdNewtork IDs.

## AppsFlyer SKAN partners

The partners listed are integrated with AppsFlyer and forward iOS SKAN postbacks to AppsFlyer.

Partners listed send AppsFlyer the SKAN postbacks they receive from iOS devices. In addition, they add to the postbacks supplement fields based on their advertising hierarchy and reporting systems. These supplement fields enrich the postback with more data and help to better understand the performance of your SKAN campaigns.

> 📘 Note
>
> SKAN postbacks are reflected in the SKAN overview dashboard regardless of the state of **Activate partner** toggle in the partner Integration tab.

The following enrichment fields are available:

- **Location**: Reported by the attributed ad network using the country code.
- **Enrichment Campaign ID**: This ID is distinct from the SKAN campaign ID reported in the iOS postback **which is always available**.
- **Enrichment Campaign name**: Displays in reports and dashboards.
- **Enrichment Adset ID**: Displays in reports and dashboards.
- **Enrichment Adset name**: Displays in reports and dashboards.
- **Enrichment Ad ID**: Displays in reports and dashboards.
- **Enrichment Ad name**: Displays in reports and dashboards.
- **Enrichment cost**: Displays in reports and dashboards.
- **View-through attribution support:** This field isn't enriched by the ad network, but rather indicates if VTA is available through SKAN postbacks.
- **Redownloads:** Available as part of the SKAN 2.0 postback for non-SRNs.

All SRNs send all install data in SKAN postbacks. Note that some SRNs choose to not distinguish between new installs and redownloads, meaning redownload data (for some SRNs) is not displayed in SKAN dashboard.

[List of SKAN networks](/docs/skan-integrated-partners-list#skan-enrichment-fields-supported-in-srn-integrations).

### SKAN SRN integrations and enrichment fields

| Partner name | Supported feature | Enrichment fields |
| --- | --- | --- |
| \*SKAN 4<br/>(data received) | Location | Camp. ID \| Camp. name \| Adset ID \| Adset Name \| Ad ID \| Ad Name \| Site ID \| Cost \| VTA+ \| Re-down-<br/>loads |
| [Meta Ads](https://support.appsflyer.com/hc/articles/360017095198-Enable-Facebook-and-AppsFlyer-SKAdNetwork-interoperation) | **✓** | - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** \| **✓** \| **✓\*\*\*** |
| [Google Ads](https://support.appsflyer.com/hc/articles/4403215779857-Google-Ads-SKAdNetwork-and-AppsFlyer-SKAdNetwork-interoperation) | - | - \| **✓\*\*** \| **✓** \| **-** \| **-** \| **-** \| **-** \| **✓** \| **✓** \| **✓** \| **✓** |
| [Snapchat](https://support.appsflyer.com/hc/articles/360017604077-Enable-Snapchat-and-AppsFlyer-SKAdNetwork-interoperation) | - | - \| **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **✓** \| **✓** \| **✓** \| **-** |
| [TikTok for Business](https://support.appsflyer.com/hc/articles/360018499098-Enable-TikTok-for-Business-and-AppsFlyer-SKAdNetwork-interoperation) | **✓** | - \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** |
| [X Ads](https://support.appsflyer.com/hc/articles/4410464316049#twitter-ads-and-appsflyer-skan-interoperation) | **✓** | - \| **✓\*\*** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **✓** \| **✓** \| **✓** \| **✓** |
| [Yahoo! Japan](https://support.appsflyer.com/hc/articles/4412602890641) | **✓** | - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - \| - \| **✓** |
| [Amazon Ads](https://support.appsflyer.com/hc/articles/27548444974353-WIP-SKAN-interoperation-with-Amazon) | **✓** | - \| **✓** \| **✓** \| **-** \| **-** \| **✓** \| **✓** \| **✓** \| - \| **✓** \| **✓** |
| [Apple Ads (Search Ads)](/docs/get-skan-postback-data-from-google-ads) | SKAN 1-3 | - \| - \| - \| **-** \| **-** \| - \| - \| - \| **✓++** \| - \| - |

\*Ad networks with more than 10% of their SKAN traffic from version 4

\*\*skan\_campaign\_id is not reported

\*\*\* Available for SKAN postbacks version 4 and above

^ Aggregated with click-through

\+ View-through attribution

\+\+ Cost is not available in the SKAN dashboard or SKAN Pull API due to the lack of campaign-level data in SKAN postbacks. Cost data is available in SSOT reports via classic ASA integration.

### SKAN non-SRN integrations and enrichment fields

| Partner name | Supported feature | Enrichment fields |
| --- | --- | --- |
| \*SKAN 4<br/>(data received) | View-through attribution | Location \| Camp. ID \| Camp. name \| Adset ID \| Adset Name \| Ad ID \| Ad Name \| Site ID \| Cost |
| RZR (formerly Aarki) | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| AdColony | - | **✓** \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| - \| **✓** |
| AdzMedia | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Appier | **✓** | **✓** \| - \| - \| - \| - \| - \| - \| - \| - \| - |
| Applovin | - | **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Appreciate | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| BigaBid | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| BoomBit | - | **✓** \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| - \| - |
| [TikTok for Business](https://support.appsflyer.com/hc/articles/360018499098-Enable-TikTok-for-Business-and-AppsFlyer-SKAdNetwork-interoperation) | - | **✓** \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| - \| **✓** |
| Chart-boost | - | **✓** \| - \| - \| - \| - \| - \| - \| - \| - \| - |
| Dataseat | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Edge Solutions | - | **✓** \| - \| **-** \| **-** \| **-** \| **-** \| **-** \| **-** \| - \| |
| InMobi | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| InMobi DSP | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **-** |
| ironSource | **-** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| **✓** \| **✓** |
| Jampp, an Affle company | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Kaden | - | **✓** \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| - \| |
| Kayzen | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| King | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Kismet | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| **✓** \| |
| Lifestreet | - | **✓** \| - \| **✓** \| - \| - \| - \| - \| - \| - \| **✓** |
| Liftoff | **✓** | **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Mapendo | - | **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| |
| Mintegral Inter-national Limited | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Moloco | **✓** | **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| MoPub Acquire | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| Myappfree | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| |
| myTarget (Mail.ru) | - | **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **✓** \| **✓** \| - \| |
| nend | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| |
| Outbrain | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Persona.ly RTB | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Reddit | **✓** | **✓** \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| **✓** \| - \| **✓** |
| Remerge | - | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Simeji | - | **✓** \| - \| - \| - \| - \| - \| - \| - \| - \| - |
| Smadex | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| **✓** |
| SmartNews | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| - \| - \| **-** |
| Tapjoy | - | - \| - \| **✓** \| **✓** \| **✓** \| **✓** \| **-** \| **-** \| - \| - |
| TD Media | - | - \| - \| **-** \| **-** \| **-** \| **-** \| **-** \| **-** \| - \| |
| Tencent AMS | - | - \| - \| - \| - \| - \| - \| - \| - \| - \| - |
| TheTradeDesk | **✓** | **✓** \| - \| **✓** \| **✓** \| - \| - \| - \| - \| - \| **✓** |
| Unicorn | **✓** | - \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| Unity Ads | **✓** | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| **✓** \| **✓** |
| Vungle | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **✓** \| **✓** \| - \| **✓** |
| Yandex Direct | - | **✓** \| - \| **✓** \| **✓** \| **-** \| **-** \| **-** \| **-** \| - \| - |
| ZinkAds | - | - \| - \| **✓** \| - \| - \| - \| - \| - \| - \| - |

\*Ad networks with more than 10% of their SKAN traffic from version 4

## Apple SKAdNetwork IDs of ad networks

The table that follows contains the list of Apple SKAdNetwork IDs to populate your app [_Info.plist_](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

[Download CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vSqwIBW3FzbrXKqluDQ2hEec7zcvVrxQ02ivWsHnGQTvLMeFmHHjGz1R5TVy6_cqAIVh0pAy4Yud7Qx/pub?gid=0&single=true&output=csv)

In accordance with [Apple guidance](https://developer.apple.com/forums/thread/663032) IDs must be in lowercase

| PID (AppsFlyer partner ID) | Apple ad network ID (SKAdNet) |
| --- | --- |
| aarki\_int | 4fzdc2evr5.skadnetwork |
| adappt\_int | 53nm4hsx3w.skadnetwork |
| adcolony\_int | 4pfyvq9l8r.skadnetwork |
| adcountymedia\_int | 633vhxswh4.skadnetwork |
| adkomo\_int | tmhh9296z4.skadnetwork |
| adperio\_int | vcra2ehyfk.skadnetwork |
| adsflourish\_int | zh3b7bxvad.skadnetwork |
| adstraction\_int | xmn954pzmp.skadnetwork |
| adsynthetic\_int | 79w64w269u.skadnetwork |
| adtheorent\_int | cg4yq2srnc.skadnetwork |
| adtiming\_int | 488r3q3dtq.skadnetwork |
| adupps\_int | d7g9azk84q.skadnetwork |
| adzmedia\_int | nzq8sh4pbs.skadnetwork |
| amazondsp\_int | vhf287vqwu.skadnetwork |
| amoad\_int | 866k9ut3g3.skadnetwork |
| appalgom\_int | 2q884k2j68.skadnetwork |
| appier\_int | v72qych5uu.skadnetwork |
| applift\_int | 6xzpu9s2p8.skadnetwork |
| applovin\_int | ludvb6z3bs.skadnetwork |
| applovin\_int | x8jxxk4ff5.skadnetwork |
| appreciateappoffers\_int | mlmmfzh3r3.skadnetwork |
| appsell\_int | gfat3222tu.skadnetwork |
| appsfiremng\_int | pd25vrrwzn.skadnetwork |
| beeswax\_int | c6k4g5qg8m.skadnetwork |
| bigabid\_int | 3qy4746246.skadnetwork |
| bondika\_int | y755zyxw56.skadnetwork |
| boombit\_int | qlbq5gtkt8.skadnetwork |
| buzzad\_int | 67369282zy.skadnetwork |
| bytedance\_int | 238da6jt44.skadnetwork |
| bytedance\_int | 899vrgt9g8.skadnetwork |
| bytedanceglobal\_int / tiktokglobal\_int | mj797d8u6f.skadnetwork |
| bytedanceglobal\_int / tiktokglobal\_int | 22mmun2rn5.skadnetwork |
| chartboosts2s\_int | f38h382jlk.skadnetwork |
| clearpier\_int | mp6xlyr22a.skadnetwork |
| creativeclicks\_int | 88k8774x49.skadnetwork |
| criteonew\_int | hs6bdukanm.skadnetwork |
| cronbay\_int | t3b3f7n3x8.skadnetwork |
| crossaudience\_int | c7g47wypnu.skadnetwork |
| crossinstall\_int | prcb7njmu6.skadnetwork |
| curatemobileltd\_int | 52fl2v3hgk.skadnetwork |
| cygobel\_int | 9vvzujtq5s.skadnetwork |
| dataliftretargeting\_int | 4468km3ulz.skadnetwork |
| dataseat\_int | m8dbw4sv7c.skadnetwork |
| disciplinedigital\_int | m5mvw97r93.skadnetwork |
| dlab\_int | z5b3gh5ugf.skadnetwork |
| dotc\_int | pwdxu55a5a.skadnetwork |
| dreamperf\_int | dd3a75yxkv.skadnetwork |
| edge\_int | 9nlqeag3gk.skadnetwork |
| evolvemedia\_int | h5jmj969g5.skadnetwork |
| exmox\_int | dr774724x4.skadnetwork |
| Facebook Ads | v9wttpbfk9.skadnetwork |
| Facebook Ads | n38lu8286q.skadnetwork |
| fascode\_int | t7ky8fmwkd.skadnetwork |
| feedmob\_int | fz2k2k5tej.skadnetwork |
| found\_int | cs644xg564.skadnetwork |
| fuzeclick\_int | w28pnjg2k4.skadnetwork |
| fyber\_int | c6k4g5qg8m.skadnetwork |
| gameberry\_int | 2rq3zucswp.skadnetwork |
| gmthub\_int | vc83br9sjg.skadnetwork |
| Google | cstr6suwn9.skadnetwork |
| Google | eqhxz8m8av.skadnetwork |
| gurmob\_int | 7k3cvf297u.skadnetwork |
| hybrid\_int | w9q455wk68.skadnetwork |
| igaworkstradingworks\_int | 54nzkqm89y.skadnetwork |
| imalimedia\_int | lr83yxwka7.skadnetwork |
| imobile\_int | v4nxqhlyqp.skadnetwork |
| inmobidsp\_int | wzmmz9fp6w.skadnetwork |
| iossearchads\_int | com.apple.ads |
| ironsource\_int | su67r6k2v3.skadnetwork |
| jampp\_int | yclnxrl5pm.skadnetwork |
| jetads\_int | 7tnzynbdc7.skadnetwork |
| jinglemobi\_int | l6nv3x923s.skadnetwork |
| jumprampgames\_int | h8vml93bkz.skadnetwork |
| jumprampgames\_int | uzqba5354d.skadnetwork |
| jungroup\_int | nu4557a4je.skadnetwork |
| kaden\_int | x44k69ngh6.skadnetwork |
| kaimedia\_int | 8qiegk9qfv.skadnetwork |
| kidoz\_int | v79kvwwj4g.skadnetwork |
| king\_int | xx9sdjej2w.skadnetwork |
| kismet\_int | 52fl2v3hgk.skadnetwork |
| lemmonetmobile\_int | au67k4efj4.skadnetwork |
| lifestreet\_int | t38b2kh725.skadnetwork |
| liftoff\_int | 7ug5zh24hu.skadnetwork |
| loopme\_int | 5lm9lj6jb7.skadnetwork |
| manplus\_int | feyaarzu9v.skadnetwork |
| mediabuying\_int | dmv22haz9p.skadnetwork |
| mediamath\_int | n6fk4nfna4.skadnetwork |
| mediasmart\_int | 7rz58n8ntl.skadnetwork |
| mfaas\_int | 7fbxrn65az.skadnetwork |
| mintegral\_int | kbd757ywx3.skadnetwork |
| mobco\_int | b55w3d8y8z.skadnetwork |
| mobilda\_int | ejvt5qm6ak.skadnetwork |
| mobione\_int | v7896pgt74.skadnetwork |
| mobrain\_int | 5ghnmfs3dh.skadnetwork |
| mobupps\_int | 275upjj5gd.skadnetwork |
| moburst\_int | 627r9wr2y5.skadnetwork |
| mobvista\_int | sczv5946wb.skadnetwork |
| mobwind\_int | 8w3np9l82g.skadnetwork |
| mocaglobal\_int | hb56zgv37p.skadnetwork |
| moloco\_int | 9t245vhmpl.skadnetwork |
| mooko\_int | nrt9jy4kw9.skadnetwork |
| motive\_int | dn942472g5.skadnetwork |
| mpnd\_int | 6v7lgmsu45.skadnetwork |
| myappfre\_int | cad8qz2s3j.skadnetwork |
| nend\_int | eh6m2bh4zr.skadnetwork |
| odenads\_int | jb7bn6koa5.skadnetwork |
| olimob\_int | fkak3gfpt6.skadnetwork |
| outbrain\_int | 97r2b46745.skadnetwork |
| persona.ly\_int | 44jx6755aq.skadnetwork |
| personalyrtb\_int | 44jx6755aq.skadnetwork |
| pipernet\_int | b9bk5wbcq9.skadnetwork |
| pocketmedia\_int | 84993kbrcf.skadnetwork |
| pokktperf\_int | zmvfpc5aq8.skadnetwork |
| pokktperformance\_int | zmvfpc5aq8.skadnetwork |
| pubnative\_int | tl55sbb4fm.skadnetwork |
| reddit\_int | 2tdux39lx8.skadnetwork |
| remerge\_int | 2u9pt9hc89.skadnetwork |
| revx\_int | 5a6flpkh64.skadnetwork |
| rtbdemand\_int | 3cgn6rq224.skadnetwork |
| rtbhouse\_int | 8s468mfl3y.skadnetwork |
| sabiomobile\_int | glqzh8vgby.skadnetwork |
| scalemonk\_int | av6w8kgt66.skadnetwork |
| siftco\_int | klf5c3l5u5.skadnetwork |
| simeji\_int | nfqy3847ph.skadnetwork |
| smadex\_int | ppxm28t8ap.skadnetwork |
| smartnewsads\_int | 9wsyqb3ku7.skadnetwork |
| snapchat\_int | 424m5254lk.skadnetwork |
| sportradar\_int | qu637u8glc.skadnetwork |
| spotad\_int | f73kdq92p3.skadnetwork |
| spykemedia\_int | 44n7hlldy6.skadnetwork |
| startapp\_int | 5l3tpt7t6e.skadnetwork |
| tapjoy\_int | ecpz2srf59.skadnetwork |
| taptica\_int | pwa73g5rt2.skadnetwork |
| targetmedia\_int | x5854y7y24.skadnetwork |
| tencentams\_int | f7s53z58qe.skadnetwork |
| thanhdat\_int | x8uqf25wch.skadnetwork |
| thetradedesk\_int | uw77j35x4d.skadnetwork |
| thingortwo\_int | 6964rsfnh4.skadnetwork |
| tnk\_int | gvmwg8q7h5.skadnetwork |
| twitter\_int | 9yg77x724h.skadnetwork |
| twitter\_int | n66cz3y3bx.skadnetwork |
| trademob\_int | ydx93a7ass.skadnetwork |
| unicorn\_int | 578prtvx9j.skadnetwork |
| unityads\_int | 4dzt52r2t5.skadnetwork |
| userbase\_int | 6qx585k4p6.skadnetwork |
| valista\_int | l93v5h6a4m.skadnetwork |
| ventesavenues\_int | rvh3l7un93.skadnetwork |
| vungle\_int | gta9lk7p23.skadnetwork |
| widenad\_int | r45fhb6rf7.skadnetwork |
| yahoogemini\_int | e5fvkxwrpn.skadnetwork |
| yahoojapan\_int | 8c4e2ghe7u.skadnetwork |
| yandexdirect\_int | zq492l623r.skadnetwork |
| yeahmobi\_int | 32z4fx6l9h.skadnetwork |
| yelohi\_int | axh5283zss.skadnetwork |
| youappi\_int | 3rd42ekr43.skadnetwork |
| zinkads\_int | 5mv394q32t.skadnetwork |
| zucks\_int | 3qcr597p9d.skadnetwork |

<Cards>
  <Card title="AppsFlyer SKAN solution guide" href="https://support.appsflyer.com/hc/articles/360011420698">
    Learn how to set up and configure AppsFlyer's SKAdNetwork solution.
  </Card>
  <Card title="SKAN Conversion Studio: Configuring performance measurement" href="https://support.appsflyer.com/hc/articles/4403727223185-">
    Configure conversion values and measure post-install performance.
  </Card>
  <Card title="SKAN Overview dashboard" href="https://support.appsflyer.com/hc/articles/360011307357">
    Analyze your SKAN campaign performance in the unified dashboard.
  </Card>
  <Card title="Send iOS postbacks directly to AppsFlyer" href="https://support.appsflyer.com/hc/articles/4402320969617">
    Configure direct postback delivery from iOS 15+ devices.
  </Card>
</Cards>