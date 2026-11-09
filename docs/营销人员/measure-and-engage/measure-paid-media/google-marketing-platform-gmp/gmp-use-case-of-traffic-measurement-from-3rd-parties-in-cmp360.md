---
title: 在CMP360中通过GMP衡量第三方流量
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-03-03T12:42:31Z'
  edited_at: '2026-10-14T10:12:18Z'
  id: 360018228758
  locale: zh-cn
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/zh-cn/articles/360018228758
---
> **概要**：在CM360中购买来自第三方媒体渠道的流量，并在AppsFlyer和CM360中同时衡量该流量入口带来的移动应用转化（AppsFlyer将其归因于该第三方媒体渠道）。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

<div id="measurement-of-cm360-with-non-dv360-third-party-media-sources" />

## 使用非DV360第三方媒体渠道在CM360中进行衡量

Google Marketing Platform（GMP）可整合广告与分析功能，帮助您建立高质量的用户联系、深入洞察用户行为并提升营销效果。

在AppsFlyer的使用场景中，GMP中的标准DV360 SRN对接（dv360\_int）可对**CM360管理**的DV360活动进行归因，无需归因链接即可实现。通过该对接，AppsFlyer可利用DV360 SRN回传数据对激活和再互动进行归因。

<div id="note" />

> 📘 **注意**
>
> * AppsFlyer通过标准DV360 SRN对接归因CM360管理的DV360广告活动，无需链接即可完成归因。 激活和再互动会通过DV360 SRN的回传机制进行归因。如果您正在通过CM360投放DV360广告，请参考<Anchor target="_blank" href="/marketers/zh/docs/google-marketing-platform-display-video-360-dv360-integration">DV360对接指南</Anchor>。
> * 如果第三方媒体渠道本身是SRN，AppsFlyer建议不要使用本文所述方法进行对接，以避免在同一合作渠道通过两种不同方式上报转化时出现冲突。例如，若您已在AppsFlyer中启用Meta Ads的SRN对接，同时又通过CM360按本文方法上报Meta Ads流量（facebook\_int），则可能同时收到Meta Ads和CM360的转化数据，CM360可能会捕捉到原本应由Meta Ads主对接归因的部分转化。

<div id="measuring-third-party-traffic-running-via-cm360" />

### 衡量来自CM360的第三方流量

以下是通过CM360管理第三方媒体渠道，并在AppsFlyer和CM360中同时进行衡量的推荐操作步骤：

<div id="step-1-integrate-the-third-party-media-source-and-gmp-with-appsflyer" />

#### 第1步：将第三方媒体渠道与GMP和AppsFlyer进行对接

为确保AppsFlyer能够正确归因，请执行以下操作：

* 确保相关第三方媒体渠道已在AppsFlyer中完成对接并启用。归因将归于该第三方媒体渠道，而不是CM360。启用GMP（dv360\_int）仅用于确保数据可以回传至CM360。
* 如果该第三方媒体渠道尚未与AppsFlyer对接，则应将其作为自有媒体渠道或自定义渠道处理。此时需要使用归因链接，并在链接中设置任意PID（media source）值。

<div id="note-1" />

> 📘 **注意**
>
> 关于代理归因：AppsFlyer需要代理名称才能对激活进行归因。请在归因链接中使用`af_prt`参数，或通过URL中的referrer参数添加代理名称。

<div id="step-2-create-the-required-attribution-links" />

#### 第2步：创建所需的归因链接

1. 1. <Anchor target="_blank" href="https://support.google.com/campaignmanager/answer/3040965?hl=en&ref_topic=2826011">创建CM360“跟踪广告”</Anchor>
   2. 在AppsFlyer中创建归因链接：
      * 归因链接中应包含您希望进行归因的实际媒体渠道，即第三方媒体渠道，而非GMP。 例如，如果第三方媒体渠道是Rocketfuel，应使用`pid=rocketfuel_int`，而非`pid=doubleclick_int`。 详情请见<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">此文档</Anchor>。
      * 如果nin1希望通过广告链接**重新唤醒已有用户**并直接打开App（而非跳转至应用商店），可使用**URI Scheme**方式实现深度链接。 此时需要在CM360链接中配置以下参数：
        * `af_dp`：设置为您的App的URI Scheme；
        * `af_force_deeplink=true`：强制启用深度链接行为。

      **归因链接示例：**

      <Tabs>
      <Tab title="Android">

      ```http
      https://app.appsflyer.com/com.example?pid=rocketfuel_int&c=campaign_name
      &advertising_id=13******-****-****-****-54**********
      ```

      </Tab>

      <Tab title="iOS">

      ```http
      https://app.appsflyer.com/com.example?pid=rocketfuel_int&c=campaign_name
      &idfa=13******-****-****-****-54**********
      ```

      </Tab>
      </Tabs>

   3. 将AppsFlyer归属链接附加到CM360链接：  

      <Tabs>
      <Tab title="Android">

      ```http
      https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
      dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
      ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
      &c=campaign_name&advertising_id=13******-****-****-****-54**********
      ```

      </Tab>

      <Tab title="iOS">

      ```http
      https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
      dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
      ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
      &c=campaign_name&idfa=13******-****-****-****-54**********
      ```

      </Tab>
      </Tabs>

      * 了解更多关于 <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters?">iOS和Android归因链接结构和参数</Anchor>的说明。
      * 了解更多关于 <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、主机端和PC端归因链接结构和参数</Anchor>的说明。

