---
title: 适用于iOS的URI scheme备用方案
metadata:
  keywords:
    - Advertisers
    - Redirects
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
  created_at: '2017-05-10T12:50:00Z'
  edited_at: '2026-10-14T10:08:53Z'
  id: 115002366466
  locale: zh-cn
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/zh-cn/articles/115002366466
---
> **概要：** 本文说明了iOS用户点击OneLink自定义链接后，Universal Link未能调起应用时的用户链路。

<div id="note" />

<div id="about-uri-fallback-for-ios" />

## 适用于iOS的URI备用方案简介

* Universal Link是在iOS设备上调起应用的最佳方案。自2016年iOS系统升级后，作为Universal Link备用方案的URI scheme开始受到诸多限制。这些限制是操作系统内置的，与AppsFlyer无关。如果您在其他链接中使用URI scheme调起应用，这些链接也会受到影响。
* 默认情况下，URI scheme（通过af\_dp参数的值来表达）仅用作调起应用的备用方案，适用于iOS中的少数特定浏览器/平台。
* 对于Safari，您可以尝试在OneLink链接中配置下列参数，使用URI scheme作为iOS中调起应用的备用方案：
  * `af_dp`（参数值为URI scheme）。
  * `af_force_deeplink=true`（通过af\_dp参数中的URI scheme强制调起应用）。该参数缺失时，系统不会通过URI scheme调起相关应用。
* 由于URI scheme的稳定性不强，因此其他浏览器默认不支持这种应用调起方式。这时，用户点击相关链接后很可能会跳转到App Store（如果您在链接中设置了参数，则跳转到该参数指定的网址）。
* 详情请见下文的用户链路图和使用场景说明。

<div id="scenarios-flowchart" />

### 用户链路图

<div id="use-cases" />

## 使用场景

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="默认支持URI scheme的浏览器">

某些情况下，Universal Link会因为相关应用不存在或链接中未配置Universal Link而无法调起应用。这时，下列浏览器/平台可默认使用URI scheme作为备用方案调起应用：

* Chrome
* X（前身为Twitter）  
  **请注意**：如果用户未安装相关应用，界面会弹出报错消息。用户关闭该消息后，会跳转到App Store（或af\_ios\_url参数中的网址）。
* Kakaotalk
* Naver
* Naver-Blog
* 微博

<div id="flowchart" />

#### **链路图**

![Copy_of_Ios_fall_back_-_browsers_that_can_use_URI_schemes_by_default__2_.png](https://files.readme.io/0059288afb39247fd2d08ff2a1d1bef6f43d958b7f5d20bc921a431b65dacc58-51911709482641.png)

</Accordion>

<div id="safari" />

<Accordion title="Safari浏览器">

如果Universal Link未能调起应用，而相关链接中配置了`af_dp`参数（参数值为URI scheme），这时的用户链路如下文所述。

**用户未安装相关应用：**

1. Safari界面会弹出报错消息。  
   [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
2. 用户点击**OK**关闭该对话框后，会短暂地看到在背景中加载的落地页，并会在1秒内自动跳转到App Store或af\_ios\_ur参数中指定的网址。

**若用户已安装相关应用：**

* 如果链接中没有`af_force_deeplink=true`，则用户会跳转到App Store，或af\_ios\_url参数中指定的网址。
* 如果链接中包含`af_force_deeplink=true`：
  1. Safari界面会弹出下图对话框。  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  2. 如果用户点击**Open**（打开），就会打开相关应用。
  3. 如果用户点击**Cancel**（取消）：
     * 如果链接中设置了af\_ios\_url参数，则用户会跳转到相应的网址。
     * [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
  4. 用户点击**OK**后会看到带有CTA按钮的落地页。
  5. 用户点击CTA按钮后，界面会显示下图对话框。  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  6. 如果用户点击**Open**（打开），就会打开相关应用。
  7. 如果用户点击**Cancel**（取消），界面会显示下图对话框。  
     [![](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)
  8. 如果用户点击**OK**，就会跳转到App Store。
  9. 如果用户点击**Cancel**（取消），就会留在落地页中。

<div id="flowchart-1" />

#### **链路图**

![Copy_of_Ios_fall_back_-_safari.png](https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png)

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Facebook帖子—自有媒体">

`af_dp`如果Universal Link未能调起应用，而相关链接中配置了af\_dp参数（参数值为URI scheme），这时的用户链路如下文所述。

**若用户已安装相关应用：**

* 用户点击链接后，相关应用随即打开。

**若用户未安装相关应用**：

1. 若您未配置社交媒体应用的落地页，或用户点击了社媒应用落地页（SALP）中的CTA按钮，界面会显示下图对话框，并在背景中加载落地页。  
   [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
2. 用户点击“Open App”（打开应用）后，会根据链接配置触发以下任一链路：
   * 如果链接中设置了`af_ios_url`参数，则用户会跳转到该参数指定的网址。
   * 如果链接中既未设置`af_ios_url`参数，也不包含`af_force_deeplink=true`，则用户会跳转到App Store。
   * 如果链接中未设置af\_ios\_url参数，但包含`af_force_deeplink=true`，则界面会再次弹出下图对话框，并在背景中加载落地页。  
     [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
3. 如果用户点击**Open**（打开），就会跳转到App Store。
4. 如果用户点击**Close**（关闭），则界面会显示背景中的落地页。  
   [![](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)
5. 用户点击App Store徽章后跳转到App Store。

<div id="flowchart-2" />

#### **链路图**

![diagram-X.png](https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png)

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=%E9%80%82%E7%94%A8%E4%BA%8Eios%E7%9A%84uri%E5%A4%87%E7%94%A8%E6%96%B9%E6%A1%88%E7%AE%80%E4%BB%8B h_01HFV6PXS5401CCW6N2T04HGSM=%E9%80%82%E7%94%A8%E4%BA%8Eios%E7%9A%84uri%E5%A4%87%E7%94%A8%E6%96%B9%E6%A1%88%E7%AE%80%E4%BB%8B scenarios-flowchart=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%9B%BE h_01HFV6PXS5WWS0B1VYF7RJAV1J=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%9B%BE use-cases=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01HFV6PXS51B2W497TADRGBX7Y=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default flowchart=%E9%93%BE%E8%B7%AF%E5%9B%BE h_01HFV6PXS5N98MHJFYPSAB5XKZ=%E9%93%BE%E8%B7%AF%E5%9B%BE h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=%E9%93%BE%E8%B7%AF%E5%9B%BE-1 h_01HFV6PXS57ZRSX2WAECS69XB4=%E9%93%BE%E8%B7%AF%E5%9B%BE-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=%E9%93%BE%E8%B7%AF%E5%9B%BE-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=%E9%93%BE%E8%B7%AF%E5%9B%BE-2" />
