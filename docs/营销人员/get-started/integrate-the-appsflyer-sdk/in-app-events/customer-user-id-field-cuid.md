---
title: 客户用户ID字段（CUID）
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-10-14T10:06:34Z'
  id: 207032016
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032016
---
> **概要：** 概要：您可以使用CUID对同一个用户通过不同设备、渠道或流量入口完成的事件进行统一衡量。

## **CUID的定义**

客户用户ID（CUID）是一种具有唯一性的用户标识符。该标识符通常由应用所有者（广告主）在用户完成注册时生成并设置。广告主能依据CUID将不同设备中的用户行为串联起来，形成完整的用户链路。

> 📄 **示例**
>
> 某应用的用户在多个设备中使用该应用，且在该应用中具有同一个CUID。该用户在其移动端或PC端设备上完成某个事件后，AF会将该事件及用户的CUID一并记录下来。这样广告主就能将不同设备的数据整合起来，从而对该用户有更全面的了解。
>
> 使用场景：
>
> * 如果该应用的用户在不同设备（手机、平板、电视、PC端）上完成应用内购买，该应用的广告主就可以使用CUID将这些购买事件关联到同一个用户，集中查看。
> * 如果用户在多个平台（PC端、移动端、电视）上安装了同一个游戏，可使用CUID对其使用情况进行跨平台共享，从而对用户体验形成一体化的理解。

## **设置CUID**

建议在SDK初始化流程中尽早设置CUID。CUID设置得越早，能关联到CUID的事件就越多。

<Tabs>
<Tab title="安卓原生">

只有在CUID设置完毕后发生的事件才能关联到CUID。

### **将激活关联到CUID**

如果您需要将激活关联到CUID，就必须在调用`start`startstart之前完成CUID的设置。

**重要提示！** 重要提示：请务必注意，如果您在调用`start`startstart之前设置CUID，可能会使SDK无法发送激活，导致归因失败。比如相关应用首次启动时，如果用户在SDK完成CUID设置之前就退出应用，就会发生这种情况。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#选择启动sdk的类class">在合适的类（Class）中启动SDK</Anchor>。

#### 在Application类中启动SDK

该方法可将SDK置于等待模式，等到CUID设置完毕后启动。

请注意： 请注意：如果CUID设置失败，SDK会一直处于等待模式，不发送任何事件。

#### 在Activity类中启动SDK

如果您想要在`Activity`ActivityActivity类中启动SDK时将CUID关联到激活，无需延迟发送激活，

#### 开发人员相关说明

开发人员需要了解以下信息：

* 开发者文档链接：
  * 如果您想将激活关联到CUID，请参见[此文档](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event)。

</Tab>

<Tab title="iOS原生">

* 如果在`start`startstart之后调用customerUserId，则只有在CUID设置完毕之后发生的事件会关联到CUID

#### 开发人员相关说明

让您的开发人员参考开发者资源中心（Dev Hub）中的[客户用户ID（Customer User ID）设置说明](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id)文档。

</Tab>

<Tab title="Unity">

#### 开发人员相关说明

让您的开发人员参考开发者资源中心（Dev Hub）中的[客户用户ID（Customer User ID）设置说明](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id)文档。

</Tab>

<Tab title="React Native">

#### 开发人员相关说明

让您的开发人员参考开发者资源中心（Dev Hub）中的[setCustomerUserId](https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid) API说明。

</Tab>
</Tabs>

## **CUID与隐私保护**

AppsFlyer重视并尊重您用户的隐私，因此我们[不允许收集敏感的个人数据或将此类信息传输到AppsFlyer平台。](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

为了确保用户的隐私不受侵犯，在设计CUID时切勿涉及任何能直接识别用户身份的信息。这类信息包括社保号码和身份证号码等。

此外，如果CUID中包含用户的邮箱地址或电话号码，请务必确保这些信息在发送到AppsFlyer时已进行哈希加密，禁止向AppsFlyer发送带有未哈希的个人数据的CUID。

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#用户链路报告">用户链路报告</Anchor>（帮助您进一步了解原始数据报告中的CUID）
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Google对于避免发送个人身份信息（PII）的建议</Anchor>

<div data-zendesk-anchors="what-is-cuid=cuid%E7%9A%84%E5%AE%9A%E4%B9%89 h_01HAJ00DVHRSDBS4FFKM16JFER=cuid%E7%9A%84%E5%AE%9A%E4%B9%89 h_01HAJ00DVHZ8V8MRAXN2W3T8DS=%E7%A4%BA%E4%BE%8B setting-the-cuid=%E8%AE%BE%E7%BD%AEcuid h_01HAJ00DVHDGM133A72HD5JXER=%E8%AE%BE%E7%BD%AEcuid associate-the-cuid-with-the-install-event=%E5%B0%86%E6%BF%80%E6%B4%BB%E5%85%B3%E8%81%94%E5%88%B0cuid h_01HAJ00DVHDE9V2MT6JQF8SAH3=%E5%B0%86%E6%BF%80%E6%B4%BB%E5%85%B3%E8%81%94%E5%88%B0cuid if-the-sdk-starts-in-the-application-class=%E5%9C%A8application%E7%B1%BB%E4%B8%AD%E5%90%AF%E5%8A%A8sdk h_01HAJ00DVH746B6YJVF70PMZJ8=%E5%9C%A8application%E7%B1%BB%E4%B8%AD%E5%90%AF%E5%8A%A8sdk if-the-sdk-starts-in-an-activity-class=%E5%9C%A8activity%E7%B1%BB%E4%B8%AD%E5%90%AF%E5%8A%A8sdk h_01HAJ00DVHYZBER40RJH0GM8KF=%E5%9C%A8activity%E7%B1%BB%E4%B8%AD%E5%90%AF%E5%8A%A8sdk developer-instructions-android=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E h_01HAJ00DVHZBZCRA1VGYJY44VY=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E developer-instructions::31dbab4b=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E h_01HAJ00DVH2RV902D6G224A4QY=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E developer-instructions-unity=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E developer-instructions-react=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E cuid-and-privacy=cuid%E4%B8%8E%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01HAJ00DVH4987JGZZVDA1NB29=cuid%E4%B8%8E%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01HE7RXTEPQAWV03276TDEPG0V=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
