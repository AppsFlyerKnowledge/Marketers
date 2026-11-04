---
title: AppsFlyer 与第三方平台之间的差异
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-10-14T10:04:05Z'
  id: 19384888063249
  locale: zh-cn
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/zh-cn/articles/19384888063249
---
> **概要：** 了解 AppsFlyer 与第三方平台在归因方面存在差异的原因。

<div id="overview" />

## 速览

由于媒体来源的数据共享政策，并非所有用户级别的<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">数据都会与第三方平台（例如分析和营销平台）共享</Anchor>。由于这些原因，第三方平台上显示的数据与 AppsFlyer 中的数据之间可能存在归因差异。

<div id="note" />

> 📘 **注意**
>
> 来自AppsFlyer的汇总和分析数据不受限制，仍然可用。

<div id="postback-restrictions-on-third-party-platforms" />

## 第三方平台的回传限制

当向第三方平台发送回传消息时，媒体来源限制有不同级别。回传信息可以完全不发送，可以不注明出处发送，也可以不受限制地发送。

<div id="types-of-postback-restrictions" />

#### 回发限制的类型

<div id="no-postbacks-sent" />

<Accordion title="不发送任何回邮邮件">

受媒体来源限制的原始数据事件的回传（详见<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">此表</Anchor>）不会发送到第三方平台。 这意味着第三方平台无法收到此类事件的回传，导致其平台上的归因信息比 AppsFlyer 少。

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="回传信息发送时不带署名。">

对于除受限原始数据事件之外的其他事件，以下列出的广告网络要求广告商在向第三方平台共享回传内容时，对媒体来源进行编辑。为了符合这类要求，AppsFlyer会**将回传中的原始媒体渠道替换为自然归因**。这意味着此类事件的回传信息发送到第三方平台时，不会包含媒体来源的署名，导致其平台上的署名信息比 AppsFlyer 少：

* Amazon
* Meta ads
* Pinterest
* Snapchat（<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>）
* X Ads
* Bing
* Yahoo（Oath:Ad Platforms / Yahoo Gemini)

<div id="note-1" />

> 📘 **注意**
>
> 对于 Meta 广告，回传行为取决于广告主是否接受了高级移动衡量 (AMM) 条款：
>
> * **AMM 不被接受：** 只有<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#install-referrer-android-only">通过安装引用归因的</Anchor>安装才会发送回传。回传数据不包含归属数据。
> * **AMM 已接受：** 对于<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">所有归因方法</Anchor>所归因的安装，都会发送回传。但是，回传数据不包含归因数据，这意味着所有回传都作为未归因（自然）数据发送到第三方平台。

</Accordion>

<div id="regular-postbacks" />

<Accordion title="定期回复">

所有其他未受限制或媒体来源未被编辑的事件都将作为常规回传发送。这包括聚合事件。

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">回传限制适用于所有与 AppsFlyer 集成的第三方平台，包括以下平台：</th></tr></thead><tbody><tr><td><span id="airship"></span>飞艇</td><td>Amplitude</td><td>批次</td><td>Braze</td><td>CleverTap</td><td>云</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>欧拉</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>卡胡纳</td><td>Leanplum</td><td>液体</td><td>局部分析</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>Salesforce</td><td>市场</td><td>MobilePush</td><td>Segment</td><td>斑点效应</td><td>斯沃夫</td></tr><tr><td><span id="tapcart"></span>塔普卡特</td><td>茶树</td><td>WebEngage</td><td>Winclap 分析</td><td>Google Analytics</td><td> </td></tr></tbody></table>

<div id="examples-of-discrepancies" />

## 差异示例

<div id="example-1" />

<Accordion title="Mixpanel上的原始数据限制">

<Tabs>
<Tab title="AMM 不被接受">

<div id="note-2" />

> 📄 **示例 1**
>
> 广告商使用 Meta 广告投放广告。他们还与 Mixpanel 合作，以更好地了解用户如何与他们的应用程序互动。广告主会查看上个月由 Meta 广告带来的安装次数：
>
>
>
> | 在 AppsFlyer 上 | 在 Mixpanel 上 |
> | --- | --- |
> | 广告主看到 100 次安装归因于 Meta 广告。<br /><br />其中 30 次安装是通过`gp_referrer`参数进行归因的。这些事件不受限制，会出现在原始数据报告中。 | 广告商只能看到 30 次安装量归因于自然流量。<br /><br />Mixpanel 无法收到 70 个受限事件的回传。使用`gp_referrer`参数归因的 30 次安装的回传数据将作为自然流量发送。 |

</Tab>

<Tab title="AMM 被接受">

