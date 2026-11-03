---
title: 公告：广告交互类型
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-10-14T10:02:56Z'
  id: 20161875390865
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/20161875390865
---

<Table>
  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>
        原始数据报告中新增下列字段：

        * engagement\_type
        * contributor1\_engagement\_type
        * contributor2\_engagement\_type
        * contributor3\_engagement\_type

        这些参数可返回下列参数值：preload、click\_to\_download、click\_to\_app、engaged\_click、engaged\_view、view、listening或空值（若未上报）

        | **engagement\_type** | **说明** |
        | --- | --- |
        | preload | 相关应用由OEM在设备出厂时预装到设备上，或由服务商在设备首次激活时完成预装。也可以在设备首次激活时通过向导对话框引导用户下载相关应用。 |
        | click\_to\_download | 如果用户与广告进行了互动，相关应用会自动下载并安装到用户设备中，无需跳转到应用商店。 |
        | click\_to\_app | 用户点击广告、扫描二维码、通过深度链接或其它类型的点击后跳转到应用中，或跳转到对应的应用商店中下载相关应用。 |
        | engaged\_click | 用户完成点击后停留在原来的网页环境中与广告进行互动，不跳转到应用商店或调起应用。 |
        | engaged\_view | 表示发生了较为重要的深度浏览。比如用户观看可跳过的视频广告达10秒或以上，或视频完播。 |
        | view | 广告呈现并完成展示，即记为一次广告浏览（ad view）。比如横幅、插屏或非互动视频。 |
        | listening | 指用户聆听音频广告，如播客广告。 |
      </td>
    </tr>
    <tr>
      <td>
        **生效日期**
      </td>
      <td>
        2024年1月17日
      </td>
    </tr>
    <tr>
      <td>
        **影响范围**
      </td>
      <td>
        * 同时符合以下条件的广告主与代理会看到这些新增字段：1）具有原始数据报告的访问权限；2）合作广告平台上报这些字段。
          * 无论广告平台是否上报上述字段，深度链接的参数值preload和click\_to\_app总是由AppsFlyer填充。
        * 此变更对下列数据传输工具中的原始数据报告生效：Data Locker、Pull API、导出数据页和Push API。
          * 这些字段并非默认选定（Push API中的“全选”选项除外），因此您需要在原始数据报告中手动勾选后方可使用这些字段。
      </td>
    </tr>
  </tbody>
</Table>
