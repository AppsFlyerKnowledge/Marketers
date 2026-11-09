---
title: 会出现在原始数据报告中。
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-10-14T10:08:51Z'
  id: 360001917778
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001917778
---
> **概要**：您可以通过Data Locker拉取原始数据报告

<div id="pba-raw-data-reports" />

## 会出现在原始数据报告中。


|  | <span id="report-descriptions"></span>说明 |
| --- | --- |
| <span id="website-visits"></span>[网页访问量](#website-visits-and-website-events) |  |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/zh/docs/pba-website-attribution-dashboard">网页事件</Anchor> | <ul><li>AF将事件归因到过去30天内的末次间接网页访问。</li></ul> |



* <span id="sample-reports"></span><span id="website-visits-and-website-events"></span><span id="raw-data-report-fields"></span><span id="rawdata-report-fields"></span>网页事件<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* 网页访问量[CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)


| <span id="field-release-notes"></span><span id="field-list-website-visits-and-website-events-report"></span><span id="website-visits-events"></span>字段名称 | 说明 | 格式 | 示例 |
| --- | --- | --- | --- |
| advertising\_id | 广告 ID (GAID) | 字符串 | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id |  | 字符串 | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | Amazon Fire 电视广告 ID | 字符串 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | 安卓设备ID | 字符串 | 68999980-58f9-4ca6-8743-c0d633364b6d |
| app\_id |  | 字符串 | id123456789 |
| app\_name |  | 字符串 | 我的应用程序 |
| app\_version |  | 字符串 | 6.32 |
| appsflyer\_id |  | 字符串 | 1594825729709-5655157112349378588 |
| attributed\_touch\_time |  | yyyy-mm-dd hh:mm:ss | 21 |
| attributed\_touch\_type |  | 字符串 | 网络访问 |
| bundle\_id |  | 字符串 | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaign |  | 字符串 |  |
| campaign\_id |  | 字符串 | 12343425 |
| city |  | 字符串 |  |
| country\_code |  | 字符串 | US |
| customer\_user\_id |  | 字符串 | 5a8771ecbb986ABC |
| device\_type |  | 字符串 | PC端 |
| dma |  | 字符串 | 501 |
| event\_name |  | 字符串 | 记录负收入 |
| event\_revenue |  | 字符串 | 199.99 |
| event\_revenue\_currency |  | 字符串 |  |
| event\_revenue\_usd | 换算成USD的收入金额 | 字符串 | 57.46 |
| event\_source |  | 字符串 |  |
| event\_time |  | yyyy-mm-dd hh:mm:ss | 21 |
| event\_type | 请做如下操作： | 字符串 | 转化事件 |
| event\_url | 产生事件的网页的URL（相当于网站访问中的Original URL） | 字符串 | http://www.brandpit.com/checkout |
| event\_value | 网页事件网页访问量总是显示为null | JSON | \{"sku":"ABC123", “color": "blue", "unit\_price":3.99,"currency":USD |
| idfa |  | 字符串 | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv |  | 字符串 | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | 设备标识符 | 字符串 | 3532211234 |
| install\_time |  | yyyy-mm-dd hh:mm:ss | 21 |
| ip |  | 字符串 | 24.7.104.115 |
| language |  | 字符串 | 中文 |
| media\_channel |  | 字符串 | Ad |
| media\_source |  | 字符串 | googleadwords\_int |
| media\_type |  | 字符串 | 已付 |
| oaid |  | 字符串 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url |  | 字符串 | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| platform |  | 字符串 | macOS |
| postal\_code |  | 字符串 | 10977 |
| query\_params | 跳转URL中“？”号之后的查询参数 | JSON |  |
| \_referrer |  | 字符串 | https://www.google.com/ |
| region |  | 字符串 | 不适用 |
| state |  | 字符串 |  |


| Date | 报告 | 更新内容 |
| --- | --- | --- |
| 2020-11-18 | 网页事件<br /><br />网页访问量 |  |
| 2020-10-04 | 网页到应用 | <ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |


<div id="application-note-downloading-and-combining-data-locker-files" />

<div id="use-cases-for-pba-and-mobile" />

<div id="combining-pba-and-mobile-data" />

<div id="setting-up-pba-reports-in-data-locker" />

<div id="procedures" />

### 配置流程

1. 从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。
3. **点击保存配置。**


**解决方案：**



**前期准备** ：

1. <Image align="center" alt="Duck_us-en.jpg" src="https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg" />

**前期准备：**

2. 请注意：   

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```

<div data-zendesk-anchors="pba-raw-data-reports=%E4%BC%9A%E5%87%BA%E7%8E%B0%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD h_01HKW341NVTCP4FY5G4TC94MZY=%E4%BC%9A%E5%87%BA%E7%8E%B0%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD h_01HKW341NVC83ZC3HCH86QBJYG=report-descriptions sample-reports=rawdata-report-fields h_01HKW341NVNYM1AGFC8GHV7VR2=rawdata-report-fields h_01HKW341NVX51NQFAA79BD7MF3=rawdata-report-fields field-list-website-visits-and-website-events-report=website-visits-events h_01J53BGNDSQCCFV1VQA8EV50GR=website-visits-events procedures=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HKW341NWXQ19ZB5QXZK84VMQ=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B use-cases-for-pba-and-mobile=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HKW341NXTXX4FJ2ZZQFZ2V85=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B" />
