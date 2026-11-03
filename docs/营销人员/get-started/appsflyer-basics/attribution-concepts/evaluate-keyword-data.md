---
title: 关键词数据
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-10-14T10:11:56Z'
  id: 17255366785553
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/17255366785553
---
> **概要：** 获取详细的关键词数据，让您了解哪些搜索词最受欢迎，以便优化自然转化率。

## 关键词数据

有机搜索是您应用程序的一个宝贵流量来源。有机用户不产生获取成本，通常是参与度最高的群体之一。

通过对您的应用页面进行一些调整，可以增加新的自然安装数量。要优化自然搜索，您需要获取应用程序的自然关键词数据。

### iOS 关键词

如果您使用 Apple 搜索广告，您可以获得与 Apple 搜索广告相关的非自然用户的详细关键字数据。在iOS中，无法获取自然关键词数据。

### 安卓关键词

谷歌为执行以下操作的用户提供有机关键词数据（在引用网址上）：

* 使用安卓设备
* 使用Chrome浏览器
* 访问 Google.com 并进行搜索
* 从Google搜索结果页面安装应用
* 启动应用

当SDK从引用者的链接中提取关键词时，如果该链接是指向Google Play的，并且包含Google提供的&utm\_term参数。可能的值包含在以下 AppsFlyer 原始数据字段中：http\_referrer，gp\_broadcast\_referrer，keywords。

预计不到1%的有机Android用户会遵循这个漏斗并拥有有机关键词数据。

在其他情况下，谷歌不分享自然关键词数据。例如，在 Google Play 中搜索的用户没有自然关键词数据。

> 📘 **注意**
>
> 此限制适用于谷歌对所有外部供应商，包括所有归因供应商。

### 使用关键字数据

有机关键词数据可以在以下内容中找到：

* 原始有机数据报告  
  在 AppsFlyer 中，从侧边菜单选择报告 > 原始数据导出，以查看使用的自然关键词的细分情况。
* 高级报告  
  转到透视、保留和群体报告，并按关键字分组。  
  根据关键词比较有机用户的质量。
* 推送API消息

### 测试有机关键词数据

1. 使用允许列表中的Android设备。
2. 打开Chrome浏览器并访问Google.com。
3. 使用强大的关键词搜索您的应用程序。   
   这个例子使用了“今晚的酒店”。  
     

   [<Image alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />](https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg)
4. 点击安装以被重定向到Google Play商店。
5. 安装并启动应用程序。  

   今晚的酒店
6. 在上述描述的 AppsFlyer 源中搜索关键字。

<div data-zendesk-anchors="keyword-data=%E5%85%B3%E9%94%AE%E8%AF%8D%E6%95%B0%E6%8D%AE h_01HKA1D1TW1R20X6K05Q9GX904=%E5%85%B3%E9%94%AE%E8%AF%8D%E6%95%B0%E6%8D%AE ios-keywords=ios-%E5%85%B3%E9%94%AE%E8%AF%8D h_01HKA1D1TW9YXBMGERHW4EHZZN=ios-%E5%85%B3%E9%94%AE%E8%AF%8D android-keywords=%E5%AE%89%E5%8D%93%E5%85%B3%E9%94%AE%E8%AF%8D h_01HKA1D1TWT1VQ6NZ789BTCZJX=%E5%AE%89%E5%8D%93%E5%85%B3%E9%94%AE%E8%AF%8D h_01HKA1D1TW7E2RM7SXC9R5SA99=%E6%B3%A8%E6%84%8F using-the%C2%A0keyword%C2%A0data=%E4%BD%BF%E7%94%A8%E5%85%B3%E9%94%AE%E5%AD%97%E6%95%B0%E6%8D%AE h_01HKA1D1TWRPGTNGJKF7T1R71B=%E4%BD%BF%E7%94%A8%E5%85%B3%E9%94%AE%E5%AD%97%E6%95%B0%E6%8D%AE testing-organic%C2%A0keyword%C2%A0data=%E6%B5%8B%E8%AF%95%E6%9C%89%E6%9C%BA%E5%85%B3%E9%94%AE%E8%AF%8D%E6%95%B0%E6%8D%AE h_01HKA1D1TW5W9A72V2NMPX932H=%E6%B5%8B%E8%AF%95%E6%9C%89%E6%9C%BA%E5%85%B3%E9%94%AE%E8%AF%8D%E6%95%B0%E6%8D%AE" />
