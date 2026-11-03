---
title: Meta ads应用内事件映射
metadata:
  keywords:
    - Facebook
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
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-10-14T10:12:39Z'
  id: 4410480904081
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410480904081
---
> **概要：** 本文解释了如何将相关应用内事件从AppsFlyer发送到Meta ads。

## Meta应用内事件映射

广告主需要将SDK或S2S应用内事件映射到Meta侧的预定义事件。广告主还可以向Meta发送每个<Anchor target="_blank" href="/marketers/zh/docs/measure-sessions">应用打开</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/measure-uninstalls#卸载事件映射">应用卸载</Anchor>的回传。

广告主可以通过事件回传充分利用Meta的高级优化功能，并搭建自定义人群包和相似受众人群包。

### 预定义事件的映射

Meta ads提供<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">多种预定义事件</Anchor>，可直接用于映射。

详情请参考<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure">此文档</Anchor>，其中列出了可用的Meta回传事件，您可以在这些事件中添加其他参数，传递更多信息，用于说明事件质量。

如需进一步了解Meta事件映射的具体操作，请参考<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#inapp-event-mapping">此文档</Anchor>。

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

请注意：Meta ads没有预定义的卸载事件。如需发送卸载事件，请使用[自定义事件](/docs/meta-ads-in-app-event-mapping#自定义应用内事件的映射)进行配置。

除了上文超链接中列出的事件之外，Meta还提供不带额外参数的其他预定义事件，详见下表。

| Meta事件标识符 | 说明 | 推荐的AppsFlyer SDK事件名称 |
| --- | --- | --- |
| Donate | 为您的组织或公益事业提供的捐款 | af\_donate |
| Schedule | 网点来访预约 | af\_schedule |
| SubmitApplication | 针对您提供的某项产品、服务或项目（如信用卡、课程、职位等）提交申请 | af\_submit\_application |
| FindLocation | 用户通过网页或应用发现您的业务网点并计划来访，比如用户搜索某个产品后发现该产品在您的线下商店有售 | af\_find\_location |
| Contact | 用户通过SMS、邮件、聊天框或其他方式与贵司联系 | af\_contact |
| CustomizeProduct | 通过配置工具或贵司的其他应用对产品进行自定义配置。 | af\_customize\_product |
| `Adimpression`安卓应用Adimpression：  <br />`Fb_mobile_purchase`iOS应用：Fb\_mobile\_purchase |  | af\_ad\_revenue |


<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th></th><th><span id="mapping-ad-revenue-data-for-campaign-optimization"></span>platform</th><th><strong>渠道映射事件</strong></th><th></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>安卓</td><td>AdImpression</td><td></td></tr><tr><td>iOS</td><td>fb_mobile_purchase</td><td>应用内购买</td></tr></tbody></table>


* <span id="availability-limitations"></span>通过**Adimpression**事件优化投放的功能目前仅支持：
  * 安卓应用。iOS应用可继续使用*fb\_mobile\_purchase*事件来发送广告收入数据。
  * 符合Meta要求的部分Meta ads账号。如果该功能显示为灰色（不可用），可能是因为该账号不符合[相关要求](https://www.facebook.com/business/help/571188993373447?id=561906377587030)。
* *af\_ad\_revenue*事件仅对购买了<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-cost-and-revenue-data">ROI360高级套餐</Anchor>的账号开放。
  * 没有ROI360套餐的账号可以使用其他事件名称发送广告收入数据。

### 自定义应用内事件的映射

在AppsFlyer平台中，您可以使用“CUSTOM”选项（自定义的Meta事件标识符）将自定义应用内事件映射到Meta。

AppsFlyer会将SDK中配置的事件名称和事件值（包括事件参数）按原样转发到Meta，并以其原始的AppsFlyer SDK事件名称呈现，不会显示为“custom”。

您可以<Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">利用这些事件来优化您的广告投放</Anchor>。

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### 自定义事件的自动参数映射

基于AppsFlyer与Meta的深度对接，AppsFlyer的众多标准SDK事件参数可自动映射到Meta侧的预定义参数。比如**af\_revenue**参数会转换为Meta中的 **\_valueToSum**参数，这样您就可以发送每个事件的收入，用于数据衡量和Meta中的投放优化。

> 📘 **注意**
>
> CUSTOM（自定义）和预定义事件的自动参数映射有所不同。
>
> 若使用<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure">预定义事件</Anchor>，**\_valueToSum**对应的参数有时是**af\_price**（例如`fb_mobile_add_to_cart` ），有时是**af\_revenue**（例如`fb_mobile_purchase`）。
>
> 对于映射到CUSTOM的事件， **af\_price** 总是映射到**fb\_price** ，**af\_revenue**总是映射到 **\_valueToSum**。

下表详细罗列了所有AppsFlyer事件的参数，这些参数通过CUSTOM事件映射到Meta时，会自动关联Meta侧对应的参数。

| AppsFlyer参数 | Meta侧参数 |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | {"fb_payment_info_"} available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | {"fb_returning_arrival_"} date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | {"fb_suggested_"} destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |


|  |  |
| --- | --- |
| <span id="value-to-sum"></span>fb\_mobile\_level\_achieved | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_price |
| fb\_mobile\_add\_to\_wishlist | af\_price |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_mobile\_initiated\_checkout | af\_price |
| fb\_mobile\_purchase | af\_revenue |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_revenue |
| fb\_mobile\_spent\_credits | af\_price |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_price |
| StartTrial | af\_price |
| Subscribe | af\_revenue |

## 事件和参数限制

[您发送到Meta ads的事件](https://developers.facebook.com/docs/app-events/faq#limits)受到以下规则的限制：

* 不允许使用以下字符：
  * 冒号（:)
  * 期间（。）
  * 非拉丁（英文）字母的字符集：自2020年1月12日起，Meta不再支持中文字符。AppsFlyer尚未测试其他字符集，因此您在使用其他字符集之前，请先确认Meta是否支持回传中出现这些字符。
* 事件名称区分大小写。为避免差异，请确保在所有媒体源和应用程序版本的事件名称中使用正确的大小写。
* 参数数量上限：25个。
* 事件和参数名称的长度限制：2–40个字符。
* 参数值长度上限：100个字符。
* af\_content参数值的长度上限：1000个字符。
* 允许使用的字符：字母、数字、下划线、连字符和空格。请勿使用非拉丁（英文）字符。使用非拉丁字符会导致数据不一致。

为应用内事件命名时需要注意以下几点：

* 您可以使用Meta侧的事件名称来命名AppsFlyer中的事件（如fb\_price），但这类事件不能作为CUSTOM事件发送给Meta。  
  **为了避免回传映射问题，建议您不要使用Meta侧的事件名称来命名AppsFlyer事件。**
* 如需将应用内事件回传映射到Meta，请向其发送所有渠道的事件数据，包括自然量。

> 🚧 **重要提示！**
>
> 除上述参数外，AppsFlyer会将其他所有CUSTOM事件数据**按原样**发送到Meta。广告主须负责确保其事件数据符合Meta的要求，且使用Meta认可的有效参数（见上文表格），否则Meta不会接收事件数据。

<div data-zendesk-anchors="facebook-iae-mapping=meta%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 h_01J1WCP44CHN0Q73P6DN7H8FKG=meta%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84 predefined-event-mapping=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%98%A0%E5%B0%84 h_01J1WCP44D18WMXCMHJ0FNF6Y0=%E9%A2%84%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%98%A0%E5%B0%84 01JAPZ6M11HSCE9QNN5NSD61FK=mapping-ad-revenue-data-for-campaign-optimization 01JAQ1ECZVR8SZ81KE6CDD08A2=availability-limitations custom-inapp-events-mapping=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%98%A0%E5%B0%84 h_01J1WCP44DK14AC5ZG4KTFFFSC=%E8%87%AA%E5%AE%9A%E4%B9%89%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E6%98%A0%E5%B0%84 automatic-parameter-mapping-with-the-custom-event=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%87%AA%E5%8A%A8%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 h_01J1WCP44D645TS6JFGM2BDGM9=%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%87%AA%E5%8A%A8%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 h_01J1WCP44DSZ7G3603W5EBWZEW=%E6%B3%A8%E6%84%8F 01JATBG1SZRRZ0PCANKQ6S8CX4=value-to-sum event-and-parameter-limitations=%E4%BA%8B%E4%BB%B6%E5%92%8C%E5%8F%82%E6%95%B0%E9%99%90%E5%88%B6 h_01J1WCP44DF2QMV10VXF8NQZ7W=%E4%BA%8B%E4%BB%B6%E5%92%8C%E5%8F%82%E6%95%B0%E9%99%90%E5%88%B6 h_01J1WCP44D9SNEYZG59KNM822K=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA" />