<div id="note-3" />

> 📄 **示例 1**
>
> 广告主使用 Meta 广告投放广告，并已接受 AMM 条款。他们还与 Mixpanel 合作，以更好地了解用户如何与他们的应用程序互动。广告主会查看上个月由 Meta 广告带来的安装次数：
>
>
>
> | 在 AppsFlyer 上 | 在 Mixpanel 上 |
> | --- | --- |
> | 广告主看到 100 次安装归因于 Meta 广告。<br /><br />安装原始数据报告将包含全部 100 次安装，而不仅仅是通过 gp\_referrer 方法归因的安装。 | 广告商看到 100 次安装归因于自然流量。<br /><br />由于 AMM 被接受，Mixpanel 会收到所有 100 次安装的回传信息。然而，所有回传数据均不包含归因数据，因此所有安装都显示为自然安装。 |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="MoEngage上的原始数据限制">

<div id="note-4" />

> 📄 **示例 2**
>
> 广告商利用 Pinterest 投放广告。他们还与 MoEngage 合作，以获取有关客户参与度的见解。广告商会查看上个月有多少次“添加到愿望清单”事件归功于 Pinterest：
>
>
>
> | 在 AppsFlyer 上 | 在 MoEngage 上 |
> | --- | --- |
> | 广告商看到 97 个“添加到愿望清单”事件归因于 Pinterest。 | 广告商没有看到任何归因于 Pinterest 的“添加到愿望清单”事件。由于 Pinterest 的点击和浏览事件属于受限事件，因此 MoEngage 无法从 Pinterest 获取这些事件的回传数据。 |

</Accordion>

<div id="example-3" />

<Accordion title="对飞艇的限制">

<div id="note-5" />

> 📄 **示例3**
>
> 广告商使用必应投放广告。他们还与 Airship 合作，优化其移动应用程序的用户体验。广告商会查看上个月有多少购买事件归功于必应搜索：
>
>
>
> | 在 AppsFlyer 上 | 在飞艇上 |
> | --- | --- |
> | 广告商看到 35 起购买事件归因于 Bing。 | 广告主从自然流量中获得了 84 次购买事件。其中 35 个购买记录来自 Bing，但他们并不知道这一点，因为这些购买事件看起来像是自然发生的。 |

</Accordion>

<div id="note-6" />

> 📄 **相关文档**
>
> 关于<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#常见问题解答">原始数据内容限制的</Anchor>常见问题解答。

<div data-zendesk-anchors="Overview=%E9%80%9F%E8%A7%88 h_01HCVTKD7ZH991A8JF7XCNNE91=%E9%80%9F%E8%A7%88 h_01HE05K6FD3GFGWHDFAZ9R4GJ9=%E6%B3%A8%E6%84%8F postback-restrictions=%E7%AC%AC%E4%B8%89%E6%96%B9%E5%B9%B3%E5%8F%B0%E7%9A%84%E5%9B%9E%E4%BC%A0%E9%99%90%E5%88%B6 h_01HDDR9JG5303R38QCAB2ZF6CW=%E7%AC%AC%E4%B8%89%E6%96%B9%E5%B9%B3%E5%8F%B0%E7%9A%84%E5%9B%9E%E4%BC%A0%E9%99%90%E5%88%B6 types-of-postback-restrictions=%E5%9B%9E%E5%8F%91%E9%99%90%E5%88%B6%E7%9A%84%E7%B1%BB%E5%9E%8B h_01HE05EXEFJF6SGYTKZ78FPP7Z=%E5%9B%9E%E5%8F%91%E9%99%90%E5%88%B6%E7%9A%84%E7%B1%BB%E5%9E%8B h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01H9JCS8H0TQBPBVWS8KCJT296=%E6%B3%A8%E6%84%8F-1 h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=%E5%B7%AE%E5%BC%82%E7%A4%BA%E4%BE%8B h_01HCW4HS35ZTAEWPXB9JKCR725=%E5%B7%AE%E5%BC%82%E7%A4%BA%E4%BE%8B h_01HDDS499QJTX5RJY6CR98BDFB=example-1 01H8BXG7YBP4SSQGQ04N9VXWE9=%E7%A4%BA%E4%BE%8B-1 h_01KQZ1FQASP81EX4JGBQPKK38Q=%E7%A4%BA%E4%BE%8B-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01HD3Y812D0ABR3XYCGP9W42J7=%E7%A4%BA%E4%BE%8B-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3 h_01HD3YVXFJZN8MY4RWP3A8MMS8=%E7%A4%BA%E4%BE%8B3 h_01HDXK7W3JD3FM3ST6S459F3QS=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
