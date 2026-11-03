---
title: 掩盖IP
metadata:
  keywords:
    - IP masking
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2026-10-14T10:12:31Z'
  id: 208879066
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/208879066
---
> **概要：**

## 掩盖IP

> 📘 **注意**
>
> * 如果您在应用配置中打开了<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem数据共享">掩盖IP地址的开关</Anchor>，则S2S和SDK事件都不支持AEM数据共享，也就是说不会与Meta ads共享数据。

> 📄 **示例**
>
> 应用安装
>
>
>
> | Install date | User ID | IP address（IP地址） |
> | --- | --- | --- |
> | 1月2日 | 用户A | 192.0.2.1 |
> | 1月18日 | 用户B | 192.0.2.33 |
> | 1月14日 | 用户C | 203.0.113.1 |
>
>
>
> | Date |  |  |
> | --- | --- | --- |
> | 1月1日 | 停用 | 用户A |
> | 1月2日 | 启用 | 用户A |
> | 1月18日 | 启用 | 用户A  <br />用户B |
> | 1月18日 | 停用 | 用户A  <br />用户B |
> | 1月15日 | 停用 | 用户A  <br />用户B  <br />用户C |


启用 IP 屏蔽

1. 从AppsFlyer后台的侧边栏中选择**配置** > 应用配置。

## 在原始数据报告中启用IP屏蔽

![ip_masking.png](https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png)

<div data-zendesk-anchors="ip-masking=%E6%8E%A9%E7%9B%96ip h_01HA91HHADCTT7QS2K79TJEY2C=%E6%8E%A9%E7%9B%96ip h_01HA92HF3ZYR2NBTXQ1S2AHCAA=%E6%B3%A8%E6%84%8F h_01HA91HHAD7BCXRZW6AD9NRDBN=%E7%A4%BA%E4%BE%8B enabling-ip-masking=%E7%A4%BA%E4%BE%8B h_01HA91HHAEM220CE8805GFQYKR=%E7%A4%BA%E4%BE%8B ip-masking-in-raw-data-reports=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E5%90%AF%E7%94%A8ip%E5%B1%8F%E8%94%BD h_01HA91HHAE14D6ES1ERNK93VY9=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E5%90%AF%E7%94%A8ip%E5%B1%8F%E8%94%BD" />