<div id="step-3-set-in-app-event-postbacks" />

#### 第3步：应用内事件回传

为确保CM360能收到这些广告活动产生的应用内事件数据，建议在dv360\_int中将事件回传范围设置为“所有媒体渠道（包括自然流量）”。

<div id="using-the-attribution-link" />

### 使用归因链接

在第三方媒体渠道投放广告时，务必使用您创建好的归因链接。当用户通过该广告激活应用后，AppsFlyer会将激活归因到相应的第三方媒体渠道，并通过回传通知该合作渠道。同时，AppsFlyer也会通过DV360对接将激活或后续的应用内事件上报至CM360。

最终结果是激活或应用内事件会被归因至相应媒体渠道，也会被DCM360记录。

<div data-zendesk-anchors="google-marketing-platform-cm360-nondv360-thirdparty-media-source-for-click-and-impression-measurement=%E4%BD%BF%E7%94%A8%E9%9D%9Edv360%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%9C%A8cm360%E4%B8%AD%E8%BF%9B%E8%A1%8C%E8%A1%A1%E9%87%8F h_01HN0GE07NDVK8MWQEYMKDFAE6=%E4%BD%BF%E7%94%A8%E9%9D%9Edv360%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%9C%A8cm360%E4%B8%AD%E8%BF%9B%E8%A1%8C%E8%A1%A1%E9%87%8F h_01HVXSGQZP305D7EF1SY56F26B=%E6%B3%A8%E6%84%8F measuring-thirdparty-traffic-running-via-cm360=%E8%A1%A1%E9%87%8F%E6%9D%A5%E8%87%AAcm360%E7%9A%84%E7%AC%AC%E4%B8%89%E6%96%B9%E6%B5%81%E9%87%8F h_01HVK04VANY30B8EX94F9WPBGB=%E8%A1%A1%E9%87%8F%E6%9D%A5%E8%87%AAcm360%E7%9A%84%E7%AC%AC%E4%B8%89%E6%96%B9%E6%B5%81%E9%87%8F step-1-integrate-the-thirdparty-media-source-and-gmp-with-appsflyer=%E7%AC%AC1%E6%AD%A5%E5%B0%86%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E4%B8%8Egmp%E5%92%8Cappsflyer%E8%BF%9B%E8%A1%8C%E5%AF%B9%E6%8E%A5 h_01HYBRGBH10N9H0WT45NQ65C6R=%E7%AC%AC1%E6%AD%A5%E5%B0%86%E7%AC%AC%E4%B8%89%E6%96%B9%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E4%B8%8Egmp%E5%92%8Cappsflyer%E8%BF%9B%E8%A1%8C%E5%AF%B9%E6%8E%A5 h_01HYBB2SJEYE0WV2PRY5SK51GB=%E6%B3%A8%E6%84%8F-1 step-2-create-the-required-attribution-links=%E7%AC%AC2%E6%AD%A5%E5%88%9B%E5%BB%BA%E6%89%80%E9%9C%80%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HYBA8YS1CWHN3APE5SV506TC=%E7%AC%AC2%E6%AD%A5%E5%88%9B%E5%BB%BA%E6%89%80%E9%9C%80%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 01JXQGQPDB66E3HWWEVPXXB8BZ=%E7%AC%AC3%E6%AD%A5%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 using-the-attribution-link=%E4%BD%BF%E7%94%A8%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HN0GE07N10T92EKR5B2482KB=%E4%BD%BF%E7%94%A8%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5" />
