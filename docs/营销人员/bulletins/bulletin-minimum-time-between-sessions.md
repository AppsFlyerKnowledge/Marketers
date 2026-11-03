---
title: 公告：应用会话时间间隔
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2021-01-03T11:28:55Z'
  edited_at: '2026-10-14T10:04:31Z'
  id: 360016827858
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/360016827858
---

<Table>
  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        生效日期
      </td>
      <td>
        2023年2月1日
      </td>
    </tr>
    <tr>
      <td>
        **更新内容**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        * 1-60分钟
        * 0-24小时

        ![MinimumTimeBetweenSessions_us-en.jpg](https://files.readme.io/12bc7191a11dda474f57055a6cf5ce6bb69b3772ad33a2a0c7bfabc51e4c07ce-360015918477.jpg)

        **比如**

        | 示例 |  | 统计的session数量 | 被忽略的session |
        | --- | --- | --- | --- |
        | A | 0, 10, 20, 30 | 4 | 无 |
        | B | 0, 1, 9, 11 | 2 | 21 |
        | C | iOS回传延时：[24 + 48 ] / 2 = 36. | 3 | 15 |
      </td>
    </tr>
    <tr>
      <td>
        保留内容
      </td>
      <td>
        * 指标：
          * 每日活跃用户（DAU）
          * Monthly active users（MAU，每月活跃用户）
          * 留存
          * 忠实用户数（以完成3次应用打开的默认标准计算）
        * 用于再互动转化

        特别是对于一般情况下用户每天打开一次的应用来说，影响尤为突出。
      </td>
    </tr>
    <tr>
      <td>
        **![Action_icon.png](https://files.readme.io/f6066b9dee413eea63c6a0bf04b627e3cef6a6fb21a6ca23634e615d3be1950d-360015730138.png)**
      </td>
      <td>
        1. 从AppsFlyer后台进入**配置** > **应用配置**。
        2. 设置**session之间的最短间隔**。
        3. 点击**保存配置**。   
           新的配置会在一小时内生效。
      </td>
    </tr>
  </tbody>
</Table>
