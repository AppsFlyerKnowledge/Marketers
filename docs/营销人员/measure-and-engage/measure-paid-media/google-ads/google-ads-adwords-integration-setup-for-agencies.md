---
title: 广告主的Google Ads（AdWords）对接设置指南
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-10-14T10:11:11Z'
  id: 115003669983
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/115003669983
---
> **概要：**

如需了解详情，请点击<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers">此处</Anchor>。


<span id="enabling-agency-attribution-of-google-ads"></span>AppsFlyer支持Google Ads的代理配置，但广告主和代理必须各自有单独的Google Ads帐户，这样AppsFlyer才能对数据进行正确的归因。


<Accordion title="视频教程">

<Embed title="广告主的Google Ads（AdWords）对接设置指南" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="文档指南">

**前期准备**：

1.

![Google_Ag_1.png](https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png)

2.

![Google_Ag_2.png](https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png)

3.

4.

![Google_Ag_3.png](https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png)

5.

![Google_Ag_4.png](https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png)

6. 点击***下一步***。

![Google_Ag_5.png](https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png)

![Google_Ag_6.png](https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png)


![Google_Ag_7.png](https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png)

![Google_ag_8.png](https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png)


1. 从AppsFlyer的侧边栏中选择协作 > 活跃对接。
2. 搜索并选择**Google Ads**。

   ![gads-search.png](https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png)

   ![gads_agency-integration-link-id.png](https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png)
3. [![](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)
4. ![gads-agency-retargeting.png](https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png)
5. AppsFlyer建议将**点击归因窗口**设置为30天，以便与Google Ads的自归因窗口期一致。

   ![gads-click-through.png](https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png)
6. ![gads-view-through.png](https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png)
7. *重装激活归因*
   * 要启用再安装归因，请打开这个开关。
   * 无需开启浏览型归因或设置再安装归因窗口期，因为会从安装归因配置中获取这些值。
8. 单击**保存并关闭** 。


1.

2.   
[![](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)

3.

[![](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)

4. 点击**保存**。


<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="衡量应用转化（必须完成）">

（仅**Google Ads**管理员账户可执行以下操作）

> 🚧 **重要提示！**
>
> 您必须打开应用并触发需要映射的应用内事件，才能让**Google Ads**记录新增的转化。如需测试iOS应用，则必须收集IDFA才能看到该事件。添加事件转化后最多需等待6小时才能生效。添加完毕后，您就可以导入这些事件。导入后，新增转化的状态就会从“No recent conversion”（最近无转化）变为“recording conversion”（正在记录转化）。

1. 回到Google Ads的**Overview**页面，进入**TOOLS AND SETTINGS** > **Measurement** > **Conversions**。   
    [![conversions_overview_en-us__1_.png](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)
2. 点击 **+ New conversion action**。   
    [![New_conversion_action_en-us__2_.png](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)
3. 在转化类型列表中选择**App**，然后选择**Third-party app analytics**并点击**Continue**。  
    [![select_app_en-us__3_.png](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)
4. 请勾选相关应用中需要导入的事件（**first\_open**必须勾选）。  

   > 📘 **注意**
   >
   > 出现以下情况时，您需要重新导入事件：1）Google Ads中的**Partner Event identifier**（渠道事件标识符）有所变更；2）您选择了CUSTOM后AppsFlyer中对应的事件名称发生了变化。


   点击**Import and Continue**，然后点击**Done**。    
    [![select_events_to_import_en-us__4_.png](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)
5. 进入**Conversions** > **Summary**页面后您就能看到第三方转化事件。如果事件未出现在列表中或已从Google Ads转化导入列表中删除，请点击View all conversion actions，您会看到Status筛选条件。此时界面会显示Status状态筛选条件。  
    [![conversions_summary_en-us__5_.png](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)
6. 点击**Status**并选择**All**查看所有事件，包括已停用或删除的事件。  
    [![conversion_action_status__6_.png](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)
7. 完成上述操作后，您就能通过AppsFlyer来衡量Google Ads移动广告了。

> 📘 **注意**
>
> 请确保“include in conversions”的设置与Google Ads的广告投放目标一致。详情请咨询您的Google账户经理或参阅<Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">此处的Google文档</Anchor>。

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HKA1J5ES5T65NT5QMY5ZGXP6=enabling-agency-attribution-of-google-ads h_01HKA1J5ETK5PXYFPXPBVH0HJQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HKA1J5ETNQ1FCBMVTQED74HG=%E6%B3%A8%E6%84%8F h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HKA1J5ETNTFKKDF6NC635H3W=%E6%B3%A8%E6%84%8F h_01HKA1J5ETEWJN8MH9NPWTWX0F=%E6%B3%A8%E6%84%8F-1 agencies-collecting-cost-clicks-and-impression-data=%E6%B3%A8%E6%84%8F-1 h_01HKA1J5ETPYE7B2NFPFHA05YT=%E6%B3%A8%E6%84%8F-1" />
